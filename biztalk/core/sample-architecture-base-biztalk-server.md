---
title: サンプル アーキテクチャ:基盤となる BizTalk Server |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4db442ec29ac9185bd1479219db795a9398073f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393958"
---
# <a name="sample-architecture-base-biztalk-server"></a><span data-ttu-id="7bbab-102">サンプル アーキテクチャ:基盤となる BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="7bbab-102">Sample Architecture: Base BizTalk Server</span></span>
<span data-ttu-id="7bbab-103">このトピックでは、基盤となるサンプル アーキテクチャについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7bbab-103">This topic discusses the base sample architecture.</span></span> <span data-ttu-id="7bbab-104">これには、BizTalk Server の展開でアダプターに依存しないコンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7bbab-104">It describes the components in a BizTalk Server deployment that are adapter-independent.</span></span> <span data-ttu-id="7bbab-105">BizTalk Server の展開に少なくともこれらのコンポーネントがあることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7bbab-105">We recommend that any BizTalk Server deployment have at least these components.</span></span>  
  
 <span data-ttu-id="7bbab-106">次の図は、サンプル アーキテクチャの基本の BizTalk Server コンポーネントを示します。</span><span class="sxs-lookup"><span data-stu-id="7bbab-106">The following figure shows the components of the base BizTalk Server sample architecture.</span></span> <span data-ttu-id="7bbab-107">これらのコンポーネントは、以降のセクションで説明するすべてのアダプター固有 BizTalk Server アーキテクチャに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7bbab-107">These components appear in all the adapter-specific BizTalk Server architectures that we discuss in later sections.</span></span>  
  
 <span data-ttu-id="7bbab-108">**図 1 基本アーキテクチャ コンポーネント**</span><span class="sxs-lookup"><span data-stu-id="7bbab-108">**Figure 1 Base architecture components**</span></span>  
  
 <span data-ttu-id="7bbab-109">![ベース アーキテクチャ コンポーネント](../core/media/tdi-sec-refarch.gif "tdi_sec_refarch _")</span><span class="sxs-lookup"><span data-stu-id="7bbab-109">![Base architecture components](../core/media/tdi-sec-refarch.gif "TDI_Sec_RefArch_")</span></span>  
  
 <span data-ttu-id="7bbab-110">このサンプル アーキテクチャには、次のセクションで説明されている項目が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7bbab-110">This sample architecture contains the items discussed in the following sections.</span></span>  
  
## <a name="perimeter-networkinternet"></a><span data-ttu-id="7bbab-111">境界ネットワーク-インターネット</span><span class="sxs-lookup"><span data-stu-id="7bbab-111">Perimeter network―internet</span></span>  
  
-   <span data-ttu-id="7bbab-112">この境界ネットワーク (DMZ、非武装地帯、およびスクリーン サブネットとも呼ばれます) には、インターネット関連のサービスを提供するサーバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7bbab-112">This perimeter network (also known as DMZ, demilitarized zone, and screened subnet) contains servers that provide Internet-related services.</span></span> <span data-ttu-id="7bbab-113">このドメインには、BizTalk Server、BizTalk 受信場所、エンタープライズ シングル サインオン サーバーはありません。</span><span class="sxs-lookup"><span data-stu-id="7bbab-113">There are no BizTalk Servers, BizTalk receive locations, or Enterprise Single Sign-On servers in this domain.</span></span>  
  
## <a name="perimeter-networkintranet"></a><span data-ttu-id="7bbab-114">境界ネットワーク-イントラネット</span><span class="sxs-lookup"><span data-stu-id="7bbab-114">Perimeter network―intranet</span></span>  
 <span data-ttu-id="7bbab-115">この境界ネットワークには、イントラネット関連のサービスを提供するサーバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7bbab-115">This perimeter network contains servers that provide intranet-related services.</span></span> <span data-ttu-id="7bbab-116">イントラネット (企業ネットワークなど) と、アプリケーションを実行しているサーバーの間のセキュリティの追加レイヤーを提供します。</span><span class="sxs-lookup"><span data-stu-id="7bbab-116">It provides an additional layer of security between your intranet (for example, a corporate network) and the servers that run the application.</span></span> <span data-ttu-id="7bbab-117">インターネットの境界ネットワークのように、イントラネット境界ネットワークに BizTalk Server が含まれていない、BizTalk 受信場所、エンタープライズ シングル サインオン サーバーです。</span><span class="sxs-lookup"><span data-stu-id="7bbab-117">Like the Internet perimeter network, the intranet perimeter network does not contain BizTalk Servers, BizTalk receive locations, or Enterprise Single Sign-On servers.</span></span>  
  
## <a name="e-business-domain"></a><span data-ttu-id="7bbab-118">E ビジネス ドメイン</span><span class="sxs-lookup"><span data-stu-id="7bbab-118">E-Business Domain</span></span>  
 <span data-ttu-id="7bbab-119">このドメインには、すべてのインフラストラクチャと、BizTalk Server の実装で使用するアプリケーションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7bbab-119">This domain contains all the infrastructure and applications used by your BizTalk Server implementation.</span></span> <span data-ttu-id="7bbab-120">このドメイン内のサーバーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7bbab-120">The servers in this domain are:</span></span>  
  
-   <span data-ttu-id="7bbab-121">**BizTalk Server です。**</span><span class="sxs-lookup"><span data-stu-id="7bbab-121">**BizTalk Server.**</span></span> <span data-ttu-id="7bbab-122">このサーバーには、BizTalk Server ランタイムとさまざまな BizTalk ホストのインスタンスのインストール。</span><span class="sxs-lookup"><span data-stu-id="7bbab-122">This server has an installation of the BizTalk Server runtime and instances of various BizTalk Hosts.</span></span> <span data-ttu-id="7bbab-123">環境で BizTalk Server の数は、実行しているホストとパフォーマンスのニーズの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="7bbab-123">The number of BizTalk Servers in the environment depends on the type of hosts they run and the performance needs.</span></span> <span data-ttu-id="7bbab-124">パフォーマンス ニーズの増加に応じて、処理ホストのホスト インスタンスの環境に BizTalk Server を追加できます。</span><span class="sxs-lookup"><span data-stu-id="7bbab-124">As your performance needs increase, you can add more BizTalk Servers to your environment for host instances of your processing hosts.</span></span>  
  
-   <span data-ttu-id="7bbab-125">**マスター シークレット サーバーです。**</span><span class="sxs-lookup"><span data-stu-id="7bbab-125">**Master secret server.**</span></span> <span data-ttu-id="7bbab-126">このサーバーは、エンタープライズ シングル サインオン (SSO) マスター シークレット サーバーです。</span><span class="sxs-lookup"><span data-stu-id="7bbab-126">This server is the Enterprise Single Sign-On (SSO) master secret server.</span></span> <span data-ttu-id="7bbab-127">SSO システムが SSO データベース内のデータの暗号化に使用するマスター シークレット (暗号化キー) を保持します。</span><span class="sxs-lookup"><span data-stu-id="7bbab-127">It holds the master secret (encryption key) that the SSO system uses to encrypt the data in the SSO database.</span></span>  
  
-   <span data-ttu-id="7bbab-128">**SQL Server。**</span><span class="sxs-lookup"><span data-stu-id="7bbab-128">**SQL Server.**</span></span> <span data-ttu-id="7bbab-129">このサーバーには、BizTalk データベースが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7bbab-129">This server contains the BizTalk databases.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="7bbab-130">フェールオーバー保護の場合は、各 BizTalk データベースをクラスター化することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7bbab-130">For failover protection, we recommend that you cluster each BizTalk database.</span></span> <span data-ttu-id="7bbab-131">Microsoft SQL Server フェールオーバー クラスタ リングの詳細については、Microsoft MSDN Web サイトを参照してください。 [ http://go.microsoft.com/fwlink/?LinkID=190216](http://go.microsoft.com/fwlink/?LinkID=190216)します。</span><span class="sxs-lookup"><span data-stu-id="7bbab-131">For more information about Microsoft SQL Server failover clustering, see the Microsoft MSDN Web site at [http://go.microsoft.com/fwlink/?LinkID=190216](http://go.microsoft.com/fwlink/?LinkID=190216).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7bbab-132">パフォーマンスのニーズに応じて、BizTalk データベースを SQL Server を実行する複数のコンピューターに分割する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7bbab-132">Depending on your performance needs, you might have to separate the BizTalk databases into multiple computers that run SQL Server.</span></span>  
  
-   <span data-ttu-id="7bbab-133">**ドメイン コント ローラー。**</span><span class="sxs-lookup"><span data-stu-id="7bbab-133">**Domain controller.**</span></span> <span data-ttu-id="7bbab-134">このサーバーは、E ビジネス Active Directory ドメインをホストします。</span><span class="sxs-lookup"><span data-stu-id="7bbab-134">This server hosts the E-Business Active Directory domain.</span></span> <span data-ttu-id="7bbab-135">すべてのグループと BizTalk Server へのアクセスを必要とする個々 のアカウントに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7bbab-135">It contains information about all the groups and individual accounts that need access to BizTalk Server.</span></span>  
  
-   <span data-ttu-id="7bbab-136">**管理ツールです。**</span><span class="sxs-lookup"><span data-stu-id="7bbab-136">**Administration tools.**</span></span> <span data-ttu-id="7bbab-137">このドメイン内のサーバーの 1 つは、管理ツールをホストします。BizTalk 管理コンソールおよびエンタープライズ シングル サインオン (SSO) 管理ユーティリティです。</span><span class="sxs-lookup"><span data-stu-id="7bbab-137">One of the servers in this domain hosts the administration tools: BizTalk Administration console and Enterprise Single Sign-On (SSO) administration utility.</span></span>  
  
## <a name="firewalls-and-domains"></a><span data-ttu-id="7bbab-138">ファイアウォールとドメイン</span><span class="sxs-lookup"><span data-stu-id="7bbab-138">Firewalls and Domains</span></span>  
 <span data-ttu-id="7bbab-139">図 1 では、Forefront Threat Management Gateway (TMG) 2010 サーバーが保護し、これらの各ドメインを含めることがソフトウェア ファイアウォールとして機能します。</span><span class="sxs-lookup"><span data-stu-id="7bbab-139">In Figure 1, Forefront Threat Management Gateway (TMG) 2010 server acts as a software firewall to help protect and contain each of these domains.</span></span> <span data-ttu-id="7bbab-140">さらに、E ビジネス ドメインが独自のドメイン コント ローラーと、このドメインは、他のドメインを信頼しません。</span><span class="sxs-lookup"><span data-stu-id="7bbab-140">Additionally, the E-Business domain has its own domain controller, and this domain does not trust any other domain.</span></span> <span data-ttu-id="7bbab-141">ドメインと信頼関係のファイアウォールを構成する方法の詳細については、Microsoft ヘルプとサポート Web サイトを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=25230](http://go.microsoft.com/fwlink/?LinkId=25230)します。</span><span class="sxs-lookup"><span data-stu-id="7bbab-141">For more information about how to configure a firewall for domains and trusts, see the Microsoft Help and Support Web site at [http://go.microsoft.com/fwlink/?LinkId=25230](http://go.microsoft.com/fwlink/?LinkId=25230).</span></span>  
  
 <span data-ttu-id="7bbab-142">サンプル アーキテクチャには、2 つのファイアウォールがあります。</span><span class="sxs-lookup"><span data-stu-id="7bbab-142">The sample architecture has two firewalls:</span></span>  
  
- <span data-ttu-id="7bbab-143">**ファイアウォール 1。**</span><span class="sxs-lookup"><span data-stu-id="7bbab-143">**Firewall 1.**</span></span> <span data-ttu-id="7bbab-144">このファイアウォールには、次の 3 つのネットワーク インターフェイスがあります。インターネット、イントラネット、および境界ネットワークからのトラフィックをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="7bbab-144">This firewall has three network interfaces: It routes traffic from the Internet, the intranet, and the perimeter networks.</span></span>  
  
- <span data-ttu-id="7bbab-145">**ファイアウォール 2。**</span><span class="sxs-lookup"><span data-stu-id="7bbab-145">**Firewall 2.**</span></span> <span data-ttu-id="7bbab-146">このファイアウォールは、デュアル ホームです。境界ネットワーク (インターネットとイントラネットの両方) および E ビジネス ドメインからのトラフィックをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="7bbab-146">This firewall is dual-homed: It routes traffic from the perimeter networks (both Internet and intranet) and the E-Business domain.</span></span>  
  
  <span data-ttu-id="7bbab-147">境界ネットワーク内のコンピューターは、任意のドメインのメンバーではないと、相互通信しません。</span><span class="sxs-lookup"><span data-stu-id="7bbab-147">The computers in the perimeter networks are not members of any domain, and they do not communicate with each other.</span></span>  
  
## <a name="ipsec"></a><span data-ttu-id="7bbab-148">IPsec (IPsec)</span><span class="sxs-lookup"><span data-stu-id="7bbab-148">IPsec</span></span>  
 <span data-ttu-id="7bbab-149">E ビジネス ドメイン内のすべてのサーバー間の通信を保護するためには、インターネット プロトコル セキュリティ (IPSec) を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7bbab-149">We recommend that you use Internet Protocol security (IPSec) to help secure the communication between all the servers in the E-Business domain.</span></span> <span data-ttu-id="7bbab-150">IPsec 規則は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7bbab-150">The IPsec rules are as follows:</span></span>  
  
- <span data-ttu-id="7bbab-151">BizTalk Server とドメイン コント ローラー間の認証されたトラフィックを許可します。</span><span class="sxs-lookup"><span data-stu-id="7bbab-151">Allow authenticated traffic between BizTalk Server and the domain controller.</span></span>  
  
- <span data-ttu-id="7bbab-152">BizTalk Server と管理ツール サーバー間の認証されたトラフィックを許可します。</span><span class="sxs-lookup"><span data-stu-id="7bbab-152">Allow authenticated traffic between BizTalk Server and the administration tools server.</span></span>  
  
- <span data-ttu-id="7bbab-153">BizTalk Server とマスター シークレット サーバー間の認証されたトラフィックを許可します。</span><span class="sxs-lookup"><span data-stu-id="7bbab-153">Allow authenticated traffic between BizTalk Server and the master secret server.</span></span>  
  
- <span data-ttu-id="7bbab-154">BizTalk Server と SQL Server 間の認証されたトラフィックを許可します。</span><span class="sxs-lookup"><span data-stu-id="7bbab-154">Allow authenticated traffic between BizTalk Server and the SQL Server.</span></span>  
  
- <span data-ttu-id="7bbab-155">マスター シークレット サーバーとドメイン コント ローラーの間の認証されたトラフィックを許可します。</span><span class="sxs-lookup"><span data-stu-id="7bbab-155">Allow authenticated traffic between the master secret server and the domain controller.</span></span>  
  
- <span data-ttu-id="7bbab-156">マスター シークレット サーバーと BizTalk Server (分離、処理、インプロセスで追跡ホストします。) の間の認証されたトラフィックを許可します。</span><span class="sxs-lookup"><span data-stu-id="7bbab-156">Allow authenticated traffic between the master secret server and the BizTalk Server (isolated, processing, in-process, and tracking hosts.)</span></span>  
  
- <span data-ttu-id="7bbab-157">マスター シークレット サーバーと SQL Server (SSO データベース) の間の認証されたトラフィックを許可します。</span><span class="sxs-lookup"><span data-stu-id="7bbab-157">Allow authenticated traffic between the master secret server and the SQL Server (SSO databases).</span></span>  
  
- <span data-ttu-id="7bbab-158">ドメイン コント ローラーとドメイン内のすべてのサーバー間の認証されたトラフィックを許可します。</span><span class="sxs-lookup"><span data-stu-id="7bbab-158">Allow authenticated traffic between the domain controller and all the servers in the domain.</span></span>  
  
- <span data-ttu-id="7bbab-159">管理ツール サーバーとドメイン内のすべてのサーバー間の認証されたトラフィックを許可します。</span><span class="sxs-lookup"><span data-stu-id="7bbab-159">Allow authenticated traffic between the administration tools server and all the servers in the domain.</span></span>  
  
  <span data-ttu-id="7bbab-160">他のアプリケーション ドメインでそれらのアプリケーションと適切なサーバー間での BizTalk Server、SQL Server、マスター シークレット サーバー、または管理ツールのサーバーのブロック トラフィックへのアクセスを必要としない場合は。</span><span class="sxs-lookup"><span data-stu-id="7bbab-160">If you have other applications in the domain that do not need access to the BizTalk Server, SQL Server, master secret server, or administration tools server, block traffic between those applications and the appropriate servers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bbab-161">参照</span><span class="sxs-lookup"><span data-stu-id="7bbab-161">See Also</span></span>  
 <span data-ttu-id="7bbab-162">[セキュリティの計画](../core/planning-for-security.md) </span><span class="sxs-lookup"><span data-stu-id="7bbab-162">[Planning for Security](../core/planning-for-security.md) </span></span>  
 <span data-ttu-id="7bbab-163">[中小規模の企業向けのサンプル アーキテクチャ](../core/sample-architectures-for-small-medium-sized-companies.md) </span><span class="sxs-lookup"><span data-stu-id="7bbab-163">[Sample Architectures for Small & Medium-Sized Companies](../core/sample-architectures-for-small-medium-sized-companies.md) </span></span>  
 [<span data-ttu-id="7bbab-164">脅威モデル分析のサンプル シナリオ</span><span class="sxs-lookup"><span data-stu-id="7bbab-164">Sample Scenarios for Threat Model Analysis</span></span>](../core/sample-scenarios-for-threat-model-analysis.md)