---
title: パイプラインを実行する式を使用する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ExecuteReceivePipeline() method
- pipelines, schema resolution
- ExecuteSendPipeline() method
- SendPipelineInputMessages class
- pipelines, restrictions
- pipelines, errors
- XLANGPipelineManager class
- receive pipelines, orchestrations
- ReceivePipelineOutputMessages class
- orchestrations, pipelines
- pipelines, component types
- send pipelines, orchestrations
- pipelines, states
- pipelines, executing
- Microsoft.XLANGs.Pipeline namespace
- pipelines, transactional
- pipelines, orchestrations
- Message Assignment shape [Orchestration Designer], pipelines
ms.assetid: f947fa73-526c-4747-8de7-df557a93056c
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d2da3d12ac8df31fc8f63db69b4611b58c58df6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383370"
---
# <a name="how-to-use-expressions-to-execute-pipelines"></a><span data-ttu-id="3f396-102">パイプラインを実行する式を使用する方法</span><span class="sxs-lookup"><span data-stu-id="3f396-102">How to Use Expressions to Execute Pipelines</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="3f396-103">オーケストレーションからパイプラインを同期的に呼び出す機能があります。</span><span class="sxs-lookup"><span data-stu-id="3f396-103">has the ability to synchronously call a pipeline from within an Orchestration.</span></span> <span data-ttu-id="3f396-104">これにより、パイプライン内でカプセル化されたメッセージの処理を活用するためのオーケストレーション (送信または受信) に対して、メッセージング インフラストラクチャを介してそのデータを送信することがなくデータの本体。</span><span class="sxs-lookup"><span data-stu-id="3f396-104">This enables orchestrations to leverage the message processing encapsulated within a pipeline (either send or receive) against a body of data without having to send that data through the messaging infrastructure.</span></span>  
  
 <span data-ttu-id="3f396-105">1 つの送信インターチェンジに複数のメッセージを集約するために、送信パイプラインを呼び出すオーケストレーションを有効にするのには、この機能を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="3f396-105">You can use this feature to enable an orchestration to call a send pipeline in order to aggregate several messages into a single outgoing interchange.</span></span> <span data-ttu-id="3f396-106">逆に、オーケストレーションでは、デコードおよびメッセージ ボックスを通過の処理コストを発生させずに、メッセージング インフラストラクチャの外部で取得されたインターチェンジを逆アセンブルするには、受信パイプラインを呼び出す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3f396-106">Conversely, an orchestration could call a receive pipeline to decode and disassemble an interchange obtained outside of the messaging infrastructure, without incurring the processing costs of going through the message box.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3f396-107">詳細</span><span class="sxs-lookup"><span data-stu-id="3f396-107">Details</span></span>  
 <span data-ttu-id="3f396-108">オーケストレーション内のメソッドを使用して、 **XLANGPipelineManager**クラス (で、 **Microsoft.XLANGs.Pipeline**名前空間) を呼び出す送信または受信パイプライン。</span><span class="sxs-lookup"><span data-stu-id="3f396-108">Orchestrations use methods in the **XLANGPipelineManager** class (in the **Microsoft.XLANGs.Pipeline** namespace) to call send or receive pipelines.</span></span>  <span data-ttu-id="3f396-109">受信パイプラインは、1 つのメッセージまたはインターチェンジのいずれかを使用して、パイプラインが受信 BizTalk メッセージ内のメッセージのコンテキストで実行される場合と同様、0 個以上のメッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="3f396-109">A Receive pipeline consumes either a single message or an interchange and yields zero or more messages, just as when the pipeline executes in the context of receiving a message within BizTalk messaging.</span></span> <span data-ttu-id="3f396-110">送信パイプラインでは、1 つまたは複数のメッセージを使用をパイプラインが BizTalk メッセージのメッセージ送信のコンテキストで実行される場合と同様、ここでも、1 つのメッセージまたはインターチェンジを生成します。</span><span class="sxs-lookup"><span data-stu-id="3f396-110">A Send pipeline consumes one or more messages and yields a single message or interchange, again, just as when the pipeline executes in the context of sending a message within BizTalk messaging.</span></span>  
  
## <a name="calling-a-receive-pipeline"></a><span data-ttu-id="3f396-111">受信パイプラインの呼び出し</span><span class="sxs-lookup"><span data-stu-id="3f396-111">Calling a Receive Pipeline</span></span>  
 <span data-ttu-id="3f396-112">アプリケーションがオーケストレーションから受信パイプラインを呼び出すために、 **ExecuteReceivePipeline()** のメソッド、 **XLANGPipelineManager**クラス。</span><span class="sxs-lookup"><span data-stu-id="3f396-112">In order to call a receive pipeline from within an orchestration, the application calls the **ExecuteReceivePipeline()** method of the **XLANGPipelineManager** class.</span></span>  <span data-ttu-id="3f396-113">このメソッドは、1 つのインターチェンジを使用し、0 個以上のメッセージのコレクションを返します (のインスタンスに含まれている、 **ReceivePipelineOutputMessages**クラス)。</span><span class="sxs-lookup"><span data-stu-id="3f396-113">This method consumes a single interchange and returns a collection of zero or more messages (contained in an instance of the **ReceivePipelineOutputMessages** class).</span></span> <span data-ttu-id="3f396-114">このメソッドの構文の .NET クラス ライブラリの参照の詳細については、 **XLANGPipelineManager**クラス。</span><span class="sxs-lookup"><span data-stu-id="3f396-114">The syntax of this method is detailed in the .NET class library reference for the **XLANGPipelineManager** class.</span></span>  
  
 <span data-ttu-id="3f396-115">オーケストレーションから受信パイプラインを実行するための API です。</span><span class="sxs-lookup"><span data-stu-id="3f396-115">The API for executing a receive pipeline from within an orchestration is:</span></span>  
  
 `// Execute receive pipeline`  
  
 `static public ReceivePipelineOutputMessages ExecuteReceivePipeline(System.Type receivePipelineType, XLANGMessage msg);`  
  
 <span data-ttu-id="3f396-116">受信パイプラインへの呼び出しを行うことが通常、**式**オーケストレーション内の図形。</span><span class="sxs-lookup"><span data-stu-id="3f396-116">A call to a receive pipeline would typically be done in an **Expression** shape within the orchestration.</span></span>  
  
 <span data-ttu-id="3f396-117">オーケストレーションから受信パイプラインを呼び出すために、開発者は、オーケストレーション プロジェクトでパイプライン アセンブリを参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f396-117">In order to call a receive pipeline from within an orchestration, the developer must reference the pipeline assembly in the orchestration project.</span></span> <span data-ttu-id="3f396-118">受信パイプラインを呼び出すオーケストレーションの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3f396-118">Following is an example of an orchestration that calls a receive pipeline:</span></span>  
  
 <span data-ttu-id="3f396-119">![受信パイプラインの呼び出し画面](../core/media/callingreceivepipelinefromorchestration.gif "CallingReceivePipelineFromOrchestration")</span><span class="sxs-lookup"><span data-stu-id="3f396-119">![Calling Receive Pipeline screen](../core/media/callingreceivepipelinefromorchestration.gif "CallingReceivePipelineFromOrchestration")</span></span>  
  
 <span data-ttu-id="3f396-120">詳細な例は、SDK サンプルを参照してください。[で構成されるメッセージ プロセッサ (BizTalk Server サンプル)](../core/composed-message-processor-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="3f396-120">For a more detailed example, see the SDK sample [Composed Message Processor (BizTalk Server Sample)](../core/composed-message-processor-biztalk-server-sample.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3f396-121">型の変数**ReceivePipelineOutputMessages**オーケストレーションのアトミックのスコープ内でのみ宣言できます。</span><span class="sxs-lookup"><span data-stu-id="3f396-121">A variable of type **ReceivePipelineOutputMessages** can be declared only within an atomic scope in an orchestration.</span></span>  <span data-ttu-id="3f396-122">これは、この型の変数がシリアル化できないし、したがって、オーケストレーションの永続性は失わオーケストレーションがアトミックのスコープ内で実行中に永続化しないためです。</span><span class="sxs-lookup"><span data-stu-id="3f396-122">This is because variables of this type are not serializable and thus would not survive persistence of the orchestration, and orchestrations are never persisted while executing within an atomic scope.</span></span>  <span data-ttu-id="3f396-123">つまり、受信パイプラインは、アトミックのスコープ内でのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="3f396-123">This means that a receive pipeline can be executed only within an atomic scope.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3f396-124">呼び出すときに**PassThruReceive**パイプラインまたはオーケストレーション内からカスタム パイプライン コンポーネントでは、受信メッセージの種類に関係なく System.Xml.XmlDocument が XML か、受信メッセージの変数の型を宣言する必要があります.</span><span class="sxs-lookup"><span data-stu-id="3f396-124">When calling **PassThruReceive** pipeline or custom pipeline component from within an orchestration, you must declare the variable type for incoming message as System.Xml.XmlDocument despite of the incoming message type is XML or not.</span></span> <span data-ttu-id="3f396-125">そのため場合は、受信メッセージがフラット ファイル形式のメッセージなどの XML 以外のメッセージ処理をしようとすると例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3f396-125">Therefore, you may encounter exception if you try to operate on it if the incoming message is a non-XML message such as a flat file format message.</span></span> <span data-ttu-id="3f396-126">これは、そのため、オーケストレーション エンジンが上記のシナリオでは受信メッセージの任意の型に System.Xml.XmlDocument を使用する予定です。</span><span class="sxs-lookup"><span data-stu-id="3f396-126">This is because of that orchestration engine intends to use System.Xml.XmlDocument for any type of incoming message in the scenario described above.</span></span>  
  
## <a name="calling-a-send-pipeline"></a><span data-ttu-id="3f396-127">送信パイプラインの呼び出し</span><span class="sxs-lookup"><span data-stu-id="3f396-127">Calling a Send Pipeline</span></span>  
 <span data-ttu-id="3f396-128">アプリケーションがオーケストレーションから送信パイプラインを呼び出す、 **ExecuteSendPipeline()** のメソッド、 **XLANGPipelineManager**クラス。</span><span class="sxs-lookup"><span data-stu-id="3f396-128">To call a send pipeline from within an orchestration, the application calls the **ExecuteSendPipeline()** method of the **XLANGPipelineManager** class.</span></span> <span data-ttu-id="3f396-129">このメソッドは 1 つまたは複数のメッセージのコレクション (のインスタンスに含まれている、 **SendPipelineInputMessages**クラス) を 1 つのインターチェンジを返します。</span><span class="sxs-lookup"><span data-stu-id="3f396-129">This method consumes a collection of one or more messages (contained in an instance of the **SendPipelineInputMessages** class) and returns a single interchange.</span></span> <span data-ttu-id="3f396-130">このメソッドの構文の .NET クラス ライブラリの参照の詳細については、 **XLANGPipelineManager**クラス。</span><span class="sxs-lookup"><span data-stu-id="3f396-130">The syntax of this method is detailed in the .NET class library reference for the **XLANGPipelineManager** class.</span></span>  <span data-ttu-id="3f396-131">送信パイプラインの実行を呼び出し、新しいインターチェンジを生成するため、 **ExecuteSendPipeline()** メソッドは、そのメッセージの割り当て図形内で行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f396-131">Because execution of a send pipeline yields a new interchange, the call to **ExecuteSendPipeline()** method must be made within a message assignment shape, as such:</span></span>  
  
 <span data-ttu-id="3f396-132">オーケストレーションから送信パイプラインを実行するための API です。</span><span class="sxs-lookup"><span data-stu-id="3f396-132">The API for executing a send pipeline from within an orchestration is:</span></span>  
  
 `// Execute a send pipeline`  
  
 `static public ExecuteSendPipeline(System.Type sendPipelineType, SendPipelineInputMessages inputMsgs, XLANGMessage msg);`  
  
 <span data-ttu-id="3f396-133">送信パイプラインの呼び出しを行う必要がある、**メッセージの割り当て**オーケストレーション内の図形。</span><span class="sxs-lookup"><span data-stu-id="3f396-133">A call to a send pipeline must be done in a **Message Assignment** shape within the orchestration.</span></span>  
  
 <span data-ttu-id="3f396-134">オーケストレーションから送信パイプラインを呼び出すために、開発者は、オーケストレーション プロジェクトでパイプライン アセンブリを参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f396-134">In order to call a send pipeline from within an orchestration, the developer must reference the pipeline assembly in the orchestration project.</span></span>  <span data-ttu-id="3f396-135">送信パイプラインを呼び出すオーケストレーションの例:</span><span class="sxs-lookup"><span data-stu-id="3f396-135">An example of an orchestration that calls a send pipeline:</span></span>  
  
 <span data-ttu-id="3f396-136">![送信パイプラインの呼び出し画面](../core/media/example-callingsendpipelinefromorchestration.gif "Example_CallingSendPipelineFromOrchestration")</span><span class="sxs-lookup"><span data-stu-id="3f396-136">![Calling Send Pipeline screen](../core/media/example-callingsendpipelinefromorchestration.gif "Example_CallingSendPipelineFromOrchestration")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3f396-137">既定の XMLTransmit パイプラインを呼び出すときに、メッセージ コンテキスト プロパティ XMLNORM を設定する必要があります。EnvelopeSpecName エンベロープ スキーマの完全修飾名にします。</span><span class="sxs-lookup"><span data-stu-id="3f396-137">When calling the default XMLTransmit pipeline, you must set the message context property XMLNORM.EnvelopeSpecName to the fully qualified name of the Envelope schema.</span></span> <span data-ttu-id="3f396-138">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3f396-138">For example:</span></span>  
>   
>  `MyMessage(XMLNORM.EnvelopeSpecName) = "PipelineSchemas.POEnv, PipelineSchemas, Version=1.0.0.0, Culture=nuetral, PublicKeyToken=12e5cc95621c33e8";`  
  
 <span data-ttu-id="3f396-139">詳細な例は、SDK サンプルを参照してください。[アグリゲーター (BizTalk Server サンプル)](../core/aggregator-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="3f396-139">For a more detailed example, see the SDK sample [Aggregator (BizTalk Server Sample)](../core/aggregator-biztalk-server-sample.md).</span></span>  
  
## <a name="pipeline-execution---behavioral-differences"></a><span data-ttu-id="3f396-140">パイプラインの実行の動作の違い</span><span class="sxs-lookup"><span data-stu-id="3f396-140">Pipeline Execution - Behavioral Differences</span></span>  
 <span data-ttu-id="3f396-141">送信の実行または受信パイプライン、オーケストレーションによって呼び出されたときに大部分がメッセージング インフラストラクチャ内で同じパイプラインを実行するときと同じ (つまりで受信場所または送信ポート)。</span><span class="sxs-lookup"><span data-stu-id="3f396-141">The execution of a send or receive pipeline when called by an orchestration is predominantly the same as when the same pipeline executes within the messaging infrastructure (i.e. at receive location or send port).</span></span>  <span data-ttu-id="3f396-142">ただし、以下で説明されている特定の動作の違いがあります。</span><span class="sxs-lookup"><span data-stu-id="3f396-142">However, there are certain behavioral differences that are noted below.</span></span>  
  
### <a name="differences-within-pipeline-stages"></a><span data-ttu-id="3f396-143">パイプラインのステージ内の相違点</span><span class="sxs-lookup"><span data-stu-id="3f396-143">Differences Within Pipeline Stages</span></span>  
 <span data-ttu-id="3f396-144">送信内のステージの実行または受信パイプラインが例外については、ステージで、BizTalk メッセージング インフラストラクチャから呼び出されると、オーケストレーション内から呼び出されたパイプラインがこれらの段階の実行とほぼ同じです以下に。</span><span class="sxs-lookup"><span data-stu-id="3f396-144">The execution of the stages within a send or receive pipeline that is called from within an orchestration is nearly identical to the execution of those stages when the pipeline is called from the BizTalk messaging infrastructure, with the exceptions noted by stage below.</span></span>  
  
-   <span data-ttu-id="3f396-145">アセンブラー/逆アセンブラー。アセンブラーおよび逆アセンブラー ステージは処理されません**追跡プロファイルの**データ。</span><span class="sxs-lookup"><span data-stu-id="3f396-145">Assembler/Disassembler:  The assembler and disassembler stages will not process **Tracking Profile** data.</span></span>  
  
-   <span data-ttu-id="3f396-146">エンコーダー/デコーダー:MIME エンコーダーは、ホストが関連付けられているホストで構成された証明書を使用してメッセージにデジタル署名します。</span><span class="sxs-lookup"><span data-stu-id="3f396-146">Encoder/Decoder:  The MIME encoder digitally signs messages using the certificate configured at the host with which the host is associated.</span></span>  <span data-ttu-id="3f396-147">SMIME エンコーダーでは、パイプラインに渡されたメッセージのコンテキストで、証明書を使用してメッセージを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="3f396-147">The SMIME encoder encrypts messages using the certificate on the context of the message passed into the pipeline.</span></span>  
  
### <a name="schema-resolution"></a><span data-ttu-id="3f396-148">スキーマの解決</span><span class="sxs-lookup"><span data-stu-id="3f396-148">Schema Resolution</span></span>  
 <span data-ttu-id="3f396-149">これには、オーケストレーションからパイプラインを実行する場合にサポートされている 2 つのスキーマ検索アルゴリズムがあります。</span><span class="sxs-lookup"><span data-stu-id="3f396-149">There are two schema lookup algorithms that are supported when executing a pipeline from an orchestration:</span></span>  
  
- <span data-ttu-id="3f396-150">種類による解決</span><span class="sxs-lookup"><span data-stu-id="3f396-150">Resolution by type</span></span>  
  
- <span data-ttu-id="3f396-151">名前による解決</span><span class="sxs-lookup"><span data-stu-id="3f396-151">Resolution by name</span></span>  
  
  <span data-ttu-id="3f396-152">重複するスキーマがデプロイされている場合、適切なスキーマを選択するためのアルゴリズムのロジックは、メッセージング インフラストラクチャのコンテキストで実行するときに使用するのと同じです。</span><span class="sxs-lookup"><span data-stu-id="3f396-152">In cases where duplicate schemas are deployed, the algorithm's logic for selecting the appropriate schema is identical to that used when executing in the context of the messaging infrastructure.</span></span>  
  
### <a name="transactional-pipelines"></a><span data-ttu-id="3f396-153">トランザクション パイプライン</span><span class="sxs-lookup"><span data-stu-id="3f396-153">Transactional Pipelines</span></span>  
 <span data-ttu-id="3f396-154">パイプラインのステージがトランザクション コンポーネントを呼び出すには、使用可能なトランザクション コンテキストがありません。</span><span class="sxs-lookup"><span data-stu-id="3f396-154">Pipelines whose stages call transactional components will not have a transactional context available.</span></span>  <span data-ttu-id="3f396-155">すべての呼び出しに**IPipelineContext.GetTransaction()** がスローされます**NotSupportedException**します。</span><span class="sxs-lookup"><span data-stu-id="3f396-155">Any call to **IPipelineContext.GetTransaction()** will throw **NotSupportedException**.</span></span>  <span data-ttu-id="3f396-156">元のオーケストレーションは、このようなパイプラインの実行は上がりますが、パイプラインを検出してこのような状況を処理する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="3f396-156">This does not preclude execution of such a pipeline from an orchestration, but it does mean that the pipeline will have to detect and handle this situation.</span></span>  
  
### <a name="message-destination"></a><span data-ttu-id="3f396-157">メッセージの宛先</span><span class="sxs-lookup"><span data-stu-id="3f396-157">Message Destination</span></span>  
 <span data-ttu-id="3f396-158">このコンテキストでは、パイプライン コンポーネントによってメッセージ送信先の制御がサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3f396-158">Controlling message destination by pipeline components is not supported in this context.</span></span>  <span data-ttu-id="3f396-159">コンテキスト プロパティを設定**MessageDestination**または**SuspendOnRoutingFailure**により、 **XLANGPipelineManagerException**がスローされます。</span><span class="sxs-lookup"><span data-stu-id="3f396-159">Setting the context properties **MessageDestination** or **SuspendOnRoutingFailure** will cause an **XLANGPipelineManagerException** to be thrown.</span></span>  
  
### <a name="pipeline-component-types"></a><span data-ttu-id="3f396-160">パイプライン コンポーネントの種類</span><span class="sxs-lookup"><span data-stu-id="3f396-160">Pipeline Component Types</span></span>  
 <span data-ttu-id="3f396-161">パイプライン コンポーネントは、オーケストレーション内から呼び出すためには、次に基づく必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f396-161">Pipeline components must be based on the following in order to be called from within an orchestration:</span></span>  
  
-   <span data-ttu-id="3f396-162">.NET framework v1.1</span><span class="sxs-lookup"><span data-stu-id="3f396-162">.NET Framework v1.1</span></span>  
  
-   <span data-ttu-id="3f396-163">.NET framework v2.0</span><span class="sxs-lookup"><span data-stu-id="3f396-163">.NET Framework v2.0</span></span>  
  
-   <span data-ttu-id="3f396-164">.NET framework バージョン 3.0</span><span class="sxs-lookup"><span data-stu-id="3f396-164">.NET Framework v3.0</span></span>  
  
-   <span data-ttu-id="3f396-165">.NET framework v3.5</span><span class="sxs-lookup"><span data-stu-id="3f396-165">.NET Framework v3.5</span></span>  
  
-   <span data-ttu-id="3f396-166">.NET framework v4.0</span><span class="sxs-lookup"><span data-stu-id="3f396-166">.NET Framework v4.0</span></span>  
  
-   <span data-ttu-id="3f396-167">.NET framework v2.0</span><span class="sxs-lookup"><span data-stu-id="3f396-167">.NET Framework v2.0</span></span>  
  
-   <span data-ttu-id="3f396-168">COM (COM)</span><span class="sxs-lookup"><span data-stu-id="3f396-168">COM</span></span>  
  
## <a name="restrictions"></a><span data-ttu-id="3f396-169">制限</span><span class="sxs-lookup"><span data-stu-id="3f396-169">Restrictions</span></span>  
 <span data-ttu-id="3f396-170">次の種類のパイプライン**できません**オーケストレーション内から実行します。</span><span class="sxs-lookup"><span data-stu-id="3f396-170">The following types of pipelines **cannot** be executed from within an orchestration:</span></span>  
  
- <span data-ttu-id="3f396-171">トランザクション パイプライン</span><span class="sxs-lookup"><span data-stu-id="3f396-171">Transactional pipelines</span></span>  
  
- <span data-ttu-id="3f396-172">回復可能パイプライン。</span><span class="sxs-lookup"><span data-stu-id="3f396-172">Recoverable pipelines</span></span>  
  
- <span data-ttu-id="3f396-173">BAM インターセプター API を呼び出すパイプライン (、 **NotSupportedException**がスローされます)。</span><span class="sxs-lookup"><span data-stu-id="3f396-173">Pipelines which call the BAM interceptor API (a **NotSupportedException** will be thrown).</span></span>  
  
- <span data-ttu-id="3f396-174">同じパイプライン インスタンスは、すべての分岐で同期のスコープに配置されていない限り、並列図形のそれぞれの分岐で実行できません。</span><span class="sxs-lookup"><span data-stu-id="3f396-174">The same pipeline instance cannot be executed in different branches of the parallel shape unless it is placed in a synchronized scope in every branch.</span></span>  
  
- <span data-ttu-id="3f396-175">既存のパイプライン (アセンブリ) に対して構築された、 [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] SDK。</span><span class="sxs-lookup"><span data-stu-id="3f396-175">Existing pipelines (assemblies) that were built against the [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] SDK.</span></span>  
  
## <a name="failure-modes-and-effects"></a><span data-ttu-id="3f396-176">障害モードと効果</span><span class="sxs-lookup"><span data-stu-id="3f396-176">Failure Modes and Effects</span></span>  
 <span data-ttu-id="3f396-177">メッセージが中断が発生した場合、パイプラインの実行でエラーをすべてから BizTalk Server メッセージング インフラストラクチャ内で呼び出すためには、このパイプラインは、例外がスローされる代わりになります。</span><span class="sxs-lookup"><span data-stu-id="3f396-177">Any failure in pipeline execution which would have resulted in a suspended message were this pipeline to be called from within the BizTalk Server Messaging Infrastructure will instead result in an exception being thrown.</span></span>  <span data-ttu-id="3f396-178">スローされる例外は、型の**Microsoft.XLANGs.Pipeline.XLANGPipelineManagerException**します。</span><span class="sxs-lookup"><span data-stu-id="3f396-178">The exception thrown is of type **Microsoft.XLANGs.Pipeline.XLANGPipelineManagerException**.</span></span>  <span data-ttu-id="3f396-179">この例外は、呼び出し元オーケストレーションの catch ブロックで処理できます。</span><span class="sxs-lookup"><span data-stu-id="3f396-179">This thrown exception can be handled in a catch block within the calling orchestration.</span></span>  <span data-ttu-id="3f396-180">オーケストレーションが、スローされた例外をキャッチしない場合、Xlang エンジンはそのテキストには、スローされた例外での例外情報が含まれています、エラーを報告します。</span><span class="sxs-lookup"><span data-stu-id="3f396-180">If the orchestration does not catch the thrown exception, the XLANGs engine reports an error the text of which includes the exception information in the thrown exception.</span></span>  
  
 <span data-ttu-id="3f396-181">例外は、パイプライン コンポーネントによって生成されるエラー メッセージの書式設定を実行します。</span><span class="sxs-lookup"><span data-stu-id="3f396-181">The exception performs formatting of the error messages generated by the pipeline components.</span></span>  
  
 <span data-ttu-id="3f396-182">**メッセージ**のプロパティ、 **XLANGPipelineManagerException**クラスには、パイプラインの実行エラーの詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3f396-182">The **Message** property of the **XLANGPipelineManagerException** class contains details of the pipeline's execution error.</span></span> <span data-ttu-id="3f396-183">この詳細は次の形式です。</span><span class="sxs-lookup"><span data-stu-id="3f396-183">This detail is in the following format:</span></span>  
  
- <span data-ttu-id="3f396-184">パイプラインの実行中にエラーが発生しました\<型をパイプライン\>します。</span><span class="sxs-lookup"><span data-stu-id="3f396-184">There was a failure executing pipeline \<pipeline type\>.</span></span>  <span data-ttu-id="3f396-185">エラーの詳細\<形式のエラー メッセージ\>します。</span><span class="sxs-lookup"><span data-stu-id="3f396-185">Error details \<formatted error message\>.</span></span>  
  
  <span data-ttu-id="3f396-186">このメッセージの\<パイプラインの種類\>パイプライン クラスの名前を指定し、\<形式のエラー メッセージ\>パイプラインの実行中に発生した特定のエラーの説明を示します。</span><span class="sxs-lookup"><span data-stu-id="3f396-186">In this message, \<pipeline type\> is the name of the pipeline class and \<formatted error message\> is a description of the specific failure that occurred during pipeline execution.</span></span>  
  
  <span data-ttu-id="3f396-187">たとえば、オーケストレーションが受信パイプラインを呼び出すし、パイプラインのコンポーネントのいずれも、メッセージの値が認識されるため、パイプラインの実行が失敗した場合、 **XLANGPipelineManagerException**のプロパティにはなります。</span><span class="sxs-lookup"><span data-stu-id="3f396-187">For example, if an orchestration calls a receive pipeline and that pipeline's execution fails because none of the pipeline's components recognizes the message, the values of the **XLANGPipelineManagerException**'s properties would be:</span></span>  
  
|<span data-ttu-id="3f396-188">XLANGPipelineManagerException のプロパティ</span><span class="sxs-lookup"><span data-stu-id="3f396-188">XLANGPipelineManagerException property</span></span>|<span data-ttu-id="3f396-189">値</span><span class="sxs-lookup"><span data-stu-id="3f396-189">Value</span></span>|  
|--------------------------------------------|-----------|  
|<span data-ttu-id="3f396-190">メッセージ</span><span class="sxs-lookup"><span data-stu-id="3f396-190">Message</span></span>|<span data-ttu-id="3f396-191">受信パイプライン"です MyPipelines.ReceivePipeline"を実行中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="3f396-191">There was a failure executing the receive pipeline "MyPipelines.ReceivePipeline".</span></span> <span data-ttu-id="3f396-192">エラーの詳細:"逆アセンブル ステージのコンポーネントはデータを認識できません。</span><span class="sxs-lookup"><span data-stu-id="3f396-192">Error details: "No Disassemble stage components can recognize the data.</span></span>|  
|<span data-ttu-id="3f396-193">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3f396-193">Component</span></span>|<span data-ttu-id="3f396-194">String.Empty</span><span class="sxs-lookup"><span data-stu-id="3f396-194">String.Empty</span></span>|  
  
 <span data-ttu-id="3f396-195">オーケストレーションが送信パイプラインを呼び出すし、検証エラー、内のテキストがあるために、パイプラインの実行が失敗した場合、別の例として、**メッセージ**プロパティの**XLANGPipelineManagerException**になります。</span><span class="sxs-lookup"><span data-stu-id="3f396-195">As another example, if an orchestration calls a send pipeline and that pipeline's execution fails because there is a validation failure, the text in the **Message** property of **XLANGPipelineManagerException** would be:</span></span>  
  
|<span data-ttu-id="3f396-196">XLANGPipelineManagerException のプロパティ</span><span class="sxs-lookup"><span data-stu-id="3f396-196">XLANGPipelineManagerException property</span></span>|<span data-ttu-id="3f396-197">値</span><span class="sxs-lookup"><span data-stu-id="3f396-197">Value</span></span>|  
|--------------------------------------------|-----------|  
|<span data-ttu-id="3f396-198">メッセージ</span><span class="sxs-lookup"><span data-stu-id="3f396-198">Message</span></span>|<span data-ttu-id="3f396-199">送信パイプライン"MyPipelines.SendPipeline"を実行中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="3f396-199">There was a failure executing the send pipeline "MyPipelines.SendPipeline".</span></span>  <span data-ttu-id="3f396-200">エラーの詳細:"ドキュメントの検証に失敗しました。"、\<要素名\>要素が無効です - 値\<要素値\>datatype 'String' - Pattern 制約に失敗しました無効です""。</span><span class="sxs-lookup"><span data-stu-id="3f396-200">Error details:  "Failed to validate the document: "The \<element name\> element is invalid - The value \<element value\> is invalid according to its datatype 'String' - The Pattern constraint failed.""</span></span>|  
|<span data-ttu-id="3f396-201">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3f396-201">Component</span></span>|<span data-ttu-id="3f396-202">“Microsoft.BizTalk.Component.XmlValidator”</span><span class="sxs-lookup"><span data-stu-id="3f396-202">“Microsoft.BizTalk.Component.XmlValidator”</span></span>|