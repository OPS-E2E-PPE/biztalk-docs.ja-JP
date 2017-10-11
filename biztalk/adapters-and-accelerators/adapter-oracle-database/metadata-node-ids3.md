---
title: "BizTalk Adapter Pack で Oracle データベース アダプターのメタデータのノードの Id |Microsoft ドキュメント"
description: "メタデータ、検索、取得ノードの種類および Oracle データベース アダプターの BizTalk アダプター パック (BAP) で公開される Oracle コンポーネントで使用される Id"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 523c7611-b21f-4598-ac77-ba71075db073
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: acb916e376a5e2dfa72483a9039b0d6cea4bae81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="node-types-and-ids-for-the-oracle-database-adapter"></a>ノードの種類と Oracle データベース アダプターの Id

## <a name="metadata-node-types-and-ids"></a>メタデータのノード型および Id 
[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サーフェス Oracle データベース アイテムの階層状にします。 次の表は、ノードの種類と Oracle データベース アイテムのノード Id を[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サーフェスします。 ノード ID で使用されているノードの絶対パスである、 **IMetadataRetrievalContractBrowse**、**検索**、および**GetMetadata**メソッドです。  
  
|成果物の表示名|ノードの種類|ノード ID|例|Description|  
|---------------------------|---------------|-------------|-------------|-----------------|  
|--|カテゴリ|/|/|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ルート ノードです。 第 1 レベルのすべてのノード以外を返しますこれには、SQLEXECUTE 操作ノード、POLLINGSTMT 操作ノードおよびすべてのスキーマ ノードが含まれます|  
|SQLEXECUTE|OPERATION|[バージョン]/SQLEXECUTE|http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE|SQLEXECUTE 操作のノードです。 SQLEXECUTE 操作の WSDL を返します。|  
|POLLINGSTMT|OPERATION|[バージョン]/POLLINGSTMT|http://Microsoft.LobServices です。 OracleDB/2007/03/POLLINGSTMT|POLLINGSTMT 操作のノードです。 POLLINGSTMT 操作の WSDL を返します。|  
|[DB_SCHEMA]|カテゴリ|[バージョン]/[DB_SCHEMA]|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT|スキーマのノードです。 指定したスキーマ用の一般カテゴリ ノード (テーブル、ビュー、プロシージャ、関数、およびパッケージ) を返します。|  
|テーブル|カテゴリ|[バージョン]/[DB_SCHEMA]/[テーブル]|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table|スキーマ テーブルのノードです。 指定したスキーマ用のすべてのテーブル ノードを返します。|  
|[DB_TABLE]|カテゴリ|[バージョン]/[DB_SCHEMA]/Table/[DB_TABLE]|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP|テーブルのノードです。 操作のすべてのノード (Insert、Select、Update、Delete、ReadLOB、および UpdateLOB)、指定したテーブルを返します。 (ReadLOB と UpdateLOB のみが返されます、LOB 列を含むテーブル。)|  
|Insert|OPERATION|[バージョン]/[DB_SCHEMA]/Table/[DB_TABLE]/挿入|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert|テーブルの挿入操作のノードです。 指定されたテーブルの挿入操作の WSDL を返します。|  
|Select|OPERATION|[バージョン]/[DB_SCHEMA]/Table/[DB_TABLE] を選択/|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select|テーブルの Select 操作のノードです。 指定されたテーブルの Select 操作の WSDL を返します。|  
|Update|OPERATION|[バージョン]/[DB_SCHEMA]/Table/[DB_TABLE]/[更新]|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update|テーブル更新操作のノードです。 指定されたテーブルの更新操作の WSDL を返します。|  
|DELETE|OPERATION|[バージョン]/[DB_SCHEMA]/Table/[DB_TABLE] を削除します|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete|テーブルな操作ノードを削除します。 指定されたテーブルの削除操作の WSDL を返します。|  
|ReadLOB|OPERATION|[バージョン]/[DB_SCHEMA]/Table/[DB_TABLE]/ReadLOB|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/ReadLOB|テーブル ReadLOB 操作のノードです。 指定されたテーブルの ReadLOB 操作の WSDL を返します。 (テーブルに LOB 列が含まれている場合の確認のみできます。)|  
|UpdateLOB|OPERATION|[バージョン]/[DB_SCHEMA]/Table/[DB_TABLE]/UpdateLOB|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/UpdateLOB|テーブル UpdateLOB 操作のノードです。 指定されたテーブルの UpdateLOB 操作の WSDL を返します。 (テーブルに LOB 列が含まれている場合の確認のみできます。)|  
|表示|カテゴリ|[バージョン]/[DB_SCHEMA]/ビュー|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View|スキーマ ビュー ノード。 指定されたスキーマのすべてのノードの表示を返します。|  
|[DB_VIEW]|カテゴリ|[バージョン]/[DB_SCHEMA]/View/[DB_VIEW]|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View/SALES_VIEW|ビューのノードです。 操作のすべてのノード (Insert、Select、Update、Delete、ReadLOB、および UpdateLOB)、指定されたビューを返します。 (ReadLOB と UpdateLOB のみが返されます、LOB 列を含むビュー。)|  
|Insert|OPERATION|[バージョン]/[DB_SCHEMA]/View/[DB_VIEW]/挿入|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View/SALES_VIEW/Insert|挿入操作のノードを表示します。 指定されたビューの挿入操作の WSDL を返します。|  
|Select|OPERATION|[バージョン]/[DB_SCHEMA]/View/[DB_VIEW] を選択/|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View/SALES_VIEW/Select|ビューの Select 操作のノードです。 指定されたビューの Select 操作の WSDL を返します。|  
|Update|OPERATION|[バージョン]/[DB_SCHEMA]/View/[DB_VIEW]/[更新]|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View/SALES_VIEW/Update|更新操作のノードを表示します。 指定されたビューの更新操作の WSDL を返します。|  
|DELETE|OPERATION|[バージョン]/[DB_SCHEMA]/View/[DB_VIEW] を削除します|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View/SALES_VIEW/Delete|削除操作のノードを表示します。 指定されたビューの削除操作の WSDL を返します。|  
|ReadLOB|OPERATION|[バージョン]/[DB_SCHEMA]/View/[DB_VIEW]/ReadLOB|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View/SALES_VIEW/ReadLOB|ReadLOB 操作のノードを表示します。 指定されたビューの ReadLOB 操作の WSDL を返します。 (ビューには、LOB 列が含まれている場合の確認のみできます。)|  
|UpdateLOB|OPERATION|[バージョン]/[DB_SCHEMA]/View/[DB_VIEW]/UpdateLOB|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View/SALES_VIEW/UpdateLOB|更新操作のノードを表示します。 指定されたテーブルの UpdateLOB 操作の WSDL を返します。 (ビューには、LOB 列が含まれている場合の確認のみできます。)|  
|手順|カテゴリ|[バージョン]/[DB_SCHEMA]/プロシージャ|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure|スキーマのプロシージャのノードです。 指定したスキーマ用のすべてのプロシージャを返します。|  
|[DB_PROCEDURE]|OPERATION|[バージョン]/[DB_SCHEMA]/Procedure/[DB_PROCEDURE]|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure/SP_GENREPORT|プロシージャのノードです。 指定されたプロシージャの WSDL を返します。|  
|関数|カテゴリ|[バージョン]/[DB_SCHEMA]/[関数]|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Function|スキーマ関数ノードです。 指定されたスキーマのすべての関数を返します。|  
|[DB_FUNCTION]|OPERATION|[バージョン]/[DB_SCHEMA]/Function/[DB_FUNCTION]|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Function/FN_GETUSERID|関数のノードです。 指定された関数の WSDL を返します。|  
|[パッケージ]|カテゴリ|[バージョン]/[DB_SCHEMA]、[パッケージ]|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package|スキーマのパッケージ ノード。 指定したスキーマ用のすべてのパッケージを返します。|  
|[DB_PACKAGE]|カテゴリ|[バージョン]/[DB_SCHEMA]/Package/[DB_PACKAGE]|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG|[パッケージ] ノード。 すべてのプロシージャと関数を指定したパッケージを返します。|  
|[PACK_PROCEDURE]|OPERATION|[バージョン]/[DB_SCHEMA]/Package/[DB_PACKAGE]/[PACK_PROCEDURE]|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT|パッケージ プロシージャ ノードです。 指定したパッケージ プロシージャの WSDL を返します。|  
|[PACK_FUNCTION]|OPERATION|[バージョン]/[DB_SCHEMA]/Package/[DB_PACKAGE]/[PACK_FUNCTION]|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT|パッケージ機能のノードです。 指定したパッケージ機能の WSDL を返します。|  
  
 [バージョン] = バージョン文字列です。たとえば、http://Microsoft.LobServices.OracleDB/2007/03 です。  
  
 [DB_SCHEMA] コレクションの Oracle の成果物を =たとえば、SCOTT です。  
  
 [DB_TABLE]、Oracle テーブルの名前を =たとえば、EMP です。  
  
 [DB_VIEW]、Oracle のビューの名前を =たとえば、SALES_VIEW です。  
  
 [DB_PROCEDURE];、Oracle のプロシージャの名前を =たとえば、SP_GENREPORT です。  
  
 [DB_FUNCTION]、Oracle 関数の名前を =たとえば、FN_GETUSERID です。  
  
 [DB_PACKAGE]; Oracle パッケージの名前を =たとえば、ACCOUNT_PKG です。  
  
 [PACK_PROCEDURE] パッケージ プロシージャの名前を =たとえば、GET_ACCOUNT です。  
  
 [PACK_FUNCTION] パッケージ関数; の名前を =たとえば、CREATE_ACCOUNT です。  
  
## <a name="metadata-search-and-node-ids"></a>メタデータの検索とノード Id  
 メタデータの検索では、高度な機能、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]サーフェスの一部としてその**MetadataRetrievalContract**インターフェイスです。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]次の Oracle アーティファクトの検索をサポートするためにこの機能を使用します。 検索スコープのメタデータは、検索操作を実行するノードのすぐ下にあるレベルに制限されます。 たとえば、関数を検索するにする必要がありますを検索できる\\[Schema] \Functions です。 再帰的な検索がサポートされていません。  
  
|成果物|ノード ID|返されるノード型|Description|  
|--------------|-------------|------------------------|-----------------|  
|[DB_SCHEMA]|/(つまり、ルート ノード)|カテゴリ|検索式に一致するすべてのスキーマ ノードを返します。|  
|[DB_TABLE]|/[バージョン]/[DB_SCHEMA]/[テーブル]|カテゴリ|テーブルのすべてのノードを返す検索式に一致するスキーマを指定します。|  
|[DB_VIEW]|/[バージョン]/[DB_SCHEMA]/ビュー|カテゴリ|ビューのすべてのノードを返す検索式に一致するスキーマを指定します。|  
|[DB_PROCEDURE]|/[バージョン]/[DB_SCHEMA]/プロシージャ|OPERATION|プロシージャのすべてのノードを返す検索式に一致するスキーマを指定します。|  
|[DB_FUNCTION]|/[バージョン]/[DB_SCHEMA]/[関数]|OPERATION|関数のすべてのノードを返す検索式に一致するスキーマを指定します。|  
|[DB_PACKAGE]|/[バージョン]/[DB_SCHEMA]、[パッケージ]|カテゴリ|パッケージのすべてのノード (カテゴリ) を返す検索式に一致するスキーマを指定します。|  
|[PACK_PROCEDURE] と [PACK_FUNCTION]|/[バージョン]/[DB_SCHEMA]/Package/[DB_PACKAGE]|OPERATION|検索式に一致する指定されたパッケージ内の関数およびプロシージャのすべてのノード (操作) を返します。|  
  
 [バージョン] = バージョン文字列です。たとえば、http://Microsoft.LobServices/2007/03 です。  
  
 [DB_SCHEMA] コレクションの Oracle の成果物を =たとえば、SCOTT です。  
  
 [DB_TABLE]、Oracle テーブルの名前を =たとえば、EMP です。  
  
 [DB_VIEW]、Oracle のビューの名前を =たとえば、SALES_VIEW です。  
  
 [DB_PROCEDURE];、Oracle のプロシージャの名前を =たとえば、SP_GENREPORT です。  
  
 [DB_FUNCTION]、Oracle 関数の名前を =たとえば、FN_GETUSERID です。  
  
 [DB_PACKAGE]; Oracle パッケージの名前を =たとえば、ACCOUNT_PKG です。  
  
 [PACK_PROCEDURE] パッケージ プロシージャの名前を =たとえば、GET_ACCOUNT です。  
  
 [PACK_FUNCTION] パッケージ関数; の名前を =たとえば、CREATE_ACCOUNT です。  
  
 Oracle LIKE 演算子を使用できる任意の有効な式と互換性がある検索式を指定することができます。 たとえば、スキーマに含まれているテーブルの検索を実行するため、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]次の SQL の実行:`SELECT TABLE_NAME FROM ALL_TABLES WHERE OWNER = '[OWNER_NAME]' AND TABLE_NAME LIKE ‘[SEARCH_STR]’`です。  
  
 次の表の特殊文字を[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]検索式でサポートしています。  
  
|特殊文字|解釈|  
|-----------------------|--------------------|  
|% (割合)|0 個以上の文字と一致します。たとえば、「%」は、"A"、"AB"、"ABC"、およびなどと一致します。|  
|_ (アンダースコア)|厳密に 1 文字と一致します。たとえば、「a _」と一致"AB"、"AC"、"AD"などです。|  
|\ (エスケープ)|'%' と '_' 以外の特殊な意味をエスケープします。たとえば、"A\\_B""A_B"に一致します。|  
  
## <a name="metadata-retrieval-and-node-ids"></a>メタデータを取得し、ノード Id  
 次の表に、によって返されるメタデータ特性[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  
|成果物|メタデータの特性|  
|--------------|------------------------------|  
|[テーブルまたはビュー]|<ul><li>テーブル名です。</li><li>テーブルのフィールド名です。</li><li>テーブルのフィールドのデータ型は、単純または複雑な WSDL の種類にマップされます。</li><li>テーブルのフィールドの長さは、ファセット maxLength にマップされます。</li><li>テーブルのフィールドの主キー制約は、ファセットの minOccurs にマップされて 1 を = です。</li><li>テーブルのフィールドの NULL 制約がファセット isNillable にマップされて = true です。</li><li>テーブルの操作<br /><br /> <ul><li>INSERT</li><li>SELECT</li><li>UPDATE</li><li>DELETE</li><li>READLOB (場合は、テーブルには、Oracle LOB 型のフィールドが含まれています)</li><li>UPDATELOB (場合は、テーブルには、Oracle LOB 型のフィールドが含まれています)</li></ul></li></ul>|  
|プロシージャまたは関数|プロシージャまたは関数の名前は、操作名にマップされます。<br />プロシージャまたは関数のパラメーター名。<br />プロシージャまたは関数のパラメーターのデータ型は、WSDL 型にマップされます。<br />プロシージャまたは関数のパラメーターの方向は、WSDL パラメーターの方向にマップされます。<br />プロシージャ パラメーターまたは関数のパラメーター データ型の長さは、ファセット maxLength にマップされます。<br />プロシージャまたは関数のパラメーターの順序は、要素のシーケンスにマップされます。<br />関数は、データ型は WSDL 型にマップを返します。<br />関数は、データ型の長さはファセット maxLength にマップを返します。|  
|パッケージのプロシージャまたは関数です。|パッケージの名前です。<br />-その他のプロシージャと関数の特性上で説明します。|  
  
 詳細については、形式のメタデータを[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]特定の成果物と Oracle データベースでの操作の公開を参照してください[メッセージと BizTalk Adapter 用 Oracle Database のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)です。  
  
## <a name="see-also"></a>参照  
[Visual Studio での Oracle DB 操作のメタデータを取得します。](get-metadata-for-oracle-database-operations-in-visual-studio.md)