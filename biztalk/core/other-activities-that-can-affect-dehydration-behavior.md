---
title: 退避の動作に影響を与える他のアクティビティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed940448-d3b1-4308-9b38-887904e03bd0
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed8c37dbcca5c15e777cf6a98e50227f8752e324
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979299"
---
# <a name="other-activities-that-can-affect-dehydration-behavior"></a><span data-ttu-id="a8b08-102">退避の動作に影響する可能性のあるその他のアクティビティ</span><span class="sxs-lookup"><span data-stu-id="a8b08-102">Other Activities That Can Affect Dehydration Behavior</span></span>
<span data-ttu-id="a8b08-103">次のアクティビティは、退避および全体のパフォーマンスに直接的または間接的に影響するため、テスト シナリオに組み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8b08-103">The following activities directly or indirectly impact dehydration and overall performance and so should be factored into any testing scenarios.</span></span>  
  
- <span data-ttu-id="a8b08-104">**BizTalk Server 管理コンソール クエリ。**</span><span class="sxs-lookup"><span data-stu-id="a8b08-104">**BizTalk Server Administration Console queries.**</span></span> <span data-ttu-id="a8b08-105">これらのクエリはリソースを消費し、クエリの種類と頻度に応じて全体的なスループットに影響します。</span><span class="sxs-lookup"><span data-stu-id="a8b08-105">These queries consume resources and affect overall throughput depending on the type and frequency of the query.</span></span>  
  
- <span data-ttu-id="a8b08-106">**バックアップ、アーカイブ、およびアクティビティを削除します。**</span><span class="sxs-lookup"><span data-stu-id="a8b08-106">**Backup, archiving, and purging activities.**</span></span> <span data-ttu-id="a8b08-107">これらのアクティビティもリソースを消費するので、テスト シナリオに組み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8b08-107">These activities also consume resources and should be factored into any testing scenarios.</span></span>  
  
- <span data-ttu-id="a8b08-108">**32 ビットおよび 64 ビット ホストが混在します。**</span><span class="sxs-lookup"><span data-stu-id="a8b08-108">**Mixed 32-bit and 64-bit hosts.**</span></span> <span data-ttu-id="a8b08-109">32 ビット ホストと 64 ビット ホストを混在して使用する場合は、次の点を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8b08-109">Here are some things to consider when using mixed 32-bit and 64-bit hosts:</span></span>  
  
  - <span data-ttu-id="a8b08-110">ストレス条件下で仮想メモリと物理メモリの使用量を測定し、その結果を特定のしきい値と比較します。</span><span class="sxs-lookup"><span data-stu-id="a8b08-110">Under stress we measure consumed virtual and physical memory and compare that against certain thresholds.</span></span> <span data-ttu-id="a8b08-111">64 ビット システムでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロセスによってより多くのメモリが使用されるため、同じシステムおよび同じ既定値を使用する 32 ビットとは退避ポリシーが異なります。</span><span class="sxs-lookup"><span data-stu-id="a8b08-111">In 64 bit systems the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] process uses more memory so there will be a difference in dehydration policy from 32-bits using the same system and the same default values.</span></span> <span data-ttu-id="a8b08-112">オーケストレーション、受信、送信、およびメッセージ ボックスのホストを別々にしてください。</span><span class="sxs-lookup"><span data-stu-id="a8b08-112">Be sure to separate orchestration, receive, send and message box hosts.</span></span>  
  
     <span data-ttu-id="a8b08-113">32 ビットの既定のしきい値を 64 ビット システムで使用する場合、オーケストレーション ホストのみが 64 ビット ボックスに配置されていれば、明確な違いはありません。</span><span class="sxs-lookup"><span data-stu-id="a8b08-113">There is not an obvious difference when using the default 32-bit thresholds for 64-bit systems, as long as only the orchestration host is on the 64 bit box.</span></span> <span data-ttu-id="a8b08-114">ただし、ストレス条件下で、さまざまな**MemoryThrottlingCriteria**が多いため、スループットを最大化のシナリオでチューニングする必要がありますが、少なくとも 2 倍または (として十分なメモリがある場合) の存在、する必要があります設定活躍要因。</span><span class="sxs-lookup"><span data-stu-id="a8b08-114">However, under stress the various **MemoryThrottlingCriteria** settings should be at least doubled or tripled (as long as you have enough memory), but the scenario should be tuned for maximizing throughput because there are many factors that come into play.</span></span> <span data-ttu-id="a8b08-115">ストレス条件下で退避のしきい値を調整し、最適なしきい値を見つける必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8b08-115">You should tune the dehydration thresholds under stress to find what is optimal for them.</span></span>  
  
  - <span data-ttu-id="a8b08-116">退避の動作は、各サブスクリプションの配信時刻履歴に応じて異なります。配信時刻履歴はサブスクリプションごとに異なる場合があるため、退避プロパティの値を調整する際にはこの点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="a8b08-116">Dehydration behavior depends on delivery time history of every subscription; the histories could be different for different subscriptions so consider this in tuning your dehydration property values.</span></span>  
  
  - <span data-ttu-id="a8b08-117">あるホストでオーケストレーション ホスト サービスを再利用し、別のホストで再利用しない場合、両ホストの履歴は異なるものになります。</span><span class="sxs-lookup"><span data-stu-id="a8b08-117">When the orchestration host service is recycled on one host, but not on another, the histories will be different.</span></span>  
  
  - <span data-ttu-id="a8b08-118">複数のサーバーで異なるバージョンの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用している場合、両サーバーの退避ポリシーは異なるものになります。</span><span class="sxs-lookup"><span data-stu-id="a8b08-118">When servers are using different versions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], there will be a difference in dehydration policy between the two.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8b08-119">参照</span><span class="sxs-lookup"><span data-stu-id="a8b08-119">See Also</span></span>  
 [<span data-ttu-id="a8b08-120">BTSNTSvc.exe.config ファイル</span><span class="sxs-lookup"><span data-stu-id="a8b08-120">BTSNTSvc.exe.config File</span></span>](../core/btsntsvc-exe-config-file.md)