---
title: インスタンス化し、送信アダプターの初期化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f10e6507-3351-4173-95f5-48546ca5f5c4
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3808af04a8b2bcf6f866629f254212d5b10b8d2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382077"
---
# <a name="instantiating-and-initializing-a-send-adapter"></a><span data-ttu-id="24a8b-102">送信アダプターのインスタンス化と初期化</span><span class="sxs-lookup"><span data-stu-id="24a8b-102">Instantiating and Initializing a Send Adapter</span></span>
<span data-ttu-id="24a8b-103">既定では、送信アダプターは、最初のメッセージは「レイジー作成します」と呼ばれるプロセスには、配信されるまでインスタンス化されません。</span><span class="sxs-lookup"><span data-stu-id="24a8b-103">By default, send adapters are not instantiated until the first message is delivered to them, a process known as "lazy creation."</span></span> <span data-ttu-id="24a8b-104">既定のレイジー作成の方法は、システム リソースを節約するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="24a8b-104">The default lazy creation approach helps to conserve system resources.</span></span> <span data-ttu-id="24a8b-105">送信アダプターを作成した後がキャッシュされ、BizTalk Server サービスが停止されるまで有効にします。</span><span class="sxs-lookup"><span data-stu-id="24a8b-105">After the send adapter is created, it is cached and lives until the BizTalk Server service is stopped.</span></span>  
  
 <span data-ttu-id="24a8b-106">**InitTransmitterOnServiceStart**のメンバー、**機能**列挙型の既定のレイジー作成を使用するのではなく、サービスの開始、送信アダプターを作成するメッセージング エンジンに指示これが必要な場合。</span><span class="sxs-lookup"><span data-stu-id="24a8b-106">The **InitTransmitterOnServiceStart** member of the **Capabilities** enumeration directs the Messaging Engine to create the send adapter on service startup, rather than using the default lazy creation, if this is desired.</span></span>  
  
 <span data-ttu-id="24a8b-107">メッセージのバッチ処理に関するメッセージの受信を別のモデルは、メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="24a8b-107">Sending a message is a different model than receiving a message with respect to batching of messages.</span></span> <span data-ttu-id="24a8b-108">受信の場合は、アダプターは、メッセージング エンジンから取得したバッチに挿入する受信メッセージが。</span><span class="sxs-lookup"><span data-stu-id="24a8b-108">In the receive case the adapter has incoming messages to insert into a batch obtained from the Messaging Engine.</span></span> <span data-ttu-id="24a8b-109">送信の場合は、メッセージング エンジンは、アダプターからバッチを取得し、送信アダプターにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="24a8b-109">In the send case the Messaging Engine obtains a batch from the adapter and sends messages to the adapter to be transmitted.</span></span> <span data-ttu-id="24a8b-110">両方は、トランスポート プロキシを使用して、メッセージ バッチ オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="24a8b-110">Both use the transport proxy to obtain the message batch objects.</span></span>  
  
## <a name="how-a-send-adapter-is-initialized"></a><span data-ttu-id="24a8b-111">送信アダプターを初期化する方法</span><span class="sxs-lookup"><span data-stu-id="24a8b-111">How a Send Adapter Is Initialized</span></span>  
 <span data-ttu-id="24a8b-112">構成とバインディングを有効にする、トランスポート プロキシには、アダプターが次の構成インターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24a8b-112">To enable configuration and binding to the transport proxy, adapters must implement the following configuration interfaces:</span></span>  
  
- <span data-ttu-id="24a8b-113">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="24a8b-113">**IBTTransport**</span></span>  
  
- <span data-ttu-id="24a8b-114">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="24a8b-114">**IBaseComponent**</span></span>  
  
- <span data-ttu-id="24a8b-115">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="24a8b-115">**IBTTransportControl**</span></span>  
  
- <span data-ttu-id="24a8b-116">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="24a8b-116">**IPersistPropertyBag**</span></span>  
  
  <span data-ttu-id="24a8b-117">次の手順では、送信アダプターの初期化に関連するイベントのシーケンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="24a8b-117">The following steps describe the sequence of events involved in initializing a send adapter:</span></span>  
  
1. <span data-ttu-id="24a8b-118">まず実行、メッセージング エンジンでは、送信アダプターの初期化、 **QueryInterface**の**IPersistPropertyBag**、これは省略可能なインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="24a8b-118">When the Messaging Engine initializes a send adapter, it first performs a **QueryInterface** for **IPersistPropertyBag**, which is an optional interface.</span></span> <span data-ttu-id="24a8b-119">ハンドラーの構成がアダプターに渡されるアダプターは、インターフェイスを実装する場合、**ロード**メソッドの呼び出し。</span><span class="sxs-lookup"><span data-stu-id="24a8b-119">If the adapter implements the interface, the handler configuration is passed to the adapter in the **Load** method call.</span></span> <span data-ttu-id="24a8b-120">アダプターでは、この情報を使用して、それが正しく構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="24a8b-120">The adapter uses this information to ensure it is configured correctly.</span></span>  
  
2. <span data-ttu-id="24a8b-121">メッセージング エンジンの実行、 **QueryInterface**の**IBTTransportControl**、必須インターフェイスであります。</span><span class="sxs-lookup"><span data-stu-id="24a8b-121">The Messaging Engine performs a **QueryInterface** for **IBTTransportControl**, which is a mandatory interface.</span></span>  
  
3. <span data-ttu-id="24a8b-122">エンジンの呼び出し**IBTTransportControl.Initialize**アダプターのトランスポート プロキシに渡します。</span><span class="sxs-lookup"><span data-stu-id="24a8b-122">The engine calls **IBTTransportControl.Initialize**, passing in the transport proxy for the adapter.</span></span>  
  
4. <span data-ttu-id="24a8b-123">メッセージング エンジンの実行、 **QueryInterface**の**IBTTransmitter**します。</span><span class="sxs-lookup"><span data-stu-id="24a8b-123">The Messaging Engine performs a **QueryInterface** for **IBTTransmitter**.</span></span>  
  
    <span data-ttu-id="24a8b-124">メッセージング エンジンにこのインターフェイスが検出された場合、アダプターはバッチ非対応の送信機として扱われます。</span><span class="sxs-lookup"><span data-stu-id="24a8b-124">If the Messaging Engine discovers this interface, the adapter is treated as a batch-unaware transmitter.</span></span>  
  
    <span data-ttu-id="24a8b-125">メッセージング エンジンが実行する場合は、メッセージング エンジンは、このインターフェイスを検出されず、 **QueryInterface**の**IBTBatchTransmitter**、検出するは、アダプターがバッチ対応であることを示します送信元。</span><span class="sxs-lookup"><span data-stu-id="24a8b-125">If the Messaging Engine does not discover this interface, the Messaging Engine performs a **QueryInterface** for **IBTBatchTransmitter**, discovery of which indicates that the adapter is a batch-aware transmitter.</span></span>  
  
    <span data-ttu-id="24a8b-126">これらのインターフェイスのどちらも、メッセージング エンジンが検出された場合、エラー状態となり、初期化に失敗します。</span><span class="sxs-lookup"><span data-stu-id="24a8b-126">If the Messaging Engine discovers neither of these interfaces, an error condition results, causing the initialization to fail.</span></span> <span data-ttu-id="24a8b-127">すべての必須インターフェイスが検出されない場合、初期化が失敗します。</span><span class="sxs-lookup"><span data-stu-id="24a8b-127">The initialization fails if any mandatory interfaces are not discovered.</span></span>  
  
   <span data-ttu-id="24a8b-128">次の図は、この API 呼び出しのシーケンスを示しています。青で示されるインターフェイスは、アダプターによって実装されます。</span><span class="sxs-lookup"><span data-stu-id="24a8b-128">The following diagram illustrates this sequence of API calls; the interfaces in blue are implemented by the adapter.</span></span>  
  
   <span data-ttu-id="24a8b-129">![](../core/media/transmit-adapter-init.gif "Transmit_adapter_init")</span><span class="sxs-lookup"><span data-stu-id="24a8b-129">![](../core/media/transmit-adapter-init.gif "Transmit_adapter_init")</span></span>  
  
   <span data-ttu-id="24a8b-130">アダプターは、それを初期化し、構成すると、すぐにメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="24a8b-130">The adapter can send messages as soon as it is initialized and configured.</span></span>  
  
   <span data-ttu-id="24a8b-131">次の図は、送信アダプターの初期化に関連するオブジェクトの相互作用を示しています。</span><span class="sxs-lookup"><span data-stu-id="24a8b-131">The following figure shows the object interactions involved in initializing a send adapter.</span></span>  
  
   <span data-ttu-id="24a8b-132">![](../core/media/ebiz-sdk-devadapter10.gif "ebiz_sdk_devadapter10")</span><span class="sxs-lookup"><span data-stu-id="24a8b-132">![](../core/media/ebiz-sdk-devadapter10.gif "ebiz_sdk_devadapter10")</span></span>  
   <span data-ttu-id="24a8b-133">送信アダプターの初期化のワークフロー</span><span class="sxs-lookup"><span data-stu-id="24a8b-133">Workflow for initializing a send adapter</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="24a8b-134">アダプターがなど呼び出しにおいてメッセージング エンジンをブロックしないでください**IBTTransportControl.Initialize**と**IPersistPropertyBag.Load**します。</span><span class="sxs-lookup"><span data-stu-id="24a8b-134">Adapters should not block the Messaging Engine in calls such as **IBTTransportControl.Initialize** and **IPersistPropertyBag.Load**.</span></span> <span data-ttu-id="24a8b-135">過度のこれらの呼び出しで処理を実行するサービスの開始時に影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="24a8b-135">Performing excessive processing in these calls affects service startup time.</span></span>