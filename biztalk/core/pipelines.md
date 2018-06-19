---
title: パイプライン |Microsoft ドキュメント
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
ms.openlocfilehash: b5fec49dcc9ba21c5d117188f280f7e9b65fe2b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22265274"
---
# <a name="pipelines"></a><span data-ttu-id="f22f5-102">パイプライン</span><span class="sxs-lookup"><span data-stu-id="f22f5-102">Pipelines</span></span>
<span data-ttu-id="f22f5-103">パイプラインは、パイプとフィルターの統合パターンを実装する Microsoft BizTalk Server のコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="f22f5-103">Pipelines are a component of Microsoft BizTalk Server that provides an implementation of the Pipes and Filters integration pattern.</span></span> <span data-ttu-id="f22f5-104">ビジネス上の理由で、メッセージの送受信中にメッセージを変換して、BizTalk Server への入力または BizTalk Server からの送信に使用できるように準備を行う必要が生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="f22f5-104">During the receiving and sending of messages, there are business reasons to perform transformations on messages to prepare them to enter or leave BizTalk Server.</span></span>  
  
 <span data-ttu-id="f22f5-105">一般的な例は、マップなどの BizTalk Server の特定の機能を利用するためにコンマ区切りフラット ファイルを XML ファイルに変換しなければならない場合などです。この変換は、フラット ファイル逆アセンブラー コンポーネントで行われます。</span><span class="sxs-lookup"><span data-stu-id="f22f5-105">A common example is that you may need to transform a comma-delimited flat file into an XML file in order to take advantage of certain features in BizTalk Server such as maps; the flat file disassembler component does just that.</span></span> <span data-ttu-id="f22f5-106">メッセージを送受信する前に統合シナリオで複数の種類のメッセージを変換しなければならない場合、パイプラインを使用してこの要件に対応します。</span><span class="sxs-lookup"><span data-stu-id="f22f5-106">It is common in integration scenarios to have a need to perform several types of transformations to a message before receiving or sending it; pipelines are used to meet this requirement.</span></span> <span data-ttu-id="f22f5-107">パイプラインを使用すると、開発者は、メッセージの送受信中に行う一連の変換を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="f22f5-107">Pipelines enable the developer to define a series of transformations that will be performed on a message as it is being received or sent.</span></span>  
  
 <span data-ttu-id="f22f5-108">パイプラインには、実行されるポートと対応して送信と受信の 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="f22f5-108">There are two types of pipelines, send and receive, and these match the ports in which they execute.</span></span> <span data-ttu-id="f22f5-109">*送信パイプライン*は送信ポートで実行され、要求/応答の応答部分では、受信ポート、中に*受信パイプライン*が実行されるには、受信場所、および送信請求-応答の応答部分で送信ポート。</span><span class="sxs-lookup"><span data-stu-id="f22f5-109">*Send pipelines* are executed in send ports and in the response portion of a request/response receive port, while *receive pipelines* are executed in receive locations, and in the response portion of a solicit/response send port.</span></span> <span data-ttu-id="f22f5-110">基本的に、受信パイプラインは、メッセージ ボックス データベースに公開されるメッセージの変換に使用されます。送信パイプラインは、サブスクライブされており BizTalk Server から送信されるメッセージに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f22f5-110">Essentially, receive pipelines are intended to be used to transform messages that are being published to the MessageBox database, while send pipelines are intended to be used on messages which have been subscribed to and are being sent out of BizTalk Server.</span></span>  
  
 <span data-ttu-id="f22f5-111">各パイプラインには、そのパイプラインの実行時に順に実行されるステージのセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f22f5-111">Each pipeline has a set of stages that are executed in order when the pipeline is executed.</span></span> <span data-ttu-id="f22f5-112">各ステージには、0 個以上のコンポーネントを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f22f5-112">Each stage can contain zero or more components.</span></span> <span data-ttu-id="f22f5-113">コンポーネントの最大数はステージによって異なります。</span><span class="sxs-lookup"><span data-stu-id="f22f5-113">The maximum number of components depends on the stage.</span></span>  
  
## <a name="receive-pipeline-stages"></a><span data-ttu-id="f22f5-114">受信パイプラインのステージ</span><span class="sxs-lookup"><span data-stu-id="f22f5-114">Receive Pipeline Stages</span></span>  
 <span data-ttu-id="f22f5-115">![受信パイプラインのステージ](../core/media/arch-pipe-receive.gif "arch_pipe_receive")</span><span class="sxs-lookup"><span data-stu-id="f22f5-115">![Receive pipeline stages](../core/media/arch-pipe-receive.gif "arch_pipe_receive")</span></span>  
  
|<span data-ttu-id="f22f5-116">段階</span><span class="sxs-lookup"><span data-stu-id="f22f5-116">Stage</span></span>|<span data-ttu-id="f22f5-117">用途</span><span class="sxs-lookup"><span data-stu-id="f22f5-117">Purpose</span></span>|  
|-----------|-------------|  
|<span data-ttu-id="f22f5-118">**デコード**</span><span class="sxs-lookup"><span data-stu-id="f22f5-118">**Decode**</span></span>|<span data-ttu-id="f22f5-119">メッセージ データを解読またはデコードします。</span><span class="sxs-lookup"><span data-stu-id="f22f5-119">Decrypts or decodes the message data</span></span>|  
|<span data-ttu-id="f22f5-120">**逆アセンブルします。**</span><span class="sxs-lookup"><span data-stu-id="f22f5-120">**Disassemble**</span></span>|<span data-ttu-id="f22f5-121">インターチェンジを小さいメッセージに逆アセンブルし、メッセージの内容を解析します。</span><span class="sxs-lookup"><span data-stu-id="f22f5-121">Disassembles an interchange into smaller messages and parses message contents</span></span>|  
|<span data-ttu-id="f22f5-122">**[検証]**</span><span class="sxs-lookup"><span data-stu-id="f22f5-122">**Validate**</span></span>|<span data-ttu-id="f22f5-123">メッセージ データを、通常、スキーマと照合して検証します。</span><span class="sxs-lookup"><span data-stu-id="f22f5-123">Validates the message data, generally against a schema</span></span>|  
|<span data-ttu-id="f22f5-124">**パーティを解決します。**</span><span class="sxs-lookup"><span data-stu-id="f22f5-124">**Resolve Party**</span></span>|<span data-ttu-id="f22f5-125">メッセージまたはメッセージのコンテキストの一部のセキュリティ トークンに関連付けられた BizTalk Server パーティを確認します。</span><span class="sxs-lookup"><span data-stu-id="f22f5-125">Identifies the BizTalk Server party associated with some security token in the message or message context</span></span>|  
  
## <a name="send-pipeline-stages"></a><span data-ttu-id="f22f5-126">送信パイプラインのステージ</span><span class="sxs-lookup"><span data-stu-id="f22f5-126">Send Pipeline Stages</span></span>  
 <span data-ttu-id="f22f5-127">![送信パイプラインのステージ](../core/media/arch-pipe-send.gif "arch_pipe_send")</span><span class="sxs-lookup"><span data-stu-id="f22f5-127">![Send pipeline stages](../core/media/arch-pipe-send.gif "arch_pipe_send")</span></span>  
  
|<span data-ttu-id="f22f5-128">段階</span><span class="sxs-lookup"><span data-stu-id="f22f5-128">Stage</span></span>|<span data-ttu-id="f22f5-129">用途</span><span class="sxs-lookup"><span data-stu-id="f22f5-129">Purpose</span></span>|  
|-----------|-------------|  
|<span data-ttu-id="f22f5-130">**プリアセンブルします。**</span><span class="sxs-lookup"><span data-stu-id="f22f5-130">**Pre-assemble**</span></span>|<span data-ttu-id="f22f5-131">メッセージをアセンブルする前に必要なメッセージ処理があれば実行します。</span><span class="sxs-lookup"><span data-stu-id="f22f5-131">Performs any message processing necessary before assembling the message</span></span>|  
|<span data-ttu-id="f22f5-132">**アセンブル**</span><span class="sxs-lookup"><span data-stu-id="f22f5-132">**Assemble**</span></span>|<span data-ttu-id="f22f5-133">エンベロープの追加や XML のフラット ファイルへの変換、受信パイプラインの逆アセンブル ステージを補完するその他のタスクなどの手順を実行して、メッセージをアセンブルし、送信のための準備をします。</span><span class="sxs-lookup"><span data-stu-id="f22f5-133">Assembles the message and prepares it to be transmitted by taking steps such as adding envelopes, converting XML to flat files, or other tasks complementary to the disassemble stage in a receive pipeline</span></span>|  
|<span data-ttu-id="f22f5-134">**エンコード**</span><span class="sxs-lookup"><span data-stu-id="f22f5-134">**Encode**</span></span>|<span data-ttu-id="f22f5-135">メッセージを配信前に暗号化またはエンコードします。</span><span class="sxs-lookup"><span data-stu-id="f22f5-135">Encodes or encrypts the message before delivery</span></span>|  
  
 <span data-ttu-id="f22f5-136">パイプラインのステージが、*実行モード*すべてのまたは複数のコンポーネントがステージに追加された場合に実行するコンポーネントを制御する、最初に一致します。</span><span class="sxs-lookup"><span data-stu-id="f22f5-136">A stage in a pipeline has an *execution mode* of either All or First Match, which controls the components that get executed if more than one component is added to a stage.</span></span> <span data-ttu-id="f22f5-137">実行モードが [すべて] に設定されているステージでは、ステージ内に構成されている順序で各コンポーネントが呼び出されてメッセージ処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="f22f5-137">For stages with a mode of All, each component is called to process the message in the order in which they are configured in the stage.</span></span> <span data-ttu-id="f22f5-138">モードが [First Match] の場合、一致するコンポーネントが見つかるまで、正しいコンポーネントを検出するためのポーリングが各コンポーネントに対して行われ、一致するコンポーネントが見つかるとそのコンポーネントが実行されて、残りのコンポーネントは実行されません。</span><span class="sxs-lookup"><span data-stu-id="f22f5-138">When the mode is First Match, each component is polled to indicate that it is the right component until a match is found, at which point the component that matches is executed, while the remaining components do not get executed.</span></span>  
  
 <span data-ttu-id="f22f5-139">実行モードの例として、受信パイプラインの逆アセンブル ステージは [First Match] ステージなので、ステージの各コンポーネントが呼び出され、そのコンポーネントでメッセージを認識して処理できるかどうかが評価されます。</span><span class="sxs-lookup"><span data-stu-id="f22f5-139">As an example of execution modes, the Disassemble stage of a receive pipeline is a First Match stage, thus each component in the stage is called to see if it recognizes the message and can process it.</span></span> <span data-ttu-id="f22f5-140">コンポーネントが肯定応答を返せば、そのステージの他のコンポーネントに対しては、メッセージを処理できるかどうかを検証するクエリは実行されません。</span><span class="sxs-lookup"><span data-stu-id="f22f5-140">If the component responds in the affirmative, then no other components in that stage are queried to see if they can also handle the message.</span></span> <span data-ttu-id="f22f5-141">これに対し、受信パイプラインのデコード ステージの実行モードは [すべて] なので、メッセージを処理するために、このステージのそれぞれのコンポーネントが構成順に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f22f5-141">However, the Decode stage of a receive pipeline has an execution mode of All, meaning that each component in this stage is called to process the message in the order in which they were configured.</span></span> <span data-ttu-id="f22f5-142">たとえば最初のデコーダーでメッセージを解読し、2 番目のデコーダーで圧縮形式からメッセージの圧縮解除を行うなどの処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="f22f5-142">The first decoder might be to decrypt the message, while the second might be to decompress the message from a zipped format.</span></span>  
  
 <span data-ttu-id="f22f5-143">パイプライン処理の実行モードに起因した問題の多くは、開発者が 1 つの受信パイプラインで複数の逆アセンブラーを使用した場合に生じます。</span><span class="sxs-lookup"><span data-stu-id="f22f5-143">One common consequence of execution mode in pipeline processing occurs when a developer wants to use multiple disassemblers in a single receive pipeline.</span></span> <span data-ttu-id="f22f5-144">通常、逆アセンブル コンポーネントの違いはわずかで、たとえば、よく似た 2 つのフラット ファイル逆アセンブラーで、構成されているスキーマのみが異なるというケースがあります。</span><span class="sxs-lookup"><span data-stu-id="f22f5-144">Often the disassembling components differ only slightly, for example two flat file disassemblers with similar but different schemas configured.</span></span> <span data-ttu-id="f22f5-145">このような場合、メッセージが実際に一致するのは 2 番目の逆アセンブラーで定義されているスキーマであっても、最初の逆アセンブラーでメッセージを処理できるとプローブで判断されることがあります。</span><span class="sxs-lookup"><span data-stu-id="f22f5-145">In this case, while the message might actually match the schema defined in the second disassembler, the first disassembler might determine through its probing that it can process the message.</span></span> <span data-ttu-id="f22f5-146">このときエラーが検出されメッセージが保留されるのは、メッセージを処理した後になってしまいます。</span><span class="sxs-lookup"><span data-stu-id="f22f5-146">It is only after processing the message that the error is discovered and the message suspended.</span></span> <span data-ttu-id="f22f5-147">これに対処するには、もっと具体的なプローブ ロジックを持つ逆アセンブラーを新しく作成するか、パイプラインを 2 つ作成することによって異なるメッセージをそれぞれ別の受信場所でを受信する方法をとる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f22f5-147">In these cases, you can either create a new disassembler which has more specific probing logic in it, or create two different pipelines and receive the different messages in different receive locations.</span></span>  
  
## <a name="pipeline-deployment"></a><span data-ttu-id="f22f5-148">パイプラインの展開</span><span class="sxs-lookup"><span data-stu-id="f22f5-148">Pipeline Deployment</span></span>  
 <span data-ttu-id="f22f5-149">パイプラインを含むアセンブリを展開するときに、管理データベースは、パイプラインを保存します。</span><span class="sxs-lookup"><span data-stu-id="f22f5-149">When you deploy an assembly that contains a pipeline, the Management database saves the pipeline.</span></span> <span data-ttu-id="f22f5-150">パイプラインは特定のバージョンのアセンブリに関連付けられており、結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="f22f5-150">The pipeline is associated with the specific version of the assembly with the following results:</span></span>  
  
-   <span data-ttu-id="f22f5-151">同じパイプラインを使用する複数のアセンブリを展開すると、管理データベースは各アセンブリのパイプラインに 1 つのエントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="f22f5-151">If you deploy multiple assemblies that use the same pipeline, the Management database creates one entry for the pipeline for each assembly.</span></span>  
  
-   <span data-ttu-id="f22f5-152">パイプラインが含まれるアセンブリを削除すると、管理データベースはそのアセンブリに関連付けられたパイプラインを削除します。</span><span class="sxs-lookup"><span data-stu-id="f22f5-152">When you remove an assembly that contains a pipeline, the Management database removes the pipeline that is associated with the assembly.</span></span> <span data-ttu-id="f22f5-153">管理データベースの関連付けられた各アセンブリにはパイプラインのコピーが存在するため、アセンブリを 1 つ削除しても他に影響はありません。</span><span class="sxs-lookup"><span data-stu-id="f22f5-153">Because there is a copy of the pipeline for each associated assembly in the Management database, removing one assembly does not affect the others.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f22f5-154">参照</span><span class="sxs-lookup"><span data-stu-id="f22f5-154">See Also</span></span>  
 [<span data-ttu-id="f22f5-155">成果物</span><span class="sxs-lookup"><span data-stu-id="f22f5-155">Artifacts</span></span>](../core/artifacts.md)