---
title: "SWIFT 受信アダプターのアーキテクチャ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 16f32689-0b70-4389-8596-991fd776f185
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3aca9b5ef1fd1130feeebad3ec6fdf072d3bf88d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="swift-receive-adapter-architecture"></a><span data-ttu-id="b0057-102">SWIFT 受信アダプターのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="b0057-102">SWIFT Receive Adapter Architecture</span></span>
<span data-ttu-id="b0057-103">BizTalk Server では、受信アダプターは、ホストを実行する別のプロセスが作成されたことを意味する独自のメモリ領域内でホストされます。</span><span class="sxs-lookup"><span data-stu-id="b0057-103">In BizTalk Server, the receive adapter is hosted within its own memory space, which means a separate process is created to run the host.</span></span> <span data-ttu-id="b0057-104">このホストが SWIFTNet リンク (SNL) 構成では、サブシステムを定義することによって生成されます。</span><span class="sxs-lookup"><span data-stu-id="b0057-104">This host is spawned by defining a subsystem in the SWIFTNet Link (SNL) configuration.</span></span>  
  
 <span data-ttu-id="b0057-105">サーバーの実行可能ファイルは、SNL 構成 (paramfile) サブシステムとして構成され、SWIFTNet Start コマンドを実行することによって生成されます。</span><span class="sxs-lookup"><span data-stu-id="b0057-105">The server executable is configured as a subsystem in the SNL configuration (paramfile) and is spawned by executing the SWIFTNet Start command.</span></span> <span data-ttu-id="b0057-106">SNL サーバー アプリケーションを終了するには、SWIFTNet Stop コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b0057-106">The SNL server application is terminated by executing the SWIFTNet Stop command.</span></span> <span data-ttu-id="b0057-107">SNL は、サーバー実行可能ファイルの有効期間を管理します。</span><span class="sxs-lookup"><span data-stu-id="b0057-107">SNL manages the lifetime of the server executable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b0057-108">サービス局のシナリオでは、独自のセキュリティ コンテキストで実行されている SWIFT メンバーを複数のサービスを提供するアダプターが必要です。</span><span class="sxs-lookup"><span data-stu-id="b0057-108">The service bureau scenario requires the adapter to service multiple SWIFT members running under their own security contexts.</span></span> <span data-ttu-id="b0057-109">個々 の構成でサポートできるこの受信場所 1 メンバー、およびサーバー実行可能ファイルの複数のインスタンスを起動 — 各いずれか 1 つに専用の受信場所。</span><span class="sxs-lookup"><span data-stu-id="b0057-109">This can be supported by configuring an individual receive location per member and spawning multiple instances of the server executable — each one dedicated to one receive location.</span></span>  
  
 <span data-ttu-id="b0057-110">BizTalk Server では、受信アダプターは、BizTalk メッセージング エンジンと対話する次の通信パターンをサポートします。</span><span class="sxs-lookup"><span data-stu-id="b0057-110">In BizTalk Server, the receive adapter supports the following communication patterns to interact with the BizTalk Messaging Engine:</span></span>  
  
-   <span data-ttu-id="b0057-111">1 つの方法: 遅延モードで、受信アダプター (サーバー) が動作しているときは、このモードが必要です。</span><span class="sxs-lookup"><span data-stu-id="b0057-111">One way — this mode is required when the receive adapter (server) is operating in deferred mode.</span></span> <span data-ttu-id="b0057-112">遅延のモードでは、アダプターは、受信メッセージの既定の受信確認を送信します。</span><span class="sxs-lookup"><span data-stu-id="b0057-112">In deferred mode, the adapter sends a default acknowledgment for incoming messages.</span></span> <span data-ttu-id="b0057-113">受信確認の場合、既定値は、アダプターのプロパティで構成できます。</span><span class="sxs-lookup"><span data-stu-id="b0057-113">The default values for the acknowledgment can be configured in the adapter properties.</span></span> <span data-ttu-id="b0057-114">送信アダプターを経由して LOB アプリケーションによって、ビジネス レベルの応答を後で送信できます。</span><span class="sxs-lookup"><span data-stu-id="b0057-114">Business level response can be sent later by the LOB application through the send adapter.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b0057-115">遅延のモードが発生した場合のすべての値入力してくださいアダプターの構成にアダプターが、応答を構築するため。</span><span class="sxs-lookup"><span data-stu-id="b0057-115">In case of deferred mode, all values must be filled up in the adapter configuration, since the adapter is constructing the response.</span></span>  
  
-   <span data-ttu-id="b0057-116">要求-応答-このモードでは、アダプターは BizTalk に SWIFT からの要求を送信して、応答を待機します。</span><span class="sxs-lookup"><span data-stu-id="b0057-116">Request response — in this mode the adapter submits the request from SWIFT to BizTalk and waits for response.</span></span> <span data-ttu-id="b0057-117">アダプターであれば、タイムアウト、LOB アプリケーションから応答がありません。</span><span class="sxs-lookup"><span data-stu-id="b0057-117">The adapter would timeout if there is no response from the LOB application.</span></span> <span data-ttu-id="b0057-118">タイムアウト値は、アダプターの構成で構成できます。</span><span class="sxs-lookup"><span data-stu-id="b0057-118">The time out value is configurable in adapter configuration.</span></span> <span data-ttu-id="b0057-119">既定値は 60 秒です。</span><span class="sxs-lookup"><span data-stu-id="b0057-119">The default value is 60 seconds.</span></span>  
  
     <span data-ttu-id="b0057-120">受信アダプターは、1 つのスレッドでのみ、SNL からコールバックを受信できます。</span><span class="sxs-lookup"><span data-stu-id="b0057-120">The receive adapter can receive the callback from SNL only on one thread.</span></span> <span data-ttu-id="b0057-121">つまり、受信アダプターできますを受け取るさらにメッセージ SNL から最初のメッセージを送信した後のみです。</span><span class="sxs-lookup"><span data-stu-id="b0057-121">This means that the receive adapter can receive further messages from SNL only after submitting the first message.</span></span> <span data-ttu-id="b0057-122">したがって、既定のバッチ サイズは 1 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="b0057-122">Therefore, the default batch size is set to 1.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b0057-123">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b0057-123">In This Section</span></span>  
  
-   [<span data-ttu-id="b0057-124">SWIFT 受信アダプター URI</span><span class="sxs-lookup"><span data-stu-id="b0057-124">SWIFT Receive Adapter URI</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md)  
  
-   [<span data-ttu-id="b0057-125">SWIFT 受信アダプターの初期化</span><span class="sxs-lookup"><span data-stu-id="b0057-125">SWIFT Receive Adapter Initialization</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md)  
  
-   [<span data-ttu-id="b0057-126">SWIFT 受信アダプター セキュリティ コンテキスト</span><span class="sxs-lookup"><span data-stu-id="b0057-126">SWIFT Receive Adapter Security Context</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-security-context.md)  
  
-   [<span data-ttu-id="b0057-127">SWIFT 受信アダプターの同期および遅延モード</span><span class="sxs-lookup"><span data-stu-id="b0057-127">SWIFT Receive Adapter Synchronous and Deferred Modes</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-synchronous-and-deferred-modes.md)  
  
-   [<span data-ttu-id="b0057-128">SWIFT 受信アダプター ストア アンド フォワード</span><span class="sxs-lookup"><span data-stu-id="b0057-128">SWIFT Receive Adapter Store and Forward</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-store-and-forward.md)