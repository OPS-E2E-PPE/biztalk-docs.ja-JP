---
title: "例外処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 00a9125c-7c7c-4d2a-ae04-c923cd89683c
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 520f4eb47fb98bf497753a8348031f7c2ab93d29
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="exception-handling"></a>例外処理
**RuleEngine**クラスには、プロパティ**CompensationHandlerInfo**をさらに 2 つのプロパティを持つ: **CompensationHandler**と**UserData**. **CompensationHandler**プロパティの型は**RuleEngineCompensationHandler**、および**UserData**プロパティの型は**オブジェクト**. 定義、 **RuleEngineCompensationHandler**のとおりです。  
  
```  
public delegate bool RuleEngineCompensationHandler(  
   Exception ex,  
   object userData  
);  
```  
  
 ルール エンジン コンシューマーを使用して、ハンドラーと、ルール エンジンにユーザー データを指定する、 **CompensationHandlerInfo**のプロパティ、 **RuleEngine**クラスです。 ハンドラーとして同じシグネチャを持つ必要があります、 **RuleEngineCompensationHandler**を委任します。 ランタイム例外が発生した場合、ルール エンジンは指定されたハンドラーを呼び出し、例外と定義済みのユーザー データをパラメーターとして渡します。 このハンドラーから `true` が返された場合、ルール エンジンは処理を続行します。 それ以外の場合、ルール エンジンは処理を中止し、発生した例外と共に制御をユーザーに返します。 使用して、ポリシーを呼び出す場合のみに、この例外処理機構を使用することがわかります、 **RuleEngine.Execute**メソッドです。  
  
 使用する場合、 **Policy.Execute**ポリシーを実行するメソッドを try-catch ブロックを使用して、ポリシーの実行中に、ルール エンジンによって生成される例外をキャッチする必要があります。  
  
 使用する場合、**ルールの呼び出し**図形に、ポリシーの実行を使用して、**例外のキャッチ**のブロック、**スコープ**図形の実行中に、ルール エンジンによって発生した例外をキャッチするにはポリシー。  
  
## <a name="see-also"></a>参照  
 [例外のキャッチ ブロックを追加する方法](../core/how-to-add-a-catch-exception-block3.md)