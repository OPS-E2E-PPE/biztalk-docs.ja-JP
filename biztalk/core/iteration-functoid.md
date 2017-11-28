---
title: "繰り返し Functoid |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Iteration functoids
- Greater Than or Equal To functoids
- And functoids
- Less Than or Equal To functoids
ms.assetid: 24d8911d-2282-4b07-910c-eb2e846dc1f9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a491b8829f23296e77ba5a89d12985e8ccd32783
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="iteration-functoid"></a><span data-ttu-id="11892-102">繰り返し Functoid</span><span class="sxs-lookup"><span data-stu-id="11892-102">Iteration Functoid</span></span>
<span data-ttu-id="11892-103">**イテレーション**ループの現在のレコードのインデックス構造体の最初のレコードでは、2 番目のレコードでは、2 の場合は 1 から開始され、functoid の出力。</span><span class="sxs-lookup"><span data-stu-id="11892-103">The **Iteration** functoid outputs the index of the current record in a looping structure, beginning at 1 for the first record, 2 for the second record, and so on.</span></span>  
  
 <span data-ttu-id="11892-104">次に示します、**イテレーション**functoid と組み合わせて使用、**より大きいまたは等しい**functoid、**以下に**functoid、および**と**の該当するショートカットを作成する functoid、**の**ループします。</span><span class="sxs-lookup"><span data-stu-id="11892-104">The following figure shows an **Iteration** functoid combined with a **Greater Than or Equal To** functoid, a **Less Than or Equal To** functoid, and an **And** functoid to create the equivalent of a **For** loop.</span></span>  
  
 <span data-ttu-id="11892-105">![繰り返し functoid の使用方法を示すマップ](../core/media/iterationfunctoid.gif "iterationfunctoid")</span><span class="sxs-lookup"><span data-stu-id="11892-105">![Map illustrating the use of the iteration functoid](../core/media/iterationfunctoid.gif "iterationfunctoid")</span></span>  
<span data-ttu-id="11892-106">繰り返し Functoid のマップ</span><span class="sxs-lookup"><span data-stu-id="11892-106">Iteration Functoid Map</span></span>  
  
 <span data-ttu-id="11892-107">あると想定、**より大きいまたは等しい**functoid またはテストのより大きい値を 2 に等しいかどうかと、**以下に**functoid をテスト 4 小さい値です。</span><span class="sxs-lookup"><span data-stu-id="11892-107">Assume that the **Greater Than or Equal To** functoid tests for values greater than or equal to 2, and the **Less Than or Equal To** functoid tests for values less than or equal to 4.</span></span> <span data-ttu-id="11892-108">その場合は、**と**functoid が返されます**true** 2、3、および 4 のレコードに対してのみです。</span><span class="sxs-lookup"><span data-stu-id="11892-108">In that case, the **And** functoid will return **true** only for records 2, 3, and 4.</span></span> <span data-ttu-id="11892-109">したがって、出力インスタンスには 2、3、および 4 つの入力インスタンス メッセージを記録します。</span><span class="sxs-lookup"><span data-stu-id="11892-109">Thus, the output instance will contain records two, three, and four of the input instance message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11892-110">参照</span><span class="sxs-lookup"><span data-stu-id="11892-110">See Also</span></span>  
 <span data-ttu-id="11892-111">[繰り返し Functoid をマップに追加する方法](../core/how-to-add-iteration-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="11892-111">[How to Add Iteration Functoids to a Map](../core/how-to-add-iteration-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="11892-112">[高度な Functoid](../core/advanced-functoids.md) </span><span class="sxs-lookup"><span data-stu-id="11892-112">[Advanced Functoids](../core/advanced-functoids.md) </span></span>  
 <span data-ttu-id="11892-113">[インデックス Functoid](../core/index-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="11892-113">[Index Functoid](../core/index-functoid.md) </span></span>  
 <span data-ttu-id="11892-114">[ループ Functoid](../core/looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="11892-114">[Looping Functoid](../core/looping-functoid.md) </span></span>  
 [<span data-ttu-id="11892-115">レコード カウント Functoid</span><span class="sxs-lookup"><span data-stu-id="11892-115">Record Count Functoid</span></span>](../core/record-count-functoid.md)