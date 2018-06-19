---
title: '手順 7: が応答メッセージを配信する送信ポートを作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, send ports
ms.assetid: 5edaefb6-72f2-4317-9477-f3a0d0027e0c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1260772f3b3df5f0dea96b0aa66023e107b9aa6c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207082"
---
# <a name="step-7-create-a-send-port-to-deliver-response-messages"></a><span data-ttu-id="19a2c-102">手順 7: 応答メッセージを配信する送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="19a2c-102">Step 7: Create a Send Port to Deliver Response Messages</span></span>
<span data-ttu-id="19a2c-103">この手順で、クエリに応答を返す、受付、放電、および転送 (ADT) を提供する送信ポートを作成するシステムです。</span><span class="sxs-lookup"><span data-stu-id="19a2c-103">In this step, you create the send port to deliver the query responses back to the Admissions, Discharge, and Transfer (ADT) system.</span></span>  
  
### <a name="to-create-the-adtsend-send-port"></a><span data-ttu-id="19a2c-104">ADT_Send 送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="19a2c-104">To create the ADT_Send send port</span></span>  
  
1.  <span data-ttu-id="19a2c-105">BizTalk Server 管理コンソールで、右クリック**送信ポート**、指す**新規**、し、**静的な一方向送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="19a2c-105">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then select **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="19a2c-106">[送信ポートのプロパティ] ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="19a2c-106">In the Send Port Properties dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="19a2c-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="19a2c-107">Use this</span></span>|<span data-ttu-id="19a2c-108">目的</span><span class="sxs-lookup"><span data-stu-id="19a2c-108">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="19a2c-109">**名前**</span><span class="sxs-lookup"><span data-stu-id="19a2c-109">**Name**</span></span>|<span data-ttu-id="19a2c-110">型**ADT_Send**です。</span><span class="sxs-lookup"><span data-stu-id="19a2c-110">Type **ADT_Send**.</span></span>|  
    |<span data-ttu-id="19a2c-111">**トランスポートの種類**</span><span class="sxs-lookup"><span data-stu-id="19a2c-111">**Transport type**</span></span>|<span data-ttu-id="19a2c-112">選択**MLLP**です。</span><span class="sxs-lookup"><span data-stu-id="19a2c-112">Select **MLLP**.</span></span>|  
    |<span data-ttu-id="19a2c-113">**構成**</span><span class="sxs-lookup"><span data-stu-id="19a2c-113">**Configure**</span></span>|<span data-ttu-id="19a2c-114">クリックして、**構成**の右側にあるボタン**型**です。</span><span class="sxs-lookup"><span data-stu-id="19a2c-114">Click the **Configure** button to the right of **Type**.</span></span>|  
  
3.  <span data-ttu-id="19a2c-115">MLLP トランスポートのプロパティ ダイアログ ボックスで、次の情報を入力し、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="19a2c-115">In the MLLP Transport Properties dialog box, enter the following information, and then click **OK**.</span></span>  
  
    |<span data-ttu-id="19a2c-116">プロパティ</span><span class="sxs-lookup"><span data-stu-id="19a2c-116">Use this</span></span>|<span data-ttu-id="19a2c-117">目的</span><span class="sxs-lookup"><span data-stu-id="19a2c-117">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="19a2c-118">**接続名**</span><span class="sxs-lookup"><span data-stu-id="19a2c-118">**Connection Name**</span></span>|<span data-ttu-id="19a2c-119">型**ADT_SendMLLP**です。</span><span class="sxs-lookup"><span data-stu-id="19a2c-119">Type **ADT_SendMLLP**.</span></span>|  
    |<span data-ttu-id="19a2c-120">**ホスト**</span><span class="sxs-lookup"><span data-stu-id="19a2c-120">**Host**</span></span>|<span data-ttu-id="19a2c-121">型**localhost**です。</span><span class="sxs-lookup"><span data-stu-id="19a2c-121">Type **localhost**.</span></span>|  
    |<span data-ttu-id="19a2c-122">**[ポート]**</span><span class="sxs-lookup"><span data-stu-id="19a2c-122">**Port**</span></span>|<span data-ttu-id="19a2c-123">型**25000**です。</span><span class="sxs-lookup"><span data-stu-id="19a2c-123">Type **25000**.</span></span>|  
  
4.  <span data-ttu-id="19a2c-124">送信ポートのプロパティ] ダイアログ ボックスの**送信パイプライン**[ **BTAHL72XPipelines.BTAHL72XSendPipeline**です。</span><span class="sxs-lookup"><span data-stu-id="19a2c-124">In the Send Port Properties dialog box, for **Send Pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span></span>  
  
5.  <span data-ttu-id="19a2c-125">コンソール ツリーでクリックして**フィルター**、し、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="19a2c-125">In the Console Tree, click **Filters**, and then do the following:</span></span>  
  
    |<span data-ttu-id="19a2c-126">プロパティ</span><span class="sxs-lookup"><span data-stu-id="19a2c-126">Use this</span></span>|<span data-ttu-id="19a2c-127">目的</span><span class="sxs-lookup"><span data-stu-id="19a2c-127">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="19a2c-128">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="19a2c-128">**Property**</span></span>|<span data-ttu-id="19a2c-129">選択**BTS です。MessageType**です。</span><span class="sxs-lookup"><span data-stu-id="19a2c-129">Select **BTS.MessageType**.</span></span>|  
    |<span data-ttu-id="19a2c-130">**演算子**</span><span class="sxs-lookup"><span data-stu-id="19a2c-130">**Operator**</span></span>|<span data-ttu-id="19a2c-131">選択 **==** ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="19a2c-131">Select **==** from the drop-down list.</span></span>|  
    |<span data-ttu-id="19a2c-132">**値**</span><span class="sxs-lookup"><span data-stu-id="19a2c-132">**Value**</span></span>|<span data-ttu-id="19a2c-133">型**http://microsoft.com/HealthCare/HL7/2X#DSR_Q01_24_GLO_DEF**です。</span><span class="sxs-lookup"><span data-stu-id="19a2c-133">Type **http://microsoft.com/HealthCare/HL7/2X#DSR_Q01_24_GLO_DEF**.</span></span>|  
    |<span data-ttu-id="19a2c-134">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="19a2c-134">**Group By**</span></span>|<span data-ttu-id="19a2c-135">選択**AND**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="19a2c-135">Select **AND** from the drop-down list.</span></span>|  
    |<span data-ttu-id="19a2c-136">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="19a2c-136">**Property**</span></span>|<span data-ttu-id="19a2c-137">最初のプロパティでは、下の空のボックスをクリックし、 **BTAHL7Schemas.MSH5_1**です。</span><span class="sxs-lookup"><span data-stu-id="19a2c-137">Under the first property, click the blank box, and then select **BTAHL7Schemas.MSH5_1**.</span></span>|  
    |<span data-ttu-id="19a2c-138">**演算子**</span><span class="sxs-lookup"><span data-stu-id="19a2c-138">**Operator**</span></span>|<span data-ttu-id="19a2c-139">選択 **==** ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="19a2c-139">Select **==** from the drop-down list.</span></span>|  
    |<span data-ttu-id="19a2c-140">**値**</span><span class="sxs-lookup"><span data-stu-id="19a2c-140">**Value**</span></span>|<span data-ttu-id="19a2c-141">型**ADT**です。</span><span class="sxs-lookup"><span data-stu-id="19a2c-141">Type **ADT**.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="19a2c-142">最初のフィルターは、送信ポートのみ DSR に準拠したメッセージを選択することを示す ^ 手順 3 a. で作成した Q01 スキーマです。</span><span class="sxs-lookup"><span data-stu-id="19a2c-142">The first filter specifies that the send port only selects messages conforming to the DSR^Q01 schema you created in step 3A.</span></span> <span data-ttu-id="19a2c-143">2 番目のフィルターを指定する変換先、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]インターフェイス エンジンは、これらのメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="19a2c-143">The second filter specifies the destination to which the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine sends these messages.</span></span>  
  
6.  <span data-ttu-id="19a2c-144">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19a2c-144">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="19a2c-145">管理コンソールで、をクリックして**送信ポート**を右クリックして**ADT_Send**、クリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="19a2c-145">In the Administration Console, click **Send Ports**, right-click **ADT_Send**, and then click **Start**.</span></span>  
  
 <span data-ttu-id="19a2c-146">進みます[手順 8: パーティ情報を構成する](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information-hl7-main.md)です。</span><span class="sxs-lookup"><span data-stu-id="19a2c-146">Proceed to [Step 8: Configure Party Information](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information-hl7-main.md).</span></span>