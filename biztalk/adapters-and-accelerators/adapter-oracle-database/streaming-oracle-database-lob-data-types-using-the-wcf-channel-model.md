---
title: WCF チャネル モデルを使用して Oracle データベース LOB データ型のストリーミング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- streaming, Oracle LOB data types
- WCF channel model, streaming Oracle LOB data types
ms.assetid: 513a7cb8-495d-4019-bce1-b5babca3629f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa8a493c94761ce74d76885ee59fae1425c15523
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013843"
---
# <a name="streaming-oracle-database-lob-data-types-using-the-wcf-channel-model"></a>ストリーミングの Oracle データベース LOB データ型 WCF チャネル モデルを使用します。
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] LOB データの特定の操作のエンド ツー エンドのストリーミングをサポートしています。 このトピックのセクションでは、WCF チャネル モデルを使用すると、LOB データのストリーミングを実装する方法について説明します。  
  
 背景情報アダプターが LOB データ型のストリーミングがサポートする方法については、次を参照してください。 [Oracle データベース アダプターのラージ オブジェクト データ型のストリーミング](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md)します。 続行する前に、このトピックを確認してください。  
  
 LOB データのストリーミングを示すサンプルに含まれる SDK サンプルでは、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。 詳細については、次を参照してください。 [SDK 内のサンプル](../../core/samples-in-the-sdk.md)します。  
  
## <a name="streaming-outbound-messages-to-the-adapter"></a>アダプターに送信メッセージのストリーミング  
 アダプターでは、エンド ツー エンドの LOB データのストリーミング UpdateLOB 操作の要求メッセージをサポートしています。  
  
 WCF チャネル モデルで UpdateLOB 操作に関するエンド ツー エンドのストリーミングをサポートするには、次の操作をする必要があります。  
  
1.  設定、 **UseAmbientTransaction**プロパティを true にバインドします。  
  
2.  実装を**System.ServiceModel.Channels.BodyWriter**ことができる (ノード値の LOB データのストリーミングを実行する) LOB データをストリーミングします。  
  
3.  トランザクション スコープ内で UpdateLOB 操作を実行します。  
  
4.  作成、 **System.ServiceModel.Message**このメッセージ本文を指定して、操作を呼び出すために使用**BodyWriter**の適切なオーバー ロードを使用して、 **Message.Create**メソッド。  
  
### <a name="setting-the-useambienttransaction-binding-property"></a>プロパティのバインド UseAmbientTransaction の設定  
 次の例のバインドを作成する方法を示しています、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]設定と、 **UseAmbientTransaction**プロパティをバインドします。  
  
```  
// Create binding  
OracleDBBinding odbBinding = new OracleDBBinding();  
  
//set the binding property  
binding.UseAmbientTransaction = true;  
  
```  
  
### <a name="implementing-a-bodywriter"></a>BodyWriter を実装します。  
 次の例の実装を示しています、 **BodyWriter**ノード値のストリーミングを実行します。  
  
```  
/// <summary>  
/// This class overrides the OnWriteBodyContents function to do node-value streaming  
/// </summary>  
class StreamingBodyWriter : BodyWriter, IDisposable  
{  
    XmlReader m_reader = null;  
  
    int m_chunkSize;  
    /// <summary>  
    /// Initializes the body writer  
    /// </summary>  
    /// <param name="reader">Reader for input</param>  
    /// <param name="chunkSize">The chunksize in which the data is passed to adapter</param>  
    public StreamingBodyWriter(XmlReader reader, int chunkSize)  
        : base(false)  
    {  
        m_reader = reader;  
        if (chunkSize \<= 0)  
            throw new ApplicationException("ChunkSize should be a positive value");  
        m_chunkSize = chunkSize;  
    }  
  
    protected override void OnWriteBodyContents(XmlDictionaryWriter writer)  
    {  
        if (m_reader == null)  
            throw new ApplicationException("Reader cannot be null");  
  
        while (m_reader.Read())  
        {  
            switch (m_reader.NodeType)  
            {  
                case XmlNodeType.Element:  
                    writer.WriteStartElement(m_reader.LocalName, m_reader.NamespaceURI);  
                    break;  
                case XmlNodeType.Text:  
                    #region Streaming Code  
                    char[] tempBuffer = new char[m_chunkSize];  
                    int length = 0;  
                    while ((length = m_reader.ReadValueChunk(tempBuffer, 0, m_chunkSize)) > 0)  
                    {  
                        writer.WriteString(new String(tempBuffer, 0, length));  
                    }  
                    #endregion  
                    break;  
                case XmlNodeType.EndElement:  
                    writer.WriteEndElement();  
                    break;  
            }  
        }  
  
    }  
  
    #region IDisposable Members  
  
    public void Dispose()  
    {  
        if (m_reader != null)  
        {  
            m_reader.Close();  
            m_reader = null;  
        }  
    }  
  
    #endregion  
}  
```  
  
### <a name="perform-the-operations-within-a-transaction-scope"></a>トランザクション スコープ内で操作を実行します。  
 次の例では、トランザクション スコープ内での操作を実行する方法を示します。  
  
```  
// Create a transaction scope  
using(TransactionScope tx = new TransactionScope())  
{  
  // perform operations within the transaction  
  // ...  
  // ...  
  
  //Complete the transaction  
  tx.Complete()  
}  
  
```  
  
### <a name="creating-a-message-by-using-a-bodywriter"></a>BodyWriter によるメッセージの作成  
 次の例では、使用して UpdateLOB 要求メッセージを作成する方法を示しています、 **BodyWriter**前の例です。 メッセージのデータは、ファイルから読み取られます。  
  
```  
// Create a transaction scope  
using(TransactionScope tx = new TransactionScope())  
{  
    XmlReader readerIn = XmlReader.Create ("updatelob.xml");  
    // StreamingBodyWrtier class is responsible for streaming  
    StreamingBodyWriter stBW = new StreamingBodyWriter(readerIn, chunkSize);  
  
    Message InputMsg = Message.CreateMessage(MessageVersion.Default,  
    "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER/UpdateLOB",   
    stBW);  
  
    //Send the request message and get the output message  
    OutputMsg = channel.Request(InputMsg);  
  
    tx.Complete();  
}  
  
```  
  
## <a name="streaming-inbound-messages-from-the-adapter"></a>アダプターから受信メッセージのストリーミング  
 アダプターには、エンド ツー エンドの LOB データが次の受信メッセージのストリーミングがサポートされています。  
  
- 応答メッセージを持つ関数または LOB データが含まれている IN OUT パラメーター。 レコードの種類のパラメーターが LOB データの列を含めることができますに注意してください。  
  
- LOB データが含まれている関数を REF CURSOR パラメーター (または戻り値) の応答メッセージ。 これには、出力側 REF CURSOR を IN パラメーターにはが含まれます。  
  
- プロシージャの応答メッセージまたは LOB データが含まれている IN OUT パラメーター。 レコードの種類のパラメーターが LOB データの列を含めることができますに注意してください。  
  
- LOB データを含む OUT REF CURSOR パラメーターを含むプロシージャの応答メッセージ。 これにより、出力側 REF CURSOR を IN パラメーターにはが含まれます。  
  
- LOB データを含む結果セットを返す SQLEXECUTE 操作の応答メッセージ。  
  
- LOB データを返す結果のテーブルまたはビューの Select 操作の応答メッセージを設定します。  
  
- (受信) POLLINGSTMT 操作の要求メッセージ  
  
  WCF チャネル モデル内の受信メッセージのエンド ツー エンドのストリーミングをサポートするには、次の操作をする必要があります。  
  
1.  実装を**System.Xml.XmlDictionaryWriter**ことができる (ノード値の LOB データのストリーミングを実行する) LOB データをストリーミングします。  
  
2.  使用、**メッセージ**を呼び出して**WriteBodyContents**メソッドをこの**XmlDictionaryWriter**します。  
  
### <a name="implementing-an-xmldictionarywriter"></a>XmlDictionaryWriter の実装  
 次の例の実装を示しています、 **XmlDictionaryWriter**ノード値のストリーミングを実行します。  
  
```  
using System;  
using System.Xml;  
using System.Text;  
  
class FileXmlWriter : XmlDictionaryWriter  
{  
    XmlTextWriter xts;  
  
    public FileXmlWriter(string file)  
    {  
        xts = new XmlTextWriter(file, Encoding.UTF8);  
    }  
  
    public override void WriteBase64(byte[] buffer, int index, int count)  
    {  
        xts.WriteBase64(buffer, index, count);  
    }  
  
    public override void WriteCData(string text)  
    {  
        xts.WriteCData(text);  
    }  
  
    public override void WriteCharEntity(char ch)  
    {  
        xts.WriteCharEntity(ch);  
    }  
  
    public override void WriteChars(char[] buffer, int index, int count)  
    {  
        xts.WriteChars(buffer, index, count);  
    }  
  
    public override void WriteComment(string text)  
    {  
        xts.WriteComment(text);  
    }  
  
    public override void WriteDocType(string name, string pubid, string sysid, string subset)  
    {  
        xts.WriteDocType(name, pubid, sysid, subset);  
    }  
  
    public override void WriteEndAttribute()  
    {  
        xts.WriteEndAttribute();  
    }  
  
    public override void WriteEndDocument()  
    {  
        xts.WriteEndDocument();  
    }  
  
    public override void WriteEndElement()  
    {  
        xts.WriteEndElement();  
    }  
  
    public override void WriteEntityRef(string name)  
    {  
        xts.WriteEntityRef(name);  
    }  
  
    public override void WriteFullEndElement()  
    {  
        xts.WriteFullEndElement();  
    }  
  
    public override void WriteProcessingInstruction(string name, string text)  
    {  
        xts.WriteProcessingInstruction(name, text);  
    }  
  
    public override void WriteRaw(string data)  
    {  
        xts.WriteRaw(data);  
    }  
  
    public override void WriteRaw(char[] buffer, int index, int count)  
    {  
        xts.WriteRaw(buffer, index, count);  
    }  
  
    public override void WriteStartAttribute(string prefix, string localName, string ns)  
    {  
        xts.WriteStartAttribute(prefix, localName, ns);  
    }  
  
    public override void WriteStartDocument(bool standalone)  
    {  
        xts.WriteStartDocument(standalone);  
    }  
  
    public override void WriteStartDocument()  
    {  
        xts.WriteStartDocument();  
    }  
  
    public override void WriteStartElement(string prefix, string localName, string ns)  
    {  
        xts.WriteStartElement(localName);  
    }  
  
    public override void WriteString(string text)  
    {  
        xts.WriteString(text);  
    }  
  
    public override void WriteSurrogateCharEntity(char lowChar, char highChar)  
    {  
        xts.WriteSurrogateCharEntity(lowChar, highChar);  
    }  
  
    public override void WriteWhitespace(string ws)  
    {  
        xts.WriteWhitespace(ws);  
    }  
  
    public override void Close()  
    {  
        xts.Close();  
    }  
  
    public override void Flush()  
    {  
        xts.Flush();  
    }  
  
    public override string LookupPrefix(string ns)  
    {  
        return xts.LookupPrefix(ns);  
    }  
  
    public override WriteState WriteState  
    {  
        get { return xts.WriteState; }  
    }  
  
}  
```  
  
### <a name="consuming-a-message-by-using-an-xmldictionarywriter"></a>メッセージを使用する XmlDictionaryWriter を使用して、  
 次の例は、応答メッセージを使用してテーブルを使用する方法を示しています、 **FileXmlWriter**前の例で実装します。 (、 **FileWriter**クラスがサブクラス化によって作成された**XmlDictionaryWriter**)。この例では、 **IRequestChannel**選択操作を呼び出すためのチャネル。 チャネルの作成の詳細が省略されています。 要求メッセージは、ファイルから読み取られ、選択の応答メッセージは、ファイルに書き込まれます。  
  
```  
// Read Select message body from a file  
XmlReader readerIn = XmlReader.Create("select.xml");  
Message InputMsg = Message.CreateMessage(MessageVersion.Default,  
    "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER/Select", readerIn);  
  
Message OutputMsg = channel.Request(InputMsg);  
  
// Streaming response message to select_output.xml using the custom XmlDictionaryWriter;  
FileXmlWriter fileXmlWriter = new FileXmlWriter("select_output.xml");  
OutputMsg.WriteBodyContents(fileXmlWriter);  
fileXmlWriter.Flush();  
fileXmlWriter.Close();  
  
// Streaming complete close output message;  
OutputMsg.Close();  
```  
  
 次の XML では、選択操作の要求メッセージ (select.xml ファイルの内容) を表示します。 CUSTOMER テーブルには、写真をという名前の BLOB 列が含まれています。  
  
```  
<Select xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER">  
  <COLUMN_NAMES>*</COLUMN_NAMES>  
  <FILTER>NAME='Kim Ralls'</FILTER>  
</Select>  
```  
  
## <a name="see-also"></a>参照  
 [WCF チャネル モデルを使用して Oracle データベース アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)