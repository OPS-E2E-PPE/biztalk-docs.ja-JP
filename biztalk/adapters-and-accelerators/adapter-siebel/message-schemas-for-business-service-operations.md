---
title: ビジネス サービス操作のメッセージ スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message schemas, for business service methods
ms.assetid: ba23248b-5d73-4de0-9f7c-987cd88a4b63
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9acda25a321c242118bb3b597c31adea8f265d25
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967963"
---
# <a name="message-schemas-for-business-service-operations"></a>ビジネス サービス操作のメッセージ スキーマ
Siebel ビジネス サービスは、Siebel システムで直接呼び出すことができるビジネス メソッドのコレクションです。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel ビジネス サービスのビジネス メソッドの操作として表示されます。  

## <a name="message-schemas-for-siebel-business-service-method-operations"></a>Siebel ビジネス サービス メソッドの操作のメッセージ スキーマ  
 次の表で表示される Siebel ビジネス サービス メソッドの操作のメッセージ スキーマ、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。  


|           演算            |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    XML の構造体                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |                                                                                                                                                                                       説明                                                                                                                                                                                        |
|--------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Business_Service_METHOD_NAME] | ビジネス サービス メソッドの要求メッセージ。<br /><br /> `<[METHOD_NAME] xmlns="[VERSION]/BusinessServices/[Business Service]/Operation">   <[METHOD_NAME]RequestRecord>     <[I_PRM1_NAME]>value1</[I_PRM1_NAME]>     <[I_PRM2_NAME]>value2</[I_PRM2_NAME]>     …   </[METHOD_NAME]RequestRecord>   <[METHOD_NAME]InOutRecord>     <[IO_PRM1_NAME]>value1</[IO_PRM1_NAME]>     <[IO_PRM2_NAME]>value2</[IO_PRM2_NAME]>     …   </[METHOD_NAME]InOutRecord> </[METHOD_NAME]>`<br /><br /> [バージョン] = メッセージ バージョン文字列。たとえば、"<http://Microsoft.LobServices.Siebel/2007/03>"。<br /><br /> [ビジネス サービス] ビジネス サービスの名前を =たとえば、ExtractDataService です。<br /><br /> [メソッド名が] ビジネス サービス メソッドの名前を =たとえば、ExecuteNext です。<br /><br /> [I_PRM_NAME] 内の名前のパラメーターを = です。<br /><br /> [IO_PRM_NAME] 名の中の OUT パラメーターを = です。<br /><br /> ビジネス サービス メソッドの応答メッセージ:<br /><br /> `<[METHOD_NAME]Response xmlns="[VERSION]/BusinessServices/[Business Service]/Operation">   <[METHOD_NAME]Result>     <[O_PRM1_NAME]>value1</[O_PRM1_NAME]>     <[O_PRM2_NAME]>value2</[O_PRM2_NAME]>     …   </[METHOD_NAME]Result>   <[METHOD_NAME]InOutRecord>     <[IO_PRM1_NAME]>value1</[IO_PRM1_NAME]>     <[IO_PRM2_NAME]>value2</[IO_PRM2_NAME]>     …   </[METHOD_NAME]InOutRecord > </[METHOD_NAME]Response>`<br /><br /> [バージョン] = メッセージ バージョン文字列。たとえば、"<http://Microsoft.LobServices.Siebel/2007/03>"。<br /><br /> [ビジネス サービス] ビジネス サービスの名前を =たとえば、ExtractDataService です。<br /><br /> [メソッド名が] ビジネス サービス メソッドの名前を =たとえば、ExecuteNext です。<br /><br /> [O_PRM_NAME] = 名前の OUT パラメーター。<br /><br /> [IO_PRM_NAME] = 名前の INOUT パラメーター。<br /><br /> **重要:** Siebel システムで必要な場合でも、OUT IN と OUT パラメーターはメタデータでは、省略可能としてマーク常にします。 そのため、パラメーターは、Siebel システムで必要なが、メタデータの省略可能としてマークされている、アダプターをスロー、 `TargetSystemException` Siebel から受信するとなく、`XmlReaderParsingException`します。 | Siebel ビジネス サービス メソッドは、操作名として表示されます。<br /><br /> -では、OUT、OUT パラメーターでサポートされます。<br /><br /> 階層型は文字列として表示されます。 Siebel アダプターでは、これらの文字列に渡される値は検証されません。 これらの値が Siebel システムで想定されているスキーマに準拠していない場合は、実行時に例外が生成されます。 |

## <a name="message-actions-for-siebel-business-service-method-operations"></a>Siebel ビジネス サービス メソッドの操作のメッセージのアクション  
 次の表では、Siebel ビジネス サービス メソッドの SOAP アクションを作成する方法を示します。 要求メッセージのアクションは、表示されて、アクション応答メッセージは追加された形式の専用"/応答"に要求メッセージのアクション。たとえば、"[VERSION]/ビジネス サービス、ExtractDataService、ExecuteNext/応答"。  

|演算|操作|説明|  
|---------------|------------|-----------------|  
|[Business_Service_METHOD_NAME]|[バージョン]/BusinessServices/[ビジネス サービス]/[Business_Service_METHOD_NAME]|[バージョン]/ビジネス サービス/ExtractDataService/ExecuteNext|  

 [バージョン] = メッセージ バージョン文字列。たとえば、"<http://Microsoft.LobServices.Siebel/2007/03>"。  

 [ビジネス サービス] ビジネス サービスの名前を =たとえば、ExtractDataService です。  

 [Business_Service_METHOD_NAME] ビジネス サービス メソッドの名前を =たとえば、ExecuteNext です。  

 使用する場合、メッセージのアクションを明示的に指定する必要があります、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]や、BizTalk Server ソリューションで WCF チャネル モデルを使用します。 詳細については、次を参照してください。 [Siebel アプリケーションの開発](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)します。  

## <a name="siebel-business-service-wcf-client-methods"></a>Siebel ビジネス サービスの WCF クライアント メソッド  
 次の表は、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]によって生成されるサービス モデルのメソッド署名、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] Siebel ビジネス サービス メソッド。  

|演算|WCF サービス モデルのメソッド|  
|---------------|------------------------------|  
|[Business_Service_METHOD_NAME]|`[Business_Service_METHOD_NAME]ResponseRecord client.[Business_Service_METHOD_NAME]([Business_Service_METHOD_NAME]RequestRecord);`<br /><br /> [Business_Service_METHOD_NAME] = ビジネス サービス メソッドの名前。たとえば、ExecuteNext です。|  

## <a name="see-also"></a>参照  
 [メッセージと BizTalk adapter for Siebel eBusiness Applications のメッセージ スキーマ](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)