---
title: リンクの表示を最適化する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a9e16ff-01d3-4b7d-91c4-59d17266ee6d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 689ab4c67bfe8cabc8109c373e899d391fdd56a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254386"
---
# <a name="how-to-optimize-the-display-of-links"></a><span data-ttu-id="783fb-102">リンクの表示を最適化する方法</span><span class="sxs-lookup"><span data-stu-id="783fb-102">How to Optimize the Display of Links</span></span>
<span data-ttu-id="783fb-103">スキーマの規模が大きい場合、マップに含まれる送信元スキーマと送信先スキーマとのリンクの数が多数になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="783fb-103">When the schemas are big, your maps might include a large number of links between the source and the destination schemas.</span></span> <span data-ttu-id="783fb-104">マップ画面全体で多くのリンクを使用する可能性がありますが難しいと感じてリンクまたはで動作する必要があるオブジェクトを追跡するためにします。</span><span class="sxs-lookup"><span data-stu-id="783fb-104">With many links across the map surface, you may find it difficult to track a link or an object you need to work on.</span></span> <span data-ttu-id="783fb-105">また、送信元スキーマ、リンク、Functoid、および送信先スキーマのエンドツーエンドの関係を追跡することも難しくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="783fb-105">Also, it can be difficult for you to track an end-to-end relationship between a source schema, the links, the functoids, and the destination schema.</span></span> <span data-ttu-id="783fb-106">BizTalk マッパーでは、複雑で大規模なスキーマを効率的に管理し、マップ内のリンクの表示を最適化することができます。</span><span class="sxs-lookup"><span data-stu-id="783fb-106">In the BizTalk Mapper, you can better manage complex and large schemas, and bring out an optimized display of links in the map.</span></span> <span data-ttu-id="783fb-107">このトピックでは、リンクの表示方法について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="783fb-107">This topic provides details about how to view links.</span></span>  
  
 <span data-ttu-id="783fb-108">リンクは次のように分類することができます。</span><span class="sxs-lookup"><span data-stu-id="783fb-108">You can categorize the links as follows:</span></span>  
  
-   <span data-ttu-id="783fb-109">部分的にスコープ内</span><span class="sxs-lookup"><span data-stu-id="783fb-109">Partially in scope</span></span>  
  
-   <span data-ttu-id="783fb-110">完全にスコープ内</span><span class="sxs-lookup"><span data-stu-id="783fb-110">Completely in scope</span></span>  
  
-   <span data-ttu-id="783fb-111">完全にスコープ外</span><span class="sxs-lookup"><span data-stu-id="783fb-111">Completely out of scope</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="783fb-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="783fb-112">Prerequisites</span></span>  
 <span data-ttu-id="783fb-113">これらの手順では、BizTalk マッパーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="783fb-113">These instructions require that BizTalk Mapper is running.</span></span>  
  
## <a name="to-view-the-links-partially-in-scope"></a><span data-ttu-id="783fb-114">部分的にスコープ内にあるリンクを表示するには</span><span class="sxs-lookup"><span data-stu-id="783fb-114">To view the links partially in scope</span></span>  
 <span data-ttu-id="783fb-115">少なくとも一方の端がグリッド画面に表示されているリンクを、"部分的にスコープ内" にあるリンクと呼びます。</span><span class="sxs-lookup"><span data-stu-id="783fb-115">Links that have at least one end visible on the grid surface are called “partially in scope.”</span></span>  
  
 <span data-ttu-id="783fb-116">次の図は、"部分的にスコープ内" にあるリンクを示しています。</span><span class="sxs-lookup"><span data-stu-id="783fb-116">The figure below shows a link that is “partially in scope.”</span></span> <span data-ttu-id="783fb-117">これらのリンクは、グリッド ページでは破線で表示されます。</span><span class="sxs-lookup"><span data-stu-id="783fb-117">These links are shown as dashed lines on the grid page.</span></span>  
  
 <span data-ttu-id="783fb-118">グリッド画面に部分的に表示されているリンクをクリックすると、グリッド ページが自動的に上/下に移動して、現在のビューにリレーションシップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="783fb-118">Click the link that is partially visible on the grid surface, and the grid page automatically moves up/down to bring the relationship into the current view.</span></span>  
  
 <span data-ttu-id="783fb-119">![部分的にスコープ内のマッパー リンク](../core/media/mapper-partiallyinscope.gif "Mapper_PartiallyInScope")</span><span class="sxs-lookup"><span data-stu-id="783fb-119">![Mapper links partially in scope](../core/media/mapper-partiallyinscope.gif "Mapper_PartiallyInScope")</span></span>  
  
## <a name="to-view-the-links-completely-in-scope"></a><span data-ttu-id="783fb-120">完全にスコープ内にあるリンクを表示するには</span><span class="sxs-lookup"><span data-stu-id="783fb-120">To view the links completely in scope</span></span>  
 <span data-ttu-id="783fb-121">グリッド画面に両方の端 (ノードとノード、ノードと Functoid、Functoid と Functoid、または Functoid とノード) が表示されているリンクを、"完全にスコープ内" にあるリンクと呼びます。</span><span class="sxs-lookup"><span data-stu-id="783fb-121">A link that has both ends (node to node, node to functoid, functoid-to-functoid, or functoid to node) visible on the grid surface is called “completely in scope.”</span></span>  
  
 <span data-ttu-id="783fb-122">次の図は、完全にスコープ内にある "DataCollection1" と "ST01" とのリンクを示しています。</span><span class="sxs-lookup"><span data-stu-id="783fb-122">The figure below shows a link between “DataCollection1” and “ST01” that is completely in scope.</span></span>  
  
 <span data-ttu-id="783fb-123">リンクをクリックすると、送信元ノードから送信先ノードへのリレーションシップが選択されます。</span><span class="sxs-lookup"><span data-stu-id="783fb-123">Click the link, and the relationship from source node to target node is selected.</span></span>  
  
 <span data-ttu-id="783fb-124">![完全にスコープ内のマッパー リンク](../core/media/mapper-completelyinscope.gif "Mapper_CompletelyInScope")</span><span class="sxs-lookup"><span data-stu-id="783fb-124">![Mapper links completely in scope](../core/media/mapper-completelyinscope.gif "Mapper_CompletelyInScope")</span></span>  
  
## <a name="to-view-the-links-completely-out-of-scope"></a><span data-ttu-id="783fb-125">完全にスコープ外にあるリンクを表示するには</span><span class="sxs-lookup"><span data-stu-id="783fb-125">To view the links completely out of scope</span></span>  
 <span data-ttu-id="783fb-126">現在のマップ ビューにどちらのエンド ポイントも表示されていないリンクを、"完全にスコープ外" にあるリンクと呼びます。</span><span class="sxs-lookup"><span data-stu-id="783fb-126">A link that has neither of its end points visible in the current map view is called “completely out of scope.”</span></span>  
  
 <span data-ttu-id="783fb-127">次の図は、完全にスコープ外にあるリンクを示しています。</span><span class="sxs-lookup"><span data-stu-id="783fb-127">The figure below shows a link that is completely out of scope.</span></span>  
  
 <span data-ttu-id="783fb-128">これらのリンク、マップ画面に (どのリンクも表示されている) ためにを表示したくない場合、 をクリックしてオフにすることもできます![リンクをすべて表示](../core/media/mapper-showhideoutscopelinks.gif "Mapper_ShowHideOutScopeLinks")マッパー上表示するユーティリティ リボンです。</span><span class="sxs-lookup"><span data-stu-id="783fb-128">If you do not want to display these links on the map surface (because none of the links are visible), you may choose to turn them off by clicking ![Show all links](../core/media/mapper-showhideoutscopelinks.gif "Mapper_ShowHideOutScopeLinks") on the Mapper utility ribbon.</span></span> <span data-ttu-id="783fb-129">これによって、グリッド ビューに表示されるリンクの数を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="783fb-129">This reduces the amount of links that are visible on the grid view.</span></span>  
  
 <span data-ttu-id="783fb-130">![完全にスコープ外のマッパー リンク](../core/media/mapper-completelyoutscope.gif "Mapper_CompletelyOutScope")</span><span class="sxs-lookup"><span data-stu-id="783fb-130">![Mapper links completely out of scope](../core/media/mapper-completelyoutscope.gif "Mapper_CompletelyOutScope")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="783fb-131">参照</span><span class="sxs-lookup"><span data-stu-id="783fb-131">See Also</span></span>  
 [<span data-ttu-id="783fb-132">BizTalk マッパーの強化された機能を使用</span><span class="sxs-lookup"><span data-stu-id="783fb-132">Using Enhanced Features in BizTalk Mapper</span></span>](../core/using-enhanced-features-in-biztalk-mapper.md)