---
title: 例外処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00a9125c-7c7c-4d2a-ae04-c923cd89683c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 235e49aedf477088e8524b7d6aa7a1a9f5f243ba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346033"
---
# <a name="exception-handling"></a>例外処理
**RuleEngine**クラスには、プロパティ**CompensationHandlerInfo**、さらには 2 つのプロパティ。**CompensationHandler**と**UserData**します。 **CompensationHandler**プロパティの型は**RuleEngineCompensationHandler**、および**UserData**プロパティの型は**オブジェクト**. 定義、 **RuleEngineCompensationHandler**のとおりです。  
  
```  
public delegate bool RuleEngineCompensationHandler(  
   Exception ex,  
   object userData  
);  
```  
  
 ルール エンジン コンシューマーを使用して、ハンドラーと、ルール エンジンのユーザー データを指定する、 **CompensationHandlerInfo**のプロパティ、 **RuleEngine**クラス。 ハンドラーとして同じシグネチャを持つ必要があります、 **RuleEngineCompensationHandler**を委任します。 実行時例外がある場合、エンジンは、ハンドラーが呼び出されます、例外と定義済みのユーザー データをパラメーターとして、ハンドラーに渡されます。 ハンドラーが戻った場合`true`、ルール エンジンは、引き続き処理されます。 それ以外の場合、ルール エンジンは、処理を中止し、元の例外でユーザーに返します。 使用してポリシーを呼び出す場合にのみ、この例外処理メカニズムを使用することができます、ご覧のとおり、 **RuleEngine.Execute**メソッド。  
  
 使用する場合、 **Policy.Execute**ポリシーを実行するメソッドは、try-catch ブロックを使用して、ポリシーの実行中に、ルール エンジンによって生成される例外をキャッチする必要があります。  
  
 使用する場合、**ルールの呼び出し**ポリシーを実行するを使用して、図形、**例外のキャッチ**のブロック、**スコープ**図形の実行中に、ルール エンジンによって発生した例外をキャッチするにはポリシー。  
  
## <a name="see-also"></a>参照  
 [例外のキャッチ ブロックを追加する方法](../core/how-to-add-a-catch-exception-block3.md)