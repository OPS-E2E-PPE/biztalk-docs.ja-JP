---
title: "メッセージの配信を順序付け |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- backing up, message order
- file transport, message order
- Messaging Engine, transports
- messages, performance
- dynamic send ports, message order
- BTS.SuspendAsNonResumable message context property
- performance, message order
- Messaging Engine, performance
- Messaging Engine, message order
- MessageBox database, message order
- messages, sorting
- backing up, backup transports
- adapters, custom receive adapters
- adapters, messages
- customizing, receive adapters
ms.assetid: 39e0bba6-81f5-4ae0-af92-837b225bc801
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: abfb0b78065d4eb3aee022d141cc833399fc1496
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="ordered-delivery-of-messages"></a><span data-ttu-id="c8e78-102">メッセージの順次配送</span><span class="sxs-lookup"><span data-stu-id="c8e78-102">Ordered Delivery of Messages</span></span>
<span data-ttu-id="c8e78-103">メッセージの順次配送とは、特定の順序でメッセージ ボックス データベースに公開されたメッセージを、それぞれ対応するサブスクライバーに (メッセージ ボックスに公開されたときと同じ順序で) 配送することです。</span><span class="sxs-lookup"><span data-stu-id="c8e78-103">Ordered message delivery ensures that messages that are published to the MessageBox database in a given order are delivered to each matching subscriber in the same order in which they were published to the message box.</span></span>  
  
## <a name="configuring-ordered-message-delivery"></a><span data-ttu-id="c8e78-104">メッセージの順次配送の構成</span><span class="sxs-lookup"><span data-stu-id="c8e78-104">Configuring Ordered Message Delivery</span></span>  
 <span data-ttu-id="c8e78-105">メッセージの順次配送は、次の場所で構成できます。</span><span class="sxs-lookup"><span data-stu-id="c8e78-105">Ordered message delivery can be configured in the following places:</span></span>  
  
-   <span data-ttu-id="c8e78-106">**受信**オーケストレーションの図形</span><span class="sxs-lookup"><span data-stu-id="c8e78-106">**Receive** shape in an orchestration</span></span>  
  
-   <span data-ttu-id="c8e78-107">送信ポート</span><span class="sxs-lookup"><span data-stu-id="c8e78-107">Send port</span></span>  
  
## <a name="ordered-delivery-with-existing-transports"></a><span data-ttu-id="c8e78-108">既存のトランスポートでの順次配送</span><span class="sxs-lookup"><span data-stu-id="c8e78-108">Ordered Delivery with Existing Transports</span></span>  
 <span data-ttu-id="c8e78-109">トランスポートに使用されるプロトコルによっては、特に順次配送が必要ないものもあります (FILE や HTTP など)。</span><span class="sxs-lookup"><span data-stu-id="c8e78-109">The protocols underlying certain transports, such as FILE and HTTP, are not consistent with the notion of ordered delivery.</span></span> <span data-ttu-id="c8e78-110">ただし、このようなトランスポートを使用しても、ポートにバインドされている場合、トランスポートが順次配送は、対象としてマークし、BizTalk Server では、順次配送を適用するトランスポートを取得しません、[次へ] の送信メッセージ現在 1 つが正常に送信されるまでにより.</span><span class="sxs-lookup"><span data-stu-id="c8e78-110">However, even with such transports, if the port bound to the transport is marked for ordered delivery, then BizTalk Server enforces ordered delivery by ensuring that the transport does not get the next outbound message until the current one has been successfully sent.</span></span> <span data-ttu-id="c8e78-111">この機能を実現するために、BizTalk Server は、各メッセージを 1 つのバッチとしてトランスポートのアダプターに渡し、アダプターがそのメッセージをメッセージ ボックスから削除するまで待機してから、次のメッセージを別のバッチとしてアダプターに配送します。</span><span class="sxs-lookup"><span data-stu-id="c8e78-111">To achieve this, BizTalk Server passes each message to the transport's adapter in a single batch and waits until the adapter has successfully deleted the message from the message box before delivering the next message, in another batch, to the adapter.</span></span>  
  
### <a name="ordered-delivery-for-custom-adapters"></a><span data-ttu-id="c8e78-112">カスタム アダプターでの順次配送</span><span class="sxs-lookup"><span data-stu-id="c8e78-112">Ordered Delivery for Custom Adapters</span></span>  
 <span data-ttu-id="c8e78-113">カスタムの受信アダプターでは、特別に考慮しなければならない事柄があります。</span><span class="sxs-lookup"><span data-stu-id="c8e78-113">There are special considerations for custom receive adapters.</span></span> <span data-ttu-id="c8e78-114">順次配送をサポートするカスタム アダプターは、次のことを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8e78-114">It you are writing a custom adapter that supports ordered delivery on receive, the adapter should do the following:</span></span>  
  
-   <span data-ttu-id="c8e78-115">カスタムの受信メッセージのバッチを送信するには後のアダプターが待機する必要があります、 **BatchComplete**次のバッチを送信する前に BizTalk Server からのコールバック。</span><span class="sxs-lookup"><span data-stu-id="c8e78-115">After submitting a batch of messages, your custom receive adapter should wait for the **BatchComplete** callback from BizTalk Server before submitting the next batch.</span></span> <span data-ttu-id="c8e78-116">詳細については、次を参照してください。 [Batch-Supported 受信アダプター用のインターフェイス](../core/interfaces-for-a-batch-supported-receive-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="c8e78-116">For more details, see [Interfaces for a Batch-Supported Receive Adapter](../core/interfaces-for-a-batch-supported-receive-adapter.md).</span></span>  
  
-   <span data-ttu-id="c8e78-117">メッセージの処理がパイプラインで失敗した場合、そのメッセージを保留 (できれば再開不可に) する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8e78-117">If a message fails in the pipeline, it should be suspended, preferably as nonresumable.</span></span> <span data-ttu-id="c8e78-118">使用して、 **BTS です。SuspendAsNonResumable**メッセージ コンテキスト プロパティ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージを適切にフラグに設定します。</span><span class="sxs-lookup"><span data-stu-id="c8e78-118">Use the **BTS.SuspendAsNonResumable** message context property in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to flag the message appropriately.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8e78-119">保留したメッセージが後で再開されると、メッセージの順序が破綻してしまいます。</span><span class="sxs-lookup"><span data-stu-id="c8e78-119">Message order can be broken if a suspended message is later resumed.</span></span> <span data-ttu-id="c8e78-120">このような事態を避けるためには、失敗したメッセージを再開不可として保留します。</span><span class="sxs-lookup"><span data-stu-id="c8e78-120">If you do not want this behavior, suspend failed messages as nonresumable.</span></span>  
  
 <span data-ttu-id="c8e78-121">カスタム アダプター作成の詳細については、次を参照してください。[カスタム アダプターの開発](../core/developing-custom-adapters.md)です。</span><span class="sxs-lookup"><span data-stu-id="c8e78-121">For more details on building a custom adapter, see [Developing Custom Adapters](../core/developing-custom-adapters.md).</span></span>  
  
## <a name="conditions-for-end-to-end-ordered-message-processing"></a><span data-ttu-id="c8e78-122">エンド ツー エンドの順次メッセージ処理を実現するための条件</span><span class="sxs-lookup"><span data-stu-id="c8e78-122">Conditions for End-to-End Ordered Message Processing</span></span>  
 <span data-ttu-id="c8e78-123">エンド ツー エンドの順次配送を実現するには、次の条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8e78-123">To provide end-to-end ordered delivery the following conditions must be met:</span></span>  
  
-   <span data-ttu-id="c8e78-124">メッセージは、BizTalk Server に送信するメッセージの順序を保持できるアダプターで受信されなければなりません。</span><span class="sxs-lookup"><span data-stu-id="c8e78-124">Messages must be received with an adapter that preserves the order of the messages when submitting them to BizTalk Server.</span></span> <span data-ttu-id="c8e78-125">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には、この条件を満たすアダプターとして、MSMQ および MQSeries があります。</span><span class="sxs-lookup"><span data-stu-id="c8e78-125">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], examples of such adapters are MSMQ and MQSeries.</span></span> <span data-ttu-id="c8e78-126">HTTP アダプターまたは SOAP アダプターを使用して、メッセージを順次配送することもできますが、その場合は、HTTP クライアントまたは SOAP クライアント側で、正しい順序が維持されるよう配慮する必要があります (メッセージを 1 つずつ送信する)。</span><span class="sxs-lookup"><span data-stu-id="c8e78-126">In addition, HTTP or SOAP adapters can be used to submit messages in order, but in that case the HTTP or SOAP client needs to enforce the order by submitting messages one at a time.</span></span>  
  
-   <span data-ttu-id="c8e78-127">持つ送信ポートでこれらのメッセージをサブスクライブする必要があります、**順次配送**オプションに設定`True`です。</span><span class="sxs-lookup"><span data-stu-id="c8e78-127">You must subscribe to these messages with a send port that has the **Ordered Delivery** option set to `True`.</span></span>  
  
-   <span data-ttu-id="c8e78-128">シーケンシャルなコンボイを使用するオーケストレーションを構成する必要があります、オーケストレーションがメッセージをオーケストレーションのインスタンスが 1 つだけを使用する必要がありますプロセスに使用されている場合、**順次配送**のプロパティ、オーケストレーションの受信ポートに設定する必要があります`True`です。</span><span class="sxs-lookup"><span data-stu-id="c8e78-128">If an orchestration is used to process the messages, only a single instance of the orchestration should be used, the orchestration should be configured to use a sequential convoy, and the **Ordered Delivery** property of the orchestration's receive port should be set to `True`.</span></span>  
  
## <a name="restrictions"></a><span data-ttu-id="c8e78-129">制限</span><span class="sxs-lookup"><span data-stu-id="c8e78-129">Restrictions</span></span>  
 <span data-ttu-id="c8e78-130">メッセージの順次配送は、次のサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c8e78-130">Ordered delivery of messages is not supported for the following:</span></span>  
  
-   <span data-ttu-id="c8e78-131">動的送信ポート[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]と以前のバージョン</span><span class="sxs-lookup"><span data-stu-id="c8e78-131">Dynamic send ports in [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)] and previous versions</span></span>

- <span data-ttu-id="c8e78-132">動的送信ポート[!INCLUDE[bts2016_md](../includes/bts2016-md.md)](および以降のバージョン) アダプターではそれらの型を**しない**順次配送の静的送信ポートのサポート</span><span class="sxs-lookup"><span data-stu-id="c8e78-132">Dynamic send ports in [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] (and any newer versions) for those adapter types that **don't** support ordered delivery on static send ports</span></span>
  
-   <span data-ttu-id="c8e78-133">バックアップ トランスポート</span><span class="sxs-lookup"><span data-stu-id="c8e78-133">Backup transports</span></span>  

  
## <a name="interactions"></a><span data-ttu-id="c8e78-134">他の設定との関係</span><span class="sxs-lookup"><span data-stu-id="c8e78-134">Interactions</span></span>  
 <span data-ttu-id="c8e78-135">送信ポートに対して順次配送を構成する場合、他の設定との関係に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8e78-135">When ordered delivery is configured for a send port, be aware of the following interactions with other configured behaviors in BizTalk Server:</span></span>  
  
-   <span data-ttu-id="c8e78-136">同じ送信ポートの "現在のメッセージが失敗したときに、後続のメッセージの送信を停止する" 設定</span><span class="sxs-lookup"><span data-stu-id="c8e78-136">For the "Stop sending subsequent messages on current message failure" setting on the same send port:</span></span>  
  
    -   <span data-ttu-id="c8e78-137">**場合は false。**</span><span class="sxs-lookup"><span data-stu-id="c8e78-137">**False.**</span></span> <span data-ttu-id="c8e78-138">失敗したメッセージだけが (再開不可として) 保留にされ、以降のすべてのメッセージは引き続き処理されます。</span><span class="sxs-lookup"><span data-stu-id="c8e78-138">Only the failed message is suspended (as not resumable) and all subsequent messages continue to be processed.</span></span> <span data-ttu-id="c8e78-139">これにより、失敗しなかったメッセージの順序は維持されますが、元の順序に抜けが生じることになります。</span><span class="sxs-lookup"><span data-stu-id="c8e78-139">This preserves the ordering of the non-failed messages but can result in gaps in the sequence.</span></span> <span data-ttu-id="c8e78-140">たとえば、101、102、103 という順序で受信され、102 が保留状態になった場合、101 と 103 については正しい順番で処理されます。</span><span class="sxs-lookup"><span data-stu-id="c8e78-140">For example, if orders 101, 102, and 103 are received and order 102 is suspended, orders 101 and 103 will continue to be processed in order.</span></span>  
  
    -   <span data-ttu-id="c8e78-141">**True です。**</span><span class="sxs-lookup"><span data-stu-id="c8e78-141">**True.**</span></span> <span data-ttu-id="c8e78-142">いずれかのメッセージで処理が失敗した場合、送信ポートのインスタンスが保留状態になります。</span><span class="sxs-lookup"><span data-stu-id="c8e78-142">The send port instance is suspended if any of the messages fails processing.</span></span> <span data-ttu-id="c8e78-143">これにより、順次配送の設定された、後続のすべてのメッセージが保留されます。</span><span class="sxs-lookup"><span data-stu-id="c8e78-143">This causes all subsequent messages in the ordered set of messages to be suspended.</span></span> <span data-ttu-id="c8e78-144">後続のメッセージが、失敗したメッセージよりも前に配送されることはないため、メッセージの順序は完全に維持されます。</span><span class="sxs-lookup"><span data-stu-id="c8e78-144">This preserves message order by preventing delivery of subsequent messages before delivery of the failed message.</span></span>  
  
-   <span data-ttu-id="c8e78-145">送信請求 - 応答の送信ポートで、"現在のメッセージが失敗したときに、後続のメッセージの送信を停止する" プロパティが `true` に設定され、応答の受信パイプラインの逆アセンブル ステージで復旧可能な交換処理が構成されていた場合、応答を逆アセンブルしているときに復旧可能なエラーが発生したとしても、送信ポートはメッセージの送信を中断しません (つまり、インスタンスは保留状態になりません)。</span><span class="sxs-lookup"><span data-stu-id="c8e78-145">If a solicit-response send port has the "Stop sending subsequent messages on current message failure" property set to `true`, and if recoverable interchange processing is configured for the disassembly stage of the receive pipeline for the response, then the send port does not stop sending messages (that is, the instance is not suspended) if there is a recoverable error in disassembling the response.</span></span>  
  
-   <span data-ttu-id="c8e78-146">順次配送の設定された送信ポートを削除する場合は、関連付けられたインスタンスが存在しないことを確認しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8e78-146">Before deleting an ordered send port, ensure that there are no instances associated with it.</span></span> <span data-ttu-id="c8e78-147">関連付けられたインスタンスが存在する場合は、それを終了させてから、送信ポートを削除します。</span><span class="sxs-lookup"><span data-stu-id="c8e78-147">If there are associated instances, you should terminate them before deleting the send port.</span></span>  
  
## <a name="ordered-delivery-to-file-transport"></a><span data-ttu-id="c8e78-148">ファイル トランスポートへの順次配送</span><span class="sxs-lookup"><span data-stu-id="c8e78-148">Ordered Delivery to File Transport</span></span>  
 <span data-ttu-id="c8e78-149">ファイル アダプターには、メッセージが順に到着します。</span><span class="sxs-lookup"><span data-stu-id="c8e78-149">Messages arrive at the File adapter in sequence.</span></span> <span data-ttu-id="c8e78-150">ファイル アダプターでは、メッセージを単一のファイルに追加していくか、個別のファイルとして書き出します。</span><span class="sxs-lookup"><span data-stu-id="c8e78-150">The File adapter may append messages to a single file or write out a sequence of files, with the following results:</span></span>  
  
-   <span data-ttu-id="c8e78-151">メッセージ データが単一のファイルに追加される場合、各メッセージは順番に追加されていきます。</span><span class="sxs-lookup"><span data-stu-id="c8e78-151">If message data is appended to a single file, individual messages are appended in order.</span></span> <span data-ttu-id="c8e78-152">ファイル アダプターを使用する送信ポートの順次配送オプションは、送信トランスポートが追加モードで動作している場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="c8e78-152">The ordered delivery option on a send port that uses the FILE adapter only makes sense if the send transport works in append mode</span></span>  
  
-   <span data-ttu-id="c8e78-153">メッセージが個別のファイルに出力される場合、その順番がファイル名に反映されます。つまり、到着した順番に基づいてファイル名が付けられます。</span><span class="sxs-lookup"><span data-stu-id="c8e78-153">If messages are written to individual files, the order is reflected in the file names, which are sequentially named.</span></span> <span data-ttu-id="c8e78-154">このとき、アダプターによって書き込まれたファイルでは、時系列 (ファイルの作成日時や更新時刻など) に関するファイル システムのプロパティには、メッセージが到着した順序は反映されません。</span><span class="sxs-lookup"><span data-stu-id="c8e78-154">In this case, for files written by the adapter, file system properties relating to chronology (for example, file creation time or modification time) do not necessarily reflect the message arrival sequence.</span></span>  
  
## <a name="performance-impact-of-ordered-delivery"></a><span data-ttu-id="c8e78-155">順次配送がパフォーマンスに与える影響</span><span class="sxs-lookup"><span data-stu-id="c8e78-155">Performance Impact of Ordered Delivery</span></span>  
 <span data-ttu-id="c8e78-156">BizTalk Server は、順次配送を実現するために、メッセージ経路のさまざまな地点において、メッセージを順番どおりに処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8e78-156">To achieve ordered delivery, BizTalk Server must serialize processing of ordered messages at various points along the message pathway.</span></span> <span data-ttu-id="c8e78-157">そのため、複数のホスト インスタンスを使用して、メッセージを並列処理するなどのスケール アウト手段が通用しなくなります。</span><span class="sxs-lookup"><span data-stu-id="c8e78-157">This works against scale-out techniques, such as the use of multiple host instances for parallel processing of messages.</span></span> <span data-ttu-id="c8e78-158">順次配送を行う場合、複数のホスト インスタンスで動作するように構成されたポートであっても、複数のホスト インスタンスで実行させることはできません。順次配送を行うには、単一のホスト インスタンスで動作させる必要があるためです。</span><span class="sxs-lookup"><span data-stu-id="c8e78-158">When using ordered delivery, even ports configured to run on multiple host instances run only on a single host instance to ensure ordered delivery.</span></span> <span data-ttu-id="c8e78-159">ただし、複数のホスト インスタンスの場合でも、高い可用性のメリットは享受できます。メッセージの順次配送を処理するホスト インスタンスで障害が発生した場合、処理に失敗したメッセージは利用可能な別のホスト インスタンスで再処理されます。</span><span class="sxs-lookup"><span data-stu-id="c8e78-159">However, in this situation, high availability is still maintained because the failure of a host instance that is processing ordered delivery of messages results in reprocessing of the failed message on another available host instance.</span></span>  
  
 <span data-ttu-id="c8e78-160">順次配送を有効にすると、既定値**再試行間隔**は 5 分です。</span><span class="sxs-lookup"><span data-stu-id="c8e78-160">When Ordered Delivery is enabled, the default **Retry Interval** is 5 minutes.</span></span> <span data-ttu-id="c8e78-161">パフォーマンスを向上させるには、[再試行の間隔] を最小値 (1 分) に設定します。</span><span class="sxs-lookup"><span data-stu-id="c8e78-161">To improve performance, set the Retry Interval to the lowest value, which is 1 minute.</span></span> <span data-ttu-id="c8e78-162">**再試行間隔**プロパティがゼロ (0) の値を受け入れることがありますが、ゼロ (0) が無効です。</span><span class="sxs-lookup"><span data-stu-id="c8e78-162">The **Retry Interval** property may accept a value of zero (0) but zero (0) is not valid.</span></span> <span data-ttu-id="c8e78-163">**再試行の回数**必要な回数を調整することできますも。</span><span class="sxs-lookup"><span data-stu-id="c8e78-163">The **Retry Count** can also be tuned to the number of retries needed.</span></span> <span data-ttu-id="c8e78-164">たとえば、リクエストを 1 分以内に処理する必要があり、送信ポート送信先がいつでもアクセスできる場合は、両方の値を 1 に設定します。</span><span class="sxs-lookup"><span data-stu-id="c8e78-164">For example, if you know the request should process in <1 minute and the send port destination is always accessible, set both values to 1.</span></span>  
  
 <span data-ttu-id="c8e78-165">再試行の値を変更するには[の送信ポートのトランスポート高度なオプションの構成方法](http://go.microsoft.com/fwlink/p/?LinkID=267697)です。</span><span class="sxs-lookup"><span data-stu-id="c8e78-165">To change the Retry values, go to [How to Configure Transport Advanced Options for a Send Port](http://go.microsoft.com/fwlink/p/?LinkID=267697).</span></span>  
  
 <span data-ttu-id="c8e78-166">順次配送の詳細については、次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8e78-166">For additional information on Ordered Delivery, refer to the following:</span></span>  
  
 [<span data-ttu-id="c8e78-167">エンド ツー エンド処理オプションのメッセージの順次配送を BizTalk:</span><span class="sxs-lookup"><span data-stu-id="c8e78-167">BizTalk: End-to-End Ordered Message Processing Options</span></span>](http://social.technet.microsoft.com/wiki/contents/articles/12887.biztalk-end-to-end-ordered-message-processing-options.aspx)  
  
 [<span data-ttu-id="c8e78-168">BizTalk: 順次配送</span><span class="sxs-lookup"><span data-stu-id="c8e78-168">BizTalk: Ordered Delivery</span></span>](http://social.technet.microsoft.com/wiki/contents/articles/6681.biztalk-ordered-delivery.aspx)  
  
## <a name="see-also"></a><span data-ttu-id="c8e78-169">参照</span><span class="sxs-lookup"><span data-stu-id="c8e78-169">See Also</span></span>  
 <span data-ttu-id="c8e78-170">[MSMQ アダプターでメッセージの配信を順序付け](../core/ordered-delivery-of-messages-with-the-msmq-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="c8e78-170">[Ordered Delivery of Messages with the MSMQ Adapter](../core/ordered-delivery-of-messages-with-the-msmq-adapter.md) </span></span>  
 [<span data-ttu-id="c8e78-171">MQSeries アダプタでメッセージの配信を順序付け</span><span class="sxs-lookup"><span data-stu-id="c8e78-171">Ordered Delivery of Messages with the MQSeries Adapter</span></span>](../core/ordered-delivery-of-messages-with-the-mqseries-adapter.md)