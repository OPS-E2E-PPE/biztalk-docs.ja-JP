---
title: アクティビティ Continuation |Microsoft ドキュメント
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
ms.openlocfilehash: c7568da0647ae9847c3de2d060d75a53466b9709
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224794"
---
# <a name="activity-continuation"></a>アクティビティ Continuation
BAM アクティビティ (ビジネス アクティビティとも呼ばれます) は複数の異種アプリケーションにまたがることができます (たとえば、1 つのパイプラインから 2 つのオーケストレーション、1 つの基幹業務アプリケーションを経て別のパイプラインに至るなど)。 BAM インフラストラクチャは、開発者と呼ばれる概念の手助けを持つ複数のアプリケーションからのイベントを関連付けることができます"*継続*、"次の図に示したです。  
  
 ![](../core/media/ebiz-prog-bam-fig4-app-scopes-cont-tokens.gif "ebiz_prog_bam_fig4_app_scopes_cont_tokens")  

## <a name="applications"></a>[アプリケーション]  
 アクティビティの最初の部分は販売アプリケーションで行われ、2 番目の部分は梱包/組み立てアプリケーションで行われます。最後に、配送の進捗が、出荷アプリケーションで利用可能になります。 各アプリケーションでは、そのときの作業単位によって、注文書番号 (PO)、販売注文番号 (SO)、出荷指示番号 (UPS) というように ID を使い分けます。 2 つの異なるアプリケーションの間でイベントを関連付けるには、以下の指示に従う必要があります。  
  
-   継続トークンという、両方のアプリケーションで使用できる一意のデータ (たとえば、交換するメッセージの一部分) を指定します。  
  
-   最初のアプリケーションで EnableContinuation を呼び出し、現在の ActivityID と共に継続トークンを渡します。  
  
-   2 つ目のアプリケーションでは BeginActivity を呼び出さないでください。  
  
-   2 つ目のアプリケーションでは、以後すべてのイベントを ActivityID ではなく継続トークンを使用して発生させます。  
  
 次のコード例で、3 つのアプリケーションでアクティビティ Continuation を使用する方法を示します。  
  
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
  
 アクティビティ Continuation をコード内で使用するときは、次のガイドラインに従ってください。  
  
-   エンド ユーザーが、異なるアプリケーションの作業を同一のアクティビティの一部として処理する必要がある場合に限り、Continuation を使用します。 エンド ユーザーが各アプリケーションの中でその作業を意味のあるアクティビティとして見る場合、アプリケーションごとに個別のアクティビティを使用し、アクティビティのリレーションシップを作成します。  
  
-   1 つの販売注文に複数の出荷があるときなど、複数のアプリケーションの作業単位間に一対一のリレーションシップがない場合、アクティビティのリレーションシップは使用できますが、Continuation は使用できません。  
  
-   (DirectEventStream を使用して) BAM に同期的にデータを送信し、関連するすべてのコンポーネントに ActivityID を伝達する場合、Continuation を使用する必要はありません。  
  
-   (BufferedEventStream を使用するか、またはオーケストレーションから) BAM に非同期にデータを送信するときは、すべてのコンポーネントに ActivityID を伝達する場合でも Continuation を使用する必要があります。 この場合、アプリケーションごとに一意の文字列 (アプリケーション名など) をプレフィックスとして付けることで、ActivityID を使い分ける必要があります。 複数のアプリケーションから BAM にランダムにデータが到着することがあり、BAM ではそのような場合にも正しいクエリと集計の結果を得るため、適切な順序でないイベントを隠蔽する必要があるので、ID の使い分けが必要です。  
  
-   Continuation を使用する場合、より多くのデータを交換できるようにアプリケーションを書き換える必要はありません。  
  
## <a name="see-also"></a>参照  
  
 [BAM 動的インフラストラクチャ](../core/bam-dynamic-infrastructure.md)   
 [BAM API (BizTalk Server サンプル)](../core/bam-api-biztalk-server-sample.md)   
 [BAM エンド ツー エンド (BizTalk Server サンプル)](../core/bam-end-to-end-biztalk-server-sample.md)