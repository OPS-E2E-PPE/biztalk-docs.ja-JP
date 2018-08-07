---
title: BAPI 操作のメッセージ スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAPI operations, message schemas for
- BAPI operations, message structure for
- BAPI operations, message actions for
ms.assetid: ef4d88e8-f31a-4b68-a303-6885b6f8c083
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 796e7beb428e6f9a4f0df63eff9cf45e9d5410bb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995219"
---
# <a name="message-schemas-for-bapi-operations"></a>BAPI 操作のメッセージ スキーマ
次のセクションでは、メッセージ スキーマやメッセージのアクションでの Bapi を呼び出すために使用について説明します、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]ビジネス オブジェクトのメソッドとして。 アダプターの RFC 操作として、Bapi を呼び出すこともできます。 Rfc の呼び出しに使用するメッセージの詳細については、次を参照してください。 [RFC 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)します。 常に、アダプターは、アダプターでの BAPI の起動方法に関係なく、SAP システムの RFC として、BAPI を呼び出します。 方法の概要については[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]サポート Bapi を参照してください[SAP の Bapi に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)します。  

## <a name="message-structure-for-business-object-operations"></a>ビジネス オブジェクトの操作のメッセージの構造  
 次の表では、ビジネス オブジェクト メソッドとして BAPI を呼び出すために使用するメッセージ スキーマを示します。  

|演算|XML の構造体|説明|  
|---------------|-------------------|-----------------|  
|[BUSOBJ_METHOD]|`<[BUSOBJ_METHOD] xmlns="[VERSION]/Bapi/[BUSOBJ]/">   <IN1_PARAM_NAME>v1</IN1_PARAM_NAME>   <IN2_PARAM_NAME>v2</IN2_PARAM_NAME>   …   <INOUT1_PARAM_NAME>v3</INOUT1_PARAM_NAME>   <INOUT2_PARAM_NAME>v4</INOUT2_PARAM_NAME>   …   <TABLE1_PARAM_NAME xmlns="[VERSION]/Types/Rfc/">     <STRUCT1_PARAM_NAME>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </STRUCT1_PARAM_NAME>     …   </TABLE1_PARAM_NAME>   … </[BUSOBJ_METHOD]>`|SAP システムのビジネス オブジェクト メソッドを呼び出します。<br /><br /> インポート、変更、およびテーブル パラメーターがサポートされています。|  
|[BUSOBJ_METHOD]応答|`<[BUSOBJ_METHOD]Response xmlns="[VERSION]/Bapi/[BUSOBJ]/">   <OUT1_PARAM_NAME>v1</OUT1_PARAM_NAME>   <OUT2_PARAM_NAME>v2</OUT2_PARAM_NAME>   …   <INOUT1_PARAM_NAME>v3</INOUT1_PARAM_NAME>   <INOUT2_PARAM_NAME>v4</INOUT2_PARAM_NAME>   …   <TABLE1_PARAM_NAME xmlns="[VERSION]/Types/Rfc/">     <STRUCT1_PARAM_NAME>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </STRUCT1_PARAM_NAME>     …   </TABLE1_PARAM_NAME>   … </[BUSOBJ_METHOD]Response>`|ビジネス オブジェクト メソッドの応答。<br /><br /> エクスポート、変更、およびテーブル パラメーターがサポートされます。<br /><br /> **注**応答メッセージに表示しないテーブル パラメーターの既定では、します。 応答メッセージのテーブルのパラメーターが必要な場合は、要求メッセージ内で空のテーブルのパラメーターを渡す必要があります。|  

 [バージョン] = メッセージ バージョン文字列。たとえば、 http://Microsoft.LobServices.Sap/2007/03 します。  

 [BUSOBJ_METHOD] ビジネス オブジェクト メソッドの名前を =たとえば、CREATEFROMDAT2 です。  

 [IN_PARAM_NAME] = BAPI インポートのパラメーターの名前。  

 [OUT_PARAM_NAME] = BAPI エクスポートのパラメーターの名前。  

 [INOUT_PARAM_NAME] パラメーターを変更する BAPI の名前を = です。  

 [TABLE_PARAM_NAME] = BAPI テーブル パラメーターの名前。  

 [STRUCT_PARAM_NAME] = BAPI 構造体のパラメーターの名前。  

## <a name="message-actions-for-business-object-operations"></a>ビジネス オブジェクトの操作のメッセージのアクション  
 次の表では、ビジネス オブジェクト メソッドとして Bapi を呼び出すに使用されるメッセージのアクションを示します。  


|        演算         |                            メッセージのアクション                             |                                                   例                                                    |
|--------------------------|-----------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
|     [BUSOBJ_METHOD]      |     [バージョン]/Bapi/[BUSOBJ_NAME]/[BUSOBJ_METHOD]/[BAPI_RFC_NAME]      |     http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2      |
| [BUSOBJ_METHOD]応答 | [バージョン]/Bapi/[BUSOBJ_NAME]/[BUSOBJ_METHOD]/[BAPI_RFC_NAME]/応答 | http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2/response |

 [バージョン] = メッセージ バージョン文字列。たとえば、 http://Microsoft.LobServices.Sap/2007/03 します。  

 [BUSOBJ_NAME]、ビジネス オブジェクトの名前を =たとえば、BUS2032 です。  

 [BUSOBJ_METHOD] ビジネス オブジェクトのメソッドを =たとえば、CREATEFROMDAT2 です。  

 [BAPI_RFC_NAME] BAPI; の名前を「RFC を =たとえば、BAPI_SALESORDER_CREATEFROMDAT2 です。  

## <a name="see-also"></a>参照  
 [メッセージと BizTalk adapter for mySAP Business Suite のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)