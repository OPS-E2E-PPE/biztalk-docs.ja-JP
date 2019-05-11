---
title: ソリューションの拡張 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance, scaling
- scaling, scaling out
- scaling, performance
- scaling, about scaling
- scaling, scaling up
- scaling
ms.assetid: e2acbaa4-29d3-4c89-ac1f-c0641cfa0442
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 068bea9427ad82621307b0db41714aa2f9db49d8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308688"
---
# <a name="scaling-your-solutions"></a><span data-ttu-id="c24fa-102">ソリューションの拡張</span><span class="sxs-lookup"><span data-stu-id="c24fa-102">Scaling Your Solutions</span></span>
<span data-ttu-id="c24fa-103">BizTalk Server アーキテクチャでは、スケーラビリティに優れたサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="c24fa-103">BizTalk Server architecture provides a very good support for scalability.</span></span> <span data-ttu-id="c24fa-104">選択した拡張パターンは、シナリオ、ハードウェア、およびスループットと待機時間要件の複雑さによって異なります。</span><span class="sxs-lookup"><span data-stu-id="c24fa-104">The scaling patterns that you choose depend on complexity of your scenario, hardware and the throughput/Latency requirements.</span></span> <span data-ttu-id="c24fa-105">小さいトポロジから最初に開始し、このセクションのガイドラインに基づいてスケール アップまたはスケール ダウンを試行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c24fa-105">You should start with a smaller topology initially and try to scale-up or down based on the guidelines in this section.</span></span>  
  
## <a name="scaling-out-and-scaling-up"></a><span data-ttu-id="c24fa-106">スケール アウトとスケール アップ</span><span class="sxs-lookup"><span data-stu-id="c24fa-106">Scaling Out and Scaling Up</span></span>  
 <span data-ttu-id="c24fa-107">BizTalk Server システムのスケールを 2 つの方法はあります。</span><span class="sxs-lookup"><span data-stu-id="c24fa-107">There are two ways to scale your BizTalk Server system:</span></span>  
  
- <span data-ttu-id="c24fa-108">スケール アウトは、追加のコンピューターを追加するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="c24fa-108">Scaling-out is the process of adding additional computers.</span></span> <span data-ttu-id="c24fa-109">たとえば、BizTalk Server の CPU リソースがボトルネックになって、別のサーバーを追加することは倍精度浮動小数点と CPU リソースが 2 倍のスループットを提供することがありますに提供します。</span><span class="sxs-lookup"><span data-stu-id="c24fa-109">For example, if BizTalk Server is bottlenecked by CPU resources, adding another server provides double the CPU resources which may provide double the throughput.</span></span>  
  
- <span data-ttu-id="c24fa-110">スケール アップは、既存のコンピューターをアップグレードするプロセスです。</span><span class="sxs-lookup"><span data-stu-id="c24fa-110">Scaling-up is process of upgrading the existing computer.</span></span> <span data-ttu-id="c24fa-111">たとえば、BizTalk Server コンピューターを 4 プロセッサのコンピューターから 8 プロセッサにアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="c24fa-111">For example, you can upgrade a BizTalk Server computer from a 4 processor machine to an 8 processor.</span></span>  
  
  <span data-ttu-id="c24fa-112">BizTalk Server システムが 2 つの層: BizTalk Server 層とメッセージ ボックス データベースを格納する SQL Server 層。</span><span class="sxs-lookup"><span data-stu-id="c24fa-112">A BizTalk Server system has two tiers: the BizTalk Server tier and the SQL Server tier, which contains your MessageBox databases.</span></span> <span data-ttu-id="c24fa-113">どのようなシナリオでは、スケール アウトまたは各層のスケール アップできます。</span><span class="sxs-lookup"><span data-stu-id="c24fa-113">In any scenario, you can scale out or scale up each tier.</span></span> <span data-ttu-id="c24fa-114">つまり、BizTalk Server と、メッセージ ボックス データベースのスケール アウトしたり、それらの両方をスケール アップできます。</span><span class="sxs-lookup"><span data-stu-id="c24fa-114">That is, you can scale-out BizTalk Server and the MessageBox database, or scale up both of them.</span></span>  
  
  <span data-ttu-id="c24fa-115">ほとんどの場合、BizTalk 層に最初に、ボトルネックになるし、これをスケール アウトしてパフォーマンスを向上させます。ある時点で、システムと使用するハードウェアの複雑さ、によってすることはできず、スケール アウト BizTalk 層もう、SQL Server 層がボトルネックになります。</span><span class="sxs-lookup"><span data-stu-id="c24fa-115">In most cases, the BizTalk tier becomes a bottleneck first, and you start improving performance by scaling it out. But, at some point, depending on complexity of your system and the hardware you use, you can’t scale out the BizTalk tier anymore and the SQL Server tier becomes the bottleneck.</span></span> <span data-ttu-id="c24fa-116">次に、SQL Server の層をスケール アップし、次にメッセージ ボックス データベースを追加してスケール アウト。</span><span class="sxs-lookup"><span data-stu-id="c24fa-116">Then, you scale up the SQL Server tier, and next scale it out by adding more MessageBox databases.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c24fa-117">新しいメッセージ ボックス データベースもここで別のサーバーとは限りません。</span><span class="sxs-lookup"><span data-stu-id="c24fa-117">A new MessageBox database does not necessarily mean another server here.</span></span> <span data-ttu-id="c24fa-118">単一の SQL server では、複数のメッセージ ボックス データベースを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="c24fa-118">A single SQL server can have multiple MessageBox databases.</span></span> <span data-ttu-id="c24fa-119">また、データベースが異なるコンピューター上にある場合、複数のメッセージ ボックス データベースは、DTC コストとネットワーク ホップが発生します。</span><span class="sxs-lookup"><span data-stu-id="c24fa-119">Also, multiple MessageBox databases incur DTC cost and network hop if the databases are on different computers.</span></span>  
  
 <span data-ttu-id="c24fa-120">理論上は、SQL Server 層スケール アウトできます無期限にマスター メッセージ ボックス データベースが飽和状態にならない限り、します。</span><span class="sxs-lookup"><span data-stu-id="c24fa-120">In theory, the SQL Server tier can scale out indefinitely as long as the master MessageBox database is not saturated.</span></span>  
  
 <span data-ttu-id="c24fa-121">このセクションでは、これらの拡張パターンについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="c24fa-121">The topics in this section describe these scaling patterns in more detail.</span></span> <span data-ttu-id="c24fa-122">これらはまた、各パターンをスケーリングする方法およびシステムのスケールを使用できるのパターンでは不要になったを確認する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c24fa-122">They also explain how to scale each pattern and how to determine when you can no longer use that pattern to scale your system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c24fa-123">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c24fa-123">In This Section</span></span>  
  
-   [<span data-ttu-id="c24fa-124">スケーラビリティについて</span><span class="sxs-lookup"><span data-stu-id="c24fa-124">What Is Scalability?</span></span>](../core/what-is-scalability.md)  
  
-   [<span data-ttu-id="c24fa-125">BizTalk Server 層のスケール アウト</span><span class="sxs-lookup"><span data-stu-id="c24fa-125">Scaling Out the BizTalk Server Tier</span></span>](../core/scaling-out-the-biztalk-server-tier.md)  
  
-   [<span data-ttu-id="c24fa-126">BizTalk Server 層のスケール アップ</span><span class="sxs-lookup"><span data-stu-id="c24fa-126">Scaling Up the BizTalk Server Tier</span></span>](../core/scaling-up-the-biztalk-server-tier.md)  
  
-   [<span data-ttu-id="c24fa-127">SQL Server 層のスケール アウト</span><span class="sxs-lookup"><span data-stu-id="c24fa-127">Scaling Out the SQL Server Tier</span></span>](../core/scaling-out-the-sql-server-tier.md)  
  
-   [<span data-ttu-id="c24fa-128">SQL Server 層のスケール アップ</span><span class="sxs-lookup"><span data-stu-id="c24fa-128">Scaling Up the SQL Server Tier</span></span>](../core/scaling-up-the-sql-server-tier.md)  
  
## <a name="see-also"></a><span data-ttu-id="c24fa-129">参照</span><span class="sxs-lookup"><span data-stu-id="c24fa-129">See Also</span></span>  
 <span data-ttu-id="c24fa-130">[受信ホスト スケール アウト](../core/scaled-out-receiving-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="c24fa-130">[Scaled-Out Receiving Hosts](../core/scaled-out-receiving-hosts.md) </span></span>  
 <span data-ttu-id="c24fa-131">[スケール アウトされた処理ホスト](../core/scaled-out-processing-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="c24fa-131">[Scaled-Out Processing Hosts](../core/scaled-out-processing-hosts.md) </span></span>  
 <span data-ttu-id="c24fa-132">[スケール アウトされた送信ホスト](../core/scaled-out-sending-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="c24fa-132">[Scaled-Out Sending Hosts](../core/scaled-out-sending-hosts.md) </span></span>  
 <span data-ttu-id="c24fa-133">[Windows Server クラスターを使用して BizTalk Server Hosts2 の高可用性を実現するには](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="c24fa-133">[Using Windows Server Cluster to Provide High Availability for BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span></span>  
 <span data-ttu-id="c24fa-134">[スケール アウト データベース](../core/scaled-out-databases.md) </span><span class="sxs-lookup"><span data-stu-id="c24fa-134">[Scaled-Out Databases](../core/scaled-out-databases.md) </span></span>  
 [<span data-ttu-id="c24fa-135">BizTalk Server データベースのクラスタリング</span><span class="sxs-lookup"><span data-stu-id="c24fa-135">Clustering the BizTalk Server Databases</span></span>](../core/clustering-the-biztalk-server-databases1.md)