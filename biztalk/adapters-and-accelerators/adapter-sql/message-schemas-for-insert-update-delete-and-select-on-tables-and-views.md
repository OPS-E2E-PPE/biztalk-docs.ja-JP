---
title: Insert、Update、Delete のメッセージ スキーマとテーブルとビューで操作を選択します |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4fff9cd3-26c0-4d5c-8162-3fd7966a5020
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebff9c7996b853a41b11b5e2c082f66224ec04d3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368454"
---
# <a name="message-schemas-for-insert-update-delete-and-select-operations-on-tables-and-views"></a>メッセージ スキーマの挿入、更新、削除、およびテーブルとビューで操作を選択します。
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] Insert、Update、Delete、および Select 操作の各テーブルと SQL Server データベースのビューに表示されます。 これらの操作は、WHERE 句で修飾された適切な SQL ステートメントを実行します。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]これらの操作で厳密に型指定されたレコードとレコード セットを使用します。  
  
## <a name="message-structure-for-table-operations"></a>テーブル操作のメッセージの構造  
 次の表は、XML メッセージの構造によって公開されている基本的なテーブル操作のため、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL server データベース テーブル。 操作の対象テーブルでは、メッセージのアクションで指定され、ターゲットの名前空間にも表示されます。  
  
|操作|XML メッセージ|Description|SQL アダプターによって実行されます。|  
|---------------|-----------------|-----------------|---------------------------------|  
|Insert|`<Insert xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <Rows>     <[TABLE_NAME]>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </[TABLE_NAME]>   </Rows> </Insert>`|厳密に型指定されたデータの指定されたレコード セットをターゲット テーブルに挿入します。|`INSERT INTO TABLE_NAME (FIELD1_NAME, FIELD2_NAME, …) VALUES (value1, value2, …);`|  
|応答を挿入します。|`<InsertResponse xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <InsertResult>     <long>[Value]</long>   </InsertResult> </InsertResponse>`|挿入の応答メッセージには、長い形式のデータ型の配列が含まれています。 配列は、存在する場合に、挿入された行の id 値を格納します。 テーブル内に id 列がない場合、戻り値は NULL です。|--|  
|Select|すべてのレコードを選択します。<br /><br /> `<Select xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <Columns>*</COLUMNS>   <Query></Query> </Select>`<br /><br /> レコード セットの特定の列を選択します。<br /><br /> `<Select xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <Columns>[COLUMN_list]</COLUMNS>   <Query>where [WHERE_clause]</Query> </Select>`<br /><br /> 選択操作の一部としてレコードを更新しています。<br /><br /> `<Select xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <Columns>[COLUMN_list]</Columns>   <Query>where [WHERE_clause];UPDATE [TABLE_NAME] SET [FIELD1_NAME] = [value1] where [WHERE_clause]</Query> </Select>`|SELECT クエリは、要素で指定する WHERE 句を使用して、対象テーブルに対して実行されます。 結果セットにはで指定した列名のコンマ区切りリスト内の列が含まれています、\<列\>要素。<br /><br /> 値を指定する必要があります、\<列\>要素。 すべての列をテーブルまたはビュー内で取得する必要がある場合 * に指定する必要があります、\<列\>要素。 特定の列を取得する場合、列名をコンマで区切らし、テーブルまたはビューで定義されているのと同じ順序で指定する必要があります。<br /><br /> SELECT ステートメントに WHERE 句を含める必要があります。 削除するか WHERE 句を指定しない場合は、\<クエリ\>要素または空のままにします。<br /><br /> 選択操作を使用してレコードを更新することができます。 UPDATE ステートメントが配置されます、\<クエリ\>from、WHERE 句はセミコロンで区切られた SELECT 要求 XML の要素。 UPDATE ステートメントが SELECT ステートメントの結果セットの操作ではなくでことに注意してください。|すべてのレコードを選択します。<br /><br /> `SELECT * FROM [TABLE_NAME] WHERE [WHERE_clause];`<br /><br /> レコード セットの特定の列を選択します。<br /><br /> `SELECT [COLUMN_list] FROM [TABLE_NAME] WHERE [WHERE_clause];`<br /><br /> 選択操作の一部としてレコードを更新しています。<br /><br /> `SELECT [COLUMN_list] FROM [TABLE_NAME] WHERE [WHERE_clause]; UPDATE [TABLE_NAME] SET [FIELD1_NAME] = value1 [WHERE_clause];`|  
|応答を選択します。|`<SelectResponse  xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <SelectResult>     <[TABLE_NAME]>       <[FIELD1_NAME]>[value1]</[FIELD1_NAME]>       <[FIELD2_NAME]>[value2]</[FIELD2_NAME]>       …     </[TABLE_NAME]>   </SelectResult> <SelectResponse>`|SELECT クエリによって生成される厳密に型指定された結果セット。|--|  
|更新|`<SelectResponse  xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <SelectResult>     <[TABLE_NAME]>       <[FIELD1_NAME]>[value1]</[FIELD1_NAME]>       <[FIELD2_NAME]>[value2]</[FIELD2_NAME]>       …     </[TABLE_NAME]>   </SelectResult> </SelectResponse>`<br /><br /> `<Update xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <Rows>     <RowPair>       <After>         <[FIELD1_NAME]>[value1]</[FIELD1_NAME]>         <[FIELD2_NAME]>[value2]</[FIELD2_NAME]>         …       </After>       <Before>         <[FIELD1_NAME]>[value3]</[FIELD1_NAME]>         <[FIELD2_NAME]>[value4]</[FIELD2_NAME]>         …       </Before>     </RowPair>   </Rows> </Update>`|レコードのペアの配列を入力として受け取ります。 レコードの各ペアは、厳密に型指定された 2 つのレコードのコレクションです。<br /><br /> 最初のレコード (で、`<After>`要素) を更新する必要がある新しい値に対応しています。<br /><br /> 2 つ目のレコード (で、 `<Before>`)、行の古い値に対応しています。|`UPDATE [TABLE_NAME] SET [FIELD1_NAME] = value1, [FIELD2_NAME] = value2, … WHERE [FIELD1_NAME] = value3, [FIELD2_NAME] = value4, …;`|  
|更新の応答|`<UpdateResponse xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <UpdateResult>[rows updated]</UpdateResult> </UpdateResponse>`|更新された行の数が返される、 **UpdateResult**要素。|--|  
|DELETE|`<Delete xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <Rows>     <[TABLE_NAME]>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </[TABLE_NAME]>   </Rows> </Delete>`|--|`DELETE FROM [TABLE_NAME] WHERE [FIELD1_NAME] = value1, [FIELD2_NAME] = value2, …;`|  
|応答を削除します。|`<DeleteResponse xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <DeleteResult>[rows deleted]</DeleteResult> </DeleteResponse>`|削除された行の数が返される、 **DeleteResult**要素。|--|  
  
 [バージョン] = メッセージ バージョン文字列。たとえば、 http://schemas.microsoft.com/Sql/2008/05 します。  
  
 [スキーマ] コレクションの SQL Server のアイテム、=たとえば、dbo です。  
  
 [TABLE_NAME]; テーブルの名前を =たとえば、従業員です。  
  
 [FIELD1_NAME] テーブルのフィールド名を =たとえば、名前を付けます。  
  
 [COLUMN_list] 列のコンマ区切りの一覧を =たとえば、名前、年齢を指定します。  
  
 [SELECT_query] = 一括挿入操作の QUERY 要素で指定された SQL SELECT ステートメントたとえば、"選択 * from MyTable"  
  
 [WHERE_clause] 操作を使用する SELECT ステートメントの WHERE_clause を =たとえば、> 10 を ID です。  
  
> [!IMPORTANT]
>  ビューに対する基本的なテーブル操作のメッセージの構造と同じテーブルにする点を除いて、ビューには、テーブルが置き換えられます:`Insert xmlns="[VERSION]/ViewOp/[SCHEMA]/[VIEW_NAME]"`します。  
  
## <a name="message-actions-for-basic-table-operations"></a>基本的なテーブル操作のメッセージのアクション  
 次の表は、メッセージのアクションで使用される、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]テーブルに対する基本的なテーブルの操作。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]操作の対象のテーブルを確認するメッセージのアクションで指定されたテーブル名を使用します。  
  
|操作|メッセージのアクション|例|  
|---------------|--------------------|-------------|  
|Insert|TableOp/挿入/[スキーマ]/[TABLE_NAME]|TableOp/挿入/dbo/従業員|  
|応答を挿入します。|TableOp/挿入/[スキーマ]/[TABLE_NAME]/応答|TableOp/挿入/dbo/従業員/応答|  
|Select|TableOp と選択/[スキーマ]/[TABLE_NAME]|TableOp/選択/dbo/従業員|  
|応答を選択します。|TableOp と選択/[スキーマ]/[TABLE_NAME]/応答|TableOp/Select/dbo/Employee/response|  
|更新|TableOp/更新/[スキーマ]/[TABLE_NAME]|TableOp/Update/dbo/Employee|  
|更新の応答|TableOp/更新/[スキーマ]/[TABLE_NAME]/応答|TableOp/Update/dbo/Employee/response|  
|DELETE|TableOp/削除/[スキーマ]/[TABLE_NAME]|TableOp/Delete/dbo/Employee|  
|応答を削除します。|TableOp/削除/[スキーマ]/[TABLE_NAME]/応答|TableOp/Delete/dbo/Employee/response|  
  
 [スキーマ] コレクションの SQL Server のアイテム、=たとえば、dbo です。  
  
 [TABLE_NAME]; テーブルの名前を =たとえば、従業員です。  
  
> [!IMPORTANT]
>  ビューで操作のメッセージのアクションとテーブルを"ViewOp"置換"TableOp";たとえば、`ViewOp``/Insert/dbo/Employee_View`します。  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk adapter for SQL Server のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)