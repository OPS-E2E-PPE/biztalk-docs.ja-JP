---
title: 消費済み Web サービスでの SOAP ヘッダー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP headers, code samples
- Web services, consuming
- Web services, SOAP headers
- SOAP headers, Web services
- Web services, code samples
ms.assetid: 7be2eee1-ce1c-4611-985c-91dbc8492d6e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9cd18a60feae0d3726b56892d1bcea2864a25d97
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244343"
---
# <a name="soap-headers-with-consumed-web-services"></a><span data-ttu-id="688fa-102">消費済み Web サービスでの SOAP ヘッダー</span><span class="sxs-lookup"><span data-stu-id="688fa-102">SOAP Headers with Consumed Web Services</span></span>
<span data-ttu-id="688fa-103">使用してオーケストレーションを Web サービスを追加した後、 **Web 参照の追加**ダイアログ ボックスで、Web サービスの Web サービス記述言語 (WSDL) を定義する SOAP ヘッダーを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="688fa-103">After you add Web services to your orchestration using the **Add Web Reference** dialog box, you can use the SOAP headers that the Web Services Description Language (WSDL) defines in the Web service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="688fa-104">使用される Web サービスは、不明な SOAP ヘッダーをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="688fa-104">Consumed Web services do not support unknown SOAP headers.</span></span>  
  
 <span data-ttu-id="688fa-105">使用する Web サービスの WSDL には、バインド要素で定義されている SOAP ヘッダーが一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="688fa-105">The WSDL for the consumed Web service lists the defined SOAP headers in the binding element.</span></span> <span data-ttu-id="688fa-106">消費済み Web サービスの WSDL ファイル内のバインド要素を次に示します。</span><span class="sxs-lookup"><span data-stu-id="688fa-106">The following example shows a binding element in the WSDL file for the consumed Web service:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<definitions xmlns:http="http://schemas.xmlsoap.org/wsdl/http/" xmlns:soap="http://schemas.xmlsoap.org/wsdl/soap/" xmlns:s="http://www.w3.org/2001/XMLSchema" xmlns:s0="http://SOAPHeaderWS.ItemAvailability" xmlns:soapenc="http://schemas.xmlsoap.org/soap/encoding/" xmlns:tm="http://microsoft.com/wsdl/mime/textMatching/" xmlns:mime="http://schemas.xmlsoap.org/wsdl/mime/" targetNamespace="http://SOAPHeaderWS.ItemAvailability" xmlns="http://schemas.xmlsoap.org/wsdl/">  
       <types>  
             <s:schema elementFormDefault="qualified" targetNamespace="http://SOAPHeaderWS.ItemAvailability">  
  
                    <s:element name="OrigDest" type="s0:OrigDest"/>  
                    <s:complexType name="OrigDest">  
                           <s:sequence>  
                                 <s:element minOccurs="0" maxOccurs="1" name="Origination" type="s:string"/>  
                                 <s:element minOccurs="0" maxOccurs="1" name="Destination" type="s:string"/>  
                           </s:sequence>  
                    </s:complexType>  
             </s:schema>  
       </types>  
  
       <binding name="ItemAvailabilityServiceSoap" type="s0:ItemAvailabilityServiceSoap">  
             <soap:binding transport="http://schemas.xmlsoap.org/soap/http" style="document"/>  
             <operation name="ItemAvailability">  
                    <soap:operation soapAction="http://SOAPHeaderWS.ItemAvailability/ItemAvailability" style="document"/>  
                    <input>  
                           <soap:body use="literal"/>  
                           <soap:header message="s0:ItemAvailabilityOrigDest" part="OrigDest" use="literal"/>  
                    </input>  
                    <output>  
                           <soap:body use="literal"/>  
                           <soap:header message="s0:ItemAvailabilityOrigDest" part="OrigDest" use="literal"/>  
                    </output>  
             </operation>  
       </binding>  
       <service name="ItemAvailabilityService">  
             <port name="ItemAvailabilityServiceSoap" binding="s0:ItemAvailabilityServiceSoap">  
                    <soap:address location="http://localhost/SOAPHeaderWS/ItemAvailability.asmx"/>  
             </port>  
       </service>  
</definitions>  
```  
  
 <span data-ttu-id="688fa-107">SOAP ヘッダーの使用に関する詳細については、.NET Framework ドキュメントの SOAP ヘッダーの使用「」を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=62266](http://go.microsoft.com/fwlink/?LinkId=62266)します。</span><span class="sxs-lookup"><span data-stu-id="688fa-107">For more information about using SOAP headers, see "Using SOAP Headers" in .NET Framework documentation at [http://go.microsoft.com/fwlink/?LinkId=62266](http://go.microsoft.com/fwlink/?LinkId=62266).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="688fa-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="688fa-108">In This Section</span></span>  
  
-   [<span data-ttu-id="688fa-109">SOAP ヘッダーによる Web サービスの使用</span><span class="sxs-lookup"><span data-stu-id="688fa-109">Consuming Web Services with SOAP Headers</span></span>](../core/consuming-web-services-with-soap-headers.md)  
  
-   [<span data-ttu-id="688fa-110">オーケストレーションでの SOAP ヘッダーの使用</span><span class="sxs-lookup"><span data-stu-id="688fa-110">Using SOAP Headers in Orchestrations</span></span>](../core/using-soap-headers-in-orchestrations.md)  
  
-   [<span data-ttu-id="688fa-111">パイプライン コンポーネントにおける SOAP ヘッダーの使用</span><span class="sxs-lookup"><span data-stu-id="688fa-111">Using SOAP Headers in Pipeline Components</span></span>](../core/using-soap-headers-in-pipeline-components.md)