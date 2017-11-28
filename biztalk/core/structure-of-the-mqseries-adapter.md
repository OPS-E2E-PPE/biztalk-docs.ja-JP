---
title: "MQSeries アダプターの構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- architecture, MQSeries adapters
- MQSeries adapters, architecture
ms.assetid: d25caf6a-3f93-4164-9c92-489b919a624d
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6239b78f0b9bd2c44a314b7ba0ba6ace8f3b78e4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="structure-of-the-mqseries-adapter"></a><span data-ttu-id="ca8ba-102">MQSeries アダプターの構造</span><span class="sxs-lookup"><span data-stu-id="ca8ba-102">Structure of the MQSeries Adapter</span></span>
<span data-ttu-id="ca8ba-103">MQSeries アダプタは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で実行されるアダプタと MQSeries Server for Windows で実行される COM+ アプリケーション (MQSAgent) の 2 つの部分で構成されます。</span><span class="sxs-lookup"><span data-stu-id="ca8ba-103">The MQSeries adapter has two parts: the adapter running under [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and a COM+ application, MQSAgent, running under MQSeries Server for Windows.</span></span> <span data-ttu-id="ca8ba-104">この関係を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="ca8ba-104">The following figure shows this relationship.</span></span>  
  
 <span data-ttu-id="ca8ba-105">![MQSeries アダプター コンポーネント](../core/media/bts-dev-mqoverallstructure.gif "BTS_Dev_MQOverallStructure")</span><span class="sxs-lookup"><span data-stu-id="ca8ba-105">![MQSeries Adapter components](../core/media/bts-dev-mqoverallstructure.gif "BTS_Dev_MQOverallStructure")</span></span>  
  
 <span data-ttu-id="ca8ba-106">アダプタによって、MQSAgent アプリケーションとの通信が行われます。</span><span class="sxs-lookup"><span data-stu-id="ca8ba-106">The adapter communicates with the MQSAgent application.</span></span> <span data-ttu-id="ca8ba-107">その後、MQSAgent アプリケーションによって、MQSeries Server for Windows との通信が行われます。</span><span class="sxs-lookup"><span data-stu-id="ca8ba-107">The MQSAgent application, in turn, communicates with MQSeries Server for Windows.</span></span> <span data-ttu-id="ca8ba-108">コンピュータに MQSeries Server for Windows をインストールした場合、アダプタと同じコンピュータにエージェントをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="ca8ba-108">You can install the agent on the same computer as the adapter if you install MQSeries Server for Windows on the computer.</span></span>  
  
 <span data-ttu-id="ca8ba-109">アダプタの送信部分では、メッセージを MQSAgent に送信します。</span><span class="sxs-lookup"><span data-stu-id="ca8ba-109">The send part of the adapter sends the message to the MQSAgent.</span></span> <span data-ttu-id="ca8ba-110">MQSAgent を使用して、 **MQPut**、MQSeries キュー マネージャにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="ca8ba-110">MQSAgent then, using **MQPut**, sends the message to the MQSeries Queue Manager.</span></span>  
  
 <span data-ttu-id="ca8ba-111">アダプタの受信部分では、MQSAgent をポーリングし、メッセージがあるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="ca8ba-111">The receive part of the adapter polls the MQSAgent to see if there are messages.</span></span> <span data-ttu-id="ca8ba-112">メッセージがあるときに、MQSAgent が実行する、 **MQGet**メッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="ca8ba-112">When there is a message, the MQSAgent performs an **MQGet** to retrieve the message.</span></span> <span data-ttu-id="ca8ba-113">MQSAgent では、キュー マネージャからメッセージを取得するときの待機時間が 3 秒にハードコードされています。</span><span class="sxs-lookup"><span data-stu-id="ca8ba-113">MQSAgent includes a hard-coded three-second wait for retrieving the message from the Queue Manager.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ca8ba-114">アダプタのポーリング間隔を設定できます。</span><span class="sxs-lookup"><span data-stu-id="ca8ba-114">You can set the polling interval of the adapter.</span></span> <span data-ttu-id="ca8ba-115">ポーリング間隔を 3 秒未満に設定すると、待機間隔にポーリング間隔が設定されます。</span><span class="sxs-lookup"><span data-stu-id="ca8ba-115">When you set the polling interval to less than three seconds, the wait interval is set to the polling interval.</span></span>  
  
 <span data-ttu-id="ca8ba-116">トランザクションでは、メッセージの送信アクションと受信アクションの両方が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="ca8ba-116">Both the send and receive message actions may occur in transactions.</span></span> <span data-ttu-id="ca8ba-117">これにより、アダプタがメッセージをロールバックし、送信操作または受信操作を再試行できる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ca8ba-117">This enables the adapter to roll back the message and, possibly, to retry the send or receive operations.</span></span> <span data-ttu-id="ca8ba-118">トランザクションの詳細については、次を参照してください。 [MQSeries アダプターのバッチ処理とトランザクション処理](../core/mqseries-adapter-batching-and-transaction-handling.md)です。</span><span class="sxs-lookup"><span data-stu-id="ca8ba-118">For more information about transactions, see [MQSeries Adapter Batching and Transaction Handling](../core/mqseries-adapter-batching-and-transaction-handling.md).</span></span>  
  
 <span data-ttu-id="ca8ba-119">アダプタは複数のコンピュータ間で動作するため、セキュリティに関する問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ca8ba-119">Because the adapter works across more than one computer, there is a possible security problem.</span></span> <span data-ttu-id="ca8ba-120">たとえば、悪意のあるプログラムによってエージェントの権限が借用され、データがキャプチャされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ca8ba-120">A hostile program could impersonate the agent and capture data.</span></span> <span data-ttu-id="ca8ba-121">アダプタとエージェントの拡張保護の詳細については、次を参照してください。 [MQSeries アダプタのセキュリティ](../core/mqseries-adapter-security.md)です。</span><span class="sxs-lookup"><span data-stu-id="ca8ba-121">For more information about enhanced protection for the adapter and agent, see [MQSeries Adapter Security](../core/mqseries-adapter-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca8ba-122">参照</span><span class="sxs-lookup"><span data-stu-id="ca8ba-122">See Also</span></span>  
 <span data-ttu-id="ca8ba-123">[MQSeries アダプターのアーキテクチャ](../core/mqseries-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="ca8ba-123">[MQSeries Adapter Architecture](../core/mqseries-adapter-architecture.md) </span></span>  
 [<span data-ttu-id="ca8ba-124">MQSeries アダプターとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="ca8ba-124">What Is the MQSeries Adapter?</span></span>](../core/what-is-the-mqseries-adapter.md)