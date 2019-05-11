---
title: グリッド ページの順序を変更する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mapper.reorderpages
ms.assetid: bbf45501-109f-4333-8d1f-1ad47b010db0
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a8ea3a0f5eb08544862081d1495ce5413aaa6f0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384276"
---
# <a name="how-to-reorder-grid-pages"></a><span data-ttu-id="26157-102">グリッド ページの順序を変更する方法</span><span class="sxs-lookup"><span data-stu-id="26157-102">How to Reorder Grid Pages</span></span>
<span data-ttu-id="26157-103">マップが複雑な場合は、複数のグリッド ページが含まれますと名前を変更しして順序を変更します。</span><span class="sxs-lookup"><span data-stu-id="26157-103">If your map is complex, you can include multiple grid pages, and then rename and reorder them.</span></span> <span data-ttu-id="26157-104">このトピックでには、これらの操作を実行する手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="26157-104">This topic includes step-by-step instructions to perform these operations.</span></span>  
  
 <span data-ttu-id="26157-105">マップの表示を簡略化し、整理したり読みして、グリッド ページの 1 つまたは複数を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="26157-105">You can include one or more grid pages to simplify the view of your map, and also to keep it organized and readable.</span></span> <span data-ttu-id="26157-106">たとえば、すべてのリンクと 1 ページにヘッダー情報に関連する functoid を配置し、し、すべてのリンクと別のページにはマップの本体に関連する functoid を配置できます。</span><span class="sxs-lookup"><span data-stu-id="26157-106">For example, you can put all the links and functoids that relate to header information on one page, and then put all the links and functoids that relate to the body of your map on another page.</span></span> <span data-ttu-id="26157-107">名前を変更し、作成したグリッド ページを並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="26157-107">You can then rename and reorder the grid pages that you have created.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="26157-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="26157-108">Prerequisites</span></span>  
 <span data-ttu-id="26157-109">これらの手順では、BizTalk マッパーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="26157-109">These instructions require that BizTalk Mapper is running.</span></span>  
  
### <a name="to-add-and-rename-a-grid-page"></a><span data-ttu-id="26157-110">追加して、グリッド ページの名前を変更するには</span><span class="sxs-lookup"><span data-stu-id="26157-110">To add and rename a grid page</span></span>  
  
1.  <span data-ttu-id="26157-111">ページ タブのパネルを右クリックし、をクリックし、**ページの追加**します。</span><span class="sxs-lookup"><span data-stu-id="26157-111">Right-click the page tabs panel, and then click **Add Page**.</span></span> <span data-ttu-id="26157-112">マップには、挿入された新しいページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="26157-112">You will see a new page inserted in your map.</span></span>  
  
     <span data-ttu-id="26157-113">![追加して、グリッド ページの名前を変更する](../core/media/adding-and-renaming-grid-page.gif "Adding_and_renaming_grid_page")</span><span class="sxs-lookup"><span data-stu-id="26157-113">![Adding and renaming grid pages](../core/media/adding-and-renaming-grid-page.gif "Adding_and_renaming_grid_page")</span></span>  
  
2.  <span data-ttu-id="26157-114">ページ タブのパネルを右クリックし、をクリックし、**ページ名の変更**します。</span><span class="sxs-lookup"><span data-stu-id="26157-114">Right-click the page tabs panel, and then click **Rename Page**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="26157-115">または、既存のページ タブをダブルクリックしますか、または、キーボードの F2 キーを押してできます。</span><span class="sxs-lookup"><span data-stu-id="26157-115">Alternatively, you can either double-click the existing page tab or press F2 on the keyboard.</span></span>  
  
3.  <span data-ttu-id="26157-116">グリッド ページの新しい名前を入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="26157-116">Type the new name for the grid page, and then press ENTER.</span></span>  
  
### <a name="to-reorder-grid-pages-using-reorder-map-pages-dialog-box"></a><span data-ttu-id="26157-117">並べ替えマップ ページ ダイアログ ボックスを使用してグリッド ページの順序を変更するには</span><span class="sxs-lookup"><span data-stu-id="26157-117">To reorder grid pages using Reorder map pages dialog box</span></span>  
  
1.  <span data-ttu-id="26157-118">ページ タブのパネルを右クリックし、をクリックし、**ページの並べ替え**します。</span><span class="sxs-lookup"><span data-stu-id="26157-118">Right-click the page tabs panel, and then click **Reorder Pages**.</span></span>  
  
2.  <span data-ttu-id="26157-119">**マップ ページの並べ替え** ダイアログ ボックスでは、移動するページのタブを選択し、上矢印または下矢印をクリックして、グリッド ページの相対位置を変更 をクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="26157-119">In the **Reorder map pages** dialog box, select the page tab you want to move, and click the UP arrow or the DOWN arrow to change the relative position of the grid page, and then click **OK**.</span></span>  
  
     <span data-ttu-id="26157-120">![グリッド ページの上下移動](../core/media/reorder-map-pages.gif "Reorder_map_pages")</span><span class="sxs-lookup"><span data-stu-id="26157-120">![Move up or down to reorder grid pages](../core/media/reorder-map-pages.gif "Reorder_map_pages")</span></span>  
  
### <a name="to-reorder-grid-pages-using-the-page-tabs-panel"></a><span data-ttu-id="26157-121">ページ タブのパネルを使用してグリッド ページの順序を変更するには</span><span class="sxs-lookup"><span data-stu-id="26157-121">To reorder grid pages using the page tabs panel</span></span>  
  
1.  <span data-ttu-id="26157-122">移動/並べ替えするページのタブを選択します。</span><span class="sxs-lookup"><span data-stu-id="26157-122">Select the page tab you want to move/reorder.</span></span>  
  
2.  <span data-ttu-id="26157-123">マウス キーを押したままページ タブのパネルに沿って動かします。</span><span class="sxs-lookup"><span data-stu-id="26157-123">Hold down the mouse key and move it along the page tabs panel.</span></span>  
  
3.  <span data-ttu-id="26157-124">ページ タブのパネルで目的の場所にページのタブを連続したときに、マウスを放します。</span><span class="sxs-lookup"><span data-stu-id="26157-124">Release the mouse when you have brought the page tab to the desired location on the page tab panel.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="26157-125">ページは移動/並べ替えマウス カーソルが 2 つのページ タブ間で縦線に変更したときのみです。</span><span class="sxs-lookup"><span data-stu-id="26157-125">The page is moved/reordered only when the mouse cursor changes into a vertical line between two page tabs.</span></span> <span data-ttu-id="26157-126">垂直線では、順序が変更されるページの位置を示します。</span><span class="sxs-lookup"><span data-stu-id="26157-126">The vertical line indicates the position of the page to be reordered.</span></span>  
  
### <a name="to-delete-a-grid-page"></a><span data-ttu-id="26157-127">グリッド ページを削除するには</span><span class="sxs-lookup"><span data-stu-id="26157-127">To delete a grid page</span></span>  
  
1.  <span data-ttu-id="26157-128">削除するページのタブを選択します。</span><span class="sxs-lookup"><span data-stu-id="26157-128">Select the tab of the page you want to delete.</span></span>  
  
2.  <span data-ttu-id="26157-129">ページのタブを右クリックし、をクリックし、**ページの削除**します。</span><span class="sxs-lookup"><span data-stu-id="26157-129">Right-click on the page tab, and then click **Delete Page**.</span></span> <span data-ttu-id="26157-130">ページは自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="26157-130">The page is deleted silently.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="26157-131">グリッド ページを削除したくない場合は、削除操作を元に戻すには、ctrl キーを押しながら Z キーを押します。</span><span class="sxs-lookup"><span data-stu-id="26157-131">If you do not want to delete the grid page, press CTRL + Z to undo the deletion operation.</span></span> <span data-ttu-id="26157-132">元に戻すまたはユーザーの操作を再実行する方法の詳細については、次を参照してください。[を元に戻すまたはユーザーの操作をやり直す方法](../core/how-to-undo-or-redo-user-operations.md)します。</span><span class="sxs-lookup"><span data-stu-id="26157-132">For more information on how to undo or redo user operations, see [How to Undo or Redo User Operations](../core/how-to-undo-or-redo-user-operations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26157-133">参照</span><span class="sxs-lookup"><span data-stu-id="26157-133">See Also</span></span>  
 [<span data-ttu-id="26157-134">グリッド ページの操作</span><span class="sxs-lookup"><span data-stu-id="26157-134">Working with Grid Pages</span></span>](../core/working-with-grid-pages.md)