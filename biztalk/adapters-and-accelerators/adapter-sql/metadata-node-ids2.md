---
title: "BizTalk Adapter Pack での SQL アダプターのメタデータのノード Id |Microsoft ドキュメント"
description: "メタデータ、検索、取得ノードの種類および SQL Server のアダプターの BizTalk アダプター パック (BAP) で公開されている SQL コンポーネントで使用される Id"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8601a328-5380-4577-a121-c926e0fd3140
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab096378820e27c640af3262b0ae39d2fa1c5810
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="node-types-and-ids-for-the-sql-server-adapter"></a>ノード型と SQL Server のアダプターの Id

## <a name="metadata-node-ids"></a>メタデータのノード Id
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]サーフェス SQL Server データベースの成果物の階層状にします。 次の表は、ノード型と SQL Server のデータベース成果物のノード Id を[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サーフェスします。 ノード ID で使用されているノードの絶対パスである、 **IMetadataRetrievalContractBrowse**、**検索**、および**GetMetadata**メソッドです。  
  
|成果物の表示名|ノードの種類|ノード ID|例|Description|  
|---------------------------|---------------|-------------|-------------|-----------------|  
|--|カテゴリ|/|/|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ルート ノードです。 第 1 レベルのすべてのノード以外を返しますこれには、ExecuteNonQuery、ExecuteReader、および ExecuteScalar 操作ノードと、送信操作のすべてのスキーマ ノードおよび受信操作のポーリング操作ノードが含まれます。|  
|ExecuteNonQuery|送信操作|GenericOp/ExecuteNonQuery|GenericOp/ExecuteNonQuery|ExecuteNonQuery 操作のノードです。 ExecuteNonQuery 操作の WSDL を返します。|  
|ExecuteReader|送信操作|GenericOp/ExecuteReader|GenericOp/ExecuteReader|ExecuteReader 操作のノードです。 ExecuteReader 操作の WSDL を返します。|  
|ExecuteScalar|送信操作|GenericOp/ExecuteScalar|GenericOp/ExecuteScalar|ExecuteScalar 操作のノードです。 ExecuteScalar 操作の WSDL を返します。|  
|ポーリング|受信操作|ポーリング|ポーリング|ポーリング操作のノードです。 ポーリング操作の WSDL を返します。|  
|Notification|受信操作|Notification|Notification|通知操作のノードです。 通知操作の WSDL を返します。|  
|手順|カテゴリ|プロシージャ/|プロシージャ/|スキーマのプロシージャのノードです。 指定したスキーマ用のすべてのプロシージャを返します。|  
|[DB_PROCEDURE]|送信操作|プロシージャ/[DB_SCHEMA]/[Procedure_Name]|プロシージャ/dbo/ADD_EMP_DETAILS|プロシージャのノードです。 指定されたプロシージャの WSDL を返します。|  
|テーブル|カテゴリ|テーブル/|テーブル/|スキーマ テーブルのノードです。 指定したスキーマ用のすべてのテーブル ノードを返します。|  
|[DB_TABLE]|カテゴリ|-|-|テーブルのノードです。 操作のすべてのノード (Insert、Select、Update、Delete、およびセット)、指定したテーブルを返します。<br /><br /> 設定操作は、次のデータ型のいずれかを持つ列を含むテーブルに対してのみ返されます。 varchar (max)、nvarchar (max)、または varbinary (max)。|  
|Insert|送信操作|TableOp/挿入/[DB_SCHEMA]/[DB_TABLE]|TableOp/挿入/dbo/従業員|テーブルの挿入操作のノードです。 指定されたテーブルの挿入操作の WSDL を返します。|  
|Select|送信操作|TableOp と選択/[DB_SCHEMA]/[DB_TABLE]|TableOp を選択して、dbo/従業員|テーブルの Select 操作のノードです。 指定されたテーブルの Select 操作の WSDL を返します。|  
|Update|送信操作|TableOp/更新/[DB_SCHEMA]/[DB_TABLE]|TableOp/更新/dbo/従業員|テーブル更新操作のノードです。 指定されたテーブルの更新操作の WSDL を返します。|  
|DELETE|送信操作|TableOp/削除/[DB_SCHEMA]/[DB_TABLE]|TableOp/削除/dbo/従業員|テーブルな操作ノードを削除します。 指定されたテーブルの削除操作の WSDL を返します。|  
|[COLUMN_NAME] の設定します。|送信操作|TableOp/WriteText/[DB_SCHEMA]/[DB_TABLE]/[COLUMN_NAME]|TableOp/WriteText/dbo/従業員/Job_Description|テーブルのセット操作のノードです。 テーブル内の指定された列の設定操作の WSDL を返します。 (テーブルには、次のデータ型のいずれかの列が含まれている場合にのみ表示: (Max)、nvarchar (max) または Varbinary(Max)) です。|  
|ビュー|カテゴリ|ビュー/|ビュー/|スキーマ ビュー ノード。 指定されたスキーマのすべてのノードの表示を返します。|  
|[DB_VIEW]|カテゴリ|-|-|ビューのノードです。 操作のすべてのノード (Insert、Select、Update、および削除)、指定されたビューを返します。|  
|Insert|送信操作|ViewOp/挿入/[DB_SCHEMA]/[DB_VIEW]|ViewOp/挿入/dbo/Employee_View|挿入操作のノードを表示します。 指定されたビューの挿入操作の WSDL を返します。|  
|Select|送信操作|ViewOp と選択/[DB_SCHEMA]/[DB_VIEW]|ViewOp を選択して、dbo/Employee_View|ビューの Select 操作のノードです。 指定されたビューの Select 操作の WSDL を返します。|  
|Update|送信操作|ViewOp/更新/[DB_SCHEMA]/[DB_VIEW]|ViewOp/更新/dbo/Employee_View|更新操作のノードを表示します。 指定されたビューの更新操作の WSDL を返します。|  
|DELETE|送信操作|ViewOp/削除/[DB_SCHEMA]/[DB_VIEW]|ViewOp/削除/dbo/Employee_View|削除操作のノードを表示します。 指定されたビューの削除操作の WSDL を返します。|  
|スカラー関数|カテゴリ|ScalarFunctions/|ScalarFunctions/|スキーマのスカラー関数のノードです。 指定されたスキーマのすべてのスカラー関数を返します。|  
|[DB_SCLR_FUNCTION]|送信操作|ScalarFunction/[DB_SCHEMA]/[DB_SCLR_FUNCTION]|ScalarFunction/dbo/GET_EMP_ID|スカラー関数のノードです。 指定したスカラー関数の WSDL を返します。|  
|テーブル値関数|カテゴリ|TableFunctions/|TableFunctions/|スキーマのテーブル値関数のノードです。 指定したスキーマ用のすべてのテーブル値関数を返します。|  
|[DB_TBL_FUNCTION]|送信操作|内/[DB_SCHEMA]/[DB_TBL_FUNCTION]|内/dbo/TVF_EMPLOYEE|テーブル値関数のノードです。 指定したテーブル値関数の WSDL を返します。|  
  
 [DB_SCHEMA]; SQL Server のコレクション アイテムを =たとえば、dbo します。  
  
 [DB_TABLE]、SQL Server テーブルの名前を =たとえば、従業員です。  
  
 [DB_VIEW]、SQL Server ビューの名前を =たとえば、Employee_View です。  
  
 [DB_PROCEDURE]、SQL Server のストアド プロシージャの名前を =たとえば、ADD_EMP_DETAILS です。  
  
 [DB_SCLR_FUNCTION]、SQL Server のスカラー関数以外の名前を =たとえば、GET_EMP_ID です。  
  
 [DB_TBL_FUNCTION]、SQL Server テーブル値関数の名前を =たとえば、TVF_EMPLOYEE です。  
  
## <a name="metadata-search-and-node-ids"></a>メタデータの検索とノード Id  
 メタデータの検索では、高度な機能、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]サーフェスの一部としてその**MetadataRetrievalContract**インターフェイスです。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次の SQL Server のアイテムの検索をサポートするためにこの機能を使用します。 検索スコープのメタデータは、検索操作を実行するノードのすぐ下にあるレベルに制限されます。 たとえば、スカラー関数を検索するにする必要があります 検索/スカラー関数/[Schema] です。 再帰的な検索がサポートされていません。  
  
|成果物|ノード ID|返されるノード型|Description|  
|--------------|-------------|------------------------|-----------------|  
|/(つまり、ルート ノード)|/|カテゴリ|検索式に一致するすべてのスキーマ ノードを返します。|  
|[DB_PROCEDURE]|/Procedure/[DB_SCHEMA]|送信操作|プロシージャのすべてのノードを返す検索式に一致するスキーマを指定します。|  
|[DB_TABLE]|/Table/[DB_SCHEMA]|カテゴリ|テーブルのすべてのノードを返す検索式に一致するスキーマを指定します。|  
|[DB_VIEW]|/View/[DB_SCHEMA]|カテゴリ|ビューのすべてのノードを返す検索式に一致するスキーマを指定します。|  
|[DB_SCLR_FUNCTION]|/ScalarFunction/[DB_SCHEMA]|送信操作|スカラー関数のすべてのノードを返す検索式に一致するスキーマを指定します。|  
|[DB_TBL_FUNCTION]|/TableFunction/[DB_SCHEMA]|送信操作|テーブル値関数のすべてのノードを返す検索式に一致するスキーマを指定します。|  
  
 [DB_SCHEMA]; SQL Server のコレクション アイテムを =たとえば、dbo します。  
  
 [DB_TABLE]、SQL Server テーブルの名前を =たとえば、従業員です。  
  
 [DB_VIEW]、SQL Server ビューの名前を =たとえば、Employee_View です。  
  
 [DB_PROCEDURE]、SQL Server プロシージャの名前を =たとえば、ADD_EMP_DETAILS です。  
  
 [DB_SCLR_FUNCTION]、SQL Server のスカラー関数以外の名前を =たとえば、GET_EMP_ID です。  
  
 [DB_TBL_FUNCTION]、SQL Server テーブル値関数の名前を =たとえば、TVF_EMPLOYEE です。  
  
 SQL Server の LIKE 演算子を使用できる任意の有効な式と互換性がある検索式を指定できます。 たとえば、スキーマに含まれているテーブルの検索を実行するため、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次の SQL の実行:`SELECT TABLE_NAME FROM ALL_TABLES WHERE TABLE_NAME LIKE ‘[SEARCH_STR]’`です。  
  
 次の表の特殊文字を[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]検索式でサポートしています。  
  
|特殊文字|解釈|  
|-----------------------|--------------------|  
|% (割合)|0 個以上の文字と一致します。<br /><br /> たとえば、「%」は、"A"、"AB"、"ABC"、およびなどと一致します。|  
|_ (アンダースコア)|厳密に 1 文字と一致します。<br /><br /> たとえば、「a _」と一致"AB"、"AC"、"AD"などです。|  
|[ ]|-_ および % の特別な意味をエスケープします。<br />-範囲または存在する文字のセットを指定します。<br /><br /> 例:<br /><br /> -% [%] % 記号を含むすべての名前に一致します。<br />-[a ~ f] の文字間 'a' と 'f' を持つすべての名前に一致します。<br />-一致する文字を含む 'a', 'b' すべての名前を [abc] と 'c' です。|  
|[^]|範囲が存在している文字のセットを指定します。<br /><br /> 例:<br /><br /> -[^ a ~ f] の文字間 'a' および 'f' が存在しないすべての名前に一致します。<br />-[^ abc] 一致するすべての名前を持たない文字 'a', 'b' および 'c' です。|  
  
## <a name="metadata-retrieval-and-node-ids"></a>メタデータを取得し、ノード Id  
 次の表に、によって返されるメタデータ特性[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
|成果物|メタデータの特性|  
|--------------|------------------------------|  
|[テーブルまたはビュー]|<ul><li>テーブル名です。</li><li>テーブルのフィールド名です。</li><li>テーブルのフィールドのデータ型は、単純または複雑な WSDL の種類にマップされます。</li><li>テーブルのフィールドの長さは、ファセット maxLength にマップされます。</li><li>テーブルのフィールドの主キー制約は、ファセットの minOccurs にマップされて 1 を = です。</li><li>テーブルのフィールドの NULL 制約がファセット isNillable にマップされて = true です。</li><li>テーブルの操作<br /><br /> <ul><li>INSERT</li><li>SELECT</li><li>UPDATE</li><li>DELETE</li><li>設定\<列名 ></li></ul></li></ul>|  
|プロシージャまたは関数|プロシージャまたは関数の名前は、操作名にマップされます。<br />プロシージャまたは関数のパラメーター名。<br />プロシージャまたは関数のパラメーターのデータ型は、WSDL 型にマップされます。<br />プロシージャまたは関数のパラメーターの方向は、WSDL パラメーターの方向にマップされます。<br />プロシージャ パラメーターまたは関数のパラメーター データ型の長さは、ファセット maxLength にマップされます。<br />プロシージャまたは関数のパラメーターの順序は、要素のシーケンスにマップされます。<br />関数は、データ型は WSDL 型にマップを返します。<br />関数は、データ型の長さはファセット maxLength にマップを返します。|  
  
 詳細については、形式のメタデータを[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]特定のアイテムおよび操作で SQL Server データベースに公開を参照してください[メッセージと BizTalk Adapter for SQL Server のメッセージ スキーマを](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)です。  
  