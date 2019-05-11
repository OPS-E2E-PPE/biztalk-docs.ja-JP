---
title: メジャーとディメンションとは | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e6b12a4c-9be5-4cac-b5b9-ece376d28cb1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c07f7ac1f3a0105549c01209e008bd880e0444c0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302306"
---
# <a name="what-are-measures-and-dimensions"></a><span data-ttu-id="f6bdf-103">メジャーとディメンションとは</span><span class="sxs-lookup"><span data-stu-id="f6bdf-103">What Are Measures and Dimensions?</span></span>
<span data-ttu-id="f6bdf-104">ディメンションとメジャーはデータ集計の物理的な要素です。</span><span class="sxs-lookup"><span data-stu-id="f6bdf-104">Dimensions and measures are the physical aspects of data aggregation.</span></span> <span data-ttu-id="f6bdf-105">ここでは、BAM シナリオを例に、メジャーとディメンションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f6bdf-105">This topic describes what measures and dimensions are, using a BAM scenario to provide context.</span></span>  
  
## <a name="measures"></a><span data-ttu-id="f6bdf-106">メジャー</span><span class="sxs-lookup"><span data-stu-id="f6bdf-106">Measures</span></span>  
 <span data-ttu-id="f6bdf-107">たとえば、受注管理プロセス用の BAM アクティビティを単純な条件で定義するとします。構成項目は次の 3 つです。</span><span class="sxs-lookup"><span data-stu-id="f6bdf-107">Suppose that you define a BAM activity for an order management process in extremely simple terms consisting of three items:</span></span>  
  
1. <span data-ttu-id="f6bdf-108">処理の開始時間 (実際に発生した時間)</span><span class="sxs-lookup"><span data-stu-id="f6bdf-108">Process start time (an event in the real world)</span></span>  
  
2. <span data-ttu-id="f6bdf-109">処理の終了時間 (実際に終わった時間)</span><span class="sxs-lookup"><span data-stu-id="f6bdf-109">Process end time (also a real-world event)</span></span>  
  
3. <span data-ttu-id="f6bdf-110">処理の所要時間 (2 から 1 を減算した値)</span><span class="sxs-lookup"><span data-stu-id="f6bdf-110">Process duration (a calculation of #2 - #1)</span></span>  
  
   <span data-ttu-id="f6bdf-111">この場合データを集計するには、個々の所要時間の値 (各注文の処理にかかった時間) のセットに対し、単に平均、最小値、最大値などの集計関数を適用します。</span><span class="sxs-lookup"><span data-stu-id="f6bdf-111">Aggregating data in this case is simply a matter of applying an aggregation function (for example, average, minimum, maximum, etc.) to a series of individual duration values (that is, the processing duration for each order).</span></span>  
  
   <span data-ttu-id="f6bdf-112">ここでは "平均所要時間" がメジャーとなります。このメジャーは単一の値をとり、</span><span class="sxs-lookup"><span data-stu-id="f6bdf-112">The concept of "average duration" is a measure, and it is a single value.</span></span> <span data-ttu-id="f6bdf-113">プロセス管理に関連する情報を生成します。この情報によって、処理全体がタイムラインとスループットの面から見て予定どおりに行われているかどうかが示されます。</span><span class="sxs-lookup"><span data-stu-id="f6bdf-113">By itself, this measure yields information relevant to process management in that it indicates whether or not the process overall is behaving (in terms of timliness/throughput) as expected.</span></span> <span data-ttu-id="f6bdf-114">しかし、"平均所要時間" は単一の値なので、他のデータがないとメジャーの実際の値が意味することを読み取るのは難しくなります。たとえば、今週の平均所要時間が急に変化した理由が</span><span class="sxs-lookup"><span data-stu-id="f6bdf-114">However, in the absence of any other data (because "average duration" is a single value), understanding the meaning of the measure's actual value is harder For example, why did we have a spike in average duration this week?</span></span> <span data-ttu-id="f6bdf-115">特定のパートナーによるものか、プログラムによるものか、製品によるものかということはわかりません。</span><span class="sxs-lookup"><span data-stu-id="f6bdf-115">Was it due to a particular partner, program, product?</span></span>  
  
## <a name="dimensions"></a><span data-ttu-id="f6bdf-116">ディメンション</span><span class="sxs-lookup"><span data-stu-id="f6bdf-116">Dimensions</span></span>  
 <span data-ttu-id="f6bdf-117">ディメンションはコンテキストを表し、メジャーの意味を理解しようとするときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f6bdf-117">Dimensions are the context that help the consumer of measures understand the meaning of those measures.</span></span>  
  
 <span data-ttu-id="f6bdf-118">上の例の続きで、受注管理プロセス用の BAM アクティビティに次の 3 つの項目を追加するとします。</span><span class="sxs-lookup"><span data-stu-id="f6bdf-118">Continuing the above example, suppose you add three additional items to the BAM activity for the order management process:</span></span>  
  
1. <span data-ttu-id="f6bdf-119">取引先の名前 (発注元)</span><span class="sxs-lookup"><span data-stu-id="f6bdf-119">trading partner name (who sent the order)</span></span>  
  
2. <span data-ttu-id="f6bdf-120">経理課長の名前 (販売連絡先)</span><span class="sxs-lookup"><span data-stu-id="f6bdf-120">account manager name (who is the sales contact)</span></span>  
  
3. <span data-ttu-id="f6bdf-121">販売地域</span><span class="sxs-lookup"><span data-stu-id="f6bdf-121">sales region</span></span>  
  
   <span data-ttu-id="f6bdf-122">アクティビティに 3 つのデータ軸 (取引先、経理課長、地域) が追加されたので、このデータを集計すると、実行時に 3 次元のキューブが作成されることになります。</span><span class="sxs-lookup"><span data-stu-id="f6bdf-122">Since the activity now includes three possible data pivots (partner, account manager, region), aggregating this data now literally results in the creation of a three-dimensional cube at run-time.</span></span>  
  
   <span data-ttu-id="f6bdf-123">このアクティビティでは、最初の処理が発生したときに "平均所要時間" の単一メジャーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f6bdf-123">It still begins with the first item of work, resulting in the creation of a single "average duration" measure.</span></span> <span data-ttu-id="f6bdf-124">別の注文書が届き、2 つ目の処理が発生した場合、取引先、経理課長、地域がすべて最初の処理と同じであれば、完了時 2 つの処理を基に (2 つの所要時間の平均として) "平均所要時間" メジャーが再計算されます。ここで導き出される "平均所要時間" メジャーの値は 1 つです。</span><span class="sxs-lookup"><span data-stu-id="f6bdf-124">When the next item of work (initiated by the arrival of another purchase order) completes, if trading partner, account manager, and region are all the same as they were for the first item of work, then all that happens is that the "average duration" measure is recalculated, based now on two items (for example, the average of the two durations), to achieve a single "average duration" measure value.</span></span>  
  
   <span data-ttu-id="f6bdf-125">3 つ目の処理が発生し、取引先、経理部長、地域のいずれかがそれまでと異なる場合は、処理が始まるとすぐ新しい "平均所要時間" メジャーの値が作成され、最初の値とは別に保持されます。</span><span class="sxs-lookup"><span data-stu-id="f6bdf-125">As soon as an item comes where any of trading partner, account manager, or region are different than the set encountered so far, a new "average duration" measure value is created and maintained separate from the first one.</span></span>  
  
   <span data-ttu-id="f6bdf-126">たとえば、3 つ目の処理の取引先が最初の 2 つと異なる場合は、取引先ディメンションに 2 つ目の "平均所要時間" メジャーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f6bdf-126">For example, if the trading partner on the third item of work was different than the previous two, the result is creation of a second "average duration" measure value along the trading partner dimension.</span></span> <span data-ttu-id="f6bdf-127">取引先ディメンションの "平均所要時間" の値を確認すると、"ここまでで、TradingPartnerX には、TradingPartnerY の平均 2 倍の処理時間かかっている" ということがわかります。</span><span class="sxs-lookup"><span data-stu-id="f6bdf-127">Now you can review "average duration" values along the trading partner dimension and see things like "it takes us almost twice as long on average to process the orders from TradingPartnerX as it does for TradingPartnerY."</span></span> <span data-ttu-id="f6bdf-128">ディメンションは折りたたんで表示でき、取引先やその他のディメンションとは関係なく全体の "平均所要時間" を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f6bdf-128">And dimensions can be collapsed for viewing so that one can still see the overall "average duration" for the process independent of any trading partner or other dimension.</span></span>  
  
   <span data-ttu-id="f6bdf-129">取引先、経理課長、地域のそれぞれが 3 つの処理とも異なる値であった場合は、これらの値が揃った時点でデータはルービック キューブ (Rubik's&reg; Cube) のようになります。ユーザーは 27 個の値すべてにそれぞれの "平均所要時間" が保持されていることと、キューブの 3 辺がそれぞれのディメンションになっていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="f6bdf-129">Finally, if trading partner, account manager, and region each have three and only three distinct values, once all permutations have occurred, the result is a Rubik's® Cube of data, where users can view each of 27 independently maintained "average duration" values, and the dimensions are each of three edges on the cube.</span></span>  
  
   <span data-ttu-id="f6bdf-130">ディメンションとメジャーの追加情報については、Excel ヘルプの「OLAP データを使ってピボットテーブル レポートまたはピボットグラフ レポートを作成する方法について」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6bdf-130">For additional information about dimensions and measures, see "About OLAP source data in PivotTable and PivotChart reports" in Excel Help.</span></span>