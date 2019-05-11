---
title: DataConnection と TypedDataTable の使用 |Microsoft Docs
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
ms.openlocfilehash: c9decd3a849aa21e0e769e006c8dfe29ca5b7315
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401612"
---
# <a name="using-dataconnection-and-typeddatatable"></a><span data-ttu-id="b38f8-102">DataConnection と TypedDataTable の使用</span><span class="sxs-lookup"><span data-stu-id="b38f8-102">Using DataConnection and TypedDataTable</span></span>
<span data-ttu-id="b38f8-103">使用して、多くのシナリオで**DataConnection**パフォーマンスが優れており、使用するよりも少ないメモリを消費**TypedDataTable**します。</span><span class="sxs-lookup"><span data-stu-id="b38f8-103">In many scenarios, using **DataConnection** provides better performance and consumes less memory than using **TypedDataTable**.</span></span> <span data-ttu-id="b38f8-104">ただし、 **TypedDataTable**の使用に関する制限があるため、場合によっては必要があります**DataConnection**します。</span><span class="sxs-lookup"><span data-stu-id="b38f8-104">However, **TypedDataTable** may be required in some cases because of certain restrictions on using **DataConnection**.</span></span> <span data-ttu-id="b38f8-105">その他の場合を使用して**TypedDataTable**を使用してより優れたパフォーマンスを生じる**DataConnection**します。</span><span class="sxs-lookup"><span data-stu-id="b38f8-105">In some other cases, using **TypedDataTable** may yield better performance than using **DataConnection**.</span></span> <span data-ttu-id="b38f8-106">このトピックでは、条件と適切なアプローチを選択するために考慮すべき要因について説明します。</span><span class="sxs-lookup"><span data-stu-id="b38f8-106">This topic describes the criteria and factors that you should consider for choosing the right approach.</span></span>  
  
## <a name="when-to-use-typeddatatable-instead-of-dataconnection"></a><span data-ttu-id="b38f8-107">DataConnection ではなく TypedDataTable を使用する場合</span><span class="sxs-lookup"><span data-stu-id="b38f8-107">When to use TypedDataTable instead of DataConnection</span></span>  
 <span data-ttu-id="b38f8-108">次のインスタンスで、DataConnection ではなく TypedDataTable を使用します。</span><span class="sxs-lookup"><span data-stu-id="b38f8-108">Use TypedDataTable instead of DataConnection in the following instances:</span></span>  
  
-   <span data-ttu-id="b38f8-109">データの変更ができるようにする必要がありますが、テーブルには、主キーにありません。</span><span class="sxs-lookup"><span data-stu-id="b38f8-109">Data changes need to be made but the table does not have a primary key.</span></span> <span data-ttu-id="b38f8-110">使用してデータを変更する**DataConnection**、主キーが必要です。</span><span class="sxs-lookup"><span data-stu-id="b38f8-110">To make data changes by using **DataConnection**, a primary key is required.</span></span> <span data-ttu-id="b38f8-111">そのため、主キーがない場合**TypedDataTable**は唯一の方法です。</span><span class="sxs-lookup"><span data-stu-id="b38f8-111">Therefore, if there is no primary key, **TypedDataTable** is the only viable approach.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b38f8-112">ルール エンジンのメモリ内の値を更新のみを**TypedDataTable**します。</span><span class="sxs-lookup"><span data-stu-id="b38f8-112">The rule engine only updates the values in memory for a **TypedDataTable**.</span></span> <span data-ttu-id="b38f8-113">これらの変更を永続的なを呼び出し元の責任です。</span><span class="sxs-lookup"><span data-stu-id="b38f8-113">It is up to the caller to make those changes permanent.</span></span>  
  
-   <span data-ttu-id="b38f8-114">選択度は、大きなテーブル内の行の割合がルールの条件として指定されたテストに合格するは、高です。</span><span class="sxs-lookup"><span data-stu-id="b38f8-114">Selectivity is high, which means that a large percentage of rows in the table will pass the tests specified as rule conditions.</span></span> <span data-ttu-id="b38f8-115">この場合、 **DataConnection**メリットを提供しない可能性がありますよりも悪い**TypedDataTable**します。</span><span class="sxs-lookup"><span data-stu-id="b38f8-115">In this case, **DataConnection** does not provide much benefit and it may perform worse than **TypedDataTable**.</span></span>  
  
-   <span data-ttu-id="b38f8-116">テーブルは通常、小規模、500 未満の行を含むテーブル。</span><span class="sxs-lookup"><span data-stu-id="b38f8-116">The table is small, typically, a table that contains fewer than 500 rows.</span></span> <span data-ttu-id="b38f8-117">この番号が大きくまたは小さく、ルール図形およびルール エンジンで使用できるメモリによってありますに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b38f8-117">Note that this number could be larger or smaller depending on the rule shape and the memory available to the rule engine.</span></span>  
  
-   <span data-ttu-id="b38f8-118">ルール連鎖の動作が規則セットが必要です。</span><span class="sxs-lookup"><span data-stu-id="b38f8-118">Rule-chaining behavior is expected in a rule set.</span></span> <span data-ttu-id="b38f8-119">呼び出す、 **Update**に対して関数を**DataConnection**はサポートされていません呼び出すことができますが、 **DataConnection.Update**ヘルパー メソッドを使用してルール。</span><span class="sxs-lookup"><span data-stu-id="b38f8-119">Calling the **Update** function on a **DataConnection** is not supported, but you could invoke **DataConnection.Update** in a rule using a helper method.</span></span> <span data-ttu-id="b38f8-120">ルール連鎖が必要なときに**TypedDataTable**をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b38f8-120">When rule chaining is required, **TypedDataTable** is a better choice.</span></span>  
  
-   <span data-ttu-id="b38f8-121">テーブルの 1 つまたは複数の列は、非常に大量のデータは、ルールで必要としないを保持します。</span><span class="sxs-lookup"><span data-stu-id="b38f8-121">One or more columns in the table hold a very large amount of data that is not required by the rules.</span></span> <span data-ttu-id="b38f8-122">例は、列に格納されるイメージ (大量のデータ)、名前、日付、およびなど、イメージ データベースです。</span><span class="sxs-lookup"><span data-stu-id="b38f8-122">An example is an image database, where the columns hold the image (large amount of data), name, date, and so on.</span></span> <span data-ttu-id="b38f8-123">イメージが必要ない場合は、ルールで必要な列のみを選択する方がよい場合があります。</span><span class="sxs-lookup"><span data-stu-id="b38f8-123">If the image is not required, it may be better to select only the columns needed by the rules.</span></span> <span data-ttu-id="b38f8-124">たとえば、"SELECT Name, Date from TABLE"などのクエリを発行できますを使用してよりも効率的**DataConnection**します。</span><span class="sxs-lookup"><span data-stu-id="b38f8-124">For example, issuing a query such as "SELECT Name, Date from TABLE" can be more efficient than using **DataConnection**.</span></span>  
  
-   <span data-ttu-id="b38f8-125">使用して多数のルールまたはデータベースの同じ行の更新を場合、 **TypedDataTable**行がすべてのルールの間で共有条件が同じである場合、(Table.Column 5 = =)、条件の評価を最適化することができます。</span><span class="sxs-lookup"><span data-stu-id="b38f8-125">If many rules need or update the same database row, using a **TypedDataTable**, the row is shared between all rules, and if the condition is the same (for example, Table.Column == 5), the condition evaluation can be optimized.</span></span> <span data-ttu-id="b38f8-126">**DataConnection**、一般を使用する各ルールには、クエリが生成、 **DataConnection**します。</span><span class="sxs-lookup"><span data-stu-id="b38f8-126">With a **DataConnection**, in general, a query is generated for each rule that uses the **DataConnection**.</span></span> <span data-ttu-id="b38f8-127">(テーブルに主キーがある場合)、行が再利用が毎回同じデータを取得する複数のクエリを生成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="b38f8-127">Although the rows are reused (if the table has a primary key), multiple queries could be generated to get the same data each time.</span></span>  
  
## <a name="when-to-use-dataconnection-instead-of-typeddatatable"></a><span data-ttu-id="b38f8-128">TypedDataTable ではなく DataConnection を使用する場合</span><span class="sxs-lookup"><span data-stu-id="b38f8-128">When to use DataConnection instead of TypedDataTable</span></span>  
 <span data-ttu-id="b38f8-129">次のインスタンスで、TypedDataTable ではなく DataConnection を使用します。</span><span class="sxs-lookup"><span data-stu-id="b38f8-129">Use DataConnection instead of TypedDataTable in the following instances:</span></span>  
  
-   <span data-ttu-id="b38f8-130">テーブルには、行の数が多いが含まれていますが、選択度が低い-ルールの条件を満たす行のごく一部のみです。</span><span class="sxs-lookup"><span data-stu-id="b38f8-130">The table contains a large number of rows, but selectivity is low—only a small percentage of rows will satisfy the rule conditions.</span></span>  
  
-   <span data-ttu-id="b38f8-131">1 つのデータベースのテーブルが大きいです。ルールで使用されるその他のすべてのオブジェクトでは、少数のインスタンスがあります。</span><span class="sxs-lookup"><span data-stu-id="b38f8-131">Only one database table is large; all other objects used in the rule have a small number of instances.</span></span> <span data-ttu-id="b38f8-132">最悪の場合、データベースに対して実行されるクエリの数は、ルールで使用されるその他のすべてのインスタンスの積に等しくなります。</span><span class="sxs-lookup"><span data-stu-id="b38f8-132">In the worst case, the number of queries executed against the database is equal to the product of all the other instances used in the rule.</span></span>  
  
-   <span data-ttu-id="b38f8-133">論理積条件だけルールを構成し、データベース テーブル以外のオブジェクトは、これらのルールで使用します。</span><span class="sxs-lookup"><span data-stu-id="b38f8-133">Rules consist exclusively of conjunctive conditions and objects other than database table are used in these rules.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b38f8-134">参照</span><span class="sxs-lookup"><span data-stu-id="b38f8-134">See Also</span></span>  
 [<span data-ttu-id="b38f8-135">ビジネス ルール エンジンでのデータ アクセス</span><span class="sxs-lookup"><span data-stu-id="b38f8-135">Data Access in the Business Rule Engine</span></span>](../core/data-access-in-the-business-rule-engine.md)