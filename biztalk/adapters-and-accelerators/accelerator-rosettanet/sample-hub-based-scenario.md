---
title: "サンプルのハブベース シナリオ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- supply chains, examples
- hub-and-spoke systems
- supply chains, hub-and-spoke systems
- examples, supply chains
- trading partners, supply chains
ms.assetid: ee92c24d-a281-4950-a61e-9cb3bd08d291
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b417398786e602379d16d6734a5ed366b9d6f2ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sample-hub-based-scenario"></a><span data-ttu-id="2fa30-102">サンプルのハブベース シナリオ</span><span class="sxs-lookup"><span data-stu-id="2fa30-102">Sample Hub-Based Scenario</span></span>
<span data-ttu-id="2fa30-103">多くのサプライ チェーン シナリオでは、企業が、各取引先に対して RNIF (RosettaNet Implementation Framework) 接続を構築します。</span><span class="sxs-lookup"><span data-stu-id="2fa30-103">In many supply-chain scenarios, a company will work with each of their trading partners to institute a RosettaNet Implementation Framework (RNIF) connection.</span></span> <span data-ttu-id="2fa30-104">これにより、サプライ チェーン全体の通信を効率的に標準化できます。</span><span class="sxs-lookup"><span data-stu-id="2fa30-104">This is an effective way to standardize communications throughout the supply chain.</span></span> <span data-ttu-id="2fa30-105">このシナリオについては、「[サンプル サプライ チェーン シナリオ](../../adapters-and-accelerators/accelerator-rosettanet/sample-supply-chain-scenario.md)です。</span><span class="sxs-lookup"><span data-stu-id="2fa30-105">This scenario is described in [Sample Supply Chain Scenario](../../adapters-and-accelerators/accelerator-rosettanet/sample-supply-chain-scenario.md).</span></span>  
  
 <span data-ttu-id="2fa30-106">サプライ チェーン全体のトランザクションを自動化するもう 1 つの選択肢として、統合システムのセットアップと管理を行う企業と契約するという方法があります。</span><span class="sxs-lookup"><span data-stu-id="2fa30-106">Another way to automate transactions throughout the supply chain is for the company to contract with another company to set up and manage the integrated system.</span></span> <span data-ttu-id="2fa30-107">これがハブベースのシナリオです。</span><span class="sxs-lookup"><span data-stu-id="2fa30-107">This is a hub-based scenario.</span></span>  
  
## <a name="how-a-hub-based-system-works"></a><span data-ttu-id="2fa30-108">ハブベース システムの動作</span><span class="sxs-lookup"><span data-stu-id="2fa30-108">How a Hub-Based System Works</span></span>  
 <span data-ttu-id="2fa30-109">ハブベースのシステムでは、統合システムを契約している企業が RNIF 接続を使用してハブ企業に接続します。</span><span class="sxs-lookup"><span data-stu-id="2fa30-109">In a hub-based system, the company contracting for an integrated system connects to the hub company using an RNIF connection.</span></span> <span data-ttu-id="2fa30-110">次に、ハブ企業は必要とされる任意の電子的接続手段を使って、その企業のすべての取引先に接続します。</span><span class="sxs-lookup"><span data-stu-id="2fa30-110">The hub then connects to all the company's trading partners using whatever type of electronic connection is required.</span></span> <span data-ttu-id="2fa30-111">ハブ企業は、RNIF 接続、EDI、フラット ファイル、Web アプリケーション、および専用接続をすべての取引先に提供できます。</span><span class="sxs-lookup"><span data-stu-id="2fa30-111">The hub company provides all the trading partners with connection options: RNIF connections, EDI, flat file, Web applications, or non-compliant, proprietary connections.</span></span> <span data-ttu-id="2fa30-112">通信システムの管理は、ハブ企業が担当します。</span><span class="sxs-lookup"><span data-stu-id="2fa30-112">Managing the communications system is the hub company's business.</span></span> <span data-ttu-id="2fa30-113">次の図に、このようなハブベース システムのしくみを示します。</span><span class="sxs-lookup"><span data-stu-id="2fa30-113">The following figure shows how such a system might work.</span></span>  
  
 <span data-ttu-id="2fa30-114">![(& m); 60変更なし &#62;。] (../../adapters-and-accelerators/accelerator-rosettanet/media/hub-based-scenario.gif "Hub_Based_Scenario")</span><span class="sxs-lookup"><span data-stu-id="2fa30-114">![&#60;No Change&#62;](../../adapters-and-accelerators/accelerator-rosettanet/media/hub-based-scenario.gif "Hub_Based_Scenario")</span></span>  
  
 <span data-ttu-id="2fa30-115">ハブベースのシステムには、以下のような多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="2fa30-115">A hub-based system has many advantages:</span></span>  
  
-   <span data-ttu-id="2fa30-116">契約する企業は複雑なサプライ チェーンを管理する必要がなくなります。これはハブ企業が担当します。</span><span class="sxs-lookup"><span data-stu-id="2fa30-116">The contracting company does not have to deal with the complexity of the supply chain; the hub company handles it.</span></span>  
  
-   <span data-ttu-id="2fa30-117">契約する企業はシステムの保守やアップグレードを行う必要がなく、ダウンタイムに対して責任を負いません。ハブ企業がシステムの保守およびダウンタイムの責任を負います。</span><span class="sxs-lookup"><span data-stu-id="2fa30-117">The contracting company does not have to maintain or upgrade the system, and it is not responsible for downtime; the hub company is responsible for system maintenance and downtime.</span></span>  
  
-   <span data-ttu-id="2fa30-118">契約する企業は、標準化、自動化、コスト節約、可視性といった RosettaNet 準拠システムの利点を享受できます。</span><span class="sxs-lookup"><span data-stu-id="2fa30-118">The contracting company gains the advantages of a RosettaNet-compliant system, including standardization, automation, cost savings, and visibility.</span></span>  
  
-   <span data-ttu-id="2fa30-119">契約する企業は、さまざまな電子的接続手段を包括する完全自動サプライ チェーンを実現でき、取引先からの接続手段を制限する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="2fa30-119">The contracting company has fully automated their supply chain with a variety of electronic connections that give the full array of trading partners a choice of connections.</span></span> <span data-ttu-id="2fa30-120">契約する企業は、さまざまな接続方法に精通した技術担当者を雇用する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="2fa30-120">The contracting company does not have to maintain technological expertise in a variety of connection options.</span></span>  
  
-   <span data-ttu-id="2fa30-121">取引先は、引き続き専用接続を使用することもできます (ハブ企業がサポートしている場合)。</span><span class="sxs-lookup"><span data-stu-id="2fa30-121">A trading partner can continue to use a proprietary connection, as long as the hub company supports it.</span></span>  
  
-   <span data-ttu-id="2fa30-122">システムには柔軟性があります。</span><span class="sxs-lookup"><span data-stu-id="2fa30-122">The system is flexible.</span></span> <span data-ttu-id="2fa30-123">取引先では RosettaNet 準拠システムを採用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2fa30-123">Trading partners do not have to adopt a RosettaNet-compliant system.</span></span> <span data-ttu-id="2fa30-124">ただし、採用すれば、このようなシステムの利点を享受できます。</span><span class="sxs-lookup"><span data-stu-id="2fa30-124">However, if they do so, they will gain the benefits from such a system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fa30-125">参照</span><span class="sxs-lookup"><span data-stu-id="2fa30-125">See Also</span></span>  
 <span data-ttu-id="2fa30-126">[BizTalk Server がビジネス ニーズを解決する方法](../../adapters-and-accelerators/accelerator-rosettanet/how-biztalk-server-solves-the-business-need1.md) </span><span class="sxs-lookup"><span data-stu-id="2fa30-126">[How BizTalk Server Solves the Business Need](../../adapters-and-accelerators/accelerator-rosettanet/how-biztalk-server-solves-the-business-need1.md) </span></span>  
 <span data-ttu-id="2fa30-127">[取引先との統合の必要性](../../adapters-and-accelerators/accelerator-rosettanet/the-need-for-trading-partner-integration.md) </span><span class="sxs-lookup"><span data-stu-id="2fa30-127">[The Need for Trading Partner Integration](../../adapters-and-accelerators/accelerator-rosettanet/the-need-for-trading-partner-integration.md) </span></span>  
 <span data-ttu-id="2fa30-128">[サプライ チェーンの課題](../../adapters-and-accelerators/accelerator-rosettanet/the-supply-chain-challenge.md) </span><span class="sxs-lookup"><span data-stu-id="2fa30-128">[The Supply Chain Challenge](../../adapters-and-accelerators/accelerator-rosettanet/the-supply-chain-challenge.md) </span></span>  
 <span data-ttu-id="2fa30-129">[サプライ チェーン ソリューション](../../adapters-and-accelerators/accelerator-rosettanet/the-supply-chain-solution.md) </span><span class="sxs-lookup"><span data-stu-id="2fa30-129">[The Supply Chain Solution](../../adapters-and-accelerators/accelerator-rosettanet/the-supply-chain-solution.md) </span></span>  
 [<span data-ttu-id="2fa30-130">サンプル サプライ チェーン シナリオ</span><span class="sxs-lookup"><span data-stu-id="2fa30-130">Sample Supply Chain Scenario</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/sample-supply-chain-scenario.md)