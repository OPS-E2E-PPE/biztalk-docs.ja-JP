---
title: "SQL Server 層のスケール アウト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- scaling, MessageBox database
- scaling, scaling out
- SQL Server, scaling
- MessageBox database, scaling
- scaling, strategies
ms.assetid: d5b2ebba-401e-4fde-8818-407fa626043a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 702c253a0135c1dc4af4cea15a9b47c77792586f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="scaling-out-the-sql-server-tier"></a><span data-ttu-id="63ef0-102">SQL Server 層のスケール アウト</span><span class="sxs-lookup"><span data-stu-id="63ef0-102">Scaling Out the SQL Server Tier</span></span>
<span data-ttu-id="63ef0-103">各 BizTalk グループには、マスター メッセージ ボックス データベースを 1 つ追加します。</span><span class="sxs-lookup"><span data-stu-id="63ef0-103">For each BizTalk group, you add one Master MessageBox database.</span></span> <span data-ttu-id="63ef0-104">以降追加したメッセージ ボックス データベースはすべて、セカンダリ メッセージ ボックスと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="63ef0-104">All the subsequent MessageBox databases that you add are called secondary MessageBoxes.</span></span> <span data-ttu-id="63ef0-105">マスター メッセージ ボックスは、すべてのサブスクリプションとメッセージ ルーティングを処理し、</span><span class="sxs-lookup"><span data-stu-id="63ef0-105">The Master MessageBox handles all subscriptions and message routing.</span></span> <span data-ttu-id="63ef0-106">メッセージの公開も行えます。</span><span class="sxs-lookup"><span data-stu-id="63ef0-106">It can also publish messages.</span></span> <span data-ttu-id="63ef0-107">セカンダリ メッセージ ボックス データベースは、特定の構成を行った場合にのみ、メッセージを公開します。</span><span class="sxs-lookup"><span data-stu-id="63ef0-107">Secondary MessageBox databases will only publish messages when specifically configured to do so.</span></span>  
  
## <a name="how-to-add-a-secondary-messagebox-database"></a><span data-ttu-id="63ef0-108">セカンダリ メッセージ ボックス データベースを追加する方法</span><span class="sxs-lookup"><span data-stu-id="63ef0-108">How to Add a Secondary MessageBox Database</span></span>  
 <span data-ttu-id="63ef0-109">セカンダリ メッセージ ボックス データベースを追加する方法は 2 とおりあります。</span><span class="sxs-lookup"><span data-stu-id="63ef0-109">There are two ways to add secondary MessageBox databases:</span></span>  
  
-   <span data-ttu-id="63ef0-110">セカンダリ メッセージ ボックス データベースを同じ物理サーバー上に追加する。</span><span class="sxs-lookup"><span data-stu-id="63ef0-110">Add the secondary MessageBox database on the same physical server.</span></span>  
  
     <span data-ttu-id="63ef0-111">既存のメッセージ ボックス物理サーバーに十分な CPU および I/O リソースがあり、ボトルネックの発生原因がロックの競合に限られている場合は、この方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="63ef0-111">Do this if the existing MessageBox physical server has enough CPU and I/O resources and is only bottlenecked by lock contention.</span></span> <span data-ttu-id="63ef0-112">セカンダリ メッセージ ボックス データベースを別の IO ドライブ上に作成します。</span><span class="sxs-lookup"><span data-stu-id="63ef0-112">Create the secondary MessageBox database on separate IO drives.</span></span>  
  
     <span data-ttu-id="63ef0-113">利点 : </span><span class="sxs-lookup"><span data-stu-id="63ef0-113">Advantages:</span></span>  
  
    -   <span data-ttu-id="63ef0-114">余分な CPU ヘッドルームを他のメッセージ ボックスに利用できます。</span><span class="sxs-lookup"><span data-stu-id="63ef0-114">The extra CPU headroom can be utilized by another message-box</span></span>  
  
    -   <span data-ttu-id="63ef0-115">SQL サーバー ライセンスが少なくて済みます。</span><span class="sxs-lookup"><span data-stu-id="63ef0-115">Fewer SQL server licenses are required</span></span>  
  
    -   <span data-ttu-id="63ef0-116">ネットワーク ホップがなくなります。</span><span class="sxs-lookup"><span data-stu-id="63ef0-116">Network hop is eliminated</span></span>  
  
-   <span data-ttu-id="63ef0-117">セカンダリ メッセージ ボックス データベースを別の物理サーバー上に追加する。</span><span class="sxs-lookup"><span data-stu-id="63ef0-117">Add the secondary MessageBox database on a different physical server</span></span>  
  
     <span data-ttu-id="63ef0-118">この場合は、追加のメッセージ ボックス データベースとして固有の IO を持つ専用の物理サーバーを使用します。</span><span class="sxs-lookup"><span data-stu-id="63ef0-118">In this case, use a dedicated physical server with its own IO as the extra MessageBox database.</span></span>  
  
 <span data-ttu-id="63ef0-119">次の図は、SQL 層を 1 つのメッセージ ボックス データベースから 3 つのメッセージ ボックス データベースにスケール アウトするシナリオを示しています。</span><span class="sxs-lookup"><span data-stu-id="63ef0-119">The following figure shows a scenario where SQL tier is scaled-out from one MessageBox database to three MessageBoxes databases.</span></span>  
  
 <span data-ttu-id="63ef0-120">![MSGBOX のスケール アウト](../core/media/scaleoutmsgbox.gif "ScaleOutMSGBOX")</span><span class="sxs-lookup"><span data-stu-id="63ef0-120">![Scale out MSGBOX](../core/media/scaleoutmsgbox.gif "ScaleOutMSGBOX")</span></span>  
  
## <a name="when-to-scale-out-the-messagebox-database"></a><span data-ttu-id="63ef0-121">メッセージ ボックス データベースのスケール アウトが必要になるケース</span><span class="sxs-lookup"><span data-stu-id="63ef0-121">When to Scale-out the MessageBox database</span></span>  
  
-   <span data-ttu-id="63ef0-122">メッセージ ボックス データベースがボトルネックとなる場合。</span><span class="sxs-lookup"><span data-stu-id="63ef0-122">The MessageBox database becomes the bottleneck.</span></span> <span data-ttu-id="63ef0-123">次のボトルネックが考えられます。</span><span class="sxs-lookup"><span data-stu-id="63ef0-123">Those bottlenecks can be:</span></span>  
  
    -   <span data-ttu-id="63ef0-124">**CPU**非常に複雑なオーケストレーション シナリオが発生した場合、メッセージ ボックス データベースは大量の CPU リソースを消費します。</span><span class="sxs-lookup"><span data-stu-id="63ef0-124">**CPU** In case of very expensive and complex orchestration scenarios, the MessageBox database consumes heavy CPU resources.</span></span> <span data-ttu-id="63ef0-125">公開メッセージ ボックス データベースを追加すると、スループットが向上します。</span><span class="sxs-lookup"><span data-stu-id="63ef0-125">Adding another publishing the MessageBox database should help increase the throughput.</span></span>  
  
    -   <span data-ttu-id="63ef0-126">**ロックの競合**複雑なシナリオで複数のホスト インスタンスやオーケストレーションがメッセージ ボックス データベースにロックの競合を作成する傾向があります。</span><span class="sxs-lookup"><span data-stu-id="63ef0-126">**Lock Contention** Complex scenarios with multiple host instances or orchestrations tend to create lock contention on the MessageBox database.</span></span> <span data-ttu-id="63ef0-127">この場合も、公開メッセージ ボックス データベースを追加すると、スループットが向上します。</span><span class="sxs-lookup"><span data-stu-id="63ef0-127">Again, adding another publishing MessageBox database should help increase the throughput.</span></span>  
  
-   <span data-ttu-id="63ef0-128">スケール アップしても、ボトルネックが解消されない場合。</span><span class="sxs-lookup"><span data-stu-id="63ef0-128">Scaling up doesn’t address the bottleneck.</span></span> <span data-ttu-id="63ef0-129">たとえば、マスター メッセージ ボックス データベースがロックの競合による制約を受けている場合、スケール アウトするしかありません。</span><span class="sxs-lookup"><span data-stu-id="63ef0-129">For example, if the Master MessageBox database is lock contention bound, scaling-out is the only option.</span></span>  
  
-   <span data-ttu-id="63ef0-130">スケール アップのコストが高すぎる場合。</span><span class="sxs-lookup"><span data-stu-id="63ef0-130">Scaling-up is too expensive.</span></span> <span data-ttu-id="63ef0-131">たとえば、既存のクアッド プロセッサ サーバーを 8 ウェイ サーバーにアップグレードするコストが、クアッド プロセッサをもう 1 つ追加するコストを上回るような場合は、スケール アウトすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="63ef0-131">For example, if upgrading the existing quad proc server to 8 way server is more expensive than adding another quad proc, scale-out is better option.</span></span>  
  
## <a name="when-you-cant-scale-out-the-sql-tier"></a><span data-ttu-id="63ef0-132">SQL 層をスケール アウトできないケース</span><span class="sxs-lookup"><span data-stu-id="63ef0-132">When You Can’t Scale-out the SQL Tier</span></span>  
 <span data-ttu-id="63ef0-133">マスター メッセージ ボックス データベースがボトルネックにならない限り、理論上は、SQL 層は無限にスケール アウトできます。</span><span class="sxs-lookup"><span data-stu-id="63ef0-133">In theory, the SQL tier should scale indefinitely as long as the Master MessageBox database is not the bottleneck.</span></span> <span data-ttu-id="63ef0-134">そのためには、マスター メッセージ ボックス データベースを非公開データベースにして、ルーティング専用にすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="63ef0-134">To achieve this, consider making the Master MessageBox database a non-publishing database so it only does routing.</span></span> <span data-ttu-id="63ef0-135">ただし、マスター メッセージ ボックス データベースがロックの競合によってボトルネックとなった場合は、SQL 層をそれ以上スケール アウトすることはできません。</span><span class="sxs-lookup"><span data-stu-id="63ef0-135">But, once the Master is bottlenecked by lock contention, you cannot scale out the SQL tier any more.</span></span>  
  
## <a name="scale-out-strategies-and-considerations"></a><span data-ttu-id="63ef0-136">スケール アウトの方法と検討事項</span><span class="sxs-lookup"><span data-stu-id="63ef0-136">Scale-out Strategies and Considerations</span></span>  
  
-   <span data-ttu-id="63ef0-137">まずマスター メッセージ ボックス データベースをスケール アップし、その後スケール アウトします。</span><span class="sxs-lookup"><span data-stu-id="63ef0-137">First scale-up the Master MessageBox database and then scale out.</span></span>  
  
-   <span data-ttu-id="63ef0-138">スケール アウト 1 から 1 ~ 2 ではなく 3 つの SQL メッセージ ボックス データベースにします。</span><span class="sxs-lookup"><span data-stu-id="63ef0-138">Scaling-out from 1 to 3 SQL MessageBox databases instead of 1 to 2.</span></span> <span data-ttu-id="63ef0-139">「4 つの BizTalk Server, 1 の SQL サーバーのトポロジでは、」というタイトル上の図に示す 1 の SQL server トポロジが考慮され、SQL server は CPU バインド、つまり、CPU の処理は、ボトルネックを前提としています。</span><span class="sxs-lookup"><span data-stu-id="63ef0-139">Consider the 1 SQL server topology illustrated in the figure above titled "4 BizTalk Server, 1 SQL Server Topology," and assume that the SQL server is CPU bound, in other words, the CPU processing is a bottleneck.</span></span> <span data-ttu-id="63ef0-140">このトポロジにメッセージ ボックス データベースを 1 つしか追加しない場合は、依然としてマスター メッセージ ボックス データベースが CPU に依存しており、セカンダリ メッセージ ボックス データベースは有効に利用されません。</span><span class="sxs-lookup"><span data-stu-id="63ef0-140">If you add only one MessageBox database to this topology, the Master Messagebox will still be CPU bound and the secondary MessageBox database will be under-utilized.</span></span> <span data-ttu-id="63ef0-141">そのため、スケール ファクターはほぼ 1 はします。</span><span class="sxs-lookup"><span data-stu-id="63ef0-141">So, the scaling factor is almost 1.</span></span> <span data-ttu-id="63ef0-142">専用のルーティングを行う場合にのみ、マスター メッセージ ボックス データベースをマスター メッセージ ボックス データベースでパブリッシングを無効にする場合、セカンダリ メッセージ ボックス データベースには公開が行われます。</span><span class="sxs-lookup"><span data-stu-id="63ef0-142">If you disable publishing on the Master MessageBox database and dedicate the Master MessageBox database only to do routing, the secondary MessageBox database will do the publishing.</span></span> <span data-ttu-id="63ef0-143">これでは、セカンダリ メッセージ ボックス データベースが唯一のパブリッシャーであり、やはりボトルネックとなってしまうので、全体のスループットは改善されません。</span><span class="sxs-lookup"><span data-stu-id="63ef0-143">This will not help increase overall throughput though since the secondary MessageBox database is the only publisher and still becomes the bottleneck.</span></span> <span data-ttu-id="63ef0-144">したがって、セカンダリ メッセージ ボックス データベースを 2 つ追加し、マスター メッセージ ボックス データベースでの公開を無効にして、このシナリオをスケールアウトすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="63ef0-144">So, adding 2 secondary MessageBox databases and disabling the publishing on the Master MessageBox database would be the recommended way to scale-out in this scenario.</span></span>  
  
-   <span data-ttu-id="63ef0-145">マスター メッセージ ボックス データベースは、いずれはボトルネックとなります。</span><span class="sxs-lookup"><span data-stu-id="63ef0-145">The Master MessageBox database will eventually be the bottleneck.</span></span> <span data-ttu-id="63ef0-146">そのため、マスター メッセージ ボックス データベースをホストする物理コンピューターの処理速度を速く、容量を大きくする必要があります。</span><span class="sxs-lookup"><span data-stu-id="63ef0-146">So, the physical computer hosting the Master MessageBox database should be faster and bigger.</span></span>  
  
-   <span data-ttu-id="63ef0-147">ネットワーク上で送信するデータ (および関連する DTC オーバーヘッド) を最小限に抑えるには、専用のドライブを持つ同一の物理コンピューター上に複数のメッセージ ボックス データベースを配置することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="63ef0-147">To minimize sending data over the network (and the associated DTC overhead), consider placing multiple MessageBox databases on the same physical computer with dedicated drives.</span></span> <span data-ttu-id="63ef0-148">それと同時に、これらの複数のデータベースを保持しているコンピューターでは、複数のマスター メッセージ ボックス データベースによってリソースが共有されているので、ボトルネックが生じないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="63ef0-148">At the same time, make sure that the computer holding these multiple databases is not bottlenecked as the resources are being shared by multiple MessageBox databases.</span></span>  
  
-   <span data-ttu-id="63ef0-149">すべての公開メッセージ ボックス データベース間で処理が均一に分散されるので、すべてのセカンダリ メッセージ ボックス データベースで同等のハードウェアを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63ef0-149">All secondary MessageBox databases should use comparable hardware because work is evenly distributed among the publishing MessageBox databases.</span></span>  
  
-   <span data-ttu-id="63ef0-150">マスター メッセージ ボックス データベースがボトルネックとならない限り、セカンダリ メッセージ ボックス データベースをスケール アウトできるので、セカンダリ メッセージ ボックス データベースは、マスター メッセージ ボックス データベース サーバーで必要とする CPU リソースよりも少ない CPU リソースのコンピューターで実行できます。</span><span class="sxs-lookup"><span data-stu-id="63ef0-150">Since you can scale out secondary MessageBox databases as long as the master MessageBox database is not bottlenecked, secondary MessageBox databases can run on computers with less CPU resources than is required by the master MessageBox database server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63ef0-151">参照</span><span class="sxs-lookup"><span data-stu-id="63ef0-151">See Also</span></span>  
 <span data-ttu-id="63ef0-152">[BizTalk Server 層のスケール アウト](../core/scaling-out-the-biztalk-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="63ef0-152">[Scaling Out the BizTalk Server Tier](../core/scaling-out-the-biztalk-server-tier.md) </span></span>  
 <span data-ttu-id="63ef0-153">[BizTalk Server 層のスケール アップ](../core/scaling-up-the-biztalk-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="63ef0-153">[Scaling Up the BizTalk Server Tier](../core/scaling-up-the-biztalk-server-tier.md) </span></span>  
 <span data-ttu-id="63ef0-154">[SQL Server 層のスケール アップ](../core/scaling-up-the-sql-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="63ef0-154">[Scaling Up the SQL Server Tier](../core/scaling-up-the-sql-server-tier.md) </span></span>  
 <span data-ttu-id="63ef0-155">[スケール アウト受信ホスト](../core/scaled-out-receiving-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="63ef0-155">[Scaled-Out Receiving Hosts](../core/scaled-out-receiving-hosts.md) </span></span>  
 <span data-ttu-id="63ef0-156">[スケール アウトされた処理ホスト](../core/scaled-out-processing-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="63ef0-156">[Scaled-Out Processing Hosts](../core/scaled-out-processing-hosts.md) </span></span>  
 <span data-ttu-id="63ef0-157">[スケール アウトされた送信ホスト](../core/scaled-out-sending-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="63ef0-157">[Scaled-Out Sending Hosts](../core/scaled-out-sending-hosts.md) </span></span>  
 <span data-ttu-id="63ef0-158">[Windows Server クラスターを使用して BizTalk Server Hosts2 の高可用性を実現するには](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="63ef0-158">[Using Windows Server Cluster to Provide High Availability for BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span></span>  
 <span data-ttu-id="63ef0-159">[スケール アウト データベース](../core/scaled-out-databases.md) </span><span class="sxs-lookup"><span data-stu-id="63ef0-159">[Scaled-Out Databases](../core/scaled-out-databases.md) </span></span>  
 [<span data-ttu-id="63ef0-160">BizTalk Server データベースをクラスタ リング</span><span class="sxs-lookup"><span data-stu-id="63ef0-160">Clustering the BizTalk Server Databases</span></span>](../core/clustering-the-biztalk-server-databases1.md)