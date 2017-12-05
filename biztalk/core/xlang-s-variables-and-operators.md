---
title: "XLANG の変数および演算子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 02512789-2cb9-4ba9-aa78-e59b248e6b24
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c1773b7af3ec029026ee884e6c1161e27a3c330
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="xlang-s-variables-and-operators"></a>XLANG の変数および演算子
このセクションでは、XLANG/s 言語で使用される変数および演算子について説明します。  
  
## <a name="xlangs-variables"></a>XLANG/s の変数  
 変数は格納場所を表します。 各変数には型があり、この型によってその変数に格納できる値が決まります。 XLANG/s はタイプ セーフであり、コンパイラによって変数に格納された値が常に適切な型であることが保証されます。 XLANG/s は、次の変数の型をサポートしています。  
  
-   メッセージ  
  
-   関連付けセット  
  
-   サービス リンク  
  
-   [ポート]  
  
-   組み込み値型を識別します**ブール**、**バイト**、 **Char**、 **10 進**、**二重**、 。**Int16**、 **Int32**、 **Int64**、 **SByte**、**単一**、**文字列**、**UInt16**、 **UInt32**、および**UInt64**  
  
-   オブジェクト  
  
-   列挙型  
  
 XLANG/s には、上記の各型について初期化のセマンティクスが用意されています。 これらの初期化は、その型の変数への代入と見なすことができます。 XLANG/s では、変数に明示的に代入しないと、その値を取得または使用することはできません。  
  
## <a name="xlangs-operators"></a>XLANG/s の演算子  
 XLANG/s は、次の演算子をサポートしています。 C# の対応する演算子の機能にほぼ準拠しています。  
  
|演算子|Description|例|  
|--------------|-----------------|-------------|  
|オン|算術オーバーフローでエラーが発生します|checked(x = y * 1000)|  
|オンになっていません。|算術オーバーフローを無視|unchecked(x = y * 1000)|  
|新機能|クラスのインスタンスを作成|myObject = new MyClass;|  
|typeof|型を取得|myMapType = typeof(myMap)|  
|succeeded|トランザクション スコープまたはオーケストレーションが正常に完了するかどうかをテスト|成功した (\<子トランザクションの現在のスコープまたはサービスのトランザクション ID\>)|  
|存在する|メッセージ コンテキスト プロパティの有無のテスト|BTS.RetryCount exists Message_In|  
|+|単項プラス|+(int x)|  
|-|単項マイナス|-(int x)|  
|!|論理否定|!myBool|  
|~|ビットごとの補数|x = ~y|  
|()|キャスト|(bool) myInt|  
|*|時間|Weight = MyMsg.numOrders * 20|  
|/|割った値|x / y|  
|+|プラス|x + y|  
|-|負符号|x - y|  
|<<|左シフト|x << 2|  
|>>|右シフト|x >> 2|  
|<|より小さい|If (MyMsg.numOrders < 10)...|  
|>|より大きい|場合 (MyMsg.numOrders > 10).|  
|<=|以下|If (MyMsg.numOrders <= 10)...|  
|>=|以上|場合 (MyMsg.numOrders > = 10).|  
|==|一致します。|If (MyMsg.numOrders == 10)...|  
|!=|等しくない|If (MyMsg.numOrders != 10)...|  
  
## <a name="see-also"></a>参照  
 [XLANG のデータ型](../core/xlang-s-data-types.md)   
 [XLANG のステートメント](../core/xlang-s-statements.md)   
 [XLANG の式](../core/xlang-s-expressions.md)   
 [XLANG s の予約語](../core/xlang-s-reserved-words.md)   
 [XLANG-s から BPEL4WS への種類の変換](../core/xlang-s-to-bpel4ws-type-conversions.md)