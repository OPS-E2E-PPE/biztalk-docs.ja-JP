---
title: "手順 7: ADT を配信する送信ポートを作成する ^ MLLP アダプターを使用して自分に A03 メッセージ |Microsoft ドキュメント"
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
ms.assetid: d9e7f281-3d25-4675-a13e-0e2057f5e69a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc122ab37ee0d618c3bd75792a5b88571dd49162
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-7-create-a-send-port-to-deliver-the-adta03-message-to-his-using-the-mllp-adapter"></a><span data-ttu-id="413e4-102">手順 7: ADT を配信する送信ポートを作成する ^ MLLP アダプターを使用して自分に A03 メッセージ</span><span class="sxs-lookup"><span data-stu-id="413e4-102">Step 7: Create a Send Port to Deliver the ADT^A03 Message to HIS Using the MLLP Adapter</span></span>
<span data-ttu-id="413e4-103">この手順では、メッセージを送信する、病院情報システム (HIS) MLLP アダプターを使用して、送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="413e4-103">In this step, you create the send port to send the message to the Hospital Information System (HIS) using the MLLP adapter.</span></span>  
  
### <a name="to-create-the-tutorialmllpsend-send-port"></a><span data-ttu-id="413e4-104">Tutorial_MllpSend 送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="413e4-104">To create the Tutorial_MllpSend send port</span></span>  
  
1.  <span data-ttu-id="413e4-105">BizTalk Server 管理コンソールで、右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="413e4-105">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="413e4-106">送信ポートのプロパティ ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="413e4-106">In the Send Port Properties dialog box, do the following actions:</span></span>  
  
    |<span data-ttu-id="413e4-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="413e4-107">Use this</span></span>|<span data-ttu-id="413e4-108">目的</span><span class="sxs-lookup"><span data-stu-id="413e4-108">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="413e4-109">**名前**</span><span class="sxs-lookup"><span data-stu-id="413e4-109">**Name**</span></span>|<span data-ttu-id="413e4-110">型**Tutorial_MllpSend**です。</span><span class="sxs-lookup"><span data-stu-id="413e4-110">Type **Tutorial_MllpSend**.</span></span>|  
    |<span data-ttu-id="413e4-111">**トランスポートの種類**</span><span class="sxs-lookup"><span data-stu-id="413e4-111">**Transport type**</span></span>|<span data-ttu-id="413e4-112">選択**MLLP**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="413e4-112">Select **MLLP** from the drop-down list.</span></span>|  
    |<span data-ttu-id="413e4-113">**構成**</span><span class="sxs-lookup"><span data-stu-id="413e4-113">**Configure**</span></span>|<span data-ttu-id="413e4-114">をクリックして**構成**を開くには、 **MLLP トランスポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="413e4-114">Click **Configure** to open the **MLLP Transport Properties** dialog box.</span></span>|  
  
3.  <span data-ttu-id="413e4-115">MLLP トランスポートのプロパティ ダイアログ ボックスで、次の操作を行うし、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="413e4-115">In the MLLP Transport Properties dialog box, do the following actions and then click **OK**.</span></span>  
  
    |<span data-ttu-id="413e4-116">プロパティ</span><span class="sxs-lookup"><span data-stu-id="413e4-116">Use this</span></span>|<span data-ttu-id="413e4-117">目的</span><span class="sxs-lookup"><span data-stu-id="413e4-117">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="413e4-118">**接続名**</span><span class="sxs-lookup"><span data-stu-id="413e4-118">**Connection Name**</span></span>|<span data-ttu-id="413e4-119">型**1WaySend**です。</span><span class="sxs-lookup"><span data-stu-id="413e4-119">Type **1WaySend**.</span></span>|  
    |<span data-ttu-id="413e4-120">**ホスト**</span><span class="sxs-lookup"><span data-stu-id="413e4-120">**Host**</span></span>|<span data-ttu-id="413e4-121">型**localhost**です。</span><span class="sxs-lookup"><span data-stu-id="413e4-121">Type **localhost**.</span></span>|  
    |<span data-ttu-id="413e4-122">**[ポート]**</span><span class="sxs-lookup"><span data-stu-id="413e4-122">**Port**</span></span>|<span data-ttu-id="413e4-123">型**14000**です。</span><span class="sxs-lookup"><span data-stu-id="413e4-123">Type **14000**.</span></span>|  
  
4.  <span data-ttu-id="413e4-124">送信ポートのプロパティ] ダイアログ ボックスの**送信パイプライン**[ **BTAHL72XPipelines.BTAHL72XSendPipeline**です。</span><span class="sxs-lookup"><span data-stu-id="413e4-124">In the Send Port Properties dialog box, for **Send Pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span></span>  
  
5.  <span data-ttu-id="413e4-125">左のペインで選択**フィルター**、し、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="413e4-125">In the left pane, select **Filters**, and then do the following:</span></span>  
  
    |<span data-ttu-id="413e4-126">プロパティ</span><span class="sxs-lookup"><span data-stu-id="413e4-126">Use this</span></span>|<span data-ttu-id="413e4-127">目的</span><span class="sxs-lookup"><span data-stu-id="413e4-127">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="413e4-128">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="413e4-128">**Property**</span></span>|<span data-ttu-id="413e4-129">選択**BTS です。ReceivePortName**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="413e4-129">Select **BTS.ReceivePortName** from the drop-down list.</span></span>|  
    |<span data-ttu-id="413e4-130">**演算子**</span><span class="sxs-lookup"><span data-stu-id="413e4-130">**Operator**</span></span>|<span data-ttu-id="413e4-131">選択 **==** ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="413e4-131">Select **==** from the drop-down list.</span></span>|  
    |<span data-ttu-id="413e4-132">**値**</span><span class="sxs-lookup"><span data-stu-id="413e4-132">**Value**</span></span>|<span data-ttu-id="413e4-133">型**Tutorial_1WayReceive**です。</span><span class="sxs-lookup"><span data-stu-id="413e4-133">Type **Tutorial_1WayReceive**.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="413e4-134">ポートのメッセージ 1WayReceive で指定されたポートをリッスンします。</span><span class="sxs-lookup"><span data-stu-id="413e4-134">The port will listen to the port specified in 1WayReceive for any messages.</span></span>  
  
6.  <span data-ttu-id="413e4-135">をクリックして**適用**、クリックして**[ok] です。**</span><span class="sxs-lookup"><span data-stu-id="413e4-135">Click **Apply**, and then click **OK.**</span></span>  
  
7.  <span data-ttu-id="413e4-136">管理コンソールで、をクリックして**送信ポート**を右クリックして**Tutorial_MllpSend**、クリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="413e4-136">In the Administration Console, click **Send Ports**, right-click **Tutorial_MllpSend**, and then click **Start**.</span></span>  
  
 <span data-ttu-id="413e4-137">進みます[手順 8: パーティ情報を構成する](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information.md)です。</span><span class="sxs-lookup"><span data-stu-id="413e4-137">Proceed to [Step 8: Configure Party Information](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information.md).</span></span>