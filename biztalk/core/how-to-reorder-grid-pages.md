---
title: "グリッド ページの順序を変更する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.mapper.reorderpages
ms.assetid: bbf45501-109f-4333-8d1f-1ad47b010db0
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 622ee8346855e41c722898a59de6dbe3da90c8a3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-reorder-grid-pages"></a><span data-ttu-id="4e897-102">グリッド ページを並び替える方法</span><span class="sxs-lookup"><span data-stu-id="4e897-102">How to Reorder Grid Pages</span></span>
<span data-ttu-id="4e897-103">マップが複雑である場合は、複数のグリッド ページを設定できます。グリッド ページの名前や順序を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="4e897-103">If your map is complex, you can include multiple grid pages, and then rename and reorder them.</span></span> <span data-ttu-id="4e897-104">このトピックでは、これらの操作の手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="4e897-104">This topic includes step-by-step instructions to perform these operations.</span></span>  
  
 <span data-ttu-id="4e897-105">グリッド ページを含めることで、マップの表示を簡素化したり、マップを整理したり読みやすくすることができます。</span><span class="sxs-lookup"><span data-stu-id="4e897-105">You can include one or more grid pages to simplify the view of your map, and also to keep it organized and readable.</span></span> <span data-ttu-id="4e897-106">たとえば、あるページにはヘッダー情報に関連するすべてのリンクと Functoid を配置し、別のページにはマップの本体に関連するすべてのリンクと Functoid を配置することができます。</span><span class="sxs-lookup"><span data-stu-id="4e897-106">For example, you can put all the links and functoids that relate to header information on one page, and then put all the links and functoids that relate to the body of your map on another page.</span></span> <span data-ttu-id="4e897-107">グリッド ページを作成した後で、ページの名前や順序を変更できます。</span><span class="sxs-lookup"><span data-stu-id="4e897-107">You can then rename and reorder the grid pages that you have created.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4e897-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="4e897-108">Prerequisites</span></span>  
 <span data-ttu-id="4e897-109">これらの手順では、BizTalk マッパーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e897-109">These instructions require that BizTalk Mapper is running.</span></span>  
  
### <a name="to-add-and-rename-a-grid-page"></a><span data-ttu-id="4e897-110">グリッド ページを追加したりその名前を変更するには</span><span class="sxs-lookup"><span data-stu-id="4e897-110">To add and rename a grid page</span></span>  
  
1.  <span data-ttu-id="4e897-111">ページ タブのパネルを右クリックし、をクリックして**Add Page**です。</span><span class="sxs-lookup"><span data-stu-id="4e897-111">Right-click the page tabs panel, and then click **Add Page**.</span></span> <span data-ttu-id="4e897-112">マップに新しいページが挿入されます。</span><span class="sxs-lookup"><span data-stu-id="4e897-112">You will see a new page inserted in your map.</span></span>  
  
     <span data-ttu-id="4e897-113">![追加して、グリッド ページの名前を変更する](../core/media/adding-and-renaming-grid-page.gif "Adding_and_renaming_grid_page")</span><span class="sxs-lookup"><span data-stu-id="4e897-113">![Adding and renaming grid pages](../core/media/adding-and-renaming-grid-page.gif "Adding_and_renaming_grid_page")</span></span>  
  
2.  <span data-ttu-id="4e897-114">ページ タブのパネルを右クリックし、をクリックして**ページ名の変更**です。</span><span class="sxs-lookup"><span data-stu-id="4e897-114">Right-click the page tabs panel, and then click **Rename Page**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="4e897-115">または、既存のページ タブをダブルクリックするか、キーボードの F2 キーを押して変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="4e897-115">Alternatively, you can either double-click the existing page tab or press F2 on the keyboard.</span></span>  
  
3.  <span data-ttu-id="4e897-116">グリッド ページの新しい名前を入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4e897-116">Type the new name for the grid page, and then press ENTER.</span></span>  
  
### <a name="to-reorder-grid-pages-using-reorder-map-pages-dialog-box"></a><span data-ttu-id="4e897-117">[マップ ページの並べ替え] ダイアログ ボックスでグリッド ページを並べ替えるには</span><span class="sxs-lookup"><span data-stu-id="4e897-117">To reorder grid pages using Reorder map pages dialog box</span></span>  
  
1.  <span data-ttu-id="4e897-118">ページ タブのパネルを右クリックし、をクリックして**ページの並べ替え**です。</span><span class="sxs-lookup"><span data-stu-id="4e897-118">Right-click the page tabs panel, and then click **Reorder Pages**.</span></span>  
  
2.  <span data-ttu-id="4e897-119">**マップ ページの並べ替え** ダイアログ ボックスは、移動するページ タブを選択し、上矢印または下矢印キー、グリッド ページの相対位置を変更し、クリックをクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="4e897-119">In the **Reorder map pages** dialog box, select the page tab you want to move, and click the UP arrow or the DOWN arrow to change the relative position of the grid page, and then click **OK**.</span></span>  
  
     <span data-ttu-id="4e897-120">![グリッド ページを並べ替える上下移動](../core/media/reorder-map-pages.gif "Reorder_map_pages")</span><span class="sxs-lookup"><span data-stu-id="4e897-120">![Move up or down to reorder grid pages](../core/media/reorder-map-pages.gif "Reorder_map_pages")</span></span>  
  
### <a name="to-reorder-grid-pages-using-the-page-tabs-panel"></a><span data-ttu-id="4e897-121">ページ タブのパネルでグリッド ページを並べ替えるには</span><span class="sxs-lookup"><span data-stu-id="4e897-121">To reorder grid pages using the page tabs panel</span></span>  
  
1.  <span data-ttu-id="4e897-122">移動/並べ替えを行うページ タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="4e897-122">Select the page tab you want to move/reorder.</span></span>  
  
2.  <span data-ttu-id="4e897-123">マウスのボタンを押したまま、ページ タブのパネルに沿って動かします。</span><span class="sxs-lookup"><span data-stu-id="4e897-123">Hold down the mouse key and move it along the page tabs panel.</span></span>  
  
3.  <span data-ttu-id="4e897-124">ページ タブのパネル上で目的の場所までページ タブを移動したら、マウス ボタンを離します。</span><span class="sxs-lookup"><span data-stu-id="4e897-124">Release the mouse when you have brought the page tab to the desired location on the page tab panel.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="4e897-125">ページの移動/並べ替えが行われるのは、マウスのカーソルが 2 つのページ タブの間で縦線に変化する場合のみです。</span><span class="sxs-lookup"><span data-stu-id="4e897-125">The page is moved/reordered only when the mouse cursor changes into a vertical line between two page tabs.</span></span> <span data-ttu-id="4e897-126">縦線は、ページの位置が並べ替えられることを示します。</span><span class="sxs-lookup"><span data-stu-id="4e897-126">The vertical line indicates the position of the page to be reordered.</span></span>  
  
### <a name="to-delete-a-grid-page"></a><span data-ttu-id="4e897-127">グリッド ページを削除するには</span><span class="sxs-lookup"><span data-stu-id="4e897-127">To delete a grid page</span></span>  
  
1.  <span data-ttu-id="4e897-128">削除するページのタブを選択します。</span><span class="sxs-lookup"><span data-stu-id="4e897-128">Select the tab of the page you want to delete.</span></span>  
  
2.  <span data-ttu-id="4e897-129">[ページ] タブを右クリックし、をクリックして**ページの削除**です。</span><span class="sxs-lookup"><span data-stu-id="4e897-129">Right-click on the page tab, and then click **Delete Page**.</span></span> <span data-ttu-id="4e897-130">ページを削除する際、確認メッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="4e897-130">The page is deleted silently.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="4e897-131">グリッド ページを削除したくない場合は、Ctrl キーを押しながら Z キーを押して、削除操作を取り消します。</span><span class="sxs-lookup"><span data-stu-id="4e897-131">If you do not want to delete the grid page, press CTRL + Z to undo the deletion operation.</span></span> <span data-ttu-id="4e897-132">元に戻すまたはユーザーの操作を再実行する方法の詳細については、次を参照してください。[を元に戻すまたはユーザーの操作を再実行する方法](../core/how-to-undo-or-redo-user-operations.md)です。</span><span class="sxs-lookup"><span data-stu-id="4e897-132">For more information on how to undo or redo user operations, see [How to Undo or Redo User Operations](../core/how-to-undo-or-redo-user-operations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e897-133">参照</span><span class="sxs-lookup"><span data-stu-id="4e897-133">See Also</span></span>  
 [<span data-ttu-id="4e897-134">グリッド ページの操作</span><span class="sxs-lookup"><span data-stu-id="4e897-134">Working with Grid Pages</span></span>](../core/working-with-grid-pages.md)