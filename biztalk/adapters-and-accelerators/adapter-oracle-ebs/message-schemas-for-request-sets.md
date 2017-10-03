---
title: "メッセージ要求のセットのスキーマ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bba9677d-ee94-4da5-8611-b1e47f2f3798
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6fd81ee75088b41a182c5a2aa675266420f8f32f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-request-sets"></a>要求のセットのメッセージ スキーマ
Oracle E-business Suite で Oracle アプリケーションの設定の各要求が内の操作として公開される[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]です。  
  
## <a name="message-structure-of-request-set-operation"></a>セット操作の要求のメッセージの構造  
 要求のセットの表示操作では、要求-応答メッセージ交換パターンに従います。 次の表は、これらの要求と応答メッセージの構造を示しています。  
  
> [!NOTE]
>  表の後に、エンティティの説明を参照してください。  
  
|操作|XML メッセージ|Description|  
|---------------|-----------------|-----------------|  
|[Request_Set_Name]要求|`<?xml version="1.0" encoding="utf-8" ?> <[Request_Set_Name] xmlns="[VERSION]/RequestSets/[APP_SHORT_NAME]/">   <SetRelClassOptions>     <Application>[value]</Application>     <ClassName>[value]</ClassName>     <CancelOrHold>[value]</CancelOrHold>     <StaleDate>[value]</StaleDate>     <ContinueOnFail>[value]</ContinueOnFail>   </SetRelClassOptions>   <SetPrintOptions>     <Printer>[value]</Printer>     <Style>[value]</Style>     <Copies>[value]</Copies>     <SaveOutput>[value]</SaveOutput>     <PrintTogether>[value]</PrintTogether>     <ContinueOnFail>[value]</ContinueOnFail>   </SetPrintOptions>   <SetRepeatOptions>     <RepeatTime>[value]</RepeatTime>     <RepeatInterval>[value]</RepeatInterval>     <RepeatUnit>[value]</RepeatUnit>     <RepeatType>[value]</RepeatType>     <RepeatEndTime>[value]</RepeatEndTime>     <ContinueOnFail>[value]</ContinueOnFail>   </SetRepeatOptions>   <SetNlsOptions>     <Language>[value]</Language>     <Territory>[value]</Territory>     <ContinueOnFail>[value]</ContinueOnFail>   </SetNlsOptions>   <StartTime><[value]</StartTime>   <[CONCURRENT_PROGRAM_NAME1]>[value]</[CONCURRENT_PROGRAM_NAME1]>   <[CONCURRENT_PROGRAM_NAME2]>[value]</[CONCURRENT_PROGRAM_NAME2]>   … </[Request_Set_Name]>`|-[Request_Set_Name] 操作は、5 つの標準的なパラメーターを受け取る: `SetRelClassOptions`、 `SetPrintOptions`、 `SetRepeatOptions`、 `SetNlsOptions`、および`StartTime`です。<br /><br /> -`ContinueOnFail`パラメーターは、要求セットの送信を続行するか、親のパラメーターのケースで例外をスローするかどうかを示します (`SetRelClassOptions`、 `SetPrintOptions`、`SetRepeatOptions`または`SetNlsOptions`) が失敗します。 指定できます**True** (続行) または**False** (例外をスローする)。<br /><br /> 各パラメーターの詳細についてを参照してください[要求セットの操作について](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md)です。|  
|[Request_Set_Name]応答|`<?xml version="1.0" encoding="utf-8" ?> <[Request_Set_Name]Response xmlns="[VERSION]/RequestSets/[APP_SHORT_NAME]">   <[Request_Set_Name]Result>[value]</[Request_Set_Name]Result> </[Request_Set_Name]Response>`|Oracle E-business Suite からの応答には、同時実行の要求 ID が含まれています。|  
  
 エンティティの説明  
  
 [バージョン] http://schemas.microsoft.com/OracleEBS/2008/05 を =  
  
 のインスタンスにアクセスするたびに SQL Server ログインを指定する必要はありません。  
  
 [CONCURRENT_PROGRAM_NAME] プログラムの同時要求セットに含めるを = です。  
  
## <a name="message-actions-for-request-sets"></a>要求のセットのメッセージの動作  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]要求セットの次のメッセージ アクションを使用します。  
  
> [!NOTE]
>  表の後に、エンティティの説明を参照してください。  
  
|メッセージ|操作|例|  
|-------------|------------|-------------|  
|Set 要求を要求します。|RequestSets/[APP_SHORT_NAME]/[REQUESTSET_SHORT_NAME]|RequestSets/SQLGL/FNDRSSUB965|  
|セットの応答を要求します。|RequestSets/[APP_SHORT_NAME]/[REQUESTSET_SHORT_NAME]/応答|RequestSets/SQLGL/FNDRSSUB965/応答|  
  
 エンティティの説明  
  
 [APP_SHORT_NAME] アプリケーションの短い名前を = です。  
  
 [REQUESTSET_SHORT_NAME] = 短い名前の設定を要求します。  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk Adapter for Oracle E-business Suite のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)