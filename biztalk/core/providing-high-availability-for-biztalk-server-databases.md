---
title: BizTalk Server データベースの高可用性を実現する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- clustering, SQL Servers
- databases, architecture
- SQL Server, clustering
- servers, clustering
- databases, high availability
- architecture
- databases, clustering
- BizTalk Server, architecture
- Windows clustering
- high availability, databases
- clustering, databases
- data, persistence
- SQL Server Analysis Services
ms.assetid: 47fbc402-9e46-41dd-bc12-d1cde1982576
caps.latest.revision: 41
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0505691eafa6a6cf2215282635c303a55e9b1ce8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398419"
---
# <a name="providing-high-availability-for-biztalk-server-databases"></a><span data-ttu-id="6f8cf-102">BizTalk Server データベースの高可用性を実現します。</span><span class="sxs-lookup"><span data-stu-id="6f8cf-102">Providing High Availability for BizTalk Server Databases</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="6f8cf-103">大きく依存して[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データ永続化します。</span><span class="sxs-lookup"><span data-stu-id="6f8cf-103">relies heavily on [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] for data persistence.</span></span> <span data-ttu-id="6f8cf-104">その他のすべてのコンポーネントおよびホストに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]異種ビジネス アプリケーション (たとえば、受信、処理、またはルーティング メッセージ) を統合するプロセスの特定のロールがデータベースのコンピューターは、この作業をキャプチャし、ディスクに永続化します。</span><span class="sxs-lookup"><span data-stu-id="6f8cf-104">All other components and hosts in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] have specific roles in the process of integrating disparate business applications (for example, receiving, processing, or routing messages), but the database computer captures this work and persists it to disk.</span></span>  
  
 <span data-ttu-id="6f8cf-105">高可用性を実現する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースを使用して、Windows Server フェールオーバー クラスタ リング サーバー クラスターを作成する SQL Server を実行している 2 つのデータベース コンピューターを構成します。</span><span class="sxs-lookup"><span data-stu-id="6f8cf-105">To provide high availability for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, use Windows Server Failover Clustering to configure two database computers that are running SQL Server to create a server cluster.</span></span> <span data-ttu-id="6f8cf-106">サーバー クラスタ リングの冗長性とフォールト トレランスを提供する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。</span><span class="sxs-lookup"><span data-stu-id="6f8cf-106">Server clustering provides redundancy and fault tolerance for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span> <span data-ttu-id="6f8cf-107">複数のコンピューターを並列に運用して可用性とスケーラビリティを高めようとする負荷分散クラスタリングとは異なり、サーバー クラスタリングでは通常、2 台のデータベース コンピューターをアクティブ/パッシブ構成で使用します。この構成では、一方のコンピューターが他方のコンピューターのバックアップ リソースを提供します。</span><span class="sxs-lookup"><span data-stu-id="6f8cf-107">Unlike load-balanced clustering, where a group of computers functions together to increase availability and scalability, server clustering typically involves a pair of database computers in an active/passive configuration so that one computer provides backup resources for the other.</span></span>  
  
 <span data-ttu-id="6f8cf-108">次に示します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アクティブ/パッシブのサーバーのクラスタ リングによる高可用性を使用したデータベース層。</span><span class="sxs-lookup"><span data-stu-id="6f8cf-108">The following figure shows a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] database tier with high availability through active/passive server clustering.</span></span>  
  
 <span data-ttu-id="6f8cf-109">![BizTalk Server のデータベース層](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")</span><span class="sxs-lookup"><span data-stu-id="6f8cf-109">![BizTalk Server Database Tier](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")</span></span>  
  
 <span data-ttu-id="6f8cf-110">アクティブ側のデータベース コンピューターでエラーや障害が発生した場合、障害の起きたコンピューターが復旧するまでの間、パッシブ側のコンピューターがアクティブになり、データベース リソースの管理を引き継ぎます。</span><span class="sxs-lookup"><span data-stu-id="6f8cf-110">If the active database computer encounters errors or fails, the passive computer becomes active and assumes control over the database resources until the failed computer is repaired.</span></span> <span data-ttu-id="6f8cf-111">Database サービスは、フェールオーバーしデータ接続を新しいアクティブなコンピューターに復元し、により、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーションは処理を続行します。</span><span class="sxs-lookup"><span data-stu-id="6f8cf-111">The database service fails over and restores data connections to the new active computer and enables the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application to continue functioning.</span></span>  
  
 <span data-ttu-id="6f8cf-112">によってインストールされているデータベースについて[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[BizTalk Server でのデータベース](../core/databases-in-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="6f8cf-112">For information about the databases that are installed by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Databases in BizTalk Server](../core/databases-in-biztalk-server.md).</span></span>  
  
 <span data-ttu-id="6f8cf-113">バックアップする方法については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースを参照してください[Backing Up and BizTalk Server データベースの復元](../core/backing-up-and-restoring-biztalk-server-databases.md)します。</span><span class="sxs-lookup"><span data-stu-id="6f8cf-113">For information about backing up your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, see [Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server-databases.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6f8cf-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6f8cf-114">In This Section</span></span>  
  
-   [<span data-ttu-id="6f8cf-115">スケールアウト データベース</span><span class="sxs-lookup"><span data-stu-id="6f8cf-115">Scaled-Out Databases</span></span>](../core/scaled-out-databases.md)  
  
-   [<span data-ttu-id="6f8cf-116">BizTalk Server データベースのクラスタリング</span><span class="sxs-lookup"><span data-stu-id="6f8cf-116">Clustering the BizTalk Server Databases</span></span>](../core/clustering-the-biztalk-server-databases1.md)  
  
-   [<span data-ttu-id="6f8cf-117">SQL Server フェールオーバー時の BizTalk Server ホスト インスタンスの動作</span><span class="sxs-lookup"><span data-stu-id="6f8cf-117">Behavior of BizTalk Server Host Instances during SQL Server Failover</span></span>](../core/behavior-of-biztalk-server-host-instances-during-sql-server-failover.md)  
  
-   [<span data-ttu-id="6f8cf-118">SQL Server データベース ミラーリング、ボリューム シャドウ コピー サービス、および AlwaysOn の使用</span><span class="sxs-lookup"><span data-stu-id="6f8cf-118">SQL Server database mirroring, Volume Shadow Copy service and AlwaysOn</span></span>](../core/sql-server-database-mirroring-volume-shadow-copy-service-and-alwayson.md)  
  
## <a name="see-also"></a><span data-ttu-id="6f8cf-119">参照</span><span class="sxs-lookup"><span data-stu-id="6f8cf-119">See Also</span></span>  
 <span data-ttu-id="6f8cf-120">[BizTalk ホストの高可用性を実現します。](../core/providing-high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="6f8cf-120">[Providing High Availability for BizTalk Hosts](../core/providing-high-availability-for-biztalk-hosts.md) </span></span>  
 [<span data-ttu-id="6f8cf-121">BizTalk Server の高可用性を実現するサンプル シナリオ</span><span class="sxs-lookup"><span data-stu-id="6f8cf-121">Sample BizTalk Server High Availability Scenarios</span></span>](../core/sample-biztalk-server-high-availability-scenarios.md)