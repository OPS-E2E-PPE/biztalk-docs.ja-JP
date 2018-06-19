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
# <a name="scenario-4-sizing-the-tracking-database-for-all-messages"></a>シナリオ 4: すべてのメッセージの追跡データベースのサイズ変更
Microsoft® BizTalk Server® 2004 の実装であるすべての 3 つのメッセージ シナリオがある場合は一緒に追加する必要があります。 すべての BizTalk 追跡データベースのサイズを決定するシナリオの結果。  
  
 上記の例について検討します。  
  
|Scenario|1 年ごとに必要な領域 (単位は GB)|  
|--------------|-------------------------------------|  
|簡易メッセージ|4.78|  
|オーケストレーション内のメッセージ|7.18|  
|同報リストに送信されるオーケストレーション内のメッセージ|10.8|  
|**合計**|22.04|  
  
 また、3 つのシナリオすべてについてメッセージ本文の追跡を有効にしている場合、結果は、次のようになります。  
  
|Scenario|1 年ごとに必要な領域 (単位は GB)|  
|--------------|-------------------------------------|  
|簡易メッセージ|50.1|  
|オーケストレーション内のメッセージ|50.1|  
|同報リストに送信されるオーケストレーション内のメッセージ|83.45|  
|**合計**|183.65|  
  
 この結果、BizTalk 追跡データベースのサイズは 1 年ごとに総計 205.69 GB 増加することになります。 この値に予備の領域は含まれません。 推奨では、総計に 10% の予備の領域を加算する場合、BizTalk 追跡データベースのサイズとして、1 年ごとに 227.94 GB の増加を見積もる必要があります。 これには、上には、SQL のインデックス、ストレージなどのためのオーバーヘッドを検討してください。可能であればテストでテストのシナリオを実行した後、乗算した要素を基準とする必要があります。  
  
## <a name="other-factors-affecting-biztalk-tracking-database-size"></a>BizTalk 追跡データベースのサイズに影響を及ぼす他の要因  
 オーケストレーション内で使用する図形など他の項目も、BizTalk 追跡データベースのサイズに影響を及ぼします。  
  
 オーケストレーション デバッガーのオプションがオン (既定の設定) の場合、オーケストレーションの各図形の状態が BizTalk 追跡データベースに保存されます。  
  
 図形の状態を追跡するために必要なサイズを決定する式は次のとおりです。  
  
```  
[(# of object shapes ] * 76 bytes  
```  
  
 たとえば、下の図の場合、次の計算式を使用して BizTalk 追跡サイズを決定します。  
  
```  
((4) * 76 bytes = 304 bytes  
```  
  
 ![オーケストレーションの例](../core/media/sample-orchestration.gif "Sample_orchestration")  
  
 このオーケストレーションで 350 万件のメッセージを処理すると仮定した場合、このオーケストレーションを追跡するために必要な追加領域は、次のようになります。  
  
```  
304 bytes * 3,500,000/1024/1024 = 1015 MB ~ 0.99 GB.  
```  
  
 BizTalk 追跡データベースのサイズを推定するには、各オーケストレーションについて、オーケストレーション デバッガーのオプションが "オン" に設定されている場合を考慮する必要があります。  
  
## <a name="see-also"></a>参照  
 [追跡データベースのサイズをメッセージ変数を使用](../core/using-message-variables-to-size-the-tracking-database.md)   
 [メッセージ本文を追跡する追跡データベースのサイズ変更](../core/sizing-the-tracking-database-to-track-message-bodies.md)   
 [シナリオ 1: 単純な BizTalk メッセージの追跡データベースのサイズ変更](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md)   
 [シナリオ 2: オーケストレーションでメッセージの追跡データベースのサイズ変更](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md)   
 [シナリオ 3: 同報リストに送信されるメッセージの追跡データベースのサイズ変更](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)