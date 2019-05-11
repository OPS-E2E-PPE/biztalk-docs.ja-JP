---
title: アーカイブのパフォーマンスの向上と、プロセスの削除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- archiving [Tracking database], system performance
- DTA Purge and Archive job, performance
- purging, limitations
- performance, archiving
- performance, purging
- purging, system performance
ms.assetid: d65da58d-65e0-4f6c-8b15-5d4448049b42
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6d7cb6adf314bd5575d354c52c2682138bad784
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382204"
---
# <a name="improving-the-performance-of-the-archiving-and-purging-process"></a><span data-ttu-id="d190d-102">アーカイブおよび削除のプロセスのパフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="d190d-102">Improving the Performance of the Archiving and Purging Process</span></span>
<span data-ttu-id="d190d-103">格納されているデータの量、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースを設計した方法に応じて非常に簡単に拡張できる、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]シナリオでは、によって処理されるメッセージのサイズと数に応じて、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]シナリオ、およびがあるかによって異なります追跡を構成します。</span><span class="sxs-lookup"><span data-stu-id="d190d-103">The amount of data stored in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases can grow very quickly depending on how you have designed your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] scenario, depending on the number and size of messages processed by your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] scenario, and depending on how you have configured tracking.</span></span> <span data-ttu-id="d190d-104">正常なレベルで、データベースのサイズを維持することによって処理効率が上がると、システム内のデータの量が特定の時点に正規化されます。</span><span class="sxs-lookup"><span data-stu-id="d190d-104">By maintaining your database size at a healthy level, processing is more efficient and the amount of data in your system is normalized at any given time.</span></span> <span data-ttu-id="d190d-105">これは、効率的で一貫性のあるパフォーマンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="d190d-105">This provides efficient and consistent performance.</span></span> <span data-ttu-id="d190d-106">このプロセスを自動化することによって解放する自分で手動でデータベースの保守の負担の。</span><span class="sxs-lookup"><span data-stu-id="d190d-106">By automating this process you free yourself of the burden of manually maintaining your databases.</span></span>  
  
## <a name="configuring-a-healthy-environment"></a><span data-ttu-id="d190d-107">正常な環境を構成します。</span><span class="sxs-lookup"><span data-stu-id="d190d-107">Configuring a healthy environment</span></span>  
 <span data-ttu-id="d190d-108">正常性を維持するために、戦略[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境は、特定のシナリオとで実行されているハードウェアに大きく依存します。</span><span class="sxs-lookup"><span data-stu-id="d190d-108">Your strategy in maintaining a healthy [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment is heavily dependent on your particular scenario and the hardware it is running on.</span></span> <span data-ttu-id="d190d-109">監視することには、増加率および BizTalk 追跡 (BizTalkDTADb) データベースのサイズです。</span><span class="sxs-lookup"><span data-stu-id="d190d-109">The key things to monitor are the rate of growth and the size of your BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="d190d-110">追跡データベースのテーブルの数が、データベースのサイズの大部分のアカウントし、ランタイムで、パフォーマンスに影響を与えるためです。</span><span class="sxs-lookup"><span data-stu-id="d190d-110">A few tables of the tracking database account for bulk of the database size and hence the performance impact on runtime.</span></span>  
  
 <span data-ttu-id="d190d-111">追跡ポイントの数がどのように存在に基づいて追跡データの量を大幅に異なるを生成するために、同じシナリオを構成することができます多くのさまざまなメッセージが使用される、メッセージのサイズとメッセージ本文の追跡のレベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="d190d-111">The same scenario can be configured to produce vastly different amount of tracking data based on how many tracking points are present, how many different messages are used, size of the messages and the level of message body tracking used.</span></span> <span data-ttu-id="d190d-112">次に、いくつかの重要な要因を監視します。</span><span class="sxs-lookup"><span data-stu-id="d190d-112">Following are some important factors to monitor:</span></span>  
  
- <span data-ttu-id="d190d-113">-パイプライン、オーケストレーション、ポートなどの追跡ポイントの数</span><span class="sxs-lookup"><span data-stu-id="d190d-113">Number of tracking points - such as pipelines, orchestrations, and ports</span></span>  
  
- <span data-ttu-id="d190d-114">追跡メッセージのプロパティの数</span><span class="sxs-lookup"><span data-stu-id="d190d-114">Number of message properties tracked</span></span>  
  
- <span data-ttu-id="d190d-115">受信メッセージあたりのメッセージ数</span><span class="sxs-lookup"><span data-stu-id="d190d-115">Number of messages per incoming message</span></span>  
  
- <span data-ttu-id="d190d-116">メッセージ サイズ</span><span class="sxs-lookup"><span data-stu-id="d190d-116">Message size</span></span>  
  
- <span data-ttu-id="d190d-117">トラフィック レート (平均およびピーク)</span><span class="sxs-lookup"><span data-stu-id="d190d-117">Traffic rate (average and peak)</span></span>  
  
- <span data-ttu-id="d190d-118">メッセージ本文の追跡の構成</span><span class="sxs-lookup"><span data-stu-id="d190d-118">Message body tracking configuration</span></span>  
  
  <span data-ttu-id="d190d-119">自動を検討する場合、アーカイブとデータの削除が、追跡データベースに保持する必要があるライブ データの量を検討します。</span><span class="sxs-lookup"><span data-stu-id="d190d-119">When considering automatic archiving and purging of data consider how much live data you need to keep in your tracking database.</span></span> <span data-ttu-id="d190d-120">対象となるライブ データの量を削除パフォーマンスを低下させることがなくサポートできるように、環境に応じて DTA Purge and Archive ジョブ パラメーターを調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d190d-120">You need to tune the DTA Purge and Archive job parameters as appropriate for your environment so that the targeted amount of live data can be supported by the purging performance without degradation.</span></span>  
  
  <span data-ttu-id="d190d-121">DTA Purge and Archive ジョブでは、指定された時間間隔内でデータ量を削除できます。</span><span class="sxs-lookup"><span data-stu-id="d190d-121">The DTA Purge and Archive job can purge a certain amount of data within a given time interval.</span></span> <span data-ttu-id="d190d-122">ジョブの容量を実行しているシナリオ、現在のデータベースのサイズ、およびハードウェアによって異なります。</span><span class="sxs-lookup"><span data-stu-id="d190d-122">The capacity of the job depends on the scenarios running, the current database size, and the hardware.</span></span> <span data-ttu-id="d190d-123">安定した環境を確保するためには、受信追跡データの生成と削除のバランスが必要です。</span><span class="sxs-lookup"><span data-stu-id="d190d-123">In order to have a stable environment, you must have a balance between the incoming tracking data generation and purging.</span></span> <span data-ttu-id="d190d-124">テスト環境では、データの有効期間と削除のジョブの頻度を変えることでバランスを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="d190d-124">In your test environment, you can find the balance by varying the live window of data and the frequency of the purging job.</span></span> <span data-ttu-id="d190d-125">バランスの取れた状態で、システムは維持可能なスループットを提供します。</span><span class="sxs-lookup"><span data-stu-id="d190d-125">In a balanced state, your system will deliver sustainable throughput.</span></span> <span data-ttu-id="d190d-126">目標は、BizTalk 追跡データベースのテーブル サイズして持続的なパフォーマンスの問題が発生する前に十分なバッファーことです。</span><span class="sxs-lookup"><span data-stu-id="d190d-126">Your goal is to have enough of a buffer before the BizTalk Tracking database table size causes sustained, significant performance issues.</span></span>  
  
## <a name="performance-limitations"></a><span data-ttu-id="d190d-127">パフォーマンスの制限</span><span class="sxs-lookup"><span data-stu-id="d190d-127">Performance limitations</span></span>  
 <span data-ttu-id="d190d-128">すべてのシナリオでは、削除パフォーマンスはスケーラビリティがありません。</span><span class="sxs-lookup"><span data-stu-id="d190d-128">Purging performance will not scale for all scenarios.</span></span> <span data-ttu-id="d190d-129">、すべてのシナリオには、追跡データの量が増加を生成することです。</span><span class="sxs-lookup"><span data-stu-id="d190d-129">For any scenario, it is possible to generate increasing amounts of tracking data.</span></span> <span data-ttu-id="d190d-130">追跡の蓄積が常に遅いレートで追跡データが削除されたとき、データベース サイズ、削除パフォーマンス低下につながります。</span><span class="sxs-lookup"><span data-stu-id="d190d-130">When tracking data is purged at a consistently slower rate, there is a buildup of the tracking database size, which worsens the purging performance further.</span></span>  
  
 <span data-ttu-id="d190d-131">負荷が大きすぎる条件下でメッセージ本文のコピーがも実行が遅くなりが、メッセージ ボックス データベース内のバックログになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d190d-131">Under unsustainable load conditions, the copying of message bodies may also become slower and there may become a backlog in the MessageBox database.</span></span> <span data-ttu-id="d190d-132">極端な場合は、毎日のメッセージの本文をコピーおよび追跡メッセージ本文がない使用可能な関連インスタンス情報が含まれる場合でもアーカイブに可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d190d-132">Under extreme conditions, the daily message body copying and tracking may lead to archives where the message body is not available even though it contains related instance information.</span></span> <span data-ttu-id="d190d-133">通常、高負荷の期間は低負荷の期間が交互し、低負荷の期間中に遅延を解消するジョブを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d190d-133">Typically, periods of high loads alternate with periods of low load and enable the job to catch up during periods of low load.</span></span>  
  
 <span data-ttu-id="d190d-134">アーカイブおよび BizTalk 追跡データベースの削除では、データベースの継続的な排除と格納された追跡データの圧縮のため負荷が大きすぎる状態の可能性を低減する必要があります大幅。</span><span class="sxs-lookup"><span data-stu-id="d190d-134">Archiving and purging the BizTalk Tracking database should considerably reduce the possibility of unsustainable load conditions because of the continuous pruning of the database and the compaction of stored tracking data.</span></span> <span data-ttu-id="d190d-135">これらのプロセスは、手動介入の必要性を大幅に削減します。</span><span class="sxs-lookup"><span data-stu-id="d190d-135">These processes greatly reduce the need for manual intervention.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d190d-136">参照</span><span class="sxs-lookup"><span data-stu-id="d190d-136">See Also</span></span>  
 [<span data-ttu-id="d190d-137">BizTalk 追跡データベースのアーカイブおよび削除</span><span class="sxs-lookup"><span data-stu-id="d190d-137">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)