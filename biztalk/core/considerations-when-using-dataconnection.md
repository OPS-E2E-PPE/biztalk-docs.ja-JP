---
title: DataConnection を使用する場合の考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Retract function [Business Rules Engine], DataConnection
- RetractByType function [Business Rules Engine], DataConnection
- Business Rules Engine, DataConnection tips
- Assert function [Business Rules Engine], DataConnection
- Update function [Business Rules Engine], DataConnection
ms.assetid: 1b4c8aa5-053f-43d7-9f5f-050383405fed
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3cf932f4082e36ed6704f848d38691326be5af66
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354637"
---
# <a name="considerations-when-using-dataconnection"></a><span data-ttu-id="ff50a-102">DataConnection を使用する場合の考慮事項</span><span class="sxs-lookup"><span data-stu-id="ff50a-102">Considerations When Using DataConnection</span></span>
<span data-ttu-id="ff50a-103">ビジネス ルール エンジンで DataConnection を使用する場合は、次を検討してください。</span><span class="sxs-lookup"><span data-stu-id="ff50a-103">Consider the following when using DataConnection with the Business Rule Engine.</span></span>  
  
## <a name="use-primary-keys"></a><span data-ttu-id="ff50a-104">主キーを使用します。</span><span class="sxs-lookup"><span data-stu-id="ff50a-104">Use primary keys</span></span>  
 <span data-ttu-id="ff50a-105">主キーがある場合は、2 つの行が等しいかどうかは、オブジェクトの比較ではなく、行、同じプライマリ キーであるかどうかによって決まります。</span><span class="sxs-lookup"><span data-stu-id="ff50a-105">When there is a primary key, the equality of two rows is determined by whether the rows have the same primary key, rather than by object comparison.</span></span> <span data-ttu-id="ff50a-106">行が確定され同じである場合は、1 つだけのコピーがメモリに保持され、他の解放されます。</span><span class="sxs-lookup"><span data-stu-id="ff50a-106">If the rows are determined to be the same, only one copy is retained in memory, and the other is released.</span></span> <span data-ttu-id="ff50a-107">これにより、少ないメモリ消費量。</span><span class="sxs-lookup"><span data-stu-id="ff50a-107">This results in less memory consumption.</span></span>  
  
 <span data-ttu-id="ff50a-108">ときに、 **DataConnection**がアサートされてルール エンジンに最初に、エンジンは、常にそのスキーマから主キーの情報の検索を試みます。</span><span class="sxs-lookup"><span data-stu-id="ff50a-108">When a **DataConnection** is asserted into the rule engine for the first time, the engine always tries to locate its primary key information from its schema.</span></span> <span data-ttu-id="ff50a-109">主キーが存在する場合の主キー情報が、取得され、以降のすべての評価で使用されます。</span><span class="sxs-lookup"><span data-stu-id="ff50a-109">If a primary key exists, primary key information is then retrieved and used in all subsequent evaluations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ff50a-110">主キーは、データベースに対する変更が必要な場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="ff50a-110">A primary key is mandatory if changes need to be made to the database.</span></span>  
  
## <a name="provide-a-running-transaction-to-the-dataconnection-whenever-possible"></a><span data-ttu-id="ff50a-111">可能な限り DataConnection に実行中のトランザクションを提供します。</span><span class="sxs-lookup"><span data-stu-id="ff50a-111">Provide a running transaction to the DataConnection whenever possible</span></span>  
 <span data-ttu-id="ff50a-112">トランザクションなしの各クエリにし、更新、 **DataConnection**ルール評価のさまざまな部分での結果を開始しますが、独自のクエリが異なると、ローカル トランザクションは別に返す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ff50a-112">Without a transaction, each query and update on the **DataConnection** initiates its own local transaction, and different queries might return different results in different parts of rule evaluations.</span></span> <span data-ttu-id="ff50a-113">ユーザーは、基になるデータベース テーブルの変更がある場合、一貫性のない動作にすることがあります。</span><span class="sxs-lookup"><span data-stu-id="ff50a-113">Users may experience inconsistent behavior if there are changes in the underlying database table.</span></span>  
  
 <span data-ttu-id="ff50a-114">使用できますが、 **DataConnection**テーブルが時間の経過と共に変更しない場合は、トランザクションを提供する、なしをお勧めトランザクションを使用する場合でも、 **DataConnection**ことのみです読み取り操作に使用されます。</span><span class="sxs-lookup"><span data-stu-id="ff50a-114">Although you can use a **DataConnection** without providing a transaction when the table does not change over time, it is recommended that a transaction be used even when the **DataConnection** is only being used for read operations.</span></span>  
  
 <span data-ttu-id="ff50a-115">ただし、トランザクションは、データを更新するときに常に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff50a-115">However, a transaction should always be used when updating data.</span></span>  
  
## <a name="number-of-queries-may-grow-linearly"></a><span data-ttu-id="ff50a-116">クエリの数が増大する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ff50a-116">Number of queries may grow linearly</span></span>  
 <span data-ttu-id="ff50a-117">クエリ、 **DataConnection**に対して実行されるクエリの数、参加している他のオブジェクトでパラメーター化される、 **DataConnection**結合オブジェクトの数に直接対応しています到達、 **DataConnection**します。</span><span class="sxs-lookup"><span data-stu-id="ff50a-117">As queries against the **DataConnection** are parameterized by other joined objects, the number of queries executed against the **DataConnection** corresponds directly to the number of joining objects reaching the **DataConnection**.</span></span> <span data-ttu-id="ff50a-118">そのため、結合オブジェクトの数に到達した場合、 **DataConnection**オブジェクト増大に対するクエリの数、 **DataConnection**も拡張されます。</span><span class="sxs-lookup"><span data-stu-id="ff50a-118">Therefore, if the number of joining objects reaching the **DataConnection** object grows linearly, the number of queries against the **DataConnection** will grow linearly as well.</span></span> <span data-ttu-id="ff50a-119">現時点では、クエリの数を削減するための最適化ではありません。</span><span class="sxs-lookup"><span data-stu-id="ff50a-119">Currently, there is no optimization in place to reduce the number of queries.</span></span>  
  
 <span data-ttu-id="ff50a-120">この例では、ルールを示します。</span><span class="sxs-lookup"><span data-stu-id="ff50a-120">An example of this is the rule:</span></span>  
  
```  
IF A.x = 7 AND DC.y = A.y  
THEN  
```  
  
 <span data-ttu-id="ff50a-121">表す、 **ObjectBinding**、dc、 **DataConnection**、x および y は A の属性を表すと DC と。</span><span class="sxs-lookup"><span data-stu-id="ff50a-121">A represents an **ObjectBinding**, DC represents a **DataConnection**, and x and y represent attributes of A and DC.</span></span>  
  
 <span data-ttu-id="ff50a-122">テストに合格する A のすべてのインスタンス (x = 7) を使用して生成されるクエリは、 **DataConnection**します。</span><span class="sxs-lookup"><span data-stu-id="ff50a-122">For every instance of A that passes the test (x = 7), a query is generated by using the **DataConnection**.</span></span> <span data-ttu-id="ff50a-123">多くの一致するインスタンスがある場合、同じ数のクエリの結果します。</span><span class="sxs-lookup"><span data-stu-id="ff50a-123">If there are many matching instances, the same number of queries results.</span></span>  
  
## <a name="use-or-conditions-with-caution"></a><span data-ttu-id="ff50a-124">注意して使用 OR 条件</span><span class="sxs-lookup"><span data-stu-id="ff50a-124">Use OR conditions with caution</span></span>  
 <span data-ttu-id="ff50a-125">ルールが論理積のみで使用する場合 (**AND**) 条件、テスト、およびクエリ実行される、できるだけ早い段階に渡されるオブジェクトのインスタンスが低下するようにします。</span><span class="sxs-lookup"><span data-stu-id="ff50a-125">If the rule uses only conjunctive (**AND**) conditions, tests and queries will be executed as early as possible, so instances of objects passing through will be reduced.</span></span> <span data-ttu-id="ff50a-126">その結果、それに続くに対するクエリの数**DataConnection**比例して制限されます。</span><span class="sxs-lookup"><span data-stu-id="ff50a-126">As a result, the number of queries against the subsequent **DataConnection** will be reduced proportionally.</span></span> <span data-ttu-id="ff50a-127">分離の場合 (**または**) 条件と**DataConnection**ルール評価は最後のクエリにプッシュされるすべての条件で一緒に使用します。</span><span class="sxs-lookup"><span data-stu-id="ff50a-127">If disjunctive (**OR**) conditions and a **DataConnection** are used together in a rule, all condition evaluations will be pushed to the final query.</span></span> <span data-ttu-id="ff50a-128">1 つ以上の場合**DataConnection**ルール、最後の 1 つの すべてのクエリ ステートメントは実質的に点を除いて、すべてのクエリで使用されます。</span><span class="sxs-lookup"><span data-stu-id="ff50a-128">If more than one **DataConnection** is used in a rule, all queries except the last one will effectively become a Select-ALL query statement.</span></span>  
  
 <span data-ttu-id="ff50a-129">一般に、勧め OR 条件を持つすべてのルールを 2 つ以上の個別のルールに分割するため、OR 条件の使用よりアトミックなルールの定義と比較してパフォーマンスが低下します。</span><span class="sxs-lookup"><span data-stu-id="ff50a-129">In general, it is better to split any rule with an OR condition into two or more discrete rules, because the use of OR conditions will decrease performance compared to the definition of more atomic rules.</span></span> <span data-ttu-id="ff50a-130">これはか Dataconnection を使用するかどうかに当てはまります。</span><span class="sxs-lookup"><span data-stu-id="ff50a-130">This is true whether DataConnections are used or not.</span></span>  
  
 <span data-ttu-id="ff50a-131">1 つの規則ではなく、論理積条件だけで構成される個別のルールの使用を検討することがありますも**または**条件。</span><span class="sxs-lookup"><span data-stu-id="ff50a-131">You may also consider using separate rules that consist only of conjunctive conditions instead of one rule with **OR** conditions.</span></span> <span data-ttu-id="ff50a-132">**または**条件、結合オブジェクトのすべてのインスタンスの乗算の速度でクエリの数が増加します。</span><span class="sxs-lookup"><span data-stu-id="ff50a-132">With **OR** conditions, the number of queries grows at the speed of multiplication of instances of all joining objects.</span></span> <span data-ttu-id="ff50a-133">次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff50a-133">This is shown in the following example.</span></span>  
  
```  
IF (A.x ==7 OR A.x == 8) AND DC.y == A.y  
THEN DC.z = 10  
```  
  
 <span data-ttu-id="ff50a-134">この例では A を表します、 **ObjectBinding**;Dc を**DataConnection**x、y、および A の属性を表す z と DC とします。</span><span class="sxs-lookup"><span data-stu-id="ff50a-134">In this example, A represents an **ObjectBinding**; DC represents a **DataConnection**, and x, y, and z represent attributes of A and DC.</span></span> <span data-ttu-id="ff50a-135">コマンドを実行する 100 個のクエリがある場合は 100 のインスタンスを持つ、x は 1、2 ~ 100 のオブジェクトの 100 で、2 番目のオブジェクトに最初のオブジェクトに、 **DataConnection**します。</span><span class="sxs-lookup"><span data-stu-id="ff50a-135">If A has 100 instances, and x is 1 in the first object, 2 in the second object, through 100 in the 100th object, 100 queries have to run against the **DataConnection**.</span></span>  
  
 <span data-ttu-id="ff50a-136">2 つのルールに分割して前のルールを書き直すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ff50a-136">It is better to rewrite the preceding rule by splitting it in to two rules.</span></span>  
  
 <span data-ttu-id="ff50a-137">**ルール 1**</span><span class="sxs-lookup"><span data-stu-id="ff50a-137">**Rule 1**</span></span>  
  
```  
IF A.x =7 AND DC.y = A.y  
THEN DC.z = 10  
```  
  
 <span data-ttu-id="ff50a-138">**Rule 2**</span><span class="sxs-lookup"><span data-stu-id="ff50a-138">**Rule 2**</span></span>  
  
```  
IF A.x = 8 AND DC.y = A.y  
THEN DC.z = 10  
```  
  
## <a name="sql-does-not-support-some-predicates-and-functions"></a><span data-ttu-id="ff50a-139">SQL は一部の述語と関数をサポートしていません</span><span class="sxs-lookup"><span data-stu-id="ff50a-139">SQL does not support some predicates and functions</span></span>  
 <span data-ttu-id="ff50a-140">一部の述語と、ルール エンジンでサポートされる関数は、SQL でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ff50a-140">Some predicates and functions that the rule engine supports are not supported by SQL.</span></span> <span data-ttu-id="ff50a-141">これらのサポートされていない述語と関数をルールの条件で使用する場合は、クエリに組み込むことはできません。</span><span class="sxs-lookup"><span data-stu-id="ff50a-141">If these unsupported predicates and functions are used in the rule conditions, it cannot be incorporated into the query.</span></span> <span data-ttu-id="ff50a-142">次の用語は、SQL クエリとして最適化できません。</span><span class="sxs-lookup"><span data-stu-id="ff50a-142">The following terms cannot be optimized as an SQL query:</span></span>  
  
-   <span data-ttu-id="ff50a-143">一部のエンジン組み込み関数があるありませんと同じ SQL クエリで。</span><span class="sxs-lookup"><span data-stu-id="ff50a-143">Some of the engine built-in functions have no equivalent in an SQL query.</span></span> <span data-ttu-id="ff50a-144">これらは**Power**、 **FindFirst**、および**FindAll**します。</span><span class="sxs-lookup"><span data-stu-id="ff50a-144">These are **Power**, **FindFirst**, and **FindAll**.</span></span> <span data-ttu-id="ff50a-145">使用して、 **DataConnection**列を 1 つ以上の引数として、クエリの一部として最適化できません; たとえば、Power (2, dc です。列 1)。</span><span class="sxs-lookup"><span data-stu-id="ff50a-145">Using a **DataConnection** column as one or more of their arguments cannot be optimized as part of a query; for example, Power( 2, dc.Column1).</span></span>  
  
-   <span data-ttu-id="ff50a-146">組み込みの述語 Match を使用する、 **DataConnection**列として、正規表現の引数 (最初の引数)。</span><span class="sxs-lookup"><span data-stu-id="ff50a-146">Built-in predicate Match that uses a **DataConnection** column as its regular expression argument (the first argument).</span></span> <span data-ttu-id="ff50a-147">たとえば、次のように一致 (「abc \*」、dc1 します。列 2) が有効ですが、一致 (dc1 します。Column1、dc1 します。列 2) を変換することはできません。</span><span class="sxs-lookup"><span data-stu-id="ff50a-147">For example, Match("abc\*", dc1.Column2) is valid, but Match(dc1.Column1, dc1.Column2) cannot be translated.</span></span>  
  
-   <span data-ttu-id="ff50a-148">持つユーザー関数を使用して、 **DataConnection**としてそのパラメーターの 1 つの列。</span><span class="sxs-lookup"><span data-stu-id="ff50a-148">Using a user function that has a **DataConnection** column as one of its parameters.</span></span> <span data-ttu-id="ff50a-149">たとえば、c1 です。M (dc です。ユーザー関数は、データベース サーバーで実行できませんが、ビジネス ルール エンジンによって実行される必要がありますので、Column1) を最適化することはできません。</span><span class="sxs-lookup"><span data-stu-id="ff50a-149">For example, c1.M(dc.Column1) cannot be optimized because the user function cannot execute on the database server, but must be executed by the Business Rule Engine.</span></span>  
  
-   <span data-ttu-id="ff50a-150">集合演算を表すユーザー関数、 **DataConnection**。 たとえば、dc です。Column1(5) します。</span><span class="sxs-lookup"><span data-stu-id="ff50a-150">User functions that represent set operations on the **DataConnection**; for example, dc.Column1(5).</span></span>  
  
-   <span data-ttu-id="ff50a-151">使用する関数、 **ObjectReference**を**DataConnection**。 例: ObjecRef(dc) します。</span><span class="sxs-lookup"><span data-stu-id="ff50a-151">Functions that use an **ObjectReference** to the **DataConnection**; for example, ObjecRef(dc).</span></span>  
  
-   <span data-ttu-id="ff50a-152">1 つ以上の関数の引数が変換可能な場合、関数呼び出しが乱す; になりますたとえば、追加 (c1 します。M (dc です。列 1)、5)。</span><span class="sxs-lookup"><span data-stu-id="ff50a-152">If one or more of a function's arguments is untranslatable, the function call becomes untranslatable; for example, Add(c1.M(dc.Column1), 5).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff50a-153">参照</span><span class="sxs-lookup"><span data-stu-id="ff50a-153">See Also</span></span>  
 [<span data-ttu-id="ff50a-154">ビジネス ルール エンジンでのデータ アクセス</span><span class="sxs-lookup"><span data-stu-id="ff50a-154">Data Access in the Business Rule Engine</span></span>](../core/data-access-in-the-business-rule-engine.md)