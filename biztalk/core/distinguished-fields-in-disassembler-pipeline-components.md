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
# <a name="distinguished-fields-in-disassembler-pipeline-components"></a><span data-ttu-id="9775e-102">識別フィールドに逆アセンブラー パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9775e-102">Distinguished Fields in Disassembler Pipeline Components</span></span>
<span data-ttu-id="9775e-103">スキーマで定義されている識別フィールドは XML 逆アセンブラー、BizTalk Framework 逆アセンブラーまたは次の形式のフラット ファイル逆アセンブラー パイプライン コンポーネントによってメッセージ コンテキストに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="9775e-103">Distinguished fields defined in a schema are written to the message context by the XML Disassembler, BizTalk Framework Disassembler, or Flat File Disassembler pipeline components in the following format:</span></span>  
  
 <span data-ttu-id="9775e-104">*使用される名前*XPath で識別フィールド</span><span class="sxs-lookup"><span data-stu-id="9775e-104">*name used* is the distinguished field in XPath</span></span>  
  
 <span data-ttu-id="9775e-105">*名前空間 URI*は"<http://schemas.microsoft.com/BizTalk/2003/btsDistinguishedFields>"</span><span class="sxs-lookup"><span data-stu-id="9775e-105">*namespace URI* is "<http://schemas.microsoft.com/BizTalk/2003/btsDistinguishedFields>"</span></span>  
  
 <span data-ttu-id="9775e-106">プロパティの値は、 **System.String**使用して XML ドキュメントから抽出された値は、XPath を指定します。</span><span class="sxs-lookup"><span data-stu-id="9775e-106">The value of the property is the **System.String** value extracted from the XML document using specified XPath.</span></span>  
  
 <span data-ttu-id="9775e-107">次の例のスキーマには、識別フィールド Price があります。</span><span class="sxs-lookup"><span data-stu-id="9775e-107">The following example schema has a distinguished field Price.</span></span>  
  
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
  
 <span data-ttu-id="9775e-108">ドキュメント インスタンスの</span><span class="sxs-lookup"><span data-stu-id="9775e-108">For the document instance</span></span>  
  
```  
<PO>  
            <Item>Bolt</Item>  
            <Price>10</Price>  
<PO>  
```  
  
 <span data-ttu-id="9775e-109">XML 逆アセンブラーは、次のようにメッセージ コンテキストで識別フィールドを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="9775e-109">the XML Disassembler writes a distinguished field on a message context as follows:</span></span>  
  
 <span data-ttu-id="9775e-110">コンテキストのプロパティの名前。 `"/*[local-name()='PO' and namespace-uri()='http://SendHtmlMessage.PO']/\*[local-name()='Price' and namespace-uri()='']"`</span><span class="sxs-lookup"><span data-stu-id="9775e-110">Name of the property on the context: `"/*[local-name()='PO' and namespace-uri()='http://SendHtmlMessage.PO']/\*[local-name()='Price' and namespace-uri()='']"`</span></span>  
  
 <span data-ttu-id="9775e-111">プロパティの Namespace: http://schemas.microsoft.com/BizTalk/2003/btsDistinguishedFields</span><span class="sxs-lookup"><span data-stu-id="9775e-111">Namespace of the property: http://schemas.microsoft.com/BizTalk/2003/btsDistinguishedFields</span></span>  
  
 <span data-ttu-id="9775e-112">プロパティの値。10</span><span class="sxs-lookup"><span data-stu-id="9775e-112">Value of the property: 10</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9775e-113">任意の XML ドキュメント要素の値のサイズが 85 KB を超える場合、ドキュメントの処理パフォーマンスの低下が発生します。</span><span class="sxs-lookup"><span data-stu-id="9775e-113">If the size of any XML document element values exceeds 85KB, a degradation in the performance of processing those documents may occur.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9775e-114">参照</span><span class="sxs-lookup"><span data-stu-id="9775e-114">See Also</span></span>  
 <span data-ttu-id="9775e-115">[フラット ファイル逆アセンブラー パイプライン コンポーネント](../core/flat-file-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="9775e-115">[Flat File Disassembler Pipeline Component](../core/flat-file-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="9775e-116">フラット ファイル逆アセンブラー パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="9775e-116">How to Configure the Flat File Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)
