---
title: 注文処理ステージで処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 698005da-1ba8-4972-83db-f5ae45fd6a83
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a8eae6b814af36d0ea07065726ca66518984703
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22265098"
---
# <a name="processing-in-the-order-processing-stages"></a><span data-ttu-id="18f2a-102">注文処理ステージでの処理</span><span class="sxs-lookup"><span data-stu-id="18f2a-102">Processing in the Order Processing Stages</span></span>
<span data-ttu-id="18f2a-103">ビジネス プロセス管理ソリューションには、2 つの段階が含まれています、 **CableOrder1**と**CableOrder2**注文処理アクションを実行するオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="18f2a-103">The Business Process Management solution includes two stages, the **CableOrder1** and **CableOrder2** orchestrations, that perform the order processing actions.</span></span> <span data-ttu-id="18f2a-104">注文処理ステージに分割する方法の詳細については、次を参照してください。[処理ステージの番号](../core/number-of-processing-stages.md)です。</span><span class="sxs-lookup"><span data-stu-id="18f2a-104">For more information about how the order process was divided into stages, see [Number of Processing Stages](../core/number-of-processing-stages.md).</span></span>  
  
 <span data-ttu-id="18f2a-105">どちらの処理ステージは、注文メッセージを受信すると、状態メッセージで応答を開始、 **OrderManager**オーケストレーションが開始されるとします。</span><span class="sxs-lookup"><span data-stu-id="18f2a-105">Both processing stages begin when they receive an order message and both reply with a status message to the **OrderManager** orchestration once they have started.</span></span> <span data-ttu-id="18f2a-106">同様に、メッセージがバックアップに、送信、 **OrderManager**ステージが完了またはエラーで終了したかどうかを示すためにします。</span><span class="sxs-lookup"><span data-stu-id="18f2a-106">Similarly, both send a message back to the **OrderManager** to indicate whether the stage completed or terminated with an error.</span></span> <span data-ttu-id="18f2a-107">間の接続の詳細について、 **OrderManager**オーケストレーションと処理ステージを参照してください。[逆パートナーの直接バインド](../core/inverse-direct-partner-binding.md)です。</span><span class="sxs-lookup"><span data-stu-id="18f2a-107">For details about the connection between the **OrderManager** orchestration and the processing stages, see [Inverse Direct Partner Binding](../core/inverse-direct-partner-binding.md).</span></span>  
  
 <span data-ttu-id="18f2a-108">自己関連付けを行う処理ステージを使用して、情報を送信する動的ポートにバックアップの両方、 **OrderManger**です。</span><span class="sxs-lookup"><span data-stu-id="18f2a-108">Both processing stages use self-correlating, dynamic ports to send information back to the **OrderManger**.</span></span> <span data-ttu-id="18f2a-109">動的なポートを使用して、ポート アドレスがメッセージから送信ポートにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="18f2a-109">With dynamic ports, the orchestrations copy the port address from the message to send port.</span></span>  
  
 <span data-ttu-id="18f2a-110">作成された正規化された標準の注文メッセージは、すべての注文メッセージを処理ステージが受信、 **OrderBroker**です。</span><span class="sxs-lookup"><span data-stu-id="18f2a-110">All of the order messages the processing stages receive are the normalized, canonical order messages created in the **OrderBroker**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="18f2a-111">長さのため、 **CableOrder1**と**CableOrder2**オーケストレーション、オーケストレーションを Microsoft Visual Studio で開いてこのセクションを参照する場合があります。</span><span class="sxs-lookup"><span data-stu-id="18f2a-111">Because of the length of the **CableOrder1** and **CableOrder2** orchestrations, you may want to read this section with the orchestrations open in Microsoft Visual Studio.</span></span>  
  
## <a name="the-cableorder1-orchestration"></a><span data-ttu-id="18f2a-112">CableOrder1 オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="18f2a-112">The CableOrder1 Orchestration</span></span>  
 <span data-ttu-id="18f2a-113">**CableOrder1**注文メッセージを受信したときに、オーケストレーションが開始します。</span><span class="sxs-lookup"><span data-stu-id="18f2a-113">The **CableOrder1** orchestration starts when it receives an order message.</span></span> <span data-ttu-id="18f2a-114">まず、このオーケストレーションでは、返信アドレスをメッセージからステージ完了ポートにコピーします。</span><span class="sxs-lookup"><span data-stu-id="18f2a-114">It then copies the reply address from the message to the stage completion port.</span></span> <span data-ttu-id="18f2a-115">次に、受信確認メッセージを構築しへの応答として送信、 **BeginStagePort**ポート、およびローカル変数に、ルーティング情報が保存されます。</span><span class="sxs-lookup"><span data-stu-id="18f2a-115">Next, it constructs an acknowledgement message and sends it as a response to the **BeginStagePort** port, and then saves the routing information in a local variable.</span></span>  
  
 <span data-ttu-id="18f2a-116">次に、SSO から構成情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="18f2a-116">The orchestration next gets the configuration information from SSO.</span></span> <span data-ttu-id="18f2a-117">ソリューションが SSO を使用する方法に関する詳細については、次を参照してください。[を使用して SSO の効率的なビジネス プロセス管理ソリューションで](../core/using-sso-efficiently-in-the-business-process-management-solution.md)です。</span><span class="sxs-lookup"><span data-stu-id="18f2a-117">For more information about how the solution uses SSO, see [Using SSO Efficiently in the Business Process Management Solution](../core/using-sso-efficiently-in-the-business-process-management-solution.md).</span></span>  
  
 <span data-ttu-id="18f2a-118">インスタンスを作成し、オーケストレーション、 **OrderHandler**バックエンド プロセスと通信するためにオブジェクト、メッセージの有効性を確認、メッセージを分析して、サービスの種類を決定および対処します。</span><span class="sxs-lookup"><span data-stu-id="18f2a-118">The orchestration then creates an instance of the **OrderHandler** object to communicate with the backend processes, checks the validity of the message, analyzes the message, determines the service type, and which action to take.</span></span> <span data-ttu-id="18f2a-119">呼び出し順序のアクションのオーケストレーションのいずれかによっては、実行するアクション、 **Activate**、**変更**、または**キャンセル**渡します、 **OrderHandler**オーケストレーションへのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="18f2a-119">Depending on the action to take, it calls one of the order action orchestrations **Activate**, **Change**, or **Cancel** and passes the **OrderHandler** object to the orchestration.</span></span>  
  
 <span data-ttu-id="18f2a-120">**CableOrder1**し、オーケストレーション、バックアップ、割り込みを聞くに待機し、機能グループにメッセージが送信をチェックします。</span><span class="sxs-lookup"><span data-stu-id="18f2a-120">The **CableOrder1** orchestration then checks for an interrupt, sends a message to the facilities group and waits to hear back.</span></span> <span data-ttu-id="18f2a-121">機能グループからメッセージが返されると、処理を続行します。</span><span class="sxs-lookup"><span data-stu-id="18f2a-121">If the orchestration gets a message back from the facilities group, it continues processing.</span></span> <span data-ttu-id="18f2a-122">割り込みがあった場合、オーケストレーションは割り込み例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="18f2a-122">Otherwise, if there is an interrupt, the orchestration throws an interrupt exception.</span></span>  
  
 <span data-ttu-id="18f2a-123">作成して、完了のメッセージと経由の送信が完了すると、オーケストレーション、 **StageCompletion**ポートです。</span><span class="sxs-lookup"><span data-stu-id="18f2a-123">The orchestration finishes by constructing a completion message and sending it through the **StageCompletion** port.</span></span>  
  
## <a name="the-cableorder2-orchestration"></a><span data-ttu-id="18f2a-124">CableOrder2 オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="18f2a-124">The CableOrder2 Orchestration</span></span>  
 <span data-ttu-id="18f2a-125">CableOrder2 オーケストレーションが同じを実行、CableOrder1 オーケストレーション、ルーティングについては、SSO 構成情報と手順を開始してのインスタンスを作成する、 **OrderHandler**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="18f2a-125">The CableOrder2 orchestration performs the same starting steps as the CableOrder1 orchestration for the routing information, SSO configuration information, and creating an instance of the **OrderHandler** object.</span></span>  
  
 <span data-ttu-id="18f2a-126">割り込みとパスを調べ、オーケストレーション、 **OrderHandler**オブジェクトへの呼び出しで、**完了**オーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="18f2a-126">The orchestration then checks for an interrupt and passes the **OrderHandler** object in a call to the **Complete** orchestration.</span></span> <span data-ttu-id="18f2a-127">次に、オーケストレーション注文ステータス メッセージを作成、注文履歴を更新し、を通じて、完了のメッセージを送信、 **StageCompletion**ポートです。</span><span class="sxs-lookup"><span data-stu-id="18f2a-127">Next, the orchestration creates an order status message, updates the order history, and sends a completion message through the **StageCompletion** port.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18f2a-128">参照</span><span class="sxs-lookup"><span data-stu-id="18f2a-128">See Also</span></span>  
 <span data-ttu-id="18f2a-129">[ビジネス プロセス管理ソリューションのバージョン管理](../core/versioning-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="18f2a-129">[Versioning the Business Process Management Solution](../core/versioning-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="18f2a-130">ビジネス プロセス管理ソリューションでの処理</span><span class="sxs-lookup"><span data-stu-id="18f2a-130">Processing in the Business Process Management Solution</span></span>](../core/processing-in-the-business-process-management-solution.md)