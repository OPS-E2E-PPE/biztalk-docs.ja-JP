---
title: "MSMQ アダプターのパフォーマンスを最適化する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, performance
- performance, MSMQ adapters
- configuring [MSMQ adapters], performance
ms.assetid: f8537ea8-a96e-4874-bcaf-cd1442a50bd4
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e554de9b00869db4a258f03984fe1ebc71e99c38
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="optimizing-performance-of-the-msmq-adapter"></a><span data-ttu-id="6c036-102">MSMQ アダプターのパフォーマンスを最適化します。</span><span class="sxs-lookup"><span data-stu-id="6c036-102">Optimizing Performance of the MSMQ Adapter</span></span>
<span data-ttu-id="6c036-103">MSMQ アダプターの最適化は、送信側と受信側で異なります。</span><span class="sxs-lookup"><span data-stu-id="6c036-103">Optimization of the MSMQ adapter differs between the send and receive sides.</span></span> <span data-ttu-id="6c036-104">受信側では、受信場所のプロパティを設定して、最適化を制御します。</span><span class="sxs-lookup"><span data-stu-id="6c036-104">You control optimization on the receive side by setting a property on the receive location.</span></span> <span data-ttu-id="6c036-105">送信側では、オーケストレーションを使用して、最適化を制御できます。</span><span class="sxs-lookup"><span data-stu-id="6c036-105">On the send side, you can control optimization by using an orchestration.</span></span>  
  
## <a name="receive-optimization"></a><span data-ttu-id="6c036-106">受信側の最適化</span><span class="sxs-lookup"><span data-stu-id="6c036-106">Receive Optimization</span></span>  
 <span data-ttu-id="6c036-107">受信側では、アダプターで 1 つの実行スレッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6c036-107">On the receive side, you can have the adapter use a single execution thread.</span></span> <span data-ttu-id="6c036-108">アダプターが 1 つのスレッドまたは複数のスレッドを使用するかどうかの設定によって異なります、**順次処理**次のように、受信場所のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="6c036-108">Whether the adapter uses a single thread or multiple threads depends on the setting of the **Ordered Processing** property on the receive location, as follows:</span></span>  
  
-   <span data-ttu-id="6c036-109">このプロパティが**True**アダプターが 1 つのスレッドで動作します。</span><span class="sxs-lookup"><span data-stu-id="6c036-109">When the property is **True**, the adapter operates on a single thread.</span></span> <span data-ttu-id="6c036-110">アダプターは一度に 1 つのメッセージに制限されるので、メモリが節約されます。</span><span class="sxs-lookup"><span data-stu-id="6c036-110">This limits the adapter to one message at a time and conserves memory.</span></span> <span data-ttu-id="6c036-111">この実質的に設定されていることを確認**バッチ サイズ**を 1 つ (1) プロパティ シートに割り当てられた値に関係なく。</span><span class="sxs-lookup"><span data-stu-id="6c036-111">Notice that this effectively sets **Batch Size** to one (1), regardless of the value assigned to it in the property sheet.</span></span>  
  
-   <span data-ttu-id="6c036-112">ときに**順次処理**は**False**アダプターが複数のスレッドを実行し、処理できる複数のメッセージ、時に、パフォーマンスを増加させます。</span><span class="sxs-lookup"><span data-stu-id="6c036-112">When **Ordered Processing** is **False**, the adapter runs multiple threads and can process multiple messages at a time, therefore increasing performance.</span></span>  
  
 <span data-ttu-id="6c036-113">設定する必要があります**順次処理**に**True**サーバー リソースの管理を重視する場合、または数またはメッセージのサイズは、使用可能なメモリを使い果たす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6c036-113">You must set **Ordered Processing** to **True** if you put a premium on managing server resources, or if the number or size of messages might exhaust available memory.</span></span>  
  
 <span data-ttu-id="6c036-114">値を減らすことによって、メモリ使用量を制御することも**バッチ サイズ**受信場所でします。</span><span class="sxs-lookup"><span data-stu-id="6c036-114">You can also control memory use by reducing the value of **Batch Size** on the receive location.</span></span> <span data-ttu-id="6c036-115">バッチ サイズは小さいほど、メモリに保持されるメッセージ数が少なくなるため、メモリ使用量が削減されます。</span><span class="sxs-lookup"><span data-stu-id="6c036-115">A smaller batch size keeps fewer messages in memory and therefore uses less memory.</span></span>  
  
 <span data-ttu-id="6c036-116">送信ポートと受信場所を別のコンピューターに配置した場合も、メモリ使用量を削減できます。</span><span class="sxs-lookup"><span data-stu-id="6c036-116">Placing send ports and receive locations on separate computers can also reduce memory use.</span></span>  
  
## <a name="send-optimization"></a><span data-ttu-id="6c036-117">送信側の最適化</span><span class="sxs-lookup"><span data-stu-id="6c036-117">Send Optimization</span></span>  
 <span data-ttu-id="6c036-118">送信側では、サンプル オーケストレーションを使用することで、同等の単一メッセージ処理をアーカイブできます。</span><span class="sxs-lookup"><span data-stu-id="6c036-118">On the send side, you can achieve the equivalent single-message processing by using the sample orchestration.</span></span> <span data-ttu-id="6c036-119">このサンプルでは、1 つのメッセージを送信した後、受信確認を受け取るまで次のメッセージの送信を待機します。</span><span class="sxs-lookup"><span data-stu-id="6c036-119">The sample sends a single message and then waits to send the next message until it receives an acknowledgment.</span></span> <span data-ttu-id="6c036-120">詳細については、次を参照してください。[コードから MSMQ 受信場所の作成と送信ポートを方法](../core/how-to-create-msmq-receive-locations-and-send-ports-from-code.md)です。</span><span class="sxs-lookup"><span data-stu-id="6c036-120">For more information, see [How to Create MSMQ Receive Locations and Send Ports from Code](../core/how-to-create-msmq-receive-locations-and-send-ports-from-code.md).</span></span>  
  
## <a name="remote-transactional-read-operations"></a><span data-ttu-id="6c036-121">リモート トランザクションの読み取り操作</span><span class="sxs-lookup"><span data-stu-id="6c036-121">Remote Transactional Read Operations</span></span>  
 <span data-ttu-id="6c036-122">[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] では、MSMQ アダプターがトランザクション MSMQ キューからのリモート読み取り操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6c036-122">With [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] the MSMQ adapter is capable of making remote read operations from transactional MSMQ queues.</span></span>  <span data-ttu-id="6c036-123">MSMQ 4.0 以降のバージョンがリモート トランザクションの読み取り操作をサポートしているためです。</span><span class="sxs-lookup"><span data-stu-id="6c036-123">This is because MSMQ 4.0 and later versions support remote transactional read operations.</span></span>  <span data-ttu-id="6c036-124">しかし、一般に、トランザクションの読み取り操作には時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="6c036-124">However, transactional read operations are typically slow operations.</span></span> <span data-ttu-id="6c036-125">パフォーマンスを最適化するために、この操作は、他の選択肢がない場合にのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="6c036-125">To optimize performance they should be used only when there is no other option.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c036-126">参照</span><span class="sxs-lookup"><span data-stu-id="6c036-126">See Also</span></span>  
 <span data-ttu-id="6c036-127">[MSMQ 受信場所を構成する方法](../core/how-to-configure-an-msmq-receive-location.md) </span><span class="sxs-lookup"><span data-stu-id="6c036-127">[How to Configure an MSMQ Receive Location](../core/how-to-configure-an-msmq-receive-location.md) </span></span>  
 <span data-ttu-id="6c036-128">[MSMQ 送信ポートを構成する方法](../core/how-to-configure-an-msmq-send-port.md) </span><span class="sxs-lookup"><span data-stu-id="6c036-128">[How to Configure an MSMQ Send Port](../core/how-to-configure-an-msmq-send-port.md) </span></span>  
 [<span data-ttu-id="6c036-129">MSMQ アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="6c036-129">Configuring the MSMQ Adapter</span></span>](../core/configuring-the-msmq-adapter.md)