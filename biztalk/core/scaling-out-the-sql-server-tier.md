---
title: SQL Server 層のスケール アウト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- scaling, MessageBox database
- scaling, scaling out
- SQL Server, scaling
- MessageBox database, scaling
- scaling, strategies
ms.assetid: d5b2ebba-401e-4fde-8818-407fa626043a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c49a6bd83b6647170574106dd06825e2e5aba75
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65309029"
---
# <a name="scaling-out-the-sql-server-tier"></a><span data-ttu-id="c6128-102">SQL Server 層のスケール アウト</span><span class="sxs-lookup"><span data-stu-id="c6128-102">Scaling Out the SQL Server Tier</span></span>
<span data-ttu-id="c6128-103">、BizTalk グループごとに 1 つのマスター メッセージ ボックス データベースを追加します。</span><span class="sxs-lookup"><span data-stu-id="c6128-103">For each BizTalk group, you add one Master MessageBox database.</span></span> <span data-ttu-id="c6128-104">追加するすべての後続のメッセージ ボックス データベースは、セカンダリ メッセージ ボックスと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="c6128-104">All the subsequent MessageBox databases that you add are called secondary MessageBoxes.</span></span> <span data-ttu-id="c6128-105">マスター メッセージ ボックスは、すべてのサブスクリプションとメッセージのルーティングを処理します。</span><span class="sxs-lookup"><span data-stu-id="c6128-105">The Master MessageBox handles all subscriptions and message routing.</span></span> <span data-ttu-id="c6128-106">メッセージを公開することもできます。</span><span class="sxs-lookup"><span data-stu-id="c6128-106">It can also publish messages.</span></span> <span data-ttu-id="c6128-107">セカンダリ メッセージ ボックス データベースにのみ、そのためには具体的には構成されている場合、メッセージが発行されます。</span><span class="sxs-lookup"><span data-stu-id="c6128-107">Secondary MessageBox databases will only publish messages when specifically configured to do so.</span></span>  
  
## <a name="how-to-add-a-secondary-messagebox-database"></a><span data-ttu-id="c6128-108">セカンダリ メッセージ ボックス データベースを追加する方法</span><span class="sxs-lookup"><span data-stu-id="c6128-108">How to Add a Secondary MessageBox Database</span></span>  
 <span data-ttu-id="c6128-109">セカンダリ メッセージ ボックス データベースを追加する 2 つの方法はあります。</span><span class="sxs-lookup"><span data-stu-id="c6128-109">There are two ways to add secondary MessageBox databases:</span></span>  
  
- <span data-ttu-id="c6128-110">同じ物理サーバー上には、セカンダリ メッセージ ボックス データベースを追加します。</span><span class="sxs-lookup"><span data-stu-id="c6128-110">Add the secondary MessageBox database on the same physical server.</span></span>  
  
   <span data-ttu-id="c6128-111">既存のメッセージ ボックス物理サーバーに十分な CPU と I/O リソースがあるし、ロックの競合によってボトルネックがのみの場合は、これを実行します。</span><span class="sxs-lookup"><span data-stu-id="c6128-111">Do this if the existing MessageBox physical server has enough CPU and I/O resources and is only bottlenecked by lock contention.</span></span> <span data-ttu-id="c6128-112">別の IO ドライブ上には、セカンダリ メッセージ ボックス データベースを作成します。</span><span class="sxs-lookup"><span data-stu-id="c6128-112">Create the secondary MessageBox database on separate IO drives.</span></span>  
  
   <span data-ttu-id="c6128-113">利点:</span><span class="sxs-lookup"><span data-stu-id="c6128-113">Advantages:</span></span>  
  
  -   <span data-ttu-id="c6128-114">余分な CPU ヘッドルームを他のメッセージ ボックスで利用できます。</span><span class="sxs-lookup"><span data-stu-id="c6128-114">The extra CPU headroom can be utilized by another message-box</span></span>  
  
  -   <span data-ttu-id="c6128-115">以下の SQL server ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="c6128-115">Fewer SQL server licenses are required</span></span>  
  
  -   <span data-ttu-id="c6128-116">ネットワーク ホップがなくなります。</span><span class="sxs-lookup"><span data-stu-id="c6128-116">Network hop is eliminated</span></span>  
  
- <span data-ttu-id="c6128-117">セカンダリ メッセージ ボックス データベースを別の物理サーバーの追加します。</span><span class="sxs-lookup"><span data-stu-id="c6128-117">Add the secondary MessageBox database on a different physical server</span></span>  
  
   <span data-ttu-id="c6128-118">ここでは、余分なメッセージ ボックス データベースとして固有の IO で専用の物理サーバーを使用します。</span><span class="sxs-lookup"><span data-stu-id="c6128-118">In this case, use a dedicated physical server with its own IO as the extra MessageBox database.</span></span>  
  
  <span data-ttu-id="c6128-119">次の図は、シナリオ、SQL 層はスケール アウトされた 1 つのメッセージ ボックス データベースから 3 つのメッセージ ボックス データベースにします。</span><span class="sxs-lookup"><span data-stu-id="c6128-119">The following figure shows a scenario where SQL tier is scaled-out from one MessageBox database to three MessageBoxes databases.</span></span>  
  
  <span data-ttu-id="c6128-120">![MSGBOX のスケール アウト](../core/media/scaleoutmsgbox.gif "ScaleOutMSGBOX")</span><span class="sxs-lookup"><span data-stu-id="c6128-120">![Scale out MSGBOX](../core/media/scaleoutmsgbox.gif "ScaleOutMSGBOX")</span></span>  
  
## <a name="when-to-scale-out-the-messagebox-database"></a><span data-ttu-id="c6128-121">メッセージ ボックス データベースをスケール アウトするタイミング</span><span class="sxs-lookup"><span data-stu-id="c6128-121">When to Scale-out the MessageBox database</span></span>  
  
-   <span data-ttu-id="c6128-122">メッセージ ボックス データベースがボトルネックになります。</span><span class="sxs-lookup"><span data-stu-id="c6128-122">The MessageBox database becomes the bottleneck.</span></span> <span data-ttu-id="c6128-123">ボトルネックが考えられます。</span><span class="sxs-lookup"><span data-stu-id="c6128-123">Those bottlenecks can be:</span></span>  
  
    -   <span data-ttu-id="c6128-124">**CPU** 、非常に高価で複雑なオーケストレーション シナリオが発生した場合、メッセージ ボックス データベースが大量の CPU リソースを消費します。</span><span class="sxs-lookup"><span data-stu-id="c6128-124">**CPU** In case of very expensive and complex orchestration scenarios, the MessageBox database consumes heavy CPU resources.</span></span> <span data-ttu-id="c6128-125">別の発行を追加するメッセージ ボックス データベース スループットが向上します。</span><span class="sxs-lookup"><span data-stu-id="c6128-125">Adding another publishing the MessageBox database should help increase the throughput.</span></span>  
  
    -   <span data-ttu-id="c6128-126">**ロックの競合**複雑なシナリオでは、複数のホスト インスタンスやオーケストレーションがメッセージ ボックス データベースでロックの競合を作成する傾向があります。</span><span class="sxs-lookup"><span data-stu-id="c6128-126">**Lock Contention** Complex scenarios with multiple host instances or orchestrations tend to create lock contention on the MessageBox database.</span></span> <span data-ttu-id="c6128-127">ここでも、別の公開メッセージ ボックス データベースを追加するには、スループットを向上させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6128-127">Again, adding another publishing MessageBox database should help increase the throughput.</span></span>  
  
-   <span data-ttu-id="c6128-128">ボトルネックを解消するには、スケール アップします。</span><span class="sxs-lookup"><span data-stu-id="c6128-128">Scaling up doesn’t address the bottleneck.</span></span> <span data-ttu-id="c6128-129">たとえば、マスター メッセージ ボックス データベースがバインドされているロックの競合の場合は、スケール アウトは、唯一のオプションです。</span><span class="sxs-lookup"><span data-stu-id="c6128-129">For example, if the Master MessageBox database is lock contention bound, scaling-out is the only option.</span></span>  
  
-   <span data-ttu-id="c6128-130">スケール アップはコストが高すぎます。</span><span class="sxs-lookup"><span data-stu-id="c6128-130">Scaling-up is too expensive.</span></span> <span data-ttu-id="c6128-131">たとえば、8 ウェイ サーバーへの既存のクアッド プロセッサ サーバーが別のクアッド プロセッサを追加するよりも高価な場合は、スケール アウトがより適切なオプションです。</span><span class="sxs-lookup"><span data-stu-id="c6128-131">For example, if upgrading the existing quad proc server to 8 way server is more expensive than adding another quad proc, scale-out is better option.</span></span>  
  
## <a name="when-you-cant-scale-out-the-sql-tier"></a><span data-ttu-id="c6128-132">SQL 層をスケール アウトすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c6128-132">When You Can’t Scale-out the SQL Tier</span></span>  
 <span data-ttu-id="c6128-133">理論上は、無期限に限り、マスター メッセージ ボックス データベースがボトルネックにならない、SQL 層をスケールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6128-133">In theory, the SQL tier should scale indefinitely as long as the Master MessageBox database is not the bottleneck.</span></span> <span data-ttu-id="c6128-134">これを実現するには、ルーティング専用にするために、マスター メッセージ ボックス データベースを非公開データベースを作成を検討します。</span><span class="sxs-lookup"><span data-stu-id="c6128-134">To achieve this, consider making the Master MessageBox database a non-publishing database so it only does routing.</span></span> <span data-ttu-id="c6128-135">ただし、マスターのロックの競合によってボトルネックになって後をスケール アウトできない SQL 層 ―。</span><span class="sxs-lookup"><span data-stu-id="c6128-135">But, once the Master is bottlenecked by lock contention, you cannot scale out the SQL tier any more.</span></span>  
  
## <a name="scale-out-strategies-and-considerations"></a><span data-ttu-id="c6128-136">スケール アウト戦略と考慮事項</span><span class="sxs-lookup"><span data-stu-id="c6128-136">Scale-out Strategies and Considerations</span></span>  
  
-   <span data-ttu-id="c6128-137">まずマスター メッセージ ボックス データベースをスケール アップし、スケール アウトします。</span><span class="sxs-lookup"><span data-stu-id="c6128-137">First scale-up the Master MessageBox database and then scale out.</span></span>  
  
-   <span data-ttu-id="c6128-138">スケール アウト 1 から 1 ~ 2 ではなく 3 つの SQL メッセージ ボックス データベースにします。</span><span class="sxs-lookup"><span data-stu-id="c6128-138">Scaling-out from 1 to 3 SQL MessageBox databases instead of 1 to 2.</span></span> <span data-ttu-id="c6128-139">「4 つの BizTalk Server, 1 SQL Server トポロジでは、」というタイトルの上の図に示す 1 の SQL サーバー トポロジを検討して、SQL server は CPU バインド、つまり、ボトルネックは、CPU の処理を仮定します。</span><span class="sxs-lookup"><span data-stu-id="c6128-139">Consider the 1 SQL server topology illustrated in the figure above titled "4 BizTalk Server, 1 SQL Server Topology," and assume that the SQL server is CPU bound, in other words, the CPU processing is a bottleneck.</span></span> <span data-ttu-id="c6128-140">このトポロジに 1 つだけのメッセージ ボックス データベースを追加する場合は、マスター メッセージ ボックスでは、CPU バインドすることができ、使用率が低いセカンダリ メッセージ ボックス データベースになります。</span><span class="sxs-lookup"><span data-stu-id="c6128-140">If you add only one MessageBox database to this topology, the Master Messagebox will still be CPU bound and the secondary MessageBox database will be under-utilized.</span></span> <span data-ttu-id="c6128-141">そのため、スケール ファクターはほぼ 1 です。</span><span class="sxs-lookup"><span data-stu-id="c6128-141">So, the scaling factor is almost 1.</span></span> <span data-ttu-id="c6128-142">マスター メッセージ ボックス データベースでパブリッシングを無効にして、専用のルーティング専用に、マスター メッセージ ボックス データベース場合、セカンダリ メッセージ ボックス データベースには公開が行われます。</span><span class="sxs-lookup"><span data-stu-id="c6128-142">If you disable publishing on the Master MessageBox database and dedicate the Master MessageBox database only to do routing, the secondary MessageBox database will do the publishing.</span></span> <span data-ttu-id="c6128-143">効果がないため、セカンダリ メッセージ ボックス データベースはやはりボトルネックとなって、唯一のパブリッシャーが全体的なスループットが向上します。</span><span class="sxs-lookup"><span data-stu-id="c6128-143">This will not help increase overall throughput though since the secondary MessageBox database is the only publisher and still becomes the bottleneck.</span></span> <span data-ttu-id="c6128-144">そのため、2 つのセカンダリ メッセージ ボックス データベースを追加して、マスター メッセージ ボックス データベースでパブリッシングを無効にするは推奨される方法をこのシナリオではスケール アウトします。</span><span class="sxs-lookup"><span data-stu-id="c6128-144">So, adding 2 secondary MessageBox databases and disabling the publishing on the Master MessageBox database would be the recommended way to scale-out in this scenario.</span></span>  
  
-   <span data-ttu-id="c6128-145">マスター メッセージ ボックス データベースがボトルネックとなる最終的になります。</span><span class="sxs-lookup"><span data-stu-id="c6128-145">The Master MessageBox database will eventually be the bottleneck.</span></span> <span data-ttu-id="c6128-146">そのため、マスター メッセージ ボックス データベースをホストする物理コンピューターには、高速で大容量があります。</span><span class="sxs-lookup"><span data-stu-id="c6128-146">So, the physical computer hosting the Master MessageBox database should be faster and bigger.</span></span>  
  
-   <span data-ttu-id="c6128-147">ネットワーク (および関連する DTC オーバーヘッド) 経由でデータの送信を最小限に抑える、専用のドライブと同じ物理コンピューターに複数のメッセージ ボックス データベースを配置することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="c6128-147">To minimize sending data over the network (and the associated DTC overhead), consider placing multiple MessageBox databases on the same physical computer with dedicated drives.</span></span> <span data-ttu-id="c6128-148">同時に、リソースが複数のメッセージ ボックス データベースによって共有されているように、これら複数のデータベースを保持しているコンピューターがボトルネックいないを確認します。</span><span class="sxs-lookup"><span data-stu-id="c6128-148">At the same time, make sure that the computer holding these multiple databases is not bottlenecked as the resources are being shared by multiple MessageBox databases.</span></span>  
  
-   <span data-ttu-id="c6128-149">すべてのセカンダリ メッセージ ボックス データベースは、作業が公開メッセージ ボックス データベース間で均等に分散しているために、同等のハードウェアを使用してください。</span><span class="sxs-lookup"><span data-stu-id="c6128-149">All secondary MessageBox databases should use comparable hardware because work is evenly distributed among the publishing MessageBox databases.</span></span>  
  
-   <span data-ttu-id="c6128-150">マスター メッセージ ボックス データベースがボトルネックとならない限り、セカンダリ メッセージ ボックス データベースをスケールすることができます、ために、セカンダリ メッセージ ボックス データベースは、CPU リソースが少なく、マスター メッセージ ボックス データベース サーバーに必要なコンピューターで実行できます。</span><span class="sxs-lookup"><span data-stu-id="c6128-150">Since you can scale out secondary MessageBox databases as long as the master MessageBox database is not bottlenecked, secondary MessageBox databases can run on computers with less CPU resources than is required by the master MessageBox database server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6128-151">参照</span><span class="sxs-lookup"><span data-stu-id="c6128-151">See Also</span></span>  
 <span data-ttu-id="c6128-152">[BizTalk Server 層のスケール アウト](../core/scaling-out-the-biztalk-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="c6128-152">[Scaling Out the BizTalk Server Tier](../core/scaling-out-the-biztalk-server-tier.md) </span></span>  
 <span data-ttu-id="c6128-153">[BizTalk Server 層のスケール アップ](../core/scaling-up-the-biztalk-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="c6128-153">[Scaling Up the BizTalk Server Tier](../core/scaling-up-the-biztalk-server-tier.md) </span></span>  
 <span data-ttu-id="c6128-154">[SQL Server 層のスケール アップ](../core/scaling-up-the-sql-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="c6128-154">[Scaling Up the SQL Server Tier](../core/scaling-up-the-sql-server-tier.md) </span></span>  
 <span data-ttu-id="c6128-155">[受信ホスト スケール アウト](../core/scaled-out-receiving-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="c6128-155">[Scaled-Out Receiving Hosts](../core/scaled-out-receiving-hosts.md) </span></span>  
 <span data-ttu-id="c6128-156">[スケール アウトされた処理ホスト](../core/scaled-out-processing-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="c6128-156">[Scaled-Out Processing Hosts](../core/scaled-out-processing-hosts.md) </span></span>  
 <span data-ttu-id="c6128-157">[スケール アウトされた送信ホスト](../core/scaled-out-sending-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="c6128-157">[Scaled-Out Sending Hosts](../core/scaled-out-sending-hosts.md) </span></span>  
 <span data-ttu-id="c6128-158">[Windows Server クラスターを使用して BizTalk Server Hosts2 の高可用性を実現するには](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="c6128-158">[Using Windows Server Cluster to Provide High Availability for BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span></span>  
 <span data-ttu-id="c6128-159">[スケール アウト データベース](../core/scaled-out-databases.md) </span><span class="sxs-lookup"><span data-stu-id="c6128-159">[Scaled-Out Databases](../core/scaled-out-databases.md) </span></span>  
 [<span data-ttu-id="c6128-160">BizTalk Server データベースのクラスタリング</span><span class="sxs-lookup"><span data-stu-id="c6128-160">Clustering the BizTalk Server Databases</span></span>](../core/clustering-the-biztalk-server-databases1.md)