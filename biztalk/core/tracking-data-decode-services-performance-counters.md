---
title: Tracking Data Decode Services のパフォーマンス カウンター |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 733450b1-71b5-48a4-9ac3-cd880324440c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 501e321c5ad0126a39ad9ebbd3a5d2d687f121b0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973248"
---
# <a name="tracking-data-decode-services-performance-counters"></a><span data-ttu-id="2ee2b-102">Tracking Data Decode Services のパフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="2ee2b-102">Tracking Data Decode Services Performance Counters</span></span>
<span data-ttu-id="2ee2b-103">パフォーマンス カウンターを使用すると、サービスによってサイトまたはシステムで実行されている作業の具体的な側面を監視できます。</span><span class="sxs-lookup"><span data-stu-id="2ee2b-103">Performance counters allow you to monitor specific aspects of work performed on the site or system by service.</span></span> <span data-ttu-id="2ee2b-104">パフォーマンス カウンターは、サーバー パフォーマンスに関する問題を特定してトラブルシューティングする際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2ee2b-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="2ee2b-105">次のパフォーマンス カウンターは各ホスト インスタンスにアクセスできる、 **BizTalk:TDDS**パフォーマンス オブジェクト カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="2ee2b-105">The following performance counters are accessible for each host instance under the **BizTalk:TDDS** performance object category:</span></span>  
  
|<span data-ttu-id="2ee2b-106">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="2ee2b-106">**Category**</span></span>|<span data-ttu-id="2ee2b-107">**カウンター**</span><span class="sxs-lookup"><span data-stu-id="2ee2b-107">**Counter**</span></span>|<span data-ttu-id="2ee2b-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="2ee2b-108">**Description**</span></span>|  
|------------------|-----------------|---------------------|  
|<span data-ttu-id="2ee2b-109">BizTalk:TDDS</span><span class="sxs-lookup"><span data-stu-id="2ee2b-109">BizTalk:TDDS</span></span>|<span data-ttu-id="2ee2b-110">Batches being processed</span><span class="sxs-lookup"><span data-stu-id="2ee2b-110">Batches being processed</span></span>|<span data-ttu-id="2ee2b-111">SQL トランザクション内部で現在処理中のバッチの数。</span><span class="sxs-lookup"><span data-stu-id="2ee2b-111">The number of batches that are being processed inside the current SQL transaction.</span></span>|  
||<span data-ttu-id="2ee2b-112">Batches committed</span><span class="sxs-lookup"><span data-stu-id="2ee2b-112">Batches committed</span></span>|<span data-ttu-id="2ee2b-113">出力先データベースにコミットされたバッチの数。</span><span class="sxs-lookup"><span data-stu-id="2ee2b-113">The number of batches committed to the destination database.</span></span>|  
||<span data-ttu-id="2ee2b-114">Events being processed</span><span class="sxs-lookup"><span data-stu-id="2ee2b-114">Events being processed</span></span>|<span data-ttu-id="2ee2b-115">SQL トランザクション内部で現在処理中のイベントの数。</span><span class="sxs-lookup"><span data-stu-id="2ee2b-115">The number of events that are being processed inside of the current SQL transaction.</span></span>|  
||<span data-ttu-id="2ee2b-116">Event Committed</span><span class="sxs-lookup"><span data-stu-id="2ee2b-116">Event Committed</span></span>|<span data-ttu-id="2ee2b-117">1 秒以内に出力先データベースにコミットされたイベントの数。</span><span class="sxs-lookup"><span data-stu-id="2ee2b-117">The number of events committed to the destination database within this second.</span></span>|  
||<span data-ttu-id="2ee2b-118">Records being processed</span><span class="sxs-lookup"><span data-stu-id="2ee2b-118">Records being processed</span></span>|<span data-ttu-id="2ee2b-119">SQL トランザクション内部で現在処理中のレコードの数。</span><span class="sxs-lookup"><span data-stu-id="2ee2b-119">The number of records that are being processed inside the current SQL transaction.</span></span>|  
||<span data-ttu-id="2ee2b-120">Records Committed</span><span class="sxs-lookup"><span data-stu-id="2ee2b-120">Records Committed</span></span>|<span data-ttu-id="2ee2b-121">1 秒以内に出力先データベースにコミットされたレコードの数。</span><span class="sxs-lookup"><span data-stu-id="2ee2b-121">The number of records committed to the destination database during this second.</span></span>|  
||<span data-ttu-id="2ee2b-122">Total Batches</span><span class="sxs-lookup"><span data-stu-id="2ee2b-122">Total Batches</span></span>|<span data-ttu-id="2ee2b-123">TDDS により処理されたバッチの合計数。</span><span class="sxs-lookup"><span data-stu-id="2ee2b-123">Total batches processed by TDDS.</span></span>|  
||<span data-ttu-id="2ee2b-124">Total Events</span><span class="sxs-lookup"><span data-stu-id="2ee2b-124">Total Events</span></span>|<span data-ttu-id="2ee2b-125">TDDS により処理されたイベントの合計数。</span><span class="sxs-lookup"><span data-stu-id="2ee2b-125">Total events processed by TDDS.</span></span>|  
||<span data-ttu-id="2ee2b-126">Total Failed Batches</span><span class="sxs-lookup"><span data-stu-id="2ee2b-126">Total Failed Batches</span></span>|<span data-ttu-id="2ee2b-127">TDDS による実行に失敗したバッチの総数。</span><span class="sxs-lookup"><span data-stu-id="2ee2b-127">Total batches failed to run by TDDS.</span></span>|  
||<span data-ttu-id="2ee2b-128">Total Failed Events</span><span class="sxs-lookup"><span data-stu-id="2ee2b-128">Total Failed Events</span></span>|<span data-ttu-id="2ee2b-129">TDDS による実行に失敗したイベントの総数。</span><span class="sxs-lookup"><span data-stu-id="2ee2b-129">Total events failed to run by TDDS.</span></span>|  
||<span data-ttu-id="2ee2b-130">Total Records</span><span class="sxs-lookup"><span data-stu-id="2ee2b-130">Total Records</span></span>|<span data-ttu-id="2ee2b-131">TDDS により処理されたレコードの合計数。</span><span class="sxs-lookup"><span data-stu-id="2ee2b-131">Total records processed by TDDS.</span></span>|  
  
## <a name="to-access-performance-counters"></a><span data-ttu-id="2ee2b-132">パフォーマンス カウンターにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="2ee2b-132">To access performance counters</span></span>  
 <span data-ttu-id="2ee2b-133">パフォーマンス カウンターにアクセスするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2ee2b-133">Use the following steps to access the performance counters.</span></span>  
  
#### <a name="if-you-are-using-windows-2008"></a><span data-ttu-id="2ee2b-134">Windows 2008 を使用している場合</span><span class="sxs-lookup"><span data-stu-id="2ee2b-134">If you are using Windows 2008</span></span>  
  
1.  <span data-ttu-id="2ee2b-135">をクリックして**開始**、 をポイント**管理ツール**、順にクリック**パフォーマンス モニター**です。</span><span class="sxs-lookup"><span data-stu-id="2ee2b-135">Click **Start**, point to **Administrative Tools**, and then click **Performance Monitor**.</span></span>  
  
2.  <span data-ttu-id="2ee2b-136">**パフォーマンス モニター** ] ダイアログ ボックスで、展開**の監視ツールを**[**パフォーマンス モニター**、順にクリック**追加**です。</span><span class="sxs-lookup"><span data-stu-id="2ee2b-136">In the **Performance Monitor** dialog box, expand **Monitoring Tools**, select **Performance Monitor**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="2ee2b-137">**カウンターの追加** ダイアログ ボックスから、**使用可能なカウンター**一覧で、展開、 **BizTalk:TDDS**パフォーマンス カウンター オブジェクトおよび監視するカウンターの選択</span><span class="sxs-lookup"><span data-stu-id="2ee2b-137">In the **Add Counters** dialog box, from the **Available Counters** list, expand the **BizTalk:TDDS** performance counter object and select the counters to be monitored</span></span>  
  
4.  <span data-ttu-id="2ee2b-138">**インスタンスの選択したオブジェクト**一覧をクリックして、選択したカウンターを監視する特定のインスタンスを選択**追加**です。</span><span class="sxs-lookup"><span data-stu-id="2ee2b-138">In the **Instances of Selected object** list, select the specific instances to be monitored for the selected counters and then click **Add**.</span></span>  <span data-ttu-id="2ee2b-139">使用可能なカウンターのすべてのインスタンスを選択するには、次のように選択します。 \<**すべてのインスタンス**\>です。</span><span class="sxs-lookup"><span data-stu-id="2ee2b-139">To select all available counter instances, select \<**All instances**\>.</span></span>  
  
5.  <span data-ttu-id="2ee2b-140">カウンターを追加すると、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="2ee2b-140">After adding the counters, click **OK**.</span></span>  
  
     <span data-ttu-id="2ee2b-141">選択したパフォーマンス カウンターが表示されます、**パフォーマンス モニター**画面。</span><span class="sxs-lookup"><span data-stu-id="2ee2b-141">The selected performance counters appear on the **Performance Monitor** screen.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ee2b-142">参照</span><span class="sxs-lookup"><span data-stu-id="2ee2b-142">See Also</span></span>  
 <span data-ttu-id="2ee2b-143">[パフォーマンスのヒントとテクニック](../core/performance-tips-and-tricks.md) </span><span class="sxs-lookup"><span data-stu-id="2ee2b-143">[Performance Tips and Tricks](../core/performance-tips-and-tricks.md) </span></span>  
 <span data-ttu-id="2ee2b-144">[維持可能な最大のエンジン スループットの測定](../core/measuring-maximum-sustainable-engine-throughput.md) </span><span class="sxs-lookup"><span data-stu-id="2ee2b-144">[Measuring Maximum Sustainable Engine Throughput](../core/measuring-maximum-sustainable-engine-throughput.md) </span></span>  
 <span data-ttu-id="2ee2b-145">[維持可能な最大の追跡スループットの測定](../core/measuring-maximum-sustainable-tracking-throughput.md) </span><span class="sxs-lookup"><span data-stu-id="2ee2b-145">[Measuring Maximum Sustainable Tracking Throughput](../core/measuring-maximum-sustainable-tracking-throughput.md) </span></span>  
 [<span data-ttu-id="2ee2b-146">ホスト制限によるリソース使用率の最適化</span><span class="sxs-lookup"><span data-stu-id="2ee2b-146">Optimizing Resource Usage Through Host Throttling</span></span>](../core/optimizing-resource-usage-through-host-throttling.md)