---
title: ストリーミングによるメモリ使用量の最適化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f8ba8820-65b4-4161-9f7a-3ae3d39e3d11
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ed7f6a3c9f20f112d5a976642d2cdd23a6890e7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291404"
---
# <a name="optimizing-memory-usage-with-streaming"></a><span data-ttu-id="183ef-102">ストリーミングによるメモリ使用量を最適化します。</span><span class="sxs-lookup"><span data-stu-id="183ef-102">Optimizing Memory Usage with Streaming</span></span>
<span data-ttu-id="183ef-103">このトピックでは、ストリーミングのパターンを使用したオーケストレーションでメッセージを読み込むときに、WCF トランスポートを使用して、またはサイズの大きいメッセージを送受信する際にメッセージ メモリのフット プリントを最小限に抑えるための推奨事項を提供します。</span><span class="sxs-lookup"><span data-stu-id="183ef-103">This topic provides recommendations for using streaming patterns to minimize message memory footprints when sending or receiving large messages with a WCF transport or when loading messages in orchestrations.</span></span>   
<span data-ttu-id="183ef-104">メッセージの内容を読み取るをオーケストレーションでコードを使用する場合は、XmlDocument 変数を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="183ef-104">When using code in an orchestration to read the contents of a message, avoid using XmlDocument variables.</span></span> <span data-ttu-id="183ef-105">XmlDocument 変数にメッセージを読み込み、特にサイズの大きいメッセージ用の大きなオーバーヘッドが発生します。</span><span class="sxs-lookup"><span data-stu-id="183ef-105">Loading a message into an XmlDocument variable incurs significant overhead, especially for large messages.</span></span> <span data-ttu-id="183ef-106">このオーバーヘッドは、メモリ使用量とメモリ内構造を構築する処理の観点からです。</span><span class="sxs-lookup"><span data-stu-id="183ef-106">This overhead is in terms of memory usage and processing to build the in-memory structures.</span></span> <span data-ttu-id="183ef-107">XmlDocument インスタンスの使用は、ドキュメント オブジェクト モジュール (DOM) のオブジェクト グラフを構築するためにメモリに読み込まれる全体のメッセージの内容を強制します。</span><span class="sxs-lookup"><span data-stu-id="183ef-107">The use of an XmlDocument instance forces the entire message contents to be loaded into memory in order to build the object graph for the Document Object Module (DOM).</span></span> <span data-ttu-id="183ef-108">このクラスのインスタンスによって使用されるメモリの総量では、実際のメッセージ サイズの約 10 倍の時間を指定できます。</span><span class="sxs-lookup"><span data-stu-id="183ef-108">The total amount of memory used by an instance of this class can be around 10 times the actual message size.</span></span> <span data-ttu-id="183ef-109">メッセージを XmlDocument 変数に読み込むときに必要なメモリ使用量の詳細については、次を参照してください。[第 9 章 – XML パフォーマンスの向上](http://go.microsoft.com/fwlink/?LinkId=139772)(http://go.microsoft.com/fwlink/?LinkId=139772) msdn です。</span><span class="sxs-lookup"><span data-stu-id="183ef-109">For more information about the memory footprint required when loading a message into an XmlDocument variable, see [Chapter 9 – Improving XML Performance](http://go.microsoft.com/fwlink/?LinkId=139772) (http://go.microsoft.com/fwlink/?LinkId=139772) on MSDN.</span></span>   
<span data-ttu-id="183ef-110">このトピックの残りの部分は、XmlDocument 変数へのメッセージの読み込みを必要としないメッセージの内容を読み取るための代替方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="183ef-110">The remainder of this topic provides alternative methods for reading message contents that do not require loading a message into an XmlDocument variable.</span></span>  
  
## <a name="use-streaming-when-sending-or-receiving-large-messages-with-a-wcf-transport"></a><span data-ttu-id="183ef-111">WCF トランスポートを使用してサイズの大きいメッセージを送受信する際にストリーミングを使用して、</span><span class="sxs-lookup"><span data-stu-id="183ef-111">Use streaming when sending or receiving large messages with a WCF transport</span></span>  
 <span data-ttu-id="183ef-112">WCF トランスポートを使用してサイズの大きいメッセージを送受信するときに、Wcf-custom または Wcf-customisolated アダプターを使用してし、をサポートするバインドの種類を構成、 **transferMode = Streamed**次のバインドなどのオプション。</span><span class="sxs-lookup"><span data-stu-id="183ef-112">When sending or receiving large messages with a WCF transport, use the WCF-Custom or WCF-CustomIsolated adapter and configure with a binding type that supports the **transferMode = Streamed** option, such as the following bindings:</span></span>  
  
- <span data-ttu-id="183ef-113">**basicHttpBinding + BasicHttpBindingElement、transferMode Streamed を =**</span><span class="sxs-lookup"><span data-stu-id="183ef-113">**basicHttpBinding + BasicHttpBindingElement, transferMode = Streamed**</span></span>  
  
- <span data-ttu-id="183ef-114">**netTcpBinding + NetTcpBindingElement、transferMode Streamed を =**</span><span class="sxs-lookup"><span data-stu-id="183ef-114">**netTcpBinding + NetTcpBindingElement, transferMode = Streamed**</span></span>  
  
- <span data-ttu-id="183ef-115">**customBinding + HttpTransportElement、transferMode Streamed を =**</span><span class="sxs-lookup"><span data-stu-id="183ef-115">**customBinding + HttpTransportElement, transferMode = Streamed**</span></span>  
  
- <span data-ttu-id="183ef-116">**customBinding + ConnectionOrientedTransportElement、transferMode Streamed を =**</span><span class="sxs-lookup"><span data-stu-id="183ef-116">**customBinding +ConnectionOrientedTransportElement, transferMode = Streamed**</span></span>  
  
  <span data-ttu-id="183ef-117">サポートするバインドと共に Wcf-custom または Wcf-customisolated アダプターを選択する、 **transferMode = Streamed**オプションは、必要に応じて、ファイル システムにサイズの大きいメッセージのストリーミングを実装して、可能性を軽減メモリ不足の問題。</span><span class="sxs-lookup"><span data-stu-id="183ef-117">Choosing a WCF-Custom or WCF-CustomIsolated adapter along with a binding that supports the **transferMode = Streamed** option will implement streaming of large messages to the file system as needed, and will mitigate potential out-of-memory issues.</span></span>  
  
## <a name="use-streaming-to-minimize-the-memory-footprint-required-when-loading-messages-in-orchestrations"></a><span data-ttu-id="183ef-118">ストリーミングを使用して、オーケストレーション内のメッセージを読み込むときに必要なメモリのフット プリントを最小限に抑える</span><span class="sxs-lookup"><span data-stu-id="183ef-118">Use streaming to minimize the memory footprint required when loading messages in orchestrations</span></span>  
 <span data-ttu-id="183ef-119">次の手法では、オーケストレーションにメッセージを読み込む場合は、メッセージのメモリ使用量を最小限に抑える方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="183ef-119">The following techniques describe how to minimize the memory footprint of a message when loading the message into an orchestration.</span></span>  
  
### <a name="use-an-xlangmessage-variable-to-process-the-contents-of-a-message-or-message-part"></a><span data-ttu-id="183ef-120">メッセージまたはメッセージ部分のコンテンツを処理するのに XLANGMessage 変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="183ef-120">Use an XLANGMessage variable to process the contents of a message or message part</span></span>  
 <span data-ttu-id="183ef-121">.NET クラス ライブラリをオーケストレーションからメッセージを渡す、ときに渡さないこと; このトピックの前半で説明した上の理由から、XmlDocument 変数として代わりに、XLANGMessage 変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="183ef-121">When passing a message from an orchestration to .NET class libraries, do not pass them as XmlDocument variables, for reasons mentioned earlier in this topic; use XLANGMessage variables instead.</span></span> <span data-ttu-id="183ef-122">次の手法では、メッセージまたは XLANGMessage 変数を使用したメッセージ部分を読み取るためのメソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="183ef-122">The following techniques illustrate methods for reading a message or message part using an XLANGMessage variable.</span></span>  
  
-   <span data-ttu-id="183ef-123">**XMLReader によるメッセージの処理**でに XmlReader インスタンスにメッセージを処理してメッセージを XLANGMessage として .NET コードに渡す、XmlReader を使用してパーツのコンテンツを取得します。</span><span class="sxs-lookup"><span data-stu-id="183ef-123">**Process messages with XMLReader** - To process a message with an XmlReader instance, pass the message to .NET code as an XLANGMessage, and retrieve the Part content using XmlReader.</span></span>  
  
    ```  
    public void ProcessMessage(XLANGMessage message)  
    {  
        try  
        {  
            using (XmlReader reader = message[0].RetrieveAs(typeof(XmlReader)) as XmlReader)  
            if (reader != null)  
            {  
                ...  
            }  
        }  
        finally  
        {  
            message.Dispose();  
        }  
    }  
    ```  
  
-   <span data-ttu-id="183ef-124">**StreamReader 文字列に、メッセージの内容を取得**-XmlDocument.OuterXml() を使用して XML 文字列としてメッセージを取得する XmlDocument のオーケストレーションでの一般的な用途の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="183ef-124">**Retrieve the contents of a message into a string with StreamReader** - One of the common uses of XmlDocument in orchestrations is to retrieve the message as an XML string using XmlDocument.OuterXml().</span></span> <span data-ttu-id="183ef-125">次のコード例は、XLANGMessage 変数を使用する文字列としてメッセージを取得する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="183ef-125">The following code example illustrates an alternative method which retrieves the message as a string using an XLANGMessage variable.</span></span>  
  
    ```  
    public static string MessageToString(XLANGMessage message)  
    {  
        string strResults;  
        try  
        {  
            using (Stream stream = message[0].RetrieveAs(typeof(Stream)) as Stream)  
            {  
                using (StreamReader reader = new StreamReader(stream))  
                {  
                    strResults = reader.ReadToEnd();  
                }  
            }  
        }  
        finally  
        {  
            message.Dispose();  
        }  
        return strResults;  
    }  
    ```  
  
-   <span data-ttu-id="183ef-126">**単純な .NET メッセージの内容を文字列に取得**-メッセージの種類が単純な .NET 型の場合は、その型とメッセージを取得できます。</span><span class="sxs-lookup"><span data-stu-id="183ef-126">**Retrieve the contents of simple .NET messages into a string** - If the type of the message is a simple .NET type, you can retrieve the message as that type.</span></span> <span data-ttu-id="183ef-127">たとえばを文字列としてメッセージを取得するには、XLANGMessage として .NET コードにメッセージを渡すし、パーツのコンテンツを文字列として取得します。</span><span class="sxs-lookup"><span data-stu-id="183ef-127">For example, to get the message as a string, pass the message to the .NET code as an XLANGMessage and retrieve the Part content as a string.</span></span>  
  
    ```  
    public void ProcessMessage(XLANGMessage message)  
    {  
        try  
        {  
            string content = message[0].RetrieveAs(typeof(string)) as string;  
            if (!string.IsNullOrEmpty(content))  
            {  
                ...  
            }  
        }  
        finally  
        {  
            message.Dispose();  
        }  
    }  
    ```  
  
-   <span data-ttu-id="183ef-128">**ストリームにメッセージの内容を取得**でにストリームとしてメッセージを取得、XLANGMessage として .NET コードにメッセージを渡すして一部のコンテンツをストリームとして取得します。</span><span class="sxs-lookup"><span data-stu-id="183ef-128">**Retrieve the contents of a message into a stream** - To get the message as a stream, pass the message to the .NET code as an XLANGMessage and retrieve the Part content as a stream.</span></span>  
  
    ```  
    public Stream ProcessRequestReturnStream(XLANGMessage message, int bufferSize, int thresholdSize)  
    {  
       ...  
       try  
       {  
          using (VirtualStream virtualStream = new VirtualStream(bufferSize, thresholdSize))  
          {  
             using (Stream partStream = (Stream)message[0].RetrieveAs(typeof(Stream)))  
             //Note that when calling this code, if the XmlDocument is quite large, keeping it in a memory with a MemoryStream may have an adverse effect on performance.   
             //In this case, it may be worthwhile to consider an approach that uses a VirtualStream + ReadonlySeekableStream to buffer it to the file system, if its size is bigger than the thresholdSize parameter.  
             //Keep in mind that:  
             // - If the message size is smaller than the threshold size, the VirtualStream class buffers the stream to a MemoryStream.  
             // - If the message size is bigger than the threshold size, the VirtualStream class buffers the stream to a temporary file.  
                using (ReadOnlySeekableStream readOnlySeekableStream = new ReadOnlySeekableStream(partStream, virtualStream, bufferSize))  
                {  
                   using (XmlReader reader = XmlReader.Create(readOnlySeekableStream))  
                   {  
  
                   }  
                }  
             }  
          }  
       }  
       catch (Exception ex)  
       {  
  
       }  
       finally  
       {  
          message.Dispose();  
       }  
       return stream;  
    }  
    ```  
  
-   <span data-ttu-id="183ef-129">**.NET オブジェクトにメッセージの内容を取得**- を .NET オブジェクトとしてメッセージを取得、XLANGMessage として .NET コードに、メッセージを渡すこと、および .NET クラスのインスタンスとしてパーツのコンテンツを取得します。</span><span class="sxs-lookup"><span data-stu-id="183ef-129">**Retrieve the contents of a message into a .NET object** - To get the message as a .NET object, pass the message to the .NET code as an XLANGMessage and retrieve the Part content as an instance of a .NET class.</span></span> <span data-ttu-id="183ef-130">この作成後者から Visual Studio 2010 で提供される XML スキーマ定義ツール (Xsd.exe) ツールを使用して、メッセージの Xml スキーマ。</span><span class="sxs-lookup"><span data-stu-id="183ef-130">Create this latter from the Xml Schema of the message using the XML Schema Definition Tool (Xsd.exe) tool provided by Visual Studio 2010.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="183ef-131">この手法は、メッセージが小さい場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="183ef-131">This technique is valid only when messages are small.</span></span> <span data-ttu-id="183ef-132">それ以外の場合、このアプローチは、.NET オブジェクトに実際のメッセージを逆シリアル化のオーバーヘッドを大幅にかかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="183ef-132">Otherwise, this approach could incur in a significant overhead to de-serialize the actual message into a .NET object.</span></span>  
  
    ```  
    public void ProcessMessage(XLANGMessage message)  
    {  
        try  
          {  
          Request request = message[0].RetrieveAs(typeof(Request)) as Request;  
          if (request != null)  
          {  
             ...  
          }  
       }  
       finally  
       {  
          message.Dispose();  
       }  
  
    }  
    ```  
  
> [!NOTE]  
>  <span data-ttu-id="183ef-133">使用、 **Dispose()** .NET コードから戻る前に、XLANGMessage パラメーターによって公開されるメソッドのシナリオとインスタンスの経過と共に蓄積される実行時間の長いオーケストレーションをループで特に重要ですが、時間の経過と共に解放せず XLANGMessage オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="183ef-133">Use of the **Dispose()** method exposed by the XLANGMessage parameter before returning from the .NET code is particularly important in looping scenarios and long-running orchestrations that can accumulate instances of the XLANGMessage object without releasing them over time.</span></span> <span data-ttu-id="183ef-134">呼び出し元のメッセージの詳細についてはします。この方法で Dispose() を参照してください[XLANGMessage として表されるメッセージ](http://go.microsoft.com/fwlink/?LinkId=139775)(http://go.microsoft.com/fwlink/?LinkId=139775) BizTalk Server のドキュメントにします。</span><span class="sxs-lookup"><span data-stu-id="183ef-134">For more information about calling message.Dispose() in this manner, see [Messages Represented as XLANGMessage](http://go.microsoft.com/fwlink/?LinkId=139775) (http://go.microsoft.com/fwlink/?LinkId=139775) in the BizTalk Server documentation.</span></span> <span data-ttu-id="183ef-135">このトピックでは、IStreamFactory を使用してストリーム ベースのアプローチを使用してユーザー コードで XLANGMessage 変数を作成するためのベスト プラクティスも示します。</span><span class="sxs-lookup"><span data-stu-id="183ef-135">This topic also provides best practices for using IStreamFactory to construct XLANGMessage variables in user code using a stream-based approach.</span></span>  
  
 <span data-ttu-id="183ef-136">オーケストレーションによって呼び出されるヘルパー コンポーネント内で、XLANGMessage を処理するさまざまな方法の詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="183ef-136">For more information about the different ways to process an XLANGMessage within an helper component invoked by an orchestration, see the following topics:</span></span>  
  
-   <span data-ttu-id="183ef-137">[4 つの方法、第 1 部、オーケストレーションによって呼び出されるヘルパー コンポーネント内で、XLANGMessage を処理する](http://go.microsoft.com/fwlink/?LinkID=210420)(http://go.microsoft.com/fwlink/?LinkID=210420)します。</span><span class="sxs-lookup"><span data-stu-id="183ef-137">[4 Different ways to process an XLANGMessage within an helper component invoked by an orchestration Part 1](http://go.microsoft.com/fwlink/?LinkID=210420) (http://go.microsoft.com/fwlink/?LinkID=210420).</span></span>  
  
-   <span data-ttu-id="183ef-138">[4 つの方法、第 2 部、オーケストレーションによって呼び出されるヘルパー コンポーネント内で、XLANGMessage を処理する](http://go.microsoft.com/fwlink/?LinkID=210421)(http://go.microsoft.com/fwlink/?LinkID=210421)します。</span><span class="sxs-lookup"><span data-stu-id="183ef-138">[4 Different ways to process an XLANGMessage within an helper component invoked by an orchestration Part 2](http://go.microsoft.com/fwlink/?LinkID=210421) (http://go.microsoft.com/fwlink/?LinkID=210421).</span></span>  
  
### <a name="using-xpathreader-and-xpathcollection-to-extract-a-value-from-an-xlangmessage-object-from-a-method-invoked-by-an-orchestration"></a><span data-ttu-id="183ef-139">XPathReader と XPathCollection を使用して、オーケストレーションによって呼び出されたメソッドから XLANGMessage オブジェクトから値を抽出するには</span><span class="sxs-lookup"><span data-stu-id="183ef-139">Using XPathReader and XPathCollection to extract a value from an XLANGMessage object from a method invoked by an orchestration</span></span>  
 <span data-ttu-id="183ef-140">XMLDocument クラスをカスタム パイプライン コンポーネントなどのカスタム コードから XML メッセージの内容を読み取るまたはオーケストレーションによって呼び出されるヘルパー クラスを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="183ef-140">Avoid using the XMLDocument class to read the contents of XML messages from custom code, such as custom pipeline components or helper classes invoked by orchestrations.</span></span> <span data-ttu-id="183ef-141">XMLDocument インスタンスを使用して、XML メッセージを読み込み、これは効率的であり、メッセージの実際サイズの 10 倍の時間の最大メモリを必要があります、メモリにメッセージ全体が読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="183ef-141">When using an XMLDocument instance to load an XML message, the entire message is loaded into memory, which is inefficient and may require memory up to 10 times the actual size of the message.</span></span> <span data-ttu-id="183ef-142">XML メッセージの内容を読み取るのより効率的な方法は、ストリーミングの手法を使用して、Microsoft.BizTalk.Streaming.dll アセンブリによって提供されるストリーム クラスのいずれかの元のストリームをラップします。</span><span class="sxs-lookup"><span data-stu-id="183ef-142">A more efficient way of reading the contents of XML messages is to use a streaming technique to wrap the original stream with one of the stream classes provided by the Microsoft.BizTalk.Streaming.dll assembly.</span></span> <span data-ttu-id="183ef-143">この手法は、サイズの大きいメッセージを読み込むときに特に便利です。</span><span class="sxs-lookup"><span data-stu-id="183ef-143">This technique is particularly useful when loading large messages.</span></span>  
  
 <span data-ttu-id="183ef-144">特定の値は、XmlDocument クラスによって公開される SelectNodes、SelectSingleNode メソッドを使用する代わりに、XML ドキュメントからプルする必要がある場合として Microsoft.BizTalk.XPathReader.dll アセンブリによって提供される XPathReader クラスのインスタンスを使用して、次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="183ef-144">If specific values need to be pulled from an XML document, instead of using the SelectNodes and SelectSingleNode methods exposed by the XmlDocument class, use an instance of the XPathReader class provided by the Microsoft.BizTalk.XPathReader.dll assembly as illustrated in the following code example.</span></span>  
  
-   <span data-ttu-id="183ef-145">この例では、オーケストレーションによって呼び出されるメソッド内で XLANGMessage オブジェクトから指定した値を抽出する XPathReader と XPathCollection を使用しています。</span><span class="sxs-lookup"><span data-stu-id="183ef-145">This example illustrates using the XPathReader and XPathCollection to extract a given value from an XLANGMessage object inside a method invoked by an orchestration.</span></span>  
  
    ```  
    public static string SelectSingleNode(XLANGMessage message, string xPath)   
    {  
        try  
        {  
            if (message == null || string.IsNullOrEmpty(xPath))  
            {  
                return string.Empty;  
            }  
            using (XmlReader reader = (XmlReader)message[0].RetrieveAs(typeof(XmlReader)))  
            {  
                XPathCollection xPathCollection = new XPathCollection();  
                XPathReader xPathReader = new XPathReader(reader, xPathCollection);  
                xPathCollection.Add(xPath);  
                while (xPathReader.ReadUntilMatch())  
                {  
                    if (xPathReader.Match(0))  
                    {  
                        return xPathReader.ReadString();  
                    }  
                }  
            }  
        }  
        catch (Exception ex)  
        {  
            ...  
        }  
        finally  
        {  
            message.Dispose();  
        }  
        return string.Empty;  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="183ef-146">参照</span><span class="sxs-lookup"><span data-stu-id="183ef-146">See Also</span></span>  
 [<span data-ttu-id="183ef-147">BizTalk Server アプリケーションの最適化</span><span class="sxs-lookup"><span data-stu-id="183ef-147">Optimizing BizTalk Server Applications</span></span>](../technical-guides/optimizing-biztalk-server-applications.md)