---
title: "数値演算 Functoid |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 244fa926-a086-4398-a677-9c322e9024b2
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 232098f27578e75bb925be47a202b07b6487d65d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="mathematical-functoids"></a><span data-ttu-id="093b3-102">数値演算 Functoid</span><span class="sxs-lookup"><span data-stu-id="093b3-102">Mathematical Functoids</span></span>

## <a name="overview"></a><span data-ttu-id="093b3-103">概要</span><span class="sxs-lookup"><span data-stu-id="093b3-103">Overview</span></span>
<span data-ttu-id="093b3-104">**数学**functoid は、さまざまな基本的な算術演算を実行するために使用します。</span><span class="sxs-lookup"><span data-stu-id="093b3-104">**Mathematical** functoids are used to perform a variety of basic mathematical operations.</span></span>  
  
 <span data-ttu-id="093b3-105">入力パラメーターの数、**数値演算**functoid、functoid から functoid が異なるし、これらの functoid が多数の入力を受け入れるよう、適切な場所です。</span><span class="sxs-lookup"><span data-stu-id="093b3-105">The number of input parameters to the **Mathematical** functoids varies from functoid to functoid, and where reasonable, these functoids accept large numbers of inputs.</span></span> <span data-ttu-id="093b3-106">たとえば、**除算**functoid には、中に 2 つの入力パラメーター (被除数と除数) が必要です、**加算**functoid を受け入れると 100 の 2 つの入力パラメーターの間で結果として得られる、合計値。</span><span class="sxs-lookup"><span data-stu-id="093b3-106">For example, the **Division** functoid requires exactly two input parameters (the dividend and the divisor), while the **Addition** functoid accepts between 2 and 100 input parameters, resulting in their sum.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="093b3-107">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 、.NET Framework の一部で生成される結果の基になる機能を使用して、**数値演算**以前のバージョンの BizTalk Server の同等な functoid から functoid が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="093b3-107">Because Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses the underlying functionality of the .NET Framework, the results produced by some of the **Mathematical** functoids may vary from the equivalent functoids in previous versions of BizTalk Server.</span></span> <span data-ttu-id="093b3-108">マップを十分にテストして、期待どおりの結果が得られることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="093b3-108">Test your maps thoroughly to be sure you are getting the results you expect.</span></span>  

## <a name="functoids-list"></a><span data-ttu-id="093b3-109">Functoid の一覧</span><span class="sxs-lookup"><span data-stu-id="093b3-109">Functoids list</span></span>  
 <span data-ttu-id="093b3-110">**数値演算**functoid には。</span><span class="sxs-lookup"><span data-stu-id="093b3-110">The **Mathematical** functoids are:</span></span> 

* <span data-ttu-id="093b3-111">絶対値算出</span><span class="sxs-lookup"><span data-stu-id="093b3-111">Absolute Value</span></span>
* <span data-ttu-id="093b3-112">追加</span><span class="sxs-lookup"><span data-stu-id="093b3-112">Addition</span></span>
* <span data-ttu-id="093b3-113">除算</span><span class="sxs-lookup"><span data-stu-id="093b3-113">Division</span></span>
* <span data-ttu-id="093b3-114">Integer</span><span class="sxs-lookup"><span data-stu-id="093b3-114">Integer</span></span>
* <span data-ttu-id="093b3-115">最大値算出</span><span class="sxs-lookup"><span data-stu-id="093b3-115">Maximum Value</span></span>
* <span data-ttu-id="093b3-116">最小値算出</span><span class="sxs-lookup"><span data-stu-id="093b3-116">Minimum Value</span></span>
* <span data-ttu-id="093b3-117">剰余</span><span class="sxs-lookup"><span data-stu-id="093b3-117">Modulo</span></span>
* <span data-ttu-id="093b3-118">乗算</span><span class="sxs-lookup"><span data-stu-id="093b3-118">Multiplication</span></span>
* <span data-ttu-id="093b3-119">四捨五入</span><span class="sxs-lookup"><span data-stu-id="093b3-119">Round</span></span>
* <span data-ttu-id="093b3-120">平方根算出</span><span class="sxs-lookup"><span data-stu-id="093b3-120">Square Root</span></span>
* <span data-ttu-id="093b3-121">減算</span><span class="sxs-lookup"><span data-stu-id="093b3-121">Subtraction</span></span>

<span data-ttu-id="093b3-122">これらの functoid について詳しくは、[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="093b3-122">More info on these functoids is [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="093b3-123">参照</span><span class="sxs-lookup"><span data-stu-id="093b3-123">See Also</span></span>  
 [<span data-ttu-id="093b3-124">マップに基本 Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="093b3-124">How to Add Basic Functoids to a Map</span></span>](../core/how-to-add-basic-functoids-to-a-map.md)   
