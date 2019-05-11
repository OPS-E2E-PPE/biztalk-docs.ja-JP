---
title: 手順 3 D:用に Sw:HandleResponse メッセージをキャプチャする FILE 送信ポートを追加、InterAct リアルタイム シナリオ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e05e4d20-4cf2-402f-aaea-66987cb6515a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc04ad643991d9685950b14874c1c6e53ae81c0e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366419"
---
# <a name="step-3d-add-a-file-send-port-to-capture-the-swhandleresponse-message-for-the-interact-real-time-scenario"></a><span data-ttu-id="84c6c-102">手順 3 D:用に Sw:HandleResponse メッセージをキャプチャする FILE 送信ポートを追加、InterAct リアルタイム シナリオ</span><span class="sxs-lookup"><span data-stu-id="84c6c-102">Step 3D: Add a FILE Send Port to Capture the Sw:HandleResponse Message for the InterAct Real-Time Scenario</span></span>
<span data-ttu-id="84c6c-103">完全な[手順 3 C:操作のリアルタイム シナリオ用に Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートの追加](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md)この手順を開始する前にします。</span><span class="sxs-lookup"><span data-stu-id="84c6c-103">Complete [Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md) before you begin this step.</span></span>
  
## <a name="add-a-file-send-port-to-capture-swhandleresponse-message"></a><span data-ttu-id="84c6c-104">ファイル送信 Sw:HandleResponse メッセージをキャプチャするポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="84c6c-104">Add a FILE send port to capture Sw:HandleResponse message</span></span>  
  
1.  <span data-ttu-id="84c6c-105">開始**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="84c6c-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="84c6c-106">コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションを順に展開します。</span><span class="sxs-lookup"><span data-stu-id="84c6c-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="84c6c-107">右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート。**</span><span class="sxs-lookup"><span data-stu-id="84c6c-107">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port.**</span></span>  
  
4.  <span data-ttu-id="84c6c-108">**送信ポートのプロパティ**ウィンドウで、送信ポート名**Tutorial_IA_SendResponseToSender**します。</span><span class="sxs-lookup"><span data-stu-id="84c6c-108">In the **Send Port Properties** window, name the send port **Tutorial_IA_SendResponseToSender**.</span></span>  
  
5.  <span data-ttu-id="84c6c-109">**送信ポートのプロパティ**ウィンドウから、 **Transporttype**ドロップダウン リストで、**ファイル**、 をクリックし、**構成**。</span><span class="sxs-lookup"><span data-stu-id="84c6c-109">In the **Send Port Properties** window, from the **Transporttype** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="84c6c-110">**FILE トランスポートのプロパティ** ダイアログ ボックスで、**先フォルダー**ボックスに「 **C:\SWIFTAdapterTutorial\Interact\Response**、をクリックしてして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="84c6c-110">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type **C:\SWIFTAdapterTutorial\Interact\Response**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="84c6c-111">**送信ポートのプロパティ**ウィンドウで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="84c6c-111">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="84c6c-112">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="84c6c-112">**Use this**</span></span>|<span data-ttu-id="84c6c-113">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="84c6c-113">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="84c6c-114">**送信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="84c6c-114">**Send handler**</span></span>|<span data-ttu-id="84c6c-115">ドロップダウン リストから選択**BizTalkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="84c6c-115">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="84c6c-116">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="84c6c-116">**Send pipeline**</span></span>|<span data-ttu-id="84c6c-117">ドロップダウン リストから選択**XMLTransmit**します。</span><span class="sxs-lookup"><span data-stu-id="84c6c-117">From the drop-down list, select **XMLTransmit**.</span></span>|  
  
8.  <span data-ttu-id="84c6c-118">**送信ポートのプロパティ**ウィンドウで、**フィルター**  タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="84c6c-118">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="84c6c-119">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="84c6c-119">**Use this**</span></span>|<span data-ttu-id="84c6c-120">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="84c6c-120">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="84c6c-121">最初の行。**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="84c6c-121">First row: **Property**</span></span>|<span data-ttu-id="84c6c-122">ドロップダウン リストから選択**BTS します。SPName**します。</span><span class="sxs-lookup"><span data-stu-id="84c6c-122">From the drop-down list, select **BTS.SPName**.</span></span>|  
    |<span data-ttu-id="84c6c-123">最初の行。**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="84c6c-123">First row: **Operator**</span></span>|<span data-ttu-id="84c6c-124">ドロップダウン リストから選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="84c6c-124">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="84c6c-125">最初の行。**[値]**</span><span class="sxs-lookup"><span data-stu-id="84c6c-125">First row: **Value**</span></span>|<span data-ttu-id="84c6c-126">型**Tutorial_IA_HandleRequest_RealTime**します。</span><span class="sxs-lookup"><span data-stu-id="84c6c-126">Type **Tutorial_IA_HandleRequest_RealTime**.</span></span>|  
    |<span data-ttu-id="84c6c-127">最初の行。**グループ化**</span><span class="sxs-lookup"><span data-stu-id="84c6c-127">First row: **Group by**</span></span>|<span data-ttu-id="84c6c-128">ドロップダウン リストから選択**または**します。</span><span class="sxs-lookup"><span data-stu-id="84c6c-128">From the drop-down list, select **OR**.</span></span>|  
    |<span data-ttu-id="84c6c-129">2 番目の行。**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="84c6c-129">Second row: **Property**</span></span>|<span data-ttu-id="84c6c-130">ドロップダウン リストから選択**BTS します。MessageType**します。</span><span class="sxs-lookup"><span data-stu-id="84c6c-130">From the drop-down list, select **BTS.MessageType**.</span></span>|  
    |<span data-ttu-id="84c6c-131">2 番目の行。**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="84c6c-131">Second row: **Operator**</span></span>|<span data-ttu-id="84c6c-132">ドロップダウン リストから選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="84c6c-132">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="84c6c-133">2 番目の行。**[値]**</span><span class="sxs-lookup"><span data-stu-id="84c6c-133">Second row: **Value**</span></span>|<span data-ttu-id="84c6c-134">型**SwInt ExchangeResponse**します。</span><span class="sxs-lookup"><span data-stu-id="84c6c-134">Type **SwInt-ExchangeResponse**.</span></span>|  
    |<span data-ttu-id="84c6c-135">2 番目の行。**グループ化**</span><span class="sxs-lookup"><span data-stu-id="84c6c-135">Second row: **Group by**</span></span>|<span data-ttu-id="84c6c-136">既定値のままにします。</span><span class="sxs-lookup"><span data-stu-id="84c6c-136">Leave the default value.</span></span>|  
  
9. <span data-ttu-id="84c6c-137">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84c6c-137">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84c6c-138">参照</span><span class="sxs-lookup"><span data-stu-id="84c6c-138">See Also</span></span>  
 <span data-ttu-id="84c6c-139">[ステップ 3:作成する送信と受信ポートを InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="84c6c-139">[Step 3: Create Send and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="84c6c-140">[手順 3 a:ファイル受信場所を追加、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="84c6c-140">[Step 3A: Add a FILE Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="84c6c-141">[手順 3 b:INTERACT の受信場所を追加、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="84c6c-141">[Step 3B: Add an INTERACT Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="84c6c-142">[手順 3 C:用に Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートを追加、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="84c6c-142">[Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="84c6c-143">手順 3 e:用の INTERACT 送信ポートを追加、InterAct リアルタイム シナリオ</span><span class="sxs-lookup"><span data-stu-id="84c6c-143">Step 3E: Add an INTERACT Send Port for the InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3e-add-an-interact-send-port-for-the-interact-real-time-scenario.md)