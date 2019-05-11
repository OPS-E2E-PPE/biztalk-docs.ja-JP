---
title: 業務用 Exchange 用の interAct アダプターのメッセージ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3b443b8a-4e56-47f1-8d91-5c807fd54ccc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d97c1bd20341719440637f0fa37bd8a806a84224
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366684"
---
# <a name="interact-adapter-messages-for-business-exchange"></a><span data-ttu-id="f4634-102">業務用 Exchange 用の interAct アダプターのメッセージ</span><span class="sxs-lookup"><span data-stu-id="f4634-102">InterAct Adapter Messages for Business Exchange</span></span>
<span data-ttu-id="f4634-103">InterAct アダプターのエンド ツー エンドのサイクルには、4 つのメッセージがあります。</span><span class="sxs-lookup"><span data-stu-id="f4634-103">There are four messages in the InterAct adapter end-to-end cycle.</span></span> <span data-ttu-id="f4634-104">これらのメッセージは SWIFTNet プリミティブです。</span><span class="sxs-lookup"><span data-stu-id="f4634-104">These messages are SWIFTNet primitives.</span></span> <span data-ttu-id="f4634-105">最初と最後のメッセージには、クライアント側のプリミティブ、SwInt:ExchangeRequest および SwInt:ExchangeResponse が構成されています。</span><span class="sxs-lookup"><span data-stu-id="f4634-105">The first and last messages comprise the client-side primitives, SwInt:ExchangeRequest and SwInt:ExchangeResponse.</span></span> <span data-ttu-id="f4634-106">中間の 2 つのメッセージには、サーバー側のプリミティブ、SwInt:HandleRequest および SwInt:HandleResponse が構成されています。</span><span class="sxs-lookup"><span data-stu-id="f4634-106">The middle two messages comprise the server-side primitives, SwInt:HandleRequest and SwInt:HandleResponse.</span></span>  
  
 <span data-ttu-id="f4634-107">この簡略化のレベルでは、エンド ツー エンドのメッセージのサイクルで 6 つの手順があります。</span><span class="sxs-lookup"><span data-stu-id="f4634-107">At this level of simplification, there are six steps in the end-to-end message cycle:</span></span>  
  
1. <span data-ttu-id="f4634-108">クライアント アプリケーションでは、要求メッセージを準備します。</span><span class="sxs-lookup"><span data-stu-id="f4634-108">The client application prepares the request message.</span></span>  
  
2. <span data-ttu-id="f4634-109">クライアント アプリケーションでは、SWIFTNet に要求メッセージを渡します。</span><span class="sxs-lookup"><span data-stu-id="f4634-109">The client application passes the request message to SWIFTNet.</span></span>  
  
3. <span data-ttu-id="f4634-110">SWIFTNet は、要求メッセージを処理し、サーバー アプリケーションに送信します。</span><span class="sxs-lookup"><span data-stu-id="f4634-110">SWIFTNet processes the request message, and sends it to the server application.</span></span>  
  
4. <span data-ttu-id="f4634-111">サーバー アプリケーションでは、SWIFTNet から要求メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="f4634-111">The server application receives the request message from SWIFTNet.</span></span>  
  
5. <span data-ttu-id="f4634-112">サーバー アプリケーションでは、応答メッセージを準備します。</span><span class="sxs-lookup"><span data-stu-id="f4634-112">The server application prepares the response message.</span></span>  
  
6. <span data-ttu-id="f4634-113">サーバー アプリケーションでは、SWIFTNet に応答メッセージを渡します。</span><span class="sxs-lookup"><span data-stu-id="f4634-113">The server application passes the response message to SWIFTNet.</span></span>  
  
7. <span data-ttu-id="f4634-114">SWIFTNet は、応答メッセージを処理し、クライアント アプリケーションに送信します。</span><span class="sxs-lookup"><span data-stu-id="f4634-114">SWIFTNet processes the response message, and sends it to the client application.</span></span>  
  
8. <span data-ttu-id="f4634-115">クライアント アプリケーションでは、SWIFTNet から応答メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="f4634-115">The client application receives the response message from SWIFTNet.</span></span>  
  
   <span data-ttu-id="f4634-116">InterAct メッセージ交換の図は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f4634-116">The following figure shows the InterAct message exchange.</span></span>  
  
   <span data-ttu-id="f4634-117">![InterAct メッセージ交換](../../adapters-and-accelerators/fileact-interact/media/12fbebc6-5ab7-4d7f-9f94-4069b22161fa.gif "12fbebc6-5ab7-4d7f-9f94-4069b22161fa")</span><span class="sxs-lookup"><span data-stu-id="f4634-117">![InterAct message exchange](../../adapters-and-accelerators/fileact-interact/media/12fbebc6-5ab7-4d7f-9f94-4069b22161fa.gif "12fbebc6-5ab7-4d7f-9f94-4069b22161fa")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4634-118">参照</span><span class="sxs-lookup"><span data-stu-id="f4634-118">See Also</span></span>  
 <span data-ttu-id="f4634-119">[InterAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="f4634-119">[InterAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="f4634-120">[InterAct アダプターのコンポーネント](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md) </span><span class="sxs-lookup"><span data-stu-id="f4634-120">[InterAct Adapter Components](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md) </span></span>  
 <span data-ttu-id="f4634-121">[InterAct アダプターのクライアント アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span><span class="sxs-lookup"><span data-stu-id="f4634-121">[InterAct Adapter Client Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span></span>  
 <span data-ttu-id="f4634-122">[InterAct アダプタ サーバー アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span><span class="sxs-lookup"><span data-stu-id="f4634-122">[InterAct Adapter Server Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span></span>  
 <span data-ttu-id="f4634-123">[InterAct アダプター ストア アンド フォワード](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="f4634-123">[InterAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="f4634-124">[InterAct アダプターのセキュリティ アーキテクチャ](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="f4634-124">[InterAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="f4634-125">[アダプターのエンド ツー エンドの信頼性の高い配信を操作します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md) </span><span class="sxs-lookup"><span data-stu-id="f4634-125">[InterAct Adapter End-to-End Reliable Delivery](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md) </span></span>  
 <span data-ttu-id="f4634-126">[InterAct アダプターの状態の監視](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md) </span><span class="sxs-lookup"><span data-stu-id="f4634-126">[InterAct Adapter Status Monitoring](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md) </span></span>  
 [<span data-ttu-id="f4634-127">InterAct アダプターの否認不可</span><span class="sxs-lookup"><span data-stu-id="f4634-127">InterAct Adapter Non-Repudiation</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)