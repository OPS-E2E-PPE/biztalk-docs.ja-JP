---
title: 複合 Operation2 のメッセージ スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0164ea07-a373-430b-b569-3e29df1d081b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2b8cbde8d83e6e973d9c0b75a56f0d9d6f2a67a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376421"
---
# <a name="message-schemas-for-the-composite-operation"></a>複合操作のメッセージ スキーマ
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Oracle データベースでの複合操作を実行することができます。 複合操作は、複数の操作を含めることができ、任意の順序で。 複合操作に含まれる操作については、次を参照してください。 [Oracle データベースでの複合操作を実行](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-in-oracle-database.md)します。  
  
 使用して複合操作を実行する方法については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[BizTalk Server を使用して Oracle データベースでの複合操作を実行](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md)します。  
  
## <a name="message-structure-for-the-composite-operation"></a>複合操作のメッセージの構造  
 複合操作には複数個々 の操作が含まれています複合操作のメッセージ構造には、個々 の操作のメッセージの構造が含まれています。 複合操作のメッセージでは、要求-応答のメッセージ交換パターンに従います。  
  
 受け取らないいずれかのパッケージ化されたストアド プロシージャの入力パラメーター、および削除操作、次の表は、挿入操作を含む複合操作の要求と応答メッセージの構造を示します。  
  
|演算|XML メッセージ|  
|---------------|-----------------|  
|複合操作の要求|`<?xml version="1.0" encoding="utf-8" ?> <Request xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <Insert xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">     <RECORDSET>       <[TABLE_NAME]RECORDINSERT>         <[FIELD1_NAME]>[value1]</[FIELD1_NAME]>         <[FIELD2_NAME]>[value2]</[FIELD2_NAME]>         …       </[TABLE_NAME]RECORDINSERT>    </RECORDSET>   </Insert>   <[SP_NAME] xmlns="[VERSION]/[SCHEMA]/Procedure" />   <Delete xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">     <FILTER>[WHERE_clause]</FILTER>   </Delete> </Request>`|  
|複合操作の応答|`<?xml version="1.0" encoding="utf-8" ?>  <RequestResponse xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <InsertResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">     <InsertResult>[value]</InsertResult>    </InsertResponse>   <[SP_NAME]Response xmlns="[VERSION]/[SCHEMA]/Procedure">     <[PRM1_NAME]>value1<[PRM1_NAME]>     <[PRM2_NAME]>value2</[PRM2_NAME]>     …   </[SP_NAME]Response>    <DeleteResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">     <DeleteResult>[value]</DeleteResult>    </DeleteResponse> </RequestResponse>`|  
  
 [バージョン] = メッセージ バージョン文字列。例えば http://Microsoft.LobServices.OracleDB/2007/03  
  
 [PROJECT_NAME] = 複合操作のスキーマを含む BizTalk プロジェクトの名前。  
  
 [COMPOSITE_SCHEMA_NAME] = ユーザーによって指定された複合操作のスキーマの名前。  
  
 [スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。  
  
 [TABLE_NAME]; テーブルの名前を =たとえば、従業員です。  
  
 [FIELD1_NAME] テーブルのフィールド名を =たとえば、名前を付けます。  
  
 [SP_NAME] を実行するパッケージ化されたストアド プロシージャを =たとえば、ADD_EMP_DETAILS です。  
  
 [PRM1_NAME] = ストアド プロシージャでの Oracle パラメーターの名前。  
  
## <a name="message-action-for-the-composite-operation"></a>複合操作のメッセージ アクション  
 複合操作のメッセージのアクションは、"<http://Microsoft.LobServices.OracleDB/2007/03/CompositeOperation.”>  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for Oracle Database 用のメッセージとメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)