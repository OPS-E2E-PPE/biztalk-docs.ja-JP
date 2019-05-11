---
title: XML アセンブラーおよび逆アセンブラー パイプライン コンポーネントでのエンベロープの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XMLNorm.EnvelopeSpecNames property
- XML Disassembler [pipeline component], envelopes
- envelopes, nesting
- envelopes, XML Disassembler [pipeline component]
- envelopes, XML Assembler [pipeline component]
- XML Assembler [pipeline component], envelopes
- Envelope Specification Names property
ms.assetid: ccffd2f7-c7b1-4103-a914-ae9b4b19bee3
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9841a9abcf188623afb46c8387d42c94982d0119
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389064"
---
# <a name="envelope-use-in-the-xml-assembler-and-disassembler-pipeline-components"></a><span data-ttu-id="177a2-102">XML アセンブラーおよび逆アセンブラー パイプライン コンポーネントでのエンベロープの使用</span><span class="sxs-lookup"><span data-stu-id="177a2-102">Envelope Use in the XML Assembler and Disassembler Pipeline Components</span></span>
<span data-ttu-id="177a2-103">XML メッセージには、0 個以上のエンベロープを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="177a2-103">An XML message can include zero or more envelopes.</span></span> <span data-ttu-id="177a2-104">XML ドキュメントをラップするエンベロープ (太字) では、次の例です。</span><span class="sxs-lookup"><span data-stu-id="177a2-104">The following example shows an envelope (in bold) wrapping an XML document.</span></span>  
  
```  
<ns1:document xmlns:ns1="http://myDocumentNamespaceURI.org">  
   <message>Hello</message>  
</ns1:document>  
  
```  
  
 <span data-ttu-id="177a2-105">エンベロープには、2 つの目的があります。</span><span class="sxs-lookup"><span data-stu-id="177a2-105">Envelopes serve two purposes:</span></span>  
  
- <span data-ttu-id="177a2-106">プロパティの昇格および降格のために使用するフィールドの値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="177a2-106">They can include field values to use for property promotion and demotion.</span></span>  
  
   <span data-ttu-id="177a2-107">XML 逆アセンブラー コンポーネントはプロパティを昇格して、XML アセンブラー コンポーネントとプロパティは降格されます。</span><span class="sxs-lookup"><span data-stu-id="177a2-107">The XML Disassembler component promotes properties, and the XML Assembler component demotes properties.</span></span> <span data-ttu-id="177a2-108">プロパティの昇格と降格は XML ドキュメントにも発生します。</span><span class="sxs-lookup"><span data-stu-id="177a2-108">Property promotion and demotion can also occur in XML documents.</span></span>  
  
- <span data-ttu-id="177a2-109">複数の XML ドキュメントを 1 つのインターチェンジに結合できます。</span><span class="sxs-lookup"><span data-stu-id="177a2-109">They can combine several XML documents into a single interchange.</span></span>  
  
   <span data-ttu-id="177a2-110">整形式 XML ドキュメントが 1 つだけのルート要素を持てないため、エンベロープでは、1 つのルート要素を共有する複数の XML ドキュメントを結合することができます。</span><span class="sxs-lookup"><span data-stu-id="177a2-110">Because a well-formed XML document can have only one root element, an envelope enables you to combine multiple XML documents to share one root element.</span></span>  
  
  <span data-ttu-id="177a2-111">使用して、エンベロープの順序を指定することによって、正規の形式を適用することができます、**スキーマ コレクション プロパティ エディター**ダイアログの省略記号をクリックしてアクセスされる、**エンベロープ スキーマ**XML アセンブラーのデザイン時プロパティです。</span><span class="sxs-lookup"><span data-stu-id="177a2-111">You can enforce the canonical form by specifying the envelope order by using the **Schema Collection Property Editor** dialog which is accessed by clicking the ellipses for the **Envelope schemas** design-time property in the XML Assembler.</span></span> <span data-ttu-id="177a2-112">使用することも、 **XMLNORM します。EnvelopeSpecNames** XML アセンブラーの実行前に、メッセージ コンテキスト プロパティ。</span><span class="sxs-lookup"><span data-stu-id="177a2-112">You can also use the **XMLNORM.EnvelopeSpecNames** message context property before the XML Assembler is run.</span></span> <span data-ttu-id="177a2-113">XML アセンブラーは、正規の形式で、エンベロープ ドキュメントを生成します。</span><span class="sxs-lookup"><span data-stu-id="177a2-113">The XML Assembler produces an enveloped document in canonical form.</span></span>  
  
## <a name="nesting-envelopes"></a><span data-ttu-id="177a2-114">入れ子の封筒</span><span class="sxs-lookup"><span data-stu-id="177a2-114">Nesting envelopes</span></span>  
 <span data-ttu-id="177a2-115">大きいインターチェンジにいくつかのエンベロープ XML ドキュメントを組み合わせることができます、フォームの複雑なドキュメント構造にエンベロープを入れ子にできます。</span><span class="sxs-lookup"><span data-stu-id="177a2-115">You can nest envelopes to form complex document structures where several enveloped XML documents can be combined into a larger interchange.</span></span> <span data-ttu-id="177a2-116">次の例では、2 つのエンペロープによってラップされたインターチェンジを示します。</span><span class="sxs-lookup"><span data-stu-id="177a2-116">The following example shows an interchange wrapped by two envelopes.</span></span>  
  
```  
<envelope1>  
   <document1/>  
   <envelope2>  
      <document2/>  
      <document3/>  
   </envelope2>  
   <document4/>  
</envelope1>  
```  
  
 <span data-ttu-id="177a2-117">前の例は、ドキュメントをエンベロープと同じ階層レベルでできることを意味する、柔軟な形式を示しています。</span><span class="sxs-lookup"><span data-stu-id="177a2-117">The preceding example illustrates a flexible form, which means that a document can be on the same hierarchy level as an envelope.</span></span> <span data-ttu-id="177a2-118">エンベロープ ドキュメントを逆アセンブルした後は、(document1、document2 など)、4 つの独立したドキュメントが作成されます。</span><span class="sxs-lookup"><span data-stu-id="177a2-118">After disassembling the enveloped document, four separate documents are created (document1, document2, and so on).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="177a2-119">参照</span><span class="sxs-lookup"><span data-stu-id="177a2-119">See Also</span></span>  
 [<span data-ttu-id="177a2-120">パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="177a2-120">Pipeline Components</span></span>](../core/pipeline-components.md)