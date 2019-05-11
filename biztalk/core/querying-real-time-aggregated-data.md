---
title: クエリ、リアルタイム集計データ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- queries [BAM], real-time data
- BAM, real-time data
ms.assetid: f60a34a1-ac64-47c7-8f83-1bc301170590
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72ee6612fc99d9411f0fb26c91c5d8ad6041edf1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398291"
---
# <a name="querying-real-time-aggregated-data"></a><span data-ttu-id="ac7cf-102">リアルタイム集計データに対するクエリの実行</span><span class="sxs-lookup"><span data-stu-id="ac7cf-102">Querying Real-Time Aggregated Data</span></span>
<span data-ttu-id="ac7cf-103">リアルタイム集計 (RTA) データは、BAM プライマリ インポート データベースに動的に作成された SQL ビューにクエリで使用できます。</span><span class="sxs-lookup"><span data-stu-id="ac7cf-103">The real-time aggregation (RTA) data is available for queries in a dynamically created SQL View in the BAM Primary Import database.</span></span>  
  
 <span data-ttu-id="ac7cf-104">クエリでのビューの名前は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ac7cf-104">The name of this view is</span></span>  
  
 <span data-ttu-id="ac7cf-105">**bam_\<** *ViewName* **\>_\<** *RTAName* **\>_RTAView**</span><span class="sxs-lookup"><span data-stu-id="ac7cf-105">**bam_\<** *ViewName* **\>_\<** *RTAName* **\>_RTAView**</span></span>  
  
 <span data-ttu-id="ac7cf-106">場所</span><span class="sxs-lookup"><span data-stu-id="ac7cf-106">Where</span></span>  
  
 <span data-ttu-id="ac7cf-107">**\<** *ViewName* **\>** は、BAM 定義 XML 内の View 要素の Name 属性、関連する Microsoft Excel ウィザードに入力されたビューの名前と同じです。</span><span class="sxs-lookup"><span data-stu-id="ac7cf-107">**\<** *ViewName* **\>** is the Name attribute of the View element in the BAM definition XML, which is the same as the View Name entered in the related Microsoft Excel wizards.</span></span>  
  
 <span data-ttu-id="ac7cf-108">**\<** *RTAName* **\>** BAM で固有に生成される BAM 定義 XML 内の RealTimeAggregation 要素の Name 属性に基づいてビューの名前。</span><span class="sxs-lookup"><span data-stu-id="ac7cf-108">**\<** *RTAName* **\>** is the Name attribute of the RealTimeAggregation element in the BAM Definition XML, which BAM generates to be unique based on the view name.</span></span>  
  
 <span data-ttu-id="ac7cf-109">リアルタイム集計データを照会するときに、次の条件を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac7cf-109">It is important to note the following conditions when querying real-time aggregated data:</span></span>  
  
-   <span data-ttu-id="ac7cf-110">一定の期間 (既定値は 1 日) の集計を保持することはありませんが非常に大きくと、リアルタイム集計を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac7cf-110">The real-time aggregations must be configured to keep the aggregations for a given amount of time (the default is one day) and to never grow very large.</span></span> <span data-ttu-id="ac7cf-111">古い集計は、代わりに、OLAP キューブで使用可能なにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac7cf-111">The older aggregations should be available in the OLAP cubes instead.</span></span>  
  
-   <span data-ttu-id="ac7cf-112">RTA に対するクエリは、RTA データ用のオンライン時間帯内となる時間ディメンションでフィルター処理を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac7cf-112">Any query against RTA must include filtering on a time dimension that will be inside the online window for the RTA data.</span></span> <span data-ttu-id="ac7cf-113">これは、BAM データを実行するためのチャンク単位で、データをドロップする BAM でのタイムスタンプに基づく Rta のメンテナンスは最適化されています。</span><span class="sxs-lookup"><span data-stu-id="ac7cf-113">This is necessary because BAM performs data maintenance for RTAs based  on the  timestamp on the BAM dataand is optimized to drop the data in chunks.</span></span> <span data-ttu-id="ac7cf-114">したがって TRANSACT-SQL コマンドを単純に送信する場合は、"`select *`"、結果に予期しない影響が及びます。</span><span class="sxs-lookup"><span data-stu-id="ac7cf-114">Thus if you simply send the Transact-SQL command "`select *`", the results will fluctuate unpredictably.</span></span>  
  
-   <span data-ttu-id="ac7cf-115">DirectEventStream を使用して bam アクティビティ データを送信する場合は、リアルタイム集計データには、待機時間がありません: 即座に認識と呼び出し元のアプリケーションでトランザクションがコミットされます。</span><span class="sxs-lookup"><span data-stu-id="ac7cf-115">If the activity data is sent to BAM via the DirectEventStream, the real-time aggregated data has no latency – it appears instantaneously when the transaction in the calling Application commits.</span></span>  
  
-   <span data-ttu-id="ac7cf-116">BufferedEventStream を使用して bam アクティビティ データを送信する場合、RTA データ表示されますクエリの数秒後、BAM イベント バス サービスと、BAM プライマリ インポート データベースをホストする SQL server の負荷によって異なります。</span><span class="sxs-lookup"><span data-stu-id="ac7cf-116">If the activity data is sent to BAM via the BufferedEventStream, the RTA data will show up for queries a few seconds later, depending on the load of the BAM Event Bus service(s) and the SQL server that hosts the BAM Primary Import database.</span></span>  
  
-   <span data-ttu-id="ac7cf-117">BAM では、変更または挿入トリガーを使用してアクティビティ データ ストレージ レコードとの同期に保持されているテーブルでリアルタイムの集計を行います。</span><span class="sxs-lookup"><span data-stu-id="ac7cf-117">BAM bases the real-time aggregation on a table that it maintains in synchronization with the changes or insertions in the activity data storage records using triggers.</span></span> <span data-ttu-id="ac7cf-118">詳細については、次を参照してください。[アクティビティ データのストレージ](../core/activity-data-storage.md)します。</span><span class="sxs-lookup"><span data-stu-id="ac7cf-118">For more information, see [Activity Data Storage](../core/activity-data-storage.md).</span></span> <span data-ttu-id="ac7cf-119">そのため、リアルタイム集計では、パフォーマンスに大きな影響をことができます。</span><span class="sxs-lookup"><span data-stu-id="ac7cf-119">Thus, the real-time aggregation can have a significant performance impact.</span></span> <span data-ttu-id="ac7cf-120">詳細については、次を参照してください。[リアルタイム集計](../core/real-time-aggregations.md)します。</span><span class="sxs-lookup"><span data-stu-id="ac7cf-120">For more information, see [Real-Time Aggregations](../core/real-time-aggregations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac7cf-121">参照</span><span class="sxs-lookup"><span data-stu-id="ac7cf-121">See Also</span></span>  
 <span data-ttu-id="ac7cf-122">[スケジュールされたクエリを実行する集計データ](../core/querying-scheduled-aggregated-data.md) </span><span class="sxs-lookup"><span data-stu-id="ac7cf-122">[Querying Scheduled Aggregated Data](../core/querying-scheduled-aggregated-data.md) </span></span>  
 [<span data-ttu-id="ac7cf-123">BAM データのクエリ</span><span class="sxs-lookup"><span data-stu-id="ac7cf-123">Querying BAM Data</span></span>](../core/querying-bam-data.md)