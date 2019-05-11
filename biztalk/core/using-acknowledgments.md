---
title: 受信確認の使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, publishing
- messages, acknowledgements
- BTS.AckSendPortID property
- BTS.AckSendPortName property
- BTS.AckType property
- BTS.AckFailureCode property
- BTS.AckID property
- acknowledgements, positive
- SOAP fault
- BTS.AckReceivePortID property
- BTS.AckReceivePortName property
- BTS.AckInboundTransportLocation property
- BTS.AckOutboundTransportLocation property
- messages, successful transmission
- BTS.AckDescription property
- orchestrations, messages
- acknowledgements, negative
- BTS.CorrelationToken property
- BTS.AckFailureCategory property
- positive acknowledgements (ACK)
- BTS.AckOwnerID property
ms.assetid: 2e5986d4-9633-4b7b-8ff3-fa3da93c5400
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec79910977625c7e93bac1e70b0f482a0db67677
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399950"
---
# <a name="using-acknowledgments"></a>受信確認の使用
BizTalk メッセージング エンジンは、ポート経由でメッセージの処理中に発生した状態に肯定受信確認応答 (ACK) および否定受信確認応答 (NACK) を生成します。 BizTalk Server では、メッセージの送信が成功を示す肯定受信確認と転送の失敗やメッセージの中断を示す否定受信確認応答をパブリッシュします。  
  
## <a name="why-use-acknowledgments"></a>受信確認を使用する理由  
 肯定および否定受信確認は、メッセージが送信先に到着したか、途中の 1 つまたは複数の問題が発生したかを判断するために使用できる強力なフィードバックを提供します。 たとえば、受信確認は便利な場合です。  
  
- スキーマ検証のための新しい取引先パートナーとその他のエラーの受信ポートを監視するには。  
  
- 正常に承認のため、パートナーに送信されるか (たとえば、パートナーのサーバーでは、ダウン) 場合、送信が失敗した場合は「失敗」の場合は、「インプロセス」として承認用に送信、ローン申請の状態をマークするには。  
  
- 複数の購買発注書を含むインターチェンジを処理し、送信または転送に失敗した注文数を追跡します。  
  
  これらの各シナリオは、受信確認とフィルターを使用するコンテンツ ベース ルーティングを使用して行うことができます。  
  
## <a name="routing-acknowledgments"></a>受信確認のルーティング  
 ACK または NACK が発行されると、すべての ACK または NACK を原因となったメッセージからメッセージ コンテキスト プロパティは降格されます。 昇格されたプロパティは、受信確認をフローしません。 受信確認をルーティングするには、次のプロパティを使用してフィルターを作成、 **BTS**名前空間。  
  
|プロパティ名|データ型|説明|  
|-------------------|---------------|-----------------|  
|BTS します。AckFailureCategory|xs:int|識別、 **ErrorCategory**場所と、中断の理由を提供します。|  
|BTS.AckFailureCode|xs:string|識別、 **ErrorCode**場所と、中断の理由を提供します。|  
|BTS.AckType|xs:string|値は、肯定受信確認と NACK の ACK を否定受信確認の場合です。|  
|BTS します。AckID|xs:string|識別、 **MessageID**元のメッセージ。|  
|BTS.AckOwnerID|xs:string|元のメッセージ インスタンス ID を識別します。|  
|BTS.CorrelationToken|xs:string|1 つが存在する場合は、元のメッセージの関連付けトークンを識別します。|  
|BTS します。AckDescription|xs:string|識別、 **ErrorDescription**場所と、中断の理由を提供します。|  
|BTS.AckSendPortID|xs:string|識別、 **SendPortID**元のメッセージ。|  
|BTS.AckSendPortName|xs:string|識別、 **SendPortName**元のメッセージ。|  
|BTS します。AckOutboundTransportLocation|xs:string|識別、 **OutboundTransportLocation**元のメッセージ。|  
|BTS します。AckReceivePortID|xs:string|識別、 **ReceivePortID**元のメッセージ。|  
|BTS.AckReceivePortName|xs:string|識別、 **ReceivePortName**元のメッセージ。|  
|BTS します。AckInboundTransportLocation|xs:string|識別、 **InboundTransportLocation**元のメッセージ。|  
  
> [!NOTE]
>  エラー情報を含むプロパティは、ので、正の配信は Ack に存在しません。  
  
## <a name="negative-acknowledgment-message-body"></a>否定受信確認応答メッセージの本文  
 多くの肯定または否定応答に関する重要な情報は、コンテキスト プロパティに含まれています。 Nack メッセージには、コンテキストのプロパティだけでなく、SOAP エラーを含むメッセージのボディ部も含まれます。 SOAP エラーの形式は次のとおりです。  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<SOAP:Envelope xmlns:SOAP="http://schemas.xmlsoap.org/soap/envelope/" SOAP:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">  
  <SOAP:Body>  
    <SOAP:Fault>  
      <faultcode>Microsoft BizTalk Server Negative Acknowledgment </faultcode>  
      <faultstring>An error occurred while processing the message, refer to the details section for more information </faultstring>  
      <faultactor>C:\Projects\Sample\Locations\Response\FM_%MessageID%.xml</faultactor>  
      <detail>  
        <ns0:NACK Type="NACK" xmlns:ns0="http://schema.microsoft.com/BizTalk/2003/NACKMessage.xsd">  
          <NAckID>{FFB1A60B-E593-4620-8897-4E9C7030A937}</NAckID>  
          <ErrorCode>0xc0c01658</ErrorCode>  
          <ErrorCategory>0</ErrorCategory>  
          <ErrorDescription>There was a failure executing the send pipeline: "Microsoft.BizTalk.DefaultPipelines.XMLTransmit, Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" Source: "XML assembler" Send Port: "Failed Message" URI: "C:\Projects\Sample\Locations\Response\FM_%MessageID%.xml" Reason: This Assembler cannot retrieve a document specification using this type: "http://Sample#Unknown".  </ErrorDescription>  
        </ns0:NACK>  
      </detail>  
    </SOAP:Fault>  
  </SOAP:Body>  
</SOAP:Envelope>  
```  
  
 アダプターによって発生した例外メッセージは、ErrorDescription 要素の SOAP 詳細セクションでです。  
  
### <a name="accessing-the-message-body-from-an-orchestration"></a>オーケストレーションからメッセージの本文にアクセスします。  
 配信通知を必要とするオーケストレーション ポートがある場合は、転送エラーの発生時にスローされる DeliveryFailureException は、NACK メッセージ本文に含まれる SOAP エラーから逆シリアル化します。 オーケストレーション内から例外メッセージ文字列にアクセスするには、DeliveryFailureException を SoapException にキャストし、次のコードに示すようにし、InnerXml にアクセスします。  
  
```  
// Cast the DeliveryFailureException to a SoapException…  
System.Web.Services.Protocols.SoapException se = (System.Web.Services.Protocols.SoapException)e.InnerException;  
System.Diagnostics.Trace.WriteLine(se.Detail.InnerXml);  
//e is an Microsoft.XLANGs.BaseTypes.DeliveryFailureException  
//object type created in an Exception handler  
```  
  
 上記のコード サンプルは、次のような XML フラグメントを返します。  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<ns0:NACK Type="NACK" xmlns:ns0="http://schema.microsoft.com/BizTalk/2003/NACKMessage.xsd">  
  <NAckID>{FFB1A60B-E593-4620-8897-4E9C7030A937}</NAckID>  
  <ErrorCode>0xc0c01658</ErrorCode>  
  <ErrorCategory>0</ErrorCategory>  
  <ErrorDescription>There was a failure executing the send pipeline: "Microsoft.BizTalk.DefaultPipelines.XMLTransmit, Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" Source: "XML assembler" Send Port: "Failed Message" URI: "C:\Projects\Sample\Locations\Response\FM_%MessageID%.xml" Reason: This Assembler cannot retrieve a document specification using this type: "http://Sample#Unknown".</ErrorDescription>  
</ns0:NACK>  
```  
  
## <a name="when-is-an-acknowledgment-published"></a>受信確認が発行される場合  
 少なくとも 1 つの一致するサブスクリプションが提供される (ACK) の正と負の値 (NACK) の受信確認の両方が失敗した時点で、メッセージ ボックス データベースに発行されます。 たとえば、受信ポートからメッセージを読み取るし、NACK サブスクリプションがないために、BizTalk Server では、一致するスキーマを見つけることができない場合、メッセージが中断 (かどうか失敗したメッセージのルーティングが有効でない)、NACK を公開しません  
  
## <a name="see-also"></a>参照  
 [エラー処理](../core/error-handling.md)   
 [失敗したメッセージのルーティングを使用します。](../core/using-failed-message-routing.md)