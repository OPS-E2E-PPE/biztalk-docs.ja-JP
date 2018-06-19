---
title: SWIFT 送信アダプターのアーキテクチャ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e52a5a21-0aa1-4cd9-a2a4-f9df425913a0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d772203c980495c5aa62266beb060693c1a8ad8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223874"
---
# <a name="swift-send-adapter-architecture"></a><span data-ttu-id="108db-102">SWIFT 送信アダプターのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="108db-102">SWIFT Send Adapter Architecture</span></span>
<span data-ttu-id="108db-103">一般に、BizTalk Server 送信アダプターは BizTalk サービス プロセス Btsntsvc.exe でホストされます。</span><span class="sxs-lookup"><span data-stu-id="108db-103">In general, BizTalk Server send adapters are hosted in the BizTalk service process, Btsntsvc.exe.</span></span> <span data-ttu-id="108db-104">これは、BizTalk Server が、アダプターの有効期間を管理することを意味します。</span><span class="sxs-lookup"><span data-stu-id="108db-104">This means that BizTalk Server manages the lifetime of the adapter.</span></span>  
  
 <span data-ttu-id="108db-105">SWIFT ネットワークへのメッセージ送信の 2 つの方法: 同期 (ExchangeRequest) と非同期 (このリリースでは実装されていません)。</span><span class="sxs-lookup"><span data-stu-id="108db-105">There are two ways of sending messages to the SWIFT network: synchronous (ExchangeRequest) and asynchronous (not implemented for this release).</span></span> <span data-ttu-id="108db-106">BizTalk Server で、送信アダプターは、BizTalk メッセージング エンジンと対話する次の通信パターンをサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="108db-106">In BizTalk Server, the send adapter should support the following communication patterns to interact with the BizTalk Messaging Engine:</span></span>  
  
-   <span data-ttu-id="108db-107">応答を送信請求-SWIFT ネットワークとのプリミティブと呼ばれる、対でメッセージを交換します。</span><span class="sxs-lookup"><span data-stu-id="108db-107">Solicit response — messages are exchanged in pairs, called the primitives, with the SWIFT network.</span></span> <span data-ttu-id="108db-108">SWIFT に送信されたメッセージは、これは、ビジネス、受信確認またはエラー応答があります。</span><span class="sxs-lookup"><span data-stu-id="108db-108">Any messages sent to SWIFT will have a response be it business, acknowledgement or error.</span></span> <span data-ttu-id="108db-109">メッセージ ボックスには、応答メッセージが送信されます。</span><span class="sxs-lookup"><span data-stu-id="108db-109">The response message is submitted back to messagebox.</span></span> <span data-ttu-id="108db-110">この操作モードは、リアルタイムの通信に使用されます。</span><span class="sxs-lookup"><span data-stu-id="108db-110">This mode of operation is used for Real-Time communication.</span></span>  
  
-   <span data-ttu-id="108db-111">一方向送信 — 1 つの方法で構成されている場合、アダプターはストアと転送モードで動作します。</span><span class="sxs-lookup"><span data-stu-id="108db-111">One way send — the adapter when configured in one way operates in store and forward mode.</span></span> <span data-ttu-id="108db-112">メッセージは、受信者ではなく、事前に構成されたキューに送信されます。</span><span class="sxs-lookup"><span data-stu-id="108db-112">The messages are sent to a preconfigured queue as opposed to a receipient.</span></span> <span data-ttu-id="108db-113">送信者は、プッシュまたはプル モードでキューにセッションを開くことによって、応答を取得できます。</span><span class="sxs-lookup"><span data-stu-id="108db-113">The sender can retrieve the response by opening a session with the queue in push or pull mode.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="108db-114">アダプターを作成する方法では、動作方法に影響します。</span><span class="sxs-lookup"><span data-stu-id="108db-114">The way you create the adapter affects the way it operates.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="108db-115">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="108db-115">In This Section</span></span>  
  
-   [<span data-ttu-id="108db-116">SWIFT 送信アダプター URI</span><span class="sxs-lookup"><span data-stu-id="108db-116">SWIFT Send Adapter URI</span></span>](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-uri.md)  
  
-   [<span data-ttu-id="108db-117">SWIFT 送信アダプターの動的送信</span><span class="sxs-lookup"><span data-stu-id="108db-117">SWIFT Send Adapter Dynamic Send</span></span>](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-dynamic-send.md)  
  
-   [<span data-ttu-id="108db-118">SWIFT 送信アダプターの初期化</span><span class="sxs-lookup"><span data-stu-id="108db-118">SWIFT Send Adapter Initialization</span></span>](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-initialization.md)  
  
-   [<span data-ttu-id="108db-119">SWIFT 送信アダプター同期モード</span><span class="sxs-lookup"><span data-stu-id="108db-119">SWIFT Send Adapter Synchronous Mode</span></span>](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-synchronous-mode.md)  
  
-   [<span data-ttu-id="108db-120">SWIFT 送信アダプターの終了</span><span class="sxs-lookup"><span data-stu-id="108db-120">SWIFT Send Adapter Termination</span></span>](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-termination.md)