---
title: 手順 3 e:FileAct ストア アンド フォワード シナリオ用に Sw-exchangesnfresponse メッセージをキャプチャする FILE 送信ポートの追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04bad2ab-1ea4-4602-9dee-5b9af9be3b93
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e77a6b8ded2a2a779155df621b3e25267b20370
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365375"
---
# <a name="step-3e-add-a-file-send-port-for-the-fileact-store-and-forward-scenario-to-capture-sw-exchangesnfresponse-messages"></a><span data-ttu-id="5111f-102">手順 3 e:FileAct ストア アンド フォワード シナリオ用に Sw-exchangesnfresponse メッセージをキャプチャする FILE 送信ポートの追加します。</span><span class="sxs-lookup"><span data-stu-id="5111f-102">Step 3E: Add a FILE Send Port for the FileAct Store and Forward Scenario to capture Sw-ExchangeSnFResponse messages</span></span>
<span data-ttu-id="5111f-103">この手順を開始する前に行う必要があります[手順 3 D:FileAct ストア アンド フォワード シナリオ用 FILEACT 送信ポートの追加](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-store-and-forward-scenario.md)します。</span><span class="sxs-lookup"><span data-stu-id="5111f-103">Before you begin this step, you must complete [Step 3D: Add a FILEACT Send Port for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-store-and-forward-scenario.md).</span></span>  
  
### <a name="to-add-a-file-send-port-to-capture-status-events"></a><span data-ttu-id="5111f-104">状態イベントをキャプチャする FILE 送信ポートを追加するには。</span><span class="sxs-lookup"><span data-stu-id="5111f-104">To add a FILE send port to capture Status Events:</span></span>  
  
1.  <span data-ttu-id="5111f-105">開始**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="5111f-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="5111f-106">コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションを順に展開します。</span><span class="sxs-lookup"><span data-stu-id="5111f-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="5111f-107">右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="5111f-107">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
4.  <span data-ttu-id="5111f-108">**送信ポートのプロパティ**ウィンドウで、名前、送信ポート Tutorial_ GetStatusReports します。</span><span class="sxs-lookup"><span data-stu-id="5111f-108">In the **Send Port Properties** window, name the send port, Tutorial_ GetStatusReports.</span></span>  
  
5.  <span data-ttu-id="5111f-109">**送信ポートのプロパティ**ウィンドウから、**トランスポートの種類**ドロップダウン リストで、**ファイル**、 をクリックし、**構成**。</span><span class="sxs-lookup"><span data-stu-id="5111f-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="5111f-110">**FILE トランスポートのプロパティ** ダイアログ ボックスで、**先フォルダー**ボックス、C:\SWIFTAdapterTutorial\Fileact\ StatusEvents を入力し、をクリックし、 **ok**します。</span><span class="sxs-lookup"><span data-stu-id="5111f-110">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type C:\SWIFTAdapterTutorial\Fileact\ StatusEvents, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="5111f-111">**送信ポートのプロパティ**ウィンドウで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5111f-111">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="5111f-112">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="5111f-112">**Use this**</span></span>|<span data-ttu-id="5111f-113">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="5111f-113">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="5111f-114">**送信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="5111f-114">**Send handler**</span></span>|<span data-ttu-id="5111f-115">ドロップダウン リストから選択**BizTalkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="5111f-115">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="5111f-116">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="5111f-116">**Send pipeline**</span></span>|<span data-ttu-id="5111f-117">ドロップダウン リストから選択**XMLTransmit**します。</span><span class="sxs-lookup"><span data-stu-id="5111f-117">From the drop-down list, select **XMLTransmit**.</span></span>|  
  
8.  <span data-ttu-id="5111f-118">**送信ポートのプロパティ**ウィンドウで、**フィルター**  タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5111f-118">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="5111f-119">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="5111f-119">**Use this**</span></span>|<span data-ttu-id="5111f-120">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="5111f-120">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="5111f-121">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="5111f-121">**Property**</span></span>|<span data-ttu-id="5111f-122">BTS を選択します。メッセージの種類</span><span class="sxs-lookup"><span data-stu-id="5111f-122">Select BTS.MessageType</span></span>|  
    |<span data-ttu-id="5111f-123">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="5111f-123">**Operator**</span></span>|<span data-ttu-id="5111f-124">選択 = =</span><span class="sxs-lookup"><span data-stu-id="5111f-124">Select ==</span></span>|  
    |<span data-ttu-id="5111f-125">**[値]**</span><span class="sxs-lookup"><span data-stu-id="5111f-125">**Value**</span></span>|<span data-ttu-id="5111f-126">Type Sw-HandleFileEventRequest</span><span class="sxs-lookup"><span data-stu-id="5111f-126">Type Sw-HandleFileEventRequest</span></span>|  
    |<span data-ttu-id="5111f-127">**[グループ]**</span><span class="sxs-lookup"><span data-stu-id="5111f-127">**Group**</span></span>|<span data-ttu-id="5111f-128">または</span><span class="sxs-lookup"><span data-stu-id="5111f-128">Or</span></span>|  
    |<span data-ttu-id="5111f-129">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="5111f-129">**Property**</span></span>|<span data-ttu-id="5111f-130">BTS を選択します。</span><span class="sxs-lookup"><span data-stu-id="5111f-130">Select BTS.</span></span> <span data-ttu-id="5111f-131">[MessageType]</span><span class="sxs-lookup"><span data-stu-id="5111f-131">MessageType</span></span>|  
    |<span data-ttu-id="5111f-132">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="5111f-132">**Operator**</span></span>|<span data-ttu-id="5111f-133">選択 = =</span><span class="sxs-lookup"><span data-stu-id="5111f-133">Select ==</span></span>|  
    |<span data-ttu-id="5111f-134">**[値]**</span><span class="sxs-lookup"><span data-stu-id="5111f-134">**Value**</span></span>|<span data-ttu-id="5111f-135">Type Sw-ExchangeSnFResponse</span><span class="sxs-lookup"><span data-stu-id="5111f-135">Type Sw-ExchangeSnFResponse</span></span>|