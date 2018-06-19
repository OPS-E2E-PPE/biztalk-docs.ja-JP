---
title: '手順 3 C: Sw:HandleRequest を取得する FILE 送信ポートの追加のリアルタイムのシナリオを対話 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 31e9c942-ba74-4ae2-b6e1-5266d0fbcb14
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ddc38913b8bf9ea5c9450334e58dfaeb5ff4ad3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224194"
---
# <a name="step-3c-add-file-send-port-to-get-swhandlerequest-interact-real-time-scenario"></a><span data-ttu-id="f9cd4-102">手順 3 C: Sw:HandleRequest を取得する FILE 送信ポートの追加のリアルタイムのシナリオの対話</span><span class="sxs-lookup"><span data-stu-id="f9cd4-102">Step 3C: Add FILE send port to get Sw:HandleRequest-InterAct real-time scenario</span></span>
<span data-ttu-id="f9cd4-103">パートナーにメッセージを送信するときに SWIFT は、メッセージ ヘッダーを変換し、Sw:HandleRequest メッセージとしてパートナーにメッセージを転送します。</span><span class="sxs-lookup"><span data-stu-id="f9cd4-103">When you send a message to your partner, SWIFT transforms the message header and forwards the message to your partner as a Sw:HandleRequest message.</span></span> <span data-ttu-id="f9cd4-104">この手順を開始する前に行う必要があります[手順 3 b: 対話リアルタイム シナリオでは、操作の受信場所を追加](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md)です。</span><span class="sxs-lookup"><span data-stu-id="f9cd4-104">Before you begin this step, you must complete [Step 3B: Add an INTERACT Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md).</span></span>  
  
### <a name="to-add-a-file-send-port-to-capture-swhandlerequest-message"></a><span data-ttu-id="f9cd4-105">Sw:HandleRequest メッセージをキャプチャするポートを送信するファイルを追加するには</span><span class="sxs-lookup"><span data-stu-id="f9cd4-105">To add a FILE send port to capture Sw:HandleRequest message</span></span>  
  
1.  <span data-ttu-id="f9cd4-106">開始**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="f9cd4-106">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="f9cd4-107">コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="f9cd4-107">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="f9cd4-108">右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート。**</span><span class="sxs-lookup"><span data-stu-id="f9cd4-108">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port.**</span></span>  
  
4.  <span data-ttu-id="f9cd4-109">**送信ポートのプロパティ**ウィンドウで、送信ポートの名前**Tutorial_IA_SendResponseToReceiver**です。</span><span class="sxs-lookup"><span data-stu-id="f9cd4-109">In the **Send Port Properties** window, name the send port **Tutorial_IA_SendResponseToReceiver**.</span></span>  
  
5.  <span data-ttu-id="f9cd4-110">**送信ポートのプロパティ** ウィンドウから、**トランスポートの種類**ドロップダウン リストで、**ファイル**、順にクリック**構成**です。</span><span class="sxs-lookup"><span data-stu-id="f9cd4-110">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="f9cd4-111">**FILE トランスポートのプロパティ** ダイアログ ボックスで、**コピー先フォルダー**ボックスに、C:\SWIFTAdapterTutorial\Interact\HandleRequest を入力し、をクリックして**ok**です。</span><span class="sxs-lookup"><span data-stu-id="f9cd4-111">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type C:\SWIFTAdapterTutorial\Interact\HandleRequest, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="f9cd4-112">**送信ポートのプロパティ** ウィンドウで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="f9cd4-112">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="f9cd4-113">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="f9cd4-113">**Use this**</span></span>|<span data-ttu-id="f9cd4-114">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="f9cd4-114">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="f9cd4-115">**送信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="f9cd4-115">**Send handler**</span></span>|<span data-ttu-id="f9cd4-116">ドロップダウン リストから選択**BizTalkServerApplication**です。</span><span class="sxs-lookup"><span data-stu-id="f9cd4-116">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="f9cd4-117">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="f9cd4-117">**Send pipeline**</span></span>|<span data-ttu-id="f9cd4-118">ドロップダウン リストから選択**XMLTransmit**です。</span><span class="sxs-lookup"><span data-stu-id="f9cd4-118">From the drop-down list, select **XMLTransmit**.</span></span>|  
  
8.  <span data-ttu-id="f9cd4-119">**送信ポートのプロパティ** ウィンドウで、**フィルター**  タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="f9cd4-119">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="f9cd4-120">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="f9cd4-120">**Use this**</span></span>|<span data-ttu-id="f9cd4-121">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="f9cd4-121">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="f9cd4-122">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="f9cd4-122">**Property**</span></span>|<span data-ttu-id="f9cd4-123">ドロップダウン リストから選択**BTS です。ReceivePortName**です。</span><span class="sxs-lookup"><span data-stu-id="f9cd4-123">From the drop-down list, select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="f9cd4-124">**演算子**</span><span class="sxs-lookup"><span data-stu-id="f9cd4-124">**Operator**</span></span>|<span data-ttu-id="f9cd4-125">ドロップダウン リストから選択 **==** です。</span><span class="sxs-lookup"><span data-stu-id="f9cd4-125">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="f9cd4-126">**値**</span><span class="sxs-lookup"><span data-stu-id="f9cd4-126">**Value**</span></span>|<span data-ttu-id="f9cd4-127">型**Tutorial_IA_HandleRequestOneWay_RealTime です。**</span><span class="sxs-lookup"><span data-stu-id="f9cd4-127">Type **Tutorial_IA_HandleRequestOneWay_RealTime.**</span></span>|  
    |<span data-ttu-id="f9cd4-128">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="f9cd4-128">**Group by**</span></span>|<span data-ttu-id="f9cd4-129">既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="f9cd4-129">Leave the default value.</span></span>|  
  
9. <span data-ttu-id="f9cd4-130">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9cd4-130">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9cd4-131">参照</span><span class="sxs-lookup"><span data-stu-id="f9cd4-131">See Also</span></span>  
 <span data-ttu-id="f9cd4-132">[手順 3: が送信を作成し、受信のポート、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="f9cd4-132">[Step 3: Create Send and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="f9cd4-133">[手順 3: ファイルの受信場所を追加、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="f9cd4-133">[Step 3A: Add a FILE Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="f9cd4-134">[手順 3 b: 対話の受信場所を追加、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="f9cd4-134">[Step 3B: Add an INTERACT Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="f9cd4-135">[ステップ 3 D: の Sw:HandleResponse メッセージをキャプチャする FILE 送信ポートを追加、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md) </span><span class="sxs-lookup"><span data-stu-id="f9cd4-135">[Step 3D: Add a FILE Send Port to Capture the Sw:HandleResponse Message for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md) </span></span>  
 [<span data-ttu-id="f9cd4-136">ステップ 3 e: 対話する送信ポートの追加、リアルタイムのシナリオの対話</span><span class="sxs-lookup"><span data-stu-id="f9cd4-136">Step 3E: Add an INTERACT Send Port for the InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3e-add-an-interact-send-port-for-the-interact-real-time-scenario.md)