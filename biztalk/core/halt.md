---
title: "停止 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Halt function [Business Rules Engine]
ms.assetid: 468ba6dd-2bb2-4787-a824-1f5455508efd
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07ca8091d4ff4405704314d72939758c7600a71a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="halt"></a>停止
使用することができます、**停止**ルール エンジンの現在の実行を停止するように機能します。 **停止**関数型のパラメーターを 1 つ取ります`Boolean`です。 パラメーターの値を `true` に指定すると、ルール エンジンは保留候補ルールを含む議題もクリアします。  
  
 **Policy.Execute**メソッドがラップするラッパーでは基本的に、 **RuleEngine.Execute**メソッドです。 これは、次のようなコードになります。  
  
```  
RuleEngine.Assert(facts);   
RuleEngine.Execute();   
RuleEngine.Retract(facts);  
```  
  
 使用する場合、 **Policy.Execute** 、ポリシーをルール エンジンを実行するメソッドに制御が戻ります、 **Policy.Execute**メソッドと、**停止**関数を実行します。 **Policy.Execute**メソッドはファクトを取り消して、呼び出し元にコントロールを返します。 したがって、この場合停止したポリシーの実行は再開できません。 同じ処理を使用するときの動作、**ルールの呼び出し**図形をポリシーを呼び出します。  
  
 ただし、使用する場合、 **RuleEngine.Execute**メソッドだけ呼び出すことによって、次のルールの実行を待機中、停止したポリシーの実行を再開する、ポリシーを実行するには、直接**RuleEngine.Execute**もう一度 (2 つの呼び出しの間に必要なオブジェクトを取り消していない) 提供します。 停止したポリシーの実行を再開するコード例を次に示します。  
  
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
  
 なお、 **Policy.Execute**メソッドは、パフォーマンス向上のためのルール エンジンのインスタンスをキャッシュします。 使用すると、 **RuleEngine.Execute**メソッドを直接、ルール エンジンのインスタンスはキャッシュされません。  
  
## <a name="see-also"></a>参照  
 [エンジン制御関数](../core/engine-control-functions.md)