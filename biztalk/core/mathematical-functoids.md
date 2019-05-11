---
title: 数値演算 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 244fa926-a086-4398-a677-9c322e9024b2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a1b9abda0e6bd1ae526f97d138616a751e7aa2d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380033"
---
# <a name="mathematical-functoids"></a><span data-ttu-id="556ba-102">数値演算 Functoid</span><span class="sxs-lookup"><span data-stu-id="556ba-102">Mathematical Functoids</span></span>

## <a name="overview"></a><span data-ttu-id="556ba-103">概要</span><span class="sxs-lookup"><span data-stu-id="556ba-103">Overview</span></span>
<span data-ttu-id="556ba-104">**数学**さまざまな基本的な算術演算を実行する functoid を使用します。</span><span class="sxs-lookup"><span data-stu-id="556ba-104">**Mathematical** functoids are used to perform a variety of basic mathematical operations.</span></span>  
  
 <span data-ttu-id="556ba-105">入力パラメーターの数、**数値演算**functoid、functoid から functoid が異なるし、これらの functoid が多数の入力を受け入れ、します。</span><span class="sxs-lookup"><span data-stu-id="556ba-105">The number of input parameters to the **Mathematical** functoids varies from functoid to functoid, and where reasonable, these functoids accept large numbers of inputs.</span></span> <span data-ttu-id="556ba-106">たとえば、**除算**functoid が中に 2 つの入力パラメーター (被除数と除数) が必要です、**加算**functoid が受け入れる 2 と 100 の入力パラメーターの間でその結果、合計。</span><span class="sxs-lookup"><span data-stu-id="556ba-106">For example, the **Division** functoid requires exactly two input parameters (the dividend and the divisor), while the **Addition** functoid accepts between 2 and 100 input parameters, resulting in their sum.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="556ba-107">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 、.NET Framework の一部で生成される結果の基になる機能を使用して、**数値演算**以前のバージョンの BizTalk Server の同等な functoid から functoid が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="556ba-107">Because Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses the underlying functionality of the .NET Framework, the results produced by some of the **Mathematical** functoids may vary from the equivalent functoids in previous versions of BizTalk Server.</span></span> <span data-ttu-id="556ba-108">期待した結果を取得するかどうかを必ず徹底的にマップをテストします。</span><span class="sxs-lookup"><span data-stu-id="556ba-108">Test your maps thoroughly to be sure you are getting the results you expect.</span></span>  

## <a name="functoids-list"></a><span data-ttu-id="556ba-109">Functoid の一覧</span><span class="sxs-lookup"><span data-stu-id="556ba-109">Functoids list</span></span>  
 <span data-ttu-id="556ba-110">**数値演算**functoid には。</span><span class="sxs-lookup"><span data-stu-id="556ba-110">The **Mathematical** functoids are:</span></span> 

* <span data-ttu-id="556ba-111">絶対値</span><span class="sxs-lookup"><span data-stu-id="556ba-111">Absolute Value</span></span>
* <span data-ttu-id="556ba-112">加算</span><span class="sxs-lookup"><span data-stu-id="556ba-112">Addition</span></span>
* <span data-ttu-id="556ba-113">除算</span><span class="sxs-lookup"><span data-stu-id="556ba-113">Division</span></span>
* <span data-ttu-id="556ba-114">Integer</span><span class="sxs-lookup"><span data-stu-id="556ba-114">Integer</span></span>
* <span data-ttu-id="556ba-115">最大値</span><span class="sxs-lookup"><span data-stu-id="556ba-115">Maximum Value</span></span>
* <span data-ttu-id="556ba-116">最小値</span><span class="sxs-lookup"><span data-stu-id="556ba-116">Minimum Value</span></span>
* <span data-ttu-id="556ba-117">剰余</span><span class="sxs-lookup"><span data-stu-id="556ba-117">Modulo</span></span>
* <span data-ttu-id="556ba-118">乗算</span><span class="sxs-lookup"><span data-stu-id="556ba-118">Multiplication</span></span>
* <span data-ttu-id="556ba-119">四捨五入</span><span class="sxs-lookup"><span data-stu-id="556ba-119">Round</span></span>
* <span data-ttu-id="556ba-120">平方根</span><span class="sxs-lookup"><span data-stu-id="556ba-120">Square Root</span></span>
* <span data-ttu-id="556ba-121">減算</span><span class="sxs-lookup"><span data-stu-id="556ba-121">Subtraction</span></span>

<span data-ttu-id="556ba-122">これらの functoid の詳細については、[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="556ba-122">More info on these functoids is [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="556ba-123">参照</span><span class="sxs-lookup"><span data-stu-id="556ba-123">See Also</span></span>  
 [<span data-ttu-id="556ba-124">マップに基本 Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="556ba-124">How to Add Basic Functoids to a Map</span></span>](../core/how-to-add-basic-functoids-to-a-map.md)   
