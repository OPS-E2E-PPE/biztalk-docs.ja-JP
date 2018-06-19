---
title: Null および DBNull を処理する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, NULL
ms.assetid: d235c265-4947-470b-9f2d-9936ae1b88a1
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b07ac74828a858b368cac5d401081a58b8602323
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255042"
---
# <a name="how-to-handle-null-and-dbnull"></a><span data-ttu-id="b3fd7-102">Null および DBNull を処理する方法</span><span class="sxs-lookup"><span data-stu-id="b3fd7-102">How to Handle Null and DBNull</span></span>
<span data-ttu-id="b3fd7-103">このトピックでは、さまざまな型に関連する Null 値が処理されるときの予期される動作、および特定のフィールドまたはメンバーについて Null または存在の有無をチェックするためのオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b3fd7-103">This topic describes the expected behaviors when dealing with null values associated with different types, and discusses options for checking null or existence of a particular field or member.</span></span>  
  
## <a name="xml"></a><span data-ttu-id="b3fd7-104">XML</span><span class="sxs-lookup"><span data-stu-id="b3fd7-104">XML</span></span>  
 <span data-ttu-id="b3fd7-105">次の説明は XML に関係します。</span><span class="sxs-lookup"><span data-stu-id="b3fd7-105">The following applies to XML:</span></span>  
  
-   <span data-ttu-id="b3fd7-106">ドキュメントから XML 値が Null として返されることはありません。</span><span class="sxs-lookup"><span data-stu-id="b3fd7-106">An XML value will never be returned from a document as null.</span></span> <span data-ttu-id="b3fd7-107">これは空の文字列または "存在しない" エラーのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="b3fd7-107">It is either an empty string or a "does not exist" error.</span></span> <span data-ttu-id="b3fd7-108">空の文字列の場合は、特定の型 (たとえばルール作成時に整数型として指定されたフィールド) の変換でエラーが発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="b3fd7-108">When it is an empty string, an error may occur for conversion of certain types, for example, fields specified as an integer type when building rules.</span></span>  
  
-   <span data-ttu-id="b3fd7-109">ビジネス ルール作成ツールで許可するフィールドを null に設定したりするためのフィールドの種類を設定していない**オブジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="b3fd7-109">The Business Rule Composer does not allow you to set a field to null or to set the type of a field to **object**.</span></span>  
  
-   <span data-ttu-id="b3fd7-110">オブジェクト モデルを使用型を設定できます**オブジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="b3fd7-110">Through the object model you can set the type to **Object**.</span></span> <span data-ttu-id="b3fd7-111">この場合、返される値は、XPath の評価結果の種類- **float**、**ブール**、または**文字列**XPath 式に応じて、します。</span><span class="sxs-lookup"><span data-stu-id="b3fd7-111">In this case, the value returned is the type to which the XPath evaluates— **float**, **boolean**, or **string**, depending on the XPath expression.</span></span>  
  
## <a name="net-classes"></a><span data-ttu-id="b3fd7-112">.NET クラス</span><span class="sxs-lookup"><span data-stu-id="b3fd7-112">.NET classes</span></span>  
 <span data-ttu-id="b3fd7-113">次の説明は .NET クラスに関係します。</span><span class="sxs-lookup"><span data-stu-id="b3fd7-113">The following applies to .NET classes:</span></span>  
  
-   <span data-ttu-id="b3fd7-114">戻り値の型がない場合、null と比較することはできません、**オブジェクト**型です。</span><span class="sxs-lookup"><span data-stu-id="b3fd7-114">You are not allowed to compare to null if your return type is not an **object** type.</span></span>  
  
-   <span data-ttu-id="b3fd7-115">値の型以外のパラメーターには Null をパラメーターとして渡せますが、メンバーの実装によっては実行時エラーが発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="b3fd7-115">You can pass null as a parameter for parameters that are not value types, but you may get a runtime error, depending on the implementation of the member.</span></span>  
  
-   <span data-ttu-id="b3fd7-116">派生した型のフィールドを設定することができます**オブジェクト**を null にします。</span><span class="sxs-lookup"><span data-stu-id="b3fd7-116">You can set fields of types derived from **Object** to null.</span></span>  
  
## <a name="data-connection"></a><span data-ttu-id="b3fd7-117">データ接続</span><span class="sxs-lookup"><span data-stu-id="b3fd7-117">Data connection</span></span>  
 <span data-ttu-id="b3fd7-118">次の説明はデータ接続に関係します。</span><span class="sxs-lookup"><span data-stu-id="b3fd7-118">The following applies to a data connection:</span></span>  
  
-   <span data-ttu-id="b3fd7-119">Null には、データベース テーブルの列を比較するには、テーブル、列の null を許可すると、列の型が**テキスト**、 **ntext**、および**イメージ**です。</span><span class="sxs-lookup"><span data-stu-id="b3fd7-119">You can compare any database table column to null, if the table allows nulls for the column and the column type is not **text**, **ntext**, and **image**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b3fd7-120">ビジネス ルール作成ツールでは、型の列を使用することができます**テキスト**と**ntext**条件にします。</span><span class="sxs-lookup"><span data-stu-id="b3fd7-120">The Business Rule Composer allows you to use columns of type, **text** and **ntext**, in conditions.</span></span> <span data-ttu-id="b3fd7-121">ただし、そのポリシーを実行すると、"IS NULL または LIKE 演算子を使用している場合を除き、テキスト、ntext、および画像のデータ型の比較や並べ替えはできません" というエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3fd7-121">However, when you execute the policy, you will receive an error message, which says, "The text, ntext, and image data types cannot be compared or sorted, except when using IS NULL or LIKE operator".</span></span>  
  
-   <span data-ttu-id="b3fd7-122">データベース テーブルの列に対してテーブルで Null が許可されている場合は、その列を Null に設定できます。</span><span class="sxs-lookup"><span data-stu-id="b3fd7-122">You can set any database table column to null, if the table allows nulls for the column.</span></span>  
  
-   <span data-ttu-id="b3fd7-123">ビジネス ルール作成ツールへのバインドで、メンバーの種類を自動的に設定**オブジェクト**比較またはに設定した場合、値型の場合は null です。 リセットするか、引数を置換する場合、元の型に変更します。</span><span class="sxs-lookup"><span data-stu-id="b3fd7-123">The Business Rule Composer automatically sets the member type in the binding to **object**, if you compare or set to null for a value type; it changes back to the original type if you reset or replace the argument.</span></span>  
  
-   <span data-ttu-id="b3fd7-124">文字列型の場合に型を変更**オブジェクト**かどうかを null に設定が状態のままを文字列として null と比較する場合。</span><span class="sxs-lookup"><span data-stu-id="b3fd7-124">For a string type, it changes the type to **object** if you set it to null, but leaves it as a string if you compare against null.</span></span>  
  
-   <span data-ttu-id="b3fd7-125">比較またはに設定することはできません**DBNull.Value** 、ビジネス ルール作成ツールから、列の型には変化しないため**オブジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="b3fd7-125">You cannot compare or set to **DBNull.Value** from the Business Rule Composer, because it will not change the column type to **object**.</span></span>  
  
-   <span data-ttu-id="b3fd7-126">エンジンでは、比較の際に DBNull 値が Null に変換され、データベースに挿入する際に Null が DBNull 値に変換されます。</span><span class="sxs-lookup"><span data-stu-id="b3fd7-126">The engine will convert a DBNull value to null for comparison and will convert null to a DBNull value for insertion into the database.</span></span>  
  
-   <span data-ttu-id="b3fd7-127">テストでは Null 値が無視されます (SQL Server の動作)。</span><span class="sxs-lookup"><span data-stu-id="b3fd7-127">Tests will ignore null values (this is the way SQL Server works).</span></span> <span data-ttu-id="b3fd7-128">たとえば、"IF db.column > 5 THEN" というルールがある場合は、db.column に値がある行のみがテストされ、Null を含んでいる行はスキップされます。</span><span class="sxs-lookup"><span data-stu-id="b3fd7-128">For example, if you have the rule "IF db.column > 5 THEN .", only the rows that have a value in db.column are tested—rows with null are skipped.</span></span>  
  
## <a name="typeddatatable-and-typeddatarow"></a><span data-ttu-id="b3fd7-129">TypedDataTable および TypedDataRow</span><span class="sxs-lookup"><span data-stu-id="b3fd7-129">TypedDataTable and TypedDataRow</span></span>  
 <span data-ttu-id="b3fd7-130">次の説明は TypedDataTable および TypedDataRow に関係します。</span><span class="sxs-lookup"><span data-stu-id="b3fd7-130">The following applies to TypedDataTable and TypedDataRow:</span></span>  
  
-   <span data-ttu-id="b3fd7-131">ビジネス ルール作成ツールの変更、フィールドの種類を**オブジェクト**と同じ方法で**DataConnection**s。</span><span class="sxs-lookup"><span data-stu-id="b3fd7-131">The Business Rule Composer changes the field type to **object** in the same manner as with **DataConnection**s.</span></span>  
  
-   <span data-ttu-id="b3fd7-132">Null と比較する場合を除いて、Null 値があるとテストは失敗します。</span><span class="sxs-lookup"><span data-stu-id="b3fd7-132">Tests will fail for null values, unless you are comparing to null.</span></span> <span data-ttu-id="b3fd7-133">たとえば、アサートされた行に Null 値が含まれている場合は、ルール "IF db.column > 5 THEN" でエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="b3fd7-133">For example, there will be an error in the rule "IF db.column > 5 THEN ", if any row asserted has a null value.</span></span>  
  
     <span data-ttu-id="b3fd7-134">条件は同時に評価されるため、"IF db.column != NULL AND db.column > 5 THEN  " のようなテストも失敗するので注意してください。これは、すべての行で両方のテストが評価される可能性があるからです。</span><span class="sxs-lookup"><span data-stu-id="b3fd7-134">Note that because conditions are evaluated in parallel, tests like "IF db.column != NULL AND db.column > 5 THEN  " will still fail, because both tests are potentially evaluated on every row.</span></span>  
  
## <a name="checking-for-null-or-existence"></a><span data-ttu-id="b3fd7-135">Null または存在の有無のチェック</span><span class="sxs-lookup"><span data-stu-id="b3fd7-135">Checking for null or existence</span></span>  
 <span data-ttu-id="b3fd7-136">ビジネス ルールを作成するときには、通常、フィールドの値を比較する前にそのフィールドの存在を確認します。</span><span class="sxs-lookup"><span data-stu-id="b3fd7-136">When writing business rules, it is natural to check for the existence of a field before comparing its value.</span></span> <span data-ttu-id="b3fd7-137">ただし、フィールドが Null かまたは存在しない場合に値を比較すると、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="b3fd7-137">However, if the field is null or does not exist, comparing the value will cause an error.</span></span> <span data-ttu-id="b3fd7-138">たとえば、次のルールがあるとします。</span><span class="sxs-lookup"><span data-stu-id="b3fd7-138">Assume you have the following rule:</span></span>  
  
 <span data-ttu-id="b3fd7-139">IF Product/Quantity Exists AND Product/Quantity > 1</span><span class="sxs-lookup"><span data-stu-id="b3fd7-139">IF Product/Quantity Exists AND Product/Quantity > 1</span></span>  
  
 <span data-ttu-id="b3fd7-140">Product/Quantity が存在しない場合は、ルールでエラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="b3fd7-140">An error will be thrown in the rule if Product/Quantity does not exist.</span></span> <span data-ttu-id="b3fd7-141">この問題を回避する 1 つの方法として、要素の値が存在する場合にその値を返し、存在しない場合は別のものを返すヘルパー メソッドに親ノードを渡します。</span><span class="sxs-lookup"><span data-stu-id="b3fd7-141">One of the ways to circumvent this problem is to pass a parent node to a helper method that returns the element value if it exists or something else if it does not.</span></span> <span data-ttu-id="b3fd7-142">次のルールを見てください。</span><span class="sxs-lookup"><span data-stu-id="b3fd7-142">See the following rules.</span></span>  
  
 <span data-ttu-id="b3fd7-143">**ルール 1**</span><span class="sxs-lookup"><span data-stu-id="b3fd7-143">**Rule 1**</span></span>  
  
 <span data-ttu-id="b3fd7-144">IF EXISTS(Product/Quantity) THEN ASSERT(CREATEOBJECT(typeof(Helper), Product/Quantity)</span><span class="sxs-lookup"><span data-stu-id="b3fd7-144">IF EXISTS(Product/Quantity) THEN ASSERT(CREATEOBJECT(typeof(Helper), Product/Quantity)</span></span>  
  
 <span data-ttu-id="b3fd7-145">**規則 2**</span><span class="sxs-lookup"><span data-stu-id="b3fd7-145">**Rule 2**</span></span>  
  
 <span data-ttu-id="b3fd7-146">IF Helper.Value == X THEN...</span><span class="sxs-lookup"><span data-stu-id="b3fd7-146">IF Helper.Value == X THEN...</span></span>  
  
 <span data-ttu-id="b3fd7-147">もう 1 つの解決方法として考えられるのは、次のようなルールを作成することです。</span><span class="sxs-lookup"><span data-stu-id="b3fd7-147">Another possible solution is to create a rule like the following:</span></span>  
  
 <span data-ttu-id="b3fd7-148">IF Product/Quantity Exist Then CheckQuantityAndDoSomething(Product/Quantity)</span><span class="sxs-lookup"><span data-stu-id="b3fd7-148">IF Product/Quantity Exist Then CheckQuantityAndDoSomething(Product/Quantity)</span></span>  
  
 <span data-ttu-id="b3fd7-149">この例では、CheckQuantityAndDoSomething 関数がパラメーター値をチェックし、条件が満たされていれば処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="b3fd7-149">In the preceding example, the CheckQuantityAndDoSomething function will check the parameter value and execute if the condition is met.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b3fd7-150">XPath を変更する代わりに、**フィールド**が、エラーをキャッチする XML ファクトのプロパティが方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b3fd7-150">Alternatively, you can modify the XPath **Field** property for the XML fact to catch any errors, but it is not the recommended approach.</span></span>