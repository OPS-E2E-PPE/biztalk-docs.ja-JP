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
ms.openlocfilehash: 1055a76039420024a5cbfacf8e63094e00b1b8b5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360245"
---
# <a name="aggregations-in-the-bam-portal"></a><span data-ttu-id="dda60-102">BAM ポータルでの集計</span><span class="sxs-lookup"><span data-stu-id="dda60-102">Aggregations in the BAM Portal</span></span>
<span data-ttu-id="dda60-103">集計は、OLAP キューブで分析処理を使用できる事前計算済みのデータのテーブルです。</span><span class="sxs-lookup"><span data-stu-id="dda60-103">Aggregations are tables of precalculated data you can use for analytical processing with an OLAP cube.</span></span> <span data-ttu-id="dda60-104">集計は、多次元データベースの効率的なクエリを容易になります。</span><span class="sxs-lookup"><span data-stu-id="dda60-104">Aggregations facilitate the efficient querying of multidimensional databases.</span></span> <span data-ttu-id="dda60-105">作成して監視モデル (ビジネス データの高度な定義) を展開するときに、主要業績評価指標 (Kpi) に関連データのコレクションをすばやく評価するために使用できる集計を作成するために Excel 用 BAM アドインを使用して、します。</span><span class="sxs-lookup"><span data-stu-id="dda60-105">When you create and deploy your observation model (the high-level definition of your business data) using the BAM Add-In for Excel, you create aggregations that you can use to quickly evaluate collections of data relating your Key Performance Indicators (KPIs).</span></span>  
  
## <a name="types-of-aggregations"></a><span data-ttu-id="dda60-106">集計の種類</span><span class="sxs-lookup"><span data-stu-id="dda60-106">Types of aggregations</span></span>  
 <span data-ttu-id="dda60-107">集計には、リアルタイムまたはスケジュールのいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="dda60-107">Aggregations can be either scheduled or real-time.</span></span> <span data-ttu-id="dda60-108">スケジュール済みの集計は、OLAP キューブは、指定する時点で、ビジネス データのスナップショットを表します。</span><span class="sxs-lookup"><span data-stu-id="dda60-108">Scheduled aggregations are OLAP cubes, which represent a snapshot of your business data at a time you specify.</span></span> <span data-ttu-id="dda60-109">リアルタイム集計では、指定したトリガー ポイントに基づいて、KPI に達したとすぐにアラートを通知するように BAM システム ビジネス データのビューを許可します。</span><span class="sxs-lookup"><span data-stu-id="dda60-109">Real-time aggregations allow a view of your business data based on trigger points that you specify, allowing the BAM system to notify you through an alert as soon as a KPI has been reached.</span></span>  
  
## <a name="pivottable-view"></a><span data-ttu-id="dda60-110">ピボット テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="dda60-110">PivotTable View</span></span>  
 <span data-ttu-id="dda60-111">ピボット テーブル ビュー領域には、Excel 用 BAM アドインを使用して設計すること、ピボット テーブル レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dda60-111">The PivotTable View area displays the PivotTable report that you design using the BAM Add-In for Excel.</span></span> <span data-ttu-id="dda60-112">Office Web コンポーネントでは、ニーズに合った最適なデータのビューを表示するピボット テーブル レポートを操作できます.</span><span class="sxs-lookup"><span data-stu-id="dda60-112">The Office Web Components allow you to manipulate the PivotTable report to present the view of the data that best fits your needs..</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dda60-113">ピボット テーブル レポートを表示する場合、アクティビティのマイルス トーンに達したが、進行状況で使用されていない場合、いくつかの行にリアルタイム集計 (Rta) と事前計算済みの集計 (OLAP 実装) の両方で null データを含む可能性があることができます。ディメンションです。</span><span class="sxs-lookup"><span data-stu-id="dda60-113">When viewing a PivotTable report it is possible that some rows could contain null data in both real-time aggregations (RTAs) and precalculated aggregations (an OLAP implementation) if the milestones in the activity have been reached but are not used in the progress dimension.</span></span> <span data-ttu-id="dda60-114">時間ディメンションは、進捗ディメンションのコンテキストで使用しが固定されるマイルス トーン「確認」など、「受信」ではなく null データを持つ行が発生することも</span><span class="sxs-lookup"><span data-stu-id="dda60-114">It is also possible to encounter rows with null data if the time dimension is used in the context of a progress dimension and is anchored to a milestone such as "acknowledged" instead of "received."</span></span> <span data-ttu-id="dda60-115">ここでアクティビティ インスタンスが受信される受信マイルス トーンがトリガーがアクティビティによって確認済みマイルス トーンをまだトリガーされていないと、0 は、時間ディメンションの行に表示されます。</span><span class="sxs-lookup"><span data-stu-id="dda60-115">In this case an activity instance is received and triggers the received milestone, but the activity has not yet triggered the acknowledge milestone and a zero will appear in the time dimension row.</span></span>  <span data-ttu-id="dda60-116">このような状況を回避するには、受信マイルス トーンまでの時間ディメンションをリンクします。</span><span class="sxs-lookup"><span data-stu-id="dda60-116">To avoid this situation, link the time dimension up to the received milestone.</span></span>  
  
 <span data-ttu-id="dda60-117">![](../core/media/aggregationpivottabletotal.gif "AggregationPivotTableTotal")</span><span class="sxs-lookup"><span data-stu-id="dda60-117">![](../core/media/aggregationpivottabletotal.gif "AggregationPivotTableTotal")</span></span>  
  
 <span data-ttu-id="dda60-118">BAM ポータルで Office Web コンポーネントを使用して、ピボット テーブル レポートを変更するときに、これらの点に留意してください。</span><span class="sxs-lookup"><span data-stu-id="dda60-118">Keep these points in mind when using the Office Web Components in the BAM portal to modify your PivotTable report:</span></span>  
  
- <span data-ttu-id="dda60-119">Excel でピボット テーブル レポートには、時間スライス ディメンションを配置できるページ フィールドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="dda60-119">PivotTable reports in Excel include a Page field where you can put a time slice dimension.</span></span> <span data-ttu-id="dda60-120">BAM ポータルで使用される Office Web コンポーネントでは、ページのフィールドは含まれません。</span><span class="sxs-lookup"><span data-stu-id="dda60-120">The Office Web Components used by the BAM portal do not include a Page field.</span></span> <span data-ttu-id="dda60-121">Excel のピボット テーブル レポートでは、任意のディメンションにページ フィールドを使用している場合、BAM ポータルでピボット テーブル レポートでこのフィールドのデータは表示されません。</span><span class="sxs-lookup"><span data-stu-id="dda60-121">If your Excel PivotTable report uses the Page field for any dimensions, the data for this field is not displayed in your PivotTable report in the BAM portal.</span></span>  
  
- <span data-ttu-id="dda60-122">Office Web コンポーネントは、BAM ポータルのコンテンツ フレームにデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="dda60-122">The Office Web Components display data in the content frame of the BAM portal.</span></span> <span data-ttu-id="dda60-123">このフレームの領域の制限のため列の領域にフィールドの一覧からディメンションを追加と、ビューからディメンション名を部分的または完全に移動するピボット テーブルの表示が発生することができます。</span><span class="sxs-lookup"><span data-stu-id="dda60-123">Because of the space limitations of this frame, adding dimensions from the field list to the columns area can cause the display of the PivotTable to move dimension names partly or wholly out of view.</span></span>  
  
  <span data-ttu-id="dda60-124">ピボット テーブルの詳細についてを参照してください「ピボット テーブルの用語集」 [ http://go.microsoft.com/fwlink/?LinkId=55416](http://go.microsoft.com/fwlink/?LinkId=55416)します。</span><span class="sxs-lookup"><span data-stu-id="dda60-124">For more information about PivotTables, see "PivotTable terminology demystified" at [http://go.microsoft.com/fwlink/?LinkId=55416](http://go.microsoft.com/fwlink/?LinkId=55416).</span></span>  
  
## <a name="chart-view"></a><span data-ttu-id="dda60-125">グラフ ビュー</span><span class="sxs-lookup"><span data-stu-id="dda60-125">Chart View</span></span>  
 <span data-ttu-id="dda60-126">グラフ ビュー領域には、グラフィカルな方法で、集計が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dda60-126">The Chart View area displays the aggregation in a graphical manner.</span></span> <span data-ttu-id="dda60-127">Office Web コンポーネントを使用すると、必要に応じて、報告されるデータを調整するグラフの表示を使用して、集計の詳細を操作できます。</span><span class="sxs-lookup"><span data-stu-id="dda60-127">The Office Web Components allow you to manipulate the details of the aggregation through the chart view to adjust the reported data as needed.</span></span> <span data-ttu-id="dda60-128">ドラッグしてグラフのフィールド リストからデータ項目をドロップする集計を調整すると、集計のピボット テーブル レポートは、変更を反映するように自動的に更新します。</span><span class="sxs-lookup"><span data-stu-id="dda60-128">When you adjust the aggregation by dragging and dropping data items from the Chart Field list, the PivotTable report for the aggregation is automatically updated to reflect your changes.</span></span> <span data-ttu-id="dda60-129">新しい集計ビューにアラートを作成するピボット テーブルをドリルスルーすることができます。</span><span class="sxs-lookup"><span data-stu-id="dda60-129">You can drill through the PivotTable to create an alert on the new aggregation view.</span></span>  
  
 <span data-ttu-id="dda60-130">![](../core/media/aggregationchartview.gif "AggregationChartView")</span><span class="sxs-lookup"><span data-stu-id="dda60-130">![](../core/media/aggregationchartview.gif "AggregationChartView")</span></span>  
  
## <a name="more"></a><span data-ttu-id="dda60-131">もっとその</span><span class="sxs-lookup"><span data-stu-id="dda60-131">More</span></span>  
  
-   [<span data-ttu-id="dda60-132">アラートを設定する方法</span><span class="sxs-lookup"><span data-stu-id="dda60-132">How to Set an Alert</span></span>](../core/how-to-set-an-alert.md)  
  
-   [<span data-ttu-id="dda60-133">アクティビティの検索の結果を表示する方法</span><span class="sxs-lookup"><span data-stu-id="dda60-133">How to View the Results of an Activity Search</span></span>](../core/how-to-view-the-results-of-an-activity-search.md)  
  
-   [<span data-ttu-id="dda60-134">集計を変更する方法</span><span class="sxs-lookup"><span data-stu-id="dda60-134">How to Modify an Aggregation</span></span>](../core/how-to-modify-an-aggregation.md)  
  
## <a name="see-also"></a><span data-ttu-id="dda60-135">参照</span><span class="sxs-lookup"><span data-stu-id="dda60-135">See Also</span></span>  
 [<span data-ttu-id="dda60-136">集計について</span><span class="sxs-lookup"><span data-stu-id="dda60-136">What Is an Aggregation?</span></span>](../core/what-is-an-aggregation.md)