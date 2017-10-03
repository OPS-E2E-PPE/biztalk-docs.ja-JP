---
title: "TIBCO Rendezvous でのデータ型マッピングの受信ハンドラー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data type mapping
- array types
- receive handlers, data type mapping
ms.assetid: 36908a94-3c0d-466e-aa49-f674ba4a26af
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8729a94fdcfc43ca17e498b10784cc163307badc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="data-type-mapping-for-receive-handlers-in-tibco-rendezvous"></a>TIBCO Rendezvous の受信ハンドラーのデータ型マッピング
Microsoft BizTalk Adapter for TIBCO Rendezvous は、次の表に示されているように、TIBCO RV の型を XML スキーマの型にマップします。  
  
## <a name="tibco-rv-to-xml-data-type-mapping"></a>TIBCO RV と XML データ型のマッピング  
  
|TIBCO RV 型|XML スキーマの型|コメント|  
|-------------------|---------------------|--------------|  
|TIBRVMSG_MSG|tibrv:message|メッセージ全体から構築される完全な XML ドキュメントです。|  
|TIBRVMSG_XML|tibrv:rawxml|バイトの配列 (アダプターによって解釈されていない) から構築された XML ドキュメントです。|  
|TIBRVMSG_DATETIME|xsd:dateTime|このアダプターは、System.Xml.XmlConvert クラスを使用して、XML スキーマの `dateTime` インスタンスと `System.DateTime` インスタンスとの変換を行います。|  
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
|TIBRVMSG_IPADDR32|tibrv:IPaddress|`System.Net.IPAddress.ToString( )` が出力を生成するために使用されます。 内容はネットワークのバイト順になります。 ToString() によって処理されます。|  
|TIBRVMSG_IPPORT16|tibrv:IPport|コンテンツがネットワークのバイト順で|  
|TIBRVMSG_I8ARRAY|tibrv:arrayOfByte|アダプターによって 'tibrv' スキーマ名前空間が提供されます。|  
|TIBRVMSG_I16ARRAY|tibrv:arrayOfShort||  
|TIBRVMSG_I32ARRAY|tibrv:arrayOfInt||  
|TIBRVMSG_I64ARRAY|tibrv:arrayOfLong||  
|TIBRVMSG_U8ARRAY|tibrv:arrayOfUnsignedByte||  
|TIBRVMSG_U16ARRAY|tibrv:arrayOfUnsignedShort||  
|TIBRVMSG_U32ARRAY|tibrv:arrayOfUnsignedInt||  
|TIBRVMSG_U64ARRAY|tibrv:arrayOfUnsignedLong||  
|TIBRVMSG_F32ARRAY|tibrv:arrayOfFloat||  
|TIBRVMSG_F64ARRAY|tibrv:arrayOfDouble||  
  
 TIBCO Rendezvous の配列は、同じ名前のフィールドのシーケンスとは異なります。 たとえば、TIBCO Rendezvous メッセージでは、70,000 の要素を含む配列を持つことは有効ですが、70,000 のフィールドを持つことは有効ではありません。  
  
 前の表の配列型のスキーマは次のようになります。  
  
```  
…  
<xsd:complexType name='arrayOfShort'>  
<xsd:sequence>  
<xsd:element name="item" type="xsd:short"/>  
</xsd:sequence>  
</xsd:complexType>  
  
```  
  
 メッセージ内の配列要素は次のようになります。  
  
```  
<someElement xsi:type='tibrv:arrayOfShort'>  
<item>100</item>  
<item>200</item>  
<item>300</item>  
<item>400</item>  
<item>500</item>  
</someElement>  
  
```  
  
 IPaddress のスキーマは次のようになります。  
  
```  
<xsd:simpleType name='IPaddress'>  
  
 <xsd:restriction base="xs:string">  
   <xsd:minLength value="7" />  
   <xsd:maxLength value="15" />  
  
 </xsd:restriction>  
       </xsd:simpleType>   
</xsd:simpleType>  
  
```  
  
 IPport のスキーマは次のようになります。  
  
```  
<xsd:simpleType name='IPport'>  
  
<xsd:restriction base='xsd:ushort'>  
</xsd:simpleType>  
```  
  
## <a name="see-also"></a>参照  
 [TIBCO Rendezvous のメッセージ マッピング](../core/message-mapping-in-tibco-rendezvous.md)   
 [作成元の TIBCO Rendezvous 受信ハンドラー](../core/creating-tibco-rendezvous-receive-handlers.md)