---
title: "サンプル アーキテクチャ: HTTP アダプタと SOAP アダプタ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, security
- architecture, examples
- SOAP adapters, security
- Web Publishing
- security, examples
- security, architecture
- SOAP adapters, architecture examples
- examples, architecture
- architecture, security
- HTTP adapters, architecture examples
- reverse proxy rules
- ISA Server implementation
- HTTP adapters, security
ms.assetid: 935197d0-5108-4970-b237-3c6d5b40c5e9
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dae8be185084a9a838876e3d50b605a63c161b66
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sample-architecture-http-and-soap-adapters"></a><span data-ttu-id="e5200-102">サンプル アーキテクチャ: HTTP アダプタと SOAP アダプタ</span><span class="sxs-lookup"><span data-stu-id="e5200-102">Sample Architecture: HTTP and SOAP Adapters</span></span>
<span data-ttu-id="e5200-103">このトピックでは、HTTP アダプターと SOAP アダプターを使用してメッセージを送受信する場合のサンプル アーキテクチャについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e5200-103">This topic describes the sample architecture when you use the HTTP and SOAP adapters to send and receive messages.</span></span>  
  
 <span data-ttu-id="e5200-104">次の図は、HTTP アダプタまたは SOAP アダプタを使用する場合の BizTalk Server サンプル アーキテクチャのコンポーネントを示しています。</span><span class="sxs-lookup"><span data-stu-id="e5200-104">The following figure shows the components of the BizTalk Server sample architecture when you use the HTTP or SOAP adapters.</span></span>  
  
 <span data-ttu-id="e5200-105">**HTTP アダプタまたは SOAP アダプタを示すサンプル アーキテクチャを図 1**</span><span class="sxs-lookup"><span data-stu-id="e5200-105">**Figure 1 Sample architecture that shows HTTP or SOAP adapters**</span></span>  
  
 <span data-ttu-id="e5200-106">![HTTP または SOAP アダプターのアーキテクチャをサンプル](../core/media/tdi-sec-refarch-http.gif "TDI_Sec_RefArch_HTTP")</span><span class="sxs-lookup"><span data-stu-id="e5200-106">![Sample architecture for HTTP or SOAP adapter](../core/media/tdi-sec-refarch-http.gif "TDI_Sec_RefArch_HTTP")</span></span>  
  
 <span data-ttu-id="e5200-107">このサンプル アーキテクチャには、次のセクションに記載されているコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e5200-107">This sample architecture contains the components as discussed in the following sections.</span></span>  
  
## <a name="perimeter-networkinternet"></a><span data-ttu-id="e5200-108">境界ネットワーク - インターネット</span><span class="sxs-lookup"><span data-stu-id="e5200-108">Perimeter network―Internet</span></span>  
 <span data-ttu-id="e5200-109">リバース プロキシ ルール (、TMG サーバー実装が呼び出される Web 公開) を使用して、E ビジネスを保護するには、ファイアウォールに、インターネットに接続されたファイアウォール (ファイアウォール 1) からメッセージを中継することをお勧め、SOAP アダプターと HTTP アダプターを使用する場合ドメイン (ファイアウォール 2)、および BizTalk Server 分離ホストを実行するには、このファイアウォールからです。</span><span class="sxs-lookup"><span data-stu-id="e5200-109">When you use the SOAP and HTTP adapters, we recommend that you use reverse proxy rules (the TMG Server implementation is called Web Publishing) to relay the message from the Internet-facing firewall (Firewall 1) to the firewall that helps protect the E-Business domain (Firewall 2), and from this firewall to the BizTalk Server that runs the isolated host.</span></span> <span data-ttu-id="e5200-110">Web 公開ルールの詳細については、Microsoft Web サイトを参照してください。 [http://go.microsoft.com/fwlink/?LinkID=205340](http://go.microsoft.com/fwlink/?LinkID=205340) (http://go.microsoft.com/fwlink/?LinkID=205340)。</span><span class="sxs-lookup"><span data-stu-id="e5200-110">For more information about Web Publishing rules, see the Microsoft Web site at [http://go.microsoft.com/fwlink/?LinkID=205340](http://go.microsoft.com/fwlink/?LinkID=205340) (http://go.microsoft.com/fwlink/?LinkID=205340).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e5200-111">リバース プロキシを使用するときは、境界ネットワークに Web サーバーは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="e5200-111">When you use reverse proxy, you do not need Web servers in the perimeter network.</span></span>  
  
## <a name="perimeter-networkintranet"></a><span data-ttu-id="e5200-112">境界ネットワーク - イントラネット</span><span class="sxs-lookup"><span data-stu-id="e5200-112">Perimeter network―intranet</span></span>  
 <span data-ttu-id="e5200-113">企業では一般的にはインターネット ベースの通信に HTTP プロトコルと SOAP プロトコルを使用するので、このシナリオをサポートするためにイントラネット境界ネットワークにサーバーは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="e5200-113">Companies commonly use the HTTP and SOAP protocols for Internet-based communications, and therefore you do not need any servers in the intranet perimeter network to support this scenario.</span></span> <span data-ttu-id="e5200-114">HTTP プロトコルまたは SOAP プロトコル経由で BizTalk Server と統合する内部アプリケーションがイントラネット内にある場合、インターネット境界ネットワークに対する推奨事項に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5200-114">If you have an internal application in the intranet that integrates with BizTalk Server through the HTTP or SOAP protocols, you should follow the recommendations for the Internet perimeter network.</span></span>  
  
## <a name="e-business-domain"></a><span data-ttu-id="e5200-115">E ビジネス ドメイン</span><span class="sxs-lookup"><span data-stu-id="e5200-115">E-Business domain</span></span>  
 <span data-ttu-id="e5200-116">このドメインには、BizTalk Server の実装によって使用されるインフラストラクチャとアプリケーションがすべて含まれます。</span><span class="sxs-lookup"><span data-stu-id="e5200-116">This domain contains all the infrastructure and applications used by your BizTalk Server implementation.</span></span> <span data-ttu-id="e5200-117">このドメイン内のサーバーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e5200-117">The servers in this domain are:</span></span>  
  
-   <span data-ttu-id="e5200-118">**BizTalk Server (処理ホストおよび追跡ホスト)。**</span><span class="sxs-lookup"><span data-stu-id="e5200-118">**BizTalk Server (processing and tracking hosts).**</span></span> <span data-ttu-id="e5200-119">このサーバーには、BizTalk Server ランタイムがインストールされており、BizTalk オーケストレーション、パイプライン、ビジネス ルール エンジン、およびその他のビジネス プロセスを含むホストのインスタンスが格納されています。</span><span class="sxs-lookup"><span data-stu-id="e5200-119">This server has an installation of the BizTalk Server runtime, and has instances of the hosts that contain the BizTalk orchestrations, pipelines, Business Rule Engine, and other business processes.</span></span> <span data-ttu-id="e5200-120">このサーバーでは、正常性監視とビジネスの監視データの追跡をサポートするホストのホスト インスタンスもあります。</span><span class="sxs-lookup"><span data-stu-id="e5200-120">This server also has a host instance of a host that supports tracking of health monitoring and business monitoring data.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e5200-121">パフォーマンスを向上させる必要がある場合、処理ホストのホスト インスタンス用の環境に BizTalk Server をさらに追加できます。</span><span class="sxs-lookup"><span data-stu-id="e5200-121">As your performance needs increase, you can add more BizTalk Servers to your environment for host instances of your processing hosts.</span></span>  
  
-   <span data-ttu-id="e5200-122">**BizTalk Server (SOAP および HTTP アダプター用の分離ホスト)。**</span><span class="sxs-lookup"><span data-stu-id="e5200-122">**BizTalk Server (isolated hosts for SOAP and HTTP adapters).**</span></span> <span data-ttu-id="e5200-123">このサーバーには BizTalk Server ランタイムがインストールされていて、HTTP アダプタと SOAP アダプタを含むホストのインスタンスのみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e5200-123">This server has an installation of the BizTalk Server runtime, and has only instances of the hosts that contain the HTTP and SOAP adapters.</span></span> <span data-ttu-id="e5200-124">HTTP アダプタと SOAP アダプタはそれぞれが実行されるコンピュータにインターネット インフォメーション サービス (IIS) をインストールする必要があるため、これらのホストは個別のサーバーで実行されます。</span><span class="sxs-lookup"><span data-stu-id="e5200-124">These hosts run in a separate server because these adapters require that you install Internet Information Services (IIS) on the computer where they run.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e5200-125">パフォーマンスを向上させる必要がある場合、HTTP アダプタ ホストと SOAP アダプタ ホストのホスト インスタンス用の環境に BizTalk Server をさらに追加できます。</span><span class="sxs-lookup"><span data-stu-id="e5200-125">As your performance needs increase, you can add more BizTalk Servers to your environment for host instances of your HTTP and SOAP adapter hosts.</span></span> <span data-ttu-id="e5200-126">これを行う場合、ネットワーク負荷分散 (NLB) を構成する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="e5200-126">When you do this, you must also configure Network Load Balancing (NLB).</span></span> <span data-ttu-id="e5200-127">BizTalk Server の高可用性を構成する方法の詳細については、次を参照してください。[高可用性の計画](../core/planning-for-high-availability3.md)です。</span><span class="sxs-lookup"><span data-stu-id="e5200-127">For more information about how to configure BizTalk Server for high availability, see [Planning for High Availability](../core/planning-for-high-availability3.md).</span></span>  
  
-   <span data-ttu-id="e5200-128">**マスター シークレット サーバーです。**</span><span class="sxs-lookup"><span data-stu-id="e5200-128">**Master secret server.**</span></span> <span data-ttu-id="e5200-129">同じように、[サンプル アーキテクチャ: 基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="e5200-129">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="e5200-130">**SQL Server。**</span><span class="sxs-lookup"><span data-stu-id="e5200-130">**SQL Server.**</span></span> <span data-ttu-id="e5200-131">同じように、[サンプル アーキテクチャ: 基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="e5200-131">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="e5200-132">**ドメイン コント ローラー。**</span><span class="sxs-lookup"><span data-stu-id="e5200-132">**Domain controller.**</span></span> <span data-ttu-id="e5200-133">同じように、[サンプル アーキテクチャ: 基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="e5200-133">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="e5200-134">**管理ツールです。**</span><span class="sxs-lookup"><span data-stu-id="e5200-134">**Administration tools.**</span></span> <span data-ttu-id="e5200-135">同じように、[サンプル アーキテクチャ: 基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="e5200-135">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5200-136">参照</span><span class="sxs-lookup"><span data-stu-id="e5200-136">See Also</span></span>  
 <span data-ttu-id="e5200-137">[小規模および中規模企業向けのサンプル アーキテクチャ](../core/sample-architectures-for-small-medium-sized-companies.md) </span><span class="sxs-lookup"><span data-stu-id="e5200-137">[Sample Architectures for Small & Medium-Sized Companies](../core/sample-architectures-for-small-medium-sized-companies.md) </span></span>  
 [<span data-ttu-id="e5200-138">脅威モデル分析のサンプル シナリオ</span><span class="sxs-lookup"><span data-stu-id="e5200-138">Sample Scenarios for Threat Model Analysis</span></span>](../core/sample-scenarios-for-threat-model-analysis.md)