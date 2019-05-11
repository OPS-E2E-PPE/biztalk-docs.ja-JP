---
title: 送信パイプライン |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send pipelines, message flow
- send pipelines, about send pipelines
- messages, message flow
- send pipelines, stages
- pipelines, send pipelines
- messages, send pipelines
ms.assetid: c963b2d8-3b2b-4575-8105-c750deae8189
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38b33fc28e9a8ec051f00c846275451a7fcbcb96
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65250453"
---
# <a name="send-pipelines"></a><span data-ttu-id="16e88-102">送信パイプライン</span><span class="sxs-lookup"><span data-stu-id="16e88-102">Send Pipelines</span></span>
<span data-ttu-id="16e88-103">次の図は、メッセージ処理のワークフローです。送信パイプラインが強調表示されています。</span><span class="sxs-lookup"><span data-stu-id="16e88-103">The following figure shows the message processing workflow, highlighting the send pipeline.</span></span>  
  
 <span data-ttu-id="16e88-104">![メッセージを処理するためのワークフローのダイアグラム。](../core/media/ebiz-dev-busprcsadptc.gif "ebiz_dev_busprcsadptc")</span><span class="sxs-lookup"><span data-stu-id="16e88-104">![Diagram of workflow for processing a message.](../core/media/ebiz-dev-busprcsadptc.gif "ebiz_dev_busprcsadptc")</span></span>  
<span data-ttu-id="16e88-105">メッセージ処理ワークフロー</span><span class="sxs-lookup"><span data-stu-id="16e88-105">Depicts the message processing workflow.</span></span>  
  
 <span data-ttu-id="16e88-106">送信パイプラインでは、最終的な送信先に送られる前のドキュメントが処理されます。</span><span class="sxs-lookup"><span data-stu-id="16e88-106">A send pipeline is responsible for processing documents before sending them to their final destinations.</span></span> <span data-ttu-id="16e88-107">送信パイプラインは、1 つのメッセージを取得し、送信する 1 つのメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="16e88-107">The send pipeline takes one message and produces one message to send.</span></span>  
  
 <span data-ttu-id="16e88-108">新しい送信パイプラインを作成することも BizTalk Server に含まれる 2 つの既定の送信パイプラインのいずれかを使用することができます: パススルー送信パイプラインと XML 送信パイプラインです。</span><span class="sxs-lookup"><span data-stu-id="16e88-108">You can create a new send pipeline or you can use one of the two default send pipelines included in BizTalk Server—the pass-through send pipeline and the XML send pipeline.</span></span>  
  
 <span data-ttu-id="16e88-109">既定では、送信パイプラインは 3 つの空のステージで構成されます。プリアセンブル、アセンブル、およびエンコードします。</span><span class="sxs-lookup"><span data-stu-id="16e88-109">By default, the send pipeline consists of three empty stages: Pre-assemble, Assemble and Encode.</span></span> <span data-ttu-id="16e88-110">このトピックでは、これらのステージを設定する際に考慮すべき点について説明します。</span><span class="sxs-lookup"><span data-stu-id="16e88-110">This topic contains design considerations for populating these stages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="16e88-111">使用するコンポーネントをパイプラインに追加すると、送信パイプラインは、ゼロ メッセージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="16e88-111">A send pipeline can produce zero messages when a consuming component is added to the pipeline.</span></span>  
  
## <a name="pre-assemble-stage"></a><span data-ttu-id="16e88-112">プリアセンブル ステージ</span><span class="sxs-lookup"><span data-stu-id="16e88-112">Pre-assemble stage</span></span>  
  
-   <span data-ttu-id="16e88-113">このステージは、メッセージのシリアル化前にメッセージに対して処理を行うカスタム コンポーネントのプレースホルダーです。</span><span class="sxs-lookup"><span data-stu-id="16e88-113">This stage is a placeholder for custom components that should perform some action on the message before the message is serialized.</span></span>  
  
-   <span data-ttu-id="16e88-114">このステージは、メッセージごとに一度ずつ実行されます。</span><span class="sxs-lookup"><span data-stu-id="16e88-114">This stage is run once per message.</span></span>  
  
-   <span data-ttu-id="16e88-115">このステージには、0 から 255 個までのコンポーネントを格納できます。</span><span class="sxs-lookup"><span data-stu-id="16e88-115">This stage can contain between zero and 255 components.</span></span>  
  
-   <span data-ttu-id="16e88-116">この段階のすべてのコンポーネントが実行されます。</span><span class="sxs-lookup"><span data-stu-id="16e88-116">All components in this stage are run.</span></span>  
  
## <a name="assemble-stage"></a><span data-ttu-id="16e88-117">アセンブル ステージ</span><span class="sxs-lookup"><span data-stu-id="16e88-117">Assemble stage</span></span>  
  
-   <span data-ttu-id="16e88-118">このステージのコンポーネントは、メッセージのアセンブルまたはシリアル化を行い、XML への変換または XML からの変換を実行します。</span><span class="sxs-lookup"><span data-stu-id="16e88-118">Components in this stage are responsible for assembling or serializing the message and converting it to or from XML.</span></span>  
  
-   <span data-ttu-id="16e88-119">このステージには、0 または 1 個のコンポーネントを格納できます。</span><span class="sxs-lookup"><span data-stu-id="16e88-119">This stage accepts zero components or one component.</span></span>  
  
-   <span data-ttu-id="16e88-120">この段階のすべてのコンポーネントが実行されます。</span><span class="sxs-lookup"><span data-stu-id="16e88-120">All components in this stage are run.</span></span>  
  
## <a name="encode-stage"></a><span data-ttu-id="16e88-121">エンコード ステージ</span><span class="sxs-lookup"><span data-stu-id="16e88-121">Encode stage</span></span>  
  
-   <span data-ttu-id="16e88-122">このステージは、メッセージをエンコードまたは暗号化するコンポーネントに使用されます。</span><span class="sxs-lookup"><span data-stu-id="16e88-122">This stage is used for components that encode or encrypt the message.</span></span>  
  
    -   <span data-ttu-id="16e88-123">メッセージの署名が必要な場合は、このステージに MIME/SMIME エンコーダー コンポーネントまたはカスタム エンコード コンポーネントを配置します。</span><span class="sxs-lookup"><span data-stu-id="16e88-123">Place the MIME/SMIME Encoder component or a custom encoding component in this stage if message signing is required.</span></span>  
  
-   <span data-ttu-id="16e88-124">このステージは、メッセージごとに一度ずつ実行されます。</span><span class="sxs-lookup"><span data-stu-id="16e88-124">This stage is run once per message.</span></span>  
  
-   <span data-ttu-id="16e88-125">このステージには、0 から 255 個までのコンポーネントを格納できます。</span><span class="sxs-lookup"><span data-stu-id="16e88-125">This stage can contain between zero and 255 components.</span></span>  
  
-   <span data-ttu-id="16e88-126">このステージのすべてのコンポーネントが実行されます。</span><span class="sxs-lookup"><span data-stu-id="16e88-126">All components in this stage are executed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16e88-127">参照</span><span class="sxs-lookup"><span data-stu-id="16e88-127">See Also</span></span>  
 <span data-ttu-id="16e88-128">[受信パイプライン](../core/receive-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="16e88-128">[Receive Pipelines](../core/receive-pipelines.md) </span></span>  
 <span data-ttu-id="16e88-129">[パイプライン、ステージ、およびコンポーネントについて](../core/about-pipelines-stages-and-components.md) </span><span class="sxs-lookup"><span data-stu-id="16e88-129">[About Pipelines, Stages, and Components](../core/about-pipelines-stages-and-components.md) </span></span>  
 <span data-ttu-id="16e88-130">[パイプラインの種類](../core/types-of-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="16e88-130">[Types of Pipelines](../core/types-of-pipelines.md) </span></span>  
 <span data-ttu-id="16e88-131">[既定のパイプライン](../core/default-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="16e88-131">[Default Pipelines](../core/default-pipelines.md) </span></span>  
 <span data-ttu-id="16e88-132">[パイプライン テンプレート](../core/pipeline-templates.md) </span><span class="sxs-lookup"><span data-stu-id="16e88-132">[Pipeline Templates](../core/pipeline-templates.md) </span></span>  
 <span data-ttu-id="16e88-133">[パイプライン コンポーネント](../core/pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="16e88-133">[Pipeline Components](../core/pipeline-components.md) </span></span>  
 [<span data-ttu-id="16e88-134">パイプライン コンポーネントの種類</span><span class="sxs-lookup"><span data-stu-id="16e88-134">Types of Pipeline Components</span></span>](../core/types-of-pipeline-components.md)