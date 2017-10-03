---
title: "アサート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Assert function [Business Rules Engine], .NET objects
- Assert function [Business Rules Engine], TypedXMLDocument
- Assert function [Business Rules Engine]
- Assert function [Business Rules Engine], examples
- Assert function [Business Rules Engine], TypedData table
- Assert function [Business Rules Engine], DataConnection
- .NET objects
ms.assetid: e9989214-3c10-4691-9c38-f6fe64e511ed
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2de66aab5cde0a9515f41713d3390632180fbff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="assert"></a><span data-ttu-id="bf2d2-102">Filter</span><span class="sxs-lookup"><span data-stu-id="bf2d2-102">Assert</span></span>
<span data-ttu-id="bf2d2-103">*アサーション*プロセスをビジネス ルール エンジンの作業メモリにオブジェクトのインスタンスを追加することです。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-103">*Assertion* is the process of adding object instances into the Business Rule engine's working memory.</span></span> <span data-ttu-id="bf2d2-104">エンジンは、一致、競合解決、アクションの各フェーズを使用し、その種類のインスタンスに対して記述された条件とアクションに基づいて各インスタンスを処理します。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-104">The engine processes each instance according to the conditions and actions that are written against the type of the instance, using the match-conflict resolution-action phases.</span></span>  
  
 <span data-ttu-id="bf2d2-105">以下のトピックを使用してに起因する動作を説明する、 **Assert**異なるファクトの種類の関数。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-105">The following topics describe behaviors that result from using the **Assert** function for different fact types.</span></span>  
  
## <a name="net-objects"></a><span data-ttu-id="bf2d2-106">.NET オブジェクト</span><span class="sxs-lookup"><span data-stu-id="bf2d2-106">.NET Objects</span></span>  
 <span data-ttu-id="bf2d2-107">各オブジェクトは、別々のインスタンスとして作業メモリにアサートされます。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-107">Each object is asserted into the working memory as a separate instance.</span></span> <span data-ttu-id="bf2d2-108">つまり、インスタンスはオブジェクトの種類を参照する各述語によって分析されます (IF Object.Property = 1 など)。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-108">This means that the instance is analyzed by each predicate that references the object's type (for example, IF Object.Property = 1).</span></span> <span data-ttu-id="bf2d2-109">ルール条件の結果によっては、その種類を参照するルール アクションからも使用できます。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-109">It is also made available to rule actions that reference the type, dependent on the results of the rule conditions.</span></span>  
  
 <span data-ttu-id="bf2d2-110">次の例を考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-110">Consider the following example.</span></span>  
  
 <span data-ttu-id="bf2d2-111">**ルール 1**</span><span class="sxs-lookup"><span data-stu-id="bf2d2-111">**Rule 1**</span></span>  
  
```  
IF A.Value = 1  
THEN A.Status = "good"  
```  
  
 <span data-ttu-id="bf2d2-112">**規則 2**</span><span class="sxs-lookup"><span data-stu-id="bf2d2-112">**Rule 2**</span></span>  
  
```  
IF B.Value = 1  
THEN A.Status = "good"  
```  
  
 <span data-ttu-id="bf2d2-113">1 の値を持つ A のインスタンスのみを持つルール 1 で、**ステータス**プロパティが更新されました。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-113">In Rule 1, only those instances of A that have a Value of 1 will have their **Status** property updated.</span></span> <span data-ttu-id="bf2d2-114">ルール 2、ただし、条件の評価が場合**true**はのすべてのインスタンスがある状態が更新されました。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-114">In Rule 2, however, if the condition evaluates to **true**, all instances of A will have their status updated.</span></span> <span data-ttu-id="bf2d2-115">実際には、B の複数のインスタンスがある場合、A のインスタンスはたびに更新する条件の評価が**true** B のインスタンス。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-115">In fact, if there are multiple instances of B, the A instances will be updated each time the condition evaluates to **true** for a B instance.</span></span>  
  
 <span data-ttu-id="bf2d2-116">ルール内から .NET オブジェクトをアサートするには、組み込みを追加することができます**Assert**ルールのアクションとして機能します。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-116">To assert a .NET object from within a rule, you can add the built-in **Assert** function as a rule action.</span></span> <span data-ttu-id="bf2d2-117">ルール エンジンは、 **CreateObject**関数が、ビジネス ルール作成ツールで別の関数として表示されません。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-117">Note that the rule engine has a **CreateObject** function, but it is not displayed as a separate function in the Business Rule Composer.</span></span> <span data-ttu-id="bf2d2-118">この関数を呼び出すには、作成するオブジェクトのコンストラクター メソッドをファクト エクスプローラーの .NET クラス ビューからアクション ペインにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-118">Its invocation is built by dragging the constructor method of the object you wish to create from the .NET Class view of the Facts Explorer to the action pane.</span></span> <span data-ttu-id="bf2d2-119">ビジネス ルール作成ツールは、コンス トラクター メソッドにし、変換、 **CreateObject**ルールの定義で呼び出します。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-119">The Business Rule Composer then translates the constructor method into a **CreateObject** call in the rule definition.</span></span>  
  
## <a name="typedxmldocument"></a><span data-ttu-id="bf2d2-120">TypedXmlDocument</span><span class="sxs-lookup"><span data-stu-id="bf2d2-120">TypedXmlDocument</span></span>  
 <span data-ttu-id="bf2d2-121">ときに、 **TypedXmlDocument**がアサートすると、子を作成するビジネス ルール エンジン**TypedXmlDocument**ルールで定義されたセレクターに基づいてインスタンス。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-121">When a **TypedXmlDocument** is asserted, the Business Rule Engine creates child **TypedXmlDocument** instances based on the selectors defined in the rule.</span></span>  
  
 <span data-ttu-id="bf2d2-122">セレクターとフィールドは両方とも XPath 式です。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-122">Selectors and fields are both XPath expressions.</span></span> <span data-ttu-id="bf2d2-123">セレクターは、XML ドキュメントのノードを分離するための方法として、フィールドは、セレクター内の特定の項目を識別するものとしてとらえることができます。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-123">You can think of selectors as a way to isolate nodes of an XML document, and fields as identifying specific items within the selector.</span></span> <span data-ttu-id="bf2d2-124">各セレクター内のすべてのフィールドは、エンジンによって 1 つのオブジェクトとしてまとめられます。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-124">All the fields inside one selector are grouped together as an object by the engine.</span></span> <span data-ttu-id="bf2d2-125">下のノードを選択すると、 **XML スキーマ** タブで、ファクト エクスプ ローラー、ビジネス ルール作成ツールが自動的に入力、 **XPath セレクター** 、すべてのノード プロパティおよび**XPath フィールド**に子ノードが含まれていない任意のノードのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-125">When you select a node under the **XML Schemas** tab in the Facts Explorer, the Business Rule Composer automatically fills in the **XPath Selector** property for all nodes, and the **XPath Field** property for any node that does not contain child nodes.</span></span> <span data-ttu-id="bf2d2-126">独自の XPath 式を入力する代わりに、 **XPath セレクター**と**XPath フィールド**必要な場合です。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-126">Alternatively, you can enter your own XPath expressions for **XPath Selector** and **XPath Field** if necessary.</span></span>  
  
 <span data-ttu-id="bf2d2-127">セレクターが XML ドキュメントの複数の部分と一致すると、この種類の複数のオブジェクトとルール エンジンの作業メモリとの間でアサートまたは取り消しが行われます。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-127">If the selector matches multiple portions of the XML document, multiple objects of this type are asserted into or retracted from the rule engine working memory.</span></span> <span data-ttu-id="bf2d2-128">たとえば、次の XML があるとします。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-128">Assume you have the following XML.</span></span>  
  
```  
<root>  
   <order customer="Joe">  
      <item name="router" quantity="10" cost="550" />  
      <item name="switch" quantity="3" cost="300" />  
   </order>  
   <order customer="Jane">  
      <item name="switch" quantity="1" cost="300" />  
      <item name="cable" quantity="23" cost="9.99" />  
   </order>  
</root>  
```  
  
 <span data-ttu-id="bf2d2-129">セレクター /root/order (または //order) を使用すると、2 つのオブジェクトが作業メモリに追加されます。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-129">If you use the selector /root/order (or //order), two objects are added to the working memory.</span></span>  
  
 <span data-ttu-id="bf2d2-130">1\)</span><span class="sxs-lookup"><span data-stu-id="bf2d2-130">1\)</span></span>  
  
```  
<order customer="Joe">  
   <item name="router" quantity="10" cost="550" />  
   <item name="switch" quantity="3" cost="300" />  
</order>  
```  
  
 <span data-ttu-id="bf2d2-131">2\)</span><span class="sxs-lookup"><span data-stu-id="bf2d2-131">2\)</span></span>  
  
```  
<order customer="Jane">  
   <item name="switch" quantity="1" cost="300" />  
   <item name="cable" quantity="23" cost="9.99" />  
</order>  
```  
  
 <span data-ttu-id="bf2d2-132">各セレクター内で、個々のフィールドは XPath によって参照されます。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-132">Within each selector, the individual fields are referred to by XPaths.</span></span>  
  
 <span data-ttu-id="bf2d2-133">セレクター/root/order/item を使用するかどうか (または (//order/item または//item)、4 つのオブジェクトがルール エンジン作業メモリ、Joe の 2 つの項目と Jane の 2 つの項目に追加されます。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-133">If you use the selector /root/order/item (or (//order/item or //item), four objects  are added to the rule engine working memory, the two items for Joe and the two items for Jane.</span></span>  
  
```  
<root>  
   <order customer="Joe">  
  
   </order>  
   <order customer="Jane">  
  
   </order>  
</root>  
```  
  
 <span data-ttu-id="bf2d2-134">各オブジェクトは、3 つのフィールドにアクセス-@name、 @quantity、および@costです。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-134">Each object has access to three fields—@name, @quantity, and @cost.</span></span> <span data-ttu-id="bf2d2-135">オブジェクトは、元のドキュメントへの参照であるために、親フィールドを参照できます (たとえば、"../@customer") です。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-135">Because the object is a reference into the original document, you can refer to parent fields (for example, "../@customer").</span></span>  
  
 <span data-ttu-id="bf2d2-136">同じドキュメント内でも、複数のセレクターを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-136">You can use multiple selectors within the same document.</span></span> <span data-ttu-id="bf2d2-137">これにより、ドキュメントのさまざまな部分 (注文を示すセクションと発送先住所を示すセクションなど) を表示することが可能になります。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-137">This enables you to view different parts of the document (for example, if one section is the order and another section contains the shipping address).</span></span> <span data-ttu-id="bf2d2-138">ただし、作成されるオブジェクトは作成元の XPath 文字列によって定義されることを覚えておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-138">However, keep in mind that the objects that are created are defined by the XPath string that created them.</span></span> <span data-ttu-id="bf2d2-139">一意の結果、同じノードに解決される場合でも、別の XPath 式を使用して**TypedXmlDocument**です。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-139">Using a different XPath expression, even if it resolves to the same node, results in a unique **TypedXmlDocument**.</span></span>  
  
 <span data-ttu-id="bf2d2-140">ルール エンジンは、基本的な .NET スカラー型をネイティブでサポートしているだけでなく、参照型のオブジェクトもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-140">The rule engine supports basic .NET scalar types natively, as well as objects for reference types.</span></span> <span data-ttu-id="bf2d2-141">XML ドキュメントは基本的にテキストですが、ルールの作成時に指定された型に基づいており、フィールド値の型は任意です。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-141">XML documents are basically text, but based on the type that was specified when the rule was built, the field value may be of any type.</span></span> <span data-ttu-id="bf2d2-142">また、フィールドは XPath 式であるため、ノード セットを返す場合があります。この場合は、セット内の最初の項目が値として使用されます。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-142">Also, because fields are XPath expressions, they may return a nodeset, in which case the first item in the set is used as the value.</span></span>  
  
 <span data-ttu-id="bf2d2-143">背後では、ルール エンジンは、によってサポートされている種類のいずれにもテキスト フィールドの値を変換できます、 **XmlConvert**関数。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-143">Behind the scenes, the rule engine can convert a text field value to any one of the supported types through the **XmlConvert** function.</span></span> <span data-ttu-id="bf2d2-144">これを指定するには、ビジネス ルール作成ツールで型を設定します。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-144">You can specify this by setting the type in the Business Rule Composer.</span></span> <span data-ttu-id="bf2d2-145">変換が不可能な場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-145">An exception is thrown if a conversion is not possible.</span></span> <span data-ttu-id="bf2d2-146">種類**bool**と**二重**それぞれの型、文字列、またはオブジェクトとしてのみ取得できます。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-146">The types **bool** and **double** can be retrieved only as their respective type, strings, or objects.</span></span>  
  
## <a name="typeddatatable"></a><span data-ttu-id="bf2d2-147">TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="bf2d2-147">TypedDataTable</span></span>  
 <span data-ttu-id="bf2d2-148">ときに、 **TypedDataTable**がアサートされ、すべて**Datarow**に含まれている、 **DataTable**としてエンジンにアサートが自動的に**TypedDataRows**.</span><span class="sxs-lookup"><span data-stu-id="bf2d2-148">When a **TypedDataTable** is asserted, all **DataRows** contained in the **DataTable** are automatically asserted into the engine as **TypedDataRows**.</span></span> <span data-ttu-id="bf2d2-149">テーブルまたはテーブルの列がルールの引数として使用される、個人に対して式が評価されます**TypedDataRows**、およびに対してではなく、 **TypedDataTable**です。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-149">Any time a table or table column is used as a rule argument, the expression is evaluated against the individual **TypedDataRows**, and not against the **TypedDataTable**.</span></span>  
  
 <span data-ttu-id="bf2d2-150">たとえば、"Customers" テーブルに対して作成された次のルールがあるとします。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-150">For example, suppose that you have the following rule built against a "Customers" table:</span></span>  
  
```  
IF Northwind.Customers.CustomerID = 001  
THEN Northwind.Customers.ContactTitle = "Purchasing Manager"  
```  
  
> [!NOTE]
>  <span data-ttu-id="bf2d2-151">データベース テーブルに対して、ルールを作成するを使用する必要があります**データ テーブル/データ行**データベース バインドの種類として。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-151">To build a rule against a database table, you must use **Data table / row** as the database binding type.</span></span>  
  
 <span data-ttu-id="bf2d2-152">次をアサートすると仮定**DataTable**を 3 つ**Datarow**エンジンに (として、 **TypedDataTable**)。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-152">Suppose that you assert the following **DataTable** with three **DataRows** into the engine (as a **TypedDataTable**).</span></span>  
  
|<span data-ttu-id="bf2d2-153">CustomerID</span><span class="sxs-lookup"><span data-stu-id="bf2d2-153">CustomerID</span></span>|<span data-ttu-id="bf2d2-154">ContactTitle</span><span class="sxs-lookup"><span data-stu-id="bf2d2-154">ContactTitle</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="bf2d2-155">001</span><span class="sxs-lookup"><span data-stu-id="bf2d2-155">001</span></span>|<span data-ttu-id="bf2d2-156">Supply Clerk</span><span class="sxs-lookup"><span data-stu-id="bf2d2-156">Supply Clerk</span></span>|  
|<span data-ttu-id="bf2d2-157">002</span><span class="sxs-lookup"><span data-stu-id="bf2d2-157">002</span></span>|<span data-ttu-id="bf2d2-158">Supply Clerk</span><span class="sxs-lookup"><span data-stu-id="bf2d2-158">Supply Clerk</span></span>|  
|<span data-ttu-id="bf2d2-159">003</span><span class="sxs-lookup"><span data-stu-id="bf2d2-159">003</span></span>|<span data-ttu-id="bf2d2-160">Supply Clerk</span><span class="sxs-lookup"><span data-stu-id="bf2d2-160">Supply Clerk</span></span>|  
  
 <span data-ttu-id="bf2d2-161">エンジンは 3 つを挿入します。 **TypedDataRows**: 001、002、003 です。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-161">The engine inserts three **TypedDataRows**: 001, 002, and 003.</span></span>  
  
 <span data-ttu-id="bf2d2-162">各**TypedDataRow**ルールに対して個別に評価されます。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-162">Each **TypedDataRow** is evaluated independently against the rule.</span></span> <span data-ttu-id="bf2d2-163">最初の**TypedDataRow**ルールの条件と残りの 2 つの失敗を満たしています。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-163">The first **TypedDataRow** meets the rule condition and the second two fail.</span></span> <span data-ttu-id="bf2d2-164">結果を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-164">The results appear as follows.</span></span>  
  
|<span data-ttu-id="bf2d2-165">CustomerID</span><span class="sxs-lookup"><span data-stu-id="bf2d2-165">CustomerID</span></span>|<span data-ttu-id="bf2d2-166">ContactTitle</span><span class="sxs-lookup"><span data-stu-id="bf2d2-166">ContactTitle</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="bf2d2-167">001</span><span class="sxs-lookup"><span data-stu-id="bf2d2-167">001</span></span>|<span data-ttu-id="bf2d2-168">Purchasing Manager</span><span class="sxs-lookup"><span data-stu-id="bf2d2-168">Purchasing Manager</span></span>|  
|<span data-ttu-id="bf2d2-169">002</span><span class="sxs-lookup"><span data-stu-id="bf2d2-169">002</span></span>|<span data-ttu-id="bf2d2-170">Supply Clerk</span><span class="sxs-lookup"><span data-stu-id="bf2d2-170">Supply Clerk</span></span>|  
|<span data-ttu-id="bf2d2-171">003</span><span class="sxs-lookup"><span data-stu-id="bf2d2-171">003</span></span>|<span data-ttu-id="bf2d2-172">Supply Clerk</span><span class="sxs-lookup"><span data-stu-id="bf2d2-172">Supply Clerk</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="bf2d2-173">TypedDataRow はエンジンに直接アサートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-173">TypedDataRows can also be directly asserted into the engine.</span></span> <span data-ttu-id="bf2d2-174">その場合も前述の方法で処理されます。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-174">These are processed in the same way as described earlier.</span></span>  
  
 <span data-ttu-id="bf2d2-175">**DataSetName.DataTableName**は一意の識別子であると見なされます。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-175">The **DataSetName.DataTableName** is considered to be a unique identifier.</span></span> <span data-ttu-id="bf2d2-176">したがって場合、2 番目**TypedDataTable**がアサートされた同じ**データセット**名と**DataTable**名、最初のによって置き換えられる**TypedDataTable**.</span><span class="sxs-lookup"><span data-stu-id="bf2d2-176">Therefore, if a second **TypedDataTable** is asserted with the same **DataSet** name and **DataTable** name, it supersedes the first **TypedDataTable**.</span></span> <span data-ttu-id="bf2d2-177">すべて**TypedDataRow**に最初の関連付けられている**TypedDataTable**は取り消され、2 番目**TypedDataTable**がアサートします。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-177">All **TypedDataRow**s associated with the first **TypedDataTable** are retracted, and the second **TypedDataTable** is asserted.</span></span>  
  
## <a name="dataconnection"></a><span data-ttu-id="bf2d2-178">DataConnection</span><span class="sxs-lookup"><span data-stu-id="bf2d2-178">DataConnection</span></span>  
 <span data-ttu-id="bf2d2-179">同様、 **TypedDataTable**、ビジネス ルール作成ツールでルールの引数としてテーブルまたは列をドラッグする結果、返されたに対してルールが作成、 **TypedDataRow**そのものではなく、 **DataConnection**自体です。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-179">As with a **TypedDataTable**, dragging a table or column as a rule argument in the Business Rule Composer results in rules built against the returned **TypedDataRow**s as opposed to the **DataConnection** itself.</span></span>  
  
 <span data-ttu-id="bf2d2-180">たとえば、次の規則を作成して**DataConnection**を格納しているがアサートされる、 **SqlConnection** Northwind.Customers に。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-180">Suppose that the following rule is created and a **DataConnection** is asserted that contains a **SqlConnection** to Northwind.Customers:</span></span>  
  
```  
IF Northwind.Customers.CustomerID = 001  
THEN Northwind.Customers.ContactTitle = "Purchasing Manager"  
```  
  
 <span data-ttu-id="bf2d2-181">エンジンがで使用されるルールと評価される場合、 **TypedDataTable**  セクションで、動的に作成し、次のようなクエリ。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-181">When the engine evaluates the rule used in the **TypedDataTable** section, it dynamically builds a query that looks like:</span></span>  
  
```  
SELECT *  
FROM Northwind.Customers  
WHERE CustomerID = 1  
```  
  
 <span data-ttu-id="bf2d2-182">データベース内の行を 1 つだけがこの条件は、1 つだけを満たすため**TypedDataRow**が作成され、さらに処理エンジンにアサートします。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-182">Because only one row in the database meets this criterion, only one **TypedDataRow** is created and asserted into the engine for further processing.</span></span>  
  
## <a name="summary-of-asserted-entities-and-instance-types"></a><span data-ttu-id="bf2d2-183">アサートされるエンティティとインスタンスの種類の要約</span><span class="sxs-lookup"><span data-stu-id="bf2d2-183">Summary of Asserted Entities and Instance Types</span></span>  
 <span data-ttu-id="bf2d2-184">次の表は、エンジンにアサートされたエンティティごとで作成された結果として得られるインスタンスの数を示す、さまざまな種類だけでなくそれらのインスタンスを識別するためのそれぞれに適用される型のアサートの動作をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="bf2d2-184">The following table summarizes the assert behavior for the various types, showing the number of resulting instances created in the engine for each asserted entity, as well as the type that is applied to each of those instances to identify them.</span></span>  
  
|<span data-ttu-id="bf2d2-185">Entity</span><span class="sxs-lookup"><span data-stu-id="bf2d2-185">Entity</span></span>|<span data-ttu-id="bf2d2-186">アサートされるインスタンスの数</span><span class="sxs-lookup"><span data-stu-id="bf2d2-186">Number of instances asserted</span></span>|<span data-ttu-id="bf2d2-187">インスタンスの種類</span><span class="sxs-lookup"><span data-stu-id="bf2d2-187">Instance type</span></span>|  
|------------|----------------------------------|-------------------|  
|<span data-ttu-id="bf2d2-188">.NET オブジェクト</span><span class="sxs-lookup"><span data-stu-id="bf2d2-188">.NET object</span></span>|<span data-ttu-id="bf2d2-189">1 (オブジェクト自体)</span><span class="sxs-lookup"><span data-stu-id="bf2d2-189">1 (the object itself)</span></span>|<span data-ttu-id="bf2d2-190">完全修飾 .NET クラス</span><span class="sxs-lookup"><span data-stu-id="bf2d2-190">Fully Qualified .NET Class</span></span>|  
|<span data-ttu-id="bf2d2-191">TypedXmlDocument</span><span class="sxs-lookup"><span data-stu-id="bf2d2-191">TypedXmlDocument</span></span>|<span data-ttu-id="bf2d2-192">1 ～ N 個の TypedXmlDocument (作成されるセレクター バインドとドキュメントのコンテンツに基づく)</span><span class="sxs-lookup"><span data-stu-id="bf2d2-192">1-N TypedXmlDocument(s): Based on Selector bindings created and document content</span></span>|<span data-ttu-id="bf2d2-193">DocumentType.Selector</span><span class="sxs-lookup"><span data-stu-id="bf2d2-193">DocumentType.Selector</span></span>|  
|<span data-ttu-id="bf2d2-194">TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="bf2d2-194">TypedDataTable</span></span>|<span data-ttu-id="bf2d2-195">1 ～ N 個の TypedDataRow</span><span class="sxs-lookup"><span data-stu-id="bf2d2-195">1-N TypedDataRow(s):</span></span><br /><br /> <span data-ttu-id="bf2d2-196">(DataTable の各 DataRow につき 1 個)</span><span class="sxs-lookup"><span data-stu-id="bf2d2-196">One for each DataRow in the DataTable</span></span>|<span data-ttu-id="bf2d2-197">DataSetName.DataTableName</span><span class="sxs-lookup"><span data-stu-id="bf2d2-197">DataSetName.DataTableName</span></span>|  
|<span data-ttu-id="bf2d2-198">TypedDataRow</span><span class="sxs-lookup"><span data-stu-id="bf2d2-198">TypedDataRow</span></span>|<span data-ttu-id="bf2d2-199">1 (アサートされる TypedDataRow)</span><span class="sxs-lookup"><span data-stu-id="bf2d2-199">1 (the TypedDataRow asserted)</span></span>|<span data-ttu-id="bf2d2-200">DataSetName.DataTableName</span><span class="sxs-lookup"><span data-stu-id="bf2d2-200">DataSetName.DataTableName</span></span>|  
|<span data-ttu-id="bf2d2-201">DataConnection</span><span class="sxs-lookup"><span data-stu-id="bf2d2-201">DataConnection</span></span>|<span data-ttu-id="bf2d2-202">1 ～N 個 (DataConnection の照会によって返される各 TypedDataRow につき 1 個)</span><span class="sxs-lookup"><span data-stu-id="bf2d2-202">1-N (one for each TypedDataRow returned by querying the DataConnection)</span></span>|<span data-ttu-id="bf2d2-203">DataSetName.DataTableName</span><span class="sxs-lookup"><span data-stu-id="bf2d2-203">DataSetName.DataTableName</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bf2d2-204">参照</span><span class="sxs-lookup"><span data-stu-id="bf2d2-204">See Also</span></span>  
 [<span data-ttu-id="bf2d2-205">エンジン制御関数</span><span class="sxs-lookup"><span data-stu-id="bf2d2-205">Engine Control Functions</span></span>](../core/engine-control-functions.md)