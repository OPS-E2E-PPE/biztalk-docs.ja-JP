---
title: リアルタイム集計 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, aggregations
- aggregations [BAM], real-time data
ms.assetid: 0ef44641-e067-4108-b318-f4373ca8fa8f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6cfb7d2c50b011743f652fd261eed68e810db10f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981043"
---
# <a name="real-time-aggregations"></a><span data-ttu-id="87c2e-102">リアルタイム集計</span><span class="sxs-lookup"><span data-stu-id="87c2e-102">Real-Time Aggregations</span></span>
<span data-ttu-id="87c2e-103">多次元集計の特定のスライスでは、時間が重要な要素になる場合があります。このような場合には、スライスをリアルタイムで使用することが必要になります。</span><span class="sxs-lookup"><span data-stu-id="87c2e-103">In some cases, specific slices of the multidimensional aggregations are so time-sensitive that you want them to be available in real time.</span></span> <span data-ttu-id="87c2e-104">たとえば、生鮮食料品を販売する業者では、配送の各段階での製品数量の集計をリアルタイムで利用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="87c2e-104">For example, your business is selling perishable products and you want the aggregation of product quantity in different stages of delivery to be available in real time.</span></span> <span data-ttu-id="87c2e-105">同時に、代表的な顧客の年齢などの他の集計を、ビジネス インテリジェンス分析のために月末にのみ実行する必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="87c2e-105">At the same time, you want other aggregations such as the age of your typical customers, but only at the end of the month for business intelligence analysis.</span></span>  
  
 <span data-ttu-id="87c2e-106">BAM には、アクティビティ ストレージ テーブルからのトリガーによって維持されるテーブルとして、リアルタイム集計 (RTA) が実装されています。</span><span class="sxs-lookup"><span data-stu-id="87c2e-106">BAM implements real-time aggregation (RTA) as a table maintained by triggers from the activity storage tables.</span></span> <span data-ttu-id="87c2e-107">注文書 (PO) を処理する場合、RTA ビューは次の図の例のようになります。</span><span class="sxs-lookup"><span data-stu-id="87c2e-107">In the case when your business deals with purchase orders (PO), the RTA view may look like the example in the following figure.</span></span>  
  
 <span data-ttu-id="87c2e-108">![](../core/media/bam-realtime-aggregations.gif "bam_realtime_aggregations")</span><span class="sxs-lookup"><span data-stu-id="87c2e-108">![](../core/media/bam-realtime-aggregations.gif "bam_realtime_aggregations")</span></span>  
<span data-ttu-id="87c2e-109">BAM リアルタイム集計</span><span class="sxs-lookup"><span data-stu-id="87c2e-109">BAM Real-time Aggregations</span></span>  
  
 <span data-ttu-id="87c2e-110">この図では、Redmond から 100 ドルの新しい PO を受け取ると、`Count=Count+1` や `Amount=Amount+$100` などの演算が行われ、対応する {Redmond, InProcess} 行のセルに金額が加算されます。</span><span class="sxs-lookup"><span data-stu-id="87c2e-110">In this figure, if a new PO of $100 from Redmond is received, BAM adds a contribution to the cells in the corresponding row for {Redmond, InProcess} by performing an operation like `Count=Count+1` and `Amount=Amount+$100`.</span></span>  
  
 <span data-ttu-id="87c2e-111">その後、その注文が出荷されると、金額が行 {Redmond, InProcess} から削除され、行 {Redmond, Shipped} に加算されます。</span><span class="sxs-lookup"><span data-stu-id="87c2e-111">Later, if the same order ships, then BAM removes this contribution from the row {Redmond, InProcess} and adds it to the row {Redmond, Shipped}.</span></span>  
  
 <span data-ttu-id="87c2e-112">BAM は特定のオンライン時間帯のデータを RTA 内に維持してから、削除します。</span><span class="sxs-lookup"><span data-stu-id="87c2e-112">BAM maintains the data inside RTA for a given online window, and then deletes it.</span></span> <span data-ttu-id="87c2e-113">オンライン時間帯を構成するには、テーブルの対応する行を変更することで**bam_Metadata_RealTimeAggregations**します。</span><span class="sxs-lookup"><span data-stu-id="87c2e-113">You can configure the online window by changing the corresponding row of the table **bam_Metadata_RealTimeAggregations**.</span></span>  
  
 <span data-ttu-id="87c2e-114">リアルタイム集計では、次のような状況が発生します。</span><span class="sxs-lookup"><span data-stu-id="87c2e-114">The following statements also apply to real-time aggregations:</span></span>  
  
- <span data-ttu-id="87c2e-115">リアルタイム集計は、BAM のデータ書き込み速度に大きく影響します。</span><span class="sxs-lookup"><span data-stu-id="87c2e-115">Real-time aggregations significantly affect the speed at which BAM can write data.</span></span> <span data-ttu-id="87c2e-116">したがって、集計構造の中で重要なスライスのみを RTA として定義してください。</span><span class="sxs-lookup"><span data-stu-id="87c2e-116">Thus, you should only define the most important slices of the aggregation structure as RTA.</span></span>  
  
- <span data-ttu-id="87c2e-117">リアルタイム集計のディメンション レベルの制限が 14 文字です。</span><span class="sxs-lookup"><span data-stu-id="87c2e-117">The limitation of the dimension levels for real-time aggregations is 14.</span></span> <span data-ttu-id="87c2e-118">たとえば、州と都市のデータ ディメンションの場所を作成する場合 (State と City) の 2 つのレベルとしてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="87c2e-118">For example, if you create a Data Dimension Location for State and City, this counts as two levels (State and City).</span></span> <span data-ttu-id="87c2e-119">進捗ディメンションのレベル数は、ツリーの深さで数えます。時間ディメンションのレベル数は、サブユニットの総数で数えます。</span><span class="sxs-lookup"><span data-stu-id="87c2e-119">For Progress Dimensions the number of levels is the depth of the tree, and for Time Dimensions it is the count of all sub-units.</span></span> <span data-ttu-id="87c2e-120">たとえば、時間ディメンションの年、月、日、1 時間としてカウントされます 4 つのレベル。</span><span class="sxs-lookup"><span data-stu-id="87c2e-120">For example, a Time Dimension for Year, Month, Day, Hour will count as four levels.</span></span>  
  
- <span data-ttu-id="87c2e-121">BAM は、型のリアルタイムの集計をサポートしていません**Min**と**最大**します。</span><span class="sxs-lookup"><span data-stu-id="87c2e-121">BAM does not support real-time aggregations of type **Min** and **Max**.</span></span> <span data-ttu-id="87c2e-122">BAM がサポートする集計は**カウント**、**合計**、および**平均**します。</span><span class="sxs-lookup"><span data-stu-id="87c2e-122">The aggregations that BAM supports are **Count**, **Sum**, and **Average**.</span></span>  
  
- <span data-ttu-id="87c2e-123">RTA のデータは特定のビジネス マイルストーンではなく、サーバーのタイム スタンプに従って古くなります。そのため、常に RTA の時間ディメンションを作成し、すべてのデータ スライスでそのディメンションを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87c2e-123">You must always create a time dimension for RTA and always use it in all data slices, because the data in RTA is aged based on the server time stamp, and not on any specific business milestone.</span></span>  
  
- <span data-ttu-id="87c2e-124">同じ BAM アクティビティを使用する RTA を複数定義しないでください。</span><span class="sxs-lookup"><span data-stu-id="87c2e-124">Do not define multiple RTAs that use the same BAM activity.</span></span> <span data-ttu-id="87c2e-125">そのような RTA を複数定義した場合、BAM データをアーカイブしたときに RTA データが不正確になります。</span><span class="sxs-lookup"><span data-stu-id="87c2e-125">If you do so, the RTA data will be incorrect when you archive the BAM data.</span></span>  
  
  <span data-ttu-id="87c2e-126">リアルタイム集計は、BAM のデータ書き込み速度に大きく影響します。</span><span class="sxs-lookup"><span data-stu-id="87c2e-126">Real-time aggregations significantly affect the speed at which BAM can write data.</span></span> <span data-ttu-id="87c2e-127">したがって、集計構造の中で重要なスライスのみを RTA として定義してください。</span><span class="sxs-lookup"><span data-stu-id="87c2e-127">Thus, you should only define the most important slices of the aggregation structure as RTA.</span></span>  
  
  <span data-ttu-id="87c2e-128">リアルタイム集計のディメンション レベルの制限が 14 文字です。</span><span class="sxs-lookup"><span data-stu-id="87c2e-128">The limitation of the dimension levels for real-time aggregations is 14.</span></span> <span data-ttu-id="87c2e-129">たとえば、州と都市のデータ ディメンションの場所を作成する場合 (State と City) の 2 つのレベルとしてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="87c2e-129">For example, if you create a Data Dimension Location for State and City, this counts as two levels (State and City).</span></span> <span data-ttu-id="87c2e-130">進捗ディメンションのレベル数は、ツリーの深さで数えます。時間ディメンションのレベル数は、サブユニットの総数で数えます。</span><span class="sxs-lookup"><span data-stu-id="87c2e-130">For Progress Dimensions the number of levels is the depth of the tree, and for Time Dimensions it is the count of all sub-units.</span></span> <span data-ttu-id="87c2e-131">たとえば、時間ディメンションの年、月、日、1 時間としてカウントされます 4 つのレベル。</span><span class="sxs-lookup"><span data-stu-id="87c2e-131">For example, a Time Dimension for Year, Month, Day, Hour will count as four levels.</span></span>  
  
  <span data-ttu-id="87c2e-132">BAM は、型のリアルタイムの集計をサポートしていません**Min**と**最大**します。</span><span class="sxs-lookup"><span data-stu-id="87c2e-132">BAM does not support real-time aggregations of type **Min** and **Max**.</span></span> <span data-ttu-id="87c2e-133">BAM がサポートする集計は**カウント**、**合計**、および**平均**します。</span><span class="sxs-lookup"><span data-stu-id="87c2e-133">The aggregations that BAM supports are **Count**, **Sum**, and **Average**.</span></span>  
  
  <span data-ttu-id="87c2e-134">同じ BAM アクティビティを使用する RTA を複数定義しないでください。</span><span class="sxs-lookup"><span data-stu-id="87c2e-134">Do not define multiple RTAs that use the same BAM activity.</span></span> <span data-ttu-id="87c2e-135">そのような RTA を複数定義した場合、BAM データをアーカイブしたときに RTA データが不正確になります。</span><span class="sxs-lookup"><span data-stu-id="87c2e-135">If you do so, the RTA data will be incorrect when you archive the BAM data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87c2e-136">参照</span><span class="sxs-lookup"><span data-stu-id="87c2e-136">See Also</span></span>  
 [<span data-ttu-id="87c2e-137">集計について</span><span class="sxs-lookup"><span data-stu-id="87c2e-137">What Is an Aggregation?</span></span>](../core/what-is-an-aggregation.md)