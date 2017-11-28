---
title: "オーケストレーションでのデザイン パターンを実装する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Aggregator pattern, orchestrations
- Error Handling pattern [orchestrations]
- patterns, orchestrations
- designing, orchestrations
- orchestrations, designing
- Exception Handling and Compensation pattern [orchestrations]
- Parallel Convoy pattern [orchestrations]
- Dynamic Router pattern [orchestrations]
- orchestrations, patterns
- patterns
- Composed Message Processor pattern [orchestrations]
- Suspend with Retry pattern, orchestrations
- Calling Pipelines from Orchestration pattern [orchestrations]
- Message Filter pattern [orchestrations]
- Message Broker pattern [orchestrations]
- Content-Based Router pattern [orchestrations]
- Sequential Convoy pattern [orchestrations]
- Scatter and Gather pattern [orchestrations]
- Splitter pattern, orchestrations
- Message Translator pattern [orchestrations]
ms.assetid: f62ba955-018a-40e7-b303-497acc906019
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a4837ddf1199425a76a6fa82bbfd6e44615b6c7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="implementing-design-patterns-in-orchestrations"></a><span data-ttu-id="2f37b-102">オーケストレーションでのデザイン パターンの実装</span><span class="sxs-lookup"><span data-stu-id="2f37b-102">Implementing Design Patterns in Orchestrations</span></span>
<span data-ttu-id="2f37b-103">ここでは、BizTalk Server の一般的なプログラミング パターンとエンタープライズ統合パターンについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2f37b-103">This section discusses the common patterns of BizTalk Server programming as well as enterprise integration patterns.</span></span> <span data-ttu-id="2f37b-104">単一のパターン、または複数のパターンの組み合わせを利用してビジネス プロセスをデザインし、そのデザインを BizTalk オーケストレーション デザイナーの図形によって実装することができます。</span><span class="sxs-lookup"><span data-stu-id="2f37b-104">You can leverage a single pattern or combine multiple patterns to design your business process and then implement the design by using shapes in BizTalk Orchestration Designer.</span></span>  
  
## <a name="design-patterns"></a><span data-ttu-id="2f37b-105">デザイン パターン</span><span class="sxs-lookup"><span data-stu-id="2f37b-105">Design Patterns</span></span>  
 <span data-ttu-id="2f37b-106">次のエントリでは、各パターンについて簡潔に説明し、BizTalk オーケストレーション デザイナーを使用したパターンの実装方法を説明した他のトピックやサンプルについても記載しています。</span><span class="sxs-lookup"><span data-stu-id="2f37b-106">The following entries briefly describe each pattern and point to the topics or samples that show how to implement the patterns using BizTalk Orchestration Designer.</span></span>  
  
### <a name="aggregator"></a><span data-ttu-id="2f37b-107">アグリゲーター</span><span class="sxs-lookup"><span data-stu-id="2f37b-107">Aggregator</span></span>  
 <span data-ttu-id="2f37b-108">アグリゲーターは、複数のソースから情報を取得して単一のメッセージに統合するパターンです。</span><span class="sxs-lookup"><span data-stu-id="2f37b-108">Aggregator is the pattern of receiving information from multiple sources and consolidating it into a single message.</span></span> <span data-ttu-id="2f37b-109">このパターンの例は、」の Aggregate.odx を参照してください。[アグリゲーター (BizTalk Server サンプル)](../core/aggregator-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="2f37b-109">For an example of this pattern, see Aggregate.odx in [Aggregator (BizTalk Server Sample)](../core/aggregator-biztalk-server-sample.md).</span></span>  
  
### <a name="calling-pipelines-from-an-orchestration"></a><span data-ttu-id="2f37b-110">オーケストレーションからのパイプラインの呼び出し</span><span class="sxs-lookup"><span data-stu-id="2f37b-110">Calling Pipelines from an Orchestration</span></span>  
 <span data-ttu-id="2f37b-111">使用しているオーケストレーションから送信パイプラインおよび受信パイプラインを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="2f37b-111">You can call send and receive pipelines from your orchestrations.</span></span> <span data-ttu-id="2f37b-112">これによって、パイプラインの再利用が可能になり、パイプライン ステージからオーケストレーションを分離できます。</span><span class="sxs-lookup"><span data-stu-id="2f37b-112">This allows the reuse of pipelines and helps maintain the decoupling of an orchestration from the pipeline stages.</span></span> <span data-ttu-id="2f37b-113">このパターンの例は、」の Aggregate.odx を参照してください。[アグリゲーター (BizTalk Server サンプル)](../core/aggregator-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="2f37b-113">For an example of this pattern, see Aggregate.odx in [Aggregator (BizTalk Server Sample)](../core/aggregator-biztalk-server-sample.md).</span></span> <span data-ttu-id="2f37b-114">別の例は」の CMP.odx[で構成されるメッセージ プロセッサ (BizTalk Server サンプル)](../core/composed-message-processor-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="2f37b-114">Another example is CMP.odx in [Composed Message Processor (BizTalk Server Sample)](../core/composed-message-processor-biztalk-server-sample.md).</span></span> <span data-ttu-id="2f37b-115">関連項目[式を使用してパイプラインを実行する方法](../core/how-to-use-expressions-to-execute-pipelines.md)です。</span><span class="sxs-lookup"><span data-stu-id="2f37b-115">See also [How to Use Expressions to Execute Pipelines](../core/how-to-use-expressions-to-execute-pipelines.md).</span></span>  
  
### <a name="composed-message-processor"></a><span data-ttu-id="2f37b-116">構成済みメッセージ プロセッサ</span><span class="sxs-lookup"><span data-stu-id="2f37b-116">Composed Message Processor</span></span>  
 <span data-ttu-id="2f37b-117">構成済みメッセージ プロセッサは、集計またはバッチ化されたインターチェンジ メッセージの個別の項目を処理するパターンです。</span><span class="sxs-lookup"><span data-stu-id="2f37b-117">Composed Message Processor is the pattern of processing individual items from an aggregated or batched interchange message.</span></span> <span data-ttu-id="2f37b-118">このパターンの例を参照してください」の CMP.odx[で構成されるメッセージ プロセッサ (BizTalk Server サンプル)](../core/composed-message-processor-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="2f37b-118">For an example of this pattern, see CMP.odx in [Composed Message Processor (BizTalk Server Sample)](../core/composed-message-processor-biztalk-server-sample.md).</span></span>  
  
### <a name="content-based-router"></a><span data-ttu-id="2f37b-119">コンテンツ ベースのルーター</span><span class="sxs-lookup"><span data-stu-id="2f37b-119">Content-Based Router</span></span>  
 <span data-ttu-id="2f37b-120">コンテンツ ベースのルーターは、メッセージのコンテンツの一部に基づいてメッセージの受信者を決定するパターンです。</span><span class="sxs-lookup"><span data-stu-id="2f37b-120">Content-Based Router is the pattern of determining the recipient of a message based on some part of the message content.</span></span> <span data-ttu-id="2f37b-121">このパターンの例は、次を参照してください。 [CBRSample (BizTalk Server サンプル)](../core/cbrsample-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="2f37b-121">For an example of this pattern, see [CBRSample (BizTalk Server Sample)](../core/cbrsample-biztalk-server-sample.md).</span></span>  
  
### <a name="dynamic-router"></a><span data-ttu-id="2f37b-122">動的ルーター</span><span class="sxs-lookup"><span data-stu-id="2f37b-122">Dynamic Router</span></span>  
 <span data-ttu-id="2f37b-123">動的ルーターは、メッセージ処理の結果に基づいて送信先アドレスとトランスポート プロトコルを決定するパターンです。</span><span class="sxs-lookup"><span data-stu-id="2f37b-123">Dynamic Router is the pattern of determining the destination address as well as the transport protocol based on the result of message processing.</span></span> <span data-ttu-id="2f37b-124">動的送信ポートを使用する、または**ロール リンク**図形をこのパターンを実装します。</span><span class="sxs-lookup"><span data-stu-id="2f37b-124">You can use a dynamic send port or a **Role Link** shape to implement this pattern.</span></span> <span data-ttu-id="2f37b-125">このパターンの例は、」の ReceiveSend.odx を参照してください。 [SendMail](../core/sendmail.md)です。</span><span class="sxs-lookup"><span data-stu-id="2f37b-125">For an example of this pattern, see ReceiveSend.odx in [SendMail](../core/sendmail.md).</span></span> <span data-ttu-id="2f37b-126">別の例は、SupplierProcess.odx に[PartyResolution (BizTalk Server サンプル)](../core/partyresolution-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="2f37b-126">Another example is SupplierProcess.odx in [PartyResolution (BizTalk Server Sample)](../core/partyresolution-biztalk-server-sample.md).</span></span>  
  
### <a name="error-handling"></a><span data-ttu-id="2f37b-127">エラー処理</span><span class="sxs-lookup"><span data-stu-id="2f37b-127">Error Handling</span></span>  
 <span data-ttu-id="2f37b-128">BizTalk Server を使用すると、失敗したメッセージを保留キューに配置する既定の処理の代わりに、失敗したメッセージの自動処理を指定できます。</span><span class="sxs-lookup"><span data-stu-id="2f37b-128">BizTalk Server allows you to designate automated handling of messaging failures as an alternative to the default behavior of placing failed messages in the Suspended queue.</span></span> <span data-ttu-id="2f37b-129">報告用または処理用のサブスクライブの対象となるポートに失敗したメッセージをルーティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="2f37b-129">You can route failed messages to a subscribing port for reporting or processing.</span></span> <span data-ttu-id="2f37b-130">このパターンの例は、」の ResubmitLogic.odx を参照してください。[エラー処理 (BizTalk Server Samples フォルダ)](../core/error-handling-biztalk-server-samples-folder.md)です。</span><span class="sxs-lookup"><span data-stu-id="2f37b-130">For an example of this pattern, see ResubmitLogic.odx in [Error Handling (BizTalk Server Samples Folder)](../core/error-handling-biztalk-server-samples-folder.md).</span></span>  
  
### <a name="exception-handling-and-compensation"></a><span data-ttu-id="2f37b-131">例外処理と補正</span><span class="sxs-lookup"><span data-stu-id="2f37b-131">Exception Handling and Compensation</span></span>  
 <span data-ttu-id="2f37b-132">例外ハンドラーを使用して、**例外のスロー**図形または**式**例外処理の図形。</span><span class="sxs-lookup"><span data-stu-id="2f37b-132">You can use an exception handler and a **Throw Exception** shape or an **Expression** shape for exception handling.</span></span> <span data-ttu-id="2f37b-133">たとえばで次のコードを配置することができます、**式**例外をスローする図形:</span><span class="sxs-lookup"><span data-stu-id="2f37b-133">For example, you can place the following code in the **Expression** shape to throw the exception:,</span></span>  
  
```  
excp = new System.Exception();  
throw(excp);  
```  
  
 <span data-ttu-id="2f37b-134">補正ブロックを使用することができます、**補正**図形をトランザクションがコミットされましたが、補正を実行します。</span><span class="sxs-lookup"><span data-stu-id="2f37b-134">You can use a compensation block and a **Compensate** shape to perform the compensation on the transactions that have been committed.</span></span> <span data-ttu-id="2f37b-135">このパターンの例は、」の UpdateContact.odx を参照してください。[補正 (BizTalk Server サンプル)](../core/compensation-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="2f37b-135">For an example of this pattern, see UpdateContact.odx in [Compensation (BizTalk Server Sample)](../core/compensation-biztalk-server-sample.md).</span></span> <span data-ttu-id="2f37b-136">別の例では、[カスタム例外](../core/custom-exceptions.md)です。</span><span class="sxs-lookup"><span data-stu-id="2f37b-136">Another example is in [Custom Exceptions](../core/custom-exceptions.md).</span></span>  
  
### <a name="message-broker"></a><span data-ttu-id="2f37b-137">メッセージ ブローカー</span><span class="sxs-lookup"><span data-stu-id="2f37b-137">Message Broker</span></span>  
 <span data-ttu-id="2f37b-138">メッセージ ブローカーは、メッセージ フローの制御を維持しながらメッセージの宛先を決定するパターンです。</span><span class="sxs-lookup"><span data-stu-id="2f37b-138">Message Broker is the pattern of determining the destination of a message and still maintaining control over the message flow.</span></span> <span data-ttu-id="2f37b-139">詳細については、次を参照してください。 [OrderBroker オーケストレーションで処理](../core/processing-in-the-orderbroker-orchestration.md)です。</span><span class="sxs-lookup"><span data-stu-id="2f37b-139">For more, see  [Processing in the OrderBroker Orchestration](../core/processing-in-the-orderbroker-orchestration.md).</span></span>  
  
### <a name="message-filter"></a><span data-ttu-id="2f37b-140">メッセージ フィルター</span><span class="sxs-lookup"><span data-stu-id="2f37b-140">Message Filter</span></span>  
 <span data-ttu-id="2f37b-141">メッセージ フィルターは、処理の特定の基準を満たすメッセージを選択するパターンです。</span><span class="sxs-lookup"><span data-stu-id="2f37b-141">The Message Filter pattern selects messages meeting particular criteria for processing.</span></span> <span data-ttu-id="2f37b-142">このパターンを実装するには、アクティブなにフィルター式を追加して**受信**図形です。</span><span class="sxs-lookup"><span data-stu-id="2f37b-142">You can implement this pattern by adding the filter expression to an activated **Receive** shape.</span></span> <span data-ttu-id="2f37b-143">詳細については、次を参照してください。[を使用してフィルターと、受信メッセージ図形](../core/using-filters-with-the-receive-message-shape.md)です。</span><span class="sxs-lookup"><span data-stu-id="2f37b-143">For more information, see [Using Filters With the Receive Message Shape](../core/using-filters-with-the-receive-message-shape.md).</span></span>  
  
### <a name="message-translator"></a><span data-ttu-id="2f37b-144">メッセージ トランスレーター</span><span class="sxs-lookup"><span data-stu-id="2f37b-144">Message Translator</span></span>  
 <span data-ttu-id="2f37b-145">メッセージ トランスレーターは、メッセージの形式を別の形式に変換するパターンです。</span><span class="sxs-lookup"><span data-stu-id="2f37b-145">The Message Translator pattern converts a message from one form to another form.</span></span> <span data-ttu-id="2f37b-146">BizTalk マップを使用して、このパターンを実装することができます、**変換**オーケストレーションの図形です。</span><span class="sxs-lookup"><span data-stu-id="2f37b-146">You can implement this pattern by using a BizTalk map with a **Transform** shape in an orchestration.</span></span> <span data-ttu-id="2f37b-147">このパターンの例は、」の HelloOrchestration.odx を参照してください。 [HelloWorld (BizTalk Server サンプル)](../core/helloworld-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="2f37b-147">For an example of this pattern, see HelloOrchestration.odx in [HelloWorld (BizTalk Server Sample)](../core/helloworld-biztalk-server-sample.md).</span></span>  
  
### <a name="parallel-convoy"></a><span data-ttu-id="2f37b-148">パラレルなコンボイ</span><span class="sxs-lookup"><span data-stu-id="2f37b-148">Parallel Convoy</span></span>  
 <span data-ttu-id="2f37b-149">パラレルなコンボイは、複数の単一項目を結合し、個々の項目が単独では実現できない処理を可能にするパターンです。</span><span class="sxs-lookup"><span data-stu-id="2f37b-149">The Parallel Convoy pattern enables multiple single items to join together to achieve something that an individual item cannot accomplish by itself.</span></span> <span data-ttu-id="2f37b-150">関連する一連の項目は任意の順序で受信されることがありますが、BizTalk Server は、プロセスの開始前にそのメッセージのすべてを受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f37b-150">The set of related items can arrive in any order, but BizTalk Server must receive all of them before starting the process.</span></span> <span data-ttu-id="2f37b-151">このパターンの例は、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=56035](http://go.microsoft.com/fwlink/?LinkId=56035)です。</span><span class="sxs-lookup"><span data-stu-id="2f37b-151">For an example of this pattern, see [http://go.microsoft.com/fwlink/?LinkId=56035](http://go.microsoft.com/fwlink/?LinkId=56035).</span></span>  
  
### <a name="scatter-and-gather"></a><span data-ttu-id="2f37b-152">スキャッター/ギャザー</span><span class="sxs-lookup"><span data-stu-id="2f37b-152">Scatter and Gather</span></span>  
 <span data-ttu-id="2f37b-153">スキャッター/ギャザーは、複数の受信者にメッセージを送信し、各受信者から返されるメッセージを受信できるようにするパターンです。</span><span class="sxs-lookup"><span data-stu-id="2f37b-153">The Scatter and Gather pattern enables messages to be sent to multiple recipients and messages to be received back from each recipient.</span></span> <span data-ttu-id="2f37b-154">このパターンは、分割パターンおよびアグリゲーター パターンを使用して実装できます。</span><span class="sxs-lookup"><span data-stu-id="2f37b-154">You can implement this pattern by using the Splitter pattern and the Aggregator pattern.</span></span> <span data-ttu-id="2f37b-155">アグリゲーター パターンを使用して、分割パターンを使用してから、結果をアセンブルし、下に配置する**並列アクション**図形です。</span><span class="sxs-lookup"><span data-stu-id="2f37b-155">You use the Aggregator pattern to assemble the results from using the Splitter pattern and put them under a **Parallel Actions** shape.</span></span> <span data-ttu-id="2f37b-156">分割パターンの例は、SDK サンプル Implementing Scatter and Gather Pattern を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=65185](http://go.microsoft.com/fwlink/?LinkId=65185)です。</span><span class="sxs-lookup"><span data-stu-id="2f37b-156">For an example of the Splitter pattern, see SDK sample named Implementing Scatter and Gather Pattern at [http://go.microsoft.com/fwlink/?LinkId=65185](http://go.microsoft.com/fwlink/?LinkId=65185).</span></span>  
  
### <a name="sequential-convoy"></a><span data-ttu-id="2f37b-157">シーケンシャルなコンボイ</span><span class="sxs-lookup"><span data-stu-id="2f37b-157">Sequential Convoy</span></span>  
 <span data-ttu-id="2f37b-158">シーケンシャルなコンボイは、複数の単一項目を結合し、個々の項目が単独では実現できない処理を可能にするパターンです。</span><span class="sxs-lookup"><span data-stu-id="2f37b-158">The Sequential Convoy pattern enables multiple single items to join together to achieve something that an individual item cannot accomplish by itself.</span></span> <span data-ttu-id="2f37b-159">シーケンシャルなコンボイは、事前定義された順序を持つ一連の関連する項目です。</span><span class="sxs-lookup"><span data-stu-id="2f37b-159">A sequential convoy is a set of related items that have a predefined order.</span></span> <span data-ttu-id="2f37b-160">項目は完全に同一である必要はありませんが、BizTalk Server は各項目を順番に受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f37b-160">Although the items do not have to be exactly the same, BizTalk Server must receive the items in a sequential order.</span></span> <span data-ttu-id="2f37b-161">このパターンの例は、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=56035](http://go.microsoft.com/fwlink/?LinkId=56035)です。</span><span class="sxs-lookup"><span data-stu-id="2f37b-161">For an example of this pattern, see [http://go.microsoft.com/fwlink/?LinkId=56035](http://go.microsoft.com/fwlink/?LinkId=56035).</span></span>  
  
### <a name="splitter"></a><span data-ttu-id="2f37b-162">スプリッター</span><span class="sxs-lookup"><span data-stu-id="2f37b-162">Splitter</span></span>  
 <span data-ttu-id="2f37b-163">分割は、1 つのメッセージを複数のメッセージに分割するパターンです。</span><span class="sxs-lookup"><span data-stu-id="2f37b-163">The Splitter pattern takes a single message and splits it into multiple messages.</span></span>  
  
### <a name="suspend-with-retry"></a><span data-ttu-id="2f37b-164">中断後再試行</span><span class="sxs-lookup"><span data-stu-id="2f37b-164">Suspend with Retry</span></span>  
 <span data-ttu-id="2f37b-165">中断後再試行は、オーケストレーションがエラー発生時にメッセージを中断できるようにするパターンです。</span><span class="sxs-lookup"><span data-stu-id="2f37b-165">The Suspend with Retry pattern enables the orchestration to suspend a message when there is an error.</span></span> <span data-ttu-id="2f37b-166">中断はループ内で発生するので、オーケストレーションでは中断してオペレーターの介入を求め、一定の回数だけ操作を再試行します。</span><span class="sxs-lookup"><span data-stu-id="2f37b-166">The suspension occurs within a loop so that the orchestration suspends, asks for intervention, and then retries the operation a fixed number of times.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f37b-167">参照</span><span class="sxs-lookup"><span data-stu-id="2f37b-167">See Also</span></span>  
 [<span data-ttu-id="2f37b-168">オーケストレーション フローのデザイン</span><span class="sxs-lookup"><span data-stu-id="2f37b-168">Designing Orchestration Flow</span></span>](../core/designing-orchestration-flow.md)