---
title: "フラッド ゲート ロード テスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- LoadGen tool, simulating floodgate events
- performance, floodgate peaks
- floodgate events [performance]
ms.assetid: 937f2478-339b-4ae2-b107-56f3a4bfc579
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74954d8b94207832ceee5bbb699a7de1a245f61b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="floodgate-load-test"></a><span data-ttu-id="12bbf-102">フラッドゲート ロード テスト</span><span class="sxs-lookup"><span data-stu-id="12bbf-102">Floodgate Load Test</span></span>
<span data-ttu-id="12bbf-103">このトピックの情報は、参照で説明されているテスト[エンジンの MST の測定のテスト シナリオ](../core/test-scenarios-for-measuring-mst-of-the-engine.md)です。</span><span class="sxs-lookup"><span data-stu-id="12bbf-103">The information in this topic refers to the tests explained in [Test Scenarios for Measuring MST of the Engine](../core/test-scenarios-for-measuring-mst-of-the-engine.md).</span></span>  
  
## <a name="what-causes-floodgate-events"></a><span data-ttu-id="12bbf-104">フラッドゲート イベントの原因</span><span class="sxs-lookup"><span data-stu-id="12bbf-104">What Causes Floodgate Events?</span></span>  
 <span data-ttu-id="12bbf-105">場所だけで、さまざまなシナリオがあるいくつかの大きなピーク (とも呼ばれる**フラッド ゲート イベント**) メッセージの到着、システムを 1 日にします。</span><span class="sxs-lookup"><span data-stu-id="12bbf-105">There are a number of scenarios where just a few large peaks (also known as **floodgate events**) of messages arrive at the system each day.</span></span> <span data-ttu-id="12bbf-106">これらのピークの合間のスループットは非常に低くなっています。</span><span class="sxs-lookup"><span data-stu-id="12bbf-106">Between these peaks, the throughput can be very low.</span></span> <span data-ttu-id="12bbf-107">このようなタイプのシナリオの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="12bbf-107">Examples of these types of scenarios include:</span></span>  
  
-   <span data-ttu-id="12bbf-108">証券取引で、市場の開始時や終了時など</span><span class="sxs-lookup"><span data-stu-id="12bbf-108">Equity trading, for example, at market open and market close</span></span>  
  
-   <span data-ttu-id="12bbf-109">銀行システムで、1 日の終わりに行われる当日取引の照合時など</span><span class="sxs-lookup"><span data-stu-id="12bbf-109">Banking systems, for example, during end of day transaction reconciliation</span></span>  
  
 <span data-ttu-id="12bbf-110">その他のタイプのイベントにより、フラッドゲート イベントに似たバックログ動作が発生する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="12bbf-110">Other types of events can cause backlog behavior similar to floodgate events.</span></span> <span data-ttu-id="12bbf-111">たとえば、パートナーの送信アドレスがオフラインになり、そのアドレスに宛てたメッセージを再送信または保留する必要が生じた場合、バックログが蓄積されます。</span><span class="sxs-lookup"><span data-stu-id="12bbf-111">For example, if a partner send address goes off line so that messages destined for that address must be re-tried and/or suspended, this can result in backlog building up.</span></span> <span data-ttu-id="12bbf-112">パートナーがオンラインに戻ると、再送信する必要のある保留メッセージが多く蓄積されているので、別のタイプのフラッドゲート イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="12bbf-112">When the partner comes back on line, there may be a large number of suspended messages that need to be resumed, resulting in another type of floodgate event.</span></span> <span data-ttu-id="12bbf-113">次のシステム テストでこの動作を示します。</span><span class="sxs-lookup"><span data-stu-id="12bbf-113">The following test of the system illustrates this behavior.</span></span>  
  
## <a name="simulating-a-floodgate-event"></a><span data-ttu-id="12bbf-114">フラッドゲート イベントのシミュレーション</span><span class="sxs-lookup"><span data-stu-id="12bbf-114">Simulating a Floodgate Event</span></span>  
 <span data-ttu-id="12bbf-115">このテストでは、維持可能な最大スループットの約半分でシステムを初期駆動しました。これは非常に安定したスループットです。</span><span class="sxs-lookup"><span data-stu-id="12bbf-115">For this test, the system was initially driven at around half the maximum sustainable throughput which of course was very stable.</span></span> <span data-ttu-id="12bbf-116">次に、フラッドゲート イベントをシミュレートするために、短時間に約 410 メッセージ/秒で送信するように負荷生成ツールを構成しました (オーバードライブ テストと同様)。</span><span class="sxs-lookup"><span data-stu-id="12bbf-116">Then, to simulate a floodgate event, the load generation tool was configured to send in about 410 msgs/sec for a short period of time (the same as for the overdrive test).</span></span> <span data-ttu-id="12bbf-117">1 秒間に受信したメッセージとスプールの深さを測定するロード プロファイルの結果を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="12bbf-117">The resultant load profile measuring messages received per second and spool depth is displayed below.</span></span>  
  
 <span data-ttu-id="12bbf-118">**フラッド ゲート ロード テストのロード プロファイル**</span><span class="sxs-lookup"><span data-stu-id="12bbf-118">**Load profile of floodgate load test**</span></span>  
  
 <span data-ttu-id="12bbf-119">![飽和による負荷のパフォーマンス モニター画面](../core/media/bts06-floodgate-load.gif "BTS06_Floodgate_Load")</span><span class="sxs-lookup"><span data-stu-id="12bbf-119">![Performance monitor display of floodgate load](../core/media/bts06-floodgate-load.gif "BTS06_Floodgate_Load")</span></span>  
  
 <span data-ttu-id="12bbf-120">このグラフから、フラッドゲート イベントの発生中に、スプール テーブルに急速にバックログが蓄積されたことがわかります。</span><span class="sxs-lookup"><span data-stu-id="12bbf-120">Note from the graph that the spool tables quickly built up a backlog during the floodgate event.</span></span> <span data-ttu-id="12bbf-121">ただし、イベントの発生は比較的短時間で、その後の受信レートは維持可能な最大受信レート以下になったので、クリーンアップ ジョブを実行して、システム受信障害を引き起こさずにイベントから回復することができました。</span><span class="sxs-lookup"><span data-stu-id="12bbf-121">However, because the event was relatively short lived and the subsequent receive rate after the event was below the maximum sustainable rate, the cleanup jobs were able to run and recover from the event without requiring a system receive outage.</span></span> <span data-ttu-id="12bbf-122">このテストでは、メッセージ ボックスは SQL Server 2005 に格納されていました。このテストの開始から終了までの時間は約 45 分でした。</span><span class="sxs-lookup"><span data-stu-id="12bbf-122">For this particular test, the MessageBox was housed on SQL Server 2005; the duration of this test from beginning to end was approximately 45 minutes.</span></span>  
  
 <span data-ttu-id="12bbf-123">もちろん、システムはそれぞれ異なるので、結果も異なります。</span><span class="sxs-lookup"><span data-stu-id="12bbf-123">Of course, every system is different, so "your mileage will vary."</span></span> <span data-ttu-id="12bbf-124">回復可能かどうかを確認するには、実稼働に移行する前に通常の負荷を使用してテストしてください。</span><span class="sxs-lookup"><span data-stu-id="12bbf-124">The best way to verify that you can recover is to test with a representative load before going into production.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12bbf-125">参照</span><span class="sxs-lookup"><span data-stu-id="12bbf-125">See Also</span></span>  
 <span data-ttu-id="12bbf-126">[エンジンの MST を測定するためのシナリオをテストします。](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span><span class="sxs-lookup"><span data-stu-id="12bbf-126">[Test Scenarios for Measuring MST of the Engine](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span></span>  
 <span data-ttu-id="12bbf-127">[BizTalk server 設定ダッシュ ボードを使用してパフォーマンス チューニング](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md) </span><span class="sxs-lookup"><span data-stu-id="12bbf-127">[Using Settings Dashboard for BizTalk Server Performance Tuning](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md) </span></span>  
 <span data-ttu-id="12bbf-128">[オーバー ドライブ ロード テスト](../core/overdrive-load-test.md) </span><span class="sxs-lookup"><span data-stu-id="12bbf-128">[Overdrive Load Test](../core/overdrive-load-test.md) </span></span>  
 [<span data-ttu-id="12bbf-129">維持可能なロード テスト</span><span class="sxs-lookup"><span data-stu-id="12bbf-129">Sustainable Load Test</span></span>](../core/sustainable-load-test.md)