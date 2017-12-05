---
title: "手順 5: ファイル アダプタを使用して、ADT システムに受信確認を配信する送信ポートの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, send ports
- send ports, acknowledgements
- creating, send ports
- acknowledgements, send ports
- send ports, creating
ms.assetid: 565a2adf-fd86-46e3-8035-7e4748aefffc
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6e63590c8cc84a6c6c1a7e957900aa44cdcd61c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-5-create-a-send-port-to-deliver-acknowledgments-to-the-adt-system-using-the-file-adapter"></a><span data-ttu-id="1f4f6-102">手順 5: ファイル アダプタを使用して、ADT システムに受信確認を配信する送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f4f6-102">Step 5: Create a Send Port to Deliver Acknowledgments to the ADT System Using the File Adapter</span></span>
<span data-ttu-id="1f4f6-103">この手順では、ファイル アダプターを使用して受信確認を生成する送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f4f6-103">In this step, you create the send port to generate acknowledgments using the File adapter.</span></span>  
  
### <a name="to-create-the-tutorialsendackadt-send-port"></a><span data-ttu-id="1f4f6-104">Tutorial_sendAck_ADT 送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="1f4f6-104">To create the Tutorial_sendAck_ADT send port</span></span>  
  
1.  <span data-ttu-id="1f4f6-105">使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、作成、 \<*ドライブ*:\>\Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End エンドツー エンド Tutorial\Tutorial_ のアクセラレータsendAck_ADT フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="1f4f6-105">Using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, create the \<*drive*:\>\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_sendAck_ADT folder.</span></span>  
  
2.  <span data-ttu-id="1f4f6-106">BizTalk Server 管理コンソールで、右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="1f4f6-106">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
3.  <span data-ttu-id="1f4f6-107">[送信ポートのプロパティ] ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1f4f6-107">In the Send Port Properties dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="1f4f6-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1f4f6-108">Use this</span></span>|<span data-ttu-id="1f4f6-109">目的</span><span class="sxs-lookup"><span data-stu-id="1f4f6-109">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="1f4f6-110">**名前**</span><span class="sxs-lookup"><span data-stu-id="1f4f6-110">**Name**</span></span>|<span data-ttu-id="1f4f6-111">型**Tutorial_sendAck_ADT**です。</span><span class="sxs-lookup"><span data-stu-id="1f4f6-111">Type **Tutorial_sendAck_ADT**.</span></span>|  
    |<span data-ttu-id="1f4f6-112">**トランスポートの種類**</span><span class="sxs-lookup"><span data-stu-id="1f4f6-112">**Transport type**</span></span>|<span data-ttu-id="1f4f6-113">選択**ファイル**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="1f4f6-113">Select **FILE** from the drop-down list.</span></span>|  
    |<span data-ttu-id="1f4f6-114">**構成**</span><span class="sxs-lookup"><span data-stu-id="1f4f6-114">**Configure**</span></span>|<span data-ttu-id="1f4f6-115">をクリックして**構成**を開くには、 **File トランスポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="1f4f6-115">Click **Configure** to open the **File Transport Properties** dialog box.</span></span>|  
  
4.  <span data-ttu-id="1f4f6-116">ファイル トランスポートのプロパティ ダイアログ ボックスで、次の操作をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="1f4f6-116">In the FILE Transport Properties dialog box, do the following and then click **OK**.</span></span>  
  
    |<span data-ttu-id="1f4f6-117">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1f4f6-117">Use this</span></span>|<span data-ttu-id="1f4f6-118">目的</span><span class="sxs-lookup"><span data-stu-id="1f4f6-118">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="1f4f6-119">**コピー先フォルダー**</span><span class="sxs-lookup"><span data-stu-id="1f4f6-119">**Destination folder**</span></span>|<span data-ttu-id="1f4f6-120">参照 **\<** *ドライブ***:\>\Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End エンドツー エンドのアクセラレータTutorial\Tutorial_sendAck_ADT**です。</span><span class="sxs-lookup"><span data-stu-id="1f4f6-120">Browse to **\<***drive***:\>\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_sendAck_ADT**.</span></span>|  
    |<span data-ttu-id="1f4f6-121">**ファイル名**</span><span class="sxs-lookup"><span data-stu-id="1f4f6-121">**File name**</span></span>|<span data-ttu-id="1f4f6-122">型**%MessageID%.txt** (拡張子 .txt に .xml 拡張子を置き換えます)。</span><span class="sxs-lookup"><span data-stu-id="1f4f6-122">Type **%MessageID%.txt** (replace the .xml extension with the .txt extension).</span></span>|  
  
5.  <span data-ttu-id="1f4f6-123">送信ポートのプロパティ] ダイアログ ボックスの**送信パイプライン**[ **BTAHL72XPipelines.BTAHL72XSendPipeline**です。</span><span class="sxs-lookup"><span data-stu-id="1f4f6-123">In the Send Port Properties dialog box, for **Send pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span></span>  
  
6.  <span data-ttu-id="1f4f6-124">左側のウィンドウでをクリックして**フィルター**、し、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1f4f6-124">In the left pane, click **Filters**, and then do the following:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1f4f6-125">最初のフィルターは、受信確認メッセージをサブスクライブしていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="1f4f6-125">The first filter means that you are subscribing for the acknowledgment message.</span></span> <span data-ttu-id="1f4f6-126">2 番目のフィルターは、パブリッシャー Tutorial_ADTSystem に送信される受信確認をサブスクライブしたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="1f4f6-126">The second filter means that you are subscribing to the acknowledgment that is destined for the publisher Tutorial_ADTSystem.</span></span>  
  
     <span data-ttu-id="1f4f6-127">をクリックして**OK**続行する準備ができたらです。</span><span class="sxs-lookup"><span data-stu-id="1f4f6-127">Click **OK** when you are ready to continue.</span></span>  
  
    |<span data-ttu-id="1f4f6-128">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1f4f6-128">Use this</span></span>|<span data-ttu-id="1f4f6-129">目的</span><span class="sxs-lookup"><span data-stu-id="1f4f6-129">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="1f4f6-130">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="1f4f6-130">**Property**</span></span>|<span data-ttu-id="1f4f6-131">下のフィールドをクリックして**プロパティ**、し、 **BTS です。MessageType**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="1f4f6-131">Click the field under **Property**, and then select **BTS.MessageType** from the drop-down list.</span></span>|  
    |<span data-ttu-id="1f4f6-132">**演算子**</span><span class="sxs-lookup"><span data-stu-id="1f4f6-132">**Operator**</span></span>|<span data-ttu-id="1f4f6-133">選択 **==** ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="1f4f6-133">Select **==** from the drop-down list.</span></span>|  
    |<span data-ttu-id="1f4f6-134">**値**</span><span class="sxs-lookup"><span data-stu-id="1f4f6-134">**Value**</span></span>|<span data-ttu-id="1f4f6-135">型**http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF**です。</span><span class="sxs-lookup"><span data-stu-id="1f4f6-135">Type **http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF**.</span></span>|  
    |<span data-ttu-id="1f4f6-136">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="1f4f6-136">**Group By**</span></span>|<span data-ttu-id="1f4f6-137">選択**または**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="1f4f6-137">Select **OR** from the drop-down list.</span></span>|  
    |<span data-ttu-id="1f4f6-138">**プロパティ (2 番目の行)**</span><span class="sxs-lookup"><span data-stu-id="1f4f6-138">**Property (second line)**</span></span>|<span data-ttu-id="1f4f6-139">下のフィールドをクリックして**プロパティ**、し、 **BTS です。MessageType**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="1f4f6-139">Click the field under **Property**, and then select **BTS.MessageType** from the drop-down list.</span></span>|  
    |<span data-ttu-id="1f4f6-140">**演算子**</span><span class="sxs-lookup"><span data-stu-id="1f4f6-140">**Operator**</span></span>|<span data-ttu-id="1f4f6-141">選択 **==** ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="1f4f6-141">Select **==** from the drop-down list.</span></span>|  
    |<span data-ttu-id="1f4f6-142">**値**</span><span class="sxs-lookup"><span data-stu-id="1f4f6-142">**Value**</span></span>|<span data-ttu-id="1f4f6-143">型**http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF です。**</span><span class="sxs-lookup"><span data-stu-id="1f4f6-143">Type **http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF.**</span></span>|  
    |<span data-ttu-id="1f4f6-144">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="1f4f6-144">**Group By**</span></span>|<span data-ttu-id="1f4f6-145">選択**AND**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="1f4f6-145">Select **AND** from the drop-down list.</span></span>|  
    |<span data-ttu-id="1f4f6-146">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="1f4f6-146">**Property**</span></span>|<span data-ttu-id="1f4f6-147">最初のプロパティでは、下の空のボックスをクリックし、 **BTAHL7Schemas.MSH5_1**です。</span><span class="sxs-lookup"><span data-stu-id="1f4f6-147">Under the first property, click the blank box, and then select **BTAHL7Schemas.MSH5_1**.</span></span>|  
    |<span data-ttu-id="1f4f6-148">**演算子**</span><span class="sxs-lookup"><span data-stu-id="1f4f6-148">**Operator**</span></span>|<span data-ttu-id="1f4f6-149">選択 **==** ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="1f4f6-149">Select **==** from the drop-down list.</span></span>|  
    |<span data-ttu-id="1f4f6-150">**値**</span><span class="sxs-lookup"><span data-stu-id="1f4f6-150">**Value**</span></span>|<span data-ttu-id="1f4f6-151">型**Tutorial_ADTSystem**です。</span><span class="sxs-lookup"><span data-stu-id="1f4f6-151">Type **Tutorial_ADTSystem**.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="1f4f6-152">BTAHL7 がファイルの格納場所に、受信確認を削除、送信ポート Tutorial_sendAck_ADT の\<*ドライブ*\>: プログラム FilesMicrosoft BizTalk <version> HL7SDKEnd エンドツー エンドのアクセラレータTutorialTutorial_sendAck_ADT です。</span><span class="sxs-lookup"><span data-stu-id="1f4f6-152">For the send port Tutorial_sendAck_ADT, BTAHL7 drops the acknowledgments at the file drop location \<*drive*\>:Program FilesMicrosoft BizTalk <version> Accelerator for HL7SDKEnd-to-End TutorialTutorial_sendAck_ADT.</span></span>  
  
7.  <span data-ttu-id="1f4f6-153">をクリックして**適用**、クリックして**[ok] です。**</span><span class="sxs-lookup"><span data-stu-id="1f4f6-153">Click **Apply**, and then click **OK.**</span></span>  
  
8.  <span data-ttu-id="1f4f6-154">管理コンソールで、をクリックして**送信ポート**を右クリックして**Tutorial_sendAck_ADT**、クリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="1f4f6-154">In the Administration Console, click **Send Ports**, right-click **Tutorial_sendAck_ADT**, and then click **Start**.</span></span>  
  
 <span data-ttu-id="1f4f6-155">進みます[手順 6: ADT を配信する送信ポートを作成 ^ A03 メッセージをファイル アダプターを使用して RX システム](../../adapters-and-accelerators/accelerator-hl7/step-6-create-send-port-to-deliver-adt^a03-message-to-rx-system-using-file.md)です。</span><span class="sxs-lookup"><span data-stu-id="1f4f6-155">Proceed to [Step 6: Create a Send Port to Deliver the ADT^A03 Message to the RX System Using the File Adapter](../../adapters-and-accelerators/accelerator-hl7/step-6-create-send-port-to-deliver-adt^a03-message-to-rx-system-using-file.md).</span></span>