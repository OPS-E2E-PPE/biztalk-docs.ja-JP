---
title: リンクの表示を最適化する方法 |Microsoft Docs
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
ms.openlocfilehash: da7eec1cb22dfea1522b94d1bbb948a627ed4ffa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335826"
---
# <a name="how-to-optimize-the-display-of-links"></a><span data-ttu-id="344b1-102">リンクの表示を最適化する方法</span><span class="sxs-lookup"><span data-stu-id="344b1-102">How to Optimize the Display of Links</span></span>
<span data-ttu-id="344b1-103">スキーマが大きい場合、マップでは、ソース スキーマと送信先スキーマ間のリンクの数が多いを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="344b1-103">When the schemas are big, your maps might include a large number of links between the source and the destination schemas.</span></span> <span data-ttu-id="344b1-104">マップ画面間で多数のリンクを使用するが困難リンクまたはで動作する必要があるオブジェクトを追跡します。</span><span class="sxs-lookup"><span data-stu-id="344b1-104">With many links across the map surface, you may find it difficult to track a link or an object you need to work on.</span></span> <span data-ttu-id="344b1-105">また、送信元スキーマ、リンク、functoid および送信先スキーマ間で、エンド ツー エンドの関係を追跡するための困難ができます。</span><span class="sxs-lookup"><span data-stu-id="344b1-105">Also, it can be difficult for you to track an end-to-end relationship between a source schema, the links, the functoids, and the destination schema.</span></span> <span data-ttu-id="344b1-106">BizTalk マッパーでより複雑で大規模なスキーマを管理し、ルイユ マップ内のリンクの表示を最適化できます。</span><span class="sxs-lookup"><span data-stu-id="344b1-106">In the BizTalk Mapper, you can better manage complex and large schemas, and bring out an optimized display of links in the map.</span></span> <span data-ttu-id="344b1-107">このトピックでは、リンクを表示する方法の詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="344b1-107">This topic provides details about how to view links.</span></span>  
  
 <span data-ttu-id="344b1-108">とおりリンクを分類することができます。</span><span class="sxs-lookup"><span data-stu-id="344b1-108">You can categorize the links as follows:</span></span>  
  
-   <span data-ttu-id="344b1-109">部分的にスコープ内</span><span class="sxs-lookup"><span data-stu-id="344b1-109">Partially in scope</span></span>  
  
-   <span data-ttu-id="344b1-110">完全にスコープ内</span><span class="sxs-lookup"><span data-stu-id="344b1-110">Completely in scope</span></span>  
  
-   <span data-ttu-id="344b1-111">完全にスコープ外</span><span class="sxs-lookup"><span data-stu-id="344b1-111">Completely out of scope</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="344b1-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="344b1-112">Prerequisites</span></span>  
 <span data-ttu-id="344b1-113">これらの手順では、BizTalk マッパーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="344b1-113">These instructions require that BizTalk Mapper is running.</span></span>  
  
## <a name="to-view-the-links-partially-in-scope"></a><span data-ttu-id="344b1-114">部分的にスコープ内のリンクを表示するには</span><span class="sxs-lookup"><span data-stu-id="344b1-114">To view the links partially in scope</span></span>  
 <span data-ttu-id="344b1-115">グリッド画面に表示される少なくとも 1 つの終了しているリンクは「部分的にスコープ内。」と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="344b1-115">Links that have at least one end visible on the grid surface are called “partially in scope.”</span></span>  
  
 <span data-ttu-id="344b1-116">次の図は、"部分的にスコープ。"内にあるリンクを示しています。</span><span class="sxs-lookup"><span data-stu-id="344b1-116">The figure below shows a link that is “partially in scope.”</span></span> <span data-ttu-id="344b1-117">これらのリンクは、グリッド ページの破線として表示されます。</span><span class="sxs-lookup"><span data-stu-id="344b1-117">These links are shown as dashed lines on the grid page.</span></span>  
  
 <span data-ttu-id="344b1-118">グリッド画面に部分的に表示されているリンクをクリックし、グリッド ページはアップ/ダウンを自動的に移動すると、現在のビューにリレーションシップを表示します。</span><span class="sxs-lookup"><span data-stu-id="344b1-118">Click the link that is partially visible on the grid surface, and the grid page automatically moves up/down to bring the relationship into the current view.</span></span>  
  
 <span data-ttu-id="344b1-119">![部分的にスコープ内のマッパー リンク](../core/media/mapper-partiallyinscope.gif "Mapper_PartiallyInScope")</span><span class="sxs-lookup"><span data-stu-id="344b1-119">![Mapper links partially in scope](../core/media/mapper-partiallyinscope.gif "Mapper_PartiallyInScope")</span></span>  
  
## <a name="to-view-the-links-completely-in-scope"></a><span data-ttu-id="344b1-120">完全にスコープ内のリンクを表示するには</span><span class="sxs-lookup"><span data-stu-id="344b1-120">To view the links completely in scope</span></span>  
 <span data-ttu-id="344b1-121">グリッド画面に両方の end (functoid、functoid、functoid、またはノードを functoid にノードをノード) 表示しているリンクは「完全にスコープ内。」と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="344b1-121">A link that has both ends (node to node, node to functoid, functoid-to-functoid, or functoid to node) visible on the grid surface is called “completely in scope.”</span></span>  
  
 <span data-ttu-id="344b1-122">"ある DataCollection1"と"ST01"間のリンクを下の図は、完全にスコープであります。</span><span class="sxs-lookup"><span data-stu-id="344b1-122">The figure below shows a link between “DataCollection1” and “ST01” that is completely in scope.</span></span>  
  
 <span data-ttu-id="344b1-123">リンクをクリックし、ターゲット ノードには、送信元ノードからのリレーションシップを選択します。</span><span class="sxs-lookup"><span data-stu-id="344b1-123">Click the link, and the relationship from source node to target node is selected.</span></span>  
  
 <span data-ttu-id="344b1-124">![完全にスコープ内のマッパー リンク](../core/media/mapper-completelyinscope.gif "Mapper_CompletelyInScope")</span><span class="sxs-lookup"><span data-stu-id="344b1-124">![Mapper links completely in scope](../core/media/mapper-completelyinscope.gif "Mapper_CompletelyInScope")</span></span>  
  
## <a name="to-view-the-links-completely-out-of-scope"></a><span data-ttu-id="344b1-125">完全にスコープ外のリンクを表示するには</span><span class="sxs-lookup"><span data-stu-id="344b1-125">To view the links completely out of scope</span></span>  
 <span data-ttu-id="344b1-126">現在のマップ ビューに表示されるエンドポイントのどちらを持つリンクは"完全にスコープ外。"と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="344b1-126">A link that has neither of its end points visible in the current map view is called “completely out of scope.”</span></span>  
  
 <span data-ttu-id="344b1-127">次の図は、完全にスコープ外にあるリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="344b1-127">The figure below shows a link that is completely out of scope.</span></span>  
  
 <span data-ttu-id="344b1-128">これらのリンク、マップ画面に (どのリンクも表示されている) ためにを表示したくない場合をクリックしてオフにすることができます![リンクをすべて表示](../core/media/mapper-showhideoutscopelinks.gif "Mapper_ShowHideOutScopeLinks")マッパー上ユーティリティ リボンです。</span><span class="sxs-lookup"><span data-stu-id="344b1-128">If you do not want to display these links on the map surface (because none of the links are visible), you may choose to turn them off by clicking ![Show all links](../core/media/mapper-showhideoutscopelinks.gif "Mapper_ShowHideOutScopeLinks") on the Mapper utility ribbon.</span></span> <span data-ttu-id="344b1-129">これには、グリッド ビューに表示されているリンクの数が削減されます。</span><span class="sxs-lookup"><span data-stu-id="344b1-129">This reduces the amount of links that are visible on the grid view.</span></span>  
  
 <span data-ttu-id="344b1-130">![完全にスコープ外のマッパー リンク](../core/media/mapper-completelyoutscope.gif "Mapper_CompletelyOutScope")</span><span class="sxs-lookup"><span data-stu-id="344b1-130">![Mapper links completely out of scope](../core/media/mapper-completelyoutscope.gif "Mapper_CompletelyOutScope")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="344b1-131">参照</span><span class="sxs-lookup"><span data-stu-id="344b1-131">See Also</span></span>  
 [<span data-ttu-id="344b1-132">BizTalk マッパーの強化された機能の使用</span><span class="sxs-lookup"><span data-stu-id="344b1-132">Using Enhanced Features in BizTalk Mapper</span></span>](../core/using-enhanced-features-in-biztalk-mapper.md)