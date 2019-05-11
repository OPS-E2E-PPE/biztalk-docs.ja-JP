---
title: A4SWIFT 送信ポートを作成する |Microsoft Docs
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
ms.assetid: d1ee18f8-a6aa-4cd5-9e65-fb2e0fa2d0c2
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73a6b90f5b0fb6dcd3075c6ea1b0dc22e05934de
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378503"
---
# <a name="creating-an-a4swift-send-port"></a><span data-ttu-id="97150-102">A4SWIFT 送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="97150-102">Creating an A4SWIFT Send Port</span></span>
<span data-ttu-id="97150-103">有効にする送信ポートを作成する必要があります[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]に次の図に示すように、SWIFT のネットワークにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="97150-103">You must create a send port to enable [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] to send a message to the SWIFT network, as shown in the following figure.</span></span> <span data-ttu-id="97150-104">この送信ポートは、送信ファイル、フォルダーにフラット ファイル メッセージが送信されます。</span><span class="sxs-lookup"><span data-stu-id="97150-104">This send port will send flat file messages to an outbound file folder.</span></span> <span data-ttu-id="97150-105">この送信ポートは、Message Repair and New Submission の機能と連動する設計されています。</span><span class="sxs-lookup"><span data-stu-id="97150-105">This send port is designed to work with the Message Repair and New Submission feature.</span></span>  
  
 <span data-ttu-id="97150-106">![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-send-port-configuration.gif "A4SWIFT_Send_Port_Configuration")</span><span class="sxs-lookup"><span data-stu-id="97150-106">![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-send-port-configuration.gif "A4SWIFT_Send_Port_Configuration")</span></span>  
  
 <span data-ttu-id="97150-107">**まとめ**</span><span class="sxs-lookup"><span data-stu-id="97150-107">**Summary**</span></span>  
  
 <span data-ttu-id="97150-108">作成し、次のプロパティおよびコンポーネントで静的な一方向送信ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="97150-108">Create and start a static one-way send port with the following properties and components:</span></span>  
  
|<span data-ttu-id="97150-109">プロパティ/コンポーネント</span><span class="sxs-lookup"><span data-stu-id="97150-109">Property/Component</span></span>|<span data-ttu-id="97150-110">設定</span><span class="sxs-lookup"><span data-stu-id="97150-110">Setting</span></span>|  
|-------------------------|-------------|  
|<span data-ttu-id="97150-111">送信ポート</span><span class="sxs-lookup"><span data-stu-id="97150-111">Send port</span></span>|<span data-ttu-id="97150-112">静的な一方向ポート</span><span class="sxs-lookup"><span data-stu-id="97150-112">Static one-way port</span></span>|  
|<span data-ttu-id="97150-113">トランスポートの種類</span><span class="sxs-lookup"><span data-stu-id="97150-113">Transport type</span></span>|<span data-ttu-id="97150-114">FILE</span><span class="sxs-lookup"><span data-stu-id="97150-114">FILE</span></span>|  
|<span data-ttu-id="97150-115">コピー先フォルダー (アドレス URI)</span><span class="sxs-lookup"><span data-stu-id="97150-115">Destination folder (Address URI)</span></span>|<span data-ttu-id="97150-116">メッセージを送信するフォルダーの名前</span><span class="sxs-lookup"><span data-stu-id="97150-116">Name of the folder that you want to send messages from</span></span>|  
|<span data-ttu-id="97150-117">ファイル名 (URI アドレス)</span><span class="sxs-lookup"><span data-stu-id="97150-117">File Name (Address URI)</span></span>|<span data-ttu-id="97150-118">%MessageID%.txt</span><span class="sxs-lookup"><span data-stu-id="97150-118">%MessageID%.txt</span></span>|  
|<span data-ttu-id="97150-119">フィルター</span><span class="sxs-lookup"><span data-stu-id="97150-119">Filters</span></span>|<span data-ttu-id="97150-120">次の表で説明されていると</span><span class="sxs-lookup"><span data-stu-id="97150-120">As described in the table below</span></span>|  
  
### <a name="to-add-the-sent-port"></a><span data-ttu-id="97150-121">送信ポートを追加するには</span><span class="sxs-lookup"><span data-stu-id="97150-121">To add the sent port</span></span>  
  
1.  <span data-ttu-id="97150-122">右クリックし、BizTalk Server 管理コンソールで**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート**。</span><span class="sxs-lookup"><span data-stu-id="97150-122">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="97150-123">送信ポートのプロパティ ダイアログ ボックスでの**名前**ボックスに、送信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="97150-123">In the Send Port Properties dialog box, in the **Name** box, type a name for the send port.</span></span>  
  
3.  <span data-ttu-id="97150-124">**トランスポート**セクションの**型**ボックス、ドロップダウン リストをクリックし、**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="97150-124">In the **Transport** section, for the **Type** box, click the drop-down list, and then select **FILE**.</span></span>  
  
4.  <span data-ttu-id="97150-125">をクリックして、**構成**型のドロップダウン リストの右側にボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="97150-125">Click the **Configure** button to the right of the Type drop-down list.</span></span>  
  
5.  <span data-ttu-id="97150-126">[FILE トランスポートのプロパティ] ダイアログ ボックスで、**参照**します。</span><span class="sxs-lookup"><span data-stu-id="97150-126">In the FILE Transport Properties dialog box, click **Browse**.</span></span>  
  
6.  <span data-ttu-id="97150-127">フォルダーの参照 ダイアログ ボックスからメッセージを送信するフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="97150-127">In the Browse For Folder dialog box, move to the folder that you want to send messages from.</span></span> <span data-ttu-id="97150-128">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97150-128">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="97150-129">このフォルダーが存在しない場合を使用してそれを作成、**フォルダの新規**コマンド。</span><span class="sxs-lookup"><span data-stu-id="97150-129">If this folder does not exist, you can create it using the **Make New Folder** command.</span></span>  
  
7.  <span data-ttu-id="97150-130">**ファイル名**ボックスに「 **%MessageID%.txt**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="97150-130">In the **File name** box, type **%MessageID%.txt**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="97150-131">**送信ポートのプロパティ** ダイアログ ボックスで、ドロップダウン リストをクリックして、**送信パイプライン**ボックスし、カスタム送信パイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="97150-131">In the **Send Port Properties** dialog box, click the drop-down list for the **Send pipeline** box, and then select your custom send pipeline.</span></span>  
  
9. <span data-ttu-id="97150-132">左側のウィンドウで次のようにクリックします。**フィルター**、し、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="97150-132">In the left pane, click **Filters**, and then do the following:</span></span>  
  
    |<span data-ttu-id="97150-133">プロパティ</span><span class="sxs-lookup"><span data-stu-id="97150-133">Use this</span></span>|<span data-ttu-id="97150-134">目的</span><span class="sxs-lookup"><span data-stu-id="97150-134">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="97150-135">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="97150-135">**Property**</span></span>|<span data-ttu-id="97150-136">選択**BTS します。操作**します。</span><span class="sxs-lookup"><span data-stu-id="97150-136">Select **BTS.Operation**.</span></span>|  
    |<span data-ttu-id="97150-137">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="97150-137">**Operator**</span></span>|<span data-ttu-id="97150-138">選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="97150-138">Select **==**.</span></span>|  
    |<span data-ttu-id="97150-139">**[値]**</span><span class="sxs-lookup"><span data-stu-id="97150-139">**Value**</span></span>|<span data-ttu-id="97150-140">型**A4SWIFT_MRSRCompleted**します。</span><span class="sxs-lookup"><span data-stu-id="97150-140">Type **A4SWIFT_MRSRCompleted**.</span></span>|  
    |<span data-ttu-id="97150-141">**[グループ]**</span><span class="sxs-lookup"><span data-stu-id="97150-141">**Group**</span></span>|<span data-ttu-id="97150-142">選択**またはします。**</span><span class="sxs-lookup"><span data-stu-id="97150-142">Select **Or.**</span></span>|  
    |<span data-ttu-id="97150-143">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="97150-143">**Property**</span></span>|<span data-ttu-id="97150-144">選択**BTS します。操作**します。</span><span class="sxs-lookup"><span data-stu-id="97150-144">Select **BTS.Operation**.</span></span>|  
    |<span data-ttu-id="97150-145">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="97150-145">**Operator**</span></span>|<span data-ttu-id="97150-146">選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="97150-146">Select **==**.</span></span>|  
    |<span data-ttu-id="97150-147">**[値]**</span><span class="sxs-lookup"><span data-stu-id="97150-147">**Value**</span></span>|<span data-ttu-id="97150-148">型**A4SWIFT_MRSRFailed**します。</span><span class="sxs-lookup"><span data-stu-id="97150-148">Type **A4SWIFT_MRSRFailed**.</span></span>|  
    |<span data-ttu-id="97150-149">**[グループ]**</span><span class="sxs-lookup"><span data-stu-id="97150-149">**Group**</span></span>|<span data-ttu-id="97150-150">選択**または**します。</span><span class="sxs-lookup"><span data-stu-id="97150-150">Select **Or**.</span></span>|  
    |<span data-ttu-id="97150-151">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="97150-151">**Property**</span></span>|<span data-ttu-id="97150-152">選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**します。</span><span class="sxs-lookup"><span data-stu-id="97150-152">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**.</span></span>|  
    |<span data-ttu-id="97150-153">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="97150-153">**Operator**</span></span>|<span data-ttu-id="97150-154">選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="97150-154">Select **==**.</span></span>|  
    |<span data-ttu-id="97150-155">**[値]**</span><span class="sxs-lookup"><span data-stu-id="97150-155">**Value**</span></span>|<span data-ttu-id="97150-156">型**True**します。</span><span class="sxs-lookup"><span data-stu-id="97150-156">Type **True**.</span></span>|  
  
10. <span data-ttu-id="97150-157">クリックして**適用**、順にクリックします**ok をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="97150-157">Click **Apply**, and then click **OK.**</span></span>  
  
11. <span data-ttu-id="97150-158">**送信ポート**ウィンドウで、送信ポートを右クリックし、順にクリックします**開始**します。</span><span class="sxs-lookup"><span data-stu-id="97150-158">In the **Send Ports** pane, right-click the send port, and then click **Start**.</span></span>