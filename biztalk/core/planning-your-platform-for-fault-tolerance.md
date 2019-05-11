---
title: プラットフォームのフォールト トレランスの計画 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, BizTalk Server
- MessageBox database, fault tolerance
- clustering, fault tolerance
- SQL Server RAID
- databases [BAM], fault tolerance
- BizTalk Server, planning
- fault tolerance
- clustering, fail-overs
- planning, fault tolerance
- Primary Import database [BAM]
- BizTalk Server, backing up
- fault tolerance, planning
- planning, BizTalk Server
- Primary Import database [BAM], fault tolerance
- fail-over clustering
ms.assetid: 512ed6b8-db1e-434a-8009-63e952cf5500
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3564be0d8e49d64b3726f7aca360bfa4042343db
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394966"
---
# <a name="planning-your-platform-for-fault-tolerance"></a><span data-ttu-id="5f1ad-102">プラットフォームのフォールト トレランスの計画</span><span class="sxs-lookup"><span data-stu-id="5f1ad-102">Planning Your Platform for Fault Tolerance</span></span>
<span data-ttu-id="5f1ad-103">Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は、Microsoft Windows と Microsoft SQL Server プラットフォーム上に構築します。</span><span class="sxs-lookup"><span data-stu-id="5f1ad-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is built on the Microsoft Windows and Microsoft SQL Server platforms.</span></span> <span data-ttu-id="5f1ad-104">存続または障害から回復する BizTalk Server の機能は、存続または回復する基になるプラットフォームの機能に依存します。</span><span class="sxs-lookup"><span data-stu-id="5f1ad-104">The ability of BizTalk Server to survive or recover from a disaster depends on the ability of the underlying platform to survive or recover.</span></span>  
  
 <span data-ttu-id="5f1ad-105">ビジネス アクティビティ監視 (BAM) データベースと、メッセージ ボックス データベースは、次を行うお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5f1ad-105">For your Business Activity Monitoring (BAM) databases and your MessageBox database, we recommend you do the following:</span></span>  
  
- <span data-ttu-id="5f1ad-106">SQL Server Enterprise Edition で提供されているフェールオーバー クラスタ リングを設定します。</span><span class="sxs-lookup"><span data-stu-id="5f1ad-106">Set up fail-over clustering, which is available in SQL Server Enterprise Edition.</span></span> <span data-ttu-id="5f1ad-107">フェールオーバー クラスタ リングでは、SQL Server が稼働中のサーバーに障害が発生したサーバーから SQL Server のインスタンスの処理を自動的に切り替えを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5f1ad-107">Fail-over clustering enables SQL Server to automatically switch the processing for an instance of SQL Server from a failed server to a working server.</span></span>  
  
   <span data-ttu-id="5f1ad-108">BAM プライマリ インポート データベースは、イベント データを収集します。</span><span class="sxs-lookup"><span data-stu-id="5f1ad-108">The BAM Primary Import database collects event data.</span></span> <span data-ttu-id="5f1ad-109">障害が発生した場合、前回のバックアップ以降に BAM プライマリ インポート データベースに書き込まれたデータが失われます。</span><span class="sxs-lookup"><span data-stu-id="5f1ad-109">In the event of a disaster, data that was written to the BAM Primary Import database since the last backup will be lost.</span></span> <span data-ttu-id="5f1ad-110">失われたイベントを再生成する方法はありません、ために、BAM プライマリ インポート データベースに対してフェールオーバー クラスタ リングの失敗を有効にすることは特に重要ですが。</span><span class="sxs-lookup"><span data-stu-id="5f1ad-110">Because there is no way to regenerate lost events, it is especially important that you enable fail over clustering on your BAM Primary Import database.</span></span>  
  
- <span data-ttu-id="5f1ad-111">特に、メッセージ ボックス データベースおよび BAM プライマリ インポート データベースの SQL Server RAID (冗長アレイの独立したディスク) を使用します。</span><span class="sxs-lookup"><span data-stu-id="5f1ad-111">Use SQL Server RAID (redundant array of independent disks), especially for the MessageBox database and the BAM Primary Import database.</span></span>  
  
  <span data-ttu-id="5f1ad-112">次のリソースを使用すると、フォールト トレランスのため、Windows および SQL Server の展開をデザインできます。</span><span class="sxs-lookup"><span data-stu-id="5f1ad-112">Use the following resources to design your Windows and SQL Server deployments for fault tolerance.</span></span> <span data-ttu-id="5f1ad-113">サービスの障害およびデータの損失を防ぐためにクラスタ リングやディスクがミラー化など、ハードウェアとサーバーの冗長性技術詳細については時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="5f1ad-113">Take time to learn about hardware and server redundancy technologies, such as clustering and disk mirroring, to prevent service outages and data loss.</span></span>  
  
- [<span data-ttu-id="5f1ad-114">ホワイト ペーパー:高可用性-常時接続テクノロジ</span><span class="sxs-lookup"><span data-stu-id="5f1ad-114">White Paper: High Availability—Always On Technologies</span></span>](http://go.microsoft.com/fwlink/?LinkId=130376)  
  
   <span data-ttu-id="5f1ad-115">"高可用性 – Always On Technologies"ホワイト ペーパーでは、SQL Server 2008 で利用できる高可用性機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="5f1ad-115">The “High Availability – Always On Technologies” whitepaper describes high availability features that are available with SQL Server 2008.</span></span>  
  
- [<span data-ttu-id="5f1ad-116">高可用性ソリューションの概要</span><span class="sxs-lookup"><span data-stu-id="5f1ad-116">High Availability Solutions Overview</span></span>](http://go.microsoft.com/fwlink/?LinkId=130377)  
  
   <span data-ttu-id="5f1ad-117">SQL Server 2008 のサーバーやデータベースの可用性を向上するにはいくつかの高可用性ソリューションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5f1ad-117">Introduces several high-availability solutions for SQL Server 2008 that improve the availability of servers or databases.</span></span>  
  
- [<span data-ttu-id="5f1ad-118">第 15 章「高可用性オプションでは、SQL Server リソース キット</span><span class="sxs-lookup"><span data-stu-id="5f1ad-118">Chapter 15 - High Availability Options, SQL Server Resource Kit</span></span>](http://go.microsoft.com/fwlink/?LinkId=24431)  
  
   <span data-ttu-id="5f1ad-119">Microsoft SQL Server リソース キットには、さまざまな管理や配置計画について説明します。</span><span class="sxs-lookup"><span data-stu-id="5f1ad-119">The Microsoft SQL Server Resource Kit covers a wide range of administrative and deployment planning areas.</span></span> <span data-ttu-id="5f1ad-120">第 15 章では、フォールト トレランスおよび復旧の計画について説明します。</span><span class="sxs-lookup"><span data-stu-id="5f1ad-120">Chapter 15 covers planning for fault tolerance and recovery.</span></span>  
  
- [<span data-ttu-id="5f1ad-121">Windows Deployment Services Step-by-Step Guide</span><span class="sxs-lookup"><span data-stu-id="5f1ad-121">Windows Deployment Services Step-by-Step Guide</span></span>](http://go.microsoft.com/fwlink/?LinkId=130379)  
  
   <span data-ttu-id="5f1ad-122">Windows Server 2008、Windows 展開サービス ロールを使用する方法についてステップ バイ ステップ ガイダンスが含まれています</span><span class="sxs-lookup"><span data-stu-id="5f1ad-122">Contains step-by-step guidance for how to use the Windows Deployment Services role in Windows Server 2008</span></span>  
  
- <span data-ttu-id="5f1ad-123">[Windows Server 2003 展開キット:サーバーの導入計画](http://go.microsoft.com/fwlink/?LinkId=24433)します。</span><span class="sxs-lookup"><span data-stu-id="5f1ad-123">[Windows Server 2003 Deployment Kit: Planning Server Deployments](http://go.microsoft.com/fwlink/?LinkId=24433).</span></span>  
  
   <span data-ttu-id="5f1ad-124">このドキュメントでは、サーバーの記憶域、および情報を設計し、ファイル サーバー、プリント サーバー、および中規模および大規模組織内のターミナル サーバーの配置に関する計画に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="5f1ad-124">This book provides information about planning server storage, and information about designing and deploying file servers, print servers, and terminal servers in medium and large organizations.</span></span>  
  
   <span data-ttu-id="5f1ad-125">この本でリモート サーバー管理の計画、設計しサーバーのクラスターを展開してデザインおよびネットワーク負荷分散クラスターをデプロイして、サーバーのスケーラビリティと可用性を最大化するのにガイドラインを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="5f1ad-125">You can also use the guidelines in this book to maximize the availability and scalability of your servers by planning for remote server management, designing and deploying server clusters, and designing and deploying Network Load Balancing clusters.</span></span>  
  
## <a name="backing-up-your-platform"></a><span data-ttu-id="5f1ad-126">プラットフォームのバックアップ</span><span class="sxs-lookup"><span data-stu-id="5f1ad-126">Backing Up Your Platform</span></span>  
 <span data-ttu-id="5f1ad-127">システムを構成した後は、データの損失が発生した場合、同一のサーバーを迅速に復元できるように、サーバーの完全バックアップを準備します。</span><span class="sxs-lookup"><span data-stu-id="5f1ad-127">After you have configured your system, prepare full backups of your servers so you can quickly restore an identical server in the event of data loss.</span></span>  
  
 <span data-ttu-id="5f1ad-128">お使いのプラットフォームをバックアップするため、次のテクノロジのそれぞれの文書化されたバックアップの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5f1ad-128">To back up your platform, perform the documented backup procedures for each of the following technologies:</span></span>  
  
- <span data-ttu-id="5f1ad-129">Microsoft Windows Server Standard、Enterprise、または Datacenter Edition</span><span class="sxs-lookup"><span data-stu-id="5f1ad-129">Microsoft Windows Server Standard, Enterprise, or Datacenter Edition</span></span>  
  
- <span data-ttu-id="5f1ad-130">インターネット インフォメーション サービス (IIS)</span><span class="sxs-lookup"><span data-stu-id="5f1ad-130">Internet Information Services (IIS)</span></span>  
  
- <span data-ttu-id="5f1ad-131">Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="5f1ad-131">Microsoft SQL Server</span></span>  
  
- <span data-ttu-id="5f1ad-132">Windows SharePoint Services、Windows SharePoint Services アダプターによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="5f1ad-132">Windows SharePoint Services, which is used by the Windows SharePoint Services adapter.</span></span>  
  
  <span data-ttu-id="5f1ad-133">「BizTalk Server 運用ガイド」で"BizTalk Server のバックアップ"での推奨事項に従って[チェックリスト。ディザスター リカバリーによる可用性の向上](http://go.microsoft.com/fwlink/?LinkId=130498)します。</span><span class="sxs-lookup"><span data-stu-id="5f1ad-133">Follow the recommendations in the “BizTalk Server Operations Guide” for “Backing up BizTalk Server” available at [Checklist: Increasing Availability with Disaster Recovery](http://go.microsoft.com/fwlink/?LinkId=130498).</span></span>  
  
  <span data-ttu-id="5f1ad-134">十分にテストしたら、バックアップと復元手順と、安全なリモートの場所に配置します。</span><span class="sxs-lookup"><span data-stu-id="5f1ad-134">Thoroughly test your backup and restore procedures, and put them in a safe, remote location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f1ad-135">参照</span><span class="sxs-lookup"><span data-stu-id="5f1ad-135">See Also</span></span>  
 [<span data-ttu-id="5f1ad-136">BizTalk Server データベースのバックアップと復元</span><span class="sxs-lookup"><span data-stu-id="5f1ad-136">Backing Up and Restoring the BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-the-biztalk-server-databases.md)