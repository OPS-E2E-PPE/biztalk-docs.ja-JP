---
title: "RosettaNet および CIDX メッセージ規格 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messaging standards
- CIDX, messaging standards
- RosettaNet, messaging standards
ms.assetid: 3e9c090b-9425-41ae-ae86-d39ca2abfb63
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65eeb63a8e397837b5a512b4a9f5450107ec36bc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="rosettanet-and-cidx-messaging-standards"></a><span data-ttu-id="1b4e8-102">RosettaNet および CIDX メッセージ規格</span><span class="sxs-lookup"><span data-stu-id="1b4e8-102">RosettaNet and CIDX Messaging Standards</span></span>
<span data-ttu-id="1b4e8-103">主な目的[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]は RosettaNet または業界 Exchange CIDX (Chemical Data) メッセージングの標準に準拠するメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="1b4e8-103">The primary purpose of [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] is to process messages that conform to the RosettaNet or Chemical Industry Data Exchange (CIDX) messaging standards.</span></span> <span data-ttu-id="1b4e8-104">ここでは、2 つの主要な RosettaNet 規格である RNIF (RosettaNet Implementation Framework) と PIP (Partner Interface Process) について説明します。</span><span class="sxs-lookup"><span data-stu-id="1b4e8-104">This section provides information about the two major RosettaNet standards: the RosettaNet Implementation Framework (RNIF) and Partner Interface Processes (PIPs).</span></span> <span data-ttu-id="1b4e8-105">また、CIDX Chem eStandards についても説明します。</span><span class="sxs-lookup"><span data-stu-id="1b4e8-105">It also provides information about the CIDX Chem eStandards.</span></span>  
  
 <span data-ttu-id="1b4e8-106">RosettaNet 規格は、ハイテク分野で自動メッセージ交換を実装するために、幅広く受け入れられている新しい一連の規格です。</span><span class="sxs-lookup"><span data-stu-id="1b4e8-106">The RosettaNet standards are an emerging, widely accepted set of standards for implementing automated message exchange in high-technology scenarios.</span></span> <span data-ttu-id="1b4e8-107">RosettaNet 組織の目的は、eBusiness プロセスの規格の作成、実装、普及を行うことです。</span><span class="sxs-lookup"><span data-stu-id="1b4e8-107">The purpose of the RosettaNet organization is to create, implement, and promote eBusiness process standards.</span></span> <span data-ttu-id="1b4e8-108">このような規格は、ハイテク製造業やサプライ チェーンの分野で広く実用化されています。</span><span class="sxs-lookup"><span data-stu-id="1b4e8-108">These standards are widely used in high-technology manufacturing and supply-chain applications.</span></span> <span data-ttu-id="1b4e8-109">RosettaNet 組織には次の 6 業界の協議会が参画しており、応用範囲の広さがわかります。</span><span class="sxs-lookup"><span data-stu-id="1b4e8-109">The six different industry councils that govern the RosettaNet organization demonstrate the breadth of the application:</span></span>  
  
-   <span data-ttu-id="1b4e8-110">電子部品</span><span class="sxs-lookup"><span data-stu-id="1b4e8-110">Electronic components</span></span>  
  
-   <span data-ttu-id="1b4e8-111">半導体製造元</span><span class="sxs-lookup"><span data-stu-id="1b4e8-111">Semiconductor manufacturers</span></span>  
  
-   <span data-ttu-id="1b4e8-112">情報技術</span><span class="sxs-lookup"><span data-stu-id="1b4e8-112">Information technology</span></span>  
  
-   <span data-ttu-id="1b4e8-113">通信</span><span class="sxs-lookup"><span data-stu-id="1b4e8-113">Telecommunications</span></span>  
  
-   <span data-ttu-id="1b4e8-114">流通</span><span class="sxs-lookup"><span data-stu-id="1b4e8-114">Logistics</span></span>  
  
-   <span data-ttu-id="1b4e8-115">ソリューション プロバイダ</span><span class="sxs-lookup"><span data-stu-id="1b4e8-115">Solution providers</span></span>  
  
 <span data-ttu-id="1b4e8-116">CIDX Chem eStandards は、化学工業分野で自動メッセージ交換を実装するために広く普及している一連の規格です。</span><span class="sxs-lookup"><span data-stu-id="1b4e8-116">The CIDX Chem eStandards are a widely accepted set of standards for implementing automated message exchange in chemical-industry scenarios.</span></span>  
  
 <span data-ttu-id="1b4e8-117">標準の詳細については、RosettaNet の Web サイトを参照してください。 [http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=33859)と CIDX の Web サイトで[http://go.microsoft.com/FWLink/?LinkID=34540](http://go.microsoft.com/FWLink/?LinkID=34540)です。</span><span class="sxs-lookup"><span data-stu-id="1b4e8-117">For more information about standards, see the RosettaNet Web site at [http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=33859) and the CIDX Web site at [http://go.microsoft.com/FWLink/?LinkID=34540](http://go.microsoft.com/FWLink/?LinkID=34540).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1b4e8-118">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1b4e8-118">In This Section</span></span>  
  
-   [<span data-ttu-id="1b4e8-119">RNIF 規格</span><span class="sxs-lookup"><span data-stu-id="1b4e8-119">RNIF Standard</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/rnif-standard.md)  
  
-   [<span data-ttu-id="1b4e8-120">RosettaNet Pip</span><span class="sxs-lookup"><span data-stu-id="1b4e8-120">RosettaNet PIPs</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-pips.md)  
  
-   [<span data-ttu-id="1b4e8-121">CIDX メッセージ規格</span><span class="sxs-lookup"><span data-stu-id="1b4e8-121">CIDX Messaging Standards</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/cidx-messaging-standards.md)