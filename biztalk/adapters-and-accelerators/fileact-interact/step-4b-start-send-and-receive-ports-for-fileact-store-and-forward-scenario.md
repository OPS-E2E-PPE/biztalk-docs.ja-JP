---
title: '手順 4 b: 送信ポートの開始し、FileAct ストア アンド フォワード (プル) シナリオの受信ポート |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea2215c5-fb43-4c7e-a42d-5d131a6dee38
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad4c6b9d17ab1ea55c1f8378f1cb481a07b09e34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224394"
---
# <a name="step-4b-start-the-send-ports-and-receive-ports-for-the-fileact-store-and-forward-pull-scenario"></a><span data-ttu-id="2f13c-102">手順 4 b: 送信ポートの開始し、FileAct ストア アンド フォワード (プル) シナリオの受信ポート</span><span class="sxs-lookup"><span data-stu-id="2f13c-102">Step 4B: Start the Send Ports and Receive Ports for the FileAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="2f13c-103">この手順を開始する前に行う必要があります[手順 4A: FileAct ストア アンド フォワード (プル) シナリオの SWIFTNet サービス起動](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-fileact-store-and-forward-pull-scenario.md)です。</span><span class="sxs-lookup"><span data-stu-id="2f13c-103">Before you begin this step, you must complete [Step 4A: Start the SWIFTNet Service for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-fileact-store-and-forward-pull-scenario.md).</span></span>  
  
### <a name="to-start-the-send-ports-and-receive-ports"></a><span data-ttu-id="2f13c-104">送信ポートの開始し、受信ポートに</span><span class="sxs-lookup"><span data-stu-id="2f13c-104">To start the send ports and receive ports</span></span>  
  
1.  <span data-ttu-id="2f13c-105">開始**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="2f13c-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="2f13c-106">コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成した BizTalk アプリケーションの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="2f13c-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application where you created the send ports.</span></span>  
  
3.  <span data-ttu-id="2f13c-107">次の各送信ポート、送信ポートを右クリックし、クリックして**開始**:</span><span class="sxs-lookup"><span data-stu-id="2f13c-107">For each of the following send ports, right-click the send port, and then click **Start**:</span></span>  
  
    -   <span data-ttu-id="2f13c-108">**Tutorial_ FA_SendPullResponseToReceiver**</span><span class="sxs-lookup"><span data-stu-id="2f13c-108">**Tutorial_ FA_SendPullResponseToReceiver**</span></span>  
  
    -   <span data-ttu-id="2f13c-109">**Tutorial_ FA_SendRequest_SnF**</span><span class="sxs-lookup"><span data-stu-id="2f13c-109">**Tutorial_ FA_SendRequest_SnF**</span></span>  
  
    -   <span data-ttu-id="2f13c-110">**Tutorial_ FA_DynamicSendPort**</span><span class="sxs-lookup"><span data-stu-id="2f13c-110">**Tutorial_ FA_DynamicSendPort**</span></span>  
  
4.  <span data-ttu-id="2f13c-111">コンソール ツリーで、BizTalk グループを展開し、受信場所を作成した BizTalk アプリケーションの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="2f13c-111">In the console tree, expand the BizTalk group, and then expand the BizTalk application where you created the receive locations.</span></span>  
  
5.  <span data-ttu-id="2f13c-112">次の受信場所ごとに、受信場所を右クリックし、をクリックして**を有効にする**:</span><span class="sxs-lookup"><span data-stu-id="2f13c-112">For each of the following receive locations, right-click the receive location, and then click **Enable**:</span></span>  
  
    -   <span data-ttu-id="2f13c-113">**Tutorial_ FA_InputRequest_SnF**</span><span class="sxs-lookup"><span data-stu-id="2f13c-113">**Tutorial_ FA_InputRequest_SnF**</span></span>  
  
    -   <span data-ttu-id="2f13c-114">**Tutorial_ FA_InputRequest_PullMode**</span><span class="sxs-lookup"><span data-stu-id="2f13c-114">**Tutorial_ FA_InputRequest_PullMode**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f13c-115">参照</span><span class="sxs-lookup"><span data-stu-id="2f13c-115">See Also</span></span>  
 <span data-ttu-id="2f13c-116">[手順 4 a: FileAct ストア アンド フォワード (プル) シナリオの SWIFTNet サービスの開始](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-fileact-store-and-forward-pull-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="2f13c-116">[Step 4A: Start the SWIFTNet Service for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-fileact-store-and-forward-pull-scenario.md) </span></span>  
 <span data-ttu-id="2f13c-117">[手順 4 C: FileAct ストア アンド フォワード (プル) シナリオのテスト インスタンスを作成します。](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-fileact-store-and-forward-pull-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="2f13c-117">[Step 4C: Create a Test Instance for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-fileact-store-and-forward-pull-scenario.md) </span></span>  
 [<span data-ttu-id="2f13c-118">手順 4 D: FileAct ストア アンド フォワード (プル) シナリオの有効なインスタンスのテスト</span><span class="sxs-lookup"><span data-stu-id="2f13c-118">Step 4D: Test a Valid Instance for the FileAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-fileact-store-and-forward-pull-scenario.md)