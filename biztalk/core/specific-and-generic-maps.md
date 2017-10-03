---
title: "専用マップと汎用マップ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maps, specific
- maps, generic
ms.assetid: ee26dd13-affb-47c5-961a-f2377129de22
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6ad84e23c3981730ee4cf7655a42d87c46158e3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="specific-and-generic-maps"></a><span data-ttu-id="7edde-102">専用マップと汎用マップ</span><span class="sxs-lookup"><span data-stu-id="7edde-102">Specific and Generic Maps</span></span>
<span data-ttu-id="7edde-103">データを変換するマップを作成するときは、いずれかを作成、*特定*または*ジェネリック*マップします。</span><span class="sxs-lookup"><span data-stu-id="7edde-103">When you create a map that transforms data, you can create either a *specific* or a *generic* map.</span></span>  
  
 <span data-ttu-id="7edde-104">専用マップを使用すると、特定の取引先の要件を満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="7edde-104">You use a specific map to meet the needs of a particular trading partner.</span></span> <span data-ttu-id="7edde-105">取引先との間に非常に特殊なビジネスの要件 (または契約) がある場合には、専用マップを使用します。</span><span class="sxs-lookup"><span data-stu-id="7edde-105">Use a specific map when you have very specific business needs or business agreements with your trading partner.</span></span> <span data-ttu-id="7edde-106">専用マップの利点は、カスタマイズして、特定の取引先とのビジネス関数の要件を満たせることです。</span><span class="sxs-lookup"><span data-stu-id="7edde-106">The advantage of a specific map is that it is customized to meet the needs of the business functions you have with specific trading partners.</span></span> <span data-ttu-id="7edde-107">専用マップの欠点は、複数の取引先に使用できないことです。</span><span class="sxs-lookup"><span data-stu-id="7edde-107">The disadvantage of a specific map is that it cannot be used with multiple trading partners.</span></span> <span data-ttu-id="7edde-108">取引先の数と、取引先と交換されるさまざまなメッセージの種類の数とを乗算した数のマップが必要である場合、関連するすべてのマップを管理するために、十分な時間とリソースを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7edde-108">If you multiply the number of trading partners by the number of different message types exchanged with those trading partners, you must allocate enough time and resources to manage all of the associated maps.</span></span>  
  
 <span data-ttu-id="7edde-109">一方、汎用マップは、複数の取引先に使用するために設計されています。</span><span class="sxs-lookup"><span data-stu-id="7edde-109">Generic maps, on the other hand, are designed to be used with multiple trading partners.</span></span> <span data-ttu-id="7edde-110">このため、特定のビジネス ドキュメントに対して複数のスキーマの開発や管理を行う代わりに、ビジネス ドキュメントの種類ごとに 1 つのスキーマを作成し、作成したスキーマをすべての取引先に対して使用します。</span><span class="sxs-lookup"><span data-stu-id="7edde-110">Therefore, instead of developing and maintaining multiple schemas for a particular business document, you create one schema for each type of business document, and then use them with all of your trading partners.</span></span> <span data-ttu-id="7edde-111">複数の取引先に対して 1 つのマップを使用すると、時間とリソースが節約されます。ただし、このようなマップは、カスタマイズできないので、すべてのケースのニーズを満たせない場合があります。</span><span class="sxs-lookup"><span data-stu-id="7edde-111">While using one map with multiple trading partners saves time and resources, these maps are not customized and may not be meet the needs of all cases.</span></span>  
  
 <span data-ttu-id="7edde-112">業務の種類にもよりますが、専用マップと汎用マップの両方を作成する場合がほとんどです。</span><span class="sxs-lookup"><span data-stu-id="7edde-112">It is likely that you will create both specific and generic maps, depending on the nature of your business.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7edde-113">参照</span><span class="sxs-lookup"><span data-stu-id="7edde-113">See Also</span></span>  
 <span data-ttu-id="7edde-114">[マップ](../core/maps.md) </span><span class="sxs-lookup"><span data-stu-id="7edde-114">[Maps](../core/maps.md) </span></span>  
 [<span data-ttu-id="7edde-115">BizTalk マッパーを使用してマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="7edde-115">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)