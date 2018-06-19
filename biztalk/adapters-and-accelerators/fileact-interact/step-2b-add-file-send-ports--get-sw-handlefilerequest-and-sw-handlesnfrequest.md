---
title: '手順 2 b: Sw:HandleFileRequest をキャプチャするファイルの送信ポートを追加し、FileAct ストア アンド フォワードの Sw:HandleSnFRequest メッセージ (プル) シナリオ |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 21d055e9-ff7c-4af1-983b-d03e8d4a94f6
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c2eb55cd6aca9b26b8a8ac47ab6dbe192f174d8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224362"
---
# <a name="step-2b-add-file-send-ports-to-capture-the-swhandlefilerequest-and-swhandlesnfrequest-messages-for-the-fileact-store-and-forward-pull-scenario"></a><span data-ttu-id="b7fa5-102">手順 2 b: Sw:HandleFileRequest をキャプチャするファイルの送信ポートを追加し、FileAct ストア アンド フォワードの Sw:HandleSnFRequest メッセージ (プル) のシナリオ</span><span class="sxs-lookup"><span data-stu-id="b7fa5-102">Step 2B: Add FILE Send Ports to Capture the Sw:HandleFileRequest and Sw:HandleSnFRequest Messages for the FileAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="b7fa5-103">この手順を開始する前に行う必要があります、 [Step 2 a: FileAct ストア アンド フォワード (プル) シナリオ用のファイル受信場所の追加](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md)セクションです。</span><span class="sxs-lookup"><span data-stu-id="b7fa5-103">Before you begin this step, you must complete the [Step 2A: Add FILE Receive Locations for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md) section.</span></span>  
  
### <a name="to-add-a-file-send-port-to-capture-the-sw-handlefilerequest-message"></a><span data-ttu-id="b7fa5-104">ファイル送信ポート、ソフトウェアのキャプチャを追加する: HandleFileRequest メッセージ</span><span class="sxs-lookup"><span data-stu-id="b7fa5-104">To add a FILE send port to capture the Sw: HandleFileRequest message</span></span>  
  
1.  <span data-ttu-id="b7fa5-105">開始**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="b7fa5-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="b7fa5-106">コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="b7fa5-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="b7fa5-107">右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート。**</span><span class="sxs-lookup"><span data-stu-id="b7fa5-107">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port.**</span></span>  
  
4.  <span data-ttu-id="b7fa5-108">**送信ポートのプロパティ**ウィンドウで、名前、送信ポートを**Tutorial_FA_SendPullResponsetoReceiver**です。</span><span class="sxs-lookup"><span data-stu-id="b7fa5-108">In the **Send Port Properties** window, name the send port, **Tutorial_FA_SendPullResponsetoReceiver**.</span></span>  
  
5.  <span data-ttu-id="b7fa5-109">**送信ポートのプロパティ** ウィンドウから、**トランスポートの種類**ドロップダウン リストで、**ファイル**、順にクリック**構成**です。</span><span class="sxs-lookup"><span data-stu-id="b7fa5-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="b7fa5-110">**FILE トランスポートのプロパティ** ダイアログ ボックスで、**コピー先フォルダー**ボックスに、入力**C:\SWIFTAdapterTutorial\FileAct\PullResponse**をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="b7fa5-110">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type **C:\SWIFTAdapterTutorial\FileAct\PullResponse**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="b7fa5-111">**送信ポートのプロパティ** ウィンドウで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="b7fa5-111">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="b7fa5-112">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="b7fa5-112">**Use this**</span></span>|<span data-ttu-id="b7fa5-113">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="b7fa5-113">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="b7fa5-114">**送信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="b7fa5-114">**Send handler**</span></span>|<span data-ttu-id="b7fa5-115">ドロップダウン リストから選択**BizTalkServerApplication**です。</span><span class="sxs-lookup"><span data-stu-id="b7fa5-115">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="b7fa5-116">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="b7fa5-116">**Send pipeline**</span></span>|<span data-ttu-id="b7fa5-117">ドロップダウン リストから選択**XMLTransmit**です。</span><span class="sxs-lookup"><span data-stu-id="b7fa5-117">From the drop-down list, select **XMLTransmit**.</span></span>|  
  
8.  <span data-ttu-id="b7fa5-118">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7fa5-118">Click **OK**.</span></span>  
  
9. <span data-ttu-id="b7fa5-119">手順 1. および 2. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="b7fa5-119">Repeat step 1 and 2.</span></span>  
  
10. <span data-ttu-id="b7fa5-120">右クリック**送信ポート**、 をポイント**新規**、クリックして**動的な送信請求-応答送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="b7fa5-120">Right-click **Send Ports**, point to **New**, and then click **Dynamic Solicit-Response Send Port**.</span></span>  
  
11. <span data-ttu-id="b7fa5-121">**送信ポートのプロパティ**ウィンドウで、送信ポートの名前 **、Tutorial_IA_DynamicSendPort**です。</span><span class="sxs-lookup"><span data-stu-id="b7fa5-121">In the **Send Port Properties** window, name the send port **, Tutorial_IA_DynamicSendPort**.</span></span>  
  
12. <span data-ttu-id="b7fa5-122">**送信ポートのプロパティ** ウィンドウで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="b7fa5-122">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="b7fa5-123">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="b7fa5-123">**Use this**</span></span>|<span data-ttu-id="b7fa5-124">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="b7fa5-124">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="b7fa5-125">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="b7fa5-125">**Send pipeline**</span></span>|<span data-ttu-id="b7fa5-126">ドロップダウン リストから選択**XMLTransmit**です。</span><span class="sxs-lookup"><span data-stu-id="b7fa5-126">From the drop-down list, select **XMLTransmit**.</span></span>|  
    |<span data-ttu-id="b7fa5-127">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="b7fa5-127">**Receive pipeline**</span></span>|<span data-ttu-id="b7fa5-128">ドロップダウン リストから選択**XMLReceive**です。</span><span class="sxs-lookup"><span data-stu-id="b7fa5-128">From the drop-down list, select **XMLReceive**.</span></span>|  
  
13. <span data-ttu-id="b7fa5-129">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7fa5-129">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7fa5-130">参照</span><span class="sxs-lookup"><span data-stu-id="b7fa5-130">See Also</span></span>  
 <span data-ttu-id="b7fa5-131">[手順 2 a: ファイルの受信場所 FileAct ストア アンド フォワード (プル) シナリオの追加](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="b7fa5-131">[Step 2A: Add FILE Receive Locations for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="b7fa5-132">手順 2 C: FileAct ストア アンド フォワード (プル) シナリオの FILEACT 送信ポートの追加</span><span class="sxs-lookup"><span data-stu-id="b7fa5-132">Step 2C: Add a FILEACT Send Port for the FileAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-2c-add-a-fileact-send-port-for-fileact-store-and-forward-pull-scenario.md)