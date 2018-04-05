---
title: ルールのアクションの副作用 |Microsoft ドキュメント
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
ms.openlocfilehash: d2ed890ca8efca6fdd1403c4ec89f4c0c5d32eaa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="rule-action-side-effects"></a><span data-ttu-id="71194-102">ルール アクションの副作用</span><span class="sxs-lookup"><span data-stu-id="71194-102">Rule Action Side Effects</span></span>
<span data-ttu-id="71194-103">アクションを実行するとオブジェクトの状態、または条件で使用される期間に影響を与える場合、そのアクションは、オブジェクトに対する副作用があると見なされます。</span><span class="sxs-lookup"><span data-stu-id="71194-103">If the execution of an action affects the state of an object or a term used in conditions, that action is considered to have a side effect on the object.</span></span>  
  
 <span data-ttu-id="71194-104">次の規則があると仮定します。</span><span class="sxs-lookup"><span data-stu-id="71194-104">Assume we have the following rules.</span></span>  
  
## <a name="rule-1"></a><span data-ttu-id="71194-105">ルール 1</span><span class="sxs-lookup"><span data-stu-id="71194-105">Rule 1</span></span>  
  
```  
IF OrderForm.ItemCount > 100   
THEN OrderForm.Status = "important"  
```  
  
## <a name="rule-2"></a><span data-ttu-id="71194-106">規則 2</span><span class="sxs-lookup"><span data-stu-id="71194-106">Rule 2</span></span>  
  
```  
IF OrderList.IsFromMember = true   
THEN OrderForm.UpdateStatus("important")  
```  
  
 <span data-ttu-id="71194-107">この場合、 **OrderForm.UpdateStatus**に副作用があるといいます**OrderForm.Status**です。</span><span class="sxs-lookup"><span data-stu-id="71194-107">In this case, **OrderForm.UpdateStatus** is said to have a side effect on **OrderForm.Status**.</span></span> <span data-ttu-id="71194-108">限りませんを**OrderForm.UpdateStatus**側の効果があります。 代わりに、 **OrderForm.Status** 1 つまたは複数のアクションの影響を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="71194-108">This does not mean that **OrderForm.UpdateStatus** has side effects; instead, **OrderForm.Status** is potentially affected by one or more actions.</span></span>  
  
 <span data-ttu-id="71194-109">既定では、 **SideEffects** .NET クラス メンバーのプロパティが**true**副作用のあるメンバーをキャッシュからルール エンジンを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="71194-109">By default, the **SideEffects** property for .NET class members is **true**, which prevents the rule engine from caching the member with side effects.</span></span> <span data-ttu-id="71194-110">この例では、ルール エンジンがキャッシュしていない**OrderForm.Status** ; 作業メモリに代わりに、最新の値を取得**OrderForm.Status**ルール 1 が評価されるたびにします。</span><span class="sxs-lookup"><span data-stu-id="71194-110">In our example, the rule engine does not cache **OrderForm.Status** in the working memory; instead it gets the most up-to-date value of **OrderForm.Status** every time Rule 1 is evaluated.</span></span> <span data-ttu-id="71194-111">場合、 **SideEffects**プロパティに設定されている**false**、ルール エンジンの値を評価して初めてキャッシュ**OrderForm.Status**がそれ以降の評価順行連鎖シナリオ)、キャッシュされた値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="71194-111">If the **SideEffects** property is set to **false**, the rule engine caches the value first time it evaluates **OrderForm.Status**, but for later evaluations (in forward-chaining scenarios), it uses the cached value.</span></span>  
  
 <span data-ttu-id="71194-112">ビジネス ルール作成ツールにユーザーを変更するための手段が用意されていません現在**SideEffects**、ただし、のみ設定できます、 **SideEffects**ビジネス ルール フレームワークを通じてプログラムによってプロパティ.</span><span class="sxs-lookup"><span data-stu-id="71194-112">Currently the Business Rule Composer does not provide a way for users to modify **SideEffects**, however, you can only set the **SideEffects** property programmatically through the Business Rules Framework.</span></span> <span data-ttu-id="71194-113">この設定を行いますを使用したバインディング、 [ClassMemberBinding](https://msdn.microsoft.com/library/microsoft.ruleengine.classmemberbinding.aspx)クラス オブジェクトのメソッド、プロパティ、およびルール条件およびアクションで使用されるフィールドを指定します。</span><span class="sxs-lookup"><span data-stu-id="71194-113">You set do this at binding, using the [ClassMemberBinding](https://msdn.microsoft.com/library/microsoft.ruleengine.classmemberbinding.aspx) class to specify object methods, properties, and fields used in rule conditions and actions.</span></span> <span data-ttu-id="71194-114">**ClassMemberBinding**プロパティが含まれる、 [SideEffects](https://msdn.microsoft.com/library/microsoft.ruleengine.classmemberbinding.sideeffects.aspx#P:Microsoft.RuleEngine.ClassMemberBinding.SideEffects)、その値を変更、メンバーにアクセスするかどうかを示すブール値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="71194-114">**ClassMemberBinding** has a property, [SideEffects](https://msdn.microsoft.com/library/microsoft.ruleengine.classmemberbinding.sideeffects.aspx#P:Microsoft.RuleEngine.ClassMemberBinding.SideEffects), which contains a Boolean value indicating whether accessing the member changes its value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71194-115">参照</span><span class="sxs-lookup"><span data-stu-id="71194-115">See Also</span></span>  
 [<span data-ttu-id="71194-116">ルール エンジン</span><span class="sxs-lookup"><span data-stu-id="71194-116">Rule Engine</span></span>](../core/rule-engine.md)