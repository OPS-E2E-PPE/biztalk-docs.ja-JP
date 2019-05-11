---
title: アクティビティ Continuation |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- continuation tokens
- activities [BAM], code samples
- activities [BAM], continuation tokens
- continuations, activities [BAM]
- code samples, activities [BAM]
ms.assetid: 47d91ae6-77c1-4efb-940f-a7b3a325e5bd
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a8615dc75802b643783e3c366159180b740521a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361700"
---
# <a name="activity-continuation"></a>アクティビティ Continuation
BAM アクティビティ (ビジネス アクティビティとも呼ばれます) は、複数の異種アプリケーション (たとえば、パイプライン、2 つのオーケストレーション、基幹業務アプリケーション、および後に別のパイプライン) にまたがることができます。 BAM インフラストラクチャは、わずかな作業、開発者などと呼ばれる概念を持つ複数のアプリケーションからのイベントを関連付けることができます"*継続*、"次の図に表示されます。  
  
 ![](../core/media/ebiz-prog-bam-fig4-app-scopes-cont-tokens.gif "ebiz_prog_bam_fig4_app_scopes_cont_tokens")  

## <a name="applications"></a>[アプリケーション]  
 アクティビティの最初の部分は、Sales アプリケーションで行われますでは、アクティビティの 2 番目の部分は梱包/組み立てアプリケーションで行われ、最後に、配送の進捗が、出荷アプリケーションで使用可能です。 各アプリケーションは、現在の作業単位の異なる Id を使用して: 発注 (書 PO) 番号、販売注文番号 (SO)、および出荷指示番号 (UPS)。 2 つのアプリケーションの間でイベントを関連付けるためには、次の必要があります。  
  
- 継続トークンという、一意の両方のアプリケーション (たとえば、交換されるメッセージの部分) に提供されるデータを特定します。  
  
- 最初のアプリケーションで EnableContinuation を呼び出し、現在の ActivityID と共に継続トークンを渡します。  
  
- 2 番目のアプリケーションでは BeginActivity を呼び出さないでください。  
  
- 2 番目のアプリケーション内のすべての後続のイベントを ActivityID ではなく、継続トークンを使用して起動します。  
  
  次のコード例では、3 つのアプリケーションでアクティビティ continuation の使用を示します。  
  
  **注文書アプリケーション**  
  
```  
string oID="PO#123";  
string soID="SO#265";  
es.BeginActivity("PurchaseOrder",poID);  
es.UpdateActivity("PurchaseOrder",poID,  
    "POReceived",DateTime.UtcNow,  
    "POAmount",100,  
"CustomerCity","Seattle");  
es.EnableContinuation(  
   "PurchaseOrder",poId,soID);  
es.EndActivity("PurchaseOrder",poID);  
```  
  
 **調達アプリケーション**  
  
```  
string soID="SO#265";  
string upsID="UPS#97892";  
es.UpdateActivity("PurchaseOrder",soID,  
    "POApproved",DateTime.UtcNow,  
    "ProductName","ProductA");  
es.EnableContinuation(  
   "PurchaseOrder",soID,upsID);  
es.EndActivity("PurchaseOrder",soID);  
```  
  
 **出荷アプリケーション**  
  
```  
string upsID="UPS#97892"  
es.UpdateActivity("PurchaseOrder", upsID,  
"POShipped",DateTime.UtcNow);  
es.EndActivity("PurchaseOrder",upsID)  
  
```  
  
 アクティビティ continuation を使用して、コード内にこれらのガイドラインに従います。  
  
-   エンド ユーザーは、同じアクティビティの一部としてさまざまなアプリケーションの作業を扱う必要がある場合にのみ継続を使用します。 アプリケーションごとに個別のアクティビティを使用し、エンド ユーザーとして意味のあるアクティビティには、各アプリケーションで作業を表示する場合に、アクティビティのリレーションシップを作成します。  
  
-   アプリケーションの作業単位には、一対一のリレーションシップがない場合、行えますアクティビティ リレーションシップがないの継続などの販売注文が存在する複数の出荷する場合。  
  
-   同期的に BAM にデータを送信する場合 (DirectEventStream を使用) に関連するすべてのコンポーネント、ActivityID を伝達し、continuation を使用する必要はありません。  
  
-   非同期的に BAM にデータを送信する場合 (BufferedEventStream を使用してまたはオーケストレーションから)、すべてのコンポーネントに ActivityID を伝達される場合でも継続を使用してする必要があります。 この場合は、一意の文字列 (たとえば、アプリケーション名) で、各アプリケーションで ActivityID を使い分けますを使用する必要があります。 これは、ため、別のアプリケーションからデータが BAM にランダムな順序でくる可能性があります。 また、BAM は正しいクエリと集計の結果を確認する順序のイベントを非表示にする必要があります。  
  
-   継続より多くのデータを交換するようにアプリケーションの書き換えは必要ありません。  
  
## <a name="see-also"></a>参照  
  
 [BAM 動的インフラストラクチャ](../core/bam-dynamic-infrastructure.md)   
 [BAM API (BizTalk Server サンプル)](../core/bam-api-biztalk-server-sample.md)   
 [BAM End-to-End (BizTalk Server サンプル)](../core/bam-end-to-end-biztalk-server-sample.md)