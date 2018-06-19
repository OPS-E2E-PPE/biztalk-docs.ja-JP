---
title: ソリューションの拡張 |Microsoft ドキュメント
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
ms.openlocfilehash: 5417e303ea8486ef5bdee8e57c66d4783fb197ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269978"
---
# <a name="scaling-your-solutions"></a><span data-ttu-id="0ca1c-102">ソリューションの拡張</span><span class="sxs-lookup"><span data-stu-id="0ca1c-102">Scaling Your Solutions</span></span>
<span data-ttu-id="0ca1c-103">BizTalk Server アーキテクチャは、スケーラビリティに優れたサポートを提供しています。</span><span class="sxs-lookup"><span data-stu-id="0ca1c-103">BizTalk Server architecture provides a very good support for scalability.</span></span> <span data-ttu-id="0ca1c-104">選択する拡張パターンは、シナリオ、ハードウェア、スループット/待機時間の要件の複雑さによって異なります。</span><span class="sxs-lookup"><span data-stu-id="0ca1c-104">The scaling patterns that you choose depend on complexity of your scenario, hardware and the throughput/Latency requirements.</span></span> <span data-ttu-id="0ca1c-105">最初は小さいトポロジから始めて、このセクションのガイドラインに従ってスケールアップまたはスケールダウンを試みてください。</span><span class="sxs-lookup"><span data-stu-id="0ca1c-105">You should start with a smaller topology initially and try to scale-up or down based on the guidelines in this section.</span></span>  
  
## <a name="scaling-out-and-scaling-up"></a><span data-ttu-id="0ca1c-106">スケール アウトとスケール アップ</span><span class="sxs-lookup"><span data-stu-id="0ca1c-106">Scaling Out and Scaling Up</span></span>  
 <span data-ttu-id="0ca1c-107">BizTalk Server システムを拡張する方法は 2 とおりあります。</span><span class="sxs-lookup"><span data-stu-id="0ca1c-107">There are two ways to scale your BizTalk Server system:</span></span>  
  
-   <span data-ttu-id="0ca1c-108">スケールアウトは、別のコンピューターを追加するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="0ca1c-108">Scaling-out is the process of adding additional computers.</span></span> <span data-ttu-id="0ca1c-109">たとえば、CPU リソースが原因で BizTalk Server にボトルネックが生じた場合、サーバーをもう 1 台追加すると CPU リソースが 2 倍になるので、2 倍のスループットを得られる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0ca1c-109">For example, if BizTalk Server is bottlenecked by CPU resources, adding another server provides double the CPU resources which may provide double the throughput.</span></span>  
  
-   <span data-ttu-id="0ca1c-110">スケールアップは、既存のコンピューターをアップグレードするプロセスです。</span><span class="sxs-lookup"><span data-stu-id="0ca1c-110">Scaling-up is process of upgrading the existing computer.</span></span> <span data-ttu-id="0ca1c-111">たとえば、BizTalk Server コンピューターを 4 プロセッサから 8 プロセッサにアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="0ca1c-111">For example, you can upgrade a BizTalk Server computer from a 4 processor machine to an 8 processor.</span></span>  
  
 <span data-ttu-id="0ca1c-112">BizTalk Server システムが 2 つの層: BizTalk Server 層と、SQL Server 層、メッセージ ボックス データベースを格納します。</span><span class="sxs-lookup"><span data-stu-id="0ca1c-112">A BizTalk Server system has two tiers: the BizTalk Server tier and the SQL Server tier, which contains your MessageBox databases.</span></span> <span data-ttu-id="0ca1c-113">いずれのシナリオでも、各層をスケール アウトまたはスケール アップすることができます。</span><span class="sxs-lookup"><span data-stu-id="0ca1c-113">In any scenario, you can scale out or scale up each tier.</span></span> <span data-ttu-id="0ca1c-114">つまり BizTalk Server とメッセージ ボックス データベースをスケール アウトしたり、両方をスケール アップすることができます。</span><span class="sxs-lookup"><span data-stu-id="0ca1c-114">That is, you can scale-out BizTalk Server and the MessageBox database, or scale up both of them.</span></span>  
  
 <span data-ttu-id="0ca1c-115">BizTalk 層が最初にボトルネックになり、これをスケール アウトしてパフォーマンスを向上させる場合がほとんどです。ただし、使用するシステムとハードウェアの複雑さによっては、BizTalk 層をそれ以上スケール アウトできなくなり、SQL Server 層がボトルネックになります。</span><span class="sxs-lookup"><span data-stu-id="0ca1c-115">In most cases, the BizTalk tier becomes a bottleneck first, and you start improving performance by scaling it out. But, at some point, depending on complexity of your system and the hardware you use, you can’t scale out the BizTalk tier anymore and the SQL Server tier becomes the bottleneck.</span></span> <span data-ttu-id="0ca1c-116">その場合は SQL Server 層をスケール アップし、次にメッセージ ボックス データベースを追加してスケール アウトします。</span><span class="sxs-lookup"><span data-stu-id="0ca1c-116">Then, you scale up the SQL Server tier, and next scale it out by adding more MessageBox databases.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ca1c-117">新しいメッセージ ボックス データベースの追加は、必ずしもサーバーの追加を意味しているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="0ca1c-117">A new MessageBox database does not necessarily mean another server here.</span></span> <span data-ttu-id="0ca1c-118">1 台の SQL Server に複数のメッセージ ボックス データベースを置くことができるためです。</span><span class="sxs-lookup"><span data-stu-id="0ca1c-118">A single SQL server can have multiple MessageBox databases.</span></span> <span data-ttu-id="0ca1c-119">また、データベースが複数のコンピューター上に存在すると、複数のメッセージ ボックス データベースにより DTC コストとネットワーク ホップが生じます。</span><span class="sxs-lookup"><span data-stu-id="0ca1c-119">Also, multiple MessageBox databases incur DTC cost and network hop if the databases are on different computers.</span></span>  
  
 <span data-ttu-id="0ca1c-120">マスター メッセージ ボックス データベースが飽和状態にならない限り、理論上は、SQL Server 層は無限にスケール アウトできます。</span><span class="sxs-lookup"><span data-stu-id="0ca1c-120">In theory, the SQL Server tier can scale out indefinitely as long as the master MessageBox database is not saturated.</span></span>  
  
 <span data-ttu-id="0ca1c-121">このセクションの各トピックでは、これらの拡張パターンについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="0ca1c-121">The topics in this section describe these scaling patterns in more detail.</span></span> <span data-ttu-id="0ca1c-122">また、各パターンを拡張する方法とそのパターンでシステムを拡張できなくなった場合を判断する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="0ca1c-122">They also explain how to scale each pattern and how to determine when you can no longer use that pattern to scale your system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0ca1c-123">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="0ca1c-123">In This Section</span></span>  
  
-   [<span data-ttu-id="0ca1c-124">スケーラビリティとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="0ca1c-124">What Is Scalability?</span></span>](../core/what-is-scalability.md)  
  
-   [<span data-ttu-id="0ca1c-125">BizTalk Server 層のスケール アウト</span><span class="sxs-lookup"><span data-stu-id="0ca1c-125">Scaling Out the BizTalk Server Tier</span></span>](../core/scaling-out-the-biztalk-server-tier.md)  
  
-   [<span data-ttu-id="0ca1c-126">BizTalk Server 層のスケール アップ</span><span class="sxs-lookup"><span data-stu-id="0ca1c-126">Scaling Up the BizTalk Server Tier</span></span>](../core/scaling-up-the-biztalk-server-tier.md)  
  
-   [<span data-ttu-id="0ca1c-127">SQL Server 層のスケール アウト</span><span class="sxs-lookup"><span data-stu-id="0ca1c-127">Scaling Out the SQL Server Tier</span></span>](../core/scaling-out-the-sql-server-tier.md)  
  
-   [<span data-ttu-id="0ca1c-128">SQL Server 層のスケール アップ</span><span class="sxs-lookup"><span data-stu-id="0ca1c-128">Scaling Up the SQL Server Tier</span></span>](../core/scaling-up-the-sql-server-tier.md)  
  
## <a name="see-also"></a><span data-ttu-id="0ca1c-129">参照</span><span class="sxs-lookup"><span data-stu-id="0ca1c-129">See Also</span></span>  
 <span data-ttu-id="0ca1c-130">[スケール アウト受信ホスト](../core/scaled-out-receiving-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="0ca1c-130">[Scaled-Out Receiving Hosts](../core/scaled-out-receiving-hosts.md) </span></span>  
 <span data-ttu-id="0ca1c-131">[スケール アウトされた処理ホスト](../core/scaled-out-processing-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="0ca1c-131">[Scaled-Out Processing Hosts](../core/scaled-out-processing-hosts.md) </span></span>  
 <span data-ttu-id="0ca1c-132">[スケール アウトされた送信ホスト](../core/scaled-out-sending-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="0ca1c-132">[Scaled-Out Sending Hosts](../core/scaled-out-sending-hosts.md) </span></span>  
 <span data-ttu-id="0ca1c-133">[Windows Server クラスターを使用して BizTalk Server Hosts2 の高可用性を実現するには](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="0ca1c-133">[Using Windows Server Cluster to Provide High Availability for BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span></span>  
 <span data-ttu-id="0ca1c-134">[スケール アウト データベース](../core/scaled-out-databases.md) </span><span class="sxs-lookup"><span data-stu-id="0ca1c-134">[Scaled-Out Databases](../core/scaled-out-databases.md) </span></span>  
 [<span data-ttu-id="0ca1c-135">BizTalk Server データベースをクラスタ リング</span><span class="sxs-lookup"><span data-stu-id="0ca1c-135">Clustering the BizTalk Server Databases</span></span>](../core/clustering-the-biztalk-server-databases1.md)