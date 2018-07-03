---
title: パブリック プロセス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- public processes, orchestrations
- business processes, public processes
- public processes, trading partners
- BTARN, public processes
- orchestrations, public-process orchestrations
- public processes
- trading partners, public processes
- public processes, about public processes
ms.assetid: 5ccc7449-5741-4d49-beb6-567bcd93f679
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f9d0288defa0705c7e12f102011edbf9ee7e90d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984723"
---
# <a name="public-processes"></a><span data-ttu-id="210ab-102">パブリック プロセス</span><span class="sxs-lookup"><span data-stu-id="210ab-102">Public Processes</span></span>
<span data-ttu-id="210ab-103">Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]パブリック プロセスとして取引先との統合に関係するビジネス プロセスを実装します。</span><span class="sxs-lookup"><span data-stu-id="210ab-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] implements business processes that involve integration with trading partners as public processes.</span></span> <span data-ttu-id="210ab-104">組織内部のビジネス プロセスは、プライベート プロセスとして実装されます。</span><span class="sxs-lookup"><span data-stu-id="210ab-104">It implements business processes that are internal to an organization as private processes.</span></span> <span data-ttu-id="210ab-105">パブリック プロセスとプライベート プロセスを使用することで、RNIF (RosettaNet Implementation Framework) の処理 (パブリック プロセス内) は、Service Content 処理とバックエンドの統合 (プライベート プロセス内) から独立します。</span><span class="sxs-lookup"><span data-stu-id="210ab-105">Using public and private processes isolates RosettaNet Implementation Framework (RNIF) handling (in the public process) from the service content processing and back-end integration (in the private process).</span></span>  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="210ab-106"> では、長期にわたって実行される BizTalk オーケストレーションとして、パブリック プロセスを実装しています。</span><span class="sxs-lookup"><span data-stu-id="210ab-106"> implements public processes as long-running BizTalk orchestrations.</span></span> <span data-ttu-id="210ab-107">1 つのパブリック プロセスのオーケストレーションは開始側で実行され、もう 1 つのオーケストレーションは応答側で実行されます。</span><span class="sxs-lookup"><span data-stu-id="210ab-107">One public-process orchestration runs on the initiator side and one on the responder side.</span></span> <span data-ttu-id="210ab-108">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] セットアップ プログラムからは、RNIF 1.1 および RNIF 2.01 用の開始側パブリック プロセス オーケストレーションと応答側パブリック プロセス オーケストレーションの各バージョンが提供されます。</span><span class="sxs-lookup"><span data-stu-id="210ab-108">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Setup program provides versions of the initiator and responder public-process orchestrations for both RNIF 1.1 and RNIF 2.01.</span></span>  
  
 <span data-ttu-id="210ab-109">これらのパブリック プロセス オーケストレーションにより、すべての RNIF プロセスが実装されます。</span><span class="sxs-lookup"><span data-stu-id="210ab-109">These public-process orchestrations implement all RNIF processes.</span></span> <span data-ttu-id="210ab-110">パブリック プロセスでは、RNIF の複雑な部分はコンポーネントの他の部分からは見えないようになっています。</span><span class="sxs-lookup"><span data-stu-id="210ab-110">Public processes hide the complexity of RNIF from the rest of the components.</span></span> <span data-ttu-id="210ab-111">パブリック プロセスは RNIF 準拠のメッセージの流れをスムーズにするだけでなく、既定の追跡設定を指定し、実行時にプロセス状態に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="210ab-111">Besides enforcing the RNIF-compliant message flow, the public process also determines default-tracking settings and provides process state information at run time.</span></span> <span data-ttu-id="210ab-112">メッセージの Service Content は処理されません。</span><span class="sxs-lookup"><span data-stu-id="210ab-112">It does not process the service content of a message.</span></span> <span data-ttu-id="210ab-113">これは、プライベート プロセスが行います。</span><span class="sxs-lookup"><span data-stu-id="210ab-113">The private process does this.</span></span>  
  
 <span data-ttu-id="210ab-114">各取引先アグリーメントは単一のパブリック プロセスを参照して、PIP (Partner Interface Process) アクションを開始するか、アクションに応答します。</span><span class="sxs-lookup"><span data-stu-id="210ab-114">Each trading partner agreement references a single public process to initiate or respond to Partner Interface Process (PIP) actions.</span></span> <span data-ttu-id="210ab-115">ただし、パブリック プロセスでは PIP は認識されません。</span><span class="sxs-lookup"><span data-stu-id="210ab-115">However, the public processes are PIP-agnostic.</span></span>  
  
 <span data-ttu-id="210ab-116">パブリック プロセスのデザインは、RosettaNet の仕様によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="210ab-116">The RosettaNet specifications dictate the design of the public process.</span></span> <span data-ttu-id="210ab-117">パブリック プロセスは変更しないことを推奨します。</span><span class="sxs-lookup"><span data-stu-id="210ab-117">It is recommended that you do not modify a public process.</span></span> <span data-ttu-id="210ab-118">パブリック プロセス オーケストレーションは、バージョン管理され、署名されています。</span><span class="sxs-lookup"><span data-stu-id="210ab-118">The public-process orchestration is versioned and signed.</span></span> <span data-ttu-id="210ab-119">パブリック プロセスを変更すると、RNIF に準拠しなくなります。</span><span class="sxs-lookup"><span data-stu-id="210ab-119">If you modify a public process, it will no longer be RNIF-compliant.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="210ab-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="210ab-120">In This Section</span></span>  
  
-   [<span data-ttu-id="210ab-121">イニシエーター パブリック プロセス</span><span class="sxs-lookup"><span data-stu-id="210ab-121">Initiator Public Process</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/initiator-public-process.md)  
  
-   [<span data-ttu-id="210ab-122">レスポンダー パブリック プロセス</span><span class="sxs-lookup"><span data-stu-id="210ab-122">Responder Public Process</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/responder-public-process.md)