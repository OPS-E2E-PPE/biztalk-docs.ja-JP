---
title: "トランザクションの処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d360742-e969-4651-b364-9edc6a93b8d4
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 954d0e91e078c7f973bddc22961c760aa4080941
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="handling-transactions"></a><span data-ttu-id="d3c50-102">トランザクションの処理</span><span class="sxs-lookup"><span data-stu-id="d3c50-102">Handling Transactions</span></span>
## <a name="transacted-receivers"></a><span data-ttu-id="d3c50-103">トランザクション受信元</span><span class="sxs-lookup"><span data-stu-id="d3c50-103">Transacted Receivers</span></span>  
 <span data-ttu-id="d3c50-104">トランザクション受信元とトランザクション以外の受信元との主な違いは、トランザクション受信元の場合、明示的な MSDTC トランザクションを作成および使用することにより、データ ソースと [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] メッセージ ボックス データベースの間の原子性が確保される点にあります。</span><span class="sxs-lookup"><span data-stu-id="d3c50-104">The main difference between transacted receivers and nontransacted receivers is that transacted receivers create and use an explicit MSDTC transaction to ensure atomicity between their data source and the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MessageBox database.</span></span> <span data-ttu-id="d3c50-105">一般に、アダプターのその他の側面はすべて同じです。</span><span class="sxs-lookup"><span data-stu-id="d3c50-105">In general every other aspect of the adapter is the same.</span></span>  
  
 <span data-ttu-id="d3c50-106">要求 - 応答の受信アダプターは、メッセージング エンジンに元の要求メッセージを送信するためにのみ、トランザクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="d3c50-106">It should be noted that a request-response receive adapter only uses a transaction for submitting the original request message to the Messaging Engine.</span></span> <span data-ttu-id="d3c50-107">メッセージング エンジンからアダプターに応答が送信されるためには、別のトランザクションが必要です。</span><span class="sxs-lookup"><span data-stu-id="d3c50-107">A different transaction is needed for the transmission of the response sent from the Messaging Engine to the adapter.</span></span> <span data-ttu-id="d3c50-108">これは、最初のトランザクションのスコープが、アダプターとメッセージ ボックス データベースの間であるためです。</span><span class="sxs-lookup"><span data-stu-id="d3c50-108">This is because the scope of the first transaction is between the adapter and the MessageBox database.</span></span> <span data-ttu-id="d3c50-109">元の要求メッセージのトランザクションがコミットされるまで、後続の要求メッセージは、メッセージング エンジンからアダプターに送信されません。</span><span class="sxs-lookup"><span data-stu-id="d3c50-109">The subsequent request message is not sent to the adapter from the Messaging Engine until the transaction for the original request message commits.</span></span>  
  
 <span data-ttu-id="d3c50-110">次のオブジェクト間の対話処理図に、受信メッセージのトランザクション送信時にアダプターとメッセージング エンジンが対話するようすを示します。</span><span class="sxs-lookup"><span data-stu-id="d3c50-110">The following object interaction diagram illustrates the interaction between the adapter and the Messaging Engine during a transactional submission of incoming messages.</span></span> <span data-ttu-id="d3c50-111">この例では、次の一連の対話が行われます。</span><span class="sxs-lookup"><span data-stu-id="d3c50-111">In this example, the following sequence of interactions takes place:</span></span>  
  
1.  <span data-ttu-id="d3c50-112">アダプターが新しいバッチをエンジンから取得します。</span><span class="sxs-lookup"><span data-stu-id="d3c50-112">The adapter gets a new batch from the engine.</span></span>  
  
2.  <span data-ttu-id="d3c50-113">アダプターが新しい MSDTC トランザクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="d3c50-113">The adapter creates a new MSDTC transaction.</span></span>  
  
3.  <span data-ttu-id="d3c50-114">アダプターが、トランザクションに参加しているデータ ソースの破壊的な読み取りを行います。</span><span class="sxs-lookup"><span data-stu-id="d3c50-114">The adapter does a destructive read from its data source that has been enlisted in the transaction.</span></span>  
  
4.  <span data-ttu-id="d3c50-115">アダプターがメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="d3c50-115">The adapter submits the message.</span></span>  
  
5.  <span data-ttu-id="d3c50-116">アダプターが**完了**に自身の MSDTC トランザクションを渡す、バッチとその**BatchComplete**コールバック ポインター。</span><span class="sxs-lookup"><span data-stu-id="d3c50-116">The adapter calls **Done** on the batch, passing in its MSDTC transaction and its **BatchComplete** callback pointer.</span></span> <span data-ttu-id="d3c50-117">エンジンを返します、 **IBTDTCCommitConfirm**インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="d3c50-117">The engine returns an **IBTDTCCommitConfirm** interface.</span></span>  
  
6.  <span data-ttu-id="d3c50-118">エンジンが、バッチ処理でアダプターをコールバックその**BatchComplete**実装では、そのメッセージをアダプターに処理の状態を伝えるとします。</span><span class="sxs-lookup"><span data-stu-id="d3c50-118">The engine processes the batch, calls the adapter back on its **BatchComplete** implementation, and conveys the status of its message processing to the adapter.</span></span>  
  
7.  <span data-ttu-id="d3c50-119">バッチが成功した場合、アダプター コミット トランザクションと呼び出し、 **IBTDTCCommitConfirm.DTCCommitConfirm** API が、`true`値がコミットを意味します。</span><span class="sxs-lookup"><span data-stu-id="d3c50-119">If the batch was successful the adapter commits the transaction and calls the **IBTDTCCommitConfirm.DTCCommitConfirm** API with a `true` value signifying commit.</span></span>  
  
 ![](../core/media/transactedreceiver.gif "TransactedReceiver")  
  
## <a name="transacted-transmitters"></a><span data-ttu-id="d3c50-120">トランザクション送信元</span><span class="sxs-lookup"><span data-stu-id="d3c50-120">Transacted Transmitters</span></span>  
 <span data-ttu-id="d3c50-121">トランザクション アダプターは、トランザクション以外のアダプターとほぼ同様です。</span><span class="sxs-lookup"><span data-stu-id="d3c50-121">Transacted adapters are for the most part very similar to nontransacted adapters.</span></span> <span data-ttu-id="d3c50-122">主な違いは、トランザクション アダプターの場合、メッセージ内のデータを、MSDTC トランザクションに参加しているリソースに送信する点です。</span><span class="sxs-lookup"><span data-stu-id="d3c50-122">The main difference is that the transacted adapter sends the data in the message to a resource that it has enlisted in an MSDTC transaction.</span></span>  
  
 <span data-ttu-id="d3c50-123">**実装のヒン ト:**トランザクション アダプターで使用する同じ MSDTC トランザクションを削除すること、先にデータを書き込むため、 **IBTTransportBatch.DeleteMessage**メソッドの呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="d3c50-123">**Implementation Tip:** For transacted sends, the adapter should use the same MSDTC transaction for writing the data to the destination and for deleting it through the **IBTTransportBatch.DeleteMessage** method call.</span></span> <span data-ttu-id="d3c50-124">トランザクションが行われる必要があるのは、この 2 つの操作だけです。</span><span class="sxs-lookup"><span data-stu-id="d3c50-124">Only these two operations need to be transacted.</span></span> <span data-ttu-id="d3c50-125">他の操作など**IBTTransportBatch.Resubmit**、 **IBTTransportBatch.MoveToNextTransport**、および**IBTTransportBatch.MoveToSuspendQ**にする必要はありませんトランザクション。</span><span class="sxs-lookup"><span data-stu-id="d3c50-125">Any other operations, such as **IBTTransportBatch.Resubmit**, **IBTTransportBatch.MoveToNextTransport**, and **IBTTransportBatch.MoveToSuspendQ** do not need to be transacted.</span></span> <span data-ttu-id="d3c50-126">これは、エンジンが暗黙的にトランザクションを使用し、これらの操作が送信先に対してアトミックである必要がないためです。</span><span class="sxs-lookup"><span data-stu-id="d3c50-126">This is because the engine implicitly uses a transaction and these types of operations do not need to be atomic with respect to the destination.</span></span>  
  
 <span data-ttu-id="d3c50-127">次のオブジェクト間の対話処理図に、アダプターとエンジンが対話するようすを示します。</span><span class="sxs-lookup"><span data-stu-id="d3c50-127">The following object interaction diagram illustrates the interactions between the adapter and the engine.</span></span> <span data-ttu-id="d3c50-128">イベントのシーケンスは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d3c50-128">The sequence of events is as follows:</span></span>  
  
1.  <span data-ttu-id="d3c50-129">エンジンが新しいバッチをアダプターから取得します。</span><span class="sxs-lookup"><span data-stu-id="d3c50-129">The engine gets a new batch from the adapter.</span></span>  
  
2.  <span data-ttu-id="d3c50-130">エンジンが 2 つのメッセージを新しいバッチに追加します。</span><span class="sxs-lookup"><span data-stu-id="d3c50-130">The engine adds two messages to the new batch.</span></span>  
  
3.  <span data-ttu-id="d3c50-131">エンジン呼び出し**完了**バッチの原因で、スレッド プールによって提供される内部送信キューにバッチを投稿するアダプター。</span><span class="sxs-lookup"><span data-stu-id="d3c50-131">The engine calls **Done** on the batch, causing the adapter to post the batch to its internal transmit queue that is serviced by its thread pool.</span></span>  
  
4.  <span data-ttu-id="d3c50-132">アダプターが新しい MSDTC トランザクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="d3c50-132">The adapter creates a new MSDTC transaction.</span></span>  
  
5.  <span data-ttu-id="d3c50-133">アダプターがメッセージを送信し、MSDTC トランザクションに送信先を参加させます。</span><span class="sxs-lookup"><span data-stu-id="d3c50-133">The adapter transmits the messages enlisting the destination in the MSDTC transaction.</span></span> <span data-ttu-id="d3c50-134">たとえば、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] データベースに書き込む場合もあります。</span><span class="sxs-lookup"><span data-stu-id="d3c50-134">For example, this could be writing to a [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] database.</span></span>  
  
6.  <span data-ttu-id="d3c50-135">送信後に、アダプターが新しいバッチをエンジンから取得します。</span><span class="sxs-lookup"><span data-stu-id="d3c50-135">After transmission, the adapter gets a new batch from the engine.</span></span>  
  
7.  <span data-ttu-id="d3c50-136">アダプターが**DeleteMessage**が、正常に送信されるメッセージ。</span><span class="sxs-lookup"><span data-stu-id="d3c50-136">The adapter calls **DeleteMessage** for the messages that it has successfully transmitted.</span></span>  
  
8.  <span data-ttu-id="d3c50-137">アダプターが**完了**に自身の DTC トランザクションを渡すバッチ。</span><span class="sxs-lookup"><span data-stu-id="d3c50-137">The adapter calls **Done** on the batch passing in its DTC transaction.</span></span> <span data-ttu-id="d3c50-138">エンジンを返します、 **IBTDTCCommitConfirm**インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="d3c50-138">The engine returns an **IBTDTCCommitConfirm** interface.</span></span>  
  
9. <span data-ttu-id="d3c50-139">エンジンがバッチを処理し、メッセージをアプリケーション キューから削除します。</span><span class="sxs-lookup"><span data-stu-id="d3c50-139">The engine processes the batch, deleting the messages from the application queue.</span></span>  
  
10. <span data-ttu-id="d3c50-140">エンジンはコールバックにアダプターの**IBTBatchCallback**削除操作の成功に関する情報を持つインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="d3c50-140">The engine calls back the adapter's **IBTBatchCallback** interface with information on the success of its deletion operations.</span></span>  
  
11. <span data-ttu-id="d3c50-141">バッチが成功した場合、アダプターがトランザクションをコミットします。</span><span class="sxs-lookup"><span data-stu-id="d3c50-141">If the batch was successful, the adapter commits the transactions.</span></span>  
  
12. <span data-ttu-id="d3c50-142">アダプターが**IBTDTCCommitConfirm.DTCCommitConfirm**トランザクションが正常にコミットされたことをエンジンに通知するためにします。</span><span class="sxs-lookup"><span data-stu-id="d3c50-142">The adapter calls **IBTDTCCommitConfirm.DTCCommitConfirm** to inform the engine that the transaction was successfully committed.</span></span>  
  
 ![](../core/media/transactedtransmitter.gif "Transactedtransmitter")  
  
### <a name="transacted-solicit-response-adapters"></a><span data-ttu-id="d3c50-143">送信請求 - 応答のトランザクション アダプター</span><span class="sxs-lookup"><span data-stu-id="d3c50-143">Transacted Solicit-Response Adapters</span></span>  
 <span data-ttu-id="d3c50-144">双方向受信とは異なり、双方向送信は同じ DTC トランザクションを使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="d3c50-144">Unlike two-way receives, two-way sends may be performed by using the same DTC transaction.</span></span> <span data-ttu-id="d3c50-145">送信請求-応答のトランザクション アダプターを使用する必要があります同じ**IBTTransportBatch**の**SubmitResponseMessage**と**DeleteMessage**操作します。</span><span class="sxs-lookup"><span data-stu-id="d3c50-145">Transacted solicit-response adapters should use the same **IBTTransportBatch** for the **SubmitResponseMessage** and **DeleteMessage** operations.</span></span> <span data-ttu-id="d3c50-146">このバッチは、送信請求 - 応答の組み合わせのメッセージの送受信時と同じ MSDTC トランザクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="d3c50-146">This batch should use the same MSDTC transaction that is used to send and receive the solicit-response message pair.</span></span> <span data-ttu-id="d3c50-147">これにより、送信請求 - 応答のメッセージ交換における原子性が確保されます。</span><span class="sxs-lookup"><span data-stu-id="d3c50-147">This ensures atomicity for the solicit-response message exchange.</span></span>  
  
## <a name="service-components-and-byot"></a><span data-ttu-id="d3c50-148">サービス コンポーネントと BYOT</span><span class="sxs-lookup"><span data-stu-id="d3c50-148">Service Components and BYOT</span></span>  
 <span data-ttu-id="d3c50-149">メッセージング エンジン API は、MSDTC トランザクションの提供を必要とします。</span><span class="sxs-lookup"><span data-stu-id="d3c50-149">The Messaging Engine APIs require an MSDTC transaction to be supplied.</span></span> <span data-ttu-id="d3c50-150">ただし、一部の .NET コンポーネントはサービス コンポーネントとして使用されるよう設計されており、プログラムによるトランザクションのコミットや中止を許可しません。</span><span class="sxs-lookup"><span data-stu-id="d3c50-150">However some .NET components are designed to be used as serviced components and do not allow the transaction to be programmatically committed or aborted.</span></span> <span data-ttu-id="d3c50-151">この場合、トランザクションは、そのプラットフォームの COM+ ランタイムによって自動的にコミットされます。</span><span class="sxs-lookup"><span data-stu-id="d3c50-151">Instead, the transaction is automatically committed by the COM+ runtime on that platform.</span></span>  
  
 <span data-ttu-id="d3c50-152">このようなシナリオでは、アダプターで BYOT (Bring Your Own Transaction) を使用します。</span><span class="sxs-lookup"><span data-stu-id="d3c50-152">For these scenarios, the adapter should use Bring Your Own Transaction (BYOT).</span></span> <span data-ttu-id="d3c50-153">こうすると、アダプターによる MSDTC トランザクションの作成と、このトランザクションを使用する .NET コンポーネントのインスタンス化が可能となります。このコンポーネントは作成されたトランザクションを継承するため、トランザクションを独自に作成することはありません。</span><span class="sxs-lookup"><span data-stu-id="d3c50-153">This allows the adapter to create an MSDTC transaction, instantiate the .NET component that uses the transaction, and allow that component to inherit the created transaction rather than create its own transaction.</span></span> <span data-ttu-id="d3c50-154">.NET Framework が提供**System.EnterpriseServices.BYOT**この目的のためです。</span><span class="sxs-lookup"><span data-stu-id="d3c50-154">The .NET Framework provides **System.EnterpriseServices.BYOT** for this purpose.</span></span> <span data-ttu-id="d3c50-155">SDK の BaseAdapter ヘルパー クラスを提供する**BYOTTransaction**、この目的のためです。</span><span class="sxs-lookup"><span data-stu-id="d3c50-155">The SDK BaseAdapter provides a helper class, **BYOTTransaction**, for this purpose.</span></span>  
  
## <a name="avoiding-race-conditions"></a><span data-ttu-id="d3c50-156">競合状態の回避</span><span class="sxs-lookup"><span data-stu-id="d3c50-156">Avoiding Race Conditions</span></span>  
 <span data-ttu-id="d3c50-157">トランザクション オブジェクトを作成して [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に渡すアダプターを記述する場合、次の操作を実行するコードを記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3c50-157">When you write an adapter that creates a transaction object and hands it to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you are accepting responsibility for writing code that does the following:</span></span>  
  
-   <span data-ttu-id="d3c50-158">バッチに関連付けられているメッセージ内のエラーを解決する。</span><span class="sxs-lookup"><span data-stu-id="d3c50-158">Resolves errors in messages associated with the batch.</span></span>  
  
-   <span data-ttu-id="d3c50-159">バッチ操作に関連付けられているトランザクションの最終結果を決定する。</span><span class="sxs-lookup"><span data-stu-id="d3c50-159">Decides the final outcome of the transaction associated with the batch operation.</span></span>  
  
 <span data-ttu-id="d3c50-160">アダプターは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にトランザクションの最終結果を知らせて内部の追跡データを維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3c50-160">The adapter must inform [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] about the final outcome of the transaction to maintain its internal tracking data.</span></span> <span data-ttu-id="d3c50-161">通知は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を呼び出して結果の**DTCConfirmCommit**です。</span><span class="sxs-lookup"><span data-stu-id="d3c50-161">The adapter informs [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] of the outcome by calling **DTCConfirmCommit**.</span></span> <span data-ttu-id="d3c50-162">アダプターがこれを行わないと、重大なメモリ リークが発生します。</span><span class="sxs-lookup"><span data-stu-id="d3c50-162">If the adapter does not do this, a significant memory leak occurs.</span></span>  
  
 <span data-ttu-id="d3c50-163">上記の 2 つのタスク (エラーの解決と最終結果の決定) は単純に見えますが、実際には、これらのタスクは次に示す異なるスレッドの情報に基づいています。</span><span class="sxs-lookup"><span data-stu-id="d3c50-163">The two tasks listed above (resolve errors and decide the final outcome) seem simple enough, but in fact they rely on information from different threads:</span></span>  
  
-   <span data-ttu-id="d3c50-164">アダプターによって渡された情報に基づいてエラーを処理する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を**BatchComplete**アダプターでのコールバック。</span><span class="sxs-lookup"><span data-stu-id="d3c50-164">The adapter processes errors based on information passed by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to the **BatchComplete** callback in the adapter.</span></span> <span data-ttu-id="d3c50-165">このコールバックはアダプターのスレッド上にあります。</span><span class="sxs-lookup"><span data-stu-id="d3c50-165">This callback is on the adapter's thread.</span></span>  
  
-   <span data-ttu-id="d3c50-166">**DTCConfirmCommit**では、メソッド、 **IBTDTCCommitConfirm**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d3c50-166">**DTCConfirmCommit** is a method on the **IBTDTCCommitConfirm** object.</span></span> <span data-ttu-id="d3c50-167">インスタンス、 **IBTDTCCommitConfirm**バッチによってオブジェクトが返される**ibttransportbatch::done**呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d3c50-167">An instance of the **IBTDTCCommitConfirm** object is returned by the batch **IBTTransportBatch::Done** call.</span></span> <span data-ttu-id="d3c50-168">このインスタンスと同じスレッドが、 **ibttransportbatch::done**呼び出すには、これは、アダプターのスレッドと異なる。</span><span class="sxs-lookup"><span data-stu-id="d3c50-168">This instance is on the same thread as the **IBTTransportBatch::Done** call, which is different from the adapter's thread.</span></span>  
  
-   <span data-ttu-id="d3c50-169">アダプターがすべての呼び出しに対して**ibttransportbatch::done**が、対応するコールバックを**BatchComplete**、それがの結果を報告する個別のスレッドで、メッセージング エンジンによって呼び出されますバッチ送信します。</span><span class="sxs-lookup"><span data-stu-id="d3c50-169">For every call that the adapter makes to **IBTTransportBatch::Done** there is a corresponding callback, **BatchComplete**, that is called by the Messaging Engine in a separate thread to report the result of the batch submission.</span></span> <span data-ttu-id="d3c50-170">**BatchComplete**アダプター ニーズをコミットまたはロールバック、トランザクションがかどうかに基づくバッチが成功または失敗します。</span><span class="sxs-lookup"><span data-stu-id="d3c50-170">In **BatchComplete** the adapter needs to commit or roll back the transaction based on whether the batch passed or failed.</span></span> <span data-ttu-id="d3c50-171">どちらの場合、アダプターは呼び出す必要があります、 **DTCConfirmCommit**メッセージング エンジンにトランザクションの状態を報告します。</span><span class="sxs-lookup"><span data-stu-id="d3c50-171">In either case, the adapter should then call **DTCConfirmCommit** to report the status of the transaction to the Messaging Engine.</span></span>  
  
 <span data-ttu-id="d3c50-172">競合状態が存在するアダプターの実装の**BatchComplete**あると想定できます、 **IBTDTCCommitConfirm**によって返されるオブジェクト**ibttransportbatch::done**は常に利用可能な場合に**BatchComplete**を実行します。</span><span class="sxs-lookup"><span data-stu-id="d3c50-172">A possible race condition exists because the adapter’s implementation of **BatchComplete** can assume that the **IBTDTCCommitConfirm** object returned by **IBTTransportBatch::Done** is always available when **BatchComplete** executes.</span></span> <span data-ttu-id="d3c50-173">ただし、 **BatchComplete**個別のメッセージング エンジン スレッドで前であってもに、呼び出すことができます**ibttransportbatch::done**を返します。</span><span class="sxs-lookup"><span data-stu-id="d3c50-173">However, **BatchComplete** can be called in a separate Messaging Engine thread, even before **IBTTransportBatch::Done** returns.</span></span> <span data-ttu-id="d3c50-174">可能であればをアダプターがアクセスしようとしたときに、 **IBTDTCCommitConfirm**オブジェクトの一部として、 **BatchComplete**実装では、アクセス違反があります。</span><span class="sxs-lookup"><span data-stu-id="d3c50-174">It is possible that when the adapter tries to access the **IBTDTCCommitConfirm** object as a part of the **BatchComplete** implementation, there is an access violation.</span></span>  
  
 <span data-ttu-id="d3c50-175">次の例ではイベントに問題が解決されます。</span><span class="sxs-lookup"><span data-stu-id="d3c50-175">The problem is solved with an event in the following example.</span></span> <span data-ttu-id="d3c50-176">この例では、イベントを使用するプロパティを通じてインターフェイス ポインターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="d3c50-176">Here the interface pointer is accessed through a property that uses the event.</span></span> <span data-ttu-id="d3c50-177">get は常に set を待機します。</span><span class="sxs-lookup"><span data-stu-id="d3c50-177">The get always waits for the set.</span></span>  
  
```  
protected IBTDTCCommitConfirm CommitConfirm  
{  
   set  
   {  
       this.commitConfirm = value;  
       this.commitConfirmEvent.Set();  
   }  
   get  
   {  
       this.commitConfirmEvent.WaitOne();  
       return this.commitConfirm;  
   }  
}  
protected IBTDTCCommitConfirm commitConfirm = null;  
private ManualResetEvent commitConfirmEvent = new ManualResetEvent(false);  
```  
  
 <span data-ttu-id="d3c50-178">戻り値を割り当てるようになりました**ibttransportbatch::done**にこのプロパティで使用して、 **BatchComplete**を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d3c50-178">Now assign the return value from **IBTTransportBatch::Done** to this property and use it in the **BatchComplete** call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3c50-179">参照</span><span class="sxs-lookup"><span data-stu-id="d3c50-179">See Also</span></span>  
 [<span data-ttu-id="d3c50-180">トランザクション メッセージ バッチ</span><span class="sxs-lookup"><span data-stu-id="d3c50-180">Transactional Message Batches</span></span>](../core/transactional-message-batches.md)