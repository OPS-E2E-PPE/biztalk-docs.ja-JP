---
title: アダプターのパフォーマンスを向上させるためにバッチ処理の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65589925-af94-45f1-b501-37c21618b2cf
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5276c6a979783a5ab6a5e4d73573eec95cabd25
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244056"
---
# <a name="configuring-batching-to-improve-adapter-performance"></a><span data-ttu-id="f0746-102">アダプターのパフォーマンスを向上させるためにバッチ処理の構成</span><span class="sxs-lookup"><span data-stu-id="f0746-102">Configuring Batching to Improve Adapter Performance</span></span>
<span data-ttu-id="f0746-103">アダプターがバッチを処理する方法には、パフォーマンスに大きな影響を及ぼすことができます。</span><span class="sxs-lookup"><span data-stu-id="f0746-103">The way an adapter processes a batch can have a significant effect on performance.</span></span> <span data-ttu-id="f0746-104">各トランザクションに関連付けられている一定の遅延があるため、1 つのバッチには、複数の操作を組み合わせることによってトランザクションの数を最小限にしようとする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0746-104">Because there is a fixed delay associated with each transaction, you should try to minimize the number of transactions by combining more than one operation into a single batch.</span></span>  
  
 <span data-ttu-id="f0746-105">メッセージを送信する場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]バッチで制限しないメッセージ数のみに基づいてバッチ サイズ。</span><span class="sxs-lookup"><span data-stu-id="f0746-105">If you are submitting messages to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in batches, do not limit the batch size based only on the message count.</span></span> <span data-ttu-id="f0746-106">など、2 つのバッチ サイズは、アダプターの 4 つのメッセージを取得する場合のサイズを 4 KB、8 KB 1 MB 5 MB それぞれられる最初のバッチ サイズの 12 KB になり、2 つ目のバッチになります 6 MB のサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="f0746-106">For example, if the batch size is two and the adapter gets four messages of size 4 KB, 8 KB, 1 MB, and 5 MB respectively, the first batch will be of size 12 KB, and the second batch will be of size 6 MB.</span></span> <span data-ttu-id="f0746-107">BizTalk メッセージング エンジンが単一のバッチ内のすべてのメッセージを順番に処理するため、この例では、2 番目のバッチは最初のバッチに比べて大幅に低下処理されます。</span><span class="sxs-lookup"><span data-stu-id="f0746-107">Because the BizTalk Messaging Engine processes all messages in a single batch sequentially, the second batch in this example will be processed much more slowly than the first batch.</span></span> <span data-ttu-id="f0746-108">このプロパティの効果は、スループットの低下します。</span><span class="sxs-lookup"><span data-stu-id="f0746-108">The effect of this is reduced throughput.</span></span>  
  
 <span data-ttu-id="f0746-109">この問題を処理するためには、メッセージの数とバッチ (バッチ サイズ (バイト単位) は、) のバイト数の合計数の両方に基づいて、バッチをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f0746-109">To handle this problem, we recommend that you batch based on both the message count and the total number of bytes in the batch (that is, batch size in bytes).</span></span> <span data-ttu-id="f0746-110">最適な数の合計バイト数はありません。</span><span class="sxs-lookup"><span data-stu-id="f0746-110">There is no optimal number for total bytes.</span></span> <span data-ttu-id="f0746-111">ただし、通常の処理のシナリオでは、バッチ サイズが 1 MB を超える場合は、開始が低い同時実行性とスループットが発生します。</span><span class="sxs-lookup"><span data-stu-id="f0746-111">However, in a normal processing scenario, if the batch size exceeds 1 MB, you will start encountering poor concurrency and throughput.</span></span>  
  
 <span data-ttu-id="f0746-112">アダプターは、一般に運用環境でさまざまなサイズのメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="f0746-112">Adapters generally process messages of varying size in the production environment.</span></span> <span data-ttu-id="f0746-113">受信メッセージのサイズが大きく異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f0746-113">The sizes of incoming messages are likely to vary significantly.</span></span> <span data-ttu-id="f0746-114">結果として、バッチの作成に常にメッセージの数と合計バイト数を使用します。</span><span class="sxs-lookup"><span data-stu-id="f0746-114">As a result, always use message count and total bytes to build the batch.</span></span>