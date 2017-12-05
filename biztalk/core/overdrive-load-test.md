---
title: "オーバー ドライブ ロード テスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d16d0a8-4255-4f5a-86a2-26cc11bb9a70
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cff4592c58dd165a85d63666958721231cfcbd4c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="overdrive-load-test"></a><span data-ttu-id="7cd18-102">オーバー ドライブ ロード テスト</span><span class="sxs-lookup"><span data-stu-id="7cd18-102">Overdrive Load Test</span></span>
<span data-ttu-id="7cd18-103">このトピックの情報は、参照で説明されているテスト[エンジンの MST の測定のテスト シナリオ](../core/test-scenarios-for-measuring-mst-of-the-engine.md)です。</span><span class="sxs-lookup"><span data-stu-id="7cd18-103">The information in this topic refers to the tests explained in [Test Scenarios for Measuring MST of the Engine](../core/test-scenarios-for-measuring-mst-of-the-engine.md).</span></span>  
  
 <span data-ttu-id="7cd18-104">負荷生成ツール LoadGen 2007 を使用すると、BizTalk Server システム上の大きな負荷をシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="7cd18-104">The Load Generation tool, LoadGen 2007, enables you to simulate heavy loads on a BizTalk Server system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7cd18-105">ダウンロード[LoadGen](https://www.microsoft.com/download/details.aspx?id=14925)です。</span><span class="sxs-lookup"><span data-stu-id="7cd18-105">Download [LoadGen](https://www.microsoft.com/download/details.aspx?id=14925).</span></span> <span data-ttu-id="7cd18-106">このツールの以前のバージョン、BizTalk Server 2004 負荷生成ツールは、ダウンロード[http://go.microsoft.com/fwlink/?linkid=108999](http://go.microsoft.com/fwlink/?linkid=108999)です。</span><span class="sxs-lookup"><span data-stu-id="7cd18-106">The previous version of this tool, the BizTalk Server 2004 Load Generation Tool is available for download at [http://go.microsoft.com/fwlink/?linkid=108999](http://go.microsoft.com/fwlink/?linkid=108999).</span></span>  
  
 <span data-ttu-id="7cd18-107">続けて負荷の多いシステムをシミュレートするため、LoadGen 2007 は、測定された維持可能な最大のスループットよりも 120 メッセージ/秒多い約 410 メッセージ/秒の送信で構成されました。</span><span class="sxs-lookup"><span data-stu-id="7cd18-107">To simulate a continuously overdriven system, LoadGen 2007 was configured to send about 410 msgs/sec, 120 msgs/sec more than the measured maximum sustainable throughput.</span></span>  
  
 <span data-ttu-id="7cd18-108">このテストは、システムの負荷だけではなく、約 200 万レコードという深さのスプール バックログから回復する時間も考慮しています。</span><span class="sxs-lookup"><span data-stu-id="7cd18-108">The test was designed not only to overdrive the system, but also to get an idea of how long it would take to recover from a spool backlog depth of around 2 million records.</span></span>  
  
 <span data-ttu-id="7cd18-109">これを実現するため、システムは、スプールの深さが約 200 万レコードになるまで、高速で動作します。</span><span class="sxs-lookup"><span data-stu-id="7cd18-109">To accomplish this, the system was driven at the increased rate until the spool depth was around 2 million records.</span></span> <span data-ttu-id="7cd18-110">スプールの深さが適切なレベルになると、負荷は生成されなくなります。</span><span class="sxs-lookup"><span data-stu-id="7cd18-110">Once the spool depth reached the desired level then no further load was generated.</span></span>  
  
 <span data-ttu-id="7cd18-111">BizTalk 制限メカニズムがスプール テーブル バックログの蓄積をできなくなる、受信ホストを制限しないことを確認する、 **DB 内の数をメッセージ**から受信ホストが変更されたために、しきい値を調整します既定値の 50000 から 2000000 にします。</span><span class="sxs-lookup"><span data-stu-id="7cd18-111">To ensure that the BizTalk throttling mechanism did not throttle the receive host, which would prevent the accumulation of a spool table backlog, the **Message count in DB** throttling threshold for the receive host was changed from the default value of 50000 to 2000000.</span></span> <span data-ttu-id="7cd18-112">変更する方法について、 **DB 内の数をメッセージ**しきい値を調整するを参照してください[リソース ベースの調整設定の変更方法](../core/how-to-modify-resource-based-throttling-settings.md)です。</span><span class="sxs-lookup"><span data-stu-id="7cd18-112">For information on changing the **Message count in DB** throttling threshold, see [How to Modify Resource Based Throttling Settings](../core/how-to-modify-resource-based-throttling-settings.md).</span></span> <span data-ttu-id="7cd18-113">既定のホスト設定の制限については、次を参照してください。[設定ダッシュ ボードの BizTalk Server のパフォーマンス チューニング](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)です。</span><span class="sxs-lookup"><span data-stu-id="7cd18-113">For information about the default host throttling settings, see [Using Settings Dashboard for BizTalk Server Performance Tuning](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md).</span></span>  
  
 <span data-ttu-id="7cd18-114">次の図は、上図と同じインジケーターを示しています。</span><span class="sxs-lookup"><span data-stu-id="7cd18-114">The following graph shows the same indicators as in the graph above.</span></span>  
  
 <span data-ttu-id="7cd18-115">**オーバー ドライブ ロード テストのロード プロファイル**</span><span class="sxs-lookup"><span data-stu-id="7cd18-115">**Load profile of overdrive load test**</span></span>  
  
 <span data-ttu-id="7cd18-116">![オーバー ドライブ ロードのパフォーマンス監視画面](../core/media/bts06-overdrive-load.gif "BTS06_Overdrive_Load")</span><span class="sxs-lookup"><span data-stu-id="7cd18-116">![Performance montor display of overdrive load](../core/media/bts06-overdrive-load.gif "BTS06_Overdrive_Load")</span></span>  
  
 <span data-ttu-id="7cd18-117">図に示されているように、スプールがすぐに深くなっていきます。約 200 万レコードが最大です。</span><span class="sxs-lookup"><span data-stu-id="7cd18-117">As can be seen from the graph, the spool depth started building up immediately, peaking at just above 2 million records.</span></span> <span data-ttu-id="7cd18-118">この場合、目標とした 200 万レコードのバックログに達するのに約 2.5 時間かかりました。</span><span class="sxs-lookup"><span data-stu-id="7cd18-118">At this rate, it took just about 2.5 hours to get to the targeted 2 million record backlog.</span></span> <span data-ttu-id="7cd18-119">負荷が止まると、クリーンアップ ジョブによるバックログからの回復に約 8 時間かかりました。</span><span class="sxs-lookup"><span data-stu-id="7cd18-119">After the load was stopped, it took around 8 hours for the cleanup jobs to recover from the backlog.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cd18-120">参照</span><span class="sxs-lookup"><span data-stu-id="7cd18-120">See Also</span></span>  
 <span data-ttu-id="7cd18-121">[エンジンの MST を測定するためのシナリオをテストします。](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span><span class="sxs-lookup"><span data-stu-id="7cd18-121">[Test Scenarios for Measuring MST of the Engine](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span></span>  
 <span data-ttu-id="7cd18-122">[BizTalk server 設定ダッシュ ボードを使用してパフォーマンス チューニング](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md) </span><span class="sxs-lookup"><span data-stu-id="7cd18-122">[Using Settings Dashboard for BizTalk Server Performance Tuning](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md) </span></span>  
 [<span data-ttu-id="7cd18-123">維持可能なロード テスト</span><span class="sxs-lookup"><span data-stu-id="7cd18-123">Sustainable Load Test</span></span>](../core/sustainable-load-test.md)