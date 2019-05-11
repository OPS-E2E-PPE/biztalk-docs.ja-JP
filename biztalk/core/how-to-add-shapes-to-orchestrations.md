---
title: オーケストレーションに図形を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- shapes, orchestrations
- orchestrations, shapes
- Construct Message shape [Orchestration Designer]
- Message Assignment shape [Orchestration Designer]
- Scope shape [Orchestration Designer]
ms.assetid: d39eb12c-cdc6-4918-93d9-536db1dfb889
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ba5e1f6484b1e7e3c268b1461aed1ea6534152b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343208"
---
# <a name="how-to-add-shapes-to-orchestrations"></a><span data-ttu-id="3e412-102">オーケストレーションに図形を追加する方法</span><span class="sxs-lookup"><span data-stu-id="3e412-102">How to Add Shapes to Orchestrations</span></span>
<span data-ttu-id="3e412-103">このセクションでは、追加すると、オーケストレーションに図形を削除する手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="3e412-103">This section describes the procedures for adding and removing shapes in your orchestration.</span></span> <span data-ttu-id="3e412-104">使用できる図形の詳細については、次を参照してください。[オーケストレーション図形](../core/orchestration-shapes.md)します。</span><span class="sxs-lookup"><span data-stu-id="3e412-104">For more information about the available shapes, see [Orchestration Shapes](../core/orchestration-shapes.md).</span></span>  
  
### <a name="to-add-a-shape-to-an-orchestration"></a><span data-ttu-id="3e412-105">オーケストレーションに図形を追加するには</span><span class="sxs-lookup"><span data-stu-id="3e412-105">To add a shape to an orchestration</span></span>  
  
1.  <span data-ttu-id="3e412-106">ツールボックスで、上、 **BizTalk オーケストレーション** タブで、オーケストレーション デザイン画面で図形を区分線にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="3e412-106">In the Toolbox, on the **BizTalk Orchestrations** tab, drag the shape onto a connecting line on the Orchestration Design Surface.</span></span>  
  
     <span data-ttu-id="3e412-107">- または -</span><span class="sxs-lookup"><span data-stu-id="3e412-107">—Or—</span></span>  
  
2.  <span data-ttu-id="3e412-108">区分線または図形を追加する図形のプレース ホルダーを右クリックして をポイント**図形の挿入**を追加する図形の名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e412-108">Right-click the connecting line or the shape placeholder where you want to add the shape, point to **Insert Shape**, and then click the shape name you want to add.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3e412-109">まだ完全に構成されていない図形にスマート タグが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3e412-109">A Smart Tag appears on shapes that are not yet fully configured.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3e412-110">**変換**図形と**メッセージの割り当て**図形内に存在できるのみ、**メッセージの構築**図形。</span><span class="sxs-lookup"><span data-stu-id="3e412-110">**Transform** shapes and **Message Assignment** shapes can only exist within a **Construct Message** shape.</span></span> <span data-ttu-id="3e412-111">これらの図形のいずれかの外側のオーケストレーションに追加するかどうか、**メッセージの構築**図形、新しい内に自動的に配置**メッセージの構築**図形。</span><span class="sxs-lookup"><span data-stu-id="3e412-111">If you add one of these shapes to your orchestration outside of a **Construct Message** shape, it is placed automatically inside a new **Construct Message** shape.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3e412-112">**例外をキャッチ**と**補正**ブロックは、次ののみ存在できます、**スコープ**図形。</span><span class="sxs-lookup"><span data-stu-id="3e412-112">**Catch Exception** and **Compensation** blocks can only exist following a **Scope** shape.</span></span>  
  
### <a name="to-remove-a-shape-from-an-orchestration"></a><span data-ttu-id="3e412-113">オーケストレーションから図形を削除するには</span><span class="sxs-lookup"><span data-stu-id="3e412-113">To remove a shape from an orchestration</span></span>  
  
1.  <span data-ttu-id="3e412-114">デザイン画面で図形を右クリックし、**削除**します。</span><span class="sxs-lookup"><span data-stu-id="3e412-114">Right-click the shape on the design surface, and then click **Delete**.</span></span>  
  
     <span data-ttu-id="3e412-115">- または -</span><span class="sxs-lookup"><span data-stu-id="3e412-115">—Or—</span></span>  
  
2.  <span data-ttu-id="3e412-116">図形を選択してキーを押して、**削除**キー。</span><span class="sxs-lookup"><span data-stu-id="3e412-116">Select the shape and press the **DELETE** key.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e412-117">参照</span><span class="sxs-lookup"><span data-stu-id="3e412-117">See Also</span></span>  
 [<span data-ttu-id="3e412-118">オーケストレーションの作成</span><span class="sxs-lookup"><span data-stu-id="3e412-118">Creating Orchestrations</span></span>](../core/creating-orchestrations.md)