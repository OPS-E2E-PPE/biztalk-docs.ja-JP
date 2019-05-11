---
title: 'シナリオ 4: すべてのメッセージの追跡データベースのサイズ調整 |Microsoft Docs'
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
ms.openlocfilehash: 123423003377d199ebd2aea54674fe820d8debff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308566"
---
# <a name="scenario-4-sizing-the-tracking-database-for-all-messages"></a><span data-ttu-id="34f2d-102">シナリオ 4: すべてのメッセージの追跡データベースのサイズ調整</span><span class="sxs-lookup"><span data-stu-id="34f2d-102">Scenario 4: Sizing the Tracking Database for all Messages</span></span>
<span data-ttu-id="34f2d-103">Microsoft® BizTalk Server® 2004 の実装に存在するすべての 3 つのメッセージ シナリオがある場合は一緒に追加する必要があります。 すべてのシナリオの結果を、BizTalk 追跡データベースのサイズを決定します。</span><span class="sxs-lookup"><span data-stu-id="34f2d-103">If you had all three message scenarios present in a Microsoft® BizTalk Server® 2004 implementation, you would need to add together all of the scenario results to determine the size of the BizTalk Tracking database.</span></span>  
  
 <span data-ttu-id="34f2d-104">前述の例: から</span><span class="sxs-lookup"><span data-stu-id="34f2d-104">From the examples shown above:</span></span>  
  
|<span data-ttu-id="34f2d-105">シナリオ</span><span class="sxs-lookup"><span data-stu-id="34f2d-105">Scenario</span></span>|<span data-ttu-id="34f2d-106">1 GB 単位、年、必要な領域</span><span class="sxs-lookup"><span data-stu-id="34f2d-106">Space required, per year, in GB</span></span>|  
|--------------|-------------------------------------|  
|<span data-ttu-id="34f2d-107">単純なメッセージ</span><span class="sxs-lookup"><span data-stu-id="34f2d-107">Simple messages</span></span>|<span data-ttu-id="34f2d-108">4.78</span><span class="sxs-lookup"><span data-stu-id="34f2d-108">4.78</span></span>|  
|<span data-ttu-id="34f2d-109">オーケストレーション内のメッセージ</span><span class="sxs-lookup"><span data-stu-id="34f2d-109">Messages in orchestrations</span></span>|<span data-ttu-id="34f2d-110">7.18</span><span class="sxs-lookup"><span data-stu-id="34f2d-110">7.18</span></span>|  
|<span data-ttu-id="34f2d-111">配布リストに送信されるオーケストレーション内のメッセージ</span><span class="sxs-lookup"><span data-stu-id="34f2d-111">Messages in orchestrations sent out to distribution lists</span></span>|<span data-ttu-id="34f2d-112">10.8</span><span class="sxs-lookup"><span data-stu-id="34f2d-112">10.8</span></span>|  
|<span data-ttu-id="34f2d-113">**合計**</span><span class="sxs-lookup"><span data-stu-id="34f2d-113">**Total**</span></span>|<span data-ttu-id="34f2d-114">22.04</span><span class="sxs-lookup"><span data-stu-id="34f2d-114">22.04</span></span>|  
  
 <span data-ttu-id="34f2d-115">さらに、メッセージ本文のすべての 3 つのシナリオの追跡を有効にすることと、次の結果が得は。</span><span class="sxs-lookup"><span data-stu-id="34f2d-115">In addition, if we turn on message body tracking for all three scenarios, we would get the following results:</span></span>  
  
|<span data-ttu-id="34f2d-116">シナリオ</span><span class="sxs-lookup"><span data-stu-id="34f2d-116">Scenario</span></span>|<span data-ttu-id="34f2d-117">1 GB 単位、年、必要な領域</span><span class="sxs-lookup"><span data-stu-id="34f2d-117">Space required, per year, in GB</span></span>|  
|--------------|-------------------------------------|  
|<span data-ttu-id="34f2d-118">単純なメッセージ</span><span class="sxs-lookup"><span data-stu-id="34f2d-118">Simple messages</span></span>|<span data-ttu-id="34f2d-119">50.1</span><span class="sxs-lookup"><span data-stu-id="34f2d-119">50.1</span></span>|  
|<span data-ttu-id="34f2d-120">オーケストレーション内のメッセージ</span><span class="sxs-lookup"><span data-stu-id="34f2d-120">Messages in orchestrations</span></span>|<span data-ttu-id="34f2d-121">50.1</span><span class="sxs-lookup"><span data-stu-id="34f2d-121">50.1</span></span>|  
|<span data-ttu-id="34f2d-122">配布リストに送信されるオーケストレーション内のメッセージ</span><span class="sxs-lookup"><span data-stu-id="34f2d-122">Messages in orchestrations sent out to distribution lists</span></span>|<span data-ttu-id="34f2d-123">83.45</span><span class="sxs-lookup"><span data-stu-id="34f2d-123">83.45</span></span>|  
|<span data-ttu-id="34f2d-124">**合計**</span><span class="sxs-lookup"><span data-stu-id="34f2d-124">**Total**</span></span>|<span data-ttu-id="34f2d-125">183.65</span><span class="sxs-lookup"><span data-stu-id="34f2d-125">183.65</span></span>|  
  
 <span data-ttu-id="34f2d-126">これは、総計 205.69 GB 増加の前年比成長ごとに、BizTalk 追跡データベース。</span><span class="sxs-lookup"><span data-stu-id="34f2d-126">This would give you a grand total of 205.69 GB per year growth on the BizTalk Tracking database.</span></span> <span data-ttu-id="34f2d-127">この図では、コンティンジェンシーは含まれません。</span><span class="sxs-lookup"><span data-stu-id="34f2d-127">This figure does not include any contingency.</span></span> <span data-ttu-id="34f2d-128">お勧めこの合計に予備の 10% を追加する場合、BizTalk 追跡データベースが 1 年あたり 227.94 GB の成長に計画してください。</span><span class="sxs-lookup"><span data-stu-id="34f2d-128">If you decided to add a contingency of 10 percent to this total, as is recommended, then you should plan on the BizTalk Tracking database growing 227.94 GB per year.</span></span> <span data-ttu-id="34f2d-129">さらに、SQL のインデックスやストレージなどが原因のオーバーヘッドを検討してください。可能であれば、テストでテスト シナリオを実行した後、増加率基にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="34f2d-129">On top of this, you should consider the overhead due to SQL indices, storage, etc. You should base your multiplying factor after running the test scenarios in test if possible.</span></span>  
  
## <a name="other-factors-affecting-biztalk-tracking-database-size"></a><span data-ttu-id="34f2d-130">その他の要因に影響を与える BizTalk 追跡データベースのサイズ</span><span class="sxs-lookup"><span data-stu-id="34f2d-130">Other factors affecting BizTalk Tracking database size</span></span>  
 <span data-ttu-id="34f2d-131">BizTalk 追跡データベースのサイズに影響を与えることも、オーケストレーション内で使用する図形などの他の項目があります。</span><span class="sxs-lookup"><span data-stu-id="34f2d-131">There are other items, such as the shapes used within an orchestration that also affect the size of the BizTalk Tracking database.</span></span>  
  
 <span data-ttu-id="34f2d-132">オーケストレーション デバッガーのオプションがオンの場合、既定では、オーケストレーション内の各図形の状態保存されている BizTalk 追跡データベースにします。</span><span class="sxs-lookup"><span data-stu-id="34f2d-132">If the orchestration debugger option is turned on, which it is by default, the status of each shape in the orchestration is saved to the BizTalk Tracking database.</span></span>  
  
 <span data-ttu-id="34f2d-133">図形の状態を追跡するために必要なサイズを決定する数式です。</span><span class="sxs-lookup"><span data-stu-id="34f2d-133">The formula to determine the size needed to track shape status is:</span></span>  
  
```  
[(# of object shapes ] * 76 bytes  
```  
  
 <span data-ttu-id="34f2d-134">たとえば、次の図の場合は、BizTalk 追跡サイズを決定するは次の数式を使用します。</span><span class="sxs-lookup"><span data-stu-id="34f2d-134">For example, in the following figure, you would use the following formula to determine the BizTalk Tracking size:</span></span>  
  
```  
((4) * 76 bytes = 304 bytes  
```  
  
 <span data-ttu-id="34f2d-135">![オーケストレーションの例](../core/media/sample-orchestration.gif "Sample_orchestration")</span><span class="sxs-lookup"><span data-stu-id="34f2d-135">![Orchestration Example](../core/media/sample-orchestration.gif "Sample_orchestration")</span></span>  
  
 <span data-ttu-id="34f2d-136">このオーケストレーションで 350万メッセージを処理すると、想定した場合、このオーケストレーションを追跡するために必要な追加領域は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="34f2d-136">If we assume that this orchestration processes 3.5 million messages, the additional space needed to track this orchestration would be:</span></span>  
  
```  
304 bytes * 3,500,000/1024/1024 = 1015 MB ~ 0.99 GB.  
```  
  
 <span data-ttu-id="34f2d-137">各オーケストレーションを BizTalk 追跡データベースのおおよそのサイズを取得する"on"に設定するオーケストレーション デバッガーを持つアカウントが必要になります。</span><span class="sxs-lookup"><span data-stu-id="34f2d-137">You will need to account for each orchestration that has the orchestration debugger set to "on" to get an approximate size for the BizTalk Tracking database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34f2d-138">参照</span><span class="sxs-lookup"><span data-stu-id="34f2d-138">See Also</span></span>  
 <span data-ttu-id="34f2d-139">[追跡データベースのサイズにメッセージ変数を使用します。](../core/using-message-variables-to-size-the-tracking-database.md) </span><span class="sxs-lookup"><span data-stu-id="34f2d-139">[Using Message Variables to Size the Tracking Database](../core/using-message-variables-to-size-the-tracking-database.md) </span></span>  
 <span data-ttu-id="34f2d-140">[メッセージ本文を追跡する追跡データベースのサイズ調整](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span><span class="sxs-lookup"><span data-stu-id="34f2d-140">[Sizing the Tracking Database to Track Message Bodies](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span></span>  
 <span data-ttu-id="34f2d-141">[シナリオ 1: 単純な BizTalk メッセージの追跡データベースのサイズ調整](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span><span class="sxs-lookup"><span data-stu-id="34f2d-141">[Scenario 1: Sizing the Tracking Database  for Simple BizTalk Messages](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span></span>  
 <span data-ttu-id="34f2d-142">[シナリオ 2: オーケストレーション内のメッセージの追跡データベースのサイズ調整](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="34f2d-142">[Scenario 2: Sizing the Tracking Database  for Messages in Orchestrations](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span></span>  
 [<span data-ttu-id="34f2d-143">シナリオ 3:配布リストに送信されるメッセージの追跡データベースのサイズ調整</span><span class="sxs-lookup"><span data-stu-id="34f2d-143">Scenario 3: Sizing the Tracking Database  for Messages Sent Out to Distribution Lists</span></span>](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)