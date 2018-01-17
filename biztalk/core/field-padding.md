---
title: "パディングをフィールド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 47017036-7d64-4222-b574-d2913bf69358
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56aa8490bd9e72677c9c8eefa73e7f6bd8438dfd
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="field-padding"></a><span data-ttu-id="99272-102">フィールドの埋め込み</span><span class="sxs-lookup"><span data-stu-id="99272-102">Field Padding</span></span>

## <a name="overview"></a><span data-ttu-id="99272-103">概要</span><span class="sxs-lookup"><span data-stu-id="99272-103">Overview</span></span>

<span data-ttu-id="99272-104">埋め込み文字は、フィールド内のデータが、そのフィールドに予約されている文字数またはバイト数より小さい場合、区切られたレコードおよび位置指定レコード内のフィールドで使用されます。</span><span class="sxs-lookup"><span data-stu-id="99272-104">Pad characters are used in fields within both delimited and positional records when the data contained within the field smaller than the number of characters or bytes reserved for the field.</span></span> <span data-ttu-id="99272-105">データだけではフィールドの長さが余ってしまうときに、その差を調整するための文字です。</span><span class="sxs-lookup"><span data-stu-id="99272-105">These characters occupy the portion of the field not required by the data, if any.</span></span> <span data-ttu-id="99272-106">使用してフィールドのごとに埋め込み文字が指定されて、**埋め込み文字**と**埋め込み文字の種類**の対応するプロパティ**フィールド要素**と**フィールド属性**ノード。</span><span class="sxs-lookup"><span data-stu-id="99272-106">Pad characters are specified on a field-by-field basis using the  **Pad Character** and **Pad Character Type** properties of the corresponding **Field Element** and **Field Attribute** nodes.</span></span> <span data-ttu-id="99272-107">特定のフィールドを既定の埋め込み文字の埋め込み文字が指定されていない場合は、スペース ("")、そのフィールドに使用します。</span><span class="sxs-lookup"><span data-stu-id="99272-107">If no pad character is specified for a particular field, the default pad character, space (" "), is used for that field.</span></span>  
  
## <a name="inbound-instances"></a><span data-ttu-id="99272-108">受信インスタンス</span><span class="sxs-lookup"><span data-stu-id="99272-108">Inbound instances</span></span>
 <span data-ttu-id="99272-109">受信インスタンス メッセージの場合、特定のレコードが位置指定ベースか区切り文字ベースであるかに関係なく、フラット ファイル逆アセンブラーは、インスタンス メッセージを等価な XML 形式に変換する際、特定のフィールドに対して指定された埋め込み文字または既定の埋め込み文字が先頭または末尾に出現する場合、それらの文字をすべて破棄します。</span><span class="sxs-lookup"><span data-stu-id="99272-109">For inbound instance messages, regardless of whether a particular record is positional or delimited, the flat file disassembler discards leading or trailing instances for the specified or default pad character for a particular field as the instance message is translated into its equivalent XML form.</span></span> <span data-ttu-id="99272-110">先頭または末尾の破棄された埋め込み文字のインスタンスかによって異なります、 **Justification**の対応するプロパティ**フィールド要素**と**フィールド属性**に設定されているノード**右**または**左**、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="99272-110">Whether it is leading or trailing instances of the relevant pad character that are discarded depends on whether the **Justification** property of corresponding **Field Element** and **Field Attribute** node is set to **Right** or **Left**, respectively.</span></span>  

## <a name="outbound-instances"></a><span data-ttu-id="99272-111">送信インスタンス</span><span class="sxs-lookup"><span data-stu-id="99272-111">Outbound instances</span></span>  
 <span data-ttu-id="99272-112">送信インスタンス メッセージの場合、フラット ファイル アセンブラーは、フィールドの長さと等しくなるように、指定された埋め込み文字または既定の埋め込み文字をフィールドに挿入します。</span><span class="sxs-lookup"><span data-stu-id="99272-112">For outbound instance messages, the flat file assembler will insert the appropriate number of the specified or default pad character into fields so that the length of the field is correct.</span></span> <span data-ttu-id="99272-113">前に、または後、データ文字かどうかに基づいて、埋め込み文字が挿入される、 **"位置揃え"** 対応するプロパティ **フィールド要素** と **フィールド属性** にノードが設定されている **右** または **左**, 、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="99272-113">The pad characters will be inserted before or after the data characters based on whether the **Justification** property of the corresponding **Field Element** and **Field Attribute** node is set to **Right** or **Left**, respectively.</span></span>  
  
 <span data-ttu-id="99272-114">送信インスタンス メッセージに埋め込まれているフィールドが位置指定レコード内に含まれるときに、**位置指定オフセット**と**位置指定値**の対応するプロパティ**フィールド要素**または**フィールド属性**フィールドを含める必要があるデータの文字の数と組み合わせると、すべてのノードには、埋め込み文字が必要であるかどうかと、そのが決定する数。</span><span class="sxs-lookup"><span data-stu-id="99272-114">When the field to be padded in an outbound instance message is contained within a positional record, the **Positional Offset** and **Positional Length** properties of the corresponding **Field Element** or **Field Attribute** node, combined with the number of data characters that the field must contain, determine whether any pad characters are required, and if so, how many.</span></span> <span data-ttu-id="99272-115">埋め込み文字がのみ、送信インスタンス メッセージに埋め込まれているフィールドは、区切られたレコード内に含まれる、ときに挿入されたときの値、**埋め込み文字を含めた最小の長さ**の対応するプロパティ**フィールド要素**または**フィールド属性**ノードは、データの文字数を超えています。</span><span class="sxs-lookup"><span data-stu-id="99272-115">When the field to be padded in an outbound instance message is contained within a delimited record, pad characters are only inserted when the value of the **Minimum Length with Pad Character** property of the corresponding **Field Element** or **Field Attribute** node exceeds the number of data characters.</span></span>  

## 
<span data-ttu-id="99272-116">これらのプロパティの詳細について[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="99272-116">More details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="99272-117">参照</span><span class="sxs-lookup"><span data-stu-id="99272-117">See Also</span></span>  
 <span data-ttu-id="99272-118">[フィールドに関する考慮事項](../core/field-considerations.md) </span><span class="sxs-lookup"><span data-stu-id="99272-118">[Field Considerations](../core/field-considerations.md) </span></span>  
 <span data-ttu-id="99272-119">[フィールドの位置揃え](../core/field-justification.md) </span><span class="sxs-lookup"><span data-stu-id="99272-119">[Field Justification](../core/field-justification.md) </span></span>  
 [<span data-ttu-id="99272-120">位置指定レコードにおけるフィールド位置の仕様</span><span class="sxs-lookup"><span data-stu-id="99272-120">Specification of Field Positions within Positional Records</span></span>](../core/specification-of-field-positions-within-positional-records.md)  