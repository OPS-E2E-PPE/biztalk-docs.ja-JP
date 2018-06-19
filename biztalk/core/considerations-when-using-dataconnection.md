---
title: DataConnection を使用する際の考慮事項 |Microsoft ドキュメント
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
ms.openlocfilehash: 1f99110daafa74cb16b6cc5b98e1382049bbb158
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "22238954"
---
# <a name="considerations-when-using-dataconnection"></a><span data-ttu-id="99e37-102">DataConnection を使用する際の注意事項</span><span class="sxs-lookup"><span data-stu-id="99e37-102">Considerations When Using DataConnection</span></span>
<span data-ttu-id="99e37-103">ビジネス ルール エンジンで DataConnection を使用する際の注意事項を、次に示します。</span><span class="sxs-lookup"><span data-stu-id="99e37-103">Consider the following when using DataConnection with the Business Rule Engine.</span></span>  
  
## <a name="use-primary-keys"></a><span data-ttu-id="99e37-104">主キーを使用する</span><span class="sxs-lookup"><span data-stu-id="99e37-104">Use primary keys</span></span>  
 <span data-ttu-id="99e37-105">主キーが存在する場合、2 つの行が等しいかどうかは、オブジェクトの比較ではなく同じ主キーを使用するかどうかで決まります。</span><span class="sxs-lookup"><span data-stu-id="99e37-105">When there is a primary key, the equality of two rows is determined by whether the rows have the same primary key, rather than by object comparison.</span></span> <span data-ttu-id="99e37-106">行が同一であると判断された場合、1 つのコピーだけがメモリに保持され、もう一方は解放されます。</span><span class="sxs-lookup"><span data-stu-id="99e37-106">If the rows are determined to be the same, only one copy is retained in memory, and the other is released.</span></span> <span data-ttu-id="99e37-107">これによって、メモリの消費が少なくなります。</span><span class="sxs-lookup"><span data-stu-id="99e37-107">This results in less memory consumption.</span></span>  
  
 <span data-ttu-id="99e37-108">ときに、 **DataConnection** がアサートされてルール エンジンに最初に、エンジンが常がそのスキーマからの主キー情報を特定します。</span><span class="sxs-lookup"><span data-stu-id="99e37-108">When a **DataConnection** is asserted into the rule engine for the first time, the engine always tries to locate its primary key information from its schema.</span></span> <span data-ttu-id="99e37-109">主キーが存在する場合、主キーの情報が取得され、後続のすべての評価で使用されます。</span><span class="sxs-lookup"><span data-stu-id="99e37-109">If a primary key exists, primary key information is then retrieved and used in all subsequent evaluations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="99e37-110">データベースに変更を加える場合、主キーが必要です。</span><span class="sxs-lookup"><span data-stu-id="99e37-110">A primary key is mandatory if changes need to be made to the database.</span></span>  
  
## <a name="provide-a-running-transaction-to-the-dataconnection-whenever-possible"></a><span data-ttu-id="99e37-111">可能な場合は DataConnection に実行中のトランザクションを提供する</span><span class="sxs-lookup"><span data-stu-id="99e37-111">Provide a running transaction to the DataConnection whenever possible</span></span>  
 <span data-ttu-id="99e37-112">トランザクションなしの クエリおよび更新の各、 **DataConnection** ルールの評価のさまざまな部分で開始され、独自のローカル トランザクションと複数の異なるクエリを別に返すことがありますが発生します。</span><span class="sxs-lookup"><span data-stu-id="99e37-112">Without a transaction, each query and update on the **DataConnection** initiates its own local transaction, and different queries might return different results in different parts of rule evaluations.</span></span> <span data-ttu-id="99e37-113">基になるデータベース テーブルが修正されると、矛盾した動作が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="99e37-113">Users may experience inconsistent behavior if there are changes in the underlying database table.</span></span>  
  
 <span data-ttu-id="99e37-114">使用できますが、 **DataConnection** せず、テーブルが時間の経過と共に変更しなかった場合は、トランザクションを提供することをお勧めトランザクションを使用する場合でも、 **DataConnection** は読み取り操作にのみ使用されています。</span><span class="sxs-lookup"><span data-stu-id="99e37-114">Although you can use a **DataConnection** without providing a transaction when the table does not change over time, it is recommended that a transaction be used even when the **DataConnection** is only being used for read operations.</span></span>  
  
 <span data-ttu-id="99e37-115">ただし、データを更新する場合は、必ずトランザクションを使用してください。</span><span class="sxs-lookup"><span data-stu-id="99e37-115">However, a transaction should always be used when updating data.</span></span>  
  
## <a name="number-of-queries-may-grow-linearly"></a><span data-ttu-id="99e37-116">クエリの数が増大する可能性がある</span><span class="sxs-lookup"><span data-stu-id="99e37-116">Number of queries may grow linearly</span></span>  
 <span data-ttu-id="99e37-117">クエリ、 **DataConnection** 他の結合されたオブジェクトに対して実行されるクエリの数でパラメーター化される、 **DataConnection** に到達するオブジェクトの結合の数に直接対応して、 **DataConnection**します。</span><span class="sxs-lookup"><span data-stu-id="99e37-117">As queries against the **DataConnection** are parameterized by other joined objects, the number of queries executed against the **DataConnection** corresponds directly to the number of joining objects reaching the **DataConnection**.</span></span> <span data-ttu-id="99e37-118">したがってへの参加の数のオブジェクトに到達する場合、 **DataConnection** オブジェクトは比例して、増大するに対するクエリの数、 **DataConnection** 直線的にも拡張されます。</span><span class="sxs-lookup"><span data-stu-id="99e37-118">Therefore, if the number of joining objects reaching the **DataConnection** object grows linearly, the number of queries against the **DataConnection** will grow linearly as well.</span></span> <span data-ttu-id="99e37-119">現在、クエリの数を減らす最適化は行われません。</span><span class="sxs-lookup"><span data-stu-id="99e37-119">Currently, there is no optimization in place to reduce the number of queries.</span></span>  
  
 <span data-ttu-id="99e37-120">この例を次のルールで示します。</span><span class="sxs-lookup"><span data-stu-id="99e37-120">An example of this is the rule:</span></span>  
  
```  
IF A.x = 7 AND DC.y = A.y  
THEN  
```  
  
 <span data-ttu-id="99e37-121">表す、 **ObjectBinding**, 、DC を表します、 **DataConnection**, 、x および y は A の属性と DC です。</span><span class="sxs-lookup"><span data-stu-id="99e37-121">A represents an **ObjectBinding**, DC represents a **DataConnection**, and x and y represent attributes of A and DC.</span></span>  
  
 <span data-ttu-id="99e37-122">テストに合格する A のすべてのインスタンス (x = 7) を使用して生成されるクエリは、 **DataConnection**します。</span><span class="sxs-lookup"><span data-stu-id="99e37-122">For every instance of A that passes the test (x = 7), a query is generated by using the **DataConnection**.</span></span> <span data-ttu-id="99e37-123">一致するインスタンスが多くある場合は、同じ数のクエリが生成されます。</span><span class="sxs-lookup"><span data-stu-id="99e37-123">If there are many matching instances, the same number of queries results.</span></span>  
  
## <a name="use-or-conditions-with-caution"></a><span data-ttu-id="99e37-124">慎重に OR 条件を使用する</span><span class="sxs-lookup"><span data-stu-id="99e37-124">Use OR conditions with caution</span></span>  
 <span data-ttu-id="99e37-125">ルールが論理積のみで使用する場合 (**AND**) 条件、テストおよびクエリ実行される、できるだけ早くため経由で渡されるオブジェクトのインスタンスを解消します。</span><span class="sxs-lookup"><span data-stu-id="99e37-125">If the rule uses only conjunctive (**AND**) conditions, tests and queries will be executed as early as possible, so instances of objects passing through will be reduced.</span></span> <span data-ttu-id="99e37-126">その結果、それに続くに対するクエリの数 **DataConnection** 比例して少なくなります。</span><span class="sxs-lookup"><span data-stu-id="99e37-126">As a result, the number of queries against the subsequent **DataConnection** will be reduced proportionally.</span></span> <span data-ttu-id="99e37-127">選言場合 (**または**) の条件と **DataConnection** ルールの評価は最後のクエリにプッシュされるすべての条件で一緒に使用します。</span><span class="sxs-lookup"><span data-stu-id="99e37-127">If disjunctive (**OR**) conditions and a **DataConnection** are used together in a rule, all condition evaluations will be pushed to the final query.</span></span> <span data-ttu-id="99e37-128">1 つ以上の場合 **DataConnection** は一般に、最後の 1 つは SELECT-ALL クエリ ステートメントに効果的になる点を除いて、すべてのクエリで使用します。</span><span class="sxs-lookup"><span data-stu-id="99e37-128">If more than one **DataConnection** is used in a rule, all queries except the last one will effectively become a Select-ALL query statement.</span></span>  
  
 <span data-ttu-id="99e37-129">一般的に、OR 条件を持つルールは複数の別ルールに分割することをお勧めします。OR 条件を使用すると、よりアトミックなルールを定義した場合に比べて、パフォーマンスが低下するためです。</span><span class="sxs-lookup"><span data-stu-id="99e37-129">In general, it is better to split any rule with an OR condition into two or more discrete rules, because the use of OR conditions will decrease performance compared to the definition of more atomic rules.</span></span> <span data-ttu-id="99e37-130">このことは、DataConnection を使用するどうかに関係なく当てはまります。</span><span class="sxs-lookup"><span data-stu-id="99e37-130">This is true whether DataConnections are used or not.</span></span>  
  
 <span data-ttu-id="99e37-131">1 つの規則ではなく論理積条件だけで構成される個別のルールの使用を検討することがありますも **または** 条件。</span><span class="sxs-lookup"><span data-stu-id="99e37-131">You may also consider using separate rules that consist only of conjunctive conditions instead of one rule with **OR** conditions.</span></span> <span data-ttu-id="99e37-132">**または** 条件、参加するすべてのオブジェクトのインスタンスの乗算の速度でクエリの数が増加します。</span><span class="sxs-lookup"><span data-stu-id="99e37-132">With **OR** conditions, the number of queries grows at the speed of multiplication of instances of all joining objects.</span></span> <span data-ttu-id="99e37-133">次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99e37-133">This is shown in the following example.</span></span>  
  
```  
IF (A.x ==7 OR A.x == 8) AND DC.y == A.y  
THEN DC.z = 10  
```  
  
 <span data-ttu-id="99e37-134">この例では A を表します、 **ObjectBinding**です。DC は、 **DataConnection**, 、x、y、および z は A の属性を表す、DC です。</span><span class="sxs-lookup"><span data-stu-id="99e37-134">In this example, A represents an **ObjectBinding**; DC represents a **DataConnection**, and x, y, and z represent attributes of A and DC.</span></span> <span data-ttu-id="99e37-135">100 個のクエリがに対して実行する必要がある A に 100 個のインスタンスは、x は最初のオブジェクトでは、100 のオブジェクトに 100、2 番目のオブジェクトでは 2 では 1 の場合、 **DataConnection**します。</span><span class="sxs-lookup"><span data-stu-id="99e37-135">If A has 100 instances, and x is 1 in the first object, 2 in the second object, through 100 in the 100th object, 100 queries have to run against the **DataConnection**.</span></span>  
  
 <span data-ttu-id="99e37-136">前のルールを書き換えて 2 つのルールに分割することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="99e37-136">It is better to rewrite the preceding rule by splitting it in to two rules.</span></span>  
  
 <span data-ttu-id="99e37-137">**ルール 1**</span><span class="sxs-lookup"><span data-stu-id="99e37-137">**Rule 1**</span></span>  
  
```  
IF A.x =7 AND DC.y = A.y  
THEN DC.z = 10  
```  
  
 <span data-ttu-id="99e37-138">**Rule 2**</span><span class="sxs-lookup"><span data-stu-id="99e37-138">**Rule 2**</span></span>  
  
```  
IF A.x = 8 AND DC.y = A.y  
THEN DC.z = 10  
```  
  
## <a name="sql-does-not-support-some-predicates-and-functions"></a><span data-ttu-id="99e37-139">SQL は一部の述語と関数をサポートしない</span><span class="sxs-lookup"><span data-stu-id="99e37-139">SQL does not support some predicates and functions</span></span>  
 <span data-ttu-id="99e37-140">ルール エンジンがサポートしている一部の述語と関数は、SQL に対応していません。</span><span class="sxs-lookup"><span data-stu-id="99e37-140">Some predicates and functions that the rule engine supports are not supported by SQL.</span></span> <span data-ttu-id="99e37-141">対応していないこれらの述語と関数をルールの条件で使用すると、クエリに組み込むことができません。</span><span class="sxs-lookup"><span data-stu-id="99e37-141">If these unsupported predicates and functions are used in the rule conditions, it cannot be incorporated into the query.</span></span> <span data-ttu-id="99e37-142">次の条件は、SQL クエリとして最適化できません。</span><span class="sxs-lookup"><span data-stu-id="99e37-142">The following terms cannot be optimized as an SQL query:</span></span>  
  
-   <span data-ttu-id="99e37-143">一部のエンジン組み込み関数に相当する機能は、SQL クエリにありません。</span><span class="sxs-lookup"><span data-stu-id="99e37-143">Some of the engine built-in functions have no equivalent in an SQL query.</span></span> <span data-ttu-id="99e37-144">これらは **電源**, 、**FindFirst**, 、および **FindAll**します。</span><span class="sxs-lookup"><span data-stu-id="99e37-144">These are **Power**, **FindFirst**, and **FindAll**.</span></span> <span data-ttu-id="99e37-145">使用して、 **DataConnection** 列を 1 つ以上の引数として、クエリの一部として最適化できません。 Power (2, dc です。列 1)。</span><span class="sxs-lookup"><span data-stu-id="99e37-145">Using a **DataConnection** column as one or more of their arguments cannot be optimized as part of a query; for example, Power( 2, dc.Column1).</span></span>  
  
-   <span data-ttu-id="99e37-146">組み込みの述語 Match を使用する、 **DataConnection** 列として、正規表現の引数 (最初の引数)。</span><span class="sxs-lookup"><span data-stu-id="99e37-146">Built-in predicate Match that uses a **DataConnection** column as its regular expression argument (the first argument).</span></span> <span data-ttu-id="99e37-147">たとえば、Match("abc\*", dc1.Column2) は有効ですが、Match(dc1.Column1, dc1.Column2) は解釈できません。</span><span class="sxs-lookup"><span data-stu-id="99e37-147">For example, Match("abc\*", dc1.Column2) is valid, but Match(dc1.Column1, dc1.Column2) cannot be translated.</span></span>  
  
-   <span data-ttu-id="99e37-148">持つユーザー関数を使用して、 **DataConnection** としてそのパラメーターの 1 つの列です。</span><span class="sxs-lookup"><span data-stu-id="99e37-148">Using a user function that has a **DataConnection** column as one of its parameters.</span></span> <span data-ttu-id="99e37-149">たとえば、ユーザー関数はデータベース サーバー上で実行できないため (ビジネス ルール エンジンで実行する必要がある)、c1.M(dc.Column1) は最適化できません。</span><span class="sxs-lookup"><span data-stu-id="99e37-149">For example, c1.M(dc.Column1) cannot be optimized because the user function cannot execute on the database server, but must be executed by the Business Rule Engine.</span></span>  
  
-   <span data-ttu-id="99e37-150">設定操作を表すユーザー関数、 **DataConnection**。 たとえば、dc です。Column1(5) します。</span><span class="sxs-lookup"><span data-stu-id="99e37-150">User functions that represent set operations on the **DataConnection**; for example, dc.Column1(5).</span></span>  
  
-   <span data-ttu-id="99e37-151">使用する関数、 **ObjectReference** に、 **DataConnection**ObjecRef(dc) 例です。</span><span class="sxs-lookup"><span data-stu-id="99e37-151">Functions that use an **ObjectReference** to the **DataConnection**; for example, ObjecRef(dc).</span></span>  
  
-   <span data-ttu-id="99e37-152">解釈できない引数がある場合、関数の呼び出し自体が解釈できなくなります (Add(c1.M(dc.Column1), 5) など)。</span><span class="sxs-lookup"><span data-stu-id="99e37-152">If one or more of a function's arguments is untranslatable, the function call becomes untranslatable; for example, Add(c1.M(dc.Column1), 5).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99e37-153">参照</span><span class="sxs-lookup"><span data-stu-id="99e37-153">See Also</span></span>  
 [<span data-ttu-id="99e37-154">ビジネス ルール エンジンでのデータ アクセス</span><span class="sxs-lookup"><span data-stu-id="99e37-154">Data Access in the Business Rule Engine</span></span>](../core/data-access-in-the-business-rule-engine.md)