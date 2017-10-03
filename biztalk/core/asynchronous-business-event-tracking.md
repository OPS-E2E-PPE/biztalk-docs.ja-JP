---
title: "非同期ビジネス イベントの追跡 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance, BAM
- events, tracking [BAM]
- BAM, event tracking
- BAM, performance
ms.assetid: 6d51fadf-b329-4536-9618-d982d9c17882
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7191d9b0be94b4b089a91e78dd526867171c68a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="asynchronous-business-event-tracking"></a><span data-ttu-id="d990c-102">非同期ビジネス イベントの追跡</span><span class="sxs-lookup"><span data-stu-id="d990c-102">Asynchronous Business Event Tracking</span></span>
<span data-ttu-id="d990c-103">非同期 (を使用して`BufferedEventStream`)-このモデルには、大幅なパフォーマンス向上が用意されています。</span><span class="sxs-lookup"><span data-stu-id="d990c-103">Asynchronous (using `BufferedEventStream`) - This model offers significant performance improvements.</span></span> <span data-ttu-id="d990c-104">このモデルでは、同期モデルに似た API を使用します (使用するコンストラクターだけが異なります)。</span><span class="sxs-lookup"><span data-stu-id="d990c-104">This uses a similar API to the synchronous model, using only a different constructor.</span></span> <span data-ttu-id="d990c-105">BufferedEventStream は、データをプライマリ インポート データベースにプッシュするのではなく、イベント データをバイナリ形式でメモリに蓄積してから、そのデータを 1 つのテーブル レコードとして中間処理用のデータベース (メッセージ ボックス データベース) に挿入します。</span><span class="sxs-lookup"><span data-stu-id="d990c-105">Instead of pushing the data into the primary import database, BufferedEventStream accumulates the event data in memory in binary form, and then inserts it as a single table record into an interim database (MessageBox).</span></span> <span data-ttu-id="d990c-106">イベント バス サービスは、BizTalk によってメッセージ ボックス データベースのキューに格納されたデータを読み取り、そのデータをプライマリ インポート データベースにインポートします。</span><span class="sxs-lookup"><span data-stu-id="d990c-106">The Event Bus service reads the data queued in the MessageBox database by BizTalk and imports it into the primary import database.</span></span>  
  
 <span data-ttu-id="d990c-107">非同期操作用に BAM を構成するには、イベント バス サービスと呼び出し元のアプリケーション (たとえば、オーケストレーション ホスト) を異なるコンピューター上で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d990c-107">To configure BAM for asynchronous operation, the Event Bus Service and the calling application (e.g. Orchestration Host) should run on different computers.</span></span> <span data-ttu-id="d990c-108">これにより、呼び出し元のアプリケーションは、別のコンピューター上の CPU を使用して処理されるイベント データをすぐに削除できます。</span><span class="sxs-lookup"><span data-stu-id="d990c-108">This allows the calling application to get rid of the event data immediately to be processed using the CPU on a different computer.</span></span>  
  
 <span data-ttu-id="d990c-109">この BAM トポロジには、トランザクションとしての一貫性もあります。</span><span class="sxs-lookup"><span data-stu-id="d990c-109">This BAM topology is also transaction-consistent.</span></span> <span data-ttu-id="d990c-110">コミットされたデータをメッセージ ボックス データベースから読み取るのはイベント バス サービスだけなので、呼び出し元のアプリケーションにロールバックされたトランザクションの BAM データを取得することはありません。</span><span class="sxs-lookup"><span data-stu-id="d990c-110">You will never get BAM data for transactions that rolled back in the calling application, because the Event Bus Service only reads the committed data from the MessageBox database.</span></span> <span data-ttu-id="d990c-111">コミットされたトランザクションの BAM データは、短い待機時間でクエリおよび集計に表示されます。</span><span class="sxs-lookup"><span data-stu-id="d990c-111">The BAM data for the transactions that were committed will show up for query and aggregation with small latency.</span></span>  
  
 <span data-ttu-id="d990c-112">エラーが発生した場合、イベント バス サービスでは、数回の再試行、タイムアウトの使用、復旧ロジックのクラッシュなどが生じます。</span><span class="sxs-lookup"><span data-stu-id="d990c-112">If errors occur, the Event Bus Service will retry a few times, use timeouts, crash recovery logic, and so on.</span></span> <span data-ttu-id="d990c-113">ただし、データの形式が無効な場合、そのデータは最終的には特殊なテーブルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="d990c-113">If however the data is in an invalid format, it ends up in special tables.</span></span> <span data-ttu-id="d990c-114">この状況を示すために、イベント ログにイベントが記録されます。</span><span class="sxs-lookup"><span data-stu-id="d990c-114">An event occurs in the event log to indicate this condition.</span></span> <span data-ttu-id="d990c-115">このように追加のエラーが発生すると、システムを管理するのが難しくなります。</span><span class="sxs-lookup"><span data-stu-id="d990c-115">This additional failure point increases the difficulty of managing the system.</span></span>  
  
 <span data-ttu-id="d990c-116">通常、コードから非同期的な方法を使用することは、DirectEventStream を BufferedEventStream と置き換え、BAM プライマリ インポートではなくメッセージ ボックスに対してコンストラクターで接続文字列を渡すことと同様に単純な操作です。</span><span class="sxs-lookup"><span data-stu-id="d990c-116">Using the asynchronous approach from code is usually as simple as replacing the DirectEventStream with BufferedEventStream, and passing the connection string to the Message Box in the constructor, instead of the one for BAM Primary Import.</span></span>  
  
 <span data-ttu-id="d990c-117">コードでの非同期ビジネス イベントの追跡に関しては、次のガイドラインに従ってください。</span><span class="sxs-lookup"><span data-stu-id="d990c-117">Use the following guidelines regarding asynchronous business event tracking in your code:</span></span>  
  
-   <span data-ttu-id="d990c-118">アクティビティが複数のアプリケーションにまたがっていて、BAM に非同期にデータを送信するときは、すべてのコンポーネントに ActivityID を伝達する場合でも、必ず Continuation を使用します。</span><span class="sxs-lookup"><span data-stu-id="d990c-118">Always use continuation when the Activity spans multiple applications and you send the data asynchronously to BAM, even if you propagate the ActivityID to all components.</span></span> <span data-ttu-id="d990c-119">この場合、アプリケーションごとに一意の文字列 (アプリケーション名など) をプレフィックスとして付けることで、ActivityID を使い分けます。</span><span class="sxs-lookup"><span data-stu-id="d990c-119">In this case, use a different ActivityID in each application by prefixing it with a unique string (e.g. Application Name).</span></span> <span data-ttu-id="d990c-120">複数のアプリケーションから BAM にランダムにデータが到着することがあり、BAM では、そのような場合にも正しいクエリと集計の結果を得るために、適切な順序になっていないイベントを管理する必要があります。このため、ID の使い分けが必要になります。</span><span class="sxs-lookup"><span data-stu-id="d990c-120">This is necessary because the data from different applications might arrive to BAM in random order, and BAM has to manage the out-of-order events to ensure correct Query and Aggregation results.</span></span>  
  
-   <span data-ttu-id="d990c-121">イベントを監視するための一般的な方法 (たとえば、COM+ 疎結合イベントや WMI イベント) は、イベント データがトランザクションに依存していないため、BAM には適用できません。</span><span class="sxs-lookup"><span data-stu-id="d990c-121">The usual methods of event monitoring (e.g. COM+ Loosely Coupled Events or WMI Events) are not applicable for BAM because the event data is independent of the transaction.</span></span> <span data-ttu-id="d990c-122">たとえば、受け取ったのは 1,000 ドルの注文書 1 件だけなのに、その注文書をデータベースに保存する処理に 10 回失敗したために、注文書を 10 件 (合計金額 10,000 ドル) を受け取ったように見える場合があります。</span><span class="sxs-lookup"><span data-stu-id="d990c-122">For example, it may look like you received 10 purchase orders for a total of $10,000 while there was only one incoming purchase order for $1000, but the attempt to save it to the database failed 10 times.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d990c-123">参照</span><span class="sxs-lookup"><span data-stu-id="d990c-123">See Also</span></span>  

 [<span data-ttu-id="d990c-124">同期ビジネス イベントの追跡</span><span class="sxs-lookup"><span data-stu-id="d990c-124">Synchronous Business Event Tracking</span></span>](../core/synchronous-business-event-tracking.md)