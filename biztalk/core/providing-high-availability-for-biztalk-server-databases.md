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
# <a name="providing-high-availability-for-biztalk-server-databases"></a>BizTalk Server データベースの高可用性を実現します。
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 大きく依存して[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データ永続化します。 その他のすべてのコンポーネントおよびホストに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]異種ビジネス アプリケーション (たとえば、受信、処理、またはルーティング メッセージ) を統合するプロセスの特定のロールがデータベースのコンピューターは、この作業をキャプチャし、ディスクに永続化します。  
  
 高可用性を実現する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースを使用して、Windows Server フェールオーバー クラスタ リング サーバー クラスターを作成する SQL Server を実行している 2 つのデータベース コンピューターを構成します。 サーバー クラスタ リングの冗長性とフォールト トレランスを提供する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。 複数のコンピューターを並列に運用して可用性とスケーラビリティを高めようとする負荷分散クラスタリングとは異なり、サーバー クラスタリングでは通常、2 台のデータベース コンピューターをアクティブ/パッシブ構成で使用します。この構成では、一方のコンピューターが他方のコンピューターのバックアップ リソースを提供します。  
  
 次に示します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アクティブ/パッシブのサーバーのクラスタ リングによる高可用性を使用したデータベース層。  
  
 ![BizTalk Server のデータベース層](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")  
  
 アクティブ側のデータベース コンピューターでエラーや障害が発生した場合、障害の起きたコンピューターが復旧するまでの間、パッシブ側のコンピューターがアクティブになり、データベース リソースの管理を引き継ぎます。 Database サービスは、フェールオーバーしデータ接続を新しいアクティブなコンピューターに復元し、により、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーションは処理を続行します。  
  
 によってインストールされているデータベースについて[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[BizTalk Server でのデータベース](../core/databases-in-biztalk-server.md)します。  
  
 バックアップする方法については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースを参照してください[Backing Up and BizTalk Server データベースの復元](../core/backing-up-and-restoring-biztalk-server-databases.md)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [スケールアウト データベース](../core/scaled-out-databases.md)  
  
-   [BizTalk Server データベースのクラスタリング](../core/clustering-the-biztalk-server-databases1.md)  
  
-   [SQL Server フェールオーバー時の BizTalk Server ホスト インスタンスの動作](../core/behavior-of-biztalk-server-host-instances-during-sql-server-failover.md)  
  
-   [SQL Server データベース ミラーリング、ボリューム シャドウ コピー サービス、および AlwaysOn の使用](../core/sql-server-database-mirroring-volume-shadow-copy-service-and-alwayson.md)  
  
## <a name="see-also"></a>参照  
 [BizTalk ホストの高可用性を実現します。](../core/providing-high-availability-for-biztalk-hosts.md)   
 [BizTalk Server の高可用性を実現するサンプル シナリオ](../core/sample-biztalk-server-high-availability-scenarios.md)