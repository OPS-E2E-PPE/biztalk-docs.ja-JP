---
title: "バッチ EDI インターチェンジをアセンブル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 18f64595-935e-4d52-9ec2-5edf7c2b9e83
caps.latest.revision: "45"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c4274362e5ec8441e203d0b2b97f27e95235fd9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="assembling-a-batched-edi-interchange"></a><span data-ttu-id="d9712-102">バッチ EDI インターチェンジのアセンブル</span><span class="sxs-lookup"><span data-stu-id="d9712-102">Assembling a Batched EDI Interchange</span></span>
<span data-ttu-id="d9712-103">個々のトランザクション セット バッチ要素を EDI インターチェンジにアセンブルするために、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI および AS2 は以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="d9712-103">To assemble individual transaction-set batch elements into an EDI interchange, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI and AS2 does the following:</span></span>  
  
-   <span data-ttu-id="d9712-104">バッチ処理用のバッチ要素を識別する。</span><span class="sxs-lookup"><span data-stu-id="d9712-104">Identifies batch elements for batching</span></span>  
  
-   <span data-ttu-id="d9712-105">受信時に個々のバッチ要素を検証しバッファーする。</span><span class="sxs-lookup"><span data-stu-id="d9712-105">Validates and buffers individual batch elements upon receipt</span></span>  
  
-   <span data-ttu-id="d9712-106">リリース条件が満たされた時点で、特定のバッチ要素を取得し、バッチ インターチェンジをアセンブルする。</span><span class="sxs-lookup"><span data-stu-id="d9712-106">Retrieves specific batch elements and assembles a batched interchange when the release criteria is met</span></span>  
  
 <span data-ttu-id="d9712-107">個々のメッセージが収集されバッチに追加される開始時刻は、バッチ アクティベーション条件により決定されます。</span><span class="sxs-lookup"><span data-stu-id="d9712-107">The start time for collection of individual messages to go into a batch is determined by the batch activation criteria.</span></span> <span data-ttu-id="d9712-108">バッチがリリースされる時刻は、バッチ リリース条件により決定されます。</span><span class="sxs-lookup"><span data-stu-id="d9712-108">The time at which the batch is released is determined by the batch release criteria.</span></span> <span data-ttu-id="d9712-109">これら 2 つの条件のセットの詳細については、次を参照してください。[送信バッチの構成](../core/configuring-an-outgoing-batch.md)です。</span><span class="sxs-lookup"><span data-stu-id="d9712-109">For more information about these two sets of criteria, see [Configuring an Outgoing Batch](../core/configuring-an-outgoing-batch.md).</span></span>  
  
## <a name="message-flow-for-outgoing-batched-messages"></a><span data-ttu-id="d9712-110">送信バッチ メッセージのメッセージ フロー</span><span class="sxs-lookup"><span data-stu-id="d9712-110">Message Flow for Outgoing Batched Messages</span></span>  
 <span data-ttu-id="d9712-111">送信メッセージをバッチ処理するように [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンポーネントは次の一連の手順を実行して、送信用のバッチ メッセージを準備します。</span><span class="sxs-lookup"><span data-stu-id="d9712-111">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is configured to batch an outgoing message, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] components will perform the following series of steps to prepare the batched message for sending.</span></span> <span data-ttu-id="d9712-112">この一連の手順では、BatchMarker パイプライン コンポーネントを備えた EDIReceive パイプラインが、送信用にバッチ処理されるトランザクション セットを含む受信インターチェンジを処理するケースを説明します。</span><span class="sxs-lookup"><span data-stu-id="d9712-112">This series of steps describes the case in which the EDIReceive pipeline with the BatchMarker pipeline component processes the received interchanges that contain transaction sets to be batched for sending.</span></span>  
  
1.  <span data-ttu-id="d9712-113">EDIReceive パイプラインの BatchMarker パイプライン コンポーネントが、パーティのプロパティの EDI バッチ フィルター設定から、どのメッセージをバッチ処理する必要があるか判断します </span><span class="sxs-lookup"><span data-stu-id="d9712-113">The BatchMarker pipeline component in the EDIReceive pipeline determines which messages need to be batched from the EDI batch filter settings in the party properties.</span></span> <span data-ttu-id="d9712-114">(このコンポーネントは、バッチ フィルター設定を参照し、それに基づいて処理を行う唯一のバッチ処理コンポーネントです)。</span><span class="sxs-lookup"><span data-stu-id="d9712-114">(This is the only batching component that looks at the batch filter settings and acts upon them.)</span></span>  
  
2.  <span data-ttu-id="d9712-115">1 つのバッチ構成のフィルター設定のみがメッセージをサブスクライブしている場合、BatchMarker コンポーネントは、`EDI.ToBeBatched = True` プロパティの昇格を実行します。</span><span class="sxs-lookup"><span data-stu-id="d9712-115">If the filter settings of only one batch configuration subscribes to a message, the BatchMarker component will promote the property `EDI.ToBeBatched = True`.</span></span> <span data-ttu-id="d9712-116">これにより、バッチ処理オーケストレーションはメッセージを確実に取得します。</span><span class="sxs-lookup"><span data-stu-id="d9712-116">This ensures that the batching orchestration will pick up the message.</span></span>  
  
3.  <span data-ttu-id="d9712-117">複数のバッチ構成のフィルター設定がメッセージのコンテキストに一致する場合、BatchMarker コンポーネントは `EDI.ToBeRouted = True` プロパティの昇格を実行し、`EDI.BatchIds` プロパティを、一致するバッチ ID を含むスペースで区切られた一覧に設定します。</span><span class="sxs-lookup"><span data-stu-id="d9712-117">If the filter settings of more than one batch configuration match the context of a message, the BatchMarker component promotes the properties `EDI.ToBeRouted = True` and sets the `EDI.BatchIds` property to a space delimited list containing the matching batch IDs.</span></span>  <span data-ttu-id="d9712-118">これにより、ルーティング オーケストレーションはメッセージを確実にサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="d9712-118">This ensures that the routing orchestration will subscribe to the message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d9712-119">カスタム受信パイプラインまたはカスタム オーケストレーションで適切なコンテキスト プロパティを昇格させることができます。</span><span class="sxs-lookup"><span data-stu-id="d9712-119">You can promote the appropriate context properties in a custom receive pipeline or a custom orchestration.</span></span> <span data-ttu-id="d9712-120">カスタム受信パイプラインは、BatchMarker パイプライン コンポーネントを使用したり、BatchMarker パイプライン コンポーネントを使用せずにプロパティを昇格したりできます。</span><span class="sxs-lookup"><span data-stu-id="d9712-120">The custom receive pipeline can use the BatchMarker pipeline component, or can promote the properties without using the BatchMarker pipeline component.</span></span>  
  
4.  <span data-ttu-id="d9712-121">ルーティング オーケストレーションは、`EDI.ToBeRouted = True` で、さらに `EDI.BatchIds` が昇格されているトランザクション セットを取得し、そのトランザクション セットのコピーを作成して、`EDI.BatchIds` に含まれている各バッチ ID のコピーが確実に存在するようにします。</span><span class="sxs-lookup"><span data-stu-id="d9712-121">The routing orchestration picks up any transaction set for which `EDI.ToBeRouted = True` and `EDI.BatchIds` is promoted, and then creates copies of the transaction set, ensuring that there is a copy for each batch ID contained in `EDI.BatchIds`.</span></span> <span data-ttu-id="d9712-122">ルーティング オーケストレーションは `EDI.ToBeBatched = True` を設定し、`EDI.BatchId` は、トランザクション セットの各コピー用の一致するバッチ構成のバッチ ID に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d9712-122">The routing orchestration sets `EDI.ToBeBatched = True` and `EDI.BatchId` is set to the batch ID of the matching batch configuration for each copy of the transaction set.</span></span> <span data-ttu-id="d9712-123">これにより、バッチ処理用のバッチ処理オーケストレーションはトランザクション セットを確実に取得します。</span><span class="sxs-lookup"><span data-stu-id="d9712-123">This ensures that the transaction sets will be picked up by the batching orchestration for batching.</span></span>  
  
5.  <span data-ttu-id="d9712-124">バッチ処理オーケストレーションは、次のプロパティが昇格されているすべてのメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="d9712-124">The batching orchestration picks up all messages for which the following properties have been promoted:</span></span>  
  
    -   <span data-ttu-id="d9712-125">`EDI.ToBeBatched = True` と、EDI.BatchId = バッチ処理オーケストレーションのこのインスタンスに関連付けられたバッチのバッチ ID。</span><span class="sxs-lookup"><span data-stu-id="d9712-125">`EDI.ToBeBatched = True` and EDI.BatchId = the batch id of the batch associated with this instance of the batching orchestration.</span></span>  
  
    -   <span data-ttu-id="d9712-126">`EDI.ToBeBatched = True` と EDI.BatchName = 構成されているバッチの名前、さらに EDI.DestinationPartyName = バッチ構成を含むパーティの名前。</span><span class="sxs-lookup"><span data-stu-id="d9712-126">`EDI.ToBeBatched = True` and EDI.BatchName = the name of the configured batch and EDI.DestinationPartyName = the party name that contains the batch configuration.</span></span>  
  
     <span data-ttu-id="d9712-127">(BatchMarker パイプライン コンポーネントを備えた) EDIReceive パイプラインにより着信メッセージが処理される場合、バッチ処理オーケストレーションは、X12 または EDIFACT でエンコードされたトランザクション セットのみをバッチ処理します。</span><span class="sxs-lookup"><span data-stu-id="d9712-127">When the incoming messages are processed by the EDIReceive pipeline (with the BatchMarker pipeline component), the batching orchestration will batch only X12- or EDIFACT-encoded transaction sets.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d9712-128">アクティブなバッチ構成ごとにバッチ処理オーケストレーションのインスタンスが 1 つ存在し、個々のインスタンスが特定のバッチ ID をサブスクライブしています。</span><span class="sxs-lookup"><span data-stu-id="d9712-128">There will be one instance of the batching orchestration for each active batch configuration, each subscribing to a specific batch ID.</span></span> <span data-ttu-id="d9712-129">新しいバッチ構成を作成するときに、バッチ ID の値が自動的に設定されます、**識別**のセクションで、**バッチ処理構成**の一方向アグリーメント タブのページ、 **アグリーメントのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="d9712-129">The batch ID value is set automatically when creating a new batch configuration in the **Identification** section of the **Batching Configuration** page of the one-way agreement tab of the **Agreement Properties** dialog box.</span></span>  
  
6.  <span data-ttu-id="d9712-130">バッチ処理オーケストレーションが、バッチ処理対象の各トランザクション セットを検証します。</span><span class="sxs-lookup"><span data-stu-id="d9712-130">The batching orchestration validates each transaction set to be batched.</span></span> <span data-ttu-id="d9712-131">トランザクション セットの検証が失敗した場合、`EDI.BatchItemValidationFailure` コンテキスト プロパティが "True" に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d9712-131">If the transaction set fails validation, it sets the `EDI.BatchItemValidationFailure` context property to "True".</span></span> <span data-ttu-id="d9712-132">**BatchSuspend**オーケストレーションがそのコンテキスト プロパティに基づいてメッセージを取得し、エラー情報を送信およびが中断し、します。</span><span class="sxs-lookup"><span data-stu-id="d9712-132">The **BatchSuspend** orchestration picks up the message based upon that context property, posts error information, and then is suspended.</span></span>  
  
7.  <span data-ttu-id="d9712-133">バッチのリリース条件が満たされている場合、バッチ処理オーケストレーションはバッチ要素をバッチにアセンブルし、エンベロープを作成します。</span><span class="sxs-lookup"><span data-stu-id="d9712-133">When the batch release criteria has been met, the batching orchestration assembles the batch elements into a batch and creates an envelope.</span></span>  
  
8.  <span data-ttu-id="d9712-134">バッチ処理オーケストレーションは、インターチェンジのバッチ処理を完了した後、そのインターチェンジの次のプロパティを昇格します。EDI.DestinationPartyName = %PartyName%、EDI.BatchEncodingType = X12 または EDIFACT、および EDI.ToBeBatched = False。</span><span class="sxs-lookup"><span data-stu-id="d9712-134">After the batching orchestration completes batching an interchange, it promotes the following properties on that interchange: EDI.DestinationPartyName = %PartyName%, EDI.BatchEncodingType = X12 or EDIFACT, and EDI.ToBeBatched = False.</span></span>  
  
9. <span data-ttu-id="d9712-135">送信ポートは、EDI に基づくバッチ トランザクション セットを取得します。DestinationPartyName = \<PartyName\>、EDI です。BatchEncodingType = EDIFACT または X12、および EDI です。ToBeBatched = False。</span><span class="sxs-lookup"><span data-stu-id="d9712-135">A send port picks up the batched transaction sets based on EDI.DestinationPartyName = \<PartyName\>, EDI.BatchEncodingType = EDIFACT or X12, and EDI.ToBeBatched = False.</span></span>  
  
## <a name="batching-orchestration-control-messages"></a><span data-ttu-id="d9712-136">バッチ処理オーケストレーションのコントロール メッセージ</span><span class="sxs-lookup"><span data-stu-id="d9712-136">Batching Orchestration Control Messages</span></span>  
 <span data-ttu-id="d9712-137">バッチ処理オーケストレーションは、次のコントロール メッセージによりアクティブ化、終了、または上書きされます。</span><span class="sxs-lookup"><span data-stu-id="d9712-137">The batching orchestration is activated, terminated, or overridden by the following control messages:</span></span>  
  
-   <span data-ttu-id="d9712-138">**BatchActivation**: オーケストレーションはこのメッセージを受け取る、バッチ処理オーケストレーションのインスタンスが作成され、オーケストレーションがアクティブに (バッチ アクティベーション条件を満たしている) 場合は、バッチ要素を受け取るときにします。</span><span class="sxs-lookup"><span data-stu-id="d9712-138">**BatchActivation**: When the orchestration receives this message, an instance of the batching orchestration is created and the orchestration is active to receive batch elements (if it meets the batch activation criteria).</span></span> <span data-ttu-id="d9712-139">クリックしてこのコントロール メッセージを送信、**開始**でバッチ構成 ボタン、**バッチ処理構成**の一方向アグリーメント タブのページ、 **アグリーメントのプロパティ**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="d9712-139">This control message is sent by clicking the **Start** button of a batch configuration on the **Batching Configuration** page of the one-way agreement tab of the **Agreement Properties** dialog box.</span></span>  
  
-   <span data-ttu-id="d9712-140">**BatchTermination**: オーケストレーションは、このメッセージを受信したときに、既存のバッチ要素からバッチを作成、メッセージを MessageBox に公開およびを終了します。</span><span class="sxs-lookup"><span data-stu-id="d9712-140">**BatchTermination**: When the orchestration receives this message, it creates a batch from existing batch elements, publishes the message to the MessageBox, and terminates.</span></span> <span data-ttu-id="d9712-141">クリックしてこのコントロール メッセージが送信される、**停止**でバッチ構成 ボタン、**バッチ処理構成**の一方向アグリーメント タブのページ、 **アグリーメントのプロパティ**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="d9712-141">This control message is sent by clicking the **Stop** button of a batch configuration on the **Batching Configuration** page of the one-way agreement tab of the **Agreement Properties** dialog box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d9712-142">指定された期間に到達した場合も、オーケストレーションは終了、**エンドによって**プロパティに、**終了**のセクションで、**バッチ処理構成**のページ、一方向アグリーメント タブの**アグリーメントのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="d9712-142">The orchestration is also terminated if it reaches the time specified for the **End-by** property in the **Termination** section of the **Batching Configuration** page of the one-way agreement tab of the **Agreement Properties** dialog box.</span></span>  
  
-   <span data-ttu-id="d9712-143">**BatchOverride**: オーケストレーションは、このメッセージを受信したときに、既存の要素からバッチを作成、メッセージを MessageBox に公開およびし、次のバッチ メッセージを待機します。</span><span class="sxs-lookup"><span data-stu-id="d9712-143">**BatchOverride**: When the orchestration receives this message, it creates a batch from existing elements, publishes the message to the MessageBox, and then waits for messages for the next batch.</span></span> <span data-ttu-id="d9712-144">クリックしてこのコントロール メッセージを送信、**オーバーライド**でバッチ構成 ボタン、**バッチ処理構成**の一方向アグリーメント タブのページ、 **アグリーメントのプロパティ**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="d9712-144">This control message is sent by clicking the **Override** button of a batch configuration on the **Batching Configuration** page of the one-way agreement tab of the **Agreement Properties** dialog box.</span></span>  
  
 <span data-ttu-id="d9712-145">バッチ処理オーケストレーションは、BatchControlMessageRecvLoc 受信場所を介してコントロール メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="d9712-145">The batching orchestration receives the control messages via the BatchControlMessageRecvLoc receive location.</span></span> <span data-ttu-id="d9712-146">この SQL 受信場所のポーリング間隔は 30 秒に既定で設定されていますに変更することができます、 **SQL トランスポートのプロパティ**受信場所のダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="d9712-146">The polling interval for this SQL receive location is set by default to 30 seconds, but can be changed in the **SQL Transport Properties** dialog box for the receive location.</span></span> <span data-ttu-id="d9712-147">ポーリング間隔を短くすると、コントロール メッセージを送信するアクションを実行した後すぐに (バッチ処理オーケストレーションを開始した場合など)、BatchControlMessageRecvLoc 受信場所でコントロール メッセージが受信されます。</span><span class="sxs-lookup"><span data-stu-id="d9712-147">Decreasing the polling interval will ensure that the BatchControlMessageRecvLoc receive location will receive a control message soon after you perform the action that sent the control message (such as when you start the batching orchestration).</span></span>  
  
 <span data-ttu-id="d9712-148">バッチ オーケストレーションを開始すると、次の手順が実行されます。</span><span class="sxs-lookup"><span data-stu-id="d9712-148">The following steps occur when you start a batch orchestration:</span></span>  
  
1.  <span data-ttu-id="d9712-149">クリックすると、**開始**ボタン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]どのパーティおよびバッチ id が、バッチ オーケストレーションをアクティブにすることを示すテーブルにレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="d9712-149">When you click the **Start** button, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] creates a record in a table indicating which party and batch id you are activating the batch orchestration for.</span></span>  
  
2.  <span data-ttu-id="d9712-150">BatchControlMessageRecvLoc 受信場所に関連付けられている SQL アダプターがポーリングを実行し、データベース内にレコードが存在しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="d9712-150">The SQL adapter associated with the BatchControlMessageRecvLoc receive location polls to see if the record exists in the database.</span></span>  
  
3.  <span data-ttu-id="d9712-151">レコードが存在している場合、SQL アダプターは、レコード内の情報を使用してコントロール メッセージを構築します。</span><span class="sxs-lookup"><span data-stu-id="d9712-151">If the record exists, the SQL adapter builds a control message, using information in the record.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d9712-152">このような方法でコントロール メッセージが構築されるので、オーケストレーションを無効なコントロール メッセージで開始することはできません。</span><span class="sxs-lookup"><span data-stu-id="d9712-152">Building the control message in this way ensures that the orchestration cannot be started by an invalid control message.</span></span>  
  
4.  <span data-ttu-id="d9712-153">BatchControlMessageRecvLoc 受信場所でコントロール メッセージが受信され、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によりバッチ処理オーケストレーション インスタンスがアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="d9712-153">The BatchControlMessageRecvLoc receive location receives the control message, and [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] activates a batching orchestration instance.</span></span>  
  
## <a name="batch-components"></a><span data-ttu-id="d9712-154">バッチ コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d9712-154">Batch Components</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="d9712-155"> EDI は、次のコンポーネントを使用して、XML トランザクション セットを EDI インターチェンジにバッチ処理します。</span><span class="sxs-lookup"><span data-stu-id="d9712-155"> EDI batches XML transaction sets into EDI interchanges using the following components:</span></span>  
  
-   <span data-ttu-id="d9712-156">EDI 受信パイプラインの BatchMarkerReceivePipelineComponent</span><span class="sxs-lookup"><span data-stu-id="d9712-156">BatchMarkerReceivePipelineComponent in the EDI receive pipeline</span></span>  
  
-   <span data-ttu-id="d9712-157">ルーティング オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="d9712-157">Routing Orchestration</span></span>  
  
-   <span data-ttu-id="d9712-158">バッチ処理オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="d9712-158">Batching Orchestration</span></span>  
  
-   <span data-ttu-id="d9712-159">バッチ処理オーケストレーションをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="d9712-159">Upgrade Batching Orchestration</span></span>  
  
-   <span data-ttu-id="d9712-160">BatchSuspend オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="d9712-160">BatchSuspend Orchestration</span></span>  
  
-   <span data-ttu-id="d9712-161">EDI 送信パイプライン</span><span class="sxs-lookup"><span data-stu-id="d9712-161">EDI Send Pipeline</span></span>  
  
 <span data-ttu-id="d9712-162">これらのコンポーネントは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI および AS2 をインストールして構成するときに DLL としてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="d9712-162">These components are installed as DLLs when you install and configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI and AS2.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d9712-163">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI および AS2 のバッチ処理コンポーネントは、バッチのトランザクション セットの順序を保証しません。</span><span class="sxs-lookup"><span data-stu-id="d9712-163">The batching components in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI and AS2 do not guarantee the ordering of the transaction sets in a batch.</span></span>  
  
### <a name="batchmarkerreceivepipelinecomponent"></a><span data-ttu-id="d9712-164">BatchMarkerReceivePipelineComponent</span><span class="sxs-lookup"><span data-stu-id="d9712-164">BatchMarkerReceivePipelineComponent</span></span>  
 <span data-ttu-id="d9712-165">EDI 受信パイプラインの BatchMarkerReceivePipelineComponent により、バッチ処理オーケストレーションは、バッチ処理対象のメッセージを取得できます。</span><span class="sxs-lookup"><span data-stu-id="d9712-165">BatchMarkerReceivePipelineComponent in the EDI receive pipeline enables the batching orchestration to pick up messages to be batched.</span></span> <span data-ttu-id="d9712-166">このパイプライン コンポーネントは、EDI 受信パイプラインの逆アセンブラーの後に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d9712-166">This pipeline component is applied after the Disassembler in the EDI Receive Pipeline.</span></span> <span data-ttu-id="d9712-167">コンポーネントで設定されたフィルター条件の評価、**フィルター**のセクションで、**バッチ処理構成**の一方向アグリーメント タブのページ、**アグリーメントのプロパティ**ダイアログ ボックスで、およびルーティングを処理し、バッチ処理オーケストレーションの次のコンテキスト プロパティでのトランザクション セットのマーク</span><span class="sxs-lookup"><span data-stu-id="d9712-167">The component evaluates the filter criteria set in the **Filter** section of the **Batching Configuration** page of the one-way agreement tab of the **Agreement Properties** dialog box, and marks the transaction sets with the following context properties for processing by the routing and batching orchestrations</span></span>  
  
-   <span data-ttu-id="d9712-168">単一のパーティがバッチ処理対象のメッセージをサブスクライブしている場合、`ToBeBatched = True` という昇格が実行され、BatchId は一致するバッチ構成のバッチ ID の値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d9712-168">If a single party subscribes to a message to be batched, it promotes `ToBeBatched = True` and BatchId is set to the value of the batch ID of the matching batch configuration.</span></span> <span data-ttu-id="d9712-169">これにより、バッチ処理オーケストレーションによる取得が可能になります。</span><span class="sxs-lookup"><span data-stu-id="d9712-169">This enables pickup by the batching orchestration.</span></span>  
  
-   <span data-ttu-id="d9712-170">複数のバッチがバッチ処理対象のメッセージをサブスクライブしている場合、`ToBeRouted = True` という昇格が実行され、さらに `EDI.BatchIds` プロパティ セットがバッチ ID のスペースで区切られた一覧に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d9712-170">If multiple batches subscribe to a message to be batched, it promotes `ToBeRouted = True`, and sets the `EDI.BatchIds` property set to a space-delimited list of batch IDs.</span></span> <span data-ttu-id="d9712-171">これにより、ルーティング オーケストレーションによる取得が可能になります。</span><span class="sxs-lookup"><span data-stu-id="d9712-171">This enables pickup by the routing orchestration.</span></span>  
  
-   <span data-ttu-id="d9712-172">サブスクリプションが存在していない場合、コンテキスト プロパティの昇格は実行されません。</span><span class="sxs-lookup"><span data-stu-id="d9712-172">If no subscriptions exist, it does not promote a context property.</span></span> <span data-ttu-id="d9712-173">したがって、トランザクション セットはバッチ処理されません。</span><span class="sxs-lookup"><span data-stu-id="d9712-173">This indicates that the transaction set is not to be batched.</span></span>  
  
 <span data-ttu-id="d9712-174">パイプライン コンポーネントは、`ReuseEnvelope` プロパティ (保存されたバッチ) が設定された XML およびメッセージ以外のメッセージを無視します。</span><span class="sxs-lookup"><span data-stu-id="d9712-174">The pipeline component ignores messages other than XML and messages with the `ReuseEnvelope` property (preserved batches).</span></span> <span data-ttu-id="d9712-175">受信確認がバッチ処理されない場合、パイプライン コンポーネントは ACK メッセージの種類 (CONTRL、TA1、および 997) を無視します。</span><span class="sxs-lookup"><span data-stu-id="d9712-175">If acknowledgments are not to be batched, the pipeline component will ignore the ACK message types (CONTRL, TA1, and 997).</span></span> <span data-ttu-id="d9712-176">ルーティング オーケストレーションおよびバッチ処理オーケストレーションの処理を最適化するために、BatchMarkerPipelineComponent は、`MessageDestination` メッセージ コンテキスト プロパティが逆アセンブラーにより "SuspendedQueue" に設定されている場合は、メッセージをメッセージ ボックスに渡します。</span><span class="sxs-lookup"><span data-stu-id="d9712-176">To optimize processing of the routing and batching orchestrations, the BatchMarkerPipelineComponent passes the message through to the MessageBox if the message context property `MessageDestination` is set to "SuspendedQueue" by the disassembler.</span></span>  
  
 <span data-ttu-id="d9712-177">EDIReceive パイプラインではなくカスタム パイプラインを使用している場合、そのカスタム パイプラインで BatchMarker コンポーネントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d9712-177">If you are using a custom pipeline, rather than the EDIReceive pipeline, you can use the BatchMarker component in your custom pipeline.</span></span> <span data-ttu-id="d9712-178">EDIReceive パイプラインを使用せず、オーケストレーションからのメッセージを公開する場合、コンポーネントの 1 つでアクティブなバッチの ID に対して `ToBeBatched = True` と `BatchID` という昇格を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9712-178">If you are not using the EDIReceive pipeline, and are publishing messages from an orchestration, you will have to promote `ToBeBatched = True` and `BatchID` to the ID of an active batch in one of your components.</span></span>  
  
### <a name="routing-orchestration"></a><span data-ttu-id="d9712-179">ルーティング オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="d9712-179">Routing Orchestration</span></span>  
 <span data-ttu-id="d9712-180">ルーティング オーケストレーションは、コンテキスト プロパティ `ToBeRouted = True` が設定され、またコンテキスト プロパティ `EDI.BatchIds` がバッチ ID のスペースで区切られた一覧に設定されているメッセージをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="d9712-180">The routing orchestration subscribes to any message with the context property `ToBeRouted = True` and the context property `EDI.BatchIds` set to a space-delimited list of batch IDs.</span></span> <span data-ttu-id="d9712-181">これは、複数のバッチ フィルターがバッチ処理対象のメッセージをサブスクライブする場合に実行されます。</span><span class="sxs-lookup"><span data-stu-id="d9712-181">This occurs when multiple batch filters subscribe to a message to be batched.</span></span> <span data-ttu-id="d9712-182">ルーティング オーケストレーションは、`EDI.BatchIds` に含まれている各バッチ ID 用にメッセージのコピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d9712-182">The routing orchestration will make a copy of the message for each batch ID contained in `EDI.BatchIds`.</span></span> <span data-ttu-id="d9712-183">ルーティング オーケストレーションは、2 つの新しいコンテキスト プロパティを各コピーに設定します。</span><span class="sxs-lookup"><span data-stu-id="d9712-183">It stamps each copy with two new context properties:</span></span>  
  
-   <span data-ttu-id="d9712-184">`EDI.BatchID` は、このメッセージが対象とするバッチの ID に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d9712-184">`EDI.BatchID`, which is set to the ID of the batch that this message is intended for.</span></span>  
  
-   <span data-ttu-id="d9712-185">`EDI.ToBeBatched` は、True に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d9712-185">`EDI.ToBeBatched`, which is set to True.</span></span>  
  
 <span data-ttu-id="d9712-186">その後、そのコピーはメッセージ ボックスにルーティングされ、バッチ処理オーケストレーションにより取得されます。</span><span class="sxs-lookup"><span data-stu-id="d9712-186">It then routes the copies to the MessageBox to be picked up by the batching orchestration.</span></span> <span data-ttu-id="d9712-187">各宛先バッチ ID は、同じオーケストレーションのシングルトン インスタンスを使用し、特定のバッチ ID にフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="d9712-187">Each destination batch ID use a singleton instance of the same orchestration, with a filter on the specific batch ID.</span></span>  
  
### <a name="batching-orchestration"></a><span data-ttu-id="d9712-188">バッチ処理オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="d9712-188">Batching Orchestration</span></span>  
 <span data-ttu-id="d9712-189">バッチ処理オーケストレーションはステートフル サービスで、バッチ要素 (トランザクション セット) を一定期間バッファーし、インターチェンジにアセンブルしてから、リリース条件に基づいてそのインターチェンジを送信パイプラインにリリースします。</span><span class="sxs-lookup"><span data-stu-id="d9712-189">The batching orchestration is a stateful service that buffers batch elements (transaction sets) over a period of time, assembles them into an interchange, and then releases the interchange to the send pipeline based upon the release criteria.</span></span>  
  
 <span data-ttu-id="d9712-190">所定のパーティを特定のエンコード タイプのメッセージのバッチ処理アクティブになった後、バッチ処理オーケストレーションのインスタンスを起動できます (場合、**開始**日時が渡された)。</span><span class="sxs-lookup"><span data-stu-id="d9712-190">After being activated, an instance of the batching orchestration can start batching messages of a particular encoding type to a given party (if the **Start** datetime has passed).</span></span> <span data-ttu-id="d9712-191">各パーティ用のバッチ処理オーケストレーションのインスタンスは、同時に多数存在することができます (アクティブなバッチ構成ごとに 1 つずつ)。</span><span class="sxs-lookup"><span data-stu-id="d9712-191">At any one time there can be many instances of the batching orchestration for each party, one per active batch configuration.</span></span> <span data-ttu-id="d9712-192">バッチ処理オーケストレーションの単一インスタンスは、単一バッチ構成用の複数のバッチをリリースできます。</span><span class="sxs-lookup"><span data-stu-id="d9712-192">A single instance of the batching orchestration can release multiple batches for a single  batch configuration.</span></span> <span data-ttu-id="d9712-193">終了条件が満たされると、バッチ処理オーケストレーション インスタンスは終了します。</span><span class="sxs-lookup"><span data-stu-id="d9712-193">After the end criteria is met, the batching orchestration instance will terminate.</span></span> <span data-ttu-id="d9712-194">取引先管理 (TPM) から手動で作成する必要があります、バッチ処理オーケストレーションの新しいインスタンスを使用して、**開始**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9712-194">A new instance of the batching orchestration will need to be created manually from the Trading Partner Management (TPM) using the **Start** button.</span></span>  
  
 <span data-ttu-id="d9712-195">開始日時に示すようにする前に、バッチ オーケストレーションを開始するかどうか、**アクティベーション**セクションの**バッチ処理構成**の一方向アグリーメント タブのページ、**アグリーメントプロパティ** ダイアログ ボックスにのみメッセージを受信するアクティベーションの範囲で指定されています。</span><span class="sxs-lookup"><span data-stu-id="d9712-195">If the batch orchestration starts before the start date time shown in the **Activation** section on the of the **Batching Configuration** page of the one-way agreement tab of the **Agreement Properties** dialog box, it will only receive messages that are specified in the activation range.</span></span> <span data-ttu-id="d9712-196">開始日時の前に送信されたメッセージは受信しません。</span><span class="sxs-lookup"><span data-stu-id="d9712-196">It will not receive messages sent before the start date time.</span></span>  
  
 <span data-ttu-id="d9712-197">バッチ処理オーケストレーションは以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="d9712-197">The batching orchestration does the following:</span></span>  
  
-   <span data-ttu-id="d9712-198">`EDI.ToBeBatched = True` およびバッチ構成の ID である `EDI.BatchId` というコンテキスト プロパティを持つ XML バッチ要素、または `EDI.ToBeBatched = True` と EDI.BatchName = 構成されているバッチの名前、さらに EDI.DestinationPartyName = バッチ構成を含むパーティ名が設定されている XML バッチ要素をサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="d9712-198">Subscribes to XML batch elements with the context properties `EDI.ToBeBatched = True` and `EDI.BatchId` the ID of the batch configuration, or `EDI.ToBeBatched = True` and EDI.BatchName = the name of the configured batch and EDI.DestinationPartyName = the party name that contains the batch configuration.</span></span> <span data-ttu-id="d9712-199">使用してバッチ要素を受け取る、**受信**ループでアクション操作します。</span><span class="sxs-lookup"><span data-stu-id="d9712-199">It receives batch elements using a **Receive** action operation in a loop.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d9712-200">バッチ処理オーケストレーションのフィルター セクションで設定されたフィルター条件に基づいてトランザクション セットをバッチ処理しません、**バッチ処理構成**の一方向アグリーメント タブのページ、 **アグリーメントのプロパティ**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="d9712-200">The batching orchestration does not batch transaction sets based upon the filter criteria set in the Filter section of the **Batching Configuration** page of the one-way agreement tab of the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="d9712-201">バッチ処理オーケストレーションは、前のコンテキスト プロパティが設定されているトランザクション セットをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="d9712-201">It subscribes to transaction sets that have the above context properties set on them.</span></span> <span data-ttu-id="d9712-202">BatchMarker パイプライン コンポーネントは、パーティのプロパティのフィルター設定に基づいて、これらのコンテキスト プロパティを設定し、昇格します。</span><span class="sxs-lookup"><span data-stu-id="d9712-202">The BatchMarker pipeline component sets and promotes those context properties based upon the filter settings in the party properties.</span></span>  
  
-   <span data-ttu-id="d9712-203">`BatchId` コンテキスト プロパティで識別されるパーティのバッチ構成設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="d9712-203">Retrieves the batch configuration settings for the party identified in the `BatchId` context property.</span></span>  
  
-   <span data-ttu-id="d9712-204">パーティの設定に基づいてバッチ要素 (トランザクション セット) を検証します。</span><span class="sxs-lookup"><span data-stu-id="d9712-204">Validates the batch element (transaction set) based on party settings.</span></span>  
  
-   <span data-ttu-id="d9712-205">バッチ要素にエラーがある場合、バッチ処理オーケストレーションは、そのトランザクション セットの `EDI.BatchItemValidationFailure = True` プロパティを昇格します。</span><span class="sxs-lookup"><span data-stu-id="d9712-205">If there is an error in a batch element, the batching orchestration will promoted the following property on that transaction set: `EDI.BatchItemValidationFailure = True`.</span></span> <span data-ttu-id="d9712-206">**BatchElementSuspend**オーケストレーションは、トランザクションは、このプロパティが昇格されたセットをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="d9712-206">The **BatchElementSuspend** orchestration subscribes to any transaction set for which this property has been promoted.</span></span> <span data-ttu-id="d9712-207">このオーケストレーションは、インターチェンジのバッチ処理において最初に発生したエラーの詳細なエラー情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="d9712-207">This orchestration will provide detailed error information for the first error encountered in batching the interchange.</span></span>  
  
-   <span data-ttu-id="d9712-208">バッチ要素にエラーがない場合、そのバッチ要素への参照を保持します。</span><span class="sxs-lookup"><span data-stu-id="d9712-208">If there is no error in a batch element, holds a reference to that batch element.</span></span>  
  
-   <span data-ttu-id="d9712-209">うち適切なコントロール メッセージが受信されるか、バッチ処理リリース条件を満たすには、ときに中断、**受信**アクション ループが、メッセージ ボックス データベースからすべてのバッチ要素を取得し、インターチェンジをアセンブルします。</span><span class="sxs-lookup"><span data-stu-id="d9712-209">When the appropriate control message is received or the batching release criteria is met, breaks out of the **Receive** action loop, retrieves all batch elements from the MessageBox, and assembles the interchange.</span></span>  
  
-   <span data-ttu-id="d9712-210">インターチェンジのコンテキスト プロパティ `ToBeBatched = False` を設定し、コンテキスト プロパティ DestinationPartyName = %PartyName% (%PartyName% は、メッセージの送信先となるパーティの名前) を設定します。</span><span class="sxs-lookup"><span data-stu-id="d9712-210">Sets the context property `ToBeBatched = False` for the interchange and the context property DestinationPartyName = %PartyName% where %PartyName% is the name of the party for which the message is intended.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d9712-211">送信ポートがプロパティ `EDI.ToBeBatched = False` とプロパティ EDI.DestinationPartyName = %PartyName% のうちの一方または両方をサブスクライブする場合、その送信ポートはバッチ インターチェンジを取得できます。</span><span class="sxs-lookup"><span data-stu-id="d9712-211">If a send port subscribes to either or both of the properties `EDI.ToBeBatched = False` and EDI.DestinationPartyName = %PartyName%, that send port can pick up the batched interchange.</span></span> <span data-ttu-id="d9712-212">必ず、送信ポートがこれらの取得対象のバッチ インターチェンジのみを取得するように送信ポートのフィルターを構成してください。</span><span class="sxs-lookup"><span data-stu-id="d9712-212">Make sure that a send port's filters are configured such that the send port picks up only those batched interchanges that it is intended to pick up.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d9712-213">バッチ処理オーケストレーションによりメッセージ ボックス内に送られるインターチェンジは、コンテキストに対して `EDI.ToBeBatched = False`、EDI.DestinationPartyName = %PartyName%、および EDI.BatchEncodingType = "X12" または "EDIFACT" というプロパティ昇格のみを実行します。</span><span class="sxs-lookup"><span data-stu-id="d9712-213">Interchanges dropped by the batching orchestration into the MessageBox have only the properties `EDI.ToBeBatched = False`, EDI.DestinationPartyName = %PartyName%, and EDI.BatchEncodingType = "X12" or "EDIFACT" promoted to the context.</span></span> <span data-ttu-id="d9712-214">元のトランザクション セットのすべてのコンテキスト プロパティは失われます。</span><span class="sxs-lookup"><span data-stu-id="d9712-214">All context properties from the original transaction sets are lost.</span></span>  
  
-   <span data-ttu-id="d9712-215">X12 でエンコードされたインターチェンジの場合、次のプロパティをエンベロープに適用します。</span><span class="sxs-lookup"><span data-stu-id="d9712-215">For an X12-encoded interchange, applies the following properties to the envelope:</span></span>  
  
    -   <span data-ttu-id="d9712-216">ISA6: インターチェンジの送信者 ID</span><span class="sxs-lookup"><span data-stu-id="d9712-216">ISA6: Interchange Sender ID</span></span>  
  
    -   <span data-ttu-id="d9712-217">ISA8: インターチェンジの受信者 ID</span><span class="sxs-lookup"><span data-stu-id="d9712-217">ISA8: Interchange Receiver ID</span></span>  
  
    -   <span data-ttu-id="d9712-218">ISA15: 使用状況インジケーター</span><span class="sxs-lookup"><span data-stu-id="d9712-218">ISA15: Usage indicator</span></span>  
  
    -   <span data-ttu-id="d9712-219">ISA_Blob (コンテキストに書き込み)</span><span class="sxs-lookup"><span data-stu-id="d9712-219">ISA_Blob (written to context)</span></span>  
  
-   <span data-ttu-id="d9712-220">EDIFACT でエンコードされたインターチェンジの場合、次のプロパティをエンベロープに適用します。</span><span class="sxs-lookup"><span data-stu-id="d9712-220">For an EDIFACT-encoded interchange, applies the following properties to the envelope:</span></span>  
  
    -   <span data-ttu-id="d9712-221">UNB2.1: インターチェンジの送信者 ID</span><span class="sxs-lookup"><span data-stu-id="d9712-221">UNB2.1: Interchange Sender ID</span></span>  
  
    -   <span data-ttu-id="d9712-222">UNB3.1: インターチェンジの受信者 ID</span><span class="sxs-lookup"><span data-stu-id="d9712-222">UNB3.1: Interchange Recipient ID</span></span>  
  
    -   <span data-ttu-id="d9712-223">UNB2.3: 逆ルーティングのアドレス</span><span class="sxs-lookup"><span data-stu-id="d9712-223">UNB2.3: Address for Reverse Routing</span></span>  
  
    -   <span data-ttu-id="d9712-224">UNB11: 使用状況インジケーター</span><span class="sxs-lookup"><span data-stu-id="d9712-224">UNB11: Usage indicator</span></span>  
  
    -   <span data-ttu-id="d9712-225">UNA_Blob (コンテキストに書き込み)</span><span class="sxs-lookup"><span data-stu-id="d9712-225">UNA_Blob (written to context)</span></span>  
  
    -   <span data-ttu-id="d9712-226">UNB_Blob (コンテキストに書き込み)</span><span class="sxs-lookup"><span data-stu-id="d9712-226">UNB_Blob (written to context)</span></span>  
  
-   <span data-ttu-id="d9712-227">バッチ インターチェンジを、EDI 送信パイプラインが取得できるようにメッセージ ボックスに配送します。</span><span class="sxs-lookup"><span data-stu-id="d9712-227">Delivers the batched interchange to the MessageBox for pickup by the EDI send pipeline.</span></span>  
  
### <a name="upgradebatching-orchestration"></a><span data-ttu-id="d9712-228">UpgradeBatching オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="d9712-228">UpgradeBatching Orchestration</span></span>  
 <span data-ttu-id="d9712-229">UpgradeBatching オーケストレーションは、`EDI.ToBeBatched` プロパティが true に設定されていて、`EDI.BatchID` プロパティが設定されていないメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="d9712-229">The UpgradeBatching orchestration handles messages that are have the `EDI.ToBeBatched` property set to true, but do not have the `EDI.BatchID` property set.</span></span>  
  
 <span data-ttu-id="d9712-230">以前のバージョンの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、各パーティは 1 つのバッチ構成しか持つことができませんでした。</span><span class="sxs-lookup"><span data-stu-id="d9712-230">In previous versions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], each party could have only one batch configuration.</span></span>  <span data-ttu-id="d9712-231">`EDI.ToBeBatched` が true に設定されたメッセージを処理するときは、`EDI.DestinationPartyId` を使用してパーティを特定し、次にアグリーメントのプロパティからバッチ構成を読み取っていました。</span><span class="sxs-lookup"><span data-stu-id="d9712-231">When processing messages that had `EDI.ToBeBatched` set to true, the `EDI.DestinationPartyId` was used to determine the party and then the batch configuration was read from the agreement properties.</span></span>  
  
 <span data-ttu-id="d9712-232">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、各パーティに複数のバッチ構成が関連付けられている場合があるため、`EDI.DestinationPartyId` が提供する情報では、どのバッチ構成を使用するかを判断するのに十分ではありません。</span><span class="sxs-lookup"><span data-stu-id="d9712-232">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], each party can have multiple batch configurations associated with it, so the `EDI.DestinationPartyId` does not provide enough information to determine which batch configuration should be used.</span></span>  <span data-ttu-id="d9712-233">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、メッセージを受け取ると、`EDI.BatchId` プロパティを使用して、メッセージの処理に使用する特定のバッチ構成を特定します。</span><span class="sxs-lookup"><span data-stu-id="d9712-233">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receives messages, the `EDI.BatchId` property is used to identify which specific batch configuration should be used when processing a message.</span></span>  
  
 <span data-ttu-id="d9712-234">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にアップグレードした後も、`EDI.DestinationPartyId` プロパティを使用してパーティ構成を指定するカスタム パイプラインを設定できます。</span><span class="sxs-lookup"><span data-stu-id="d9712-234">After upgrading to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you may still have custom pipelines that use the `EDI.DestinationPartyId` property to specify the party configuration.</span></span> <span data-ttu-id="d9712-235">受け取ったメッセージで `EDI.ToBeBatched` が true に設定され、さらに EDI.BatchID ではなく `EDI.DestinationPartyID` が設定されている場合、UpgradeBatching オーケストレーションは、どのバッチ構成を使用するかの判断を試みます。</span><span class="sxs-lookup"><span data-stu-id="d9712-235">When a message is received that has `EDI.ToBeBatched` set to true, and has `EDI.DestinationPartyID` set instead of EDI.BatchID, the UpgradeBatching orchestration attempts to determine which batch configuration should be used.</span></span>  
  
 <span data-ttu-id="d9712-236">UpgradeBatching オーケストレーションは次のサブスクリプション フィルターを使用して、バッチ処理の対象として設定されており、バッチ ID が指定されていないドキュメントをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="d9712-236">The UpgradeBatching orchestration uses the following subscription filters to subscribe to documents that are marked for batching, but do not specify a batch ID:</span></span>  
  
-   `EDI.ToBeBatched=True`  
  
-   <span data-ttu-id="d9712-237">`EDI.EncodingType` が存在します</span><span class="sxs-lookup"><span data-stu-id="d9712-237">`EDI.EncodingType` exists</span></span>  
  
-   <span data-ttu-id="d9712-238">`EDI.DestinationPartyId` が存在します</span><span class="sxs-lookup"><span data-stu-id="d9712-238">`EDI.DestinationPartyId` exists</span></span>  
  
 <span data-ttu-id="d9712-239">このオーケストレーションは、メッセージを受け取ると、パーティ名とエンコードの種類を使用して、メッセージ用の一致するバッチ構成を見つけようとします。</span><span class="sxs-lookup"><span data-stu-id="d9712-239">When the orchestration receives a message, it will try to find a matching batch configuration for the message by using the party name and encoding type.</span></span>  <span data-ttu-id="d9712-240">`EDI.DestinationPartyID`プロパティを使用して、パーティ名を指定して、オーケストレーションと一致するバッチ名が検索されます\<PartyName\>+\<EncodingType\>+ Default です。</span><span class="sxs-lookup"><span data-stu-id="d9712-240">The `EDI.DestinationPartyID` property is used to determine the party name, and then the orchestration looks for a batch name that matches \<PartyName\>+\<EncodingType\>+Default.</span></span>  <span data-ttu-id="d9712-241">たとえば、パーティ名が Contoso で、`EDI.EncodingType` の値が X12 である場合、オーケストレーションは ContosoX12Default という名前のバッチを検索します。</span><span class="sxs-lookup"><span data-stu-id="d9712-241">For example if the party name is Contoso, and the value of `EDI.EncodingType` is X12, then the orchestration will look for a batch named ContosoX12Default.</span></span>  
  
 <span data-ttu-id="d9712-242">一致するバッチ構成が見つかった場合、メッセージには次のプロパティが設定されてメッセージ ボックスに戻されます。</span><span class="sxs-lookup"><span data-stu-id="d9712-242">If a matching batch configuration is found, the message is placed back in the message box with the following properties:</span></span>  
  
-   `EDI.ToBeBatched = True`  
  
-   `EDI.ToBeRouted = False`  
  
-   <span data-ttu-id="d9712-243">EDI.BatchId = 一致するバッチのバッチ ID</span><span class="sxs-lookup"><span data-stu-id="d9712-243">EDI.BatchId = the batch ID for the matching batch</span></span>  
  
 <span data-ttu-id="d9712-244">その後、バッチ処理オーケストレーションはメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="d9712-244">The batching orchestration will then process the message</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d9712-245">一致するバッチが見つからない場合は、次の処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="d9712-245">If no matching batch is found, then the following will happen:</span></span>  
>   
>  -   <span data-ttu-id="d9712-246">メッセージは BatchSuspend オーケストレーションに送信されません。</span><span class="sxs-lookup"><span data-stu-id="d9712-246">The message will not be sent to the BatchSuspend orchestration.</span></span>  
> -   <span data-ttu-id="d9712-247">UpgradeBatching オーケストレーションのインスタンスとメッセージが中断されます。</span><span class="sxs-lookup"><span data-stu-id="d9712-247">The UpgradeBatching orchestration instance and message will be suspended.</span></span>  
> -   <span data-ttu-id="d9712-248">バッチが見つからなかったことを示すエラーがイベント ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="d9712-248">An error will be logged to the event log stating that a batch was not found.</span></span>  
  
### <a name="batchsuspend-orchestration"></a><span data-ttu-id="d9712-249">BatchSuspend オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="d9712-249">BatchSuspend Orchestration</span></span>  
 <span data-ttu-id="d9712-250">BatchSuspend オーケストレーションは、バッチ処理オーケストレーションが受信した無効なメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="d9712-250">The BatchSuspend orchestration handles invalid messages received by the batching orchestration.</span></span> <span data-ttu-id="d9712-251">BatchSuspend オーケストレーションが必要な理由は、オーケストレーションのインスタンスの実行を停止することなく、オーケストレーション (この場合、バッチ処理オーケストレーション) からのメッセージを中断する直接的な方法がないためです。</span><span class="sxs-lookup"><span data-stu-id="d9712-251">The BatchSuspend orchestration is needed because there is no direct way to suspend a message from an orchestration (in this case, the batching orchestration) without stopping the execution of the instance of the orchestration.</span></span>  
  
 <span data-ttu-id="d9712-252">バッチ処理オーケストレーションのインスタンスは、メッセージを受信すると、それを検証しようとします。</span><span class="sxs-lookup"><span data-stu-id="d9712-252">When an instance of the batching orchestration receives a message, it attempts to validate it.</span></span> <span data-ttu-id="d9712-253">メッセージの検証が失敗すると、バッチ処理オーケストレーションは BatchSuspend オーケストレーションのインスタンスを作成し、`EDI.BatchItemValidationFailure` コンテキスト プロパティを True に設定します。</span><span class="sxs-lookup"><span data-stu-id="d9712-253">If the message fails validation, the batching orchestration creates an instance of the BatchSuspend orchestration, and sets the `EDI.BatchItemValidationFailure` context property to True.</span></span> <span data-ttu-id="d9712-254">BatchSuspend オーケストレーションは、このコンテキスト プロパティが True に設定されたすべてのメッセージをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="d9712-254">The BatchSuspend orchestration subscribes to all messages with that context property set to True.</span></span> <span data-ttu-id="d9712-255">無効なトランザクション セットが BatchSuspend オーケストレーションにルーティングされると、BatchSuspend オーケストレーション インスタンスは中断されます。</span><span class="sxs-lookup"><span data-stu-id="d9712-255">After the invalid transaction set is routed to the BatchSuspend orchestration, the BatchSuspend orchestration instance is suspended.</span></span>  
  
 <span data-ttu-id="d9712-256">最初に発生したエラーに関する詳細なエラー情報は BatchSuspend オーケストレーションにより提供されます。</span><span class="sxs-lookup"><span data-stu-id="d9712-256">Detailed error information for the first error encountered is provided by the BatchSuspend orchestration.</span></span>  
  
 <span data-ttu-id="d9712-257">カスタム オーケストレーションを作成し、フィルターで `EDI.BatchElementValidationFailure` プロパティを使用することで、バッチ処理オーケストレーションによる検証が失敗したトランザクション セットを処理できます。</span><span class="sxs-lookup"><span data-stu-id="d9712-257">You can create a custom orchestration to handle transaction sets that fail validation by the batching orchestration, by using the `EDI.BatchElementValidationFailure` property in a filter.</span></span>  
  
### <a name="edi-send-pipeline"></a><span data-ttu-id="d9712-258">EDI 送信パイプライン</span><span class="sxs-lookup"><span data-stu-id="d9712-258">EDI Send Pipeline</span></span>  
 <span data-ttu-id="d9712-259">EDI 送信パイプラインは、バッチ処理オーケストレーションからバッチ インターチェンジを受信した後、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="d9712-259">After receiving a batched interchange from the batching orchestration, the EDI send pipeline does the following:</span></span>  
  
-   <span data-ttu-id="d9712-260">X12 でエンコードされたインターチェンジの場合、送信パイプラインは、次のプロパティをエンベロープに適用します。</span><span class="sxs-lookup"><span data-stu-id="d9712-260">For an X12-encoded interchange, the send pipeline applies the following properties to the envelope:</span></span>  
  
    -   <span data-ttu-id="d9712-261">ISA2: 認証情報</span><span class="sxs-lookup"><span data-stu-id="d9712-261">ISA2: Authorization Information</span></span>  
  
    -   <span data-ttu-id="d9712-262">ISA4: セキュリティ情報</span><span class="sxs-lookup"><span data-stu-id="d9712-262">ISA4: Security Information</span></span>  
  
    -   <span data-ttu-id="d9712-263">ISA9: インターチェンジ日付</span><span class="sxs-lookup"><span data-stu-id="d9712-263">ISA9: Interchange Date</span></span>  
  
    -   <span data-ttu-id="d9712-264">ISA10: インターチェンジ時刻</span><span class="sxs-lookup"><span data-stu-id="d9712-264">ISA10: Interchange Time</span></span>  
  
    -   <span data-ttu-id="d9712-265">ISA13: インターチェンジ制御番号</span><span class="sxs-lookup"><span data-stu-id="d9712-265">ISA13: Interchange Control Number</span></span>  
  
    -   <span data-ttu-id="d9712-266">GS4: 日付</span><span class="sxs-lookup"><span data-stu-id="d9712-266">GS4: Date</span></span>  
  
    -   <span data-ttu-id="d9712-267">GS5: 時刻</span><span class="sxs-lookup"><span data-stu-id="d9712-267">GS5: Time</span></span>  
  
    -   <span data-ttu-id="d9712-268">GS6: グループ制御番号</span><span class="sxs-lookup"><span data-stu-id="d9712-268">GS6: Group Control Number</span></span>  
  
    -   <span data-ttu-id="d9712-269">ST2: トランザクション セット制御番号</span><span class="sxs-lookup"><span data-stu-id="d9712-269">ST2: Transaction Set Control Number</span></span>  
  
-   <span data-ttu-id="d9712-270">EDIFACT でエンコードされたインターチェンジの場合、送信パイプラインは、次のプロパティをエンベロープに適用します。</span><span class="sxs-lookup"><span data-stu-id="d9712-270">For an EDIFACT-encoded interchange, the send pipeline applies the following properties to the envelope:</span></span>  
  
    -   <span data-ttu-id="d9712-271">UNB4.1: 日付</span><span class="sxs-lookup"><span data-stu-id="d9712-271">UNB4.1: Date</span></span>  
  
    -   <span data-ttu-id="d9712-272">UNB4.2: 時刻</span><span class="sxs-lookup"><span data-stu-id="d9712-272">UNB4.2: Time</span></span>  
  
    -   <span data-ttu-id="d9712-273">UNB5: インターチェンジ制御参照</span><span class="sxs-lookup"><span data-stu-id="d9712-273">UNB5: Interchange Control Reference</span></span>  
  
    -   <span data-ttu-id="d9712-274">UNB6.1: 受信者の参照/パスワード</span><span class="sxs-lookup"><span data-stu-id="d9712-274">UNB6.1: Recipient Reference Password</span></span>  
  
    -   <span data-ttu-id="d9712-275">UNG4.1: 日付</span><span class="sxs-lookup"><span data-stu-id="d9712-275">UNG4.1: Date</span></span>  
  
    -   <span data-ttu-id="d9712-276">UNG4.2: 時刻</span><span class="sxs-lookup"><span data-stu-id="d9712-276">UNG4.2: Time</span></span>  
  
    -   <span data-ttu-id="d9712-277">UNG5: 機能グループの参照</span><span class="sxs-lookup"><span data-stu-id="d9712-277">UNG5: Functional Group Reference</span></span>  
  
    -   <span data-ttu-id="d9712-278">UNG8: アプリケーションのパスワード</span><span class="sxs-lookup"><span data-stu-id="d9712-278">UNG8: Application Password</span></span>  
  
-   <span data-ttu-id="d9712-279">関連アダプターを使用してメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="d9712-279">Delivers the message via the associated adapter</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9712-280">参照</span><span class="sxs-lookup"><span data-stu-id="d9712-280">See Also</span></span>  
 [<span data-ttu-id="d9712-281">送信 EDI メッセージのバッチ処理</span><span class="sxs-lookup"><span data-stu-id="d9712-281">Batching Outgoing EDI Messages</span></span>](../core/batching-outgoing-edi-messages.md)