---
title: 受信確認の使用 |Microsoft ドキュメント
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
ms.openlocfilehash: 0c3a5363ee70a67c5882088af9fa3d2f4b805823
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288186"
---
# <a name="using-acknowledgments"></a>受信確認の使用
BizTalk メッセージング エンジンは、ポートを通じたメッセージの処理中に発生した条件に応じて、肯定受信確認応答 (ACK) および否定受信確認応答 (NACK) を生成します。 BizTalk Server では、メッセージの転送が成功したことを示す受信確認、および転送の失敗やメッセージの中断を示す否定受信確認応答を作成します。  
  
## <a name="why-use-acknowledgments"></a>受信確認を使用する理由  
 受信確認および否定受信確認応答は、強力なフィードバックを提供します。このフィードバックを使用して、メッセージが送信先に到達したかどうか、途中で問題が発生したかどうかを判断できます。 たとえば、受信確認は、次の場合に役立ちます。  
  
-   スキーマの検証や他のエラーの調査を行うため、新しい取引先の受信ポートを監視する。  
  
-   取引先に承認用のローン要求が正常に送信された場合に、"インプロセス" としてその状態をマークする。または、転送に失敗した場合 (取引先のサーバーがダウンしている場合など) に "失敗" としてその状態をマークする。  
  
-   複数の注文書を含むインターチェンジを処理し、転送された注文数または転送に失敗した注文数を追跡する。  
  
 フィルターを使用するコンテンツ ベースのルーティングと受信確認を使用して、これらの各シナリオを実現できます。  
  
## <a name="routing-acknowledgments"></a>受信確認のルーティング  
 ACK または NACK が生成されると、ACK/NACK を発生させたメッセージのすべてのメッセージ コンテキスト プロパティが降格します。 昇格させたプロパティは、受信確認に流れません。 受信確認をルーティングする次のプロパティを使用してフィルターを作成、 **BTS**名前空間。  
  
|プロパティ名|データ型|Description|  
|-------------------|---------------|-----------------|  
|BTS.AckFailureCategory|xs:int|識別、 **ErrorCategory**場所と中断理由を提供します。|  
|BTS.AckFailureCode|xs:string|識別、 **ErrorCode**場所と中断理由を提供します。|  
|BTS.AckType|xs:string|受信確認の値は ACK、否定受信確認応答の値は NACK です。|  
|BTS.AckID|xs:string|識別、 **MessageID**元のメッセージ。|  
|BTS.AckOwnerID|xs:string|元のメッセージのインスタンス ID を確認します。|  
|BTS.CorrelationToken|xs:string|元のメッセージの関連付けトークン (存在する場合) を確認します。|  
|BTS.AckDescription|xs:string|識別、 **ErrorDescription**場所と中断理由を提供します。|  
|BTS.AckSendPortID|xs:string|識別、 **SendPortID**元のメッセージ。|  
|BTS.AckSendPortName|xs:string|識別、 **SendPortName**元のメッセージ。|  
|BTS.AckOutboundTransportLocation|xs:string|識別、 **OutboundTransportLocation**元のメッセージ。|  
|BTS.AckReceivePortID|xs:string|識別、 **ReceivePortID**元のメッセージ。|  
|BTS.AckReceivePortName|xs:string|識別、 **ReceivePortName**元のメッセージ。|  
|BTS.AckInboundTransportLocation|xs:string|識別、 **InboundTransportLocation**元のメッセージ。|  
  
> [!NOTE]
>  エラー情報を含むプロパティは、配信確認で示されるので、ACK に存在しません。  
  
## <a name="negative-acknowledgment-message-body"></a>否定受信確認応答のメッセージ本文  
 受信確認および否定受信確認応答に関する重要な情報の多くは、コンテキスト プロパティに格納されています。 コンテキスト プロパティ以外に、NACK には、SOAP エラーを含むメッセージの本文部分があります。 SOAP エラーの形式を次に示します。  
  
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
  
 アダプターによって生成される例外メッセージは、ErrorDescription 要素の SOAP 詳細セクションにあります。  
  
### <a name="accessing-the-message-body-from-an-orchestration"></a>オーケストレーションからメッセージ本文へアクセスする  
 配信通知を必要とするオーケストレーション ポートを使用している場合、送信エラーがスローされる DeliveryFailureException は、NACK メッセージ本文に含まれる SOAP エラーからシリアル化解除されます。 オーケストレーションの例外のメッセージ文字列にアクセスするには、DeliveryFailureException を SoapException にキャストし、次のコードで示されるように InnerXml にアクセスします。  
  
```  
// Cast the DeliveryFailureException to a SoapException…  
System.Web.Services.Protocols.SoapException se = (System.Web.Services.Protocols.SoapException)e.InnerException;  
System.Diagnostics.Trace.WriteLine(se.Detail.InnerXml);  
//e is an Microsoft.XLANGs.BaseTypes.DeliveryFailureException  
//object type created in an Exception handler  
```  
  
 上記のサンプル コードは、次のような XML フラグメントを返します。  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<ns0:NACK Type="NACK" xmlns:ns0="http://schema.microsoft.com/BizTalk/2003/NACKMessage.xsd">  
  <NAckID>{FFB1A60B-E593-4620-8897-4E9C7030A937}</NAckID>  
  <ErrorCode>0xc0c01658</ErrorCode>  
  <ErrorCategory>0</ErrorCategory>  
  <ErrorDescription>There was a failure executing the send pipeline: "Microsoft.BizTalk.DefaultPipelines.XMLTransmit, Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" Source: "XML assembler" Send Port: "Failed Message" URI: "C:\Projects\Sample\Locations\Response\FM_%MessageID%.xml" Reason: This Assembler cannot retrieve a document specification using this type: "http://Sample#Unknown".</ErrorDescription>  
</ns0:NACK>  
```  
  
## <a name="when-is-an-acknowledgment-published"></a>受信確認が生成される場合とは  
 少なくとも 1 つのサブスクリプションが一致する場合、肯定受信確認応答 (ACK) および否定受信確認応答 (NACK) の両方が障害発生時点のメッセージ ボックス データベースに生成されます。 たとえば、受信ポートから読み込まれるメッセージに一致するスキーマを BizTalk Server が検出できず、NACK サブスクリプションがない場合、メッセージが中断され (失敗したメッセージのルーティングが無効の場合)、NACK は生成されません。  
  
## <a name="see-also"></a>参照  
 [エラー処理](../core/error-handling.md)   
 [失敗したメッセージのルーティングを使用します。](../core/using-failed-message-routing.md)