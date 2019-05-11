---
title: BAM パフォーマンス カウンター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [BAM], performance counters
- performance, counters [BAM]
ms.assetid: e23f7038-36a5-4957-bc73-47011763d109
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad0502e27bfaefb25d03e88b6d1730d0495cc189
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358458"
---
# <a name="bam-performance-counters"></a><span data-ttu-id="5e949-102">BAM パフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="5e949-102">BAM Performance Counters</span></span>
<span data-ttu-id="5e949-103">パフォーマンス カウンターを使用すると、BAM イベント バス サービスによって実行される作業に関する特定の側面を監視できます。</span><span class="sxs-lookup"><span data-stu-id="5e949-103">Performance counters allow you to monitor specific aspects of work performed by the BAM Event Bus Service.</span></span> <span data-ttu-id="5e949-104">パフォーマンス カウンターは、サーバー パフォーマンスに関する問題を特定してトラブルシューティングする際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5e949-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="5e949-105">次の表は、ビジネス アクティビティ監視で利用できるパフォーマンス カウンターの一覧を示しています。</span><span class="sxs-lookup"><span data-stu-id="5e949-105">The following table lists the performance counters available in Business Activity Monitoring.</span></span>  
  
|<span data-ttu-id="5e949-106">カウンター</span><span class="sxs-lookup"><span data-stu-id="5e949-106">Counter</span></span>|<span data-ttu-id="5e949-107">説明</span><span class="sxs-lookup"><span data-stu-id="5e949-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5e949-108">Events being processed</span><span class="sxs-lookup"><span data-stu-id="5e949-108">Events being processed</span></span>|<span data-ttu-id="5e949-109">BAM イベント バス サービスが現在処理しているイベントの数</span><span class="sxs-lookup"><span data-stu-id="5e949-109">The number of events the BAM Event Bus Service is currently processing</span></span>|  
|<span data-ttu-id="5e949-110">Batches being processed</span><span class="sxs-lookup"><span data-stu-id="5e949-110">Batches being processed</span></span>|<span data-ttu-id="5e949-111">BAM イベント バス サービスが現在処理しているバッチの数</span><span class="sxs-lookup"><span data-stu-id="5e949-111">The number of batches the BAM Event Bus Service is currently processing</span></span>|  
|<span data-ttu-id="5e949-112">Events Committed</span><span class="sxs-lookup"><span data-stu-id="5e949-112">Events Committed</span></span>|<span data-ttu-id="5e949-113">最後の 1 秒間に BAM イベント バス サービスが SQL Server にコミットしたイベントの数</span><span class="sxs-lookup"><span data-stu-id="5e949-113">The number of events the BAM Event Bus Service has committed to SQL Server in the last second.</span></span>|  
|<span data-ttu-id="5e949-114">Records Committed</span><span class="sxs-lookup"><span data-stu-id="5e949-114">Records Committed</span></span>|<span data-ttu-id="5e949-115">最後の 1 秒間に BAM イベント バス サービスが SQL Server にコミットしたレコードの数</span><span class="sxs-lookup"><span data-stu-id="5e949-115">The number of records the BAM Event Bus Service has committed to SQL Server in the last second.</span></span>|  
|<span data-ttu-id="5e949-116">Batches Committed</span><span class="sxs-lookup"><span data-stu-id="5e949-116">Batches Committed</span></span>|<span data-ttu-id="5e949-117">最後の 1 秒間に BAM イベント バス サービスが SQL Server にコミットしたバッチの数</span><span class="sxs-lookup"><span data-stu-id="5e949-117">The number of batches the BAM Event Bus Service has committed to SQL Server in the last second.</span></span>|  
|<span data-ttu-id="5e949-118">Total Events</span><span class="sxs-lookup"><span data-stu-id="5e949-118">Total Events</span></span>|<span data-ttu-id="5e949-119">BAM イベント バス サービスが開始以降に処理したイベントの数</span><span class="sxs-lookup"><span data-stu-id="5e949-119">The number of events the BAM Event Bus Service has processed since you started it.</span></span>|  
|<span data-ttu-id="5e949-120">Total Records</span><span class="sxs-lookup"><span data-stu-id="5e949-120">Total Records</span></span>|<span data-ttu-id="5e949-121">BAM イベント バス サービスが開始以降に処理したレコードの数</span><span class="sxs-lookup"><span data-stu-id="5e949-121">Then number of records the BAM Event Bus Service has processed since you started it.</span></span>|  
|<span data-ttu-id="5e949-122">Total Batches</span><span class="sxs-lookup"><span data-stu-id="5e949-122">Total Batches</span></span>|<span data-ttu-id="5e949-123">BAM イベント バス サービスが開始以降に処理したバッチの数</span><span class="sxs-lookup"><span data-stu-id="5e949-123">Then number of batches the BAM Event Bus Service has processed since you started it.</span></span>|  
|<span data-ttu-id="5e949-124">Total Failed Batches</span><span class="sxs-lookup"><span data-stu-id="5e949-124">Total Failed Batches</span></span>|<span data-ttu-id="5e949-125">BAM イベント バス サービスが開始以降に処理に失敗したバッチの数</span><span class="sxs-lookup"><span data-stu-id="5e949-125">Then number of batches the BAM Event Bus Service has failed to process since you started it.</span></span>|  
|<span data-ttu-id="5e949-126">Total Failed Events</span><span class="sxs-lookup"><span data-stu-id="5e949-126">Total Failed Events</span></span>|<span data-ttu-id="5e949-127">BAM イベント バス サービスが開始以降に処理に失敗したイベントの数</span><span class="sxs-lookup"><span data-stu-id="5e949-127">Then number of events the BAM Event Bus Service has failed to process since you started it.</span></span>|  
  
 <span data-ttu-id="5e949-128">パフォーマンス カウンターは、BizTalk:TDDS パフォーマンス オブジェクトの下のパフォーマンス モニター (perfmon) にあります。</span><span class="sxs-lookup"><span data-stu-id="5e949-128">The performance counters are located in the Performance Monitor (perfmon) under the BizTalk:TDDS performance object.</span></span> <span data-ttu-id="5e949-129">パフォーマンス カウンターのインスタンス名は、ソース サーバーの名前とソース データベースの名前を組み合わせたものになります。</span><span class="sxs-lookup"><span data-stu-id="5e949-129">The instance name of the performance counters are a combination of the source server name and the name of the source database.</span></span> <span data-ttu-id="5e949-130">同一のコンピューター上で、2 つの BAM イベント バス サービスが、2 つの異なるソース データベースに対して実行されている場合は、2 つの BAM イベント バス サービス カウンター インスタンスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5e949-130">If two of the BAM Event Bus Services are running on the same computer against two different source databases, you will see two instances of the BAM Event Bus Service counters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e949-131">参照</span><span class="sxs-lookup"><span data-stu-id="5e949-131">See Also</span></span>  
 <span data-ttu-id="5e949-132">[BAM イベント バス サービスの管理](../core/managing-the-bam-event-bus-service.md) </span><span class="sxs-lookup"><span data-stu-id="5e949-132">[Managing the BAM Event Bus Service](../core/managing-the-bam-event-bus-service.md) </span></span>  
 <span data-ttu-id="5e949-133">[BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="5e949-133">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="5e949-134">BAM の管理</span><span class="sxs-lookup"><span data-stu-id="5e949-134">Managing BAM</span></span>](../core/managing-bam.md)