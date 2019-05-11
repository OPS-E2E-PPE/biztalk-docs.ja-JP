---
title: パイプライン ステージ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3e24d6660e56bfbd44391b092152735f67fbb23
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395784"
---
# <a name="pipeline-stages"></a><span data-ttu-id="c62a7-102">パイプライン ステージ</span><span class="sxs-lookup"><span data-stu-id="c62a7-102">Pipeline Stages</span></span>
<span data-ttu-id="c62a7-103">このトピックで説明、**実行モード**プロパティとステージ関係します。</span><span class="sxs-lookup"><span data-stu-id="c62a7-103">This topic discusses the **Execution Mode** property and stage affinity.</span></span>  
  
## <a name="execution-mode-property"></a><span data-ttu-id="c62a7-104">実行モードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="c62a7-104">Execution Mode property</span></span>  
 <span data-ttu-id="c62a7-105">パイプラインの実行中には、パイプライン ステージは、メッセージの形式を認識する最初のコンポーネントのみまたはすべてのコンポーネントを実行できます。</span><span class="sxs-lookup"><span data-stu-id="c62a7-105">During the execution of a pipeline, the pipeline stages can run only the first component that recognizes the message format, or all components.</span></span> <span data-ttu-id="c62a7-106">実行パターンを決定するプロパティが**実行モード**します。</span><span class="sxs-lookup"><span data-stu-id="c62a7-106">The property that determines the execution pattern is **Execution Mode**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c62a7-107">このプロパティは読み取り専用で、ステージ、パイプライン テンプレートに含まれるが、重要な概念は、そのしくみを理解します。</span><span class="sxs-lookup"><span data-stu-id="c62a7-107">This property is read-only on the stages included in the pipeline templates, but understanding how it works is an important concept.</span></span>  
  
 <span data-ttu-id="c62a7-108">ときに、**実行モード**プロパティに設定されて**すべて**ステージ内のすべてのコンポーネントが構成されている順序で実行されます。</span><span class="sxs-lookup"><span data-stu-id="c62a7-108">When the **Execution Mode** property is set to **All**, all the components within the stage are run in the configured sequence.</span></span> <span data-ttu-id="c62a7-109">このモードでは、論理タスクを完了するいくつかのコンポーネントを実行します。</span><span class="sxs-lookup"><span data-stu-id="c62a7-109">This mode runs several components to complete a logical task.</span></span> <span data-ttu-id="c62a7-110">この場合、このパイプライン ステージにメッセージを処理中にエラーが発生したコンポーネントと、実行時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="c62a7-110">In this case, a run-time error results if any component encounters an error while processing a message during this pipeline stage.</span></span>  
  
 <span data-ttu-id="c62a7-111">パイプラインを使用して、いくつかの形式でメッセージを受信するときに、**実行モード**プロパティに設定されて**FirstMatch**します。</span><span class="sxs-lookup"><span data-stu-id="c62a7-111">When a pipeline is used to receive messages in several formats, then the **Execution Mode** property is set to **FirstMatch**.</span></span> <span data-ttu-id="c62a7-112">このモードでは、メッセージを認識する最初のコンポーネントのみが実行されます。</span><span class="sxs-lookup"><span data-stu-id="c62a7-112">In this mode, only the first component that recognizes the message is run.</span></span> <span data-ttu-id="c62a7-113">ステージのコンポーネントがメッセージを認識しなかった場合を実行時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="c62a7-113">If no components in the stage recognize the message, a run-time error results.</span></span>  
  
 <span data-ttu-id="c62a7-114">各ステージがあることができます独自ことに注意してください。**実行モード**パイプライン内の設定では、異なるステージは異なる実行モードであることができます。</span><span class="sxs-lookup"><span data-stu-id="c62a7-114">Note that each stage can have its own **Execution Mode** setting, so different stages within a pipeline can have different execution modes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c62a7-115">このリリースの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、すべての段階、送信パイプラインおよび受信パイプラインの逆アセンブルを除くすべての段階でなければ、**実行モード**プロパティに設定**すべて**します。</span><span class="sxs-lookup"><span data-stu-id="c62a7-115">In this release of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], all the stages in a send pipeline and all stages except Disassemble in a receive pipeline have the value of the **Execution Mode** property set to **All**.</span></span> <span data-ttu-id="c62a7-116">値、**実行モード**逆アセンブル ステージでプロパティに設定されて**FirstMatch**します。</span><span class="sxs-lookup"><span data-stu-id="c62a7-116">The value of the **Execution Mode** property in the Disassemble stage is set to **FirstMatch**.</span></span> <span data-ttu-id="c62a7-117">変更することはできません、**実行モード**ステージのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="c62a7-117">You cannot change the **Execution Mode** property of a stage.</span></span>  
  
#### <a name="to-read-pipeline-stage-properties"></a><span data-ttu-id="c62a7-118">パイプライン ステージのプロパティを読み取る</span><span class="sxs-lookup"><span data-stu-id="c62a7-118">To read pipeline stage properties</span></span>  
  
1.  <span data-ttu-id="c62a7-119">パイプライン デザイナーでステージの図形をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c62a7-119">In Pipeline Designer, click a stage shape.</span></span>  
  
2.  <span data-ttu-id="c62a7-120">プロパティ ウィンドウでの**全般** セクションで、次のプロパティの読み取り。</span><span class="sxs-lookup"><span data-stu-id="c62a7-120">In the Properties window, in the **General** section, read the following properties:</span></span>  
  
    |<span data-ttu-id="c62a7-121">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c62a7-121">Use this</span></span>|<span data-ttu-id="c62a7-122">目的</span><span class="sxs-lookup"><span data-stu-id="c62a7-122">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="c62a7-123">**名前**</span><span class="sxs-lookup"><span data-stu-id="c62a7-123">**Name**</span></span>|<span data-ttu-id="c62a7-124">ステージの名前を示します。</span><span class="sxs-lookup"><span data-stu-id="c62a7-124">Indicates the name of the stage.</span></span>|  
    |<span data-ttu-id="c62a7-125">**[実行モード]**</span><span class="sxs-lookup"><span data-stu-id="c62a7-125">**Execution Mode**</span></span>|<span data-ttu-id="c62a7-126">ステージの実行パターンを示します。</span><span class="sxs-lookup"><span data-stu-id="c62a7-126">Indicates the execution pattern of the stage.</span></span><br /><br /> <span data-ttu-id="c62a7-127">有効な値:**すべて**または**FirstMatch**</span><span class="sxs-lookup"><span data-stu-id="c62a7-127">Valid values: **All** or **FirstMatch**</span></span>|  
    |<span data-ttu-id="c62a7-128">**コンポーネントの最小数**</span><span class="sxs-lookup"><span data-stu-id="c62a7-128">**Minimum Number of Components**</span></span>|<span data-ttu-id="c62a7-129">ステージに追加できるパイプライン コンポーネントの最小数を示します。</span><span class="sxs-lookup"><span data-stu-id="c62a7-129">Indicates the minimum number of pipeline components that can be added to the stage.</span></span>|  
    |<span data-ttu-id="c62a7-130">**コンポーネントの最大数**</span><span class="sxs-lookup"><span data-stu-id="c62a7-130">**Maximum Number of Components**</span></span>|<span data-ttu-id="c62a7-131">ステージに追加できるパイプライン コンポーネントの最大数を示します。</span><span class="sxs-lookup"><span data-stu-id="c62a7-131">Indicates the maximum number of pipeline components that can be added to the stage.</span></span>|  
    |<span data-ttu-id="c62a7-132">**StageID**</span><span class="sxs-lookup"><span data-stu-id="c62a7-132">**StageID**</span></span>|<span data-ttu-id="c62a7-133">ステージの一意の識別子を示します。</span><span class="sxs-lookup"><span data-stu-id="c62a7-133">Indicates the unique identifier for the stage.</span></span>|  
  
## <a name="stage-affinity"></a><span data-ttu-id="c62a7-134">ステージ関係</span><span class="sxs-lookup"><span data-stu-id="c62a7-134">Stage affinity</span></span>  
 <span data-ttu-id="c62a7-135">パイプライン コンポーネントがあるステージ関係を特定のステージまたはステージ、パイプライン内で使用するために作成されたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="c62a7-135">Pipeline components have stage affinity, meaning that they are created for use within a particular stage or stages in a pipeline.</span></span>  
  
 <span data-ttu-id="c62a7-136">COM ベースのパイプライン コンポーネントは、実装カテゴリとしてステージ ID を使用して自身を登録することにより、ステージ関係を express にします。NET ベースのパイプライン コンポーネントを使用して、ステージ関係を指定する、 **ComponentCategory**クラス属性。</span><span class="sxs-lookup"><span data-stu-id="c62a7-136">COM-based pipeline components express their stage affinity by registering themselves using the stage ID as the implementation category, while .NET-based pipeline components specify their stage affinity by using the **ComponentCategory** class attribute.</span></span> <span data-ttu-id="c62a7-137">コンポーネント自体を 1 つ以上のステージに関連付けることは、コンポーネントが 1 つ以上の実装カテゴリを持つことができますまたは**ComponentCategory**属性。</span><span class="sxs-lookup"><span data-stu-id="c62a7-137">Note that it is possible for a component to associate itself with more than one stage—components can have more than one implementation category or **ComponentCategory** attribute.</span></span>  
  
 <span data-ttu-id="c62a7-138">次の表は、使用可能なコンポーネントのカテゴリとその関連付けられたステージを示します。</span><span class="sxs-lookup"><span data-stu-id="c62a7-138">The following table shows the available component categories and their associated stages.</span></span>  
  
|<span data-ttu-id="c62a7-139">コンポーネント カテゴリ</span><span class="sxs-lookup"><span data-stu-id="c62a7-139">Component category</span></span>|<span data-ttu-id="c62a7-140">ステージのコンポーネントを配置できる場所</span><span class="sxs-lookup"><span data-stu-id="c62a7-140">Stage where component can be placed</span></span>|<span data-ttu-id="c62a7-141">説明</span><span class="sxs-lookup"><span data-stu-id="c62a7-141">Description</span></span>|  
|------------------------|-----------------------------------------|-----------------|  
|<span data-ttu-id="c62a7-142">CATID_Decoder {9d0e4103-4cce-4536-83fa-4a5040674ad6}</span><span class="sxs-lookup"><span data-stu-id="c62a7-142">CATID_Decoder {9d0e4103-4cce-4536-83fa-4a5040674ad6}</span></span>|<span data-ttu-id="c62a7-143">デコード</span><span class="sxs-lookup"><span data-stu-id="c62a7-143">Decode</span></span>|<span data-ttu-id="c62a7-144">すべてのデコード コンポーネントは、このカテゴリを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c62a7-144">All decoding components should implement this category.</span></span>|  
|<span data-ttu-id="c62a7-145">CATID_DisassemblingParser {9d0e4105-4cce-4536-83fa-4a5040674ad6}</span><span class="sxs-lookup"><span data-stu-id="c62a7-145">CATID_DisassemblingParser {9d0e4105-4cce-4536-83fa-4a5040674ad6}</span></span>|<span data-ttu-id="c62a7-146">逆アセンブルします。</span><span class="sxs-lookup"><span data-stu-id="c62a7-146">Disassemble</span></span>|<span data-ttu-id="c62a7-147">すべての逆アセンブル コンポーネントおよび解析コンポーネントは、このカテゴリを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c62a7-147">All disassembling and parsing components should implement this category.</span></span>|  
|<span data-ttu-id="c62a7-148">CATID_Validate {9d0e410d-4cce-4536-83fa-4a5040674ad6}</span><span class="sxs-lookup"><span data-stu-id="c62a7-148">CATID_Validate {9d0e410d-4cce-4536-83fa-4a5040674ad6}</span></span>|<span data-ttu-id="c62a7-149">[検証]</span><span class="sxs-lookup"><span data-stu-id="c62a7-149">Validate</span></span>|<span data-ttu-id="c62a7-150">検証コンポーネントは、このカテゴリを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c62a7-150">Validation components should implement this category.</span></span>|  
|<span data-ttu-id="c62a7-151">CATID_PartyResolver {9d0e410e-4cce-4536-83fa-4a5040674ad6}</span><span class="sxs-lookup"><span data-stu-id="c62a7-151">CATID_PartyResolver {9d0e410e-4cce-4536-83fa-4a5040674ad6}</span></span>|<span data-ttu-id="c62a7-152">パーティの解決</span><span class="sxs-lookup"><span data-stu-id="c62a7-152">ResolveParty</span></span>|<span data-ttu-id="c62a7-153">パーティの解決コンポーネントに使用する段階です。</span><span class="sxs-lookup"><span data-stu-id="c62a7-153">Stage used for Party Resolution component.</span></span>|  
|<span data-ttu-id="c62a7-154">CATID_Encoder {9d0e4108-4cce-4536-83fa-4a5040674ad6}</span><span class="sxs-lookup"><span data-stu-id="c62a7-154">CATID_Encoder {9d0e4108-4cce-4536-83fa-4a5040674ad6}</span></span>|<span data-ttu-id="c62a7-155">エンコード</span><span class="sxs-lookup"><span data-stu-id="c62a7-155">Encode</span></span>|<span data-ttu-id="c62a7-156">すべてのエンコード コンポーネントは、このカテゴリを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c62a7-156">All encoding components should implement this category.</span></span>|  
|<span data-ttu-id="c62a7-157">CATID_AssemblingSerializer {9d0e4107-4cce-4536-83fa-4a5040674ad6}</span><span class="sxs-lookup"><span data-stu-id="c62a7-157">CATID_AssemblingSerializer {9d0e4107-4cce-4536-83fa-4a5040674ad6}</span></span>|<span data-ttu-id="c62a7-158">シリアル化します。</span><span class="sxs-lookup"><span data-stu-id="c62a7-158">Serialize</span></span>|<span data-ttu-id="c62a7-159">すべてのシリアル化およびアセンブラー コンポーネントは、このカテゴリを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c62a7-159">All serializing and assembling components should implement this category.</span></span>|  
|<span data-ttu-id="c62a7-160">CATID_Any {9d0e4101-4cce-4536-83fa-4a5040674ad6}</span><span class="sxs-lookup"><span data-stu-id="c62a7-160">CATID_Any {9d0e4101-4cce-4536-83fa-4a5040674ad6}</span></span>|<span data-ttu-id="c62a7-161">これらのステージのいずれか</span><span class="sxs-lookup"><span data-stu-id="c62a7-161">Any of these stages</span></span>|<span data-ttu-id="c62a7-162">パイプライン コンポーネントは、このカテゴリを実装する場合は、コンポーネントをパイプラインのすべてのステージに配置できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="c62a7-162">If a pipeline component implements this category, it means that the component can be placed into any stage of a pipeline.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c62a7-163">参照</span><span class="sxs-lookup"><span data-stu-id="c62a7-163">See Also</span></span>  
 <span data-ttu-id="c62a7-164">[パイプライン デザイナーを使用してパイプラインを作成します。](../core/creating-pipelines-using-pipeline-designer.md) </span><span class="sxs-lookup"><span data-stu-id="c62a7-164">[Creating Pipelines Using Pipeline Designer](../core/creating-pipelines-using-pipeline-designer.md) </span></span>  
 [<span data-ttu-id="c62a7-165">パイプライン、ステージ、およびコンポーネントについて</span><span class="sxs-lookup"><span data-stu-id="c62a7-165">About Pipelines, Stages, and Components</span></span>](../core/about-pipelines-stages-and-components.md)