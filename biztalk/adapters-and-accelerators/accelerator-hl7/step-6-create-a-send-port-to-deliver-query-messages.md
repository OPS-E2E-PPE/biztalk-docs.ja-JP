---
title: '手順 6: クエリ メッセージを配信する送信ポートの作成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, send ports
ms.assetid: a3cfa2aa-888d-4a82-9eb3-2e9cc29ee582
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24e65ec7bc4e04850907609fc6d1d63e6f166593
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004051"
---
# <a name="step-6-create-a-send-port-to-deliver-query-messages"></a><span data-ttu-id="a44be-102">手順 6: クエリ メッセージを配信する送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="a44be-102">Step 6: Create a Send Port to Deliver Query Messages</span></span>
<span data-ttu-id="a44be-103">この手順で受信クエリを配信する送信ポートを作成する (QRY ^ Q01 メッセージ) 病院情報システム (HIS) にします。</span><span class="sxs-lookup"><span data-stu-id="a44be-103">In this step, you create the send port to deliver the incoming queries (QRY^Q01 messages) to the Hospital Information System (HIS).</span></span>  

### <a name="to-create-the-hissend-send-port"></a><span data-ttu-id="a44be-104">HIS_Send 送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="a44be-104">To create the HIS_Send send port</span></span>  

1. <span data-ttu-id="a44be-105">右クリックし、BizTalk Server 管理コンソールで**送信ポート**、] をポイント**新規**、し、[**静的な一方向送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="a44be-105">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then select **Static One-way Send Port**.</span></span>  

2. <span data-ttu-id="a44be-106">[送信ポートのプロパティ] ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a44be-106">In the Send Port Properties dialog box, do the following:</span></span>  


   |      <span data-ttu-id="a44be-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a44be-107">Use this</span></span>      |                        <span data-ttu-id="a44be-108">目的</span><span class="sxs-lookup"><span data-stu-id="a44be-108">To do this</span></span>                        |
   |--------------------|----------------------------------------------------------|
   |      <span data-ttu-id="a44be-109">**名前**</span><span class="sxs-lookup"><span data-stu-id="a44be-109">**Name**</span></span>      |                    <span data-ttu-id="a44be-110">型**HIS_Send**します。</span><span class="sxs-lookup"><span data-stu-id="a44be-110">Type **HIS_Send**.</span></span>                    |
   | <span data-ttu-id="a44be-111">**トランスポートの種類**</span><span class="sxs-lookup"><span data-stu-id="a44be-111">**Transport type**</span></span> |                     <span data-ttu-id="a44be-112">選択**MLLP**します。</span><span class="sxs-lookup"><span data-stu-id="a44be-112">Select **MLLP**.</span></span>                     |
   |   <span data-ttu-id="a44be-113">**構成**</span><span class="sxs-lookup"><span data-stu-id="a44be-113">**Configure**</span></span>    | <span data-ttu-id="a44be-114">をクリックして、**構成**ボタンの右側に**型**します。</span><span class="sxs-lookup"><span data-stu-id="a44be-114">Click the **Configure** button to the right of **Type**.</span></span> |


3. <span data-ttu-id="a44be-115">MLLP トランスポートのプロパティ ダイアログ ボックスで、次の情報を入力し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="a44be-115">In the MLLP Transport Properties dialog box, enter the following information and then click **OK**.</span></span>  


   |      <span data-ttu-id="a44be-116">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a44be-116">Use this</span></span>       |       <span data-ttu-id="a44be-117">目的</span><span class="sxs-lookup"><span data-stu-id="a44be-117">To do this</span></span>       |
   |---------------------|------------------------|
   | <span data-ttu-id="a44be-118">**接続名**</span><span class="sxs-lookup"><span data-stu-id="a44be-118">**Connection Name**</span></span> | <span data-ttu-id="a44be-119">型**HIS_SendMLLP**します。</span><span class="sxs-lookup"><span data-stu-id="a44be-119">Type **HIS_SendMLLP**.</span></span> |
   |      <span data-ttu-id="a44be-120">**ホスト**</span><span class="sxs-lookup"><span data-stu-id="a44be-120">**Host**</span></span>       |  <span data-ttu-id="a44be-121">型**localhost**します。</span><span class="sxs-lookup"><span data-stu-id="a44be-121">Type **localhost**.</span></span>   |
   |      <span data-ttu-id="a44be-122">**[ポート]**</span><span class="sxs-lookup"><span data-stu-id="a44be-122">**Port**</span></span>       |    <span data-ttu-id="a44be-123">型**24000**します。</span><span class="sxs-lookup"><span data-stu-id="a44be-123">Type **24000**.</span></span>     |


4. <span data-ttu-id="a44be-124">送信ポートのプロパティ ダイアログ ボックスでの**送信パイプライン**、 **BTAHL72XPipelines.BTAHL72XSendPipeline**します。</span><span class="sxs-lookup"><span data-stu-id="a44be-124">In the Send Port Properties dialog box, for **Send Pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span></span>  

5. <span data-ttu-id="a44be-125">コンソール ツリーで、クリックして**フィルター**、し、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a44be-125">In the Console Tree, click **Filters**, and then do the following:</span></span>  


   |   <span data-ttu-id="a44be-126">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a44be-126">Use this</span></span>   |                              <span data-ttu-id="a44be-127">目的</span><span class="sxs-lookup"><span data-stu-id="a44be-127">To do this</span></span>                               |
   |--------------|-----------------------------------------------------------------------|
   | <span data-ttu-id="a44be-128">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="a44be-128">**Property**</span></span> |             <span data-ttu-id="a44be-129">**プロパティ**、 **BTS します。MessageType**します。</span><span class="sxs-lookup"><span data-stu-id="a44be-129">For **Property**, select **BTS.MessageType**.</span></span>             |
   | <span data-ttu-id="a44be-130">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="a44be-130">**Operator**</span></span> |                <span data-ttu-id="a44be-131">選択**==** ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="a44be-131">Select **==** from the drop-down list.</span></span>                 |
   |  <span data-ttu-id="a44be-132">**[値]**</span><span class="sxs-lookup"><span data-stu-id="a44be-132">**Value**</span></span>   | <span data-ttu-id="a44be-133">型 **<http://microsoft.com/HealthCare/HL7/2X#QRY_Q01_24_GLO_DEF>** します。</span><span class="sxs-lookup"><span data-stu-id="a44be-133">Type **<http://microsoft.com/HealthCare/HL7/2X#QRY_Q01_24_GLO_DEF>**.</span></span> |
   | <span data-ttu-id="a44be-134">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="a44be-134">**Group By**</span></span> |                <span data-ttu-id="a44be-135">選択**AND**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="a44be-135">Select **AND** from the drop-down list.</span></span>                |
   | <span data-ttu-id="a44be-136">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="a44be-136">**Property**</span></span> | <span data-ttu-id="a44be-137">**プロパティ**2 行目で、次のように選択します。 **BTAHL7Schemas.MSH5_1**します。</span><span class="sxs-lookup"><span data-stu-id="a44be-137">For **Property** on the second line, select **BTAHL7Schemas.MSH5_1**.</span></span> |
   | <span data-ttu-id="a44be-138">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="a44be-138">**Operator**</span></span> |                <span data-ttu-id="a44be-139">選択**==** ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="a44be-139">Select **==** from the drop-down list.</span></span>                 |
   |  <span data-ttu-id="a44be-140">**[値]**</span><span class="sxs-lookup"><span data-stu-id="a44be-140">**Value**</span></span>   |                             <span data-ttu-id="a44be-141">型**HIS**します。</span><span class="sxs-lookup"><span data-stu-id="a44be-141">Type **HIS**.</span></span>                             |

   > [!NOTE]
   >  <span data-ttu-id="a44be-142">最初のフィルターは、送信ポートのみ、クエリに準拠したメッセージを選択することを指定します ^ 手順 3 a. で作成した Q01 スキーマ。</span><span class="sxs-lookup"><span data-stu-id="a44be-142">The first filter specifies that the send port only selects messages conforming to the QRY^Q01 schema you created in step 3A.</span></span> <span data-ttu-id="a44be-143">2 番目のフィルターが先を指定します、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]インターフェイス エンジンはこれらのメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="a44be-143">The second filter specifies the destination to which the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine sends these messages.</span></span>  

6. <span data-ttu-id="a44be-144">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a44be-144">Click **OK**.</span></span>  

7. <span data-ttu-id="a44be-145">管理コンソールで、[**送信ポート**を右クリックして**HIS_Send**、] をクリックし、**開始**。</span><span class="sxs-lookup"><span data-stu-id="a44be-145">In the Administration console, select **Send Ports**, right-click **HIS_Send**, and then click **Start**.</span></span>  

   <span data-ttu-id="a44be-146">続行する[手順 7: 応答メッセージを配信する送信ポートを作成](../../adapters-and-accelerators/accelerator-hl7/step-7-create-a-send-port-to-deliver-response-messages.md)です。</span><span class="sxs-lookup"><span data-stu-id="a44be-146">Proceed to [Step 7: Create a Send Port to Deliver Response Messages](../../adapters-and-accelerators/accelerator-hl7/step-7-create-a-send-port-to-deliver-response-messages.md).</span></span>