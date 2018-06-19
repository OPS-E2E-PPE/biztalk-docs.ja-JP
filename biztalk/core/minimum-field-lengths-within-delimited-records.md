---
title: 区切られたレコード内の最小フィールド長 |Microsoft ドキュメント
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
ms.openlocfilehash: d803eb311bda7c27db5a05830f7a84f9b9857e8f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263642"
---
# <a name="minimum-field-lengths-within-delimited-records"></a><span data-ttu-id="cd048-102">区切られたレコード内の最小フィールド長</span><span class="sxs-lookup"><span data-stu-id="cd048-102">Minimum Field Lengths Within Delimited Records</span></span>
<span data-ttu-id="cd048-103">位置指定レコードの定義では、すべてのフィールドは、特定の厳密な長さに定義されます。</span><span class="sxs-lookup"><span data-stu-id="cd048-103">By definition, the fields in positional records are all defined to have specific exact lengths.</span></span> <span data-ttu-id="cd048-104">区切られたレコードでは、レコードのフィールドに対して最小のフィールド長を定義できます。</span><span class="sxs-lookup"><span data-stu-id="cd048-104">Fields in delimited records can also be defined to have a minimum length.</span></span> <span data-ttu-id="cd048-105">この特性がによって定義された、 **[埋め込み文字を含めた最小の長さ**プロパティの**フィールド要素**と**フィールド属性**ノード。</span><span class="sxs-lookup"><span data-stu-id="cd048-105">This characteristic is defined by the **[Minimum Length with Pad Character** property of **Field Element** and **Field Attribute** nodes.</span></span>  
  
 <span data-ttu-id="cd048-106">以外の値を指定すると、**埋め込み文字を含めた最小の長さ**プロパティ、フラット ファイル アセンブラーがかどうかをフィールドに関連付けられているデータの文字の数、の設定よりも小さい**埋め込み文字を含めた最小の長さ**プロパティの違いは、構成に使用する埋め込み文字。</span><span class="sxs-lookup"><span data-stu-id="cd048-106">When you provide a nonzero value for the **Minimum Length with Pad Character** property, the flat file assembler will determine whether the number of data characters associated with the field is smaller than the setting of the **Minimum Length with Pad Character** property, the relevant pad character will be used to make up the difference.</span></span>  
  
 <span data-ttu-id="cd048-107">設定に基づいて、データ文字の前後に埋め込み文字が追加されます、 **Justification**フィールドのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="cd048-107">The pad characters will be added before or after the data characters based on the setting of the **Justification** property for the field.</span></span> <span data-ttu-id="cd048-108">ときに、 **Justification**プロパティに設定されている**左**を最小の長さを満たすために必要な埋め込み文字は、データ文字の後に追加されます。</span><span class="sxs-lookup"><span data-stu-id="cd048-108">When the **Justification** property is set to **Left**, any pad characters required to meet the minimum length will be added after the data characters.</span></span> <span data-ttu-id="cd048-109">ときに、 **Justification**プロパティに設定されている**右**を最小の長さを満たすために必要な埋め込み文字は、データ文字の前に追加されます。</span><span class="sxs-lookup"><span data-stu-id="cd048-109">When the **Justification** property is set to **Right**, any pad characters required to meet the minimum length will be added before the data characters.</span></span>  
  
 <span data-ttu-id="cd048-110">以外の値を指定すると、**埋め込み文字を含めた最小の長さ**プロパティ、フラット ファイル逆アセンブラーは、先頭または末尾を調べます (の設定に基づいて、 **Justification**プロパティ) のフィールド値の適切な埋め込み文字の存在と存在する場合、埋め込み文字は破棄され、構築される同等の XML メッセージに表示されません。</span><span class="sxs-lookup"><span data-stu-id="cd048-110">When you provide a nonzero value for the **Minimum Length with Pad Character** property, the flat file disassembler will examine the beginning or end (based on the setting of the **Justification** property) of the field value for the presence of the relevant pad character, and if present, the pad characters will be discarded and not appear in the equivalent XML message being constructed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd048-111">参照</span><span class="sxs-lookup"><span data-stu-id="cd048-111">See Also</span></span>  
-  [<span data-ttu-id="cd048-112">フィールドに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="cd048-112">Field Considerations</span></span>](../core/field-considerations.md)   
-  <span data-ttu-id="cd048-113">**位置揃え (フラット ファイル スキーマのノード プロパティ)** と**埋め込み文字 (フラット ファイル スキーマのノード プロパティ) を含めた最小長**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="cd048-113">**Justification (Node Property of Flat File Schemas)** and **Minimum Length with Pad Character (Node Property of Flat File Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>