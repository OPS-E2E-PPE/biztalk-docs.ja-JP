---
title: マップ項目を強調する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2732b36-ca57-4566-ba26-da27a3082f32
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5be500ad36b27848733863ffde1a648d42c7db17
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385147"
---
# <a name="how-to-emphasize-map-items"></a><span data-ttu-id="3d662-102">マップ項目を強調する方法</span><span class="sxs-lookup"><span data-stu-id="3d662-102">How to Emphasize Map Items</span></span>
<span data-ttu-id="3d662-103">BizTalk マッパーでマップ アイテムを選択すると、すべての関連するリンクと functoid が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="3d662-103">In the BizTalk Mapper, when you select a map item, all the associated links and functoids are emphasized.</span></span> <span data-ttu-id="3d662-104">これはリレーションシップと関連するスキーマ項目を識別するが難しいマップ リンクが多数に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3d662-104">This is useful in maps with many links, where it is difficult to identify a relationship and the related schema items.</span></span>  
  
 <span data-ttu-id="3d662-105">リンク、functoid、またはスキーマ要素を選択すると、BizTalk マッパーは、関連するリレーションシップとスキーマ要素を強調します。</span><span class="sxs-lookup"><span data-stu-id="3d662-105">When you select a link, a functoid, or a schema element, the BizTalk Mapper emphasizes the related relationship and schema elements.</span></span> <span data-ttu-id="3d662-106">選択したマップ項目の太字で強調表示は、受信リンクと送信リンクが (再帰的に) すべてと他のすべてのマップ項目がグレーします。次のスクリーン ショットが太字で選択したマップ項目を表示し、色とその他のマップ項目が明るきます。</span><span class="sxs-lookup"><span data-stu-id="3d662-106">For the selected map item, all the incoming links and the outgoing links (recursively) are highlighted in bold, and all the other map items are greyed out. The following screenshot shows the selected map item in bold and color and the other map items appear lighter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3d662-107">このコンテキストでは、関連するリレーションシップは、直接または間接的には、選択したマップ項目にリンクされているすべてのリンク、functoid、またはスキーマ要素を意味します。</span><span class="sxs-lookup"><span data-stu-id="3d662-107">In this context, a related relationship means all the links, functoids, or schema elements directly or indirectly linked to the selected map item.</span></span>  
  
 <span data-ttu-id="3d662-108">![マップ項目の強調](../core/media/mapper-intelliselect.gif "Mapper_IntelliSelect")</span><span class="sxs-lookup"><span data-stu-id="3d662-108">![Emphasizing a map item](../core/media/mapper-intelliselect.gif "Mapper_IntelliSelect")</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3d662-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="3d662-109">Prerequisites</span></span>  
 <span data-ttu-id="3d662-110">この操作では、BizTalk マッパーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d662-110">This operation requires that BizTalk Mapper is running.</span></span>  
  
## <a name="to-emphasize-a-map-item"></a><span data-ttu-id="3d662-111">マップ項目を強調するには</span><span class="sxs-lookup"><span data-stu-id="3d662-111">To emphasize a map item</span></span>  
  
-   <span data-ttu-id="3d662-112">マップ アイテム (リンク、functoid、またはスキーマ要素) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3d662-112">Click a map item (a link, a functoid, or a schema element).</span></span> <span data-ttu-id="3d662-113">その他のすべてのリンクと functoid (スキーマ ノードを含む) に関連付けられた現在のグリッド ページで選択したマップ項目が強調表示されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="3d662-113">You can see that all the other links and functoids (including the schema nodes) associated with the selected map item in the current grid page are highlighted.</span></span>  
  
     <span data-ttu-id="3d662-114">場合によっては、選択したノードのある可能性がありますの他のグリッド ページ内に存在するリレーションシップ。</span><span class="sxs-lookup"><span data-stu-id="3d662-114">Sometimes, for the selected node, there might be relationships existing in other grid pages.</span></span> <span data-ttu-id="3d662-115">このような場合は、BizTalk マッパーは現在のグリッド ページ内のインスタンスが強調しも選択したノードに関連するリレーションシップが存在するページのタブが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="3d662-115">In such a case, the BizTalk Mapper emphasizes the instance in current grid page and also highlights the page tab where the other related relationship to the selected node exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d662-116">参照</span><span class="sxs-lookup"><span data-stu-id="3d662-116">See Also</span></span>  
 [<span data-ttu-id="3d662-117">BizTalk マッパーの強化された機能の使用</span><span class="sxs-lookup"><span data-stu-id="3d662-117">Using Enhanced Features in BizTalk Mapper</span></span>](../core/using-enhanced-features-in-biztalk-mapper.md)