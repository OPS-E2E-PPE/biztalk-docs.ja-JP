---
title: 手順 1:FileAct リアルタイム シナリオ用に SWIFT アダプターを構成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: afc52c63-9f83-4e90-9269-e90834b792bf
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e2caca5af7d6bd1bf67a7a6cd890ba2fd3be833
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366557"
---
# <a name="step-1-configure-the-swift-adapter-for-the-fileact-real-time-scenario"></a><span data-ttu-id="9158f-102">手順 1:FileAct リアルタイム シナリオ用に SWIFT アダプターを構成します。</span><span class="sxs-lookup"><span data-stu-id="9158f-102">Step 1: Configure the SWIFT Adapter for the FileAct Real-Time Scenario</span></span>
<span data-ttu-id="9158f-103">この手順を開始する前に行う必要があります[チュートリアルを使用する準備](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md)します。</span><span class="sxs-lookup"><span data-stu-id="9158f-103">Before you begin this step, you must complete [Preparing to Use the Tutorial](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md).</span></span>  
  
### <a name="to-configure-the-swift-adapter"></a><span data-ttu-id="9158f-104">SWIFT アダプターを構成するには</span><span class="sxs-lookup"><span data-stu-id="9158f-104">To configure the SWIFT adapter</span></span>  
  
1.  <span data-ttu-id="9158f-105">開始**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="9158f-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="9158f-106">コンソール ツリーで、展開**BizTalk Server 管理**展開し、BizTalk グループを展開し、**プラットフォームの設定**、展開**アダプター**、右クリックして**FILEACT**、 をポイント**新規**、 をクリックし、**送信ハンドラー**します。</span><span class="sxs-lookup"><span data-stu-id="9158f-106">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Platform Settings**, expand **Adapter**, right-click **FILEACT**, point to **New**, and then click **Send Handler**.</span></span>  
  
3.  <span data-ttu-id="9158f-107">**FILEACT-アダプター ハンドラーのプロパティ** ダイアログ ボックスの 、**全般** タブから、**ホスト名**ドロップダウン リストで、 **fileacthost**、 をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="9158f-107">In the **FILEACT – Adapter Handler Properties** dialog box, on the **General** tab, from the **Host name** drop-down list, select **fileacthost**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="9158f-108">**FILEACT トランスポートのプロパティ** ダイアログ ボックスの 、**プロパティ** タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9158f-108">In the **FILEACT Transport Properties** dialog box, on the **Properties** tab, do the following:</span></span>  
  
    |<span data-ttu-id="9158f-109">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="9158f-109">**Use this**</span></span>|<span data-ttu-id="9158f-110">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="9158f-110">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="9158f-111">**引数**</span><span class="sxs-lookup"><span data-stu-id="9158f-111">**Arguments**</span></span>|<span data-ttu-id="9158f-112">次の引数を入力: - SagMessagePartner \<SAG で Fileact クライアント メッセージのパートナーが作成される\>**に注意してください。** 引数のクライアントは、SAG で構成した MessagePartner です。</span><span class="sxs-lookup"><span data-stu-id="9158f-112">Type the following argument: -SagMessagePartner \<Fileact Client Message Partner created in SAG\> **Note:**  The client in the argument is the MessagePartner you configured in SAG.</span></span>|  
    |<span data-ttu-id="9158f-113">**暗号モード**</span><span class="sxs-lookup"><span data-stu-id="9158f-113">**Crypto Mode**</span></span>|<span data-ttu-id="9158f-114">ドロップダウン リストから選択**詳細**します。</span><span class="sxs-lookup"><span data-stu-id="9158f-114">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="9158f-115">**FACryptoMode**</span><span class="sxs-lookup"><span data-stu-id="9158f-115">**FACryptoMode**</span></span>|<span data-ttu-id="9158f-116">ドロップダウン リストから選択**詳細**します。</span><span class="sxs-lookup"><span data-stu-id="9158f-116">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="9158f-117">**し**</span><span class="sxs-lookup"><span data-stu-id="9158f-117">**LogMessages**</span></span>|<span data-ttu-id="9158f-118">ドロップダウン リストから選択**TRUE**します。</span><span class="sxs-lookup"><span data-stu-id="9158f-118">From the drop-down list, select **TRUE**.</span></span> <span data-ttu-id="9158f-119">これにより、メッセージ イベントをキャプチャし、BAM ポータルで追跡できます。</span><span class="sxs-lookup"><span data-stu-id="9158f-119">This enables the message events to be captured and tracked in the BAM portal.</span></span>|  
    |<span data-ttu-id="9158f-120">**[有効化]**</span><span class="sxs-lookup"><span data-stu-id="9158f-120">**Enable**</span></span>|<span data-ttu-id="9158f-121">False</span><span class="sxs-lookup"><span data-stu-id="9158f-121">False</span></span>|  
    |<span data-ttu-id="9158f-122">**イベントのエンドポイント**</span><span class="sxs-lookup"><span data-stu-id="9158f-122">**Event end-point**</span></span>|<span data-ttu-id="9158f-123">適切な SAG エンドポイントを入力します。</span><span class="sxs-lookup"><span data-stu-id="9158f-123">Type the appropriate SAG end-point.</span></span>|  
    |<span data-ttu-id="9158f-124">**PhysicalFolderName**</span><span class="sxs-lookup"><span data-stu-id="9158f-124">**PhysicalFolderName**</span></span>|<span data-ttu-id="9158f-125">サーバー上のフォルダーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="9158f-125">Type the name of the folder on the server.</span></span> <span data-ttu-id="9158f-126">たとえば、C:\Fileact\ServerLocation です。</span><span class="sxs-lookup"><span data-stu-id="9158f-126">For example, C:\Fileact\ServerLocation.</span></span>|  
    |<span data-ttu-id="9158f-127">**PollingInterval**</span><span class="sxs-lookup"><span data-stu-id="9158f-127">**PollingInterval**</span></span>|<span data-ttu-id="9158f-128">適切な秒単位で確認間隔をアダプター ファイル転送の状態を入力します。</span><span class="sxs-lookup"><span data-stu-id="9158f-128">Type the appropriate interval (in seconds) after which the adapter checks for the status of file transfer.</span></span>|  
    |<span data-ttu-id="9158f-129">**Password**</span><span class="sxs-lookup"><span data-stu-id="9158f-129">**Password**</span></span>|<span data-ttu-id="9158f-130">SAG への接続に使用するパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="9158f-130">Type the password you use to connect to SAG.</span></span> <span data-ttu-id="9158f-131">詳細については、SAG ヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9158f-131">See SAG Help for more information.</span></span>|  
    |<span data-ttu-id="9158f-132">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="9158f-132">**Username**</span></span>|<span data-ttu-id="9158f-133">SAG への接続に使用するユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="9158f-133">Type the user name you use to connect to SAG.</span></span>|  
  
5.  <span data-ttu-id="9158f-134">クリックして**OK** FILEACT トランスポートのプロパティ ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="9158f-134">Click **OK** to close the FILEACT Transport Properties dialog box.</span></span>  
  
6.  <span data-ttu-id="9158f-135">クリックして**OK** FILEACT-アダプター ハンドラーのプロパティ ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="9158f-135">Click **OK** to close the FILEACT – Adapter Handler Properties dialog box.</span></span>  
  
7.  <span data-ttu-id="9158f-136">メッセージ ボックスで、次のようにクリックします。 **OK**、し FileAct のホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="9158f-136">In the message box, click **OK**, and then restart the FileAct host instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9158f-137">参照</span><span class="sxs-lookup"><span data-stu-id="9158f-137">See Also</span></span>  
 <span data-ttu-id="9158f-138">[FileAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="9158f-138">[FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="9158f-139">[手順 2:FileAct リアルタイム シナリオ用に Paramfile に SWIFTNet 構成を追加します。](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="9158f-139">[Step 2: Add SWIFTNet Configuration to the Paramfile for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="9158f-140">[ステップ 3:送信ポートを作成および FileAct リアルタイム シナリオ用の受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="9158f-140">[Step 3: Create the Send Ports and Receive Ports for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="9158f-141">手順 4:FileAct リアルタイム エンド ツー エンド シナリオをテストします。</span><span class="sxs-lookup"><span data-stu-id="9158f-141">Step 4: Test FileAct Real-Time End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md)