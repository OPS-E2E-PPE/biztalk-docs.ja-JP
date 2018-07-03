---
title: '手順 6: ADT を配信する送信ポートを作成する ^ A03 メッセージをファイル アダプターを使用して RX System |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, send ports
- creating, send ports
- send ports, creating
ms.assetid: 66c4b524-c8ff-43b5-9c44-6d7bc759ae2c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 95a9200d4c03f11f2feca89042bfb57ba36de345
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004379"
---
# <a name="step-6-create-a-send-port-to-deliver-the-adta03-message-to-the-rx-system-using-the-file-adapter"></a><span data-ttu-id="0c671-102">手順 6: ADT を配信する送信ポートを作成する ^ A03 メッセージをファイル アダプターを使用して RX System</span><span class="sxs-lookup"><span data-stu-id="0c671-102">Step 6: Create a Send Port to Deliver the ADT^A03 Message to the RX System Using the File Adapter</span></span>
<span data-ttu-id="0c671-103">この手順で、送信ポートの薬剤システム (RX)、ファイル アダプターを使用してを作成します。</span><span class="sxs-lookup"><span data-stu-id="0c671-103">In this step, you create the send port for the Pharmacy System (RX) using the File adapter.</span></span>  

### <a name="to-create-the-tutorialsendmsgrx-send-port"></a><span data-ttu-id="0c671-104">Tutorial_sendMsg_RX 送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="0c671-104">To create the Tutorial_sendMsg_RX send port</span></span>  

1. <span data-ttu-id="0c671-105">右クリックし、BizTalk Server 管理コンソールで**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート**。</span><span class="sxs-lookup"><span data-stu-id="0c671-105">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  

2. <span data-ttu-id="0c671-106">**送信ポートのプロパティ** ダイアログ ボックスで、次の操作を実行し、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="0c671-106">In the **Send Port Properties** dialog box, do the following actions and then click **OK**.</span></span>  


   |      <span data-ttu-id="0c671-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0c671-107">Use this</span></span>      |                                <span data-ttu-id="0c671-108">目的</span><span class="sxs-lookup"><span data-stu-id="0c671-108">To do this</span></span>                                 |
   |--------------------|---------------------------------------------------------------------------|
   |      <span data-ttu-id="0c671-109">**名前**</span><span class="sxs-lookup"><span data-stu-id="0c671-109">**Name**</span></span>      |                       <span data-ttu-id="0c671-110">型**Tutorial_sendMsg_RX**します。</span><span class="sxs-lookup"><span data-stu-id="0c671-110">Type **Tutorial_sendMsg_RX**.</span></span>                       |
   | <span data-ttu-id="0c671-111">**トランスポートの種類**</span><span class="sxs-lookup"><span data-stu-id="0c671-111">**Transport type**</span></span> |                 <span data-ttu-id="0c671-112">選択**ファイル**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="0c671-112">Select **FILE** from the drop-down list.</span></span>                  |
   |   <span data-ttu-id="0c671-113">**構成**</span><span class="sxs-lookup"><span data-stu-id="0c671-113">**Configure**</span></span>    | <span data-ttu-id="0c671-114">クリックして**構成**を開く、 **File トランスポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="0c671-114">Click **Configure** to open the **File Transport Properties** dialog box.</span></span> |


3. <span data-ttu-id="0c671-115">ファイル トランスポートのプロパティ ダイアログ ボックスで、次の操作を実行し、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="0c671-115">In the FILE Transport Properties dialog box, do the following actions and then click **OK**.</span></span>  


   |        <span data-ttu-id="0c671-116">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0c671-116">Use this</span></span>        |                                                                     <span data-ttu-id="0c671-117">目的</span><span class="sxs-lookup"><span data-stu-id="0c671-117">To do this</span></span>                                                                     |
   |------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="0c671-118">**コピー先フォルダー**</span><span class="sxs-lookup"><span data-stu-id="0c671-118">**Destination folder**</span></span> | <span data-ttu-id="0c671-119">参照する**\<**<em>ドライブ</em>**:\>\Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End ツー エンドのアクセラレータTutorial\Tutorial_sendMsg_RX**します。</span><span class="sxs-lookup"><span data-stu-id="0c671-119">Browse to **\<**<em>drive</em>**:\>\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_sendMsg_RX**.</span></span> |
   |     <span data-ttu-id="0c671-120">**[ファイル名]**</span><span class="sxs-lookup"><span data-stu-id="0c671-120">**File name**</span></span>      |                                   <span data-ttu-id="0c671-121">型 **%MessageID%.txt** (.txt 拡張子 .xml 拡張子を置き換えます)。</span><span class="sxs-lookup"><span data-stu-id="0c671-121">Type **%MessageID%.txt** (replace the .xml extension with the .txt extension).</span></span>                                   |


4. <span data-ttu-id="0c671-122">**送信ポートのプロパティ** ダイアログ ボックスの**送信パイプライン**を選択します**BTAHL72XPipelines.BTAHL72XSendPipeline**します。</span><span class="sxs-lookup"><span data-stu-id="0c671-122">In the **Send Port Properties** dialog box, for **Send Pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span></span>  

5. <span data-ttu-id="0c671-123">左側のウィンドウで次のように選択します。**フィルター**、し、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="0c671-123">In the left pane, select **Filters**, and then do the following actions.</span></span> <span data-ttu-id="0c671-124">**[OK]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="0c671-124">Click **OK** to continue.</span></span>  


   |          <span data-ttu-id="0c671-125">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0c671-125">Use this</span></span>          |                                            <span data-ttu-id="0c671-126">目的</span><span class="sxs-lookup"><span data-stu-id="0c671-126">To do this</span></span>                                            |
   |----------------------------|--------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="0c671-127">**プロパティ**(1 行目)</span><span class="sxs-lookup"><span data-stu-id="0c671-127">**Property** (first line)</span></span>  |                       <span data-ttu-id="0c671-128">選択**BTS します。MessageType**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="0c671-128">Select **BTS.MessageType** from the drop-down list.</span></span>                        |
   |        <span data-ttu-id="0c671-129">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="0c671-129">**Operator**</span></span>        |                              <span data-ttu-id="0c671-130">選択 **! =** ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="0c671-130">Select **!=** from the drop-down list.</span></span>                              |
   |         <span data-ttu-id="0c671-131">**[値]**</span><span class="sxs-lookup"><span data-stu-id="0c671-131">**Value**</span></span>          |                <span data-ttu-id="0c671-132">型 **<http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF>** します。</span><span class="sxs-lookup"><span data-stu-id="0c671-132">Type **<http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF>**.</span></span>                 |
   |        <span data-ttu-id="0c671-133">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="0c671-133">**Group By**</span></span>        |                              <span data-ttu-id="0c671-134">選択**または**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="0c671-134">Select **OR** from the drop-down list.</span></span>                              |
   | <span data-ttu-id="0c671-135">**プロパティ**(2 行目)</span><span class="sxs-lookup"><span data-stu-id="0c671-135">**Property** (second line)</span></span> | <span data-ttu-id="0c671-136">下のフィールドをクリックします。**プロパティ**、し、 **BTS します。MessageType**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="0c671-136">Click the field under **Property**, and then select **BTS.MessageType** from the drop-down list.</span></span> |
   |        <span data-ttu-id="0c671-137">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="0c671-137">**Operator**</span></span>        |                              <span data-ttu-id="0c671-138">選択 **! =** ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="0c671-138">Select **!=** from the drop-down list.</span></span>                              |
   |         <span data-ttu-id="0c671-139">**[値]**</span><span class="sxs-lookup"><span data-stu-id="0c671-139">**Value**</span></span>          |                <span data-ttu-id="0c671-140">型**<http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF>します。**</span><span class="sxs-lookup"><span data-stu-id="0c671-140">Type **<http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF>.**</span></span>                 |
   |        <span data-ttu-id="0c671-141">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="0c671-141">**Group By**</span></span>        |                             <span data-ttu-id="0c671-142">選択**AND**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="0c671-142">Select **AND** from the drop-down list.</span></span>                              |
   | <span data-ttu-id="0c671-143">**プロパティ**(3 行目)</span><span class="sxs-lookup"><span data-stu-id="0c671-143">**Property** (third line)</span></span>  |                                 <span data-ttu-id="0c671-144">選択**BTAHL7Schemas.MSH3_1**します。</span><span class="sxs-lookup"><span data-stu-id="0c671-144">Select **BTAHL7Schemas.MSH3_1**.</span></span>                                 |
   |        <span data-ttu-id="0c671-145">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="0c671-145">**Operator**</span></span>        |                              <span data-ttu-id="0c671-146">選択**==** ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="0c671-146">Select **==** from the drop-down list.</span></span>                              |
   |         <span data-ttu-id="0c671-147">**[値]**</span><span class="sxs-lookup"><span data-stu-id="0c671-147">**Value**</span></span>          |                                   <span data-ttu-id="0c671-148">型**Tutorial_ADTSystem**します。</span><span class="sxs-lookup"><span data-stu-id="0c671-148">Type **Tutorial_ADTSystem**.</span></span>                                   |

   > [!NOTE]
   >  <span data-ttu-id="0c671-149">最初のフィルターは、病院情報システム (HIS) が受信確認にいないメッセージにサブスクライブすることを意味します。</span><span class="sxs-lookup"><span data-stu-id="0c671-149">The first filter means that the Hospital Information System (HIS) is subscribing to a message, not an acknowledgment.</span></span> <span data-ttu-id="0c671-150">2 番目のフィルターは、ソースが入学放電と転送 (ADT) システムは、メッセージのサブスクライブ彼はことを意味します。</span><span class="sxs-lookup"><span data-stu-id="0c671-150">The second filter means that HIS is subscribing to messages whose source is the Admissions Discharge and Transfer (ADT) System.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="0c671-151">BTAHL7 ファイルの格納場所でメッセージをドロップする\<*ドライブ*\>: Program FilesMicrosoft BizTalk <version> HL7SDKEnd ツー エンド TutorialTutorial_sendMsg_RX のアクセラレータです。</span><span class="sxs-lookup"><span data-stu-id="0c671-151">BTAHL7 drops the message at the file drop location \<*drive*\>:Program FilesMicrosoft BizTalk <version> Accelerator for HL7SDKEnd-to-End TutorialTutorial_sendMsg_RX.</span></span>  

6. <span data-ttu-id="0c671-152">クリックして**適用**、順にクリックします**ok をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="0c671-152">Click **Apply**, and then click **OK.**</span></span>  

7. <span data-ttu-id="0c671-153">管理コンソールで、**送信ポート**を右クリックして**Tutorial_sendMsg_RX**、順にクリックします**開始**します。</span><span class="sxs-lookup"><span data-stu-id="0c671-153">In the Administration Console, click **Send Ports**, right-click **Tutorial_sendMsg_RX**, and then click **Start**.</span></span>  

   <span data-ttu-id="0c671-154">進みます[手順 7: ADT を配信する送信ポートを作成 ^ A03 メッセージを MLLP アダプターを使用して HIS](../../adapters-and-accelerators/accelerator-hl7/step-7-create-send-port-to-deliver-adt^a03-message-to-his-using-mllp-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="0c671-154">Proceed to [Step 7: Create a Send Port to Deliver the ADT^A03 Message to HIS Using the MLLP Adapter](../../adapters-and-accelerators/accelerator-hl7/step-7-create-send-port-to-deliver-adt^a03-message-to-his-using-mllp-adapter.md).</span></span>