---
title: データ変換の構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XSLT
- maps, compiling
- Source Links property
- BizTalk Mapper, compiler directives
- code samples, XSLT
- compiler directives, copy text and subcontentent value
- compiler directives, copy text value
- maps, XSLT
- compiler directives, copy name
- compiler directives
- maps, code sample [XSLT]
- XSLT, code samples
ms.assetid: 05abe091-5202-4590-99ec-e60ca53a4324
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8304d43f59f63e474a3257915521d5dc36c38d30
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238962"
---
# <a name="data-transformation-configuration"></a><span data-ttu-id="26f6e-102">データ変換の構成</span><span class="sxs-lookup"><span data-stu-id="26f6e-102">Data Transformation Configuration</span></span>
<span data-ttu-id="26f6e-103">要素からマップされた XSLT (Extensible Stylesheet Language Transformations) の一般的な例は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="26f6e-103">When mapping from an element, a typical Extensible Stylesheet Language Transformations (XSLT) looks as follows.</span></span>  
  
```  
<xsl:attribute name='CatalogPurposeCode'>  
     <xsl:value-of select='BCT/BCT01/text()'/>  
</xsl:attribute>  
```  
  
 <span data-ttu-id="26f6e-104">場合、要素**BCT01**を含む混合コンテンツ、text() を使用できるようになります、までのテキストのみ、最初のサブ要素のポイントにアクセスする場合。</span><span class="sxs-lookup"><span data-stu-id="26f6e-104">If the element **BCT01** contains mixed content, the use of text() makes it possible to access the first text only up to the point of the first subelement, if any.</span></span> <span data-ttu-id="26f6e-105">この XSLT ステートメントで text() を使用しない場合、すべてのテキスト コンテンツ (存在する場合はすべてのサブ要素のテキスト コンテンツも含む) が 1 つのテキスト文字列としてマップされます。</span><span class="sxs-lookup"><span data-stu-id="26f6e-105">If text() were not used in this XSLT statement, the result would be that all text content, plus any text content of subelements, would be mapped as one string of text.</span></span> <span data-ttu-id="26f6e-106">構成、**送信元のリンク**リンクのプロパティでは、送信先スキーマで定義された構造にコピーされるデータのソースを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="26f6e-106">Configuring the **Source Links** property for a link allows you to control the source of the data that is copied into the structure defined by the destination schema.</span></span>  
  
 <span data-ttu-id="26f6e-107">表示されるプロパティのいずれかの表示されているグリッド ページで、リンクを選択すると、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウが、**送信元のリンク**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="26f6e-107">When you select a link in the displayed grid page, one of the properties displayed in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window is the **Source Links** property.</span></span> <span data-ttu-id="26f6e-108">マップの各リンクに対して選択できる設定可能な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="26f6e-108">You can choose between the following possible values for each link in your map:</span></span>  
  
-   <span data-ttu-id="26f6e-109">**テキスト値をコピーします。**</span><span class="sxs-lookup"><span data-stu-id="26f6e-109">**Copy text value.**</span></span> <span data-ttu-id="26f6e-110">この値 (既定) を使用すると、入力インスタンス メッセージの要素または属性の値がコピーされます。</span><span class="sxs-lookup"><span data-stu-id="26f6e-110">Use this value, which is the default, to copy the value of the element or attribute in the input instance message.</span></span> <span data-ttu-id="26f6e-111">たとえば、関連する要素が BoldExample の場合、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="26f6e-111">For example, if the relevant element is BoldExample, as follows:</span></span>  
  
    ```  
    <BoldExample>This is a <B>Bold Text</B> example.</BoldExample>  
    ```  
  
     <span data-ttu-id="26f6e-112">出力インスタンス メッセージの関連する要素または属性に、"This is a " という値がコピーされます。</span><span class="sxs-lookup"><span data-stu-id="26f6e-112">The value copied into the relevant element or attribute in the output instance message is "This is a ".</span></span> <span data-ttu-id="26f6e-113">上記の例のように混合コンテンツ要素の場合は、希望どおりの結果にならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="26f6e-113">For mixed content elements like this, this result may not be what is desired.</span></span> <span data-ttu-id="26f6e-114">混合コンテンツ要素は比較的まれであるためですが、**テキスト値をコピー**の設定、**送信元のリンク**プロパティは、ほとんどの場合に適切な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="26f6e-114">But because mixed content elements are relatively rare, the **Copy text value** setting for the **Source Links** property is probably appropriate in most cases.</span></span>  
  
-   <span data-ttu-id="26f6e-115">**名前をコピーします。**</span><span class="sxs-lookup"><span data-stu-id="26f6e-115">**Copy name.**</span></span> <span data-ttu-id="26f6e-116">この値を使用すると、入力インスタンス メッセージのノードの名前がコピーされます。</span><span class="sxs-lookup"><span data-stu-id="26f6e-116">Use this value to copy the name of the node in the input instance message.</span></span> <span data-ttu-id="26f6e-117">例で、**テキスト値をコピー**については、結果は"boldexample"の場合、これは、要素の実際の名前。</span><span class="sxs-lookup"><span data-stu-id="26f6e-117">For the example in the **Copy text value** description, the result is "BoldExample", which is the actual name of the element.</span></span>  
  
-   <span data-ttu-id="26f6e-118">**テキストのコピーし、サブコンテンツの値。**</span><span class="sxs-lookup"><span data-stu-id="26f6e-118">**Copy text and sub content value.**</span></span> <span data-ttu-id="26f6e-119">この値を使用すると、入力インスタンス メッセージのノードの値と子ノードのすべての値が連結されます。</span><span class="sxs-lookup"><span data-stu-id="26f6e-119">Use this value to concatenate the values of the node and all values of its child nodes in the input instance message.</span></span> <span data-ttu-id="26f6e-120">例で、**テキスト値をコピー** 「これは、太字のテキストの例です。」、説明、結果は場合がよくあります混合コンテンツを含むように定義する要素の適切な結果です。</span><span class="sxs-lookup"><span data-stu-id="26f6e-120">For the example in the **Copy text value** description, the result is "This is a Bold Text example.", which might very well be the appropriate result for elements defined to contain mixed content.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26f6e-121">参照</span><span class="sxs-lookup"><span data-stu-id="26f6e-121">See Also</span></span>  
 <span data-ttu-id="26f6e-122">[一括コピー Functoid](../core/mass-copy-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="26f6e-122">[Mass Copy Functoid](../core/mass-copy-functoid.md) </span></span>  
 <span data-ttu-id="26f6e-123">[ソースへのリンクのコンパイラ値を設定する方法](../core/how-to-set-the-source-links-compiler-value.md) </span><span class="sxs-lookup"><span data-stu-id="26f6e-123">[How to Set the Source Links Compiler Value](../core/how-to-set-the-source-links-compiler-value.md) </span></span>  
 [<span data-ttu-id="26f6e-124">ノード階層レベルの照合</span><span class="sxs-lookup"><span data-stu-id="26f6e-124">Node-Hierarchy Level Matching</span></span>](../core/node-hierarchy-level-matching.md)