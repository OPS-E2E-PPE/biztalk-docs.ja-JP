---
title: 小規模のアーキテクチャのサンプル&amp;規模の企業 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, examples
ms.assetid: fc8c2fdd-bcb1-481c-b351-03092dd48540
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81bde6f78cad46e0c1346ec1ca705f44014d4cb6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65271064"
---
# <a name="sample-architectures-for-small-amp-medium-sized-companies"></a><span data-ttu-id="8231b-102">小規模のアーキテクチャのサンプル&amp;中規模企業</span><span class="sxs-lookup"><span data-stu-id="8231b-102">Sample Architectures for Small &amp; Medium-Sized Companies</span></span>
<span data-ttu-id="8231b-103">このセクションでは、小規模または中規模の会社の資産を保護する場合に、Microsoft BizTalk Server をデプロイするサンプル アーキテクチャを提供します。</span><span class="sxs-lookup"><span data-stu-id="8231b-103">This section provides a sample architecture to deploy Microsoft BizTalk Server when you want to help to protect the assets in a small or medium-sized company.</span></span> <span data-ttu-id="8231b-104">これらのアーキテクチャでは、縦深防御や攻撃の影響を最小限にサービスの分離を促進、中に、ハードウェア、ソフトウェア、および大企業に一般に利用人事の数量と仮定します。</span><span class="sxs-lookup"><span data-stu-id="8231b-104">While these architectures encourage defense in depth and separation of services to minimize the impact of an attack, they assume quantities of hardware, software, and human resources that are generally available to large companies.</span></span>  
  
 <span data-ttu-id="8231b-105">ただし、小規模および中規模企業 (または小規模な BizTalk Server 展開に持つ大企業) する必要がありますも考慮する環境を保護する方法。</span><span class="sxs-lookup"><span data-stu-id="8231b-105">However, small and medium-sized companies (or large companies with small BizTalk Server deployments) should also be concerned with how to protect their environments.</span></span> <span data-ttu-id="8231b-106">企業の展開または展開する予定に考えた後、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューション、中小規模の企業に最大限のセキュリティと使用可能なリソースのバランスを取るサンプル アーキテクチャを導き出しました。</span><span class="sxs-lookup"><span data-stu-id="8231b-106">After we looked at how companies deployed or plan to deploy their [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solutions, we derived a sample architecture for small and medium-sized companies that balances available resources with the greatest possible security.</span></span> <span data-ttu-id="8231b-107">このセクションで情報を使用して、独自の展開を計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8231b-107">You should use the information in this section to help you plan your own deployment.</span></span> <span data-ttu-id="8231b-108">お客様のビジネス ニーズと資産を評価した後、BizTalk Server の展開のさまざまなアーキテクチャを決定する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8231b-108">After you evaluate your business needs and assets you might decide on a different architecture for your BizTalk Server deployment.</span></span>  
  
 <span data-ttu-id="8231b-109">アーキテクチャを確認する方法を容易にできるように、このセクションでは、環境内で使用するさまざまなアダプタに基づいたサンプル アーキテクチャを提供します。</span><span class="sxs-lookup"><span data-stu-id="8231b-109">To make it easier to see how your architecture would look, this section provides sample architectures based on various adapters that you might use in your environment.</span></span> <span data-ttu-id="8231b-110">図では、BizTalk Server 環境で使用すると、トポロジのコンポーネントがアダプタに依存せずとして、アダプターに依存するコンポーネントを表示します。</span><span class="sxs-lookup"><span data-stu-id="8231b-110">The figures show you which components of the topology are adapter-independent, and which components depend on the adapter you use in your BizTalk Server environment.</span></span>  
  
 <span data-ttu-id="8231b-111">BizTalk Server で使用できるアダプターの一部に基づいた使用シナリオを考察します。</span><span class="sxs-lookup"><span data-stu-id="8231b-111">We also examine usage scenarios based on some of the adapters you can use with BizTalk Server.</span></span> <span data-ttu-id="8231b-112">計画して、独自のアーキテクチャを設計するために、このサンプル アーキテクチャの脅威モデル分析を提供します。</span><span class="sxs-lookup"><span data-stu-id="8231b-112">To help you as you plan and design your own architecture, we provide a threat model analysis of this sample architecture.</span></span> <span data-ttu-id="8231b-113">この分析を使用すると、パートナーとの通信に使用するアダプタに応じて、企業に影響を与える可能性のあるセキュリティの問題について詳しく説明できます。</span><span class="sxs-lookup"><span data-stu-id="8231b-113">This analysis gives you a deeper look at the potential security issues that might affect your company, depending on the adapters you use to communicate with your partners.</span></span>  
  
 <span data-ttu-id="8231b-114">このセクションでは、のセキュリティで保護された展開を設計するのに役立つ情報を提供するときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、環境内のサーバー間の通信をセキュリティで保護することも検討環境内のセキュリティを強化します。</span><span class="sxs-lookup"><span data-stu-id="8231b-114">While this section gives you information to help you design a secure deployment of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], to increase the security in your environment you should also consider securing the communication between the servers in the environment.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8231b-115">このセクションでは、ビジネス アクティビティ監視 (BAM) を使用していないことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="8231b-115">This section assumes that you are not using Business Activity Monitoring (BAM).</span></span> <span data-ttu-id="8231b-116">この機能には、追加のセキュリティに関する考慮事項が必要です。</span><span class="sxs-lookup"><span data-stu-id="8231b-116">This feature requires additional security considerations.</span></span> <span data-ttu-id="8231b-117">詳細については[Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)します。</span><span class="sxs-lookup"><span data-stu-id="8231b-117">This is discussed in [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8231b-118">このドキュメントに記載されていないアダプタの詳細については、BizTalk Server デベロッパー センターを参照してください ([http://go.microsoft.com/fwlink/?LinkId=46420](http://go.microsoft.com/fwlink/?LinkId=46420)。)。</span><span class="sxs-lookup"><span data-stu-id="8231b-118">For more information about adapters not described in this document, see the BizTalk Server Developer Center ([http://go.microsoft.com/fwlink/?LinkId=46420](http://go.microsoft.com/fwlink/?LinkId=46420).)</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8231b-119">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8231b-119">In This Section</span></span>  
  
-   [<span data-ttu-id="8231b-120">サンプル アーキテクチャ:基盤となる BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="8231b-120">Sample Architecture: Base BizTalk Server</span></span>](../core/sample-architecture-base-biztalk-server.md)  
  
-   [<span data-ttu-id="8231b-121">サンプル アーキテクチャ:HTTP アダプターと SOAP アダプター</span><span class="sxs-lookup"><span data-stu-id="8231b-121">Sample Architecture: HTTP and SOAP Adapters</span></span>](../core/sample-architecture-http-and-soap-adapters.md)  
  
-   [<span data-ttu-id="8231b-122">サンプル アーキテクチャ:BizTalk メッセージ キュー</span><span class="sxs-lookup"><span data-stu-id="8231b-122">Sample Architecture: BizTalk Message Queuing</span></span>](../core/sample-architecture-biztalk-message-queuing.md)  
  
-   [<span data-ttu-id="8231b-123">サンプル アーキテクチャ:FTP アダプター</span><span class="sxs-lookup"><span data-stu-id="8231b-123">Sample Architecture: FTP Adapter</span></span>](../core/sample-architecture-ftp-adapter.md)  
  
-   [<span data-ttu-id="8231b-124">サンプル アーキテクチャ:ファイル アダプター</span><span class="sxs-lookup"><span data-stu-id="8231b-124">Sample Architecture: File Adapter</span></span>](../core/sample-architecture-file-adapter.md)