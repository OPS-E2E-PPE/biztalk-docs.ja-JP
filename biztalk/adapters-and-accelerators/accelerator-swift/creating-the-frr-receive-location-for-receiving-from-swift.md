---
title: SWIFT からの受信用の受信場所の作成、FRR |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, creating
- creating, receive locations
- FRR, creating receive locations
ms.assetid: e10857f4-21cb-4c09-8eed-cb6e9b0a0aa9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1912187c299e959c1a4f56c6650201efc5b37246
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378403"
---
# <a name="creating-the-frr-receive-location-for-receiving-from-swift"></a><span data-ttu-id="573ce-102">SWIFT からの受信用の受信場所の FRR を作成します。</span><span class="sxs-lookup"><span data-stu-id="573ce-102">Creating the FRR Receive Location for Receiving from SWIFT</span></span>
<span data-ttu-id="573ce-103">FIN Response Reconciliation を実行するには、A4SWIFT に SWIFT ネットワークからメッセージを受信する受信場所を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="573ce-103">To perform FIN Response Reconciliation, you need to create a receive location that receives a message from the SWIFT Network into A4SWIFT.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="573ce-104">お勧めを設定するには、2 つの受信 SAA からメッセージを受信するための場所: パン/Nan と 1 つの他のすべてのメッセージの受信を受信する 1 つ。</span><span class="sxs-lookup"><span data-stu-id="573ce-104">It is advisable to set up two receive locations for receiving messages from SAA: one to receive PAN/NANs and one to receive all other messages.</span></span> <span data-ttu-id="573ce-105">設定する 2 つの受信場所、SAA で 2 つの MQSeries キューからメッセージを受信する必要があります。 パン/Nan とその他のすべてのメッセージの種類のいずれかのいずれか。</span><span class="sxs-lookup"><span data-stu-id="573ce-105">To set up the two receive locations, you must receive messages from two MQSeries queues at SAA: one for PAN/NANs and one for all other message types.</span></span>  
  
 <span data-ttu-id="573ce-106">**まとめ**</span><span class="sxs-lookup"><span data-stu-id="573ce-106">**Summary**</span></span>  
  
 <span data-ttu-id="573ce-107">次のプロパティおよびコンポーネントで受信場所を作成します。</span><span class="sxs-lookup"><span data-stu-id="573ce-107">Create a receive location with the following properties and components:</span></span>  
  
|<span data-ttu-id="573ce-108">プロパティ/コンポーネント</span><span class="sxs-lookup"><span data-stu-id="573ce-108">Property/Component</span></span>|<span data-ttu-id="573ce-109">設定</span><span class="sxs-lookup"><span data-stu-id="573ce-109">Setting</span></span>|  
|-------------------------|-------------|  
|<span data-ttu-id="573ce-110">受信ポート</span><span class="sxs-lookup"><span data-stu-id="573ce-110">Receive port</span></span>|<span data-ttu-id="573ce-111">一方向のポート</span><span class="sxs-lookup"><span data-stu-id="573ce-111">One-way port</span></span>|  
|<span data-ttu-id="573ce-112">トランスポートの種類</span><span class="sxs-lookup"><span data-stu-id="573ce-112">Transport type</span></span>|<span data-ttu-id="573ce-113">MQSeries</span><span class="sxs-lookup"><span data-stu-id="573ce-113">MQSeries</span></span>|  
|<span data-ttu-id="573ce-114">キュー定義 (MQSeries)</span><span class="sxs-lookup"><span data-stu-id="573ce-114">Queue Definition (MQSeries)</span></span>|<span data-ttu-id="573ce-115">MQSeries server</span><span class="sxs-lookup"><span data-stu-id="573ce-115">MQSeries server</span></span><br /><span data-ttu-id="573ce-116">キュー マネージャー</span><span class="sxs-lookup"><span data-stu-id="573ce-116">Queue manager</span></span><br /><span data-ttu-id="573ce-117">キュー</span><span class="sxs-lookup"><span data-stu-id="573ce-117">Queue</span></span>|  
|<span data-ttu-id="573ce-118">[受信ハンドラー]</span><span class="sxs-lookup"><span data-stu-id="573ce-118">Receive handler</span></span>|<span data-ttu-id="573ce-119">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="573ce-119">BizTalkServerApplication</span></span>|  
|<span data-ttu-id="573ce-120">受信パイプライン。</span><span class="sxs-lookup"><span data-stu-id="573ce-120">Receive pipeline</span></span>|<span data-ttu-id="573ce-121">A4SWIFT 受信 FRR 用に作成したパイプライン</span><span class="sxs-lookup"><span data-stu-id="573ce-121">The A4SWIFT receive pipeline that you created for FRR</span></span>|  
  
### <a name="to-add-an-frr-receive-location-for-receiving-from-swift"></a><span data-ttu-id="573ce-122">SWIFT から、FRR 受信の受信場所を追加</span><span class="sxs-lookup"><span data-stu-id="573ce-122">To add an FRR receive location for receiving from SWIFT</span></span>  
  
1.  <span data-ttu-id="573ce-123">BizTalk Server 管理コンソールで  **BizTalk Server 管理**、 **BizTalk グループ**、**アプリケーション**、および**BizTalk アプリケーション1**ノード。</span><span class="sxs-lookup"><span data-stu-id="573ce-123">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, **BizTalk Group**, **Applications**, and  **BizTalk Application 1** nodes.</span></span>  
  
2.  <span data-ttu-id="573ce-124">右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="573ce-124">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
3.  <span data-ttu-id="573ce-125">受信ポートのプロパティ ダイアログ ボックスでの**名前**ボックスに、FRRSWIFTReceivePort など、受信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="573ce-125">In the Receive Port Properties dialog box, in the **Name** box, type a name for the receive port, such as FRRSWIFTReceivePort.</span></span>  
  
4.  <span data-ttu-id="573ce-126">をクリックして**適用**をクリックして、ポートのバインド**OK**します。</span><span class="sxs-lookup"><span data-stu-id="573ce-126">Click **Apply** to bind the port, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="573ce-127">管理コンソールで、右クリック**受信場所**、 をポイント**新規**、 をクリックし、**一方向の受信場所**します。</span><span class="sxs-lookup"><span data-stu-id="573ce-127">In the Administration Console, right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
6.  <span data-ttu-id="573ce-128">受信ポートのダイアログ ボックスの 選択した受信ポートを作成し、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="573ce-128">In the Select a Receive Port dialog box, select the receive port that you just created, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="573ce-129">受信場所のプロパティ ダイアログ ボックスでの**名前**ボックスに、FRRSWIFTReceiveLocation など、受信場所の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="573ce-129">In the Receive Location Properties dialog box, in the **Name** box, type a name for the receive location, such as FRRSWIFTReceiveLocation.</span></span>  
  
8.  <span data-ttu-id="573ce-130">**トランスポート**セクションの**型**テキスト ボックスで、 **MQSeries**します。</span><span class="sxs-lookup"><span data-stu-id="573ce-130">In the **Transport** section, for the **Type** text box, select **MQSeries**.</span></span>  
  
9. <span data-ttu-id="573ce-131">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="573ce-131">Click **Configure**.</span></span>  
  
10. <span data-ttu-id="573ce-132">[MQSeries トランスポートのプロパティ] ダイアログ ボックスで、**キュー定義**、クリックして、省略記号 (**.**) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="573ce-132">In the MQSeries Transport Properties dialog box, click **Queue Definition**, and then click the ellipsis (**…**) button.</span></span>  
  
11. <span data-ttu-id="573ce-133">**キュー定義**ダイアログ ボックスで、MQSeries サーバー、キュー マネージャー、入力し、キューします。</span><span class="sxs-lookup"><span data-stu-id="573ce-133">In the **Queue Definition** dialog box, enter the MQSeries server, queue manager, and queue.</span></span> <span data-ttu-id="573ce-134">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="573ce-134">Click **OK**.</span></span>  
  
12. <span data-ttu-id="573ce-135">**MQSeries トランスポートのプロパティ** ダイアログ ボックスで、プロパティが必要なであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="573ce-135">In the **MQSeries Transport Properties** dialog box, verify that the properties are as needed.</span></span> <span data-ttu-id="573ce-136">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="573ce-136">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="573ce-137">MQSeries トランスポートのプロパティの詳細については、MQSeries のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="573ce-137">For more information about MQSeries transport properties, see the MQSeries documentation.</span></span>  
  
13. <span data-ttu-id="573ce-138">受信場所のプロパティ ダイアログ ボックスでの**受信ハンドラー**、 **BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="573ce-138">In the Receive Location Properties dialog box, for **Receive Handler**, select **BizTalkServerApplication**.</span></span>  
  
14. <span data-ttu-id="573ce-139">**受信パイプライン** セクションで、選択、A4SWIFT 受信 FRR 用に作成したパイプライン。</span><span class="sxs-lookup"><span data-stu-id="573ce-139">For **Receive Pipeline** section, select the A4SWIFT receive pipeline that you created for FRR.</span></span>  
  
15. <span data-ttu-id="573ce-140">クリックして**適用**、 をクリックし、 **OK**</span><span class="sxs-lookup"><span data-stu-id="573ce-140">Click **Apply**, and then click **OK**</span></span>  
  
16. <span data-ttu-id="573ce-141">BizTalk エクスプ ローラーで右クリックした受信場所を作成し、**を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="573ce-141">In BizTalk Explorer, right-click the receive location that you just created, and then click **Enable**.</span></span>