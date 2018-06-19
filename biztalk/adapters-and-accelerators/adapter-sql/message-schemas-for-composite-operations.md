---
title: 複合操作のメッセージ スキーマ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d80c023b-1912-43d4-be29-eb9e1b323593
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b89c354baea2ddb46abf549752dc09699b9c9695
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222514"
---
# <a name="message-schemas-for-composite-operations"></a>複合操作のメッセージ スキーマ
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] SQL Server データベースでの複合操作を実行することができます。 複合操作では、Insert、Update を含む複数の操作を含むでき、テーブルとビューを操作およびストアド プロシージャでの操作を削除することができます。 複合操作は、任意の順序でこれらの操作を含めることができます。  
  
 詳細については。  
  
-   複合操作を参照してください[複合操作に対するサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-composite-operations2.md)です。  
  
-   使用して複合操作を実行する方法、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[SQL アダプタを使用して SQL Server で複合操作を実行](../../adapters-and-accelerators/adapter-sql/run-composite-operations-in-sql-server-using-the-sql-adapter.md)です。  
  
## <a name="message-structure-for-the-composite-operation"></a>複合操作のメッセージの構造  
 複合操作には、複数個々 の操作が含まれているので複合操作のメッセージの構造には、個々 の操作のメッセージの構造体が含まれています。 複合操作には、テーブル、ビュー、およびストアド プロシージャでの操作が含まれている、合成の操作メッセージは、要求-応答メッセージ交換パターンに従います。  
  
 次の表は、挿入操作を含む複合操作の要求および応答メッセージの構造を示しています。 は、ストアド プロシージャを受け取らない入力パラメーター、および削除操作。  
  
|操作|XML メッセージ|  
|---------------|-----------------|  
|複合操作要求|`<?xml version="1.0" encoding="utf-8" ?> <Request xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <Insert xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <Rows>       <[TABLE_NAME]>         <[FIELD1_NAME]>[Value1]</[FIELD1_NAME]>         <[FIELD2_NAME]>[Value1]</[FIELD2_NAME]>         …       </[TABLE_NAME]>     </Rows>   </Insert>   <[SP_NAME] xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/[SCHEMA]" />   <Delete xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <Rows>       <[TABLE_NAME]>         <[FIELD1_NAME]>[Value1]</[FIELD1_NAME]>       </[TABLE_NAME]>     </Rows>   </Delete> </Request>`|  
|複合操作の応答|`<?xml version="1.0" encoding="utf-8" ?>  <RequestResponse xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <InsertResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <InsertResult>       <long>[value]</long>      </InsertResult>   </InsertResponse>   <[SP_NAME]Response xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/[SCHEMA]">     <[SP_NAME]Result>       <DataSet>         <any>[Value]</any>          <any>[Value]</any>          …       </DataSet>     </[SP_NAME]Result>     <ReturnValue>[value]</ReturnValue>    </[SP_NAME]Response>   <DeleteResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <DeleteResult>[value]</DeleteResult>    </DeleteResponse> </RequestResponse>`|  
  
 [PROJECT_NAME] = 複合操作のスキーマを含む BizTalk プロジェクトの名前。  
  
 [COMPOSITE_SCHEMA_NAME]、ユーザーによって指定された複合操作のスキーマの名前を = です。  
  
 [スキーマ]; SQL Server のコレクション アイテムを =たとえば、dbo します。  
  
 [TABLE_NAME] テーブルの名前を =たとえば、従業員です。  
  
 [FIELD1_NAME] = テーブルのフィールド名です。たとえば、名前を付けます。  
  
 [SP_NAME] を実行するストアド プロシージャを =たとえば、ADD_EMP_DETAILS です。  
  
## <a name="message-action-for-the-composite-operation"></a>複合操作のメッセージ アクション  
 複合操作のメッセージ アクションが"CompositeOperation"  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk Adapter for SQL Server のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)