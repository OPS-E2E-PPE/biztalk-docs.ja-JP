---
title: アクティビティを使用して |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5e218e2a-27f8-4df2-a1e0-27392112d369
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2da2176ba4573762853f44447284c6aeb73f57e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399906"
---
# <a name="using-an-activity"></a><span data-ttu-id="2b955-102">アクティビティを使用</span><span class="sxs-lookup"><span data-stu-id="2b955-102">Using an Activity</span></span>
<span data-ttu-id="2b955-103">BAM を使用する最も簡単な方法は、明示的なマイルス トーンまたは BAM API を使用してデータを送信します。</span><span class="sxs-lookup"><span data-stu-id="2b955-103">The simplest way to use BAM is to send explicit milestones or data using the BAM API.</span></span> <span data-ttu-id="2b955-104">BAM アクティビティが作業の実際のユニットとの同期に維持している SQL テーブル内のレコードとして考えることができます。</span><span class="sxs-lookup"><span data-stu-id="2b955-104">You can think of the BAM activity as a record in a SQL table that you are keeping in synchronization with the actual unit of work.</span></span>  
  
-   <span data-ttu-id="2b955-105">呼び出す`BeginActivity`新しい各作業単位です。</span><span class="sxs-lookup"><span data-stu-id="2b955-105">Call `BeginActivity` for each new unit of work.</span></span>  
  
-   <span data-ttu-id="2b955-106">呼び出す`EndActivity`ときに、作業が完了し、作業単位のコンテキストでイベントがなくなったらを期待します。</span><span class="sxs-lookup"><span data-stu-id="2b955-106">Call `EndActivity` when the work is complete and you expect no more events in the context of this unit of work.</span></span>  
  
-   <span data-ttu-id="2b955-107">呼び出す[Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx)データとインフォメーション ワーカーに役に立つマイルス トーンを送信する、実装の重要な箇所でします。</span><span class="sxs-lookup"><span data-stu-id="2b955-107">Call [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) in critical places of the implementation, to send data and milestones that will be useful to the information worker.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2b955-108">イベント Stream は、破棄される前にフラッシュする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b955-108">The Event Stream must be flushed before disposing.</span></span> <span data-ttu-id="2b955-109">EventStream オブジェクトには、破棄されたときに、データの自動フラッシュを実行しません。</span><span class="sxs-lookup"><span data-stu-id="2b955-109">The EventStream object does not perform an automatic flush of the data when disposed.</span></span> <span data-ttu-id="2b955-110">これは、通常記述フラッシュ操作の処理が完了した後にのみストリーム損失につながる可能性のデータをフラッシュの呼び出しの前に、例外が発生した場合、そのコードを意味します。</span><span class="sxs-lookup"><span data-stu-id="2b955-110">This means that code you would typically write in which you flush the stream only after you have finished processing your activities can result in data loss if an exception occurs before a call to flush.</span></span>  
>   
>  <span data-ttu-id="2b955-111">データの損失を回避するためには、処理をカプセル化し、以下の擬似コードに示すように、try/finally ブロックでフラッシュすることお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2b955-111">To avoid data loss, we recommend that you encapsulate the processing and flush in a try/finally block as shown in the pseudo code below:</span></span>  
  
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
  
 <span data-ttu-id="2b955-112">次のコード例では、作業単位が注文書 BeginActivity、UpdateActivity、および EndActivity の使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2b955-112">The following example code shows how to do use BeginActivity, UpdateActivity, and EndActivity when the unit of work is a Purchase Order.</span></span> <span data-ttu-id="2b955-113">この例で行っている文字列変数**poid**プロセスの現在の注文書を識別します。</span><span class="sxs-lookup"><span data-stu-id="2b955-113">In the example, we assume that the string variable **poid** identifies the current Purchase Order in process:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2b955-114">参照</span><span class="sxs-lookup"><span data-stu-id="2b955-114">See Also</span></span>  
 <span data-ttu-id="2b955-115">[イベント ストリームを使用した BAM アクティビティを実装します。](../core/implementing-bam-activities-with-event-streams.md) </span><span class="sxs-lookup"><span data-stu-id="2b955-115">[Implementing BAM Activities with Event Streams](../core/implementing-bam-activities-with-event-streams.md) </span></span>  
 <span data-ttu-id="2b955-116">[アクティビティ Continuation](../core/activity-continuation.md) </span><span class="sxs-lookup"><span data-stu-id="2b955-116">[Activity Continuation](../core/activity-continuation.md) </span></span>  
 <span data-ttu-id="2b955-117">[BAM 動的インフラストラクチャ](../core/bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="2b955-117">[BAM Dynamic Infrastructure](../core/bam-dynamic-infrastructure.md) </span></span>  
 [<span data-ttu-id="2b955-118">BAM API (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="2b955-118">BAM API (BizTalk Server Sample)</span></span>](../core/bam-api-biztalk-server-sample.md)