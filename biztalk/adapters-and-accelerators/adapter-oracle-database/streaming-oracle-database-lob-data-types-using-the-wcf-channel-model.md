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
# <a name="streaming-oracle-database-lob-data-types-using-the-wcf-channel-model"></a><span data-ttu-id="2f968-102">ストリーミングの Oracle データベース LOB データ型 WCF チャネル モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="2f968-102">Streaming Oracle Database LOB Data Types Using the WCF Channel Model</span></span>
<span data-ttu-id="2f968-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] LOB データの特定の操作のエンド ツー エンドのストリーミングをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="2f968-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] supports end-to-end streaming of LOB data for certain operations.</span></span> <span data-ttu-id="2f968-104">このトピックのセクションでは、WCF チャネル モデルを使用すると、LOB データのストリーミングを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2f968-104">The sections in this topic describe how to implement streaming for LOB data when you use the WCF channel model.</span></span>  
  
 <span data-ttu-id="2f968-105">背景情報アダプターが LOB データ型のストリーミングがサポートする方法については、[Oracle データベース アダプターのラージ オブジェクト データ型のストリーミング](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f968-105">For background information about how the adapter supports streaming of LOB data types, see [Streaming large object data types in Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md).</span></span> <span data-ttu-id="2f968-106">続行する前に、このトピックを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2f968-106">You should read this topic before proceeding.</span></span>  
  
 <span data-ttu-id="2f968-107">LOB データのストリーミングを示すサンプルに含まれる SDK サンプルでは、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="2f968-107">A sample that demonstrates LOB data streaming is available in the SDK samples included with the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="2f968-108">詳細については、[SDK 内のサンプル](../../core/samples-in-the-sdk.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f968-108">For more information, see [Samples in the SDK](../../core/samples-in-the-sdk.md).</span></span>  
  
## <a name="streaming-outbound-messages-to-the-adapter"></a><span data-ttu-id="2f968-109">アダプターに送信メッセージのストリーミング</span><span class="sxs-lookup"><span data-stu-id="2f968-109">Streaming Outbound Messages to the Adapter</span></span>  
 <span data-ttu-id="2f968-110">アダプターでは、エンド ツー エンドの LOB データのストリーミング UpdateLOB 操作の要求メッセージをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="2f968-110">The adapter supports end-to-end LOB data streaming for the request message for the UpdateLOB operation.</span></span>  
  
 <span data-ttu-id="2f968-111">WCF チャネル モデルで UpdateLOB 操作に関するエンド ツー エンドのストリーミングをサポートするには、次の操作をする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f968-111">To support end-to-end streaming on UpdateLOB operations in the WCF channel model, you must:</span></span>  
  
1.  <span data-ttu-id="2f968-112">設定、 **UseAmbientTransaction**プロパティを true にバインドします。</span><span class="sxs-lookup"><span data-stu-id="2f968-112">Set the **UseAmbientTransaction** binding property to true.</span></span>  
  
2.  <span data-ttu-id="2f968-113">実装を**System.ServiceModel.Channels.BodyWriter**ことができる (ノード値の LOB データのストリーミングを実行する) LOB データをストリーミングします。</span><span class="sxs-lookup"><span data-stu-id="2f968-113">Implement a **System.ServiceModel.Channels.BodyWriter** that is capable of streaming the LOB data (performing node-value streaming on the LOB data).</span></span>  
  
3.  <span data-ttu-id="2f968-114">トランザクション スコープ内で UpdateLOB 操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="2f968-114">Perform the UpdateLOB operation within a transaction scope.</span></span>  
  
4.  <span data-ttu-id="2f968-115">作成、 **System.ServiceModel.Message**このメッセージ本文を指定して、操作を呼び出すために使用**BodyWriter**の適切なオーバー ロードを使用して、 **Message.Create**メソッド。</span><span class="sxs-lookup"><span data-stu-id="2f968-115">Create the **System.ServiceModel.Message** used to invoke the operation by supplying the message body with this **BodyWriter** using an appropriate overload of the **Message.Create** method.</span></span>  
  
### <a name="setting-the-useambienttransaction-binding-property"></a><span data-ttu-id="2f968-116">プロパティのバインド UseAmbientTransaction の設定</span><span class="sxs-lookup"><span data-stu-id="2f968-116">Setting the UseAmbientTransaction Binding Property</span></span>  
 <span data-ttu-id="2f968-117">次の例のバインドを作成する方法を示しています、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]設定と、 **UseAmbientTransaction**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="2f968-117">The following example shows how to create a binding for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] and set the **UseAmbientTransaction** binding property.</span></span>  
  
```  
// Create binding  
OracleDBBinding odbBinding = new OracleDBBinding();  
  
//set the binding property  
binding.UseAmbientTransaction = true;  
  
```  
  
### <a name="implementing-a-bodywriter"></a><span data-ttu-id="2f968-118">BodyWriter を実装します。</span><span class="sxs-lookup"><span data-stu-id="2f968-118">Implementing a BodyWriter</span></span>  
 <span data-ttu-id="2f968-119">次の例の実装を示しています、 **BodyWriter**ノード値のストリーミングを実行します。</span><span class="sxs-lookup"><span data-stu-id="2f968-119">The following example shows an implementation of a **BodyWriter** that performs node-value streaming.</span></span>  
  
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
  
### <a name="perform-the-operations-within-a-transaction-scope"></a><span data-ttu-id="2f968-120">トランザクション スコープ内で操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="2f968-120">Perform the Operations Within a Transaction Scope</span></span>  
 <span data-ttu-id="2f968-121">次の例では、トランザクション スコープ内での操作を実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2f968-121">The following example shows how to perform operations within a transaction scope.</span></span>  
  
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
  
### <a name="creating-a-message-by-using-a-bodywriter"></a><span data-ttu-id="2f968-122">BodyWriter によるメッセージの作成</span><span class="sxs-lookup"><span data-stu-id="2f968-122">Creating a Message by using a BodyWriter</span></span>  
 <span data-ttu-id="2f968-123">次の例では、使用して UpdateLOB 要求メッセージを作成する方法を示しています、 **BodyWriter**前の例です。</span><span class="sxs-lookup"><span data-stu-id="2f968-123">The following example shows how to create an UpdateLOB request message using the **BodyWriter** in the preceding example.</span></span> <span data-ttu-id="2f968-124">メッセージのデータは、ファイルから読み取られます。</span><span class="sxs-lookup"><span data-stu-id="2f968-124">The message data is read from a file.</span></span>  
  
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
  
## <a name="streaming-inbound-messages-from-the-adapter"></a><span data-ttu-id="2f968-125">アダプターから受信メッセージのストリーミング</span><span class="sxs-lookup"><span data-stu-id="2f968-125">Streaming Inbound Messages from the Adapter</span></span>  
 <span data-ttu-id="2f968-126">アダプターには、エンド ツー エンドの LOB データが次の受信メッセージのストリーミングがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2f968-126">The adapter supports end-to-end LOB data streaming for the following inbound messages:</span></span>  
  
- <span data-ttu-id="2f968-127">応答メッセージを持つ関数または LOB データが含まれている IN OUT パラメーター。</span><span class="sxs-lookup"><span data-stu-id="2f968-127">Response message for functions with OUT or IN OUT parameters that contain LOB data.</span></span> <span data-ttu-id="2f968-128">レコードの種類のパラメーターが LOB データの列を含めることができますに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2f968-128">Note that RECORD TYPE parameters can contain LOB data columns.</span></span>  
  
- <span data-ttu-id="2f968-129">LOB データが含まれている関数を REF CURSOR パラメーター (または戻り値) の応答メッセージ。</span><span class="sxs-lookup"><span data-stu-id="2f968-129">Response message for functions with OUT REF CURSOR parameters (or return values) that contain LOB data.</span></span> <span data-ttu-id="2f968-130">これには、出力側 REF CURSOR を IN パラメーターにはが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2f968-130">This includes the output side of IN OUT REF CURSOR parameters.</span></span>  
  
- <span data-ttu-id="2f968-131">プロシージャの応答メッセージまたは LOB データが含まれている IN OUT パラメーター。</span><span class="sxs-lookup"><span data-stu-id="2f968-131">Response message for procedures with IN or IN OUT parameters that contain LOB data.</span></span> <span data-ttu-id="2f968-132">レコードの種類のパラメーターが LOB データの列を含めることができますに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2f968-132">Note that RECORD TYPE parameters can contain LOB data columns.</span></span>  
  
- <span data-ttu-id="2f968-133">LOB データを含む OUT REF CURSOR パラメーターを含むプロシージャの応答メッセージ。</span><span class="sxs-lookup"><span data-stu-id="2f968-133">Response message for procedures with OUT REF CURSOR parameters that contain LOB data.</span></span> <span data-ttu-id="2f968-134">これにより、出力側 REF CURSOR を IN パラメーターにはが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2f968-134">This includes the output side of IN OUT REF CURSOR parameters</span></span>  
  
- <span data-ttu-id="2f968-135">LOB データを含む結果セットを返す SQLEXECUTE 操作の応答メッセージ。</span><span class="sxs-lookup"><span data-stu-id="2f968-135">Response message for SQLEXECUTE operations that return result sets that contain LOB data.</span></span>  
  
- <span data-ttu-id="2f968-136">LOB データを返す結果のテーブルまたはビューの Select 操作の応答メッセージを設定します。</span><span class="sxs-lookup"><span data-stu-id="2f968-136">Response message for Table or view Select operations that return LOB data in the result set.</span></span>  
  
- <span data-ttu-id="2f968-137">(受信) POLLINGSTMT 操作の要求メッセージ</span><span class="sxs-lookup"><span data-stu-id="2f968-137">Request message for the (inbound) POLLINGSTMT operation</span></span>  
  
  <span data-ttu-id="2f968-138">WCF チャネル モデル内の受信メッセージのエンド ツー エンドのストリーミングをサポートするには、次の操作をする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f968-138">To support end-to-end streaming on an inbound message in the WCF channel model, you must:</span></span>  
  
1.  <span data-ttu-id="2f968-139">実装を**System.Xml.XmlDictionaryWriter**ことができる (ノード値の LOB データのストリーミングを実行する) LOB データをストリーミングします。</span><span class="sxs-lookup"><span data-stu-id="2f968-139">Implement a **System.Xml.XmlDictionaryWriter** that is capable of streaming the LOB data (performing node-value streaming on the LOB data).</span></span>  
  
2.  <span data-ttu-id="2f968-140">使用、**メッセージ**を呼び出して**WriteBodyContents**メソッドをこの**XmlDictionaryWriter**します。</span><span class="sxs-lookup"><span data-stu-id="2f968-140">Consume the **Message** by invoking **WriteBodyContents** method with this **XmlDictionaryWriter**.</span></span>  
  
### <a name="implementing-an-xmldictionarywriter"></a><span data-ttu-id="2f968-141">XmlDictionaryWriter の実装</span><span class="sxs-lookup"><span data-stu-id="2f968-141">Implementing an XmlDictionaryWriter</span></span>  
 <span data-ttu-id="2f968-142">次の例の実装を示しています、 **XmlDictionaryWriter**ノード値のストリーミングを実行します。</span><span class="sxs-lookup"><span data-stu-id="2f968-142">The following example shows an implementation of an **XmlDictionaryWriter** that performs node-value streaming.</span></span>  
  
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
  
### <a name="consuming-a-message-by-using-an-xmldictionarywriter"></a><span data-ttu-id="2f968-143">メッセージを使用する XmlDictionaryWriter を使用して、</span><span class="sxs-lookup"><span data-stu-id="2f968-143">Consuming a Message by using an XmlDictionaryWriter</span></span>  
 <span data-ttu-id="2f968-144">次の例は、応答メッセージを使用してテーブルを使用する方法を示しています、 **FileXmlWriter**前の例で実装します。</span><span class="sxs-lookup"><span data-stu-id="2f968-144">The following example shows how to consume a table Select response message using the **FileXmlWriter** implemented in the preceding example.</span></span> <span data-ttu-id="2f968-145">(、 **FileWriter**クラスがサブクラス化によって作成された**XmlDictionaryWriter**)。この例では、 **IRequestChannel**選択操作を呼び出すためのチャネル。</span><span class="sxs-lookup"><span data-stu-id="2f968-145">(The **FileWriter** class was created by sub-classing **XmlDictionaryWriter**.) The example uses an **IRequestChannel** channel to invoke the Select operation.</span></span> <span data-ttu-id="2f968-146">チャネルの作成の詳細が省略されています。</span><span class="sxs-lookup"><span data-stu-id="2f968-146">The details of the channel creation have been omitted.</span></span> <span data-ttu-id="2f968-147">要求メッセージは、ファイルから読み取られ、選択の応答メッセージは、ファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="2f968-147">The Select request message is read from a file and the Select response message is written to a file.</span></span>  
  
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
  
 <span data-ttu-id="2f968-148">次の XML では、選択操作の要求メッセージ (select.xml ファイルの内容) を表示します。</span><span class="sxs-lookup"><span data-stu-id="2f968-148">The following XML shows the request message (contents of the select.xml file) for the Select operation.</span></span> <span data-ttu-id="2f968-149">CUSTOMER テーブルには、写真をという名前の BLOB 列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2f968-149">The CUSTOMER table contains a BLOB column named PHOTO.</span></span>  
  
```  
<Select xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER">  
  <COLUMN_NAMES>*</COLUMN_NAMES>  
  <FILTER>NAME='Kim Ralls'</FILTER>  
</Select>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2f968-150">参照</span><span class="sxs-lookup"><span data-stu-id="2f968-150">See Also</span></span>  
 [<span data-ttu-id="2f968-151">WCF チャネル モデルを使用して Oracle データベース アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="2f968-151">Develop Oracle Database applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)