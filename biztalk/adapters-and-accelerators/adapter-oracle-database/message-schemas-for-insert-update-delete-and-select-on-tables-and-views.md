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
# <a name="message-schemas-for-the-basic-insert-update-delete-and-select-operations-on-tables-and-views"></a>基本的な insert、メッセージ スキーマを更新、削除、およびテーブルおよびビューの操作の選択
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]サーフェスの基本的な Insert、Update、Delete、および Select 操作ごとにテーブルが表示され、Oracle データベースで表示します。 これらの操作は、WHERE 句で修飾された適切な SQL ステートメントを実行します。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]これらの操作で厳密に型指定されたレコードとレコード セットを使用します。  
  
## <a name="message-structure-for-basic-table-operations"></a>基本的なテーブル操作に対するメッセージの構造  
 次の表は、XML メッセージの構造によって公開されている基本的なテーブル操作のため、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベース テーブルにします。 操作の対象テーブルでは、メッセージのアクションで指定され、ターゲットの名前空間にも表示されます。  

### <a name="insert"></a>Insert  
挿入操作の次の種類があります。 メッセージには、挿入操作の種類を 1 つだけを含めることができます。

- 対象のテーブルに厳密に型指定されたデータの指定されたレコード セットを挿入する複数のレコードを挿入します。
- 複数のレコード挿入内の各レコードと呼ばれる省略可能な属性の値を指定できます**InlineValue**です。 指定する場合は、要素の値を上書きします。
- 一括挿入は、対象のテーブルにクエリ要素で指定された選択クエリによって返されるレコード セットを挿入します。 これは、それらの要素で指定された列のコンマ区切りリストを使用して行います。

#### <a name="xml-message"></a>XML メッセージ  

**複数のレコードの挿入**  
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

SQL アダプターによって実行します。`INSERT INTO TABLE_NAME (FIELD1_NAME, FIELD2_NAME, …)VALUES (value1, value2, …);`


**一括挿入**  
```
<Insert xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">
<COLUMN_NAMES>[COLUMN_list]</COLUMN_NAMES>
<QUERY>[SELECT_query]</QUERY>
</Insert>
```

SQL アダプターによって実行します。`INSERT INTO TABLE_NAME (COLUMN_list) SELECT_query;`

### <a name="insert-response"></a>応答を挿入します。
InsertResult 要素では、挿入された行の数が返されます。

#### <a name="xml-message"></a>XML メッセージ  

```
<InsertResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<InsertResult>[rows inserted]</InsertResult> 
</InsertResponse>
```

### <a name="select"></a>Select
SELECT クエリは、フィルター要素で指定する WHERE 句を使用して、対象テーブルで実行されます。 結果セットには、それらの要素で指定された列名のコンマ区切りリスト内の列が含まれています。

#### <a name="xml-message"></a>XML メッセージ  
```
<Select xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<COLUMN_NAMES>[COLUMN_list]</COLUMN_NAMES>   
<FILTER>WHERE_clause</FILTER> 
</Select>
```

SQL アダプターによって実行します。`SELECT COLUMN_list FROM TABLE_NAME WHERE WHERE_clause;`

### <a name="select-response"></a>応答を選択します。
SELECT クエリによって生成される結果セットです。

#### <a name="xml-message"></a>XML メッセージ  
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

### <a name="update"></a>Update
Where に一致する行フィルター要素で指定されている句は、レコード セットの指定した値に更新されます。 レコード セットで指定されている列のみが一致行ごとに更新されます。

#### <a name="xml-message"></a>XML メッセージ  
```
<Update xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<RECORDSET>     
<[FIELD1_NAME]>value1</[FIELD1_NAME]>     
<[FIELD2_NAME]>value2</[FIELD2_NAME]>       
…   
</RECORDSET>   
<FILTER>WHERE_clause</FILTER> </Update>
```

SQL アダプターによって実行します。`UPDATE [TABLE_NAME] SET [FIELD1_NAME] = value1, [FIELD2_NAME] = value2, … WHERE WHERE_clause;`

### <a name="update-response"></a>更新の応答
UpdateResult 要素では、更新された行の数が返されます。

#### <a name="xml-message"></a>XML メッセージ  
```
<UpdateResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<UpdateResult>[rows inserted]</UpdateResult> 
</UpdateResponse>
```

### <a name="delete"></a>DELETE
フィルター要素で指定された WHERE 句に一致する行が削除されます。

#### <a name="xml-message"></a>XML メッセージ 
```
<Delete xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<FILTER>WHERE_clause</FILTER> 
</Delete>
```

SQL アダプターによって実行します。`DELETE FROM [TABLE_NAME] WHERE WHERE_clause;`

### <a name="delete-response"></a>応答を削除します。
DeleteResult 要素では、削除された行の数が返されます。

#### <a name="xml-message"></a>XML メッセージ 
```
<DeleteResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<DeleteResult>[rows inserted]</DeleteResult> 
</DeleteResponse>
```
  
  | プレース ホルダーの値| Description |
  | --- | --- |
  | [バージョン] | メッセージのバージョン文字列です。例えば`http://Microsoft.LobServices.OracleDB/2007/03`|
  | [スキーマ] | Oracle の成果物のコレクション例えば`SCOTT`|
  | [TABLE_NAME] | テーブルの名前例えば`EMP`|
  | [FIELD1_NAME] | テーブルのフィールド名です。例えば`EMPNAME`|
  | [COLUMN_list] | 列のコンマ区切りの一覧例えば`NAME`|
  | [SELECT_query] | 一括挿入操作のクエリ要素で指定した SQL SELECT ステートメント例えば`SELECT * from MyTable`|
  | [WHERE_clause] | 操作を使用する SELECT ステートメントの WHERE_clause例えば`ID > 10`|
  
> [!IMPORTANT]
>  基本的なテーブルでの操作のビューのメッセージの構造と同じテーブルは、操作の名前空間は、テーブルではなく、ビューを指定します。:`<Insert xmlns ="[VERSION]/[SCHEMA]/``View``/[VIEW_NAME]">`です。  
  
## <a name="message-actions-for-basic-table-operations"></a>基本的なテーブル操作のメッセージ アクション  
 次の表は、メッセージ アクションで使用される、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]基本的なテーブルでの操作のテーブルです。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]メッセージ アクションで指定したテーブル名を使用して、操作の対象のテーブルを確認します。  
  
|操作|メッセージのアクション|例|  
|---------------|--------------------|-------------|  
|Insert|[バージョン]/[SCHEMA]/Table/[TABLE_NAME]/挿入|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert|  
|応答を挿入します。|[バージョン]/[SCHEMA]/Table/[TABLE_NAME]/挿入/応答|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert/response|  
|Select|[バージョン]/[SCHEMA]/Table/[TABLE_NAME] を選択/|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select|  
|応答を選択します。|[バージョン]/[SCHEMA]/Table/[TABLE_NAME] を選択/応答|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select/response|  
|Update|[バージョン]/[SCHEMA]/Table/[TABLE_NAME]/更新|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update|  
|更新の応答|[バージョン]/[SCHEMA]/Table/[TABLE_NAME]/更新/応答|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update/response|  
|DELETE|[バージョン]/[SCHEMA]/Table/[TABLE_NAME] を削除します|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete|  
|応答を削除します。|[バージョン]/[SCHEMA]/Table/[TABLE_NAME]/削除/応答|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete/response|  
  
 [バージョン]、メッセージのバージョン文字列を =たとえば、http://Microsoft.LobServices.OracleDB/2007/03 です。  
  
 [スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。  
  
 [TABLE_NAME] テーブルの名前を =たとえば、EMP です。  
  
> [!IMPORTANT]
>  ビューで操作のメッセージ アクションと同じでは、テーブルの"View"が"Table"; を置換する点を除いてたとえば、`http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/``View``/EMPVIEW/Insert`です。  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk Adapter 用 Oracle Database のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)