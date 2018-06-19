---
title: TRFC 操作のメッセージ スキーマ |Microsoft ドキュメント
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
ms.openlocfilehash: 5667d2f6a9f18bbccbdebc0d5dc36ad73e4867ec
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964920"
---
# <a name="message-schemas-for-trfc-operations"></a>TRFC 操作のメッセージ スキーマ
Transactiostructnal リモート関数呼び出し (tRFCs) は、作業 (LUW) の論理単位での RFC 呼び出しの実行に使用されます。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]受信 tRFC の呼び出しのため LUW あたり複数 tRFCs をサポートしています。 送信 (クライアント) tRFC の呼び出しのため、アダプターは、LUW; で tRFC は 1 つのみをサポートできます。そのための LUW に作成 SAP クライアント tRFC の呼び出しごとにします。 方法の詳細については[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]tRFC 操作をサポートするを参照してください[SAP で tRFCs に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)です。 このセクションでは、メッセージ スキーマと tRFC 操作のアクションについて説明します。  
  
## <a name="message-structure-for-trfc-operations"></a>TRFC 操作のメッセージの構造  
 各 tRFC 操作は、要求メッセージと応答 (応答) メッセージで構成されます。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システム トランザクション ID (TID) を SAP システムで LUW を識別する GUID を関連付けます。 この GUID は、どちらの tRFC 要求と応答メッセージ内で使用できる、 \<TransactionalRfcOperationIdentifier\>要素。  
  
-   送信 tRFC の呼び出しのため、tRFC 要求メッセージでアダプターに GUID を渡すことができます。 GUID を指定しない場合、アダプターでは、いずれかが生成されます。 アダプターは、常に tRFC 応答メッセージの GUID を返します。 SAP システムで TID を確認する RfcConfirmTransID 操作では、この GUID を渡します。  
  
-   受信 tRFC の呼び出し、アダプターが生成された、tRFC 要求メッセージ内の SAP TID にマップする GUID は渡されます。 この GUID は、応答メッセージのオプションで返すことができます。  
  
> [!IMPORTANT]
>  たとえば、SAP システム上の問題をトラブルシューティングするために、一部のシナリオでは、SAP システムで tRFC を識別する SAP TID の実際の値を必要があります。 呼び出すことによって、GUID に関連付けられている SAP TID の値を取得することができます、 **ConvertGuidToTid**メソッドです。 詳細については**ConvertGuidToTid**を参照してください[特別な操作](../../adapters-and-accelerators/adapter-sap/special-operations.md)です。  
  
 TRFC 操作と RfcConfirmTransID 操作に使用するメッセージ スキーマを次の表に示します。 クライアント tRFC の呼び出しで SAP TID を確認できるように、RfcConfirmTransID 操作は、アダプターによって確認できます。  
  
|操作|XML データ構造|Description|  
|---------------|-------------------|-----------------|  
|tRFC<br /><br /> ([RFC_NAME])|`<[RFC_NAME] xmlns="[VERSION]/Trfc/">   <IN1_PARAM_NAME>v1</IN1_PARAM_NAME>   <IN2_PARAM_NAME>v2</IN2_PARAM_NAME>   …   <INOUT1_PARAM_NAME>v3</INOUT1_PARAM_NAME>   <INOUT2_PARAM_NAME>v4</INOUT2_PARAM_NAME>   …   <TABLE1_PARAM_NAME xmlns="[VERSION]/Types/Trfc/">     <STRUCT1_PARAM_NAME>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </STRUCT1_PARAM_NAME>     …   </TABLE1_PARAM_NAME>   …   <TransactionalRfcOperationIdentifier>GUID   </TransactionalRfcOperationIdentifier> </[RFC_NAME]>`|SAP システムで tRFC を呼び出します。<br /><br /> に変更するインポートしてテーブル パラメーターがサポートされます。<br /><br /> -インポートし、SAP 構造体の型、SAP テーブル型または SAP 単純なデータ型のパラメーターを変更できます。<br /><br /> -tRFC クライアント呼び出しには、出力側で返される値はありません。 SAP では、入力側の値のみを使用して非同期的に実行します。<br /><br /> \<TransactionalRfcOperationIdentifier\>要素。<br /><br /> -送信 tRFC の呼び出しの GUID がこの要素で、アダプターで SAP TID にマップする必要がありますを指定することができます。 GUID が指定されていない場合、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]いずれかを生成し、tRFC の SAP TID にマップします。<br /><br /> -着信 tRFC の呼び出しに対しては、アダプターは、この要素内の SAP TID にマップされている GUID を渡します。|  
|tRFC 応答<br /><br /> ([RFC_NAME] 応答)。|`<[RFC_NAME]Response xmlns="[VERSION]/Trfc/">   <TransactionalRfcOperationIdentifier>GUID   </TransactionalRfcOperationIdentifier> </[RFC_NAME]Response>`|RFC が SAP システムに送信されたことを示します。<br /><br /> -tRFC クライアント呼び出しには、出力側で返される値はありません。 SAP では、入力側の値のみを使用して非同期的に実行します。<br /><br /> \<TransactionalRfcOperationIdentifier\>要素。<br /><br /> -に対して送信 tRFC の呼び出しは、アダプターは、この要素で tRFC の SAP TID に関連付けられている GUID を送信します。<br /><br /> -着信 tRFC の呼び出しのため、要求メッセージで、アダプターによって送信された GUID をオプションで返すことができます。|  
|RfcConfirmTransID<br /><br /> (RfcConfirmTransID)|`<RfcConfirmTransID xmlns="[VERSION]/Trfc/">   <TransactionalRfcOperationIdentifier>GUID   </TransactionalRfcOperationIdentifier> </RfcConfirmTransID>`|RfcConfirmTransID 操作は、SAP システムに対して送信 tRFC 操作で使用される TID を確認します。<br /><br /> \<TransactionalRfcOperationIdentifier\>要素には、送信 tRFC の呼び出しに関連付けられている TID にマップされている GUID が含まれています。 これは、tRFC 応答メッセージにアダプターによって返された GUID の値を設定する必要があります。<br /><br /> RfcConfirmTransID 操作に関する詳細については、次を参照してください。[特別な操作](../../adapters-and-accelerators/adapter-sap/special-operations.md)です。|  
|RfcConfirmTransIDResponse<br /><br /> (RfcConfirmTransIDResponse)|`<RfcConfirmTransIDResponse xmlns="[VERSION]/Trfc/"> </RfcConfirmTransIDResponse>`|示します、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムで TID を確認しています。|  
  
 [バージョン]、メッセージのバージョン文字列を =たとえば、http://Microsoft.LobServices.Sap/2007/03 です。  
  
 [RFC_NAME] RFC; の名前を =たとえば、RFC_CUSTOMER_GET です。  
  
 [IN_PARAM_NAME] RFC インポートのパラメーターの名前を = です。  
  
 [INOUT_PARAM_NAME] RFC を変更するパラメーターの名前を = です。  
  
 [TABLE_PARAM_NAME] RFC テーブル パラメーターの名前を = です。  
  
 [STRUCT_PARAM_NAME] RFC 構造パラメーターの名前を = です。  
  
 GUID を tRFC に関連付けられている SAP TID を識別する GUID を = です。  
  
## <a name="message-actions-for-trfc-operations"></a>TRFC 操作のメッセージの動作  
 TRFC 操作に使用されるメッセージのアクションを次の表に示します。  
  
|操作|メッセージのアクション|例|  
|---------------|--------------------|-------------|  
|[RFC_NAME]|[バージョン]/Trfc/[RFC_NAME]|http://Microsoft.LobServices.Sap/2007/03/Trfc/RFC_CUSTOMER_GET|  
|[RFC_NAME]応答|[バージョン]/Trfc/[RFC_NAME]/応答|http://Microsoft.LobServices.Sap/2007/03/Trfc/RFC_CUSTOMER_GET/response|  
|RfcConfirmTransID|[バージョン]/Trfc RfcConfirmTransID|http://Microsoft.LobServices.Sap/2007/03/Trfc/RfcConfirmTransID|  
|RfcConfirmTransID 応答|[バージョン/Trfc/RfcConfirmTransID/応答|http://Microsoft.LobServices.Sap/2007/03/Trfc/RfcConfirmTransID/response|  
  
 [バージョン]、メッセージのバージョン文字列を =たとえば、http://Microsoft.LobServices.Sap/2007/03 です。  
  
 [RFC_NAME]; 呼び出される RFC の名前を =たとえば、RFC_CUSTOMER_GET です。  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk Adapter 用 mySAP Business Suite のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)