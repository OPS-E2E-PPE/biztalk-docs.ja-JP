---
title: 議題と優先度 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85274b0cbd59cd9272bb63030296d3f527e096a9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360417"
---
# <a name="agenda-and-priority"></a>議題と優先度
ビジネス ルール エンジンが規則を評価し、アクションを実行する方法については、概念を理解する必要があります。*議題*と*優先度*します。  
  
## <a name="agenda"></a>議題  
 議題は、キューの規則を実行するためのエンジンによって使用されるスケジュールです。 議題はエンジン インスタンスの場合は存在し、一連のポリシーではなく、1 つのポリシーで機能します。 ファクトが作業メモリにアサートされ、特定の規則の条件が満たされている、ルールが議題に配置し、優先順位に従って実行されます。 ルールのアクションが上から下に順番に実行され、議題の次のルールのアクションの実行後。  
  
 ルールに属するアクションは、次のルールに進む前にすべてのアクションが実行されるように、ブロックとして扱われます。 ルール ブロック内のすべてのアクションは、ブロック内の他のアクションに関係なく実行されます。 アサーションの詳細については、次を参照してください。[エンジン制御関数](../core/engine-control-functions.md)します。  
  
 次の例では、議題のしくみを示します。  
  
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
  
 ファクト Fact1 で、1 の値を持つ、エンジンにアサートします。 ルール 1 と Rule 2 の両方の条件が満たされているため、そのアクションを実行するため、両方のルールが議題に移動されます。  
  
|作業メモリ|議題|  
|--------------------|------------|  
|Fact1 (値 = 1)|**Rule1**<br /><br /> -Action1<br />-Action2<br /><br /> **Rule2**<br /><br /> -Action3<br />-Action4|  
  
## <a name="priority"></a>[Priority]  
 実行の優先度は、すべてのルールの場合は 0 の既定の優先順位で、個々 のルールに設定されています。 大きい数値が高い優先順位で、0 のどちら側の優先度の範囲します。 アクションは、最も高い優先度から最も低い優先順位の順序で実行されます。  
  
 次の例では、優先度がルールの実行の順序に影響する方法を示します。  
  
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
  
 両方のルール条件を満たしているが、Rule2 は高い優先順位があるため、最初に実行します。 最終的な割引は、10% は次の表に示すように、Rule1 に実行されるアクションの結果になるためです。  
  
|作業メモリ|議題|  
|--------------------|------------|  
|Fact1 (値 = 1)|**Rule2**<br /><br /> 割引の 15% を =<br /><br /> **Rule1**<br /><br /> 割引の 10% を =|  
  
## <a name="see-also"></a>参照  
 [ルール エンジン](../core/rule-engine.md)