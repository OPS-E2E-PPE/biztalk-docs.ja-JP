---
title: フラッド ゲート ロード テスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- LoadGen tool, simulating floodgate events
- performance, floodgate peaks
- floodgate events [performance]
ms.assetid: 937f2478-339b-4ae2-b107-56f3a4bfc579
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b78509cc1bc2c38ab1fcf536ce71e3d14b70d500
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387959"
---
# <a name="floodgate-load-test"></a><span data-ttu-id="dea99-102">フラッド ゲート ロード テスト</span><span class="sxs-lookup"><span data-stu-id="dea99-102">Floodgate Load Test</span></span>
<span data-ttu-id="dea99-103">このトピックの情報を指すで説明されているテスト[エンジンの MST を測定するテストのシナリオ](../core/test-scenarios-for-measuring-mst-of-the-engine.md)します。</span><span class="sxs-lookup"><span data-stu-id="dea99-103">The information in this topic refers to the tests explained in [Test Scenarios for Measuring MST of the Engine](../core/test-scenarios-for-measuring-mst-of-the-engine.md).</span></span>  
  
## <a name="what-causes-floodgate-events"></a><span data-ttu-id="dea99-104">どのような原因のフラッド ゲート イベントでしょうか。</span><span class="sxs-lookup"><span data-stu-id="dea99-104">What Causes Floodgate Events?</span></span>  
 <span data-ttu-id="dea99-105">だけが、さまざまなシナリオがあるいくつかの大きなピーク (とも呼ばれます**フラッド ゲート イベント**) メッセージのシステムに到着毎日です。</span><span class="sxs-lookup"><span data-stu-id="dea99-105">There are a number of scenarios where just a few large peaks (also known as **floodgate events**) of messages arrive at the system each day.</span></span> <span data-ttu-id="dea99-106">これらのピークの間でスループットが非常に低いできます。</span><span class="sxs-lookup"><span data-stu-id="dea99-106">Between these peaks, the throughput can be very low.</span></span> <span data-ttu-id="dea99-107">これらのシナリオの例は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dea99-107">Examples of these types of scenarios include:</span></span>  
  
- <span data-ttu-id="dea99-108">株式取引先、たとえば、市場の開始と市場を閉じる</span><span class="sxs-lookup"><span data-stu-id="dea99-108">Equity trading, for example, at market open and market close</span></span>  
  
- <span data-ttu-id="dea99-109">銀行トランザクション調整の日の終了時にシステムで、たとえば、</span><span class="sxs-lookup"><span data-stu-id="dea99-109">Banking systems, for example, during end of day transaction reconciliation</span></span>  
  
  <span data-ttu-id="dea99-110">その他の種類のイベントには、フラッド ゲート イベントに似たバックログ動作を可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dea99-110">Other types of events can cause backlog behavior similar to floodgate events.</span></span> <span data-ttu-id="dea99-111">たとえば、パートナーに送信する場合アドレスがオフラインに宛てたメッセージ バックログが蓄積この結果をアドレスの再試行または保留する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dea99-111">For example, if a partner send address goes off line so that messages destined for that address must be re-tried and/or suspended, this can result in backlog building up.</span></span> <span data-ttu-id="dea99-112">パートナーは行が返される、別のタイプのフラッド ゲート イベント、再開する必要がある保留メッセージの数が多いである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dea99-112">When the partner comes back on line, there may be a large number of suspended messages that need to be resumed, resulting in another type of floodgate event.</span></span> <span data-ttu-id="dea99-113">システムの次のテストでは、この動作を示します。</span><span class="sxs-lookup"><span data-stu-id="dea99-113">The following test of the system illustrates this behavior.</span></span>  
  
## <a name="simulating-a-floodgate-event"></a><span data-ttu-id="dea99-114">フラッド ゲート イベントをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="dea99-114">Simulating a Floodgate Event</span></span>  
 <span data-ttu-id="dea99-115">このテストでは、これはもちろん、非常に安定した、最大約 30 の維持可能なスループットで、システムを初期駆動します。</span><span class="sxs-lookup"><span data-stu-id="dea99-115">For this test, the system was initially driven at around half the maximum sustainable throughput which of course was very stable.</span></span> <span data-ttu-id="dea99-116">次に、フラッド ゲート イベントをシミュレートするには、短期間のうちの約 410 メッセージ/秒で送信するツールが構成されている負荷の生成時間 (と同じオーバー ドライブ テスト)。</span><span class="sxs-lookup"><span data-stu-id="dea99-116">Then, to simulate a floodgate event, the load generation tool was configured to send in about 410 msgs/sec for a short period of time (the same as for the overdrive test).</span></span> <span data-ttu-id="dea99-117">スプールの深さ、1 秒あたりに受信したメッセージを測定する結果のロード プロファイルは、下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="dea99-117">The resultant load profile measuring messages received per second and spool depth is displayed below.</span></span>  
  
 <span data-ttu-id="dea99-118">**フラッド ゲート ロード テストのロード プロファイル**</span><span class="sxs-lookup"><span data-stu-id="dea99-118">**Load profile of floodgate load test**</span></span>  
  
 <span data-ttu-id="dea99-119">![フラッド ゲート ロードのパフォーマンス監視画面](../core/media/bts06-floodgate-load.gif "BTS06_Floodgate_Load")</span><span class="sxs-lookup"><span data-stu-id="dea99-119">![Performance monitor display of floodgate load](../core/media/bts06-floodgate-load.gif "BTS06_Floodgate_Load")</span></span>  
  
 <span data-ttu-id="dea99-120">グラフから、フラッド ゲート イベント中に、スプール テーブルすばやいバックログを構築することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="dea99-120">Note from the graph that the spool tables quickly built up a backlog during the floodgate event.</span></span> <span data-ttu-id="dea99-121">ただし、イベントが比較的短い存続期間と最大持続可能な速度より下のイベントの後、後続の受信レートが、ため、クリーンアップ ジョブを実行し、システムを必要とせずにイベントから回復することの停止を受信します。</span><span class="sxs-lookup"><span data-stu-id="dea99-121">However, because the event was relatively short lived and the subsequent receive rate after the event was below the maximum sustainable rate, the cleanup jobs were able to run and recover from the event without requiring a system receive outage.</span></span> <span data-ttu-id="dea99-122">SQL Server 2005; に格納されていました、メッセージ ボックスのこの特定のテストこのテストを最初から最後までの期間は、約 45 分でした。</span><span class="sxs-lookup"><span data-stu-id="dea99-122">For this particular test, the MessageBox was housed on SQL Server 2005; the duration of this test from beginning to end was approximately 45 minutes.</span></span>  
  
 <span data-ttu-id="dea99-123">もちろん、すべてのシステムは異なるので、「自分のマイレージは異なります」</span><span class="sxs-lookup"><span data-stu-id="dea99-123">Of course, every system is different, so "your mileage will vary."</span></span> <span data-ttu-id="dea99-124">回復できることを確認する最善の方法では、実稼働に移行する前に、典型的な負荷でテストです。</span><span class="sxs-lookup"><span data-stu-id="dea99-124">The best way to verify that you can recover is to test with a representative load before going into production.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dea99-125">参照</span><span class="sxs-lookup"><span data-stu-id="dea99-125">See Also</span></span>  
 <span data-ttu-id="dea99-126">[エンジンの MST を測定するためのテスト シナリオ](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span><span class="sxs-lookup"><span data-stu-id="dea99-126">[Test Scenarios for Measuring MST of the Engine](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span></span>  
 <span data-ttu-id="dea99-127">[BizTalk server 設定ダッシュ ボードを使用してパフォーマンス チューニング](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md) </span><span class="sxs-lookup"><span data-stu-id="dea99-127">[Using Settings Dashboard for BizTalk Server Performance Tuning](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md) </span></span>  
 <span data-ttu-id="dea99-128">[オーバー ドライブ ロード テスト](../core/overdrive-load-test.md) </span><span class="sxs-lookup"><span data-stu-id="dea99-128">[Overdrive Load Test](../core/overdrive-load-test.md) </span></span>  
 [<span data-ttu-id="dea99-129">維持可能なロード テスト</span><span class="sxs-lookup"><span data-stu-id="dea99-129">Sustainable Load Test</span></span>](../core/sustainable-load-test.md)