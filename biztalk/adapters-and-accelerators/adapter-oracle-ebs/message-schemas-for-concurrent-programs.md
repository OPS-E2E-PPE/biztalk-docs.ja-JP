---
title: 同時実行プログラムのメッセージ スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3c5709d5-e2b3-485b-9cdd-004985972ba1
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b2dc458ea1c537172cb2e8d2fb13961555fb3be
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375394"
---
# <a name="message-schemas-for-concurrent-programs"></a>同時実行プログラムのメッセージ スキーマ
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]操作として同時実行プログラムを表示します。 操作として公開されている同時実行プログラムと共に、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]次の 3 つの標準的な操作も明らかになります。Get_Status、Wait_For_Request、および Submit_Request です。 同時実行プログラムに関連するこれらの操作については、次を参照してください。[同時実行プログラムに対する操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md)します。  
  
## <a name="message-structure-of-concurrent-program-operations"></a>同時実行プログラムの操作のメッセージの構造  
 同時実行プログラムの表示操作では、要求-応答のメッセージ交換パターンに従います。 次の表では、これらの要求と応答メッセージの構造を示します。  
  
> [!NOTE]
>  表の後は、エンティティの説明を参照してください。  
  
|操作|XML メッセージ|説明|  
|---------------|-----------------|-----------------|  
|[Concurrent_Program_Name]要求|`<?xml version="1.0" encoding="utf-8" ?> <[Concurrent_Program_Name] xmlns="[VERSION]/ConcurrentPrograms/[APP_SHORT_NAME]/">   <SetOptions>     <Implicit>[value]</Implicit>     <Protected>[value]</Protected>     <Language>[value]</Language>     <Territory>[value]</Territory>     <ContinueOnFail>[value]</ContinueOnFail>   </SetOptions>   <SetPrintOptions>     <Printer>[value]</Printer>     <Style>[value]</Style>     <Copies>[value]</Copies>     <SaveOutput>[value]</SaveOutput>     <PrintTogether>[value]</PrintTogether>     <ContinueOnFail>[value]</ContinueOnFail>   </SetPrintOptions>   <SetRepeatOptions>     <RepeatTime>[value]</RepeatTime>     <RepeatInterval>[value]</RepeatInterval>     <RepeatUnit>[value]</RepeatUnit>     <RepeatType>[value]</RepeatType>     <RepeatEndTime>[value]</RepeatEndTime>     <ContinueOnFail>[value]</ContinueOnFail>   </SetRepeatOptions>   <Description>[value]</Description>   <StartTime><[value]</StartTime>   <[CONCURRENT_PROGRAM_ARGUMENT1]>[value]</[CONCURRENT_PROGRAM_ARGUMENT1]>   <[CONCURRENT_PROGRAM_ARGUMENT2]>[value]</[CONCURRENT_PROGRAM_ARGUMENT2]>   … </[Concurrent_Program_Name]>`|-[Concurrent_Program_Name] 操作では、5 つの標準パラメーターを受け取ります。*SetOptions*、 *SetPrintOptions*、 *SetRepeatOptions*、*説明*、および*StartTime*します。<br /><br /> - *ContinueOnFail*パラメーターかどうか同時要求を送信する必要がありますを続行を示す場合は親パラメーター (*SetOptions*、 *SetPrintOptions*、または*SetRepeatOptions*) 失敗した場合、例外をスローする必要がありますか。 指定できる**True** (続行) または**False** (例外をスロー)。<br /><br /> 各パラメーターの詳細については、次を参照してください。[同時実行プログラムに対する操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md)します。|  
|[Concurrent_Program_Name]応答|`<?xml version="1.0" encoding="utf-8" ?> <[Concurrent_Program_Name]Response xmlns="[VERSION]/ConcurrentPrograms/[APP_SHORT_NAME]">   <[Concurrent_Program_Name]Result>[value]</[Concurrent_Program_Name]Result> </[Concurrent_Program_Name]Response>`|Oracle E-business Suite からの応答には、同時実行の要求 ID が含まれています。|  
|Get_Status 要求|`<?xml version="1.0" encoding="utf-8" ?> <GetStatusForConcurrentProgram xmlns="[VERSION]/ConcurrentPrograms/[APP_SHORT_NAME]">   <RequestId>[value]</RequestId>  </GetStatusForConcurrentProgram>`|この Get_Status 要求メッセージは、同時実行プログラムの要求 ID を入力として処理します。|  
|Get_Status 応答|`<?xml version="1.0" encoding="utf-8" ?> <GetStatusForConcurrentProgramResponse xmlns="[VERSION]/ConcurrentPrograms/[APP_SHORT_NAME]">   <GetStatusForConcurrentProgramResult>[value]</GetStatusForConcurrentProgramResult>    <Phase>[value]</Phase>    <Status>[value]</Status>    <DevPhase>[value]</DevPhase>    <DevStatus>[value]</DevStatus>    <Message>[value]</Message>  </GetStatusForConcurrentProgramResponse>`|この Get_Status 応答メッセージは、要求フェーズ/状態と同時実行プログラムの完了のメッセージを返します。<br /><br /> 各パラメーターの詳細については、次を参照してください。[同時実行プログラムに対する操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md)します。|  
|Wait_For_Request 要求|`<?xml version="1.0" encoding="utf-8" ?> <WaitForRequestForConcurrentProgram xmlns="[VERSION]/ConcurrentPrograms/[APP_SHORT_NAME]">   <RequestId>[value]</RequestId>   <Interval>[value]</Interval>   <MaxWait>[value]</MaxWait>    </WaitForRequestForConcurrentProgram>`|各パラメーターの詳細については、次を参照してください。[同時実行プログラムに対する操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md)します。|  
|Wait_For_Request 応答|`<?xml version="1.0" encoding="utf-8" ?> <WaitForRequestForConcurrentProgramResponse xmlns="[VERSION]/ConcurrentPrograms/[APP_SHORT_NAME]">   <WaitForRequestForConcurrentProgramResult>[value]</WaitForRequestForConcurrentProgramResult>    <Phase>[value]</Phase>    <Status>[value]</Status>    <DevPhase>[value]</DevPhase>    <DevStatus>[value]</DevStatus>    <Message>[value]</Message>    </WaitForRequestForConcurrentProgramResponse>`|この Wait_For_Request 応答メッセージは、要求フェーズ/状態と同時実行プログラムの完了のメッセージを返します。<br /><br /> 各パラメーターの詳細については、次を参照してください。[同時実行プログラムに対する操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md)します。|  
|Submit_Request 要求|`<?xml version="1.0" encoding="utf-8" ?> <SubmitRequestForConcurrentProgram xmlns="[VERSION]/ConcurrentPrograms/[APP_SHORT_NAME]">   <SetOptions>     <Implicit>[value]</Implicit>     <Protected>[value]</Protected>     <Language>[value]</Language>     <Territory>[value]</Territory>     <ContinueOnFail>[value]</ContinueOnFail>   </SetOptions>   <SetPrintOptions>     <Printer>[value]</Printer>     <Style>[value]</Style>     <Copies>[value]</Copies>     <SaveOutput>[value]</SaveOutput>     <PrintTogether>[value]</PrintTogether>     <ContinueOnFail>[value]</ContinueOnFail>   </SetPrintOptions>   <SetRepeatOptions>     <RepeatTime>[value]</RepeatTime>     <RepeatInterval>[value]</RepeatInterval>     <RepeatUnit>[value]</RepeatUnit>     <RepeatType>[value]</RepeatType>     <RepeatEndTime>[value]</RepeatEndTime>     <ContinueOnFail>[value]</ContinueOnFail>   </SetRepeatOptions>     <Program>[value]</Program>   <Description>[value]</Description>   <StartTime>[value]</StartTime>   <Arguments>[array_of_strings</Arguments>    </SubmitRequestForConcurrentProgram>`|各パラメーターの詳細については、次を参照してください。[同時実行プログラムに対する操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md)します。|  
|Submit_Request 応答|`<?xml version="1.0" encoding="utf-8" ?> <SubmitRequestForConcurrentProgramResponse xmlns="[VERSION]/ConcurrentPrograms/[APP_SHORT_NAME]">   <SubmitRequestForConcurrentProgramResult>[value]</SubmitRequestForConcurrentProgramResult>  </SubmitRequestForConcurrentProgramResponse>`|要求の送信が正常に完了するは、応答メッセージは、同時要求 ID でを返します。 それ以外の場合、「0」を返します。|  
  
 エンティティの説明  
  
 [バージョン] = http://schemas.microsoft.com/OracleEBS/2008/05  
  
 [APP_SHORT_NAME] アプリケーションの短い名前を =  
  
 [CONCURRENT_PROGRAM_ARGUMENT] Oracle E-business Suite で定義されている、同時実行プログラムで想定されている引数を =  
  
## <a name="message-actions-for-concurrent-programs"></a>同時実行プログラムのメッセージのアクション  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]同時実行プログラムの次のメッセージのアクションを使用します。  
  
> [!NOTE]
>  表の後は、エンティティの説明を参照してください。  
  
|メッセージ|操作|例|  
|-------------|------------|-------------|  
|[Concurrent_Program_Name]要求|ConcurrentPrograms/[APP_SHORT_NAME]/[CONCURRENT_PROGRAM_SHORT_NAME]|ConcurrentPrograms/SQLGL/ADSFINS|  
|[Concurrent_Program_Name]応答|ConcurrentPrograms/[APP_SHORT_NAME]/[CONCURRENT_PROGRAM_SHORT_NAME]/応答|ConcurrentPrograms SQLGL/ADSFINS/応答|  
|Get_Status 要求|ConcurrentPrograms/[APP_SHORT_NAME]/GetStatusForConcurrentProgram|ConcurrentPrograms/SQLGL/GetStatusForConcurrentProgram|  
|Get_Status 応答|ConcurrentPrograms/[APP_SHORT_NAME] GetStatusForConcurrentProgram/応答|ConcurrentPrograms/SQLGL/GetStatusForConcurrentProgram/response|  
|Wait_For_Request 要求|ConcurrentPrograms/[APP_SHORT_NAME]/WaitForRequestForConcurrentProgram|ConcurrentPrograms/SQLGL/WaitForRequestForConcurrentProgram|  
|Wait_For_Request 応答|ConcurrentPrograms/[APP_SHORT_NAME] WaitForRequestForConcurrentProgram/応答|ConcurrentPrograms SQLGL/WaitForRequestForConcurrentProgram/応答|  
|Submit_Request 要求|ConcurrentPrograms/[APP_SHORT_NAME]/SubmitRequestForConcurrentProgram|ConcurrentPrograms/SQLGL/SubmitRequestForConcurrentProgram|  
|Submit_Request 応答|ConcurrentPrograms/[APP_SHORT_NAME] SubmitRequestForConcurrentProgram/応答|ConcurrentPrograms/SQLGL/SubmitRequestForConcurrentProgram/response|  
  
 エンティティの説明  
  
 [APP_SHORT_NAME] アプリケーションの短い名前を =  
  
 [CONCURRENT_PROGRAM_SHORT_NAME] = 同時実行プログラムの短い名前  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk Adapter for Oracle E-business Suite のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)