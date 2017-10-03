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
# <a name="using-an-activity"></a>アクティビティの使用
BAM の最も簡単な使用方法は、BAM API を使用して明示的なマイルストーンまたはデータを送信することです。 BAM アクティビティは、実際の作業単位との同期を維持している、SQL テーブルのレコードと考えることができます。  
  
-   呼び出す`BeginActivity`新しい各作業単位です。  
  
-   呼び出す`EndActivity`ときに、作業が完了し、作業単位のコンテキストでイベントがなくなったらを期待します。  
  
-   呼び出す[Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx)データとマイルス トーン、インフォメーション ワーカーにとって役に立つを送信する実装の重要な箇所でします。  
  
> [!IMPORTANT]
>  イベント ストリームは破棄される前にフラッシュされる必要があります。 EventStream オブジェクトは、ストリームを破棄するときにデータの自動フラッシュを実行しません。 つまり、通常記述されるコード (操作の処理が完了した後にのみストリームをフラッシュするコード) では、フラッシュの呼び出し前に例外が発生した場合にデータを損失することになります。  
>   
>  データの損失を防ぐには、以下の擬似コードのように、処理をカプセル化して try/finally ブロックでフラッシュすることをお勧めします。  
  
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
  
 次のコード例は、作業単位が注文書の場合の BeginActivity、UpdateActivity、および EndActivity の使用方法を示しています。 例と仮定する文字列変数**poid**プロセスの現在の注文を識別します。  
  
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
 [BAM アクティビティのイベント ストリームの実装](../core/implementing-bam-activities-with-event-streams.md)   
 [アクティビティ Continuation](../core/activity-continuation.md)   
 [BAM 動的インフラストラクチャ](../core/bam-dynamic-infrastructure.md)   
 [BAM API (BizTalk Server サンプル)](../core/bam-api-biztalk-server-sample.md)