---
title: ビジネス ルールにおけるポリシー テストのトレース出力の情報 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing, business rules
- testing, policies
- business rules, testing
- policies, testing
ms.assetid: 26ff584e-97a1-4d76-a8a9-a55b4c99231f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 427eb9f1a7cae3cd6a1c9a6fe9a5ecac82e60c80
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394946"
---
# <a name="policy-test-trace-output-information-for-business-rules"></a><span data-ttu-id="18ce5-102">ビジネス ルールにおけるポリシー テストのトレース出力情報</span><span class="sxs-lookup"><span data-stu-id="18ce5-102">Policy Test Trace Output Information for Business Rules</span></span>
<span data-ttu-id="18ce5-103">このセクションでは、ビジネス ルール作成ツールでポリシーをテストするときに表示される追跡情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="18ce5-103">This section provides information on the tracking information that is displayed when testing a policy in the Business Rule Composer.</span></span> <span data-ttu-id="18ce5-104">グループ ハブ ページでクエリを追跡メッセージ イベントおよびサービス インスタンスを使用してポリシーの実行の追跡結果を表示するときによく似ています情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="18ce5-104">Very similar information is seen when viewing tracking results for policy execution using the message event and service instance tracking queries on the Group Hub page.</span></span>  
  
 <span data-ttu-id="18ce5-105">追跡出力に表示される 4 つのステートメントの種類があります。</span><span class="sxs-lookup"><span data-stu-id="18ce5-105">There are four statement types that are displayed in the tracking output:</span></span>  
  
- <span data-ttu-id="18ce5-106">ファクト アクティビティ</span><span class="sxs-lookup"><span data-stu-id="18ce5-106">Fact Activity</span></span>  
  
- <span data-ttu-id="18ce5-107">条件の評価</span><span class="sxs-lookup"><span data-stu-id="18ce5-107">Condition Evaluation</span></span>  
  
- <span data-ttu-id="18ce5-108">議題の更新</span><span class="sxs-lookup"><span data-stu-id="18ce5-108">Agenda Update</span></span>  
  
- <span data-ttu-id="18ce5-109">実行されたルール</span><span class="sxs-lookup"><span data-stu-id="18ce5-109">Rule Fired</span></span>  
  
  <span data-ttu-id="18ce5-110">各ステートメントの種類を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="18ce5-110">Each statement type is described below.</span></span>  
  
## <a name="fact-activity"></a><span data-ttu-id="18ce5-111">ファクト アクティビティ</span><span class="sxs-lookup"><span data-stu-id="18ce5-111">Fact Activity</span></span>  
 <span data-ttu-id="18ce5-112">このステートメントでは、エンジンの作業メモリに存在するファクトに対する変更を示します。</span><span class="sxs-lookup"><span data-stu-id="18ce5-112">This statement indicates changes to the facts present in the working memory of the engine.</span></span> <span data-ttu-id="18ce5-113">ファクト アクティビティのエントリの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="18ce5-113">The following is an example of a fact activity entry:</span></span>  
  
```  
FACT ACTIVITY 3/16/2004 9:50:28 AM  
Rule Engine Instance Identifier: 9effe3f9-d3ad-4125-99fa-56bb379188f7  
Ruleset Name: LoanProcessing  
Operation: Assert  
Object Type: MyTest.test  
Object Instance Identifier: 872  
```  
  
### <a name="rule-engine-instance-identifier"></a><span data-ttu-id="18ce5-114">ルール エンジン インスタンス識別子</span><span class="sxs-lookup"><span data-stu-id="18ce5-114">Rule Engine Instance Identifier</span></span>  
 <span data-ttu-id="18ce5-115">一意の識別子、 **RuleEngine**実行されているルールの実行環境を提供するインスタンス。</span><span class="sxs-lookup"><span data-stu-id="18ce5-115">Unique identifier for the **RuleEngine** instance that provides the execution environment for the rule firing.</span></span>  
  
### <a name="ruleset-name"></a><span data-ttu-id="18ce5-116">ルール セット名</span><span class="sxs-lookup"><span data-stu-id="18ce5-116">Ruleset Name</span></span>  
 <span data-ttu-id="18ce5-117">ルール セット (ポリシー) の名前。</span><span class="sxs-lookup"><span data-stu-id="18ce5-117">The name of the rule set (policy).</span></span>  
  
### <a name="operation"></a><span data-ttu-id="18ce5-118">操作</span><span class="sxs-lookup"><span data-stu-id="18ce5-118">Operation</span></span>  
 <span data-ttu-id="18ce5-119">ファクト アクティビティで発生する操作の 3 つの種類があります。</span><span class="sxs-lookup"><span data-stu-id="18ce5-119">There are three types of operation that can occur in a fact activity:</span></span>  
  
 <span data-ttu-id="18ce5-120">Filter</span><span class="sxs-lookup"><span data-stu-id="18ce5-120">Assert</span></span>  
  
 <span data-ttu-id="18ce5-121">作業メモリに追加されるという事実です。</span><span class="sxs-lookup"><span data-stu-id="18ce5-121">The fact is being added to the working memory.</span></span>  
  
 <span data-ttu-id="18ce5-122">更新</span><span class="sxs-lookup"><span data-stu-id="18ce5-122">Update</span></span>  
  
 <span data-ttu-id="18ce5-123">という事実は、ルールによって更新されると、新しいデータと状態に基づいて、再評価するエンジンにアサートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="18ce5-123">The fact is being updated by a rule and then needs to be reasserted into the engine to be re-evaluated, based on the new data and state.</span></span>  
  
 <span data-ttu-id="18ce5-124">取り消し</span><span class="sxs-lookup"><span data-stu-id="18ce5-124">Retract</span></span>  
  
 <span data-ttu-id="18ce5-125">事実を作業メモリから削除しています。</span><span class="sxs-lookup"><span data-stu-id="18ce5-125">The fact is being removed from the working memory.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="18ce5-126">型と一致しません、ポリシーで使用される型のいずれかのファクトがアサートされると場合、アサート操作は「アサート-認識されないファクト」で表示されます。</span><span class="sxs-lookup"><span data-stu-id="18ce5-126">If a fact is asserted whose type does not match any of the types used in the policy, the Assert operation will display "Assert – Fact Unrecognized".</span></span>  
  
### <a name="object-type"></a><span data-ttu-id="18ce5-127">[オブジェクトの種類]</span><span class="sxs-lookup"><span data-stu-id="18ce5-127">Object Type</span></span>  
 <span data-ttu-id="18ce5-128">特定のアクティビティのファクトの種類:</span><span class="sxs-lookup"><span data-stu-id="18ce5-128">The type of fact for a particular activity:</span></span>  
  
-   <span data-ttu-id="18ce5-129">DataConnection</span><span class="sxs-lookup"><span data-stu-id="18ce5-129">DataConnection</span></span>  
  
-   <span data-ttu-id="18ce5-130">TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="18ce5-130">TypedDataTable</span></span>  
  
-   <span data-ttu-id="18ce5-131">TypedDataRow</span><span class="sxs-lookup"><span data-stu-id="18ce5-131">TypedDataRow</span></span>  
  
     <span data-ttu-id="18ce5-132">すべての含まれる行の TypedDataTable がアサートされる場合は、TypedDataRows としてアサートされます。</span><span class="sxs-lookup"><span data-stu-id="18ce5-132">When a TypedDataTable is asserted all of the contained rows are asserted as TypedDataRows.</span></span>  <span data-ttu-id="18ce5-133">条件が評価され、結果として得られるクエリが実行されるまで、DataConnection に関連付けられている TypedDataRows はアサートされません。</span><span class="sxs-lookup"><span data-stu-id="18ce5-133">TypedDataRows associated with a DataConnection are not asserted until a condition is evaluated and the resulting query is executed.</span></span>  
  
-   <span data-ttu-id="18ce5-134">TypedXmlDocument</span><span class="sxs-lookup"><span data-stu-id="18ce5-134">TypedXmlDocument</span></span>  
  
     <span data-ttu-id="18ce5-135">アサーションが親と子の TypedXmlDocument インスタンスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="18ce5-135">Assertions will be seen for both parent and child TypedXmlDocument instances.</span></span>  
  
### <a name="object-instance-identifier"></a><span data-ttu-id="18ce5-136">オブジェクト インスタンス識別子</span><span class="sxs-lookup"><span data-stu-id="18ce5-136">Object Instance Identifier</span></span>  
 <span data-ttu-id="18ce5-137">ファクト参照の一意のインスタンス ID。</span><span class="sxs-lookup"><span data-stu-id="18ce5-137">Unique instance ID of the fact reference.</span></span>  
  
## <a name="condition-evaluation"></a><span data-ttu-id="18ce5-138">条件の評価</span><span class="sxs-lookup"><span data-stu-id="18ce5-138">Condition Evaluation</span></span>  
 <span data-ttu-id="18ce5-139">このアクティビティでは、個々 の述語を評価した結果を示します。</span><span class="sxs-lookup"><span data-stu-id="18ce5-139">This activity indicates the result of evaluating individual predicates.</span></span> <span data-ttu-id="18ce5-140">条件評価のエントリの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="18ce5-140">The following is an example of a condition evaluation entry:</span></span>  
  
```  
CONDITION EVALUATION TEST (MATCH) 1/07/2004 5:33:13 PM  
Rule Engine Instance Identifier: f1dd3ff2-b4a8-4fe1-8d46-4d9b3e2502d3  
Ruleset Name: LoanProcessing  
Test Expression: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:Root.EmploymentType/TimeInMonths >= 18  
Left Operand Value: 31  
Right Operand Value: 18  
Test Result: True  
```  
  
 <span data-ttu-id="18ce5-141">上記の例では用語の一部の説明は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="18ce5-141">The descriptions for some of the terms in the preceding example are as follows:</span></span>  
  
-   <span data-ttu-id="18ce5-142">**式をテストします。**</span><span class="sxs-lookup"><span data-stu-id="18ce5-142">**Test Expression.**</span></span> <span data-ttu-id="18ce5-143">ルールに含まれる (単項式または二) 単純な式です。</span><span class="sxs-lookup"><span data-stu-id="18ce5-143">A simple (unary or binary) expression within a rule.</span></span>  
  
-   <span data-ttu-id="18ce5-144">**左側のオペランドの値。**</span><span class="sxs-lookup"><span data-stu-id="18ce5-144">**Left Operand Value.**</span></span> <span data-ttu-id="18ce5-145">式の左側にある用語の値。</span><span class="sxs-lookup"><span data-stu-id="18ce5-145">The value of the term on the left side of an expression.</span></span>  
  
-   <span data-ttu-id="18ce5-146">**右側のオペランドの値。**</span><span class="sxs-lookup"><span data-stu-id="18ce5-146">**Right Operand Value.**</span></span> <span data-ttu-id="18ce5-147">式の右側にある用語の値。</span><span class="sxs-lookup"><span data-stu-id="18ce5-147">The value of the term on the right side of an expression.</span></span>  
  
-   <span data-ttu-id="18ce5-148">**結果をテストします。**</span><span class="sxs-lookup"><span data-stu-id="18ce5-148">**Test Result.**</span></span> <span data-ttu-id="18ce5-149">True であると、評価の結果または False。</span><span class="sxs-lookup"><span data-stu-id="18ce5-149">The result of the evaluation, which is either True or False.</span></span>  
  
## <a name="agenda-update"></a><span data-ttu-id="18ce5-150">議題の更新</span><span class="sxs-lookup"><span data-stu-id="18ce5-150">Agenda Update</span></span>  
 <span data-ttu-id="18ce5-151">このアクティビティでは、後続の実行のルール エンジンの議題に追加される規則を示します。</span><span class="sxs-lookup"><span data-stu-id="18ce5-151">This activity indicates rules that are added to the rule engine agenda for subsequent execution.</span></span> <span data-ttu-id="18ce5-152">議題の更新プログラムのエントリの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="18ce5-152">The following is an example of an agenda update entry:</span></span>  
  
```  
AGENDA UPDATE 1/07/2004 5:33:13 PM  
Rule Engine Instance Identifier: f1dd3ff2-b4a8-4fe1-8d46-4d9b3e2502d3  
Ruleset Name: LoanProcessing  
Operation: Add  
Rule Name: Employment Status Rule  
Conflict Resolution Criteria: 0  
```  
  
 <span data-ttu-id="18ce5-153">上記の例では用語の一部の説明は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="18ce5-153">The descriptions for some of the terms in the preceding example are as follows:</span></span>  
  
-   <span data-ttu-id="18ce5-154">**操作です。**</span><span class="sxs-lookup"><span data-stu-id="18ce5-154">**Operation.**</span></span> <span data-ttu-id="18ce5-155">ルールの追加または議題から削除できます。</span><span class="sxs-lookup"><span data-stu-id="18ce5-155">Rules can be added or removed from the agenda.</span></span>  
  
-   <span data-ttu-id="18ce5-156">**規則の名前。**</span><span class="sxs-lookup"><span data-stu-id="18ce5-156">**Rule Name.**</span></span> <span data-ttu-id="18ce5-157">議題に追加されている規則の名前。</span><span class="sxs-lookup"><span data-stu-id="18ce5-157">The name of the rule that is being added to the agenda.</span></span>  
  
-   <span data-ttu-id="18ce5-158">**競合解決条件。**</span><span class="sxs-lookup"><span data-stu-id="18ce5-158">**Conflict Resolution Criteria.**</span></span> <span data-ttu-id="18ce5-159">アクションが実行される相対的な順序を決定するルールの優先順位 (優先順位の高いアクションが最初に実行されます)。</span><span class="sxs-lookup"><span data-stu-id="18ce5-159">The priority of a rule, which determines the relative order in which actions are executed (higher-priority actions are executed first).</span></span>  
  
## <a name="rule-fired"></a><span data-ttu-id="18ce5-160">実行されたルール</span><span class="sxs-lookup"><span data-stu-id="18ce5-160">Rule Fired</span></span>  
 <span data-ttu-id="18ce5-161">このアクティビティでは、ルールのアクションの実行を示します。</span><span class="sxs-lookup"><span data-stu-id="18ce5-161">This activity indicates the execution of a rule's actions.</span></span> <span data-ttu-id="18ce5-162">実行されたルールのエントリの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="18ce5-162">The following is an example of a rule fired entry:</span></span>  
  
```  
RULE FIRED 1/07/2004 5:33:13 PM  
Rule Engine Instance Identifier: f1dd3ff2-b4a8-4fe1-8d46-4d9b3e2502d3  
Ruleset Name: LoanProcessing  
Rule Name: Residency Status Rule  
Conflict Resolution Criteria: 10  
```