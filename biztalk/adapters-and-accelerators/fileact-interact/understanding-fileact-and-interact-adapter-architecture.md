---
title: 理解 FileAct および InterAct アダプターのアーキテクチャ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f97a7fe-20df-4509-bb6e-53743c3a57df
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b1a6b5cf310dfd7e65cba21364cbccc385300df
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364076"
---
# <a name="understanding-fileact-and-interact-adapter-architecture"></a><span data-ttu-id="df967-102">理解 FileAct および InterAct アダプターのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="df967-102">Understanding FileAct and InterAct Adapter Architecture</span></span>
<span data-ttu-id="df967-103">SWIFT アダプターは、BizTalk アダプター フレームワークに基づきます。</span><span class="sxs-lookup"><span data-stu-id="df967-103">The SWIFT Adapter is based on the BizTalk Adapter Framework.</span></span> <span data-ttu-id="df967-104">BizTalk Server 内のアダプターの分類を使用して、FileAct および InterAct は、SWIFT アダプターを表す次。</span><span class="sxs-lookup"><span data-stu-id="df967-104">Using the classifications of adapters within BizTalk Server, the SWIFT adapters, FileAct and InterAct, represent the following:</span></span>  
  
- <span data-ttu-id="df967-105">カスタム アダプター。</span><span class="sxs-lookup"><span data-stu-id="df967-105">Custom Adapter.</span></span> <span data-ttu-id="df967-106">これは、カスタム アダプター FileAct および Interact と呼ばれる独自の標準を使用する SWIFT ネットワークとやり取りするための専用です。</span><span class="sxs-lookup"><span data-stu-id="df967-106">This is a custom adapter built specifically to interact with the SWIFT network using a proprietary standard called FileAct and Interact.</span></span>  
  
- <span data-ttu-id="df967-107">トランスポート アダプターです。</span><span class="sxs-lookup"><span data-stu-id="df967-107">Transport Adapter.</span></span> <span data-ttu-id="df967-108">このアダプターは、SWIFT ネットワークとのメッセージを送受信する業務ソフトウェア アプリケーションを許可します。</span><span class="sxs-lookup"><span data-stu-id="df967-108">This adapter allows business software application to send and receive messages with the SWIFT network.</span></span>  
  
- <span data-ttu-id="df967-109">非トランザクションです。</span><span class="sxs-lookup"><span data-stu-id="df967-109">Non-transacted.</span></span> <span data-ttu-id="df967-110">アダプターを行わないの任意のトランザクション オブジェクトを使用して行う SWIFT ネットワークとやり取りします。</span><span class="sxs-lookup"><span data-stu-id="df967-110">The adapter does not make use of any transaction object to interact with the SWIFT network.</span></span>  
  
- <span data-ttu-id="df967-111">分離します。</span><span class="sxs-lookup"><span data-stu-id="df967-111">Isolated.</span></span> <span data-ttu-id="df967-112">受信アダプターが別のプロセスで実行し、通常の送信アダプターはプロセスで実行します。</span><span class="sxs-lookup"><span data-stu-id="df967-112">The receive adapter runs in a separate process and regular send adapters run in process.</span></span>  
  
  <span data-ttu-id="df967-113">BizTalk アダプター フレームワークについては、次を参照してください、"とは、アダプター フレームワーク"。</span><span class="sxs-lookup"><span data-stu-id="df967-113">For information about the BizTalk Adapter Framework, see the "What Is the Adapter Framework?"</span></span> <span data-ttu-id="df967-114">BizTalk Server ヘルプのトピックです。</span><span class="sxs-lookup"><span data-stu-id="df967-114">topic in BizTalk Server Help.</span></span>  
  
  <span data-ttu-id="df967-115">FileAct および InterAct のアーキテクチャの概要を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="df967-115">The following figure shows a high-level view of the FileAct and InterAct architecture.</span></span>  
  
  <span data-ttu-id="df967-116">![](../../adapters-and-accelerators/fileact-interact/media/035ebb05-ce11-447c-b56b-ba8b41e07e50.gif "035ebb05-ce11-447c-b56b-ba8b41e07e50")</span><span class="sxs-lookup"><span data-stu-id="df967-116">![](../../adapters-and-accelerators/fileact-interact/media/035ebb05-ce11-447c-b56b-ba8b41e07e50.gif "035ebb05-ce11-447c-b56b-ba8b41e07e50")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="df967-117">Microsoft[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]厳格モード SWIFTNet リンク (SNL) API のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="df967-117">Microsoft [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] supports only strict mode SWIFTNet Link (SNL) API.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="df967-118">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="df967-118">In This Section</span></span>  
  
-   [<span data-ttu-id="df967-119">SWIFTNet クライアントおよびサーバー</span><span class="sxs-lookup"><span data-stu-id="df967-119">SWIFTNet Client and Server</span></span>](../../adapters-and-accelerators/fileact-interact/swiftnet-client-and-server.md)  
  
-   [<span data-ttu-id="df967-120">SWIFT 送信アダプターのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="df967-120">SWIFT Send Adapter Architecture</span></span>](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-architecture.md)  
  
-   [<span data-ttu-id="df967-121">SWIFT 受信アダプターのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="df967-121">SWIFT Receive Adapter Architecture</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md)  
  
-   [<span data-ttu-id="df967-122">FileAct アダプターのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="df967-122">FileAct Adapter Architecture</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)  
  
-   [<span data-ttu-id="df967-123">InterAct アダプターのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="df967-123">InterAct Adapter Architecture</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)