---
title: カスタム ハンドラーに送信するための FRR 送信ポートの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, send ports
- send ports, creating
- FRR, creating send ports
ms.assetid: 036f1f97-17a2-4e02-a85a-a52739a48528
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aeddd040dd3cfb0c423eea149a81a1395a468087
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378384"
---
# <a name="creating-the-frr-send-ports-for-sending-to-the-custom-handlers"></a><span data-ttu-id="4e61b-102">カスタム ハンドラーに送信するための FRR 送信ポートの作成</span><span class="sxs-lookup"><span data-stu-id="4e61b-102">Creating the FRR Send Ports for Sending to the Custom Handlers</span></span>
<span data-ttu-id="4e61b-103">FIN Response Reconciliation を実行する必要があります (元のメッセージまたは応答) メッセージを送信する各送信ポートの系列を作成するから[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]相関メッセージを処理するカスタム ハンドラーにします。</span><span class="sxs-lookup"><span data-stu-id="4e61b-103">To perform FIN Response Reconciliation, you need to create a series of send ports, each of which sends a message (original message or response) from [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] to the custom handlers that process the correlated messages.</span></span>  

 <span data-ttu-id="4e61b-104">**まとめ**</span><span class="sxs-lookup"><span data-stu-id="4e61b-104">**Summary**</span></span>  

 <span data-ttu-id="4e61b-105">次のプロパティとコンポーネントをそれぞれ 1 つが BTS の値によって識別して、一連の送信ポートを作成します。フィルターの操作:</span><span class="sxs-lookup"><span data-stu-id="4e61b-105">Create a series of send ports with the following properties and components, each one distinguished by the value of BTS.Operation in the filter:</span></span>  


|        <span data-ttu-id="4e61b-106">プロパティ/コンポーネント</span><span class="sxs-lookup"><span data-stu-id="4e61b-106">Property/Component</span></span>        |                                             <span data-ttu-id="4e61b-107">設定</span><span class="sxs-lookup"><span data-stu-id="4e61b-107">Setting</span></span>                                              |
|----------------------------------|--------------------------------------------------------------------------------------------------|
|            <span data-ttu-id="4e61b-108">送信ポート</span><span class="sxs-lookup"><span data-stu-id="4e61b-108">Send port</span></span>             |                                       <span data-ttu-id="4e61b-109">静的な一方向ポート</span><span class="sxs-lookup"><span data-stu-id="4e61b-109">Static one-way port</span></span>                                        |
|          <span data-ttu-id="4e61b-110">トランスポートの種類</span><span class="sxs-lookup"><span data-stu-id="4e61b-110">Transport type</span></span>          |                                               <span data-ttu-id="4e61b-111">FILE</span><span class="sxs-lookup"><span data-stu-id="4e61b-111">FILE</span></span>                                               |
| <span data-ttu-id="4e61b-112">コピー先フォルダー (アドレス URI)</span><span class="sxs-lookup"><span data-stu-id="4e61b-112">Destination folder (Address URI)</span></span> |                         <span data-ttu-id="4e61b-113">メッセージを送信するフォルダー</span><span class="sxs-lookup"><span data-stu-id="4e61b-113">The folder that you want to send the message to</span></span>                          |
|     <span data-ttu-id="4e61b-114">ファイル名 (アドレス URI)</span><span class="sxs-lookup"><span data-stu-id="4e61b-114">File name (Address URI)</span></span>      |                                         <span data-ttu-id="4e61b-115">%MessageID%.txt</span><span class="sxs-lookup"><span data-stu-id="4e61b-115">%MessageID%.txt</span></span>                                          |
|          <span data-ttu-id="4e61b-116">[送信パイプライン]</span><span class="sxs-lookup"><span data-stu-id="4e61b-116">Send pipeline</span></span>           | <span data-ttu-id="4e61b-117">Microsoft。BizTalk.DefaultPipelines します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-117">Microsoft .BizTalk.DefaultPipelines.</span></span> <span data-ttu-id="4e61b-118">PassThruTransmit</span><span class="sxs-lookup"><span data-stu-id="4e61b-118">PassThruTransmit</span></span> |
|             <span data-ttu-id="4e61b-119">フィルター</span><span class="sxs-lookup"><span data-stu-id="4e61b-119">Filters</span></span>              |                                   <span data-ttu-id="4e61b-120">次の表に示すように</span><span class="sxs-lookup"><span data-stu-id="4e61b-120">As shown in the tables below</span></span>                                   |

 <span data-ttu-id="4e61b-121">さまざまなメッセージの送信ポートは、BTS の値によって識別されます。操作は、送信ポートのフィルターです。</span><span class="sxs-lookup"><span data-stu-id="4e61b-121">The send ports for the different messages are distinguished by the value of BTS.Operation in the send port's filter.</span></span>  

### <a name="to-add-frr-send-ports-for-sending-to-the-custom-handlers"></a><span data-ttu-id="4e61b-122">カスタム ハンドラーに送信するための FRR 送信ポートを追加するには</span><span class="sxs-lookup"><span data-stu-id="4e61b-122">To add FRR send ports for sending to the custom handlers</span></span>  

1.  <span data-ttu-id="4e61b-123">BizTalk Server 管理コンソールで、右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的 1 waySend ポート**します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-123">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-waySend Port**.</span></span>  

2.  <span data-ttu-id="4e61b-124">送信ポートのプロパティ ダイアログ ボックスでの**名前**ボックスに、FRRCustomHandlersSendPort など、送信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-124">In the Send Port Properties dialog box, in the **Name** box, type a name for the send port, such as FRRCustomHandlersSendPort.</span></span>  

3.  <span data-ttu-id="4e61b-125">**型**、**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-125">For **Type**, select **FILE**.</span></span>  

4.  <span data-ttu-id="4e61b-126">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="4e61b-126">Click **Configure**.</span></span>  

5.  <span data-ttu-id="4e61b-127">[FILE トランスポートのプロパティ] ダイアログ ボックスで、**参照**します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-127">In the FILE Transport Properties dialog box, click **Browse**.</span></span>  

6.  <span data-ttu-id="4e61b-128">フォルダーの参照 ダイアログ ボックスからメッセージを送信するフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-128">In the Browse For Folder dialog box, move to the folder that you want to send messages from.</span></span> <span data-ttu-id="4e61b-129">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e61b-129">Click **OK**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="4e61b-130">このフォルダーが存在しない場合を使用してそれを作成、**フォルダの新規**コマンド。</span><span class="sxs-lookup"><span data-stu-id="4e61b-130">If this folder does not exist, you can create it using the **Make New Folder** command.</span></span>  

7.  <span data-ttu-id="4e61b-131">**ファイル名**ボックスに「 **%MessageID%.txt**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-131">In the **File name** box, type **%MessageID%.txt**, and then click **OK**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="4e61b-132">メッセージの種類ごとに別のフォルダーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="4e61b-132">You can create a different folder for each type of message.</span></span>  

8.  <span data-ttu-id="4e61b-133">送信ポートのプロパティ ダイアログ ボックスの送信ハンドラーであることを確認**BizTalkServerApplication**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="4e61b-133">In the Send Port Properties dialog box, for Send handler, verify that **BizTalkServerApplication** is selected.</span></span>  

9. <span data-ttu-id="4e61b-134">**送信パイプライン**、 **PassThruTransmit**します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-134">For **Send Pipeline**, select **PassThruTransmit**.</span></span>  

10. <span data-ttu-id="4e61b-135">クリックして**フィルター**左側のウィンドウで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4e61b-135">Click **Filters** in the left pane, and then do the following:</span></span>  

    |<span data-ttu-id="4e61b-136">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4e61b-136">Use this</span></span>|<span data-ttu-id="4e61b-137">目的</span><span class="sxs-lookup"><span data-stu-id="4e61b-137">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="4e61b-138">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="4e61b-138">**Property**</span></span>|<span data-ttu-id="4e61b-139">選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SendingServiceType**します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-139">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SendingServiceType**.</span></span>|  
    |<span data-ttu-id="4e61b-140">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="4e61b-140">**Operator**</span></span>|<span data-ttu-id="4e61b-141">選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-141">Select **==**.</span></span>|  
    |<span data-ttu-id="4e61b-142">**[値]**</span><span class="sxs-lookup"><span data-stu-id="4e61b-142">**Value**</span></span>|<span data-ttu-id="4e61b-143">型**A4SWIFT_FrrService**します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-143">Type **A4SWIFT_FrrService**.</span></span>|  
    |<span data-ttu-id="4e61b-144">**[グループ]**</span><span class="sxs-lookup"><span data-stu-id="4e61b-144">**Group**</span></span>|<span data-ttu-id="4e61b-145">**And**</span><span class="sxs-lookup"><span data-stu-id="4e61b-145">**And**</span></span>|  
    |<span data-ttu-id="4e61b-146">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="4e61b-146">**Property**</span></span>|<span data-ttu-id="4e61b-147">選択**BTS します。操作**します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-147">Select **BTS.Operation**.</span></span>|  
    |<span data-ttu-id="4e61b-148">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="4e61b-148">**Operator**</span></span>|<span data-ttu-id="4e61b-149">選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-149">Select **==**.</span></span>|  
    |<span data-ttu-id="4e61b-150">**[値]**</span><span class="sxs-lookup"><span data-stu-id="4e61b-150">**Value**</span></span>|<span data-ttu-id="4e61b-151">BTS のいずれかを入力します。次の表からの値を操作します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-151">Type one of the BTS.Operation values from the table below.</span></span>|  

     <span data-ttu-id="4e61b-152">BTS の.操作では、次の値のいずれかを入力します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-152">For BTS.Operation, enter one of the following values:</span></span>  

    |<span data-ttu-id="4e61b-153">メッセージ型</span><span class="sxs-lookup"><span data-stu-id="4e61b-153">Message type</span></span>|<span data-ttu-id="4e61b-154">BTS します。操作の値</span><span class="sxs-lookup"><span data-stu-id="4e61b-154">BTS.Operation value</span></span>|  
    |------------------|-------------------------|  
    |<span data-ttu-id="4e61b-155">すべてのカテゴリ 0 ~ 9 SWIFT FIN メッセージの種類</span><span class="sxs-lookup"><span data-stu-id="4e61b-155">All Category 0 to 9 SWIFT FIN message types</span></span>|<span data-ttu-id="4e61b-156">**A4SWIFT_FrrSendMTMsg**</span><span class="sxs-lookup"><span data-stu-id="4e61b-156">**A4SWIFT_FrrSendMTMsg**</span></span>|  
    |<span data-ttu-id="4e61b-157">MQ Series パン/NAN (MQ Series トランス ポート レベル ACK/NAK)</span><span class="sxs-lookup"><span data-stu-id="4e61b-157">MQ Series PAN/NAN (MQ Series transport-level ACK/NAK)</span></span>|<span data-ttu-id="4e61b-158">**A4SWIFT_FrrSendTransport**</span><span class="sxs-lookup"><span data-stu-id="4e61b-158">**A4SWIFT_FrrSendTransport**</span></span>|  
    |<span data-ttu-id="4e61b-159">MT010 (警告の配信不能)</span><span class="sxs-lookup"><span data-stu-id="4e61b-159">MT010 (Non-Delivery Warning)</span></span>|<span data-ttu-id="4e61b-160">**A4SWIFT_FrrSend010NDW**</span><span class="sxs-lookup"><span data-stu-id="4e61b-160">**A4SWIFT_FrrSend010NDW**</span></span>|  
    |<span data-ttu-id="4e61b-161">MT011 (配信通知)</span><span class="sxs-lookup"><span data-stu-id="4e61b-161">MT011 (Delivery Notification)</span></span>|<span data-ttu-id="4e61b-162">**A4SWIFT_FrrSend011Delivered**</span><span class="sxs-lookup"><span data-stu-id="4e61b-162">**A4SWIFT_FrrSend011Delivered**</span></span>|  
    |<span data-ttu-id="4e61b-163">MT012 (送信者の通知)</span><span class="sxs-lookup"><span data-stu-id="4e61b-163">MT012 (Sender Notification)</span></span>|<span data-ttu-id="4e61b-164">**A4SWIFT_FrrSend012SenderACK**</span><span class="sxs-lookup"><span data-stu-id="4e61b-164">**A4SWIFT_FrrSend012SenderACK**</span></span>|  
    |<span data-ttu-id="4e61b-165">MT015 (DNK、または遅延 NAK)</span><span class="sxs-lookup"><span data-stu-id="4e61b-165">MT015 (DNK, or Delayed NAK)</span></span>|<span data-ttu-id="4e61b-166">**A4SWIFT_FrrSend015DNK**</span><span class="sxs-lookup"><span data-stu-id="4e61b-166">**A4SWIFT_FrrSend015DNK**</span></span>|  
    |<span data-ttu-id="4e61b-167">MT019 (通知を中止)</span><span class="sxs-lookup"><span data-stu-id="4e61b-167">MT019 (Abort Notification)</span></span>|<span data-ttu-id="4e61b-168">**A4SWIFT_FrrSend019Abort**</span><span class="sxs-lookup"><span data-stu-id="4e61b-168">**A4SWIFT_FrrSend019Abort**</span></span>|  
    |<span data-ttu-id="4e61b-169">MTS21_FIN_ACKNAK (、LT (ACK) によって送信された FIN メッセージの受信確認</span><span class="sxs-lookup"><span data-stu-id="4e61b-169">MTS21_FIN_ACKNAK (Acknowledgment of a FIN message sent by an LT (ACK)</span></span>|<span data-ttu-id="4e61b-170">**A4SWIFT_FrrSendS21ACK**</span><span class="sxs-lookup"><span data-stu-id="4e61b-170">**A4SWIFT_FrrSendS21ACK**</span></span>|  
    |<span data-ttu-id="4e61b-171">MTS21_FIN_ACKNAK (否定、LT (NAK) によって送信された FIN メッセージの受信確認</span><span class="sxs-lookup"><span data-stu-id="4e61b-171">MTS21_FIN_ACKNAK (Negative acknowledgment of a FIN message sent by an LT (NAK)</span></span>|<span data-ttu-id="4e61b-172">**A4SWIFT_FrrSendS21NAK**</span><span class="sxs-lookup"><span data-stu-id="4e61b-172">**A4SWIFT_FrrSendS21NAK**</span></span>|  

11. <span data-ttu-id="4e61b-173">次の操作が正常に送信されていないカテゴリ 0 ~ 9 の SWIFT FIN メッセージに対して、**フィルター**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="4e61b-173">For Category 0 to 9 SWIFT FIN messages that are not successfully sent, do the following in the **Filters** pane:</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="4e61b-174">**A4SWIFT_FRRFailedReason**で次のフィルターのプロパティをグループ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e61b-174">The **A4SWIFT_FRRFailedReason** properties in the following filter should be grouped.</span></span>  

    |<span data-ttu-id="4e61b-175">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4e61b-175">Use this</span></span>|<span data-ttu-id="4e61b-176">目的</span><span class="sxs-lookup"><span data-stu-id="4e61b-176">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="4e61b-177">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="4e61b-177">**Property**</span></span>|<span data-ttu-id="4e61b-178">選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SendingServiceType**します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-178">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SendingServiceType**.</span></span>|  
    |<span data-ttu-id="4e61b-179">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="4e61b-179">**Operator**</span></span>|<span data-ttu-id="4e61b-180">選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-180">Select **==**.</span></span>|  
    |<span data-ttu-id="4e61b-181">**[値]**</span><span class="sxs-lookup"><span data-stu-id="4e61b-181">**Value**</span></span>|<span data-ttu-id="4e61b-182">型**A4SWIFT_FrrService**します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-182">Type **A4SWIFT_FrrService**.</span></span>|  
    |<span data-ttu-id="4e61b-183">**[グループ]**</span><span class="sxs-lookup"><span data-stu-id="4e61b-183">**Group**</span></span>|<span data-ttu-id="4e61b-184">**And**</span><span class="sxs-lookup"><span data-stu-id="4e61b-184">**And**</span></span>|  
    |<span data-ttu-id="4e61b-185">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="4e61b-185">**Property**</span></span>|<span data-ttu-id="4e61b-186">選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FrrFailed**します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-186">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FrrFailed**.</span></span>|  
    |<span data-ttu-id="4e61b-187">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="4e61b-187">**Operator**</span></span>|<span data-ttu-id="4e61b-188">選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-188">Select **==**.</span></span>|  
    |<span data-ttu-id="4e61b-189">**[値]**</span><span class="sxs-lookup"><span data-stu-id="4e61b-189">**Value**</span></span>|<span data-ttu-id="4e61b-190">型**True**します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-190">Type **True**.</span></span>|  
    |<span data-ttu-id="4e61b-191">**[グループ]**</span><span class="sxs-lookup"><span data-stu-id="4e61b-191">**Group**</span></span>|<span data-ttu-id="4e61b-192">**And**</span><span class="sxs-lookup"><span data-stu-id="4e61b-192">**And**</span></span>|  
    |<span data-ttu-id="4e61b-193">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="4e61b-193">**Property**</span></span>|<span data-ttu-id="4e61b-194">選択**BTS します。操作**します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-194">Select **BTS.Operation**.</span></span>|  
    |<span data-ttu-id="4e61b-195">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="4e61b-195">**Operator**</span></span>|<span data-ttu-id="4e61b-196">選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-196">Select **==**.</span></span>|  
    |<span data-ttu-id="4e61b-197">**[値]**</span><span class="sxs-lookup"><span data-stu-id="4e61b-197">**Value**</span></span>|<span data-ttu-id="4e61b-198">型**A4SWIFT_FrrSendMTMsg**します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-198">Type **A4SWIFT_FrrSendMTMsg**.</span></span>|  
    |<span data-ttu-id="4e61b-199">**[グループ]**</span><span class="sxs-lookup"><span data-stu-id="4e61b-199">**Group**</span></span>|<span data-ttu-id="4e61b-200">**And**</span><span class="sxs-lookup"><span data-stu-id="4e61b-200">**And**</span></span>|  
    |<span data-ttu-id="4e61b-201">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="4e61b-201">**Property**</span></span>|<span data-ttu-id="4e61b-202">選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-202">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.</span></span>|  
    |<span data-ttu-id="4e61b-203">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="4e61b-203">**Operator**</span></span>|<span data-ttu-id="4e61b-204">選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-204">Select **==**.</span></span>|  
    |<span data-ttu-id="4e61b-205">**[値]**</span><span class="sxs-lookup"><span data-stu-id="4e61b-205">**Value**</span></span>|<span data-ttu-id="4e61b-206">型 *\<NAKErrorCode\>*、"Y01"など。</span><span class="sxs-lookup"><span data-stu-id="4e61b-206">Type *\<NAKErrorCode\>*, such as "Y01".</span></span>|  
    |<span data-ttu-id="4e61b-207">**[グループ]**</span><span class="sxs-lookup"><span data-stu-id="4e61b-207">**Group**</span></span>|<span data-ttu-id="4e61b-208">**Or**</span><span class="sxs-lookup"><span data-stu-id="4e61b-208">**Or**</span></span>|  
    |<span data-ttu-id="4e61b-209">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="4e61b-209">**Property**</span></span>|<span data-ttu-id="4e61b-210">選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-210">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.</span></span>|  
    |<span data-ttu-id="4e61b-211">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="4e61b-211">**Operator**</span></span>|<span data-ttu-id="4e61b-212">選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-212">Select **==**.</span></span>|  
    |<span data-ttu-id="4e61b-213">**[値]**</span><span class="sxs-lookup"><span data-stu-id="4e61b-213">**Value**</span></span>|<span data-ttu-id="4e61b-214">型**TimedOut**します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-214">Type **TimedOut**.</span></span>|  
    |<span data-ttu-id="4e61b-215">**[グループ]**</span><span class="sxs-lookup"><span data-stu-id="4e61b-215">**Group**</span></span>|<span data-ttu-id="4e61b-216">**Or**</span><span class="sxs-lookup"><span data-stu-id="4e61b-216">**Or**</span></span>|  
    |<span data-ttu-id="4e61b-217">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="4e61b-217">**Property**</span></span>|<span data-ttu-id="4e61b-218">選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-218">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.</span></span>|  
    |<span data-ttu-id="4e61b-219">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="4e61b-219">**Operator**</span></span>|<span data-ttu-id="4e61b-220">選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-220">Select **==**.</span></span>|  
    |<span data-ttu-id="4e61b-221">**[値]**</span><span class="sxs-lookup"><span data-stu-id="4e61b-221">**Value**</span></span>|<span data-ttu-id="4e61b-222">型**TransportError**します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-222">Type **TransportError**.</span></span>|  
    |<span data-ttu-id="4e61b-223">**[グループ]**</span><span class="sxs-lookup"><span data-stu-id="4e61b-223">**Group**</span></span>|<span data-ttu-id="4e61b-224">**Or**</span><span class="sxs-lookup"><span data-stu-id="4e61b-224">**Or**</span></span>|  
    |<span data-ttu-id="4e61b-225">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="4e61b-225">**Property**</span></span>|<span data-ttu-id="4e61b-226">選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-226">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.</span></span>|  
    |<span data-ttu-id="4e61b-227">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="4e61b-227">**Operator**</span></span>|<span data-ttu-id="4e61b-228">選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-228">Select **==**.</span></span>|  
    |<span data-ttu-id="4e61b-229">**[値]**</span><span class="sxs-lookup"><span data-stu-id="4e61b-229">**Value**</span></span>|<span data-ttu-id="4e61b-230">型**DelayedNAK**します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-230">Type **DelayedNAK**.</span></span>|  
    |<span data-ttu-id="4e61b-231">**[グループ]**</span><span class="sxs-lookup"><span data-stu-id="4e61b-231">**Group**</span></span>|<span data-ttu-id="4e61b-232">**Or**</span><span class="sxs-lookup"><span data-stu-id="4e61b-232">**Or**</span></span>|  
    |<span data-ttu-id="4e61b-233">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="4e61b-233">**Property**</span></span>|<span data-ttu-id="4e61b-234">選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-234">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.</span></span>|  
    |<span data-ttu-id="4e61b-235">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="4e61b-235">**Operator**</span></span>|<span data-ttu-id="4e61b-236">選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-236">Select **==**.</span></span>|  
    |<span data-ttu-id="4e61b-237">**[値]**</span><span class="sxs-lookup"><span data-stu-id="4e61b-237">**Value**</span></span>|<span data-ttu-id="4e61b-238">型**AbortMessage**します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-238">Type **AbortMessage**.</span></span>|  

12. <span data-ttu-id="4e61b-239">クリックして**適用**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-239">Click **Apply**, and then click **OK**.</span></span>  

13. <span data-ttu-id="4e61b-240">送信ポートを右クリックし、**開始**します。</span><span class="sxs-lookup"><span data-stu-id="4e61b-240">Right-click the send port, and then click **Start**.</span></span>  

14. <span data-ttu-id="4e61b-241">手順 2. ~ 13 に必要なメッセージの種類ごとの送信ポートを作成する.</span><span class="sxs-lookup"><span data-stu-id="4e61b-241">Repeat steps 2 through 13 to create a send port for each message type required.</span></span>