---
title: 受信パイプライン |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive pipelines, about receive pipelines
- receive pipelines, message flow
- receive pipelines
- messages, receive pipelines
- messages, message flow
- pipelines, receive pipelines
- receive pipelines, stages
ms.assetid: ee75c1d4-00b7-4177-bca3-1447a39d2238
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0a248c69cb96603e9c4883e5d21caa39165da13
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268866"
---
# <a name="receive-pipelines"></a><span data-ttu-id="29050-102">受信パイプライン</span><span class="sxs-lookup"><span data-stu-id="29050-102">Receive Pipelines</span></span>
<span data-ttu-id="29050-103">次の図は、メッセージ処理のワークフローです。受信パイプラインが強調表示されています。</span><span class="sxs-lookup"><span data-stu-id="29050-103">The following figure shows the message processing workflow, highlighting the receive pipeline.</span></span>  
  
 <span data-ttu-id="29050-104">![メッセージ処理ワークフローのダイアグラム。](../core/media/ebiz-dev-busprcsb.gif "ebiz_dev_busprcsb")</span><span class="sxs-lookup"><span data-stu-id="29050-104">![Diagram of the message processing workflow.](../core/media/ebiz-dev-busprcsb.gif "ebiz_dev_busprcsb")</span></span>  
<span data-ttu-id="29050-105">メッセージ処理ワークフロー</span><span class="sxs-lookup"><span data-stu-id="29050-105">Depicts the message processing workflow.</span></span>  
  
 <span data-ttu-id="29050-106">受信パイプラインは、受信アダプターがメッセージを受け取った後に、メッセージを操作します。</span><span class="sxs-lookup"><span data-stu-id="29050-106">A receive pipeline operates on a message after it is received by the receive adapter.</span></span> <span data-ttu-id="29050-107">受信パイプラインは、最初のメッセージを取得し、いくつかの変換を行い、未加工のデータを 0 個のメッセージ、単一のメッセージ、または複数のメッセージに逆アセンブルします。</span><span class="sxs-lookup"><span data-stu-id="29050-107">The receive pipeline takes the initial message, performs some transformations, and disassembles the raw data into zero, one, or multiple messages.</span></span> <span data-ttu-id="29050-108">これらの操作により、各メッセージが BizTalk Server で処理可能な状態になります。</span><span class="sxs-lookup"><span data-stu-id="29050-108">These individual messages can then be processed by BizTalk Server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="29050-109">メッセージを破棄するコンポーネントをパイプラインに追加すると、受信パイプラインは、ゼロ メッセージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="29050-109">A receive pipeline can produce zero messages if a consuming component is added to the pipeline.</span></span> <span data-ttu-id="29050-110">この場合、パイプライン コンポーネントではメッセージが破棄されるため、出力メッセージは作成されません。</span><span class="sxs-lookup"><span data-stu-id="29050-110">In this case, the pipeline component consumes the message and does not produce any output messages.</span></span> <span data-ttu-id="29050-111">メッセージを破棄するコンポーネントが、逆アセンブルするコンポーネントの後に配置される場合は、最初のメッセージが破棄され、逆アセンブルするコンポーネントから後続のメッセージが取得されなくなったときに、パイプラインの実行が停止します。</span><span class="sxs-lookup"><span data-stu-id="29050-111">If a consuming component is placed after a disassembling component, pipeline execution stops after the first message is consumed and no subsequent messages are retrieved from the disassembling component.</span></span>  
  
 <span data-ttu-id="29050-112">ビジネス プロセスを作成するときに、新しい受信パイプラインを作成または 2 つの既定値のいずれかを使用することができます受信パイプラインが BizTalk Server に含まれる、パススルー受信パイプラインまたは XML 受信パイプラインです。</span><span class="sxs-lookup"><span data-stu-id="29050-112">When creating a business process, you can create a new receive pipeline or you can use one of the two default receive pipelines included in BizTalk Server—the pass-through receive pipeline or the XML receive pipeline.</span></span> <span data-ttu-id="29050-113">これらの既定のパイプラインの詳細については、次を参照してください。[既定のパイプライン](../core/default-pipelines.md)です。</span><span class="sxs-lookup"><span data-stu-id="29050-113">For more information about these default pipelines, see [Default Pipelines](../core/default-pipelines.md).</span></span>  
  
 <span data-ttu-id="29050-114">受信パイプラインは、4 つの段階で構成されています。 デコード、逆アセンブル、検証、およびパーティの解決。</span><span class="sxs-lookup"><span data-stu-id="29050-114">The receive pipeline consists of four stages: Decode, Disassemble, Validate, and ResolveParty.</span></span> <span data-ttu-id="29050-115">このトピックでは、これらのステージを設定する際に考慮すべき点について説明します。</span><span class="sxs-lookup"><span data-stu-id="29050-115">This topic contains design considerations for populating these stages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="29050-116">このリリースでは、ステージの順序の変更やステージの省略はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="29050-116">In this release, changing the order or presence of these stages in a pipeline is not supported.</span></span>  
  
## <a name="decode-stage"></a><span data-ttu-id="29050-117">デコード ステージ</span><span class="sxs-lookup"><span data-stu-id="29050-117">Decode stage</span></span>  
  
-   <span data-ttu-id="29050-118">このステージは、メッセージをデコードまたは復号化するコンポーネントに使用されます。</span><span class="sxs-lookup"><span data-stu-id="29050-118">This stage is used for components that decode or decrypt the message.</span></span>  
  
    -   <span data-ttu-id="29050-119">受信メッセージの形式を別の形式にデコードする必要がある場合、MIME/SMIME デコーダー パイプライン コンポーネントまたはカスタム デコード コンポーネントをこのステージに配置します。</span><span class="sxs-lookup"><span data-stu-id="29050-119">The MIME/SMIME Decoder pipeline component or a custom decoding component should be placed in this stage if the incoming messages need to be decoded from one format to another.</span></span>  
  
-   <span data-ttu-id="29050-120">このステージでは、1 つのメッセージを取得し、1 つのメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="29050-120">This stage takes one message and produces one message.</span></span>  
  
-   <span data-ttu-id="29050-121">このステージには、0 から 255 個までのコンポーネントを格納できます。</span><span class="sxs-lookup"><span data-stu-id="29050-121">This stage can contain between zero and 255 components.</span></span>  
  
-   <span data-ttu-id="29050-122">この段階のすべてのコンポーネントが実行されます。</span><span class="sxs-lookup"><span data-stu-id="29050-122">All components in this stage are run.</span></span>  
  
## <a name="disassemble-stage"></a><span data-ttu-id="29050-123">逆アセンブル ステージ</span><span class="sxs-lookup"><span data-stu-id="29050-123">Disassemble stage</span></span>  
  
-   <span data-ttu-id="29050-124">このステージは、メッセージを解析または逆アセンブルするコンポーネントに使用されます。</span><span class="sxs-lookup"><span data-stu-id="29050-124">This stage is used for components that parse or disassemble the message.</span></span>  
  
    -   <span data-ttu-id="29050-125">このステージのコンポーネントは、メッセージを検証して、メッセージの形式が識別可能かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="29050-125">The components within this stage probe the message to see if the format of the message is recognized.</span></span> <span data-ttu-id="29050-126">識別可能な形式を基にして、コンポーネントの 1 つがメッセージを逆アセンブルします。</span><span class="sxs-lookup"><span data-stu-id="29050-126">Based on the recognition of the format, one of the components disassembles the message.</span></span>  
  
    -   <span data-ttu-id="29050-127">このステージに 1 つ以上のコンポーネントが含まれている場合、メッセージの形式を識別する最初のコンポーネントだけが実行されます。</span><span class="sxs-lookup"><span data-stu-id="29050-127">If this stage contains more than one component, only the first component that recognizes the message format is run.</span></span> <span data-ttu-id="29050-128">このステージのすべてのコンポーネントがメッセージの形式を識別しない場合は、メッセージの処理が失敗します。</span><span class="sxs-lookup"><span data-stu-id="29050-128">If none of the components within the stage recognize the message format, the message processing fails.</span></span>  
  
    -   <span data-ttu-id="29050-129">このステージには、メッセージ コンテンツを逆アセンブルするために特殊な動作を実装するカスタム コンポーネントを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="29050-129">This stage should include any custom components that implement special behavior to disassemble the message contents.</span></span>  
  
    -   <span data-ttu-id="29050-130">このステージには、0 から 255 個までのコンポーネントを格納できます。</span><span class="sxs-lookup"><span data-stu-id="29050-130">This stage can contain between zero and 255 components.</span></span> <span data-ttu-id="29050-131">このステージにコンポーネントがない場合、メッセージはパス スルーされます。</span><span class="sxs-lookup"><span data-stu-id="29050-131">If there are no components in the stage, the message is passed through.</span></span>  
  
## <a name="validate-stage"></a><span data-ttu-id="29050-132">検証ステージ</span><span class="sxs-lookup"><span data-stu-id="29050-132">Validate stage</span></span>  
  
-   <span data-ttu-id="29050-133">このステージは、メッセージの形式を検証するコンポーネントに使用されます。</span><span class="sxs-lookup"><span data-stu-id="29050-133">This stage is used for components that validate the message format.</span></span>  
  
    -   <span data-ttu-id="29050-134">パイプライン コンポーネントは、コンポーネントに指定されるスキーマに準拠しているメッセージのみ処理します。</span><span class="sxs-lookup"><span data-stu-id="29050-134">A pipeline component processes only messages that conform to the schemas specified in that component.</span></span> <span data-ttu-id="29050-135">パイプラインのコンポーネントに関連付けられていないスキーマを持つメッセージをパイプラインが受け取った場合、そのメッセージは処理されません。</span><span class="sxs-lookup"><span data-stu-id="29050-135">If a pipeline receives a message whose schema is not associated with any component in the pipeline, that message is not processed.</span></span> <span data-ttu-id="29050-136">メッセージを送信するアダプターに応じて、メッセージが停止されるか、送信者に対してエラーが発行されます。</span><span class="sxs-lookup"><span data-stu-id="29050-136">Depending on the adapter that submits the message, the message is either suspended or an error is issued to the sender.</span></span>  
  
    -   <span data-ttu-id="29050-137">このステージのコンポーネントは、逆アセンブル ステージで作成された XML メッセージを検証するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="29050-137">Components in this stage are used to validate the XML messages produced by the Disassemble stage.</span></span> <span data-ttu-id="29050-138">このステージのコンポーネントでは、XML 検証を実行するスキーマを指定します。</span><span class="sxs-lookup"><span data-stu-id="29050-138">Components in this stage specify schemas to perform the XML validation.</span></span>  
  
-   <span data-ttu-id="29050-139">このステージには、0 から 255 個までのコンポーネントを格納できます。</span><span class="sxs-lookup"><span data-stu-id="29050-139">This stage can contain between zero and 255 components.</span></span>  
  
-   <span data-ttu-id="29050-140">この段階のすべてのコンポーネントが実行されます。</span><span class="sxs-lookup"><span data-stu-id="29050-140">All components in this stage are run.</span></span>  
  
    -   <span data-ttu-id="29050-141">このステージは、複数回実行される場合があります。</span><span class="sxs-lookup"><span data-stu-id="29050-141">This stage may be run more than once.</span></span> <span data-ttu-id="29050-142">またこのステージは、逆アセンブル ステージで作成された各メッセージに対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="29050-142">It runs once per message created by the Disassemble stage.</span></span>  
  
## <a name="resolveparty-stage"></a><span data-ttu-id="29050-143">パーティの解決ステージ</span><span class="sxs-lookup"><span data-stu-id="29050-143">ResolveParty stage</span></span>  
  
-   <span data-ttu-id="29050-144">この段階のプレース ホルダーでは、[パーティの解決パイプライン コンポーネント](../core/party-resolution-pipeline-component.md)です。</span><span class="sxs-lookup"><span data-stu-id="29050-144">This stage is a placeholder for the [Party Resolution Pipeline Component](../core/party-resolution-pipeline-component.md).</span></span>  
  
-   <span data-ttu-id="29050-145">このステージは、複数回実行される場合があります。</span><span class="sxs-lookup"><span data-stu-id="29050-145">This stage may be run more than once.</span></span> <span data-ttu-id="29050-146">またこのステージは、逆アセンブル ステージで作成された各メッセージに対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="29050-146">It runs once per message created by the Disassemble stage.</span></span>  
  
-   <span data-ttu-id="29050-147">このステージには、0 から 255 個までのコンポーネントを格納できます。</span><span class="sxs-lookup"><span data-stu-id="29050-147">This stage can contain between zero and 255 components.</span></span>  
  
-   <span data-ttu-id="29050-148">この段階のすべてのコンポーネントが実行されます。</span><span class="sxs-lookup"><span data-stu-id="29050-148">All components in this stage are run.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29050-149">参照</span><span class="sxs-lookup"><span data-stu-id="29050-149">See Also</span></span>  
 <span data-ttu-id="29050-150">[送信パイプライン](../core/send-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="29050-150">[Send Pipelines](../core/send-pipelines.md) </span></span>  
 <span data-ttu-id="29050-151">[パイプライン、ステージ、およびコンポーネントについて](../core/about-pipelines-stages-and-components.md) </span><span class="sxs-lookup"><span data-stu-id="29050-151">[About Pipelines, Stages, and Components](../core/about-pipelines-stages-and-components.md) </span></span>  
 <span data-ttu-id="29050-152">[パイプライン コンポーネントの種類](../core/types-of-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="29050-152">[Types of Pipeline Components](../core/types-of-pipeline-components.md) </span></span>  
 <span data-ttu-id="29050-153">[既定のパイプライン](../core/default-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="29050-153">[Default Pipelines](../core/default-pipelines.md) </span></span>  
 <span data-ttu-id="29050-154">[パイプライン テンプレート](../core/pipeline-templates.md) </span><span class="sxs-lookup"><span data-stu-id="29050-154">[Pipeline Templates](../core/pipeline-templates.md) </span></span>  
 <span data-ttu-id="29050-155">[パイプライン コンポーネント](../core/pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="29050-155">[Pipeline Components](../core/pipeline-components.md) </span></span>  
 [<span data-ttu-id="29050-156">パイプラインの種類</span><span class="sxs-lookup"><span data-stu-id="29050-156">Types of Pipelines</span></span>](../core/types-of-pipelines.md)