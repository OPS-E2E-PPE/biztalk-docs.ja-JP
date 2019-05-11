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
ms.openlocfilehash: dad0587f02d0307140e5208043eb16735bb6f03e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354169"
---
# <a name="creating-a-highly-available-biztalk-server-environment"></a><span data-ttu-id="2dcc0-102">高可用性 BizTalk Server 環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="2dcc0-102">Creating a Highly Available BizTalk Server Environment</span></span>
<span data-ttu-id="2dcc0-103">このセクションは、Microsoft での通信とデータの高可用性を提供する方法を説明します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]異種システムとアプリケーションを統合するときにします。</span><span class="sxs-lookup"><span data-stu-id="2dcc0-103">This section describes how to provide high availability for the data and communications in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] when integrating disparate systems and applications.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="2dcc0-104">可用性データベースをスケールすることによって発行およびホストを別々 に解決できるように、データを処理するホストが分離されます。</span><span class="sxs-lookup"><span data-stu-id="2dcc0-104">separates the data from the hosts that process the data, enabling you to resolve availability issues by scaling the databases and hosts independently.</span></span>  
  
## <a name="demonstrating-high-availability"></a><span data-ttu-id="2dcc0-105">高可用性の実証</span><span class="sxs-lookup"><span data-stu-id="2dcc0-105">Demonstrating High Availability</span></span>  
 <span data-ttu-id="2dcc0-106">高可用性を[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可用性を低下させている機能コンポーネントの復旧にかかっています、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]展開します。</span><span class="sxs-lookup"><span data-stu-id="2dcc0-106">High availability for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] focuses on recovering functional components that might disrupt availability in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment.</span></span>  
  
 <span data-ttu-id="2dcc0-107">高可用性をデモンストレーションする[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]障害を適用し、復旧で、製品の効果を測定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2dcc0-107">To demonstrate high availability in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you have to apply failure and measure the product's effectiveness in recovery.</span></span> <span data-ttu-id="2dcc0-108">高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]展開は、外部アプリケーションとシステムに、エラーや障害を透明と最小限の中断で正しく機能しているすべてのサービスを続行するようにします。</span><span class="sxs-lookup"><span data-stu-id="2dcc0-108">A highly available [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment makes errors and failures transparent to external applications and systems, and makes sure that all services continue functioning correctly with minimal disruption.</span></span>  
  
## <a name="designing-for-high-availability"></a><span data-ttu-id="2dcc0-109">高可用性のための設計</span><span class="sxs-lookup"><span data-stu-id="2dcc0-109">Designing for High Availability</span></span>  
 <span data-ttu-id="2dcc0-110">設計、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]高可用性を提供する展開では、アプリケーションの統合またはビジネス プロセス統合シナリオに関連する各機能コンポーネントの冗長性を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2dcc0-110">Designing a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment that provides high availability involves implementing redundancy for each functional component involved in an application integration or business process integration scenario.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="2dcc0-111">概念的には、データを処理するホストからデータを分離することでは、これらのシナリオの実装を簡素化されます。</span><span class="sxs-lookup"><span data-stu-id="2dcc0-111">simplifies the implementation of these scenarios by conceptually separating the data from the hosts that process the data.</span></span> <span data-ttu-id="2dcc0-112">高可用性を実現する手段[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は、複数のホスト インスタンスを実行し、クラスタ リング、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="2dcc0-112">So providing high availability for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] involves running multiple host instances and clustering the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, as follows:</span></span>  
  
- <span data-ttu-id="2dcc0-113">**BizTalk ホストのアーキテクチャ**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホストを分離し、メッセージの受信、処理オーケストレーション、メッセージを送信するなどの主要機能の高可用性を実現する複数のホスト インスタンスを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="2dcc0-113">**Architecture for BizTalk Hosts** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] lets you separate hosts and run multiple host instances to provide high availability for key functions such as receiving messages, processing orchestrations, and sending messages.</span></span> <span data-ttu-id="2dcc0-114">これらのホストので必要ありません、クラスタ リングを追加または負荷分散メカニズム[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ワークロードを複数のコンピューターのホスト インスタンスを自動的に分散します。</span><span class="sxs-lookup"><span data-stu-id="2dcc0-114">These hosts do not require any additional clustering or load-balancing mechanism because [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] automatically distributes workload across multiple computers through host instances.</span></span> <span data-ttu-id="2dcc0-115">ただし、HTTP および SOAP アダプターの受信ハンドラーを実行しているホストには、負荷分散メカニズムなどネットワーク負荷分散 (NLB) の高可用性を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2dcc0-115">However, hosts running the receive handler for the HTTP and SOAP adapters require a load-balancing mechanism such as Network Load Balancing (NLB) to provide high availability.</span></span>  
  
- <span data-ttu-id="2dcc0-116">**BizTalk Server データベースのアーキテクチャ**の高可用性、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースは通常、アクティブ/パッシブのサーバー クラスター構成で構成されている 2 つ以上のデータベース コンピューターで構成されます。</span><span class="sxs-lookup"><span data-stu-id="2dcc0-116">**Architecture for BizTalk Server databases** High availability for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases typically consists of two or more database computers configured in an active/passive server cluster configuration.</span></span> <span data-ttu-id="2dcc0-117">これらのコンピューターでは、共通のディスク リソース (RAID5 SCSI ディスク アレイやストレージ エリア ネットワークなど) を共有し、Windows クラスタ リングを使用して、バックアップの冗長性とフォールト トレランスを提供します。</span><span class="sxs-lookup"><span data-stu-id="2dcc0-117">These computers share a common disk resource (such as a RAID5 SCSI disk array or storage area network) and use Windows Clustering to provide backup redundancy and fault tolerance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2dcc0-118">高可用性環境は、性質上、複数コンピューター環境です。</span><span class="sxs-lookup"><span data-stu-id="2dcc0-118">Highly-available environments are, by nature, multi-computer environments.</span></span> <span data-ttu-id="2dcc0-119">構成するときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]複数コンピューター環境では、ドメイン ユーザー グループとアカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2dcc0-119">When configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a multi-computer environment you must use domain user groups and accounts.</span></span>  
  
 <span data-ttu-id="2dcc0-120">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]基に構築されて[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]または[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]と用のホストを構成する前に、高可用性を備えた、これらの製品をデプロイすることを確認、Microsoft SQL Server 2008[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="2dcc0-120">Because [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is built on Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)], and Microsoft SQL Server 2008, make sure that you deploy these products with high availability before configuring hosts for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="2dcc0-121">次のリンクには、これらの基になる製品用の高可用性を実現するに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2dcc0-121">The following links include information about providing high availability for these underlying products:</span></span>  
  
- <span data-ttu-id="2dcc0-122">**高可用性 – Always On Technologies**、 [ http://go.microsoft.com/fwlink/?LinkId=130376](http://go.microsoft.com/fwlink/?LinkId=130376)します。</span><span class="sxs-lookup"><span data-stu-id="2dcc0-122">**High Availability – Always On Technologies**, available at [http://go.microsoft.com/fwlink/?LinkId=130376](http://go.microsoft.com/fwlink/?LinkId=130376).</span></span>  
  
   <span data-ttu-id="2dcc0-123">このホワイト ペーパーでは、SQL Server 2008 で利用できる高可用性機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="2dcc0-123">This whitepaper describes high availability features that are available with SQL Server 2008.</span></span>  
  
- <span data-ttu-id="2dcc0-124">**高可用性ソリューションの概要**、 [ http://go.microsoft.com/fwlink/?LinkId=130377](http://go.microsoft.com/fwlink/?LinkId=130377)します。</span><span class="sxs-lookup"><span data-stu-id="2dcc0-124">**High Availability Solutions Overview**, available at [http://go.microsoft.com/fwlink/?LinkId=130377](http://go.microsoft.com/fwlink/?LinkId=130377).</span></span>  
  
   <span data-ttu-id="2dcc0-125">SQL Server 2008 のサーバーやデータベースの可用性を向上するにはいくつかの高可用性ソリューションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2dcc0-125">Introduces several high-availability solutions for SQL Server 2008 that improve the availability of servers or databases.</span></span>  
  
- <span data-ttu-id="2dcc0-126">**Windows 展開サービス ステップ バイ ステップ ガイド**、 [ http://go.microsoft.com/fwlink/?LinkId=130379](http://go.microsoft.com/fwlink/?LinkId=130379)します。</span><span class="sxs-lookup"><span data-stu-id="2dcc0-126">**Windows Deployment Services Step-by-Step Guide**, available at [http://go.microsoft.com/fwlink/?LinkId=130379](http://go.microsoft.com/fwlink/?LinkId=130379).</span></span>  
  
   <span data-ttu-id="2dcc0-127">Windows Server 2008、Windows 展開サービス ロールを使用する方法についてステップ バイ ステップ ガイダンスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2dcc0-127">Contains step-by-step guidance for how to use the Windows Deployment Services role in Windows Server 2008.</span></span>  
  
- <span data-ttu-id="2dcc0-128">**Windows Server 2003 展開キット:サーバーの導入計画**、 [ http://go.microsoft.com/fwlink/?LinkId=24433](http://go.microsoft.com/fwlink/?LinkId=24433)します。</span><span class="sxs-lookup"><span data-stu-id="2dcc0-128">**Windows Server 2003 Deployment Kit: Planning Server Deployments**, available at [http://go.microsoft.com/fwlink/?LinkId=24433](http://go.microsoft.com/fwlink/?LinkId=24433).</span></span>  
  
   <span data-ttu-id="2dcc0-129">このドキュメントでは、サーバーの記憶域、および情報を設計し、ファイル サーバー、プリント サーバー、および中規模および大規模組織内のターミナル サーバーの配置に関する計画に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="2dcc0-129">This book provides information about planning server storage, and information about designing and deploying file servers, print servers, and terminal servers in medium and large organizations.</span></span>  
  
- <span data-ttu-id="2dcc0-130">**BizTalk Server の可用性を高める**、 [ http://go.microsoft.com/fwlink/?LinkId=130457](http://go.microsoft.com/fwlink/?LinkId=130457)します。</span><span class="sxs-lookup"><span data-stu-id="2dcc0-130">**Increasing Availability for BizTalk Server**, available at [http://go.microsoft.com/fwlink/?LinkId=130457](http://go.microsoft.com/fwlink/?LinkId=130457).</span></span>  
  
   <span data-ttu-id="2dcc0-131">セクション、 [BizTalk Server 運用ガイド](http://go.microsoft.com/fwlink/?LinkId=130458)の可用性を向上させる方法について説明する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システム。</span><span class="sxs-lookup"><span data-stu-id="2dcc0-131">Section of the [BizTalk Server Operations Guide](http://go.microsoft.com/fwlink/?LinkId=130458) that describes ways you can increase the availability of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2dcc0-132">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2dcc0-132">In This Section</span></span>  
  
-   [<span data-ttu-id="2dcc0-133">BizTalk ホストの高可用性を実現します。</span><span class="sxs-lookup"><span data-stu-id="2dcc0-133">Providing High Availability for BizTalk Hosts</span></span>](../core/providing-high-availability-for-biztalk-hosts.md)  
  
-   [<span data-ttu-id="2dcc0-134">BizTalk Server データベースの高可用性を実現します。</span><span class="sxs-lookup"><span data-stu-id="2dcc0-134">Providing High Availability for BizTalk Server Databases</span></span>](../core/providing-high-availability-for-biztalk-server-databases.md)  
  
## <a name="see-also"></a><span data-ttu-id="2dcc0-135">参照</span><span class="sxs-lookup"><span data-stu-id="2dcc0-135">See Also</span></span>  
 <span data-ttu-id="2dcc0-136">[サンプル BizTalk Server の高可用性のシナリオ](../core/sample-biztalk-server-high-availability-scenarios.md) </span><span class="sxs-lookup"><span data-stu-id="2dcc0-136">[Sample BizTalk Server High Availability Scenarios](../core/sample-biztalk-server-high-availability-scenarios.md) </span></span>  
 [<span data-ttu-id="2dcc0-137">Windows Server クラスターを使用して BizTalk Server Hosts2 の高可用性を実現するには</span><span class="sxs-lookup"><span data-stu-id="2dcc0-137">Using Windows Server Cluster to Provide High Availability for BizTalk Server Hosts2</span></span>](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)