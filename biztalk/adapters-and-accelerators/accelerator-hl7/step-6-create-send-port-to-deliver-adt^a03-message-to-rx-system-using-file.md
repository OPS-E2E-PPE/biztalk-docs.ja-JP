---
title: 手順 6:ADT を配信する送信ポートを作成 ^ A03 メッセージをファイル アダプターを使用して RX System |Microsoft Docs
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
ms.openlocfilehash: 7674721e3c59ea9f7af0864b2c0790ebf9a1ab92
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288005"
---
# <a name="step-6-create-a-send-port-to-deliver-the-adta03-message-to-the-rx-system-using-the-file-adapter"></a><span data-ttu-id="ac189-102">手順 6:ADT を配信する送信ポートを作成 ^ A03 メッセージをファイル アダプターを使用して RX System</span><span class="sxs-lookup"><span data-stu-id="ac189-102">Step 6: Create a Send Port to Deliver the ADT^A03 Message to the RX System Using the File Adapter</span></span>
<span data-ttu-id="ac189-103">この手順で、送信ポートの薬剤システム (RX)、ファイル アダプターを使用してを作成します。</span><span class="sxs-lookup"><span data-stu-id="ac189-103">In this step, you create the send port for the Pharmacy System (RX) using the File adapter.</span></span>  

### <a name="to-create-the-tutorialsendmsgrx-send-port"></a><span data-ttu-id="ac189-104">Tutorial_sendMsg_RX 送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="ac189-104">To create the Tutorial_sendMsg_RX send port</span></span>  

1. <span data-ttu-id="ac189-105">右クリックし、BizTalk Server 管理コンソールで**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート**。</span><span class="sxs-lookup"><span data-stu-id="ac189-105">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  

2. <span data-ttu-id="ac189-106">**送信ポートのプロパティ** ダイアログ ボックスで、次の操作を実行し、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="ac189-106">In the **Send Port Properties** dialog box, do the following actions and then click **OK**.</span></span>  


   |      <span data-ttu-id="ac189-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ac189-107">Use this</span></span>      |                                <span data-ttu-id="ac189-108">目的</span><span class="sxs-lookup"><span data-stu-id="ac189-108">To do this</span></span>                                 |
   |--------------------|---------------------------------------------------------------------------|
   |      <span data-ttu-id="ac189-109">**名前**</span><span class="sxs-lookup"><span data-stu-id="ac189-109">**Name**</span></span>      |                       <span data-ttu-id="ac189-110">型**Tutorial_sendMsg_RX**します。</span><span class="sxs-lookup"><span data-stu-id="ac189-110">Type **Tutorial_sendMsg_RX**.</span></span>                       |
   | <span data-ttu-id="ac189-111">**トランスポートの種類**</span><span class="sxs-lookup"><span data-stu-id="ac189-111">**Transport type**</span></span> |                 <span data-ttu-id="ac189-112">選択**ファイル**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="ac189-112">Select **FILE** from the drop-down list.</span></span>                  |
   |   <span data-ttu-id="ac189-113">**構成**</span><span class="sxs-lookup"><span data-stu-id="ac189-113">**Configure**</span></span>    | <span data-ttu-id="ac189-114">クリックして**構成**を開く、 **File トランスポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="ac189-114">Click **Configure** to open the **File Transport Properties** dialog box.</span></span> |


3. <span data-ttu-id="ac189-115">ファイル トランスポートのプロパティ ダイアログ ボックスで、次の操作を実行し、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="ac189-115">In the FILE Transport Properties dialog box, do the following actions and then click **OK**.</span></span>  


   |        <span data-ttu-id="ac189-116">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ac189-116">Use this</span></span>        |                                                                     <span data-ttu-id="ac189-117">目的</span><span class="sxs-lookup"><span data-stu-id="ac189-117">To do this</span></span>                                                                     |
   |------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="ac189-118">**コピー先フォルダー**</span><span class="sxs-lookup"><span data-stu-id="ac189-118">**Destination folder**</span></span> | <span data-ttu-id="ac189-119">参照する**\<**<em>ドライブ</em>**:\>\Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End ツー エンドのアクセラレータTutorial\Tutorial_sendMsg_RX**します。</span><span class="sxs-lookup"><span data-stu-id="ac189-119">Browse to **\<**<em>drive</em>**:\>\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_sendMsg_RX**.</span></span> |
   |     <span data-ttu-id="ac189-120">**[ファイル名]**</span><span class="sxs-lookup"><span data-stu-id="ac189-120">**File name**</span></span>      |                                   <span data-ttu-id="ac189-121">型 **%MessageID%.txt** (.txt 拡張子 .xml 拡張子を置き換えます)。</span><span class="sxs-lookup"><span data-stu-id="ac189-121">Type **%MessageID%.txt** (replace the .xml extension with the .txt extension).</span></span>                                   |


4. <span data-ttu-id="ac189-122">**送信ポートのプロパティ** ダイアログ ボックスの**送信パイプライン**を選択します**BTAHL72XPipelines.BTAHL72XSendPipeline**します。</span><span class="sxs-lookup"><span data-stu-id="ac189-122">In the **Send Port Properties** dialog box, for **Send Pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span></span>  

5. <span data-ttu-id="ac189-123">左側のウィンドウで次のように選択します。**フィルター**、し、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="ac189-123">In the left pane, select **Filters**, and then do the following actions.</span></span> <span data-ttu-id="ac189-124">続行するには、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac189-124">Click **OK** to continue.</span></span>  


   |          <span data-ttu-id="ac189-125">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ac189-125">Use this</span></span>          |                                            <span data-ttu-id="ac189-126">目的</span><span class="sxs-lookup"><span data-stu-id="ac189-126">To do this</span></span>                                            |
   |----------------------------|--------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="ac189-127">**プロパティ**(1 行目)</span><span class="sxs-lookup"><span data-stu-id="ac189-127">**Property** (first line)</span></span>  |                       <span data-ttu-id="ac189-128">選択**BTS します。MessageType**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="ac189-128">Select **BTS.MessageType** from the drop-down list.</span></span>                        |
   |        <span data-ttu-id="ac189-129">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="ac189-129">**Operator**</span></span>        |                              <span data-ttu-id="ac189-130">選択 **! =** ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="ac189-130">Select **!=** from the drop-down list.</span></span>                              |
   |         <span data-ttu-id="ac189-131">**[値]**</span><span class="sxs-lookup"><span data-stu-id="ac189-131">**Value**</span></span>          |                <span data-ttu-id="ac189-132">型 **<http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF>** します。</span><span class="sxs-lookup"><span data-stu-id="ac189-132">Type **<http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF>**.</span></span>                 |
   |        <span data-ttu-id="ac189-133">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="ac189-133">**Group By**</span></span>        |                              <span data-ttu-id="ac189-134">選択**または**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="ac189-134">Select **OR** from the drop-down list.</span></span>                              |
   | <span data-ttu-id="ac189-135">**プロパティ**(2 行目)</span><span class="sxs-lookup"><span data-stu-id="ac189-135">**Property** (second line)</span></span> | <span data-ttu-id="ac189-136">下のフィールドをクリックします。**プロパティ**、し、 **BTS します。MessageType**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="ac189-136">Click the field under **Property**, and then select **BTS.MessageType** from the drop-down list.</span></span> |
   |        <span data-ttu-id="ac189-137">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="ac189-137">**Operator**</span></span>        |                              <span data-ttu-id="ac189-138">選択 **! =** ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="ac189-138">Select **!=** from the drop-down list.</span></span>                              |
   |         <span data-ttu-id="ac189-139">**[値]**</span><span class="sxs-lookup"><span data-stu-id="ac189-139">**Value**</span></span>          |                <span data-ttu-id="ac189-140">型**<http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF>します。**</span><span class="sxs-lookup"><span data-stu-id="ac189-140">Type **<http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF>.**</span></span>                 |
   |        <span data-ttu-id="ac189-141">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="ac189-141">**Group By**</span></span>        |                             <span data-ttu-id="ac189-142">選択**AND**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="ac189-142">Select **AND** from the drop-down list.</span></span>                              |
   | <span data-ttu-id="ac189-143">**プロパティ**(3 行目)</span><span class="sxs-lookup"><span data-stu-id="ac189-143">**Property** (third line)</span></span>  |                                 <span data-ttu-id="ac189-144">選択**BTAHL7Schemas.MSH3_1**します。</span><span class="sxs-lookup"><span data-stu-id="ac189-144">Select **BTAHL7Schemas.MSH3_1**.</span></span>                                 |
   |        <span data-ttu-id="ac189-145">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="ac189-145">**Operator**</span></span>        |                              <span data-ttu-id="ac189-146">選択**==** ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="ac189-146">Select **==** from the drop-down list.</span></span>                              |
   |         <span data-ttu-id="ac189-147">**[値]**</span><span class="sxs-lookup"><span data-stu-id="ac189-147">**Value**</span></span>          |                                   <span data-ttu-id="ac189-148">型**Tutorial_ADTSystem**します。</span><span class="sxs-lookup"><span data-stu-id="ac189-148">Type **Tutorial_ADTSystem**.</span></span>                                   |

   > [!NOTE]
   >  <span data-ttu-id="ac189-149">最初のフィルターは、病院情報システム (HIS) が受信確認にいないメッセージにサブスクライブすることを意味します。</span><span class="sxs-lookup"><span data-stu-id="ac189-149">The first filter means that the Hospital Information System (HIS) is subscribing to a message, not an acknowledgment.</span></span> <span data-ttu-id="ac189-150">2 番目のフィルターは、ソースが入学放電と転送 (ADT) システムは、メッセージのサブスクライブ彼はことを意味します。</span><span class="sxs-lookup"><span data-stu-id="ac189-150">The second filter means that HIS is subscribing to messages whose source is the Admissions Discharge and Transfer (ADT) System.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="ac189-151">BTAHL7 ファイルの格納場所でメッセージをドロップする\<*ドライブ*\>: Program FilesMicrosoft BizTalk <version> HL7SDKEnd ツー エンド TutorialTutorial_sendMsg_RX のアクセラレータです。</span><span class="sxs-lookup"><span data-stu-id="ac189-151">BTAHL7 drops the message at the file drop location \<*drive*\>:Program FilesMicrosoft BizTalk <version> Accelerator for HL7SDKEnd-to-End TutorialTutorial_sendMsg_RX.</span></span>  

6. <span data-ttu-id="ac189-152">クリックして**適用**、順にクリックします**ok をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="ac189-152">Click **Apply**, and then click **OK.**</span></span>  

7. <span data-ttu-id="ac189-153">管理コンソールで、**送信ポート**を右クリックして**Tutorial_sendMsg_RX**、順にクリックします**開始**します。</span><span class="sxs-lookup"><span data-stu-id="ac189-153">In the Administration Console, click **Send Ports**, right-click **Tutorial_sendMsg_RX**, and then click **Start**.</span></span>  

   <span data-ttu-id="ac189-154">続行する[手順 7。ADT を配信する送信ポートを作成 ^ A03 メッセージを MLLP アダプターを使用して HIS](../../adapters-and-accelerators/accelerator-hl7/step-7-create-send-port-to-deliver-adt^a03-message-to-his-using-mllp-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="ac189-154">Proceed to [Step 7: Create a Send Port to Deliver the ADT^A03 Message to HIS Using the MLLP Adapter](../../adapters-and-accelerators/accelerator-hl7/step-7-create-send-port-to-deliver-adt^a03-message-to-his-using-mllp-adapter.md).</span></span>