---
title: "既定の退避プロパティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68c59def-d73b-4880-9884-ccbe5d982f4b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff78b1e096f1a73675ffc02550794f5a300f5614
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="dehydration-default-properties"></a><span data-ttu-id="77481-102">既定の退避プロパティ</span><span class="sxs-lookup"><span data-stu-id="77481-102">Dehydration Default Properties</span></span>
<span data-ttu-id="77481-103">退避プロパティの名前とその既定値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="77481-103">Following are the names of the dehydration properties and their default values.</span></span> <span data-ttu-id="77481-104">これらのプロパティは、[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] を使用するか、または XML として BizTalk 構成ファイル (BTSNTSvc.exe.config または BTSNTSvc64.exe.config) で構成可能です。</span><span class="sxs-lookup"><span data-stu-id="77481-104">These properties are configurable in [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] or as XML in the BizTalk configuration file (BTSNTSvc.exe.config or BTSNTSvc64.exe.config).</span></span> <span data-ttu-id="77481-105">BizTalk 構成ファイルの値が先に適用されます。</span><span class="sxs-lookup"><span data-stu-id="77481-105">The values in the BizTalk configuration file are applied first.</span></span> <span data-ttu-id="77481-106">次に、[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] の設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="77481-106">Then, the [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] settings are applied.</span></span> <span data-ttu-id="77481-107">退避プロパティは、オーケストレーションを含んでいるすべてのホスト インスタンスの開始時に読み取られます。</span><span class="sxs-lookup"><span data-stu-id="77481-107">The dehydration properties are read when all host instances containing an orchestration start.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="77481-108">すべてのオーケストレーション設定が [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] で公開されているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="77481-108">Not all orchestrations settings are exposed in [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)].</span></span> <span data-ttu-id="77481-109">これらの設定については、BizTalk 構成ファイル (BTSNTSvc.exe.config または BTSNTSvc64.exe.config) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="77481-109">For these settings, the BizTalk configuration file (BTSNTSvc.exe.config or BTSNTSvc64.exe.config) is used.</span></span> <span data-ttu-id="77481-110">BizTalk 構成ファイルを使用する場合、多くのプロパティは一覧に表示されません。</span><span class="sxs-lookup"><span data-stu-id="77481-110">When using the BizTalk configuration file, many properties are not listed.</span></span> <span data-ttu-id="77481-111">これらのプロパティおよび既定値は、構成ファイルで明示的に指定されていない場合でも常に適用されています。</span><span class="sxs-lookup"><span data-stu-id="77481-111">These properties and their default values are still applied, even if they are not explicitly specified in the configuration file.</span></span>  
  
 <span data-ttu-id="77481-112">既定値を変更するには、[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] を使用するか、BizTalk 構成ファイルに明示的に追加します。</span><span class="sxs-lookup"><span data-stu-id="77481-112">To change the default values, you can use [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] or explicitly add them to the BizTalk configuration file.</span></span> <span data-ttu-id="77481-113">詳細については、次を参照してください。[設定ダッシュ ボードの BizTalk Server のパフォーマンス チューニング](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)と[BTSNTSvc.exe.config ファイル](../core/btsntsvc-exe-config-file.md)です。</span><span class="sxs-lookup"><span data-stu-id="77481-113">For more information, see [Using Settings Dashboard for BizTalk Server Performance Tuning](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md) and [BTSNTSvc.exe.config File](../core/btsntsvc-exe-config-file.md).</span></span>  
  
 <span data-ttu-id="77481-114">**退避**</span><span class="sxs-lookup"><span data-stu-id="77481-114">**Dehydration**</span></span>  
  
-   <span data-ttu-id="77481-115">**MaxThreshold** 1800 を =</span><span class="sxs-lookup"><span data-stu-id="77481-115">**MaxThreshold** = 1800</span></span>  
  
-   <span data-ttu-id="77481-116">**MinThreshold** = 1</span><span class="sxs-lookup"><span data-stu-id="77481-116">**MinThreshold** = 1</span></span>  
  
-   <span data-ttu-id="77481-117">**ConstantThreshold** -1 を =</span><span class="sxs-lookup"><span data-stu-id="77481-117">**ConstantThreshold** = -1</span></span>  
  
 <span data-ttu-id="77481-118">**VirtualMemoryThrottlingCriteria**</span><span class="sxs-lookup"><span data-stu-id="77481-118">**VirtualMemoryThrottlingCriteria**</span></span>  
  
-   <span data-ttu-id="77481-119">**OptimalUsage** 900 を =</span><span class="sxs-lookup"><span data-stu-id="77481-119">**OptimalUsage** = 900</span></span>  
  
-   <span data-ttu-id="77481-120">**MaximalUsage** 1300 を =</span><span class="sxs-lookup"><span data-stu-id="77481-120">**MaximalUsage** =  1300</span></span>  
  
-   <span data-ttu-id="77481-121">**IsActive** = true</span><span class="sxs-lookup"><span data-stu-id="77481-121">**IsActive** = true</span></span>  
  
 <span data-ttu-id="77481-122">**PrivateMemoryThrottlingCriteria**</span><span class="sxs-lookup"><span data-stu-id="77481-122">**PrivateMemoryThrottlingCriteria**</span></span>  
  
-   <span data-ttu-id="77481-123">**OptimalUsage** 50 を =</span><span class="sxs-lookup"><span data-stu-id="77481-123">**OptimalUsage** = 50</span></span>  
  
-   <span data-ttu-id="77481-124">**MaximalUsage** 350 を =</span><span class="sxs-lookup"><span data-stu-id="77481-124">**MaximalUsage** =  350</span></span>  
  
-   <span data-ttu-id="77481-125">**IsActive** = true</span><span class="sxs-lookup"><span data-stu-id="77481-125">**IsActive** = true</span></span>  
  
 <span data-ttu-id="77481-126">**PhysicalMemoryThrottlingCriteria**</span><span class="sxs-lookup"><span data-stu-id="77481-126">**PhysicalMemoryThrottlingCriteria**</span></span>  
  
-   <span data-ttu-id="77481-127">**OptimalUsage** = 90</span><span class="sxs-lookup"><span data-stu-id="77481-127">**OptimalUsage** = 90</span></span>  
  
-   <span data-ttu-id="77481-128">**MaximalUsage** 95 を =</span><span class="sxs-lookup"><span data-stu-id="77481-128">**MaximalUsage** =  95</span></span>  
  
-   <span data-ttu-id="77481-129">**IsActive** = false</span><span class="sxs-lookup"><span data-stu-id="77481-129">**IsActive** = false</span></span>  
  
 <span data-ttu-id="77481-130">次に、これらの各プロパティについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="77481-130">Each of these properties is described in detail next.</span></span>  
  
## <a name="dehydration"></a><span data-ttu-id="77481-131">退避</span><span class="sxs-lookup"><span data-stu-id="77481-131">Dehydration</span></span>  
 <span data-ttu-id="77481-132">**MaxThreshold**と**MinThreshold**が、上限と下限で退避されるまで (つまり、受信、待ち受け、または遅延によってブロックされている) サブスクリプションでオーケストレーションがブロックされている時間 (秒)。</span><span class="sxs-lookup"><span data-stu-id="77481-132">**MaxThreshold** and **MinThreshold** are the upper and lower bounds, in seconds, of the time that an orchestration can be blocked at a subscription (that is, blocked by a receive, listen, or delay) before being dehydrated.</span></span> <span data-ttu-id="77481-133">あります値呼び出されて、実行時に計算**TestThreshold**、秒単位で、その値は、間と**MinThreshold**と**MaxThreshold**です。</span><span class="sxs-lookup"><span data-stu-id="77481-133">There will also be a value calculated at run-time, called **TestThreshold**, and its value, measured in seconds, is between **MinThreshold** and **MaxThreshold**.</span></span>  
  
 <span data-ttu-id="77481-134">既定の-1 以外の値を設定するかどうかは**ConstantThreshold**、実行時値されません**TestThreshold**です。</span><span class="sxs-lookup"><span data-stu-id="77481-134">If you set a value besides the default of -1 for **ConstantThreshold**, there will not be a run-time value **TestThreshold**.</span></span> <span data-ttu-id="77481-135">ときに、サブスクリプションでオーケストレーションがブロックされているし、そのサブスクリプションでそのオーケストレーションのすべてのインスタンスがブロックされた時間の履歴がの値より大きい**TestThreshold**オーケストレーションは、退避します。</span><span class="sxs-lookup"><span data-stu-id="77481-135">When an orchestration is blocked at a subscription, and the history of how long all instances of that orchestration have been blocked at that subscription is greater than the value of **TestThreshold**, then the orchestration will dehydrate.</span></span> <span data-ttu-id="77481-136">それ以外の場合は、履歴はより小さい**TestThreshold**値は、オーケストレーションは退避されません。</span><span class="sxs-lookup"><span data-stu-id="77481-136">Otherwise, if the history is less than **TestThreshold** value the orchestration will not dehydrate.</span></span> <span data-ttu-id="77481-137">また、場合でも、履歴を示します、退避は行われません、現在のブロック時間が 2 に達すると ***TestThreshold**、退避が行われます。</span><span class="sxs-lookup"><span data-stu-id="77481-137">Also, even if the history indicates that dehydration will not take place, if the current blocking time reaches 2***TestThreshold**, then the dehydration will take place.</span></span> <span data-ttu-id="77481-138">履歴は秒単位の最後の 10 待機時間の平均、または、待機時間の数が 10 未満の場合は履歴内に存在する待機時間の数の平均によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="77481-138">The history is defined by the average of the last 10 waiting times in seconds, or the average of however many waiting times there are in the history if the waiting times are less than 10.</span></span>  
  
 <span data-ttu-id="77481-139">ときに、値の**TestThreshold**に近づく**MinThreshold**メモリ使用量が増加するにつれて、呼び出された「メモリ ベースの退避制限します」。</span><span class="sxs-lookup"><span data-stu-id="77481-139">When the value of **TestThreshold** tends toward **MinThreshold** as memory usage increases, it is called "memory based dehydration throttling."</span></span> <span data-ttu-id="77481-140">メモリ ベースの退避制限では、より多くのオーケストレーション インスタンスをライブにできます。これらのインスタンスのいずれかがブロックされて作業を待機 (メッセージの待機または遅延) するとき、これらを退避させたりメモリから消去したりできるためです。</span><span class="sxs-lookup"><span data-stu-id="77481-140">Memory-based dehydration throttling allows more orchestration instances to be live because when any of them are blocked waiting for work (that is, waiting for a message or a delay), they can be dehydrated and taken out of memory.</span></span> <span data-ttu-id="77481-141">**TestThreshold**単調に減少する関数は、メモリ使用量がメモリ使用量に反比例します。</span><span class="sxs-lookup"><span data-stu-id="77481-141">**TestThreshold** is a monotonically decreasing function of memory usage, it is inversely proportional to memory usage.</span></span>  
  
 <span data-ttu-id="77481-142">次に、Dehydration の各プロパティの説明を示します。</span><span class="sxs-lookup"><span data-stu-id="77481-142">Following are descriptions of the individual Dehydration properties:</span></span>  
  
-   <span data-ttu-id="77481-143">**MaxThreshold**: 上限の境界、退避前に、サブスクリプションでオーケストレーションがブロックされている時間 (秒)。</span><span class="sxs-lookup"><span data-stu-id="77481-143">**MaxThreshold**: the upper bounds, in seconds, of the time that an orchestration can be blocked at a subscription before being dehydrated.</span></span>  
  
-   <span data-ttu-id="77481-144">**MinThreshold**: 下位の境界、退避前に、サブスクリプションでオーケストレーションがブロックされている時間 (秒)。</span><span class="sxs-lookup"><span data-stu-id="77481-144">**MinThreshold**: the lower bounds, in seconds, of the time that an orchestration can be blocked at a subscription before being dehydrated.</span></span>  
  
-   <span data-ttu-id="77481-145">**ConstantThreshold**: 動的なしきい値は、通常、最小値および最大値の間で変動します。</span><span class="sxs-lookup"><span data-stu-id="77481-145">**ConstantThreshold**: the dynamic threshold, which usually fluctuates between the minimum and maximum values specified.</span></span> <span data-ttu-id="77481-146">ただし、このプロパティを設定するとしきい値を固定することができます。</span><span class="sxs-lookup"><span data-stu-id="77481-146">However, you can make the threshold a fixed value by setting this property.</span></span> <span data-ttu-id="77481-147">値 -1 は、固定しきい値を使用しないようにエンジンに通知します。</span><span class="sxs-lookup"><span data-stu-id="77481-147">A value of -1 tells the engine not to use a constant threshold.</span></span> <span data-ttu-id="77481-148">ベースの退避制限が無効になりますので、このプロパティを-1 以外の値に設定しません。</span><span class="sxs-lookup"><span data-stu-id="77481-148">Don't set this property to a value other than -1 because it will disable dehydration based throttling.</span></span>  
  
## <a name="virtualmemorythrottlingcriteria"></a><span data-ttu-id="77481-149">VirtualMemoryThrottlingCriteria</span><span class="sxs-lookup"><span data-stu-id="77481-149">VirtualMemoryThrottlingCriteria</span></span>  
 <span data-ttu-id="77481-150">現在は、アンマネージ ヒープの断片化のため、仮想メモリが 32 ビット マシンのボトルネックとなる可能性があります。このため、このリソースも制限する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77481-150">Currently, virtual memory can become a bottleneck on 32-bit machines due to unmanaged heap fragmentation, so you should throttle by this resource as well.</span></span> <span data-ttu-id="77481-151">/3GB が設定されている場合、またはホストが 64 ビット プラットフォーム上で実行されている場合は、再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77481-151">You should re-configure if /3GB is set or if the hosts are running on a 64-bit platform.</span></span> <span data-ttu-id="77481-152">最適使用量と最大使用量は MB 単位です。</span><span class="sxs-lookup"><span data-stu-id="77481-152">Optimal and maximal usages are in MB.</span></span>  
  
 <span data-ttu-id="77481-153">次に、VirtualMemoryThrottlingCriteria の各プロパティの説明を示します。</span><span class="sxs-lookup"><span data-stu-id="77481-153">Following are descriptions of the individual VirtualMemoryThrottlingCriteria properties:</span></span>  
  
-   <span data-ttu-id="77481-154">**OptimalUsage**: 開始位置と退避制限を有効にする仮想メモリ使用量。</span><span class="sxs-lookup"><span data-stu-id="77481-154">**OptimalUsage**: The amount of virtual memory usage at which dehydration throttling begins to take effect.</span></span> <span data-ttu-id="77481-155">この時点では、 **TestThreshold**プロパティ値を持つ**MaxThreshold**と、メモリ使用量を超える**OptimalUsage**により**TestThreshold**するより小さい**MaxThreshold**です。</span><span class="sxs-lookup"><span data-stu-id="77481-155">At this point, **TestThreshold** has the value **MaxThreshold** and any memory usage greater than **OptimalUsage** causes **TestThreshold** to be less than **MaxThreshold**.</span></span>  
  
-   <span data-ttu-id="77481-156">**MaximalUsage**: で退避制限が最大限になった仮想メモリ使用量。</span><span class="sxs-lookup"><span data-stu-id="77481-156">**MaximalUsage**: The amount of virtual memory usage at which dehydration throttling is at a maximum.</span></span> <span data-ttu-id="77481-157">この時点では、 **TestThreshold**プロパティ値を持つ**MinThreshold**とメモリ使用量より小さい**MaximalUsage**により**TestThreshold**大きくなければ**MinThreshold**です。</span><span class="sxs-lookup"><span data-stu-id="77481-157">At this point, **TestThreshold** has the value **MinThreshold** and any memory usage less than **MaximalUsage** causes **TestThreshold** to be greater than **MinThreshold**.</span></span>  
  
-   <span data-ttu-id="77481-158">**IsActive**: 仮想メモリの制限がアクティブなかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="77481-158">**IsActive**: A boolean value indicating if virtual memory throttling is active.</span></span>  
  
## <a name="privatememorythrottlingcriteria"></a><span data-ttu-id="77481-159">PrivateMemoryThrottlingCriteria</span><span class="sxs-lookup"><span data-stu-id="77481-159">PrivateMemoryThrottlingCriteria</span></span>  
 <span data-ttu-id="77481-160">このプロパティは制限のために役立つ条件ですが、コンピューター上で他の Windows サービスが実行されているかどうかによって適切な値が異なります。</span><span class="sxs-lookup"><span data-stu-id="77481-160">This property is a useful criterion for throttling, but appropriate values depend on whether the computer is running other windows services.</span></span> <span data-ttu-id="77481-161">コンピューターに大量のメモリがあり、他の Windows サービスと共有していない場合、これらの値を大幅に増やすことができます。</span><span class="sxs-lookup"><span data-stu-id="77481-161">If the computer has a lot of memory and is not being shared with other windows services, then you can increase these values significantly.</span></span>  
  
 <span data-ttu-id="77481-162">次に、PrivateMemoryThrottlingCriteria の各プロパティの説明を示します。</span><span class="sxs-lookup"><span data-stu-id="77481-162">Following are descriptions of the individual PrivateMemoryThrottlingCriteria properties:</span></span>  
  
-   <span data-ttu-id="77481-163">**OptimalUsage**: の mb、開始位置と退避制限を有効にする、プライベート メモリ使用量。</span><span class="sxs-lookup"><span data-stu-id="77481-163">**OptimalUsage**: the amount of private memory usage, in MB, at which dehydration throttling begins to take effect.</span></span> <span data-ttu-id="77481-164">この時点で**TestThreshold**プロパティ値を持つ**MaxThreshold**と、メモリ使用量を超える**OptimalUsage**により**TestThreshold**するより小さい**MaxThreshold**です。</span><span class="sxs-lookup"><span data-stu-id="77481-164">At this point **TestThreshold** has the value **MaxThreshold** and any memory usage greater than **OptimalUsage** causes **TestThreshold** to be less than **MaxThreshold**.</span></span>  
  
-   <span data-ttu-id="77481-165">**MaximalUsage**: の mb、最大退避制限が、プライベート メモリ使用量。</span><span class="sxs-lookup"><span data-stu-id="77481-165">**MaximalUsage**: the amount of private memory usage, in MB, at which dehydration throttling is at a maximum.</span></span> <span data-ttu-id="77481-166">この時点で**TestThreshold**プロパティ値を持つ**MinThreshold**とメモリ使用量より小さい**MaximalUsage**により**TestThreshold**大きくなければ**MinThreshold**です。</span><span class="sxs-lookup"><span data-stu-id="77481-166">At this point **TestThreshold** has the value **MinThreshold** and any memory usage less than **MaximalUsage** causes **TestThreshold** to be greater than **MinThreshold**.</span></span>  
  
-   <span data-ttu-id="77481-167">**IsActive**: プライベート メモリ制限がアクティブなかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="77481-167">**IsActive**: a boolean value indicating if private memory throttling is active.</span></span>  
  
## <a name="physicalmemorythrottlingcriteria"></a><span data-ttu-id="77481-168">PhysicalMemoryThrottlingCriteria</span><span class="sxs-lookup"><span data-stu-id="77481-168">PhysicalMemoryThrottlingCriteria</span></span>  
 <span data-ttu-id="77481-169">メモリ使用量を MB 単位ではなくパーセンテージで表す、物理メモリ制限もあります。</span><span class="sxs-lookup"><span data-stu-id="77481-169">There is also a physical memory throttling where numbers are measured in percentage of memory used rather than MB.</span></span> <span data-ttu-id="77481-170">このプロパティは既定で無効になっていますが、必要に応じて有効にできます。</span><span class="sxs-lookup"><span data-stu-id="77481-170">This property is disabled by default, but you can enable if needed.</span></span>  
  
 <span data-ttu-id="77481-171">次に、PhysicalMemoryThrottlingCriteria の各プロパティの説明を示します。</span><span class="sxs-lookup"><span data-stu-id="77481-171">Following are descriptions of the individual PhysicalMemoryThrottlingCriteria properties:</span></span>  
  
-   <span data-ttu-id="77481-172">**OptimalUsage**: ホスト インスタンスに使用する物理メモリの最適なパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="77481-172">**OptimalUsage**: the optimum percentage of physical memory to use for the host instances.</span></span>  
  
-   <span data-ttu-id="77481-173">**MaximalUsage**: ホスト インスタンスに使用する物理メモリの最大パーセンテージです。</span><span class="sxs-lookup"><span data-stu-id="77481-173">**MaximalUsage**: the maximum percentage of physical memory to use for the host instances.</span></span>  
  
-   <span data-ttu-id="77481-174">**IsActive**: 物理メモリの制限がアクティブなかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="77481-174">**IsActive**: boolean value indicating if physical memory throttling is active.</span></span>  
  
## <a name="dehydration-properties-behavior"></a><span data-ttu-id="77481-175">退避プロパティの動作</span><span class="sxs-lookup"><span data-stu-id="77481-175">Dehydration Properties Behavior</span></span>  
 <span data-ttu-id="77481-176">BizTalk Server はこれらの退避プロパティを使用して、オーケストレーションをいつ退避および復元するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="77481-176">BizTalk Server uses these dehydration properties to decide when to dehydrate and rehydrate orchestrations.</span></span> <span data-ttu-id="77481-177">標準の負荷状態では、既定の復元値で十分です。しかし、負荷が高い状態で実行していてパフォーマンス特性を変更する場合、自分でチューニングを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="77481-177">Under normal load, the default dehydration values are sufficient, but if you are running under heavy load and want to change performance characteristics, you should do the tuning yourself.</span></span>  
  
 <span data-ttu-id="77481-178">BizTalk Server の復元動作は、使用可能なメモリ量と使用されているメモリ量に完全に依存します。</span><span class="sxs-lookup"><span data-stu-id="77481-178">The dehydration behavior of BizTalk Server depends entirely on how much memory is available and how much memory is being used.</span></span> <span data-ttu-id="77481-179">復元動作は、メモリ量によって異なります。また、32 ビットと 64 ビットのホスト間のメモリ使用の違いによっても異なります。</span><span class="sxs-lookup"><span data-stu-id="77481-179">The dehydration behavior is different with different amounts of memory and differences in memory use between 32-bit and 64-bit hosts.</span></span>  
  
 <span data-ttu-id="77481-180">復元プロパティでは、オーケストレーション ホストのプライベート バイトと仮想バイトが、次のように識別されます。</span><span class="sxs-lookup"><span data-stu-id="77481-180">The dehydration properties distinguish between Private Bytes and Virtual Bytes for the orchestration host:</span></span>  
  
-   <span data-ttu-id="77481-181">**仮想バイト**です。</span><span class="sxs-lookup"><span data-stu-id="77481-181">**Virtual Bytes**.</span></span> <span data-ttu-id="77481-182">これは、(バイト単位) を使用して、プロセス仮想アドレス空間の現在のサイズです。</span><span class="sxs-lookup"><span data-stu-id="77481-182">This is thecurrent size, in bytes, of the virtual address space the process is using.</span></span> <span data-ttu-id="77481-183">仮想アドレス空間を使用していても、ディスク ページまたはメイン メモリ ページを使用しているとは限りません。</span><span class="sxs-lookup"><span data-stu-id="77481-183">Use of virtual address space does not necessarily imply corresponding use of either disk or main memory pages.</span></span> <span data-ttu-id="77481-184">仮想空間は有限であり、プロセスではライブラリ読み込み機能を制限できます。</span><span class="sxs-lookup"><span data-stu-id="77481-184">Virtual space is finite, and the process can limit its ability to load libraries.</span></span>  
  
-   <span data-ttu-id="77481-185">**Private Bytes**です。</span><span class="sxs-lookup"><span data-stu-id="77481-185">**Private Bytes**.</span></span> <span data-ttu-id="77481-186">これは、このプロセスによって割り当てられ、他のプロセスと共有できないメモリの現在のサイズ (バイト単位) です。</span><span class="sxs-lookup"><span data-stu-id="77481-186">This is the current size, in bytes, of memory that this process has allocated that cannot be shared with other processes.</span></span>