---
title: 受信アダプターをインプロセスで用のインターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4ed668d9-7512-4026-a8f3-df05aeed4df6
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d608f9e511b1a3cb0ba94f30fbe3cd1eb7c9e87
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36965867"
---
# <a name="interfaces-for-an-in-process-receive-adapter"></a><span data-ttu-id="bd126-102">インプロセス受信アダプター用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="bd126-102">Interfaces for an In-Process Receive Adapter</span></span>
<span data-ttu-id="bd126-103">メッセージング エンジンは、インプロセス アダプターをインスタンス化して構成し、トランスポート プロキシに渡して、アダプターがその機能にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="bd126-103">The Messaging Engine instantiates and configures in-process adapters, passing in the transport proxy to allow the adapter to access its functionality.</span></span> <span data-ttu-id="bd126-104">構成およびトランスポート プロキシへのバインドを有効にするには、アダプターに次の構成インターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd126-104">To enable configuration and binding to the transport proxy, adapters must implement the following configuration interfaces:</span></span>  
  
- <span data-ttu-id="bd126-105">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="bd126-105">**IBTTransport**</span></span>  
  
- <span data-ttu-id="bd126-106">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="bd126-106">**IBTTransportControl**</span></span>  
  
- <span data-ttu-id="bd126-107">**IBTTransportConfig**</span><span class="sxs-lookup"><span data-stu-id="bd126-107">**IBTTransportConfig**</span></span>  
  
- <span data-ttu-id="bd126-108">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="bd126-108">**IBaseComponent**</span></span>  
  
  <span data-ttu-id="bd126-109">必要に応じて、アダプターが初期化中にハンドラー情報を受信する場合は、する必要がある実装**IPersistPropertyBag**します。</span><span class="sxs-lookup"><span data-stu-id="bd126-109">Optionally if the adapter wants to receive handler information during initialization it needs to implement **IPersistPropertyBag**.</span></span>  
  
  <span data-ttu-id="bd126-110">メッセージング エンジンは、アダプターのインスタンスを作成し、初期化して、受信場所の構成を設定します。</span><span class="sxs-lookup"><span data-stu-id="bd126-110">The Messaging Engine creates an instance of an adapter, initializes it, and sets the configuration of receive locations.</span></span> <span data-ttu-id="bd126-111">メッセージング エンジンがアダプター プロパティ バッグを渡します、 **AddReceiveEndpoint**メソッドの呼び出し。</span><span class="sxs-lookup"><span data-stu-id="bd126-111">The Messaging Engine passes a property bag to an adapter on the **AddReceiveEndpoint** method call.</span></span> <span data-ttu-id="bd126-112">プロパティ バッグには、受信場所と受信ハンドラーの構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="bd126-112">The property bag contains the configuration for the receive location and receive handler.</span></span> <span data-ttu-id="bd126-113">構成は、XML スタイルのプロパティ バッグの形式で、データベースに格納されます。</span><span class="sxs-lookup"><span data-stu-id="bd126-113">The configuration is stored in the database in the form of an XML-styled property bag.</span></span> <span data-ttu-id="bd126-114">メッセージング エンジンは、XML を読み取り、XML からプロパティ バッグを復元します。</span><span class="sxs-lookup"><span data-stu-id="bd126-114">The Messaging Engine reads the XML and rehydrates a property bag from the XML.</span></span> <span data-ttu-id="bd126-115">少なくとも 1 つのエンドポイント (受信場所) が追加されたら、アダプターはメッセージの送信を開始できます。</span><span class="sxs-lookup"><span data-stu-id="bd126-115">After at least one endpoint (receive location) is added, the adapter can start submitting messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bd126-116">アダプターがメッセージング エンジンなどの呼び出しはブロックされません**IBTTransportControl.Initialize**、 **IPersistPropertyBag.Load**、および**IBTTransportConfig.AddReceiveEndpoint**.</span><span class="sxs-lookup"><span data-stu-id="bd126-116">Adapters should not block Messaging Engine calls such as **IBTTransportControl.Initialize**, **IPersistPropertyBag.Load**, and **IBTTransportConfig.AddReceiveEndpoint**.</span></span> <span data-ttu-id="bd126-117">過度のこれらの呼び出しで処理を実行すると、サービスの開始時に影響します。</span><span class="sxs-lookup"><span data-stu-id="bd126-117">Performing excessive processing in these calls will affect service startup time.</span></span>  
  
 <span data-ttu-id="bd126-118">インプロセス受信アダプターを作成するときの、オブジェクト間の対話処理を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bd126-118">The following figure shows the object interactions involved in creating an in-process receive adapter.</span></span>  
  
 <span data-ttu-id="bd126-119">![](../core/media/ebiz-sdk-devadapter11.gif "ebiz_sdk_devadapter11")</span><span class="sxs-lookup"><span data-stu-id="bd126-119">![](../core/media/ebiz-sdk-devadapter11.gif "ebiz_sdk_devadapter11")</span></span>  
<span data-ttu-id="bd126-120">インプロセス受信アダプターのワークフロー</span><span class="sxs-lookup"><span data-stu-id="bd126-120">Workflow for an in-process receive adapter</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd126-121">参照</span><span class="sxs-lookup"><span data-stu-id="bd126-121">See Also</span></span>  
 <span data-ttu-id="bd126-122">[アダプター変数](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="bd126-122">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="bd126-123">[開発、受信アダプター](../core/developing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="bd126-123">[Developing a Receive Adapter](../core/developing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="bd126-124">[インスタンス化と初期化、アダプターの受信](../core/instantiating-and-initializing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="bd126-124">[Instantiating and Initializing a Receive Adapter](../core/instantiating-and-initializing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="bd126-125">[インターフェイスの分離受信アダプター](../core/interfaces-for-an-isolated-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="bd126-125">[Interfaces for an Isolated Receive Adapter](../core/interfaces-for-an-isolated-receive-adapter.md) </span></span>  
 <span data-ttu-id="bd126-126">[受信アダプターのバッチ サポート用のインターフェイス](../core/interfaces-for-a-batch-supported-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="bd126-126">[Interfaces for a Batch-Supported Receive Adapter](../core/interfaces-for-a-batch-supported-receive-adapter.md) </span></span>  
 <span data-ttu-id="bd126-127">[受信アダプターのバッチでサポートされているトランザクション パブリケーション用のインターフェイス](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="bd126-127">[Interfaces for a Transactional Batch-Supported Receive Adapter](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md) </span></span>  
 [<span data-ttu-id="bd126-128">要求 - 応答の同期受信アダプター用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="bd126-128">Interfaces for a Synchronous Request-Response Receive Adapter</span></span>](../core/interfaces-for-a-synchronous-request-response-receive-adapter.md)