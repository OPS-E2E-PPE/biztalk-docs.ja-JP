---
title: コピー、切り取り、および Functoid を貼り付けする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 825847e4-87db-4b40-8e5d-5b5b1c79c6de
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9af3662fb866eb09c1dcb2516279ca097cc998f6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249530"
---
# <a name="how-to-copy-cut-and-paste-a-functoid"></a><span data-ttu-id="6b976-102">コピー、切り取り、および貼り付けする方法について</span><span class="sxs-lookup"><span data-stu-id="6b976-102">How to Copy, Cut, and Paste a Functoid</span></span>
<span data-ttu-id="6b976-103">BizTalk マッパーのコピー機能、切り取り機能、および貼り付け機能により、Functoid を再利用できます。</span><span class="sxs-lookup"><span data-stu-id="6b976-103">The copy/cut/paste feature in the BizTalk Mapper enables the reusability of functoids.</span></span> <span data-ttu-id="6b976-104">マップで、1 つ以上の Functoid をあるグリッド ページから別のグリッド ページにコピー、切り取り、および貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="6b976-104">In a map, you can copy, cut, and paste one or more functoids from one grid page to another.</span></span> <span data-ttu-id="6b976-105">このトピックでは、これらの操作を実行するための手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="6b976-105">This topic provides step-by-step instructions to perform these operations.</span></span>  
  
 <span data-ttu-id="6b976-106">コピー/貼り付け機能は、Functoid を再利用するときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="6b976-106">You can use the copy/paste feature when you want to reuse functoids.</span></span> <span data-ttu-id="6b976-107">また、Functoid を既存の場所から削除し、新しい場所に移動するときは、切り取り/貼り付け機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6b976-107">And, when you want to remove a functoid from the existing location and move it to a new location, you can use the cut/paste feature.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6b976-108">Functoid のコピーを選択すると、Functoid、ラベル、コメント、および定数入力がプレースホルダー インデックスと共にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="6b976-108">When you choose to copy a functoid, the functoid, its label, comments, and the constant-inputs, along with the placeholder indices, are copied.</span></span> <span data-ttu-id="6b976-109">同様に、Functoid の切り取りを選択すると、Functoid、ラベル、コメント、および定数入力がプレースホルダー インデックスと共に切り取られます。</span><span class="sxs-lookup"><span data-stu-id="6b976-109">Similarly, when you choose to cut a functoid, the functoid, its label, comments, constant-inputs, along with the placeholder indices, are cut.</span></span> <span data-ttu-id="6b976-110">しかし、切り取りを選択した後に選択内容を貼り付けると、Functoid のみが維持され、孤立したリンクは削除されます。</span><span class="sxs-lookup"><span data-stu-id="6b976-110">But, when you paste (after choosing to cut) the selection, only the functoid is retained and the orphaned links are deleted.</span></span> <span data-ttu-id="6b976-111">ラベル、コメント、定数入力、およびプレースホルダー インデックスは維持されません。</span><span class="sxs-lookup"><span data-stu-id="6b976-111">The label, comments, constant inputs, and placeholder indices are not retained.</span></span>  
  
 <span data-ttu-id="6b976-112">別の Functoid またはスキーマ ノードにリンクしている Functoid のみを選択した場合、その Functoid のみが切り取られるかまたはコピーされ、リンクの切り取りやコピーは行われません。</span><span class="sxs-lookup"><span data-stu-id="6b976-112">If you select only a functoid, which is either linked to another functoid or a schema node, only the functoid will be cut or copied, without the links.</span></span> <span data-ttu-id="6b976-113">マップ内の他の Functoid またはスキーマ ノードにリンクした Functoid を切り取った場合、切り取った Functoid へのリンクは削除されます。</span><span class="sxs-lookup"><span data-stu-id="6b976-113">If you cut a functoid that is linked to other functoids in the map or to the schema nodes, the links to the functoid that is cut are deleted.</span></span>  
  
 <span data-ttu-id="6b976-114">Functoid のコピー/切り取り操作は次の場所で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6b976-114">You can copy/cut functoids from:</span></span>  
  
-   <span data-ttu-id="6b976-115">マップの同じグリッド ページ内</span><span class="sxs-lookup"><span data-stu-id="6b976-115">Within the same grid page of a map</span></span>  
  
-   <span data-ttu-id="6b976-116">同じマップのグリッド ページ間</span><span class="sxs-lookup"><span data-stu-id="6b976-116">One grid page to the other in the same map</span></span>  
  
-   <span data-ttu-id="6b976-117">Visual Studio のインスタンス間</span><span class="sxs-lookup"><span data-stu-id="6b976-117">One instance of Visual Studio to another</span></span>  
  
 <span data-ttu-id="6b976-118">切り取り/貼り付け操作は元に戻したり、やり直したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="6b976-118">You can undo or redo the cut and paste operations.</span></span> <span data-ttu-id="6b976-119">詳細については、次を参照してください。[を元に戻すまたはユーザーの操作をやり直す方法](../core/how-to-undo-or-redo-user-operations.md)です。</span><span class="sxs-lookup"><span data-stu-id="6b976-119">For more information, see [How to Undo or Redo User Operations](../core/how-to-undo-or-redo-user-operations.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6b976-120">前提条件</span><span class="sxs-lookup"><span data-stu-id="6b976-120">Prerequisites</span></span>  
 <span data-ttu-id="6b976-121">これらの手順では、BizTalk マッパーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b976-121">These instructions require that BizTalk Mapper is running.</span></span>  
  
### <a name="to-copy-and-paste-a-functoid"></a><span data-ttu-id="6b976-122">Functoid のコピーおよび貼り付けを行うには</span><span class="sxs-lookup"><span data-stu-id="6b976-122">To copy and paste a functoid</span></span>  
  
1.  <span data-ttu-id="6b976-123">ソリューション エクスプローラーで、BizTalk プロジェクトを開き、マップをダブルクリックして BizTalk マッパーで開きます。</span><span class="sxs-lookup"><span data-stu-id="6b976-123">In Solution Explorer, open the BizTalk project, and then double-click the map to open it in BizTalk Mapper.</span></span>  
  
2.  <span data-ttu-id="6b976-124">コピーする Functoid を選択します。</span><span class="sxs-lookup"><span data-stu-id="6b976-124">Select the functoid you want to copy.</span></span> <span data-ttu-id="6b976-125">複数の functoid を選択するには、Ctrl キーを押しながら他の functoid をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b976-125">To select multiple functoids, click one functoid, hold down the CTRL key, and then click the other functoids.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6b976-126">"リボン選択" 操作を使用して、複数のリンクや Functoid を選択できます。</span><span class="sxs-lookup"><span data-stu-id="6b976-126">You can use the “ribbon select” operation to select multiple link(s) and/or functoid(s).</span></span> <span data-ttu-id="6b976-127">詳細については、次を参照してください。[および Functoid を複数のリンクを選択する方法](../core/how-to-select-multiple-links-and-functoids.md)です。</span><span class="sxs-lookup"><span data-stu-id="6b976-127">For more information, see [How to Select Multiple Links and Functoids](../core/how-to-select-multiple-links-and-functoids.md).</span></span>  
  
3.  <span data-ttu-id="6b976-128">選択範囲を右クリックし、をクリックして**コピー**です。</span><span class="sxs-lookup"><span data-stu-id="6b976-128">Right-click the selection, and then click **Copy**.</span></span> <span data-ttu-id="6b976-129">いずれかをクリックすることができます、**コピー** Visual studio の**編集**メニューやキーボードの ctrl キーを押しながら C キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6b976-129">Alternatively, you can either click **Copy** from the Visual Studio’s **Edit** menu or press CTRL+C on the keyboard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6b976-130">キーボード ショートカットの一覧は、次を参照してください。 [BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)です。</span><span class="sxs-lookup"><span data-stu-id="6b976-130">For a list of keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
4.  <span data-ttu-id="6b976-131">Functoid を貼り付ける場所にカーソルを置きます。</span><span class="sxs-lookup"><span data-stu-id="6b976-131">Place the cursor where you wish to paste the functoid.</span></span>  
  
5.  <span data-ttu-id="6b976-132">グリッド ページを右クリックし、をクリックして**貼り付け**です。</span><span class="sxs-lookup"><span data-stu-id="6b976-132">Right-click on the grid page, and then click **Paste**.</span></span> <span data-ttu-id="6b976-133">いずれかをクリックすることができます、**貼り付け**Visual studio の**編集**メニューやキーボードの ctrl キーを押しながら V キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6b976-133">Alternatively, you can either click **Paste** from the Visual Studio’s **Edit** menu or press CTRL+V on the keyboard.</span></span> <span data-ttu-id="6b976-134">選択した Functoid または Functoid のグループが新しい場所に表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b976-134">A copy of the selected functoid or group of functoids appears at the new location.</span></span>  
  
### <a name="to-cut-and-paste-a-functoid"></a><span data-ttu-id="6b976-135">Functoid の切り取りおよび貼り付けを行うには</span><span class="sxs-lookup"><span data-stu-id="6b976-135">To cut and paste a functoid</span></span>  
  
1.  <span data-ttu-id="6b976-136">ソリューション エクスプローラーで、BizTalk プロジェクトを開き、マップをダブルクリックして BizTalk マッパーで開きます。</span><span class="sxs-lookup"><span data-stu-id="6b976-136">In Solution Explorer, open the BizTalk project, and then double-click the map to open it in BizTalk Mapper.</span></span>  
  
2.  <span data-ttu-id="6b976-137">切り取る Functoid を選択します。</span><span class="sxs-lookup"><span data-stu-id="6b976-137">Select the functoid you want to cut.</span></span> <span data-ttu-id="6b976-138">複数の functoid を選択するには、Ctrl キーを押しながら他の functoid をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b976-138">To select multiple functoids, click one functoid, hold down the CTRL key, and then click the other functoids.</span></span>  
  
3.  <span data-ttu-id="6b976-139">選択範囲を右クリックし、をクリックして**切り取り**です。</span><span class="sxs-lookup"><span data-stu-id="6b976-139">Right-click the selection, and then click **Cut**.</span></span> <span data-ttu-id="6b976-140">いずれかをクリックすることができます、**切り取り**Visual studio の**編集**メニューやキーボードの ctrl キーを押しながら X キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6b976-140">Alternatively, you can either click **Cut** from the Visual Studio’s **Edit** menu or press CTRL+X on the keyboard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6b976-141">キーボード ショートカットの一覧は、次を参照してください。 [BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)です。</span><span class="sxs-lookup"><span data-stu-id="6b976-141">For a list of keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
4.  <span data-ttu-id="6b976-142">Functoid を貼り付ける場所にカーソルを置きます。</span><span class="sxs-lookup"><span data-stu-id="6b976-142">Place the cursor where you wish to paste the functoid.</span></span>  
  
5.  <span data-ttu-id="6b976-143">グリッド ページを右クリックし、をクリックして**貼り付け**です。</span><span class="sxs-lookup"><span data-stu-id="6b976-143">Right-click on the grid page, and then click **Paste**.</span></span> <span data-ttu-id="6b976-144">いずれかをクリックすることができます、**貼り付け**Visual studio の**編集**メニューやキーボードの ctrl キーを押しながら V キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6b976-144">Alternatively, you can either click **Paste** from the Visual Studio’s **Edit** menu or press CTRL+V on the keyboard.</span></span> <span data-ttu-id="6b976-145">選択した Functoid または Functoid のグループが既存の場所から削除され、新しい場所に表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b976-145">The selected functoid or group of functoids are deleted from the existing location and appear at the new location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b976-146">参照</span><span class="sxs-lookup"><span data-stu-id="6b976-146">See Also</span></span>  
 [<span data-ttu-id="6b976-147">Functoid を使用して、複雑なマッピングを作成するには</span><span class="sxs-lookup"><span data-stu-id="6b976-147">Using Functoids to Create More Complex Mappings</span></span>](../core/using-functoids-to-create-more-complex-mappings.md)