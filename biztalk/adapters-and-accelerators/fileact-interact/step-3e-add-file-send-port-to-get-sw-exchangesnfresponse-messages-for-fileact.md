---
title: "ステップ 3 e: FileAct ストア アンド ソフトウェア ExchangeSnFResponse メッセージをキャプチャするシナリオ前方の FILE 送信ポートの追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 04bad2ab-1ea4-4602-9dee-5b9af9be3b93
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44cf320f22f5acc2511d6327c36c54cda8f0dd1c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3e-add-a-file-send-port-for-the-fileact-store-and-forward-scenario-to-capture-sw-exchangesnfresponse-messages"></a><span data-ttu-id="185e6-102">ステップ 3 e: FileAct ストア アンド ソフトウェア ExchangeSnFResponse メッセージをキャプチャするシナリオ前方の FILE 送信ポートの追加</span><span class="sxs-lookup"><span data-stu-id="185e6-102">Step 3E: Add a FILE Send Port for the FileAct Store and Forward Scenario to capture Sw-ExchangeSnFResponse messages</span></span>
<span data-ttu-id="185e6-103">この手順を開始する前に行う必要があります[ステップ 3 D: FileAct ストア アンド フォワードのシナリオの FILEACT 送信ポートを追加](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-store-and-forward-scenario.md)です。</span><span class="sxs-lookup"><span data-stu-id="185e6-103">Before you begin this step, you must complete [Step 3D: Add a FILEACT Send Port for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-store-and-forward-scenario.md).</span></span>  
  
### <a name="to-add-a-file-send-port-to-capture-status-events"></a><span data-ttu-id="185e6-104">状態イベントをキャプチャする FILE 送信ポートを追加するには。</span><span class="sxs-lookup"><span data-stu-id="185e6-104">To add a FILE send port to capture Status Events:</span></span>  
  
1.  <span data-ttu-id="185e6-105">開始**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="185e6-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="185e6-106">コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="185e6-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="185e6-107">右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="185e6-107">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
4.  <span data-ttu-id="185e6-108">**送信ポートのプロパティ**ウィンドウで、名前、送信ポートを Tutorial_ GetStatusReports です。</span><span class="sxs-lookup"><span data-stu-id="185e6-108">In the **Send Port Properties** window, name the send port, Tutorial_ GetStatusReports.</span></span>  
  
5.  <span data-ttu-id="185e6-109">**送信ポートのプロパティ** ウィンドウから、**トランスポートの種類**ドロップダウン リストで、**ファイル**、順にクリック**構成**です。</span><span class="sxs-lookup"><span data-stu-id="185e6-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="185e6-110">**FILE トランスポートのプロパティ** ダイアログ ボックスで、**コピー先フォルダー**ボックス、C:\SWIFTAdapterTutorial\Fileact\ StatusEvents を入力し、をクリックして**ok**です。</span><span class="sxs-lookup"><span data-stu-id="185e6-110">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type C:\SWIFTAdapterTutorial\Fileact\ StatusEvents, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="185e6-111">**送信ポートのプロパティ** ウィンドウで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="185e6-111">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="185e6-112">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="185e6-112">**Use this**</span></span>|<span data-ttu-id="185e6-113">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="185e6-113">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="185e6-114">**送信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="185e6-114">**Send handler**</span></span>|<span data-ttu-id="185e6-115">ドロップダウン リストから選択**BizTalkServerApplication**です。</span><span class="sxs-lookup"><span data-stu-id="185e6-115">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="185e6-116">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="185e6-116">**Send pipeline**</span></span>|<span data-ttu-id="185e6-117">ドロップダウン リストから選択**XMLTransmit**です。</span><span class="sxs-lookup"><span data-stu-id="185e6-117">From the drop-down list, select **XMLTransmit**.</span></span>|  
  
8.  <span data-ttu-id="185e6-118">**送信ポートのプロパティ** ウィンドウで、**フィルター**  タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="185e6-118">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="185e6-119">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="185e6-119">**Use this**</span></span>|<span data-ttu-id="185e6-120">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="185e6-120">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="185e6-121">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="185e6-121">**Property**</span></span>|<span data-ttu-id="185e6-122">BTS を選択します。MessageType</span><span class="sxs-lookup"><span data-stu-id="185e6-122">Select BTS.MessageType</span></span>|  
    |<span data-ttu-id="185e6-123">**演算子**</span><span class="sxs-lookup"><span data-stu-id="185e6-123">**Operator**</span></span>|<span data-ttu-id="185e6-124">オン = =</span><span class="sxs-lookup"><span data-stu-id="185e6-124">Select ==</span></span>|  
    |<span data-ttu-id="185e6-125">**値**</span><span class="sxs-lookup"><span data-stu-id="185e6-125">**Value**</span></span>|<span data-ttu-id="185e6-126">型のソフトウェア HandleFileEventRequest</span><span class="sxs-lookup"><span data-stu-id="185e6-126">Type Sw-HandleFileEventRequest</span></span>|  
    |<span data-ttu-id="185e6-127">**[グループ]**</span><span class="sxs-lookup"><span data-stu-id="185e6-127">**Group**</span></span>|<span data-ttu-id="185e6-128">または</span><span class="sxs-lookup"><span data-stu-id="185e6-128">Or</span></span>|  
    |<span data-ttu-id="185e6-129">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="185e6-129">**Property**</span></span>|<span data-ttu-id="185e6-130">BTS を選択します。</span><span class="sxs-lookup"><span data-stu-id="185e6-130">Select BTS.</span></span> <span data-ttu-id="185e6-131">[MessageType]</span><span class="sxs-lookup"><span data-stu-id="185e6-131">MessageType</span></span>|  
    |<span data-ttu-id="185e6-132">**演算子**</span><span class="sxs-lookup"><span data-stu-id="185e6-132">**Operator**</span></span>|<span data-ttu-id="185e6-133">オン = =</span><span class="sxs-lookup"><span data-stu-id="185e6-133">Select ==</span></span>|  
    |<span data-ttu-id="185e6-134">**値**</span><span class="sxs-lookup"><span data-stu-id="185e6-134">**Value**</span></span>|<span data-ttu-id="185e6-135">型のソフトウェア ExchangeSnFResponse</span><span class="sxs-lookup"><span data-stu-id="185e6-135">Type Sw-ExchangeSnFResponse</span></span>|