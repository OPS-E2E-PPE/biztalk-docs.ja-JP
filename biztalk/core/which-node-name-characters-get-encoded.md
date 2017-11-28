---
title: "ノード名における文字エン コードを |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48a581d2-48fa-4c36-b5c2-fe87c328a7f4
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3895fd74ac63380d5502a05eed7c145e13bfd681
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="which-node-name-characters-get-encoded"></a><span data-ttu-id="47996-102">ノード名における文字エンコード</span><span class="sxs-lookup"><span data-stu-id="47996-102">Which Node Name Characters Get Encoded</span></span>
<span data-ttu-id="47996-103">XML には、XML 名の先頭文字に対する特殊な制約も含め、要素名などの XML 名に使用できる文字に制限があります。</span><span class="sxs-lookup"><span data-stu-id="47996-103">XML places some restrictions on the characters that can be used in XML names, such as element names, including some special restrictions on the first character of an XML name.</span></span> <span data-ttu-id="47996-104">どのような文字を使用でき、また、どのような文字を使用すべきでないかというガイドラインを次に示します。</span><span class="sxs-lookup"><span data-stu-id="47996-104">The conceptual goals in determining which characters to allow and which characters to exclude from legal XML names are:</span></span>  
  
-   <span data-ttu-id="47996-105">新しい書記体系に対応できるよう、できるだけ汎用性の高い文字 (つまり、Unicode にエンコード可能な文字) を使用する。</span><span class="sxs-lookup"><span data-stu-id="47996-105">Wherever applicable, be inclusive rather than exclusive, so that new writing systems can be accommodated as they are encoded in Unicode.</span></span>  
  
-   <span data-ttu-id="47996-106">区切り記号として使われる可能性のある文字は使用しない。区切り記号が使用された、XML 以外のコンテキストに XML 名が表示されることも考慮する。</span><span class="sxs-lookup"><span data-stu-id="47996-106">Exclude characters that may be or are used as delimiters, so that XML names can more easily appear in a non-XML, delimited context.</span></span>  
  
 <span data-ttu-id="47996-107">次の表は、XML 名として使用できる文字を示しています。任意の位置で使用できる文字と、先頭以外のすべての位置で使用できる文字とに分類されています。</span><span class="sxs-lookup"><span data-stu-id="47996-107">The following table shows which characters can be used in an XML name, either in any position within the name, or in any position other than the first.</span></span> <span data-ttu-id="47996-108">名前の先頭文字としては使用できないが、他の位置であれば使用できる文字もあるためです。</span><span class="sxs-lookup"><span data-stu-id="47996-108">Some allowable characters are excluded from being the first character in the name.</span></span> <span data-ttu-id="47996-109">リテラル文字は引用符で囲み、文字の範囲は角かっこで示しています。</span><span class="sxs-lookup"><span data-stu-id="47996-109">Literal characters are quoted, and ranges are shown within square brackets.</span></span>  
  
|<span data-ttu-id="47996-110">名前における位置</span><span class="sxs-lookup"><span data-stu-id="47996-110">Position in name</span></span>|<span data-ttu-id="47996-111">使用可能な文字</span><span class="sxs-lookup"><span data-stu-id="47996-111">Allowed characters</span></span>|  
|----------------------|------------------------|  
|<span data-ttu-id="47996-112">任意の位置</span><span class="sxs-lookup"><span data-stu-id="47996-112">Any position</span></span>|<span data-ttu-id="47996-113">["A"-"Z"]、["a"-"z"]、"_"、[0x00C0-0x02FF]、[0x0370-0x037D]、[0x037F-0x1FFF]、[0x200C-0x200D]、[0x2070-0x218F]、[0x2C00-0x2FEF]、[0x3001-0xD7FF]、[0xF900-0xEFFF]</span><span class="sxs-lookup"><span data-stu-id="47996-113">["A"-"Z"], ["a"-"z"], "_", [0x00C0-0x02FF], [0x0370-0x037D], [0x037F-0x1FFF], [0x200C-0x200D], [0x2070-0x218F], [0x2C00-0x2FEF], [0x3001-0xD7FF], [0xF900-0xEFFF]</span></span>|  
|<span data-ttu-id="47996-114">先頭を除く任意の位置</span><span class="sxs-lookup"><span data-stu-id="47996-114">Any position except first</span></span>|<span data-ttu-id="47996-115">"-"、"."、["0"-"9"]、0x00B7、[0x0300-0x036F]、[0x203F-0x2040]</span><span class="sxs-lookup"><span data-stu-id="47996-115">"-", ".", ["0"-"9"], 0x00B7, [0x0300-0x036F], [0x203F-0x2040]</span></span>|  
  
 <span data-ttu-id="47996-116">英語の要素名または属性名 (スキーマ ツリー ビューでのノード名) を使用する場合のベスト プラクティスを次に示します。</span><span class="sxs-lookup"><span data-stu-id="47996-116">Best practice in English for an element or attribute name (a node name in the schema tree view) can be summarized as:</span></span>  
  
-   <span data-ttu-id="47996-117">英数字文字を使用する。ただし、先頭に数値は使用しない。</span><span class="sxs-lookup"><span data-stu-id="47996-117">Use alphanumeric characters, except do not begin a name with a numeral.</span></span>  
  
-   <span data-ttu-id="47996-118">アンダー スコア (_)、ハイフン (-)、ピリオド (.)、および中点 (·) を使用します。</span><span class="sxs-lookup"><span data-stu-id="47996-118">Use the underscore (_),hyphen (-), period (.), and middle dot (·).</span></span>  
  
-   <span data-ttu-id="47996-119">スペースは使用しない。</span><span class="sxs-lookup"><span data-stu-id="47996-119">Do not use white space.</span></span>  
  
-   <span data-ttu-id="47996-120">意味を把握しやすい単語または単語の組み合わせを使用する。</span><span class="sxs-lookup"><span data-stu-id="47996-120">Use meaningful words or combinations of words in natural languages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47996-121">参照</span><span class="sxs-lookup"><span data-stu-id="47996-121">See Also</span></span>  
 <span data-ttu-id="47996-122">[ノード名プロパティ](../core/node-name-property.md) </span><span class="sxs-lookup"><span data-stu-id="47996-122">[Node Name Property](../core/node-name-property.md) </span></span>  
 [<span data-ttu-id="47996-123">ノード名における文字エン コードの方法</span><span class="sxs-lookup"><span data-stu-id="47996-123">How Node Name Characters Get Encoded</span></span>](../core/how-node-name-characters-get-encoded.md)