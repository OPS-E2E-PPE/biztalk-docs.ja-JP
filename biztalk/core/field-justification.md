---
title: "位置揃えのフィールド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 04380208-9bfd-43cf-a279-104daea2b978
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da9209040e64380b3a7a167dd013a15232543a75
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="field-justification"></a><span data-ttu-id="67974-102">フィールドの位置揃え</span><span class="sxs-lookup"><span data-stu-id="67974-102">Field Justification</span></span>

## <a name="overview"></a><span data-ttu-id="67974-103">概要</span><span class="sxs-lookup"><span data-stu-id="67974-103">Overview</span></span>
<span data-ttu-id="67974-104">フィールドの位置揃えは、フィールド データの文字が埋め込み文字の前 (左揃えの場合) に出現するか、後 (右揃えの場合) に出現するかを制御します。</span><span class="sxs-lookup"><span data-stu-id="67974-104">Field justification concerns whether the data characters in a field occur before (left-aligned) or after (right-aligned) any accompanying pad characters.</span></span>  
  
 <span data-ttu-id="67974-105">フィールドに含まれるデータの文字数が、そのフィールドに割り当てられている領域と必ずしも一致するとは限りません。フィールドの領域が余る場合もあります。</span><span class="sxs-lookup"><span data-stu-id="67974-105">Sometimes the data characters contained within a field do not require all of the space dedicated to that field.</span></span> <span data-ttu-id="67974-106">これは、によって決定されるバイト数またはフィールドに割り当てられる文字数が固定の位置指定レコードで最も頻繁には true、**位置指定値**と**位置指定オフセット**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="67974-106">This is true most frequently in positional records, where the number of bytes or characters dedicated to a field is fixed, as determined by the **Positional Length** and **Positional Offset** properties.</span></span> <span data-ttu-id="67974-107">データ項目がフィールド長よりも短い場合、使用されないフィールド領域には、埋め込み文字が挿入されます。</span><span class="sxs-lookup"><span data-stu-id="67974-107">It is common in such scenarios that the item of data is smaller than the field length, with the unused portion of the field being filled with pad characters.</span></span>  
  
 <span data-ttu-id="67974-108">このような埋め込みは区切られたレコードにも発生するときの値、**埋め込み文字を含めた最小の長さ**プロパティは、データの関連する項目を格納するために必要な領域を超えています。</span><span class="sxs-lookup"><span data-stu-id="67974-108">Such padding can also occur in delimited records when the value of the **Minimum Length with Pad Character** property exceeds the space required to store the relevant item of data.</span></span>  
  
 <span data-ttu-id="67974-109">両方このような場合の値、 **Justification**プロパティ (**左**または**右**) の関連**フィールド要素**または**Field 属性**ノードは、埋め込み文字が、データの文字 (左揃え) を後ろするかどうか、または埋め込み文字は (右揃え)、データ文字の前にするかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="67974-109">In both such cases, the value of the **Justification** property (**Left** or **Right**) of the relevant **Field Element** or **Field Attribute** node determines whether the pad characters will follow the data characters (left-aligned) or whether the pad characters will precede the data characters (right-aligned).</span></span>  
  
 <span data-ttu-id="67974-110">同等の XML インスタンス メッセージに、フラット ファイル逆アセンブラーがフラット ファイル インスタンス メッセージを変換するときに、 **Justification**プロパティは、対応するフィールドを解析するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="67974-110">When the flat file disassembler is converting a flat file instance message into an equivalent XML instance message, the **Justification** property is used when parsing the corresponding field.</span></span> <span data-ttu-id="67974-111">フラット ファイル アセンブラーが、同等のフラット ファイル インスタンス メッセージに XML インスタンス メッセージを変換するときに、 **Justification**と埋め込み文字に関連付けられている特定のフィールドでは、存在する場合を決定するプロパティを使用データ ストリームに追加する必要があります。 前に、または対応するデータの文字の後にします。</span><span class="sxs-lookup"><span data-stu-id="67974-111">When the flat file assembler is converting an XML instance message into an equivalent flat file instance message, the **Justification** property is used to determine when the pad characters associated with a particular field, if any, should be added to the data stream: either before or after the corresponding data characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67974-112">参照</span><span class="sxs-lookup"><span data-stu-id="67974-112">See Also</span></span>  
- [<span data-ttu-id="67974-113">フィールドに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="67974-113">Field Considerations</span></span>](../core/field-considerations.md)   
- <span data-ttu-id="67974-114">詳細については、次のプロパティで[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span><span class="sxs-lookup"><span data-stu-id="67974-114">More info on the following properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span></span>  
    - <span data-ttu-id="67974-115">位置揃え (フラット ファイル スキーマのノード プロパティ)</span><span class="sxs-lookup"><span data-stu-id="67974-115">Justification (Node Property of Flat File Schemas)</span></span>  
    - <span data-ttu-id="67974-116">位置指定オフセット (フラット ファイル スキーマのノード プロパティ)</span><span class="sxs-lookup"><span data-stu-id="67974-116">Positional Offset (Node Property of Flat File Schemas)</span></span>  
    - <span data-ttu-id="67974-117">位置指定値 (フラット ファイル スキーマのノード プロパティ)</span><span class="sxs-lookup"><span data-stu-id="67974-117">Positional Length (Node Property of Flat File Schemas)</span></span>