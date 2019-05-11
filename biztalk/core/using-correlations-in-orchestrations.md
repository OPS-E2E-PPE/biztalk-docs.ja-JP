---
title: オーケストレーションでの相関関係の使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, orchestrations
- messages, correlation sets
- correlation sets
- orchestrations, messages
- messages, validating
ms.assetid: d919afa9-bada-406a-bf4b-7b46c831c6d5
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b16c54f4c49a1a81ea412c5b980ba23e60e8290
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401624"
---
# <a name="using-correlations-in-orchestrations"></a><span data-ttu-id="45a14-102">オーケストレーションでの関連付けの使用</span><span class="sxs-lookup"><span data-stu-id="45a14-102">Using Correlations in Orchestrations</span></span>
<span data-ttu-id="45a14-103">関連付けは、受信メッセージをオーケストレーションの適切なインスタンスに一致させるプロセスです。</span><span class="sxs-lookup"><span data-stu-id="45a14-103">Correlation is the process of matching an incoming message with the appropriate instance of an orchestration.</span></span> <span data-ttu-id="45a14-104">たとえば、オーケストレーションからメッセージを送信して応答を受信したり、同じオーケストレーションに応答を返信します。</span><span class="sxs-lookup"><span data-stu-id="45a14-104">For example, orchestration sends out of a message and receives the response or responses back into the same orchestration.</span></span> <span data-ttu-id="45a14-105">以下の 3 つの関連付けメッセージ交換パターンがあります。</span><span class="sxs-lookup"><span data-stu-id="45a14-105">There are three correlated messages exchange patterns:</span></span>  
  
- <span data-ttu-id="45a14-106">従来のハンドシェイク</span><span class="sxs-lookup"><span data-stu-id="45a14-106">Traditional handshake</span></span>  
  
- <span data-ttu-id="45a14-107">シーケンシャルなコンボイ</span><span class="sxs-lookup"><span data-stu-id="45a14-107">Sequential convoy</span></span>  
  
- <span data-ttu-id="45a14-108">パラレルなコンボイ</span><span class="sxs-lookup"><span data-stu-id="45a14-108">Parallel convoy</span></span>  
  
  <span data-ttu-id="45a14-109">従来のハンドシェイク パターンの場合、ハンドシェイクはオーケストレーションまたはビジネス プロセス間でのメッセージの交換の間に存在します。ハンドシェイクを実現するには、オーケストレーションで関連付けセットを定義します。このオーケストレーションでは、関連付けセットが、特定のオーケストレーション インスタンスへメッセージをルーティングするために使用する特定の値の昇格させたプロパティの一覧になります。</span><span class="sxs-lookup"><span data-stu-id="45a14-109">In the traditional handshake pattern, handshakes exist between the exchanges of the messages among the orchestrations or business processes, and you can achieve the handshakes by defining correlation sets in the orchestrations where a correlation set is a list of promoted properties with specific values that you use to route messages to a specific orchestration instance.</span></span>  
  
  <span data-ttu-id="45a14-110">たとえば、オーケストレーションが注文書の発行、請求書の受信、および支払いの送金を目的としている場合は、その時点で多くの注文書が処理される可能性があるため、対応する注文書の送信元と同じオーケストレーションが請求書メッセージを受信するようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="45a14-110">If, for example, your orchestration is designed to issue a purchase order, receive an invoice, and send out the payment, you need to be sure that the invoice message is received by the same orchestration instance that the corresponding purchase order was sent from since numbers of purchase orders may be processed at the time.</span></span> <span data-ttu-id="45a14-111">この例では、注文書の識別番号を関連付けセットでパラメーターとして使用して、注文書メッセージと請求書メッセージを関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="45a14-111">In this example, the purchase order identification number can be used as a parameter in the correlation set for correlating the purchase order message and the invoice message.</span></span> <span data-ttu-id="45a14-112">次のシナリオは、この例のフローを示しています。</span><span class="sxs-lookup"><span data-stu-id="45a14-112">The following is the scenario flow for this example,</span></span>  
  
1. <span data-ttu-id="45a14-113">オーケストレーション A は、注文書メッセージをオーケストレーション B に送信します。注文書メッセージを送信する前に、関連付けセットが初期化されます。</span><span class="sxs-lookup"><span data-stu-id="45a14-113">The Orchestration A sends out the purchase order message to the Orchestration B. Before sending out the purchase order message, the correlation set is initialized.</span></span>  
  
2. <span data-ttu-id="45a14-114">注文書を処理し、請求書を生成して返信するオーケストレーション B では、最初の受信図形が同じ関連付けセットに従って注文書メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="45a14-114">In the Orchestration B, in which processes the purchase order, generates and sends back the invoice, the first Receive shape follows the same correlation set to receive the purchase order message.</span></span>  
  
3. <span data-ttu-id="45a14-115">注文書メッセージの処理後に、請求書メッセージをオーケストレーション A に返信するときにも、同じ関連付けセットに従います。</span><span class="sxs-lookup"><span data-stu-id="45a14-115">After processing the purchase order message, when sending back the invoice message to the Orchestration A, the same correlation set is also followed.</span></span>  
  
4. <span data-ttu-id="45a14-116">オーケストレーション A で、オーケストレーション B から返信された請求書メッセージを受信する受信図形でも同じ関連付けセットに従って、関連付けられた請求書メッセージを定義済みの関連付けセットに基づいて受け取れるようにします。</span><span class="sxs-lookup"><span data-stu-id="45a14-116">In the Orchestration A, at the Receive shape which receives the invoice message back from the orchestration B, the same correlation set is also followed to ensure that receiving the correlated invoice message based on the predefined correlation set.</span></span>  
  
   <span data-ttu-id="45a14-117">シーケンシャルなコンボイ パターンとパラレル コンボイ パターンは、個々の項目が単独では実現できない処理を可能にするために複数の単一項目を関連付ける必要がある状況に存在します。</span><span class="sxs-lookup"><span data-stu-id="45a14-117">The sequential convoy and parallel convoy patterns exist in the world any time multiple single items must be related together in order to achieve something that the individual item cannot accomplish by itself.</span></span> <span data-ttu-id="45a14-118">詳細については、次を参照してください。[コンボイ シナリオの](../core/working-with-convoy-scenarios.md)します。</span><span class="sxs-lookup"><span data-stu-id="45a14-118">For more information, see [Working with Convoy Scenarios](../core/working-with-convoy-scenarios.md).</span></span>  
  
   <span data-ttu-id="45a14-119">関連付けられたメッセージ交換パターンに加えて、オーケストレーションには、次の 2 種類の関連付けが存在します。</span><span class="sxs-lookup"><span data-stu-id="45a14-119">In addition to the correlated message exchange patterns, there are two types of correlations in orchestration:</span></span>  
  
- <span data-ttu-id="45a14-120">手動の関連付け</span><span class="sxs-lookup"><span data-stu-id="45a14-120">Manual correlation</span></span>  
  
- <span data-ttu-id="45a14-121">自動の関連付け</span><span class="sxs-lookup"><span data-stu-id="45a14-121">Automatic correlation</span></span>  
  
  <span data-ttu-id="45a14-122">手動の関連付けシナリオでは、オーケストレーションを手動で構成して関連付けセットを初期化し、その関連付けセットに従ってメッセージを適切なインスタンスに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="45a14-122">In the manual correlation scenario, you manually configure the orchestrations to initialize and follow the correlation set to associate the messages with proper instances.</span></span> <span data-ttu-id="45a14-123">自動の関連付けシナリオでは、オーケストレーションで要求 - 応答ポートや自己関連付けを行うポートを設定する場合などに、メッセージング エンジンがメッセージをインスタンスに自動的に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="45a14-123">In the automatic correlation scenario, the messaging engine will correlate the messages with the instances for you, for example, when you set up Request-Response port or Self-Correlating port in your orchestrations.</span></span>  
  
  <span data-ttu-id="45a14-124">アクティブ化受信ポート、要求 - 応答ポート、自己関連付けを行うポートなど、オーケストレーションにメッセージをインスタンスに関連付ける明示的な方法がない場合は常に関連付けを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45a14-124">You must use correlation whenever your orchestration does not have an explicit way of associating a message with an instance, such as an activate receive, a request-response, or a self-correlating port.</span></span>  
  
## <a name="examples-of-using-correlations"></a><span data-ttu-id="45a14-125">関連付けの使用例</span><span class="sxs-lookup"><span data-stu-id="45a14-125">Examples of Using Correlations</span></span>  
  
-   [<span data-ttu-id="45a14-126">PartyResolution (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="45a14-126">PartyResolution (BizTalk Server Sample)</span></span>](../core/partyresolution-biztalk-server-sample.md)  
  
-   <span data-ttu-id="45a14-127">「関連付けメッセージとオーケストレーション インスタンスの」SDK サンプルからダウンロード[ http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)します。</span><span class="sxs-lookup"><span data-stu-id="45a14-127">Download the SDK sample "Correlating Messages with Orchestration Instances" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="45a14-128">SDK サンプル「パラレルなコンボイ」のダウンロード[ http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)します。</span><span class="sxs-lookup"><span data-stu-id="45a14-128">Download the SDK sample "Parallel Convoy" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="45a14-129">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="45a14-129">In This Section</span></span>  
  
-   [<span data-ttu-id="45a14-130">関連付けセット</span><span class="sxs-lookup"><span data-stu-id="45a14-130">Correlation Sets</span></span>](../core/correlation-sets.md) 
  
-   [<span data-ttu-id="45a14-131">関連付けの種類</span><span class="sxs-lookup"><span data-stu-id="45a14-131">Correlation Types</span></span>](../core/correlation-types.md) 
  
-   [<span data-ttu-id="45a14-132">追加および関連付けセットを削除する方法</span><span class="sxs-lookup"><span data-stu-id="45a14-132">How to Add and Remove Correlation Sets</span></span>](../core/how-to-add-and-remove-correlation-sets.md) 
  
-   [<span data-ttu-id="45a14-133">関連付けセットを構成する方法</span><span class="sxs-lookup"><span data-stu-id="45a14-133">How to Configure Correlation Sets</span></span>](../core/how-to-configure-correlation-sets.md)  
  
-   [<span data-ttu-id="45a14-134">関連付けの種類を構成する方法</span><span class="sxs-lookup"><span data-stu-id="45a14-134">How to Configure Correlation Types</span></span>](../core/how-to-configure-correlation-types.md)  
  
-   [<span data-ttu-id="45a14-135">コンボイ シナリオの活用</span><span class="sxs-lookup"><span data-stu-id="45a14-135">Working with Convoy Scenarios</span></span>](../core/working-with-convoy-scenarios.md)  
  
## <a name="see-also"></a><span data-ttu-id="45a14-136">参照</span><span class="sxs-lookup"><span data-stu-id="45a14-136">See Also</span></span>  
 [<span data-ttu-id="45a14-137">自己関連付けを行う Direct を使用する方法のポートのバインド</span><span class="sxs-lookup"><span data-stu-id="45a14-137">How to Use Self-Correlating Direct Bound Ports</span></span>](../core/how-to-use-self-correlating-direct-bound-ports.md)