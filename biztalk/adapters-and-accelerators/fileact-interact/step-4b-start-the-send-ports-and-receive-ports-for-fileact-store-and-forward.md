---
title: 手順 4 b:送信ポートの開始し、受信 FileAct ストア アンド フォワード シナリオ用のポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f8c34b1-24a5-4ac7-bb96-27834bc3c711
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6b1cea7699cfb45ebf736e0547e1f0cca9fcf63
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364891"
---
# <a name="step-4b-start-the-send-ports-and-receive-ports-for-the-fileact-store-and-forward-scenario"></a><span data-ttu-id="29ec1-102">手順 4 b:送信ポートの開始し、受信 FileAct ストア アンド フォワード シナリオ用のポート</span><span class="sxs-lookup"><span data-stu-id="29ec1-102">Step 4B: Start the Send Ports and Receive Ports for the FileAct Store and Forward Scenario</span></span>
<span data-ttu-id="29ec1-103">この手順を開始する前に行う必要があります[手順 4 a:FileAct ストア アンド フォワード シナリオ用に SWIFTNet サービスを開始](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-store-and-forward-scenario.md)します。</span><span class="sxs-lookup"><span data-stu-id="29ec1-103">Before you begin this step, you must complete [Step 4A: Start the SWIFTNet Service for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-store-and-forward-scenario.md).</span></span>  
  
### <a name="to-start-the-send-ports-and-receive-ports"></a><span data-ttu-id="29ec1-104">ポート、送信ポートと受信開始するには</span><span class="sxs-lookup"><span data-stu-id="29ec1-104">To start the send ports and receive ports</span></span>  
  
1.  <span data-ttu-id="29ec1-105">開始**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="29ec1-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="29ec1-106">コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成した BizTalk アプリケーションを順に展開します。</span><span class="sxs-lookup"><span data-stu-id="29ec1-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application where you created the send ports.</span></span>  
  
3.  <span data-ttu-id="29ec1-107">次の各送信ポート、送信ポートを右クリックし、クリックして**開始**:</span><span class="sxs-lookup"><span data-stu-id="29ec1-107">For each of the following send ports, right-click the send port, and then click **Start**:</span></span>  
  
    -   <span data-ttu-id="29ec1-108">**Tutorial_FA_SendResponseToReceiver**</span><span class="sxs-lookup"><span data-stu-id="29ec1-108">**Tutorial_FA_SendResponseToReceiver**</span></span>  
  
    -   <span data-ttu-id="29ec1-109">**Tutorial_FA_SendRequest_SnF**</span><span class="sxs-lookup"><span data-stu-id="29ec1-109">**Tutorial_FA_SendRequest_SnF**</span></span>  
  
    -   <span data-ttu-id="29ec1-110">**Tutorial_ GetStatusReports**</span><span class="sxs-lookup"><span data-stu-id="29ec1-110">**Tutorial_ GetStatusReports**</span></span>  
  
4.  <span data-ttu-id="29ec1-111">コンソール ツリーで、BizTalk グループを展開し、受信場所を作成した BizTalk アプリケーションを順に展開します。</span><span class="sxs-lookup"><span data-stu-id="29ec1-111">In the console tree, expand the BizTalk group, and then expand the BizTalk application where you created the receive locations.</span></span>  
  
5.  <span data-ttu-id="29ec1-112">次の受信場所ごとに、受信場所を右クリックし、順にクリックします**を有効にする**:</span><span class="sxs-lookup"><span data-stu-id="29ec1-112">For each of the following receive locations, right-click the receive location, and then click **Enable**:</span></span>  
  
    -   <span data-ttu-id="29ec1-113">**Tutorial_FA_InputRequest_SnF**</span><span class="sxs-lookup"><span data-stu-id="29ec1-113">**Tutorial_FA_InputRequest_SnF**</span></span>  
  
    -   <span data-ttu-id="29ec1-114">**Tutorial_FA_HandleRequestOneWay_SnF**</span><span class="sxs-lookup"><span data-stu-id="29ec1-114">**Tutorial_FA_HandleRequestOneWay_SnF**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29ec1-115">参照</span><span class="sxs-lookup"><span data-stu-id="29ec1-115">See Also</span></span>  
 <span data-ttu-id="29ec1-116">[手順 4:テスト FileAct ストア アンド フォワード エンド ツー エンドのシナリオ](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="29ec1-116">[Step 4: Test FileAct Store and Forward End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="29ec1-117">[手順 4 a:FileAct ストア アンド フォワード シナリオ用に SWIFTNet サービスを開始します。](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="29ec1-117">[Step 4A: Start the SWIFTNet Service for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="29ec1-118">[手順 4 C:FileAct ストア アンド フォワード シナリオ用のテスト インスタンスを作成します。](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="29ec1-118">[Step 4C: Create a Test Instance for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="29ec1-119">手順 4 D:FileAct ストア アンド フォワード シナリオ用に有効なインスタンスをテストします。</span><span class="sxs-lookup"><span data-stu-id="29ec1-119">Step 4D: Test a Valid Instance for the FileAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-fileact-store-and-forward-scenario.md)