---
title: 既定の退避プロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 68c59def-d73b-4880-9884-ccbe5d982f4b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 907bd9f9b47db10a199f5a93a828558dfb3ae210
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981963"
---
# <a name="dehydration-default-properties"></a><span data-ttu-id="05e2e-102">既定の退避プロパティ</span><span class="sxs-lookup"><span data-stu-id="05e2e-102">Dehydration Default Properties</span></span>
<span data-ttu-id="05e2e-103">退避プロパティの名前とその既定値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="05e2e-103">Following are the names of the dehydration properties and their default values.</span></span> <span data-ttu-id="05e2e-104">これらのプロパティは、[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] を使用するか、または XML として BizTalk 構成ファイル (BTSNTSvc.exe.config または BTSNTSvc64.exe.config) で構成可能です。</span><span class="sxs-lookup"><span data-stu-id="05e2e-104">These properties are configurable in [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] or as XML in the BizTalk configuration file (BTSNTSvc.exe.config or BTSNTSvc64.exe.config).</span></span> <span data-ttu-id="05e2e-105">BizTalk 構成ファイルの値が先に適用されます。</span><span class="sxs-lookup"><span data-stu-id="05e2e-105">The values in the BizTalk configuration file are applied first.</span></span> <span data-ttu-id="05e2e-106">次に、[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] の設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="05e2e-106">Then, the [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] settings are applied.</span></span> <span data-ttu-id="05e2e-107">退避プロパティは、オーケストレーションを含んでいるすべてのホスト インスタンスの開始時に読み取られます。</span><span class="sxs-lookup"><span data-stu-id="05e2e-107">The dehydration properties are read when all host instances containing an orchestration start.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="05e2e-108">すべてのオーケストレーション設定が [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] で公開されているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="05e2e-108">Not all orchestrations settings are exposed in [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)].</span></span> <span data-ttu-id="05e2e-109">これらの設定については、BizTalk 構成ファイル (BTSNTSvc.exe.config または BTSNTSvc64.exe.config) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="05e2e-109">For these settings, the BizTalk configuration file (BTSNTSvc.exe.config or BTSNTSvc64.exe.config) is used.</span></span> <span data-ttu-id="05e2e-110">BizTalk 構成ファイルを使用する場合、多くのプロパティは一覧に表示されません。</span><span class="sxs-lookup"><span data-stu-id="05e2e-110">When using the BizTalk configuration file, many properties are not listed.</span></span> <span data-ttu-id="05e2e-111">これらのプロパティおよび既定値は、構成ファイルで明示的に指定されていない場合でも常に適用されています。</span><span class="sxs-lookup"><span data-stu-id="05e2e-111">These properties and their default values are still applied, even if they are not explicitly specified in the configuration file.</span></span>  
  
 <span data-ttu-id="05e2e-112">既定値を変更するには、[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] を使用するか、BizTalk 構成ファイルに明示的に追加します。</span><span class="sxs-lookup"><span data-stu-id="05e2e-112">To change the default values, you can use [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] or explicitly add them to the BizTalk configuration file.</span></span> <span data-ttu-id="05e2e-113">詳細については、次を参照してください。[設定ダッシュ ボードの BizTalk Server のパフォーマンス チューニングを使用して](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)と[BTSNTSvc.exe.config ファイル](../core/btsntsvc-exe-config-file.md)します。</span><span class="sxs-lookup"><span data-stu-id="05e2e-113">For more information, see [Using Settings Dashboard for BizTalk Server Performance Tuning](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md) and [BTSNTSvc.exe.config File](../core/btsntsvc-exe-config-file.md).</span></span>  
  
 <span data-ttu-id="05e2e-114">**退避**</span><span class="sxs-lookup"><span data-stu-id="05e2e-114">**Dehydration**</span></span>  
  
- <span data-ttu-id="05e2e-115">**MaxThreshold** = 1800</span><span class="sxs-lookup"><span data-stu-id="05e2e-115">**MaxThreshold** = 1800</span></span>  
  
- <span data-ttu-id="05e2e-116">**MinThreshold** = 1</span><span class="sxs-lookup"><span data-stu-id="05e2e-116">**MinThreshold** = 1</span></span>  
  
- <span data-ttu-id="05e2e-117">**ConstantThreshold** =-1</span><span class="sxs-lookup"><span data-stu-id="05e2e-117">**ConstantThreshold** = -1</span></span>  
  
  <span data-ttu-id="05e2e-118">**VirtualMemoryThrottlingCriteria**</span><span class="sxs-lookup"><span data-stu-id="05e2e-118">**VirtualMemoryThrottlingCriteria**</span></span>  
  
- <span data-ttu-id="05e2e-119">**OptimalUsage** 900 を =</span><span class="sxs-lookup"><span data-stu-id="05e2e-119">**OptimalUsage** = 900</span></span>  
  
- <span data-ttu-id="05e2e-120">**MaximalUsage** 1300 を =</span><span class="sxs-lookup"><span data-stu-id="05e2e-120">**MaximalUsage** =  1300</span></span>  
  
- <span data-ttu-id="05e2e-121">**IsActive** = true</span><span class="sxs-lookup"><span data-stu-id="05e2e-121">**IsActive** = true</span></span>  
  
  <span data-ttu-id="05e2e-122">**PrivateMemoryThrottlingCriteria**</span><span class="sxs-lookup"><span data-stu-id="05e2e-122">**PrivateMemoryThrottlingCriteria**</span></span>  
  
- <span data-ttu-id="05e2e-123">**OptimalUsage** = 50</span><span class="sxs-lookup"><span data-stu-id="05e2e-123">**OptimalUsage** = 50</span></span>  
  
- <span data-ttu-id="05e2e-124">**MaximalUsage** = 350</span><span class="sxs-lookup"><span data-stu-id="05e2e-124">**MaximalUsage** =  350</span></span>  
  
- <span data-ttu-id="05e2e-125">**IsActive** = true</span><span class="sxs-lookup"><span data-stu-id="05e2e-125">**IsActive** = true</span></span>  
  
  <span data-ttu-id="05e2e-126">**PhysicalMemoryThrottlingCriteria**</span><span class="sxs-lookup"><span data-stu-id="05e2e-126">**PhysicalMemoryThrottlingCriteria**</span></span>  
  
- <span data-ttu-id="05e2e-127">**OptimalUsage** = 90</span><span class="sxs-lookup"><span data-stu-id="05e2e-127">**OptimalUsage** = 90</span></span>  
  
- <span data-ttu-id="05e2e-128">**MaximalUsage** = 95</span><span class="sxs-lookup"><span data-stu-id="05e2e-128">**MaximalUsage** =  95</span></span>  
  
- <span data-ttu-id="05e2e-129">**IsActive** = false</span><span class="sxs-lookup"><span data-stu-id="05e2e-129">**IsActive** = false</span></span>  
  
  <span data-ttu-id="05e2e-130">次に、これらの各プロパティについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="05e2e-130">Each of these properties is described in detail next.</span></span>  
  
## <a name="dehydration"></a><span data-ttu-id="05e2e-131">退避</span><span class="sxs-lookup"><span data-stu-id="05e2e-131">Dehydration</span></span>  
 <span data-ttu-id="05e2e-132">**MaxThreshold**と**MinThreshold**上には、下位の境界をオーケストレーションが退避されるまで (つまり、受信、待ち受け、または遅延によってブロックされている) サブスクリプションでブロックされて時間 (秒)。</span><span class="sxs-lookup"><span data-stu-id="05e2e-132">**MaxThreshold** and **MinThreshold** are the upper and lower bounds, in seconds, of the time that an orchestration can be blocked at a subscription (that is, blocked by a receive, listen, or delay) before being dehydrated.</span></span> <span data-ttu-id="05e2e-133">あります値を実行時に計算される、という**TestThreshold**、秒単位で、その値が**MinThreshold**と**MaxThreshold**します。</span><span class="sxs-lookup"><span data-stu-id="05e2e-133">There will also be a value calculated at run-time, called **TestThreshold**, and its value, measured in seconds, is between **MinThreshold** and **MaxThreshold**.</span></span>  
  
 <span data-ttu-id="05e2e-134">既定の-1 以外の値を設定するかどうかは**ConstantThreshold**、実行時値されません**TestThreshold**します。</span><span class="sxs-lookup"><span data-stu-id="05e2e-134">If you set a value besides the default of -1 for **ConstantThreshold**, there will not be a run-time value **TestThreshold**.</span></span> <span data-ttu-id="05e2e-135">サブスクリプションでオーケストレーションがブロックされているし、オーケストレーションのすべてのインスタンスをサブスクリプションでブロックされているどのくらいの期間の履歴がの値より大きい**TestThreshold**オーケストレーションは、退避します。</span><span class="sxs-lookup"><span data-stu-id="05e2e-135">When an orchestration is blocked at a subscription, and the history of how long all instances of that orchestration have been blocked at that subscription is greater than the value of **TestThreshold**, then the orchestration will dehydrate.</span></span> <span data-ttu-id="05e2e-136">それ以外の場合、履歴がある場合より小さい**TestThreshold**値は、オーケストレーションは退避されません。</span><span class="sxs-lookup"><span data-stu-id="05e2e-136">Otherwise, if the history is less than **TestThreshold** value the orchestration will not dehydrate.</span></span> <span data-ttu-id="05e2e-137">また、場合でも、履歴、退避は行われません、現在のブロック時間が 2 に達する場合を示します<em>\**TestThreshold</em>*、退避が行われます。</span><span class="sxs-lookup"><span data-stu-id="05e2e-137">Also, even if the history indicates that dehydration will not take place, if the current blocking time reaches 2<em>\**TestThreshold</em>*, then the dehydration will take place.</span></span> <span data-ttu-id="05e2e-138">履歴は秒単位の最後の 10 待機時間の平均、または、待機時間の数が 10 未満の場合は履歴内に存在する待機時間の数の平均によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="05e2e-138">The history is defined by the average of the last 10 waiting times in seconds, or the average of however many waiting times there are in the history if the waiting times are less than 10.</span></span>  
  
 <span data-ttu-id="05e2e-139">ときの値**TestThreshold**に向かって傾向**MinThreshold**メモリ使用量が増加すると呼び出されます「メモリ ベースの退避制限します」。</span><span class="sxs-lookup"><span data-stu-id="05e2e-139">When the value of **TestThreshold** tends toward **MinThreshold** as memory usage increases, it is called "memory based dehydration throttling."</span></span> <span data-ttu-id="05e2e-140">メモリ ベースの退避制限では、より多くのオーケストレーション インスタンスをライブにできます。これらのインスタンスのいずれかがブロックされて作業を待機 (メッセージの待機または遅延) するとき、これらを退避させたりメモリから消去したりできるためです。</span><span class="sxs-lookup"><span data-stu-id="05e2e-140">Memory-based dehydration throttling allows more orchestration instances to be live because when any of them are blocked waiting for work (that is, waiting for a message or a delay), they can be dehydrated and taken out of memory.</span></span> <span data-ttu-id="05e2e-141">**TestThreshold**が 1 ずつ減少関数のメモリ使用量、メモリ使用量に反比例します。</span><span class="sxs-lookup"><span data-stu-id="05e2e-141">**TestThreshold** is a monotonically decreasing function of memory usage, it is inversely proportional to memory usage.</span></span>  
  
 <span data-ttu-id="05e2e-142">次に、Dehydration の各プロパティの説明を示します。</span><span class="sxs-lookup"><span data-stu-id="05e2e-142">Following are descriptions of the individual Dehydration properties:</span></span>  
  
-   <span data-ttu-id="05e2e-143">**MaxThreshold**: オーケストレーションが退避される前に、サブスクリプションでブロックされて時間 (秒) の上限。</span><span class="sxs-lookup"><span data-stu-id="05e2e-143">**MaxThreshold**: the upper bounds, in seconds, of the time that an orchestration can be blocked at a subscription before being dehydrated.</span></span>  
  
-   <span data-ttu-id="05e2e-144">**MinThreshold**: オーケストレーションが退避される前に、サブスクリプションでブロックされて時間 (秒) の下限。</span><span class="sxs-lookup"><span data-stu-id="05e2e-144">**MinThreshold**: the lower bounds, in seconds, of the time that an orchestration can be blocked at a subscription before being dehydrated.</span></span>  
  
-   <span data-ttu-id="05e2e-145">**ConstantThreshold**: 動的なしきい値は、通常、指定した最小値と最大値の間で変動します。</span><span class="sxs-lookup"><span data-stu-id="05e2e-145">**ConstantThreshold**: the dynamic threshold, which usually fluctuates between the minimum and maximum values specified.</span></span> <span data-ttu-id="05e2e-146">ただし、このプロパティを設定するとしきい値を固定することができます。</span><span class="sxs-lookup"><span data-stu-id="05e2e-146">However, you can make the threshold a fixed value by setting this property.</span></span> <span data-ttu-id="05e2e-147">値 -1 は、固定しきい値を使用しないようにエンジンに通知します。</span><span class="sxs-lookup"><span data-stu-id="05e2e-147">A value of -1 tells the engine not to use a constant threshold.</span></span> <span data-ttu-id="05e2e-148">ベースの退避制限が無効になりますので、このプロパティを-1 以外の値に設定はありません。</span><span class="sxs-lookup"><span data-stu-id="05e2e-148">Don't set this property to a value other than -1 because it will disable dehydration based throttling.</span></span>  
  
## <a name="virtualmemorythrottlingcriteria"></a><span data-ttu-id="05e2e-149">VirtualMemoryThrottlingCriteria</span><span class="sxs-lookup"><span data-stu-id="05e2e-149">VirtualMemoryThrottlingCriteria</span></span>  
 <span data-ttu-id="05e2e-150">現在は、アンマネージ ヒープの断片化のため、仮想メモリが 32 ビット マシンのボトルネックとなる可能性があります。このため、このリソースも制限する必要があります。</span><span class="sxs-lookup"><span data-stu-id="05e2e-150">Currently, virtual memory can become a bottleneck on 32-bit machines due to unmanaged heap fragmentation, so you should throttle by this resource as well.</span></span> <span data-ttu-id="05e2e-151">/3GB が設定されている場合、またはホストが 64 ビット プラットフォーム上で実行されている場合は、再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="05e2e-151">You should re-configure if /3GB is set or if the hosts are running on a 64-bit platform.</span></span> <span data-ttu-id="05e2e-152">最適使用量と最大使用量は MB 単位です。</span><span class="sxs-lookup"><span data-stu-id="05e2e-152">Optimal and maximal usages are in MB.</span></span>  
  
 <span data-ttu-id="05e2e-153">次に、VirtualMemoryThrottlingCriteria の各プロパティの説明を示します。</span><span class="sxs-lookup"><span data-stu-id="05e2e-153">Following are descriptions of the individual VirtualMemoryThrottlingCriteria properties:</span></span>  
  
-   <span data-ttu-id="05e2e-154">**OptimalUsage**: の退避制限を有効にするが、仮想メモリ使用量。</span><span class="sxs-lookup"><span data-stu-id="05e2e-154">**OptimalUsage**: The amount of virtual memory usage at which dehydration throttling begins to take effect.</span></span> <span data-ttu-id="05e2e-155">この時点では、 **TestThreshold** 、値を持つ**MaxThreshold**メモリ使用量を超える**OptimalUsage**により**TestThreshold**をより小さい**MaxThreshold**します。</span><span class="sxs-lookup"><span data-stu-id="05e2e-155">At this point, **TestThreshold** has the value **MaxThreshold** and any memory usage greater than **OptimalUsage** causes **TestThreshold** to be less than **MaxThreshold**.</span></span>  
  
-   <span data-ttu-id="05e2e-156">**MaximalUsage**: 仮想メモリ使用量の制限が最大時点では、退避の量。</span><span class="sxs-lookup"><span data-stu-id="05e2e-156">**MaximalUsage**: The amount of virtual memory usage at which dehydration throttling is at a maximum.</span></span> <span data-ttu-id="05e2e-157">この時点では、 **TestThreshold** 、値を持つ**MinThreshold**メモリ使用量より小さい**MaximalUsage**により**TestThreshold**超える**MinThreshold**します。</span><span class="sxs-lookup"><span data-stu-id="05e2e-157">At this point, **TestThreshold** has the value **MinThreshold** and any memory usage less than **MaximalUsage** causes **TestThreshold** to be greater than **MinThreshold**.</span></span>  
  
-   <span data-ttu-id="05e2e-158">**IsActive**: 仮想メモリの制限がアクティブかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="05e2e-158">**IsActive**: A boolean value indicating if virtual memory throttling is active.</span></span>  
  
## <a name="privatememorythrottlingcriteria"></a><span data-ttu-id="05e2e-159">PrivateMemoryThrottlingCriteria</span><span class="sxs-lookup"><span data-stu-id="05e2e-159">PrivateMemoryThrottlingCriteria</span></span>  
 <span data-ttu-id="05e2e-160">このプロパティは制限のために役立つ条件ですが、コンピューター上で他の Windows サービスが実行されているかどうかによって適切な値が異なります。</span><span class="sxs-lookup"><span data-stu-id="05e2e-160">This property is a useful criterion for throttling, but appropriate values depend on whether the computer is running other windows services.</span></span> <span data-ttu-id="05e2e-161">コンピューターに大量のメモリがあり、他の Windows サービスと共有していない場合、これらの値を大幅に増やすことができます。</span><span class="sxs-lookup"><span data-stu-id="05e2e-161">If the computer has a lot of memory and is not being shared with other windows services, then you can increase these values significantly.</span></span>  
  
 <span data-ttu-id="05e2e-162">次に、PrivateMemoryThrottlingCriteria の各プロパティの説明を示します。</span><span class="sxs-lookup"><span data-stu-id="05e2e-162">Following are descriptions of the individual PrivateMemoryThrottlingCriteria properties:</span></span>  
  
-   <span data-ttu-id="05e2e-163">**OptimalUsage**: の退避制限が適用されますを有効にする (mb) のプライベート メモリ使用量。</span><span class="sxs-lookup"><span data-stu-id="05e2e-163">**OptimalUsage**: the amount of private memory usage, in MB, at which dehydration throttling begins to take effect.</span></span> <span data-ttu-id="05e2e-164">この時点で**TestThreshold** 、値を持つ**MaxThreshold**メモリ使用量を超える**OptimalUsage**により**TestThreshold**をより小さい**MaxThreshold**します。</span><span class="sxs-lookup"><span data-stu-id="05e2e-164">At this point **TestThreshold** has the value **MaxThreshold** and any memory usage greater than **OptimalUsage** causes **TestThreshold** to be less than **MaxThreshold**.</span></span>  
  
-   <span data-ttu-id="05e2e-165">**MaximalUsage**: mb、最大で退避制限が、プライベート メモリ使用量。</span><span class="sxs-lookup"><span data-stu-id="05e2e-165">**MaximalUsage**: the amount of private memory usage, in MB, at which dehydration throttling is at a maximum.</span></span> <span data-ttu-id="05e2e-166">この時点で**TestThreshold** 、値を持つ**MinThreshold**メモリ使用量より小さい**MaximalUsage**により**TestThreshold**超える**MinThreshold**します。</span><span class="sxs-lookup"><span data-stu-id="05e2e-166">At this point **TestThreshold** has the value **MinThreshold** and any memory usage less than **MaximalUsage** causes **TestThreshold** to be greater than **MinThreshold**.</span></span>  
  
-   <span data-ttu-id="05e2e-167">**IsActive**: プライベート メモリ制限がアクティブかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="05e2e-167">**IsActive**: a boolean value indicating if private memory throttling is active.</span></span>  
  
## <a name="physicalmemorythrottlingcriteria"></a><span data-ttu-id="05e2e-168">PhysicalMemoryThrottlingCriteria</span><span class="sxs-lookup"><span data-stu-id="05e2e-168">PhysicalMemoryThrottlingCriteria</span></span>  
 <span data-ttu-id="05e2e-169">メモリ使用量を MB 単位ではなくパーセンテージで表す、物理メモリ制限もあります。</span><span class="sxs-lookup"><span data-stu-id="05e2e-169">There is also a physical memory throttling where numbers are measured in percentage of memory used rather than MB.</span></span> <span data-ttu-id="05e2e-170">このプロパティは既定で無効になっていますが、必要に応じて有効にできます。</span><span class="sxs-lookup"><span data-stu-id="05e2e-170">This property is disabled by default, but you can enable if needed.</span></span>  
  
 <span data-ttu-id="05e2e-171">次に、PhysicalMemoryThrottlingCriteria の各プロパティの説明を示します。</span><span class="sxs-lookup"><span data-stu-id="05e2e-171">Following are descriptions of the individual PhysicalMemoryThrottlingCriteria properties:</span></span>  
  
-   <span data-ttu-id="05e2e-172">**OptimalUsage**: ホストのインスタンスに使用する物理メモリの最適なパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="05e2e-172">**OptimalUsage**: the optimum percentage of physical memory to use for the host instances.</span></span>  
  
-   <span data-ttu-id="05e2e-173">**MaximalUsage**: ホストのインスタンスに使用する物理メモリの最大パーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="05e2e-173">**MaximalUsage**: the maximum percentage of physical memory to use for the host instances.</span></span>  
  
-   <span data-ttu-id="05e2e-174">**IsActive**: 物理メモリの制限がアクティブなを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="05e2e-174">**IsActive**: boolean value indicating if physical memory throttling is active.</span></span>  
  
## <a name="dehydration-properties-behavior"></a><span data-ttu-id="05e2e-175">退避プロパティの動作</span><span class="sxs-lookup"><span data-stu-id="05e2e-175">Dehydration Properties Behavior</span></span>  
 <span data-ttu-id="05e2e-176">BizTalk Server はこれらの退避プロパティを使用して、オーケストレーションをいつ退避および復元するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="05e2e-176">BizTalk Server uses these dehydration properties to decide when to dehydrate and rehydrate orchestrations.</span></span> <span data-ttu-id="05e2e-177">標準の負荷状態では、既定の復元値で十分です。しかし、負荷が高い状態で実行していてパフォーマンス特性を変更する場合、自分でチューニングを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="05e2e-177">Under normal load, the default dehydration values are sufficient, but if you are running under heavy load and want to change performance characteristics, you should do the tuning yourself.</span></span>  
  
 <span data-ttu-id="05e2e-178">BizTalk Server の復元動作は、使用可能なメモリ量と使用されているメモリ量に完全に依存します。</span><span class="sxs-lookup"><span data-stu-id="05e2e-178">The dehydration behavior of BizTalk Server depends entirely on how much memory is available and how much memory is being used.</span></span> <span data-ttu-id="05e2e-179">復元動作は、メモリ量によって異なります。また、32 ビットと 64 ビットのホスト間のメモリ使用の違いによっても異なります。</span><span class="sxs-lookup"><span data-stu-id="05e2e-179">The dehydration behavior is different with different amounts of memory and differences in memory use between 32-bit and 64-bit hosts.</span></span>  
  
 <span data-ttu-id="05e2e-180">復元プロパティでは、オーケストレーション ホストのプライベート バイトと仮想バイトが、次のように識別されます。</span><span class="sxs-lookup"><span data-stu-id="05e2e-180">The dehydration properties distinguish between Private Bytes and Virtual Bytes for the orchestration host:</span></span>  
  
-   <span data-ttu-id="05e2e-181">**仮想バイト**します。</span><span class="sxs-lookup"><span data-stu-id="05e2e-181">**Virtual Bytes**.</span></span> <span data-ttu-id="05e2e-182">使用して、プロセス仮想アドレス空間のバイト単位の現在のサイズです。</span><span class="sxs-lookup"><span data-stu-id="05e2e-182">This is thecurrent size, in bytes, of the virtual address space the process is using.</span></span> <span data-ttu-id="05e2e-183">仮想アドレス空間を使用していても、ディスク ページまたはメイン メモリ ページを使用しているとは限りません。</span><span class="sxs-lookup"><span data-stu-id="05e2e-183">Use of virtual address space does not necessarily imply corresponding use of either disk or main memory pages.</span></span> <span data-ttu-id="05e2e-184">仮想空間は有限であり、プロセスではライブラリ読み込み機能を制限できます。</span><span class="sxs-lookup"><span data-stu-id="05e2e-184">Virtual space is finite, and the process can limit its ability to load libraries.</span></span>  
  
-   <span data-ttu-id="05e2e-185">**Private Bytes**します。</span><span class="sxs-lookup"><span data-stu-id="05e2e-185">**Private Bytes**.</span></span> <span data-ttu-id="05e2e-186">これは、このプロセスによって割り当てられ、他のプロセスと共有できないメモリの現在のサイズ (バイト単位) です。</span><span class="sxs-lookup"><span data-stu-id="05e2e-186">This is the current size, in bytes, of memory that this process has allocated that cannot be shared with other processes.</span></span>