---
title: "手順 3 b: InterAct ストアと転送 (するプル) シナリオ用の動的送信ポートにオーケストレーションをバインド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 55eec1f3-b920-48f8-946a-9ad7afa36fd6
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b289d8478eb020067d9231fb1d4f135c7b43b289
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3b-bind-the-orchestration-with-dynamic-send-port-for-interact-store-and-forward-pull-scenario"></a><span data-ttu-id="01acb-102">手順 3 b: InterAct ストアと転送 (するプル) シナリオ用の動的送信ポートにオーケストレーションをバインド</span><span class="sxs-lookup"><span data-stu-id="01acb-102">Step 3B: Bind the orchestration with dynamic send port for InterAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="01acb-103">この手順を開始する前に行う必要があります[手順 3A: InterAct ストアと転送 (するプル) シナリオの動的送信ポートのオーケストレーションを作成](../../adapters-and-accelerators/fileact-interact/step-3a-create-orchestration-for-dynamic-send-port-interact-store-and-forward.md)です。</span><span class="sxs-lookup"><span data-stu-id="01acb-103">Before you begin this step, you must complete [Step 3A: Create an orchestration for dynamic send port for InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-create-orchestration-for-dynamic-send-port-interact-store-and-forward.md).</span></span>  
  
### <a name="to-add-a-file-receive-location"></a><span data-ttu-id="01acb-104">ファイル受信場所を追加するには</span><span class="sxs-lookup"><span data-stu-id="01acb-104">To add a FILE Receive location</span></span>  
  
1.  <span data-ttu-id="01acb-105">開始**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="01acb-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="01acb-106">左側のウィンドウで、BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**プラットフォームの設定**、し、をクリックして**ホスト インスタンス**です。</span><span class="sxs-lookup"><span data-stu-id="01acb-106">In the BizTalk Server Administration Console, in the left pane, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Host Instances**.</span></span> <span data-ttu-id="01acb-107">いることを確認の状態、 **BizTalkServerApplication**インスタンスと対話するホスト インスタンスをホストが**を実行している**です。</span><span class="sxs-lookup"><span data-stu-id="01acb-107">Verify that the status for the **BizTalkServerApplication** host instance and Interact host instance is **running**.</span></span> <span data-ttu-id="01acb-108">ホスト インスタンスを右クリックしをクリックしていない場合は、**開始**です。</span><span class="sxs-lookup"><span data-stu-id="01acb-108">If not, right-click the host instances, and click **Start**.</span></span>  
  
3.  <span data-ttu-id="01acb-109">左側のウィンドウで、アプリケーションを展開し、BizTalk アプリケーション 1 の順に展開します。</span><span class="sxs-lookup"><span data-stu-id="01acb-109">In the left pane, expand Applications, and then expand BizTalk Application 1.</span></span> <span data-ttu-id="01acb-110">[オーケストレーション] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01acb-110">Click Orchestrations.</span></span>  
  
4.  <span data-ttu-id="01acb-111">右クリック**DynamicSendOrchestration**  をクリック**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="01acb-111">Right-click **DynamicSendOrchestration** and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="01acb-112">**オーケストレーションのプロパティ**ダイアログ ボックスで、左側のウィンドウでをクリックして**バインド**し、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="01acb-112">In the **Orchestration Properties** dialog box, in the left pane, click **Bindings** and do the following:</span></span>  
  
    |<span data-ttu-id="01acb-113">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="01acb-113">**Use this**</span></span>|<span data-ttu-id="01acb-114">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="01acb-114">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="01acb-115">**ホスト**</span><span class="sxs-lookup"><span data-stu-id="01acb-115">**Host**</span></span>|<span data-ttu-id="01acb-116">ドロップダウン リストから選択**BizTalkServer アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="01acb-116">From the drop-down list, select **BizTalkServer Application**.</span></span>|  
    |<span data-ttu-id="01acb-117">**動的なプル**</span><span class="sxs-lookup"><span data-stu-id="01acb-117">**Dynamic Pull**</span></span>|<span data-ttu-id="01acb-118">ドロップダウン リストから選択**Tutorial_IA_DynamicSendPort**です。</span><span class="sxs-lookup"><span data-stu-id="01acb-118">From the drop-down list, select **Tutorial_IA_DynamicSendPort**.</span></span>|  
    |<span data-ttu-id="01acb-119">**SendPullResponseToSender**</span><span class="sxs-lookup"><span data-stu-id="01acb-119">**SendPullResponseToSender**</span></span>|<span data-ttu-id="01acb-120">ドロップダウン リストから選択**Tutorial_IA_SendPullResponsetoReceiver**です。</span><span class="sxs-lookup"><span data-stu-id="01acb-120">From the drop-down list, select **Tutorial_IA_SendPullResponsetoReceiver**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="01acb-121">参照</span><span class="sxs-lookup"><span data-stu-id="01acb-121">See Also</span></span>  
 [<span data-ttu-id="01acb-122">手順 3: InterAct ストアと転送 (するプル) シナリオの動的送信ポートのオーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="01acb-122">Step 3A: Create an orchestration for dynamic send port for InterAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3a-create-orchestration-for-dynamic-send-port-interact-store-and-forward.md)