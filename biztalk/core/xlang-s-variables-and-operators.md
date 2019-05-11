---
title: Xlang-s の変数および演算子 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 02512789-2cb9-4ba9-aa78-e59b248e6b24
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4eace5d4a30f8cac80403143a5dc3cfb887c0bc5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65246442"
---
# <a name="xlang-s-variables-and-operators"></a>Xlang-s の変数および演算子
このセクションでは、変数と、xlang/s 言語で使用される演算子について説明します。  
  
## <a name="xlangs-variables"></a>Xlang/s の変数  
 変数は、記憶域の場所を表します。 すべての変数ができる値を指定する型で変数に格納されています。 Xlang/s はタイプ セーフ、およびそのコンパイラでは、変数に格納されている値は常に適切な型のことが保証されます。 XLANG/秒には、次の変数の型がサポートされています。  
  
- メッセージ  
  
- 関連付けセット  
  
- サービスへのリンク  
  
- ポート  
  
- 識別の組み込み値型:**ブール**、**バイト**、 **Char**、 **Decimal**、**二重**、 **Int16**、 **Int32**、 **Int64**、 **SByte**、**単一**、**文字列**、 **UInt16**、 **UInt32**、および**UInt64**  
  
- オブジェクト  
  
- 列挙型  
  
  XLANG/秒では、これらの型のそれぞれの初期化のセマンティクスを提供します。 このような初期化は、その型の変数への代入として表示できます。 Xlang/s では、変数を割り当てる必要があります間違いなく前に、その値を取得または使用することができます。  
  
## <a name="xlangs-operators"></a>Xlang/s の演算子  
 XLANG/秒では、次の演算子をサポートします。 C# の対応する演算子の機能にほぼ準拠します。  
  
|演算子|説明|例|  
|--------------|-----------------|-------------|  
|オン|算術オーバーフローでエラーを発生させます。|checked(x = y * 1000)|  
|unchecked|算術オーバーフローを無視します。|unchecked(x = y * 1000)|  
|新機能|クラスのインスタンスを作成します|myObject 新しい MyClass; を =|  
|typeof|型を取得します。|myMapType typeof(myMap) を =|  
|succeeded|トランザクション スコープまたはオーケストレーションが正常に完了のテスト|成功した (\<子トランザクションの現在のスコープまたはサービスのトランザクション ID\>)|  
|存在します。|メッセージ コンテキスト プロパティの存在のテスト|BTS します。RetryCount Message_In が存在します。|  
|+|単項プラス|+(int x)|  
|-|単項マイナス|-(int x)|  
|!|論理否定|!myBool|  
|~|ビットごとの補数|x = ~y|  
|()|キャスト|たとえば、myInt (bool)|  
|*|時間|Weight = MyMsg.numOrders * 20|  
|/|割った値|x / y|  
|+|プラス|x + y|  
|-|マイナス|x - y|  
|<<|左シフト|x << 2|  
|>>|右シフトします。|x >> 2|  
|<|次の値未満|場合 (MyMsg.numOrders < 10).|  
|>|より大きい|場合 (MyMsg.numOrders > 10).|  
|<=|以下|場合 (MyMsg.numOrders < = 10).|  
|>=|以上|場合 (MyMsg.numOrders > = 10).|  
|==|等しい|If (MyMsg.numOrders == 10)...|  
|!=|次の値に等しくない|場合 (MyMsg.numOrders! = 10).|  
  
## <a name="see-also"></a>参照  
 [Xlang-s データ型](../core/xlang-s-data-types.md)   
 [Xlang-s ステートメント](../core/xlang-s-statements.md)   
 [Xlang-s 式](../core/xlang-s-expressions.md)   
 [Xlang-s の予約語](../core/xlang-s-reserved-words.md)   
 [XLANG-s から BPEL4WS への種類の変換](../core/xlang-s-to-bpel4ws-type-conversions.md)