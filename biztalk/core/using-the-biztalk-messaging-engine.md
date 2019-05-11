---
title: BizTalk メッセージングを使用してエンジン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 598a7030b885057dc7781336c2925f0cb99b17fd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395185"
---
# <a name="using-the-biztalk-messaging-engine"></a><span data-ttu-id="9f8bd-102">BizTalk メッセージング エンジンを使用します。</span><span class="sxs-lookup"><span data-stu-id="9f8bd-102">Using the BizTalk Messaging Engine</span></span>
<span data-ttu-id="9f8bd-103">次の図は、メッセージング エンジンのアーキテクチャを示しています。</span><span class="sxs-lookup"><span data-stu-id="9f8bd-103">The following diagram illustrates the architecture of the Messaging Engine.</span></span> <span data-ttu-id="9f8bd-104">メッセージがアダプターによって受信および BizTalk Server に送信されるシナリオを示しています。</span><span class="sxs-lookup"><span data-stu-id="9f8bd-104">It shows a scenario in which a message is received by an adapter and submitted into BizTalk Server.</span></span>  
  
 <span data-ttu-id="9f8bd-105">![](../core/media/ebiz-prog-messaging1.gif "ebiz_prog_messaging1")</span><span class="sxs-lookup"><span data-stu-id="9f8bd-105">![](../core/media/ebiz-prog-messaging1.gif "ebiz_prog_messaging1")</span></span>  
<span data-ttu-id="9f8bd-106">メッセージング エンジンのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="9f8bd-106">Architecture of the Messaging Engine</span></span>  
  
 <span data-ttu-id="9f8bd-107">各アダプターに独自のインスタンスには、 **TransportProxy**メッセージング エンジンと対話するために使用するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="9f8bd-107">Each adapter has its own instance of a **TransportProxy** object that it uses to interact with the Messaging Engine.</span></span> <span data-ttu-id="9f8bd-108">アダプターは、バッチ、アトミックに処理されますが、メッセージング エンジンに対する作業を実行します。</span><span class="sxs-lookup"><span data-stu-id="9f8bd-108">Adapters perform work against the Messaging Engine in batches, which are processed atomically.</span></span> <span data-ttu-id="9f8bd-109">バッチは、SubmitMessage、suspendmessage、DeleteMessage などの操作のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="9f8bd-109">A batch is a collection of operations such as SubmitMessage, SuspendMessage, or DeleteMessage.</span></span>  
  
 <span data-ttu-id="9f8bd-110">以下は、一連のシナリオでは、アダプターがメッセージング エンジンにメッセージを送信するイベントです。</span><span class="sxs-lookup"><span data-stu-id="9f8bd-110">The following is the sequence of events for the scenario where an adapter submits a message to the Messaging Engine:</span></span>  
  
1.  <span data-ttu-id="9f8bd-111">アダプターは、新しいメッセージを作成し、データ ストリームをメッセージに接続します。</span><span class="sxs-lookup"><span data-stu-id="9f8bd-111">The adapter creates a new message and connects the data stream to the message.</span></span>  
  
2.  <span data-ttu-id="9f8bd-112">アダプターは、メッセージング エンジンから新しいバッチを取得します。</span><span class="sxs-lookup"><span data-stu-id="9f8bd-112">The adapter gets a new batch from the Messaging Engine.</span></span>  
  
3.  <span data-ttu-id="9f8bd-113">アダプターでは、送信するバッチにメッセージを追加します。</span><span class="sxs-lookup"><span data-stu-id="9f8bd-113">The adapter adds the message to the batch to be submitted.</span></span>  
  
4.  <span data-ttu-id="9f8bd-114">バッチがコミットされ、メッセージング エンジン スレッドのプールでキューに登録します。</span><span class="sxs-lookup"><span data-stu-id="9f8bd-114">The batch is committed and queued up on the Messaging Engine thread pool.</span></span>  
  
5.  <span data-ttu-id="9f8bd-115">メッセージング エンジン スレッドのプールでは、新しいバッチの処理を開始します。</span><span class="sxs-lookup"><span data-stu-id="9f8bd-115">The Messaging Engine thread pool starts processing the new batch.</span></span>  
  
6.  <span data-ttu-id="9f8bd-116">メッセージは、受信パイプラインで処理されます。</span><span class="sxs-lookup"><span data-stu-id="9f8bd-116">The message is processed in the receive pipeline.</span></span>  
  
7.  <span data-ttu-id="9f8bd-117">受信パイプラインは、0 個以上のメッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="9f8bd-117">The receive pipeline produces zero or more messages.</span></span> <span data-ttu-id="9f8bd-118">パイプラインは、すべてのエラーを返さないを提供するメッセージを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9f8bd-118">Pipelines can consume messages providing they do not return any errors.</span></span> <span data-ttu-id="9f8bd-119">受信パイプラインは、1 つ以上のメッセージを生成できます通常は、逆アセンブラー コンポーネントがメッセージの数に 1 つのインターチェンジを逆アセンブルするときに発生します。</span><span class="sxs-lookup"><span data-stu-id="9f8bd-119">Receive pipelines can produce more than one message; typically this happens when the dissassembler component disassembles a single interchange into many messages.</span></span> <span data-ttu-id="9f8bd-120">通常、受信パイプラインは、送信されたメッセージを XML に正規化します。</span><span class="sxs-lookup"><span data-stu-id="9f8bd-120">Typically the receive pipeline normalizes the submitted message into XML.</span></span>  
  
8.  <span data-ttu-id="9f8bd-121">マッピングが構成されている場合、パイプラインによって生成されたメッセージは、マッパーで処理されます。</span><span class="sxs-lookup"><span data-stu-id="9f8bd-121">The message(s) produced by the pipeline will be processed in the mapper if mapping is configured.</span></span>  
  
9. <span data-ttu-id="9f8bd-122">メッセージは、メッセージ エージェントまたはメッセージ ボックス データベースに公開されます。</span><span class="sxs-lookup"><span data-stu-id="9f8bd-122">The message(s) are published to the Message Agent or to the MessageBox database.</span></span>  
  
10. <span data-ttu-id="9f8bd-123">メッセージング エンジンがアダプター バッチの処理の結果を通知するコールバックします。</span><span class="sxs-lookup"><span data-stu-id="9f8bd-123">The Messaging Engine calls back the adapter to notify it of the outcome of the batch of work.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9f8bd-124">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="9f8bd-124">In This Section</span></span>  
  
-   [<span data-ttu-id="9f8bd-125">回復可能なインターチェンジ処理</span><span class="sxs-lookup"><span data-stu-id="9f8bd-125">Recoverable Interchange Processing</span></span>](../core/recoverable-interchange-processing.md)  
  
-   [<span data-ttu-id="9f8bd-126">メッセージの配信を順序付け</span><span class="sxs-lookup"><span data-stu-id="9f8bd-126">Ordered Delivery of Messages</span></span>](../core/ordered-delivery-of-messages.md)  
  
-   [<span data-ttu-id="9f8bd-127">エラー処理</span><span class="sxs-lookup"><span data-stu-id="9f8bd-127">Error Handling</span></span>](../core/error-handling.md)  
  
## <a name="see-also"></a><span data-ttu-id="9f8bd-128">参照</span><span class="sxs-lookup"><span data-stu-id="9f8bd-128">See Also</span></span>  
 <span data-ttu-id="9f8bd-129">[BizTalk Server がサイズの大きいメッセージを処理する方法](../core/how-biztalk-server-processes-large-messages.md) </span><span class="sxs-lookup"><span data-stu-id="9f8bd-129">[How BizTalk Server Processes Large Messages](../core/how-biztalk-server-processes-large-messages.md) </span></span>  
 <span data-ttu-id="9f8bd-130">[エンジン パフォーマンスの特性](../core/engine-performance-characteristics.md) </span><span class="sxs-lookup"><span data-stu-id="9f8bd-130">[Engine Performance Characteristics](../core/engine-performance-characteristics.md) </span></span>  
 <span data-ttu-id="9f8bd-131">[維持可能な最大のエンジン スループットの測定](../core/measuring-maximum-sustainable-engine-throughput.md) </span><span class="sxs-lookup"><span data-stu-id="9f8bd-131">[Measuring Maximum Sustainable Engine Throughput](../core/measuring-maximum-sustainable-engine-throughput.md) </span></span>  
 <span data-ttu-id="9f8bd-132">[エンジンの MST を測定するためのテスト シナリオ](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span><span class="sxs-lookup"><span data-stu-id="9f8bd-132">[Test Scenarios for Measuring MST of the Engine](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span></span>  
 [<span data-ttu-id="9f8bd-133">Microsoft BizTalk LoadGen 2007 ツールを使用</span><span class="sxs-lookup"><span data-stu-id="9f8bd-133">Using the Microsoft BizTalk LoadGen 2007 Tool</span></span>](../core/using-the-microsoft-biztalk-loadgen-2007-tool.md)