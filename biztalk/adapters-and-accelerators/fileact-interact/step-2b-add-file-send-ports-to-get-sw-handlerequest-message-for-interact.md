---
title: 手順 2 b:InterAct ストア アンド フォワード (プル) シナリオ用に Sw:HandleRequest メッセージをキャプチャするファイルの送信ポートの追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa22d6e7-f1bd-43ad-9a0e-0b287057d20f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36ca62623cc6dd78f9c980fa35c3f0e744bc2666
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366113"
---
# <a name="step-2b-add-file-send-ports-to-capture-the-swhandlerequest-message-for-the-interact-store-and-forward-pull-scenario"></a><span data-ttu-id="5238b-102">手順 2 b:InterAct ストア アンド フォワード (プル) シナリオ用に Sw:HandleRequest メッセージをキャプチャするファイルの送信ポートの追加します。</span><span class="sxs-lookup"><span data-stu-id="5238b-102">Step 2B: Add FILE Send Ports to Capture the Sw:HandleRequest Message for the InterAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="5238b-103">この手順を開始する前に行う必要があります[Step 2 a:ファイル受信 InterAct ストア アンド フォワード (プル) シナリオ用の場所を追加](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md)します。</span><span class="sxs-lookup"><span data-stu-id="5238b-103">Before you begin this step, you must complete [Step 2A: Add FILE Receive Locations for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md).</span></span>  

### <a name="to-add-a-file-send-port-to-capture-the-swhandlerequest-message"></a><span data-ttu-id="5238b-104">ファイルを追加するには、送信の Sw:HandleRequest メッセージをキャプチャするポート</span><span class="sxs-lookup"><span data-stu-id="5238b-104">To add a FILE send port to capture the Sw:HandleRequest message</span></span>  

1. <span data-ttu-id="5238b-105">開始**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="5238b-105">Start **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="5238b-106">コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションを順に展開します。</span><span class="sxs-lookup"><span data-stu-id="5238b-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  

3. <span data-ttu-id="5238b-107">右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート。**</span><span class="sxs-lookup"><span data-stu-id="5238b-107">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port.**</span></span>  

4. <span data-ttu-id="5238b-108">**送信ポートのプロパティ**ウィンドウで、送信ポート名**Tutorial_IA_SendPullResponsetoReceiver**します。</span><span class="sxs-lookup"><span data-stu-id="5238b-108">In the **Send Port Properties** window, name the send port, **Tutorial_IA_SendPullResponsetoReceiver**.</span></span>  

5. <span data-ttu-id="5238b-109">**送信ポートのプロパティ**ウィンドウから、**トランスポートの種類**ドロップダウン リストで、**ファイル**、 をクリックし、**構成**。</span><span class="sxs-lookup"><span data-stu-id="5238b-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  

6. <span data-ttu-id="5238b-110">**FILE トランスポートのプロパティ** ダイアログ ボックスで、**先フォルダー**ボックスに「 **C:\SWIFTAdapterTutorial\Interact\PullResponse**、をクリックしてして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="5238b-110">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type **C:\SWIFTAdapterTutorial\Interact\PullResponse**, and then click **OK**.</span></span>  

7. <span data-ttu-id="5238b-111">**送信ポートのプロパティ**ウィンドウで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5238b-111">In the **Send Port Properties** window, do the following:</span></span>  


   |   <span data-ttu-id="5238b-112">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="5238b-112">**Use this**</span></span>    |                        <span data-ttu-id="5238b-113">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="5238b-113">**To do this**</span></span>                         |
   |-------------------|---------------------------------------------------------------|
   | <span data-ttu-id="5238b-114">**送信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="5238b-114">**Send handler**</span></span>  | <span data-ttu-id="5238b-115">ドロップダウン リストから選択**BizTalkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="5238b-115">From the drop-down list, select **BizTalkServerApplication**.</span></span> |
   | <span data-ttu-id="5238b-116">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="5238b-116">**Send pipeline**</span></span> |       <span data-ttu-id="5238b-117">ドロップダウン リストから選択**XMLTransmit**します。</span><span class="sxs-lookup"><span data-stu-id="5238b-117">From the drop-down list, select **XMLTransmit**.</span></span>        |


8. <span data-ttu-id="5238b-118">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5238b-118">Click **OK**.</span></span>  

9. <span data-ttu-id="5238b-119">手順 1. および 2. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="5238b-119">Repeat step 1 and 2.</span></span>  

10. <span data-ttu-id="5238b-120">右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**動的な送信請求-応答送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="5238b-120">Right-click **Send Ports**, point to **New**, and then click **Dynamic Solicit-Response Send Port**.</span></span>  

11. <span data-ttu-id="5238b-121">**送信ポートのプロパティ**ウィンドウで、送信ポート名<strong>、Tutorial_IA_DynamicSendPort</strong>します。</span><span class="sxs-lookup"><span data-stu-id="5238b-121">In the **Send Port Properties** window, name the send port<strong>, Tutorial_IA_DynamicSendPort</strong>.</span></span>  

12. <span data-ttu-id="5238b-122">**送信ポートのプロパティ**ウィンドウで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5238b-122">In the **Send Port Properties** window, do the following:</span></span>  


    |     <span data-ttu-id="5238b-123">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="5238b-123">**Use this**</span></span>     |                  <span data-ttu-id="5238b-124">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="5238b-124">**To do this**</span></span>                  |
    |----------------------|--------------------------------------------------|
    |  <span data-ttu-id="5238b-125">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="5238b-125">**Send pipeline**</span></span>   | <span data-ttu-id="5238b-126">ドロップダウン リストから選択**XMLTransmit**します。</span><span class="sxs-lookup"><span data-stu-id="5238b-126">From the drop-down list, select **XMLTransmit**.</span></span> |
    | <span data-ttu-id="5238b-127">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="5238b-127">**Receive pipeline**</span></span> | <span data-ttu-id="5238b-128">ドロップダウン リストから選択**XMLReceive**します。</span><span class="sxs-lookup"><span data-stu-id="5238b-128">From the drop-down list, select **XMLReceive**.</span></span>  |


13. <span data-ttu-id="5238b-129">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5238b-129">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="5238b-130">参照</span><span class="sxs-lookup"><span data-stu-id="5238b-130">See Also</span></span>  
 <span data-ttu-id="5238b-131">[手順 2 a:ファイル受信 InterAct ストア アンド フォワード (プル) シナリオ用の場所を追加します。](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="5238b-131">[Step 2A: Add FILE Receive Locations for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="5238b-132">手順 2 C:InterAct ストア アンド フォワード (プル) シナリオ用に INTERACT 送信ポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="5238b-132">Step 2C: Add an INTERACT Send Port for the InterAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-2c-add-interact-send-port-for-interact-store-and-forward-pull-scenario.md)