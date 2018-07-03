---
title: MSMQ アダプターのパフォーマンスの最適化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, performance
- performance, MSMQ adapters
- configuring [MSMQ adapters], performance
ms.assetid: f8537ea8-a96e-4874-bcaf-cd1442a50bd4
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 729aaddba023d854d7ecfeb5644357f2383bc6b1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011587"
---
# <a name="optimizing-performance-of-the-msmq-adapter"></a><span data-ttu-id="455a6-102">MSMQ アダプターのパフォーマンスを最適化します。</span><span class="sxs-lookup"><span data-stu-id="455a6-102">Optimizing Performance of the MSMQ Adapter</span></span>
<span data-ttu-id="455a6-103">MSMQ アダプターの最適化は、送信側と受信側で異なります。</span><span class="sxs-lookup"><span data-stu-id="455a6-103">Optimization of the MSMQ adapter differs between the send and receive sides.</span></span> <span data-ttu-id="455a6-104">受信側では、受信場所のプロパティを設定して、最適化を制御します。</span><span class="sxs-lookup"><span data-stu-id="455a6-104">You control optimization on the receive side by setting a property on the receive location.</span></span> <span data-ttu-id="455a6-105">送信側では、オーケストレーションを使用して、最適化を制御できます。</span><span class="sxs-lookup"><span data-stu-id="455a6-105">On the send side, you can control optimization by using an orchestration.</span></span>  
  
## <a name="receive-optimization"></a><span data-ttu-id="455a6-106">受信側の最適化</span><span class="sxs-lookup"><span data-stu-id="455a6-106">Receive Optimization</span></span>  
 <span data-ttu-id="455a6-107">受信側では、アダプターで 1 つの実行スレッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="455a6-107">On the receive side, you can have the adapter use a single execution thread.</span></span> <span data-ttu-id="455a6-108">設定によって異なります、アダプターが 1 つのスレッドまたは複数のスレッドを使用するかどうか、**順次処理**次のように、受信場所のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="455a6-108">Whether the adapter uses a single thread or multiple threads depends on the setting of the **Ordered Processing** property on the receive location, as follows:</span></span>  
  
- <span data-ttu-id="455a6-109">プロパティが**True**アダプターが 1 つのスレッドで動作します。</span><span class="sxs-lookup"><span data-stu-id="455a6-109">When the property is **True**, the adapter operates on a single thread.</span></span> <span data-ttu-id="455a6-110">アダプターは一度に 1 つのメッセージに制限されるので、メモリが節約されます。</span><span class="sxs-lookup"><span data-stu-id="455a6-110">This limits the adapter to one message at a time and conserves memory.</span></span> <span data-ttu-id="455a6-111">これを効果的に設定する通知**バッチ サイズ**を 1 つ (1) プロパティ シートに割り当てられた値に関係なく。</span><span class="sxs-lookup"><span data-stu-id="455a6-111">Notice that this effectively sets **Batch Size** to one (1), regardless of the value assigned to it in the property sheet.</span></span>  
  
- <span data-ttu-id="455a6-112">ときに**順次処理**は**False**アダプターが複数のスレッドを実行し、メッセージを処理できる複数、時に、そのためパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="455a6-112">When **Ordered Processing** is **False**, the adapter runs multiple threads and can process multiple messages at a time, therefore increasing performance.</span></span>  
  
  <span data-ttu-id="455a6-113">設定する必要があります**順次処理**に**True**サーバー リソースの管理に重点を置いてするか、数やメッセージのサイズが使用可能なメモリを使い果たす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="455a6-113">You must set **Ordered Processing** to **True** if you put a premium on managing server resources, or if the number or size of messages might exhaust available memory.</span></span>  
  
  <span data-ttu-id="455a6-114">値を減らすことでメモリ使用量を制御することもできます。**バッチ サイズ**、受信場所でします。</span><span class="sxs-lookup"><span data-stu-id="455a6-114">You can also control memory use by reducing the value of **Batch Size** on the receive location.</span></span> <span data-ttu-id="455a6-115">バッチ サイズは小さいほど、メモリに保持されるメッセージ数が少なくなるため、メモリ使用量が削減されます。</span><span class="sxs-lookup"><span data-stu-id="455a6-115">A smaller batch size keeps fewer messages in memory and therefore uses less memory.</span></span>  
  
  <span data-ttu-id="455a6-116">送信ポートと受信場所を別のコンピューターに配置した場合も、メモリ使用量を削減できます。</span><span class="sxs-lookup"><span data-stu-id="455a6-116">Placing send ports and receive locations on separate computers can also reduce memory use.</span></span>  
  
## <a name="send-optimization"></a><span data-ttu-id="455a6-117">送信側の最適化</span><span class="sxs-lookup"><span data-stu-id="455a6-117">Send Optimization</span></span>  
 <span data-ttu-id="455a6-118">送信側では、サンプル オーケストレーションを使用することで、同等の単一メッセージ処理をアーカイブできます。</span><span class="sxs-lookup"><span data-stu-id="455a6-118">On the send side, you can achieve the equivalent single-message processing by using the sample orchestration.</span></span> <span data-ttu-id="455a6-119">このサンプルでは、1 つのメッセージを送信した後、受信確認を受け取るまで次のメッセージの送信を待機します。</span><span class="sxs-lookup"><span data-stu-id="455a6-119">The sample sends a single message and then waits to send the next message until it receives an acknowledgment.</span></span> <span data-ttu-id="455a6-120">詳細については、次を参照してください。[コードから MSMQ 受信場所の作成と送信ポートを方法](../core/how-to-create-msmq-receive-locations-and-send-ports-from-code.md)します。</span><span class="sxs-lookup"><span data-stu-id="455a6-120">For more information, see [How to Create MSMQ Receive Locations and Send Ports from Code](../core/how-to-create-msmq-receive-locations-and-send-ports-from-code.md).</span></span>  
  
## <a name="remote-transactional-read-operations"></a><span data-ttu-id="455a6-121">リモート トランザクションの読み取り操作</span><span class="sxs-lookup"><span data-stu-id="455a6-121">Remote Transactional Read Operations</span></span>  
 <span data-ttu-id="455a6-122">BizTalk Server、MSMQ アダプターがトランザクション MSMQ キューからのリモート読み取り操作をすることが可能です。</span><span class="sxs-lookup"><span data-stu-id="455a6-122">With BizTalk Server the MSMQ adapter is capable of making remote read operations from transactional MSMQ queues.</span></span>  <span data-ttu-id="455a6-123">MSMQ 4.0 以降のバージョンがリモート トランザクションの読み取り操作をサポートしているためです。</span><span class="sxs-lookup"><span data-stu-id="455a6-123">This is because MSMQ 4.0 and later versions support remote transactional read operations.</span></span>  <span data-ttu-id="455a6-124">しかし、一般に、トランザクションの読み取り操作には時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="455a6-124">However, transactional read operations are typically slow operations.</span></span> <span data-ttu-id="455a6-125">パフォーマンスを最適化するために、この操作は、他の選択肢がない場合にのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="455a6-125">To optimize performance they should be used only when there is no other option.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="455a6-126">参照</span><span class="sxs-lookup"><span data-stu-id="455a6-126">See Also</span></span>  
 <span data-ttu-id="455a6-127">[MSMQ 受信場所を構成する方法](../core/how-to-configure-an-msmq-receive-location.md) </span><span class="sxs-lookup"><span data-stu-id="455a6-127">[How to Configure an MSMQ Receive Location](../core/how-to-configure-an-msmq-receive-location.md) </span></span>  
 <span data-ttu-id="455a6-128">[MSMQ 送信ポートを構成する方法](../core/how-to-configure-an-msmq-send-port.md) </span><span class="sxs-lookup"><span data-stu-id="455a6-128">[How to Configure an MSMQ Send Port](../core/how-to-configure-an-msmq-send-port.md) </span></span>  
 [<span data-ttu-id="455a6-129">MSMQ アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="455a6-129">Configuring the MSMQ Adapter</span></span>](../core/configuring-the-msmq-adapter.md)