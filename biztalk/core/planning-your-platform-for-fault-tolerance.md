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
ms.openlocfilehash: a5ddc4565449171c71685bcddd2c68b699f5113b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007491"
---
# <a name="planning-your-platform-for-fault-tolerance"></a><span data-ttu-id="3da56-102">プラットフォームのフォールト トレランスの計画</span><span class="sxs-lookup"><span data-stu-id="3da56-102">Planning Your Platform for Fault Tolerance</span></span>
<span data-ttu-id="3da56-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、Microsoft Windows プラットフォームおよび Microsoft SQL Server プラットフォームを基盤としています。</span><span class="sxs-lookup"><span data-stu-id="3da56-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is built on the Microsoft Windows and Microsoft SQL Server platforms.</span></span> <span data-ttu-id="3da56-104">BizTalk Server の障害に対する耐性や回復力は、その基盤となるプラットフォームの耐性と回復力にかかっています。</span><span class="sxs-lookup"><span data-stu-id="3da56-104">The ability of BizTalk Server to survive or recover from a disaster depends on the ability of the underlying platform to survive or recover.</span></span>  
  
 <span data-ttu-id="3da56-105">ビジネス アクティビティ監視 (BAM) データベースと、メッセージ ボックス データベースは、次を行うお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3da56-105">For your Business Activity Monitoring (BAM) databases and your MessageBox database, we recommend you do the following:</span></span>  
  
- <span data-ttu-id="3da56-106">SQL Server Enterprise Edition のフェールオーバー クラスタリングを使用します。</span><span class="sxs-lookup"><span data-stu-id="3da56-106">Set up fail-over clustering, which is available in SQL Server Enterprise Edition.</span></span> <span data-ttu-id="3da56-107">フェールオーバー クラスターを使用することにより、サーバーで障害が発生した場合に、SQL Server インスタンスの処理を、稼働しているサーバーへと自動的に切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="3da56-107">Fail-over clustering enables SQL Server to automatically switch the processing for an instance of SQL Server from a failed server to a working server.</span></span>  
  
   <span data-ttu-id="3da56-108">BAM プライマリ インポート データベースは、イベント データを収集します。</span><span class="sxs-lookup"><span data-stu-id="3da56-108">The BAM Primary Import database collects event data.</span></span> <span data-ttu-id="3da56-109">障害が発生した場合、前回のバックアップ以降に BAM プライマリ インポート データベースに書き込まれたデータが失われます。</span><span class="sxs-lookup"><span data-stu-id="3da56-109">In the event of a disaster, data that was written to the BAM Primary Import database since the last backup will be lost.</span></span> <span data-ttu-id="3da56-110">失われたイベント データを再生成することはできません。そのため、BAM プライマリ インポート データベースに対してフェールオーバー クラスタリングを有効にすることがきわめて重要となります。</span><span class="sxs-lookup"><span data-stu-id="3da56-110">Because there is no way to regenerate lost events, it is especially important that you enable fail over clustering on your BAM Primary Import database.</span></span>  
  
- <span data-ttu-id="3da56-111">SQL Server RAID (Redundant Array of Independent Disks) を使用します。メッセージ ボックス データベースおよび BAM プライマリ インポート データベースに関して、RAID の使用が特に重要となります。</span><span class="sxs-lookup"><span data-stu-id="3da56-111">Use SQL Server RAID (redundant array of independent disks), especially for the MessageBox database and the BAM Primary Import database.</span></span>  
  
  <span data-ttu-id="3da56-112">フォールト トレラントな Windows and SQL Server 環境を設計するにあたっては、以下に示す情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3da56-112">Use the following resources to design your Windows and SQL Server deployments for fault tolerance.</span></span> <span data-ttu-id="3da56-113">クラスタリングやディスク ミラー化など、サービス障害やデータ損失を防ぐためのハードウェアおよびサーバーの冗長性技術をしっかり習得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3da56-113">Take time to learn about hardware and server redundancy technologies, such as clustering and disk mirroring, to prevent service outages and data loss.</span></span>  
  
- [<span data-ttu-id="3da56-114">ホワイト ペーパー: 高可用性-常時接続テクノロジ</span><span class="sxs-lookup"><span data-stu-id="3da56-114">White Paper: High Availability—Always On Technologies</span></span>](http://go.microsoft.com/fwlink/?LinkId=130376)  
  
   <span data-ttu-id="3da56-115">"高可用性 – Always On Technologies"ホワイト ペーパーでは、SQL Server 2008 で利用できる高可用性機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="3da56-115">The “High Availability – Always On Technologies” whitepaper describes high availability features that are available with SQL Server 2008.</span></span>  
  
- [<span data-ttu-id="3da56-116">高可用性ソリューションの概要</span><span class="sxs-lookup"><span data-stu-id="3da56-116">High Availability Solutions Overview</span></span>](http://go.microsoft.com/fwlink/?LinkId=130377)  
  
   <span data-ttu-id="3da56-117">サーバーまたはデータベースの可用性を向上させる SQL Server 2008 の高可用性ソリューションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3da56-117">Introduces several high-availability solutions for SQL Server 2008 that improve the availability of servers or databases.</span></span>  
  
- [<span data-ttu-id="3da56-118">第 15 章「高可用性オプションでは、SQL Server リソース キット</span><span class="sxs-lookup"><span data-stu-id="3da56-118">Chapter 15 - High Availability Options, SQL Server Resource Kit</span></span>](http://go.microsoft.com/fwlink/?LinkId=24431)  
  
   <span data-ttu-id="3da56-119">Microsoft SQL Server リソース キットには、管理や配置計画に関する情報が広範囲にわたって記載されています。</span><span class="sxs-lookup"><span data-stu-id="3da56-119">The Microsoft SQL Server Resource Kit covers a wide range of administrative and deployment planning areas.</span></span> <span data-ttu-id="3da56-120">第 15 章では、フォールト トレランスおよび復旧のための計画について説明しています。</span><span class="sxs-lookup"><span data-stu-id="3da56-120">Chapter 15 covers planning for fault tolerance and recovery.</span></span>  
  
- [<span data-ttu-id="3da56-121">Windows Deployment Services Step-by-Step Guide</span><span class="sxs-lookup"><span data-stu-id="3da56-121">Windows Deployment Services Step-by-Step Guide</span></span>](http://go.microsoft.com/fwlink/?LinkId=130379)  
  
   <span data-ttu-id="3da56-122">Windows 展開サービスの役割を Windows Server 2008 で使用する手順が示されています</span><span class="sxs-lookup"><span data-stu-id="3da56-122">Contains step-by-step guidance for how to use the Windows Deployment Services role in Windows Server 2008</span></span>  
  
- <span data-ttu-id="3da56-123">[Windows Server 2003 導入ガイド: サーバーの展開を計画する](http://go.microsoft.com/fwlink/?LinkId=24433)します。</span><span class="sxs-lookup"><span data-stu-id="3da56-123">[Windows Server 2003 Deployment Kit: Planning Server Deployments](http://go.microsoft.com/fwlink/?LinkId=24433).</span></span>  
  
   <span data-ttu-id="3da56-124">このドキュメントでは、サーバー ストレージの導入計画のほか、中規模から大規模な組織におけるファイル サーバー、プリント サーバー、およびターミナル サーバーの設計と導入について説明しています。</span><span class="sxs-lookup"><span data-stu-id="3da56-124">This book provides information about planning server storage, and information about designing and deploying file servers, print servers, and terminal servers in medium and large organizations.</span></span>  
  
   <span data-ttu-id="3da56-125">また、このドキュメントには、リモート サーバーの管理計画、サーバー クラスターの設計と導入、ネットワーク負荷分散クラスターの設計と導入に関するガイドラインが記載されています。このガイドラインに従うことによって、サーバーの可用性とスケーラビリティを最大限に高めることができます。</span><span class="sxs-lookup"><span data-stu-id="3da56-125">You can also use the guidelines in this book to maximize the availability and scalability of your servers by planning for remote server management, designing and deploying server clusters, and designing and deploying Network Load Balancing clusters.</span></span>  
  
## <a name="backing-up-your-platform"></a><span data-ttu-id="3da56-126">プラットフォームのバックアップ</span><span class="sxs-lookup"><span data-stu-id="3da56-126">Backing Up Your Platform</span></span>  
 <span data-ttu-id="3da56-127">システムの構成を終えたら、サーバーの完全バックアップを行い、データが万一失われてしまっても迅速にサーバーを元の状態に復旧できるように準備します。</span><span class="sxs-lookup"><span data-stu-id="3da56-127">After you have configured your system, prepare full backups of your servers so you can quickly restore an identical server in the event of data loss.</span></span>  
  
 <span data-ttu-id="3da56-128">プラットフォームをバックアップするには、記載されたバックアップ手順を次の各テクノロジについて実行します。</span><span class="sxs-lookup"><span data-stu-id="3da56-128">To back up your platform, perform the documented backup procedures for each of the following technologies:</span></span>  
  
- <span data-ttu-id="3da56-129">Microsoft Windows Server Standard、Enterprise、または Datacenter Edition</span><span class="sxs-lookup"><span data-stu-id="3da56-129">Microsoft Windows Server Standard, Enterprise, or Datacenter Edition</span></span>  
  
- <span data-ttu-id="3da56-130">インターネット インフォメーション サービス (IIS)</span><span class="sxs-lookup"><span data-stu-id="3da56-130">Internet Information Services (IIS)</span></span>  
  
- <span data-ttu-id="3da56-131">Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="3da56-131">Microsoft SQL Server</span></span>  
  
- <span data-ttu-id="3da56-132">Windows SharePoint Services。Windows SharePoint Services アダプターが使用します。</span><span class="sxs-lookup"><span data-stu-id="3da56-132">Windows SharePoint Services, which is used by the Windows SharePoint Services adapter.</span></span>  
  
  <span data-ttu-id="3da56-133">「BizTalk Server 運用ガイド」で"BizTalk Server のバックアップ"での推奨事項に従って[チェックリスト: ディザスター リカバリーによる可用性の向上](http://go.microsoft.com/fwlink/?LinkId=130498)します。</span><span class="sxs-lookup"><span data-stu-id="3da56-133">Follow the recommendations in the “BizTalk Server Operations Guide” for “Backing up BizTalk Server” available at [Checklist: Increasing Availability with Disaster Recovery](http://go.microsoft.com/fwlink/?LinkId=130498).</span></span>  
  
  <span data-ttu-id="3da56-134">バックアップ手順および復元手順を十分にテストしたら、バックアップを安全かつ離れた場所に保管します。</span><span class="sxs-lookup"><span data-stu-id="3da56-134">Thoroughly test your backup and restore procedures, and put them in a safe, remote location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3da56-135">参照</span><span class="sxs-lookup"><span data-stu-id="3da56-135">See Also</span></span>  
 [<span data-ttu-id="3da56-136">BizTalk Server データベースのバックアップと復元</span><span class="sxs-lookup"><span data-stu-id="3da56-136">Backing Up and Restoring the BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-the-biztalk-server-databases.md)