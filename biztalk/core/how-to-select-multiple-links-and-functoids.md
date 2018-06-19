---
title: 複数のリンクおよび Functoid を選択する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 8885fe33d0c3a2dc081fbca66a398003c3e21913
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255226"
---
# <a name="how-to-select-multiple-links-and-functoids"></a><span data-ttu-id="bcdf0-102">複数のリンクおよび Functoid を選択する方法</span><span class="sxs-lookup"><span data-stu-id="bcdf0-102">How to Select Multiple Links and Functoids</span></span>
<span data-ttu-id="bcdf0-103">マップ内の Functoid およびリンクのグループに対して同じ操作を実行したい場合は、複数の Functoid およびリンクをグループとして同時に選択することができます。</span><span class="sxs-lookup"><span data-stu-id="bcdf0-103">When you want to perform a similar operation on a group of functoids and/or links in a map, you can select that group of functoids and/or links all at the same time.</span></span> <span data-ttu-id="bcdf0-104">このトピックでは、次の操作を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bcdf0-104">This topic provides information about how to perform this operation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bcdf0-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="bcdf0-105">Prerequisites</span></span>  
 <span data-ttu-id="bcdf0-106">これらの手順では、BizTalk マッパーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcdf0-106">These instructions require that BizTalk Mapper is running.</span></span>  
  
## <a name="why-do-you-need-to-bulk-select-linksfunctoids"></a><span data-ttu-id="bcdf0-107">リンクおよび Functoid を一括選択する理由</span><span class="sxs-lookup"><span data-stu-id="bcdf0-107">Why do you need to bulk-select links/functoids?</span></span>  
 <span data-ttu-id="bcdf0-108">次のどちらかの状況では、リンクおよび Functoid を一括選択できます。</span><span class="sxs-lookup"><span data-stu-id="bcdf0-108">You can bulk-select links and/or functoids to do any of the following:</span></span>  
  
-   <span data-ttu-id="bcdf0-109">同じグリッド ページまたは同じマップ内の他のグリッド ページで、選択項目のコピーまたは切り取りと貼り付けを実行する場合。</span><span class="sxs-lookup"><span data-stu-id="bcdf0-109">Copy/cut and paste the selection in the same grid page or another grid page in the same map.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bcdf0-110">コピー、切り取り、および貼り付けのリンクおよび functoid をする方法については、次を参照してください。[方法は、コピー、切り取り、貼り付けリンク、および Functoid](../core/how-to-copy-cut-and-paste-links-and-functoids.md)です。</span><span class="sxs-lookup"><span data-stu-id="bcdf0-110">For information on how to copy, cut, and paste links and functoids, see [How to Copy, Cut, and Paste Links and Functoids](../core/how-to-copy-cut-and-paste-links-and-functoids.md).</span></span>  
  
-   <span data-ttu-id="bcdf0-111">グリッド ページ間で選択項目を移動する場合。</span><span class="sxs-lookup"><span data-stu-id="bcdf0-111">Move the selection between grid pages</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bcdf0-112">グリッド ページ間でリレーションシップを移動する方法については、次を参照してください。 [、リレーションシップのグリッド ページ間を移動する方法](../core/how-to-move-a-relationship-between-grid-pages.md)です。</span><span class="sxs-lookup"><span data-stu-id="bcdf0-112">For information on how to move a relationship from one grid page to another, see [How to Move a Relationship Between Grid Pages](../core/how-to-move-a-relationship-between-grid-pages.md).</span></span>  
  
-   <span data-ttu-id="bcdf0-113">選択した Functoid およびリンクの共通プロパティを編集する場合。</span><span class="sxs-lookup"><span data-stu-id="bcdf0-113">Edit the common properties of functoids and links in the selection</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bcdf0-114">Functoid およびリンクのコメントとラベルを設定する方法については、次を参照してください。[リンクのラベルを付ける方法](../core/how-to-label-a-link.md)または[方法、Functoid ラベルとコメント](../core/how-to-label-and-comment-a-functoid.md)です。</span><span class="sxs-lookup"><span data-stu-id="bcdf0-114">For information on how to set comments and labels for functoids and links, see [How to Label a Link](../core/how-to-label-a-link.md) or [How to Label and Comment a Functoid](../core/how-to-label-and-comment-a-functoid.md).</span></span>  
  
-   <span data-ttu-id="bcdf0-115">複数のリンクや Functoid を一度に削除する場合。</span><span class="sxs-lookup"><span data-stu-id="bcdf0-115">Deleting multiple link(s) and/or functoid(s) in one step</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bcdf0-116">Functoid を削除する方法については、次を参照してください。 [Functoid を削除する方法](../core/how-to-delete-functoids.md)です。</span><span class="sxs-lookup"><span data-stu-id="bcdf0-116">For information on how to delete functoids, see [How to Delete Functoids](../core/how-to-delete-functoids.md).</span></span>  
  
## <a name="to-select-multiple-links-and-functoids"></a><span data-ttu-id="bcdf0-117">複数のリンクおよび Functoid を選択するには</span><span class="sxs-lookup"><span data-stu-id="bcdf0-117">To select multiple links and functoids</span></span>  
 <span data-ttu-id="bcdf0-118">リンクおよび Functoid は、次のいずれかの方法で一括選択できます。</span><span class="sxs-lookup"><span data-stu-id="bcdf0-118">You can bulk-select functoids and/or links in any of the following ways:</span></span>  
  
-   <span data-ttu-id="bcdf0-119">リンクまたは Functoid をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bcdf0-119">Click the link or the functoid.</span></span> <span data-ttu-id="bcdf0-120">Ctrl キーを押しながら、選択したい他のリンクまたは Functoid をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bcdf0-120">Hold down the CTRL key, and then click the other links and/or functoids you want to select.</span></span>  
  
     <span data-ttu-id="bcdf0-121">次の図では、選択済みの Functoid およびリンクが強調表示されています。</span><span class="sxs-lookup"><span data-stu-id="bcdf0-121">The following figure shows the selected functoids and links highlighted.</span></span>  
  
     <span data-ttu-id="bcdf0-122">![Functoid およびリンクを選択する一括](../core/media/bulkselect-functois-links.gif "BulkSelect_Functois & へのリンク")</span><span class="sxs-lookup"><span data-stu-id="bcdf0-122">![Bulk selecting functoids and links](../core/media/bulkselect-functois-links.gif "BulkSelect_Functois&Links")</span></span>  
  
-   <span data-ttu-id="bcdf0-123">マップ画面上でマウスをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="bcdf0-123">Drag the mouse on the map surface.</span></span> <span data-ttu-id="bcdf0-124">選択した範囲内の Functoid が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="bcdf0-124">The functoids under the selection rectangle are highlighted.</span></span>  
  
     <span data-ttu-id="bcdf0-125">![Functoid の矩形選択](../core/media/bulkselect-selectionrectangle.gif "BulkSelect_SelectionRectangle")</span><span class="sxs-lookup"><span data-stu-id="bcdf0-125">![Rectangle selection of functoids](../core/media/bulkselect-selectionrectangle.gif "BulkSelect_SelectionRectangle")</span></span>  
  
-   <span data-ttu-id="bcdf0-126">ドラッグと Ctrl + クリックを組み合わせて使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="bcdf0-126">You can use a combination of dragging and CTRL-click.</span></span> <span data-ttu-id="bcdf0-127">マップ画面上でマウスをドラッグして、その範囲内の Functoid またはリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="bcdf0-127">Drag the mouse on the map surface and select the functoids and/or links in that range.</span></span> <span data-ttu-id="bcdf0-128">Ctrl キーを押しながら、選択範囲の外側にあるリンクまたは Functoid をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bcdf0-128">Hold down the CTRL key, and then click the functoids and/or links outside the selection range.</span></span>  
  
## <a name="to-select-all-links-and-functoids-on-the-grid-page"></a><span data-ttu-id="bcdf0-129">グリッド ページ内のすべてのリンクと Functoid を選択するには</span><span class="sxs-lookup"><span data-stu-id="bcdf0-129">To select all links and functoids on the grid page</span></span>  
 <span data-ttu-id="bcdf0-130">マッパーのグリッド ページにあるすべての Functoid とリンクは、次のいずれかの方法で一括選択できます。</span><span class="sxs-lookup"><span data-stu-id="bcdf0-130">You can select all the functoids and links on the Mapper grid page in any of the following ways:</span></span>  
  
-   <span data-ttu-id="bcdf0-131">グリッド ページの任意の場所を右クリックし、をクリックして**すべて選択**です。</span><span class="sxs-lookup"><span data-stu-id="bcdf0-131">Right-click anywhere on the grid page and click **Select All**.</span></span>  
  
-   <span data-ttu-id="bcdf0-132">グリッド ページの任意の場所をクリックし、Ctrl キーを押しながら A キーを押します。</span><span class="sxs-lookup"><span data-stu-id="bcdf0-132">Click anywhere on the grid page and click press CTRL+A from the keyboard.</span></span>  
  
-   <span data-ttu-id="bcdf0-133">グリッド ページの任意の場所をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bcdf0-133">Click anywhere on the grid page.</span></span> <span data-ttu-id="bcdf0-134">Visual Studio のメニューからをクリックして**編集**、クリックして**すべて選択**です。</span><span class="sxs-lookup"><span data-stu-id="bcdf0-134">From the Visual Studio menu, click **Edit**, and then click **Select All**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcdf0-135">参照</span><span class="sxs-lookup"><span data-stu-id="bcdf0-135">See Also</span></span>  
 [<span data-ttu-id="bcdf0-136">リンクを使用してレコードを指定してフィールドのマッピング</span><span class="sxs-lookup"><span data-stu-id="bcdf0-136">Using Links to Specify Record and Field Mappings</span></span>](../core/using-links-to-specify-record-and-field-mappings.md)