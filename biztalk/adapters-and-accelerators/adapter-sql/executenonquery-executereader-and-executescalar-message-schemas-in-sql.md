---
title: "メッセージ スキーマを ExecuteNonQuery、ExecuteReader、および ExecuteScalar Operations2 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 51f8cb98-8da8-40c1-bf87-4aad5a24bba2
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0aaef682ad0528e8d22e043da94dc31e4f723f24
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-the-executenonquery-executereader-and-executescalar-operations"></a>ExecuteNonQuery、ExecuteReader、および ExecuteScalar 操作のメッセージ スキーマ
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] SQL Server の任意の SQL ステートメントを実行するルート レベルで ExecuteNonQuery、ExecuteReader、および ExecuteScalar 送信操作を公開します。  
  
 詳細については。  
  
-   これらの操作を参照してください[ExecuteNonQuery、ExecuteReader、および ExecuteScalar 操作のサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)です。  
  
-   使用してこれらの操作を実行する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[ExecuteReader、ExecuteScalar、または BizTalk Server を使用して SQL の ExecuteNonQuery Operations](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md)です。  
  
## <a name="message-structure-for-the-executenonquery-executereader-and-executescalar-operations"></a>ExecuteNonQuery、ExecuteReader、および ExecuteScalar 操作のメッセージの構造  
 これらの操作でメッセージが、要求-応答メッセージ交換パターンに従うし、次の表は、これらの要求と応答メッセージの構造を示しています。  
  
|操作|XML メッセージ|Description|  
|---------------|-----------------|-----------------|  
|ExecuteNonQuery 要求|`<ExecuteNonQuery xmlns="http://schemas.microsoft.com/Sql/2008/05/GenericTableOp/">    <Query>[PL/SQL STATEMENT1];[PL/SQL STATEMENT2];…</Query>  </ExecuteNonQuery>`|内で、`<Query>`タグをセミコロンで区切られた複数の PL/SQL ステートメントを指定することができます。|  
|ExecuteNonQuery 応答|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteNonQueryResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/GenericTableOp/">   <ExecuteNonQueryResult>[value]</ExecuteNonQueryResult> </ExecuteNonQueryResponse>`|UPDATE、INSERT、および DELETE のステートメントの`[value]`PL/SQL ステートメントの影響を受ける行の数を表す、 *ExecuteNonQuery 要求*メッセージ。 その他のすべての種類のステートメント、 `[value]` -1 です。|  
|ExecuteReader 要求|`<ExecuteReader xmlns="http://schemas.microsoft.com/Sql/2008/05/GenericTableOp/">   <Query>[PL/SQL STATEMENT1];[PL/SQL STATEMENT2];…</Query> </ExecuteReader>`|内で、`<Query>`タグをセミコロンで区切られた複数の PL/SQL ステートメントを指定することができます。|  
|ExecuteReader 応答|`<?xml version="1.0" encoding="utf-8" ?>  <ExecuteReaderResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/GenericTableOp/">   <ExecuteReaderResult>     <DataSet>       <Any>[value]</Any>       <Any>[value]</Any>       …     </DataSet>   </ExecuteReaderResult> </ExecuteReaderResponse>`|結果セットで実行される PL/SQL ステートメントの応答メッセージでは、 *ExecuteReader 要求*メッセージ、およびデータセットの配列として返されます。 データセットについてで「データセット クラス」を参照してください。 [http://go.microsoft.com/fwlink/?LinkID=196853](http://go.microsoft.com/fwlink/?LinkID=196853)です。|  
|ExecuteScalar 要求|`<ExecuteScalar xmlns="http://schemas.microsoft.com/Sql/2008/05/GenericTableOp/">   <Query>[PL/SQL STATEMENT1];[PL/SQL STATEMENT2];…</Query> </ExecuteScalar>`|内で、`<Query>`タグをセミコロンで区切られた複数の PL/SQL ステートメントを指定することができます。|  
|ExecuteScalar 応答|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteScalarResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/GenericTableOp/">   <ExecuteScalarResult>[value]</ExecuteScalarResult> </ExecuteScalarResponse>`|`[value]` PL/SQL ステートメントによって返される結果セットの最初の行の最初の列の値を表す、 *ExecuteScalar 要求*メッセージ。|  
  
 [PL/SQL ステートメント] を実行する PL/SQL ステートメント全体を = です。  
  
## <a name="message-action-for-the-executenonquery-executereader-and-executescalar-operations"></a>ExecuteNonQuery、ExecuteReader、および ExecuteScalar 操作のメッセージのアクション  
 次の表は、ExecuteNonQuery、ExecuteReader、ExecuteScalar 操作で使用されるメッセージのアクションを示します。  
  
|操作|操作|  
|---------------|------------|  
|ExecuteNonQuery 要求|GenericOp/ExecuteNonQuery|  
|ExecuteNonQuery 応答|GenericOp/ExecuteNonQuery/応答|  
|ExecuteReader 要求|GenericOp/ExecuteReader|  
|ExecuteReader 応答|GenericOp/ExecuteReader/応答|  
|ExecuteScalar 要求|GenericOp/ExecuteScalar|  
|ExecuteScalar 応答|GenericOp/ExecuteScalar/応答|  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk Adapter for SQL Server のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)