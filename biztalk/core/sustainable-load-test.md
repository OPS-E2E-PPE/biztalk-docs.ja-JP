---
title: 維持可能なロード テスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- sustainable load test
- LoadGen tool, sustainable load test
ms.assetid: a9d752ff-aff1-4445-8af5-8f84609880e2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d059f7f2aa29be68ea87d72d9357d01601d2c958
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65321769"
---
# <a name="sustainable-load-test"></a><span data-ttu-id="1b770-102">維持可能なロード テスト</span><span class="sxs-lookup"><span data-stu-id="1b770-102">Sustainable Load Test</span></span>
<span data-ttu-id="1b770-103">このトピックの情報を指すで説明されているテスト[エンジンの MST を測定するテストのシナリオ](../core/test-scenarios-for-measuring-mst-of-the-engine.md)します。</span><span class="sxs-lookup"><span data-stu-id="1b770-103">The information in this topic refers to the tests explained in [Test Scenarios for Measuring MST of the Engine](../core/test-scenarios-for-measuring-mst-of-the-engine.md).</span></span>  
  
 <span data-ttu-id="1b770-104">最初のテストでは、システムは MST に到達する駆動が正常なシステムの観測にできるようにします。</span><span class="sxs-lookup"><span data-stu-id="1b770-104">For the first test, the system was driven to MST so that observations of a healthy system can be made.</span></span>  
  
 <span data-ttu-id="1b770-105">次のグラフは、このアプローチを使用して、テスト システムの維持可能な最大スループットの調査した後、主要な指標を示します。</span><span class="sxs-lookup"><span data-stu-id="1b770-105">The following graph shows key indicators after using this approach to find the maximum sustainable throughput of the test system.</span></span>  
  
 <span data-ttu-id="1b770-106">**維持可能なロード テストのロード プロファイル**</span><span class="sxs-lookup"><span data-stu-id="1b770-106">**Load profile of sustainable load test**</span></span>  
  
 <span data-ttu-id="1b770-107">![パフォーマンス モニターの測定の維持可能なロード](../core/media/bts06-sustainable-load.gif "BTS06_Sustainable_Load")</span><span class="sxs-lookup"><span data-stu-id="1b770-107">![Performance monitor measuring sustainable load](../core/media/bts06-sustainable-load.gif "BTS06_Sustainable_Load")</span></span>  
  
 <span data-ttu-id="1b770-108">このグラフは、テストの時間、スプールの深さが安定し、増大しなかったを示しています。</span><span class="sxs-lookup"><span data-stu-id="1b770-108">This graph shows that, for the hour of the test, the spool depth was stable and not growing:</span></span>  
  
- <span data-ttu-id="1b770-109">グラフの上部にある黒い線は、(たとえばの受信側サーバーの両方)、システムによって 1 秒あたりに受信したメッセージの総数を表示します。</span><span class="sxs-lookup"><span data-stu-id="1b770-109">The black lines at the top of the graph show the total messages received per second by the system (for example, for both of the receiving servers).</span></span>  
  
- <span data-ttu-id="1b770-110">グラフの下部にある行は、SQL サーバーごとに、メッセージ ボックス スプールの深さを示します。</span><span class="sxs-lookup"><span data-stu-id="1b770-110">The lines at the bottom of the graph indicate the MessageBox spool depth on each of the SQL Servers.</span></span>  
  
  <span data-ttu-id="1b770-111">システムを駆動するには、最大の安定したスプールの深さのポイントすると、MST は 1 秒あたりに受信したメッセージの数によって測定されます。</span><span class="sxs-lookup"><span data-stu-id="1b770-111">Once the system is driven to the point of the maximum stable spool depth, MST is measured by the number of messages received per second.</span></span> <span data-ttu-id="1b770-112">このシナリオで説明されている、ハードウェアで 290 メッセージ/秒の MST が行われました。</span><span class="sxs-lookup"><span data-stu-id="1b770-112">For this scenario, on the hardware described, an MST of 290 messages per second was achieved.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b770-113">システムを駆動するには、スプールの深さが安定しなく時間の経過と共に、ポイントするとは、MST を超過しています。</span><span class="sxs-lookup"><span data-stu-id="1b770-113">Once the system is driven to a point where the spool depth is no longer stable over time, MST has been exceeded.</span></span> <span data-ttu-id="1b770-114">変化する負荷をいくつかのテストの実行がどのスプールの深さが安定した最大負荷を評価する必要があるし、システムは、追加のメッセージ バックログを発生させずにメッセージのバックログを処理できます。</span><span class="sxs-lookup"><span data-stu-id="1b770-114">Several test runs with varying load may be required to evaluate the maximum load at which spool depth remains stable and your system can handle the message backlog without incurring additional message backlog.</span></span>  
  
 <span data-ttu-id="1b770-115">BizTalk 展開のパフォーマンスの分析の一部では、リソースのボトルネックを理解する主要な指標のチェックを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b770-115">Part of any analysis of a BizTalk deployment performance should include checking some key indicators to understand resource bottlenecks.</span></span> <span data-ttu-id="1b770-116">キーのメジャーと最大持続可能スループットで実行されているこの展開に使用される、値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1b770-116">The key measures and their values used for this deployment running under maximum sustainable throughput were as follows:</span></span>  
  
 <span data-ttu-id="1b770-117">**CPU 使用率**</span><span class="sxs-lookup"><span data-stu-id="1b770-117">**CPU Utilization**</span></span>  
  
|<span data-ttu-id="1b770-118">[サーバー]</span><span class="sxs-lookup"><span data-stu-id="1b770-118">Server</span></span>|<span data-ttu-id="1b770-119">平均 CPU 使用率</span><span class="sxs-lookup"><span data-stu-id="1b770-119">Average CPU Utilization</span></span>|  
|------------|-----------------------------|  
|<span data-ttu-id="1b770-120">BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="1b770-120">BizTalk Servers</span></span>|<span data-ttu-id="1b770-121">55%</span><span class="sxs-lookup"><span data-stu-id="1b770-121">55%</span></span>|  
|<span data-ttu-id="1b770-122">SQL Server (マスター メッセージ ボックス サーバー)</span><span class="sxs-lookup"><span data-stu-id="1b770-122">SQL Server (Master MessageBox Server)</span></span>|<span data-ttu-id="1b770-123">76%</span><span class="sxs-lookup"><span data-stu-id="1b770-123">76%</span></span>|  
|<span data-ttu-id="1b770-124">SQL Server (他のメッセージ ボックス サーバー)</span><span class="sxs-lookup"><span data-stu-id="1b770-124">SQL Server (Other MessageBox Servers)</span></span>|<span data-ttu-id="1b770-125">83%</span><span class="sxs-lookup"><span data-stu-id="1b770-125">83%</span></span>|  
  
 <span data-ttu-id="1b770-126">**物理ディスクのアイドル時間**</span><span class="sxs-lookup"><span data-stu-id="1b770-126">**Physical Disk Idle Time**</span></span>  
  
|<span data-ttu-id="1b770-127">[サーバー]</span><span class="sxs-lookup"><span data-stu-id="1b770-127">Server</span></span>|<span data-ttu-id="1b770-128">ディスクの平均アイドル時間</span><span class="sxs-lookup"><span data-stu-id="1b770-128">Average Disk Idle Time</span></span>|  
|------------|----------------------------|  
|<span data-ttu-id="1b770-129">すべての SQL Server の平均値</span><span class="sxs-lookup"><span data-stu-id="1b770-129">Average for all SQL Servers</span></span>|<span data-ttu-id="1b770-130">69%</span><span class="sxs-lookup"><span data-stu-id="1b770-130">69%</span></span>|  
  
 <span data-ttu-id="1b770-131">**SQL Server の SQL ロック**</span><span class="sxs-lookup"><span data-stu-id="1b770-131">**SQL Locks on SQL Server**</span></span>  
  
|<span data-ttu-id="1b770-132">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1b770-132">Parameter</span></span>|<span data-ttu-id="1b770-133">値</span><span class="sxs-lookup"><span data-stu-id="1b770-133">Value</span></span>|  
|---------------|-----------|  
|<span data-ttu-id="1b770-134">ロック タイムアウト合計平均/秒 (SQL Server) 数</span><span class="sxs-lookup"><span data-stu-id="1b770-134">Average Total Lock Timeouts per second (per SQL Server)</span></span>|<span data-ttu-id="1b770-135">1980</span><span class="sxs-lookup"><span data-stu-id="1b770-135">1980</span></span>|  
|<span data-ttu-id="1b770-136">平均合計ロック待機時間 (ミリ秒)</span><span class="sxs-lookup"><span data-stu-id="1b770-136">Average Total Lock Wait Time (ms)</span></span>|<span data-ttu-id="1b770-137">495</span><span class="sxs-lookup"><span data-stu-id="1b770-137">495</span></span>|  
  
 <span data-ttu-id="1b770-138">このテスト中にエラーが生成されましたない BizTalk または SQL Server アプリケーション ログにします。</span><span class="sxs-lookup"><span data-stu-id="1b770-138">During this test no errors were generated in the BizTalk or SQL Server application log.</span></span>  
  
 <span data-ttu-id="1b770-139">このデータから、次の結論を描画できます。</span><span class="sxs-lookup"><span data-stu-id="1b770-139">From this data, we can draw the following conclusions:</span></span>  
  
- <span data-ttu-id="1b770-140">システム内では、明らかなリソース ボトルネックはありません。</span><span class="sxs-lookup"><span data-stu-id="1b770-140">There are no obvious resource bottlenecks in our system.</span></span>  
  
- <span data-ttu-id="1b770-141">これらのインジケーターのすべては、正常な制限範囲内です。</span><span class="sxs-lookup"><span data-stu-id="1b770-141">All of these indicators are well within healthy limits.</span></span>  
  
- <span data-ttu-id="1b770-142">CPU とディスク アイドル時間は、余裕があるし、設定されているもの近くにいないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="1b770-142">CPU and Disk Idle Times show that there is plenty of headroom and they are not even close to being pegged.</span></span>  
  
- <span data-ttu-id="1b770-143">SQL ロック インジケーターは見栄え**Lock timeouts/sec**までおよそ 5000 (SQL Server) によって問題なく起動しないロック待機時間 1 秒以下でされても正常な状態です。</span><span class="sxs-lookup"><span data-stu-id="1b770-143">The SQL lock indicators look good, **Lock Timeouts/sec** doesn’t start to become an issue until around 5000 or so (depending on your SQL Server) and Lock Wait times under 1 second are also healthy.</span></span>  
  
  <span data-ttu-id="1b770-144">最大持続可能スループットを検索する方法について説明し、維持可能な正常なシステムの主要な指標がどのように表示されることが、処理と収集よりも高速化を受信しているシステムに関連付けられているいくつかの動作を見てみましょうガベージ。</span><span class="sxs-lookup"><span data-stu-id="1b770-144">Now that we have shown how to find the maximum sustainable throughput and seen what the key indicators look like for a sustainable, healthy system, let’s explore some behavior associated with a system that is receiving faster than it is processing and collecting garbage.</span></span> <span data-ttu-id="1b770-145">続行する[ロード テストをオーバー ドライブ](../core/overdrive-load-test.md)します。</span><span class="sxs-lookup"><span data-stu-id="1b770-145">Proceed to [Overdrive Load Test](../core/overdrive-load-test.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b770-146">参照</span><span class="sxs-lookup"><span data-stu-id="1b770-146">See Also</span></span>  
 <span data-ttu-id="1b770-147">[エンジンの MST を測定するためのテスト シナリオ](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span><span class="sxs-lookup"><span data-stu-id="1b770-147">[Test Scenarios for Measuring MST of the Engine](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span></span>  
 [<span data-ttu-id="1b770-148">オーバードライブ ロード テスト</span><span class="sxs-lookup"><span data-stu-id="1b770-148">Overdrive Load Test</span></span>](../core/overdrive-load-test.md)