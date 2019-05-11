---
title: 停止 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Halt function [Business Rules Engine]
ms.assetid: 468ba6dd-2bb2-4787-a824-1f5455508efd
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dcc7006581b3ccbf856d48d365cf6b003d97ec93
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344788"
---
# <a name="halt"></a>停止
使用することができます、 **Halt**関数を現在のルール エンジン実行を停止します。 **Halt**関数は 1 つのパラメーター型の`Boolean`します。 パラメーターの値を指定する場合`true`、ルール エンジンは保留候補ルールを含む議題もクリアします。  
  
 **Policy.Execute**メソッドは、ラッパーでは基本的に、 **RuleEngine.Execute**メソッド。 次のコードのようなコードがあります。  
  
```  
RuleEngine.Assert(facts);   
RuleEngine.Execute();   
RuleEngine.Retract(facts);  
```  
  
 使用する場合、 **Policy.Execute**ポリシー、ルール エンジンを実行するメソッドに制御が戻ります、 **Policy.Execute**メソッドと、 **Halt**関数を実行します。 **Policy.Execute**メソッドはファクトを取り消して、呼び出し元にコントロールを返します。 そのため、ここで、停止したポリシーの実行を再開できません。 同じ処理を使用するときの動作、**ルールの呼び出し**図形にポリシーを呼び出します。  
  
 ただし、使用する場合、 **RuleEngine.Execute**メソッド呼び出すだけで、次のルールの実行を待機中、停止したポリシーの実行を再開する、ポリシーを実行するには、直接**RuleEngine.Execute**もう一度 (指定された 2 つの呼び出しの間に必要なオブジェクトを取り消していない)。 停止したポリシーの実行を再開するためのサンプル コードは次のとおりです。  
  
```  
//assert facts into working memory of the rule engine instance  
RuleEngine.Assert(facts);   
//execute the policy  
RuleEngine.Execute();   
//policy invokes the Halt method when executing actions.   
//control is returned to here when the Halt method is invoked  
  
//when engine is halted do the following  
//Add your code here  
  
//To resume the halted rule engine execution  
RuleEngine.Execute();  
//retract or remove facts frm the working memory of the rule engine  
RuleEngine.Retract(facts);  
```  
  
 なお、 **Policy.Execute**メソッドはパフォーマンス向上のためのルール エンジンのインスタンスをキャッシュします。 使用すると、 **RuleEngine.Execute**メソッドを直接、ルール エンジン インスタンスはキャッシュされません。  
  
## <a name="see-also"></a>参照  
 [エンジン制御関数](../core/engine-control-functions.md)