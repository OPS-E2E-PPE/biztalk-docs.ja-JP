---
title: 式における演算子の使用 |Microsoft Docs
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
ms.openlocfilehash: acb471fd12ad41776b116b1ed2f27fcfb6ea6f8f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395430"
---
# <a name="using-operators-in-expressions"></a>式における演算子の使用
次の xlang/s 演算子は、オーケストレーションの式で使用可能な。 C# の対応する演算子の機能にほぼ準拠します。  
  
|演算子|説明|例|  
|--------------|-----------------|-------------|  
|checked()|算術オーバーフローでエラーが発生します。|checked(x = y * 1000)|  
|unchecked()|算術オーバーフローを無視します。|unchecked(x = y * 1000)|  
|新機能|クラスのインスタンスを作成します。|myObject 新しい MyClass; を =|  
|typeof|型の取得|myMapType typeof(myMap) を =|  
|succeeded()|トランザクション スコープまたはオーケストレーションが正常に完了のテスト|成功した (\<子トランザクションの現在のスコープまたはサービスのトランザクション ID\>)|  
|存在します。|メッセージ コンテキスト プロパティの存在をテストします。|BTS します。RetryCount Message_In が存在します。|  
|+|単項プラス|+(int x)|  
|-|単項マイナス|-(int x)|  
|!|論理否定|!myBool|  
|~|ビットごとの補数|x = ~y|  
|()|キャスト|たとえば、myInt (bool)|  
|*|times|Weight = MyMsg.numOrders * 20|  
|/|割った値|x / y|  
|+|プラス|x + y|  
|-|マイナス|x - y|  
|<<|左シフト|x << 2|  
|>>|右シフトします。|x >> 2|  
|<|小さい|場合 (MyMsg.numOrders < 10).|  
|>|大きい|場合 (MyMsg.numOrders > 10).|  
|<=|等しいまたはそれよりも小さい|場合 (MyMsg.numOrders < = 10).|  
|>=|大きいまたは等しい|場合 (MyMsg.numOrders > = 10).|  
|==|等しい|If (MyMsg.numOrders == 10)...|  
|!=|等しくないです。|場合 (MyMsg.numOrders! = 10).|  
|&|、|場合 (myByte & 255).|  
|^|排他または|場合 (myByte ^1).|  
|&#124;|または|場合 (myByte &#124; 1).|  
|&&|条件付きと|If (MyMsg.numOrders > 10) && (MyMsg.numOrders < 100)|  
|&#124;&#124;|条件付きまたは|If (MyMsg.numOrders < 10) &#124;&#124; (MyMsg.numOrders > 100)|  
|//|コメント|これはコメントです。|  
  
> [!NOTE]
>  一般的な式とフィルター式で使用される規則とは異なる、**受信**図形。  
  
## <a name="see-also"></a>参照  
 [フィルターと受信メッセージ図形の使用](../core/using-filters-with-the-receive-message-shape.md)