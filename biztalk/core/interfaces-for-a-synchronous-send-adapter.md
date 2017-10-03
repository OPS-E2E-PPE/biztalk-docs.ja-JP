---
title: "送信アダプターの同期用のインターフェイス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e1b397a-3a35-4447-8522-d8a5f39a42d7
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1012b52bf5c6ab564cc219926b97445e43f60dd1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="interfaces-for-a-synchronous-send-adapter"></a><span data-ttu-id="4bfff-102">同期送信アダプター用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="4bfff-102">Interfaces for a Synchronous Send Adapter</span></span>
<span data-ttu-id="4bfff-103">アダプターは、受信メッセージング エンジンの呼び出し元スレッドをブロックするときに、送信操作を実行しながらメッセージを同期的に送信します。</span><span class="sxs-lookup"><span data-stu-id="4bfff-103">An adapter sends messages synchronously when it blocks the incoming Messaging Engine calling thread while performing its send operation.</span></span> <span data-ttu-id="4bfff-104">メッセージを同期的に送信できるようにするには、アダプターに次のインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bfff-104">To be able to send messages synchronously, an adapter needs to implement the following interfaces:</span></span>  
  
-   <span data-ttu-id="4bfff-105">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="4bfff-105">**IBTTransport**</span></span>  
  
-   <span data-ttu-id="4bfff-106">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="4bfff-106">**IBaseComponent**</span></span>  
  
-   <span data-ttu-id="4bfff-107">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="4bfff-107">**IBTTransportControl**</span></span>  
  
-   <span data-ttu-id="4bfff-108">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="4bfff-108">**IPersistPropertyBag**</span></span>  
  
-   <span data-ttu-id="4bfff-109">**IBTTransmitter**</span><span class="sxs-lookup"><span data-stu-id="4bfff-109">**IBTTransmitter**</span></span>  
  
 <span data-ttu-id="4bfff-110">同期送信アダプターがブロックしているときにメッセージを送信**TransmitMessage**、返された転送が成功した後、`True.`</span><span class="sxs-lookup"><span data-stu-id="4bfff-110">In a synchronous send, the adapter sends the message while blocking **TransmitMessage**, and after successful transmission returns `True.`</span></span>  
  
 <span data-ttu-id="4bfff-111">同期送信アダプターを作成するときの、オブジェクト間の対話処理を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4bfff-111">The following figure shows the object interactions involved in creating a synchronous send adapter.</span></span>  
  
 ![](../core/media/ebiz-sdk-devadapter4.gif "ebiz_sdk_devadapter4")  
<span data-ttu-id="4bfff-112">メッセージを同期的に送信するためのワークフロー</span><span class="sxs-lookup"><span data-stu-id="4bfff-112">Workflow for sending a message synchronously</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bfff-113">参照</span><span class="sxs-lookup"><span data-stu-id="4bfff-113">See Also</span></span>  
 <span data-ttu-id="4bfff-114">[アダプタの変数](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="4bfff-114">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="4bfff-115">[送信アダプターの開発](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="4bfff-115">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="4bfff-116">[インスタンス化して、送信アダプターの初期化](../core/instantiating-and-initializing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="4bfff-116">[Instantiating and Initializing a Send Adapter](../core/instantiating-and-initializing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="4bfff-117">[送信アダプターの非同期インターフェイス](../core/interfaces-for-an-asynchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="4bfff-117">[Interfaces for an Asynchronous Send Adapter](../core/interfaces-for-an-asynchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="4bfff-118">[同期のバッチでサポートされている送信アダプター用のインターフェイス](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="4bfff-118">[Interfaces for a Synchronous Batch-Supported Send Adapter](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="4bfff-119">[サポートされるバッチの非同期送信アダプター用のインターフェイス](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="4bfff-119">[Interfaces for an Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="4bfff-120">[バッチでサポートされているトランザクションの非同期送信アダプター用のインターフェイス](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="4bfff-120">[Interfaces for a Transactional Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md) </span></span>  
 [<span data-ttu-id="4bfff-121">送信アダプターの送信請求-応答のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="4bfff-121">Interfaces for a Solicit-Response Send Adapter</span></span>](../core/interfaces-for-a-solicit-response-send-adapter.md)