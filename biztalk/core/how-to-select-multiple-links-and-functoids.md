---
title: 複数のリンクおよび Functoid を選択する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f9ae50cb-c212-48f3-9dfb-74df282645c5
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5dbc88252719a59780f5971a4f68990057b130b4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383973"
---
# <a name="how-to-select-multiple-links-and-functoids"></a><span data-ttu-id="de248-102">複数のリンクおよび Functoid を選択する方法</span><span class="sxs-lookup"><span data-stu-id="de248-102">How to Select Multiple Links and Functoids</span></span>
<span data-ttu-id="de248-103">マップの functoid やリンクのグループに対して同じ操作を実行する場合は、同時にすべての functoid やリンクには、そのグループを選択できます。</span><span class="sxs-lookup"><span data-stu-id="de248-103">When you want to perform a similar operation on a group of functoids and/or links in a map, you can select that group of functoids and/or links all at the same time.</span></span> <span data-ttu-id="de248-104">このトピックでは、次の操作を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="de248-104">This topic provides information about how to perform this operation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="de248-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="de248-105">Prerequisites</span></span>  
 <span data-ttu-id="de248-106">これらの手順では、BizTalk マッパーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="de248-106">These instructions require that BizTalk Mapper is running.</span></span>  
  
## <a name="why-do-you-need-to-bulk-select-linksfunctoids"></a><span data-ttu-id="de248-107">一括選択のリンクおよび functoid に必要な理由</span><span class="sxs-lookup"><span data-stu-id="de248-107">Why do you need to bulk-select links/functoids?</span></span>  
 <span data-ttu-id="de248-108">一括選択できますリンクや functoid には、次のいずれかの。</span><span class="sxs-lookup"><span data-stu-id="de248-108">You can bulk-select links and/or functoids to do any of the following:</span></span>  
  
-   <span data-ttu-id="de248-109">コピーまたは切り取りと同じグリッド ページまたは同じマップ内の別のグリッド ページで選択内容を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="de248-109">Copy/cut and paste the selection in the same grid page or another grid page in the same map.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="de248-110">コピー、切り取り、貼り付けのリンクおよび functoid については、次を参照してください。[方法は、コピー、切り取り、貼り付けのリンクおよび Functoid](../core/how-to-copy-cut-and-paste-links-and-functoids.md)します。</span><span class="sxs-lookup"><span data-stu-id="de248-110">For information on how to copy, cut, and paste links and functoids, see [How to Copy, Cut, and Paste Links and Functoids](../core/how-to-copy-cut-and-paste-links-and-functoids.md).</span></span>  
  
-   <span data-ttu-id="de248-111">グリッド ページ間で移動します。</span><span class="sxs-lookup"><span data-stu-id="de248-111">Move the selection between grid pages</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="de248-112">1 つのグリッド ページ間のリレーションシップを移動する方法については、次を参照してください。[グリッド ページ間のリレーションシップを移動する方法](../core/how-to-move-a-relationship-between-grid-pages.md)します。</span><span class="sxs-lookup"><span data-stu-id="de248-112">For information on how to move a relationship from one grid page to another, see [How to Move a Relationship Between Grid Pages](../core/how-to-move-a-relationship-between-grid-pages.md).</span></span>  
  
-   <span data-ttu-id="de248-113">Functoid およびリンクの選択範囲の共通プロパティを編集します。</span><span class="sxs-lookup"><span data-stu-id="de248-113">Edit the common properties of functoids and links in the selection</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="de248-114">コメントと functoid およびリンクのラベルを設定する方法については、次を参照してください。[リンクにラベルを付ける方法](../core/how-to-label-a-link.md)または[方法、Functoid ラベルとコメント](../core/how-to-label-and-comment-a-functoid.md)。</span><span class="sxs-lookup"><span data-stu-id="de248-114">For information on how to set comments and labels for functoids and links, see [How to Label a Link](../core/how-to-label-a-link.md) or [How to Label and Comment a Functoid](../core/how-to-label-and-comment-a-functoid.md).</span></span>  
  
-   <span data-ttu-id="de248-115">複数のリンクや functoid を 1 つの手順で削除しています</span><span class="sxs-lookup"><span data-stu-id="de248-115">Deleting multiple link(s) and/or functoid(s) in one step</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="de248-116">Functoid を削除する方法については、次を参照してください。 [Functoid を削除する方法](../core/how-to-delete-functoids.md)します。</span><span class="sxs-lookup"><span data-stu-id="de248-116">For information on how to delete functoids, see [How to Delete Functoids](../core/how-to-delete-functoids.md).</span></span>  
  
## <a name="to-select-multiple-links-and-functoids"></a><span data-ttu-id="de248-117">複数のリンクおよび functoid を選択するには</span><span class="sxs-lookup"><span data-stu-id="de248-117">To select multiple links and functoids</span></span>  
 <span data-ttu-id="de248-118">一括選択できます functoid やリンクで、次の方法のいずれか。</span><span class="sxs-lookup"><span data-stu-id="de248-118">You can bulk-select functoids and/or links in any of the following ways:</span></span>  
  
-   <span data-ttu-id="de248-119">リンクまたは functoid をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de248-119">Click the link or the functoid.</span></span> <span data-ttu-id="de248-120">CTRL キー、キーを押しながら他のリンクまたは functoid を選択する をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de248-120">Hold down the CTRL key, and then click the other links and/or functoids you want to select.</span></span>  
  
     <span data-ttu-id="de248-121">次の図は、選択した functoid およびリンクの強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="de248-121">The following figure shows the selected functoids and links highlighted.</span></span>  
  
     <span data-ttu-id="de248-122">![Functoid およびリンクを選択する一括](../core/media/bulkselect-functois-links.gif "BulkSelect_Functois & リンク")</span><span class="sxs-lookup"><span data-stu-id="de248-122">![Bulk selecting functoids and links](../core/media/bulkselect-functois-links.gif "BulkSelect_Functois&Links")</span></span>  
  
-   <span data-ttu-id="de248-123">マップ画面で、マウスをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="de248-123">Drag the mouse on the map surface.</span></span> <span data-ttu-id="de248-124">選択範囲内の functoid が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="de248-124">The functoids under the selection rectangle are highlighted.</span></span>  
  
     <span data-ttu-id="de248-125">![Functoid の矩形選択](../core/media/bulkselect-selectionrectangle.gif "BulkSelect_SelectionRectangle")</span><span class="sxs-lookup"><span data-stu-id="de248-125">![Rectangle selection of functoids](../core/media/bulkselect-selectionrectangle.gif "BulkSelect_SelectionRectangle")</span></span>  
  
-   <span data-ttu-id="de248-126">ドラッグの組み合わせを使用することができ、ctrl キーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="de248-126">You can use a combination of dragging and CTRL-click.</span></span> <span data-ttu-id="de248-127">マップ画面上にマウスをドラッグし、その範囲の functoid やリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="de248-127">Drag the mouse on the map surface and select the functoids and/or links in that range.</span></span> <span data-ttu-id="de248-128">CTRL キー、キーを押しながら functoid や選択範囲の外側にあるリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="de248-128">Hold down the CTRL key, and then click the functoids and/or links outside the selection range.</span></span>  
  
## <a name="to-select-all-links-and-functoids-on-the-grid-page"></a><span data-ttu-id="de248-129">すべてのリンクと functoid をグリッド ページを選択するには</span><span class="sxs-lookup"><span data-stu-id="de248-129">To select all links and functoids on the grid page</span></span>  
 <span data-ttu-id="de248-130">次の方法のいずれかでは、すべての functoid およびマッパー グリッド ページ上のリンクを選択できます。</span><span class="sxs-lookup"><span data-stu-id="de248-130">You can select all the functoids and links on the Mapper grid page in any of the following ways:</span></span>  
  
-   <span data-ttu-id="de248-131">グリッド ページで任意の場所を右クリックし、をクリックして**すべて選択**します。</span><span class="sxs-lookup"><span data-stu-id="de248-131">Right-click anywhere on the grid page and click **Select All**.</span></span>  
  
-   <span data-ttu-id="de248-132">グリッド ページで任意の場所 をクリックし、キーボードの CTRL + A キーを押します。</span><span class="sxs-lookup"><span data-stu-id="de248-132">Click anywhere on the grid page and click press CTRL+A from the keyboard.</span></span>  
  
-   <span data-ttu-id="de248-133">グリッド ページで、任意の場所をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de248-133">Click anywhere on the grid page.</span></span> <span data-ttu-id="de248-134">Visual Studio のメニューからクリックして**編集**、順にクリックします**すべて選択**します。</span><span class="sxs-lookup"><span data-stu-id="de248-134">From the Visual Studio menu, click **Edit**, and then click **Select All**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de248-135">参照</span><span class="sxs-lookup"><span data-stu-id="de248-135">See Also</span></span>  
 [<span data-ttu-id="de248-136">リンクを使用してレコードとフィールド マッピングを指定する</span><span class="sxs-lookup"><span data-stu-id="de248-136">Using Links to Specify Record and Field Mappings</span></span>](../core/using-links-to-specify-record-and-field-mappings.md)