---
title: 複合操作のメッセージ スキーマ |Microsoft Docs
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
ms.openlocfilehash: 3c262eeecb5910ddcebb1e7dab4f8c2ac7f11bdc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368559"
---
# <a name="message-schemas-for-composite-operations"></a>複合操作のメッセージ スキーマ
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] SQL Server データベースでの複合操作を実行することができます。 複合操作では、Insert、Update を含む複数の操作を含めることができ、テーブルとビューを操作およびストアド プロシージャに対する操作を削除することができます。 複合操作では、任意の順序でこれらの操作を含めることができます。  
  
 詳細については。  
  
- 複合操作を参照してください[複合操作のサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-composite-operations2.md)します。  
  
- 使用して複合操作を実行する方法、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[複合操作の実行、SQL アダプターを使用して SQL Server で](../../adapters-and-accelerators/adapter-sql/run-composite-operations-in-sql-server-using-the-sql-adapter.md)します。  
  
## <a name="message-structure-for-the-composite-operation"></a>複合操作のメッセージの構造  
 複合操作には、複数個々 の操作が含まれているので複合操作のメッセージ構造には、個々 の操作のメッセージの構造が含まれています。 複合操作には、テーブル、ビュー、およびストアド プロシージャに対する操作が含まれている、複合操作のメッセージは、要求-応答のメッセージ交換パターンに従います。  
  
 次の表は、挿入操作を含む複合操作の要求と応答メッセージの構造、ストアド プロシージャを受け取らないいずれかの入力パラメーター、および削除操作です。  
  
|操作|XML メッセージ|  
|---------------|-----------------|  
|複合操作の要求|`<?xml version="1.0" encoding="utf-8" ?> <Request xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <Insert xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <Rows>       <[TABLE_NAME]>         <[FIELD1_NAME]>[Value1]</[FIELD1_NAME]>         <[FIELD2_NAME]>[Value1]</[FIELD2_NAME]>         …       </[TABLE_NAME]>     </Rows>   </Insert>   <[SP_NAME] xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/[SCHEMA]" />   <Delete xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <Rows>       <[TABLE_NAME]>         <[FIELD1_NAME]>[Value1]</[FIELD1_NAME]>       </[TABLE_NAME]>     </Rows>   </Delete> </Request>`|  
|複合操作の応答|`<?xml version="1.0" encoding="utf-8" ?>  <RequestResponse xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <InsertResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <InsertResult>       <long>[value]</long>      </InsertResult>   </InsertResponse>   <[SP_NAME]Response xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/[SCHEMA]">     <[SP_NAME]Result>       <DataSet>         <any>[Value]</any>          <any>[Value]</any>          …       </DataSet>     </[SP_NAME]Result>     <ReturnValue>[value]</ReturnValue>    </[SP_NAME]Response>   <DeleteResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <DeleteResult>[value]</DeleteResult>    </DeleteResponse> </RequestResponse>`|  
  
 [PROJECT_NAME] = 複合操作のスキーマを含む BizTalk プロジェクトの名前。  
  
 [COMPOSITE_SCHEMA_NAME] = ユーザーによって指定された複合操作のスキーマの名前。  
  
 [スキーマ] コレクションの SQL Server のアイテム、=たとえば、dbo です。  
  
 [TABLE_NAME]; テーブルの名前を =たとえば、従業員です。  
  
 [FIELD1_NAME] テーブルのフィールド名を =たとえば、名前を付けます。  
  
 [SP_NAME] を実行するストアド プロシージャを =たとえば、ADD_EMP_DETAILS です。  
  
## <a name="message-action-for-the-composite-operation"></a>複合操作のメッセージ アクション  
 複合操作のメッセージ アクションが"CompositeOperation"  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk adapter for SQL Server のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)