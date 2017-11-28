---
title: "オーケストレーション メモリ制限の設定を変更する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Bts10.settings.HostInstanceOrchestration
ms.assetid: f6953c68-7809-4518-87ec-e75c98884af3
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c48f1ec5e74ae577a7c1d130e22f3b4a1b53874c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-modify-orchestration-memory-throttling-settings"></a><span data-ttu-id="974e5-102">オーケストレーション メモリの制限の設定を変更する方法</span><span class="sxs-lookup"><span data-stu-id="974e5-102">How to Modify Orchestration Memory Throttling Settings</span></span>
<span data-ttu-id="974e5-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のホスト インスタンス メモリ制限メカニズムは、制限の条件を継続的に監視し、制限の条件の重大度を評価し、評価された重大度に応じてホスト インスタンス メモリ制限を段階的に適用します。</span><span class="sxs-lookup"><span data-stu-id="974e5-103">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] host instance memory throttling mechanism continuously monitors for a throttling condition, calculates the severity of the throttling condition, and applies host instance memory throttling progressively depending on the calculated severity.</span></span> <span data-ttu-id="974e5-104">このトピックでは、設定ダッシュボードを使用して、この操作を変更する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="974e5-104">This topic provides the step-by-step procedure to modify these settings using the Settings Dashboard.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="974e5-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="974e5-105">Prerequisites</span></span>  
 <span data-ttu-id="974e5-106">ここで示す操作を実行するには、BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="974e5-106">To perform this operation, you must be logged on as a member of the BizTalk Server Administrators group.</span></span>  
  
### <a name="to-modify-the-orchestration-memory-throttling-settings-of-a-host-instance"></a><span data-ttu-id="974e5-107">ホスト インスタンスのオーケストレーション メモリ制限の設定を変更するには</span><span class="sxs-lookup"><span data-stu-id="974e5-107">To modify the orchestration memory throttling settings of a host instance</span></span>  
  
1.  <span data-ttu-id="974e5-108">**BizTalk Server 管理コンソール**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]を右クリックして**BizTalk グループ**、クリックして**設定**です。</span><span class="sxs-lookup"><span data-stu-id="974e5-108">In the **BizTalk Server Administration Console**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click **BizTalk Group**, and then click **Settings**.</span></span>  
  
2.  <span data-ttu-id="974e5-109">**BizTalk 設定ダッシュ ボード** ダイアログ ボックスで、**ホスト インスタンス** ページで、をクリックして、**オーケストレーション メモリ制限**タブです。</span><span class="sxs-lookup"><span data-stu-id="974e5-109">In the **BizTalk Settings Dashboard** dialog box, on the **Host Instances** page, click the **Orchestration Memory Throttling** tab.</span></span>  
  
3.  <span data-ttu-id="974e5-110">クリックして、次の操作、**適用**を変更を適用し、別のタブに進みます。をクリックしてまたは**OK**を変更を適用し、設定ダッシュ ボードを終了します。</span><span class="sxs-lookup"><span data-stu-id="974e5-110">Do the following, and then click **Apply** to apply the modifications and proceed to another tab. Or click **OK** to apply the modifications and exit the Settings Dashboard.</span></span>  
  
    |<span data-ttu-id="974e5-111">プロパティ</span><span class="sxs-lookup"><span data-stu-id="974e5-111">Use this</span></span>|<span data-ttu-id="974e5-112">目的</span><span class="sxs-lookup"><span data-stu-id="974e5-112">To do this</span></span>|<span data-ttu-id="974e5-113">境界値</span><span class="sxs-lookup"><span data-stu-id="974e5-113">Boundary values</span></span>|<span data-ttu-id="974e5-114">既定値</span><span class="sxs-lookup"><span data-stu-id="974e5-114">Default value</span></span>|  
    |--------------|----------------|---------------------|-------------------|  
    |<span data-ttu-id="974e5-115">**ホスト インスタンス**</span><span class="sxs-lookup"><span data-stu-id="974e5-115">**Host Instance**</span></span>|<span data-ttu-id="974e5-116">ドロップダウン ボックスから、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイム コンピューター上のホストで実行中のインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="974e5-116">From the drop-down box, select the running instance of a host on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime machine.</span></span>|-|-|  
  
     <span data-ttu-id="974e5-117">**物理**</span><span class="sxs-lookup"><span data-stu-id="974e5-117">**Physical**</span></span>  
  
    |<span data-ttu-id="974e5-118">プロパティ</span><span class="sxs-lookup"><span data-stu-id="974e5-118">Use this</span></span>|<span data-ttu-id="974e5-119">目的</span><span class="sxs-lookup"><span data-stu-id="974e5-119">To do this</span></span>|<span data-ttu-id="974e5-120">境界値</span><span class="sxs-lookup"><span data-stu-id="974e5-120">Boundary values</span></span>|<span data-ttu-id="974e5-121">既定値</span><span class="sxs-lookup"><span data-stu-id="974e5-121">Default value</span></span>|  
    |--------------|----------------|---------------------|-------------------|  
    |<span data-ttu-id="974e5-122">**最適使用量**</span><span class="sxs-lookup"><span data-stu-id="974e5-122">**Optimal usage**</span></span>|<span data-ttu-id="974e5-123">退避制限を有効にする物理メモリの使用量をパーセンテージで指定します。</span><span class="sxs-lookup"><span data-stu-id="974e5-123">Specify the percentage of physical memory usage at which dehydration throttling comes into effect.</span></span> <span data-ttu-id="974e5-124">これはホスト インスタンスに使用する物理メモリの最適なパーセンテージです。</span><span class="sxs-lookup"><span data-stu-id="974e5-124">This is the optimum percentage of physical memory to use for the host instances.</span></span>|<span data-ttu-id="974e5-125">[0 – 100]</span><span class="sxs-lookup"><span data-stu-id="974e5-125">[0 – 100]</span></span>|<span data-ttu-id="974e5-126">70</span><span class="sxs-lookup"><span data-stu-id="974e5-126">70</span></span>|  
    |<span data-ttu-id="974e5-127">**最大使用量**</span><span class="sxs-lookup"><span data-stu-id="974e5-127">**Maximal usage**</span></span>|<span data-ttu-id="974e5-128">退避制限が最大になる物理メモリの使用量をパーセンテージで指定します。</span><span class="sxs-lookup"><span data-stu-id="974e5-128">Specify the percentage of physical memory usage at which dehydration throttling is maximum.</span></span> <span data-ttu-id="974e5-129">これはホスト インスタンスに使用する物理メモリの最大のパーセンテージです。</span><span class="sxs-lookup"><span data-stu-id="974e5-129">This is the maximum percentage of physical memory to use for the host instances.</span></span><br /><br /> <span data-ttu-id="974e5-130">最小値**maximalusage**する必要があります**最適使用量**です。</span><span class="sxs-lookup"><span data-stu-id="974e5-130">The minimum value of **Maximal usage** should be **Optimal usage**.</span></span>|<span data-ttu-id="974e5-131">(最適使用量 - 100]</span><span class="sxs-lookup"><span data-stu-id="974e5-131">(Optimal usage – 100]</span></span><br /><br /> <span data-ttu-id="974e5-132">両方が 0 または 100 の場合は除外します。</span><span class="sxs-lookup"><span data-stu-id="974e5-132">Except when both are 0 or 100.</span></span>|<span data-ttu-id="974e5-133">85</span><span class="sxs-lookup"><span data-stu-id="974e5-133">85</span></span>|  
  
     <span data-ttu-id="974e5-134">**仮想**</span><span class="sxs-lookup"><span data-stu-id="974e5-134">**Virtual**</span></span>  
  
    |<span data-ttu-id="974e5-135">プロパティ</span><span class="sxs-lookup"><span data-stu-id="974e5-135">Use this</span></span>|<span data-ttu-id="974e5-136">目的</span><span class="sxs-lookup"><span data-stu-id="974e5-136">To do this</span></span>|<span data-ttu-id="974e5-137">境界値</span><span class="sxs-lookup"><span data-stu-id="974e5-137">Boundary values</span></span>|<span data-ttu-id="974e5-138">既定値</span><span class="sxs-lookup"><span data-stu-id="974e5-138">Default value</span></span>|  
    |--------------|----------------|---------------------|-------------------|  
    |<span data-ttu-id="974e5-139">**最適使用量**</span><span class="sxs-lookup"><span data-stu-id="974e5-139">**Optimal usage**</span></span>|<span data-ttu-id="974e5-140">退避制限を有効にする仮想メモリの使用量をパーセンテージで指定します。</span><span class="sxs-lookup"><span data-stu-id="974e5-140">Specify the percentage of virtual memory usage at which dehydration throttling comes into effect.</span></span><br /><br /> <span data-ttu-id="974e5-141">この時点では、 **TestThreshold**プロパティ値を持つ**MaxThreshold**と、メモリ使用量を超える**OptimalUsage**により**TestThreshold**するより小さい**MaxThreshold**です。</span><span class="sxs-lookup"><span data-stu-id="974e5-141">At this point, **TestThreshold** has the value **MaxThreshold** and any memory usage greater than **OptimalUsage** causes **TestThreshold** to be less than **MaxThreshold**.</span></span>|<span data-ttu-id="974e5-142">[0 – 100]</span><span class="sxs-lookup"><span data-stu-id="974e5-142">[0 – 100]</span></span>|<span data-ttu-id="974e5-143">65</span><span class="sxs-lookup"><span data-stu-id="974e5-143">65</span></span>|  
    |<span data-ttu-id="974e5-144">**最大使用量**</span><span class="sxs-lookup"><span data-stu-id="974e5-144">**Maximal usage**</span></span>|<span data-ttu-id="974e5-145">退避制限が最大になる仮想メモリの使用量をパーセンテージで指定します。</span><span class="sxs-lookup"><span data-stu-id="974e5-145">Specify the percentage of virtual memory usage at which dehydration throttling is maximum.</span></span><br /><br /> <span data-ttu-id="974e5-146">この時点では、 **TestThreshold**プロパティ値を持つ**MinThreshold**とメモリ使用量より小さい**MaximalUsage**により**TestThreshold**大きくなければ**MinThreshold**です。</span><span class="sxs-lookup"><span data-stu-id="974e5-146">At this point, **TestThreshold** has the value **MinThreshold** and any memory usage less than **MaximalUsage** causes **TestThreshold** to be greater than **MinThreshold**.</span></span>|<span data-ttu-id="974e5-147">(最適使用量 - 100]</span><span class="sxs-lookup"><span data-stu-id="974e5-147">(Optimal usage – 100]</span></span><br /><br /> <span data-ttu-id="974e5-148">両方が 0 または 100 の場合は除外します。</span><span class="sxs-lookup"><span data-stu-id="974e5-148">Except when both are 0 or 100.</span></span>|<span data-ttu-id="974e5-149">85</span><span class="sxs-lookup"><span data-stu-id="974e5-149">85</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="974e5-150">既定の設定を復元する をクリックして**既定値に戻す**です。</span><span class="sxs-lookup"><span data-stu-id="974e5-150">To restore the default settings, click **Restore Defaults**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="974e5-151">参照</span><span class="sxs-lookup"><span data-stu-id="974e5-151">See Also</span></span>  
 [<span data-ttu-id="974e5-152">ホスト インスタンスの設定を変更する方法</span><span class="sxs-lookup"><span data-stu-id="974e5-152">How to Modify Host Instance Settings</span></span>](../core/how-to-modify-host-instance-settings.md)