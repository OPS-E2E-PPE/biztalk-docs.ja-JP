---
title: '手順 5: ファイル アダプターを使用して ADT System に受信確認を配信する送信ポートの作成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, send ports
- send ports, acknowledgements
- creating, send ports
- acknowledgements, send ports
- send ports, creating
ms.assetid: 565a2adf-fd86-46e3-8035-7e4748aefffc
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1421b39ed4bbd15fb82cb16ed55b23e5781eead6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002099"
---
# <a name="step-5-create-a-send-port-to-deliver-acknowledgments-to-the-adt-system-using-the-file-adapter"></a><span data-ttu-id="b16f8-102">手順 5: ファイル アダプターを使用して ADT System に受信確認を配信する送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="b16f8-102">Step 5: Create a Send Port to Deliver Acknowledgments to the ADT System Using the File Adapter</span></span>
<span data-ttu-id="b16f8-103">この手順では、ファイル アダプターを使用して受信確認を生成する送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="b16f8-103">In this step, you create the send port to generate acknowledgments using the File adapter.</span></span>  

### <a name="to-create-the-tutorialsendackadt-send-port"></a><span data-ttu-id="b16f8-104">Tutorial_sendAck_ADT 送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="b16f8-104">To create the Tutorial_sendAck_ADT send port</span></span>  

1. <span data-ttu-id="b16f8-105">使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、作成、 \<*ドライブ*:\>\Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End ツー エンド Tutorial\Tutorial_ のアクセラレータsendAck_ADT フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="b16f8-105">Using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, create the \<*drive*:\>\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_sendAck_ADT folder.</span></span>  

2. <span data-ttu-id="b16f8-106">右クリックし、BizTalk Server 管理コンソールで**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート**。</span><span class="sxs-lookup"><span data-stu-id="b16f8-106">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  

3. <span data-ttu-id="b16f8-107">[送信ポートのプロパティ] ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b16f8-107">In the Send Port Properties dialog box, do the following:</span></span>  


   |      <span data-ttu-id="b16f8-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b16f8-108">Use this</span></span>      |                                <span data-ttu-id="b16f8-109">目的</span><span class="sxs-lookup"><span data-stu-id="b16f8-109">To do this</span></span>                                 |
   |--------------------|---------------------------------------------------------------------------|
   |      <span data-ttu-id="b16f8-110">**名前**</span><span class="sxs-lookup"><span data-stu-id="b16f8-110">**Name**</span></span>      |                      <span data-ttu-id="b16f8-111">型**Tutorial_sendAck_ADT**します。</span><span class="sxs-lookup"><span data-stu-id="b16f8-111">Type **Tutorial_sendAck_ADT**.</span></span>                       |
   | <span data-ttu-id="b16f8-112">**トランスポートの種類**</span><span class="sxs-lookup"><span data-stu-id="b16f8-112">**Transport type**</span></span> |                 <span data-ttu-id="b16f8-113">選択**ファイル**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="b16f8-113">Select **FILE** from the drop-down list.</span></span>                  |
   |   <span data-ttu-id="b16f8-114">**構成**</span><span class="sxs-lookup"><span data-stu-id="b16f8-114">**Configure**</span></span>    | <span data-ttu-id="b16f8-115">クリックして**構成**を開く、 **File トランスポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="b16f8-115">Click **Configure** to open the **File Transport Properties** dialog box.</span></span> |


4. <span data-ttu-id="b16f8-116">FILE トランスポートのプロパティ ダイアログ ボックスで、次の操作し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="b16f8-116">In the FILE Transport Properties dialog box, do the following and then click **OK**.</span></span>  


   |        <span data-ttu-id="b16f8-117">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b16f8-117">Use this</span></span>        |                                                                     <span data-ttu-id="b16f8-118">目的</span><span class="sxs-lookup"><span data-stu-id="b16f8-118">To do this</span></span>                                                                      |
   |------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="b16f8-119">**コピー先フォルダー**</span><span class="sxs-lookup"><span data-stu-id="b16f8-119">**Destination folder**</span></span> | <span data-ttu-id="b16f8-120">参照する**\<**<em>ドライブ</em>**:\>\Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End ツー エンドのアクセラレータTutorial\Tutorial_sendAck_ADT**します。</span><span class="sxs-lookup"><span data-stu-id="b16f8-120">Browse to **\<**<em>drive</em>**:\>\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_sendAck_ADT**.</span></span> |
   |     <span data-ttu-id="b16f8-121">**[ファイル名]**</span><span class="sxs-lookup"><span data-stu-id="b16f8-121">**File name**</span></span>      |                                   <span data-ttu-id="b16f8-122">型 **%MessageID%.txt** (.txt 拡張子 .xml 拡張子を置き換えます)。</span><span class="sxs-lookup"><span data-stu-id="b16f8-122">Type **%MessageID%.txt** (replace the .xml extension with the .txt extension).</span></span>                                    |


5. <span data-ttu-id="b16f8-123">送信ポートのプロパティ ダイアログ ボックスでの**送信パイプライン**、 **BTAHL72XPipelines.BTAHL72XSendPipeline**します。</span><span class="sxs-lookup"><span data-stu-id="b16f8-123">In the Send Port Properties dialog box, for **Send pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span></span>  

6. <span data-ttu-id="b16f8-124">左側のウィンドウで次のようにクリックします。**フィルター**、し、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b16f8-124">In the left pane, click **Filters**, and then do the following:</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="b16f8-125">最初のフィルターは、受信確認メッセージをサブスクライブしていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="b16f8-125">The first filter means that you are subscribing for the acknowledgment message.</span></span> <span data-ttu-id="b16f8-126">2 番目のフィルターは、パブリッシャー Tutorial_ADTSystem 送信先となる受信確認をサブスクライブしていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="b16f8-126">The second filter means that you are subscribing to the acknowledgment that is destined for the publisher Tutorial_ADTSystem.</span></span>  

    <span data-ttu-id="b16f8-127">クリックして**OK**続行する準備ができたら。</span><span class="sxs-lookup"><span data-stu-id="b16f8-127">Click **OK** when you are ready to continue.</span></span>  


   |          <span data-ttu-id="b16f8-128">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b16f8-128">Use this</span></span>          |                                            <span data-ttu-id="b16f8-129">目的</span><span class="sxs-lookup"><span data-stu-id="b16f8-129">To do this</span></span>                                            |
   |----------------------------|--------------------------------------------------------------------------------------------------|
   |        <span data-ttu-id="b16f8-130">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="b16f8-130">**Property**</span></span>        | <span data-ttu-id="b16f8-131">下のフィールドをクリックします。**プロパティ**、し、 **BTS します。MessageType**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="b16f8-131">Click the field under **Property**, and then select **BTS.MessageType** from the drop-down list.</span></span> |
   |        <span data-ttu-id="b16f8-132">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="b16f8-132">**Operator**</span></span>        |                              <span data-ttu-id="b16f8-133">選択**==** ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="b16f8-133">Select **==** from the drop-down list.</span></span>                              |
   |         <span data-ttu-id="b16f8-134">**[値]**</span><span class="sxs-lookup"><span data-stu-id="b16f8-134">**Value**</span></span>          |                <span data-ttu-id="b16f8-135">型 **<http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF>** します。</span><span class="sxs-lookup"><span data-stu-id="b16f8-135">Type **<http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF>**.</span></span>                 |
   |        <span data-ttu-id="b16f8-136">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="b16f8-136">**Group By**</span></span>        |                              <span data-ttu-id="b16f8-137">選択**または**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="b16f8-137">Select **OR** from the drop-down list.</span></span>                              |
   | <span data-ttu-id="b16f8-138">**プロパティ (2 行目)**</span><span class="sxs-lookup"><span data-stu-id="b16f8-138">**Property (second line)**</span></span> | <span data-ttu-id="b16f8-139">下のフィールドをクリックします。**プロパティ**、し、 **BTS します。MessageType**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="b16f8-139">Click the field under **Property**, and then select **BTS.MessageType** from the drop-down list.</span></span> |
   |        <span data-ttu-id="b16f8-140">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="b16f8-140">**Operator**</span></span>        |                              <span data-ttu-id="b16f8-141">選択**==** ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="b16f8-141">Select **==** from the drop-down list.</span></span>                              |
   |         <span data-ttu-id="b16f8-142">**[値]**</span><span class="sxs-lookup"><span data-stu-id="b16f8-142">**Value**</span></span>          |                <span data-ttu-id="b16f8-143">型**<http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF>します。**</span><span class="sxs-lookup"><span data-stu-id="b16f8-143">Type **<http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF>.**</span></span>                 |
   |        <span data-ttu-id="b16f8-144">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="b16f8-144">**Group By**</span></span>        |                             <span data-ttu-id="b16f8-145">選択**AND**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="b16f8-145">Select **AND** from the drop-down list.</span></span>                              |
   |        <span data-ttu-id="b16f8-146">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="b16f8-146">**Property**</span></span>        |     <span data-ttu-id="b16f8-147">最初のプロパティの下の空のボックスをクリックし、 **BTAHL7Schemas.MSH5_1**します。</span><span class="sxs-lookup"><span data-stu-id="b16f8-147">Under the first property, click the blank box, and then select **BTAHL7Schemas.MSH5_1**.</span></span>     |
   |        <span data-ttu-id="b16f8-148">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="b16f8-148">**Operator**</span></span>        |                              <span data-ttu-id="b16f8-149">選択**==** ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="b16f8-149">Select **==** from the drop-down list.</span></span>                              |
   |         <span data-ttu-id="b16f8-150">**[値]**</span><span class="sxs-lookup"><span data-stu-id="b16f8-150">**Value**</span></span>          |                                   <span data-ttu-id="b16f8-151">型**Tutorial_ADTSystem**します。</span><span class="sxs-lookup"><span data-stu-id="b16f8-151">Type **Tutorial_ADTSystem**.</span></span>                                   |

   > [!NOTE]
   >  <span data-ttu-id="b16f8-152">BTAHL7 Tutorial_sendAck_ADT 送信ポートのファイルの格納場所で、受信確認を削除します\<*ドライブ*\>: Program FilesMicrosoft BizTalk <version> HL7SDKEnd ツー エンドのアクセラレータTutorialTutorial_sendAck_ADT します。</span><span class="sxs-lookup"><span data-stu-id="b16f8-152">For the send port Tutorial_sendAck_ADT, BTAHL7 drops the acknowledgments at the file drop location \<*drive*\>:Program FilesMicrosoft BizTalk <version> Accelerator for HL7SDKEnd-to-End TutorialTutorial_sendAck_ADT.</span></span>  

7. <span data-ttu-id="b16f8-153">クリックして**適用**、順にクリックします**ok をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="b16f8-153">Click **Apply**, and then click **OK.**</span></span>  

8. <span data-ttu-id="b16f8-154">管理コンソールで、**送信ポート**を右クリックして**Tutorial_sendAck_ADT**、順にクリックします**開始**します。</span><span class="sxs-lookup"><span data-stu-id="b16f8-154">In the Administration Console, click **Send Ports**, right-click **Tutorial_sendAck_ADT**, and then click **Start**.</span></span>  

   <span data-ttu-id="b16f8-155">続行する[手順 6: ADT を配信する送信ポートを作成 ^ A03 メッセージをファイル アダプターを使用して RX System](../../adapters-and-accelerators/accelerator-hl7/step-6-create-send-port-to-deliver-adt^a03-message-to-rx-system-using-file.md)します。</span><span class="sxs-lookup"><span data-stu-id="b16f8-155">Proceed to [Step 6: Create a Send Port to Deliver the ADT^A03 Message to the RX System Using the File Adapter](../../adapters-and-accelerators/accelerator-hl7/step-6-create-send-port-to-deliver-adt^a03-message-to-rx-system-using-file.md).</span></span>