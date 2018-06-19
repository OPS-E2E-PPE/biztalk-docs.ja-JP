---
title: '手順 3 C: Sw:HandleFileRequest と Sw:HandleSnFRequest FileAct ストア アンド フォワードのシナリオについてメッセージをキャプチャする FILE 送信ポートの追加 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc41e352-acc5-47eb-bb87-38990f0e76a7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae6858164ee82f935c607246e7e93ffd86908f93
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225946"
---
# <a name="step-3c-add-a-file-send-port-to-capture-the-swhandlefilerequest-and-swhandlesnfrequest-messages-for-the-fileact-store-and-forward-scenario"></a><span data-ttu-id="734c3-102">手順 3 C: Sw:HandleFileRequest と Sw:HandleSnFRequest FileAct ストア アンド フォワードのシナリオについてメッセージをキャプチャする FILE 送信ポートの追加</span><span class="sxs-lookup"><span data-stu-id="734c3-102">Step 3C: Add a FILE Send Port to Capture the Sw:HandleFileRequest and Sw:HandleSnFRequest Messages for the FileAct Store and Forward Scenario</span></span>
<span data-ttu-id="734c3-103">この手順を開始する前に行う必要があります[手順 3 b: FileAct ストア アンド フォワードのシナリオの FILEACT 受信場所を追加](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-fileact-store-and-forward-scenario.md)です。</span><span class="sxs-lookup"><span data-stu-id="734c3-103">Before you begin this step, you must complete [Step 3B: Add a FILEACT Receive Location for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-fileact-store-and-forward-scenario.md).</span></span>  
  
### <a name="to-add-a-file-send-port-to-capture-swresponseserver-message"></a><span data-ttu-id="734c3-104">Sw:ResponseServer メッセージをキャプチャするポートを送信するファイルを追加するには</span><span class="sxs-lookup"><span data-stu-id="734c3-104">To add a FILE send port to capture Sw:ResponseServer message</span></span>  
  
1.  <span data-ttu-id="734c3-105">開始**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="734c3-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="734c3-106">コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="734c3-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="734c3-107">右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート。**</span><span class="sxs-lookup"><span data-stu-id="734c3-107">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port.**</span></span>  
  
4.  <span data-ttu-id="734c3-108">**送信ポートのプロパティ**ウィンドウで、名前、送信ポートを Tutorial_FA_SendResponseToReceiver です。</span><span class="sxs-lookup"><span data-stu-id="734c3-108">In the **Send Port Properties** window, name the send port, Tutorial_FA_SendResponseToReceiver.</span></span>  
  
5.  <span data-ttu-id="734c3-109">**送信ポートのプロパティ** ウィンドウから、**トランスポートの種類**ドロップダウン リストで、**ファイル**、順にクリック**構成**です。</span><span class="sxs-lookup"><span data-stu-id="734c3-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="734c3-110">**FILE トランスポートのプロパティ** ダイアログ ボックスで、**コピー先フォルダー**ボックスに、C:\SWIFTAdapterTutorial\Fileact\ResponseServer を入力し、をクリックして**ok**です。</span><span class="sxs-lookup"><span data-stu-id="734c3-110">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type C:\SWIFTAdapterTutorial\Fileact\ResponseServer, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="734c3-111">**送信ポートのプロパティ** ウィンドウで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="734c3-111">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="734c3-112">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="734c3-112">**Use this**</span></span>|<span data-ttu-id="734c3-113">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="734c3-113">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="734c3-114">**送信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="734c3-114">**Send handler**</span></span>|<span data-ttu-id="734c3-115">ドロップダウン リストから選択**BizTalkServerApplication**です。</span><span class="sxs-lookup"><span data-stu-id="734c3-115">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="734c3-116">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="734c3-116">**Send pipeline**</span></span>|<span data-ttu-id="734c3-117">ドロップダウン リストから選択**XMLTransmit**です。</span><span class="sxs-lookup"><span data-stu-id="734c3-117">From the drop-down list, select **XMLTransmit**.</span></span>|  
  
8.  <span data-ttu-id="734c3-118">**送信ポートのプロパティ** ウィンドウで、**フィルター**  タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="734c3-118">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="734c3-119">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="734c3-119">**Use this**</span></span>|<span data-ttu-id="734c3-120">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="734c3-120">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="734c3-121">**最初の行: プロパティ**</span><span class="sxs-lookup"><span data-stu-id="734c3-121">**First row: Property**</span></span>|<span data-ttu-id="734c3-122">ドロップダウン リストから選択**BTS です。MessageType**です。</span><span class="sxs-lookup"><span data-stu-id="734c3-122">From the drop-down list, select **BTS.MessageType**.</span></span>|  
    |<span data-ttu-id="734c3-123">**最初の行: 演算子**</span><span class="sxs-lookup"><span data-stu-id="734c3-123">**First row: Operator**</span></span>|<span data-ttu-id="734c3-124">ドロップダウン リストから選択 **==** です。</span><span class="sxs-lookup"><span data-stu-id="734c3-124">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="734c3-125">**最初の行: 値**</span><span class="sxs-lookup"><span data-stu-id="734c3-125">**First row: Value**</span></span>|<span data-ttu-id="734c3-126">型**ソフトウェア HandleFileRequest**です。</span><span class="sxs-lookup"><span data-stu-id="734c3-126">Type **Sw-HandleFileRequest**.</span></span>|  
    |<span data-ttu-id="734c3-127">**最初の行: グループ化**</span><span class="sxs-lookup"><span data-stu-id="734c3-127">**First row: Group by**</span></span>|<span data-ttu-id="734c3-128">ドロップダウン リストから選択**または**です。</span><span class="sxs-lookup"><span data-stu-id="734c3-128">From the drop-down list, select **OR**.</span></span>|  
    |<span data-ttu-id="734c3-129">**2 番目の行: プロパティ**</span><span class="sxs-lookup"><span data-stu-id="734c3-129">**Second row: Property**</span></span>|<span data-ttu-id="734c3-130">ドロップダウン リストから選択**BTS です。MessageType**です。</span><span class="sxs-lookup"><span data-stu-id="734c3-130">From the drop-down list, select **BTS.MessageType**.</span></span>|  
    |<span data-ttu-id="734c3-131">**2 番目の行: 演算子**</span><span class="sxs-lookup"><span data-stu-id="734c3-131">**Second row: Operator**</span></span>|<span data-ttu-id="734c3-132">ドロップダウン リストから選択 **==** です。</span><span class="sxs-lookup"><span data-stu-id="734c3-132">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="734c3-133">**2 番目の行: 値**</span><span class="sxs-lookup"><span data-stu-id="734c3-133">**Second row: Value**</span></span>|<span data-ttu-id="734c3-134">型**ソフトウェア HandleSnFRequest**です。</span><span class="sxs-lookup"><span data-stu-id="734c3-134">Type **Sw-HandleSnFRequest**.</span></span>|  
    |<span data-ttu-id="734c3-135">**2 番目の行: グループ化**</span><span class="sxs-lookup"><span data-stu-id="734c3-135">**Second row: Group by**</span></span>|<span data-ttu-id="734c3-136">既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="734c3-136">Leave the default value.</span></span>|  
  
9. <span data-ttu-id="734c3-137">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="734c3-137">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="734c3-138">参照</span><span class="sxs-lookup"><span data-stu-id="734c3-138">See Also</span></span>  
 <span data-ttu-id="734c3-139">[手順 3: 送信ポートを作成し、FileAct ストア アンド フォワードのシナリオの受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="734c3-139">[Step 3: Create Send Ports and Receive Ports for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span></span>  
 <span data-ttu-id="734c3-140">[手順 3: ファイルの受信場所が FileAct ストア アンド フォワードのシナリオを追加](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="734c3-140">[Step 3A: Add a FILE Receive Location for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="734c3-141">[手順 3 b: FILEACT の受信場所が FileAct ストア アンド フォワードのシナリオを追加](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="734c3-141">[Step 3B: Add a FILEACT Receive Location for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-fileact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="734c3-142">ステップ 3 D: FileAct ストア アンド フォワードのシナリオの FILEACT 送信ポートの追加</span><span class="sxs-lookup"><span data-stu-id="734c3-142">Step 3D: Add a FILEACT Send Port for the FileAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-store-and-forward-scenario.md)