---
title: "ノード階層レベルの照合 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b2d0c363abfefb9e3d0eb8abfb332c59539bb67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="node-hierarchy-level-matching"></a><span data-ttu-id="61cb7-102">ノード階層レベルの照合</span><span class="sxs-lookup"><span data-stu-id="61cb7-102">Node-Hierarchy Level Matching</span></span>
<span data-ttu-id="61cb7-103">BizTalk マッパーでは、リンク プロパティを構成することによって、コンパイラによる送信元スキーマと送信先スキーマ間のノード階層の照合方法を制御できます。</span><span class="sxs-lookup"><span data-stu-id="61cb7-103">BizTalk Mapper enables you to configure a link property to control how the compiler matches node hierarchies between the source and destination schemas.</span></span> <span data-ttu-id="61cb7-104">送信元スキーマのフィールドと送信先スキーマのフィールド間にリンクを作成すると、BizTalk マッパーにより自動的にコンパイラ リンクが追加されます。</span><span class="sxs-lookup"><span data-stu-id="61cb7-104">When you create a link from a field in the source schema to a field in the destination schema, BizTalk Mapper automatically adds compiler links.</span></span> <span data-ttu-id="61cb7-105">コンパイラ リンクは、選択した照合方法に基づいて追加されます。</span><span class="sxs-lookup"><span data-stu-id="61cb7-105">These compiler links depend on the matching you select.</span></span>  
  
 <span data-ttu-id="61cb7-106">表示されるプロパティのいずれかの表示されているグリッド ページで、リンクを選択すると、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウが、**ターゲット リンク**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="61cb7-106">When you select a link in the displayed grid page, one of the properties displayed in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window is the **Target Links** property.</span></span> <span data-ttu-id="61cb7-107">マップの各リンクに対して選択できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="61cb7-107">You can choose among the following possible values for each link in your map:</span></span>  
  
-   <span data-ttu-id="61cb7-108">**リンクをフラット化します。**</span><span class="sxs-lookup"><span data-stu-id="61cb7-108">**Flatten links.**</span></span> <span data-ttu-id="61cb7-109">: 送信元のすべての階層をフラット化して、送信先スキーマ ノードの親レコードと照合する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="61cb7-109">Use this value to flatten all source hierarchies to the parent record in the destination schema node.</span></span>  
  
-   <span data-ttu-id="61cb7-110">**リンクを上から順に一致します。**</span><span class="sxs-lookup"><span data-stu-id="61cb7-110">**Match links top down.**</span></span> <span data-ttu-id="61cb7-111">: スキーマの最上位から最下位へと順にノード レベルを照合する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="61cb7-111">Use this value to match node levels from the top of the schemas to the bottom of the schemas.</span></span>  
  
-   <span data-ttu-id="61cb7-112">**一致リンクを下からです。**</span><span class="sxs-lookup"><span data-stu-id="61cb7-112">**Match links bottom up.**</span></span> <span data-ttu-id="61cb7-113">: スキーマの最下位から最上位へと順にノード レベルを照合する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="61cb7-113">Use this value to match node levels from the bottom of the schemas to the top of the schemas.</span></span>  
  
## <a name="flatten-links"></a><span data-ttu-id="61cb7-114">リンクをフラット化</span><span class="sxs-lookup"><span data-stu-id="61cb7-114">Flatten Links</span></span>  
 <span data-ttu-id="61cb7-115">このモードでは、送信元の階層がフラット化されて、送信先ノードの親レコードと照合されます。</span><span class="sxs-lookup"><span data-stu-id="61cb7-115">In this mode, all the source hierarchies are flattened to the parent record of the destination node.</span></span> <span data-ttu-id="61cb7-116">第 1 のケースでは、送信元スキーマが送信先スキーマよりも複雑な仕様になっています。</span><span class="sxs-lookup"><span data-stu-id="61cb7-116">In the first case, the source schema is more complex than the destination schema.</span></span> <span data-ttu-id="61cb7-117">第 2 のケースでは、送信先スキーマが送信元スキーマよりも複雑な仕様になっています。</span><span class="sxs-lookup"><span data-stu-id="61cb7-117">In the second case, the destination schema is more complex.</span></span>  
  
 ![](../core/media/bts-tls-flatten.gif "bts_tls_flatten")  
<span data-ttu-id="61cb7-118">リンクをフラット化</span><span class="sxs-lookup"><span data-stu-id="61cb7-118">Flatten Links</span></span>  
  
 ![](../core/media/bts-tls-flatten-2.gif "bts_tls_flatten_2")  
<span data-ttu-id="61cb7-119">フラット化されたリンク (第 2 のケース)</span><span class="sxs-lookup"><span data-stu-id="61cb7-119">Flatten Links, Second Case</span></span>  
  
## <a name="match-links-top-down"></a><span data-ttu-id="61cb7-120">一致へのリンクを上から下</span><span class="sxs-lookup"><span data-stu-id="61cb7-120">Match Links Top-Down</span></span>  
 <span data-ttu-id="61cb7-121">このモードでは、上のレベルから下のレベルへと順に照合されます。</span><span class="sxs-lookup"><span data-stu-id="61cb7-121">This mode matches level to level from the top down.</span></span> <span data-ttu-id="61cb7-122">第 1 のケースでは、送信元スキーマが送信先スキーマよりも複雑な仕様になっています。</span><span class="sxs-lookup"><span data-stu-id="61cb7-122">In the first case, the source schema is more complex than the destination schema.</span></span> <span data-ttu-id="61cb7-123">第 2 のケースでは、送信先スキーマが送信元スキーマよりも複雑な仕様になっています。</span><span class="sxs-lookup"><span data-stu-id="61cb7-123">In the second case, the destination schema is more complex.</span></span>  
  
 ![](../core/media/bts-tls-topdown.gif "bts_tls_topdown")  
<span data-ttu-id="61cb7-124">上から順に対応付け</span><span class="sxs-lookup"><span data-stu-id="61cb7-124">Top-Down Matching</span></span>  
  
 ![](../core/media/bts-tls-topdown-2.gif "bts_tls_topdown_2")  
<span data-ttu-id="61cb7-125">上から順に対応付け (第 2 のケース)</span><span class="sxs-lookup"><span data-stu-id="61cb7-125">Top-Down Matching, Second Case</span></span>  
  
## <a name="match-links-bottom-up"></a><span data-ttu-id="61cb7-126">リンクを下から順に一致</span><span class="sxs-lookup"><span data-stu-id="61cb7-126">Match Links Bottom-Up</span></span>  
 <span data-ttu-id="61cb7-127">このモードでは、下のレベルから上のレベルへと順に照合されます。</span><span class="sxs-lookup"><span data-stu-id="61cb7-127">This mode matches level to level from the bottom up.</span></span> <span data-ttu-id="61cb7-128">第 1 のケースでは、送信元スキーマが送信先スキーマよりも複雑な仕様になっています。</span><span class="sxs-lookup"><span data-stu-id="61cb7-128">In the first case, the source schema is more complex than the destination schema.</span></span> <span data-ttu-id="61cb7-129">第 2 のケースでは、送信先スキーマが送信元スキーマよりも複雑な仕様になっています。</span><span class="sxs-lookup"><span data-stu-id="61cb7-129">In the second case, the destination schema is more complex.</span></span>  
  
 ![](../core/media/bts-tls-bottomup.gif "bts_tls_bottomup")  
<span data-ttu-id="61cb7-130">下から順に対応付け</span><span class="sxs-lookup"><span data-stu-id="61cb7-130">Bottom-Up Matching</span></span>  
  
 ![](../core/media/bts-tls-bottomup-2.gif "bts_tls_bottomup_2")  
<span data-ttu-id="61cb7-131">下から順に対応付け (第 2 のケース)</span><span class="sxs-lookup"><span data-stu-id="61cb7-131">Bottom-Up Matching, Second Case</span></span>  
  
## <a name="how-biztalk-mapper-processes-link-types"></a><span data-ttu-id="61cb7-132">BizTalk マッパーによる各種リンクの処理</span><span class="sxs-lookup"><span data-stu-id="61cb7-132">How BizTalk Mapper Processes Link Types</span></span>  
 <span data-ttu-id="61cb7-133">設定できるため、**ターゲット リンク**プロパティを別のリンクに別の値は、BizTalk マッパーに競合しないようにする場合は、さまざまな設定を解決するのには方法が必要です。</span><span class="sxs-lookup"><span data-stu-id="61cb7-133">Because you can set the **Target Links** property to different values for different links, BizTalk Mapper needs a way to resolve the different settings when they may conflict.</span></span>  
  
 <span data-ttu-id="61cb7-134">たとえば、flatten コンパイラ ディレクティブ、トップダウン コンパイラ ディレクティブとボトムアップ コンパイラ ディレクティブからのリンクを使用する場合**フィールド**ノード**フィールド**送信先スキーマ、およびこれらのノードノードは、同じ親を共有**レコード**ノード、BizTalk マッパーが上から下へとボトムアップ コンパイラ ディレクティブの競合を無視し、flatten コンパイラ ディレクティブが設定されている場合、すべてのリンクが処理されます。</span><span class="sxs-lookup"><span data-stu-id="61cb7-134">For example, if you use a flatten compiler directive, a top-down compiler directive, and a bottom-up compiler directive for links from **Field** nodes to **Field** nodes in the destination schema, and these nodes share the same parent **Record** node, BizTalk Mapper ignores the conflicting top-down and bottom-up compiler directives and treats all the links as if they were set to the flatten compiler directive.</span></span>  
  
 <span data-ttu-id="61cb7-135">次の表は、BizTalk マッパーがへのリンクを処理する方法を示しています**フィールド**、同じノード**レコード**の設定に基づいて、送信先スキーマのノード、**ターゲット リンク**。同じ内のリンクのプロパティを**レコード**ノード。</span><span class="sxs-lookup"><span data-stu-id="61cb7-135">The following table shows how BizTalk Mapper treats links to **Field** nodes in the same **Record** node in the destination schema, based on the settings for the **Target Links** property for the links within the same **Record** node.</span></span>  
  
|<span data-ttu-id="61cb7-136">フラット化</span><span class="sxs-lookup"><span data-stu-id="61cb7-136">Flatten</span></span>|<span data-ttu-id="61cb7-137">上から下</span><span class="sxs-lookup"><span data-stu-id="61cb7-137">Top-down</span></span>|<span data-ttu-id="61cb7-138">下から上</span><span class="sxs-lookup"><span data-stu-id="61cb7-138">Bottom-up</span></span>|<span data-ttu-id="61cb7-139">結果</span><span class="sxs-lookup"><span data-stu-id="61cb7-139">Result</span></span>|  
|-------------|---------------|----------------|------------|  
|<span data-ttu-id="61cb7-140">0 以上</span><span class="sxs-lookup"><span data-stu-id="61cb7-140">0 or more</span></span>|<span data-ttu-id="61cb7-141">1 つ以上</span><span class="sxs-lookup"><span data-stu-id="61cb7-141">1 or more</span></span>|<span data-ttu-id="61cb7-142">1 つ以上</span><span class="sxs-lookup"><span data-stu-id="61cb7-142">1 or more</span></span>|<span data-ttu-id="61cb7-143">[リンクをフラット化] のコンパイラ ディレクティブが設定されているものとして、すべてのリンクが処理されます。</span><span class="sxs-lookup"><span data-stu-id="61cb7-143">BizTalk Mapper treats all the links as if they were set to the flatten compiler directive.</span></span>|  
|<span data-ttu-id="61cb7-144">1 つ以上</span><span class="sxs-lookup"><span data-stu-id="61cb7-144">1 or more</span></span>|<span data-ttu-id="61cb7-145">1 つ以上</span><span class="sxs-lookup"><span data-stu-id="61cb7-145">1 or more</span></span>|<span data-ttu-id="61cb7-146">0</span><span class="sxs-lookup"><span data-stu-id="61cb7-146">0</span></span>|<span data-ttu-id="61cb7-147">[リンクを上から順に一致] のコンパイラ ディレクティブが設定されているものとして、すべてのリンクが処理されます。</span><span class="sxs-lookup"><span data-stu-id="61cb7-147">BizTalk Mapper treats all the links as if they were set to the top-down compiler directive.</span></span>|  
|<span data-ttu-id="61cb7-148">1 つ以上</span><span class="sxs-lookup"><span data-stu-id="61cb7-148">1 or more</span></span>|<span data-ttu-id="61cb7-149">0</span><span class="sxs-lookup"><span data-stu-id="61cb7-149">0</span></span>|<span data-ttu-id="61cb7-150">1 つ以上</span><span class="sxs-lookup"><span data-stu-id="61cb7-150">1 or more</span></span>|<span data-ttu-id="61cb7-151">[リンクを下から順に一致] のコンパイラ ディレクティブが設定されているものとして、すべてのリンクが処理されます。</span><span class="sxs-lookup"><span data-stu-id="61cb7-151">BizTalk Mapper treats all the links as if they were set to the bottom-up compiler directive.</span></span>|  
  
 <span data-ttu-id="61cb7-152">[リンクを上から順に一致] および [リンクを下から順に一致] のコンパイラ ディレクティブは [リンクをフラット化] よりも優先されますが、両方が存在する場合は、どちらの動作も無効になります。</span><span class="sxs-lookup"><span data-stu-id="61cb7-152">The top-down and bottom-up compiler directives take precedence over the flatten compiler directive, but cancel each other out when both are present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61cb7-153">参照</span><span class="sxs-lookup"><span data-stu-id="61cb7-153">See Also</span></span>  
 <span data-ttu-id="61cb7-154">[一括コピー Functoid](../core/mass-copy-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="61cb7-154">[Mass Copy Functoid](../core/mass-copy-functoid.md) </span></span>  
 <span data-ttu-id="61cb7-155">[ソースへのリンクのコンパイラ値を設定する方法](../core/how-to-set-the-source-links-compiler-value.md) </span><span class="sxs-lookup"><span data-stu-id="61cb7-155">[How to Set the Source Links Compiler Value](../core/how-to-set-the-source-links-compiler-value.md) </span></span>  
 [<span data-ttu-id="61cb7-156">マップのコンパイル</span><span class="sxs-lookup"><span data-stu-id="61cb7-156">Compiling Maps</span></span>](../core/compiling-maps.md)