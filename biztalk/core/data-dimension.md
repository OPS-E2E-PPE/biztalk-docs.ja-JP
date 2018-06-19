---
title: データ ディメンション |Microsoft ドキュメント
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
ms.openlocfilehash: b7138cf31a9cb86a9ba949142129ac5c906754b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238354"
---
# <a name="data-dimension"></a><span data-ttu-id="5d93e-102">データ ディメンション</span><span class="sxs-lookup"><span data-stu-id="5d93e-102">Data Dimension</span></span>
<span data-ttu-id="5d93e-103">行と列に使用する BAM アクティビティ内のテキスト項目の値をデータ ディメンションを定義できます。</span><span class="sxs-lookup"><span data-stu-id="5d93e-103">Defining a data dimension allows the value of some text items in the BAM activity to be used on rows or columns.</span></span> <span data-ttu-id="5d93e-104">たとえば、製品という名前のデータ ディメンションを使用して、次のテーブルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5d93e-104">For example a data dimension named Product can be used to create the following table:</span></span>  
  
|<span data-ttu-id="5d93e-105">Product</span><span class="sxs-lookup"><span data-stu-id="5d93e-105">Product</span></span>|<span data-ttu-id="5d93e-106">Count</span><span class="sxs-lookup"><span data-stu-id="5d93e-106">Count</span></span>|  
|-------------|-----------|  
|<span data-ttu-id="5d93e-107">テニス ラケット</span><span class="sxs-lookup"><span data-stu-id="5d93e-107">Tennis racquets</span></span>|<span data-ttu-id="5d93e-108">100</span><span class="sxs-lookup"><span data-stu-id="5d93e-108">100</span></span>|  
|<span data-ttu-id="5d93e-109">サッカー ボール</span><span class="sxs-lookup"><span data-stu-id="5d93e-109">Soccer balls</span></span>|<span data-ttu-id="5d93e-110">200</span><span class="sxs-lookup"><span data-stu-id="5d93e-110">200</span></span>|  
  
 <span data-ttu-id="5d93e-111">また、BAM ビュー ウィザードで複数のデータ ディメンションを定義できます。</span><span class="sxs-lookup"><span data-stu-id="5d93e-111">Also, more than one data dimension can be defined in the BAM view wizard.</span></span> <span data-ttu-id="5d93e-112">たとえば、という名前のデータ ディメンションを定義する**場所**のレベルを持つ**状態**と**市区町村**次の表の作成に使用できます。</span><span class="sxs-lookup"><span data-stu-id="5d93e-112">For example, defining a data dimension named **Location** with levels for **State** and **City** can be used to create the following table:</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="5d93e-113">California</span><span class="sxs-lookup"><span data-stu-id="5d93e-113">California</span></span>||<span data-ttu-id="5d93e-114">Washington</span><span class="sxs-lookup"><span data-stu-id="5d93e-114">Washington</span></span>|  
||<span data-ttu-id="5d93e-115">Los Angeles</span><span class="sxs-lookup"><span data-stu-id="5d93e-115">Los Angeles</span></span>|<span data-ttu-id="5d93e-116">San Francisco</span><span class="sxs-lookup"><span data-stu-id="5d93e-116">San Francisco</span></span>|<span data-ttu-id="5d93e-117">Seattle</span><span class="sxs-lookup"><span data-stu-id="5d93e-117">Seattle</span></span>|  
|<span data-ttu-id="5d93e-118">テニス ラケット</span><span class="sxs-lookup"><span data-stu-id="5d93e-118">Tennis racquets</span></span>|<span data-ttu-id="5d93e-119">50</span><span class="sxs-lookup"><span data-stu-id="5d93e-119">50</span></span>|<span data-ttu-id="5d93e-120">20</span><span class="sxs-lookup"><span data-stu-id="5d93e-120">20</span></span>|<span data-ttu-id="5d93e-121">30</span><span class="sxs-lookup"><span data-stu-id="5d93e-121">30</span></span>|  
|<span data-ttu-id="5d93e-122">サッカー ボール</span><span class="sxs-lookup"><span data-stu-id="5d93e-122">Soccer balls</span></span>|<span data-ttu-id="5d93e-123">130</span><span class="sxs-lookup"><span data-stu-id="5d93e-123">130</span></span>|<span data-ttu-id="5d93e-124">50</span><span class="sxs-lookup"><span data-stu-id="5d93e-124">50</span></span>|<span data-ttu-id="5d93e-125">20</span><span class="sxs-lookup"><span data-stu-id="5d93e-125">20</span></span>|  
  
 <span data-ttu-id="5d93e-126">このテーブルでは、製品ディメンションは行として使用され、場所ディメンションは列として使用されています。</span><span class="sxs-lookup"><span data-stu-id="5d93e-126">In this table, the Product dimension was used as the rows, and the Location dimension was used as the columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d93e-127">参照</span><span class="sxs-lookup"><span data-stu-id="5d93e-127">See Also</span></span>  
 <span data-ttu-id="5d93e-128">[時間ディメンション](../core/time-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="5d93e-128">[Time Dimension](../core/time-dimension.md) </span></span>  
 <span data-ttu-id="5d93e-129">[進捗ディメンション](../core/progress-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="5d93e-129">[Progress Dimension](../core/progress-dimension.md) </span></span>  
 <span data-ttu-id="5d93e-130">[数値範囲ディメンション](../core/numeric-range-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="5d93e-130">[Numeric Range Dimension](../core/numeric-range-dimension.md) </span></span>  
 [<span data-ttu-id="5d93e-131">ディメンションの定義</span><span class="sxs-lookup"><span data-stu-id="5d93e-131">Defining Dimensions</span></span>](../core/defining-dimensions.md)