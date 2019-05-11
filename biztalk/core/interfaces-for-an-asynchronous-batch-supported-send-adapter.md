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
ms.openlocfilehash: 07890cb81bb76a665f98d7f489b4775c01f436b3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381798"
---
# <a name="interfaces-for-an-asynchronous-batch-supported-send-adapter"></a><span data-ttu-id="7092c-102">バッチ処理に対応の非同期送信アダプター用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="7092c-102">Interfaces for an Asynchronous Batch-Supported Send Adapter</span></span>
<span data-ttu-id="7092c-103">バッチ対応アダプターでは、同期または非同期にメッセージを送信し、トランザクション送信を実行することがあります。</span><span class="sxs-lookup"><span data-stu-id="7092c-103">Batch-aware adapters may send messages synchronously or asynchronously, and may perform transacted sends.</span></span> <span data-ttu-id="7092c-104">メッセージのバッチを送信するには、送信アダプターは、次のインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7092c-104">To send batches of messages, a send adapter must implement the following interfaces:</span></span>  
  
- <span data-ttu-id="7092c-105">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="7092c-105">**IBTTransport**</span></span>  
  
- <span data-ttu-id="7092c-106">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="7092c-106">**IBaseComponent**</span></span>  
  
- <span data-ttu-id="7092c-107">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="7092c-107">**IBTTransportControl**</span></span>  
  
- <span data-ttu-id="7092c-108">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="7092c-108">**IPersistPropertyBag**</span></span>  
  
- <span data-ttu-id="7092c-109">**IBTBatchTransmitter**</span><span class="sxs-lookup"><span data-stu-id="7092c-109">**IBTBatchTransmitter**</span></span>  
  
- <span data-ttu-id="7092c-110">**IBTTransmitterBatch**</span><span class="sxs-lookup"><span data-stu-id="7092c-110">**IBTTransmitterBatch**</span></span>  
  
  <span data-ttu-id="7092c-111">非同期バッチ送信では、メッセージング エンジンがアダプターからバッチを取得し、そのバッチに送信するメッセージを追加します。</span><span class="sxs-lookup"><span data-stu-id="7092c-111">For the asynchronous batch send, the Messaging Engine gets a batch from the adapter and adds messages to be transmitted to that batch.</span></span> <span data-ttu-id="7092c-112">メッセージング エンジンを呼び出すと、メッセージの送信、**完了**batch でのメソッド。</span><span class="sxs-lookup"><span data-stu-id="7092c-112">The messages are only sent when the Messaging Engine calls the **Done** method on the batch.</span></span> <span data-ttu-id="7092c-113">アダプターは返します`False`非同期的に送信するメッセージごとにします。</span><span class="sxs-lookup"><span data-stu-id="7092c-113">The adapter returns `False` for each message that it intends to transmit asynchronously.</span></span> <span data-ttu-id="7092c-114">アダプターは、アダプターのプロキシからバッチを取得し、正常に送信されたメッセージを削除します。</span><span class="sxs-lookup"><span data-stu-id="7092c-114">The adapter then gets a batch from the adapter proxy and deletes those messages that it successfully transmitted.</span></span>  
  
  <span data-ttu-id="7092c-115">次の図は、送信アダプターのバッチでサポートされている非同期作成に関連するオブジェクトの相互作用を示しています。</span><span class="sxs-lookup"><span data-stu-id="7092c-115">The following figure shows the object interactions involved in creating an asynchronous batch-supported send adapter.</span></span>  
  
  <span data-ttu-id="7092c-116">![](../core/media/ebiz-sdk-devadapter7.gif "ebiz_sdk_devadapter7")</span><span class="sxs-lookup"><span data-stu-id="7092c-116">![](../core/media/ebiz-sdk-devadapter7.gif "ebiz_sdk_devadapter7")</span></span>  
  <span data-ttu-id="7092c-117">非同期的にメッセージを送信するためのワークフロー</span><span class="sxs-lookup"><span data-stu-id="7092c-117">Workflow for sending a message asynchronously</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7092c-118">参照</span><span class="sxs-lookup"><span data-stu-id="7092c-118">See Also</span></span>  
 <span data-ttu-id="7092c-119">[アダプター変数](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="7092c-119">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="7092c-120">[送信アダプターの開発](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="7092c-120">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="7092c-121">[インスタンス化し、送信アダプターの初期化](../core/instantiating-and-initializing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="7092c-121">[Instantiating and Initializing a Send Adapter](../core/instantiating-and-initializing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="7092c-122">[送信アダプターの同期用のインターフェイス](../core/interfaces-for-a-synchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="7092c-122">[Interfaces for a Synchronous Send Adapter](../core/interfaces-for-a-synchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="7092c-123">[送信アダプターの非同期インターフェイス](../core/interfaces-for-an-asynchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="7092c-123">[Interfaces for an Asynchronous Send Adapter](../core/interfaces-for-an-asynchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="7092c-124">[同期のバッチでサポートされている送信アダプター用のインターフェイス](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="7092c-124">[Interfaces for a Synchronous Batch-Supported Send Adapter](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="7092c-125">[Batch でサポートされているトランザクションの非同期送信アダプター用のインターフェイス](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="7092c-125">[Interfaces for a Transactional Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span></span>  
 [<span data-ttu-id="7092c-126">送信請求 - 応答送信アダプター用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="7092c-126">Interfaces for a Solicit-Response Send Adapter</span></span>](../core/interfaces-for-a-solicit-response-send-adapter.md)