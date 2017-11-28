---
title: "要求-応答のメッセージング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- request/response messaging, about request/response messaging
- SOAP adapters, message processing
- SOAP adapters, request/response messaging
- request/response messaging
- patterns, messages
- messages, request/response messaging
- request/response messaging, processing
- request/response messaging, SOAP adapters
- messages, patterns
ms.assetid: 1a2f79b5-1f44-4191-8ce1-b3c9043be4f4
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd612d5f41e4648625a2a28398f20ecf74e0a4e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="request-response-messaging"></a><span data-ttu-id="74eff-102">要求-応答のメッセージング</span><span class="sxs-lookup"><span data-stu-id="74eff-102">Request-Response Messaging</span></span>
<span data-ttu-id="74eff-103">要求/応答メッセージ方式では、送信側が要求メッセージを送信し、受信側が応答メッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="74eff-103">In a request/response messaging pattern, one party sends a request message and the receiving party returns a response message.</span></span> <span data-ttu-id="74eff-104">要求/応答処理の一般的な使用例としては、HTTP アダプターを使用した Web サーバーとブラウザー間の対話処理、および、Simple Object Access Protocol (SOAP) アダプターを使用した Web サービス処理の 2 つがあります。</span><span class="sxs-lookup"><span data-stu-id="74eff-104">Two typical examples of request/response processing are the interaction that a browser has with a Web server using the HTTP adapter, and Web service processing using the Simple Object Access Protocol (SOAP) adapter.</span></span> <span data-ttu-id="74eff-105">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の要求/応答メッセージは、通常のパブリッシュ/サブスクライブ形式で処理されます。</span><span class="sxs-lookup"><span data-stu-id="74eff-105">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], both the request and the response messages are handled in a typical publish/subscribe fashion.</span></span> <span data-ttu-id="74eff-106">このことは、BizTalk アプリケーションのパフォーマンス調整を行うときの重要な注意事項です。高いスループットを必要とするシステムは、個々のメッセージの待ち時間を短くする必要のあるシステムとは異なる構成が行われる可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="74eff-106">This is an important consideration to understand when you performance-tune a BizTalk application, because a system requiring high throughput might be configured differently than one requiring low latency for individual messages.</span></span>  
  
 <span data-ttu-id="74eff-107">![要求である (、&) #47 です。応答のメッセージング](../core/media/arch-request-response-1.gif "arch_request-応答-1")</span><span class="sxs-lookup"><span data-stu-id="74eff-107">![Request&#47;Response messaging](../core/media/arch-request-response-1.gif "arch_request-response-1")</span></span>  
  
 <span data-ttu-id="74eff-108">要求/応答形式の受信アダプターでメッセージを受信する場合、BizTalk Server は、最初に要求メッセージをメッセージ ボックス データベースに公開します。</span><span class="sxs-lookup"><span data-stu-id="74eff-108">When a message is received by a request/response style receive adapter, BizTalk Server first publishes the request message to the MessageBox database.</span></span> <span data-ttu-id="74eff-109">次に、適切なサブスクライバー (受信ポートにバインドされているオーケストレーションの可能性が高い) がこのメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="74eff-109">Next this message is received by the appropriate subscriber, which is likely an orchestration bound to a receive port.</span></span> <span data-ttu-id="74eff-110">このサブスクライバーは、応答メッセージを作成し、要求元の受信ポートに応答メッセージを返信するプロパティと一緒にメッセージ ボックス データベースに応答メッセージを公開します。</span><span class="sxs-lookup"><span data-stu-id="74eff-110">This subscriber formulates a response message and publishes it to the MessageBox, along with properties that cause it to be sent back to the receive port from which the request came.</span></span> <span data-ttu-id="74eff-111">最後に、要求元のパブリッシャー (要求を送信した受信アダプター) が応答メッセージを受け取ってから、呼び出し元のアプリケーションに応答メッセージが返されます。</span><span class="sxs-lookup"><span data-stu-id="74eff-111">Finally, the response message is picked up by the publisher of the request, the receive adapter that submitted the request, and is returned to the calling application.</span></span> <span data-ttu-id="74eff-112">次の図は、これらの手順の詳細を示しています。</span><span class="sxs-lookup"><span data-stu-id="74eff-112">The diagram below provides a detailed graphical representation of these steps.</span></span>  
  
 <span data-ttu-id="74eff-113">![要求 (&) #47; SOAP アダプターで受信した応答メッセージ](../core/media/arch-request-response-2.gif "arch_request-応答-2")</span><span class="sxs-lookup"><span data-stu-id="74eff-113">![Request&#47;response message received by SOAP adapter](../core/media/arch-request-response-2.gif "arch_request-response-2")</span></span>  
  
 <span data-ttu-id="74eff-114">**SOAP アダプターで受信した要求/応答メッセージのフロー**</span><span class="sxs-lookup"><span data-stu-id="74eff-114">**Flow of request/response message received by SOAP adapter**</span></span>  
  
1.  <span data-ttu-id="74eff-115">SOAP アダプターは、メッセージをエンドポイント マネージャーに送信します。</span><span class="sxs-lookup"><span data-stu-id="74eff-115">The SOAP adapter submits messages to the Endpoint Manager.</span></span>  
  
2.  <span data-ttu-id="74eff-116">エンドポイント マネージャーは、メッセージをメッセージ ボックス データベースに公開します。</span><span class="sxs-lookup"><span data-stu-id="74eff-116">The Endpoint Manager publishes the message into the MessageBox.</span></span>  
  
3.  <span data-ttu-id="74eff-117">受信ポートにバインドされている (メッセージにサブスクリプションを含む) オーケストレーションは、メッセージを受信して処理します。</span><span class="sxs-lookup"><span data-stu-id="74eff-117">The orchestration, which is bound to the receive port and therefore has a subscription for the message, receives the message and processes it.</span></span>  
  
4.  <span data-ttu-id="74eff-118">オーケストレーションは、メッセージ ボックス データベースに公開されている応答メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="74eff-118">The orchestration sends a response message that is published to the MessageBox.</span></span>  
  
5.  <span data-ttu-id="74eff-119">エンドポイント マネージャーは、応答メッセージを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="74eff-119">The Endpoint Manager receives the response message.</span></span>  
  
6.  <span data-ttu-id="74eff-120">エンドポイント マネージャーは、応答を SOAP アダプターに返します。</span><span class="sxs-lookup"><span data-stu-id="74eff-120">The Endpoint Manager returns the response to the SOAP adapter</span></span>  
  
 <span data-ttu-id="74eff-121">内部の実装を理解していない場合、パフォーマンスに対するこのような動作の影響は見過ごされがちです。</span><span class="sxs-lookup"><span data-stu-id="74eff-121">The implications of this type of behavior on performance can be overlooked if the internal implementation is not understood.</span></span> <span data-ttu-id="74eff-122">BizTalk Server は、当初は、高スループット シナリオ用にチューニングされていますが、低いスループットや少ない待機時間 (特に要求/応答シナリオ) に合わせた環境の構成も行うことができます。</span><span class="sxs-lookup"><span data-stu-id="74eff-122">BizTalk Server is initially tuned for high throughput scenarios, but it can also be configured for an environment with lower throughput and a need for lower latency, especially in request/response scenarios.</span></span> <span data-ttu-id="74eff-123">このシナリオに合わせて、いくつかのコンポーネントを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74eff-123">You need to consider several components for tuning in this scenario.</span></span> <span data-ttu-id="74eff-124">最初に、サブスクライバーは、ポーリング機構を通じて公開されたメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="74eff-124">First, subscribers find out about published messages through a polling mechanism.</span></span> <span data-ttu-id="74eff-125">ポーリング間隔が大きすぎると、要求/応答形式の対話処理の待機時間が長くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="74eff-125">If the polling interval is set too high, this could cause request/response style interactions to have a higher latency than you would want.</span></span>  
  
 <span data-ttu-id="74eff-126">このシナリオでは 2 つのサブスクリプション (最初のメッセージのサブスクリプションと応答メッセージのサブスクリプション) を使用していることに注意してください。これにより、このポーリング間隔の影響が大きくなります。</span><span class="sxs-lookup"><span data-stu-id="74eff-126">Note that in this scenario, there are two subscriptions to be filled: the subscription for the initial message, as well as the one for the response message, and this increases the impact of this polling interval.</span></span> <span data-ttu-id="74eff-127">次に、受信アダプターを構成して、さまざまなサイズのバッチ単位で、メッセージ ボックス データベースにメッセージを挿入します。</span><span class="sxs-lookup"><span data-stu-id="74eff-127">Second, receive adapters are configured to insert messages into the MessageBox in batches of varying sizes.</span></span> <span data-ttu-id="74eff-128">ほとんどのアダプターでは、通常のアダプター構成インターフェイス、BizTalk Server のパラメーター、またはレジストリを使用して、バッチ サイズを構成できます。</span><span class="sxs-lookup"><span data-stu-id="74eff-128">Most adapters enable you to configure the batch size through the typical adapter configuration interface or through parameters in BizTalk Server or the registry.</span></span> <span data-ttu-id="74eff-129">バッチ サイズが大きすぎると、個々のメッセージの待機時間が長くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="74eff-129">If the batch size is set too high, the latency for individual messages may be increased.</span></span> <span data-ttu-id="74eff-130">パフォーマンス特性の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[継続的なパフォーマンスの計画](../core/planning-for-sustained-performance.md)です。</span><span class="sxs-lookup"><span data-stu-id="74eff-130">For more information about the performance characteristics of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Planning for Sustained Performance](../core/planning-for-sustained-performance.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74eff-131">参照</span><span class="sxs-lookup"><span data-stu-id="74eff-131">See Also</span></span>  
 [<span data-ttu-id="74eff-132">ランタイム アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="74eff-132">Runtime Architecture</span></span>](../core/runtime-architecture.md)