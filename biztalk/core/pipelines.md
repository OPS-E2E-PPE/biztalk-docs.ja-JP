---
title: パイプライン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines
- deploying, pipelines
- receive pipelines, about receive pipelines
- pipelines, deploying
- send pipelines, about send pipelines
- receive pipelines
- pipelines, about pipelines
- send pipelines, stages
- send pipelines
- pipelines, receive pipelines
- pipelines, send pipelines
- receive pipelines, stages
ms.assetid: 76947dd8-728a-4fa3-bd33-7a708ae82cac
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8ef3fab99e8356d00da859a29548064fc4af086
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395744"
---
# <a name="pipelines"></a><span data-ttu-id="c2f39-102">パイプライン</span><span class="sxs-lookup"><span data-stu-id="c2f39-102">Pipelines</span></span>
<span data-ttu-id="c2f39-103">パイプラインは、パイプとフィルターの統合パターンの実装を提供する Microsoft BizTalk Server のコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="c2f39-103">Pipelines are a component of Microsoft BizTalk Server that provides an implementation of the Pipes and Filters integration pattern.</span></span> <span data-ttu-id="c2f39-104">受信およびメッセージの送信中には、ビジネス上の理由を入力または BizTalk Server を準備するためにメッセージの変換を実行します。</span><span class="sxs-lookup"><span data-stu-id="c2f39-104">During the receiving and sending of messages, there are business reasons to perform transformations on messages to prepare them to enter or leave BizTalk Server.</span></span>  
  
 <span data-ttu-id="c2f39-105">一般的な例は、活用するために特定の機能では、BizTalk Server マップ; など、コンマで区切られたフラット ファイルを XML ファイルに変換する必要があります。フラット ファイル逆アセンブラー コンポーネントを実行します。</span><span class="sxs-lookup"><span data-stu-id="c2f39-105">A common example is that you may need to transform a comma-delimited flat file into an XML file in order to take advantage of certain features in BizTalk Server such as maps; the flat file disassembler component does just that.</span></span> <span data-ttu-id="c2f39-106">受信または送信する前にいくつかの種類のメッセージに変換を実行する必要がある統合シナリオでは一般的パイプラインは、この要件を満たすために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c2f39-106">It is common in integration scenarios to have a need to perform several types of transformations to a message before receiving or sending it; pipelines are used to meet this requirement.</span></span> <span data-ttu-id="c2f39-107">パイプラインを使用する一連のされるように、メッセージに対して実行される変換を定義する開発者の受信または送信します。</span><span class="sxs-lookup"><span data-stu-id="c2f39-107">Pipelines enable the developer to define a series of transformations that will be performed on a message as it is being received or sent.</span></span>  
  
 <span data-ttu-id="c2f39-108">これらが実行されるポートを一致と 2 つの種類のパイプライン、送信および受信するがあります。</span><span class="sxs-lookup"><span data-stu-id="c2f39-108">There are two types of pipelines, send and receive, and these match the ports in which they execute.</span></span> <span data-ttu-id="c2f39-109">*送信パイプライン*は送信ポートで実行され、要求/応答の応答部分では、受信ポート、中に*受信パイプライン*実行では、受信場所、および送信請求-応答の応答部分で送信ポート。</span><span class="sxs-lookup"><span data-stu-id="c2f39-109">*Send pipelines* are executed in send ports and in the response portion of a request/response receive port, while *receive pipelines* are executed in receive locations, and in the response portion of a solicit/response send port.</span></span> <span data-ttu-id="c2f39-110">基本的に、受信パイプラインは、送信パイプラインにサブスクライブしているし、BizTalk Server から送信されるメッセージで使用するものでは、メッセージ ボックス データベースに公開されるメッセージの変換に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c2f39-110">Essentially, receive pipelines are intended to be used to transform messages that are being published to the MessageBox database, while send pipelines are intended to be used on messages which have been subscribed to and are being sent out of BizTalk Server.</span></span>  
  
 <span data-ttu-id="c2f39-111">各パイプラインには、パイプラインが実行されるときの順序で実行されるステージのセットがあります。</span><span class="sxs-lookup"><span data-stu-id="c2f39-111">Each pipeline has a set of stages that are executed in order when the pipeline is executed.</span></span> <span data-ttu-id="c2f39-112">各ステージは、0 個以上のコンポーネントを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c2f39-112">Each stage can contain zero or more components.</span></span> <span data-ttu-id="c2f39-113">コンポーネントの最大数はステージによって異なります。</span><span class="sxs-lookup"><span data-stu-id="c2f39-113">The maximum number of components depends on the stage.</span></span>  
  
## <a name="receive-pipeline-stages"></a><span data-ttu-id="c2f39-114">受信パイプラインのステージ</span><span class="sxs-lookup"><span data-stu-id="c2f39-114">Receive Pipeline Stages</span></span>  
 <span data-ttu-id="c2f39-115">![受信パイプラインのステージ](../core/media/arch-pipe-receive.gif "arch_pipe_receive")</span><span class="sxs-lookup"><span data-stu-id="c2f39-115">![Receive pipeline stages](../core/media/arch-pipe-receive.gif "arch_pipe_receive")</span></span>  
  
|<span data-ttu-id="c2f39-116">ステージ</span><span class="sxs-lookup"><span data-stu-id="c2f39-116">Stage</span></span>|<span data-ttu-id="c2f39-117">目的</span><span class="sxs-lookup"><span data-stu-id="c2f39-117">Purpose</span></span>|  
|-----------|-------------|  
|<span data-ttu-id="c2f39-118">**デコード**</span><span class="sxs-lookup"><span data-stu-id="c2f39-118">**Decode**</span></span>|<span data-ttu-id="c2f39-119">復号化、またはメッセージ データをデコードします。</span><span class="sxs-lookup"><span data-stu-id="c2f39-119">Decrypts or decodes the message data</span></span>|  
|<span data-ttu-id="c2f39-120">**逆アセンブルします。**</span><span class="sxs-lookup"><span data-stu-id="c2f39-120">**Disassemble**</span></span>|<span data-ttu-id="c2f39-121">小さいメッセージにインターチェンジを逆アセンブルし、メッセージの内容を解析します。</span><span class="sxs-lookup"><span data-stu-id="c2f39-121">Disassembles an interchange into smaller messages and parses message contents</span></span>|  
|<span data-ttu-id="c2f39-122">**[検証]**</span><span class="sxs-lookup"><span data-stu-id="c2f39-122">**Validate**</span></span>|<span data-ttu-id="c2f39-123">一般に、スキーマに対して、メッセージ データを検証します。</span><span class="sxs-lookup"><span data-stu-id="c2f39-123">Validates the message data, generally against a schema</span></span>|  
|<span data-ttu-id="c2f39-124">**パーティを解決します。**</span><span class="sxs-lookup"><span data-stu-id="c2f39-124">**Resolve Party**</span></span>|<span data-ttu-id="c2f39-125">メッセージまたはメッセージのコンテキストでは、いくつかのセキュリティ トークンに関連付けられた BizTalk Server パーティを識別します。</span><span class="sxs-lookup"><span data-stu-id="c2f39-125">Identifies the BizTalk Server party associated with some security token in the message or message context</span></span>|  
  
## <a name="send-pipeline-stages"></a><span data-ttu-id="c2f39-126">送信パイプラインのステージ</span><span class="sxs-lookup"><span data-stu-id="c2f39-126">Send Pipeline Stages</span></span>  
 <span data-ttu-id="c2f39-127">![送信パイプラインのステージ](../core/media/arch-pipe-send.gif "arch_pipe_send")</span><span class="sxs-lookup"><span data-stu-id="c2f39-127">![Send pipeline stages](../core/media/arch-pipe-send.gif "arch_pipe_send")</span></span>  
  
|<span data-ttu-id="c2f39-128">ステージ</span><span class="sxs-lookup"><span data-stu-id="c2f39-128">Stage</span></span>|<span data-ttu-id="c2f39-129">目的</span><span class="sxs-lookup"><span data-stu-id="c2f39-129">Purpose</span></span>|  
|-----------|-------------|  
|<span data-ttu-id="c2f39-130">**プリアセンブルします。**</span><span class="sxs-lookup"><span data-stu-id="c2f39-130">**Pre-assemble**</span></span>|<span data-ttu-id="c2f39-131">すべてのメッセージ、メッセージをアセンブルする前に必要な処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="c2f39-131">Performs any message processing necessary before assembling the message</span></span>|  
|<span data-ttu-id="c2f39-132">**アセンブル**</span><span class="sxs-lookup"><span data-stu-id="c2f39-132">**Assemble**</span></span>|<span data-ttu-id="c2f39-133">メッセージをアセンブルし、送信される XML に変換するフラット ファイル、またはその他のタスクは、受信パイプラインの逆アセンブル ステージを補完、エンベロープの追加などの手順を実行できるように準備します</span><span class="sxs-lookup"><span data-stu-id="c2f39-133">Assembles the message and prepares it to be transmitted by taking steps such as adding envelopes, converting XML to flat files, or other tasks complementary to the disassemble stage in a receive pipeline</span></span>|  
|<span data-ttu-id="c2f39-134">**エンコード**</span><span class="sxs-lookup"><span data-stu-id="c2f39-134">**Encode**</span></span>|<span data-ttu-id="c2f39-135">配信する前にメッセージを暗号化またはエンコードします。</span><span class="sxs-lookup"><span data-stu-id="c2f39-135">Encodes or encrypts the message before delivery</span></span>|  
  
 <span data-ttu-id="c2f39-136">パイプラインのステージが、*実行モード*すべてまたは First Match ステージに 1 つ以上のコンポーネントが追加された場合に実行するコンポーネントを制御します。</span><span class="sxs-lookup"><span data-stu-id="c2f39-136">A stage in a pipeline has an *execution mode* of either All or First Match, which controls the components that get executed if more than one component is added to a stage.</span></span> <span data-ttu-id="c2f39-137">ステージのすべてのモードでは、ステージで構成されている順序でメッセージを処理する各コンポーネントが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c2f39-137">For stages with a mode of All, each component is called to process the message in the order in which they are configured in the stage.</span></span> <span data-ttu-id="c2f39-138">最初の一致のモードの場合は、各コンポーネントをポーリングして、この時点で一致するコンポーネントが実行されて、残りのコンポーネントは実行されません、一致が見つかるまで、正しいコンポーネントことを示します。</span><span class="sxs-lookup"><span data-stu-id="c2f39-138">When the mode is First Match, each component is polled to indicate that it is the right component until a match is found, at which point the component that matches is executed, while the remaining components do not get executed.</span></span>  
  
 <span data-ttu-id="c2f39-139">実行モードの例として、受信パイプラインの逆アセンブル ステージが First Match ステージには、ステージ内の各コンポーネントがメッセージを認識し、処理できるかどうかに表示すると呼ばれるためです。</span><span class="sxs-lookup"><span data-stu-id="c2f39-139">As an example of execution modes, the Disassemble stage of a receive pipeline is a First Match stage, thus each component in the stage is called to see if it recognizes the message and can process it.</span></span> <span data-ttu-id="c2f39-140">コンポーネントは、肯定で応答する場合、そのステージの他のコンポーネントなしにたずねますメッセージを処理できるかどうかを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2f39-140">If the component responds in the affirmative, then no other components in that stage are queried to see if they can also handle the message.</span></span> <span data-ttu-id="c2f39-141">ただし、受信パイプラインのデコード ステージには、このステージでは、各コンポーネントが呼び出され、構成された順序でメッセージを処理することを意味する、すべての実行モードがあります。</span><span class="sxs-lookup"><span data-stu-id="c2f39-141">However, the Decode stage of a receive pipeline has an execution mode of All, meaning that each component in this stage is called to process the message in the order in which they were configured.</span></span> <span data-ttu-id="c2f39-142">最初のデコーダーは、中、2 つ目は、zip 形式からメッセージを圧縮解除を行う可能性があります、メッセージを復号化する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c2f39-142">The first decoder might be to decrypt the message, while the second might be to decompress the message from a zipped format.</span></span>  
  
 <span data-ttu-id="c2f39-143">パイプライン処理の実行モードの 1 つの一般的な結果には、開発者が 1 つの受信パイプラインで複数の逆アセンブラーを使用する場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="c2f39-143">One common consequence of execution mode in pipeline processing occurs when a developer wants to use multiple disassemblers in a single receive pipeline.</span></span> <span data-ttu-id="c2f39-144">2 つのファイルの逆アセンブラーと似ていますが、別のスキーマが構成されているフラットなどは、多くの場合、逆アセンブラー コンポーネントはわずかに異なります。</span><span class="sxs-lookup"><span data-stu-id="c2f39-144">Often the disassembling components differ only slightly, for example two flat file disassemblers with similar but different schemas configured.</span></span> <span data-ttu-id="c2f39-145">この場合、メッセージでは、2 番目の逆アセンブラーで定義されたスキーマが実際に一致、中には、最初の逆アセンブラーがメッセージを処理できるとプローブで判断可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c2f39-145">In this case, while the message might actually match the schema defined in the second disassembler, the first disassembler might determine through its probing that it can process the message.</span></span> <span data-ttu-id="c2f39-146">エラーが検出されるメッセージと中断メッセージを処理した後のみになります。</span><span class="sxs-lookup"><span data-stu-id="c2f39-146">It is only after processing the message that the error is discovered and the message suspended.</span></span> <span data-ttu-id="c2f39-147">このような場合は、いずれかを具体的なプローブ ロジックを持つ新しい逆アセンブラーを作成または 2 つの異なるパイプラインを作成して受信できます、さまざまな異なる内のメッセージの受信場所。</span><span class="sxs-lookup"><span data-stu-id="c2f39-147">In these cases, you can either create a new disassembler which has more specific probing logic in it, or create two different pipelines and receive the different messages in different receive locations.</span></span>  
  
## <a name="pipeline-deployment"></a><span data-ttu-id="c2f39-148">パイプラインの展開</span><span class="sxs-lookup"><span data-stu-id="c2f39-148">Pipeline Deployment</span></span>  
 <span data-ttu-id="c2f39-149">パイプラインを含むアセンブリを展開するときに、パイプラインが、管理データベースに保存します。</span><span class="sxs-lookup"><span data-stu-id="c2f39-149">When you deploy an assembly that contains a pipeline, the Management database saves the pipeline.</span></span> <span data-ttu-id="c2f39-150">パイプラインは、次の結果でアセンブリの特定のバージョンに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="c2f39-150">The pipeline is associated with the specific version of the assembly with the following results:</span></span>  
  
-   <span data-ttu-id="c2f39-151">同じパイプラインを使用する複数のアセンブリを展開する場合、管理データベースは、各アセンブリのパイプラインの 1 つのエントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="c2f39-151">If you deploy multiple assemblies that use the same pipeline, the Management database creates one entry for the pipeline for each assembly.</span></span>  
  
-   <span data-ttu-id="c2f39-152">パイプラインを含むアセンブリを削除するときに、管理データベースは、アセンブリに関連付けられているパイプラインを削除します。</span><span class="sxs-lookup"><span data-stu-id="c2f39-152">When you remove an assembly that contains a pipeline, the Management database removes the pipeline that is associated with the assembly.</span></span> <span data-ttu-id="c2f39-153">管理データベースに関連付けられている各アセンブリのパイプラインのコピーがあるため、1 つのアセンブリを削除するには影響しません、他のユーザー。</span><span class="sxs-lookup"><span data-stu-id="c2f39-153">Because there is a copy of the pipeline for each associated assembly in the Management database, removing one assembly does not affect the others.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2f39-154">参照</span><span class="sxs-lookup"><span data-stu-id="c2f39-154">See Also</span></span>  
 [<span data-ttu-id="c2f39-155">アイテム</span><span class="sxs-lookup"><span data-stu-id="c2f39-155">Artifacts</span></span>](../core/artifacts.md)