---
title: "サンプル アーキテクチャ: 基盤となる BizTalk Server |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- architecture, examples
- IPSec
- BizTalk Server, examples
- security, examples
- security, architecture
- IPSec, about IPSec
- BizTalk Server, architecture
- architecture, security
ms.assetid: 7ccc1ef3-670f-423f-b6ca-3d56b9bbeabf
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea815c0165f58c28cea8ce7cae35fd6ed7437323
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sample-architecture-base-biztalk-server"></a><span data-ttu-id="67dce-102">サンプル アーキテクチャ: 基盤となる BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="67dce-102">Sample Architecture: Base BizTalk Server</span></span>
<span data-ttu-id="67dce-103">ここでは、基盤となるサンプル アーキテクチャについて説明します。</span><span class="sxs-lookup"><span data-stu-id="67dce-103">This topic discusses the base sample architecture.</span></span> <span data-ttu-id="67dce-104">BizTalk Server の展開の中で、アダプターに依存しないコンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="67dce-104">It describes the components in a BizTalk Server deployment that are adapter-independent.</span></span> <span data-ttu-id="67dce-105">BizTalk Server の展開に少なくともこれらのコンポーネントを含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="67dce-105">We recommend that any BizTalk Server deployment have at least these components.</span></span>  
  
 <span data-ttu-id="67dce-106">次の図は、基盤となる BizTalk Server サンプル アーキテクチャのコンポーネントを示しています。</span><span class="sxs-lookup"><span data-stu-id="67dce-106">The following figure shows the components of the base BizTalk Server sample architecture.</span></span> <span data-ttu-id="67dce-107">これらのコンポーネントは、後半で説明するアダプター固有の BizTalk Server アーキテクチャにすべて出現します。</span><span class="sxs-lookup"><span data-stu-id="67dce-107">These components appear in all the adapter-specific BizTalk Server architectures that we discuss in later sections.</span></span>  
  
 <span data-ttu-id="67dce-108">**図 1 の基本アーキテクチャ コンポーネント**</span><span class="sxs-lookup"><span data-stu-id="67dce-108">**Figure 1 Base architecture components**</span></span>  
  
 <span data-ttu-id="67dce-109">![ベース アーキテクチャ コンポーネント](../core/media/tdi-sec-refarch.gif "tdi_sec_refarch _")</span><span class="sxs-lookup"><span data-stu-id="67dce-109">![Base architecture components](../core/media/tdi-sec-refarch.gif "TDI_Sec_RefArch_")</span></span>  
  
 <span data-ttu-id="67dce-110">このサンプル アーキテクチャには、以下のセクションに記載する項目が含まれています。</span><span class="sxs-lookup"><span data-stu-id="67dce-110">This sample architecture contains the items discussed in the following sections.</span></span>  
  
## <a name="perimeter-networkinternet"></a><span data-ttu-id="67dce-111">境界ネットワーク-インターネット</span><span class="sxs-lookup"><span data-stu-id="67dce-111">Perimeter network―internet</span></span>  
  
-   <span data-ttu-id="67dce-112">この境界ネットワーク (DMZ、非武装地帯、スクリーン サブネットとも呼ばれます) には、インターネット関連のサービスを提供するサーバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="67dce-112">This perimeter network (also known as DMZ, demilitarized zone, and screened subnet) contains servers that provide Internet-related services.</span></span> <span data-ttu-id="67dce-113">このドメインには、BizTalk Server、BizTalk 受信場所、エンタープライズ シングル サインオン サーバーはありません。</span><span class="sxs-lookup"><span data-stu-id="67dce-113">There are no BizTalk Servers, BizTalk receive locations, or Enterprise Single Sign-On servers in this domain.</span></span>  
  
## <a name="perimeter-networkintranet"></a><span data-ttu-id="67dce-114">境界ネットワーク - イントラネット</span><span class="sxs-lookup"><span data-stu-id="67dce-114">Perimeter network―intranet</span></span>  
 <span data-ttu-id="67dce-115">この境界ネットワークには、イントラネット関連のサービスを提供するサーバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="67dce-115">This perimeter network contains servers that provide intranet-related services.</span></span> <span data-ttu-id="67dce-116">イントラネット (企業ネットワークなど) とアプリケーションが実行されるサーバー間のセキュリティに追加の層を提供します。</span><span class="sxs-lookup"><span data-stu-id="67dce-116">It provides an additional layer of security between your intranet (for example, a corporate network) and the servers that run the application.</span></span> <span data-ttu-id="67dce-117">インターネット境界ネットワークと同様に、イントラネット境界ネットワークには、BizTalk Server、BizTalk 受信場所、エンタープライズ シングル サインオン サーバーは含まれません。</span><span class="sxs-lookup"><span data-stu-id="67dce-117">Like the Internet perimeter network, the intranet perimeter network does not contain BizTalk Servers, BizTalk receive locations, or Enterprise Single Sign-On servers.</span></span>  
  
## <a name="e-business-domain"></a><span data-ttu-id="67dce-118">E ビジネス ドメイン</span><span class="sxs-lookup"><span data-stu-id="67dce-118">E-Business Domain</span></span>  
 <span data-ttu-id="67dce-119">このドメインには、BizTalk Server の実装によって使用されるインフラストラクチャとアプリケーションがすべて含まれます。</span><span class="sxs-lookup"><span data-stu-id="67dce-119">This domain contains all the infrastructure and applications used by your BizTalk Server implementation.</span></span> <span data-ttu-id="67dce-120">このドメイン内のサーバーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="67dce-120">The servers in this domain are:</span></span>  
  
-   <span data-ttu-id="67dce-121">**BizTalk Server です。**</span><span class="sxs-lookup"><span data-stu-id="67dce-121">**BizTalk Server.**</span></span> <span data-ttu-id="67dce-122">このサーバーには BizTalk Server ランタイムのインストールと、さまざまな BizTalk ホストのインスタンスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="67dce-122">This server has an installation of the BizTalk Server runtime and instances of various BizTalk Hosts.</span></span> <span data-ttu-id="67dce-123">環境内の BizTalk Server の数は、実行されるホストの種類とパフォーマンスのニーズによって異なります。</span><span class="sxs-lookup"><span data-stu-id="67dce-123">The number of BizTalk Servers in the environment depends on the type of hosts they run and the performance needs.</span></span> <span data-ttu-id="67dce-124">パフォーマンスを向上させる必要がある場合、処理ホストのホスト インスタンス用の環境に BizTalk Server をさらに追加できます。</span><span class="sxs-lookup"><span data-stu-id="67dce-124">As your performance needs increase, you can add more BizTalk Servers to your environment for host instances of your processing hosts.</span></span>  
  
-   <span data-ttu-id="67dce-125">**マスター シークレット サーバーです。**</span><span class="sxs-lookup"><span data-stu-id="67dce-125">**Master secret server.**</span></span> <span data-ttu-id="67dce-126">このサーバーは、エンタープライズ シングル サインオン (SSO) マスター シークレット サーバーです。</span><span class="sxs-lookup"><span data-stu-id="67dce-126">This server is the Enterprise Single Sign-On (SSO) master secret server.</span></span> <span data-ttu-id="67dce-127">SSO システムが SSO データベース内のデータの暗号化に使用するマスター シークレット (暗号化キー) が保存されています。</span><span class="sxs-lookup"><span data-stu-id="67dce-127">It holds the master secret (encryption key) that the SSO system uses to encrypt the data in the SSO database.</span></span>  
  
-   <span data-ttu-id="67dce-128">**SQL Server。**</span><span class="sxs-lookup"><span data-stu-id="67dce-128">**SQL Server.**</span></span> <span data-ttu-id="67dce-129">このサーバーには、BizTalk データベースが含まれます。</span><span class="sxs-lookup"><span data-stu-id="67dce-129">This server contains the BizTalk databases.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="67dce-130">フェールオーバー保護のために、各 BizTalk データベースをクラスター化することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="67dce-130">For failover protection, we recommend that you cluster each BizTalk database.</span></span> <span data-ttu-id="67dce-131">Microsoft SQL Server フェールオーバー クラスタ リングの詳細については、Microsoft MSDN Web サイトを参照してください。 [http://go.microsoft.com/fwlink/?LinkID=190216](http://go.microsoft.com/fwlink/?LinkID=190216)です。</span><span class="sxs-lookup"><span data-stu-id="67dce-131">For more information about Microsoft SQL Server failover clustering, see the Microsoft MSDN Web site at [http://go.microsoft.com/fwlink/?LinkID=190216](http://go.microsoft.com/fwlink/?LinkID=190216).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="67dce-132">パフォーマンスのニーズによっては、BizTalk データベースを SQL Server が実行されている複数のコンピューターに分散することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="67dce-132">Depending on your performance needs, you might have to separate the BizTalk databases into multiple computers that run SQL Server.</span></span>  
  
-   <span data-ttu-id="67dce-133">**ドメイン コント ローラー。**</span><span class="sxs-lookup"><span data-stu-id="67dce-133">**Domain controller.**</span></span> <span data-ttu-id="67dce-134">このサーバーは E ビジネス Active Directory ドメインをホストします。</span><span class="sxs-lookup"><span data-stu-id="67dce-134">This server hosts the E-Business Active Directory domain.</span></span> <span data-ttu-id="67dce-135">BizTalk Server へのアクセスが必要なすべてのグループと個別のアカウントについての情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="67dce-135">It contains information about all the groups and individual accounts that need access to BizTalk Server.</span></span>  
  
-   <span data-ttu-id="67dce-136">**管理ツールです。**</span><span class="sxs-lookup"><span data-stu-id="67dce-136">**Administration tools.**</span></span> <span data-ttu-id="67dce-137">このドメインのサーバーの 1 つは、管理ツール (BizTalk 管理コンソールおよびエンタープライズ シングル サインオン (SSO) 管理ユーティリティ) をホストしています。</span><span class="sxs-lookup"><span data-stu-id="67dce-137">One of the servers in this domain hosts the administration tools: BizTalk Administration console and Enterprise Single Sign-On (SSO) administration utility.</span></span>  
  
## <a name="firewalls-and-domains"></a><span data-ttu-id="67dce-138">ファイアウォールとドメイン</span><span class="sxs-lookup"><span data-stu-id="67dce-138">Firewalls and Domains</span></span>  
 <span data-ttu-id="67dce-139">図 1 では、Forefront Threat Management Gateway (TMG) 2010 サーバーがソフトウェア ファイアウォールの役割を担い、これらの各ドメインを保護すると共に境界となっています。</span><span class="sxs-lookup"><span data-stu-id="67dce-139">In Figure 1, Forefront Threat Management Gateway (TMG) 2010 server acts as a software firewall to help protect and contain each of these domains.</span></span> <span data-ttu-id="67dce-140">また、E ビジネス ドメインには独自のドメイン コントローラーがあり、このドメインは他のドメインとの信頼関係がありません。</span><span class="sxs-lookup"><span data-stu-id="67dce-140">Additionally, the E-Business domain has its own domain controller, and this domain does not trust any other domain.</span></span> <span data-ttu-id="67dce-141">ドメインと信頼関係に対してファイアウォールを構成する方法の詳細については、Microsoft ヘルプとサポート Web サイトを参照してください。 [http://go.microsoft.com/fwlink/?LinkId=25230](http://go.microsoft.com/fwlink/?LinkId=25230)です。</span><span class="sxs-lookup"><span data-stu-id="67dce-141">For more information about how to configure a firewall for domains and trusts, see the Microsoft Help and Support Web site at [http://go.microsoft.com/fwlink/?LinkId=25230](http://go.microsoft.com/fwlink/?LinkId=25230).</span></span>  
  
 <span data-ttu-id="67dce-142">サンプル アーキテクチャには 2 つのファイアウォールがあります。</span><span class="sxs-lookup"><span data-stu-id="67dce-142">The sample architecture has two firewalls:</span></span>  
  
-   <span data-ttu-id="67dce-143">**ファイアウォール 1。**</span><span class="sxs-lookup"><span data-stu-id="67dce-143">**Firewall 1.**</span></span> <span data-ttu-id="67dce-144">このファイアフォールには 3 つのネットワーク インターフェイスがあり、インターネット、イントラネット、および境界ネットワークからのトラフィックをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="67dce-144">This firewall has three network interfaces: It routes traffic from the Internet, the intranet, and the perimeter networks.</span></span>  
  
-   <span data-ttu-id="67dce-145">**ファイアウォール 2。**</span><span class="sxs-lookup"><span data-stu-id="67dce-145">**Firewall 2.**</span></span> <span data-ttu-id="67dce-146">このファイアウォールはデュアルホームです。境界ネットワーク (インターネットとイントラネットの両方) および E ビジネス ドメインからのトラフィックをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="67dce-146">This firewall is dual-homed: It routes traffic from the perimeter networks (both Internet and intranet) and the E-Business domain.</span></span>  
  
 <span data-ttu-id="67dce-147">境界ネットワーク内のコンピューターはどのドメインにも属していないので、相互通信することはありません。</span><span class="sxs-lookup"><span data-stu-id="67dce-147">The computers in the perimeter networks are not members of any domain, and they do not communicate with each other.</span></span>  
  
## <a name="ipsec"></a><span data-ttu-id="67dce-148">IPsec (IPsec)</span><span class="sxs-lookup"><span data-stu-id="67dce-148">IPsec</span></span>  
 <span data-ttu-id="67dce-149">Internet Protocol security (IPSec) を使用して、E ビジネス ドメイン内のすべてのサーバー間の通信をセキュリティで保護することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="67dce-149">We recommend that you use Internet Protocol security (IPSec) to help secure the communication between all the servers in the E-Business domain.</span></span> <span data-ttu-id="67dce-150">IPsec 規則は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="67dce-150">The IPsec rules are as follows:</span></span>  
  
-   <span data-ttu-id="67dce-151">BizTalk Server とドメイン コントローラー間の認証されたトラフィックを許可します。</span><span class="sxs-lookup"><span data-stu-id="67dce-151">Allow authenticated traffic between BizTalk Server and the domain controller.</span></span>  
  
-   <span data-ttu-id="67dce-152">BizTalk Server と管理ツール サーバー間の認証されたトラフィックを許可します。</span><span class="sxs-lookup"><span data-stu-id="67dce-152">Allow authenticated traffic between BizTalk Server and the administration tools server.</span></span>  
  
-   <span data-ttu-id="67dce-153">BizTalk Server とマスター シークレット サーバー間の認証されたトラフィックを許可します。</span><span class="sxs-lookup"><span data-stu-id="67dce-153">Allow authenticated traffic between BizTalk Server and the master secret server.</span></span>  
  
-   <span data-ttu-id="67dce-154">BizTalk Server と SQL Server 間の認証されたトラフィックを許可します。</span><span class="sxs-lookup"><span data-stu-id="67dce-154">Allow authenticated traffic between BizTalk Server and the SQL Server.</span></span>  
  
-   <span data-ttu-id="67dce-155">マスター シークレット サーバーとドメイン コントローラー間の認証されたトラフィックを許可します。</span><span class="sxs-lookup"><span data-stu-id="67dce-155">Allow authenticated traffic between the master secret server and the domain controller.</span></span>  
  
-   <span data-ttu-id="67dce-156">マスター シークレット サーバーと BizTalk Server (分離ホスト、処理ホスト、インプロセス ホスト、追跡ホスト) 間の認証されたトラフィックを許可します。</span><span class="sxs-lookup"><span data-stu-id="67dce-156">Allow authenticated traffic between the master secret server and the BizTalk Server (isolated, processing, in-process, and tracking hosts.)</span></span>  
  
-   <span data-ttu-id="67dce-157">マスター シークレット サーバーと SQL Server (SSO データベース) 間の認証されたトラフィックを許可します。</span><span class="sxs-lookup"><span data-stu-id="67dce-157">Allow authenticated traffic between the master secret server and the SQL Server (SSO databases).</span></span>  
  
-   <span data-ttu-id="67dce-158">ドメイン コントローラーとドメイン内のすべてのサーバー間の認証されたトラフィックを許可します。</span><span class="sxs-lookup"><span data-stu-id="67dce-158">Allow authenticated traffic between the domain controller and all the servers in the domain.</span></span>  
  
-   <span data-ttu-id="67dce-159">管理ツール サーバーとドメイン内のすべてのサーバー間の認証されたトラフィックを許可します。</span><span class="sxs-lookup"><span data-stu-id="67dce-159">Allow authenticated traffic between the administration tools server and all the servers in the domain.</span></span>  
  
 <span data-ttu-id="67dce-160">ドメイン内に BizTalk Server、SQL Server、マスター シークレット サーバー、または管理ツール サーバーへのアクセスが不要なその他のアプリケーションがある場合、それらのアプリケーションと該当するサーバー間のトラフィックをブロックしてください。</span><span class="sxs-lookup"><span data-stu-id="67dce-160">If you have other applications in the domain that do not need access to the BizTalk Server, SQL Server, master secret server, or administration tools server, block traffic between those applications and the appropriate servers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67dce-161">参照</span><span class="sxs-lookup"><span data-stu-id="67dce-161">See Also</span></span>  
 <span data-ttu-id="67dce-162">[セキュリティの計画](../core/planning-for-security.md) </span><span class="sxs-lookup"><span data-stu-id="67dce-162">[Planning for Security](../core/planning-for-security.md) </span></span>  
 <span data-ttu-id="67dce-163">[小規模および中規模企業向けのサンプル アーキテクチャ](../core/sample-architectures-for-small-medium-sized-companies.md) </span><span class="sxs-lookup"><span data-stu-id="67dce-163">[Sample Architectures for Small & Medium-Sized Companies](../core/sample-architectures-for-small-medium-sized-companies.md) </span></span>  
 [<span data-ttu-id="67dce-164">脅威モデル分析のサンプル シナリオ</span><span class="sxs-lookup"><span data-stu-id="67dce-164">Sample Scenarios for Threat Model Analysis</span></span>](../core/sample-scenarios-for-threat-model-analysis.md)