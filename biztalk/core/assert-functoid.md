---
title: アサート Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e91dac06-f909-4fb2-8c87-828a3dfe2c27
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e3f14c05d1d4fd6538c126659c27cdb8b25fe08
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530632"
---
# <a name="assert-functoid"></a><span data-ttu-id="fc238-102">アサート Functoid</span><span class="sxs-lookup"><span data-stu-id="fc238-102">Assert Functoid</span></span>

## <a name="overview"></a><span data-ttu-id="fc238-103">概要</span><span class="sxs-lookup"><span data-stu-id="fc238-103">Overview</span></span>
<span data-ttu-id="fc238-104">**Assert** functoid が文字列値を出力またはブール値に基づいて例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="fc238-104">The **Assert** functoid either outputs a string value or throws an exception based on a Boolean value.</span></span> <span data-ttu-id="fc238-105">この functoid を組み合わせた 1 つまたは複数の場合、**論理**functoid をマップには、条件に関する仮定を効果的にテストできます。</span><span class="sxs-lookup"><span data-stu-id="fc238-105">If you combine this functoid with one or more of the **Logical** functoids, you can effectively test assumptions about conditions in your map.</span></span> <span data-ttu-id="fc238-106">たとえば、特定のしきい値を超えない発注書の金額を必要があるマップがあれば、テストできます発注値を使用して、**より大きい**functoid に接続し、 **Assert**functoid。</span><span class="sxs-lookup"><span data-stu-id="fc238-106">For example, if you have a map that expects purchase order amounts never to exceed a certain threshold, you can test the purchase order value by using the **Greater Than** functoid and then connect it to the **Assert** functoid.</span></span> <span data-ttu-id="fc238-107">論理演算 functoid で返された場合**True**、 **Assert** functoid では、指定した文字列を使用して例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="fc238-107">If the logical functoid returns **True**, the **Assert** functoid will throw an exception using a string you provide.</span></span>  
  
 <span data-ttu-id="fc238-108">![アサート Functoid](../core/media/assertfunctoid.gif "AssertFunctoid")</span><span class="sxs-lookup"><span data-stu-id="fc238-108">![Assert Functoid](../core/media/assertfunctoid.gif "AssertFunctoid")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc238-109">参照</span><span class="sxs-lookup"><span data-stu-id="fc238-109">See Also</span></span>  
 <span data-ttu-id="fc238-110">**アサート Functoid リファレンス**と**論理演算 Functoid のリファレンス** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="fc238-110">**Assert Functoid Reference** and **Logical Functoids Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>