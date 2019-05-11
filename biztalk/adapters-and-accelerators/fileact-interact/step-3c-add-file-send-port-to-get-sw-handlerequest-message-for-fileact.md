---
title: 手順 3 C:FileAct リアルタイム シナリオ用に Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートの追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc0a9173-20df-4c73-80ee-755987d639d2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5bfada4652e021db8e61e2b37e50e291dcab00f3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365510"
---
# <a name="step-3c-add-a-file-send-port-to-capture-swhandlerequest-message-for-the-fileact-real-time-scenario"></a><span data-ttu-id="0305c-102">手順 3 C:FileAct リアルタイム シナリオ用に Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートの追加します。</span><span class="sxs-lookup"><span data-stu-id="0305c-102">Step 3C: Add a FILE Send Port to Capture Sw:HandleRequest Message for the FileAct Real-Time Scenario</span></span>
<span data-ttu-id="0305c-103">この手順を開始する前に行う必要があります[手順 3 b:FileAct リアルタイム シナリオ用の場所に、FILEACT の受信を追加](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md)します。</span><span class="sxs-lookup"><span data-stu-id="0305c-103">Before you begin this step, you must complete [Step 3B: Add a FILEACT Receive Location for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md).</span></span>  
  
### <a name="to-add-a-file-send-port-to-capture-swhandlefilerequest-message"></a><span data-ttu-id="0305c-104">ファイルを追加するには、送信の Sw:HandleFileRequest メッセージをキャプチャするポート</span><span class="sxs-lookup"><span data-stu-id="0305c-104">To add a FILE send port to capture Sw:HandleFileRequest message</span></span>  
  
1.  <span data-ttu-id="0305c-105">開始**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="0305c-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="0305c-106">コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションを順に展開します。</span><span class="sxs-lookup"><span data-stu-id="0305c-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="0305c-107">右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート。**</span><span class="sxs-lookup"><span data-stu-id="0305c-107">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port.**</span></span>  
  
4.  <span data-ttu-id="0305c-108">**送信ポートのプロパティ**ウィンドウで、名前、送信ポート Tutorial_FA_SendResponseToReceiver します。</span><span class="sxs-lookup"><span data-stu-id="0305c-108">In the **Send Port Properties** window, name the send port, Tutorial_FA_SendResponseToReceiver.</span></span>  
  
5.  <span data-ttu-id="0305c-109">**送信ポートのプロパティ**ウィンドウから、**トランスポートの種類**ドロップダウン リストで、**ファイル**、 をクリックし、**構成**。</span><span class="sxs-lookup"><span data-stu-id="0305c-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="0305c-110">**FILE トランスポートのプロパティ** ダイアログ ボックスで、**先フォルダー**ボックスに、C:\SWIFTAdapterTutorial\Fileact\ResponseServer を入力し、 をクリックし、 **ok**します。</span><span class="sxs-lookup"><span data-stu-id="0305c-110">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type C:\SWIFTAdapterTutorial\Fileact\ResponseServer, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="0305c-111">**送信ポートのプロパティ**ウィンドウで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0305c-111">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="0305c-112">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="0305c-112">**Use this**</span></span>|<span data-ttu-id="0305c-113">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="0305c-113">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="0305c-114">**送信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="0305c-114">**Send handler**</span></span>|<span data-ttu-id="0305c-115">ドロップダウン リストから選択**BizTalkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="0305c-115">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="0305c-116">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="0305c-116">**Send pipeline**</span></span>|<span data-ttu-id="0305c-117">ドロップダウン リストから選択**XMLTransmit**します。</span><span class="sxs-lookup"><span data-stu-id="0305c-117">From the drop-down list, select **XMLTransmit**.</span></span>|  
  
8.  <span data-ttu-id="0305c-118">**送信ポートのプロパティ**ウィンドウで、**フィルター**  タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0305c-118">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="0305c-119">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="0305c-119">**Use this**</span></span>|<span data-ttu-id="0305c-120">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="0305c-120">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="0305c-121">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="0305c-121">**Property**</span></span>|<span data-ttu-id="0305c-122">ドロップダウン リストから選択**BTS します。MessageType**します。</span><span class="sxs-lookup"><span data-stu-id="0305c-122">From the drop-down list, select **BTS.MessageType**.</span></span>|  
    |<span data-ttu-id="0305c-123">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="0305c-123">**Operator**</span></span>|<span data-ttu-id="0305c-124">ドロップダウン リストから選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="0305c-124">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="0305c-125">**[値]**</span><span class="sxs-lookup"><span data-stu-id="0305c-125">**Value**</span></span>|<span data-ttu-id="0305c-126">型**Sw HandleFileRequest**します。</span><span class="sxs-lookup"><span data-stu-id="0305c-126">Type **Sw-HandleFileRequest**.</span></span>|  
    |<span data-ttu-id="0305c-127">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="0305c-127">**Group by**</span></span>|<span data-ttu-id="0305c-128">既定値のままにします</span><span class="sxs-lookup"><span data-stu-id="0305c-128">Leave the default value</span></span>|  
  
9. <span data-ttu-id="0305c-129">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0305c-129">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0305c-130">参照</span><span class="sxs-lookup"><span data-stu-id="0305c-130">See Also</span></span>  
 <span data-ttu-id="0305c-131">[ステップ 3:送信ポートを作成および FileAct リアルタイム シナリオ用の受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="0305c-131">[Step 3: Create the Send Ports and Receive Ports for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="0305c-132">[手順 3 a:ファイル受信 FileAct リアルタイム シナリオ用の場所を追加します。](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="0305c-132">[Step 3A: Add a FILE Receive Location for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="0305c-133">[手順 3 b:FileAct リアルタイム シナリオ用の場所に、FILEACT の受信を追加します。](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="0305c-133">[Step 3B: Add a FILEACT Receive Location for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="0305c-134">[手順 3 D:FileAct リアルタイム シナリオ用に FILEACT 送信ポートを追加します。](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="0305c-134">[Step 3D: Add a FILEACT Send Port for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="0305c-135">手順 3 e:FileAct リアルタイム シナリオ用に Sw:ExchangeFileResponse メッセージをキャプチャする FILE 送信ポートの追加します。</span><span class="sxs-lookup"><span data-stu-id="0305c-135">Step 3E: Add a FILE Send Port to Capture Sw:ExchangeFileResponse Message for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)