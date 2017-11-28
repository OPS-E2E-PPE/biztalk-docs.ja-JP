---
title: "移動してノードをコピーする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4f1ec14-c607-4da3-9139-73a61963b819
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a55901e9ba6b27d05dccce0e547df618123ab466
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-move-and-copy-nodes"></a><span data-ttu-id="83c87-102">移動してノードをコピーする方法</span><span class="sxs-lookup"><span data-stu-id="83c87-102">How to Move and Copy Nodes</span></span>
<span data-ttu-id="83c87-103">既存のノードは、スキーマ ツリー内の別の場所に移動できます。</span><span class="sxs-lookup"><span data-stu-id="83c87-103">You will probably encounter situations where you want to move an existing node to a different location in the schema tree.</span></span> <span data-ttu-id="83c87-104">また、既存のノードをコピーして、スキーマ ツリー内の別の場所に貼り付けることによって作業を効率化することもできます。</span><span class="sxs-lookup"><span data-stu-id="83c87-104">You might also be able to save time by making a copy of an existing node and then pasting it into a different location in the schema tree.</span></span> <span data-ttu-id="83c87-105">このトピックでは、ノードの移動やコピーの操作手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="83c87-105">This topic provides step-by-step instructions for performing these tasks.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="83c87-106">BizTalk エディターでは、スキーマ内でのみノードのコピーと貼り付けができます。あるスキーマから別のスキーマにノードをコピーし、貼り付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="83c87-106">BizTalk Editor supports copying and pasting nodes only within schemas, not between schemas.</span></span>  
  
### <a name="to-move-a-node-within-a-schema"></a><span data-ttu-id="83c87-107">スキーマ内でノードを移動するには</span><span class="sxs-lookup"><span data-stu-id="83c87-107">To move a node within a schema</span></span>  
  
1.  <span data-ttu-id="83c87-108">あらかじめスキーマ ツリーを展開し、移動するノードと、移動先の場所を表示しておきます。</span><span class="sxs-lookup"><span data-stu-id="83c87-108">If necessary, expand the schema tree to show both the node you are moving and the location to which you want to move it.</span></span> <span data-ttu-id="83c87-109">展開と折りたたみ、スキーマ ツリー ビューの詳細については、次を参照してください。[スキーマ ツリー ビューの管理](../core/how-to-manage-the-schema-tree-view.md)です。</span><span class="sxs-lookup"><span data-stu-id="83c87-109">For more information about expanding and collapsing the schema tree view, see [Managing the Schema Tree View](../core/how-to-manage-the-schema-tree-view.md).</span></span>  
  
2.  <span data-ttu-id="83c87-110">移動するノードをクリックし、ツリー内の別の場所にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="83c87-110">Click and hold the node that you want to move and drag it to another location in the tree.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="83c87-111">スキーマ ツリー内でノードを上下にドラッグすると、その位置に応じてマウス ポインターの形状が変化します。</span><span class="sxs-lookup"><span data-stu-id="83c87-111">When you begin to drag the node up and down the schema tree, the mouse pointer changes to an Up, Down, or child arrow.</span></span> <span data-ttu-id="83c87-112">この矢印は、マウス ボタンを離したときにノードが挿入される位置 (ノードの前に挿入されるか、ノードの後に挿入されるか、またはノードの子として挿入されるか) を示しています。</span><span class="sxs-lookup"><span data-stu-id="83c87-112">This arrow indicates where the node will be placed when you release the mouse button, either before the node, after the node, or as a child of the node.</span></span>  
  
#### <a name="to-copy-a-node-within-a-schema"></a><span data-ttu-id="83c87-113">スキーマ内でノードをコピーするには</span><span class="sxs-lookup"><span data-stu-id="83c87-113">To copy a node within a schema</span></span>  
  
1.  <span data-ttu-id="83c87-114">コピー、およびをクリックするノードを右クリックして**コピー**です。</span><span class="sxs-lookup"><span data-stu-id="83c87-114">Right-click the node that you want to copy, and then click **Copy**.</span></span>  
  
2.  <span data-ttu-id="83c87-115">右クリックし、**レコード**コピーしたノードを挿入し、をクリックするノードまたはグループ ノード**貼り付け**です。</span><span class="sxs-lookup"><span data-stu-id="83c87-115">Right-click the **Record** node or group node into which you want to insert the copied node, and then click **Paste**.</span></span>  
  
     <span data-ttu-id="83c87-116">子ノードの最後にコピーされたノードのコピーが置かれる、**レコード**ノードまたは手順 2. で選択したグループ ノード。</span><span class="sxs-lookup"><span data-stu-id="83c87-116">The copy of the copied node is placed at the end of the child nodes of the **Record** node or group node you selected in step 2.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="83c87-117">切り取り/コピー/貼り付けの機能は、単一のスキーマ内でのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="83c87-117">You may only use cut/copy/paste functionality within a single schema.</span></span> <span data-ttu-id="83c87-118">つまり、あるスキーマから別のスキーマへノードをコピーすることはできません。</span><span class="sxs-lookup"><span data-stu-id="83c87-118">In other words, you cannot copy nodes from one schema into another schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83c87-119">参照</span><span class="sxs-lookup"><span data-stu-id="83c87-119">See Also</span></span>  
 [<span data-ttu-id="83c87-120">既存のノードの操作</span><span class="sxs-lookup"><span data-stu-id="83c87-120">Working with Existing Nodes</span></span>](../core/working-with-existing-nodes.md)