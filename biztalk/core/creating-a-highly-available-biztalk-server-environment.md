---
title: 高可用性 BizTalk Server 環境を作成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, high availability
- architecture, databases
- databases, architecture
- performance
- hosts, multiple
- hosts, architecture
- architecture, hosts
- databases, clustering
- high availability, designing
- BizTalk Server, architecture
- installation, planning
- clustering, databases
- installation, availability
ms.assetid: 758eb3bd-a25b-4863-a4ca-d7a1635f7542
caps.latest.revision: 54
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0db43b53e9229747172a203d3c7788997ecedbfb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981891"
---
# <a name="creating-a-highly-available-biztalk-server-environment"></a><span data-ttu-id="2f273-102">高可用性 BizTalk Server 環境の構築</span><span class="sxs-lookup"><span data-stu-id="2f273-102">Creating a Highly Available BizTalk Server Environment</span></span>
<span data-ttu-id="2f273-103">このセクションは、Microsoft での通信とデータの高可用性を提供する方法を説明します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]異種システムとアプリケーションを統合するときにします。</span><span class="sxs-lookup"><span data-stu-id="2f273-103">This section describes how to provide high availability for the data and communications in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] when integrating disparate systems and applications.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="2f273-104"> 可用性データベースをスケールすることによって発行およびホストを別々 に解決できるように、データを処理するホストが分離されます。</span><span class="sxs-lookup"><span data-stu-id="2f273-104"> separates the data from the hosts that process the data, enabling you to resolve availability issues by scaling the databases and hosts independently.</span></span>  
  
## <a name="demonstrating-high-availability"></a><span data-ttu-id="2f273-105">高可用性の実証</span><span class="sxs-lookup"><span data-stu-id="2f273-105">Demonstrating High Availability</span></span>  
 <span data-ttu-id="2f273-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の高可用性は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 展開の可用性を低下させている機能コンポーネントの復旧にかかっています。</span><span class="sxs-lookup"><span data-stu-id="2f273-106">High availability for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] focuses on recovering functional components that might disrupt availability in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment.</span></span>  
  
 <span data-ttu-id="2f273-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の高可用性を実証するには、障害を想定して製品の復旧能力を評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f273-107">To demonstrate high availability in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you have to apply failure and measure the product's effectiveness in recovery.</span></span> <span data-ttu-id="2f273-108">高い可用性を備えた [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境の条件は、そのエラーや障害が外部のアプリケーションやシステムに影響を与えることなく、混乱を最小限に抑えながら、すべてのサービスが正常な機能を維持できることです。</span><span class="sxs-lookup"><span data-stu-id="2f273-108">A highly available [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment makes errors and failures transparent to external applications and systems, and makes sure that all services continue functioning correctly with minimal disruption.</span></span>  
  
## <a name="designing-for-high-availability"></a><span data-ttu-id="2f273-109">高可用性を実現するための設計</span><span class="sxs-lookup"><span data-stu-id="2f273-109">Designing for High Availability</span></span>  
 <span data-ttu-id="2f273-110">設計、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]高可用性を提供する展開では、アプリケーションの統合またはビジネス プロセス統合シナリオに関連する各機能コンポーネントの冗長性を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f273-110">Designing a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment that provides high availability involves implementing redundancy for each functional component involved in an application integration or business process integration scenario.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="2f273-111"> 概念的には、データを処理するホストからデータを分離することでは、これらのシナリオの実装を簡素化されます。</span><span class="sxs-lookup"><span data-stu-id="2f273-111"> simplifies the implementation of these scenarios by conceptually separating the data from the hosts that process the data.</span></span> <span data-ttu-id="2f273-112">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の高可用性を実現する手段として、次のように、複数のホスト インスタンスの実行や、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースのクラスター化があります。</span><span class="sxs-lookup"><span data-stu-id="2f273-112">So providing high availability for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] involves running multiple host instances and clustering the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, as follows:</span></span>  
  
- <span data-ttu-id="2f273-113">**BizTalk ホストのアーキテクチャ**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホストを分離し、メッセージの受信、処理オーケストレーション、メッセージを送信するなどの主要機能の高可用性を実現する複数のホスト インスタンスを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="2f273-113">**Architecture for BizTalk Hosts** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] lets you separate hosts and run multiple host instances to provide high availability for key functions such as receiving messages, processing orchestrations, and sending messages.</span></span> <span data-ttu-id="2f273-114">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ではホスト インスタンスを通じて複数のコンピューターに自動的に負荷が分散されるため、これらのホストにクラスタリングを追加したり、負荷分散メカニズムを適用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2f273-114">These hosts do not require any additional clustering or load-balancing mechanism because [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] automatically distributes workload across multiple computers through host instances.</span></span> <span data-ttu-id="2f273-115">ただし、HTTP アダプターおよび SOAP アダプターの受信ハンドラーを実行するホストに高可用性を確保するためには、ネットワーク負荷分散 (NLB) などの負荷分散メカニズムが必要となります。</span><span class="sxs-lookup"><span data-stu-id="2f273-115">However, hosts running the receive handler for the HTTP and SOAP adapters require a load-balancing mechanism such as Network Load Balancing (NLB) to provide high availability.</span></span>  
  
- <span data-ttu-id="2f273-116">**BizTalk Server データベースのアーキテクチャ**の高可用性、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースは通常、アクティブ/パッシブのサーバー クラスター構成で構成されている 2 つ以上のデータベース コンピューターで構成されます。</span><span class="sxs-lookup"><span data-stu-id="2f273-116">**Architecture for BizTalk Server databases** High availability for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases typically consists of two or more database computers configured in an active/passive server cluster configuration.</span></span> <span data-ttu-id="2f273-117">複数のコンピューターが同じディスク リソース (RAID5 SCSI ディスク アレイやストレージ エリア ネットワークなど) を共有し、Windows クラスタリングを通じてバックアップの冗長性とフォールト トレランスを提供します。</span><span class="sxs-lookup"><span data-stu-id="2f273-117">These computers share a common disk resource (such as a RAID5 SCSI disk array or storage area network) and use Windows Clustering to provide backup redundancy and fault tolerance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2f273-118">高い可用性を備えた環境とは、本質的に複数のコンピューターから成る環境です。</span><span class="sxs-lookup"><span data-stu-id="2f273-118">Highly-available environments are, by nature, multi-computer environments.</span></span> <span data-ttu-id="2f273-119">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を複数コンピューター環境で構成する場合は、ドメイン ユーザー グループとアカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f273-119">When configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a multi-computer environment you must use domain user groups and accounts.</span></span>  
  
 <span data-ttu-id="2f273-120">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] または [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]、および Microsoft SQL Server 2008 を基盤としているので、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 用のホストを構成する前に、高可用性を実現しながらこれらの製品を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f273-120">Because [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is built on Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)], and Microsoft SQL Server 2008, make sure that you deploy these products with high availability before configuring hosts for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="2f273-121">こうした基盤となる製品の高可用性を実現する方法については、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f273-121">The following links include information about providing high availability for these underlying products:</span></span>  
  
- <span data-ttu-id="2f273-122">**高可用性 – Always On Technologies**、 [ http://go.microsoft.com/fwlink/?LinkId=130376](http://go.microsoft.com/fwlink/?LinkId=130376)します。</span><span class="sxs-lookup"><span data-stu-id="2f273-122">**High Availability – Always On Technologies**, available at [http://go.microsoft.com/fwlink/?LinkId=130376](http://go.microsoft.com/fwlink/?LinkId=130376).</span></span>  
  
   <span data-ttu-id="2f273-123">このホワイトペーパーでは、SQL Server 2008 で使用できる高可用性機能について説明しています。</span><span class="sxs-lookup"><span data-stu-id="2f273-123">This whitepaper describes high availability features that are available with SQL Server 2008.</span></span>  
  
- <span data-ttu-id="2f273-124">**高可用性ソリューションの概要**、 [ http://go.microsoft.com/fwlink/?LinkId=130377](http://go.microsoft.com/fwlink/?LinkId=130377)します。</span><span class="sxs-lookup"><span data-stu-id="2f273-124">**High Availability Solutions Overview**, available at [http://go.microsoft.com/fwlink/?LinkId=130377](http://go.microsoft.com/fwlink/?LinkId=130377).</span></span>  
  
   <span data-ttu-id="2f273-125">サーバーまたはデータベースの可用性を向上させる SQL Server 2008 の高可用性ソリューションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2f273-125">Introduces several high-availability solutions for SQL Server 2008 that improve the availability of servers or databases.</span></span>  
  
- <span data-ttu-id="2f273-126">**Windows 展開サービス ステップ バイ ステップ ガイド**、 [ http://go.microsoft.com/fwlink/?LinkId=130379](http://go.microsoft.com/fwlink/?LinkId=130379)します。</span><span class="sxs-lookup"><span data-stu-id="2f273-126">**Windows Deployment Services Step-by-Step Guide**, available at [http://go.microsoft.com/fwlink/?LinkId=130379](http://go.microsoft.com/fwlink/?LinkId=130379).</span></span>  
  
   <span data-ttu-id="2f273-127">Windows Server 2008 で Windows 展開サービス ロールを使用する方法についてのステップ バイ ステップ ガイドを含みます。</span><span class="sxs-lookup"><span data-stu-id="2f273-127">Contains step-by-step guidance for how to use the Windows Deployment Services role in Windows Server 2008.</span></span>  
  
- <span data-ttu-id="2f273-128">**Windows Server 2003 導入ガイド: サーバーの展開を計画する**、 [ http://go.microsoft.com/fwlink/?LinkId=24433](http://go.microsoft.com/fwlink/?LinkId=24433)します。</span><span class="sxs-lookup"><span data-stu-id="2f273-128">**Windows Server 2003 Deployment Kit: Planning Server Deployments**, available at [http://go.microsoft.com/fwlink/?LinkId=24433](http://go.microsoft.com/fwlink/?LinkId=24433).</span></span>  
  
   <span data-ttu-id="2f273-129">このドキュメントでは、サーバー ストレージの導入計画のほか、中規模から大規模な組織におけるファイル サーバー、プリント サーバー、およびターミナル サーバーの設計と導入について説明しています。</span><span class="sxs-lookup"><span data-stu-id="2f273-129">This book provides information about planning server storage, and information about designing and deploying file servers, print servers, and terminal servers in medium and large organizations.</span></span>  
  
- <span data-ttu-id="2f273-130">**BizTalk Server の可用性を高める**、 [ http://go.microsoft.com/fwlink/?LinkId=130457](http://go.microsoft.com/fwlink/?LinkId=130457)します。</span><span class="sxs-lookup"><span data-stu-id="2f273-130">**Increasing Availability for BizTalk Server**, available at [http://go.microsoft.com/fwlink/?LinkId=130457](http://go.microsoft.com/fwlink/?LinkId=130457).</span></span>  
  
   <span data-ttu-id="2f273-131">セクション、 [BizTalk Server 運用ガイド](http://go.microsoft.com/fwlink/?LinkId=130458)の可用性を向上させる方法について説明する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システム。</span><span class="sxs-lookup"><span data-stu-id="2f273-131">Section of the [BizTalk Server Operations Guide](http://go.microsoft.com/fwlink/?LinkId=130458) that describes ways you can increase the availability of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2f273-132">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2f273-132">In This Section</span></span>  
  
-   [<span data-ttu-id="2f273-133">BizTalk ホストの高可用性</span><span class="sxs-lookup"><span data-stu-id="2f273-133">Providing High Availability for BizTalk Hosts</span></span>](../core/providing-high-availability-for-biztalk-hosts.md)  
  
-   [<span data-ttu-id="2f273-134">BizTalk Server データベースの高可用性を実現します。</span><span class="sxs-lookup"><span data-stu-id="2f273-134">Providing High Availability for BizTalk Server Databases</span></span>](../core/providing-high-availability-for-biztalk-server-databases.md)  
  
## <a name="see-also"></a><span data-ttu-id="2f273-135">参照</span><span class="sxs-lookup"><span data-stu-id="2f273-135">See Also</span></span>  
 <span data-ttu-id="2f273-136">[サンプル BizTalk Server の高可用性のシナリオ](../core/sample-biztalk-server-high-availability-scenarios.md) </span><span class="sxs-lookup"><span data-stu-id="2f273-136">[Sample BizTalk Server High Availability Scenarios](../core/sample-biztalk-server-high-availability-scenarios.md) </span></span>  
 [<span data-ttu-id="2f273-137">Windows Server クラスターを使用して BizTalk Server Hosts2 の高可用性を実現するには</span><span class="sxs-lookup"><span data-stu-id="2f273-137">Using Windows Server Cluster to Provide High Availability for BizTalk Server Hosts2</span></span>](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)