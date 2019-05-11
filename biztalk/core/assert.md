---
title: アサート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce3fcf26ae039999b4d4593f94ab4b8f375cd03a
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528620"
---
# <a name="assert"></a><span data-ttu-id="9d41b-102">Filter</span><span class="sxs-lookup"><span data-stu-id="9d41b-102">Assert</span></span>
<span data-ttu-id="9d41b-103">*アサーション*は、ビジネス ルール エンジンの作業メモリにオブジェクトのインスタンスを追加するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="9d41b-103">*Assertion* is the process of adding object instances into the Business Rule engine's working memory.</span></span> <span data-ttu-id="9d41b-104">エンジンは、条件と一致-競合解決-アクション フェーズを使用して、インスタンスの型に対して記述されたアクションに従って各インスタンスを処理します。</span><span class="sxs-lookup"><span data-stu-id="9d41b-104">The engine processes each instance according to the conditions and actions that are written against the type of the instance, using the match-conflict resolution-action phases.</span></span>  
  
 <span data-ttu-id="9d41b-105">次のトピックでは、動作を使用した、 **Assert**関数のさまざまなファクトの種類。</span><span class="sxs-lookup"><span data-stu-id="9d41b-105">The following topics describe behaviors that result from using the **Assert** function for different fact types.</span></span>  
  
## <a name="net-objects"></a><span data-ttu-id="9d41b-106">.NET オブジェクト</span><span class="sxs-lookup"><span data-stu-id="9d41b-106">.NET Objects</span></span>  
 <span data-ttu-id="9d41b-107">各オブジェクトは、別個のインスタンスとして作業メモリにアサートされます。</span><span class="sxs-lookup"><span data-stu-id="9d41b-107">Each object is asserted into the working memory as a separate instance.</span></span> <span data-ttu-id="9d41b-108">つまり、インスタンスが、オブジェクトの型を参照する各述語によって分析される (たとえば、IF Object.Property = 1)。</span><span class="sxs-lookup"><span data-stu-id="9d41b-108">This means that the instance is analyzed by each predicate that references the object's type (for example, IF Object.Property = 1).</span></span> <span data-ttu-id="9d41b-109">ルールの条件の結果に依存して、型を参照するルール アクションで使用できるもされます。</span><span class="sxs-lookup"><span data-stu-id="9d41b-109">It is also made available to rule actions that reference the type, dependent on the results of the rule conditions.</span></span>  
  
 <span data-ttu-id="9d41b-110">次の例を考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="9d41b-110">Consider the following example.</span></span>  
  
 <span data-ttu-id="9d41b-111">**ルール 1**</span><span class="sxs-lookup"><span data-stu-id="9d41b-111">**Rule 1**</span></span>  
  
```  
IF A.Value = 1  
THEN A.Status = "good"  
```  
  
 <span data-ttu-id="9d41b-112">**Rule 2**</span><span class="sxs-lookup"><span data-stu-id="9d41b-112">**Rule 2**</span></span>  
  
```  
IF B.Value = 1  
THEN A.Status = "good"  
```  
  
 <span data-ttu-id="9d41b-113">ルール 1 では、1 の値が A のインスタンスのみがその**状態**プロパティが更新されました。</span><span class="sxs-lookup"><span data-stu-id="9d41b-113">In Rule 1, only those instances of A that have a Value of 1 will have their **Status** property updated.</span></span> <span data-ttu-id="9d41b-114">ルール 2、ただし、条件の評価が場合**true**はのすべてのインスタンスがある、状態を更新します。</span><span class="sxs-lookup"><span data-stu-id="9d41b-114">In Rule 2, however, if the condition evaluates to **true**, all instances of A will have their status updated.</span></span> <span data-ttu-id="9d41b-115">実際には、B の複数のインスタンスがある場合、A のインスタンスはたびに更新する条件の評価が**true** B のインスタンス。</span><span class="sxs-lookup"><span data-stu-id="9d41b-115">In fact, if there are multiple instances of B, the A instances will be updated each time the condition evaluates to **true** for a B instance.</span></span>  
  
 <span data-ttu-id="9d41b-116">ルール内から .NET オブジェクトをアサートするには、組み込みを追加することができます**Assert**ルールのアクションとして機能します。</span><span class="sxs-lookup"><span data-stu-id="9d41b-116">To assert a .NET object from within a rule, you can add the built-in **Assert** function as a rule action.</span></span> <span data-ttu-id="9d41b-117">ルール エンジンは、 **CreateObject**関数がビジネス ルール作成ツールで個別の関数としては表示されません。</span><span class="sxs-lookup"><span data-stu-id="9d41b-117">Note that the rule engine has a **CreateObject** function, but it is not displayed as a separate function in the Business Rule Composer.</span></span> <span data-ttu-id="9d41b-118">その呼び出しは、操作ウィンドウに、ファクト エクスプ ローラーの .NET クラス ビューから作成するオブジェクトのコンス トラクター メソッドをドラッグして構築されています。</span><span class="sxs-lookup"><span data-stu-id="9d41b-118">Its invocation is built by dragging the constructor method of the object you wish to create from the .NET Class view of the Facts Explorer to the action pane.</span></span> <span data-ttu-id="9d41b-119">ビジネス ルール作成ツールには、コンス トラクターのメソッドに変換されます、 **CreateObject**ルール定義で呼び出します。</span><span class="sxs-lookup"><span data-stu-id="9d41b-119">The Business Rule Composer then translates the constructor method into a **CreateObject** call in the rule definition.</span></span>  
  
## <a name="typedxmldocument"></a><span data-ttu-id="9d41b-120">TypedXmlDocument</span><span class="sxs-lookup"><span data-stu-id="9d41b-120">TypedXmlDocument</span></span>  
 <span data-ttu-id="9d41b-121">ときに、 **TypedXmlDocument**アサートすると、ビジネス ルール エンジンは、子を作成します。 **TypedXmlDocument**ルールで定義されたセレクターに基づいてインスタンス。</span><span class="sxs-lookup"><span data-stu-id="9d41b-121">When a **TypedXmlDocument** is asserted, the Business Rule Engine creates child **TypedXmlDocument** instances based on the selectors defined in the rule.</span></span>  
  
 <span data-ttu-id="9d41b-122">セレクターとフィールドは、両方の XPath 式です。</span><span class="sxs-lookup"><span data-stu-id="9d41b-122">Selectors and fields are both XPath expressions.</span></span> <span data-ttu-id="9d41b-123">セレクターは、XML ドキュメント、および、セレクター内の特定の項目を識別するフィールドのノードを分離する方法として考えることができます。</span><span class="sxs-lookup"><span data-stu-id="9d41b-123">You can think of selectors as a way to isolate nodes of an XML document, and fields as identifying specific items within the selector.</span></span> <span data-ttu-id="9d41b-124">1 つのセレクター内のすべてのフィールドは、エンジンによって、オブジェクトとしてまとめられます。</span><span class="sxs-lookup"><span data-stu-id="9d41b-124">All the fields inside one selector are grouped together as an object by the engine.</span></span> <span data-ttu-id="9d41b-125">下のノードを選択すると、 **XML スキーマ** タブで、ファクト エクスプ ローラー、ビジネス ルール作成ツールが自動的に入力、 **XPath セレクター** 、すべてのノードのプロパティと**XPath フィールド**に子ノードが含まれていない任意のノードのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="9d41b-125">When you select a node under the **XML Schemas** tab in the Facts Explorer, the Business Rule Composer automatically fills in the **XPath Selector** property for all nodes, and the **XPath Field** property for any node that does not contain child nodes.</span></span> <span data-ttu-id="9d41b-126">独自の XPath 式を入力する代わりに、 **XPath セレクター**と**XPath フィールド**必要な場合。</span><span class="sxs-lookup"><span data-stu-id="9d41b-126">Alternatively, you can enter your own XPath expressions for **XPath Selector** and **XPath Field** if necessary.</span></span>  
  
 <span data-ttu-id="9d41b-127">セレクターには、XML ドキュメントの複数の部分が一致すると、この種類の複数のオブジェクトがアサートまたはルール エンジンの作業メモリから取り消されます。</span><span class="sxs-lookup"><span data-stu-id="9d41b-127">If the selector matches multiple portions of the XML document, multiple objects of this type are asserted into or retracted from the rule engine working memory.</span></span> <span data-ttu-id="9d41b-128">次の XML があると仮定します。</span><span class="sxs-lookup"><span data-stu-id="9d41b-128">Assume you have the following XML.</span></span>  
  
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
  
 <span data-ttu-id="9d41b-129">セレクター/ルート順序を使用する場合 (または/注文/)、2 つのオブジェクトが作業メモリに追加されます。</span><span class="sxs-lookup"><span data-stu-id="9d41b-129">If you use the selector /root/order (or //order), two objects are added to the working memory.</span></span>  
  
 <span data-ttu-id="9d41b-130">1\)</span><span class="sxs-lookup"><span data-stu-id="9d41b-130">1\)</span></span>  
  
```  
<order customer="Joe">  
   <item name="router" quantity="10" cost="550" />  
   <item name="switch" quantity="3" cost="300" />  
</order>  
```  
  
 <span data-ttu-id="9d41b-131">2\)</span><span class="sxs-lookup"><span data-stu-id="9d41b-131">2\)</span></span>  
  
```  
<order customer="Jane">  
   <item name="switch" quantity="1" cost="300" />  
   <item name="cable" quantity="23" cost="9.99" />  
</order>  
```  
  
 <span data-ttu-id="9d41b-132">各セレクター内では、個々 のフィールドを Xpath によって呼びます。</span><span class="sxs-lookup"><span data-stu-id="9d41b-132">Within each selector, the individual fields are referred to by XPaths.</span></span>  
  
 <span data-ttu-id="9d41b-133">セレクター/root/order/item を使用するかどうか (または (//order/item または//item)、4 つのオブジェクトがルール エンジン作業メモリ、Joe の 2 つの項目と Jane の 2 つの項目に追加されます。</span><span class="sxs-lookup"><span data-stu-id="9d41b-133">If you use the selector /root/order/item (or (//order/item or //item), four objects  are added to the rule engine working memory, the two items for Joe and the two items for Jane.</span></span>  
  
```  
<root>  
   <order customer="Joe">  
  
   </order>  
   <order customer="Jane">  
  
   </order>  
</root>  
```  
  
 <span data-ttu-id="9d41b-134">各オブジェクトは、3 つのフィールドにアクセス-@name、 @quantity、および@costします。</span><span class="sxs-lookup"><span data-stu-id="9d41b-134">Each object has access to three fields—@name, @quantity, and @cost.</span></span> <span data-ttu-id="9d41b-135">オブジェクトは元のドキュメントへの参照では、親フィールドを参照できます (たとえば、"../@customer")。</span><span class="sxs-lookup"><span data-stu-id="9d41b-135">Because the object is a reference into the original document, you can refer to parent fields (for example, "../@customer").</span></span>  
  
 <span data-ttu-id="9d41b-136">同じドキュメント内の複数のセレクターを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="9d41b-136">You can use multiple selectors within the same document.</span></span> <span data-ttu-id="9d41b-137">これにより、(場合など、1 つのセクションでは、順序と、別のセクションには、出荷先住所が含まれています)、ドキュメントのさまざまな部分を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="9d41b-137">This enables you to view different parts of the document (for example, if one section is the order and another section contains the shipping address).</span></span> <span data-ttu-id="9d41b-138">ただし、それを作成した、XPath 文字列によって作成されるオブジェクトが定義されていることに留意してください。</span><span class="sxs-lookup"><span data-stu-id="9d41b-138">However, keep in mind that the objects that are created are defined by the XPath string that created them.</span></span> <span data-ttu-id="9d41b-139">一意の結果、同じノードに解決される場合でも、別の XPath 式を使用して**TypedXmlDocument**します。</span><span class="sxs-lookup"><span data-stu-id="9d41b-139">Using a different XPath expression, even if it resolves to the same node, results in a unique **TypedXmlDocument**.</span></span>  
  
 <span data-ttu-id="9d41b-140">ルール エンジンは、参照型のオブジェクトおよびネイティブに基本的な .NET スカラー型をサポートします。</span><span class="sxs-lookup"><span data-stu-id="9d41b-140">The rule engine supports basic .NET scalar types natively, as well as objects for reference types.</span></span> <span data-ttu-id="9d41b-141">XML ドキュメントは、基本的に、テキストがフィールドの値は、ルールの作成時に指定された型に基づき、任意の型指定可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9d41b-141">XML documents are basically text, but based on the type that was specified when the rule was built, the field value may be of any type.</span></span> <span data-ttu-id="9d41b-142">また、フィールドは XPath 式であるために、ケース セットの最初の項目が値として使用されている、ノード セットを返す、可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9d41b-142">Also, because fields are XPath expressions, they may return a nodeset, in which case the first item in the set is used as the value.</span></span>  
  
 <span data-ttu-id="9d41b-143">背後では、ルール エンジンでサポートされている型のいずれかにテキスト フィールドの値を変換できる、 **XmlConvert**関数。</span><span class="sxs-lookup"><span data-stu-id="9d41b-143">Behind the scenes, the rule engine can convert a text field value to any one of the supported types through the **XmlConvert** function.</span></span> <span data-ttu-id="9d41b-144">これは、ビジネス ルール作成ツールの種類を設定を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="9d41b-144">You can specify this by setting the type in the Business Rule Composer.</span></span> <span data-ttu-id="9d41b-145">変換が不可能な場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="9d41b-145">An exception is thrown if a conversion is not possible.</span></span> <span data-ttu-id="9d41b-146">種類**bool**と**二重**それぞれの型、文字列、またはオブジェクトとしてのみ取得できます。</span><span class="sxs-lookup"><span data-stu-id="9d41b-146">The types **bool** and **double** can be retrieved only as their respective type, strings, or objects.</span></span>  
  
## <a name="typeddatatable"></a><span data-ttu-id="9d41b-147">TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="9d41b-147">TypedDataTable</span></span>  
 <span data-ttu-id="9d41b-148">ときに、 **TypedDataTable**がアサートされると、すべて**Datarow**に含まれている、 **DataTable**としてエンジンにアサートが自動的に**TypedDataRows**.</span><span class="sxs-lookup"><span data-stu-id="9d41b-148">When a **TypedDataTable** is asserted, all **DataRows** contained in the **DataTable** are automatically asserted into the engine as **TypedDataRows**.</span></span> <span data-ttu-id="9d41b-149">テーブルまたはテーブルの列がルールの引数として使用される、個人に対して式が評価される**TypedDataRows**、およびに対してではなく、 **TypedDataTable**します。</span><span class="sxs-lookup"><span data-stu-id="9d41b-149">Any time a table or table column is used as a rule argument, the expression is evaluated against the individual **TypedDataRows**, and not against the **TypedDataTable**.</span></span>  
  
 <span data-ttu-id="9d41b-150">たとえば、"Customers"テーブルに対して構築された、次の規則があるとします。</span><span class="sxs-lookup"><span data-stu-id="9d41b-150">For example, suppose that you have the following rule built against a "Customers" table:</span></span>  
  
```  
IF Northwind.Customers.CustomerID = 001  
THEN Northwind.Customers.ContactTitle = "Purchasing Manager"  
```  
  
> [!NOTE]
>  <span data-ttu-id="9d41b-151">使用する必要があります、データベース テーブルに対してルールを構築する**データ テーブル/データ行**データベース バインドの種類として。</span><span class="sxs-lookup"><span data-stu-id="9d41b-151">To build a rule against a database table, you must use **Data table / row** as the database binding type.</span></span>  
  
 <span data-ttu-id="9d41b-152">次をアサートするとします**DataTable** 3 **Datarow**エンジンに (として、 **TypedDataTable**)。</span><span class="sxs-lookup"><span data-stu-id="9d41b-152">Suppose that you assert the following **DataTable** with three **DataRows** into the engine (as a **TypedDataTable**).</span></span>  
  
|<span data-ttu-id="9d41b-153">CustomerID</span><span class="sxs-lookup"><span data-stu-id="9d41b-153">CustomerID</span></span>|<span data-ttu-id="9d41b-154">[部署]</span><span class="sxs-lookup"><span data-stu-id="9d41b-154">ContactTitle</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="9d41b-155">001</span><span class="sxs-lookup"><span data-stu-id="9d41b-155">001</span></span>|<span data-ttu-id="9d41b-156">クラークを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d41b-156">Supply Clerk</span></span>|  
|<span data-ttu-id="9d41b-157">002</span><span class="sxs-lookup"><span data-stu-id="9d41b-157">002</span></span>|<span data-ttu-id="9d41b-158">クラークを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d41b-158">Supply Clerk</span></span>|  
|<span data-ttu-id="9d41b-159">003</span><span class="sxs-lookup"><span data-stu-id="9d41b-159">003</span></span>|<span data-ttu-id="9d41b-160">クラークを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d41b-160">Supply Clerk</span></span>|  
  
 <span data-ttu-id="9d41b-161">3 つのエンジンが挿入**TypedDataRows**:001、002、003</span><span class="sxs-lookup"><span data-stu-id="9d41b-161">The engine inserts three **TypedDataRows**: 001, 002, and 003.</span></span>  
  
 <span data-ttu-id="9d41b-162">各**TypedDataRow**ルールに対して個別に評価します。</span><span class="sxs-lookup"><span data-stu-id="9d41b-162">Each **TypedDataRow** is evaluated independently against the rule.</span></span> <span data-ttu-id="9d41b-163">最初の**TypedDataRow**ルールの条件と 2 つの失敗を満たしています。</span><span class="sxs-lookup"><span data-stu-id="9d41b-163">The first **TypedDataRow** meets the rule condition and the second two fail.</span></span> <span data-ttu-id="9d41b-164">結果は次のようです。</span><span class="sxs-lookup"><span data-stu-id="9d41b-164">The results appear as follows.</span></span>  
  
|<span data-ttu-id="9d41b-165">CustomerID</span><span class="sxs-lookup"><span data-stu-id="9d41b-165">CustomerID</span></span>|<span data-ttu-id="9d41b-166">[部署]</span><span class="sxs-lookup"><span data-stu-id="9d41b-166">ContactTitle</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="9d41b-167">001</span><span class="sxs-lookup"><span data-stu-id="9d41b-167">001</span></span>|<span data-ttu-id="9d41b-168">購買担当マネージャー</span><span class="sxs-lookup"><span data-stu-id="9d41b-168">Purchasing Manager</span></span>|  
|<span data-ttu-id="9d41b-169">002</span><span class="sxs-lookup"><span data-stu-id="9d41b-169">002</span></span>|<span data-ttu-id="9d41b-170">クラークを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d41b-170">Supply Clerk</span></span>|  
|<span data-ttu-id="9d41b-171">003</span><span class="sxs-lookup"><span data-stu-id="9d41b-171">003</span></span>|<span data-ttu-id="9d41b-172">クラークを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d41b-172">Supply Clerk</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="9d41b-173">TypedDataRows も、エンジンにアサート直接ことができます。</span><span class="sxs-lookup"><span data-stu-id="9d41b-173">TypedDataRows can also be directly asserted into the engine.</span></span> <span data-ttu-id="9d41b-174">これらには、前述のと同じ方法で処理されます。</span><span class="sxs-lookup"><span data-stu-id="9d41b-174">These are processed in the same way as described earlier.</span></span>  
  
 <span data-ttu-id="9d41b-175">**DataSetName.DataTableName**一意識別子と見なされます。</span><span class="sxs-lookup"><span data-stu-id="9d41b-175">The **DataSetName.DataTableName** is considered to be a unique identifier.</span></span> <span data-ttu-id="9d41b-176">そのため、2 番目の場合**TypedDataTable**がアサートされた同じ**データセット**名と**DataTable**名、1 つ目の後継となります**TypedDataTable**.</span><span class="sxs-lookup"><span data-stu-id="9d41b-176">Therefore, if a second **TypedDataTable** is asserted with the same **DataSet** name and **DataTable** name, it supersedes the first **TypedDataTable**.</span></span> <span data-ttu-id="9d41b-177">すべて**TypedDataRow**s が最初に関連付けられている**TypedDataTable**は取り消され、2 番目**TypedDataTable**がアサートされます。</span><span class="sxs-lookup"><span data-stu-id="9d41b-177">All **TypedDataRow**s associated with the first **TypedDataTable** are retracted, and the second **TypedDataTable** is asserted.</span></span>  
  
## <a name="dataconnection"></a><span data-ttu-id="9d41b-178">DataConnection</span><span class="sxs-lookup"><span data-stu-id="9d41b-178">DataConnection</span></span>  
 <span data-ttu-id="9d41b-179">同様、 **TypedDataTable**、結果、返されたに対してルールが作成、ビジネス ルール作成ツールでルールの引数としてテーブルまたは列をドラッグ**TypedDataRow**ではなく、 **DataConnection**自体。</span><span class="sxs-lookup"><span data-stu-id="9d41b-179">As with a **TypedDataTable**, dragging a table or column as a rule argument in the Business Rule Composer results in rules built against the returned **TypedDataRow**s as opposed to the **DataConnection** itself.</span></span>  
  
 <span data-ttu-id="9d41b-180">たとえば、次の規則が作成されると**DataConnection**アサートされる、 **SqlConnection** Northwind.Customers に。</span><span class="sxs-lookup"><span data-stu-id="9d41b-180">Suppose that the following rule is created and a **DataConnection** is asserted that contains a **SqlConnection** to Northwind.Customers:</span></span>  
  
```  
IF Northwind.Customers.CustomerID = 001  
THEN Northwind.Customers.ContactTitle = "Purchasing Manager"  
```  
  
 <span data-ttu-id="9d41b-181">エンジンがで使用されるルールと評価される場合、 **TypedDataTable**  セクションで、動的に作成し、次のようなクエリ。</span><span class="sxs-lookup"><span data-stu-id="9d41b-181">When the engine evaluates the rule used in the **TypedDataTable** section, it dynamically builds a query that looks like:</span></span>  
  
```  
SELECT *  
FROM Northwind.Customers  
WHERE CustomerID = 1  
```  
  
 <span data-ttu-id="9d41b-182">データベースの 1 つだけの行が 1 つだけ、この条件を満たしているので**TypedDataRow**が作成され、さらに処理エンジンにアサートします。</span><span class="sxs-lookup"><span data-stu-id="9d41b-182">Because only one row in the database meets this criterion, only one **TypedDataRow** is created and asserted into the engine for further processing.</span></span>  
  
## <a name="summary-of-asserted-entities-and-instance-types"></a><span data-ttu-id="9d41b-183">アサートされるエンティティとインスタンスの型の概要</span><span class="sxs-lookup"><span data-stu-id="9d41b-183">Summary of Asserted Entities and Instance Types</span></span>  
 <span data-ttu-id="9d41b-184">次の表は、それらを識別するためにそれらのインスタンスのそれぞれに適用される型と同様に、アサートされた各エンティティのエンジンで作成された結果として得られるインスタンスの数を示す、さまざまな種類の assert の動作をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="9d41b-184">The following table summarizes the assert behavior for the various types, showing the number of resulting instances created in the engine for each asserted entity, as well as the type that is applied to each of those instances to identify them.</span></span>  
  
|<span data-ttu-id="9d41b-185">Entity</span><span class="sxs-lookup"><span data-stu-id="9d41b-185">Entity</span></span>|<span data-ttu-id="9d41b-186">アサートされるインスタンスの数</span><span class="sxs-lookup"><span data-stu-id="9d41b-186">Number of instances asserted</span></span>|<span data-ttu-id="9d41b-187">インスタンスの種類</span><span class="sxs-lookup"><span data-stu-id="9d41b-187">Instance type</span></span>|  
|------------|----------------------------------|-------------------|  
|<span data-ttu-id="9d41b-188">.NET オブジェクト</span><span class="sxs-lookup"><span data-stu-id="9d41b-188">.NET object</span></span>|<span data-ttu-id="9d41b-189">1 (オブジェクト自体)</span><span class="sxs-lookup"><span data-stu-id="9d41b-189">1 (the object itself)</span></span>|<span data-ttu-id="9d41b-190">完全修飾 .NET クラス</span><span class="sxs-lookup"><span data-stu-id="9d41b-190">Fully Qualified .NET Class</span></span>|  
|<span data-ttu-id="9d41b-191">TypedXmlDocument</span><span class="sxs-lookup"><span data-stu-id="9d41b-191">TypedXmlDocument</span></span>|<span data-ttu-id="9d41b-192">1 ~ n 個の TypedXmlDocument (s):作成されるセレクター バインドとドキュメントのコンテンツに基づく</span><span class="sxs-lookup"><span data-stu-id="9d41b-192">1-N TypedXmlDocument(s): Based on Selector bindings created and document content</span></span>|<span data-ttu-id="9d41b-193">DocumentType.Selector</span><span class="sxs-lookup"><span data-stu-id="9d41b-193">DocumentType.Selector</span></span>|  
|<span data-ttu-id="9d41b-194">TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="9d41b-194">TypedDataTable</span></span>|<span data-ttu-id="9d41b-195">1 ~ n 個の TypedDataRow (s):</span><span class="sxs-lookup"><span data-stu-id="9d41b-195">1-N TypedDataRow(s):</span></span><br /><br /> <span data-ttu-id="9d41b-196">DataTable 内の各 DataRow のいずれか</span><span class="sxs-lookup"><span data-stu-id="9d41b-196">One for each DataRow in the DataTable</span></span>|<span data-ttu-id="9d41b-197">DataSetName.DataTableName</span><span class="sxs-lookup"><span data-stu-id="9d41b-197">DataSetName.DataTableName</span></span>|  
|<span data-ttu-id="9d41b-198">TypedDataRow</span><span class="sxs-lookup"><span data-stu-id="9d41b-198">TypedDataRow</span></span>|<span data-ttu-id="9d41b-199">1 (アサートされる TypedDataRow)</span><span class="sxs-lookup"><span data-stu-id="9d41b-199">1 (the TypedDataRow asserted)</span></span>|<span data-ttu-id="9d41b-200">DataSetName.DataTableName</span><span class="sxs-lookup"><span data-stu-id="9d41b-200">DataSetName.DataTableName</span></span>|  
|<span data-ttu-id="9d41b-201">DataConnection</span><span class="sxs-lookup"><span data-stu-id="9d41b-201">DataConnection</span></span>|<span data-ttu-id="9d41b-202">1 ~ N (DataConnection の照会によって返される各 typeddatarow につき 1 つ)</span><span class="sxs-lookup"><span data-stu-id="9d41b-202">1-N (one for each TypedDataRow returned by querying the DataConnection)</span></span>|<span data-ttu-id="9d41b-203">DataSetName.DataTableName</span><span class="sxs-lookup"><span data-stu-id="9d41b-203">DataSetName.DataTableName</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9d41b-204">参照</span><span class="sxs-lookup"><span data-stu-id="9d41b-204">See Also</span></span>  
 [<span data-ttu-id="9d41b-205">エンジン制御関数</span><span class="sxs-lookup"><span data-stu-id="9d41b-205">Engine Control Functions</span></span>](../core/engine-control-functions.md)