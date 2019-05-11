---
title: 手順 4 b:送信ポートの開始し、InterAct ストア アンド フォワード (プル) シナリオ用の受信ポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00ab119d-ed44-4f4a-84ea-20f2c41e5a92
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48b8f9ec4d2403d72de24d737aeae55305f5068b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364940"
---
# <a name="step-4b-start-the-send-ports-and-receive-ports-for-the-interact-store-and-forward-pull-scenario"></a><span data-ttu-id="946b6-102">手順 4 b:送信ポートの開始し、InterAct ストア アンド フォワード (プル) シナリオ用の受信ポート</span><span class="sxs-lookup"><span data-stu-id="946b6-102">Step 4B: Start the Send Ports and Receive Ports for the InterAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="946b6-103">この手順を開始する前に行う必要があります[手順 4。InterAct ストア アンド フォワード エンド ツー エンドのシナリオ テスト](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md)します。</span><span class="sxs-lookup"><span data-stu-id="946b6-103">Before you begin this step, you must complete[Step 4: Test the InterAct Store and Forward End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md).</span></span>  
  
### <a name="to-start-the-send-ports-and-receive-ports"></a><span data-ttu-id="946b6-104">ポート、送信ポートと受信開始するには</span><span class="sxs-lookup"><span data-stu-id="946b6-104">To start the send ports and receive ports</span></span>  
  
1.  <span data-ttu-id="946b6-105">開始**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="946b6-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="946b6-106">コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成した BizTalk アプリケーションを順に展開します。</span><span class="sxs-lookup"><span data-stu-id="946b6-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application where you created the send ports.</span></span>  
  
3.  <span data-ttu-id="946b6-107">次の各送信ポート、送信ポートを右クリックし、クリックして**開始**:</span><span class="sxs-lookup"><span data-stu-id="946b6-107">For each of the following send ports, right-click the send port, and then click **Start**:</span></span>  
  
    -   <span data-ttu-id="946b6-108">**Tutorial_ IA_SendPullResponseToReceiver**</span><span class="sxs-lookup"><span data-stu-id="946b6-108">**Tutorial_ IA_SendPullResponseToReceiver**</span></span>  
  
    -   <span data-ttu-id="946b6-109">**Tutorial_IA_SendRequest_SnF**</span><span class="sxs-lookup"><span data-stu-id="946b6-109">**Tutorial_IA_SendRequest_SnF**</span></span>  
  
    -   <span data-ttu-id="946b6-110">**Tutorial_IA_DynamicSendPort**</span><span class="sxs-lookup"><span data-stu-id="946b6-110">**Tutorial_IA_DynamicSendPort**</span></span>  
  
4.  <span data-ttu-id="946b6-111">コンソール ツリーで、BizTalk グループを展開し、受信場所を作成した BizTalk アプリケーションを順に展開します。</span><span class="sxs-lookup"><span data-stu-id="946b6-111">In the console tree, expand the BizTalk group, and then expand the BizTalk application where you created the receive locations.</span></span>  
  
5.  <span data-ttu-id="946b6-112">次の受信場所ごとに、受信場所を右クリックし、順にクリックします**を有効にする**:</span><span class="sxs-lookup"><span data-stu-id="946b6-112">For each of the following receive locations, right-click the receive location, and then click **Enable**:</span></span>  
  
    -   <span data-ttu-id="946b6-113">**Tutorial_IA_InputRequest_SnF**</span><span class="sxs-lookup"><span data-stu-id="946b6-113">**Tutorial_IA_InputRequest_SnF**</span></span>  
  
    -   <span data-ttu-id="946b6-114">**Tutorial_ IA_InputRequest_PullMode**</span><span class="sxs-lookup"><span data-stu-id="946b6-114">**Tutorial_ IA_InputRequest_PullMode**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="946b6-115">参照</span><span class="sxs-lookup"><span data-stu-id="946b6-115">See Also</span></span>  
 <span data-ttu-id="946b6-116">[手順 4 a:InterAct ストア アンド フォワード (プル) シナリオ用に SWIFTNet サービスを開始します。](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="946b6-116">[Step 4A: Start the SWIFTNet Service for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="946b6-117">[手順 4 C:InterAct ストア アンド フォワード (プル) シナリオのテスト インスタンスを作成します。](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-interact-store-and-forward-pull-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="946b6-117">[Step 4C: Create a Test Instance for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-interact-store-and-forward-pull-scenario.md) </span></span>  
 [<span data-ttu-id="946b6-118">手順 4 D:InterAct ストア アンド フォワード (プル) シナリオ用の有効なインスタンスをテストします。</span><span class="sxs-lookup"><span data-stu-id="946b6-118">Step 4D: Test a Valid Instance for the InterAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-interact-store-and-forward-pull-scenario.md)