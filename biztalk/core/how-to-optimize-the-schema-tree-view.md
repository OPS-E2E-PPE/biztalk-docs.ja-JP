---
title: スキーマ ツリー ビューを最適化する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ab4ad6b5-5bbd-443b-9041-6cddf9d64735
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aeeddd0893b80c1c7b37b2d0ee5f9f6cd68849d6
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
---
# <a name="how-to-optimize-the-schema-tree-view"></a><span data-ttu-id="efc04-102">スキーマ ツリー ビューを最適化する方法</span><span class="sxs-lookup"><span data-stu-id="efc04-102">How to Optimize the Schema Tree View</span></span>
<span data-ttu-id="efc04-103">使用することができます、 **関連ビュー** 最適化元や送信先スキーマ ツリーに BizTalk マッパーでします。</span><span class="sxs-lookup"><span data-stu-id="efc04-103">You can use the **Relevance View** in BizTalk Mapper to optimize the source and/or target schema trees.</span></span> <span data-ttu-id="efc04-104">このトピックでは、その操作の実行手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="efc04-104">This topic provides instructions about how to perform the operation.</span></span>  
  
 <span data-ttu-id="efc04-105">関連ビューでは、兄弟要素をまとめることにより関連のないスキーマ要素が折りたたまれ、スキーマがよりコンパクトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="efc04-105">The relevance view uses sibling coalescence to collapse the non-relevant schema elements to provide a more compact view of the schema.</span></span> <span data-ttu-id="efc04-106">これにより、スクロール操作が減り、スキーマやマップの使用要件に集中しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="efc04-106">This further reduces the need of scrolling and helps you focus on your requirement for using schemas and maps.</span></span>  
  
 <span data-ttu-id="efc04-107">次の図は、関連ビューが無効になっている場合のスキーマです。</span><span class="sxs-lookup"><span data-stu-id="efc04-107">The following figure shows a schema when the relevance view is turned OFF.</span></span> <span data-ttu-id="efc04-108">スキーマ ペインには、ノードがリレーションシップの一部であるかどうかは関係なく、すべてのノードが表示されています。</span><span class="sxs-lookup"><span data-stu-id="efc04-108">The schema pane displays all nodes, irrespective of whether the nodes are part of any relationship or not.</span></span>  
  
 <span data-ttu-id="efc04-109">![関連ビューがオフになっている場合は、スキーマ](../core/media/off-schema-relevance-view.gif "Off_Schema_Relevance_View")</span><span class="sxs-lookup"><span data-stu-id="efc04-109">![Schema when relevance view is switched off](../core/media/off-schema-relevance-view.gif "Off_Schema_Relevance_View")</span></span>  
  
 <span data-ttu-id="efc04-110">クリックして、![関連ビューに切り替える](../core/media/mapper-intellitree.gif "Mapper_IntelliTree")関連ビューをオンにするマッパー ユーティリティ リボンのアイコン。</span><span class="sxs-lookup"><span data-stu-id="efc04-110">Click the ![Switch to relevance view](../core/media/mapper-intellitree.gif "Mapper_IntelliTree") icon on the Mapper utility ribbon to turn the relevance view ON.</span></span> <span data-ttu-id="efc04-111">送信元スキーマと送信先スキーマのそれぞれのアイコンをクリックすることで、送信元スキーマや送信先スキーマのいずれかまたは両方を関連ビューに切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="efc04-111">You can switch to relevance view for any one or both the source schema and the target schema; click the respective icons for source and target schemas.</span></span>  
  
 <span data-ttu-id="efc04-112">スキーマの関連ビューに切り替えると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="efc04-112">When you switch to relevance view for a schema:</span></span>  
  
-   <span data-ttu-id="efc04-113">その要素またはその子フィールド要素についてのリンクがないレコード要素はすべて折りたたまれます。</span><span class="sxs-lookup"><span data-stu-id="efc04-113">All the record elements that do not have any links either for them or their child field elements are collapsed.</span></span>  
  
-   <span data-ttu-id="efc04-114">すべてのリンクを持たないすべての連続したノードとして結合し、は置き換えられます、![ノードの非表示に結合された](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On")アイコン。</span><span class="sxs-lookup"><span data-stu-id="efc04-114">All successive nodes that do not have any links are coalesced and are replaced by the ![Coalesced nodes hidden](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On") icon.</span></span> <span data-ttu-id="efc04-115">BizTalk マッパーでは、関連のない 2 つ以上連続したノードを見つけて、1 つにまとめます。</span><span class="sxs-lookup"><span data-stu-id="efc04-115">The BizTalk Mapper looks for a minimum of two successive non-relevant nodes that can be coalesced.</span></span> <span data-ttu-id="efc04-116">アイコンの上にマウス ポインターを置くと、まとめられたノードの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="efc04-116">You can move the mouse over the icon to view the list of coalesced nodes.</span></span> <span data-ttu-id="efc04-117">多数のノードが 1 つにまとめられているとしても、ヒントに表示されるのは、そのうち最初の 3 つのノードの名前だけです。</span><span class="sxs-lookup"><span data-stu-id="efc04-117">Note that the infotip will only list the names of the first three coalesced nodes, even if there are more coalesced nodes.</span></span> <span data-ttu-id="efc04-118">クリックしてすべてのノードを表示することができます、![ノードの非表示に結合された](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On")アイコン。</span><span class="sxs-lookup"><span data-stu-id="efc04-118">You can view all the nodes by clicking the ![Coalesced nodes hidden](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On") icon.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="efc04-119">ヒントの詳細については、次を参照してください。[ビュー ヒントとツールヒント ハウツー](../core/how-to-view-infotip-and-tooltip.md)です。</span><span class="sxs-lookup"><span data-stu-id="efc04-119">For more information about infotip, see [How to View Infotip and Tooltip](../core/how-to-view-infotip-and-tooltip.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="efc04-120">前提条件</span><span class="sxs-lookup"><span data-stu-id="efc04-120">Prerequisites</span></span>  
 <span data-ttu-id="efc04-121">この操作では、BizTalk マッパーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="efc04-121">This operation requires that BizTalk Mapper is running.</span></span>  
  
## <a name="to-optimize-the-schema-tree-view"></a><span data-ttu-id="efc04-122">スキーマのツリー ビューを最適化するには</span><span class="sxs-lookup"><span data-stu-id="efc04-122">To optimize the schema tree view</span></span>  
 <span data-ttu-id="efc04-123">マッパー ユーティリティ リボンで、送信元/送信先スキーマの関連ビューをクリックしてにそれぞれ![関連ビューに切り替える](../core/media/mapper-intellitree.gif "Mapper_IntelliTree")アイコン。</span><span class="sxs-lookup"><span data-stu-id="efc04-123">On the Mapper utility ribbon, turn ON the relevance view for source and/or target schemas by clicking the respective ![Switch to relevance view](../core/media/mapper-intellitree.gif "Mapper_IntelliTree") icons.</span></span> <span data-ttu-id="efc04-124">次の図は、関連ビューが有効になっている場合の同じスキーマです。</span><span class="sxs-lookup"><span data-stu-id="efc04-124">The following figure shows the same schema when the relevance view is turned ON.</span></span> <span data-ttu-id="efc04-125">関連のないすべてのノードは置き換え、![ノードの非表示に結合された](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On")アイコンでよりコンパクトなスキーマのビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="efc04-125">All the non-relevant nodes are replaced by the ![Coalesced nodes hidden](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On") icon to provide a more compact view of the schema.</span></span>  
  
 <span data-ttu-id="efc04-126">![関連ビューが ON の場合、スキーマ](../core/media/on-schema.gif "On_schema")</span><span class="sxs-lookup"><span data-stu-id="efc04-126">![Schema when relevance view is ON](../core/media/on-schema.gif "On_schema")</span></span>  
  
 <span data-ttu-id="efc04-127">送信元または送信先のスキーマのまとめられたノードを展開すると、![ノードの非表示に結合された](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On")変更![表示されているノードに結合された](../core/media/switchoff-mapper-coalesence.jpg "SwitchOff_Mapper_Coalesence")アイコン。</span><span class="sxs-lookup"><span data-stu-id="efc04-127">When you expand the coalesced nodes in source and/or destination schemas, the ![Coalesced nodes hidden](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On") changes to ![Coalesced nodes shown](../core/media/switchoff-mapper-coalesence.jpg "SwitchOff_Mapper_Coalesence") icon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="efc04-128">Ctrl + M キー、Ctrl + E キーを押すと送信元スキーマのツリー ノードが展開され、Ctrl + M キー、Ctrl + C キーを押すと、折りたたまれます。</span><span class="sxs-lookup"><span data-stu-id="efc04-128">You can press CTRL+M, CTRL+E or CTRL+M, CTRL+C to expand or collapse the tree nodes in source schema respectively.</span></span> <span data-ttu-id="efc04-129">同様に、Ctrl + M キー、Ctrl + E キーを押すと送信先スキーマのツリー ノードが展開され、Ctrl + M キー、Ctrl + C キーを押すと、折りたたまれます。</span><span class="sxs-lookup"><span data-stu-id="efc04-129">Similarly, you can press CTRL+M, CTRL+E or CTRL+M, CTRL+C to expand or collapse the tree nodes in destination schema respectively.</span></span> <span data-ttu-id="efc04-130">また、送信元または送信先のまとめられたノードについても、それぞれ Ctrl + M キー、Ctrl + H キーまたは Ctrl + M キー、Ctrl + D キーを押すことができます。</span><span class="sxs-lookup"><span data-stu-id="efc04-130">You can also press Ctrl+M, Ctrl+H or Ctrl+M, Ctrl+D for source or target coalescing respectively.</span></span> <span data-ttu-id="efc04-131">マッパーのキーボード ショートカットの一覧は、次を参照してください。 [BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)です。</span><span class="sxs-lookup"><span data-stu-id="efc04-131">For a list of Mapper keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efc04-132">参照</span><span class="sxs-lookup"><span data-stu-id="efc04-132">See Also</span></span>  
 [<span data-ttu-id="efc04-133">BizTalk マッパーで強化された機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="efc04-133">Using Enhanced Features in BizTalk Mapper</span></span>](../core/using-enhanced-features-in-biztalk-mapper.md)