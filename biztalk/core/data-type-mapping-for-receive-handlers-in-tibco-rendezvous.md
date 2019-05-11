---
title: TIBCO Rendezvous から受信するデータ型マッピング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 36908a94-3c0d-466e-aa49-f674ba4a26af
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37f064021c58e2d870df8e1110a07ce42d0dc9ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389960"
---
# <a name="data-type-mapping-for-receive-handlers-in-tibco-rendezvous"></a>データ型マッピングの TIBCO Rendezvous 受信ハンドラー
Microsoft BizTalk Adapter for TIBCO Rendezvous は、TIBCO RV の型を次の表で指定された XML スキーマ型にマップします。  
  
## <a name="tibco-rv-to-xml-data-type-mapping"></a>TIBCO RV と XML データ型マッピング  
  
|TIBCO RV 型|XML スキーマ型|コメント|  
|-------------------|---------------------|--------------|  
|TIBRVMSG_MSG|tibrv:message|完全な XML ドキュメントがメッセージ全体から構築します。|  
|TIBRVMSG_XML|tibrv:rawxml|(アダプターによって解釈されない) バイトの配列から構築された XML ドキュメントです。|  
|TIBRVMSG_DATETIME|xsd:dateTime|アダプターでは、System.Xml.XmlConvert クラスを使用して、XML スキーマ間で変換`dateTime`と`System.DateTime`インスタンス。|  
|TIBRVMSG_OPAQUE|xsd:base64Binary||  
|TIBRVMSG_STRING|xsd:string||  
|TIBRVMSG_BOOL|xsd:boolean||  
|TIBRVMSG_I8|xsd:byte||  
|TIBRVMSG_I16|xsd:short||  
|TIBRVMSG_I32|xsd:int||  
|TIBRVMSG_I64|xsd:long||  
|TIBRVMSG_U8|xsd:unsignedByte||  
|TIBRVMSG_U16|xsd:unsignedShort||  
|TIBRVMSG_U32|xsd:unsignedInt||  
|TIBRVMSG_U64|xsd:unsignedLong||  
|TIBRVMSG_F32|xsd:float||  
|TIBRVMSG_F64|xsd:double||  
|TIBRVMSG_IPADDR32|tibrv:IPaddress|`System.Net.IPAddress.ToString( )` 出力の生成に使用されます。 コンテンツは、ネットワークのバイト順では。 ToString() によって処理されます。|  
|TIBRVMSG_IPPORT16|tibrv:IPport|コンテンツがネットワークのバイト順で|  
|TIBRVMSG_I8ARRAY|tibrv:arrayOfByte|アダプター 'によって tibrv' スキーマ名前空間が提供されます。|  
|TIBRVMSG_I16ARRAY|tibrv:arrayOfShort||  
|TIBRVMSG_I32ARRAY|tibrv:arrayOfInt||  
|TIBRVMSG_I64ARRAY|tibrv:arrayOfLong||  
|TIBRVMSG_U8ARRAY|tibrv:arrayOfUnsignedByte||  
|TIBRVMSG_U16ARRAY|tibrv:arrayOfUnsignedShort||  
|TIBRVMSG_U32ARRAY|tibrv:arrayOfUnsignedInt||  
|TIBRVMSG_U64ARRAY|tibrv:arrayOfUnsignedLong||  
|TIBRVMSG_F32ARRAY|tibrv:arrayOfFloat||  
|TIBRVMSG_F64ARRAY|tibrv:arrayOfDouble||  
  
 TIBCO Rendezvous の配列は、同じ名前のフィールドのシーケンスとは異なります。 たとえば、TIBCO Rendezvous メッセージでは、70,000 の要素を持つ配列を指定することが、70,000 のフィールドには無効です。  
  
 前の表に、配列型のスキーマのようになります。  
  
```  
…  
<xsd:complexType name='arrayOfShort'>  
<xsd:sequence>  
<xsd:element name="item" type="xsd:short"/>  
</xsd:sequence>  
</xsd:complexType>  
  
```  
  
 メッセージ内の配列要素のようになります。  
  
```  
<someElement xsi:type='tibrv:arrayOfShort'>  
<item>100</item>  
<item>200</item>  
<item>300</item>  
<item>400</item>  
<item>500</item>  
</someElement>  
  
```  
  
 IPaddress のスキーマのようになります。  
  
```  
<xsd:simpleType name='IPaddress'>  
  
 <xsd:restriction base="xs:string">  
   <xsd:minLength value="7" />  
   <xsd:maxLength value="15" />  
  
 </xsd:restriction>  
       </xsd:simpleType>   
</xsd:simpleType>  
  
```  
  
 IPport のスキーマのようになります。  
  
```  
<xsd:simpleType name='IPport'>  
  
<xsd:restriction base='xsd:ushort'>  
</xsd:simpleType>  
```  
  
## <a name="see-also"></a>参照  
 [TIBCO Rendezvous でのメッセージ マッピング](../core/message-mapping-in-tibco-rendezvous.md)   
 [TIBCO Rendezvous 受信ハンドラーの作成](../core/creating-tibco-rendezvous-receive-handlers.md)