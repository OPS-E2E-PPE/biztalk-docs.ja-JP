---
title: 関数 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0311b7dc-1955-45af-b858-681faccc939b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf7a181f200948335aab0ffa2a06d43d38408afb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977418"
---
# <a name="scientific-functoids"></a><span data-ttu-id="b3526-102">関数 Functoid</span><span class="sxs-lookup"><span data-stu-id="b3526-102">Scientific Functoids</span></span>

## <a name="overview"></a><span data-ttu-id="b3526-103">概要</span><span class="sxs-lookup"><span data-stu-id="b3526-103">Overview</span></span>
<span data-ttu-id="b3526-104">**科学**functoid は、さまざまな標準の三角関数演算、対数演算、および指数演算を実行するために使用します。</span><span class="sxs-lookup"><span data-stu-id="b3526-104">**Scientific** functoids are used to perform a variety of standard trigonometric, logarithmic, and exponential calculations.</span></span>  

 <span data-ttu-id="b3526-105">例外として、**底指定対数**と**X ^ Y** functoid をそれぞれ 2 つの入力パラメーターを取る、**科学的**すべての functoid が 1 つのパラメーターを受け取る。</span><span class="sxs-lookup"><span data-stu-id="b3526-105">With the exception of the **Base-Specified Logarithm** and **X^Y** functoids, which each take two input parameters, the **Scientific** functoids all take a single parameter.</span></span>  

 <span data-ttu-id="b3526-106">4 つの三角関数**科学的**functoid (**アーク タンジェント**、**コサイン**、**サイン**、および**タンジェント**)、関連する入力または出力パラメーターの単位として度ではなく、ラジアンを使用すべて。</span><span class="sxs-lookup"><span data-stu-id="b3526-106">The four trigonometric **Scientific** functoids (**Arc Tangent**, **Cosine**, **Sine**, and **Tangent**) all use radians rather than degrees as the units for their relevant input or output parameters.</span></span> <span data-ttu-id="b3526-107">ラジアンは角度の単位で、2π ラジアンで円になります。</span><span class="sxs-lookup"><span data-stu-id="b3526-107">A radian is a unit of measure of angles, such that there are 2π radians in a circle.</span></span> <span data-ttu-id="b3526-108">つまり、次の式が成立します。</span><span class="sxs-lookup"><span data-stu-id="b3526-108">It follows that:</span></span>  

- <span data-ttu-id="b3526-109">2π ラジアン = 360 度</span><span class="sxs-lookup"><span data-stu-id="b3526-109">2π radians equals 360 degrees</span></span>  

- <span data-ttu-id="b3526-110">1 ラジアン = 180/π 度</span><span class="sxs-lookup"><span data-stu-id="b3526-110">1 radian = 180/π degrees</span></span>  

- <span data-ttu-id="b3526-111">1 度 = π/180 ラジアン</span><span class="sxs-lookup"><span data-stu-id="b3526-111">1 degree = π/180 radians</span></span>  

  <span data-ttu-id="b3526-112">入力または出力インスタンス メッセージには、角度のメジャーの単位として度を使用して、使用する必要があります、**数値演算**functoid は三角関数と組み合わせて**科学的**functoid を正しい結果を実現します。</span><span class="sxs-lookup"><span data-stu-id="b3526-112">If your input or output instance messages use degrees as their unit of measure for angles, you will need to use a **Mathematical** functoid in conjunction with a trigonometric **Scientific** functoid to achieve the correct result.</span></span>  

## <a name="available-functoids"></a><span data-ttu-id="b3526-113">使用可能な functoid</span><span class="sxs-lookup"><span data-stu-id="b3526-113">Available functoids</span></span>  
 <span data-ttu-id="b3526-114">**科学的**functoid には。</span><span class="sxs-lookup"><span data-stu-id="b3526-114">The **Scientific** functoids are:</span></span> 

* <span data-ttu-id="b3526-115">10^n</span><span class="sxs-lookup"><span data-stu-id="b3526-115">10^n</span></span>
* <span data-ttu-id="b3526-116">アーク タンジェント</span><span class="sxs-lookup"><span data-stu-id="b3526-116">Arc Tangent</span></span>
* <span data-ttu-id="b3526-117">底指定対数</span><span class="sxs-lookup"><span data-stu-id="b3526-117">Base-Specified Logarithm</span></span>
* <span data-ttu-id="b3526-118">常用対数</span><span class="sxs-lookup"><span data-stu-id="b3526-118">Common Logarithm</span></span>
* <span data-ttu-id="b3526-119">コサイン</span><span class="sxs-lookup"><span data-stu-id="b3526-119">Cosine</span></span>
* <span data-ttu-id="b3526-120">自然指数関数</span><span class="sxs-lookup"><span data-stu-id="b3526-120">Natural Exponential Function</span></span>
* <span data-ttu-id="b3526-121">自然対数</span><span class="sxs-lookup"><span data-stu-id="b3526-121">Natural Logarithm</span></span>
* <span data-ttu-id="b3526-122">サイン</span><span class="sxs-lookup"><span data-stu-id="b3526-122">Sine</span></span>
* <span data-ttu-id="b3526-123">タンジェント</span><span class="sxs-lookup"><span data-stu-id="b3526-123">Tangent</span></span>
* <span data-ttu-id="b3526-124">X^Y</span><span class="sxs-lookup"><span data-stu-id="b3526-124">X^Y</span></span>

## <a name="see-also"></a><span data-ttu-id="b3526-125">参照</span><span class="sxs-lookup"><span data-stu-id="b3526-125">See Also</span></span>  
- [<span data-ttu-id="b3526-126">マップに基本 Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="b3526-126">How to Add Basic Functoids to a Map</span></span>](../core/how-to-add-basic-functoids-to-a-map.md)   
- <span data-ttu-id="b3526-127">**関数 Functoid のリファレンス** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="b3526-127">**Scientific Functoids Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
