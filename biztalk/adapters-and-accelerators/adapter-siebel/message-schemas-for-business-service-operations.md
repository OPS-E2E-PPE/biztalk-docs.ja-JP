---
title: ビジネス サービス操作のメッセージ スキーマ |Microsoft ドキュメント
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
ms.openlocfilehash: 0062b8e6b6ce3961c937e9e5bece81cb24281049
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222298"
---
# <a name="message-schemas-for-business-service-operations"></a>ビジネス サービス操作のメッセージ スキーマ
Siebel ビジネス サービスは、Siebel システムに直接呼び出すことができるビジネス メソッドのコレクションです。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]操作としては、Siebel ビジネス サービスのビジネス メソッドを表示します。  
  
## <a name="message-schemas-for-siebel-business-service-method-operations"></a>Siebel ビジネス サービス メソッドの操作のメッセージ スキーマ  
 次の表では、Siebel ビジネス サービス メソッドの操作が側に表示されるメッセージ スキーマ、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。  
  
|操作|XML データ構造|Description|  
|---------------|-------------------|-----------------|  
|[Business_Service_METHOD_NAME]|ビジネス サービス メソッドの要求メッセージ。<br /><br /> `<[METHOD_NAME] xmlns="[VERSION]/BusinessServices/[Business Service]/Operation">   <[METHOD_NAME]RequestRecord>     <[I_PRM1_NAME]>value1</[I_PRM1_NAME]>     <[I_PRM2_NAME]>value2</[I_PRM2_NAME]>     …   </[METHOD_NAME]RequestRecord>   <[METHOD_NAME]InOutRecord>     <[IO_PRM1_NAME]>value1</[IO_PRM1_NAME]>     <[IO_PRM2_NAME]>value2</[IO_PRM2_NAME]>     …   </[METHOD_NAME]InOutRecord> </[METHOD_NAME]>`<br /><br /> [バージョン]、メッセージのバージョン文字列を =たとえば、"http://Microsoft.LobServices.Siebel/2007/03"です。<br /><br /> [ビジネス サービス] ビジネス サービスの名前を =たとえば、ExtractDataService です。<br /><br /> [メソッド名が] ビジネス サービス メソッドの名前を =たとえば、ExecuteNext です。<br /><br /> [I_PRM_NAME] 名の入力パラメーターを = です。<br /><br /> [IO_PRM_NAME] = 名前の IN OUT パラメーターです。<br /><br /> ビジネス サービス メソッドの応答メッセージ:<br /><br /> `<[METHOD_NAME]Response xmlns="[VERSION]/BusinessServices/[Business Service]/Operation">   <[METHOD_NAME]Result>     <[O_PRM1_NAME]>value1</[O_PRM1_NAME]>     <[O_PRM2_NAME]>value2</[O_PRM2_NAME]>     …   </[METHOD_NAME]Result>   <[METHOD_NAME]InOutRecord>     <[IO_PRM1_NAME]>value1</[IO_PRM1_NAME]>     <[IO_PRM2_NAME]>value2</[IO_PRM2_NAME]>     …   </[METHOD_NAME]InOutRecord > </[METHOD_NAME]Response>`<br /><br /> [バージョン]、メッセージのバージョン文字列を =たとえば、"http://Microsoft.LobServices.Siebel/2007/03"です。<br /><br /> [ビジネス サービス] ビジネス サービスの名前を =たとえば、ExtractDataService です。<br /><br /> [メソッド名が] ビジネス サービス メソッドの名前を =たとえば、ExecuteNext です。<br /><br /> [O_PRM_NAME] = 名前の OUT パラメーターです。<br /><br /> [IO_PRM_NAME] INOUT 名パラメーターを = です。<br /><br /> **重要:** Siebel システムで必要な場合でも、IN OUT パラメーターと OUT パラメーターは、メタデータでは、省略可能としてマーク常にします。 そのため、パラメーターは、Siebel システムで必要なのですが、メタデータで省略可能としてマークされている、アダプターをスロー、 `TargetSystemException` Siebel から受信したおよび not、`XmlReaderParsingException`です。|Siebel ビジネス サービス メソッドは、操作名として確認できます。<br /><br /> 入力、出力、OUT パラメーターがサポートされます。<br /><br /> 階層の種類は、文字列として表示されます。 Siebel アダプターでは、これらの文字列に渡された値は検証しません。 これらの値が Siebel システムで想定されているスキーマに準拠していない場合は、実行時に例外が生成されます。|  
  
## <a name="message-actions-for-siebel-business-service-method-operations"></a>Siebel ビジネス サービス メソッドの操作のメッセージの動作  
 次の表では、Siebel ビジネス サービス メソッドの SOAP アクションを生成する方法を示します。 だけ、要求メッセージに対するアクションが表示されている、アクション応答メッセージは追加された形式の"/応答"に要求メッセージのアクションです。たとえば、"[バージョン]/ビジネス サービス/ExtractDataService/ExecuteNext/応答"です。  
  
|操作|操作|Description|  
|---------------|------------|-----------------|  
|[Business_Service_METHOD_NAME]|[バージョン]/BusinessServices/[ビジネス サービス]/[Business_Service_METHOD_NAME]|[バージョン]/[ビジネス サービス]/ExtractDataService/ExecuteNext|  
  
 [バージョン]、メッセージのバージョン文字列を =たとえば、"http://Microsoft.LobServices.Siebel/2007/03"です。  
  
 [ビジネス サービス] ビジネス サービスの名前を =たとえば、ExtractDataService です。  
  
 [Business_Service_METHOD_NAME] ビジネス サービス メソッドの名前を =たとえば、ExecuteNext です。  
  
 使用するときに、メッセージのアクションを明示的に指定する必要があります、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]または WCF チャネル モデルを使用して、BizTalk Server ソリューションでします。 詳細については、次を参照してください。 [Siebel アプリケーションの開発](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)です。  
  
## <a name="siebel-business-service-wcf-client-methods"></a>Siebel ビジネス サービスの WCF クライアント メソッド  
 次の表に、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]によって生成されるサービス モデルのメソッド シグネチャ、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] Siebel ビジネス サービスのメソッドです。  
  
|操作|WCF サービス モデル メソッド|  
|---------------|------------------------------|  
|[Business_Service_METHOD_NAME]|`[Business_Service_METHOD_NAME]ResponseRecord client.[Business_Service_METHOD_NAME]([Business_Service_METHOD_NAME]RequestRecord);`<br /><br /> [Business_Service_METHOD_NAME] = ビジネス サービス メソッドの名前です。たとえば、ExecuteNext です。|  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk Adapter for Siebel eBusiness Applications のメッセージ スキーマ](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)