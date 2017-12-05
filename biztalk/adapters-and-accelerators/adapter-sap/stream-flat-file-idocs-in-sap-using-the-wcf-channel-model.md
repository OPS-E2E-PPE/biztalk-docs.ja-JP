---
title: "WCF チャネル モデルを使用して SAP のフラット ファイル Idoc をストリーム配信 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF channel model, streaming flat-file IDOCs
ms.assetid: 5010e215-d8d0-47c8-93a6-20cfdeff2951
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8de850022a03a3be0310da3022a2cf496c94f30
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="stream-flat-file-idocs-in-sap-using-the-wcf-channel-model"></a><span data-ttu-id="5112e-102">WCF チャネル モデルを使用して SAP のフラット ファイル Idoc をストリーム</span><span class="sxs-lookup"><span data-stu-id="5112e-102">Stream Flat-File IDOCs in SAP using the WCF Channel Model</span></span>
<span data-ttu-id="5112e-103">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]ノード値、SendIdoc および ReceiveIdoc 操作のストリーミングをサポートします。</span><span class="sxs-lookup"><span data-stu-id="5112e-103">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] supports node-value streaming for the SendIdoc and ReceiveIdoc operations.</span></span> <span data-ttu-id="5112e-104">これらの操作は、フラット ファイル (string) Idoc をして、アダプターからの送受信に使用されます。</span><span class="sxs-lookup"><span data-stu-id="5112e-104">These operations are used to send and receive flat-file (string) IDOCs to and from the adapter.</span></span> <span data-ttu-id="5112e-105">1 つのノードの下の文字列にこれらの操作の両方で全体の IDOC のデータが含まれている (\<idocData\>)。</span><span class="sxs-lookup"><span data-stu-id="5112e-105">In both of these operations, the data for the entire IDOC is contained in a string under a single node (\<idocData\>).</span></span> <span data-ttu-id="5112e-106">大規模の Idoc は、アダプターとコード間で IDOC データのストリーミングは、大量のメモリ リソースに保存できます。</span><span class="sxs-lookup"><span data-stu-id="5112e-106">For large IDOCs, streaming the IDOC data between the adapter and your code may save significant memory resources.</span></span>  
  
 <span data-ttu-id="5112e-107">アダプターがストリーミングをサポートする方法の詳細については、次を参照してください。[ストリーミングと SAP アダプター](../../adapters-and-accelerators/adapter-sap/streaming-and-the-sap-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="5112e-107">For background information about how the adapter supports streaming, see [Streaming and the SAP Adapter](../../adapters-and-accelerators/adapter-sap/streaming-and-the-sap-adapter.md).</span></span> <span data-ttu-id="5112e-108">続行する前にこのトピックの内容を確認してください。</span><span class="sxs-lookup"><span data-stu-id="5112e-108">You should read this topic before proceeding.</span></span>  
  
 <span data-ttu-id="5112e-109">このトピックのセクションでは、ノードと値の WCF チャネル モデルを使用すると、SendIdoc および ReceiveIdoc 操作のストリーミングを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5112e-109">The sections in this topic describe how to implement node-value streaming for the SendIdoc and ReceiveIdoc operations when you use the WCF channel model.</span></span>  
  
## <a name="streaming-outbound-flat-file-idocs-to-the-adapter"></a><span data-ttu-id="5112e-110">送信フラット ファイル Idoc をアダプターにストリーミング</span><span class="sxs-lookup"><span data-stu-id="5112e-110">Streaming Outbound Flat-File IDOCs to the Adapter</span></span>  
 <span data-ttu-id="5112e-111">アダプターは、ノード値 SendIdoc 操作の要求メッセージのストリーミングをサポートします。</span><span class="sxs-lookup"><span data-stu-id="5112e-111">The adapter supports node-value streaming on the request message for the SendIdoc operation.</span></span>  
  
 <span data-ttu-id="5112e-112">ノード値が、WCF チャネル モデルで SendIdoc 操作でストリーミングをサポートするために次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="5112e-112">To support node-value streaming on SendIdoc operations in the WCF channel model, you must:</span></span>  
  
1.  <span data-ttu-id="5112e-113">実装する**System.ServiceModel.Channels.BodyWriter**が (ノード値 IDOC データのストリーミングを実行する) IDOC データをストリーミング可能です。</span><span class="sxs-lookup"><span data-stu-id="5112e-113">Implement a **System.ServiceModel.Channels.BodyWriter** that is capable of streaming the IDOC data (performing node-value streaming on the IDOC data).</span></span>  
  
2.  <span data-ttu-id="5112e-114">作成、 **System.ServiceModel.Message**これを使用してメッセージ本文を指定することによって、操作を呼び出すために使用**BodyWriter**の適切なオーバー ロードを使用して、 **Message.Create**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="5112e-114">Create the **System.ServiceModel.Message** used to invoke the operation by supplying the message body with this **BodyWriter** using an appropriate overload of the **Message.Create** method.</span></span>  
  
### <a name="implementing-a-bodywriter"></a><span data-ttu-id="5112e-115">BodyWriter を実装します。</span><span class="sxs-lookup"><span data-stu-id="5112e-115">Implementing a BodyWriter</span></span>  
 <span data-ttu-id="5112e-116">次の例の実装を示しています、 **BodyWriter**ノード値のストリーミングを実行します。</span><span class="sxs-lookup"><span data-stu-id="5112e-116">The following example shows an implementation of a **BodyWriter** that performs node-value streaming.</span></span>  
  
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
  
### <a name="creating-a-message-by-using-a-bodywriter"></a><span data-ttu-id="5112e-117">BodyWriter によるメッセージの作成</span><span class="sxs-lookup"><span data-stu-id="5112e-117">Creating a Message by using a BodyWriter</span></span>  
 <span data-ttu-id="5112e-118">次の例を使用して SendIdoc 要求メッセージを作成する方法を示しています、 **BodyWriter**前の例です。</span><span class="sxs-lookup"><span data-stu-id="5112e-118">The following example shows how to create a SendIdoc request message using the **BodyWriter** in the preceding example.</span></span> <span data-ttu-id="5112e-119">メッセージのデータは、ファイルから読み取られます。</span><span class="sxs-lookup"><span data-stu-id="5112e-119">The message data is read from a file.</span></span>  
  
```  
XmlReader readerIn = XmlReader.Create ("sendidoc.xml");  
// StreamingBodyWrtier class is responsible for streaming  
StreamingBodyWriter stBW = new StreamingBodyWriter(readerIn, chunkSize);  
  
Message InputMsg = Message.CreateMessage(MessageVersion.Default,  
    "http://Microsoft.LobServices.SAP/2007/03/Idoc/SendIdoc",   
    stBW);  
  
```  
  
## <a name="streaming-inbound-flat-file-idocs-from-the-adapter"></a><span data-ttu-id="5112e-120">アダプターからの着信フラット ファイル Idoc のストリーミング</span><span class="sxs-lookup"><span data-stu-id="5112e-120">Streaming Inbound Flat-File IDOCs from the Adapter</span></span>  
 <span data-ttu-id="5112e-121">受信 ReceiveIdoc 操作では、フラット ファイル Idoc を受信します。</span><span class="sxs-lookup"><span data-stu-id="5112e-121">You receive a flat-file IDOCs in the inbound ReceiveIdoc operation.</span></span> <span data-ttu-id="5112e-122">アダプターは、ノード値 ReceiveIdoc 操作の要求メッセージのストリーミングをサポートします。</span><span class="sxs-lookup"><span data-stu-id="5112e-122">The adapter supports node-value streaming on the request message for the ReceiveIdoc operation.</span></span>  
  
 <span data-ttu-id="5112e-123">ノード値が、WCF チャネル モデルで ReceiveIdoc 操作でストリーミングをサポートするために次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="5112e-123">To support node-value streaming on ReceiveIdoc operations in the WCF channel model, you must:</span></span>  
  
1.  <span data-ttu-id="5112e-124">実装する**System.Xml.XmlDictionaryWriter**が (ノード値 IDOC データのストリーミングを実行する) IDOC データをストリーミング可能です。</span><span class="sxs-lookup"><span data-stu-id="5112e-124">Implement a **System.Xml.XmlDictionaryWriter** that is capable of streaming the IDOC data (performing node-value streaming on the IDOC data).</span></span>  
  
2.  <span data-ttu-id="5112e-125">消費、**メッセージ**を呼び出すことによってその**WriteBodyContents**メソッドをこの**XmlDictionaryWriter**です。</span><span class="sxs-lookup"><span data-stu-id="5112e-125">Consume the **Message** by invoking its **WriteBodyContents** method with this **XmlDictionaryWriter**.</span></span>  
  
### <a name="implementing-an-xmldictionarywriter"></a><span data-ttu-id="5112e-126">XmlDictionaryWriter の実装</span><span class="sxs-lookup"><span data-stu-id="5112e-126">Implementing an XmlDictionaryWriter</span></span>  
 <span data-ttu-id="5112e-127">次の例の実装を示しています、 **XmlDictionaryWriter**ノード値のストリーミングを実行します。</span><span class="sxs-lookup"><span data-stu-id="5112e-127">The following example shows an implementation of an **XmlDictionaryWriter** that performs node-value streaming.</span></span>  
  
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
  
### <a name="consuming-a-message-by-using-an-xmldictionarywriter"></a><span data-ttu-id="5112e-128">メッセージを使用する XmlDictionaryWriter を使用して、</span><span class="sxs-lookup"><span data-stu-id="5112e-128">Consuming a Message by Using an XmlDictionaryWriter</span></span>  
 <span data-ttu-id="5112e-129">次の例を使用して ReceiveIdoc 要求メッセージを使用する方法を示しています、 **FileXmlWriter**前の例で実装します。</span><span class="sxs-lookup"><span data-stu-id="5112e-129">The following example shows how to consume a ReceiveIdoc request message using the **FileXmlWriter** implemented in the preceding example.</span></span> <span data-ttu-id="5112e-130">(、 **FileWriter**サブクラスによってクラスが作成された**XmlDictionaryWriter**)。この例では、 **IReplyChannel**受信 ReceiveIdoc 操作へのチャネル。</span><span class="sxs-lookup"><span data-stu-id="5112e-130">(The **FileWriter** class was created by sub-classing **XmlDictionaryWriter**.) The example uses an **IReplyChannel** channel to receive the ReceiveIdoc operation.</span></span> <span data-ttu-id="5112e-131">チャネルの作成の詳細が省略されています。</span><span class="sxs-lookup"><span data-stu-id="5112e-131">The details of the channel creation have been omitted.</span></span> <span data-ttu-id="5112e-132">ReceiveIdoc 要求メッセージは、ファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="5112e-132">The ReceiveIdoc request message is written to a file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5112e-133">参照</span><span class="sxs-lookup"><span data-stu-id="5112e-133">See Also</span></span>  
[<span data-ttu-id="5112e-134">WCF チャネル モデルを使用してアプリケーションを開発する</span><span class="sxs-lookup"><span data-stu-id="5112e-134">Develop applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)