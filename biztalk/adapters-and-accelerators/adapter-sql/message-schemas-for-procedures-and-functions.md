---
title: プロシージャと関数のメッセージ スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4acfb29e-8774-4eb7-ba10-2dcb93d2b41a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63eef3d6656b02be2a4b0257f0ff1d22ce561e79
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368737"
---
# <a name="message-schemas-for-procedures-and-functions"></a>プロシージャおよび関数のメッセージ スキーマ
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]サーフェス SQL Server データベースのストアド プロシージャおよびスカラーおよびテーブル値関数の操作として。 このセクションでは、メッセージの構造とプロシージャと関数の呼び出しに使用するアクションについて説明します。  
  
## <a name="message-structure-of-procedures-and-functions"></a>プロシージャと関数のメッセージの構造  
 手順については、操作が表示され、関数は、要求-応答のメッセージ交換パターンに従います。 次の表では、これらの要求と応答メッセージの構造を示します。  
  
|操作|XML メッセージ|説明|  
|---------------|-----------------|-----------------|  
|ストアド プロシージャの要求|`<[SP_NAME] xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/[SCHEMA]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]>`|-|  
|ストアド プロシージャの応答|`<[SP_NAME]Response xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/[SCHEMA]">   <[SP_NAME]Result>      <DataSet>        <any>[Value]</any>       <any>[Value]</any>       …     </DataSet>   </[SP_NAME]Result>   <ReturnValue>[Value]</ReturnValue> </[SP_NAME]Response>`|ストアド プロシージャの戻り値は、データセットの配列です。|  
|厳密に型指定されたストアド プロシージャの要求|`<[STRNG_SP_NAME] xmlns="http://schemas.microsoft.com/Sql/2008/05/TypedProcedures/[SCHEMA]">   <[PRM1_NAME]>value1<[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[STRNG_SP_NAME]>`|-|  
|ストアド プロシージャの厳密に型指定された応答|`<[STRNG_SP_NAME]Response xmlns="http://schemas.microsoft.com/Sql/2008/05/TypedProcedures/[SCHEMA]">     <StoredProcedureResultSet0>          <StoredProcedureResultSet0 xmlns:ns1="http://schemas.microsoft.com/Sql/2008/05/ProcedureResultSets/[SCHEMA]/[STRNG_SP_NAME]">               <[PRM1_NAME]>value1<[PRM1_NAME]>               <[PRM2_NAME]>value2</[PRM2_NAME]>               …         </StoredProcedureResultSet0>     </StoredProcedureResultSet0>    <ReturnValue>[Value]</ReturnValue> </[STRNG_SP_NAME]Response>`|厳密に型指定されたストアド プロシージャの戻り値は、厳密に型指定されたデータの配列です。|  
|スカラー関数の要求|`<[SCLR_FN_NAME] xmlns="http://schemas.microsoft.com/Sql/2008/05/ScalarFunctions/[SCHEMA]">   <[PRM_NAME]>value</[PRM_NAME]> </[SCLR_FN_NAME]>`|-|  
|スカラー関数の応答|`<[SCLR_FN_NAME]Response xmlns="http://schemas.microsoft.com/Sql/2008/05/ScalarFunctions/[SCHEMA]">   <[SCLR_FN_NAME]Result>return_value</[SCLR_FN_NAME]Result>   <[PRM_NAME]>value</[PRM_NAME]>   </[SCLR_FN_NAME]Response>`|-|  
|テーブル値関数の要求|`<[TBL_FN_NAME] xmlns="http://schemas.microsoft.com/Sql/2008/05/TableValuedFunctions/[SCHEMA]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[TBL_FN_NAME]>`|-|  
|テーブル値関数の応答|`<[TBL_FN_NAME]Response xmlns="http://schemas.microsoft.com/Sql/2008/05/TableValuedFunctions/[SCHEMA]">   <[TBL_FN_NAME]Result>      <[TBL_FN_NAME] xmlns="http://schemas.microsoft.com/Sql/2008/05/TableValuedFunctions/[SCHEMA]">         <[PRM1_NAME]>value1</[PRM1_NAME]>         <[PRM2_NAME]>value2</[PRM2_NAME]>         ...      </[TBL_FN_NAME]">        ...      </[TBL_FN_NAME]Result> </[TBL_FN_NAME]Response>`||  
  
 [スキーマ] コレクションの SQL Server のアイテム、=たとえば、dbo です。  
  
 [SP_NAME] を実行するストアド プロシージャを =たとえば、ADD_EMP_DETAILS です。  
  
 [STRNG_SP_NAME] を実行することを厳密に型指定されたストアド プロシージャを =たとえば、GET_EMP_DETAILS です。  
  
 [SCLR_FN_NAME] = スカラー関数を実行します。たとえば、GET_EMP_ID です。  
  
 [TBL_FN_NAME] 実行するテーブル値関数を =たとえば、TVF_EMPLOYEE です。  
  
 [PRM_NAME] = SQL Server パラメーターの名前。  
  
## <a name="message-actions-of-functions-and-procedures"></a>関数およびプロシージャのメッセージのアクション  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]ストアド プロシージャと関数の操作を次のメッセージ アクションを使用します。  
  
|メッセージ|操作|例|  
|-------------|------------|-------------|  
|ストアド プロシージャの要求|プロシージャ/[スキーマ]/[SP_NAME]|プロシージャ/dbo/ADD_EMP_DETAILS|  
|ストアド プロシージャの応答|プロシージャ/[スキーマ]/[SP_NAME]/応答|プロシージャ、dbo、ADD_EMP_DETAILS/応答|  
|厳密に型指定されたストアド プロシージャの要求|TypedProcedure/[スキーマ]/[STRNG_SP_NAME]|TypedProcedure/dbo/GET_EMP_DETAILS|  
|ストアド プロシージャの厳密に型指定された応答|TypedProcedure/[スキーマ]/[STRNG_SP_NAME]/応答|TypedProcedure、dbo、GET_EMP_DETAILS/応答|  
|XML のストアド プロシージャの要求|XmlProcedure/[スキーマ]/[SP_NAME]|XmlProcedure/dbo/GET_EMP_DETAILS_FOR_XML|  
|XML のストアド プロシージャの応答|XmlProcedure/[スキーマ]/[SP_NAME]/resp|XmlProcedure、dbo、GET_EMP_DETAILS_FOR_XML/応答|  
|スカラー関数の要求|ScalarFunction/[スキーマ]/[SCLR_FN_NAME]|ScalarFunction/dbo/GET_EMP_ID|  
|スカラー関数の応答|ScalarFunction/[スキーマ]/[SCLR_FN_NAME]/応答|ScalarFunction、dbo、GET_EMP_ID/応答|  
|テーブル値関数の要求|しません/[スキーマ]/[TBL_FN_NAME]|しません/dbo/TVF_EMPLOYEE|  
|テーブル値関数の応答|しません/[スキーマ]/[TBL_FN_NAME]/応答|しません、dbo、TVF_EMPLOYEE/応答|  
  
 [SP_NAME] を実行するストアド プロシージャを =たとえば、ADD_EMP_DETAILS です。  
  
 [STRNG_SP_NAME] を実行することを厳密に型指定されたストアド プロシージャを =たとえば、GET_EMP_DETAILS です。  
  
 [SCLR_FN_NAME] = スカラー関数を実行します。たとえば、GET_EMP_ID です。  
  
 [TBL_FN_NAME] を実行するのには、テーブル値関数の名前を =たとえば、TVF_EMPLOYEE です。  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk adapter for SQL Server のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)