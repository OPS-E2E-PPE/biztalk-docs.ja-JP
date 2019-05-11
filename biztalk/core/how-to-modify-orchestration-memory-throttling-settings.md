---
title: オーケストレーション メモリ制限の設定を変更する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- Bts10.settings.HostInstanceOrchestration
ms.assetid: f6953c68-7809-4518-87ec-e75c98884af3
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 839ef9d8d97e06c85192c3d8fee049029942fb99
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336059"
---
# <a name="how-to-modify-orchestration-memory-throttling-settings"></a><span data-ttu-id="8ba19-102">オーケストレーション メモリ制限の設定を変更する方法</span><span class="sxs-lookup"><span data-stu-id="8ba19-102">How to Modify Orchestration Memory Throttling Settings</span></span>
<span data-ttu-id="8ba19-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]制限メカニズムを継続的にホスト インスタンス メモリ制限の条件を監視、制限の条件の重大度を計算およびホスト インスタンスのメモリが制限を段階的に、計算によって適用されます重大度。</span><span class="sxs-lookup"><span data-stu-id="8ba19-103">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] host instance memory throttling mechanism continuously monitors for a throttling condition, calculates the severity of the throttling condition, and applies host instance memory throttling progressively depending on the calculated severity.</span></span> <span data-ttu-id="8ba19-104">このトピックでは、設定ダッシュ ボードを使用してこれらの設定を変更するための手順を提供します。</span><span class="sxs-lookup"><span data-stu-id="8ba19-104">This topic provides the step-by-step procedure to modify these settings using the Settings Dashboard.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="8ba19-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="8ba19-105">Prerequisites</span></span>  
 <span data-ttu-id="8ba19-106">この操作を実行するには、BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ba19-106">To perform this operation, you must be logged on as a member of the BizTalk Server Administrators group.</span></span>  

### <a name="to-modify-the-orchestration-memory-throttling-settings-of-a-host-instance"></a><span data-ttu-id="8ba19-107">オーケストレーション メモリ制限のホスト インスタンスの設定を変更するには</span><span class="sxs-lookup"><span data-stu-id="8ba19-107">To modify the orchestration memory throttling settings of a host instance</span></span>  

1. <span data-ttu-id="8ba19-108">**BizTalk Server 管理コンソール**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]を右クリックして**BizTalk グループ**、 をクリックし、**設定**します。</span><span class="sxs-lookup"><span data-stu-id="8ba19-108">In the **BizTalk Server Administration Console**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click **BizTalk Group**, and then click **Settings**.</span></span>  

2. <span data-ttu-id="8ba19-109">**BizTalk 設定ダッシュ ボード** ダイアログ ボックスで、**ホスト インスタンス** ページで、をクリックして、**オーケストレーション メモリ制限**タブ。</span><span class="sxs-lookup"><span data-stu-id="8ba19-109">In the **BizTalk Settings Dashboard** dialog box, on the **Host Instances** page, click the **Orchestration Memory Throttling** tab.</span></span>  

3. <span data-ttu-id="8ba19-110">クリックして、次の操作を**適用**を変更を適用し、別のタブに進みます。をクリックしてまたは**OK**変更を適用し、設定ダッシュ ボードを終了します。</span><span class="sxs-lookup"><span data-stu-id="8ba19-110">Do the following, and then click **Apply** to apply the modifications and proceed to another tab. Or click **OK** to apply the modifications and exit the Settings Dashboard.</span></span>  


   |     <span data-ttu-id="8ba19-111">プロパティ</span><span class="sxs-lookup"><span data-stu-id="8ba19-111">Use this</span></span>      |                                                                                <span data-ttu-id="8ba19-112">目的</span><span class="sxs-lookup"><span data-stu-id="8ba19-112">To do this</span></span>                                                                                | <span data-ttu-id="8ba19-113">境界値</span><span class="sxs-lookup"><span data-stu-id="8ba19-113">Boundary values</span></span> | <span data-ttu-id="8ba19-114">既定値</span><span class="sxs-lookup"><span data-stu-id="8ba19-114">Default value</span></span> |
   |-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------|---------------|
   | <span data-ttu-id="8ba19-115">**ホスト インスタンス**</span><span class="sxs-lookup"><span data-stu-id="8ba19-115">**Host Instance**</span></span> | <span data-ttu-id="8ba19-116">ホストの実行中のインスタンスを選択、ドロップダウン ボックスから、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム コンピューター。</span><span class="sxs-lookup"><span data-stu-id="8ba19-116">From the drop-down box, select the running instance of a host on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime machine.</span></span> |        -        |       -       |

    <span data-ttu-id="8ba19-117">**物理**</span><span class="sxs-lookup"><span data-stu-id="8ba19-117">**Physical**</span></span>  

   |<span data-ttu-id="8ba19-118">プロパティ</span><span class="sxs-lookup"><span data-stu-id="8ba19-118">Use this</span></span>|<span data-ttu-id="8ba19-119">目的</span><span class="sxs-lookup"><span data-stu-id="8ba19-119">To do this</span></span>|<span data-ttu-id="8ba19-120">境界値</span><span class="sxs-lookup"><span data-stu-id="8ba19-120">Boundary values</span></span>|<span data-ttu-id="8ba19-121">既定値</span><span class="sxs-lookup"><span data-stu-id="8ba19-121">Default value</span></span>|  
   |--------------|----------------|---------------------|-------------------|  
   |<span data-ttu-id="8ba19-122">**最適使用量**</span><span class="sxs-lookup"><span data-stu-id="8ba19-122">**Optimal usage**</span></span>|<span data-ttu-id="8ba19-123">有効にする退避制限が物理メモリ使用量の割合を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ba19-123">Specify the percentage of physical memory usage at which dehydration throttling comes into effect.</span></span> <span data-ttu-id="8ba19-124">これは、ホスト インスタンスに使用する物理メモリの最適なパーセンテージです。</span><span class="sxs-lookup"><span data-stu-id="8ba19-124">This is the optimum percentage of physical memory to use for the host instances.</span></span>|<span data-ttu-id="8ba19-125">[0 – 100]</span><span class="sxs-lookup"><span data-stu-id="8ba19-125">[0 – 100]</span></span>|<span data-ttu-id="8ba19-126">70</span><span class="sxs-lookup"><span data-stu-id="8ba19-126">70</span></span>|  
   |<span data-ttu-id="8ba19-127">**最大使用量**</span><span class="sxs-lookup"><span data-stu-id="8ba19-127">**Maximal usage**</span></span>|<span data-ttu-id="8ba19-128">退避制限が最大物理メモリ使用量の割合を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ba19-128">Specify the percentage of physical memory usage at which dehydration throttling is maximum.</span></span> <span data-ttu-id="8ba19-129">これは、ホスト インスタンスに使用する物理メモリの最大パーセンテージです。</span><span class="sxs-lookup"><span data-stu-id="8ba19-129">This is the maximum percentage of physical memory to use for the host instances.</span></span><br /><br /> <span data-ttu-id="8ba19-130">最小値**maximalusage**べき**最適使用量**します。</span><span class="sxs-lookup"><span data-stu-id="8ba19-130">The minimum value of **Maximal usage** should be **Optimal usage**.</span></span>|<span data-ttu-id="8ba19-131">(最適使用量-100]</span><span class="sxs-lookup"><span data-stu-id="8ba19-131">(Optimal usage – 100]</span></span><br /><br /> <span data-ttu-id="8ba19-132">両方が 0 または 100 の場合は除きます。</span><span class="sxs-lookup"><span data-stu-id="8ba19-132">Except when both are 0 or 100.</span></span>|<span data-ttu-id="8ba19-133">85</span><span class="sxs-lookup"><span data-stu-id="8ba19-133">85</span></span>|  

    <span data-ttu-id="8ba19-134">**仮想**</span><span class="sxs-lookup"><span data-stu-id="8ba19-134">**Virtual**</span></span>  

   |<span data-ttu-id="8ba19-135">プロパティ</span><span class="sxs-lookup"><span data-stu-id="8ba19-135">Use this</span></span>|<span data-ttu-id="8ba19-136">目的</span><span class="sxs-lookup"><span data-stu-id="8ba19-136">To do this</span></span>|<span data-ttu-id="8ba19-137">境界値</span><span class="sxs-lookup"><span data-stu-id="8ba19-137">Boundary values</span></span>|<span data-ttu-id="8ba19-138">既定値</span><span class="sxs-lookup"><span data-stu-id="8ba19-138">Default value</span></span>|  
   |--------------|----------------|---------------------|-------------------|  
   |<span data-ttu-id="8ba19-139">**最適使用量**</span><span class="sxs-lookup"><span data-stu-id="8ba19-139">**Optimal usage**</span></span>|<span data-ttu-id="8ba19-140">退避制限を有効には仮想メモリ使用量の割合を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ba19-140">Specify the percentage of virtual memory usage at which dehydration throttling comes into effect.</span></span><br /><br /> <span data-ttu-id="8ba19-141">この時点では、 **TestThreshold** 、値を持つ**MaxThreshold**メモリ使用量を超える**OptimalUsage**により**TestThreshold**をより小さい**MaxThreshold**します。</span><span class="sxs-lookup"><span data-stu-id="8ba19-141">At this point, **TestThreshold** has the value **MaxThreshold** and any memory usage greater than **OptimalUsage** causes **TestThreshold** to be less than **MaxThreshold**.</span></span>|<span data-ttu-id="8ba19-142">[0 – 100]</span><span class="sxs-lookup"><span data-stu-id="8ba19-142">[0 – 100]</span></span>|<span data-ttu-id="8ba19-143">65</span><span class="sxs-lookup"><span data-stu-id="8ba19-143">65</span></span>|  
   |<span data-ttu-id="8ba19-144">**最大使用量**</span><span class="sxs-lookup"><span data-stu-id="8ba19-144">**Maximal usage**</span></span>|<span data-ttu-id="8ba19-145">退避制限が最大仮想メモリ使用量の割合を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ba19-145">Specify the percentage of virtual memory usage at which dehydration throttling is maximum.</span></span><br /><br /> <span data-ttu-id="8ba19-146">この時点では、 **TestThreshold** 、値を持つ**MinThreshold**メモリ使用量より小さい**MaximalUsage**により**TestThreshold**超える**MinThreshold**します。</span><span class="sxs-lookup"><span data-stu-id="8ba19-146">At this point, **TestThreshold** has the value **MinThreshold** and any memory usage less than **MaximalUsage** causes **TestThreshold** to be greater than **MinThreshold**.</span></span>|<span data-ttu-id="8ba19-147">(最適使用量-100]</span><span class="sxs-lookup"><span data-stu-id="8ba19-147">(Optimal usage – 100]</span></span><br /><br /> <span data-ttu-id="8ba19-148">両方が 0 または 100 の場合は除きます。</span><span class="sxs-lookup"><span data-stu-id="8ba19-148">Except when both are 0 or 100.</span></span>|<span data-ttu-id="8ba19-149">85</span><span class="sxs-lookup"><span data-stu-id="8ba19-149">85</span></span>|  

   > [!NOTE]
   >  <span data-ttu-id="8ba19-150">既定の設定を復元するには、次のようにクリックします。**既定値に戻す**します。</span><span class="sxs-lookup"><span data-stu-id="8ba19-150">To restore the default settings, click **Restore Defaults**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="8ba19-151">参照</span><span class="sxs-lookup"><span data-stu-id="8ba19-151">See Also</span></span>  
 [<span data-ttu-id="8ba19-152">ホスト インスタンスの設定を変更する方法</span><span class="sxs-lookup"><span data-stu-id="8ba19-152">How to Modify Host Instance Settings</span></span>](../core/how-to-modify-host-instance-settings.md)