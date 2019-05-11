---
title: 手順 2 a - 追加のファイルの受信場所 |Microsoft Docs
description: 手順 2 a-追加のファイルは、BizTalk server FileAct ストア アンド フォワード (プル) シナリオ用の場所を受信
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 13720ebb-fbe4-4fe1-a095-9ae14c62def1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30311c846b26142e0beeea5ab503dd9599b41e18
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366188"
---
# <a name="step-2a-add-file-receive-locations-for-the-fileact-store-and-forward-pull-scenario"></a><span data-ttu-id="8ecb7-103">手順 2 a:ファイルの受信場所 FileAct ストア アンド フォワード (プル) シナリオの追加します。</span><span class="sxs-lookup"><span data-stu-id="8ecb7-103">Step 2A: Add FILE Receive Locations for the FileAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="8ecb7-104">この手順を開始する前に行う必要があります[手順 1。FileAct ストア アンド フォワード (プル) シナリオ用に SWIFT アダプターを構成する](step-1-configure-the-swift-adapter-for-fileact-store-and-forward-pull-scenario.md)します。</span><span class="sxs-lookup"><span data-stu-id="8ecb7-104">Before you begin this step, you must complete [Step 1: Configure the SWIFT Adapter for the FileAct Store and Forward (Pull) Scenario](step-1-configure-the-swift-adapter-for-fileact-store-and-forward-pull-scenario.md).</span></span>  
  
## <a name="add-a-file-receive-location"></a><span data-ttu-id="8ecb7-105">ファイル受信場所を追加します。</span><span class="sxs-lookup"><span data-stu-id="8ecb7-105">Add a FILE Receive location</span></span>  
  
1.  <span data-ttu-id="8ecb7-106">開始**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="8ecb7-106">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="8ecb7-107">コンソール ツリーで、BizTalk グループを展開し、受信ポートを作成する BizTalk アプリケーションを順に展開します。</span><span class="sxs-lookup"><span data-stu-id="8ecb7-107">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a receive port.</span></span>  
  
3.  <span data-ttu-id="8ecb7-108">右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート。**</span><span class="sxs-lookup"><span data-stu-id="8ecb7-108">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
4.  <span data-ttu-id="8ecb7-109">**受信ポートのプロパティ**ウィンドウで、受信ポート名**Tutorial_FA_InputRequest_SnF**します。</span><span class="sxs-lookup"><span data-stu-id="8ecb7-109">In the **Receive Port Properties** window, name the receive port, **Tutorial_FA_InputRequest_SnF**.</span></span>  
  
5.  <span data-ttu-id="8ecb7-110">**受信ポートのプロパティ**ウィンドウで、**受信場所**] タブで [**新規**します。</span><span class="sxs-lookup"><span data-stu-id="8ecb7-110">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
6.  <span data-ttu-id="8ecb7-111">**受信場所のプロパティ**ウィンドウの**全般** タブから、**トランスポートの種類**ドロップダウン リストで、**ファイル**とクリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="8ecb7-111">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="8ecb7-112">**FILE トランスポートのプロパティ**ダイアログ ボックスに「 **C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="8ecb7-112">In the **FILE Transport Properties** dialog box, type **C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="8ecb7-113">**受信場所のプロパティ**ウィンドウの**全般** タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8ecb7-113">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="8ecb7-114">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="8ecb7-114">**Use this**</span></span>|<span data-ttu-id="8ecb7-115">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="8ecb7-115">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="8ecb7-116">**受信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="8ecb7-116">**Receive handler**</span></span>|<span data-ttu-id="8ecb7-117">ドロップダウン リストから選択**BizTalkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="8ecb7-117">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="8ecb7-118">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="8ecb7-118">**Receive pipeline**</span></span>|<span data-ttu-id="8ecb7-119">ドロップダウン リストから選択**XMLReceive**します。</span><span class="sxs-lookup"><span data-stu-id="8ecb7-119">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="8ecb7-120">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ecb7-120">Click **OK**.</span></span>  
  
10. <span data-ttu-id="8ecb7-121">手順 1. および 2. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="8ecb7-121">Repeat steps 1 and 2.</span></span>  
  
11. <span data-ttu-id="8ecb7-122">右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート。**</span><span class="sxs-lookup"><span data-stu-id="8ecb7-122">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
12. <span data-ttu-id="8ecb7-123">**受信ポートのプロパティ**ウィンドウで、受信ポート名**Tutorial_ FA_InputRequest_PullMode**します。</span><span class="sxs-lookup"><span data-stu-id="8ecb7-123">In the **Receive Port Properties** window, name the receive port, **Tutorial_ FA_InputRequest_PullMode**.</span></span>  
  
13. <span data-ttu-id="8ecb7-124">**受信ポートのプロパティ**ウィンドウで、**受信場所**] タブで [**新規**します。</span><span class="sxs-lookup"><span data-stu-id="8ecb7-124">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
14. <span data-ttu-id="8ecb7-125">**受信場所のプロパティ**ウィンドウの**全般** タブから、**トランスポートの種類**ドロップダウン リストで、**ファイル**とクリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="8ecb7-125">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
15. <span data-ttu-id="8ecb7-126">**FILE トランスポートのプロパティ**ダイアログ ボックスに「 **C:\SWIFTAdapterTutorial\Interact\PullRequest**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="8ecb7-126">In the **FILE Transport Properties** dialog box, type **C:\SWIFTAdapterTutorial\Interact\PullRequest**, and then click **OK**.</span></span>  
  
16. <span data-ttu-id="8ecb7-127">**受信場所のプロパティ**ウィンドウの**全般** タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8ecb7-127">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="8ecb7-128">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="8ecb7-128">**Use this**</span></span>|<span data-ttu-id="8ecb7-129">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="8ecb7-129">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="8ecb7-130">**受信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="8ecb7-130">**Receive handler**</span></span>|<span data-ttu-id="8ecb7-131">ドロップダウン リストから選択**BizTalkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="8ecb7-131">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="8ecb7-132">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="8ecb7-132">**Receive pipeline**</span></span>|<span data-ttu-id="8ecb7-133">ドロップダウン リストから選択**XMLReceive**します。</span><span class="sxs-lookup"><span data-stu-id="8ecb7-133">From the drop-down list, select **XMLReceive**.</span></span>|  
  
17. <span data-ttu-id="8ecb7-134">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ecb7-134">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8ecb7-135">次のステップ</span><span class="sxs-lookup"><span data-stu-id="8ecb7-135">Next steps</span></span>
-  [<span data-ttu-id="8ecb7-136">手順 2 b:FileAct ストア アンド フォワード (プル) シナリオに Sw:HandleFileRequest および Sw:HandleSnFRequest メッセージをキャプチャするファイルの送信ポートの追加します。</span><span class="sxs-lookup"><span data-stu-id="8ecb7-136">Step 2B: Add FILE Send Ports to Capture the Sw:HandleFileRequest and Sw:HandleSnFRequest Messages for the FileAct Store and Forward (Pull) Scenario</span></span>](step-2b-add-file-send-ports--get-sw-handlefilerequest-and-sw-handlesnfrequest.md)   
-  [<span data-ttu-id="8ecb7-137">手順 2 C:FileAct ストア アンド フォワード (プル) シナリオに FILEACT 送信ポートの追加します。</span><span class="sxs-lookup"><span data-stu-id="8ecb7-137">Step 2C: Add a FILEACT Send Port for the FileAct Store and Forward (Pull) Scenario</span></span>](step-2c-add-a-fileact-send-port-for-fileact-store-and-forward-pull-scenario.md)