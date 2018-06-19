---
title: 'ステップ 3 D: の Sw:HandleResponse メッセージをキャプチャする FILE 送信ポートを追加、リアルタイムのシナリオを対話 |Microsoft ドキュメント'
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
ms.openlocfilehash: 5a0c8c8721d9f7de7b1cd1e57537aa02d2ed8fd5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225890"
---
# <a name="step-3d-add-a-file-send-port-to-capture-the-swhandleresponse-message-for-the-interact-real-time-scenario"></a><span data-ttu-id="a501a-102">ステップ 3 D: の Sw:HandleResponse メッセージをキャプチャする FILE 送信ポートを追加、リアルタイムのシナリオの対話</span><span class="sxs-lookup"><span data-stu-id="a501a-102">Step 3D: Add a FILE Send Port to Capture the Sw:HandleResponse Message for the InterAct Real-Time Scenario</span></span>
<span data-ttu-id="a501a-103">完全な[手順 3 C: リアルタイム シナリオでは対話 Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートを追加](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md)この手順を開始する前にします。</span><span class="sxs-lookup"><span data-stu-id="a501a-103">Complete [Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md) before you begin this step.</span></span>
  
## <a name="add-a-file-send-port-to-capture-swhandleresponse-message"></a><span data-ttu-id="a501a-104">ファイル送信 Sw:HandleResponse メッセージをキャプチャするポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="a501a-104">Add a FILE send port to capture Sw:HandleResponse message</span></span>  
  
1.  <span data-ttu-id="a501a-105">開始**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="a501a-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="a501a-106">コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="a501a-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="a501a-107">右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート。**</span><span class="sxs-lookup"><span data-stu-id="a501a-107">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port.**</span></span>  
  
4.  <span data-ttu-id="a501a-108">**送信ポートのプロパティ**ウィンドウで、送信ポートの名前**Tutorial_IA_SendResponseToSender**です。</span><span class="sxs-lookup"><span data-stu-id="a501a-108">In the **Send Port Properties** window, name the send port **Tutorial_IA_SendResponseToSender**.</span></span>  
  
5.  <span data-ttu-id="a501a-109">**送信ポートのプロパティ** ウィンドウから、 **Transporttype**ドロップダウン リストで、**ファイル**、順にクリック**構成**です。</span><span class="sxs-lookup"><span data-stu-id="a501a-109">In the **Send Port Properties** window, from the **Transporttype** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="a501a-110">**FILE トランスポートのプロパティ** ダイアログ ボックスで、**コピー先フォルダー**ボックスに、入力**C:\SWIFTAdapterTutorial\Interact\Response**をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="a501a-110">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type **C:\SWIFTAdapterTutorial\Interact\Response**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="a501a-111">**送信ポートのプロパティ** ウィンドウで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="a501a-111">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="a501a-112">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="a501a-112">**Use this**</span></span>|<span data-ttu-id="a501a-113">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="a501a-113">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="a501a-114">**送信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="a501a-114">**Send handler**</span></span>|<span data-ttu-id="a501a-115">ドロップダウン リストから選択**BizTalkServerApplication**です。</span><span class="sxs-lookup"><span data-stu-id="a501a-115">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="a501a-116">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="a501a-116">**Send pipeline**</span></span>|<span data-ttu-id="a501a-117">ドロップダウン リストから選択**XMLTransmit**です。</span><span class="sxs-lookup"><span data-stu-id="a501a-117">From the drop-down list, select **XMLTransmit**.</span></span>|  
  
8.  <span data-ttu-id="a501a-118">**送信ポートのプロパティ** ウィンドウで、**フィルター**  タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="a501a-118">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="a501a-119">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="a501a-119">**Use this**</span></span>|<span data-ttu-id="a501a-120">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="a501a-120">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="a501a-121">最初の行:**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="a501a-121">First row: **Property**</span></span>|<span data-ttu-id="a501a-122">ドロップダウン リストから選択**BTS です。SPName**です。</span><span class="sxs-lookup"><span data-stu-id="a501a-122">From the drop-down list, select **BTS.SPName**.</span></span>|  
    |<span data-ttu-id="a501a-123">最初の行:**演算子**</span><span class="sxs-lookup"><span data-stu-id="a501a-123">First row: **Operator**</span></span>|<span data-ttu-id="a501a-124">ドロップダウン リストから選択 **==** です。</span><span class="sxs-lookup"><span data-stu-id="a501a-124">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="a501a-125">最初の行:**値**</span><span class="sxs-lookup"><span data-stu-id="a501a-125">First row: **Value**</span></span>|<span data-ttu-id="a501a-126">型**Tutorial_IA_HandleRequest_RealTime**です。</span><span class="sxs-lookup"><span data-stu-id="a501a-126">Type **Tutorial_IA_HandleRequest_RealTime**.</span></span>|  
    |<span data-ttu-id="a501a-127">最初の行:**でグループ化**</span><span class="sxs-lookup"><span data-stu-id="a501a-127">First row: **Group by**</span></span>|<span data-ttu-id="a501a-128">ドロップダウン リストから選択**または**です。</span><span class="sxs-lookup"><span data-stu-id="a501a-128">From the drop-down list, select **OR**.</span></span>|  
    |<span data-ttu-id="a501a-129">2 番目の行:**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="a501a-129">Second row: **Property**</span></span>|<span data-ttu-id="a501a-130">ドロップダウン リストから選択**BTS です。MessageType**です。</span><span class="sxs-lookup"><span data-stu-id="a501a-130">From the drop-down list, select **BTS.MessageType**.</span></span>|  
    |<span data-ttu-id="a501a-131">2 番目の行:**演算子**</span><span class="sxs-lookup"><span data-stu-id="a501a-131">Second row: **Operator**</span></span>|<span data-ttu-id="a501a-132">ドロップダウン リストから選択 **==** です。</span><span class="sxs-lookup"><span data-stu-id="a501a-132">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="a501a-133">2 番目の行:**値**</span><span class="sxs-lookup"><span data-stu-id="a501a-133">Second row: **Value**</span></span>|<span data-ttu-id="a501a-134">型**SwInt ExchangeResponse**です。</span><span class="sxs-lookup"><span data-stu-id="a501a-134">Type **SwInt-ExchangeResponse**.</span></span>|  
    |<span data-ttu-id="a501a-135">2 番目の行:**でグループ化**</span><span class="sxs-lookup"><span data-stu-id="a501a-135">Second row: **Group by**</span></span>|<span data-ttu-id="a501a-136">既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="a501a-136">Leave the default value.</span></span>|  
  
9. <span data-ttu-id="a501a-137">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a501a-137">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a501a-138">参照</span><span class="sxs-lookup"><span data-stu-id="a501a-138">See Also</span></span>  
 <span data-ttu-id="a501a-139">[手順 3: が送信を作成し、受信のポート、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="a501a-139">[Step 3: Create Send and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="a501a-140">[手順 3: ファイルの受信場所を追加、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="a501a-140">[Step 3A: Add a FILE Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="a501a-141">[手順 3 b: 対話の受信場所を追加、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="a501a-141">[Step 3B: Add an INTERACT Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="a501a-142">[手順 3 C: の Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートを追加、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="a501a-142">[Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="a501a-143">ステップ 3 e: 対話する送信ポートの追加、リアルタイムのシナリオの対話</span><span class="sxs-lookup"><span data-stu-id="a501a-143">Step 3E: Add an INTERACT Send Port for the InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3e-add-an-interact-send-port-for-the-interact-real-time-scenario.md)