---
title: SWIFT 受信アダプターのストア アンド フォワード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 11eeb335-366b-4b29-9078-de9396b258ca
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1744f86cc10bfe37b1a4c7814c31e6e2e8812507
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364381"
---
# <a name="swift-receive-adapter-store-and-forward"></a><span data-ttu-id="4250e-102">SWIFT 受信アダプターのストア アンド フォワード</span><span class="sxs-lookup"><span data-stu-id="4250e-102">SWIFT Receive Adapter Store and Forward</span></span>
<span data-ttu-id="4250e-103">受信アダプターは、SWIFT ストア アンド フォワード (SnF) キューからメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="4250e-103">The receive adapter receives messages from the SWIFT store and forward (SnF) queue.</span></span> <span data-ttu-id="4250e-104">キューからメッセージを受信するには、アダプターは SnF キューでセッションを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="4250e-104">To receive messages from the queue, the adapter must open a session with the SnF queue.</span></span> <span data-ttu-id="4250e-105">キューを開くには、キューとのセッションを確立する専用のクライアント プロセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="4250e-105">To open the queue, it must have a dedicated client process that establishes the session with the queue.</span></span> <span data-ttu-id="4250e-106">設計では、このプロセスは、COM + のアウト プロセス コンポーネントとして実装されます。</span><span class="sxs-lookup"><span data-stu-id="4250e-106">In the design, this process is implemented as a COM plus out-of-proc component.</span></span>  
  
## <a name="push-session-store-and-forward-sequence"></a><span data-ttu-id="4250e-107">セッション ストア アンド フォワードのシーケンスをプッシュします。</span><span class="sxs-lookup"><span data-stu-id="4250e-107">Push session store and forward sequence</span></span>  
 <span data-ttu-id="4250e-108">次の一覧には、ストア アンド フォワードのシーケンスがについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4250e-108">The following list describes the store and forward sequence.</span></span>  
  
1.  <span data-ttu-id="4250e-109">メッセージを処理するサーバー アプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="4250e-109">Start the server application that processes the messages.</span></span>  
  
2.  <span data-ttu-id="4250e-110">サーバー プロセスは、入力プリミティブとして、Sw:HandleInitRequest で最初の SwCallback 中に必要なセキュリティ コンテキストを開きます。</span><span class="sxs-lookup"><span data-stu-id="4250e-110">The server process opens the required security contexts during the first SwCallback with the Sw:HandleInitRequest as an input primitive.</span></span>  
  
3.  <span data-ttu-id="4250e-111">サーバーは、Sw:CryptoMode と Sw:FACryptoMode 高度な設定のいずれかまたは両方 Sw:HandleInitRequest に応答します。</span><span class="sxs-lookup"><span data-stu-id="4250e-111">The server responds to the Sw:HandleInitRequest with either or both Sw:CryptoMode and Sw:FACryptoMode set to Advanced.</span></span>  
  
     <span data-ttu-id="4250e-112">サーバーは、受信要求の処理を開始する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="4250e-112">The server is now ready to start processing incoming requests.</span></span>  
  
4.  <span data-ttu-id="4250e-113">キューからメッセージの配信を開始するには、クライアント プロセスは、プッシュ セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="4250e-113">To start the delivery of messages from a queue, a client process starts a push session.</span></span> <span data-ttu-id="4250e-114">アダプターの構成 (プッシュ モード) に基づいて、受信アダプターは、プッシュ モードでキューを取得する SnFQueueManager.exe と呼ばれるクライアント プロセスを生成します。</span><span class="sxs-lookup"><span data-stu-id="4250e-114">Based on the adapter configuration (push mode), the receive adapter spawns a client process called SnFQueueManager.exe to acquire the queue in push mode.</span></span>  
  
5.  <span data-ttu-id="4250e-115">(内 Sw:ExchangeSnFRequest) Sw:AcquireSnFRequest 入力プリミティブとして、SwCall() が実行されます。</span><span class="sxs-lookup"><span data-stu-id="4250e-115">An SwCall() runs with Sw:AcquireSnFRequest (within the Sw:ExchangeSnFRequest) as an input primitive.</span></span> <span data-ttu-id="4250e-116">この要求が示されるキューと、セッションを開始 (かどうか、SwSec:AuthorisationContext が必要な RBAC ロール)。</span><span class="sxs-lookup"><span data-stu-id="4250e-116">This request starts a session with the queue indicated (if the SwSec:AuthorisationContext has the required RBAC role).</span></span>  
  
6.  <span data-ttu-id="4250e-117">"Accepted"で、Sw:AcquireStatus で応答した直後に SWIFTNet SnF は、取得で指定されているサーバーにメッセージを送信を開始します。</span><span class="sxs-lookup"><span data-stu-id="4250e-117">Immediately after responding with “Accepted” in the Sw:AcquireStatus, SWIFTNet SnF starts sending messages to the server as specified in the acquire.</span></span> <span data-ttu-id="4250e-118">受信アダプターがまだ開始されていない場合、メッセージは、例外を取得します。</span><span class="sxs-lookup"><span data-stu-id="4250e-118">If the receive adapter was not yet started, messages get exceptions.</span></span> <span data-ttu-id="4250e-119">(いるため、受信アダプターが既に開始することが重要) です。</span><span class="sxs-lookup"><span data-stu-id="4250e-119">(That is why it is important to have the receive adapters already started).</span></span>  
  
7.  <span data-ttu-id="4250e-120">SWIFTNet SnF (最大ウィンドウ サイズ) のメッセージ数のプッシュを開始します。</span><span class="sxs-lookup"><span data-stu-id="4250e-120">SWIFTNet SnF starts pushing a number of messages (up to the window size).</span></span>  
  
8.  <span data-ttu-id="4250e-121">すべてのメッセージが受信確認 (ある場合)、新しいメッセージがプッシュされます。</span><span class="sxs-lookup"><span data-stu-id="4250e-121">For every message acknowledged, a new message (if any) is pushed.</span></span>  
  
9. <span data-ttu-id="4250e-122">クライアント プロセス (SnFQueueManager.exe) は、そのジョブで実行され、終了するようになりました。</span><span class="sxs-lookup"><span data-stu-id="4250e-122">The client process (SnFQueueManager.exe) has done its job and can now terminate.</span></span> <span data-ttu-id="4250e-123">プロセスは、オープンなセキュリティ コンテキストをクリーンアップする SwSec:DestroyContextRequest を発行します。</span><span class="sxs-lookup"><span data-stu-id="4250e-123">The process issues SwSec:DestroyContextRequest, which cleans up the open security contexts.</span></span> <span data-ttu-id="4250e-124">Sw:TermRequest 後、プロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="4250e-124">After the Sw:TermRequest, the process exits.</span></span>  
  
### <a name="message-correlation"></a><span data-ttu-id="4250e-125">メッセージの関連付け</span><span class="sxs-lookup"><span data-stu-id="4250e-125">Message Correlation</span></span>  
 <span data-ttu-id="4250e-126">RequestRef フィールドは保持され、応答メッセージに戻り、受信アダプターによって代わりに使用します。</span><span class="sxs-lookup"><span data-stu-id="4250e-126">The RequestRef field is preserved and substituted back in the response messages by the receive adapter.</span></span> <span data-ttu-id="4250e-127">これにより、受信メッセージと応答メッセージの間のエンド ツー エンドの相関関係</span><span class="sxs-lookup"><span data-stu-id="4250e-127">This ensures end to end correlation between the incoming message and the response message</span></span>  
  
### <a name="duplicate-processing"></a><span data-ttu-id="4250e-128">重複した処理</span><span class="sxs-lookup"><span data-stu-id="4250e-128">Duplicate processing</span></span>  
 <span data-ttu-id="4250e-129">FileAct 要求、およびアダプターのインスタンスを受信している場合は、参照先の転送が正常に完了既にか、または失敗したかを確認して適切なアクションを実行する必要がありますを可能な複製のインジケーターのノードでは、メッセージを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="4250e-129">If receiving a FileAct request, and the adapter instance receives a message with a Possible Duplicate Indicator node, then it must check to see if the referenced transfer has already completed successfully or if it has failed, and take the appropriate action.</span></span> <span data-ttu-id="4250e-130">ファイル転送が既にが発生した場合、アダプターは、"Duplicate"として転送状態を更新し、それ以外の場合、更新し、「受理します」</span><span class="sxs-lookup"><span data-stu-id="4250e-130">If the file transfer has already taken place then the adapter updates the transfer status as “Duplicate” otherwise it updates it as “Accepted.”</span></span>  
  
### <a name="acknowledgments"></a><span data-ttu-id="4250e-131">受信確認</span><span class="sxs-lookup"><span data-stu-id="4250e-131">Acknowledgments</span></span>  
 <span data-ttu-id="4250e-132">FileAct 要求の受信確認を送信者に要求している場合、アダプターはファイル転送の完了イベントをチェックし、ファイルのダイジェスト値を確認した後、受信確認を生成します。</span><span class="sxs-lookup"><span data-stu-id="4250e-132">If the sender requests an acknowledgement for a FileAct request, the adapter checks for the file transfer completion event and generates the acknowledgement after verifying the file digest value.</span></span> <span data-ttu-id="4250e-133">アダプターは、BizTalk を取得し、送信者に送信する送信アダプターに受信確認メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="4250e-133">The adapter sends the acknowledgement message to BizTalk for the send adapter to pick it up and send it to the sender.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4250e-134">参照</span><span class="sxs-lookup"><span data-stu-id="4250e-134">See Also</span></span>  
 <span data-ttu-id="4250e-135">[SWIFT 受信アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="4250e-135">[SWIFT Receive Adapter Architecture](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md) </span></span>  
 <span data-ttu-id="4250e-136">[SWIFT 受信アダプターの URI](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md) </span><span class="sxs-lookup"><span data-stu-id="4250e-136">[SWIFT Receive Adapter URI](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md) </span></span>  
 <span data-ttu-id="4250e-137">[SWIFT 受信アダプターの初期化](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md) </span><span class="sxs-lookup"><span data-stu-id="4250e-137">[SWIFT Receive Adapter Initialization](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md) </span></span>  
 <span data-ttu-id="4250e-138">[SWIFT 受信アダプター セキュリティ コンテキスト](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-security-context.md) </span><span class="sxs-lookup"><span data-stu-id="4250e-138">[SWIFT Receive Adapter Security Context](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-security-context.md) </span></span>  
 [<span data-ttu-id="4250e-139">SWIFT 受信アダプターの同期および遅延モード</span><span class="sxs-lookup"><span data-stu-id="4250e-139">SWIFT Receive Adapter Synchronous and Deferred Modes</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-synchronous-and-deferred-modes.md)