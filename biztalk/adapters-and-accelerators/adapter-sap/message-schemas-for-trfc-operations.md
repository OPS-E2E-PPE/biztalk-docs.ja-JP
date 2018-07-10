---
title: TRFC 操作のメッセージ スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tRFC operations, message structure for
- tRFC operations, message schemas for
- tRFC operations, message actions for
ms.assetid: 0e269555-f0a1-40ae-a1b5-d8c4981e730f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a25413854b35a7bd27b3621a9c8ddfff31f083a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999779"
---
# <a name="message-schemas-for-trfc-operations"></a>TRFC 操作のメッセージ スキーマ
Transactiostructnal リモート関数呼び出し (Trfc) は、作業 (LUW) の論理単位での RFC 呼び出しの実行に使用されます。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]受信 tRFC 呼び出しの LUW ごとの複数の Trfc をサポートしています。 TRFC の呼び出しを送信 (クライアント) のアダプターは、;、LUW で tRFC は 1 つのみをサポートできます。そのための作成、LUW で SAP クライアント tRFC の呼び出しごとにされます。 方法の詳細については[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]、tRFC 操作のサポートを参照してください[SAP の Trfc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)します。 このセクションでは、メッセージ スキーマと tRFC 操作のアクションについて説明します。  

## <a name="message-structure-for-trfc-operations"></a>TRFC 操作のメッセージの構造  
 各 tRFC 操作は、要求メッセージと応答 (応答) メッセージで構成されます。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムのトランザクション ID (TID)、LUW で SAP システムを識別する GUID を関連付けます。 この GUID は、どちらの tRFC 要求と応答メッセージ内で使用できる、 \<TransactionalRfcOperationIdentifier\>要素。  

-   送信 tRFC の呼び出しに対して、tRFC 要求メッセージでアダプターに GUID を渡すことができます。 GUID を指定しない場合、いずれかのアダプターが生成されます。 アダプターは常に、tRFC 応答メッセージの GUID を返します。 SAP システムで TID を確認する RfcConfirmTransID 操作では、この GUID を渡します。  

-   受信 tRFC の呼び出しは、アダプターは、生成を持ち、tRFC の要求メッセージ内で SAP TID にマップする GUID を渡します。 必要に応じて、応答メッセージにこの GUID を取得できます。  

> [!IMPORTANT]
>  SAP システムの問題をトラブルシューティングする例については、一部のシナリオでは、SAP システムで tRFC を識別する SAP TID の実際の値を必要があります。 呼び出すことによって、GUID に関連付けられている SAP TID の値を取得することができます、 **ConvertGuidToTid**メソッド。 詳細については**ConvertGuidToTid**を参照してください[特別な操作](../../adapters-and-accelerators/adapter-sap/special-operations.md)します。  

 TRFC 操作や、RfcConfirmTransID 操作に使用されるメッセージ スキーマを次の表に示します。 TRFC の呼び出しをクライアントでの SAP TID を確認するように、アダプターによって RfcConfirmTransID 操作が表示されます。  


|                             演算                             |                                                                                                                                                                                                                                                                         XML の構造体                                                                                                                                                                                                                                                                         |                                                                                                                                                                                                                                                                                                                                                                                                                             説明                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                   tRFC<br /><br /> ([RFC_NAME])                   | `<[RFC_NAME] xmlns="[VERSION]/Trfc/">   <IN1_PARAM_NAME>v1</IN1_PARAM_NAME>   <IN2_PARAM_NAME>v2</IN2_PARAM_NAME>   …   <INOUT1_PARAM_NAME>v3</INOUT1_PARAM_NAME>   <INOUT2_PARAM_NAME>v4</INOUT2_PARAM_NAME>   …   <TABLE1_PARAM_NAME xmlns="[VERSION]/Types/Trfc/">     <STRUCT1_PARAM_NAME>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </STRUCT1_PARAM_NAME>     …   </TABLE1_PARAM_NAME>   …   <TransactionalRfcOperationIdentifier>GUID   </TransactionalRfcOperationIdentifier> </[RFC_NAME]>` | SAP システムでの tRFC を呼び出します。<br /><br /> -インポート、変更、およびテーブル パラメーターがサポートされます。<br /><br /> -インポート SAP 構造体の型、テーブル型の SAP または SAP の単純なデータ型のパラメーターを変更できます。<br /><br /> -tRFC クライアント呼び出しは、出力側に返される値はありません。 SAP では、入力側にある値のみを使用して非同期的に実行します。<br /><br /> \<TransactionalRfcOperationIdentifier\>要素。<br /><br /> -送信 tRFC の呼び出しはこの要素で、アダプターによって SAP TID を対応する GUID を指定することができます。 GUID が指定されていない場合、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を生成して、tRFC の SAP TID にマップします。<br /><br /> 受信 tRFC の呼び出しは、アダプターは、この要素内の SAP TID にマップされている GUID を渡します。 |
|          tRFC 応答<br /><br /> ([RFC_NAME] 応答)           |                                                                                                                                                                                                   `<[RFC_NAME]Response xmlns="[VERSION]/Trfc/">   <TransactionalRfcOperationIdentifier>GUID   </TransactionalRfcOperationIdentifier> </[RFC_NAME]Response>`                                                                                                                                                                                                   |                                                                                                                                                                   RFC が SAP システムに送信されたことを示します。<br /><br /> -tRFC クライアント呼び出しは、出力側に返される値はありません。 SAP では、入力側にある値のみを使用して非同期的に実行します。<br /><br /> \<TransactionalRfcOperationIdentifier\>要素。<br /><br /> -送信 tRFC の呼び出しについては、アダプターは、この要素で tRFC の SAP TID に関連付けられている GUID を送信します。<br /><br /> -受信 tRFC 呼び出しを必要に応じて、要求メッセージで、アダプターによって送信された GUID を取得できます。                                                                                                                                                                    |
|         RfcConfirmTransID<br /><br /> (RfcConfirmTransID)         |                                                                                                                                                                                                    `<RfcConfirmTransID xmlns="[VERSION]/Trfc/">   <TransactionalRfcOperationIdentifier>GUID   </TransactionalRfcOperationIdentifier> </RfcConfirmTransID>`                                                                                                                                                                                                    |                                                                                                                                                             RfcConfirmTransID 操作は、SAP システムに対する送信 tRFC 操作で使用される TID を確認します。<br /><br /> \<TransactionalRfcOperationIdentifier\>要素には、送信 tRFC の呼び出しに関連付けられている TID にマップされている GUID が含まれています。 TRFC の応答メッセージで、アダプターによって返された GUID の値に設定する必要があります。<br /><br /> RfcConfirmTransID 操作に関する詳細については、次を参照してください。[特別な操作](../../adapters-and-accelerators/adapter-sap/special-operations.md)します。                                                                                                                                                              |
| RfcConfirmTransIDResponse<br /><br /> (RfcConfirmTransIDResponse) |                                                                                                                                                                                                                                      `<RfcConfirmTransIDResponse xmlns="[VERSION]/Trfc/"> </RfcConfirmTransIDResponse>`                                                                                                                                                                                                                                       |                                                                                                                                                                                                                                                                                                                                                                   示します、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]が SAP システムで TID を確認します。                                                                                                                                                                                                                                                                                                                                                                    |

 [バージョン] = メッセージ バージョン文字列。たとえば、http://Microsoft.LobServices.Sap/2007/03します。  

 [RFC_NAME] RFC; の名前を =たとえば、RFC_CUSTOMER_GET です。  

 [IN_PARAM_NAME] = RFC インポート パラメーターの名前。  

 [INOUT_PARAM_NAME] = RFC を変更するパラメーターの名前。  

 [TABLE_PARAM_NAME] = RFC テーブル パラメーターの名前。  

 [STRUCT_PARAM_NAME] = [構造の RFC パラメーターの名前。  

 GUID、tRFC に関連付けられている SAP TID を識別する GUID を = です。  

## <a name="message-actions-for-trfc-operations"></a>TRFC 操作のメッセージのアクション  
 TRFC 操作に使用されるメッセージのアクションを次の表に示します。  


|         演算          |              メッセージのアクション              |                                 例                                  |
|----------------------------|------------------------------------------|--------------------------------------------------------------------------|
|         [RFC_NAME]         |        [バージョン]/Trfc/[RFC_NAME]         |      http://Microsoft.LobServices.Sap/2007/03/Trfc/RFC_CUSTOMER_GET      |
|    [RFC_NAME]応答     |    [VERSION]/Trfc/[RFC_NAME]/response    | http://Microsoft.LobServices.Sap/2007/03/Trfc/RFC_CUSTOMER_GET/response  |
|     RfcConfirmTransID      |     [VERSION]/Trfc/RfcConfirmTransID     |     http://Microsoft.LobServices.Sap/2007/03/Trfc/RfcConfirmTransID      |
| RfcConfirmTransID 応答 | [VERSION/Trfc/RfcConfirmTransID/response | http://Microsoft.LobServices.Sap/2007/03/Trfc/RfcConfirmTransID/response |

 [バージョン] = メッセージ バージョン文字列。たとえば、http://Microsoft.LobServices.Sap/2007/03します。  

 [RFC_NAME]; 呼び出す RFC の名前を =たとえば、RFC_CUSTOMER_GET です。  

## <a name="see-also"></a>参照  
 [メッセージと BizTalk adapter for mySAP Business Suite のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)