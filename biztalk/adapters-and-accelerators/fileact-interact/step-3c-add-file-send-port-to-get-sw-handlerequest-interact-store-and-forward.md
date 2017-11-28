---
title: "手順 3 C: Sw:HandleRequest を取得する FILE 送信ポートの追加-対話ストア アンド フォワード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c872b4be-ef8b-4e42-b5ef-63dfd120793f
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b82c57f2f3a6e2fcfc199e56d34c44aa7667451d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3c-add-file-send-port-to-get-swhandlerequest-interact-store-and-forward"></a><span data-ttu-id="7a066-102">手順 3 C: Sw:HandleRequest を取得する FILE 送信ポートの追加-対話ストア アンド フォワード</span><span class="sxs-lookup"><span data-stu-id="7a066-102">Step 3C: Add FILE send port to get Sw:HandleRequest-InterAct Store and Forward</span></span>
<span data-ttu-id="7a066-103">この手順を開始する前に行う必要があります[手順 3 b: InterAct ストア アンド フォワードのシナリオの対話を受信場所を追加](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md)です。</span><span class="sxs-lookup"><span data-stu-id="7a066-103">Before you begin this step, you must complete [Step 3B: Add an INTERACT Receive Location for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md).</span></span>  
  
### <a name="to-add-a-file-send-port-to-capture-the-swhandlerequest-message"></a><span data-ttu-id="7a066-104">Sw:HandleRequest メッセージをキャプチャするポートを送信するファイルを追加するには</span><span class="sxs-lookup"><span data-stu-id="7a066-104">To add a FILE send port to capture the Sw:HandleRequest message</span></span>  
  
1.  <span data-ttu-id="7a066-105">開始**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="7a066-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="7a066-106">コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="7a066-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="7a066-107">右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート。**</span><span class="sxs-lookup"><span data-stu-id="7a066-107">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port.**</span></span>  
  
4.  <span data-ttu-id="7a066-108">**送信ポートのプロパティ**ウィンドウで、名前、送信ポートを Tutorial_IA_SendResponseToReceiver です。</span><span class="sxs-lookup"><span data-stu-id="7a066-108">In the **Send Port Properties** window, name the send port, Tutorial_IA_SendResponseToReceiver.</span></span>  
  
5.  <span data-ttu-id="7a066-109">**送信ポートのプロパティ** ウィンドウから、**トランスポートの種類**ドロップダウン リストで、**ファイル**、順にクリック**構成**です。</span><span class="sxs-lookup"><span data-stu-id="7a066-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="7a066-110">**FILE トランスポートのプロパティ** ダイアログ ボックスで、**コピー先フォルダー**ボックスに、C:\SWIFTAdapterTutorial\Interact\HandleRequest を入力し、をクリックして**ok**です。</span><span class="sxs-lookup"><span data-stu-id="7a066-110">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type C:\SWIFTAdapterTutorial\Interact\HandleRequest, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="7a066-111">**送信ポートのプロパティ** ウィンドウで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="7a066-111">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="7a066-112">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="7a066-112">**Use this**</span></span>|<span data-ttu-id="7a066-113">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="7a066-113">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="7a066-114">**送信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="7a066-114">**Send handler**</span></span>|<span data-ttu-id="7a066-115">ドロップダウン リストから選択**BizTalkServerApplication**です。</span><span class="sxs-lookup"><span data-stu-id="7a066-115">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="7a066-116">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="7a066-116">**Send pipeline**</span></span>|<span data-ttu-id="7a066-117">ドロップダウン リストから選択**XMLTransmit**です。</span><span class="sxs-lookup"><span data-stu-id="7a066-117">From the drop-down list, select **XMLTransmit**.</span></span>|  
  
8.  <span data-ttu-id="7a066-118">**送信ポートのプロパティ** ウィンドウで、**フィルター**  タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="7a066-118">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="7a066-119">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="7a066-119">**Use this**</span></span>|<span data-ttu-id="7a066-120">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="7a066-120">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="7a066-121">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="7a066-121">**Property**</span></span>|<span data-ttu-id="7a066-122">ドロップダウン リストから選択**BTS です。ReceivePortName**です。</span><span class="sxs-lookup"><span data-stu-id="7a066-122">From the drop-down list, select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="7a066-123">**演算子**</span><span class="sxs-lookup"><span data-stu-id="7a066-123">**Operator**</span></span>|<span data-ttu-id="7a066-124">ドロップダウン リストから選択 **==**です。</span><span class="sxs-lookup"><span data-stu-id="7a066-124">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="7a066-125">**値**</span><span class="sxs-lookup"><span data-stu-id="7a066-125">**Value**</span></span>|<span data-ttu-id="7a066-126">型**Tutorial_IA_InputRequest_SnF**です。</span><span class="sxs-lookup"><span data-stu-id="7a066-126">Type **Tutorial_IA_InputRequest_SnF**.</span></span>|  
    |<span data-ttu-id="7a066-127">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="7a066-127">**Group by**</span></span>|<span data-ttu-id="7a066-128">既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="7a066-128">Leave the default value.</span></span>|  
  
9. <span data-ttu-id="7a066-129">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a066-129">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a066-130">参照</span><span class="sxs-lookup"><span data-stu-id="7a066-130">See Also</span></span>  
 <span data-ttu-id="7a066-131">[手順 3: 送信ポートを作成し、対話ストアと転送シナリオの受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="7a066-131">[Step 3: Create Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="7a066-132">[手順 3: ファイルの受信場所が、対話ストアと転送シナリオの追加](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="7a066-132">[Step 3A: Add a FILE Receive Location for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="7a066-133">[手順 3 b: 追加、対話の受信場所が、対話ストアと転送シナリオ](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="7a066-133">[Step 3B: Add an INTERACT Receive Location for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="7a066-134">ステップ 3 D: InterAct ストアと転送シナリオの対話の送信ポートの追加</span><span class="sxs-lookup"><span data-stu-id="7a066-134">Step 3D: Add an INTERACT Send Port for the InterAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3d-add-an-interact-send-port-for-the-interact-store-and-forward-scenario.md)