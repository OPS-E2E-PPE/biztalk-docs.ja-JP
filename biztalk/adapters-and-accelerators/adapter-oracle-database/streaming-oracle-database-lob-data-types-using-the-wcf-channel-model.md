---
title: WCF チャネル モデルを使用して Oracle データベース LOB データ型をストリーミング |Microsoft ドキュメント
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
ms.openlocfilehash: bf0ee2f8d1c90f69a206a3006398d52e67f819e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215794"
---
# <a name="streaming-oracle-database-lob-data-types-using-the-wcf-channel-model"></a>ストリーミングの Oracle データベース LOB データ型 WCF チャネル モデルを使用します。
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]エンド ツー エンドの特定の操作の LOB データのストリーミングをサポートしています。 このトピックのセクションでは、WCF チャネル モデルを使用すると、LOB データのストリーミングを実装する方法について説明します。  
  
 アダプターが LOB データ型のストリーミングをサポートする方法の詳細については、次を参照してください。 [Oracle データベース アダプターのラージ オブジェクト データ型をストリーミング](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md)です。 続行する前にこのトピックの内容を確認してください。  
  
 LOB データのストリーミングを示すサンプルに含まれている SDK のサンプルで使用できる、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。 詳細については、次を参照してください。 [SDK 内のサンプル](../../core/samples-in-the-sdk.md)です。  
  
## <a name="streaming-outbound-messages-to-the-adapter"></a>アダプターに送信メッセージのストリーミング  
 アダプターは、エンド ツー エンドの LOB データ UpdateLOB 操作の要求メッセージのストリーミングをサポートします。  
  
 ストリーミングをサポートするエンド ツー エンド WCF チャネル モデルで UpdateLOB 操作で、次の操作を行う必要があります。  
  
1.  設定、 **UseAmbientTransaction**バインディング プロパティを true に設定します。  
  
2.  実装する**System.ServiceModel.Channels.BodyWriter**が (ノード値の LOB データのストリーミングを実行中) の LOB データをストリーミング可能です。  
  
3.  トランザクションのスコープ内で UpdateLOB 操作を実行します。  
  
4.  作成、 **System.ServiceModel.Message**これを使用してメッセージ本文を指定することによって、操作を呼び出すために使用**BodyWriter**の適切なオーバー ロードを使用して、 **Message.Create**メソッドです。  
  
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
  
### <a name="perform-the-operations-within-a-transaction-scope"></a>トランザクションのスコープ内での操作を実行します。  
 次の例では、トランザクション スコープ内で操作を実行する方法を示します。  
  
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
 次の例は、UpdateLOB 要求を使用してメッセージを作成する方法を示します、 **BodyWriter**前の例です。 メッセージのデータは、ファイルから読み取られます。  
  
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
 アダプターには、次の受信メッセージのストリーミング エンド ツー エンドの LOB データがサポートされています。  
  
-   出力を持つ関数の応答メッセージまたは LOB データを含む IN OUT パラメーターです。 レコード型のパラメーターが LOB データの列を含めることができますに注意してください。  
  
-   LOB データを含む関数の REF CURSOR 出力パラメーター (または戻り値) の応答メッセージ。 これには、REF CURSOR を IN パラメーターの出力側が含まれます。  
  
-   プロシージャの応答メッセージまたは LOB データを含む IN OUT パラメーターです。 レコード型のパラメーターが LOB データの列を含めることができますに注意してください。  
  
-   LOB データを含む REF CURSOR 出力パラメーターを含むプロシージャの応答メッセージ。 出力側 REF CURSOR を IN パラメーターにはが含まれます  
  
-   LOB データを含む結果セットを返す SQLEXECUTE 操作の応答メッセージ。  
  
-   LOB データを返す結果のテーブルまたはビューの Select 操作の応答メッセージを設定します。  
  
-   要求操作のメッセージ (受信) POLLINGSTMT  
  
 WCF チャネル モデルで受信メッセージのエンド ツー エンドのストリーミングをサポートする必要があります。  
  
1.  実装する**System.Xml.XmlDictionaryWriter**が (ノード値の LOB データのストリーミングを実行中) の LOB データをストリーミング可能です。  
  
2.  使用する、**メッセージ**を呼び出すことによって**WriteBodyContents**メソッドをこの**XmlDictionaryWriter**です。  
  
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
 次の例は、応答メッセージを使用してテーブルを使用する方法を示しています、 **FileXmlWriter**前の例で実装します。 (、 **FileWriter**サブクラスによってクラスが作成された**XmlDictionaryWriter**)。この例では、 **IRequestChannel**選択操作を呼び出すためのチャネル。 チャネルの作成の詳細が省略されています。 要求メッセージはファイルから読み取られ、応答メッセージは、ファイルに書き込まれます。  
  
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
  
 次の XML では、Select 操作の要求メッセージ (select.xml ファイルの内容) を表示します。 CUSTOMER テーブルには、写真をという名前の BLOB 列が含まれています。  
  
```  
<Select xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER">  
  <COLUMN_NAMES>*</COLUMN_NAMES>  
  <FILTER>NAME='Kim Ralls'</FILTER>  
</Select>  
```  
  
## <a name="see-also"></a>参照  
 [WCF チャネル モデルを使用して Oracle データベース アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)