---
title: "BAM インターセプター パフォーマンス カウンター |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b9b64ae1-4d94-4c3c-add1-fa020713be5c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 989316edff34463905c7547db815b3daaf4d4a46
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="bam-interceptor-performance-counters"></a><span data-ttu-id="71e73-102">BAM インターセプタのパフォーマンス カウンタ</span><span class="sxs-lookup"><span data-stu-id="71e73-102">BAM Interceptor Performance Counters</span></span>
<span data-ttu-id="71e73-103">パフォーマンス カウンタにより、BAM インターセプタによって実行される作業の特定の側面を監視できます。</span><span class="sxs-lookup"><span data-stu-id="71e73-103">Performance counters allow you to monitor specific aspects of work performed by the BAM interceptors.</span></span> <span data-ttu-id="71e73-104">パフォーマンス カウンターは、サーバー パフォーマンスに関する問題を特定してトラブルシューティングする際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="71e73-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="71e73-105">次の表に、BAM インターセプタで利用できるパフォーマンス カウンタを示します。</span><span class="sxs-lookup"><span data-stu-id="71e73-105">The following table lists the performance counters available for the BAM interceptors.</span></span> <span data-ttu-id="71e73-106">パフォーマンス カウンタのカテゴリは "BAM インターセプタ" です。</span><span class="sxs-lookup"><span data-stu-id="71e73-106">The performance counters category is “BAM Interceptor.”</span></span>  
  
|<span data-ttu-id="71e73-107">カウンター</span><span class="sxs-lookup"><span data-stu-id="71e73-107">Counter</span></span>|<span data-ttu-id="71e73-108">Description</span><span class="sxs-lookup"><span data-stu-id="71e73-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="71e73-109">Avg. Failed BAM Events/Flush Avg</span><span class="sxs-lookup"><span data-stu-id="71e73-109">Avg. Failed BAM Events/Flush Avg</span></span>|<span data-ttu-id="71e73-110">プライマリ インポート データベースへのデータ フラッシュ中に発生したエラー BAM イベントの平均数です。</span><span class="sxs-lookup"><span data-stu-id="71e73-110">The average number of failed BAM events that occurred during a flush of data to the Primary Import database.</span></span>|  
|<span data-ttu-id="71e73-111">Successful BAM Events/Flush</span><span class="sxs-lookup"><span data-stu-id="71e73-111">Successful BAM Events/Flush</span></span>|<span data-ttu-id="71e73-112">プライマリ インポート データベースへのデータ フラッシュ中に発生した正常 BAM イベントの平均数です。</span><span class="sxs-lookup"><span data-stu-id="71e73-112">The average number of successful BAM events that occurred during a data flush to the Primary Import database.</span></span> <span data-ttu-id="71e73-113">トランザクションがロールバックされる場合、これらのイベントはデータベースに保存されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="71e73-113">The events may not be persisted to the database if the transaction is rolled back.</span></span>|  
|<span data-ttu-id="71e73-114">Avg. Extraction sec/BAM Event</span><span class="sxs-lookup"><span data-stu-id="71e73-114">Avg. Extraction sec/BAM Event</span></span>|<span data-ttu-id="71e73-115">BAM イベントの抽出にかかった時間の平均値です。</span><span class="sxs-lookup"><span data-stu-id="71e73-115">The average amount of time spent extracting BAM events.</span></span>|  
|<span data-ttu-id="71e73-116">Avg. Flush sec/BAM Event</span><span class="sxs-lookup"><span data-stu-id="71e73-116">Avg. Flush sec/BAM Event</span></span>|<span data-ttu-id="71e73-117">BAM イベントのフラッシュにかかった時間の平均値です。</span><span class="sxs-lookup"><span data-stu-id="71e73-117">The average amount of time spent flushing BAM events.</span></span>|  
|<span data-ttu-id="71e73-118">Total Failed BAM Events During Flush</span><span class="sxs-lookup"><span data-stu-id="71e73-118">Total Failed BAM Events During Flush</span></span>|<span data-ttu-id="71e73-119">データ フラッシュ中に発生したエラー BAM イベントの合計数です。</span><span class="sxs-lookup"><span data-stu-id="71e73-119">The total number of failed BAM events that occurred during the data flush</span></span>|  
|<span data-ttu-id="71e73-120">Total Successful BAM Events During Flush</span><span class="sxs-lookup"><span data-stu-id="71e73-120">Total Successful BAM Events During Flush</span></span>|<span data-ttu-id="71e73-121">プライマリ インポート データベースにフラッシュされた正常 BAM イベントの合計数です。</span><span class="sxs-lookup"><span data-stu-id="71e73-121">The total number of successful BAM events flushed to the Primary Import database.</span></span> <span data-ttu-id="71e73-122">トランザクションがロールバックされる場合、これらのイベントはデータベースに保存されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="71e73-122">The events may not be persisted to the database if the transaction is rolled back.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="71e73-123">参照</span><span class="sxs-lookup"><span data-stu-id="71e73-123">See Also</span></span>  
 [<span data-ttu-id="71e73-124">BAM パフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="71e73-124">BAM Performance Counters</span></span>](../core/bam-performance-counters.md)