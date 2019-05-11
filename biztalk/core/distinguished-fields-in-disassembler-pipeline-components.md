---
title: 識別フィールドに逆アセンブラー パイプライン コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, distinquished fields
- Flat File Disassembler [pipeline component], distinquished fields
- BizTalk Framework Disassembler [pipeline component], distinquished fields
- XML Disassembler [pipeline component], distinquished fields
ms.assetid: 7e51d2fe-0004-4a7b-9055-bd41e8a4b7ab
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63f3fd2dd8948e880af7b2135e8b4fef64f1b39d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389353"
---
# <a name="distinguished-fields-in-disassembler-pipeline-components"></a>識別フィールドに逆アセンブラー パイプライン コンポーネント
スキーマで定義されている識別フィールドは XML 逆アセンブラー、BizTalk Framework 逆アセンブラーまたは次の形式のフラット ファイル逆アセンブラー パイプライン コンポーネントによってメッセージ コンテキストに書き込まれます。  
  
 *使用される名前*XPath で識別フィールド  
  
 *名前空間 URI*は"<http://schemas.microsoft.com/BizTalk/2003/btsDistinguishedFields>"  
  
 プロパティの値は、 **System.String**使用して XML ドキュメントから抽出された値は、XPath を指定します。  
  
 次の例のスキーマには、識別フィールド Price があります。  
  
```  
<?xml version="1.0" encoding="utf-16" ?>   
<xs:schema xmlns="http://SendHtmlMessage.PO" xmlns:b="http://schemas.microsoft.com/BizTalk/2003" targetNamespace="http://SendHtmlMessage.PO xmlns:xs="http://www.w3.org/2001/XMLSchema">  
   <xs:element name="PO">  
      <xs:annotation>  
         <xs:appinfo>  
            <b:properties>  
               <b:property distinguished="true" xpath="/*[local-name()='PO' and namespace-uri()='http://SendHtmlMessage.PO']/*[local-  
               name()='Price' and namespace-uri()='']" />   
            </b:properties>  
         </xs:appinfo>  
      </xs:annotation>  
      <xs:complexType>  
         <xs:sequence>  
            <xs:element name="Item" type="xs:string" />   
            <xs:element name="Price" type="xs:string" />   
         </xs:sequence>  
      </xs:complexType>  
   </xs:element>  
</xs:schema>  
```  
  
 ドキュメント インスタンスの  
  
```  
<PO>  
            <Item>Bolt</Item>  
            <Price>10</Price>  
<PO>  
```  
  
 XML 逆アセンブラーは、次のようにメッセージ コンテキストで識別フィールドを書き込みます。  
  
 コンテキストのプロパティの名前。 `"/*[local-name()='PO' and namespace-uri()='http://SendHtmlMessage.PO']/\*[local-name()='Price' and namespace-uri()='']"`  
  
 プロパティの Namespace: http://schemas.microsoft.com/BizTalk/2003/btsDistinguishedFields  
  
 プロパティの値。10  
  
> [!NOTE]
>  任意の XML ドキュメント要素の値のサイズが 85 KB を超える場合、ドキュメントの処理パフォーマンスの低下が発生します。  
  
## <a name="see-also"></a>参照  
 [フラット ファイル逆アセンブラー パイプライン コンポーネント](../core/flat-file-disassembler-pipeline-component.md)   
 [フラット ファイル逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)
