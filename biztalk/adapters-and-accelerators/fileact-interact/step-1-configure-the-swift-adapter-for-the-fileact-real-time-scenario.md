---
title: "手順 1: FileAct リアルタイム シナリオでは、SWIFT のアダプターを構成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: afc52c63-9f83-4e90-9269-e90834b792bf
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 991d3d37bab70e07eb21b21a040e3479fc2658df
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-1-configure-the-swift-adapter-for-the-fileact-real-time-scenario"></a><span data-ttu-id="1bb21-102">手順 1: FileAct リアルタイム シナリオでは、SWIFT のアダプターを構成します。</span><span class="sxs-lookup"><span data-stu-id="1bb21-102">Step 1: Configure the SWIFT Adapter for the FileAct Real-Time Scenario</span></span>
<span data-ttu-id="1bb21-103">この手順を開始する前に行う必要があります[、チュートリアルを使用する準備](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md)です。</span><span class="sxs-lookup"><span data-stu-id="1bb21-103">Before you begin this step, you must complete [Preparing to Use the Tutorial](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md).</span></span>  
  
### <a name="to-configure-the-swift-adapter"></a><span data-ttu-id="1bb21-104">SWIFT のアダプターを構成するには</span><span class="sxs-lookup"><span data-stu-id="1bb21-104">To configure the SWIFT adapter</span></span>  
  
1.  <span data-ttu-id="1bb21-105">開始**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="1bb21-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="1bb21-106">コンソール ツリーで  **BizTalk Server 管理コンソール**、BizTalk グループを展開し、**プラットフォームの設定**、展開**アダプター**を右クリックして**FILEACT**、指す**新規**、順にクリック**送信ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="1bb21-106">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Platform Settings**, expand **Adapter**, right-click **FILEACT**, point to **New**, and then click **Send Handler**.</span></span>  
  
3.  <span data-ttu-id="1bb21-107">**FILEACT-アダプター ハンドラーのプロパティ**ダイアログ ボックスの**全般** タブから、**ホスト名**ドロップダウン リストで、 **fileacthost**、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="1bb21-107">In the **FILEACT – Adapter Handler Properties** dialog box, on the **General** tab, from the **Host name** drop-down list, select **fileacthost**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="1bb21-108">**FILEACT トランスポートのプロパティ** ダイアログ ボックスで、**プロパティ** タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="1bb21-108">In the **FILEACT Transport Properties** dialog box, on the **Properties** tab, do the following:</span></span>  
  
    |<span data-ttu-id="1bb21-109">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="1bb21-109">**Use this**</span></span>|<span data-ttu-id="1bb21-110">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="1bb21-110">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="1bb21-111">**引数**</span><span class="sxs-lookup"><span data-stu-id="1bb21-111">**Arguments**</span></span>|<span data-ttu-id="1bb21-112">次の引数を入力: - SagMessagePartner \<SAG で Fileact クライアント メッセージのパートナーが作成される\>**注:**引数で、クライアントは SAG で構成されている MessagePartner です。</span><span class="sxs-lookup"><span data-stu-id="1bb21-112">Type the following argument: -SagMessagePartner \<Fileact Client Message Partner created in SAG\> **Note:**  The client in the argument is the MessagePartner you configured in SAG.</span></span>|  
    |<span data-ttu-id="1bb21-113">**暗号化モード**</span><span class="sxs-lookup"><span data-stu-id="1bb21-113">**Crypto Mode**</span></span>|<span data-ttu-id="1bb21-114">ドロップダウン リストから選択**詳細**です。</span><span class="sxs-lookup"><span data-stu-id="1bb21-114">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="1bb21-115">**FACryptoMode**</span><span class="sxs-lookup"><span data-stu-id="1bb21-115">**FACryptoMode**</span></span>|<span data-ttu-id="1bb21-116">ドロップダウン リストから選択**詳細**です。</span><span class="sxs-lookup"><span data-stu-id="1bb21-116">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="1bb21-117">**し**</span><span class="sxs-lookup"><span data-stu-id="1bb21-117">**LogMessages**</span></span>|<span data-ttu-id="1bb21-118">ドロップダウン リストから選択**TRUE**です。</span><span class="sxs-lookup"><span data-stu-id="1bb21-118">From the drop-down list, select **TRUE**.</span></span> <span data-ttu-id="1bb21-119">これにより、メッセージ イベントをキャプチャし、BAM ポータルで追跡できます。</span><span class="sxs-lookup"><span data-stu-id="1bb21-119">This enables the message events to be captured and tracked in the BAM portal.</span></span>|  
    |<span data-ttu-id="1bb21-120">**[有効化]**</span><span class="sxs-lookup"><span data-stu-id="1bb21-120">**Enable**</span></span>|<span data-ttu-id="1bb21-121">False</span><span class="sxs-lookup"><span data-stu-id="1bb21-121">False</span></span>|  
    |<span data-ttu-id="1bb21-122">**イベントのエンドポイント**</span><span class="sxs-lookup"><span data-stu-id="1bb21-122">**Event end-point**</span></span>|<span data-ttu-id="1bb21-123">適切な SAG エンドポイントを入力します。</span><span class="sxs-lookup"><span data-stu-id="1bb21-123">Type the appropriate SAG end-point.</span></span>|  
    |<span data-ttu-id="1bb21-124">**PhysicalFolderName**</span><span class="sxs-lookup"><span data-stu-id="1bb21-124">**PhysicalFolderName**</span></span>|<span data-ttu-id="1bb21-125">サーバー上のフォルダーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="1bb21-125">Type the name of the folder on the server.</span></span> <span data-ttu-id="1bb21-126">たとえば、C:\Fileact\ServerLocation です。</span><span class="sxs-lookup"><span data-stu-id="1bb21-126">For example, C:\Fileact\ServerLocation.</span></span>|  
    |<span data-ttu-id="1bb21-127">**PollingInterval**</span><span class="sxs-lookup"><span data-stu-id="1bb21-127">**PollingInterval**</span></span>|<span data-ttu-id="1bb21-128">適切な間隔 (秒) アダプターを確認するまでのファイル転送の状態を入力します。</span><span class="sxs-lookup"><span data-stu-id="1bb21-128">Type the appropriate interval (in seconds) after which the adapter checks for the status of file transfer.</span></span>|  
    |<span data-ttu-id="1bb21-129">**Password**</span><span class="sxs-lookup"><span data-stu-id="1bb21-129">**Password**</span></span>|<span data-ttu-id="1bb21-130">SAG への接続に使用するパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="1bb21-130">Type the password you use to connect to SAG.</span></span> <span data-ttu-id="1bb21-131">詳細については、SAG のヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bb21-131">See SAG Help for more information.</span></span>|  
    |<span data-ttu-id="1bb21-132">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="1bb21-132">**Username**</span></span>|<span data-ttu-id="1bb21-133">SAG への接続に使用するユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="1bb21-133">Type the user name you use to connect to SAG.</span></span>|  
  
5.  <span data-ttu-id="1bb21-134">をクリックして**OK** FILEACT トランスポートのプロパティ ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="1bb21-134">Click **OK** to close the FILEACT Transport Properties dialog box.</span></span>  
  
6.  <span data-ttu-id="1bb21-135">をクリックして**OK** FILEACT-アダプター ハンドラーのプロパティ ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="1bb21-135">Click **OK** to close the FILEACT – Adapter Handler Properties dialog box.</span></span>  
  
7.  <span data-ttu-id="1bb21-136">メッセージ ボックスで、をクリックして**OK**、FileAct ホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="1bb21-136">In the message box, click **OK**, and then restart the FileAct host instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bb21-137">参照</span><span class="sxs-lookup"><span data-stu-id="1bb21-137">See Also</span></span>  
 <span data-ttu-id="1bb21-138">[FileAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="1bb21-138">[FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="1bb21-139">[手順 2: SWIFTNet の構成を追加、Paramfile FileAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="1bb21-139">[Step 2: Add SWIFTNet Configuration to the Paramfile for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="1bb21-140">[手順 3: 送信ポートを作成し、FileAct リアルタイムのシナリオの受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="1bb21-140">[Step 3: Create the Send Ports and Receive Ports for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="1bb21-141">手順 4: FileAct リアルタイム エンド ツー エンド シナリオをテストする</span><span class="sxs-lookup"><span data-stu-id="1bb21-141">Step 4: Test FileAct Real-Time End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md)