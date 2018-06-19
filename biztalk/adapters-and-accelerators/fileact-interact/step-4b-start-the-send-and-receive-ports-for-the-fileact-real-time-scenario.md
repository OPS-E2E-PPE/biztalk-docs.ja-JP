---
title: '手順 4 b: 送信ポートの開始し、受信ポートを FileAct リアルタイムのシナリオの |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c56b5f7b-551a-4bd2-97c7-0996f5d1b1a2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a9933f347d2da08dc2b8665dfd01530871a8cdf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225426"
---
# <a name="step-4b-start-the-send-ports-and-receive-ports-for-the-fileact-real-time-scenario"></a><span data-ttu-id="26c31-102">手順 4 b: 送信ポートを開始および FileAct リアルタイム シナリオでは、受信ポート</span><span class="sxs-lookup"><span data-stu-id="26c31-102">Step 4B: Start the Send Ports and Receive Ports for the FileAct Real-Time Scenario</span></span>
<span data-ttu-id="26c31-103">この手順を開始する前に行う必要があります[手順 4A: FileAct リアルタイム シナリオの SWIFTNet サービス起動](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-real-time-scenario.md)です。</span><span class="sxs-lookup"><span data-stu-id="26c31-103">Before you begin this step, you must complete [Step 4A: Start the SWIFTNet Service for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-real-time-scenario.md).</span></span>  
  
### <a name="to-start-the-send-ports-and-receive-ports"></a><span data-ttu-id="26c31-104">送信ポートの開始し、受信ポートに</span><span class="sxs-lookup"><span data-stu-id="26c31-104">To start the send ports and receive ports</span></span>  
  
1.  <span data-ttu-id="26c31-105">開始**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="26c31-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="26c31-106">コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成した BizTalk アプリケーションの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="26c31-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application where you created the send ports.</span></span>  
  
3.  <span data-ttu-id="26c31-107">次の各送信ポート、送信ポートを右クリックし、クリックして**開始**:</span><span class="sxs-lookup"><span data-stu-id="26c31-107">For each of the following send ports, right-click the send port, and then click **Start**:</span></span>  
  
    -   <span data-ttu-id="26c31-108">**Tutorial_FA_SendResponseToReceiver**</span><span class="sxs-lookup"><span data-stu-id="26c31-108">**Tutorial_FA_SendResponseToReceiver**</span></span>  
  
    -   <span data-ttu-id="26c31-109">**Tutorial_FA_SendResponseToSender**</span><span class="sxs-lookup"><span data-stu-id="26c31-109">**Tutorial_FA_SendResponseToSender**</span></span>  
  
    -   <span data-ttu-id="26c31-110">**Tutorial_FA_SendRequest_RealTime**</span><span class="sxs-lookup"><span data-stu-id="26c31-110">**Tutorial_FA_SendRequest_RealTime**</span></span>  
  
    -   <span data-ttu-id="26c31-111">**Tutorial_ GetStatusReports**</span><span class="sxs-lookup"><span data-stu-id="26c31-111">**Tutorial_ GetStatusReports**</span></span>  
  
4.  <span data-ttu-id="26c31-112">コンソール ツリーで、BizTalk グループを展開し、受信場所を作成した BizTalk アプリケーションの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="26c31-112">In the console tree, expand the BizTalk group, and then expand the BizTalk application where you created the receive locations.</span></span>  
  
5.  <span data-ttu-id="26c31-113">次の受信場所ごとに、受信場所を右クリックし、をクリックして**を有効にする**:</span><span class="sxs-lookup"><span data-stu-id="26c31-113">For each of the following receive locations, right-click the receive location, and then click **Enable**:</span></span>  
  
    -   <span data-ttu-id="26c31-114">**Tutorial_FA_InputRequest_RealTime**</span><span class="sxs-lookup"><span data-stu-id="26c31-114">**Tutorial_FA_InputRequest_RealTime**</span></span>  
  
    -   <span data-ttu-id="26c31-115">**Tutorial_FA_HandleRequestOneWay_RealTime**</span><span class="sxs-lookup"><span data-stu-id="26c31-115">**Tutorial_FA_HandleRequestOneWay_RealTime**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26c31-116">参照</span><span class="sxs-lookup"><span data-stu-id="26c31-116">See Also</span></span>  
 <span data-ttu-id="26c31-117">[手順 4: FileAct エンド ツー エンドのリアルタイムのシナリオをテストします。](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="26c31-117">[Step 4: Test FileAct Real-Time End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="26c31-118">[手順 4 a: FileAct リアルタイム シナリオの SWIFTNet サービスの開始](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="26c31-118">[Step 4A: Start the SWIFTNet Service for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="26c31-119">[手順 4 C: FileAct リアルタイム シナリオのテスト インスタンスを作成](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="26c31-119">[Step 4C: Create a Test Instance for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="26c31-120">手順 4 D: FileAct リアルタイム シナリオでは、有効なインスタンスをテストします。</span><span class="sxs-lookup"><span data-stu-id="26c31-120">Step 4D: Test a Valid Instance for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-fileact-real-time-scenario.md)