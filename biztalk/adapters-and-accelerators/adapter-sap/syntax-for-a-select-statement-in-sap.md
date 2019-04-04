---
title: SAP の SELECT ステートメントの構文 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SELECT statement, syntax for
ms.assetid: 47120d74-bf41-4622-a6bc-7b8ddc959305
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92b3cb47df9b151de741b0e64f21041a60b9c90d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970715"
---
# <a name="syntax-for-a-select-statement-in-sap"></a><span data-ttu-id="a6118-102">SAP の SELECT ステートメントの構文</span><span class="sxs-lookup"><span data-stu-id="a6118-102">Syntax for a SELECT Statement in SAP</span></span>
<span data-ttu-id="a6118-103">次のセクションでは、文法仕様に対する SELECT クエリを実装するための記述、[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a6118-103">The following sections describe grammar specifications for implementing SELECT queries against the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].</span></span> <span data-ttu-id="a6118-104">いくつかの場合、構文が少し異なる基本の TRANSACT-SQL 構文に注意してください。</span><span class="sxs-lookup"><span data-stu-id="a6118-104">Notice that in several cases, the syntax is somewhat different from the base Transact-SQL syntax.</span></span>  
  
```  
SELECT {TOP <const> }[0,1] <select_list>  {INTO FILE [‘file_name’ | “file_name”]   
{DELIMITED}[0,1]}[0,1]  FROM table_name  {AS alias_name }[0,1]    
{INNER JOIN table_name {AS alias_name}[0,1] ON  <Join_Condition>}[0,1]  
{ WHERE <predicate> } [0,1] {;}[0,1]   
[OPTION 'no_conversion' | 'batchsize <size>' | 'disabledatavalidation'  
```  
  
 <span data-ttu-id="a6118-105">各要素の説明は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a6118-105">Where:</span></span>  
  
- <span data-ttu-id="a6118-106">**<select_list>** = `[ {table_name.}[0,1]column_name { AS alias_name } [0,1] } [ 1, …n ]`</span><span class="sxs-lookup"><span data-stu-id="a6118-106">**<select_list>** = `[ {table_name.}[0,1]column_name { AS alias_name } [0,1] } [ 1, …n ]`</span></span>  
  
- <span data-ttu-id="a6118-107">**<Join_Condition>** = `[Alias_name.|table_name.]column_name <expr> [Alias_name.|table_name.]column_name`</span><span class="sxs-lookup"><span data-stu-id="a6118-107">**<Join_Condition>** = `[Alias_name.|table_name.]column_name <expr> [Alias_name.|table_name.]column_name`</span></span>  
  
- <span data-ttu-id="a6118-108">**\<predicate\>** = `[ predicate [AND|OR] predicate [between|not between] predicate |  NOT predicate |  ‘(‘ predicate ‘)’ | condition ]`</span><span class="sxs-lookup"><span data-stu-id="a6118-108">**\<predicate\>** = `[ predicate [AND|OR] predicate [between|not between] predicate |  NOT predicate |  ‘(‘ predicate ‘)’ | condition ]`</span></span>  
  
  <span data-ttu-id="a6118-109">サポートされている条件と式は。</span><span class="sxs-lookup"><span data-stu-id="a6118-109">The supported conditions and expressions are:</span></span>  
  
- <span data-ttu-id="a6118-110">**\<条件\>** = `[ expr | expr [NOT | ] BETWEEN const AND const | expr [NOT | ] LIKE const ]`</span><span class="sxs-lookup"><span data-stu-id="a6118-110">**\<condition\>** = `[ expr | expr [NOT | ] BETWEEN const AND const | expr [NOT | ] LIKE const ]`</span></span>  
  
- <span data-ttu-id="a6118-111">**\<expr\>** = `[ const | column_name [= | ! = | > | > = | ! > | < | < = | ! < ] const | column_name | - const  | const | column_name ]`</span><span class="sxs-lookup"><span data-stu-id="a6118-111">**\<expr\>** = `[ const | column_name [= | ! = | > | > = | ! > | < | < = | ! < ] const | column_name | - const  | const | column_name ]`</span></span>  
  
  <span data-ttu-id="a6118-112">場所 **\<const\>** = `integer | real | string | ? | NULL | xml_element`します。</span><span class="sxs-lookup"><span data-stu-id="a6118-112">Where **\<const\>** = `integer | real | string | ? | NULL | xml_element`.</span></span>  
  
  <span data-ttu-id="a6118-113">**オプションのキーワードの値**</span><span class="sxs-lookup"><span data-stu-id="a6118-113">**Values for the OPTION Keyword**</span></span>  
  
  <span data-ttu-id="a6118-114">としてオプションを指定できます`OPTION '<option>'`ここで、 `<option> = 'no_conversion' | 'batchsize <size>' | 'disabledatavalidation'`</span><span class="sxs-lookup"><span data-stu-id="a6118-114">You can specify the options as `OPTION '<option>'`, where `<option> = 'no_conversion' | 'batchsize <size>' | 'disabledatavalidation'`</span></span>  
  
- <span data-ttu-id="a6118-115">**No_conversion**オプション。</span><span class="sxs-lookup"><span data-stu-id="a6118-115">The **no_conversion** option:</span></span>  
  
  -   <span data-ttu-id="a6118-116">場合、 **no_conversion**オプションを使用し、同等の .NET 型を使用して、テーブル内のフィールドが公開されます。</span><span class="sxs-lookup"><span data-stu-id="a6118-116">If the **no_conversion** option is used then the fields in the table are exposed using the equivalent .NET types.</span></span> <span data-ttu-id="a6118-117">SAP のデータ型の .NET 相当するものについては、[SAP データ型の基本的な](../../adapters-and-accelerators/adapter-sap/basic-sap-data-types.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6118-117">For information about the .NET equivalent of the SAP data types, see [Basic SAP Data Types](../../adapters-and-accelerators/adapter-sap/basic-sap-data-types.md).</span></span>  
  
  -   <span data-ttu-id="a6118-118">場合、 **no_conversion**フィールドに、変換がないかどうかは、定義された終了オプションは使用されませんし、同等の .NET 型を使用してテーブル内のこれらのフィールドが公開されます。</span><span class="sxs-lookup"><span data-stu-id="a6118-118">If the **no_conversion** option is not used, and if a field does not have a conversion exit defined then those fields in the table are exposed using the equivalent .NET types.</span></span> <span data-ttu-id="a6118-119">SAP のデータ型の .NET 相当するものについては、[SAP データ型の基本的な](../../adapters-and-accelerators/adapter-sap/basic-sap-data-types.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6118-119">For information about the .NET equivalent of the SAP data types, see [Basic SAP Data Types](../../adapters-and-accelerators/adapter-sap/basic-sap-data-types.md).</span></span>  
  
  -   <span data-ttu-id="a6118-120">ときに、 **no_conversion**オプションを使用しないと変換されていないかどうかは、定義されている終了し、テーブル内のこれらのフィールドが .NET 文字列として公開されます。</span><span class="sxs-lookup"><span data-stu-id="a6118-120">When the **no_conversion** option is not used, and if a field has a conversion exit defined then those fields in the table are exposed as .NET String.</span></span>  
  
- <span data-ttu-id="a6118-121">設定すると**batchsize\<サイズ\>**、SELECT ステートメントの実行と複数の呼び出しを SAP システムおよび各呼び出しでのみ\<サイズ\>レコードの数取得されます。</span><span class="sxs-lookup"><span data-stu-id="a6118-121">When set to **batchsize \<size\>**, the execution of the SELECT statement causes multiple calls to be made to the SAP system, and in each call, only \<size\> number of records are retrieved.</span></span> <span data-ttu-id="a6118-122">たとえば、指定した ' batchsize 100'、SELECT クエリは、SAP システムへの各呼び出しでのみ 100 個のレコードを取得します。</span><span class="sxs-lookup"><span data-stu-id="a6118-122">For example, if you specify 'batchsize 100', the SELECT query retrieves 100 records only in each call to the SAP system.</span></span> <span data-ttu-id="a6118-123">場合**batchsize\<サイズ\>** が指定されていない、10,000 の既定値は、バッチ サイズと見なされます。</span><span class="sxs-lookup"><span data-stu-id="a6118-123">If **batchsize \<size\>** is not specified, the default value of 10,000 is assumed for the batch size.</span></span> <span data-ttu-id="a6118-124">SAP システムで、コンピューターと行の数の物理メモリに基づくバッチ サイズの最適の値を指定する必要がありますに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a6118-124">Note that you should specify an optimum value for the batch size based on the physical memory of the computer and the number of rows in the SAP system.</span></span> <span data-ttu-id="a6118-125">バッチ サイズの最適の値を指定するときにエラーがメモリ不足例外があります。</span><span class="sxs-lookup"><span data-stu-id="a6118-125">Failure in specifying an optimum value for batch size may result in out of memory exceptions.</span></span>  
  
- <span data-ttu-id="a6118-126">設定すると**disabledatavalidation**、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] DATS、TIM、NUMC 列に存在する値を検証しませんが、代わりに文字列として公開されます。</span><span class="sxs-lookup"><span data-stu-id="a6118-126">When set to **disabledatavalidation**, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] does not validate the values present in the DATS, TIMS, and NUMC columns but instead exposes them as string.</span></span>  
  
   <span data-ttu-id="a6118-127">これは DATS、TIM、および NUMC 列に無効なデータを持つ SAP テーブルからデータを取得する ADO.NET クライアントが失敗するシナリオで役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a6118-127">This is useful in scenarios where ADO.NET clients fail to retrieve data from an SAP table having invalid data in DATS, TIMS, and NUMC columns.</span></span> <span data-ttu-id="a6118-128">SAP DATS、TIM、および NUMC 列に存在するデータが無効なため、データの読み取りを試みている ADO.NET クライアントは、無効なデータを解析することはできませんし、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="a6118-128">Because SAP allows invalid data to be present in DATS, TIMS, and NUMC columns, ADO.NET clients attempting to read the data will not be able to parse the invalid data and will throw an exception.</span></span> <span data-ttu-id="a6118-129">場合、 **disabledatavalidation** SELECT のクエリでは、オプションを設定してください。、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]無効なデータを解析しませんが、それらを文字列として抽出します。</span><span class="sxs-lookup"><span data-stu-id="a6118-129">If the **disabledatavalidation** option is set on the SELECT query, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] does not parse the invalid data but extracts them as strings.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a6118-130">たとえば、常に単一引用符で囲まれたオプションのキーワードの値を指定する必要があります '*disabledatavalidation*'。</span><span class="sxs-lookup"><span data-stu-id="a6118-130">You must always provide the values for the OPTION keyword within single quotes, for example, '*disabledatavalidation*'.</span></span>  
  
 <span data-ttu-id="a6118-131">たとえば、ステートメントを参照してください[SELECT ステートメントの例](../../adapters-and-accelerators/adapter-sap/examples-for-select-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="a6118-131">For example statements, see [Examples for SELECT Statement](../../adapters-and-accelerators/adapter-sap/examples-for-select-statement.md).</span></span>  
  
## <a name="predicates-syntax"></a><span data-ttu-id="a6118-132">述語の構文</span><span class="sxs-lookup"><span data-stu-id="a6118-132">Predicates Syntax</span></span>  
 <span data-ttu-id="a6118-133">次の例は、SELECT ステートメントで述語を使用するための文法を指定します。</span><span class="sxs-lookup"><span data-stu-id="a6118-133">The following specifies the grammar for using predicates in a SELECT statement:</span></span>  
  
 <span data-ttu-id="a6118-134">`Predicate`[ ] :</span><span class="sxs-lookup"><span data-stu-id="a6118-134">`Predicate`:</span></span>  
  
```  
Predicates [AND | OR] Predicates [between|not between] Predicates | [NOT] Predicates | '(' Predicates ')' | Condition  
```  
  
 <span data-ttu-id="a6118-135">`Condition`[ ] :</span><span class="sxs-lookup"><span data-stu-id="a6118-135">`Condition`:</span></span>  
  
```  
Expr | LExpr [NOT] BETWEEN RExpr AND RExpr | LExpr [NOT] LIKE Const  
```  
  
 <span data-ttu-id="a6118-136">`Expr`[ ] :</span><span class="sxs-lookup"><span data-stu-id="a6118-136">`Expr`:</span></span>  
  
```  
LExpr [=|!=|>|>=|!>|<|<=|!<] RExpr>  
```  
  
 <span data-ttu-id="a6118-137">`LExpr`[ ] :</span><span class="sxs-lookup"><span data-stu-id="a6118-137">`LExpr`:</span></span>  
  
```  
ColumnName  
```  
  
 <span data-ttu-id="a6118-138">`RExpr`[ ] :</span><span class="sxs-lookup"><span data-stu-id="a6118-138">`RExpr`:</span></span>  
  
```  
Const | PlaceHolder  
```  
  
 <span data-ttu-id="a6118-139">`ColumnName`[ ] :</span><span class="sxs-lookup"><span data-stu-id="a6118-139">`ColumnName`:</span></span>  
  
```  
Column | TableName.Column | '['Column']'  
```  
  
 <span data-ttu-id="a6118-140">`Tablename`[ ] :</span><span class="sxs-lookup"><span data-stu-id="a6118-140">`Tablename`:</span></span>  
  
```  
Table | '['Table']'  
```  
  
## <a name="considerations-when-calling-a-select-statement"></a><span data-ttu-id="a6118-141">SELECT ステートメントを呼び出す際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="a6118-141">Considerations When Calling a SELECT Statement</span></span>  
 <span data-ttu-id="a6118-142">このセクションに一覧表示されたポイントを含む SELECT ステートメントを使用する場合は、点に注意する必要があります[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a6118-142">This section lists the points that you must keep in mind when using the SELECT statement with [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  
  
- <span data-ttu-id="a6118-143">をパラメーターまたはクエリの日付/時刻値を指定する場合は、文字列として値を指定します。</span><span class="sxs-lookup"><span data-stu-id="a6118-143">When specifying date-time values in parameters or queries, provide the values as a string.</span></span> <span data-ttu-id="a6118-144">SAP の日付と時刻の形式で日付と時刻の文字列を提供します。</span><span class="sxs-lookup"><span data-stu-id="a6118-144">Provide date-time strings in the SAP date-time format.</span></span>  
  
  - <span data-ttu-id="a6118-145">`SAP date format`: YYYYMMDD</span><span class="sxs-lookup"><span data-stu-id="a6118-145">`SAP date format`: YYYYMMDD</span></span>  
  
     <span data-ttu-id="a6118-146">たとえば、2004 年の日 11 月 10 日 SAP クエリでは表現 '20041110' です。</span><span class="sxs-lookup"><span data-stu-id="a6118-146">For example, the date 2004 November 10 in a SAP query is expressed '20041110'.</span></span>  
  
     <span data-ttu-id="a6118-147">2004 年日文字列 p1 は SAPParameter p1 の 11 月 10 日のです。値 = '20041110'。</span><span class="sxs-lookup"><span data-stu-id="a6118-147">The date 2004 November 10 in a SAPParameter p1 is the string p1.Value='20041110'.</span></span>  
  
  - <span data-ttu-id="a6118-148">`SAP time format`: 時刻</span><span class="sxs-lookup"><span data-stu-id="a6118-148">`SAP time format`: HHMMSS</span></span>  
  
     <span data-ttu-id="a6118-149">たとえば、時間 10時 34分: 32 SAP クエリでは表現 '103432' です。</span><span class="sxs-lookup"><span data-stu-id="a6118-149">For example, the time 10:34:32 in a SAP query is expressed '103432'.</span></span>  
  
     <span data-ttu-id="a6118-150">時間 10時 34分: 32 SAPParameter p2 では、文字列の p2 です。値 = '103432'。</span><span class="sxs-lookup"><span data-stu-id="a6118-150">The time 10:34:32 in a SAPParameter p2 is the string p2.Value='103432'.</span></span>  
  
    <span data-ttu-id="a6118-151">SELECT ステートメントの[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]返します`DATE`フィールドの値として .NET`System.DateTime`オブジェクトを返します`TIME`フィールドの値として`System.TimeSpan`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a6118-151">For a SELECT statement, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] returns `DATE` field values as .NET `System.DateTime` objects, and returns `TIME` field values as `System.TimeSpan` objects.</span></span> <span data-ttu-id="a6118-152">場合、SAP の値`DATE`オブジェクトが許容される SQL Server の最小値より小さい (`1/1/1753`)、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]この最小値を返す`1/1/1753`します。</span><span class="sxs-lookup"><span data-stu-id="a6118-152">If the value of the SAP `DATE` object is less than the minimum allowable SQL Server value (`1/1/1753`), the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] returns this minimum value, `1/1/1753`.</span></span>  
  
- <span data-ttu-id="a6118-153">特殊文字「#」を使用する場合、SELECT クエリの TOP 句で"^"、"&"、「%」とする前に、または整数の後に、特殊文字は無視されます、エラー メッセージは生成されませんが。</span><span class="sxs-lookup"><span data-stu-id="a6118-153">In the TOP clause of a SELECT query, when using the special characters "#", "^", "&", and "%" before or after an integer, the special characters are ignored, although no error message is raised.</span></span> <span data-ttu-id="a6118-154">たとえば、次は無視されます、SELECT クエリの TOP 句で。</span><span class="sxs-lookup"><span data-stu-id="a6118-154">For example, the following are ignored in the TOP clause of a SELECT query:</span></span>  
  
   <span data-ttu-id="a6118-155">\#5, 5 ^、% 5%、または 5 (&)</span><span class="sxs-lookup"><span data-stu-id="a6118-155">\#5, 5^, %5%, or &5</span></span>  
  
   <span data-ttu-id="a6118-156">ただし、5 のように、整数の間でこれらの文字を使用して、5 ドルが、エラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="a6118-156">However, using these characters between integers, as in 5$5, does throw an error.</span></span>  
  
- <span data-ttu-id="a6118-157">テーブルのスキーマで返される列名は、すべて大文字の文字として返されます。</span><span class="sxs-lookup"><span data-stu-id="a6118-157">Column names returned in a schema for a table are returned as all uppercase characters.</span></span> <span data-ttu-id="a6118-158">クエリの結果がフィールドに設定するなど、`Last Name`列見出しを返します`LAST NAME`します。</span><span class="sxs-lookup"><span data-stu-id="a6118-158">For example, a query result set on the field `Last Name` returns the column heading `LAST NAME`.</span></span> <span data-ttu-id="a6118-159">一意性を回避するために SELECT ステートメントではすべて大文字を使用して、競合の使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a6118-159">To avoid uniqueness conflicts, using all uppercase in SELECT statements is recommended.</span></span>  
  
- <span data-ttu-id="a6118-160">SELECT クエリでは、LIKE 句で、パーセント記号、(0 個以上の文字の文字列) の「%」と、アンダー スコアのみ **「_」** (任意の 1 文字) が使用できる特殊文字。</span><span class="sxs-lookup"><span data-stu-id="a6118-160">In the LIKE clause of a SELECT query, only the percent sign, "%" (for any string of zero or more characters), and underscore, **"_"** (for any single character), are allowable special characters.</span></span> <span data-ttu-id="a6118-161">その他のすべての特殊文字は、文字列値と見なされますが、無視されます。</span><span class="sxs-lookup"><span data-stu-id="a6118-161">All other special characters are considered string values and are ignored.</span></span>  
  
- <span data-ttu-id="a6118-162">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] Z_EXTRACT_DATA_OO RFC を使用して SAP システムで SELECT クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="a6118-162">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] uses the Z_EXTRACT_DATA_OO RFC to perform SELECT queries on the SAP system.</span></span> <span data-ttu-id="a6118-163">RFC では、次の条件を満たすテーブルからデータを読み取るサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a6118-163">The RFC supports reading data from tables that satisfy the following conditions:</span></span>  
  
  - <span data-ttu-id="a6118-164">テーブルの TabClass は TRANSP、クラスター、またはプールです。</span><span class="sxs-lookup"><span data-stu-id="a6118-164">TabClass for the table is TRANSP, CUSTER, or POOL.</span></span>  
  
  - <span data-ttu-id="a6118-165">TabClass はビューと ViewClass が D または P.</span><span class="sxs-lookup"><span data-stu-id="a6118-165">TabClass is VIEW and ViewClass is either D or P.</span></span>  
  
    <span data-ttu-id="a6118-166">SELECT ステートメントでは、これらの条件を満たすテーブルからデータを読み取ることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a6118-166">Make sure the SELECT statement reads data from tables that satisfy these conditions.</span></span>  
  
- <span data-ttu-id="a6118-167">255 文字、たとえば文字列、RAWSTRING、LRAW、VARC、および LCHAR が実行できるデータ型の値は、SELECT クエリでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="a6118-167">Values of data types that can take more than 255 characters, for example STRING, RAWSTRING, LRAW, VARC, and LCHAR cannot be used in a SELECT query.</span></span> <span data-ttu-id="a6118-168">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]に付属のカスタム RFC を使用して、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]Z_EXTRACT_DATA_OO、SAP システムに対して SELECT クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="a6118-168">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] uses a custom RFC shipped with the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], Z_EXTRACT_DATA_OO, to perform SELECT queries on the SAP system.</span></span> <span data-ttu-id="a6118-169">このカスタム RFC は 255 文字以上が実行できる任意のデータ型をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="a6118-169">This custom RFC does not support any data type that can take more than 255 characters.</span></span>  
  
- <span data-ttu-id="a6118-170">列または SELECT ステートメントでサポートされているフィールドの最大数は、1000 です。</span><span class="sxs-lookup"><span data-stu-id="a6118-170">The maximum number of columns or fields that are supported in a SELECT statement is 1000.</span></span>  
  
- <span data-ttu-id="a6118-171">WHERE 句でサポートされている述語の最大数は、100 です。</span><span class="sxs-lookup"><span data-stu-id="a6118-171">The maximum number of predicates supported in a WHERE clause is 100.</span></span>  
  
- <span data-ttu-id="a6118-172">同じ SELECT ステートメントで複数回、同じフィールドを選択することはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a6118-172">Selecting the same field multiple times in the same SELECT statement is not supported.</span></span> <span data-ttu-id="a6118-173">使用されるカスタム RFC (Z_EXTRACT_DATA_OO)、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]実行する前に、ステートメントから重複するフィールドを削除します。</span><span class="sxs-lookup"><span data-stu-id="a6118-173">The custom RFC (Z_EXTRACT_DATA_OO) used by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] removes the duplicate fields from the statement before executing.</span></span> <span data-ttu-id="a6118-174">たとえば、次のステートメント。</span><span class="sxs-lookup"><span data-stu-id="a6118-174">For example, this statement:</span></span>  
  
   `SELECT BUKRS, BUKRS, BUKRS from T001`  
  
   <span data-ttu-id="a6118-175">このステートメントのように記述できるように実行します。</span><span class="sxs-lookup"><span data-stu-id="a6118-175">executes as though written like this statement:</span></span>  
  
   `SELECT BUKRS from T001`  
  
- [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] <span data-ttu-id="a6118-176">SELECT ステートメントでは、エイリアスの重複名をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="a6118-176">does not support duplicate alias names in a SELECT statement.</span></span> <span data-ttu-id="a6118-177">そのため、次の SELECT ステートメントでは、エラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="a6118-177">Therefore, the following SELECT statement throws an error:</span></span>  
  
  ```  
  SELECT KUNNR AS [MYKNA1], JMJAH AS MYKNA1 from KNA1 where KUNNR LIKE 'T-S62A08' AND JMJAH=1995  
  ```  
  
- [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] <span data-ttu-id="a6118-178">重複する列名を伴う SELECT ステートメントはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="a6118-178">does not support a SELECT statement with duplicate column names.</span></span> <span data-ttu-id="a6118-179">そのため、次の SELECT ステートメントでは、エラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="a6118-179">Therefore, the following SELECT statement throws an error:</span></span>  
  
  ```  
  SELECT KUNNR AS [MYKNA1], KUNNR AS MYKNA2 from KNA1 where MYKNA2='T-S62A08'  
  ```  
  
- <span data-ttu-id="a6118-180">SAP では、テーブルで NULL 値は格納されません。</span><span class="sxs-lookup"><span data-stu-id="a6118-180">SAP does not store NULL values in the tables.</span></span> <span data-ttu-id="a6118-181">結果として、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SELECT ステートメントで、"IS NULL"値をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="a6118-181">As a result, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] does not support an "IS NULL" value in a SELECT statement.</span></span> <span data-ttu-id="a6118-182">そのため、次の SELECT ステートメントでは、エラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="a6118-182">Therefore, the following SELECT statement throws an error:</span></span>  
  
  ```  
  SELECT NAME1, PSTLZ  from KNA1 where CITY IS NULL AND NAME1 LIKE '%MODE%'  
  ```  
  
- [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] <span data-ttu-id="a6118-183">SELECT ステートメントで ORDER BY 句をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="a6118-183">does not support an ORDER BY clause in a SELECT statement.</span></span> <span data-ttu-id="a6118-184">そのため、次の SELECT ステートメントでは、エラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="a6118-184">Therefore, the following SELECT statement throws an error:</span></span>  
  
  ```  
  SELECT NAME1  AS [MYNAME],  LAND1, KUNNR  from KNA1 where NAME1 LIKE '%MODE%'  ORDER BY NAME1  ASC  
  ```  
  
- [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] <span data-ttu-id="a6118-185">SAP テーブル内のすべてのフィールドを選択するアスタリスク (\*) を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="a6118-185">does not support specifying an asterisk (\*) to select all the fields in an SAP table.</span></span> <span data-ttu-id="a6118-186">そのため、次の SELECT ステートメントでは、エラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="a6118-186">Therefore, the following SELECT statement throws an error:</span></span>  
  
  ```  
  SELECT spfli.* from spfli inner join sflight on spfli.carrid = sflight.carrid  
  ```  
  
   <span data-ttu-id="a6118-187">すべてのフィールドを選択するには、フィールド名を個別に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6118-187">To select all the fields, you must specify the field names individually.</span></span>  
  
- <span data-ttu-id="a6118-188">SELECT ステートメントの一部として、SELECT ステートメントの出力を書き込むファイルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="a6118-188">As part of the SELECT statement, you can specify a file to which the output of the SELECT statement will be written.</span></span> <span data-ttu-id="a6118-189">ただし、出力ファイルがネットワーク共有上にある場合は、必ず、SAP サービスが実行されている SAP のサービス アカウントがネットワーク共有に対する書き込み権限。</span><span class="sxs-lookup"><span data-stu-id="a6118-189">However, if the output file is on a network share, make sure the SAP service account under which the SAP service is running has write permission to the network share.</span></span> <span data-ttu-id="a6118-190">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a6118-190">For example:</span></span>  
  
  ```  
  SELECT * into file '\\share\output.txt' from spfli inner join sflight on spfli.carrid = sflight.carrid  
  ```  
  
   <span data-ttu-id="a6118-191">前の例では、SAP のサービス アカウントに名前「共有」を使用したネットワーク共有に対する書き込み権限があります。</span><span class="sxs-lookup"><span data-stu-id="a6118-191">In the preceding example, the SAP service account must have write permission to the network share with the name "share."</span></span>  
  
- <span data-ttu-id="a6118-192">SELECT ステートメントを使用して、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SELECT クエリで引数の値のパラメーターの名前をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a6118-192">A SELECT statement using [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] supports parameter names for argument values in a SELECT query.</span></span> <span data-ttu-id="a6118-193">ただし、パラメーター名に関して規則に従うことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a6118-193">However, make sure you follow these rules with respect to parameter names:</span></span>  
  
  -   <span data-ttu-id="a6118-194">SELECT のクエリで、"\@"記号はパラメーターの名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6118-194">In the SELECT query, an "\@" symbol must precede the parameter name.</span></span>  
  
  -   <span data-ttu-id="a6118-195">"\@"シンボルは、英字 (A ~ Z または a ~ z) の後になければなりません。</span><span class="sxs-lookup"><span data-stu-id="a6118-195">The "\@" symbol must be followed by an alphabetic character (A-Z or a-z).</span></span>  
  
  -   <span data-ttu-id="a6118-196">パラメーター名は文字の英数字を含めることができます (A ~ Z、a ~ z、または 0 ~ 9) と特殊文字。</span><span class="sxs-lookup"><span data-stu-id="a6118-196">The parameter name can contain alphanumeric characters (A-Z, a-z, or 0-9) and special characters.</span></span> <span data-ttu-id="a6118-197">パラメーター名に含めることができる唯一の特殊な文字はアンダー スコア「_」と「#」のハッシュは。</span><span class="sxs-lookup"><span data-stu-id="a6118-197">The only special characters that can be included in the parameter name are underscore "_" and hash "#".</span></span>  
  
- <span data-ttu-id="a6118-198">ビューで SELECT クエリを実行すると、ベース テーブルの主キー列がビューに存在してもすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a6118-198">When you run a SELECT query on a View, make sure that all the primary key columns of the base table are also present in the View.</span></span> <span data-ttu-id="a6118-199">また、実際には、ビューの主キー列として列もマークする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6118-199">Also, as a practice, you must mark the columns as primary key columns in the View also.</span></span>  
  
   <span data-ttu-id="a6118-200">主キー列がビューに存在しない場合は、ビューの SELECT クエリが、例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="a6118-200">If the primary key columns are not present in the View, a SELECT query on the View will result in an exception.</span></span>  
  
- <span data-ttu-id="a6118-201">LRAW 型のフィールドを選択するテーブルで SELECT クエリを実行すると、対応する PREC フィールドを選択することを確認します。</span><span class="sxs-lookup"><span data-stu-id="a6118-201">When you run a SELECT query on a table to select fields of type LRAW, make sure you select the corresponding PREC field.</span></span> <span data-ttu-id="a6118-202">また、PREC フィールドは、SELECT 句で LRAW フィールドの前にすぐに表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6118-202">Also, the PREC field must appear immediately before the LRAW field in the SELECT clause.</span></span>  
  
   <span data-ttu-id="a6118-203">テーブル内のすべての LRAW フィールドには、LRAW フィールドにデータの長さを格納する対応する PREC フィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="a6118-203">Every LRAW field in a table has a corresponding PREC field that stores the length of data in the LRAW field.</span></span> <span data-ttu-id="a6118-204">PREC フィールドことがなく、SELECT 句で LRAW フィールドだけを指定すると、不適切なデータが抽出される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a6118-204">Specifying just the LRAW field in the SELECT clause without the PREC field may result in incorrect data being extracted.</span></span>  
  
- <span data-ttu-id="a6118-205">SAP システムでは、文字の比較は大文字小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="a6118-205">In an SAP system, character comparisons are case sensitive.</span></span> <span data-ttu-id="a6118-206">そのため、次の 2 つのクエリでは、異なる結果を返す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a6118-206">So, the following two queries may return different results.</span></span>  
  
  ```  
  SELECT * FROM KNA1 WHERE LAND1 LIKE 'D%'  
  ```  
  
   <span data-ttu-id="a6118-207">And</span><span class="sxs-lookup"><span data-stu-id="a6118-207">And</span></span>  
  
  ```  
  SELECT * FROM KNA1 WHERE LAND1 LIKE 'd%'  
  ```  
  
   <span data-ttu-id="a6118-208">Select クエリのフレーム化時に適切な場合を使用することを確認します。</span><span class="sxs-lookup"><span data-stu-id="a6118-208">Make sure you use the right cases when framing a select query.</span></span> <span data-ttu-id="a6118-209">また、SAP システムでは、一部の列が小文字または大文字の文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a6118-209">Also, in an SAP system, not all columns can contain lowercase or uppercase characters.</span></span> <span data-ttu-id="a6118-210">SAP GUI を使用して、テーブル内の列が小文字または大文字の文字を格納するかどうかを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="a6118-210">You can use the SAP GUI to find out whether a column in a table stores lowercase or uppercase characters.</span></span> <span data-ttu-id="a6118-211">SAP GUI の使用方法の詳細については、[を決定するかどうかを列ストア小文字または大文字の値](../../adapters-and-accelerators/adapter-sap/determining-whether-a-column-stores-lowercase-or-uppercase-values.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6118-211">For instructions on using the SAP GUI, see [Determining Whether a Column Stores Lowercase or Uppercase Values](../../adapters-and-accelerators/adapter-sap/determining-whether-a-column-stores-lowercase-or-uppercase-values.md).</span></span>  
  
- <span data-ttu-id="a6118-212">WHERE 条件はいくつかのデータ値をフィールド値の比較に対してのみサポートと*いない*とその他のテーブルのフィールド値。</span><span class="sxs-lookup"><span data-stu-id="a6118-212">The WHERE condition is supported only for comparison of a field value with some data value, and *not* with some other table field value.</span></span> <span data-ttu-id="a6118-213">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]サポートしている 1 つのテーブル SELECT クエリ、テーブルのフィールド クエリの結合条件では、同じをサポートするために、結合条件を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6118-213">Because the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] supports only one table SELECT query, table field queries in join conditions should use the join condition to support the same.</span></span>  
  
- <span data-ttu-id="a6118-214">結合条件では、テーブル名を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6118-214">A join condition must contain a table name.</span></span>  
  
   <span data-ttu-id="a6118-215">次に適切な SELECT ステートメント</span><span class="sxs-lookup"><span data-stu-id="a6118-215">The following is a correct SELECT statement</span></span>  
  
  ```  
  select A.x, B.y from A inner join B on A.m = B.n  
  ```  
  
   <span data-ttu-id="a6118-216">次に、正しくない SELECT ステートメント</span><span class="sxs-lookup"><span data-stu-id="a6118-216">The following is an incorrect SELECT statement</span></span>  
  
  ```  
  select A.x, B.y from A inner join B on m = n  
  ```  
  
- <span data-ttu-id="a6118-217">結合条件で結合条件で左テーブルは、条件の左側にあるべきし、結合条件の右側にある右側のテーブルの結合条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6118-217">In a join condition, the left table in a join condition should be on the left side of the condition, and the right table of the join condition should be specified on the right side of the join condition.</span></span>  
  
   <span data-ttu-id="a6118-218">結合条件を指定する正しい方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a6118-218">The following is the correct way of specifying a join condition:</span></span>  
  
  ```  
  select A.x, B.y from A inner join B on A.m = B.n  
  ```  
  
   <span data-ttu-id="a6118-219">結合条件を指定するを誤った方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a6118-219">The following is an incorrect way of specifying a join condition:</span></span>  
  
  ```  
  select A.x, B.y from A inner join B on B.n = A.m  
  ```  
  
- <span data-ttu-id="a6118-220">SELECT ステートメントには、JOIN 句の「等しい」の条件のみ含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a6118-220">A SELECT statement can only contain an “equal to” condition in a JOIN clause.</span></span> <span data-ttu-id="a6118-221">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a6118-221">For example:</span></span>  
  
  ```  
  select * from spfli inner join sflight on spfli.carrid = sflight.carrid  
  ```  
  
- <span data-ttu-id="a6118-222">SELECT ステートメントは、SAP システムから文字列型の列を取得できません。</span><span class="sxs-lookup"><span data-stu-id="a6118-222">A SELECT statement does not retrieve columns of type STRING from the SAP system.</span></span>  
  
- <span data-ttu-id="a6118-223">SELECT ステートメントでは、1 つの結合のみを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6118-223">A SELECT statement must contain only a single JOIN.</span></span> <span data-ttu-id="a6118-224">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a6118-224">For example:</span></span>  
  
  ```  
  select * from spfli inner join sflight on spfli.carrid = sflight.carrid  
  ```  
  
## <a name="see-also"></a><span data-ttu-id="a6118-225">参照</span><span class="sxs-lookup"><span data-stu-id="a6118-225">See Also</span></span>  
 [<span data-ttu-id="a6118-226">.NET Framework Data Provider for mySAP Business Suite について</span><span class="sxs-lookup"><span data-stu-id="a6118-226">About the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)
