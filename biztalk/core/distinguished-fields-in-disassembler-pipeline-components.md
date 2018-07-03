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
ms.openlocfilehash: b08a5c3dd6b88351e67f678524a03052e8435439
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012291"
---
# <a name="distinguished-fields-in-disassembler-pipeline-components"></a>識別フィールドに逆アセンブラー パイプライン コンポーネント
スキーマで定義された識別フィールドは、XML 逆アセンブラー、BizTalk 逆アセンブラー、またはフラット ファイル逆アセンブラー パイプランによって、次の形式でメッセージ コンテキストに書き込まれます。  
  
 *使用される名前*XPath で識別フィールド  
  
 *名前空間 URI*は"<http://schemas.microsoft.com/BizTalk/2003/btsDistinguishedFields>"  
  
 プロパティの値は、 **System.String**使用して XML ドキュメントから抽出された値は、XPath を指定します。  
  
 次の例では、スキーマに識別フィールド Price があります。  
  
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
  
 次のようなドキュメント インスタンスの場合は、  
  
```  
<PO>  
            <Item>Bolt</Item>  
            <Price>10</Price>  
<PO>  
```  
  
 XML 逆アセンブラーがメッセージ コンテキストで次のように識別フィールドを書き込みます。  
  
 コンテキストのプロパティの名前。 `"/*[local-name()='PO' and namespace-uri()='http://SendHtmlMessage.PO']/\*[local-name()='Price' and namespace-uri()='']"`  
  
 プロパティの Namespace: http://schemas.microsoft.com/BizTalk/2003/btsDistinguishedFields  
  
 プロパティの値: 10  
  
> [!NOTE]
>  いずれかの XML ドキュメント要素の値のサイズが 85 KB を超えると、ドキュメントの処理パフォーマンスが低下する場合があります。  
  
## <a name="see-also"></a>参照  
 [フラット ファイル逆アセンブラー パイプライン コンポーネント](../core/flat-file-disassembler-pipeline-component.md)   
 [フラット ファイル逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)
