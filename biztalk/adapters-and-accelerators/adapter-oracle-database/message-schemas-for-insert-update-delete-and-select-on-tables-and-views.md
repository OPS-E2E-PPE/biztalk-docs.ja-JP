---
title: 基本的な Insert、Update、Delete、メッセージ スキーマとテーブルとビューで操作を選択します |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- operations on tables, message actions for
- table operations, message actions for
- table operations, message structure for
- operations on tables, message schemas for
- table operations, message schemas for
- operations on tables, message structure for
ms.assetid: 8228d5e6-14af-49e0-b34b-be03aea59189
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7f815f88144c2cb3659614c517fdc224c601e27
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989195"
---
# <a name="message-schemas-for-the-basic-insert-update-delete-and-select-operations-on-tables-and-views"></a><span data-ttu-id="34f5e-102">基本の挿入のメッセージ スキーマを更新、削除、およびテーブルとビューで操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="34f5e-102">Message Schemas for the Basic Insert, Update, Delete, and Select Operations on Tables and Views</span></span>
<span data-ttu-id="34f5e-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]サーフェスの基本的な Insert、Update、Delete、および Select 操作の各テーブルが表示され、Oracle データベースで表示します。</span><span class="sxs-lookup"><span data-stu-id="34f5e-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces basic Insert, Update, Delete, and Select operations for each table and view in the Oracle database.</span></span> <span data-ttu-id="34f5e-104">これらの操作では、WHERE 句で修飾された適切な SQL ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="34f5e-104">These operations perform the appropriate SQL statement qualified by a WHERE clause.</span></span> <span data-ttu-id="34f5e-105">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]これらの操作で厳密に型指定されたレコードとレコード セットを使用します。</span><span class="sxs-lookup"><span data-stu-id="34f5e-105">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] uses strongly-typed records and record sets in these operations.</span></span>  

## <a name="message-structure-for-basic-table-operations"></a><span data-ttu-id="34f5e-106">基本的なテーブル操作のメッセージの構造</span><span class="sxs-lookup"><span data-stu-id="34f5e-106">Message Structure for Basic Table Operations</span></span>  
 <span data-ttu-id="34f5e-107">次の表は、XML メッセージの構造によって公開されている基本的なテーブル操作のため、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースのテーブル。</span><span class="sxs-lookup"><span data-stu-id="34f5e-107">The following table shows the XML message structure for the basic table operations exposed by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] on Oracle database tables.</span></span> <span data-ttu-id="34f5e-108">操作の対象テーブルでは、メッセージのアクションで指定され、ターゲットの名前空間にも表示されます。</span><span class="sxs-lookup"><span data-stu-id="34f5e-108">The target table for an operation is specified in the message action and also appears in the target namespace.</span></span>  

### <a name="insert"></a><span data-ttu-id="34f5e-109">Insert</span><span class="sxs-lookup"><span data-stu-id="34f5e-109">Insert</span></span>  
<span data-ttu-id="34f5e-110">挿入操作の次の種類があります。</span><span class="sxs-lookup"><span data-stu-id="34f5e-110">There are the following types of Insert operations.</span></span> <span data-ttu-id="34f5e-111">メッセージには、挿入操作の種類を 1 つだけ含めることができます。</span><span class="sxs-lookup"><span data-stu-id="34f5e-111">A message can contain only one kind of Insert operation.</span></span>

- <span data-ttu-id="34f5e-112">対象のテーブルに厳密に型指定されたデータの指定されたレコード セットを挿入する複数のレコードを挿入します。</span><span class="sxs-lookup"><span data-stu-id="34f5e-112">Multiple Record Insert inserts the supplied record set of strongly-typed data into the target table.</span></span>
- <span data-ttu-id="34f5e-113">という名前の省略可能な属性の値を指定する複数のレコード挿入の各レコードの**InlineValue**します。</span><span class="sxs-lookup"><span data-stu-id="34f5e-113">For each record in a multiple record insert, you can specify value for an optional attribute called **InlineValue**.</span></span> <span data-ttu-id="34f5e-114">指定した場合は、要素の値をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="34f5e-114">If specified, it overrides the value of the element.</span></span>
- <span data-ttu-id="34f5e-115">Bulk Insert では、対象のテーブルにクエリ要素で指定された選択クエリによって返されるレコード セットを挿入します。</span><span class="sxs-lookup"><span data-stu-id="34f5e-115">Bulk Insert inserts the record set returned by a SELECT query specified in the QUERY element into the target table.</span></span> <span data-ttu-id="34f5e-116">これは、それらの要素で指定された列のコンマ区切りリストを使用して行います。</span><span class="sxs-lookup"><span data-stu-id="34f5e-116">This is done by using the comma-separated list of columns specified in the COLUMN_NAMES element.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="34f5e-117">XML メッセージ</span><span class="sxs-lookup"><span data-stu-id="34f5e-117">XML message</span></span>  

<span data-ttu-id="34f5e-118">**複数のレコードの挿入**</span><span class="sxs-lookup"><span data-stu-id="34f5e-118">**Multiple record insert**</span></span>  
```
<Insert xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<RECORDSET>     
<[TABLE_NAME]RECORDINSERT>       
<[FIELD1_NAME InlineValue="value"]>value1</[FIELD1_NAME]>       
<[FIELD2_NAME InlineValue="value"]>value2</[FIELD2_NAME]>       
…     
</[TABLE_NAME]RECORDINSERT>       
<[TABLE_NAME]RECORDINSERT >       
<[FIELD1_NAME InlineValue="value"]>value1</[FIELD1_NAME]>       
<[FIELD2_NAME InlineValue="value"]>value2</[FIELD2_NAME]>       
…     
</[TABLE_NAME]RECORDINSERT>     
…   
</RECORDSET> 
</Insert>
```

<span data-ttu-id="34f5e-119">SQL アダプターによって実行します。 `INSERT INTO TABLE_NAME (FIELD1_NAME, FIELD2_NAME, …)VALUES (value1, value2, …);`</span><span class="sxs-lookup"><span data-stu-id="34f5e-119">SQL executed by the adapter: `INSERT INTO TABLE_NAME (FIELD1_NAME, FIELD2_NAME, …)VALUES (value1, value2, …);`</span></span>


<span data-ttu-id="34f5e-120">**一括挿入**</span><span class="sxs-lookup"><span data-stu-id="34f5e-120">**Bulk Insert**</span></span>  
```
<Insert xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">
<COLUMN_NAMES>[COLUMN_list]</COLUMN_NAMES>
<QUERY>[SELECT_query]</QUERY>
</Insert>
```

<span data-ttu-id="34f5e-121">SQL アダプターによって実行します。 `INSERT INTO TABLE_NAME (COLUMN_list) SELECT_query;`</span><span class="sxs-lookup"><span data-stu-id="34f5e-121">SQL executed by the adapter: `INSERT INTO TABLE_NAME (COLUMN_list) SELECT_query;`</span></span>

### <a name="insert-response"></a><span data-ttu-id="34f5e-122">応答を挿入します。</span><span class="sxs-lookup"><span data-stu-id="34f5e-122">Insert Response</span></span>
<span data-ttu-id="34f5e-123">InsertResult 要素では、挿入された行の数が返されます。</span><span class="sxs-lookup"><span data-stu-id="34f5e-123">The number of rows inserted is returned in the InsertResult element.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="34f5e-124">XML メッセージ</span><span class="sxs-lookup"><span data-stu-id="34f5e-124">XML message</span></span>  

```
<InsertResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<InsertResult>[rows inserted]</InsertResult> 
</InsertResponse>
```

### <a name="select"></a><span data-ttu-id="34f5e-125">Select</span><span class="sxs-lookup"><span data-stu-id="34f5e-125">Select</span></span>
<span data-ttu-id="34f5e-126">フィルター要素で指定した WHERE 句を使用して対象テーブルに対する SELECT クエリが実行されます。</span><span class="sxs-lookup"><span data-stu-id="34f5e-126">A SELECT query is performed on the target table using the WHERE clause specified in the FILTER element.</span></span> <span data-ttu-id="34f5e-127">結果セットには、それらの要素で指定された列名のコンマ区切りリスト内の列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="34f5e-127">The result set contains the columns in the comma-separated list of column names specified in the COLUMN_NAMES element.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="34f5e-128">XML メッセージ</span><span class="sxs-lookup"><span data-stu-id="34f5e-128">XML message</span></span>  
```
<Select xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<COLUMN_NAMES>[COLUMN_list]</COLUMN_NAMES>   
<FILTER>WHERE_clause</FILTER> 
</Select>
```

<span data-ttu-id="34f5e-129">SQL アダプターによって実行します。 `SELECT COLUMN_list FROM TABLE_NAME WHERE WHERE_clause;`</span><span class="sxs-lookup"><span data-stu-id="34f5e-129">SQL executed by the adapter: `SELECT COLUMN_list FROM TABLE_NAME WHERE WHERE_clause;`</span></span>

### <a name="select-response"></a><span data-ttu-id="34f5e-130">応答を選択します。</span><span class="sxs-lookup"><span data-stu-id="34f5e-130">Select Response</span></span>
<span data-ttu-id="34f5e-131">SELECT クエリによって生成される結果セット。</span><span class="sxs-lookup"><span data-stu-id="34f5e-131">The result set generated by the SELECT query.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="34f5e-132">XML メッセージ</span><span class="sxs-lookup"><span data-stu-id="34f5e-132">XML message</span></span>  
```
<SelectResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<SelectResult>     
<[TABLE_NAME]RECORDSELECT>       
<[FIELD1_NAME]>value1</[FIELD1_NAME]>       
<[FIELD2_NAME]>value2</[FIELD2_NAME]>       
…     
</[TABLE_NAME]RECORDSELECT>   
</SelectResult> 
</SelectResponse>
``` 

### <a name="update"></a><span data-ttu-id="34f5e-133">更新</span><span class="sxs-lookup"><span data-stu-id="34f5e-133">Update</span></span>
<span data-ttu-id="34f5e-134">Where に一致する行フィルター要素で指定した句は、レコード セットで指定された値に更新されます。</span><span class="sxs-lookup"><span data-stu-id="34f5e-134">Rows that match the where clause specified in the FILTER element are updated to the values specified in the RECORDSET.</span></span> <span data-ttu-id="34f5e-135">レコード セットで指定されている列のみが一致する行ごとに更新されます。</span><span class="sxs-lookup"><span data-stu-id="34f5e-135">Only the columns that are specified in the RECORDSET are updated in each matching row.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="34f5e-136">XML メッセージ</span><span class="sxs-lookup"><span data-stu-id="34f5e-136">XML message</span></span>  
```
<Update xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<RECORDSET>     
<[FIELD1_NAME]>value1</[FIELD1_NAME]>     
<[FIELD2_NAME]>value2</[FIELD2_NAME]>       
…   
</RECORDSET>   
<FILTER>WHERE_clause</FILTER> </Update>
```

<span data-ttu-id="34f5e-137">SQL アダプターによって実行します。 `UPDATE [TABLE_NAME] SET [FIELD1_NAME] = value1, [FIELD2_NAME] = value2, … WHERE WHERE_clause;`</span><span class="sxs-lookup"><span data-stu-id="34f5e-137">SQL executed by the adapter: `UPDATE [TABLE_NAME] SET [FIELD1_NAME] = value1, [FIELD2_NAME] = value2, … WHERE WHERE_clause;`</span></span>

### <a name="update-response"></a><span data-ttu-id="34f5e-138">更新の応答</span><span class="sxs-lookup"><span data-stu-id="34f5e-138">Update Response</span></span>
<span data-ttu-id="34f5e-139">UpdateResult 要素では、更新された行の数が返されます。</span><span class="sxs-lookup"><span data-stu-id="34f5e-139">The number of rows updated is returned in the UpdateResult element.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="34f5e-140">XML メッセージ</span><span class="sxs-lookup"><span data-stu-id="34f5e-140">XML message</span></span>  
```
<UpdateResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<UpdateResult>[rows inserted]</UpdateResult> 
</UpdateResponse>
```

### <a name="delete"></a><span data-ttu-id="34f5e-141">DELETE</span><span class="sxs-lookup"><span data-stu-id="34f5e-141">Delete</span></span>
<span data-ttu-id="34f5e-142">フィルター要素で指定した WHERE 句に一致する行が削除されます。</span><span class="sxs-lookup"><span data-stu-id="34f5e-142">Rows matching the WHERE clause specified by the FILTER element are deleted.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="34f5e-143">XML メッセージ</span><span class="sxs-lookup"><span data-stu-id="34f5e-143">XML message</span></span> 
```
<Delete xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<FILTER>WHERE_clause</FILTER> 
</Delete>
```

<span data-ttu-id="34f5e-144">SQL アダプターによって実行します。 `DELETE FROM [TABLE_NAME] WHERE WHERE_clause;`</span><span class="sxs-lookup"><span data-stu-id="34f5e-144">SQL executed by the adapter: `DELETE FROM [TABLE_NAME] WHERE WHERE_clause;`</span></span>

### <a name="delete-response"></a><span data-ttu-id="34f5e-145">応答を削除します。</span><span class="sxs-lookup"><span data-stu-id="34f5e-145">Delete Response</span></span>
<span data-ttu-id="34f5e-146">DeleteResult 要素では、削除された行の数が返されます。</span><span class="sxs-lookup"><span data-stu-id="34f5e-146">The number of rows deleted is returned in the DeleteResult element.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="34f5e-147">XML メッセージ</span><span class="sxs-lookup"><span data-stu-id="34f5e-147">XML message</span></span> 
```
<DeleteResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<DeleteResult>[rows inserted]</DeleteResult> 
</DeleteResponse>
```

  | <span data-ttu-id="34f5e-148">プレース ホルダーの値</span><span class="sxs-lookup"><span data-stu-id="34f5e-148">Placeholder value</span></span>| <span data-ttu-id="34f5e-149">説明</span><span class="sxs-lookup"><span data-stu-id="34f5e-149">Description</span></span> |
  | --- | --- |
  | <span data-ttu-id="34f5e-150">[バージョン]</span><span class="sxs-lookup"><span data-stu-id="34f5e-150">[VERSION]</span></span> | <span data-ttu-id="34f5e-151">メッセージのバージョン文字列。例えば `http://Microsoft.LobServices.OracleDB/2007/03`</span><span class="sxs-lookup"><span data-stu-id="34f5e-151">The message version string; for example, `http://Microsoft.LobServices.OracleDB/2007/03`</span></span>|
  | <span data-ttu-id="34f5e-152">[スキーマ]</span><span class="sxs-lookup"><span data-stu-id="34f5e-152">[SCHEMA]</span></span> | <span data-ttu-id="34f5e-153">Oracle の成果物のコレクション例えば `SCOTT`</span><span class="sxs-lookup"><span data-stu-id="34f5e-153">Collection of Oracle artifacts; for example, `SCOTT`</span></span>|
  | <span data-ttu-id="34f5e-154">[TABLE_NAME]</span><span class="sxs-lookup"><span data-stu-id="34f5e-154">[TABLE_NAME]</span></span> | <span data-ttu-id="34f5e-155">テーブルの名前例えば `EMP`</span><span class="sxs-lookup"><span data-stu-id="34f5e-155">Name of the table; for example, `EMP`</span></span>|
  | <span data-ttu-id="34f5e-156">[FIELD1_NAME]</span><span class="sxs-lookup"><span data-stu-id="34f5e-156">[FIELD1_NAME]</span></span> | <span data-ttu-id="34f5e-157">テーブルのフィールド名です。例えば `EMPNAME`</span><span class="sxs-lookup"><span data-stu-id="34f5e-157">Table field name; for example, `EMPNAME`</span></span>|
  | <span data-ttu-id="34f5e-158">[COLUMN_list]</span><span class="sxs-lookup"><span data-stu-id="34f5e-158">[COLUMN_list]</span></span> | <span data-ttu-id="34f5e-159">列のコンマ区切りの一覧例えば `NAME`</span><span class="sxs-lookup"><span data-stu-id="34f5e-159">Comma-separated list of columns; for example, `NAME`</span></span>|
  | <span data-ttu-id="34f5e-160">[SELECT_query]</span><span class="sxs-lookup"><span data-stu-id="34f5e-160">[SELECT_query]</span></span> | <span data-ttu-id="34f5e-161">一括挿入操作のクエリ要素で指定した SQL SELECT ステートメント例えば `SELECT * from MyTable`</span><span class="sxs-lookup"><span data-stu-id="34f5e-161">A SQL SELECT statement specified in the QUERY element of a Bulk Insert operation; for example, `SELECT * from MyTable`</span></span>|
  | <span data-ttu-id="34f5e-162">[WHERE_clause]</span><span class="sxs-lookup"><span data-stu-id="34f5e-162">[WHERE_clause]</span></span> | <span data-ttu-id="34f5e-163">WHERE_clause; 操作に使用される SELECT ステートメント例えば `ID > 10`</span><span class="sxs-lookup"><span data-stu-id="34f5e-163">WHERE_clause for the SELECT statement used for the operation; for example, `ID > 10`</span></span>|

> [!IMPORTANT]
>  <span data-ttu-id="34f5e-164">テーブル、ビューに対する基本的なテーブル操作のメッセージの構造と同じですが、操作の名前空間は、テーブルではなく、ビューを指定します:`<Insert xmlns ="[VERSION]/[SCHEMA]/``View``/[VIEW_NAME]">`します。</span><span class="sxs-lookup"><span data-stu-id="34f5e-164">The message structure for the basic table operations on views is the same as that on tables, but the namespace for the operation specifies a view rather than a table: `<Insert xmlns ="[VERSION]/[SCHEMA]/``View``/[VIEW_NAME]">`.</span></span>  

## <a name="message-actions-for-basic-table-operations"></a><span data-ttu-id="34f5e-165">基本的なテーブル操作のメッセージのアクション</span><span class="sxs-lookup"><span data-stu-id="34f5e-165">Message Actions for Basic Table Operations</span></span>  
 <span data-ttu-id="34f5e-166">次の表は、メッセージのアクションで使用される、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]テーブルに対する基本的なテーブルの操作。</span><span class="sxs-lookup"><span data-stu-id="34f5e-166">The following table shows the message actions that are used by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] for the basic table operations on tables.</span></span> <span data-ttu-id="34f5e-167">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]操作の対象のテーブルを確認するメッセージのアクションで指定されたテーブル名を使用します。</span><span class="sxs-lookup"><span data-stu-id="34f5e-167">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] uses the table name specified in the message action to determine the target table of the operation.</span></span>  


|    <span data-ttu-id="34f5e-168">演算</span><span class="sxs-lookup"><span data-stu-id="34f5e-168">Operation</span></span>    |                    <span data-ttu-id="34f5e-169">メッセージのアクション</span><span class="sxs-lookup"><span data-stu-id="34f5e-169">Message Action</span></span>                     |                                    <span data-ttu-id="34f5e-170">例</span><span class="sxs-lookup"><span data-stu-id="34f5e-170">Example</span></span>                                    |
|-----------------|-------------------------------------------------------|-------------------------------------------------------------------------------|
|     <span data-ttu-id="34f5e-171">Insert</span><span class="sxs-lookup"><span data-stu-id="34f5e-171">Insert</span></span>      |     <span data-ttu-id="34f5e-172">[バージョン]/[SCHEMA]/Table/[TABLE_NAME]/挿入</span><span class="sxs-lookup"><span data-stu-id="34f5e-172">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Insert</span></span>      |     http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert      |
| <span data-ttu-id="34f5e-173">応答を挿入します。</span><span class="sxs-lookup"><span data-stu-id="34f5e-173">Insert Response</span></span> | <span data-ttu-id="34f5e-174">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Insert/response</span><span class="sxs-lookup"><span data-stu-id="34f5e-174">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Insert/response</span></span> | http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert/response |
|     <span data-ttu-id="34f5e-175">Select</span><span class="sxs-lookup"><span data-stu-id="34f5e-175">Select</span></span>      |     <span data-ttu-id="34f5e-176">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Select</span><span class="sxs-lookup"><span data-stu-id="34f5e-176">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Select</span></span>      |     http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select      |
| <span data-ttu-id="34f5e-177">応答を選択します。</span><span class="sxs-lookup"><span data-stu-id="34f5e-177">Select Response</span></span> | <span data-ttu-id="34f5e-178">[バージョン]/[SCHEMA]/Table/[TABLE_NAME] を選択/応答</span><span class="sxs-lookup"><span data-stu-id="34f5e-178">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Select/response</span></span> | http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select/response |
|     <span data-ttu-id="34f5e-179">更新</span><span class="sxs-lookup"><span data-stu-id="34f5e-179">Update</span></span>      |     <span data-ttu-id="34f5e-180">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Update</span><span class="sxs-lookup"><span data-stu-id="34f5e-180">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Update</span></span>      |     http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update      |
| <span data-ttu-id="34f5e-181">更新の応答</span><span class="sxs-lookup"><span data-stu-id="34f5e-181">Update Response</span></span> | <span data-ttu-id="34f5e-182">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Update/response</span><span class="sxs-lookup"><span data-stu-id="34f5e-182">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Update/response</span></span> | http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update/response |
|     <span data-ttu-id="34f5e-183">DELETE</span><span class="sxs-lookup"><span data-stu-id="34f5e-183">Delete</span></span>      |     <span data-ttu-id="34f5e-184">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Delete</span><span class="sxs-lookup"><span data-stu-id="34f5e-184">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Delete</span></span>      |     http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete      |
| <span data-ttu-id="34f5e-185">応答を削除します。</span><span class="sxs-lookup"><span data-stu-id="34f5e-185">Delete Response</span></span> | <span data-ttu-id="34f5e-186">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Delete/response</span><span class="sxs-lookup"><span data-stu-id="34f5e-186">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Delete/response</span></span> | http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete/response |

 <span data-ttu-id="34f5e-187">[バージョン] = メッセージ バージョン文字列。たとえば、http://Microsoft.LobServices.OracleDB/2007/03します。</span><span class="sxs-lookup"><span data-stu-id="34f5e-187">[VERSION] = The message version string; for example, http://Microsoft.LobServices.OracleDB/2007/03.</span></span>  

 <span data-ttu-id="34f5e-188">[スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。</span><span class="sxs-lookup"><span data-stu-id="34f5e-188">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  

 <span data-ttu-id="34f5e-189">[TABLE_NAME]; テーブルの名前を =たとえば、EMP です。</span><span class="sxs-lookup"><span data-stu-id="34f5e-189">[TABLE_NAME] = Name of the table; for example, EMP.</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="34f5e-190">ビューで操作のメッセージのアクションと同じですがテーブルの"View"が"Table"; を置換する点を除いてたとえば、 `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/``View``/EMPVIEW/Insert` します。</span><span class="sxs-lookup"><span data-stu-id="34f5e-190">The message action for an operation on a view is the same as that for a table except that "View" replaces "Table"; for example, `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/``View``/EMPVIEW/Insert`.</span></span>  

## <a name="see-also"></a><span data-ttu-id="34f5e-191">参照</span><span class="sxs-lookup"><span data-stu-id="34f5e-191">See Also</span></span>  
 [<span data-ttu-id="34f5e-192">BizTalk Adapter for Oracle Database 用のメッセージとメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="34f5e-192">Messages and Message Schemas for BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)