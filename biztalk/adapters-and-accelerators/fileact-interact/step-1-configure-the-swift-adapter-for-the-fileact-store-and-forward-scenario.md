---
title: "手順 1: FileAct ストア アンド フォワードのシナリオ用のアダプターを SWIFT の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 18653322-b748-4954-93f7-9a7a39e406f8
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d2946bcd37e0e7641a2d3bf750f88cd3199fc74
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario"></a><span data-ttu-id="9bc2e-102">手順 1: FileAct ストア アンド フォワードのシナリオ用 SWIFT アダプターを構成します。</span><span class="sxs-lookup"><span data-stu-id="9bc2e-102">Step 1: Configure the SWIFT Adapter for the FileAct Store and Forward Scenario</span></span>
<span data-ttu-id="9bc2e-103">完全な[、チュートリアルを使用する準備](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md)この手順を開始する前にします。</span><span class="sxs-lookup"><span data-stu-id="9bc2e-103">Complete [Preparing to Use the Tutorial](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md) before you begin this step.</span></span>
  
## <a name="configure-the-swift-adapter"></a><span data-ttu-id="9bc2e-104">SWIFT のアダプターを構成します。</span><span class="sxs-lookup"><span data-stu-id="9bc2e-104">Configure the SWIFT adapter</span></span>  
  
1.  <span data-ttu-id="9bc2e-105">開始**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="9bc2e-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="9bc2e-106">コンソール ツリーで  **BizTalk Server 管理コンソール**、BizTalk グループを展開し、**プラットフォームの設定**、展開**アダプター**を右クリックして**FILEACT**、指す**新規**、順にクリック**送信ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="9bc2e-106">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Platform Settings**, expand **Adapter**, right-click **FILEACT**, point to **New**, and then click **Send Handler**.</span></span>  
  
3.  <span data-ttu-id="9bc2e-107">**FILEACT – アダプター HandlerProperties**ダイアログ ボックスの**全般** タブから、**ホスト名**ドロップダウン リストで、 **fileacthost**、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="9bc2e-107">In the **FILEACT – Adapter HandlerProperties** dialog box, on the **General** tab, from the **Host name** drop-down list, select **fileacthost**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="9bc2e-108">**FILEACT トランスポートのプロパティ** ダイアログ ボックスで、**プロパティ** タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="9bc2e-108">In the **FILEACT Transport Properties** dialog box, on the **Properties** tab, do the following:</span></span>  
  
    |<span data-ttu-id="9bc2e-109">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="9bc2e-109">**Use this**</span></span>|<span data-ttu-id="9bc2e-110">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="9bc2e-110">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="9bc2e-111">**引数**</span><span class="sxs-lookup"><span data-stu-id="9bc2e-111">**Arguments**</span></span>|<span data-ttu-id="9bc2e-112">次の引数を入力: - SagMessagePartner \<SAG で Fileact クライアント メッセージのパートナーが作成される >**注:**引数で、クライアントは SAG で構成されている MessagePartner です。</span><span class="sxs-lookup"><span data-stu-id="9bc2e-112">Type the following argument: -SagMessagePartner \<Fileact Client Message Partner created in SAG> **Note:**  The client in the argument is the MessagePartner you configured in SAG.</span></span>|  
    |<span data-ttu-id="9bc2e-113">**暗号化モード**</span><span class="sxs-lookup"><span data-stu-id="9bc2e-113">**Crypto Mode**</span></span>|<span data-ttu-id="9bc2e-114">ドロップダウン リストから選択**詳細**です。</span><span class="sxs-lookup"><span data-stu-id="9bc2e-114">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="9bc2e-115">**FACryptoMode**</span><span class="sxs-lookup"><span data-stu-id="9bc2e-115">**FACryptoMode**</span></span>|<span data-ttu-id="9bc2e-116">ドロップダウン リストから選択**詳細**です。</span><span class="sxs-lookup"><span data-stu-id="9bc2e-116">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="9bc2e-117">**し**</span><span class="sxs-lookup"><span data-stu-id="9bc2e-117">**LogMessages**</span></span>|<span data-ttu-id="9bc2e-118">ドロップダウン リストから選択**TRUE**です。</span><span class="sxs-lookup"><span data-stu-id="9bc2e-118">From the drop-down list, select **TRUE**.</span></span> <span data-ttu-id="9bc2e-119">これにより、メッセージ イベントをキャプチャし、BAM ポータルで追跡できます。</span><span class="sxs-lookup"><span data-stu-id="9bc2e-119">This enables the message events to be captured and tracked in the BAM portal.</span></span>|  
    |<span data-ttu-id="9bc2e-120">**[有効化]**</span><span class="sxs-lookup"><span data-stu-id="9bc2e-120">**Enable**</span></span>|<span data-ttu-id="9bc2e-121">False</span><span class="sxs-lookup"><span data-stu-id="9bc2e-121">False</span></span>|  
    |<span data-ttu-id="9bc2e-122">**イベントのエンドポイント**</span><span class="sxs-lookup"><span data-stu-id="9bc2e-122">**Event end-point**</span></span>|<span data-ttu-id="9bc2e-123">適切な SAG エンドポイントを入力します。</span><span class="sxs-lookup"><span data-stu-id="9bc2e-123">Type the appropriate SAG end-point.</span></span>|  
    |<span data-ttu-id="9bc2e-124">**PhysicalFolderName**</span><span class="sxs-lookup"><span data-stu-id="9bc2e-124">**PhysicalFolderName**</span></span>|<span data-ttu-id="9bc2e-125">サーバー上のフォルダーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="9bc2e-125">Type the name of the folder on the server.</span></span> <span data-ttu-id="9bc2e-126">たとえば、C:\Fileact\ServerLocation です。</span><span class="sxs-lookup"><span data-stu-id="9bc2e-126">For example, C:\Fileact\ServerLocation.</span></span>|  
    |<span data-ttu-id="9bc2e-127">**PollingInterval**</span><span class="sxs-lookup"><span data-stu-id="9bc2e-127">**PollingInterval**</span></span>|<span data-ttu-id="9bc2e-128">適切な間隔 (秒) アダプターを確認するまでのファイル転送の状態を入力します。</span><span class="sxs-lookup"><span data-stu-id="9bc2e-128">Type the appropriate interval (in seconds) after which the adapter checks for the status of file transfer.</span></span>|  
    |<span data-ttu-id="9bc2e-129">**Password**</span><span class="sxs-lookup"><span data-stu-id="9bc2e-129">**Password**</span></span>|<span data-ttu-id="9bc2e-130">SAG への接続に使用するパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="9bc2e-130">Type the password you use to connect to SAG.</span></span> <span data-ttu-id="9bc2e-131">詳細については、SAG のヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9bc2e-131">See SAG Help for more information.</span></span>|  
    |<span data-ttu-id="9bc2e-132">**[ユーザー名]**</span><span class="sxs-lookup"><span data-stu-id="9bc2e-132">**User Name**</span></span>|<span data-ttu-id="9bc2e-133">SAG への接続に使用するユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="9bc2e-133">Type the user name you use to connect to SAG.</span></span>|  
  
5.  <span data-ttu-id="9bc2e-134">をクリックして**OK** FILEACT トランスポートのプロパティ ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="9bc2e-134">Click **OK** to close the FILEACT Transport Properties dialog box.</span></span>  
  
6.  <span data-ttu-id="9bc2e-135">をクリックして**OK** FILEACT-アダプター ハンドラーのプロパティ ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="9bc2e-135">Click **OK** to close the FILEACT – Adapter Handler Properties dialog box.</span></span>  
  
7.  <span data-ttu-id="9bc2e-136">メッセージ ボックスで、をクリックして**OK**、FileAct ホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="9bc2e-136">In the Message box, click **OK**, and then restart the FileAct host instance.</span></span>  
  
## <a name="complete-steps"></a><span data-ttu-id="9bc2e-137">詳細な手順</span><span class="sxs-lookup"><span data-stu-id="9bc2e-137">Complete steps</span></span>
 <span data-ttu-id="9bc2e-138">[FileAct ストア アンド フォワードのシナリオ](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="9bc2e-138">[FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="9bc2e-139">[手順 2: FileAct ストア アンド フォワードのシナリオの Paramfile に SWIFTNet 構成を追加します。](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="9bc2e-139">[Step 2: Add SWIFTNet Configuration to the Paramfile for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-store-and-forward.md) </span></span>  
 <span data-ttu-id="9bc2e-140">[手順 3: 送信ポートを作成し、FileAct ストア アンド フォワードのシナリオの受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="9bc2e-140">[Step 3: Create Send Ports and Receive Ports for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span></span>  
 [<span data-ttu-id="9bc2e-141">手順 4: FileAct ストア アンド フォワードのエンド ツー エンド シナリオをテストします。</span><span class="sxs-lookup"><span data-stu-id="9bc2e-141">Step 4: Test FileAct Store and Forward End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md)