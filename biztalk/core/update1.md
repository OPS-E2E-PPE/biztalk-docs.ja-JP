---
title: 更新プログラム 1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Update function [Business Rules Engine]
- Update function [Business Rules Engine], TypedXMLDocument
- Update function [Business Rules Engine], TypedData table
- Update function [Business Rules Engine], .NET objects
- .NET objects
- Update function [Business Rules Engine], DataConnection
ms.assetid: 939e45dc-6433-42f3-a336-8f3c247417ac
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccb9c8e8b75bc67954c30bf2b4a6e6ff39b3ee01
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008827"
---
# <a name="update"></a><span data-ttu-id="446a3-102">更新</span><span class="sxs-lookup"><span data-stu-id="446a3-102">Update</span></span>
<span data-ttu-id="446a3-103">ときに**Update**関数が呼び出されたオブジェクト、オブジェクトに再アサートされて再評価されることをエンジンに基づいて、新しいデータと状態。</span><span class="sxs-lookup"><span data-stu-id="446a3-103">When **Update** function is invoked an object, the object is reasserted into the engine to be re-evaluated, based on the new data and state.</span></span> <span data-ttu-id="446a3-104">型のオブジェクトを指定できます**TypedXmlDocument**または .NET クラスまたは**DataConnection**または**TypedDataTable**します。</span><span class="sxs-lookup"><span data-stu-id="446a3-104">The object can be of type **TypedXmlDocument** or .NET class or **DataConnection** or **TypedDataTable**.</span></span>  
  
 <span data-ttu-id="446a3-105">使用することも**Update**エンジンのパフォーマンスが向上し、このトピックの説明に従って、無限ループ シナリオを防止する関数。</span><span class="sxs-lookup"><span data-stu-id="446a3-105">You can also use **Update** function to improve engine performance and prevent endless loop scenarios as described in this topic.</span></span>  
  
 <span data-ttu-id="446a3-106">通常、使用して**Assert** 、ルール エンジンの作業メモリに新しいオブジェクトを配置し、使用する**更新**作業メモリ内の既存のオブジェクトを更新します。</span><span class="sxs-lookup"><span data-stu-id="446a3-106">Typically, you use **Assert** to place a new object in the working memory of the rule engine, and use **Update** to update an already existing object in the working memory.</span></span> <span data-ttu-id="446a3-107">新しいオブジェクトをアサートすると、すべてのルールの条件が評価されます。</span><span class="sxs-lookup"><span data-stu-id="446a3-107">When you assert a new object, conditions in all the rules are evaluated.</span></span> <span data-ttu-id="446a3-108">既存のオブジェクトを更新すると、更新されたファクトを使用する条件のみ再評価され、これらの条件が true に評価された場合にアクションが議題に追加されます。</span><span class="sxs-lookup"><span data-stu-id="446a3-108">When you update an existing object, only conditions that use the updated fact are reevaluated, and actions are added to the agenda if these conditions are evaluated to true.</span></span>  
  
## <a name="using-update-function-on-net-facts"></a><span data-ttu-id="446a3-109">.NET ファクトに対する Update 関数の使用</span><span class="sxs-lookup"><span data-stu-id="446a3-109">Using Update function on .NET facts</span></span>  
 <span data-ttu-id="446a3-110">例として 2 つのルールを示します。</span><span class="sxs-lookup"><span data-stu-id="446a3-110">Take the two rules that follow as an example.</span></span> <span data-ttu-id="446a3-111">オブジェクトと**ItemA**と**ItemB**作業メモリ内に存在します。</span><span class="sxs-lookup"><span data-stu-id="446a3-111">Suppose that objects **ItemA** and **ItemB** already exist in working memory.</span></span> <span data-ttu-id="446a3-112">ルール 1 の評価、 **Id**プロパティ**ItemA**、設定、 **Id**プロパティ**ItemB**、によって、および**ItemB**変更後にします。</span><span class="sxs-lookup"><span data-stu-id="446a3-112">Rule 1 evaluates the **Id** property on **ItemA**, sets the **Id** property on **ItemB**, and then reasserts **ItemB** after the change.</span></span> <span data-ttu-id="446a3-113">ときに**ItemB**が再アサートされた場合は、新しいオブジェクトとして扱われ、エンジンはオブジェクトを使用するすべてのルールを再評価**ItemB**述語またはアクションにします。</span><span class="sxs-lookup"><span data-stu-id="446a3-113">When **ItemB** is reasserted, it is treated as a new object and the engine re-evaluates all rules that use object **ItemB** in the predicates or actions.</span></span> <span data-ttu-id="446a3-114">これによりルール 2 の新しい値に対して再評価が**ItemB.Id**ルール 1 で設定します。</span><span class="sxs-lookup"><span data-stu-id="446a3-114">This ensures that Rule 2 is re-evaluated against the new value of **ItemB.Id**, as set in Rule 1.</span></span> <span data-ttu-id="446a3-115">Rule 2 は、最初にそれは評価されましたに評価できなかった可能性があります**true** 2 回目に評価されます。</span><span class="sxs-lookup"><span data-stu-id="446a3-115">Rule 2 may have failed the first time it was evaluated, but evaluates to **true** the second time it is evaluated.</span></span>  
  
### <a name="rule-1"></a><span data-ttu-id="446a3-116">ルール 1</span><span class="sxs-lookup"><span data-stu-id="446a3-116">Rule 1</span></span>  
  
```  
IF ItemA.Id == 1  
THEN ItemB.Id = 2  
Assert(ItemB)  
```  
  
### <a name="rule-2"></a><span data-ttu-id="446a3-117">Rule 2</span><span class="sxs-lookup"><span data-stu-id="446a3-117">Rule 2</span></span>  
  
```  
IF ItemB.Id == 2  
THEN ItemB.Value = 100  
```  
  
 <span data-ttu-id="446a3-118">オブジェクトを作業メモリに再度アサートする機能により、ユーザーは、順行連鎖シナリオでの動作を明示的に制御できます。</span><span class="sxs-lookup"><span data-stu-id="446a3-118">This ability to reassert objects into working memory allows the user explicit control over the behavior in forward-chaining scenarios.</span></span> <span data-ttu-id="446a3-119">しかし、この例では再アサーションの副作用により、ルール 1 も再評価されます。</span><span class="sxs-lookup"><span data-stu-id="446a3-119">A side effect of the reassertion in this example, however, is that Rule 1 is also re-evaluated.</span></span> <span data-ttu-id="446a3-120">**ItemA.Id**は変更されませんでした、ルール 1 にもう一度評価**true**と**assert (itemb)** 操作をもう一度起動します。</span><span class="sxs-lookup"><span data-stu-id="446a3-120">Because **ItemA.Id** was not changed, Rule 1 again evaluates to **true** and the **Assert(ItemB)** action fires again.</span></span> <span data-ttu-id="446a3-121">その結果、無限ループが発生します。</span><span class="sxs-lookup"><span data-stu-id="446a3-121">As a result, the rule creates an endless loop situation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="446a3-122">ルールの再評価の既定の最大ループ カウントが 2 ^32 です。</span><span class="sxs-lookup"><span data-stu-id="446a3-122">The default maximum loop count of re-evaluation of rules is 2^32.</span></span> <span data-ttu-id="446a3-123">ルールによって、ポリシーの実行でした時間の最後の。</span><span class="sxs-lookup"><span data-stu-id="446a3-123">For certain rules, the policy execution could last for a long time.</span></span> <span data-ttu-id="446a3-124">調整することによって、数を減らせる、**実行ループの最大の深さ**ポリシーのバージョンのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="446a3-124">You can reduce the count by adjusting the **Maximum Execution Loop Depth** property of the policy version.</span></span>  
  
 <span data-ttu-id="446a3-125">無限ループを作成せずにオブジェクトを再アサートできる必要があります、 **Update**関数は、この機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="446a3-125">You need to be able to reassert objects without creating endless loops, and the **Update** function provides this capability.</span></span> <span data-ttu-id="446a3-126">を再アサートと同様、 **Update**関数を実行します**Retract**と**Assert** 、関連付けられているオブジェクトのインスタンスのこれから変更されているルールのアクションが、2 つを使用する必要があります。主な違い:</span><span class="sxs-lookup"><span data-stu-id="446a3-126">Like a reassert, the **Update** function performs **Retract** and **Assert** of the associated object instances, which have been changed from rule actions, but there are two key differences:</span></span>  
  
- <span data-ttu-id="446a3-127">そのインスタンスの種類が述語ではなくアクションのみで使用されるルールでは、議題に含まれるアクションが議題に維持されます。</span><span class="sxs-lookup"><span data-stu-id="446a3-127">Actions on the agenda for rules where the instance type is only used in the actions (not the predicates) will remain on the agenda.</span></span>  
  
- <span data-ttu-id="446a3-128">そのインスタンスの種類をアクションのみで使用するルールは再評価されません。</span><span class="sxs-lookup"><span data-stu-id="446a3-128">Rules that only use the instance type in the actions will not be re-evaluated.</span></span>  
  
  <span data-ttu-id="446a3-129">したがって、述語のみ、または述語とアクションの両方でインスタンスの種類を使用するルールが再評価され、そのアクションが議題に適切に追加されます。</span><span class="sxs-lookup"><span data-stu-id="446a3-129">Therefore, rules that use the instance types in either the predicates only or both the predicates and actions will be re-evaluated and their actions added to the agenda as appropriate.</span></span>  
  
  <span data-ttu-id="446a3-130">使用する前の例を変更する、 **Update**関数によりため、ルール 2 のみが再評価される**ItemB**ルール 2 の条件に使用されます。</span><span class="sxs-lookup"><span data-stu-id="446a3-130">Changing the preceding example to use the **Update** function ensures that only Rule 2 is re-evaluated because **ItemB** is used in the condition of Rule 2.</span></span> <span data-ttu-id="446a3-131">ルール 1 は再評価されません**ItemB**は、ループ シナリオ、ルール 1 のアクションでのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="446a3-131">Rule 1 is not reevaluated because **ItemB** is only used in the actions of Rule 1, eliminating the looping scenario.</span></span>  
  
### <a name="rule-1"></a><span data-ttu-id="446a3-132">ルール 1</span><span class="sxs-lookup"><span data-stu-id="446a3-132">Rule 1</span></span>  
  
```  
IF ItemA.Id == 1  
THEN ItemB.Id = 2  
Update(ItemB)  
```  
  
### <a name="rule-2"></a><span data-ttu-id="446a3-133">Rule 2</span><span class="sxs-lookup"><span data-stu-id="446a3-133">Rule 2</span></span>  
  
```  
IF ItemB.Id == 2  
THEN ItemB.Value = 100  
```  
  
 <span data-ttu-id="446a3-134">しかし、まだループ シナリオが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="446a3-134">However, it is still possible to create looping scenarios.</span></span> <span data-ttu-id="446a3-135">たとえば、次のルールを検討してください。</span><span class="sxs-lookup"><span data-stu-id="446a3-135">For example, consider the following rule.</span></span>  
  
### <a name="rule-1"></a><span data-ttu-id="446a3-136">ルール 1</span><span class="sxs-lookup"><span data-stu-id="446a3-136">Rule 1</span></span>  
  
```  
IF ItemA.Id == 1  
THEN ItemA.Value = 20  
Update(ItemA)  
```  
  
 <span data-ttu-id="446a3-137">**ItemA**される述語では、そのときに再評価されます**更新**で呼び出される**ItemA**します。</span><span class="sxs-lookup"><span data-stu-id="446a3-137">Because **ItemA** is used in the predicate, it is re-evaluated when **Update** is called on **ItemA**.</span></span> <span data-ttu-id="446a3-138">場合の値**ItemA.Id**その他の場所は変更されませんに評価されるルール 1 は**true**原因となる、 **Update** A. でもう一度呼び出されますルール デザイナーは、このようなループ シナリオは作成されないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="446a3-138">If the value of **ItemA.Id** is not changed elsewhere, Rule 1 continues to evaluate to **true**, causing **Update** to once again be called on A. The rule designer must ensure that looping scenarios such as this are not created.</span></span>  
  
 <span data-ttu-id="446a3-139">この場合の適切なアプローチは、ルールの特性により異なります。</span><span class="sxs-lookup"><span data-stu-id="446a3-139">The appropriate approach for this will differ based on the nature of the rules.</span></span> <span data-ttu-id="446a3-140">前の例の問題を解決するための簡単なメカニズムを次に示します。</span><span class="sxs-lookup"><span data-stu-id="446a3-140">The following is a simple mechanism to solve the problem in the preceding example.</span></span>  
  
 <span data-ttu-id="446a3-141">**Update**関数は、クラスへの参照でビジネス ルール作成ツールで使用できますのと同様、 **Assert**、 **Retract**、または**RetractByType**関数。</span><span class="sxs-lookup"><span data-stu-id="446a3-141">The **Update** function may be used in the Business Rule Composer with a reference to the class, as with the **Assert**, **Retract**, or **RetractByType** functions.</span></span>  
  
### <a name="rule-1"></a><span data-ttu-id="446a3-142">ルール 1</span><span class="sxs-lookup"><span data-stu-id="446a3-142">Rule 1</span></span>  
  
```  
IF ItemA.Id == 1 and ItemA.Value != 20  
THEN ItemA.Value = 20  
Update(ItemA)  
```  
  
 <span data-ttu-id="446a3-143">チェックを追加する**ItemA.Value**ルール 1 に評価されることを防ぎます**true**もう一度ルール 1 のアクションには、最初の時間が実行された後です。</span><span class="sxs-lookup"><span data-stu-id="446a3-143">Adding the check on **ItemA.Value** prevents Rule 1 from evaluating to **true** again after the actions of Rule 1 are executed the first time.</span></span>  
  
## <a name="using-update-function-on-xml-facts"></a><span data-ttu-id="446a3-144">XML ファクトに対する Update 関数の使用</span><span class="sxs-lookup"><span data-stu-id="446a3-144">Using Update function on XML facts</span></span>  
 <span data-ttu-id="446a3-145">例として 2 つのルールを示します。</span><span class="sxs-lookup"><span data-stu-id="446a3-145">Take the two rules that follow as an example.</span></span> <span data-ttu-id="446a3-146">次のものとします。</span><span class="sxs-lookup"><span data-stu-id="446a3-146">Suppose that.</span></span> <span data-ttu-id="446a3-147">ルール 1 では注文書メッセージの項目の合計数を評価します。合計数が 10 以上である場合、ルール 2 により状態は "Needs approval" に設定されます。</span><span class="sxs-lookup"><span data-stu-id="446a3-147">Rule 1 evaluates the total count of the items in a purchase order message, and rule2 sets the status to "Needs approval" if the total count is greater than or equal to 10.</span></span>  
  
### <a name="rule-1"></a><span data-ttu-id="446a3-148">ルール 1</span><span class="sxs-lookup"><span data-stu-id="446a3-148">Rule 1</span></span>  
  
```  
IF 1 == 1  
THEN ProcessPO.Order:/Order/Items/TotalCount = (ProcessPO.Order:/Order/Items/TotalCount + ProcessPO:/Order/Items/Item/Count)  
```  
  
### <a name="rule-2"></a><span data-ttu-id="446a3-149">Rule 2</span><span class="sxs-lookup"><span data-stu-id="446a3-149">Rule 2</span></span>  
  
```  
IF ProcessPO.Order:/Order/Items/TotalCount >= 10  
THEN ProcessPO.Order:/Order/Status = "Needs approval"  
```  
  
 <span data-ttu-id="446a3-150">このポリシーへの入力として、次の発注書 (PO) メッセージを渡すと、合計項目数は 14 場合でも、状態は"Needs approval"に設定しないことがわかります。</span><span class="sxs-lookup"><span data-stu-id="446a3-150">If you pass the following purchase order (PO) message as an input to this policy, you notice that the status is not set to "Needs approval" even though the total item count is 14.</span></span> <span data-ttu-id="446a3-151">あるため、rule2 が先頭にのみ評価されるときの値、 **TotalCount**フィールドは 0、およびルールは、合計使用可能なカウントが更新されるたびに評価されません。</span><span class="sxs-lookup"><span data-stu-id="446a3-151">It is because that the rule2 is evaluated only at the beginning when the value of the **TotalCount** field is 0, and the rule is not evaluated each time the total available count is updated.</span></span> <span data-ttu-id="446a3-152">条件があるたびに再評価されます、 **TotalCount**を呼び出す必要があります、更新、**更新**親ノードでの関数 (**項目**) 変更されたノード (**TotalCount**)。</span><span class="sxs-lookup"><span data-stu-id="446a3-152">To have the conditions reevaluated each time the **TotalCount** is updated, you need to call the **Update** function on the parent node (**Items**) of the modified node (**TotalCount**).</span></span> <span data-ttu-id="446a3-153">ルール 1 を次に示すように変更し、もう一度テストすると、Status フィールドの値は "Needs Approval" に設定されます。</span><span class="sxs-lookup"><span data-stu-id="446a3-153">If you change the Rule1 as shown below, and test it one more time, you should see the value of the Status field set to "Needs Approval".</span></span>  
  
```  
<ns0:Order xmlns:ns0="http://ProcessPO.Order">  
    <Items>  
        <Item>  
            <Id>ITM1</Id>  
            <Count>2</Count>  
        </Item>  
        <Item>  
            <Id>ITM2</Id>  
            <Count>5</Count>  
        </Item>  
        <Item>  
            <Id>ITM3</Id>  
            <Count>7</Count>  
        </Item>  
        <TotalCount>0</TotalCount>  
    </Items>  
    <Status>No approval needed</Status>  
</ns0:Order>  
```  
  
 <span data-ttu-id="446a3-154">変更された**ルール 1**のとおりです。</span><span class="sxs-lookup"><span data-stu-id="446a3-154">The modified **Rule 1** is as follows:</span></span>  
  
### <a name="rule-1"></a><span data-ttu-id="446a3-155">ルール 1</span><span class="sxs-lookup"><span data-stu-id="446a3-155">Rule 1</span></span>  
  
```  
IF 1 == 1  
THEN ProcessPO.Order:/Order/Items/TotalCount = (ProcessPO.Order:/Order/Items/TotalCount + ProcessPO:/Order/Items/Item/Count) AND  
Update(ProcessPO.Order:/Order/Items)  
```  
  
## <a name="using-update-function-on-database-facts"></a><span data-ttu-id="446a3-156">データベース ファクトに対する Update 関数の使用</span><span class="sxs-lookup"><span data-stu-id="446a3-156">Using Update function on database facts</span></span>  
  
### <a name="typeddatatable"></a><span data-ttu-id="446a3-157">TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="446a3-157">TypedDataTable</span></span>  
 <span data-ttu-id="446a3-158">場合**Update**で呼び出される、 **TypedDataTable**、 **Update**は関連付けられているすべてのエンジンによって呼び出されます**TypedDataRows**します。</span><span class="sxs-lookup"><span data-stu-id="446a3-158">If **Update** is called on a **TypedDataTable**, **Update** is called by the engine on all associated **TypedDataRows**.</span></span> <span data-ttu-id="446a3-159">**Update**個人で呼び出すことができますも**TypedDataRows**します。</span><span class="sxs-lookup"><span data-stu-id="446a3-159">**Update** may also be called on individual **TypedDataRows**.</span></span>  
  
### <a name="dataconnection"></a><span data-ttu-id="446a3-160">DataConnection</span><span class="sxs-lookup"><span data-stu-id="446a3-160">DataConnection</span></span>  
 <span data-ttu-id="446a3-161">更新を**DataConnection**はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="446a3-161">Update of a **DataConnection** is not supported.</span></span> <span data-ttu-id="446a3-162">使用**Assert**代わりにします。</span><span class="sxs-lookup"><span data-stu-id="446a3-162">Use **Assert** instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="446a3-163">参照</span><span class="sxs-lookup"><span data-stu-id="446a3-163">See Also</span></span>  
 [<span data-ttu-id="446a3-164">エンジン制御関数</span><span class="sxs-lookup"><span data-stu-id="446a3-164">Engine Control Functions</span></span>](../core/engine-control-functions.md)