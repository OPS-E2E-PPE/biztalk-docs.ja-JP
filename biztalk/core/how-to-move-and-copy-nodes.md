---
title: ノードのコピーに移動する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e4f1ec14-c607-4da3-9139-73a61963b819
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe123de8a55635aa06fc5f08ccc525690d945ec9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384529"
---
# <a name="how-to-move-and-copy-nodes"></a><span data-ttu-id="3bb7f-102">ノードのコピーと移動する方法</span><span class="sxs-lookup"><span data-stu-id="3bb7f-102">How to Move and Copy Nodes</span></span>
<span data-ttu-id="3bb7f-103">既存のノードをスキーマ ツリーの別の場所に移動する必要がある場合は発生可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3bb7f-103">You will probably encounter situations where you want to move an existing node to a different location in the schema tree.</span></span> <span data-ttu-id="3bb7f-104">既存のノードのコピーを作成し、スキーマ ツリーの別の場所に貼り付けたり、時間を節約できる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3bb7f-104">You might also be able to save time by making a copy of an existing node and then pasting it into a different location in the schema tree.</span></span> <span data-ttu-id="3bb7f-105">このトピックでは、これらのタスクを実行する手順を提供します。</span><span class="sxs-lookup"><span data-stu-id="3bb7f-105">This topic provides step-by-step instructions for performing these tasks.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3bb7f-106">BizTalk エディターでは、コピーと貼り付けノードのスキーマ間ではなく、スキーマ内でのみサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3bb7f-106">BizTalk Editor supports copying and pasting nodes only within schemas, not between schemas.</span></span>  
  
### <a name="to-move-a-node-within-a-schema"></a><span data-ttu-id="3bb7f-107">スキーマ内のノードを移動するには</span><span class="sxs-lookup"><span data-stu-id="3bb7f-107">To move a node within a schema</span></span>  
  
1.  <span data-ttu-id="3bb7f-108">必要に応じて、ノードを移動して移動する場所の両方を表示するには、あるスキーマ ツリーを展開します。</span><span class="sxs-lookup"><span data-stu-id="3bb7f-108">If necessary, expand the schema tree to show both the node you are moving and the location to which you want to move it.</span></span> <span data-ttu-id="3bb7f-109">展開と折りたたみ、スキーマ ツリー ビューの詳細については、次を参照してください。[スキーマ ツリー ビューの管理](../core/how-to-manage-the-schema-tree-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="3bb7f-109">For more information about expanding and collapsing the schema tree view, see [Managing the Schema Tree View](../core/how-to-manage-the-schema-tree-view.md).</span></span>  
  
2.  <span data-ttu-id="3bb7f-110">移動し、ツリーの別の場所にドラッグするノードを押したままにします。</span><span class="sxs-lookup"><span data-stu-id="3bb7f-110">Click and hold the node that you want to move and drag it to another location in the tree.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3bb7f-111">ダウン、上下をマウス ポインターであるスキーマ ツリー ノードのドラッグを開始すると、または子矢印。</span><span class="sxs-lookup"><span data-stu-id="3bb7f-111">When you begin to drag the node up and down the schema tree, the mouse pointer changes to an Up, Down, or child arrow.</span></span> <span data-ttu-id="3bb7f-112">この矢印は、ノードの後に、またはノードの子として、ノードの前にいずれかのマウス ボタンを放すと、ノードを配置する場所を示します。</span><span class="sxs-lookup"><span data-stu-id="3bb7f-112">This arrow indicates where the node will be placed when you release the mouse button, either before the node, after the node, or as a child of the node.</span></span>  
  
#### <a name="to-copy-a-node-within-a-schema"></a><span data-ttu-id="3bb7f-113">スキーマ内のノードをコピーするには</span><span class="sxs-lookup"><span data-stu-id="3bb7f-113">To copy a node within a schema</span></span>  
  
1.  <span data-ttu-id="3bb7f-114">コピーするをクリックするノードを右クリックして**コピー**します。</span><span class="sxs-lookup"><span data-stu-id="3bb7f-114">Right-click the node that you want to copy, and then click **Copy**.</span></span>  
  
2.  <span data-ttu-id="3bb7f-115">右クリックし、**レコード**コピーのノードを挿入し、クリックするノードまたはグループ ノード**貼り付け**します。</span><span class="sxs-lookup"><span data-stu-id="3bb7f-115">Right-click the **Record** node or group node into which you want to insert the copied node, and then click **Paste**.</span></span>  
  
     <span data-ttu-id="3bb7f-116">子ノードの最後にコピーされたノードのコピーが置かれる、**レコード**ノードまたは手順 2 で選択したグループ ノード。</span><span class="sxs-lookup"><span data-stu-id="3bb7f-116">The copy of the copied node is placed at the end of the child nodes of the **Record** node or group node you selected in step 2.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3bb7f-117">1 つのスキーマ内での切り取り/コピー/貼り付け機能のみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="3bb7f-117">You may only use cut/copy/paste functionality within a single schema.</span></span> <span data-ttu-id="3bb7f-118">つまり、別のスキーマに 1 つのスキーマからノードをコピーすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3bb7f-118">In other words, you cannot copy nodes from one schema into another schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bb7f-119">参照</span><span class="sxs-lookup"><span data-stu-id="3bb7f-119">See Also</span></span>  
 [<span data-ttu-id="3bb7f-120">既存のノードの操作</span><span class="sxs-lookup"><span data-stu-id="3bb7f-120">Working with Existing Nodes</span></span>](../core/working-with-existing-nodes.md)