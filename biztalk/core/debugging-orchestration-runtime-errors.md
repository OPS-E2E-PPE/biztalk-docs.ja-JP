---
title: オーケストレーションの実行時エラーのデバッグ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7be9ee5a-b9fa-428b-8b92-0fa0f801c724
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87a47c5b2ee432059365c6f9046a75bb5775fc02
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969904"
---
# <a name="debugging-orchestration-runtime-errors"></a><span data-ttu-id="dc8b3-102">オーケストレーションの実行時エラーのデバッグ</span><span class="sxs-lookup"><span data-stu-id="dc8b3-102">Debugging Orchestration Runtime Errors</span></span>
<span data-ttu-id="dc8b3-103">このセクションでは、オーケストレーションに関する実行時の問題の解決に役立つ一連の質問と回答を示します。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-103">This section contains a set of questions and answers designed to help you resolve runtime issues with your orchestrations.</span></span>  
  
## <a name="why-do-i-get-intermittent-subscription-errors-when-sending-to-a-child-orchestration-that-was-just-started-by-the-parent"></a><span data-ttu-id="dc8b3-104">親によって開始された直後の子オーケストレーションに送信を行うと、断続的なサブスクリプション エラーが発生するのはなぜでしょうか。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-104">Why do I get intermittent subscription errors when sending to a child orchestration that was just started by the parent?</span></span>  
 <span data-ttu-id="dc8b3-105">サブスクリプションが見つかりませんでした、というサブスクリプション エラーは、競合状態の結果です。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-105">The subscription error "could not find subscription" is a result of a race condition.</span></span> <span data-ttu-id="dc8b3-106">競合状態は、プロセスの結果が実行順序によって変わる場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-106">A race condition occurs when the outcome of a process depends on the particular order in which the process takes place.</span></span> <span data-ttu-id="dc8b3-107">この場合、競合状態が発生するのは、親によって送信されたメッセージを受信する時点で、まだ子オーケストレーションが開始されていないときです。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-107">In this case, the condition occurs when the child orchestration has not been started in time to receive the message sent by the parent.</span></span>  
  
 <span data-ttu-id="dc8b3-108">この問題を回避するには、子オーケストレーションが開始されてメッセージを受信できる状態になったときに、子オーケストレーションから親にメッセージを返すようにします。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-108">To avoid this problem, the child orchestration could send a message back to the parent when it has been started and is prepared to receive a message.</span></span> <span data-ttu-id="dc8b3-109">この方法にすれば、子オーケストレーションを開始した親オーケストレーションが、メッセージを送信する前に受信者の存在を認識できます。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-109">In this way, the parent orchestration that started it would know that there is a receiver before sending a message.</span></span>  
  
## <a name="why-do-i-get-errors-when-i-attach-a-dynamic-send-port-to-a-logical-port"></a><span data-ttu-id="dc8b3-110">動的送信ポートを論理ポートに接続すると、エラーが発生するのはなぜでしょうか。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-110">Why do I get errors when I attach a dynamic send port to a logical port?</span></span>  
 <span data-ttu-id="dc8b3-111">動的ポートは、割り当てるポートの属性と特性のすべてを継承するようには設計されていません。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-111">A dynamic port is not designed to inherit all of the attributes and characteristics of the port assigned to it.</span></span> <span data-ttu-id="dc8b3-112">動的ポートは、アドレスを取得するだけであり、論理ポートに関連付けられているその他の情報は継承しません。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-112">A dynamic port gets an address only; it does not inherit the other information associated with the logical port.</span></span>  
  
 <span data-ttu-id="dc8b3-113">たとえば、"配信通知 = 送信済み" 状態の論理ポートに動的送信ポートを接続した場合、ランタイムは配信通知を配信しません。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-113">For example, if you attach a dynamic send port to a logical port with Delivery Notification = Transmitted, the runtime will not deliver a delivery notification.</span></span> <span data-ttu-id="dc8b3-114">XLANGs ランタイムが配信通知を待機するのは、実際にポートがそのように静的に設定されている場合のみです。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-114">The XLANGs runtime only listens for a delivery notification if the port has actually been set up that way statically.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc8b3-115">XLANGs では、ポートは静的に構成されているものとしてのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-115">In XLANGs, ports will behave only as they have been configured statically.</span></span>  
  
## <a name="when-i-try-to-run-my-application-after-deploying-an-orchestration-with-custom-components-why-do-i-get-the-error-file-or-assembly-name-or-one-of-its-dependencies-not-found"></a><span data-ttu-id="dc8b3-116">カスタム コンポーネントを含むオーケストレーションの展開後にアプリケーションを実行しようとすると、ファイルまたはアセンブリ名、あるいはその依存関係の 1 つが見つかりません、というエラーが発生するのはなぜでしょうか。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-116">When I try to run my application after deploying an orchestration with custom components, why do I get the error "File or Assembly name or one of its dependencies not found"?</span></span>  
 <span data-ttu-id="dc8b3-117">このエラーは、通常、BizTalk オーケストレーション エンジンがカスタム コンポーネントを見つけられないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-117">This error usually means the BizTalk orchestration engine cannot locate the custom component.</span></span> <span data-ttu-id="dc8b3-118">アプリケーションをホストするコンピューターのグローバル アセンブリ キャッシュに、BizTalk アプリケーションに含まれているすべてのアセンブリをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-118">You must install all assemblies included in a BizTalk application in the global assembly cache of the computer that hosts the application.</span></span>  
  
## <a name="an-assemblyname-context-property-was-not-valid-error-occurs-when-submitting-a-document-to-a-web-service-via-an-orchestration"></a><span data-ttu-id="dc8b3-119">オーケストレーション経由で Web サービスにドキュメントを送信する際に、AssemblyName コンテキスト プロパティが無効でした、というエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-119">An "AssemblyName context property was not valid" error occurs when submitting a document to a Web service via an orchestration</span></span>  
  
### <a name="problem"></a><span data-ttu-id="dc8b3-120">問題</span><span class="sxs-lookup"><span data-stu-id="dc8b3-120">Problem</span></span>  
 <span data-ttu-id="dc8b3-121">オーケストレーション経由でドキュメントを Web サービスに送信すると、AssemblyName コンテキスト プロパティが無効です、というエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-121">Submitting a document to a Web service via an orchestration results in an "AssemblyName context property not valid" error.</span></span>  
  
### <a name="cause"></a><span data-ttu-id="dc8b3-122">原因</span><span class="sxs-lookup"><span data-stu-id="dc8b3-122">Cause</span></span>  
 <span data-ttu-id="dc8b3-123">BizTalk アプリケーションでは、介在するオーケストレーションなし「メッセージング」アプローチを使用してもともとです。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-123">The BizTalk application was originally designed using a "messaging" approach without an intervening orchestration.</span></span> <span data-ttu-id="dc8b3-124">このようなソリューションでは、送信ポート フィルターを使用して受信ポートと送信ポートをリンクするので、ドキュメントは受信時に送信ポートに渡されます。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-124">This type of solution uses a send port filter to link the receive port and the send port so that the document is passed through to the send port upon receipt.</span></span> <span data-ttu-id="dc8b3-125">その後、ソリューションは、送信ポートにバインドされているオーケストレーションを含むように変更されました。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-125">Later, the solution was modified to include an orchestration that was bound to the send port.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="dc8b3-126">解決策</span><span class="sxs-lookup"><span data-stu-id="dc8b3-126">Resolution</span></span>  
 <span data-ttu-id="dc8b3-127">送信ポートのフィルターを削除します。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-127">Remove the filter on the send port.</span></span> <span data-ttu-id="dc8b3-128">オーケストレーションにバインドされている送信ポートにフィルターを適用すると、多くの場合、メッセージがオーケストレーションをバイパスするので、コンテキスト プロパティ エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-128">If you apply a filter to a send port that is bound to an orchestration, messages will often bypass the orchestration and cause the context property error.</span></span>  
  
## <a name="a-wrongbodypartexception-occurs-when-handling-a-multipart-mime-message-in-an-orchestration"></a><span data-ttu-id="dc8b3-129">オーケストレーションでマルチパート MIME メッセージを処理する際に、"WrongBodyPartException" が発生します。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-129">A "WrongBodyPartException" occurs when handling a multipart MIME message in an orchestration</span></span>  
  
### <a name="problem"></a><span data-ttu-id="dc8b3-130">問題</span><span class="sxs-lookup"><span data-stu-id="dc8b3-130">Problem</span></span>  
 <span data-ttu-id="dc8b3-131">結果をオーケストレーションにマルチパート MIME メッセージの受信、 **WrongBodyPartException**例外。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-131">Receiving a multipart MIME message into an orchestration results in a **WrongBodyPartException** exception.</span></span>  
  
### <a name="cause"></a><span data-ttu-id="dc8b3-132">原因</span><span class="sxs-lookup"><span data-stu-id="dc8b3-132">Cause</span></span>  
 <span data-ttu-id="dc8b3-133">このエラーは、部分の順序が誤って指定された場合、または指定された部分の位置にメッセージが準拠していない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-133">This error can occur if the order of the parts is specified incorrectly or messages do not conform to the part positions you have specified.</span></span> <span data-ttu-id="dc8b3-134">たとえば、3 番目の部分にボディ部を指定している場合に、到着したメッセージの 3 番目の位置がヘッダー部であるときなどです。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-134">For example, if you specify that the third part is a body part but messages arrive with a header part in the third position.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="dc8b3-135">解決策</span><span class="sxs-lookup"><span data-stu-id="dc8b3-135">Resolution</span></span>  
 <span data-ttu-id="dc8b3-136">ボディ部のインデックス設定が正しいことを確認し、アダプター経由で到着するすべてのメッセージがその設定と一致するようにします。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-136">Verify that the body part index setting is correct and then ensure that all messages arriving through the adapter are consistent with the setting.</span></span> <span data-ttu-id="dc8b3-137">オーケストレーションを停止することで (ただし参加は継続)、オーケストレーション内で失敗する MIME メッセージのコンテンツを調査できます。この方法では、メッセージが強制的に公開されるので、管理コンソールを使用してメッセージを調べて、部分の順序を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-137">You can inspect the contents of MIME messages that fail inside an orchestration by stopping the orchestration (but keeping it enlisted); this will force the message to be published so you can examine it using the Administration console and verify the order of the parts.</span></span>  
  
## <a name="multipart-mime-message-part-cannot-be-found"></a><span data-ttu-id="dc8b3-138">マルチパート MIME メッセージ部分が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-138">Multipart MIME message part cannot be found</span></span>  
  
### <a name="problem"></a><span data-ttu-id="dc8b3-139">問題</span><span class="sxs-lookup"><span data-stu-id="dc8b3-139">Problem</span></span>  
 <span data-ttu-id="dc8b3-140">MIME を取得したメッセージのようなエラーをスロー、BizTalk Server ランタイムで結果が 0 より大きいインデックス値を持つ部分"のインデックスでのマルチパート メッセージを見つけることができません =\<値\>"です。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-140">Attempts to retrieve a MIME message part with an index value greater than 0 results in the BizTalk Server runtime throwing an error similar to "can't find multi-part message with index = \<value\>".</span></span>  
  
### <a name="cause"></a><span data-ttu-id="dc8b3-141">原因</span><span class="sxs-lookup"><span data-stu-id="dc8b3-141">Cause</span></span>  
 <span data-ttu-id="dc8b3-142">このエラーの最も一般的な原因を次に示します。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-142">The most common causes for this error are:</span></span>  
  
-   <span data-ttu-id="dc8b3-143">MIME メッセージの部分が想定された数に足りません。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-143">The MIME message has fewer parts than expected.</span></span>  
  
-   <span data-ttu-id="dc8b3-144">MIME メッセージが正常に解析できませんでした。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-144">The MIME message could not be fully parsed.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="dc8b3-145">解決策</span><span class="sxs-lookup"><span data-stu-id="dc8b3-145">Resolution</span></span>  
 <span data-ttu-id="dc8b3-146">この問題は、メッセージ ソースから取得するメッセージ部分が、想定される範囲内の部分のみになるようにすることで解決できます。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-146">You can resolve this problem by ensuring that your code retrieves only message parts that are within the range expected from the message source.</span></span> <span data-ttu-id="dc8b3-147">解析の問題の場合、元の MIME メッセージの構造に誤りがなく、正しく構築されているか確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-147">In the case of a parsing issue, you should verify that the original MIME message is structurally sound and properly constructed.</span></span> <span data-ttu-id="dc8b3-148">不定期に解析の問題が起こる場合、オーケストレーションに適切な例外ハンドラーがあるか確認します。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-148">If you expect occasional parsing problems, ensure that your orchestration has appropriate exception handlers.</span></span>  
  
## <a name="you-receive-a-the-file-send-adapter-cannot-open-file-for-writing-error-when-sending-using-a-dynamic-send-port"></a><span data-ttu-id="dc8b3-149">動的送信ポートを使用して送信を行うと、"FILE 送信アダプターがファイルを書き込み用に開けません" というエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-149">You receive a "The FILE send adapter cannot open file for writing" error when sending using a dynamic send port</span></span>  
  
### <a name="problem"></a><span data-ttu-id="dc8b3-150">問題</span><span class="sxs-lookup"><span data-stu-id="dc8b3-150">Problem</span></span>  
 <span data-ttu-id="dc8b3-151">表示されたら、"ファイル送信アダプターがファイルを開くことができません *\<filename\>* 書き込み用"動的なを使用して送信するときに、BizTalk Server のイベント ログにエラーが送信ポート。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-151">You receive a "The FILE send adapter cannot open file *\<filename\>* for writing" error in the BizTalk Server event log when sending using a dynamic send port.</span></span>  
  
 <span data-ttu-id="dc8b3-152">この問題が発生したときに、 **BTS です。OutBoundTransportLocation**プロパティがオーケストレーションの式で定義されていると、ファイル トランスポートを指定すると、たとえば、次の式では実行時にこのエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-152">This problem occurs when the **BTS.OutBoundTransportLocation** property is defined in an orchestration expression and the file transport is specified, for example the following expressions will cause this error at runtime:</span></span>  
  
```  
Message2=Message1;  
Message2(BTS.OutboundTransportLocation) = "file:///c:/test/out";  
MySendPort(Microsoft.XLANGs.BaseTypes.Address)=Message2(BTS.OutboundTransportLocation);  
```  
  
 <span data-ttu-id="dc8b3-153">\- または -</span><span class="sxs-lookup"><span data-stu-id="dc8b3-153">\- Or -</span></span>  
  
```  
Message2=Message1;  
Message2(BTS.OutboundTransportLocation) = "file://mymachine/test/out";  
MySendPort(Microsoft.XLANGs.BaseTypes.Address)=Message2(BTS.OutboundTransportLocation);  
```  
  
### <a name="cause"></a><span data-ttu-id="dc8b3-154">原因</span><span class="sxs-lookup"><span data-stu-id="dc8b3-154">Cause</span></span>  
 <span data-ttu-id="dc8b3-155">この問題は、オーケストレーション エンジンは実行時にテキストを削除すると、"**file://"** 指定した URL からです。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-155">This problem occurs because at runtime the orchestration engine removes the text "**file://"** from the specified URL.</span></span> <span data-ttu-id="dc8b3-156">したがって、先ほどの例では、"file:///c:/test/out" は \c:\test\out と評価され、"file://mymachine/test/out" は mymachine\test\out と評価されます。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-156">So, using the examples above, "file:///c:/test/out" is evaluated as \c:\test\out and "file://mymachine/test/out" is evaluated as mymachine\test\out.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="dc8b3-157">解決策</span><span class="sxs-lookup"><span data-stu-id="dc8b3-157">Resolution</span></span>  
 <span data-ttu-id="dc8b3-158">URL を指定する場合、 **BTS です。OutBoundTransportLocation**を式でプロパティを追加または削除「/」文字がします。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-158">When specifying the URL for the **BTS.OutBoundTransportLocation** property in an expression, add or remove "/" characters as needed.</span></span> <span data-ttu-id="dc8b3-159">上記の例を使用して、 **BTS です。OutBoundTransportLocation**プロパティを"file://c:/test/out がまたはに評価される c:\test\out"file:///mymachine/test/out"\\mymachine\test\out として定義すべき\\\mymachine\test\out です。</span><span class="sxs-lookup"><span data-stu-id="dc8b3-159">Using the examples above the **BTS.OutBoundTransportLocation** property should be defined as "file://c:/test/out", which would evaluate to c:\test\out or "file:////mymachine/test/out", which would evaluate to \\\mymachine\test\out.</span></span>