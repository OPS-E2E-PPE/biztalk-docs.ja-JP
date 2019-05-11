---
title: 専用マップと汎用マップ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps, specific
- maps, generic
ms.assetid: ee26dd13-affb-47c5-961a-f2377129de22
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69b85658030540ae9b823a5eab32501a200f974c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243210"
---
# <a name="specific-and-generic-maps"></a><span data-ttu-id="46296-102">専用マップと汎用マップ</span><span class="sxs-lookup"><span data-stu-id="46296-102">Specific and Generic Maps</span></span>
<span data-ttu-id="46296-103">データを変換するマップを作成するときに、いずれかを作成、*特定*または*ジェネリック*マップします。</span><span class="sxs-lookup"><span data-stu-id="46296-103">When you create a map that transforms data, you can create either a *specific* or a *generic* map.</span></span>  
  
 <span data-ttu-id="46296-104">特定のマップを使用して、特定の取引先パートナーのニーズに対応します。</span><span class="sxs-lookup"><span data-stu-id="46296-104">You use a specific map to meet the needs of a particular trading partner.</span></span> <span data-ttu-id="46296-105">取引先パートナーと非常に特定のビジネス ニーズやビジネス アグリーメントがある場合は、特定のマップを使用します。</span><span class="sxs-lookup"><span data-stu-id="46296-105">Use a specific map when you have very specific business needs or business agreements with your trading partner.</span></span> <span data-ttu-id="46296-106">特定のマップの利点は、それを特定の取引先パートナーとビジネス関数のニーズに合わせてカスタマイズしたことです。</span><span class="sxs-lookup"><span data-stu-id="46296-106">The advantage of a specific map is that it is customized to meet the needs of the business functions you have with specific trading partners.</span></span> <span data-ttu-id="46296-107">特定のマップの欠点は、複数の取引先パートナーと使用できないことです。</span><span class="sxs-lookup"><span data-stu-id="46296-107">The disadvantage of a specific map is that it cannot be used with multiple trading partners.</span></span> <span data-ttu-id="46296-108">取引先と交換するさまざまなメッセージ型の数で取引先パートナーの数を乗算する場合は、十分な時間と関連付けられているマップのすべてを管理するリソースを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="46296-108">If you multiply the number of trading partners by the number of different message types exchanged with those trading partners, you must allocate enough time and resources to manage all of the associated maps.</span></span>  
  
 <span data-ttu-id="46296-109">これに対して、汎用マップは、複数の取引で使用する設計されます。</span><span class="sxs-lookup"><span data-stu-id="46296-109">Generic maps, on the other hand, are designed to be used with multiple trading partners.</span></span> <span data-ttu-id="46296-110">そのため、開発し、特定のビジネス ドキュメントに対して複数のスキーマの維持を代わりに、ビジネス ドキュメントの種類ごとに 1 つのスキーマを作成して、それらを使用して、すべての取引先パートナーと。</span><span class="sxs-lookup"><span data-stu-id="46296-110">Therefore, instead of developing and maintaining multiple schemas for a particular business document, you create one schema for each type of business document, and then use them with all of your trading partners.</span></span> <span data-ttu-id="46296-111">複数の取引先に 1 つのマップを使用するには、時間とリソースが節約できます、これらのマップはカスタマイズされていませんし、すべてのケースのニーズを満たすができない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="46296-111">While using one map with multiple trading partners saves time and resources, these maps are not customized and may not be meet the needs of all cases.</span></span>  
  
 <span data-ttu-id="46296-112">ビジネスの性質に応じて、固有および汎用の両方のマップを作成することが可能性があります。</span><span class="sxs-lookup"><span data-stu-id="46296-112">It is likely that you will create both specific and generic maps, depending on the nature of your business.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46296-113">参照</span><span class="sxs-lookup"><span data-stu-id="46296-113">See Also</span></span>  
 <span data-ttu-id="46296-114">[マップ](../core/maps.md) </span><span class="sxs-lookup"><span data-stu-id="46296-114">[Maps](../core/maps.md) </span></span>  
 [<span data-ttu-id="46296-115">BizTalk マッパーを使用してマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="46296-115">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)