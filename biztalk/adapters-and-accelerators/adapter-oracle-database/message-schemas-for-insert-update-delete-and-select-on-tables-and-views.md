---
title: 基本的な Insert、Update、Delete のメッセージ スキーマおよびテーブルおよびビューの操作の選択 |Microsoft ドキュメント
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
ms.openlocfilehash: 571a6a192ca85eb0bd3e5abeb8ef8f3715818236
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216002"
---
# <a name="message-schemas-for-the-basic-insert-update-delete-and-select-operations-on-tables-and-views"></a><span data-ttu-id="cf87f-102">基本的な insert、メッセージ スキーマを更新、削除、およびテーブルおよびビューの操作の選択</span><span class="sxs-lookup"><span data-stu-id="cf87f-102">Message Schemas for the Basic Insert, Update, Delete, and Select Operations on Tables and Views</span></span>
<span data-ttu-id="cf87f-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]サーフェスの基本的な Insert、Update、Delete、および Select 操作ごとにテーブルが表示され、Oracle データベースで表示します。</span><span class="sxs-lookup"><span data-stu-id="cf87f-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces basic Insert, Update, Delete, and Select operations for each table and view in the Oracle database.</span></span> <span data-ttu-id="cf87f-104">これらの操作は、WHERE 句で修飾された適切な SQL ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="cf87f-104">These operations perform the appropriate SQL statement qualified by a WHERE clause.</span></span> <span data-ttu-id="cf87f-105">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]これらの操作で厳密に型指定されたレコードとレコード セットを使用します。</span><span class="sxs-lookup"><span data-stu-id="cf87f-105">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] uses strongly-typed records and record sets in these operations.</span></span>  
  
## <a name="message-structure-for-basic-table-operations"></a><span data-ttu-id="cf87f-106">基本的なテーブル操作に対するメッセージの構造</span><span class="sxs-lookup"><span data-stu-id="cf87f-106">Message Structure for Basic Table Operations</span></span>  
 <span data-ttu-id="cf87f-107">次の表は、XML メッセージの構造によって公開されている基本的なテーブル操作のため、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベース テーブルにします。</span><span class="sxs-lookup"><span data-stu-id="cf87f-107">The following table shows the XML message structure for the basic table operations exposed by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] on Oracle database tables.</span></span> <span data-ttu-id="cf87f-108">操作の対象テーブルでは、メッセージのアクションで指定され、ターゲットの名前空間にも表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf87f-108">The target table for an operation is specified in the message action and also appears in the target namespace.</span></span>  

### <a name="insert"></a><span data-ttu-id="cf87f-109">Insert</span><span class="sxs-lookup"><span data-stu-id="cf87f-109">Insert</span></span>  
<span data-ttu-id="cf87f-110">挿入操作の次の種類があります。</span><span class="sxs-lookup"><span data-stu-id="cf87f-110">There are the following types of Insert operations.</span></span> <span data-ttu-id="cf87f-111">メッセージには、挿入操作の種類を 1 つだけを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="cf87f-111">A message can contain only one kind of Insert operation.</span></span>

- <span data-ttu-id="cf87f-112">対象のテーブルに厳密に型指定されたデータの指定されたレコード セットを挿入する複数のレコードを挿入します。</span><span class="sxs-lookup"><span data-stu-id="cf87f-112">Multiple Record Insert inserts the supplied record set of strongly-typed data into the target table.</span></span>
- <span data-ttu-id="cf87f-113">複数のレコード挿入内の各レコードと呼ばれる省略可能な属性の値を指定できます**InlineValue**です。</span><span class="sxs-lookup"><span data-stu-id="cf87f-113">For each record in a multiple record insert, you can specify value for an optional attribute called **InlineValue**.</span></span> <span data-ttu-id="cf87f-114">指定する場合は、要素の値を上書きします。</span><span class="sxs-lookup"><span data-stu-id="cf87f-114">If specified, it overrides the value of the element.</span></span>
- <span data-ttu-id="cf87f-115">一括挿入は、対象のテーブルにクエリ要素で指定された選択クエリによって返されるレコード セットを挿入します。</span><span class="sxs-lookup"><span data-stu-id="cf87f-115">Bulk Insert inserts the record set returned by a SELECT query specified in the QUERY element into the target table.</span></span> <span data-ttu-id="cf87f-116">これは、それらの要素で指定された列のコンマ区切りリストを使用して行います。</span><span class="sxs-lookup"><span data-stu-id="cf87f-116">This is done by using the comma-separated list of columns specified in the COLUMN_NAMES element.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="cf87f-117">XML メッセージ</span><span class="sxs-lookup"><span data-stu-id="cf87f-117">XML message</span></span>  

<span data-ttu-id="cf87f-118">**複数のレコードの挿入**</span><span class="sxs-lookup"><span data-stu-id="cf87f-118">**Multiple record insert**</span></span>  
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

<span data-ttu-id="cf87f-119">SQL アダプターによって実行します。`INSERT INTO TABLE_NAME (FIELD1_NAME, FIELD2_NAME, …)VALUES (value1, value2, …);`</span><span class="sxs-lookup"><span data-stu-id="cf87f-119">SQL executed by the adapter: `INSERT INTO TABLE_NAME (FIELD1_NAME, FIELD2_NAME, …)VALUES (value1, value2, …);`</span></span>


<span data-ttu-id="cf87f-120">**一括挿入**</span><span class="sxs-lookup"><span data-stu-id="cf87f-120">**Bulk Insert**</span></span>  
```
<Insert xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">
<COLUMN_NAMES>[COLUMN_list]</COLUMN_NAMES>
<QUERY>[SELECT_query]</QUERY>
</Insert>
```

<span data-ttu-id="cf87f-121">SQL アダプターによって実行します。`INSERT INTO TABLE_NAME (COLUMN_list) SELECT_query;`</span><span class="sxs-lookup"><span data-stu-id="cf87f-121">SQL executed by the adapter: `INSERT INTO TABLE_NAME (COLUMN_list) SELECT_query;`</span></span>

### <a name="insert-response"></a><span data-ttu-id="cf87f-122">応答を挿入します。</span><span class="sxs-lookup"><span data-stu-id="cf87f-122">Insert Response</span></span>
<span data-ttu-id="cf87f-123">InsertResult 要素では、挿入された行の数が返されます。</span><span class="sxs-lookup"><span data-stu-id="cf87f-123">The number of rows inserted is returned in the InsertResult element.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="cf87f-124">XML メッセージ</span><span class="sxs-lookup"><span data-stu-id="cf87f-124">XML message</span></span>  

```
<InsertResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<InsertResult>[rows inserted]</InsertResult> 
</InsertResponse>
```

### <a name="select"></a><span data-ttu-id="cf87f-125">Select</span><span class="sxs-lookup"><span data-stu-id="cf87f-125">Select</span></span>
<span data-ttu-id="cf87f-126">SELECT クエリは、フィルター要素で指定する WHERE 句を使用して、対象テーブルで実行されます。</span><span class="sxs-lookup"><span data-stu-id="cf87f-126">A SELECT query is performed on the target table using the WHERE clause specified in the FILTER element.</span></span> <span data-ttu-id="cf87f-127">結果セットには、それらの要素で指定された列名のコンマ区切りリスト内の列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cf87f-127">The result set contains the columns in the comma-separated list of column names specified in the COLUMN_NAMES element.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="cf87f-128">XML メッセージ</span><span class="sxs-lookup"><span data-stu-id="cf87f-128">XML message</span></span>  
```
<Select xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<COLUMN_NAMES>[COLUMN_list]</COLUMN_NAMES>   
<FILTER>WHERE_clause</FILTER> 
</Select>
```

<span data-ttu-id="cf87f-129">SQL アダプターによって実行します。`SELECT COLUMN_list FROM TABLE_NAME WHERE WHERE_clause;`</span><span class="sxs-lookup"><span data-stu-id="cf87f-129">SQL executed by the adapter: `SELECT COLUMN_list FROM TABLE_NAME WHERE WHERE_clause;`</span></span>

### <a name="select-response"></a><span data-ttu-id="cf87f-130">応答を選択します。</span><span class="sxs-lookup"><span data-stu-id="cf87f-130">Select Response</span></span>
<span data-ttu-id="cf87f-131">SELECT クエリによって生成される結果セットです。</span><span class="sxs-lookup"><span data-stu-id="cf87f-131">The result set generated by the SELECT query.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="cf87f-132">XML メッセージ</span><span class="sxs-lookup"><span data-stu-id="cf87f-132">XML message</span></span>  
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

### <a name="update"></a><span data-ttu-id="cf87f-133">Update</span><span class="sxs-lookup"><span data-stu-id="cf87f-133">Update</span></span>
<span data-ttu-id="cf87f-134">Where に一致する行フィルター要素で指定されている句は、レコード セットの指定した値に更新されます。</span><span class="sxs-lookup"><span data-stu-id="cf87f-134">Rows that match the where clause specified in the FILTER element are updated to the values specified in the RECORDSET.</span></span> <span data-ttu-id="cf87f-135">レコード セットで指定されている列のみが一致行ごとに更新されます。</span><span class="sxs-lookup"><span data-stu-id="cf87f-135">Only the columns that are specified in the RECORDSET are updated in each matching row.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="cf87f-136">XML メッセージ</span><span class="sxs-lookup"><span data-stu-id="cf87f-136">XML message</span></span>  
```
<Update xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<RECORDSET>     
<[FIELD1_NAME]>value1</[FIELD1_NAME]>     
<[FIELD2_NAME]>value2</[FIELD2_NAME]>       
…   
</RECORDSET>   
<FILTER>WHERE_clause</FILTER> </Update>
```

<span data-ttu-id="cf87f-137">SQL アダプターによって実行します。`UPDATE [TABLE_NAME] SET [FIELD1_NAME] = value1, [FIELD2_NAME] = value2, … WHERE WHERE_clause;`</span><span class="sxs-lookup"><span data-stu-id="cf87f-137">SQL executed by the adapter: `UPDATE [TABLE_NAME] SET [FIELD1_NAME] = value1, [FIELD2_NAME] = value2, … WHERE WHERE_clause;`</span></span>

### <a name="update-response"></a><span data-ttu-id="cf87f-138">更新の応答</span><span class="sxs-lookup"><span data-stu-id="cf87f-138">Update Response</span></span>
<span data-ttu-id="cf87f-139">UpdateResult 要素では、更新された行の数が返されます。</span><span class="sxs-lookup"><span data-stu-id="cf87f-139">The number of rows updated is returned in the UpdateResult element.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="cf87f-140">XML メッセージ</span><span class="sxs-lookup"><span data-stu-id="cf87f-140">XML message</span></span>  
```
<UpdateResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<UpdateResult>[rows inserted]</UpdateResult> 
</UpdateResponse>
```

### <a name="delete"></a><span data-ttu-id="cf87f-141">DELETE</span><span class="sxs-lookup"><span data-stu-id="cf87f-141">Delete</span></span>
<span data-ttu-id="cf87f-142">フィルター要素で指定された WHERE 句に一致する行が削除されます。</span><span class="sxs-lookup"><span data-stu-id="cf87f-142">Rows matching the WHERE clause specified by the FILTER element are deleted.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="cf87f-143">XML メッセージ</span><span class="sxs-lookup"><span data-stu-id="cf87f-143">XML message</span></span> 
```
<Delete xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<FILTER>WHERE_clause</FILTER> 
</Delete>
```

<span data-ttu-id="cf87f-144">SQL アダプターによって実行します。`DELETE FROM [TABLE_NAME] WHERE WHERE_clause;`</span><span class="sxs-lookup"><span data-stu-id="cf87f-144">SQL executed by the adapter: `DELETE FROM [TABLE_NAME] WHERE WHERE_clause;`</span></span>

### <a name="delete-response"></a><span data-ttu-id="cf87f-145">応答を削除します。</span><span class="sxs-lookup"><span data-stu-id="cf87f-145">Delete Response</span></span>
<span data-ttu-id="cf87f-146">DeleteResult 要素では、削除された行の数が返されます。</span><span class="sxs-lookup"><span data-stu-id="cf87f-146">The number of rows deleted is returned in the DeleteResult element.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="cf87f-147">XML メッセージ</span><span class="sxs-lookup"><span data-stu-id="cf87f-147">XML message</span></span> 
```
<DeleteResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<DeleteResult>[rows inserted]</DeleteResult> 
</DeleteResponse>
```
  
  | <span data-ttu-id="cf87f-148">プレース ホルダーの値</span><span class="sxs-lookup"><span data-stu-id="cf87f-148">Placeholder value</span></span>| <span data-ttu-id="cf87f-149">Description</span><span class="sxs-lookup"><span data-stu-id="cf87f-149">Description</span></span> |
  | --- | --- |
  | <span data-ttu-id="cf87f-150">[バージョン]</span><span class="sxs-lookup"><span data-stu-id="cf87f-150">[VERSION]</span></span> | <span data-ttu-id="cf87f-151">メッセージのバージョン文字列です。例えば`http://Microsoft.LobServices.OracleDB/2007/03`</span><span class="sxs-lookup"><span data-stu-id="cf87f-151">The message version string; for example, `http://Microsoft.LobServices.OracleDB/2007/03`</span></span>|
  | <span data-ttu-id="cf87f-152">[スキーマ]</span><span class="sxs-lookup"><span data-stu-id="cf87f-152">[SCHEMA]</span></span> | <span data-ttu-id="cf87f-153">Oracle の成果物のコレクション例えば`SCOTT`</span><span class="sxs-lookup"><span data-stu-id="cf87f-153">Collection of Oracle artifacts; for example, `SCOTT`</span></span>|
  | <span data-ttu-id="cf87f-154">[TABLE_NAME]</span><span class="sxs-lookup"><span data-stu-id="cf87f-154">[TABLE_NAME]</span></span> | <span data-ttu-id="cf87f-155">テーブルの名前例えば`EMP`</span><span class="sxs-lookup"><span data-stu-id="cf87f-155">Name of the table; for example, `EMP`</span></span>|
  | <span data-ttu-id="cf87f-156">[FIELD1_NAME]</span><span class="sxs-lookup"><span data-stu-id="cf87f-156">[FIELD1_NAME]</span></span> | <span data-ttu-id="cf87f-157">テーブルのフィールド名です。例えば`EMPNAME`</span><span class="sxs-lookup"><span data-stu-id="cf87f-157">Table field name; for example, `EMPNAME`</span></span>|
  | <span data-ttu-id="cf87f-158">[COLUMN_list]</span><span class="sxs-lookup"><span data-stu-id="cf87f-158">[COLUMN_list]</span></span> | <span data-ttu-id="cf87f-159">列のコンマ区切りの一覧例えば`NAME`</span><span class="sxs-lookup"><span data-stu-id="cf87f-159">Comma-separated list of columns; for example, `NAME`</span></span>|
  | <span data-ttu-id="cf87f-160">[SELECT_query]</span><span class="sxs-lookup"><span data-stu-id="cf87f-160">[SELECT_query]</span></span> | <span data-ttu-id="cf87f-161">一括挿入操作のクエリ要素で指定した SQL SELECT ステートメント例えば`SELECT * from MyTable`</span><span class="sxs-lookup"><span data-stu-id="cf87f-161">A SQL SELECT statement specified in the QUERY element of a Bulk Insert operation; for example, `SELECT * from MyTable`</span></span>|
  | <span data-ttu-id="cf87f-162">[WHERE_clause]</span><span class="sxs-lookup"><span data-stu-id="cf87f-162">[WHERE_clause]</span></span> | <span data-ttu-id="cf87f-163">操作を使用する SELECT ステートメントの WHERE_clause例えば`ID > 10`</span><span class="sxs-lookup"><span data-stu-id="cf87f-163">WHERE_clause for the SELECT statement used for the operation; for example, `ID > 10`</span></span>|
  
> [!IMPORTANT]
>  <span data-ttu-id="cf87f-164">基本的なテーブルでの操作のビューのメッセージの構造と同じテーブルは、操作の名前空間は、テーブルではなく、ビューを指定します。:`<Insert xmlns ="[VERSION]/[SCHEMA]/``View``/[VIEW_NAME]">`です。</span><span class="sxs-lookup"><span data-stu-id="cf87f-164">The message structure for the basic table operations on views is the same as that on tables, but the namespace for the operation specifies a view rather than a table: `<Insert xmlns ="[VERSION]/[SCHEMA]/``View``/[VIEW_NAME]">`.</span></span>  
  
## <a name="message-actions-for-basic-table-operations"></a><span data-ttu-id="cf87f-165">基本的なテーブル操作のメッセージ アクション</span><span class="sxs-lookup"><span data-stu-id="cf87f-165">Message Actions for Basic Table Operations</span></span>  
 <span data-ttu-id="cf87f-166">次の表は、メッセージ アクションで使用される、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]基本的なテーブルでの操作のテーブルです。</span><span class="sxs-lookup"><span data-stu-id="cf87f-166">The following table shows the message actions that are used by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] for the basic table operations on tables.</span></span> <span data-ttu-id="cf87f-167">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]メッセージ アクションで指定したテーブル名を使用して、操作の対象のテーブルを確認します。</span><span class="sxs-lookup"><span data-stu-id="cf87f-167">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] uses the table name specified in the message action to determine the target table of the operation.</span></span>  
  
|<span data-ttu-id="cf87f-168">操作</span><span class="sxs-lookup"><span data-stu-id="cf87f-168">Operation</span></span>|<span data-ttu-id="cf87f-169">メッセージのアクション</span><span class="sxs-lookup"><span data-stu-id="cf87f-169">Message Action</span></span>|<span data-ttu-id="cf87f-170">例</span><span class="sxs-lookup"><span data-stu-id="cf87f-170">Example</span></span>|  
|---------------|--------------------|-------------|  
|<span data-ttu-id="cf87f-171">Insert</span><span class="sxs-lookup"><span data-stu-id="cf87f-171">Insert</span></span>|<span data-ttu-id="cf87f-172">[バージョン]/[SCHEMA]/Table/[TABLE_NAME]/挿入</span><span class="sxs-lookup"><span data-stu-id="cf87f-172">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Insert</span></span>|<span data-ttu-id="cf87f-173">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert</span><span class="sxs-lookup"><span data-stu-id="cf87f-173">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert</span></span>|  
|<span data-ttu-id="cf87f-174">応答を挿入します。</span><span class="sxs-lookup"><span data-stu-id="cf87f-174">Insert Response</span></span>|<span data-ttu-id="cf87f-175">[バージョン]/[SCHEMA]/Table/[TABLE_NAME]/挿入/応答</span><span class="sxs-lookup"><span data-stu-id="cf87f-175">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Insert/response</span></span>|<span data-ttu-id="cf87f-176">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert/response</span><span class="sxs-lookup"><span data-stu-id="cf87f-176">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert/response</span></span>|  
|<span data-ttu-id="cf87f-177">Select</span><span class="sxs-lookup"><span data-stu-id="cf87f-177">Select</span></span>|<span data-ttu-id="cf87f-178">[バージョン]/[SCHEMA]/Table/[TABLE_NAME] を選択/</span><span class="sxs-lookup"><span data-stu-id="cf87f-178">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Select</span></span>|<span data-ttu-id="cf87f-179">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select</span><span class="sxs-lookup"><span data-stu-id="cf87f-179">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select</span></span>|  
|<span data-ttu-id="cf87f-180">応答を選択します。</span><span class="sxs-lookup"><span data-stu-id="cf87f-180">Select Response</span></span>|<span data-ttu-id="cf87f-181">[バージョン]/[SCHEMA]/Table/[TABLE_NAME] を選択/応答</span><span class="sxs-lookup"><span data-stu-id="cf87f-181">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Select/response</span></span>|<span data-ttu-id="cf87f-182">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select/response</span><span class="sxs-lookup"><span data-stu-id="cf87f-182">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select/response</span></span>|  
|<span data-ttu-id="cf87f-183">Update</span><span class="sxs-lookup"><span data-stu-id="cf87f-183">Update</span></span>|<span data-ttu-id="cf87f-184">[バージョン]/[SCHEMA]/Table/[TABLE_NAME]/更新</span><span class="sxs-lookup"><span data-stu-id="cf87f-184">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Update</span></span>|<span data-ttu-id="cf87f-185">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update</span><span class="sxs-lookup"><span data-stu-id="cf87f-185">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update</span></span>|  
|<span data-ttu-id="cf87f-186">更新の応答</span><span class="sxs-lookup"><span data-stu-id="cf87f-186">Update Response</span></span>|<span data-ttu-id="cf87f-187">[バージョン]/[SCHEMA]/Table/[TABLE_NAME]/更新/応答</span><span class="sxs-lookup"><span data-stu-id="cf87f-187">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Update/response</span></span>|<span data-ttu-id="cf87f-188">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update/response</span><span class="sxs-lookup"><span data-stu-id="cf87f-188">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update/response</span></span>|  
|<span data-ttu-id="cf87f-189">DELETE</span><span class="sxs-lookup"><span data-stu-id="cf87f-189">Delete</span></span>|<span data-ttu-id="cf87f-190">[バージョン]/[SCHEMA]/Table/[TABLE_NAME] を削除します</span><span class="sxs-lookup"><span data-stu-id="cf87f-190">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Delete</span></span>|<span data-ttu-id="cf87f-191">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete</span><span class="sxs-lookup"><span data-stu-id="cf87f-191">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete</span></span>|  
|<span data-ttu-id="cf87f-192">応答を削除します。</span><span class="sxs-lookup"><span data-stu-id="cf87f-192">Delete Response</span></span>|<span data-ttu-id="cf87f-193">[バージョン]/[SCHEMA]/Table/[TABLE_NAME]/削除/応答</span><span class="sxs-lookup"><span data-stu-id="cf87f-193">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Delete/response</span></span>|<span data-ttu-id="cf87f-194">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete/response</span><span class="sxs-lookup"><span data-stu-id="cf87f-194">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete/response</span></span>|  
  
 <span data-ttu-id="cf87f-195">[バージョン]、メッセージのバージョン文字列を =たとえば、http://Microsoft.LobServices.OracleDB/2007/03 です。</span><span class="sxs-lookup"><span data-stu-id="cf87f-195">[VERSION] = The message version string; for example, http://Microsoft.LobServices.OracleDB/2007/03.</span></span>  
  
 <span data-ttu-id="cf87f-196">[スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。</span><span class="sxs-lookup"><span data-stu-id="cf87f-196">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="cf87f-197">[TABLE_NAME] テーブルの名前を =たとえば、EMP です。</span><span class="sxs-lookup"><span data-stu-id="cf87f-197">[TABLE_NAME] = Name of the table; for example, EMP.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cf87f-198">ビューで操作のメッセージ アクションと同じでは、テーブルの"View"が"Table"; を置換する点を除いてたとえば、`http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/``View``/EMPVIEW/Insert`です。</span><span class="sxs-lookup"><span data-stu-id="cf87f-198">The message action for an operation on a view is the same as that for a table except that "View" replaces "Table"; for example, `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/``View``/EMPVIEW/Insert`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf87f-199">参照</span><span class="sxs-lookup"><span data-stu-id="cf87f-199">See Also</span></span>  
 [<span data-ttu-id="cf87f-200">メッセージと BizTalk Adapter 用 Oracle Database のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="cf87f-200">Messages and Message Schemas for BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)