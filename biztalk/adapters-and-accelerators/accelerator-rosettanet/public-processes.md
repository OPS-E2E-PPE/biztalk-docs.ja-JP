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
ms.openlocfilehash: 426884dd700ad5b7862b5c191339b8ca49388232
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282611"
---
# <a name="public-processes"></a><span data-ttu-id="f6f2c-102">パブリック プロセス</span><span class="sxs-lookup"><span data-stu-id="f6f2c-102">Public Processes</span></span>
<span data-ttu-id="f6f2c-103">Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]パブリック プロセスとして取引先との統合に関係するビジネス プロセスを実装します。</span><span class="sxs-lookup"><span data-stu-id="f6f2c-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] implements business processes that involve integration with trading partners as public processes.</span></span> <span data-ttu-id="f6f2c-104">プライベート プロセスとして、組織の内部ビジネス プロセスを実装します。</span><span class="sxs-lookup"><span data-stu-id="f6f2c-104">It implements business processes that are internal to an organization as private processes.</span></span> <span data-ttu-id="f6f2c-105">パブリックおよびプライベート プロセスを使用して、service content 処理とバックエンド統合 (プライベート プロセス) 内から Framework RNIF (RosettaNet Implementation) (パブリック プロセス) 内の処理を分離します。</span><span class="sxs-lookup"><span data-stu-id="f6f2c-105">Using public and private processes isolates RosettaNet Implementation Framework (RNIF) handling (in the public process) from the service content processing and back-end integration (in the private process).</span></span>  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="f6f2c-106">パブリック プロセスは、長時間実行される BizTalk オーケストレーションとして実装します。</span><span class="sxs-lookup"><span data-stu-id="f6f2c-106">implements public processes as long-running BizTalk orchestrations.</span></span> <span data-ttu-id="f6f2c-107">1 つのパブリック プロセス オーケストレーションは、発信側と応答側のいずれかで実行されます。</span><span class="sxs-lookup"><span data-stu-id="f6f2c-107">One public-process orchestration runs on the initiator side and one on the responder side.</span></span> <span data-ttu-id="f6f2c-108">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]セットアップ プログラムは、イニシエーターとレスポンダーのバージョンの RNIF 1.1 および RNIF 2.01 用のパブリック プロセス オーケストレーションを提供します。</span><span class="sxs-lookup"><span data-stu-id="f6f2c-108">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Setup program provides versions of the initiator and responder public-process orchestrations for both RNIF 1.1 and RNIF 2.01.</span></span>  
  
 <span data-ttu-id="f6f2c-109">これらのパブリック プロセス オーケストレーションは、すべての RNIF プロセスを実装します。</span><span class="sxs-lookup"><span data-stu-id="f6f2c-109">These public-process orchestrations implement all RNIF processes.</span></span> <span data-ttu-id="f6f2c-110">パブリック プロセスには、残りのコンポーネントから RNIF の複雑さが非表示にします。</span><span class="sxs-lookup"><span data-stu-id="f6f2c-110">Public processes hide the complexity of RNIF from the rest of the components.</span></span> <span data-ttu-id="f6f2c-111">RNIF 準拠のメッセージ フローをするだけでなく、パブリック プロセスも既定の追跡設定を決定し、実行時にプロセス状態に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="f6f2c-111">Besides enforcing the RNIF-compliant message flow, the public process also determines default-tracking settings and provides process state information at run time.</span></span> <span data-ttu-id="f6f2c-112">メッセージの service content は処理されません。</span><span class="sxs-lookup"><span data-stu-id="f6f2c-112">It does not process the service content of a message.</span></span> <span data-ttu-id="f6f2c-113">プライベート プロセスで行われます。</span><span class="sxs-lookup"><span data-stu-id="f6f2c-113">The private process does this.</span></span>  
  
 <span data-ttu-id="f6f2c-114">各取引先アグリーメントは、1 つのパブリック プロセスを開始またはプロセス PIP (Partner Interface) の操作に対する応答を参照します。</span><span class="sxs-lookup"><span data-stu-id="f6f2c-114">Each trading partner agreement references a single public process to initiate or respond to Partner Interface Process (PIP) actions.</span></span> <span data-ttu-id="f6f2c-115">ただし、パブリック プロセスでは PIP は認識されません。</span><span class="sxs-lookup"><span data-stu-id="f6f2c-115">However, the public processes are PIP-agnostic.</span></span>  
  
 <span data-ttu-id="f6f2c-116">RosettaNet の仕様では、パブリック プロセスの設計を決定します。</span><span class="sxs-lookup"><span data-stu-id="f6f2c-116">The RosettaNet specifications dictate the design of the public process.</span></span> <span data-ttu-id="f6f2c-117">パブリック プロセスを変更しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f6f2c-117">It is recommended that you do not modify a public process.</span></span> <span data-ttu-id="f6f2c-118">パブリック プロセス オーケストレーションとは、バージョン管理され、署名付きです。</span><span class="sxs-lookup"><span data-stu-id="f6f2c-118">The public-process orchestration is versioned and signed.</span></span> <span data-ttu-id="f6f2c-119">パブリック プロセスを変更することと、RNIF 準拠ができなくなります。</span><span class="sxs-lookup"><span data-stu-id="f6f2c-119">If you modify a public process, it will no longer be RNIF-compliant.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f6f2c-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f6f2c-120">In This Section</span></span>  
  
-   [<span data-ttu-id="f6f2c-121">イニシエーター パブリック プロセス</span><span class="sxs-lookup"><span data-stu-id="f6f2c-121">Initiator Public Process</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/initiator-public-process.md)  
  
-   [<span data-ttu-id="f6f2c-122">レスポンダー パブリック プロセス</span><span class="sxs-lookup"><span data-stu-id="f6f2c-122">Responder Public Process</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/responder-public-process.md)