---
title: BizTalk Adapter Pack での SQL アダプターのメタデータ ノード Id |Microsoft Docs
description: メタデータ、検索、取得のタイプのノード、および SQL Server のアダプターの BizTalk アダプター パック (BAP) で公開されている SQL コンポーネントで使用される Id
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8601a328-5380-4577-a121-c926e0fd3140
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80dd7d58f220f7c7fdf8c70851373311999927f1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022624"
---
# <a name="node-types-and-ids-for-the-sql-server-adapter"></a>ノードの種類と、SQL Server のアダプターの Id

## <a name="metadata-node-ids"></a>メタデータ ノード Id
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]サーフェス SQL Server データベースの成果物の階層的にします。 次の表は、ノードの種類と SQL Server のデータベース成果物のノード Id を[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サーフェス。 ノード ID で使用されているノードの絶対パス、 **IMetadataRetrievalContractBrowse**、**検索**、および**GetMetadata**メソッド。  


| 成果物の表示名  |     ノードの種類      |                        ノード ID                         |                    例                     |                                                                                                                                                    説明                                                                                                                                                    |
|------------------------|--------------------|--------------------------------------------------------|------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|           --           |      カテゴリ      |                           /                            |                       /                        | [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] ルート ノードです。 すべての第 1 レベル ノードを返しますこれには、ExecuteNonQuery、ExecuteReader、executescalar 操作のノードと出力方向の操作では、すべてのスキーマ ノードと受信操作のポーリング操作のノードが含まれます。 |
|    ExecuteNonQuery     | 送信操作 |               GenericOp/ExecuteNonQuery                |           GenericOp/ExecuteNonQuery            |                                                                                                                  ExecuteNonQuery 操作のノードです。 ExecuteNonQuery 操作の WSDL を返します。                                                                                                                  |
|     ExecuteReader      | 送信操作 |                GenericOp/ExecuteReader                 |            GenericOp/ExecuteReader             |                                                                                                                    ExecuteReader 操作のノードです。 ExecuteReader 操作の WSDL を返します。                                                                                                                    |
|     ExecuteScalar      | 送信操作 |                GenericOp/ExecuteScalar                 |            GenericOp/ExecuteScalar             |                                                                                                                    ExecuteScalar 操作のノードです。 ExecuteScalar 操作の WSDL を返します。                                                                                                                    |
|        ポーリング         | 受信操作  |                        ポーリング                         |                    ポーリング                     |                                                                                                                          ポーリング操作のノードです。 ポーリング操作の WSDL を返します。                                                                                                                          |
|      Notification      | 受信操作  |                      Notification                      |                  Notification                  |                                                                                                                     通知操作のノードです。 通知操作の WSDL を返します。                                                                                                                     |
|       手順       |      カテゴリ      |                      プロシージャ/                       |                  プロシージャ/                   |                                                                                                                     スキーマのプロシージャのノードです。 指定したスキーマのすべてのプロシージャを返します。                                                                                                                      |
|     [DB_PROCEDURE]     | 送信操作 |         プロシージャ/[DB_SCHEMA]/[Procedure_Name]         |         プロシージャ/dbo/ADD_EMP_DETAILS          |                                                                                                                           プロシージャのノード。 指定されたプロシージャの WSDL を返します。                                                                                                                           |
|         テーブル         |      カテゴリ      |                        テーブル/                         |                    テーブル/                     |                                                                                                                       スキーマ テーブルのノード。 指定したスキーマのすべてのテーブル ノードを返します。                                                                                                                       |
|       [DB_TABLE]       |      カテゴリ      |                           -                            |                       -                        |                   テーブルのノードです。 操作のすべてのノード (Insert、Select、Update、Delete、およびセット)、指定したテーブルを返します。<br /><br /> 設定操作が次のデータ型のいずれかの列を含むテーブルに対してのみ返されます。 varchar (max)、nvarchar (max) または varbinary (max)。                   |
|         Insert         | 送信操作 |         TableOp/挿入/[DB_SCHEMA]/[DB_TABLE]          |          TableOp/挿入/dbo/従業員           |                                                                                                            テーブルな挿入操作のノード。 指定されたテーブルの挿入操作の WSDL を返します。                                                                                                            |
|         Select         | 送信操作 |         TableOp と選択/[DB_SCHEMA]/[DB_TABLE]          |          TableOp/選択/dbo/従業員           |                                                                                                            テーブルの選択操作のノードです。 指定されたテーブルの選択操作の WSDL を返します。                                                                                                            |
|         更新         | 送信操作 |         TableOp/更新/[DB_SCHEMA]/[DB_TABLE]          |          TableOp/Update/dbo/Employee           |                                                                                                            テーブル更新操作のノード。 指定されたテーブルの更新操作の WSDL を返します。                                                                                                            |
|         DELETE         | 送信操作 |         TableOp/削除/[DB_SCHEMA]/[DB_TABLE]          |          TableOp/Delete/dbo/Employee           |                                                                                                            テーブル操作ノードを削除します。 指定されたテーブルの削除操作の WSDL を返します。                                                                                                            |
|    [COLUMN_NAME] の設定します。    | 送信操作 | TableOp/WriteText/[DB_SCHEMA]/[DB_TABLE]/[COLUMN_NAME] | TableOp/WriteText/dbo/従業員/Job_Description |                                          テーブルなセット操作のノード。 テーブル内の指定された列の設定操作の WSDL を返します。 (テーブルには、次のデータ型のいずれかの列が含まれている場合のみ表示されます: (Max)、nvarchar (max) または Varbinary(Max)) します。                                           |
|         ビュー          |      カテゴリ      |                         ビュー/                         |                     ビュー/                     |                                                                                                                        スキーマ ビュー ノード。 指定したスキーマのすべてのビューのノードを返します。                                                                                                                        |
|       [DB_VIEW]        |      カテゴリ      |                           -                            |                       -                        |                                                                                                        ビューのノードです。 操作のすべてのノード (Insert、Select、Update、および削除)、指定されたビューを返します。                                                                                                        |
|         Insert         | 送信操作 |          ViewOp/挿入/[DB_SCHEMA]/[DB_VIEW]           |        ViewOp/挿入/dbo/Employee_View         |                                                                                                             ノードの挿入 操作を表示します。 指定されたビューの挿入操作の WSDL を返します。                                                                                                             |
|         Select         | 送信操作 |          ViewOp と選択/[DB_SCHEMA]/[DB_VIEW]           |        ViewOp/選択/dbo/Employee_View         |                                                                                                             ビューの選択操作のノード。 指定されたビューの選択操作の WSDL を返します。                                                                                                             |
|         更新         | 送信操作 |          ViewOp/更新/[DB_SCHEMA]/[DB_VIEW]           |        ViewOp/更新/dbo/Employee_View         |                                                                                                             更新操作のノードを表示します。 指定されたビューの更新操作の WSDL を返します。                                                                                                             |
|         DELETE         | 送信操作 |          ViewOp/削除/[DB_SCHEMA]/[DB_VIEW]           |        ViewOp/削除/dbo/Employee_View         |                                                                                                             削除操作のノードを表示します。 指定されたビューの削除操作の WSDL を返します。                                                                                                             |
|    スカラー関数    |      カテゴリ      |                    ScalarFunctions/                    |                ScalarFunctions/                |                                                                                                               スカラー関数ノードのスキーマです。 指定したスキーマのすべてのスカラー関数を返します。                                                                                                                |
|   [DB_SCLR_FUNCTION]   | 送信操作 |     ScalarFunction/[DB_SCHEMA]/[DB_SCLR_FUNCTION]      |         ScalarFunction/dbo/GET_EMP_ID          |                                                                                                                     スカラー関数ノードです。 指定したスカラー関数の WSDL を返します。                                                                                                                     |
| テーブル値関数 |      カテゴリ      |                    TableFunctions/                     |                TableFunctions/                 |                                                                                                         テーブル値関数ノードのスキーマ。 指定したスキーマのすべてのテーブル値関数を返します。                                                                                                          |
|   [DB_TBL_FUNCTION]    | 送信操作 |      しません/[DB_SCHEMA]/[DB_TBL_FUNCTION]       |         しません/dbo/TVF_EMPLOYEE         |                                                                                                               テーブル値関数ノード。 指定したテーブル値関数の WSDL を返します。                                                                                                               |

 [DB_SCHEMA] コレクションの SQL Server のアイテム、=たとえば、dbo です。  

 [DB_TABLE]、SQL Server テーブルの名前を =たとえば、従業員です。  

 [DB_VIEW]; SQL Server のビューの名前を =たとえば、Employee_View です。  

 [DB_PROCEDURE]、SQL Server のストアド プロシージャの名前を =たとえば、ADD_EMP_DETAILS です。  

 [DB_SCLR_FUNCTION]; SQL Server スカラー関数の名前を =たとえば、GET_EMP_ID です。  

 [DB_TBL_FUNCTION]、SQL Server テーブル値関数の名前を =たとえば、TVF_EMPLOYEE です。  

## <a name="metadata-search-and-node-ids"></a>メタデータの検索とノードの Id  
 メタデータの検索は、強力な機能、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]サーフェスの一部としてその**MetadataRetrievalContract**インターフェイス。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]この機能を使用して、次の SQL Server のアイテムに対する検索をサポートします。 メタデータの検索スコープは、検索操作を実行するノードのすぐ下にあるレベルに限定されます。 たとえば、スカラー関数を検索するにする必要があります 検索/スカラー関数/[Schema] です。 再帰的な検索がサポートされていません。  

|成果物|ノード ID|返されるノードの型|説明|  
|--------------|-------------|------------------------|-----------------|  
|/(つまり、ルート ノード)|/|カテゴリ|検索式に一致するすべてのスキーマ ノードを返します。|  
|[DB_PROCEDURE]|/Procedure/[DB_SCHEMA]|送信操作|検索式に一致する指定したスキーマには、プロシージャのすべてのノードを返します。|  
|[DB_TABLE]|/Table/[DB_SCHEMA]|カテゴリ|検索式に一致する指定したスキーマには、すべてのテーブル ノードを返します。|  
|[DB_VIEW]|/View/[DB_SCHEMA]|カテゴリ|検索式に一致する指定されたスキーマ ビューのすべてのノードを返します。|  
|[DB_SCLR_FUNCTION]|/ScalarFunction/[DB_SCHEMA]|送信操作|検索式に一致する指定したスキーマには、スカラー関数のすべてのノードを返します。|  
|[DB_TBL_FUNCTION]|/TableFunction/[DB_SCHEMA]|送信操作|検索式に一致する指定されたスキーマでテーブル値関数のすべてのノードを返します。|  

 [DB_SCHEMA] コレクションの SQL Server のアイテム、=たとえば、dbo です。  

 [DB_TABLE]、SQL Server テーブルの名前を =たとえば、従業員です。  

 [DB_VIEW]; SQL Server のビューの名前を =たとえば、Employee_View です。  

 [DB_PROCEDURE]、SQL Server プロシージャの名前を =たとえば、ADD_EMP_DETAILS です。  

 [DB_SCLR_FUNCTION]; SQL Server スカラー関数の名前を =たとえば、GET_EMP_ID です。  

 [DB_TBL_FUNCTION]、SQL Server テーブル値関数の名前を =たとえば、TVF_EMPLOYEE です。  

 SQL Server の LIKE 演算子を使用できる有効な式と互換性がある検索式を指定することができます。 たとえば、スキーマに含まれているテーブルの検索を実行するため、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] 、次の SQL を実行します:`SELECT TABLE_NAME FROM ALL_TABLES WHERE TABLE_NAME LIKE ‘[SEARCH_STR]’`します。  

 次の表特殊文字を[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]検索式をサポートしています。  

|特殊文字|解釈|  
|-----------------------|--------------------|  
|% (割合)|0 個以上の文字と一致します。<br /><br /> たとえば、「%」は、"A"、"AB"、"ABC"、およびなどと一致します。|  
|_ (アンダースコア)|正確に 1 文字と一致します。<br /><br /> たとえば、「a _」に一致"AB"、"AC"、"AD"など。|  
|[ ]|-_ % の特別な意味をエスケープします。<br />-範囲または存在する文字のセットを指定します。<br /><br /> 以下に例を示します。<br /><br /> -[%] % が、"%"記号を含むすべての名前と一致します。<br />-[a ~ f] と 'a' などの文字と 'f' を持つすべての名前に一致します。<br />-[abc] と 'a'、'b' 文字を含むすべての名前を一致して、'c'。|  
|[^]|範囲または存在しない文字のセットを指定します。<br /><br /> 以下に例を示します。<br /><br /> -[^ a ~ f] と 'a' などの文字または 'f' に存在しないすべての名前と一致します。<br />-[^ abc] 一致するすべての名前がない文字 'a '、'b'、'c' とします。|  

## <a name="metadata-retrieval-and-node-ids"></a>メタデータを取得し、ノード Id  
 次の表は、によって返されるメタデータの特性をまとめたものです。[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  

|成果物|メタデータの特性|  
|--------------|------------------------------|  
|[テーブルまたはビュー]|<ul><li>テーブル名です。</li><li>テーブルのフィールド名です。</li><li>テーブルのフィールドのデータ型は、単純または複雑な WSDL の種類にマップされます。</li><li>テーブルのフィールドの長さは、ファセット maxLength にマップされます。</li><li>テーブルのフィールドの主キー制約は、ファセットの minOccurs にマップされて = 1。</li><li>テーブルのフィールドの NULL 制約がファセット isNillable にマップされて = true。</li><li>テーブルの操作<br /><br /> <ul><li>INSERT</li><li>SELECT</li><li>UPDATE</li><li>Del</li><li>設定\<列名\></li></ul></li></ul>|  
|プロシージャまたは関数|プロシージャまたは関数の名前は、操作名にマップされます。<br />プロシージャまたは関数のパラメーター名。<br />プロシージャまたは関数のパラメーターのデータ型は、WSDL 型にマップされます。<br />プロシージャまたは関数のパラメーターの方向は、WSDL パラメーターの方向にマップされます。<br />プロシージャ パラメーターまたは関数のパラメーター データ型の長さは、ファセット maxLength にマップされます。<br />プロシージャまたは関数のパラメーターの順序は、要素のシーケンスにマップされます。<br />関数は、データ型は WSDL の種類にマッピングを返します。<br />関数は、データ型の長さが maxLength のファセットにマップを返します。|  

 メタデータの形式に関する詳細情報を[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]特定の成果物と、SQL Server データベースに対する操作の公開を参照してください[メッセージと BizTalk adapter for SQL Server のメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)します。  
