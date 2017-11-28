---
title: "議題と優先度 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4529753251c2bf7934616b91662bde836c8339e1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="agenda-and-priority"></a><span data-ttu-id="0365b-102">議題と優先度</span><span class="sxs-lookup"><span data-stu-id="0365b-102">Agenda and Priority</span></span>
<span data-ttu-id="0365b-103">ビジネス ルール エンジンの規則を評価し、アクションが実行を理解するのには、概念を理解する必要があります*議題*と*優先度*です。</span><span class="sxs-lookup"><span data-stu-id="0365b-103">To understand how the Business Rule engine evaluates rules and executes actions, you need to understand the concepts of *agenda* and *priority*.</span></span>  
  
## <a name="agenda"></a><span data-ttu-id="0365b-104">議題</span><span class="sxs-lookup"><span data-stu-id="0365b-104">Agenda</span></span>  
 <span data-ttu-id="0365b-105">議題は、実行するルールをキューに入れるためにエンジンが使用するスケジュールです。</span><span class="sxs-lookup"><span data-stu-id="0365b-105">The agenda is a schedule used by the engine to queue rules for execution.</span></span> <span data-ttu-id="0365b-106">議題はエンジンのインスタンスに存在し、一連のポリシーではなく 1 つのポリシーに作用します。</span><span class="sxs-lookup"><span data-stu-id="0365b-106">The agenda exists for an engine instance, and acts on a single policy, not on a series of policies.</span></span> <span data-ttu-id="0365b-107">ファクトが作業メモリにアサートされ、特定のルールの条件が満たされると、議題にルールが配置され、優先度に従って実行されます。</span><span class="sxs-lookup"><span data-stu-id="0365b-107">When a fact is asserted into working memory and the conditions of a given rule are satisfied, the rule is placed on the agenda and executed according to priority.</span></span> <span data-ttu-id="0365b-108">ルールのアクションが上から下へと順に実行されたら、議題の次のルールのアクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="0365b-108">A rule's actions are executed in order from top to bottom, and then the actions of the next rule on the agenda are executed.</span></span>  
  
 <span data-ttu-id="0365b-109">ルールに属するアクションはブロックとして扱われるので、すべてのアクションが実行されてから次のルールに移行します。</span><span class="sxs-lookup"><span data-stu-id="0365b-109">The actions belonging to a rule are treated as a block, so that all actions are executed before moving on to the next rule.</span></span> <span data-ttu-id="0365b-110">ルール ブロック内のアクションはすべて、ブロック内の他のアクションとは無関係に実行されます。</span><span class="sxs-lookup"><span data-stu-id="0365b-110">All actions in a rule block will execute regardless of other actions in the block.</span></span> <span data-ttu-id="0365b-111">アサーションの詳細については、次を参照してください。[エンジンの制御関数](../core/engine-control-functions.md)です。</span><span class="sxs-lookup"><span data-stu-id="0365b-111">For more information about assertion, see [Engine Control Functions](../core/engine-control-functions.md).</span></span>  
  
 <span data-ttu-id="0365b-112">議題の使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0365b-112">The following example demonstrates how the agenda works.</span></span>  
  
 <span data-ttu-id="0365b-113">**Rule1**</span><span class="sxs-lookup"><span data-stu-id="0365b-113">**Rule1**</span></span>  
  
```  
IF  
Fact1 == 1  
THEN  
Action1  
Action2  
```  
  
 <span data-ttu-id="0365b-114">**Rule2**</span><span class="sxs-lookup"><span data-stu-id="0365b-114">**Rule2**</span></span>  
  
```  
IF  
Fact1 > 0  
THEN  
Action3  
Action4  
```  
  
 <span data-ttu-id="0365b-115">値が 1 のファクト Fact1 をエンジンにアサートします。</span><span class="sxs-lookup"><span data-stu-id="0365b-115">We assert the fact Fact1, which has a value of 1, into the engine.</span></span> <span data-ttu-id="0365b-116">Rule1 と Rule2 の両方の条件が満たされているため、両方のルールがアクションを実行するために議題に移動します。</span><span class="sxs-lookup"><span data-stu-id="0365b-116">Because the conditions of both Rule 1 and Rule 2 are satisfied, both rules are moved to the agenda for execution of their actions.</span></span>  
  
|<span data-ttu-id="0365b-117">作業メモリ</span><span class="sxs-lookup"><span data-stu-id="0365b-117">Working memory</span></span>|<span data-ttu-id="0365b-118">議題</span><span class="sxs-lookup"><span data-stu-id="0365b-118">Agenda</span></span>|  
|--------------------|------------|  
|<span data-ttu-id="0365b-119">Fact1 (値 = 1)</span><span class="sxs-lookup"><span data-stu-id="0365b-119">Fact1 (value=1)</span></span>|<span data-ttu-id="0365b-120">**Rule1**</span><span class="sxs-lookup"><span data-stu-id="0365b-120">**Rule1**</span></span><br /><br /> <span data-ttu-id="0365b-121">-アクション 1</span><span class="sxs-lookup"><span data-stu-id="0365b-121">-   Action1</span></span><br /><span data-ttu-id="0365b-122">-Action2</span><span class="sxs-lookup"><span data-stu-id="0365b-122">-   Action2</span></span><br /><br /> <span data-ttu-id="0365b-123">**Rule2**</span><span class="sxs-lookup"><span data-stu-id="0365b-123">**Rule2**</span></span><br /><br /> <span data-ttu-id="0365b-124">-Action3</span><span class="sxs-lookup"><span data-stu-id="0365b-124">-   Action3</span></span><br /><span data-ttu-id="0365b-125">-Action4</span><span class="sxs-lookup"><span data-stu-id="0365b-125">-   Action4</span></span>|  
  
## <a name="priority"></a><span data-ttu-id="0365b-126">[Priority]</span><span class="sxs-lookup"><span data-stu-id="0365b-126">Priority</span></span>  
 <span data-ttu-id="0365b-127">実行の優先度は個々のルールに設定され、既定の優先度はすべてのルールで 0 です。</span><span class="sxs-lookup"><span data-stu-id="0365b-127">Priority for execution is set on each individual rule, with a default priority of 0 for all rules.</span></span> <span data-ttu-id="0365b-128">優先度の範囲は正と負のどちらも可能で、大きい数値が高い優先度となります。</span><span class="sxs-lookup"><span data-stu-id="0365b-128">The priority can range on either side of 0, with larger numbers having higher priority.</span></span> <span data-ttu-id="0365b-129">優先度の高い順にアクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="0365b-129">Actions are executed in order from highest priority to lowest priority.</span></span>  
  
 <span data-ttu-id="0365b-130">次の例は、優先度がルールの実行順序にどのように影響するかを示しています。</span><span class="sxs-lookup"><span data-stu-id="0365b-130">The following example shows how priority affects the order of execution for the rules.</span></span>  
  
 <span data-ttu-id="0365b-131">**Rule1 (優先度 = 0)**</span><span class="sxs-lookup"><span data-stu-id="0365b-131">**Rule1 (priority = 0)**</span></span>  
  
```  
IF  
Fact1 == 1  
THEN  
Discount = 10%  
```  
  
 <span data-ttu-id="0365b-132">**Rule2 (優先度 = 10)**</span><span class="sxs-lookup"><span data-stu-id="0365b-132">**Rule2 (priority = 10)**</span></span>  
  
```  
IF  
Fact1 > 0  
THEN  
Discount = 15%  
```  
  
 <span data-ttu-id="0365b-133">両方のルールの条件が満たされましたが、Rule2 の方が優先度が高いため先に実行されます。</span><span class="sxs-lookup"><span data-stu-id="0365b-133">The conditions for both rules have been met, but Rule2 is executed first because it has higher priority.</span></span> <span data-ttu-id="0365b-134">次の表に示すように、Rule1 に実行されるアクションの結果、最終的な割引は 10% です。</span><span class="sxs-lookup"><span data-stu-id="0365b-134">The final discount is 10 percent, because it is the result of the action executed for Rule1, as shown in the following table.</span></span>  
  
|<span data-ttu-id="0365b-135">作業メモリ</span><span class="sxs-lookup"><span data-stu-id="0365b-135">Working memory</span></span>|<span data-ttu-id="0365b-136">議題</span><span class="sxs-lookup"><span data-stu-id="0365b-136">Agenda</span></span>|  
|--------------------|------------|  
|<span data-ttu-id="0365b-137">Fact1 (値 = 1)</span><span class="sxs-lookup"><span data-stu-id="0365b-137">Fact1 (value=1)</span></span>|<span data-ttu-id="0365b-138">**Rule2**</span><span class="sxs-lookup"><span data-stu-id="0365b-138">**Rule2**</span></span><br /><br /> <span data-ttu-id="0365b-139">Discount = 15%</span><span class="sxs-lookup"><span data-stu-id="0365b-139">Discount = 15%</span></span><br /><br /> <span data-ttu-id="0365b-140">**Rule1**</span><span class="sxs-lookup"><span data-stu-id="0365b-140">**Rule1**</span></span><br /><br /> <span data-ttu-id="0365b-141">割引の 10% を =</span><span class="sxs-lookup"><span data-stu-id="0365b-141">Discount = 10%</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0365b-142">参照</span><span class="sxs-lookup"><span data-stu-id="0365b-142">See Also</span></span>  
 [<span data-ttu-id="0365b-143">ルール エンジン</span><span class="sxs-lookup"><span data-stu-id="0365b-143">Rule Engine</span></span>](../core/rule-engine.md)