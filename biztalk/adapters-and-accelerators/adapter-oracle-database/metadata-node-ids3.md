---
title: BizTalk Adapter Pack での Oracle DB アダプターのメタデータ ノード Id |Microsoft Docs
description: メタデータ、検索、取得のタイプのノード、および Oracle DB アダプターの BizTalk アダプター パック (BAP) で公開される Oracle コンポーネントで使用される Id
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 523c7611-b21f-4598-ac77-ba71075db073
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a131cc8e70311f6f57154b90e98ea1067ec5dc02
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969659"
---
# <a name="node-types-and-ids-for-the-oracle-database-adapter"></a>ノードの種類と Oracle データベース アダプターの Id

## <a name="metadata-node-types-and-ids"></a>メタデータのノードの種類と Id 
[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サーフェス Oracle データベース アイテムの階層的にします。 次の表は、ノードの種類と Oracle データベース アイテムのノード Id を[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サーフェス。 ノード ID で使用されているノードの絶対パス、 **IMetadataRetrievalContractBrowse**、**検索**、および**GetMetadata**メソッド。  


| 成果物の表示名 | ノードの種類 |                           ノード ID                           |                                        例                                         |                                                                                                     説明                                                                                                     |
|-----------------------|-----------|-------------------------------------------------------------|----------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|          --           | カテゴリ  |                              /                              |                                           /                                            | [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] ルート ノードです。 すべての第 1 レベル ノードを返しますSQLEXECUTE 操作のノード、POLLINGSTMT 操作ノード、およびスキーマのすべてのノードが含まれます |
|      SQLEXECUTE       | OPERATION |                    [バージョン]/SQLEXECUTE                     |                http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE                |                                                                        SQLEXECUTE 操作のノードです。 SQLEXECUTE 操作の WSDL を返します。                                                                        |
|      POLLINGSTMT      | OPERATION |                    [バージョン]/POLLINGSTMT                    |               http://Microsoft.LobServices。 OracleDB/2007/03/POLLINGSTMT               |                                                                       POLLINGSTMT 操作のノードです。 POLLINGSTMT 操作の WSDL を返します。                                                                       |
|      [DB_SCHEMA]      | カテゴリ  |                    [バージョン]/[DB_SCHEMA]                    |                  http://Microsoft.LobServices.OracleDB/2007/03/SCOTT                   |                                                スキーマのノードです。 指定したスキーマの [全般] カテゴリ ノード (テーブル、ビュー、プロシージャ、関数、およびパッケージ) を返します。                                                |
|         テーブル         | カテゴリ  |                 [バージョン]/[DB_SCHEMA]/[テーブル]                 |               http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table                |                                                                        スキーマ テーブルのノード。 指定したスキーマのすべてのテーブル ノードを返します。                                                                        |
|      [DB_TABLE]       | カテゴリ  |           [バージョン]/[DB_SCHEMA]/Table/[DB_TABLE]            |             http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP              |      テーブルのノードです。 操作のすべてのノード (Insert、Select、Update、Delete、ReadLOB、および UpdateLOB)、指定したテーブルを返します。 (ReadLOB と UpdateLOB のみが返されます、LOB 列を含むテーブル。)      |
|        Insert         | OPERATION |        [バージョン]/[DB_SCHEMA]/Table/[DB_TABLE]/挿入        |          http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert          |                                                             テーブルな挿入操作のノード。 指定されたテーブルの挿入操作の WSDL を返します。                                                             |
|        Select         | OPERATION |        [バージョン]/[DB_SCHEMA]/Table/[DB_TABLE] を選択/        |          http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select          |                                                             テーブルの選択操作のノードです。 指定されたテーブルの選択操作の WSDL を返します。                                                             |
|        更新         | OPERATION |        [バージョン]/[DB_SCHEMA]/Table/[DB_TABLE]/[更新]        |          http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update          |                                                             テーブル更新操作のノード。 指定されたテーブルの更新操作の WSDL を返します。                                                             |
|        DELETE         | OPERATION |        [バージョン]/[DB_SCHEMA]/Table/[DB_TABLE]/削除        |          http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete          |                                                             テーブル操作ノードを削除します。 指定されたテーブルの削除操作の WSDL を返します。                                                             |
|        ReadLOB        | OPERATION |       [バージョン]/[DB_SCHEMA]/Table/[DB_TABLE]/ReadLOB        |         http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/ReadLOB          |                                  テーブル ReadLOB 操作ノード。 指定されたテーブルの ReadLOB 操作の WSDL を返します。 (テーブルに LOB 列が含まれている場合の表示のみ。)                                  |
|       UpdateLOB       | OPERATION |      [バージョン]/[DB_SCHEMA]/Table/[DB_TABLE]/UpdateLOB       |        http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/UpdateLOB         |                                テーブル UpdateLOB 操作ノード。 指定されたテーブルの UpdateLOB 操作の WSDL を返します。 (テーブルに LOB 列が含まれている場合の表示のみ。)                                |
|         表示          | カテゴリ  |                 [バージョン]/[DB_SCHEMA]/ビュー                  |                http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View                |                                                                         スキーマ ビュー ノード。 指定したスキーマのすべてのビューのノードを返します。                                                                         |
|       [DB_VIEW]       | カテゴリ  |            [バージョン]/[DB_SCHEMA]/View/[DB_VIEW]             |          http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View/SALES_VIEW           |       ビューのノードです。 操作のすべてのノード (Insert、Select、Update、Delete、ReadLOB、および UpdateLOB)、指定されたビューを返します。 (ReadLOB と UpdateLOB のみが返されます LOB 列を含むビュー。)        |
|        Insert         | OPERATION |         [バージョン]/[DB_SCHEMA]/View/[DB_VIEW]/挿入         |       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View/SALES_VIEW/Insert       |                                                              ノードの挿入 操作を表示します。 指定されたビューの挿入操作の WSDL を返します。                                                              |
|        Select         | OPERATION |         [バージョン]/[DB_SCHEMA]/View/[DB_VIEW] を選択/         |       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View/SALES_VIEW/Select       |                                                              ビューの選択操作のノード。 指定されたビューの選択操作の WSDL を返します。                                                              |
|        更新         | OPERATION |         [バージョン]/[DB_SCHEMA]/View/[DB_VIEW]/[更新]         |       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View/SALES_VIEW/Update       |                                                              更新操作のノードを表示します。 指定されたビューの更新操作の WSDL を返します。                                                              |
|        DELETE         | OPERATION |         [バージョン]/[DB_SCHEMA]/View/[DB_VIEW]/削除         |       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View/SALES_VIEW/Delete       |                                                              削除操作のノードを表示します。 指定されたビューの削除操作の WSDL を返します。                                                              |
|        ReadLOB        | OPERATION |        [バージョン]/[DB_SCHEMA]/View/[DB_VIEW]/ReadLOB         |      http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View/SALES_VIEW/ReadLOB       |                                   ReadLOB 操作のノードを表示します。 指定されたビューの ReadLOB 操作の WSDL を返します。 (ビューには、LOB 列が含まれている場合の表示のみ。)                                    |
|       UpdateLOB       | OPERATION |       [バージョン]/[DB_SCHEMA]/View/[DB_VIEW]/UpdateLOB        |     http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View/SALES_VIEW/UpdateLOB      |                                  更新操作のノードを表示します。 指定されたテーブルの UpdateLOB 操作の WSDL を返します。 (ビューには、LOB 列が含まれている場合の表示のみ。)                                   |
|       手順       | カテゴリ  |               [バージョン]/[DB_SCHEMA]/プロシージャ               |             http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure              |                                                                      スキーマのプロシージャのノードです。 指定したスキーマのすべてのプロシージャを返します。                                                                       |
|    [DB_PROCEDURE]     | OPERATION |       [バージョン]/[DB_SCHEMA]/Procedure/[DB_PROCEDURE]        |       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure/SP_GENREPORT       |                                                                            プロシージャのノード。 指定されたプロシージャの WSDL を返します。                                                                            |
|       機能        | カテゴリ  |               [バージョン]/[DB_SCHEMA]/[関数]                |              http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Function              |                                                                       スキーマ ノードの関数。 指定したスキーマのすべての関数を返します。                                                                        |
|     [DB_FUNCTION]     | OPERATION |        [バージョン]/[DB_SCHEMA]/Function/[DB_FUNCTION]         |       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Function/FN_GETUSERID        |                                                                             関数のノードです。 指定された関数の WSDL を返します。                                                                             |
|        [パッケージ]        | カテゴリ  |                [バージョン]/[DB_SCHEMA]、[パッケージ]                |              http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package               |                                                                        スキーマのパッケージ ノード。 指定したスキーマのすべてのパッケージを返します。                                                                         |
|     [DB_PACKAGE]      | カテゴリ  |         [バージョン]/[DB_SCHEMA]/Package/[DB_PACKAGE]          |        http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG         |                                                                    パッケージのノードです。 すべてのプロシージャと、指定したパッケージの関数を返します。                                                                    |
|   [PACK_PROCEDURE]    | OPERATION | [バージョン]/[DB_SCHEMA]/Package/[DB_PACKAGE]/[PACK_PROCEDURE] |  http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT   |                                                                    パッケージ プロシージャ ノード。 指定したパッケージのプロシージャの WSDL を返します。                                                                    |
|    [PACK_FUNCTION]    | OPERATION | [バージョン]/[DB_SCHEMA]/Package/[DB_PACKAGE]/[PACK_FUNCTION]  | http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT |                                                                     パッケージの関数のノードです。 指定したパッケージの関数の WSDL を返します。                                                                     |

 [バージョン] バージョンの文字列を =たとえば、 http://Microsoft.LobServices.OracleDB/2007/03 します。  

 [DB_SCHEMA] コレクションの Oracle の成果物を =たとえば、SCOTT です。  

 [DB_TABLE]、Oracle テーブルの名前を =たとえば、EMP です。  

 [DB_VIEW]、Oracle のビューの名前を =たとえば、SALES_VIEW です。  

 [DB_PROCEDURE];、Oracle のプロシージャの名前を =たとえば、SP_GENREPORT です。  

 [DB_FUNCTION]; Oracle 関数の名前を =たとえば、FN_GETUSERID です。  

 [DB_PACKAGE]; Oracle パッケージの名前を =たとえば、ACCOUNT_PKG です。  

 [PACK_PROCEDURE] パッケージ プロシージャの名前を =たとえば、GET_ACCOUNT です。  

 [PACK_FUNCTION] パッケージ関数; の名前を =たとえば、CREATE_ACCOUNT です。  

## <a name="metadata-search-and-node-ids"></a>メタデータの検索とノードの Id  
 メタデータの検索は、強力な機能、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]サーフェスの一部としてその**MetadataRetrievalContract**インターフェイス。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]この機能を使用して、次の Oracle アーティファクトに対する検索をサポートします。 メタデータの検索スコープは、検索操作を実行するノードのすぐ下にあるレベルに限定されます。 たとえば、関数を検索するをする必要があります検索する\\[Schema] \Functions します。 再帰的な検索がサポートされていません。  

|成果物|ノード ID|返されるノードの型|説明|  
|--------------|-------------|------------------------|-----------------|  
|[DB_SCHEMA]|/(つまり、ルート ノード)|カテゴリ|検索式に一致するすべてのスキーマ ノードを返します。|  
|[DB_TABLE]|/[バージョン]/[DB_SCHEMA]/[テーブル]|カテゴリ|検索式に一致する指定したスキーマには、すべてのテーブル ノードを返します。|  
|[DB_VIEW]|/[バージョン]/[DB_SCHEMA]/ビュー|カテゴリ|検索式に一致する指定されたスキーマ ビューのすべてのノードを返します。|  
|[DB_PROCEDURE]|/[バージョン]/[DB_SCHEMA]/プロシージャ|OPERATION|検索式に一致する指定したスキーマには、プロシージャのすべてのノードを返します。|  
|[DB_FUNCTION]|/[バージョン]/[DB_SCHEMA]/[関数]|OPERATION|検索式に一致する指定したスキーマには、関数のすべてのノードを返します。|  
|[DB_PACKAGE]|/[バージョン]/[DB_SCHEMA]、[パッケージ]|カテゴリ|検索式に一致する指定したスキーマには、すべてのパッケージ ノード (カテゴリ) を返します。|  
|[PACK_PROCEDURE] と [PACK_FUNCTION]|/[バージョン]/[DB_SCHEMA]/Package/[DB_PACKAGE]|OPERATION|検索式に一致する指定されたパッケージ内の関数およびプロシージャのすべてのノード (操作) を返します。|  

 [バージョン] バージョンの文字列を =たとえば、http://Microsoft.LobServices/2007/03します。  

 [DB_SCHEMA] コレクションの Oracle の成果物を =たとえば、SCOTT です。  

 [DB_TABLE]、Oracle テーブルの名前を =たとえば、EMP です。  

 [DB_VIEW]、Oracle のビューの名前を =たとえば、SALES_VIEW です。  

 [DB_PROCEDURE];、Oracle のプロシージャの名前を =たとえば、SP_GENREPORT です。  

 [DB_FUNCTION]; Oracle 関数の名前を =たとえば、FN_GETUSERID です。  

 [DB_PACKAGE]; Oracle パッケージの名前を =たとえば、ACCOUNT_PKG です。  

 [PACK_PROCEDURE] パッケージ プロシージャの名前を =たとえば、GET_ACCOUNT です。  

 [PACK_FUNCTION] パッケージ関数; の名前を =たとえば、CREATE_ACCOUNT です。  

 Oracle のような演算子を使用できる有効な式と互換性がある検索式を指定することができます。 たとえば、スキーマに含まれているテーブルの検索を実行するため、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] 、次の SQL を実行します:`SELECT TABLE_NAME FROM ALL_TABLES WHERE OWNER = '[OWNER_NAME]' AND TABLE_NAME LIKE ‘[SEARCH_STR]’`します。  

 次の表特殊文字を[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]検索式をサポートしています。  

|特殊文字|解釈|  
|-----------------------|--------------------|  
|% (割合)|0 個以上の文字と一致たとえば、「%」は、"A"、"AB"、"ABC"、およびなどと一致します。|  
|_ (アンダースコア)|正確に 1 文字と一致します。たとえば、「a _」に一致"AB"、"AC"、"AD"など。|  
|\ (エスケープ)|'%' と '_'; の特別な意味でのエスケープします。たとえば、"A\\_B""A_B"に一致します。|  

## <a name="metadata-retrieval-and-node-ids"></a>メタデータを取得し、ノード Id  
 次の表は、によって返されるメタデータの特性をまとめたものです。[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  

|成果物|メタデータの特性|  
|--------------|------------------------------|  
|[テーブルまたはビュー]|<ul><li>テーブル名です。</li><li>テーブルのフィールド名です。</li><li>テーブルのフィールドのデータ型は、単純または複雑な WSDL の種類にマップされます。</li><li>テーブルのフィールドの長さは、ファセット maxLength にマップされます。</li><li>テーブルのフィールドの主キー制約は、ファセットの minOccurs にマップされて = 1。</li><li>テーブルのフィールドの NULL 制約がファセット isNillable にマップされて = true。</li><li>テーブルの操作<br /><br /> <ul><li>INSERT</li><li>SELECT</li><li>UPDATE</li><li>Del</li><li>READLOB (この場合、テーブルには、Oracle LOB の種類 フィールドが含まれています)</li><li>UPDATELOB (この場合、テーブルには、Oracle LOB の種類 フィールドが含まれています)</li></ul></li></ul>|  
|プロシージャまたは関数|プロシージャまたは関数の名前は、操作名にマップされます。<br />プロシージャまたは関数のパラメーター名。<br />プロシージャまたは関数のパラメーターのデータ型は、WSDL 型にマップされます。<br />プロシージャまたは関数のパラメーターの方向は、WSDL パラメーターの方向にマップされます。<br />プロシージャ パラメーターまたは関数のパラメーター データ型の長さは、ファセット maxLength にマップされます。<br />プロシージャまたは関数のパラメーターの順序は、要素のシーケンスにマップされます。<br />関数は、データ型は WSDL の種類にマッピングを返します。<br />関数は、データ型の長さが maxLength のファセットにマップを返します。|  
|パッケージのプロシージャまたは関数。|パッケージの名前。<br />-その他のプロシージャと関数の特性上に示したようにします。|  

 メタデータの形式に関する詳細情報を[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]特定の成果物と、Oracle データベースに対する操作の公開を参照してください[メッセージとメッセージ スキーマの BizTalk Adapter for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)します。  

## <a name="see-also"></a>参照  
[Visual Studio で Oracle DB 操作用のメタデータを取得する](get-metadata-for-oracle-database-operations-in-visual-studio.md)