---
title: ルールのアクションの副作用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rules Engine, side effects
ms.assetid: 1ef65014-9c0a-40d3-b941-2a67c20b54d3
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8cfcff7fed8a559c725d0180f89cdd0d385b1e0e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254616"
---
# <a name="rule-action-side-effects"></a>ルール アクションの副作用
アクションの実行に影響を与えるオブジェクトまたは条件で使用される用語の状態と、そのアクションをオブジェクトに対する副作用があると見なされます。  
  
 次の規則があると仮定します。  
  
## <a name="rule-1"></a>ルール 1  
  
```  
IF OrderForm.ItemCount > 100   
THEN OrderForm.Status = "important"  
```  
  
## <a name="rule-2"></a>Rule 2  
  
```  
IF OrderList.IsFromMember = true   
THEN OrderForm.UpdateStatus("important")  
```  
  
 この場合、 **OrderForm.UpdateStatus**副作用があると言います**OrderForm.Status**します。 意味ではない**OrderForm.UpdateStatus**側の効果があります。 代わりに、 **OrderForm.Status**は可能性のある 1 つまたは複数のアクションの影響をします。  
  
 既定では、 **SideEffects** .NET クラス メンバーのプロパティは**true**副作用のあるメンバーをキャッシュからルール エンジンを防ぐことができます。 この例では、ルール エンジンはキャッシュにない**OrderForm.Status** ; 作業メモリに代わりに、最新の値を取得**OrderForm.Status** Rule 1 が評価されるたびにします。 場合、 **SideEffects**プロパティに設定されて**false**、ルール エンジンが初めて評価の値をキャッシュ**OrderForm.Status**がの評価順行連鎖シナリオ)、キャッシュされた値が使用されます。  
  
 現在、ビジネス ルール作成ツールにユーザーを変更する方法を提供しない**SideEffects**、ただし、のみ設定できます、 **SideEffects**ビジネス ルール フレームワークを通じてプログラムでプロパティ. この設定を行いますを使用したバインド、 [ClassMemberBinding](https://msdn.microsoft.com/library/microsoft.ruleengine.classmemberbinding.aspx)クラス オブジェクトのメソッド、プロパティ、およびルールの条件とアクションで使用されるフィールドを指定します。 **ClassMemberBinding**プロパティ、 [SideEffects](https://msdn.microsoft.com/library/microsoft.ruleengine.classmemberbinding.sideeffects.aspx#P:Microsoft.RuleEngine.ClassMemberBinding.SideEffects)、その値を変更、メンバーにアクセスするかどうかを示すブール値を含むです。  
  
## <a name="see-also"></a>参照  
 [ルール エンジン](../core/rule-engine.md)