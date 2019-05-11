---
title: 要求セットのメッセージ スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bba9677d-ee94-4da5-8611-b1e47f2f3798
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1fb14d8ed93f61f72b08bc4db31464bcf8eb4561
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530684"
---
# <a name="message-schemas-for-request-sets"></a>要求セットのメッセージ スキーマ
内の操作として表示される各要求では、Oracle E-business Suite で Oracle アプリケーション設定[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]します。  
  
## <a name="message-structure-of-request-set-operation"></a>設定操作の要求のメッセージの構造  
 要求セットの表示操作では、要求-応答のメッセージ交換パターンに従います。 次の表では、これらの要求と応答メッセージの構造を示します。  
  
> [!NOTE]
>  表の後は、エンティティの説明を参照してください。  
  
|操作|XML メッセージ|説明|  
|---------------|-----------------|-----------------|  
|[Request_Set_Name]要求|`<?xml version="1.0" encoding="utf-8" ?> <[Request_Set_Name] xmlns="[VERSION]/RequestSets/[APP_SHORT_NAME]/">   <SetRelClassOptions>     <Application>[value]</Application>     <ClassName>[value]</ClassName>     <CancelOrHold>[value]</CancelOrHold>     <StaleDate>[value]</StaleDate>     <ContinueOnFail>[value]</ContinueOnFail>   </SetRelClassOptions>   <SetPrintOptions>     <Printer>[value]</Printer>     <Style>[value]</Style>     <Copies>[value]</Copies>     <SaveOutput>[value]</SaveOutput>     <PrintTogether>[value]</PrintTogether>     <ContinueOnFail>[value]</ContinueOnFail>   </SetPrintOptions>   <SetRepeatOptions>     <RepeatTime>[value]</RepeatTime>     <RepeatInterval>[value]</RepeatInterval>     <RepeatUnit>[value]</RepeatUnit>     <RepeatType>[value]</RepeatType>     <RepeatEndTime>[value]</RepeatEndTime>     <ContinueOnFail>[value]</ContinueOnFail>   </SetRepeatOptions>   <SetNlsOptions>     <Language>[value]</Language>     <Territory>[value]</Territory>     <ContinueOnFail>[value]</ContinueOnFail>   </SetNlsOptions>   <StartTime><[value]</StartTime>   <[CONCURRENT_PROGRAM_NAME1]>[value]</[CONCURRENT_PROGRAM_NAME1]>   <[CONCURRENT_PROGRAM_NAME2]>[value]</[CONCURRENT_PROGRAM_NAME2]>   … </[Request_Set_Name]>`|-[Request_Set_Name] 操作は、5 つの標準パラメーターを受け取ります。 `SetRelClassOptions`、 `SetPrintOptions`、 `SetRepeatOptions`、 `SetNlsOptions`、および`StartTime`します。<br /><br /> -`ContinueOnFail`パラメーターは、要求セットを送信する必要があります続行または親パラメーターの場合は例外をスローするかどうかを示します (`SetRelClassOptions`、 `SetPrintOptions`、`SetRepeatOptions`または`SetNlsOptions`) が失敗します。 指定できる**True** (続行) または**False** (例外をスロー)。<br /><br /> 各パラメーターの詳細については、次を参照してください。[要求セットの操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md)します。|  
|[Request_Set_Name]応答|`<?xml version="1.0" encoding="utf-8" ?> <[Request_Set_Name]Response xmlns="[VERSION]/RequestSets/[APP_SHORT_NAME]">   <[Request_Set_Name]Result>[value]</[Request_Set_Name]Result> </[Request_Set_Name]Response>`|Oracle E-business Suite からの応答には、同時実行の要求 ID が含まれています。|  
  
 エンティティの説明  
  
 [バージョン] = http://schemas.microsoft.com/OracleEBS/2008/05  
  
 .  
  
 [CONCURRENT_PROGRAM_NAME] = 同時実行プログラムの要求セットに含まれています。  
  
## <a name="message-actions-for-request-sets"></a>要求セットのメッセージのアクション  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]要求セットの次のメッセージのアクションを使用します。  
  
> [!NOTE]
>  表の後は、エンティティの説明を参照してください。  
  
|メッセージ|操作|例|  
|-------------|------------|-------------|  
|要求セット|RequestSets/[APP_SHORT_NAME]/[REQUESTSET_SHORT_NAME]|RequestSets/SQLGL/FNDRSSUB965|  
|要求セットの応答|RequestSets/[APP_SHORT_NAME]/[REQUESTSET_SHORT_NAME]/応答|RequestSets SQLGL/FNDRSSUB965/応答|  
  
 エンティティの説明  
  
 [APP_SHORT_NAME] アプリケーションの短い名前を = です。  
  
 [REQUESTSET_SHORT_NAME] = 短い名前の設定を要求します。  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk Adapter for Oracle E-business Suite のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)