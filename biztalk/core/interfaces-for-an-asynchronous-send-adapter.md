---
title: 送信アダプターの非同期インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a214716-8f39-400d-a111-ba1b92a284b4
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd90aa9c5d010acc4d73a66220964ebdcb31e1f0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980355"
---
# <a name="interfaces-for-an-asynchronous-send-adapter"></a><span data-ttu-id="b7102-102">非同期送信アダプター用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="b7102-102">Interfaces for an Asynchronous Send Adapter</span></span>
<span data-ttu-id="b7102-103">一度に 1 つのメッセージを送信するアダプターは、同期的または非同期的にメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="b7102-103">Adapters sending messages one at a time may send messages either synchronously or asynchronously.</span></span> <span data-ttu-id="b7102-104">アダプターは、送信操作中にトランスポート プロキシ スレッドをブロックせずに、個々のスレッドを使用する場合、メッセージを非同期的に送信します。</span><span class="sxs-lookup"><span data-stu-id="b7102-104">An adapter sends messages asynchronously when it does not block the transport proxy thread but rather uses a separate thread while performing the send operations.</span></span> <span data-ttu-id="b7102-105">メッセージを非同期的に送信できるようにするには、アダプターに次のインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7102-105">To be able to send messages asynchronously, an adapter needs to implement the following interfaces:</span></span>  
  
- <span data-ttu-id="b7102-106">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="b7102-106">**IBTTransport**</span></span>  
  
- <span data-ttu-id="b7102-107">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="b7102-107">**IBaseComponent**</span></span>  
  
- <span data-ttu-id="b7102-108">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="b7102-108">**IBTTransportControl**</span></span>  
  
- <span data-ttu-id="b7102-109">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="b7102-109">**IPersistPropertyBag**</span></span>  
  
- <span data-ttu-id="b7102-110">**IBTTransmitter**</span><span class="sxs-lookup"><span data-stu-id="b7102-110">**IBTTransmitter**</span></span>  
  
  <span data-ttu-id="b7102-111">送信アダプターは、メッセージ エンジンの要求時にメッセージをサーバーから送信するとき、次の順序でアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="b7102-111">The following steps describe the sequence of actions that the send adapter performs to transmit messages out of the server at the request of the Messaging Engine:</span></span>  
  
1.  <span data-ttu-id="b7102-112">メッセージング エンジンはトランスポート プロキシを使用して呼び出すことによって、送信アダプター、送信メッセージを渡す、 **TransmitMessage**のメソッド、 **IBTTransmitter**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="b7102-112">The Messaging Engine uses the transport proxy to pass an outgoing message to a send adapter by calling the **TransmitMessage** method of the **IBTTransmitter** interface.</span></span>  
  
2.  <span data-ttu-id="b7102-113">アダプターを直ちに返します**TransmitMessage**をいくつかの内部キューを返す送信されるメッセージを格納した後`False`の**bDeleteMessage**します。</span><span class="sxs-lookup"><span data-stu-id="b7102-113">The adapter returns immediately from **TransmitMessage** after storing the message to be sent to some internal queue, and returns `False` for **bDeleteMessage**.</span></span> <span data-ttu-id="b7102-114">これにより、メッセージが非同期で送信されることがメッセージング エンジンに伝えられます。</span><span class="sxs-lookup"><span data-stu-id="b7102-114">This tells the Messaging Engine the message will be transmitted in an asynchronous manner.</span></span>  
  
3.  <span data-ttu-id="b7102-115">アダプターは、その独自のスレッド プールを使用してメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="b7102-115">The adapter sends the message using its own thread pool.</span></span>  
  
4.  <span data-ttu-id="b7102-116">送信操作が完了すると、アダプターは元のメッセージをメッセージ ボックス データベースから削除します。</span><span class="sxs-lookup"><span data-stu-id="b7102-116">After the send operation completes, the adapter deletes the original message from the MessageBox database.</span></span> <span data-ttu-id="b7102-117">使用して、メッセージング エンジンからバッチを取得、 **IBTTransportBatch.GetBatch**トランスポート プロキシにし、呼び出しメソッド**DeleteMessage**します。</span><span class="sxs-lookup"><span data-stu-id="b7102-117">It obtains a batch from the Messaging Engine using the **IBTTransportBatch.GetBatch** method of the transport proxy, and then calls **DeleteMessage**.</span></span>  
  
     <span data-ttu-id="b7102-118">非同期送信アダプターを作成するときの、オブジェクト間の対話処理を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b7102-118">The following figure shows the object interactions involved in creating an asynchronous send adapter.</span></span>  
  
     <span data-ttu-id="b7102-119">![](../core/media/ebiz-sdk-devadapter5.gif "ebiz_sdk_devadapter5")</span><span class="sxs-lookup"><span data-stu-id="b7102-119">![](../core/media/ebiz-sdk-devadapter5.gif "ebiz_sdk_devadapter5")</span></span>  
<span data-ttu-id="b7102-120">メッセージの非同期送信のワークフロー</span><span class="sxs-lookup"><span data-stu-id="b7102-120">Workflow for sending a message asynchronously</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b7102-121">アダプターでは現在処理中のメッセージ数を保持することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b7102-121">We recommend that the adapter keep a count of the messages currently being processed.</span></span> <span data-ttu-id="b7102-122">アダプターをブロックする必要があります、 **Terminate**メソッド メッセージの数が 0 に到達するまでです。</span><span class="sxs-lookup"><span data-stu-id="b7102-122">The adapter should block the **Terminate** method until the message count has reached zero.</span></span> <span data-ttu-id="b7102-123">送信アダプターの場合は、処理されているメッセージを適切に処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7102-123">For send adapters, messages that are being processed should be handled appropriately.</span></span> <span data-ttu-id="b7102-124">つまり、非同期で正常に送信されたメッセージは、アダプターのプライベート アプリケーション メッセージ キューから削除して、メッセージが 2 回送信されるのを防ぐ必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7102-124">This means that any message that was successfully delivered asynchronously should be deleted from the adapter's private application message queue to prevent messages from being sent twice.</span></span> <span data-ttu-id="b7102-125">一般的に、 **Terminate**と呼ばれますが、アダプターからの新しいメッセージを公開する要求を受け入れません、メッセージング エンジンによって。</span><span class="sxs-lookup"><span data-stu-id="b7102-125">In general, after **Terminate** is called by the Messaging Engine it does not accept requests to publish new messages from the adapter.</span></span> <span data-ttu-id="b7102-126">送信請求 - 応答の組み合わせに関連する応答メッセージの場合は例外です。</span><span class="sxs-lookup"><span data-stu-id="b7102-126">The exception to this is response messages related to solicit-response pairs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7102-127">参照</span><span class="sxs-lookup"><span data-stu-id="b7102-127">See Also</span></span>  
 <span data-ttu-id="b7102-128">[アダプター変数](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="b7102-128">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="b7102-129">[送信アダプターの開発](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="b7102-129">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="b7102-130">[インスタンス化し、送信アダプターの初期化](../core/instantiating-and-initializing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="b7102-130">[Instantiating and Initializing a Send Adapter](../core/instantiating-and-initializing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="b7102-131">[送信アダプターの同期用のインターフェイス](../core/interfaces-for-a-synchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="b7102-131">[Interfaces for a Synchronous Send Adapter](../core/interfaces-for-a-synchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="b7102-132">[同期のバッチでサポートされている送信アダプター用のインターフェイス](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="b7102-132">[Interfaces for a Synchronous Batch-Supported Send Adapter](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="b7102-133">[バッチ処理に対応の非同期送信アダプター用のインターフェイス](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="b7102-133">[Interfaces for an Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="b7102-134">[Batch でサポートされているトランザクションの非同期送信アダプター用のインターフェイス](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="b7102-134">[Interfaces for a Transactional Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span></span>  
 [<span data-ttu-id="b7102-135">送信請求 - 応答送信アダプター用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="b7102-135">Interfaces for a Solicit-Response Send Adapter</span></span>](../core/interfaces-for-a-solicit-response-send-adapter.md)