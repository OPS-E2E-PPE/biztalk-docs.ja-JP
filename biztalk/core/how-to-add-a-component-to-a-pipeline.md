---
title: パイプラインにコンポーネントを追加する方法 |Microsoft Docs
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
ms.openlocfilehash: 65db8b09dfcb7f1821746ffb5716e5f1e3f3e1dc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387394"
---
# <a name="how-to-add-a-component-to-a-pipeline"></a><span data-ttu-id="36038-102">パイプラインにコンポーネントを追加する方法</span><span class="sxs-lookup"><span data-stu-id="36038-102">How to Add a Component to a Pipeline</span></span>
<span data-ttu-id="36038-103">コンポーネントをパイプラインに追加するには、ツールボックスからデザイン画面にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="36038-103">You add components to pipelines by dragging from the Toolbox to the design surface.</span></span>  
  
### <a name="to-add-a-component-to-a-pipeline"></a><span data-ttu-id="36038-104">パイプラインにコンポーネントを追加するには</span><span class="sxs-lookup"><span data-stu-id="36038-104">To add a component to a pipeline</span></span>  
  
- <span data-ttu-id="36038-105">ツールボックスで、パイプライン コンポーネントをドラッグして、**ここにドロップします。**</span><span class="sxs-lookup"><span data-stu-id="36038-105">In the Toolbox, drag the pipeline component onto a **Drop Here!**</span></span> <span data-ttu-id="36038-106">デザイン サーフェイス上のボックスです。</span><span class="sxs-lookup"><span data-stu-id="36038-106">box on the design surface.</span></span>  
  
  <span data-ttu-id="36038-107">次の図は、パイプラインのデザイン画面がパイプラインに示しています。</span><span class="sxs-lookup"><span data-stu-id="36038-107">The following illustration shows how the pipeline design surface illustrates pipelines.</span></span> <span data-ttu-id="36038-108">このパイプラインには、2 つの段階、アセンブル ステージとエンコード段階があります。</span><span class="sxs-lookup"><span data-stu-id="36038-108">This pipeline has two stages, the Assemble stage and the Encode stage.</span></span> <span data-ttu-id="36038-109">XML アセンブラー パイプライン コンポーネントがアセンブル ステージに追加されましたが、表示されたままにするため、エンコード ステージが空のまま、**ここにドロップします。**</span><span class="sxs-lookup"><span data-stu-id="36038-109">The XML Assembler pipeline component was added to the Assemble stage, but the Encode stage is still empty, because it still shows **Drop Here!**</span></span> <span data-ttu-id="36038-110">パイプライン コンポーネントをステージに追加できることを示します。</span><span class="sxs-lookup"><span data-stu-id="36038-110">to indicate that a pipeline component can be added to the stage.</span></span>  
  
  <span data-ttu-id="36038-111">![BizTalk パイプラインのステージおよびコンポーネント](../core/media/ebiz-pipe-stages02.gif "ebiz_pipe_stages02")</span><span class="sxs-lookup"><span data-stu-id="36038-111">![Stages and components in a BizTalk pipeline](../core/media/ebiz-pipe-stages02.gif "ebiz_pipe_stages02")</span></span>  
  <span data-ttu-id="36038-112">BizTalk パイプラインのステージおよびコンポーネントを示しています。</span><span class="sxs-lookup"><span data-stu-id="36038-112">Illustrates stages and components in a BizTalk pipeline.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36038-113">パイプライン コンポーネントは、デザイン サーフェイス上の特定の場所でのみ削除できます。</span><span class="sxs-lookup"><span data-stu-id="36038-113">A pipeline component can only be dropped at specific places on the design surface.</span></span> <span data-ttu-id="36038-114">パイプライン コンポーネントは、ステージ関係がステージでのみ削除できます。</span><span class="sxs-lookup"><span data-stu-id="36038-114">The pipeline component can only be dropped in a stage in which it has stage affinity.</span></span> <span data-ttu-id="36038-115">取り消し線、円は、パイプライン コンポーネントを削除できませんポインターの隣に表示されます。</span><span class="sxs-lookup"><span data-stu-id="36038-115">A circle with a line through it appears next to the pointer where the pipeline component cannot be dropped.</span></span> <span data-ttu-id="36038-116">矢印が表示されたら、およびパイプライン コンポーネントの配置場所、デザイン サーフェイスの一部が強調表示します。</span><span class="sxs-lookup"><span data-stu-id="36038-116">An arrow appears, and a portion of the design surface is highlighted where a pipeline component can be placed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36038-117">参照</span><span class="sxs-lookup"><span data-stu-id="36038-117">See Also</span></span>  
 <span data-ttu-id="36038-118">[新しいパイプラインを作成する方法](../core/how-to-create-a-new-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="36038-118">[How to Create a New Pipeline](../core/how-to-create-a-new-pipeline.md) </span></span>  
 <span data-ttu-id="36038-119">[パイプラインを開く方法](../core/how-to-open-a-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="36038-119">[How to Open a Pipeline](../core/how-to-open-a-pipeline.md) </span></span>  
 <span data-ttu-id="36038-120">[ツールボックスの使用方法](../core/how-to-use-the-toolbox.md) </span><span class="sxs-lookup"><span data-stu-id="36038-120">[How to Use the Toolbox](../core/how-to-use-the-toolbox.md) </span></span>  
 <span data-ttu-id="36038-121">[キーボードで移動する方法](../core/how-to-navigate-with-the-keyboard.md) </span><span class="sxs-lookup"><span data-stu-id="36038-121">[How to Navigate with the Keyboard](../core/how-to-navigate-with-the-keyboard.md) </span></span>  
 [<span data-ttu-id="36038-122">パイプライン デザイナーでのパイプラインの作成</span><span class="sxs-lookup"><span data-stu-id="36038-122">Creating Pipelines with Pipeline Designer</span></span>](../core/creating-pipelines-with-pipeline-designer.md)