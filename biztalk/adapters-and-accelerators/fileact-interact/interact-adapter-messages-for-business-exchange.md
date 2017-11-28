---
title: "ビジネスの Exchange に対するアダプターのメッセージを相互作用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b443b8a-4e56-47f1-8d91-5c807fd54ccc
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d19e10940e6a83c24e9397f0df94d0fc54e4da38
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="interact-adapter-messages-for-business-exchange"></a><span data-ttu-id="0a9b1-102">ビジネスの Exchange に対するアダプターのメッセージを相互作用します。</span><span class="sxs-lookup"><span data-stu-id="0a9b1-102">InterAct Adapter Messages for Business Exchange</span></span>
<span data-ttu-id="0a9b1-103">InterAct アダプターのエンド ツー エンドのサイクルには、4 つのメッセージがあります。</span><span class="sxs-lookup"><span data-stu-id="0a9b1-103">There are four messages in the InterAct adapter end-to-end cycle.</span></span> <span data-ttu-id="0a9b1-104">このメッセージは SWIFTNet プリミティブです。</span><span class="sxs-lookup"><span data-stu-id="0a9b1-104">These messages are SWIFTNet primitives.</span></span> <span data-ttu-id="0a9b1-105">最初と最後のメッセージには、クライアント側のプリミティブ、SwInt:ExchangeRequest および SwInt:ExchangeResponse が構成されています。</span><span class="sxs-lookup"><span data-stu-id="0a9b1-105">The first and last messages comprise the client-side primitives, SwInt:ExchangeRequest and SwInt:ExchangeResponse.</span></span> <span data-ttu-id="0a9b1-106">中央の 2 つのメッセージには、サーバー側のプリミティブ、SwInt:HandleRequest および SwInt:HandleResponse が構成されています。</span><span class="sxs-lookup"><span data-stu-id="0a9b1-106">The middle two messages comprise the server-side primitives, SwInt:HandleRequest and SwInt:HandleResponse.</span></span>  
  
 <span data-ttu-id="0a9b1-107">簡略化のレベルはこのエンド ツー エンドのメッセージのサイクルに 6 つの手順があります。</span><span class="sxs-lookup"><span data-stu-id="0a9b1-107">At this level of simplification, there are six steps in the end-to-end message cycle:</span></span>  
  
1.  <span data-ttu-id="0a9b1-108">クライアント アプリケーションでは、要求メッセージを準備します。</span><span class="sxs-lookup"><span data-stu-id="0a9b1-108">The client application prepares the request message.</span></span>  
  
2.  <span data-ttu-id="0a9b1-109">クライアント アプリケーションは、要求メッセージを SWIFTNet に渡します。</span><span class="sxs-lookup"><span data-stu-id="0a9b1-109">The client application passes the request message to SWIFTNet.</span></span>  
  
3.  <span data-ttu-id="0a9b1-110">SWIFTNet は要求メッセージを処理し、サーバー アプリケーションに送信します。</span><span class="sxs-lookup"><span data-stu-id="0a9b1-110">SWIFTNet processes the request message, and sends it to the server application.</span></span>  
  
4.  <span data-ttu-id="0a9b1-111">サーバー アプリケーションは、SWIFTNet から要求メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="0a9b1-111">The server application receives the request message from SWIFTNet.</span></span>  
  
5.  <span data-ttu-id="0a9b1-112">サーバー アプリケーションは、応答メッセージを準備します。</span><span class="sxs-lookup"><span data-stu-id="0a9b1-112">The server application prepares the response message.</span></span>  
  
6.  <span data-ttu-id="0a9b1-113">サーバー アプリケーションは、応答メッセージを SWIFTNet に渡します。</span><span class="sxs-lookup"><span data-stu-id="0a9b1-113">The server application passes the response message to SWIFTNet.</span></span>  
  
7.  <span data-ttu-id="0a9b1-114">SWIFTNet は応答メッセージを処理し、クライアント アプリケーションに送信します。</span><span class="sxs-lookup"><span data-stu-id="0a9b1-114">SWIFTNet processes the response message, and sends it to the client application.</span></span>  
  
8.  <span data-ttu-id="0a9b1-115">クライアント アプリケーションは、SWIFTNet から応答メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="0a9b1-115">The client application receives the response message from SWIFTNet.</span></span>  
  
 <span data-ttu-id="0a9b1-116">次の図は、InterAct メッセージ交換を示しています。</span><span class="sxs-lookup"><span data-stu-id="0a9b1-116">The following figure shows the InterAct message exchange.</span></span>  
  
 <span data-ttu-id="0a9b1-117">![InterAct メッセージ交換](../../adapters-and-accelerators/fileact-interact/media/12fbebc6-5ab7-4d7f-9f94-4069b22161fa.gif "12fbebc6-5ab7-4d7f-9f94-4069b22161fa")</span><span class="sxs-lookup"><span data-stu-id="0a9b1-117">![InterAct message exchange](../../adapters-and-accelerators/fileact-interact/media/12fbebc6-5ab7-4d7f-9f94-4069b22161fa.gif "12fbebc6-5ab7-4d7f-9f94-4069b22161fa")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a9b1-118">参照</span><span class="sxs-lookup"><span data-stu-id="0a9b1-118">See Also</span></span>  
 <span data-ttu-id="0a9b1-119">[アダプターのアーキテクチャを対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="0a9b1-119">[InterAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="0a9b1-120">[InterAct アダプター コンポーネント](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md) </span><span class="sxs-lookup"><span data-stu-id="0a9b1-120">[InterAct Adapter Components](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md) </span></span>  
 <span data-ttu-id="0a9b1-121">[InterAct アダプターのクライアント アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span><span class="sxs-lookup"><span data-stu-id="0a9b1-121">[InterAct Adapter Client Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span></span>  
 <span data-ttu-id="0a9b1-122">[InterAct アダプタ サーバー アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span><span class="sxs-lookup"><span data-stu-id="0a9b1-122">[InterAct Adapter Server Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span></span>  
 <span data-ttu-id="0a9b1-123">[アダプター ストア アンド フォワードを対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="0a9b1-123">[InterAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="0a9b1-124">[アダプターのセキュリティ アーキテクチャを対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="0a9b1-124">[InterAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="0a9b1-125">[アダプターのエンド ツー エンドの信頼性の高い配信を対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md) </span><span class="sxs-lookup"><span data-stu-id="0a9b1-125">[InterAct Adapter End-to-End Reliable Delivery](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md) </span></span>  
 <span data-ttu-id="0a9b1-126">[アダプターの状態を操作の監視](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md) </span><span class="sxs-lookup"><span data-stu-id="0a9b1-126">[InterAct Adapter Status Monitoring](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md) </span></span>  
 [<span data-ttu-id="0a9b1-127">アダプター否認不可を対話します。</span><span class="sxs-lookup"><span data-stu-id="0a9b1-127">InterAct Adapter Non-Repudiation</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)