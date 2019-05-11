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
# <a name="agenda-and-priority"></a><span data-ttu-id="ae615-102">議題と優先度</span><span class="sxs-lookup"><span data-stu-id="ae615-102">Agenda and Priority</span></span>
<span data-ttu-id="ae615-103">ビジネス ルール エンジンが規則を評価し、アクションを実行する方法については、概念を理解する必要があります。*議題*と*優先度*します。</span><span class="sxs-lookup"><span data-stu-id="ae615-103">To understand how the Business Rule engine evaluates rules and executes actions, you need to understand the concepts of *agenda* and *priority*.</span></span>  
  
## <a name="agenda"></a><span data-ttu-id="ae615-104">議題</span><span class="sxs-lookup"><span data-stu-id="ae615-104">Agenda</span></span>  
 <span data-ttu-id="ae615-105">議題は、キューの規則を実行するためのエンジンによって使用されるスケジュールです。</span><span class="sxs-lookup"><span data-stu-id="ae615-105">The agenda is a schedule used by the engine to queue rules for execution.</span></span> <span data-ttu-id="ae615-106">議題はエンジン インスタンスの場合は存在し、一連のポリシーではなく、1 つのポリシーで機能します。</span><span class="sxs-lookup"><span data-stu-id="ae615-106">The agenda exists for an engine instance, and acts on a single policy, not on a series of policies.</span></span> <span data-ttu-id="ae615-107">ファクトが作業メモリにアサートされ、特定の規則の条件が満たされている、ルールが議題に配置し、優先順位に従って実行されます。</span><span class="sxs-lookup"><span data-stu-id="ae615-107">When a fact is asserted into working memory and the conditions of a given rule are satisfied, the rule is placed on the agenda and executed according to priority.</span></span> <span data-ttu-id="ae615-108">ルールのアクションが上から下に順番に実行され、議題の次のルールのアクションの実行後。</span><span class="sxs-lookup"><span data-stu-id="ae615-108">A rule's actions are executed in order from top to bottom, and then the actions of the next rule on the agenda are executed.</span></span>  
  
 <span data-ttu-id="ae615-109">ルールに属するアクションは、次のルールに進む前にすべてのアクションが実行されるように、ブロックとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="ae615-109">The actions belonging to a rule are treated as a block, so that all actions are executed before moving on to the next rule.</span></span> <span data-ttu-id="ae615-110">ルール ブロック内のすべてのアクションは、ブロック内の他のアクションに関係なく実行されます。</span><span class="sxs-lookup"><span data-stu-id="ae615-110">All actions in a rule block will execute regardless of other actions in the block.</span></span> <span data-ttu-id="ae615-111">アサーションの詳細については、次を参照してください。[エンジン制御関数](../core/engine-control-functions.md)します。</span><span class="sxs-lookup"><span data-stu-id="ae615-111">For more information about assertion, see [Engine Control Functions](../core/engine-control-functions.md).</span></span>  
  
 <span data-ttu-id="ae615-112">次の例では、議題のしくみを示します。</span><span class="sxs-lookup"><span data-stu-id="ae615-112">The following example demonstrates how the agenda works.</span></span>  
  
 <span data-ttu-id="ae615-113">**Rule1**</span><span class="sxs-lookup"><span data-stu-id="ae615-113">**Rule1**</span></span>  
  
```  
IF  
Fact1 == 1  
THEN  
Action1  
Action2  
```  
  
 <span data-ttu-id="ae615-114">**Rule2**</span><span class="sxs-lookup"><span data-stu-id="ae615-114">**Rule2**</span></span>  
  
```  
IF  
Fact1 > 0  
THEN  
Action3  
Action4  
```  
  
 <span data-ttu-id="ae615-115">ファクト Fact1 で、1 の値を持つ、エンジンにアサートします。</span><span class="sxs-lookup"><span data-stu-id="ae615-115">We assert the fact Fact1, which has a value of 1, into the engine.</span></span> <span data-ttu-id="ae615-116">ルール 1 と Rule 2 の両方の条件が満たされているため、そのアクションを実行するため、両方のルールが議題に移動されます。</span><span class="sxs-lookup"><span data-stu-id="ae615-116">Because the conditions of both Rule 1 and Rule 2 are satisfied, both rules are moved to the agenda for execution of their actions.</span></span>  
  
|<span data-ttu-id="ae615-117">作業メモリ</span><span class="sxs-lookup"><span data-stu-id="ae615-117">Working memory</span></span>|<span data-ttu-id="ae615-118">議題</span><span class="sxs-lookup"><span data-stu-id="ae615-118">Agenda</span></span>|  
|--------------------|------------|  
|<span data-ttu-id="ae615-119">Fact1 (値 = 1)</span><span class="sxs-lookup"><span data-stu-id="ae615-119">Fact1 (value=1)</span></span>|<span data-ttu-id="ae615-120">**Rule1**</span><span class="sxs-lookup"><span data-stu-id="ae615-120">**Rule1**</span></span><br /><br /> <span data-ttu-id="ae615-121">-Action1</span><span class="sxs-lookup"><span data-stu-id="ae615-121">-   Action1</span></span><br /><span data-ttu-id="ae615-122">-Action2</span><span class="sxs-lookup"><span data-stu-id="ae615-122">-   Action2</span></span><br /><br /> <span data-ttu-id="ae615-123">**Rule2**</span><span class="sxs-lookup"><span data-stu-id="ae615-123">**Rule2**</span></span><br /><br /> <span data-ttu-id="ae615-124">-Action3</span><span class="sxs-lookup"><span data-stu-id="ae615-124">-   Action3</span></span><br /><span data-ttu-id="ae615-125">-Action4</span><span class="sxs-lookup"><span data-stu-id="ae615-125">-   Action4</span></span>|  
  
## <a name="priority"></a><span data-ttu-id="ae615-126">[Priority]</span><span class="sxs-lookup"><span data-stu-id="ae615-126">Priority</span></span>  
 <span data-ttu-id="ae615-127">実行の優先度は、すべてのルールの場合は 0 の既定の優先順位で、個々 のルールに設定されています。</span><span class="sxs-lookup"><span data-stu-id="ae615-127">Priority for execution is set on each individual rule, with a default priority of 0 for all rules.</span></span> <span data-ttu-id="ae615-128">大きい数値が高い優先順位で、0 のどちら側の優先度の範囲します。</span><span class="sxs-lookup"><span data-stu-id="ae615-128">The priority can range on either side of 0, with larger numbers having higher priority.</span></span> <span data-ttu-id="ae615-129">アクションは、最も高い優先度から最も低い優先順位の順序で実行されます。</span><span class="sxs-lookup"><span data-stu-id="ae615-129">Actions are executed in order from highest priority to lowest priority.</span></span>  
  
 <span data-ttu-id="ae615-130">次の例では、優先度がルールの実行の順序に影響する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ae615-130">The following example shows how priority affects the order of execution for the rules.</span></span>  
  
 <span data-ttu-id="ae615-131">**Rule1 (優先度 = 0)**</span><span class="sxs-lookup"><span data-stu-id="ae615-131">**Rule1 (priority = 0)**</span></span>  
  
```  
IF  
Fact1 == 1  
THEN  
Discount = 10%  
```  
  
 <span data-ttu-id="ae615-132">**Rule2 (優先度 = 10)**</span><span class="sxs-lookup"><span data-stu-id="ae615-132">**Rule2 (priority = 10)**</span></span>  
  
```  
IF  
Fact1 > 0  
THEN  
Discount = 15%  
```  
  
 <span data-ttu-id="ae615-133">両方のルール条件を満たしているが、Rule2 は高い優先順位があるため、最初に実行します。</span><span class="sxs-lookup"><span data-stu-id="ae615-133">The conditions for both rules have been met, but Rule2 is executed first because it has higher priority.</span></span> <span data-ttu-id="ae615-134">最終的な割引は、10% は次の表に示すように、Rule1 に実行されるアクションの結果になるためです。</span><span class="sxs-lookup"><span data-stu-id="ae615-134">The final discount is 10 percent, because it is the result of the action executed for Rule1, as shown in the following table.</span></span>  
  
|<span data-ttu-id="ae615-135">作業メモリ</span><span class="sxs-lookup"><span data-stu-id="ae615-135">Working memory</span></span>|<span data-ttu-id="ae615-136">議題</span><span class="sxs-lookup"><span data-stu-id="ae615-136">Agenda</span></span>|  
|--------------------|------------|  
|<span data-ttu-id="ae615-137">Fact1 (値 = 1)</span><span class="sxs-lookup"><span data-stu-id="ae615-137">Fact1 (value=1)</span></span>|<span data-ttu-id="ae615-138">**Rule2**</span><span class="sxs-lookup"><span data-stu-id="ae615-138">**Rule2**</span></span><br /><br /> <span data-ttu-id="ae615-139">割引の 15% を =</span><span class="sxs-lookup"><span data-stu-id="ae615-139">Discount = 15%</span></span><br /><br /> <span data-ttu-id="ae615-140">**Rule1**</span><span class="sxs-lookup"><span data-stu-id="ae615-140">**Rule1**</span></span><br /><br /> <span data-ttu-id="ae615-141">割引の 10% を =</span><span class="sxs-lookup"><span data-stu-id="ae615-141">Discount = 10%</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ae615-142">参照</span><span class="sxs-lookup"><span data-stu-id="ae615-142">See Also</span></span>  
 [<span data-ttu-id="ae615-143">ルール エンジン</span><span class="sxs-lookup"><span data-stu-id="ae615-143">Rule Engine</span></span>](../core/rule-engine.md)