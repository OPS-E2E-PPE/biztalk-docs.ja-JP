---
title: BizTalk Server 層のスケール アウト |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, scaling
- scaling, planning
- scaling, load balancing
- host instances, scaling
- scaling, examples
- fault tolerance
- scaling, scaling out
- scaling, fault tolerance
- NLB system, scaling
- scaling, host instances
ms.assetid: 01d1ab20-d7a9-4d0b-a61e-65e56fe5010e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35674e89d8f8104a35718531f2a87f95e8bc67e6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271970"
---
# <a name="scaling-out-the-biztalk-server-tier"></a><span data-ttu-id="d4575-102">BizTalk Server 層のスケール アウト</span><span class="sxs-lookup"><span data-stu-id="d4575-102">Scaling Out the BizTalk Server Tier</span></span>
<span data-ttu-id="d4575-103">BizTalk Server 層をスケール アウトするには、追加のハードウェアを既存のトポロジに追加します。</span><span class="sxs-lookup"><span data-stu-id="d4575-103">To scale out the BizTalk tier, add more hardware to the existing topology.</span></span> <span data-ttu-id="d4575-104">次のシナリオでは、ハードウェアを追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d4575-104">It is recommended that you add hardware in the following scenarios:</span></span>  
  
-   <span data-ttu-id="d4575-105">BizTalk Server がボトルネックになります。</span><span class="sxs-lookup"><span data-stu-id="d4575-105">BizTalk Server becomes a bottleneck.</span></span> <span data-ttu-id="d4575-106">ボトルネックは、次のいずれかの問題によって引き起こされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d4575-106">The bottleneck itself may be caused by one of the following problems:</span></span>  
  
-   <span data-ttu-id="d4575-107">CPU: CPU を集中的に使用するパイプライン、マップ、またはオーケストレーションをシナリオで使用する場合に、BizTalk Server に余分な CPU ヘッドルームがない。</span><span class="sxs-lookup"><span data-stu-id="d4575-107">CPU: If the scenario uses CPU intensive pipelines, maps, or orchestrations, the BizTalk servers will not have any extra CPU headroom.</span></span>  
  
-   <span data-ttu-id="d4575-108">メモリと I/O: 既存のコンピューターのメモリおよび I/O が上限に達した場合に、リソースを追加する方法として、別の物理的なコンピューターを追加するしかない。</span><span class="sxs-lookup"><span data-stu-id="d4575-108">Memory and I/O: If the existing computers have reached their maximum limit on memory and IO, the only way to add resources is to add another physical computer.</span></span>  
  
-   <span data-ttu-id="d4575-109">スケール アップは、非常に高コストです。</span><span class="sxs-lookup"><span data-stu-id="d4575-109">Scaling up is too expensive.</span></span> <span data-ttu-id="d4575-110">たとえば、BizTalk の CPU が最大容量に達しているシングル BizTalk Server トポロジについて考えてみます。</span><span class="sxs-lookup"><span data-stu-id="d4575-110">For example, consider the 1 BizTalk Server topology where the BizTalk CPU is at maximum capacity.</span></span> <span data-ttu-id="d4575-111">デュアル プロセッサをクワド プロセッサにアップグレードするよりもデュアル プロセッサを搭載したコンピューターを追加する方がコストがかからない場合は、システムをスケール アウトする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4575-111">If it is cheaper to add extra dual processor machines instead of upgrading the dual processor to a quad processor, you should instead scale-outyour system.</span></span>  
  
-   <span data-ttu-id="d4575-112">スケール アップは、ボトルネックを解消しません。</span><span class="sxs-lookup"><span data-stu-id="d4575-112">Scaling-up does not fix the bottleneck.</span></span> <span data-ttu-id="d4575-113">次のシナリオでは、スケール アップが機能しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="d4575-113">Scaling up may not work in the following scenarios:</span></span>  
  
    -   <span data-ttu-id="d4575-114">I/O が BizTalk コンピューターの最大値に達したので、I/O を調整するために別のコンピューターが必要である。</span><span class="sxs-lookup"><span data-stu-id="d4575-114">IO is at the maximum level for the BizTalk computer so you need another computer to scale the IO.</span></span>  
  
    -   <span data-ttu-id="d4575-115">メモリがオペレーティング システムの最大値に達している。</span><span class="sxs-lookup"><span data-stu-id="d4575-115">Memory is at the maximum level for your operating system.</span></span> <span data-ttu-id="d4575-116">このシナリオで、システムを拡張する方法は、BizTalk コンピューターをトポロジに追加する方法だけです。</span><span class="sxs-lookup"><span data-stu-id="d4575-116">In this scenario, the only way to scale your system is to add an extra BizTalk computermachine to the topology.</span></span>  
  
 <span data-ttu-id="d4575-117">一部のシナリオでは、メッセージの受信、メッセージの送信、およびその処理を行う専用サーバーが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d4575-117">In some scenarios, you may want dedicated servers for receiving messages, sending messages, and processing them.</span></span> <span data-ttu-id="d4575-118">専用サーバーがあれば、問題を切り離して、他のコンピューターに影響を与えることなく 1 台のコンピューターの保守を行うことが容易です。</span><span class="sxs-lookup"><span data-stu-id="d4575-118">When you have dedicated servers, it is easier to isolate problems and do maintenance on one computer without impacting the others.</span></span> <span data-ttu-id="d4575-119">BizTalk 層を拡張して、これらのコンピューターを追加できます。</span><span class="sxs-lookup"><span data-stu-id="d4575-119">You can add these computers by scaling our the BizTalk tier.</span></span>  
  
## <a name="when-you-cant-scale-out-the-biztalk-tier"></a><span data-ttu-id="d4575-120">BizTalk 層をスケール アウトできない場合</span><span class="sxs-lookup"><span data-stu-id="d4575-120">When You Can’t Scale Out the BizTalk Tier</span></span>  
  
-   <span data-ttu-id="d4575-121">メッセージ ボックス データベースがボトルネックの場合。</span><span class="sxs-lookup"><span data-stu-id="d4575-121">The MessageBox database is the bottleneck.</span></span>  
  
-   <span data-ttu-id="d4575-122">アダプターがボトルネックになる場合。</span><span class="sxs-lookup"><span data-stu-id="d4575-122">An adapter becomes the bottleneck.</span></span> <span data-ttu-id="d4575-123">たとえば、SQL アダプターを使用している場合、BizTalk の受信者数を増やすと、BizTalk SQL アダプターがデータを抽出する SQL データベースでロックの競合が増えます。</span><span class="sxs-lookup"><span data-stu-id="d4575-123">For example, if you are using the SQL adapter, after you increase the number of BizTalk receivers, lock contention increases on the SQL database where the BizTalk SQL adapter is pulling data from.</span></span> <span data-ttu-id="d4575-124">このため、SQL アダプターのスケール アウトが制限されます。</span><span class="sxs-lookup"><span data-stu-id="d4575-124">This limits your ability to scale out the SQL adapter.</span></span>  
  
 <span data-ttu-id="d4575-125">次の図は、BizTalk 層のスケール アウト方法の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="d4575-125">The following figure shows an example of how you might scale out the BizTalk tier.</span></span>  
  
 <span data-ttu-id="d4575-126">![BTS のスケール アウト](../core/media/scaleoutbts.gif "ScaleOutBTS")</span><span class="sxs-lookup"><span data-stu-id="d4575-126">![Scaleout BTS](../core/media/scaleoutbts.gif "ScaleOutBTS")</span></span>  
  
 <span data-ttu-id="d4575-127">この図は、スケール アウトされた BizTalk トポロジを示しています。シングル BizTalk Server からダブル BizTalk Server に拡張されています。</span><span class="sxs-lookup"><span data-stu-id="d4575-127">This figure shows a scaled-out BizTalk topology, scaling from one BizTalk server to 2 BizTalk servers.</span></span> <span data-ttu-id="d4575-128">シングル BizTalk Server トポロジでは、3 つのホスト インスタンスが BizTalk コンピューター リソースを共有しています。</span><span class="sxs-lookup"><span data-stu-id="d4575-128">In the one BizTalk server topology, three host instances are sharing the BizTalk computer resources.</span></span> <span data-ttu-id="d4575-129">ダブル BizTalk Server トポロジでは、送信ホストが別のサーバーに分離され、スループットが向上します。</span><span class="sxs-lookup"><span data-stu-id="d4575-129">In the two BizTalk server topology, the transmit host is separated onto a different server, which achieves more throughput.</span></span>  
  
## <a name="considerations-when-scaling-out-the-biztalk-tier"></a><span data-ttu-id="d4575-130">BizTalk 層をスケール アウトする際の注意</span><span class="sxs-lookup"><span data-stu-id="d4575-130">Considerations When Scaling Out the BizTalk Tier</span></span>  
 <span data-ttu-id="d4575-131">別の BizTalk Server コンピューターを追加する前に、次の質問を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4575-131">You must consider the following questions before you add another BizTalk Server computer:</span></span>  
  
#### <a name="how-do-i-configure-the-system-for-load-balancing-and-fault-tolerance-when-i-scale-out-the-biztalk-tier"></a><span data-ttu-id="d4575-132">BizTalk 層をスケール アウトする際、負荷分散およびフォールト トレランスを考慮するとシステムをどのように構成すればよいか</span><span class="sxs-lookup"><span data-stu-id="d4575-132">How do I configure the system for load balancing and fault tolerance when I scale out the BizTalk tier?</span></span>  
 <span data-ttu-id="d4575-133">負荷分散およびフォールト トレランスを使用するかどうかは、シナリオで使用されているアダプターによって異なります。</span><span class="sxs-lookup"><span data-stu-id="d4575-133">The selection of load balancing and fault tolerance technology depends on the adapter that is being used in the scenario.</span></span> <span data-ttu-id="d4575-134">SOAP アダプターおよび HTTP アダプターを使用する場合、NLB を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d4575-134">For SOAP and HTTP adapters, the recommended way is to use NLB.</span></span> <span data-ttu-id="d4575-135">詳細については、NLB のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4575-135">Refer to NLB documentation for more details.</span></span>  
  
#### <a name="how-do-i-refactor-the-host-instances"></a><span data-ttu-id="d4575-136">ホスト インスタンスをリファクタリングするにはどうすればよいか</span><span class="sxs-lookup"><span data-stu-id="d4575-136">How do I refactor the host instances?</span></span>  
 <span data-ttu-id="d4575-137">BizTalk 層をスケール アウトする際にホスト インスタンスをリファクタリングする方法を規定している規則はありません。</span><span class="sxs-lookup"><span data-stu-id="d4575-137">There is no one rule to determine how you should refactor the host instances when you scale out the BizTalk tier.</span></span> <span data-ttu-id="d4575-138">ホスト インスタンスをファクタリングする時期は、シナリオの複雑さによって異なります。</span><span class="sxs-lookup"><span data-stu-id="d4575-138">When you factor the host instances depends on the complexity of scenario.</span></span> <span data-ttu-id="d4575-139">ホスト インスタンスをファクタリングする方法の例をいくつか次に示します。</span><span class="sxs-lookup"><span data-stu-id="d4575-139">Following are some examples how to factor the host instances.</span></span>  
  
##### <a name="scenario-1"></a><span data-ttu-id="d4575-140">シナリオ 1</span><span class="sxs-lookup"><span data-stu-id="d4575-140">Scenario 1</span></span>  
 <span data-ttu-id="d4575-141">シングル BizTalk Server 構成で、受信用と送信用のホスト インスタンスが同じコンピューター上にあります。</span><span class="sxs-lookup"><span data-stu-id="d4575-141">One BizTalk server configuration, and receive and transmit host instances are on the same computer.</span></span>  
  
 <span data-ttu-id="d4575-142">CPU にボトルネックがあると仮定します。</span><span class="sxs-lookup"><span data-stu-id="d4575-142">Assume there is a CPU bottleneck.</span></span> <span data-ttu-id="d4575-143">スケール アウトするために別の同等の BizTalk コンピューターをグループに追加する場合、ホスト インスタンスをファクタリングする方法は 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="d4575-143">You add another identical BizTalk computer to the group to scale-out, giving you two ways to factor the host instances.</span></span>  
  
 <span data-ttu-id="d4575-144">この問題の 2 つの解決方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d4575-144">Here are two solutions to this problem:</span></span>  
  
-   <span data-ttu-id="d4575-145">**解決策 1**: このシナリオでファクタリングの最も簡単な方法は、ファクタリングするホスト インスタンスの最初のコンピューターから 2 つ目のコンピューターに複製します。</span><span class="sxs-lookup"><span data-stu-id="d4575-145">**Solution 1**: The easiest way of factoring in this scenario is to clone the host instance factoring from first computer to second computer.</span></span> <span data-ttu-id="d4575-146">したがって、2 番目のコンピューターは、機能性の面で 1 番目のコンピューターと完全に同等になります。また、受信ホストおよび送信ホストの両方を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d4575-146">So, the second computer is an exact copy of the first in term of functionality; it can also have both receive and send hosts.</span></span> <span data-ttu-id="d4575-147">他のボトルネックがないと仮定した場合、CPU リソースが 2 倍になるため、スケール ファクターは 2 となります。</span><span class="sxs-lookup"><span data-stu-id="d4575-147">Assuming there is no other bottleneck, you may get a scaling factor of 2 as the CPU resources are doubled.</span></span>  
  
-   <span data-ttu-id="d4575-148">**解決策 2**: ホスト インスタンスをファクタリングする別の方法は、受信を分離し、別のコンピューターに関数を送信します。</span><span class="sxs-lookup"><span data-stu-id="d4575-148">**Solution 2**: Another way to factor the host instances is to isolate the receive and send functions onto different computers.</span></span> <span data-ttu-id="d4575-149">したがって、1 つの BizTalk Server を受信用に使用し、他の BizTalk Server を送信用に使用します。</span><span class="sxs-lookup"><span data-stu-id="d4575-149">So, one of the BizTalk servers is dedicated for receiving and other for sending.</span></span>  
  
 <span data-ttu-id="d4575-150">**解決方法 1 と 2 のソリューションの比較**</span><span class="sxs-lookup"><span data-stu-id="d4575-150">**Comparing Solution 1 and Solution 2**</span></span>  
  
 <span data-ttu-id="d4575-151">解決方法 1 のホスト インスタンス数は、シングル BTS 構成の 2 倍になります。</span><span class="sxs-lookup"><span data-stu-id="d4575-151">In solution 1, the number of host instances is doubled from 1 BTS configuration.</span></span> <span data-ttu-id="d4575-152">つまり、SQL Server 上のロックの競合が増加することを示しています。</span><span class="sxs-lookup"><span data-stu-id="d4575-152">This means that lock contention on the SQL server will increase.</span></span> <span data-ttu-id="d4575-153">ロックの競合がどれだけ増えるかによって、スケール ファクターが決まります。</span><span class="sxs-lookup"><span data-stu-id="d4575-153">How much it increases in lock contention will determine the scaling factor.</span></span> <span data-ttu-id="d4575-154">ロックの競合がボトルネックとなる制限の範囲内の場合、スケール ファクターは 2 になります。</span><span class="sxs-lookup"><span data-stu-id="d4575-154">If the lock contention is well within limits of becoming a bottleneck, you can see a scaling factor of 2.</span></span>  
  
 <span data-ttu-id="d4575-155">解決方法 2 の場合は、SQL server のロックの競合は解決方法 1 よりも少なくなるために、2 つのホスト インスタンスがあること。</span><span class="sxs-lookup"><span data-stu-id="d4575-155">The advantage of solution 2 is that you have only two host instances, so the lock contention on the SQL server should be less compared to solution 1.</span></span> <span data-ttu-id="d4575-156">ただし、スケール ファクターが、受信の複雑さに完全に依存し、送信ホスト インスタンス。</span><span class="sxs-lookup"><span data-stu-id="d4575-156">But, the scaling factor depends completely on the complexity of the receive and send host instances.</span></span> <span data-ttu-id="d4575-157">解決方法 2 での次のような事例を考えてみます。</span><span class="sxs-lookup"><span data-stu-id="d4575-157">Consider the following cases in solution 2:</span></span>  
  
 <span data-ttu-id="d4575-158">受信ホスト インスタンスと送信ホスト インスタンスに同じ負荷がかかり、シングル BizTalk Server トポロジでそれぞれが CPU の 50% を使用していると仮定します。</span><span class="sxs-lookup"><span data-stu-id="d4575-158">Assume that both the receive and transmit host instances are equally intensive and they each use 50% of the CPU in the one BizTalk server topology.</span></span> <span data-ttu-id="d4575-159">ダブル BizTalk Server トポロジでは、送信ホスト インスタンスを別のコンピューターに移動するため、受信と送信の両方でリソースを 2 倍消費します。</span><span class="sxs-lookup"><span data-stu-id="d4575-159">In the two BizTalk server topology, you move the transmit host instance to different computer, and now both receive and transmit get double the resources.</span></span> <span data-ttu-id="d4575-160">このため、他のボトルネックがないと仮定した場合、スケール ファクターは 2 になります。</span><span class="sxs-lookup"><span data-stu-id="d4575-160">This should provide a scaling factor of 2, assuming that there is no other bottleneck.</span></span> <span data-ttu-id="d4575-161">ホスト インスタンスが 2 つだけでロックの競合が少ないため、この事例では解決方法 1 よりも適しています。</span><span class="sxs-lookup"><span data-stu-id="d4575-161">This case is better than Solution 1 because there are only two host instances and hence les lock contention.</span></span>  
  
 <span data-ttu-id="d4575-162">受信よりも送信に多くの負荷がかかり、シングル BizTalk Server トポロジで 80% の CPU リソースを消費していると仮定します。</span><span class="sxs-lookup"><span data-stu-id="d4575-162">Assume that transmit is way more intensive than receive, and uses 80% CPU resources in the one BizTalk server topology.</span></span> <span data-ttu-id="d4575-163">送信ホスト インスタンスを別のコンピューターに移動しても、使用できる CPU リソースは 20% しか増えません。このため、スケール ファクターの最大値は、1.2 になります。</span><span class="sxs-lookup"><span data-stu-id="d4575-163">By moving the transmit host instance to another machine, you gain only 20% more CPU resources so the maximum scaling factor will be 1.2.</span></span> <span data-ttu-id="d4575-164">さらに、受信ホスト インスタンスのコンピューターは、CPU リソースを 20 ～ 30% しか使用しません。このため、スケールアウトの利点はさらに少なくなります。</span><span class="sxs-lookup"><span data-stu-id="d4575-164">Moreover, the computer with the receive host instance will use only 20-30% CPU resources so the advantage of scaling-out is much less.</span></span>  
  
 <span data-ttu-id="d4575-165">4 つの BizTalk Server のある次の図を見てください。</span><span class="sxs-lookup"><span data-stu-id="d4575-165">Consider the following figure that has four BizTalk servers.</span></span> <span data-ttu-id="d4575-166">各コンピューターは、受信と送信の役割を果たし、各種類 (受信と送信) の 4 つのホスト インスタンスが提供されています。</span><span class="sxs-lookup"><span data-stu-id="d4575-166">Each computer is both receiver and sender, giving you a  total of four host instances of each type (receive and transmit).</span></span>  
  
 <span data-ttu-id="d4575-167">![Re &#45; ホスト インスタンスをファクタリング](../core/media/refactoringhostinstances.gif "RefactoringHostinstances")</span><span class="sxs-lookup"><span data-stu-id="d4575-167">![Re&#45;factoring host instances](../core/media/refactoringhostinstances.gif "RefactoringHostinstances")</span></span>  
  
 <span data-ttu-id="d4575-168">このトポロジは、最適ではありません。</span><span class="sxs-lookup"><span data-stu-id="d4575-168">This topology might not be the best possible one possible.</span></span> <span data-ttu-id="d4575-169">また、シナリオの複雑さに応じて、他のファクタリングの配置をテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4575-169">You should also test other factoring permutations, depending on the complexity of scenario.</span></span> <span data-ttu-id="d4575-170">例:</span><span class="sxs-lookup"><span data-stu-id="d4575-170">For example:</span></span>  
  
-   <span data-ttu-id="d4575-171">受信用と送信用にそれぞれ 2 台のコンピューターを使用します。</span><span class="sxs-lookup"><span data-stu-id="d4575-171">Dedicate two computers for receiving and  two for transmitting.</span></span> <span data-ttu-id="d4575-172">これによって、受信と送信で同じ負荷がかかった場合に、最適な拡張を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d4575-172">This will give you the best possible scaling when both receive and send are equally intensive.</span></span>  
  
-   <span data-ttu-id="d4575-173">送信よりも受信に負荷がかかっている場合、受信用に 3 台のコンピューター、送信用に 1 台のコンピューターを使用します。</span><span class="sxs-lookup"><span data-stu-id="d4575-173">Dedicate three computersfor receiving and one for transmitting, if receiving is more intensive than transmit.</span></span>  
  
-   <span data-ttu-id="d4575-174">受信よりも送信に負荷がかかっている場合、受信用に 1 台のコンピューター、送信用に 3 台のコンピューターを使用します。</span><span class="sxs-lookup"><span data-stu-id="d4575-174">Dedicate one computer for receive and three for transmitting if transmitting is more intensive than receive.</span></span>  
  
 <span data-ttu-id="d4575-175">すべてのシナリオにおいて、メッセージ ボックス データベースの競合を減らすと共にコンピューター リソースを最大限に利用するため、各ホストのホスト インスタンスの数を最小限にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d4575-175">In all scenarios, it is recommended that you minimize the number of host instances of each host so that contention on the MessageBox database is reduced and at the same time use the computer resources are use to the fullest.</span></span> <span data-ttu-id="d4575-176">最適なファクタリングの配置は、シナリオの複雑さとボトルネックの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="d4575-176">The best factoring permutation depends on the complexity of scenario and type of bottleneck.</span></span> <span data-ttu-id="d4575-177">配置を決める前にファクタリングを必ずテストしてください。</span><span class="sxs-lookup"><span data-stu-id="d4575-177">Always test your factoring before you finalize a permutation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4575-178">参照</span><span class="sxs-lookup"><span data-stu-id="d4575-178">See Also</span></span>  
 <span data-ttu-id="d4575-179">[BizTalk Server 層のスケール アップ](../core/scaling-up-the-biztalk-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="d4575-179">[Scaling Up the BizTalk Server Tier](../core/scaling-up-the-biztalk-server-tier.md) </span></span>  
 <span data-ttu-id="d4575-180">[SQL Server 層のスケール アップ](../core/scaling-up-the-sql-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="d4575-180">[Scaling Up the SQL Server Tier](../core/scaling-up-the-sql-server-tier.md) </span></span>  
 <span data-ttu-id="d4575-181">[SQL Server 層のスケール アウト](../core/scaling-out-the-sql-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="d4575-181">[Scaling Out the SQL Server Tier](../core/scaling-out-the-sql-server-tier.md) </span></span>  
 <span data-ttu-id="d4575-182">[スケール アウト受信ホスト](../core/scaled-out-receiving-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="d4575-182">[Scaled-Out Receiving Hosts](../core/scaled-out-receiving-hosts.md) </span></span>  
 <span data-ttu-id="d4575-183">[スケール アウトされた処理ホスト](../core/scaled-out-processing-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="d4575-183">[Scaled-Out Processing Hosts](../core/scaled-out-processing-hosts.md) </span></span>  
 <span data-ttu-id="d4575-184">[スケール アウトされた送信ホスト](../core/scaled-out-sending-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="d4575-184">[Scaled-Out Sending Hosts](../core/scaled-out-sending-hosts.md) </span></span>  
 <span data-ttu-id="d4575-185">[Windows Server クラスターを使用して BizTalk Server Hosts2 の高可用性を実現するには](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="d4575-185">[Using Windows Server Cluster to Provide High Availability for BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span></span>  
 <span data-ttu-id="d4575-186">[スケール アウト データベース](../core/scaled-out-databases.md) </span><span class="sxs-lookup"><span data-stu-id="d4575-186">[Scaled-Out Databases](../core/scaled-out-databases.md) </span></span>  
 [<span data-ttu-id="d4575-187">BizTalk Server データベースをクラスタ リング</span><span class="sxs-lookup"><span data-stu-id="d4575-187">Clustering the BizTalk Server Databases</span></span>](../core/clustering-the-biztalk-server-databases1.md)