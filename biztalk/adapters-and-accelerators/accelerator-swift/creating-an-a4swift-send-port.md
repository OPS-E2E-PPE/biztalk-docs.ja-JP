---
title: "A4SWIFT 送信ポートの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, send ports
- send ports, creating
ms.assetid: d1ee18f8-a6aa-4cd5-9e65-fb2e0fa2d0c2
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cf24cb99643acc869123450ce14fd5050ee7408
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-an-a4swift-send-port"></a><span data-ttu-id="26d83-102">A4SWIFT 送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="26d83-102">Creating an A4SWIFT Send Port</span></span>
<span data-ttu-id="26d83-103">有効にする送信ポートを作成する必要があります[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]SWIFT ネットワークは、次の図に示すようにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="26d83-103">You must create a send port to enable [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] to send a message to the SWIFT network, as shown in the following figure.</span></span> <span data-ttu-id="26d83-104">この送信ポートは、送信ファイル フォルダーにフラット ファイル メッセージが送信されます。</span><span class="sxs-lookup"><span data-stu-id="26d83-104">This send port will send flat file messages to an outbound file folder.</span></span> <span data-ttu-id="26d83-105">この送信ポートは、Message Repair and New Submission の機能を使用するよう設計されています。</span><span class="sxs-lookup"><span data-stu-id="26d83-105">This send port is designed to work with the Message Repair and New Submission feature.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-send-port-configuration.gif "A4SWIFT_Send_Port_Configuration")  
  
 <span data-ttu-id="26d83-106">**概要**</span><span class="sxs-lookup"><span data-stu-id="26d83-106">**Summary**</span></span>  
  
 <span data-ttu-id="26d83-107">作成し、次のプロパティとコンポーネントの静的な一方向送信ポートを起動します。</span><span class="sxs-lookup"><span data-stu-id="26d83-107">Create and start a static one-way send port with the following properties and components:</span></span>  
  
|<span data-ttu-id="26d83-108">プロパティ/コンポーネント</span><span class="sxs-lookup"><span data-stu-id="26d83-108">Property/Component</span></span>|<span data-ttu-id="26d83-109">設定</span><span class="sxs-lookup"><span data-stu-id="26d83-109">Setting</span></span>|  
|-------------------------|-------------|  
|<span data-ttu-id="26d83-110">送信ポート</span><span class="sxs-lookup"><span data-stu-id="26d83-110">Send port</span></span>|<span data-ttu-id="26d83-111">静的な一方向ポート</span><span class="sxs-lookup"><span data-stu-id="26d83-111">Static one-way port</span></span>|  
|<span data-ttu-id="26d83-112">トランスポートの種類</span><span class="sxs-lookup"><span data-stu-id="26d83-112">Transport type</span></span>|<span data-ttu-id="26d83-113">FILE</span><span class="sxs-lookup"><span data-stu-id="26d83-113">FILE</span></span>|  
|<span data-ttu-id="26d83-114">コピー先フォルダー (アドレス URI)</span><span class="sxs-lookup"><span data-stu-id="26d83-114">Destination folder (Address URI)</span></span>|<span data-ttu-id="26d83-115">メッセージを送信するフォルダーの名前</span><span class="sxs-lookup"><span data-stu-id="26d83-115">Name of the folder that you want to send messages from</span></span>|  
|<span data-ttu-id="26d83-116">ファイル名 (アドレス URI)</span><span class="sxs-lookup"><span data-stu-id="26d83-116">File Name (Address URI)</span></span>|<span data-ttu-id="26d83-117">%MessageID%.txt</span><span class="sxs-lookup"><span data-stu-id="26d83-117">%MessageID%.txt</span></span>|  
|<span data-ttu-id="26d83-118">フィルター</span><span class="sxs-lookup"><span data-stu-id="26d83-118">Filters</span></span>|<span data-ttu-id="26d83-119">次の表の説明に従って</span><span class="sxs-lookup"><span data-stu-id="26d83-119">As described in the table below</span></span>|  
  
### <a name="to-add-the-sent-port"></a><span data-ttu-id="26d83-120">送信ポートを追加するには</span><span class="sxs-lookup"><span data-stu-id="26d83-120">To add the sent port</span></span>  
  
1.  <span data-ttu-id="26d83-121">BizTalk Server 管理コンソールで、右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="26d83-121">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="26d83-122">送信ポートのプロパティ ダイアログ ボックスで、**名前**ボックスで、送信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="26d83-122">In the Send Port Properties dialog box, in the **Name** box, type a name for the send port.</span></span>  
  
3.  <span data-ttu-id="26d83-123">**トランスポート**] セクションの**型**ボックス、ドロップダウン リストをクリックし、[**ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="26d83-123">In the **Transport** section, for the **Type** box, click the drop-down list, and then select **FILE**.</span></span>  
  
4.  <span data-ttu-id="26d83-124">クリックして、**構成**型のドロップダウン リストの右側にあるボタンです。</span><span class="sxs-lookup"><span data-stu-id="26d83-124">Click the **Configure** button to the right of the Type drop-down list.</span></span>  
  
5.  <span data-ttu-id="26d83-125">[FILE トランスポートのプロパティ] ダイアログ ボックスで、**参照**です。</span><span class="sxs-lookup"><span data-stu-id="26d83-125">In the FILE Transport Properties dialog box, click **Browse**.</span></span>  
  
6.  <span data-ttu-id="26d83-126">フォルダーの参照 ダイアログ ボックスからメッセージを送信するフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="26d83-126">In the Browse For Folder dialog box, move to the folder that you want to send messages from.</span></span> <span data-ttu-id="26d83-127">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26d83-127">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="26d83-128">このフォルダーが存在しない場合を使用してそれを作成、**新しいフォルダーの作成**コマンド。</span><span class="sxs-lookup"><span data-stu-id="26d83-128">If this folder does not exist, you can create it using the **Make New Folder** command.</span></span>  
  
7.  <span data-ttu-id="26d83-129">**ファイル名**ボックスに、入力**%MessageID%.txt**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="26d83-129">In the **File name** box, type **%MessageID%.txt**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="26d83-130">**送信ポートのプロパティ** ダイアログ ボックスで、ドロップダウン リストをクリックして、**送信パイプライン**ボックス、およびカスタムの送信パイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="26d83-130">In the **Send Port Properties** dialog box, click the drop-down list for the **Send pipeline** box, and then select your custom send pipeline.</span></span>  
  
9. <span data-ttu-id="26d83-131">左側のウィンドウでをクリックして**フィルター**、し、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="26d83-131">In the left pane, click **Filters**, and then do the following:</span></span>  
  
    |<span data-ttu-id="26d83-132">プロパティ</span><span class="sxs-lookup"><span data-stu-id="26d83-132">Use this</span></span>|<span data-ttu-id="26d83-133">目的</span><span class="sxs-lookup"><span data-stu-id="26d83-133">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="26d83-134">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="26d83-134">**Property**</span></span>|<span data-ttu-id="26d83-135">選択**BTS です。操作**です。</span><span class="sxs-lookup"><span data-stu-id="26d83-135">Select **BTS.Operation**.</span></span>|  
    |<span data-ttu-id="26d83-136">**演算子**</span><span class="sxs-lookup"><span data-stu-id="26d83-136">**Operator**</span></span>|<span data-ttu-id="26d83-137">選択 **==**です。</span><span class="sxs-lookup"><span data-stu-id="26d83-137">Select **==**.</span></span>|  
    |<span data-ttu-id="26d83-138">**値**</span><span class="sxs-lookup"><span data-stu-id="26d83-138">**Value**</span></span>|<span data-ttu-id="26d83-139">型**A4SWIFT_MRSRCompleted**です。</span><span class="sxs-lookup"><span data-stu-id="26d83-139">Type **A4SWIFT_MRSRCompleted**.</span></span>|  
    |<span data-ttu-id="26d83-140">**[グループ]**</span><span class="sxs-lookup"><span data-stu-id="26d83-140">**Group**</span></span>|<span data-ttu-id="26d83-141">選択**またはします。**</span><span class="sxs-lookup"><span data-stu-id="26d83-141">Select **Or.**</span></span>|  
    |<span data-ttu-id="26d83-142">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="26d83-142">**Property**</span></span>|<span data-ttu-id="26d83-143">選択**BTS です。操作**です。</span><span class="sxs-lookup"><span data-stu-id="26d83-143">Select **BTS.Operation**.</span></span>|  
    |<span data-ttu-id="26d83-144">**演算子**</span><span class="sxs-lookup"><span data-stu-id="26d83-144">**Operator**</span></span>|<span data-ttu-id="26d83-145">選択 **==**です。</span><span class="sxs-lookup"><span data-stu-id="26d83-145">Select **==**.</span></span>|  
    |<span data-ttu-id="26d83-146">**値**</span><span class="sxs-lookup"><span data-stu-id="26d83-146">**Value**</span></span>|<span data-ttu-id="26d83-147">型**A4SWIFT_MRSRFailed**です。</span><span class="sxs-lookup"><span data-stu-id="26d83-147">Type **A4SWIFT_MRSRFailed**.</span></span>|  
    |<span data-ttu-id="26d83-148">**[グループ]**</span><span class="sxs-lookup"><span data-stu-id="26d83-148">**Group**</span></span>|<span data-ttu-id="26d83-149">選択**または**です。</span><span class="sxs-lookup"><span data-stu-id="26d83-149">Select **Or**.</span></span>|  
    |<span data-ttu-id="26d83-150">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="26d83-150">**Property**</span></span>|<span data-ttu-id="26d83-151">選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**です。</span><span class="sxs-lookup"><span data-stu-id="26d83-151">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**.</span></span>|  
    |<span data-ttu-id="26d83-152">**演算子**</span><span class="sxs-lookup"><span data-stu-id="26d83-152">**Operator**</span></span>|<span data-ttu-id="26d83-153">選択 **==**です。</span><span class="sxs-lookup"><span data-stu-id="26d83-153">Select **==**.</span></span>|  
    |<span data-ttu-id="26d83-154">**値**</span><span class="sxs-lookup"><span data-stu-id="26d83-154">**Value**</span></span>|<span data-ttu-id="26d83-155">型**True**です。</span><span class="sxs-lookup"><span data-stu-id="26d83-155">Type **True**.</span></span>|  
  
10. <span data-ttu-id="26d83-156">をクリックして**適用**、クリックして**[ok] です。**</span><span class="sxs-lookup"><span data-stu-id="26d83-156">Click **Apply**, and then click **OK.**</span></span>  
  
11. <span data-ttu-id="26d83-157">**送信ポート** ウィンドウでは、送信ポートを右クリックし、をクリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="26d83-157">In the **Send Ports** pane, right-click the send port, and then click **Start**.</span></span>