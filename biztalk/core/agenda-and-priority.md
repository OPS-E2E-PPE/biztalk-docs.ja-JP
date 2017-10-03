---
title: "議題と優先度 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- business rules, executing
- Business Rules Engine, agendas
- Business Rules Engine, priorities
- business rules, priorities
- business rules, examples
- Business Rules Engine, examples
- examples, Business Rules Engine
- Business Rules Engine, rules
ms.assetid: ca54f750-4f2d-4734-8e6e-7af1b4967e6a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4529753251c2bf7934616b91662bde836c8339e1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="agenda-and-priority"></a>議題と優先度
ビジネス ルール エンジンの規則を評価し、アクションが実行を理解するのには、概念を理解する必要があります*議題*と*優先度*です。  
  
## <a name="agenda"></a>議題  
 議題は、実行するルールをキューに入れるためにエンジンが使用するスケジュールです。 議題はエンジンのインスタンスに存在し、一連のポリシーではなく 1 つのポリシーに作用します。 ファクトが作業メモリにアサートされ、特定のルールの条件が満たされると、議題にルールが配置され、優先度に従って実行されます。 ルールのアクションが上から下へと順に実行されたら、議題の次のルールのアクションが実行されます。  
  
 ルールに属するアクションはブロックとして扱われるので、すべてのアクションが実行されてから次のルールに移行します。 ルール ブロック内のアクションはすべて、ブロック内の他のアクションとは無関係に実行されます。 アサーションの詳細については、次を参照してください。[エンジンの制御関数](../core/engine-control-functions.md)です。  
  
 議題の使用例を次に示します。  
  
 **Rule1**  
  
```  
IF  
Fact1 == 1  
THEN  
Action1  
Action2  
```  
  
 **Rule2**  
  
```  
IF  
Fact1 > 0  
THEN  
Action3  
Action4  
```  
  
 値が 1 のファクト Fact1 をエンジンにアサートします。 Rule1 と Rule2 の両方の条件が満たされているため、両方のルールがアクションを実行するために議題に移動します。  
  
|作業メモリ|議題|  
|--------------------|------------|  
|Fact1 (値 = 1)|**Rule1**<br /><br /> -アクション 1<br />-Action2<br /><br /> **Rule2**<br /><br /> -Action3<br />-Action4|  
  
## <a name="priority"></a>[Priority]  
 実行の優先度は個々のルールに設定され、既定の優先度はすべてのルールで 0 です。 優先度の範囲は正と負のどちらも可能で、大きい数値が高い優先度となります。 優先度の高い順にアクションが実行されます。  
  
 次の例は、優先度がルールの実行順序にどのように影響するかを示しています。  
  
 **Rule1 (優先度 = 0)**  
  
```  
IF  
Fact1 == 1  
THEN  
Discount = 10%  
```  
  
 **Rule2 (優先度 = 10)**  
  
```  
IF  
Fact1 > 0  
THEN  
Discount = 15%  
```  
  
 両方のルールの条件が満たされましたが、Rule2 の方が優先度が高いため先に実行されます。 次の表に示すように、Rule1 に実行されるアクションの結果、最終的な割引は 10% です。  
  
|作業メモリ|議題|  
|--------------------|------------|  
|Fact1 (値 = 1)|**Rule2**<br /><br /> Discount = 15%<br /><br /> **Rule1**<br /><br /> 割引の 10% を =|  
  
## <a name="see-also"></a>参照  
 [ルール エンジン](../core/rule-engine.md)