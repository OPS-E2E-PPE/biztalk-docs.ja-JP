---
title: 手順 3 f:Sw-handlefileeventrequest メッセージをキャプチャする FileAct リアルタイム シナリオ用の FILE 送信ポートの追加 |Microsoft Docs
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
ms.openlocfilehash: 45ad02b111d6fabde4260994f29a0b756cb1dd66
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365346"
---
# <a name="step-3f-add-a-file-send-port-for-the-fileact-real-time-scenario-to-capture-sw-handlefileeventrequest-messages"></a><span data-ttu-id="942c5-102">手順 3 f:Sw-handlefileeventrequest メッセージをキャプチャする FileAct リアルタイム シナリオ用の FILE 送信ポートの追加します。</span><span class="sxs-lookup"><span data-stu-id="942c5-102">Step 3F: Add a FILE Send Port for the FileAct Real-Time Scenario to Capture Sw-HandleFileEventRequest Messages</span></span>
<span data-ttu-id="942c5-103">この手順を開始する前に行う必要があります[手順 3 e:FileAct リアルタイム シナリオ用に Sw:ExchangeFileResponse メッセージをキャプチャする FILE 送信ポートの追加します。](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)</span><span class="sxs-lookup"><span data-stu-id="942c5-103">Before you begin this step, you must complete [Step 3E: Add a FILE Send Port to Capture Sw:ExchangeFileResponse Message for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)</span></span>  
  
### <a name="to-add-a-file-send-port-to-capture-status-events"></a><span data-ttu-id="942c5-104">状態イベントをキャプチャする FILE 送信ポートを追加するには。</span><span class="sxs-lookup"><span data-stu-id="942c5-104">To add a FILE send port to capture Status Events:</span></span>  
  
1.  <span data-ttu-id="942c5-105">開始**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="942c5-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="942c5-106">コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションを順に展開します。</span><span class="sxs-lookup"><span data-stu-id="942c5-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="942c5-107">右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="942c5-107">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
4.  <span data-ttu-id="942c5-108">**送信ポートのプロパティ**ウィンドウで、名前、送信ポート Tutorial_ GetStatusReports します。</span><span class="sxs-lookup"><span data-stu-id="942c5-108">In the **Send Port Properties** window, name the send port, Tutorial_ GetStatusReports.</span></span>  
  
5.  <span data-ttu-id="942c5-109">**送信ポートのプロパティ**ウィンドウから、**トランスポートの種類**ドロップダウン リストで、**ファイル**、 をクリックし、**構成**。</span><span class="sxs-lookup"><span data-stu-id="942c5-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="942c5-110">**FILE トランスポートのプロパティ** ダイアログ ボックスで、**先フォルダー**ボックス、C:\SWIFTAdapterTutorial\Fileact\ StatusEvents を入力し、をクリックし、 **ok**します。</span><span class="sxs-lookup"><span data-stu-id="942c5-110">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type C:\SWIFTAdapterTutorial\Fileact\ StatusEvents, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="942c5-111">**送信ポートのプロパティ**ウィンドウで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="942c5-111">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="942c5-112">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="942c5-112">**Use this**</span></span>|<span data-ttu-id="942c5-113">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="942c5-113">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="942c5-114">**送信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="942c5-114">**Send handler**</span></span>|<span data-ttu-id="942c5-115">ドロップダウン リストから選択**BizTalkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="942c5-115">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="942c5-116">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="942c5-116">**Send pipeline**</span></span>|<span data-ttu-id="942c5-117">ドロップダウン リストから選択**XMLTransmit**します。</span><span class="sxs-lookup"><span data-stu-id="942c5-117">From the drop-down list, select **XMLTransmit**.</span></span>|  
  
8.  <span data-ttu-id="942c5-118">**送信ポートのプロパティ**ウィンドウで、**フィルター**  タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="942c5-118">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="942c5-119">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="942c5-119">**Use this**</span></span>|<span data-ttu-id="942c5-120">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="942c5-120">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="942c5-121">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="942c5-121">**Property**</span></span>|<span data-ttu-id="942c5-122">BTS を選択します。</span><span class="sxs-lookup"><span data-stu-id="942c5-122">Select BTS.</span></span> <span data-ttu-id="942c5-123">[MessageType]</span><span class="sxs-lookup"><span data-stu-id="942c5-123">MessageType</span></span>|  
    |<span data-ttu-id="942c5-124">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="942c5-124">**Operator**</span></span>|<span data-ttu-id="942c5-125">選択 = =</span><span class="sxs-lookup"><span data-stu-id="942c5-125">Select ==</span></span>|  
    |<span data-ttu-id="942c5-126">**[値]**</span><span class="sxs-lookup"><span data-stu-id="942c5-126">**Value**</span></span>|<span data-ttu-id="942c5-127">Type Sw-HandleFileEventRequest</span><span class="sxs-lookup"><span data-stu-id="942c5-127">Type Sw-HandleFileEventRequest</span></span>|  
    |<span data-ttu-id="942c5-128">**[グループ]**</span><span class="sxs-lookup"><span data-stu-id="942c5-128">**Group**</span></span>|<span data-ttu-id="942c5-129">または</span><span class="sxs-lookup"><span data-stu-id="942c5-129">Or</span></span>|  
    |<span data-ttu-id="942c5-130">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="942c5-130">**Property**</span></span>|<span data-ttu-id="942c5-131">BTS を選択します。</span><span class="sxs-lookup"><span data-stu-id="942c5-131">Select BTS.</span></span> <span data-ttu-id="942c5-132">[MessageType]</span><span class="sxs-lookup"><span data-stu-id="942c5-132">MessageType</span></span>|  
    |<span data-ttu-id="942c5-133">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="942c5-133">**Operator**</span></span>|<span data-ttu-id="942c5-134">選択 = =</span><span class="sxs-lookup"><span data-stu-id="942c5-134">Select ==</span></span>|  
    |<span data-ttu-id="942c5-135">**[値]**</span><span class="sxs-lookup"><span data-stu-id="942c5-135">**Value**</span></span>|<span data-ttu-id="942c5-136">Type Sw-ExchangeSnFResponse</span><span class="sxs-lookup"><span data-stu-id="942c5-136">Type Sw-ExchangeSnFResponse</span></span>|