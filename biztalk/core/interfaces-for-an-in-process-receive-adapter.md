---
title: "受信アダプターをインプロセスで用のインターフェイス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4ed668d9-7512-4026-a8f3-df05aeed4df6
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7135471700cf640f61b56506ad159b5c47c7d877
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="interfaces-for-an-in-process-receive-adapter"></a><span data-ttu-id="4cc55-102">インプロセス受信アダプター用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="4cc55-102">Interfaces for an In-Process Receive Adapter</span></span>
<span data-ttu-id="4cc55-103">メッセージング エンジンは、インプロセス アダプターをインスタンス化して構成し、トランスポート プロキシに渡して、アダプターがその機能にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="4cc55-103">The Messaging Engine instantiates and configures in-process adapters, passing in the transport proxy to allow the adapter to access its functionality.</span></span> <span data-ttu-id="4cc55-104">構成およびトランスポート プロキシへのバインドを有効にするには、アダプターに次の構成インターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cc55-104">To enable configuration and binding to the transport proxy, adapters must implement the following configuration interfaces:</span></span>  
  
-   <span data-ttu-id="4cc55-105">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="4cc55-105">**IBTTransport**</span></span>  
  
-   <span data-ttu-id="4cc55-106">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="4cc55-106">**IBTTransportControl**</span></span>  
  
-   <span data-ttu-id="4cc55-107">**IBTTransportConfig**</span><span class="sxs-lookup"><span data-stu-id="4cc55-107">**IBTTransportConfig**</span></span>  
  
-   <span data-ttu-id="4cc55-108">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="4cc55-108">**IBaseComponent**</span></span>  
  
 <span data-ttu-id="4cc55-109">必要に応じて、アダプターが初期化中にハンドラー情報を受信する場合に必要な実装**IPersistPropertyBag**です。</span><span class="sxs-lookup"><span data-stu-id="4cc55-109">Optionally if the adapter wants to receive handler information during initialization it needs to implement **IPersistPropertyBag**.</span></span>  
  
 <span data-ttu-id="4cc55-110">メッセージング エンジンは、アダプターのインスタンスを作成し、初期化して、受信場所の構成を設定します。</span><span class="sxs-lookup"><span data-stu-id="4cc55-110">The Messaging Engine creates an instance of an adapter, initializes it, and sets the configuration of receive locations.</span></span> <span data-ttu-id="4cc55-111">メッセージング エンジンが上のアダプターにプロパティ バッグを渡します、 **AddReceiveEndpoint**メソッドの呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="4cc55-111">The Messaging Engine passes a property bag to an adapter on the **AddReceiveEndpoint** method call.</span></span> <span data-ttu-id="4cc55-112">プロパティ バッグには、受信場所と受信ハンドラーの構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4cc55-112">The property bag contains the configuration for the receive location and receive handler.</span></span> <span data-ttu-id="4cc55-113">構成は、XML スタイルのプロパティ バッグの形式で、データベースに格納されます。</span><span class="sxs-lookup"><span data-stu-id="4cc55-113">The configuration is stored in the database in the form of an XML-styled property bag.</span></span> <span data-ttu-id="4cc55-114">メッセージング エンジンは、XML を読み取り、XML からプロパティ バッグを復元します。</span><span class="sxs-lookup"><span data-stu-id="4cc55-114">The Messaging Engine reads the XML and rehydrates a property bag from the XML.</span></span> <span data-ttu-id="4cc55-115">少なくとも 1 つのエンドポイント (受信場所) が追加されたら、アダプターはメッセージの送信を開始できます。</span><span class="sxs-lookup"><span data-stu-id="4cc55-115">After at least one endpoint (receive location) is added, the adapter can start submitting messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4cc55-116">アダプターがメッセージング エンジンなどの呼び出しはブロックされません**IBTTransportControl.Initialize**、 **IPersistPropertyBag.Load**、および**IBTTransportConfig.AddReceiveEndpoint**.</span><span class="sxs-lookup"><span data-stu-id="4cc55-116">Adapters should not block Messaging Engine calls such as **IBTTransportControl.Initialize**, **IPersistPropertyBag.Load**, and **IBTTransportConfig.AddReceiveEndpoint**.</span></span> <span data-ttu-id="4cc55-117">過剰なこれらの呼び出しでの処理を実行すると、サービスの起動時、影響します。</span><span class="sxs-lookup"><span data-stu-id="4cc55-117">Performing excessive processing in these calls will affect service startup time.</span></span>  
  
 <span data-ttu-id="4cc55-118">インプロセス受信アダプターを作成するときの、オブジェクト間の対話処理を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4cc55-118">The following figure shows the object interactions involved in creating an in-process receive adapter.</span></span>  
  
 ![](../core/media/ebiz-sdk-devadapter11.gif "ebiz_sdk_devadapter11")  
<span data-ttu-id="4cc55-119">インプロセス受信アダプターのワークフロー</span><span class="sxs-lookup"><span data-stu-id="4cc55-119">Workflow for an in-process receive adapter</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cc55-120">参照</span><span class="sxs-lookup"><span data-stu-id="4cc55-120">See Also</span></span>  
 <span data-ttu-id="4cc55-121">[アダプタの変数](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="4cc55-121">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="4cc55-122">[開発、受信アダプター](../core/developing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="4cc55-122">[Developing a Receive Adapter](../core/developing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="4cc55-123">[インスタンス化と初期化、アダプターの受信](../core/instantiating-and-initializing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="4cc55-123">[Instantiating and Initializing a Receive Adapter](../core/instantiating-and-initializing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="4cc55-124">[受信アダプターの分離用のインターフェイス](../core/interfaces-for-an-isolated-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="4cc55-124">[Interfaces for an Isolated Receive Adapter](../core/interfaces-for-an-isolated-receive-adapter.md) </span></span>  
 <span data-ttu-id="4cc55-125">[受信アダプターのバッチ サポート用のインターフェイス](../core/interfaces-for-a-batch-supported-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="4cc55-125">[Interfaces for a Batch-Supported Receive Adapter](../core/interfaces-for-a-batch-supported-receive-adapter.md) </span></span>  
 <span data-ttu-id="4cc55-126">[受信アダプターのバッチでサポートされているトランザクション パブリケーション用のインターフェイス](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="4cc55-126">[Interfaces for a Transactional Batch-Supported Receive Adapter](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md) </span></span>  
 [<span data-ttu-id="4cc55-127">アダプターの受信要求-応答の同期用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="4cc55-127">Interfaces for a Synchronous Request-Response Receive Adapter</span></span>](../core/interfaces-for-a-synchronous-request-response-receive-adapter.md)