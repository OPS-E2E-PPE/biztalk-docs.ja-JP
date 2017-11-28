---
title: "BizTalk メッセージングを使用してエンジン |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters, Messaging Engine
- adapters, TransportProxy object
- Messaging Engine, adapters
- Messaging Engine, architecture
- TransportProxy object
- Messaging Engine, how to
- architecture, Messaging Engine
- messages, Messaging Engine
ms.assetid: e6b6d1ec-38cd-4721-9673-ae40da003dec
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 701ed3e82eb75b98a948313a99bb4debc65a8cce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-biztalk-messaging-engine"></a><span data-ttu-id="50ad6-102">BizTalk メッセージング エンジンの使用</span><span class="sxs-lookup"><span data-stu-id="50ad6-102">Using the BizTalk Messaging Engine</span></span>
<span data-ttu-id="50ad6-103">メッセージング エンジンのアーキテクチャを次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="50ad6-103">The following diagram illustrates the architecture of the Messaging Engine.</span></span> <span data-ttu-id="50ad6-104">メッセージがアダプターによって受信され、BizTalk Server に送信されるシナリオを示しています。</span><span class="sxs-lookup"><span data-stu-id="50ad6-104">It shows a scenario in which a message is received by an adapter and submitted into BizTalk Server.</span></span>  
  
 ![](../core/media/ebiz-prog-messaging1.gif "ebiz_prog_messaging1")  
<span data-ttu-id="50ad6-105">メッセージング エンジンのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="50ad6-105">Architecture of the Messaging Engine</span></span>  
  
 <span data-ttu-id="50ad6-106">各アダプターには、独自のインスタンス、 **TransportProxy**メッセージング エンジンとの対話に使用されるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="50ad6-106">Each adapter has its own instance of a **TransportProxy** object that it uses to interact with the Messaging Engine.</span></span> <span data-ttu-id="50ad6-107">アダプターとメッセージング エンジンとの対話はバッチ単位で実行され、バッチには分離的な処理が適用されます。</span><span class="sxs-lookup"><span data-stu-id="50ad6-107">Adapters perform work against the Messaging Engine in batches, which are processed atomically.</span></span> <span data-ttu-id="50ad6-108">バッチとは、SubmitMessage、SuspendMessage、DeleteMessage などの操作をひとまとめにしたものです。</span><span class="sxs-lookup"><span data-stu-id="50ad6-108">A batch is a collection of operations such as SubmitMessage, SuspendMessage, or DeleteMessage.</span></span>  
  
 <span data-ttu-id="50ad6-109">アダプターがメッセージング エンジンにメッセージを送信するときに、具体的にどのような処理が行われるかを次に示します。</span><span class="sxs-lookup"><span data-stu-id="50ad6-109">The following is the sequence of events for the scenario where an adapter submits a message to the Messaging Engine:</span></span>  
  
1.  <span data-ttu-id="50ad6-110">アダプターが新しいメッセージを作成し、データ ストリームをメッセージに接続します。</span><span class="sxs-lookup"><span data-stu-id="50ad6-110">The adapter creates a new message and connects the data stream to the message.</span></span>  
  
2.  <span data-ttu-id="50ad6-111">アダプターが新しいバッチをメッセージング エンジンから取得します。</span><span class="sxs-lookup"><span data-stu-id="50ad6-111">The adapter gets a new batch from the Messaging Engine.</span></span>  
  
3.  <span data-ttu-id="50ad6-112">送信対象のバッチに対し、アダプターがメッセージを追加します。</span><span class="sxs-lookup"><span data-stu-id="50ad6-112">The adapter adds the message to the batch to be submitted.</span></span>  
  
4.  <span data-ttu-id="50ad6-113">バッチがコミットされ、メッセージング エンジンのスレッド プールのキューに格納されます。</span><span class="sxs-lookup"><span data-stu-id="50ad6-113">The batch is committed and queued up on the Messaging Engine thread pool.</span></span>  
  
5.  <span data-ttu-id="50ad6-114">メッセージング エンジンのスレッド プールが新しいバッチの処理を開始します。</span><span class="sxs-lookup"><span data-stu-id="50ad6-114">The Messaging Engine thread pool starts processing the new batch.</span></span>  
  
6.  <span data-ttu-id="50ad6-115">メッセージが受信パイプラインで処理されます。</span><span class="sxs-lookup"><span data-stu-id="50ad6-115">The message is processed in the receive pipeline.</span></span>  
  
7.  <span data-ttu-id="50ad6-116">受信パイプラインがメッセージ (ゼロ個以上) を生成します。</span><span class="sxs-lookup"><span data-stu-id="50ad6-116">The receive pipeline produces zero or more messages.</span></span> <span data-ttu-id="50ad6-117">パイプラインでは、エラーが発生しない限り、メッセージを処理できます。</span><span class="sxs-lookup"><span data-stu-id="50ad6-117">Pipelines can consume messages providing they do not return any errors.</span></span> <span data-ttu-id="50ad6-118">受信パイプラインで複数のメッセージが生成される場合もあります。複数のメッセージが生成される典型的なケースとしては、逆アセンブラー コンポーネントが、単一のインターチェンジを複数のメッセージに逆アセンブルする場合などが考えられます。</span><span class="sxs-lookup"><span data-stu-id="50ad6-118">Receive pipelines can produce more than one message; typically this happens when the dissassembler component disassembles a single interchange into many messages.</span></span> <span data-ttu-id="50ad6-119">通常、送信されたメッセージは、受信パイプラインによって XML として正規化されます。</span><span class="sxs-lookup"><span data-stu-id="50ad6-119">Typically the receive pipeline normalizes the submitted message into XML.</span></span>  
  
8.  <span data-ttu-id="50ad6-120">マッピングが構成されていた場合、パイプラインによって生成されたメッセージが、マッパーで処理されます。</span><span class="sxs-lookup"><span data-stu-id="50ad6-120">The message(s) produced by the pipeline will be processed in the mapper if mapping is configured.</span></span>  
  
9. <span data-ttu-id="50ad6-121">メッセージがメッセージ エージェントまたはメッセージ ボックス データベースに公開されます。</span><span class="sxs-lookup"><span data-stu-id="50ad6-121">The message(s) are published to the Message Agent or to the MessageBox database.</span></span>  
  
10. <span data-ttu-id="50ad6-122">メッセージング エンジンが、アダプターをコールバックし、バッチの処理結果を通知します。</span><span class="sxs-lookup"><span data-stu-id="50ad6-122">The Messaging Engine calls back the adapter to notify it of the outcome of the batch of work.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="50ad6-123">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="50ad6-123">In This Section</span></span>  
  
-   [<span data-ttu-id="50ad6-124">回復可能なインターチェンジ処理</span><span class="sxs-lookup"><span data-stu-id="50ad6-124">Recoverable Interchange Processing</span></span>](../core/recoverable-interchange-processing.md)  
  
-   [<span data-ttu-id="50ad6-125">メッセージの順次配送</span><span class="sxs-lookup"><span data-stu-id="50ad6-125">Ordered Delivery of Messages</span></span>](../core/ordered-delivery-of-messages.md)  
  
-   [<span data-ttu-id="50ad6-126">エラー処理</span><span class="sxs-lookup"><span data-stu-id="50ad6-126">Error Handling</span></span>](../core/error-handling.md)  
  
## <a name="see-also"></a><span data-ttu-id="50ad6-127">参照</span><span class="sxs-lookup"><span data-stu-id="50ad6-127">See Also</span></span>  
 <span data-ttu-id="50ad6-128">[BizTalk Server がサイズの大きいメッセージを処理する方法](../core/how-biztalk-server-processes-large-messages.md) </span><span class="sxs-lookup"><span data-stu-id="50ad6-128">[How BizTalk Server Processes Large Messages](../core/how-biztalk-server-processes-large-messages.md) </span></span>  
 <span data-ttu-id="50ad6-129">[エンジン パフォーマンスの特性](../core/engine-performance-characteristics.md) </span><span class="sxs-lookup"><span data-stu-id="50ad6-129">[Engine Performance Characteristics](../core/engine-performance-characteristics.md) </span></span>  
 <span data-ttu-id="50ad6-130">[維持可能な最大のエンジン スループットの測定](../core/measuring-maximum-sustainable-engine-throughput.md) </span><span class="sxs-lookup"><span data-stu-id="50ad6-130">[Measuring Maximum Sustainable Engine Throughput](../core/measuring-maximum-sustainable-engine-throughput.md) </span></span>  
 <span data-ttu-id="50ad6-131">[エンジンの MST を測定するためのシナリオをテストします。](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span><span class="sxs-lookup"><span data-stu-id="50ad6-131">[Test Scenarios for Measuring MST of the Engine](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span></span>  
 [<span data-ttu-id="50ad6-132">Microsoft BizTalk LoadGen 2007 ツールの使用</span><span class="sxs-lookup"><span data-stu-id="50ad6-132">Using the Microsoft BizTalk LoadGen 2007 Tool</span></span>](../core/using-the-microsoft-biztalk-loadgen-2007-tool.md)