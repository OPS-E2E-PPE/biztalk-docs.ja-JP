---
title: 規則を変更する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2badd7947e439fe3ba80d86607a1a271d52b5eb6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336007"
---
# <a name="how-to-modify-rules"></a><span data-ttu-id="8e1d5-102">規則を変更する方法</span><span class="sxs-lookup"><span data-stu-id="8e1d5-102">How to Modify Rules</span></span>
<span data-ttu-id="8e1d5-103">ルールを変更する機能は、ビジネス ルールのパラダイムの重要な部分です。</span><span class="sxs-lookup"><span data-stu-id="8e1d5-103">The ability to change rules is an important part of the business rules paradigm.</span></span> <span data-ttu-id="8e1d5-104">2 つの方法で、ポリシー内のルールを変更することができます。 ポリシーの新しいバージョンを作成するか、発行されていないバージョンのポリシーを直接変更します。</span><span class="sxs-lookup"><span data-stu-id="8e1d5-104">You can modify rules within a policy in two ways: either by creating a new version of the policy, or by directly modifying an unpublished version of the policy.</span></span>  
  
 <span data-ttu-id="8e1d5-105">ルールを個別に変更する、新しいルールを追加、または既存のルールを削除できます。</span><span class="sxs-lookup"><span data-stu-id="8e1d5-105">You can modify rules individually, add new rules, or delete existing rules.</span></span> <span data-ttu-id="8e1d5-106">述語および論理演算子をルールの条件から削除して操作を削除する、画面で、アクションを上下に移動するか、または述語や論理演算子、条件内を移動できます。</span><span class="sxs-lookup"><span data-stu-id="8e1d5-106">You can delete predicates and logical operators from a rule condition, delete actions, move actions up and down in the display, or move predicates and logical operators within a condition.</span></span> <span data-ttu-id="8e1d5-107">ただしに注意してください、述語や論理演算子の表示順序が評価の順序を決定していません。</span><span class="sxs-lookup"><span data-stu-id="8e1d5-107">Keep in mind, however, the order in which the predicates and logical operators are displayed does not determine the order of evaluation.</span></span>  
  
 <span data-ttu-id="8e1d5-108">非アクティブ化する、ポリシーの実行、または非アクティブ化されているルールを再アクティブ化することができる場合、ルールが実行されないように規則を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="8e1d5-108">You can set a rule to be inactive, so that the rule is not executed when the policy is executed, or you can reactivate a rule that has been deactivated.</span></span>  
  
 <span data-ttu-id="8e1d5-109">前に、または別の優先順位のルールのアクションの後にそのアクションが実行できるように、ルールの優先順位を設定できます。</span><span class="sxs-lookup"><span data-stu-id="8e1d5-109">You can set the priority on a rule so that its actions will be executed before or after the actions of any rule of different priority.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="8e1d5-110">SQL Server コンピューターを停止する場合は、必ずをすべて保存されていないボキャブラリ バージョンまたはボキャブラリの定義を保存し、変更が失われないように、ビジネス ルール作成ツールを閉じます。</span><span class="sxs-lookup"><span data-stu-id="8e1d5-110">If you need to stop your SQL Server computer, be sure to save any unsaved vocabulary versions or vocabulary definitions, and close the Business Rule Composer so that no changes are lost.</span></span>  
  
 <span data-ttu-id="8e1d5-111">このトピックには、次のタスクの手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8e1d5-111">This topic contains procedures for the following tasks:</span></span>  
  
-   <span data-ttu-id="8e1d5-112">条件またはアクションの引数を変更するには</span><span class="sxs-lookup"><span data-stu-id="8e1d5-112">To change an argument in a condition or action</span></span>  
  
-   <span data-ttu-id="8e1d5-113">条件内で述語を移動するには</span><span class="sxs-lookup"><span data-stu-id="8e1d5-113">To move a predicate within a condition</span></span>  
  
-   <span data-ttu-id="8e1d5-114">条件内で論理演算子を移動するには</span><span class="sxs-lookup"><span data-stu-id="8e1d5-114">To move a logical operator within a condition</span></span>  
  
-   <span data-ttu-id="8e1d5-115">ルール内のアクションの順序を変更するには</span><span class="sxs-lookup"><span data-stu-id="8e1d5-115">To change the order of actions within a rule</span></span>  
  
-   <span data-ttu-id="8e1d5-116">述語、論理演算子、またはアクションを削除するには</span><span class="sxs-lookup"><span data-stu-id="8e1d5-116">To delete a predicate, logical operator, or action</span></span>  
  
-   <span data-ttu-id="8e1d5-117">アクティブ化またはルールを非アクティブ化するには</span><span class="sxs-lookup"><span data-stu-id="8e1d5-117">To activate or deactivate a rule</span></span>  
  
-   <span data-ttu-id="8e1d5-118">ルールの優先順位を設定するには</span><span class="sxs-lookup"><span data-stu-id="8e1d5-118">To set a priority on a rule</span></span>  
  
### <a name="to-change-an-argument-in-a-condition-or-action"></a><span data-ttu-id="8e1d5-119">条件またはアクションの引数を変更するには</span><span class="sxs-lookup"><span data-stu-id="8e1d5-119">To change an argument in a condition or action</span></span>  
  
1.  <span data-ttu-id="8e1d5-120">ファクトと定義 ウィンドウで、適切なタブをクリックし、引数として使用する用語に移動します。</span><span class="sxs-lookup"><span data-stu-id="8e1d5-120">In the Facts and Definitions window, click the appropriate tab, and navigate to the term you want to use as an argument.</span></span> <span data-ttu-id="8e1d5-121">という用語は、述語または関数で想定されている型でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="8e1d5-121">The term must be of a type expected by the predicate or function.</span></span>  
  
2.  <span data-ttu-id="8e1d5-122">用語をクリックし、条件の述語の引数またはアクション内の関数の引数にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="8e1d5-122">Click the term and drag it onto a predicate argument in a condition or a function argument in an action.</span></span>  
  
### <a name="to-move-a-predicate-within-a-condition"></a><span data-ttu-id="8e1d5-123">条件内で述語を移動するには</span><span class="sxs-lookup"><span data-stu-id="8e1d5-123">To move a predicate within a condition</span></span>  
  
-   <span data-ttu-id="8e1d5-124">述語をクリックし、もう 1 つの論理演算子にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="8e1d5-124">Click the predicate, and drag it to another logical operator.</span></span>  
  
### <a name="to-move-a-logical-operator-within-a-condition"></a><span data-ttu-id="8e1d5-125">条件内で論理演算子を移動するには</span><span class="sxs-lookup"><span data-stu-id="8e1d5-125">To move a logical operator within a condition</span></span>  
  
-   <span data-ttu-id="8e1d5-126">論理演算子をクリックし、もう 1 つの論理演算子またはには、それをドラッグ**条件**します。</span><span class="sxs-lookup"><span data-stu-id="8e1d5-126">Click the logical operator, and drag it onto another logical operator or onto **Conditions**.</span></span>  
  
### <a name="to-change-the-order-of-actions-within-a-rule"></a><span data-ttu-id="8e1d5-127">ルール内のアクションの順序を変更するには</span><span class="sxs-lookup"><span data-stu-id="8e1d5-127">To change the order of actions within a rule</span></span>  
  
-   <span data-ttu-id="8e1d5-128">アクションをクリックし、クリックして**アクションを上へ移動**または**下へ移動**します。</span><span class="sxs-lookup"><span data-stu-id="8e1d5-128">Click the action and then click **Move action up** or **Move action down**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8e1d5-129">ルールのアクションは、その他のアクションの後に実行されるエンジン制御関数を除き、指定された順序で実行されます。</span><span class="sxs-lookup"><span data-stu-id="8e1d5-129">The actions of a rule will be executed in the order specified with the exception of engine control functions which are executed after the other actions.</span></span>  
  
### <a name="to-delete-a-predicate-logical-operator-or-action"></a><span data-ttu-id="8e1d5-130">述語、論理演算子、またはアクションを削除するには</span><span class="sxs-lookup"><span data-stu-id="8e1d5-130">To delete a predicate, logical operator, or action</span></span>  
  
-   <span data-ttu-id="8e1d5-131">述語、論理演算子、またはアクションをクリックし、クリックして**削除**します。</span><span class="sxs-lookup"><span data-stu-id="8e1d5-131">Click the predicate, logical operator, or action, and then click **Delete**.</span></span>  
  
### <a name="to-activate-or-deactivate-a-rule"></a><span data-ttu-id="8e1d5-132">アクティブ化またはルールを非アクティブ化するには</span><span class="sxs-lookup"><span data-stu-id="8e1d5-132">To activate or deactivate a rule</span></span>  
  
-   <span data-ttu-id="8e1d5-133">ルールをクリックし、[プロパティ] ウィンドウで次のように設定します。 **Active**いずれかに**True**または**False**します。</span><span class="sxs-lookup"><span data-stu-id="8e1d5-133">Click the rule, and then in the Properties window, set **Active** to either **True** or **False**.</span></span>  
  
### <a name="to-set-a-priority-on-a-rule"></a><span data-ttu-id="8e1d5-134">ルールの優先順位を設定するには</span><span class="sxs-lookup"><span data-stu-id="8e1d5-134">To set a priority on a rule</span></span>  
  
-   <span data-ttu-id="8e1d5-135">ルールをクリックし、[プロパティ] ウィンドウで次のように設定します。**優先度**整数値。</span><span class="sxs-lookup"><span data-stu-id="8e1d5-135">Click the rule, and then in the Properties window, set **Priority** to an integer value.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8e1d5-136">優先度は相対的と特定の優先順位のルールのアクションのすべての優先度の低い値を持つルールのアクションの前に、順序で実行されます。</span><span class="sxs-lookup"><span data-stu-id="8e1d5-136">Priorities are relative, and all of the actions of a rule of a given priority will be executed in order before any of the actions of a rule with a lower value for priority.</span></span> <span data-ttu-id="8e1d5-137">優先度の値の既定値は 0 が、正または負の値であることができます。</span><span class="sxs-lookup"><span data-stu-id="8e1d5-137">The priority value defaults to zero, but it can be positive or negative.</span></span>