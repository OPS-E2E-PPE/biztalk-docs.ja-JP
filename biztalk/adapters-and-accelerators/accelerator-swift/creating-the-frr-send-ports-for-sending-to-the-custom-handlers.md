---
title: "カスタム ハンドラーに送信するための FRR 送信ポートの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, send ports
- send ports, creating
- FRR, creating send ports
ms.assetid: 036f1f97-17a2-4e02-a85a-a52739a48528
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7da5d51407bed1cca257e14cc4f548e8c991cf9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-the-frr-send-ports-for-sending-to-the-custom-handlers"></a><span data-ttu-id="f8439-102">カスタム ハンドラーに送信するための FRR 送信ポートの作成</span><span class="sxs-lookup"><span data-stu-id="f8439-102">Creating the FRR Send Ports for Sending to the Custom Handlers</span></span>
<span data-ttu-id="f8439-103">FIN 対応調整を実行する必要があります (元のメッセージまたは応答) メッセージを送信するの各送信ポートの系列を作成するから[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]相関関係を持つメッセージを処理するカスタム ハンドラーにします。</span><span class="sxs-lookup"><span data-stu-id="f8439-103">To perform FIN Response Reconciliation, you need to create a series of send ports, each of which sends a message (original message or response) from [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] to the custom handlers that process the correlated messages.</span></span>  
  
 <span data-ttu-id="f8439-104">**概要**</span><span class="sxs-lookup"><span data-stu-id="f8439-104">**Summary**</span></span>  
  
 <span data-ttu-id="f8439-105">次のプロパティとコンポーネント、BTS の値で識別される 1 つずつ一連の送信ポートを作成します。フィルターの操作:</span><span class="sxs-lookup"><span data-stu-id="f8439-105">Create a series of send ports with the following properties and components, each one distinguished by the value of BTS.Operation in the filter:</span></span>  
  
|<span data-ttu-id="f8439-106">プロパティ/コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f8439-106">Property/Component</span></span>|<span data-ttu-id="f8439-107">設定</span><span class="sxs-lookup"><span data-stu-id="f8439-107">Setting</span></span>|  
|-------------------------|-------------|  
|<span data-ttu-id="f8439-108">送信ポート</span><span class="sxs-lookup"><span data-stu-id="f8439-108">Send port</span></span>|<span data-ttu-id="f8439-109">静的な一方向ポート</span><span class="sxs-lookup"><span data-stu-id="f8439-109">Static one-way port</span></span>|  
|<span data-ttu-id="f8439-110">トランスポートの種類</span><span class="sxs-lookup"><span data-stu-id="f8439-110">Transport type</span></span>|<span data-ttu-id="f8439-111">FILE</span><span class="sxs-lookup"><span data-stu-id="f8439-111">FILE</span></span>|  
|<span data-ttu-id="f8439-112">コピー先フォルダー (アドレス URI)</span><span class="sxs-lookup"><span data-stu-id="f8439-112">Destination folder (Address URI)</span></span>|<span data-ttu-id="f8439-113">メッセージを送信する先のフォルダー</span><span class="sxs-lookup"><span data-stu-id="f8439-113">The folder that you want to send the message to</span></span>|  
|<span data-ttu-id="f8439-114">ファイル名 (アドレス URI)</span><span class="sxs-lookup"><span data-stu-id="f8439-114">File name (Address URI)</span></span>|<span data-ttu-id="f8439-115">%MessageID%.txt</span><span class="sxs-lookup"><span data-stu-id="f8439-115">%MessageID%.txt</span></span>|  
|<span data-ttu-id="f8439-116">[送信パイプライン]</span><span class="sxs-lookup"><span data-stu-id="f8439-116">Send pipeline</span></span>|[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="f8439-117">.BizTalk.DefaultPipelines です。</span><span class="sxs-lookup"><span data-stu-id="f8439-117">.BizTalk.DefaultPipelines.</span></span> <span data-ttu-id="f8439-118">PassThruTransmit</span><span class="sxs-lookup"><span data-stu-id="f8439-118">PassThruTransmit</span></span>|  
|<span data-ttu-id="f8439-119">フィルター</span><span class="sxs-lookup"><span data-stu-id="f8439-119">Filters</span></span>|<span data-ttu-id="f8439-120">次の表に示すように</span><span class="sxs-lookup"><span data-stu-id="f8439-120">As shown in the tables below</span></span>|  
  
 <span data-ttu-id="f8439-121">さまざまなメッセージの送信ポートは、BTS の値で識別されます。操作は、送信ポートのフィルターです。</span><span class="sxs-lookup"><span data-stu-id="f8439-121">The send ports for the different messages are distinguished by the value of BTS.Operation in the send port's filter.</span></span>  
  
### <a name="to-add-frr-send-ports-for-sending-to-the-custom-handlers"></a><span data-ttu-id="f8439-122">カスタム ハンドラーに送信するための FRR 送信ポートを追加するには</span><span class="sxs-lookup"><span data-stu-id="f8439-122">To add FRR send ports for sending to the custom handlers</span></span>  
  
1.  <span data-ttu-id="f8439-123">BizTalk Server 管理コンソールで、右クリック**送信ポート**、 をポイント**新規**、クリックして**静的なポートを 1 つ waySend**です。</span><span class="sxs-lookup"><span data-stu-id="f8439-123">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-waySend Port**.</span></span>  
  
2.  <span data-ttu-id="f8439-124">送信ポートのプロパティ ダイアログ ボックスで、**名前**ボックス FRRCustomHandlersSendPort など、送信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="f8439-124">In the Send Port Properties dialog box, in the **Name** box, type a name for the send port, such as FRRCustomHandlersSendPort.</span></span>  
  
3.  <span data-ttu-id="f8439-125">**型****ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="f8439-125">For **Type**, select **FILE**.</span></span>  
  
4.  <span data-ttu-id="f8439-126">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="f8439-126">Click **Configure**.</span></span>  
  
5.  <span data-ttu-id="f8439-127">[FILE トランスポートのプロパティ] ダイアログ ボックスで、**参照**です。</span><span class="sxs-lookup"><span data-stu-id="f8439-127">In the FILE Transport Properties dialog box, click **Browse**.</span></span>  
  
6.  <span data-ttu-id="f8439-128">フォルダーの参照 ダイアログ ボックスからメッセージを送信するフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="f8439-128">In the Browse For Folder dialog box, move to the folder that you want to send messages from.</span></span> <span data-ttu-id="f8439-129">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8439-129">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f8439-130">このフォルダーが存在しない場合を使用してそれを作成、**新しいフォルダーの作成**コマンド。</span><span class="sxs-lookup"><span data-stu-id="f8439-130">If this folder does not exist, you can create it using the **Make New Folder** command.</span></span>  
  
7.  <span data-ttu-id="f8439-131">**ファイル名**ボックスに、入力**%MessageID%.txt**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="f8439-131">In the **File name** box, type **%MessageID%.txt**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f8439-132">メッセージの種類ごとに別のフォルダーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="f8439-132">You can create a different folder for each type of message.</span></span>  
  
8.  <span data-ttu-id="f8439-133">送信ポートのプロパティ ダイアログ ボックスの送信ハンドラーであることを確認**BizTalkServerApplication**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="f8439-133">In the Send Port Properties dialog box, for Send handler, verify that **BizTalkServerApplication** is selected.</span></span>  
  
9. <span data-ttu-id="f8439-134">**送信パイプライン** **PassThruTransmit**です。</span><span class="sxs-lookup"><span data-stu-id="f8439-134">For **Send Pipeline**, select **PassThruTransmit**.</span></span>  
  
10. <span data-ttu-id="f8439-135">をクリックして**フィルター**左側のウィンドウで、次の操作。</span><span class="sxs-lookup"><span data-stu-id="f8439-135">Click **Filters** in the left pane, and then do the following:</span></span>  
  
    |<span data-ttu-id="f8439-136">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f8439-136">Use this</span></span>|<span data-ttu-id="f8439-137">目的</span><span class="sxs-lookup"><span data-stu-id="f8439-137">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="f8439-138">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="f8439-138">**Property**</span></span>|<span data-ttu-id="f8439-139">選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SendingServiceType**です。</span><span class="sxs-lookup"><span data-stu-id="f8439-139">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SendingServiceType**.</span></span>|  
    |<span data-ttu-id="f8439-140">**演算子**</span><span class="sxs-lookup"><span data-stu-id="f8439-140">**Operator**</span></span>|<span data-ttu-id="f8439-141">選択 **==**です。</span><span class="sxs-lookup"><span data-stu-id="f8439-141">Select **==**.</span></span>|  
    |<span data-ttu-id="f8439-142">**値**</span><span class="sxs-lookup"><span data-stu-id="f8439-142">**Value**</span></span>|<span data-ttu-id="f8439-143">型**A4SWIFT_FrrService**です。</span><span class="sxs-lookup"><span data-stu-id="f8439-143">Type **A4SWIFT_FrrService**.</span></span>|  
    |<span data-ttu-id="f8439-144">**[グループ]**</span><span class="sxs-lookup"><span data-stu-id="f8439-144">**Group**</span></span>|<span data-ttu-id="f8439-145">**そして**</span><span class="sxs-lookup"><span data-stu-id="f8439-145">**And**</span></span>|  
    |<span data-ttu-id="f8439-146">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="f8439-146">**Property**</span></span>|<span data-ttu-id="f8439-147">選択**BTS です。操作**です。</span><span class="sxs-lookup"><span data-stu-id="f8439-147">Select **BTS.Operation**.</span></span>|  
    |<span data-ttu-id="f8439-148">**演算子**</span><span class="sxs-lookup"><span data-stu-id="f8439-148">**Operator**</span></span>|<span data-ttu-id="f8439-149">選択 **==**です。</span><span class="sxs-lookup"><span data-stu-id="f8439-149">Select **==**.</span></span>|  
    |<span data-ttu-id="f8439-150">**値**</span><span class="sxs-lookup"><span data-stu-id="f8439-150">**Value**</span></span>|<span data-ttu-id="f8439-151">BTS のいずれかを入力します。次の表の値を操作します。</span><span class="sxs-lookup"><span data-stu-id="f8439-151">Type one of the BTS.Operation values from the table below.</span></span>|  
  
     <span data-ttu-id="f8439-152">BTS です。操作では、次の値のいずれかを入力します。</span><span class="sxs-lookup"><span data-stu-id="f8439-152">For BTS.Operation, enter one of the following values:</span></span>  
  
    |<span data-ttu-id="f8439-153">メッセージ型</span><span class="sxs-lookup"><span data-stu-id="f8439-153">Message type</span></span>|<span data-ttu-id="f8439-154">BTS です。操作の値</span><span class="sxs-lookup"><span data-stu-id="f8439-154">BTS.Operation value</span></span>|  
    |------------------|-------------------------|  
    |<span data-ttu-id="f8439-155">すべてのカテゴリ、0 ~ 9 SWIFT FIN メッセージ型</span><span class="sxs-lookup"><span data-stu-id="f8439-155">All Category 0 to 9 SWIFT FIN message types</span></span>|<span data-ttu-id="f8439-156">**A4SWIFT_FrrSendMTMsg**</span><span class="sxs-lookup"><span data-stu-id="f8439-156">**A4SWIFT_FrrSendMTMsg**</span></span>|  
    |<span data-ttu-id="f8439-157">MQ 系列パン/NAN (MQ Series トランスポート レベル ACK/NAK)</span><span class="sxs-lookup"><span data-stu-id="f8439-157">MQ Series PAN/NAN (MQ Series transport-level ACK/NAK)</span></span>|<span data-ttu-id="f8439-158">**A4SWIFT_FrrSendTransport**</span><span class="sxs-lookup"><span data-stu-id="f8439-158">**A4SWIFT_FrrSendTransport**</span></span>|  
    |<span data-ttu-id="f8439-159">MT010 (配信不能警告)</span><span class="sxs-lookup"><span data-stu-id="f8439-159">MT010 (Non-Delivery Warning)</span></span>|<span data-ttu-id="f8439-160">**A4SWIFT_FrrSend010NDW**</span><span class="sxs-lookup"><span data-stu-id="f8439-160">**A4SWIFT_FrrSend010NDW**</span></span>|  
    |<span data-ttu-id="f8439-161">MT011 (配信通知)</span><span class="sxs-lookup"><span data-stu-id="f8439-161">MT011 (Delivery Notification)</span></span>|<span data-ttu-id="f8439-162">**A4SWIFT_FrrSend011Delivered**</span><span class="sxs-lookup"><span data-stu-id="f8439-162">**A4SWIFT_FrrSend011Delivered**</span></span>|  
    |<span data-ttu-id="f8439-163">MT012 (送信者 Notification)</span><span class="sxs-lookup"><span data-stu-id="f8439-163">MT012 (Sender Notification)</span></span>|<span data-ttu-id="f8439-164">**A4SWIFT_FrrSend012SenderACK**</span><span class="sxs-lookup"><span data-stu-id="f8439-164">**A4SWIFT_FrrSend012SenderACK**</span></span>|  
    |<span data-ttu-id="f8439-165">MT015 (DNK、または遅延 NAK)</span><span class="sxs-lookup"><span data-stu-id="f8439-165">MT015 (DNK, or Delayed NAK)</span></span>|<span data-ttu-id="f8439-166">**A4SWIFT_FrrSend015DNK**</span><span class="sxs-lookup"><span data-stu-id="f8439-166">**A4SWIFT_FrrSend015DNK**</span></span>|  
    |<span data-ttu-id="f8439-167">MT019 (通知を中止)</span><span class="sxs-lookup"><span data-stu-id="f8439-167">MT019 (Abort Notification)</span></span>|<span data-ttu-id="f8439-168">**A4SWIFT_FrrSend019Abort**</span><span class="sxs-lookup"><span data-stu-id="f8439-168">**A4SWIFT_FrrSend019Abort**</span></span>|  
    |<span data-ttu-id="f8439-169">MTS21_FIN_ACKNAK (LT (ACK) によって送信された FIN メッセージの受信確認</span><span class="sxs-lookup"><span data-stu-id="f8439-169">MTS21_FIN_ACKNAK (Acknowledgment of a FIN message sent by an LT (ACK)</span></span>|<span data-ttu-id="f8439-170">**A4SWIFT_FrrSendS21ACK**</span><span class="sxs-lookup"><span data-stu-id="f8439-170">**A4SWIFT_FrrSendS21ACK**</span></span>|  
    |<span data-ttu-id="f8439-171">MTS21_FIN_ACKNAK (否定、LT (NAK) によって送信された FIN メッセージの受信確認</span><span class="sxs-lookup"><span data-stu-id="f8439-171">MTS21_FIN_ACKNAK (Negative acknowledgment of a FIN message sent by an LT (NAK)</span></span>|<span data-ttu-id="f8439-172">**A4SWIFT_FrrSendS21NAK**</span><span class="sxs-lookup"><span data-stu-id="f8439-172">**A4SWIFT_FrrSendS21NAK**</span></span>|  
  
11. <span data-ttu-id="f8439-173">次の操作を正常に送信されていない、カテゴリ、0 ~ 9 SWIFT FIN メッセージに対して、**フィルター**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="f8439-173">For Category 0 to 9 SWIFT FIN messages that are not successfully sent, do the following in the **Filters** pane:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f8439-174">**A4SWIFT_FRRFailedReason**次のフィルターのプロパティをグループ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8439-174">The **A4SWIFT_FRRFailedReason** properties in the following filter should be grouped.</span></span>  
  
    |<span data-ttu-id="f8439-175">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f8439-175">Use this</span></span>|<span data-ttu-id="f8439-176">目的</span><span class="sxs-lookup"><span data-stu-id="f8439-176">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="f8439-177">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="f8439-177">**Property**</span></span>|<span data-ttu-id="f8439-178">選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SendingServiceType**です。</span><span class="sxs-lookup"><span data-stu-id="f8439-178">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SendingServiceType**.</span></span>|  
    |<span data-ttu-id="f8439-179">**演算子**</span><span class="sxs-lookup"><span data-stu-id="f8439-179">**Operator**</span></span>|<span data-ttu-id="f8439-180">選択 **==**です。</span><span class="sxs-lookup"><span data-stu-id="f8439-180">Select **==**.</span></span>|  
    |<span data-ttu-id="f8439-181">**値**</span><span class="sxs-lookup"><span data-stu-id="f8439-181">**Value**</span></span>|<span data-ttu-id="f8439-182">型**A4SWIFT_FrrService**です。</span><span class="sxs-lookup"><span data-stu-id="f8439-182">Type **A4SWIFT_FrrService**.</span></span>|  
    |<span data-ttu-id="f8439-183">**[グループ]**</span><span class="sxs-lookup"><span data-stu-id="f8439-183">**Group**</span></span>|<span data-ttu-id="f8439-184">**そして**</span><span class="sxs-lookup"><span data-stu-id="f8439-184">**And**</span></span>|  
    |<span data-ttu-id="f8439-185">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="f8439-185">**Property**</span></span>|<span data-ttu-id="f8439-186">選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FrrFailed**です。</span><span class="sxs-lookup"><span data-stu-id="f8439-186">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FrrFailed**.</span></span>|  
    |<span data-ttu-id="f8439-187">**演算子**</span><span class="sxs-lookup"><span data-stu-id="f8439-187">**Operator**</span></span>|<span data-ttu-id="f8439-188">選択 **==**です。</span><span class="sxs-lookup"><span data-stu-id="f8439-188">Select **==**.</span></span>|  
    |<span data-ttu-id="f8439-189">**値**</span><span class="sxs-lookup"><span data-stu-id="f8439-189">**Value**</span></span>|<span data-ttu-id="f8439-190">型**True**です。</span><span class="sxs-lookup"><span data-stu-id="f8439-190">Type **True**.</span></span>|  
    |<span data-ttu-id="f8439-191">**[グループ]**</span><span class="sxs-lookup"><span data-stu-id="f8439-191">**Group**</span></span>|<span data-ttu-id="f8439-192">**そして**</span><span class="sxs-lookup"><span data-stu-id="f8439-192">**And**</span></span>|  
    |<span data-ttu-id="f8439-193">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="f8439-193">**Property**</span></span>|<span data-ttu-id="f8439-194">選択**BTS です。操作**です。</span><span class="sxs-lookup"><span data-stu-id="f8439-194">Select **BTS.Operation**.</span></span>|  
    |<span data-ttu-id="f8439-195">**演算子**</span><span class="sxs-lookup"><span data-stu-id="f8439-195">**Operator**</span></span>|<span data-ttu-id="f8439-196">選択 **==**です。</span><span class="sxs-lookup"><span data-stu-id="f8439-196">Select **==**.</span></span>|  
    |<span data-ttu-id="f8439-197">**値**</span><span class="sxs-lookup"><span data-stu-id="f8439-197">**Value**</span></span>|<span data-ttu-id="f8439-198">型**A4SWIFT_FrrSendMTMsg**です。</span><span class="sxs-lookup"><span data-stu-id="f8439-198">Type **A4SWIFT_FrrSendMTMsg**.</span></span>|  
    |<span data-ttu-id="f8439-199">**[グループ]**</span><span class="sxs-lookup"><span data-stu-id="f8439-199">**Group**</span></span>|<span data-ttu-id="f8439-200">**そして**</span><span class="sxs-lookup"><span data-stu-id="f8439-200">**And**</span></span>|  
    |<span data-ttu-id="f8439-201">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="f8439-201">**Property**</span></span>|<span data-ttu-id="f8439-202">選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**です。</span><span class="sxs-lookup"><span data-stu-id="f8439-202">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.</span></span>|  
    |<span data-ttu-id="f8439-203">**演算子**</span><span class="sxs-lookup"><span data-stu-id="f8439-203">**Operator**</span></span>|<span data-ttu-id="f8439-204">選択 **==**です。</span><span class="sxs-lookup"><span data-stu-id="f8439-204">Select **==**.</span></span>|  
    |<span data-ttu-id="f8439-205">**値**</span><span class="sxs-lookup"><span data-stu-id="f8439-205">**Value**</span></span>|<span data-ttu-id="f8439-206">型 *\<NAKErrorCode >*、"Y01"などです。</span><span class="sxs-lookup"><span data-stu-id="f8439-206">Type *\<NAKErrorCode>*, such as "Y01".</span></span>|  
    |<span data-ttu-id="f8439-207">**[グループ]**</span><span class="sxs-lookup"><span data-stu-id="f8439-207">**Group**</span></span>|<span data-ttu-id="f8439-208">**Or**</span><span class="sxs-lookup"><span data-stu-id="f8439-208">**Or**</span></span>|  
    |<span data-ttu-id="f8439-209">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="f8439-209">**Property**</span></span>|<span data-ttu-id="f8439-210">選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**です。</span><span class="sxs-lookup"><span data-stu-id="f8439-210">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.</span></span>|  
    |<span data-ttu-id="f8439-211">**演算子**</span><span class="sxs-lookup"><span data-stu-id="f8439-211">**Operator**</span></span>|<span data-ttu-id="f8439-212">選択 **==**です。</span><span class="sxs-lookup"><span data-stu-id="f8439-212">Select **==**.</span></span>|  
    |<span data-ttu-id="f8439-213">**値**</span><span class="sxs-lookup"><span data-stu-id="f8439-213">**Value**</span></span>|<span data-ttu-id="f8439-214">型**TimedOut**です。</span><span class="sxs-lookup"><span data-stu-id="f8439-214">Type **TimedOut**.</span></span>|  
    |<span data-ttu-id="f8439-215">**[グループ]**</span><span class="sxs-lookup"><span data-stu-id="f8439-215">**Group**</span></span>|<span data-ttu-id="f8439-216">**Or**</span><span class="sxs-lookup"><span data-stu-id="f8439-216">**Or**</span></span>|  
    |<span data-ttu-id="f8439-217">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="f8439-217">**Property**</span></span>|<span data-ttu-id="f8439-218">選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**です。</span><span class="sxs-lookup"><span data-stu-id="f8439-218">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.</span></span>|  
    |<span data-ttu-id="f8439-219">**演算子**</span><span class="sxs-lookup"><span data-stu-id="f8439-219">**Operator**</span></span>|<span data-ttu-id="f8439-220">選択 **==**です。</span><span class="sxs-lookup"><span data-stu-id="f8439-220">Select **==**.</span></span>|  
    |<span data-ttu-id="f8439-221">**値**</span><span class="sxs-lookup"><span data-stu-id="f8439-221">**Value**</span></span>|<span data-ttu-id="f8439-222">型**TransportError**です。</span><span class="sxs-lookup"><span data-stu-id="f8439-222">Type **TransportError**.</span></span>|  
    |<span data-ttu-id="f8439-223">**[グループ]**</span><span class="sxs-lookup"><span data-stu-id="f8439-223">**Group**</span></span>|<span data-ttu-id="f8439-224">**Or**</span><span class="sxs-lookup"><span data-stu-id="f8439-224">**Or**</span></span>|  
    |<span data-ttu-id="f8439-225">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="f8439-225">**Property**</span></span>|<span data-ttu-id="f8439-226">選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**です。</span><span class="sxs-lookup"><span data-stu-id="f8439-226">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.</span></span>|  
    |<span data-ttu-id="f8439-227">**演算子**</span><span class="sxs-lookup"><span data-stu-id="f8439-227">**Operator**</span></span>|<span data-ttu-id="f8439-228">選択 **==**です。</span><span class="sxs-lookup"><span data-stu-id="f8439-228">Select **==**.</span></span>|  
    |<span data-ttu-id="f8439-229">**値**</span><span class="sxs-lookup"><span data-stu-id="f8439-229">**Value**</span></span>|<span data-ttu-id="f8439-230">型**DelayedNAK**です。</span><span class="sxs-lookup"><span data-stu-id="f8439-230">Type **DelayedNAK**.</span></span>|  
    |<span data-ttu-id="f8439-231">**[グループ]**</span><span class="sxs-lookup"><span data-stu-id="f8439-231">**Group**</span></span>|<span data-ttu-id="f8439-232">**Or**</span><span class="sxs-lookup"><span data-stu-id="f8439-232">**Or**</span></span>|  
    |<span data-ttu-id="f8439-233">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="f8439-233">**Property**</span></span>|<span data-ttu-id="f8439-234">選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**です。</span><span class="sxs-lookup"><span data-stu-id="f8439-234">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.</span></span>|  
    |<span data-ttu-id="f8439-235">**演算子**</span><span class="sxs-lookup"><span data-stu-id="f8439-235">**Operator**</span></span>|<span data-ttu-id="f8439-236">選択 **==**です。</span><span class="sxs-lookup"><span data-stu-id="f8439-236">Select **==**.</span></span>|  
    |<span data-ttu-id="f8439-237">**値**</span><span class="sxs-lookup"><span data-stu-id="f8439-237">**Value**</span></span>|<span data-ttu-id="f8439-238">型**AbortMessage**です。</span><span class="sxs-lookup"><span data-stu-id="f8439-238">Type **AbortMessage**.</span></span>|  
  
12. <span data-ttu-id="f8439-239">をクリックして**適用**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="f8439-239">Click **Apply**, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="f8439-240">送信ポートを右クリックし、をクリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="f8439-240">Right-click the send port, and then click **Start**.</span></span>  
  
14. <span data-ttu-id="f8439-241">手順 2. ~ 13. を必要なメッセージの種類ごとの送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="f8439-241">Repeat steps 2 through 13 to create a send port for each message type required.</span></span>