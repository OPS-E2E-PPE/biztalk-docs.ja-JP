---
title: コンポーネントをパイプラインに追加する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, components
ms.assetid: 6b1dbeab-6acc-46d7-8ddd-79b79da3591c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a9f11f03e818ae1067bc22027822bfeef202260
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-component-to-a-pipeline"></a><span data-ttu-id="dbd00-102">コンポーネントをパイプラインに追加する方法</span><span class="sxs-lookup"><span data-stu-id="dbd00-102">How to Add a Component to a Pipeline</span></span>
<span data-ttu-id="dbd00-103">コンポーネントをパイプラインに追加する場合は、ツールボックスからデザイン画面にパイプラインをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="dbd00-103">You add components to pipelines by dragging from the Toolbox to the design surface.</span></span>  
  
### <a name="to-add-a-component-to-a-pipeline"></a><span data-ttu-id="dbd00-104">コンポーネントをパイプラインに追加するには</span><span class="sxs-lookup"><span data-stu-id="dbd00-104">To add a component to a pipeline</span></span>  
  
-   <span data-ttu-id="dbd00-105">ツールボックスで、パイプライン コンポーネントをドラッグして、**ここにドロップします。**</span><span class="sxs-lookup"><span data-stu-id="dbd00-105">In the Toolbox, drag the pipeline component onto a **Drop Here!**</span></span> <span data-ttu-id="dbd00-106">ボックスにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="dbd00-106">box on the design surface.</span></span>  
  
 <span data-ttu-id="dbd00-107">次の図は、パイプラインがパイプラインのデザイン画面でどのように示されてを示します。</span><span class="sxs-lookup"><span data-stu-id="dbd00-107">The following illustration shows how the pipeline design surface illustrates pipelines.</span></span> <span data-ttu-id="dbd00-108">このパイプラインには、アセンブル ステージとエンコード ステージという 2 つのステージがあります。</span><span class="sxs-lookup"><span data-stu-id="dbd00-108">This pipeline has two stages, the Assemble stage and the Encode stage.</span></span> <span data-ttu-id="dbd00-109">XML アセンブラー パイプライン コンポーネントがアセンブル ステージに追加されましたが、エンコード ステージでは、空のまま表示されたままに**ここにドロップします。**</span><span class="sxs-lookup"><span data-stu-id="dbd00-109">The XML Assembler pipeline component was added to the Assemble stage, but the Encode stage is still empty, because it still shows **Drop Here!**</span></span> <span data-ttu-id="dbd00-110">これは、ステージが空であること、つまりパイプライン コンポーネントを追加できることを示しています。</span><span class="sxs-lookup"><span data-stu-id="dbd00-110">to indicate that a pipeline component can be added to the stage.</span></span>  
  
 <span data-ttu-id="dbd00-111">![BizTalk パイプラインのステージおよびコンポーネント](../core/media/ebiz-pipe-stages02.gif "ebiz_pipe_stages02")</span><span class="sxs-lookup"><span data-stu-id="dbd00-111">![Stages and components in a BizTalk pipeline](../core/media/ebiz-pipe-stages02.gif "ebiz_pipe_stages02")</span></span>  
<span data-ttu-id="dbd00-112">BizTalk パイプラインのステージおよびコンポーネントを示します。</span><span class="sxs-lookup"><span data-stu-id="dbd00-112">Illustrates stages and components in a BizTalk pipeline.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dbd00-113">パイプライン コンポーネントは、デザイン画面の特定の位置にのみドロップできます。</span><span class="sxs-lookup"><span data-stu-id="dbd00-113">A pipeline component can only be dropped at specific places on the design surface.</span></span> <span data-ttu-id="dbd00-114">パイプライン コンポーネントをドロップできるのは、コンポーネントがステージ関係を持つステージ内のみです。</span><span class="sxs-lookup"><span data-stu-id="dbd00-114">The pipeline component can only be dropped in a stage in which it has stage affinity.</span></span> <span data-ttu-id="dbd00-115">パイプライン コンポーネントをドロップできないポインターの隣には、中に 1 本の線が描かれた円が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dbd00-115">A circle with a line through it appears next to the pointer where the pipeline component cannot be dropped.</span></span> <span data-ttu-id="dbd00-116">矢印が表示され、デザイン画面内でパイプライン コンポーネントを配置できる部分が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="dbd00-116">An arrow appears, and a portion of the design surface is highlighted where a pipeline component can be placed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbd00-117">参照</span><span class="sxs-lookup"><span data-stu-id="dbd00-117">See Also</span></span>  
 <span data-ttu-id="dbd00-118">[新しいパイプラインを作成する方法](../core/how-to-create-a-new-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="dbd00-118">[How to Create a New Pipeline](../core/how-to-create-a-new-pipeline.md) </span></span>  
 <span data-ttu-id="dbd00-119">[パイプラインを開く方法](../core/how-to-open-a-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="dbd00-119">[How to Open a Pipeline](../core/how-to-open-a-pipeline.md) </span></span>  
 <span data-ttu-id="dbd00-120">[ツールボックスの使用方法](../core/how-to-use-the-toolbox.md) </span><span class="sxs-lookup"><span data-stu-id="dbd00-120">[How to Use the Toolbox](../core/how-to-use-the-toolbox.md) </span></span>  
 <span data-ttu-id="dbd00-121">[キーボードで移動する方法](../core/how-to-navigate-with-the-keyboard.md) </span><span class="sxs-lookup"><span data-stu-id="dbd00-121">[How to Navigate with the Keyboard](../core/how-to-navigate-with-the-keyboard.md) </span></span>  
 [<span data-ttu-id="dbd00-122">パイプライン デザイナーでパイプラインの作成</span><span class="sxs-lookup"><span data-stu-id="dbd00-122">Creating Pipelines with Pipeline Designer</span></span>](../core/creating-pipelines-with-pipeline-designer.md)