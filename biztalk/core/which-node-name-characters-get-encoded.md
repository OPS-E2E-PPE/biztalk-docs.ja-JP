---
title: ノード名における文字エン コードが |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48a581d2-48fa-4c36-b5c2-fe87c328a7f4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b72c7bb1eb05e8bb8ce8c0596cbacc88cb3d2f0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022072"
---
# <a name="which-node-name-characters-get-encoded"></a><span data-ttu-id="c2b5c-102">ノード名における文字エンコード</span><span class="sxs-lookup"><span data-stu-id="c2b5c-102">Which Node Name Characters Get Encoded</span></span>
<span data-ttu-id="c2b5c-103">XML には、XML 名の先頭文字に対する特殊な制約も含め、要素名などの XML 名に使用できる文字に制限があります。</span><span class="sxs-lookup"><span data-stu-id="c2b5c-103">XML places some restrictions on the characters that can be used in XML names, such as element names, including some special restrictions on the first character of an XML name.</span></span> <span data-ttu-id="c2b5c-104">どのような文字を使用でき、また、どのような文字を使用すべきでないかというガイドラインを次に示します。</span><span class="sxs-lookup"><span data-stu-id="c2b5c-104">The conceptual goals in determining which characters to allow and which characters to exclude from legal XML names are:</span></span>  
  
- <span data-ttu-id="c2b5c-105">新しい書記体系に対応できるよう、できるだけ汎用性の高い文字 (つまり、Unicode にエンコード可能な文字) を使用する。</span><span class="sxs-lookup"><span data-stu-id="c2b5c-105">Wherever applicable, be inclusive rather than exclusive, so that new writing systems can be accommodated as they are encoded in Unicode.</span></span>  
  
- <span data-ttu-id="c2b5c-106">区切り記号として使われる可能性のある文字は使用しない。区切り記号が使用された、XML 以外のコンテキストに XML 名が表示されることも考慮する。</span><span class="sxs-lookup"><span data-stu-id="c2b5c-106">Exclude characters that may be or are used as delimiters, so that XML names can more easily appear in a non-XML, delimited context.</span></span>  
  
  <span data-ttu-id="c2b5c-107">次の表は、XML 名として使用できる文字を示しています。任意の位置で使用できる文字と、先頭以外のすべての位置で使用できる文字とに分類されています。</span><span class="sxs-lookup"><span data-stu-id="c2b5c-107">The following table shows which characters can be used in an XML name, either in any position within the name, or in any position other than the first.</span></span> <span data-ttu-id="c2b5c-108">名前の先頭文字としては使用できないが、他の位置であれば使用できる文字もあるためです。</span><span class="sxs-lookup"><span data-stu-id="c2b5c-108">Some allowable characters are excluded from being the first character in the name.</span></span> <span data-ttu-id="c2b5c-109">リテラル文字は引用符で囲み、文字の範囲は角かっこで示しています。</span><span class="sxs-lookup"><span data-stu-id="c2b5c-109">Literal characters are quoted, and ranges are shown within square brackets.</span></span>  
  
|<span data-ttu-id="c2b5c-110">名前における位置</span><span class="sxs-lookup"><span data-stu-id="c2b5c-110">Position in name</span></span>|<span data-ttu-id="c2b5c-111">使用可能な文字</span><span class="sxs-lookup"><span data-stu-id="c2b5c-111">Allowed characters</span></span>|  
|----------------------|------------------------|  
|<span data-ttu-id="c2b5c-112">任意の位置</span><span class="sxs-lookup"><span data-stu-id="c2b5c-112">Any position</span></span>|<span data-ttu-id="c2b5c-113">["A"-"Z"]、["a"-"z"]、"_"、[0x00C0-0x02FF]、[0x0370-0x037D]、[0x037F-0x1FFF]、[0x200C-0x200D]、[0x2070-0x218F]、[0x2C00-0x2FEF]、[0x3001-0xD7FF]、[0xF900-0xEFFF]</span><span class="sxs-lookup"><span data-stu-id="c2b5c-113">["A"-"Z"], ["a"-"z"], "_", [0x00C0-0x02FF], [0x0370-0x037D], [0x037F-0x1FFF], [0x200C-0x200D], [0x2070-0x218F], [0x2C00-0x2FEF], [0x3001-0xD7FF], [0xF900-0xEFFF]</span></span>|  
|<span data-ttu-id="c2b5c-114">先頭を除く任意の位置</span><span class="sxs-lookup"><span data-stu-id="c2b5c-114">Any position except first</span></span>|<span data-ttu-id="c2b5c-115">"-"、"."、["0"-"9"]、0x00B7、[0x0300-0x036F]、[0x203F-0x2040]</span><span class="sxs-lookup"><span data-stu-id="c2b5c-115">"-", ".", ["0"-"9"], 0x00B7, [0x0300-0x036F], [0x203F-0x2040]</span></span>|  
  
 <span data-ttu-id="c2b5c-116">英語の要素名または属性名 (スキーマ ツリー ビューでのノード名) を使用する場合のベスト プラクティスを次に示します。</span><span class="sxs-lookup"><span data-stu-id="c2b5c-116">Best practice in English for an element or attribute name (a node name in the schema tree view) can be summarized as:</span></span>  
  
-   <span data-ttu-id="c2b5c-117">英数字文字を使用する。ただし、先頭に数値は使用しない。</span><span class="sxs-lookup"><span data-stu-id="c2b5c-117">Use alphanumeric characters, except do not begin a name with a numeral.</span></span>  
  
-   <span data-ttu-id="c2b5c-118">アンダー スコア (_)、ハイフン (-)、ピリオド (.)、および中間点 (押し) を使用します。</span><span class="sxs-lookup"><span data-stu-id="c2b5c-118">Use the underscore (_),hyphen (-), period (.), and middle dot (·).</span></span>  
  
-   <span data-ttu-id="c2b5c-119">スペースは使用しない。</span><span class="sxs-lookup"><span data-stu-id="c2b5c-119">Do not use white space.</span></span>  
  
-   <span data-ttu-id="c2b5c-120">意味を把握しやすい単語または単語の組み合わせを使用する。</span><span class="sxs-lookup"><span data-stu-id="c2b5c-120">Use meaningful words or combinations of words in natural languages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2b5c-121">参照</span><span class="sxs-lookup"><span data-stu-id="c2b5c-121">See Also</span></span>  
 <span data-ttu-id="c2b5c-122">[ノード名プロパティ](../core/node-name-property.md) </span><span class="sxs-lookup"><span data-stu-id="c2b5c-122">[Node Name Property](../core/node-name-property.md) </span></span>  
 [<span data-ttu-id="c2b5c-123">ノード名の文字エンコードの方法</span><span class="sxs-lookup"><span data-stu-id="c2b5c-123">How Node Name Characters Get Encoded</span></span>](../core/how-node-name-characters-get-encoded.md)