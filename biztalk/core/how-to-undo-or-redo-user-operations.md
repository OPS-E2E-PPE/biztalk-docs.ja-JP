---
title: 元に戻すまたはユーザーの操作を再実行する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1cb3708e-a9c2-4795-aba0-9c6d9635e08c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ef4122e31bae1c3bd0e107b5a5bb8a4c7405e42
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383683"
---
# <a name="how-to-undo-or-redo-user-operations"></a><span data-ttu-id="e4c8c-102">元に戻すまたはユーザーの操作を再実行する方法</span><span class="sxs-lookup"><span data-stu-id="e4c8c-102">How to Undo or Redo User Operations</span></span>
<span data-ttu-id="e4c8c-103">元に戻す/やり直しのサポートはまだ別の便利な操作は、BizTalk マッパーによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="e4c8c-103">The support for undo/redo is yet another usability aid provided by the BizTalk Mapper.</span></span> <span data-ttu-id="e4c8c-104">変更に満足していない場合、ユーザーが実行または変更を誤って作成した場合は、段階的には、前の状態、およびそこから再開する元に戻すを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e4c8c-104">If you are not satisfied with modifications you have made, or if you have made a change by mistake, you can use undo to gradually come back to an earlier "untouched" state, and resume from there.</span></span> <span data-ttu-id="e4c8c-105">再実行完了されている編集操作を再適用することができます。</span><span class="sxs-lookup"><span data-stu-id="e4c8c-105">Redo allows you to reapply the editing actions that have been undone.</span></span> <span data-ttu-id="e4c8c-106">このトピックでは、操作を元に戻す/やり直すをについてを説明します。</span><span class="sxs-lookup"><span data-stu-id="e4c8c-106">This topic provides information about the operations that you can undo/redo.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e4c8c-107">マップ上の操作が編集を行ったときに少なくとも 1 つのみ、操作を元に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="e4c8c-107">You can undo an operation only when you have performed at least one edit operation on the map.</span></span> <span data-ttu-id="e4c8c-108">元に戻すコマンドを使用していない限り、再実行は使用できません。</span><span class="sxs-lookup"><span data-stu-id="e4c8c-108">Redo is unavailable unless you have used the undo command.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e4c8c-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="e4c8c-109">Prerequisites</span></span>  
 <span data-ttu-id="e4c8c-110">これらの手順では、BizTalk マッパーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4c8c-110">These instructions require that BizTalk Mapper is running.</span></span>  
  
## <a name="what-can-you-undoredo"></a><span data-ttu-id="e4c8c-111">内容を元に戻す/やり直すでしょうか。</span><span class="sxs-lookup"><span data-stu-id="e4c8c-111">What can you undo/redo?</span></span>  
 <span data-ttu-id="e4c8c-112">元に戻す/やり直すすべての編集操作。</span><span class="sxs-lookup"><span data-stu-id="e4c8c-112">You can undo/redo all editing operations.</span></span> <span data-ttu-id="e4c8c-113">元に戻す/再実行できる操作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e4c8c-113">The operations that can be undone/redone are as follows:</span></span>  
  
-   <span data-ttu-id="e4c8c-114">切り取り/コピー/貼り付け functoid やリンク</span><span class="sxs-lookup"><span data-stu-id="e4c8c-114">Cutting/copying/pasting functoids and/or link</span></span>  
  
     <span data-ttu-id="e4c8c-115">元に戻すまたは任意の数の項目 (リンクや functoid) を選択してコピーすることだけで再実行できません。</span><span class="sxs-lookup"><span data-stu-id="e4c8c-115">You cannot undo or redo any number of items (links/functoids) by simply selecting and copying them.</span></span> <span data-ttu-id="e4c8c-116">コピー関数は、マップでは何も変わりません。</span><span class="sxs-lookup"><span data-stu-id="e4c8c-116">Copy function does not change anything on the map.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e4c8c-117">Functoid の切り取り/コピー/貼り付けする方法については、次を参照してください。[コピー、切り取り、および Functoid を貼り付ける方法](../core/how-to-copy-cut-and-paste-a-functoid.md)します。</span><span class="sxs-lookup"><span data-stu-id="e4c8c-117">For information about how to cut/copy/paste a functoid, see [How to Copy, Cut, and Paste a Functoid](../core/how-to-copy-cut-and-paste-a-functoid.md).</span></span> <span data-ttu-id="e4c8c-118">切り取り/コピー/貼り付けの functoid とリンクする方法の詳細については、次を参照してください。[方法は、コピー、切り取り、貼り付けのリンクおよび Functoid](../core/how-to-copy-cut-and-paste-links-and-functoids.md)します。</span><span class="sxs-lookup"><span data-stu-id="e4c8c-118">For more information about how to cut/copy/paste functoid and link, see [How to Copy, Cut, and Paste Links and Functoids](../core/how-to-copy-cut-and-paste-links-and-functoids.md).</span></span>  
  
-   <span data-ttu-id="e4c8c-119">ソース ノードをリンクする、ターゲット ノードまたは functoid を別の functoid、functoid または functoid からターゲット ノードへのソース ノード</span><span class="sxs-lookup"><span data-stu-id="e4c8c-119">Linking a source node to a target node, or a source node to a functoid, a functoid to another functoid, or a functoid to a target node</span></span>  
  
-   <span data-ttu-id="e4c8c-120">Functoid やリンクを削除しています</span><span class="sxs-lookup"><span data-stu-id="e4c8c-120">Deleting functoids and/or links</span></span>  
  
-   <span data-ttu-id="e4c8c-121">選択したリンクおよび functoid を別のグリッド ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="e4c8c-121">Moving selected links and functoids to another grid page</span></span>  
  
-   <span data-ttu-id="e4c8c-122">追加、移動、順序変更、またはグリッド ページを削除します。</span><span class="sxs-lookup"><span data-stu-id="e4c8c-122">Adding, moving, reordering, or deleting grid pages</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e4c8c-123">移動、順序変更、または、グリッド ページの削除が参照を追加する方法については、[グリッド ページの順序を変更する方法](../core/how-to-reorder-grid-pages.md)します。</span><span class="sxs-lookup"><span data-stu-id="e4c8c-123">For information on adding, moving, reordering, or deleting grid pages, see [How to Reorder Grid Pages](../core/how-to-reorder-grid-pages.md).</span></span>  
  
-   <span data-ttu-id="e4c8c-124">マップを作成するときに、元と送信先スキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c8c-124">Selecting source and destination schemas while creating a map</span></span>  
  
-   <span data-ttu-id="e4c8c-125">送信元/送信先スキーマの置換</span><span class="sxs-lookup"><span data-stu-id="e4c8c-125">Replacing source/destination schema</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e4c8c-126">送信元/送信先スキーマの置換する方法については、次を参照してください。[スキーマの置換方法](../core/how-to-replace-schemas.md)します。</span><span class="sxs-lookup"><span data-stu-id="e4c8c-126">For information on how to replace source/destination schema, see [How to Replace Schemas](../core/how-to-replace-schemas.md).</span></span>  
  
-   <span data-ttu-id="e4c8c-127">Functoid の入力パラメーターを構成します。</span><span class="sxs-lookup"><span data-stu-id="e4c8c-127">Configuring input parameters for functoids</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e4c8c-128">詳細については、次を参照してください。 [Functoid 入力パラメーターを構成する方法](../core/how-to-configure-functoid-input-parameters.md)します。</span><span class="sxs-lookup"><span data-stu-id="e4c8c-128">For more information, see [How to Configure Functoid Input Parameters](../core/how-to-configure-functoid-input-parameters.md).</span></span>  
  
-   <span data-ttu-id="e4c8c-129">リンクのラベルの設定/編集</span><span class="sxs-lookup"><span data-stu-id="e4c8c-129">Setting/editing labels for links</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e4c8c-130">詳細については、次を参照してください。[リンクにラベルを付ける方法](../core/how-to-label-a-link.md)します。</span><span class="sxs-lookup"><span data-stu-id="e4c8c-130">For more information, see [How to Label a Link](../core/how-to-label-a-link.md).</span></span>  
  
-   <span data-ttu-id="e4c8c-131">Functoid のラベルの設定/編集およびコメント</span><span class="sxs-lookup"><span data-stu-id="e4c8c-131">Setting/editing labels and/or comments for functoids</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e4c8c-132">詳細については、次を参照してください。[方法、Functoid ラベルとコメント](../core/how-to-label-and-comment-a-functoid.md)します。</span><span class="sxs-lookup"><span data-stu-id="e4c8c-132">For more information, see [How to Label and Comment a Functoid](../core/how-to-label-and-comment-a-functoid.md).</span></span>  
  
-   <span data-ttu-id="e4c8c-133">マッパー グリッドのリンクとスクリプトの種類の優先順位のプロパティの名前空間を無視します。</span><span class="sxs-lookup"><span data-stu-id="e4c8c-133">Ignore Namespaces for Links and Script Type Precedence properties for Mapper grid.</span></span>  
  
-   <span data-ttu-id="e4c8c-134">ノードまたは functoid を別のノードまたは functoid からのリンクの 1 つの終点をドラッグしてリンクの置き換えです。</span><span class="sxs-lookup"><span data-stu-id="e4c8c-134">Replacing a link by dragging one end point of a link from a node or functoid to anther node or functoid.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e4c8c-135">詳細については、次を参照してください。[リンクを作成する方法](../core/how-to-create-links.md)します。</span><span class="sxs-lookup"><span data-stu-id="e4c8c-135">For more information, see [How to Create Links](../core/how-to-create-links.md).</span></span>  
  
-   <span data-ttu-id="e4c8c-136">複数の変更を実行する、**構成\<Functoid\> Functoid**ダイアログ ボックスで、1 つの操作として扱われます。</span><span class="sxs-lookup"><span data-stu-id="e4c8c-136">Performing multiple modifications in the **Configure \<Functoid\> Functoid** dialog box, which is treated as a single operation.</span></span>  
  
-   <span data-ttu-id="e4c8c-137">Functoid およびマッパー グリッド内のリンクをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="e4c8c-137">Dragging functoid(s) and/or link(s) within the Mapper grid.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e4c8c-138">詳細については、次を参照してください。[グリッド ページ間のリレーションシップを移動する方法](../core/how-to-move-a-relationship-between-grid-pages.md)します。</span><span class="sxs-lookup"><span data-stu-id="e4c8c-138">For more information, see [How to Move a Relationship Between Grid Pages](../core/how-to-move-a-relationship-between-grid-pages.md).</span></span>  
  
## <a name="how-can-you-undoredo-any-operation"></a><span data-ttu-id="e4c8c-139">方法を元に戻す/やり直す操作でしょうか。</span><span class="sxs-lookup"><span data-stu-id="e4c8c-139">How can you undo/redo any operation?</span></span>  
 <span data-ttu-id="e4c8c-140">元に戻す/やり直す操作は次の方法のいずれかで。</span><span class="sxs-lookup"><span data-stu-id="e4c8c-140">You can undo/redo an operation in one of the following ways:</span></span>  
  
-   <span data-ttu-id="e4c8c-141">Visual studio の**編集**メニュー。</span><span class="sxs-lookup"><span data-stu-id="e4c8c-141">From the Visual Studio’s **Edit** menu.</span></span>  
  
-   <span data-ttu-id="e4c8c-142">ツールバーの取り消しとやり直しのアイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c8c-142">Clicking the undo and redo icons on the toolbar.</span></span>  
  
-   <span data-ttu-id="e4c8c-143">元に戻すには、CTRL + Z と再実行では、CTRL + Y キーを押します。</span><span class="sxs-lookup"><span data-stu-id="e4c8c-143">Pressing CTRL+Z for undo and CTRL+Y for redo.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4c8c-144">参照</span><span class="sxs-lookup"><span data-stu-id="e4c8c-144">See Also</span></span>  
 [<span data-ttu-id="e4c8c-145">グリッド ページの操作</span><span class="sxs-lookup"><span data-stu-id="e4c8c-145">Working with Grid Pages</span></span>](../core/working-with-grid-pages.md)