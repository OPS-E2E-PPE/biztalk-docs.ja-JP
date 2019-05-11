---
title: 公開済み WCF サービスでの SOAP ヘッダー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- publishing, SOAP headers [WCF services]
- SOAP headers, WCF services
- WCF services, SOAP headers
ms.assetid: 5564a57e-e241-4595-a959-4289c8502410
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d8a133dc15f88d35fe55d82c651738b15af69133
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244326"
---
# <a name="soap-headers-with-published-wcf-services"></a>公開済み WCF サービスでの SOAP ヘッダー
WCF 受信アダプタへの受信メッセージですべての SOAP ヘッダーの値をコピーすることができます、 **InboundHeaders**プロパティ、またはこれらできます記述または指定された値を BizTalk メッセージ コンテキストに昇格します。 アダプターは、カスタム SOAP ヘッダーと WS アドレス指定など、WCF インフラストラクチャが使用する標準 SOAP ヘッダーの両方で作業でき、Ws-security、WS-AtomicTransaction します。 **InboundHeaders**コンテキスト プロパティは、ターゲットの名前空間**http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties**、受信メッセージの SOAP ヘッダーの値の文字列表現が含まれています。  
  
> [!NOTE]
>  指定した SOAP ヘッダーの値を昇格する場合は、必要があります配置されたプロパティ スキーマで昇格する値に対応する BizTalk プロジェクト。  
  
> [!NOTE]
>  昇格させたプロパティは、256 文字より長くすることはできません。  
  
 次の XML データの SOAP ヘッダーの文字列表現の例を示しています、 **InboundHeaders**プロパティ。 これが、クライアントから取得され、BizTalk に送信される受信場所。  
  
```  
<headers>  
<a:Action s:mustUnderstand="1" xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">Operation_1</a:Action>  
<SalesAgent xmlns="Microsoft.Samples.BizTalk.WCF.CustomSoapHeaderPipeline">Contoso</SalesAgent>  
<a:MessageID xmlns:a="http://www.w3.org/2005/08/addressing">urn:uuid:26e6720f-5a82-4ef2-b597-6ef077bab92e</a:MessageID>  
<a:ReplyTo xmlns:a="http://www.w3.org/2005/08/addressing"><a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address></a:ReplyTo>  
<a:To s:mustUnderstand="1" xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">net.tcp://localhost:9990/NetTcpOrderProcess</a:To>  
</headers>  
```  
  
 SOAP ヘッダーの値を BizTalk メッセージ コンテキストに昇格を書き込んだり、WCF アダプターはヘッダーの値が書き込みまたは昇格することを認識できるように、WCF メッセージにプロパティ名と名前空間で構成される値のペアのコレクションを配置する必要があります。 WCF アダプターで SOAP ヘッダーの値を BizTalk メッセージ コンテキストに書き込む、または昇格させるには、WCF メッセージで次のメッセージ プロパティを指定する必要があります。  
  
- BizTalk メッセージ コンテキストに SOAP ヘッダーの値を昇格するには、WCF アダプターを検索して、キーのペアを**http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties/Promote**と値**一覧\<KeyValuePair\<XmlQualifiedName、オブジェクト\>\>**.  
  
   このペアを使用して、WCF アダプタを名前空間、名前、および値から、 **XmlQualifiedName**オブジェクトし、ヘッダーの値を昇格する場合に使用します。  
  
- 書き込むが、SOAP ヘッダーの値を BizTalk メッセージ コンテキストに昇格させること、WCF アダプターを検索して、キーのペアを**http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties/WriteToContext**と値**一覧\<KeyValuePair\<XmlQualifiedName、オブジェクト\>\>** します。  
  
   WCF アダプターは、このペアを使用して、値をメッセージ コンテキストに書き込みます。  
  
  次のコードでは、書き込みまたは SOAP ヘッダーの値を BizTalk メッセージ コンテキストに昇格する方法を示します。  
  
```  
const string PropertiesToPromoteKey="http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties/Promote";  
const string PropertiesToWriteKey="http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties/WriteToContext";  
  
XmlQualifiedName PropName1=new XmlQualifiedName("Destination", "http://tempuri.org/2007/sample-properties");  
XmlQualifiedName PropName2=new XmlQualifiedName("Source", "http://tempuri.org/2007/sample-properties");  
  
//Create a List of KeyValuePairs that indicate properties to be promoted to BizTalk message context.   
//A Property Schema must be deployed and string values have a limit of 256 characters  
List<KeyValuePair<XmlQualifiedName, object>> promoteProps=new List<KeyValuePair<XmlQualifiedName, object>>();  
promoteProps.Add(new KeyValuePair<XmlQualifiedName, object>(PropName1, "Property value"));  
wcfMessage.Properties[PropertiesToPromoteKey]=promoteProps;  
  
//Create a List of KeyValuePairs that indicate properties to be written to BizTalk message context  
List<KeyValuePair<XmlQualifiedName, object>> writeProps=new List<KeyValuePair<XmlQualifiedName, object>>();  
writeProps.Add(new KeyValuePair<XmlQualifiedName, object>(PropName2, "Property value"));  
wcfMessage.Properties[PropertiesToWriteKey]=writeProps;  
```  
  
 BizTalk WCF サービス公開ウィザードでは、生成されたメタデータでのカスタム SOAP ヘッダーの定義が含まれません。 カスタム SOAP ヘッダーを使用して WCF サービスのメタデータを公開するには、手動で Web サービス記述言語 (WSDL) ファイルを作成する必要があります。 使用することができます、 **externalMetadataLocation**の属性、 [ \<serviceMetadata\> ](http://go.microsoft.com/fwlink/?LinkId=89121)の場所を指定して、ウィザードが生成する Web.config ファイル内の要素、WSDL ファイルです。 WSDL ファイルをユーザーに応答で返される WSDL およびメタデータを自動生成された WSDL ではなく exchange (MEX) 要求します。  
  
 次の XML データは、カスタム SOAP ヘッダーを定義する WSDL ファイルの一部の例を示します。  
  
```  
<wsdl:operation name="Request">  
  <soap12:operation soapAction="http://Microsoft.Samples.BizTalk.NetTcpAdapter/OrderProcess/IOrderProcess/Request" style="document" />   
   <wsdl:input name="Order">  
     <soap12:header message="i0:Order_Headers" part="SalesAgent" use="literal" />   
     <soap12:body use="literal" />   
   </wsdl:input>  
   <wsdl:output name="OrderConfirmation">  
     <soap12:header message="i0:OrderConfirmation_Headers" part="PaymentAgent" use="literal" />   
     <soap12:body use="literal" />   
   </wsdl:output>  
</wsdl:operation>  
```  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [オーケストレーションにおける WCF メッセージでの SOAP ヘッダーへのアクセス](../core/accessing-soap-headers-in-wcf-messages-with-orchestrations.md)  
  
-   [パイプライン コンポーネントにおける WCF メッセージでの SOAP ヘッダーへのアクセス](../core/accessing-soap-headers-in-wcf-messages-with-pipeline-components.md)  
  
## <a name="see-also"></a>参照  
 [WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md)   
 [消費済み WCF サービスでの SOAP ヘッダー](../core/soap-headers-with-consumed-wcf-services.md)