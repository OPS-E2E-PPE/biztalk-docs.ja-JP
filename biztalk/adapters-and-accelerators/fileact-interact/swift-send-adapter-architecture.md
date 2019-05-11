---
title: SWIFT 送信アダプターのアーキテクチャ |Microsoft Docs
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
ms.openlocfilehash: a4347680cf4fa1434e72e80c74debe0ca2de8d47
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364182"
---
# <a name="swift-send-adapter-architecture"></a><span data-ttu-id="0652c-102">SWIFT 送信アダプターのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="0652c-102">SWIFT Send Adapter Architecture</span></span>
<span data-ttu-id="0652c-103">一般に、BizTalk Server 送信アダプターは、BizTalk サービス プロセス Btsntsvc.exe でホストされます。</span><span class="sxs-lookup"><span data-stu-id="0652c-103">In general, BizTalk Server send adapters are hosted in the BizTalk service process, Btsntsvc.exe.</span></span> <span data-ttu-id="0652c-104">これは、BizTalk Server がアダプターの有効期間を管理することを意味します。</span><span class="sxs-lookup"><span data-stu-id="0652c-104">This means that BizTalk Server manages the lifetime of the adapter.</span></span>  
  
 <span data-ttu-id="0652c-105">SWIFT ネットワークへのメッセージ送信の 2 つの方法: 同期 (ExchangeRequest) と非同期 (このリリースでは実装されていません)。</span><span class="sxs-lookup"><span data-stu-id="0652c-105">There are two ways of sending messages to the SWIFT network: synchronous (ExchangeRequest) and asynchronous (not implemented for this release).</span></span> <span data-ttu-id="0652c-106">BizTalk Server で、送信アダプターは、BizTalk メッセージング エンジンと対話する次の通信パターンをサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0652c-106">In BizTalk Server, the send adapter should support the following communication patterns to interact with the BizTalk Messaging Engine:</span></span>  
  
-   <span data-ttu-id="0652c-107">応答の送信請求-SWIFT ネットワークと、プリミティブと呼ばれる、ペアで交換されるメッセージ。</span><span class="sxs-lookup"><span data-stu-id="0652c-107">Solicit response — messages are exchanged in pairs, called the primitives, with the SWIFT network.</span></span> <span data-ttu-id="0652c-108">SWIFT へ送信されたメッセージは、これは、ビジネス、受信確認またはエラー応答があります。</span><span class="sxs-lookup"><span data-stu-id="0652c-108">Any messages sent to SWIFT will have a response be it business, acknowledgement or error.</span></span> <span data-ttu-id="0652c-109">応答メッセージは、メッセージ ボックスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="0652c-109">The response message is submitted back to messagebox.</span></span> <span data-ttu-id="0652c-110">この操作モードでは、リアルタイム通信に使用されます。</span><span class="sxs-lookup"><span data-stu-id="0652c-110">This mode of operation is used for Real-Time communication.</span></span>  
  
-   <span data-ttu-id="0652c-111">一方向の送信: 1 つの方法で構成されている場合、アダプターは、ストアと転送モードで動作します。</span><span class="sxs-lookup"><span data-stu-id="0652c-111">One way send — the adapter when configured in one way operates in store and forward mode.</span></span> <span data-ttu-id="0652c-112">メッセージは、事前構成済みのキューの受信者とは対照的に送信されます。</span><span class="sxs-lookup"><span data-stu-id="0652c-112">The messages are sent to a preconfigured queue as opposed to a receipient.</span></span> <span data-ttu-id="0652c-113">送信者は、プッシュまたはプル モードでのキューでセッションを開いて、応答を取得できます。</span><span class="sxs-lookup"><span data-stu-id="0652c-113">The sender can retrieve the response by opening a session with the queue in push or pull mode.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0652c-114">アダプターを作成する方法は、動作方法に影響します。</span><span class="sxs-lookup"><span data-stu-id="0652c-114">The way you create the adapter affects the way it operates.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0652c-115">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="0652c-115">In This Section</span></span>  
  
-   [<span data-ttu-id="0652c-116">SWIFT 送信アダプターの URI</span><span class="sxs-lookup"><span data-stu-id="0652c-116">SWIFT Send Adapter URI</span></span>](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-uri.md)  
  
-   [<span data-ttu-id="0652c-117">SWIFT 送信アダプターの動的送信</span><span class="sxs-lookup"><span data-stu-id="0652c-117">SWIFT Send Adapter Dynamic Send</span></span>](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-dynamic-send.md)  
  
-   [<span data-ttu-id="0652c-118">SWIFT 送信アダプターの初期化</span><span class="sxs-lookup"><span data-stu-id="0652c-118">SWIFT Send Adapter Initialization</span></span>](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-initialization.md)  
  
-   [<span data-ttu-id="0652c-119">SWIFT 送信アダプターの同期モード</span><span class="sxs-lookup"><span data-stu-id="0652c-119">SWIFT Send Adapter Synchronous Mode</span></span>](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-synchronous-mode.md)  
  
-   [<span data-ttu-id="0652c-120">SWIFT 送信アダプターの終了</span><span class="sxs-lookup"><span data-stu-id="0652c-120">SWIFT Send Adapter Termination</span></span>](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-termination.md)