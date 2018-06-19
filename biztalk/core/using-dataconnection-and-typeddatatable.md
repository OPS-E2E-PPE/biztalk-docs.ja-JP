---
title: DataConnection と TypedDataTable を使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Retract function [Business Rules Engine], TypedData table
- RetractByType function [Business Rules Engine], TypedData table
- Retract function [Business Rules Engine], DataConnection
- RetractByType function [Business Rules Engine], DataConnection
- Assert function [Business Rules Engine], TypedData table
- Business Rules Engine, DataConnection tips
- TypedData table
- Business Rules Engine, TypedData table tips
- Assert function [Business Rules Engine], DataConnection
- Update function [Business Rules Engine], TypedData table
- Update function [Business Rules Engine], DataConnection
ms.assetid: e825803e-6626-4ddd-a77e-75a3ba2b74a4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b5a0a490023d77676cc5d156ad5126ad5d7d6c7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287546"
---
# <a name="using-dataconnection-and-typeddatatable"></a><span data-ttu-id="1af53-102">DataConnection と TypedDataTable の使用</span><span class="sxs-lookup"><span data-stu-id="1af53-102">Using DataConnection and TypedDataTable</span></span>
<span data-ttu-id="1af53-103">使用して、多くのシナリオで**DataConnection**パフォーマンスを向上させると、使用するよりも少ないメモリを消費する**TypedDataTable**です。</span><span class="sxs-lookup"><span data-stu-id="1af53-103">In many scenarios, using **DataConnection** provides better performance and consumes less memory than using **TypedDataTable**.</span></span> <span data-ttu-id="1af53-104">ただし、 **TypedDataTable**で必要になる場合によってを使用して上の特定の制限のため**DataConnection**です。</span><span class="sxs-lookup"><span data-stu-id="1af53-104">However, **TypedDataTable** may be required in some cases because of certain restrictions on using **DataConnection**.</span></span> <span data-ttu-id="1af53-105">場合によっては他を使用して**TypedDataTable**を使用するよりも優れたパフォーマンスが生じる**DataConnection**です。</span><span class="sxs-lookup"><span data-stu-id="1af53-105">In some other cases, using **TypedDataTable** may yield better performance than using **DataConnection**.</span></span> <span data-ttu-id="1af53-106">このトピックでは、正しいアプローチを選択するために考慮する必要がある条件と要因について説明します。</span><span class="sxs-lookup"><span data-stu-id="1af53-106">This topic describes the criteria and factors that you should consider for choosing the right approach.</span></span>  
  
## <a name="when-to-use-typeddatatable-instead-of-dataconnection"></a><span data-ttu-id="1af53-107">DataConnection より TypedDataTable が適している場合</span><span class="sxs-lookup"><span data-stu-id="1af53-107">When to use TypedDataTable instead of DataConnection</span></span>  
 <span data-ttu-id="1af53-108">次の場合は、DataConnection ではなく TypedDataTable を使用します。</span><span class="sxs-lookup"><span data-stu-id="1af53-108">Use TypedDataTable instead of DataConnection in the following instances:</span></span>  
  
-   <span data-ttu-id="1af53-109">データを変更する必要があるが、テーブルに主キーがない場合。</span><span class="sxs-lookup"><span data-stu-id="1af53-109">Data changes need to be made but the table does not have a primary key.</span></span> <span data-ttu-id="1af53-110">使用してデータを変更する**DataConnection**、主キーが必要です。</span><span class="sxs-lookup"><span data-stu-id="1af53-110">To make data changes by using **DataConnection**, a primary key is required.</span></span> <span data-ttu-id="1af53-111">そのための主キーがない場合、 **TypedDataTable**唯一の方法です。</span><span class="sxs-lookup"><span data-stu-id="1af53-111">Therefore, if there is no primary key, **TypedDataTable** is the only viable approach.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1af53-112">ルール エンジンのメモリ内の値の更新のみ、 **TypedDataTable**です。</span><span class="sxs-lookup"><span data-stu-id="1af53-112">The rule engine only updates the values in memory for a **TypedDataTable**.</span></span> <span data-ttu-id="1af53-113">変更が永続的になるかどうかは呼び出し元によって異なります。</span><span class="sxs-lookup"><span data-stu-id="1af53-113">It is up to the caller to make those changes permanent.</span></span>  
  
-   <span data-ttu-id="1af53-114">選択度が高い場合。つまり、ルール条件として指定されたテストに大半のテーブル行が合格する場合。</span><span class="sxs-lookup"><span data-stu-id="1af53-114">Selectivity is high, which means that a large percentage of rows in the table will pass the tests specified as rule conditions.</span></span> <span data-ttu-id="1af53-115">この場合、 **DataConnection**メリットは提供されませんを実行できるよりも悪い**TypedDataTable**です。</span><span class="sxs-lookup"><span data-stu-id="1af53-115">In this case, **DataConnection** does not provide much benefit and it may perform worse than **TypedDataTable**.</span></span>  
  
-   <span data-ttu-id="1af53-116">テーブルのサイズが小さい場合。通常これには、行数が 500 未満のテーブルが該当します。</span><span class="sxs-lookup"><span data-stu-id="1af53-116">The table is small, typically, a table that contains fewer than 500 rows.</span></span> <span data-ttu-id="1af53-117">ただし、この値は、ルール図形およびルール エンジンで使用可能なメモリによって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1af53-117">Note that this number could be larger or smaller depending on the rule shape and the memory available to the rule engine.</span></span>  
  
-   <span data-ttu-id="1af53-118">ルール連鎖の動作がルール セットで予想されている場合。</span><span class="sxs-lookup"><span data-stu-id="1af53-118">Rule-chaining behavior is expected in a rule set.</span></span> <span data-ttu-id="1af53-119">呼び出す、**更新**で機能、 **DataConnection**はサポートされていません呼び出すことが**DataConnection.Update**ヘルパー メソッドを使用して、ルールにします。</span><span class="sxs-lookup"><span data-stu-id="1af53-119">Calling the **Update** function on a **DataConnection** is not supported, but you could invoke **DataConnection.Update** in a rule using a helper method.</span></span> <span data-ttu-id="1af53-120">ルール連鎖が必要な場合、 **TypedDataTable**方が適しています。</span><span class="sxs-lookup"><span data-stu-id="1af53-120">When rule chaining is required, **TypedDataTable** is a better choice.</span></span>  
  
-   <span data-ttu-id="1af53-121">テーブルの 1 つまたは複数の列に、ルールに不要なデータが大量に格納されている場合。</span><span class="sxs-lookup"><span data-stu-id="1af53-121">One or more columns in the table hold a very large amount of data that is not required by the rules.</span></span> <span data-ttu-id="1af53-122">その例としては、イメージ (大量のデータ)、名前、日付などが列に格納される、イメージ データベースが挙げられます。</span><span class="sxs-lookup"><span data-stu-id="1af53-122">An example is an image database, where the columns hold the image (large amount of data), name, date, and so on.</span></span> <span data-ttu-id="1af53-123">イメージが不要な場合は、ルールに必要な列だけを選択した方が効果的です。</span><span class="sxs-lookup"><span data-stu-id="1af53-123">If the image is not required, it may be better to select only the columns needed by the rules.</span></span> <span data-ttu-id="1af53-124">たとえば、"SELECT Name, Date from TABLE"のようなクエリを発行できますを使用するよりも効率的**DataConnection**です。</span><span class="sxs-lookup"><span data-stu-id="1af53-124">For example, issuing a query such as "SELECT Name, Date from TABLE" can be more efficient than using **DataConnection**.</span></span>  
  
-   <span data-ttu-id="1af53-125">使用して多数のルールは、データベースの同じ行の更新が必要する場合、 **TypedDataTable**行はすべての規則の間で共有と同じ場合は、条件 (Table.Column = = 5)、条件の評価を最適化することができます。</span><span class="sxs-lookup"><span data-stu-id="1af53-125">If many rules need or update the same database row, using a **TypedDataTable**, the row is shared between all rules, and if the condition is the same (for example, Table.Column == 5), the condition evaluation can be optimized.</span></span> <span data-ttu-id="1af53-126">**DataConnection**、使用するルールごとに生成されるクエリは一般に、 **DataConnection**です。</span><span class="sxs-lookup"><span data-stu-id="1af53-126">With a **DataConnection**, in general, a query is generated for each rule that uses the **DataConnection**.</span></span> <span data-ttu-id="1af53-127">行は再使用されますが (テーブルに主キーがある場合)、同じデータを毎回取得する複数のクエリが生成されることがあります。</span><span class="sxs-lookup"><span data-stu-id="1af53-127">Although the rows are reused (if the table has a primary key), multiple queries could be generated to get the same data each time.</span></span>  
  
## <a name="when-to-use-dataconnection-instead-of-typeddatatable"></a><span data-ttu-id="1af53-128">TypedDataTable より DataConnection が適している場合</span><span class="sxs-lookup"><span data-stu-id="1af53-128">When to use DataConnection instead of TypedDataTable</span></span>  
 <span data-ttu-id="1af53-129">次の場合は、TypedDataTable ではなく DataConnection を使用します。</span><span class="sxs-lookup"><span data-stu-id="1af53-129">Use DataConnection instead of TypedDataTable in the following instances:</span></span>  
  
-   <span data-ttu-id="1af53-130">テーブルには、行の数が多いが含まれていますが、選択度が低い — だけで、ルールの条件を満たす行の少ないです。</span><span class="sxs-lookup"><span data-stu-id="1af53-130">The table contains a large number of rows, but selectivity is low—only a small percentage of rows will satisfy the rule conditions.</span></span>  
  
-   <span data-ttu-id="1af53-131">サイズの大きなデータベース テーブルが 1 つしかなく、ルールで使用されるその他のオブジェクトには、少数のインスタンスしか含まれていない場合。</span><span class="sxs-lookup"><span data-stu-id="1af53-131">Only one database table is large; all other objects used in the rule have a small number of instances.</span></span> <span data-ttu-id="1af53-132">最悪の場合は、データベースに対して実行されるクエリの数が、ルールで使用されるその他すべてのインスタンスの結果と等しくなります。</span><span class="sxs-lookup"><span data-stu-id="1af53-132">In the worst case, the number of queries executed against the database is equal to the product of all the other instances used in the rule.</span></span>  
  
-   <span data-ttu-id="1af53-133">ルールが論理積条件だけで構成され、データベース テーブル以外のオブジェクトがこれらのルールで使用される場合。</span><span class="sxs-lookup"><span data-stu-id="1af53-133">Rules consist exclusively of conjunctive conditions and objects other than database table are used in these rules.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1af53-134">参照</span><span class="sxs-lookup"><span data-stu-id="1af53-134">See Also</span></span>  
 [<span data-ttu-id="1af53-135">ビジネス ルール エンジンでのデータ アクセス</span><span class="sxs-lookup"><span data-stu-id="1af53-135">Data Access in the Business Rule Engine</span></span>](../core/data-access-in-the-business-rule-engine.md)