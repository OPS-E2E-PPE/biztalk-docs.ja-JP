---
title: '手順 4 b: 送信ポートの開始し、受信のポート、リアルタイムのシナリオを対話 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dffee9a6-5877-4744-9b46-12ca4f8fa959
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3391f966fb1033ec1886f44b62158f910179d72f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224322"
---
# <a name="step-4b-start-the-send-ports-and-receive-ports-for-the-interact-real-time-scenario"></a><span data-ttu-id="4e686-102">手順 4 b: 送信ポートの開始し、受信のポート、リアルタイムのシナリオの対話</span><span class="sxs-lookup"><span data-stu-id="4e686-102">Step 4B: Start the Send Ports and Receive Ports for the InterAct Real-Time Scenario</span></span>
<span data-ttu-id="4e686-103">この手順を開始する前に行う必要があります[手順 4A: サービスを開始します SWIFTNet](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md)です。</span><span class="sxs-lookup"><span data-stu-id="4e686-103">Before you begin this step, you must complete [Step 4A: Start the SWIFTNet Service](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md).</span></span>  
  
### <a name="to-start-the-send-ports-and-receive-ports"></a><span data-ttu-id="4e686-104">送信ポートの開始し、受信ポートに</span><span class="sxs-lookup"><span data-stu-id="4e686-104">To start the send ports and receive ports</span></span>  
  
1.  <span data-ttu-id="4e686-105">開始**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="4e686-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="4e686-106">コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成した BizTalk アプリケーションの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="4e686-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application where you created the send ports.</span></span>  
  
3.  <span data-ttu-id="4e686-107">次の各送信ポート、送信ポートを右クリックし、クリックして**開始**:</span><span class="sxs-lookup"><span data-stu-id="4e686-107">For each of the following send ports, right-click the send port, and then click **Start**:</span></span>  
  
    -   <span data-ttu-id="4e686-108">**Tutorial_IA_SendResponseToReceiver**</span><span class="sxs-lookup"><span data-stu-id="4e686-108">**Tutorial_IA_SendResponseToReceiver**</span></span>  
  
    -   <span data-ttu-id="4e686-109">**Tutorial_IA_SendResponseToSender**</span><span class="sxs-lookup"><span data-stu-id="4e686-109">**Tutorial_IA_SendResponseToSender**</span></span>  
  
    -   <span data-ttu-id="4e686-110">**Tutorial_IA_SendRequest_RealTime**</span><span class="sxs-lookup"><span data-stu-id="4e686-110">**Tutorial_IA_SendRequest_RealTime**</span></span>  
  
4.  <span data-ttu-id="4e686-111">コンソール ツリーで、BizTalk グループを展開し、受信場所を作成した BizTalk アプリケーションの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="4e686-111">In the console tree, expand the BizTalk group, and then expand the BizTalk application where you created the receive locations.</span></span>  
  
5.  <span data-ttu-id="4e686-112">次の受信場所ごとに、受信場所を右クリックし、をクリックして**を有効にする**:</span><span class="sxs-lookup"><span data-stu-id="4e686-112">For each of the following receive locations, right-click the receive location, and then click **Enable**:</span></span>  
  
    -   <span data-ttu-id="4e686-113">**Tutorial_IA_InputRequest_RealTime**</span><span class="sxs-lookup"><span data-stu-id="4e686-113">**Tutorial_IA_InputRequest_RealTime**</span></span>  
  
    -   <span data-ttu-id="4e686-114">**Tutorial_IA_HandleRequestOneWay_RealTime**</span><span class="sxs-lookup"><span data-stu-id="4e686-114">**Tutorial_IA_HandleRequestOneWay_RealTime**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e686-115">参照</span><span class="sxs-lookup"><span data-stu-id="4e686-115">See Also</span></span>  
 <span data-ttu-id="4e686-116">[手順 4: テスト、リアルタイムのエンド ツー エンド シナリオの対話](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="4e686-116">[Step 4: Test the InterAct Real-Time End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="4e686-117">[手順 4 a: SWIFTNet サービスの開始](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md) </span><span class="sxs-lookup"><span data-stu-id="4e686-117">[Step 4A: Start the SWIFTNet Service](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md) </span></span>  
 <span data-ttu-id="4e686-118">[手順 4 C: のテスト インスタンスを作成、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="4e686-118">[Step 4C: Create a Test Instance for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="4e686-119">手順 4 D: テストの有効なインスタンス、リアルタイムのシナリオの対話</span><span class="sxs-lookup"><span data-stu-id="4e686-119">Step 4D: Test a Valid Instance for the InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-interact-real-time-scenario.md)