---
title: "SQL Server 層のスケール アップ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, scaling
- scaling, examples
- SQL Server, scaling
- scaling, scaling up
- scaling, strategies
ms.assetid: 4352c4af-6861-43d9-b433-9ca25668b439
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c654c4a3b1bba166ae8a49918f6ef31827cf041
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="scaling-up-the-sql-server-tier"></a><span data-ttu-id="a1d32-102">SQL Server 層のスケール アップ</span><span class="sxs-lookup"><span data-stu-id="a1d32-102">Scaling Up the SQL Server Tier</span></span>
<span data-ttu-id="a1d32-103">このパターンで、スループットまたは待機時間の要件に応じて、既存の SQL メッセージ ボックス データベースをアップグレードしてスケール アップします。</span><span class="sxs-lookup"><span data-stu-id="a1d32-103">In this pattern, the existing SQL MessageBox database is upgraded to scale according to the requirements in throughput or latency.</span></span>  
  
 <span data-ttu-id="a1d32-104">次の図は、マスターのメッセージ ボックス データベースをクワド (4) プロセッサ サーバーから 8 プロセッサ サーバーにアップグレードするシナリオを示しています。</span><span class="sxs-lookup"><span data-stu-id="a1d32-104">The following figure shows a scenario where the master MessageBox database is upgraded from quad processor server to 8 processor server.</span></span>  
  
 <span data-ttu-id="a1d32-105">![スケール &#45; 最大 MSGBOX](../core/media/scaleupmsgbox2.gif "ScaleUpMsgBox2")</span><span class="sxs-lookup"><span data-stu-id="a1d32-105">![Scale&#45;up MSGBOX](../core/media/scaleupmsgbox2.gif "ScaleUpMsgBox2")</span></span>  
  
## <a name="when-to-scale-up-the-sql-tier"></a><span data-ttu-id="a1d32-106">SQL 層をスケール アップするタイミング</span><span class="sxs-lookup"><span data-stu-id="a1d32-106">When to Scale-up the SQL Tier</span></span>  
  
-   <span data-ttu-id="a1d32-107">マスターのメッセージ ボックス データベースをスケール アップするとき。</span><span class="sxs-lookup"><span data-stu-id="a1d32-107">When you can scale up the master MessageBox database.</span></span>  
  
-   <span data-ttu-id="a1d32-108">マスターのメッセージ ボックス データベースがボトルネックになっている場合。</span><span class="sxs-lookup"><span data-stu-id="a1d32-108">When the master MessageBox database becomes the bottleneck.</span></span> <span data-ttu-id="a1d32-109">次のボトルネックが考えられます。</span><span class="sxs-lookup"><span data-stu-id="a1d32-109">Those bottlenecks can be:</span></span>  
  
    -   <span data-ttu-id="a1d32-110">**CPU**非常に複雑なオーケストレーション シナリオが発生した場合、メッセージ ボックスは大量の CPU リソースを消費します。</span><span class="sxs-lookup"><span data-stu-id="a1d32-110">**CPU** In case of very expensive and complex orchestration scenarios, Message box consumes heavy CPU resources.</span></span> <span data-ttu-id="a1d32-111">CPU を追加して SQL Server をスケール アップすると、シナリオもスケール アップされます。</span><span class="sxs-lookup"><span data-stu-id="a1d32-111">Scaling-up the SQL server by adding more CPUs should scale the scenario.</span></span>  
  
    -   <span data-ttu-id="a1d32-112">**メモリまたは I/O**メモリまたは I/O のボトルネックになることができ、アップグレードすることができます。</span><span class="sxs-lookup"><span data-stu-id="a1d32-112">**Memory or I/O** Memory or I/O can be bottleneck and can be upgraded.</span></span>  
  
-   <span data-ttu-id="a1d32-113">スケール アップがスケール アウトよりもコストがかからず、スケール アップによりボトルネックを解消できる場合。</span><span class="sxs-lookup"><span data-stu-id="a1d32-113">When scaling-up is cheaper than scaling-out and scaling-up can address the bottleneck.</span></span> <span data-ttu-id="a1d32-114">たとえば、マスターのメッセージ ボックス データベースに SQL のロックの競合があった場合、スケール アップではこの問題を解決できません。</span><span class="sxs-lookup"><span data-stu-id="a1d32-114">For example, if the master MessageBox database has an issue with SQL lock contention, this issue cannot be solved by scaling-up.</span></span>  
  
## <a name="when-do-you-decide-sql-cannot-scale-up"></a><span data-ttu-id="a1d32-115">SQL をスケール アップできないと判断するタイミング</span><span class="sxs-lookup"><span data-stu-id="a1d32-115">When do you decide SQL cannot scale-up?</span></span>  
 <span data-ttu-id="a1d32-116">スケール アップは、SQL 層のロックの競合のボトルネックを解消できません。</span><span class="sxs-lookup"><span data-stu-id="a1d32-116">Scale-up cannot address lock contention bottlenecks on the SQL tier.</span></span> <span data-ttu-id="a1d32-117">これらのボトルネックに達すると、スケール アウトがスケール アップよりも優れた手法です。</span><span class="sxs-lookup"><span data-stu-id="a1d32-117">If these kinds of bottlenecks are hit, scale-out is better option than scale-up.</span></span>  
  
## <a name="strategies-and-considerations-for-scaling-up-the-sql-tier"></a><span data-ttu-id="a1d32-118">SQL 層をスケール アップする方法と注意事項</span><span class="sxs-lookup"><span data-stu-id="a1d32-118">Strategies and Considerations for Scaling Up the SQL Tier</span></span>  
  
-   <span data-ttu-id="a1d32-119">マスターのメッセージ ボックス データベースをスケール アップしてから、スケール アウトします。</span><span class="sxs-lookup"><span data-stu-id="a1d32-119">Scale-up the master MessageBox database first and then scale-out.</span></span>  
  
-   <span data-ttu-id="a1d32-120">マスターのメッセージ ボックス データベースは、いずれはボトルネックとなります。</span><span class="sxs-lookup"><span data-stu-id="a1d32-120">The master MessageBox database will eventually be the bottleneck.</span></span> <span data-ttu-id="a1d32-121">そのため、マスターのメッセージ ボックス データベースを高速で大容量にする必要があります (たとえば、Itanium ベースの 64 ビットまたは x64 ベースの、デュアル コア コンピューターなど)。</span><span class="sxs-lookup"><span data-stu-id="a1d32-121">So, the master MessageBox database should be faster and bigger (for example, an Itanium-based 64-bit or x64-based, dual core computer).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1d32-122">参照</span><span class="sxs-lookup"><span data-stu-id="a1d32-122">See Also</span></span>  
 <span data-ttu-id="a1d32-123">[BizTalk Server 層のスケール アウト](../core/scaling-out-the-biztalk-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="a1d32-123">[Scaling Out the BizTalk Server Tier](../core/scaling-out-the-biztalk-server-tier.md) </span></span>  
 <span data-ttu-id="a1d32-124">[BizTalk Server 層のスケール アップ](../core/scaling-up-the-biztalk-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="a1d32-124">[Scaling Up the BizTalk Server Tier](../core/scaling-up-the-biztalk-server-tier.md) </span></span>  
 <span data-ttu-id="a1d32-125">[SQL Server 層のスケール アウト](../core/scaling-out-the-sql-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="a1d32-125">[Scaling Out the SQL Server Tier](../core/scaling-out-the-sql-server-tier.md) </span></span>  
 <span data-ttu-id="a1d32-126">[スケール アウト受信ホスト](../core/scaled-out-receiving-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="a1d32-126">[Scaled-Out Receiving Hosts](../core/scaled-out-receiving-hosts.md) </span></span>  
 <span data-ttu-id="a1d32-127">[スケール アウトされた処理ホスト](../core/scaled-out-processing-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="a1d32-127">[Scaled-Out Processing Hosts](../core/scaled-out-processing-hosts.md) </span></span>  
 <span data-ttu-id="a1d32-128">[スケール アウトされた送信ホスト](../core/scaled-out-sending-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="a1d32-128">[Scaled-Out Sending Hosts](../core/scaled-out-sending-hosts.md) </span></span>  
 <span data-ttu-id="a1d32-129">[Windows Server クラスターを使用して BizTalk Server Hosts2 の高可用性を実現するには](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="a1d32-129">[Using Windows Server Cluster to Provide High Availability for BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span></span>  
 <span data-ttu-id="a1d32-130">[スケール アウト データベース](../core/scaled-out-databases.md) </span><span class="sxs-lookup"><span data-stu-id="a1d32-130">[Scaled-Out Databases](../core/scaled-out-databases.md) </span></span>  
 [<span data-ttu-id="a1d32-131">BizTalk Server データベースをクラスタ リング</span><span class="sxs-lookup"><span data-stu-id="a1d32-131">Clustering the BizTalk Server Databases</span></span>](../core/clustering-the-biztalk-server-databases1.md)