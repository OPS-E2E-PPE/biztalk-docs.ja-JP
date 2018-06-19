---
title: 送信アダプターの送信請求-応答のインターフェイス |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c54650e8-dbfb-4c66-843b-0b82c8183dd4
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb8ce9b625bfea144f9a4a615a604efdbe2a3cb1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257602"
---
# <a name="interfaces-for-a-solicit-response-send-adapter"></a><span data-ttu-id="21e99-102">送信請求 - 応答送信アダプター用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="21e99-102">Interfaces for a Solicit-Response Send Adapter</span></span>
<span data-ttu-id="21e99-103">送信アダプターが受信サーバーに応答メッセージを送信するアダプターと同じバッチ メカニズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="21e99-103">Send adapters use the same batch mechanism as receive adapters to submit response messages back into the server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="21e99-104">送信請求 - 応答アダプターではメッセージを非同期で処理することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="21e99-104">It is recommended that a solicit-response adapter is process messages asynchronously.</span></span> <span data-ttu-id="21e99-105">同期的に処理した場合、メッセージが重複する危険性があります。</span><span class="sxs-lookup"><span data-stu-id="21e99-105">If the adapter processes message in a synchronous manner, there is a risk of message duplication.</span></span>  
  
 <span data-ttu-id="21e99-106">送信アダプターが送信請求 - 応答モードで動作するには、アダプターに次のインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21e99-106">Send adapters need to implement the following interfaces to work in solicit-response mode:</span></span>  
  
-   <span data-ttu-id="21e99-107">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="21e99-107">**IBTTransport**</span></span>  
  
-   <span data-ttu-id="21e99-108">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="21e99-108">**IBaseComponent**</span></span>  
  
-   <span data-ttu-id="21e99-109">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="21e99-109">**IBTTransportControl**</span></span>  
  
-   <span data-ttu-id="21e99-110">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="21e99-110">**IPersistPropertyBag**</span></span>  
  
-   <span data-ttu-id="21e99-111">**IBTTransmitter**</span><span class="sxs-lookup"><span data-stu-id="21e99-111">**IBTTransmitter**</span></span>  
  
-   <span data-ttu-id="21e99-112">**IBTTransmitterBatch**と**IBTBatchTransmitter** (送信バッチ処理が必要な場合)</span><span class="sxs-lookup"><span data-stu-id="21e99-112">**IBTTransmitterBatch** and **IBTBatchTransmitter** (if send batching is required)</span></span>  
  
-   <span data-ttu-id="21e99-113">**IBTBatchCallBack**</span><span class="sxs-lookup"><span data-stu-id="21e99-113">**IBTBatchCallBack**</span></span>  
  
 <span data-ttu-id="21e99-114">オブジェクト間では次の対話処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="21e99-114">The steps involved in the object interaction are as follows:</span></span>  
  
1.  <span data-ttu-id="21e99-115">送信アダプターは、送信請求メッセージを送信した後、送信先のサーバーから応答メッセージを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="21e99-115">After the adapter sends a solicit message, it receives back a response message from that destination server.</span></span> <span data-ttu-id="21e99-116">その後、トランスポート プロキシからバッチを取得します。</span><span class="sxs-lookup"><span data-stu-id="21e99-116">It then obtains a batch from the transport proxy.</span></span>  
  
2.  <span data-ttu-id="21e99-117">アダプターがバッチに呼び出すことによって、応答メッセージを追加**ibttransportproxy::submitresponsemessage**です。</span><span class="sxs-lookup"><span data-stu-id="21e99-117">The adapter adds the response message to the batch by calling **IBTTransportProxy::SubmitResponseMessage**.</span></span>  
  
3.  <span data-ttu-id="21e99-118">アダプターを呼び出してバッチを送信する**ibttransportproxy::done**へのポインターを渡してその**IBTBatchComplete**メッセージング エンジンからコールバック インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="21e99-118">The adapter submits the batch by calling **IBTTransportProxy::Done** passing in a pointer to its **IBTBatchComplete** interface for the callback from the Messaging Engine.</span></span>  
  
4.  <span data-ttu-id="21e99-119">メッセージング エンジンがアダプターの**ibtbatchcallback::batchcomplete**送信操作の結果のことを通知する、トランスポート プロキシを使用してコールバック メソッド。</span><span class="sxs-lookup"><span data-stu-id="21e99-119">The Messaging Engine calls the adapter's **IBTBatchCallBack::BatchComplete** callback method using the transport proxy notifying it of the result of submission operation.</span></span>  
  
 <span data-ttu-id="21e99-120">送信請求 - 応答送信アダプターを作成するときの、オブジェクト間の対話処理を次に示します。</span><span class="sxs-lookup"><span data-stu-id="21e99-120">The following figure shows the object interactions involved in creating a solicit-response send adapter.</span></span>  
  
 ![](../core/media/ebiz-sdk-devadapter13.gif "ebiz_sdk_devadapter13")  
<span data-ttu-id="21e99-121">送信請求 - 応答送信アダプターにおける対話処理</span><span class="sxs-lookup"><span data-stu-id="21e99-121">Interaction diagram for a solicit-response send adapter</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21e99-122">参照</span><span class="sxs-lookup"><span data-stu-id="21e99-122">See Also</span></span>  
 <span data-ttu-id="21e99-123">[アダプタの変数](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="21e99-123">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="21e99-124">[送信アダプターの開発](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="21e99-124">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="21e99-125">[インスタンス化して、送信アダプターの初期化](../core/instantiating-and-initializing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="21e99-125">[Instantiating and Initializing a Send Adapter](../core/instantiating-and-initializing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="21e99-126">[送信アダプターの同期用のインターフェイス](../core/interfaces-for-a-synchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="21e99-126">[Interfaces for a Synchronous Send Adapter](../core/interfaces-for-a-synchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="21e99-127">[送信アダプターの非同期インターフェイス](../core/interfaces-for-an-asynchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="21e99-127">[Interfaces for an Asynchronous Send Adapter](../core/interfaces-for-an-asynchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="21e99-128">[同期のバッチでサポートされている送信アダプター用のインターフェイス](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="21e99-128">[Interfaces for a Synchronous Batch-Supported Send Adapter](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="21e99-129">[サポートされるバッチの非同期送信アダプター用のインターフェイス](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="21e99-129">[Interfaces for an Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span></span>  
 [<span data-ttu-id="21e99-130">バッチでサポートされているトランザクションの非同期送信アダプター用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="21e99-130">Interfaces for a Transactional Asynchronous Batch-Supported Send Adapter</span></span>](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md)