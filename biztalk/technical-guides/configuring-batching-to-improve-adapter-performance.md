---
title: "アダプターのパフォーマンスを向上させるためにバッチ処理の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 65589925-af94-45f1-b501-37c21618b2cf
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0dbee8e5b238af0a6dc7f15d54b85d85e0c4b26c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-batching-to-improve-adapter-performance"></a><span data-ttu-id="51bba-102">アダプターのパフォーマンスを向上させるためにバッチ処理の構成</span><span class="sxs-lookup"><span data-stu-id="51bba-102">Configuring Batching to Improve Adapter Performance</span></span>
<span data-ttu-id="51bba-103">アダプターがバッチを処理する方法には、パフォーマンスに大きな影響を及ぼすことができます。</span><span class="sxs-lookup"><span data-stu-id="51bba-103">The way an adapter processes a batch can have a significant effect on performance.</span></span> <span data-ttu-id="51bba-104">トランザクションごとに一定の遅延が発生するため、複数の操作を 1 つのバッチにまとめることによってトランザクションの数を最小限に抑える必要があります。</span><span class="sxs-lookup"><span data-stu-id="51bba-104">Because there is a fixed delay associated with each transaction, you should try to minimize the number of transactions by combining more than one operation into a single batch.</span></span>  
  
 <span data-ttu-id="51bba-105">メッセージを送信している場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]バッチで制限しないメッセージ数のみに基づいてバッチ サイズ。</span><span class="sxs-lookup"><span data-stu-id="51bba-105">If you are submitting messages to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in batches, do not limit the batch size based only on the message count.</span></span> <span data-ttu-id="51bba-106">たとえば、2 つのバッチ サイズは、アダプターの 4 つのメッセージを取得する場合のサイズを 4 KB、8 KB、1 MB、および 5 MB それぞれ、られる最初のバッチ サイズの 12 KB になり、2 番目のバッチになります 6 MB のサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="51bba-106">For example, if the batch size is two and the adapter gets four messages of size 4 KB, 8 KB, 1 MB, and 5 MB respectively, the first batch will be of size 12 KB, and the second batch will be of size 6 MB.</span></span> <span data-ttu-id="51bba-107">BizTalk メッセージング エンジンは各バッチのすべてのメッセージを順に処理するため、この例の 2 つ目のバッチの処理速度は 1 つ目のバッチに比べて大幅に低下します。</span><span class="sxs-lookup"><span data-stu-id="51bba-107">Because the BizTalk Messaging Engine processes all messages in a single batch sequentially, the second batch in this example will be processed much more slowly than the first batch.</span></span> <span data-ttu-id="51bba-108">このプロパティの効果は、スループットの低下がします。</span><span class="sxs-lookup"><span data-stu-id="51bba-108">The effect of this is reduced throughput.</span></span>  
  
 <span data-ttu-id="51bba-109">この問題を処理するためには、メッセージの数と合計 (バイト単位では、バッチ サイズ)、バッチ内のバイト数の両方に基づいて、バッチをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="51bba-109">To handle this problem, we recommend that you batch based on both the message count and the total number of bytes in the batch (that is, batch size in bytes).</span></span> <span data-ttu-id="51bba-110">合計バイト数の最適な数はありません。</span><span class="sxs-lookup"><span data-stu-id="51bba-110">There is no optimal number for total bytes.</span></span> <span data-ttu-id="51bba-111">ただし、通常の処理のシナリオでバッチ サイズが 1 MB を超える場合は開始する不適切な同時実行性とスループットが発生します。</span><span class="sxs-lookup"><span data-stu-id="51bba-111">However, in a normal processing scenario, if the batch size exceeds 1 MB, you will start encountering poor concurrency and throughput.</span></span>  
  
 <span data-ttu-id="51bba-112">アダプターは、通常、実稼働環境でさまざまなサイズのメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="51bba-112">Adapters generally process messages of varying size in the production environment.</span></span> <span data-ttu-id="51bba-113">受信メッセージのサイズは大きく異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="51bba-113">The sizes of incoming messages are likely to vary significantly.</span></span> <span data-ttu-id="51bba-114">その結果、バッチを構築するのに常にメッセージの数と合計バイト数を使用します。</span><span class="sxs-lookup"><span data-stu-id="51bba-114">As a result, always use message count and total bytes to build the batch.</span></span>