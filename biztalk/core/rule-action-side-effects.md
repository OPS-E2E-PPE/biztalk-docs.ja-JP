---
title: "ルールのアクションの副作用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Business Rules Engine, side effects
ms.assetid: 1ef65014-9c0a-40d3-b941-2a67c20b54d3
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2ed890ca8efca6fdd1403c4ec89f4c0c5d32eaa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="rule-action-side-effects"></a>ルール アクションの副作用
アクションを実行するとオブジェクトの状態、または条件で使用される期間に影響を与える場合、そのアクションは、オブジェクトに対する副作用があると見なされます。  
  
 次の規則があると仮定します。  
  
## <a name="rule-1"></a>ルール 1  
  
```  
IF OrderForm.ItemCount > 100   
THEN OrderForm.Status = "important"  
```  
  
## <a name="rule-2"></a>規則 2  
  
```  
IF OrderList.IsFromMember = true   
THEN OrderForm.UpdateStatus("important")  
```  
  
 この場合、 **OrderForm.UpdateStatus**に副作用があるといいます**OrderForm.Status**です。 限りませんを**OrderForm.UpdateStatus**側の効果があります。 代わりに、 **OrderForm.Status** 1 つまたは複数のアクションの影響を受ける可能性があります。  
  
 既定では、 **SideEffects** .NET クラス メンバーのプロパティが**true**副作用のあるメンバーをキャッシュからルール エンジンを防ぐことができます。 この例では、ルール エンジンがキャッシュしていない**OrderForm.Status** ; 作業メモリに代わりに、最新の値を取得**OrderForm.Status**ルール 1 が評価されるたびにします。 場合、 **SideEffects**プロパティに設定されている**false**、ルール エンジンの値を評価して初めてキャッシュ**OrderForm.Status**がそれ以降の評価順行連鎖シナリオ)、キャッシュされた値が使用されます。  
  
 ビジネス ルール作成ツールにユーザーを変更するための手段が用意されていません現在**SideEffects**、ただし、のみ設定できます、 **SideEffects**ビジネス ルール フレームワークを通じてプログラムによってプロパティ. この設定を行いますを使用したバインディング、 [ClassMemberBinding](https://msdn.microsoft.com/library/microsoft.ruleengine.classmemberbinding.aspx)クラス オブジェクトのメソッド、プロパティ、およびルール条件およびアクションで使用されるフィールドを指定します。 **ClassMemberBinding**プロパティが含まれる、 [SideEffects](https://msdn.microsoft.com/library/microsoft.ruleengine.classmemberbinding.sideeffects.aspx#P:Microsoft.RuleEngine.ClassMemberBinding.SideEffects)、その値を変更、メンバーにアクセスするかどうかを示すブール値が含まれています。  
  
## <a name="see-also"></a>参照  
 [ルール エンジン](../core/rule-engine.md)