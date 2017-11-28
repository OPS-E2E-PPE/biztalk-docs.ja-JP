---
title: "処理領域に固有のショートカットをキーボード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- keyboard shortcuts, Orchestration Designer
- Orchestration Designer, keyboard shortcuts
ms.assetid: d993d341-99f2-4788-b1f3-6a8b911e5278
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba60b23c6c8719789e8de6903dbb538fa5088b08
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="keyboard-shortcuts-specific-to-the-process-area"></a><span data-ttu-id="86ebd-102">処理領域に固有のキーボード ショートカット</span><span class="sxs-lookup"><span data-stu-id="86ebd-102">Keyboard Shortcuts Specific to the Process Area</span></span>
<span data-ttu-id="86ebd-103">処理領域で使用できるキーボード操作を次の表に示します。処理領域はデザイン画面の中央の領域で、オーケストレーションのプロセス フローの定義に使用します。</span><span class="sxs-lookup"><span data-stu-id="86ebd-103">The following table describes the keyboard navigation available in the Process Area, the central area of the design surface used to define the process flow of the orchestration.</span></span>  
  
|<span data-ttu-id="86ebd-104">[キー]</span><span class="sxs-lookup"><span data-stu-id="86ebd-104">Key</span></span>|<span data-ttu-id="86ebd-105">結果</span><span class="sxs-lookup"><span data-stu-id="86ebd-105">Effect</span></span>|  
|---------|------------|  
|<span data-ttu-id="86ebd-106">下方向キー</span><span class="sxs-lookup"><span data-stu-id="86ebd-106">DOWN ARROW</span></span>|<span data-ttu-id="86ebd-107">下方向にある次の区分線または図形に選択対象を移動します。</span><span class="sxs-lookup"><span data-stu-id="86ebd-107">Moves the selection to the next connecting line or shape below.</span></span> <span data-ttu-id="86ebd-108">判断図形のように、図形の下に複数の分岐が接続されている場合、選択対象は最も左の分岐の最初の図形に移動します。</span><span class="sxs-lookup"><span data-stu-id="86ebd-108">If the shape is connected to several branches below (as in the case of a Decide shape), the selection moves to the first shape in the leftmost branch.</span></span><br /><br /> <span data-ttu-id="86ebd-109">選択対象がオーケストレーションの終了図形である場合は、終了図形より下には図形が存在しないため、このキーを押しても何も起こりません。</span><span class="sxs-lookup"><span data-stu-id="86ebd-109">If selection is on the End shape for the orchestration, pressing this key has no effect, because there are no more shapes below it.</span></span>|  
|<span data-ttu-id="86ebd-110">上矢印</span><span class="sxs-lookup"><span data-stu-id="86ebd-110">UP ARROW</span></span>|<span data-ttu-id="86ebd-111">上方向にある次の区分線または図形に選択対象を移動します。</span><span class="sxs-lookup"><span data-stu-id="86ebd-111">Moves the selection to the next connecting line or shape above.</span></span> <span data-ttu-id="86ebd-112">図形の上に複数の分岐が接続されている場合、選択対象は最も左の分岐の最後の図形に移動します。</span><span class="sxs-lookup"><span data-stu-id="86ebd-112">If the shape is connected to several branches above, selection moves to the last shape on the leftmost branch.</span></span><br /><br /> <span data-ttu-id="86ebd-113">このキーを押すと持たないされるときに有効、**開始**図形が選択されています。</span><span class="sxs-lookup"><span data-stu-id="86ebd-113">Pressing this key has no effect when the **Start** shape is selected.</span></span>|  
|<span data-ttu-id="86ebd-114">左方向キー</span><span class="sxs-lookup"><span data-stu-id="86ebd-114">LEFT ARROW</span></span>|<span data-ttu-id="86ebd-115">選択対象が送信図形または受信図形であり、その図形がポートに接続されている場合は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="86ebd-115">If the selection is on a Send or Receive shape and the shape is connected to a port:</span></span><br /><br /> <span data-ttu-id="86ebd-116">-図形にポート左ポート画面に向かうポート コネクタがある場合、図形のポート コネクタにフォーカスと選択をシフトします。</span><span class="sxs-lookup"><span data-stu-id="86ebd-116">-   If the shape has a port connector leading to a port in the Left Port Surface, focus and selection shift to the port connector of the shape.</span></span><br /><span data-ttu-id="86ebd-117">-図形にポート右ポート画面に向かうポート コネクタがある場合、このキーを押しても何も起こりません。</span><span class="sxs-lookup"><span data-stu-id="86ebd-117">-   If the shape has a port connector leading to a port in the Right Port Surface, pressing this key has no effect.</span></span><br /><span data-ttu-id="86ebd-118">-図形にポート コネクタがあるない場合、ナビゲーション、その他の図形として同じです。</span><span class="sxs-lookup"><span data-stu-id="86ebd-118">-   If the shape has no port connector, navigation is the same as with any other shape.</span></span><br /><br /> <span data-ttu-id="86ebd-119">その他の図形 (ポートに接続されていない送信図形および受信図形) の場合は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="86ebd-119">For other shapes (or Send or Receive shapes not connected to a port):</span></span><br /><br /> <span data-ttu-id="86ebd-120">-場合、分岐が、選択されているため、現在のブランチの左側に図形を含む分岐が存在する、選択範囲は、左側の分岐で最も近い図形に移動します。</span><span class="sxs-lookup"><span data-stu-id="86ebd-120">-   If the selection is in a branch, and a branch exists with shapes on it to the left of the current branch, the selection moves to the nearest shape on the branch to the left.</span></span><br /><span data-ttu-id="86ebd-121">-キーには、他の場所、オーケストレーションでの効果はありません。</span><span class="sxs-lookup"><span data-stu-id="86ebd-121">-   The key has no effect anywhere else in the orchestration.</span></span>|  
|<span data-ttu-id="86ebd-122">右矢印</span><span class="sxs-lookup"><span data-stu-id="86ebd-122">RIGHT ARROW</span></span>|<span data-ttu-id="86ebd-123">← キーと同じですが、方向が逆です。</span><span class="sxs-lookup"><span data-stu-id="86ebd-123">Same as the LEFT ARROW key, but in the opposite direction.</span></span>|  
|<span data-ttu-id="86ebd-124">Home</span><span class="sxs-lookup"><span data-stu-id="86ebd-124">HOME</span></span>|<span data-ttu-id="86ebd-125">選択対象をオーケストレーションの開始図形から出ているコネクタに変更します。</span><span class="sxs-lookup"><span data-stu-id="86ebd-125">Selection changes to the connector that leads from the Start shape of the orchestration.</span></span>|  
|<span data-ttu-id="86ebd-126">END</span><span class="sxs-lookup"><span data-stu-id="86ebd-126">END</span></span>|<span data-ttu-id="86ebd-127">選択対象をオーケストレーションの終了図形に入るコネクタに変更します。</span><span class="sxs-lookup"><span data-stu-id="86ebd-127">Selection changes to the connector that leads into the End shape of the orchestration.</span></span>|  
|<span data-ttu-id="86ebd-128">NumLock+マイナス記号 (-)</span><span class="sxs-lookup"><span data-stu-id="86ebd-128">NUM LOCK + -</span></span>|<span data-ttu-id="86ebd-129">選択した複雑な図形を折りたたみます。</span><span class="sxs-lookup"><span data-stu-id="86ebd-129">Collapses the selected complex shape.</span></span>|  
|<span data-ttu-id="86ebd-130">NumLock+プラス記号 (+)</span><span class="sxs-lookup"><span data-stu-id="86ebd-130">NUM LOCK + +</span></span>|<span data-ttu-id="86ebd-131">選択した複雑な図形を展開します。</span><span class="sxs-lookup"><span data-stu-id="86ebd-131">Expands the selected complex shape.</span></span>|  
|<span data-ttu-id="86ebd-132">NumLock+*</span><span class="sxs-lookup"><span data-stu-id="86ebd-132">NUM LOCK + *</span></span>|<span data-ttu-id="86ebd-133">選択した複雑な図形を展開します。その図形に複雑な子の図形がある場合は、その子の図形も展開します。</span><span class="sxs-lookup"><span data-stu-id="86ebd-133">Expands the selected complex shape, plus any child complex shapes it may have.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="86ebd-134">参照</span><span class="sxs-lookup"><span data-stu-id="86ebd-134">See Also</span></span>  
 [<span data-ttu-id="86ebd-135">オーケストレーション デザイナーのキーボード ショートカット</span><span class="sxs-lookup"><span data-stu-id="86ebd-135">Orchestration Designer Keyboard Shortcuts</span></span>](../core/orchestration-designer-keyboard-shortcuts.md)