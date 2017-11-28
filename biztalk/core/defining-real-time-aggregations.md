---
title: "リアルタイム集計の定義 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- real-time data, aggregating
- aggregations [BAM], real-time data
ms.assetid: cb3d7124-1663-4af2-9540-4171cc51568a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2b2df32149f67a002a5a6281b6f1abd848523a6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="defining-real-time-aggregations"></a><span data-ttu-id="41ace-102">リアルタイム集計の定義</span><span class="sxs-lookup"><span data-stu-id="41ace-102">Defining Real-Time Aggregations</span></span>
<span data-ttu-id="41ace-103">場合によっては、多次元集計の特定のスライスはので時間を区別することをリアルタイムで使用することです。</span><span class="sxs-lookup"><span data-stu-id="41ace-103">In some cases, specific slices of the multi-dimensional aggregations are so time- sensitive that you want them to be available in real time.</span></span> <span data-ttu-id="41ace-104">たとえば、生鮮食料品を販売する業者では、配送の各段階での製品数量の集計をリアルタイムで利用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="41ace-104">For example, your business is selling perishable products and you want the aggregation of product quantity in different stages of delivery to be available in real time.</span></span> <span data-ttu-id="41ace-105">同時に、代表的な顧客の年齢などの他の集計を、ビジネス インテリジェンス分析のために月末にのみ実行する必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="41ace-105">At the same time, you want other aggregations such as the age of your typical customers, but only at the end of the month for business intelligence analysis.</span></span>  
  
-   <span data-ttu-id="41ace-106">使用して、**ピボット テーブル**ツールバーで、該当する場合は、リアルタイム集計 (RTA) として選択した PivotTable をマークします。</span><span class="sxs-lookup"><span data-stu-id="41ace-106">Using the **PivotTable** toolbar, mark the selected PivotTable as a real-time aggregation (RTA), if applicable.</span></span> <span data-ttu-id="41ace-107">ピボットテーブルに格納されたデータの種類によって、データをリアルタイムで表示する必要があるかどうかが決まります。</span><span class="sxs-lookup"><span data-stu-id="41ace-107">The type of data contained in the PivotTable should determine whether it needs to be viewed in real time.</span></span> <span data-ttu-id="41ace-108">たとえば、1 時間ごとに Web 注文を追跡するレポートであればリアルタイムで表示する必要がありますが、1 日の販売総数を追跡するレポートであればリアルタイムで表示する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="41ace-108">For example, a report that tracks hourly Web orders might need to viewed in real time, whereas a report that tracks daily sales totals would not be viewed in real time.</span></span>  
  
     ![](../core/media/ebiz-sdk-sample-bam12.gif "ebiz_sdk_sample_bam12")  
<span data-ttu-id="41ace-109">[RTA] ボタン</span><span class="sxs-lookup"><span data-stu-id="41ace-109">RTA button</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="41ace-110">同じ BAM アクティビティを使用する RTA を複数定義しないでください。</span><span class="sxs-lookup"><span data-stu-id="41ace-110">Do not define multiple RTAs that use the same BAM activity.</span></span> <span data-ttu-id="41ace-111">そのような RTA を複数定義した場合、BAM データをアーカイブしたときに RTA データが不正確になります。</span><span class="sxs-lookup"><span data-stu-id="41ace-111">If you do so, the RTA data will be incorrect when you archive the BAM data.</span></span>  
  
 <span data-ttu-id="41ace-112">ピボットテーブルの詳細については、Excel のオンライン ヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="41ace-112">For more information about Pivot tables, see Excel online help.</span></span> <span data-ttu-id="41ace-113">ピボットテーブルを作成すると、ライブ BAM データを表示できます。</span><span class="sxs-lookup"><span data-stu-id="41ace-113">After you create your Pivot table, you can view your live BAM data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41ace-114">参照</span><span class="sxs-lookup"><span data-stu-id="41ace-114">See Also</span></span>  
 <span data-ttu-id="41ace-115">[ライブ BAM データの表示](../core/viewing-live-bam-data.md) </span><span class="sxs-lookup"><span data-stu-id="41ace-115">[Viewing Live BAM Data](../core/viewing-live-bam-data.md) </span></span>  
 <span data-ttu-id="41ace-116">[進捗ディメンション](../core/progress-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="41ace-116">[Progress Dimension](../core/progress-dimension.md) </span></span>  
 <span data-ttu-id="41ace-117">[データ ディメンション](../core/data-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="41ace-117">[Data Dimension](../core/data-dimension.md) </span></span>  
 <span data-ttu-id="41ace-118">[時間ディメンション](../core/time-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="41ace-118">[Time Dimension](../core/time-dimension.md) </span></span>  
 <span data-ttu-id="41ace-119">[数値範囲ディメンション](../core/numeric-range-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="41ace-119">[Numeric Range Dimension](../core/numeric-range-dimension.md) </span></span>  
 [<span data-ttu-id="41ace-120">ディメンションの定義</span><span class="sxs-lookup"><span data-stu-id="41ace-120">Defining Dimensions</span></span>](../core/defining-dimensions.md)