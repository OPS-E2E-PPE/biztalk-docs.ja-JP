---
title: "送信アダプターのバッチでサポートされている非同期用のインターフェイス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d38b8b87-508a-499b-86b2-846938050b44
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4af0a5c116c19c4cb1fa728cc016144594f42f13
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="interfaces-for-an-asynchronous-batch-supported-send-adapter"></a><span data-ttu-id="d7575-102">バッチ処理に対応した非同期送信アダプター用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="d7575-102">Interfaces for an Asynchronous Batch-Supported Send Adapter</span></span>
<span data-ttu-id="d7575-103">バッチ対応アダプターでは、同期的または非同期的にメッセージを送信し、トランザクション送信を実行できます。</span><span class="sxs-lookup"><span data-stu-id="d7575-103">Batch-aware adapters may send messages synchronously or asynchronously, and may perform transacted sends.</span></span> <span data-ttu-id="d7575-104">メッセージのバッチを送信するには、送信アダプターに次のインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7575-104">To send batches of messages, a send adapter must implement the following interfaces:</span></span>  
  
-   <span data-ttu-id="d7575-105">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="d7575-105">**IBTTransport**</span></span>  
  
-   <span data-ttu-id="d7575-106">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="d7575-106">**IBaseComponent**</span></span>  
  
-   <span data-ttu-id="d7575-107">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="d7575-107">**IBTTransportControl**</span></span>  
  
-   <span data-ttu-id="d7575-108">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="d7575-108">**IPersistPropertyBag**</span></span>  
  
-   <span data-ttu-id="d7575-109">**IBTBatchTransmitter**</span><span class="sxs-lookup"><span data-stu-id="d7575-109">**IBTBatchTransmitter**</span></span>  
  
-   <span data-ttu-id="d7575-110">**IBTTransmitterBatch**</span><span class="sxs-lookup"><span data-stu-id="d7575-110">**IBTTransmitterBatch**</span></span>  
  
 <span data-ttu-id="d7575-111">バッチの非同期送信では、メッセージング エンジンがアダプターからバッチを取得し、そのバッチに送信するメッセージを追加します。</span><span class="sxs-lookup"><span data-stu-id="d7575-111">For the asynchronous batch send, the Messaging Engine gets a batch from the adapter and adds messages to be transmitted to that batch.</span></span> <span data-ttu-id="d7575-112">メッセージング エンジンを呼び出すと、メッセージの送信、**実行**バッチのメソッドです。</span><span class="sxs-lookup"><span data-stu-id="d7575-112">The messages are only sent when the Messaging Engine calls the **Done** method on the batch.</span></span> <span data-ttu-id="d7575-113">アダプターは、非同期送信する各メッセージに対して `False` を返します。</span><span class="sxs-lookup"><span data-stu-id="d7575-113">The adapter returns `False` for each message that it intends to transmit asynchronously.</span></span> <span data-ttu-id="d7575-114">アダプターはアダプターのプロキシからバッチを取得し、正常に送信されたメッセージを削除します。</span><span class="sxs-lookup"><span data-stu-id="d7575-114">The adapter then gets a batch from the adapter proxy and deletes those messages that it successfully transmitted.</span></span>  
  
 <span data-ttu-id="d7575-115">バッチ処理に対応した非同期送信アダプターを作成するときの、オブジェクト間の対話処理を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d7575-115">The following figure shows the object interactions involved in creating an asynchronous batch-supported send adapter.</span></span>  
  
 ![](../core/media/ebiz-sdk-devadapter7.gif "ebiz_sdk_devadapter7")  
<span data-ttu-id="d7575-116">メッセージの非同期送信のワークフロー</span><span class="sxs-lookup"><span data-stu-id="d7575-116">Workflow for sending a message asynchronously</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7575-117">参照</span><span class="sxs-lookup"><span data-stu-id="d7575-117">See Also</span></span>  
 <span data-ttu-id="d7575-118">[アダプタの変数](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="d7575-118">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="d7575-119">[送信アダプターの開発](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="d7575-119">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="d7575-120">[インスタンス化して、送信アダプターの初期化](../core/instantiating-and-initializing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="d7575-120">[Instantiating and Initializing a Send Adapter](../core/instantiating-and-initializing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="d7575-121">[送信アダプターの同期用のインターフェイス](../core/interfaces-for-a-synchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="d7575-121">[Interfaces for a Synchronous Send Adapter](../core/interfaces-for-a-synchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="d7575-122">[送信アダプターの非同期インターフェイス](../core/interfaces-for-an-asynchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="d7575-122">[Interfaces for an Asynchronous Send Adapter](../core/interfaces-for-an-asynchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="d7575-123">[同期のバッチでサポートされている送信アダプター用のインターフェイス](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="d7575-123">[Interfaces for a Synchronous Batch-Supported Send Adapter](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="d7575-124">[バッチでサポートされているトランザクションの非同期送信アダプター用のインターフェイス](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="d7575-124">[Interfaces for a Transactional Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span></span>  
 [<span data-ttu-id="d7575-125">送信アダプターの送信請求-応答のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="d7575-125">Interfaces for a Solicit-Response Send Adapter</span></span>](../core/interfaces-for-a-solicit-response-send-adapter.md)