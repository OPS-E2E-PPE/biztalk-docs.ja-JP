---
title: リアルタイム集計の定義 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- real-time data, aggregating
- aggregations [BAM], real-time data
ms.assetid: cb3d7124-1663-4af2-9540-4171cc51568a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b585ba7f07ba6cd0f36a3fe2e68b92c50f4e206
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389699"
---
# <a name="defining-real-time-aggregations"></a><span data-ttu-id="6f152-102">リアルタイム集計の定義</span><span class="sxs-lookup"><span data-stu-id="6f152-102">Defining Real-Time Aggregations</span></span>
<span data-ttu-id="6f152-103">場合によっては、多次元集計の特定のスライスは時間を区別するためにリアルタイムで使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="6f152-103">In some cases, specific slices of the multi-dimensional aggregations are so time- sensitive that you want them to be available in real time.</span></span> <span data-ttu-id="6f152-104">たとえば、使い捨ての製品を販売しているお客様のビジネスとをリアルタイムで使用できる配信のさまざまな段階での製品の数量の集計します。</span><span class="sxs-lookup"><span data-stu-id="6f152-104">For example, your business is selling perishable products and you want the aggregation of product quantity in different stages of delivery to be available in real time.</span></span> <span data-ttu-id="6f152-105">同時に、必要なその他の集計、年齢などの一般的な顧客がビジネス インテリジェンス分析の月の最後にのみです。</span><span class="sxs-lookup"><span data-stu-id="6f152-105">At the same time, you want other aggregations such as the age of your typical customers, but only at the end of the month for business intelligence analysis.</span></span>  
  
-   <span data-ttu-id="6f152-106">使用して、**ピボット テーブル**ツールバーで、該当する場合は、リアルタイム集計 (RTA) として選択したピボット テーブルをマークします。</span><span class="sxs-lookup"><span data-stu-id="6f152-106">Using the **PivotTable** toolbar, mark the selected PivotTable as a real-time aggregation (RTA), if applicable.</span></span> <span data-ttu-id="6f152-107">ピボット テーブルに含まれるデータの種類には、リアルタイムで表示する必要があるかどうかが決まります。</span><span class="sxs-lookup"><span data-stu-id="6f152-107">The type of data contained in the PivotTable should determine whether it needs to be viewed in real time.</span></span> <span data-ttu-id="6f152-108">たとえば、Web 注文を 1 時間ごとに追跡するレポートは、毎日の売上合計を追跡するレポートをリアルタイムで表示しない場合は、リアルタイムで表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f152-108">For example, a report that tracks hourly Web orders might need to viewed in real time, whereas a report that tracks daily sales totals would not be viewed in real time.</span></span>  
  
     <span data-ttu-id="6f152-109">![](../core/media/ebiz-sdk-sample-bam12.gif "ebiz_sdk_sample_bam12")</span><span class="sxs-lookup"><span data-stu-id="6f152-109">![](../core/media/ebiz-sdk-sample-bam12.gif "ebiz_sdk_sample_bam12")</span></span>  
<span data-ttu-id="6f152-110">RTA ボタン</span><span class="sxs-lookup"><span data-stu-id="6f152-110">RTA button</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6f152-111">同じ BAM アクティビティを使用する RTA を複数定義しないでください。</span><span class="sxs-lookup"><span data-stu-id="6f152-111">Do not define multiple RTAs that use the same BAM activity.</span></span> <span data-ttu-id="6f152-112">そのような RTA を複数定義した場合、BAM データをアーカイブしたときに RTA データが不正確になります。</span><span class="sxs-lookup"><span data-stu-id="6f152-112">If you do so, the RTA data will be incorrect when you archive the BAM data.</span></span>  
  
 <span data-ttu-id="6f152-113">ピボット テーブルの詳細については、Excel のオンライン ヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f152-113">For more information about Pivot tables, see Excel online help.</span></span> <span data-ttu-id="6f152-114">ピボット テーブルを作成した後は、ライブ BAM データを表示できます。</span><span class="sxs-lookup"><span data-stu-id="6f152-114">After you create your Pivot table, you can view your live BAM data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f152-115">参照</span><span class="sxs-lookup"><span data-stu-id="6f152-115">See Also</span></span>  
 <span data-ttu-id="6f152-116">[ライブ BAM データの表示](../core/viewing-live-bam-data.md) </span><span class="sxs-lookup"><span data-stu-id="6f152-116">[Viewing Live BAM Data](../core/viewing-live-bam-data.md) </span></span>  
 <span data-ttu-id="6f152-117">[進捗ディメンション](../core/progress-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="6f152-117">[Progress Dimension](../core/progress-dimension.md) </span></span>  
 <span data-ttu-id="6f152-118">[データ ディメンション](../core/data-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="6f152-118">[Data Dimension](../core/data-dimension.md) </span></span>  
 <span data-ttu-id="6f152-119">[時間ディメンション](../core/time-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="6f152-119">[Time Dimension](../core/time-dimension.md) </span></span>  
 <span data-ttu-id="6f152-120">[数値範囲ディメンション](../core/numeric-range-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="6f152-120">[Numeric Range Dimension](../core/numeric-range-dimension.md) </span></span>  
 [<span data-ttu-id="6f152-121">ディメンションの定義</span><span class="sxs-lookup"><span data-stu-id="6f152-121">Defining Dimensions</span></span>](../core/defining-dimensions.md)