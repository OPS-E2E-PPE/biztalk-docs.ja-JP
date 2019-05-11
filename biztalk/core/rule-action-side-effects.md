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
# <a name="rule-action-side-effects"></a><span data-ttu-id="f379d-102">ルール アクションの副作用</span><span class="sxs-lookup"><span data-stu-id="f379d-102">Rule Action Side Effects</span></span>
<span data-ttu-id="f379d-103">アクションの実行に影響を与えるオブジェクトまたは条件で使用される用語の状態と、そのアクションをオブジェクトに対する副作用があると見なされます。</span><span class="sxs-lookup"><span data-stu-id="f379d-103">If the execution of an action affects the state of an object or a term used in conditions, that action is considered to have a side effect on the object.</span></span>  
  
 <span data-ttu-id="f379d-104">次の規則があると仮定します。</span><span class="sxs-lookup"><span data-stu-id="f379d-104">Assume we have the following rules.</span></span>  
  
## <a name="rule-1"></a><span data-ttu-id="f379d-105">ルール 1</span><span class="sxs-lookup"><span data-stu-id="f379d-105">Rule 1</span></span>  
  
```  
IF OrderForm.ItemCount > 100   
THEN OrderForm.Status = "important"  
```  
  
## <a name="rule-2"></a><span data-ttu-id="f379d-106">Rule 2</span><span class="sxs-lookup"><span data-stu-id="f379d-106">Rule 2</span></span>  
  
```  
IF OrderList.IsFromMember = true   
THEN OrderForm.UpdateStatus("important")  
```  
  
 <span data-ttu-id="f379d-107">この場合、 **OrderForm.UpdateStatus**副作用があると言います**OrderForm.Status**します。</span><span class="sxs-lookup"><span data-stu-id="f379d-107">In this case, **OrderForm.UpdateStatus** is said to have a side effect on **OrderForm.Status**.</span></span> <span data-ttu-id="f379d-108">意味ではない**OrderForm.UpdateStatus**側の効果があります。 代わりに、 **OrderForm.Status**は可能性のある 1 つまたは複数のアクションの影響をします。</span><span class="sxs-lookup"><span data-stu-id="f379d-108">This does not mean that **OrderForm.UpdateStatus** has side effects; instead, **OrderForm.Status** is potentially affected by one or more actions.</span></span>  
  
 <span data-ttu-id="f379d-109">既定では、 **SideEffects** .NET クラス メンバーのプロパティは**true**副作用のあるメンバーをキャッシュからルール エンジンを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="f379d-109">By default, the **SideEffects** property for .NET class members is **true**, which prevents the rule engine from caching the member with side effects.</span></span> <span data-ttu-id="f379d-110">この例では、ルール エンジンはキャッシュにない**OrderForm.Status** ; 作業メモリに代わりに、最新の値を取得**OrderForm.Status** Rule 1 が評価されるたびにします。</span><span class="sxs-lookup"><span data-stu-id="f379d-110">In our example, the rule engine does not cache **OrderForm.Status** in the working memory; instead it gets the most up-to-date value of **OrderForm.Status** every time Rule 1 is evaluated.</span></span> <span data-ttu-id="f379d-111">場合、 **SideEffects**プロパティに設定されて**false**、ルール エンジンが初めて評価の値をキャッシュ**OrderForm.Status**がの評価順行連鎖シナリオ)、キャッシュされた値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f379d-111">If the **SideEffects** property is set to **false**, the rule engine caches the value first time it evaluates **OrderForm.Status**, but for later evaluations (in forward-chaining scenarios), it uses the cached value.</span></span>  
  
 <span data-ttu-id="f379d-112">現在、ビジネス ルール作成ツールにユーザーを変更する方法を提供しない**SideEffects**、ただし、のみ設定できます、 **SideEffects**ビジネス ルール フレームワークを通じてプログラムでプロパティ.</span><span class="sxs-lookup"><span data-stu-id="f379d-112">Currently the Business Rule Composer does not provide a way for users to modify **SideEffects**, however, you can only set the **SideEffects** property programmatically through the Business Rules Framework.</span></span> <span data-ttu-id="f379d-113">この設定を行いますを使用したバインド、 [ClassMemberBinding](https://msdn.microsoft.com/library/microsoft.ruleengine.classmemberbinding.aspx)クラス オブジェクトのメソッド、プロパティ、およびルールの条件とアクションで使用されるフィールドを指定します。</span><span class="sxs-lookup"><span data-stu-id="f379d-113">You set do this at binding, using the [ClassMemberBinding](https://msdn.microsoft.com/library/microsoft.ruleengine.classmemberbinding.aspx) class to specify object methods, properties, and fields used in rule conditions and actions.</span></span> <span data-ttu-id="f379d-114">**ClassMemberBinding**プロパティ、 [SideEffects](https://msdn.microsoft.com/library/microsoft.ruleengine.classmemberbinding.sideeffects.aspx#P:Microsoft.RuleEngine.ClassMemberBinding.SideEffects)、その値を変更、メンバーにアクセスするかどうかを示すブール値を含むです。</span><span class="sxs-lookup"><span data-stu-id="f379d-114">**ClassMemberBinding** has a property, [SideEffects](https://msdn.microsoft.com/library/microsoft.ruleengine.classmemberbinding.sideeffects.aspx#P:Microsoft.RuleEngine.ClassMemberBinding.SideEffects), which contains a Boolean value indicating whether accessing the member changes its value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f379d-115">参照</span><span class="sxs-lookup"><span data-stu-id="f379d-115">See Also</span></span>  
 [<span data-ttu-id="f379d-116">ルール エンジン</span><span class="sxs-lookup"><span data-stu-id="f379d-116">Rule Engine</span></span>](../core/rule-engine.md)