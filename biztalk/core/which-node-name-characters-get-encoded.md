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
ms.openlocfilehash: 810476ccd640b33ecf5996bc351947a8bceb0ad4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394791"
---
# <a name="which-node-name-characters-get-encoded"></a><span data-ttu-id="feead-102">ノード名における文字エン コード</span><span class="sxs-lookup"><span data-stu-id="feead-102">Which Node Name Characters Get Encoded</span></span>
<span data-ttu-id="feead-103">XML は、いくつかの制限をいくつかの特別な XML 名の最初の文字制限など、要素名などの XML 名に使用できる文字に配置します。</span><span class="sxs-lookup"><span data-stu-id="feead-103">XML places some restrictions on the characters that can be used in XML names, such as element names, including some special restrictions on the first character of an XML name.</span></span> <span data-ttu-id="feead-104">どの文字を許可して有効な XML 名から除外する文字の決定に使用すべき次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="feead-104">The conceptual goals in determining which characters to allow and which characters to exclude from legal XML names are:</span></span>  
  
- <span data-ttu-id="feead-105">可能な場合は、新しい書記を確保できるように Unicode でエンコードされているように、排他的ではなく包括的に。</span><span class="sxs-lookup"><span data-stu-id="feead-105">Wherever applicable, be inclusive rather than exclusive, so that new writing systems can be accommodated as they are encoded in Unicode.</span></span>  
  
- <span data-ttu-id="feead-106">XML 名は、XML、以外でより簡単に表示されます。 コンテキストを区切られるようにすることがありますまたは区切り記号として使用される文字を除外します。</span><span class="sxs-lookup"><span data-stu-id="feead-106">Exclude characters that may be or are used as delimiters, so that XML names can more easily appear in a non-XML, delimited context.</span></span>  
  
  <span data-ttu-id="feead-107">次の表は、どの文字を任意の位置は、名前または任意の位置、先頭以外で XML 名で使用することができます。</span><span class="sxs-lookup"><span data-stu-id="feead-107">The following table shows which characters can be used in an XML name, either in any position within the name, or in any position other than the first.</span></span> <span data-ttu-id="feead-108">いくつか使用できる文字は、名前の最初の文字の中から除外されます。</span><span class="sxs-lookup"><span data-stu-id="feead-108">Some allowable characters are excluded from being the first character in the name.</span></span> <span data-ttu-id="feead-109">リテラル文字が引用符で囲まれたと範囲は角かっこ内に表示します。</span><span class="sxs-lookup"><span data-stu-id="feead-109">Literal characters are quoted, and ranges are shown within square brackets.</span></span>  
  
|<span data-ttu-id="feead-110">名前における位置</span><span class="sxs-lookup"><span data-stu-id="feead-110">Position in name</span></span>|<span data-ttu-id="feead-111">許可されている文字</span><span class="sxs-lookup"><span data-stu-id="feead-111">Allowed characters</span></span>|  
|----------------------|------------------------|  
|<span data-ttu-id="feead-112">任意の位置</span><span class="sxs-lookup"><span data-stu-id="feead-112">Any position</span></span>|<span data-ttu-id="feead-113">["A"、"Z"]、["a"、"z"]、「_」、0x00C0-0x02FF、0x0370-0x037D、0x037F-0x1FFF、0x200C-0x200D、0x2070-0x218F、0x2C00-0x2FEF、[0x3001 0xD7FF]、[0xF900 0 xefff]</span><span class="sxs-lookup"><span data-stu-id="feead-113">["A"-"Z"], ["a"-"z"], "_", [0x00C0-0x02FF], [0x0370-0x037D], [0x037F-0x1FFF], [0x200C-0x200D], [0x2070-0x218F], [0x2C00-0x2FEF], [0x3001-0xD7FF], [0xF900-0xEFFF]</span></span>|  
|<span data-ttu-id="feead-114">先頭を除く任意の位置</span><span class="sxs-lookup"><span data-stu-id="feead-114">Any position except first</span></span>|<span data-ttu-id="feead-115">"-"、"."、[「0」-「9」]、0x00B7、[0x0300-0x036F]、[0x203f-0x2040]</span><span class="sxs-lookup"><span data-stu-id="feead-115">"-", ".", ["0"-"9"], 0x00B7, [0x0300-0x036F], [0x203F-0x2040]</span></span>|  
  
 <span data-ttu-id="feead-116">として英語での要素または属性名 (スキーマ ツリー ビューでノード名) のベスト プラクティスをまとめることができます。</span><span class="sxs-lookup"><span data-stu-id="feead-116">Best practice in English for an element or attribute name (a node name in the schema tree view) can be summarized as:</span></span>  
  
-   <span data-ttu-id="feead-117">点を除いては、英数字を使用していない名前に数値を開始します。</span><span class="sxs-lookup"><span data-stu-id="feead-117">Use alphanumeric characters, except do not begin a name with a numeral.</span></span>  
  
-   <span data-ttu-id="feead-118">アンダー スコア (_)、ハイフン (-)、ピリオド (.)、および中間点 (押し) を使用します。</span><span class="sxs-lookup"><span data-stu-id="feead-118">Use the underscore (_),hyphen (-), period (.), and middle dot (·).</span></span>  
  
-   <span data-ttu-id="feead-119">空白文字は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="feead-119">Do not use white space.</span></span>  
  
-   <span data-ttu-id="feead-120">自然言語で意味のある単語または単語の組み合わせを使用します。</span><span class="sxs-lookup"><span data-stu-id="feead-120">Use meaningful words or combinations of words in natural languages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="feead-121">参照</span><span class="sxs-lookup"><span data-stu-id="feead-121">See Also</span></span>  
 <span data-ttu-id="feead-122">[ノード名プロパティ](../core/node-name-property.md) </span><span class="sxs-lookup"><span data-stu-id="feead-122">[Node Name Property](../core/node-name-property.md) </span></span>  
 [<span data-ttu-id="feead-123">ノード名の文字エンコードの方法</span><span class="sxs-lookup"><span data-stu-id="feead-123">How Node Name Characters Get Encoded</span></span>](../core/how-node-name-characters-get-encoded.md)