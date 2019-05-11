---
title: 繰り返し Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Iteration functoids
- Greater Than or Equal To functoids
- And functoids
- Less Than or Equal To functoids
ms.assetid: 24d8911d-2282-4b07-910c-eb2e846dc1f9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4074e5555a327ab18e1991727d88011b395ae8e7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380683"
---
# <a name="iteration-functoid"></a><span data-ttu-id="0a11e-102">繰り返し Functoid</span><span class="sxs-lookup"><span data-stu-id="0a11e-102">Iteration Functoid</span></span>
<span data-ttu-id="0a11e-103">**イテレーション**functoid の出力、ループの現在のレコードのインデックスが構造体の最初のレコードでは、2、2 つ目のレコードを 1 から始まる具合です。</span><span class="sxs-lookup"><span data-stu-id="0a11e-103">The **Iteration** functoid outputs the index of the current record in a looping structure, beginning at 1 for the first record, 2 for the second record, and so on.</span></span>  
  
 <span data-ttu-id="0a11e-104">次に示します、**イテレーション**functoid が組み合わさ、**より大きいまたは等しい**functoid、**に等しいまたはそれよりも小さい**functoid、および**と** functoid を作成するのと同じ、**の**ループします。</span><span class="sxs-lookup"><span data-stu-id="0a11e-104">The following figure shows an **Iteration** functoid combined with a **Greater Than or Equal To** functoid, a **Less Than or Equal To** functoid, and an **And** functoid to create the equivalent of a **For** loop.</span></span>  
  
 <span data-ttu-id="0a11e-105">![繰り返し functoid の使用方法を示すマップ](../core/media/iterationfunctoid.gif "iterationfunctoid")</span><span class="sxs-lookup"><span data-stu-id="0a11e-105">![Map illustrating the use of the iteration functoid](../core/media/iterationfunctoid.gif "iterationfunctoid")</span></span>  
<span data-ttu-id="0a11e-106">繰り返し Functoid のマップ</span><span class="sxs-lookup"><span data-stu-id="0a11e-106">Iteration Functoid Map</span></span>  
  
 <span data-ttu-id="0a11e-107">前提としています、**より大きいまたは等しい**より大きい値または 2 に等しいのテストの functoid と**に等しいまたはそれよりも小さい**functoid をテスト 4 小さい値です。</span><span class="sxs-lookup"><span data-stu-id="0a11e-107">Assume that the **Greater Than or Equal To** functoid tests for values greater than or equal to 2, and the **Less Than or Equal To** functoid tests for values less than or equal to 4.</span></span> <span data-ttu-id="0a11e-108">その場合は、**と**functoid が返されます**true**レコード 2、3、および 4 に対してのみです。</span><span class="sxs-lookup"><span data-stu-id="0a11e-108">In that case, the **And** functoid will return **true** only for records 2, 3, and 4.</span></span> <span data-ttu-id="0a11e-109">したがって、出力インスタンスには 2 つ、3、および 4 つの入力インスタンス メッセージを記録します。</span><span class="sxs-lookup"><span data-stu-id="0a11e-109">Thus, the output instance will contain records two, three, and four of the input instance message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a11e-110">参照</span><span class="sxs-lookup"><span data-stu-id="0a11e-110">See Also</span></span>  
 <span data-ttu-id="0a11e-111">[マップに繰り返し Functoid を追加する方法](../core/how-to-add-iteration-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="0a11e-111">[How to Add Iteration Functoids to a Map](../core/how-to-add-iteration-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="0a11e-112">[高度な Functoid](../core/advanced-functoids.md) </span><span class="sxs-lookup"><span data-stu-id="0a11e-112">[Advanced Functoids](../core/advanced-functoids.md) </span></span>  
 <span data-ttu-id="0a11e-113">[インデックス Functoid](../core/index-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="0a11e-113">[Index Functoid](../core/index-functoid.md) </span></span>  
 <span data-ttu-id="0a11e-114">[ループ Functoid](../core/looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="0a11e-114">[Looping Functoid](../core/looping-functoid.md) </span></span>  
 [<span data-ttu-id="0a11e-115">レコード カウント Functoid</span><span class="sxs-lookup"><span data-stu-id="0a11e-115">Record Count Functoid</span></span>](../core/record-count-functoid.md)