---
title: "維持可能なロード テスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- sustainable load test
- LoadGen tool, sustainable load test
ms.assetid: a9d752ff-aff1-4445-8af5-8f84609880e2
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a32f7ab31435cb81bee9e4ed52afc1f7d5194e8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sustainable-load-test"></a><span data-ttu-id="f1a36-102">維持可能なロード テスト</span><span class="sxs-lookup"><span data-stu-id="f1a36-102">Sustainable Load Test</span></span>
<span data-ttu-id="f1a36-103">このトピックの情報は、参照で説明されているテスト[エンジンの MST の測定のテスト シナリオ](../core/test-scenarios-for-measuring-mst-of-the-engine.md)です。</span><span class="sxs-lookup"><span data-stu-id="f1a36-103">The information in this topic refers to the tests explained in [Test Scenarios for Measuring MST of the Engine](../core/test-scenarios-for-measuring-mst-of-the-engine.md).</span></span>  
  
 <span data-ttu-id="f1a36-104">最初のテストでは、健全なシステムの監視を行えるように、MST に到達するまでシステムを駆動しました。</span><span class="sxs-lookup"><span data-stu-id="f1a36-104">For the first test, the system was driven to MST so that observations of a healthy system can be made.</span></span>  
  
 <span data-ttu-id="f1a36-105">次の図に、テスト システムの維持可能な最大スループットを見つけるためにこのアプローチを使用した後の主要な指標を示します。</span><span class="sxs-lookup"><span data-stu-id="f1a36-105">The following graph shows key indicators after using this approach to find the maximum sustainable throughput of the test system.</span></span>  
  
 <span data-ttu-id="f1a36-106">**維持可能なロード テストのロード プロファイル**</span><span class="sxs-lookup"><span data-stu-id="f1a36-106">**Load profile of sustainable load test**</span></span>  
  
 <span data-ttu-id="f1a36-107">![パフォーマンス モニターの測定の維持可能なロード](../core/media/bts06-sustainable-load.gif "BTS06_Sustainable_Load")</span><span class="sxs-lookup"><span data-stu-id="f1a36-107">![Performance monitor measuring sustainable load](../core/media/bts06-sustainable-load.gif "BTS06_Sustainable_Load")</span></span>  
  
 <span data-ttu-id="f1a36-108">このグラフは、テスト中、スプールの深さが安定し、増大しなかったことを示しています。</span><span class="sxs-lookup"><span data-stu-id="f1a36-108">This graph shows that, for the hour of the test, the spool depth was stable and not growing:</span></span>  
  
-   <span data-ttu-id="f1a36-109">グラフの最上部の黒い線は、1 秒あたりに受信したメッセージ総数をシステム別 (たとえば、両方の受信サーバーのシステムごと) に示しています。</span><span class="sxs-lookup"><span data-stu-id="f1a36-109">The black lines at the top of the graph show the total messages received per second by the system (for example, for both of the receiving servers).</span></span>  
  
-   <span data-ttu-id="f1a36-110">グラフの下部の線は、各 SQL Server のメッセージ ボックス スプールの深さを示しています。</span><span class="sxs-lookup"><span data-stu-id="f1a36-110">The lines at the bottom of the graph indicate the MessageBox spool depth on each of the SQL Servers.</span></span>  
  
 <span data-ttu-id="f1a36-111">安定したスプールの深さの最大値に到達するまでシステムを駆動すると、MST は 1 秒あたりに受信したメッセージ数で測定されます。</span><span class="sxs-lookup"><span data-stu-id="f1a36-111">Once the system is driven to the point of the maximum stable spool depth, MST is measured by the number of messages received per second.</span></span> <span data-ttu-id="f1a36-112">このシナリオでは、記載してあるハードウェアで 290 メッセージ/秒の MST に到達しました。</span><span class="sxs-lookup"><span data-stu-id="f1a36-112">For this scenario, on the hardware described, an MST of 290 messages per second was achieved.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1a36-113">時間の経過と共に、スプールの深さが安定しなくなる点までシステムを駆動すると、MST を超えます。</span><span class="sxs-lookup"><span data-stu-id="f1a36-113">Once the system is driven to a point where the spool depth is no longer stable over time, MST has been exceeded.</span></span> <span data-ttu-id="f1a36-114">スプールの深さの安定状態が保たれ、追加のメッセージ バックログを発生しないで、システムでメッセージ バックログを処理できる最大負荷を評価するには、さまざまな負荷を使用して複数のテストを実行する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="f1a36-114">Several test runs with varying load may be required to evaluate the maximum load at which spool depth remains stable and your system can handle the message backlog without incurring additional message backlog.</span></span>  
  
 <span data-ttu-id="f1a36-115">BizTalk 展開パフォーマンスを分析する際には、常にリソースのボトルネックについて理解するために主要な指標を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1a36-115">Part of any analysis of a BizTalk deployment performance should include checking some key indicators to understand resource bottlenecks.</span></span> <span data-ttu-id="f1a36-116">維持可能な最大スループットで実行されているこの展開で使用する主要な指標とその値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f1a36-116">The key measures and their values used for this deployment running under maximum sustainable throughput were as follows:</span></span>  
  
 <span data-ttu-id="f1a36-117">**CPU 使用率**</span><span class="sxs-lookup"><span data-stu-id="f1a36-117">**CPU Utilization**</span></span>  
  
|<span data-ttu-id="f1a36-118">[サーバー]</span><span class="sxs-lookup"><span data-stu-id="f1a36-118">Server</span></span>|<span data-ttu-id="f1a36-119">CPU の平均使用率</span><span class="sxs-lookup"><span data-stu-id="f1a36-119">Average CPU Utilization</span></span>|  
|------------|-----------------------------|  
|<span data-ttu-id="f1a36-120">BizTalk サーバー</span><span class="sxs-lookup"><span data-stu-id="f1a36-120">BizTalk Servers</span></span>|<span data-ttu-id="f1a36-121">55%</span><span class="sxs-lookup"><span data-stu-id="f1a36-121">55%</span></span>|  
|<span data-ttu-id="f1a36-122">SQL Server (マスター メッセージ ボックス サーバー)</span><span class="sxs-lookup"><span data-stu-id="f1a36-122">SQL Server (Master MessageBox Server)</span></span>|<span data-ttu-id="f1a36-123">76%</span><span class="sxs-lookup"><span data-stu-id="f1a36-123">76%</span></span>|  
|<span data-ttu-id="f1a36-124">SQL Server (その他のメッセージ ボックス サーバー)</span><span class="sxs-lookup"><span data-stu-id="f1a36-124">SQL Server (Other MessageBox Servers)</span></span>|<span data-ttu-id="f1a36-125">83%</span><span class="sxs-lookup"><span data-stu-id="f1a36-125">83%</span></span>|  
  
 <span data-ttu-id="f1a36-126">**物理ディスクのアイドル時間**</span><span class="sxs-lookup"><span data-stu-id="f1a36-126">**Physical Disk Idle Time**</span></span>  
  
|<span data-ttu-id="f1a36-127">[サーバー]</span><span class="sxs-lookup"><span data-stu-id="f1a36-127">Server</span></span>|<span data-ttu-id="f1a36-128">ディスク アイドル平均時間</span><span class="sxs-lookup"><span data-stu-id="f1a36-128">Average Disk Idle Time</span></span>|  
|------------|----------------------------|  
|<span data-ttu-id="f1a36-129">すべての SQL Server の平均</span><span class="sxs-lookup"><span data-stu-id="f1a36-129">Average for all SQL Servers</span></span>|<span data-ttu-id="f1a36-130">69%</span><span class="sxs-lookup"><span data-stu-id="f1a36-130">69%</span></span>|  
  
 <span data-ttu-id="f1a36-131">**SQL Server の SQL ロック**</span><span class="sxs-lookup"><span data-stu-id="f1a36-131">**SQL Locks on SQL Server**</span></span>  
  
|<span data-ttu-id="f1a36-132">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f1a36-132">Parameter</span></span>|<span data-ttu-id="f1a36-133">値</span><span class="sxs-lookup"><span data-stu-id="f1a36-133">Value</span></span>|  
|---------------|-----------|  
|<span data-ttu-id="f1a36-134">1 秒あたりのロック タイムアウト合計平均 (SQL Server ごと)</span><span class="sxs-lookup"><span data-stu-id="f1a36-134">Average Total Lock Timeouts per second (per SQL Server)</span></span>|<span data-ttu-id="f1a36-135">1980</span><span class="sxs-lookup"><span data-stu-id="f1a36-135">1980</span></span>|  
|<span data-ttu-id="f1a36-136">ロック待機時間合計平均 (ms)</span><span class="sxs-lookup"><span data-stu-id="f1a36-136">Average Total Lock Wait Time (ms)</span></span>|<span data-ttu-id="f1a36-137">495</span><span class="sxs-lookup"><span data-stu-id="f1a36-137">495</span></span>|  
  
 <span data-ttu-id="f1a36-138">このテスト中、BizTalk または SQL Server アプリケーション ログではエラーは生成されませんでした。</span><span class="sxs-lookup"><span data-stu-id="f1a36-138">During this test no errors were generated in the BizTalk or SQL Server application log.</span></span>  
  
 <span data-ttu-id="f1a36-139">このデータから、次の結論を下すことができます。</span><span class="sxs-lookup"><span data-stu-id="f1a36-139">From this data, we can draw the following conclusions:</span></span>  
  
-   <span data-ttu-id="f1a36-140">システムには明らかなリソース ボトルネックはありません。</span><span class="sxs-lookup"><span data-stu-id="f1a36-140">There are no obvious resource bottlenecks in our system.</span></span>  
  
-   <span data-ttu-id="f1a36-141">これらの指標はすべて健全な制限範囲内です。</span><span class="sxs-lookup"><span data-stu-id="f1a36-141">All of these indicators are well within healthy limits.</span></span>  
  
-   <span data-ttu-id="f1a36-142">CPU とディスク アイドル時間には、十分なヘッドルームがあり、いっぱいになるまでにはかなりの余裕があります。</span><span class="sxs-lookup"><span data-stu-id="f1a36-142">CPU and Disk Idle Times show that there is plenty of headroom and they are not even close to being pegged.</span></span>  
  
-   <span data-ttu-id="f1a36-143">SQL ロック インジケーターは見栄え**Lock timeouts/sec**までの周囲 5000 (SQL Server) によっては問題になるに起動しないロック待機時間で 1 秒間も、正常な状態とします。</span><span class="sxs-lookup"><span data-stu-id="f1a36-143">The SQL lock indicators look good, **Lock Timeouts/sec** doesn’t start to become an issue until around 5000 or so (depending on your SQL Server) and Lock Wait times under 1 second are also healthy.</span></span>  
  
 <span data-ttu-id="f1a36-144">維持可能な最大スループットを確認する方法を説明し、維持可能な健全なシステムの主要な指標がどのようなものかを確認しました。次に、ガベージの処理と収集よりも受信の速度が速いシステムに関連する動作について検討します。</span><span class="sxs-lookup"><span data-stu-id="f1a36-144">Now that we have shown how to find the maximum sustainable throughput and seen what the key indicators look like for a sustainable, healthy system, let’s explore some behavior associated with a system that is receiving faster than it is processing and collecting garbage.</span></span> <span data-ttu-id="f1a36-145">進みます[オーバー ドライブ ロード テスト](../core/overdrive-load-test.md)です。</span><span class="sxs-lookup"><span data-stu-id="f1a36-145">Proceed to [Overdrive Load Test](../core/overdrive-load-test.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1a36-146">参照</span><span class="sxs-lookup"><span data-stu-id="f1a36-146">See Also</span></span>  
 <span data-ttu-id="f1a36-147">[エンジンの MST を測定するためのシナリオをテストします。](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span><span class="sxs-lookup"><span data-stu-id="f1a36-147">[Test Scenarios for Measuring MST of the Engine](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span></span>  
 [<span data-ttu-id="f1a36-148">オーバー ドライブ ロード テスト</span><span class="sxs-lookup"><span data-stu-id="f1a36-148">Overdrive Load Test</span></span>](../core/overdrive-load-test.md)