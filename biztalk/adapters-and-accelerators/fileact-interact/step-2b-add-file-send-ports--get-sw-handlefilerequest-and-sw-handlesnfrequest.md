---
title: 手順 2 b:ファイル送信ポート、Sw:HandleFileRequest のキャプチャを追加および Sw:HandleSnFRequest メッセージを FileAct ストア アンド フォワード (プル) シナリオ |Microsoft Docs
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
ms.openlocfilehash: 8d832f94f205ab74ee3dbfac06828a750fb89847
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366146"
---
# <a name="step-2b-add-file-send-ports-to-capture-the-swhandlefilerequest-and-swhandlesnfrequest-messages-for-the-fileact-store-and-forward-pull-scenario"></a><span data-ttu-id="03156-102">手順 2 b:FileAct ストア アンド フォワード (プル) シナリオに Sw:HandleFileRequest および Sw:HandleSnFRequest メッセージをキャプチャするファイルの送信ポートの追加します。</span><span class="sxs-lookup"><span data-stu-id="03156-102">Step 2B: Add FILE Send Ports to Capture the Sw:HandleFileRequest and Sw:HandleSnFRequest Messages for the FileAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="03156-103">この手順を開始する前に行う必要があります、 [Step 2 a:FileAct ストア アンド フォワード (プル) シナリオ用の受信場所のファイルを追加](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md)セクション。</span><span class="sxs-lookup"><span data-stu-id="03156-103">Before you begin this step, you must complete the [Step 2A: Add FILE Receive Locations for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md) section.</span></span>  

### <a name="to-add-a-file-send-port-to-capture-the-sw-handlefilerequest-message"></a><span data-ttu-id="03156-104">ソフトウェアをキャプチャする FILE 送信ポートを追加します。HandleFileRequest メッセージ</span><span class="sxs-lookup"><span data-stu-id="03156-104">To add a FILE send port to capture the Sw: HandleFileRequest message</span></span>  

1. <span data-ttu-id="03156-105">開始**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="03156-105">Start **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="03156-106">コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションを順に展開します。</span><span class="sxs-lookup"><span data-stu-id="03156-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  

3. <span data-ttu-id="03156-107">右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート。**</span><span class="sxs-lookup"><span data-stu-id="03156-107">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port.**</span></span>  

4. <span data-ttu-id="03156-108">**送信ポートのプロパティ**ウィンドウで、送信ポート名**Tutorial_FA_SendPullResponsetoReceiver**します。</span><span class="sxs-lookup"><span data-stu-id="03156-108">In the **Send Port Properties** window, name the send port, **Tutorial_FA_SendPullResponsetoReceiver**.</span></span>  

5. <span data-ttu-id="03156-109">**送信ポートのプロパティ**ウィンドウから、**トランスポートの種類**ドロップダウン リストで、**ファイル**、 をクリックし、**構成**。</span><span class="sxs-lookup"><span data-stu-id="03156-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  

6. <span data-ttu-id="03156-110">**FILE トランスポートのプロパティ** ダイアログ ボックスで、**先フォルダー**ボックスに「 **C:\SWIFTAdapterTutorial\FileAct\PullResponse**、をクリックしてして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="03156-110">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type **C:\SWIFTAdapterTutorial\FileAct\PullResponse**, and then click **OK**.</span></span>  

7. <span data-ttu-id="03156-111">**送信ポートのプロパティ**ウィンドウで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="03156-111">In the **Send Port Properties** window, do the following:</span></span>  


   |   <span data-ttu-id="03156-112">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="03156-112">**Use this**</span></span>    |                        <span data-ttu-id="03156-113">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="03156-113">**To do this**</span></span>                         |
   |-------------------|---------------------------------------------------------------|
   | <span data-ttu-id="03156-114">**送信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="03156-114">**Send handler**</span></span>  | <span data-ttu-id="03156-115">ドロップダウン リストから選択**BizTalkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="03156-115">From the drop-down list, select **BizTalkServerApplication**.</span></span> |
   | <span data-ttu-id="03156-116">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="03156-116">**Send pipeline**</span></span> |       <span data-ttu-id="03156-117">ドロップダウン リストから選択**XMLTransmit**します。</span><span class="sxs-lookup"><span data-stu-id="03156-117">From the drop-down list, select **XMLTransmit**.</span></span>        |


8. <span data-ttu-id="03156-118">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03156-118">Click **OK**.</span></span>  

9. <span data-ttu-id="03156-119">手順 1. および 2. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="03156-119">Repeat step 1 and 2.</span></span>  

10. <span data-ttu-id="03156-120">右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**動的な送信請求-応答送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="03156-120">Right-click **Send Ports**, point to **New**, and then click **Dynamic Solicit-Response Send Port**.</span></span>  

11. <span data-ttu-id="03156-121">**送信ポートのプロパティ**ウィンドウで、送信ポート名<strong>、Tutorial_IA_DynamicSendPort</strong>します。</span><span class="sxs-lookup"><span data-stu-id="03156-121">In the **Send Port Properties** window, name the send port<strong>, Tutorial_IA_DynamicSendPort</strong>.</span></span>  

12. <span data-ttu-id="03156-122">**送信ポートのプロパティ**ウィンドウで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="03156-122">In the **Send Port Properties** window, do the following:</span></span>  


    |     <span data-ttu-id="03156-123">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="03156-123">**Use this**</span></span>     |                  <span data-ttu-id="03156-124">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="03156-124">**To do this**</span></span>                  |
    |----------------------|--------------------------------------------------|
    |  <span data-ttu-id="03156-125">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="03156-125">**Send pipeline**</span></span>   | <span data-ttu-id="03156-126">ドロップダウン リストから選択**XMLTransmit**します。</span><span class="sxs-lookup"><span data-stu-id="03156-126">From the drop-down list, select **XMLTransmit**.</span></span> |
    | <span data-ttu-id="03156-127">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="03156-127">**Receive pipeline**</span></span> | <span data-ttu-id="03156-128">ドロップダウン リストから選択**XMLReceive**します。</span><span class="sxs-lookup"><span data-stu-id="03156-128">From the drop-down list, select **XMLReceive**.</span></span>  |


13. <span data-ttu-id="03156-129">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03156-129">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="03156-130">参照</span><span class="sxs-lookup"><span data-stu-id="03156-130">See Also</span></span>  
 <span data-ttu-id="03156-131">[手順 2 a:ファイルの受信場所 FileAct ストア アンド フォワード (プル) シナリオの追加します。](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="03156-131">[Step 2A: Add FILE Receive Locations for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="03156-132">手順 2 C:FileAct ストア アンド フォワード (プル) シナリオに FILEACT 送信ポートの追加します。</span><span class="sxs-lookup"><span data-stu-id="03156-132">Step 2C: Add a FILEACT Send Port for the FileAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-2c-add-a-fileact-send-port-for-fileact-store-and-forward-pull-scenario.md)