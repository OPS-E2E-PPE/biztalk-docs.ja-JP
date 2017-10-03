---
title: "規則を変更する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- business rules, activating
- deactivating business rules
- business rules, priorities
- activating business rules
- business rules, deactivating
- modifying, business rules
- business rules, modifying
ms.assetid: 661b2637-b5d6-4bde-9c42-24cd9e9d241c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fce3fb78ce67b6c82f2301dfcb4cb2175aee0dde
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-modify-rules"></a><span data-ttu-id="a7dc0-102">規則を変更する方法</span><span class="sxs-lookup"><span data-stu-id="a7dc0-102">How to Modify Rules</span></span>
<span data-ttu-id="a7dc0-103">ルールを変更する機能は、ビジネス ルールのパラダイムにおいて重要な役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="a7dc0-103">The ability to change rules is an important part of the business rules paradigm.</span></span> <span data-ttu-id="a7dc0-104">2 つの方法で、ポリシー内のルールを変更することができます。 ポリシーの新しいバージョンを作成するかによって発行されていないバージョンのポリシーを直接変更します。</span><span class="sxs-lookup"><span data-stu-id="a7dc0-104">You can modify rules within a policy in two ways: either by creating a new version of the policy, or by directly modifying an unpublished version of the policy.</span></span>  
  
 <span data-ttu-id="a7dc0-105">ルールは個別に修正できるほか、新しいルールを追加したり、既存のルールを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="a7dc0-105">You can modify rules individually, add new rules, or delete existing rules.</span></span> <span data-ttu-id="a7dc0-106">他にも、述語や論理演算子をルールの条件から削除する、アクションを削除する、アクションを上下に移動する、述語や論理演算子を同じ条件内で移動するなどの操作ができます。</span><span class="sxs-lookup"><span data-stu-id="a7dc0-106">You can delete predicates and logical operators from a rule condition, delete actions, move actions up and down in the display, or move predicates and logical operators within a condition.</span></span> <span data-ttu-id="a7dc0-107">ただし、述語および論理演算子の表示上の順序が、評価の順序を決定するわけではないという点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="a7dc0-107">Keep in mind, however, the order in which the predicates and logical operators are displayed does not determine the order of evaluation.</span></span>  
  
 <span data-ttu-id="a7dc0-108">ルールを非アクティブに設定すると、ポリシーの実行時にルールが実行されないようにできます。また、非アクティブ化されたルールを再度アクティブ化することもできます。</span><span class="sxs-lookup"><span data-stu-id="a7dc0-108">You can set a rule to be inactive, so that the rule is not executed when the policy is executed, or you can reactivate a rule that has been deactivated.</span></span>  
  
 <span data-ttu-id="a7dc0-109">ルールに優先度を設定することにより、別の優先度を持つルールのアクションが実行される前または実行された後に、そのルールのアクションを実行させることができます。</span><span class="sxs-lookup"><span data-stu-id="a7dc0-109">You can set the priority on a rule so that its actions will be executed before or after the actions of any rule of different priority.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="a7dc0-110">SQL Server コンピューターを停止させる必要がある場合は、まだ保存されていないボキャブラリ バージョンまたはボキャブラリ定義をすべて保存してからビジネス ルール作成ツールを閉じる必要があります。そのようにしないと、変更が失われます。</span><span class="sxs-lookup"><span data-stu-id="a7dc0-110">If you need to stop your SQL Server computer, be sure to save any unsaved vocabulary versions or vocabulary definitions, and close the Business Rule Composer so that no changes are lost.</span></span>  
  
 <span data-ttu-id="a7dc0-111">このトピックでは、次の操作の手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="a7dc0-111">This topic contains procedures for the following tasks:</span></span>  
  
-   <span data-ttu-id="a7dc0-112">条件またはアクションの引数を変更するには</span><span class="sxs-lookup"><span data-stu-id="a7dc0-112">To change an argument in a condition or action</span></span>  
  
-   <span data-ttu-id="a7dc0-113">条件内で述語を移動するには</span><span class="sxs-lookup"><span data-stu-id="a7dc0-113">To move a predicate within a condition</span></span>  
  
-   <span data-ttu-id="a7dc0-114">条件内で論理演算子を移動するには</span><span class="sxs-lookup"><span data-stu-id="a7dc0-114">To move a logical operator within a condition</span></span>  
  
-   <span data-ttu-id="a7dc0-115">ルール内のアクションの順序を変更するには</span><span class="sxs-lookup"><span data-stu-id="a7dc0-115">To change the order of actions within a rule</span></span>  
  
-   <span data-ttu-id="a7dc0-116">述語、論理演算子、またはアクションを削除するには</span><span class="sxs-lookup"><span data-stu-id="a7dc0-116">To delete a predicate, logical operator, or action</span></span>  
  
-   <span data-ttu-id="a7dc0-117">ルールをアクティブ化または非アクティブ化するには</span><span class="sxs-lookup"><span data-stu-id="a7dc0-117">To activate or deactivate a rule</span></span>  
  
-   <span data-ttu-id="a7dc0-118">ルールに優先度を設定するには</span><span class="sxs-lookup"><span data-stu-id="a7dc0-118">To set a priority on a rule</span></span>  
  
### <a name="to-change-an-argument-in-a-condition-or-action"></a><span data-ttu-id="a7dc0-119">条件またはアクションの引数を変更するには</span><span class="sxs-lookup"><span data-stu-id="a7dc0-119">To change an argument in a condition or action</span></span>  
  
1.  <span data-ttu-id="a7dc0-120">[ファクト エクスプローラー] ウィンドウで、適切なタブをクリックし、引数として使用する用語に移動します。</span><span class="sxs-lookup"><span data-stu-id="a7dc0-120">In the Facts and Definitions window, click the appropriate tab, and navigate to the term you want to use as an argument.</span></span> <span data-ttu-id="a7dc0-121">用語の型は、述語または関数に想定されている型と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7dc0-121">The term must be of a type expected by the predicate or function.</span></span>  
  
2.  <span data-ttu-id="a7dc0-122">用語をクリックし、条件内の述語の引数またはアクション内の関数の引数にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="a7dc0-122">Click the term and drag it onto a predicate argument in a condition or a function argument in an action.</span></span>  
  
### <a name="to-move-a-predicate-within-a-condition"></a><span data-ttu-id="a7dc0-123">条件内で述語を移動するには</span><span class="sxs-lookup"><span data-stu-id="a7dc0-123">To move a predicate within a condition</span></span>  
  
-   <span data-ttu-id="a7dc0-124">述語をクリックし、別の論理演算子にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="a7dc0-124">Click the predicate, and drag it to another logical operator.</span></span>  
  
### <a name="to-move-a-logical-operator-within-a-condition"></a><span data-ttu-id="a7dc0-125">条件内で論理演算子を移動するには</span><span class="sxs-lookup"><span data-stu-id="a7dc0-125">To move a logical operator within a condition</span></span>  
  
-   <span data-ttu-id="a7dc0-126">論理演算子をクリックし、別の論理演算子またはには、それをドラッグ**条件**です。</span><span class="sxs-lookup"><span data-stu-id="a7dc0-126">Click the logical operator, and drag it onto another logical operator or onto **Conditions**.</span></span>  
  
### <a name="to-change-the-order-of-actions-within-a-rule"></a><span data-ttu-id="a7dc0-127">ルール内のアクションの順序を変更するには</span><span class="sxs-lookup"><span data-stu-id="a7dc0-127">To change the order of actions within a rule</span></span>  
  
-   <span data-ttu-id="a7dc0-128">アクションをクリックし、をクリックして**上に移動**または**下へ移動**です。</span><span class="sxs-lookup"><span data-stu-id="a7dc0-128">Click the action and then click **Move action up** or **Move action down**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a7dc0-129">ルールのアクションは、他のアクションの後に実行されるエンジンの制御関数を除き、指定された順序で実行されます。</span><span class="sxs-lookup"><span data-stu-id="a7dc0-129">The actions of a rule will be executed in the order specified with the exception of engine control functions which are executed after the other actions.</span></span>  
  
### <a name="to-delete-a-predicate-logical-operator-or-action"></a><span data-ttu-id="a7dc0-130">述語、論理演算子、またはアクションを削除するには</span><span class="sxs-lookup"><span data-stu-id="a7dc0-130">To delete a predicate, logical operator, or action</span></span>  
  
-   <span data-ttu-id="a7dc0-131">述語、論理演算子、またはアクション、をクリックし、をクリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="a7dc0-131">Click the predicate, logical operator, or action, and then click **Delete**.</span></span>  
  
### <a name="to-activate-or-deactivate-a-rule"></a><span data-ttu-id="a7dc0-132">ルールをアクティブ化または非アクティブ化するには</span><span class="sxs-lookup"><span data-stu-id="a7dc0-132">To activate or deactivate a rule</span></span>  
  
-   <span data-ttu-id="a7dc0-133">ルールをクリックし、[プロパティ] ウィンドウで次のように設定します。 **Active**いずれかに**True**または**False**です。</span><span class="sxs-lookup"><span data-stu-id="a7dc0-133">Click the rule, and then in the Properties window, set **Active** to either **True** or **False**.</span></span>  
  
### <a name="to-set-a-priority-on-a-rule"></a><span data-ttu-id="a7dc0-134">ルールに優先度を設定するには</span><span class="sxs-lookup"><span data-stu-id="a7dc0-134">To set a priority on a rule</span></span>  
  
-   <span data-ttu-id="a7dc0-135">ルールをクリックし、[プロパティ] ウィンドウで次のように設定します。**優先度**整数値にします。</span><span class="sxs-lookup"><span data-stu-id="a7dc0-135">Click the rule, and then in the Properties window, set **Priority** to an integer value.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a7dc0-136">優先度は相対的に使用されます。特定の優先度を持つルールのすべてのアクションは、より低い優先度値を持つルールのアクションよりも前に実行されます。</span><span class="sxs-lookup"><span data-stu-id="a7dc0-136">Priorities are relative, and all of the actions of a rule of a given priority will be executed in order before any of the actions of a rule with a lower value for priority.</span></span> <span data-ttu-id="a7dc0-137">優先度には正数または負数を設定できます。既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="a7dc0-137">The priority value defaults to zero, but it can be positive or negative.</span></span>