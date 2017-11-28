---
title: "Siebel の SELECT ステートメントの構文 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Data Provider for Siebel, searching and sorting data using
- Data Provider for Siebel, SELECT statement
- SELECT statement, syntax for
ms.assetid: 8528b115-d6f3-420d-8617-0e56dc8922bf
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2a5ee569ff05acf9a14293503ee1238e311bcf1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="syntax-for-a-select-statement-in-siebel"></a><span data-ttu-id="5b4a5-102">Siebel の SELECT ステートメントの構文</span><span class="sxs-lookup"><span data-stu-id="5b4a5-102">Syntax for a SELECT Statement in Siebel</span></span>
<span data-ttu-id="5b4a5-103">使用して、 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]、ADO.NET クライアントは Siebel 検索の有効な定義を表す WHERE 句を指定することで Siebel ビジネス コンポーネントで SELECT クエリを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="5b4a5-103">Using the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], ADO.NET clients can perform a SELECT query on Siebel business components by specifying a WHERE clause that represents a valid Siebel search specification.</span></span> <span data-ttu-id="5b4a5-104">SELECT ステートメントの構文です。</span><span class="sxs-lookup"><span data-stu-id="5b4a5-104">The syntax for the SELECT statement is:</span></span>  
  
```  
SELECT  
\<column name 1> AS \<column alias 1>,  
\<column name 2> AS \<column alias 2>,  
…  
FROM  
<Business object name>.<Business component name> AS <table alias>  
WHERE  
<filter condition>  
OPTION  
'ViewMode <value>'  
```  
  
 <span data-ttu-id="5b4a5-105">上記の構文では、ViewMode オプションに対応 Siebel システムの表示モードは、クエリに一致するレコードのセットを制限するフィルター メカニズムです。</span><span class="sxs-lookup"><span data-stu-id="5b4a5-105">In the above syntax, the ViewMode option corresponds to the Siebel system View Modes, which is a filtering mechanism to restrict the set of records that match the query.</span></span> <span data-ttu-id="5b4a5-106">値の許可されたセットは、Siebel のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b4a5-106">For the allowed set of values, see the Siebel documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5b4a5-107">WHERE 句内のフィールド名に特殊文字や空白を含んでいる場合は、常に角かっこ内のフィールド名を囲むを確認します。</span><span class="sxs-lookup"><span data-stu-id="5b4a5-107">If the field names in the WHERE clause contain special characters or empty spaces, make sure you always enclose the field names within square brackets.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5b4a5-108">特殊文字を含むエイリアス名を含む SELECT クエリでは、角かっこ内のエイリアス名を含めるを確認します。</span><span class="sxs-lookup"><span data-stu-id="5b4a5-108">In SELECT queries containing alias names with special characters, make sure you include the alias names within square brackets.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5b4a5-109">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]をサポートしている別名テーブルでの名前、WHERE 句ではなく、SELECT 句でします。</span><span class="sxs-lookup"><span data-stu-id="5b4a5-109">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] supports alias names for tables in the SELECT clause but not in the WHERE clause.</span></span>  
  
## <a name="searching-and-sorting-data-using-the-data-provider-for-siebel"></a><span data-ttu-id="5b4a5-110">Siebel のデータ プロバイダーを使用してデータの並べ替えと検索</span><span class="sxs-lookup"><span data-stu-id="5b4a5-110">Searching and Sorting Data Using the Data Provider for Siebel</span></span>  
 <span data-ttu-id="5b4a5-111">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] Siebel システムでサポートされている検索仕様に基づいて SQL ステートメントでフィルター条件をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5b4a5-111">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] supports a filter condition in SQL statements based on the search specifications supported by the Siebel system.</span></span>  
  
 <span data-ttu-id="5b4a5-112">検索条件の規則は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5b4a5-112">The rules for the search specification are:</span></span>  
  
-   <span data-ttu-id="5b4a5-113">標準的な比較演算子は、定数、フィールドまたは別のフィールドに 1 つのフィールドを比較するために使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b4a5-113">Standard comparison operators must be used to compare a field to a constant, or one field to another field.</span></span> <span data-ttu-id="5b4a5-114">これらを含める =、! =、>、 \<、> =、および < = です。</span><span class="sxs-lookup"><span data-stu-id="5b4a5-114">These include =, !=, >, \<, >=, and <=.</span></span>  
  
    ```  
    Example: [Revenue] > 5000  
    ```  
  
-   <span data-ttu-id="5b4a5-115">文字列定数は、二重引用符で囲む必要があり、文字列の値は大文字小文字を区別する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b4a5-115">String constants must be enclosed in double quotation marks, and the string values must be case-sensitive.</span></span>  
  
    ```  
    Example: [Type] != "COST LIST"  
    ```  
  
-   <span data-ttu-id="5b4a5-116">論理演算子 AND、OR、および否定または式を結合に使用する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="5b4a5-116">The logical operators AND, OR, and NOT must be used to negate or combine expressions.</span></span> <span data-ttu-id="5b4a5-117">これらの演算子では、大文字小文字の区別が無視されます。たとえば、「と」と同じでは、"AND"です。</span><span class="sxs-lookup"><span data-stu-id="5b4a5-117">Case sensitivity is ignored in these operators; for example, “and” is the same as “AND”.</span></span>  
  
    ```  
    Example: [Competitor] IS NOT NULL and [Competitor] != "N"  
    ```  
  
-   <span data-ttu-id="5b4a5-118">検索の定義でフィールド名は、角かっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b4a5-118">A field name in a search specification must be enclosed in square brackets.</span></span>  
  
    ```  
    Example: [Conflict Id] = 0  
    ```  
  
-   <span data-ttu-id="5b4a5-119">フィールドが、定数と比較して比較式のテキスト文字列を作成する LIKE 演算子を使用するまたは、別のフィールドといくつかの先頭の文字のみで一致するフィールドが必要です。</span><span class="sxs-lookup"><span data-stu-id="5b4a5-119">The LIKE operator may be used to create text string comparison expressions in which a field is compared to a constant, or a field to another field and a match on only the first several characters is required.</span></span> <span data-ttu-id="5b4a5-120">ワイルドカード文字"*「と」?"</span><span class="sxs-lookup"><span data-stu-id="5b4a5-120">The wildcard characters “*” and “?”</span></span> <span data-ttu-id="5b4a5-121">それぞれの文字、および単一の文字の任意の数を示すために使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b4a5-121">must be used to indicate any number of characters, and a single character, respectively.</span></span>  
  
-   <span data-ttu-id="5b4a5-122">ADO.NET クライアントには、元の Siebel ビジネス オブジェクト、ビジネス コンポーネント、およびビジネス コンポーネントのフィールド名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5b4a5-122">ADO.NET clients can specify original Siebel business objects, business components, and business component field names.</span></span> <span data-ttu-id="5b4a5-123">任意の特殊文字または空白文字が含まれる場合、これらの名前を角かっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b4a5-123">These names must be enclosed in square brackets if they contain any special characters or white space.</span></span> <span data-ttu-id="5b4a5-124">サポートされているクエリの例は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5b4a5-124">Examples of queries that are supported are:</span></span>  
  
    ```  
    SELECT [Name], [Postal Code] FROM Account.Account where [Postal Code] != '11065'  
    SELECT [Name], [Postal Code], Id From Account.Account where [Postal Code] != '60626' Order BY Id ASC, Name DESC  
    SELECT * FROM [Admin Price List].[Price Book Items]  
    ```  
  
 <span data-ttu-id="5b4a5-125">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] Siebel でサポートされている並べ替えの指定に基づいて SQL ステートメントの仕様の並べ替えをサポートします。</span><span class="sxs-lookup"><span data-stu-id="5b4a5-125">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] supports sort specifications in SQL statements based on the sort specification supported by Siebel.</span></span> <span data-ttu-id="5b4a5-126">並べ替えの指定の規則は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5b4a5-126">The rules for the sort specification are:</span></span>  
  
-   <span data-ttu-id="5b4a5-127">仕様では、並べ替え以外のフィールド名を区切るコンマを使用します。たとえば、名前、場所</span><span class="sxs-lookup"><span data-stu-id="5b4a5-127">Use commas to separate field names in a sort specification; for instance, Name, Location</span></span>  
  
-   <span data-ttu-id="5b4a5-128">リスト内のフィールドを降順に並べ替えることを示す、「開始日 (DESC) です」のように、フィールド名の後 (DESC) を含める</span><span class="sxs-lookup"><span data-stu-id="5b4a5-128">To indicate that a field in the list sorts in descending order, include (DESC) after the field name, as in “Start Date (DESC).”</span></span> <span data-ttu-id="5b4a5-129">並べ替え順序が指定されていない場合は、昇順を使用します。</span><span class="sxs-lookup"><span data-stu-id="5b4a5-129">If no sort order is specified, ascending order is used.</span></span> <span data-ttu-id="5b4a5-130">昇順を明示的に指定するには、キーワード (ASC) を使用します。</span><span class="sxs-lookup"><span data-stu-id="5b4a5-130">To explicitly specify ascending order, use the keyword (ASC).</span></span>  
  
-   <span data-ttu-id="5b4a5-131">並べ替え式の仕様は 255 文字である必要があります以下です。</span><span class="sxs-lookup"><span data-stu-id="5b4a5-131">The sort specification expression must be 255 characters or less.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b4a5-132">参照</span><span class="sxs-lookup"><span data-stu-id="5b4a5-132">See Also</span></span>  
 [<span data-ttu-id="5b4a5-133">Siebel eBusiness Applications の .NET Framework データ プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="5b4a5-133">Use the .NET Framework Data Provider for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)