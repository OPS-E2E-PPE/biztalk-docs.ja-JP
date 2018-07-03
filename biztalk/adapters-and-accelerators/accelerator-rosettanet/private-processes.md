---
title: プライベート プロセス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ff99f03b3a38ff9d8c1c33ec16b108e5bd58ca7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967489"
---
# <a name="private-processes"></a><span data-ttu-id="ab5b2-102">プライベート プロセス</span><span class="sxs-lookup"><span data-stu-id="ab5b2-102">Private Processes</span></span>
<span data-ttu-id="ab5b2-103">Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]プライベート プロセスとして、組織の内部ビジネス プロセスを実装します。</span><span class="sxs-lookup"><span data-stu-id="ab5b2-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] implements business processes that are internal to an organization as private processes.</span></span> <span data-ttu-id="ab5b2-104">パブリック プロセスは、取引先との統合に関係するビジネス プロセスを処理します。</span><span class="sxs-lookup"><span data-stu-id="ab5b2-104">Public processes handle business processes that involve integration with trading partners.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="ab5b2-105"> service content 処理とバックエンド統合 (プライベート プロセス) 内から Framework RNIF (RosettaNet Implementation) (パブリック プロセス) 内の処理を分離します。</span><span class="sxs-lookup"><span data-stu-id="ab5b2-105"> isolates service-content processing and back-end integration (in the private process) from RosettaNet Implementation Framework (RNIF) handling (in the public process).</span></span>  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="ab5b2-106"> プライベート プロセスは、長時間実行される BizTalk オーケストレーションとして実装します。</span><span class="sxs-lookup"><span data-stu-id="ab5b2-106"> implements private processes as long-running BizTalk orchestrations.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="ab5b2-107"> 発信側と応答側のいずれかで 1 つのプライベート プロセス オーケストレーションを使用します。</span><span class="sxs-lookup"><span data-stu-id="ab5b2-107"> uses one private-process orchestration on the initiator side and one on the responder side.</span></span> <span data-ttu-id="ab5b2-108">各プライベート プロセスは、着信または送信の Service Content メッセージ部を解釈して処理します。</span><span class="sxs-lookup"><span data-stu-id="ab5b2-108">Each private process interprets and processes the service-content message part, either incoming or outgoing.</span></span> <span data-ttu-id="ab5b2-109">プライベート プロセスは、パブリック プロセスとの間で Service Content の送受信を行います。</span><span class="sxs-lookup"><span data-stu-id="ab5b2-109">The private process sends the service content to, or receives it from, the public process.</span></span> <span data-ttu-id="ab5b2-110">プライベート プロセスはヘッダーを処理しません。また、RNIF 処理も実行しません。</span><span class="sxs-lookup"><span data-stu-id="ab5b2-110">A private process does not handle headers, and does not perform RNIF processing.</span></span> <span data-ttu-id="ab5b2-111">これらの処理は、パブリック プロセスが行います。</span><span class="sxs-lookup"><span data-stu-id="ab5b2-111">It leaves that to the public process.</span></span>  
  
 <span data-ttu-id="ab5b2-112">エンタープライズのシナリオでは、PIP メッセージ スキーマごとにプライベート プロセスが 1 つあるのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="ab5b2-112">In an enterprise scenario, there would typically be one private process for each PIP message schema.</span></span> <span data-ttu-id="ab5b2-113">ただし、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK には、任意の PIP メッセージを処理できるプライベート プロセス オーケストレーションが 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="ab5b2-113">However, the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK includes two private-process orchestrations that can process any PIP message.</span></span> <span data-ttu-id="ab5b2-114">1 つのオーケストレーションは、開始側プロセス (PrivateInitiator.odx を参照してください[PrivateInitiator サンプル&#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/privateinitiator-sample.md)) と 1 つは、応答側プロセス (PrivateResponder.odx を参照してください[PrivateResponderサンプル&#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md))。</span><span class="sxs-lookup"><span data-stu-id="ab5b2-114">One orchestration is for the initiator process (PrivateInitiator.odx, see [PrivateInitiator Sample &#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/privateinitiator-sample.md)) and one is for the responder process (PrivateResponder.odx, see [PrivateResponder Sample &#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md)).</span></span> <span data-ttu-id="ab5b2-115">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] を特定のビジネス プロセスに適応させるためには、プライベート プロセスをカスタマイズする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab5b2-115">You will have to customize the private processes to adapt [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] to your specific business processes.</span></span>  
  
 <span data-ttu-id="ab5b2-116">SDK には、ビジネス ルール PIP 固有の応答側プライベート プロセスを実装するプロセスも含まれています (PIP3A4PrivateResponder.odx を参照してください[3A4 プライベート レスポンダー オーケストレーションを使用してビジネス ルール](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md))。</span><span class="sxs-lookup"><span data-stu-id="ab5b2-116">The SDK also includes a process that implements a PIP-specific private responder process incorporating a business rule (PIP3A4PrivateResponder.odx, see [3A4 Private Responder Orchestration Using a Business Rule](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)).</span></span>  
  
 <span data-ttu-id="ab5b2-117">プライベート プロセスは、Service Content の書式をバックエンドの基幹業務 (LOB) 形式から XML 形式に変更します。</span><span class="sxs-lookup"><span data-stu-id="ab5b2-117">The private process changes the format of the service content from the back-end line-of-business (LOB) format to XML.</span></span> <span data-ttu-id="ab5b2-118">XML 形式に変更された Service Content は、すぐに [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] によって処理され、送信のためにパブリック プロセスによって RNIF 準拠のヘッダーが追加されます。</span><span class="sxs-lookup"><span data-stu-id="ab5b2-118">As soon as it is in XML format, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] processes the service content, and the public process adds RNIF-compliant headers to the service content for transmission.</span></span>  
  
 <span data-ttu-id="ab5b2-119">プライベート プロセスは、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] データベースの MessageToLOB テーブルと MessagesFromLOB テーブルを介して、バックエンドの基幹業務 (LOB) アプリケーションに接続します。</span><span class="sxs-lookup"><span data-stu-id="ab5b2-119">The private process connects to the back-end line-of-business applications through the MessageToLOB and MessagesFromLOB tables in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database.</span></span> <span data-ttu-id="ab5b2-120">このデータベースは、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] と LOB アプリケーション間の通信を処理します。</span><span class="sxs-lookup"><span data-stu-id="ab5b2-120">This database handles the communication between [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] and the LOB applications.</span></span> <span data-ttu-id="ab5b2-121">LOB アプリケーションは、インターフェイスを使用して、データベース テーブルにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="ab5b2-121">The LOB application uses an interface to gain access to the database tables.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ab5b2-122">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ab5b2-122">In This Section</span></span>  
  
-   [<span data-ttu-id="ab5b2-123">イニシエーター プライベート プロセス</span><span class="sxs-lookup"><span data-stu-id="ab5b2-123">Initiator Private Process</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md)  
  
-   [<span data-ttu-id="ab5b2-124">レスポンダー プライベート プロセス</span><span class="sxs-lookup"><span data-stu-id="ab5b2-124">Responder Private Process</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md)