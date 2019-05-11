---
title: ExecuteNonQuery、ExecuteReader、ExecuteScalar Operations2 のメッセージ スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51f8cb98-8da8-40c1-bf87-4aad5a24bba2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77dfd6fcd54edb1253eb153b4a3560b8bf6b6357
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369529"
---
# <a name="message-schemas-for-the-executenonquery-executereader-and-executescalar-operations"></a>ExecuteNonQuery、ExecuteReader、ExecuteScalar 操作のメッセージ スキーマ
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] SQL Server の任意の SQL ステートメントを実行する、ルート レベルで ExecuteNonQuery、ExecuteReader、executescalar 送信操作を公開します。  
  
 詳細については。  
  
- これらの操作を参照してください[ExecuteNonQuery、ExecuteReader、ExecuteScalar 操作のサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)します。  
  
- 使用してこれらの操作を実行する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[ExecuteReader、executescalar、ExecuteNonQuery 操作では、BizTalk Server を使用して SQL](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md)します。  
  
## <a name="message-structure-for-the-executenonquery-executereader-and-executescalar-operations"></a>ExecuteNonQuery、ExecuteReader、ExecuteScalar 操作のメッセージの構造  
 これらの操作でメッセージが、要求-応答メッセージ交換パターンに従うし、次の表は、これらの要求と応答メッセージの構造を示します。  
  
|操作|XML メッセージ|説明|  
|---------------|-----------------|-----------------|  
|ExecuteNonQuery 要求|`<ExecuteNonQuery xmlns="http://schemas.microsoft.com/Sql/2008/05/GenericTableOp/">    <Query>[PL/SQL STATEMENT1];[PL/SQL STATEMENT2];…</Query>  </ExecuteNonQuery>`|内で、`<Query>`タグをセミコロンで区切られた複数の PL/SQL ステートメントを指定することができます。|  
|ExecuteNonQuery 応答|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteNonQueryResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/GenericTableOp/">   <ExecuteNonQueryResult>[value]</ExecuteNonQueryResult> </ExecuteNonQueryResponse>`|UPDATE、INSERT、および DELETE のステートメントの`[value]`PL/SQL ステートメントによって影響を受ける行の数を表す、 *ExecuteNonQuery 要求*メッセージ。 その他のすべての種類のステートメント、`[value]`は-1 です。|  
|ExecuteReader 要求|`<ExecuteReader xmlns="http://schemas.microsoft.com/Sql/2008/05/GenericTableOp/">   <Query>[PL/SQL STATEMENT1];[PL/SQL STATEMENT2];…</Query> </ExecuteReader>`|内で、`<Query>`タグをセミコロンで区切られた複数の PL/SQL ステートメントを指定することができます。|  
|ExecuteReader 応答|`<?xml version="1.0" encoding="utf-8" ?>  <ExecuteReaderResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/GenericTableOp/">   <ExecuteReaderResult>     <DataSet>       <Any>[value]</Any>       <Any>[value]</Any>       …     </DataSet>   </ExecuteReaderResult> </ExecuteReaderResponse>`|結果セットで実行される PL/SQL ステートメントの応答メッセージでは、 *ExecuteReader 要求*メッセージ、およびデータセットの配列として返されます。 データセットの詳細についてを参照してください「DataSet クラス」 [ http://go.microsoft.com/fwlink/?LinkID=196853](http://go.microsoft.com/fwlink/?LinkID=196853)します。|  
|ExecuteScalar 要求|`<ExecuteScalar xmlns="http://schemas.microsoft.com/Sql/2008/05/GenericTableOp/">   <Query>[PL/SQL STATEMENT1];[PL/SQL STATEMENT2];…</Query> </ExecuteScalar>`|内で、`<Query>`タグをセミコロンで区切られた複数の PL/SQL ステートメントを指定することができます。|  
|ExecuteScalar 応答|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteScalarResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/GenericTableOp/">   <ExecuteScalarResult>[value]</ExecuteScalarResult> </ExecuteScalarResponse>`|`[value]` PL/SQL ステートメントによって返される結果セットの最初の行の最初の列の値を表す、 *ExecuteScalar 要求*メッセージ。|  
  
 [PL]/[SQL ステートメント] = PL/SQL ステートメント全体を実行します。  
  
## <a name="message-action-for-the-executenonquery-executereader-and-executescalar-operations"></a>ExecuteNonQuery、ExecuteReader、ExecuteScalar 操作のメッセージのアクション  
 ExecuteNonQuery、ExecuteReader、executescalar 操作によって使用されるメッセージのアクションを次の表に示します。  
  
|操作|操作|  
|---------------|------------|  
|ExecuteNonQuery 要求|GenericOp/ExecuteNonQuery|  
|ExecuteNonQuery 応答|GenericOp/ExecuteNonQuery/応答|  
|ExecuteReader 要求|GenericOp/ExecuteReader|  
|ExecuteReader 応答|GenericOp/ExecuteReader/応答|  
|ExecuteScalar 要求|GenericOp/ExecuteScalar|  
|ExecuteScalar 応答|GenericOp/ExecuteScalar/応答|  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk adapter for SQL Server のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)