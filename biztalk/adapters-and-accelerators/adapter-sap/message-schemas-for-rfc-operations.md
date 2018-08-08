---
title: RFC 操作のメッセージ スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RFC operations, message structure for
- RFC operations, message actions for
ms.assetid: 50cd9b28-2e66-4c76-9d19-f0da6e7b8e10
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 156b8e8c218c4ad23d49959323ed324b0c7cdfd0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972851"
---
# <a name="message-schemas-for-rfc-operations"></a>RFC 操作のメッセージ スキーマ
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]操作として SAP リモート関数呼び出し (RFC) を表示します。 このトピックには、メッセージのスキーマおよび RFC 操作のためのメッセージ アクションに関する情報が含まれています。 メッセージの構造は、受信と送信の RFC 操作のと同じです。 アダプターをサポートする RFC 操作の概要については、次を参照してください。 [SAP で Rfc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md)します。  

 アダプターの RFC 操作として、Bapi を呼び出すこともできます。 このトピックでは、このような呼び出しメッセージ構造の例が含まれます。  

## <a name="message-structure-for-rfc-operations"></a>RFC 操作のメッセージの構造  
 次の表では、RFC のメッセージ スキーマを示します。 RFC の各操作は、要求メッセージと応答 (応答) メッセージで構成されます。  


|                             メッセージ                              |                                                                                                                                                                                                                         XML メッセージの構造                                                                                                                                                                                                                          |                                                                                                                                                                                                     説明                                                                                                                                                                                                      |
|------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                   RFC<br /><br /> ([RFC_NAME])                   | `<[RFC_NAME] xmlns="[VERSION]/Rfc/">   <IN1_PARAM_NAME>v1</IN1_PARAM_NAME>   <IN2_PARAM_NAME>v2</IN2_PARAM_NAME>   …   <INOUT1_PARAM_NAME>v3</INOUT1_PARAM_NAME>   <INOUT2_PARAM_NAME>v4</INOUT2_PARAM_NAME>   …   <TABLE1_PARAM_NAME xmlns="[VERSION]/Types/Rfc/">     <STRUCT1_PARAM_NAME>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </STRUCT1_PARAM_NAME>     …   </TABLE1_PARAM_NAME>   … </[RFC_NAME]>` |                                                                                              SAP システムの RFC を呼び出します。<br /><br /> -インポート、変更、およびテーブル パラメーターがサポートされます。<br /><br /> -インポート SAP 構造体の型、テーブル型の SAP または SAP の単純なデータ型のパラメーターを変更できます。                                                                                              |
|                RFC 応答 ([RFC_NAME] 応答)                 |     `<[RFC_NAME]Response xmlns="[VERSION]/Rfc/">   <OUT1_PARAM_NAME>v1</OUT1_PARAM_NAME>   <OUT2_PARAM_NAME>v2</OUT2_PARAM_NAME>   …   <INOUT1_PARAM_NAME>v3</INOUT1_PARAM_NAME>   <INOUT2_PARAM_NAME>v4</INOUT2_PARAM_NAME>   …   <TABLE1_PARAM_NAME>     <STRUCT1_PARAM_NAME>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </STRUCT1_PARAM_NAME>     …   </TABLE1_PARAM_NAME>   … </[RFC_NAME]Response>`      | RFC を返します。<br /><br /> -エクスポート、変更、およびテーブル パラメーターがサポートされます。<br /><br /> **注:** 応答メッセージに表示しないテーブル パラメーターの既定では、します。 応答メッセージのテーブルのパラメーターが必要な場合は、要求メッセージ内で空のテーブルのパラメーターを渡す必要があります。<br /><br /> -インポート SAP 構造体の型、テーブル型の SAP または SAP の単純なデータ型のパラメーターを変更できます。 |
|         RfcGetAttributes<br /><br /> (RfcGetAttributes)          |                                                                                                                                                                                                                `<RfcGetAttributes> </RfcGetAttributes>`                                                                                                                                                                                                                |                                                  RfcGetAttributes RFC SDK の API 操作によって表示されるは、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 RfcGetAttributes 操作により、クライアント プログラムが、言語、システム ID、および RFC 接続に関連付けられているパートナーのコード ページを取得します。                                                   |
| RfcGetAttributes 応答<br /><br /> (RfcGetAttributesResponse) |                                                                                                                                                          `<RfcGetAttributesResponse>   <Language>lang</Language>   <SysId>id</SysId>   <PartnerCodePage>pnrcp</PartnerCodePage> </RfcGetAttributesResponse>`                                                                                                                                                           |                                                                                                                              RfcGetAttributes 操作に対する応答は、言語、システム ID、および RFC 接続に関連付けられているパートナーのコード ページを返します。                                                                                                                              |

 [バージョン] = メッセージ バージョン文字列。たとえば、 http://Microsoft.LobServices.SAP/2007/03 します。  

 [RFC_NAME] RFC; の名前を =たとえば、RFC_CUSTOMER_GET です。  

 [IN_PARAM_NAME] = RFC インポート パラメーターの名前。  

 [OUT_PARAM_NAME] = RFC エクスポートのパラメーターの名前。  

 [INOUT_PARAM_NAME] = RFC を変更するパラメーターの名前。  

 [TABLE_PARAM_NAME] = RFC テーブル パラメーターの名前。  

 [STRUCT_PARAM_NAME] = 構造の RFC パラメーターの名前。  

## <a name="message-actions-for-rfc-operations"></a>RFC 操作のメッセージのアクション  
 次の表では、RFC 操作のメッセージのアクションを示します。  


|         演算         |           メッセージのアクション           |                                例                                 |
|---------------------------|------------------------------------|------------------------------------------------------------------------|
|        [RFC_NAME]         |      [VERSION]/Rfc/[RFC_NAME]      |     http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET      |
|    [RFC_NAME]応答    | [VERSION]/Rfc/[RFC_NAME]/response  | http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET/response |
|     RfcGetAttributes      |     [バージョン]/RfcGetAttributes     |       http://Microsoft.LobServices.Sap/2007/03/RfcGetAttributes        |
| RfcGetAttributes 応答 | [VERSION/RfcGetAttributes/response |   http://Microsoft.LobServices.Sap/2007/03/RfcGetAttributes/response   |

 [バージョン] = メッセージ バージョン文字列。たとえば、http://Microsoft.LobServices.Sap/2007/03します。  

 [RFC_NAME]; 呼び出す RFC の名前を =たとえば、RFC_CUSTOMER_GET です。  

## <a name="invoking-a-bapi-as-an-rfc-operation"></a>RFC 操作として BAPI を呼び出す  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] RFC 操作、およびビジネス オブジェクトのメソッドとして Bapi 明らかになります。 RFC の操作として Bapi は名前で表示されます。 ビジネス オブジェクトのインターフェイスを使用して Bapi を呼び出す方法の詳細については、次を参照してください。 [SAP の Bapi に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)します。  

 次の XML では、RFC として呼び出される BAPI (BAPI_CUSTOMER_GETDETAIL2) のメッセージ構造を示します。 この操作のメッセージ アクション: http://Microsoft.LobServices.Sap/2007/03/Rfc/BAPI_CUSTOMER_GETDETAIL2 します。  

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
 [メッセージと BizTalk adapter for mySAP Business Suite のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)