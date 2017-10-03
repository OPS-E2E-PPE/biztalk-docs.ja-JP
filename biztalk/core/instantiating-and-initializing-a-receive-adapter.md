---
title: "インスタンス化と初期化、受信アダプター |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c5cb5ba7-e2b5-49d2-adf5-a8df0bb81def
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 565712faecf11b728c4f552798b1e3daebf962f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="instantiating-and-initializing-a-receive-adapter"></a><span data-ttu-id="dd860-102">受信アダプターのインスタンス化と初期化</span><span class="sxs-lookup"><span data-stu-id="dd860-102">Instantiating and Initializing a Receive Adapter</span></span>
<span data-ttu-id="dd860-103">受信アダプターは、インスタンス化されるとすぐメッセージング エンジンによって初期化されます。メッセージング エンジンはまず、IBTTransportControl の QueryInteraface を呼び出し、</span><span class="sxs-lookup"><span data-stu-id="dd860-103">Immediately after a receive adapter is instantiated it is initialized by the Messaging Engine, the engine calls QueryInteraface for IBTTransportControl.</span></span> <span data-ttu-id="dd860-104">IBTTransportControl 順に呼び出して**です。初期化**をメンバー変数に永続化する、アダプター、アダプターのトランスポート プロキシに渡します。</span><span class="sxs-lookup"><span data-stu-id="dd860-104">It then calls IBTTransportControl**.Initialize** passing in the adapter's transport proxy, which the adapter persists in a member variable.</span></span> <span data-ttu-id="dd860-105">次に、エンジンを呼び出す**QueryInterface**の**IPersistPropertyBag**です。</span><span class="sxs-lookup"><span data-stu-id="dd860-105">Next the engine calls **QueryInterface** for **IPersistPropertyBag**.</span></span> <span data-ttu-id="dd860-106">これは省略可能なインターフェイスです。ハンドラーの構成がアダプターに渡される場合は、アダプターを実装すると、**ロード**メソッドの呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="dd860-106">This is an optional interface; if the adapter implements it, the handler configuration is passed to the adapter in the **Load** method call.</span></span> <span data-ttu-id="dd860-107">受信アダプターの初期化の最終段階では、エンドポイント構成がアダプターに渡されます。</span><span class="sxs-lookup"><span data-stu-id="dd860-107">The final stage of initializing a receive adapter involves passing the endpoint configuration to the adapter.</span></span> <span data-ttu-id="dd860-108">このフェーズ エンジン呼び出し**IBTTransportConfig.AddReceiveEndpoint**エンドポイント、エンドポイントのアダプター固有の構成および BizTalk の構成を URI で渡すしながら、アクティブなエンドポイントごとに 1 回そのエンドポイント。</span><span class="sxs-lookup"><span data-stu-id="dd860-108">During this phase the engine calls **IBTTransportConfig.AddReceiveEndpoint** once for each active endpoint, passing in the URI for the endpoint, the adapter specific configuration for the endpoint, and the BizTalk configuration for that endpoint.</span></span>  
  
 <span data-ttu-id="dd860-109">この API 呼び出しの順序は、次の図のようになります。</span><span class="sxs-lookup"><span data-stu-id="dd860-109">The following figure illustrates this sequence of API calls.</span></span> <span data-ttu-id="dd860-110">アダプターは、青色で示されるインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="dd860-110">The adapter implements the interfaces shown in blue.</span></span>  
  
 ![](../core/media/sequence-of-init-calls.gif "Sequence_of_init_calls")  
  
 <span data-ttu-id="dd860-111">**実装のヒン ト:**一般に、アダプターをブロックしないでください呼び出しにおいてメッセージング エンジンなど**IBTTransportControl.Initialize**、 **IPersistPropertyBag.Load**、および**IBTTransportConfig.AddReceiveEndpoint**です。</span><span class="sxs-lookup"><span data-stu-id="dd860-111">**Implementation Tip:** In general, adapters should not block the Messaging Engine in calls such as **IBTTransportControl.Initialize**, **IPersistPropertyBag.Load**, and **IBTTransportConfig.AddReceiveEndpoint**.</span></span> <span data-ttu-id="dd860-112">過剰なこれらの呼び出しでの処理を実行すると、サービスの起動時にマイナスの影響があります。</span><span class="sxs-lookup"><span data-stu-id="dd860-112">Performing excessive processing in these calls can have a negative impact on service startup time.</span></span>  
  
 <span data-ttu-id="dd860-113">受信場所が 1 つ以上関連付けられている受信アダプターはすべて、サービスの開始時に作成されます。</span><span class="sxs-lookup"><span data-stu-id="dd860-113">All receive adapters that have one or more associated receive locations are created at service startup.</span></span> <span data-ttu-id="dd860-114">すべての受信アダプターは非同期であり、バッチ処理をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="dd860-114">All receive adapters are asynchronous and support batching.</span></span> <span data-ttu-id="dd860-115">受信アダプターは、インプロセスの場合と分離の場合があります。</span><span class="sxs-lookup"><span data-stu-id="dd860-115">They can be in-process or isolated.</span></span> <span data-ttu-id="dd860-116">詳細については、受信アダプター変数を参照してください[のアダプタ変数](../core/adapter-variables.md)です。</span><span class="sxs-lookup"><span data-stu-id="dd860-116">For additional information about receive adapter variables, see [Adapter Variables](../core/adapter-variables.md).</span></span>