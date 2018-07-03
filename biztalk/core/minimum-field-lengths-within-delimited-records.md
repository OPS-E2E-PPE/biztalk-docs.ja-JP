---
title: 区切られたレコード内の最小フィールド長 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24272d0d-34c8-487a-9334-683c65c159b8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 992ffbc6a2e0568bc000413bf90b3c92012d4d59
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983315"
---
# <a name="minimum-field-lengths-within-delimited-records"></a><span data-ttu-id="524e7-102">区切られたレコード内の最小フィールド長</span><span class="sxs-lookup"><span data-stu-id="524e7-102">Minimum Field Lengths Within Delimited Records</span></span>
<span data-ttu-id="524e7-103">位置指定レコードの定義では、すべてのフィールドは、特定の厳密な長さに定義されます。</span><span class="sxs-lookup"><span data-stu-id="524e7-103">By definition, the fields in positional records are all defined to have specific exact lengths.</span></span> <span data-ttu-id="524e7-104">区切られたレコードでは、レコードのフィールドに対して最小のフィールド長を定義できます。</span><span class="sxs-lookup"><span data-stu-id="524e7-104">Fields in delimited records can also be defined to have a minimum length.</span></span> <span data-ttu-id="524e7-105">このような特性がによって定義されている、 **[埋め込み文字を含めた最小値**プロパティの**フィールド要素**と**フィールド属性**ノード。</span><span class="sxs-lookup"><span data-stu-id="524e7-105">This characteristic is defined by the **[Minimum Length with Pad Character** property of **Field Element** and **Field Attribute** nodes.</span></span>  

 <span data-ttu-id="524e7-106">0 以外の値を指定すると、**埋め込み文字を含めた最小値**プロパティ、フラット ファイル アセンブラーがかどうかをフィールドに関連付けられたデータの文字の数、の設定よりも小さい**埋め込み文字を含めた最小値**プロパティ、違いは、構成に関連する埋め込み文字が使用されます。</span><span class="sxs-lookup"><span data-stu-id="524e7-106">When you provide a nonzero value for the **Minimum Length with Pad Character** property, the flat file assembler will determine whether the number of data characters associated with the field is smaller than the setting of the **Minimum Length with Pad Character** property, the relevant pad character will be used to make up the difference.</span></span>  

 <span data-ttu-id="524e7-107">前に、または後の設定に基づいてデータの文字に埋め込み文字が追加、 **Justification**フィールドのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="524e7-107">The pad characters will be added before or after the data characters based on the setting of the **Justification** property for the field.</span></span> <span data-ttu-id="524e7-108">ときに、 **Justification**プロパティに設定されて**左**、最小の長さを満たすために必要な埋め込み文字は、データ文字後に追加されます。</span><span class="sxs-lookup"><span data-stu-id="524e7-108">When the **Justification** property is set to **Left**, any pad characters required to meet the minimum length will be added after the data characters.</span></span> <span data-ttu-id="524e7-109">ときに、 **Justification**プロパティに設定されて**右**、最小の長さを満たすために必要な埋め込み文字は、データ文字の前に追加されます。</span><span class="sxs-lookup"><span data-stu-id="524e7-109">When the **Justification** property is set to **Right**, any pad characters required to meet the minimum length will be added before the data characters.</span></span>  

 <span data-ttu-id="524e7-110">0 以外の値を指定すると、**埋め込み文字を含めた最小値**プロパティ、フラット ファイル逆アセンブラーは、先頭または末尾が確認されます (の設定に基づいて、 **Justification**プロパティ) のフィールドの値、適切な埋め込み文字の存在と存在する場合、埋め込み文字は破棄され、構築される同等の XML メッセージに表示されません。</span><span class="sxs-lookup"><span data-stu-id="524e7-110">When you provide a nonzero value for the **Minimum Length with Pad Character** property, the flat file disassembler will examine the beginning or end (based on the setting of the **Justification** property) of the field value for the presence of the relevant pad character, and if present, the pad characters will be discarded and not appear in the equivalent XML message being constructed.</span></span>  

## <a name="see-also"></a><span data-ttu-id="524e7-111">参照</span><span class="sxs-lookup"><span data-stu-id="524e7-111">See Also</span></span>  
- [<span data-ttu-id="524e7-112">フィールドに関する注意</span><span class="sxs-lookup"><span data-stu-id="524e7-112">Field Considerations</span></span>](../core/field-considerations.md)   
- <span data-ttu-id="524e7-113">**位置揃え (フラット ファイル スキーマのノード プロパティ)** と**埋め込み文字 (フラット ファイル スキーマのノード プロパティ) を含めた最小値** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="524e7-113">**Justification (Node Property of Flat File Schemas)** and **Minimum Length with Pad Character (Node Property of Flat File Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
