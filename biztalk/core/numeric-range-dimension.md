---
title: 数値範囲ディメンション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], Numeric Range dimension
- Numeric Range dimension [BAM]
ms.assetid: a874ce44-b034-498f-ba58-114028dbef2c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0cde21a4cf30dd6f46af226bf056aa0efc398ca5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65263207"
---
# <a name="numeric-range-dimension"></a><span data-ttu-id="60530-102">数値範囲ディメンション</span><span class="sxs-lookup"><span data-stu-id="60530-102">Numeric Range Dimension</span></span>
<span data-ttu-id="60530-103">数値範囲ディメンションは、のフレンドリ名に基づいて集計を分類する範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="60530-103">The numeric range dimension allows aggregations to be categorized based on friendly names of given ranges.</span></span> <span data-ttu-id="60530-104">たとえば、ビジネス アナリストは、発注書の間で 0-100 ドルと、100 ドルを 1,000 ドルと l の間の 1,000 ドルを超える注文の発注書の中規模の小さな範囲と PO サイズをという名前の数値範囲ディメンションを定義できます。</span><span class="sxs-lookup"><span data-stu-id="60530-104">For example, a business analyst can define a numeric range dimension named PO Size with the ranges Small for purchase orders between 0-$100, Medium for purchase orders between $100 to $1,000, and Large for purchase orders exceeding $1,000.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="60530-105">注文の合計が定義した範囲にない場合は、たとえば、注文の合計が 0 未満とし、「範囲外」行が自動的に作成範囲外のデータに合わせて BAM によって。</span><span class="sxs-lookup"><span data-stu-id="60530-105">If a purchase order amount is not in the defined ranges, for example, a purchase order amount is less than 0, and then an "Out of range" row will be automatically created by BAM to accommodate the out-of-range data.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="60530-106">同じデータ エイリアスを参照する 2 つの数値範囲ディメンションを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="60530-106">You cannot create two numeric range dimensions that reference the same data alias.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60530-107">参照</span><span class="sxs-lookup"><span data-stu-id="60530-107">See Also</span></span>  
 <span data-ttu-id="60530-108">[ピボット テーブルを使用する方法](../core/how-to-use-the-pivottable.md) </span><span class="sxs-lookup"><span data-stu-id="60530-108">[How to Use the PivotTable](../core/how-to-use-the-pivottable.md) </span></span>  
 <span data-ttu-id="60530-109">[進捗ディメンション](../core/progress-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="60530-109">[Progress Dimension](../core/progress-dimension.md) </span></span>  
 <span data-ttu-id="60530-110">[データ ディメンション](../core/data-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="60530-110">[Data Dimension](../core/data-dimension.md) </span></span>  
 <span data-ttu-id="60530-111">[時間ディメンション](../core/time-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="60530-111">[Time Dimension](../core/time-dimension.md) </span></span>  
 [<span data-ttu-id="60530-112">ディメンションの定義</span><span class="sxs-lookup"><span data-stu-id="60530-112">Defining Dimensions</span></span>](../core/defining-dimensions.md)