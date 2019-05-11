---
title: データ変換の構成 |Microsoft Docs
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
ms.openlocfilehash: 017f5b38c30acd37728fc1834ff39b3125f4f07f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352700"
---
# <a name="data-transformation-configuration"></a><span data-ttu-id="bbe5f-102">データ変換の構成</span><span class="sxs-lookup"><span data-stu-id="bbe5f-102">Data Transformation Configuration</span></span>
<span data-ttu-id="bbe5f-103">要素からマッピング、ように、一般的な XSLT Extensible Stylesheet Language Transformations () が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-103">When mapping from an element, a typical Extensible Stylesheet Language Transformations (XSLT) looks as follows.</span></span>  
  
```  
<xsl:attribute name='CatalogPurposeCode'>  
     <xsl:value-of select='BCT/BCT01/text()'/>  
</xsl:attribute>  
```  
  
 <span data-ttu-id="bbe5f-104">場合、要素**BCT01**を含む混合コンテンツ、text() を使用できるようになりますアクセスの最初のテキストが最初のサブ要素のポイントまでしか存在する場合。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-104">If the element **BCT01** contains mixed content, the use of text() makes it possible to access the first text only up to the point of the first subelement, if any.</span></span> <span data-ttu-id="bbe5f-105">この XSLT ステートメントで text() を使用しない場合の結果はテキストの 1 つの文字列としてマップは、すべてのテキスト コンテンツとサブ要素のテキストのコンテンツになります。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-105">If text() were not used in this XSLT statement, the result would be that all text content, plus any text content of subelements, would be mapped as one string of text.</span></span> <span data-ttu-id="bbe5f-106">構成、**ソース リンク**リンクのプロパティでは、送信先スキーマで定義された構造にコピーされたデータのソースを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-106">Configuring the **Source Links** property for a link allows you to control the source of the data that is copied into the structure defined by the destination schema.</span></span>  
  
 <span data-ttu-id="bbe5f-107">表示、プロパティの 1 つ表示されているグリッド ページで、リンクを選択すると、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウが、**ソース リンク**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-107">When you select a link in the displayed grid page, one of the properties displayed in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window is the **Source Links** property.</span></span> <span data-ttu-id="bbe5f-108">マップには、リンクごとに次の値の間で選択できます。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-108">You can choose between the following possible values for each link in your map:</span></span>  
  
-   <span data-ttu-id="bbe5f-109">**テキスト値をコピーします。**</span><span class="sxs-lookup"><span data-stu-id="bbe5f-109">**Copy text value.**</span></span> <span data-ttu-id="bbe5f-110">入力インスタンス メッセージ内の要素または属性の値をコピーするのにには、この値は、既定を使用します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-110">Use this value, which is the default, to copy the value of the element or attribute in the input instance message.</span></span> <span data-ttu-id="bbe5f-111">たとえば、次のように関連する要素が boldexample の場合、次のように設定されている場合。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-111">For example, if the relevant element is BoldExample, as follows:</span></span>  
  
    ```  
    <BoldExample>This is a <B>Bold Text</B> example.</BoldExample>  
    ```  
  
     <span data-ttu-id="bbe5f-112">値が関連する要素にコピーまたは出力インスタンス メッセージ内の属性は、"これは、"。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-112">The value copied into the relevant element or attribute in the output instance message is "This is a ".</span></span> <span data-ttu-id="bbe5f-113">このような混合コンテンツ要素をこの結果が希望どおりの結果は限りません。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-113">For mixed content elements like this, this result may not be what is desired.</span></span> <span data-ttu-id="bbe5f-114">混合コンテンツ要素は比較的まれであるため、**テキスト値をコピー**の設定、**ソース リンク**プロパティは、ほとんどの場合に適してします。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-114">But because mixed content elements are relatively rare, the **Copy text value** setting for the **Source Links** property is probably appropriate in most cases.</span></span>  
  
-   <span data-ttu-id="bbe5f-115">**名前をコピーします。**</span><span class="sxs-lookup"><span data-stu-id="bbe5f-115">**Copy name.**</span></span> <span data-ttu-id="bbe5f-116">入力インスタンス メッセージ内のノードの名前をコピーするのにには、この値を使用します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-116">Use this value to copy the name of the node in the input instance message.</span></span> <span data-ttu-id="bbe5f-117">例では、**テキスト値をコピー**説明、結果がある"BoldExample"要素の実際の名前です。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-117">For the example in the **Copy text value** description, the result is "BoldExample", which is the actual name of the element.</span></span>  
  
-   <span data-ttu-id="bbe5f-118">**コピーのテキストとサブコンテンツの値。**</span><span class="sxs-lookup"><span data-stu-id="bbe5f-118">**Copy text and sub content value.**</span></span> <span data-ttu-id="bbe5f-119">ノードの値と、入力インスタンス メッセージでは、その子ノードのすべての値を連結するのにには、この値を使用します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-119">Use this value to concatenate the values of the node and all values of its child nodes in the input instance message.</span></span> <span data-ttu-id="bbe5f-120">例では、**テキスト値をコピー** 「. これが太字のテキストの例」、説明、結果は、これは混合コンテンツを含むように定義する要素の適切な結果では非常にうまく可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-120">For the example in the **Copy text value** description, the result is "This is a Bold Text example.", which might very well be the appropriate result for elements defined to contain mixed content.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbe5f-121">参照</span><span class="sxs-lookup"><span data-stu-id="bbe5f-121">See Also</span></span>  
 <span data-ttu-id="bbe5f-122">[一括コピー Functoid](../core/mass-copy-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="bbe5f-122">[Mass Copy Functoid](../core/mass-copy-functoid.md) </span></span>  
 <span data-ttu-id="bbe5f-123">[ソース リンクのコンパイラ値を設定する方法](../core/how-to-set-the-source-links-compiler-value.md) </span><span class="sxs-lookup"><span data-stu-id="bbe5f-123">[How to Set the Source Links Compiler Value](../core/how-to-set-the-source-links-compiler-value.md) </span></span>  
 [<span data-ttu-id="bbe5f-124">ノード階層レベルの照合</span><span class="sxs-lookup"><span data-stu-id="bbe5f-124">Node-Hierarchy Level Matching</span></span>](../core/node-hierarchy-level-matching.md)