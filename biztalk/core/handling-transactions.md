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
ms.openlocfilehash: ea7601fdb2a11927cee0a9ffcbcb00b5c689e70b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387585"
---
# <a name="handling-transactions"></a><span data-ttu-id="7a21f-102">トランザクションの処理</span><span class="sxs-lookup"><span data-stu-id="7a21f-102">Handling Transactions</span></span>
## <a name="transacted-receivers"></a><span data-ttu-id="7a21f-103">トランザクション受信元</span><span class="sxs-lookup"><span data-stu-id="7a21f-103">Transacted Receivers</span></span>  
 <span data-ttu-id="7a21f-104">トランザクション受信元とトランザクション以外の受信の主な違いは、トランザクション受信元を作成し、明示的な MSDTC トランザクションを使用して、そのデータ ソース間の原子性が確保、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックス データベースです。</span><span class="sxs-lookup"><span data-stu-id="7a21f-104">The main difference between transacted receivers and nontransacted receivers is that transacted receivers create and use an explicit MSDTC transaction to ensure atomicity between their data source and the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MessageBox database.</span></span> <span data-ttu-id="7a21f-105">一般に、アダプターの他のすべての側面は、同じです。</span><span class="sxs-lookup"><span data-stu-id="7a21f-105">In general every other aspect of the adapter is the same.</span></span>  
  
 <span data-ttu-id="7a21f-106">要求-応答の受信に注意する必要がありますのみ、アダプターは、メッセージング エンジンに元の要求メッセージを送信するため、トランザクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="7a21f-106">It should be noted that a request-response receive adapter only uses a transaction for submitting the original request message to the Messaging Engine.</span></span> <span data-ttu-id="7a21f-107">メッセージング エンジンからアダプターに送信される応答を送信するためには、別のトランザクションが必要です。</span><span class="sxs-lookup"><span data-stu-id="7a21f-107">A different transaction is needed for the transmission of the response sent from the Messaging Engine to the adapter.</span></span> <span data-ttu-id="7a21f-108">これは、最初のトランザクションのスコープが、アダプターと、メッセージ ボックス データベース間にあるためです。</span><span class="sxs-lookup"><span data-stu-id="7a21f-108">This is because the scope of the first transaction is between the adapter and the MessageBox database.</span></span> <span data-ttu-id="7a21f-109">後続の要求メッセージは送信されません、アダプターにメッセージング エンジンから元の要求メッセージのトランザクションがコミットされるまで。</span><span class="sxs-lookup"><span data-stu-id="7a21f-109">The subsequent request message is not sent to the adapter from the Messaging Engine until the transaction for the original request message commits.</span></span>  
  
 <span data-ttu-id="7a21f-110">次のオブジェクト相互作用の図は、受信メッセージのトランザクション送信中に、アダプターとメッセージング エンジン間の相互作用を示しています。</span><span class="sxs-lookup"><span data-stu-id="7a21f-110">The following object interaction diagram illustrates the interaction between the adapter and the Messaging Engine during a transactional submission of incoming messages.</span></span> <span data-ttu-id="7a21f-111">この例では、次の一連の相互作用が行わをれます。</span><span class="sxs-lookup"><span data-stu-id="7a21f-111">In this example, the following sequence of interactions takes place:</span></span>  
  
1. <span data-ttu-id="7a21f-112">アダプターは、エンジンから新しいバッチを取得します。</span><span class="sxs-lookup"><span data-stu-id="7a21f-112">The adapter gets a new batch from the engine.</span></span>  
  
2. <span data-ttu-id="7a21f-113">アダプターは、新しい MSDTC トランザクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="7a21f-113">The adapter creates a new MSDTC transaction.</span></span>  
  
3. <span data-ttu-id="7a21f-114">アダプターは、そのトランザクションに参加しているデータ ソースからの破壊的な読み取りが。</span><span class="sxs-lookup"><span data-stu-id="7a21f-114">The adapter does a destructive read from its data source that has been enlisted in the transaction.</span></span>  
  
4. <span data-ttu-id="7a21f-115">アダプターは、メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="7a21f-115">The adapter submits the message.</span></span>  
  
5. <span data-ttu-id="7a21f-116">アダプターが**完了**自身の MSDTC トランザクションを渡して、バッチに対して、その**BatchComplete**コールバック ポインター。</span><span class="sxs-lookup"><span data-stu-id="7a21f-116">The adapter calls **Done** on the batch, passing in its MSDTC transaction and its **BatchComplete** callback pointer.</span></span> <span data-ttu-id="7a21f-117">エンジンが返す、 **IBTDTCCommitConfirm**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="7a21f-117">The engine returns an **IBTDTCCommitConfirm** interface.</span></span>  
  
6. <span data-ttu-id="7a21f-118">エンジンは、バッチ処理、アダプターをコールバックにその**BatchComplete**実装し、そのメッセージをアダプターに処理の状態を伝達します。</span><span class="sxs-lookup"><span data-stu-id="7a21f-118">The engine processes the batch, calls the adapter back on its **BatchComplete** implementation, and conveys the status of its message processing to the adapter.</span></span>  
  
7. <span data-ttu-id="7a21f-119">バッチが成功した場合、アダプター コミット トランザクションと呼び出し、 **IBTDTCCommitConfirm.DTCCommitConfirm** API を`true`値がコミットを意味します。</span><span class="sxs-lookup"><span data-stu-id="7a21f-119">If the batch was successful the adapter commits the transaction and calls the **IBTDTCCommitConfirm.DTCCommitConfirm** API with a `true` value signifying commit.</span></span>  
  
   <span data-ttu-id="7a21f-120">![](../core/media/transactedreceiver.gif "TransactedReceiver")</span><span class="sxs-lookup"><span data-stu-id="7a21f-120">![](../core/media/transactedreceiver.gif "TransactedReceiver")</span></span>  
  
## <a name="transacted-transmitters"></a><span data-ttu-id="7a21f-121">トランザクション送信元</span><span class="sxs-lookup"><span data-stu-id="7a21f-121">Transacted Transmitters</span></span>  
 <span data-ttu-id="7a21f-122">トランザクション アダプターは、ほとんどの場合、トランザクション以外のアダプターに非常に似ています。</span><span class="sxs-lookup"><span data-stu-id="7a21f-122">Transacted adapters are for the most part very similar to nontransacted adapters.</span></span> <span data-ttu-id="7a21f-123">主な違いは、トランザクション アダプターが、MSDTC トランザクションに参加しているリソースにメッセージのデータを送信します。</span><span class="sxs-lookup"><span data-stu-id="7a21f-123">The main difference is that the transacted adapter sends the data in the message to a resource that it has enlisted in an MSDTC transaction.</span></span>  
  
 <span data-ttu-id="7a21f-124">**実装のヒン ト:** トランザクションの送信のアダプターで使用する同じ MSDTC トランザクションとを通じてそれを削除するため、変換先にデータを書き込むため、 **IBTTransportBatch.DeleteMessage**メソッドの呼び出し。</span><span class="sxs-lookup"><span data-stu-id="7a21f-124">**Implementation Tip:** For transacted sends, the adapter should use the same MSDTC transaction for writing the data to the destination and for deleting it through the **IBTTransportBatch.DeleteMessage** method call.</span></span> <span data-ttu-id="7a21f-125">これら 2 つの操作だけでは、トランザクションが行われる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a21f-125">Only these two operations need to be transacted.</span></span> <span data-ttu-id="7a21f-126">他の操作など**IBTTransportBatch.Resubmit**、 **IBTTransportBatch.MoveToNextTransport**、および**IBTTransportBatch.MoveToSuspendQ**にする必要はありませんトランザクション。</span><span class="sxs-lookup"><span data-stu-id="7a21f-126">Any other operations, such as **IBTTransportBatch.Resubmit**, **IBTTransportBatch.MoveToNextTransport**, and **IBTTransportBatch.MoveToSuspendQ** do not need to be transacted.</span></span> <span data-ttu-id="7a21f-127">これは、エンジンが暗黙的にトランザクションを使用し、これらの種類の操作は、送信先に対してアトミックである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7a21f-127">This is because the engine implicitly uses a transaction and these types of operations do not need to be atomic with respect to the destination.</span></span>  
  
 <span data-ttu-id="7a21f-128">次のオブジェクト相互作用の図は、アダプターとエンジン間の相互作用を示しています。</span><span class="sxs-lookup"><span data-stu-id="7a21f-128">The following object interaction diagram illustrates the interactions between the adapter and the engine.</span></span> <span data-ttu-id="7a21f-129">イベントの順序は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7a21f-129">The sequence of events is as follows:</span></span>  
  
1. <span data-ttu-id="7a21f-130">エンジンは、アダプターから新しいバッチを取得します。</span><span class="sxs-lookup"><span data-stu-id="7a21f-130">The engine gets a new batch from the adapter.</span></span>  
  
2. <span data-ttu-id="7a21f-131">エンジンは、新しいバッチに 2 つのメッセージを追加します。</span><span class="sxs-lookup"><span data-stu-id="7a21f-131">The engine adds two messages to the new batch.</span></span>  
  
3. <span data-ttu-id="7a21f-132">エンジンの呼び出し**完了**バッチの原因で、スレッド プールによって提供される内部送信キューにバッチを投稿するアダプター。</span><span class="sxs-lookup"><span data-stu-id="7a21f-132">The engine calls **Done** on the batch, causing the adapter to post the batch to its internal transmit queue that is serviced by its thread pool.</span></span>  
  
4. <span data-ttu-id="7a21f-133">アダプターは、新しい MSDTC トランザクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="7a21f-133">The adapter creates a new MSDTC transaction.</span></span>  
  
5. <span data-ttu-id="7a21f-134">アダプターが送信メッセージの送信先を MSDTC トランザクションに参加させます。</span><span class="sxs-lookup"><span data-stu-id="7a21f-134">The adapter transmits the messages enlisting the destination in the MSDTC transaction.</span></span> <span data-ttu-id="7a21f-135">たとえば、このでしたに書き込む場合、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース。</span><span class="sxs-lookup"><span data-stu-id="7a21f-135">For example, this could be writing to a [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] database.</span></span>  
  
6. <span data-ttu-id="7a21f-136">送信後に、アダプターは、新しいバッチをエンジンから取得します。</span><span class="sxs-lookup"><span data-stu-id="7a21f-136">After transmission, the adapter gets a new batch from the engine.</span></span>  
  
7. <span data-ttu-id="7a21f-137">アダプターが**DeleteMessage**が正常に送信されているメッセージ。</span><span class="sxs-lookup"><span data-stu-id="7a21f-137">The adapter calls **DeleteMessage** for the messages that it has successfully transmitted.</span></span>  
  
8. <span data-ttu-id="7a21f-138">アダプターが**完了**自身の DTC トランザクションを渡して batch 上でします。</span><span class="sxs-lookup"><span data-stu-id="7a21f-138">The adapter calls **Done** on the batch passing in its DTC transaction.</span></span> <span data-ttu-id="7a21f-139">エンジンが返す、 **IBTDTCCommitConfirm**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="7a21f-139">The engine returns an **IBTDTCCommitConfirm** interface.</span></span>  
  
9. <span data-ttu-id="7a21f-140">エンジンは、アプリケーション キューからメッセージを削除するバッチを処理します。</span><span class="sxs-lookup"><span data-stu-id="7a21f-140">The engine processes the batch, deleting the messages from the application queue.</span></span>  
  
10. <span data-ttu-id="7a21f-141">エンジンはコールバックにアダプターの**IBTBatchCallback**削除操作の成功に関する情報を持つインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="7a21f-141">The engine calls back the adapter's **IBTBatchCallback** interface with information on the success of its deletion operations.</span></span>  
  
11. <span data-ttu-id="7a21f-142">バッチが成功した場合、アダプターは、トランザクションをコミットします。</span><span class="sxs-lookup"><span data-stu-id="7a21f-142">If the batch was successful, the adapter commits the transactions.</span></span>  
  
12. <span data-ttu-id="7a21f-143">アダプターが**IBTDTCCommitConfirm.DTCCommitConfirm**トランザクションがコミットに成功したことをエンジンに通知するためにします。</span><span class="sxs-lookup"><span data-stu-id="7a21f-143">The adapter calls **IBTDTCCommitConfirm.DTCCommitConfirm** to inform the engine that the transaction was successfully committed.</span></span>  
  
    <span data-ttu-id="7a21f-144">![](../core/media/transactedtransmitter.gif "Transactedtransmitter")</span><span class="sxs-lookup"><span data-stu-id="7a21f-144">![](../core/media/transactedtransmitter.gif "Transactedtransmitter")</span></span>  
  
### <a name="transacted-solicit-response-adapters"></a><span data-ttu-id="7a21f-145">トランザクション送信請求-応答アダプター</span><span class="sxs-lookup"><span data-stu-id="7a21f-145">Transacted Solicit-Response Adapters</span></span>  
 <span data-ttu-id="7a21f-146">異なり、双方向受信、双方向の送信は同じ DTC トランザクションを使用して実行する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7a21f-146">Unlike two-way receives, two-way sends may be performed by using the same DTC transaction.</span></span> <span data-ttu-id="7a21f-147">トランザクション送信請求-応答アダプターを使用する必要があります、同じ**IBTTransportBatch**の**SubmitResponseMessage**と**DeleteMessage**操作。</span><span class="sxs-lookup"><span data-stu-id="7a21f-147">Transacted solicit-response adapters should use the same **IBTTransportBatch** for the **SubmitResponseMessage** and **DeleteMessage** operations.</span></span> <span data-ttu-id="7a21f-148">このバッチには、送信請求-応答の組み合わせのメッセージの送受信に使用される同じ MSDTC トランザクションを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a21f-148">This batch should use the same MSDTC transaction that is used to send and receive the solicit-response message pair.</span></span> <span data-ttu-id="7a21f-149">これにより、送信請求-応答のメッセージ交換の原子性です。</span><span class="sxs-lookup"><span data-stu-id="7a21f-149">This ensures atomicity for the solicit-response message exchange.</span></span>  
  
## <a name="service-components-and-byot"></a><span data-ttu-id="7a21f-150">サービス コンポーネントと BYOT</span><span class="sxs-lookup"><span data-stu-id="7a21f-150">Service Components and BYOT</span></span>  
 <span data-ttu-id="7a21f-151">メッセージング エンジン Api では、MSDTC トランザクションに指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a21f-151">The Messaging Engine APIs require an MSDTC transaction to be supplied.</span></span> <span data-ttu-id="7a21f-152">ただし一部の .NET コンポーネントは、サービス コンポーネントとして使用するように設計されてし、トランザクションのコミットまたは中止するプログラムを使用できないようにします。</span><span class="sxs-lookup"><span data-stu-id="7a21f-152">However some .NET components are designed to be used as serviced components and do not allow the transaction to be programmatically committed or aborted.</span></span> <span data-ttu-id="7a21f-153">代わりに、そのプラットフォームで COM + ランタイムによって、トランザクションを自動的にコミットします。</span><span class="sxs-lookup"><span data-stu-id="7a21f-153">Instead, the transaction is automatically committed by the COM+ runtime on that platform.</span></span>  
  
 <span data-ttu-id="7a21f-154">これらのシナリオについて、アダプターは、Bring Your Own トランザクション BYOT () を使用してください。</span><span class="sxs-lookup"><span data-stu-id="7a21f-154">For these scenarios, the adapter should use Bring Your Own Transaction (BYOT).</span></span> <span data-ttu-id="7a21f-155">これにより、アダプターは MSDTC トランザクションを作成、トランザクションを使用する .NET コンポーネントをインスタンス化し、独自のトランザクションを作成するのではなく、作成されたトランザクションを継承するには、そのコンポーネントを許可できます。</span><span class="sxs-lookup"><span data-stu-id="7a21f-155">This allows the adapter to create an MSDTC transaction, instantiate the .NET component that uses the transaction, and allow that component to inherit the created transaction rather than create its own transaction.</span></span> <span data-ttu-id="7a21f-156">.NET Framework には**System.EnterpriseServices.BYOT**この目的のためです。</span><span class="sxs-lookup"><span data-stu-id="7a21f-156">The .NET Framework provides **System.EnterpriseServices.BYOT** for this purpose.</span></span> <span data-ttu-id="7a21f-157">ヘルパー クラスを提供する SDK の BaseAdapter **BYOTTransaction**、この目的のためです。</span><span class="sxs-lookup"><span data-stu-id="7a21f-157">The SDK BaseAdapter provides a helper class, **BYOTTransaction**, for this purpose.</span></span>  
  
## <a name="avoiding-race-conditions"></a><span data-ttu-id="7a21f-158">競合状態の回避</span><span class="sxs-lookup"><span data-stu-id="7a21f-158">Avoiding Race Conditions</span></span>  
 <span data-ttu-id="7a21f-159">トランザクション オブジェクトを作成しに渡すアダプターを記述するとき[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、実行すると、次のコードの記述を担当することになります。</span><span class="sxs-lookup"><span data-stu-id="7a21f-159">When you write an adapter that creates a transaction object and hands it to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you are accepting responsibility for writing code that does the following:</span></span>  
  
- <span data-ttu-id="7a21f-160">バッチに関連付けられているメッセージ内のエラーを解決します。</span><span class="sxs-lookup"><span data-stu-id="7a21f-160">Resolves errors in messages associated with the batch.</span></span>  
  
- <span data-ttu-id="7a21f-161">バッチ操作に関連付けられたトランザクションの最終結果を決定します。</span><span class="sxs-lookup"><span data-stu-id="7a21f-161">Decides the final outcome of the transaction associated with the batch operation.</span></span>  
  
  <span data-ttu-id="7a21f-162">アダプターに通知する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の内部で維持するために、トランザクションの最終的な結果に関するデータを追跡します。</span><span class="sxs-lookup"><span data-stu-id="7a21f-162">The adapter must inform [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] about the final outcome of the transaction to maintain its internal tracking data.</span></span> <span data-ttu-id="7a21f-163">通知[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]呼び出すことによって、結果の**DTCConfirmCommit**します。</span><span class="sxs-lookup"><span data-stu-id="7a21f-163">The adapter informs [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] of the outcome by calling **DTCConfirmCommit**.</span></span> <span data-ttu-id="7a21f-164">アダプターがこれにもいない場合は、大量のメモリ リークが発生します。</span><span class="sxs-lookup"><span data-stu-id="7a21f-164">If the adapter does not do this, a significant memory leak occurs.</span></span>  
  
  <span data-ttu-id="7a21f-165">上記 2 つのタスク (エラーの解決し、最終結果の決定) が、単純に見えますが、実際に別のスレッドからの情報に依存します。</span><span class="sxs-lookup"><span data-stu-id="7a21f-165">The two tasks listed above (resolve errors and decide the final outcome) seem simple enough, but in fact they rely on information from different threads:</span></span>  
  
- <span data-ttu-id="7a21f-166">アダプターによって渡された情報に基づいてエラーを処理する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を**BatchComplete**アダプターでのコールバック。</span><span class="sxs-lookup"><span data-stu-id="7a21f-166">The adapter processes errors based on information passed by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to the **BatchComplete** callback in the adapter.</span></span> <span data-ttu-id="7a21f-167">このコールバックはアダプターのスレッドでは。</span><span class="sxs-lookup"><span data-stu-id="7a21f-167">This callback is on the adapter's thread.</span></span>  
  
- <span data-ttu-id="7a21f-168">**DTCConfirmCommit**に、メソッドが、 **IBTDTCCommitConfirm**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="7a21f-168">**DTCConfirmCommit** is a method on the **IBTDTCCommitConfirm** object.</span></span> <span data-ttu-id="7a21f-169">インスタンス、 **IBTDTCCommitConfirm**オブジェクトは、batch によって返される**ibttransportbatch::done**呼び出します。</span><span class="sxs-lookup"><span data-stu-id="7a21f-169">An instance of the **IBTDTCCommitConfirm** object is returned by the batch **IBTTransportBatch::Done** call.</span></span> <span data-ttu-id="7a21f-170">このインスタンスが同じスレッドでは、 **ibttransportbatch::done**呼び出すには、これは、アダプターのスレッドと異なる。</span><span class="sxs-lookup"><span data-stu-id="7a21f-170">This instance is on the same thread as the **IBTTransportBatch::Done** call, which is different from the adapter's thread.</span></span>  
  
- <span data-ttu-id="7a21f-171">アダプターがすべての呼び出しに対して**ibttransportbatch::done** 、対応するコールバックがある**BatchComplete**がの結果を報告する別のスレッドでメッセージング エンジンによって呼び出されますバッチ送信します。</span><span class="sxs-lookup"><span data-stu-id="7a21f-171">For every call that the adapter makes to **IBTTransportBatch::Done** there is a corresponding callback, **BatchComplete**, that is called by the Messaging Engine in a separate thread to report the result of the batch submission.</span></span> <span data-ttu-id="7a21f-172">**BatchComplete**アダプターのニーズをコミットまたはロールバック トランザクションかどうかに基づいて、バッチが成功または失敗します。</span><span class="sxs-lookup"><span data-stu-id="7a21f-172">In **BatchComplete** the adapter needs to commit or roll back the transaction based on whether the batch passed or failed.</span></span> <span data-ttu-id="7a21f-173">どちらの場合、アダプターは呼び出す必要がありますし、 **DTCConfirmCommit**メッセージング エンジンにトランザクションの状態を報告します。</span><span class="sxs-lookup"><span data-stu-id="7a21f-173">In either case, the adapter should then call **DTCConfirmCommit** to report the status of the transaction to the Messaging Engine.</span></span>  
  
  <span data-ttu-id="7a21f-174">競合状態が存在するためのアダプターの実装**BatchComplete**を想定できます、 **IBTDTCCommitConfirm**によって返されるオブジェクト**ibttransportbatch::done**は常に利用可能な場合に**BatchComplete**を実行します。</span><span class="sxs-lookup"><span data-stu-id="7a21f-174">A possible race condition exists because the adapter’s implementation of **BatchComplete** can assume that the **IBTDTCCommitConfirm** object returned by **IBTTransportBatch::Done** is always available when **BatchComplete** executes.</span></span> <span data-ttu-id="7a21f-175">ただし、 **BatchComplete**前であってもに、、別のメッセージング エンジン スレッドで呼び出すこと**ibttransportbatch::done**を返します。</span><span class="sxs-lookup"><span data-stu-id="7a21f-175">However, **BatchComplete** can be called in a separate Messaging Engine thread, even before **IBTTransportBatch::Done** returns.</span></span> <span data-ttu-id="7a21f-176">できるアダプターがアクセスしようとしたときに、 **IBTDTCCommitConfirm**オブジェクトの一部として、 **BatchComplete**実装では、アクセス違反があります。</span><span class="sxs-lookup"><span data-stu-id="7a21f-176">It is possible that when the adapter tries to access the **IBTDTCCommitConfirm** object as a part of the **BatchComplete** implementation, there is an access violation.</span></span>  
  
  <span data-ttu-id="7a21f-177">次の例では、内のイベントには、問題が解決します。</span><span class="sxs-lookup"><span data-stu-id="7a21f-177">The problem is solved with an event in the following example.</span></span> <span data-ttu-id="7a21f-178">ここでインターフェイス ポインターは、イベントを使用するプロパティを通じてアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="7a21f-178">Here the interface pointer is accessed through a property that uses the event.</span></span> <span data-ttu-id="7a21f-179">Get では、セットが常に待機します。</span><span class="sxs-lookup"><span data-stu-id="7a21f-179">The get always waits for the set.</span></span>  
  
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
  
 <span data-ttu-id="7a21f-180">戻り値を割り当てるようになりました**ibttransportbatch::done**にこのプロパティでそれを使用して、 **BatchComplete**呼び出します。</span><span class="sxs-lookup"><span data-stu-id="7a21f-180">Now assign the return value from **IBTTransportBatch::Done** to this property and use it in the **BatchComplete** call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a21f-181">参照</span><span class="sxs-lookup"><span data-stu-id="7a21f-181">See Also</span></span>  
 [<span data-ttu-id="7a21f-182">トランザクション メッセージ バッチ</span><span class="sxs-lookup"><span data-stu-id="7a21f-182">Transactional Message Batches</span></span>](../core/transactional-message-batches.md)