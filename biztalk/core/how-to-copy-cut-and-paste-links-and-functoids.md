---
title: コピー、切り取り、およびリンクおよび Functoid を貼り付けする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 80b4792a-5ff6-4603-96cd-b3d3d530c12f
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5eec0ddc164af936e1c3739e4da167753a6e58c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22250370"
---
# <a name="how-to-copy-cut-and-paste-links-and-functoids"></a><span data-ttu-id="0d2d8-102">リンクと Functoid をコピー、切り取り、および貼り付けする方法</span><span class="sxs-lookup"><span data-stu-id="0d2d8-102">How to Copy, Cut, and Paste Links and Functoids</span></span>
<span data-ttu-id="0d2d8-103">BizTalk マッパーのコピー/切り取り/貼り付け機能を利用すると、リレーションシップを再利用できます。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-103">The copy/cut/paste feature in the BizTalk Mapper enables the reusability of a relationship.</span></span> <span data-ttu-id="0d2d8-104">このトピックでは、マップ内の Functoid やリンクのコピー、切り取り、および貼り付けの手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-104">This topic provides step-by-step instructions to copy, cut, and paste functoids and/or links in a map.</span></span>  
  
 <span data-ttu-id="0d2d8-105">コピー/貼り付け機能は、Functoid やリンクを再利用するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-105">You can use the copy/paste feature when you want to reuse a set of functoids and/or links.</span></span> <span data-ttu-id="0d2d8-106">また、既存の場所から選択したものを削除して別の場所に移動するときは、切り取り/貼り付け機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-106">And, when you want to remove the selection from the existing location and move it to a new location, you can use the cut/paste feature.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0d2d8-107">切り取り/貼り付けと移動は、よく似ていますが、</span><span class="sxs-lookup"><span data-stu-id="0d2d8-107">Do you feel cut/paste feature and the move feature are similar?</span></span> <span data-ttu-id="0d2d8-108">別の機能です。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-108">There is a difference.</span></span> <span data-ttu-id="0d2d8-109">切り取りを選択したときは、選択範囲の Functoid やリンクのみがソース グリッド ページから削除されます。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-109">When you select cut, only the functoids and/or links in your selection are removed from the source grid page.</span></span> <span data-ttu-id="0d2d8-110">移動を選択したときは、そのリレーションシップ内のすべての Functoid とリンクが (ユーザーが選択したかどうかにかかわらず)、再帰的に、ソース グリッド ページから削除されます。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-110">But, when you select move, all the functoids and links in the relationship (irrespective of the selection), recursively, are removed from the source grid page.</span></span> <span data-ttu-id="0d2d8-111">リレーションシップの移動の詳細については、次を参照してください。 [、リレーションシップのグリッド ページ間を移動する方法](../core/how-to-move-a-relationship-between-grid-pages.md)です。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-111">For more information about moving a relationship, see [How to Move a Relationship Between Grid Pages](../core/how-to-move-a-relationship-between-grid-pages.md).</span></span>  
  
 <span data-ttu-id="0d2d8-112">ときに、コピー/切り取り functoid やリンクのセット、functoid、ラベル、コメント、および、定数値 (プレース ホルダーも) に関連付けられているのセットが保持されます。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-112">When you copy/cut a set of functoids and/or links, the functoids, labels, comments, and the constant values (along with the correct place holders) associated with that set are retained.</span></span>  
  
 <span data-ttu-id="0d2d8-113">コピー/切り取りを実行できるのは、次のマップ項目のみです。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-113">You can copy/cut only these map items:</span></span>  
  
-   <span data-ttu-id="0d2d8-114">ソースからターゲット スキーマへのリンクします。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-114">Link from source to target schema.</span></span>  
  
-   <span data-ttu-id="0d2d8-115">Functoid からスキーマ ノードへのリンク ("Functoid" もリンクと共に選択された場合のみ)</span><span class="sxs-lookup"><span data-stu-id="0d2d8-115">Link from functoid to schema node, if and only if the “functoid” is also selected along with the link.</span></span>  
  
-   <span data-ttu-id="0d2d8-116">Functoid から Functoid へのリンク (両方の Functoid がリンクと共に選択された場合のみ)</span><span class="sxs-lookup"><span data-stu-id="0d2d8-116">Link from functoid to functoid, if and only if both the functoids are selected along with the link.</span></span>  
  
 <span data-ttu-id="0d2d8-117">Functoid やリンクのコピー/切り取りは、次の場所で実行できます。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-117">You can copy/cut functoids and/or links from:</span></span>  
  
-   <span data-ttu-id="0d2d8-118">マップの同じグリッド ページ内</span><span class="sxs-lookup"><span data-stu-id="0d2d8-118">Within the same grid page of a map</span></span>  
  
-   <span data-ttu-id="0d2d8-119">同じマップのグリッド ページ間</span><span class="sxs-lookup"><span data-stu-id="0d2d8-119">One grid page to the other in the same map</span></span>  
  
-   <span data-ttu-id="0d2d8-120">Visual Studio の同じインスタンス内のマップ間</span><span class="sxs-lookup"><span data-stu-id="0d2d8-120">One map to the other in the same instance of Visual Studio</span></span>  
  
-   <span data-ttu-id="0d2d8-121">Visual Studio のインスタンスから別のインスタンス</span><span class="sxs-lookup"><span data-stu-id="0d2d8-121">Across different instances of Visual Studio</span></span>  
  
 <span data-ttu-id="0d2d8-122">切り取り/貼り付け操作は元に戻したり、やり直したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-122">You can undo or redo the cut and paste operations.</span></span> <span data-ttu-id="0d2d8-123">詳細については、次を参照してください。[を元に戻すまたはユーザーの操作をやり直す方法](../core/how-to-undo-or-redo-user-operations.md)です。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-123">For more information, see [How to Undo or Redo User Operations](../core/how-to-undo-or-redo-user-operations.md).</span></span>  
  
 <span data-ttu-id="0d2d8-124">これに加えて、リンクを貼り付けるときは次の点を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-124">In addition to this, you must consider the following points while pasting links:</span></span>  
  
-   <span data-ttu-id="0d2d8-125">ソース スキーマ/ターゲット スキーマ間のリンクの貼り付けができるのは、そのリンクのソース ノードおよびターゲット ノードの XPath と同一の XPath を持つソース ノードおよびターゲット ノードが、貼り付け先のマップに存在している場合のみです。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-125">A link between the source and target schema can be pasted if and only if the current map, where the link is being pasted, contains a source node as well as a target node whose XPath is identical to the XPath of the source and target nodes for the link being pasted.</span></span>  
  
-   <span data-ttu-id="0d2d8-126">ソース スキーマ/ターゲット スキーマ間のリンクの貼り付けができるのは、前述のソース ノードとターゲット ノードの間にリンクが 1 つも存在しない場合のみです。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-126">A link between the source and target schema can be pasted if and only if there is no existing link between the aforesaid source and target nodes.</span></span>  
  
-   <span data-ttu-id="0d2d8-127">Functoid からターゲット スキーマへのリンクの貼り付けができるのは、そのリンクのターゲット ノードの XPath と同じ XPath を持つターゲット ノードが存在する場合のみです。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-127">A link from a functoid to target schema can be pasted if and only if there exists a target node whose XPath is same as the XPath of the target node of the link being pasted.</span></span>  
  
-   <span data-ttu-id="0d2d8-128">ソース スキーマから Functoid へのリンクの貼り付けができるのは、そのリンクのソース ノードの XPath と同じ XPath を持つソース ノードが存在する場合のみです。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-128">A link from a source schema to a functoid can be pasted if and only if there exists a source node whose XPath is same as the XPath of the source node of the link being pasted.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0d2d8-129">複数のアイテム (リンクや Functoid) を選択し、その一部の切り取りまたはコピーができない場合、切り取り/コピー コマンドを実行すると、Visual Studio のステータス バーに "Some of the selected items could not be cut/copied" という警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-129">When you select multiple items (links and/or functoids) such that some of them cannot be cut/copied, then on executing the cut/copy command, the status bar in Visual Studio displays a warning message “Some of the selected items could not be cut/copied.”</span></span> <span data-ttu-id="0d2d8-130">また、メッセージには関連する詳細情報も表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-130">The message also displays relevant details.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0d2d8-131">前提条件</span><span class="sxs-lookup"><span data-stu-id="0d2d8-131">Prerequisites</span></span>  
 <span data-ttu-id="0d2d8-132">これらの手順では、BizTalk マッパーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-132">These instructions require that BizTalk Mapper is running.</span></span>  
  
### <a name="to-copy-and-paste-a-relationship"></a><span data-ttu-id="0d2d8-133">リレーションシップをコピーして貼り付けるには</span><span class="sxs-lookup"><span data-stu-id="0d2d8-133">To copy and paste a relationship</span></span>  
  
1.  <span data-ttu-id="0d2d8-134">ソリューション エクスプローラーで、BizTalk プロジェクトを開き、マップをダブルクリックして BizTalk マッパーで開きます。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-134">In Solution Explorer, open the BizTalk project, and then double-click the map to open it in BizTalk Mapper.</span></span>  
  
2.  <span data-ttu-id="0d2d8-135">コピーする Functoid やリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-135">Select the functoids and/or links you want to copy.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="0d2d8-136">Ctrl キーを押しながら目的の functoid を選択するか、複数のリンクにまたがってマウスをドラッグ アンド ドロップして矩形の選択範囲を形成します。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-136">You can select either by holding down the CTRL key, and then selecting the desired functoids and/or links or by dragging and dropping the mouse across the links to form a rectangular selection.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0d2d8-137">"リボン選択" 操作を使用して、複数のリンクや Functoid を選択できます。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-137">You can use the “ribbon select” operation to select multiple link(s) and/or functoid(s).</span></span> <span data-ttu-id="0d2d8-138">詳細については、次を参照してください。[および Functoid を複数のリンクを選択する方法](../core/how-to-select-multiple-links-and-functoids.md)です。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-138">For more information, see [How to Select Multiple Links and Functoids](../core/how-to-select-multiple-links-and-functoids.md).</span></span>  
  
3.  <span data-ttu-id="0d2d8-139">選択範囲を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-139">Right-click the selection.</span></span> <span data-ttu-id="0d2d8-140">クリックして**コピー**です。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-140">and then click **Copy**.</span></span> <span data-ttu-id="0d2d8-141">または、Ctrl キーを押しながら C キーを押します。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-141">Alternatively, you can press CTRL+C on the keyboard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0d2d8-142">キーボード ショートカットの一覧は、次を参照してください。 [BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)です。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-142">For a list of keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
4.  <span data-ttu-id="0d2d8-143">選択内容を貼り付ける場所にカーソルを置きます。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-143">Place the cursor where you wish to paste the selection.</span></span>  
  
5.  <span data-ttu-id="0d2d8-144">グリッド ページを右クリックし、をクリックして**貼り付け**です。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-144">Right-click on the grid page, and then click **Paste**.</span></span> <span data-ttu-id="0d2d8-145">または、キーボードの Ctrl キーを押しながら V キーを押します。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-145">Alternatively, you can select and press CTRL+V on the keyboard.</span></span> <span data-ttu-id="0d2d8-146">選択したもののコピーが、新しい場所に表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-146">A copy of the selection appears at the new location.</span></span>  
  
### <a name="to-cut-and-paste-a-relationship"></a><span data-ttu-id="0d2d8-147">リレーションシップを切り取って貼り付けるには</span><span class="sxs-lookup"><span data-stu-id="0d2d8-147">To cut and paste a relationship</span></span>  
  
1.  <span data-ttu-id="0d2d8-148">ソリューション エクスプローラーで、BizTalk プロジェクトを開き、マップをダブルクリックして BizTalk マッパーで開きます。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-148">In Solution Explorer, open the BizTalk project, and then double-click the map to open it in BizTalk Mapper.</span></span>  
  
2.  <span data-ttu-id="0d2d8-149">切り取る Functoid やリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-149">Select the functoids and/or links you want to cut.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="0d2d8-150">Ctrl キーを押しながら目的の functoid を選択するか、複数のリンクにまたがってマウスをドラッグ アンド ドロップして矩形の選択範囲を形成します。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-150">You can select either by holding down the CTRL key, and then selecting the desired functoids and/or links or by dragging and dropping the mouse across the links to form a rectangular selection.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0d2d8-151">"リボン選択" 操作を使用して、複数のリンクや Functoid を選択できます。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-151">You can use the “ribbon select” operation to select multiple link(s) and/or functoid(s).</span></span> <span data-ttu-id="0d2d8-152">詳細については、次を参照してください。[および Functoid を複数のリンクを選択する方法](../core/how-to-select-multiple-links-and-functoids.md)です。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-152">For more information, see [How to Select Multiple Links and Functoids](../core/how-to-select-multiple-links-and-functoids.md).</span></span>  
  
3.  <span data-ttu-id="0d2d8-153">選択範囲を右クリックし、をクリックして**切り取り**です。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-153">Right-click the selection, and then click **Cut**.</span></span> <span data-ttu-id="0d2d8-154">または、Ctrl キーを押しながら X キーを押します。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-154">Alternatively, you can press CTRL+X on the keyboard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0d2d8-155">キーボード ショートカットの一覧は、次を参照してください。 [BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)です。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-155">For a list of keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
4.  <span data-ttu-id="0d2d8-156">選択内容を貼り付ける場所にカーソルを置きます。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-156">Place the cursor where you wish to paste the selection.</span></span>  
  
5.  <span data-ttu-id="0d2d8-157">グリッド ページを右クリックし、をクリックして**貼り付け**です。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-157">Right-click on the grid page, and then click **Paste**.</span></span> <span data-ttu-id="0d2d8-158">または、キーボードの Ctrl キーを押しながら V キーを押します。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-158">Alternatively, you can select and press CTRL+V on the keyboard.</span></span> <span data-ttu-id="0d2d8-159">選択したものが既存の場所から削除され、新しい場所に表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d2d8-159">The selection is deleted from the existing location and appears at the new location.</span></span>