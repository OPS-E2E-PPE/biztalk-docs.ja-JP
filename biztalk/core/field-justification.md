---
title: フィールドの妥当性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04380208-9bfd-43cf-a279-104daea2b978
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f6ddea01774cdae6fb17c27212f2d53351fa072
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345578"
---
# <a name="field-justification"></a><span data-ttu-id="f4007-102">フィールドの位置揃え</span><span class="sxs-lookup"><span data-stu-id="f4007-102">Field Justification</span></span>

## <a name="overview"></a><span data-ttu-id="f4007-103">概要</span><span class="sxs-lookup"><span data-stu-id="f4007-103">Overview</span></span>
<span data-ttu-id="f4007-104">フィールドのデータの文字にする前に発生するかどうかに関係するフィールドの位置揃え (左揃え) または後 (右揃え)、埋め込み文字に付属します。</span><span class="sxs-lookup"><span data-stu-id="f4007-104">Field justification concerns whether the data characters in a field occur before (left-aligned) or after (right-aligned) any accompanying pad characters.</span></span>  
  
 <span data-ttu-id="f4007-105">場合によってフィールド内に含まれるデータの文字では、そのフィールドに専用の領域をすべて必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f4007-105">Sometimes the data characters contained within a field do not require all of the space dedicated to that field.</span></span> <span data-ttu-id="f4007-106">これは、によって決定されるバイト数またはフィールドに割り当てられる文字の数が固定の位置指定レコードで最も頻繁には true、**位置指定値**と**位置指定オフセット**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="f4007-106">This is true most frequently in positional records, where the number of bytes or characters dedicated to a field is fixed, as determined by the **Positional Length** and **Positional Offset** properties.</span></span> <span data-ttu-id="f4007-107">データの項目が埋め込み文字が挿入されているフィールドの未使用の部分で、フィールドの長さより小さいこと、このようなシナリオで一般的です。</span><span class="sxs-lookup"><span data-stu-id="f4007-107">It is common in such scenarios that the item of data is smaller than the field length, with the unused portion of the field being filled with pad characters.</span></span>  
  
 <span data-ttu-id="f4007-108">このような埋め込みは、区切られたレコードにも発生時の値、**埋め込み文字を含めた最小値**プロパティは、データの関連する項目を格納するために必要な領域を超えています。</span><span class="sxs-lookup"><span data-stu-id="f4007-108">Such padding can also occur in delimited records when the value of the **Minimum Length with Pad Character** property exceeds the space required to store the relevant item of data.</span></span>  
  
 <span data-ttu-id="f4007-109">両方このような場合の値、 **Justification**プロパティ (**左**または**右**) の関連**フィールド要素**または**フィールド属性**ノードが埋め込み文字が、データの文字 (左揃え) に従うかどうか、または埋め込み文字は (右揃え)、データ文字の前にするかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="f4007-109">In both such cases, the value of the **Justification** property (**Left** or **Right**) of the relevant **Field Element** or **Field Attribute** node determines whether the pad characters will follow the data characters (left-aligned) or whether the pad characters will precede the data characters (right-aligned).</span></span>  
  
 <span data-ttu-id="f4007-110">フラット ファイル逆アセンブラーは、フラット ファイル インスタンス メッセージを同等の XML インスタンス メッセージに変換されるとき、 **Justification**プロパティは、対応するフィールドを解析するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f4007-110">When the flat file disassembler is converting a flat file instance message into an equivalent XML instance message, the **Justification** property is used when parsing the corresponding field.</span></span> <span data-ttu-id="f4007-111">フラット ファイル アセンブラーが、同等のフラット ファイル インスタンス メッセージに XML インスタンス メッセージを変換するときに、**理由**プロパティを使用して、存在する場合と、埋め込み文字が特定のフィールドに関連付けられたを確認します。データ ストリームに追加する必要があります。 前または後、対応するデータの文字。</span><span class="sxs-lookup"><span data-stu-id="f4007-111">When the flat file assembler is converting an XML instance message into an equivalent flat file instance message, the **Justification** property is used to determine when the pad characters associated with a particular field, if any, should be added to the data stream: either before or after the corresponding data characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4007-112">参照</span><span class="sxs-lookup"><span data-stu-id="f4007-112">See Also</span></span>  
- [<span data-ttu-id="f4007-113">フィールドに関する注意</span><span class="sxs-lookup"><span data-stu-id="f4007-113">Field Considerations</span></span>](../core/field-considerations.md)   
- <span data-ttu-id="f4007-114">詳細については、次のプロパティで[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span><span class="sxs-lookup"><span data-stu-id="f4007-114">More info on the following properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span></span>  
    - <span data-ttu-id="f4007-115">位置揃え (フラット ファイル スキーマのノード プロパティ)</span><span class="sxs-lookup"><span data-stu-id="f4007-115">Justification (Node Property of Flat File Schemas)</span></span>  
    - <span data-ttu-id="f4007-116">位置指定オフセット (フラット ファイル スキーマのノード プロパティ)</span><span class="sxs-lookup"><span data-stu-id="f4007-116">Positional Offset (Node Property of Flat File Schemas)</span></span>  
    - <span data-ttu-id="f4007-117">位置指定値 (フラット ファイル スキーマのノード プロパティ)</span><span class="sxs-lookup"><span data-stu-id="f4007-117">Positional Length (Node Property of Flat File Schemas)</span></span>