---
title: "手順 3 b: FileAct ストア アンド フォワード (プル) シナリオ用の動的送信ポートにオーケストレーションをバインド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb973066-8797-4f51-a89e-3845f2811605
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10111de1080aacd532be96f501be1d20acda1dc5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3b-bind-the-orchestration-with-dynamic-send-port-for-fileact-store-and-forward-pull-scenario"></a><span data-ttu-id="bb81b-102">手順 3 b: FileAct ストア アンド フォワード (プル) シナリオ用の動的送信ポートにオーケストレーションをバインド</span><span class="sxs-lookup"><span data-stu-id="bb81b-102">Step 3B: Bind the orchestration with dynamic send port for FileAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="bb81b-103">この手順を開始する前に行う必要があります[手順 3A: FileAct ストア アンド フォワード (プル) シナリオの動的送信ポート用のオーケストレーションを作成](../../adapters-and-accelerators/fileact-interact/step-3a-create-orchestration-for-dynamic-send-port-fileact-store-and-forward.md)です。</span><span class="sxs-lookup"><span data-stu-id="bb81b-103">Before you begin this step, you must complete [Step 3A: Create an orchestration for dynamic send port for FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-create-orchestration-for-dynamic-send-port-fileact-store-and-forward.md).</span></span>  
  
### <a name="to-add-a-file-receive-location"></a><span data-ttu-id="bb81b-104">ファイル受信場所を追加するには</span><span class="sxs-lookup"><span data-stu-id="bb81b-104">To add a FILE Receive location</span></span>  
  
1.  <span data-ttu-id="bb81b-105">開始**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="bb81b-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="bb81b-106">左側のウィンドウで、BizTalk Server 管理コンソールで BizTalk Server 管理コンソールを展開し、 **BizTalk グループ**、展開**プラットフォームの設定**、クリックして**ホスト インスタンス**.</span><span class="sxs-lookup"><span data-stu-id="bb81b-106">In the BizTalk Server Administration Console, in the left pane, expand BizTalk Server Administration, expand **BizTalk Group**, expand **Platform Settings**, and then click **Host Instances**.</span></span> <span data-ttu-id="bb81b-107">いることを確認の状態、 **BizTalkServerApplication**と FileActhost インスタンスのインスタンスをホストが**を実行している**です。</span><span class="sxs-lookup"><span data-stu-id="bb81b-107">Verify that the status for the **BizTalkServerApplication** host instance and FileActhost instance is **running**.</span></span> <span data-ttu-id="bb81b-108">ホスト インスタンスを右クリックしをクリックしていない場合は、**開始**です。</span><span class="sxs-lookup"><span data-stu-id="bb81b-108">If not, right-click the host instances, and click **Start**.</span></span>  
  
3.  <span data-ttu-id="bb81b-109">左側のウィンドウで、アプリケーションを展開し、BizTalk アプリケーション 1 の順に展開します。</span><span class="sxs-lookup"><span data-stu-id="bb81b-109">In the left pane, expand Applications, and then expand BizTalk Application 1.</span></span> <span data-ttu-id="bb81b-110">[オーケストレーション] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb81b-110">Click Orchestrations.</span></span>  
  
4.  <span data-ttu-id="bb81b-111">右クリック**DynamicSendOrchestration**  をクリック**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="bb81b-111">Right-click **DynamicSendOrchestration** and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="bb81b-112">**オーケストレーションのプロパティ**ダイアログ ボックスで、左側のウィンドウでをクリックして**バインド**し、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="bb81b-112">In the **Orchestration Properties** dialog box, in the left pane, click **Bindings** and do the following:</span></span>  
  
    |<span data-ttu-id="bb81b-113">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="bb81b-113">**Use this**</span></span>|<span data-ttu-id="bb81b-114">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="bb81b-114">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="bb81b-115">**ホスト**</span><span class="sxs-lookup"><span data-stu-id="bb81b-115">**Host**</span></span>|<span data-ttu-id="bb81b-116">ドロップダウン リストから選択**BizTalkServer アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="bb81b-116">From the drop-down list, select **BizTalkServer Application**.</span></span>|  
    |<span data-ttu-id="bb81b-117">**動的なプル**</span><span class="sxs-lookup"><span data-stu-id="bb81b-117">**Dynamic Pull**</span></span>|<span data-ttu-id="bb81b-118">ドロップダウン リストから選択**Tutorial_FA_DynamicSendPort**です。</span><span class="sxs-lookup"><span data-stu-id="bb81b-118">From the drop-down list, select **Tutorial_FA_DynamicSendPort**.</span></span>|  
    |<span data-ttu-id="bb81b-119">**SendPullResponseToSender**</span><span class="sxs-lookup"><span data-stu-id="bb81b-119">**SendPullResponseToSender**</span></span>|<span data-ttu-id="bb81b-120">ドロップダウン リストから選択**Tutorial_FA_SendPullResponsetoReceiver**です。</span><span class="sxs-lookup"><span data-stu-id="bb81b-120">From the drop-down list, select **Tutorial_FA_SendPullResponsetoReceiver**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bb81b-121">参照</span><span class="sxs-lookup"><span data-stu-id="bb81b-121">See Also</span></span>  
 [<span data-ttu-id="bb81b-122">手順 3: FileAct ストア アンド フォワード (プル) シナリオの動的送信ポート用のオーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="bb81b-122">Step 3A: Create an orchestration for dynamic send port for FileAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3a-create-orchestration-for-dynamic-send-port-fileact-store-and-forward.md)