---
title: "パイプライン ステージ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipelines, properties
- CATID_AssemblingSerializer component category
- CATID_Encoder component category
- pipelines, stages
- CATID_DisassemblingParser component category
- CATID_Validate component category
- ComponentCategory class attribute
- CATID_Decoder component category
- CATID_Any component category
- CATID_PartyResolver component category
- Execution Mode property
ms.assetid: ac50c48c-6ed5-4322-95cc-af55df6bcd1c
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aeb675f39cb39ade4230e6e39f798e95115aaf78
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="pipeline-stages"></a><span data-ttu-id="771f2-102">パイプラインのステージ</span><span class="sxs-lookup"><span data-stu-id="771f2-102">Pipeline Stages</span></span>
<span data-ttu-id="771f2-103">このトピックの内容について説明します、**実行モード**プロパティとステージ関係します。</span><span class="sxs-lookup"><span data-stu-id="771f2-103">This topic discusses the **Execution Mode** property and stage affinity.</span></span>  
  
## <a name="execution-mode-property"></a><span data-ttu-id="771f2-104">"実行モード" プロパティ</span><span class="sxs-lookup"><span data-stu-id="771f2-104">Execution Mode property</span></span>  
 <span data-ttu-id="771f2-105">パイプライン ステージでは、パイプラインの実行中、メッセージの形式を識別する最初のコンポーネントだけが実行される場合と、すべてのコンポーネントが実行される場合とがあります。</span><span class="sxs-lookup"><span data-stu-id="771f2-105">During the execution of a pipeline, the pipeline stages can run only the first component that recognizes the message format, or all components.</span></span> <span data-ttu-id="771f2-106">実行パターンを決定するプロパティは**実行モード**です。</span><span class="sxs-lookup"><span data-stu-id="771f2-106">The property that determines the execution pattern is **Execution Mode**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="771f2-107">このプロパティは、パイプライン テンプレートに追加されたステージの読み取り専用プロパティとして存在しますが、その動作を理解することは重要です。</span><span class="sxs-lookup"><span data-stu-id="771f2-107">This property is read-only on the stages included in the pipeline templates, but understanding how it works is an important concept.</span></span>  
  
 <span data-ttu-id="771f2-108">ときに、**実行モード**プロパティに設定されている**すべて**ステージ内のすべてのコンポーネントが構成されている順序で実行されます。</span><span class="sxs-lookup"><span data-stu-id="771f2-108">When the **Execution Mode** property is set to **All**, all the components within the stage are run in the configured sequence.</span></span> <span data-ttu-id="771f2-109">このモードは、論理タスクを完了するために複数のコンポーネントを実行します。</span><span class="sxs-lookup"><span data-stu-id="771f2-109">This mode runs several components to complete a logical task.</span></span> <span data-ttu-id="771f2-110">この場合、このパイプライン ステージに送信されたメッセージを処理しているときに、いずれかのコンポーネントでエラーが発生すると、実行時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="771f2-110">In this case, a run-time error results if any component encounters an error while processing a message during this pipeline stage.</span></span>  
  
 <span data-ttu-id="771f2-111">パイプラインを使用して、いくつかの形式でメッセージを受信するときに、**実行モード**プロパティに設定されている**FirstMatch**です。</span><span class="sxs-lookup"><span data-stu-id="771f2-111">When a pipeline is used to receive messages in several formats, then the **Execution Mode** property is set to **FirstMatch**.</span></span> <span data-ttu-id="771f2-112">このモードでは、メッセージを認識した最初のコンポーネントだけが実行されます。</span><span class="sxs-lookup"><span data-stu-id="771f2-112">In this mode, only the first component that recognizes the message is run.</span></span> <span data-ttu-id="771f2-113">ステージ内のいずれのコンポーネントもメッセージを認識しなかった場合、実行時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="771f2-113">If no components in the stage recognize the message, a run-time error results.</span></span>  
  
 <span data-ttu-id="771f2-114">各ステージがあることができます独自ことに注意してください**実行モード**パイプライン内での設定では、大きく異なるステージが別の実行モードを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="771f2-114">Note that each stage can have its own **Execution Mode** setting, so different stages within a pipeline can have different execution modes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="771f2-115">このリリースで[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、すべての段階、送信パイプラインおよび受信パイプラインの逆アセンブルを除くすべてのステージは、値を持つ、**実行モード**プロパティに設定**すべて**です。</span><span class="sxs-lookup"><span data-stu-id="771f2-115">In this release of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], all the stages in a send pipeline and all stages except Disassemble in a receive pipeline have the value of the **Execution Mode** property set to **All**.</span></span> <span data-ttu-id="771f2-116">値、**実行モード**逆アセンブル ステージでプロパティに設定されて**FirstMatch**です。</span><span class="sxs-lookup"><span data-stu-id="771f2-116">The value of the **Execution Mode** property in the Disassemble stage is set to **FirstMatch**.</span></span> <span data-ttu-id="771f2-117">変更することはできません、**実行モード**ステージのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="771f2-117">You cannot change the **Execution Mode** property of a stage.</span></span>  
  
#### <a name="to-read-pipeline-stage-properties"></a><span data-ttu-id="771f2-118">パイプライン ステージのプロパティを確認するには</span><span class="sxs-lookup"><span data-stu-id="771f2-118">To read pipeline stage properties</span></span>  
  
1.  <span data-ttu-id="771f2-119">パイプライン デザイナーでステージの図形をクリックします。</span><span class="sxs-lookup"><span data-stu-id="771f2-119">In Pipeline Designer, click a stage shape.</span></span>  
  
2.  <span data-ttu-id="771f2-120">プロパティ ウィンドウでの**全般** セクションで、次のプロパティの読み取り。</span><span class="sxs-lookup"><span data-stu-id="771f2-120">In the Properties window, in the **General** section, read the following properties:</span></span>  
  
    |<span data-ttu-id="771f2-121">プロパティ</span><span class="sxs-lookup"><span data-stu-id="771f2-121">Use this</span></span>|<span data-ttu-id="771f2-122">目的</span><span class="sxs-lookup"><span data-stu-id="771f2-122">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="771f2-123">**名前**</span><span class="sxs-lookup"><span data-stu-id="771f2-123">**Name**</span></span>|<span data-ttu-id="771f2-124">ステージの名前を示します。</span><span class="sxs-lookup"><span data-stu-id="771f2-124">Indicates the name of the stage.</span></span>|  
    |<span data-ttu-id="771f2-125">**[実行モード]**</span><span class="sxs-lookup"><span data-stu-id="771f2-125">**Execution Mode**</span></span>|<span data-ttu-id="771f2-126">ステージの実行パターンを示します。</span><span class="sxs-lookup"><span data-stu-id="771f2-126">Indicates the execution pattern of the stage.</span></span><br /><br /> <span data-ttu-id="771f2-127">有効な値:**すべて**または**FirstMatch**</span><span class="sxs-lookup"><span data-stu-id="771f2-127">Valid values: **All** or **FirstMatch**</span></span>|  
    |<span data-ttu-id="771f2-128">**コンポーネントの最小数**</span><span class="sxs-lookup"><span data-stu-id="771f2-128">**Minimum Number of Components**</span></span>|<span data-ttu-id="771f2-129">ステージに追加することのできるパイプライン コンポーネントの最小数を示します。</span><span class="sxs-lookup"><span data-stu-id="771f2-129">Indicates the minimum number of pipeline components that can be added to the stage.</span></span>|  
    |<span data-ttu-id="771f2-130">**コンポーネントの最大数**</span><span class="sxs-lookup"><span data-stu-id="771f2-130">**Maximum Number of Components**</span></span>|<span data-ttu-id="771f2-131">ステージに追加することのできるパイプライン コンポーネントの最大数を示します。</span><span class="sxs-lookup"><span data-stu-id="771f2-131">Indicates the maximum number of pipeline components that can be added to the stage.</span></span>|  
    |<span data-ttu-id="771f2-132">**StageID**</span><span class="sxs-lookup"><span data-stu-id="771f2-132">**StageID**</span></span>|<span data-ttu-id="771f2-133">ステージの一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="771f2-133">Indicates the unique identifier for the stage.</span></span>|  
  
## <a name="stage-affinity"></a><span data-ttu-id="771f2-134">ステージ関係</span><span class="sxs-lookup"><span data-stu-id="771f2-134">Stage affinity</span></span>  
 <span data-ttu-id="771f2-135">パイプライン コンポーネントは、そのコンポーネントがパイプラインの特定のステージ (1 つまたは複数) 内で使用するために作成されたことを意味するステージ関係を持ちます。</span><span class="sxs-lookup"><span data-stu-id="771f2-135">Pipeline components have stage affinity, meaning that they are created for use within a particular stage or stages in a pipeline.</span></span>  
  
 <span data-ttu-id="771f2-136">COM ベースのパイプライン コンポーネントがステージ ID を使用して、実装カテゴリとして自分自身を登録することにより、ステージ関係を表すときにします。NET ベースのパイプライン コンポーネントを使用して、ステージ関係を指定する、 **ComponentCategory**クラスの属性です。</span><span class="sxs-lookup"><span data-stu-id="771f2-136">COM-based pipeline components express their stage affinity by registering themselves using the stage ID as the implementation category, while .NET-based pipeline components specify their stage affinity by using the **ComponentCategory** class attribute.</span></span> <span data-ttu-id="771f2-137">あること、コンポーネント自体を 2 つ以上のステージに関連付けることに注意してください: コンポーネントが 1 つ以上の実装カテゴリを持つことができますか**ComponentCategory**属性。</span><span class="sxs-lookup"><span data-stu-id="771f2-137">Note that it is possible for a component to associate itself with more than one stage—components can have more than one implementation category or **ComponentCategory** attribute.</span></span>  
  
 <span data-ttu-id="771f2-138">次の表は、コンポーネントのカテゴリと、それぞれに関連付けられたステージを示しています。</span><span class="sxs-lookup"><span data-stu-id="771f2-138">The following table shows the available component categories and their associated stages.</span></span>  
  
|<span data-ttu-id="771f2-139">コンポーネント カテゴリ</span><span class="sxs-lookup"><span data-stu-id="771f2-139">Component category</span></span>|<span data-ttu-id="771f2-140">コンポーネントを配置可能なステージ</span><span class="sxs-lookup"><span data-stu-id="771f2-140">Stage where component can be placed</span></span>|<span data-ttu-id="771f2-141">Description</span><span class="sxs-lookup"><span data-stu-id="771f2-141">Description</span></span>|  
|------------------------|-----------------------------------------|-----------------|  
|<span data-ttu-id="771f2-142">CATID_Decoder {9d0e4103-4cce-4536-83fa-4a5040674ad6}</span><span class="sxs-lookup"><span data-stu-id="771f2-142">CATID_Decoder {9d0e4103-4cce-4536-83fa-4a5040674ad6}</span></span>|<span data-ttu-id="771f2-143">デコード</span><span class="sxs-lookup"><span data-stu-id="771f2-143">Decode</span></span>|<span data-ttu-id="771f2-144">すべてのデコード コンポーネントはこのカテゴリを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="771f2-144">All decoding components should implement this category.</span></span>|  
|<span data-ttu-id="771f2-145">CATID_DisassemblingParser {9d0e4105-4cce-4536-83fa-4a5040674ad6}</span><span class="sxs-lookup"><span data-stu-id="771f2-145">CATID_DisassemblingParser {9d0e4105-4cce-4536-83fa-4a5040674ad6}</span></span>|<span data-ttu-id="771f2-146">逆アセンブル</span><span class="sxs-lookup"><span data-stu-id="771f2-146">Disassemble</span></span>|<span data-ttu-id="771f2-147">すべての逆アセンブル コンポーネントおよび解析コンポーネントは、このカテゴリを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="771f2-147">All disassembling and parsing components should implement this category.</span></span>|  
|<span data-ttu-id="771f2-148">CATID_Validate {9d0e410d-4cce-4536-83fa-4a5040674ad6}</span><span class="sxs-lookup"><span data-stu-id="771f2-148">CATID_Validate {9d0e410d-4cce-4536-83fa-4a5040674ad6}</span></span>|<span data-ttu-id="771f2-149">[検証]</span><span class="sxs-lookup"><span data-stu-id="771f2-149">Validate</span></span>|<span data-ttu-id="771f2-150">すべての検証コンポーネントはこのカテゴリを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="771f2-150">Validation components should implement this category.</span></span>|  
|<span data-ttu-id="771f2-151">CATID_PartyResolver {9d0e410e-4cce-4536-83fa-4a5040674ad6}</span><span class="sxs-lookup"><span data-stu-id="771f2-151">CATID_PartyResolver {9d0e410e-4cce-4536-83fa-4a5040674ad6}</span></span>|<span data-ttu-id="771f2-152">パーティの解決</span><span class="sxs-lookup"><span data-stu-id="771f2-152">ResolveParty</span></span>|<span data-ttu-id="771f2-153">パーティの解決コンポーネントに使用されるステージです。</span><span class="sxs-lookup"><span data-stu-id="771f2-153">Stage used for Party Resolution component.</span></span>|  
|<span data-ttu-id="771f2-154">CATID_Encoder {9d0e4108-4cce-4536-83fa-4a5040674ad6}</span><span class="sxs-lookup"><span data-stu-id="771f2-154">CATID_Encoder {9d0e4108-4cce-4536-83fa-4a5040674ad6}</span></span>|<span data-ttu-id="771f2-155">エンコード</span><span class="sxs-lookup"><span data-stu-id="771f2-155">Encode</span></span>|<span data-ttu-id="771f2-156">すべてのエンコード コンポーネントはこのカテゴリを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="771f2-156">All encoding components should implement this category.</span></span>|  
|<span data-ttu-id="771f2-157">CATID_AssemblingSerializer {9d0e4107-4cce-4536-83fa-4a5040674ad6}</span><span class="sxs-lookup"><span data-stu-id="771f2-157">CATID_AssemblingSerializer {9d0e4107-4cce-4536-83fa-4a5040674ad6}</span></span>|<span data-ttu-id="771f2-158">シリアル化します。</span><span class="sxs-lookup"><span data-stu-id="771f2-158">Serialize</span></span>|<span data-ttu-id="771f2-159">すべてのシリアル化コンポーネントおよびアセンブル コンポーネントは、このカテゴリを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="771f2-159">All serializing and assembling components should implement this category.</span></span>|  
|<span data-ttu-id="771f2-160">CATID_Any {9d0e4101-4cce-4536-83fa-4a5040674ad6}</span><span class="sxs-lookup"><span data-stu-id="771f2-160">CATID_Any {9d0e4101-4cce-4536-83fa-4a5040674ad6}</span></span>|<span data-ttu-id="771f2-161">上記の全ステージ</span><span class="sxs-lookup"><span data-stu-id="771f2-161">Any of these stages</span></span>|<span data-ttu-id="771f2-162">このカテゴリを実装するパイプライン コンポーネントは、任意のパイプライン ステージに配置できます。</span><span class="sxs-lookup"><span data-stu-id="771f2-162">If a pipeline component implements this category, it means that the component can be placed into any stage of a pipeline.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="771f2-163">参照</span><span class="sxs-lookup"><span data-stu-id="771f2-163">See Also</span></span>  
 <span data-ttu-id="771f2-164">[パイプライン デザイナーを使用してパイプラインを作成します。](../core/creating-pipelines-using-pipeline-designer.md) </span><span class="sxs-lookup"><span data-stu-id="771f2-164">[Creating Pipelines Using Pipeline Designer](../core/creating-pipelines-using-pipeline-designer.md) </span></span>  
 [<span data-ttu-id="771f2-165">パイプライン、ステージ、およびコンポーネントについて</span><span class="sxs-lookup"><span data-stu-id="771f2-165">About Pipelines, Stages, and Components</span></span>](../core/about-pipelines-stages-and-components.md)