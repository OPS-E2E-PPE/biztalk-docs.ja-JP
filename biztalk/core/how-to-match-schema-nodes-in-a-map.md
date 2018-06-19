---
title: マップ内のスキーマのノードを照合する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 584f85d2-6198-4ef3-90d9-a322f1457d9a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1e2ce880489ca49b0b55d2e6f45b9e887d719a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22253938"
---
# <a name="how-to-match-schema-nodes-in-a-map"></a><span data-ttu-id="06d7f-102">マップ内のスキーマ ノードを照合する方法</span><span class="sxs-lookup"><span data-stu-id="06d7f-102">How to Match Schema Nodes in a Map</span></span>
<span data-ttu-id="06d7f-103">送信元スキーマまたは送信先スキーマが複雑な場合、要素をマップするのが難しいことがあります。</span><span class="sxs-lookup"><span data-stu-id="06d7f-103">When the source or destination schemas are complex, it can be difficult to map the elements.</span></span> <span data-ttu-id="06d7f-104">BizTalk マッパー、**指示一致**機能で、最適な一致を指摘することで複雑なスキーマ要素をマップすることができます。</span><span class="sxs-lookup"><span data-stu-id="06d7f-104">The BizTalk Mapper introduces the **Indicative Match** feature, which enables you to map complex schema elements by suggesting the best possible matches.</span></span> <span data-ttu-id="06d7f-105">このトピックでは、次の操作を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="06d7f-105">This topic provides information about how to perform this operation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="06d7f-106">BizTalk マッパーは、スキーマ ノードに対して可能性のある一致を示します。</span><span class="sxs-lookup"><span data-stu-id="06d7f-106">The BizTalk Mapper suggests possible matches for a schema node.</span></span> <span data-ttu-id="06d7f-107">現在、この機能は English 名についてのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="06d7f-107">This feature is currently supported only for English names.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="06d7f-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="06d7f-108">Prerequisites</span></span>  
 <span data-ttu-id="06d7f-109">作業を行うには、BizTalk マッパーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="06d7f-109">These instructions require that the BizTalk Mapper is running.</span></span>  
  
### <a name="to-match-relevant-schema-nodes"></a><span data-ttu-id="06d7f-110">関連するスキーマ ノードを一致させるには</span><span class="sxs-lookup"><span data-stu-id="06d7f-110">To match relevant schema nodes</span></span>  
  
1.  <span data-ttu-id="06d7f-111">最善の一致を調べることや、をクリックする必要のあるスキーマ要素を右クリックして**指示一致**です。</span><span class="sxs-lookup"><span data-stu-id="06d7f-111">Select and right-click the schema element for which you need to know the best matches, and then click **Indicate Matches**.</span></span> <span data-ttu-id="06d7f-112">BizTalk マッパーで、最善の一致 (7 つ) が強調表示され、その中で最適な一致が選択されます。</span><span class="sxs-lookup"><span data-stu-id="06d7f-112">The BizTalk Mapper highlights the best matches (restricted to seven), with the most optimum match selected.</span></span>  
  
     <span data-ttu-id="06d7f-113">または、選択することができます**指示一致**BizTalk メニュー、または SHIFT キーを押し + スペース キー。</span><span class="sxs-lookup"><span data-stu-id="06d7f-113">Alternatively, you can select **Indicate Matches** from the BizTalk menu, or press SHIFT + SPACE keys.</span></span>  
  
     <span data-ttu-id="06d7f-114">次の図は、送信先スキーマで選択したノードの推奨一致を示したものです。</span><span class="sxs-lookup"><span data-stu-id="06d7f-114">The following figure shows suggestive matches for the selected node in destination schema.</span></span>  
  
     <span data-ttu-id="06d7f-115">![推奨マッピング](../core/media/suggestive-mapping.gif "Suggestive_Mapping")</span><span class="sxs-lookup"><span data-stu-id="06d7f-115">![Suggestive mapping](../core/media/suggestive-mapping.gif "Suggestive_Mapping")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="06d7f-116">推奨一致の間を移動するには、Shift キーを押します。</span><span class="sxs-lookup"><span data-stu-id="06d7f-116">Hold down the SHIFT key to traverse among the suggestive matches.</span></span>  
  
2.  <span data-ttu-id="06d7f-117">ここでは次の操作が可能です。</span><span class="sxs-lookup"><span data-stu-id="06d7f-117">You can now do the following:</span></span>  
  
    -   <span data-ttu-id="06d7f-118">Enter キーを押して、強調表示されている (可能な範囲で最善の) 一致を確定します。</span><span class="sxs-lookup"><span data-stu-id="06d7f-118">Press ENTER to confirm the highlighted (best possible) match.</span></span>  
  
    -   <span data-ttu-id="06d7f-119">上下矢印キーを使用して、強調表示されている一致の間を優先順位の順序で循環移動します。</span><span class="sxs-lookup"><span data-stu-id="06d7f-119">Use the UP/DOWN ARROW keys to cycle through the highlighted matches in the order of preference.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="06d7f-120">下矢印キーを押すと次の最善一致に移動し、上矢印キーを押すと前の最善一致が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="06d7f-120">Press the DOWN ARROW key to traverse to the next best match, and the UP ARROW key highlights the previous best match.</span></span>  
  
    -   <span data-ttu-id="06d7f-121">Home キーを押すと、最初の一致に戻ります。</span><span class="sxs-lookup"><span data-stu-id="06d7f-121">Press the HOME key to return to the top match.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06d7f-122">参照</span><span class="sxs-lookup"><span data-stu-id="06d7f-122">See Also</span></span>  
 [<span data-ttu-id="06d7f-123">BizTalk マッパーの強化された機能を使用</span><span class="sxs-lookup"><span data-stu-id="06d7f-123">Using Enhanced Features in BizTalk Mapper</span></span>](../core/using-enhanced-features-in-biztalk-mapper.md)