---
title: 手順 2 a:ファイルの受信場所 InterAct ストア アンド フォワード (プル) シナリオの追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: acdc30e1-d80c-40bf-864d-bf136c77a2b8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39fe96e60ea183c4ab9ccde767f9848395191233
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366219"
---
# <a name="step-2a-add-file-receive-locations-for-the-interact-store-and-forward-pull-scenario"></a><span data-ttu-id="645d6-102">手順 2 a:ファイル受信 InterAct ストア アンド フォワード (プル) シナリオ用の場所を追加します。</span><span class="sxs-lookup"><span data-stu-id="645d6-102">Step 2A: Add FILE Receive Locations for the InterAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="645d6-103">この手順を開始する前に行う必要があります[手順 2。InterAct ストア アンド フォワード シナリオ用に Paramfile に SWIFTNet 構成を追加](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-store-and-forward.md)します。</span><span class="sxs-lookup"><span data-stu-id="645d6-103">Before you begin this step, you must complete [Step 2: Add SWIFTNet Configuration to the Paramfile for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-store-and-forward.md).</span></span>  
  
### <a name="to-add-a-file-receive-location"></a><span data-ttu-id="645d6-104">ファイル受信場所を追加するには</span><span class="sxs-lookup"><span data-stu-id="645d6-104">To add a FILE Receive location</span></span>  
  
1.  <span data-ttu-id="645d6-105">開始**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="645d6-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="645d6-106">コンソール ツリーで、BizTalk グループを展開し、受信ポートを作成する BizTalk アプリケーションを順に展開します。</span><span class="sxs-lookup"><span data-stu-id="645d6-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a receive port.</span></span>  
  
3.  <span data-ttu-id="645d6-107">右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート。**</span><span class="sxs-lookup"><span data-stu-id="645d6-107">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
4.  <span data-ttu-id="645d6-108">**受信ポートのプロパティ**ウィンドウで、受信ポート名**Tutorial_IA_InputRequest_SnF**します。</span><span class="sxs-lookup"><span data-stu-id="645d6-108">In the **Receive Port Properties** window, name the receive port, **Tutorial_IA_InputRequest_SnF**.</span></span>  
  
5.  <span data-ttu-id="645d6-109">**受信ポートのプロパティ**ウィンドウで、**受信場所**] タブで [**新規**します。</span><span class="sxs-lookup"><span data-stu-id="645d6-109">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
6.  <span data-ttu-id="645d6-110">**受信場所のプロパティ**ウィンドウの**全般** タブから、**トランスポートの種類**ドロップダウン リストで、**ファイル**とクリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="645d6-110">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="645d6-111">**FILE トランスポートのプロパティ**ダイアログ ボックスに「 **C:\SWIFTAdapterTutorial\Interact\InputRequest_SnF**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="645d6-111">In the **FILE Transport Properties** dialog box, type **C:\SWIFTAdapterTutorial\Interact\InputRequest_SnF**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="645d6-112">**受信場所のプロパティ**ウィンドウの**全般** タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="645d6-112">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="645d6-113">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="645d6-113">**Use this**</span></span>|<span data-ttu-id="645d6-114">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="645d6-114">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="645d6-115">**受信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="645d6-115">**Receive handler**</span></span>|<span data-ttu-id="645d6-116">ドロップダウン リストから選択**BizTalkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="645d6-116">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="645d6-117">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="645d6-117">**Receive pipeline**</span></span>|<span data-ttu-id="645d6-118">ドロップダウン リストから選択**XMLReceive**します。</span><span class="sxs-lookup"><span data-stu-id="645d6-118">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="645d6-119">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="645d6-119">Click **OK**.</span></span>  
  
10. <span data-ttu-id="645d6-120">手順 1. および 2. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="645d6-120">Repeat steps 1 and 2.</span></span>  
  
11. <span data-ttu-id="645d6-121">右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート。**</span><span class="sxs-lookup"><span data-stu-id="645d6-121">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
12. <span data-ttu-id="645d6-122">**受信ポートのプロパティ**ウィンドウで、受信ポート名**Tutorial_IA_InputRequest_PullMode**します。</span><span class="sxs-lookup"><span data-stu-id="645d6-122">In the **Receive Port Properties** window, name the receive port, **Tutorial_IA_InputRequest_PullMode**.</span></span>  
  
13. <span data-ttu-id="645d6-123">**受信ポートのプロパティ**ウィンドウで、**受信場所**] タブで [**新規**します。</span><span class="sxs-lookup"><span data-stu-id="645d6-123">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
14. <span data-ttu-id="645d6-124">**受信場所のプロパティ**ウィンドウの**全般** タブから、**トランスポートの種類**ドロップダウン リストで、**ファイル**とクリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="645d6-124">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
15. <span data-ttu-id="645d6-125">**FILE トランスポートのプロパティ**ダイアログ ボックスに「 **C:\SWIFTAdapterTutorial\Interact\PullRequest**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="645d6-125">In the **FILE Transport Properties** dialog box, type **C:\SWIFTAdapterTutorial\Interact\PullRequest**, and then click **OK**.</span></span>  
  
16. <span data-ttu-id="645d6-126">**受信場所のプロパティ**ウィンドウの**全般** タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="645d6-126">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="645d6-127">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="645d6-127">**Use this**</span></span>|<span data-ttu-id="645d6-128">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="645d6-128">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="645d6-129">**受信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="645d6-129">**Receive handler**</span></span>|<span data-ttu-id="645d6-130">ドロップダウン リストから選択**BizTalkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="645d6-130">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="645d6-131">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="645d6-131">**Receive pipeline**</span></span>|<span data-ttu-id="645d6-132">ドロップダウン リストから選択**XMLReceive**します。</span><span class="sxs-lookup"><span data-stu-id="645d6-132">From the drop-down list, select **XMLReceive**.</span></span>|  
  
17. <span data-ttu-id="645d6-133">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="645d6-133">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="645d6-134">参照</span><span class="sxs-lookup"><span data-stu-id="645d6-134">See Also</span></span>  
 <span data-ttu-id="645d6-135">[手順 2 b:InterAct ストア アンド フォワード (プル) シナリオ用に Sw:HandleRequest メッセージをキャプチャするファイルの送信ポートの追加します。](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md) </span><span class="sxs-lookup"><span data-stu-id="645d6-135">[Step 2B: Add FILE Send Ports to Capture the Sw:HandleRequest Message for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md) </span></span>  
 [<span data-ttu-id="645d6-136">手順 2 C:InterAct ストア アンド フォワード (プル) シナリオ用に INTERACT 送信ポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="645d6-136">Step 2C: Add an INTERACT Send Port for the InterAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-2c-add-interact-send-port-for-interact-store-and-forward-pull-scenario.md)