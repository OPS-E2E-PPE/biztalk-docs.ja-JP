---
title: 複合 Operation1 のメッセージ スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 768473ef-da8d-4e58-86cb-597c28ded49c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d069e543e64c26a9229bcb561052ce456c82e32
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375385"
---
# <a name="message-schemas-for-the-composite-operation"></a>複合操作のメッセージ スキーマ
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] Oracle E-business Suite で複合操作を実行することができます。 複合操作は、複数の操作を含めることができ、任意の順序で。 複合操作に含まれる操作については、次を参照してください。[複合操作のサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-composite-operations2.md)します。  
  
 使用して複合操作を実行する方法については、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[BizTalk Server を使用して Oracle データベースでの複合操作を実行](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md)します。  
  
## <a name="message-structure-for-the-composite-operation"></a>複合操作のメッセージの構造  
 複合操作には、複数個々 の操作が含まれているので複合操作のメッセージ構造には、個々 の操作のメッセージの構造が含まれています。 複合操作のメッセージでは、要求-応答のメッセージ交換パターンに従います。  
  
 受け取らないいずれかのパッケージ化されたストアド プロシージャの入力パラメーター、および削除操作、次の表は、挿入操作を含む複合操作の要求と応答メッセージの構造を示します。  
  
> [!NOTE]
>  表の後は、エンティティの説明を参照してください。  
  
|操作|XML メッセージ|  
|---------------|-----------------|  
|複合操作の要求|`<?xml version="1.0" encoding="utf-8" ?> <Request xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <Insert xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/[SCHEMA]/[TABLE_NAME]">     <Recordset>       <InsertRecord>         <[FIELD1_NAME]>[value1]</[FIELD1_NAME]>           <InLineValue>[value]</InlineValue>         <[FIELD2_NAME]>[value2]</[FIELD2_NAME]>           <InLineValue>[value]</InlineValue>         …       <InsertRecord>    </RECORDSET>   </Insert>   <[SP_NAME] xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/PackageApis/[SCHEMA]/[APP_NAME]" />   <Delete xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/[SCHEMA]/[TABLE_NAME]">     <FILTER>[WHERE_clause]</FILTER>   </Delete> </Request>`|  
|複合操作の応答|`<?xml version="1.0" encoding="utf-8" ?>  <RequestResponse xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <InsertResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/[SCHEMA]/[TABLE_NAME]">     <InsertResult>[value]</InsertResult>    </InsertResponse>   <[SP_NAME]Response xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Procedures/[SCHEMA]">     <[PRM1_NAME]>value1<[PRM1_NAME]>     <[PRM2_NAME]>value2</[PRM2_NAME]>     …   </[SP_NAME]Response>    <DeleteResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <DeleteResult>[value]</DeleteResult>    </DeleteResponse> </RequestResponse>`|  
  
 エンティティの説明  
  
 [PROJECT_NAME] = 複合操作のスキーマを含む BizTalk プロジェクトの名前。  
  
 [COMPOSITE_SCHEMA_NAME] = ユーザーによって指定された複合操作のスキーマの名前。  
  
 [スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。  
  
 [TABLE_NAME]; テーブルの名前を =たとえば、従業員です。  
  
 [FIELD1_NAME] テーブルのフィールド名を =たとえば、名前を付けます。  
  
 [SP_NAME] を実行するパッケージ化されたストアド プロシージャを =たとえば、ADD_EMP_DETAILS です。  
  
 [構成] = パッケージ化されたストアド プロシージャを含む Oracle アプリケーションの名前。  
  
 [PRM1_NAME] パッケージ化されたストアド プロシージャでの Oracle パラメーターの名前を = です。  
  
## <a name="message-action-for-the-composite-operation"></a>複合操作のメッセージ アクション  
 複合操作のメッセージ アクションが"CompositeOperation"  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk Adapter for Oracle E-business Suite のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)