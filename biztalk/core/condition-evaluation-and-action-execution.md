---
title: 条件の評価とアクションの実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3d971f805ab546bd758166429bdca47e5073a72
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356492"
---
# <a name="condition-evaluation-and-action-execution"></a><span data-ttu-id="78a64-102">条件の評価とアクションの実行</span><span class="sxs-lookup"><span data-stu-id="78a64-102">Condition Evaluation and Action Execution</span></span>
<span data-ttu-id="78a64-103">ビジネス ルール フレームワークでは、ルールを .NET オブジェクト、XML ドキュメント、またはデータベース テーブルにリンクできる効率的な推論エンジンを提供します。</span><span class="sxs-lookup"><span data-stu-id="78a64-103">The Business Rules Framework provides a highly efficient inference engine capable of linking rules to .NET objects, XML documents, or database tables.</span></span>  
  
 <span data-ttu-id="78a64-104">ビジネス ルール エンジンは、ポリシーの実行に 3 つのステージのアルゴリズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="78a64-104">The Business Rule Engine uses a three-stage algorithm for policy execution.</span></span> <span data-ttu-id="78a64-105">各段階は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="78a64-105">The stages are as follows:</span></span>  
  
- <span data-ttu-id="78a64-106">**一致**します。</span><span class="sxs-lookup"><span data-stu-id="78a64-106">**Match**.</span></span> <span data-ttu-id="78a64-107">一致ステージでは、ファクトはファクトの種類 (オブジェクト参照は、ルール エンジンの作業メモリに保持) を使用する述語と照合されます、ルールの条件で定義された述語を使用します。</span><span class="sxs-lookup"><span data-stu-id="78a64-107">In the match stage, facts are matched against the predicates that use the fact type (object references maintained in the rule engine's working memory) using the predicates defined in the rule conditions.</span></span> <span data-ttu-id="78a64-108">、効率を高める、ポリシー内のすべてのルールで行われるパターンに一致して、ルール間で共有される条件が 1 回だけ一致します。</span><span class="sxs-lookup"><span data-stu-id="78a64-108">For the sake of efficiency, pattern matching occurs over all the rules in the policy, and conditions that are shared across rules are matched only once.</span></span> <span data-ttu-id="78a64-109">部分的な条件の一致を後続のパターン マッチング操作を短縮するための作業メモリに格納できます。</span><span class="sxs-lookup"><span data-stu-id="78a64-109">Partial condition matches may be stored in working memory to expedite subsequent pattern-matching operations.</span></span> <span data-ttu-id="78a64-110">パターン照合フェーズの出力は、ルール エンジンの議題の更新プログラムで構成されます。</span><span class="sxs-lookup"><span data-stu-id="78a64-110">The output of the pattern-matching phase consists of updates to the rule engine agenda.</span></span>  
  
- <span data-ttu-id="78a64-111">**競合解決**します。</span><span class="sxs-lookup"><span data-stu-id="78a64-111">**Conflict resolution**.</span></span> <span data-ttu-id="78a64-112">競合解決の段階で、事前に定義された解決スキームに基づいて、次の一連のルールのアクションを実行するかを判断する実行の候補となる規則が確認されます。</span><span class="sxs-lookup"><span data-stu-id="78a64-112">In the conflict resolution stage, the rules that are candidates for execution are examined to determine the next set of rule actions to execute based on a predetermined resolution scheme.</span></span> <span data-ttu-id="78a64-113">照合ステージ中に検出されたすべての候補ルールは、ルール エンジンの議題に追加されます。</span><span class="sxs-lookup"><span data-stu-id="78a64-113">All candidate rules found during the matching stage are added to the rule engine's agenda.</span></span>  
  
   <span data-ttu-id="78a64-114">既定の競合解決スキームは、ポリシー内でルールの優先度に基づいています。</span><span class="sxs-lookup"><span data-stu-id="78a64-114">The default conflict resolution scheme is based on rule priorities within a policy.</span></span> <span data-ttu-id="78a64-115">優先順位は、ビジネス ルール作成ツールでルールの構成可能なプロパティです。</span><span class="sxs-lookup"><span data-stu-id="78a64-115">The priority is a configurable property of a rule in the Business Rule Composer.</span></span> <span data-ttu-id="78a64-116">数値が大きいほど、高いほど、優先度はしたがって複数のルールがトリガーされた場合、優先順位の高いアクションは最初に実行されます。</span><span class="sxs-lookup"><span data-stu-id="78a64-116">The larger the number, the higher the priority; therefore if multiple rules are triggered, the higher-priority actions are executed first.</span></span>  
  
- <span data-ttu-id="78a64-117">**アクション**します。</span><span class="sxs-lookup"><span data-stu-id="78a64-117">**Action**.</span></span> <span data-ttu-id="78a64-118">アクション ステージでは、解決済みのルールのアクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="78a64-118">In the action stage, the actions in the resolved rule are executed.</span></span> <span data-ttu-id="78a64-119">ルールの処理は続行のサイクルがルール エンジンに新しいファクトをアサートすることができますに注意してください。</span><span class="sxs-lookup"><span data-stu-id="78a64-119">Note that rule actions can assert new facts into the rule engine, which causes the cycle to continue.</span></span> <span data-ttu-id="78a64-120">これは順行連鎖とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="78a64-120">This is also known as forward chaining.</span></span> <span data-ttu-id="78a64-121">アルゴリズムは、現在実行中のルールを決して横取りに注意してください。</span><span class="sxs-lookup"><span data-stu-id="78a64-121">It is important to note that the algorithm never preempts the currently executing rule.</span></span> <span data-ttu-id="78a64-122">現在発生しているルールのすべてのアクションは、一致フェーズが繰り返される前に実行されます。</span><span class="sxs-lookup"><span data-stu-id="78a64-122">All actions for the rule that is currently firing will be executed before the match phase is repeated.</span></span> <span data-ttu-id="78a64-123">ただし、一致フェーズがもう一度開始する前に、議題の他のルールは起動しません。</span><span class="sxs-lookup"><span data-stu-id="78a64-123">However, other rules on the agenda will not be fired before the match phase begins again.</span></span> <span data-ttu-id="78a64-124">一致フェーズを実行する前に、議題から削除する議題のこれらのルールがあります。</span><span class="sxs-lookup"><span data-stu-id="78a64-124">The match phase may cause those rules on the agenda to be removed from the agenda before they ever fire.</span></span>  
  
  <span data-ttu-id="78a64-125">次の例は、一致-競合解決-アクションの 3 つのステージのアルゴリズムを示しています。</span><span class="sxs-lookup"><span data-stu-id="78a64-125">The following example shows the three-stage algorithm of match-conflict resolution-action.</span></span>  
  
  <span data-ttu-id="78a64-126">**規則 1:収入を評価します。**</span><span class="sxs-lookup"><span data-stu-id="78a64-126">**Rule 1: Evaluate income**</span></span>  
  
- <span data-ttu-id="78a64-127">宣言型の表現。</span><span class="sxs-lookup"><span data-stu-id="78a64-127">Declarative representation:</span></span>  
  
   <span data-ttu-id="78a64-128">申請者の収入とローンの比率が 0.2 未満の場合にのみ、申請者の信用格付けを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78a64-128">An applicant's credit rating should be obtained only if the applicant's income-to-loan ratio is less than 0.2.</span></span>  
  
- <span data-ttu-id="78a64-129">場合は、ビジネス オブジェクトを使用して表現から。</span><span class="sxs-lookup"><span data-stu-id="78a64-129">IF—THEN representation using business objects:</span></span>  
  
  ```  
  IF Application.Income / Property.Price < 0.2    
  THEN Assert new CreditRating( Application)   
  ```  
  
  <span data-ttu-id="78a64-130">**規則 2:信用格付けを評価します。**</span><span class="sxs-lookup"><span data-stu-id="78a64-130">**Rule 2: Evaluate credit rating**</span></span>  
  
- <span data-ttu-id="78a64-131">宣言型の表現。</span><span class="sxs-lookup"><span data-stu-id="78a64-131">Declarative representation:</span></span>  
  
   <span data-ttu-id="78a64-132">申請者の信用格付けが 725 を上回る場合にのみ、応募者を承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78a64-132">An applicant should be approved only if the applicant's credit rating is more than 725.</span></span>  
  
- <span data-ttu-id="78a64-133">場合、し、ビジネス オブジェクトを使用して形式。</span><span class="sxs-lookup"><span data-stu-id="78a64-133">IF—THEN Representation using business objects:</span></span>  
  
  ```  
  IF Application.SSN = CreditRating.SSN AND CreditRating.Value > 725    
  THEN SendApprovalLetter(Application)    
  ```  
  
  <span data-ttu-id="78a64-134">ファクトは、次の表にまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="78a64-134">The facts are summarized in the following table.</span></span>  
  
|<span data-ttu-id="78a64-135">[ファクト]</span><span class="sxs-lookup"><span data-stu-id="78a64-135">Fact</span></span>|<span data-ttu-id="78a64-136">フィールド</span><span class="sxs-lookup"><span data-stu-id="78a64-136">Fields</span></span>|  
|----------|------------|  
|<span data-ttu-id="78a64-137">Application-住宅ローン アプリケーションを表す XML ドキュメント</span><span class="sxs-lookup"><span data-stu-id="78a64-137">Application – An XML document representing a home loan application</span></span>|<span data-ttu-id="78a64-138">-Income $65,000 を =</span><span class="sxs-lookup"><span data-stu-id="78a64-138">-   Income = $65,000</span></span><br /><span data-ttu-id="78a64-139">-SSN = XXX-XX XXXX</span><span class="sxs-lookup"><span data-stu-id="78a64-139">-   SSN = XXX-XX-XXXX</span></span>|  
|<span data-ttu-id="78a64-140">プロパティ – 購入されているプロパティを表す XML ドキュメント</span><span class="sxs-lookup"><span data-stu-id="78a64-140">Property – An XML document representing the property being purchased</span></span>|<span data-ttu-id="78a64-141">-価格 $225,000 を =</span><span class="sxs-lookup"><span data-stu-id="78a64-141">-   Price = $225,000</span></span>|  
|<span data-ttu-id="78a64-142">CreditRating – ローン申請者の信用格付けを含む XML ドキュメント</span><span class="sxs-lookup"><span data-stu-id="78a64-142">CreditRating – An XML document containing the loan applicant's credit rating</span></span>|<span data-ttu-id="78a64-143">-値 = 0 ~ 800</span><span class="sxs-lookup"><span data-stu-id="78a64-143">-   Value = 0 – 800</span></span><br /><span data-ttu-id="78a64-144">-SSN = XXX-XX XXXX</span><span class="sxs-lookup"><span data-stu-id="78a64-144">-   SSN = XXX-XX-XXXX</span></span>|  
  
 <span data-ttu-id="78a64-145">最初に、ルール エンジンの作業メモリと議題が空です。</span><span class="sxs-lookup"><span data-stu-id="78a64-145">Initially the rule engine working memory and agenda are empty.</span></span> <span data-ttu-id="78a64-146">アプリケーションが Application と Property のファクトを追加した後、次のようにルール エンジン作業メモリと議題が更新されます。</span><span class="sxs-lookup"><span data-stu-id="78a64-146">After the application adds the Application and Property facts, the rule engine working memory and agenda are updated as follows.</span></span>  
  
|<span data-ttu-id="78a64-147">作業メモリ</span><span class="sxs-lookup"><span data-stu-id="78a64-147">Working memory</span></span>|<span data-ttu-id="78a64-148">議題</span><span class="sxs-lookup"><span data-stu-id="78a64-148">Agenda</span></span>|  
|--------------------|------------|  
|<span data-ttu-id="78a64-149">-アプリケーション</span><span class="sxs-lookup"><span data-stu-id="78a64-149">-   Application</span></span><br /><span data-ttu-id="78a64-150">-プロパティ</span><span class="sxs-lookup"><span data-stu-id="78a64-150">-   Property</span></span>|<span data-ttu-id="78a64-151">ルール 1</span><span class="sxs-lookup"><span data-stu-id="78a64-151">Rule 1</span></span>|  
  
 <span data-ttu-id="78a64-152">議題に追加されてルール 1 の条件 (Application.Income/Property.Price < 0.2) に評価される**true**一致フェーズ中にします。</span><span class="sxs-lookup"><span data-stu-id="78a64-152">Rule 1 is added to the agenda because its condition (Application.Income / Property.Price < 0.2) evaluated to **true** during the match phase.</span></span> <span data-ttu-id="78a64-153">CreditRating ファクト、作業メモリにルール 2 の条件が評価されなかったためです。</span><span class="sxs-lookup"><span data-stu-id="78a64-153">There is no CreditRating fact in working memory, so the condition for Rule 2 was not evaluated.</span></span> <span data-ttu-id="78a64-154">議題に専用のルールは、ルール 1 であるため、ルールが実行され、議題から消えます。</span><span class="sxs-lookup"><span data-stu-id="78a64-154">Because the only rule in the agenda is Rule 1, the rule is executed and then disappears from the agenda.</span></span> <span data-ttu-id="78a64-155">ルール 1 の結果を新しいファクト (申請者の CreditRating ドキュメント) で定義されている 1 つのアクション作業メモリに追加されます。</span><span class="sxs-lookup"><span data-stu-id="78a64-155">The single action defined for Rule 1 results in a new fact (CreditRating document for the applicant) being added to working memory.</span></span> <span data-ttu-id="78a64-156">ルール 1 の実行が完了すると、一致フェーズに制御が戻ります。</span><span class="sxs-lookup"><span data-stu-id="78a64-156">After the execution of Rule 1 completes, control returns to the match phase.</span></span> <span data-ttu-id="78a64-157">一致するようにのみ新しいオブジェクトは CreditRating ファクトでは、一致フェーズの結果次に示します。</span><span class="sxs-lookup"><span data-stu-id="78a64-157">Because the only new object to match is the CreditRating fact, the results of the match phase are as follows.</span></span>  
  
|<span data-ttu-id="78a64-158">作業メモリ</span><span class="sxs-lookup"><span data-stu-id="78a64-158">Working memory</span></span>|<span data-ttu-id="78a64-159">議題</span><span class="sxs-lookup"><span data-stu-id="78a64-159">Agenda</span></span>|  
|--------------------|------------|  
|<span data-ttu-id="78a64-160">-アプリケーション</span><span class="sxs-lookup"><span data-stu-id="78a64-160">-   Application</span></span><br /><span data-ttu-id="78a64-161">-プロパティ</span><span class="sxs-lookup"><span data-stu-id="78a64-161">-   Property</span></span><br /><span data-ttu-id="78a64-162">-   CreditRating</span><span class="sxs-lookup"><span data-stu-id="78a64-162">-   CreditRating</span></span>|<span data-ttu-id="78a64-163">Rule 2</span><span class="sxs-lookup"><span data-stu-id="78a64-163">Rule 2</span></span>|  
  
 <span data-ttu-id="78a64-164">この時点でルール 2 が実行され、申請者に、承認状を送信する関数の呼び出しで。</span><span class="sxs-lookup"><span data-stu-id="78a64-164">At this point Rule 2 is executed, resulting in the invocation of a function that sends an approval letter to the applicant.</span></span> <span data-ttu-id="78a64-165">Rule 2 が完了すると、順行連鎖アルゴリズムの実行は、一致フェーズに返します。</span><span class="sxs-lookup"><span data-stu-id="78a64-165">After Rule 2 has completed, execution of the forward-chaining algorithm returns to the match phase.</span></span> <span data-ttu-id="78a64-166">一致するように新しいファクトが不要になったため、議題が空、順行連鎖は終了し、そのポリシーの実行は完了します。</span><span class="sxs-lookup"><span data-stu-id="78a64-166">Because there are no longer new facts to match and the agenda is empty, forward chaining terminates and policy execution is complete.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78a64-167">参照</span><span class="sxs-lookup"><span data-stu-id="78a64-167">See Also</span></span>  
 [<span data-ttu-id="78a64-168">ルール エンジン</span><span class="sxs-lookup"><span data-stu-id="78a64-168">Rule Engine</span></span>](../core/rule-engine.md)