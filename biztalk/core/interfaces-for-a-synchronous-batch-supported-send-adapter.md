---
title: 送信アダプターのバッチ処理に対応する同期用のインターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b191c41-ca4f-4d2b-bd15-a93ad87a743d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 091b735604a0b38044498f712de63ad9eac1c057
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331609"
---
# <a name="interfaces-for-a-synchronous-batch-supported-send-adapter"></a><span data-ttu-id="3f092-102">同期のバッチでサポートされている送信アダプター用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="3f092-102">Interfaces for a Synchronous Batch-Supported Send Adapter</span></span>
<span data-ttu-id="3f092-103">バッチ対応アダプターでは、同期または非同期にメッセージを送信し、トランザクション送信操作を実行することがあります。</span><span class="sxs-lookup"><span data-stu-id="3f092-103">Batch-aware adapters may send messages synchronously or asynchronously, and may perform transacted send operations.</span></span> <span data-ttu-id="3f092-104">メッセージのバッチを送信するには、送信アダプターは、次のインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f092-104">To send batches of messages, a send adapter must implement the following interfaces:</span></span>  
  
- <span data-ttu-id="3f092-105">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="3f092-105">**IBTTransport**</span></span>  
  
- <span data-ttu-id="3f092-106">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="3f092-106">**IBaseComponent**</span></span>  
  
- <span data-ttu-id="3f092-107">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="3f092-107">**IBTTransportControl**</span></span>  
  
- <span data-ttu-id="3f092-108">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="3f092-108">**IPersistPropertyBag**</span></span>  
  
- <span data-ttu-id="3f092-109">**IBTBatchTransmitter**</span><span class="sxs-lookup"><span data-stu-id="3f092-109">**IBTBatchTransmitter**</span></span>  
  
- <span data-ttu-id="3f092-110">**IBTTransmitterBatch**</span><span class="sxs-lookup"><span data-stu-id="3f092-110">**IBTTransmitterBatch**</span></span>  
  
  <span data-ttu-id="3f092-111">同期バッチの送信では、メッセージング エンジンがアダプターからバッチを取得し、そのバッチに送信するメッセージを追加します。</span><span class="sxs-lookup"><span data-stu-id="3f092-111">For the synchronous batch send, the Messaging Engine gets a batch from the adapter and adds messages to be transmitted to that batch.</span></span> <span data-ttu-id="3f092-112">メッセージング エンジンは、各メッセージをバッチに追加およびを呼び出すときにのみ、メッセージを送信します、**完了**batch でのメソッド。</span><span class="sxs-lookup"><span data-stu-id="3f092-112">The Messaging Engine adds each message to the batch and sends the messages only when it calls the **Done** method on the batch.</span></span> <span data-ttu-id="3f092-113">アダプターは返します`True`の**bDeleteMessage**同期的に送信するメッセージごとにします。</span><span class="sxs-lookup"><span data-stu-id="3f092-113">The adapter returns `True` for **bDeleteMessage** for each message that it intends to transmit synchronously.</span></span> <span data-ttu-id="3f092-114">アダプターで、メッセージ ポインターではなく、メッセージ データを保存する必要があります、 **TransmitMessage**実装します。</span><span class="sxs-lookup"><span data-stu-id="3f092-114">The adapter should save message data, as opposed to a message pointer, in its **TransmitMessage** implementation.</span></span> <span data-ttu-id="3f092-115">これは、メッセージ ポインターが後に無効になっているため`True`が返されますとを使用せず、後で使用するためにキャッシュします。</span><span class="sxs-lookup"><span data-stu-id="3f092-115">This is because the message pointer is no longer valid after `True` is returned, and should not be used or cached for later use.</span></span>  
  
  <span data-ttu-id="3f092-116">次の図は、送信アダプターのバッチでサポートされている同期の作成に関連するオブジェクトの相互作用を示しています。</span><span class="sxs-lookup"><span data-stu-id="3f092-116">The following figure shows the object interactions involved in creating a synchronous batch-supported send adapter.</span></span>  
  
  <span data-ttu-id="3f092-117">![](../core/media/ebiz-sdk-devadapter6.gif "ebiz_sdk_devadapter6")</span><span class="sxs-lookup"><span data-stu-id="3f092-117">![](../core/media/ebiz-sdk-devadapter6.gif "ebiz_sdk_devadapter6")</span></span>  
  <span data-ttu-id="3f092-118">同期的にメッセージを送信するためのワークフロー</span><span class="sxs-lookup"><span data-stu-id="3f092-118">Workflow for submitting a message synchronously</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f092-119">参照</span><span class="sxs-lookup"><span data-stu-id="3f092-119">See Also</span></span>  
 <span data-ttu-id="3f092-120">[アダプター変数](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="3f092-120">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="3f092-121">[送信アダプターの開発](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="3f092-121">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="3f092-122">[インスタンス化し、送信アダプターの初期化](../core/instantiating-and-initializing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="3f092-122">[Instantiating and Initializing a Send Adapter](../core/instantiating-and-initializing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="3f092-123">[送信アダプターの同期用のインターフェイス](../core/interfaces-for-a-synchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="3f092-123">[Interfaces for a Synchronous Send Adapter](../core/interfaces-for-a-synchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="3f092-124">[送信アダプターの非同期インターフェイス](../core/interfaces-for-an-asynchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="3f092-124">[Interfaces for an Asynchronous Send Adapter](../core/interfaces-for-an-asynchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="3f092-125">[バッチ処理に対応の非同期送信アダプター用のインターフェイス](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="3f092-125">[Interfaces for an Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="3f092-126">[Batch でサポートされているトランザクションの非同期送信アダプター用のインターフェイス](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="3f092-126">[Interfaces for a Transactional Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span></span>  
 [<span data-ttu-id="3f092-127">送信請求 - 応答送信アダプター用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="3f092-127">Interfaces for a Solicit-Response Send Adapter</span></span>](../core/interfaces-for-a-solicit-response-send-adapter.md)