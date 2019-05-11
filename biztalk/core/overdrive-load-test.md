---
title: ロード テストをオーバー ドライブ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0d16d0a8-4255-4f5a-86a2-26cc11bb9a70
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 734c0dffc64ca7efd52b6325227a26ee0387b50e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393409"
---
# <a name="overdrive-load-test"></a><span data-ttu-id="a6302-102">オーバー ドライブ ロード テスト</span><span class="sxs-lookup"><span data-stu-id="a6302-102">Overdrive Load Test</span></span>
<span data-ttu-id="a6302-103">このトピックの情報を指すで説明されているテスト[エンジンの MST を測定するテストのシナリオ](../core/test-scenarios-for-measuring-mst-of-the-engine.md)します。</span><span class="sxs-lookup"><span data-stu-id="a6302-103">The information in this topic refers to the tests explained in [Test Scenarios for Measuring MST of the Engine](../core/test-scenarios-for-measuring-mst-of-the-engine.md).</span></span>  
  
 <span data-ttu-id="a6302-104">負荷生成ツール LoadGen 2007 では、BizTalk Server システム上の負荷をシミュレートすることができます。</span><span class="sxs-lookup"><span data-stu-id="a6302-104">The Load Generation tool, LoadGen 2007, enables you to simulate heavy loads on a BizTalk Server system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a6302-105">ダウンロード[LoadGen](https://www.microsoft.com/download/details.aspx?id=14925)します。</span><span class="sxs-lookup"><span data-stu-id="a6302-105">Download [LoadGen](https://www.microsoft.com/download/details.aspx?id=14925).</span></span> <span data-ttu-id="a6302-106">このツールの以前のバージョン、BizTalk Server 2004 負荷生成ツールがダウンロードできる[ http://go.microsoft.com/fwlink/?linkid=108999](http://go.microsoft.com/fwlink/?linkid=108999)します。</span><span class="sxs-lookup"><span data-stu-id="a6302-106">The previous version of this tool, the BizTalk Server 2004 Load Generation Tool is available for download at [http://go.microsoft.com/fwlink/?linkid=108999](http://go.microsoft.com/fwlink/?linkid=108999).</span></span>  
  
 <span data-ttu-id="a6302-107">続けて負荷の多いシステムをシミュレートするには、LoadGen 2007 よりも最大測定された維持可能なスループットの約 410 メッセージ/秒、120 メッセージ/秒の送信構成されました。</span><span class="sxs-lookup"><span data-stu-id="a6302-107">To simulate a continuously overdriven system, LoadGen 2007 was configured to send about 410 msgs/sec, 120 msgs/sec more than the measured maximum sustainable throughput.</span></span>  
  
 <span data-ttu-id="a6302-108">テストは、システムをオーバー ドライブするだけでなく、どのくらいの時間がかかる約 200万レコードのスプール バックログの深さから回復するを把握するも設計されています。</span><span class="sxs-lookup"><span data-stu-id="a6302-108">The test was designed not only to overdrive the system, but also to get an idea of how long it would take to recover from a spool backlog depth of around 2 million records.</span></span>  
  
 <span data-ttu-id="a6302-109">これを行うには、スプールの深さが約 200万レコードまでシステムが、高速で駆動します。</span><span class="sxs-lookup"><span data-stu-id="a6302-109">To accomplish this, the system was driven at the increased rate until the spool depth was around 2 million records.</span></span> <span data-ttu-id="a6302-110">スプールの深さではそれ以上の負荷が生成された後、必要なレベルに達するとします。</span><span class="sxs-lookup"><span data-stu-id="a6302-110">Once the spool depth reached the desired level then no further load was generated.</span></span>  
  
 <span data-ttu-id="a6302-111">BizTalk 制限メカニズムがスプール テーブル バックログが蓄積されるように、受信ホストを制限しないことを確認する、 **DB のメッセージ カウント**から受信ホストが変更されたは、しきい値を調整します既定値の 50000 から 2000000 にします。</span><span class="sxs-lookup"><span data-stu-id="a6302-111">To ensure that the BizTalk throttling mechanism did not throttle the receive host, which would prevent the accumulation of a spool table backlog, the **Message count in DB** throttling threshold for the receive host was changed from the default value of 50000 to 2000000.</span></span> <span data-ttu-id="a6302-112">変更する方法について、 **DB のメッセージ カウント**しきい値を調整するを参照してください[リソース ベースのスロットル設定の変更方法](../core/how-to-modify-resource-based-throttling-settings.md)します。</span><span class="sxs-lookup"><span data-stu-id="a6302-112">For information on changing the **Message count in DB** throttling threshold, see [How to Modify Resource Based Throttling Settings](../core/how-to-modify-resource-based-throttling-settings.md).</span></span> <span data-ttu-id="a6302-113">既定のホスト制限設定については、次を参照してください。[設定ダッシュ ボードの BizTalk Server のパフォーマンス チューニングを使用して](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)します。</span><span class="sxs-lookup"><span data-stu-id="a6302-113">For information about the default host throttling settings, see [Using Settings Dashboard for BizTalk Server Performance Tuning](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md).</span></span>  
  
 <span data-ttu-id="a6302-114">次のグラフでは、上のグラフと同じインジケーターを示します。</span><span class="sxs-lookup"><span data-stu-id="a6302-114">The following graph shows the same indicators as in the graph above.</span></span>  
  
 <span data-ttu-id="a6302-115">**オーバー ドライブ ロード テストのロード プロファイル**</span><span class="sxs-lookup"><span data-stu-id="a6302-115">**Load profile of overdrive load test**</span></span>  
  
 <span data-ttu-id="a6302-116">![オーバー ドライブ ロードのパフォーマンス監視画面](../core/media/bts06-overdrive-load.gif "BTS06_Overdrive_Load")</span><span class="sxs-lookup"><span data-stu-id="a6302-116">![Performance montor display of overdrive load](../core/media/bts06-overdrive-load.gif "BTS06_Overdrive_Load")</span></span>  
  
 <span data-ttu-id="a6302-117">グラフからわかるように、スプールの深さは、構築すぐに、2 件のレコードのすぐ上にピークとなるを開始します。</span><span class="sxs-lookup"><span data-stu-id="a6302-117">As can be seen from the graph, the spool depth started building up immediately, peaking at just above 2 million records.</span></span> <span data-ttu-id="a6302-118">この速度で対象となる 200万レコードのバックログを表示するには約 2.5 時間がかかりました。</span><span class="sxs-lookup"><span data-stu-id="a6302-118">At this rate, it took just about 2.5 hours to get to the targeted 2 million record backlog.</span></span> <span data-ttu-id="a6302-119">負荷が停止した後、クリーンアップ ジョブ バックログから回復するのに約 8 時間がかかりました。</span><span class="sxs-lookup"><span data-stu-id="a6302-119">After the load was stopped, it took around 8 hours for the cleanup jobs to recover from the backlog.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6302-120">参照</span><span class="sxs-lookup"><span data-stu-id="a6302-120">See Also</span></span>  
 <span data-ttu-id="a6302-121">[エンジンの MST を測定するためのテスト シナリオ](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span><span class="sxs-lookup"><span data-stu-id="a6302-121">[Test Scenarios for Measuring MST of the Engine](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span></span>  
 <span data-ttu-id="a6302-122">[BizTalk server 設定ダッシュ ボードを使用してパフォーマンス チューニング](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md) </span><span class="sxs-lookup"><span data-stu-id="a6302-122">[Using Settings Dashboard for BizTalk Server Performance Tuning](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md) </span></span>  
 [<span data-ttu-id="a6302-123">維持可能なロード テスト</span><span class="sxs-lookup"><span data-stu-id="a6302-123">Sustainable Load Test</span></span>](../core/sustainable-load-test.md)