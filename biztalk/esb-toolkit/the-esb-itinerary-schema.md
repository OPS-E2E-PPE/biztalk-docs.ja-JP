---
title: ESB スケジュール スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 168e7b98-6282-494e-bde8-3171e0be7d59
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d205d4722270dd36f7d3611845b0d5bc4c7953f7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399781"
---
# <a name="the-esb-itinerary-schema"></a><span data-ttu-id="55eea-102">ESB スケジュール スキーマ</span><span class="sxs-lookup"><span data-stu-id="55eea-102">The ESB Itinerary Schema</span></span>
<span data-ttu-id="55eea-103">Itinerary.xsd をという名前の ESB 行程スキーマでは、一連の手順については、スケジュール サービスと呼ばれる通常の処理として、旅行プランを定義します。</span><span class="sxs-lookup"><span data-stu-id="55eea-103">The ESB Itinerary schema named Itinerary.xsd defines an itinerary as a set of processing instructions, generally referred to as itinerary services.</span></span> <span data-ttu-id="55eea-104">スケジュールのサービスには、次のスキーマ定義に示すように 1 つまたは複数のスケジュール サービスと、対応する競合回避モジュールの接続文字列を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="55eea-104">An itinerary service may contain one or more itinerary services and the corresponding resolver connection strings, as shown in the following schema definition.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-16"?>  
  
<xs:schema xmlns:b="http://schemas.microsoft.com/BizTalk/2003" xmlns="http://schemas.microsoft.biztalk.practices.esb.com/itinerary" targetNamespace="http://schemas.microsoft.biztalk.practices.esb.com/itinerary" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  
  <xs:annotation>  
    <xs:appinfo>  
      <b:schemaInfo root_reference="Itinerary" xmlns:b="http://schemas.microsoft.con/BizTalk/2003" />  
    </xs:appinfo>  
  </xs:annotation>  
  <xs:element name="Itinerary">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="BizTalkSegment">  
          <xs:complexType>  
            <xs:attribute name="interchangeId" type="xs:string" />  
            <xs:attribute name="epmRRCorrelationToken" type="xs:string" />  
            <xs:attribute name="receiveInstanceId" type="xs:string" />  
            <xs:attribute name="messageId" type="xs:string" />  
          </xs:complexType>  
        </xs:element>  
        <xs:element name="ServiceInstance">  
          <xs:complexType>  
            <xs:attribute name="uuid" type="xs:string" />  
            <xs:attribute name="name" type="xs:string" />  
            <xs:attribute name="type" type="xs:string" />  
            <xs:attribute name="state" type="xs:string" />  
            <xs:attribute name="position" type="xs:int" />  
            <xs:attribute name="isRequestResponse" type="xs:boolean" />  
            <xs:attribute name="stage" type="Stages" />  
          </xs:complexType>  
        </xs:element>  
        <xs:element minOccurs="1" maxOccurs="unbounded" name="Services">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="Services">  
                <xs:complexType>  
                  <xs:sequence>  
                    <xs:element minOccurs="0" maxOccurs="1" name="PropertyBag" nillable="true">  
                      <xs:complexType>  
                        <xs:sequence minOccurs="0" maxOccurs="1">  
                          <xs:element minOccurs="0" maxOccurs="unbounded" name="Property">  
                            <xs:complexType>  
                              <xs:attribute name="name" type="xs:string" use="required" />  
                              <xs:attribute name="value" type="xs:string" use="required" />  
                            </xs:complexType>  
                          </xs:element>  
                        </xs:sequence>  
                      </xs:complexType>  
                    </xs:element>  
                  </xs:sequence>  
                  <xs:attribute name="uuid" type="xs:string" />  
                  <xs:attribute name="beginTime" type="xs:string" />  
                  <xs:attribute name="completeTime" type="xs:string" />  
                  <xs:attribute name="name" type="xs:string" />  
                  <xs:attribute name="type" type="xs:string" />  
                  <xs:attribute name="state" type="xs:string" />  
                  <xs:attribute name="resolve" type="xs:boolean" />  
                  <xs:attribute name="isRequestResponse" type="xs:boolean" />  
                  <xs:attribute name="position" type="xs:int" />  
                  <xs:attribute name="serviceInstanceId" type="xs:string" />  
                  <xs:attribute name="isTrackingEnabled">  
                    <xs:simpleType>  
                      <xs:restriction base="xs:boolean" />  
                    </xs:simpleType>  
                  </xs:attribute>  
                  <xs:attribute name="stage" type="Stages" />  
                </xs:complexType>  
              </xs:element>  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
        <xs:element name="ResolverGroups">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element maxOccurs="unbounded" name="Resolvers">  
                <xs:complexType>  
                  <xs:simpleContent>  
                    <xs:extension base="xs:string">  
                      <xs:attribute name="serviceId" type="xs:string" />  
                    </xs:extension>  
                  </xs:simpleContent>  
                </xs:complexType>  
              </xs:element>  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
      </xs:sequence>  
      <xs:attribute name="uuid" type="xs:string" />  
      <xs:attribute name="beginTime" type="xs:string" />  
      <xs:attribute name="completeTime" type="xs:string" />  
      <xs:attribute name="state" type="xs:string" />  
      <xs:attribute name="isRequestResponse" type="xs:boolean" />  
      <xs:attribute name="servicecount" type="xs:int" use="required" />  
    </xs:complexType>  
  </xs:element>  
  <xs:simpleType name="Stages">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="notSpecified" />  
      <xs:enumeration value="receiveInbound" />  
      <xs:enumeration value="receiveTransmit" />  
      <xs:enumeration value="sendTransmit" />  
      <xs:enumeration value="sendInbound" />  
    </xs:restriction>  
  </xs:simpleType>  
</xs:schema>  
```  
  
 <span data-ttu-id="55eea-105">**ServiceInstance**要素が現在スケジュール サービスに対応し、プロパティを含む**名前**、**型**、**状態**、および**位置**サービスがメッセージ コンテキストに昇格します。</span><span class="sxs-lookup"><span data-stu-id="55eea-105">The **ServiceInstance** element corresponds to the current itinerary service and contains properties such as **name**, **type**, **state**, and **position** that the service promotes into the message context.</span></span> <span data-ttu-id="55eea-106">システム-Properties.xsd でという名前のスキーマ、 **Microsoft.Practices.ESB.ItinerarySchemas**アセンブリは、これらのプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="55eea-106">The schema named System-Properties.xsd in the **Microsoft.Practices.ESB.ItinerarySchemas** assembly defines these properties.</span></span>  
  
 <span data-ttu-id="55eea-107">**サービス**要素は、その状態で定義された各サービスでのスケジュール サービスのセットを表します、開始時間、完了時刻、種類 (**オーケストレーション**または**メッセージング**)、および、必要に応じて、ステージ (**receiveInbound**、 **receiveTransmit**、 **sendTransmit**、 **sendInbound**)。</span><span class="sxs-lookup"><span data-stu-id="55eea-107">The **Services** element represents a set of itinerary services, with each service defined by its state, begin time, completion time, type (**Orchestration** or **Messaging**), and, optionally, stage (**receiveInbound**, **receiveTransmit**, **sendTransmit**, **sendInbound**).</span></span>  
  
 <span data-ttu-id="55eea-108">**ResolverGroups**要素が複数含まれている**リゾルバー**を通じて、旅行プランを参照する 1 つまたは複数の競合回避モジュールの接続文字列を定義の要素、 **serviceid**属性。</span><span class="sxs-lookup"><span data-stu-id="55eea-108">The **ResolverGroups** element contains multiple **Resolvers** elements, each of which defines one or more resolver connection strings that an itinerary references through the **serviceid** attribute.</span></span>  
  
 <span data-ttu-id="55eea-109">次に示します ESB 行程パイプライン コンポーネントによって処理される前に、の送信スケジュール オンランプ SOAP ヘッダーのサンプルを。</span><span class="sxs-lookup"><span data-stu-id="55eea-109">The following shows a sample of a submitted itinerary SOAP header before it is processed by the ESB Itinerary Pipeline component.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Itinerary xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" uuid="" beginTime="" completeTime="" state="Pending" isRequestResponse="false" xmlns="http://schemas.microsoft.biztalk.practices.esb.com/itinerary">  
  
  <ServiceInstance uuid="" name="Microsoft.Practices.ESB.Services.Transform" type="Messaging" state="Pending" position="0" isRequestResponse="false" xmlns="" />  
  
  <Services xmlns="">  
    <Service uuid="" beginTime="" completeTime="" name="Microsoft.Practices.ESB.Services.Transform" type="Messaging" state="Pending" isRequestResponse="false" position="0" serviceInstanceId="" />  
  </Services>  
  
  <Services xmlns="">  
    <Service uuid="" beginTime="" completeTime="" name="DynamicResolutionSolicitResp" type="Messaging" state="Pending" isRequestResponse="true" position="1" serviceInstanceId="" />  
  </Services>  
  
  <ResolverGroups xmlns="">  
    <Resolvers serviceId="DynamicResolutionSolicitResp1"><![CDATA[BRE:\\policy=GetCanadaEndPoint;version=;useMsg=;]]></Resolvers>  
  
    <Resolvers serviceId="Microsoft.Practices.ESB.Services.Transform0"><![CDATA[BRE:\\policy=CanadaSubmitOrderMaps;version=;useMsg=;]]></Resolvers>  
  </ResolverGroups>  
  
</Itinerary>  
```