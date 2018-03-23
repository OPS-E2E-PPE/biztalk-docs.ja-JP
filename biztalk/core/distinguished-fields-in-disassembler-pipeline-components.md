---
title: 識別フィールドに逆アセンブラー パイプライン コンポーネント |Microsoft ドキュメント
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
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64e4c8f15d167f5343089c11b92b0f373aa45576
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
---
# <a name="distinguished-fields-in-disassembler-pipeline-components"></a><span data-ttu-id="2d2c2-102">識別フィールドに逆アセンブラー パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2d2c2-102">Distinguished Fields in Disassembler Pipeline Components</span></span>
<span data-ttu-id="2d2c2-103">スキーマで定義された識別フィールドは、XML 逆アセンブラー、BizTalk 逆アセンブラー、またはフラット ファイル逆アセンブラー パイプランによって、次の形式でメッセージ コンテキストに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="2d2c2-103">Distinguished fields defined in a schema are written to the message context by the XML Disassembler, BizTalk Framework Disassembler, or Flat File Disassembler pipeline components in the following format:</span></span>  
  
 <span data-ttu-id="2d2c2-104">*使用される名前* XPath で識別フィールドは、</span><span class="sxs-lookup"><span data-stu-id="2d2c2-104">*name used* is the distinguished field in XPath</span></span>  
  
 <span data-ttu-id="2d2c2-105">*namespace URI* is "http://schemas.microsoft.com/BizTalk/2003/btsDistinguishedFields"</span><span class="sxs-lookup"><span data-stu-id="2d2c2-105">*namespace URI* is "http://schemas.microsoft.com/BizTalk/2003/btsDistinguishedFields"</span></span>  
  
 <span data-ttu-id="2d2c2-106">プロパティの値は、 **System.String** による XML ドキュメントから抽出された値は、XPath を指定します。</span><span class="sxs-lookup"><span data-stu-id="2d2c2-106">The value of the property is the **System.String** value extracted from the XML document using specified XPath.</span></span>  
  
 <span data-ttu-id="2d2c2-107">次の例では、スキーマに識別フィールド Price があります。</span><span class="sxs-lookup"><span data-stu-id="2d2c2-107">The following example schema has a distinguished field Price.</span></span>  
  
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
  
 <span data-ttu-id="2d2c2-108">次のようなドキュメント インスタンスの場合は、</span><span class="sxs-lookup"><span data-stu-id="2d2c2-108">For the document instance</span></span>  
  
```  
<PO>  
            <Item>Bolt</Item>  
            <Price>10</Price>  
<PO>  
```  
  
 <span data-ttu-id="2d2c2-109">XML 逆アセンブラーがメッセージ コンテキストで次のように識別フィールドを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="2d2c2-109">the XML Disassembler writes a distinguished field on a message context as follows:</span></span>  
  
 <span data-ttu-id="2d2c2-110">コンテキストのプロパティの名前:"/* [ローカル名 () = 'PO' and namespace-uri() ='http://SendHtmlMessage.PO']/\*[ローカル名 () '価格' and namespace-uri() = = ']"</span><span class="sxs-lookup"><span data-stu-id="2d2c2-110">Name of the property on the context: "/*[local-name()='PO' and namespace-uri()='http://SendHtmlMessage.PO']/\*[local-name()='Price' and namespace-uri()='']"</span></span>  
  
 <span data-ttu-id="2d2c2-111">プロパティの Namespace: http://schemas.microsoft.com/BizTalk/2003/btsDistinguishedFields</span><span class="sxs-lookup"><span data-stu-id="2d2c2-111">Namespace of the property: http://schemas.microsoft.com/BizTalk/2003/btsDistinguishedFields</span></span>  
  
 <span data-ttu-id="2d2c2-112">プロパティの値: 10</span><span class="sxs-lookup"><span data-stu-id="2d2c2-112">Value of the property: 10</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2d2c2-113">いずれかの XML ドキュメント要素の値のサイズが 85 KB を超えると、ドキュメントの処理パフォーマンスが低下する場合があります。</span><span class="sxs-lookup"><span data-stu-id="2d2c2-113">If the size of any XML document element values exceeds 85KB, a degradation in the performance of processing those documents may occur.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d2c2-114">参照</span><span class="sxs-lookup"><span data-stu-id="2d2c2-114">See Also</span></span>  
 <span data-ttu-id="2d2c2-115">[フラット ファイル逆アセンブラー パイプライン コンポーネント](../core/flat-file-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="2d2c2-115">[Flat File Disassembler Pipeline Component](../core/flat-file-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="2d2c2-116">フラット ファイル逆アセンブラー パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="2d2c2-116">How to Configure the Flat File Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)