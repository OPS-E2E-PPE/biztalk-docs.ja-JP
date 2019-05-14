---
title: グリッド ページ間のリレーションシップを移動する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mapper.movetopage
ms.assetid: 185add4d-c876-44b6-b6e0-71c15a9b7c26
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da495b073df7f76ba60946f66a4a40b697c25793
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335973"
---
# <a name="how-to-move-a-relationship-between-grid-pages"></a><span data-ttu-id="ab371-102">グリッド ページ間のリレーションシップを移動する方法</span><span class="sxs-lookup"><span data-stu-id="ab371-102">How to Move a Relationship Between Grid Pages</span></span>
<span data-ttu-id="ab371-103">大規模なマップは、多くの functoid とリンクで、複数の functoid に参加するリンクを識別するための難しいことがあります。</span><span class="sxs-lookup"><span data-stu-id="ab371-103">Large maps include many sets of functoids and links, which can make it difficult for you to identify the links joining multiple functoids.</span></span> <span data-ttu-id="ab371-104">このようなシナリオでは、functoid およびリンクのようなセットは、マップを読みやすくする別のグリッド ページに移動する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ab371-104">In such a scenario, you might want to move a similar set of functoids and links to a different grid page to make the map more readable.</span></span> <span data-ttu-id="ab371-105">このトピックで、操作を実行する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="ab371-105">This topic provides step-by-step instructions to perform the operation.</span></span>  
  
 <span data-ttu-id="ab371-106">間のみ、同じマップ内の 1 つのグリッド ページからリレーションシップを移動するには、次の方法のいずれかで。</span><span class="sxs-lookup"><span data-stu-id="ab371-106">You can move a relationship from one grid page to another, in the same map only, in one of the following ways:</span></span>  
  
-   <span data-ttu-id="ab371-107">使用して、**ページに移動する** ダイアログ ボックス</span><span class="sxs-lookup"><span data-stu-id="ab371-107">Using the **Move to Page** dialog box</span></span>  
  
-   <span data-ttu-id="ab371-108">ドラッグ アンド ドロップのリボンで選択した functoid (およびリンク) を使用します。</span><span class="sxs-lookup"><span data-stu-id="ab371-108">Using the drag-and-drop of the ribbon-selected functoid(s) (and links)</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ab371-109">1 つまたは複数の functoid とそのリンクを移動することができます。</span><span class="sxs-lookup"><span data-stu-id="ab371-109">You can move one or more functoids and their links.</span></span> <span data-ttu-id="ab371-110">リレーションシップ、ラベル、コメント、および (正しいプレース ホルダー) と定数の値を移動すると関連付けられているリレーションシップが保持されます。</span><span class="sxs-lookup"><span data-stu-id="ab371-110">When you move a relationship, the labels, comments, and the constant values (along with the correct place holders) associated with that relationship are retained.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ab371-111">別のグリッド ページにのみリンクをドラッグ アンド ドロップすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ab371-111">You cannot drag-and-drop only links to another grid page.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ab371-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="ab371-112">Prerequisites</span></span>  
 <span data-ttu-id="ab371-113">これらの手順では、BizTalk マッパーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab371-113">These instructions require that BizTalk Mapper is running.</span></span>  
  
### <a name="to-move-a-relationship-using-move-to-page-dialog-box"></a><span data-ttu-id="ab371-114">ページに移動 ダイアログ ボックスを使用してリレーションシップを移動するには</span><span class="sxs-lookup"><span data-stu-id="ab371-114">To move a relationship using Move To Page dialog box</span></span>  
  
1.  <span data-ttu-id="ab371-115">マップでは、関係を移動するグリッド ページを選択します。</span><span class="sxs-lookup"><span data-stu-id="ab371-115">On the map, select the grid page from which you want to move a relationship.</span></span>  
  
2.  <span data-ttu-id="ab371-116">Functoid またはリンクをクリックして移動するリレーションシップを右クリックして**ページに移動する**します。</span><span class="sxs-lookup"><span data-stu-id="ab371-116">Right-click a functoid or a link in the relationship you want to move and then click **Move to Page**.</span></span> <span data-ttu-id="ab371-117">すべて、選択したマップ項目 (s) との関連リンクと functoid が移動されることを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ab371-117">A message saying that all the selected map items(s), along with related links and functoids, will be moved is displayed.</span></span> <span data-ttu-id="ab371-118">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ab371-118">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ab371-119">Visual Studio のメニューで、メッセージのポップアップを無効にするには**ツール**、 をクリックして**オプション**、 をクリックして**BizTalk マッパー**、 をクリックして**全般**、オフにし、**ページに移動**オプション。</span><span class="sxs-lookup"><span data-stu-id="ab371-119">To disable the message popup, in the Visual Studio menu, go to **Tools**, click **Options**, click **BizTalk Mapper**, click **General**, and then uncheck the **Move to page** option.</span></span> <span data-ttu-id="ab371-120">[全般] オプションの詳細については、次を参照してください。 [BizTalk マッパーの全般設定をカスタマイズする方法](../core/how-to-customize-general-settings-in-biztalk-mapper.md)します。</span><span class="sxs-lookup"><span data-stu-id="ab371-120">For more information about general options, see [How to Customize General Settings in BizTalk Mapper](../core/how-to-customize-general-settings-in-biztalk-mapper.md).</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="ab371-121">または、CTRL + M, CTRL + M を開くをキー、**ページに移動する** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="ab371-121">Alternatively, you can press CTRL+M, CTRL+M to open the **Move to Page** dialog box.</span></span> <span data-ttu-id="ab371-122">マッパーのショートカットの一覧は、次を参照してください。 [BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)します。</span><span class="sxs-lookup"><span data-stu-id="ab371-122">For a list of Mapper shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
     <span data-ttu-id="ab371-123">![選択した関係を新しいページに移動](../core/media/moving-a-functoid-new.gif "Moving_a_functoid_new")</span><span class="sxs-lookup"><span data-stu-id="ab371-123">![Moving selected relationship to a new page](../core/media/moving-a-functoid-new.gif "Moving_a_functoid_new")</span></span>  
  
3.  <span data-ttu-id="ab371-124">**ページに移動する** ダイアログ ボックスで、リレーションシップを移動し、クリックするターゲットのグリッド ページを選択します。 **OK**。</span><span class="sxs-lookup"><span data-stu-id="ab371-124">In the **Move to Page** dialog box, select the target grid page to which you want to move the relationship, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ab371-125">選択して、新しいページを作成することもできます。  **\*(新しいページを追加)**、 をクリックし、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="ab371-125">You can also create a new page by selecting **\*(add new page)**, and then clicking **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ab371-126">または、CTRL + M, CTRL + A マップで新しいグリッド ページを追加するキーを押すことができます。</span><span class="sxs-lookup"><span data-stu-id="ab371-126">Alternatively, you can press CTRL+M, CTRL+A to add a new grid page in a map.</span></span> <span data-ttu-id="ab371-127">マッパーのショートカットの一覧は、次を参照してください。 [BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)します。</span><span class="sxs-lookup"><span data-stu-id="ab371-127">For a list of Mapper shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
     <span data-ttu-id="ab371-128">![ターゲットのグリッド ページの選択](../core/media/moving-a-functoid-step4.gif "Moving_a_functoid_Step4")</span><span class="sxs-lookup"><span data-stu-id="ab371-128">![Selecting the target grid page](../core/media/moving-a-functoid-step4.gif "Moving_a_functoid_Step4")</span></span>  
  
     <span data-ttu-id="ab371-129">関連の functoid およびリンクと共に選択した functoid/リンクでは、新しいグリッド ページに移動されます。</span><span class="sxs-lookup"><span data-stu-id="ab371-129">The selected functoid/link, along with the related functoids and links, is moved to the new grid page.</span></span> <span data-ttu-id="ab371-130">次の図は、選択したリレーションシップ (ページ 3 では) を 1 ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="ab371-130">The figure below shows the selected relationship (which was in Page 3) moved to Page 1.</span></span>  
  
     <span data-ttu-id="ab371-131">![選択したリレーションシップは新しいページに移動](../core/media/moving-a-functoid-new2.gif "Moving_a_functoid_new2")</span><span class="sxs-lookup"><span data-stu-id="ab371-131">![Selected relationship is moved to a new page](../core/media/moving-a-functoid-new2.gif "Moving_a_functoid_new2")</span></span>  
  
### <a name="to-move-a-relationship-using-drag-and-drop"></a><span data-ttu-id="ab371-132">ドラッグ アンド ドロップを使用してリレーションシップを移動するには</span><span class="sxs-lookup"><span data-stu-id="ab371-132">To move a relationship using drag-and-drop</span></span>  
  
1.  <span data-ttu-id="ab371-133">マップでは、関係を移動するグリッド ページを選択します。</span><span class="sxs-lookup"><span data-stu-id="ab371-133">On the map, select the grid page from which you want to move a relationship.</span></span>  
  
2.  <span data-ttu-id="ab371-134">Functoid (および別のグリッド ページに移動する link(s)) を選択します。</span><span class="sxs-lookup"><span data-stu-id="ab371-134">Select the functoid(s) (and link(s)) you want to move to another grid page.</span></span> <span data-ttu-id="ab371-135">この再帰的には、選択範囲の functoid に接続するすべてのリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="ab371-135">This recursively selects all links that connect to the functoids in the selection.</span></span>  
  
3.  <span data-ttu-id="ab371-136">リレーションシップを移動する ([ページ] タブで) ページに、選択をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="ab371-136">Drag the selection to the page (on the page tab) where you want to move the relationship.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="ab371-137">手順 4. を実行するまでマウスを解放できません。</span><span class="sxs-lookup"><span data-stu-id="ab371-137">Do not release the mouse till you perform step 4.</span></span>  
  
4.  <span data-ttu-id="ab371-138">ときに、ターゲットのグリッド ページにフォーカスが移ったら (上記の図では、1 ページにフォーカスが)、グリッド ページで、空のセルの選択項目をドロップします。</span><span class="sxs-lookup"><span data-stu-id="ab371-138">When the target grid page comes into focus (in the above figure, Page 1 is in focus), drop the selection on an empty cell on the grid page.</span></span> <span data-ttu-id="ab371-139">選択したリレーションシップは、新しいグリッド ページに移動されます。</span><span class="sxs-lookup"><span data-stu-id="ab371-139">The selected relationship is moved to the new grid page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab371-140">参照</span><span class="sxs-lookup"><span data-stu-id="ab371-140">See Also</span></span>  
 [<span data-ttu-id="ab371-141">グリッド ページの操作</span><span class="sxs-lookup"><span data-stu-id="ab371-141">Working with Grid Pages</span></span>](../core/working-with-grid-pages.md)