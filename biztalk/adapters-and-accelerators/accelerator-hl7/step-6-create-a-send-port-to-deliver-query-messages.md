---
title: '手順 6: クエリ メッセージを配信する送信ポートの作成 |Microsoft ドキュメント'
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
ms.openlocfilehash: 43c373940d8ab1e847b66527d83ef24e952d84d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206802"
---
# <a name="step-6-create-a-send-port-to-deliver-query-messages"></a><span data-ttu-id="6d240-102">手順 6: クエリ メッセージを配信する送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="6d240-102">Step 6: Create a Send Port to Deliver Query Messages</span></span>
<span data-ttu-id="6d240-103">この手順では、着信クエリを配信する送信ポートを作成 (クエリ ^ Q01 メッセージ) 病院情報システム (HIS) にします。</span><span class="sxs-lookup"><span data-stu-id="6d240-103">In this step, you create the send port to deliver the incoming queries (QRY^Q01 messages) to the Hospital Information System (HIS).</span></span>  
  
### <a name="to-create-the-hissend-send-port"></a><span data-ttu-id="6d240-104">HIS_Send 送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="6d240-104">To create the HIS_Send send port</span></span>  
  
1.  <span data-ttu-id="6d240-105">BizTalk Server 管理コンソールで、右クリック**送信ポート**、指す**新規**、し、**静的な一方向送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="6d240-105">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then select **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="6d240-106">[送信ポートのプロパティ] ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6d240-106">In the Send Port Properties dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="6d240-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6d240-107">Use this</span></span>|<span data-ttu-id="6d240-108">目的</span><span class="sxs-lookup"><span data-stu-id="6d240-108">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="6d240-109">**名前**</span><span class="sxs-lookup"><span data-stu-id="6d240-109">**Name**</span></span>|<span data-ttu-id="6d240-110">型**HIS_Send**です。</span><span class="sxs-lookup"><span data-stu-id="6d240-110">Type **HIS_Send**.</span></span>|  
    |<span data-ttu-id="6d240-111">**トランスポートの種類**</span><span class="sxs-lookup"><span data-stu-id="6d240-111">**Transport type**</span></span>|<span data-ttu-id="6d240-112">選択**MLLP**です。</span><span class="sxs-lookup"><span data-stu-id="6d240-112">Select **MLLP**.</span></span>|  
    |<span data-ttu-id="6d240-113">**構成**</span><span class="sxs-lookup"><span data-stu-id="6d240-113">**Configure**</span></span>|<span data-ttu-id="6d240-114">クリックして、**構成**の右側にあるボタン**型**です。</span><span class="sxs-lookup"><span data-stu-id="6d240-114">Click the **Configure** button to the right of **Type**.</span></span>|  
  
3.  <span data-ttu-id="6d240-115">MLLP トランスポートのプロパティ ダイアログ ボックスで、次の情報を入力し、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="6d240-115">In the MLLP Transport Properties dialog box, enter the following information and then click **OK**.</span></span>  
  
    |<span data-ttu-id="6d240-116">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6d240-116">Use this</span></span>|<span data-ttu-id="6d240-117">目的</span><span class="sxs-lookup"><span data-stu-id="6d240-117">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="6d240-118">**接続名**</span><span class="sxs-lookup"><span data-stu-id="6d240-118">**Connection Name**</span></span>|<span data-ttu-id="6d240-119">型**HIS_SendMLLP**です。</span><span class="sxs-lookup"><span data-stu-id="6d240-119">Type **HIS_SendMLLP**.</span></span>|  
    |<span data-ttu-id="6d240-120">**ホスト**</span><span class="sxs-lookup"><span data-stu-id="6d240-120">**Host**</span></span>|<span data-ttu-id="6d240-121">型**localhost**です。</span><span class="sxs-lookup"><span data-stu-id="6d240-121">Type **localhost**.</span></span>|  
    |<span data-ttu-id="6d240-122">**[ポート]**</span><span class="sxs-lookup"><span data-stu-id="6d240-122">**Port**</span></span>|<span data-ttu-id="6d240-123">型**24000**です。</span><span class="sxs-lookup"><span data-stu-id="6d240-123">Type **24000**.</span></span>|  
  
4.  <span data-ttu-id="6d240-124">送信ポートのプロパティ] ダイアログ ボックスの**送信パイプライン**[ **BTAHL72XPipelines.BTAHL72XSendPipeline**です。</span><span class="sxs-lookup"><span data-stu-id="6d240-124">In the Send Port Properties dialog box, for **Send Pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span></span>  
  
5.  <span data-ttu-id="6d240-125">コンソール ツリーでクリックして**フィルター**、し、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6d240-125">In the Console Tree, click **Filters**, and then do the following:</span></span>  
  
    |<span data-ttu-id="6d240-126">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6d240-126">Use this</span></span>|<span data-ttu-id="6d240-127">目的</span><span class="sxs-lookup"><span data-stu-id="6d240-127">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="6d240-128">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="6d240-128">**Property**</span></span>|<span data-ttu-id="6d240-129">**プロパティ** **BTS です。MessageType**です。</span><span class="sxs-lookup"><span data-stu-id="6d240-129">For **Property**, select **BTS.MessageType**.</span></span>|  
    |<span data-ttu-id="6d240-130">**演算子**</span><span class="sxs-lookup"><span data-stu-id="6d240-130">**Operator**</span></span>|<span data-ttu-id="6d240-131">選択 **==** ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="6d240-131">Select **==** from the drop-down list.</span></span>|  
    |<span data-ttu-id="6d240-132">**値**</span><span class="sxs-lookup"><span data-stu-id="6d240-132">**Value**</span></span>|<span data-ttu-id="6d240-133">型**http://microsoft.com/HealthCare/HL7/2X#QRY_Q01_24_GLO_DEF**です。</span><span class="sxs-lookup"><span data-stu-id="6d240-133">Type **http://microsoft.com/HealthCare/HL7/2X#QRY_Q01_24_GLO_DEF**.</span></span>|  
    |<span data-ttu-id="6d240-134">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="6d240-134">**Group By**</span></span>|<span data-ttu-id="6d240-135">選択**AND**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="6d240-135">Select **AND** from the drop-down list.</span></span>|  
    |<span data-ttu-id="6d240-136">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="6d240-136">**Property**</span></span>|<span data-ttu-id="6d240-137">**プロパティ**2 行目に次のように選択します。 **BTAHL7Schemas.MSH5_1**です。</span><span class="sxs-lookup"><span data-stu-id="6d240-137">For **Property** on the second line, select **BTAHL7Schemas.MSH5_1**.</span></span>|  
    |<span data-ttu-id="6d240-138">**演算子**</span><span class="sxs-lookup"><span data-stu-id="6d240-138">**Operator**</span></span>|<span data-ttu-id="6d240-139">選択 **==** ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="6d240-139">Select **==** from the drop-down list.</span></span>|  
    |<span data-ttu-id="6d240-140">**値**</span><span class="sxs-lookup"><span data-stu-id="6d240-140">**Value**</span></span>|<span data-ttu-id="6d240-141">型**HIS**です。</span><span class="sxs-lookup"><span data-stu-id="6d240-141">Type **HIS**.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="6d240-142">最初のフィルターは、送信ポートにのみ、クエリに準拠するメッセージが選択することを示す ^ 手順 3 a. で作成した Q01 スキーマです。</span><span class="sxs-lookup"><span data-stu-id="6d240-142">The first filter specifies that the send port only selects messages conforming to the QRY^Q01 schema you created in step 3A.</span></span> <span data-ttu-id="6d240-143">2 番目のフィルターを指定する変換先、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]インターフェイス エンジンは、これらのメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="6d240-143">The second filter specifies the destination to which the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine sends these messages.</span></span>  
  
6.  <span data-ttu-id="6d240-144">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d240-144">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="6d240-145">管理コンソールで、次のように選択します。**送信ポート**、を右クリック**HIS_Send**、クリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="6d240-145">In the Administration console, select **Send Ports**, right-click **HIS_Send**, and then click **Start**.</span></span>  
  
 <span data-ttu-id="6d240-146">進みます[手順 7: 応答メッセージを配信する送信ポートを作成](../../adapters-and-accelerators/accelerator-hl7/step-7-create-a-send-port-to-deliver-response-messages.md)です。</span><span class="sxs-lookup"><span data-stu-id="6d240-146">Proceed to [Step 7: Create a Send Port to Deliver Response Messages](../../adapters-and-accelerators/accelerator-hl7/step-7-create-a-send-port-to-deliver-response-messages.md).</span></span>