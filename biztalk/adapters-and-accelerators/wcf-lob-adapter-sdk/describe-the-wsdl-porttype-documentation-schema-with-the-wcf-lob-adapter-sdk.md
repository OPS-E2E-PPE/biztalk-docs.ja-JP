---
title: WCF LOB Adapter SDK と WSDL PortType ドキュメント スキーマについて説明します |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9dd96eaf-b3b3-49b4-aea9-0ae1e8999d62
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f24476e97807900b686dc471276de76f92212a3e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363668"
---
# <a name="describe-the-wsdl-porttype-documentation-schema-with-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="db62d-102">WCF LOB Adapter SDK と WSDL PortType ドキュメント スキーマについて説明します</span><span class="sxs-lookup"><span data-stu-id="db62d-102">Describe the WSDL PortType Documentation Schema with the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="db62d-103">WSDL を[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]生成各 portType の追加のわかりやすい情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="db62d-103">The WSDL that the  [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] generates contains additional descriptive information for each portType.</span></span> <span data-ttu-id="db62d-104">このトピックでは、この追加情報のスキーマを説明します。</span><span class="sxs-lookup"><span data-stu-id="db62d-104">The schema for this additional information is described in this topic.</span></span>  
  
## <a name="documentation-xml-schema"></a><span data-ttu-id="db62d-105">XML スキーマのドキュメント</span><span class="sxs-lookup"><span data-stu-id="db62d-105">Documentation XML Schema</span></span>  
 <span data-ttu-id="db62d-106">操作のドキュメントは、アダプターのドキュメントの操作を表すノードを追加する、portType の注釈を使用して実装されます。</span><span class="sxs-lookup"><span data-stu-id="db62d-106">The operation documentation is implemented using annotation of the portType to add a node that represents the adapter documentation for the operation.</span></span> <span data-ttu-id="db62d-107">このノードには、操作とパラメーターの詳細に説明するサブノードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="db62d-107">This node contains subnodes that further describe the operation and parameters.</span></span> <span data-ttu-id="db62d-108">このスキーマの定義は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="db62d-108">This schema is defined as follows.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:element name="adapterOperationDocumentation">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="summary" type="xs:string" />  
        <xs:element maxOccurs="unbounded" name="param">  
          <xs:complexType>  
            <xs:simpleContent>  
              <xs:extension base="xs:string">  
                <xs:attribute name="name" type="xs:string" use="required" />  
              </xs:extension>  
            </xs:simpleContent>  
          </xs:complexType>  
        </xs:element>  
        <xs:element name="returns" type="xs:string" />  
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="db62d-109">指定した操作で生成される WSDL は、人間が読める形式で追加のわかりやすい情報を提供する、前のスキーマが使用されます。</span><span class="sxs-lookup"><span data-stu-id="db62d-109">When WSDL is generated for a given operation, the preceding schema is used to provide additional descriptive information in human readable format.</span></span> <span data-ttu-id="db62d-110">たとえば、エコー アダプターの EchoString 操作の portType は次の情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="db62d-110">For example, the following portType information is returned for the EchoString operation of the Echo Adapter.</span></span>  
  
```  
<wsdl:portType name="EchoService">  
  <wsdl:operation name="EchoString">  
    <wsdl:documentation>  
      <doc:adapterOperationDocumentation>  
        <doc:summary>String EchoString( string aName)\</doc:summary>  
        <doc:param name="aName">This string will be echoed back to the user.\</doc:param>  
        <doc:returns>String value containing the value of aName \</doc:returns>  
      </doc:adapterOperationDocumentation>  
    </wsdl:documentation>  
    <wsdl:input wsaw:Action="Echo/EchoString" message="ns2:EchoService_EchoString_InputMessage" />  
    <wsdl:output wsaw:Action="Echo/EchoString/response" message="ns2:EchoService_EchoString_OutputMessage" />  
  </wsdl:operation>  
</wsdl:portType>  
```  
  
 <span data-ttu-id="db62d-111">ドキュメント要素の値がから取得した`Microsoft.ServiceModel.Channels.Common.ParameterizedOperationMetadata`操作。</span><span class="sxs-lookup"><span data-stu-id="db62d-111">The values for the documentation elements are obtained from `Microsoft.ServiceModel.Channels.Common.ParameterizedOperationMetadata` for the operation.</span></span> <span data-ttu-id="db62d-112">前の例は、次の例の結果として生成されました。</span><span class="sxs-lookup"><span data-stu-id="db62d-112">The preceding example was generated as a result of the following example.</span></span>  
  
```csharp  
ParameterizedOperationMetadata om = new ParameterizedOperationMetadata(operationId, operationId);  
// set this if you want this operation to belong to this interface name  
// in the generated proxy, the interface name will be EchoService  
// and the client implementation name will be EchoServiceClient.  
om.OperationGroup = "EchoService";  
// set the operation namespace to be same as service namespace  
om.OperationNamespace = EchoAdapter.SERVICENAMESPACE;              
switch (operationId)  
{  
   case "Echo/EchoString":  
       om.DisplayName = "EchoString";  
       om.OriginalName = "targetSystemEchoString";  
       om.Description = "String EchoString( string aName)";  
       OperationParameter parm1 = new OperationParameter("aName", OperationParameterDirection.In, QualifiedType.StringType, false);  
       parm1.Description = "This string will be echoed back to the user.";  
       OperationResult result = new OperationResult(new SimpleQualifiedType(XmlTypeCode.String), false);  
       result.Description = "String value containing the value of aName";  
       om.Parameters.Add(parm1);  
       om.OperationResult = result;  
       return om;   
```  
  
## <a name="see-also"></a><span data-ttu-id="db62d-113">参照</span><span class="sxs-lookup"><span data-stu-id="db62d-113">See Also</span></span>  
 [<span data-ttu-id="db62d-114">WCF LOB Adapter SDK を使用して開発のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="db62d-114">Development best practices using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/development-best-practices-using-the-wcf-lob-adapter-sdk.md)