---
title: "RFC 操作のメッセージ スキーマ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RFC operations, message structure for
- RFC operations, message actions for
ms.assetid: 50cd9b28-2e66-4c76-9d19-f0da6e7b8e10
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef9d1dfe3ff3cef27269facfe89d3aea8f43cb10
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-rfc-operations"></a>RFC 操作のメッセージ スキーマ
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]操作として SAP リモート関数呼び出し (RFC) を表示します。 このトピックには、メッセージ スキーマおよび RFC 操作に使用されるメッセージのアクションに関する情報が含まれています。 メッセージの構造は、着信および発信の RFC 操作に対して同じです。 アダプタでは、RFC 操作の概要については、次を参照してください。 [SAP Rfc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md)です。  
  
 Bapi のアダプターでの RFC 操作として呼び出すこともできます。 このトピックでは、このような呼び出しのメッセージの構造の例が含まれます。  
  
## <a name="message-structure-for-rfc-operations"></a>RFC 操作のメッセージの構造  
 次の表は、RFC メッセージ スキーマを示します。 RFC の各操作は、要求メッセージと応答 (応答) メッセージで構成されます。  
  
|メッセージ|XML メッセージの構造体|Description|  
|-------------|---------------------------|-----------------|  
|RFC<br /><br /> ([RFC_NAME])|`<[RFC_NAME] xmlns="[VERSION]/Rfc/">   <IN1_PARAM_NAME>v1</IN1_PARAM_NAME>   <IN2_PARAM_NAME>v2</IN2_PARAM_NAME>   …   <INOUT1_PARAM_NAME>v3</INOUT1_PARAM_NAME>   <INOUT2_PARAM_NAME>v4</INOUT2_PARAM_NAME>   …   <TABLE1_PARAM_NAME xmlns="[VERSION]/Types/Rfc/">     <STRUCT1_PARAM_NAME>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </STRUCT1_PARAM_NAME>     …   </TABLE1_PARAM_NAME>   … </[RFC_NAME]>`|SAP システムで RFC を呼び出します。<br /><br /> に変更するインポートしてテーブル パラメーターがサポートされます。<br /><br /> -インポートし、SAP 構造体の型、SAP テーブル型または SAP 単純なデータ型のパラメーターを変更できます。|  
|RFC 応答 ([RFC_NAME] 応答)。|`<[RFC_NAME]Response xmlns="[VERSION]/Rfc/">   <OUT1_PARAM_NAME>v1</OUT1_PARAM_NAME>   <OUT2_PARAM_NAME>v2</OUT2_PARAM_NAME>   …   <INOUT1_PARAM_NAME>v3</INOUT1_PARAM_NAME>   <INOUT2_PARAM_NAME>v4</INOUT2_PARAM_NAME>   …   <TABLE1_PARAM_NAME>     <STRUCT1_PARAM_NAME>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </STRUCT1_PARAM_NAME>     …   </TABLE1_PARAM_NAME>   … </[RFC_NAME]Response>`|RFC を返します。<br /><br /> エクスポートする、変更するとテーブルのパラメーターがサポートされます。<br /><br /> **注:**応答メッセージに表示されませんテーブル パラメーター既定では、します。 応答メッセージ内のテーブルのパラメーターを必要とする場合は、要求メッセージ内で空のテーブルのパラメーターを渡す必要があります。<br /><br /> -インポートし、SAP 構造体の型、SAP テーブル型または SAP 単純なデータ型のパラメーターを変更できます。|  
|RfcGetAttributes<br /><br /> (RfcGetAttributes)|`<RfcGetAttributes> </RfcGetAttributes>`|RfcGetAttributes は RFC SDK の API 操作によって提示されるを[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 RfcGetAttributes 操作を使用すると、クライアント プログラムが、言語、システム ID、および RFC 接続に関連付けられているパートナーのコード ページを取得します。|  
|RfcGetAttributes 応答<br /><br /> (RfcGetAttributesResponse)|`<RfcGetAttributesResponse>   <Language>lang</Language>   <SysId>id</SysId>   <PartnerCodePage>pnrcp</PartnerCodePage> </RfcGetAttributesResponse>`|RfcGetAttributes 操作に対する応答は、言語、システム ID、および RFC 接続に関連付けられているパートナーのコード ページを返します。|  
  
 [バージョン]、メッセージのバージョン文字列を =たとえば、http://Microsoft.LobServices.SAP/2007/03 です。  
  
 [RFC_NAME] RFC; の名前を =たとえば、RFC_CUSTOMER_GET です。  
  
 [IN_PARAM_NAME] RFC インポート パラメーターの名前を = です。  
  
 [OUT_PARAM_NAME] RFC エクスポートのパラメーターの名前を = です。  
  
 [INOUT_PARAM_NAME] RFC を変更するパラメーターの名前を = です。  
  
 [TABLE_PARAM_NAME] RFC テーブル パラメーターの名前を = です。  
  
 [STRUCT_PARAM_NAME] RFC 構造パラメーターの名前を = です。  
  
## <a name="message-actions-for-rfc-operations"></a>RFC 操作のメッセージの動作  
 次の表は、RFC 操作のメッセージ アクションを示します。  
  
|操作|メッセージのアクション|例|  
|---------------|--------------------|-------------|  
|[RFC_NAME]|[バージョン]/Rfc/[RFC_NAME]|http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET|  
|[RFC_NAME]応答|[バージョン]/Rfc/[RFC_NAME]/応答|http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET/response|  
|RfcGetAttributes|[バージョン]/RfcGetAttributes|http://Microsoft.LobServices.Sap/2007/03/RfcGetAttributes|  
|RfcGetAttributes 応答|[バージョン/RfcGetAttributes/応答|http://Microsoft.LobServices.Sap/2007/03/RfcGetAttributes/response|  
  
 [バージョン]、メッセージのバージョン文字列を =たとえば、http://Microsoft.LobServices.Sap/2007/03 です。  
  
 [RFC_NAME]; 呼び出される RFC の名前を =たとえば、RFC_CUSTOMER_GET です。  
  
## <a name="invoking-a-bapi-as-an-rfc-operation"></a>RFC 操作として BAPI を呼び出す  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] RFC 操作とビジネス オブジェクトのメソッドの両方の Bapi を表示します。 RFC 操作としての Bapi は、名前で表示されます。 ビジネス オブジェクトのインターフェイスを使用して Bapi の呼び出しの詳細については、次を参照してください。 [SAP での Bapi の操作](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)です。  
  
 次の XML は、RFC として呼び出される BAPI (BAPI_CUSTOMER_GETDETAIL2) のメッセージ構造を示します。 この操作のメッセージのアクションが: http://Microsoft.LobServices.Sap/2007/03/Rfc/BAPI_CUSTOMER_GETDETAIL2 です。  
  
```  
<BAPI_CUSTOMER_GETDETAIL2 xmlns="http://Microsoft.LobServices.Sap/2007/03/Rfc/">  
  <COMPANYCODE>1001</COMPANYCODE>  
  <CUSTOMERNO>0000001001</CUSTOMERNO>  
  <CUSTOMERBANKDETAIL>  
    <BAPICUSTOMER_02 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
      <CUSTOMER />  
      <BANK_CTRY />  
      <BANK_KEY />  
      <BANK_ACCT />  
      <CTRL_KEY />  
      <PARTNER_BK />  
      <COLL_AUTH />  
      <BANK_REF />  
    </BAPICUSTOMER_02>  
  </CUSTOMERBANKDETAIL>  
</BAPI_CUSTOMER_GETDETAIL2>  
```  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk Adapter 用 mySAP Business Suite のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)