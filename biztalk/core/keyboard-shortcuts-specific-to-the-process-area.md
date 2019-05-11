---
title: 処理領域に固有のショートカットをキーボード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- keyboard shortcuts, Orchestration Designer
- Orchestration Designer, keyboard shortcuts
ms.assetid: d993d341-99f2-4788-b1f3-6a8b911e5278
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0dc59da751ee8acb68ff4d38f42b08020ae94b66
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329462"
---
# <a name="keyboard-shortcuts-specific-to-the-process-area"></a><span data-ttu-id="4a14e-102">処理領域に固有のキーボード ショートカット</span><span class="sxs-lookup"><span data-stu-id="4a14e-102">Keyboard Shortcuts Specific to the Process Area</span></span>
<span data-ttu-id="4a14e-103">次の表では、処理領域、オーケストレーションのプロセス フローを定義するためのデザイン画面の中央の領域内で使用できるキーボード操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="4a14e-103">The following table describes the keyboard navigation available in the Process Area, the central area of the design surface used to define the process flow of the orchestration.</span></span>  
  
|<span data-ttu-id="4a14e-104">キー</span><span class="sxs-lookup"><span data-stu-id="4a14e-104">Key</span></span>|<span data-ttu-id="4a14e-105">効果</span><span class="sxs-lookup"><span data-stu-id="4a14e-105">Effect</span></span>|  
|---------|------------|  
|<span data-ttu-id="4a14e-106">下方向キー</span><span class="sxs-lookup"><span data-stu-id="4a14e-106">DOWN ARROW</span></span>|<span data-ttu-id="4a14e-107">次の区分線または図形の下に移動します。</span><span class="sxs-lookup"><span data-stu-id="4a14e-107">Moves the selection to the next connecting line or shape below.</span></span> <span data-ttu-id="4a14e-108">図形は、(判断図形の場合) のように複数の分岐の下に接続されて、選択範囲が一番左の分岐の最初の図形に移動します。</span><span class="sxs-lookup"><span data-stu-id="4a14e-108">If the shape is connected to several branches below (as in the case of a Decide shape), the selection moves to the first shape in the leftmost branch.</span></span><br /><br /> <span data-ttu-id="4a14e-109">オーケストレーションの終了図形を選択する場合は、このキーを押しては影響しません、下にある図形があるためです。</span><span class="sxs-lookup"><span data-stu-id="4a14e-109">If selection is on the End shape for the orchestration, pressing this key has no effect, because there are no more shapes below it.</span></span>|  
|<span data-ttu-id="4a14e-110">上矢印</span><span class="sxs-lookup"><span data-stu-id="4a14e-110">UP ARROW</span></span>|<span data-ttu-id="4a14e-111">次の区分線または図形の上に移動します。</span><span class="sxs-lookup"><span data-stu-id="4a14e-111">Moves the selection to the next connecting line or shape above.</span></span> <span data-ttu-id="4a14e-112">場合は、図形は、上記の複数の分岐に接続されて、選択が移動最後の図形で一番左の分岐。</span><span class="sxs-lookup"><span data-stu-id="4a14e-112">If the shape is connected to several branches above, selection moves to the last shape on the leftmost branch.</span></span><br /><br /> <span data-ttu-id="4a14e-113">このキーを押してにない場合は影響、**開始**図形が選択されています。</span><span class="sxs-lookup"><span data-stu-id="4a14e-113">Pressing this key has no effect when the **Start** shape is selected.</span></span>|  
|<span data-ttu-id="4a14e-114">左方向キー</span><span class="sxs-lookup"><span data-stu-id="4a14e-114">LEFT ARROW</span></span>|<span data-ttu-id="4a14e-115">送信または受信図形を選択している場合、図形をポートに接続します。</span><span class="sxs-lookup"><span data-stu-id="4a14e-115">If the selection is on a Send or Receive shape and the shape is connected to a port:</span></span><br /><br /> <span data-ttu-id="4a14e-116">-図形に左ポート画面でのポートに向かうポート コネクタがある場合、図形のポート コネクタにフォーカスと選択が移動します。</span><span class="sxs-lookup"><span data-stu-id="4a14e-116">-   If the shape has a port connector leading to a port in the Left Port Surface, focus and selection shift to the port connector of the shape.</span></span><br /><span data-ttu-id="4a14e-117">場合、図形の右ポート画面でのポートに向かうポート コネクタには、このキーを押しても効果はありません。</span><span class="sxs-lookup"><span data-stu-id="4a14e-117">-   If the shape has a port connector leading to a port in the Right Port Surface, pressing this key has no effect.</span></span><br /><span data-ttu-id="4a14e-118">-図形にポート コネクタがあるない場合、ナビゲーションは、他の図形と同じになります。</span><span class="sxs-lookup"><span data-stu-id="4a14e-118">-   If the shape has no port connector, navigation is the same as with any other shape.</span></span><br /><br /> <span data-ttu-id="4a14e-119">その他の図形 (またはポートに接続されていない送信または受信図形)。</span><span class="sxs-lookup"><span data-stu-id="4a14e-119">For other shapes (or Send or Receive shapes not connected to a port):</span></span><br /><br /> <span data-ttu-id="4a14e-120">-分岐が、選択されているため、ブランチが存在する場合、current branch の左側に図形を含む選択は、左側の分岐で、最も近い図形に移動します。</span><span class="sxs-lookup"><span data-stu-id="4a14e-120">-   If the selection is in a branch, and a branch exists with shapes on it to the left of the current branch, the selection moves to the nearest shape on the branch to the left.</span></span><br /><span data-ttu-id="4a14e-121">-キーには、オーケストレーションの他の場所の効果はありません。</span><span class="sxs-lookup"><span data-stu-id="4a14e-121">-   The key has no effect anywhere else in the orchestration.</span></span>|  
|<span data-ttu-id="4a14e-122">右矢印</span><span class="sxs-lookup"><span data-stu-id="4a14e-122">RIGHT ARROW</span></span>|<span data-ttu-id="4a14e-123">同じ反対の方向ですが、左矢印キーとして。</span><span class="sxs-lookup"><span data-stu-id="4a14e-123">Same as the LEFT ARROW key, but in the opposite direction.</span></span>|  
|<span data-ttu-id="4a14e-124">Home</span><span class="sxs-lookup"><span data-stu-id="4a14e-124">HOME</span></span>|<span data-ttu-id="4a14e-125">選択対象は、オーケストレーションの開始図形から出ているコネクタに変更します。</span><span class="sxs-lookup"><span data-stu-id="4a14e-125">Selection changes to the connector that leads from the Start shape of the orchestration.</span></span>|  
|<span data-ttu-id="4a14e-126">END</span><span class="sxs-lookup"><span data-stu-id="4a14e-126">END</span></span>|<span data-ttu-id="4a14e-127">選択対象は、オーケストレーションの終了図形に入るコネクタに変更します。</span><span class="sxs-lookup"><span data-stu-id="4a14e-127">Selection changes to the connector that leads into the End shape of the orchestration.</span></span>|  
|<span data-ttu-id="4a14e-128">NUMLOCK + -</span><span class="sxs-lookup"><span data-stu-id="4a14e-128">NUM LOCK + -</span></span>|<span data-ttu-id="4a14e-129">選択した複雑な図形を折りたたみます。</span><span class="sxs-lookup"><span data-stu-id="4a14e-129">Collapses the selected complex shape.</span></span>|  
|<span data-ttu-id="4a14e-130">NUMLOCK + +</span><span class="sxs-lookup"><span data-stu-id="4a14e-130">NUM LOCK + +</span></span>|<span data-ttu-id="4a14e-131">選択した複雑な図形を展開します。</span><span class="sxs-lookup"><span data-stu-id="4a14e-131">Expands the selected complex shape.</span></span>|  
|<span data-ttu-id="4a14e-132">NUMLOCK + \*</span><span class="sxs-lookup"><span data-stu-id="4a14e-132">NUM LOCK + \*</span></span>|<span data-ttu-id="4a14e-133">選択した複雑な図形とする可能性があります、子の複雑な図形を展開します。</span><span class="sxs-lookup"><span data-stu-id="4a14e-133">Expands the selected complex shape, plus any child complex shapes it may have.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4a14e-134">参照</span><span class="sxs-lookup"><span data-stu-id="4a14e-134">See Also</span></span>  
 [<span data-ttu-id="4a14e-135">オーケストレーション デザイナーのキーボード ショートカット</span><span class="sxs-lookup"><span data-stu-id="4a14e-135">Orchestration Designer Keyboard Shortcuts</span></span>](../core/orchestration-designer-keyboard-shortcuts.md)