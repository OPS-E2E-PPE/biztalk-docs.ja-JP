---
title: インターフェイスの分離受信アダプター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5c6b195e-76bf-4c3e-a324-5513bc24fed1
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d0db026534a15b1c1e3cfe2f5582db8b9e1078f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331489"
---
# <a name="interfaces-for-an-isolated-receive-adapter"></a><span data-ttu-id="d66da-102">分離受信アダプター用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="d66da-102">Interfaces for an Isolated Receive Adapter</span></span>
<span data-ttu-id="d66da-103">分離受信アダプターが以外のプロセス空間内でホストされる、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロセス。</span><span class="sxs-lookup"><span data-stu-id="d66da-103">Isolated receive adapters are hosted in a process space other than the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] process.</span></span> <span data-ttu-id="d66da-104">をメッセージング エンジンと対話するには、分離受信アダプターのレジスタ自体の起動時に、エンジンの構成および制御できるようにします。</span><span class="sxs-lookup"><span data-stu-id="d66da-104">To interact with the Messaging Engine, an isolated receive adapter registers itself on startup so that the engine can configure and control it.</span></span> <span data-ttu-id="d66da-105">アダプターのトランスポート プロキシを作成、インターフェイスのクエリ**IBTTransportProxy**、および呼び出し**IBTTransportProxy.RegisterIsolatedReceiver**を登録するその**IBTTransportConfig**メッセージング エンジンとコールバック インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="d66da-105">The adapter creates the transport proxy, queries for the interface **IBTTransportProxy**, and calls **IBTTransportProxy.RegisterIsolatedReceiver** to register its **IBTTransportConfig** callback interface with the Messaging Engine.</span></span> <span data-ttu-id="d66da-106">アダプターは、その最初のメッセージを送信する前に、この同期呼び出しが発生した[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="d66da-106">This synchronous call occurs before the adapter submits its first message to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="d66da-107">これにより、メッセージング エンジンでアダプターにコールバックして、エンドポイントがアクティブと受信メッセージをリッスンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d66da-107">This allows the Messaging Engine to call back into the adapter and tell it which of its endpoints are active and should be listened on for incoming messages.</span></span> <span data-ttu-id="d66da-108">分離アダプターは、次のインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d66da-108">Isolated adapters must implement the following interfaces:</span></span>  
  
- <span data-ttu-id="d66da-109">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="d66da-109">**IBTTransport**</span></span>  
  
- <span data-ttu-id="d66da-110">**IBTTransportConfig**</span><span class="sxs-lookup"><span data-stu-id="d66da-110">**IBTTransportConfig**</span></span>  
  
- <span data-ttu-id="d66da-111">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="d66da-111">**IBaseComponent**</span></span>  
  
- <span data-ttu-id="d66da-112">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="d66da-112">**IPersistPropertyBag**</span></span>  
  
  <span data-ttu-id="d66da-113">アダプターを登録するには、アダプターが渡す、構成されている必要があり、有効になっている受信場所。</span><span class="sxs-lookup"><span data-stu-id="d66da-113">Registering the adapter requires the adapter to pass a configured and enabled receive location.</span></span> <span data-ttu-id="d66da-114">アダプターのホスト プロセスは、BizTalk 分離ホスト ユーザー グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="d66da-114">The adapter's host process must be a member of the BizTalk Isolated Host Users group.</span></span> <span data-ttu-id="d66da-115">さらに、アダプターを照会して、id が正しいクラスと、そのホスト インスタンス用に構成されたコンピューターで実行していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d66da-115">In addition, the adapter is queried to ensure that it has the correct class ID and is running on the computer that was configured for that host instance.</span></span>  
  
  <span data-ttu-id="d66da-116">メッセージング エンジンは、構成情報を渡すし、呼び出すことによって、その他の受信場所、アダプターをアダプターがトランスポート プロキシで正常に登録した後、**ロード**のメソッド、 **IPersistPropertyBag**インターフェイスと**AddReceiveEndpoint**のメソッド、 **IBTTransportConfig**それぞれインターフェイスします。</span><span class="sxs-lookup"><span data-stu-id="d66da-116">After the adapter has successfully registered with the transport proxy, the Messaging Engine passes the configuration information and the other receive locations back to the adapter by calling the **Load** method of the **IPersistPropertyBag** interface and the **AddReceiveEndpoint** method of the **IBTTransportConfig** interface respectively.</span></span>  
  
  <span data-ttu-id="d66da-117">呼び出す必要があります、分離受信アダプターがメッセージの処理を終了および終了する、 **TerminateIsolatedReceiver**のメソッド、 **IBTTransportProxy**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="d66da-117">When an isolated receive adapter ends the processing of messages and is going to be terminated, it must call the **TerminateIsolatedReceiver** method of the **IBTTransportProxy** interface.</span></span>  
  
  <span data-ttu-id="d66da-118">次の図は、受信アダプターの分離の作成に関連するオブジェクトの相互作用を示しています。</span><span class="sxs-lookup"><span data-stu-id="d66da-118">The following illustration shows the object interactions involved in creating an isolated receive adapter.</span></span>  
  
  <span data-ttu-id="d66da-119">![](../core/media/ebiz-sdk-devadapter9.gif "ebiz_sdk_devadapter9")</span><span class="sxs-lookup"><span data-stu-id="d66da-119">![](../core/media/ebiz-sdk-devadapter9.gif "ebiz_sdk_devadapter9")</span></span>  
  <span data-ttu-id="d66da-120">受信アダプターの分離を初期化するためのワークフロー。</span><span class="sxs-lookup"><span data-stu-id="d66da-120">Workflow for initializing an isolated receive adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d66da-121">あるアダプターの追跡を現在実行中の要求をお勧めします。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="d66da-121">We recommend that the adapter keep track of currently executing requests to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="d66da-122">アダプターをブロックする必要があります、 **Terminate**作業数が 0 に到達するまでメソッド。</span><span class="sxs-lookup"><span data-stu-id="d66da-122">The adapter should block the **Terminate** method until the work count has reached zero.</span></span> <span data-ttu-id="d66da-123">受信側では、この作業に公開されていない、未処理の要求が含まれています[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="d66da-123">On the receive side, this work includes any outstanding requests that have not been published to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="d66da-124">応答メッセージは通常できませんに配信されたこと後に受信アダプターに注意してください。 **Terminate**が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d66da-124">Note that response messages are typically not delivered to a receive adapter after **Terminate** is called.</span></span> <span data-ttu-id="d66da-125">一般に、アダプターの呼び出し後、 **Terminate**メソッド、メッセージング エンジンでは送信請求-応答の組み合わせに対する応答メッセージを除き、新しいメッセージを発行する要求が受け付けられません。</span><span class="sxs-lookup"><span data-stu-id="d66da-125">In general, after the adapter calls the **Terminate** method, the Messaging Engine does not accept requests to publish new messages, with the exception of response messages for solicit-response pairs.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="d66da-126">1 つだけのプロセスが 1 つのアダプターをホスト中に、1 つのプロセスは、分離アダプターの複数のインスタンスをホストできます。</span><span class="sxs-lookup"><span data-stu-id="d66da-126">One process may host several instances of isolated adapters, while only one process may host one adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d66da-127">参照</span><span class="sxs-lookup"><span data-stu-id="d66da-127">See Also</span></span>  
 <span data-ttu-id="d66da-128">[アダプター変数](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="d66da-128">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="d66da-129">[開発、受信アダプター](../core/developing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="d66da-129">[Developing a Receive Adapter](../core/developing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="d66da-130">[インスタンス化と初期化、アダプターの受信](../core/instantiating-and-initializing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="d66da-130">[Instantiating and Initializing a Receive Adapter](../core/instantiating-and-initializing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="d66da-131">[受信アダプターをインプロセスで用のインターフェイス](../core/interfaces-for-an-in-process-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="d66da-131">[Interfaces for an In-Process Receive Adapter](../core/interfaces-for-an-in-process-receive-adapter.md) </span></span>  
 <span data-ttu-id="d66da-132">[受信アダプターのバッチ サポート用のインターフェイス](../core/interfaces-for-a-batch-supported-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="d66da-132">[Interfaces for a Batch-Supported Receive Adapter](../core/interfaces-for-a-batch-supported-receive-adapter.md) </span></span>  
 <span data-ttu-id="d66da-133">[受信アダプターのバッチでサポートされているトランザクション パブリケーション用のインターフェイス](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="d66da-133">[Interfaces for a Transactional Batch-Supported Receive Adapter](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md) </span></span>  
 [<span data-ttu-id="d66da-134">要求 - 応答の同期受信アダプター用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="d66da-134">Interfaces for a Synchronous Request-Response Receive Adapter</span></span>](../core/interfaces-for-a-synchronous-request-response-receive-adapter.md)