---
title: "手順 2 a: ファイルの受信場所 InterAct ストア アンド フォワード (プル) シナリオの追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: acdc30e1-d80c-40bf-864d-bf136c77a2b8
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 195480b616437eea7b1cfafa703d4ec5d0bd2b54
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-2a-add-file-receive-locations-for-the-interact-store-and-forward-pull-scenario"></a><span data-ttu-id="07340-102">手順 2 a: ファイルの受信場所 InterAct ストア アンド フォワード (プル) シナリオの追加</span><span class="sxs-lookup"><span data-stu-id="07340-102">Step 2A: Add FILE Receive Locations for the InterAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="07340-103">この手順を開始する前に行う必要があります[手順 2: InterAct ストアと転送シナリオ Paramfile に SWIFTNet 構成を追加](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-store-and-forward.md)です。</span><span class="sxs-lookup"><span data-stu-id="07340-103">Before you begin this step, you must complete [Step 2: Add SWIFTNet Configuration to the Paramfile for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-store-and-forward.md).</span></span>  
  
### <a name="to-add-a-file-receive-location"></a><span data-ttu-id="07340-104">ファイル受信場所を追加するには</span><span class="sxs-lookup"><span data-stu-id="07340-104">To add a FILE Receive location</span></span>  
  
1.  <span data-ttu-id="07340-105">開始**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="07340-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="07340-106">コンソール ツリーで、BizTalk グループを展開し、受信ポートを作成する BizTalk アプリケーションの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="07340-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a receive port.</span></span>  
  
3.  <span data-ttu-id="07340-107">右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート。**</span><span class="sxs-lookup"><span data-stu-id="07340-107">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
4.  <span data-ttu-id="07340-108">**受信ポートのプロパティ**ウィンドウで、受信ポート名**Tutorial_IA_InputRequest_SnF**です。</span><span class="sxs-lookup"><span data-stu-id="07340-108">In the **Receive Port Properties** window, name the receive port, **Tutorial_IA_InputRequest_SnF**.</span></span>  
  
5.  <span data-ttu-id="07340-109">**受信ポートのプロパティ** ウィンドウで、**受信場所** タブで、をクリックして**新規**です。</span><span class="sxs-lookup"><span data-stu-id="07340-109">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
6.  <span data-ttu-id="07340-110">**受信場所のプロパティ**ウィンドウで、**全般** タブから、**トランスポートの種類**ドロップダウン リストで、**ファイル**とをクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="07340-110">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="07340-111">**FILE トランスポートのプロパティ** ダイアログ ボックスで、「 **C:\SWIFTAdapterTutorial\Interact\InputRequest_SnF**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="07340-111">In the **FILE Transport Properties** dialog box, type **C:\SWIFTAdapterTutorial\Interact\InputRequest_SnF**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="07340-112">**受信場所のプロパティ** ウィンドウで、**全般** タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="07340-112">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="07340-113">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="07340-113">**Use this**</span></span>|<span data-ttu-id="07340-114">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="07340-114">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="07340-115">**受信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="07340-115">**Receive handler**</span></span>|<span data-ttu-id="07340-116">ドロップダウン リストから選択**BizTalkServerApplication**です。</span><span class="sxs-lookup"><span data-stu-id="07340-116">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="07340-117">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="07340-117">**Receive pipeline**</span></span>|<span data-ttu-id="07340-118">ドロップダウン リストから選択**XMLReceive**です。</span><span class="sxs-lookup"><span data-stu-id="07340-118">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="07340-119">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07340-119">Click **OK**.</span></span>  
  
10. <span data-ttu-id="07340-120">手順 1. と 2. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="07340-120">Repeat steps 1 and 2.</span></span>  
  
11. <span data-ttu-id="07340-121">右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート。**</span><span class="sxs-lookup"><span data-stu-id="07340-121">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
12. <span data-ttu-id="07340-122">**受信ポートのプロパティ**ウィンドウで、受信ポート名**Tutorial_IA_InputRequest_PullMode**です。</span><span class="sxs-lookup"><span data-stu-id="07340-122">In the **Receive Port Properties** window, name the receive port, **Tutorial_IA_InputRequest_PullMode**.</span></span>  
  
13. <span data-ttu-id="07340-123">**受信ポートのプロパティ** ウィンドウで、**受信場所** タブで、をクリックして**新規**です。</span><span class="sxs-lookup"><span data-stu-id="07340-123">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
14. <span data-ttu-id="07340-124">**受信場所のプロパティ**ウィンドウで、**全般** タブから、**トランスポートの種類**ドロップダウン リストで、**ファイル**とをクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="07340-124">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
15. <span data-ttu-id="07340-125">**FILE トランスポートのプロパティ** ダイアログ ボックスで、「 **C:\SWIFTAdapterTutorial\Interact\PullRequest**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="07340-125">In the **FILE Transport Properties** dialog box, type **C:\SWIFTAdapterTutorial\Interact\PullRequest**, and then click **OK**.</span></span>  
  
16. <span data-ttu-id="07340-126">**受信場所のプロパティ** ウィンドウで、**全般** タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="07340-126">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="07340-127">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="07340-127">**Use this**</span></span>|<span data-ttu-id="07340-128">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="07340-128">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="07340-129">**受信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="07340-129">**Receive handler**</span></span>|<span data-ttu-id="07340-130">ドロップダウン リストから選択**BizTalkServerApplication**です。</span><span class="sxs-lookup"><span data-stu-id="07340-130">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="07340-131">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="07340-131">**Receive pipeline**</span></span>|<span data-ttu-id="07340-132">ドロップダウン リストから選択**XMLReceive**です。</span><span class="sxs-lookup"><span data-stu-id="07340-132">From the drop-down list, select **XMLReceive**.</span></span>|  
  
17. <span data-ttu-id="07340-133">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07340-133">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07340-134">参照</span><span class="sxs-lookup"><span data-stu-id="07340-134">See Also</span></span>  
 <span data-ttu-id="07340-135">[手順 2 b: InterAct ストア アンド フォワード (プル) シナリオの Sw:HandleRequest メッセージをキャプチャするファイルの送信ポートの追加](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md) </span><span class="sxs-lookup"><span data-stu-id="07340-135">[Step 2B: Add FILE Send Ports to Capture the Sw:HandleRequest Message for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md) </span></span>  
 [<span data-ttu-id="07340-136">手順 2 C: InterAct ストア アンド フォワード (プル) シナリオの対話の送信ポートを追加</span><span class="sxs-lookup"><span data-stu-id="07340-136">Step 2C: Add an INTERACT Send Port for the InterAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-2c-add-interact-send-port-for-interact-store-and-forward-pull-scenario.md)