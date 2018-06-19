---
title: ポリシーとルールを作成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 52fb3d835b39a4059fc7a4a1644d7653257ea3dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22250330"
---
# <a name="how-to-create-policies-and-rules"></a><span data-ttu-id="96243-102">ポリシーおよびルールを作成する方法</span><span class="sxs-lookup"><span data-stu-id="96243-102">How to Create Policies and Rules</span></span>
<span data-ttu-id="96243-103">論理演算子の論理グループの条件で規則を作成することができます (**AND**、 **OR**、および**いない**) 述語 (組み込みまたはユーザー定義の関数に適用or 演算子) を受け取る引数 (組み込みまたはユーザー定義のファクトの参照)。</span><span class="sxs-lookup"><span data-stu-id="96243-103">You can create rules with conditions that are logical groupings of logical operators (**AND**, **OR**, and **NOT**) applied to predicates (built-in or user-defined functions or operators) that take arguments (built-in or user-defined fact references).</span></span> <span data-ttu-id="96243-104">右クリックすることができますも**条件**演算子または論理演算子、コンテキスト メニューから論理演算子および組み込み述語を選択します。</span><span class="sxs-lookup"><span data-stu-id="96243-104">You can also right-click **Conditions** or logical operators and select a logical operator or built-in predicate from the context menu.</span></span>  
  
 <span data-ttu-id="96243-105">ルールの条件を評価する場合に実行するアクション (組み込みまたはユーザー定義関数) を定義することができます**true**です。</span><span class="sxs-lookup"><span data-stu-id="96243-105">You can define actions (built-in or user-defined functions) to be executed if the rule condition evaluates to **true**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96243-106">複数の述語をルールに含める場合は、すべての述語が論理演算子に対する引数となるように指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96243-106">If you include more than one predicate in a rule, all predicates must appear as arguments to a logical operator.</span></span> <span data-ttu-id="96243-107">(最上位には、ブール型の単一の .NET メンバー、db 列、または XML フィールド/属性を使用できます)。</span><span class="sxs-lookup"><span data-stu-id="96243-107">(The top level can be a single .NET member, db column, or XML field/attribute that is of boolean type.)</span></span>  
  
### <a name="to-create-a-policy"></a><span data-ttu-id="96243-108">ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="96243-108">To create a policy</span></span>  
  
1.  <span data-ttu-id="96243-109">ポリシー エクスプローラ ペインで右クリック**ポリシー**、クリックして**新しいポリシーの追加**です。</span><span class="sxs-lookup"><span data-stu-id="96243-109">In the Policy Explorer pane, right-click **Policies**, and then click **Add New Policy**.</span></span>  
  
     <span data-ttu-id="96243-110">新しいフォルダーを **"policy1"** の下に作成**ポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="96243-110">A new folder, **Policy1**, is created under **Policies**.</span></span> <span data-ttu-id="96243-111">既定では、新しいポリシーのバージョン 1 が作成されます。</span><span class="sxs-lookup"><span data-stu-id="96243-111">By default, version 1 of a new policy is created for you.</span></span>  
  
2.  <span data-ttu-id="96243-112">をクリックして **"policy1"** です。</span><span class="sxs-lookup"><span data-stu-id="96243-112">Click **Policy1**.</span></span>  
  
3.  <span data-ttu-id="96243-113">"名前" プロパティ ペインに、名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="96243-113">In the Name property pane, type a name.</span></span>  
  
### <a name="to-add-a-rule-to-a-policy-version"></a><span data-ttu-id="96243-114">ルールをポリシーのバージョンに追加するには</span><span class="sxs-lookup"><span data-stu-id="96243-114">To add a rule to a policy version</span></span>  
  
-   <span data-ttu-id="96243-115">ポリシー エクスプローラ ペインで、展開 [**ポリシー**] を右クリックして**バージョン 1.0 (未保存)**、し、**新しいルールの追加**です。</span><span class="sxs-lookup"><span data-stu-id="96243-115">In the Policy Explorer pane, expand [**your policy**], right-click **Version 1.0 (not saved)**, and then select **Add New Rule**.</span></span>  
  
### <a name="to-add-a-logical-operator-to-a-rule-condition"></a><span data-ttu-id="96243-116">論理演算子をルールの条件に追加するには</span><span class="sxs-lookup"><span data-stu-id="96243-116">To add a logical operator to a rule condition</span></span>  
  
-   <span data-ttu-id="96243-117">ルールの定義 ウィンドウで、右クリック**条件**のいずれかをクリックして**論理積**、**論理和の追加**、または**論理否定の追加**.</span><span class="sxs-lookup"><span data-stu-id="96243-117">In the Rule Definition window, right-click **Conditions**, and then click one of **Add Logical AND**, **Add Logical OR**, or **Add Logical NOT**.</span></span>  
  
### <a name="to-add-a-built-in-predicate-to-a-rule-condition-or-logical-operator"></a><span data-ttu-id="96243-118">ルールの条件または論理演算子に組み込みの述語を追加するには</span><span class="sxs-lookup"><span data-stu-id="96243-118">To add a built-in predicate to a rule condition or logical operator</span></span>  
  
1.  <span data-ttu-id="96243-119">ファクト エクスプ ローラー ウィンドウ、**ボキャブラリ** タブをクリックして、**述語**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="96243-119">In the Facts Explorer window, click the **Vocabularies** tab, and then click the **Predicates** folder.</span></span>  
  
2.  <span data-ttu-id="96243-120">公開された述語ボキャブラリのバージョンを展開し、目的の述語をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96243-120">Expand a published version of a predicate vocabulary, and click the predicate you want.</span></span>  
  
3.  <span data-ttu-id="96243-121">論理演算子、またはに述語をドラッグ**条件**ルールには、1 つしか述語が含まれる場合。</span><span class="sxs-lookup"><span data-stu-id="96243-121">Drag the predicate onto the logical operator, or onto **Conditions** if your rule will contain only one predicate.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="96243-122">指定したデータ要素が述語として機能、データ ソースから直接、述語に追加することもできます (に評価される**true**または**false**)。</span><span class="sxs-lookup"><span data-stu-id="96243-122">You can also add a predicate directly from a data source, provided that the data element acts as a predicate (evaluates to **true** or **false**).</span></span>  
  
### <a name="to-add-a-built-in-action-to-a-rule"></a><span data-ttu-id="96243-123">組み込みのアクションをルールに追加するには</span><span class="sxs-lookup"><span data-stu-id="96243-123">To add a built-in action to a rule</span></span>  
  
1.  <span data-ttu-id="96243-124">ファクト エクスプ ローラー ウィンドウ、**ボキャブラリ** タブをクリックして、**関数**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="96243-124">In the Facts Explorer window, click the **Vocabularies** tab, and then click the **Functions** folder.</span></span>  
  
2.  <span data-ttu-id="96243-125">公開された関数ボキャブラリのバージョンを展開し、目的の関数をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96243-125">Expand a published version of the function vocabulary, and click the function you want.</span></span>  
  
3.  <span data-ttu-id="96243-126">関数をドラッグして**アクション**です。</span><span class="sxs-lookup"><span data-stu-id="96243-126">Drag the function onto **Actions**.</span></span> <span data-ttu-id="96243-127">右クリックすることができますも**アクション**、し、コンテキスト メニューから組み込みアクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="96243-127">You can also right-click **Actions**, and select a built-in action from the context menu.</span></span>  
  
### <a name="to-add-an-argument-to-a-condition-or-action"></a><span data-ttu-id="96243-128">条件またはアクションに引数を追加するには</span><span class="sxs-lookup"><span data-stu-id="96243-128">To add an argument to a condition or action</span></span>  
  
1.  <span data-ttu-id="96243-129">ファクト エクスプ ローラー ウィンドウ、**ボキャブラリ** タブし、ボキャブラリ フォルダーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="96243-129">In the Facts Explorer window, click the **Vocabularies** tab, and then click a vocabulary folder.</span></span>  
  
2.  <span data-ttu-id="96243-130">公開されたボキャブラリのバージョンを展開し、目的の用語をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96243-130">Expand a published version of the vocabulary, and click the term you want.</span></span> <span data-ttu-id="96243-131">用語の型は、述語または関数に想定されている型と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="96243-131">The term must be of a type expected by the predicate or function.</span></span>  
  
3.  <span data-ttu-id="96243-132">条件内の述語の引数またはアクション内の関数の引数に用語をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="96243-132">Drag the term onto a predicate argument in a condition or a function argument in an action.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="96243-133">引数をデータ ソースから直接追加することもできます。また、XML の場合は、フィールドの選択時にプロパティでフィールドの型を指定することもできます。この場合、フィールドの型には、データの型と互換性のある型を指定する必要があります。ただし、データ要素が述語またはアクションで想定されている型と一致していることが前提となります。</span><span class="sxs-lookup"><span data-stu-id="96243-133">You can also add an argument directly from a data source or in the case of XML you can specify the field type in the properties when selecting a field; this must of course be compatible with the data itself , provided that the data element is of a type expected by the predicate or action.</span></span> <span data-ttu-id="96243-134">引数を直接データ送信元から追加する場合は、[ファクト エクスプローラー] ウィンドウで該当するタブをクリックして目的の項目を探し、それを述語の引数または関数の引数にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="96243-134">To add an argument directly from a data source, click the appropriate tab in the Facts Explorer window, navigate to the item you want, and drag it onto a predicate argument or function argument.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="96243-135">定数値を直接引数に追加することもできます。その場合は、引数をクリックして目的の定数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="96243-135">You can add a constant value to an argument directly by clicking the argument and entering the constant value you want.</span></span>