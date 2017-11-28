---
title: "アクティビティを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5e218e2a-27f8-4df2-a1e0-27392112d369
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13b56424e06bdb8fad043acd92c22a88ca19f478
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-an-activity"></a><span data-ttu-id="3af7c-102">アクティビティの使用</span><span class="sxs-lookup"><span data-stu-id="3af7c-102">Using an Activity</span></span>
<span data-ttu-id="3af7c-103">BAM の最も簡単な使用方法は、BAM API を使用して明示的なマイルストーンまたはデータを送信することです。</span><span class="sxs-lookup"><span data-stu-id="3af7c-103">The simplest way to use BAM is to send explicit milestones or data using the BAM API.</span></span> <span data-ttu-id="3af7c-104">BAM アクティビティは、実際の作業単位との同期を維持している、SQL テーブルのレコードと考えることができます。</span><span class="sxs-lookup"><span data-stu-id="3af7c-104">You can think of the BAM activity as a record in a SQL table that you are keeping in synchronization with the actual unit of work.</span></span>  
  
-   <span data-ttu-id="3af7c-105">呼び出す`BeginActivity`新しい各作業単位です。</span><span class="sxs-lookup"><span data-stu-id="3af7c-105">Call `BeginActivity` for each new unit of work.</span></span>  
  
-   <span data-ttu-id="3af7c-106">呼び出す`EndActivity`ときに、作業が完了し、作業単位のコンテキストでイベントがなくなったらを期待します。</span><span class="sxs-lookup"><span data-stu-id="3af7c-106">Call `EndActivity` when the work is complete and you expect no more events in the context of this unit of work.</span></span>  
  
-   <span data-ttu-id="3af7c-107">呼び出す[Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx)データとマイルス トーン、インフォメーション ワーカーにとって役に立つを送信する実装の重要な箇所でします。</span><span class="sxs-lookup"><span data-stu-id="3af7c-107">Call [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) in critical places of the implementation, to send data and milestones that will be useful to the information worker.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3af7c-108">イベント ストリームは破棄される前にフラッシュされる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3af7c-108">The Event Stream must be flushed before disposing.</span></span> <span data-ttu-id="3af7c-109">EventStream オブジェクトは、ストリームを破棄するときにデータの自動フラッシュを実行しません。</span><span class="sxs-lookup"><span data-stu-id="3af7c-109">The EventStream object does not perform an automatic flush of the data when disposed.</span></span> <span data-ttu-id="3af7c-110">つまり、通常記述されるコード (操作の処理が完了した後にのみストリームをフラッシュするコード) では、フラッシュの呼び出し前に例外が発生した場合にデータを損失することになります。</span><span class="sxs-lookup"><span data-stu-id="3af7c-110">This means that code you would typically write in which you flush the stream only after you have finished processing your activities can result in data loss if an exception occurs before a call to flush.</span></span>  
>   
>  <span data-ttu-id="3af7c-111">データの損失を防ぐには、以下の擬似コードのように、処理をカプセル化して try/finally ブロックでフラッシュすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3af7c-111">To avoid data loss, we recommend that you encapsulate the processing and flush in a try/finally block as shown in the pseudo code below:</span></span>  
  
```  
BufferedEventStream es = new BufferedEventStream(…)  
Try  
{  
   // Do the activity processing here.  
}  
Finally  
{  
   if (es != null ) es.Flush();  
}  
```  
  
 <span data-ttu-id="3af7c-112">次のコード例は、作業単位が注文書の場合の BeginActivity、UpdateActivity、および EndActivity の使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="3af7c-112">The following example code shows how to do use BeginActivity, UpdateActivity, and EndActivity when the unit of work is a Purchase Order.</span></span> <span data-ttu-id="3af7c-113">例と仮定する文字列変数**poid**プロセスの現在の注文を識別します。</span><span class="sxs-lookup"><span data-stu-id="3af7c-113">In the example, we assume that the string variable **poid** identifies the current Purchase Order in process:</span></span>  
  
```  
using Microsoft.BizTalk.BAM.EventObservation;  
...   
EventStream es=new DirectEventStream(connectionString,1);  
...  
// At the beginning of the processing of a new work:  
//    Here poid is a string variable that has the current   
//    Purchase Order identifier (e.g. PO number)  
es.BeginActivity("PurchaseOrder",poid);  
es.UpdateActivity("PurchaseOrder",poid,  
    "POReceived",DateTime.UtcNow,  
    "POAmount",100,  
    "CustomerName",""Joe",  
    "CustomerCity","Seattle");  
...  
// few days later  
es.UpdateActivity("PurchaseOrder",poid,  
    "POApproved",DateTime.UtcNow,  
    "ProductName","Widget");  
...  
// and another few days later  
es. UpdateActivity("PurchaseOrder",poid,  
    "POShipped",DateTime.UtcNow);  
...  
// and finally  
es. UpdateActivity("PurchaseOrder",poid,  
    "Delivered",DateTime.UtcNow);  
es.EndActivity("PurchaseOrder",poid);  
```  
  
## <a name="see-also"></a><span data-ttu-id="3af7c-114">参照</span><span class="sxs-lookup"><span data-stu-id="3af7c-114">See Also</span></span>  
 <span data-ttu-id="3af7c-115">[BAM アクティビティのイベント ストリームの実装](../core/implementing-bam-activities-with-event-streams.md) </span><span class="sxs-lookup"><span data-stu-id="3af7c-115">[Implementing BAM Activities with Event Streams](../core/implementing-bam-activities-with-event-streams.md) </span></span>  
 <span data-ttu-id="3af7c-116">[アクティビティ Continuation](../core/activity-continuation.md) </span><span class="sxs-lookup"><span data-stu-id="3af7c-116">[Activity Continuation](../core/activity-continuation.md) </span></span>  
 <span data-ttu-id="3af7c-117">[BAM 動的インフラストラクチャ](../core/bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="3af7c-117">[BAM Dynamic Infrastructure](../core/bam-dynamic-infrastructure.md) </span></span>  
 [<span data-ttu-id="3af7c-118">BAM API (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="3af7c-118">BAM API (BizTalk Server Sample)</span></span>](../core/bam-api-biztalk-server-sample.md)