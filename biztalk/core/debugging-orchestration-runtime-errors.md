---
title: オーケストレーションの実行時エラーのデバッグ |Microsoft Docs
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
ms.openlocfilehash: 3b74291083afc5c25df0723bcbdf105ba51016a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389762"
---
# <a name="debugging-orchestration-runtime-errors"></a><span data-ttu-id="914bf-102">オーケストレーションの実行時エラーのデバッグ</span><span class="sxs-lookup"><span data-stu-id="914bf-102">Debugging Orchestration Runtime Errors</span></span>
<span data-ttu-id="914bf-103">このセクションには、一連質問と回答では、オーケストレーションの実行時の問題を解決するために設計されていますにはが含まれています。</span><span class="sxs-lookup"><span data-stu-id="914bf-103">This section contains a set of questions and answers designed to help you resolve runtime issues with your orchestrations.</span></span>  
  
## <a name="why-do-i-get-intermittent-subscription-errors-when-sending-to-a-child-orchestration-that-was-just-started-by-the-parent"></a><span data-ttu-id="914bf-104">親によって開始された直後の子オーケストレーションに送信するときに断続的なサブスクリプション エラーするはなぜですか。</span><span class="sxs-lookup"><span data-stu-id="914bf-104">Why do I get intermittent subscription errors when sending to a child orchestration that was just started by the parent?</span></span>  
 <span data-ttu-id="914bf-105">サブスクリプション エラー「が見つかりませんでしたサブスクリプション」は、競合状態の結果です。</span><span class="sxs-lookup"><span data-stu-id="914bf-105">The subscription error "could not find subscription" is a result of a race condition.</span></span> <span data-ttu-id="914bf-106">競合状態は、プロセスの結果は、処理が行われる特定の順序に依存する場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="914bf-106">A race condition occurs when the outcome of a process depends on the particular order in which the process takes place.</span></span> <span data-ttu-id="914bf-107">この場合、条件は、親によって送信されたメッセージを受信する時点で、子オーケストレーションが開始されていないときに発生します。</span><span class="sxs-lookup"><span data-stu-id="914bf-107">In this case, the condition occurs when the child orchestration has not been started in time to receive the message sent by the parent.</span></span>  
  
 <span data-ttu-id="914bf-108">この問題を回避するには、ことが起動し、メッセージを受信する準備がとき、子オーケストレーションはでした、親に戻るメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="914bf-108">To avoid this problem, the child orchestration could send a message back to the parent when it has been started and is prepared to receive a message.</span></span> <span data-ttu-id="914bf-109">この方法でを起動した親オーケストレーションにメッセージを送信する前に、受信側があることは認識。</span><span class="sxs-lookup"><span data-stu-id="914bf-109">In this way, the parent orchestration that started it would know that there is a receiver before sending a message.</span></span>  
  
## <a name="why-do-i-get-errors-when-i-attach-a-dynamic-send-port-to-a-logical-port"></a><span data-ttu-id="914bf-110">論理ポートを動的送信ポートを接続したときにエラーするはなぜですか。</span><span class="sxs-lookup"><span data-stu-id="914bf-110">Why do I get errors when I attach a dynamic send port to a logical port?</span></span>  
 <span data-ttu-id="914bf-111">動的なポートは、すべての属性とそれに割り当てられているポートの特性を継承するように設計されていません。</span><span class="sxs-lookup"><span data-stu-id="914bf-111">A dynamic port is not designed to inherit all of the attributes and characteristics of the port assigned to it.</span></span> <span data-ttu-id="914bf-112">動的なポートのみで、アドレスを取得します。論理ポートに関連付けられたその他の情報は継承されません。</span><span class="sxs-lookup"><span data-stu-id="914bf-112">A dynamic port gets an address only; it does not inherit the other information associated with the logical port.</span></span>  
  
 <span data-ttu-id="914bf-113">たとえば、配信通知の論理ポートに動的送信ポートを接続する場合は、= 送信済み、ランタイムは配信通知を配信しません。</span><span class="sxs-lookup"><span data-stu-id="914bf-113">For example, if you attach a dynamic send port to a logical port with Delivery Notification = Transmitted, the runtime will not deliver a delivery notification.</span></span> <span data-ttu-id="914bf-114">XLANGs ランタイムはのみに、ポートが実際に設定されているように静的にする場合、配信通知をリッスンします。</span><span class="sxs-lookup"><span data-stu-id="914bf-114">The XLANGs runtime only listens for a delivery notification if the port has actually been set up that way statically.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="914bf-115">XLANGs では、ポートは静的に構成されている場合にのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="914bf-115">In XLANGs, ports will behave only as they have been configured statically.</span></span>  
  
## <a name="when-i-try-to-run-my-application-after-deploying-an-orchestration-with-custom-components-why-do-i-get-the-error-file-or-assembly-name-or-one-of-its-dependencies-not-found"></a><span data-ttu-id="914bf-116">カスタム コンポーネントを使用したオーケストレーションを展開した後にアプリケーションを実行しようとするとなぜ、エラー「ファイルまたはアセンブリの名前またはその依存関係が見つかりません。 いずれかの」でしょうか。</span><span class="sxs-lookup"><span data-stu-id="914bf-116">When I try to run my application after deploying an orchestration with custom components, why do I get the error "File or Assembly name or one of its dependencies not found"?</span></span>  
 <span data-ttu-id="914bf-117">このエラーは通常、BizTalk オーケストレーション エンジンは、カスタム コンポーネントを見つけることはできませんを意味します。</span><span class="sxs-lookup"><span data-stu-id="914bf-117">This error usually means the BizTalk orchestration engine cannot locate the custom component.</span></span> <span data-ttu-id="914bf-118">アプリケーションをホストするコンピューターのグローバル アセンブリ キャッシュ内の BizTalk アプリケーションに含まれるすべてのアセンブリをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="914bf-118">You must install all assemblies included in a BizTalk application in the global assembly cache of the computer that hosts the application.</span></span>  
  
## <a name="an-assemblyname-context-property-was-not-valid-error-occurs-when-submitting-a-document-to-a-web-service-via-an-orchestration"></a><span data-ttu-id="914bf-119">オーケストレーション経由で Web サービスへのドキュメントを送信するときに、「AssemblyName コンテキスト プロパティが無効です」エラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="914bf-119">An "AssemblyName context property was not valid" error occurs when submitting a document to a Web service via an orchestration</span></span>  
  
### <a name="problem"></a><span data-ttu-id="914bf-120">問題</span><span class="sxs-lookup"><span data-stu-id="914bf-120">Problem</span></span>  
 <span data-ttu-id="914bf-121">「AssemblyName コンテキスト プロパティが無効です」エラーで、オーケストレーションの結果を使用して Web サービスへのドキュメントを送信しています。</span><span class="sxs-lookup"><span data-stu-id="914bf-121">Submitting a document to a Web service via an orchestration results in an "AssemblyName context property not valid" error.</span></span>  
  
### <a name="cause"></a><span data-ttu-id="914bf-122">原因</span><span class="sxs-lookup"><span data-stu-id="914bf-122">Cause</span></span>  
 <span data-ttu-id="914bf-123">BizTalk アプリケーションは、介在するオーケストレーションなし「メッセージング」アプローチを使用してもともと設計されました。</span><span class="sxs-lookup"><span data-stu-id="914bf-123">The BizTalk application was originally designed using a "messaging" approach without an intervening orchestration.</span></span> <span data-ttu-id="914bf-124">この種のソリューションは、送信ポート フィルターを使用して、受信ポートと送信ポートをリンクして、ドキュメントを受信すると、送信ポートに渡されます。</span><span class="sxs-lookup"><span data-stu-id="914bf-124">This type of solution uses a send port filter to link the receive port and the send port so that the document is passed through to the send port upon receipt.</span></span> <span data-ttu-id="914bf-125">後で、ソリューションは、送信ポートにバインドされたオーケストレーションを含むに変更されました。</span><span class="sxs-lookup"><span data-stu-id="914bf-125">Later, the solution was modified to include an orchestration that was bound to the send port.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="914bf-126">解決策</span><span class="sxs-lookup"><span data-stu-id="914bf-126">Resolution</span></span>  
 <span data-ttu-id="914bf-127">送信ポートでフィルターを削除します。</span><span class="sxs-lookup"><span data-stu-id="914bf-127">Remove the filter on the send port.</span></span> <span data-ttu-id="914bf-128">オーケストレーションにバインドされている送信ポートにフィルターを適用する場合メッセージは多くの場合、オーケストレーションをバイパス コンテキスト プロパティのエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="914bf-128">If you apply a filter to a send port that is bound to an orchestration, messages will often bypass the orchestration and cause the context property error.</span></span>  
  
## <a name="a-wrongbodypartexception-occurs-when-handling-a-multipart-mime-message-in-an-orchestration"></a><span data-ttu-id="914bf-129">"WrongBodyPartException"は、オーケストレーションでマルチパート MIME メッセージを処理するときに発生します。</span><span class="sxs-lookup"><span data-stu-id="914bf-129">A "WrongBodyPartException" occurs when handling a multipart MIME message in an orchestration</span></span>  
  
### <a name="problem"></a><span data-ttu-id="914bf-130">問題</span><span class="sxs-lookup"><span data-stu-id="914bf-130">Problem</span></span>  
 <span data-ttu-id="914bf-131">結果をオーケストレーションにマルチパート MIME メッセージの受信、 **WrongBodyPartException**例外。</span><span class="sxs-lookup"><span data-stu-id="914bf-131">Receiving a multipart MIME message into an orchestration results in a **WrongBodyPartException** exception.</span></span>  
  
### <a name="cause"></a><span data-ttu-id="914bf-132">原因</span><span class="sxs-lookup"><span data-stu-id="914bf-132">Cause</span></span>  
 <span data-ttu-id="914bf-133">このエラーは、要素の順序が正しく指定されていない、またはメッセージ部分の指定した位置に準拠していない場合に発生することができます。</span><span class="sxs-lookup"><span data-stu-id="914bf-133">This error can occur if the order of the parts is specified incorrectly or messages do not conform to the part positions you have specified.</span></span> <span data-ttu-id="914bf-134">などのことを指定する場合は、3 番目の部分がボディ部がメッセージを受け取るまでに 3 番目の位置でのヘッダー部分。</span><span class="sxs-lookup"><span data-stu-id="914bf-134">For example, if you specify that the third part is a body part but messages arrive with a header part in the third position.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="914bf-135">解決策</span><span class="sxs-lookup"><span data-stu-id="914bf-135">Resolution</span></span>  
 <span data-ttu-id="914bf-136">ボディ部のインデックス設定が正しいことを確認して、し、アダプター経由で到着するすべてのメッセージが整合性の設定があることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="914bf-136">Verify that the body part index setting is correct and then ensure that all messages arriving through the adapter are consistent with the setting.</span></span> <span data-ttu-id="914bf-137">オーケストレーションを停止することで、オーケストレーション内で失敗する MIME メッセージの内容を検査することができます (ただし、参加を維持する)。これで、メッセージが公開されるので、管理コンソールを使用してチェックし、要素の順序を確認できます。</span><span class="sxs-lookup"><span data-stu-id="914bf-137">You can inspect the contents of MIME messages that fail inside an orchestration by stopping the orchestration (but keeping it enlisted); this will force the message to be published so you can examine it using the Administration console and verify the order of the parts.</span></span>  
  
## <a name="multipart-mime-message-part-cannot-be-found"></a><span data-ttu-id="914bf-138">マルチパート MIME メッセージ部分が見つかりません</span><span class="sxs-lookup"><span data-stu-id="914bf-138">Multipart MIME message part cannot be found</span></span>  
  
### <a name="problem"></a><span data-ttu-id="914bf-139">問題</span><span class="sxs-lookup"><span data-stu-id="914bf-139">Problem</span></span>  
 <span data-ttu-id="914bf-140">メッセージのようなエラーをスローする BizTalk Server ランタイムに結果が 0 より大きいインデックス値を持つパーツの MIME を取得すると"インデックスを持つ、マルチパート メッセージを見つけることができません =\<値\>"。</span><span class="sxs-lookup"><span data-stu-id="914bf-140">Attempts to retrieve a MIME message part with an index value greater than 0 results in the BizTalk Server runtime throwing an error similar to "can't find multi-part message with index = \<value\>".</span></span>  
  
### <a name="cause"></a><span data-ttu-id="914bf-141">原因</span><span class="sxs-lookup"><span data-stu-id="914bf-141">Cause</span></span>  
 <span data-ttu-id="914bf-142">このエラーの最も一般的な原因は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="914bf-142">The most common causes for this error are:</span></span>  
  
-   <span data-ttu-id="914bf-143">MIME メッセージは、予想よりも少ない部分です。</span><span class="sxs-lookup"><span data-stu-id="914bf-143">The MIME message has fewer parts than expected.</span></span>  
  
-   <span data-ttu-id="914bf-144">MIME メッセージを完全に解析できませんでした。</span><span class="sxs-lookup"><span data-stu-id="914bf-144">The MIME message could not be fully parsed.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="914bf-145">解決策</span><span class="sxs-lookup"><span data-stu-id="914bf-145">Resolution</span></span>  
 <span data-ttu-id="914bf-146">コードは、メッセージ ソースから予想される範囲内にあるメッセージ部分のみを取得することによってこの問題を解決することができます。</span><span class="sxs-lookup"><span data-stu-id="914bf-146">You can resolve this problem by ensuring that your code retrieves only message parts that are within the range expected from the message source.</span></span> <span data-ttu-id="914bf-147">解析の問題の場合は、元の MIME メッセージは、構造的なサウンドと適切に構築されたことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="914bf-147">In the case of a parsing issue, you should verify that the original MIME message is structurally sound and properly constructed.</span></span> <span data-ttu-id="914bf-148">不定期の解析の問題を想定する場合は、オーケストレーションが適切な例外ハンドラーを持つことを確認します。</span><span class="sxs-lookup"><span data-stu-id="914bf-148">If you expect occasional parsing problems, ensure that your orchestration has appropriate exception handlers.</span></span>  
  
## <a name="you-receive-a-the-file-send-adapter-cannot-open-file-for-writing-error-when-sending-using-a-dynamic-send-port"></a><span data-ttu-id="914bf-149">送信ポートの動的なを使用して送信する場合に"ファイル送信アダプターはファイルを書き込み用に開けません"というエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="914bf-149">You receive a "The FILE send adapter cannot open file for writing" error when sending using a dynamic send port</span></span>  
  
### <a name="problem"></a><span data-ttu-id="914bf-150">問題</span><span class="sxs-lookup"><span data-stu-id="914bf-150">Problem</span></span>  
 <span data-ttu-id="914bf-151">表示されたら、"ファイル送信アダプターがファイルを開くことができません*\<filename\>* 書き込み用"、dynamic の使用を送信するときに、BizTalk Server イベント ログにエラーの送信ポート。</span><span class="sxs-lookup"><span data-stu-id="914bf-151">You receive a "The FILE send adapter cannot open file *\<filename\>* for writing" error in the BizTalk Server event log when sending using a dynamic send port.</span></span>  
  
 <span data-ttu-id="914bf-152">この問題が発生したときに、 **BTS します。OutBoundTransportLocation**プロパティがオーケストレーションの式で定義されていると、ファイル トランスポートを指定すると、たとえば、次の式では実行時に、このエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="914bf-152">This problem occurs when the **BTS.OutBoundTransportLocation** property is defined in an orchestration expression and the file transport is specified, for example the following expressions will cause this error at runtime:</span></span>  
  
```  
Message2=Message1;  
Message2(BTS.OutboundTransportLocation) = "file:///c:/test/out";  
MySendPort(Microsoft.XLANGs.BaseTypes.Address)=Message2(BTS.OutboundTransportLocation);  
```  
  
 <span data-ttu-id="914bf-153">\- または -</span><span class="sxs-lookup"><span data-stu-id="914bf-153">\- Or -</span></span>  
  
```  
Message2=Message1;  
Message2(BTS.OutboundTransportLocation) = "file://mymachine/test/out";  
MySendPort(Microsoft.XLANGs.BaseTypes.Address)=Message2(BTS.OutboundTransportLocation);  
```  
  
### <a name="cause"></a><span data-ttu-id="914bf-154">原因</span><span class="sxs-lookup"><span data-stu-id="914bf-154">Cause</span></span>  
 <span data-ttu-id="914bf-155">この問題は、実行時にオーケストレーション エンジンは、テキストを削除するために発生します。"**file://"** から指定された URL。</span><span class="sxs-lookup"><span data-stu-id="914bf-155">This problem occurs because at runtime the orchestration engine removes the text "**file://"** from the specified URL.</span></span> <span data-ttu-id="914bf-156">そのため、上記の例を使用して、"file:///c:/test/out"が \c:\test\out として評価され、"file://mymachine/test/out"は \c: として評価されます。</span><span class="sxs-lookup"><span data-stu-id="914bf-156">So, using the examples above, "file:///c:/test/out" is evaluated as \c:\test\out and "file://mymachine/test/out" is evaluated as mymachine\test\out.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="914bf-157">解決策</span><span class="sxs-lookup"><span data-stu-id="914bf-157">Resolution</span></span>  
 <span data-ttu-id="914bf-158">URL を指定する場合、 **BTS します。OutBoundTransportLocation**プロパティを指定する式を追加または削除「/」文字です。</span><span class="sxs-lookup"><span data-stu-id="914bf-158">When specifying the URL for the **BTS.OutBoundTransportLocation** property in an expression, add or remove "/" characters as needed.</span></span> <span data-ttu-id="914bf-159">上記の例を使用して、 **BTS します。OutBoundTransportLocation**として"file://c:/test/out"これに評価される c:\test\out または"file:///mymachine/test/out"に評価されるプロパティを定義する必要があります\\\mymachine\test\out します。</span><span class="sxs-lookup"><span data-stu-id="914bf-159">Using the examples above the **BTS.OutBoundTransportLocation** property should be defined as "file://c:/test/out", which would evaluate to c:\test\out or "file:////mymachine/test/out", which would evaluate to \\\mymachine\test\out.</span></span>