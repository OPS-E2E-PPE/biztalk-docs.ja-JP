---
title: 送信アダプターの同期用のインターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e1b397a-3a35-4447-8522-d8a5f39a42d7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1602d19bc5b97231a25f5449f5837fce153c037d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008843"
---
# <a name="interfaces-for-a-synchronous-send-adapter"></a><span data-ttu-id="d60c2-102">同期送信アダプター用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="d60c2-102">Interfaces for a Synchronous Send Adapter</span></span>
<span data-ttu-id="d60c2-103">アダプターは、受信メッセージング エンジンの呼び出し元スレッドをブロックするときに、送信操作を実行しながらメッセージを同期的に送信します。</span><span class="sxs-lookup"><span data-stu-id="d60c2-103">An adapter sends messages synchronously when it blocks the incoming Messaging Engine calling thread while performing its send operation.</span></span> <span data-ttu-id="d60c2-104">メッセージを同期的に送信できるようにするには、アダプターに次のインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d60c2-104">To be able to send messages synchronously, an adapter needs to implement the following interfaces:</span></span>  
  
- <span data-ttu-id="d60c2-105">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="d60c2-105">**IBTTransport**</span></span>  
  
- <span data-ttu-id="d60c2-106">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="d60c2-106">**IBaseComponent**</span></span>  
  
- <span data-ttu-id="d60c2-107">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="d60c2-107">**IBTTransportControl**</span></span>  
  
- <span data-ttu-id="d60c2-108">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="d60c2-108">**IPersistPropertyBag**</span></span>  
  
- <span data-ttu-id="d60c2-109">**IBTTransmitter**</span><span class="sxs-lookup"><span data-stu-id="d60c2-109">**IBTTransmitter**</span></span>  
  
  <span data-ttu-id="d60c2-110">同期送信の場合は、アダプターは、ブロック メッセージを送信**TransmitMessage**転送が成功したが返した後、 `True.`</span><span class="sxs-lookup"><span data-stu-id="d60c2-110">In a synchronous send, the adapter sends the message while blocking **TransmitMessage**, and after successful transmission returns `True.`</span></span>  
  
  <span data-ttu-id="d60c2-111">同期送信アダプターを作成するときの、オブジェクト間の対話処理を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d60c2-111">The following figure shows the object interactions involved in creating a synchronous send adapter.</span></span>  
  
  <span data-ttu-id="d60c2-112">![](../core/media/ebiz-sdk-devadapter4.gif "ebiz_sdk_devadapter4")</span><span class="sxs-lookup"><span data-stu-id="d60c2-112">![](../core/media/ebiz-sdk-devadapter4.gif "ebiz_sdk_devadapter4")</span></span>  
  <span data-ttu-id="d60c2-113">同期的にメッセージを送信するためのワークフロー</span><span class="sxs-lookup"><span data-stu-id="d60c2-113">Workflow for sending a message synchronously</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d60c2-114">参照</span><span class="sxs-lookup"><span data-stu-id="d60c2-114">See Also</span></span>  
 <span data-ttu-id="d60c2-115">[アダプター変数](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="d60c2-115">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="d60c2-116">[送信アダプターの開発](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="d60c2-116">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="d60c2-117">[インスタンス化し、送信アダプターの初期化](../core/instantiating-and-initializing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="d60c2-117">[Instantiating and Initializing a Send Adapter](../core/instantiating-and-initializing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="d60c2-118">[送信アダプターの非同期インターフェイス](../core/interfaces-for-an-asynchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="d60c2-118">[Interfaces for an Asynchronous Send Adapter](../core/interfaces-for-an-asynchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="d60c2-119">[同期のバッチでサポートされている送信アダプター用のインターフェイス](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="d60c2-119">[Interfaces for a Synchronous Batch-Supported Send Adapter](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="d60c2-120">[バッチ処理に対応の非同期送信アダプター用のインターフェイス](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="d60c2-120">[Interfaces for an Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="d60c2-121">[Batch でサポートされているトランザクションの非同期送信アダプター用のインターフェイス](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="d60c2-121">[Interfaces for a Transactional Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span></span>  
 [<span data-ttu-id="d60c2-122">送信請求 - 応答送信アダプター用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="d60c2-122">Interfaces for a Solicit-Response Send Adapter</span></span>](../core/interfaces-for-a-solicit-response-send-adapter.md)