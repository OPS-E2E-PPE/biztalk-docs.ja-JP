---
title: MQSeries アダプターの構造 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, MQSeries adapters
- MQSeries adapters, architecture
ms.assetid: d25caf6a-3f93-4164-9c92-489b919a624d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21bd7d9dee24e8235aff34a14babd4cc69240c74
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379942"
---
# <a name="structure-of-the-mqseries-adapter"></a><span data-ttu-id="0b9ff-102">MQSeries アダプターの構造</span><span class="sxs-lookup"><span data-stu-id="0b9ff-102">Structure of the MQSeries Adapter</span></span>
<span data-ttu-id="0b9ff-103">MQSeries アダプターが 2 つの部分: で実行されるアダプタ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、MQSAgent COM + アプリケーション、Windows の MQSeries サーバーの下で実行されているとします。</span><span class="sxs-lookup"><span data-stu-id="0b9ff-103">The MQSeries adapter has two parts: the adapter running under [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and a COM+ application, MQSAgent, running under MQSeries Server for Windows.</span></span> <span data-ttu-id="0b9ff-104">次の図は、この関係を示します。</span><span class="sxs-lookup"><span data-stu-id="0b9ff-104">The following figure shows this relationship.</span></span>  
  
 <span data-ttu-id="0b9ff-105">![MQSeries アダプター コンポーネント](../core/media/bts-dev-mqoverallstructure.gif "BTS_Dev_MQOverallStructure")</span><span class="sxs-lookup"><span data-stu-id="0b9ff-105">![MQSeries Adapter components](../core/media/bts-dev-mqoverallstructure.gif "BTS_Dev_MQOverallStructure")</span></span>  
  
 <span data-ttu-id="0b9ff-106">アダプターは、MQSAgent アプリケーションと通信します。</span><span class="sxs-lookup"><span data-stu-id="0b9ff-106">The adapter communicates with the MQSAgent application.</span></span> <span data-ttu-id="0b9ff-107">さらに、MQSAgent アプリケーションは Windows の MQSeries Server と通信します。</span><span class="sxs-lookup"><span data-stu-id="0b9ff-107">The MQSAgent application, in turn, communicates with MQSeries Server for Windows.</span></span> <span data-ttu-id="0b9ff-108">MQSeries Server を Windows のコンピューターにインストールする場合は、アダプターと同じコンピューターにエージェントをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="0b9ff-108">You can install the agent on the same computer as the adapter if you install MQSeries Server for Windows on the computer.</span></span>  
  
 <span data-ttu-id="0b9ff-109">アダプターの送信部分は、メッセージを MQSAgent に送信します。</span><span class="sxs-lookup"><span data-stu-id="0b9ff-109">The send part of the adapter sends the message to the MQSAgent.</span></span> <span data-ttu-id="0b9ff-110">MQSAgent を使用して、 **MQPut**、MQSeries キュー マネージャにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="0b9ff-110">MQSAgent then, using **MQPut**, sends the message to the MQSeries Queue Manager.</span></span>  
  
 <span data-ttu-id="0b9ff-111">アダプターの受信部分では、メッセージがないかどうかに、MQSAgent をポーリングします。</span><span class="sxs-lookup"><span data-stu-id="0b9ff-111">The receive part of the adapter polls the MQSAgent to see if there are messages.</span></span> <span data-ttu-id="0b9ff-112">メッセージがある場合、MQSAgent を実行、 **MQGet**メッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="0b9ff-112">When there is a message, the MQSAgent performs an **MQGet** to retrieve the message.</span></span> <span data-ttu-id="0b9ff-113">MQSAgent には、キュー マネージャーからメッセージを取得するためのハード コーディングされた 3 秒待機が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0b9ff-113">MQSAgent includes a hard-coded three-second wait for retrieving the message from the Queue Manager.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0b9ff-114">アダプターのポーリング間隔を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="0b9ff-114">You can set the polling interval of the adapter.</span></span> <span data-ttu-id="0b9ff-115">ポーリング間隔を 3 秒未満に設定すると、待機間隔はポーリング間隔を設定します。</span><span class="sxs-lookup"><span data-stu-id="0b9ff-115">When you set the polling interval to less than three seconds, the wait interval is set to the polling interval.</span></span>  
  
 <span data-ttu-id="0b9ff-116">両方の送信とアクションがトランザクションで発生するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b9ff-116">Both the send and receive message actions may occur in transactions.</span></span> <span data-ttu-id="0b9ff-117">これにより、アダプターがメッセージをロールバック、および送信を再試行してください。 または、操作を受信します。</span><span class="sxs-lookup"><span data-stu-id="0b9ff-117">This enables the adapter to roll back the message and, possibly, to retry the send or receive operations.</span></span> <span data-ttu-id="0b9ff-118">トランザクションの詳細については、次を参照してください。 [MQSeries アダプターのバッチ処理とトランザクション処理](../core/mqseries-adapter-batching-and-transaction-handling.md)します。</span><span class="sxs-lookup"><span data-stu-id="0b9ff-118">For more information about transactions, see [MQSeries Adapter Batching and Transaction Handling](../core/mqseries-adapter-batching-and-transaction-handling.md).</span></span>  
  
 <span data-ttu-id="0b9ff-119">アダプターは、1 つ以上のコンピューター間では、セキュリティ上の問題があります。</span><span class="sxs-lookup"><span data-stu-id="0b9ff-119">Because the adapter works across more than one computer, there is a possible security problem.</span></span> <span data-ttu-id="0b9ff-120">エージェントとキャプチャのデータが悪意のあるプログラムの権限を借用でした。</span><span class="sxs-lookup"><span data-stu-id="0b9ff-120">A hostile program could impersonate the agent and capture data.</span></span> <span data-ttu-id="0b9ff-121">アダプターとエージェントの拡張保護の詳細については、次を参照してください。 [MQSeries アダプターのセキュリティ](../core/mqseries-adapter-security.md)します。</span><span class="sxs-lookup"><span data-stu-id="0b9ff-121">For more information about enhanced protection for the adapter and agent, see [MQSeries Adapter Security](../core/mqseries-adapter-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b9ff-122">参照</span><span class="sxs-lookup"><span data-stu-id="0b9ff-122">See Also</span></span>  
 <span data-ttu-id="0b9ff-123">[MQSeries アダプターのアーキテクチャ](../core/mqseries-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="0b9ff-123">[MQSeries Adapter Architecture](../core/mqseries-adapter-architecture.md) </span></span>  
 [<span data-ttu-id="0b9ff-124">MQSeries アダプターとは</span><span class="sxs-lookup"><span data-stu-id="0b9ff-124">What Is the MQSeries Adapter?</span></span>](../core/what-is-the-mqseries-adapter.md)