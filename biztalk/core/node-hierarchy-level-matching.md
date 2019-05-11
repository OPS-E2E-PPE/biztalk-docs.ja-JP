---
title: ノード階層レベルの照合 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Field nodes
- BizTalk Mapper, processing
- Record node
- BizTalk Mapper, compiler directives
- destination schemas, matching nodes
- source schemas, matching nodes
- maps, links
- Target Links property
- BizTalk Mapper, links
- compiler directives, matching schema nodes
- compiler directives, flattening source hierarchies
- maps, processing
ms.assetid: 5ba1ac77-0e70-4c58-9b8c-1b379dbbb3bd
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 016a02be9634c86c03ac0a5532caf49a59a26c7c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323568"
---
# <a name="node-hierarchy-level-matching"></a><span data-ttu-id="0b4a8-102">ノード階層レベルの照合</span><span class="sxs-lookup"><span data-stu-id="0b4a8-102">Node-Hierarchy Level Matching</span></span>
<span data-ttu-id="0b4a8-103">BizTalk マッパーでは、コンパイラが元と送信先スキーマ間のノード階層をどのように一致しているかを制御する、リンクのプロパティを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="0b4a8-103">BizTalk Mapper enables you to configure a link property to control how the compiler matches node hierarchies between the source and destination schemas.</span></span> <span data-ttu-id="0b4a8-104">送信先スキーマ内のフィールドに、送信元スキーマのフィールドからのリンクを作成するときに BizTalk マッパーが自動的にコンパイラ リンクを追加します。</span><span class="sxs-lookup"><span data-stu-id="0b4a8-104">When you create a link from a field in the source schema to a field in the destination schema, BizTalk Mapper automatically adds compiler links.</span></span> <span data-ttu-id="0b4a8-105">これらのコンパイラ リンクは、選択した照合に依存します。</span><span class="sxs-lookup"><span data-stu-id="0b4a8-105">These compiler links depend on the matching you select.</span></span>  
  
 <span data-ttu-id="0b4a8-106">表示、プロパティの 1 つ表示されているグリッド ページで、リンクを選択すると、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウが、**ターゲット リンク**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="0b4a8-106">When you select a link in the displayed grid page, one of the properties displayed in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window is the **Target Links** property.</span></span> <span data-ttu-id="0b4a8-107">マップには、各リンクの次の値の間で選択できます。</span><span class="sxs-lookup"><span data-stu-id="0b4a8-107">You can choose among the following possible values for each link in your map:</span></span>  
  
-   <span data-ttu-id="0b4a8-108">**リンクをフラット化します。**</span><span class="sxs-lookup"><span data-stu-id="0b4a8-108">**Flatten links.**</span></span> <span data-ttu-id="0b4a8-109">送信先スキーマ ノードの親レコードへのすべてのソース階層をフラット化するのにには、この値を使用します。</span><span class="sxs-lookup"><span data-stu-id="0b4a8-109">Use this value to flatten all source hierarchies to the parent record in the destination schema node.</span></span>  
  
-   <span data-ttu-id="0b4a8-110">**リンクを上から順に一致します。**</span><span class="sxs-lookup"><span data-stu-id="0b4a8-110">**Match links top down.**</span></span> <span data-ttu-id="0b4a8-111">スキーマの下に、スキーマの先頭からのノード レベルを照合するのにには、この値を使用します。</span><span class="sxs-lookup"><span data-stu-id="0b4a8-111">Use this value to match node levels from the top of the schemas to the bottom of the schemas.</span></span>  
  
-   <span data-ttu-id="0b4a8-112">**一致するもの下にリンクします。**</span><span class="sxs-lookup"><span data-stu-id="0b4a8-112">**Match links bottom up.**</span></span> <span data-ttu-id="0b4a8-113">スキーマの先頭に、スキーマの下部にあるノードのレベルを照合するのにには、この値を使用します。</span><span class="sxs-lookup"><span data-stu-id="0b4a8-113">Use this value to match node levels from the bottom of the schemas to the top of the schemas.</span></span>  
  
## <a name="flatten-links"></a><span data-ttu-id="0b4a8-114">リンクをフラット化します。</span><span class="sxs-lookup"><span data-stu-id="0b4a8-114">Flatten Links</span></span>  
 <span data-ttu-id="0b4a8-115">このモードでは、すべてのソース階層は、送信先ノードの親レコードにフラット化します。</span><span class="sxs-lookup"><span data-stu-id="0b4a8-115">In this mode, all the source hierarchies are flattened to the parent record of the destination node.</span></span> <span data-ttu-id="0b4a8-116">最初のケースでは、送信元スキーマは、送信先スキーマよりも複雑です。</span><span class="sxs-lookup"><span data-stu-id="0b4a8-116">In the first case, the source schema is more complex than the destination schema.</span></span> <span data-ttu-id="0b4a8-117">2 番目のケースでは、送信先スキーマが複雑です。</span><span class="sxs-lookup"><span data-stu-id="0b4a8-117">In the second case, the destination schema is more complex.</span></span>  
  
 <span data-ttu-id="0b4a8-118">![](../core/media/bts-tls-flatten.gif "bts_tls_flatten")</span><span class="sxs-lookup"><span data-stu-id="0b4a8-118">![](../core/media/bts-tls-flatten.gif "bts_tls_flatten")</span></span>  
<span data-ttu-id="0b4a8-119">リンクをフラット化します。</span><span class="sxs-lookup"><span data-stu-id="0b4a8-119">Flatten Links</span></span>  
  
 <span data-ttu-id="0b4a8-120">![](../core/media/bts-tls-flatten-2.gif "bts_tls_flatten_2")</span><span class="sxs-lookup"><span data-stu-id="0b4a8-120">![](../core/media/bts-tls-flatten-2.gif "bts_tls_flatten_2")</span></span>  
<span data-ttu-id="0b4a8-121">リンクをフラット化、2 番目のケース</span><span class="sxs-lookup"><span data-stu-id="0b4a8-121">Flatten Links, Second Case</span></span>  
  
## <a name="match-links-top-down"></a><span data-ttu-id="0b4a8-122">一致するリンクの上から下へ</span><span class="sxs-lookup"><span data-stu-id="0b4a8-122">Match Links Top-Down</span></span>  
 <span data-ttu-id="0b4a8-123">このモードでは、上からレベルと一致します。</span><span class="sxs-lookup"><span data-stu-id="0b4a8-123">This mode matches level to level from the top down.</span></span> <span data-ttu-id="0b4a8-124">最初のケースでは、送信元スキーマは、送信先スキーマよりも複雑です。</span><span class="sxs-lookup"><span data-stu-id="0b4a8-124">In the first case, the source schema is more complex than the destination schema.</span></span> <span data-ttu-id="0b4a8-125">2 番目のケースでは、送信先スキーマが複雑です。</span><span class="sxs-lookup"><span data-stu-id="0b4a8-125">In the second case, the destination schema is more complex.</span></span>  
  
 <span data-ttu-id="0b4a8-126">![](../core/media/bts-tls-topdown.gif "bts_tls_topdown")</span><span class="sxs-lookup"><span data-stu-id="0b4a8-126">![](../core/media/bts-tls-topdown.gif "bts_tls_topdown")</span></span>  
<span data-ttu-id="0b4a8-127">上から順に一致します。</span><span class="sxs-lookup"><span data-stu-id="0b4a8-127">Top-Down Matching</span></span>  
  
 <span data-ttu-id="0b4a8-128">![](../core/media/bts-tls-topdown-2.gif "bts_tls_topdown_2")</span><span class="sxs-lookup"><span data-stu-id="0b4a8-128">![](../core/media/bts-tls-topdown-2.gif "bts_tls_topdown_2")</span></span>  
<span data-ttu-id="0b4a8-129">2 番目のケースに一致する、上から下へ</span><span class="sxs-lookup"><span data-stu-id="0b4a8-129">Top-Down Matching, Second Case</span></span>  
  
## <a name="match-links-bottom-up"></a><span data-ttu-id="0b4a8-130">下の一致リンク</span><span class="sxs-lookup"><span data-stu-id="0b4a8-130">Match Links Bottom-Up</span></span>  
 <span data-ttu-id="0b4a8-131">このモードでは、下からレベルと一致します。</span><span class="sxs-lookup"><span data-stu-id="0b4a8-131">This mode matches level to level from the bottom up.</span></span> <span data-ttu-id="0b4a8-132">最初のケースでは、送信元スキーマは、送信先スキーマよりも複雑です。</span><span class="sxs-lookup"><span data-stu-id="0b4a8-132">In the first case, the source schema is more complex than the destination schema.</span></span> <span data-ttu-id="0b4a8-133">2 番目のケースでは、送信先スキーマが複雑です。</span><span class="sxs-lookup"><span data-stu-id="0b4a8-133">In the second case, the destination schema is more complex.</span></span>  
  
 <span data-ttu-id="0b4a8-134">![](../core/media/bts-tls-bottomup.gif "bts_tls_bottomup")</span><span class="sxs-lookup"><span data-stu-id="0b4a8-134">![](../core/media/bts-tls-bottomup.gif "bts_tls_bottomup")</span></span>  
<span data-ttu-id="0b4a8-135">下から順に一致します。</span><span class="sxs-lookup"><span data-stu-id="0b4a8-135">Bottom-Up Matching</span></span>  
  
 <span data-ttu-id="0b4a8-136">![](../core/media/bts-tls-bottomup-2.gif "bts_tls_bottomup_2")</span><span class="sxs-lookup"><span data-stu-id="0b4a8-136">![](../core/media/bts-tls-bottomup-2.gif "bts_tls_bottomup_2")</span></span>  
<span data-ttu-id="0b4a8-137">下から順に一致する、2 番目のケース</span><span class="sxs-lookup"><span data-stu-id="0b4a8-137">Bottom-Up Matching, Second Case</span></span>  
  
## <a name="how-biztalk-mapper-processes-link-types"></a><span data-ttu-id="0b4a8-138">BizTalk マッパーによる各種リンクの処理</span><span class="sxs-lookup"><span data-stu-id="0b4a8-138">How BizTalk Mapper Processes Link Types</span></span>  
 <span data-ttu-id="0b4a8-139">設定できるため、**ターゲット リンク**プロパティごとに異なるリンクに別の値を BizTalk マッパーにさまざまな設定を解決する競合しないようにする方法が必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b4a8-139">Because you can set the **Target Links** property to different values for different links, BizTalk Mapper needs a way to resolve the different settings when they may conflict.</span></span>  
  
 <span data-ttu-id="0b4a8-140">たとえばからのリンクを flatten コンパイラ ディレクティブ、上から下へのコンパイラ ディレクティブおよびボトムアップ コンパイラ ディレクティブを使用する場合**フィールド**ノードを**フィールド**送信先スキーマ、およびこれらのノードノードが同じ親を共有**レコード**ノードで、BizTalk マッパーは、上から下へとボトムアップのコンパイラ ディレクティブの競合を無視し、flatten コンパイラ ディレクティブに設定されているかのように、すべてのリンクを扱います。</span><span class="sxs-lookup"><span data-stu-id="0b4a8-140">For example, if you use a flatten compiler directive, a top-down compiler directive, and a bottom-up compiler directive for links from **Field** nodes to **Field** nodes in the destination schema, and these nodes share the same parent **Record** node, BizTalk Mapper ignores the conflicting top-down and bottom-up compiler directives and treats all the links as if they were set to the flatten compiler directive.</span></span>  
  
 <span data-ttu-id="0b4a8-141">次の表は、BizTalk マッパーがへのリンクを処理する方法を示しています**フィールド**ノードで同じ**レコード**の設定に基づいて、送信先スキーマ ノード、**ターゲット リンク**。プロパティ内で同じリンクを**レコード**ノード。</span><span class="sxs-lookup"><span data-stu-id="0b4a8-141">The following table shows how BizTalk Mapper treats links to **Field** nodes in the same **Record** node in the destination schema, based on the settings for the **Target Links** property for the links within the same **Record** node.</span></span>  
  
|<span data-ttu-id="0b4a8-142">フラット化します。</span><span class="sxs-lookup"><span data-stu-id="0b4a8-142">Flatten</span></span>|<span data-ttu-id="0b4a8-143">上から下へ</span><span class="sxs-lookup"><span data-stu-id="0b4a8-143">Top-down</span></span>|<span data-ttu-id="0b4a8-144">ボトムアップ</span><span class="sxs-lookup"><span data-stu-id="0b4a8-144">Bottom-up</span></span>|<span data-ttu-id="0b4a8-145">結果</span><span class="sxs-lookup"><span data-stu-id="0b4a8-145">Result</span></span>|  
|-------------|---------------|----------------|------------|  
|<span data-ttu-id="0b4a8-146">0 個以上</span><span class="sxs-lookup"><span data-stu-id="0b4a8-146">0 or more</span></span>|<span data-ttu-id="0b4a8-147">1 つ以上</span><span class="sxs-lookup"><span data-stu-id="0b4a8-147">1 or more</span></span>|<span data-ttu-id="0b4a8-148">1 つ以上</span><span class="sxs-lookup"><span data-stu-id="0b4a8-148">1 or more</span></span>|<span data-ttu-id="0b4a8-149">Flatten コンパイラ ディレクティブが指定された場合と、BizTalk マッパーは、すべてのリンクを扱います。</span><span class="sxs-lookup"><span data-stu-id="0b4a8-149">BizTalk Mapper treats all the links as if they were set to the flatten compiler directive.</span></span>|  
|<span data-ttu-id="0b4a8-150">1 つ以上</span><span class="sxs-lookup"><span data-stu-id="0b4a8-150">1 or more</span></span>|<span data-ttu-id="0b4a8-151">1 つ以上</span><span class="sxs-lookup"><span data-stu-id="0b4a8-151">1 or more</span></span>|<span data-ttu-id="0b4a8-152">0</span><span class="sxs-lookup"><span data-stu-id="0b4a8-152">0</span></span>|<span data-ttu-id="0b4a8-153">BizTalk マッパーは、上から下へのコンパイラ ディレクティブに設定されているかのように、すべてのリンクを扱います。</span><span class="sxs-lookup"><span data-stu-id="0b4a8-153">BizTalk Mapper treats all the links as if they were set to the top-down compiler directive.</span></span>|  
|<span data-ttu-id="0b4a8-154">1 つ以上</span><span class="sxs-lookup"><span data-stu-id="0b4a8-154">1 or more</span></span>|<span data-ttu-id="0b4a8-155">0</span><span class="sxs-lookup"><span data-stu-id="0b4a8-155">0</span></span>|<span data-ttu-id="0b4a8-156">1 つ以上</span><span class="sxs-lookup"><span data-stu-id="0b4a8-156">1 or more</span></span>|<span data-ttu-id="0b4a8-157">BizTalk マッパーは、ボトムアップ コンパイラ ディレクティブに設定されているかのように、すべてのリンクを扱います。</span><span class="sxs-lookup"><span data-stu-id="0b4a8-157">BizTalk Mapper treats all the links as if they were set to the bottom-up compiler directive.</span></span>|  
  
 <span data-ttu-id="0b4a8-158">上から下へとボトムアップのコンパイラ ディレクティブは、flatten コンパイラ ディレクティブよりも優先しますが、取り消して他の両方が存在します。</span><span class="sxs-lookup"><span data-stu-id="0b4a8-158">The top-down and bottom-up compiler directives take precedence over the flatten compiler directive, but cancel each other out when both are present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b4a8-159">参照</span><span class="sxs-lookup"><span data-stu-id="0b4a8-159">See Also</span></span>  
 <span data-ttu-id="0b4a8-160">[一括コピー Functoid](../core/mass-copy-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="0b4a8-160">[Mass Copy Functoid](../core/mass-copy-functoid.md) </span></span>  
 <span data-ttu-id="0b4a8-161">[ソース リンクのコンパイラ値を設定する方法](../core/how-to-set-the-source-links-compiler-value.md) </span><span class="sxs-lookup"><span data-stu-id="0b4a8-161">[How to Set the Source Links Compiler Value](../core/how-to-set-the-source-links-compiler-value.md) </span></span>  
 [<span data-ttu-id="0b4a8-162">マップのコンパイル</span><span class="sxs-lookup"><span data-stu-id="0b4a8-162">Compiling Maps</span></span>](../core/compiling-maps.md)