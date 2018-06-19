---
title: 'ステップ 3 f: ソフトウェア HandleFileEventRequest メッセージをキャプチャする FileAct リアルタイム シナリオの FILE 送信ポートの追加 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b7594b0-0443-41b7-ae04-55b2cc8bf90e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1d70c338696f1c4455161a88c8d2988e0ea0ccb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225530"
---
# <a name="step-3f-add-a-file-send-port-for-the-fileact-real-time-scenario-to-capture-sw-handlefileeventrequest-messages"></a><span data-ttu-id="86e65-102">ステップ 3 f: ソフトウェア HandleFileEventRequest メッセージをキャプチャする FileAct リアルタイム シナリオの FILE 送信ポートの追加</span><span class="sxs-lookup"><span data-stu-id="86e65-102">Step 3F: Add a FILE Send Port for the FileAct Real-Time Scenario to Capture Sw-HandleFileEventRequest Messages</span></span>
<span data-ttu-id="86e65-103">この手順を開始する前に行う必要があります[ステップ 3 e: Sw:ExchangeFileResponse メッセージのキャプチャに FileAct リアルタイム シナリオでは、ファイル送信ポートの追加](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)</span><span class="sxs-lookup"><span data-stu-id="86e65-103">Before you begin this step, you must complete [Step 3E: Add a FILE Send Port to Capture Sw:ExchangeFileResponse Message for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)</span></span>  
  
### <a name="to-add-a-file-send-port-to-capture-status-events"></a><span data-ttu-id="86e65-104">状態イベントをキャプチャする FILE 送信ポートを追加するには。</span><span class="sxs-lookup"><span data-stu-id="86e65-104">To add a FILE send port to capture Status Events:</span></span>  
  
1.  <span data-ttu-id="86e65-105">開始**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="86e65-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="86e65-106">コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="86e65-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="86e65-107">右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="86e65-107">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
4.  <span data-ttu-id="86e65-108">**送信ポートのプロパティ**ウィンドウで、名前、送信ポートを Tutorial_ GetStatusReports です。</span><span class="sxs-lookup"><span data-stu-id="86e65-108">In the **Send Port Properties** window, name the send port, Tutorial_ GetStatusReports.</span></span>  
  
5.  <span data-ttu-id="86e65-109">**送信ポートのプロパティ** ウィンドウから、**トランスポートの種類**ドロップダウン リストで、**ファイル**、順にクリック**構成**です。</span><span class="sxs-lookup"><span data-stu-id="86e65-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="86e65-110">**FILE トランスポートのプロパティ** ダイアログ ボックスで、**コピー先フォルダー**ボックス、C:\SWIFTAdapterTutorial\Fileact\ StatusEvents を入力し、をクリックして**ok**です。</span><span class="sxs-lookup"><span data-stu-id="86e65-110">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type C:\SWIFTAdapterTutorial\Fileact\ StatusEvents, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="86e65-111">**送信ポートのプロパティ** ウィンドウで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="86e65-111">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="86e65-112">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="86e65-112">**Use this**</span></span>|<span data-ttu-id="86e65-113">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="86e65-113">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="86e65-114">**送信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="86e65-114">**Send handler**</span></span>|<span data-ttu-id="86e65-115">ドロップダウン リストから選択**BizTalkServerApplication**です。</span><span class="sxs-lookup"><span data-stu-id="86e65-115">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="86e65-116">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="86e65-116">**Send pipeline**</span></span>|<span data-ttu-id="86e65-117">ドロップダウン リストから選択**XMLTransmit**です。</span><span class="sxs-lookup"><span data-stu-id="86e65-117">From the drop-down list, select **XMLTransmit**.</span></span>|  
  
8.  <span data-ttu-id="86e65-118">**送信ポートのプロパティ** ウィンドウで、**フィルター**  タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="86e65-118">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="86e65-119">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="86e65-119">**Use this**</span></span>|<span data-ttu-id="86e65-120">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="86e65-120">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="86e65-121">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="86e65-121">**Property**</span></span>|<span data-ttu-id="86e65-122">BTS を選択します。</span><span class="sxs-lookup"><span data-stu-id="86e65-122">Select BTS.</span></span> <span data-ttu-id="86e65-123">[MessageType]</span><span class="sxs-lookup"><span data-stu-id="86e65-123">MessageType</span></span>|  
    |<span data-ttu-id="86e65-124">**演算子**</span><span class="sxs-lookup"><span data-stu-id="86e65-124">**Operator**</span></span>|<span data-ttu-id="86e65-125">オン = =</span><span class="sxs-lookup"><span data-stu-id="86e65-125">Select ==</span></span>|  
    |<span data-ttu-id="86e65-126">**値**</span><span class="sxs-lookup"><span data-stu-id="86e65-126">**Value**</span></span>|<span data-ttu-id="86e65-127">型のソフトウェア HandleFileEventRequest</span><span class="sxs-lookup"><span data-stu-id="86e65-127">Type Sw-HandleFileEventRequest</span></span>|  
    |<span data-ttu-id="86e65-128">**[グループ]**</span><span class="sxs-lookup"><span data-stu-id="86e65-128">**Group**</span></span>|<span data-ttu-id="86e65-129">または</span><span class="sxs-lookup"><span data-stu-id="86e65-129">Or</span></span>|  
    |<span data-ttu-id="86e65-130">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="86e65-130">**Property**</span></span>|<span data-ttu-id="86e65-131">BTS を選択します。</span><span class="sxs-lookup"><span data-stu-id="86e65-131">Select BTS.</span></span> <span data-ttu-id="86e65-132">[MessageType]</span><span class="sxs-lookup"><span data-stu-id="86e65-132">MessageType</span></span>|  
    |<span data-ttu-id="86e65-133">**演算子**</span><span class="sxs-lookup"><span data-stu-id="86e65-133">**Operator**</span></span>|<span data-ttu-id="86e65-134">オン = =</span><span class="sxs-lookup"><span data-stu-id="86e65-134">Select ==</span></span>|  
    |<span data-ttu-id="86e65-135">**値**</span><span class="sxs-lookup"><span data-stu-id="86e65-135">**Value**</span></span>|<span data-ttu-id="86e65-136">型のソフトウェア ExchangeSnFResponse</span><span class="sxs-lookup"><span data-stu-id="86e65-136">Type Sw-ExchangeSnFResponse</span></span>|