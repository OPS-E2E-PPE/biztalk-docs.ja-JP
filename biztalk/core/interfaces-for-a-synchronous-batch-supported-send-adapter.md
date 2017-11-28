---
title: "送信アダプターのバッチでサポートされている同期用のインターフェイス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2b191c41-ca4f-4d2b-bd15-a93ad87a743d
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ab61fd6624468e0464cfe0c648fcc868bd20005
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="interfaces-for-a-synchronous-batch-supported-send-adapter"></a><span data-ttu-id="b5cd8-102">バッチ処理に対応した同期送信アダプター用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="b5cd8-102">Interfaces for a Synchronous Batch-Supported Send Adapter</span></span>
<span data-ttu-id="b5cd8-103">バッチ対応アダプターでは、同期的または非同期的にメッセージを送信し、トランザクション送信操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="b5cd8-103">Batch-aware adapters may send messages synchronously or asynchronously, and may perform transacted send operations.</span></span> <span data-ttu-id="b5cd8-104">メッセージのバッチを送信するには、送信アダプターに次のインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5cd8-104">To send batches of messages, a send adapter must implement the following interfaces:</span></span>  
  
-   <span data-ttu-id="b5cd8-105">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="b5cd8-105">**IBTTransport**</span></span>  
  
-   <span data-ttu-id="b5cd8-106">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="b5cd8-106">**IBaseComponent**</span></span>  
  
-   <span data-ttu-id="b5cd8-107">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="b5cd8-107">**IBTTransportControl**</span></span>  
  
-   <span data-ttu-id="b5cd8-108">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="b5cd8-108">**IPersistPropertyBag**</span></span>  
  
-   <span data-ttu-id="b5cd8-109">**IBTBatchTransmitter**</span><span class="sxs-lookup"><span data-stu-id="b5cd8-109">**IBTBatchTransmitter**</span></span>  
  
-   <span data-ttu-id="b5cd8-110">**IBTTransmitterBatch**</span><span class="sxs-lookup"><span data-stu-id="b5cd8-110">**IBTTransmitterBatch**</span></span>  
  
 <span data-ttu-id="b5cd8-111">バッチの同期送信では、メッセージング エンジンがアダプターからバッチを取得し、そのバッチに送信するメッセージを追加します。</span><span class="sxs-lookup"><span data-stu-id="b5cd8-111">For the synchronous batch send, the Messaging Engine gets a batch from the adapter and adds messages to be transmitted to that batch.</span></span> <span data-ttu-id="b5cd8-112">メッセージング エンジンは、各メッセージのバッチを追加しを呼び出すときにのみ、メッセージを送信、**完了**バッチのメソッドです。</span><span class="sxs-lookup"><span data-stu-id="b5cd8-112">The Messaging Engine adds each message to the batch and sends the messages only when it calls the **Done** method on the batch.</span></span> <span data-ttu-id="b5cd8-113">アダプターを返します`True`の**bDeleteMessage**同期的に送信する各メッセージにします。</span><span class="sxs-lookup"><span data-stu-id="b5cd8-113">The adapter returns `True` for **bDeleteMessage** for each message that it intends to transmit synchronously.</span></span> <span data-ttu-id="b5cd8-114">アダプターは、メッセージ ポインターではなく、メッセージ データに保存してその**TransmitMessage**実装します。</span><span class="sxs-lookup"><span data-stu-id="b5cd8-114">The adapter should save message data, as opposed to a message pointer, in its **TransmitMessage** implementation.</span></span> <span data-ttu-id="b5cd8-115">この理由は、`True` が返されるとメッセージ ポインターは無効になり、使用できなくなるか、後で使用するためにキャッシュできなくなるためです。</span><span class="sxs-lookup"><span data-stu-id="b5cd8-115">This is because the message pointer is no longer valid after `True` is returned, and should not be used or cached for later use.</span></span>  
  
 <span data-ttu-id="b5cd8-116">バッチ処理に対応した同期送信アダプターを作成するときの、オブジェクト間の対話処理を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b5cd8-116">The following figure shows the object interactions involved in creating a synchronous batch-supported send adapter.</span></span>  
  
 ![](../core/media/ebiz-sdk-devadapter6.gif "ebiz_sdk_devadapter6")  
<span data-ttu-id="b5cd8-117">メッセージの同期送信のワークフロー</span><span class="sxs-lookup"><span data-stu-id="b5cd8-117">Workflow for submitting a message synchronously</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5cd8-118">参照</span><span class="sxs-lookup"><span data-stu-id="b5cd8-118">See Also</span></span>  
 <span data-ttu-id="b5cd8-119">[アダプタの変数](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="b5cd8-119">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="b5cd8-120">[送信アダプターの開発](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="b5cd8-120">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="b5cd8-121">[インスタンス化して、送信アダプターの初期化](../core/instantiating-and-initializing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="b5cd8-121">[Instantiating and Initializing a Send Adapter](../core/instantiating-and-initializing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="b5cd8-122">[送信アダプターの同期用のインターフェイス](../core/interfaces-for-a-synchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="b5cd8-122">[Interfaces for a Synchronous Send Adapter](../core/interfaces-for-a-synchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="b5cd8-123">[送信アダプターの非同期インターフェイス](../core/interfaces-for-an-asynchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="b5cd8-123">[Interfaces for an Asynchronous Send Adapter](../core/interfaces-for-an-asynchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="b5cd8-124">[サポートされるバッチの非同期送信アダプター用のインターフェイス](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="b5cd8-124">[Interfaces for an Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="b5cd8-125">[バッチでサポートされているトランザクションの非同期送信アダプター用のインターフェイス](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="b5cd8-125">[Interfaces for a Transactional Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span></span>  
 [<span data-ttu-id="b5cd8-126">送信アダプターの送信請求-応答のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="b5cd8-126">Interfaces for a Solicit-Response Send Adapter</span></span>](../core/interfaces-for-a-solicit-response-send-adapter.md)