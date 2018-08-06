---
title: Insert、Update、Delete のメッセージ スキーマおよびテーブルおよびビューの操作の選択 |Microsoft ドキュメント
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
ms.openlocfilehash: 73270b3d096a8d72de5b339835737cc74d264c9c
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
ms.locfileid: "25967216"
---
# <a name="message-schemas-for-insert-update-delete-and-select-operations-on-tables-and-views"></a>メッセージ スキーマの挿入、更新、削除、およびテーブルおよびビューの操作の選択
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] Insert、Update、Delete、および Select 操作の各テーブルと、SQL Server データベースのビューを表示します。 これらの操作は、WHERE 句で修飾された適切な SQL ステートメントを実行します。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]これらの操作で厳密に型指定されたレコードとレコード セットを使用します。  
  
## <a name="message-structure-for-table-operations"></a>テーブル操作に対するメッセージの構造  
 次の表は、XML メッセージの構造によって公開されている基本的なテーブル操作のため、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL server データベース テーブルです。 操作の対象テーブルでは、メッセージのアクションで指定され、ターゲットの名前空間にも表示されます。  
  
|操作|XML メッセージ|Description|SQL アダプターによって実行されます。|  
|---------------|-----------------|-----------------|---------------------------------|  
|Insert|`<Insert xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <Rows>     <[TABLE_NAME]>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </[TABLE_NAME]>   </Rows> </Insert>`|厳密に型指定されたデータの指定されたレコード セットは、対象のテーブルに挿入します。|`INSERT INTO TABLE_NAME (FIELD1_NAME, FIELD2_NAME, …) VALUES (value1, value2, …);`|  
|応答を挿入します。|`<InsertResponse xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <InsertResult>     <long>[Value]</long>   </InsertResult> </InsertResponse>`|挿入の応答メッセージには、長い形式のデータ型の配列が含まれています。 配列は、存在する場合に、挿入された行の id 値を格納します。 テーブル内に id 列がない場合、戻り値は NULL です。|--|  
|Select|すべてのレコードを選択します。<br /><br /> `<Select xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <Columns>*</COLUMNS>   <Query></Query> </Select>`<br /><br /> レコード セットの特定の列の選択。<br /><br /> `<Select xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <Columns>[COLUMN_list]</COLUMNS>   <Query>where [WHERE_clause]</Query> </Select>`<br /><br /> 選択操作の一環として、レコードを更新しています。<br /><br /> `<Select xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <Columns>[COLUMN_list]</Columns>   <Query>where [WHERE_clause];UPDATE [TABLE_NAME] SET [FIELD1_NAME] = [value1] where [WHERE_clause]</Query> </Select>`|SELECT クエリは、要素で指定する WHERE 句を使用して、対象テーブルで実行されます。 結果セットにはで指定された列名のコンマ区切りリスト内の列が含まれています、\<列\>要素。<br /><br /> 値を指定する必須では、\<列\>要素。 すべての列をテーブルまたはビュー内で取得する必要がある場合 * で指定する必要があります、\<列\>要素。 特定の列を取得する場合、列の名前をコンマで区切らしてテーブルまたはビューで定義されているように同じ順序で指定する必要があります。<br /><br /> 必須では、SELECT ステートメントで WHERE 句を指定します。 WHERE 句を指定しない場合は削除するか、\<クエリ\>要素または空のままにします。<br /><br /> 選択操作を使用してレコードを更新することができます。 UPDATE ステートメントを配置している、\<クエリ\>from、WHERE 句では、セミコロンで区切られた SELECT 要求 XML の要素。 SELECT ステートメントの結果セットの操作ではなく、UPDATE ステートメントでは注意してください。|すべてのレコードを選択します。<br /><br /> `SELECT * FROM [TABLE_NAME] WHERE [WHERE_clause];`<br /><br /> レコード セットの特定の列の選択。<br /><br /> `SELECT [COLUMN_list] FROM [TABLE_NAME] WHERE [WHERE_clause];`<br /><br /> 選択操作の一環として、レコードを更新しています。<br /><br /> `SELECT [COLUMN_list] FROM [TABLE_NAME] WHERE [WHERE_clause]; UPDATE [TABLE_NAME] SET [FIELD1_NAME] = value1 [WHERE_clause];`|  
|応答を選択します。|`<SelectResponse  xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <SelectResult>     <[TABLE_NAME]>       <[FIELD1_NAME]>[value1]</[FIELD1_NAME]>       <[FIELD2_NAME]>[value2]</[FIELD2_NAME]>       …     </[TABLE_NAME]>   </SelectResult> <SelectResponse>`|SELECT クエリによって生成される厳密に型指定された結果セットです。|--|  
|Update|`<SelectResponse  xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <SelectResult>     <[TABLE_NAME]>       <[FIELD1_NAME]>[value1]</[FIELD1_NAME]>       <[FIELD2_NAME]>[value2]</[FIELD2_NAME]>       …     </[TABLE_NAME]>   </SelectResult> </SelectResponse>`<br /><br /> `<Update xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <Rows>     <RowPair>       <After>         <[FIELD1_NAME]>[value1]</[FIELD1_NAME]>         <[FIELD2_NAME]>[value2]</[FIELD2_NAME]>         …       </After>       <Before>         <[FIELD1_NAME]>[value3]</[FIELD1_NAME]>         <[FIELD2_NAME]>[value4]</[FIELD2_NAME]>         …       </Before>     </RowPair>   </Rows> </Update>`|入力としてレコードのペアの配列を取得します。 各レコードのペアは、厳密に型指定された 2 つのレコードのコレクションを示します。<br /><br /> まず記録 (で、`<After>`要素) を更新する必要がある新しい値に対応しています。<br /><br /> 2 番目のレコード (で、 `<Before>`)、行の古い値に対応しています。|`UPDATE [TABLE_NAME] SET [FIELD1_NAME] = value1, [FIELD2_NAME] = value2, … WHERE [FIELD1_NAME] = value3, [FIELD2_NAME] = value4, …;`|  
|更新の応答|`<UpdateResponse xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <UpdateResult>[rows updated]</UpdateResult> </UpdateResponse>`|更新された行の数が返される、 **UpdateResult**要素。|--|  
|Del|`<Delete xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <Rows>     <[TABLE_NAME]>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </[TABLE_NAME]>   </Rows> </Delete>`|--|`DELETE FROM [TABLE_NAME] WHERE [FIELD1_NAME] = value1, [FIELD2_NAME] = value2, …;`|  
|応答を削除します。|`<DeleteResponse xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <DeleteResult>[rows deleted]</DeleteResult> </DeleteResponse>`|削除された行の数が返される、 **DeleteResult**要素。|--|  
  
 [バージョン]、メッセージのバージョン文字列を =たとえば http://schemas.microsoft.com/Sql/2008/05 です。  
  
 [スキーマ]; SQL Server のコレクション アイテムを =たとえば、dbo します。  
  
 [TABLE_NAME] テーブルの名前を =たとえば、従業員です。  
  
 [FIELD1_NAME] = テーブルのフィールド名です。たとえば、名前を付けます。  
  
 [COLUMN_list] 列のコンマ区切りの一覧を =たとえば、名前、年齢を指定します。  
  
 [SELECT_query]、一括挿入操作のクエリ要素で指定した SQL SELECT ステートメントを =たとえば、"選択 * から MyTable"  
  
 [WHERE_clause] 操作を使用する SELECT ステートメントの WHERE_clause を =たとえば、> 10 を ID です。  
  
> [!IMPORTANT]
>  基本的なテーブルでの操作のビューのメッセージの構造と同じではテーブルで、ビュー、テーブルで置き換えられる点を除いて:`Insert xmlns="[VERSION]/ViewOp/[SCHEMA]/[VIEW_NAME]"`です。  
  
## <a name="message-actions-for-basic-table-operations"></a>基本的なテーブル操作のメッセージ アクション  
 次の表は、メッセージ アクションで使用される、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]基本的なテーブルでの操作のテーブルです。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]メッセージ アクションで指定したテーブル名を使用して、操作の対象のテーブルを確認します。  
  
|操作|メッセージのアクション|例|  
|---------------|--------------------|-------------|  
|Insert|TableOp/挿入/[スキーマ]/[TABLE_NAME]|TableOp/Insert/dbo/Employee|  
|応答を挿入します。|TableOp/挿入/[スキーマ]/[TABLE_NAME]/応答|TableOp/Insert/dbo/Employee/response|  
|Select|TableOp と選択/[スキーマ]/[TABLE_NAME]|TableOp/Select/dbo/Employee|  
|応答を選択します。|TableOp と選択/[スキーマ]/[TABLE_NAME]/応答|TableOp/Select/dbo/Employee/response|  
|Update|TableOp/更新/[スキーマ]/[TABLE_NAME]|TableOp/Update/dbo/Employee|  
|更新の応答|TableOp/更新/[スキーマ]/[TABLE_NAME]/応答|TableOp/Update/dbo/Employee/response|  
|Del|TableOp/削除/[スキーマ]/[TABLE_NAME]|TableOp/Delete/dbo/Employee|  
|応答を削除します。|TableOp/削除/[スキーマ]/[TABLE_NAME]/応答|TableOp/Delete/dbo/Employee/response|  
  
 [スキーマ]; SQL Server のコレクション アイテムを =たとえば、dbo します。  
  
 [TABLE_NAME] テーブルの名前を =たとえば、従業員です。  
  
> [!IMPORTANT]
>  ビューで操作のメッセージ アクションと同じでは、テーブルの"ViewOp"が"TableOp;"を置換する点を除いてたとえば、`ViewOp``/Insert/dbo/Employee_View`です。  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk Adapter for SQL Server のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)