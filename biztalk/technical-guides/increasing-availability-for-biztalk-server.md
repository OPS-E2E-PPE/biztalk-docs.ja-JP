---
title: BizTalk Server の可用性の向上 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 72d9ce5e-d775-4f8e-b1a4-bf3c7c05f571
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d8d3b74fe8c0389093b9525be7ad7adbad5638f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395850"
---
# <a name="increasing-availability-for-biztalk-server"></a><span data-ttu-id="c6a80-102">BizTalk Server の可用性の向上</span><span class="sxs-lookup"><span data-stu-id="c6a80-102">Increasing Availability for BizTalk Server</span></span>
<span data-ttu-id="c6a80-103">このセクションの可用性を向上させる方法を説明します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システム。</span><span class="sxs-lookup"><span data-stu-id="c6a80-103">This section describes ways you can increase the availability of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system.</span></span>  
  
## <a name="strategies-for-increasing-availability"></a><span data-ttu-id="c6a80-104">可用性を高めるための戦略</span><span class="sxs-lookup"><span data-stu-id="c6a80-104">Strategies for Increasing Availability</span></span>  
 <span data-ttu-id="c6a80-105">可用性を高めるための戦略を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="c6a80-105">Strategies for increasing availability include the following:</span></span>  
  
- <span data-ttu-id="c6a80-106">**Windows Server 2003 サーバー クラスターまたは Windows Server 2008 フェールオーバー クラスタ リングを使用して高可用性を提供する**します。</span><span class="sxs-lookup"><span data-stu-id="c6a80-106">**Providing high availability using Windows Server 2003 server clustering or Windows Server 2008 failover clustering**.</span></span> <span data-ttu-id="c6a80-107">サーバーまたはフェールオーバー クラスターは、重要なアプリケーションとリソースがクライアントで使用できる維持するために 1 つのシステムとして連携して、ノードと呼ばれる、独立したコンピューターのシステムのグループです。</span><span class="sxs-lookup"><span data-stu-id="c6a80-107">A server/failover cluster is a group of independent computer systems, known as nodes, working together as a single system to ensure that critical applications and resources remain available to clients.</span></span> <span data-ttu-id="c6a80-108">ノードの 1 つの障害やメンテナンスのダウンタイムの要件の結果として利用できなくなると、すぐに別のノードがサービス (フェールオーバーと呼ばれるプロセス) の提供を開始します。</span><span class="sxs-lookup"><span data-stu-id="c6a80-108">If one of the nodes becomes unavailable as a result of failure or maintenance downtime requirements, another node immediately begins providing service (a process known as failover).</span></span>  
  
  - <span data-ttu-id="c6a80-109">サーバーまたはフェールオーバー クラスターは通常そのハウスの SQL Server を実行するコンピューターの推奨、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。</span><span class="sxs-lookup"><span data-stu-id="c6a80-109">A server/failover cluster is typically recommended for the computers running SQL Server that house the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span>  
  
  - <span data-ttu-id="c6a80-110">サーバー クラスターは、特定の BizTalk アダプターの高可用性を実現する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6a80-110">A server cluster may be required to provide high availability for certain BizTalk adapters.</span></span>  
  
  - <span data-ttu-id="c6a80-111">サーバー クラスターは通常、エンタープライズ シングル サインオン マスター シークレット サーバーをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c6a80-111">A server cluster is typically recommended for the Enterprise Single Sign-On master secret server.</span></span>  
  
- <span data-ttu-id="c6a80-112">**負荷分散のフォームを使用して高可用性を提供する**します。</span><span class="sxs-lookup"><span data-stu-id="c6a80-112">**Providing high availability using a form of load balancing**.</span></span>  
  
  - <span data-ttu-id="c6a80-113">ネットワーク負荷分散 (NLB)。</span><span class="sxs-lookup"><span data-stu-id="c6a80-113">Network load balancing (NLB).</span></span> <span data-ttu-id="c6a80-114">NLB は、ホストが失敗したかオフラインの場合、NLB クラスター ホストを操作への着信ネットワーク トラフィックのリダイレクトにより、高可用性を実現します。</span><span class="sxs-lookup"><span data-stu-id="c6a80-114">NLB delivers high availability by redirecting incoming network traffic to working NLB cluster hosts if a host fails or is offline.</span></span> <span data-ttu-id="c6a80-115">サーバーのクラスターとは異なり、NLB は、特殊なハードウェアを必要ありません。</span><span class="sxs-lookup"><span data-stu-id="c6a80-115">Unlike server clusters, NLB does not require special hardware.</span></span>  
  
  - <span data-ttu-id="c6a80-116">BizTalk ホストの負荷分散します。</span><span class="sxs-lookup"><span data-stu-id="c6a80-116">BizTalk host load balancing.</span></span> <span data-ttu-id="c6a80-117">実行している複数のサーバーを追加することで、BizTalk ホストの BizTalk ホストの負荷分散が提供されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループと、これらのサーバーで実行するインプロセス ホストの複数のインスタンスを構成します。</span><span class="sxs-lookup"><span data-stu-id="c6a80-117">BizTalk host load balancing is provided for BizTalk Hosts by adding multiple servers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group and then configuring multiple instances of an in-process host to run on these servers.</span></span> <span data-ttu-id="c6a80-118">これは、サービスとその可用性とスケーラビリティを向上すると、ホストの複数のインスタンス間でそのホストで構成されているアイテムの実行が分散します。</span><span class="sxs-lookup"><span data-stu-id="c6a80-118">This distributes the execution of services and artifacts configured in that host across multiple instances of the host, which enhances its availability and scalability.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c6a80-119">ホストの負荷分散機能は、インプロセス ホストでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c6a80-119">Host load balancing functionality is available for in-process hosts only.</span></span>  
  
  - <span data-ttu-id="c6a80-120">SQL Server のディスク、SAN を使用して、または複数のメッセージ ボックス データベースを追加することで負荷分散を提供しています。</span><span class="sxs-lookup"><span data-stu-id="c6a80-120">Load balancing is provided for SQL Server disks through the use of a SAN or by adding multiple MessageBox databases.</span></span>  
  
- <span data-ttu-id="c6a80-121">提供するための戦略**可用性を向上させる**します。</span><span class="sxs-lookup"><span data-stu-id="c6a80-121">Strategies for providing **increased availability**.</span></span> <span data-ttu-id="c6a80-122">これらの戦略を可用性を向上することも、管理者が実行時に 1 つまたは複数のアクションを実行することが必要です。</span><span class="sxs-lookup"><span data-stu-id="c6a80-122">These strategies provide increased availability but usually also require that an administrator perform one or more actions at runtime.</span></span> <span data-ttu-id="c6a80-123">そのためこれらの戦略が通常と考えられるの高可用性ではなく可用性の向上を提供します。</span><span class="sxs-lookup"><span data-stu-id="c6a80-123">Therefore these strategies are typically thought of as providing increased availability as opposed to high availability:</span></span>  
  
  - <span data-ttu-id="c6a80-124">可用性を使用して増やす[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ログ配布とディザスター リカバリー。</span><span class="sxs-lookup"><span data-stu-id="c6a80-124">Increasing availability using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping and disaster recovery.</span></span>  
  
  - <span data-ttu-id="c6a80-125">適切な監視とメンテナンス戦略の実装を通じて可用性が向上します。</span><span class="sxs-lookup"><span data-stu-id="c6a80-125">Increasing availability through implementation of the appropriate monitoring and maintenance strategies.</span></span>  
  
## <a name="difference-between-clustering-and-disaster-recovery"></a><span data-ttu-id="c6a80-126">クラスタ リングの違いとディザスター リカバリー</span><span class="sxs-lookup"><span data-stu-id="c6a80-126">Difference Between Clustering and Disaster Recovery</span></span>  
 <span data-ttu-id="c6a80-127">クラスターとディザスター リカバリー可用性を向上させる、それらの主な違いはクラスターは、ディザスター リカバリーよりもはるかに高速の復旧時間を通常提供します。</span><span class="sxs-lookup"><span data-stu-id="c6a80-127">While clusters and disaster recovery both increase availability, a key difference between them is that clusters typically provide much faster recovery time than disaster recovery does.</span></span> <span data-ttu-id="c6a80-128">したがって、サーバーまたはフェールオーバー クラスターでソリューションをビルドまたは負荷分散はよく考えることだけで可用性を実現するのではなく高可用性を提供します。</span><span class="sxs-lookup"><span data-stu-id="c6a80-128">Therefore a solution built on server/failover clusters or load balancing is commonly thought of as providing high availability as opposed to merely providing availability.</span></span>  
  
 <span data-ttu-id="c6a80-129">ディザスター リカバリーは、失敗したシステムの操作を再開することができますが、手動プロセスでは、通常と高可用性の実装よりも多くの復旧時間が必要です。</span><span class="sxs-lookup"><span data-stu-id="c6a80-129">Disaster recovery allows you to resume operation of a failed system but is typically a manual process and requires more recovery time than a high-availability implementation.</span></span> <span data-ttu-id="c6a80-130">そのため、可用性がない高可用性、災害復旧の実装を提供します。</span><span class="sxs-lookup"><span data-stu-id="c6a80-130">Therefore, a disaster recovery implementation provides availability but not high availability.</span></span> <span data-ttu-id="c6a80-131">サーバーまたはフェールオーバー クラスターと、負荷分散による高可用性と、運用環境でのディザスター リカバリーによる可用性の両方を使用する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。</span><span class="sxs-lookup"><span data-stu-id="c6a80-131">You should employ both high availability through server/failover clusters and load balancing, and availability through disaster recovery, in a production [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c6a80-132">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c6a80-132">In This Section</span></span>  
  
-   [<span data-ttu-id="c6a80-133">高可用性の実現</span><span class="sxs-lookup"><span data-stu-id="c6a80-133">Providing High Availability</span></span>](../technical-guides/providing-high-availability.md)  
  
-   [<span data-ttu-id="c6a80-134">ディザスター リカバリー</span><span class="sxs-lookup"><span data-stu-id="c6a80-134">Disaster Recovery</span></span>](../technical-guides/disaster-recovery.md)  
  
## <a name="see-also"></a><span data-ttu-id="c6a80-135">参照</span><span class="sxs-lookup"><span data-stu-id="c6a80-135">See Also</span></span>  
 <span data-ttu-id="c6a80-136">[チェックリスト:フォールト トレランスまたは負荷分散と高可用性を実現します。](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md) </span><span class="sxs-lookup"><span data-stu-id="c6a80-136">[Checklist: Providing High Availability with Fault Tolerance or Load Balancing](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md) </span></span>  
 [<span data-ttu-id="c6a80-137">チェックリスト:ディザスター リカバリーによる可用性の向上</span><span class="sxs-lookup"><span data-stu-id="c6a80-137">Checklist: Increasing Availability with Disaster Recovery</span></span>](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)