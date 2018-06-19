---
title: SWIFTNet クライアントとサーバー |Microsoft ドキュメント
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
ms.openlocfilehash: 5ea3a1b974a26f90d03bb65675c1c4e8966720f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224658"
---
# <a name="swiftnet-client-and-server"></a><span data-ttu-id="95ac1-102">SWIFTNet クライアントとサーバー</span><span class="sxs-lookup"><span data-stu-id="95ac1-102">SWIFTNet Client and Server</span></span>
<span data-ttu-id="95ac1-103">SWIFT 条項クライアントとサーバーを使用して送信および受信について説明します。</span><span class="sxs-lookup"><span data-stu-id="95ac1-103">SWIFT uses the terms client and server to describe sending and receiving.</span></span> <span data-ttu-id="95ac1-104">SWIFT クライアントは、SWIFTNet 経由で通信を開始する SWIFTNet リンク (SNL) を呼び出すプロセスです。</span><span class="sxs-lookup"><span data-stu-id="95ac1-104">A SWIFT client is a process that calls the SWIFTNet Link (SNL) to initiate communication over SWIFTNet.</span></span> <span data-ttu-id="95ac1-105">BizTalk Server で、これは、送信アダプターが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="95ac1-105">In BizTalk Server, this is called the send adapter.</span></span> <span data-ttu-id="95ac1-106">SWIFT サーバーは、SWIFTNet 経由でトラフィックを受信すると、SNL によって呼び出されるプログラムです。</span><span class="sxs-lookup"><span data-stu-id="95ac1-106">A SWIFT server is a program that is called by the SNL when traffic comes in over SWIFTNet.</span></span> <span data-ttu-id="95ac1-107">BizTalk Server で、受信アダプターは、呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="95ac1-107">In BizTalk Server, this is called the receive adapter.</span></span>  
  
 <span data-ttu-id="95ac1-108">SWIFT クライアントとビジネス クライアントとサーバーでサーバーを混同しないでください。</span><span class="sxs-lookup"><span data-stu-id="95ac1-108">Do not confuse the SWIFT client and server with the business client and server.</span></span> <span data-ttu-id="95ac1-109">たとえば、クライアント (組織) は、サーバー (組織) によって提供されるサービスに依存します。</span><span class="sxs-lookup"><span data-stu-id="95ac1-109">For example, a client (organization) relies on the services provided by a server (organization).</span></span> <span data-ttu-id="95ac1-110">サーバー (組織) は、クライアント (組織) との通信を開始する場合、必要があります SNL クライアント アプリケーションのためとを使用して、着信トラフィックを受信する SNL サーバー アプリケーションがクライアント (組織) に必要です。</span><span class="sxs-lookup"><span data-stu-id="95ac1-110">If the server (organization) wants to initiate a communication with the client (organization), it must use an SNL client application to do so, and the client (organization) must have an SNL server application to receive the incoming traffic.</span></span> <span data-ttu-id="95ac1-111">これは、次の図で説明します。</span><span class="sxs-lookup"><span data-stu-id="95ac1-111">This is described in the following figure.</span></span>  
  
 <span data-ttu-id="95ac1-112">![クライアントとサーバー間の SWIFTNet 関係](../../adapters-and-accelerators/fileact-interact/media/7ad5d877-19d4-431f-9358-d5ae278cf945.gif "7ad5d877-19d4-431f-9358-d5ae278cf945")</span><span class="sxs-lookup"><span data-stu-id="95ac1-112">![SWIFTNet relationship between client and server](../../adapters-and-accelerators/fileact-interact/media/7ad5d877-19d4-431f-9358-d5ae278cf945.gif "7ad5d877-19d4-431f-9358-d5ae278cf945")</span></span>  
  
 <span data-ttu-id="95ac1-113">SNL では、クライアントとサーバーの両方のアプリケーションは、コマンド プロンプトから起動された実行可能ファイルを前提としています。</span><span class="sxs-lookup"><span data-stu-id="95ac1-113">SNL assumes both client and server applications are executables started from the command prompt.</span></span> <span data-ttu-id="95ac1-114">どちらも DLL にリンク SNL API、SNL インスタンスの実際のプロセスと通信します。</span><span class="sxs-lookup"><span data-stu-id="95ac1-114">They both link to the SNL API DLL, which communicates with the actual SNL instance process.</span></span>  
  
## <a name="snl-client-applications"></a><span data-ttu-id="95ac1-115">SNL クライアント アプリケーション</span><span class="sxs-lookup"><span data-stu-id="95ac1-115">SNL client applications</span></span>  
 <span data-ttu-id="95ac1-116">SNL クライアント アプリケーションは、次に示す SwCall API に依存します。</span><span class="sxs-lookup"><span data-stu-id="95ac1-116">SNL client applications rely on the SwCall API described below.</span></span> <span data-ttu-id="95ac1-117">技術的には、一般的なクライアント アプリケーションできるように記述します。</span><span class="sxs-lookup"><span data-stu-id="95ac1-117">Technically speaking, a typical client application can be described as follows:</span></span>  
  
```  
Main:  
  Initialize SNL API  
  Repeat  
    Call SwCall API  
  Until shutdown  
```  
  
 <span data-ttu-id="95ac1-118">SNL によるクライアントのコンテキストを参照しているために、アプリケーションが専用のプロセスで実行する必要があります SNL クライアント プロセス id。</span><span class="sxs-lookup"><span data-stu-id="95ac1-118">SNL client applications must run in a dedicated process, because SNL references the client context by process ID.</span></span> <span data-ttu-id="95ac1-119">SNL は、SwCall タキシード リソースを使用する呼び出しを同期します。</span><span class="sxs-lookup"><span data-stu-id="95ac1-119">SNL synchronizes calls that use Tuxedo resources to SwCall.</span></span> <span data-ttu-id="95ac1-120">その結果、一度に 1 つのクライアント スレッドだけは、SwCall 効果的に実行できます。</span><span class="sxs-lookup"><span data-stu-id="95ac1-120">As a result, only a single client thread at a time can effectively execute a SwCall.</span></span>  
  
 <span data-ttu-id="95ac1-121">クライアントでは、同期通信モードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="95ac1-121">The client supports the synchronous communication mode.</span></span> <span data-ttu-id="95ac1-122">これは、SWCall で戻り値には、応答から返されたとき、サーバーが発生することを意味します。</span><span class="sxs-lookup"><span data-stu-id="95ac1-122">This means that the return on the SWCall occurs when the response comes back from the server.</span></span> <span data-ttu-id="95ac1-123">[次へ] SwCall は、この戻り値の後にのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="95ac1-123">The next SwCall can be performed only after this return.</span></span>  
  
## <a name="snl-server-applications"></a><span data-ttu-id="95ac1-124">SNL サーバー アプリケーション</span><span class="sxs-lookup"><span data-stu-id="95ac1-124">SNL server applications</span></span>  
 <span data-ttu-id="95ac1-125">SNL サーバー アプリケーションは、クライアントのアプリケーションよりも若干複雑です。</span><span class="sxs-lookup"><span data-stu-id="95ac1-125">SNL server applications are slightly more complex than the client applications.</span></span> <span data-ttu-id="95ac1-126">サーバー アプリケーションは、SNL DLL にブロッキング呼び出しを実行する前に、コールバック関数を登録します。</span><span class="sxs-lookup"><span data-stu-id="95ac1-126">Server applications register callback functions before performing a blocking call into the SNL DLL.</span></span> <span data-ttu-id="95ac1-127">技術的には、一般的なサーバー アプリケーションできるように記述します。</span><span class="sxs-lookup"><span data-stu-id="95ac1-127">Technically speaking, a typical server application can be described as follows:</span></span>  
  
```  
Main:  
  Initialize SNL API  
  Call SwRegisterSwCallback, registering the Callback function  
  Call SwServer, block and receive callbacks  
  
Callback(Request):  
  Process Request  
  Return Response  
```  
  
 <span data-ttu-id="95ac1-128">サーバー アプリケーションは、コールバック関数の中に SwCall API を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="95ac1-128">The server application can call the SwCall API while in the callback function.</span></span> <span data-ttu-id="95ac1-129">場合によっては、目的の結果または応答を生成できる SwCall 呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="95ac1-129">In some cases it must call SwCall to be able to produce the desired result or response.</span></span> <span data-ttu-id="95ac1-130">ただし、サーバー アプリケーションは、ネットワーク経由で通信を開始することができますされません。</span><span class="sxs-lookup"><span data-stu-id="95ac1-130">However, a server application can never initiate a communication over the network.</span></span> <span data-ttu-id="95ac1-131">サーバー アプリケーションでは、クライアント アプリケーションをすることはできません。</span><span class="sxs-lookup"><span data-stu-id="95ac1-131">A server application can never be a client application.</span></span>  
  
 <span data-ttu-id="95ac1-132">次の図に、呼び出しというラベルの付いた**初期化**SNL API 初期化プロセスは、複数の呼び出しを必要とする抽象化したものです。</span><span class="sxs-lookup"><span data-stu-id="95ac1-132">In the following figure, the call labeled **Initialize** is an abstraction for the SNL API initialization process, which requires multiple calls.</span></span> <span data-ttu-id="95ac1-133">ラベルの付いた呼び出し**SwCallback()** が複数回繰り返す、および呼び出しというラベルの付いた**SwCall()** は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="95ac1-133">The call labeled **SwCallback()** will be repeated several times, and the call labeled **SwCall()** is optional.</span></span>  
  
 <span data-ttu-id="95ac1-134">![SNL サーバー機能](../../adapters-and-accelerators/fileact-interact/media/42395775-cdbc-4e36-8b36-566caefa2aaf.gif "42395775-cdbc-4e36-8b36-566caefa2aaf")</span><span class="sxs-lookup"><span data-stu-id="95ac1-134">![SNL Server functionality](../../adapters-and-accelerators/fileact-interact/media/42395775-cdbc-4e36-8b36-566caefa2aaf.gif "42395775-cdbc-4e36-8b36-566caefa2aaf")</span></span>  
  
 <span data-ttu-id="95ac1-135">サーバーと SNL API DLL の間のすべての呼び出しは、標準の C 呼び出し規約の同期の関数呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="95ac1-135">All calls between the server and the SNL API DLL are standard C calling convention synchronous function calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95ac1-136">参照</span><span class="sxs-lookup"><span data-stu-id="95ac1-136">See Also</span></span>  
 <span data-ttu-id="95ac1-137">[FileAct を理解し、アダプターのアーキテクチャの対話](../../adapters-and-accelerators/fileact-interact/understanding-fileact-and-interact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="95ac1-137">[Understanding FileAct and InterAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/understanding-fileact-and-interact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="95ac1-138">[SWIFT 送信アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="95ac1-138">[SWIFT Send Adapter Architecture](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-architecture.md) </span></span>  
 [<span data-ttu-id="95ac1-139">SWIFT 受信アダプターのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="95ac1-139">SWIFT Receive Adapter Architecture</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md)