---
title: 手順 2A - 追加するファイルの受信場所 |Microsoft ドキュメント
description: 手順 2A-追加のファイルは、BizTalk server FileAct ストア アンド フォワード (プル) シナリオの場所を受信
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
ms.openlocfilehash: e297a85f309445c3caf569d2d752be58997e9754
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224074"
---
# <a name="step-2a-add-file-receive-locations-for-the-fileact-store-and-forward-pull-scenario"></a><span data-ttu-id="04efc-103">手順 2 a: ファイルの受信場所 FileAct ストア アンド フォワード (プル) シナリオの追加</span><span class="sxs-lookup"><span data-stu-id="04efc-103">Step 2A: Add FILE Receive Locations for the FileAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="04efc-104">この手順を開始する前に行う必要があります[手順 1: SWIFT アダプター FileAct ストア アンド フォワード (プル) シナリオ用に構成](step-1-configure-the-swift-adapter-for-fileact-store-and-forward-pull-scenario.md)です。</span><span class="sxs-lookup"><span data-stu-id="04efc-104">Before you begin this step, you must complete [Step 1: Configure the SWIFT Adapter for the FileAct Store and Forward (Pull) Scenario](step-1-configure-the-swift-adapter-for-fileact-store-and-forward-pull-scenario.md).</span></span>  
  
## <a name="add-a-file-receive-location"></a><span data-ttu-id="04efc-105">ファイル受信場所を追加します。</span><span class="sxs-lookup"><span data-stu-id="04efc-105">Add a FILE Receive location</span></span>  
  
1.  <span data-ttu-id="04efc-106">開始**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="04efc-106">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="04efc-107">コンソール ツリーで、BizTalk グループを展開し、受信ポートを作成する BizTalk アプリケーションの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="04efc-107">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a receive port.</span></span>  
  
3.  <span data-ttu-id="04efc-108">右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート。**</span><span class="sxs-lookup"><span data-stu-id="04efc-108">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
4.  <span data-ttu-id="04efc-109">**受信ポートのプロパティ**ウィンドウで、受信ポート名**Tutorial_FA_InputRequest_SnF**です。</span><span class="sxs-lookup"><span data-stu-id="04efc-109">In the **Receive Port Properties** window, name the receive port, **Tutorial_FA_InputRequest_SnF**.</span></span>  
  
5.  <span data-ttu-id="04efc-110">**受信ポートのプロパティ** ウィンドウで、**受信場所** タブで、をクリックして**新規**です。</span><span class="sxs-lookup"><span data-stu-id="04efc-110">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
6.  <span data-ttu-id="04efc-111">**受信場所のプロパティ**ウィンドウで、**全般** タブから、**トランスポートの種類**ドロップダウン リストで、**ファイル**とをクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="04efc-111">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="04efc-112">**FILE トランスポートのプロパティ** ダイアログ ボックスで、「 **C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="04efc-112">In the **FILE Transport Properties** dialog box, type **C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="04efc-113">**受信場所のプロパティ** ウィンドウで、**全般** タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="04efc-113">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="04efc-114">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="04efc-114">**Use this**</span></span>|<span data-ttu-id="04efc-115">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="04efc-115">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="04efc-116">**受信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="04efc-116">**Receive handler**</span></span>|<span data-ttu-id="04efc-117">ドロップダウン リストから選択**BizTalkServerApplication**です。</span><span class="sxs-lookup"><span data-stu-id="04efc-117">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="04efc-118">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="04efc-118">**Receive pipeline**</span></span>|<span data-ttu-id="04efc-119">ドロップダウン リストから選択**XMLReceive**です。</span><span class="sxs-lookup"><span data-stu-id="04efc-119">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="04efc-120">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04efc-120">Click **OK**.</span></span>  
  
10. <span data-ttu-id="04efc-121">手順 1. と 2. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="04efc-121">Repeat steps 1 and 2.</span></span>  
  
11. <span data-ttu-id="04efc-122">右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート。**</span><span class="sxs-lookup"><span data-stu-id="04efc-122">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
12. <span data-ttu-id="04efc-123">**受信ポートのプロパティ**ウィンドウで、受信ポート名**Tutorial_ FA_InputRequest_PullMode**です。</span><span class="sxs-lookup"><span data-stu-id="04efc-123">In the **Receive Port Properties** window, name the receive port, **Tutorial_ FA_InputRequest_PullMode**.</span></span>  
  
13. <span data-ttu-id="04efc-124">**受信ポートのプロパティ** ウィンドウで、**受信場所** タブで、をクリックして**新規**です。</span><span class="sxs-lookup"><span data-stu-id="04efc-124">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
14. <span data-ttu-id="04efc-125">**受信場所のプロパティ**ウィンドウで、**全般** タブから、**トランスポートの種類**ドロップダウン リストで、**ファイル**とをクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="04efc-125">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
15. <span data-ttu-id="04efc-126">**FILE トランスポートのプロパティ** ダイアログ ボックスで、「 **C:\SWIFTAdapterTutorial\Interact\PullRequest**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="04efc-126">In the **FILE Transport Properties** dialog box, type **C:\SWIFTAdapterTutorial\Interact\PullRequest**, and then click **OK**.</span></span>  
  
16. <span data-ttu-id="04efc-127">**受信場所のプロパティ** ウィンドウで、**全般** タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="04efc-127">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="04efc-128">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="04efc-128">**Use this**</span></span>|<span data-ttu-id="04efc-129">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="04efc-129">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="04efc-130">**受信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="04efc-130">**Receive handler**</span></span>|<span data-ttu-id="04efc-131">ドロップダウン リストから選択**BizTalkServerApplication**です。</span><span class="sxs-lookup"><span data-stu-id="04efc-131">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="04efc-132">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="04efc-132">**Receive pipeline**</span></span>|<span data-ttu-id="04efc-133">ドロップダウン リストから選択**XMLReceive**です。</span><span class="sxs-lookup"><span data-stu-id="04efc-133">From the drop-down list, select **XMLReceive**.</span></span>|  
  
17. <span data-ttu-id="04efc-134">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04efc-134">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="04efc-135">次の手順</span><span class="sxs-lookup"><span data-stu-id="04efc-135">Next steps</span></span>
-  [<span data-ttu-id="04efc-136">手順 2 b: Sw:HandleFileRequest をキャプチャするファイルの送信ポートを追加し、FileAct ストア アンド フォワードの Sw:HandleSnFRequest メッセージ (プル) のシナリオ</span><span class="sxs-lookup"><span data-stu-id="04efc-136">Step 2B: Add FILE Send Ports to Capture the Sw:HandleFileRequest and Sw:HandleSnFRequest Messages for the FileAct Store and Forward (Pull) Scenario</span></span>](step-2b-add-file-send-ports--get-sw-handlefilerequest-and-sw-handlesnfrequest.md)   
-  [<span data-ttu-id="04efc-137">手順 2 C: FileAct ストア アンド フォワード (プル) シナリオの FILEACT 送信ポートの追加</span><span class="sxs-lookup"><span data-stu-id="04efc-137">Step 2C: Add a FILEACT Send Port for the FileAct Store and Forward (Pull) Scenario</span></span>](step-2c-add-a-fileact-send-port-for-fileact-store-and-forward-pull-scenario.md)