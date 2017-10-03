---
title: "元に戻すまたはユーザーの操作を再実行する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1cb3708e-a9c2-4795-aba0-9c6d9635e08c
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6f47071ee003a896b66120c0fd81a121ab73230
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-undo-or-redo-user-operations"></a><span data-ttu-id="73151-102">ユーザー操作の取り消しまたはやり直しの方法</span><span class="sxs-lookup"><span data-stu-id="73151-102">How to Undo or Redo User Operations</span></span>
<span data-ttu-id="73151-103">元に戻す/やり直しのサポートも、BizTalk マッパーに用意されている便利な操作です。</span><span class="sxs-lookup"><span data-stu-id="73151-103">The support for undo/redo is yet another usability aid provided by the BizTalk Mapper.</span></span> <span data-ttu-id="73151-104">自分が加えた変更が希望どおりでないか、誤って変更を加えた場合は、	元に戻すを使用して、変更を加えていない以前の状態に徐々に戻り、そこから操作を再開することができます。</span><span class="sxs-lookup"><span data-stu-id="73151-104">If you are not satisfied with modifications you have made, or if you have made a change by mistake, you can use undo to gradually come back to an earlier "untouched" state, and resume from there.</span></span> <span data-ttu-id="73151-105">やり直しを使用すると、元に戻した編集操作を再適用することができます。</span><span class="sxs-lookup"><span data-stu-id="73151-105">Redo allows you to reapply the editing actions that have been undone.</span></span> <span data-ttu-id="73151-106">このトピックでは、元に戻すかやり直すことができる操作に関する情報を示します。</span><span class="sxs-lookup"><span data-stu-id="73151-106">This topic provides information about the operations that you can undo/redo.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="73151-107">操作を元に戻すことができるのは、マップで少なくとも 1 つの編集操作を実行した場合のみです。</span><span class="sxs-lookup"><span data-stu-id="73151-107">You can undo an operation only when you have performed at least one edit operation on the map.</span></span> <span data-ttu-id="73151-108">やり直しは、元に戻すコマンドを使用していない限り使用できません。</span><span class="sxs-lookup"><span data-stu-id="73151-108">Redo is unavailable unless you have used the undo command.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="73151-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="73151-109">Prerequisites</span></span>  
 <span data-ttu-id="73151-110">これらの手順では、BizTalk マッパーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="73151-110">These instructions require that BizTalk Mapper is running.</span></span>  
  
## <a name="what-can-you-undoredo"></a><span data-ttu-id="73151-111">元に戻す/やり直しの対象となる操作</span><span class="sxs-lookup"><span data-stu-id="73151-111">What can you undo/redo?</span></span>  
 <span data-ttu-id="73151-112">元に戻す/やり直しの対象となるのは、すべての編集操作です。</span><span class="sxs-lookup"><span data-stu-id="73151-112">You can undo/redo all editing operations.</span></span> <span data-ttu-id="73151-113">それらの操作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="73151-113">The operations that can be undone/redone are as follows:</span></span>  
  
-   <span data-ttu-id="73151-114">Functoid またはリンクの切り取り/コピー/貼り付け</span><span class="sxs-lookup"><span data-stu-id="73151-114">Cutting/copying/pasting functoids and/or link</span></span>  
  
     <span data-ttu-id="73151-115">単に選択してコピーするのでは、任意の数の項目 (リンクや Functoid) を取り消したり、やり直したりできません。</span><span class="sxs-lookup"><span data-stu-id="73151-115">You cannot undo or redo any number of items (links/functoids) by simply selecting and copying them.</span></span> <span data-ttu-id="73151-116">コピー機能ではマップ上の何も変更されません。</span><span class="sxs-lookup"><span data-stu-id="73151-116">Copy function does not change anything on the map.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="73151-117">Functoid の切り取り/コピー/貼り付けする方法については、次を参照してください。[コピー、切り取り、および Functoid を貼り付けする方法](../core/how-to-copy-cut-and-paste-a-functoid.md)です。</span><span class="sxs-lookup"><span data-stu-id="73151-117">For information about how to cut/copy/paste a functoid, see [How to Copy, Cut, and Paste a Functoid](../core/how-to-copy-cut-and-paste-a-functoid.md).</span></span> <span data-ttu-id="73151-118">切り取り/コピー/貼り付け functoid とリンクする方法の詳細については、次を参照してください。[方法は、コピー、切り取り、貼り付けリンク、および Functoid](../core/how-to-copy-cut-and-paste-links-and-functoids.md)です。</span><span class="sxs-lookup"><span data-stu-id="73151-118">For more information about how to cut/copy/paste functoid and link, see [How to Copy, Cut, and Paste Links and Functoids](../core/how-to-copy-cut-and-paste-links-and-functoids.md).</span></span>  
  
-   <span data-ttu-id="73151-119">送信元ノードから送信先ノード、送信元ノードから Functoid、Functoid から別の Functoid、または Functoid から送信先ノードへのリンク</span><span class="sxs-lookup"><span data-stu-id="73151-119">Linking a source node to a target node, or a source node to a functoid, a functoid to another functoid, or a functoid to a target node</span></span>  
  
-   <span data-ttu-id="73151-120">Functoid またはリンクの削除</span><span class="sxs-lookup"><span data-stu-id="73151-120">Deleting functoids and/or links</span></span>  
  
-   <span data-ttu-id="73151-121">別のグリッド ページへの選択したリンクおよび Functoid の移動</span><span class="sxs-lookup"><span data-stu-id="73151-121">Moving selected links and functoids to another grid page</span></span>  
  
-   <span data-ttu-id="73151-122">グリッド ページの追加、移動、順序変更、または削除</span><span class="sxs-lookup"><span data-stu-id="73151-122">Adding, moving, reordering, or deleting grid pages</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="73151-123">追加する方法については、移動、順序変更、削除するグリッド ページを参照してください[グリッド ページの順序を変更する方法](../core/how-to-reorder-grid-pages.md)です。</span><span class="sxs-lookup"><span data-stu-id="73151-123">For information on adding, moving, reordering, or deleting grid pages, see [How to Reorder Grid Pages](../core/how-to-reorder-grid-pages.md).</span></span>  
  
-   <span data-ttu-id="73151-124">マップ作成時における送信元スキーマおよび送信先スキーマの選択</span><span class="sxs-lookup"><span data-stu-id="73151-124">Selecting source and destination schemas while creating a map</span></span>  
  
-   <span data-ttu-id="73151-125">送信元/送信先スキーマの置換</span><span class="sxs-lookup"><span data-stu-id="73151-125">Replacing source/destination schema</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="73151-126">送信元/送信先スキーマの置換する方法については、次を参照してください。[スキーマの置換方法](../core/how-to-replace-schemas.md)です。</span><span class="sxs-lookup"><span data-stu-id="73151-126">For information on how to replace source/destination schema, see [How to Replace Schemas](../core/how-to-replace-schemas.md).</span></span>  
  
-   <span data-ttu-id="73151-127">Functoid の入力パラメーターの構成</span><span class="sxs-lookup"><span data-stu-id="73151-127">Configuring input parameters for functoids</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="73151-128">詳細については、次を参照してください。 [Functoid の入力パラメーターを構成する方法](../core/how-to-configure-functoid-input-parameters.md)です。</span><span class="sxs-lookup"><span data-stu-id="73151-128">For more information, see [How to Configure Functoid Input Parameters](../core/how-to-configure-functoid-input-parameters.md).</span></span>  
  
-   <span data-ttu-id="73151-129">リンクのラベルの設定/編集</span><span class="sxs-lookup"><span data-stu-id="73151-129">Setting/editing labels for links</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="73151-130">詳細については、次を参照してください。[リンクのラベルを付ける方法](../core/how-to-label-a-link.md)です。</span><span class="sxs-lookup"><span data-stu-id="73151-130">For more information, see [How to Label a Link](../core/how-to-label-a-link.md).</span></span>  
  
-   <span data-ttu-id="73151-131">Functoid のラベルおよびコメントの設定/編集</span><span class="sxs-lookup"><span data-stu-id="73151-131">Setting/editing labels and/or comments for functoids</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="73151-132">詳細については、次を参照してください。[方法、Functoid ラベルとコメント](../core/how-to-label-and-comment-a-functoid.md)です。</span><span class="sxs-lookup"><span data-stu-id="73151-132">For more information, see [How to Label and Comment a Functoid](../core/how-to-label-and-comment-a-functoid.md).</span></span>  
  
-   <span data-ttu-id="73151-133">マッパー グリッドに対する "リンクの Namespaces を無視する" および "スクリプトの種類の優先順位" プロパティ</span><span class="sxs-lookup"><span data-stu-id="73151-133">Ignore Namespaces for Links and Script Type Precedence properties for Mapper grid.</span></span>  
  
-   <span data-ttu-id="73151-134">あるノードまたは Functoid から別のノードまたは Functoid にリンクの 1 つの端点をドラッグすることによるリンクの置き換え</span><span class="sxs-lookup"><span data-stu-id="73151-134">Replacing a link by dragging one end point of a link from a node or functoid to anther node or functoid.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="73151-135">詳細については、次を参照してください。[リンクを作成する方法](../core/how-to-create-links.md)です。</span><span class="sxs-lookup"><span data-stu-id="73151-135">For more information, see [How to Create Links](../core/how-to-create-links.md).</span></span>  
  
-   <span data-ttu-id="73151-136">複数の変更を実行する、**構成\<Functoid > Functoid**  ダイアログ ボックスは、1 つの操作として扱われます。</span><span class="sxs-lookup"><span data-stu-id="73151-136">Performing multiple modifications in the **Configure \<Functoid> Functoid** dialog box, which is treated as a single operation.</span></span>  
  
-   <span data-ttu-id="73151-137">マッパー グリッド内での Functoid およびリンクのドラッグ</span><span class="sxs-lookup"><span data-stu-id="73151-137">Dragging functoid(s) and/or link(s) within the Mapper grid.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="73151-138">詳細については、次を参照してください。 [、リレーションシップのグリッド ページ間を移動する方法](../core/how-to-move-a-relationship-between-grid-pages.md)です。</span><span class="sxs-lookup"><span data-stu-id="73151-138">For more information, see [How to Move a Relationship Between Grid Pages](../core/how-to-move-a-relationship-between-grid-pages.md).</span></span>  
  
## <a name="how-can-you-undoredo-any-operation"></a><span data-ttu-id="73151-139">操作を元に戻す/やり直す方法</span><span class="sxs-lookup"><span data-stu-id="73151-139">How can you undo/redo any operation?</span></span>  
 <span data-ttu-id="73151-140">操作を元に戻すかやり直すには、次のいずれかの方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="73151-140">You can undo/redo an operation in one of the following ways:</span></span>  
  
-   <span data-ttu-id="73151-141">Visual studio の**編集**メニュー。</span><span class="sxs-lookup"><span data-stu-id="73151-141">From the Visual Studio’s **Edit** menu.</span></span>  
  
-   <span data-ttu-id="73151-142">ツール バーの [元に戻す] アイコンおよび [やり直す] アイコンをクリックする。</span><span class="sxs-lookup"><span data-stu-id="73151-142">Clicking the undo and redo icons on the toolbar.</span></span>  
  
-   <span data-ttu-id="73151-143">Ctrl + Z キー (元に戻す場合) および Ctrl + Y キー (やり直す場合) を押す。</span><span class="sxs-lookup"><span data-stu-id="73151-143">Pressing CTRL+Z for undo and CTRL+Y for redo.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73151-144">参照</span><span class="sxs-lookup"><span data-stu-id="73151-144">See Also</span></span>  
 [<span data-ttu-id="73151-145">グリッド ページの操作</span><span class="sxs-lookup"><span data-stu-id="73151-145">Working with Grid Pages</span></span>](../core/working-with-grid-pages.md)