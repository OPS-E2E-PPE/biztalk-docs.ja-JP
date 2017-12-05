---
title: "手順 5: は、メッセージ バッチの送信ポートを作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5db815df-5b76-4ba4-99ab-c7766b0c301a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5749166c8a9b34d5e5a04849c4179ac4427201c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="step-5-create-the-send-port-for-the-message-batch"></a><span data-ttu-id="ed55c-102">手順 5: メッセージのバッチの送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="ed55c-102">Step 5: Create the Send Port for the Message Batch</span></span>
<span data-ttu-id="ed55c-103">この手順では、送信先パーティを作成するメッセージのバッチを配信する送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="ed55c-103">In this step, you create a send port to deliver the message batch that you create to the destination party.</span></span> <span data-ttu-id="ed55c-104">これは、ファイル アダプターの種類に静的な一方向のポートです。</span><span class="sxs-lookup"><span data-stu-id="ed55c-104">This is a static one-way port with a FILE adapter type.</span></span> <span data-ttu-id="ed55c-105">ここで、変換先 (\Tutorial_BatchMsgDrop) のファイルのフォルダーを指定する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージ バッチ ファイルが削除されます。</span><span class="sxs-lookup"><span data-stu-id="ed55c-105">You designate a file folder for the destination (\Tutorial_BatchMsgDrop) where [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] will drop the message batch file.</span></span> <span data-ttu-id="ed55c-106">ポートで送信するメッセージのバッチの種類を示すポートのフィルターを定義するとします。</span><span class="sxs-lookup"><span data-stu-id="ed55c-106">You define a filter for the port indicating what type of message batches the ports will send.</span></span> <span data-ttu-id="ed55c-107">フィルターは、Tutorial_BatchDest と OutboundBatch のメッセージの種類の変換先を指定します。</span><span class="sxs-lookup"><span data-stu-id="ed55c-107">The filter specifies the destination of Tutorial_BatchDest and the message type of OutboundBatch.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ed55c-108">チュートリアルの第 2 部で使用する送信ポートを停止することによって、結果を簡略化できますチュートリアルのこの部分を実行する場合: **Tutorial_BTAHL7Drop**ポートを送信します。</span><span class="sxs-lookup"><span data-stu-id="ed55c-108">When running this part of the tutorial, you can simplify the results by stopping the send port used in Part 2 of the tutorial: the **Tutorial_BTAHL7Drop** send port.</span></span>  
  
### <a name="to-create-the-send-port-for-the-message-batch"></a><span data-ttu-id="ed55c-109">メッセージ バッチの送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="ed55c-109">To create the send port for the message batch</span></span>  
  
1.  <span data-ttu-id="ed55c-110">BizTalk Server 管理コンソールで、右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="ed55c-110">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="ed55c-111">[送信ポートのプロパティ] ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ed55c-111">In the Send Port Properties dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="ed55c-112">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ed55c-112">Use this</span></span>|<span data-ttu-id="ed55c-113">目的</span><span class="sxs-lookup"><span data-stu-id="ed55c-113">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="ed55c-114">**名前**</span><span class="sxs-lookup"><span data-stu-id="ed55c-114">**Name**</span></span>|<span data-ttu-id="ed55c-115">型**Tutorial_BatchDest**です。</span><span class="sxs-lookup"><span data-stu-id="ed55c-115">Type **Tutorial_BatchDest**.</span></span>|  
    |<span data-ttu-id="ed55c-116">**型**</span><span class="sxs-lookup"><span data-stu-id="ed55c-116">**Type**</span></span>|<span data-ttu-id="ed55c-117">選択**ファイル**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="ed55c-117">Select **FILE** from the drop-down list.</span></span>|  
    |<span data-ttu-id="ed55c-118">**構成**</span><span class="sxs-lookup"><span data-stu-id="ed55c-118">**Configure**</span></span>|<span data-ttu-id="ed55c-119">をクリックして**構成**FILE トランスポートのプロパティ ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="ed55c-119">Click **Configure** to open the FILE Transport Properties dialog box.</span></span>|  
  
3.  <span data-ttu-id="ed55c-120">**FILE トランスポートのプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="ed55c-120">In the **FILE Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="ed55c-121">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ed55c-121">Use this</span></span>|<span data-ttu-id="ed55c-122">目的</span><span class="sxs-lookup"><span data-stu-id="ed55c-122">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="ed55c-123">**コピー先フォルダー**</span><span class="sxs-lookup"><span data-stu-id="ed55c-123">**Destination folder**</span></span>|<span data-ttu-id="ed55c-124">参照  **\<*ドライブ*:\>\Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End エンドツー エンド Tutorial\Tutorial_ のアクセラレータ* * BatchMsgDrop。</span><span class="sxs-lookup"><span data-stu-id="ed55c-124">Browse to **\<*drive*:\>\Program Files\Microsoft  BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BatchMsgDrop**.</span></span> <span data-ttu-id="ed55c-125">これは、ファイル システムまたはパブリックの共有の場所にパス[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージ バッチを含んでいるファイルを記述します。</span><span class="sxs-lookup"><span data-stu-id="ed55c-125">This is the path to the location on the file system or public share to which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] will write the file containing the message batch.</span></span>|  
    |<span data-ttu-id="ed55c-126">**ファイル名**</span><span class="sxs-lookup"><span data-stu-id="ed55c-126">**File name**</span></span>|<span data-ttu-id="ed55c-127">型**%MessageID%.txt** (拡張子 .txt に .xml 拡張子を置き換えます)。</span><span class="sxs-lookup"><span data-stu-id="ed55c-127">Type **%MessageID%.txt** (replace the .xml extension with the .txt extension).</span></span>|  
    |<span data-ttu-id="ed55c-128">**[コピー モード]**</span><span class="sxs-lookup"><span data-stu-id="ed55c-128">**Copy mode**</span></span>|<span data-ttu-id="ed55c-129">選択**新規作成**です。</span><span class="sxs-lookup"><span data-stu-id="ed55c-129">Select **Create New**.</span></span>|  
  
4.  <span data-ttu-id="ed55c-130">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed55c-130">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="ed55c-131">送信ポートのプロパティ] ダイアログ ボックスの**送信パイプライン**[ **BTAHL72XPipelines.BTAHL72XSendPipeline**です。</span><span class="sxs-lookup"><span data-stu-id="ed55c-131">In the Send Port Properties dialog box, for **Send pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span></span>  
  
6.  <span data-ttu-id="ed55c-132">コンソール ツリーでクリックして**フィルター**、し、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ed55c-132">In the console tree, click **Filters**, and then do the following:</span></span>  
  
    |<span data-ttu-id="ed55c-133">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ed55c-133">Use this</span></span>|<span data-ttu-id="ed55c-134">目的</span><span class="sxs-lookup"><span data-stu-id="ed55c-134">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="ed55c-135">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="ed55c-135">**Property**</span></span>|<span data-ttu-id="ed55c-136">下のフィールドをクリックして**プロパティ**、し、 **Microsoft.Solutions.BTAHL7.BatchOrchestration.Party**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="ed55c-136">Click the field under **Property**, and then select **Microsoft.Solutions.BTAHL7.BatchOrchestration.Party** from the drop-down list.</span></span>|  
    |<span data-ttu-id="ed55c-137">**演算子**</span><span class="sxs-lookup"><span data-stu-id="ed55c-137">**Operator**</span></span>|<span data-ttu-id="ed55c-138">ままにして **==** 演算子とします。</span><span class="sxs-lookup"><span data-stu-id="ed55c-138">Leave **==** as the operator.</span></span>|  
    |<span data-ttu-id="ed55c-139">**値**</span><span class="sxs-lookup"><span data-stu-id="ed55c-139">**Value**</span></span>|<span data-ttu-id="ed55c-140">型**Tutorial_BatchDest**です。</span><span class="sxs-lookup"><span data-stu-id="ed55c-140">Type **Tutorial_BatchDest**.</span></span>|  
    |<span data-ttu-id="ed55c-141">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="ed55c-141">**Group By**</span></span>|<span data-ttu-id="ed55c-142">選択**と**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="ed55c-142">Select **And** from the drop-down list.</span></span>|  
    |<span data-ttu-id="ed55c-143">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="ed55c-143">**Property**</span></span>|<span data-ttu-id="ed55c-144">選択**BTAHL7Schemas.BTAHL7MessageType**です。</span><span class="sxs-lookup"><span data-stu-id="ed55c-144">Select **BTAHL7Schemas.BTAHL7MessageType**.</span></span>|  
    |<span data-ttu-id="ed55c-145">**演算子**</span><span class="sxs-lookup"><span data-stu-id="ed55c-145">**Operator**</span></span>|<span data-ttu-id="ed55c-146">ままにして **==** 演算子とします。</span><span class="sxs-lookup"><span data-stu-id="ed55c-146">Leave **==** as the operator.</span></span>|  
    |<span data-ttu-id="ed55c-147">**値**</span><span class="sxs-lookup"><span data-stu-id="ed55c-147">**Value**</span></span>|<span data-ttu-id="ed55c-148">型**OutboundBatch**です。</span><span class="sxs-lookup"><span data-stu-id="ed55c-148">Type **OutboundBatch**.</span></span>|  
  
7.  <span data-ttu-id="ed55c-149">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ed55c-149">Press **Enter**.</span></span> <span data-ttu-id="ed55c-150">クリックしてダイアログ ボックスの下部にあるペインで、フィルター式の入力が正しいことを確認してください**OK**です。</span><span class="sxs-lookup"><span data-stu-id="ed55c-150">In the pane at the bottom of the dialog box, verify that you entered the filter expression correctly, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="ed55c-151">BizTalk 管理コンソールで、次のように選択します。**送信ポート**、を右クリック**Tutorial_BatchDest**、順にクリック**開始**です。</span><span class="sxs-lookup"><span data-stu-id="ed55c-151">In the BizTalk Administration Console, select **Send Ports**, right-click **Tutorial_BatchDest**, and then click **Start**.</span></span>  
  
### <a name="to-associate-the-send-port-with-the-destination-party"></a><span data-ttu-id="ed55c-152">送信先パーティに送信ポートを関連付ける</span><span class="sxs-lookup"><span data-stu-id="ed55c-152">To associate the send port with the destination party</span></span>  
  
1.  <span data-ttu-id="ed55c-153">BizTalk Server 管理コンソールで、展開**パーティ**をクリックして**Tutorial_BatchDest**、し、右クリック**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="ed55c-153">In the BizTalk Server Administration Console, expand **Parties**, click **Tutorial_BatchDest**, and then right-click **Properties**.</span></span>  
  
2.  <span data-ttu-id="ed55c-154">[パーティのプロパティ] ダイアログ ボックスで、**送信ポート**コンソール ツリーでします。</span><span class="sxs-lookup"><span data-stu-id="ed55c-154">In the Party Properties dialog box, click  **Send Ports** in the console tree.</span></span>  <span data-ttu-id="ed55c-155">選択**Tutorial_BatchDest**クリックしてドロップダウン リストから**OK**です。</span><span class="sxs-lookup"><span data-stu-id="ed55c-155">Select **Tutorial_BatchDest** from the drop-down list, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ed55c-156">同時実行制御違反が発生した場合中に、 **Tutorial_DestBatch**パーティの更新中で、**[OK]** ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="ed55c-156">If a concurrency violation occurs while the **Tutorial_DestBatch** party was being updated, click **OK** and close the dialog box.</span></span> <span data-ttu-id="ed55c-157">管理コンソールで、右クリック**BizTalk グループ**、 をクリックして**更新**、手順 1. と 2. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="ed55c-157">In the Administration Console, right-click **BizTalk Group**, click **Refresh**, and then repeat steps 1 and 2.</span></span>  
  
 <span data-ttu-id="ed55c-158">進みます[手順 6: 受信確認のバッチの送信ポートを作成する](../../adapters-and-accelerators/accelerator-hl7/step-6-create-the-send-port-for-the-acknowledgment-batch.md)です。</span><span class="sxs-lookup"><span data-stu-id="ed55c-158">Proceed to [Step 6: Create the Send Port for the Acknowledgment Batch](../../adapters-and-accelerators/accelerator-hl7/step-6-create-the-send-port-for-the-acknowledgment-batch.md).</span></span>