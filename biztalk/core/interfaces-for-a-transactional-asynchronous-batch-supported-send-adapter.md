---
title: Batch でサポートされているトランザクションの非同期送信アダプター用のインターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e5b2dbdf-e6ba-4b58-a0a5-fc78feaf5c35
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e911445cd0f92bbe863f10b8335aee0bf64630bd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381856"
---
# <a name="interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter"></a><span data-ttu-id="5ca68-102">Batch でサポートされているトランザクションの非同期送信アダプター用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="5ca68-102">Interfaces for a Transactional Asynchronous Batch-Supported Send Adapter</span></span>
<span data-ttu-id="5ca68-103">送信アダプターは、作成し、メッセージのトランザクション送信が必要な場合は、トランザクションを制御できます。</span><span class="sxs-lookup"><span data-stu-id="5ca68-103">A send adapter can create and control transactions when transactional transmission of messages is required.</span></span> <span data-ttu-id="5ca68-104">トランザクション送信をサポートするために、アダプターは、次のインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ca68-104">To support transactional send, an adapter needs to implement the following interfaces:</span></span>  
  
- <span data-ttu-id="5ca68-105">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="5ca68-105">**IBTTransport**</span></span>  
  
- <span data-ttu-id="5ca68-106">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="5ca68-106">**IBaseComponent**</span></span>  
  
- <span data-ttu-id="5ca68-107">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="5ca68-107">**IBTTransportControl**</span></span>  
  
- <span data-ttu-id="5ca68-108">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="5ca68-108">**IPersistPropertyBag**</span></span>  
  
- <span data-ttu-id="5ca68-109">**IBTBatchTransmitter**</span><span class="sxs-lookup"><span data-stu-id="5ca68-109">**IBTBatchTransmitter**</span></span>  
  
- <span data-ttu-id="5ca68-110">**IBTTransmitterBatch**</span><span class="sxs-lookup"><span data-stu-id="5ca68-110">**IBTTransmitterBatch**</span></span>  
  
- <span data-ttu-id="5ca68-111">**IBTBatchCallBack**</span><span class="sxs-lookup"><span data-stu-id="5ca68-111">**IBTBatchCallBack**</span></span>  
  
  <span data-ttu-id="5ca68-112">アダプターは、MSDTC トランザクションを作成しへの呼び出しでは、そのオブジェクトへのポインターを返します、 **BeginBatch**のメソッド、 **IBTTransmitterBatch**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="5ca68-112">An adapter creates an MSDTC transaction and returns a pointer to that object in the call to the **BeginBatch** method of the **IBTTransmitterBatch** interface.</span></span> <span data-ttu-id="5ca68-113">メッセージング エンジンは、送信アダプターに送信メッセージのポストバックがバッチを取得するには、このメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="5ca68-113">The Messaging Engine calls this method to obtain a batch with which it posts outgoing messages to the send adapter.</span></span> <span data-ttu-id="5ca68-114">使用して、トランザクションの結果をメッセージング エンジンに通知アダプターが送信操作が完了し、コミットまたはトランザクションをロールバック、ときに、 **DTCCommitConfirm**のメソッド、 **IBTDTCCommitConfirm**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="5ca68-114">When the adapter finishes the send operation and commits or rolls back a transaction, it notifies the Messaging Engine of the result of the transaction by using the **DTCCommitConfirm** method of the **IBTDTCCommitConfirm** interface.</span></span>  
  
  <span data-ttu-id="5ca68-115">トランザクション送信操作を実行するときに、次の図は、トランスポート プロキシと送信アダプター間のやり取りを示します。</span><span class="sxs-lookup"><span data-stu-id="5ca68-115">The following figure shows the interaction between the transport proxy and the send adapter when performing a transactional send operation.</span></span>  
  
  <span data-ttu-id="5ca68-116">![](../core/media/ebiz-sdk-devadapter8.gif "ebiz_sdk_devadapter8")</span><span class="sxs-lookup"><span data-stu-id="5ca68-116">![](../core/media/ebiz-sdk-devadapter8.gif "ebiz_sdk_devadapter8")</span></span>  
  <span data-ttu-id="5ca68-117">トランザクション メッセージを非同期的に送信するためのワークフロー</span><span class="sxs-lookup"><span data-stu-id="5ca68-117">Workflow for sending a transactional message asynchronously</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ca68-118">参照</span><span class="sxs-lookup"><span data-stu-id="5ca68-118">See Also</span></span>  
 <span data-ttu-id="5ca68-119">[アダプター変数](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="5ca68-119">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="5ca68-120">[送信アダプターの開発](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="5ca68-120">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="5ca68-121">[インスタンス化し、送信アダプターの初期化](../core/instantiating-and-initializing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="5ca68-121">[Instantiating and Initializing a Send Adapter](../core/instantiating-and-initializing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="5ca68-122">[送信アダプターの同期用のインターフェイス](../core/interfaces-for-a-synchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="5ca68-122">[Interfaces for a Synchronous Send Adapter](../core/interfaces-for-a-synchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="5ca68-123">[送信アダプターの非同期インターフェイス](../core/interfaces-for-an-asynchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="5ca68-123">[Interfaces for an Asynchronous Send Adapter](../core/interfaces-for-an-asynchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="5ca68-124">[同期のバッチでサポートされている送信アダプター用のインターフェイス](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="5ca68-124">[Interfaces for a Synchronous Batch-Supported Send Adapter](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="5ca68-125">[バッチ処理に対応の非同期送信アダプター用のインターフェイス](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="5ca68-125">[Interfaces for an Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span></span>  
 [<span data-ttu-id="5ca68-126">送信請求 - 応答送信アダプター用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="5ca68-126">Interfaces for a Solicit-Response Send Adapter</span></span>](../core/interfaces-for-a-solicit-response-send-adapter.md)