---
title: BizTalk Server データベースの高可用性を実現する |Microsoft ドキュメント
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
ms.openlocfilehash: 3648a8f6d48bbfd6cf67995e1d314511b70db7bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269346"
---
# <a name="providing-high-availability-for-biztalk-server-databases"></a><span data-ttu-id="1132e-102">BizTalk Server データベースの高可用性を実現する</span><span class="sxs-lookup"><span data-stu-id="1132e-102">Providing High Availability for BizTalk Server Databases</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="1132e-103"> は、データの永続性を実現するという点で、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] に強く依存しています。</span><span class="sxs-lookup"><span data-stu-id="1132e-103"> relies heavily on [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] for data persistence.</span></span> <span data-ttu-id="1132e-104">その他すべての [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンポーネントおよびホストにも、多種多様な業務アプリケーション (メッセージの受信、処理、ルーティングなど) を統合するプロセスにおいて、それぞれ固有の役割がありますが、この作業をディスクに取り込み、維持するという役割は、データベース コンピューターにあります。</span><span class="sxs-lookup"><span data-stu-id="1132e-104">All other components and hosts in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] have specific roles in the process of integrating disparate business applications (for example, receiving, processing, or routing messages), but the database computer captures this work and persists it to disk.</span></span>  
  
 <span data-ttu-id="1132e-105">高可用性を実現する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースを使用して Windows Server フェールオーバー クラスタ リングをサーバー クラスターを作成する SQL Server を実行している 2 つのデータベース コンピューターを構成します。</span><span class="sxs-lookup"><span data-stu-id="1132e-105">To provide high availability for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, use Windows Server Failover Clustering to configure two database computers that are running SQL Server to create a server cluster.</span></span> <span data-ttu-id="1132e-106">サーバーをクラスター化することにより、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースの冗長性とフォールト トレランス性が向上します。</span><span class="sxs-lookup"><span data-stu-id="1132e-106">Server clustering provides redundancy and fault tolerance for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span> <span data-ttu-id="1132e-107">複数のコンピューターを並列に運用して可用性とスケーラビリティを高めようとする負荷分散クラスタリングとは異なり、サーバー クラスタリングでは通常、2 台のデータベース コンピューターをアクティブ/パッシブ構成で使用します。この構成では、一方のコンピューターが他方のコンピューターのバックアップ リソースを提供します。</span><span class="sxs-lookup"><span data-stu-id="1132e-107">Unlike load-balanced clustering, where a group of computers functions together to increase availability and scalability, server clustering typically involves a pair of database computers in an active/passive configuration so that one computer provides backup resources for the other.</span></span>  
  
 <span data-ttu-id="1132e-108">次の図は、アクティブ/パッシブ構成のサーバー クラスタリングによって高可用性を実現した [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のデータベース層を示しています。</span><span class="sxs-lookup"><span data-stu-id="1132e-108">The following figure shows a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] database tier with high availability through active/passive server clustering.</span></span>  
  
 <span data-ttu-id="1132e-109">![BizTalk Server のデータベース層](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")</span><span class="sxs-lookup"><span data-stu-id="1132e-109">![BizTalk Server Database Tier](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")</span></span>  
  
 <span data-ttu-id="1132e-110">アクティブ側のデータベース コンピューターでエラーや障害が発生した場合、障害の起きたコンピューターが復旧するまでの間、パッシブ側のコンピューターがアクティブになり、データベース リソースの管理を引き継ぎます。</span><span class="sxs-lookup"><span data-stu-id="1132e-110">If the active database computer encounters errors or fails, the passive computer becomes active and assumes control over the database resources until the failed computer is repaired.</span></span> <span data-ttu-id="1132e-111">データベース サービスのフェール オーバーが行われ、さらに、新たにアクティブとなったコンピューターへのデータ接続が確立されることによって、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーションは処理を続行できます。</span><span class="sxs-lookup"><span data-stu-id="1132e-111">The database service fails over and restores data connections to the new active computer and enables the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application to continue functioning.</span></span>  
  
 <span data-ttu-id="1132e-112">によってインストールされるデータベースについては[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[BizTalk Server でのデータベース](../core/databases-in-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="1132e-112">For information about the databases that are installed by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Databases in BizTalk Server](../core/databases-in-biztalk-server.md).</span></span>  
  
 <span data-ttu-id="1132e-113">バックアップする方法について、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースを参照してください[をバックアップおよび BizTalk Server データベースの復元](../core/backing-up-and-restoring-biztalk-server-databases.md)です。</span><span class="sxs-lookup"><span data-stu-id="1132e-113">For information about backing up your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, see [Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server-databases.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1132e-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1132e-114">In This Section</span></span>  
  
-   [<span data-ttu-id="1132e-115">スケール アウト データベース</span><span class="sxs-lookup"><span data-stu-id="1132e-115">Scaled-Out Databases</span></span>](../core/scaled-out-databases.md)  
  
-   [<span data-ttu-id="1132e-116">BizTalk Server データベースをクラスタ リング</span><span class="sxs-lookup"><span data-stu-id="1132e-116">Clustering the BizTalk Server Databases</span></span>](../core/clustering-the-biztalk-server-databases1.md)  
  
-   [<span data-ttu-id="1132e-117">BizTalk Server ホスト インスタンスを SQL Server フェールオーバー時の動作</span><span class="sxs-lookup"><span data-stu-id="1132e-117">Behavior of BizTalk Server Host Instances during SQL Server Failover</span></span>](../core/behavior-of-biztalk-server-host-instances-during-sql-server-failover.md)  
  
-   [<span data-ttu-id="1132e-118">SQL Server データベース ミラーリング、ボリューム シャドウ コピー サービスと AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="1132e-118">SQL Server database mirroring, Volume Shadow Copy service and AlwaysOn</span></span>](../core/sql-server-database-mirroring-volume-shadow-copy-service-and-alwayson.md)  
  
## <a name="see-also"></a><span data-ttu-id="1132e-119">参照</span><span class="sxs-lookup"><span data-stu-id="1132e-119">See Also</span></span>  
 <span data-ttu-id="1132e-120">[BizTalk ホストの高可用性を実現します。](../core/providing-high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="1132e-120">[Providing High Availability for BizTalk Hosts](../core/providing-high-availability-for-biztalk-hosts.md) </span></span>  
 [<span data-ttu-id="1132e-121">サンプル BizTalk Server の高可用性のシナリオ</span><span class="sxs-lookup"><span data-stu-id="1132e-121">Sample BizTalk Server High Availability Scenarios</span></span>](../core/sample-biztalk-server-high-availability-scenarios.md)