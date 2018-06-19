---
title: BAPI 操作のメッセージ スキーマ |Microsoft ドキュメント
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
ms.openlocfilehash: 999e60a7e2cac827031ea2a19f9482d9da0baaa6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217450"
---
# <a name="message-schemas-for-bapi-operations"></a>BAPI 操作のメッセージ スキーマ
次の説明は、メッセージ スキーマやメッセージのアクションでの Bapi の呼び出しに使用、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]ビジネス オブジェクトのメソッドとして。 Bapi のアダプターでの RFC 操作として呼び出すこともできます。 Rfc 呼び出しに使用されるメッセージの詳細については、次を参照してください。 [RFC 操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)です。 常に、アダプターは、アダプターでの BAPI の起動方法に関係なく、SAP システムで RFC として、BAPI を呼び出します。 方法の概要については[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]サポートの Bapi を参照してください[SAP での Bapi の操作](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)です。  
  
## <a name="message-structure-for-business-object-operations"></a>ビジネス オブジェクトの操作のメッセージの構造  
 次の表は、ビジネス オブジェクトのメソッドとして BAPI を呼び出すために使用するメッセージ スキーマを示します。  
  
|操作|XML データ構造|Description|  
|---------------|-------------------|-----------------|  
|[BUSOBJ_METHOD]|`<[BUSOBJ_METHOD] xmlns="[VERSION]/Bapi/[BUSOBJ]/">   <IN1_PARAM_NAME>v1</IN1_PARAM_NAME>   <IN2_PARAM_NAME>v2</IN2_PARAM_NAME>   …   <INOUT1_PARAM_NAME>v3</INOUT1_PARAM_NAME>   <INOUT2_PARAM_NAME>v4</INOUT2_PARAM_NAME>   …   <TABLE1_PARAM_NAME xmlns="[VERSION]/Types/Rfc/">     <STRUCT1_PARAM_NAME>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </STRUCT1_PARAM_NAME>     …   </TABLE1_PARAM_NAME>   … </[BUSOBJ_METHOD]>`|SAP システムでビジネス オブジェクト メソッドを呼び出します。<br /><br /> インポート、変更、およびテーブルのパラメーターがサポートされています。|  
|[BUSOBJ_METHOD]応答|`<[BUSOBJ_METHOD]Response xmlns="[VERSION]/Bapi/[BUSOBJ]/">   <OUT1_PARAM_NAME>v1</OUT1_PARAM_NAME>   <OUT2_PARAM_NAME>v2</OUT2_PARAM_NAME>   …   <INOUT1_PARAM_NAME>v3</INOUT1_PARAM_NAME>   <INOUT2_PARAM_NAME>v4</INOUT2_PARAM_NAME>   …   <TABLE1_PARAM_NAME xmlns="[VERSION]/Types/Rfc/">     <STRUCT1_PARAM_NAME>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </STRUCT1_PARAM_NAME>     …   </TABLE1_PARAM_NAME>   … </[BUSOBJ_METHOD]Response>`|ビジネス オブジェクト メソッドの応答です。<br /><br /> エクスポート、変更すると、およびテーブル パラメーターはサポートされています。<br /><br /> **注**応答メッセージに表示されませんテーブル パラメーター既定では、します。 応答メッセージ内のテーブルのパラメーターを必要とする場合は、要求メッセージ内で空のテーブルのパラメーターを渡す必要があります。|  
  
 [バージョン]、メッセージのバージョン文字列を =たとえば、http://Microsoft.LobServices.Sap/2007/03 です。  
  
 [BUSOBJ_METHOD]、ビジネス オブジェクトのメソッドの名前を =たとえば、CREATEFROMDAT2 です。  
  
 [IN_PARAM_NAME] BAPI インポートのパラメーターの名前を = です。  
  
 [OUT_PARAM_NAME] BAPI エクスポート パラメーターの名前を = です。  
  
 [INOUT_PARAM_NAME] パラメーターを変更する BAPI の名前を = です。  
  
 [TABLE_PARAM_NAME] BAPI テーブル パラメーターの名前を = です。  
  
 [STRUCT_PARAM_NAME] BAPI 構造パラメーターの名前を = です。  
  
## <a name="message-actions-for-business-object-operations"></a>ビジネス オブジェクトの操作のメッセージの動作  
 次の表は、ビジネス オブジェクト メソッドとしての Bapi の呼び出しに使用されるメッセージのアクションを示します。  
  
|操作|メッセージのアクション|例|  
|---------------|--------------------|-------------|  
|[BUSOBJ_METHOD]|[バージョン]/Bapi/[BUSOBJ_NAME]/[BUSOBJ_METHOD]/[BAPI_RFC_NAME]|http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2|  
|[BUSOBJ_METHOD]応答|[バージョン]/Bapi/[BUSOBJ_NAME]/[BUSOBJ_METHOD]/[BAPI_RFC_NAME]/応答|http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2/response|  
  
 [バージョン]、メッセージのバージョン文字列を =たとえば、http://Microsoft.LobServices.Sap/2007/03 です。  
  
 [BUSOBJ_NAME]、ビジネス オブジェクトの名前を =たとえば、BUS2032 です。  
  
 [BUSOBJ_METHOD] ビジネス オブジェクトのメソッドを =たとえば、CREATEFROMDAT2 です。  
  
 [BAPI_RFC_NAME] BAPI; の名前を RFC を =たとえば、BAPI_SALESORDER_CREATEFROMDAT2 です。  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk Adapter 用 mySAP Business Suite のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)