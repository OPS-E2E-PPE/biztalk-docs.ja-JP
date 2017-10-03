---
title: "SAP の SELECT ステートメントの構文 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: SELECT statement, syntax for
ms.assetid: 47120d74-bf41-4622-a6bc-7b8ddc959305
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 331688f3c197fcc26f157346f2f78b74496fbd30
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="syntax-for-a-select-statement-in-sap"></a><span data-ttu-id="decde-102">SAP の SELECT ステートメントの構文</span><span class="sxs-lookup"><span data-stu-id="decde-102">Syntax for a SELECT Statement in SAP</span></span>
<span data-ttu-id="decde-103">次のセクションでは、文法仕様に対する SELECT クエリを実装するための記述、[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="decde-103">The following sections describe grammar specifications for implementing SELECT queries against the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].</span></span> <span data-ttu-id="decde-104">いくつかのケースでは、構文は、基本の TRANSACT-SQL 構文から若干異なることを確認します。</span><span class="sxs-lookup"><span data-stu-id="decde-104">Notice that in several cases, the syntax is somewhat different from the base Transact-SQL syntax.</span></span>  
  
```  
SELECT {TOP <const> }[0,1] <select_list>  {INTO FILE [‘file_name’ | “file_name”]   
{DELIMITED}[0,1]}[0,1]  FROM table_name  {AS alias_name }[0,1]    
{INNER JOIN table_name {AS alias_name}[0,1] ON  <Join_Condition>}[0,1]  
{ WHERE <predicate> } [0,1] {;}[0,1]   
[OPTION 'no_conversion' | 'batchsize <size>' | 'disabledatavalidation'  
```  
  
 <span data-ttu-id="decde-105">各要素の説明は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="decde-105">Where:</span></span>  
  
-   <span data-ttu-id="decde-106">**< select_list >** = `[ {table_name.}[0,1]column_name { AS alias_name } [0,1] } [ 1, …n ]`</span><span class="sxs-lookup"><span data-stu-id="decde-106">**<select_list>** = `[ {table_name.}[0,1]column_name { AS alias_name } [0,1] } [ 1, …n ]`</span></span>  
  
-   <span data-ttu-id="decde-107">**< Join_Condition >** = `[Alias_name.|table_name.]column_name <expr> [Alias_name.|table_name.]column_name`</span><span class="sxs-lookup"><span data-stu-id="decde-107">**<Join_Condition>** = `[Alias_name.|table_name.]column_name <expr> [Alias_name.|table_name.]column_name`</span></span>  
  
-   <span data-ttu-id="decde-108">**\<述語 >** = `[ predicate [AND|OR] predicate [between|not between] predicate |  NOT predicate |  ‘(‘ predicate ‘)’ | condition ]`</span><span class="sxs-lookup"><span data-stu-id="decde-108">**\<predicate>** = `[ predicate [AND|OR] predicate [between|not between] predicate |  NOT predicate |  ‘(‘ predicate ‘)’ | condition ]`</span></span>  
  
 <span data-ttu-id="decde-109">サポートされている条件と式は、次のようには。</span><span class="sxs-lookup"><span data-stu-id="decde-109">The supported conditions and expressions are:</span></span>  
  
-   <span data-ttu-id="decde-110">**\<条件 >** = `[ expr | expr [NOT | ] BETWEEN const AND const | expr [NOT | ] LIKE const ]`</span><span class="sxs-lookup"><span data-stu-id="decde-110">**\<condition>** = `[ expr | expr [NOT | ] BETWEEN const AND const | expr [NOT | ] LIKE const ]`</span></span>  
  
-   <span data-ttu-id="decde-111">**\<expr >** = `[ const | column_name [= | ! = | > | > = | ! > | < | < = | ! < ] const | column_name | - const  | const | column_name ]`</span><span class="sxs-lookup"><span data-stu-id="decde-111">**\<expr>** = `[ const | column_name [= | ! = | > | > = | ! > | < | < = | ! < ] const | column_name | - const  | const | column_name ]`</span></span>  
  
 <span data-ttu-id="decde-112">ここで **\<const >** = `integer | real | string | ? | NULL | xml_element`です。</span><span class="sxs-lookup"><span data-stu-id="decde-112">Where **\<const>** = `integer | real | string | ? | NULL | xml_element`.</span></span>  
  
 <span data-ttu-id="decde-113">**オプションのキーワードの値**</span><span class="sxs-lookup"><span data-stu-id="decde-113">**Values for the OPTION Keyword**</span></span>  
  
 <span data-ttu-id="decde-114">としてオプションを指定できます`OPTION '<option>'`ここで、`<option> = 'no_conversion' | 'batchsize <size>' | 'disabledatavalidation'`</span><span class="sxs-lookup"><span data-stu-id="decde-114">You can specify the options as `OPTION '<option>'`, where `<option> = 'no_conversion' | 'batchsize <size>' | 'disabledatavalidation'`</span></span>  
  
-   <span data-ttu-id="decde-115">**No_conversion**オプション。</span><span class="sxs-lookup"><span data-stu-id="decde-115">The **no_conversion** option:</span></span>  
  
    -   <span data-ttu-id="decde-116">場合、 **no_conversion**オプションを使用し、同等の .NET 型を使用して、テーブルのフィールドが公開されます。</span><span class="sxs-lookup"><span data-stu-id="decde-116">If the **no_conversion** option is used then the fields in the table are exposed using the equivalent .NET types.</span></span> <span data-ttu-id="decde-117">SAP のデータ型の同等の .NET 関数については、次を参照してください。 [SAP の基本データ型](../../adapters-and-accelerators/adapter-sap/basic-sap-data-types.md)です。</span><span class="sxs-lookup"><span data-stu-id="decde-117">For information about the .NET equivalent of the SAP data types, see [Basic SAP Data Types](../../adapters-and-accelerators/adapter-sap/basic-sap-data-types.md).</span></span>  
  
    -   <span data-ttu-id="decde-118">場合、 **no_conversion**フィールドに、変換がないかどうかは、定義されている終了オプションは使用されませんし、同等の .NET 型を使用して、テーブル内のそれらのフィールドが公開されます。</span><span class="sxs-lookup"><span data-stu-id="decde-118">If the **no_conversion** option is not used, and if a field does not have a conversion exit defined then those fields in the table are exposed using the equivalent .NET types.</span></span> <span data-ttu-id="decde-119">SAP のデータ型の同等の .NET 関数については、次を参照してください。 [SAP の基本データ型](../../adapters-and-accelerators/adapter-sap/basic-sap-data-types.md)です。</span><span class="sxs-lookup"><span data-stu-id="decde-119">For information about the .NET equivalent of the SAP data types, see [Basic SAP Data Types](../../adapters-and-accelerators/adapter-sap/basic-sap-data-types.md).</span></span>  
  
    -   <span data-ttu-id="decde-120">ときに、 **no_conversion**フィールドに、変換があるかどうかとは、定義されている終了オプションは使用されませんし、テーブル内のそれらのフィールドが .NET 文字列として公開されます。</span><span class="sxs-lookup"><span data-stu-id="decde-120">When the **no_conversion** option is not used, and if a field has a conversion exit defined then those fields in the table are exposed as .NET String.</span></span>  
  
-   <span data-ttu-id="decde-121">設定すると**batchsize\<サイズ >**、SELECT ステートメントの実行により複数の呼び出しを SAP システム的に各呼び出しでのみ行われる\<サイズ > レコードの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="decde-121">When set to **batchsize \<size>**, the execution of the SELECT statement causes multiple calls to be made to the SAP system, and in each call, only \<size> number of records are retrieved.</span></span> <span data-ttu-id="decde-122">例では、指定した場合の ' 100'、SELECT クエリ batchsize が SAP システムへの各呼び出しでのみ 100 のレコードを取得します。</span><span class="sxs-lookup"><span data-stu-id="decde-122">For example, if you specify 'batchsize 100', the SELECT query retrieves 100 records only in each call to the SAP system.</span></span> <span data-ttu-id="decde-123">場合**batchsize\<サイズ >**が指定されていない、10,000 の既定値は、バッチ サイズと見なされます。</span><span class="sxs-lookup"><span data-stu-id="decde-123">If **batchsize \<size>** is not specified, the default value of 10,000 is assumed for the batch size.</span></span> <span data-ttu-id="decde-124">SAP システムでコンピューターと行の数の物理メモリに基づくバッチ サイズの最適な値を指定する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="decde-124">Note that you should specify an optimum value for the batch size based on the physical memory of the computer and the number of rows in the SAP system.</span></span> <span data-ttu-id="decde-125">バッチ サイズの最適な値を指定するときにエラーは、メモリ不足の例外、可能性があります。</span><span class="sxs-lookup"><span data-stu-id="decde-125">Failure in specifying an optimum value for batch size may result in out of memory exceptions.</span></span>  
  
-   <span data-ttu-id="decde-126">設定すると**disabledatavalidation**、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] DATS、TIM、NUMC 列に存在する値を検証しませんが、代わりに文字列として公開します。</span><span class="sxs-lookup"><span data-stu-id="decde-126">When set to **disabledatavalidation**, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] does not validate the values present in the DATS, TIMS, and NUMC columns but instead exposes them as string.</span></span>  
  
     <span data-ttu-id="decde-127">これは、DATS、TIM、および NUMC 列に無効なデータを持つ SAP テーブルからデータを取得する ADO.NET クライアントが失敗する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="decde-127">This is useful in scenarios where ADO.NET clients fail to retrieve data from an SAP table having invalid data in DATS, TIMS, and NUMC columns.</span></span> <span data-ttu-id="decde-128">SAP DATS、TIM、および NUMC 列に存在するデータが無効なため、データの読み取りを試みている ADO.NET クライアントは、無効なデータを解析することはできませんし、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="decde-128">Because SAP allows invalid data to be present in DATS, TIMS, and NUMC columns, ADO.NET clients attempting to read the data will not be able to parse the invalid data and will throw an exception.</span></span> <span data-ttu-id="decde-129">場合、 **disabledatavalidation** 、SELECT クエリでオプションを設定、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]無効なデータを解析しませんが、それらを文字列として抽出します。</span><span class="sxs-lookup"><span data-stu-id="decde-129">If the **disabledatavalidation** option is set on the SELECT query, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] does not parse the invalid data but extracts them as strings.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="decde-130">たとえば、常に 1 つの引用符で囲まれたオプションのキーワードの値を提供する必要があります '*disabledatavalidation*' です。</span><span class="sxs-lookup"><span data-stu-id="decde-130">You must always provide the values for the OPTION keyword within single quotes, for example, '*disabledatavalidation*'.</span></span>  
  
 <span data-ttu-id="decde-131">たとえば、ステートメントを参照してください[SELECT ステートメントの例](../../adapters-and-accelerators/adapter-sap/examples-for-select-statement.md)です。</span><span class="sxs-lookup"><span data-stu-id="decde-131">For example statements, see [Examples for SELECT Statement](../../adapters-and-accelerators/adapter-sap/examples-for-select-statement.md).</span></span>  
  
## <a name="predicates-syntax"></a><span data-ttu-id="decde-132">述語の構文</span><span class="sxs-lookup"><span data-stu-id="decde-132">Predicates Syntax</span></span>  
 <span data-ttu-id="decde-133">次の例は、SELECT ステートメントの述語を使用するための文法を指定します。</span><span class="sxs-lookup"><span data-stu-id="decde-133">The following specifies the grammar for using predicates in a SELECT statement:</span></span>  
  
 <span data-ttu-id="decde-134">`Predicate`: </span><span class="sxs-lookup"><span data-stu-id="decde-134">`Predicate`:</span></span>  
  
```  
Predicates [AND | OR] Predicates [between|not between] Predicates | [NOT] Predicates | '(' Predicates ')' | Condition  
```  
  
 <span data-ttu-id="decde-135">`Condition`: </span><span class="sxs-lookup"><span data-stu-id="decde-135">`Condition`:</span></span>  
  
```  
Expr | LExpr [NOT] BETWEEN RExpr AND RExpr | LExpr [NOT] LIKE Const  
```  
  
 <span data-ttu-id="decde-136">`Expr`: </span><span class="sxs-lookup"><span data-stu-id="decde-136">`Expr`:</span></span>  
  
```  
LExpr [=|!=|>|>=|!>|<|<=|!<] RExpr>  
```  
  
 <span data-ttu-id="decde-137">`LExpr`: </span><span class="sxs-lookup"><span data-stu-id="decde-137">`LExpr`:</span></span>  
  
```  
ColumnName  
```  
  
 <span data-ttu-id="decde-138">`RExpr`: </span><span class="sxs-lookup"><span data-stu-id="decde-138">`RExpr`:</span></span>  
  
```  
Const | PlaceHolder  
```  
  
 <span data-ttu-id="decde-139">`ColumnName`: </span><span class="sxs-lookup"><span data-stu-id="decde-139">`ColumnName`:</span></span>  
  
```  
Column | TableName.Column | '['Column']'  
```  
  
 <span data-ttu-id="decde-140">`Tablename`: </span><span class="sxs-lookup"><span data-stu-id="decde-140">`Tablename`:</span></span>  
  
```  
Table | '['Table']'  
```  
  
## <a name="considerations-when-calling-a-select-statement"></a><span data-ttu-id="decde-141">SELECT ステートメントを呼び出す際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="decde-141">Considerations When Calling a SELECT Statement</span></span>  
 <span data-ttu-id="decde-142">このセクションの内容を含む SELECT ステートメントを使用する場合は、点に注意する必要がありますポイントを一覧表示[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="decde-142">This section lists the points that you must keep in mind when using the SELECT statement with [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  
  
-   <span data-ttu-id="decde-143">をパラメーターまたはクエリの日付と時刻の値を指定する場合は、文字列として値を提供します。</span><span class="sxs-lookup"><span data-stu-id="decde-143">When specifying date-time values in parameters or queries, provide the values as a string.</span></span> <span data-ttu-id="decde-144">SAP の日付と時刻の形式で日付と時刻の文字列を提供します。</span><span class="sxs-lookup"><span data-stu-id="decde-144">Provide date-time strings in the SAP date-time format.</span></span>  
  
    -   <span data-ttu-id="decde-145">`SAP date format`: YYYYMMDD 形式で指定</span><span class="sxs-lookup"><span data-stu-id="decde-145">`SAP date format`: YYYYMMDD</span></span>  
  
         <span data-ttu-id="decde-146">たとえば、2004 年の日 11 月 10 日 SAP クエリでは表された '20041110' です。</span><span class="sxs-lookup"><span data-stu-id="decde-146">For example, the date 2004 November 10 in a SAP query is expressed '20041110'.</span></span>  
  
         <span data-ttu-id="decde-147">2004 年の日文字列 p1 は SAPParameter p1 の 11 月 10 日のです。値 '20041110' を = です。</span><span class="sxs-lookup"><span data-stu-id="decde-147">The date 2004 November 10 in a SAPParameter p1 is the string p1.Value='20041110'.</span></span>  
  
    -   <span data-ttu-id="decde-148">`SAP time format`: HHMMSS 形式で指定</span><span class="sxs-lookup"><span data-stu-id="decde-148">`SAP time format`: HHMMSS</span></span>  
  
         <span data-ttu-id="decde-149">たとえば、時間 10時 34分: 32 SAP クエリでは表された '103432' です。</span><span class="sxs-lookup"><span data-stu-id="decde-149">For example, the time 10:34:32 in a SAP query is expressed '103432'.</span></span>  
  
         <span data-ttu-id="decde-150">時間 10時 34分: 32 SAPParameter p2 では、文字列 p2 です。値 '103432' を = です。</span><span class="sxs-lookup"><span data-stu-id="decde-150">The time 10:34:32 in a SAPParameter p2 is the string p2.Value='103432'.</span></span>  
  
     <span data-ttu-id="decde-151">SELECT ステートメントで、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を返します`DATE`.NET として値をフィールド`System.DateTime`オブジェクト、および返します`TIME`フィールドの値として`System.TimeSpan`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="decde-151">For a SELECT statement, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] returns `DATE` field values as .NET `System.DateTime` objects, and returns `TIME` field values as `System.TimeSpan` objects.</span></span> <span data-ttu-id="decde-152">場合、SAP の値`DATE`オブジェクトが許容される SQL Server の最小値より小さい (`1/1/1753`) では、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]この最小値を返します`1/1/1753`です。</span><span class="sxs-lookup"><span data-stu-id="decde-152">If the value of the SAP `DATE` object is less than the minimum allowable SQL Server value (`1/1/1753`), the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] returns this minimum value, `1/1/1753`.</span></span>  
  
-   <span data-ttu-id="decde-153">特殊文字「#」を使用する場合、SELECT クエリの TOP 句の"^"、"&"と「%」前に、または整数の後に、特殊文字、無視されますが、エラー メッセージは発生しません。</span><span class="sxs-lookup"><span data-stu-id="decde-153">In the TOP clause of a SELECT query, when using the special characters "#", "^", "&", and "%" before or after an integer, the special characters are ignored, although no error message is raised.</span></span> <span data-ttu-id="decde-154">たとえば、次は無視されます、SELECT クエリの TOP 句で。</span><span class="sxs-lookup"><span data-stu-id="decde-154">For example, the following are ignored in the TOP clause of a SELECT query:</span></span>  
  
     <span data-ttu-id="decde-155">\#5, 5 ^、% 5%、または 5 &</span><span class="sxs-lookup"><span data-stu-id="decde-155">\#5, 5^, %5%, or &5</span></span>  
  
     <span data-ttu-id="decde-156">ただし、5 と同様に、整数の間でこれらの文字を使用して、5 ドルはエラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="decde-156">However, using these characters between integers, as in 5$5, does throw an error.</span></span>  
  
-   <span data-ttu-id="decde-157">テーブルのスキーマで返される列名は大文字をすべてとして返されます。</span><span class="sxs-lookup"><span data-stu-id="decde-157">Column names returned in a schema for a table are returned as all uppercase characters.</span></span> <span data-ttu-id="decde-158">フィールドに、クエリ結果を設定するなど、`Last Name`列見出しを返します`LAST NAME`です。</span><span class="sxs-lookup"><span data-stu-id="decde-158">For example, a query result set on the field `Last Name` returns the column heading `LAST NAME`.</span></span> <span data-ttu-id="decde-159">一意性を避けるために SELECT ステートメントではすべて大文字を使用して、競合の使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="decde-159">To avoid uniqueness conflicts, using all uppercase in SELECT statements is recommended.</span></span>  
  
-   <span data-ttu-id="decde-160">選択クエリの LIKE 句でのみ、パーセント記号 (任意の文字列に 0 個以上の文字)、「%」、アンダー スコア、 **「_」** (任意の 1 文字) が使用できる特殊文字。</span><span class="sxs-lookup"><span data-stu-id="decde-160">In the LIKE clause of a SELECT query, only the percent sign, "%" (for any string of zero or more characters), and underscore, **"_"** (for any single character), are allowable special characters.</span></span> <span data-ttu-id="decde-161">他のすべての特殊文字は、文字列値が考慮され、無視されます。</span><span class="sxs-lookup"><span data-stu-id="decde-161">All other special characters are considered string values and are ignored.</span></span>  
  
-   <span data-ttu-id="decde-162">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] Z_EXTRACT_DATA_OO RFC を使用して SAP システムで SELECT クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="decde-162">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] uses the Z_EXTRACT_DATA_OO RFC to perform SELECT queries on the SAP system.</span></span> <span data-ttu-id="decde-163">RFC は、次の条件を満たすテーブルからデータを読み取りをサポートします。</span><span class="sxs-lookup"><span data-stu-id="decde-163">The RFC supports reading data from tables that satisfy the following conditions:</span></span>  
  
    -   <span data-ttu-id="decde-164">テーブルの TabClass は TRANSP、クラスター、またはプールです。</span><span class="sxs-lookup"><span data-stu-id="decde-164">TabClass for the table is TRANSP, CUSTER, or POOL.</span></span>  
  
    -   <span data-ttu-id="decde-165">TabClass ビューは、ViewClass D または P. のいずれか</span><span class="sxs-lookup"><span data-stu-id="decde-165">TabClass is VIEW and ViewClass is either D or P.</span></span>  
  
     <span data-ttu-id="decde-166">SELECT ステートメントでは、これらの条件を満たすテーブルからデータを読み取ることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="decde-166">Make sure the SELECT statement reads data from tables that satisfy these conditions.</span></span>  
  
-   <span data-ttu-id="decde-167">255 文字より長い、たとえば文字列、RAWSTRING、LRAW、VARC、および LCHAR が実行できるデータ型の値は、SELECT クエリでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="decde-167">Values of data types that can take more than 255 characters, for example STRING, RAWSTRING, LRAW, VARC, and LCHAR cannot be used in a SELECT query.</span></span> <span data-ttu-id="decde-168">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]付属のカスタム RFC を使用して、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]Z_EXTRACT_DATA_OO、SAP システムで SELECT クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="decde-168">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] uses a custom RFC shipped with the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], Z_EXTRACT_DATA_OO, to perform SELECT queries on the SAP system.</span></span> <span data-ttu-id="decde-169">このカスタム RFC は 255 文字以上が実行できるデータ型をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="decde-169">This custom RFC does not support any data type that can take more than 255 characters.</span></span>  
  
-   <span data-ttu-id="decde-170">SELECT ステートメントでサポートされているフィールドまたは列の最大数は 1000 です。</span><span class="sxs-lookup"><span data-stu-id="decde-170">The maximum number of columns or fields that are supported in a SELECT statement is 1000.</span></span>  
  
-   <span data-ttu-id="decde-171">WHERE 句でサポートされている述語の最大数は 100 です。</span><span class="sxs-lookup"><span data-stu-id="decde-171">The maximum number of predicates supported in a WHERE clause is 100.</span></span>  
  
-   <span data-ttu-id="decde-172">同じ SELECT ステートメントで複数回の同じフィールドを選択することはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="decde-172">Selecting the same field multiple times in the same SELECT statement is not supported.</span></span> <span data-ttu-id="decde-173">によって使用されるカスタム RFC (Z_EXTRACT_DATA_OO)、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]実行する前に、ステートメントから重複するフィールドを削除します。</span><span class="sxs-lookup"><span data-stu-id="decde-173">The custom RFC (Z_EXTRACT_DATA_OO) used by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] removes the duplicate fields from the statement before executing.</span></span> <span data-ttu-id="decde-174">たとえば、次のステートメント。</span><span class="sxs-lookup"><span data-stu-id="decde-174">For example, this statement:</span></span>  
  
     `SELECT BUKRS, BUKRS, BUKRS from T001`  
  
     <span data-ttu-id="decde-175">このステートメントと同様に書き込まれるように実行します。</span><span class="sxs-lookup"><span data-stu-id="decde-175">executes as though written like this statement:</span></span>  
  
     `SELECT BUKRS from T001`  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]<span data-ttu-id="decde-176">SELECT ステートメントでは重複するエイリアス名はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="decde-176"> does not support duplicate alias names in a SELECT statement.</span></span> <span data-ttu-id="decde-177">したがって、次の SELECT ステートメントでは、エラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="decde-177">Therefore, the following SELECT statement throws an error:</span></span>  
  
    ```  
    SELECT KUNNR AS [MYKNA1], JMJAH AS MYKNA1 from KNA1 where KUNNR LIKE 'T-S62A08' AND JMJAH=1995  
    ```  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]<span data-ttu-id="decde-178">重複する列名を含む SELECT ステートメントはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="decde-178"> does not support a SELECT statement with duplicate column names.</span></span> <span data-ttu-id="decde-179">したがって、次の SELECT ステートメントでは、エラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="decde-179">Therefore, the following SELECT statement throws an error:</span></span>  
  
    ```  
    SELECT KUNNR AS [MYKNA1], KUNNR AS MYKNA2 from KNA1 where MYKNA2='T-S62A08'  
    ```  
  
-   <span data-ttu-id="decde-180">SAP では、テーブルで NULL 値は格納されません。</span><span class="sxs-lookup"><span data-stu-id="decde-180">SAP does not store NULL values in the tables.</span></span> <span data-ttu-id="decde-181">その結果、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SELECT ステートメントで、"IS NULL"値をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="decde-181">As a result, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] does not support an "IS NULL" value in a SELECT statement.</span></span> <span data-ttu-id="decde-182">したがって、次の SELECT ステートメントでは、エラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="decde-182">Therefore, the following SELECT statement throws an error:</span></span>  
  
    ```  
    SELECT NAME1, PSTLZ  from KNA1 where CITY IS NULL AND NAME1 LIKE '%MODE%'  
    ```  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]<span data-ttu-id="decde-183">SELECT ステートメントで ORDER BY 句はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="decde-183"> does not support an ORDER BY clause in a SELECT statement.</span></span> <span data-ttu-id="decde-184">したがって、次の SELECT ステートメントでは、エラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="decde-184">Therefore, the following SELECT statement throws an error:</span></span>  
  
    ```  
    SELECT NAME1  AS [MYNAME],  LAND1, KUNNR  from KNA1 where NAME1 LIKE '%MODE%'  ORDER BY NAME1  ASC  
    ```  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]<span data-ttu-id="decde-185">SAP テーブル内のすべてのフィールドを選択するアスタリスク (*) を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="decde-185"> does not support specifying an asterisk (*) to select all the fields in an SAP table.</span></span> <span data-ttu-id="decde-186">したがって、次の SELECT ステートメントでは、エラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="decde-186">Therefore, the following SELECT statement throws an error:</span></span>  
  
    ```  
    SELECT spfli.* from spfli inner join sflight on spfli.carrid = sflight.carrid  
    ```  
  
     <span data-ttu-id="decde-187">すべてのフィールドを選択するには、個別にフィールド名を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="decde-187">To select all the fields, you must specify the field names individually.</span></span>  
  
-   <span data-ttu-id="decde-188">SELECT ステートメントの一部として、SELECT ステートメントの出力の書き込み先となるファイルを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="decde-188">As part of the SELECT statement, you can specify a file to which the output of the SELECT statement will be written.</span></span> <span data-ttu-id="decde-189">ただし、出力ファイルがネットワーク共有上にある場合は、SAP サービスが実行されている SAP サービス アカウントにネットワーク共有に対する書き込み権限があることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="decde-189">However, if the output file is on a network share, make sure the SAP service account under which the SAP service is running has write permission to the network share.</span></span> <span data-ttu-id="decde-190">例:</span><span class="sxs-lookup"><span data-stu-id="decde-190">For example:</span></span>  
  
    ```  
    SELECT * into file '\\share\output.txt' from spfli inner join sflight on spfli.carrid = sflight.carrid  
    ```  
  
     <span data-ttu-id="decde-191">前の例では、SAP のサービス アカウントが必要名「共有」とネットワーク共有への書き込みアクセス許可</span><span class="sxs-lookup"><span data-stu-id="decde-191">In the preceding example, the SAP service account must have write permission to the network share with the name "share."</span></span>  
  
-   <span data-ttu-id="decde-192">SELECT ステートメントを使用して、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]選択クエリで引数の値のパラメーターの名前をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="decde-192">A SELECT statement using [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] supports parameter names for argument values in a SELECT query.</span></span> <span data-ttu-id="decde-193">ただし、パラメーター名に関してこれらの規則に従うことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="decde-193">However, make sure you follow these rules with respect to parameter names:</span></span>  
  
    -   <span data-ttu-id="decde-194">SELECT クエリで、"@"記号はパラメーターの名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="decde-194">In the SELECT query, an "@" symbol must precede the parameter name.</span></span>  
  
    -   <span data-ttu-id="decde-195">"@"記号は、英字 (A ~ Z または a ~ z) の後になければなりません。</span><span class="sxs-lookup"><span data-stu-id="decde-195">The "@" symbol must be followed by an alphabetic character (A-Z or a-z).</span></span>  
  
    -   <span data-ttu-id="decde-196">パラメーター名は英数字文字を含めることができます (A ~ Z、a ~ z、または 0 ~ 9) と特殊文字。</span><span class="sxs-lookup"><span data-stu-id="decde-196">The parameter name can contain alphanumeric characters (A-Z, a-z, or 0-9) and special characters.</span></span> <span data-ttu-id="decde-197">パラメーター名に含めることができる唯一の特殊な文字は、アンダー スコア「_」と「#」のハッシュです。</span><span class="sxs-lookup"><span data-stu-id="decde-197">The only special characters that can be included in the parameter name are underscore "_" and hash "#".</span></span>  
  
-   <span data-ttu-id="decde-198">ビューで SELECT クエリを実行すると、ベース テーブルの主キー列がビューに存在してもすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="decde-198">When you run a SELECT query on a View, make sure that all the primary key columns of the base table are also present in the View.</span></span> <span data-ttu-id="decde-199">プラクティスとして、また、ビューの主キー列として列もマークする必要があります。</span><span class="sxs-lookup"><span data-stu-id="decde-199">Also, as a practice, you must mark the columns as primary key columns in the View also.</span></span>  
  
     <span data-ttu-id="decde-200">主キー列がビューに存在しない場合、ビューで SELECT クエリ、例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="decde-200">If the primary key columns are not present in the View, a SELECT query on the View will result in an exception.</span></span>  
  
-   <span data-ttu-id="decde-201">LRAW の種類のフィールドを選択するテーブルに対する SELECT クエリを実行するときに対応する PREC フィールドを選択することを確認します。</span><span class="sxs-lookup"><span data-stu-id="decde-201">When you run a SELECT query on a table to select fields of type LRAW, make sure you select the corresponding PREC field.</span></span> <span data-ttu-id="decde-202">また、SELECT 句で LRAW フィールドの直前 PREC フィールドが表示されます必要があります。</span><span class="sxs-lookup"><span data-stu-id="decde-202">Also, the PREC field must appear immediately before the LRAW field in the SELECT clause.</span></span>  
  
     <span data-ttu-id="decde-203">テーブル内の各 LRAW フィールドには、LRAW フィールドにデータの長さを格納する対応する PREC フィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="decde-203">Every LRAW field in a table has a corresponding PREC field that stores the length of data in the LRAW field.</span></span> <span data-ttu-id="decde-204">SELECT 句なしで PREC フィールドで LRAW フィールドだけを指定すると、不適切なデータが抽出されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="decde-204">Specifying just the LRAW field in the SELECT clause without the PREC field may result in incorrect data being extracted.</span></span>  
  
-   <span data-ttu-id="decde-205">SAP システムで文字の比較、大文字小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="decde-205">In an SAP system, character comparisons are case sensitive.</span></span> <span data-ttu-id="decde-206">そのため、次の 2 つのクエリでは、異なる結果を返すことがあります。</span><span class="sxs-lookup"><span data-stu-id="decde-206">So, the following two queries may return different results.</span></span>  
  
    ```  
    SELECT * FROM KNA1 WHERE LAND1 LIKE 'D%'  
    ```  
  
     <span data-ttu-id="decde-207">And</span><span class="sxs-lookup"><span data-stu-id="decde-207">And</span></span>  
  
    ```  
    SELECT * FROM KNA1 WHERE LAND1 LIKE 'd%'  
    ```  
  
     <span data-ttu-id="decde-208">Select クエリのフレーム化時に、右側のケースを使用することを確認します。</span><span class="sxs-lookup"><span data-stu-id="decde-208">Make sure you use the right cases when framing a select query.</span></span> <span data-ttu-id="decde-209">また、SAP システムでは、必ずしもすべての列が小文字または大文字の文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="decde-209">Also, in an SAP system, not all columns can contain lowercase or uppercase characters.</span></span> <span data-ttu-id="decde-210">SAP の GUI を使用すると、テーブル内の列が小文字または大文字の文字を格納するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="decde-210">You can use the SAP GUI to find out whether a column in a table stores lowercase or uppercase characters.</span></span> <span data-ttu-id="decde-211">SAP の GUI を使用する方法の詳細については、次を参照してください。[を決定するかどうか、列ストア小文字または大文字の値](../../adapters-and-accelerators/adapter-sap/determining-whether-a-column-stores-lowercase-or-uppercase-values.md)です。</span><span class="sxs-lookup"><span data-stu-id="decde-211">For instructions on using the SAP GUI, see [Determining Whether a Column Stores Lowercase or Uppercase Values](../../adapters-and-accelerators/adapter-sap/determining-whether-a-column-stores-lowercase-or-uppercase-values.md).</span></span>  
  
-   <span data-ttu-id="decde-212">WHERE 条件はいくつかのデータ値を持つフィールドの値の比較に対してのみサポートと*いない*他のテーブルのフィールド値を使用します。</span><span class="sxs-lookup"><span data-stu-id="decde-212">The WHERE condition is supported only for comparison of a field value with some data value, and *not* with some other table field value.</span></span> <span data-ttu-id="decde-213">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]サポートしている 1 つのテーブル SELECT クエリ、テーブルのフィールド クエリの結合条件では、同じをサポートするために、結合条件を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="decde-213">Because the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] supports only one table SELECT query, table field queries in join conditions should use the join condition to support the same.</span></span>  
  
-   <span data-ttu-id="decde-214">結合条件では、テーブル名を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="decde-214">A join condition must contain a table name.</span></span>  
  
     <span data-ttu-id="decde-215">適切な SELECT ステートメントを次に示します</span><span class="sxs-lookup"><span data-stu-id="decde-215">The following is a correct SELECT statement</span></span>  
  
    ```  
    select A.x, B.y from A inner join B on A.m = B.n  
    ```  
  
     <span data-ttu-id="decde-216">正しくない SELECT ステートメントを次に示します</span><span class="sxs-lookup"><span data-stu-id="decde-216">The following is an incorrect SELECT statement</span></span>  
  
    ```  
    select A.x, B.y from A inner join B on m = n  
    ```  
  
-   <span data-ttu-id="decde-217">結合条件で結合条件で、左側のテーブルは、条件の左側にする必要があり、結合条件の右側にある、結合条件の右側のテーブルを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="decde-217">In a join condition, the left table in a join condition should be on the left side of the condition, and the right table of the join condition should be specified on the right side of the join condition.</span></span>  
  
     <span data-ttu-id="decde-218">結合条件を指定するための正しい方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="decde-218">The following is the correct way of specifying a join condition:</span></span>  
  
    ```  
    select A.x, B.y from A inner join B on A.m = B.n  
    ```  
  
     <span data-ttu-id="decde-219">結合条件を指定した場合の誤った方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="decde-219">The following is an incorrect way of specifying a join condition:</span></span>  
  
    ```  
    select A.x, B.y from A inner join B on B.n = A.m  
    ```  
  
-   <span data-ttu-id="decde-220">SELECT ステートメントには、JOIN 句で「と等しい」の条件のみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="decde-220">A SELECT statement can only contain an “equal to” condition in a JOIN clause.</span></span> <span data-ttu-id="decde-221">例:</span><span class="sxs-lookup"><span data-stu-id="decde-221">For example:</span></span>  
  
    ```  
    select * from spfli inner join sflight on spfli.carrid = sflight.carrid  
    ```  
  
-   <span data-ttu-id="decde-222">SELECT ステートメントは、SAP システムから文字列型の列を取得できません。</span><span class="sxs-lookup"><span data-stu-id="decde-222">A SELECT statement does not retrieve columns of type STRING from the SAP system.</span></span>  
  
-   <span data-ttu-id="decde-223">SELECT ステートメントでは、1 つの結合だけを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="decde-223">A SELECT statement must contain only a single JOIN.</span></span> <span data-ttu-id="decde-224">例:</span><span class="sxs-lookup"><span data-stu-id="decde-224">For example:</span></span>  
  
    ```  
    select * from spfli inner join sflight on spfli.carrid = sflight.carrid  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="decde-225">参照</span><span class="sxs-lookup"><span data-stu-id="decde-225">See Also</span></span>  
 [<span data-ttu-id="decde-226">.NET Framework Data Provider for mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="decde-226">About the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)