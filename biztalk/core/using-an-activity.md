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
# <a name="using-an-activity"></a>アクティビティを使用
BAM を使用する最も簡単な方法は、明示的なマイルス トーンまたは BAM API を使用してデータを送信します。 BAM アクティビティが作業の実際のユニットとの同期に維持している SQL テーブル内のレコードとして考えることができます。  
  
-   呼び出す`BeginActivity`新しい各作業単位です。  
  
-   呼び出す`EndActivity`ときに、作業が完了し、作業単位のコンテキストでイベントがなくなったらを期待します。  
  
-   呼び出す[Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx)データとインフォメーション ワーカーに役に立つマイルス トーンを送信する、実装の重要な箇所でします。  
  
> [!IMPORTANT]
>  イベント Stream は、破棄される前にフラッシュする必要があります。 EventStream オブジェクトには、破棄されたときに、データの自動フラッシュを実行しません。 これは、通常記述フラッシュ操作の処理が完了した後にのみストリーム損失につながる可能性のデータをフラッシュの呼び出しの前に、例外が発生した場合、そのコードを意味します。  
>   
>  データの損失を回避するためには、処理をカプセル化し、以下の擬似コードに示すように、try/finally ブロックでフラッシュすることお勧めします。  
  
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
  
 次のコード例では、作業単位が注文書 BeginActivity、UpdateActivity、および EndActivity の使用方法を示します。 この例で行っている文字列変数**poid**プロセスの現在の注文書を識別します。  
  
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
  
## <a name="see-also"></a>参照  
 [イベント ストリームを使用した BAM アクティビティを実装します。](../core/implementing-bam-activities-with-event-streams.md)   
 [アクティビティ Continuation](../core/activity-continuation.md)   
 [BAM 動的インフラストラクチャ](../core/bam-dynamic-infrastructure.md)   
 [BAM API (BizTalk Server サンプル)](../core/bam-api-biztalk-server-sample.md)