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
ms.openlocfilehash: ea48ab7afeae2b54136c9134d3ef92878b802924
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985371"
---
# <a name="soap-headers-with-published-wcf-services"></a>公開済み WCF サービスでの SOAP ヘッダー
WCF 受信アダプタへの受信メッセージですべての SOAP ヘッダーの値をコピーすることができます、 **InboundHeaders**プロパティ、またはこれらできます記述または指定された値を BizTalk メッセージ コンテキストに昇格します。 WCF アダプタでは、カスタムの SOAP ヘッダーと、WCF インフラストラクチャが使用する WS-Addressing、WS-Security、WS-AtomicTransaction などの標準 SOAP ヘッダーの両方を処理できます。 **InboundHeaders**コンテキスト プロパティは、ターゲットの名前空間**http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties**、受信メッセージの SOAP ヘッダーの値の文字列表現が含まれています。  
  
> [!NOTE]
>  指定した SOAP ヘッダーの値を昇格させる場合は、昇格対象の値に対応するプロパティ スキーマが、BizTalk プロジェクト内で展開されている必要があります。  
  
> [!NOTE]
>  昇格されたプロパティの長さは 256 文字以下にしてください。  
  
 次の XML データの SOAP ヘッダーの文字列表現の例を示しています、 **InboundHeaders**プロパティ。 これはクライアントから渡されて、BizTalk 受信場所に送信されます。  
  
```  
<headers>  
<a:Action s:mustUnderstand="1" xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">Operation_1</a:Action>  
<SalesAgent xmlns="Microsoft.Samples.BizTalk.WCF.CustomSoapHeaderPipeline">Contoso</SalesAgent>  
<a:MessageID xmlns:a="http://www.w3.org/2005/08/addressing">urn:uuid:26e6720f-5a82-4ef2-b597-6ef077bab92e</a:MessageID>  
<a:ReplyTo xmlns:a="http://www.w3.org/2005/08/addressing"><a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address></a:ReplyTo>  
<a:To s:mustUnderstand="1" xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">net.tcp://localhost:9990/NetTcpOrderProcess</a:To>  
</headers>  
```  
  
 SOAP ヘッダーの値を BizTalk メッセージ コンテキストに書き込む、または昇格させるには、プロパティ名と名前空間で構成される値ペアのコレクションを WCF メッセージに挿入することにより、ヘッダー値の書き込みまたは昇格を実行する必要があることを、WCF アダプタが認識できるようにする必要があります。 WCF アダプターで SOAP ヘッダーの値を BizTalk メッセージ コンテキストに書き込む、または昇格させるには、WCF メッセージで次のメッセージ プロパティを指定する必要があります。  
  
- BizTalk メッセージ コンテキストに SOAP ヘッダーの値を昇格するには、WCF アダプターを検索して、キーのペアを**http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties/Promote**と値**一覧\<KeyValuePair\<XmlQualifiedName、オブジェクト\>\>**.  
  
   このペアを使用して、WCF アダプタを名前空間、名前、および値から、 **XmlQualifiedName**オブジェクトし、ヘッダーの値を昇格する場合に使用します。  
  
- 書き込むが、SOAP ヘッダーの値を BizTalk メッセージ コンテキストに昇格させること、WCF アダプターを検索して、キーのペアを**http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties/WriteToContext**と値**一覧\<KeyValuePair\<XmlQualifiedName、オブジェクト\>\>** します。  
  
   WCF アダプターは、このペアを使用して、値をメッセージ コンテキストに書き込みます。  
  
  次のコードは、SOAP ヘッダーの値を BizTalk メッセージ コンテキストに書き込む、または昇格させる方法を示しています。  
  
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
  
 BizTalk WCF サービス公開ウィザードで生成されたメタデータには、カスタム SOAP ヘッダーの定義が含まれません。 カスタム SOAP ヘッダーを使用して、WCF サービスにメタデータを公開するには、Web サービス記述言語 (WSDL) ファイルを手動で作成する必要があります。 使用することができます、 **externalMetadataLocation**の属性、 [ \<serviceMetadata\> ](http://go.microsoft.com/fwlink/?LinkId=89121)の場所を指定して、ウィザードが生成する Web.config ファイル内の要素、WSDL ファイルです。 この WSDL ファイルは、WSDL およびメタデータ交換 (MEX) 要求の応答として、自動生成された WSDL の代わりにユーザーに返されます。  
  
 次の XML データは、カスタム SOAP ヘッダーを定義する WSDL ファイルの一部を示しています。  
  
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