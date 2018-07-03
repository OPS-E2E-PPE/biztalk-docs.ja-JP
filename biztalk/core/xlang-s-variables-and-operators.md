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
ms.openlocfilehash: f47ee6f69c1a69d0686bdb75b5dcaffc4a7c60a4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023848"
---
# <a name="xlang-s-variables-and-operators"></a>Xlang-s の変数および演算子
このセクションでは、XLANG/s 言語で使用される変数および演算子について説明します。  
  
## <a name="xlangs-variables"></a>XLANG/s の変数  
 変数は格納場所を表します。 各変数には型があり、この型によってその変数に格納できる値が決まります。 XLANG/s はタイプ セーフであり、コンパイラによって変数に格納された値が常に適切な型であることが保証されます。 XLANG/s は、次の変数の型をサポートしています。  
  
- メッセージ  
  
- 関連付けセット  
  
- サービス リンク  
  
- [ポート]  
  
- 組み込みの値の型を識別:**ブール**、**バイト**、 **Char**、 **Decimal**、**二重**、 **Int16**、 **Int32**、 **Int64**、 **SByte**、**単一**、**文字列**、**UInt16**、 **UInt32**、および**UInt64**  
  
- オブジェクト  
  
- 列挙型  
  
  XLANG/s には、上記の各型について初期化のセマンティクスが用意されています。 これらの初期化は、その型の変数への代入と見なすことができます。 XLANG/s では、変数に明示的に代入しないと、その値を取得または使用することはできません。  
  
## <a name="xlangs-operators"></a>XLANG/s の演算子  
 XLANG/s は、次の演算子をサポートしています。 C# の対応する演算子の機能にほぼ準拠しています。  
  
|演算子|説明|例|  
|--------------|-----------------|-------------|  
|オン|算術オーバーフローでエラーを発生させます。|checked(x = y * 1000)|  
|オフ|算術オーバーフローを無視|unchecked(x = y * 1000)|  
|新機能|クラスのインスタンスを作成|myObject = new MyClass;|  
|typeof|型を取得|myMapType = typeof(myMap)|  
|succeeded|トランザクション スコープまたはオーケストレーションが正常に完了するかどうかをテスト|成功した (\<子トランザクションの現在のスコープまたはサービスのトランザクション ID\>)|  
|存在する|メッセージ コンテキスト プロパティの存在のテスト|BTS.RetryCount exists Message_In|  
|+|単項プラス|+(int x)|  
|-|単項マイナス|-(int x)|  
|!|論理否定|!myBool|  
|~|ビットごとの補数|x = ~y|  
|()|キャスト|(bool) myInt|  
|*|時間|Weight = MyMsg.numOrders * 20|  
|/|割った値|x / y|  
|+|プラス|x + y|  
|-|マイナス|x - y|  
|<<|左シフト|x << 2|  
|>>|右シフト|x >> 2|  
|<|より小さい|If (MyMsg.numOrders < 10)...|  
|>|より大きい|場合 (MyMsg.numOrders > 10).|  
|<=|以下|If (MyMsg.numOrders <= 10)...|  
|>=|以上|場合 (MyMsg.numOrders > = 10).|  
|==|等しい|If (MyMsg.numOrders == 10)...|  
|!=|等しくない|If (MyMsg.numOrders != 10)...|  
  
## <a name="see-also"></a>参照  
 [Xlang-s データ型](../core/xlang-s-data-types.md)   
 [Xlang-s ステートメント](../core/xlang-s-statements.md)   
 [Xlang-s 式](../core/xlang-s-expressions.md)   
 [Xlang-s の予約語](../core/xlang-s-reserved-words.md)   
 [XLANG-s から BPEL4WS への種類の変換](../core/xlang-s-to-bpel4ws-type-conversions.md)