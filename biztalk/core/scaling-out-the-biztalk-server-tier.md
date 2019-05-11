---
title: BizTalk Server 層のスケール アウト |Microsoft Docs
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
ms.openlocfilehash: 5e04050f1d7346f06d8b0d0a7163ac28f8d538f0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308966"
---
# <a name="scaling-out-the-biztalk-server-tier"></a><span data-ttu-id="524ab-102">BizTalk Server 層のスケール アウト</span><span class="sxs-lookup"><span data-stu-id="524ab-102">Scaling Out the BizTalk Server Tier</span></span>
<span data-ttu-id="524ab-103">BizTalk 層を拡大するには、既存のトポロジにより多くのハードウェアを追加します。</span><span class="sxs-lookup"><span data-stu-id="524ab-103">To scale out the BizTalk tier, add more hardware to the existing topology.</span></span> <span data-ttu-id="524ab-104">次のシナリオでは、ハードウェアを追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="524ab-104">It is recommended that you add hardware in the following scenarios:</span></span>  
  
- <span data-ttu-id="524ab-105">BizTalk Server では、ボトルネックになります。</span><span class="sxs-lookup"><span data-stu-id="524ab-105">BizTalk Server becomes a bottleneck.</span></span> <span data-ttu-id="524ab-106">次の問題のいずれかでは、ボトルネックが考えられます。</span><span class="sxs-lookup"><span data-stu-id="524ab-106">The bottleneck itself may be caused by one of the following problems:</span></span>  
  
- <span data-ttu-id="524ab-107">CPU:シナリオでは、CPU 負荷のかかるパイプライン、マップ、またはオーケストレーションを使用する場合、BizTalk server には余分な CPU ヘッドルームはありません。</span><span class="sxs-lookup"><span data-stu-id="524ab-107">CPU: If the scenario uses CPU intensive pipelines, maps, or orchestrations, the BizTalk servers will not have any extra CPU headroom.</span></span>  
  
- <span data-ttu-id="524ab-108">メモリと I/O:既存のコンピューターが、メモリおよび I/O が上限に達すると、リソースを追加する唯一の方法では、別の物理コンピューターを追加します。</span><span class="sxs-lookup"><span data-stu-id="524ab-108">Memory and I/O: If the existing computers have reached their maximum limit on memory and IO, the only way to add resources is to add another physical computer.</span></span>  
  
- <span data-ttu-id="524ab-109">スケール アップは、コストが高すぎます。</span><span class="sxs-lookup"><span data-stu-id="524ab-109">Scaling up is too expensive.</span></span> <span data-ttu-id="524ab-110">たとえば、BizTalk の CPU が最大能力では、1 BizTalk Server トポロジを検討してください。</span><span class="sxs-lookup"><span data-stu-id="524ab-110">For example, consider the 1 BizTalk Server topology where the BizTalk CPU is at maximum capacity.</span></span> <span data-ttu-id="524ab-111">デュアル プロセッサをクワド プロセッサにアップグレードする代わりに余分なデュアル プロセッサ コンピューターを追加コストは、システムのスケールよりを代わりにしてください。</span><span class="sxs-lookup"><span data-stu-id="524ab-111">If it is cheaper to add extra dual processor machines instead of upgrading the dual processor to a quad processor, you should instead scale-outyour system.</span></span>  
  
- <span data-ttu-id="524ab-112">スケール アップは、ボトルネックを解決できません。</span><span class="sxs-lookup"><span data-stu-id="524ab-112">Scaling-up does not fix the bottleneck.</span></span> <span data-ttu-id="524ab-113">スケール アップは、次のシナリオでが機能しません。</span><span class="sxs-lookup"><span data-stu-id="524ab-113">Scaling up may not work in the following scenarios:</span></span>  
  
  -   <span data-ttu-id="524ab-114">IO は BizTalk コンピューターの最大レベルでは別のコンピューターに、I/O を調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="524ab-114">IO is at the maximum level for the BizTalk computer so you need another computer to scale the IO.</span></span>  
  
  -   <span data-ttu-id="524ab-115">メモリは、オペレーティング システムの最大レベルでです。</span><span class="sxs-lookup"><span data-stu-id="524ab-115">Memory is at the maximum level for your operating system.</span></span> <span data-ttu-id="524ab-116">このシナリオでは、トポロジに追加の BizTalk コンピューターを追加する、システムを拡張するしかありません。</span><span class="sxs-lookup"><span data-stu-id="524ab-116">In this scenario, the only way to scale your system is to add an extra BizTalk computermachine to the topology.</span></span>  
  
  <span data-ttu-id="524ab-117">一部のシナリオで専用のサーバーのメッセージの受信、メッセージを送信する、およびそれらを処理する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="524ab-117">In some scenarios, you may want dedicated servers for receiving messages, sending messages, and processing them.</span></span> <span data-ttu-id="524ab-118">専用サーバーがときは、問題を特定し、他のユーザーに影響を与えることがなく 1 台のコンピューターのメンテナンスを行うには簡単です。</span><span class="sxs-lookup"><span data-stu-id="524ab-118">When you have dedicated servers, it is easier to isolate problems and do maintenance on one computer without impacting the others.</span></span> <span data-ttu-id="524ab-119">これらのコンピューターを追加するには、スケーリング、BizTalk 層。</span><span class="sxs-lookup"><span data-stu-id="524ab-119">You can add these computers by scaling our the BizTalk tier.</span></span>  
  
## <a name="when-you-cant-scale-out-the-biztalk-tier"></a><span data-ttu-id="524ab-120">ときに、BizTalk 層を拡大することはできません。</span><span class="sxs-lookup"><span data-stu-id="524ab-120">When You Can’t Scale Out the BizTalk Tier</span></span>  
  
- <span data-ttu-id="524ab-121">メッセージ ボックス データベースでは、ボトルネックです。</span><span class="sxs-lookup"><span data-stu-id="524ab-121">The MessageBox database is the bottleneck.</span></span>  
  
- <span data-ttu-id="524ab-122">アダプターがボトルネックになります。</span><span class="sxs-lookup"><span data-stu-id="524ab-122">An adapter becomes the bottleneck.</span></span> <span data-ttu-id="524ab-123">たとえば、BizTalk の受信者数を増やした後、SQL アダプターを使用する場合、BizTalk SQL アダプターがデータを抽出する SQL database でロックの競合が増加します。</span><span class="sxs-lookup"><span data-stu-id="524ab-123">For example, if you are using the SQL adapter, after you increase the number of BizTalk receivers, lock contention increases on the SQL database where the BizTalk SQL adapter is pulling data from.</span></span> <span data-ttu-id="524ab-124">これは、SQL アダプターをスケーリングする能力を制限します。</span><span class="sxs-lookup"><span data-stu-id="524ab-124">This limits your ability to scale out the SQL adapter.</span></span>  
  
  <span data-ttu-id="524ab-125">次の図は、BizTalk 層をスケールとする方法の例を示します。</span><span class="sxs-lookup"><span data-stu-id="524ab-125">The following figure shows an example of how you might scale out the BizTalk tier.</span></span>  
  
  <span data-ttu-id="524ab-126">![BTS のスケール アウト](../core/media/scaleoutbts.gif "ScaleOutBTS")</span><span class="sxs-lookup"><span data-stu-id="524ab-126">![Scaleout BTS](../core/media/scaleoutbts.gif "ScaleOutBTS")</span></span>  
  
  <span data-ttu-id="524ab-127">この図は、スケール アウトされた BizTalk トポロジでは、2 つの BizTalk サーバーに 1 つの BizTalk server からのスケーリングを示しています。</span><span class="sxs-lookup"><span data-stu-id="524ab-127">This figure shows a scaled-out BizTalk topology, scaling from one BizTalk server to 2 BizTalk servers.</span></span> <span data-ttu-id="524ab-128">1 つの BizTalk server トポロジで 3 つのホスト インスタンスが BizTalk コンピューター リソースを共有します。</span><span class="sxs-lookup"><span data-stu-id="524ab-128">In the one BizTalk server topology, three host instances are sharing the BizTalk computer resources.</span></span> <span data-ttu-id="524ab-129">2 つの BizTalk server トポロジより多くのスループットが実現される別のサーバーに、送信ホストが区切られています。</span><span class="sxs-lookup"><span data-stu-id="524ab-129">In the two BizTalk server topology, the transmit host is separated onto a different server, which achieves more throughput.</span></span>  
  
## <a name="considerations-when-scaling-out-the-biztalk-tier"></a><span data-ttu-id="524ab-130">スケーリング時の考慮事項は、BizTalk 層を Out します。</span><span class="sxs-lookup"><span data-stu-id="524ab-130">Considerations When Scaling Out the BizTalk Tier</span></span>  
 <span data-ttu-id="524ab-131">別の BizTalk Server コンピューターを追加する前に、次の質問を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="524ab-131">You must consider the following questions before you add another BizTalk Server computer:</span></span>  
  
#### <a name="how-do-i-configure-the-system-for-load-balancing-and-fault-tolerance-when-i-scale-out-the-biztalk-tier"></a><span data-ttu-id="524ab-132">BizTalk 層をスケールする場合に負荷分散およびフォールト トレランスのシステムを構成する方法はありますか</span><span class="sxs-lookup"><span data-stu-id="524ab-132">How do I configure the system for load balancing and fault tolerance when I scale out the BizTalk tier?</span></span>  
 <span data-ttu-id="524ab-133">負荷分散およびフォールト トレランスの選択は、シナリオで使用されているアダプターによって異なります。</span><span class="sxs-lookup"><span data-stu-id="524ab-133">The selection of load balancing and fault tolerance technology depends on the adapter that is being used in the scenario.</span></span> <span data-ttu-id="524ab-134">SOAP および HTTP アダプターでは、NLB を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="524ab-134">For SOAP and HTTP adapters, the recommended way is to use NLB.</span></span> <span data-ttu-id="524ab-135">詳細については、NLB のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="524ab-135">Refer to NLB documentation for more details.</span></span>  
  
#### <a name="how-do-i-refactor-the-host-instances"></a><span data-ttu-id="524ab-136">ホスト インスタンスをリファクタリングする方法は?</span><span class="sxs-lookup"><span data-stu-id="524ab-136">How do I refactor the host instances?</span></span>  
 <span data-ttu-id="524ab-137">BizTalk 層をスケールする場合は、ホスト インスタンスをリファクタリングする方法を決定する 1 つルールがありません。</span><span class="sxs-lookup"><span data-stu-id="524ab-137">There is no one rule to determine how you should refactor the host instances when you scale out the BizTalk tier.</span></span> <span data-ttu-id="524ab-138">ホスト インスタンスをファクタリングする時期は、シナリオの複雑さによって異なります。</span><span class="sxs-lookup"><span data-stu-id="524ab-138">When you factor the host instances depends on the complexity of scenario.</span></span> <span data-ttu-id="524ab-139">次は、ホスト インスタンスをファクタリングする方法をいくつかの例に示します。</span><span class="sxs-lookup"><span data-stu-id="524ab-139">Following are some examples how to factor the host instances.</span></span>  
  
##### <a name="scenario-1"></a><span data-ttu-id="524ab-140">シナリオ 1</span><span class="sxs-lookup"><span data-stu-id="524ab-140">Scenario 1</span></span>  
 <span data-ttu-id="524ab-141">1 つの BizTalk server 構成では、送受信を行い、ホスト インスタンスが同じコンピューター上に送信します。</span><span class="sxs-lookup"><span data-stu-id="524ab-141">One BizTalk server configuration, and receive and transmit host instances are on the same computer.</span></span>  
  
 <span data-ttu-id="524ab-142">CPU のボトルネックがあると仮定します。</span><span class="sxs-lookup"><span data-stu-id="524ab-142">Assume there is a CPU bottleneck.</span></span> <span data-ttu-id="524ab-143">グループに別の同等の BizTalk コンピューターを追加するスケール アウト、ホスト インスタンスをファクタリングする 2 つの方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="524ab-143">You add another identical BizTalk computer to the group to scale-out, giving you two ways to factor the host instances.</span></span>  
  
 <span data-ttu-id="524ab-144">この問題を解決する 2 つを次に示します。</span><span class="sxs-lookup"><span data-stu-id="524ab-144">Here are two solutions to this problem:</span></span>  
  
- <span data-ttu-id="524ab-145">**解決策 1**:このシナリオでファクタリングの最も簡単な方法では、ファクタリングするホスト インスタンス最初のコンピューターから 2 番目のコンピューターに複製します。</span><span class="sxs-lookup"><span data-stu-id="524ab-145">**Solution 1**: The easiest way of factoring in this scenario is to clone the host instance factoring from first computer to second computer.</span></span> <span data-ttu-id="524ab-146">そのため、2 番目のコンピューターには、最初の正確なコピー機能性の面でどちらも持つことができますも受信および送信ホスト。</span><span class="sxs-lookup"><span data-stu-id="524ab-146">So, the second computer is an exact copy of the first in term of functionality; it can also have both receive and send hosts.</span></span> <span data-ttu-id="524ab-147">CPU リソースが 2 倍とは、その他のボトルネックがないと仮定すると、スケール ファクターは 2 を取得可能性があります。</span><span class="sxs-lookup"><span data-stu-id="524ab-147">Assuming there is no other bottleneck, you may get a scaling factor of 2 as the CPU resources are doubled.</span></span>  
  
- <span data-ttu-id="524ab-148">**解決策 2**:ホスト インスタンスをファクタリングする別の方法を受信を特定し、別のコンピューターに関数を送信します。</span><span class="sxs-lookup"><span data-stu-id="524ab-148">**Solution 2**: Another way to factor the host instances is to isolate the receive and send functions onto different computers.</span></span> <span data-ttu-id="524ab-149">したがって、BizTalk server の 1 つは、受信用と送信の他にです。</span><span class="sxs-lookup"><span data-stu-id="524ab-149">So, one of the BizTalk servers is dedicated for receiving and other for sending.</span></span>  
  
  <span data-ttu-id="524ab-150">**解決策 1 と解決方法 2 の比較**</span><span class="sxs-lookup"><span data-stu-id="524ab-150">**Comparing Solution 1 and Solution 2**</span></span>  
  
  <span data-ttu-id="524ab-151">ソリューション 1 では、シングル BTS 構成からホスト インスタンスの数が倍になります。</span><span class="sxs-lookup"><span data-stu-id="524ab-151">In solution 1, the number of host instances is doubled from 1 BTS configuration.</span></span> <span data-ttu-id="524ab-152">これは、SQL server ロックの競合が増加することを意味します。</span><span class="sxs-lookup"><span data-stu-id="524ab-152">This means that lock contention on the SQL server will increase.</span></span> <span data-ttu-id="524ab-153">ロックの競合量が増えると、スケール ファクターが決まります。</span><span class="sxs-lookup"><span data-stu-id="524ab-153">How much it increases in lock contention will determine the scaling factor.</span></span> <span data-ttu-id="524ab-154">ロックの競合がボトルネックとなることの制限範囲内にある場合は、スケール ファクターは 2 を表示できます。</span><span class="sxs-lookup"><span data-stu-id="524ab-154">If the lock contention is well within limits of becoming a bottleneck, you can see a scaling factor of 2.</span></span>  
  
  <span data-ttu-id="524ab-155">解決方法 2 の利点は、SQL server のロックの競合の解決方法 1 より小さいをする必要がありますので、2 つのホスト インスタンスがあることです。</span><span class="sxs-lookup"><span data-stu-id="524ab-155">The advantage of solution 2 is that you have only two host instances, so the lock contention on the SQL server should be less compared to solution 1.</span></span> <span data-ttu-id="524ab-156">ただし、スケール ファクターは、受信の複雑さに完全に依存し、送信ホスト インスタンス。</span><span class="sxs-lookup"><span data-stu-id="524ab-156">But, the scaling factor depends completely on the complexity of the receive and send host instances.</span></span> <span data-ttu-id="524ab-157">解決方法 2 では、次の場合を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="524ab-157">Consider the following cases in solution 2:</span></span>  
  
  <span data-ttu-id="524ab-158">ある両方、受信および送信ホスト インスタンスが均等に負荷と 1 つの BizTalk server トポロジで、CPU の 50% を使用して、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="524ab-158">Assume that both the receive and transmit host instances are equally intensive and they each use 50% of the CPU in the one BizTalk server topology.</span></span> <span data-ttu-id="524ab-159">2 つの BizTalk server トポロジでは、送信ホスト インスタンスを別のコンピューターに移動し、これで、受信し、送信の両方が倍精度浮動小数点のリソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="524ab-159">In the two BizTalk server topology, you move the transmit host instance to different computer, and now both receive and transmit get double the resources.</span></span> <span data-ttu-id="524ab-160">これにより、スケール ファクターは 2、他のボトルネックがないと仮定するとが提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="524ab-160">This should provide a scaling factor of 2, assuming that there is no other bottleneck.</span></span> <span data-ttu-id="524ab-161">この例は、les ロックの競合のためだけの 2 つのホスト インスタンスがあるため、解決方法 1 よりも優れています。</span><span class="sxs-lookup"><span data-stu-id="524ab-161">This case is better than Solution 1 because there are only two host instances and hence les lock contention.</span></span>  
  
  <span data-ttu-id="524ab-162">送信するとしますが、受信よりも方法にかかっているし、1 つの BizTalk server トポロジで 80% の CPU リソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="524ab-162">Assume that transmit is way more intensive than receive, and uses 80% CPU resources in the one BizTalk server topology.</span></span> <span data-ttu-id="524ab-163">別のコンピューターに送信ホスト インスタンスを移動することでは、最大のスケール ファクターは 1.2 になりますのでのみの 20% 以上の CPU リソースを行えます。</span><span class="sxs-lookup"><span data-stu-id="524ab-163">By moving the transmit host instance to another machine, you gain only 20% more CPU resources so the maximum scaling factor will be 1.2.</span></span> <span data-ttu-id="524ab-164">さらに、受信ホスト インスタンスを使用してコンピューターは、スケール アウトの利点ははるかに少ないために、のみの 20 ~ 30 %cpu リソースを使用しません。</span><span class="sxs-lookup"><span data-stu-id="524ab-164">Moreover, the computer with the receive host instance will use only 20-30% CPU resources so the advantage of scaling-out is much less.</span></span>  
  
  <span data-ttu-id="524ab-165">次の 4 つの BizTalk サーバーがある次の図を検討してください。</span><span class="sxs-lookup"><span data-stu-id="524ab-165">Consider the following figure that has four BizTalk servers.</span></span> <span data-ttu-id="524ab-166">各コンピューターが受信と送信、各型の 4 つのホスト インスタンスの合計を提供するには (受信し、送信) します。</span><span class="sxs-lookup"><span data-stu-id="524ab-166">Each computer is both receiver and sender, giving you a  total of four host instances of each type (receive and transmit).</span></span>  
  
  <span data-ttu-id="524ab-167">![Re&#45;ホスト インスタンスをファクタリング](../core/media/refactoringhostinstances.gif "RefactoringHostinstances")</span><span class="sxs-lookup"><span data-stu-id="524ab-167">![Re&#45;factoring host instances](../core/media/refactoringhostinstances.gif "RefactoringHostinstances")</span></span>  
  
  <span data-ttu-id="524ab-168">このトポロジは、最適できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="524ab-168">This topology might not be the best possible one possible.</span></span> <span data-ttu-id="524ab-169">シナリオの複雑さに応じてその他のファクタリングの順列をテストすることも必要があります。</span><span class="sxs-lookup"><span data-stu-id="524ab-169">You should also test other factoring permutations, depending on the complexity of scenario.</span></span> <span data-ttu-id="524ab-170">例 :</span><span class="sxs-lookup"><span data-stu-id="524ab-170">For example:</span></span>  
  
- <span data-ttu-id="524ab-171">受信するための 2 台のコンピューターと送信用に専用です。</span><span class="sxs-lookup"><span data-stu-id="524ab-171">Dedicate two computers for receiving and  two for transmitting.</span></span> <span data-ttu-id="524ab-172">こうと、受信し、送信は均等に負荷がかかりますが、最適な拡張します。</span><span class="sxs-lookup"><span data-stu-id="524ab-172">This will give you the best possible scaling when both receive and send are equally intensive.</span></span>  
  
- <span data-ttu-id="524ab-173">専用用の 3 つの受信と送信のいずれかの受信が送信よりもかかっている場合。</span><span class="sxs-lookup"><span data-stu-id="524ab-173">Dedicate three computersfor receiving and one for transmitting, if receiving is more intensive than transmit.</span></span>  
  
- <span data-ttu-id="524ab-174">1 台のコンピューターの受信と送信の受信よりもかかってがない場合に送信するための 3 つ専用にします。</span><span class="sxs-lookup"><span data-stu-id="524ab-174">Dedicate one computer for receive and three for transmitting if transmitting is more intensive than receive.</span></span>  
  
  <span data-ttu-id="524ab-175">すべてのシナリオでは、メッセージ ボックス データベースでの競合の削減、同じの使用時に、コンピューター リソースを最大限ように各ホストのホスト インスタンスの数を最小限にするをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="524ab-175">In all scenarios, it is recommended that you minimize the number of host instances of each host so that contention on the MessageBox database is reduced and at the same time use the computer resources are use to the fullest.</span></span> <span data-ttu-id="524ab-176">最適なファクタリングは、シナリオの複雑さとボトルネックの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="524ab-176">The best factoring permutation depends on the complexity of scenario and type of bottleneck.</span></span> <span data-ttu-id="524ab-177">順列を確定する前にファクタリングを必ずテストします。</span><span class="sxs-lookup"><span data-stu-id="524ab-177">Always test your factoring before you finalize a permutation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="524ab-178">参照</span><span class="sxs-lookup"><span data-stu-id="524ab-178">See Also</span></span>  
 <span data-ttu-id="524ab-179">[BizTalk Server 層のスケール アップ](../core/scaling-up-the-biztalk-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="524ab-179">[Scaling Up the BizTalk Server Tier](../core/scaling-up-the-biztalk-server-tier.md) </span></span>  
 <span data-ttu-id="524ab-180">[SQL Server 層のスケール アップ](../core/scaling-up-the-sql-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="524ab-180">[Scaling Up the SQL Server Tier](../core/scaling-up-the-sql-server-tier.md) </span></span>  
 <span data-ttu-id="524ab-181">[SQL Server 層のスケール アウト](../core/scaling-out-the-sql-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="524ab-181">[Scaling Out the SQL Server Tier](../core/scaling-out-the-sql-server-tier.md) </span></span>  
 <span data-ttu-id="524ab-182">[受信ホスト スケール アウト](../core/scaled-out-receiving-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="524ab-182">[Scaled-Out Receiving Hosts](../core/scaled-out-receiving-hosts.md) </span></span>  
 <span data-ttu-id="524ab-183">[スケール アウトされた処理ホスト](../core/scaled-out-processing-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="524ab-183">[Scaled-Out Processing Hosts](../core/scaled-out-processing-hosts.md) </span></span>  
 <span data-ttu-id="524ab-184">[スケール アウトされた送信ホスト](../core/scaled-out-sending-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="524ab-184">[Scaled-Out Sending Hosts](../core/scaled-out-sending-hosts.md) </span></span>  
 <span data-ttu-id="524ab-185">[Windows Server クラスターを使用して BizTalk Server Hosts2 の高可用性を実現するには](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="524ab-185">[Using Windows Server Cluster to Provide High Availability for BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span></span>  
 <span data-ttu-id="524ab-186">[スケール アウト データベース](../core/scaled-out-databases.md) </span><span class="sxs-lookup"><span data-stu-id="524ab-186">[Scaled-Out Databases](../core/scaled-out-databases.md) </span></span>  
 [<span data-ttu-id="524ab-187">BizTalk Server データベースのクラスタリング</span><span class="sxs-lookup"><span data-stu-id="524ab-187">Clustering the BizTalk Server Databases</span></span>](../core/clustering-the-biztalk-server-databases1.md)