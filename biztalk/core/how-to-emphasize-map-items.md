---
title: マップ項目を強調する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2732b36-ca57-4566-ba26-da27a3082f32
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6bb03969a044c6a474f5d2d1c1e5e1a5067cf81
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
---
# <a name="how-to-emphasize-map-items"></a><span data-ttu-id="298aa-102">マップ項目を強調する方法</span><span class="sxs-lookup"><span data-stu-id="298aa-102">How to Emphasize Map Items</span></span>
<span data-ttu-id="298aa-103">BizTalk マッパーでマップ項目を選択すると、関連付けられたすべてのリンクと Functoid が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="298aa-103">In the BizTalk Mapper, when you select a map item, all the associated links and functoids are emphasized.</span></span> <span data-ttu-id="298aa-104">これは、マップに多くのリンクが設定されていて、リレーションシップや関連するスキーマ項目を識別するのが難しい場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="298aa-104">This is useful in maps with many links, where it is difficult to identify a relationship and the related schema items.</span></span>  
  
 <span data-ttu-id="298aa-105">BizTalk マッパーでリンク、Functoid、またはスキーマ要素を選択すると、関連するリレーションシップとスキーマ要素が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="298aa-105">When you select a link, a functoid, or a schema element, the BizTalk Mapper emphasizes the related relationship and schema elements.</span></span> <span data-ttu-id="298aa-106">選択したマップ項目について、すべての受信リンクと送信リンクが (再帰的に) 太く強調され、その他すべてのマップ項目はグレー表示されます。次のスクリーンショットは、選択されたマップ項目が太くカラーで表示され、その他のマップ項目が薄く表示された状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="298aa-106">For the selected map item, all the incoming links and the outgoing links (recursively) are highlighted in bold, and all the other map items are greyed out. The following screenshot shows the selected map item in bold and color and the other map items appear lighter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="298aa-107">ここでの関連するリレーションシップとは、選択されたマップ項目に直接または間接的にリンクされたリンク、Functoid、またはスキーマ要素を意味します。</span><span class="sxs-lookup"><span data-stu-id="298aa-107">In this context, a related relationship means all the links, functoids, or schema elements directly or indirectly linked to the selected map item.</span></span>  
  
 <span data-ttu-id="298aa-108">![マップ項目の強調](../core/media/mapper-intelliselect.gif "Mapper_IntelliSelect")</span><span class="sxs-lookup"><span data-stu-id="298aa-108">![Emphasizing a map item](../core/media/mapper-intelliselect.gif "Mapper_IntelliSelect")</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="298aa-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="298aa-109">Prerequisites</span></span>  
 <span data-ttu-id="298aa-110">この操作では、BizTalk マッパーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="298aa-110">This operation requires that BizTalk Mapper is running.</span></span>  
  
## <a name="to-emphasize-a-map-item"></a><span data-ttu-id="298aa-111">マップ項目を強調表示するには</span><span class="sxs-lookup"><span data-stu-id="298aa-111">To emphasize a map item</span></span>  
  
-   <span data-ttu-id="298aa-112">マップ項目 (リンク、Functoid、またはスキーマ要素) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="298aa-112">Click a map item (a link, a functoid, or a schema element).</span></span> <span data-ttu-id="298aa-113">その他のすべてのリンクおよび functoid (スキーマのノードを含む) の現在のグリッド ページで選択されているマップ アイテムに関連付けられているが強調表示されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="298aa-113">You can see that all the other links and functoids (including the schema nodes) associated with the selected map item in the current grid page are highlighted.</span></span>  
  
     <span data-ttu-id="298aa-114">選択されたノードには、他のグリッド ページにもリレーションシップが存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="298aa-114">Sometimes, for the selected node, there might be relationships existing in other grid pages.</span></span> <span data-ttu-id="298aa-115">そのような場合、BizTalk マッパーでは現在のグリッド ページ内のインスタンスが強調表示されることに加えて、選択したノードと関連するリレーションシップが存在するページのタブも強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="298aa-115">In such a case, the BizTalk Mapper emphasizes the instance in current grid page and also highlights the page tab where the other related relationship to the selected node exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="298aa-116">参照</span><span class="sxs-lookup"><span data-stu-id="298aa-116">See Also</span></span>  
 [<span data-ttu-id="298aa-117">BizTalk マッパーで強化された機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="298aa-117">Using Enhanced Features in BizTalk Mapper</span></span>](../core/using-enhanced-features-in-biztalk-mapper.md)