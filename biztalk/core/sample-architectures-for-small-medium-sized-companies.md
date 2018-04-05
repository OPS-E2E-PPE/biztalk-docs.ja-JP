---
title: サンプル アーキテクチャの小規模&amp;規模の企業 |Microsoft ドキュメント
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
ms.openlocfilehash: 0fa7911b7b2da942d559f2c85ad32e896c79d174
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sample-architectures-for-small-amp-medium-sized-companies"></a><span data-ttu-id="4c9db-102">サンプル アーキテクチャの小規模&amp;中規模企業</span><span class="sxs-lookup"><span data-stu-id="4c9db-102">Sample Architectures for Small &amp; Medium-Sized Companies</span></span>
<span data-ttu-id="4c9db-103">このセクションでは、中小企業の資産を保護する必要がある場合に、Microsoft BizTalk Server を展開するためのサンプル アーキテクチャについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4c9db-103">This section provides a sample architecture to deploy Microsoft BizTalk Server when you want to help to protect the assets in a small or medium-sized company.</span></span> <span data-ttu-id="4c9db-104">これらのアーキテクチャでは、重層的な防御とサービスの分離を使用して、攻撃の影響を最小限に抑えていますが、ハードウェア、ソフトウェア、および人材の数量は大企業で一般的に必要であるとされる数量を想定しています。</span><span class="sxs-lookup"><span data-stu-id="4c9db-104">While these architectures encourage defense in depth and separation of services to minimize the impact of an attack, they assume quantities of hardware, software, and human resources that are generally available to large companies.</span></span>  
  
 <span data-ttu-id="4c9db-105">ただし、中小企業 (または小規模な BizTalk Server の展開を使用する大企業) では、既存の環境を保護する方法について検討する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="4c9db-105">However, small and medium-sized companies (or large companies with small BizTalk Server deployments) should also be concerned with how to protect their environments.</span></span> <span data-ttu-id="4c9db-106">そこで、企業が [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ソリューションをどのように展開したか、または展開する予定であるかを調査し、使用可能なリソースと実現できる最善のセキュリティとのバランスを考えた中小企業向けのサンプル アーキテクチャを導き出しました。</span><span class="sxs-lookup"><span data-stu-id="4c9db-106">After we looked at how companies deployed or plan to deploy their [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solutions, we derived a sample architecture for small and medium-sized companies that balances available resources with the greatest possible security.</span></span> <span data-ttu-id="4c9db-107">このセクションに記載されている情報は、独自の展開を計画する際に役立ててください。</span><span class="sxs-lookup"><span data-stu-id="4c9db-107">You should use the information in this section to help you plan your own deployment.</span></span> <span data-ttu-id="4c9db-108">実際に BizTalk Server を展開する際には、ビジネスのニーズと資産の評価結果に応じたアーキテクチャの使用が必要になります。</span><span class="sxs-lookup"><span data-stu-id="4c9db-108">After you evaluate your business needs and assets you might decide on a different architecture for your BizTalk Server deployment.</span></span>  
  
 <span data-ttu-id="4c9db-109">どのようなアーキテクチャを使用するのが適しているのかを簡単に確認できるようにするために、このセクションでは環境で使用することが考えられるさまざまなアダプタに基づいたサンプル アーキテクチャを提供します。</span><span class="sxs-lookup"><span data-stu-id="4c9db-109">To make it easier to see how your architecture would look, this section provides sample architectures based on various adapters that you might use in your environment.</span></span> <span data-ttu-id="4c9db-110">図では、トポロジのどのコンポーネントがアダプタに依存しないコンポーネントであるか、およびどのコンポーネントが BizTalk Server 環境で使用するアダプタに依存しているかを示します。</span><span class="sxs-lookup"><span data-stu-id="4c9db-110">The figures show you which components of the topology are adapter-independent, and which components depend on the adapter you use in your BizTalk Server environment.</span></span>  
  
 <span data-ttu-id="4c9db-111">また、BizTalk Server で使用できるいくつかのアダプタに基づいた使用シナリオについても見ていきます。</span><span class="sxs-lookup"><span data-stu-id="4c9db-111">We also examine usage scenarios based on some of the adapters you can use with BizTalk Server.</span></span> <span data-ttu-id="4c9db-112">独自のアーキテクチャの計画および設計に役立つように、このサンプル アーキテクチャの脅威モデル分析を提供します。</span><span class="sxs-lookup"><span data-stu-id="4c9db-112">To help you as you plan and design your own architecture, we provide a threat model analysis of this sample architecture.</span></span> <span data-ttu-id="4c9db-113">この分析によって、パートナーとの通信に使用するアダプタに応じて、企業に影響を与える可能性があるセキュリティ上の潜在的な問題の理解を深めることができます。</span><span class="sxs-lookup"><span data-stu-id="4c9db-113">This analysis gives you a deeper look at the potential security issues that might affect your company, depending on the adapters you use to communicate with your partners.</span></span>  
  
 <span data-ttu-id="4c9db-114">このセクションでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のセキュリティで保護された展開を設計するための情報を提供しますが、実環境でのセキュリティを強化するには、その環境に含まれるサーバーどうしの通信をセキュリティで保護する方法についても検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c9db-114">While this section gives you information to help you design a secure deployment of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], to increase the security in your environment you should also consider securing the communication between the servers in the environment.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4c9db-115">ここでは、ビジネス アクティビティ監視 (BAM) を使用していない前提で説明します。</span><span class="sxs-lookup"><span data-stu-id="4c9db-115">This section assumes that you are not using Business Activity Monitoring (BAM).</span></span> <span data-ttu-id="4c9db-116">この機能を使用する場合は、セキュリティについて別途考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c9db-116">This feature requires additional security considerations.</span></span> <span data-ttu-id="4c9db-117">これは、後ほど[サンプル BizTalk Server アーキテクチャ](../core/sample-biztalk-server-architectures.md)です。</span><span class="sxs-lookup"><span data-stu-id="4c9db-117">This is discussed in [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4c9db-118">このドキュメントに記載されていないアダプタの詳細については、BizTalk Server デベロッパー センターを参照してください ([http://go.microsoft.com/fwlink/?LinkId=46420](http://go.microsoft.com/fwlink/?LinkId=46420))。</span><span class="sxs-lookup"><span data-stu-id="4c9db-118">For more information about adapters not described in this document, see the BizTalk Server Developer Center ([http://go.microsoft.com/fwlink/?LinkId=46420](http://go.microsoft.com/fwlink/?LinkId=46420).)</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4c9db-119">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4c9db-119">In This Section</span></span>  
  
-   [<span data-ttu-id="4c9db-120">サンプル アーキテクチャ: 基盤となる BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="4c9db-120">Sample Architecture: Base BizTalk Server</span></span>](../core/sample-architecture-base-biztalk-server.md)  
  
-   [<span data-ttu-id="4c9db-121">サンプル アーキテクチャ: HTTP アダプタと SOAP アダプタ</span><span class="sxs-lookup"><span data-stu-id="4c9db-121">Sample Architecture: HTTP and SOAP Adapters</span></span>](../core/sample-architecture-http-and-soap-adapters.md)  
  
-   [<span data-ttu-id="4c9db-122">BizTalk メッセージ キューのサンプル アーキテクチャ:</span><span class="sxs-lookup"><span data-stu-id="4c9db-122">Sample Architecture: BizTalk Message Queuing</span></span>](../core/sample-architecture-biztalk-message-queuing.md)  
  
-   [<span data-ttu-id="4c9db-123">FTP アダプターのサンプル アーキテクチャ:</span><span class="sxs-lookup"><span data-stu-id="4c9db-123">Sample Architecture: FTP Adapter</span></span>](../core/sample-architecture-ftp-adapter.md)  
  
-   [<span data-ttu-id="4c9db-124">ファイル アダプターのサンプル アーキテクチャ:</span><span class="sxs-lookup"><span data-stu-id="4c9db-124">Sample Architecture: File Adapter</span></span>](../core/sample-architecture-file-adapter.md)