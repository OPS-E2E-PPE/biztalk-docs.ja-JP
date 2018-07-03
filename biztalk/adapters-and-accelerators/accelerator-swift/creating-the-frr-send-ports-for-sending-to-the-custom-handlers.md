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
ms.openlocfilehash: ed467b149674580b9ed8921a59433c5402a24a0e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013939"
---
# <a name="creating-the-frr-send-ports-for-sending-to-the-custom-handlers"></a><span data-ttu-id="a605d-102">カスタム ハンドラーに送信するための FRR 送信ポートの作成</span><span class="sxs-lookup"><span data-stu-id="a605d-102">Creating the FRR Send Ports for Sending to the Custom Handlers</span></span>
<span data-ttu-id="a605d-103">FIN Response Reconciliation を実行する必要があります (元のメッセージまたは応答) メッセージを送信する各送信ポートの系列を作成するから[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]相関メッセージを処理するカスタム ハンドラーにします。</span><span class="sxs-lookup"><span data-stu-id="a605d-103">To perform FIN Response Reconciliation, you need to create a series of send ports, each of which sends a message (original message or response) from [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] to the custom handlers that process the correlated messages.</span></span>  

 <span data-ttu-id="a605d-104">**概要**</span><span class="sxs-lookup"><span data-stu-id="a605d-104">**Summary**</span></span>  

 <span data-ttu-id="a605d-105">次のプロパティとコンポーネントをそれぞれ 1 つが BTS の値によって識別して、一連の送信ポートを作成します。フィルターの操作:</span><span class="sxs-lookup"><span data-stu-id="a605d-105">Create a series of send ports with the following properties and components, each one distinguished by the value of BTS.Operation in the filter:</span></span>  


|        <span data-ttu-id="a605d-106">プロパティ/コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a605d-106">Property/Component</span></span>        |                                             <span data-ttu-id="a605d-107">設定</span><span class="sxs-lookup"><span data-stu-id="a605d-107">Setting</span></span>                                              |
|----------------------------------|--------------------------------------------------------------------------------------------------|
|            <span data-ttu-id="a605d-108">送信ポート</span><span class="sxs-lookup"><span data-stu-id="a605d-108">Send port</span></span>             |                                       <span data-ttu-id="a605d-109">静的な一方向ポート</span><span class="sxs-lookup"><span data-stu-id="a605d-109">Static one-way port</span></span>                                        |
|          <span data-ttu-id="a605d-110">トランスポートの種類</span><span class="sxs-lookup"><span data-stu-id="a605d-110">Transport type</span></span>          |                                               <span data-ttu-id="a605d-111">FILE</span><span class="sxs-lookup"><span data-stu-id="a605d-111">FILE</span></span>                                               |
| <span data-ttu-id="a605d-112">コピー先フォルダー (アドレス URI)</span><span class="sxs-lookup"><span data-stu-id="a605d-112">Destination folder (Address URI)</span></span> |                         <span data-ttu-id="a605d-113">メッセージを送信するフォルダー</span><span class="sxs-lookup"><span data-stu-id="a605d-113">The folder that you want to send the message to</span></span>                          |
|     <span data-ttu-id="a605d-114">ファイル名 (アドレス URI)</span><span class="sxs-lookup"><span data-stu-id="a605d-114">File name (Address URI)</span></span>      |                                         <span data-ttu-id="a605d-115">%MessageID%.txt</span><span class="sxs-lookup"><span data-stu-id="a605d-115">%MessageID%.txt</span></span>                                          |
|          <span data-ttu-id="a605d-116">[送信パイプライン]</span><span class="sxs-lookup"><span data-stu-id="a605d-116">Send pipeline</span></span>           | <span data-ttu-id="a605d-117">Microsoft。BizTalk.DefaultPipelines します。</span><span class="sxs-lookup"><span data-stu-id="a605d-117">Microsoft .BizTalk.DefaultPipelines.</span></span> <span data-ttu-id="a605d-118">PassThruTransmit</span><span class="sxs-lookup"><span data-stu-id="a605d-118">PassThruTransmit</span></span> |
|             <span data-ttu-id="a605d-119">フィルター</span><span class="sxs-lookup"><span data-stu-id="a605d-119">Filters</span></span>              |                                   <span data-ttu-id="a605d-120">次の表に示すように</span><span class="sxs-lookup"><span data-stu-id="a605d-120">As shown in the tables below</span></span>                                   |

 <span data-ttu-id="a605d-121">さまざまなメッセージの送信ポートは、BTS の値によって識別されます。操作は、送信ポートのフィルターです。</span><span class="sxs-lookup"><span data-stu-id="a605d-121">The send ports for the different messages are distinguished by the value of BTS.Operation in the send port's filter.</span></span>  

### <a name="to-add-frr-send-ports-for-sending-to-the-custom-handlers"></a><span data-ttu-id="a605d-122">カスタム ハンドラーに送信するための FRR 送信ポートを追加するには</span><span class="sxs-lookup"><span data-stu-id="a605d-122">To add FRR send ports for sending to the custom handlers</span></span>  

1.  <span data-ttu-id="a605d-123">BizTalk Server 管理コンソールで、右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的 1 waySend ポート**します。</span><span class="sxs-lookup"><span data-stu-id="a605d-123">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-waySend Port**.</span></span>  

2.  <span data-ttu-id="a605d-124">送信ポートのプロパティ ダイアログ ボックスでの**名前**ボックスに、FRRCustomHandlersSendPort など、送信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a605d-124">In the Send Port Properties dialog box, in the **Name** box, type a name for the send port, such as FRRCustomHandlersSendPort.</span></span>  

3.  <span data-ttu-id="a605d-125">**型**、**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="a605d-125">For **Type**, select **FILE**.</span></span>  

4.  <span data-ttu-id="a605d-126">クリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="a605d-126">Click **Configure**.</span></span>  

5.  <span data-ttu-id="a605d-127">[FILE トランスポートのプロパティ] ダイアログ ボックスで、**参照**します。</span><span class="sxs-lookup"><span data-stu-id="a605d-127">In the FILE Transport Properties dialog box, click **Browse**.</span></span>  

6.  <span data-ttu-id="a605d-128">フォルダーの参照 ダイアログ ボックスからメッセージを送信するフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="a605d-128">In the Browse For Folder dialog box, move to the folder that you want to send messages from.</span></span> <span data-ttu-id="a605d-129">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a605d-129">Click **OK**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="a605d-130">このフォルダーが存在しない場合を使用してそれを作成、**フォルダの新規**コマンド。</span><span class="sxs-lookup"><span data-stu-id="a605d-130">If this folder does not exist, you can create it using the **Make New Folder** command.</span></span>  

7.  <span data-ttu-id="a605d-131">**ファイル名**ボックスに「 **%MessageID%.txt**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="a605d-131">In the **File name** box, type **%MessageID%.txt**, and then click **OK**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="a605d-132">メッセージの種類ごとに別のフォルダーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="a605d-132">You can create a different folder for each type of message.</span></span>  

8.  <span data-ttu-id="a605d-133">送信ポートのプロパティ ダイアログ ボックスの送信ハンドラーであることを確認**BizTalkServerApplication**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="a605d-133">In the Send Port Properties dialog box, for Send handler, verify that **BizTalkServerApplication** is selected.</span></span>  

9. <span data-ttu-id="a605d-134">**送信パイプライン**、 **PassThruTransmit**します。</span><span class="sxs-lookup"><span data-stu-id="a605d-134">For **Send Pipeline**, select **PassThruTransmit**.</span></span>  

10. <span data-ttu-id="a605d-135">クリックして**フィルター**左側のウィンドウで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a605d-135">Click **Filters** in the left pane, and then do the following:</span></span>  

    |<span data-ttu-id="a605d-136">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a605d-136">Use this</span></span>|<span data-ttu-id="a605d-137">目的</span><span class="sxs-lookup"><span data-stu-id="a605d-137">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="a605d-138">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="a605d-138">**Property**</span></span>|<span data-ttu-id="a605d-139">選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SendingServiceType**します。</span><span class="sxs-lookup"><span data-stu-id="a605d-139">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SendingServiceType**.</span></span>|  
    |<span data-ttu-id="a605d-140">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="a605d-140">**Operator**</span></span>|<span data-ttu-id="a605d-141">選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="a605d-141">Select **==**.</span></span>|  
    |<span data-ttu-id="a605d-142">**[値]**</span><span class="sxs-lookup"><span data-stu-id="a605d-142">**Value**</span></span>|<span data-ttu-id="a605d-143">型**A4SWIFT_FrrService**します。</span><span class="sxs-lookup"><span data-stu-id="a605d-143">Type **A4SWIFT_FrrService**.</span></span>|  
    |<span data-ttu-id="a605d-144">**[グループ]**</span><span class="sxs-lookup"><span data-stu-id="a605d-144">**Group**</span></span>|<span data-ttu-id="a605d-145">**And**</span><span class="sxs-lookup"><span data-stu-id="a605d-145">**And**</span></span>|  
    |<span data-ttu-id="a605d-146">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="a605d-146">**Property**</span></span>|<span data-ttu-id="a605d-147">選択**BTS します。操作**します。</span><span class="sxs-lookup"><span data-stu-id="a605d-147">Select **BTS.Operation**.</span></span>|  
    |<span data-ttu-id="a605d-148">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="a605d-148">**Operator**</span></span>|<span data-ttu-id="a605d-149">選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="a605d-149">Select **==**.</span></span>|  
    |<span data-ttu-id="a605d-150">**[値]**</span><span class="sxs-lookup"><span data-stu-id="a605d-150">**Value**</span></span>|<span data-ttu-id="a605d-151">BTS のいずれかを入力します。次の表からの値を操作します。</span><span class="sxs-lookup"><span data-stu-id="a605d-151">Type one of the BTS.Operation values from the table below.</span></span>|  

     <span data-ttu-id="a605d-152">BTS の.操作では、次の値のいずれかを入力します。</span><span class="sxs-lookup"><span data-stu-id="a605d-152">For BTS.Operation, enter one of the following values:</span></span>  

    |<span data-ttu-id="a605d-153">メッセージ型</span><span class="sxs-lookup"><span data-stu-id="a605d-153">Message type</span></span>|<span data-ttu-id="a605d-154">BTS します。操作の値</span><span class="sxs-lookup"><span data-stu-id="a605d-154">BTS.Operation value</span></span>|  
    |------------------|-------------------------|  
    |<span data-ttu-id="a605d-155">すべてのカテゴリ 0 ~ 9 SWIFT FIN メッセージの種類</span><span class="sxs-lookup"><span data-stu-id="a605d-155">All Category 0 to 9 SWIFT FIN message types</span></span>|<span data-ttu-id="a605d-156">**A4SWIFT_FrrSendMTMsg**</span><span class="sxs-lookup"><span data-stu-id="a605d-156">**A4SWIFT_FrrSendMTMsg**</span></span>|  
    |<span data-ttu-id="a605d-157">MQ Series パン/NAN (MQ Series トランス ポート レベル ACK/NAK)</span><span class="sxs-lookup"><span data-stu-id="a605d-157">MQ Series PAN/NAN (MQ Series transport-level ACK/NAK)</span></span>|<span data-ttu-id="a605d-158">**A4SWIFT_FrrSendTransport**</span><span class="sxs-lookup"><span data-stu-id="a605d-158">**A4SWIFT_FrrSendTransport**</span></span>|  
    |<span data-ttu-id="a605d-159">MT010 (警告の配信不能)</span><span class="sxs-lookup"><span data-stu-id="a605d-159">MT010 (Non-Delivery Warning)</span></span>|<span data-ttu-id="a605d-160">**A4SWIFT_FrrSend010NDW**</span><span class="sxs-lookup"><span data-stu-id="a605d-160">**A4SWIFT_FrrSend010NDW**</span></span>|  
    |<span data-ttu-id="a605d-161">MT011 (配信通知)</span><span class="sxs-lookup"><span data-stu-id="a605d-161">MT011 (Delivery Notification)</span></span>|<span data-ttu-id="a605d-162">**A4SWIFT_FrrSend011Delivered**</span><span class="sxs-lookup"><span data-stu-id="a605d-162">**A4SWIFT_FrrSend011Delivered**</span></span>|  
    |<span data-ttu-id="a605d-163">MT012 (送信者の通知)</span><span class="sxs-lookup"><span data-stu-id="a605d-163">MT012 (Sender Notification)</span></span>|<span data-ttu-id="a605d-164">**A4SWIFT_FrrSend012SenderACK**</span><span class="sxs-lookup"><span data-stu-id="a605d-164">**A4SWIFT_FrrSend012SenderACK**</span></span>|  
    |<span data-ttu-id="a605d-165">MT015 (DNK、または遅延 NAK)</span><span class="sxs-lookup"><span data-stu-id="a605d-165">MT015 (DNK, or Delayed NAK)</span></span>|<span data-ttu-id="a605d-166">**A4SWIFT_FrrSend015DNK**</span><span class="sxs-lookup"><span data-stu-id="a605d-166">**A4SWIFT_FrrSend015DNK**</span></span>|  
    |<span data-ttu-id="a605d-167">MT019 (通知を中止)</span><span class="sxs-lookup"><span data-stu-id="a605d-167">MT019 (Abort Notification)</span></span>|<span data-ttu-id="a605d-168">**A4SWIFT_FrrSend019Abort**</span><span class="sxs-lookup"><span data-stu-id="a605d-168">**A4SWIFT_FrrSend019Abort**</span></span>|  
    |<span data-ttu-id="a605d-169">MTS21_FIN_ACKNAK (、LT (ACK) によって送信された FIN メッセージの受信確認</span><span class="sxs-lookup"><span data-stu-id="a605d-169">MTS21_FIN_ACKNAK (Acknowledgment of a FIN message sent by an LT (ACK)</span></span>|<span data-ttu-id="a605d-170">**A4SWIFT_FrrSendS21ACK**</span><span class="sxs-lookup"><span data-stu-id="a605d-170">**A4SWIFT_FrrSendS21ACK**</span></span>|  
    |<span data-ttu-id="a605d-171">MTS21_FIN_ACKNAK (否定、LT (NAK) によって送信された FIN メッセージの受信確認</span><span class="sxs-lookup"><span data-stu-id="a605d-171">MTS21_FIN_ACKNAK (Negative acknowledgment of a FIN message sent by an LT (NAK)</span></span>|<span data-ttu-id="a605d-172">**A4SWIFT_FrrSendS21NAK**</span><span class="sxs-lookup"><span data-stu-id="a605d-172">**A4SWIFT_FrrSendS21NAK**</span></span>|  

11. <span data-ttu-id="a605d-173">次の操作が正常に送信されていないカテゴリ 0 ~ 9 の SWIFT FIN メッセージに対して、**フィルター**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="a605d-173">For Category 0 to 9 SWIFT FIN messages that are not successfully sent, do the following in the **Filters** pane:</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="a605d-174">**A4SWIFT_FRRFailedReason**で次のフィルターのプロパティをグループ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a605d-174">The **A4SWIFT_FRRFailedReason** properties in the following filter should be grouped.</span></span>  

    |<span data-ttu-id="a605d-175">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a605d-175">Use this</span></span>|<span data-ttu-id="a605d-176">目的</span><span class="sxs-lookup"><span data-stu-id="a605d-176">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="a605d-177">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="a605d-177">**Property**</span></span>|<span data-ttu-id="a605d-178">選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SendingServiceType**します。</span><span class="sxs-lookup"><span data-stu-id="a605d-178">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SendingServiceType**.</span></span>|  
    |<span data-ttu-id="a605d-179">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="a605d-179">**Operator**</span></span>|<span data-ttu-id="a605d-180">選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="a605d-180">Select **==**.</span></span>|  
    |<span data-ttu-id="a605d-181">**[値]**</span><span class="sxs-lookup"><span data-stu-id="a605d-181">**Value**</span></span>|<span data-ttu-id="a605d-182">型**A4SWIFT_FrrService**します。</span><span class="sxs-lookup"><span data-stu-id="a605d-182">Type **A4SWIFT_FrrService**.</span></span>|  
    |<span data-ttu-id="a605d-183">**[グループ]**</span><span class="sxs-lookup"><span data-stu-id="a605d-183">**Group**</span></span>|<span data-ttu-id="a605d-184">**And**</span><span class="sxs-lookup"><span data-stu-id="a605d-184">**And**</span></span>|  
    |<span data-ttu-id="a605d-185">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="a605d-185">**Property**</span></span>|<span data-ttu-id="a605d-186">選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FrrFailed**します。</span><span class="sxs-lookup"><span data-stu-id="a605d-186">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FrrFailed**.</span></span>|  
    |<span data-ttu-id="a605d-187">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="a605d-187">**Operator**</span></span>|<span data-ttu-id="a605d-188">選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="a605d-188">Select **==**.</span></span>|  
    |<span data-ttu-id="a605d-189">**[値]**</span><span class="sxs-lookup"><span data-stu-id="a605d-189">**Value**</span></span>|<span data-ttu-id="a605d-190">型**True**します。</span><span class="sxs-lookup"><span data-stu-id="a605d-190">Type **True**.</span></span>|  
    |<span data-ttu-id="a605d-191">**[グループ]**</span><span class="sxs-lookup"><span data-stu-id="a605d-191">**Group**</span></span>|<span data-ttu-id="a605d-192">**And**</span><span class="sxs-lookup"><span data-stu-id="a605d-192">**And**</span></span>|  
    |<span data-ttu-id="a605d-193">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="a605d-193">**Property**</span></span>|<span data-ttu-id="a605d-194">選択**BTS します。操作**します。</span><span class="sxs-lookup"><span data-stu-id="a605d-194">Select **BTS.Operation**.</span></span>|  
    |<span data-ttu-id="a605d-195">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="a605d-195">**Operator**</span></span>|<span data-ttu-id="a605d-196">選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="a605d-196">Select **==**.</span></span>|  
    |<span data-ttu-id="a605d-197">**[値]**</span><span class="sxs-lookup"><span data-stu-id="a605d-197">**Value**</span></span>|<span data-ttu-id="a605d-198">型**A4SWIFT_FrrSendMTMsg**します。</span><span class="sxs-lookup"><span data-stu-id="a605d-198">Type **A4SWIFT_FrrSendMTMsg**.</span></span>|  
    |<span data-ttu-id="a605d-199">**[グループ]**</span><span class="sxs-lookup"><span data-stu-id="a605d-199">**Group**</span></span>|<span data-ttu-id="a605d-200">**And**</span><span class="sxs-lookup"><span data-stu-id="a605d-200">**And**</span></span>|  
    |<span data-ttu-id="a605d-201">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="a605d-201">**Property**</span></span>|<span data-ttu-id="a605d-202">選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**します。</span><span class="sxs-lookup"><span data-stu-id="a605d-202">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.</span></span>|  
    |<span data-ttu-id="a605d-203">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="a605d-203">**Operator**</span></span>|<span data-ttu-id="a605d-204">選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="a605d-204">Select **==**.</span></span>|  
    |<span data-ttu-id="a605d-205">**[値]**</span><span class="sxs-lookup"><span data-stu-id="a605d-205">**Value**</span></span>|<span data-ttu-id="a605d-206">型 *\<NAKErrorCode\>*、"Y01"など。</span><span class="sxs-lookup"><span data-stu-id="a605d-206">Type *\<NAKErrorCode\>*, such as "Y01".</span></span>|  
    |<span data-ttu-id="a605d-207">**[グループ]**</span><span class="sxs-lookup"><span data-stu-id="a605d-207">**Group**</span></span>|<span data-ttu-id="a605d-208">**Or**</span><span class="sxs-lookup"><span data-stu-id="a605d-208">**Or**</span></span>|  
    |<span data-ttu-id="a605d-209">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="a605d-209">**Property**</span></span>|<span data-ttu-id="a605d-210">選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**します。</span><span class="sxs-lookup"><span data-stu-id="a605d-210">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.</span></span>|  
    |<span data-ttu-id="a605d-211">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="a605d-211">**Operator**</span></span>|<span data-ttu-id="a605d-212">選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="a605d-212">Select **==**.</span></span>|  
    |<span data-ttu-id="a605d-213">**[値]**</span><span class="sxs-lookup"><span data-stu-id="a605d-213">**Value**</span></span>|<span data-ttu-id="a605d-214">型**TimedOut**します。</span><span class="sxs-lookup"><span data-stu-id="a605d-214">Type **TimedOut**.</span></span>|  
    |<span data-ttu-id="a605d-215">**[グループ]**</span><span class="sxs-lookup"><span data-stu-id="a605d-215">**Group**</span></span>|<span data-ttu-id="a605d-216">**Or**</span><span class="sxs-lookup"><span data-stu-id="a605d-216">**Or**</span></span>|  
    |<span data-ttu-id="a605d-217">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="a605d-217">**Property**</span></span>|<span data-ttu-id="a605d-218">選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**します。</span><span class="sxs-lookup"><span data-stu-id="a605d-218">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.</span></span>|  
    |<span data-ttu-id="a605d-219">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="a605d-219">**Operator**</span></span>|<span data-ttu-id="a605d-220">選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="a605d-220">Select **==**.</span></span>|  
    |<span data-ttu-id="a605d-221">**[値]**</span><span class="sxs-lookup"><span data-stu-id="a605d-221">**Value**</span></span>|<span data-ttu-id="a605d-222">型**TransportError**します。</span><span class="sxs-lookup"><span data-stu-id="a605d-222">Type **TransportError**.</span></span>|  
    |<span data-ttu-id="a605d-223">**[グループ]**</span><span class="sxs-lookup"><span data-stu-id="a605d-223">**Group**</span></span>|<span data-ttu-id="a605d-224">**Or**</span><span class="sxs-lookup"><span data-stu-id="a605d-224">**Or**</span></span>|  
    |<span data-ttu-id="a605d-225">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="a605d-225">**Property**</span></span>|<span data-ttu-id="a605d-226">選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**します。</span><span class="sxs-lookup"><span data-stu-id="a605d-226">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.</span></span>|  
    |<span data-ttu-id="a605d-227">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="a605d-227">**Operator**</span></span>|<span data-ttu-id="a605d-228">選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="a605d-228">Select **==**.</span></span>|  
    |<span data-ttu-id="a605d-229">**[値]**</span><span class="sxs-lookup"><span data-stu-id="a605d-229">**Value**</span></span>|<span data-ttu-id="a605d-230">型**DelayedNAK**します。</span><span class="sxs-lookup"><span data-stu-id="a605d-230">Type **DelayedNAK**.</span></span>|  
    |<span data-ttu-id="a605d-231">**[グループ]**</span><span class="sxs-lookup"><span data-stu-id="a605d-231">**Group**</span></span>|<span data-ttu-id="a605d-232">**Or**</span><span class="sxs-lookup"><span data-stu-id="a605d-232">**Or**</span></span>|  
    |<span data-ttu-id="a605d-233">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="a605d-233">**Property**</span></span>|<span data-ttu-id="a605d-234">選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**します。</span><span class="sxs-lookup"><span data-stu-id="a605d-234">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.</span></span>|  
    |<span data-ttu-id="a605d-235">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="a605d-235">**Operator**</span></span>|<span data-ttu-id="a605d-236">選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="a605d-236">Select **==**.</span></span>|  
    |<span data-ttu-id="a605d-237">**[値]**</span><span class="sxs-lookup"><span data-stu-id="a605d-237">**Value**</span></span>|<span data-ttu-id="a605d-238">型**AbortMessage**します。</span><span class="sxs-lookup"><span data-stu-id="a605d-238">Type **AbortMessage**.</span></span>|  

12. <span data-ttu-id="a605d-239">クリックして**適用**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="a605d-239">Click **Apply**, and then click **OK**.</span></span>  

13. <span data-ttu-id="a605d-240">送信ポートを右クリックし、**開始**します。</span><span class="sxs-lookup"><span data-stu-id="a605d-240">Right-click the send port, and then click **Start**.</span></span>  

14. <span data-ttu-id="a605d-241">手順 2. ~ 13 に必要なメッセージの種類ごとの送信ポートを作成する.</span><span class="sxs-lookup"><span data-stu-id="a605d-241">Repeat steps 2 through 13 to create a send port for each message type required.</span></span>