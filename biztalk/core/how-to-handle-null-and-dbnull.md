---
title: Null および DBNull を処理する方法 |Microsoft Docs
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
ms.openlocfilehash: ea5635e289ce1d510e7e2701c79eeb3c9543b54e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385010"
---
# <a name="how-to-handle-null-and-dbnull"></a><span data-ttu-id="df4fb-102">Null および DBNull を処理する方法</span><span class="sxs-lookup"><span data-stu-id="df4fb-102">How to Handle Null and DBNull</span></span>
<span data-ttu-id="df4fb-103">このトピックでは、さまざまな種類に関連付けられている null 値を処理するときに予期される動作について説明し、null または特定のフィールドまたはメンバーの存在をチェックするためのオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="df4fb-103">This topic describes the expected behaviors when dealing with null values associated with different types, and discusses options for checking null or existence of a particular field or member.</span></span>  
  
## <a name="xml"></a><span data-ttu-id="df4fb-104">XML</span><span class="sxs-lookup"><span data-stu-id="df4fb-104">XML</span></span>  
 <span data-ttu-id="df4fb-105">次の XML に適用されます。</span><span class="sxs-lookup"><span data-stu-id="df4fb-105">The following applies to XML:</span></span>  
  
-   <span data-ttu-id="df4fb-106">XML 値は、null としてのドキュメントからは返されません。</span><span class="sxs-lookup"><span data-stu-id="df4fb-106">An XML value will never be returned from a document as null.</span></span> <span data-ttu-id="df4fb-107">空の文字列または「存在しません」エラーのいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="df4fb-107">It is either an empty string or a "does not exist" error.</span></span> <span data-ttu-id="df4fb-108">空の文字列がある場合に、エラーが発生する、特定の種類の変換などのルールを作成するときに、整数型として指定されたフィールド。</span><span class="sxs-lookup"><span data-stu-id="df4fb-108">When it is an empty string, an error may occur for conversion of certain types, for example, fields specified as an integer type when building rules.</span></span>  
  
-   <span data-ttu-id="df4fb-109">ビジネス ルール作成ツールでは許可するフィールドを null に設定したりするためのフィールドの型を設定しない**オブジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="df4fb-109">The Business Rule Composer does not allow you to set a field to null or to set the type of a field to **object**.</span></span>  
  
-   <span data-ttu-id="df4fb-110">オブジェクト モデルを使用種類を設定することができます**オブジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="df4fb-110">Through the object model you can set the type to **Object**.</span></span> <span data-ttu-id="df4fb-111">この場合、返される値は、XPath の評価結果の種類: **float**、**ブール**、または**文字列**XPath 式に応じて、します。</span><span class="sxs-lookup"><span data-stu-id="df4fb-111">In this case, the value returned is the type to which the XPath evaluates— **float**, **boolean**, or **string**, depending on the XPath expression.</span></span>  
  
## <a name="net-classes"></a><span data-ttu-id="df4fb-112">.NET クラス</span><span class="sxs-lookup"><span data-stu-id="df4fb-112">.NET classes</span></span>  
 <span data-ttu-id="df4fb-113">次の .NET クラスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="df4fb-113">The following applies to .NET classes:</span></span>  
  
-   <span data-ttu-id="df4fb-114">戻り値の型でない場合は、null と比較することはできません、**オブジェクト**型。</span><span class="sxs-lookup"><span data-stu-id="df4fb-114">You are not allowed to compare to null if your return type is not an **object** type.</span></span>  
  
-   <span data-ttu-id="df4fb-115">Null 値の型ではないパラメーターをパラメーターとして渡すことができますが、メンバーの実装によって、ランタイム エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="df4fb-115">You can pass null as a parameter for parameters that are not value types, but you may get a runtime error, depending on the implementation of the member.</span></span>  
  
-   <span data-ttu-id="df4fb-116">派生した型のフィールドを設定する**オブジェクト**を null にします。</span><span class="sxs-lookup"><span data-stu-id="df4fb-116">You can set fields of types derived from **Object** to null.</span></span>  
  
## <a name="data-connection"></a><span data-ttu-id="df4fb-117">データ接続</span><span class="sxs-lookup"><span data-stu-id="df4fb-117">Data connection</span></span>  
 <span data-ttu-id="df4fb-118">次のデータ接続に適用されます。</span><span class="sxs-lookup"><span data-stu-id="df4fb-118">The following applies to a data connection:</span></span>  
  
-   <span data-ttu-id="df4fb-119">Null にデータベース テーブルの列を比較するには、テーブル列の null 値を使用して、列の型でない場合**テキスト**、 **ntext**、および**イメージ**します。</span><span class="sxs-lookup"><span data-stu-id="df4fb-119">You can compare any database table column to null, if the table allows nulls for the column and the column type is not **text**, **ntext**, and **image**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="df4fb-120">ビジネス ルール作成ツールでは、型の列を使用できます。**テキスト**と**ntext**、条件にします。</span><span class="sxs-lookup"><span data-stu-id="df4fb-120">The Business Rule Composer allows you to use columns of type, **text** and **ntext**, in conditions.</span></span> <span data-ttu-id="df4fb-121">ただし、ポリシーを実行するときに、「text、ntext、および image データ型と比較することはできませんまたは以外の場合、IS NULL を使用して、並べ替え、または LIKE 演算子」と表示、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="df4fb-121">However, when you execute the policy, you will receive an error message, which says, "The text, ntext, and image data types cannot be compared or sorted, except when using IS NULL or LIKE operator".</span></span>  
  
-   <span data-ttu-id="df4fb-122">データベース テーブルの列は、テーブル列の null 値を許可する場合を null に設定できます。</span><span class="sxs-lookup"><span data-stu-id="df4fb-122">You can set any database table column to null, if the table allows nulls for the column.</span></span>  
  
-   <span data-ttu-id="df4fb-123">ビジネス ルール作成ツールが自動的にメンバーの種類を設定するバインディングで**オブジェクト**比較またはに設定する場合は、値型の場合は null 以外、リセットまたは引数を置換する場合、元の型に変更します。</span><span class="sxs-lookup"><span data-stu-id="df4fb-123">The Business Rule Composer automatically sets the member type in the binding to **object**, if you compare or set to null for a value type; it changes back to the original type if you reset or replace the argument.</span></span>  
  
-   <span data-ttu-id="df4fb-124">文字列型の場合に型を変更**オブジェクト**かどうか、null に設定が、null と比較した場合、文字列として残ります。</span><span class="sxs-lookup"><span data-stu-id="df4fb-124">For a string type, it changes the type to **object** if you set it to null, but leaves it as a string if you compare against null.</span></span>  
  
-   <span data-ttu-id="df4fb-125">比較またはに設定することはできません**DBNull.Value** 、ビジネス ルール作成ツールから、列の型には変更されないため、**オブジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="df4fb-125">You cannot compare or set to **DBNull.Value** from the Business Rule Composer, because it will not change the column type to **object**.</span></span>  
  
-   <span data-ttu-id="df4fb-126">エンジンは、null を比較する際に DBNull 値を変換し、null をデータベースへの挿入の際に DBNull 値に変換されます。</span><span class="sxs-lookup"><span data-stu-id="df4fb-126">The engine will convert a DBNull value to null for comparison and will convert null to a DBNull value for insertion into the database.</span></span>  
  
-   <span data-ttu-id="df4fb-127">テストでは、(これは SQL Server の動作です)、null 値を無視します。</span><span class="sxs-lookup"><span data-stu-id="df4fb-127">Tests will ignore null values (this is the way SQL Server works).</span></span> <span data-ttu-id="df4fb-128">例では、ルールがある場合、"場合 db.column > 5 THEN。"、db.column に値を持つ行のみがテストされます-null 行はスキップされます。</span><span class="sxs-lookup"><span data-stu-id="df4fb-128">For example, if you have the rule "IF db.column > 5 THEN .", only the rows that have a value in db.column are tested—rows with null are skipped.</span></span>  
  
## <a name="typeddatatable-and-typeddatarow"></a><span data-ttu-id="df4fb-129">TypedDataTable および TypedDataRow</span><span class="sxs-lookup"><span data-stu-id="df4fb-129">TypedDataTable and TypedDataRow</span></span>  
 <span data-ttu-id="df4fb-130">次は TypedDataTable および TypedDataRow に適用されます。</span><span class="sxs-lookup"><span data-stu-id="df4fb-130">The following applies to TypedDataTable and TypedDataRow:</span></span>  
  
-   <span data-ttu-id="df4fb-131">ビジネス ルール作成ツールの変更、フィールドの種類を**オブジェクト**と同じ方法で**DataConnection**秒。</span><span class="sxs-lookup"><span data-stu-id="df4fb-131">The Business Rule Composer changes the field type to **object** in the same manner as with **DataConnection**s.</span></span>  
  
-   <span data-ttu-id="df4fb-132">Null を比較する場合を除き、null 値は、テストは失敗します。</span><span class="sxs-lookup"><span data-stu-id="df4fb-132">Tests will fail for null values, unless you are comparing to null.</span></span> <span data-ttu-id="df4fb-133">などがありますエラー ルール"IF db.column > 5 THEN"アサートされた行の値が null の場合、します。</span><span class="sxs-lookup"><span data-stu-id="df4fb-133">For example, there will be an error in the rule "IF db.column > 5 THEN ", if any row asserted has a null value.</span></span>  
  
     <span data-ttu-id="df4fb-134">並列での条件が評価されるため、テストのように注意してください。"IF db.column! = NULL AND db.column > 5 THEN"は、両方のテストは 1 行ごとに評価される可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="df4fb-134">Note that because conditions are evaluated in parallel, tests like "IF db.column != NULL AND db.column > 5 THEN  " will still fail, because both tests are potentially evaluated on every row.</span></span>  
  
## <a name="checking-for-null-or-existence"></a><span data-ttu-id="df4fb-135">Null または存在の有無の確認</span><span class="sxs-lookup"><span data-stu-id="df4fb-135">Checking for null or existence</span></span>  
 <span data-ttu-id="df4fb-136">ビジネス ルールを記述する場合は、自然にその値を比較する前に、フィールドの存在を確認します。</span><span class="sxs-lookup"><span data-stu-id="df4fb-136">When writing business rules, it is natural to check for the existence of a field before comparing its value.</span></span> <span data-ttu-id="df4fb-137">ただし、フィールドが null か、存在しない場合、値と比較するエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="df4fb-137">However, if the field is null or does not exist, comparing the value will cause an error.</span></span> <span data-ttu-id="df4fb-138">次のルールがあると仮定します。</span><span class="sxs-lookup"><span data-stu-id="df4fb-138">Assume you have the following rule:</span></span>  
  
 <span data-ttu-id="df4fb-139">Product/quantity AND Product/quantity が存在する場合 > 1</span><span class="sxs-lookup"><span data-stu-id="df4fb-139">IF Product/Quantity Exists AND Product/Quantity > 1</span></span>  
  
 <span data-ttu-id="df4fb-140">Product/quantity が存在しない場合、ルールでエラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="df4fb-140">An error will be thrown in the rule if Product/Quantity does not exist.</span></span> <span data-ttu-id="df4fb-141">この問題を回避する方法の 1 つは、要素の値が存在する場合、またはそうでない場合は、別のものを返すヘルパー メソッドに親ノードを渡します。</span><span class="sxs-lookup"><span data-stu-id="df4fb-141">One of the ways to circumvent this problem is to pass a parent node to a helper method that returns the element value if it exists or something else if it does not.</span></span> <span data-ttu-id="df4fb-142">次の規則を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df4fb-142">See the following rules.</span></span>  
  
 <span data-ttu-id="df4fb-143">**ルール 1**</span><span class="sxs-lookup"><span data-stu-id="df4fb-143">**Rule 1**</span></span>  
  
 <span data-ttu-id="df4fb-144">IF EXISTS(Product/Quantity) し ASSERT(CREATEOBJECT(typeof(Helper)、Product/quantity)</span><span class="sxs-lookup"><span data-stu-id="df4fb-144">IF EXISTS(Product/Quantity) THEN ASSERT(CREATEOBJECT(typeof(Helper), Product/Quantity)</span></span>  
  
 <span data-ttu-id="df4fb-145">**Rule 2**</span><span class="sxs-lookup"><span data-stu-id="df4fb-145">**Rule 2**</span></span>  
  
 <span data-ttu-id="df4fb-146">IF Helper.Value X = = し.</span><span class="sxs-lookup"><span data-stu-id="df4fb-146">IF Helper.Value == X THEN...</span></span>  
  
 <span data-ttu-id="df4fb-147">別の解決策では、次のようなルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="df4fb-147">Another possible solution is to create a rule like the following:</span></span>  
  
 <span data-ttu-id="df4fb-148">Product/quantity が存在し CheckQuantityAndDoSomething(Product/Quantity) を場合</span><span class="sxs-lookup"><span data-stu-id="df4fb-148">IF Product/Quantity Exist Then CheckQuantityAndDoSomething(Product/Quantity)</span></span>  
  
 <span data-ttu-id="df4fb-149">前の例では、CheckQuantityAndDoSomething 関数は、パラメーターの値がチェックされ、条件が満たされた場合に実行します。</span><span class="sxs-lookup"><span data-stu-id="df4fb-149">In the preceding example, the CheckQuantityAndDoSomething function will check the parameter value and execute if the condition is met.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="df4fb-150">XPath を変更する代わりに、**フィールド**プロパティがすべてのエラーをキャッチする XML ファクトが推奨されるアプローチです。</span><span class="sxs-lookup"><span data-stu-id="df4fb-150">Alternatively, you can modify the XPath **Field** property for the XML fact to catch any errors, but it is not the recommended approach.</span></span>