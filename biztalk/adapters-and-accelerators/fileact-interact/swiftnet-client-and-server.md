---
title: SWIFTNet クライアントおよびサーバー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 89d9f54f-af16-4f14-bbe4-8306758320d8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f18055bfae40f5a2369f153faa811639c1cc51bb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364098"
---
# <a name="swiftnet-client-and-server"></a><span data-ttu-id="5e5b8-102">SWIFTNet クライアントおよびサーバー</span><span class="sxs-lookup"><span data-stu-id="5e5b8-102">SWIFTNet Client and Server</span></span>
<span data-ttu-id="5e5b8-103">SWIFT では、用語のクライアントとサーバーを使用して、送信と受信について説明します。</span><span class="sxs-lookup"><span data-stu-id="5e5b8-103">SWIFT uses the terms client and server to describe sending and receiving.</span></span> <span data-ttu-id="5e5b8-104">SWIFT クライアントは、呼び出す SWIFTNet リンク (SNL) SWIFTNet 経由で通信を開始するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="5e5b8-104">A SWIFT client is a process that calls the SWIFTNet Link (SNL) to initiate communication over SWIFTNet.</span></span> <span data-ttu-id="5e5b8-105">BizTalk Server で、これは、送信アダプターが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5e5b8-105">In BizTalk Server, this is called the send adapter.</span></span> <span data-ttu-id="5e5b8-106">SWIFT サーバーは、SWIFTNet 経由でトラフィックを受信すると、SNL によって呼び出されるプログラムです。</span><span class="sxs-lookup"><span data-stu-id="5e5b8-106">A SWIFT server is a program that is called by the SNL when traffic comes in over SWIFTNet.</span></span> <span data-ttu-id="5e5b8-107">BizTalk Server で、これは受信アダプターは、呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5e5b8-107">In BizTalk Server, this is called the receive adapter.</span></span>  
  
 <span data-ttu-id="5e5b8-108">SWIFT クライアントとビジネス クライアントとサーバーでサーバーを混同しないでください。</span><span class="sxs-lookup"><span data-stu-id="5e5b8-108">Do not confuse the SWIFT client and server with the business client and server.</span></span> <span data-ttu-id="5e5b8-109">たとえば、クライアント (組織) は、サーバー (組織) によって提供されるサービスに依存します。</span><span class="sxs-lookup"><span data-stu-id="5e5b8-109">For example, a client (organization) relies on the services provided by a server (organization).</span></span> <span data-ttu-id="5e5b8-110">(組織) のサーバーがクライアント (組織) との通信を開始しようとすると、SNL クライアント アプリケーションを使用して、そのためがあり、着信トラフィックを受信する SNL サーバー アプリケーションがクライアント (組織) に必要です。</span><span class="sxs-lookup"><span data-stu-id="5e5b8-110">If the server (organization) wants to initiate a communication with the client (organization), it must use an SNL client application to do so, and the client (organization) must have an SNL server application to receive the incoming traffic.</span></span> <span data-ttu-id="5e5b8-111">これは、次の図で説明します。</span><span class="sxs-lookup"><span data-stu-id="5e5b8-111">This is described in the following figure.</span></span>  
  
 <span data-ttu-id="5e5b8-112">![クライアントとサーバー間の SWIFTNet 関係](../../adapters-and-accelerators/fileact-interact/media/7ad5d877-19d4-431f-9358-d5ae278cf945.gif "7ad5d877-19d4-431f-9358-d5ae278cf945")</span><span class="sxs-lookup"><span data-stu-id="5e5b8-112">![SWIFTNet relationship between client and server](../../adapters-and-accelerators/fileact-interact/media/7ad5d877-19d4-431f-9358-d5ae278cf945.gif "7ad5d877-19d4-431f-9358-d5ae278cf945")</span></span>  
  
 <span data-ttu-id="5e5b8-113">SNL では、クライアントとサーバーの両方のアプリケーションは、コマンド プロンプトから起動する実行可能ファイルを前提としています。</span><span class="sxs-lookup"><span data-stu-id="5e5b8-113">SNL assumes both client and server applications are executables started from the command prompt.</span></span> <span data-ttu-id="5e5b8-114">どちらは、実際の SNL インスタンス プロセスと通信して SNL API DLL にリンクします。</span><span class="sxs-lookup"><span data-stu-id="5e5b8-114">They both link to the SNL API DLL, which communicates with the actual SNL instance process.</span></span>  
  
## <a name="snl-client-applications"></a><span data-ttu-id="5e5b8-115">SNL クライアント アプリケーション</span><span class="sxs-lookup"><span data-stu-id="5e5b8-115">SNL client applications</span></span>  
 <span data-ttu-id="5e5b8-116">SNL クライアント アプリケーションは、以下に示す SwCall API に依存します。</span><span class="sxs-lookup"><span data-stu-id="5e5b8-116">SNL client applications rely on the SwCall API described below.</span></span> <span data-ttu-id="5e5b8-117">厳密に言うと、典型的なクライアント アプリケーションできますように説明します。</span><span class="sxs-lookup"><span data-stu-id="5e5b8-117">Technically speaking, a typical client application can be described as follows:</span></span>  
  
```  
Main:  
  Initialize SNL API  
  Repeat  
    Call SwCall API  
  Until shutdown  
```  
  
 <span data-ttu-id="5e5b8-118">SNL によってクライアント コンテキストを参照しているために、アプリケーションが専用のプロセスで実行する必要があります SNL クライアント プロセス id。</span><span class="sxs-lookup"><span data-stu-id="5e5b8-118">SNL client applications must run in a dedicated process, because SNL references the client context by process ID.</span></span> <span data-ttu-id="5e5b8-119">SNL は、タキシード リソース SwCall を使用して呼び出しを同期します。</span><span class="sxs-lookup"><span data-stu-id="5e5b8-119">SNL synchronizes calls that use Tuxedo resources to SwCall.</span></span> <span data-ttu-id="5e5b8-120">その結果、一度に 1 つのクライアント スレッドのみは、SwCall 効果的に実行できます。</span><span class="sxs-lookup"><span data-stu-id="5e5b8-120">As a result, only a single client thread at a time can effectively execute a SwCall.</span></span>  
  
 <span data-ttu-id="5e5b8-121">クライアントは、同期通信モードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="5e5b8-121">The client supports the synchronous communication mode.</span></span> <span data-ttu-id="5e5b8-122">これは、SWCall で戻り値には、サーバーから応答が戻ったときに発生することを意味します。</span><span class="sxs-lookup"><span data-stu-id="5e5b8-122">This means that the return on the SWCall occurs when the response comes back from the server.</span></span> <span data-ttu-id="5e5b8-123">[次へ] SwCall は、この戻り値の後にのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="5e5b8-123">The next SwCall can be performed only after this return.</span></span>  
  
## <a name="snl-server-applications"></a><span data-ttu-id="5e5b8-124">SNL サーバー アプリケーション</span><span class="sxs-lookup"><span data-stu-id="5e5b8-124">SNL server applications</span></span>  
 <span data-ttu-id="5e5b8-125">SNL サーバー アプリケーションは、クライアント アプリケーションより多少複雑です。</span><span class="sxs-lookup"><span data-stu-id="5e5b8-125">SNL server applications are slightly more complex than the client applications.</span></span> <span data-ttu-id="5e5b8-126">サーバー アプリケーションは、SNL DLL にブロッキング呼び出しを実行する前に、コールバック関数を登録します。</span><span class="sxs-lookup"><span data-stu-id="5e5b8-126">Server applications register callback functions before performing a blocking call into the SNL DLL.</span></span> <span data-ttu-id="5e5b8-127">厳密に言うと、標準的なサーバー アプリケーションをできるように説明します。</span><span class="sxs-lookup"><span data-stu-id="5e5b8-127">Technically speaking, a typical server application can be described as follows:</span></span>  
  
```  
Main:  
  Initialize SNL API  
  Call SwRegisterSwCallback, registering the Callback function  
  Call SwServer, block and receive callbacks  
  
Callback(Request):  
  Process Request  
  Return Response  
```  
  
 <span data-ttu-id="5e5b8-128">サーバー アプリケーションでは、コールバック関数の中に SwCall API を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="5e5b8-128">The server application can call the SwCall API while in the callback function.</span></span> <span data-ttu-id="5e5b8-129">場合によっては、目的の結果または応答を生成できる SwCall 呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e5b8-129">In some cases it must call SwCall to be able to produce the desired result or response.</span></span> <span data-ttu-id="5e5b8-130">ただし、サーバー アプリケーションは、ネットワーク経由で通信を開始することができますされません。</span><span class="sxs-lookup"><span data-stu-id="5e5b8-130">However, a server application can never initiate a communication over the network.</span></span> <span data-ttu-id="5e5b8-131">サーバー アプリケーションでは、クライアント アプリケーションをすることはできません。</span><span class="sxs-lookup"><span data-stu-id="5e5b8-131">A server application can never be a client application.</span></span>  
  
 <span data-ttu-id="5e5b8-132">次の図に、呼び出しがというラベルが付いた**初期化**SNL API の初期化プロセスは、複数の呼び出しを必要とする抽象化です。</span><span class="sxs-lookup"><span data-stu-id="5e5b8-132">In the following figure, the call labeled **Initialize** is an abstraction for the SNL API initialization process, which requires multiple calls.</span></span> <span data-ttu-id="5e5b8-133">というラベルの付いた呼び出し**SwCallback()** が何回か繰り返すし、呼び出しというラベルの付いた**SwCall()** は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="5e5b8-133">The call labeled **SwCallback()** will be repeated several times, and the call labeled **SwCall()** is optional.</span></span>  
  
 <span data-ttu-id="5e5b8-134">![SNL サーバー機能](../../adapters-and-accelerators/fileact-interact/media/42395775-cdbc-4e36-8b36-566caefa2aaf.gif "42395775-cdbc-4e36-8b36-566caefa2aaf")</span><span class="sxs-lookup"><span data-stu-id="5e5b8-134">![SNL Server functionality](../../adapters-and-accelerators/fileact-interact/media/42395775-cdbc-4e36-8b36-566caefa2aaf.gif "42395775-cdbc-4e36-8b36-566caefa2aaf")</span></span>  
  
 <span data-ttu-id="5e5b8-135">サーバーと SNL API の DLL の間のすべての呼び出しは、標準の C 呼び出し規則の同期の関数呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="5e5b8-135">All calls between the server and the SNL API DLL are standard C calling convention synchronous function calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e5b8-136">参照</span><span class="sxs-lookup"><span data-stu-id="5e5b8-136">See Also</span></span>  
 <span data-ttu-id="5e5b8-137">[理解 FileAct および InterAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/understanding-fileact-and-interact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="5e5b8-137">[Understanding FileAct and InterAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/understanding-fileact-and-interact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="5e5b8-138">[SWIFT 送信アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="5e5b8-138">[SWIFT Send Adapter Architecture](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-architecture.md) </span></span>  
 [<span data-ttu-id="5e5b8-139">SWIFT 受信アダプターのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="5e5b8-139">SWIFT Receive Adapter Architecture</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md)