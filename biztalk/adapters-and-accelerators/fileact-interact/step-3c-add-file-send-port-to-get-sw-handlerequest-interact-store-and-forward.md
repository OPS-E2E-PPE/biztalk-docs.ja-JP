---
title: 手順 3 C:FILE 送信ポート Sw:HandleRequest を取得する追加の操作のストア アンド フォワード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c872b4be-ef8b-4e42-b5ef-63dfd120793f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16941c97e1ee74d9cefc1cc2b70e36ec743a8a20
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365521"
---
# <a name="step-3c-add-file-send-port-to-get-swhandlerequest-interact-store-and-forward"></a><span data-ttu-id="2bb1e-102">手順 3 C:FILE 送信ポート Sw:HandleRequest を取得する追加の操作のストア アンド フォワード</span><span class="sxs-lookup"><span data-stu-id="2bb1e-102">Step 3C: Add FILE send port to get Sw:HandleRequest-InterAct Store and Forward</span></span>
<span data-ttu-id="2bb1e-103">この手順を開始する前に行う必要があります[手順 3 b:InterAct ストア アンド フォワード シナリオ用の場所の受信、INTERACT 追加](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md)します。</span><span class="sxs-lookup"><span data-stu-id="2bb1e-103">Before you begin this step, you must complete [Step 3B: Add an INTERACT Receive Location for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md).</span></span>  
  
### <a name="to-add-a-file-send-port-to-capture-the-swhandlerequest-message"></a><span data-ttu-id="2bb1e-104">ファイルを追加するには、送信の Sw:HandleRequest メッセージをキャプチャするポート</span><span class="sxs-lookup"><span data-stu-id="2bb1e-104">To add a FILE send port to capture the Sw:HandleRequest message</span></span>  
  
1.  <span data-ttu-id="2bb1e-105">開始**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="2bb1e-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="2bb1e-106">コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションを順に展開します。</span><span class="sxs-lookup"><span data-stu-id="2bb1e-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="2bb1e-107">右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート。**</span><span class="sxs-lookup"><span data-stu-id="2bb1e-107">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port.**</span></span>  
  
4.  <span data-ttu-id="2bb1e-108">**送信ポートのプロパティ**ウィンドウで、名前、送信ポート Tutorial_IA_SendResponseToReceiver します。</span><span class="sxs-lookup"><span data-stu-id="2bb1e-108">In the **Send Port Properties** window, name the send port, Tutorial_IA_SendResponseToReceiver.</span></span>  
  
5.  <span data-ttu-id="2bb1e-109">**送信ポートのプロパティ**ウィンドウから、**トランスポートの種類**ドロップダウン リストで、**ファイル**、 をクリックし、**構成**。</span><span class="sxs-lookup"><span data-stu-id="2bb1e-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="2bb1e-110">**FILE トランスポートのプロパティ** ダイアログ ボックスで、**先フォルダー**ボックスに、C:\SWIFTAdapterTutorial\Interact\HandleRequest を入力し、 をクリックし、 **ok**します。</span><span class="sxs-lookup"><span data-stu-id="2bb1e-110">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type C:\SWIFTAdapterTutorial\Interact\HandleRequest, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="2bb1e-111">**送信ポートのプロパティ**ウィンドウで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2bb1e-111">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="2bb1e-112">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="2bb1e-112">**Use this**</span></span>|<span data-ttu-id="2bb1e-113">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="2bb1e-113">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="2bb1e-114">**送信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="2bb1e-114">**Send handler**</span></span>|<span data-ttu-id="2bb1e-115">ドロップダウン リストから選択**BizTalkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="2bb1e-115">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="2bb1e-116">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="2bb1e-116">**Send pipeline**</span></span>|<span data-ttu-id="2bb1e-117">ドロップダウン リストから選択**XMLTransmit**します。</span><span class="sxs-lookup"><span data-stu-id="2bb1e-117">From the drop-down list, select **XMLTransmit**.</span></span>|  
  
8.  <span data-ttu-id="2bb1e-118">**送信ポートのプロパティ**ウィンドウで、**フィルター**  タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2bb1e-118">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="2bb1e-119">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="2bb1e-119">**Use this**</span></span>|<span data-ttu-id="2bb1e-120">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="2bb1e-120">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="2bb1e-121">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="2bb1e-121">**Property**</span></span>|<span data-ttu-id="2bb1e-122">ドロップダウン リストから選択**BTS します。ReceivePortName**します。</span><span class="sxs-lookup"><span data-stu-id="2bb1e-122">From the drop-down list, select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="2bb1e-123">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="2bb1e-123">**Operator**</span></span>|<span data-ttu-id="2bb1e-124">ドロップダウン リストから選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="2bb1e-124">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="2bb1e-125">**[値]**</span><span class="sxs-lookup"><span data-stu-id="2bb1e-125">**Value**</span></span>|<span data-ttu-id="2bb1e-126">型**Tutorial_IA_InputRequest_SnF**します。</span><span class="sxs-lookup"><span data-stu-id="2bb1e-126">Type **Tutorial_IA_InputRequest_SnF**.</span></span>|  
    |<span data-ttu-id="2bb1e-127">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="2bb1e-127">**Group by**</span></span>|<span data-ttu-id="2bb1e-128">既定値のままにします。</span><span class="sxs-lookup"><span data-stu-id="2bb1e-128">Leave the default value.</span></span>|  
  
9. <span data-ttu-id="2bb1e-129">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2bb1e-129">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bb1e-130">参照</span><span class="sxs-lookup"><span data-stu-id="2bb1e-130">See Also</span></span>  
 <span data-ttu-id="2bb1e-131">[ステップ 3:送信ポートの作成し、InterAct ストア アンド フォワード シナリオ用の受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="2bb1e-131">[Step 3: Create Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="2bb1e-132">[手順 3 a:InterAct ストア アンド フォワード シナリオ用の場所の受信ファイルを追加します。](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="2bb1e-132">[Step 3A: Add a FILE Receive Location for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="2bb1e-133">[手順 3 b:INTERACT の受信場所 InterAct ストア アンド フォワード シナリオ用の追加します。](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="2bb1e-133">[Step 3B: Add an INTERACT Receive Location for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="2bb1e-134">手順 3 D:InterAct ストア アンド フォワード シナリオ用に INTERACT 送信ポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="2bb1e-134">Step 3D: Add an INTERACT Send Port for the InterAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3d-add-an-interact-send-port-for-the-interact-store-and-forward-scenario.md)