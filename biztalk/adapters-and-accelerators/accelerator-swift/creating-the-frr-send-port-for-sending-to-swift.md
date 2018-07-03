---
title: SWIFT に送信するための FRR 送信ポートを作成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, send ports
- send ports, creating
- FRR, creating send ports
ms.assetid: 1ad766db-d1da-437a-a520-a3b04f0695c4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1583072986eba20b5a0202e6973a5c08095aab01
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972323"
---
# <a name="creating-the-frr-send-port-for-sending-to-swift"></a><span data-ttu-id="1f038-102">SWIFT に送信するための FRR 送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f038-102">Creating the FRR Send Port for Sending to SWIFT</span></span>
<span data-ttu-id="1f038-103">FIN Response Reconciliation を実行するのからのメッセージを送信する送信ポートを作成する必要があります[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]SWIFT ネットワークにします。</span><span class="sxs-lookup"><span data-stu-id="1f038-103">To perform FIN Response Reconciliation, you need to create a send port that sends a message from [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] to the SWIFT Network.</span></span>  

 <span data-ttu-id="1f038-104">**概要**</span><span class="sxs-lookup"><span data-stu-id="1f038-104">**Summary**</span></span>  

 <span data-ttu-id="1f038-105">次のプロパティおよびコンポーネントで、送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f038-105">Create a send port with the following properties and components:</span></span>  


|     <span data-ttu-id="1f038-106">プロパティ/コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1f038-106">Property/Component</span></span>      |                                                               <span data-ttu-id="1f038-107">設定</span><span class="sxs-lookup"><span data-stu-id="1f038-107">Setting</span></span>                                                                |
|-----------------------------|--------------------------------------------------------------------------------------------------------------------------------------|
|          <span data-ttu-id="1f038-108">送信ポート</span><span class="sxs-lookup"><span data-stu-id="1f038-108">Send port</span></span>          |                                                         <span data-ttu-id="1f038-109">静的な一方向ポート</span><span class="sxs-lookup"><span data-stu-id="1f038-109">Static one-way port</span></span>                                                          |
|       <span data-ttu-id="1f038-110">トランスポートの種類</span><span class="sxs-lookup"><span data-stu-id="1f038-110">Transport type</span></span>        |                                                               <span data-ttu-id="1f038-111">MQSeries</span><span class="sxs-lookup"><span data-stu-id="1f038-111">MQSeries</span></span>                                                               |
| <span data-ttu-id="1f038-112">キュー定義 (MQSeries)</span><span class="sxs-lookup"><span data-stu-id="1f038-112">Queue Definition (MQSeries)</span></span> |                                                 <span data-ttu-id="1f038-113">MQSeries server キュー マネージャー キュー</span><span class="sxs-lookup"><span data-stu-id="1f038-113">MQSeries server Queue manager Queue</span></span>                                                  |
|        <span data-ttu-id="1f038-114">[送信パイプライン]</span><span class="sxs-lookup"><span data-stu-id="1f038-114">Send pipeline</span></span>        | <span data-ttu-id="1f038-115">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FRR 用に作成した送信パイプライン</span><span class="sxs-lookup"><span data-stu-id="1f038-115">The [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] send pipeline that you created for FRR</span></span> |
|           <span data-ttu-id="1f038-116">フィルター</span><span class="sxs-lookup"><span data-stu-id="1f038-116">Filters</span></span>           |                                                     <span data-ttu-id="1f038-117">次の表に示すように</span><span class="sxs-lookup"><span data-stu-id="1f038-117">As shown in the table below</span></span>                                                      |

### <a name="to-add-a-custom-send-port-for-sending-to-swift"></a><span data-ttu-id="1f038-118">SWIFT に送信するためのカスタムの送信ポートを追加するには</span><span class="sxs-lookup"><span data-stu-id="1f038-118">To add a custom send port for sending to SWIFT</span></span>  

1. <span data-ttu-id="1f038-119">BizTalk Server 管理コンソールで、右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的 1 waySend ポート**します。</span><span class="sxs-lookup"><span data-stu-id="1f038-119">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-waySend Port**.</span></span>  

2. <span data-ttu-id="1f038-120">送信ポートのプロパティ ダイアログ ボックスでの**名前**ボックスに、FRRSWIFTSendPort など、送信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="1f038-120">In the Send Port Properties dialog box, in the **Name** box, type a name for the send port, such as FRRSWIFTSendPort.</span></span>  

3. <span data-ttu-id="1f038-121">**型**、 **MQSeries**します。</span><span class="sxs-lookup"><span data-stu-id="1f038-121">For **Type**, select **MQSeries**.</span></span>  

4. <span data-ttu-id="1f038-122">クリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="1f038-122">Click **Configure**.</span></span>  

5. <span data-ttu-id="1f038-123">[MQSeries トランスポートのプロパティ] ダイアログ ボックスで、**キュー定義**、省略記号 () ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f038-123">In the MQSeries Transport Properties dialog box, click **Queue Definition**, and then click the ellipsis () button.</span></span>  

6. <span data-ttu-id="1f038-124">キュー定義 ダイアログ ボックスで、MQSeries サーバー、キュー マネージャー、およびキューを入力します。</span><span class="sxs-lookup"><span data-stu-id="1f038-124">In the Queue Definition dialog box, enter the MQSeries server, queue manager, and queue.</span></span> <span data-ttu-id="1f038-125">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f038-125">Click **OK**.</span></span>  

7. <span data-ttu-id="1f038-126">MQSeries トランスポートのプロパティ ダイアログ ボックスでプロパティが必要なであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f038-126">In the MQSeries Transport Properties dialog box, verify that the properties are as needed.</span></span> <span data-ttu-id="1f038-127">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f038-127">Click **OK**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="1f038-128">MQSeries トランスポートのプロパティの詳細については、MQSeries のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f038-128">For more information about MQSeries transport properties, see the MQSeries documentation.</span></span>  

8. <span data-ttu-id="1f038-129">送信ポートのプロパティ ダイアログ ボックスでの**送信ハンドラー**、biztalkserverapplication が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f038-129">In the Send Port Properties dialog box, for **Send handler**, verify that BizTalkServerApplication is selected.</span></span>  

9. <span data-ttu-id="1f038-130">**送信パイプライン**を選択、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FRR 用に作成した送信パイプラインです。</span><span class="sxs-lookup"><span data-stu-id="1f038-130">For **Send Pipeline**, select the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] send pipeline that you created for FRR.</span></span>  

10. <span data-ttu-id="1f038-131">クリックして**フィルター**左側のウィンドウで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1f038-131">Click **Filters** in the left pane, and then do the following:</span></span>  


    |   <span data-ttu-id="1f038-132">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1f038-132">Use this</span></span>   |                            <span data-ttu-id="1f038-133">目的</span><span class="sxs-lookup"><span data-stu-id="1f038-133">To do this</span></span>                             |
    |--------------|-------------------------------------------------------------------|
    | <span data-ttu-id="1f038-134">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="1f038-134">**Property**</span></span> |  <span data-ttu-id="1f038-135">選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**します。</span><span class="sxs-lookup"><span data-stu-id="1f038-135">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**.</span></span>  |
    | <span data-ttu-id="1f038-136">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="1f038-136">**Operator**</span></span> |                          <span data-ttu-id="1f038-137">選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="1f038-137">Select **==**.</span></span>                           |
    |  <span data-ttu-id="1f038-138">**[値]**</span><span class="sxs-lookup"><span data-stu-id="1f038-138">**Value**</span></span>   |                          <span data-ttu-id="1f038-139">型**False**します。</span><span class="sxs-lookup"><span data-stu-id="1f038-139">Type **False**.</span></span>                          |
    |  <span data-ttu-id="1f038-140">**[グループ]**</span><span class="sxs-lookup"><span data-stu-id="1f038-140">**Group**</span></span>   |                          <span data-ttu-id="1f038-141">選択**と**します。</span><span class="sxs-lookup"><span data-stu-id="1f038-141">Select **And**.</span></span>                          |
    | <span data-ttu-id="1f038-142">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="1f038-142">**Property**</span></span> | <span data-ttu-id="1f038-143">型**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SwiftBound**します。</span><span class="sxs-lookup"><span data-stu-id="1f038-143">Type **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SwiftBound**.</span></span> |
    | <span data-ttu-id="1f038-144">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="1f038-144">**Operator**</span></span> |                          <span data-ttu-id="1f038-145">選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="1f038-145">Select **==**.</span></span>                           |
    |  <span data-ttu-id="1f038-146">**[値]**</span><span class="sxs-lookup"><span data-stu-id="1f038-146">**Value**</span></span>   |                          <span data-ttu-id="1f038-147">型**True**します。</span><span class="sxs-lookup"><span data-stu-id="1f038-147">Type **True**.</span></span>                           |


11. <span data-ttu-id="1f038-148">クリックして**適用**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="1f038-148">Click **Apply**, and then click **OK**.</span></span>  

12. <span data-ttu-id="1f038-149">送信ポートを右クリックし、**開始**します。</span><span class="sxs-lookup"><span data-stu-id="1f038-149">Right-click the send port, and then click **Start**.</span></span>
