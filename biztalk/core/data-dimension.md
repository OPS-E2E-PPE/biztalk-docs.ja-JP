---
title: データ ディメンション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data dimension [BAM]
- aggregations [BAM], data dimensions
ms.assetid: 07b5e56a-4fd5-4c88-a98a-758e514d0621
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 036491d9f0fdb946c748850b7c25c959854f2098
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353195"
---
# <a name="data-dimension"></a><span data-ttu-id="e6859-102">データ ディメンション</span><span class="sxs-lookup"><span data-stu-id="e6859-102">Data Dimension</span></span>
<span data-ttu-id="e6859-103">行または列で使用する BAM アクティビティ内のテキスト項目の値をデータ ディメンションを定義できます。</span><span class="sxs-lookup"><span data-stu-id="e6859-103">Defining a data dimension allows the value of some text items in the BAM activity to be used on rows or columns.</span></span> <span data-ttu-id="e6859-104">たとえば、次の表を作成する製品の名前のデータ ディメンションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e6859-104">For example a data dimension named Product can be used to create the following table:</span></span>  
  
|<span data-ttu-id="e6859-105">製品</span><span class="sxs-lookup"><span data-stu-id="e6859-105">Product</span></span>|<span data-ttu-id="e6859-106">Count</span><span class="sxs-lookup"><span data-stu-id="e6859-106">Count</span></span>|  
|-------------|-----------|  
|<span data-ttu-id="e6859-107">テニス ラケット</span><span class="sxs-lookup"><span data-stu-id="e6859-107">Tennis racquets</span></span>|<span data-ttu-id="e6859-108">100</span><span class="sxs-lookup"><span data-stu-id="e6859-108">100</span></span>|  
|<span data-ttu-id="e6859-109">サッカー ボール</span><span class="sxs-lookup"><span data-stu-id="e6859-109">Soccer balls</span></span>|<span data-ttu-id="e6859-110">200</span><span class="sxs-lookup"><span data-stu-id="e6859-110">200</span></span>|  
  
 <span data-ttu-id="e6859-111">また、BAM ビュー ウィザードでは、複数のデータ ディメンションを定義できます。</span><span class="sxs-lookup"><span data-stu-id="e6859-111">Also, more than one data dimension can be defined in the BAM view wizard.</span></span> <span data-ttu-id="e6859-112">たとえば、という名前のデータ ディメンションを定義する**場所**レベルが含ま**状態**と**市区町村**次の表を作成するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="e6859-112">For example, defining a data dimension named **Location** with levels for **State** and **City** can be used to create the following table:</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="e6859-113">California</span><span class="sxs-lookup"><span data-stu-id="e6859-113">California</span></span>||<span data-ttu-id="e6859-114">Washington</span><span class="sxs-lookup"><span data-stu-id="e6859-114">Washington</span></span>|  
||<span data-ttu-id="e6859-115">Los Angeles</span><span class="sxs-lookup"><span data-stu-id="e6859-115">Los Angeles</span></span>|<span data-ttu-id="e6859-116">San Francisco</span><span class="sxs-lookup"><span data-stu-id="e6859-116">San Francisco</span></span>|<span data-ttu-id="e6859-117">Seattle</span><span class="sxs-lookup"><span data-stu-id="e6859-117">Seattle</span></span>|  
|<span data-ttu-id="e6859-118">テニス ラケット</span><span class="sxs-lookup"><span data-stu-id="e6859-118">Tennis racquets</span></span>|<span data-ttu-id="e6859-119">50</span><span class="sxs-lookup"><span data-stu-id="e6859-119">50</span></span>|<span data-ttu-id="e6859-120">20</span><span class="sxs-lookup"><span data-stu-id="e6859-120">20</span></span>|<span data-ttu-id="e6859-121">30</span><span class="sxs-lookup"><span data-stu-id="e6859-121">30</span></span>|  
|<span data-ttu-id="e6859-122">サッカー ボール</span><span class="sxs-lookup"><span data-stu-id="e6859-122">Soccer balls</span></span>|<span data-ttu-id="e6859-123">130</span><span class="sxs-lookup"><span data-stu-id="e6859-123">130</span></span>|<span data-ttu-id="e6859-124">50</span><span class="sxs-lookup"><span data-stu-id="e6859-124">50</span></span>|<span data-ttu-id="e6859-125">20</span><span class="sxs-lookup"><span data-stu-id="e6859-125">20</span></span>|  
  
 <span data-ttu-id="e6859-126">この表で、Product ディメンションは、行として使用され、場所ディメンションは列として使用されました。</span><span class="sxs-lookup"><span data-stu-id="e6859-126">In this table, the Product dimension was used as the rows, and the Location dimension was used as the columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6859-127">参照</span><span class="sxs-lookup"><span data-stu-id="e6859-127">See Also</span></span>  
 <span data-ttu-id="e6859-128">[時間ディメンション](../core/time-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="e6859-128">[Time Dimension](../core/time-dimension.md) </span></span>  
 <span data-ttu-id="e6859-129">[進捗ディメンション](../core/progress-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="e6859-129">[Progress Dimension](../core/progress-dimension.md) </span></span>  
 <span data-ttu-id="e6859-130">[数値範囲ディメンション](../core/numeric-range-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="e6859-130">[Numeric Range Dimension](../core/numeric-range-dimension.md) </span></span>  
 [<span data-ttu-id="e6859-131">ディメンションの定義</span><span class="sxs-lookup"><span data-stu-id="e6859-131">Defining Dimensions</span></span>](../core/defining-dimensions.md)