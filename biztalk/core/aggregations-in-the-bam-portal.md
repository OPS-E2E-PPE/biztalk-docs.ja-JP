---
title: BAM ポータルでの集計 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM portal, pivot tables
- BAM, data analysis
- pivot tables [BAM portal]
- BAM portal, charts
- data, analysis [BAM]
- data, OLAP cubes
- aggregations [BAM], BAM portal
- charts, BAM portal
- BAM portal, aggregations
ms.assetid: 1c689563-714b-4573-9c18-a5b0efe97fb8
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14496535f12171be1d391ebe88312a9730c36953
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986947"
---
# <a name="aggregations-in-the-bam-portal"></a><span data-ttu-id="46368-102">BAM ポータルでの集計</span><span class="sxs-lookup"><span data-stu-id="46368-102">Aggregations in the BAM Portal</span></span>
<span data-ttu-id="46368-103">集計とは、OLAP キューブで分析処理を行う際に使用できる事前計算されたデータのテーブルです。</span><span class="sxs-lookup"><span data-stu-id="46368-103">Aggregations are tables of precalculated data you can use for analytical processing with an OLAP cube.</span></span> <span data-ttu-id="46368-104">集計を使用すると、多次元データベースを効率的にクエリできるようになります。</span><span class="sxs-lookup"><span data-stu-id="46368-104">Aggregations facilitate the efficient querying of multidimensional databases.</span></span> <span data-ttu-id="46368-105">Excel 用の BAM アドインを使用して監視モデル (ビジネス データの概要定義) を作成および展開すると、集計が作成されます。この集計を使用すると、主要業績評価指数 (KPI) と関連のあるデータのコレクションを迅速に評価することができます。</span><span class="sxs-lookup"><span data-stu-id="46368-105">When you create and deploy your observation model (the high-level definition of your business data) using the BAM Add-In for Excel, you create aggregations that you can use to quickly evaluate collections of data relating your Key Performance Indicators (KPIs).</span></span>  
  
## <a name="types-of-aggregations"></a><span data-ttu-id="46368-106">集計の種類</span><span class="sxs-lookup"><span data-stu-id="46368-106">Types of aggregations</span></span>  
 <span data-ttu-id="46368-107">集計には、スケジュール済みの集計とリアルタイム集計があります。</span><span class="sxs-lookup"><span data-stu-id="46368-107">Aggregations can be either scheduled or real-time.</span></span> <span data-ttu-id="46368-108">スケジュール済みの集計は OLAP キューブであり、指定した時刻のビジネス データのスナップショットを表します。</span><span class="sxs-lookup"><span data-stu-id="46368-108">Scheduled aggregations are OLAP cubes, which represent a snapshot of your business data at a time you specify.</span></span> <span data-ttu-id="46368-109">リアルタイム集計では、指定したトリガー ポイントに基づいてビジネス データを表示でき、KPI に達した直後に BAM システムから通知が送信されるようにできます。</span><span class="sxs-lookup"><span data-stu-id="46368-109">Real-time aggregations allow a view of your business data based on trigger points that you specify, allowing the BAM system to notify you through an alert as soon as a KPI has been reached.</span></span>  
  
## <a name="pivottable-view"></a><span data-ttu-id="46368-110">ピボットテーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="46368-110">PivotTable View</span></span>  
 <span data-ttu-id="46368-111">ピボットテーブル ビュー領域には、Excel 用の BAM アドインを使用してデザインしたピボットテーブル レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="46368-111">The PivotTable View area displays the PivotTable report that you design using the BAM Add-In for Excel.</span></span> <span data-ttu-id="46368-112">Office Web コンポーネントでは、ニーズに合った最適なデータのビューを表示するピボット テーブル レポートを操作できます.</span><span class="sxs-lookup"><span data-stu-id="46368-112">The Office Web Components allow you to manipulate the PivotTable report to present the view of the data that best fits your needs..</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="46368-113">リアルタイム集計 (RTA) と事前計算済みの集計 (OLAP 実装) のどちらを使用した場合でも、アクティビティのマイルストーンに達したときに、そのマイルストーンが進捗ディメンションで使用されていなければ、ピボットテーブル レポートを表示しても、一部の行に空のデータが含まれることがあります。</span><span class="sxs-lookup"><span data-stu-id="46368-113">When viewing a PivotTable report it is possible that some rows could contain null data in both real-time aggregations (RTAs) and precalculated aggregations (an OLAP implementation) if the milestones in the activity have been reached but are not used in the progress dimension.</span></span> <span data-ttu-id="46368-114">また、進捗ディメンションのコンテキストで時間ディメンションが使用され、"確認済み" または "受信" マイルストーンに固定されている場合は、空のデータが設定された行が含まれることがあります。</span><span class="sxs-lookup"><span data-stu-id="46368-114">It is also possible to encounter rows with null data if the time dimension is used in the context of a progress dimension and is anchored to a milestone such as "acknowledged" instead of "received."</span></span> <span data-ttu-id="46368-115">この場合、アクティビティ インスタンスが受信され、受信マイルストーンがトリガーされます。ただし、アクティビティでは、確認済みマイルストーンがトリガーされていないため、時間ディメンションの行に 0 が表示されます。</span><span class="sxs-lookup"><span data-stu-id="46368-115">In this case an activity instance is received and triggers the received milestone, but the activity has not yet triggered the acknowledge milestone and a zero will appear in the time dimension row.</span></span>  <span data-ttu-id="46368-116">このような状況を回避するには、時間ディメンションを受信マイルストーンまでリンクします。</span><span class="sxs-lookup"><span data-stu-id="46368-116">To avoid this situation, link the time dimension up to the received milestone.</span></span>  
  
 <span data-ttu-id="46368-117">![](../core/media/aggregationpivottabletotal.gif "AggregationPivotTableTotal")</span><span class="sxs-lookup"><span data-stu-id="46368-117">![](../core/media/aggregationpivottabletotal.gif "AggregationPivotTableTotal")</span></span>  
  
 <span data-ttu-id="46368-118">BAM ポータルでピボットテーブル レポートを変更する際に Office Web コンポーネントを使用する場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="46368-118">Keep these points in mind when using the Office Web Components in the BAM portal to modify your PivotTable report:</span></span>  
  
- <span data-ttu-id="46368-119">Excel のピボットテーブル レポートには、タイム スライス ディメンションを設定できるページ フィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="46368-119">PivotTable reports in Excel include a Page field where you can put a time slice dimension.</span></span> <span data-ttu-id="46368-120">BAM ポータルで使用される Office Web コンポーネントでは、ページのフィールドは含まれません。</span><span class="sxs-lookup"><span data-stu-id="46368-120">The Office Web Components used by the BAM portal do not include a Page field.</span></span> <span data-ttu-id="46368-121">Excel のピボットテーブル レポートで、ディメンションにページ フィールドを使用している場合、BAM ポータルのピボットテーブル レポートではページ フィールドのデータは表示されません。</span><span class="sxs-lookup"><span data-stu-id="46368-121">If your Excel PivotTable report uses the Page field for any dimensions, the data for this field is not displayed in your PivotTable report in the BAM portal.</span></span>  
  
- <span data-ttu-id="46368-122">Office Web コンポーネントは、BAM ポータルのコンテンツ フレームにデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="46368-122">The Office Web Components display data in the content frame of the BAM portal.</span></span> <span data-ttu-id="46368-123">このフレームの領域の制限により、フィールドの一覧から列の領域にディメンションを追加すると、ピボットテーブル レポートでは、ディメンション名の一部または全体が表示されなくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="46368-123">Because of the space limitations of this frame, adding dimensions from the field list to the columns area can cause the display of the PivotTable to move dimension names partly or wholly out of view.</span></span>  
  
  <span data-ttu-id="46368-124">ピボット テーブルの詳細についてを参照してください「ピボット テーブルの用語集」 [ http://go.microsoft.com/fwlink/?LinkId=55416](http://go.microsoft.com/fwlink/?LinkId=55416)します。</span><span class="sxs-lookup"><span data-stu-id="46368-124">For more information about PivotTables, see "PivotTable terminology demystified" at [http://go.microsoft.com/fwlink/?LinkId=55416](http://go.microsoft.com/fwlink/?LinkId=55416).</span></span>  
  
## <a name="chart-view"></a><span data-ttu-id="46368-125">グラフ ビュー</span><span class="sxs-lookup"><span data-stu-id="46368-125">Chart View</span></span>  
 <span data-ttu-id="46368-126">グラフ ビュー領域に表示される集計はグラフィカル インターフェイスで操作できます。</span><span class="sxs-lookup"><span data-stu-id="46368-126">The Chart View area displays the aggregation in a graphical manner.</span></span> <span data-ttu-id="46368-127">Office Web コンポーネントを使用すると、グラフ ビューを使用して集計の詳細を操作し、必要に応じてレポートに表示されるデータを調整することができます。</span><span class="sxs-lookup"><span data-stu-id="46368-127">The Office Web Components allow you to manipulate the details of the aggregation through the chart view to adjust the reported data as needed.</span></span> <span data-ttu-id="46368-128">グラフ フィールドの一覧からデータ項目をドラッグ アンド ドロップして集計を調整すると、その集計のピボットテーブル レポートでは調整内容が自動的に反映されます。</span><span class="sxs-lookup"><span data-stu-id="46368-128">When you adjust the aggregation by dragging and dropping data items from the Chart Field list, the PivotTable report for the aggregation is automatically updated to reflect your changes.</span></span> <span data-ttu-id="46368-129">また、ピボットテーブル レポートをドリルスルーして、新しい集計ビューに警告を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="46368-129">You can drill through the PivotTable to create an alert on the new aggregation view.</span></span>  
  
 <span data-ttu-id="46368-130">![](../core/media/aggregationchartview.gif "AggregationChartView")</span><span class="sxs-lookup"><span data-stu-id="46368-130">![](../core/media/aggregationchartview.gif "AggregationChartView")</span></span>  
  
## <a name="more"></a><span data-ttu-id="46368-131">もっとその</span><span class="sxs-lookup"><span data-stu-id="46368-131">More</span></span>  
  
-   [<span data-ttu-id="46368-132">アラートを設定する方法</span><span class="sxs-lookup"><span data-stu-id="46368-132">How to Set an Alert</span></span>](../core/how-to-set-an-alert.md)  
  
-   [<span data-ttu-id="46368-133">アクティビティの検索の結果を表示する方法</span><span class="sxs-lookup"><span data-stu-id="46368-133">How to View the Results of an Activity Search</span></span>](../core/how-to-view-the-results-of-an-activity-search.md)  
  
-   [<span data-ttu-id="46368-134">集計を変更する方法</span><span class="sxs-lookup"><span data-stu-id="46368-134">How to Modify an Aggregation</span></span>](../core/how-to-modify-an-aggregation.md)  
  
## <a name="see-also"></a><span data-ttu-id="46368-135">参照</span><span class="sxs-lookup"><span data-stu-id="46368-135">See Also</span></span>  
 [<span data-ttu-id="46368-136">集計について</span><span class="sxs-lookup"><span data-stu-id="46368-136">What Is an Aggregation?</span></span>](../core/what-is-an-aggregation.md)