---
title: 手順 4 b:送信ポートの開始し、InterAct ストア アンド フォワード シナリオ用の受信ポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7b0ecd4-ea08-4567-80bd-14f465ba4867
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1c3efec973c57ad056d738a9048c276d677644b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364850"
---
# <a name="step-4b-start-the-send-ports-and-receive-ports-for-the-interact-store-and-forward-scenario"></a><span data-ttu-id="53b04-102">手順 4 b:送信ポートの開始し、InterAct ストア アンド フォワード シナリオ用の受信ポート</span><span class="sxs-lookup"><span data-stu-id="53b04-102">Step 4B: Start the Send Ports and Receive Ports for the InterAct Store and Forward Scenario</span></span>
<span data-ttu-id="53b04-103">この手順を開始する前に行う必要があります[手順 4 a:InterAct ストア アンド フォワード シナリオ用に SWIFTNet サービスを開始](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-interact-store-and-forward-scenario.md)します。</span><span class="sxs-lookup"><span data-stu-id="53b04-103">Before you begin this step, you must complete [Step 4A: Start the SWIFTNet Service for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-interact-store-and-forward-scenario.md).</span></span>  
  
### <a name="to-start-the-send-ports-and-receive-ports"></a><span data-ttu-id="53b04-104">ポート、送信ポートと受信開始するには</span><span class="sxs-lookup"><span data-stu-id="53b04-104">To start the send ports and receive ports</span></span>  
  
1.  <span data-ttu-id="53b04-105">開始**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="53b04-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="53b04-106">コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成した BizTalk アプリケーションを順に展開します。</span><span class="sxs-lookup"><span data-stu-id="53b04-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application where you created the send ports.</span></span>  
  
3.  <span data-ttu-id="53b04-107">次の各送信ポート、送信ポートを右クリックし、クリックして**開始**:</span><span class="sxs-lookup"><span data-stu-id="53b04-107">For each of the following send ports, right-click the send port, and then click **Start**:</span></span>  
  
    -   <span data-ttu-id="53b04-108">**Tutorial_IA_SendResponseToReceiver**</span><span class="sxs-lookup"><span data-stu-id="53b04-108">**Tutorial_IA_SendResponseToReceiver**</span></span>  
  
    -   <span data-ttu-id="53b04-109">**Tutorial_IA_SendResponseToSender**</span><span class="sxs-lookup"><span data-stu-id="53b04-109">**Tutorial_IA_SendResponseToSender**</span></span>  
  
    -   <span data-ttu-id="53b04-110">**Tutorial_IA_SendRequest_SnF**</span><span class="sxs-lookup"><span data-stu-id="53b04-110">**Tutorial_IA_SendRequest_SnF**</span></span>  
  
4.  <span data-ttu-id="53b04-111">コンソール ツリーで、BizTalk グループを展開し、受信場所を作成した BizTalk アプリケーションを順に展開します。</span><span class="sxs-lookup"><span data-stu-id="53b04-111">In the console tree, expand the BizTalk group, and then expand the BizTalk application where you created the receive locations.</span></span>  
  
5.  <span data-ttu-id="53b04-112">次の受信場所ごとに、受信場所を右クリックし、順にクリックします**を有効にする**:</span><span class="sxs-lookup"><span data-stu-id="53b04-112">For each of the following receive locations, right-click the receive location, and then click **Enable**:</span></span>  
  
    -   <span data-ttu-id="53b04-113">**Tutorial_IA_InputRequest_SnF**</span><span class="sxs-lookup"><span data-stu-id="53b04-113">**Tutorial_IA_InputRequest_SnF**</span></span>  
  
    -   <span data-ttu-id="53b04-114">**Tutorial_IA_HandleRequestOneWay_SnF**</span><span class="sxs-lookup"><span data-stu-id="53b04-114">**Tutorial_IA_HandleRequestOneWay_SnF**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53b04-115">参照</span><span class="sxs-lookup"><span data-stu-id="53b04-115">See Also</span></span>  
 <span data-ttu-id="53b04-116">[手順 4:InterAct ストア アンド フォワード エンド ツー エンド シナリオをテストします。](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="53b04-116">[Step 4: Test the InterAct Store and Forward End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="53b04-117">[手順 4 a:InterAct ストア アンド フォワード シナリオ用に SWIFTNet サービスを開始します。](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="53b04-117">[Step 4A: Start the SWIFTNet Service for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="53b04-118">[手順 4 C:InterAct ストア アンド フォワード シナリオ用のテスト インスタンスを作成します。](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="53b04-118">[Step 4C: Create a Test Instance for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="53b04-119">手順 4 D:InterAct ストア アンド フォワード シナリオ用の有効なインスタンスをテストします。</span><span class="sxs-lookup"><span data-stu-id="53b04-119">Step 4D: Test a Valid Instance for the InterAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-interact-store-and-forward-scenario.md)