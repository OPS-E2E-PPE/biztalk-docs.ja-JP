---
title: "ビュー内のアイテムを選択したマップを表示する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3e287b22-5738-428a-aa35-cced877e51ea
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1dff8e981b65b6b91c744ce26648a5f4e06adea
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-bring-selected-map-items-in-view"></a><span data-ttu-id="61dc3-102">選択したマップ項目をビューに表示する方法</span><span class="sxs-lookup"><span data-stu-id="61dc3-102">How to Bring Selected Map Items in View</span></span>
<span data-ttu-id="61dc3-103">以前のバージョンの BizTalk マッパーでは、マップが大きいスキーマで構成される場合は、送信元スキーマ ウィンドウ、グリッド ページ、およびターゲット スキーマ ウィンドウを手動でスクロールして、関連するすべてのマップ項目を 1 つのビューに収める必要がありました。</span><span class="sxs-lookup"><span data-stu-id="61dc3-103">With earlier versions of BizTalk Mapper, if a map comprised big schemas, you had to manually scroll the source schema pane, the grid page, and the target schema pane to bring all the relevant map items into a single view.</span></span> <span data-ttu-id="61dc3-104">BizTalk Server と BizTalk マッパーでは、1 つのビューに、グリッド ページを自動的にスクロールして選択した functoid/リンクのすべての関連するマップ項目を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="61dc3-104">The BizTalk Mapper with BizTalk Server allows you to bring all the relevant map items of the selected functoid/link into a single view by automatically scrolling the grid page.</span></span> <span data-ttu-id="61dc3-105">このトピックでは、この操作を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="61dc3-105">This topic provides information about how to perform the operation.</span></span>  
  
 <span data-ttu-id="61dc3-106">選択内容に応じて (送信元スキーマ ノード、リレーションシップ ビューの要素、またはターゲット スキーマ ノード)、BizTalk マッパーはスキーマ ビューとリレーションシップ ビューを同期して自動的にスクロールし、選択されている項目の全体的なリレーションシップ ビューを表示します。</span><span class="sxs-lookup"><span data-stu-id="61dc3-106">Depending on your selection (a source schema node, an element in the relationship view, or a target schema node), the BizTalk Mapper auto-scrolls the schema views and relationship view in a synchronized fashion, and displays the overall relationship view of the selected item.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61dc3-107">自動スクロール機能は、BizTalk マッパーですべての関連するマップ項目が強調表示されると有効になります。</span><span class="sxs-lookup"><span data-stu-id="61dc3-107">The auto-scroll feature comes into effect after the BizTalk Mapper has emphasized all the relevant map items.</span></span> <span data-ttu-id="61dc3-108">つまり、最初に選択内容に関連する要素が強調表示され、次に BizTalk マッパーが自動的にスクロールして関連する要素をビューに表示します。</span><span class="sxs-lookup"><span data-stu-id="61dc3-108">In other words, first the elements related to the selection are highlighted, and then the BizTalk Mapper auto-scrolls to bring the related elements into view.</span></span>  
  
 <span data-ttu-id="61dc3-109">グリッド オブジェクトが実際に移動されることはありません。</span><span class="sxs-lookup"><span data-stu-id="61dc3-109">The BizTalk Mapper does not actually move the grid objects.</span></span> <span data-ttu-id="61dc3-110">選択を削除または変更すると、グリッド オブジェクトはそれぞれの場所に戻ります。</span><span class="sxs-lookup"><span data-stu-id="61dc3-110">The grid objects return to their respective locations when you remove or modify the selection.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="61dc3-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="61dc3-111">Prerequisites</span></span>  
 <span data-ttu-id="61dc3-112">この操作では、BizTalk マッパーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="61dc3-112">This operation requires that BizTalk Mapper is running.</span></span>  
  
### <a name="to-bring-the-selected-map-items-in-view"></a><span data-ttu-id="61dc3-113">選択されているマップ項目をビューに表示するには</span><span class="sxs-lookup"><span data-stu-id="61dc3-113">To bring the selected map items in view</span></span>  
  
1.  <span data-ttu-id="61dc3-114">マッパー ユーティリティ リボンで自動スクロール アイコンをクリックして![自動 &#45; スクロール アイコン](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll")オフにします。</span><span class="sxs-lookup"><span data-stu-id="61dc3-114">On the Mapper utility ribbon, click the auto-scroll icon ![Auto&#45;scroll icon](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll") to switch it OFF.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="61dc3-115">![自動 &#45; スクロール アイコン](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll")アイコンが切り替えられる既定では OFF です。</span><span class="sxs-lookup"><span data-stu-id="61dc3-115">The ![Auto&#45;scroll icon](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll") icon is switched OFF by default.</span></span>  
  
2.  <span data-ttu-id="61dc3-116">Functoid またはリンクをクリックします。リレーションシップで関連するマップ項目が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="61dc3-116">Click a functoid or a link; the relevant map items in the relationship are emphasized.</span></span>  
  
     <span data-ttu-id="61dc3-117">次の図では選択されているリンクが青で表示されています。</span><span class="sxs-lookup"><span data-stu-id="61dc3-117">The following figure displays the selected link in blue color.</span></span> <span data-ttu-id="61dc3-118">次に、BizTalk マッパーが選択項目に関連する他のマップ項目を緑色で強調表示します。</span><span class="sxs-lookup"><span data-stu-id="61dc3-118">In turn, BizTalk Mapper emphasizes the other map items relevant to the selection, in green color.</span></span> <span data-ttu-id="61dc3-119">図では、選択したリレーションシップのすべての要素が、強調表示されてはいても、現在のビューでは完全には表示されていないことがわかります。</span><span class="sxs-lookup"><span data-stu-id="61dc3-119">From the figure, you can see that all the elements of the selected relationship, though emphasized, are completely not in the current view.</span></span>  
  
     <span data-ttu-id="61dc3-120">![リンク時に自動 &#45; スクロールをオフ](../core/media/autoscroll-switchoff.gif "AutoScroll_SwitchOff")</span><span class="sxs-lookup"><span data-stu-id="61dc3-120">![Links when auto&#45;scrolling is switched off](../core/media/autoscroll-switchoff.gif "AutoScroll_SwitchOff")</span></span>  
  
3.  <span data-ttu-id="61dc3-121">自動スクロール アイコンをクリックして![自動 &#45; スクロール アイコン](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll")をオンにします。</span><span class="sxs-lookup"><span data-stu-id="61dc3-121">Click the auto-scroll icon ![Auto&#45;scroll icon](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll") to switch it ON.</span></span>  
  
     <span data-ttu-id="61dc3-122">BizTalk マッパーが自動的にスクロールし、選択のすべての関連項目が現在のマップ ビューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="61dc3-122">The BizTalk Mapper automatically scrolls to bring all the relevant items in the selection into the current map view.</span></span>  
  
     <span data-ttu-id="61dc3-123">![自動スクロールをとき表示](../core/media/autoscroll-switchon.gif "AutoScroll_SwitchOn")</span><span class="sxs-lookup"><span data-stu-id="61dc3-123">![View when autoscrolling is switched on](../core/media/autoscroll-switchon.gif "AutoScroll_SwitchOn")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="61dc3-124">または、Ctrl キーを押しながら M キーを押し、次に Ctrl キーを押しながら U キーを押します。</span><span class="sxs-lookup"><span data-stu-id="61dc3-124">Alternatively, you can press CTRL+M, CTRL+U from the keyboard.</span></span> <span data-ttu-id="61dc3-125">マッパーのキーボード ショートカットの一覧は、次を参照してください。 [BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)です。</span><span class="sxs-lookup"><span data-stu-id="61dc3-125">For a list of Mapper keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61dc3-126">参照</span><span class="sxs-lookup"><span data-stu-id="61dc3-126">See Also</span></span>  
 [<span data-ttu-id="61dc3-127">BizTalk マッパーの強化された機能の使用</span><span class="sxs-lookup"><span data-stu-id="61dc3-127">Using Enhanced Features in BizTalk Mapper</span></span>](../core/using-enhanced-features-in-biztalk-mapper.md)