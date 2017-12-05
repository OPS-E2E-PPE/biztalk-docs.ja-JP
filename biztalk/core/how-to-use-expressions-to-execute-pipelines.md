---
title: "式を使用してパイプラインを実行する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "26"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08f5933d3592d391087196f31185e279c40c4836
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-use-expressions-to-execute-pipelines"></a><span data-ttu-id="a5560-102">パイプラインを実行する式の使用方法</span><span class="sxs-lookup"><span data-stu-id="a5560-102">How to Use Expressions to Execute Pipelines</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="a5560-103"> では、オーケストレーション内からパイプラインを同期的に呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="a5560-103"> has the ability to synchronously call a pipeline from within an Orchestration.</span></span> <span data-ttu-id="a5560-104">これにより、オーケストレーションで、パイプライン (送信または受信) にカプセル化されたメッセージ処理をデータの本体に対して利用することができます。そのデータをメッセージング インフラストラクチャに送信する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a5560-104">This enables orchestrations to leverage the message processing encapsulated within a pipeline (either send or receive) against a body of data without having to send that data through the messaging infrastructure.</span></span>  
  
 <span data-ttu-id="a5560-105">この機能を使用すると、オーケストレーションから送信パイプラインを呼び出して、複数のメッセージを 1 つの送信インターチェンジに統合することができます。</span><span class="sxs-lookup"><span data-stu-id="a5560-105">You can use this feature to enable an orchestration to call a send pipeline in order to aggregate several messages into a single outgoing interchange.</span></span> <span data-ttu-id="a5560-106">反対に、オーケストレーションから受信パイプラインを呼び出して、メッセージング インフラストラクチャの外部で取得されたインターチェンジをデコードおよび逆アセンブルすることもできます。メッセージ ボックスを通過する場合の処理コストが発生することもありません。</span><span class="sxs-lookup"><span data-stu-id="a5560-106">Conversely, an orchestration could call a receive pipeline to decode and disassemble an interchange obtained outside of the messaging infrastructure, without incurring the processing costs of going through the message box.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a5560-107">詳細</span><span class="sxs-lookup"><span data-stu-id="a5560-107">Details</span></span>  
 <span data-ttu-id="a5560-108">オーケストレーション内のメソッドを使用して、 **XLANGPipelineManager**クラス (で、 **Microsoft.XLANGs.Pipeline**名前空間) を呼び出して送信または受信パイプラインです。</span><span class="sxs-lookup"><span data-stu-id="a5560-108">Orchestrations use methods in the **XLANGPipelineManager** class (in the **Microsoft.XLANGs.Pipeline** namespace) to call send or receive pipelines.</span></span>  <span data-ttu-id="a5560-109">受信パイプラインは、BizTalk メッセージングのメッセージ受信のコンテキストでパイプラインが実行される場合と同じように、単一のメッセージまたはインターチェンジを処理して 0 個以上のメッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="a5560-109">A Receive pipeline consumes either a single message or an interchange and yields zero or more messages, just as when the pipeline executes in the context of receiving a message within BizTalk messaging.</span></span> <span data-ttu-id="a5560-110">送信パイプラインも、BizTalk メッセージングのメッセージ送信のコンテキストでパイプラインが実行される場合と同じように、1 つ以上のメッセージを処理して単一のメッセージまたはインターチェンジを生成します。</span><span class="sxs-lookup"><span data-stu-id="a5560-110">A Send pipeline consumes one or more messages and yields a single message or interchange, again, just as when the pipeline executes in the context of sending a message within BizTalk messaging.</span></span>  
  
## <a name="calling-a-receive-pipeline"></a><span data-ttu-id="a5560-111">受信パイプラインの呼び出し</span><span class="sxs-lookup"><span data-stu-id="a5560-111">Calling a Receive Pipeline</span></span>  
 <span data-ttu-id="a5560-112">アプリケーションの呼び出し、オーケストレーション内から受信パイプラインを呼び出すために、 **ExecuteReceivePipeline()**のメソッド、 **XLANGPipelineManager**クラスです。</span><span class="sxs-lookup"><span data-stu-id="a5560-112">In order to call a receive pipeline from within an orchestration, the application calls the **ExecuteReceivePipeline()** method of the **XLANGPipelineManager** class.</span></span>  <span data-ttu-id="a5560-113">このメソッドは、単一のインターチェンジを消費し、0 個以上のメッセージのコレクションを返します (のインスタンスに含まれている、 **ReceivePipelineOutputMessages**クラス)。</span><span class="sxs-lookup"><span data-stu-id="a5560-113">This method consumes a single interchange and returns a collection of zero or more messages (contained in an instance of the **ReceivePipelineOutputMessages** class).</span></span> <span data-ttu-id="a5560-114">このメソッドの構文の詳細については、.NET クラス ライブラリ参照を**XLANGPipelineManager**クラスです。</span><span class="sxs-lookup"><span data-stu-id="a5560-114">The syntax of this method is detailed in the .NET class library reference for the **XLANGPipelineManager** class.</span></span>  
  
 <span data-ttu-id="a5560-115">オーケストレーションから受信パイプラインを実行するための API を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="a5560-115">The API for executing a receive pipeline from within an orchestration is:</span></span>  
  
 `// Execute receive pipeline`  
  
 `static public ReceivePipelineOutputMessages ExecuteReceivePipeline(System.Type receivePipelineType, XLANGMessage msg);`  
  
 <span data-ttu-id="a5560-116">受信パイプラインへの呼び出しを完了できると通常、**式**オーケストレーション内の図形です。</span><span class="sxs-lookup"><span data-stu-id="a5560-116">A call to a receive pipeline would typically be done in an **Expression** shape within the orchestration.</span></span>  
  
 <span data-ttu-id="a5560-117">オーケストレーションから受信パイプラインを呼び出すには、オーケストレーション プロジェクトでパイプライン アセンブリを参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5560-117">In order to call a receive pipeline from within an orchestration, the developer must reference the pipeline assembly in the orchestration project.</span></span> <span data-ttu-id="a5560-118">次に、受信パイプラインを呼び出すオーケストレーションの例を示します。</span><span class="sxs-lookup"><span data-stu-id="a5560-118">Following is an example of an orchestration that calls a receive pipeline:</span></span>  
  
 <span data-ttu-id="a5560-119">![受信パイプラインの呼び出し画面](../core/media/callingreceivepipelinefromorchestration.gif "CallingReceivePipelineFromOrchestration")</span><span class="sxs-lookup"><span data-stu-id="a5560-119">![Calling Receive Pipeline screen](../core/media/callingreceivepipelinefromorchestration.gif "CallingReceivePipelineFromOrchestration")</span></span>  
  
 <span data-ttu-id="a5560-120">さらに詳細な例では、SDK サンプルを参照してください。[で構成されるメッセージ プロセッサ (BizTalk Server サンプル)](../core/composed-message-processor-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="a5560-120">For a more detailed example, see the SDK sample [Composed Message Processor (BizTalk Server Sample)](../core/composed-message-processor-biztalk-server-sample.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5560-121">型の変数**ReceivePipelineOutputMessages**オーケストレーションのアトミックのスコープ内でのみ宣言できます。</span><span class="sxs-lookup"><span data-stu-id="a5560-121">A variable of type **ReceivePipelineOutputMessages** can be declared only within an atomic scope in an orchestration.</span></span>  <span data-ttu-id="a5560-122">この型の変数はシリアル化できないため、オーケストレーションの永続化が維持されないからですが、オーケストレーションはアトミックのスコープ内で実行されるときは永続化されません。</span><span class="sxs-lookup"><span data-stu-id="a5560-122">This is because variables of this type are not serializable and thus would not survive persistence of the orchestration, and orchestrations are never persisted while executing within an atomic scope.</span></span>  <span data-ttu-id="a5560-123">したがって、受信パイプラインはアトミックのスコープ内でしか実行できないことになります。</span><span class="sxs-lookup"><span data-stu-id="a5560-123">This means that a receive pipeline can be executed only within an atomic scope.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5560-124">呼び出すときに**PassThruReceive**ように、着信メッセージの種類に関係なく System.Xml.XmlDocument が XML か、受信メッセージの変数の型を宣言する必要がありますパイプラインまたはオーケストレーション内からカスタム パイプライン コンポーネントでは、.</span><span class="sxs-lookup"><span data-stu-id="a5560-124">When calling **PassThruReceive** pipeline or custom pipeline component from within an orchestration, you must declare the variable type for incoming message as System.Xml.XmlDocument despite of the incoming message type is XML or not.</span></span> <span data-ttu-id="a5560-125">したがって、受信メッセージが XML メッセージ以外 (フラット ファイル形式のメッセージなど) の場合は、処理しようとすると例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="a5560-125">Therefore, you may encounter exception if you try to operate on it if the incoming message is a non-XML message such as a flat file format message.</span></span> <span data-ttu-id="a5560-126">これは、オーケストレーション エンジンが上記のシナリオでは受信メッセージの種類に関係なく System.Xml.XmlDocument を使用するためです。</span><span class="sxs-lookup"><span data-stu-id="a5560-126">This is because of that orchestration engine intends to use System.Xml.XmlDocument for any type of incoming message in the scenario described above.</span></span>  
  
## <a name="calling-a-send-pipeline"></a><span data-ttu-id="a5560-127">送信パイプラインの呼び出し</span><span class="sxs-lookup"><span data-stu-id="a5560-127">Calling a Send Pipeline</span></span>  
 <span data-ttu-id="a5560-128">アプリケーションの呼び出し、オーケストレーション内から送信パイプラインを呼び出す、 **ExecuteSendPipeline()**のメソッド、 **XLANGPipelineManager**クラスです。</span><span class="sxs-lookup"><span data-stu-id="a5560-128">To call a send pipeline from within an orchestration, the application calls the **ExecuteSendPipeline()** method of the **XLANGPipelineManager** class.</span></span> <span data-ttu-id="a5560-129">このメソッドは、1 つまたは複数のメッセージのコレクション (のインスタンスに含まれている、 **SendPipelineInputMessages**クラス) を 1 つのインターチェンジを返します。</span><span class="sxs-lookup"><span data-stu-id="a5560-129">This method consumes a collection of one or more messages (contained in an instance of the **SendPipelineInputMessages** class) and returns a single interchange.</span></span> <span data-ttu-id="a5560-130">このメソッドの構文の詳細については、.NET クラス ライブラリ参照を**XLANGPipelineManager**クラスです。</span><span class="sxs-lookup"><span data-stu-id="a5560-130">The syntax of this method is detailed in the .NET class library reference for the **XLANGPipelineManager** class.</span></span>  <span data-ttu-id="a5560-131">送信パイプラインの実行、新しいインターチェンジへの呼び出しを生成するため**ExecuteSendPipeline()**メソッドは、メッセージの割り当て図形、よう内で行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5560-131">Because execution of a send pipeline yields a new interchange, the call to **ExecuteSendPipeline()** method must be made within a message assignment shape, as such:</span></span>  
  
 <span data-ttu-id="a5560-132">オーケストレーションから送信パイプラインを実行するための API を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="a5560-132">The API for executing a send pipeline from within an orchestration is:</span></span>  
  
 `// Execute a send pipeline`  
  
 `static public ExecuteSendPipeline(System.Type sendPipelineType, SendPipelineInputMessages inputMsgs, XLANGMessage msg);`  
  
 <span data-ttu-id="a5560-133">送信パイプラインの呼び出しを行う必要があります、**メッセージの割り当て**オーケストレーション内の図形です。</span><span class="sxs-lookup"><span data-stu-id="a5560-133">A call to a send pipeline must be done in a **Message Assignment** shape within the orchestration.</span></span>  
  
 <span data-ttu-id="a5560-134">オーケストレーションから送信パイプラインを呼び出すには、オーケストレーション プロジェクトでパイプライン アセンブリを参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5560-134">In order to call a send pipeline from within an orchestration, the developer must reference the pipeline assembly in the orchestration project.</span></span>  <span data-ttu-id="a5560-135">次に、送信パイプラインを呼び出すオーケストレーションの例を示します。</span><span class="sxs-lookup"><span data-stu-id="a5560-135">An example of an orchestration that calls a send pipeline:</span></span>  
  
 <span data-ttu-id="a5560-136">![送信パイプラインの呼び出し画面](../core/media/example-callingsendpipelinefromorchestration.gif "Example_CallingSendPipelineFromOrchestration")</span><span class="sxs-lookup"><span data-stu-id="a5560-136">![Calling Send Pipeline screen](../core/media/example-callingsendpipelinefromorchestration.gif "Example_CallingSendPipelineFromOrchestration")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5560-137">既定の XMLTransmit パイプラインを呼び出す際には、メッセージ コンテキスト プロパティの XMLNORM.EnvelopeSpecName をエンベロープ スキーマの完全修飾名に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5560-137">When calling the default XMLTransmit pipeline, you must set the message context property XMLNORM.EnvelopeSpecName to the fully qualified name of the Envelope schema.</span></span> <span data-ttu-id="a5560-138">例:</span><span class="sxs-lookup"><span data-stu-id="a5560-138">For example:</span></span>  
>   
>  `MyMessage(XMLNORM.EnvelopeSpecName) = "PipelineSchemas.POEnv, PipelineSchemas, Version=1.0.0.0, Culture=nuetral, PublicKeyToken=12e5cc95621c33e8";`  
  
 <span data-ttu-id="a5560-139">さらに詳細な例では、SDK サンプルを参照してください。[アグリゲーター (BizTalk Server サンプル)](../core/aggregator-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="a5560-139">For a more detailed example, see the SDK sample [Aggregator (BizTalk Server Sample)](../core/aggregator-biztalk-server-sample.md).</span></span>  
  
## <a name="pipeline-execution---behavioral-differences"></a><span data-ttu-id="a5560-140">パイプラインの実行の動作の違い</span><span class="sxs-lookup"><span data-stu-id="a5560-140">Pipeline Execution - Behavioral Differences</span></span>  
 <span data-ttu-id="a5560-141">送信パイプラインや受信パイプラインは、オーケストレーションによって呼び出された場合も、メッセージング インフラストラクチャ内 (受信場所や送信ポート) で実行された場合とほとんど同じように実行されます。</span><span class="sxs-lookup"><span data-stu-id="a5560-141">The execution of a send or receive pipeline when called by an orchestration is predominantly the same as when the same pipeline executes within the messaging infrastructure (i.e. at receive location or send port).</span></span>  <span data-ttu-id="a5560-142">ただし、次に示すような動作の違いもあります。</span><span class="sxs-lookup"><span data-stu-id="a5560-142">However, there are certain behavioral differences that are noted below.</span></span>  
  
### <a name="differences-within-pipeline-stages"></a><span data-ttu-id="a5560-143">パイプラインのステージ内の違い</span><span class="sxs-lookup"><span data-stu-id="a5560-143">Differences Within Pipeline Stages</span></span>  
 <span data-ttu-id="a5560-144">送信パイプラインや受信パイプラインのステージは、パイプラインがオーケストレーションから呼び出された場合も、パイプラインが BizTalk メッセージング インフラストラクチャから呼び出された場合とほとんど同じように実行されますが、次に示すような例外もあります。</span><span class="sxs-lookup"><span data-stu-id="a5560-144">The execution of the stages within a send or receive pipeline that is called from within an orchestration is nearly identical to the execution of those stages when the pipeline is called from the BizTalk messaging infrastructure, with the exceptions noted by stage below.</span></span>  
  
-   <span data-ttu-id="a5560-145">アセンブラー/逆アセンブラー: アセンブラーおよび逆アセンブラー ステージが処理されません**追跡プロファイルの**データ。</span><span class="sxs-lookup"><span data-stu-id="a5560-145">Assembler/Disassembler:  The assembler and disassembler stages will not process **Tracking Profile** data.</span></span>  
  
-   <span data-ttu-id="a5560-146">エンコーダー/デコーダー: MIME エンコーダーが、ホストが関連付けられているホストで構成された証明書を使用してメッセージがデジタル署名します。</span><span class="sxs-lookup"><span data-stu-id="a5560-146">Encoder/Decoder:  The MIME encoder digitally signs messages using the certificate configured at the host with which the host is associated.</span></span>  <span data-ttu-id="a5560-147">SMIME エンコーダーでは、パイプラインに渡されたメッセージのコンテキストの証明書を使用してメッセージが暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="a5560-147">The SMIME encoder encrypts messages using the certificate on the context of the message passed into the pipeline.</span></span>  
  
### <a name="schema-resolution"></a><span data-ttu-id="a5560-148">スキーマの解決</span><span class="sxs-lookup"><span data-stu-id="a5560-148">Schema Resolution</span></span>  
 <span data-ttu-id="a5560-149">オーケストレーションからパイプラインを実行する際には、次の 2 つのスキーマ検索アルゴリズムがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="a5560-149">There are two schema lookup algorithms that are supported when executing a pipeline from an orchestration:</span></span>  
  
-   <span data-ttu-id="a5560-150">種類による解決</span><span class="sxs-lookup"><span data-stu-id="a5560-150">Resolution by type</span></span>  
  
-   <span data-ttu-id="a5560-151">名前による解決</span><span class="sxs-lookup"><span data-stu-id="a5560-151">Resolution by name</span></span>  
  
 <span data-ttu-id="a5560-152">重複するスキーマが展開されていた場合に適切なスキーマを選択するアルゴリズムのロジックは、メッセージング インフラストラクチャのコンテキストで実行された場合に使用されるものと同じです。</span><span class="sxs-lookup"><span data-stu-id="a5560-152">In cases where duplicate schemas are deployed, the algorithm's logic for selecting the appropriate schema is identical to that used when executing in the context of the messaging infrastructure.</span></span>  
  
### <a name="transactional-pipelines"></a><span data-ttu-id="a5560-153">トランザクション パイプライン</span><span class="sxs-lookup"><span data-stu-id="a5560-153">Transactional Pipelines</span></span>  
 <span data-ttu-id="a5560-154">トランザクション コンポーネントを呼び出すステージがあるパイプラインでは、トランザクション コンテキストを使用できません。</span><span class="sxs-lookup"><span data-stu-id="a5560-154">Pipelines whose stages call transactional components will not have a transactional context available.</span></span>  <span data-ttu-id="a5560-155">すべての呼び出しに**IPipelineContext.GetTransaction()**がスローされます**NotSupportedException**です。</span><span class="sxs-lookup"><span data-stu-id="a5560-155">Any call to **IPipelineContext.GetTransaction()** will throw **NotSupportedException**.</span></span>  <span data-ttu-id="a5560-156">このようなパイプラインをオーケストレーションから実行できないわけではありませんが、パイプラインでこの状況を検出して処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5560-156">This does not preclude execution of such a pipeline from an orchestration, but it does mean that the pipeline will have to detect and handle this situation.</span></span>  
  
### <a name="message-destination"></a><span data-ttu-id="a5560-157">メッセージ送信先</span><span class="sxs-lookup"><span data-stu-id="a5560-157">Message Destination</span></span>  
 <span data-ttu-id="a5560-158">パイプライン コンポーネントによるメッセージ送信先の制御は、このコンテキストではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="a5560-158">Controlling message destination by pipeline components is not supported in this context.</span></span>  <span data-ttu-id="a5560-159">コンテキスト プロパティを設定**MessageDestination**または**SuspendOnRoutingFailure**により、 **XLANGPipelineManagerException**がスローされます。</span><span class="sxs-lookup"><span data-stu-id="a5560-159">Setting the context properties **MessageDestination** or **SuspendOnRoutingFailure** will cause an **XLANGPipelineManagerException** to be thrown.</span></span>  
  
### <a name="pipeline-component-types"></a><span data-ttu-id="a5560-160">パイプライン コンポーネントの種類</span><span class="sxs-lookup"><span data-stu-id="a5560-160">Pipeline Component Types</span></span>  
 <span data-ttu-id="a5560-161">オーケストレーションから呼び出すには、パイプライン コンポーネントが次のいずれかに基づいている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5560-161">Pipeline components must be based on the following in order to be called from within an orchestration:</span></span>  
  
-   <span data-ttu-id="a5560-162">NET Framework Version 1.1</span><span class="sxs-lookup"><span data-stu-id="a5560-162">.NET Framework v1.1</span></span>  
  
-   <span data-ttu-id="a5560-163">NET Framework Version 2.0</span><span class="sxs-lookup"><span data-stu-id="a5560-163">.NET Framework v2.0</span></span>  
  
-   <span data-ttu-id="a5560-164">.NET Framework Version 3.0</span><span class="sxs-lookup"><span data-stu-id="a5560-164">.NET Framework v3.0</span></span>  
  
-   <span data-ttu-id="a5560-165">.NET Framework Version 3.5</span><span class="sxs-lookup"><span data-stu-id="a5560-165">.NET Framework v3.5</span></span>  
  
-   <span data-ttu-id="a5560-166">.NET Framework Version 4.0</span><span class="sxs-lookup"><span data-stu-id="a5560-166">.NET Framework v4.0</span></span>  
  
-   <span data-ttu-id="a5560-167">NET Framework Version 2.0</span><span class="sxs-lookup"><span data-stu-id="a5560-167">.NET Framework v2.0</span></span>  
  
-   <span data-ttu-id="a5560-168">COM (COM)</span><span class="sxs-lookup"><span data-stu-id="a5560-168">COM</span></span>  
  
## <a name="restrictions"></a><span data-ttu-id="a5560-169">制限</span><span class="sxs-lookup"><span data-stu-id="a5560-169">Restrictions</span></span>  
 <span data-ttu-id="a5560-170">次の種類のパイプライン**できません**オーケストレーション内から実行します。</span><span class="sxs-lookup"><span data-stu-id="a5560-170">The following types of pipelines **cannot** be executed from within an orchestration:</span></span>  
  
-   <span data-ttu-id="a5560-171">トランザクション パイプライン</span><span class="sxs-lookup"><span data-stu-id="a5560-171">Transactional pipelines</span></span>  
  
-   <span data-ttu-id="a5560-172">回復可能パイプライン。</span><span class="sxs-lookup"><span data-stu-id="a5560-172">Recoverable pipelines</span></span>  
  
-   <span data-ttu-id="a5560-173">BAM インターセプター API を呼び出すパイプライン (、 **NotSupportedException**がスローされます)。</span><span class="sxs-lookup"><span data-stu-id="a5560-173">Pipelines which call the BAM interceptor API (a **NotSupportedException** will be thrown).</span></span>  
  
-   <span data-ttu-id="a5560-174">同じパイプライン インスタンスを並列図形の別の分岐で実行することはできません (すべての分岐で同期されたスコープに配置されている場合を除く)。</span><span class="sxs-lookup"><span data-stu-id="a5560-174">The same pipeline instance cannot be executed in different branches of the parallel shape unless it is placed in a synchronized scope in every branch.</span></span>  
  
-   <span data-ttu-id="a5560-175">[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] SDK でビルドされた既存のパイプライン (アセンブリ)。</span><span class="sxs-lookup"><span data-stu-id="a5560-175">Existing pipelines (assemblies) that were built against the [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] SDK.</span></span>  
  
## <a name="failure-modes-and-effects"></a><span data-ttu-id="a5560-176">エラー モードと結果</span><span class="sxs-lookup"><span data-stu-id="a5560-176">Failure Modes and Effects</span></span>  
 <span data-ttu-id="a5560-177">パイプラインの実行で、BizTalk Server メッセージング インフラストラクチャから呼び出された場合はメッセージを保留するようなエラーが発生した場合、代わりに例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="a5560-177">Any failure in pipeline execution which would have resulted in a suspended message were this pipeline to be called from within the BizTalk Server Messaging Infrastructure will instead result in an exception being thrown.</span></span>  <span data-ttu-id="a5560-178">スローされる例外は型**Microsoft.XLANGs.Pipeline.XLANGPipelineManagerException**です。</span><span class="sxs-lookup"><span data-stu-id="a5560-178">The exception thrown is of type **Microsoft.XLANGs.Pipeline.XLANGPipelineManagerException**.</span></span>  <span data-ttu-id="a5560-179">この例外は、呼び出し元オーケストレーションの catch ブロックで処理できます。</span><span class="sxs-lookup"><span data-stu-id="a5560-179">This thrown exception can be handled in a catch block within the calling orchestration.</span></span>  <span data-ttu-id="a5560-180">スローされた例外がオーケストレーションでキャッチされなかった場合は、XLANG エンジンがエラーを報告します。このエラーのテキストには、スローされた例外の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a5560-180">If the orchestration does not catch the thrown exception, the XLANGs engine reports an error the text of which includes the exception information in the thrown exception.</span></span>  
  
 <span data-ttu-id="a5560-181">この例外は、パイプライン コンポーネントによって生成されたエラー メッセージの書式設定を実行します。</span><span class="sxs-lookup"><span data-stu-id="a5560-181">The exception performs formatting of the error messages generated by the pipeline components.</span></span>  
  
 <span data-ttu-id="a5560-182">**メッセージ**のプロパティ、 **XLANGPipelineManagerException**クラスには、パイプラインの実行エラーの詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a5560-182">The **Message** property of the **XLANGPipelineManagerException** class contains details of the pipeline's execution error.</span></span> <span data-ttu-id="a5560-183">詳細は次のような形式になっています。</span><span class="sxs-lookup"><span data-stu-id="a5560-183">This detail is in the following format:</span></span>  
  
-   <span data-ttu-id="a5560-184">パイプラインを実行中にエラーが発生しました\<の種類のパイプライン\>です。</span><span class="sxs-lookup"><span data-stu-id="a5560-184">There was a failure executing pipeline \<pipeline type\>.</span></span>  <span data-ttu-id="a5560-185">エラーの詳細\<形式のエラー メッセージ\>です。</span><span class="sxs-lookup"><span data-stu-id="a5560-185">Error details \<formatted error message\>.</span></span>  
  
 <span data-ttu-id="a5560-186">このメッセージに\<パイプラインの種類\>のパイプライン クラスの名前を指定し、\<形式のエラー メッセージ\>パイプラインの実行中に発生した特定のエラーの説明を示します。</span><span class="sxs-lookup"><span data-stu-id="a5560-186">In this message, \<pipeline type\> is the name of the pipeline class and \<formatted error message\> is a description of the specific failure that occurred during pipeline execution.</span></span>  
  
 <span data-ttu-id="a5560-187">たとえば、オーケストレーションが受信パイプラインを呼び出すし、パイプラインのコンポーネントのいずれも、メッセージの値が認識されるため、パイプラインの実行が失敗した場合、 **XLANGPipelineManagerException**のプロパティにはなります。</span><span class="sxs-lookup"><span data-stu-id="a5560-187">For example, if an orchestration calls a receive pipeline and that pipeline's execution fails because none of the pipeline's components recognizes the message, the values of the **XLANGPipelineManagerException**'s properties would be:</span></span>  
  
|<span data-ttu-id="a5560-188">XLANGPipelineManagerException のプロパティ</span><span class="sxs-lookup"><span data-stu-id="a5560-188">XLANGPipelineManagerException property</span></span>|<span data-ttu-id="a5560-189">値</span><span class="sxs-lookup"><span data-stu-id="a5560-189">Value</span></span>|  
|--------------------------------------------|-----------|  
|<span data-ttu-id="a5560-190">メッセージ</span><span class="sxs-lookup"><span data-stu-id="a5560-190">Message</span></span>|<span data-ttu-id="a5560-191">受信パイプラインの実行エラーです "MyPipelines.ReceivePipeline"。</span><span class="sxs-lookup"><span data-stu-id="a5560-191">There was a failure executing the receive pipeline "MyPipelines.ReceivePipeline".</span></span> <span data-ttu-id="a5560-192">エラーの詳細:"逆アセンブル ステージのコンポーネントを認識できませんデータ。</span><span class="sxs-lookup"><span data-stu-id="a5560-192">Error details: "No Disassemble stage components can recognize the data.</span></span>|  
|<span data-ttu-id="a5560-193">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a5560-193">Component</span></span>|<span data-ttu-id="a5560-194">String.Empty</span><span class="sxs-lookup"><span data-stu-id="a5560-194">String.Empty</span></span>|  
  
 <span data-ttu-id="a5560-195">別の例として、オーケストレーションが送信パイプラインを呼び出すし、テキストで、検証エラーが発生したため、パイプラインの実行が失敗した場合、**メッセージ**プロパティ**XLANGPipelineManagerException**になります。</span><span class="sxs-lookup"><span data-stu-id="a5560-195">As another example, if an orchestration calls a send pipeline and that pipeline's execution fails because there is a validation failure, the text in the **Message** property of **XLANGPipelineManagerException** would be:</span></span>  
  
|<span data-ttu-id="a5560-196">XLANGPipelineManagerException のプロパティ</span><span class="sxs-lookup"><span data-stu-id="a5560-196">XLANGPipelineManagerException property</span></span>|<span data-ttu-id="a5560-197">値</span><span class="sxs-lookup"><span data-stu-id="a5560-197">Value</span></span>|  
|--------------------------------------------|-----------|  
|<span data-ttu-id="a5560-198">メッセージ</span><span class="sxs-lookup"><span data-stu-id="a5560-198">Message</span></span>|<span data-ttu-id="a5560-199">送信パイプライン "MyPipelines.SendPipeline" を実行中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="a5560-199">There was a failure executing the send pipeline "MyPipelines.SendPipeline".</span></span>  <span data-ttu-id="a5560-200">エラーの詳細:"ドキュメントの検証に失敗しました:"、\<要素名\>要素が正しくありません - 値\<要素の値\>が正しくないデータ型 'String' - Pattern 制約が失敗しました""。</span><span class="sxs-lookup"><span data-stu-id="a5560-200">Error details:  "Failed to validate the document: "The \<element name\> element is invalid - The value \<element value\> is invalid according to its datatype 'String' - The Pattern constraint failed.""</span></span>|  
|<span data-ttu-id="a5560-201">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a5560-201">Component</span></span>|<span data-ttu-id="a5560-202">“Microsoft.BizTalk.Component.XmlValidator”</span><span class="sxs-lookup"><span data-stu-id="a5560-202">“Microsoft.BizTalk.Component.XmlValidator”</span></span>|