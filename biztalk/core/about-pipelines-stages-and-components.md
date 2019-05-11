---
title: パイプライン、ステージ、およびコンポーネントについて |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Microsoft.BizTalk.Component.Interop namespace
- pipelines, about pipelines
ms.assetid: a98e1c93-f264-4577-bd12-4430a5859e3c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04bef6e1c443ca2723029014f5a4d3b703b4d7a3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362349"
---
# <a name="about-pipelines-stages-and-components"></a><span data-ttu-id="2f6a2-102">パイプライン、ステージ、およびコンポーネントについて</span><span class="sxs-lookup"><span data-stu-id="2f6a2-102">About Pipelines, Stages, and Components</span></span>
<span data-ttu-id="2f6a2-103">パイプラインは、定義済みの順序でメッセージを処理する .NET または COM コンポーネントのセットを含むソフトウェア インフラストラクチャです。</span><span class="sxs-lookup"><span data-stu-id="2f6a2-103">A pipeline is a piece of software infrastructure that contains a set of .NET or COM components that process messages in a predefined sequence.</span></span> <span data-ttu-id="2f6a2-104">パイプラインは、処理ステージと呼ばれる作業のカテゴリを除算し、ステージが実行されるシーケンスを決定します。</span><span class="sxs-lookup"><span data-stu-id="2f6a2-104">A pipeline divides processing into categories of work called stages, and determines the sequence in which the stages are performed.</span></span> <span data-ttu-id="2f6a2-105">各ステージは、作業の論理グループを定義、段階に移動したり、コンポーネントを決定およびステージにおけるパイプライン コンポーネントを実行する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="2f6a2-105">Each stage defines logical work groups, determines which components can go in that stage, and specifies how the pipeline components in the stage are run.</span></span>  
  
 <span data-ttu-id="2f6a2-106">各ステージでは、内では、パイプライン コンポーネントは、特定のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="2f6a2-106">Within each stage, pipeline components perform specific tasks.</span></span> <span data-ttu-id="2f6a2-107">たとえば、受信パイプラインのステージ内のコンポーネントがデコード、逆アセンブルし、他の形式からドキュメントを XML に変換します。</span><span class="sxs-lookup"><span data-stu-id="2f6a2-107">For example, components within stages of a receive pipeline may decode, disassemble, and then convert documents from other formats to XML.</span></span> <span data-ttu-id="2f6a2-108">送信パイプラインは基本的に逆: ドキュメントを XML から他の形式に変換、アセンブル、およびプロセス全体の一部を実行する各パイプライン コンポーネントを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="2f6a2-108">Send pipelines do essentially the opposite: convert documents from XML to other formats, assemble, and encrypt, with each pipeline component performing a portion of the entire process.</span></span> <span data-ttu-id="2f6a2-109">ステージには、コンポーネントのコンテナーが、各ステージ自体がメタデータを持つコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="2f6a2-109">Although a stage is a container of components, each stage is itself a component with metadata.</span></span> <span data-ttu-id="2f6a2-110">ステージは、実行コードを持つパイプライン コンポーネントではなく、実行コードを持つありません。</span><span class="sxs-lookup"><span data-stu-id="2f6a2-110">Stages have no execution code, as opposed to pipeline components, which do have execution code.</span></span>  
  
 <span data-ttu-id="2f6a2-111">次の図は、パイプラインのデザイン画面がパイプラインに示しています。</span><span class="sxs-lookup"><span data-stu-id="2f6a2-111">The following figure shows how the pipeline design surface illustrates pipelines.</span></span> <span data-ttu-id="2f6a2-112">このパイプラインには、2 つの段階、アセンブル ステージとエンコード段階があります。</span><span class="sxs-lookup"><span data-stu-id="2f6a2-112">This pipeline has two stages, the Assemble stage and the Encode stage.</span></span> <span data-ttu-id="2f6a2-113">XML アセンブラー パイプライン コンポーネントがアセンブル ステージに追加されましたが、表示されたままにするため、エンコード ステージが空のまま、**ここにドロップします。**</span><span class="sxs-lookup"><span data-stu-id="2f6a2-113">The XML Assembler pipeline component was added to the Assemble stage, but the Encode stage is still empty, because it still shows **Drop Here!**</span></span> <span data-ttu-id="2f6a2-114">パイプライン コンポーネントをステージに追加できることを示します。</span><span class="sxs-lookup"><span data-stu-id="2f6a2-114">to indicate that a pipeline component can be added to the stage.</span></span>  
  
 <span data-ttu-id="2f6a2-115">![BizTalk パイプラインのステージおよびコンポーネント](../core/media/ebiz-pipe-stages02.gif "ebiz_pipe_stages02")</span><span class="sxs-lookup"><span data-stu-id="2f6a2-115">![Stages and components in a BizTalk pipeline](../core/media/ebiz-pipe-stages02.gif "ebiz_pipe_stages02")</span></span>  
<span data-ttu-id="2f6a2-116">BizTalk パイプラインのステージおよびコンポーネントを示しています。</span><span class="sxs-lookup"><span data-stu-id="2f6a2-116">Illustrates stages and components in a BizTalk pipeline.</span></span>  
  
 <span data-ttu-id="2f6a2-117">Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パイプライン テンプレート、パイプライン コンポーネント、および既定のパイプラインのセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2f6a2-117">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] contains a set of pipeline templates, pipeline components, and default pipelines.</span></span> <span data-ttu-id="2f6a2-118">作成して、パイプライン デザイナー ユーザー インターフェイスを使用してパイプラインを構成します。API を使用してパイプラインを実装する、 **Microsoft.BizTalk.Component.Interop**名前空間。</span><span class="sxs-lookup"><span data-stu-id="2f6a2-118">You can create and configure pipelines by using the Pipeline Designer user interface; you implement pipelines by using the API in the **Microsoft.BizTalk.Component.Interop** namespace.</span></span> <span data-ttu-id="2f6a2-119">パイプライン テンプレートを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="2f6a2-119">You cannot modify the pipeline templates.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2f6a2-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2f6a2-120">In This Section</span></span>  
  
-   [<span data-ttu-id="2f6a2-121">パイプラインの種類</span><span class="sxs-lookup"><span data-stu-id="2f6a2-121">Types of Pipelines</span></span>](../core/types-of-pipelines.md)  
  
-   [<span data-ttu-id="2f6a2-122">パイプライン コンポーネントの種類</span><span class="sxs-lookup"><span data-stu-id="2f6a2-122">Types of Pipeline Components</span></span>](../core/types-of-pipeline-components.md)  
  
-   [<span data-ttu-id="2f6a2-123">パイプラインのステージ</span><span class="sxs-lookup"><span data-stu-id="2f6a2-123">Pipeline Stages</span></span>](../core/pipeline-stages.md)  
  
-   [<span data-ttu-id="2f6a2-124">既定のパイプライン</span><span class="sxs-lookup"><span data-stu-id="2f6a2-124">Default Pipelines</span></span>](../core/default-pipelines.md)  
  
-   [<span data-ttu-id="2f6a2-125">パイプラインのテンプレート</span><span class="sxs-lookup"><span data-stu-id="2f6a2-125">Pipeline Templates</span></span>](../core/pipeline-templates.md)  
  
-   [<span data-ttu-id="2f6a2-126">パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2f6a2-126">Pipeline Components</span></span>](../core/pipeline-components.md)  
  
-   [<span data-ttu-id="2f6a2-127">パイプライン コンポーネントのスキーマ解決</span><span class="sxs-lookup"><span data-stu-id="2f6a2-127">Schema Resolution in Pipeline Components</span></span>](../core/schema-resolution-in-pipeline-components.md)  
  
-   [<span data-ttu-id="2f6a2-128">XML アセンブラーおよび逆アセンブラー パイプライン コンポーネントでのエンベロープの使用</span><span class="sxs-lookup"><span data-stu-id="2f6a2-128">Envelope Use in the XML Assembler and Disassembler Pipeline Components</span></span>](../core/envelope-use-in-the-xml-assembler-and-disassembler-pipeline-components.md)  
  
-   [<span data-ttu-id="2f6a2-129">アセンブラー パイプライン コンポーネントでのプロパティの降格</span><span class="sxs-lookup"><span data-stu-id="2f6a2-129">Property Demotion in Assembler Pipeline Components</span></span>](../core/property-demotion-in-assembler-pipeline-components.md)  
  
-   [<span data-ttu-id="2f6a2-130">逆アセンブラー パイプライン コンポーネントでのプロパティの昇格</span><span class="sxs-lookup"><span data-stu-id="2f6a2-130">Property Promotion in Disassembler Pipeline Components</span></span>](../core/property-promotion-in-disassembler-pipeline-components.md)  
  
-   [<span data-ttu-id="2f6a2-131">逆アセンブラー パイプライン コンポーネントでの識別フィールド</span><span class="sxs-lookup"><span data-stu-id="2f6a2-131">Distinguished Fields in Disassembler Pipeline Components</span></span>](../core/distinguished-fields-in-disassembler-pipeline-components.md)