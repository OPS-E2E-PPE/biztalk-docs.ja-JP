---
title: '手順 7: ADT を配信する送信ポートを作成する ^ A03 メッセージを MLLP アダプターを使用して HIS |Microsoft Docs'
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
ms.assetid: d9e7f281-3d25-4675-a13e-0e2057f5e69a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 540a8745da811e7f14ab6ac5c1909bffe057c5f7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006107"
---
# <a name="step-7-create-a-send-port-to-deliver-the-adta03-message-to-his-using-the-mllp-adapter"></a><span data-ttu-id="3deed-102">手順 7: ADT を配信する送信ポートを作成する ^ A03 メッセージを MLLP アダプターを使用して HIS</span><span class="sxs-lookup"><span data-stu-id="3deed-102">Step 7: Create a Send Port to Deliver the ADT^A03 Message to HIS Using the MLLP Adapter</span></span>
<span data-ttu-id="3deed-103">この手順では、MLLP アダプターを使用して医療情報システム (HIS) にメッセージを送信する送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="3deed-103">In this step, you create the send port to send the message to the Hospital Information System (HIS) using the MLLP adapter.</span></span>  

### <a name="to-create-the-tutorialmllpsend-send-port"></a><span data-ttu-id="3deed-104">Tutorial_MllpSend 送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="3deed-104">To create the Tutorial_MllpSend send port</span></span>  

1. <span data-ttu-id="3deed-105">右クリックし、BizTalk Server 管理コンソールで**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート**。</span><span class="sxs-lookup"><span data-stu-id="3deed-105">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  

2. <span data-ttu-id="3deed-106">送信ポートのプロパティ ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3deed-106">In the Send Port Properties dialog box, do the following actions:</span></span>  


   |      <span data-ttu-id="3deed-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="3deed-107">Use this</span></span>      |                                <span data-ttu-id="3deed-108">目的</span><span class="sxs-lookup"><span data-stu-id="3deed-108">To do this</span></span>                                 |
   |--------------------|---------------------------------------------------------------------------|
   |      <span data-ttu-id="3deed-109">**名前**</span><span class="sxs-lookup"><span data-stu-id="3deed-109">**Name**</span></span>      |                        <span data-ttu-id="3deed-110">型**Tutorial_MllpSend**します。</span><span class="sxs-lookup"><span data-stu-id="3deed-110">Type **Tutorial_MllpSend**.</span></span>                        |
   | <span data-ttu-id="3deed-111">**トランスポートの種類**</span><span class="sxs-lookup"><span data-stu-id="3deed-111">**Transport type**</span></span> |                 <span data-ttu-id="3deed-112">選択**MLLP**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="3deed-112">Select **MLLP** from the drop-down list.</span></span>                  |
   |   <span data-ttu-id="3deed-113">**構成**</span><span class="sxs-lookup"><span data-stu-id="3deed-113">**Configure**</span></span>    | <span data-ttu-id="3deed-114">クリックして**構成**を開く、 **MLLP トランスポート プロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="3deed-114">Click **Configure** to open the **MLLP Transport Properties** dialog box.</span></span> |


3. <span data-ttu-id="3deed-115">MLLP トランスポートのプロパティ ダイアログ ボックスで、次の操作を行ってをクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="3deed-115">In the MLLP Transport Properties dialog box, do the following actions and then click **OK**.</span></span>  


   |      <span data-ttu-id="3deed-116">プロパティ</span><span class="sxs-lookup"><span data-stu-id="3deed-116">Use this</span></span>       |     <span data-ttu-id="3deed-117">目的</span><span class="sxs-lookup"><span data-stu-id="3deed-117">To do this</span></span>      |
   |---------------------|---------------------|
   | <span data-ttu-id="3deed-118">**接続名**</span><span class="sxs-lookup"><span data-stu-id="3deed-118">**Connection Name**</span></span> | <span data-ttu-id="3deed-119">型**1WaySend**します。</span><span class="sxs-lookup"><span data-stu-id="3deed-119">Type **1WaySend**.</span></span>  |
   |      <span data-ttu-id="3deed-120">**ホスト**</span><span class="sxs-lookup"><span data-stu-id="3deed-120">**Host**</span></span>       | <span data-ttu-id="3deed-121">型**localhost**します。</span><span class="sxs-lookup"><span data-stu-id="3deed-121">Type **localhost**.</span></span> |
   |      <span data-ttu-id="3deed-122">**[ポート]**</span><span class="sxs-lookup"><span data-stu-id="3deed-122">**Port**</span></span>       |   <span data-ttu-id="3deed-123">型**14000**します。</span><span class="sxs-lookup"><span data-stu-id="3deed-123">Type **14000**.</span></span>   |


4. <span data-ttu-id="3deed-124">送信ポートのプロパティ ダイアログ ボックスでの**送信パイプライン**、 **BTAHL72XPipelines.BTAHL72XSendPipeline**します。</span><span class="sxs-lookup"><span data-stu-id="3deed-124">In the Send Port Properties dialog box, for **Send Pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span></span>  

5. <span data-ttu-id="3deed-125">左側のウィンドウで次のように選択します。**フィルター**、し、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3deed-125">In the left pane, select **Filters**, and then do the following:</span></span>  

   |<span data-ttu-id="3deed-126">プロパティ</span><span class="sxs-lookup"><span data-stu-id="3deed-126">Use this</span></span>|<span data-ttu-id="3deed-127">目的</span><span class="sxs-lookup"><span data-stu-id="3deed-127">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="3deed-128">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="3deed-128">**Property**</span></span>|<span data-ttu-id="3deed-129">選択**BTS します。ReceivePortName**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="3deed-129">Select **BTS.ReceivePortName** from the drop-down list.</span></span>|  
   |<span data-ttu-id="3deed-130">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="3deed-130">**Operator**</span></span>|<span data-ttu-id="3deed-131">選択**==** ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="3deed-131">Select **==** from the drop-down list.</span></span>|  
   |<span data-ttu-id="3deed-132">**[値]**</span><span class="sxs-lookup"><span data-stu-id="3deed-132">**Value**</span></span>|<span data-ttu-id="3deed-133">型**Tutorial_1WayReceive**します。</span><span class="sxs-lookup"><span data-stu-id="3deed-133">Type **Tutorial_1WayReceive**.</span></span>|  

   > [!NOTE]
   >  <span data-ttu-id="3deed-134">ポートのメッセージ 1WayReceive で指定されたポートをリッスンします。</span><span class="sxs-lookup"><span data-stu-id="3deed-134">The port will listen to the port specified in 1WayReceive for any messages.</span></span>  

6. <span data-ttu-id="3deed-135">クリックして**適用**、順にクリックします**ok をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="3deed-135">Click **Apply**, and then click **OK.**</span></span>  

7. <span data-ttu-id="3deed-136">管理コンソールで、**送信ポート**を右クリックして**Tutorial_MllpSend**、順にクリックします**開始**します。</span><span class="sxs-lookup"><span data-stu-id="3deed-136">In the Administration Console, click **Send Ports**, right-click **Tutorial_MllpSend**, and then click **Start**.</span></span>  

   <span data-ttu-id="3deed-137">続行する[手順 8: パーティ情報の構成](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information.md)します。</span><span class="sxs-lookup"><span data-stu-id="3deed-137">Proceed to [Step 8: Configure Party Information](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information.md).</span></span>