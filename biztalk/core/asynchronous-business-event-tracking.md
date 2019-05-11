---
title: 非同期ビジネス イベントの追跡 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance, BAM
- events, tracking [BAM]
- BAM, event tracking
- BAM, performance
ms.assetid: 6d51fadf-b329-4536-9618-d982d9c17882
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: daff76641e9c70cc2860aa1571b86e74d664f66e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358801"
---
# <a name="asynchronous-business-event-tracking"></a><span data-ttu-id="3b9e0-102">非同期ビジネス イベントの追跡</span><span class="sxs-lookup"><span data-stu-id="3b9e0-102">Asynchronous Business Event Tracking</span></span>
<span data-ttu-id="3b9e0-103">非同期 (を使用して`BufferedEventStream`)-このモデルは、大幅なパフォーマンス向上を提供しています。</span><span class="sxs-lookup"><span data-stu-id="3b9e0-103">Asynchronous (using `BufferedEventStream`) - This model offers significant performance improvements.</span></span> <span data-ttu-id="3b9e0-104">これは、別のコンス トラクターのみを使用して、同期モデルに同様の API を使用します。</span><span class="sxs-lookup"><span data-stu-id="3b9e0-104">This uses a similar API to the synchronous model, using only a different constructor.</span></span> <span data-ttu-id="3b9e0-105">プライマリ インポート データベースにデータをプッシュするのではなく、BufferedEventStream はイベント データをバイナリ形式でメモリに蓄積され、暫定的なデータベース (MessageBox) に 1 つのテーブルのレコードとして挿入されます。</span><span class="sxs-lookup"><span data-stu-id="3b9e0-105">Instead of pushing the data into the primary import database, BufferedEventStream accumulates the event data in memory in binary form, and then inserts it as a single table record into an interim database (MessageBox).</span></span> <span data-ttu-id="3b9e0-106">イベント バス サービスでは、データが BizTalk によってメッセージ ボックス データベースに入れられ、プライマリ インポート データベースにインポートを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="3b9e0-106">The Event Bus service reads the data queued in the MessageBox database by BizTalk and imports it into the primary import database.</span></span>  
  
 <span data-ttu-id="3b9e0-107">で非同期操作が BAM を構成するには、別のコンピューターに、イベント バス サービスと、呼び出し元アプリケーション (たとえば、オーケストレーション ホスト) を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b9e0-107">To configure BAM for asynchronous operation, the Event Bus Service and the calling application (e.g. Orchestration Host) should run on different computers.</span></span> <span data-ttu-id="3b9e0-108">これにより、呼び出し元のアプリケーションをすぐに、別のコンピューターで、CPU を使用して処理するイベント データを削除します。</span><span class="sxs-lookup"><span data-stu-id="3b9e0-108">This allows the calling application to get rid of the event data immediately to be processed using the CPU on a different computer.</span></span>  
  
 <span data-ttu-id="3b9e0-109">この BAM トポロジは、トランザクションの一貫性もあります。</span><span class="sxs-lookup"><span data-stu-id="3b9e0-109">This BAM topology is also transaction-consistent.</span></span> <span data-ttu-id="3b9e0-110">イベント バス サービスは、メッセージ ボックス データベースからコミットされたデータを読み取るだけのため、呼び出し元のアプリケーションにロールバックされたトランザクションの BAM データは取得ことはありません。</span><span class="sxs-lookup"><span data-stu-id="3b9e0-110">You will never get BAM data for transactions that rolled back in the calling application, because the Event Bus Service only reads the committed data from the MessageBox database.</span></span> <span data-ttu-id="3b9e0-111">コミットされたトランザクションの BAM データは、短い待機時間でのクエリと集計表示されます。</span><span class="sxs-lookup"><span data-stu-id="3b9e0-111">The BAM data for the transactions that were committed will show up for query and aggregation with small latency.</span></span>  
  
 <span data-ttu-id="3b9e0-112">エラーが発生した場合、いくつかの時間、タイムアウトを使用して、復旧ロジックのクラッシュおよび具合に、イベント バス サービスが再試行されます。</span><span class="sxs-lookup"><span data-stu-id="3b9e0-112">If errors occur, the Event Bus Service will retry a few times, use timeouts, crash recovery logic, and so on.</span></span> <span data-ttu-id="3b9e0-113">ただし、データが無効な形式にある場合は特殊なテーブル終了します。</span><span class="sxs-lookup"><span data-stu-id="3b9e0-113">If however the data is in an invalid format, it ends up in special tables.</span></span> <span data-ttu-id="3b9e0-114">この状態を示す、イベント ログでイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="3b9e0-114">An event occurs in the event log to indicate this condition.</span></span> <span data-ttu-id="3b9e0-115">この追加の障害点では、システム管理の難しさが向上します。</span><span class="sxs-lookup"><span data-stu-id="3b9e0-115">This additional failure point increases the difficulty of managing the system.</span></span>  
  
 <span data-ttu-id="3b9e0-116">コードから非同期のアプローチを使用することは、通常、DirectEventStream を BufferedEventStream と置き換えると、BAM プライマリ インポート、1 つではなく、コンス トラクターで、メッセージ ボックスに、接続文字列を渡すことと同程度に簡単です。</span><span class="sxs-lookup"><span data-stu-id="3b9e0-116">Using the asynchronous approach from code is usually as simple as replacing the DirectEventStream with BufferedEventStream, and passing the connection string to the Message Box in the constructor, instead of the one for BAM Primary Import.</span></span>  
  
 <span data-ttu-id="3b9e0-117">非同期ビジネス イベントのコードで追跡に関する次のガイドラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="3b9e0-117">Use the following guidelines regarding asynchronous business event tracking in your code:</span></span>  
  
-   <span data-ttu-id="3b9e0-118">常に continuation を使用、アクティビティが複数のアプリケーションを対象とし、BAM にデータを非同期に送信するときにすべてのコンポーネントに ActivityID を伝達する場合でもです。</span><span class="sxs-lookup"><span data-stu-id="3b9e0-118">Always use continuation when the Activity spans multiple applications and you send the data asynchronously to BAM, even if you propagate the ActivityID to all components.</span></span> <span data-ttu-id="3b9e0-119">この場合は、一意の文字列 (アプリケーション名など) で各アプリケーションで ActivityID を使い分けますを使用します。</span><span class="sxs-lookup"><span data-stu-id="3b9e0-119">In this case, use a different ActivityID in each application by prefixing it with a unique string (e.g. Application Name).</span></span> <span data-ttu-id="3b9e0-120">これは、機能は、BAM は、クエリが正しいことを確認順序のイベントを管理する必要があり、集計の結果では、ランダムな順序は、BAM に別のアプリケーションからデータが届く場合があります必要です。</span><span class="sxs-lookup"><span data-stu-id="3b9e0-120">This is necessary because the data from different applications might arrive to BAM in random order, and BAM has to manage the out-of-order events to ensure correct Query and Aggregation results.</span></span>  
  
-   <span data-ttu-id="3b9e0-121">イベント データは、トランザクションに依存しているために、(COM + 疎結合イベントや WMI イベント) を監視するイベントの一般的な方法は BAM には適用ではありません。</span><span class="sxs-lookup"><span data-stu-id="3b9e0-121">The usual methods of event monitoring (e.g. COM+ Loosely Coupled Events or WMI Events) are not applicable for BAM because the event data is independent of the transaction.</span></span> <span data-ttu-id="3b9e0-122">たとえば、$1000 の 1 つだけ受信する販売注文がありましたが、データベースに保存する試行が 10 回失敗したときに、$10,000 の合計 10 個の注文が受信したように見えます可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3b9e0-122">For example, it may look like you received 10 purchase orders for a total of $10,000 while there was only one incoming purchase order for $1000, but the attempt to save it to the database failed 10 times.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b9e0-123">参照</span><span class="sxs-lookup"><span data-stu-id="3b9e0-123">See Also</span></span>  

 [<span data-ttu-id="3b9e0-124">同期ビジネス イベントの追跡</span><span class="sxs-lookup"><span data-stu-id="3b9e0-124">Synchronous Business Event Tracking</span></span>](../core/synchronous-business-event-tracking.md)