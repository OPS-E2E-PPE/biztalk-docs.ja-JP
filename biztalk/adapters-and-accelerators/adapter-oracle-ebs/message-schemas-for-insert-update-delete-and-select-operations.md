---
title: Insert、Update、Delete のメッセージ スキーマおよび操作の選択 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5b8de271-67db-4279-8f95-0b4dd92fa3c4
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15bb515eee9a052852952f0ec245f8c954953a9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218234"
---
# <a name="message-schemas-for-insert-update-delete-and-select-operations"></a>メッセージ スキーマの挿入、更新、削除、および操作の選択
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]サーフェスの基本的な Insert、Update、Delete、および Oracle E-business Suite では、各インターフェイス テーブルと、基になるデータベース内の各テーブルの操作を選択します。 アダプターでは、Oracle E-business Suite では、各インターフェイス ビューと基になるデータベース内の各ビューの Select 操作も明らかです。 これらの操作は、WHERE 句で修飾された適切な SQL ステートメントを実行します。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]これらの操作で厳密に型指定されたレコードとレコード セットを使用します。  
  
## <a name="message-structure-for-basic-operations"></a>基本的な操作のメッセージの構造  
 次の表は、XML メッセージの構造によって公開されている基本的な操作、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite のインターフェイス テーブルやビューのインターフェイスと、基になるデータベース テーブルとビュー。 操作の対象のオブジェクトは、メッセージのアクションで指定され、ターゲットの名前空間にも表示されます。  
  
> [!NOTE]
>  表の後に属性の説明を参照してください。  
  
|操作|XML メッセージ|Description|SQL アダプターによって実行されます。|  
|---------------|-----------------|-----------------|---------------------------------|  
|Insert|`<Insert xmlns="[VERSION]/InterfaceTables/[SCHEMA]/[APP_NAME]/[INTERFACETABLE_NAME]">   <RECORDSET>     <InsertRecord>       <[FIELD1_NAME] InlineValue="value">[value1]</[FIELD1_NAME]>       <[FIELD2_NAME] InlineValue="value">[value2]</[FIELD2_NAME]>       …     </InsertRecord>   </RECORDSET> </Insert>`|値、 **InlineValue**属性に指定する場合は、要素の値を上書きします。|`INSERT INTO TABLE_NAME (FIELD1_NAME, FIELD2_NAME, …) VALUES (value1, value2, …);`|  
|応答を挿入します。|`<InsertResponse xmlns="[VERSION]/InterfaceTables/[SCHEMA]/[APP_NAME]/[INTERFACETABLE_NAME]">   <InsertResult>[rows inserted]</InsertResult> </InsertResponse>`|挿入された行の数が返されます、 **InsertResult**要素。|--|  
|Select|`<Select xmlns="[VERSION]/InterfaceTables/[SCHEMA]/[APP_NAME]/[INTERFACETABLE_NAME]">   <COLUMN_NAMES>[COLUMN_list]</COLUMN_NAMES>   <FILTER>WHERE_clause</FILTER> </Select>`|SELECT クエリは、フィルター要素で指定する WHERE 句を使用して、対象テーブルで実行されます。 結果セットにはで指定された列名のコンマ区切りリスト内の列が含まれています、**それら**要素。<br /><br /> **重要:** インターフェイス ビューとデータベースのビューに適用できる唯一の操作です。|`SELECT COLUMN_list FROM TABLE_NAME WHERE WHERE_clause;`|  
|応答を選択します。|`<SelectResponse  xmlns="[VERSION]/InterfaceTables/[SCHEMA]/[APP_NAME]/[INTERFACETABLE_NAME]">   <SelectResult>     <SelectRecord>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </SelectRecord>   </SelectResult> </SelectResponse>`|SELECT クエリによって生成される結果セットです。|--|  
|Update|`<Update xmlns="[VERSION]/InterfaceTables/[SCHEMA]/[APP_NAME]/[INTERFACETABLE_NAME]">   <RECORDSET>     <[FIELD1_NAME]>value1</[FIELD1_NAME]>     <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …   </RECORDSET>   <FILTER>WHERE_clause</FILTER> </Update>`|Where に一致する行句で指定された、**フィルター**要素で指定した値に更新が、 **RECORDSET**です。 指定されている列のみ、 **RECORDSET**要素が一致行ごとに更新されます。|`UPDATE [TABLE_NAME] SET [FIELD1_NAME] = value1, [FIELD2_NAME] = value2, … WHERE WHERE_clause;`|  
|更新の応答|`<UpdateResponse xmlns="[VERSION]/InterfaceTables/[SCHEMA]/[APP_NAME]/[INTERFACETABLE_NAME]">   <UpdateResult>[rows inserted]</UpdateResult> </UpdateResponse>`|更新された行の数が返される、 **UpdateResult**要素。|--|  
|DELETE|`<Delete xmlns="[VERSION]/InterfaceTables/[SCHEMA]/[APP_NAME]/[INTERFACETABLE_NAME]">   <FILTER>WHERE_clause</FILTER> </Delete>`|指定された WHERE 句に一致する行、**フィルター**要素が削除されます。|`DELETE FROM [TABLE_NAME] WHERE WHERE_clause;`|  
|応答を削除します。|`<DeleteResponse xmlns="[VERSION]/InterfaceTables/[SCHEMA]/[APP_NAME]/[INTERFACETABLE_NAME]">   <DeleteResult>[rows deleted]</DeleteResult> </DeleteResponse>`|削除された行の数が返される、 **DeleteResult**要素。|--|  
  
 属性の説明:  
  
 [バージョン]、メッセージのバージョン文字列を =たとえば、http://schemas.microsoft.com/OracleEBS/2008/05 です。  
  
 [スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。  
  
 [APP_NAME] アプリケーションの短い名前を = です。  
  
 [INTERFACETABLE_NAME] インターフェイス テーブルの名前を = です。  
  
 [FIELD1_NAME] テーブルのフィールド名を = です。  
  
 [COLUMN_list] 列のコンマ区切りの一覧を = です。  
  
 [WHERE_clause] 操作を使用する SELECT ステートメントの WHERE_clause を =たとえば、> 10 を ID です。  
  
> [!IMPORTANT]
>  インターフェイス ビュー、データベース テーブル、およびデータベースのビューでは、基本的な操作のメッセージの構造と同じインターフェイス テーブルは、操作の名前空間は、インターフェイス ビュー、データベース テーブルまたはデータベース ビューではなく、インターフェイスを指定します。テーブルです。  
  
## <a name="message-actions-for-basic-operations"></a>基本的な操作のメッセージの動作  
 次の表は、メッセージのアクションを[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]インターフェイス テーブルと Oracle E-business Suite のインターフェイス ビューのテーブルおよび基になるデータベース内のビューでは、基本的な操作を使用します。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]インターフェイス テーブル、インターフェイスの表示、データベース テーブル、またはメッセージのアクションに指定されたデータベースのビューを使用して、操作の対象を決定します。  
  
> [!NOTE]
>  表の後に、エンティティの説明を参照してください。  
  
|操作|メッセージのアクション|例|  
|---------------|--------------------|-------------|  
|Insert|**アプリケーション**: InterfaceTables/挿入/[SHORT_NAME]/[APP_NAME]/[TABLE_NAME]<br /><br /> **データベース**: テーブル/挿入/[スキーマ]/[TABLE_NAME]|**アプリケーション**: InterfaceTables/挿入/SQLGL/GL/GL_ALLOC_HISTORY<br /><br /> **データベース**: テーブル/挿入/GL/GL_ALLOC_HISTORY|  
|応答を挿入します。|**アプリケーション**: InterfaceTables/挿入/[SHORT_NAME]/[APP_NAME]/[TABLE_NAME]/応答<br /><br /> **データベース**: テーブル/挿入/[スキーマ]/[TABLE_NAME]/応答|**アプリケーション**: InterfaceTables/挿入/SQLGL/GL/GL_ALLOC_HISTORY/応答<br /><br /> **データベース**: テーブル/挿入/GL/GL_ALLOC_HISTORY/応答|  
|Select|**アプリケーション**: InterfaceTables [と選択]/[SHORT_NAME]/[APP_NAME]/[TABLE_NAME]<br /><br /> **データベース**: [テーブルと選択]/[スキーマ]/[TABLE_NAME]|**アプリケーション**: InterfaceTables/選択/SQLGL/GL/GL_ALLOC_HISTORY<br /><br /> **データベース**: テーブル/選択/GL/GL_ALLOC_HISTORY|  
|応答を選択します。|**アプリケーション**: InterfaceTables [と選択]/[SHORT_NAME]/[APP_NAME]/[TABLE_NAME]/応答<br /><br /> **データベース**: [テーブルと選択]/[スキーマ]/[TABLE_NAME]/応答|**アプリケーション**: InterfaceTables/選択/SQLGL/GL/GL_ALLOC_HISTORY/応答<br /><br /> **データベース**: テーブル/選択/GL/GL_ALLOC_HISTORY/応答|  
|Update|**アプリケーション**: InterfaceTables/更新/[SHORT_NAME]/[APP_NAME]/[TABLE_NAME]<br /><br /> **データベース**: テーブル/更新/[スキーマ]/[TABLE_NAME]|**アプリケーション**: InterfaceTables/更新/SQLGL/GL/GL_ALLOC_HISTORY<br /><br /> **データベース**: テーブル/更新/GL/GL_ALLOC_HISTORY|  
|更新の応答|**アプリケーション**: InterfaceTables/更新/[SHORT_NAME]/[APP_NAME]/[TABLE_NAME]/応答<br /><br /> **データベース**: テーブル/更新/[スキーマ]/[TABLE_NAME]/応答|**アプリケーション**: InterfaceTables/更新/SQLGL/GL/GL_ALLOC_HISTORY/応答<br /><br /> **データベース**: テーブル/更新/GL/GL_ALLOC_HISTORY/応答|  
|DELETE|**アプリケーション**: InterfaceTables/削除/[SHORT_NAME]/[APP_NAME]/[TABLE_NAME]<br /><br /> **データベース**: テーブル/削除/[スキーマ]/[TABLE_NAME]|**アプリケーション**: InterfaceTables/削除/SQLGL/GL/GL_ALLOC_HISTORY<br /><br /> **データベース**: テーブル/削除/GL/GL_ALLOC_HISTORY|  
|応答を削除します。|**アプリケーション**: InterfaceTables/削除/[SHORT_NAME]/[APP_NAME]/[TABLE_NAME]/応答<br /><br /> **データベース**: テーブル/削除/[スキーマ]/[TABLE_NAME]/応答|**アプリケーション**: InterfaceTables/削除/SQLGL/GL/GL_ALLOC_HISTORY/応答<br /><br /> **データベース**: テーブル/削除/GL/GL_ALLOC_HISTORY/応答|  
  
 エンティティの説明  
  
-   [スキーマ] - Oracle のコレクション アイテム (たとえば、GL)。  
  
-   [TABLE_NAME] - テーブル (たとえば、GL_ALLOC_HISTORY) の名前。  
  
> [!IMPORTANT]
>  インターフェイス ビューの Select 操作のメッセージ アクションと同じでは、インターフェイス テーブルの"InterfaceViews"が"InterfaceTables"を置換する点を除いて 同様に、データベース ビューの Select 操作のメッセージ アクションと同じでは、データベース テーブルの「ビュー」が"Tables"を置換する点を除いて  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk Adapter for Oracle E-business Suite のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)