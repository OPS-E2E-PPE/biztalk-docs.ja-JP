---
title: "SWIFT から受信するための受信場所の作成、FRR |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive locations, creating
- creating, receive locations
- FRR, creating receive locations
ms.assetid: e10857f4-21cb-4c09-8eed-cb6e9b0a0aa9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e43ac2ac0fab9b2a29a44784032f9d3369833ae2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-the-frr-receive-location-for-receiving-from-swift"></a><span data-ttu-id="6c74e-102">SWIFT から受信するための受信場所の FRR を作成します。</span><span class="sxs-lookup"><span data-stu-id="6c74e-102">Creating the FRR Receive Location for Receiving from SWIFT</span></span>
<span data-ttu-id="6c74e-103">FIN 対応調整を実行するには、A4SWIFT に SWIFT ネットワークからメッセージを受信する受信場所を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c74e-103">To perform FIN Response Reconciliation, you need to create a receive location that receives a message from the SWIFT Network into A4SWIFT.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6c74e-104">お勧め SAA からメッセージを受信するための場所が表示される 2 つを設定する: パン/nans 値や 1 つの他のすべてのメッセージを受信する受信します。</span><span class="sxs-lookup"><span data-stu-id="6c74e-104">It is advisable to set up two receive locations for receiving messages from SAA: one to receive PAN/NANs and one to receive all other messages.</span></span> <span data-ttu-id="6c74e-105">設定するには 2 つの受信場所、SAA で 2 つの MQSeries キューからメッセージを受信する必要があります: パン/nans 値やその他のすべてのメッセージ型のいずれかのいずれか。</span><span class="sxs-lookup"><span data-stu-id="6c74e-105">To set up the two receive locations, you must receive messages from two MQSeries queues at SAA: one for PAN/NANs and one for all other message types.</span></span>  
  
 <span data-ttu-id="6c74e-106">**概要**</span><span class="sxs-lookup"><span data-stu-id="6c74e-106">**Summary**</span></span>  
  
 <span data-ttu-id="6c74e-107">次のプロパティおよびコンポーネントで受信場所を作成します。</span><span class="sxs-lookup"><span data-stu-id="6c74e-107">Create a receive location with the following properties and components:</span></span>  
  
|<span data-ttu-id="6c74e-108">プロパティ/コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6c74e-108">Property/Component</span></span>|<span data-ttu-id="6c74e-109">設定</span><span class="sxs-lookup"><span data-stu-id="6c74e-109">Setting</span></span>|  
|-------------------------|-------------|  
|<span data-ttu-id="6c74e-110">受信ポート</span><span class="sxs-lookup"><span data-stu-id="6c74e-110">Receive port</span></span>|<span data-ttu-id="6c74e-111">一方向のポート</span><span class="sxs-lookup"><span data-stu-id="6c74e-111">One-way port</span></span>|  
|<span data-ttu-id="6c74e-112">トランスポートの種類</span><span class="sxs-lookup"><span data-stu-id="6c74e-112">Transport type</span></span>|<span data-ttu-id="6c74e-113">MQSeries</span><span class="sxs-lookup"><span data-stu-id="6c74e-113">MQSeries</span></span>|  
|<span data-ttu-id="6c74e-114">キュー定義 (MQSeries)</span><span class="sxs-lookup"><span data-stu-id="6c74e-114">Queue Definition (MQSeries)</span></span>|<span data-ttu-id="6c74e-115">MQSeries server</span><span class="sxs-lookup"><span data-stu-id="6c74e-115">MQSeries server</span></span><br /><span data-ttu-id="6c74e-116">キュー マネージャー</span><span class="sxs-lookup"><span data-stu-id="6c74e-116">Queue manager</span></span><br /><span data-ttu-id="6c74e-117">キュー</span><span class="sxs-lookup"><span data-stu-id="6c74e-117">Queue</span></span>|  
|<span data-ttu-id="6c74e-118">[受信ハンドラー]</span><span class="sxs-lookup"><span data-stu-id="6c74e-118">Receive handler</span></span>|<span data-ttu-id="6c74e-119">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="6c74e-119">BizTalkServerApplication</span></span>|  
|<span data-ttu-id="6c74e-120">受信パイプライン。</span><span class="sxs-lookup"><span data-stu-id="6c74e-120">Receive pipeline</span></span>|<span data-ttu-id="6c74e-121">A4SWIFT FRR 用に作成したパイプラインを受信します。</span><span class="sxs-lookup"><span data-stu-id="6c74e-121">The A4SWIFT receive pipeline that you created for FRR</span></span>|  
  
### <a name="to-add-an-frr-receive-location-for-receiving-from-swift"></a><span data-ttu-id="6c74e-122">SWIFT から、FRR 受信受信するための場所を追加</span><span class="sxs-lookup"><span data-stu-id="6c74e-122">To add an FRR receive location for receiving from SWIFT</span></span>  
  
1.  <span data-ttu-id="6c74e-123">BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、 **BizTalk グループ**、**アプリケーション**、および**BizTalk アプリケーション1**ノード。</span><span class="sxs-lookup"><span data-stu-id="6c74e-123">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, **BizTalk Group**, **Applications**, and  **BizTalk Application 1** nodes.</span></span>  
  
2.  <span data-ttu-id="6c74e-124">右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="6c74e-124">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
3.  <span data-ttu-id="6c74e-125">受信ポートのプロパティ ダイアログ ボックスで、**名前**ボックス FRRSWIFTReceivePort など、受信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="6c74e-125">In the Receive Port Properties dialog box, in the **Name** box, type a name for the receive port, such as FRRSWIFTReceivePort.</span></span>  
  
4.  <span data-ttu-id="6c74e-126">をクリックして**適用**をクリックして、ポートのバインド**OK**です。</span><span class="sxs-lookup"><span data-stu-id="6c74e-126">Click **Apply** to bind the port, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="6c74e-127">管理コンソールで、右クリック**受信場所**、 をポイント**新規**、クリックして**一方向の受信場所**です。</span><span class="sxs-lookup"><span data-stu-id="6c74e-127">In the Administration Console, right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
6.  <span data-ttu-id="6c74e-128">受信ポート ダイアログ ボックスの 選択した受信ポートを作成し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="6c74e-128">In the Select a Receive Port dialog box, select the receive port that you just created, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="6c74e-129">受信場所のプロパティ ダイアログ ボックスで、**名前**ボックス FRRSWIFTReceiveLocation など、受信場所の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="6c74e-129">In the Receive Location Properties dialog box, in the **Name** box, type a name for the receive location, such as FRRSWIFTReceiveLocation.</span></span>  
  
8.  <span data-ttu-id="6c74e-130">**トランスポート** セクションの**型**テキスト ボックスで、 **MQSeries**です。</span><span class="sxs-lookup"><span data-stu-id="6c74e-130">In the **Transport** section, for the **Type** text box, select **MQSeries**.</span></span>  
  
9. <span data-ttu-id="6c74e-131">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="6c74e-131">Click **Configure**.</span></span>  
  
10. <span data-ttu-id="6c74e-132">[MQSeries トランスポートのプロパティ] ダイアログ ボックスで、**キュー定義**、クリックして、省略記号 (**.**) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c74e-132">In the MQSeries Transport Properties dialog box, click **Queue Definition**, and then click the ellipsis (**…**) button.</span></span>  
  
11. <span data-ttu-id="6c74e-133">**キュー定義**ダイアログ ボックスで、MQSeries サーバー、キュー マネージャーでは、入力をキューに登録します。</span><span class="sxs-lookup"><span data-stu-id="6c74e-133">In the **Queue Definition** dialog box, enter the MQSeries server, queue manager, and queue.</span></span> <span data-ttu-id="6c74e-134">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c74e-134">Click **OK**.</span></span>  
  
12. <span data-ttu-id="6c74e-135">**MQSeries トランスポートのプロパティ** ダイアログ ボックスで、プロパティが必要なことを確認します。</span><span class="sxs-lookup"><span data-stu-id="6c74e-135">In the **MQSeries Transport Properties** dialog box, verify that the properties are as needed.</span></span> <span data-ttu-id="6c74e-136">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c74e-136">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6c74e-137">MQSeries トランスポートのプロパティの詳細については、MQSeries のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c74e-137">For more information about MQSeries transport properties, see the MQSeries documentation.</span></span>  
  
13. <span data-ttu-id="6c74e-138">受信場所のプロパティ] ダイアログ ボックスの**受信ハンドラー**[ **BizTalkServerApplication**です。</span><span class="sxs-lookup"><span data-stu-id="6c74e-138">In the Receive Location Properties dialog box, for **Receive Handler**, select **BizTalkServerApplication**.</span></span>  
  
14. <span data-ttu-id="6c74e-139">**受信パイプライン** セクションで、選択、A4SWIFT 受信パイプライン FRR 用に作成します。</span><span class="sxs-lookup"><span data-stu-id="6c74e-139">For **Receive Pipeline** section, select the A4SWIFT receive pipeline that you created for FRR.</span></span>  
  
15. <span data-ttu-id="6c74e-140">をクリックして**適用**、クリックして**OK**</span><span class="sxs-lookup"><span data-stu-id="6c74e-140">Click **Apply**, and then click **OK**</span></span>  
  
16. <span data-ttu-id="6c74e-141">BizTalk エクスプローラを右クリックした受信場所を作成し、をクリックして**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="6c74e-141">In BizTalk Explorer, right-click the receive location that you just created, and then click **Enable**.</span></span>