---
title: "パイプライン、ステージ、およびコンポーネントについて |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Microsoft.BizTalk.Component.Interop namespace
- pipelines, about pipelines
ms.assetid: a98e1c93-f264-4577-bd12-4430a5859e3c
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 070c785924021f8e398a547c01afe969fa6430cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="about-pipelines-stages-and-components"></a><span data-ttu-id="5a347-102">パイプライン、ステージ、およびコンポーネントについて</span><span class="sxs-lookup"><span data-stu-id="5a347-102">About Pipelines, Stages, and Components</span></span>
<span data-ttu-id="5a347-103">パイプラインとは、事前に定義された順序でメッセージを処理する、一連の .NET コンポーネントまたは COM コンポーネントを含んだソフトウェア インフラストラクチャのことです。</span><span class="sxs-lookup"><span data-stu-id="5a347-103">A pipeline is a piece of software infrastructure that contains a set of .NET or COM components that process messages in a predefined sequence.</span></span> <span data-ttu-id="5a347-104">パイプラインでは、処理がステージと呼ばれる作業単位に分割されます。各ステージの順序もパイプラインによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="5a347-104">A pipeline divides processing into categories of work called stages, and determines the sequence in which the stages are performed.</span></span> <span data-ttu-id="5a347-105">ステージごとに論理的なワークグループが定義され、使用コンポーネントが決定されるほか、そのステージにおけるパイプライン コンポーネントの実行方法も指定されます。</span><span class="sxs-lookup"><span data-stu-id="5a347-105">Each stage defines logical work groups, determines which components can go in that stage, and specifies how the pipeline components in the stage are run.</span></span>  
  
 <span data-ttu-id="5a347-106">各ステージでは、それぞれのパイプライン コンポーネントが固有のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a347-106">Within each stage, pipeline components perform specific tasks.</span></span> <span data-ttu-id="5a347-107">たとえば、受信パイプラインのステージに含まれるコンポーネントは、デコード、逆アセンブル、変換などの各タスクを通じて、特定の形式のドキュメントを XML 形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="5a347-107">For example, components within stages of a receive pipeline may decode, disassemble, and then convert documents from other formats to XML.</span></span> <span data-ttu-id="5a347-108">送信パイプラインは、逆に、基本的には: ドキュメントを XML から他の形式に変換する、アセンブル、および暗号化には、プロセス全体の一部を実行する各パイプライン コンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="5a347-108">Send pipelines do essentially the opposite: convert documents from XML to other formats, assemble, and encrypt, with each pipeline component performing a portion of the entire process.</span></span> <span data-ttu-id="5a347-109">ステージはコンポーネントのコンテナーであると共に、各ステージはそれ自体がメタデータを持つコンポーネントといえます。</span><span class="sxs-lookup"><span data-stu-id="5a347-109">Although a stage is a container of components, each stage is itself a component with metadata.</span></span> <span data-ttu-id="5a347-110">実行コードを持つパイプライン コンポーネントとは異なり、ステージには実行コードがありません。</span><span class="sxs-lookup"><span data-stu-id="5a347-110">Stages have no execution code, as opposed to pipeline components, which do have execution code.</span></span>  
  
 <span data-ttu-id="5a347-111">次の図は、パイプライン デザイン画面でパイプラインがどのように表されるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="5a347-111">The following figure shows how the pipeline design surface illustrates pipelines.</span></span> <span data-ttu-id="5a347-112">このパイプラインには、アセンブル ステージとエンコード ステージという 2 つのステージがあります。</span><span class="sxs-lookup"><span data-stu-id="5a347-112">This pipeline has two stages, the Assemble stage and the Encode stage.</span></span> <span data-ttu-id="5a347-113">XML アセンブラー パイプライン コンポーネントがアセンブル ステージに追加されましたが、エンコード ステージでは、空のまま表示されたままに**ここにドロップします。**</span><span class="sxs-lookup"><span data-stu-id="5a347-113">The XML Assembler pipeline component was added to the Assemble stage, but the Encode stage is still empty, because it still shows **Drop Here!**</span></span> <span data-ttu-id="5a347-114">これは、ステージが空であること、つまりパイプライン コンポーネントを追加できることを示しています。</span><span class="sxs-lookup"><span data-stu-id="5a347-114">to indicate that a pipeline component can be added to the stage.</span></span>  
  
 <span data-ttu-id="5a347-115">![BizTalk パイプラインのステージおよびコンポーネント](../core/media/ebiz-pipe-stages02.gif "ebiz_pipe_stages02")</span><span class="sxs-lookup"><span data-stu-id="5a347-115">![Stages and components in a BizTalk pipeline](../core/media/ebiz-pipe-stages02.gif "ebiz_pipe_stages02")</span></span>  
<span data-ttu-id="5a347-116">BizTalk パイプラインのステージおよびコンポーネントを示します。</span><span class="sxs-lookup"><span data-stu-id="5a347-116">Illustrates stages and components in a BizTalk pipeline.</span></span>  
  
 <span data-ttu-id="5a347-117">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には、パイプライン テンプレート、パイプライン コンポーネント、および既定のパイプラインが複数用意されています。</span><span class="sxs-lookup"><span data-stu-id="5a347-117">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] contains a set of pipeline templates, pipeline components, and default pipelines.</span></span> <span data-ttu-id="5a347-118">作成して、パイプライン デザイナー ユーザー インターフェイスを使用してパイプラインを構成します。内の API を使用してパイプラインを実装する、 **Microsoft.BizTalk.Component.Interop**名前空間。</span><span class="sxs-lookup"><span data-stu-id="5a347-118">You can create and configure pipelines by using the Pipeline Designer user interface; you implement pipelines by using the API in the **Microsoft.BizTalk.Component.Interop** namespace.</span></span> <span data-ttu-id="5a347-119">パイプライン テンプレートを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="5a347-119">You cannot modify the pipeline templates.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5a347-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5a347-120">In This Section</span></span>  
  
-   [<span data-ttu-id="5a347-121">パイプラインの種類</span><span class="sxs-lookup"><span data-stu-id="5a347-121">Types of Pipelines</span></span>](../core/types-of-pipelines.md)  
  
-   [<span data-ttu-id="5a347-122">パイプライン コンポーネントの種類</span><span class="sxs-lookup"><span data-stu-id="5a347-122">Types of Pipeline Components</span></span>](../core/types-of-pipeline-components.md)  
  
-   [<span data-ttu-id="5a347-123">パイプライン ステージ</span><span class="sxs-lookup"><span data-stu-id="5a347-123">Pipeline Stages</span></span>](../core/pipeline-stages.md)  
  
-   [<span data-ttu-id="5a347-124">既定のパイプライン</span><span class="sxs-lookup"><span data-stu-id="5a347-124">Default Pipelines</span></span>](../core/default-pipelines.md)  
  
-   [<span data-ttu-id="5a347-125">パイプライン テンプレート</span><span class="sxs-lookup"><span data-stu-id="5a347-125">Pipeline Templates</span></span>](../core/pipeline-templates.md)  
  
-   [<span data-ttu-id="5a347-126">パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5a347-126">Pipeline Components</span></span>](../core/pipeline-components.md)  
  
-   [<span data-ttu-id="5a347-127">スキーマの解決パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5a347-127">Schema Resolution in Pipeline Components</span></span>](../core/schema-resolution-in-pipeline-components.md)  
  
-   [<span data-ttu-id="5a347-128">XML アセンブラーおよび逆アセンブラー パイプライン コンポーネントでのエンベロープの使用</span><span class="sxs-lookup"><span data-stu-id="5a347-128">Envelope Use in the XML Assembler and Disassembler Pipeline Components</span></span>](../core/envelope-use-in-the-xml-assembler-and-disassembler-pipeline-components.md)  
  
-   [<span data-ttu-id="5a347-129">アセンブラー パイプライン コンポーネントでプロパティの降格</span><span class="sxs-lookup"><span data-stu-id="5a347-129">Property Demotion in Assembler Pipeline Components</span></span>](../core/property-demotion-in-assembler-pipeline-components.md)  
  
-   [<span data-ttu-id="5a347-130">逆アセンブラー パイプライン コンポーネントのプロパティの昇格</span><span class="sxs-lookup"><span data-stu-id="5a347-130">Property Promotion in Disassembler Pipeline Components</span></span>](../core/property-promotion-in-disassembler-pipeline-components.md)  
  
-   [<span data-ttu-id="5a347-131">識別フィールドに逆アセンブラー パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5a347-131">Distinguished Fields in Disassembler Pipeline Components</span></span>](../core/distinguished-fields-in-disassembler-pipeline-components.md)