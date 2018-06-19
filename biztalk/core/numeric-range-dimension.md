---
title: 数値範囲ディメンション |Microsoft ドキュメント
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
ms.openlocfilehash: 2fb6d4c21e0a207cfeec3e592569ca0f48f3badf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263402"
---
# <a name="numeric-range-dimension"></a><span data-ttu-id="c2363-102">数値範囲ディメンション</span><span class="sxs-lookup"><span data-stu-id="c2363-102">Numeric Range Dimension</span></span>
<span data-ttu-id="c2363-103">数値範囲ディメンションを使用すると、特定の数値範囲のフレンドリ名に基づいて集計を分類できます。</span><span class="sxs-lookup"><span data-stu-id="c2363-103">The numeric range dimension allows aggregations to be categorized based on friendly names of given ranges.</span></span> <span data-ttu-id="c2363-104">たとえば、ビジネス アナリストは "PO サイズ" という名前の数値範囲ディメンションを定義し、0 ～ 100 ドルの注文には "小"、100 ドルを超え 1,000 ドル以下の注文には "中"、1,000 ドルを超える注文には "大" というように範囲を設定できます。</span><span class="sxs-lookup"><span data-stu-id="c2363-104">For example, a business analyst can define a numeric range dimension named PO Size with the ranges Small for purchase orders between 0-$100, Medium for purchase orders between $100 to $1,000, and Large for purchase orders exceeding $1,000.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c2363-105">注文額が定義した範囲内にない場合、たとえば 0 ドル未満である場合は、BAM によって "範囲外" という列が自動的に作成され、範囲外のデータはここに追加されます。</span><span class="sxs-lookup"><span data-stu-id="c2363-105">If a purchase order amount is not in the defined ranges, for example, a purchase order amount is less than 0, and then an "Out of range" row will be automatically created by BAM to accommodate the out-of-range data.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c2363-106">同じデータ エイリアスを参照する複数の数値範囲ディメンションは作成できません。</span><span class="sxs-lookup"><span data-stu-id="c2363-106">You cannot create two numeric range dimensions that reference the same data alias.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2363-107">参照</span><span class="sxs-lookup"><span data-stu-id="c2363-107">See Also</span></span>  
 <span data-ttu-id="c2363-108">[ピボット テーブルを使用する方法](../core/how-to-use-the-pivottable.md) </span><span class="sxs-lookup"><span data-stu-id="c2363-108">[How to Use the PivotTable](../core/how-to-use-the-pivottable.md) </span></span>  
 <span data-ttu-id="c2363-109">[進捗ディメンション](../core/progress-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="c2363-109">[Progress Dimension](../core/progress-dimension.md) </span></span>  
 <span data-ttu-id="c2363-110">[データ ディメンション](../core/data-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="c2363-110">[Data Dimension](../core/data-dimension.md) </span></span>  
 <span data-ttu-id="c2363-111">[時間ディメンション](../core/time-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="c2363-111">[Time Dimension](../core/time-dimension.md) </span></span>  
 [<span data-ttu-id="c2363-112">ディメンションの定義</span><span class="sxs-lookup"><span data-stu-id="c2363-112">Defining Dimensions</span></span>](../core/defining-dimensions.md)