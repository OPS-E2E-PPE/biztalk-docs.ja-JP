---
title: トランザクションの処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d360742-e969-4651-b364-9edc6a93b8d4
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c82bb8077b1a89a979a658e4bd7cd9a61220f48
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980451"
---
# <a name="handling-transactions"></a><span data-ttu-id="e238f-102">トランザクションの処理</span><span class="sxs-lookup"><span data-stu-id="e238f-102">Handling Transactions</span></span>
## <a name="transacted-receivers"></a><span data-ttu-id="e238f-103">トランザクション受信元</span><span class="sxs-lookup"><span data-stu-id="e238f-103">Transacted Receivers</span></span>  
 <span data-ttu-id="e238f-104">トランザクション受信元とトランザクション以外の受信元との主な違いは、トランザクション受信元の場合、明示的な MSDTC トランザクションを作成および使用することにより、データ ソースと [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] メッセージ ボックス データベースの間の原子性が確保される点にあります。</span><span class="sxs-lookup"><span data-stu-id="e238f-104">The main difference between transacted receivers and nontransacted receivers is that transacted receivers create and use an explicit MSDTC transaction to ensure atomicity between their data source and the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MessageBox database.</span></span> <span data-ttu-id="e238f-105">一般に、アダプターのその他の側面はすべて同じです。</span><span class="sxs-lookup"><span data-stu-id="e238f-105">In general every other aspect of the adapter is the same.</span></span>  
  
 <span data-ttu-id="e238f-106">要求 - 応答の受信アダプターは、メッセージング エンジンに元の要求メッセージを送信するためにのみ、トランザクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="e238f-106">It should be noted that a request-response receive adapter only uses a transaction for submitting the original request message to the Messaging Engine.</span></span> <span data-ttu-id="e238f-107">メッセージング エンジンからアダプターに応答が送信されるためには、別のトランザクションが必要です。</span><span class="sxs-lookup"><span data-stu-id="e238f-107">A different transaction is needed for the transmission of the response sent from the Messaging Engine to the adapter.</span></span> <span data-ttu-id="e238f-108">これは、最初のトランザクションのスコープが、アダプターとメッセージ ボックス データベースの間であるためです。</span><span class="sxs-lookup"><span data-stu-id="e238f-108">This is because the scope of the first transaction is between the adapter and the MessageBox database.</span></span> <span data-ttu-id="e238f-109">元の要求メッセージのトランザクションがコミットされるまで、後続の要求メッセージは、メッセージング エンジンからアダプターに送信されません。</span><span class="sxs-lookup"><span data-stu-id="e238f-109">The subsequent request message is not sent to the adapter from the Messaging Engine until the transaction for the original request message commits.</span></span>  
  
 <span data-ttu-id="e238f-110">次のオブジェクト間の対話処理図に、受信メッセージのトランザクション送信時にアダプターとメッセージング エンジンが対話するようすを示します。</span><span class="sxs-lookup"><span data-stu-id="e238f-110">The following object interaction diagram illustrates the interaction between the adapter and the Messaging Engine during a transactional submission of incoming messages.</span></span> <span data-ttu-id="e238f-111">この例では、次の一連の対話が行われます。</span><span class="sxs-lookup"><span data-stu-id="e238f-111">In this example, the following sequence of interactions takes place:</span></span>  
  
1. <span data-ttu-id="e238f-112">アダプターが新しいバッチをエンジンから取得します。</span><span class="sxs-lookup"><span data-stu-id="e238f-112">The adapter gets a new batch from the engine.</span></span>  
  
2. <span data-ttu-id="e238f-113">アダプターが新しい MSDTC トランザクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="e238f-113">The adapter creates a new MSDTC transaction.</span></span>  
  
3. <span data-ttu-id="e238f-114">アダプターが、トランザクションに参加しているデータ ソースの破壊的な読み取りを行います。</span><span class="sxs-lookup"><span data-stu-id="e238f-114">The adapter does a destructive read from its data source that has been enlisted in the transaction.</span></span>  
  
4. <span data-ttu-id="e238f-115">アダプターがメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="e238f-115">The adapter submits the message.</span></span>  
  
5. <span data-ttu-id="e238f-116">アダプターが**完了**自身の MSDTC トランザクションを渡して、バッチに対して、その**BatchComplete**コールバック ポインター。</span><span class="sxs-lookup"><span data-stu-id="e238f-116">The adapter calls **Done** on the batch, passing in its MSDTC transaction and its **BatchComplete** callback pointer.</span></span> <span data-ttu-id="e238f-117">エンジンが返す、 **IBTDTCCommitConfirm**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="e238f-117">The engine returns an **IBTDTCCommitConfirm** interface.</span></span>  
  
6. <span data-ttu-id="e238f-118">エンジンは、バッチ処理、アダプターをコールバックにその**BatchComplete**実装し、そのメッセージをアダプターに処理の状態を伝達します。</span><span class="sxs-lookup"><span data-stu-id="e238f-118">The engine processes the batch, calls the adapter back on its **BatchComplete** implementation, and conveys the status of its message processing to the adapter.</span></span>  
  
7. <span data-ttu-id="e238f-119">バッチが成功した場合、アダプター コミット トランザクションと呼び出し、 **IBTDTCCommitConfirm.DTCCommitConfirm** API を`true`値がコミットを意味します。</span><span class="sxs-lookup"><span data-stu-id="e238f-119">If the batch was successful the adapter commits the transaction and calls the **IBTDTCCommitConfirm.DTCCommitConfirm** API with a `true` value signifying commit.</span></span>  
  
   <span data-ttu-id="e238f-120">![](../core/media/transactedreceiver.gif "TransactedReceiver")</span><span class="sxs-lookup"><span data-stu-id="e238f-120">![](../core/media/transactedreceiver.gif "TransactedReceiver")</span></span>  
  
## <a name="transacted-transmitters"></a><span data-ttu-id="e238f-121">トランザクション送信元</span><span class="sxs-lookup"><span data-stu-id="e238f-121">Transacted Transmitters</span></span>  
 <span data-ttu-id="e238f-122">トランザクション アダプターは、トランザクション以外のアダプターとほぼ同様です。</span><span class="sxs-lookup"><span data-stu-id="e238f-122">Transacted adapters are for the most part very similar to nontransacted adapters.</span></span> <span data-ttu-id="e238f-123">主な違いは、トランザクション アダプターの場合、メッセージ内のデータを、MSDTC トランザクションに参加しているリソースに送信する点です。</span><span class="sxs-lookup"><span data-stu-id="e238f-123">The main difference is that the transacted adapter sends the data in the message to a resource that it has enlisted in an MSDTC transaction.</span></span>  
  
 <span data-ttu-id="e238f-124">**実装のヒン ト:** のトランザクション送信は、アダプターで使用する同じ MSDTC トランザクションとを通じてそれを削除するため、変換先にデータを書き込むため、 **IBTTransportBatch.DeleteMessage**メソッドの呼び出し。</span><span class="sxs-lookup"><span data-stu-id="e238f-124">**Implementation Tip:** For transacted sends, the adapter should use the same MSDTC transaction for writing the data to the destination and for deleting it through the **IBTTransportBatch.DeleteMessage** method call.</span></span> <span data-ttu-id="e238f-125">トランザクションが行われる必要があるのは、この 2 つの操作だけです。</span><span class="sxs-lookup"><span data-stu-id="e238f-125">Only these two operations need to be transacted.</span></span> <span data-ttu-id="e238f-126">他の操作など**IBTTransportBatch.Resubmit**、 **IBTTransportBatch.MoveToNextTransport**、および**IBTTransportBatch.MoveToSuspendQ**にする必要はありませんトランザクション。</span><span class="sxs-lookup"><span data-stu-id="e238f-126">Any other operations, such as **IBTTransportBatch.Resubmit**, **IBTTransportBatch.MoveToNextTransport**, and **IBTTransportBatch.MoveToSuspendQ** do not need to be transacted.</span></span> <span data-ttu-id="e238f-127">これは、エンジンが暗黙的にトランザクションを使用し、これらの操作が送信先に対してアトミックである必要がないためです。</span><span class="sxs-lookup"><span data-stu-id="e238f-127">This is because the engine implicitly uses a transaction and these types of operations do not need to be atomic with respect to the destination.</span></span>  
  
 <span data-ttu-id="e238f-128">次のオブジェクト間の対話処理図に、アダプターとエンジンが対話するようすを示します。</span><span class="sxs-lookup"><span data-stu-id="e238f-128">The following object interaction diagram illustrates the interactions between the adapter and the engine.</span></span> <span data-ttu-id="e238f-129">イベントのシーケンスは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e238f-129">The sequence of events is as follows:</span></span>  
  
1. <span data-ttu-id="e238f-130">エンジンが新しいバッチをアダプターから取得します。</span><span class="sxs-lookup"><span data-stu-id="e238f-130">The engine gets a new batch from the adapter.</span></span>  
  
2. <span data-ttu-id="e238f-131">エンジンが 2 つのメッセージを新しいバッチに追加します。</span><span class="sxs-lookup"><span data-stu-id="e238f-131">The engine adds two messages to the new batch.</span></span>  
  
3. <span data-ttu-id="e238f-132">エンジンの呼び出し**完了**バッチの原因で、スレッド プールによって提供される内部送信キューにバッチを投稿するアダプター。</span><span class="sxs-lookup"><span data-stu-id="e238f-132">The engine calls **Done** on the batch, causing the adapter to post the batch to its internal transmit queue that is serviced by its thread pool.</span></span>  
  
4. <span data-ttu-id="e238f-133">アダプターが新しい MSDTC トランザクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="e238f-133">The adapter creates a new MSDTC transaction.</span></span>  
  
5. <span data-ttu-id="e238f-134">アダプターがメッセージを送信し、MSDTC トランザクションに送信先を参加させます。</span><span class="sxs-lookup"><span data-stu-id="e238f-134">The adapter transmits the messages enlisting the destination in the MSDTC transaction.</span></span> <span data-ttu-id="e238f-135">たとえば、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] データベースに書き込む場合もあります。</span><span class="sxs-lookup"><span data-stu-id="e238f-135">For example, this could be writing to a [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] database.</span></span>  
  
6. <span data-ttu-id="e238f-136">送信後に、アダプターが新しいバッチをエンジンから取得します。</span><span class="sxs-lookup"><span data-stu-id="e238f-136">After transmission, the adapter gets a new batch from the engine.</span></span>  
  
7. <span data-ttu-id="e238f-137">アダプターが**DeleteMessage**が正常に送信されているメッセージ。</span><span class="sxs-lookup"><span data-stu-id="e238f-137">The adapter calls **DeleteMessage** for the messages that it has successfully transmitted.</span></span>  
  
8. <span data-ttu-id="e238f-138">アダプターが**完了**自身の DTC トランザクションを渡して batch 上でします。</span><span class="sxs-lookup"><span data-stu-id="e238f-138">The adapter calls **Done** on the batch passing in its DTC transaction.</span></span> <span data-ttu-id="e238f-139">エンジンが返す、 **IBTDTCCommitConfirm**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="e238f-139">The engine returns an **IBTDTCCommitConfirm** interface.</span></span>  
  
9. <span data-ttu-id="e238f-140">エンジンがバッチを処理し、メッセージをアプリケーション キューから削除します。</span><span class="sxs-lookup"><span data-stu-id="e238f-140">The engine processes the batch, deleting the messages from the application queue.</span></span>  
  
10. <span data-ttu-id="e238f-141">エンジンはコールバックにアダプターの**IBTBatchCallback**削除操作の成功に関する情報を持つインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="e238f-141">The engine calls back the adapter's **IBTBatchCallback** interface with information on the success of its deletion operations.</span></span>  
  
11. <span data-ttu-id="e238f-142">バッチが成功した場合、アダプターがトランザクションをコミットします。</span><span class="sxs-lookup"><span data-stu-id="e238f-142">If the batch was successful, the adapter commits the transactions.</span></span>  
  
12. <span data-ttu-id="e238f-143">アダプターが**IBTDTCCommitConfirm.DTCCommitConfirm**トランザクションがコミットに成功したことをエンジンに通知するためにします。</span><span class="sxs-lookup"><span data-stu-id="e238f-143">The adapter calls **IBTDTCCommitConfirm.DTCCommitConfirm** to inform the engine that the transaction was successfully committed.</span></span>  
  
    <span data-ttu-id="e238f-144">![](../core/media/transactedtransmitter.gif "Transactedtransmitter")</span><span class="sxs-lookup"><span data-stu-id="e238f-144">![](../core/media/transactedtransmitter.gif "Transactedtransmitter")</span></span>  
  
### <a name="transacted-solicit-response-adapters"></a><span data-ttu-id="e238f-145">送信請求 - 応答のトランザクション アダプター</span><span class="sxs-lookup"><span data-stu-id="e238f-145">Transacted Solicit-Response Adapters</span></span>  
 <span data-ttu-id="e238f-146">双方向受信とは異なり、双方向送信は同じ DTC トランザクションを使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="e238f-146">Unlike two-way receives, two-way sends may be performed by using the same DTC transaction.</span></span> <span data-ttu-id="e238f-147">トランザクション送信請求-応答アダプターを使用する必要があります、同じ**IBTTransportBatch**の**SubmitResponseMessage**と**DeleteMessage**操作。</span><span class="sxs-lookup"><span data-stu-id="e238f-147">Transacted solicit-response adapters should use the same **IBTTransportBatch** for the **SubmitResponseMessage** and **DeleteMessage** operations.</span></span> <span data-ttu-id="e238f-148">このバッチは、送信請求 - 応答の組み合わせのメッセージの送受信時と同じ MSDTC トランザクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="e238f-148">This batch should use the same MSDTC transaction that is used to send and receive the solicit-response message pair.</span></span> <span data-ttu-id="e238f-149">これにより、送信請求 - 応答のメッセージ交換における原子性が確保されます。</span><span class="sxs-lookup"><span data-stu-id="e238f-149">This ensures atomicity for the solicit-response message exchange.</span></span>  
  
## <a name="service-components-and-byot"></a><span data-ttu-id="e238f-150">サービス コンポーネントと BYOT</span><span class="sxs-lookup"><span data-stu-id="e238f-150">Service Components and BYOT</span></span>  
 <span data-ttu-id="e238f-151">メッセージング エンジン API は、MSDTC トランザクションの提供を必要とします。</span><span class="sxs-lookup"><span data-stu-id="e238f-151">The Messaging Engine APIs require an MSDTC transaction to be supplied.</span></span> <span data-ttu-id="e238f-152">ただし、一部の .NET コンポーネントはサービス コンポーネントとして使用されるよう設計されており、プログラムによるトランザクションのコミットや中止を許可しません。</span><span class="sxs-lookup"><span data-stu-id="e238f-152">However some .NET components are designed to be used as serviced components and do not allow the transaction to be programmatically committed or aborted.</span></span> <span data-ttu-id="e238f-153">この場合、トランザクションは、そのプラットフォームの COM+ ランタイムによって自動的にコミットされます。</span><span class="sxs-lookup"><span data-stu-id="e238f-153">Instead, the transaction is automatically committed by the COM+ runtime on that platform.</span></span>  
  
 <span data-ttu-id="e238f-154">このようなシナリオでは、アダプターで BYOT (Bring Your Own Transaction) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e238f-154">For these scenarios, the adapter should use Bring Your Own Transaction (BYOT).</span></span> <span data-ttu-id="e238f-155">こうすると、アダプターによる MSDTC トランザクションの作成と、このトランザクションを使用する .NET コンポーネントのインスタンス化が可能となります。このコンポーネントは作成されたトランザクションを継承するため、トランザクションを独自に作成することはありません。</span><span class="sxs-lookup"><span data-stu-id="e238f-155">This allows the adapter to create an MSDTC transaction, instantiate the .NET component that uses the transaction, and allow that component to inherit the created transaction rather than create its own transaction.</span></span> <span data-ttu-id="e238f-156">.NET Framework には**System.EnterpriseServices.BYOT**この目的のためです。</span><span class="sxs-lookup"><span data-stu-id="e238f-156">The .NET Framework provides **System.EnterpriseServices.BYOT** for this purpose.</span></span> <span data-ttu-id="e238f-157">ヘルパー クラスを提供する SDK の BaseAdapter **BYOTTransaction**、この目的のためです。</span><span class="sxs-lookup"><span data-stu-id="e238f-157">The SDK BaseAdapter provides a helper class, **BYOTTransaction**, for this purpose.</span></span>  
  
## <a name="avoiding-race-conditions"></a><span data-ttu-id="e238f-158">競合状態の回避</span><span class="sxs-lookup"><span data-stu-id="e238f-158">Avoiding Race Conditions</span></span>  
 <span data-ttu-id="e238f-159">トランザクション オブジェクトを作成して [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に渡すアダプターを記述する場合、次の操作を実行するコードを記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e238f-159">When you write an adapter that creates a transaction object and hands it to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you are accepting responsibility for writing code that does the following:</span></span>  
  
- <span data-ttu-id="e238f-160">バッチに関連付けられているメッセージ内のエラーを解決する。</span><span class="sxs-lookup"><span data-stu-id="e238f-160">Resolves errors in messages associated with the batch.</span></span>  
  
- <span data-ttu-id="e238f-161">バッチ操作に関連付けられているトランザクションの最終結果を決定する。</span><span class="sxs-lookup"><span data-stu-id="e238f-161">Decides the final outcome of the transaction associated with the batch operation.</span></span>  
  
  <span data-ttu-id="e238f-162">アダプターは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にトランザクションの最終結果を知らせて内部の追跡データを維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e238f-162">The adapter must inform [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] about the final outcome of the transaction to maintain its internal tracking data.</span></span> <span data-ttu-id="e238f-163">通知[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]呼び出すことによって、結果の**DTCConfirmCommit**します。</span><span class="sxs-lookup"><span data-stu-id="e238f-163">The adapter informs [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] of the outcome by calling **DTCConfirmCommit**.</span></span> <span data-ttu-id="e238f-164">アダプターがこれを行わないと、重大なメモリ リークが発生します。</span><span class="sxs-lookup"><span data-stu-id="e238f-164">If the adapter does not do this, a significant memory leak occurs.</span></span>  
  
  <span data-ttu-id="e238f-165">上記の 2 つのタスク (エラーの解決と最終結果の決定) は単純に見えますが、実際には、これらのタスクは次に示す異なるスレッドの情報に基づいています。</span><span class="sxs-lookup"><span data-stu-id="e238f-165">The two tasks listed above (resolve errors and decide the final outcome) seem simple enough, but in fact they rely on information from different threads:</span></span>  
  
- <span data-ttu-id="e238f-166">アダプターによって渡された情報に基づいてエラーを処理する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を**BatchComplete**アダプターでのコールバック。</span><span class="sxs-lookup"><span data-stu-id="e238f-166">The adapter processes errors based on information passed by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to the **BatchComplete** callback in the adapter.</span></span> <span data-ttu-id="e238f-167">このコールバックはアダプターのスレッド上にあります。</span><span class="sxs-lookup"><span data-stu-id="e238f-167">This callback is on the adapter's thread.</span></span>  
  
- <span data-ttu-id="e238f-168">**DTCConfirmCommit**に、メソッドが、 **IBTDTCCommitConfirm**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="e238f-168">**DTCConfirmCommit** is a method on the **IBTDTCCommitConfirm** object.</span></span> <span data-ttu-id="e238f-169">インスタンス、 **IBTDTCCommitConfirm**オブジェクトは、batch によって返される**ibttransportbatch::done**呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e238f-169">An instance of the **IBTDTCCommitConfirm** object is returned by the batch **IBTTransportBatch::Done** call.</span></span> <span data-ttu-id="e238f-170">このインスタンスが同じスレッドでは、 **ibttransportbatch::done**呼び出すには、これは、アダプターのスレッドと異なる。</span><span class="sxs-lookup"><span data-stu-id="e238f-170">This instance is on the same thread as the **IBTTransportBatch::Done** call, which is different from the adapter's thread.</span></span>  
  
- <span data-ttu-id="e238f-171">アダプターがすべての呼び出しに対して**ibttransportbatch::done** 、対応するコールバックがある**BatchComplete**がの結果を報告する別のスレッドでメッセージング エンジンによって呼び出されますバッチ送信します。</span><span class="sxs-lookup"><span data-stu-id="e238f-171">For every call that the adapter makes to **IBTTransportBatch::Done** there is a corresponding callback, **BatchComplete**, that is called by the Messaging Engine in a separate thread to report the result of the batch submission.</span></span> <span data-ttu-id="e238f-172">**BatchComplete**アダプターのニーズをコミットまたはロールバック トランザクションかどうかに基づいて、バッチが成功または失敗します。</span><span class="sxs-lookup"><span data-stu-id="e238f-172">In **BatchComplete** the adapter needs to commit or roll back the transaction based on whether the batch passed or failed.</span></span> <span data-ttu-id="e238f-173">どちらの場合、アダプターは呼び出す必要がありますし、 **DTCConfirmCommit**メッセージング エンジンにトランザクションの状態を報告します。</span><span class="sxs-lookup"><span data-stu-id="e238f-173">In either case, the adapter should then call **DTCConfirmCommit** to report the status of the transaction to the Messaging Engine.</span></span>  
  
  <span data-ttu-id="e238f-174">競合状態が存在するためのアダプターの実装**BatchComplete**を想定できます、 **IBTDTCCommitConfirm**によって返されるオブジェクト**ibttransportbatch::done**は常に利用可能な場合に**BatchComplete**を実行します。</span><span class="sxs-lookup"><span data-stu-id="e238f-174">A possible race condition exists because the adapter’s implementation of **BatchComplete** can assume that the **IBTDTCCommitConfirm** object returned by **IBTTransportBatch::Done** is always available when **BatchComplete** executes.</span></span> <span data-ttu-id="e238f-175">ただし、 **BatchComplete**前であってもに、、別のメッセージング エンジン スレッドで呼び出すこと**ibttransportbatch::done**を返します。</span><span class="sxs-lookup"><span data-stu-id="e238f-175">However, **BatchComplete** can be called in a separate Messaging Engine thread, even before **IBTTransportBatch::Done** returns.</span></span> <span data-ttu-id="e238f-176">できるアダプターがアクセスしようとしたときに、 **IBTDTCCommitConfirm**オブジェクトの一部として、 **BatchComplete**実装では、アクセス違反があります。</span><span class="sxs-lookup"><span data-stu-id="e238f-176">It is possible that when the adapter tries to access the **IBTDTCCommitConfirm** object as a part of the **BatchComplete** implementation, there is an access violation.</span></span>  
  
  <span data-ttu-id="e238f-177">次の例では、内のイベントには、問題が解決します。</span><span class="sxs-lookup"><span data-stu-id="e238f-177">The problem is solved with an event in the following example.</span></span> <span data-ttu-id="e238f-178">この例では、イベントを使用するプロパティを通じてインターフェイス ポインターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="e238f-178">Here the interface pointer is accessed through a property that uses the event.</span></span> <span data-ttu-id="e238f-179">get は常に set を待機します。</span><span class="sxs-lookup"><span data-stu-id="e238f-179">The get always waits for the set.</span></span>  
  
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
  
 <span data-ttu-id="e238f-180">戻り値を割り当てるようになりました**ibttransportbatch::done**にこのプロパティでそれを使用して、 **BatchComplete**呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e238f-180">Now assign the return value from **IBTTransportBatch::Done** to this property and use it in the **BatchComplete** call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e238f-181">参照</span><span class="sxs-lookup"><span data-stu-id="e238f-181">See Also</span></span>  
 [<span data-ttu-id="e238f-182">トランザクション メッセージ バッチ</span><span class="sxs-lookup"><span data-stu-id="e238f-182">Transactional Message Batches</span></span>](../core/transactional-message-batches.md)