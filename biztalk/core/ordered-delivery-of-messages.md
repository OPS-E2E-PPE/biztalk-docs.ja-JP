---
title: メッセージの配信を順序付けられた |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52798c5f34c1f436d5c55954f61c6e18fcb2a398
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013019"
---
# <a name="ordered-delivery-of-messages"></a><span data-ttu-id="891f5-102">メッセージの順次配送</span><span class="sxs-lookup"><span data-stu-id="891f5-102">Ordered Delivery of Messages</span></span>
<span data-ttu-id="891f5-103">メッセージの順次配送とは、特定の順序でメッセージ ボックス データベースに公開されたメッセージを、それぞれ対応するサブスクライバーに (メッセージ ボックスに公開されたときと同じ順序で) 配送することです。</span><span class="sxs-lookup"><span data-stu-id="891f5-103">Ordered message delivery ensures that messages that are published to the MessageBox database in a given order are delivered to each matching subscriber in the same order in which they were published to the message box.</span></span>  
  
## <a name="configuring-ordered-message-delivery"></a><span data-ttu-id="891f5-104">メッセージの順次配送の構成</span><span class="sxs-lookup"><span data-stu-id="891f5-104">Configuring Ordered Message Delivery</span></span>  
 <span data-ttu-id="891f5-105">メッセージの順次配送は、次の場所で構成できます。</span><span class="sxs-lookup"><span data-stu-id="891f5-105">Ordered message delivery can be configured in the following places:</span></span>  
  
-   <span data-ttu-id="891f5-106">**受信**のオーケストレーションの図形</span><span class="sxs-lookup"><span data-stu-id="891f5-106">**Receive** shape in an orchestration</span></span>  
  
-   <span data-ttu-id="891f5-107">送信ポート</span><span class="sxs-lookup"><span data-stu-id="891f5-107">Send port</span></span>  
  
## <a name="ordered-delivery-with-existing-transports"></a><span data-ttu-id="891f5-108">既存のトランスポートでの順次配送</span><span class="sxs-lookup"><span data-stu-id="891f5-108">Ordered Delivery with Existing Transports</span></span>  
 <span data-ttu-id="891f5-109">トランスポートに使用されるプロトコルによっては、特に順次配送が必要ないものもあります (FILE や HTTP など)。</span><span class="sxs-lookup"><span data-stu-id="891f5-109">The protocols underlying certain transports, such as FILE and HTTP, are not consistent with the notion of ordered delivery.</span></span> <span data-ttu-id="891f5-110">ただし、このようなトランスポートの場合でもポートにバインドする場合、トランスポートが順次配送は、対象としてマークし、BizTalk Server では、順次配送を強制により、エントリの現在の 1 つが正常に送信されるまで、トランスポートは、[次へ] の送信メッセージが取得できません.</span><span class="sxs-lookup"><span data-stu-id="891f5-110">However, even with such transports, if the port bound to the transport is marked for ordered delivery, then BizTalk Server enforces ordered delivery by ensuring that the transport does not get the next outbound message until the current one has been successfully sent.</span></span> <span data-ttu-id="891f5-111">この機能を実現するために、BizTalk Server は、各メッセージを 1 つのバッチとしてトランスポートのアダプターに渡し、アダプターがそのメッセージをメッセージ ボックスから削除するまで待機してから、次のメッセージを別のバッチとしてアダプターに配送します。</span><span class="sxs-lookup"><span data-stu-id="891f5-111">To achieve this, BizTalk Server passes each message to the transport's adapter in a single batch and waits until the adapter has successfully deleted the message from the message box before delivering the next message, in another batch, to the adapter.</span></span>  
  
### <a name="ordered-delivery-for-custom-adapters"></a><span data-ttu-id="891f5-112">カスタム アダプターでの順次配送</span><span class="sxs-lookup"><span data-stu-id="891f5-112">Ordered Delivery for Custom Adapters</span></span>  
 <span data-ttu-id="891f5-113">カスタムの受信アダプターでは、特別に考慮しなければならない事柄があります。</span><span class="sxs-lookup"><span data-stu-id="891f5-113">There are special considerations for custom receive adapters.</span></span> <span data-ttu-id="891f5-114">順次配送をサポートするカスタム アダプターは、次のことを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="891f5-114">It you are writing a custom adapter that supports ordered delivery on receive, the adapter should do the following:</span></span>  
  
- <span data-ttu-id="891f5-115">カスタムの受信メッセージのバッチを送信した後にアダプターが待機する必要があります、 **BatchComplete**次のバッチを送信する前に、BizTalk Server からのコールバック。</span><span class="sxs-lookup"><span data-stu-id="891f5-115">After submitting a batch of messages, your custom receive adapter should wait for the **BatchComplete** callback from BizTalk Server before submitting the next batch.</span></span> <span data-ttu-id="891f5-116">詳細については、次を参照してください。 [Batch-Supported の受信アダプター用のインターフェイス](../core/interfaces-for-a-batch-supported-receive-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="891f5-116">For more details, see [Interfaces for a Batch-Supported Receive Adapter](../core/interfaces-for-a-batch-supported-receive-adapter.md).</span></span>  
  
- <span data-ttu-id="891f5-117">メッセージの処理がパイプラインで失敗した場合、そのメッセージを保留 (できれば再開不可に) する必要があります。</span><span class="sxs-lookup"><span data-stu-id="891f5-117">If a message fails in the pipeline, it should be suspended, preferably as nonresumable.</span></span> <span data-ttu-id="891f5-118">使用して、 **BTS します。SuspendAsNonResumable**メッセージ コンテキスト プロパティ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]にメッセージを適切にフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="891f5-118">Use the **BTS.SuspendAsNonResumable** message context property in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to flag the message appropriately.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="891f5-119">保留したメッセージが後で再開されると、メッセージの順序が破綻してしまいます。</span><span class="sxs-lookup"><span data-stu-id="891f5-119">Message order can be broken if a suspended message is later resumed.</span></span> <span data-ttu-id="891f5-120">このような事態を避けるためには、失敗したメッセージを再開不可として保留します。</span><span class="sxs-lookup"><span data-stu-id="891f5-120">If you do not want this behavior, suspend failed messages as nonresumable.</span></span>  
  
 <span data-ttu-id="891f5-121">カスタム アダプター作成の詳細については、次を参照してください。[カスタム アダプターの開発](../core/developing-custom-adapters.md)します。</span><span class="sxs-lookup"><span data-stu-id="891f5-121">For more details on building a custom adapter, see [Developing Custom Adapters](../core/developing-custom-adapters.md).</span></span>  
  
## <a name="conditions-for-end-to-end-ordered-message-processing"></a><span data-ttu-id="891f5-122">エンド ツー エンドの順次メッセージ処理を実現するための条件</span><span class="sxs-lookup"><span data-stu-id="891f5-122">Conditions for End-to-End Ordered Message Processing</span></span>  
 <span data-ttu-id="891f5-123">エンド ツー エンドの順次配送を実現するには、次の条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="891f5-123">To provide end-to-end ordered delivery the following conditions must be met:</span></span>  
  
- <span data-ttu-id="891f5-124">メッセージは、BizTalk Server に送信するメッセージの順序を保持できるアダプターで受信されなければなりません。</span><span class="sxs-lookup"><span data-stu-id="891f5-124">Messages must be received with an adapter that preserves the order of the messages when submitting them to BizTalk Server.</span></span> <span data-ttu-id="891f5-125">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には、この条件を満たすアダプターとして、MSMQ および MQSeries があります。</span><span class="sxs-lookup"><span data-stu-id="891f5-125">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], examples of such adapters are MSMQ and MQSeries.</span></span> <span data-ttu-id="891f5-126">HTTP アダプターまたは SOAP アダプターを使用して、メッセージを順次配送することもできますが、その場合は、HTTP クライアントまたは SOAP クライアント側で、正しい順序が維持されるよう配慮する必要があります (メッセージを 1 つずつ送信する)。</span><span class="sxs-lookup"><span data-stu-id="891f5-126">In addition, HTTP or SOAP adapters can be used to submit messages in order, but in that case the HTTP or SOAP client needs to enforce the order by submitting messages one at a time.</span></span>  
  
- <span data-ttu-id="891f5-127">これらのメッセージを持つ送信ポートをサブスクライブする必要があります、**順次配送**オプションに設定されて`True`します。</span><span class="sxs-lookup"><span data-stu-id="891f5-127">You must subscribe to these messages with a send port that has the **Ordered Delivery** option set to `True`.</span></span>  
  
- <span data-ttu-id="891f5-128">プロセスがメッセージをオーケストレーションのインスタンスが 1 つだけを使用する必要がありますにオーケストレーションを使用する場合、オーケストレーションを構成して、シーケンシャルなコンボイを使用する必要がある、**順次配送**のプロパティ、オーケストレーションの受信ポートに設定する必要があります`True`します。</span><span class="sxs-lookup"><span data-stu-id="891f5-128">If an orchestration is used to process the messages, only a single instance of the orchestration should be used, the orchestration should be configured to use a sequential convoy, and the **Ordered Delivery** property of the orchestration's receive port should be set to `True`.</span></span>  
  
## <a name="restrictions"></a><span data-ttu-id="891f5-129">制限</span><span class="sxs-lookup"><span data-stu-id="891f5-129">Restrictions</span></span>  
 <span data-ttu-id="891f5-130">メッセージの順次配送は、次のサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="891f5-130">Ordered delivery of messages is not supported for the following:</span></span>  
  
- <span data-ttu-id="891f5-131">動的送信ポート[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]と以前のバージョン</span><span class="sxs-lookup"><span data-stu-id="891f5-131">Dynamic send ports in [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)] and previous versions</span></span>

- <span data-ttu-id="891f5-132">動的送信ポート[!INCLUDE[bts2016_md](../includes/bts2016-md.md)](および以降のバージョン) のアダプターの種類を**しない**順次配送の静的送信ポートのサポート</span><span class="sxs-lookup"><span data-stu-id="891f5-132">Dynamic send ports in [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] (and any newer versions) for those adapter types that **don't** support ordered delivery on static send ports</span></span>
  
- <span data-ttu-id="891f5-133">バックアップ トランスポート</span><span class="sxs-lookup"><span data-stu-id="891f5-133">Backup transports</span></span>  

  
## <a name="interactions"></a><span data-ttu-id="891f5-134">他の設定との関係</span><span class="sxs-lookup"><span data-stu-id="891f5-134">Interactions</span></span>  
 <span data-ttu-id="891f5-135">送信ポートに対して順次配送を構成する場合、他の設定との関係に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="891f5-135">When ordered delivery is configured for a send port, be aware of the following interactions with other configured behaviors in BizTalk Server:</span></span>  
  
-   <span data-ttu-id="891f5-136">同じ送信ポートの "現在のメッセージが失敗したときに、後続のメッセージの送信を停止する" 設定</span><span class="sxs-lookup"><span data-stu-id="891f5-136">For the "Stop sending subsequent messages on current message failure" setting on the same send port:</span></span>  
  
    -   <span data-ttu-id="891f5-137">**False です。**</span><span class="sxs-lookup"><span data-stu-id="891f5-137">**False.**</span></span> <span data-ttu-id="891f5-138">失敗したメッセージだけが (再開不可として) 保留にされ、以降のすべてのメッセージは引き続き処理されます。</span><span class="sxs-lookup"><span data-stu-id="891f5-138">Only the failed message is suspended (as not resumable) and all subsequent messages continue to be processed.</span></span> <span data-ttu-id="891f5-139">これにより、失敗しなかったメッセージの順序は維持されますが、元の順序に抜けが生じることになります。</span><span class="sxs-lookup"><span data-stu-id="891f5-139">This preserves the ordering of the non-failed messages but can result in gaps in the sequence.</span></span> <span data-ttu-id="891f5-140">たとえば、101、102、103 という順序で受信され、102 が保留状態になった場合、101 と 103 については正しい順番で処理されます。</span><span class="sxs-lookup"><span data-stu-id="891f5-140">For example, if orders 101, 102, and 103 are received and order 102 is suspended, orders 101 and 103 will continue to be processed in order.</span></span>  
  
    -   <span data-ttu-id="891f5-141">**True です。**</span><span class="sxs-lookup"><span data-stu-id="891f5-141">**True.**</span></span> <span data-ttu-id="891f5-142">いずれかのメッセージで処理が失敗した場合、送信ポートのインスタンスが保留状態になります。</span><span class="sxs-lookup"><span data-stu-id="891f5-142">The send port instance is suspended if any of the messages fails processing.</span></span> <span data-ttu-id="891f5-143">これにより、順次配送の設定された、後続のすべてのメッセージが保留されます。</span><span class="sxs-lookup"><span data-stu-id="891f5-143">This causes all subsequent messages in the ordered set of messages to be suspended.</span></span> <span data-ttu-id="891f5-144">後続のメッセージが、失敗したメッセージよりも前に配送されることはないため、メッセージの順序は完全に維持されます。</span><span class="sxs-lookup"><span data-stu-id="891f5-144">This preserves message order by preventing delivery of subsequent messages before delivery of the failed message.</span></span>  
  
-   <span data-ttu-id="891f5-145">送信請求 - 応答の送信ポートで、"現在のメッセージが失敗したときに、後続のメッセージの送信を停止する" プロパティが `true` に設定され、応答の受信パイプラインの逆アセンブル ステージで復旧可能な交換処理が構成されていた場合、応答を逆アセンブルしているときに復旧可能なエラーが発生したとしても、送信ポートはメッセージの送信を中断しません (つまり、インスタンスは保留状態になりません)。</span><span class="sxs-lookup"><span data-stu-id="891f5-145">If a solicit-response send port has the "Stop sending subsequent messages on current message failure" property set to `true`, and if recoverable interchange processing is configured for the disassembly stage of the receive pipeline for the response, then the send port does not stop sending messages (that is, the instance is not suspended) if there is a recoverable error in disassembling the response.</span></span>  
  
-   <span data-ttu-id="891f5-146">順次配送の設定された送信ポートを削除する場合は、関連付けられたインスタンスが存在しないことを確認しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="891f5-146">Before deleting an ordered send port, ensure that there are no instances associated with it.</span></span> <span data-ttu-id="891f5-147">関連付けられたインスタンスが存在する場合は、それを終了させてから、送信ポートを削除します。</span><span class="sxs-lookup"><span data-stu-id="891f5-147">If there are associated instances, you should terminate them before deleting the send port.</span></span>  
  
## <a name="ordered-delivery-to-file-transport"></a><span data-ttu-id="891f5-148">ファイル トランスポートへの順次配送</span><span class="sxs-lookup"><span data-stu-id="891f5-148">Ordered Delivery to File Transport</span></span>  
 <span data-ttu-id="891f5-149">ファイル アダプターには、メッセージが順に到着します。</span><span class="sxs-lookup"><span data-stu-id="891f5-149">Messages arrive at the File adapter in sequence.</span></span> <span data-ttu-id="891f5-150">ファイル アダプターでは、メッセージを単一のファイルに追加していくか、個別のファイルとして書き出します。</span><span class="sxs-lookup"><span data-stu-id="891f5-150">The File adapter may append messages to a single file or write out a sequence of files, with the following results:</span></span>  
  
-   <span data-ttu-id="891f5-151">メッセージ データが単一のファイルに追加される場合、各メッセージは順番に追加されていきます。</span><span class="sxs-lookup"><span data-stu-id="891f5-151">If message data is appended to a single file, individual messages are appended in order.</span></span> <span data-ttu-id="891f5-152">ファイル アダプターを使用する送信ポートの順次配送オプションは、送信トランスポートが追加モードで動作している場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="891f5-152">The ordered delivery option on a send port that uses the FILE adapter only makes sense if the send transport works in append mode</span></span>  
  
-   <span data-ttu-id="891f5-153">メッセージが個別のファイルに出力される場合、その順番がファイル名に反映されます。つまり、到着した順番に基づいてファイル名が付けられます。</span><span class="sxs-lookup"><span data-stu-id="891f5-153">If messages are written to individual files, the order is reflected in the file names, which are sequentially named.</span></span> <span data-ttu-id="891f5-154">このとき、アダプターによって書き込まれたファイルでは、時系列 (ファイルの作成日時や更新時刻など) に関するファイル システムのプロパティには、メッセージが到着した順序は反映されません。</span><span class="sxs-lookup"><span data-stu-id="891f5-154">In this case, for files written by the adapter, file system properties relating to chronology (for example, file creation time or modification time) do not necessarily reflect the message arrival sequence.</span></span>  
  
## <a name="performance-impact-of-ordered-delivery"></a><span data-ttu-id="891f5-155">順次配送がパフォーマンスに与える影響</span><span class="sxs-lookup"><span data-stu-id="891f5-155">Performance Impact of Ordered Delivery</span></span>  
 <span data-ttu-id="891f5-156">BizTalk Server は、順次配送を実現するために、メッセージ経路のさまざまな地点において、メッセージを順番どおりに処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="891f5-156">To achieve ordered delivery, BizTalk Server must serialize processing of ordered messages at various points along the message pathway.</span></span> <span data-ttu-id="891f5-157">そのため、複数のホスト インスタンスを使用して、メッセージを並列処理するなどのスケール アウト手段が通用しなくなります。</span><span class="sxs-lookup"><span data-stu-id="891f5-157">This works against scale-out techniques, such as the use of multiple host instances for parallel processing of messages.</span></span> <span data-ttu-id="891f5-158">順次配送を行う場合、複数のホスト インスタンスで動作するように構成されたポートであっても、複数のホスト インスタンスで実行させることはできません。順次配送を行うには、単一のホスト インスタンスで動作させる必要があるためです。</span><span class="sxs-lookup"><span data-stu-id="891f5-158">When using ordered delivery, even ports configured to run on multiple host instances run only on a single host instance to ensure ordered delivery.</span></span> <span data-ttu-id="891f5-159">ただし、複数のホスト インスタンスの場合でも、高い可用性のメリットは享受できます。メッセージの順次配送を処理するホスト インスタンスで障害が発生した場合、処理に失敗したメッセージは利用可能な別のホスト インスタンスで再処理されます。</span><span class="sxs-lookup"><span data-stu-id="891f5-159">However, in this situation, high availability is still maintained because the failure of a host instance that is processing ordered delivery of messages results in reprocessing of the failed message on another available host instance.</span></span>  
  
 <span data-ttu-id="891f5-160">順次配送が有効な場合、既定値**再試行間隔**は 5 分です。</span><span class="sxs-lookup"><span data-stu-id="891f5-160">When Ordered Delivery is enabled, the default **Retry Interval** is 5 minutes.</span></span> <span data-ttu-id="891f5-161">パフォーマンスを向上させるには、[再試行の間隔] を最小値 (1 分) に設定します。</span><span class="sxs-lookup"><span data-stu-id="891f5-161">To improve performance, set the Retry Interval to the lowest value, which is 1 minute.</span></span> <span data-ttu-id="891f5-162">**再試行間隔**プロパティがゼロ (0) の値を受け入れることがありますが、ゼロ (0) が無効です。</span><span class="sxs-lookup"><span data-stu-id="891f5-162">The **Retry Interval** property may accept a value of zero (0) but zero (0) is not valid.</span></span> <span data-ttu-id="891f5-163">**再試行の回数**も必要な回数を調整できます。</span><span class="sxs-lookup"><span data-stu-id="891f5-163">The **Retry Count** can also be tuned to the number of retries needed.</span></span> <span data-ttu-id="891f5-164">たとえば、リクエストを 1 分以内に処理する必要があり、送信ポート送信先がいつでもアクセスできる場合は、両方の値を 1 に設定します。</span><span class="sxs-lookup"><span data-stu-id="891f5-164">For example, if you know the request should process in <1 minute and the send port destination is always accessible, set both values to 1.</span></span>  
  
 <span data-ttu-id="891f5-165">再試行の値を変更するには[送信ポートのトランスポート詳細設定オプションの構成方法](http://go.microsoft.com/fwlink/p/?LinkID=267697)します。</span><span class="sxs-lookup"><span data-stu-id="891f5-165">To change the Retry values, go to [How to Configure Transport Advanced Options for a Send Port](http://go.microsoft.com/fwlink/p/?LinkID=267697).</span></span>  
  
 <span data-ttu-id="891f5-166">順次配送の詳細については、次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="891f5-166">For additional information on Ordered Delivery, refer to the following:</span></span>  
  
 [<span data-ttu-id="891f5-167">エンド ツー エンドのオプションを処理するメッセージの順次配送を BizTalk:</span><span class="sxs-lookup"><span data-stu-id="891f5-167">BizTalk: End-to-End Ordered Message Processing Options</span></span>](http://social.technet.microsoft.com/wiki/contents/articles/12887.biztalk-end-to-end-ordered-message-processing-options.aspx)  
  
 [<span data-ttu-id="891f5-168">BizTalk: 順次配送</span><span class="sxs-lookup"><span data-stu-id="891f5-168">BizTalk: Ordered Delivery</span></span>](http://social.technet.microsoft.com/wiki/contents/articles/6681.biztalk-ordered-delivery.aspx)  
  
## <a name="see-also"></a><span data-ttu-id="891f5-169">参照</span><span class="sxs-lookup"><span data-stu-id="891f5-169">See Also</span></span>  
 <span data-ttu-id="891f5-170">[MSMQ アダプターでメッセージの配信を順序付け](../core/ordered-delivery-of-messages-with-the-msmq-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="891f5-170">[Ordered Delivery of Messages with the MSMQ Adapter](../core/ordered-delivery-of-messages-with-the-msmq-adapter.md) </span></span>  
 [<span data-ttu-id="891f5-171">MQSeries アダプターを使用したメッセージの順次配送</span><span class="sxs-lookup"><span data-stu-id="891f5-171">Ordered Delivery of Messages with the MQSeries Adapter</span></span>](../core/ordered-delivery-of-messages-with-the-mqseries-adapter.md)