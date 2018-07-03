---
title: 送信アダプターのバッチ処理に対応する非同期のインターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d38b8b87-508a-499b-86b2-846938050b44
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc579995821a97dc588b2221f8a7dd2e9cd1e136
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993019"
---
# <a name="interfaces-for-an-asynchronous-batch-supported-send-adapter"></a><span data-ttu-id="6fc53-102">バッチ処理に対応した非同期送信アダプター用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="6fc53-102">Interfaces for an Asynchronous Batch-Supported Send Adapter</span></span>
<span data-ttu-id="6fc53-103">バッチ対応アダプターでは、同期的または非同期的にメッセージを送信し、トランザクション送信を実行できます。</span><span class="sxs-lookup"><span data-stu-id="6fc53-103">Batch-aware adapters may send messages synchronously or asynchronously, and may perform transacted sends.</span></span> <span data-ttu-id="6fc53-104">メッセージのバッチを送信するには、送信アダプターに次のインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fc53-104">To send batches of messages, a send adapter must implement the following interfaces:</span></span>  
  
- <span data-ttu-id="6fc53-105">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="6fc53-105">**IBTTransport**</span></span>  
  
- <span data-ttu-id="6fc53-106">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="6fc53-106">**IBaseComponent**</span></span>  
  
- <span data-ttu-id="6fc53-107">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="6fc53-107">**IBTTransportControl**</span></span>  
  
- <span data-ttu-id="6fc53-108">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="6fc53-108">**IPersistPropertyBag**</span></span>  
  
- <span data-ttu-id="6fc53-109">**IBTBatchTransmitter**</span><span class="sxs-lookup"><span data-stu-id="6fc53-109">**IBTBatchTransmitter**</span></span>  
  
- <span data-ttu-id="6fc53-110">**IBTTransmitterBatch**</span><span class="sxs-lookup"><span data-stu-id="6fc53-110">**IBTTransmitterBatch**</span></span>  
  
  <span data-ttu-id="6fc53-111">バッチの非同期送信では、メッセージング エンジンがアダプターからバッチを取得し、そのバッチに送信するメッセージを追加します。</span><span class="sxs-lookup"><span data-stu-id="6fc53-111">For the asynchronous batch send, the Messaging Engine gets a batch from the adapter and adds messages to be transmitted to that batch.</span></span> <span data-ttu-id="6fc53-112">メッセージング エンジンを呼び出すと、メッセージの送信、**完了**batch でのメソッド。</span><span class="sxs-lookup"><span data-stu-id="6fc53-112">The messages are only sent when the Messaging Engine calls the **Done** method on the batch.</span></span> <span data-ttu-id="6fc53-113">アダプターは、非同期送信する各メッセージに対して `False` を返します。</span><span class="sxs-lookup"><span data-stu-id="6fc53-113">The adapter returns `False` for each message that it intends to transmit asynchronously.</span></span> <span data-ttu-id="6fc53-114">アダプターはアダプターのプロキシからバッチを取得し、正常に送信されたメッセージを削除します。</span><span class="sxs-lookup"><span data-stu-id="6fc53-114">The adapter then gets a batch from the adapter proxy and deletes those messages that it successfully transmitted.</span></span>  
  
  <span data-ttu-id="6fc53-115">バッチ処理に対応した非同期送信アダプターを作成するときの、オブジェクト間の対話処理を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6fc53-115">The following figure shows the object interactions involved in creating an asynchronous batch-supported send adapter.</span></span>  
  
  <span data-ttu-id="6fc53-116">![](../core/media/ebiz-sdk-devadapter7.gif "ebiz_sdk_devadapter7")</span><span class="sxs-lookup"><span data-stu-id="6fc53-116">![](../core/media/ebiz-sdk-devadapter7.gif "ebiz_sdk_devadapter7")</span></span>  
  <span data-ttu-id="6fc53-117">メッセージの非同期送信のワークフロー</span><span class="sxs-lookup"><span data-stu-id="6fc53-117">Workflow for sending a message asynchronously</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fc53-118">参照</span><span class="sxs-lookup"><span data-stu-id="6fc53-118">See Also</span></span>  
 <span data-ttu-id="6fc53-119">[アダプター変数](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="6fc53-119">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="6fc53-120">[送信アダプターの開発](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="6fc53-120">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="6fc53-121">[インスタンス化し、送信アダプターの初期化](../core/instantiating-and-initializing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="6fc53-121">[Instantiating and Initializing a Send Adapter](../core/instantiating-and-initializing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="6fc53-122">[送信アダプターの同期用のインターフェイス](../core/interfaces-for-a-synchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="6fc53-122">[Interfaces for a Synchronous Send Adapter](../core/interfaces-for-a-synchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="6fc53-123">[送信アダプターの非同期インターフェイス](../core/interfaces-for-an-asynchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="6fc53-123">[Interfaces for an Asynchronous Send Adapter](../core/interfaces-for-an-asynchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="6fc53-124">[同期のバッチでサポートされている送信アダプター用のインターフェイス](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="6fc53-124">[Interfaces for a Synchronous Batch-Supported Send Adapter](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="6fc53-125">[Batch でサポートされているトランザクションの非同期送信アダプター用のインターフェイス](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="6fc53-125">[Interfaces for a Transactional Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span></span>  
 [<span data-ttu-id="6fc53-126">送信請求 - 応答送信アダプター用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="6fc53-126">Interfaces for a Solicit-Response Send Adapter</span></span>](../core/interfaces-for-a-solicit-response-send-adapter.md)