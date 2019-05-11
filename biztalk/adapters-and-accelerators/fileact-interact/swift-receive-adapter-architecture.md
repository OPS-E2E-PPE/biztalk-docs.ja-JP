---
title: SWIFT 受信アダプターのアーキテクチャ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 16f32689-0b70-4389-8596-991fd776f185
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23deda6ba243e3b6823f5b8b80e560260c45fc7d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364616"
---
# <a name="swift-receive-adapter-architecture"></a><span data-ttu-id="dbafa-102">SWIFT 受信アダプターのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="dbafa-102">SWIFT Receive Adapter Architecture</span></span>
<span data-ttu-id="dbafa-103">BizTalk Server で、受信アダプターはホストを実行する別のプロセスが作成されたことを意味する独自のメモリ領域内でホストされます。</span><span class="sxs-lookup"><span data-stu-id="dbafa-103">In BizTalk Server, the receive adapter is hosted within its own memory space, which means a separate process is created to run the host.</span></span> <span data-ttu-id="dbafa-104">SWIFTNet リンク (SNL) 構成では、サブシステムを定義することでこのホストが生成されます。</span><span class="sxs-lookup"><span data-stu-id="dbafa-104">This host is spawned by defining a subsystem in the SWIFTNet Link (SNL) configuration.</span></span>  
  
 <span data-ttu-id="dbafa-105">サーバーの実行可能ファイルは SNL 構成 (に paramfile) サブシステムとして構成し、SWIFTNet Start コマンドを実行することが生成されます。</span><span class="sxs-lookup"><span data-stu-id="dbafa-105">The server executable is configured as a subsystem in the SNL configuration (paramfile) and is spawned by executing the SWIFTNet Start command.</span></span> <span data-ttu-id="dbafa-106">SNL サーバー アプリケーションは SWIFTNet 停止コマンドを実行して終了します。</span><span class="sxs-lookup"><span data-stu-id="dbafa-106">The SNL server application is terminated by executing the SWIFTNet Stop command.</span></span> <span data-ttu-id="dbafa-107">SNL は、サーバー実行可能ファイルの有効期間を管理します。</span><span class="sxs-lookup"><span data-stu-id="dbafa-107">SNL manages the lifetime of the server executable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dbafa-108">サービスの局シナリオでは、独自のセキュリティ コンテキストで実行されている SWIFT メンバーを複数のサービスを提供するアダプターが必要です。</span><span class="sxs-lookup"><span data-stu-id="dbafa-108">The service bureau scenario requires the adapter to service multiple SWIFT members running under their own security contexts.</span></span> <span data-ttu-id="dbafa-109">個人を構成することによってサポートされるこの受信場所ごとのメンバーとサーバーの実行可能ファイルの複数のインスタンスを生成-それぞれ専用の 1 つの受信場所。</span><span class="sxs-lookup"><span data-stu-id="dbafa-109">This can be supported by configuring an individual receive location per member and spawning multiple instances of the server executable — each one dedicated to one receive location.</span></span>  
  
 <span data-ttu-id="dbafa-110">BizTalk Server では、受信アダプターは、BizTalk メッセージング エンジンと対話する次の通信パターンをサポートします。</span><span class="sxs-lookup"><span data-stu-id="dbafa-110">In BizTalk Server, the receive adapter supports the following communication patterns to interact with the BizTalk Messaging Engine:</span></span>  
  
-   <span data-ttu-id="dbafa-111">1 つの方法-受信アダプター (サーバー) を遅延モードで動作しているときは、このモードが必要です。</span><span class="sxs-lookup"><span data-stu-id="dbafa-111">One way — this mode is required when the receive adapter (server) is operating in deferred mode.</span></span> <span data-ttu-id="dbafa-112">遅延のモードでは、アダプターは、受信メッセージの既定の受信確認を送信します。</span><span class="sxs-lookup"><span data-stu-id="dbafa-112">In deferred mode, the adapter sends a default acknowledgment for incoming messages.</span></span> <span data-ttu-id="dbafa-113">受信確認用の既定値は、アダプターのプロパティで構成できます。</span><span class="sxs-lookup"><span data-stu-id="dbafa-113">The default values for the acknowledgment can be configured in the adapter properties.</span></span> <span data-ttu-id="dbafa-114">送信アダプター経由で LOB アプリケーションで、ビジネス レベルの応答を後で送信できます。</span><span class="sxs-lookup"><span data-stu-id="dbafa-114">Business level response can be sent later by the LOB application through the send adapter.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dbafa-115">遅延のモードが発生した場合のすべての値必要がありますを入力するアダプターの構成では、アダプターが、応答を構築するため。</span><span class="sxs-lookup"><span data-stu-id="dbafa-115">In case of deferred mode, all values must be filled up in the adapter configuration, since the adapter is constructing the response.</span></span>  
  
-   <span data-ttu-id="dbafa-116">要求-応答: このモードでは、アダプターが BizTalk には、SWIFT からの要求を送信して、応答を待機します。</span><span class="sxs-lookup"><span data-stu-id="dbafa-116">Request response — in this mode the adapter submits the request from SWIFT to BizTalk and waits for response.</span></span> <span data-ttu-id="dbafa-117">アダプターは、LOB アプリケーションからの応答がない場合、タイムアウトが。</span><span class="sxs-lookup"><span data-stu-id="dbafa-117">The adapter would timeout if there is no response from the LOB application.</span></span> <span data-ttu-id="dbafa-118">タイムアウト値は、アダプターの構成で構成できます。</span><span class="sxs-lookup"><span data-stu-id="dbafa-118">The time out value is configurable in adapter configuration.</span></span> <span data-ttu-id="dbafa-119">既定値は 60 秒です。</span><span class="sxs-lookup"><span data-stu-id="dbafa-119">The default value is 60 seconds.</span></span>  
  
     <span data-ttu-id="dbafa-120">受信アダプターは、1 つのスレッドでのみ、SNL からコールバックを受信できます。</span><span class="sxs-lookup"><span data-stu-id="dbafa-120">The receive adapter can receive the callback from SNL only on one thread.</span></span> <span data-ttu-id="dbafa-121">つまり、受信アダプターできます受信さらにメッセージ SNL から最初のメッセージを送信した後のみです。</span><span class="sxs-lookup"><span data-stu-id="dbafa-121">This means that the receive adapter can receive further messages from SNL only after submitting the first message.</span></span> <span data-ttu-id="dbafa-122">そのため、既定のバッチ サイズは 1 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="dbafa-122">Therefore, the default batch size is set to 1.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dbafa-123">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="dbafa-123">In This Section</span></span>  
  
-   [<span data-ttu-id="dbafa-124">SWIFT 受信アダプターの URI</span><span class="sxs-lookup"><span data-stu-id="dbafa-124">SWIFT Receive Adapter URI</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md)  
  
-   [<span data-ttu-id="dbafa-125">SWIFT 受信アダプターの初期化</span><span class="sxs-lookup"><span data-stu-id="dbafa-125">SWIFT Receive Adapter Initialization</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md)  
  
-   [<span data-ttu-id="dbafa-126">SWIFT 受信アダプター セキュリティ コンテキスト</span><span class="sxs-lookup"><span data-stu-id="dbafa-126">SWIFT Receive Adapter Security Context</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-security-context.md)  
  
-   [<span data-ttu-id="dbafa-127">SWIFT 受信アダプターの同期および遅延モード</span><span class="sxs-lookup"><span data-stu-id="dbafa-127">SWIFT Receive Adapter Synchronous and Deferred Modes</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-synchronous-and-deferred-modes.md)  
  
-   [<span data-ttu-id="dbafa-128">SWIFT 受信アダプターのストア アンド フォワード</span><span class="sxs-lookup"><span data-stu-id="dbafa-128">SWIFT Receive Adapter Store and Forward</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-store-and-forward.md)