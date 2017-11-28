---
title: "パイプラインのパフォーマンスの最適化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5137747-0dcf-4c96-90a7-01afb92f56a6
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4311efd0d23e29b63f02fc34b1650a894d29d335
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="optimizing-pipeline-performance"></a><span data-ttu-id="cad3f-102">パイプラインのパフォーマンスを最適化します。</span><span class="sxs-lookup"><span data-stu-id="cad3f-102">Optimizing Pipeline Performance</span></span>
<span data-ttu-id="cad3f-103">このトピックでのパイプラインのパフォーマンスを最適化するためのガイドラインを説明します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="cad3f-103">This topic describes guidelines for optimizing performance of pipelines in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
## <a name="best-practices-for-optimizing-performance-of-biztalk-server-pipelines"></a><span data-ttu-id="cad3f-104">BizTalk Server パイプラインのパフォーマンスを最適化するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="cad3f-104">Best practices for optimizing performance of BizTalk Server pipelines</span></span>  
  
1.  <span data-ttu-id="cad3f-105">パイプライン コンポーネントは、パフォーマンスに大きな影響を与えるため (たとえば、パススルー パイプライン コンポーネントを実行する、XML アセンブラー/逆アセンブラー パイプライン コンポーネントをより最大 30%)、そのカスタム パイプライン コンポーネントが実行することを確認してください最適な状態での展開では、それらを実装前にします。</span><span class="sxs-lookup"><span data-stu-id="cad3f-105">Because pipeline components have a significant impact on performance (for example, a pass-through pipeline component performs up to 30 percent better than an XML assembler/disassembler pipeline component), make sure that any custom pipeline components perform optimally before implementing them in your deployment.</span></span> <span data-ttu-id="cad3f-106">BizTalk アプリケーションの全体的なパフォーマンスを最大化したい場合は、パイプライン コンポーネントで、カスタム パイプラインの数を最小限に抑えます。</span><span class="sxs-lookup"><span data-stu-id="cad3f-106">Minimize the number of pipeline components in your custom pipelines if you want to maximize the overall performance of your BizTalk application.</span></span>  
  
2.  <span data-ttu-id="cad3f-107">パフォーマンスを向上できます全体と、パイプライン コンポーネントでメッセージの永続化の頻度を減らすことによって冗長性を最小化するようにコンポーネントをコーディングします。</span><span class="sxs-lookup"><span data-stu-id="cad3f-107">You also can improve overall performance by reducing the message persistence frequency in your pipeline component and by coding your component to minimize redundancy.</span></span> <span data-ttu-id="cad3f-108">すべてのカスタム アセンブリは具体的には、カスタムの追跡コンポーネントと同様に、パフォーマンスに悪影響を及ぼす可能性のあるアイテム テストするくださいとは別に負荷が高い状況を検索して、システムが最大能力で操作するときに、その動作を確認するにはボトルネックです。</span><span class="sxs-lookup"><span data-stu-id="cad3f-108">Every custom assembly and in particular artifacts that could potentially disrupt performance, like custom tracking components, should be tested separately under heavy load condition to observe their behavior when the system is working at full capacity and to find any possible bottlenecks.</span></span>  
  
3.  <span data-ttu-id="cad3f-109">パイプライン コンポーネント内の受信メッセージを読み取る必要がある場合は、メモリを使用してにドキュメント全体が読み込まれないように、 **XmlDocument**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="cad3f-109">If you need to read the inbound message inside a pipeline component, avoid loading the entire document into memory using an **XmlDocument** object.</span></span> <span data-ttu-id="cad3f-110">インスタンスで必要な領域の量、 **XmlDocument**を読み込んで、XML ドキュメントのメモリ内表現を作成するクラスは、実際のメッセージ サイズの 10 倍までです。</span><span class="sxs-lookup"><span data-stu-id="cad3f-110">The amount of space required by an instance of the **XmlDocument** class to load and create an in-memory representation of a XML document is up to 10 times the actual message size.</span></span> <span data-ttu-id="cad3f-111">メッセージを読み取るために使用する必要があります、 **XmlTextReader**と共に、次のクラスのインスタンスのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="cad3f-111">In order to read a message, you should use an **XmlTextReader** object along with an instance of the following classes:</span></span>  
  
    -   <span data-ttu-id="cad3f-112">**VirtualStream (Microsoft.BizTalk.Streaming.dll)** -このクラスのソース コードにある 2 つの場所、パイプラインの SDK の下にある次のように: \samples\pipelines\arbitraryxpathpropertyhandler および SDK\Samples\Pipelines\SchemaResolverComponent\SchemaResolverFlatFileDasm です。</span><span class="sxs-lookup"><span data-stu-id="cad3f-112">**VirtualStream (Microsoft.BizTalk.Streaming.dll)** - The source code for this class is located in two locations under the Pipelines SDK as follows: SDK\Samples\Pipelines\ArbitraryXPathPropertyHandler and SDK\Samples\Pipelines\SchemaResolverComponent\SchemaResolverFlatFileDasm.</span></span>  
  
    -   <span data-ttu-id="cad3f-113">**ReadOnlySeekableStream (Microsoft.BizTalk.Streaming.dll)**です。</span><span class="sxs-lookup"><span data-stu-id="cad3f-113">**ReadOnlySeekableStream (Microsoft.BizTalk.Streaming.dll)**.</span></span>  
  
    -   <span data-ttu-id="cad3f-114">**SeekAbleReadOnlyStream** -このクラスのソース コードにある 2 つの場所、パイプラインの SDK の下にある次のように: \samples\pipelines\arbitraryxpathpropertyhandler および SDK\Samples\Pipelines\SchemaResolverComponent\SchemaResolverFlatFileDasm です。</span><span class="sxs-lookup"><span data-stu-id="cad3f-114">**SeekAbleReadOnlyStream** - The source code for this class is located in two locations under the Pipelines SDK as follows: SDK\Samples\Pipelines\ArbitraryXPathPropertyHandler and SDK\Samples\Pipelines\SchemaResolverComponent\SchemaResolverFlatFileDasm.</span></span>  
  
4.  <span data-ttu-id="cad3f-115">PassThruReceive パイプラインと可能な限り PassThruTransmit の標準パイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="cad3f-115">Use the PassThruReceive and the PassThruTransmit standard pipelines whenever possible.</span></span> <span data-ttu-id="cad3f-116">任意のパイプライン コンポーネントが含まれていないし、メッセージの処理を実行しません。</span><span class="sxs-lookup"><span data-stu-id="cad3f-116">They do not contain any pipeline component and do not perform any processing of the message.</span></span> <span data-ttu-id="cad3f-117">このため、それらには受信または送信メッセージの最大のパフォーマンスを確認してください。</span><span class="sxs-lookup"><span data-stu-id="cad3f-117">For this reason, they ensure maximum performance in receiving or sending messages.</span></span> <span data-ttu-id="cad3f-118">バイナリ メッセージを送信する必要がある場合は、BizTalk メッセージ ボックスと送信ポートで PassThruTransmit パイプラインにバイナリ ドキュメントを公開する必要がある場合は、受信場所で PassThruReceive パイプラインを使用できます。</span><span class="sxs-lookup"><span data-stu-id="cad3f-118">You can use a PassThruReceive pipeline on a receive location if you need to publish a binary document to the BizTalk MessageBox and a PassThruTransmit pipeline on a send port if you need to send out a binary message.</span></span> <span data-ttu-id="cad3f-119">メッセージがフォーマットされているし、転送する準備ができて場合オーケストレーションにバインドされる物理送信ポートで PassThruTransmit パイプラインを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="cad3f-119">You can also use the PassThruTransmit pipeline on a physical send port bound to an orchestration if the message has been formatted and is ready to be transmitted.</span></span> <span data-ttu-id="cad3f-120">次の操作のいずれかを実行する必要がある場合、別のアプローチを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cad3f-120">You will need to use a different approach if you need to accomplish one of the following actions:</span></span>  
  
    -   <span data-ttu-id="cad3f-121">受信 XML またはフラット ファイル メッセージのコンテキストにプロパティを昇格します。</span><span class="sxs-lookup"><span data-stu-id="cad3f-121">Promote properties on the context of an inbound XML or Flat File message.</span></span>  
  
    -   <span data-ttu-id="cad3f-122">受信場所内のマップを適用します。</span><span class="sxs-lookup"><span data-stu-id="cad3f-122">Apply a map inside a receive location.</span></span>  
  
    -   <span data-ttu-id="cad3f-123">メッセージをサブスクライブするオーケストレーションでマップを適用します。</span><span class="sxs-lookup"><span data-stu-id="cad3f-123">Apply a map in an orchestration that subscribes to a message.</span></span>  
  
    -   <span data-ttu-id="cad3f-124">メッセージをサブスクライブする送信ポートでマップを適用します。</span><span class="sxs-lookup"><span data-stu-id="cad3f-124">Apply a map on a send port that subscribes to a message.</span></span>  
  
     <span data-ttu-id="cad3f-125">これらの操作を行うためには、プローブし、受信パイプライン内のドキュメントの種類を検出して MessageType コンテキスト プロパティに、(名前空間 #root 名) の値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="cad3f-125">To accomplish one of these actions, you must probe and discover the document type inside the receive pipeline and assign the (namespace#root-name) value to the MessageType context property.</span></span> <span data-ttu-id="cad3f-126">この操作は、通常、Xml 逆アセンブラー コンポーネント (XmlDasmComp) などの逆アセンブラー コンポーネントまたはフラット ファイル逆アセンブラー コンポーネント (FFDasmComp) して行います。</span><span class="sxs-lookup"><span data-stu-id="cad3f-126">This operation is typically accomplished by a disassembler component such as the Xml Disassembler component (XmlDasmComp) or the Flat File disassembler component (FFDasmComp).</span></span> <span data-ttu-id="cad3f-127">この例では、standard (たとえば、XmlReceive パイプライン) または標準またはカスタム逆アセンブラー コンポーネントを含むカスタム パイプラインを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cad3f-127">In this case, you need to use a standard (for instance, XmlReceive pipeline) or a custom pipeline that contains a standard or a custom disassembler component.</span></span>  
  
5.  <span data-ttu-id="cad3f-128">できる限り遅くリソースを取得し、できるだけ早くリリースできるだけします。</span><span class="sxs-lookup"><span data-stu-id="cad3f-128">Acquire resources as late as possible and release them as early as possible.</span></span> <span data-ttu-id="cad3f-129">たとえば、データベース上のデータにアクセスする必要がある場合は、できるだけ遅く接続を開くしてできるだけ早く閉じます。</span><span class="sxs-lookup"><span data-stu-id="cad3f-129">For example, if you need to access data on a database, open the connection as late as possible and close it as soon as possible.</span></span> <span data-ttu-id="cad3f-130">C# を使用して、暗黙的に破棄可能なオブジェクトを解放するステートメントを使用して、または、オブジェクトを明示的に破棄するには、try – catch – finally ステートメントの finally ブロックします。</span><span class="sxs-lookup"><span data-stu-id="cad3f-130">Use the C# using statement to implicitly release disposable objects or the finally block of a try-catch-finally statement to explicitly dispose your objects.</span></span> <span data-ttu-id="cad3f-131">すると、コンポーネントをデバッグする単純なソース コードをインストルメント化します。</span><span class="sxs-lookup"><span data-stu-id="cad3f-131">Instrument your source code to make your components simple to debug.</span></span>  
  
6.  <span data-ttu-id="cad3f-132">厳密にメッセージの処理を高速化する必要はありません、パイプラインからコンポーネントを削除します。</span><span class="sxs-lookup"><span data-stu-id="cad3f-132">Eliminate any components from your pipelines that are not strictly required to speed up message processing.</span></span>  
  
7.  <span data-ttu-id="cad3f-133">受信パイプライン内のメッセージのルーティング (オーケストレーション、送信ポート) またはメッセージ コンテキスト プロパティ (送信ポート) の降格する必要がある場合にのみ、メッセージ コンテキストに項目を昇格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cad3f-133">Inside a receive pipeline, you should promote items to the message context only if you need them for message routing (Orchestrations, Send Ports) or demotion of message context properties (Send Ports).</span></span>  
  
8.  <span data-ttu-id="cad3f-134">メッセージを表示してメタデータを含める必要があるあり、ルーティングまたは降格目的で、使用するメタデータを使用しない場合、 **IBaseMessageContext.Write**メソッドの代わりに、 **IBaseMessageContext.Promote**メソッド。</span><span class="sxs-lookup"><span data-stu-id="cad3f-134">If you need to include metadata with a message, and you don't use the metadata for routing or demotion purposes, use the **IBaseMessageContext.Write** method instead of the **IBaseMessageContext.Promote** method.</span></span>  
  
9. <span data-ttu-id="cad3f-135">XPath 式を使用してメッセージから情報を抽出する必要がある場合は、メモリを使用してにドキュメント全体が読み込まれないように、 **XmlDocument**だけ使用するオブジェクトを**SelectNodes**または**SelectSingleNode**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="cad3f-135">If you need to extract information from a message using an XPath expression, avoid loading the entire document into memory using an **XmlDocument** object just to use the **SelectNodes** or **SelectSingleNode** methods.</span></span> <span data-ttu-id="cad3f-136">またはで説明する手法を使用して[ストリーミングでのメモリ使用量の最適化](../technical-guides/optimizing-memory-usage-with-streaming.md)です。</span><span class="sxs-lookup"><span data-stu-id="cad3f-136">Alternatively, use the techniques described in [Optimizing Memory Usage with Streaming](../technical-guides/optimizing-memory-usage-with-streaming.md).</span></span>  
  
## <a name="use-streaming-to-minimize-the-memory-footprint-required-when-loading-messages-in-pipelines"></a><span data-ttu-id="cad3f-137">ストリーミングを使用して、パイプラインでメッセージを読み込むときに必要なメモリ使用量を最小限に抑える</span><span class="sxs-lookup"><span data-stu-id="cad3f-137">Use streaming to minimize the memory footprint required when loading messages in pipelines</span></span>  
 <span data-ttu-id="cad3f-138">次の手法では、パイプラインにメッセージを読み込む場合は、メッセージのメモリ使用量を最小限に抑える方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cad3f-138">The following techniques describe how to minimize the memory footprint of a message when loading the message into a pipeline.</span></span>  
  
### <a name="use-readonlyseekablestream-and-virtualstream-to-process-a-message-from-a-pipeline-component"></a><span data-ttu-id="cad3f-139">ReadOnlySeekableStream と VirtualStream パイプライン コンポーネントからのメッセージの処理を使用してください。</span><span class="sxs-lookup"><span data-stu-id="cad3f-139">Use ReadOnlySeekableStream and VirtualStream to process a message from a pipeline component</span></span>  
 <span data-ttu-id="cad3f-140">メッセージ全体をパイプライン コンポーネントの内部でメモリに読み込まれないようにするベスト プラクティスと見なされます。</span><span class="sxs-lookup"><span data-stu-id="cad3f-140">It is considered a best practice to avoid loading the entire message into memory inside pipeline components.</span></span> <span data-ttu-id="cad3f-141">優先のアプローチは、カスタム ストリームの実装とし、要求が行われる読み取りとして、受信ストリームをラップする、カスタム ストリームの実装が、基になる、ラップされたストリームを読み取り、(純粋なストリーミング的に) 読み取られると、データを処理します。</span><span class="sxs-lookup"><span data-stu-id="cad3f-141">A preferable approach is to wrap the inbound stream with a custom stream implementation, and then as read requests are made, the custom stream implementation reads the underlying, wrapped stream and processes the data as it is read (in a pure streaming manner).</span></span> <span data-ttu-id="cad3f-142">これを実装するのには非常に難しくなり、ストリームで実行する必要がある新機能によって、可能なことができない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cad3f-142">This can be very hard to implement and may not be possible, depending on what needs to be done with the stream.</span></span> <span data-ttu-id="cad3f-143">このケースでは、使用して、 **ReadOnlySeekableStream**と**VirtualStream** Microsoft.BizTalk.Streaming.dll によって公開されるクラスです。</span><span class="sxs-lookup"><span data-stu-id="cad3f-143">In this case, use the **ReadOnlySeekableStream** and **VirtualStream** classes exposed by the Microsoft.BizTalk.Streaming.dll.</span></span> <span data-ttu-id="cad3f-144">これらの実装を提供しても[任意の XPath プロパティ ハンドラ (BizTalk Server サンプル)](http://go.microsoft.com/fwlink/?LinkId=160069) (http://go.microsoft.com/fwlink/?LinkId=160069) BizTalk SDK に含まれています。**ReadOnlySeekableStream**カーソルは、ストリームの先頭に移動できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cad3f-144">An implementation of these is also provided in [Arbitrary XPath Property Handler (BizTalk Server Sample)](http://go.microsoft.com/fwlink/?LinkId=160069) (http://go.microsoft.com/fwlink/?LinkId=160069) in the BizTalk SDK.**ReadOnlySeekableStream** ensures that the cursor can be repositioned to the beginning of the stream.</span></span> <span data-ttu-id="cad3f-145">**VirtualStream**サイズが、指定されたしきい値を超えていない限り、MemoryStream を内部で、使用する場合、ファイル システムにストリームが書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="cad3f-145">The **VirtualStream** will use a MemoryStream internally, unless the size is over a specified threshold, in which case it will write the stream to the file system.</span></span> <span data-ttu-id="cad3f-146">これら 2 つのストリームの組み合わせで使用する (を使用して**VirtualStream**の永続的な記憶域として、 **ReadOnlySeekableStream**)"seekability"と「オーバーフロー ファイル システムに」機能の両方を提供します。</span><span class="sxs-lookup"><span data-stu-id="cad3f-146">Use of these two streams in combination (using **VirtualStream** as persistent storage for the **ReadOnlySeekableStream**) provides both “seekability” and “overflow to file system” capabilities.</span></span> <span data-ttu-id="cad3f-147">これには、メッセージ全体をメモリに読み込むことがなくサイズの大きいメッセージの処理が対応しています。</span><span class="sxs-lookup"><span data-stu-id="cad3f-147">This accommodates the processing of large messages without loading the entire message into memory.</span></span> <span data-ttu-id="cad3f-148">次のコードは、この機能を実装するパイプライン コンポーネントで使用可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cad3f-148">The following code could be used in a pipeline component to implement this functionality.</span></span>  
  
```  
int bufferSize = 0x280;  
int thresholdSize = 0x100000;  
Stream vStream = new VirtualStream(bufferSize, thresholdSize);  
Stream seekStream = new ReadOnlySeekableStream(inboundStream, vStream, bufferSize);  
```  
  
 <span data-ttu-id="cad3f-149">このコードは、bufferSize を公開することで「オーバーフローしきい値」を提供し、各 thresholdSize 変数は、受信場所または送信ポート構成します。</span><span class="sxs-lookup"><span data-stu-id="cad3f-149">This code provides an “overflow threshold” by exposing bufferSize and thresholdSize variables on each receive location or send port configuration.</span></span> <span data-ttu-id="cad3f-150">開発者や管理者がさまざまなメッセージ型と (32 ビット エディションとなどのさまざまな構成が、このオーバーフローしきい値を調整し、ことができます。64 ビット)。</span><span class="sxs-lookup"><span data-stu-id="cad3f-150">This overflow threshold can then be adjusted by developers or administrators for different message types and different configurations (such as 32-bit vs. 64-bit).</span></span>  
  
### <a name="using-xpathreader-and-xpathcollection-to-extract-a-given-ibasemessage-object-from-within-a-custom-pipeline-component"></a><span data-ttu-id="cad3f-151">XPathReader と XPathCollection を使用して、カスタム パイプライン コンポーネントの中から指定された IBaseMessage オブジェクトを抽出します。</span><span class="sxs-lookup"><span data-stu-id="cad3f-151">Using XPathReader and XPathCollection to extract a given IBaseMessage object from within a custom pipeline component.</span></span>  
 <span data-ttu-id="cad3f-152">特定の値を使用する代わりに、XML ドキュメントからプルされる必要がある場合、 **SelectNodes**と**SelectSingleNode** XmlDocument クラスによって公開されたメソッドが XPathReader クラスのインスタンスを使用します。次のコード例に示すように、Microsoft.BizTalk.XPathReader.dll アセンブリによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="cad3f-152">If specific values need to be pulled from an XML document, instead of using the **SelectNodes** and **SelectSingleNode** methods exposed by the XmlDocument class, use an instance of the XPathReader class provided by the Microsoft.BizTalk.XPathReader.dll assembly as illustrated in the following code example.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cad3f-153">小さいメッセージを特に、SelectNodes または SelectSingleNode と共に、XmlDocument を使用することがあります XPathReader を使用するよりも優れたパフォーマンスが、XPathReader では、アプリケーションのフラットなメモリ プロファイルを維持することができます。</span><span class="sxs-lookup"><span data-stu-id="cad3f-153">For smaller messages especially, using an XmlDocument with SelectNodes or SelectSingleNode may provide better performance than using XPathReader, but XPathReader allows you to keep a flat memory profile for your application.</span></span>  
  
 <span data-ttu-id="cad3f-154">XPathReader と XPathCollection を使用して抽出する方法を示します、指定された**IBaseMessage**カスタム パイプライン コンポーネント内のオブジェクトにします。</span><span class="sxs-lookup"><span data-stu-id="cad3f-154">This example shows how to use the XPathReader and XPathCollection to extract a given **IBaseMessage** object from within a custom pipeline component.</span></span>  
  
```  
public IBaseMessage Execute(IPipelineContext context, IBaseMessage message)  
{  
    try  
    {  
        ...  
        IBaseMessageContext messageContext = message.Context;  
        if (string.IsNullOrEmpty(xPath) && string.IsNullOrEmpty(propertyValue))  
        {  
            throw new ArgumentException(...);  
        }  
        IBaseMessagePart bodyPart = message.BodyPart;  
        Stream inboundStream = bodyPart.GetOriginalDataStream();  
        VirtualStream virtualStream = new VirtualStream(bufferSize, thresholdSize);  
        ReadOnlySeekableStream readOnlySeekableStream = new ReadOnlySeekableStream(inboundStream, virtualStream, bufferSize);  
        XmlTextReader xmlTextReader = new XmlTextReader(readOnlySeekableStream);  
        XPathCollection xPathCollection = new XPathCollection();  
        XPathReader xPathReader = new XPathReader(xmlTextReader, xPathCollection);  
        xPathCollection.Add(xPath);  
        bool ok = false;  
        while (xPathReader.ReadUntilMatch())  
        {  
            if (xPathReader.Match(0) && !ok)  
            {  
                propertyValue = xPathReader.ReadString();  
                messageContext.Promote(propertyName, propertyNamespace, propertyValue);  
                ok = true;  
            }  
        }  
        readOnlySeekableStream.Position = 0;  
        bodyPart.Data = readOnlySeekableStream;  
    }  
    catch (Exception ex)  
    {  
        if (message != null)  
        {  
            message.SetErrorInfo(ex);  
        }  
        ...  
        throw ex;  
    }  
    return message;  
}  
```  
  
## <a name="use-xmlreader-and-xmlwriter-with-xmltranslatorstream-to-process-a-message-from-a-pipeline-component"></a><span data-ttu-id="cad3f-155">パイプライン コンポーネントからのメッセージを処理するのに XMLTranslatorStream で XMLReader および XMLWriter を使用します。</span><span class="sxs-lookup"><span data-stu-id="cad3f-155">Use XMLReader and XMLWriter with XMLTranslatorStream to process a message from a pipeline component</span></span>  
 <span data-ttu-id="cad3f-156">ストリーミングの手法を使用してカスタム パイプライン コンポーネントを実装するための別の方法は、.NET を使用する**XmlReader**と**XmlWriter**クラスと組み合わせて、 **XmlTranslatorStream** BizTalk Server によって提供されるクラスです。</span><span class="sxs-lookup"><span data-stu-id="cad3f-156">Another method for implementing a custom pipeline component which uses a streaming approach is to use the .NET **XmlReader** and **XmlWriter** classes in conjunction with the **XmlTranslatorStream** class provided by BizTalk Server.</span></span> <span data-ttu-id="cad3f-157">たとえば、 **NamespaceTranslatorStream** Microsoft.BizTalk.Pipeline.Components アセンブリに含まれているクラスから継承**XmlTranslatorStream**し、古い名前空間の代わりに使用することができますストリームに含まれる XML ドキュメントに新しいものです。</span><span class="sxs-lookup"><span data-stu-id="cad3f-157">For example, the **NamespaceTranslatorStream** class contained in the Microsoft.BizTalk.Pipeline.Components assembly inherits from **XmlTranslatorStream** and can be used to replace an old namespace with a new one in the XML document contained in the stream.</span></span> <span data-ttu-id="cad3f-158">新しいインスタンスをメッセージのボディ部の元のデータ ストリームをラップするカスタム パイプライン コンポーネントの内部には、この機能を使用するために、 **NamespaceTranslatorStream**クラスおよび後者を返します。</span><span class="sxs-lookup"><span data-stu-id="cad3f-158">In order to use this functionality inside a custom a pipeline component, you can wrap the original data stream of the message body part with a new instance of the **NamespaceTranslatorStream** class and return the latter.</span></span> <span data-ttu-id="cad3f-159">この方法で、受信メッセージがない読み取り、処理内では、パイプライン コンポーネントが、ストリームは、同一のパイプラインの後続のコンポーネントによって読み取られるか、最後に、ドキュメントを BizTalk Server に発行する前に、メッセージ エージェントによって使用される場合にのみメッセージ ボックスです。</span><span class="sxs-lookup"><span data-stu-id="cad3f-159">In this way the inbound message is not read or processed inside the pipeline component, but only when the stream is read by a subsequent component in the same pipeline or is finally consumed by the Message Agent before publishing the document to the BizTalk Server MessageBox.</span></span>  
  
 <span data-ttu-id="cad3f-160">次の例では、この機能を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cad3f-160">The following example illustrates how to use this functionality.</span></span>  
  
```  
public IBaseMessage Execute(IPipelineContext context, IBaseMessage message)  
{  
   IBaseMessage outboundMessage = message;  
   try  
   {  
      if (context == null)  
      {  
         throw new ArgumentException(Resources.ContextIsNullMessage);  
      }  
      if (message == null)  
      {  
         throw new ArgumentException(Resources.InboundMessageIsNullMessage);  
      }  
  
      IBaseMessagePart bodyPart = message.BodyPart;  
      Stream stream = new NamespaceTranslatorStream(context,   
                                                    bodyPart.GetOriginalDataStream(),   
                                                    oldNamespace,   
                                                    newNamespace);  
      context.ResourceTracker.AddResource(stream);  
      bodyPart.Data = stream;  
   }  
   catch (Exception ex)  
   {  
      if (message != null)  
      {  
         message.SetErrorInfo(ex);  
      }  
  
      throw ex;  
   }  
   return outboundMessage;  
}  
```  
  
## <a name="using-resourcetracker-in-custom-pipeline-components"></a><span data-ttu-id="cad3f-161">カスタム パイプライン コンポーネントで ResourceTracker を使用します。</span><span class="sxs-lookup"><span data-stu-id="cad3f-161">Using ResourceTracker in Custom Pipeline Components</span></span>  
 <span data-ttu-id="cad3f-162">パイプライン コンポーネントを作成オブジェクトの有効期間を管理し、これらのオブジェクトが不要にするとすぐに、ガベージ コレクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="cad3f-162">A pipeline component should manage the lifetime of the objects it creates and perform garbage collection as soon as these objects are no longer required.</span></span>  <span data-ttu-id="cad3f-163">場合は、パイプライン コンポーネントには、このようなオブジェクトをパイプラインがパイプラインのコンテキストからフェッチするリソースの追跡ツールに追加する必要がありますし、最後のパイプラインの実行が終了するまでにオブジェクトの有効期間が希望しています。</span><span class="sxs-lookup"><span data-stu-id="cad3f-163">If the pipeline component wants the lifetime of the objects to last until the end of pipeline execution, then you must add such objects to the resource tracker that your pipeline may fetch from the pipeline context.</span></span>  
  
 <span data-ttu-id="cad3f-164">リソースの追跡ツールは、次の種類のオブジェクトに使用します。</span><span class="sxs-lookup"><span data-stu-id="cad3f-164">The resource tracker is used for the following types of objects:</span></span>  
  
-   <span data-ttu-id="cad3f-165">ストリーム オブジェクト</span><span class="sxs-lookup"><span data-stu-id="cad3f-165">Stream objects</span></span>  
  
-   <span data-ttu-id="cad3f-166">COM オブジェクト</span><span class="sxs-lookup"><span data-stu-id="cad3f-166">COM objects</span></span>  
  
-   <span data-ttu-id="cad3f-167">IDisposable オブジェクト</span><span class="sxs-lookup"><span data-stu-id="cad3f-167">IDisposable objects</span></span>  
  
 <span data-ttu-id="cad3f-168">メッセージ エンジンはそれが成功したか失敗したかどうかに関係なく、パイプラインは完全に実行した後、適切なタイミングでリソースの追跡ツールに追加されるすべてのネイティブ リソースが解放されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cad3f-168">The message engine ensures that all the native resources that are added to the resource tracker are released at an appropriate time, that is after the pipeline is completely executed, regardless of whether it was successful or failed.</span></span> <span data-ttu-id="cad3f-169">リソース トラッカー インスタンスとそれを追跡しているオブジェクトの有効期間は、パイプラインのコンテキスト オブジェクトによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="cad3f-169">The lifetime of the Resource Tracker instance and the objects that it is tracking is managed by the pipeline context object.</span></span> <span data-ttu-id="cad3f-170">パイプラインのコンテキストは IPipelineContext インターフェイスを実装するオブジェクトをパイプライン コンポーネントのすべての種類に提供されます。</span><span class="sxs-lookup"><span data-stu-id="cad3f-170">The pipeline context is made available to all types of pipeline components through an object that implements the IPipelineContext interface.</span></span>  
  
 <span data-ttu-id="cad3f-171">たとえば、次のコード スニペットは、カスタム パイプライン コンポーネントで ResourceTracker プロパティを使用する方法について説明するサンプルです。</span><span class="sxs-lookup"><span data-stu-id="cad3f-171">For example, the following code snippet is a sample that illustrates how to use ResourceTracker property in custom pipeline components.</span></span> <span data-ttu-id="cad3f-172">コード スニペットを ResourceTracker プロパティを使用するには、次のパラメーターを使用して`IPipelineContext.ResourceTracker.AddResource`です。</span><span class="sxs-lookup"><span data-stu-id="cad3f-172">To use ResourceTracker property, the code snippet uses the following parameter `IPipelineContext.ResourceTracker.AddResource`.</span></span> <span data-ttu-id="cad3f-173">このパラメーターには。</span><span class="sxs-lookup"><span data-stu-id="cad3f-173">In this parameter:</span></span>  
  
-   <span data-ttu-id="cad3f-174">IPipelineContext インターフェイスは、ドキュメント処理に固有のすべてのインターフェイスへのアクセスに使用するメソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="cad3f-174">IPipelineContext interface defines the methods used to access all document processing-specific interfaces.</span></span>  
  
-   <span data-ttu-id="cad3f-175">ResourceTracker プロパティは、IPipelineContext を参照し、パイプライン処理の最後に明示的に破棄されるオブジェクトを追跡するために使用します。</span><span class="sxs-lookup"><span data-stu-id="cad3f-175">ResourceTracker property references IPipelineContext and is used to keep track of objects that will be explicitly disposed at the end of pipeline processing.</span></span>  
  
-   <span data-ttu-id="cad3f-176">ResourceTracker.AddResource メソッド COM オブジェクト、破棄可能なオブジェクトおよびストリームを追跡するために使用およびは常に内で使用、カスタム パイプライン コンポーネントを明示的に閉じる (ストリーム)、(IDisposable オブジェクト) を破棄またはこれら (COM オブジェクト) のリリースBizTalk メッセージ ボックスに、メッセージが公開される場合、リソースの種類。</span><span class="sxs-lookup"><span data-stu-id="cad3f-176">ResourceTracker.AddResource method is used to keep track of COM objects, Disposable objects and Streams, and should always be used inside a custom pipeline component to explicitly close (streams), dispose (IDisposable objects) or release (COM objects) these types of resources when a message is published to the BizTalk MessageBox.</span></span>  
  
```  
public IBaseMessage Execute(IPipelineContext pContext, IBaseMessage pInMsg)  
  
{  
      IBaseMessage outMessage = pContext.GetMessageFactory().CreateMessage();  
  
      IBaseMessagePart outMsgBodyPart = pContext.GetMessageFactory().CreateMessagePart();  
  
      outMsgBodyPart.Charset = Encoding.UTF8.WebName;   
  
      outMsgBodyPart.ContentType = "text/xml";  
  
//Code to load message content in the MemoryStream object//  
  
      MemoryStream messageData = new MemoryStream();  
  
   //The MemoryStream needs to be closed after the whole pipeline has executed, thus adding it into ResourceTracker//  
  
      pContext.ResourceTracker.AddResource(messageData);  
  
//Custom pipeline code to load message data into xmlPayload//  
  
      XmlDocument xmlPayLoad = new XmlDocument();  
  
      xmlPayLoad.Save(messageData);  
  
      messageData.Seek(0, SeekOrigin.Begin);  
  
//The new stream is assigned to the message part’s data//  
  
      outMsgBodyPart.Data = messageData;  
  
// Pipeline component logic here//  
  
      return outMessage;  
  
}  
```  
  
## <a name="comparison-of-loading-messages-into-pipelines-using-an-in-memory-approach-and-using-a-streaming-approach"></a><span data-ttu-id="cad3f-177">読み込みメッセージをインメモリ アプローチを使用して、ストリーミングの手法を使用するパイプラインの比較</span><span class="sxs-lookup"><span data-stu-id="cad3f-177">Comparison of loading messages into pipelines using an in-memory approach and using a streaming approach</span></span>  
 <span data-ttu-id="cad3f-178">次の情報は、Nic Barden ブログから取得されました[http://blogs.objectsharp.com/cs/blogs/nbarden/archive/2008/04/14/developing-streaming-pipeline-components-part-1.aspx](http://go.microsoft.com/fwlink/?LinkId=160228) (http://go.microsoft.com/fwlink/?LinkId=160228)。</span><span class="sxs-lookup"><span data-stu-id="cad3f-178">The following information was taken from Nic Barden’s blog, [http://blogs.objectsharp.com/cs/blogs/nbarden/archive/2008/04/14/developing-streaming-pipeline-components-part-1.aspx](http://go.microsoft.com/fwlink/?LinkId=160228) (http://go.microsoft.com/fwlink/?LinkId=160228).</span></span> <span data-ttu-id="cad3f-179">次の表は、パイプライン インメモリ アプローチを使用して、ストリーミングの手法の利用に読み込みメッセージの集計の比較を提供します。</span><span class="sxs-lookup"><span data-stu-id="cad3f-179">This table provides a summarized comparison of loading messages into pipelines using an in-memory approach and using a streaming approach.</span></span>  
  
|<span data-ttu-id="cad3f-180">比較しています.</span><span class="sxs-lookup"><span data-stu-id="cad3f-180">Comparison of...</span></span>|<span data-ttu-id="cad3f-181">ストリーミング</span><span class="sxs-lookup"><span data-stu-id="cad3f-181">Streaming</span></span>|<span data-ttu-id="cad3f-182">メモリ内</span><span class="sxs-lookup"><span data-stu-id="cad3f-182">In memory</span></span>|  
|----------------------|---------------|---------------|  
|<span data-ttu-id="cad3f-183">1 つのメッセージのメモリ使用量</span><span class="sxs-lookup"><span data-stu-id="cad3f-183">Memory usage per message</span></span>|<span data-ttu-id="cad3f-184">メッセージのサイズに関係なく、低</span><span class="sxs-lookup"><span data-stu-id="cad3f-184">Low, regardless of message size</span></span>|<span data-ttu-id="cad3f-185">高 (メッセージのサイズによって異なります)</span><span class="sxs-lookup"><span data-stu-id="cad3f-185">High (varies depending on message size)</span></span>|  
|<span data-ttu-id="cad3f-186">XML データの処理に使用する一般的なクラス</span><span class="sxs-lookup"><span data-stu-id="cad3f-186">Common classes used to process XML data</span></span>|<span data-ttu-id="cad3f-187">構築されたのとではカスタム派生します。</span><span class="sxs-lookup"><span data-stu-id="cad3f-187">Built in and custom derivations of:</span></span><br /><br /> <span data-ttu-id="cad3f-188">XmlTranslatorStream、XmlReader、および XmlWriter</span><span class="sxs-lookup"><span data-stu-id="cad3f-188">XmlTranslatorStream, XmlReader and XmlWriter</span></span>|<span data-ttu-id="cad3f-189">XmlDocument、XPathDocument、MemoryStream および VirtualStream</span><span class="sxs-lookup"><span data-stu-id="cad3f-189">XmlDocument, XPathDocument, MemoryStream and VirtualStream</span></span>|  
|<span data-ttu-id="cad3f-190">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="cad3f-190">Documentation</span></span>|<span data-ttu-id="cad3f-191">Poor – 多くのサポートされないと文書化されていない BizTalk クラス</span><span class="sxs-lookup"><span data-stu-id="cad3f-191">Poor – many un-supported and un-documented BizTalk classes</span></span>|<span data-ttu-id="cad3f-192">非常に良好 - .NET Framework クラス</span><span class="sxs-lookup"><span data-stu-id="cad3f-192">Very good - .NET Framework classes</span></span>|  
|<span data-ttu-id="cad3f-193">「処理ロジック」のコードの場所</span><span class="sxs-lookup"><span data-stu-id="cad3f-193">Location of “Processing Logic” code</span></span>|<span data-ttu-id="cad3f-194">-「をネットワーク上で」リーダーおよび Execute メソッドを使用してストリーム。</span><span class="sxs-lookup"><span data-stu-id="cad3f-194">-   “Wire up” readers and streams via Execute method.</span></span><br /><span data-ttu-id="cad3f-195">実際の実行は、データの読み取りと、リーダーおよびストリーム内に発生します。</span><span class="sxs-lookup"><span data-stu-id="cad3f-195">-   Actual execution occurs in the readers and streams as the data is read.</span></span>|<span data-ttu-id="cad3f-196">パイプライン コンポーネントの実行メソッドから直接。</span><span class="sxs-lookup"><span data-stu-id="cad3f-196">Directly from the Execute method of the pipeline component.</span></span>|  
|<span data-ttu-id="cad3f-197">data</span><span class="sxs-lookup"><span data-stu-id="cad3f-197">Data</span></span>|<span data-ttu-id="cad3f-198">それを介するデータが読み込まれるとは、ラッピング各層で再作成されます。</span><span class="sxs-lookup"><span data-stu-id="cad3f-198">Re-created at each wrapping layer as data is read through it.</span></span>|<span data-ttu-id="cad3f-199">読み、変更して、次のコンポーネントが呼び出される前に各コンポーネントに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="cad3f-199">Read in, modified and written out at each component prior to next component being called.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cad3f-200">参照</span><span class="sxs-lookup"><span data-stu-id="cad3f-200">See Also</span></span>  
 [<span data-ttu-id="cad3f-201">BizTalk Server アプリケーションの最適化</span><span class="sxs-lookup"><span data-stu-id="cad3f-201">Optimizing BizTalk Server Applications</span></span>](../technical-guides/optimizing-biztalk-server-applications.md)