---
title: "アサート Functoid |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e91dac06-f909-4fb2-8c87-828a3dfe2c27
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03237c27e0e35642be197b549c8b0102d9350702
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="assert-functoid"></a><span data-ttu-id="c9c9e-102">アサート Functoid</span><span class="sxs-lookup"><span data-stu-id="c9c9e-102">Assert Functoid</span></span>

## <a name="overview"></a><span data-ttu-id="c9c9e-103">概要</span><span class="sxs-lookup"><span data-stu-id="c9c9e-103">Overview</span></span>
<span data-ttu-id="c9c9e-104">**Assert** functoid か、文字列値を出力するか、ブール値に基づく例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="c9c9e-104">The **Assert** functoid either outputs a string value or throws an exception based on a Boolean value.</span></span> <span data-ttu-id="c9c9e-105">この functoid を 1 つ以上のとを組み合わせる場合、**論理**functoid をマップには、条件に関する仮定を効率的にテストできます。</span><span class="sxs-lookup"><span data-stu-id="c9c9e-105">If you combine this functoid with one or more of the **Logical** functoids, you can effectively test assumptions about conditions in your map.</span></span> <span data-ttu-id="c9c9e-106">たとえば、発注量が特定のしきい値を超えないものと想定するマップがあれば、テストできます発注値を使用して、**より大きい**functoid に接続し、 **Assert**functoid です。</span><span class="sxs-lookup"><span data-stu-id="c9c9e-106">For example, if you have a map that expects purchase order amounts never to exceed a certain threshold, you can test the purchase order value by using the **Greater Than** functoid and then connect it to the **Assert** functoid.</span></span> <span data-ttu-id="c9c9e-107">論理演算 functoid を返す場合**True**、 **Assert** functoid が指定した文字列を使用して例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="c9c9e-107">If the logical functoid returns **True**, the **Assert** functoid will throw an exception using a string you provide.</span></span>  
  
 <span data-ttu-id="c9c9e-108">![アサート Functoid](../core/media/assertfunctoid.gif "AssertFunctoid")</span><span class="sxs-lookup"><span data-stu-id="c9c9e-108">![Assert Functoid](../core/media/assertfunctoid.gif "AssertFunctoid")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9c9e-109">参照</span><span class="sxs-lookup"><span data-stu-id="c9c9e-109">See Also</span></span>  
 <span data-ttu-id="c9c9e-110">**アサート Functoid リファレンス**と**論理演算 Functoid リファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="c9c9e-110">**Assert Functoid Reference** and **Logical Functoids Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>