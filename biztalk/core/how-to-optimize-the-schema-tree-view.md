---
title: スキーマ ツリー ビューを最適化する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ab4ad6b5-5bbd-443b-9041-6cddf9d64735
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3655e3bdf60aafc243c2d415f70da26224140a67
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384467"
---
# <a name="how-to-optimize-the-schema-tree-view"></a><span data-ttu-id="4d88e-102">スキーマ ツリー ビューを最適化する方法</span><span class="sxs-lookup"><span data-stu-id="4d88e-102">How to Optimize the Schema Tree View</span></span>
<span data-ttu-id="4d88e-103">使用することができます、**関連ビュー**ソースの最適化や送信先スキーマ ツリーに BizTalk マッパーでします。</span><span class="sxs-lookup"><span data-stu-id="4d88e-103">You can use the **Relevance View** in BizTalk Mapper to optimize the source and/or target schema trees.</span></span> <span data-ttu-id="4d88e-104">このトピックでは、操作を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4d88e-104">This topic provides instructions about how to perform the operation.</span></span>  
  
 <span data-ttu-id="4d88e-105">関連ビューでは、折りたたむには、スキーマのよりコンパクトなビューを提供するのに関連のないスキーマ要素の兄弟要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="4d88e-105">The relevance view uses sibling coalescence to collapse the non-relevant schema elements to provide a more compact view of the schema.</span></span> <span data-ttu-id="4d88e-106">これにより、スクロールし、スキーマとマップを使用するための要件に重点を置く必要があるがさらに削減されます。</span><span class="sxs-lookup"><span data-stu-id="4d88e-106">This further reduces the need of scrolling and helps you focus on your requirement for using schemas and maps.</span></span>  
  
 <span data-ttu-id="4d88e-107">関連ビューがスキーマが無効になっている図は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4d88e-107">The following figure shows a schema when the relevance view is turned OFF.</span></span> <span data-ttu-id="4d88e-108">[スキーマ] ペインには、ノードがリレーションシップの一部がするかしないかどうかに関係なく、すべてのノードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d88e-108">The schema pane displays all nodes, irrespective of whether the nodes are part of any relationship or not.</span></span>  
  
 <span data-ttu-id="4d88e-109">![関連ビューがオフになっている場合は、スキーマ](../core/media/off-schema-relevance-view.gif "Off_Schema_Relevance_View")</span><span class="sxs-lookup"><span data-stu-id="4d88e-109">![Schema when relevance view is switched off](../core/media/off-schema-relevance-view.gif "Off_Schema_Relevance_View")</span></span>  
  
 <span data-ttu-id="4d88e-110">をクリックして、![関連ビューに切り替える](../core/media/mapper-intellitree.gif "Mapper_IntelliTree")関連ビューを有効にするマッパー ユーティリティ リボンのアイコン。</span><span class="sxs-lookup"><span data-stu-id="4d88e-110">Click the ![Switch to relevance view](../core/media/mapper-intellitree.gif "Mapper_IntelliTree") icon on the Mapper utility ribbon to turn the relevance view ON.</span></span> <span data-ttu-id="4d88e-111">いずれかまたは両方、送信元スキーマとターゲット スキーマの関連ビューに切り替えることができます。ソースとターゲット スキーマのそれぞれのアイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4d88e-111">You can switch to relevance view for any one or both the source schema and the target schema; click the respective icons for source and target schemas.</span></span>  
  
 <span data-ttu-id="4d88e-112">スキーマの関連ビューに切り替えると。</span><span class="sxs-lookup"><span data-stu-id="4d88e-112">When you switch to relevance view for a schema:</span></span>  
  
-   <span data-ttu-id="4d88e-113">それらのいずれかのすべてのリンクがないすべてのレコード要素またはその子フィールド要素が折りたたまれています。</span><span class="sxs-lookup"><span data-stu-id="4d88e-113">All the record elements that do not have any links either for them or their child field elements are collapsed.</span></span>  
  
-   <span data-ttu-id="4d88e-114">すべてのリンクがないすべての連続したノードをひとまとめにしては置き換えられます、![ひとまとめにすると非表示ノード](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On")アイコン。</span><span class="sxs-lookup"><span data-stu-id="4d88e-114">All successive nodes that do not have any links are coalesced and are replaced by the ![Coalesced nodes hidden](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On") icon.</span></span> <span data-ttu-id="4d88e-115">BizTalk マッパーは、結合して 2 つの連続する関連のないノードの最小値を検索します。</span><span class="sxs-lookup"><span data-stu-id="4d88e-115">The BizTalk Mapper looks for a minimum of two successive non-relevant nodes that can be coalesced.</span></span> <span data-ttu-id="4d88e-116">まとめられたノードの一覧を表示するアイコンの上、マウスを移動することができます。</span><span class="sxs-lookup"><span data-stu-id="4d88e-116">You can move the mouse over the icon to view the list of coalesced nodes.</span></span> <span data-ttu-id="4d88e-117">まとめられた複数のノードがある場合でも、ヒントは最初の 3 つのまとめられたノードの名前を一覧表示のみに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4d88e-117">Note that the infotip will only list the names of the first three coalesced nodes, even if there are more coalesced nodes.</span></span> <span data-ttu-id="4d88e-118">すべてのノードをクリックして表示することができます、![ひとまとめにすると非表示ノード](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On")アイコン。</span><span class="sxs-lookup"><span data-stu-id="4d88e-118">You can view all the nodes by clicking the ![Coalesced nodes hidden](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On") icon.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4d88e-119">ヒントの詳細については、次を参照してください。[ビュー ヒントとツールヒント方法](../core/how-to-view-infotip-and-tooltip.md)します。</span><span class="sxs-lookup"><span data-stu-id="4d88e-119">For more information about infotip, see [How to View Infotip and Tooltip](../core/how-to-view-infotip-and-tooltip.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4d88e-120">前提条件</span><span class="sxs-lookup"><span data-stu-id="4d88e-120">Prerequisites</span></span>  
 <span data-ttu-id="4d88e-121">この操作では、BizTalk マッパーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d88e-121">This operation requires that BizTalk Mapper is running.</span></span>  
  
## <a name="to-optimize-the-schema-tree-view"></a><span data-ttu-id="4d88e-122">スキーマ ツリー ビューを最適化するには</span><span class="sxs-lookup"><span data-stu-id="4d88e-122">To optimize the schema tree view</span></span>  
 <span data-ttu-id="4d88e-123">マッパー ユーティリティ リボンで、クリックして、それぞれ元/送信先スキーマの関連性ビューでに![関連ビューに切り替える](../core/media/mapper-intellitree.gif "Mapper_IntelliTree")アイコン。</span><span class="sxs-lookup"><span data-stu-id="4d88e-123">On the Mapper utility ribbon, turn ON the relevance view for source and/or target schemas by clicking the respective ![Switch to relevance view](../core/media/mapper-intellitree.gif "Mapper_IntelliTree") icons.</span></span> <span data-ttu-id="4d88e-124">次の図は、オンにすると、関連ビューを同じスキーマを示します。</span><span class="sxs-lookup"><span data-stu-id="4d88e-124">The following figure shows the same schema when the relevance view is turned ON.</span></span> <span data-ttu-id="4d88e-125">すべての関連のないノードに置き換え、![ひとまとめにすると非表示ノード](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On")アイコンでよりコンパクトにスキーマの表示を提供します。</span><span class="sxs-lookup"><span data-stu-id="4d88e-125">All the non-relevant nodes are replaced by the ![Coalesced nodes hidden](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On") icon to provide a more compact view of the schema.</span></span>  
  
 <span data-ttu-id="4d88e-126">![関連ビューが ON の場合、スキーマ](../core/media/on-schema.gif "On_schema")</span><span class="sxs-lookup"><span data-stu-id="4d88e-126">![Schema when relevance view is ON](../core/media/on-schema.gif "On_schema")</span></span>  
  
 <span data-ttu-id="4d88e-127">元または送信先のスキーマにまとめられたノードを展開すると、![ひとまとめにすると非表示ノード](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On")変更![ひとまとめにすると表示されているノード](../core/media/switchoff-mapper-coalesence.jpg "SwitchOff_Mapper_Coalesence")アイコン。</span><span class="sxs-lookup"><span data-stu-id="4d88e-127">When you expand the coalesced nodes in source and/or destination schemas, the ![Coalesced nodes hidden](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On") changes to ![Coalesced nodes shown](../core/media/switchoff-mapper-coalesence.jpg "SwitchOff_Mapper_Coalesence") icon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d88e-128">CTRL + M、CTRL + E または CTRL + M、CTRL + C を展開または送信元スキーマのツリー ノードを折りたたみますキーを押すことができます。</span><span class="sxs-lookup"><span data-stu-id="4d88e-128">You can press CTRL+M, CTRL+E or CTRL+M, CTRL+C to expand or collapse the tree nodes in source schema respectively.</span></span> <span data-ttu-id="4d88e-129">同様に、CTRL + M、CTRL + E または CTRL + M、CTRL + C を展開または送信先スキーマ内のツリー ノードを折りたたみますキーを押すことができます。</span><span class="sxs-lookup"><span data-stu-id="4d88e-129">Similarly, you can press CTRL+M, CTRL+E or CTRL+M, CTRL+C to expand or collapse the tree nodes in destination schema respectively.</span></span> <span data-ttu-id="4d88e-130">ソースまたはターゲットのそれぞれの結合、CTRL + M キー、Ctrl + H または Ctrl + M、Ctrl キーを押しながら D キーを押すこともできます。</span><span class="sxs-lookup"><span data-stu-id="4d88e-130">You can also press Ctrl+M, Ctrl+H or Ctrl+M, Ctrl+D for source or target coalescing respectively.</span></span> <span data-ttu-id="4d88e-131">マッパーのキーボード ショートカットの一覧は、次を参照してください。 [BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)です。</span><span class="sxs-lookup"><span data-stu-id="4d88e-131">For a list of Mapper keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d88e-132">参照</span><span class="sxs-lookup"><span data-stu-id="4d88e-132">See Also</span></span>  
 [<span data-ttu-id="4d88e-133">BizTalk マッパーの強化された機能の使用</span><span class="sxs-lookup"><span data-stu-id="4d88e-133">Using Enhanced Features in BizTalk Mapper</span></span>](../core/using-enhanced-features-in-biztalk-mapper.md)