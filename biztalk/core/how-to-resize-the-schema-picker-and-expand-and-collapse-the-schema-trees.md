---
title: スキーマの選択のサイズを変更しを展開し、スキーマ ツリーを折りたたむ方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 267ea17d-54fe-4031-a044-719606489f24
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 682077ffc044c3f293d5bf7f2d3c2a1d81a4c918
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993051"
---
# <a name="how-to-resize-the-schema-picker-and-expand-and-collapse-the-schema-trees"></a><span data-ttu-id="3e983-102">スキーマの選択のサイズを変更しを展開し、スキーマ ツリーを折りたたむ方法</span><span class="sxs-lookup"><span data-stu-id="3e983-102">How to resize the schema picker, and expand and collapse the schema trees</span></span>
<span data-ttu-id="3e983-103">BizTalk マップを展開する際、さまざまなスキーマ ノードの表示または非表示を行うため、送信元スキーマ ツリーおよび送信先スキーマ ツリーの展開および折りたたみが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="3e983-103">When developing BizTalk maps, you are likely to need to expand and collapse the source and destination schema trees to expose or to hide the various schema nodes.</span></span> <span data-ttu-id="3e983-104">このトピックの「スキーマの選択のサイズを変更して、スキーマ ツリーを閉じたりする手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="3e983-104">This topic provides step-by-step instructions to resize the schema picker, and to expand and collapse the schema tree.</span></span>  

## <a name="resize-the-schema-picker"></a><span data-ttu-id="3e983-105">スキーマの選択のサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="3e983-105">Resize the schema picker</span></span>

<span data-ttu-id="3e983-106">マップを作成するときは、送信元スキーマと送信先スキーマを追加します。</span><span class="sxs-lookup"><span data-stu-id="3e983-106">When you create a map, you add a source schema, and a destination schema.</span></span> <span data-ttu-id="3e983-107">追加またはスキーマを置換するときは、BizTalk 型の選択ウィンドウが開き、スキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="3e983-107">When you add or replace a schema, the BizTalk Type Picker window opens, and you select your schema.</span></span> 

<span data-ttu-id="3e983-108">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** 、この型の選択 ウィンドウのサイズを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="3e983-108">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**, you can resize this Type Picker window.</span></span> <span data-ttu-id="3e983-109">この機能を使用して、スキーマの完全名を表示できます。</span><span class="sxs-lookup"><span data-stu-id="3e983-109">This feature allows you to see the full name of your schema.</span></span>

1. <span data-ttu-id="3e983-110">マップで、次のように選択します。**送信先スキーマを開く**、または**ソース スキーマを開く**します。</span><span class="sxs-lookup"><span data-stu-id="3e983-110">In your map, select **Open Destination Schema**, or **Open Source Schema**.</span></span>
2. <span data-ttu-id="3e983-111">**BizTalk 型の選択**ウィンドウで、ウィンドウのサイズを増減するドラッグ右下隅。</span><span class="sxs-lookup"><span data-stu-id="3e983-111">In the **BizTalk Type Picker** window, drag the bottom-right corner to increase or decrease the window size.</span></span>
  
## <a name="expand-all-or-part-of-a-schema-tree"></a><span data-ttu-id="3e983-112">スキーマ ツリーの一部またはすべてを展開します。</span><span class="sxs-lookup"><span data-stu-id="3e983-112">Expand all or part of a schema tree</span></span>  
  
1.  <span data-ttu-id="3e983-113">スキーマ ツリーをすべて展開するノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="3e983-113">Select the node under which you want to completely expand the schema tree.</span></span>  
  
     <span data-ttu-id="3e983-114">ノードの横に正符号 (+) アイコンまたは負符号 (-) アイコンがあるノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="3e983-114">The selected node must be a node with a plus (+) or minus (-) icon next to it.</span></span>  
  
2.  <span data-ttu-id="3e983-115">**BizTalk**メニュー、またはそのノードのショートカット メニュー、**ツリー ノードの展開**。</span><span class="sxs-lookup"><span data-stu-id="3e983-115">On the **BizTalk** menu, or on the shortcut menu for that node, click **Expand Tree Node**.</span></span> <span data-ttu-id="3e983-116">選択したノードの下にあるすべてのノードが展開されます。</span><span class="sxs-lookup"><span data-stu-id="3e983-116">All nodes below the selected node are completely expanded.</span></span>  
  
     <span data-ttu-id="3e983-117">選択したノードの下のスキーマ ツリーが既に展開されている場合、**ツリー ノードの展開**メニュー項目が無効になっています。</span><span class="sxs-lookup"><span data-stu-id="3e983-117">If the schema tree below the selected node is already completely expanded, the **Expand Tree Node** menu item is disabled.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3e983-118">または、Ctrl キーを押しながら M キーを押し、次に Ctrl キーを押しながら E キーを押して、スキーマ ツリー ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="3e983-118">Alternatively you can press CTRL+M, E to expand the schema tree nodes.</span></span> <span data-ttu-id="3e983-119">キーボード ショートカットの一覧は、[BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e983-119">For a list of keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3e983-120">大規模で複雑なスキーマをクリックすると**ツリー ノードの展開**で複合型を含むノードをスキーマ内のいくつかのノードが折りたたまれた状態で残る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3e983-120">In a large and complex schema, when you click **Expand Tree Node** on a node that contains complex types, some nodes in the schema may remain in the collapsed state.</span></span> <span data-ttu-id="3e983-121">これは、再帰処理が特定の複合型を最初に検出したノードだけを展開するためです。</span><span class="sxs-lookup"><span data-stu-id="3e983-121">This is because the recursive process expands only the first occurrence of a given complex type.</span></span> <span data-ttu-id="3e983-122">同じ型を含む他のノードは、手動で展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e983-122">You must manually expand later occurrences of the same type.</span></span> <span data-ttu-id="3e983-123">大きくて複雑なスキーマのノードを展開するときのパフォーマンスを最適化するために、このような動作になっています。</span><span class="sxs-lookup"><span data-stu-id="3e983-123">This behavior is designed to optimize performance when expanding nodes in large and complex schemas.</span></span>  
  
## <a name="collapse-all-or-part-of-a-schema-tree"></a><span data-ttu-id="3e983-124">スキーマ ツリーの一部またはすべてを折りたたむ</span><span class="sxs-lookup"><span data-stu-id="3e983-124">Collapse all or part of a schema tree</span></span>  
  
1. <span data-ttu-id="3e983-125">スキーマ ツリーをすべて折りたたむノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="3e983-125">Select the node under which you want to completely collapse the schema tree.</span></span>  
  
    <span data-ttu-id="3e983-126">ノードの横に正符号 (+) アイコンまたは負符号 (-) アイコンがあるノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="3e983-126">The selected node must be a node with a plus (+) or minus (-) icon next to it.</span></span>  
  
2. <span data-ttu-id="3e983-127">**BizTalk**メニュー、またはそのノードのショートカット メニュー、**ツリー ノードの折りたたみ**します。</span><span class="sxs-lookup"><span data-stu-id="3e983-127">On the **BizTalk** menu, or on the shortcut menu for that node, click **Collapse Tree Node**.</span></span>  
  
    <span data-ttu-id="3e983-128">選択したノードの下にあるすべてのノードが折りたたまれます。</span><span class="sxs-lookup"><span data-stu-id="3e983-128">All nodes below the selected node are completely collapsed.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="3e983-129">または、Ctrl キーを押しながら M、C キーを押して、スキーマ ツリー ノードを折りたたみます。</span><span class="sxs-lookup"><span data-stu-id="3e983-129">Alternatively you can press CTRL+M, C to collapse the schema tree nodes.</span></span> <span data-ttu-id="3e983-130">キーボード ショートカットの一覧は、[BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e983-130">For a list of keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
    <span data-ttu-id="3e983-131">選択したノードの下のスキーマ ツリーが既に折りたたまれている場合、**ツリー ノードの折りたたみ**メニュー項目が無効になっています。</span><span class="sxs-lookup"><span data-stu-id="3e983-131">If the schema tree below the selected node is already collapsed, the **Collapse Tree Node** menu item is disabled.</span></span>  
  
   <span data-ttu-id="3e983-132">この手順は、選択したノードの下にある各ノードの展開設定および折りたたみ設定を維持しません。</span><span class="sxs-lookup"><span data-stu-id="3e983-132">This operation will not remember the individual expand and collapse settings of the nodes below the selected node.</span></span> <span data-ttu-id="3e983-133">折りたたまれたノードを再度展開すると、以前の設定が失われているので、下位のスキーマ ツリーをノードごとに展開するか、スキーマ ツリー全体を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e983-133">When you re-expand the collapsed node, previous settings are lost, and you must expand the schema tree below that point node-by-node, or expand it entirely.</span></span>  
  
### <a name="expand-a-node"></a><span data-ttu-id="3e983-134">ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="3e983-134">Expand a node</span></span>
  
- <span data-ttu-id="3e983-135">展開するノードの横の正符号 (+) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e983-135">Click the plus (+) icon next to the node you want to expand.</span></span>  
  
  <span data-ttu-id="3e983-136">選択したノードが展開されます。</span><span class="sxs-lookup"><span data-stu-id="3e983-136">The selected node is expanded.</span></span> <span data-ttu-id="3e983-137">子孫のノードを展開または折りたたまれているかどうかは、選択したノードが折りたたまれている方法、および以前の展開に依存し、折りたたみ設定。</span><span class="sxs-lookup"><span data-stu-id="3e983-137">Whether or not its descendent nodes are expanded or collapsed depends on how the selected node was collapsed and their previous expand and collapse settings.</span></span>  
  
### <a name="collapse-a-node"></a><span data-ttu-id="3e983-138">ノードを折りたたむ</span><span class="sxs-lookup"><span data-stu-id="3e983-138">Collapse a node</span></span>
  
- <span data-ttu-id="3e983-139">折りたたむノードの横の負符号 (-) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e983-139">Click the minus (-) icon next to the node you want to collapse.</span></span>  
  
  <span data-ttu-id="3e983-140">選択したノードが折りたたまれます。</span><span class="sxs-lookup"><span data-stu-id="3e983-140">The selected node is collapsed.</span></span>  
  
  <span data-ttu-id="3e983-141">この手順は、選択したノードの下にある各ノードの展開設定および折りたたみ設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="3e983-141">This operation will remember the individual expand and collapse settings of the nodes below the selected node.</span></span> <span data-ttu-id="3e983-142">正符号 (+) アイコンで折りたたまれたノードを再度展開すると、以前の設定が失われないので、下位のスキーマ ツリーは、以前の状態になります。</span><span class="sxs-lookup"><span data-stu-id="3e983-142">When you re-expand the collapsed node by using the plus (+) icon, the previous individual settings are not lost, and the schema tree below that point returns to its previous state.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e983-143">参照</span><span class="sxs-lookup"><span data-stu-id="3e983-143">See Also</span></span>  
 [<span data-ttu-id="3e983-144">BizTalk マッパーの使用</span><span class="sxs-lookup"><span data-stu-id="3e983-144">Using BizTalk Mapper</span></span>](../core/using-biztalk-mapper.md)