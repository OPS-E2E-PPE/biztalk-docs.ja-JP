---
title: 受信アダプターの分離インターフェイス |Microsoft ドキュメント
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
ms.openlocfilehash: 7848e5c808ad2e7517d0e850e449f8a8575ec5da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257770"
---
# <a name="interfaces-for-an-isolated-receive-adapter"></a><span data-ttu-id="a4a3d-102">分離受信アダプター用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="a4a3d-102">Interfaces for an Isolated Receive Adapter</span></span>
<span data-ttu-id="a4a3d-103">分離受信アダプターは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 以外のプロセス領域でホストされます。</span><span class="sxs-lookup"><span data-stu-id="a4a3d-103">Isolated receive adapters are hosted in a process space other than the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] process.</span></span> <span data-ttu-id="a4a3d-104">メッセージング エンジンと連携するために、分離受信アダプターは、エンジンが分離受信アダプターを構成および制御できるように、起動時に分離受信アダプター自体を登録します。</span><span class="sxs-lookup"><span data-stu-id="a4a3d-104">To interact with the Messaging Engine, an isolated receive adapter registers itself on startup so that the engine can configure and control it.</span></span> <span data-ttu-id="a4a3d-105">アダプターが、トランスポート プロキシを作成し、インターフェイスの照会**IBTTransportProxy**、および呼び出し**IBTTransportProxy.RegisterIsolatedReceiver**を登録する、 **IBTTransportConfig**メッセージング エンジンにコールバック インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="a4a3d-105">The adapter creates the transport proxy, queries for the interface **IBTTransportProxy**, and calls **IBTTransportProxy.RegisterIsolatedReceiver** to register its **IBTTransportConfig** callback interface with the Messaging Engine.</span></span> <span data-ttu-id="a4a3d-106">この同期呼び出しは、アダプターが最初のメッセージを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に送信する前に発生します。</span><span class="sxs-lookup"><span data-stu-id="a4a3d-106">This synchronous call occurs before the adapter submits its first message to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="a4a3d-107">これによって、メッセージ エンジンは、アダプターへのコールバックを行い、どのエンドポイントがアクティブであるか、および受信メッセージの待ち受けの対象となる必要があるかをアダプターに示すことができます。</span><span class="sxs-lookup"><span data-stu-id="a4a3d-107">This allows the Messaging Engine to call back into the adapter and tell it which of its endpoints are active and should be listened on for incoming messages.</span></span> <span data-ttu-id="a4a3d-108">分離アダプターは次のインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4a3d-108">Isolated adapters must implement the following interfaces:</span></span>  
  
-   <span data-ttu-id="a4a3d-109">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="a4a3d-109">**IBTTransport**</span></span>  
  
-   <span data-ttu-id="a4a3d-110">**IBTTransportConfig**</span><span class="sxs-lookup"><span data-stu-id="a4a3d-110">**IBTTransportConfig**</span></span>  
  
-   <span data-ttu-id="a4a3d-111">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="a4a3d-111">**IBaseComponent**</span></span>  
  
-   <span data-ttu-id="a4a3d-112">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="a4a3d-112">**IPersistPropertyBag**</span></span>  
  
 <span data-ttu-id="a4a3d-113">アダプターの登録では、構成および有効化された受信場所をアダプターが渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4a3d-113">Registering the adapter requires the adapter to pass a configured and enabled receive location.</span></span> <span data-ttu-id="a4a3d-114">アダプターのホスト プロセスは、BizTalk 分離ホスト ユーザー グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4a3d-114">The adapter's host process must be a member of the BizTalk Isolated Host Users group.</span></span> <span data-ttu-id="a4a3d-115">また、クラス ID が正しく、実行するように構成されているホスト インスタンスに対応したコンピューターで実行中であることを確認するための照会が、アダプターに対して行われます。</span><span class="sxs-lookup"><span data-stu-id="a4a3d-115">In addition, the adapter is queried to ensure that it has the correct class ID and is running on the computer that was configured for that host instance.</span></span>  
  
 <span data-ttu-id="a4a3d-116">登録した後、アダプターが正常にトランスポート プロキシを使用して、メッセージング エンジンは、構成情報を渡しますおよび、他の受信場所のアダプターに戻し、呼び出すことによって、**ロード**のメソッド、 **IPersistPropertyBag**インターフェイスおよび**AddReceiveEndpoint**のメソッド、 **IBTTransportConfig**それぞれインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="a4a3d-116">After the adapter has successfully registered with the transport proxy, the Messaging Engine passes the configuration information and the other receive locations back to the adapter by calling the **Load** method of the **IPersistPropertyBag** interface and the **AddReceiveEndpoint** method of the **IBTTransportConfig** interface respectively.</span></span>  
  
 <span data-ttu-id="a4a3d-117">分離受信アダプターがメッセージの処理を終了し、終了すると、呼び出す必要があります、 **TerminateIsolatedReceiver**のメソッド、 **IBTTransportProxy**インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="a4a3d-117">When an isolated receive adapter ends the processing of messages and is going to be terminated, it must call the **TerminateIsolatedReceiver** method of the **IBTTransportProxy** interface.</span></span>  
  
 <span data-ttu-id="a4a3d-118">分離受信アダプターを作成するときのオブジェクト間の対話処理を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="a4a3d-118">The following illustration shows the object interactions involved in creating an isolated receive adapter.</span></span>  
  
 ![](../core/media/ebiz-sdk-devadapter9.gif "ebiz_sdk_devadapter9")  
<span data-ttu-id="a4a3d-119">分離受信アダプターの初期化のワークフロー</span><span class="sxs-lookup"><span data-stu-id="a4a3d-119">Workflow for initializing an isolated receive adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4a3d-120">アダプターでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に対して現在実行している要求を追跡することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a4a3d-120">We recommend that the adapter keep track of currently executing requests to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="a4a3d-121">アダプターをブロックする必要があります、 **Terminate**作業数が 0 に到達するまでメソッドです。</span><span class="sxs-lookup"><span data-stu-id="a4a3d-121">The adapter should block the **Terminate** method until the work count has reached zero.</span></span> <span data-ttu-id="a4a3d-122">受信側では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に対して公開されていない未処理の要求がこの作業に含まれます。</span><span class="sxs-lookup"><span data-stu-id="a4a3d-122">On the receive side, this work includes any outstanding requests that have not been published to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="a4a3d-123">応答メッセージは通常配信されることは後に受信アダプターに注意してください**Terminate**と呼びます。</span><span class="sxs-lookup"><span data-stu-id="a4a3d-123">Note that response messages are typically not delivered to a receive adapter after **Terminate** is called.</span></span> <span data-ttu-id="a4a3d-124">一般に、アダプターの呼び出し後に、 **Terminate**メソッド、メッセージング エンジンでは送信請求-応答の組み合わせに対する応答メッセージを除き、新しいメッセージを公開要求が受け付けられません。</span><span class="sxs-lookup"><span data-stu-id="a4a3d-124">In general, after the adapter calls the **Terminate** method, the Messaging Engine does not accept requests to publish new messages, with the exception of response messages for solicit-response pairs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4a3d-125">1 つのプロセスは 1 つのアダプターしかホストできませんが、分離アダプターの複数のインスタンスをホストできます。</span><span class="sxs-lookup"><span data-stu-id="a4a3d-125">One process may host several instances of isolated adapters, while only one process may host one adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4a3d-126">参照</span><span class="sxs-lookup"><span data-stu-id="a4a3d-126">See Also</span></span>  
 <span data-ttu-id="a4a3d-127">[アダプタの変数](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="a4a3d-127">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="a4a3d-128">[開発、受信アダプター](../core/developing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="a4a3d-128">[Developing a Receive Adapter](../core/developing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="a4a3d-129">[インスタンス化と初期化、アダプターの受信](../core/instantiating-and-initializing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="a4a3d-129">[Instantiating and Initializing a Receive Adapter](../core/instantiating-and-initializing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="a4a3d-130">[受信アダプターをインプロセスで用のインターフェイス](../core/interfaces-for-an-in-process-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="a4a3d-130">[Interfaces for an In-Process Receive Adapter](../core/interfaces-for-an-in-process-receive-adapter.md) </span></span>  
 <span data-ttu-id="a4a3d-131">[受信アダプターのバッチ サポート用のインターフェイス](../core/interfaces-for-a-batch-supported-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="a4a3d-131">[Interfaces for a Batch-Supported Receive Adapter](../core/interfaces-for-a-batch-supported-receive-adapter.md) </span></span>  
 <span data-ttu-id="a4a3d-132">[受信アダプターのバッチでサポートされているトランザクション パブリケーション用のインターフェイス](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="a4a3d-132">[Interfaces for a Transactional Batch-Supported Receive Adapter](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md) </span></span>  
 [<span data-ttu-id="a4a3d-133">アダプターの受信要求-応答の同期用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="a4a3d-133">Interfaces for a Synchronous Request-Response Receive Adapter</span></span>](../core/interfaces-for-a-synchronous-request-response-receive-adapter.md)