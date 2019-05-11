---
title: 手順 1:用に SWIFT アダプターを構成、InterAct リアルタイム シナリオ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f4d3e08-611a-4af1-a3e3-957ace3b74e6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08da44a01765bd1a3b1b936d77eb7cfdccae2c4d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366508"
---
# <a name="step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario"></a><span data-ttu-id="2d2a5-102">手順 1:用に SWIFT アダプターを構成、InterAct リアルタイム シナリオ</span><span class="sxs-lookup"><span data-stu-id="2d2a5-102">Step 1: Configure the SWIFT Adapter for the InterAct Real-Time Scenario</span></span>
<span data-ttu-id="2d2a5-103">次の手順では、Interact アダプターの送信ハンドラーを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2d2a5-103">The following steps explain how to configure the send handler for the Interact adapter.</span></span> <span data-ttu-id="2d2a5-104">一覧された要件を完了する必要があります、プロシージャを開始する前に[チュートリアルを使用する準備](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md)します。</span><span class="sxs-lookup"><span data-stu-id="2d2a5-104">Before you begin the procedure, you must complete the requirements listed in [Preparing to Use the Tutorial](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md).</span></span>  
  
### <a name="to-configure-the-swift-adapter"></a><span data-ttu-id="2d2a5-105">SWIFT アダプターを構成するには</span><span class="sxs-lookup"><span data-stu-id="2d2a5-105">To configure the SWIFT adapter</span></span>  
  
1.  <span data-ttu-id="2d2a5-106">開始**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="2d2a5-106">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="2d2a5-107">コンソール ツリーで、展開**BizTalk Server 管理**展開し、BizTalk グループを展開し、**プラットフォームの設定**、展開**アダプター**、右クリックして**INTERACT**、 をポイント**新規**、 をクリックし、**送信ハンドラー**します。</span><span class="sxs-lookup"><span data-stu-id="2d2a5-107">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Platform Settings**, expand **Adapter**, right-click **INTERACT**, point to **New**, and then click **Send Handler**.</span></span>  
  
3.  <span data-ttu-id="2d2a5-108">**アダプター ハンドラーのプロパティ-対話** ダイアログ ボックスで、**全般** タブから、**ホスト名**ドロップダウン リストで、 **interacthost**、 をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="2d2a5-108">In the **INTERACT – Adapter Handler Properties** dialog box, on the **General** tab, from the **Host name** drop-down list, select **interacthost**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="2d2a5-109">**INTERACTTransport プロパティ** ダイアログ ボックスの 、**プロパティ** タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2d2a5-109">In the **INTERACTTransport Properties** dialog box, on the **Properties** tab, do the following:</span></span>  
  
    |<span data-ttu-id="2d2a5-110">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="2d2a5-110">**Use this**</span></span>|<span data-ttu-id="2d2a5-111">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="2d2a5-111">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="2d2a5-112">**引数**</span><span class="sxs-lookup"><span data-stu-id="2d2a5-112">**Arguments**</span></span>|<span data-ttu-id="2d2a5-113">次の引数を入力します。**SagMessagePartner**\<SAG で対話するクライアントのメッセージのパートナーが作成された\>**に注意してください。** 引数のクライアントは、SAG で構成した MessagePartner です。</span><span class="sxs-lookup"><span data-stu-id="2d2a5-113">Type the following argument: **SagMessagePartner**\<Interact Client Message Partner created in SAG\> **Note:**  The client in the argument is the MessagePartner you configured in SAG.</span></span>|  
    |<span data-ttu-id="2d2a5-114">**暗号モード**</span><span class="sxs-lookup"><span data-stu-id="2d2a5-114">**Crypto Mode**</span></span>|<span data-ttu-id="2d2a5-115">ドロップダウン リストから選択**詳細**します。</span><span class="sxs-lookup"><span data-stu-id="2d2a5-115">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="2d2a5-116">**LogMessageBody**</span><span class="sxs-lookup"><span data-stu-id="2d2a5-116">**LogMessageBody**</span></span>|<span data-ttu-id="2d2a5-117">ドロップダウン リストから選択`FALSE`します。</span><span class="sxs-lookup"><span data-stu-id="2d2a5-117">From the drop-down list, select `FALSE`.</span></span> <span data-ttu-id="2d2a5-118">**注:** 設定した場合`TRUE`、追跡データベースにメッセージ本文が維持されます。</span><span class="sxs-lookup"><span data-stu-id="2d2a5-118">**Note:**  If you set to `TRUE`, it preserves the message body in the tracking database.</span></span> <span data-ttu-id="2d2a5-119">ただし、セキュリティ上の理由から、メッセージ本文は、BAM ポータルでは表示ことはありませんすることができます。</span><span class="sxs-lookup"><span data-stu-id="2d2a5-119">However, for security reasons, the message body can never be viewed in the BAM portal.</span></span>|  
    |<span data-ttu-id="2d2a5-120">**し**</span><span class="sxs-lookup"><span data-stu-id="2d2a5-120">**LogMessages**</span></span>|<span data-ttu-id="2d2a5-121">ドロップダウン リストから選択`TRUE`します。</span><span class="sxs-lookup"><span data-stu-id="2d2a5-121">From the drop-down list, select `TRUE`.</span></span> <span data-ttu-id="2d2a5-122">これにより、メッセージ イベントをキャプチャし、BAM ポータルで追跡できます。</span><span class="sxs-lookup"><span data-stu-id="2d2a5-122">This enables the message events to be captured and tracked in the BAM portal.</span></span>|  
    |<span data-ttu-id="2d2a5-123">**[有効化]**</span><span class="sxs-lookup"><span data-stu-id="2d2a5-123">**Enable**</span></span>|<span data-ttu-id="2d2a5-124">False</span><span class="sxs-lookup"><span data-stu-id="2d2a5-124">False</span></span>|  
    |<span data-ttu-id="2d2a5-125">**Password**</span><span class="sxs-lookup"><span data-stu-id="2d2a5-125">**Password**</span></span>|<span data-ttu-id="2d2a5-126">SAG への接続に使用するパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="2d2a5-126">Type the password you use to connect to SAG.</span></span> <span data-ttu-id="2d2a5-127">詳細については、SAG ヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d2a5-127">See SAG Help for more information.</span></span>|  
    |<span data-ttu-id="2d2a5-128">**[ユーザー名]**</span><span class="sxs-lookup"><span data-stu-id="2d2a5-128">**User Name**</span></span>|<span data-ttu-id="2d2a5-129">SAG への接続に使用するユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="2d2a5-129">Type the user name you use to connect to SAG.</span></span>|  
  
5.  <span data-ttu-id="2d2a5-130">クリックして**OK**対話トランスポートのプロパティのダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="2d2a5-130">Click **OK** to close the INTERACT Transport Properties dialog box.</span></span>  
  
6.  <span data-ttu-id="2d2a5-131">クリックして**OK** INTERACT-アダプター ハンドラーのプロパティ ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="2d2a5-131">Click **OK** to close the INTERACT – Adapter Handler Properties dialog box.</span></span>  
  
7.  <span data-ttu-id="2d2a5-132">メッセージ ボックスで、次のようにクリックします。 **OK**、し、対話のホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="2d2a5-132">In the message box, click **OK**, and then restart the Interact host instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d2a5-133">参照</span><span class="sxs-lookup"><span data-stu-id="2d2a5-133">See Also</span></span>  
 <span data-ttu-id="2d2a5-134">[InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="2d2a5-134">[InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="2d2a5-135">[ステップ 1: 用に SWIFT アダプターを構成、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="2d2a5-135">[Step 1: Configure the SWIFT Adapter for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="2d2a5-136">[手順 2:用に Paramfile に SWIFTNet 構成を追加、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="2d2a5-136">[Step 2: Add SWIFTNet Configuration to the Paramfile for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="2d2a5-137">[ステップ 3:作成する送信と受信ポートを InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="2d2a5-137">[Step 3: Create Send and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="2d2a5-138">手順 4:テスト、InterAct リアルタイム エンド ツー エンドのシナリオ</span><span class="sxs-lookup"><span data-stu-id="2d2a5-138">Step 4: Test the InterAct Real-Time End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md)