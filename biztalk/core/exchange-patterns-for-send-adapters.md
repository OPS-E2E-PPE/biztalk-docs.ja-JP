---
title: 送信アダプターの交換パターン |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ad65fb5-640d-4bd2-aabe-946210f58a22
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 997aaa9a92f90f30bdaaeb59cc9cecb0c454496f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248354"
---
# <a name="exchange-patterns-for-send-adapters"></a><span data-ttu-id="7fb1b-102">送信アダプターの交換パターン</span><span class="sxs-lookup"><span data-stu-id="7fb1b-102">Exchange Patterns for Send Adapters</span></span>
<span data-ttu-id="7fb1b-103">送信アダプターには、BizTalk メッセージング エンジンから、回線で送信されるメッセージが配信されます。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-103">Send adapters are delivered messages from the BizTalk Messaging Engine to be transmitted over the wire.</span></span> <span data-ttu-id="7fb1b-104">配信されたメッセージは、一方向または双方向のメッセージ交換パターンを使用して送信される場合があります。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-104">These messages may be sent by using a one-way or two-way message exchange pattern.</span></span> <span data-ttu-id="7fb1b-105">この双方向のメッセージ交換パターンを処理するアダプターを送信請求 - 応答アダプターと呼びます。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-105">An adapter that handles this two-way message exchange pattern is called a Solicit-Response adapter.</span></span>  
  
## <a name="blocking-vs-non-blocking-transmissions"></a><span data-ttu-id="7fb1b-106">Vs をブロックしています。非ブロッキング送信</span><span class="sxs-lookup"><span data-stu-id="7fb1b-106">Blocking vs. Non-Blocking Transmissions</span></span>  
 <span data-ttu-id="7fb1b-107">メッセージング エンジンでは、送信アダプターにメッセージを配信するかを使用して、 **IBTTransmitter.TransmitMessage**メソッドまたは**IBTTransmitterBatch.TransmitMessage**かどうかに応じて、メソッドアダプターはバッチ対応です。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-107">The Messaging Engine delivers messages to the send adapter by using either the **IBTTransmitter.TransmitMessage** method or the **IBTTransmitterBatch.TransmitMessage** method, depending on whether the adapter is batch-aware.</span></span> <span data-ttu-id="7fb1b-108">どちらのメソッドにも、アダプターがメッセージを送信した方法を示すブール値が返されます。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-108">Both versions of the method have a Boolean return value that indicates how the adapter transmitted the message.</span></span> <span data-ttu-id="7fb1b-109">アダプターが `true` を返した場合、メッセージの送信が既に完了していることを示しています。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-109">If the adapter returns `true`, it has completely sent the message before returning.</span></span> <span data-ttu-id="7fb1b-110">この場合、アダプターの代わりにメッセージング エンジンによってメッセージ ボックス データベースからメッセージが削除されます。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-110">In this case the Messaging Engine deletes the message from the MessageBox database on behalf of the adapter.</span></span> <span data-ttu-id="7fb1b-111">アダプターが `false` を返した場合、メッセージの送信は開始されていますが、まだ送信が完了していないことを示します。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-111">If the adapter returns `false`, it started message transmission and returned before the transmission completed.</span></span> <span data-ttu-id="7fb1b-112">この場合、アダプターはアプリケーション キューからメッセージを削除するだけでなく、メッセージの再送信または保留の試行が必要になる送信エラーも処理します。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-112">In this case, the adapter is responsible not only for deleting the message from its application queue but also for handling transmission failures that require the message to be retried for transmission or suspended.</span></span>  
  
 <span data-ttu-id="7fb1b-113">返すアダプター`false`つまり、非ブロッキング呼び出しには、 **TransmitMessage**実装コードは、メッセージング エンジンの呼び出し元のスレッドをブロックしません。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-113">The adapter returning `false` is a nonblocking call, meaning that the **TransmitMessage** implementation code does not block the calling thread of the Messaging Engine.</span></span> <span data-ttu-id="7fb1b-114">アダプターは、送信準備が完了したインメモリ キューにメッセージを追加し、その後、値を返すだけです。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-114">The adapter simply adds the message to an in-memory queue ready to be transmitted and then returns.</span></span> <span data-ttu-id="7fb1b-115">このアダプターには、インメモリ キューの提供とメッセージの送信を行い、その後にエンジンに対して送信結果を通知する独自のスレッド プールが必要です。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-115">The adapter should have its own thread pool that services the in-memory queue, transmits the message, and then notifies the engine of the outcome of the transmission.</span></span>  
  
 <span data-ttu-id="7fb1b-116">通常、メッセージング エンジンのスレッドの方が、回線でのデータ送信に使用されるスレッドよりも CPU の制約を受けます。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-116">The Messaging Engine’s threads are typically more CPU bound than the threads used to send data over the wire.</span></span> <span data-ttu-id="7fb1b-117">この 2 種類のスレッドを混合して使用すると、パフォーマンスに悪影響を及ぼします。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-117">Mixing these two types of threads has a negative impact on performance.</span></span> <span data-ttu-id="7fb1b-118">非ブロッキング送信を使用すると 2 種類のスレッドを切り離せるので、ブロッキング呼び出しのパフォーマンスを大幅に向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-118">Non-blocking sends enable the decoupling of these two types of threads and yield a significant performance improvement over blocking calls.</span></span>  
  
 <span data-ttu-id="7fb1b-119">I/O 操作の制約を受ける傾向があるアダプターのスレッド プールを次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-119">The following diagram shows the adapter's thread pool which can tend to be bound by I/O operations.</span></span> <span data-ttu-id="7fb1b-120">BizTalk Server メッセージング エンジンのスレッド プールの方が CPU 処理の制約を受けます。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-120">The BizTalk Server Messaging Engine's thread pool is more bound by the CPU processing.</span></span> <span data-ttu-id="7fb1b-121">2 種類のスレッド プールを保持し、同じ種類のスレッドを混合しないことによって、システムのパフォーマンスをこれまでよりも向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-121">By keeping two different thread pools and not mixing the same type of threads the system can operate more efficiently.</span></span>  
  
 ![](../core/media/io-cpu-bound-threadpools.gif "Io_cpu_bound_threadpools")  
  
 <span data-ttu-id="7fb1b-122">**パフォーマンス ヒント:** 最適なパフォーマンスを送信アダプターする必要が非ブロッキングとバッチに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-122">**Performance Tip:** For the best performance, send adapters should be nonblocking and batch aware.</span></span> <span data-ttu-id="7fb1b-123">BizTalk ファイル アダプターをブロッキング呼び出しを行うバッチ非対応から、非ブロッキング呼び出しを行うバッチ対応に変更すると、パフォーマンスが 3 倍向上します。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-123">When the BizTalk File adapter was changed from blocking and non-batch aware to nonblocking and batch aware, a threefold performance gain was realized.</span></span>  
  
 <span data-ttu-id="7fb1b-124">**トラブルシューティングのヒント:** ブロッキング送信ホスト インスタンス全体のパフォーマンスの低下が発生することができます。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-124">**Troubleshooting Tip:** Blocking transmits can cause a performance degradation of an entire host instance.</span></span> <span data-ttu-id="7fb1b-125">場合、アダプターはで過度のブロッキング**TransmitMessage**エンジンのスレッドから他のアダプターにメッセージを配信できなくなります。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-125">If the adapter does excessive blocking in **TransmitMessage** it will prevent engine threads from delivering messages to other adapters.</span></span>  
  
## <a name="non-batched-sends"></a><span data-ttu-id="7fb1b-126">バッチ化されていない送信</span><span class="sxs-lookup"><span data-stu-id="7fb1b-126">Non-Batched Sends</span></span>  
 <span data-ttu-id="7fb1b-127">バッチ対応アダプターを実装する必要があります**IBTTransmitter**詳しく説明したよう[非同期送信アダプター用のインターフェイス](../core/interfaces-for-an-asynchronous-send-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-127">Adapters that are not batch aware should implement **IBTTransmitter** as detailed in [Interfaces for an Asynchronous Send Adapter](../core/interfaces-for-an-asynchronous-send-adapter.md).</span></span> <span data-ttu-id="7fb1b-128">アダプターがメッセージング エンジンに送信する必要がある各メッセージの呼び出しに対する**IBTTransmitter.TransmitMessage**です。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-128">For each message that the adapter needs to transmit the Messaging Engine calls **IBTTransmitter.TransmitMessage**.</span></span> <span data-ttu-id="7fb1b-129">次のオブジェクト間の対話処理図は、一般的なメッセージの送信方法の詳細について示しています。その方法は、次に示す手順で構成されています。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-129">The object interaction diagram below details the typical approach for transmitting messages, which consists of the following steps:</span></span>  
  
1.  <span data-ttu-id="7fb1b-130">エンジンがメッセージをアダプターに配信します。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-130">The engine delivers the message to the adapter.</span></span>  
  
2.  <span data-ttu-id="7fb1b-131">アダプターが、送信準備のできているインメモリ キューにメッセージを追加します。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-131">The adapter enqueues the message to an in-memory queue ready to be transmitted.</span></span>  
  
3.  <span data-ttu-id="7fb1b-132">アダプターのスレッド プールのスレッドが、キューからメッセージを取り出し、メッセージの構成を読み取って回線でメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-132">A thread from the adapter's thread pool dequeues the message from the queue, reads the configuration for the message, and transmits the message over the wire.</span></span>  
  
4.  <span data-ttu-id="7fb1b-133">アダプターが新しいバッチをエンジンから取得します。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-133">The adapter gets a new batch from the engine.</span></span>  
  
5.  <span data-ttu-id="7fb1b-134">アダプターが**DeleteMessage**だけが送信されるメッセージを渡して、バッチにします。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-134">The adapter calls **DeleteMessage** on the batch, passing in the message that it has just transmitted.</span></span>  
  
6.  <span data-ttu-id="7fb1b-135">アダプターが**完了**バッチにします。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-135">The adapter calls **Done** on the batch.</span></span>  
  
7.  <span data-ttu-id="7fb1b-136">エンジンは、バッチを処理し、アプリケーション キューからメッセージを削除します。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-136">The engine processes the batch and deletes the message from the application queue.</span></span>  
  
8.  <span data-ttu-id="7fb1b-137">エンジンはコールバックにアダプターの結果を通知する、 **DeleteMessage**操作します。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-137">The engine calls back the adapter to notify it of the outcome of the **DeleteMessage** operation.</span></span>  
  
 ![](../core/media/deleting-from-message-queue.gif "Deleting_from_message_queue")  
  
 <span data-ttu-id="7fb1b-138">上記のオブジェクト間の対話処理図は、1 通のメッセージをアプリケーション キューから削除するアダプターを示しています。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-138">The preceding object interaction diagram shows the adapter deleting a single message from the application queue.</span></span> <span data-ttu-id="7fb1b-139">ただし、一度に 1 通のメッセージを操作するのではなく、すべてのメッセージ操作をアダプターでバッチにするのが理想的です。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-139">Ideally the adapter batches up message operations as opposed to operating on a single message at a time.</span></span>  
  
## <a name="batched-sends"></a><span data-ttu-id="7fb1b-140">バッチ化された送信</span><span class="sxs-lookup"><span data-stu-id="7fb1b-140">Batched Sends</span></span>  
 <span data-ttu-id="7fb1b-141">バッチ対応であるアダプターを実装する必要があります**IBTBatchTransmitter**と**IBTTransmitterBatch**詳しく説明したよう[送信アダプター用のインターフェイス](../core/interfaces-for-send-adapters.md)です。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-141">Adapters that are batch aware should implement **IBTBatchTransmitter** and **IBTTransmitterBatch** as detailed in [Interfaces for Send Adapters](../core/interfaces-for-send-adapters.md).</span></span> <span data-ttu-id="7fb1b-142">エンジンが、呼び出すことによってアダプターから新しいバッチを取得、エンジンがメッセージを送信するアダプターの場合、 **IBTBatchTransmitter.GetBatch**です。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-142">When the engine has messages for the adapter to transmit, the engine gets a new batch from the adapter by calling **IBTBatchTransmitter.GetBatch**.</span></span> <span data-ttu-id="7fb1b-143">アダプターを実装する新しいバッチ オブジェクトを返します**IBTTransmitterBatch**です。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-143">The adapter returns a new batch object that implements **IBTTransmitterBatch**.</span></span> <span data-ttu-id="7fb1b-144">エンジンを呼び出してバッチを開始し**IBTTransmitterBatch.BeginBatch**です。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-144">The engine then starts the batch by calling **IBTTransmitterBatch.BeginBatch**.</span></span> <span data-ttu-id="7fb1b-145">この API には、アダプターがバッチで受け入れるメッセージの最大数をアダプターで指定することができる出力パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-145">This API has an out parameter that allows the adapter to specify the maximum number of messages that it will accept on the batch.</span></span> <span data-ttu-id="7fb1b-146">アダプターは、任意に DTC トランザクションを返すことがあります。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-146">The adapter may optionally return a DTC transaction.</span></span> <span data-ttu-id="7fb1b-147">エンジンが呼び出す、 **IBTTransmitterBatch.TransmitMessage**バッチに追加する送信メッセージごとに 1 回です。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-147">The engine then calls **IBTTransmitterBatch.TransmitMessage** once for each outgoing message to be added to the batch.</span></span> <span data-ttu-id="7fb1b-148">その呼び出し回数は、0 より大きく、かつ、アダプターで指定されたバッチの最大サイズ以下です。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-148">The number of times this is called is greater than zero but less than or equal to the maximum size of the batch as indicated by the adapter.</span></span> <span data-ttu-id="7fb1b-149">アダプターが呼び出すすべてのメッセージがバッチに追加したら、 **IBTTransmitterBatch.Done**です。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-149">When all the messages have been added to the batch, the adapter calls **IBTTransmitterBatch.Done**.</span></span> <span data-ttu-id="7fb1b-150">この時点で、通常、アダプターはバッチ内のすべてのメッセージをインメモリ キューに追加します。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-150">At this point the adapter typically enqueues all the messages in the batch to its in-memory queue.</span></span> <span data-ttu-id="7fb1b-151">アダプターは、バッチ非対応のアダプターの場合と同様に、アダプター独自のスレッド プールに含まれている 1 つまたは複数のスレッドからメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-151">The adapter transmits the messages from a thread or threads in its own thread pool as in the case of non-batch-aware adapters.</span></span> <span data-ttu-id="7fb1b-152">次に、アダプターは送信結果をエンジンに通知します。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-152">The adapter then notifies the engine of the outcome of the transmission.</span></span>  
  
 <span data-ttu-id="7fb1b-153">次のオブジェクト間の対話処理図に、バッチ化された送信アダプターによって 2 通のメッセージが送信されるようすを示します。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-153">The following object interaction diagram illustrates the transmission of two messages by a batched send adapter.</span></span>  
  
 ![](../core/media/batchedsends.gif "BatchedSends")  
  
## <a name="handling-transmission-failures"></a><span data-ttu-id="7fb1b-154">送信エラーの処理</span><span class="sxs-lookup"><span data-stu-id="7fb1b-154">Handling Transmission Failures</span></span>  
 <span data-ttu-id="7fb1b-155">送信エラーの推奨セマンティクスを次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-155">The recommended semantics for transmission failures are illustrated in the figure below.</span></span> <span data-ttu-id="7fb1b-156">これらのセマンティクスは推奨にすぎず、メッセージング エンジンによって適用されるものではありません。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-156">These are only recommendations and are not enforced by the Messaging Engine.</span></span> <span data-ttu-id="7fb1b-157">有効な理由があるが、注意が必要ここでは、次のガイドラインから逸脱したアダプターを開発することができます。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-157">You can develop an adapter that deviates from these guidelines if there are valid reasons for doing so but you should be careful in this case.</span></span> <span data-ttu-id="7fb1b-158">たとえば、アダプターは一般的に、再試行回数分だけ再試行した後、必ずメッセージをバックアップ トランスポートに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-158">For example, in general an adapter should always move messages to the backup transport after all retries have been exhausted.</span></span>  
  
 <span data-ttu-id="7fb1b-159">さらに一般的なこととして、トランスポートでは、構成されている回数よりも多くの再試行を行う必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-159">More commonly a transport may need to use more retries than are configured.</span></span> <span data-ttu-id="7fb1b-160">トランスポート層の回復性は向上しているので、その差がわずかな場合には、対応可能と見なされます。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-160">While this is slightly different it is considered acceptable because the resilience of the transport layer is being increased.</span></span> <span data-ttu-id="7fb1b-161">一般的に、メッセージング エンジンによって公開される API は、可能な場合にはアダプターに最大限の制御を与えるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-161">In general the APIs exposed by the Messaging Engine are designed to give the adapter maximum control where possible.</span></span> <span data-ttu-id="7fb1b-162">この制御により、より優れたレベルの応答性を実現できます。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-162">With this control comes a greater level of responsibility.</span></span>  
  
 ![](../core/media/handlingerrors.gif "HandlingErrors")  
  
 <span data-ttu-id="7fb1b-163">アダプターが、システム コンテキスト プロパティをチェックして、メッセージで使用できる再試行回数を決定**RetryCount**です。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-163">The adapter determines the number of retries available on a message by checking the system context property **RetryCount**.</span></span> <span data-ttu-id="7fb1b-164">アダプターが、 **Resubmit** API 1 回ごとに再試行してください再送信するメッセージに渡します。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-164">The adapter calls the **Resubmit** API once for each retry attempt and passes in the message to be resubmitted.</span></span> <span data-ttu-id="7fb1b-165">また、メッセージのほか、エンジンからアダプターへのメッセージ配信時刻を示すタイム スタンプも渡します。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-165">Along with the message it passes the time stamp indicating when the engine should deliver the message back to the adapter.</span></span> <span data-ttu-id="7fb1b-166">この値は通常、現在の時刻の値を加えた**RetryInterval**です。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-166">This value should typically be the current time plus the value of **RetryInterval**.</span></span> <span data-ttu-id="7fb1b-167">**RetryInterval**システム コンテキスト プロパティの単位は分です。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-167">**RetryInterval** is a system context property whose units are minutes.</span></span> <span data-ttu-id="7fb1b-168">両方の**RetryCount**と**RetryInterval**メッセージ コンテキストでは、送信ポートで構成されている値。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-168">Both the **RetryCount** and **RetryInterval** in the message context are the values that are configured on the send port.</span></span> <span data-ttu-id="7fb1b-169">同一の BizTalk ホストのインスタンスが複数のコンピューター上に配置されているスケールアウト配置を考えてみます。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-169">Consider a scaled-out deployment with instances of the same BizTalk Host deployed on multiple computers.</span></span> <span data-ttu-id="7fb1b-170">再試行間隔の有効期限が切れた後でメッセージが配信されると、そのメッセージは実行するように構成されている任意のコンピューター上のいずれかのホスト インスタンスに配信されることがあります。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-170">If the message is delivered after the retry interval has expired, the message may be delivered to the any one of the host instances on any of the computers where they are configured to run.</span></span> <span data-ttu-id="7fb1b-171">このような理由から、その後の送信もアダプターの同一インスタンスによって実行される保証がないため、再試行で使用するメッセージに関連付けられているどの状態も、アダプターでは保持しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-171">For this reason the adapter should not hold any state associated with a message to be used on the retry attempt because there is no guarantee that same instance of the adapter will be responsible for the transmission at a later time.</span></span>  
  
 <span data-ttu-id="7fb1b-172">アダプターでは、再試行回数が 0 以下になった後は、メッセージをバックアップ トランスポートに移動しようとするだけです。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-172">The adapter should only attempt to move the message to the backup transport after the retry count is less than or equal to zero.</span></span> <span data-ttu-id="7fb1b-173">ポートにバックアップ トランスポートが構成されていない場合、メッセージをバックアップ トランスポートに移動しようとしても失敗します。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-173">An attempt to move the message to the backup transport will fail if there is no backup transport configured for the port.</span></span> <span data-ttu-id="7fb1b-174">この場合、メッセージは保留されます。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-174">In this case the message should be suspended.</span></span>  
  
 <span data-ttu-id="7fb1b-175">次のコードは、メッセージ コンテキストから再試行回数と再試行間隔を決定し、次にバックアップ トランスポートへの再送信または移動を行う方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-175">The following code fragment illustrates how to determine the retry count and interval from the message context, and the subsequent resubmit or move to the backup transport.</span></span>  
  
```  
using Microsoft.XLANGs.BaseTypes;  
using Microsoft.BizTalk.Message.Interop;  
using Microsoft.BizTalk.TransportProxy.Interop;  
 …  
// RetryCount and RetyInterval are system context properties...  
private static readonly PropertyBase RetryCountProperty =   
 new BTS.RetryCount();  
private static readonly PropertyBase RetryIntervalProperty =   
 new BTS.RetryInterval();  
  
public void HandleRetry(IBaseMessage msg, IBTTransportBatch batch)  
{  
int retryCount = 0;  
int retryInterval = 0;  
  
// Get the RetryCount and RetryInterval off the msg ctx...  
 GetMessageRetryState(msg, out retryCount, out retryInterval);  
  
// If we have retries available resubmit, else move to   
 // backup transport...  
 if ( retryCount > 0 )  
batch.Resubmit(  
 msg, DateTime.Now.AddMinutes(retryInterval));  
else  
batch.MoveToNextTransport(msg);  
}  
  
public void GetMessageRetryState(  
 IBaseMessage msg,   
 out int retryCount,   
 out int retryInterval )  
{  
retryCount = 0;  
retryInterval = 0;  
  
object obj =  msg.Context.Read(  
RetryCountProperty.Name.Name,    
RetryCountProperty.Name.Namespace);   
  
if ( null != obj )  
retryCount = (int)obj;  
  
obj =  msg.Context.Read(  
RetryIntervalProperty.Name.Name,    
RetryIntervalProperty.Name.Namespace);   
  
if ( null != obj )  
retryInterval = (int)obj;  
}  
```  
  
## <a name="throwing-an-exception-from-transmitmessage"></a><span data-ttu-id="7fb1b-176">TransmitMessage からの例外のスロー</span><span class="sxs-lookup"><span data-stu-id="7fb1b-176">Throwing an Exception from TransmitMessage</span></span>  
 <span data-ttu-id="7fb1b-177">アダプターが Api のいずれかで例外をスローするかどうかは**IBTTransmitter.TransmitMessage**、 **IBTTransmitterBatch.TransmitMessage**、 **IBTTransmitterBatch.Done**では、エンジンが送信エラーと関連するメッセージの送信を処理しで詳しく説明されている、メッセージの適切な措置を取ります[アダプターの障害を処理する方法](../core/how-to-handle-adapter-failures.md)です。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-177">If the adapter throws an exception on any of the APIs **IBTTransmitter.TransmitMessage**, **IBTTransmitterBatch.TransmitMessage**, **IBTTransmitterBatch.Done**, the engine treats the transmission of the messages involved as transmission failures and takes the appropriate action for the message, as detailed in [How to Handle Adapter Failures](../core/how-to-handle-adapter-failures.md).</span></span>  
  
 <span data-ttu-id="7fb1b-178">バッチ対応の送信アダプターの場合、TransmitMessage API で例外を送信するとバッチ全体が消去され、既定の送信エラー操作がバッチ内のすべてのメッセージに対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-178">For batch-aware send adapters, throwing an exception on the TransmitMessage API results in the entire batch being cleared and the default transmit failure actions being performed for all messages in that batch.</span></span>  
  
## <a name="solicit-response"></a><span data-ttu-id="7fb1b-179">[送信請求 - 応答]</span><span class="sxs-lookup"><span data-stu-id="7fb1b-179">Solicit-Response</span></span>  
 <span data-ttu-id="7fb1b-180">通常、双方向の送信アダプターでは、一方向の送信と双方向の送信の両方がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-180">Two-way send adapters typically support both one-way and two-way transmissions.</span></span> <span data-ttu-id="7fb1b-181">送信アダプターを調べることによって、メッセージを一方向または双方向の送信に転送される必要があるかどうかを決定する、 **IsSolicitResponse**メッセージ コンテキストのシステム コンテキスト プロパティです。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-181">The send adapter determines whether the message should be transmitted as a one-way or two-way send by inspecting the **IsSolicitResponse** system context property in the message context.</span></span>  
  
 <span data-ttu-id="7fb1b-182">このコード例の一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-182">The following code fragment demonstrates this:</span></span>  
  
```  
private bool portIsTwoWay = false;  
private static readonly PropertyBase IsSolicitResponseProperty= new BTS.IsSolicitResponse();  
  
...  
  
 // Port is one way or two way...  
 object obj =  this.message.Context.Read(  
 IsSolicitResponseProperty.Name.Name,    
 IsSolicitResponseProperty.Name.Namespace);   
  
if ( null != obj )  
 this.portIsTwoWay = (bool)obj;  
```  
  
 <span data-ttu-id="7fb1b-183">アダプターは、送信請求 - 応答送信の間、送信請求メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-183">During a solicit-response transmission the adapter transmits the solicit message.</span></span> <span data-ttu-id="7fb1b-184">この操作の完了後、アダプターは関連する応答を送信し、最初の送信請求メッセージをメッセージ ボックス データベースから削除するようにメッセージング エンジンに通知します。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-184">After this completed it submits the associated response and tells the Messaging Engine to delete the original solicit message from the MessageBox database.</span></span> <span data-ttu-id="7fb1b-185">アプリケーション キューからメッセージを削除するこの操作は、応答メッセージの送信と同じトランスポート プロキシ バッチ内で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-185">The action of deleting the message from the application queue should be performed in the same transport proxy batch as the submission of the response message.</span></span> <span data-ttu-id="7fb1b-186">これにより、応答の削除および送信における原子性が確保されます。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-186">This ensures atomicity of the deletion and submission of the response.</span></span> <span data-ttu-id="7fb1b-187">原子性を完全に維持するには、アダプターは、トランザクション対応リソースへの送信請求メッセージの送信、応答メッセージの送信、および送信請求メッセージの削除がすべて同一の DTC トランザクションのコンテキストに含まれている DTC トランザクションを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-187">For complete atomicity the adapter should use a DTC transaction whereby the transmission of the solicit message to a transaction-aware resource, submission of the response message, and deletion of the solicit message are all in the context of the same DTC transaction.</span></span> <span data-ttu-id="7fb1b-188">ここでも、送信請求メッセージを非ブロッキング送信を使用して送信することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-188">As always, we recommend that the solicit message is transmitted using a non-blocking send.</span></span>  
  
 <span data-ttu-id="7fb1b-189">次のコードは、双方向の送信の主要な側面を示しています。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-189">The following code fragment illustrates the main aspects of a two-way send.</span></span> <span data-ttu-id="7fb1b-190">エンジンを呼び出すと**IBTTransmitter.TransmitMessage**アダプターが、インメモリ キューに送信するメッセージをエンキューします。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-190">When the engine calls **IBTTransmitter.TransmitMessage** the adapter enqueues the message to be transmitted to an in-memory queue.</span></span> <span data-ttu-id="7fb1b-191">アダプターは `false` を返して、非ブロッキング送信を実行していることを示します。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-191">The adapter returns `false` to indicate that it is performing a non-blocking send.</span></span> <span data-ttu-id="7fb1b-192">アダプターのスレッド プール (**WorkerThreadThunk**) サービスのメモリ内キューとヘルパー メソッドに渡すメッセージをデキューします。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-192">The adapter's thread pool (**WorkerThreadThunk**) services the in-memory queue and dequeues a message to hand it off to a helper method.</span></span> <span data-ttu-id="7fb1b-193">このメソッドの役割は、送信請求メッセージを送信して応答メッセージを受信することです </span><span class="sxs-lookup"><span data-stu-id="7fb1b-193">This method is responsible for sending the solicit message and receiving the response message.</span></span> <span data-ttu-id="7fb1b-194">(このヘルパー メソッドの実装はこのトピックの対象範囲外です)。応答メッセージはエンジンに送信され、送信請求メッセージはアプリケーション キューから削除されます。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-194">(The implementation of this helper method is outside the scope of this topic.) The response message is submitted into the engine, and the solicit message is deleted from the application queue.</span></span>  
  
```  
using System.Collections;  
using Microsoft.XLANGs.BaseTypes;  
using Microsoft.BizTalk.Message.Interop;  
using Microsoft.BizTalk.TransportProxy.Interop;  
  
     static private Queue _transmitQueue = new Queue();  
  static private IBTTransportProxy _transportProxy = null;   
// IBTTransmitter...  
 public bool TransmitMessage(IBaseMessage msg)  
{  
// Add message to the transmit queue...  
lock(_transmitQueue.SyncRoot)  
 {  
_transmitQueue.Enqueue(msg);  
 }  
  
 return false;  
}  
  
 // Threadpool worker thread...   
private void WorkerThreadThunk()  
{  
try  
{  
 IBaseMessage solicitMsg = null;  
  
 lock(_transmitQueue.SyncRoot)  
 {  
 solicitMsg =   
 (IBaseMessage)_transmitQueue.Dequeue();  
}  
  
 IBaseMessage responseMsg = SendSolicitResponse(   
 solicitMsg );  
Callback cb = new Callback();  
  
IBTTransportBatch batch = _transportProxy.GetBatch(  
 cb, null);  
batch.SubmitResponseMessage( solicitMsg, responseMsg );  
batch.DeleteMessage( solicitMsg );  
batch.Done(null);  
}  
catch(Exception)  
{  
// Handle failure....  
}  
}  
  
static private IBaseMessage SendSolicitResponse(  
 IBaseMessage solicitMsg )  
{  
// Helper method to send solicit message and receive   
 // response message...  
IBaseMessage responseMsg = null;  
return responseMsg;  
}  
```  
  
## <a name="dynamic-sends"></a><span data-ttu-id="7fb1b-195">動的送信</span><span class="sxs-lookup"><span data-stu-id="7fb1b-195">Dynamic Sends</span></span>  
 <span data-ttu-id="7fb1b-196">動的送信ポートには、関連付けられているアダプター構成がありません。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-196">Dynamic send ports do not have adapter configuration associated with them.</span></span> <span data-ttu-id="7fb1b-197">代わりに、動的送信ポートでは、アダプターが動的ポートでメッセージを送信することが必要になる、既定のプロパティのハンドラー構成を使用します。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-197">Instead they use handler configuration for any default properties that the adapter needs to transmit messages on a dynamic port.</span></span> <span data-ttu-id="7fb1b-198">たとえば、HTTP アダプターでプロキシを使用する場合には、HTTP アダプターで資格情報を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-198">For example, an HTTP adapter may need to use a proxy and need to provide credentials.</span></span> <span data-ttu-id="7fb1b-199">アダプターが実行時にキャッシュするハンドラー構成では、ユーザー名、パスワード、およびポートを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-199">The user name, password, and port could be specified in the handler configuration that the adapter caches at run time.</span></span>  
  
 <span data-ttu-id="7fb1b-200">動的なメッセージが、経由で送信するのには、トランスポートを決定する、エンジンの**OutboundTransportLocation**アダプターのエイリアスが付いています。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-200">For the engine to determine the transport that a dynamic message is to be sent over, the **OutboundTransportLocation** is prefixed with the adapter's alias.</span></span> <span data-ttu-id="7fb1b-201">アダプターは、インストール時に 1 つ以上のエイリアスを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に登録できます。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-201">An adapter can register one or more aliases with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] at install time.</span></span> <span data-ttu-id="7fb1b-202">エンジンは、解析、 **OutboundTransportLocation**一致を見つける実行時にします。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-202">The engine parses the **OutboundTransportLocation** at run time to find a match.</span></span> <span data-ttu-id="7fb1b-203">処理のため、アダプターは、 **OutboundTransportLocation**有無にかかわらず、エイリアスが付いています。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-203">The adapter is responsible for handling the **OutboundTransportLocation** with or without the alias prepended to it.</span></span> <span data-ttu-id="7fb1b-204">次の表に、追加設定なしの BizTalk アダプター用に登録されているエイリアスの例をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="7fb1b-204">The following table shows some examples of aliases registered for out-of-the-box BizTalk adapters.</span></span>  
  
|<span data-ttu-id="7fb1b-205">アダプターのエイリアス</span><span class="sxs-lookup"><span data-stu-id="7fb1b-205">Adapter alias</span></span>|<span data-ttu-id="7fb1b-206">[アダプター]</span><span class="sxs-lookup"><span data-stu-id="7fb1b-206">Adapter</span></span>|<span data-ttu-id="7fb1b-207">OutboundTransportLocation の例</span><span class="sxs-lookup"><span data-stu-id="7fb1b-207">OutboundTransportLocation example</span></span>|  
|-------------------|-------------|---------------------------------------|  
|<span data-ttu-id="7fb1b-208">HTTP://</span><span class="sxs-lookup"><span data-stu-id="7fb1b-208">HTTP://</span></span>|<span data-ttu-id="7fb1b-209">HTTP</span><span class="sxs-lookup"><span data-stu-id="7fb1b-209">HTTP</span></span>|<span data-ttu-id="7fb1b-210">http://www.</span><span class="sxs-lookup"><span data-stu-id="7fb1b-210">http://www.</span></span> <span data-ttu-id="7fb1b-211">MyCompany.com/bar</span><span class="sxs-lookup"><span data-stu-id="7fb1b-211">MyCompany.com/bar</span></span>|  
|<span data-ttu-id="7fb1b-212">HTTPS://</span><span class="sxs-lookup"><span data-stu-id="7fb1b-212">HTTPS://</span></span>|<span data-ttu-id="7fb1b-213">HTTP</span><span class="sxs-lookup"><span data-stu-id="7fb1b-213">HTTP</span></span>|<span data-ttu-id="7fb1b-214">https://www.</span><span class="sxs-lookup"><span data-stu-id="7fb1b-214">https://www.</span></span> <span data-ttu-id="7fb1b-215">MyCompany.com/bar</span><span class="sxs-lookup"><span data-stu-id="7fb1b-215">MyCompany.com/bar</span></span>|  
|<span data-ttu-id="7fb1b-216">mailto:</span><span class="sxs-lookup"><span data-stu-id="7fb1b-216">mailto:</span></span>|<span data-ttu-id="7fb1b-217">SMTP (SMTP)</span><span class="sxs-lookup"><span data-stu-id="7fb1b-217">SMTP</span></span>|mailto:A.User@MyCompany.com|  
|<span data-ttu-id="7fb1b-218">FILE://</span><span class="sxs-lookup"><span data-stu-id="7fb1b-218">FILE://</span></span>|<span data-ttu-id="7fb1b-219">FILE</span><span class="sxs-lookup"><span data-stu-id="7fb1b-219">FILE</span></span>|<span data-ttu-id="7fb1b-220">FILE://C:\MyCompany \\%MessageID%.xml</span><span class="sxs-lookup"><span data-stu-id="7fb1b-220">FILE://C:\ MyCompany \\%MessageID%.xml</span></span>|