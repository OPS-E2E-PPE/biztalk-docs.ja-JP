---
title: ビュー内のアイテムを選択したマップを表示する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e287b22-5738-428a-aa35-cced877e51ea
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cd4a932b00ac2d0a89eb9cfb8f343fd9ab0d4fd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342618"
---
# <a name="how-to-bring-selected-map-items-in-view"></a><span data-ttu-id="2231d-102">選択したマップ項目をビューに表示する方法</span><span class="sxs-lookup"><span data-stu-id="2231d-102">How to Bring Selected Map Items in View</span></span>
<span data-ttu-id="2231d-103">以前のバージョンの BizTalk マッパーでは、マップが大きいスキーマで構成される場合必要がある元スキーマ ペイン、グリッド ページで、および 1 つのビューに関連するマップのすべての項目をターゲット スキーマ ウィンドウを手動でスクロールします。</span><span class="sxs-lookup"><span data-stu-id="2231d-103">With earlier versions of BizTalk Mapper, if a map comprised big schemas, you had to manually scroll the source schema pane, the grid page, and the target schema pane to bring all the relevant map items into a single view.</span></span> <span data-ttu-id="2231d-104">BizTalk Server と BizTalk マッパーを使用すると、グリッド ページを自動的にスクロールして、選択した functoid/リンクのすべての関連するマップ項目を 1 つのビューに取り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="2231d-104">The BizTalk Mapper with BizTalk Server allows you to bring all the relevant map items of the selected functoid/link into a single view by automatically scrolling the grid page.</span></span> <span data-ttu-id="2231d-105">このトピックでは、操作を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2231d-105">This topic provides information about how to perform the operation.</span></span>  
  
 <span data-ttu-id="2231d-106">(送信元スキーマのノード、リレーションシップ ビュー、またはターゲット スキーマのノード内の要素) 選択内容に応じて、BizTalk マッパーはスキーマ ビューと同期的に、リレーションシップ ビューが自動的にスクロールとの関係の全体的なビューが表示されます、選択された項目。</span><span class="sxs-lookup"><span data-stu-id="2231d-106">Depending on your selection (a source schema node, an element in the relationship view, or a target schema node), the BizTalk Mapper auto-scrolls the schema views and relationship view in a synchronized fashion, and displays the overall relationship view of the selected item.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2231d-107">自動スクロール機能は、BizTalk マッパーには、すべての関連するマップ項目が強調表示される後効果に渡されます。</span><span class="sxs-lookup"><span data-stu-id="2231d-107">The auto-scroll feature comes into effect after the BizTalk Mapper has emphasized all the relevant map items.</span></span> <span data-ttu-id="2231d-108">つまり、最初の選択項目に関連する要素が強調表示されとし、BizTalk マッパーが自動的にスクロールに関連する要素の表示にします。</span><span class="sxs-lookup"><span data-stu-id="2231d-108">In other words, first the elements related to the selection are highlighted, and then the BizTalk Mapper auto-scrolls to bring the related elements into view.</span></span>  
  
 <span data-ttu-id="2231d-109">BizTalk マッパーは、grid オブジェクトを実際には移動しません。</span><span class="sxs-lookup"><span data-stu-id="2231d-109">The BizTalk Mapper does not actually move the grid objects.</span></span> <span data-ttu-id="2231d-110">Grid オブジェクトは、削除、または選択範囲を変更するときにそれぞれの場所に戻ります。</span><span class="sxs-lookup"><span data-stu-id="2231d-110">The grid objects return to their respective locations when you remove or modify the selection.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2231d-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="2231d-111">Prerequisites</span></span>  
 <span data-ttu-id="2231d-112">この操作では、BizTalk マッパーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2231d-112">This operation requires that BizTalk Mapper is running.</span></span>  
  
### <a name="to-bring-the-selected-map-items-in-view"></a><span data-ttu-id="2231d-113">ビューに、選択したマップ項目を表示するには</span><span class="sxs-lookup"><span data-stu-id="2231d-113">To bring the selected map items in view</span></span>  
  
1.  <span data-ttu-id="2231d-114">マッパー ユーティリティ リボンで自動スクロール アイコンをクリックします。![自動&#45;スクロール アイコン](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll")してオフにします。</span><span class="sxs-lookup"><span data-stu-id="2231d-114">On the Mapper utility ribbon, click the auto-scroll icon ![Auto&#45;scroll icon](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll") to switch it OFF.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2231d-115">![自動&#45;スクロール アイコン](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll")アイコンが切り替えられた既定でオフです。</span><span class="sxs-lookup"><span data-stu-id="2231d-115">The ![Auto&#45;scroll icon](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll") icon is switched OFF by default.</span></span>  
  
2.  <span data-ttu-id="2231d-116">Functoid またはリンクをクリックします。リレーションシップに関連するマップ項目が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="2231d-116">Click a functoid or a link; the relevant map items in the relationship are emphasized.</span></span>  
  
     <span data-ttu-id="2231d-117">次の図では、青の色の選択したリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2231d-117">The following figure displays the selected link in blue color.</span></span> <span data-ttu-id="2231d-118">さらに、BizTalk マッパーでは、緑の色の選択内容に関連するその他のマップ項目が強調表示します。</span><span class="sxs-lookup"><span data-stu-id="2231d-118">In turn, BizTalk Mapper emphasizes the other map items relevant to the selection, in green color.</span></span> <span data-ttu-id="2231d-119">図で、現在のビューで完全にできないの強調表示されますが、選択したリレーションシップのすべての要素がわかります。</span><span class="sxs-lookup"><span data-stu-id="2231d-119">From the figure, you can see that all the elements of the selected relationship, though emphasized, are completely not in the current view.</span></span>  
  
     <span data-ttu-id="2231d-120">![リンクするときに自動&#45;スクロール](../core/media/autoscroll-switchoff.gif "AutoScroll_SwitchOff")</span><span class="sxs-lookup"><span data-stu-id="2231d-120">![Links when auto&#45;scrolling is switched off](../core/media/autoscroll-switchoff.gif "AutoScroll_SwitchOff")</span></span>  
  
3.  <span data-ttu-id="2231d-121">自動スクロール アイコンをクリックします。![自動&#45;スクロール アイコン](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll")オンにします。</span><span class="sxs-lookup"><span data-stu-id="2231d-121">Click the auto-scroll icon ![Auto&#45;scroll icon](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll") to switch it ON.</span></span>  
  
     <span data-ttu-id="2231d-122">BizTalk マッパーは、選択範囲を現在のマップ ビューに関連するすべての項目を自動的にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="2231d-122">The BizTalk Mapper automatically scrolls to bring all the relevant items in the selection into the current map view.</span></span>  
  
     <span data-ttu-id="2231d-123">![自動スクロールはオンになっているときに表示](../core/media/autoscroll-switchon.gif "AutoScroll_SwitchOn")</span><span class="sxs-lookup"><span data-stu-id="2231d-123">![View when autoscrolling is switched on](../core/media/autoscroll-switchon.gif "AutoScroll_SwitchOn")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2231d-124">または、CTRL + M, CTRL + U、キーボードからキーを押すことができます。</span><span class="sxs-lookup"><span data-stu-id="2231d-124">Alternatively, you can press CTRL+M, CTRL+U from the keyboard.</span></span> <span data-ttu-id="2231d-125">マッパーのキーボード ショートカットの一覧は、次を参照してください。 [BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)です。</span><span class="sxs-lookup"><span data-stu-id="2231d-125">For a list of Mapper keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2231d-126">参照</span><span class="sxs-lookup"><span data-stu-id="2231d-126">See Also</span></span>  
 [<span data-ttu-id="2231d-127">BizTalk マッパーの強化された機能の使用</span><span class="sxs-lookup"><span data-stu-id="2231d-127">Using Enhanced Features in BizTalk Mapper</span></span>](../core/using-enhanced-features-in-biztalk-mapper.md)