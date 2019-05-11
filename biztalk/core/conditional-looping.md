---
title: 条件付きループ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Looping functoids, conditional
- Equal functoids
- maps, conditional looping
ms.assetid: eb16efb8-b12c-47d6-afc9-579fc85ea59c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a29aa5c1835b37f1b268c1aca9b87cc688c291b9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391620"
---
# <a name="conditional-looping"></a><span data-ttu-id="053cb-102">条件付きループ</span><span class="sxs-lookup"><span data-stu-id="053cb-102">Conditional Looping</span></span>
<span data-ttu-id="053cb-103">条件を追加することができます、**ループ**functoid の出力リンクを**ループ**functoid と**論理**functoid 同じ送信先レコードを送信します。</span><span class="sxs-lookup"><span data-stu-id="053cb-103">You can add conditions to a **Looping** functoid by linking the output of a **Looping** functoid and a **Logical** functoid to the same destination record.</span></span> <span data-ttu-id="053cb-104">論理条件が満たされている場合のみ、送信先レコードが作成されます。</span><span class="sxs-lookup"><span data-stu-id="053cb-104">The destination records are created only when the logical condition is met.</span></span>  
  
## <a name="conditional-looping-map"></a><span data-ttu-id="053cb-105">条件付きループのマップ</span><span class="sxs-lookup"><span data-stu-id="053cb-105">Conditional Looping Map</span></span>  
 <span data-ttu-id="053cb-106">![条件付きループ functoid を示すをマップします。](../core/media/loopingconditionalfunctoid.gif "loopingconditionalfunctoid")</span><span class="sxs-lookup"><span data-stu-id="053cb-106">![Map illustrating conditional looping functoid.](../core/media/loopingconditionalfunctoid.gif "loopingconditionalfunctoid")</span></span>  
  
 <span data-ttu-id="053cb-107">上記の図では、最初**等しい**functoid を比較、**名**フィールド**FoodSurvey** "Wendy wheeler"です。</span><span class="sxs-lookup"><span data-stu-id="053cb-107">In the preceding figure, the first **Equal** functoid compares the **Name** field under **FoodSurvey** to "Wendy Wheeler".</span></span> <span data-ttu-id="053cb-108">2 番目**等しい**functoid を比較、**名前**フィールド**FlowerSurvey** "Kelly focht"です。</span><span class="sxs-lookup"><span data-stu-id="053cb-108">The second **Equal** functoid compares the **Name** field under **FlowerSurvey** to "Kelly Focht".</span></span> <span data-ttu-id="053cb-109">したがって、先の作成、マップ**アドレス**レコードのみ、2 つの名前。</span><span class="sxs-lookup"><span data-stu-id="053cb-109">Thus, the map creates the destination **Address** records only for the two names.</span></span> <span data-ttu-id="053cb-110">サンプル データを使用して、**ループ**functoid 例では、出力インスタンス メッセージは次のようです。</span><span class="sxs-lookup"><span data-stu-id="053cb-110">Using the sample data from the **Looping** functoid example, the output instance message would appear as follows.</span></span>  
  
```  
<ns0:MasterAddresses xmlns:ns0="http://ConditionalLoop.MasterAddresses">  
    <Address Name="Wendy Wheeler" Street="7890 Broadway" City="Columbus" State="OH" PostalCode="46290">  
    <Address Name="Kelly Focht" Street="456 1st Ave" City="Miami" State="FL" PostalCode="81406">  
</ns0:MasterAddresses>  
```  
  
## <a name="see-also"></a><span data-ttu-id="053cb-111">参照</span><span class="sxs-lookup"><span data-stu-id="053cb-111">See Also</span></span>  
 <span data-ttu-id="053cb-112">[マップにループ Functoid を追加する方法](../core/how-to-add-looping-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="053cb-112">[How to Add Looping Functoids to a Map](../core/how-to-add-looping-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="053cb-113">[高度な Functoid](../core/advanced-functoids.md) </span><span class="sxs-lookup"><span data-stu-id="053cb-113">[Advanced Functoids](../core/advanced-functoids.md) </span></span>  
 <span data-ttu-id="053cb-114">[インデックス Functoid](../core/index-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="053cb-114">[Index Functoid](../core/index-functoid.md) </span></span>  
 <span data-ttu-id="053cb-115">[繰り返し Functoid](../core/iteration-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="053cb-115">[Iteration Functoid](../core/iteration-functoid.md) </span></span>  
 <span data-ttu-id="053cb-116">[ループ Functoid](../core/looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="053cb-116">[Looping Functoid](../core/looping-functoid.md) </span></span>  
 [<span data-ttu-id="053cb-117">レコード カウント Functoid</span><span class="sxs-lookup"><span data-stu-id="053cb-117">Record Count Functoid</span></span>](../core/record-count-functoid.md)