---
title: パイプラインのパフォーマンスの最適化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b5137747-0dcf-4c96-90a7-01afb92f56a6
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34d83aad4a393df0cc0532545d5518fff9e0f8e5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291352"
---
# <a name="optimizing-pipeline-performance"></a><span data-ttu-id="193f2-102">パイプラインのパフォーマンスを最適化します。</span><span class="sxs-lookup"><span data-stu-id="193f2-102">Optimizing Pipeline Performance</span></span>
<span data-ttu-id="193f2-103">このトピックでは、パイプラインでのパフォーマンスを最適化するためのガイドラインを説明します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューション。</span><span class="sxs-lookup"><span data-stu-id="193f2-103">This topic describes guidelines for optimizing performance of pipelines in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
## <a name="best-practices-for-optimizing-performance-of-biztalk-server-pipelines"></a><span data-ttu-id="193f2-104">BizTalk Server パイプラインのパフォーマンスを最適化するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="193f2-104">Best practices for optimizing performance of BizTalk Server pipelines</span></span>  
  
1. <span data-ttu-id="193f2-105">パイプライン コンポーネントは、パフォーマンスに大きな影響を与えるため、(たとえば、パススルー パイプライン コンポーネントは XML アセンブラ/逆アセンブラ パイプライン コンポーネントをより最大 30% を実行します)、カスタム パイプライン コンポーネントが実行を確認最適に実装する前に、展開でします。</span><span class="sxs-lookup"><span data-stu-id="193f2-105">Because pipeline components have a significant impact on performance (for example, a pass-through pipeline component performs up to 30 percent better than an XML assembler/disassembler pipeline component), make sure that any custom pipeline components perform optimally before implementing them in your deployment.</span></span> <span data-ttu-id="193f2-106">BizTalk アプリケーションの全体的なパフォーマンスを最大化したい場合は、カスタム パイプラインのパイプライン コンポーネントの数を最小限に抑えます。</span><span class="sxs-lookup"><span data-stu-id="193f2-106">Minimize the number of pipeline components in your custom pipelines if you want to maximize the overall performance of your BizTalk application.</span></span>  
  
2. <span data-ttu-id="193f2-107">パフォーマンスを向上できます全体的なパイプライン コンポーネントでメッセージの永続化の頻度を減らすことで、冗長性を最小化するコンポーネントをコーディングしています。</span><span class="sxs-lookup"><span data-stu-id="193f2-107">You also can improve overall performance by reducing the message persistence frequency in your pipeline component and by coding your component to minimize redundancy.</span></span> <span data-ttu-id="193f2-108">すべてのカスタム アセンブリ具体的には、カスタムの追跡のコンポーネントと同様のパフォーマンスに悪影響を及ぼす可能性があるアーティファクト テストするくださいとは別に、システムが最大能力で作業する場合、その動作を観察して、検索の高負荷条件下で任意のボトルネックの可能性。</span><span class="sxs-lookup"><span data-stu-id="193f2-108">Every custom assembly and in particular artifacts that could potentially disrupt performance, like custom tracking components, should be tested separately under heavy load condition to observe their behavior when the system is working at full capacity and to find any possible bottlenecks.</span></span>  
  
3. <span data-ttu-id="193f2-109">パイプライン コンポーネント内で受信メッセージを確認する必要がある場合にメモリを使用してドキュメント全体を読み込みを避けるため、 **XmlDocument**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="193f2-109">If you need to read the inbound message inside a pipeline component, avoid loading the entire document into memory using an **XmlDocument** object.</span></span> <span data-ttu-id="193f2-110">インスタンスで必要な領域の量、 **XmlDocument**を読み込むし、XML ドキュメントのメモリ内表現を作成するクラスは、最大 10 倍の実際のメッセージ サイズ。</span><span class="sxs-lookup"><span data-stu-id="193f2-110">The amount of space required by an instance of the **XmlDocument** class to load and create an in-memory representation of a XML document is up to 10 times the actual message size.</span></span> <span data-ttu-id="193f2-111">メッセージを読み取るために使用する必要があります、 **XmlTextReader**オブジェクトと共に、次のクラスのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="193f2-111">In order to read a message, you should use an **XmlTextReader** object along with an instance of the following classes:</span></span>  
  
   -   <span data-ttu-id="193f2-112">**VirtualStream (Microsoft.BizTalk.Streaming.dll)** -このクラスのソース コードが次のように、パイプラインの SDK の下の 2 つの場所にあります。\Samples\pipelines\arbitraryxpathpropertyhandler および \samples\pipelines\schemaresolvercomponent\schemaresolverflatfiledasm します。</span><span class="sxs-lookup"><span data-stu-id="193f2-112">**VirtualStream (Microsoft.BizTalk.Streaming.dll)** - The source code for this class is located in two locations under the Pipelines SDK as follows: SDK\Samples\Pipelines\ArbitraryXPathPropertyHandler and SDK\Samples\Pipelines\SchemaResolverComponent\SchemaResolverFlatFileDasm.</span></span>  
  
   -   <span data-ttu-id="193f2-113">**ReadOnlySeekableStream (Microsoft.BizTalk.Streaming.dll)** します。</span><span class="sxs-lookup"><span data-stu-id="193f2-113">**ReadOnlySeekableStream (Microsoft.BizTalk.Streaming.dll)**.</span></span>  
  
   -   <span data-ttu-id="193f2-114">**SeekAbleReadOnlyStream** -このクラスのソース コードが次のように、パイプラインの SDK の下の 2 つの場所にあります。\Samples\pipelines\arbitraryxpathpropertyhandler および \samples\pipelines\schemaresolvercomponent\schemaresolverflatfiledasm します。</span><span class="sxs-lookup"><span data-stu-id="193f2-114">**SeekAbleReadOnlyStream** - The source code for this class is located in two locations under the Pipelines SDK as follows: SDK\Samples\Pipelines\ArbitraryXPathPropertyHandler and SDK\Samples\Pipelines\SchemaResolverComponent\SchemaResolverFlatFileDasm.</span></span>  
  
4. <span data-ttu-id="193f2-115">PassThruReceive パイプラインおよび可能な限り PassThruTransmit 標準パイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="193f2-115">Use the PassThruReceive and the PassThruTransmit standard pipelines whenever possible.</span></span> <span data-ttu-id="193f2-116">任意のパイプライン コンポーネントが含まれていないされ、メッセージの処理を実行しないでください。</span><span class="sxs-lookup"><span data-stu-id="193f2-116">They do not contain any pipeline component and do not perform any processing of the message.</span></span> <span data-ttu-id="193f2-117">このため、受信または送信メッセージの最大のパフォーマンスを支えます。</span><span class="sxs-lookup"><span data-stu-id="193f2-117">For this reason, they ensure maximum performance in receiving or sending messages.</span></span> <span data-ttu-id="193f2-118">バイナリ メッセージを送信する必要がある場合は、バイナリのドキュメントを BizTalk メッセージ ボックスと送信ポートで PassThruTransmit パイプラインに発行する必要がある場合は、受信場所で PassThruReceive パイプラインを使用できます。</span><span class="sxs-lookup"><span data-stu-id="193f2-118">You can use a PassThruReceive pipeline on a receive location if you need to publish a binary document to the BizTalk MessageBox and a PassThruTransmit pipeline on a send port if you need to send out a binary message.</span></span> <span data-ttu-id="193f2-119">PassThruTransmit パイプラインで、メッセージは、フォーマットされているし、送信する準備ができている場合、オーケストレーションにバインドする物理送信ポートを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="193f2-119">You can also use the PassThruTransmit pipeline on a physical send port bound to an orchestration if the message has been formatted and is ready to be transmitted.</span></span> <span data-ttu-id="193f2-120">次の操作のいずれかを実行する必要がある場合に、別のアプローチを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="193f2-120">You will need to use a different approach if you need to accomplish one of the following actions:</span></span>  
  
   - <span data-ttu-id="193f2-121">受信 XML またはフラット ファイル メッセージのコンテキストのプロパティを昇格させます。</span><span class="sxs-lookup"><span data-stu-id="193f2-121">Promote properties on the context of an inbound XML or Flat File message.</span></span>  
  
   - <span data-ttu-id="193f2-122">受信場所内でマップを適用します。</span><span class="sxs-lookup"><span data-stu-id="193f2-122">Apply a map inside a receive location.</span></span>  
  
   - <span data-ttu-id="193f2-123">メッセージにサブスクライブするオーケストレーションでマップを適用します。</span><span class="sxs-lookup"><span data-stu-id="193f2-123">Apply a map in an orchestration that subscribes to a message.</span></span>  
  
   - <span data-ttu-id="193f2-124">メッセージをサブスクライブする送信ポートでマップを適用します。</span><span class="sxs-lookup"><span data-stu-id="193f2-124">Apply a map on a send port that subscribes to a message.</span></span>  
  
     <span data-ttu-id="193f2-125">これらの操作を行うためには、プローブし受信パイプライン内のドキュメントの種類を検出し、MessageType のコンテキスト プロパティに (名前空間 #root 名の) 値を代入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="193f2-125">To accomplish one of these actions, you must probe and discover the document type inside the receive pipeline and assign the (namespace#root-name) value to the MessageType context property.</span></span> <span data-ttu-id="193f2-126">この操作は、通常、Xml 逆アセンブラー コンポーネント (XmlDasmComp) などの逆アセンブラー コンポーネントまたはフラット ファイル逆アセンブラー コンポーネント (FFDasmComp) して行います。</span><span class="sxs-lookup"><span data-stu-id="193f2-126">This operation is typically accomplished by a disassembler component such as the Xml Disassembler component (XmlDasmComp) or the Flat File disassembler component (FFDasmComp).</span></span> <span data-ttu-id="193f2-127">この場合は、標準 (たとえば、XmlReceive パイプライン) または標準またはカスタム逆アセンブラー コンポーネントを含むカスタム パイプラインを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="193f2-127">In this case, you need to use a standard (for instance, XmlReceive pipeline) or a custom pipeline that contains a standard or a custom disassembler component.</span></span>  
  
5. <span data-ttu-id="193f2-128">できる限り遅くリソースを取得し、できるだけ早期にリリースします。</span><span class="sxs-lookup"><span data-stu-id="193f2-128">Acquire resources as late as possible and release them as early as possible.</span></span> <span data-ttu-id="193f2-129">たとえば、データをデータベースにアクセスする必要がある場合は、できるだけ遅く接続を開くして、できるだけ早く閉じます。</span><span class="sxs-lookup"><span data-stu-id="193f2-129">For example, if you need to access data on a database, open the connection as late as possible and close it as soon as possible.</span></span> <span data-ttu-id="193f2-130">C# のステートメントを使用して、破棄可能なオブジェクトを暗黙的にリリースを使用して、または、オブジェクトを明示的に破棄するには、try – catch – finally ステートメントの最後にブロックします。</span><span class="sxs-lookup"><span data-stu-id="193f2-130">Use the C# using statement to implicitly release disposable objects or the finally block of a try-catch-finally statement to explicitly dispose your objects.</span></span> <span data-ttu-id="193f2-131">すると、コンポーネントをデバッグする単純なソース コードをインストルメント化します。</span><span class="sxs-lookup"><span data-stu-id="193f2-131">Instrument your source code to make your components simple to debug.</span></span>  
  
6. <span data-ttu-id="193f2-132">厳密に、メッセージの処理を高速化する必要はありませんが、パイプラインからコンポーネントを削除します。</span><span class="sxs-lookup"><span data-stu-id="193f2-132">Eliminate any components from your pipelines that are not strictly required to speed up message processing.</span></span>  
  
7. <span data-ttu-id="193f2-133">受信パイプラインでは、内部で (オーケストレーション、送信ポート) のメッセージのルーティング、メッセージ コンテキスト プロパティ (送信ポート) の下位変換の必要な場合にのみメッセージ コンテキストに項目を昇格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="193f2-133">Inside a receive pipeline, you should promote items to the message context only if you need them for message routing (Orchestrations, Send Ports) or demotion of message context properties (Send Ports).</span></span>  
  
8. <span data-ttu-id="193f2-134">メッセージを表示してメタデータを含める必要があると、ルーティングまたは降格のための使用をメタデータを使用しない場合、 **IBaseMessageContext.Write**メソッドの代わりに、 **IBaseMessageContext.Promote**メソッド。</span><span class="sxs-lookup"><span data-stu-id="193f2-134">If you need to include metadata with a message, and you don't use the metadata for routing or demotion purposes, use the **IBaseMessageContext.Write** method instead of the **IBaseMessageContext.Promote** method.</span></span>  
  
9. <span data-ttu-id="193f2-135">XPath 式を使用してメッセージから情報を抽出する必要がある場合にメモリを使用してドキュメント全体を読み込みを避けるため、 **XmlDocument**のみを使用するオブジェクト、 **SelectNodes**または**SelectSingleNode**メソッド。</span><span class="sxs-lookup"><span data-stu-id="193f2-135">If you need to extract information from a message using an XPath expression, avoid loading the entire document into memory using an **XmlDocument** object just to use the **SelectNodes** or **SelectSingleNode** methods.</span></span> <span data-ttu-id="193f2-136">説明する手法を使用して、または、[ストリーミングでのメモリ使用量の最適化](../technical-guides/optimizing-memory-usage-with-streaming.md)します。</span><span class="sxs-lookup"><span data-stu-id="193f2-136">Alternatively, use the techniques described in [Optimizing Memory Usage with Streaming](../technical-guides/optimizing-memory-usage-with-streaming.md).</span></span>  
  
## <a name="use-streaming-to-minimize-the-memory-footprint-required-when-loading-messages-in-pipelines"></a><span data-ttu-id="193f2-137">ストリーミングを使ってパイプラインでメッセージを読み込むときに必要なメモリのフット プリントを最小限にするには</span><span class="sxs-lookup"><span data-stu-id="193f2-137">Use streaming to minimize the memory footprint required when loading messages in pipelines</span></span>  
 <span data-ttu-id="193f2-138">次の手法では、パイプラインにメッセージを読み込む場合は、メッセージのメモリ使用量を最小限に抑える方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="193f2-138">The following techniques describe how to minimize the memory footprint of a message when loading the message into a pipeline.</span></span>  
  
### <a name="use-readonlyseekablestream-and-virtualstream-to-process-a-message-from-a-pipeline-component"></a><span data-ttu-id="193f2-139">ReadOnlySeekableStream と VirtualStream を使用して、パイプライン コンポーネントからのメッセージを処理するには</span><span class="sxs-lookup"><span data-stu-id="193f2-139">Use ReadOnlySeekableStream and VirtualStream to process a message from a pipeline component</span></span>  
 <span data-ttu-id="193f2-140">パイプライン コンポーネントの内部でメモリへのメッセージ全体の読み込みを回避するために、ベスト プラクティスと見なされます。</span><span class="sxs-lookup"><span data-stu-id="193f2-140">It is considered a best practice to avoid loading the entire message into memory inside pipeline components.</span></span> <span data-ttu-id="193f2-141">お勧めの方法は、カスタム ストリームの実装では、使用し、要求が行われた読み取りとして、受信ストリームをラップする、カスタム ストリームの実装は、基になる、ラップされたストリームを読み取り、(純粋なストリーミング方法) で読み取られると、データを処理します。</span><span class="sxs-lookup"><span data-stu-id="193f2-141">A preferable approach is to wrap the inbound stream with a custom stream implementation, and then as read requests are made, the custom stream implementation reads the underlying, wrapped stream and processes the data as it is read (in a pure streaming manner).</span></span> <span data-ttu-id="193f2-142">これは、実装が非常に困難にすることができ、可能であれば、に応じて、ストリームを使用して行うに必要なことができない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="193f2-142">This can be very hard to implement and may not be possible, depending on what needs to be done with the stream.</span></span> <span data-ttu-id="193f2-143">ここでは、使用して、 **ReadOnlySeekableStream**と**VirtualStream** Microsoft.BizTalk.Streaming.dll によって公開されるクラス。</span><span class="sxs-lookup"><span data-stu-id="193f2-143">In this case, use the **ReadOnlySeekableStream** and **VirtualStream** classes exposed by the Microsoft.BizTalk.Streaming.dll.</span></span> <span data-ttu-id="193f2-144">これらの実装でも提供[任意の XPath プロパティ ハンドラ (BizTalk Server サンプル)](http://go.microsoft.com/fwlink/?LinkId=160069) (http://go.microsoft.com/fwlink/?LinkId=160069) BizTalk SDK に含まれています **。ReadOnlySeekableStream**により、カーソルは、ストリームの先頭に移動できます。</span><span class="sxs-lookup"><span data-stu-id="193f2-144">An implementation of these is also provided in [Arbitrary XPath Property Handler (BizTalk Server Sample)](http://go.microsoft.com/fwlink/?LinkId=160069) (http://go.microsoft.com/fwlink/?LinkId=160069) in the BizTalk SDK.**ReadOnlySeekableStream** ensures that the cursor can be repositioned to the beginning of the stream.</span></span> <span data-ttu-id="193f2-145">**VirtualStream**サイズが指定のしきい値を超えていない限り、MemoryStream を内部で、使用する場合、ストリーム、ファイル システムに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="193f2-145">The **VirtualStream** will use a MemoryStream internally, unless the size is over a specified threshold, in which case it will write the stream to the file system.</span></span> <span data-ttu-id="193f2-146">これら 2 つのストリームを組み合わせての使用 (を使用して**VirtualStream**の永続的なストレージとして、 **ReadOnlySeekableStream**)"seekability"と「オーバーフロー ファイル システムに」機能の両方を提供します。</span><span class="sxs-lookup"><span data-stu-id="193f2-146">Use of these two streams in combination (using **VirtualStream** as persistent storage for the **ReadOnlySeekableStream**) provides both “seekability” and “overflow to file system” capabilities.</span></span> <span data-ttu-id="193f2-147">これには、メッセージ全体をメモリに読み込むことがなくサイズの大きいメッセージの処理が対応しています。</span><span class="sxs-lookup"><span data-stu-id="193f2-147">This accommodates the processing of large messages without loading the entire message into memory.</span></span> <span data-ttu-id="193f2-148">次のコードは、この機能を実装するパイプライン コンポーネントで使用可能性があります。</span><span class="sxs-lookup"><span data-stu-id="193f2-148">The following code could be used in a pipeline component to implement this functionality.</span></span>  
  
```  
int bufferSize = 0x280;  
int thresholdSize = 0x100000;  
Stream vStream = new VirtualStream(bufferSize, thresholdSize);  
Stream seekStream = new ReadOnlySeekableStream(inboundStream, vStream, bufferSize);  
```  
  
 <span data-ttu-id="193f2-149">このコードは、bufferSize を公開することで「オーバーフローしきい値」を提供し、各 thresholdSize 変数は、受信場所または送信ポートの構成。</span><span class="sxs-lookup"><span data-stu-id="193f2-149">This code provides an “overflow threshold” by exposing bufferSize and thresholdSize variables on each receive location or send port configuration.</span></span> <span data-ttu-id="193f2-150">開発者や管理者のさまざまなメッセージの種類と (32 ビットとなどのさまざまな構成によって、このオーバーフローしきい値を調整し、ことができます。64 ビット)。</span><span class="sxs-lookup"><span data-stu-id="193f2-150">This overflow threshold can then be adjusted by developers or administrators for different message types and different configurations (such as 32-bit vs. 64-bit).</span></span>  
  
### <a name="using-xpathreader-and-xpathcollection-to-extract-a-given-ibasemessage-object-from-within-a-custom-pipeline-component"></a><span data-ttu-id="193f2-151">XPathReader と XPathCollection を使用して、カスタム パイプライン コンポーネント内から指定した IBaseMessage オブジェクトを抽出します。</span><span class="sxs-lookup"><span data-stu-id="193f2-151">Using XPathReader and XPathCollection to extract a given IBaseMessage object from within a custom pipeline component.</span></span>  
 <span data-ttu-id="193f2-152">特定の値を使用する代わりに、XML ドキュメントからプルする必要がある場合、 **SelectNodes**と**SelectSingleNode** XPathReader クラスのインスタンスを使用して、XmlDocument クラスによって公開されるメソッド次のコード例に示すように、Microsoft.BizTalk.XPathReader.dll アセンブリによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="193f2-152">If specific values need to be pulled from an XML document, instead of using the **SelectNodes** and **SelectSingleNode** methods exposed by the XmlDocument class, use an instance of the XPathReader class provided by the Microsoft.BizTalk.XPathReader.dll assembly as illustrated in the following code example.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="193f2-153">XPathReader を使用してより優れたパフォーマンスを提供 SelectNodes または SelectSingleNode で XmlDocument を使用する可能性がありますが、XPathReader では、アプリケーションのフラットなメモリのプロファイルを保持できます。 特に、小さいメッセージ。</span><span class="sxs-lookup"><span data-stu-id="193f2-153">For smaller messages especially, using an XmlDocument with SelectNodes or SelectSingleNode may provide better performance than using XPathReader, but XPathReader allows you to keep a flat memory profile for your application.</span></span>  
  
 <span data-ttu-id="193f2-154">XPathReader と XPathCollection を使用して、抽出する方法を示します、指定された**IBaseMessage**からカスタム パイプライン コンポーネント内のオブジェクトします。</span><span class="sxs-lookup"><span data-stu-id="193f2-154">This example shows how to use the XPathReader and XPathCollection to extract a given **IBaseMessage** object from within a custom pipeline component.</span></span>  
  
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
  
## <a name="use-xmlreader-and-xmlwriter-with-xmltranslatorstream-to-process-a-message-from-a-pipeline-component"></a><span data-ttu-id="193f2-155">パイプライン コンポーネントからのメッセージを処理する XMLTranslatorStream と XMLReader および XMLWriter を使用して、</span><span class="sxs-lookup"><span data-stu-id="193f2-155">Use XMLReader and XMLWriter with XMLTranslatorStream to process a message from a pipeline component</span></span>  
 <span data-ttu-id="193f2-156">ストリーミングの手法を使用するカスタム パイプライン コンポーネントを実装するためのもう 1 つのメソッドは、.NET を使用する**XmlReader**と**XmlWriter**クラスと組み合わせて、 **XmlTranslatorStream** BizTalk Server によって提供されるクラス。</span><span class="sxs-lookup"><span data-stu-id="193f2-156">Another method for implementing a custom pipeline component which uses a streaming approach is to use the .NET **XmlReader** and **XmlWriter** classes in conjunction with the **XmlTranslatorStream** class provided by BizTalk Server.</span></span> <span data-ttu-id="193f2-157">たとえば、 **NamespaceTranslatorStream** Microsoft.BizTalk.Pipeline.Components アセンブリに含まれるクラスから継承**XmlTranslatorStream**古い名前空間を置換するために使用できますストリームに含まれる XML ドキュメントに新しいものです。</span><span class="sxs-lookup"><span data-stu-id="193f2-157">For example, the **NamespaceTranslatorStream** class contained in the Microsoft.BizTalk.Pipeline.Components assembly inherits from **XmlTranslatorStream** and can be used to replace an old namespace with a new one in the XML document contained in the stream.</span></span> <span data-ttu-id="193f2-158">新しいインスタンスをメッセージのボディ パーツの元のデータ ストリームをラップするカスタム パイプライン コンポーネント内でこの機能を使用するには、 **NamespaceTranslatorStream**クラスし、後者を返します。</span><span class="sxs-lookup"><span data-stu-id="193f2-158">In order to use this functionality inside a custom a pipeline component, you can wrap the original data stream of the message body part with a new instance of the **NamespaceTranslatorStream** class and return the latter.</span></span> <span data-ttu-id="193f2-159">この方法で、受信メッセージがない読み取り、処理ではなく、パイプライン コンポーネントでは、内部ストリームが同じパイプラインに後続のコンポーネントによって読み取られたか、ドキュメントを BizTalk Server に発行する前に、メッセージ エージェントによって最後に使用された場合にのみメッセージ ボックス。</span><span class="sxs-lookup"><span data-stu-id="193f2-159">In this way the inbound message is not read or processed inside the pipeline component, but only when the stream is read by a subsequent component in the same pipeline or is finally consumed by the Message Agent before publishing the document to the BizTalk Server MessageBox.</span></span>  
  
 <span data-ttu-id="193f2-160">次の例では、この機能を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="193f2-160">The following example illustrates how to use this functionality.</span></span>  
  
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
  
## <a name="using-resourcetracker-in-custom-pipeline-components"></a><span data-ttu-id="193f2-161">カスタム パイプライン コンポーネントで ResourceTracker を使用します。</span><span class="sxs-lookup"><span data-stu-id="193f2-161">Using ResourceTracker in Custom Pipeline Components</span></span>  
 <span data-ttu-id="193f2-162">パイプライン コンポーネントは、作成オブジェクトの有効期間を管理して、これらのオブジェクトが不要とすぐに、ガベージ コレクションを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="193f2-162">A pipeline component should manage the lifetime of the objects it creates and perform garbage collection as soon as these objects are no longer required.</span></span>  <span data-ttu-id="193f2-163">場合は、パイプライン コンポーネントには、このようなオブジェクトをパイプラインのコンテキストから、パイプラインをフェッチがリソースの追跡ツールに追加する必要がありますし、最後のパイプラインの実行が終わるまでオブジェクトの有効期間が希望しています。</span><span class="sxs-lookup"><span data-stu-id="193f2-163">If the pipeline component wants the lifetime of the objects to last until the end of pipeline execution, then you must add such objects to the resource tracker that your pipeline may fetch from the pipeline context.</span></span>  
  
 <span data-ttu-id="193f2-164">リソースの追跡ツールは、次の種類のオブジェクトに使用されます。</span><span class="sxs-lookup"><span data-stu-id="193f2-164">The resource tracker is used for the following types of objects:</span></span>  
  
- <span data-ttu-id="193f2-165">Stream オブジェクト</span><span class="sxs-lookup"><span data-stu-id="193f2-165">Stream objects</span></span>  
  
- <span data-ttu-id="193f2-166">COM オブジェクト</span><span class="sxs-lookup"><span data-stu-id="193f2-166">COM objects</span></span>  
  
- <span data-ttu-id="193f2-167">IDisposable オブジェクト</span><span class="sxs-lookup"><span data-stu-id="193f2-167">IDisposable objects</span></span>  
  
  <span data-ttu-id="193f2-168">メッセージ エンジンによりが成功または失敗したかどうかに関係なく、パイプラインは完全に実行した後、適切なタイミングでリソースの追跡ツールに追加されるすべてのネイティブ リソースが解放されるようになります。</span><span class="sxs-lookup"><span data-stu-id="193f2-168">The message engine ensures that all the native resources that are added to the resource tracker are released at an appropriate time, that is after the pipeline is completely executed, regardless of whether it was successful or failed.</span></span> <span data-ttu-id="193f2-169">リソースの追跡ツールのインスタンスとそれを追跡しているオブジェクトの有効期間は、パイプラインのコンテキスト オブジェクトによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="193f2-169">The lifetime of the Resource Tracker instance and the objects that it is tracking is managed by the pipeline context object.</span></span> <span data-ttu-id="193f2-170">IPipelineContext インターフェイスを実装するオブジェクトをパイプライン コンポーネントのすべての種類に利用可能になってパイプライン コンテキスト。</span><span class="sxs-lookup"><span data-stu-id="193f2-170">The pipeline context is made available to all types of pipeline components through an object that implements the IPipelineContext interface.</span></span>  
  
  <span data-ttu-id="193f2-171">たとえば、次のコード スニペットは、カスタム パイプライン コンポーネントで ResourceTracker プロパティを使用する方法を示すサンプルです。</span><span class="sxs-lookup"><span data-stu-id="193f2-171">For example, the following code snippet is a sample that illustrates how to use ResourceTracker property in custom pipeline components.</span></span> <span data-ttu-id="193f2-172">コード スニペットを ResourceTracker プロパティを使用するには、次のパラメーターを使用して`IPipelineContext.ResourceTracker.AddResource`します。</span><span class="sxs-lookup"><span data-stu-id="193f2-172">To use ResourceTracker property, the code snippet uses the following parameter `IPipelineContext.ResourceTracker.AddResource`.</span></span> <span data-ttu-id="193f2-173">このパラメーターには。</span><span class="sxs-lookup"><span data-stu-id="193f2-173">In this parameter:</span></span>  
  
- <span data-ttu-id="193f2-174">IPipelineContext インターフェイスは、すべてのドキュメント処理に固有のインターフェイスへのアクセスに使用するメソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="193f2-174">IPipelineContext interface defines the methods used to access all document processing-specific interfaces.</span></span>  
  
- <span data-ttu-id="193f2-175">ResourceTracker プロパティは、IPipelineContext を参照し、パイプライン処理の最後に明示的に破棄されたオブジェクトを追跡するために使用します。</span><span class="sxs-lookup"><span data-stu-id="193f2-175">ResourceTracker property references IPipelineContext and is used to keep track of objects that will be explicitly disposed at the end of pipeline processing.</span></span>  
  
- <span data-ttu-id="193f2-176">ResourceTracker.AddResource メソッドが COM オブジェクト、破棄可能なオブジェクトおよびストリームを追跡するために使用し、明示的に閉じる (ストリーム)、(IDisposable オブジェクト) を破棄またはこれら (COM オブジェクト) のリリースにカスタム パイプライン コンポーネント内で常に使用します。BizTalk メッセージ ボックスに、メッセージが発行されると、リソースの種類。</span><span class="sxs-lookup"><span data-stu-id="193f2-176">ResourceTracker.AddResource method is used to keep track of COM objects, Disposable objects and Streams, and should always be used inside a custom pipeline component to explicitly close (streams), dispose (IDisposable objects) or release (COM objects) these types of resources when a message is published to the BizTalk MessageBox.</span></span>  
  
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
  
## <a name="comparison-of-loading-messages-into-pipelines-using-an-in-memory-approach-and-using-a-streaming-approach"></a><span data-ttu-id="193f2-177">読み込みメッセージをメモリ内のアプローチを使用して、ストリーミングのアプローチを使用して、パイプラインの比較</span><span class="sxs-lookup"><span data-stu-id="193f2-177">Comparison of loading messages into pipelines using an in-memory approach and using a streaming approach</span></span>  
 <span data-ttu-id="193f2-178">次の情報が Nic Barden のブログから引用したもの[ http://blogs.objectsharp.com/cs/blogs/nbarden/archive/2008/04/14/developing-streaming-pipeline-components-part-1.aspx ](http://go.microsoft.com/fwlink/?LinkId=160228) (http://go.microsoft.com/fwlink/?LinkId=160228)します。</span><span class="sxs-lookup"><span data-stu-id="193f2-178">The following information was taken from Nic Barden’s blog, [http://blogs.objectsharp.com/cs/blogs/nbarden/archive/2008/04/14/developing-streaming-pipeline-components-part-1.aspx](http://go.microsoft.com/fwlink/?LinkId=160228) (http://go.microsoft.com/fwlink/?LinkId=160228).</span></span> <span data-ttu-id="193f2-179">このテーブルは、メモリ内のアプローチを使用して、ストリーミングのアプローチを使用してパイプラインに読み込みメッセージの集計の比較を提供します。</span><span class="sxs-lookup"><span data-stu-id="193f2-179">This table provides a summarized comparison of loading messages into pipelines using an in-memory approach and using a streaming approach.</span></span>  
  
|<span data-ttu-id="193f2-180">比較しています.</span><span class="sxs-lookup"><span data-stu-id="193f2-180">Comparison of...</span></span>|<span data-ttu-id="193f2-181">ストリーミング</span><span class="sxs-lookup"><span data-stu-id="193f2-181">Streaming</span></span>|<span data-ttu-id="193f2-182">メモリ内</span><span class="sxs-lookup"><span data-stu-id="193f2-182">In memory</span></span>|  
|----------------------|---------------|---------------|  
|<span data-ttu-id="193f2-183">メッセージごとのメモリ使用量</span><span class="sxs-lookup"><span data-stu-id="193f2-183">Memory usage per message</span></span>|<span data-ttu-id="193f2-184">メッセージのサイズに関係なく、低</span><span class="sxs-lookup"><span data-stu-id="193f2-184">Low, regardless of message size</span></span>|<span data-ttu-id="193f2-185">高 (メッセージ サイズによって異なります)</span><span class="sxs-lookup"><span data-stu-id="193f2-185">High (varies depending on message size)</span></span>|  
|<span data-ttu-id="193f2-186">XML データの処理に使用される一般的なクラス</span><span class="sxs-lookup"><span data-stu-id="193f2-186">Common classes used to process XML data</span></span>|<span data-ttu-id="193f2-187">ビルドとカスタムの派生の。</span><span class="sxs-lookup"><span data-stu-id="193f2-187">Built in and custom derivations of:</span></span><br /><br /> <span data-ttu-id="193f2-188">XmlTranslatorStream、XmlReader および XmlWriter</span><span class="sxs-lookup"><span data-stu-id="193f2-188">XmlTranslatorStream, XmlReader and XmlWriter</span></span>|<span data-ttu-id="193f2-189">XmlDocument、XPathDocument、MemoryStream および VirtualStream</span><span class="sxs-lookup"><span data-stu-id="193f2-189">XmlDocument, XPathDocument, MemoryStream and VirtualStream</span></span>|  
|<span data-ttu-id="193f2-190">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="193f2-190">Documentation</span></span>|<span data-ttu-id="193f2-191">役に立たなかった – 多くのサポートされていないと文書化されていない BizTalk クラス</span><span class="sxs-lookup"><span data-stu-id="193f2-191">Poor – many un-supported and un-documented BizTalk classes</span></span>|<span data-ttu-id="193f2-192">非常に良好な - .NET Framework クラス</span><span class="sxs-lookup"><span data-stu-id="193f2-192">Very good - .NET Framework classes</span></span>|  
|<span data-ttu-id="193f2-193">「ロジックを処理する」コードの場所</span><span class="sxs-lookup"><span data-stu-id="193f2-193">Location of “Processing Logic” code</span></span>|<span data-ttu-id="193f2-194">-「結び付ける」リーダーおよび Execute メソッドを使用してストリームします。</span><span class="sxs-lookup"><span data-stu-id="193f2-194">-   “Wire up” readers and streams via Execute method.</span></span><br /><span data-ttu-id="193f2-195">のデータの読み取りとは、リーダーおよびストリーム内実際の実行に発生します。</span><span class="sxs-lookup"><span data-stu-id="193f2-195">-   Actual execution occurs in the readers and streams as the data is read.</span></span>|<span data-ttu-id="193f2-196">パイプライン コンポーネントの Execute メソッドから直接。</span><span class="sxs-lookup"><span data-stu-id="193f2-196">Directly from the Execute method of the pipeline component.</span></span>|  
|<span data-ttu-id="193f2-197">data</span><span class="sxs-lookup"><span data-stu-id="193f2-197">Data</span></span>|<span data-ttu-id="193f2-198">説明データを読むには、ラッピング各層で再作成されます。</span><span class="sxs-lookup"><span data-stu-id="193f2-198">Re-created at each wrapping layer as data is read through it.</span></span>|<span data-ttu-id="193f2-199">変更し、次のコンポーネントが呼び出される前に各コンポーネントに書き出さの読み取り。</span><span class="sxs-lookup"><span data-stu-id="193f2-199">Read in, modified and written out at each component prior to next component being called.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="193f2-200">参照</span><span class="sxs-lookup"><span data-stu-id="193f2-200">See Also</span></span>  
 [<span data-ttu-id="193f2-201">BizTalk Server アプリケーションの最適化</span><span class="sxs-lookup"><span data-stu-id="193f2-201">Optimizing BizTalk Server Applications</span></span>](../technical-guides/optimizing-biztalk-server-applications.md)