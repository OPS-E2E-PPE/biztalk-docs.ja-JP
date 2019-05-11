---
title: 手順 3 C:FILE 送信ポート Sw:HandleRequest を取得する追加の InterAct リアルタイム シナリオ |Microsoft Docs
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
ms.openlocfilehash: 2a1deeb12f4af2cf5540217463c211f31a385ba3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365670"
---
# <a name="step-3c-add-file-send-port-to-get-swhandlerequest-interact-real-time-scenario"></a><span data-ttu-id="50312-102">手順 3 C:FILE 送信ポート Sw:HandleRequest を取得する追加の InterAct リアルタイム シナリオ</span><span class="sxs-lookup"><span data-stu-id="50312-102">Step 3C: Add FILE send port to get Sw:HandleRequest-InterAct real-time scenario</span></span>
<span data-ttu-id="50312-103">パートナーにメッセージを送信するときに、SWIFT はメッセージ ヘッダーを変換し、Sw:HandleRequest メッセージとしてパートナーにメッセージを転送します。</span><span class="sxs-lookup"><span data-stu-id="50312-103">When you send a message to your partner, SWIFT transforms the message header and forwards the message to your partner as a Sw:HandleRequest message.</span></span> <span data-ttu-id="50312-104">この手順を開始する前に行う必要があります[手順 3 b:INTERACT の受信場所を追加、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md)します。</span><span class="sxs-lookup"><span data-stu-id="50312-104">Before you begin this step, you must complete [Step 3B: Add an INTERACT Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md).</span></span>  
  
### <a name="to-add-a-file-send-port-to-capture-swhandlerequest-message"></a><span data-ttu-id="50312-105">ファイルを追加するには、送信の Sw:HandleRequest メッセージをキャプチャするポート</span><span class="sxs-lookup"><span data-stu-id="50312-105">To add a FILE send port to capture Sw:HandleRequest message</span></span>  
  
1.  <span data-ttu-id="50312-106">開始**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="50312-106">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="50312-107">コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションを順に展開します。</span><span class="sxs-lookup"><span data-stu-id="50312-107">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="50312-108">右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート。**</span><span class="sxs-lookup"><span data-stu-id="50312-108">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port.**</span></span>  
  
4.  <span data-ttu-id="50312-109">**送信ポートのプロパティ**ウィンドウで、送信ポート名**Tutorial_IA_SendResponseToReceiver**します。</span><span class="sxs-lookup"><span data-stu-id="50312-109">In the **Send Port Properties** window, name the send port **Tutorial_IA_SendResponseToReceiver**.</span></span>  
  
5.  <span data-ttu-id="50312-110">**送信ポートのプロパティ**ウィンドウから、**トランスポートの種類**ドロップダウン リストで、**ファイル**、 をクリックし、**構成**。</span><span class="sxs-lookup"><span data-stu-id="50312-110">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="50312-111">**FILE トランスポートのプロパティ** ダイアログ ボックスで、**先フォルダー**ボックスに、C:\SWIFTAdapterTutorial\Interact\HandleRequest を入力し、 をクリックし、 **ok**します。</span><span class="sxs-lookup"><span data-stu-id="50312-111">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type C:\SWIFTAdapterTutorial\Interact\HandleRequest, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="50312-112">**送信ポートのプロパティ**ウィンドウで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="50312-112">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="50312-113">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="50312-113">**Use this**</span></span>|<span data-ttu-id="50312-114">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="50312-114">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="50312-115">**送信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="50312-115">**Send handler**</span></span>|<span data-ttu-id="50312-116">ドロップダウン リストから選択**BizTalkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="50312-116">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="50312-117">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="50312-117">**Send pipeline**</span></span>|<span data-ttu-id="50312-118">ドロップダウン リストから選択**XMLTransmit**します。</span><span class="sxs-lookup"><span data-stu-id="50312-118">From the drop-down list, select **XMLTransmit**.</span></span>|  
  
8.  <span data-ttu-id="50312-119">**送信ポートのプロパティ**ウィンドウで、**フィルター**  タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="50312-119">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="50312-120">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="50312-120">**Use this**</span></span>|<span data-ttu-id="50312-121">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="50312-121">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="50312-122">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="50312-122">**Property**</span></span>|<span data-ttu-id="50312-123">ドロップダウン リストから選択**BTS します。ReceivePortName**します。</span><span class="sxs-lookup"><span data-stu-id="50312-123">From the drop-down list, select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="50312-124">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="50312-124">**Operator**</span></span>|<span data-ttu-id="50312-125">ドロップダウン リストから選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="50312-125">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="50312-126">**[値]**</span><span class="sxs-lookup"><span data-stu-id="50312-126">**Value**</span></span>|<span data-ttu-id="50312-127">型**Tutorial_IA_HandleRequestOneWay_RealTime します。**</span><span class="sxs-lookup"><span data-stu-id="50312-127">Type **Tutorial_IA_HandleRequestOneWay_RealTime.**</span></span>|  
    |<span data-ttu-id="50312-128">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="50312-128">**Group by**</span></span>|<span data-ttu-id="50312-129">既定値のままにします。</span><span class="sxs-lookup"><span data-stu-id="50312-129">Leave the default value.</span></span>|  
  
9. <span data-ttu-id="50312-130">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50312-130">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50312-131">参照</span><span class="sxs-lookup"><span data-stu-id="50312-131">See Also</span></span>  
 <span data-ttu-id="50312-132">[ステップ 3:作成する送信と受信ポートを InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="50312-132">[Step 3: Create Send and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="50312-133">[手順 3 a:ファイル受信場所を追加、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="50312-133">[Step 3A: Add a FILE Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="50312-134">[手順 3 b:INTERACT の受信場所を追加、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="50312-134">[Step 3B: Add an INTERACT Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="50312-135">[手順 3 D:用に Sw:HandleResponse メッセージをキャプチャする FILE 送信ポートを追加、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md) </span><span class="sxs-lookup"><span data-stu-id="50312-135">[Step 3D: Add a FILE Send Port to Capture the Sw:HandleResponse Message for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md) </span></span>  
 [<span data-ttu-id="50312-136">手順 3 e:用の INTERACT 送信ポートを追加、InterAct リアルタイム シナリオ</span><span class="sxs-lookup"><span data-stu-id="50312-136">Step 3E: Add an INTERACT Send Port for the InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3e-add-an-interact-send-port-for-the-interact-real-time-scenario.md)