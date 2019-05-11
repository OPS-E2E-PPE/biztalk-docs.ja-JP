---
title: WCF チャネル モデルを使用して SAP でのフラット ファイル Idoc を Stream |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF channel model, streaming flat-file IDOCs
ms.assetid: 5010e215-d8d0-47c8-93a6-20cfdeff2951
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf0b2c0cd8fe401e8d410c8827d2d3ed7547edab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372773"
---
# <a name="stream-flat-file-idocs-in-sap-using-the-wcf-channel-model"></a>WCF チャネル モデルを使用して SAP でのフラット ファイル Idoc の Stream
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]ノード値のストリーミング、SendIdoc および ReceiveIdoc 操作をサポートしています。 これらの操作は、フラット ファイル (string) Idoc とアダプターの間の送受信に使用されます。 1 つのノードの下の文字列にこれらの操作の両方で全体の IDOC のデータが含まれている (\<idocData\>)。 大規模の Idoc は、アダプターと、コードの間、IDOC データのストリーミングは、大量のメモリ リソースに保存できます。  
  
 アダプターがストリーミングをサポートする方法の詳細については、次を参照してください。[ストリーミングと SAP アダプター](../../adapters-and-accelerators/adapter-sap/streaming-and-the-sap-adapter.md)します。 続行する前に、このトピックを確認してください。  
  
 このトピックのセクションでは、ノードと値の WCF チャネル モデルを使用すると、SendIdoc および ReceiveIdoc 操作のストリーミングを実装する方法について説明します。  
  
## <a name="streaming-outbound-flat-file-idocs-to-the-adapter"></a>送信フラット ファイル Idoc をアダプターにストリーミング  
 アダプターは、ノード値 SendIdoc 操作の要求メッセージのストリーミングをサポートします。  
  
 ノード値 SendIdoc 操作 WCF チャネル モデルでのストリーミングをサポートするためには、次の必要があります。  
  
1.  実装を**System.ServiceModel.Channels.BodyWriter**ことができる (ノード値の IDOC のデータのストリーミングを実行する) IDOC データをストリーミングします。  
  
2.  作成、 **System.ServiceModel.Message**このメッセージ本文を指定して、操作を呼び出すために使用**BodyWriter**の適切なオーバー ロードを使用して、 **Message.Create**メソッド。  
  
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
        if (chunkSize <= 0)  
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
  
### <a name="creating-a-message-by-using-a-bodywriter"></a>BodyWriter によるメッセージの作成  
 次の例は、SendIdoc 要求メッセージを作成する方法を示しています、 **BodyWriter**前の例です。 メッセージのデータは、ファイルから読み取られます。  
  
```  
XmlReader readerIn = XmlReader.Create ("sendidoc.xml");  
// StreamingBodyWrtier class is responsible for streaming  
StreamingBodyWriter stBW = new StreamingBodyWriter(readerIn, chunkSize);  
  
Message InputMsg = Message.CreateMessage(MessageVersion.Default,  
    "http://Microsoft.LobServices.SAP/2007/03/Idoc/SendIdoc",   
    stBW);  
  
```  
  
## <a name="streaming-inbound-flat-file-idocs-from-the-adapter"></a>アダプターからの着信フラット ファイル Idoc のストリーミング  
 受信 ReceiveIdoc 操作では、フラット ファイル Idoc を受信します。 アダプターは、ノード値 ReceiveIdoc 操作の要求メッセージのストリーミングをサポートします。  
  
 ノード値 ReceiveIdoc 操作 WCF チャネル モデルでのストリーミングをサポートするためには、次の必要があります。  
  
1.  実装を**System.Xml.XmlDictionaryWriter**ことができる (ノード値の IDOC のデータのストリーミングを実行する) IDOC データをストリーミングします。  
  
2.  使用、**メッセージ**を呼び出すことによってその**WriteBodyContents**メソッドをこの**XmlDictionaryWriter**します。  
  
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
 次の例では、使用して ReceiveIdoc 要求メッセージを使用する方法を示しています、 **FileXmlWriter**前の例で実装します。 (、 **FileWriter**クラスがサブクラス化によって作成された**XmlDictionaryWriter**)。この例では、 **IReplyChannel** ReceiveIdoc 操作を受信するチャネル。 チャネルの作成の詳細が省略されています。 ReceiveIdoc 要求メッセージは、ファイルに書き込まれます。  
  
```  
// Receive the ReceiveIdoc request message from the adapter.  
RequestContext rc = channel.ReceiveRequest();  
Message inputMsg = rc.RequestMessage;  
  
// Stream the request message to received_idoc.xml using the custom XmlDictionaryWriter.  
FileXmlWriter fileXmlWriter = new FileXmlWriter("received_idoc.xml");  
inputMsg.WriteBodyContents(fileXmlWriter);  
fileXmlWriter.Flush();  
fileXmlWriter.Close();  
  
```  
  
## <a name="see-also"></a>参照  
[WCF チャネル モデルを使用してアプリケーションを開発する](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)