---
title: "FileAct を理解し、アダプターのアーキテクチャの対話 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f97a7fe-20df-4509-bb6e-53743c3a57df
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c04d0ba8b1c2bbd99a71e3d76c8d7ad60c251147
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="understanding-fileact-and-interact-adapter-architecture"></a><span data-ttu-id="dd2ce-102">FileAct を理解し、アダプターのアーキテクチャの対話</span><span class="sxs-lookup"><span data-stu-id="dd2ce-102">Understanding FileAct and InterAct Adapter Architecture</span></span>
<span data-ttu-id="dd2ce-103">SWIFT アダプターは、BizTalk アダプター フレームワークに基づいています。</span><span class="sxs-lookup"><span data-stu-id="dd2ce-103">The SWIFT Adapter is based on the BizTalk Adapter Framework.</span></span> <span data-ttu-id="dd2ce-104">BizTalk Server 内のアダプターの分類を使用して、SWIFT アダプター, FileAct および InterAct、意味は次の。</span><span class="sxs-lookup"><span data-stu-id="dd2ce-104">Using the classifications of adapters within BizTalk Server, the SWIFT adapters, FileAct and InterAct, represent the following:</span></span>  
  
-   <span data-ttu-id="dd2ce-105">カスタム アダプター。</span><span class="sxs-lookup"><span data-stu-id="dd2ce-105">Custom Adapter.</span></span> <span data-ttu-id="dd2ce-106">これは、カスタム アダプター FileAct および Interact と呼ばれる独自の標準を使用する SWIFT ネットワークと対話するための専用です。</span><span class="sxs-lookup"><span data-stu-id="dd2ce-106">This is a custom adapter built specifically to interact with the SWIFT network using a proprietary standard called FileAct and Interact.</span></span>  
  
-   <span data-ttu-id="dd2ce-107">トランスポート アダプターです。</span><span class="sxs-lookup"><span data-stu-id="dd2ce-107">Transport Adapter.</span></span> <span data-ttu-id="dd2ce-108">このアダプターは、SWIFT ネットワークは、メッセージを送受信するビジネス ソフトウェア アプリケーションを許可します。</span><span class="sxs-lookup"><span data-stu-id="dd2ce-108">This adapter allows business software application to send and receive messages with the SWIFT network.</span></span>  
  
-   <span data-ttu-id="dd2ce-109">非トランザクションです。</span><span class="sxs-lookup"><span data-stu-id="dd2ce-109">Non-transacted.</span></span> <span data-ttu-id="dd2ce-110">アダプターは加えません SWIFT ネットワークと対話する任意のトランザクション オブジェクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="dd2ce-110">The adapter does not make use of any transaction object to interact with the SWIFT network.</span></span>  
  
-   <span data-ttu-id="dd2ce-111">分離。</span><span class="sxs-lookup"><span data-stu-id="dd2ce-111">Isolated.</span></span> <span data-ttu-id="dd2ce-112">受信アダプターが別のプロセスで実行し、プロセスで正規の送信アダプターを実行します。</span><span class="sxs-lookup"><span data-stu-id="dd2ce-112">The receive adapter runs in a separate process and regular send adapters run in process.</span></span>  
  
 <span data-ttu-id="dd2ce-113">BizTalk アダプター フレームワークの詳細については、次を参照してください、は、アダプター フレームワーク?"。</span><span class="sxs-lookup"><span data-stu-id="dd2ce-113">For information about the BizTalk Adapter Framework, see the "What Is the Adapter Framework?"</span></span> <span data-ttu-id="dd2ce-114">BizTalk Server ヘルプのトピックです。</span><span class="sxs-lookup"><span data-stu-id="dd2ce-114">topic in BizTalk Server Help.</span></span>  
  
 <span data-ttu-id="dd2ce-115">次の図は、FileAct および InterAct アーキテクチャの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="dd2ce-115">The following figure shows a high-level view of the FileAct and InterAct architecture.</span></span>  
  
 ![](../../adapters-and-accelerators/fileact-interact/media/035ebb05-ce11-447c-b56b-ba8b41e07e50.gif "035ebb05-ce11-447c-b56b-ba8b41e07e50")  
  
> [!NOTE]
>  <span data-ttu-id="dd2ce-116">Microsoft[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]厳格モードの SWIFTNet リンク (SNL) API のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="dd2ce-116">Microsoft [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] supports only strict mode SWIFTNet Link (SNL) API.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dd2ce-117">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="dd2ce-117">In This Section</span></span>  
  
-   [<span data-ttu-id="dd2ce-118">SWIFTNet クライアントとサーバー</span><span class="sxs-lookup"><span data-stu-id="dd2ce-118">SWIFTNet Client and Server</span></span>](../../adapters-and-accelerators/fileact-interact/swiftnet-client-and-server.md)  
  
-   [<span data-ttu-id="dd2ce-119">SWIFT 送信アダプターのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="dd2ce-119">SWIFT Send Adapter Architecture</span></span>](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-architecture.md)  
  
-   [<span data-ttu-id="dd2ce-120">SWIFT 受信アダプターのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="dd2ce-120">SWIFT Receive Adapter Architecture</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md)  
  
-   [<span data-ttu-id="dd2ce-121">FileAct アダプターのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="dd2ce-121">FileAct Adapter Architecture</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)  
  
-   [<span data-ttu-id="dd2ce-122">アダプターのアーキテクチャを対話します。</span><span class="sxs-lookup"><span data-stu-id="dd2ce-122">InterAct Adapter Architecture</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)