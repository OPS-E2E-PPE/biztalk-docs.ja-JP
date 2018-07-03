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
ms.openlocfilehash: 0c3ad79f09563b3e65ccfab64da5b9ec6ea3033c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982899"
---
# <a name="interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter"></a><span data-ttu-id="f2584-102">バッチ処理に対応したトランザクションとしての非同期送信アダプター用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="f2584-102">Interfaces for a Transactional Asynchronous Batch-Supported Send Adapter</span></span>
<span data-ttu-id="f2584-103">メッセージのトランザクション送信が求められた場合、送信アダプターはトランザクションを作成および制御できます。</span><span class="sxs-lookup"><span data-stu-id="f2584-103">A send adapter can create and control transactions when transactional transmission of messages is required.</span></span> <span data-ttu-id="f2584-104">トランザクション送信をサポートするには、アダプターに次のインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2584-104">To support transactional send, an adapter needs to implement the following interfaces:</span></span>  
  
- <span data-ttu-id="f2584-105">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="f2584-105">**IBTTransport**</span></span>  
  
- <span data-ttu-id="f2584-106">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="f2584-106">**IBaseComponent**</span></span>  
  
- <span data-ttu-id="f2584-107">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="f2584-107">**IBTTransportControl**</span></span>  
  
- <span data-ttu-id="f2584-108">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="f2584-108">**IPersistPropertyBag**</span></span>  
  
- <span data-ttu-id="f2584-109">**IBTBatchTransmitter**</span><span class="sxs-lookup"><span data-stu-id="f2584-109">**IBTBatchTransmitter**</span></span>  
  
- <span data-ttu-id="f2584-110">**IBTTransmitterBatch**</span><span class="sxs-lookup"><span data-stu-id="f2584-110">**IBTTransmitterBatch**</span></span>  
  
- <span data-ttu-id="f2584-111">**IBTBatchCallBack**</span><span class="sxs-lookup"><span data-stu-id="f2584-111">**IBTBatchCallBack**</span></span>  
  
  <span data-ttu-id="f2584-112">アダプターは、MSDTC トランザクションを作成しへの呼び出しでは、そのオブジェクトへのポインターを返します、 **BeginBatch**のメソッド、 **IBTTransmitterBatch**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="f2584-112">An adapter creates an MSDTC transaction and returns a pointer to that object in the call to the **BeginBatch** method of the **IBTTransmitterBatch** interface.</span></span> <span data-ttu-id="f2584-113">メッセージング エンジンはこのメソッドを呼び出して、送信メッセージを送信アダプターに送るときに使用するバッチを取得します。</span><span class="sxs-lookup"><span data-stu-id="f2584-113">The Messaging Engine calls this method to obtain a batch with which it posts outgoing messages to the send adapter.</span></span> <span data-ttu-id="f2584-114">使用して、トランザクションの結果をメッセージング エンジンに通知アダプターが送信操作が完了し、コミットまたはトランザクションをロールバック、ときに、 **DTCCommitConfirm**のメソッド、 **IBTDTCCommitConfirm**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="f2584-114">When the adapter finishes the send operation and commits or rolls back a transaction, it notifies the Messaging Engine of the result of the transaction by using the **DTCCommitConfirm** method of the **IBTDTCCommitConfirm** interface.</span></span>  
  
  <span data-ttu-id="f2584-115">トランザクション送信操作を実行した際の、トランスポート プロキシと送信アダプター間の対話処理を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f2584-115">The following figure shows the interaction between the transport proxy and the send adapter when performing a transactional send operation.</span></span>  
  
  <span data-ttu-id="f2584-116">![](../core/media/ebiz-sdk-devadapter8.gif "ebiz_sdk_devadapter8")</span><span class="sxs-lookup"><span data-stu-id="f2584-116">![](../core/media/ebiz-sdk-devadapter8.gif "ebiz_sdk_devadapter8")</span></span>  
  <span data-ttu-id="f2584-117">トランザクション メッセージの非同期送信のワークフロー</span><span class="sxs-lookup"><span data-stu-id="f2584-117">Workflow for sending a transactional message asynchronously</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2584-118">参照</span><span class="sxs-lookup"><span data-stu-id="f2584-118">See Also</span></span>  
 <span data-ttu-id="f2584-119">[アダプター変数](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="f2584-119">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="f2584-120">[送信アダプターの開発](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="f2584-120">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="f2584-121">[インスタンス化し、送信アダプターの初期化](../core/instantiating-and-initializing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="f2584-121">[Instantiating and Initializing a Send Adapter](../core/instantiating-and-initializing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="f2584-122">[送信アダプターの同期用のインターフェイス](../core/interfaces-for-a-synchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="f2584-122">[Interfaces for a Synchronous Send Adapter](../core/interfaces-for-a-synchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="f2584-123">[送信アダプターの非同期インターフェイス](../core/interfaces-for-an-asynchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="f2584-123">[Interfaces for an Asynchronous Send Adapter](../core/interfaces-for-an-asynchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="f2584-124">[同期のバッチでサポートされている送信アダプター用のインターフェイス](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="f2584-124">[Interfaces for a Synchronous Batch-Supported Send Adapter](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="f2584-125">[バッチ処理に対応の非同期送信アダプター用のインターフェイス](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="f2584-125">[Interfaces for an Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span></span>  
 [<span data-ttu-id="f2584-126">送信請求 - 応答送信アダプター用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="f2584-126">Interfaces for a Solicit-Response Send Adapter</span></span>](../core/interfaces-for-a-solicit-response-send-adapter.md)