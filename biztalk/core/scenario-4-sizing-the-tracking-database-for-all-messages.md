---
title: 'シナリオ 4: すべてのメッセージの追跡データベースのサイズ変更 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking database, database size
ms.assetid: db1126c7-0b86-4635-bfdc-3b69a82cc64b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 327953843b2d9b70f500796f43302320924a330c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269842"
---
# <a name="scenario-4-sizing-the-tracking-database-for-all-messages"></a><span data-ttu-id="e4811-102">シナリオ 4: すべてのメッセージの追跡データベースのサイズ変更</span><span class="sxs-lookup"><span data-stu-id="e4811-102">Scenario 4: Sizing the Tracking Database for all Messages</span></span>
<span data-ttu-id="e4811-103">Microsoft® BizTalk Server® 2004 の実装であるすべての 3 つのメッセージ シナリオがある場合は一緒に追加する必要があります。 すべての BizTalk 追跡データベースのサイズを決定するシナリオの結果。</span><span class="sxs-lookup"><span data-stu-id="e4811-103">If you had all three message scenarios present in a Microsoft® BizTalk Server® 2004 implementation, you would need to add together all of the scenario results to determine the size of the BizTalk Tracking database.</span></span>  
  
 <span data-ttu-id="e4811-104">上記の例について検討します。</span><span class="sxs-lookup"><span data-stu-id="e4811-104">From the examples shown above:</span></span>  
  
|<span data-ttu-id="e4811-105">Scenario</span><span class="sxs-lookup"><span data-stu-id="e4811-105">Scenario</span></span>|<span data-ttu-id="e4811-106">1 年ごとに必要な領域 (単位は GB)</span><span class="sxs-lookup"><span data-stu-id="e4811-106">Space required, per year, in GB</span></span>|  
|--------------|-------------------------------------|  
|<span data-ttu-id="e4811-107">簡易メッセージ</span><span class="sxs-lookup"><span data-stu-id="e4811-107">Simple messages</span></span>|<span data-ttu-id="e4811-108">4.78</span><span class="sxs-lookup"><span data-stu-id="e4811-108">4.78</span></span>|  
|<span data-ttu-id="e4811-109">オーケストレーション内のメッセージ</span><span class="sxs-lookup"><span data-stu-id="e4811-109">Messages in orchestrations</span></span>|<span data-ttu-id="e4811-110">7.18</span><span class="sxs-lookup"><span data-stu-id="e4811-110">7.18</span></span>|  
|<span data-ttu-id="e4811-111">同報リストに送信されるオーケストレーション内のメッセージ</span><span class="sxs-lookup"><span data-stu-id="e4811-111">Messages in orchestrations sent out to distribution lists</span></span>|<span data-ttu-id="e4811-112">10.8</span><span class="sxs-lookup"><span data-stu-id="e4811-112">10.8</span></span>|  
|<span data-ttu-id="e4811-113">**合計**</span><span class="sxs-lookup"><span data-stu-id="e4811-113">**Total**</span></span>|<span data-ttu-id="e4811-114">22.04</span><span class="sxs-lookup"><span data-stu-id="e4811-114">22.04</span></span>|  
  
 <span data-ttu-id="e4811-115">また、3 つのシナリオすべてについてメッセージ本文の追跡を有効にしている場合、結果は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="e4811-115">In addition, if we turn on message body tracking for all three scenarios, we would get the following results:</span></span>  
  
|<span data-ttu-id="e4811-116">Scenario</span><span class="sxs-lookup"><span data-stu-id="e4811-116">Scenario</span></span>|<span data-ttu-id="e4811-117">1 年ごとに必要な領域 (単位は GB)</span><span class="sxs-lookup"><span data-stu-id="e4811-117">Space required, per year, in GB</span></span>|  
|--------------|-------------------------------------|  
|<span data-ttu-id="e4811-118">簡易メッセージ</span><span class="sxs-lookup"><span data-stu-id="e4811-118">Simple messages</span></span>|<span data-ttu-id="e4811-119">50.1</span><span class="sxs-lookup"><span data-stu-id="e4811-119">50.1</span></span>|  
|<span data-ttu-id="e4811-120">オーケストレーション内のメッセージ</span><span class="sxs-lookup"><span data-stu-id="e4811-120">Messages in orchestrations</span></span>|<span data-ttu-id="e4811-121">50.1</span><span class="sxs-lookup"><span data-stu-id="e4811-121">50.1</span></span>|  
|<span data-ttu-id="e4811-122">同報リストに送信されるオーケストレーション内のメッセージ</span><span class="sxs-lookup"><span data-stu-id="e4811-122">Messages in orchestrations sent out to distribution lists</span></span>|<span data-ttu-id="e4811-123">83.45</span><span class="sxs-lookup"><span data-stu-id="e4811-123">83.45</span></span>|  
|<span data-ttu-id="e4811-124">**合計**</span><span class="sxs-lookup"><span data-stu-id="e4811-124">**Total**</span></span>|<span data-ttu-id="e4811-125">183.65</span><span class="sxs-lookup"><span data-stu-id="e4811-125">183.65</span></span>|  
  
 <span data-ttu-id="e4811-126">この結果、BizTalk 追跡データベースのサイズは 1 年ごとに総計 205.69 GB 増加することになります。</span><span class="sxs-lookup"><span data-stu-id="e4811-126">This would give you a grand total of 205.69 GB per year growth on the BizTalk Tracking database.</span></span> <span data-ttu-id="e4811-127">この値に予備の領域は含まれません。</span><span class="sxs-lookup"><span data-stu-id="e4811-127">This figure does not include any contingency.</span></span> <span data-ttu-id="e4811-128">推奨では、総計に 10% の予備の領域を加算する場合、BizTalk 追跡データベースのサイズとして、1 年ごとに 227.94 GB の増加を見積もる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4811-128">If you decided to add a contingency of 10 percent to this total, as is recommended, then you should plan on the BizTalk Tracking database growing 227.94 GB per year.</span></span> <span data-ttu-id="e4811-129">これには、上には、SQL のインデックス、ストレージなどのためのオーバーヘッドを検討してください。可能であればテストでテストのシナリオを実行した後、乗算した要素を基準とする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4811-129">On top of this, you should consider the overhead due to SQL indices, storage, etc. You should base your multiplying factor after running the test scenarios in test if possible.</span></span>  
  
## <a name="other-factors-affecting-biztalk-tracking-database-size"></a><span data-ttu-id="e4811-130">BizTalk 追跡データベースのサイズに影響を及ぼす他の要因</span><span class="sxs-lookup"><span data-stu-id="e4811-130">Other factors affecting BizTalk Tracking database size</span></span>  
 <span data-ttu-id="e4811-131">オーケストレーション内で使用する図形など他の項目も、BizTalk 追跡データベースのサイズに影響を及ぼします。</span><span class="sxs-lookup"><span data-stu-id="e4811-131">There are other items, such as the shapes used within an orchestration that also affect the size of the BizTalk Tracking database.</span></span>  
  
 <span data-ttu-id="e4811-132">オーケストレーション デバッガーのオプションがオン (既定の設定) の場合、オーケストレーションの各図形の状態が BizTalk 追跡データベースに保存されます。</span><span class="sxs-lookup"><span data-stu-id="e4811-132">If the orchestration debugger option is turned on, which it is by default, the status of each shape in the orchestration is saved to the BizTalk Tracking database.</span></span>  
  
 <span data-ttu-id="e4811-133">図形の状態を追跡するために必要なサイズを決定する式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e4811-133">The formula to determine the size needed to track shape status is:</span></span>  
  
```  
[(# of object shapes ] * 76 bytes  
```  
  
 <span data-ttu-id="e4811-134">たとえば、下の図の場合、次の計算式を使用して BizTalk 追跡サイズを決定します。</span><span class="sxs-lookup"><span data-stu-id="e4811-134">For example, in the following figure, you would use the following formula to determine the BizTalk Tracking size:</span></span>  
  
```  
((4) * 76 bytes = 304 bytes  
```  
  
 <span data-ttu-id="e4811-135">![オーケストレーションの例](../core/media/sample-orchestration.gif "Sample_orchestration")</span><span class="sxs-lookup"><span data-stu-id="e4811-135">![Orchestration Example](../core/media/sample-orchestration.gif "Sample_orchestration")</span></span>  
  
 <span data-ttu-id="e4811-136">このオーケストレーションで 350 万件のメッセージを処理すると仮定した場合、このオーケストレーションを追跡するために必要な追加領域は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="e4811-136">If we assume that this orchestration processes 3.5 million messages, the additional space needed to track this orchestration would be:</span></span>  
  
```  
304 bytes * 3,500,000/1024/1024 = 1015 MB ~ 0.99 GB.  
```  
  
 <span data-ttu-id="e4811-137">BizTalk 追跡データベースのサイズを推定するには、各オーケストレーションについて、オーケストレーション デバッガーのオプションが "オン" に設定されている場合を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4811-137">You will need to account for each orchestration that has the orchestration debugger set to "on" to get an approximate size for the BizTalk Tracking database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4811-138">参照</span><span class="sxs-lookup"><span data-stu-id="e4811-138">See Also</span></span>  
 <span data-ttu-id="e4811-139">[追跡データベースのサイズをメッセージ変数を使用](../core/using-message-variables-to-size-the-tracking-database.md) </span><span class="sxs-lookup"><span data-stu-id="e4811-139">[Using Message Variables to Size the Tracking Database](../core/using-message-variables-to-size-the-tracking-database.md) </span></span>  
 <span data-ttu-id="e4811-140">[メッセージ本文を追跡する追跡データベースのサイズ変更](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span><span class="sxs-lookup"><span data-stu-id="e4811-140">[Sizing the Tracking Database to Track Message Bodies](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span></span>  
 <span data-ttu-id="e4811-141">[シナリオ 1: 単純な BizTalk メッセージの追跡データベースのサイズ変更](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span><span class="sxs-lookup"><span data-stu-id="e4811-141">[Scenario 1: Sizing the Tracking Database  for Simple BizTalk Messages](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span></span>  
 <span data-ttu-id="e4811-142">[シナリオ 2: オーケストレーションでメッセージの追跡データベースのサイズ変更](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="e4811-142">[Scenario 2: Sizing the Tracking Database  for Messages in Orchestrations](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span></span>  
 [<span data-ttu-id="e4811-143">シナリオ 3: 同報リストに送信されるメッセージの追跡データベースのサイズ変更</span><span class="sxs-lookup"><span data-stu-id="e4811-143">Scenario 3: Sizing the Tracking Database  for Messages Sent Out to Distribution Lists</span></span>](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)