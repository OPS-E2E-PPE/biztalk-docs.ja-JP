---
title: 時間ディメンション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Time dimension [BAM]
- aggregations [BAM], Time dimension
ms.assetid: 8f83b758-09a1-4efb-ae0e-32753f56c4e4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ac4e3d64b2bfee949ca0adca06dc79c9b944192
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399469"
---
# <a name="time-dimension"></a><span data-ttu-id="64f1f-102">時間ディメンション</span><span class="sxs-lookup"><span data-stu-id="64f1f-102">Time Dimension</span></span>
<span data-ttu-id="64f1f-103">時間ディメンションは、集計を時間を基準として作成できます。</span><span class="sxs-lookup"><span data-stu-id="64f1f-103">The time dimension allows aggregations to be created with respect to time.</span></span> <span data-ttu-id="64f1f-104">たとえば、次の表を作成する時間ディメンションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="64f1f-104">For example a time dimension can be used to create the following table:</span></span>  
  
|<span data-ttu-id="64f1f-105">年</span><span class="sxs-lookup"><span data-stu-id="64f1f-105">Year</span></span>|<span data-ttu-id="64f1f-106">Month</span><span class="sxs-lookup"><span data-stu-id="64f1f-106">Month</span></span>|<span data-ttu-id="64f1f-107">Count</span><span class="sxs-lookup"><span data-stu-id="64f1f-107">Count</span></span>|  
|----------|-----------|-----------|  
|<span data-ttu-id="64f1f-108">2003</span><span class="sxs-lookup"><span data-stu-id="64f1f-108">2003</span></span>|<span data-ttu-id="64f1f-109">January</span><span class="sxs-lookup"><span data-stu-id="64f1f-109">January</span></span>|<span data-ttu-id="64f1f-110">120</span><span class="sxs-lookup"><span data-stu-id="64f1f-110">120</span></span>|  
||<span data-ttu-id="64f1f-111">February</span><span class="sxs-lookup"><span data-stu-id="64f1f-111">February</span></span>|<span data-ttu-id="64f1f-112">230</span><span class="sxs-lookup"><span data-stu-id="64f1f-112">230</span></span>|  
||<span data-ttu-id="64f1f-113">March</span><span class="sxs-lookup"><span data-stu-id="64f1f-113">March</span></span>|<span data-ttu-id="64f1f-114">350</span><span class="sxs-lookup"><span data-stu-id="64f1f-114">350</span></span>|  
||<span data-ttu-id="64f1f-115">April</span><span class="sxs-lookup"><span data-stu-id="64f1f-115">April</span></span>|<span data-ttu-id="64f1f-116">280</span><span class="sxs-lookup"><span data-stu-id="64f1f-116">280</span></span>|  
  
 <span data-ttu-id="64f1f-117">時間ディメンションは、他のディメンションと組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="64f1f-117">The time dimension can be combined with any other dimension.</span></span> <span data-ttu-id="64f1f-118">たとえば、次の表を作成するのに行と列のデータ ディメンションで時間ディメンションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="64f1f-118">For example, you can use the time dimension on rows and the data dimension on columns to create the following table:</span></span>  
  
|||<span data-ttu-id="64f1f-119">テニス ラケット</span><span class="sxs-lookup"><span data-stu-id="64f1f-119">Tennis racquets</span></span>|<span data-ttu-id="64f1f-120">サッカー ボール</span><span class="sxs-lookup"><span data-stu-id="64f1f-120">Soccer balls</span></span>|  
|------|------|---------------------|------------------|  
||<span data-ttu-id="64f1f-121">January</span><span class="sxs-lookup"><span data-stu-id="64f1f-121">January</span></span>|<span data-ttu-id="64f1f-122">50</span><span class="sxs-lookup"><span data-stu-id="64f1f-122">50</span></span>|<span data-ttu-id="64f1f-123">70</span><span class="sxs-lookup"><span data-stu-id="64f1f-123">70</span></span>|  
||<span data-ttu-id="64f1f-124">February</span><span class="sxs-lookup"><span data-stu-id="64f1f-124">February</span></span>|<span data-ttu-id="64f1f-125">120</span><span class="sxs-lookup"><span data-stu-id="64f1f-125">120</span></span>|<span data-ttu-id="64f1f-126">110</span><span class="sxs-lookup"><span data-stu-id="64f1f-126">110</span></span>|  
||<span data-ttu-id="64f1f-127">March</span><span class="sxs-lookup"><span data-stu-id="64f1f-127">March</span></span>|<span data-ttu-id="64f1f-128">300</span><span class="sxs-lookup"><span data-stu-id="64f1f-128">300</span></span>|<span data-ttu-id="64f1f-129">50</span><span class="sxs-lookup"><span data-stu-id="64f1f-129">50</span></span>|  
||<span data-ttu-id="64f1f-130">April</span><span class="sxs-lookup"><span data-stu-id="64f1f-130">April</span></span>|<span data-ttu-id="64f1f-131">220</span><span class="sxs-lookup"><span data-stu-id="64f1f-131">220</span></span>|<span data-ttu-id="64f1f-132">60</span><span class="sxs-lookup"><span data-stu-id="64f1f-132">60</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="64f1f-133">参照</span><span class="sxs-lookup"><span data-stu-id="64f1f-133">See Also</span></span>  
 <span data-ttu-id="64f1f-134">[数値範囲ディメンション](../core/numeric-range-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="64f1f-134">[Numeric Range Dimension](../core/numeric-range-dimension.md) </span></span>  
 <span data-ttu-id="64f1f-135">[進捗ディメンション](../core/progress-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="64f1f-135">[Progress Dimension](../core/progress-dimension.md) </span></span>  
 <span data-ttu-id="64f1f-136">[データ ディメンション](../core/data-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="64f1f-136">[Data Dimension](../core/data-dimension.md) </span></span>  
 [<span data-ttu-id="64f1f-137">ディメンションの定義</span><span class="sxs-lookup"><span data-stu-id="64f1f-137">Defining Dimensions</span></span>](../core/defining-dimensions.md)