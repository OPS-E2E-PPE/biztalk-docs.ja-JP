---
title: 型指定されたファクト |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RuleEngine library
- Business Rule Composer, typed facts
- ITypedFact interface
- DataConnection class
- facts, typed
- TypedDataTable class
- TypedDataRow class
- TypedXmlDocument class
ms.assetid: 8207bfd5-ebd2-45ac-8992-795acdf3ba4c
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6041a64fcc4b3496c319a25a2ce758ed7f52a71
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="typed-facts"></a><span data-ttu-id="c317e-102">型指定されたファクト</span><span class="sxs-lookup"><span data-stu-id="c317e-102">Typed Facts</span></span>
<span data-ttu-id="c317e-103">*型指定されたファクト* クラスを実装するには、 **ITypedFact** インターフェイス: **TypedXmlDocument**, 、**DataConnection**, 、**TypedDataTable**, 、および **TypedDataRow**します。</span><span class="sxs-lookup"><span data-stu-id="c317e-103">*Typed facts* are classes that implement the **ITypedFact** interface: **TypedXmlDocument**, **DataConnection**, **TypedDataTable**, and **TypedDataRow**.</span></span>  
  
## <a name="typedxmldocument"></a><span data-ttu-id="c317e-104">TypedXmlDocument</span><span class="sxs-lookup"><span data-stu-id="c317e-104">TypedXmlDocument</span></span>  
 <span data-ttu-id="c317e-105">**TypedXmlDocument** クラスは、ビジネス ルール フレームワークで XML ドキュメントの種類を表します。</span><span class="sxs-lookup"><span data-stu-id="c317e-105">The **TypedXmlDocument** class represents the XML document type in the Business Rules Framework.</span></span> <span data-ttu-id="c317e-106">2 つの XPath 式を作成するルールの引数として、XML ドキュメントのノードを使用する場合: セレクターとフィールド バインドします。</span><span class="sxs-lookup"><span data-stu-id="c317e-106">When you use a node of an XML document as an argument in a rule, two XPath expressions are created: the Selector and Field bindings.</span></span>  
  
 <span data-ttu-id="c317e-107">ノードに子ノードがあるない場合、 *セレクター バインド* (XmlDocument バインド) がノードの親ノードを作成し、 *フィールドのバインド* ノード自体を (XmlDocumentMember バインドとも呼ばれます) を作成します。</span><span class="sxs-lookup"><span data-stu-id="c317e-107">If the node has no child nodes, a *Selector binding* (also known as an XmlDocument binding) is created to the node's parent node and a *Field binding* (also known as an XmlDocumentMember binding) is created to the node itself.</span></span> <span data-ttu-id="c317e-108">このフィールド バインドはセレクター バインドと相対的な関係にあります。</span><span class="sxs-lookup"><span data-stu-id="c317e-108">This Field binding is relative to the Selector binding.</span></span> <span data-ttu-id="c317e-109">ノードに子ノードがある場合は、そのノードにセレクター バインドが作成され、フィールド バインドは作成されません。</span><span class="sxs-lookup"><span data-stu-id="c317e-109">If the node has child nodes, a Selector binding is created to the node and no Field binding is created.</span></span>  
  
 <span data-ttu-id="c317e-110">次のスキーマがあると仮定します。</span><span class="sxs-lookup"><span data-stu-id="c317e-110">Suppose that you have the following schema.</span></span>  
  
 <span data-ttu-id="c317e-111">![ファクト エクスプ ローラーに表示されたサンプル スキーマ](../core/media/xmldocumentbrowser.gif "xmldocumentbrowser")</span><span class="sxs-lookup"><span data-stu-id="c317e-111">![Sample schema displayed in Facts Explorer](../core/media/xmldocumentbrowser.gif "xmldocumentbrowser")</span></span>  
<span data-ttu-id="c317e-112">Case.xsd</span><span class="sxs-lookup"><span data-stu-id="c317e-112">Case.xsd</span></span>  
  
 <span data-ttu-id="c317e-113">Income ノードが選択されている場合は、このノードに子ノードがないため、セレクター バインドのみが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c317e-113">If the Income node is selected, only a Selector binding is created, because the node has child nodes.</span></span> <span data-ttu-id="c317e-114">既定の XPath 式、 **XPath セレクター** プロパティ ペインのプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c317e-114">The default XPath expression in the **XPath Selector** property of the Property pane contains:</span></span>  
  
```  
/*[local-name()='Root' and namespace-uri()='http://LoansProcessor.Case']/*[local-name()='Income' and namespace-uri()='']  
```  
  
 <span data-ttu-id="c317e-115">一方、Name ノードが選択されている場合は、セレクター バインドとフィールド バインドが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c317e-115">However, if the Name node is selected, both a Selector binding and a Field binding are created.</span></span> <span data-ttu-id="c317e-116">バインド情報は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="c317e-116">The binding information looks like.</span></span>  
  
|<span data-ttu-id="c317e-117">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c317e-117">Property</span></span>|<span data-ttu-id="c317e-118">値</span><span class="sxs-lookup"><span data-stu-id="c317e-118">Value</span></span>|  
|--------------|-----------|  
|<span data-ttu-id="c317e-119">**XPath フィールド**</span><span class="sxs-lookup"><span data-stu-id="c317e-119">**XPath Field**</span></span>|<span data-ttu-id="c317e-120">\*[local-name()='Name' and namespace-uri()='']</span><span class="sxs-lookup"><span data-stu-id="c317e-120">\*[local-name()='Name' and namespace-uri()='']</span></span>|  
|<span data-ttu-id="c317e-121">**XPath セレクター**</span><span class="sxs-lookup"><span data-stu-id="c317e-121">**XPath Selector**</span></span>|<span data-ttu-id="c317e-122">/\*[local-name()='Root' and namespace-uri()='http://LoansProcessor.Case']</span><span class="sxs-lookup"><span data-stu-id="c317e-122">/\*[local-name()='Root' and namespace-uri()='http://LoansProcessor.Case']</span></span>|  
  
 <span data-ttu-id="c317e-123">ノードをルールの引数にドラッグする前に、XML ノードに対する既定の XPath 式を変更することもできます。これにより、新しいバインド情報がポリシーに含められます。</span><span class="sxs-lookup"><span data-stu-id="c317e-123">You can change the default XPath expressions for the XML nodes before you drag the node into a rule argument, and the new binding information is placed in the policy.</span></span> <span data-ttu-id="c317e-124">ただし、XPath 式に加えた編集はすべて、スキーマを再読み込みするときにビジネス ルール作成ツールで再入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c317e-124">Note, however, that any edits that are made to the XPath expressions must be re-entered in the Business Rule Composer when the schema is reloaded.</span></span>  
  
 <span data-ttu-id="c317e-125">XML ノードのボキャブラリ定義が作成される際、バインドの XPath 式には、前に説明したルールに基づいた同様の既定値が設定されますが、これはボキャブラリ定義ウィザードで編集できます。</span><span class="sxs-lookup"><span data-stu-id="c317e-125">When vocabulary definitions are created for XML nodes, the XPath expressions for the bindings have similar defaults based on the rules described earlier, but can be edited in the Vocabulary Definition Wizard.</span></span> <span data-ttu-id="c317e-126">式に加えた変更はボキャブラリ定義に含められ、その定義から作成されたルールの引数すべてに反映されます。</span><span class="sxs-lookup"><span data-stu-id="c317e-126">Changes to the expressions are placed in the vocabulary definition and are reflected in any rule arguments built from the definitions.</span></span>  
  
## <a name="dataconnection"></a><span data-ttu-id="c317e-127">DataConnection</span><span class="sxs-lookup"><span data-stu-id="c317e-127">DataConnection</span></span>  
 <span data-ttu-id="c317e-128">**DataConnection** .NET クラスに追加された、 **RuleEngine** ライブラリです。</span><span class="sxs-lookup"><span data-stu-id="c317e-128">**DataConnection** is a .NET class provided in the **RuleEngine** library.</span></span> <span data-ttu-id="c317e-129">.NET が含まれている **SqlConnection** インスタンスおよび **データセット** 名。</span><span class="sxs-lookup"><span data-stu-id="c317e-129">It contains a .NET **SqlConnection** instance and a **DataSet** name.</span></span> <span data-ttu-id="c317e-130">**データセット** 名では、一意の識別子を作成することができます、 **SqlConnection** され、結果の型を定義する際に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c317e-130">The **DataSet** name enables you to create a unique identifier for the **SqlConnection** and is used in defining the resulting type.</span></span>  
  
 <span data-ttu-id="c317e-131">**DataConnection** クラスには、パフォーマンスを最適化するには、ビジネス ルール エンジンが用意されています。</span><span class="sxs-lookup"><span data-stu-id="c317e-131">The **DataConnection** class provides a performance optimization to the Business Rule engine.</span></span> <span data-ttu-id="c317e-132">エンジンの非常に大規模なデータベース テーブルにアサートするのではなく (**TypedDataTable** クラス) 多数のデータベース行が含まれている可能性があります (**TypedDataRow** クラス) は、ポリシーに関連するでは、軽量をアサートする **DataConnection**します。</span><span class="sxs-lookup"><span data-stu-id="c317e-132">Rather than asserting into the engine very large database tables (**TypedDataTable** class) that may contain many database rows (**TypedDataRow** class) that are not relevant to the policy, you can assert a lightweight **DataConnection**.</span></span> <span data-ttu-id="c317e-133">ルールの述語やアクションとクエリに基づく SELECT クエリを動的に作成し、エンジンは、ポリシーを評価するとき、 **DataConnection** の実行時。</span><span class="sxs-lookup"><span data-stu-id="c317e-133">When the engine evaluates a policy, it dynamically builds a SELECT query based on the rule predicates/actions and queries the **DataConnection** at execution.</span></span> <span data-ttu-id="c317e-134">たとえば、次のようなルールがあるとします。</span><span class="sxs-lookup"><span data-stu-id="c317e-134">For example, suppose you have the following rule:</span></span>  
  
```  
IF NorthWind.Products.UnitPrice >= 0   
THEN <do something>  
```  
  
 <span data-ttu-id="c317e-135">次の SQL クエリは、ルールで生成されます。</span><span class="sxs-lookup"><span data-stu-id="c317e-135">The following SQL query is generated by from the rule:</span></span>  
  
```  
Select * From [Product] Where [UnitPrice] >= 0  
```  
  
 <span data-ttu-id="c317e-136">クエリの結果がデータ行としてエンジンにアサートされます。</span><span class="sxs-lookup"><span data-stu-id="c317e-136">The results of the query are asserted back into the engine as data rows.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c317e-137">使用、 **OleDbConnection** で、 **DataConnection** は現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c317e-137">The use of an **OleDbConnection** in a **DataConnection** is not currently supported.</span></span>  
  
 <span data-ttu-id="c317e-138">ルール条件またはアクションで使用するデータベースのテーブルまたは列を選択するときに、いずれかを使用してオブジェクトにバインドできます **DataConnection** または **TypedDataTable** から データ接続 または データベースのテーブルの行/"を選択して、 **データベース バインドの種類**ドロップダウン ボックスの プロパティ ウィンドウで、 **データベース** ファクト エクスプ ローラーのタブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c317e-138">When you select a database table/column to use in a rule condition or action, you can choose to bind to the object using either **DataConnection** or **TypedDataTable** by selecting "Data connection" or "Database table/row" from the **Database binding type**drop-down box in the Property Window for the **Databases** tab of Fact Explorer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c317e-139">既定では DataConnection バインドが使用されます。</span><span class="sxs-lookup"><span data-stu-id="c317e-139">The DataConnection binding is used by default.</span></span>  
  
## <a name="typeddatatable"></a><span data-ttu-id="c317e-140">TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="c317e-140">TypedDataTable</span></span>  
 <span data-ttu-id="c317e-141">ADO.NET をアサートする **DataTable** 、エンジンにオブジェクトが他の .NET オブジェクトと同様に扱われます。</span><span class="sxs-lookup"><span data-stu-id="c317e-141">You can assert an ADO.NET **DataTable** object into the engine, but it will be treated like any other .NET object.</span></span> <span data-ttu-id="c317e-142">ほとんどの場合は代わりにするルール エンジン クラスをアサート **TypedDataTable**します。</span><span class="sxs-lookup"><span data-stu-id="c317e-142">In most cases you will instead want to assert the rule engine class **TypedDataTable**.</span></span>  
  
 <span data-ttu-id="c317e-143">**TypedDataTable** ADO.NET を含んでいるラッパー クラスは、 **DataTable**します。</span><span class="sxs-lookup"><span data-stu-id="c317e-143">**TypedDataTable** is a wrapper class that contains an ADO.NET **DataTable**.</span></span> <span data-ttu-id="c317e-144">コンス トラクターを受け取り、 **DataTable**します。</span><span class="sxs-lookup"><span data-stu-id="c317e-144">The constructor simply takes a **DataTable**.</span></span> <span data-ttu-id="c317e-145">テーブルまたはテーブルの列がルールの引数として使用される、個人に対して式が評価されます **TypedDataRow** ラッパーでなく、 **TypedDataTable**します。</span><span class="sxs-lookup"><span data-stu-id="c317e-145">Any time a table or table column is used as a rule argument, the expression is evaluated against the individual **TypedDataRow** wrappers, and not against the **TypedDataTable**.</span></span>  
  
## <a name="typeddatarow"></a><span data-ttu-id="c317e-146">TypedDataRow</span><span class="sxs-lookup"><span data-stu-id="c317e-146">TypedDataRow</span></span>  
 <span data-ttu-id="c317e-147">これは、ADO の型指定されたファクト ラッパー **DataRow** オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="c317e-147">This is a typed fact wrapper for an ADO **DataRow** object.</span></span> <span data-ttu-id="c317e-148">ビジネス ルール作成ツールでルールの引数にテーブルまたは列をドラッグする結果、返されたに対してルールが作成、 **TypedDataRow** ラッパーです。</span><span class="sxs-lookup"><span data-stu-id="c317e-148">Dragging a table or column to a rule argument in the Business Rule Composer results in rules built against the returned **TypedDataRow** wrappers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c317e-149">参照</span><span class="sxs-lookup"><span data-stu-id="c317e-149">See Also</span></span>  
 [<span data-ttu-id="c317e-150">ファクト</span><span class="sxs-lookup"><span data-stu-id="c317e-150">Facts</span></span>](../core/facts.md)