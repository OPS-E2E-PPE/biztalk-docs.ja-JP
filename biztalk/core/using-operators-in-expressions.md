---
title: 式における演算子の使用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, operators
- XLANG/s, operators
- orchestrations, XLANG/s
ms.assetid: f0948ce2-c508-48aa-af79-d207f577b22f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5aec9ed6ebecb0b151dbfe9d5c09707b954fdf45
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974304"
---
# <a name="using-operators-in-expressions"></a>式における演算子の使用
オーケストレーションの式では次の XLANG/s 演算子を使用できます。 C# の対応する演算子の機能にほぼ準拠しています。  
  
|演算子|Description|例|  
|--------------|-----------------|-------------|  
|checked()|算術オーバーフローでエラーを発生|checked(x = y * 1000)|  
|unchecked()|算術オーバーフローを無視します。|unchecked(x = y * 1000)|  
|新機能|クラスのインスタンスを作成します。|myObject = new MyClass;|  
|typeof|型の取得|myMapType = typeof(myMap)|  
|succeeded()|トランザクションのスコープまたはオーケストレーションが正常に完了のテスト|成功した (\<子トランザクションの現在のスコープまたはサービスのトランザクション ID\>)|  
|存在する|メッセージ コンテキスト プロパティの存在をテスト|BTS.RetryCount exists Message_In|  
|+|単項プラス|+(int x)|  
|-|単項マイナス|-(int x)|  
|!|論理否定|!myBool|  
|~|ビットごとの補数|x = ~y|  
|()|キャスト|(bool) myInt|  
|*|times|Weight = MyMsg.numOrders * 20|  
|/|割った値|x / y|  
|+|加算|x + y|  
|-|負符号|x - y|  
|<<|左シフト|x << 2|  
|>>|右シフトします。|x >> 2|  
|<|小さい|If (MyMsg.numOrders < 10)...|  
|>|大きい|場合 (MyMsg.numOrders > 10).|  
|<=|以下に|If (MyMsg.numOrders <= 10)...|  
|>=|大きいまたは等しい|場合 (MyMsg.numOrders > = 10).|  
|==|一致します。|If (MyMsg.numOrders == 10)...|  
|!=|等しくないです。|If (MyMsg.numOrders != 10)...|  
|&|クエリと|If (myByte & 255)...|  
|^|排他的 OR|If (myByte ^ 1)...|  
|&#124;|または|場合 (myByte (& a) #124; 1).|  
|&&|条件 AND|If (MyMsg.numOrders > 10) && (MyMsg.numOrders < 100)|  
|&#124;&#124;|条件 OR|場合 (MyMsg.numOrders < 10) (& m); #124 &#124;です。(MyMsg.numOrders > 100)|  
|//|コメントを付ける|//これはコメントです。|  
  
> [!NOTE]
>  一般式とフィルター式で使用されるとが異なるルール、**受信**図形です。  
  
## <a name="see-also"></a>参照  
 [フィルターと受信メッセージ図形の使用](../core/using-filters-with-the-receive-message-shape.md)