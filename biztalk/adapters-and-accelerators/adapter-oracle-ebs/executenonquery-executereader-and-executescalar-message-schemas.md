---
title: ExecuteNonQuery、ExecuteReader、ExecuteScalar Operations1 のメッセージ スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8aa5fdb2-1e7f-4a34-a1e5-c16d8fb477d5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7078fed7a007eca4dfb3eb5608eb6e688bb74a45
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011971"
---
# <a name="message-schemas-for-the-executenonquery-executereader-and-executescalar-operations"></a>ExecuteNonQuery、ExecuteReader、ExecuteScalar 操作のメッセージ スキーマ
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] Oracle E-business Suite で、任意の SQL ステートメントまたは PL/SQL ブロックを実行する、ルート レベルで ExecuteNonQuery、ExecuteReader、executescalar 送信操作を公開します。  
  
 詳細については。  
  
- これらの操作を参照してください[ExecuteNonQuery、ExecuteReader、ExecuteScalar 操作のサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)します。  
  
- 使用してこれらの操作を実行する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[ExecuteReader、executescalar、ExecuteNonQuery 操作では、BizTalk Server を使用して SQL](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md)します。  
  
## <a name="message-structure-for-the-executenonquery-executereader-and-executescalar-operations"></a>ExecuteNonQuery、ExecuteReader、ExecuteScalar 操作のメッセージの構造  
 これらの操作でメッセージが、要求-応答メッセージ交換パターンに従うし、次の表は、これらの要求と応答メッセージの構造を示します。  
  
> [!NOTE]
>  表の後は、エンティティの説明を参照してください。  
  
|演算|XML メッセージ|  
|---------------|-----------------|  
|ExecuteNonQuery 要求|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteNonQuery xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <Query>[PL/SQL block]</Query>   <OutputRefCursorNames>     <string>[stringvalue1]</string>     <string>[stringvalue2]</string>     …   </OutputRefCursorNames> </ExecuteNonQuery>`|  
|ExecuteNonQuery 応答|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteNonQueryResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <ExecuteNonQueryResult>[value]</ExecuteNonQueryResult>   <OutputRefCursors>     <DataSet>       <Any>[value]</Any>       <Any>[value]</Any>       …     </DataSet>   </OutputRefCursors> </ExecuteNonQueryResponse>`|  
|ExecuteReader 要求|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteReader xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <Query>[PL/SQL block]</Query> </ExecuteReader>`|  
|ExecuteReader 応答|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteReaderResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <ExecuteReaderResult>     <Any>[value]</Any>     <Any>[value]</Any>       …   </ExecuteReaderResult> </ExecuteReaderResponse>`|  
|ExecuteScalar 要求|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteScalar xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <Query>[PL/SQL block]</Query> </ExecuteScalar>`|  
|ExecuteScalar 応答|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteScalarResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <ExecuteScalarResult>[value]</ExecuteScalarResult> </ExecuteScalarResponse>`|  
  
 エンティティの説明:  
  
 [ブロックの PL/SQL] = PL/SQL ブロック全体を実行します。  
  
 [stringvalue1] = 文字列の配列内の値。  
  
## <a name="message-action-for-the-executenonquery-executereader-and-executescalar-operations"></a>ExecuteNonQuery、ExecuteReader、ExecuteScalar 操作のメッセージのアクション  
 ExecuteNonQuery、ExecuteReader、executescalar 操作によって使用されるメッセージのアクションを次の表に示します。  
  
|演算|操作|  
|---------------|------------|  
|ExecuteNonQuery 要求|GenericOp/ExecuteNonQuery|  
|ExecuteNonQuery 応答|GenericOp/ExecuteNonQuery/応答|  
|ExecuteReader 要求|GenericOp/ExecuteReader|  
|ExecuteReader 応答|GenericOp/ExecuteReader/応答|  
|ExecuteScalar 要求|GenericOp/ExecuteScalar|  
|ExecuteScalar 応答|GenericOp/ExecuteScalar/応答|