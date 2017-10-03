---
title: "手順 3 C: FileAct リアルタイム シナリオ Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートの追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc0a9173-20df-4c73-80ee-755987d639d2
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3705f0b649e7f8d1c85898677ddc0301851dd302
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3c-add-a-file-send-port-to-capture-swhandlerequest-message-for-the-fileact-real-time-scenario"></a><span data-ttu-id="39978-102">手順 3 C: FileAct リアルタイム シナリオ Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートの追加</span><span class="sxs-lookup"><span data-stu-id="39978-102">Step 3C: Add a FILE Send Port to Capture Sw:HandleRequest Message for the FileAct Real-Time Scenario</span></span>
<span data-ttu-id="39978-103">この手順を開始する前に行う必要があります[手順 3 b: FileAct リアルタイム シナリオ FILEACT 受信場所を追加](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md)です。</span><span class="sxs-lookup"><span data-stu-id="39978-103">Before you begin this step, you must complete [Step 3B: Add a FILEACT Receive Location for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md).</span></span>  
  
### <a name="to-add-a-file-send-port-to-capture-swhandlefilerequest-message"></a><span data-ttu-id="39978-104">Sw:HandleFileRequest メッセージをキャプチャするポートを送信するファイルを追加するには</span><span class="sxs-lookup"><span data-stu-id="39978-104">To add a FILE send port to capture Sw:HandleFileRequest message</span></span>  
  
1.  <span data-ttu-id="39978-105">開始**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="39978-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="39978-106">コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="39978-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="39978-107">右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート。**</span><span class="sxs-lookup"><span data-stu-id="39978-107">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port.**</span></span>  
  
4.  <span data-ttu-id="39978-108">**送信ポートのプロパティ**ウィンドウで、名前、送信ポートを Tutorial_FA_SendResponseToReceiver です。</span><span class="sxs-lookup"><span data-stu-id="39978-108">In the **Send Port Properties** window, name the send port, Tutorial_FA_SendResponseToReceiver.</span></span>  
  
5.  <span data-ttu-id="39978-109">**送信ポートのプロパティ** ウィンドウから、**トランスポートの種類**ドロップダウン リストで、**ファイル**、順にクリック**構成**です。</span><span class="sxs-lookup"><span data-stu-id="39978-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="39978-110">**FILE トランスポートのプロパティ** ダイアログ ボックスで、**コピー先フォルダー**ボックスに、C:\SWIFTAdapterTutorial\Fileact\ResponseServer を入力し、をクリックして**ok**です。</span><span class="sxs-lookup"><span data-stu-id="39978-110">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type C:\SWIFTAdapterTutorial\Fileact\ResponseServer, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="39978-111">**送信ポートのプロパティ** ウィンドウで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="39978-111">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="39978-112">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="39978-112">**Use this**</span></span>|<span data-ttu-id="39978-113">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="39978-113">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="39978-114">**送信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="39978-114">**Send handler**</span></span>|<span data-ttu-id="39978-115">ドロップダウン リストから選択**BizTalkServerApplication**です。</span><span class="sxs-lookup"><span data-stu-id="39978-115">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="39978-116">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="39978-116">**Send pipeline**</span></span>|<span data-ttu-id="39978-117">ドロップダウン リストから選択**XMLTransmit**です。</span><span class="sxs-lookup"><span data-stu-id="39978-117">From the drop-down list, select **XMLTransmit**.</span></span>|  
  
8.  <span data-ttu-id="39978-118">**送信ポートのプロパティ** ウィンドウで、**フィルター**  タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="39978-118">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="39978-119">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="39978-119">**Use this**</span></span>|<span data-ttu-id="39978-120">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="39978-120">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="39978-121">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="39978-121">**Property**</span></span>|<span data-ttu-id="39978-122">ドロップダウン リストから選択**BTS です。MessageType**です。</span><span class="sxs-lookup"><span data-stu-id="39978-122">From the drop-down list, select **BTS.MessageType**.</span></span>|  
    |<span data-ttu-id="39978-123">**演算子**</span><span class="sxs-lookup"><span data-stu-id="39978-123">**Operator**</span></span>|<span data-ttu-id="39978-124">ドロップダウン リストから選択 **==**です。</span><span class="sxs-lookup"><span data-stu-id="39978-124">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="39978-125">**値**</span><span class="sxs-lookup"><span data-stu-id="39978-125">**Value**</span></span>|<span data-ttu-id="39978-126">型**ソフトウェア HandleFileRequest**です。</span><span class="sxs-lookup"><span data-stu-id="39978-126">Type **Sw-HandleFileRequest**.</span></span>|  
    |<span data-ttu-id="39978-127">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="39978-127">**Group by**</span></span>|<span data-ttu-id="39978-128">既定値をそのまま</span><span class="sxs-lookup"><span data-stu-id="39978-128">Leave the default value</span></span>|  
  
9. <span data-ttu-id="39978-129">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39978-129">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39978-130">参照</span><span class="sxs-lookup"><span data-stu-id="39978-130">See Also</span></span>  
 <span data-ttu-id="39978-131">[手順 3: 送信ポートを作成し、FileAct リアルタイムのシナリオの受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="39978-131">[Step 3: Create the Send Ports and Receive Ports for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="39978-132">[手順 3: ファイルの受信場所、FileAct リアルタイムのシナリオの追加](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="39978-132">[Step 3A: Add a FILE Receive Location for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="39978-133">[手順 3 b: FILEACT の受信場所が FileAct リアルタイム シナリオの追加](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="39978-133">[Step 3B: Add a FILEACT Receive Location for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="39978-134">[ステップ 3 D: FileAct リアルタイム シナリオ FILEACT 送信ポートの追加](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="39978-134">[Step 3D: Add a FILEACT Send Port for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="39978-135">ステップ 3 e: FileAct リアルタイム シナリオ Sw:ExchangeFileResponse メッセージをキャプチャする FILE 送信ポートの追加</span><span class="sxs-lookup"><span data-stu-id="39978-135">Step 3E: Add a FILE Send Port to Capture Sw:ExchangeFileResponse Message for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)