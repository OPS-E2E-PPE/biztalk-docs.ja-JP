---
title: "プライベート プロセス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- private processes, trading partners
- private processes, about private processes
- private processes, orchestrations
- private processes
- orchestrations, private-process orchestrations
- trading partners, private processes
- BTARN, private processes
- business processes, private processes
ms.assetid: 0c5895eb-22c1-431f-a769-ae6ca05d1e45
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b28bf49af1305220d96f129080b274b5391495eb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="private-processes"></a><span data-ttu-id="6e7f0-102">プライベート プロセス</span><span class="sxs-lookup"><span data-stu-id="6e7f0-102">Private Processes</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="6e7f0-103">[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]プライベート プロセスとして組織の内部には、ビジネス プロセスを実装します。</span><span class="sxs-lookup"><span data-stu-id="6e7f0-103"> [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] implements business processes that are internal to an organization as private processes.</span></span> <span data-ttu-id="6e7f0-104">パブリック プロセスは、取引先との統合を伴うビジネス プロセスを処理します。</span><span class="sxs-lookup"><span data-stu-id="6e7f0-104">Public processes handle business processes that involve integration with trading partners.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="6e7f0-105">service content 処理とバックエンド統合 (プライベート プロセス) から Framework RNIF (RosettaNet Implementation) 処理 (パブリック プロセス) を分離します。</span><span class="sxs-lookup"><span data-stu-id="6e7f0-105"> isolates service-content processing and back-end integration (in the private process) from RosettaNet Implementation Framework (RNIF) handling (in the public process).</span></span>  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="6e7f0-106">長時間実行される BizTalk オーケストレーションとして、プライベート プロセスを実装します。</span><span class="sxs-lookup"><span data-stu-id="6e7f0-106"> implements private processes as long-running BizTalk orchestrations.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="6e7f0-107">開始側と応答側に 1 つの 1 つのプライベート プロセス オーケストレーションを使用します。</span><span class="sxs-lookup"><span data-stu-id="6e7f0-107"> uses one private-process orchestration on the initiator side and one on the responder side.</span></span> <span data-ttu-id="6e7f0-108">各プライベート プロセスは、着信または送信の Service Content メッセージ部を解釈して処理します。</span><span class="sxs-lookup"><span data-stu-id="6e7f0-108">Each private process interprets and processes the service-content message part, either incoming or outgoing.</span></span> <span data-ttu-id="6e7f0-109">プライベート プロセスは、パブリック プロセスとの間で Service Content の送受信を行います。</span><span class="sxs-lookup"><span data-stu-id="6e7f0-109">The private process sends the service content to, or receives it from, the public process.</span></span> <span data-ttu-id="6e7f0-110">プライベート プロセスはヘッダーを処理しません。また、RNIF 処理も実行しません。</span><span class="sxs-lookup"><span data-stu-id="6e7f0-110">A private process does not handle headers, and does not perform RNIF processing.</span></span> <span data-ttu-id="6e7f0-111">これらの処理は、パブリック プロセスが行います。</span><span class="sxs-lookup"><span data-stu-id="6e7f0-111">It leaves that to the public process.</span></span>  
  
 <span data-ttu-id="6e7f0-112">エンタープライズのシナリオでは、PIP メッセージ スキーマごとにプライベート プロセスが 1 つあるのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="6e7f0-112">In an enterprise scenario, there would typically be one private process for each PIP message schema.</span></span> <span data-ttu-id="6e7f0-113">ただし、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK には、任意の PIP メッセージを処理できるプライベート プロセス オーケストレーションが 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="6e7f0-113">However, the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK includes two private-process orchestrations that can process any PIP message.</span></span> <span data-ttu-id="6e7f0-114">1 つのオーケストレーションは、開始側プロセス (PrivateInitiator.odx を参照してください[PrivateInitiator サンプル &#91;RN3 &#93;](../../adapters-and-accelerators/accelerator-rosettanet/privateinitiator-sample.md)) その 1 つは応答側プロセス (PrivateResponder.odx を参照してください[PrivateResponder サンプル &#91;RN3 &#93;](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md)).</span><span class="sxs-lookup"><span data-stu-id="6e7f0-114">One orchestration is for the initiator process (PrivateInitiator.odx, see [PrivateInitiator Sample &#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/privateinitiator-sample.md)) and one is for the responder process (PrivateResponder.odx, see [PrivateResponder Sample &#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md)).</span></span> <span data-ttu-id="6e7f0-115">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] を特定のビジネス プロセスに適応させるためには、プライベート プロセスをカスタマイズする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e7f0-115">You will have to customize the private processes to adapt [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] to your specific business processes.</span></span>  
  
 <span data-ttu-id="6e7f0-116">SDK には、ビジネス ルール PIP に固有のプライベート応答側プロセスを実装するプロセスも含まれています (PIP3A4PrivateResponder.odx を参照してください[3A4 プライベート応答側オーケストレーションを使用して、ビジネス ルール](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md))。</span><span class="sxs-lookup"><span data-stu-id="6e7f0-116">The SDK also includes a process that implements a PIP-specific private responder process incorporating a business rule (PIP3A4PrivateResponder.odx, see [3A4 Private Responder Orchestration Using a Business Rule](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)).</span></span>  
  
 <span data-ttu-id="6e7f0-117">プライベート プロセスは、Service Content の書式をバックエンドの基幹業務 (LOB) 形式から XML 形式に変更します。</span><span class="sxs-lookup"><span data-stu-id="6e7f0-117">The private process changes the format of the service content from the back-end line-of-business (LOB) format to XML.</span></span> <span data-ttu-id="6e7f0-118">XML 形式に変更された Service Content は、すぐに [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] によって処理され、送信のためにパブリック プロセスによって RNIF 準拠のヘッダーが追加されます。</span><span class="sxs-lookup"><span data-stu-id="6e7f0-118">As soon as it is in XML format, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] processes the service content, and the public process adds RNIF-compliant headers to the service content for transmission.</span></span>  
  
 <span data-ttu-id="6e7f0-119">プライベート プロセスは、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] データベースの MessageToLOB テーブルと MessagesFromLOB テーブルを介して、バックエンドの基幹業務 (LOB) アプリケーションに接続します。</span><span class="sxs-lookup"><span data-stu-id="6e7f0-119">The private process connects to the back-end line-of-business applications through the MessageToLOB and MessagesFromLOB tables in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database.</span></span> <span data-ttu-id="6e7f0-120">このデータベースは、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] と LOB アプリケーション間の通信を処理します。</span><span class="sxs-lookup"><span data-stu-id="6e7f0-120">This database handles the communication between [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] and the LOB applications.</span></span> <span data-ttu-id="6e7f0-121">LOB アプリケーションは、インターフェイスを使用して、データベース テーブルにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="6e7f0-121">The LOB application uses an interface to gain access to the database tables.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6e7f0-122">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6e7f0-122">In This Section</span></span>  
  
-   [<span data-ttu-id="6e7f0-123">開始側プライベート プロセス</span><span class="sxs-lookup"><span data-stu-id="6e7f0-123">Initiator Private Process</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md)  
  
-   [<span data-ttu-id="6e7f0-124">応答側プライベート プロセス</span><span class="sxs-lookup"><span data-stu-id="6e7f0-124">Responder Private Process</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md)