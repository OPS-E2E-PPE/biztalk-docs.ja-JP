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
ms.openlocfilehash: bb3fcbb2799cba8e808c2bd2da66c09706fe7a33
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393451"
---
# <a name="other-activities-that-can-affect-dehydration-behavior"></a><span data-ttu-id="23536-102">退避の動作に影響を与える他のアクティビティ</span><span class="sxs-lookup"><span data-stu-id="23536-102">Other Activities That Can Affect Dehydration Behavior</span></span>
<span data-ttu-id="23536-103">次のアクティビティに直接または間接的に影響退避および全体のパフォーマンスとこれは、テスト シナリオに組み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="23536-103">The following activities directly or indirectly impact dehydration and overall performance and so should be factored into any testing scenarios.</span></span>  
  
- <span data-ttu-id="23536-104">**BizTalk Server 管理コンソール クエリ。**</span><span class="sxs-lookup"><span data-stu-id="23536-104">**BizTalk Server Administration Console queries.**</span></span> <span data-ttu-id="23536-105">これらのクエリでは、リソースを消費し、種類と、クエリの頻度に応じて全体的なスループットに影響します。</span><span class="sxs-lookup"><span data-stu-id="23536-105">These queries consume resources and affect overall throughput depending on the type and frequency of the query.</span></span>  
  
- <span data-ttu-id="23536-106">**バックアップ、アーカイブ、およびアクティビティを削除します。**</span><span class="sxs-lookup"><span data-stu-id="23536-106">**Backup, archiving, and purging activities.**</span></span> <span data-ttu-id="23536-107">これらのアクティビティもリソースを消費し、テスト シナリオに組み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="23536-107">These activities also consume resources and should be factored into any testing scenarios.</span></span>  
  
- <span data-ttu-id="23536-108">**32 ビットおよび 64 ビット ホストが混在します。**</span><span class="sxs-lookup"><span data-stu-id="23536-108">**Mixed 32-bit and 64-bit hosts.**</span></span> <span data-ttu-id="23536-109">32 ビットおよび 64 ビット ホストの混在を使用する場合の考慮事項を次に示します。</span><span class="sxs-lookup"><span data-stu-id="23536-109">Here are some things to consider when using mixed 32-bit and 64-bit hosts:</span></span>  
  
  - <span data-ttu-id="23536-110">ストレス条件下では仮想および物理メモリの消費量を測定し、特定のしきい値と比較することです。</span><span class="sxs-lookup"><span data-stu-id="23536-110">Under stress we measure consumed virtual and physical memory and compare that against certain thresholds.</span></span> <span data-ttu-id="23536-111">64 ビット システムで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロセスでは、同じシステムと同じ既定値を使用して 32 ビットからの退避ポリシーに違いがあるためにより多くのメモリを使用します。</span><span class="sxs-lookup"><span data-stu-id="23536-111">In 64 bit systems the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] process uses more memory so there will be a difference in dehydration policy from 32-bits using the same system and the same default values.</span></span> <span data-ttu-id="23536-112">オーケストレーションを個別の受信、送信、およびメッセージ ボックスのホストを必ず。</span><span class="sxs-lookup"><span data-stu-id="23536-112">Be sure to separate orchestration, receive, send and message box hosts.</span></span>  
  
     <span data-ttu-id="23536-113">違いはありません、明白な 64 ビット システムでは、32 ビットの既定のしきい値を使用する場合、オーケストレーション ホストのみが、64 ビット ボックスにある限りです。</span><span class="sxs-lookup"><span data-stu-id="23536-113">There is not an obvious difference when using the default 32-bit thresholds for 64-bit systems, as long as only the orchestration host is on the 64 bit box.</span></span> <span data-ttu-id="23536-114">ただし、ストレス条件下で、さまざまな**MemoryThrottlingCriteria**が多いため、スループットを最大化のシナリオでチューニングする必要がありますが、少なくとも 2 倍または (として十分なメモリがある場合) の存在、する必要があります設定活躍要因。</span><span class="sxs-lookup"><span data-stu-id="23536-114">However, under stress the various **MemoryThrottlingCriteria** settings should be at least doubled or tripled (as long as you have enough memory), but the scenario should be tuned for maximizing throughput because there are many factors that come into play.</span></span> <span data-ttu-id="23536-115">ものを検索し、最適のストレス条件下で退避のしきい値を調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23536-115">You should tune the dehydration thresholds under stress to find what is optimal for them.</span></span>  
  
  - <span data-ttu-id="23536-116">退避の動作は、すべてのサブスクリプションの配信時刻履歴によって異なります。異なるサブスクリプションように検討してくださいこの退避プロパティの値をチューニングの履歴は異なるできます。</span><span class="sxs-lookup"><span data-stu-id="23536-116">Dehydration behavior depends on delivery time history of every subscription; the histories could be different for different subscriptions so consider this in tuning your dehydration property values.</span></span>  
  
  - <span data-ttu-id="23536-117">オーケストレーション ホスト サービスが 1 つのホストでは、再利用されるが、別の履歴は異なるものになります。</span><span class="sxs-lookup"><span data-stu-id="23536-117">When the orchestration host service is recycled on one host, but not on another, the histories will be different.</span></span>  
  
  - <span data-ttu-id="23536-118">サーバーに異なるバージョンを使用しているときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、退避ポリシーで、2 つの間の違いがあります。</span><span class="sxs-lookup"><span data-stu-id="23536-118">When servers are using different versions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], there will be a difference in dehydration policy between the two.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23536-119">参照</span><span class="sxs-lookup"><span data-stu-id="23536-119">See Also</span></span>  
 [<span data-ttu-id="23536-120">BTSNTSvc.exe.config ファイル</span><span class="sxs-lookup"><span data-stu-id="23536-120">BTSNTSvc.exe.config File</span></span>](../core/btsntsvc-exe-config-file.md)