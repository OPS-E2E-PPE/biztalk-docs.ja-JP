---
title: ポリシーとルールを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, business rules
- policies, rules
- policies, predicates
- business rules, creating
- creating, policies
- policies, logical operators
- policies, examples
- policies, default actions
- policies
- policies, arguments
- policies, creating
ms.assetid: 59f06a67-edde-443b-9fbb-55ec4429837a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57fa00774f1c27b6a3de323369c3d260851ecade
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385465"
---
# <a name="how-to-create-policies-and-rules"></a><span data-ttu-id="3a362-102">ポリシーとルールを作成する方法</span><span class="sxs-lookup"><span data-stu-id="3a362-102">How to Create Policies and Rules</span></span>
<span data-ttu-id="3a362-103">論理グループの論理演算子の条件で規則を作成することができます (**AND**、 **OR**、および**いない**) 述語 (の組み込みまたはユーザー定義関数に適用or 演算子) を受け取る引数 (組み込みまたはユーザー定義のファクトの参照)。</span><span class="sxs-lookup"><span data-stu-id="3a362-103">You can create rules with conditions that are logical groupings of logical operators (**AND**, **OR**, and **NOT**) applied to predicates (built-in or user-defined functions or operators) that take arguments (built-in or user-defined fact references).</span></span> <span data-ttu-id="3a362-104">右クリックすることができますも**条件**or 論理演算子、コンテキスト メニューから論理演算子および組み込み述語を選択します。</span><span class="sxs-lookup"><span data-stu-id="3a362-104">You can also right-click **Conditions** or logical operators and select a logical operator or built-in predicate from the context menu.</span></span>  
  
 <span data-ttu-id="3a362-105">ルールの条件を評価する場合に実行されるアクション (組み込みまたはユーザー定義関数) を定義する**true**します。</span><span class="sxs-lookup"><span data-stu-id="3a362-105">You can define actions (built-in or user-defined functions) to be executed if the rule condition evaluates to **true**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3a362-106">ルールでは、複数の述語を含めると、すべての述語する必要があります、論理演算子を引数として表示されます。</span><span class="sxs-lookup"><span data-stu-id="3a362-106">If you include more than one predicate in a rule, all predicates must appear as arguments to a logical operator.</span></span> <span data-ttu-id="3a362-107">(最上位は単一の .NET メンバー、db 列、またはブール型の XML フィールド/属性を使用できます)</span><span class="sxs-lookup"><span data-stu-id="3a362-107">(The top level can be a single .NET member, db column, or XML field/attribute that is of boolean type.)</span></span>  
  
### <a name="to-create-a-policy"></a><span data-ttu-id="3a362-108">ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="3a362-108">To create a policy</span></span>  
  
1.  <span data-ttu-id="3a362-109">ポリシー エクスプローラ ペインで右クリック**ポリシー**、 をクリックし、**新しいポリシーの追加**します。</span><span class="sxs-lookup"><span data-stu-id="3a362-109">In the Policy Explorer pane, right-click **Policies**, and then click **Add New Policy**.</span></span>  
  
     <span data-ttu-id="3a362-110">新しいフォルダーを**Policy1**、下に作成されます**ポリシー**します。</span><span class="sxs-lookup"><span data-stu-id="3a362-110">A new folder, **Policy1**, is created under **Policies**.</span></span> <span data-ttu-id="3a362-111">既定では、新しいポリシーのバージョン 1 が作成されます。</span><span class="sxs-lookup"><span data-stu-id="3a362-111">By default, version 1 of a new policy is created for you.</span></span>  
  
2.  <span data-ttu-id="3a362-112">クリックして**Policy1**します。</span><span class="sxs-lookup"><span data-stu-id="3a362-112">Click **Policy1**.</span></span>  
  
3.  <span data-ttu-id="3a362-113">名前のプロパティ ウィンドウで名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="3a362-113">In the Name property pane, type a name.</span></span>  
  
### <a name="to-add-a-rule-to-a-policy-version"></a><span data-ttu-id="3a362-114">ポリシーのバージョンにルールを追加するには</span><span class="sxs-lookup"><span data-stu-id="3a362-114">To add a rule to a policy version</span></span>  
  
-   <span data-ttu-id="3a362-115">ポリシー エクスプ ローラー] ウィンドウで **[ポリシー]** を右クリックして**バージョン 1.0 (未保存)**、し、[**新しいルールの追加**します。</span><span class="sxs-lookup"><span data-stu-id="3a362-115">In the Policy Explorer pane, expand [**your policy**], right-click **Version 1.0 (not saved)**, and then select **Add New Rule**.</span></span>  
  
### <a name="to-add-a-logical-operator-to-a-rule-condition"></a><span data-ttu-id="3a362-116">ルールの条件に論理演算子を追加するには</span><span class="sxs-lookup"><span data-stu-id="3a362-116">To add a logical operator to a rule condition</span></span>  
  
-   <span data-ttu-id="3a362-117">ルールの定義 ウィンドウで、右クリック**条件**のいずれかをクリックして**論理積の追加**、**論理和の追加**、または**論理否定の追加**.</span><span class="sxs-lookup"><span data-stu-id="3a362-117">In the Rule Definition window, right-click **Conditions**, and then click one of **Add Logical AND**, **Add Logical OR**, or **Add Logical NOT**.</span></span>  
  
### <a name="to-add-a-built-in-predicate-to-a-rule-condition-or-logical-operator"></a><span data-ttu-id="3a362-118">ルール条件または論理演算子に組み込みの述語を追加するには</span><span class="sxs-lookup"><span data-stu-id="3a362-118">To add a built-in predicate to a rule condition or logical operator</span></span>  
  
1.  <span data-ttu-id="3a362-119">[ファクト エクスプ ローラー] ウィンドウ、**ボキャブラリ**タブをクリックし、をクリックし、**述語**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="3a362-119">In the Facts Explorer window, click the **Vocabularies** tab, and then click the **Predicates** folder.</span></span>  
  
2.  <span data-ttu-id="3a362-120">公開された述語のボキャブラリのバージョンを展開し、希望の述語をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3a362-120">Expand a published version of a predicate vocabulary, and click the predicate you want.</span></span>  
  
3.  <span data-ttu-id="3a362-121">論理演算子、またはに述語をドラッグ**条件**ルールには、1 つしか述語が含まれる場合。</span><span class="sxs-lookup"><span data-stu-id="3a362-121">Drag the predicate onto the logical operator, or onto **Conditions** if your rule will contain only one predicate.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3a362-122">データ要素が述語として機能しますが、データ ソースから直接、述語に追加することもできます (に評価される**true**または**false**)。</span><span class="sxs-lookup"><span data-stu-id="3a362-122">You can also add a predicate directly from a data source, provided that the data element acts as a predicate (evaluates to **true** or **false**).</span></span>  
  
### <a name="to-add-a-built-in-action-to-a-rule"></a><span data-ttu-id="3a362-123">ルールに、組み込みアクションを追加するには</span><span class="sxs-lookup"><span data-stu-id="3a362-123">To add a built-in action to a rule</span></span>  
  
1.  <span data-ttu-id="3a362-124">[ファクト エクスプ ローラー] ウィンドウ、**ボキャブラリ**タブをクリックし、をクリックし、**関数**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="3a362-124">In the Facts Explorer window, click the **Vocabularies** tab, and then click the **Functions** folder.</span></span>  
  
2.  <span data-ttu-id="3a362-125">公開された関数のボキャブラリのバージョンを展開し、関数をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3a362-125">Expand a published version of the function vocabulary, and click the function you want.</span></span>  
  
3.  <span data-ttu-id="3a362-126">関数をドラッグして**アクション**します。</span><span class="sxs-lookup"><span data-stu-id="3a362-126">Drag the function onto **Actions**.</span></span> <span data-ttu-id="3a362-127">右クリックすることができますも**アクション**、コンテキスト メニューから組み込みアクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="3a362-127">You can also right-click **Actions**, and select a built-in action from the context menu.</span></span>  
  
### <a name="to-add-an-argument-to-a-condition-or-action"></a><span data-ttu-id="3a362-128">条件またはアクションに引数を追加するには</span><span class="sxs-lookup"><span data-stu-id="3a362-128">To add an argument to a condition or action</span></span>  
  
1.  <span data-ttu-id="3a362-129">[ファクト エクスプ ローラー] ウィンドウ、**ボキャブラリ**] タブの [をボキャブラリ フォルダーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3a362-129">In the Facts Explorer window, click the **Vocabularies** tab, and then click a vocabulary folder.</span></span>  
  
2.  <span data-ttu-id="3a362-130">公開された、ボキャブラリのバージョンを展開し、目的の用語をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3a362-130">Expand a published version of the vocabulary, and click the term you want.</span></span> <span data-ttu-id="3a362-131">という用語は、述語または関数で想定されている型でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="3a362-131">The term must be of a type expected by the predicate or function.</span></span>  
  
3.  <span data-ttu-id="3a362-132">用語を条件の述語の引数またはアクション内の関数の引数にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="3a362-132">Drag the term onto a predicate argument in a condition or a function argument in an action.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3a362-133">データ ソースから直接、引数を追加することもできます。 または XML の場合で指定できます、フィールドの種類、プロパティ フィールドを選択するときにもちろんあります自体には、データとの互換性提供されるデータの要素が述語またはアクションで想定されている型の。</span><span class="sxs-lookup"><span data-stu-id="3a362-133">You can also add an argument directly from a data source or in the case of XML you can specify the field type in the properties when selecting a field; this must of course be compatible with the data itself , provided that the data element is of a type expected by the predicate or action.</span></span> <span data-ttu-id="3a362-134">データ ソースから直接には、引数を追加するには、[ファクト エクスプ ローラー] ウィンドウで、適切なタブをクリックして、項目に移動して述語の引数または関数の引数にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="3a362-134">To add an argument directly from a data source, click the appropriate tab in the Facts Explorer window, navigate to the item you want, and drag it onto a predicate argument or function argument.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3a362-135">引数をクリックし、使用する定数値を入力して直接引数に定数値を追加できます。</span><span class="sxs-lookup"><span data-stu-id="3a362-135">You can add a constant value to an argument directly by clicking the argument and entering the constant value you want.</span></span>