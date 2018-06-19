---
title: バッチでサポートされているトランザクションの非同期送信アダプター用のインターフェイス |Microsoft ドキュメント
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
ms.openlocfilehash: 948000883c092c8e247b1d4f41fb2bc7e2280e40
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257714"
---
# <a name="interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter"></a><span data-ttu-id="cfabc-102">バッチ処理に対応したトランザクションとしての非同期送信アダプター用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="cfabc-102">Interfaces for a Transactional Asynchronous Batch-Supported Send Adapter</span></span>
<span data-ttu-id="cfabc-103">メッセージのトランザクション送信が求められた場合、送信アダプターはトランザクションを作成および制御できます。</span><span class="sxs-lookup"><span data-stu-id="cfabc-103">A send adapter can create and control transactions when transactional transmission of messages is required.</span></span> <span data-ttu-id="cfabc-104">トランザクション送信をサポートするには、アダプターに次のインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfabc-104">To support transactional send, an adapter needs to implement the following interfaces:</span></span>  
  
-   <span data-ttu-id="cfabc-105">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="cfabc-105">**IBTTransport**</span></span>  
  
-   <span data-ttu-id="cfabc-106">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="cfabc-106">**IBaseComponent**</span></span>  
  
-   <span data-ttu-id="cfabc-107">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="cfabc-107">**IBTTransportControl**</span></span>  
  
-   <span data-ttu-id="cfabc-108">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="cfabc-108">**IPersistPropertyBag**</span></span>  
  
-   <span data-ttu-id="cfabc-109">**IBTBatchTransmitter**</span><span class="sxs-lookup"><span data-stu-id="cfabc-109">**IBTBatchTransmitter**</span></span>  
  
-   <span data-ttu-id="cfabc-110">**IBTTransmitterBatch**</span><span class="sxs-lookup"><span data-stu-id="cfabc-110">**IBTTransmitterBatch**</span></span>  
  
-   <span data-ttu-id="cfabc-111">**IBTBatchCallBack**</span><span class="sxs-lookup"><span data-stu-id="cfabc-111">**IBTBatchCallBack**</span></span>  
  
 <span data-ttu-id="cfabc-112">アダプターは MSDTC トランザクションを作成し、呼び出しでは、そのオブジェクトへのポインターを返します、 **BeginBatch**のメソッド、 **IBTTransmitterBatch**インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="cfabc-112">An adapter creates an MSDTC transaction and returns a pointer to that object in the call to the **BeginBatch** method of the **IBTTransmitterBatch** interface.</span></span> <span data-ttu-id="cfabc-113">メッセージング エンジンはこのメソッドを呼び出して、送信メッセージを送信アダプターに送るときに使用するバッチを取得します。</span><span class="sxs-lookup"><span data-stu-id="cfabc-113">The Messaging Engine calls this method to obtain a batch with which it posts outgoing messages to the send adapter.</span></span> <span data-ttu-id="cfabc-114">使用して、トランザクションの結果のメッセージング エンジンに通知、アダプターでは、送信操作が完了すると、コミットまたはとトランザクションをロールバック、ときに、 **DTCCommitConfirm**のメソッド、 **IBTDTCCommitConfirm**インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="cfabc-114">When the adapter finishes the send operation and commits or rolls back a transaction, it notifies the Messaging Engine of the result of the transaction by using the **DTCCommitConfirm** method of the **IBTDTCCommitConfirm** interface.</span></span>  
  
 <span data-ttu-id="cfabc-115">トランザクション送信操作を実行した際の、トランスポート プロキシと送信アダプター間の対話処理を次に示します。</span><span class="sxs-lookup"><span data-stu-id="cfabc-115">The following figure shows the interaction between the transport proxy and the send adapter when performing a transactional send operation.</span></span>  
  
 ![](../core/media/ebiz-sdk-devadapter8.gif "ebiz_sdk_devadapter8")  
<span data-ttu-id="cfabc-116">トランザクション メッセージの非同期送信のワークフロー</span><span class="sxs-lookup"><span data-stu-id="cfabc-116">Workflow for sending a transactional message asynchronously</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfabc-117">参照</span><span class="sxs-lookup"><span data-stu-id="cfabc-117">See Also</span></span>  
 <span data-ttu-id="cfabc-118">[アダプタの変数](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="cfabc-118">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="cfabc-119">[送信アダプターの開発](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="cfabc-119">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="cfabc-120">[インスタンス化して、送信アダプターの初期化](../core/instantiating-and-initializing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="cfabc-120">[Instantiating and Initializing a Send Adapter](../core/instantiating-and-initializing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="cfabc-121">[送信アダプターの同期用のインターフェイス](../core/interfaces-for-a-synchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="cfabc-121">[Interfaces for a Synchronous Send Adapter](../core/interfaces-for-a-synchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="cfabc-122">[送信アダプターの非同期インターフェイス](../core/interfaces-for-an-asynchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="cfabc-122">[Interfaces for an Asynchronous Send Adapter](../core/interfaces-for-an-asynchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="cfabc-123">[同期のバッチでサポートされている送信アダプター用のインターフェイス](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="cfabc-123">[Interfaces for a Synchronous Batch-Supported Send Adapter](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="cfabc-124">[サポートされるバッチの非同期送信アダプター用のインターフェイス](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="cfabc-124">[Interfaces for an Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span></span>  
 [<span data-ttu-id="cfabc-125">送信アダプターの送信請求-応答のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="cfabc-125">Interfaces for a Solicit-Response Send Adapter</span></span>](../core/interfaces-for-a-solicit-response-send-adapter.md)