---
title: DTA 追跡のパフォーマンスに関する動作を理解する |Microsoft ドキュメント
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
ms.openlocfilehash: 278d1e3c4b52c14c68d692ce3d3a3179d15bb10b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287026"
---
# <a name="understanding-dta-tracking-performance-behavior"></a><span data-ttu-id="9b5a3-102">DTA 追跡のパフォーマンス特性について</span><span class="sxs-lookup"><span data-stu-id="9b5a3-102">Understanding DTA Tracking Performance Behavior</span></span>
<span data-ttu-id="9b5a3-103">DTA 追跡の維持可能な最大スループット (MST) を決定する主要な要因として、次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="9b5a3-103">The primary factors that determine maximum sustainable throughput (MST) for DTA tracking are:</span></span>  
  
-   <span data-ttu-id="9b5a3-104">システムに必要なメッセージのスループット (単位時間に受信されたメッセージ)。</span><span class="sxs-lookup"><span data-stu-id="9b5a3-104">The desired message throughput, that is, messages received per unit time, for the system.</span></span>  
  
-   <span data-ttu-id="9b5a3-105">メッセージごとの追跡データ量。</span><span class="sxs-lookup"><span data-stu-id="9b5a3-105">How much data is being tracked for each message.</span></span>  
  
-   <span data-ttu-id="9b5a3-106">データが BizTalkDTADb データベースから削除されるまでの存続期間 (データ保有期間)。</span><span class="sxs-lookup"><span data-stu-id="9b5a3-106">How long the data is to live in the BizTalkDTADb database before being purged, that is, the data retention window.</span></span>  
  
-   <span data-ttu-id="9b5a3-107">BizTalkDTADb のデータをアーカイブして削除するかどうか。</span><span class="sxs-lookup"><span data-stu-id="9b5a3-107">Whether or not the BizTalkDTADb data is archived as well as purged.</span></span> <span data-ttu-id="9b5a3-108">アーカイブは任意ですが、削除は定期的に行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b5a3-108">Archiving is optional but purging must be performed periodically.</span></span>  
  
 <span data-ttu-id="9b5a3-109">これらの要因のすべてに共通するのは、DTA がデータを受け入れて処理 (アーカイブおよび削除) する速度です。</span><span class="sxs-lookup"><span data-stu-id="9b5a3-109">There is one thing that all of these factors have in common: the speed at which the DTA can accept and process (archive and purge) data.</span></span>  
  
## <a name="how-the-biztalkdtadb-insert-and-processing-speed-affects-your-system"></a><span data-ttu-id="9b5a3-110">BizTalkDTADb の挿入と処理速度がシステムに与える影響</span><span class="sxs-lookup"><span data-stu-id="9b5a3-110">How the BizTalkDTADb Insert and Processing Speed Affects Your System</span></span>  
 <span data-ttu-id="9b5a3-111">ここで、追跡を見ていきましょうに記載されているデータの経路[維持可能な最大の追跡スループットの測定](../core/measuring-maximum-sustainable-tracking-throughput.md)、およびシステムのさまざまなコンポーネントで BizTalkDTADb の挿入と処理速度の影響を評価します。</span><span class="sxs-lookup"><span data-stu-id="9b5a3-111">Now, let’s walk through the tracking data pathway that is described in [Measuring Maximum Sustainable Tracking Throughput](../core/measuring-maximum-sustainable-tracking-throughput.md), and evaluate the affect of BizTalkDTADb insert and processing speed on the various components of the system.</span></span>  
  
 <span data-ttu-id="9b5a3-112">まず trackingdata テーブルとスプール テーブルについて考えてみると、これらのテーブルから BizTalkDTADb データベースにデータを移動するプロセスが、ランタイムによって trackingdata テーブルおよびスプール テーブルにデータが挿入されるのと同等以上の速度で BizTalkDTADb データベースにデータを挿入できなければ、trackingdata テーブルおよびスプール テーブルにバックログが蓄積され始めることは想像がつきます。</span><span class="sxs-lookup"><span data-stu-id="9b5a3-112">Starting with the trackingdata and spool tables, we can imagine that, if the processes that move data from these tables to the BizTalkDTADb database are not able to insert data into the BizTalkDTADb database at least as fast as the runtime is inserting into the trackingdata and spool tables, then the spool and trackingdata tables will start to build up a backlog.</span></span> <span data-ttu-id="9b5a3-113">これは、メッセージ スループットの低下により最終的にはバックログを解消できることがわかっている限り、短期的には必ずしも問題にはなりません。</span><span class="sxs-lookup"><span data-stu-id="9b5a3-113">This isn’t necessarily a bad thing in the short term as long as you know the message throughput will be reduced to allow the backlog to eventually drain.</span></span> <span data-ttu-id="9b5a3-114">しかし、データがスプール テーブルまたは trackingdata テーブルに残っている間は、BizTalkDTADb データベースのデータを [グループ ハブ] ページでクエリを追跡したりその他のツールで照会することはできません。</span><span class="sxs-lookup"><span data-stu-id="9b5a3-114">However, as long as the data is still sitting in the spool or trackingdata tables, it will not be available in the BizTalkDTADb database for querying by tracking queries on the Group Hub page or any other tool.</span></span>  <span data-ttu-id="9b5a3-115">このため、問題解決には役立ちません。</span><span class="sxs-lookup"><span data-stu-id="9b5a3-115">Thus it will not be useful for problem resolution.</span></span> <span data-ttu-id="9b5a3-116">したがって、想定されるバックログ期間は、BizTalkDTADb データに基づいて調査する必要のある問題が発生した時点でタイムリーに追跡情報を利用できる程度に抑える必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b5a3-116">Therefore any expected backlog periods must be short enough that the tracked information is still available in a timely fashion should a problem arise that needs to be investigated using BizTalkDTADb data.</span></span>  
  
 <span data-ttu-id="9b5a3-117">テストの結果、バックログが蓄積されるかどうかを決定する要因は、追跡データを BizTalkDTADb データベースに移動するプロセス (TDDS および TrackedMessages_Copy_BizTalkMsgBoxDb) ではなく、BizTalkDTADb データベースが入力を受け入れる速度であることがわかっています。</span><span class="sxs-lookup"><span data-stu-id="9b5a3-117">From testing, we know that it isn’t the processes that move tracking data to the BizTalkDTADb database (that is, TDDS and TrackedMessages_Copy_BizTalkMsgBoxDb) that are the determining factor if a backlog builds up, but the speed of the BizTalkDTADb database in accepting the input.</span></span> <span data-ttu-id="9b5a3-118">通常、I/O バインドになるのは BizTalkDTADb データベースのデータ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="9b5a3-118">Typically, it is the data file of the BizTalkDTADb database that is I/O bound.</span></span> <span data-ttu-id="9b5a3-119">つまり、DTA 全体の速度を決定するのは、BizTalkDTADb データベースのデータ ファイルが存在するドライブの速度ということになります。</span><span class="sxs-lookup"><span data-stu-id="9b5a3-119">That is, it is the speed of the drive that the BizTalkDTADb database data file resides on that will determine the speed of the DTA overall.</span></span>  
  
## <a name="how-the-amount-of-data-in-biztalkdtadb-affects-io-speed"></a><span data-ttu-id="9b5a3-120">BizTalkDTADb のデータ量が I/O 速度に与える影響</span><span class="sxs-lookup"><span data-stu-id="9b5a3-120">How the Amount of Data in BizTalkDTADb Affects I/O Speed</span></span>  
 <span data-ttu-id="9b5a3-121">I/O 速度に関連するもう 1 つの主要な要因は、BizTalkDTADb データベースのデータ量です。BizTalkDTADb データベース内の追跡データの量が多くなると、新しいデータの挿入時に並べ替えるデータの量が多くなり、これが挿入ごとに必要な I/O の量に影響するため、BizTalkDTADb データベースの入力および処理の速度は低下します。</span><span class="sxs-lookup"><span data-stu-id="9b5a3-121">Another key factor related to the I/O speed is the amount of data in the BizTalkDTADb database: as the amount of tracked data in the BizTalkDTADb database increases, the input and processing speed of the BizTalkDTADb database decreases since there is simply more data to sort through as new data is inserted, and this affects the amount of I/O required for each insert.</span></span>  
  
 <span data-ttu-id="9b5a3-122">ここでかかわってくるのが、BizTalkDTADb データベースのサイズが大きくなりすぎないように維持するアーカイブと削除のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="9b5a3-122">This is where archiving and purging enter the picture since it is these processes that keep the BizTalkDTADb database from growing too large to keep up.</span></span> <span data-ttu-id="9b5a3-123">基本的な考え方は、BizTalkDTADb データベースのサイズを抑え、スプール テーブルと trackingdata テーブルにデータが滞り始めるレベルに達しないようにするというものです。</span><span class="sxs-lookup"><span data-stu-id="9b5a3-123">The basic idea is to make sure that the BizTalkDTADb database size is kept below the level at which things begin to backup in the spool and trackingdata tables.</span></span> <span data-ttu-id="9b5a3-124">ただし、DTA Purge and Archive (BizTalkDTADb) SQL ジョブに実装されている削除とアーカイブのプロセスも BizTalkDTADb データベース サーバーのリソース (CPU、メモリ、そして特に I/O) を必要とするため、追跡を有効にして MST を測定する際にはこの点も考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b5a3-124">However, the purge and archive processes implemented in the DTA Purge and Archive (BizTalkDTADb) SQL Job also require resources (CPU, Memory, and especially I/O) from the BizTalkDTADb database server, which must be taken into account when measuring MST with tracking.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b5a3-125">参照</span><span class="sxs-lookup"><span data-stu-id="9b5a3-125">See Also</span></span>  
 <span data-ttu-id="9b5a3-126">[維持可能な最大の追跡スループットの測定](../core/measuring-maximum-sustainable-tracking-throughput.md) </span><span class="sxs-lookup"><span data-stu-id="9b5a3-126">[Measuring Maximum Sustainable Tracking Throughput](../core/measuring-maximum-sustainable-tracking-throughput.md) </span></span>  
 <span data-ttu-id="9b5a3-127">[DTA 追跡の MST を測定するためのシナリオをテストします。](../core/test-scenarios-for-measuring-mst-of-dta-tracking.md) </span><span class="sxs-lookup"><span data-stu-id="9b5a3-127">[Test Scenarios for Measuring MST of DTA Tracking](../core/test-scenarios-for-measuring-mst-of-dta-tracking.md) </span></span>  
 <span data-ttu-id="9b5a3-128">[DTA 追跡の MST の検索のヒントし、テクニック](../core/tips-and-tricks-for-finding-mst-of-dta-tracking.md) </span><span class="sxs-lookup"><span data-stu-id="9b5a3-128">[Tips and Tricks for Finding MST of DTA Tracking](../core/tips-and-tricks-for-finding-mst-of-dta-tracking.md) </span></span>  
 [<span data-ttu-id="9b5a3-129">追跡データベースのサイズに関するガイドライン</span><span class="sxs-lookup"><span data-stu-id="9b5a3-129">Tracking Database Sizing Guidelines</span></span>](../core/tracking-database-sizing-guidelines.md)