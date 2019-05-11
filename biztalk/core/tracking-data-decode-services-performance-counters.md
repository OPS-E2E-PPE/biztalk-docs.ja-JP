---
title: Tracking Data Decode Services のパフォーマンス カウンター |Microsoft Docs
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
ms.openlocfilehash: 944baf51a1ca10edc157f2062a6883d77ddffeb0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65313897"
---
# <a name="tracking-data-decode-services-performance-counters"></a><span data-ttu-id="16f97-102">Tracking Data Decode Services のパフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="16f97-102">Tracking Data Decode Services Performance Counters</span></span>
<span data-ttu-id="16f97-103">パフォーマンス カウンターを使用して、サービスによってサイトまたはシステムで実行される作業の具体的な側面を監視できます。</span><span class="sxs-lookup"><span data-stu-id="16f97-103">Performance counters allow you to monitor specific aspects of work performed on the site or system by service.</span></span> <span data-ttu-id="16f97-104">パフォーマンス カウンターは、サーバー パフォーマンスに関する問題を特定してトラブルシューティングする際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="16f97-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="16f97-105">次のパフォーマンス カウンターは各ホスト インスタンスにアクセスできますが、 **BizTalk:TDDS**パフォーマンス オブジェクト カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="16f97-105">The following performance counters are accessible for each host instance under the **BizTalk:TDDS** performance object category:</span></span>  
  
|<span data-ttu-id="16f97-106">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="16f97-106">**Category**</span></span>|<span data-ttu-id="16f97-107">**カウンター**</span><span class="sxs-lookup"><span data-stu-id="16f97-107">**Counter**</span></span>|<span data-ttu-id="16f97-108">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="16f97-108">**Description**</span></span>|  
|------------------|-----------------|---------------------|  
|<span data-ttu-id="16f97-109">Biztalk: Tdds</span><span class="sxs-lookup"><span data-stu-id="16f97-109">BizTalk:TDDS</span></span>|<span data-ttu-id="16f97-110">Batches being processed</span><span class="sxs-lookup"><span data-stu-id="16f97-110">Batches being processed</span></span>|<span data-ttu-id="16f97-111">現在の SQL トランザクション内部で処理されているバッチの数。</span><span class="sxs-lookup"><span data-stu-id="16f97-111">The number of batches that are being processed inside the current SQL transaction.</span></span>|  
||<span data-ttu-id="16f97-112">コミットされたバッチ</span><span class="sxs-lookup"><span data-stu-id="16f97-112">Batches committed</span></span>|<span data-ttu-id="16f97-113">転送先データベースにコミットされたバッチの数。</span><span class="sxs-lookup"><span data-stu-id="16f97-113">The number of batches committed to the destination database.</span></span>|  
||<span data-ttu-id="16f97-114">Events being processed</span><span class="sxs-lookup"><span data-stu-id="16f97-114">Events being processed</span></span>|<span data-ttu-id="16f97-115">現在の SQL トランザクション内部で処理されているイベントの数。</span><span class="sxs-lookup"><span data-stu-id="16f97-115">The number of events that are being processed inside of the current SQL transaction.</span></span>|  
||<span data-ttu-id="16f97-116">コミットされたイベント</span><span class="sxs-lookup"><span data-stu-id="16f97-116">Event Committed</span></span>|<span data-ttu-id="16f97-117">1 秒以内に、転送先データベースにコミットされたイベントの数。</span><span class="sxs-lookup"><span data-stu-id="16f97-117">The number of events committed to the destination database within this second.</span></span>|  
||<span data-ttu-id="16f97-118">レコードの処理中</span><span class="sxs-lookup"><span data-stu-id="16f97-118">Records being processed</span></span>|<span data-ttu-id="16f97-119">現在の SQL トランザクション内部で処理されているレコードの数。</span><span class="sxs-lookup"><span data-stu-id="16f97-119">The number of records that are being processed inside the current SQL transaction.</span></span>|  
||<span data-ttu-id="16f97-120">Records Committed</span><span class="sxs-lookup"><span data-stu-id="16f97-120">Records Committed</span></span>|<span data-ttu-id="16f97-121">この 1 秒間に転送先データベースにコミットされたレコードの数。</span><span class="sxs-lookup"><span data-stu-id="16f97-121">The number of records committed to the destination database during this second.</span></span>|  
||<span data-ttu-id="16f97-122">Total Batches</span><span class="sxs-lookup"><span data-stu-id="16f97-122">Total Batches</span></span>|<span data-ttu-id="16f97-123">TDDS により処理されたバッチの総数。</span><span class="sxs-lookup"><span data-stu-id="16f97-123">Total batches processed by TDDS.</span></span>|  
||<span data-ttu-id="16f97-124">Total Events</span><span class="sxs-lookup"><span data-stu-id="16f97-124">Total Events</span></span>|<span data-ttu-id="16f97-125">TDDS により処理されたイベントの総数。</span><span class="sxs-lookup"><span data-stu-id="16f97-125">Total events processed by TDDS.</span></span>|  
||<span data-ttu-id="16f97-126">Total Failed Batches</span><span class="sxs-lookup"><span data-stu-id="16f97-126">Total Failed Batches</span></span>|<span data-ttu-id="16f97-127">TDDS による実行に失敗したバッチの合計。</span><span class="sxs-lookup"><span data-stu-id="16f97-127">Total batches failed to run by TDDS.</span></span>|  
||<span data-ttu-id="16f97-128">Total Failed Events</span><span class="sxs-lookup"><span data-stu-id="16f97-128">Total Failed Events</span></span>|<span data-ttu-id="16f97-129">TDDS による実行に失敗したイベントの合計。</span><span class="sxs-lookup"><span data-stu-id="16f97-129">Total events failed to run by TDDS.</span></span>|  
||<span data-ttu-id="16f97-130">Total Records</span><span class="sxs-lookup"><span data-stu-id="16f97-130">Total Records</span></span>|<span data-ttu-id="16f97-131">TDDS により処理されたレコードの合計数します。</span><span class="sxs-lookup"><span data-stu-id="16f97-131">Total records processed by TDDS.</span></span>|  
  
## <a name="to-access-performance-counters"></a><span data-ttu-id="16f97-132">パフォーマンス カウンターにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="16f97-132">To access performance counters</span></span>  
 <span data-ttu-id="16f97-133">パフォーマンス カウンターにアクセスするのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="16f97-133">Use the following steps to access the performance counters.</span></span>  
  
#### <a name="if-you-are-using-windows-2008"></a><span data-ttu-id="16f97-134">Windows 2008 を使用している場合</span><span class="sxs-lookup"><span data-stu-id="16f97-134">If you are using Windows 2008</span></span>  
  
1.  <span data-ttu-id="16f97-135">クリックして**開始**、 をポイント**管理ツール**、順にクリックします**パフォーマンス モニター**します。</span><span class="sxs-lookup"><span data-stu-id="16f97-135">Click **Start**, point to **Administrative Tools**, and then click **Performance Monitor**.</span></span>  
  
2.  <span data-ttu-id="16f97-136">**パフォーマンス モニター**  ダイアログ ボックスで、展開**監視ツール**を選択します**パフォーマンス モニター**、 をクリックし、**追加**。</span><span class="sxs-lookup"><span data-stu-id="16f97-136">In the **Performance Monitor** dialog box, expand **Monitoring Tools**, select **Performance Monitor**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="16f97-137">**カウンターの追加** ダイアログ ボックスから、**使用可能なカウンター**一覧で、展開、 **BizTalk:TDDS**パフォーマンス カウンター オブジェクトと監視するカウンターを選択します。</span><span class="sxs-lookup"><span data-stu-id="16f97-137">In the **Add Counters** dialog box, from the **Available Counters** list, expand the **BizTalk:TDDS** performance counter object and select the counters to be monitored</span></span>  
  
4.  <span data-ttu-id="16f97-138">**インスタンスの選択したオブジェクト**一覧をクリックして、選択したカウンターを監視する特定のインスタンスを選択**追加**します。</span><span class="sxs-lookup"><span data-stu-id="16f97-138">In the **Instances of Selected object** list, select the specific instances to be monitored for the selected counters and then click **Add**.</span></span>  <span data-ttu-id="16f97-139">使用可能なカウンターのインスタンスすべてを選択する\<**すべてのインスタンス**\>します。</span><span class="sxs-lookup"><span data-stu-id="16f97-139">To select all available counter instances, select \<**All instances**\>.</span></span>  
  
5.  <span data-ttu-id="16f97-140">カウンターを追加すると、次のようにクリックします。 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="16f97-140">After adding the counters, click **OK**.</span></span>  
  
     <span data-ttu-id="16f97-141">選択したパフォーマンス カウンターが表示される、**パフォーマンス モニター**画面。</span><span class="sxs-lookup"><span data-stu-id="16f97-141">The selected performance counters appear on the **Performance Monitor** screen.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16f97-142">参照</span><span class="sxs-lookup"><span data-stu-id="16f97-142">See Also</span></span>  
 <span data-ttu-id="16f97-143">[パフォーマンスのヒントとテクニック](../core/performance-tips-and-tricks.md) </span><span class="sxs-lookup"><span data-stu-id="16f97-143">[Performance Tips and Tricks](../core/performance-tips-and-tricks.md) </span></span>  
 <span data-ttu-id="16f97-144">[維持可能な最大のエンジン スループットの測定](../core/measuring-maximum-sustainable-engine-throughput.md) </span><span class="sxs-lookup"><span data-stu-id="16f97-144">[Measuring Maximum Sustainable Engine Throughput](../core/measuring-maximum-sustainable-engine-throughput.md) </span></span>  
 <span data-ttu-id="16f97-145">[維持可能な最大の追跡スループットの測定](../core/measuring-maximum-sustainable-tracking-throughput.md) </span><span class="sxs-lookup"><span data-stu-id="16f97-145">[Measuring Maximum Sustainable Tracking Throughput](../core/measuring-maximum-sustainable-tracking-throughput.md) </span></span>  
 [<span data-ttu-id="16f97-146">ホスト制限によるリソース使用率の最適化</span><span class="sxs-lookup"><span data-stu-id="16f97-146">Optimizing Resource Usage Through Host Throttling</span></span>](../core/optimizing-resource-usage-through-host-throttling.md)