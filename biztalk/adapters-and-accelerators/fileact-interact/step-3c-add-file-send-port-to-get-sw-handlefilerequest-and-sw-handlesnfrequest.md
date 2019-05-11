---
title: 手順 3 C:FileAct ストア アンド フォワード シナリオ用 Sw:HandleFileRequest および Sw:HandleSnFRequest メッセージをキャプチャする FILE 送信ポートの追加 |Microsoft Docs
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
ms.openlocfilehash: ca89ba30184664aada5f312dc021f858234bc39c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365585"
---
# <a name="step-3c-add-a-file-send-port-to-capture-the-swhandlefilerequest-and-swhandlesnfrequest-messages-for-the-fileact-store-and-forward-scenario"></a><span data-ttu-id="0e788-102">手順 3 C:FileAct ストア アンド フォワード シナリオ用 Sw:HandleFileRequest および Sw:HandleSnFRequest メッセージをキャプチャする FILE 送信ポートの追加します。</span><span class="sxs-lookup"><span data-stu-id="0e788-102">Step 3C: Add a FILE Send Port to Capture the Sw:HandleFileRequest and Sw:HandleSnFRequest Messages for the FileAct Store and Forward Scenario</span></span>
<span data-ttu-id="0e788-103">この手順を開始する前に行う必要があります[手順 3 b:FileAct ストア アンド フォワード シナリオ用の場所に、FILEACT の受信を追加](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-fileact-store-and-forward-scenario.md)します。</span><span class="sxs-lookup"><span data-stu-id="0e788-103">Before you begin this step, you must complete [Step 3B: Add a FILEACT Receive Location for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-fileact-store-and-forward-scenario.md).</span></span>  
  
### <a name="to-add-a-file-send-port-to-capture-swresponseserver-message"></a><span data-ttu-id="0e788-104">ファイルを追加するには、送信の Sw:ResponseServer メッセージをキャプチャするポート</span><span class="sxs-lookup"><span data-stu-id="0e788-104">To add a FILE send port to capture Sw:ResponseServer message</span></span>  
  
1.  <span data-ttu-id="0e788-105">開始**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="0e788-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="0e788-106">コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションを順に展開します。</span><span class="sxs-lookup"><span data-stu-id="0e788-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="0e788-107">右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート。**</span><span class="sxs-lookup"><span data-stu-id="0e788-107">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port.**</span></span>  
  
4.  <span data-ttu-id="0e788-108">**送信ポートのプロパティ**ウィンドウで、名前、送信ポート Tutorial_FA_SendResponseToReceiver します。</span><span class="sxs-lookup"><span data-stu-id="0e788-108">In the **Send Port Properties** window, name the send port, Tutorial_FA_SendResponseToReceiver.</span></span>  
  
5.  <span data-ttu-id="0e788-109">**送信ポートのプロパティ**ウィンドウから、**トランスポートの種類**ドロップダウン リストで、**ファイル**、 をクリックし、**構成**。</span><span class="sxs-lookup"><span data-stu-id="0e788-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="0e788-110">**FILE トランスポートのプロパティ** ダイアログ ボックスで、**先フォルダー**ボックスに、C:\SWIFTAdapterTutorial\Fileact\ResponseServer を入力し、 をクリックし、 **ok**します。</span><span class="sxs-lookup"><span data-stu-id="0e788-110">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type C:\SWIFTAdapterTutorial\Fileact\ResponseServer, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="0e788-111">**送信ポートのプロパティ**ウィンドウで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0e788-111">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="0e788-112">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="0e788-112">**Use this**</span></span>|<span data-ttu-id="0e788-113">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="0e788-113">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="0e788-114">**送信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="0e788-114">**Send handler**</span></span>|<span data-ttu-id="0e788-115">ドロップダウン リストから選択**BizTalkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="0e788-115">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="0e788-116">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="0e788-116">**Send pipeline**</span></span>|<span data-ttu-id="0e788-117">ドロップダウン リストから選択**XMLTransmit**します。</span><span class="sxs-lookup"><span data-stu-id="0e788-117">From the drop-down list, select **XMLTransmit**.</span></span>|  
  
8.  <span data-ttu-id="0e788-118">**送信ポートのプロパティ**ウィンドウで、**フィルター**  タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0e788-118">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="0e788-119">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="0e788-119">**Use this**</span></span>|<span data-ttu-id="0e788-120">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="0e788-120">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="0e788-121">**最初の行。プロパティ**</span><span class="sxs-lookup"><span data-stu-id="0e788-121">**First row: Property**</span></span>|<span data-ttu-id="0e788-122">ドロップダウン リストから選択**BTS します。MessageType**します。</span><span class="sxs-lookup"><span data-stu-id="0e788-122">From the drop-down list, select **BTS.MessageType**.</span></span>|  
    |<span data-ttu-id="0e788-123">**最初の行。!**</span><span class="sxs-lookup"><span data-stu-id="0e788-123">**First row: Operator**</span></span>|<span data-ttu-id="0e788-124">ドロップダウン リストから選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="0e788-124">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="0e788-125">**最初の行。値**</span><span class="sxs-lookup"><span data-stu-id="0e788-125">**First row: Value**</span></span>|<span data-ttu-id="0e788-126">型**Sw HandleFileRequest**します。</span><span class="sxs-lookup"><span data-stu-id="0e788-126">Type **Sw-HandleFileRequest**.</span></span>|  
    |<span data-ttu-id="0e788-127">**最初の行。グループ化**</span><span class="sxs-lookup"><span data-stu-id="0e788-127">**First row: Group by**</span></span>|<span data-ttu-id="0e788-128">ドロップダウン リストから選択**または**します。</span><span class="sxs-lookup"><span data-stu-id="0e788-128">From the drop-down list, select **OR**.</span></span>|  
    |<span data-ttu-id="0e788-129">**2 番目の行。プロパティ**</span><span class="sxs-lookup"><span data-stu-id="0e788-129">**Second row: Property**</span></span>|<span data-ttu-id="0e788-130">ドロップダウン リストから選択**BTS します。MessageType**します。</span><span class="sxs-lookup"><span data-stu-id="0e788-130">From the drop-down list, select **BTS.MessageType**.</span></span>|  
    |<span data-ttu-id="0e788-131">**2 番目の行。!**</span><span class="sxs-lookup"><span data-stu-id="0e788-131">**Second row: Operator**</span></span>|<span data-ttu-id="0e788-132">ドロップダウン リストから選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="0e788-132">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="0e788-133">**2 番目の行。値**</span><span class="sxs-lookup"><span data-stu-id="0e788-133">**Second row: Value**</span></span>|<span data-ttu-id="0e788-134">型**Sw HandleSnFRequest**します。</span><span class="sxs-lookup"><span data-stu-id="0e788-134">Type **Sw-HandleSnFRequest**.</span></span>|  
    |<span data-ttu-id="0e788-135">**2 番目の行。グループ化**</span><span class="sxs-lookup"><span data-stu-id="0e788-135">**Second row: Group by**</span></span>|<span data-ttu-id="0e788-136">既定値のままにします。</span><span class="sxs-lookup"><span data-stu-id="0e788-136">Leave the default value.</span></span>|  
  
9. <span data-ttu-id="0e788-137">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e788-137">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e788-138">参照</span><span class="sxs-lookup"><span data-stu-id="0e788-138">See Also</span></span>  
 <span data-ttu-id="0e788-139">[ステップ 3:送信ポートを作成し、受信 FileAct ストア アンド フォワード シナリオ用のポート](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="0e788-139">[Step 3: Create Send Ports and Receive Ports for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span></span>  
 <span data-ttu-id="0e788-140">[手順 3 a:FileAct ストア アンド フォワード シナリオ用の場所の受信ファイルを追加します。](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="0e788-140">[Step 3A: Add a FILE Receive Location for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="0e788-141">[手順 3 b:FileAct ストア アンド フォワード シナリオ用の場所に、FILEACT の受信を追加します。](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="0e788-141">[Step 3B: Add a FILEACT Receive Location for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-fileact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="0e788-142">手順 3 D:FileAct ストア アンド フォワード シナリオ用 FILEACT 送信ポートの追加します。</span><span class="sxs-lookup"><span data-stu-id="0e788-142">Step 3D: Add a FILEACT Send Port for the FileAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-store-and-forward-scenario.md)