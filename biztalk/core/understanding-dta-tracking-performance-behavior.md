---
title: DTA 追跡のパフォーマンス特性を理解する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b1a70951-bfed-435c-97f4-0b28a8e4e4dc
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 409138a38b75aebdd4e2df63d23e301dae483738
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292675"
---
# <a name="understanding-dta-tracking-performance-behavior"></a><span data-ttu-id="5c0d2-102">DTA 追跡のパフォーマンス特性を理解します。</span><span class="sxs-lookup"><span data-stu-id="5c0d2-102">Understanding DTA Tracking Performance Behavior</span></span>
<span data-ttu-id="5c0d2-103">DTA 追跡の維持可能な最大のスループット (MST) を決定する主な要因は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5c0d2-103">The primary factors that determine maximum sustainable throughput (MST) for DTA tracking are:</span></span>  
  
- <span data-ttu-id="5c0d2-104">目的のメッセージのスループット、つまり、システムの単位時間あたりの受信メッセージ。</span><span class="sxs-lookup"><span data-stu-id="5c0d2-104">The desired message throughput, that is, messages received per unit time, for the system.</span></span>  
  
- <span data-ttu-id="5c0d2-105">メッセージごとに、データの量が追跡されています。</span><span class="sxs-lookup"><span data-stu-id="5c0d2-105">How much data is being tracked for each message.</span></span>  
  
- <span data-ttu-id="5c0d2-106">BizTalkDTADb データベースから削除されるまで、つまり、データのリテンション期間の有効期限は、データをどのくらいの時間です。</span><span class="sxs-lookup"><span data-stu-id="5c0d2-106">How long the data is to live in the BizTalkDTADb database before being purged, that is, the data retention window.</span></span>  
  
- <span data-ttu-id="5c0d2-107">かどうか、BizTalkDTADb データがアーカイブだけでなく削除します。</span><span class="sxs-lookup"><span data-stu-id="5c0d2-107">Whether or not the BizTalkDTADb data is archived as well as purged.</span></span> <span data-ttu-id="5c0d2-108">アーカイブは省略可能ですが、削除し、定期的に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c0d2-108">Archiving is optional but purging must be performed periodically.</span></span>  
  
  <span data-ttu-id="5c0d2-109">1 つあります共通これらすべての要素があること。 位置、DTA はそのまま使用し、処理の速度 (アーカイブおよび削除) のデータ。</span><span class="sxs-lookup"><span data-stu-id="5c0d2-109">There is one thing that all of these factors have in common: the speed at which the DTA can accept and process (archive and purge) data.</span></span>  
  
## <a name="how-the-biztalkdtadb-insert-and-processing-speed-affects-your-system"></a><span data-ttu-id="5c0d2-110">BizTalkDTADb の挿入と処理速度がシステムに影響</span><span class="sxs-lookup"><span data-stu-id="5c0d2-110">How the BizTalkDTADb Insert and Processing Speed Affects Your System</span></span>  
 <span data-ttu-id="5c0d2-111">次に、追跡してみましょうで説明されているデータの経路[維持可能な最大の追跡スループットの測定](../core/measuring-maximum-sustainable-tracking-throughput.md)、およびシステムのさまざまなコンポーネントで BizTalkDTADb の挿入と処理速度の影響を評価します。</span><span class="sxs-lookup"><span data-stu-id="5c0d2-111">Now, let’s walk through the tracking data pathway that is described in [Measuring Maximum Sustainable Tracking Throughput](../core/measuring-maximum-sustainable-tracking-throughput.md), and evaluate the affect of BizTalkDTADb insert and processing speed on the various components of the system.</span></span>  
  
 <span data-ttu-id="5c0d2-112">以降、trackingdata テーブルおよびスプール テーブルでは、想像が、これらのテーブルから BizTalkDTADb データベースにデータを移動するプロセスは、少なくとも同じ速度に、ランタイムを挿入、BizTalkDTADb データベースにデータを挿入することがない場合、trackingdata テーブルとスプール テーブル、スプールと trackingdata テーブルは、バックログが蓄積が開始されます。</span><span class="sxs-lookup"><span data-stu-id="5c0d2-112">Starting with the trackingdata and spool tables, we can imagine that, if the processes that move data from these tables to the BizTalkDTADb database are not able to insert data into the BizTalkDTADb database at least as fast as the runtime is inserting into the trackingdata and spool tables, then the spool and trackingdata tables will start to build up a backlog.</span></span> <span data-ttu-id="5c0d2-113">最終的にドレインするまでにバックログを許可するメッセージのスループットに減少することがわかっている限りいない必ずしも短期的に悪いことになります。</span><span class="sxs-lookup"><span data-stu-id="5c0d2-113">This isn’t necessarily a bad thing in the short term as long as you know the message throughput will be reduced to allow the backlog to eventually drain.</span></span> <span data-ttu-id="5c0d2-114">ただし、として、スプール テーブルまたは trackingdata テーブルには、データが残っている間、そのされません、BizTalkDTADb データベースのグループ ハブ ページまたはその他のツールでクエリを追跡することによってクエリで使用できます。</span><span class="sxs-lookup"><span data-stu-id="5c0d2-114">However, as long as the data is still sitting in the spool or trackingdata tables, it will not be available in the BizTalkDTADb database for querying by tracking queries on the Group Hub page or any other tool.</span></span>  <span data-ttu-id="5c0d2-115">したがって、されません問題解決のために便利です。</span><span class="sxs-lookup"><span data-stu-id="5c0d2-115">Thus it will not be useful for problem resolution.</span></span> <span data-ttu-id="5c0d2-116">そのため、想定されるバックログ期間が短いことから追跡情報の問題が発生する必要がありますも BizTalkDTADb のデータを使用して、調査に必要な適切なタイミングで引き続き使用できますがあります。</span><span class="sxs-lookup"><span data-stu-id="5c0d2-116">Therefore any expected backlog periods must be short enough that the tracked information is still available in a timely fashion should a problem arise that needs to be investigated using BizTalkDTADb data.</span></span>  
  
 <span data-ttu-id="5c0d2-117">テストからわかる決定要因は、バックログが蓄積する場合 BizTalkDTADb データベース (TDDS および TrackedMessages_Copy_BizTalkMsgBoxDb) が、速度で BizTalkDTADb データベースの追跡データを移動するプロセスではありません。入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="5c0d2-117">From testing, we know that it isn’t the processes that move tracking data to the BizTalkDTADb database (that is, TDDS and TrackedMessages_Copy_BizTalkMsgBoxDb) that are the determining factor if a backlog builds up, but the speed of the BizTalkDTADb database in accepting the input.</span></span> <span data-ttu-id="5c0d2-118">通常、I/O バウンドになっている BizTalkDTADb データベースのデータ ファイルになります。</span><span class="sxs-lookup"><span data-stu-id="5c0d2-118">Typically, it is the data file of the BizTalkDTADb database that is I/O bound.</span></span> <span data-ttu-id="5c0d2-119">つまりに BizTalkDTADb データベースのデータ ファイルが置かれているドライブの速度は、DTA 全体の速度を決定するをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5c0d2-119">That is, it is the speed of the drive that the BizTalkDTADb database data file resides on that will determine the speed of the DTA overall.</span></span>  
  
## <a name="how-the-amount-of-data-in-biztalkdtadb-affects-io-speed"></a><span data-ttu-id="5c0d2-120">BizTalkDTADb のデータの量が I/O 速度に与える影響</span><span class="sxs-lookup"><span data-stu-id="5c0d2-120">How the Amount of Data in BizTalkDTADb Affects I/O Speed</span></span>  
 <span data-ttu-id="5c0d2-121">I/O 速度に関連するもう 1 つの主要要素が BizTalkDTADb データベース内のデータの量単により多くのデータであるために、BizTalkDTADb データベースの入力および処理の速度が低下として BizTalkDTADb データベースが増えるの追跡データの量、。新しいデータの挿入し、挿入ごとに必要な I/O の量に影響を並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="5c0d2-121">Another key factor related to the I/O speed is the amount of data in the BizTalkDTADb database: as the amount of tracked data in the BizTalkDTADb database increases, the input and processing speed of the BizTalkDTADb database decreases since there is simply more data to sort through as new data is inserted, and this affects the amount of I/O required for each insert.</span></span>  
  
 <span data-ttu-id="5c0d2-122">これは、アーカイブおよび削除でかかわってくる大きくなりすぎるため、BizTalkDTADb データベースを保持するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="5c0d2-122">This is where archiving and purging enter the picture since it is these processes that keep the BizTalkDTADb database from growing too large to keep up.</span></span> <span data-ttu-id="5c0d2-123">基本的な考え方では、位置が滞り始めるスプールと trackingdata テーブル レベルの下、BizTalkDTADb データベースのサイズを保持することを確認します。</span><span class="sxs-lookup"><span data-stu-id="5c0d2-123">The basic idea is to make sure that the BizTalkDTADb database size is kept below the level at which things begin to backup in the spool and trackingdata tables.</span></span> <span data-ttu-id="5c0d2-124">ただし、DTA Purge and Archive (BizTalkDTADb) SQL ジョブで実装されている削除とアーカイブのプロセスも必要なリソース (CPU、メモリ、および特に I/O) での MST を測定するときに考慮する必要があります、BizTalkDTADb データベース サーバーから追跡します。</span><span class="sxs-lookup"><span data-stu-id="5c0d2-124">However, the purge and archive processes implemented in the DTA Purge and Archive (BizTalkDTADb) SQL Job also require resources (CPU, Memory, and especially I/O) from the BizTalkDTADb database server, which must be taken into account when measuring MST with tracking.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c0d2-125">参照</span><span class="sxs-lookup"><span data-stu-id="5c0d2-125">See Also</span></span>  
 <span data-ttu-id="5c0d2-126">[維持可能な最大の追跡スループットの測定](../core/measuring-maximum-sustainable-tracking-throughput.md) </span><span class="sxs-lookup"><span data-stu-id="5c0d2-126">[Measuring Maximum Sustainable Tracking Throughput](../core/measuring-maximum-sustainable-tracking-throughput.md) </span></span>  
 <span data-ttu-id="5c0d2-127">[DTA 追跡の MST を測定するためのテスト シナリオ](../core/test-scenarios-for-measuring-mst-of-dta-tracking.md) </span><span class="sxs-lookup"><span data-stu-id="5c0d2-127">[Test Scenarios for Measuring MST of DTA Tracking](../core/test-scenarios-for-measuring-mst-of-dta-tracking.md) </span></span>  
 <span data-ttu-id="5c0d2-128">[DTA 追跡の MST を特定のヒントし、テクニック](../core/tips-and-tricks-for-finding-mst-of-dta-tracking.md) </span><span class="sxs-lookup"><span data-stu-id="5c0d2-128">[Tips and Tricks for Finding MST of DTA Tracking](../core/tips-and-tricks-for-finding-mst-of-dta-tracking.md) </span></span>  
 [<span data-ttu-id="5c0d2-129">追跡データベースのサイズに関するガイドライン</span><span class="sxs-lookup"><span data-stu-id="5c0d2-129">Tracking Database Sizing Guidelines</span></span>](../core/tracking-database-sizing-guidelines.md)