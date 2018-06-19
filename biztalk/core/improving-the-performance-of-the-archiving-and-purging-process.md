---
title: アーカイブのパフォーマンスの向上と処理をパージ |Microsoft ドキュメント
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
ms.openlocfilehash: 3876021fec4d604960d672671cab8bf4be1dc0a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257842"
---
# <a name="improving-the-performance-of-the-archiving-and-purging-process"></a><span data-ttu-id="c5398-102">アーカイブおよび削除のプロセスのパフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="c5398-102">Improving the Performance of the Archiving and Purging Process</span></span>
<span data-ttu-id="c5398-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースに格納されているデータの量は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] シナリオの設計、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] シナリオで処理されるメッセージの数とサイズ、および追跡に関する構成内容によって、非常に短期間で増加することがあります。</span><span class="sxs-lookup"><span data-stu-id="c5398-103">The amount of data stored in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases can grow very quickly depending on how you have designed your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] scenario, depending on the number and size of messages processed by your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] scenario, and depending on how you have configured tracking.</span></span> <span data-ttu-id="c5398-104">データベース サイズを正常なレベルに保つことにより、処理の効率を向上させ、システム内のデータの量をどの時点でも正常な値に維持することができます。</span><span class="sxs-lookup"><span data-stu-id="c5398-104">By maintaining your database size at a healthy level, processing is more efficient and the amount of data in your system is normalized at any given time.</span></span> <span data-ttu-id="c5398-105">また、効率的で一貫性のあるパフォーマンスを達成できます。</span><span class="sxs-lookup"><span data-stu-id="c5398-105">This provides efficient and consistent performance.</span></span> <span data-ttu-id="c5398-106">このプロセスを自動化すると、データベースを手動で保守するための労力を軽減することができます。</span><span class="sxs-lookup"><span data-stu-id="c5398-106">By automating this process you free yourself of the burden of manually maintaining your databases.</span></span>  
  
## <a name="configuring-a-healthy-environment"></a><span data-ttu-id="c5398-107">正常な環境の構成</span><span class="sxs-lookup"><span data-stu-id="c5398-107">Configuring a healthy environment</span></span>  
 <span data-ttu-id="c5398-108">正常な [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境を保つための戦略は、使用するシナリオおよび実行用のハードウェアに大きく依存します。</span><span class="sxs-lookup"><span data-stu-id="c5398-108">Your strategy in maintaining a healthy [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment is heavily dependent on your particular scenario and the hardware it is running on.</span></span> <span data-ttu-id="c5398-109">監視すべき主要な対象は、BizTalk 追跡 (BizTalkDTADb) データベースの増加率およびサイズです。</span><span class="sxs-lookup"><span data-stu-id="c5398-109">The key things to monitor are the rate of growth and the size of your BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="c5398-110">追跡データベース内にある少数のテーブルが、データベース サイズの大部分を占めているため、これらのテーブルが実行時のパフォーマンスを左右します。</span><span class="sxs-lookup"><span data-stu-id="c5398-110">A few tables of the tracking database account for bulk of the database size and hence the performance impact on runtime.</span></span>  
  
 <span data-ttu-id="c5398-111">シナリオが同じでも、生成される追跡データの量は構成によって大きく異なり、存在する追跡ポイントの数、使用されるメッセージ数、メッセージのサイズ、および追跡に使用されるメッセージ本文のレベルに応じて変化します。</span><span class="sxs-lookup"><span data-stu-id="c5398-111">The same scenario can be configured to produce vastly different amount of tracking data based on how many tracking points are present, how many different messages are used, size of the messages and the level of message body tracking used.</span></span> <span data-ttu-id="c5398-112">監視すべき重要な事項を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c5398-112">Following are some important factors to monitor:</span></span>  
  
-   <span data-ttu-id="c5398-113">追跡ポイントの数 (パイプライン、オーケストレーション、ポートなど)</span><span class="sxs-lookup"><span data-stu-id="c5398-113">Number of tracking points - such as pipelines, orchestrations, and ports</span></span>  
  
-   <span data-ttu-id="c5398-114">追跡対象のメッセージ プロパティ数</span><span class="sxs-lookup"><span data-stu-id="c5398-114">Number of message properties tracked</span></span>  
  
-   <span data-ttu-id="c5398-115">1 つの受信メッセージあたりのメッセージ数</span><span class="sxs-lookup"><span data-stu-id="c5398-115">Number of messages per incoming message</span></span>  
  
-   <span data-ttu-id="c5398-116">メッセージのサイズ</span><span class="sxs-lookup"><span data-stu-id="c5398-116">Message size</span></span>  
  
-   <span data-ttu-id="c5398-117">トラフィック レート (平均およびピーク)</span><span class="sxs-lookup"><span data-stu-id="c5398-117">Traffic rate (average and peak)</span></span>  
  
-   <span data-ttu-id="c5398-118">メッセージ本文の追跡の構成</span><span class="sxs-lookup"><span data-stu-id="c5398-118">Message body tracking configuration</span></span>  
  
 <span data-ttu-id="c5398-119">データの自動的なアーカイブおよび削除の実行を検討する場合は、追跡データベースに保持する必要のあるライブ データの量を考慮します。</span><span class="sxs-lookup"><span data-stu-id="c5398-119">When considering automatic archiving and purging of data consider how much live data you need to keep in your tracking database.</span></span> <span data-ttu-id="c5398-120">削除の実行時にパフォーマンスの低下がないように、対象となるライブ データの量を処理するには、使用する環境に応じて DTA Purge and Archive ジョブ パラメーターを適切に調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5398-120">You need to tune the DTA Purge and Archive job parameters as appropriate for your environment so that the targeted amount of live data can be supported by the purging performance without degradation.</span></span>  
  
 <span data-ttu-id="c5398-121">DTA Purge and Archive ジョブでは、指定した間隔で所定の量のデータを削除できます。</span><span class="sxs-lookup"><span data-stu-id="c5398-121">The DTA Purge and Archive job can purge a certain amount of data within a given time interval.</span></span> <span data-ttu-id="c5398-122">ジョブの容量は、実行しているシナリオ、現在のデータベース サイズ、およびハードウェアによって異なります。</span><span class="sxs-lookup"><span data-stu-id="c5398-122">The capacity of the job depends on the scenarios running, the current database size, and the hardware.</span></span> <span data-ttu-id="c5398-123">安定した環境を維持するために、受信追跡データの生成と削除のバランスを整える必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5398-123">In order to have a stable environment, you must have a balance between the incoming tracking data generation and purging.</span></span> <span data-ttu-id="c5398-124">テスト環境では、データの有効期間と削除ジョブの頻度を変化させながら適正なバランスを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="c5398-124">In your test environment, you can find the balance by varying the live window of data and the frequency of the purging job.</span></span> <span data-ttu-id="c5398-125">良好なバランスを保つことにより、維持可能なスループットが達成されます。</span><span class="sxs-lookup"><span data-stu-id="c5398-125">In a balanced state, your system will deliver sustainable throughput.</span></span> <span data-ttu-id="c5398-126">これらの操作の目的は、BizTalk 追跡データベース テーブルのサイズが増大して持続的なパフォーマンス低下の問題が発生する前に、十分なバッファーを確保することです。</span><span class="sxs-lookup"><span data-stu-id="c5398-126">Your goal is to have enough of a buffer before the BizTalk Tracking database table size causes sustained, significant performance issues.</span></span>  
  
## <a name="performance-limitations"></a><span data-ttu-id="c5398-127">パフォーマンスの制限</span><span class="sxs-lookup"><span data-stu-id="c5398-127">Performance limitations</span></span>  
 <span data-ttu-id="c5398-128">すべてのシナリオで削除パフォーマンスが向上するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="c5398-128">Purging performance will not scale for all scenarios.</span></span> <span data-ttu-id="c5398-129">一部のシナリオでは、生成される追跡データの量が増えてしまうことがあります。</span><span class="sxs-lookup"><span data-stu-id="c5398-129">For any scenario, it is possible to generate increasing amounts of tracking data.</span></span> <span data-ttu-id="c5398-130">常に遅いレートで追跡データの削除が実行されると、データベース サイズが蓄積され、削除パフォーマンスの低下につながります。</span><span class="sxs-lookup"><span data-stu-id="c5398-130">When tracking data is purged at a consistently slower rate, there is a buildup of the tracking database size, which worsens the purging performance further.</span></span>  
  
 <span data-ttu-id="c5398-131">負荷が大きすぎる状態では、メッセージ本文のコピーの実行が遅くなり、メッセージ ボックス データベースのバックログになる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c5398-131">Under unsustainable load conditions, the copying of message bodies may also become slower and there may become a backlog in the MessageBox database.</span></span> <span data-ttu-id="c5398-132">極端な場合は、毎日のメッセージ本文のコピーおよび追跡のアーカイブで、メッセージ本文に関連インスタンス情報が含まれているにもかかわらず、メッセージ本文を利用できないことがあります。</span><span class="sxs-lookup"><span data-stu-id="c5398-132">Under extreme conditions, the daily message body copying and tracking may lead to archives where the message body is not available even though it contains related instance information.</span></span> <span data-ttu-id="c5398-133">通常、高負荷の期間と低負荷の期間が交互に発生するので、ジョブは低負荷の期間中に遅れを取り戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="c5398-133">Typically, periods of high loads alternate with periods of low load and enable the job to catch up during periods of low load.</span></span>  
  
 <span data-ttu-id="c5398-134">BizTalk Tracking データベースのアーカイブおよび削除を行うと、データベースが継続的に簡略化され、格納された追跡データが圧縮されるので、負荷が大きすぎる状態が発生する可能性は非常に少なくなります。</span><span class="sxs-lookup"><span data-stu-id="c5398-134">Archiving and purging the BizTalk Tracking database should considerably reduce the possibility of unsustainable load conditions because of the continuous pruning of the database and the compaction of stored tracking data.</span></span> <span data-ttu-id="c5398-135">これらのプロセスにより、手動による介入の必要性は大きく低減します。</span><span class="sxs-lookup"><span data-stu-id="c5398-135">These processes greatly reduce the need for manual intervention.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5398-136">参照</span><span class="sxs-lookup"><span data-stu-id="c5398-136">See Also</span></span>  
 [<span data-ttu-id="c5398-137">BizTalk 追跡データベースのアーカイブおよび削除</span><span class="sxs-lookup"><span data-stu-id="c5398-137">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)