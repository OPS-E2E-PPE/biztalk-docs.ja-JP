---
title: サンプル アーキテクチャ:HTTP アダプターと SOAP アダプター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77b7d8557564cfa94bbfb243447e5e85d4b6865d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65271074"
---
# <a name="sample-architecture-http-and-soap-adapters"></a><span data-ttu-id="22e6c-102">サンプル アーキテクチャ:HTTP アダプターと SOAP アダプター</span><span class="sxs-lookup"><span data-stu-id="22e6c-102">Sample Architecture: HTTP and SOAP Adapters</span></span>
<span data-ttu-id="22e6c-103">このトピックでは、HTTP アダプタと SOAP アダプタを使用してメッセージを送受信するときに、サンプル アーキテクチャについて説明します。</span><span class="sxs-lookup"><span data-stu-id="22e6c-103">This topic describes the sample architecture when you use the HTTP and SOAP adapters to send and receive messages.</span></span>  
  
 <span data-ttu-id="22e6c-104">次の図は、HTTP または SOAP アダプターを使用する場合に、BizTalk Server のコンポーネントのサンプル アーキテクチャを示します。</span><span class="sxs-lookup"><span data-stu-id="22e6c-104">The following figure shows the components of the BizTalk Server sample architecture when you use the HTTP or SOAP adapters.</span></span>  
  
 <span data-ttu-id="22e6c-105">**図 1. HTTP または SOAP アダプターを示すサンプル アーキテクチャ**</span><span class="sxs-lookup"><span data-stu-id="22e6c-105">**Figure 1 Sample architecture that shows HTTP or SOAP adapters**</span></span>  
  
 <span data-ttu-id="22e6c-106">![HTTP または SOAP アダプターのアーキテクチャのサンプル](../core/media/tdi-sec-refarch-http.gif "TDI_Sec_RefArch_HTTP")</span><span class="sxs-lookup"><span data-stu-id="22e6c-106">![Sample architecture for HTTP or SOAP adapter](../core/media/tdi-sec-refarch-http.gif "TDI_Sec_RefArch_HTTP")</span></span>  
  
 <span data-ttu-id="22e6c-107">このサンプル アーキテクチャには、次のセクションで説明したように、コンポーネントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="22e6c-107">This sample architecture contains the components as discussed in the following sections.</span></span>  
  
## <a name="perimeter-networkinternet"></a><span data-ttu-id="22e6c-108">境界ネットワーク-インターネット</span><span class="sxs-lookup"><span data-stu-id="22e6c-108">Perimeter network―Internet</span></span>  
 <span data-ttu-id="22e6c-109">リバース プロキシ ルールの (TMG サーバー実装は Web 公開呼びます) を使用して、E ビジネスを保護するファイアウォールからインターネットに接続されたファイアウォール (ファイアウォール 1) メッセージを中継することをお勧め、SOAP および HTTP アダプターを使用する場合ドメイン (ファイアウォール 2)、および BizTalk Server 分離ホストを実行するには、このファイアウォールから。</span><span class="sxs-lookup"><span data-stu-id="22e6c-109">When you use the SOAP and HTTP adapters, we recommend that you use reverse proxy rules (the TMG Server implementation is called Web Publishing) to relay the message from the Internet-facing firewall (Firewall 1) to the firewall that helps protect the E-Business domain (Firewall 2), and from this firewall to the BizTalk Server that runs the isolated host.</span></span> <span data-ttu-id="22e6c-110">Web 公開ルールの詳細については、Microsoft Web サイトを参照してください。 [ http://go.microsoft.com/fwlink/?LinkID=205340 ](http://go.microsoft.com/fwlink/?LinkID=205340) (http://go.microsoft.com/fwlink/?LinkID=205340)します。</span><span class="sxs-lookup"><span data-stu-id="22e6c-110">For more information about Web Publishing rules, see the Microsoft Web site at [http://go.microsoft.com/fwlink/?LinkID=205340](http://go.microsoft.com/fwlink/?LinkID=205340) (http://go.microsoft.com/fwlink/?LinkID=205340).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="22e6c-111">リバース プロキシを使用すると、境界ネットワーク内の Web サーバーは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="22e6c-111">When you use reverse proxy, you do not need Web servers in the perimeter network.</span></span>  
  
## <a name="perimeter-networkintranet"></a><span data-ttu-id="22e6c-112">境界ネットワーク-イントラネット</span><span class="sxs-lookup"><span data-stu-id="22e6c-112">Perimeter network―intranet</span></span>  
 <span data-ttu-id="22e6c-113">企業はインターネット ベースの通信に HTTP および SOAP プロトコルを使用する一般的と、このシナリオをサポートするためにイントラネット境界ネットワーク内のサーバーでそのため必要がありません。</span><span class="sxs-lookup"><span data-stu-id="22e6c-113">Companies commonly use the HTTP and SOAP protocols for Internet-based communications, and therefore you do not need any servers in the intranet perimeter network to support this scenario.</span></span> <span data-ttu-id="22e6c-114">HTTP または SOAP プロトコルを通じて BizTalk Server と統合された、イントラネット内の内部アプリケーションがあれば、インターネット境界ネットワークの推奨事項に従ってください。</span><span class="sxs-lookup"><span data-stu-id="22e6c-114">If you have an internal application in the intranet that integrates with BizTalk Server through the HTTP or SOAP protocols, you should follow the recommendations for the Internet perimeter network.</span></span>  
  
## <a name="e-business-domain"></a><span data-ttu-id="22e6c-115">E ビジネス ドメイン</span><span class="sxs-lookup"><span data-stu-id="22e6c-115">E-Business domain</span></span>  
 <span data-ttu-id="22e6c-116">このドメインには、すべてのインフラストラクチャと、BizTalk Server の実装で使用するアプリケーションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="22e6c-116">This domain contains all the infrastructure and applications used by your BizTalk Server implementation.</span></span> <span data-ttu-id="22e6c-117">このドメイン内のサーバーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="22e6c-117">The servers in this domain are:</span></span>  
  
-   <span data-ttu-id="22e6c-118">**BizTalk Server (処理ホストおよび追跡ホスト)。**</span><span class="sxs-lookup"><span data-stu-id="22e6c-118">**BizTalk Server (processing and tracking hosts).**</span></span> <span data-ttu-id="22e6c-119">このサーバーは、BizTalk Server ランタイムのインストールされてし、BizTalk オーケストレーション、パイプライン、ビジネス ルール エンジン、および他のビジネス プロセスが含まれているホストのインスタンスが存在します。</span><span class="sxs-lookup"><span data-stu-id="22e6c-119">This server has an installation of the BizTalk Server runtime, and has instances of the hosts that contain the BizTalk orchestrations, pipelines, Business Rule Engine, and other business processes.</span></span> <span data-ttu-id="22e6c-120">このサーバーでは、正常性の監視とビジネスの監視データの追跡をサポートするホストのホスト インスタンスもあります。</span><span class="sxs-lookup"><span data-stu-id="22e6c-120">This server also has a host instance of a host that supports tracking of health monitoring and business monitoring data.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="22e6c-121">パフォーマンス ニーズの増加に応じて、処理ホストのホスト インスタンスの環境に BizTalk Server を追加できます。</span><span class="sxs-lookup"><span data-stu-id="22e6c-121">As your performance needs increase, you can add more BizTalk Servers to your environment for host instances of your processing hosts.</span></span>  
  
-   <span data-ttu-id="22e6c-122">**BizTalk Server (SOAP および HTTP アダプター用の分離ホスト)。**</span><span class="sxs-lookup"><span data-stu-id="22e6c-122">**BizTalk Server (isolated hosts for SOAP and HTTP adapters).**</span></span> <span data-ttu-id="22e6c-123">このサーバーは、BizTalk Server ランタイムのインストールを備え、HTTP および SOAP アダプターが含まれているホストのインスタンスのみが存在します。</span><span class="sxs-lookup"><span data-stu-id="22e6c-123">This server has an installation of the BizTalk Server runtime, and has only instances of the hosts that contain the HTTP and SOAP adapters.</span></span> <span data-ttu-id="22e6c-124">これらのホスト実行を別のサーバーでこれらのアダプターでは、コンピューターのインターネット インフォメーション サービス (IIS) をインストールする必要があるために実行されます。</span><span class="sxs-lookup"><span data-stu-id="22e6c-124">These hosts run in a separate server because these adapters require that you install Internet Information Services (IIS) on the computer where they run.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="22e6c-125">パフォーマンス ニーズの増加に応じて、HTTP および SOAP アダプターのホストのホスト インスタンスの環境に BizTalk Server を追加できます。</span><span class="sxs-lookup"><span data-stu-id="22e6c-125">As your performance needs increase, you can add more BizTalk Servers to your environment for host instances of your HTTP and SOAP adapter hosts.</span></span> <span data-ttu-id="22e6c-126">これを行うときにネットワーク負荷分散 (NLB) を構成する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="22e6c-126">When you do this, you must also configure Network Load Balancing (NLB).</span></span> <span data-ttu-id="22e6c-127">高可用性のための BizTalk Server を構成する方法の詳細については、次を参照してください。[高可用性の計画](../core/planning-for-high-availability3.md)します。</span><span class="sxs-lookup"><span data-stu-id="22e6c-127">For more information about how to configure BizTalk Server for high availability, see [Planning for High Availability](../core/planning-for-high-availability3.md).</span></span>  
  
-   <span data-ttu-id="22e6c-128">**マスター シークレット サーバーです。**</span><span class="sxs-lookup"><span data-stu-id="22e6c-128">**Master secret server.**</span></span> <span data-ttu-id="22e6c-129">同じように、[サンプル アーキテクチャ。基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="22e6c-129">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="22e6c-130">**SQL Server。**</span><span class="sxs-lookup"><span data-stu-id="22e6c-130">**SQL Server.**</span></span> <span data-ttu-id="22e6c-131">同じように、[サンプル アーキテクチャ。基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="22e6c-131">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="22e6c-132">**ドメイン コント ローラー。**</span><span class="sxs-lookup"><span data-stu-id="22e6c-132">**Domain controller.**</span></span> <span data-ttu-id="22e6c-133">同じように、[サンプル アーキテクチャ。基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="22e6c-133">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="22e6c-134">**管理ツールです。**</span><span class="sxs-lookup"><span data-stu-id="22e6c-134">**Administration tools.**</span></span> <span data-ttu-id="22e6c-135">同じように、[サンプル アーキテクチャ。基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="22e6c-135">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22e6c-136">参照</span><span class="sxs-lookup"><span data-stu-id="22e6c-136">See Also</span></span>  
 <span data-ttu-id="22e6c-137">[中小規模の企業向けのサンプル アーキテクチャ](../core/sample-architectures-for-small-medium-sized-companies.md) </span><span class="sxs-lookup"><span data-stu-id="22e6c-137">[Sample Architectures for Small & Medium-Sized Companies](../core/sample-architectures-for-small-medium-sized-companies.md) </span></span>  
 [<span data-ttu-id="22e6c-138">脅威モデル分析のサンプル シナリオ</span><span class="sxs-lookup"><span data-stu-id="22e6c-138">Sample Scenarios for Threat Model Analysis</span></span>](../core/sample-scenarios-for-threat-model-analysis.md)