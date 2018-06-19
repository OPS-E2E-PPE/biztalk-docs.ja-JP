---
title: インスタンス化して、送信アダプターの初期化 |Microsoft ドキュメント
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
ms.openlocfilehash: 07ed590b73d31a03a4b3316a4d84edfc1e39eb0f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257666"
---
# <a name="instantiating-and-initializing-a-send-adapter"></a><span data-ttu-id="2c5fc-102">送信アダプターのインスタンス化と初期化</span><span class="sxs-lookup"><span data-stu-id="2c5fc-102">Instantiating and Initializing a Send Adapter</span></span>
<span data-ttu-id="2c5fc-103">既定では、送信アダプターは、最初のメッセージが配信されるまでインスタンス化されません。これは "レイジー作成" と呼ばれるプロセスです。</span><span class="sxs-lookup"><span data-stu-id="2c5fc-103">By default, send adapters are not instantiated until the first message is delivered to them, a process known as "lazy creation."</span></span> <span data-ttu-id="2c5fc-104">レイジー作成による既定のアプローチは、システム リソースの節約に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2c5fc-104">The default lazy creation approach helps to conserve system resources.</span></span> <span data-ttu-id="2c5fc-105">作成された送信アダプターはキャッシュされ、BizTalk Server サービスが停止されるまで有効になります。</span><span class="sxs-lookup"><span data-stu-id="2c5fc-105">After the send adapter is created, it is cached and lives until the BizTalk Server service is stopped.</span></span>  
  
 <span data-ttu-id="2c5fc-106">**InitTransmitterOnServiceStart**のメンバー、**機能**列挙型を既定のレイジー作成を使用するのではなく、サービスの開始に送信アダプターを作成するメッセージング エンジンに指示これが必要な場合です。</span><span class="sxs-lookup"><span data-stu-id="2c5fc-106">The **InitTransmitterOnServiceStart** member of the **Capabilities** enumeration directs the Messaging Engine to create the send adapter on service startup, rather than using the default lazy creation, if this is desired.</span></span>  
  
 <span data-ttu-id="2c5fc-107">メッセージの送信は、メッセージのバッチ処理の点でメッセージの受信とは異なるモデルです。</span><span class="sxs-lookup"><span data-stu-id="2c5fc-107">Sending a message is a different model than receiving a message with respect to batching of messages.</span></span> <span data-ttu-id="2c5fc-108">受信の場合、アダプターには、メッセージング エンジンから取得したバッチに挿入する受信メッセージがあります。</span><span class="sxs-lookup"><span data-stu-id="2c5fc-108">In the receive case the adapter has incoming messages to insert into a batch obtained from the Messaging Engine.</span></span> <span data-ttu-id="2c5fc-109">送信の場合は、メッセージング エンジンがアダプターからバッチを取得し、送信先のアダプターにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="2c5fc-109">In the send case the Messaging Engine obtains a batch from the adapter and sends messages to the adapter to be transmitted.</span></span> <span data-ttu-id="2c5fc-110">どちらの場合も、トランスポート プロキシを使用してメッセージ バッチ オブジェクトが取得されます。</span><span class="sxs-lookup"><span data-stu-id="2c5fc-110">Both use the transport proxy to obtain the message batch objects.</span></span>  
  
## <a name="how-a-send-adapter-is-initialized"></a><span data-ttu-id="2c5fc-111">送信アダプターの初期化</span><span class="sxs-lookup"><span data-stu-id="2c5fc-111">How a Send Adapter Is Initialized</span></span>  
 <span data-ttu-id="2c5fc-112">構成およびトランスポート プロキシへのバインドを有効にするには、アダプターに次の構成インターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c5fc-112">To enable configuration and binding to the transport proxy, adapters must implement the following configuration interfaces:</span></span>  
  
-   <span data-ttu-id="2c5fc-113">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="2c5fc-113">**IBTTransport**</span></span>  
  
-   <span data-ttu-id="2c5fc-114">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="2c5fc-114">**IBaseComponent**</span></span>  
  
-   <span data-ttu-id="2c5fc-115">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="2c5fc-115">**IBTTransportControl**</span></span>  
  
-   <span data-ttu-id="2c5fc-116">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="2c5fc-116">**IPersistPropertyBag**</span></span>  
  
 <span data-ttu-id="2c5fc-117">送信アダプターの初期化に関連する一連のイベントを次に示します。</span><span class="sxs-lookup"><span data-stu-id="2c5fc-117">The following steps describe the sequence of events involved in initializing a send adapter:</span></span>  
  
1.  <span data-ttu-id="2c5fc-118">まず実行、メッセージング エンジンには、送信アダプターが初期化されるときに、 **QueryInterface**の**IPersistPropertyBag**、これは省略可能なインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="2c5fc-118">When the Messaging Engine initializes a send adapter, it first performs a **QueryInterface** for **IPersistPropertyBag**, which is an optional interface.</span></span> <span data-ttu-id="2c5fc-119">ハンドラーの構成がアダプターに渡されるアダプターは、インターフェイスを実装する場合、**ロード**メソッドの呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="2c5fc-119">If the adapter implements the interface, the handler configuration is passed to the adapter in the **Load** method call.</span></span> <span data-ttu-id="2c5fc-120">アダプターは、この情報を使用して適切に構成されます。</span><span class="sxs-lookup"><span data-stu-id="2c5fc-120">The adapter uses this information to ensure it is configured correctly.</span></span>  
  
2.  <span data-ttu-id="2c5fc-121">メッセージング エンジンを実行、 **QueryInterface**の**IBTTransportControl**、これは必須のインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="2c5fc-121">The Messaging Engine performs a **QueryInterface** for **IBTTransportControl**, which is a mandatory interface.</span></span>  
  
3.  <span data-ttu-id="2c5fc-122">エンジン呼び出し**IBTTransportControl.Initialize**アダプターのトランスポート プロキシに渡します。</span><span class="sxs-lookup"><span data-stu-id="2c5fc-122">The engine calls **IBTTransportControl.Initialize**, passing in the transport proxy for the adapter.</span></span>  
  
4.  <span data-ttu-id="2c5fc-123">メッセージング エンジンの実行、 **QueryInterface**の**IBTTransmitter**です。</span><span class="sxs-lookup"><span data-stu-id="2c5fc-123">The Messaging Engine performs a **QueryInterface** for **IBTTransmitter**.</span></span>  
  
     <span data-ttu-id="2c5fc-124">このインターフェイスが検出された場合、アダプターはバッチ非対応の送信元として扱われます。</span><span class="sxs-lookup"><span data-stu-id="2c5fc-124">If the Messaging Engine discovers this interface, the adapter is treated as a batch-unaware transmitter.</span></span>  
  
     <span data-ttu-id="2c5fc-125">メッセージング エンジンを実行している場合は、メッセージング エンジンでは、このインターフェイスは検出しません、 **QueryInterface**の**IBTBatchTransmitter**、検出うちは、アダプターがバッチ対応であることを示します送信機能します。</span><span class="sxs-lookup"><span data-stu-id="2c5fc-125">If the Messaging Engine does not discover this interface, the Messaging Engine performs a **QueryInterface** for **IBTBatchTransmitter**, discovery of which indicates that the adapter is a batch-aware transmitter.</span></span>  
  
     <span data-ttu-id="2c5fc-126">これらのどちらのインターフェイスも検出されなかった場合、エラー状態となり、初期化が失敗します。</span><span class="sxs-lookup"><span data-stu-id="2c5fc-126">If the Messaging Engine discovers neither of these interfaces, an error condition results, causing the initialization to fail.</span></span> <span data-ttu-id="2c5fc-127">必須のインターフェイスのうち 1 つでも検出されないものがあると、初期化は失敗します。</span><span class="sxs-lookup"><span data-stu-id="2c5fc-127">The initialization fails if any mandatory interfaces are not discovered.</span></span>  
  
 <span data-ttu-id="2c5fc-128">この API の呼び出しの順序は、次の図のようになります。アダプターは、青色で示されるインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="2c5fc-128">The following diagram illustrates this sequence of API calls; the interfaces in blue are implemented by the adapter.</span></span>  
  
 ![](../core/media/transmit-adapter-init.gif "Transmit_adapter_init")  
  
 <span data-ttu-id="2c5fc-129">アダプターは初期化して構成された時点で、すぐにメッセージを送信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2c5fc-129">The adapter can send messages as soon as it is initialized and configured.</span></span>  
  
 <span data-ttu-id="2c5fc-130">送信アダプターを初期化するときの、オブジェクト間の対話処理を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2c5fc-130">The following figure shows the object interactions involved in initializing a send adapter.</span></span>  
  
 ![](../core/media/ebiz-sdk-devadapter10.gif "ebiz_sdk_devadapter10")  
<span data-ttu-id="2c5fc-131">送信アダプターの初期化のワークフロー</span><span class="sxs-lookup"><span data-stu-id="2c5fc-131">Workflow for initializing a send adapter</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c5fc-132">アダプターをブロックしないでください呼び出しにおいてメッセージング エンジンなど**IBTTransportControl.Initialize**と**IPersistPropertyBag.Load**です。</span><span class="sxs-lookup"><span data-stu-id="2c5fc-132">Adapters should not block the Messaging Engine in calls such as **IBTTransportControl.Initialize** and **IPersistPropertyBag.Load**.</span></span> <span data-ttu-id="2c5fc-133">これらの呼び出しで過度な処理を実行した場合、サービスの開始が遅れる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2c5fc-133">Performing excessive processing in these calls affects service startup time.</span></span>