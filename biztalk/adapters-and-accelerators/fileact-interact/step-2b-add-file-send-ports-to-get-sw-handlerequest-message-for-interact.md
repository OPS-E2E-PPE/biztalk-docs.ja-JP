---
title: "手順 2 b: InterAct ストア アンド フォワード (プル) シナリオの Sw:HandleRequest メッセージをキャプチャするファイルの送信ポートの追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aa22d6e7-f1bd-43ad-9a0e-0b287057d20f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24200d21ef4a2047b94f9d818864a0a9da2ceb3b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-2b-add-file-send-ports-to-capture-the-swhandlerequest-message-for-the-interact-store-and-forward-pull-scenario"></a><span data-ttu-id="e6d83-102">手順 2 b: InterAct ストア アンド フォワード (プル) シナリオの Sw:HandleRequest メッセージをキャプチャするファイルの送信ポートの追加</span><span class="sxs-lookup"><span data-stu-id="e6d83-102">Step 2B: Add FILE Send Ports to Capture the Sw:HandleRequest Message for the InterAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="e6d83-103">この手順を開始する前に行う必要があります[Step 2 a: InterAct ストア アンド フォワード (プル) シナリオ用のファイル受信場所の追加](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md)です。</span><span class="sxs-lookup"><span data-stu-id="e6d83-103">Before you begin this step, you must complete [Step 2A: Add FILE Receive Locations for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md).</span></span>  
  
### <a name="to-add-a-file-send-port-to-capture-the-swhandlerequest-message"></a><span data-ttu-id="e6d83-104">Sw:HandleRequest メッセージをキャプチャするポートを送信するファイルを追加するには</span><span class="sxs-lookup"><span data-stu-id="e6d83-104">To add a FILE send port to capture the Sw:HandleRequest message</span></span>  
  
1.  <span data-ttu-id="e6d83-105">開始**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="e6d83-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="e6d83-106">コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="e6d83-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="e6d83-107">右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート。**</span><span class="sxs-lookup"><span data-stu-id="e6d83-107">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port.**</span></span>  
  
4.  <span data-ttu-id="e6d83-108">**送信ポートのプロパティ**ウィンドウで、名前、送信ポートを**Tutorial_IA_SendPullResponsetoReceiver**です。</span><span class="sxs-lookup"><span data-stu-id="e6d83-108">In the **Send Port Properties** window, name the send port, **Tutorial_IA_SendPullResponsetoReceiver**.</span></span>  
  
5.  <span data-ttu-id="e6d83-109">**送信ポートのプロパティ** ウィンドウから、**トランスポートの種類**ドロップダウン リストで、**ファイル**、順にクリック**構成**です。</span><span class="sxs-lookup"><span data-stu-id="e6d83-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="e6d83-110">**FILE トランスポートのプロパティ** ダイアログ ボックスで、**コピー先フォルダー**ボックスに、入力**C:\SWIFTAdapterTutorial\Interact\PullResponse**をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="e6d83-110">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type **C:\SWIFTAdapterTutorial\Interact\PullResponse**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="e6d83-111">**送信ポートのプロパティ** ウィンドウで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="e6d83-111">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="e6d83-112">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="e6d83-112">**Use this**</span></span>|<span data-ttu-id="e6d83-113">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="e6d83-113">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="e6d83-114">**送信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="e6d83-114">**Send handler**</span></span>|<span data-ttu-id="e6d83-115">ドロップダウン リストから選択**BizTalkServerApplication**です。</span><span class="sxs-lookup"><span data-stu-id="e6d83-115">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="e6d83-116">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="e6d83-116">**Send pipeline**</span></span>|<span data-ttu-id="e6d83-117">ドロップダウン リストから選択**XMLTransmit**です。</span><span class="sxs-lookup"><span data-stu-id="e6d83-117">From the drop-down list, select **XMLTransmit**.</span></span>|  
  
8.  <span data-ttu-id="e6d83-118">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6d83-118">Click **OK**.</span></span>  
  
9. <span data-ttu-id="e6d83-119">手順 1. および 2. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e6d83-119">Repeat step 1 and 2.</span></span>  
  
10. <span data-ttu-id="e6d83-120">右クリック**送信ポート**、 をポイント**新規**、クリックして**動的な送信請求-応答送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="e6d83-120">Right-click **Send Ports**, point to **New**, and then click **Dynamic Solicit-Response Send Port**.</span></span>  
  
11. <span data-ttu-id="e6d83-121">**送信ポートのプロパティ**ウィンドウで、送信ポートの名前**、Tutorial_IA_DynamicSendPort**です。</span><span class="sxs-lookup"><span data-stu-id="e6d83-121">In the **Send Port Properties** window, name the send port**, Tutorial_IA_DynamicSendPort**.</span></span>  
  
12. <span data-ttu-id="e6d83-122">**送信ポートのプロパティ** ウィンドウで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="e6d83-122">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="e6d83-123">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="e6d83-123">**Use this**</span></span>|<span data-ttu-id="e6d83-124">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="e6d83-124">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="e6d83-125">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="e6d83-125">**Send pipeline**</span></span>|<span data-ttu-id="e6d83-126">ドロップダウン リストから選択**XMLTransmit**です。</span><span class="sxs-lookup"><span data-stu-id="e6d83-126">From the drop-down list, select **XMLTransmit**.</span></span>|  
    |<span data-ttu-id="e6d83-127">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="e6d83-127">**Receive pipeline**</span></span>|<span data-ttu-id="e6d83-128">ドロップダウン リストから選択**XMLReceive**です。</span><span class="sxs-lookup"><span data-stu-id="e6d83-128">From the drop-down list, select **XMLReceive**.</span></span>|  
  
13. <span data-ttu-id="e6d83-129">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6d83-129">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6d83-130">参照</span><span class="sxs-lookup"><span data-stu-id="e6d83-130">See Also</span></span>  
 <span data-ttu-id="e6d83-131">[手順 2 a: ファイルの受信場所 InterAct ストア アンド フォワード (プル) シナリオの追加](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="e6d83-131">[Step 2A: Add FILE Receive Locations for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="e6d83-132">手順 2 C: InterAct ストア アンド フォワード (プル) シナリオの対話の送信ポートを追加</span><span class="sxs-lookup"><span data-stu-id="e6d83-132">Step 2C: Add an INTERACT Send Port for the InterAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-2c-add-interact-send-port-for-interact-store-and-forward-pull-scenario.md)