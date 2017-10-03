---
title: "公開済み WCF サービスでの SOAP ヘッダー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- publishing, SOAP headers [WCF services]
- SOAP headers, WCF services
- WCF services, SOAP headers
ms.assetid: 5564a57e-e241-4595-a959-4289c8502410
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b62ebea1380e686a0afbf18dc63aedbfab190fac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="soap-headers-with-published-wcf-services"></a><span data-ttu-id="1f025-102">公開済み WCF サービスでの SOAP ヘッダー</span><span class="sxs-lookup"><span data-stu-id="1f025-102">SOAP Headers with Published WCF Services</span></span>
<span data-ttu-id="1f025-103">WCF 受信アダプター、受信メッセージにすべての SOAP ヘッダーの値をコピーすることができます、 **InboundHeaders**プロパティ、またはこれらを作成したりできます指定の値を BizTalk メッセージ コンテキストに昇格します。</span><span class="sxs-lookup"><span data-stu-id="1f025-103">The WCF receive adapters can copy all the SOAP header values in the inbound messages to the **InboundHeaders** property, or they can write or promote specified values to the BizTalk message context.</span></span> <span data-ttu-id="1f025-104">WCF アダプタでは、カスタムの SOAP ヘッダーと、WCF インフラストラクチャが使用する WS-Addressing、WS-Security、WS-AtomicTransaction などの標準 SOAP ヘッダーの両方を処理できます。</span><span class="sxs-lookup"><span data-stu-id="1f025-104">The adapters can work with both custom SOAP headers and standard SOAP headers that the WCF infrastructure uses, such as WS-Addressing, WS-Security, and WS-AtomicTransaction.</span></span> <span data-ttu-id="1f025-105">**InboundHeaders**コンテキスト プロパティがターゲットの名前空間内に**http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties**SOAP の文字列表現が含まれています受信メッセージのヘッダー値。</span><span class="sxs-lookup"><span data-stu-id="1f025-105">The **InboundHeaders** context property is in the target namespace **http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties**, and contains string representations of the SOAP header values in inbound messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1f025-106">指定した SOAP ヘッダーの値を昇格させる場合は、昇格対象の値に対応するプロパティ スキーマが、BizTalk プロジェクト内で展開されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f025-106">If you are going to promote the SOAP header values you specified, there must be a deployed property schema in your BizTalk project that corresponds to the values you are promoting.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1f025-107">昇格されたプロパティの長さは 256 文字以下にしてください。</span><span class="sxs-lookup"><span data-stu-id="1f025-107">The promoted properties cannot be longer than 256 characters.</span></span>  
  
 <span data-ttu-id="1f025-108">次の XML データの SOAP ヘッダーの文字列表現の例を示しています、 **InboundHeaders**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="1f025-108">The following XML data shows an example of the string representation of the SOAP headers for the **InboundHeaders** property.</span></span> <span data-ttu-id="1f025-109">これはクライアントから渡されて、BizTalk 受信場所に送信されます。</span><span class="sxs-lookup"><span data-stu-id="1f025-109">This comes from the client and is sent to the BizTalk receive location.</span></span>  
  
```  
<headers>  
<a:Action s:mustUnderstand="1" xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">Operation_1</a:Action>  
<SalesAgent xmlns="Microsoft.Samples.BizTalk.WCF.CustomSoapHeaderPipeline">Contoso</SalesAgent>  
<a:MessageID xmlns:a="http://www.w3.org/2005/08/addressing">urn:uuid:26e6720f-5a82-4ef2-b597-6ef077bab92e</a:MessageID>  
<a:ReplyTo xmlns:a="http://www.w3.org/2005/08/addressing"><a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address></a:ReplyTo>  
<a:To s:mustUnderstand="1" xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">net.tcp://localhost:9990/NetTcpOrderProcess</a:To>  
</headers>  
```  
  
 <span data-ttu-id="1f025-110">SOAP ヘッダーの値を BizTalk メッセージ コンテキストに書き込む、または昇格させるには、プロパティ名と名前空間で構成される値ペアのコレクションを WCF メッセージに挿入することにより、ヘッダー値の書き込みまたは昇格を実行する必要があることを、WCF アダプタが認識できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f025-110">To write or promote SOAP header values to the BizTalk message context, you need to put a collection of value pairs that consist of property name and namespace into the WCF message so that the WCF adapters will recognize that the header values are to be written or promoted.</span></span> <span data-ttu-id="1f025-111">WCF アダプターで SOAP ヘッダーの値を BizTalk メッセージ コンテキストに書き込む、または昇格させるには、WCF メッセージで次のメッセージ プロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f025-111">A WCF adapter expects the following message properties in the WCF messages for writing or promoting SOAP header values to the BizTalk message context:</span></span>  
  
-   <span data-ttu-id="1f025-112">BizTalk メッセージ コンテキストに SOAP ヘッダーの値を昇格するには、WCF アダプタを探しているキーのペアは、 **http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties/Promote**および値**リスト <KeyValuePair\<XmlQualifiedName、オブジェクト >>**です。</span><span class="sxs-lookup"><span data-stu-id="1f025-112">To promote the SOAP header values to the BizTalk message context, WCF adapters are looking for the pair of key **http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties/Promote** and value **List<KeyValuePair\<XmlQualifiedName, object>>**.</span></span>  
  
     <span data-ttu-id="1f025-113">このペアを使用して、WCF アダプタを実行し、名前空間、名前からの値、 **XmlQualifiedName**オブジェクトおよびヘッダーの値を昇格させるために使用します。</span><span class="sxs-lookup"><span data-stu-id="1f025-113">Using this pair, WCF adapters take the namespace, name, and value from the **XmlQualifiedName** object and use them for promoting the header values.</span></span>  
  
-   <span data-ttu-id="1f025-114">書き込むが、BizTalk メッセージ コンテキストに SOAP ヘッダーの値を昇格しません、WCF アダプタを探しているキーのペアは、 **http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties/WriteToContext**および値**リスト < KeyValuePair\<XmlQualifiedName、オブジェクト >>**です。</span><span class="sxs-lookup"><span data-stu-id="1f025-114">To write but not promote the SOAP header values to the BizTalk message context, WCF adapters are looking for the pair of key **http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties/WriteToContext** and value **List<KeyValuePair\<XmlQualifiedName, object>>**.</span></span>  
  
     <span data-ttu-id="1f025-115">WCF アダプターは、このペアを使用して、値をメッセージ コンテキストに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="1f025-115">Using this pair, WCF adapters write the values to the message context.</span></span>  
  
 <span data-ttu-id="1f025-116">次のコードは、SOAP ヘッダーの値を BizTalk メッセージ コンテキストに書き込む、または昇格させる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="1f025-116">The following code shows how to write or promote the SOAP header values to the BizTalk message context:</span></span>  
  
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
  
 <span data-ttu-id="1f025-117">BizTalk WCF サービス公開ウィザードで生成されたメタデータには、カスタム SOAP ヘッダーの定義が含まれません。</span><span class="sxs-lookup"><span data-stu-id="1f025-117">The BizTalk WCF Service Publishing Wizard does not include custom SOAP header definitions in the generated metadata.</span></span> <span data-ttu-id="1f025-118">カスタム SOAP ヘッダーを使用して、WCF サービスにメタデータを公開するには、Web サービス記述言語 (WSDL) ファイルを手動で作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f025-118">To publish metadata for WCF services using custom SOAP headers, you should manually create a Web Services Description Language (WSDL) file.</span></span> <span data-ttu-id="1f025-119">使用することができます、 **externalMetadataLocation**の属性、 [ \<serviceMetadata >](http://go.microsoft.com/fwlink/?LinkId=89121) WSDL ファイルの場所を指定して、ウィザードを生成する Web.config ファイル内の要素。</span><span class="sxs-lookup"><span data-stu-id="1f025-119">You can use the **externalMetadataLocation** attribute of the [\<serviceMetadata>](http://go.microsoft.com/fwlink/?LinkId=89121) element in the Web.config file that the wizard generates to specify the location of the WSDL file.</span></span> <span data-ttu-id="1f025-120">この WSDL ファイルは、WSDL およびメタデータ交換 (MEX) 要求の応答として、自動生成された WSDL の代わりにユーザーに返されます。</span><span class="sxs-lookup"><span data-stu-id="1f025-120">The WSDL file is returned to the user in response to WSDL and metadata exchange (MEX) requests instead of the auto-generated WSDL.</span></span>  
  
 <span data-ttu-id="1f025-121">次の XML データは、カスタム SOAP ヘッダーを定義する WSDL ファイルの一部を示しています。</span><span class="sxs-lookup"><span data-stu-id="1f025-121">The following XML data shows an example of a part of the WSDL file defining custom SOAP headers:</span></span>  
  
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
  
## <a name="in-this-section"></a><span data-ttu-id="1f025-122">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1f025-122">In This Section</span></span>  
  
-   [<span data-ttu-id="1f025-123">オーケストレーションでの WCF メッセージにおける SOAP ヘッダーへのアクセス</span><span class="sxs-lookup"><span data-stu-id="1f025-123">Accessing SOAP Headers in WCF Messages with Orchestrations</span></span>](../core/accessing-soap-headers-in-wcf-messages-with-orchestrations.md)  
  
-   [<span data-ttu-id="1f025-124">パイプライン コンポーネントでの WCF メッセージにおける SOAP ヘッダーへのアクセス</span><span class="sxs-lookup"><span data-stu-id="1f025-124">Accessing SOAP Headers in WCF Messages with Pipeline Components</span></span>](../core/accessing-soap-headers-in-wcf-messages-with-pipeline-components.md)  
  
## <a name="see-also"></a><span data-ttu-id="1f025-125">参照</span><span class="sxs-lookup"><span data-stu-id="1f025-125">See Also</span></span>  
 <span data-ttu-id="1f025-126">[WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md) </span><span class="sxs-lookup"><span data-stu-id="1f025-126">[WCF Adapters Property Schema and Properties](../core/wcf-adapters-property-schema-and-properties.md) </span></span>  
 [<span data-ttu-id="1f025-127">消費済み WCF サービスでの SOAP ヘッダー</span><span class="sxs-lookup"><span data-stu-id="1f025-127">SOAP Headers with Consumed WCF Services</span></span>](../core/soap-headers-with-consumed-wcf-services.md)