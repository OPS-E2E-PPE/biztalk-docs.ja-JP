---
title: "手順 6: ADT を配信する送信ポートを作成する ^ A03 メッセージをファイル アダプターを使用して RX システム |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, send ports
- creating, send ports
- send ports, creating
ms.assetid: 66c4b524-c8ff-43b5-9c44-6d7bc759ae2c
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c25a348fb739f4558f1507eda0d46d209cd44c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-6-create-a-send-port-to-deliver-the-adta03-message-to-the-rx-system-using-the-file-adapter"></a><span data-ttu-id="adec8-102">手順 6: ADT を配信する送信ポートを作成する ^ A03 メッセージをファイル アダプターを使用して RX システム</span><span class="sxs-lookup"><span data-stu-id="adec8-102">Step 6: Create a Send Port to Deliver the ADT^A03 Message to the RX System Using the File Adapter</span></span>
<span data-ttu-id="adec8-103">この手順で、送信ポートの薬局システム (RX)、ファイル アダプターを使用してを作成します。</span><span class="sxs-lookup"><span data-stu-id="adec8-103">In this step, you create the send port for the Pharmacy System (RX) using the File adapter.</span></span>  
  
### <a name="to-create-the-tutorialsendmsgrx-send-port"></a><span data-ttu-id="adec8-104">Tutorial_sendMsg_RX 送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="adec8-104">To create the Tutorial_sendMsg_RX send port</span></span>  
  
1.  <span data-ttu-id="adec8-105">[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]管理コンソールを右クリックして**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="adec8-105">In the [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="adec8-106">**送信ポートのプロパティ** ダイアログ ボックスを次の操作を実行してクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="adec8-106">In the **Send Port Properties** dialog box, do the following actions and then click **OK**.</span></span>  
  
    |<span data-ttu-id="adec8-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="adec8-107">Use this</span></span>|<span data-ttu-id="adec8-108">目的</span><span class="sxs-lookup"><span data-stu-id="adec8-108">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="adec8-109">**名前**</span><span class="sxs-lookup"><span data-stu-id="adec8-109">**Name**</span></span>|<span data-ttu-id="adec8-110">型**Tutorial_sendMsg_RX**です。</span><span class="sxs-lookup"><span data-stu-id="adec8-110">Type **Tutorial_sendMsg_RX**.</span></span>|  
    |<span data-ttu-id="adec8-111">**トランスポートの種類**</span><span class="sxs-lookup"><span data-stu-id="adec8-111">**Transport type**</span></span>|<span data-ttu-id="adec8-112">選択**ファイル**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="adec8-112">Select **FILE** from the drop-down list.</span></span>|  
    |<span data-ttu-id="adec8-113">**構成**</span><span class="sxs-lookup"><span data-stu-id="adec8-113">**Configure**</span></span>|<span data-ttu-id="adec8-114">をクリックして**構成**を開くには、 **File トランスポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="adec8-114">Click **Configure** to open the **File Transport Properties** dialog box.</span></span>|  
  
3.  <span data-ttu-id="adec8-115">ファイル トランスポートのプロパティ ダイアログ ボックスで、次の操作を行うし、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="adec8-115">In the FILE Transport Properties dialog box, do the following actions and then click **OK**.</span></span>  
  
    |<span data-ttu-id="adec8-116">プロパティ</span><span class="sxs-lookup"><span data-stu-id="adec8-116">Use this</span></span>|<span data-ttu-id="adec8-117">目的</span><span class="sxs-lookup"><span data-stu-id="adec8-117">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="adec8-118">**コピー先フォルダー**</span><span class="sxs-lookup"><span data-stu-id="adec8-118">**Destination folder**</span></span>|<span data-ttu-id="adec8-119">参照 **\<** *ドライブ***: > \Program Files\Microsoft BizTalk\<バージョン > Accelerator for HL7\SDK\End エンドツー エンド Tutorial\Tutorial_sendMsg_RX**.</span><span class="sxs-lookup"><span data-stu-id="adec8-119">Browse to **\<***drive***:>\Program Files\Microsoft BizTalk \<version> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_sendMsg_RX**.</span></span>|  
    |<span data-ttu-id="adec8-120">**ファイル名**</span><span class="sxs-lookup"><span data-stu-id="adec8-120">**File name**</span></span>|<span data-ttu-id="adec8-121">型**%MessageID%.txt** (拡張子 .txt に .xml 拡張子を置き換えます)。</span><span class="sxs-lookup"><span data-stu-id="adec8-121">Type **%MessageID%.txt** (replace the .xml extension with the .txt extension).</span></span>|  
  
4.  <span data-ttu-id="adec8-122">**送信ポートのプロパティ**] ダイアログ ボックスの**送信パイプライン**[ **BTAHL72XPipelines.BTAHL72XSendPipeline**です。</span><span class="sxs-lookup"><span data-stu-id="adec8-122">In the **Send Port Properties** dialog box, for **Send Pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span></span>  
  
5.  <span data-ttu-id="adec8-123">左のペインで選択**フィルター**、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="adec8-123">In the left pane, select **Filters**, and then do the following actions.</span></span> <span data-ttu-id="adec8-124">続行するには、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="adec8-124">Click **OK** to continue.</span></span>  
  
    |<span data-ttu-id="adec8-125">プロパティ</span><span class="sxs-lookup"><span data-stu-id="adec8-125">Use this</span></span>|<span data-ttu-id="adec8-126">目的</span><span class="sxs-lookup"><span data-stu-id="adec8-126">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="adec8-127">**プロパティ**(1 行目)</span><span class="sxs-lookup"><span data-stu-id="adec8-127">**Property** (first line)</span></span>|<span data-ttu-id="adec8-128">選択**BTS です。MessageType**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="adec8-128">Select **BTS.MessageType** from the drop-down list.</span></span>|  
    |<span data-ttu-id="adec8-129">**演算子**</span><span class="sxs-lookup"><span data-stu-id="adec8-129">**Operator**</span></span>|<span data-ttu-id="adec8-130">選択**! =**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="adec8-130">Select **!=** from the drop-down list.</span></span>|  
    |<span data-ttu-id="adec8-131">**値**</span><span class="sxs-lookup"><span data-stu-id="adec8-131">**Value**</span></span>|<span data-ttu-id="adec8-132">型**http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF**です。</span><span class="sxs-lookup"><span data-stu-id="adec8-132">Type **http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF**.</span></span>|  
    |<span data-ttu-id="adec8-133">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="adec8-133">**Group By**</span></span>|<span data-ttu-id="adec8-134">選択**または**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="adec8-134">Select **OR** from the drop-down list.</span></span>|  
    |<span data-ttu-id="adec8-135">**プロパティ**(2 番目の行)</span><span class="sxs-lookup"><span data-stu-id="adec8-135">**Property** (second line)</span></span>|<span data-ttu-id="adec8-136">下のフィールドをクリックして**プロパティ**、し、 **BTS です。MessageType**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="adec8-136">Click the field under **Property**, and then select **BTS.MessageType** from the drop-down list.</span></span>|  
    |<span data-ttu-id="adec8-137">**演算子**</span><span class="sxs-lookup"><span data-stu-id="adec8-137">**Operator**</span></span>|<span data-ttu-id="adec8-138">選択**! =**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="adec8-138">Select **!=** from the drop-down list.</span></span>|  
    |<span data-ttu-id="adec8-139">**値**</span><span class="sxs-lookup"><span data-stu-id="adec8-139">**Value**</span></span>|<span data-ttu-id="adec8-140">型**http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF です。**</span><span class="sxs-lookup"><span data-stu-id="adec8-140">Type **http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF.**</span></span>|  
    |<span data-ttu-id="adec8-141">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="adec8-141">**Group By**</span></span>|<span data-ttu-id="adec8-142">選択**AND**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="adec8-142">Select **AND** from the drop-down list.</span></span>|  
    |<span data-ttu-id="adec8-143">**プロパティ**(3 行目)</span><span class="sxs-lookup"><span data-stu-id="adec8-143">**Property** (third line)</span></span>|<span data-ttu-id="adec8-144">選択**BTAHL7Schemas.MSH3_1**です。</span><span class="sxs-lookup"><span data-stu-id="adec8-144">Select **BTAHL7Schemas.MSH3_1**.</span></span>|  
    |<span data-ttu-id="adec8-145">**演算子**</span><span class="sxs-lookup"><span data-stu-id="adec8-145">**Operator**</span></span>|<span data-ttu-id="adec8-146">選択 **==** ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="adec8-146">Select **==** from the drop-down list.</span></span>|  
    |<span data-ttu-id="adec8-147">**値**</span><span class="sxs-lookup"><span data-stu-id="adec8-147">**Value**</span></span>|<span data-ttu-id="adec8-148">型**Tutorial_ADTSystem**です。</span><span class="sxs-lookup"><span data-stu-id="adec8-148">Type **Tutorial_ADTSystem**.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="adec8-149">最初のフィルターは、病院情報システム (HIS) は、メッセージの受信確認にないにサブスクライブしていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="adec8-149">The first filter means that the Hospital Information System (HIS) is subscribing to a message, not an acknowledgment.</span></span> <span data-ttu-id="adec8-150">2 番目のフィルターでは、ソースは、受付放電と転送 (ADT) のシステム メッセージに、彼はサブスクライブしていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="adec8-150">The second filter means that HIS is subscribing to messages whose source is the Admissions Discharge and Transfer (ADT) System.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="adec8-151">ファイルの格納場所にメッセージをドロップする BTAHL7 \<*ドライブ*>: プログラム FilesMicrosoft BizTalk <version> HL7SDKEnd エンドツー エンド TutorialTutorial_sendMsg_RX のアクセラレータです。</span><span class="sxs-lookup"><span data-stu-id="adec8-151">BTAHL7 drops the message at the file drop location \<*drive*>:Program FilesMicrosoft BizTalk <version> Accelerator for HL7SDKEnd-to-End TutorialTutorial_sendMsg_RX.</span></span>  
  
6.  <span data-ttu-id="adec8-152">をクリックして**適用**、クリックして**[ok] です。**</span><span class="sxs-lookup"><span data-stu-id="adec8-152">Click **Apply**, and then click **OK.**</span></span>  
  
7.  <span data-ttu-id="adec8-153">管理コンソールで、をクリックして**送信ポート**を右クリックして**Tutorial_sendMsg_RX**、クリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="adec8-153">In the Administration Console, click **Send Ports**, right-click **Tutorial_sendMsg_RX**, and then click **Start**.</span></span>  
  
 <span data-ttu-id="adec8-154">進みます[手順 7: ADT を配信する送信ポートを作成 ^ MLLP アダプターを使用して自分に A03 メッセージ](../../adapters-and-accelerators/accelerator-hl7/step-7-create-send-port-to-deliver-adt^a03-message-to-his-using-mllp-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="adec8-154">Proceed to [Step 7: Create a Send Port to Deliver the ADT^A03 Message to HIS Using the MLLP Adapter](../../adapters-and-accelerators/accelerator-hl7/step-7-create-send-port-to-deliver-adt^a03-message-to-his-using-mllp-adapter.md).</span></span>