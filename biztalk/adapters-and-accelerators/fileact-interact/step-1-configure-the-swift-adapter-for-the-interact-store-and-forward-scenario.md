---
title: 手順 1:InterAct ストア アンド フォワード シナリオ用に SWIFT アダプターを構成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 03b81599-bd26-44dc-9cf3-73868248764c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e10c320f82d66d4bc78059d0e9bf078efae5e638
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366446"
---
# <a name="step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-scenario"></a><span data-ttu-id="7257a-102">手順 1:InterAct ストア アンド フォワード シナリオ用に SWIFT アダプターを構成します。</span><span class="sxs-lookup"><span data-stu-id="7257a-102">Step 1: Configure the SWIFT Adapter for the InterAct Store and Forward Scenario</span></span>
<span data-ttu-id="7257a-103">この手順を開始する前に行う必要があります[チュートリアルを使用する準備](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md)します。</span><span class="sxs-lookup"><span data-stu-id="7257a-103">Before you begin this step, you must complete [Preparing to Use the Tutorial](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md).</span></span>  
  
### <a name="to-configure-the-swift-adapter"></a><span data-ttu-id="7257a-104">SWIFT アダプターを構成するには</span><span class="sxs-lookup"><span data-stu-id="7257a-104">To configure the SWIFT adapter</span></span>  
  
1.  <span data-ttu-id="7257a-105">開始**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="7257a-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="7257a-106">コンソール ツリーで、BizTalk Server 管理コンソールを展開し、BizTalk グループを展開し、**プラットフォームの設定**、展開**アダプター**、右クリックして**INTERACT**、 をポイント**新規**、 をクリックし、**送信ハンドラー**します。</span><span class="sxs-lookup"><span data-stu-id="7257a-106">In the console tree, expand BizTalk Server Administration, expand the BizTalk group, expand **Platform Settings**, expand **Adapter**, right-click **INTERACT**, point to **New**, and then click **Send Handler**.</span></span>  
  
3.  <span data-ttu-id="7257a-107">**アダプター ハンドラーのプロパティ-対話** ダイアログ ボックスで、**全般** タブから、**ホスト名**ドロップダウン リストで、 **interacthost**、 をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="7257a-107">In the **INTERACT – Adapter Handler Properties** dialog box, on the **General** tab, from the **Host name** drop-down list, select **interacthost**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="7257a-108">**トランスポートのプロパティの対話** ダイアログ ボックスで、**プロパティ** タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7257a-108">In the **INTERACT Transport Properties** dialog box, on the **Properties** tab, do the following:</span></span>  
  
    |<span data-ttu-id="7257a-109">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="7257a-109">**Use this**</span></span>|<span data-ttu-id="7257a-110">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="7257a-110">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="7257a-111">**引数**</span><span class="sxs-lookup"><span data-stu-id="7257a-111">**Arguments**</span></span>|<span data-ttu-id="7257a-112">次の引数を入力: – SagMessagePartner \<SAG で対話するクライアントのメッセージのパートナーが作成された\>**に注意してください。** 引数のクライアントは、SAG で構成した MessagePartner です。</span><span class="sxs-lookup"><span data-stu-id="7257a-112">Type the following argument: –SagMessagePartner \<Interact Client Message Partner created in SAG\> **Note:**  The client in the argument is the MessagePartner you configured in SAG.</span></span>|  
    |<span data-ttu-id="7257a-113">**暗号モード**</span><span class="sxs-lookup"><span data-stu-id="7257a-113">**Crypto Mode**</span></span>|<span data-ttu-id="7257a-114">ドロップダウン リストから選択**詳細**します。</span><span class="sxs-lookup"><span data-stu-id="7257a-114">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="7257a-115">**LogMessageBody**</span><span class="sxs-lookup"><span data-stu-id="7257a-115">**LogMessageBody**</span></span>|<span data-ttu-id="7257a-116">ドロップダウン リストから選択**FALSE**します。</span><span class="sxs-lookup"><span data-stu-id="7257a-116">From the drop-down list, select **FALSE**.</span></span> <span data-ttu-id="7257a-117">**注:** TRUE に設定した場合は、BizTalk 追跡データベースでメッセージの本文を保持します。</span><span class="sxs-lookup"><span data-stu-id="7257a-117">**Note:**  If you set to TRUE, it preserves the message body in the BizTalk Tracking database.</span></span> <span data-ttu-id="7257a-118">ただし、セキュリティ上の理由から、メッセージ本文は、BAM ポータルでは表示ことはありませんすることができます。</span><span class="sxs-lookup"><span data-stu-id="7257a-118">However, for security reasons, the message body can never be viewed in the BAM portal.</span></span>|  
    |<span data-ttu-id="7257a-119">**し**</span><span class="sxs-lookup"><span data-stu-id="7257a-119">**LogMessages**</span></span>|<span data-ttu-id="7257a-120">ドロップダウン リストから選択**TRUE**します。</span><span class="sxs-lookup"><span data-stu-id="7257a-120">From the drop-down list, select **TRUE**.</span></span> <span data-ttu-id="7257a-121">これにより、メッセージ イベントをキャプチャし、BAM ポータルで追跡できます。</span><span class="sxs-lookup"><span data-stu-id="7257a-121">This enables the message events to be captured and tracked in the BAM portal.</span></span>|  
    |<span data-ttu-id="7257a-122">**[有効化]**</span><span class="sxs-lookup"><span data-stu-id="7257a-122">**Enable**</span></span>|<span data-ttu-id="7257a-123">False です。</span><span class="sxs-lookup"><span data-stu-id="7257a-123">False.</span></span>|  
    |<span data-ttu-id="7257a-124">**Password**</span><span class="sxs-lookup"><span data-stu-id="7257a-124">**Password**</span></span>|<span data-ttu-id="7257a-125">SAG への接続に使用するパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="7257a-125">Type the password you use to connect to SAG.</span></span> <span data-ttu-id="7257a-126">詳細については、SAG ヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7257a-126">See SAG Help for more information.</span></span>|  
    |<span data-ttu-id="7257a-127">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="7257a-127">**Username**</span></span>|<span data-ttu-id="7257a-128">SAG への接続に使用するユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="7257a-128">Type the user name you use to connect to SAG.</span></span>|  
  
5.  <span data-ttu-id="7257a-129">クリックして**OK**対話トランスポートのプロパティのダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7257a-129">Click **OK** to close the INTERACT Transport Properties dialog box.</span></span>  
  
6.  <span data-ttu-id="7257a-130">クリックして**OK** INTERACT-アダプター ハンドラーのプロパティ ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7257a-130">Click **OK** to close the INTERACT – Adapter Handler Properties dialog box.</span></span>  
  
7.  <span data-ttu-id="7257a-131">メッセージ ボックスで、次のようにクリックします。 **OK**、し、対話のホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="7257a-131">In the message box, click **OK**, and then restart the InterAct host instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7257a-132">参照</span><span class="sxs-lookup"><span data-stu-id="7257a-132">See Also</span></span>  
 <span data-ttu-id="7257a-133">[InterAct ストア アンド フォワード (プッシュ) シナリオ](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="7257a-133">[InterAct Store and Forward (Push) Scenario](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md) </span></span>  
 <span data-ttu-id="7257a-134">[手順 2:InterAct ストア アンド フォワード シナリオ用に Paramfile に SWIFTNet 構成を追加します。](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="7257a-134">[Step 2: Add SWIFTNet Configuration to the Paramfile for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-store-and-forward.md) </span></span>  
 <span data-ttu-id="7257a-135">[ステップ 3:送信ポートの作成し、InterAct ストア アンド フォワード シナリオ用の受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="7257a-135">[Step 3: Create Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="7257a-136">手順 4:InterAct ストア アンド フォワード エンド ツー エンド シナリオをテストします。</span><span class="sxs-lookup"><span data-stu-id="7257a-136">Step 4: Test the InterAct Store and Forward End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md)