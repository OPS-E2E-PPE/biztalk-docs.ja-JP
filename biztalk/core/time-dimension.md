---
title: "時間ディメンション |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Time dimension [BAM]
- aggregations [BAM], Time dimension
ms.assetid: 8f83b758-09a1-4efb-ae0e-32753f56c4e4
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 418afdc5b7507aba9a564628341c10495b2a740a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="time-dimension"></a><span data-ttu-id="fa578-102">時間ディメンション</span><span class="sxs-lookup"><span data-stu-id="fa578-102">Time Dimension</span></span>
<span data-ttu-id="fa578-103">時間ディメンションを使用すると、時間を基準として集計を作成できます。</span><span class="sxs-lookup"><span data-stu-id="fa578-103">The time dimension allows aggregations to be created with respect to time.</span></span> <span data-ttu-id="fa578-104">たとえば、時間ディメンションを使用して、次のテーブルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="fa578-104">For example a time dimension can be used to create the following table:</span></span>  
  
|<span data-ttu-id="fa578-105">年</span><span class="sxs-lookup"><span data-stu-id="fa578-105">Year</span></span>|<span data-ttu-id="fa578-106">Month</span><span class="sxs-lookup"><span data-stu-id="fa578-106">Month</span></span>|<span data-ttu-id="fa578-107">Count</span><span class="sxs-lookup"><span data-stu-id="fa578-107">Count</span></span>|  
|----------|-----------|-----------|  
|<span data-ttu-id="fa578-108">2003</span><span class="sxs-lookup"><span data-stu-id="fa578-108">2003</span></span>|<span data-ttu-id="fa578-109">January</span><span class="sxs-lookup"><span data-stu-id="fa578-109">January</span></span>|<span data-ttu-id="fa578-110">120</span><span class="sxs-lookup"><span data-stu-id="fa578-110">120</span></span>|  
||<span data-ttu-id="fa578-111">February</span><span class="sxs-lookup"><span data-stu-id="fa578-111">February</span></span>|<span data-ttu-id="fa578-112">230</span><span class="sxs-lookup"><span data-stu-id="fa578-112">230</span></span>|  
||<span data-ttu-id="fa578-113">March</span><span class="sxs-lookup"><span data-stu-id="fa578-113">March</span></span>|<span data-ttu-id="fa578-114">350</span><span class="sxs-lookup"><span data-stu-id="fa578-114">350</span></span>|  
||<span data-ttu-id="fa578-115">April</span><span class="sxs-lookup"><span data-stu-id="fa578-115">April</span></span>|<span data-ttu-id="fa578-116">280</span><span class="sxs-lookup"><span data-stu-id="fa578-116">280</span></span>|  
  
 <span data-ttu-id="fa578-117">時間ディメンションは、他のディメンションと組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="fa578-117">The time dimension can be combined with any other dimension.</span></span> <span data-ttu-id="fa578-118">たとえば、行に時間ディメンションを使用し、列にデータ ディメンションを使用して、次のテーブルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="fa578-118">For example, you can use the time dimension on rows and the data dimension on columns to create the following table:</span></span>  
  
|||<span data-ttu-id="fa578-119">テニス ラケット</span><span class="sxs-lookup"><span data-stu-id="fa578-119">Tennis racquets</span></span>|<span data-ttu-id="fa578-120">サッカー ボール</span><span class="sxs-lookup"><span data-stu-id="fa578-120">Soccer balls</span></span>|  
|------|------|---------------------|------------------|  
||<span data-ttu-id="fa578-121">January</span><span class="sxs-lookup"><span data-stu-id="fa578-121">January</span></span>|<span data-ttu-id="fa578-122">50</span><span class="sxs-lookup"><span data-stu-id="fa578-122">50</span></span>|<span data-ttu-id="fa578-123">70</span><span class="sxs-lookup"><span data-stu-id="fa578-123">70</span></span>|  
||<span data-ttu-id="fa578-124">February</span><span class="sxs-lookup"><span data-stu-id="fa578-124">February</span></span>|<span data-ttu-id="fa578-125">120</span><span class="sxs-lookup"><span data-stu-id="fa578-125">120</span></span>|<span data-ttu-id="fa578-126">110</span><span class="sxs-lookup"><span data-stu-id="fa578-126">110</span></span>|  
||<span data-ttu-id="fa578-127">March</span><span class="sxs-lookup"><span data-stu-id="fa578-127">March</span></span>|<span data-ttu-id="fa578-128">300</span><span class="sxs-lookup"><span data-stu-id="fa578-128">300</span></span>|<span data-ttu-id="fa578-129">50</span><span class="sxs-lookup"><span data-stu-id="fa578-129">50</span></span>|  
||<span data-ttu-id="fa578-130">April</span><span class="sxs-lookup"><span data-stu-id="fa578-130">April</span></span>|<span data-ttu-id="fa578-131">220</span><span class="sxs-lookup"><span data-stu-id="fa578-131">220</span></span>|<span data-ttu-id="fa578-132">60</span><span class="sxs-lookup"><span data-stu-id="fa578-132">60</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fa578-133">参照</span><span class="sxs-lookup"><span data-stu-id="fa578-133">See Also</span></span>  
 <span data-ttu-id="fa578-134">[数値範囲ディメンション](../core/numeric-range-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="fa578-134">[Numeric Range Dimension](../core/numeric-range-dimension.md) </span></span>  
 <span data-ttu-id="fa578-135">[進捗ディメンション](../core/progress-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="fa578-135">[Progress Dimension](../core/progress-dimension.md) </span></span>  
 <span data-ttu-id="fa578-136">[データ ディメンション](../core/data-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="fa578-136">[Data Dimension](../core/data-dimension.md) </span></span>  
 [<span data-ttu-id="fa578-137">ディメンションの定義</span><span class="sxs-lookup"><span data-stu-id="fa578-137">Defining Dimensions</span></span>](../core/defining-dimensions.md)