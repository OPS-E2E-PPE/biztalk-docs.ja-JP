---
title: SQL Server 層のスケール アップ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, scaling
- scaling, examples
- SQL Server, scaling
- scaling, scaling up
- scaling, strategies
ms.assetid: 4352c4af-6861-43d9-b433-9ca25668b439
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7642b09a9380dd33231fce7be85caee19e31a5fa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308704"
---
# <a name="scaling-up-the-sql-server-tier"></a><span data-ttu-id="465b4-102">SQL Server 層のスケール アップ</span><span class="sxs-lookup"><span data-stu-id="465b4-102">Scaling Up the SQL Server Tier</span></span>
<span data-ttu-id="465b4-103">このパターンでは、既存の SQL メッセージ ボックス データベースのアップグレードにスループットや待機時間の要件に応じてスケールします。</span><span class="sxs-lookup"><span data-stu-id="465b4-103">In this pattern, the existing SQL MessageBox database is upgraded to scale according to the requirements in throughput or latency.</span></span>  
  
 <span data-ttu-id="465b4-104">次の図は、8 プロセッサ サーバーにクアッド プロセッサ サーバーからマスター メッセージ ボックス データベースがアップグレードされた、シナリオを示しています。</span><span class="sxs-lookup"><span data-stu-id="465b4-104">The following figure shows a scenario where the master MessageBox database is upgraded from quad processor server to 8 processor server.</span></span>  
  
 <span data-ttu-id="465b4-105">![スケール&#45;を MSGBOX](../core/media/scaleupmsgbox2.gif "ScaleUpMsgBox2")</span><span class="sxs-lookup"><span data-stu-id="465b4-105">![Scale&#45;up MSGBOX](../core/media/scaleupmsgbox2.gif "ScaleUpMsgBox2")</span></span>  
  
## <a name="when-to-scale-up-the-sql-tier"></a><span data-ttu-id="465b4-106">SQL 層をスケール アップするタイミング</span><span class="sxs-lookup"><span data-stu-id="465b4-106">When to Scale-up the SQL Tier</span></span>  
  
-   <span data-ttu-id="465b4-107">ときに、マスター メッセージ ボックス データベースをスケール アップすることができます。</span><span class="sxs-lookup"><span data-stu-id="465b4-107">When you can scale up the master MessageBox database.</span></span>  
  
-   <span data-ttu-id="465b4-108">マスター メッセージ ボックス データベースがボトルネックになる場合。</span><span class="sxs-lookup"><span data-stu-id="465b4-108">When the master MessageBox database becomes the bottleneck.</span></span> <span data-ttu-id="465b4-109">ボトルネックが考えられます。</span><span class="sxs-lookup"><span data-stu-id="465b4-109">Those bottlenecks can be:</span></span>  
  
    -   <span data-ttu-id="465b4-110">**CPU** 、非常に高価で複雑なオーケストレーション シナリオが発生した場合、メッセージ ボックスは大量の CPU リソースを消費します。</span><span class="sxs-lookup"><span data-stu-id="465b4-110">**CPU** In case of very expensive and complex orchestration scenarios, Message box consumes heavy CPU resources.</span></span> <span data-ttu-id="465b4-111">スケール アップ SQL server 個以上の Cpu を追加することでは、シナリオをスケールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="465b4-111">Scaling-up the SQL server by adding more CPUs should scale the scenario.</span></span>  
  
    -   <span data-ttu-id="465b4-112">**メモリまたは I/O**メモリまたは I/O のボトルネックになることができ、アップグレードすることができます。</span><span class="sxs-lookup"><span data-stu-id="465b4-112">**Memory or I/O** Memory or I/O can be bottleneck and can be upgraded.</span></span>  
  
-   <span data-ttu-id="465b4-113">スケール アップ、スケール アウトよりも低コストとスケール アップは、ボトルネックに対処できます。</span><span class="sxs-lookup"><span data-stu-id="465b4-113">When scaling-up is cheaper than scaling-out and scaling-up can address the bottleneck.</span></span> <span data-ttu-id="465b4-114">たとえば、マスター メッセージ ボックス データベースに SQL ロックの競合の問題がある場合は、スケール アップでこの問題は解決できません。</span><span class="sxs-lookup"><span data-stu-id="465b4-114">For example, if the master MessageBox database has an issue with SQL lock contention, this issue cannot be solved by scaling-up.</span></span>  
  
## <a name="when-do-you-decide-sql-cannot-scale-up"></a><span data-ttu-id="465b4-115">SQL をスケール アップできないと判断するでしょうか。</span><span class="sxs-lookup"><span data-stu-id="465b4-115">When do you decide SQL cannot scale-up?</span></span>  
 <span data-ttu-id="465b4-116">スケール アップは、SQL 層でのロック競合のボトルネックに対処ことはできません。</span><span class="sxs-lookup"><span data-stu-id="465b4-116">Scale-up cannot address lock contention bottlenecks on the SQL tier.</span></span> <span data-ttu-id="465b4-117">この種のボトルネックをヒットすると場合、スケール アウトは、スケール アップよりも優れたオプションです。</span><span class="sxs-lookup"><span data-stu-id="465b4-117">If these kinds of bottlenecks are hit, scale-out is better option than scale-up.</span></span>  
  
## <a name="strategies-and-considerations-for-scaling-up-the-sql-tier"></a><span data-ttu-id="465b4-118">戦略と SQL 層のスケール アップに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="465b4-118">Strategies and Considerations for Scaling Up the SQL Tier</span></span>  
  
-   <span data-ttu-id="465b4-119">マスター メッセージ ボックス データベースを最初にスケール アップし、スケール アウトします。</span><span class="sxs-lookup"><span data-stu-id="465b4-119">Scale-up the master MessageBox database first and then scale-out.</span></span>  
  
-   <span data-ttu-id="465b4-120">マスター メッセージ ボックス データベースがボトルネックとなる最終的になります。</span><span class="sxs-lookup"><span data-stu-id="465b4-120">The master MessageBox database will eventually be the bottleneck.</span></span> <span data-ttu-id="465b4-121">高速で大容量マスター メッセージ ボックス データベースがそのため、する必要があります (たとえば、Itanium ベースの 64 ビットまたは x64 ベース、デュアル コア コンピューターなど)。</span><span class="sxs-lookup"><span data-stu-id="465b4-121">So, the master MessageBox database should be faster and bigger (for example, an Itanium-based 64-bit or x64-based, dual core computer).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="465b4-122">参照</span><span class="sxs-lookup"><span data-stu-id="465b4-122">See Also</span></span>  
 <span data-ttu-id="465b4-123">[BizTalk Server 層のスケール アウト](../core/scaling-out-the-biztalk-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="465b4-123">[Scaling Out the BizTalk Server Tier](../core/scaling-out-the-biztalk-server-tier.md) </span></span>  
 <span data-ttu-id="465b4-124">[BizTalk Server 層のスケール アップ](../core/scaling-up-the-biztalk-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="465b4-124">[Scaling Up the BizTalk Server Tier](../core/scaling-up-the-biztalk-server-tier.md) </span></span>  
 <span data-ttu-id="465b4-125">[SQL Server 層のスケール アウト](../core/scaling-out-the-sql-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="465b4-125">[Scaling Out the SQL Server Tier](../core/scaling-out-the-sql-server-tier.md) </span></span>  
 <span data-ttu-id="465b4-126">[受信ホスト スケール アウト](../core/scaled-out-receiving-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="465b4-126">[Scaled-Out Receiving Hosts](../core/scaled-out-receiving-hosts.md) </span></span>  
 <span data-ttu-id="465b4-127">[スケール アウトされた処理ホスト](../core/scaled-out-processing-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="465b4-127">[Scaled-Out Processing Hosts](../core/scaled-out-processing-hosts.md) </span></span>  
 <span data-ttu-id="465b4-128">[スケール アウトされた送信ホスト](../core/scaled-out-sending-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="465b4-128">[Scaled-Out Sending Hosts](../core/scaled-out-sending-hosts.md) </span></span>  
 <span data-ttu-id="465b4-129">[Windows Server クラスターを使用して BizTalk Server Hosts2 の高可用性を実現するには](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="465b4-129">[Using Windows Server Cluster to Provide High Availability for BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span></span>  
 <span data-ttu-id="465b4-130">[スケール アウト データベース](../core/scaled-out-databases.md) </span><span class="sxs-lookup"><span data-stu-id="465b4-130">[Scaled-Out Databases](../core/scaled-out-databases.md) </span></span>  
 [<span data-ttu-id="465b4-131">BizTalk Server データベースのクラスタリング</span><span class="sxs-lookup"><span data-stu-id="465b4-131">Clustering the BizTalk Server Databases</span></span>](../core/clustering-the-biztalk-server-databases1.md)