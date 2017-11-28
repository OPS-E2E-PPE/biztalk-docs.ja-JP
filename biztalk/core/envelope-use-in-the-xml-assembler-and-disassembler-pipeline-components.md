---
title: "XML アセンブラーおよび逆アセンブラー パイプライン コンポーネントでのエンベロープの使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0ae57a65bad84f3d46ceb27e9b5415dc3d1bc31
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="envelope-use-in-the-xml-assembler-and-disassembler-pipeline-components"></a><span data-ttu-id="190be-102">XML アセンブラーおよび逆アセンブラー パイプライン コンポーネントでのエンベロープの使用</span><span class="sxs-lookup"><span data-stu-id="190be-102">Envelope Use in the XML Assembler and Disassembler Pipeline Components</span></span>
<span data-ttu-id="190be-103">XML メッセージには 0 個以上のエンベロープを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="190be-103">An XML message can include zero or more envelopes.</span></span> <span data-ttu-id="190be-104">次の例では、XML ドキュメントをラップするエンベロープを太字で示します。</span><span class="sxs-lookup"><span data-stu-id="190be-104">The following example shows an envelope (in bold) wrapping an XML document.</span></span>  
  
```  
<ns1:document xmlns:ns1="http://myDocumentNamespaceURI.org">  
   <message>Hello</message>  
</ns1:document>  
  
```  
  
 <span data-ttu-id="190be-105">エンベロープの用途は次の 2 つです。</span><span class="sxs-lookup"><span data-stu-id="190be-105">Envelopes serve two purposes:</span></span>  
  
-   <span data-ttu-id="190be-106">プロパティの昇格と降格のために使用するフィールド値を含めることができる。</span><span class="sxs-lookup"><span data-stu-id="190be-106">They can include field values to use for property promotion and demotion.</span></span>  
  
     <span data-ttu-id="190be-107">XML 逆アセンブラー コンポーネントはプロパティを昇格させ、XML アセンブラー コンポーネントはプロパティを降格させます。</span><span class="sxs-lookup"><span data-stu-id="190be-107">The XML Disassembler component promotes properties, and the XML Assembler component demotes properties.</span></span> <span data-ttu-id="190be-108">プロパティの昇格と降格は、XML ドキュメントでも行うことができます。</span><span class="sxs-lookup"><span data-stu-id="190be-108">Property promotion and demotion can also occur in XML documents.</span></span>  
  
-   <span data-ttu-id="190be-109">複数の XML ドキュメントを 1 つのインターチェンジに結合できる。</span><span class="sxs-lookup"><span data-stu-id="190be-109">They can combine several XML documents into a single interchange.</span></span>  
  
     <span data-ttu-id="190be-110">整形式 XML ドキュメントに含めることができるルート要素は 1 つだけです。エンベロープを使用することにより、複数の XML ドキュメントで 1 つのルート要素を共有できます。</span><span class="sxs-lookup"><span data-stu-id="190be-110">Because a well-formed XML document can have only one root element, an envelope enables you to combine multiple XML documents to share one root element.</span></span>  
  
 <span data-ttu-id="190be-111">使用して、エンベロープの順序を指定することによって、正規の形式を適用することができます、**スキーマ コレクション プロパティ エディター**  ダイアログ ボックスの省略記号ボタンをクリックしてアクセスが、**エンベロープ スキーマ**XML アセンブラーでデザイン時プロパティです。</span><span class="sxs-lookup"><span data-stu-id="190be-111">You can enforce the canonical form by specifying the envelope order by using the **Schema Collection Property Editor** dialog which is accessed by clicking the ellipses for the **Envelope schemas** design-time property in the XML Assembler.</span></span> <span data-ttu-id="190be-112">使用することも、 **XMLNORM です。EnvelopeSpecNames**メッセージ コンテキスト プロパティを XML アセンブラーの実行前にします。</span><span class="sxs-lookup"><span data-stu-id="190be-112">You can also use the **XMLNORM.EnvelopeSpecNames** message context property before the XML Assembler is run.</span></span> <span data-ttu-id="190be-113">XML アセンブラーは、エンベロープ ドキュメントを正規の形式で生成します。</span><span class="sxs-lookup"><span data-stu-id="190be-113">The XML Assembler produces an enveloped document in canonical form.</span></span>  
  
## <a name="nesting-envelopes"></a><span data-ttu-id="190be-114">エンベロープを入れ子にする</span><span class="sxs-lookup"><span data-stu-id="190be-114">Nesting envelopes</span></span>  
 <span data-ttu-id="190be-115">エンベロープを入れ子にすることにより、複数のエンベロープ XML ドキュメントが大きいインターチェンジに結合された、複雑なドキュメント構造を形成できます。</span><span class="sxs-lookup"><span data-stu-id="190be-115">You can nest envelopes to form complex document structures where several enveloped XML documents can be combined into a larger interchange.</span></span> <span data-ttu-id="190be-116">次の例では、2 つのエンペロープによってラップされたインターチェンジを示します。</span><span class="sxs-lookup"><span data-stu-id="190be-116">The following example shows an interchange wrapped by two envelopes.</span></span>  
  
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
  
 <span data-ttu-id="190be-117">前の例では、柔軟な形式を示しました。ドキュメントをエンベロープと同じ階層レベルにすることができます。</span><span class="sxs-lookup"><span data-stu-id="190be-117">The preceding example illustrates a flexible form, which means that a document can be on the same hierarchy level as an envelope.</span></span> <span data-ttu-id="190be-118">エンベロープ ドキュメントを逆アセンブルした後で、4 つの別個のドキュメントが作成されます (document1、document2 など)。</span><span class="sxs-lookup"><span data-stu-id="190be-118">After disassembling the enveloped document, four separate documents are created (document1, document2, and so on).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="190be-119">参照</span><span class="sxs-lookup"><span data-stu-id="190be-119">See Also</span></span>  
 [<span data-ttu-id="190be-120">パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="190be-120">Pipeline Components</span></span>](../core/pipeline-components.md)