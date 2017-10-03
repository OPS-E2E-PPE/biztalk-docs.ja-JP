---
title: "BizTalk Server データベースの高可用性を実現する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "41"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3648a8f6d48bbfd6cf67995e1d314511b70db7bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="providing-high-availability-for-biztalk-server-databases"></a>BizTalk Server データベースの高可用性を実現する
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、データの永続性を実現するという点で、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] に強く依存しています。 その他すべての [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンポーネントおよびホストにも、多種多様な業務アプリケーション (メッセージの受信、処理、ルーティングなど) を統合するプロセスにおいて、それぞれ固有の役割がありますが、この作業をディスクに取り込み、維持するという役割は、データベース コンピューターにあります。  
  
 高可用性を実現する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースを使用して Windows Server フェールオーバー クラスタ リングをサーバー クラスターを作成する SQL Server を実行している 2 つのデータベース コンピューターを構成します。 サーバーをクラスター化することにより、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースの冗長性とフォールト トレランス性が向上します。 複数のコンピューターを並列に運用して可用性とスケーラビリティを高めようとする負荷分散クラスタリングとは異なり、サーバー クラスタリングでは通常、2 台のデータベース コンピューターをアクティブ/パッシブ構成で使用します。この構成では、一方のコンピューターが他方のコンピューターのバックアップ リソースを提供します。  
  
 次の図は、アクティブ/パッシブ構成のサーバー クラスタリングによって高可用性を実現した [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のデータベース層を示しています。  
  
 ![BizTalk Server のデータベース層](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")  
  
 アクティブ側のデータベース コンピューターでエラーや障害が発生した場合、障害の起きたコンピューターが復旧するまでの間、パッシブ側のコンピューターがアクティブになり、データベース リソースの管理を引き継ぎます。 データベース サービスのフェール オーバーが行われ、さらに、新たにアクティブとなったコンピューターへのデータ接続が確立されることによって、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーションは処理を続行できます。  
  
 によってインストールされるデータベースについては[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[BizTalk Server でのデータベース](../core/databases-in-biztalk-server.md)です。  
  
 バックアップする方法について、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースを参照してください[をバックアップおよび BizTalk Server データベースの復元](../core/backing-up-and-restoring-biztalk-server-databases.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [スケール アウト データベース](../core/scaled-out-databases.md)  
  
-   [BizTalk Server データベースをクラスタ リング](../core/clustering-the-biztalk-server-databases1.md)  
  
-   [BizTalk Server ホスト インスタンスを SQL Server フェールオーバー時の動作](../core/behavior-of-biztalk-server-host-instances-during-sql-server-failover.md)  
  
-   [SQL Server データベース ミラーリング、ボリューム シャドウ コピー サービスと AlwaysOn](../core/sql-server-database-mirroring-volume-shadow-copy-service-and-alwayson.md)  
  
## <a name="see-also"></a>参照  
 [BizTalk ホストの高可用性を実現します。](../core/providing-high-availability-for-biztalk-hosts.md)   
 [サンプル BizTalk Server の高可用性のシナリオ](../core/sample-biztalk-server-high-availability-scenarios.md)