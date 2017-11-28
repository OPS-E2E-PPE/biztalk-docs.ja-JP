---
title: "グリッド ページ間のリレーションシップを移動する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.mapper.movetopage
ms.assetid: 185add4d-c876-44b6-b6e0-71c15a9b7c26
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5737adcb9159568bfea7c7cdde9dff8015b19706
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-move-a-relationship-between-grid-pages"></a><span data-ttu-id="38160-102">グリッド ページ間で関係を移動する方法</span><span class="sxs-lookup"><span data-stu-id="38160-102">How to Move a Relationship Between Grid Pages</span></span>
<span data-ttu-id="38160-103">大規模なマップには多数の Functoid とリンクが含まれる場合があり、複数の Functoid に参加しているリンクを識別することが困難です。</span><span class="sxs-lookup"><span data-stu-id="38160-103">Large maps include many sets of functoids and links, which can make it difficult for you to identify the links joining multiple functoids.</span></span> <span data-ttu-id="38160-104">このようなシナリオでは、類似した一連の Functoid とリンクを別のグリッド ページに移動してマップを読みやすくすることができます。</span><span class="sxs-lookup"><span data-stu-id="38160-104">In such a scenario, you might want to move a similar set of functoids and links to a different grid page to make the map more readable.</span></span> <span data-ttu-id="38160-105">このトピックでは、この操作の手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="38160-105">This topic provides step-by-step instructions to perform the operation.</span></span>  
  
 <span data-ttu-id="38160-106">同じマップ内に限り、次のいずれかの方法で 1 つのグリッド ページから別のグリッド ページに関係を移動できます。</span><span class="sxs-lookup"><span data-stu-id="38160-106">You can move a relationship from one grid page to another, in the same map only, in one of the following ways:</span></span>  
  
-   <span data-ttu-id="38160-107">使用して、**ページに移動する** ダイアログ ボックス</span><span class="sxs-lookup"><span data-stu-id="38160-107">Using the **Move to Page** dialog box</span></span>  
  
-   <span data-ttu-id="38160-108">リボンで選択した Functoid (およびリンク) のドラッグ アンド ドロップを使用する</span><span class="sxs-lookup"><span data-stu-id="38160-108">Using the drag-and-drop of the ribbon-selected functoid(s) (and links)</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="38160-109">1 つ以上の Functoid とそのリンクを移動できます。</span><span class="sxs-lookup"><span data-stu-id="38160-109">You can move one or more functoids and their links.</span></span> <span data-ttu-id="38160-110">関係を移動する場合、その関係に関連付けられたラベル、コメント、および定数値は (正しいプレースホルダーと共に) 維持されます。</span><span class="sxs-lookup"><span data-stu-id="38160-110">When you move a relationship, the labels, comments, and the constant values (along with the correct place holders) associated with that relationship are retained.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="38160-111">リンクだけを別のグリッド ペインにドラッグ アンド ドロップすることはできません。</span><span class="sxs-lookup"><span data-stu-id="38160-111">You cannot drag-and-drop only links to another grid page.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="38160-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="38160-112">Prerequisites</span></span>  
 <span data-ttu-id="38160-113">これらの手順では、BizTalk マッパーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="38160-113">These instructions require that BizTalk Mapper is running.</span></span>  
  
### <a name="to-move-a-relationship-using-move-to-page-dialog-box"></a><span data-ttu-id="38160-114">[ページに移動] ダイアログ ボックスを使用して関係を移動するには</span><span class="sxs-lookup"><span data-stu-id="38160-114">To move a relationship using Move To Page dialog box</span></span>  
  
1.  <span data-ttu-id="38160-115">マップで、リレーションシップの移動元のグリッド ページを選択します。</span><span class="sxs-lookup"><span data-stu-id="38160-115">On the map, select the grid page from which you want to move a relationship.</span></span>  
  
2.  <span data-ttu-id="38160-116">Functoid またはリンクに移動し、をクリックするリレーションシップを右クリックして**ページに移動する**です。</span><span class="sxs-lookup"><span data-stu-id="38160-116">Right-click a functoid or a link in the relationship you want to move and then click **Move to Page**.</span></span> <span data-ttu-id="38160-117">選択されているすべてのマップ項目と共に関連するリンクと Functoid が移動されることを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="38160-117">A message saying that all the selected map items(s), along with related links and functoids, will be moved is displayed.</span></span> <span data-ttu-id="38160-118">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="38160-118">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="38160-119">Visual Studio のメニューで、メッセージのポップアップを無効にするには**ツール**、 をクリックして**オプション**、 をクリックして**BizTalk マッパー**をクリックして**全般**、ボックスをオフにし、**ページに移動**オプション。</span><span class="sxs-lookup"><span data-stu-id="38160-119">To disable the message popup, in the Visual Studio menu, go to **Tools**, click **Options**, click **BizTalk Mapper**, click **General**, and then uncheck the **Move to page** option.</span></span> <span data-ttu-id="38160-120">[全般] オプションの詳細については、次を参照してください。 [BizTalk マッパーの全般的な設定をカスタマイズする方法](../core/how-to-customize-general-settings-in-biztalk-mapper.md)です。</span><span class="sxs-lookup"><span data-stu-id="38160-120">For more information about general options, see [How to Customize General Settings in BizTalk Mapper](../core/how-to-customize-general-settings-in-biztalk-mapper.md).</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="38160-121">または、CTRL + M, CTRL + M を開くにをキー、**ページに移動する** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="38160-121">Alternatively, you can press CTRL+M, CTRL+M to open the **Move to Page** dialog box.</span></span> <span data-ttu-id="38160-122">マッパーのショートカットの一覧は、次を参照してください。 [BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)です。</span><span class="sxs-lookup"><span data-stu-id="38160-122">For a list of Mapper shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
     <span data-ttu-id="38160-123">![選択した関係を新しいページに移動](../core/media/moving-a-functoid-new.gif "Moving_a_functoid_new")</span><span class="sxs-lookup"><span data-stu-id="38160-123">![Moving selected relationship to a new page](../core/media/moving-a-functoid-new.gif "Moving_a_functoid_new")</span></span>  
  
3.  <span data-ttu-id="38160-124">**ページに移動する** ダイアログ ボックスで、クリックして、リレーションシップを移動するターゲットのグリッド ページの選択**OK**です。</span><span class="sxs-lookup"><span data-stu-id="38160-124">In the **Move to Page** dialog box, select the target grid page to which you want to move the relationship, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="38160-125">選択して、新しいページを作成することもできます。  **\*(新しいページの追加)**、クリックし、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="38160-125">You can also create a new page by selecting **\*(add new page)**, and then clicking **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="38160-126">または、Ctrl キーを押しながら M キーを押し、次に Ctrl キーを押しながら A キーを押して、マップに新しいグリッド ページを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="38160-126">Alternatively, you can press CTRL+M, CTRL+A to add a new grid page in a map.</span></span> <span data-ttu-id="38160-127">マッパーのショートカットの一覧は、次を参照してください。 [BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)です。</span><span class="sxs-lookup"><span data-stu-id="38160-127">For a list of Mapper shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
     <span data-ttu-id="38160-128">![ターゲットのグリッド ページの選択](../core/media/moving-a-functoid-step4.gif "Moving_a_functoid_Step4")</span><span class="sxs-lookup"><span data-stu-id="38160-128">![Selecting the target grid page](../core/media/moving-a-functoid-step4.gif "Moving_a_functoid_Step4")</span></span>  
  
     <span data-ttu-id="38160-129">選択した Functoid とリンク、および関連の Functoid およびリンクが、新しいグリッド ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="38160-129">The selected functoid/link, along with the related functoids and links, is moved to the new grid page.</span></span> <span data-ttu-id="38160-130">次のページは、選択した関係 (ページ 3 にあった) がページ 1 に移動したところを示しています。</span><span class="sxs-lookup"><span data-stu-id="38160-130">The figure below shows the selected relationship (which was in Page 3) moved to Page 1.</span></span>  
  
     <span data-ttu-id="38160-131">![選択したリレーションシップが新しいページに移動](../core/media/moving-a-functoid-new2.gif "Moving_a_functoid_new2")</span><span class="sxs-lookup"><span data-stu-id="38160-131">![Selected relationship is moved to a new page](../core/media/moving-a-functoid-new2.gif "Moving_a_functoid_new2")</span></span>  
  
### <a name="to-move-a-relationship-using-drag-and-drop"></a><span data-ttu-id="38160-132">ドラッグ アンド ドロップを使用して関係を移動するには</span><span class="sxs-lookup"><span data-stu-id="38160-132">To move a relationship using drag-and-drop</span></span>  
  
1.  <span data-ttu-id="38160-133">マップで、リレーションシップの移動元のグリッド ページを選択します。</span><span class="sxs-lookup"><span data-stu-id="38160-133">On the map, select the grid page from which you want to move a relationship.</span></span>  
  
2.  <span data-ttu-id="38160-134">別のグリッド ページに移動する Functoid (およびリンク) を選択します。</span><span class="sxs-lookup"><span data-stu-id="38160-134">Select the functoid(s) (and link(s)) you want to move to another grid page.</span></span> <span data-ttu-id="38160-135">この操作により、選択した Functoid に接続するすべてのリンクが再帰的に選択されます。</span><span class="sxs-lookup"><span data-stu-id="38160-135">This recursively selects all links that connect to the functoids in the selection.</span></span>  
  
3.  <span data-ttu-id="38160-136">選択した関係を移動先のページ (ページ タブ上) にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="38160-136">Drag the selection to the page (on the page tab) where you want to move the relationship.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="38160-137">手順 4. を実行するまでマウスを放さないでください。</span><span class="sxs-lookup"><span data-stu-id="38160-137">Do not release the mouse till you perform step 4.</span></span>  
  
4.  <span data-ttu-id="38160-138">移動先のグリッド ページにフォーカスが移ったら (前の図では、ページ 1 にフォーカスがあります)、グリッド ページの空のセルに選択したものをドロップします。</span><span class="sxs-lookup"><span data-stu-id="38160-138">When the target grid page comes into focus (in the above figure, Page 1 is in focus), drop the selection on an empty cell on the grid page.</span></span> <span data-ttu-id="38160-139">選択した関係が新しいグリッド ページに移動しました。</span><span class="sxs-lookup"><span data-stu-id="38160-139">The selected relationship is moved to the new grid page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38160-140">参照</span><span class="sxs-lookup"><span data-stu-id="38160-140">See Also</span></span>  
 [<span data-ttu-id="38160-141">グリッド ページの操作</span><span class="sxs-lookup"><span data-stu-id="38160-141">Working with Grid Pages</span></span>](../core/working-with-grid-pages.md)