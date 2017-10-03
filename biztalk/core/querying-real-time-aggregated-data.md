---
title: "集計データをリアルタイムに照会 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- queries [BAM], real-time data
- BAM, real-time data
ms.assetid: f60a34a1-ac64-47c7-8f83-1bc301170590
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f02ec8a33fdb050462860efc6c6a0cd5f8fa5650
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="querying-real-time-aggregated-data"></a><span data-ttu-id="e079b-102">リアルタイム集計データに対するクエリの実行</span><span class="sxs-lookup"><span data-stu-id="e079b-102">Querying Real-Time Aggregated Data</span></span>
<span data-ttu-id="e079b-103">BAM プライマリ インポート データベースで動的に作成された SQL ビューでは、リアルタイム集計 (RTA) データに対してクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e079b-103">The real-time aggregation (RTA) data is available for queries in a dynamically created SQL View in the BAM Primary Import database.</span></span>  
  
 <span data-ttu-id="e079b-104">クエリでのビューの名前は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="e079b-104">The name of this view is</span></span>  
  
 <span data-ttu-id="e079b-105">**bam _\<**  *ViewName* **> _\<**  *RTAName* **> _RTAView**</span><span class="sxs-lookup"><span data-stu-id="e079b-105">**bam_\<** *ViewName* **>_\<** *RTAName* **>_RTAView**</span></span>  
  
 <span data-ttu-id="e079b-106">場所</span><span class="sxs-lookup"><span data-stu-id="e079b-106">Where</span></span>  
  
 <span data-ttu-id="e079b-107">**\<***ViewName*  **>**  BAM 定義 XML 内の View 要素の Name 属性は、関連する Microsoft Excel ウィザードに入力されたビュー名と同じです。</span><span class="sxs-lookup"><span data-stu-id="e079b-107">**\<** *ViewName* **>** is the Name attribute of the View element in the BAM definition XML, which is the same as the View Name entered in the related Microsoft Excel wizards.</span></span>  
  
 <span data-ttu-id="e079b-108">**\<***RTAName*  **>** は一意である BAM が生成される BAM 定義 XML 内の RealTimeAggregation 要素の Name 属性に基づいて、ビュー名。</span><span class="sxs-lookup"><span data-stu-id="e079b-108">**\<** *RTAName* **>** is the Name attribute of the RealTimeAggregation element in the BAM Definition XML, which BAM generates to be unique based on the view name.</span></span>  
  
 <span data-ttu-id="e079b-109">リアルタイム集計データに対してクエリを実行する際は、次の条件に特に注意してください。</span><span class="sxs-lookup"><span data-stu-id="e079b-109">It is important to note the following conditions when querying real-time aggregated data:</span></span>  
  
-   <span data-ttu-id="e079b-110">特定の期間 (既定では 1 日) にわたって集計を継続するようにリアルタイム集計を設定する必要がありますが、データ量が増えすぎないようにします。</span><span class="sxs-lookup"><span data-stu-id="e079b-110">The real-time aggregations must be configured to keep the aggregations for a given amount of time (the default is one day) and to never grow very large.</span></span> <span data-ttu-id="e079b-111">また、OLAP キューブ内で古い集計データが利用可能になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e079b-111">The older aggregations should be available in the OLAP cubes instead.</span></span>  
  
-   <span data-ttu-id="e079b-112">RTA に対するクエリでは、RTA データ用のオンライン ウィンドウに表示される時間ディメンションに関してフィルター処理を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e079b-112">Any query against RTA must include filtering on a time dimension that will be inside the online window for the RTA data.</span></span> <span data-ttu-id="e079b-113">これは、BAM では RTA のデータ保守が BAM データのタイムスタンプに基づいて行われ、最適化されてチャンク内のデータが削除されるためです。</span><span class="sxs-lookup"><span data-stu-id="e079b-113">This is necessary because BAM performs data maintenance for RTAs based  on the  timestamp on the BAM dataand is optimized to drop the data in chunks.</span></span> <span data-ttu-id="e079b-114">したがって、Transact-SQL コマンド "`select *`" を送信するだけでは、結果が予期せず変動する場合があります。</span><span class="sxs-lookup"><span data-stu-id="e079b-114">Thus if you simply send the Transact-SQL command "`select *`", the results will fluctuate unpredictably.</span></span>  
  
-   <span data-ttu-id="e079b-115">DirectEventStream を使用してアクティビティ データを BAM に送信する場合、リアルタイム集計データは、呼び出し元アプリケーションのトランザクションが実行されると直ちに表示され、待機時間がありません。</span><span class="sxs-lookup"><span data-stu-id="e079b-115">If the activity data is sent to BAM via the DirectEventStream, the real-time aggregated data has no latency – it appears instantaneously when the transaction in the calling Application commits.</span></span>  
  
-   <span data-ttu-id="e079b-116">BufferedEventStream を使用してアクティビティ データを BAM に送信する場合、RTA データは数秒後にクエリとして表示されます。待機時間は、BAM Event Bus サービスと、BAM プライマリ インポート データベースをホストする SQL サーバーの負荷によって異なります。</span><span class="sxs-lookup"><span data-stu-id="e079b-116">If the activity data is sent to BAM via the BufferedEventStream, the RTA data will show up for queries a few seconds later, depending on the load of the BAM Event Bus service(s) and the SQL server that hosts the BAM Primary Import database.</span></span>  
  
-   <span data-ttu-id="e079b-117">BAM では、トリガーを使用してアクティビティ データ ストレージ レコードの変更や挿入に関する同期が行われているテーブルに基づいて、リアルタイムの集計を行います。</span><span class="sxs-lookup"><span data-stu-id="e079b-117">BAM bases the real-time aggregation on a table that it maintains in synchronization with the changes or insertions in the activity data storage records using triggers.</span></span> <span data-ttu-id="e079b-118">詳細については、次を参照してください。[アクティビティ データのストレージ](../core/activity-data-storage.md)です。</span><span class="sxs-lookup"><span data-stu-id="e079b-118">For more information, see [Activity Data Storage](../core/activity-data-storage.md).</span></span> <span data-ttu-id="e079b-119">リアルタイム集計はパフォーマンスに大きな影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e079b-119">Thus, the real-time aggregation can have a significant performance impact.</span></span> <span data-ttu-id="e079b-120">詳細については、次を参照してください。[リアルタイム集計](../core/real-time-aggregations.md)です。</span><span class="sxs-lookup"><span data-stu-id="e079b-120">For more information, see [Real-Time Aggregations](../core/real-time-aggregations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e079b-121">参照</span><span class="sxs-lookup"><span data-stu-id="e079b-121">See Also</span></span>  
 <span data-ttu-id="e079b-122">[スケジュールされているクエリを実行する集計データ](../core/querying-scheduled-aggregated-data.md) </span><span class="sxs-lookup"><span data-stu-id="e079b-122">[Querying Scheduled Aggregated Data](../core/querying-scheduled-aggregated-data.md) </span></span>  
 [<span data-ttu-id="e079b-123">BAM データを照会します。</span><span class="sxs-lookup"><span data-stu-id="e079b-123">Querying BAM Data</span></span>](../core/querying-bam-data.md)