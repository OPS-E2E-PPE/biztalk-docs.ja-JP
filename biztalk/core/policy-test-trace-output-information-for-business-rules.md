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
ms.openlocfilehash: e8795e926d496f586d032bb85fe4a1fddb473ec5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005139"
---
# <a name="policy-test-trace-output-information-for-business-rules"></a><span data-ttu-id="71e0c-102">ビジネス ルールにおけるポリシー テストのトレース出力情報</span><span class="sxs-lookup"><span data-stu-id="71e0c-102">Policy Test Trace Output Information for Business Rules</span></span>
<span data-ttu-id="71e0c-103">このセクションでは、ビジネス ルール作成ツールでポリシーをテストする場合に表示される追跡情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="71e0c-103">This section provides information on the tracking information that is displayed when testing a policy in the Business Rule Composer.</span></span> <span data-ttu-id="71e0c-104">[グループ ハブ] ページでメッセージ イベントとサービス インスタンスの追跡クエリを使用してポリシー実行の追跡結果を表示すると、同様の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="71e0c-104">Very similar information is seen when viewing tracking results for policy execution using the message event and service instance tracking queries on the Group Hub page.</span></span>  
  
 <span data-ttu-id="71e0c-105">追跡出力に表示されるステートメントの種類には、次の 4 つがあります。</span><span class="sxs-lookup"><span data-stu-id="71e0c-105">There are four statement types that are displayed in the tracking output:</span></span>  
  
- <span data-ttu-id="71e0c-106">ファクト アクティビティ</span><span class="sxs-lookup"><span data-stu-id="71e0c-106">Fact Activity</span></span>  
  
- <span data-ttu-id="71e0c-107">条件の評価</span><span class="sxs-lookup"><span data-stu-id="71e0c-107">Condition Evaluation</span></span>  
  
- <span data-ttu-id="71e0c-108">議題の更新</span><span class="sxs-lookup"><span data-stu-id="71e0c-108">Agenda Update</span></span>  
  
- <span data-ttu-id="71e0c-109">実行されたルール</span><span class="sxs-lookup"><span data-stu-id="71e0c-109">Rule Fired</span></span>  
  
  <span data-ttu-id="71e0c-110">各ステートメントの種類を次に示します。</span><span class="sxs-lookup"><span data-stu-id="71e0c-110">Each statement type is described below.</span></span>  
  
## <a name="fact-activity"></a><span data-ttu-id="71e0c-111">ファクト アクティビティ</span><span class="sxs-lookup"><span data-stu-id="71e0c-111">Fact Activity</span></span>  
 <span data-ttu-id="71e0c-112">このステートメントは、エンジンの作業メモリに存在するファクトに対する変更を示します。</span><span class="sxs-lookup"><span data-stu-id="71e0c-112">This statement indicates changes to the facts present in the working memory of the engine.</span></span> <span data-ttu-id="71e0c-113">ファクト アクティビティのエントリの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="71e0c-113">The following is an example of a fact activity entry:</span></span>  
  
```  
FACT ACTIVITY 3/16/2004 9:50:28 AM  
Rule Engine Instance Identifier: 9effe3f9-d3ad-4125-99fa-56bb379188f7  
Ruleset Name: LoanProcessing  
Operation: Assert  
Object Type: MyTest.test  
Object Instance Identifier: 872  
```  
  
### <a name="rule-engine-instance-identifier"></a><span data-ttu-id="71e0c-114">ルール エンジン インスタンス識別子</span><span class="sxs-lookup"><span data-stu-id="71e0c-114">Rule Engine Instance Identifier</span></span>  
 <span data-ttu-id="71e0c-115">一意の識別子、 **RuleEngine**実行されているルールの実行環境を提供するインスタンス。</span><span class="sxs-lookup"><span data-stu-id="71e0c-115">Unique identifier for the **RuleEngine** instance that provides the execution environment for the rule firing.</span></span>  
  
### <a name="ruleset-name"></a><span data-ttu-id="71e0c-116">ルール セット名</span><span class="sxs-lookup"><span data-stu-id="71e0c-116">Ruleset Name</span></span>  
 <span data-ttu-id="71e0c-117">ルール セット (ポリシー) の名前です。</span><span class="sxs-lookup"><span data-stu-id="71e0c-117">The name of the rule set (policy).</span></span>  
  
### <a name="operation"></a><span data-ttu-id="71e0c-118">演算</span><span class="sxs-lookup"><span data-stu-id="71e0c-118">Operation</span></span>  
 <span data-ttu-id="71e0c-119">ファクト アクティビティでは、3 種類の操作があります。</span><span class="sxs-lookup"><span data-stu-id="71e0c-119">There are three types of operation that can occur in a fact activity:</span></span>  
  
 <span data-ttu-id="71e0c-120">Filter</span><span class="sxs-lookup"><span data-stu-id="71e0c-120">Assert</span></span>  
  
 <span data-ttu-id="71e0c-121">ファクトが作業メモリに追加されます。</span><span class="sxs-lookup"><span data-stu-id="71e0c-121">The fact is being added to the working memory.</span></span>  
  
 <span data-ttu-id="71e0c-122">更新</span><span class="sxs-lookup"><span data-stu-id="71e0c-122">Update</span></span>  
  
 <span data-ttu-id="71e0c-123">ファクトがルールによって更新されます。このファクトは、新しいデータおよび状態に基づいて、再評価するエンジンに再度アサートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="71e0c-123">The fact is being updated by a rule and then needs to be reasserted into the engine to be re-evaluated, based on the new data and state.</span></span>  
  
 <span data-ttu-id="71e0c-124">取り消し</span><span class="sxs-lookup"><span data-stu-id="71e0c-124">Retract</span></span>  
  
 <span data-ttu-id="71e0c-125">ファクトが作業メモリから削除されます。</span><span class="sxs-lookup"><span data-stu-id="71e0c-125">The fact is being removed from the working memory.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="71e0c-126">型と一致しません、ポリシーで使用される型のいずれかのファクトがアサートされると場合、アサート操作は「アサート-認識されないファクト」で表示されます。</span><span class="sxs-lookup"><span data-stu-id="71e0c-126">If a fact is asserted whose type does not match any of the types used in the policy, the Assert operation will display "Assert – Fact Unrecognized".</span></span>  
  
### <a name="object-type"></a><span data-ttu-id="71e0c-127">[オブジェクトの種類]</span><span class="sxs-lookup"><span data-stu-id="71e0c-127">Object Type</span></span>  
 <span data-ttu-id="71e0c-128">特定のアクティビティのファクトの種類です。</span><span class="sxs-lookup"><span data-stu-id="71e0c-128">The type of fact for a particular activity:</span></span>  
  
-   <span data-ttu-id="71e0c-129">DataConnection</span><span class="sxs-lookup"><span data-stu-id="71e0c-129">DataConnection</span></span>  
  
-   <span data-ttu-id="71e0c-130">TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="71e0c-130">TypedDataTable</span></span>  
  
-   <span data-ttu-id="71e0c-131">TypedDataRow</span><span class="sxs-lookup"><span data-stu-id="71e0c-131">TypedDataRow</span></span>  
  
     <span data-ttu-id="71e0c-132">TypedDataTable がアサートされると、含まれるすべての行が TypedDataRows としてアサートされます。</span><span class="sxs-lookup"><span data-stu-id="71e0c-132">When a TypedDataTable is asserted all of the contained rows are asserted as TypedDataRows.</span></span>  <span data-ttu-id="71e0c-133">DataConnection に関連付けられている TypedDataRows は、条件が評価され、結果のクエリが実行されるまで、アサートされません。</span><span class="sxs-lookup"><span data-stu-id="71e0c-133">TypedDataRows associated with a DataConnection are not asserted until a condition is evaluated and the resulting query is executed.</span></span>  
  
-   <span data-ttu-id="71e0c-134">TypedXmlDocument</span><span class="sxs-lookup"><span data-stu-id="71e0c-134">TypedXmlDocument</span></span>  
  
     <span data-ttu-id="71e0c-135">親と子の TypedXmlDocument インスタンスにアサーションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="71e0c-135">Assertions will be seen for both parent and child TypedXmlDocument instances.</span></span>  
  
### <a name="object-instance-identifier"></a><span data-ttu-id="71e0c-136">オブジェクト インスタンス識別子</span><span class="sxs-lookup"><span data-stu-id="71e0c-136">Object Instance Identifier</span></span>  
 <span data-ttu-id="71e0c-137">ファクト参照の一意のインスタンス ID。</span><span class="sxs-lookup"><span data-stu-id="71e0c-137">Unique instance ID of the fact reference.</span></span>  
  
## <a name="condition-evaluation"></a><span data-ttu-id="71e0c-138">条件の評価</span><span class="sxs-lookup"><span data-stu-id="71e0c-138">Condition Evaluation</span></span>  
 <span data-ttu-id="71e0c-139">このアクティビティは、個別の述語の評価結果を示します。</span><span class="sxs-lookup"><span data-stu-id="71e0c-139">This activity indicates the result of evaluating individual predicates.</span></span> <span data-ttu-id="71e0c-140">条件の評価のエントリの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="71e0c-140">The following is an example of a condition evaluation entry:</span></span>  
  
```  
CONDITION EVALUATION TEST (MATCH) 1/07/2004 5:33:13 PM  
Rule Engine Instance Identifier: f1dd3ff2-b4a8-4fe1-8d46-4d9b3e2502d3  
Ruleset Name: LoanProcessing  
Test Expression: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:Root.EmploymentType/TimeInMonths >= 18  
Left Operand Value: 31  
Right Operand Value: 18  
Test Result: True  
```  
  
 <span data-ttu-id="71e0c-141">前の例に記されている用語について説明します。</span><span class="sxs-lookup"><span data-stu-id="71e0c-141">The descriptions for some of the terms in the preceding example are as follows:</span></span>  
  
-   <span data-ttu-id="71e0c-142">**式をテストします。**</span><span class="sxs-lookup"><span data-stu-id="71e0c-142">**Test Expression.**</span></span> <span data-ttu-id="71e0c-143">ルール内の簡単な式 (単項式または二項式)。</span><span class="sxs-lookup"><span data-stu-id="71e0c-143">A simple (unary or binary) expression within a rule.</span></span>  
  
-   <span data-ttu-id="71e0c-144">**左側のオペランドの値。**</span><span class="sxs-lookup"><span data-stu-id="71e0c-144">**Left Operand Value.**</span></span> <span data-ttu-id="71e0c-145">式の左側の条件値です。</span><span class="sxs-lookup"><span data-stu-id="71e0c-145">The value of the term on the left side of an expression.</span></span>  
  
-   <span data-ttu-id="71e0c-146">**右側のオペランドの値。**</span><span class="sxs-lookup"><span data-stu-id="71e0c-146">**Right Operand Value.**</span></span> <span data-ttu-id="71e0c-147">式の右側の条件値です。</span><span class="sxs-lookup"><span data-stu-id="71e0c-147">The value of the term on the right side of an expression.</span></span>  
  
-   <span data-ttu-id="71e0c-148">**結果をテストします。**</span><span class="sxs-lookup"><span data-stu-id="71e0c-148">**Test Result.**</span></span> <span data-ttu-id="71e0c-149">評価の結果 (True または False のいずれか) です。</span><span class="sxs-lookup"><span data-stu-id="71e0c-149">The result of the evaluation, which is either True or False.</span></span>  
  
## <a name="agenda-update"></a><span data-ttu-id="71e0c-150">議題の更新</span><span class="sxs-lookup"><span data-stu-id="71e0c-150">Agenda Update</span></span>  
 <span data-ttu-id="71e0c-151">このアクティビティは、以降の実行に使用するルール エンジンの議題に追加されるルールを示します。</span><span class="sxs-lookup"><span data-stu-id="71e0c-151">This activity indicates rules that are added to the rule engine agenda for subsequent execution.</span></span> <span data-ttu-id="71e0c-152">議題の更新のエントリの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="71e0c-152">The following is an example of an agenda update entry:</span></span>  
  
```  
AGENDA UPDATE 1/07/2004 5:33:13 PM  
Rule Engine Instance Identifier: f1dd3ff2-b4a8-4fe1-8d46-4d9b3e2502d3  
Ruleset Name: LoanProcessing  
Operation: Add  
Rule Name: Employment Status Rule  
Conflict Resolution Criteria: 0  
```  
  
 <span data-ttu-id="71e0c-153">前の例に記されている用語について説明します。</span><span class="sxs-lookup"><span data-stu-id="71e0c-153">The descriptions for some of the terms in the preceding example are as follows:</span></span>  
  
-   <span data-ttu-id="71e0c-154">**操作です。**</span><span class="sxs-lookup"><span data-stu-id="71e0c-154">**Operation.**</span></span> <span data-ttu-id="71e0c-155">ルールを議題から追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="71e0c-155">Rules can be added or removed from the agenda.</span></span>  
  
-   <span data-ttu-id="71e0c-156">**規則の名前。**</span><span class="sxs-lookup"><span data-stu-id="71e0c-156">**Rule Name.**</span></span> <span data-ttu-id="71e0c-157">議題に追加されているルールの名前です。</span><span class="sxs-lookup"><span data-stu-id="71e0c-157">The name of the rule that is being added to the agenda.</span></span>  
  
-   <span data-ttu-id="71e0c-158">**競合解決条件。**</span><span class="sxs-lookup"><span data-stu-id="71e0c-158">**Conflict Resolution Criteria.**</span></span> <span data-ttu-id="71e0c-159">アクションが実行される相対的な順序を決定するルールの優先順位 (優先順位の高いアクションが最初に実行されます)。</span><span class="sxs-lookup"><span data-stu-id="71e0c-159">The priority of a rule, which determines the relative order in which actions are executed (higher-priority actions are executed first).</span></span>  
  
## <a name="rule-fired"></a><span data-ttu-id="71e0c-160">実行されたルール</span><span class="sxs-lookup"><span data-stu-id="71e0c-160">Rule Fired</span></span>  
 <span data-ttu-id="71e0c-161">このアクティビティは、ルールのアクションの実行を示します。</span><span class="sxs-lookup"><span data-stu-id="71e0c-161">This activity indicates the execution of a rule's actions.</span></span> <span data-ttu-id="71e0c-162">実行されたルールのエントリの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="71e0c-162">The following is an example of a rule fired entry:</span></span>  
  
```  
RULE FIRED 1/07/2004 5:33:13 PM  
Rule Engine Instance Identifier: f1dd3ff2-b4a8-4fe1-8d46-4d9b3e2502d3  
Ruleset Name: LoanProcessing  
Rule Name: Residency Status Rule  
Conflict Resolution Criteria: 10  
```