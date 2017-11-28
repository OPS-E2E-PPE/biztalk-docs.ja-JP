---
title: "同時に複数のノードを操作する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a44d11c-c6f9-4825-b89d-d1b3c3357931
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9efc8c6205b0724820d0395dde39924c55a861f9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-work-with-multiple-nodes-simultaneously"></a><span data-ttu-id="4cb84-102">同時に複数のノードを操作する方法</span><span class="sxs-lookup"><span data-stu-id="4cb84-102">How to Work with Multiple Nodes Simultaneously</span></span>
<span data-ttu-id="4cb84-103">一部の操作を複数のノードで同時に行うことができます。ただし、関連するノードをすべて選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cb84-103">Some operations can be performed on multiple nodes simultaneously, but the relevant nodes must all be selected.</span></span> <span data-ttu-id="4cb84-104">このトピックでは、複数のノードを同時に操作する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4cb84-104">This topic provides instructions about how to work with multiple nodes simultaneously.</span></span>  
  
### <a name="to-select-multiple-nodes-that-are-not-adjacent"></a><span data-ttu-id="4cb84-105">隣接していない複数のノードを選択するには</span><span class="sxs-lookup"><span data-stu-id="4cb84-105">To select multiple nodes that are not adjacent</span></span>  
  
1.  <span data-ttu-id="4cb84-106">選択対象となる複数のノードの、最初のノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="4cb84-106">Select the first node in the set of nonadjacent nodes to be selected at the same time.</span></span>  
  
2.  <span data-ttu-id="4cb84-107"><localizedText>Ctrl</localizedText> キーを押しながら、残りの対象ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="4cb84-107">Press and hold CTRL and then select the remaining nodes in the set of nonadjacent nodes to be selected at the same time.</span></span>  
  
     <span data-ttu-id="4cb84-108">これで、隣接していないノードが同時にすべて選択されます。</span><span class="sxs-lookup"><span data-stu-id="4cb84-108">The nonadjacent nodes are all selected at the same time.</span></span>  
  
### <a name="to-select-a-range-of-adjacent-nodes"></a><span data-ttu-id="4cb84-109">隣接しているノードをまとめて選択するには</span><span class="sxs-lookup"><span data-stu-id="4cb84-109">To select a range of adjacent nodes</span></span>  
  
1.  <span data-ttu-id="4cb84-110">同時に選択する隣接するノードのセットの 1 つの極端な例として、ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="4cb84-110">Select the node at one extreme of the set of adjacent nodes to be selected at the same time.</span></span>  
  
2.  <span data-ttu-id="4cb84-111"><localizedText>Shift</localizedText> キーを押しながら、選択対象となる最後のノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="4cb84-111">Press and hold SHIFT and then select the node at the other extreme of the set of nodes to be selected at the same time.</span></span>  
  
     <span data-ttu-id="4cb84-112">手順 1. および手順 2. で選択したノードによって指定された範囲内の隣接しているノードが、同時にすべて選択されます。</span><span class="sxs-lookup"><span data-stu-id="4cb84-112">The range of adjacent nodes defined by the nodes selected in steps 1 and 2 are all selected at the same time.</span></span>  
  
### <a name="to-modify-property-values-of-simultaneously-selected-nodes"></a><span data-ttu-id="4cb84-113">同時に選択したノードのプロパティの値を変更するには</span><span class="sxs-lookup"><span data-stu-id="4cb84-113">To modify property values of simultaneously selected nodes</span></span>  
  
1.  <span data-ttu-id="4cb84-114">隣接していない複数のノードを選択するには"するには」の手順に従って、複数のノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="4cb84-114">Select multiple nodes, as described in the procedure "To select multiple nodes that are not adjacent".</span></span> <span data-ttu-id="4cb84-115">前述の「します。</span><span class="sxs-lookup"><span data-stu-id="4cb84-115">earlier in this document.</span></span>  
  
2.  <span data-ttu-id="4cb84-116">関連するプロパティ値を変更、**プロパティ**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="4cb84-116">Modify the relevant property values in the **Properties** window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4cb84-117">選択したノードすべてに共通のプロパティのみ、同時に変更できます。</span><span class="sxs-lookup"><span data-stu-id="4cb84-117">Only properties common to all selected nodes can be changed simultaneously.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cb84-118">参照</span><span class="sxs-lookup"><span data-stu-id="4cb84-118">See Also</span></span>  
 [<span data-ttu-id="4cb84-119">既存のノードの操作</span><span class="sxs-lookup"><span data-stu-id="4cb84-119">Working with Existing Nodes</span></span>](../core/working-with-existing-nodes.md)