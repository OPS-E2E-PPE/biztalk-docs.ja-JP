---
title: マップ内のスキーマのノードを照合する方法 |Microsoft Docs
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
ms.openlocfilehash: 3a25bf295a767f34b692d54fc922fb8fe489ecc1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336151"
---
# <a name="how-to-match-schema-nodes-in-a-map"></a><span data-ttu-id="208ec-102">マップ内のスキーマ ノードを照合する方法</span><span class="sxs-lookup"><span data-stu-id="208ec-102">How to Match Schema Nodes in a Map</span></span>
<span data-ttu-id="208ec-103">送信元または送信先スキーマが複雑なときに、要素をマップ難しいことができます。</span><span class="sxs-lookup"><span data-stu-id="208ec-103">When the source or destination schemas are complex, it can be difficult to map the elements.</span></span> <span data-ttu-id="208ec-104">BizTalk マッパー、**指示一致**機能で、最適な一致を提案して複雑なスキーマ要素をマップすることができます。</span><span class="sxs-lookup"><span data-stu-id="208ec-104">The BizTalk Mapper introduces the **Indicative Match** feature, which enables you to map complex schema elements by suggesting the best possible matches.</span></span> <span data-ttu-id="208ec-105">このトピックでは、次の操作を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="208ec-105">This topic provides information about how to perform this operation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="208ec-106">BizTalk マッパーでは、スキーマのノードに一致する候補を提案します。</span><span class="sxs-lookup"><span data-stu-id="208ec-106">The BizTalk Mapper suggests possible matches for a schema node.</span></span> <span data-ttu-id="208ec-107">この機能は現在 English 名についてのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="208ec-107">This feature is currently supported only for English names.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="208ec-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="208ec-108">Prerequisites</span></span>  
 <span data-ttu-id="208ec-109">これらの手順では、BizTalk マッパーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="208ec-109">These instructions require that the BizTalk Mapper is running.</span></span>  
  
### <a name="to-match-relevant-schema-nodes"></a><span data-ttu-id="208ec-110">関連するスキーマのノードに一致するには</span><span class="sxs-lookup"><span data-stu-id="208ec-110">To match relevant schema nodes</span></span>  
  
1.  <span data-ttu-id="208ec-111">選択しをクリックして、最善の一致を知る必要があるスキーマ要素を右クリックして**指示一致**します。</span><span class="sxs-lookup"><span data-stu-id="208ec-111">Select and right-click the schema element for which you need to know the best matches, and then click **Indicate Matches**.</span></span> <span data-ttu-id="208ec-112">BizTalk マッパーには、最適な一致 (7 つに制限付き)、選択されている最も最適な一致が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="208ec-112">The BizTalk Mapper highlights the best matches (restricted to seven), with the most optimum match selected.</span></span>  
  
     <span data-ttu-id="208ec-113">または、選択**指示一致**BizTalk メニューのまたは SHIFT キーを押してから + スペース キー。</span><span class="sxs-lookup"><span data-stu-id="208ec-113">Alternatively, you can select **Indicate Matches** from the BizTalk menu, or press SHIFT + SPACE keys.</span></span>  
  
     <span data-ttu-id="208ec-114">次の図は、送信先スキーマで選択したノードの一致を示したものを示します。</span><span class="sxs-lookup"><span data-stu-id="208ec-114">The following figure shows suggestive matches for the selected node in destination schema.</span></span>  
  
     <span data-ttu-id="208ec-115">![推奨マッピング](../core/media/suggestive-mapping.gif "Suggestive_Mapping")</span><span class="sxs-lookup"><span data-stu-id="208ec-115">![Suggestive mapping](../core/media/suggestive-mapping.gif "Suggestive_Mapping")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="208ec-116">一致を示したものの間を移動する SHIFT キーを保持します。</span><span class="sxs-lookup"><span data-stu-id="208ec-116">Hold down the SHIFT key to traverse among the suggestive matches.</span></span>  
  
2.  <span data-ttu-id="208ec-117">次のようになりました行えます。</span><span class="sxs-lookup"><span data-stu-id="208ec-117">You can now do the following:</span></span>  
  
    -   <span data-ttu-id="208ec-118">Enter キーを押して、強調表示されている最適な (可能な場合) の一致を確認します。</span><span class="sxs-lookup"><span data-stu-id="208ec-118">Press ENTER to confirm the highlighted (best possible) match.</span></span>  
  
    -   <span data-ttu-id="208ec-119">上下矢印キーを使用して、順番に強調表示されている一致する優先順位の順序。</span><span class="sxs-lookup"><span data-stu-id="208ec-119">Use the UP/DOWN ARROW keys to cycle through the highlighted matches in the order of preference.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="208ec-120">次の最適な一致をスキャンする下方向キーを押し、上矢印キーは、前の最適な一致を強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="208ec-120">Press the DOWN ARROW key to traverse to the next best match, and the UP ARROW key highlights the previous best match.</span></span>  
  
    -   <span data-ttu-id="208ec-121">最上位の一致に戻りますホーム キーを押します。</span><span class="sxs-lookup"><span data-stu-id="208ec-121">Press the HOME key to return to the top match.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="208ec-122">参照</span><span class="sxs-lookup"><span data-stu-id="208ec-122">See Also</span></span>  
 [<span data-ttu-id="208ec-123">BizTalk マッパーの強化された機能の使用</span><span class="sxs-lookup"><span data-stu-id="208ec-123">Using Enhanced Features in BizTalk Mapper</span></span>](../core/using-enhanced-features-in-biztalk-mapper.md)