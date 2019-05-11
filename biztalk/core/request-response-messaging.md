---
title: 要求-応答メッセージング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38652fdb7b1b5484c4c01510416489c4437b629e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398887"
---
# <a name="request-response-messaging"></a><span data-ttu-id="32d24-102">要求-応答メッセージング</span><span class="sxs-lookup"><span data-stu-id="32d24-102">Request-Response Messaging</span></span>
<span data-ttu-id="32d24-103">要求/応答メッセージング パターンでは、1 つのパーティは、要求メッセージを送信および受信側パーティは、応答メッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="32d24-103">In a request/response messaging pattern, one party sends a request message and the receiving party returns a response message.</span></span> <span data-ttu-id="32d24-104">要求/応答の処理の 2 つの一般的な例は、HTTP アダプター、および簡易オブジェクト アクセス プロトコル (SOAP) アダプターを使用して Web サービスの処理を使用して Web サーバーとブラウザーのある操作です。</span><span class="sxs-lookup"><span data-stu-id="32d24-104">Two typical examples of request/response processing are the interaction that a browser has with a Web server using the HTTP adapter, and Web service processing using the Simple Object Access Protocol (SOAP) adapter.</span></span> <span data-ttu-id="32d24-105">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]要求と応答メッセージの両方が、標準的なパブリッシュ/サブスクライブ形式で処理されます。</span><span class="sxs-lookup"><span data-stu-id="32d24-105">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], both the request and the response messages are handled in a typical publish/subscribe fashion.</span></span> <span data-ttu-id="32d24-106">これは、個々 のメッセージを低待機時間を必要とする 1 つとは異なる高スループットを必要とするシステムを構成する場合がありますとパフォーマンス調整を行う、BizTalk アプリケーションを理解する重要な考慮事項です。</span><span class="sxs-lookup"><span data-stu-id="32d24-106">This is an important consideration to understand when you performance-tune a BizTalk application, because a system requiring high throughput might be configured differently than one requiring low latency for individual messages.</span></span>  
  
 <span data-ttu-id="32d24-107">![要求&#47;応答メッセージング](../core/media/arch-request-response-1.gif "arch_request-応答-1")</span><span class="sxs-lookup"><span data-stu-id="32d24-107">![Request&#47;Response messaging](../core/media/arch-request-response-1.gif "arch_request-response-1")</span></span>  
  
 <span data-ttu-id="32d24-108">メッセージが受信したときに要求/応答スタイルでは、受信アダプター、BizTalk Server がメッセージ ボックス データベースに最初に要求メッセージを発行します。</span><span class="sxs-lookup"><span data-stu-id="32d24-108">When a message is received by a request/response style receive adapter, BizTalk Server first publishes the request message to the MessageBox database.</span></span> <span data-ttu-id="32d24-109">次にこのメッセージは、受信ポートにバインドされたオーケストレーションの可能性が、適切なサブスクライバーによって受信されます。</span><span class="sxs-lookup"><span data-stu-id="32d24-109">Next this message is received by the appropriate subscriber, which is likely an orchestration bound to a receive port.</span></span> <span data-ttu-id="32d24-110">このサブスクライバーは、応答メッセージを作成し、要求が元の受信ポートに送信するようにするプロパティと一緒にメッセージ ボックス データベースに公開します。</span><span class="sxs-lookup"><span data-stu-id="32d24-110">This subscriber formulates a response message and publishes it to the MessageBox, along with properties that cause it to be sent back to the receive port from which the request came.</span></span> <span data-ttu-id="32d24-111">最後に、応答メッセージは要求を送信し、呼び出し元アプリケーションに返される受信アダプターは、要求の発行元によってピックアップられます。</span><span class="sxs-lookup"><span data-stu-id="32d24-111">Finally, the response message is picked up by the publisher of the request, the receive adapter that submitted the request, and is returned to the calling application.</span></span> <span data-ttu-id="32d24-112">次の図は、次の手順の詳細なグラフィック表示を提供します。</span><span class="sxs-lookup"><span data-stu-id="32d24-112">The diagram below provides a detailed graphical representation of these steps.</span></span>  
  
 <span data-ttu-id="32d24-113">![要求&#47;SOAP アダプターで受信した応答メッセージ](../core/media/arch-request-response-2.gif "arch_request-応答-2")</span><span class="sxs-lookup"><span data-stu-id="32d24-113">![Request&#47;response message received by SOAP adapter](../core/media/arch-request-response-2.gif "arch_request-response-2")</span></span>  
  
 <span data-ttu-id="32d24-114">**SOAP アダプターで受信した要求/応答メッセージのフロー**</span><span class="sxs-lookup"><span data-stu-id="32d24-114">**Flow of request/response message received by SOAP adapter**</span></span>  
  
1. <span data-ttu-id="32d24-115">SOAP アダプターでは、エンドポイント マネージャーにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="32d24-115">The SOAP adapter submits messages to the Endpoint Manager.</span></span>  
  
2. <span data-ttu-id="32d24-116">エンドポイント マネージャーは、メッセージ ボックスに、メッセージを公開します。</span><span class="sxs-lookup"><span data-stu-id="32d24-116">The Endpoint Manager publishes the message into the MessageBox.</span></span>  
  
3. <span data-ttu-id="32d24-117">これは、受信ポートにバインドされ、メッセージのサブスクリプション、オーケストレーションはメッセージを受信し、処理します。</span><span class="sxs-lookup"><span data-stu-id="32d24-117">The orchestration, which is bound to the receive port and therefore has a subscription for the message, receives the message and processes it.</span></span>  
  
4. <span data-ttu-id="32d24-118">オーケストレーションでは、メッセージ ボックスに公開されている応答メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="32d24-118">The orchestration sends a response message that is published to the MessageBox.</span></span>  
  
5. <span data-ttu-id="32d24-119">エンドポイント マネージャーは、応答メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="32d24-119">The Endpoint Manager receives the response message.</span></span>  
  
6. <span data-ttu-id="32d24-120">エンドポイント マネージャーには、SOAP アダプターに応答が返されます。</span><span class="sxs-lookup"><span data-stu-id="32d24-120">The Endpoint Manager returns the response to the SOAP adapter</span></span>  
  
   <span data-ttu-id="32d24-121">内部の実装が認識されない場合は、この種類のパフォーマンスの動作の影響を見落とす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="32d24-121">The implications of this type of behavior on performance can be overlooked if the internal implementation is not understood.</span></span> <span data-ttu-id="32d24-122">BizTalk Server は最初に、高スループットのシナリオに合わせて調整しますが、低いスループットで環境と短い待機時間、特に要求/応答シナリオでの必要性を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="32d24-122">BizTalk Server is initially tuned for high throughput scenarios, but it can also be configured for an environment with lower throughput and a need for lower latency, especially in request/response scenarios.</span></span> <span data-ttu-id="32d24-123">このシナリオでチューニングするためのいくつかのコンポーネントを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32d24-123">You need to consider several components for tuning in this scenario.</span></span> <span data-ttu-id="32d24-124">最初に、サブスクライバーについて公開されたメッセージ、ポーリング メカニズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="32d24-124">First, subscribers find out about published messages through a polling mechanism.</span></span> <span data-ttu-id="32d24-125">ポーリング間隔の設定が高すぎる場合する可能性が要求/応答形式の対話処理を待機するよりも時間があります。</span><span class="sxs-lookup"><span data-stu-id="32d24-125">If the polling interval is set too high, this could cause request/response style interactions to have a higher latency than you would want.</span></span>  
  
   <span data-ttu-id="32d24-126">このシナリオであることを格納する 2 つのサブスクリプションに注意してください。 最初のメッセージのサブスクリプションと、1 つの応答メッセージ、およびこれにはこのポーリング間隔の影響が大きくなります。</span><span class="sxs-lookup"><span data-stu-id="32d24-126">Note that in this scenario, there are two subscriptions to be filled: the subscription for the initial message, as well as the one for the response message, and this increases the impact of this polling interval.</span></span> <span data-ttu-id="32d24-127">次に、受信アダプターがさまざまなサイズのバッチでメッセージ ボックス データベースにメッセージを挿入するように構成されます。</span><span class="sxs-lookup"><span data-stu-id="32d24-127">Second, receive adapters are configured to insert messages into the MessageBox in batches of varying sizes.</span></span> <span data-ttu-id="32d24-128">ほとんどのアダプターには、BizTalk Server またはレジストリで、一般的なアダプター構成インターフェイス、またはパラメーターを通じてバッチ サイズを構成することが有効にします。</span><span class="sxs-lookup"><span data-stu-id="32d24-128">Most adapters enable you to configure the batch size through the typical adapter configuration interface or through parameters in BizTalk Server or the registry.</span></span> <span data-ttu-id="32d24-129">バッチ サイズの設定が高すぎると、個々 のメッセージ待機時間を増やすことができます。</span><span class="sxs-lookup"><span data-stu-id="32d24-129">If the batch size is set too high, the latency for individual messages may be increased.</span></span> <span data-ttu-id="32d24-130">パフォーマンス特性の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[パフォーマンス維持の計画](../core/planning-for-sustained-performance.md)します。</span><span class="sxs-lookup"><span data-stu-id="32d24-130">For more information about the performance characteristics of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Planning for Sustained Performance](../core/planning-for-sustained-performance.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32d24-131">参照</span><span class="sxs-lookup"><span data-stu-id="32d24-131">See Also</span></span>  
 [<span data-ttu-id="32d24-132">ランタイム アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="32d24-132">Runtime Architecture</span></span>](../core/runtime-architecture.md)