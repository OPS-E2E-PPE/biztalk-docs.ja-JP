---
title: "条件の評価とアクションの実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Action stage [Business Rules Engine]
- examples, business rules
- Business Rules Engine, policies
- Match stage [Business Rules Engine]
- business rules, examples
- Business Rules Engine, algorithm
- Business Rules Engine, examples
- conflict resolution [Business Rules Engine]
- Business Rules Engine, stages
ms.assetid: dcaa32c2-3403-4f54-92e2-128686bfc193
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2814a97c1907b1bb29eee2a718d04d14cfe901a6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="condition-evaluation-and-action-execution"></a><span data-ttu-id="07618-102">条件の評価とアクションの実行</span><span class="sxs-lookup"><span data-stu-id="07618-102">Condition Evaluation and Action Execution</span></span>
<span data-ttu-id="07618-103">ビジネス ルール フレームワークは、.NET オブジェクト、XML ドキュメント、データベース テーブルにルールをリンクすることができる効率的な推論エンジンを提供します。</span><span class="sxs-lookup"><span data-stu-id="07618-103">The Business Rules Framework provides a highly efficient inference engine capable of linking rules to .NET objects, XML documents, or database tables.</span></span>  
  
 <span data-ttu-id="07618-104">ビジネス ルール エンジンは、ポリシーの実行に 3 つのステージのアルゴリズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="07618-104">The Business Rule Engine uses a three-stage algorithm for policy execution.</span></span> <span data-ttu-id="07618-105">この 3 つのステージを次に示します。</span><span class="sxs-lookup"><span data-stu-id="07618-105">The stages are as follows:</span></span>  
  
-   <span data-ttu-id="07618-106">**一致**です。</span><span class="sxs-lookup"><span data-stu-id="07618-106">**Match**.</span></span> <span data-ttu-id="07618-107">一致ステージでは、ルール条件で定義された述語を使用して、ファクトの種類 (ルール エンジンの作業メモリに保存されているオブジェクト参照) を使用する述語とファクトが照合されます。</span><span class="sxs-lookup"><span data-stu-id="07618-107">In the match stage, facts are matched against the predicates that use the fact type (object references maintained in the rule engine's working memory) using the predicates defined in the rule conditions.</span></span> <span data-ttu-id="07618-108">パターン照合はポリシーのすべてのルールに対して行われますが、効率を高めるために、ルール間で共有される条件は一度しか照合されません。</span><span class="sxs-lookup"><span data-stu-id="07618-108">For the sake of efficiency, pattern matching occurs over all the rules in the policy, and conditions that are shared across rules are matched only once.</span></span> <span data-ttu-id="07618-109">条件の一致を部分的に作業メモリに保存することにより、以降のパターン照合操作の効率を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="07618-109">Partial condition matches may be stored in working memory to expedite subsequent pattern-matching operations.</span></span> <span data-ttu-id="07618-110">パターン照合フェーズの出力には、ルール エンジンの議題に対する更新が含まれています。</span><span class="sxs-lookup"><span data-stu-id="07618-110">The output of the pattern-matching phase consists of updates to the rule engine agenda.</span></span>  
  
-   <span data-ttu-id="07618-111">**競合解決**です。</span><span class="sxs-lookup"><span data-stu-id="07618-111">**Conflict resolution**.</span></span> <span data-ttu-id="07618-112">競合解決ステージでは、実行の候補となるルールを確認し、あらかじめ指定した解決スキームに基づいて、次に実行するルール アクションのセットを決定します。</span><span class="sxs-lookup"><span data-stu-id="07618-112">In the conflict resolution stage, the rules that are candidates for execution are examined to determine the next set of rule actions to execute based on a predetermined resolution scheme.</span></span> <span data-ttu-id="07618-113">一致ステージで検出された候補ルールはすべてルール エンジンの議題に追加されます。</span><span class="sxs-lookup"><span data-stu-id="07618-113">All candidate rules found during the matching stage are added to the rule engine's agenda.</span></span>  
  
     <span data-ttu-id="07618-114">既定の競合解決スキームでは、ポリシー内のルールの優先度がベースになります。</span><span class="sxs-lookup"><span data-stu-id="07618-114">The default conflict resolution scheme is based on rule priorities within a policy.</span></span> <span data-ttu-id="07618-115">優先度は、ビジネス ルール作成ツールで構成が可能なルールのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="07618-115">The priority is a configurable property of a rule in the Business Rule Composer.</span></span> <span data-ttu-id="07618-116">番号が大きいほど、優先度は高くなります。複数のルールが呼び出された場合は、優先度の高いアクションが最初に実行されます。</span><span class="sxs-lookup"><span data-stu-id="07618-116">The larger the number, the higher the priority; therefore if multiple rules are triggered, the higher-priority actions are executed first.</span></span>  
  
-   <span data-ttu-id="07618-117">**アクション**です。</span><span class="sxs-lookup"><span data-stu-id="07618-117">**Action**.</span></span> <span data-ttu-id="07618-118">アクション ステージでは、解決されたルールのアクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="07618-118">In the action stage, the actions in the resolved rule are executed.</span></span> <span data-ttu-id="07618-119">ルール アクションは、ルール エンジンに新しいファクトをアサートすることができるので、その結果、サイクルを継続できます。</span><span class="sxs-lookup"><span data-stu-id="07618-119">Note that rule actions can assert new facts into the rule engine, which causes the cycle to continue.</span></span> <span data-ttu-id="07618-120">これは順行連鎖とも呼びます。</span><span class="sxs-lookup"><span data-stu-id="07618-120">This is also known as forward chaining.</span></span> <span data-ttu-id="07618-121">重要な点は、現在実行中のルールがアルゴリズムに横取りされないということです。</span><span class="sxs-lookup"><span data-stu-id="07618-121">It is important to note that the algorithm never preempts the currently executing rule.</span></span> <span data-ttu-id="07618-122">現在実行中のルールのアクションはすべて、一致フェーズが繰り返される前に実行されます。</span><span class="sxs-lookup"><span data-stu-id="07618-122">All actions for the rule that is currently firing will be executed before the match phase is repeated.</span></span> <span data-ttu-id="07618-123">ただし、一致フェーズが再開しなければ、議題の他のルールが実行されることはありません。</span><span class="sxs-lookup"><span data-stu-id="07618-123">However, other rules on the agenda will not be fired before the match phase begins again.</span></span> <span data-ttu-id="07618-124">そのため、一致フェーズが原因で、議題の他のルールが実行前に議題から削除されることがあります。</span><span class="sxs-lookup"><span data-stu-id="07618-124">The match phase may cause those rules on the agenda to be removed from the agenda before they ever fire.</span></span>  
  
 <span data-ttu-id="07618-125">次の例は、一致 - 競合解決 - アクションの 3 つのステージのアルゴリズムを示します。</span><span class="sxs-lookup"><span data-stu-id="07618-125">The following example shows the three-stage algorithm of match-conflict resolution-action.</span></span>  
  
 <span data-ttu-id="07618-126">**ルール 1: 収入を評価します。**</span><span class="sxs-lookup"><span data-stu-id="07618-126">**Rule 1: Evaluate income**</span></span>  
  
-   <span data-ttu-id="07618-127">宣言型表記</span><span class="sxs-lookup"><span data-stu-id="07618-127">Declarative representation:</span></span>  
  
     <span data-ttu-id="07618-128">申請者の信用格付けは、申請者の収入とローンの比率が 0.2 未満の場合にのみ入手します。</span><span class="sxs-lookup"><span data-stu-id="07618-128">An applicant's credit rating should be obtained only if the applicant's income-to-loan ratio is less than 0.2.</span></span>  
  
-   <span data-ttu-id="07618-129">場合は、ビジネス オブジェクトを使用して表現し。</span><span class="sxs-lookup"><span data-stu-id="07618-129">IF—THEN representation using business objects:</span></span>  
  
    ```  
    IF Application.Income / Property.Price < 0.2    
    THEN Assert new CreditRating( Application)   
    ```  
  
 <span data-ttu-id="07618-130">**信用格付けの評価ルール 2。**</span><span class="sxs-lookup"><span data-stu-id="07618-130">**Rule 2: Evaluate credit rating**</span></span>  
  
-   <span data-ttu-id="07618-131">宣言型表記</span><span class="sxs-lookup"><span data-stu-id="07618-131">Declarative representation:</span></span>  
  
     <span data-ttu-id="07618-132">申請者は、申請者の信用格付けが 725 を上回る場合にのみ承認されます。</span><span class="sxs-lookup"><span data-stu-id="07618-132">An applicant should be approved only if the applicant's credit rating is more than 725.</span></span>  
  
-   <span data-ttu-id="07618-133">場合など、ビジネス オブジェクトを使用して形式。</span><span class="sxs-lookup"><span data-stu-id="07618-133">IF—THEN Representation using business objects:</span></span>  
  
    ```  
    IF Application.SSN = CreditRating.SSN AND CreditRating.Value > 725    
    THEN SendApprovalLetter(Application)    
    ```  
  
 <span data-ttu-id="07618-134">ファクトを次の表にまとめます。</span><span class="sxs-lookup"><span data-stu-id="07618-134">The facts are summarized in the following table.</span></span>  
  
|<span data-ttu-id="07618-135">[ファクト]</span><span class="sxs-lookup"><span data-stu-id="07618-135">Fact</span></span>|<span data-ttu-id="07618-136">フィールド</span><span class="sxs-lookup"><span data-stu-id="07618-136">Fields</span></span>|  
|----------|------------|  
|<span data-ttu-id="07618-137">Application - 住宅ローン申請を表す XML ドキュメント</span><span class="sxs-lookup"><span data-stu-id="07618-137">Application – An XML document representing a home loan application</span></span>|<span data-ttu-id="07618-138">-Income ドル 65,000 を =</span><span class="sxs-lookup"><span data-stu-id="07618-138">-   Income = $65,000</span></span><br /><span data-ttu-id="07618-139">-SSN = XXX XX XXXX</span><span class="sxs-lookup"><span data-stu-id="07618-139">-   SSN = XXX-XX-XXXX</span></span>|  
|<span data-ttu-id="07618-140">Property - 購入する資産を表す XML ドキュメント</span><span class="sxs-lookup"><span data-stu-id="07618-140">Property – An XML document representing the property being purchased</span></span>|<span data-ttu-id="07618-141">-価格ドル 225,000 を =</span><span class="sxs-lookup"><span data-stu-id="07618-141">-   Price = $225,000</span></span>|  
|<span data-ttu-id="07618-142">CreditRating – ローン申請者の信用格付けが含まれる XML ドキュメント</span><span class="sxs-lookup"><span data-stu-id="07618-142">CreditRating – An XML document containing the loan applicant's credit rating</span></span>|<span data-ttu-id="07618-143">値 = 0 ~ 800</span><span class="sxs-lookup"><span data-stu-id="07618-143">-   Value = 0 – 800</span></span><br /><span data-ttu-id="07618-144">-SSN = XXX XX XXXX</span><span class="sxs-lookup"><span data-stu-id="07618-144">-   SSN = XXX-XX-XXXX</span></span>|  
  
 <span data-ttu-id="07618-145">ルール エンジン作業メモリと議題は、最初は空です。</span><span class="sxs-lookup"><span data-stu-id="07618-145">Initially the rule engine working memory and agenda are empty.</span></span> <span data-ttu-id="07618-146">Application と Property のファクトが追加されると、ルール エンジン作業メモリと議題は次のように更新されます。</span><span class="sxs-lookup"><span data-stu-id="07618-146">After the application adds the Application and Property facts, the rule engine working memory and agenda are updated as follows.</span></span>  
  
|<span data-ttu-id="07618-147">作業メモリ</span><span class="sxs-lookup"><span data-stu-id="07618-147">Working memory</span></span>|<span data-ttu-id="07618-148">議題</span><span class="sxs-lookup"><span data-stu-id="07618-148">Agenda</span></span>|  
|--------------------|------------|  
|<span data-ttu-id="07618-149">-アプリケーション</span><span class="sxs-lookup"><span data-stu-id="07618-149">-   Application</span></span><br /><span data-ttu-id="07618-150">-プロパティ</span><span class="sxs-lookup"><span data-stu-id="07618-150">-   Property</span></span>|<span data-ttu-id="07618-151">ルール 1</span><span class="sxs-lookup"><span data-stu-id="07618-151">Rule 1</span></span>|  
  
 <span data-ttu-id="07618-152">ルール 1 はため議題に追加されますその条件 (Application.Income/Property.Price < 0.2) に評価される**true**一致フェーズ中にします。</span><span class="sxs-lookup"><span data-stu-id="07618-152">Rule 1 is added to the agenda because its condition (Application.Income / Property.Price < 0.2) evaluated to **true** during the match phase.</span></span> <span data-ttu-id="07618-153">作業メモリに CreditRating ファクトは存在しないため、ルール 2 の条件は評価されません。</span><span class="sxs-lookup"><span data-stu-id="07618-153">There is no CreditRating fact in working memory, so the condition for Rule 2 was not evaluated.</span></span> <span data-ttu-id="07618-154">議題のルールはルール 1 のみなので、このルールは実行され、その後、議題から削除されます。</span><span class="sxs-lookup"><span data-stu-id="07618-154">Because the only rule in the agenda is Rule 1, the rule is executed and then disappears from the agenda.</span></span> <span data-ttu-id="07618-155">ルール 1 に定義された 1 つのアクションにより、新しいファクト (申請者の CreditRating ドキュメント) が作業メモリに追加されます。</span><span class="sxs-lookup"><span data-stu-id="07618-155">The single action defined for Rule 1 results in a new fact (CreditRating document for the applicant) being added to working memory.</span></span> <span data-ttu-id="07618-156">ルール 1 の実行が完了すると、制御が一致フェーズに戻されます。</span><span class="sxs-lookup"><span data-stu-id="07618-156">After the execution of Rule 1 completes, control returns to the match phase.</span></span> <span data-ttu-id="07618-157">照合対象となる新しいオブジェクトは CreditRating ファクトしかないため、一致フェーズの結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="07618-157">Because the only new object to match is the CreditRating fact, the results of the match phase are as follows.</span></span>  
  
|<span data-ttu-id="07618-158">作業メモリ</span><span class="sxs-lookup"><span data-stu-id="07618-158">Working memory</span></span>|<span data-ttu-id="07618-159">議題</span><span class="sxs-lookup"><span data-stu-id="07618-159">Agenda</span></span>|  
|--------------------|------------|  
|<span data-ttu-id="07618-160">-アプリケーション</span><span class="sxs-lookup"><span data-stu-id="07618-160">-   Application</span></span><br /><span data-ttu-id="07618-161">-プロパティ</span><span class="sxs-lookup"><span data-stu-id="07618-161">-   Property</span></span><br /><span data-ttu-id="07618-162">-CreditRating</span><span class="sxs-lookup"><span data-stu-id="07618-162">-   CreditRating</span></span>|<span data-ttu-id="07618-163">規則 2</span><span class="sxs-lookup"><span data-stu-id="07618-163">Rule 2</span></span>|  
  
 <span data-ttu-id="07618-164">この時点でルール 2 が実行され、申請者に対して承認通知を送付する機能が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="07618-164">At this point Rule 2 is executed, resulting in the invocation of a function that sends an approval letter to the applicant.</span></span> <span data-ttu-id="07618-165">ルール 2 が完了すると、順行連鎖アルゴリズムの実行は一致フェーズに戻されます。</span><span class="sxs-lookup"><span data-stu-id="07618-165">After Rule 2 has completed, execution of the forward-chaining algorithm returns to the match phase.</span></span> <span data-ttu-id="07618-166">照合する新しいファクトが存在せず、議題が空であるため、順行連鎖は終了し、ポリシー実行は完了します。</span><span class="sxs-lookup"><span data-stu-id="07618-166">Because there are no longer new facts to match and the agenda is empty, forward chaining terminates and policy execution is complete.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07618-167">参照</span><span class="sxs-lookup"><span data-stu-id="07618-167">See Also</span></span>  
 [<span data-ttu-id="07618-168">ルール エンジン</span><span class="sxs-lookup"><span data-stu-id="07618-168">Rule Engine</span></span>](../core/rule-engine.md)