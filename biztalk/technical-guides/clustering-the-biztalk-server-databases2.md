---
title: データベースをクラスター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1b68bc3f-c0c4-4050-8ca3-df6dd1927637
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 676f3078974384579c113bdcd51d5d118d43b4f3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65277325"
---
# <a name="clustering-the-biztalk-server-databases"></a>BizTalk Server データベースのクラスター化
BizTalk Server データベースに障害が発生すると、BizTalk Server 環境は正常に機能することができなくなります。 次の図に示すように、BizTalk Server データベースに対して、Microsoft SQL Server クラスターを作成することによって高可用性を確保できます。  
  
 ![BizTalk Server のデータベース層](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")  
  
 BizTalk Server データベースの高可用性ソリューションを構築するためには、SQL Server を実行する 2 台以上のコンピューターと、クラスター内の共有ディスク アレイが必要です。  
  
## <a name="clustering-options"></a>クラスタ リングのオプション  
 ビジネス ニーズに合わせて、BizTalk Server データベースの最適なクラスター構成を確認します。 オプションの一覧を次に示します。  
  
-   **アクティブ/パッシブ**します。 通常、BizTalk Server データベースの高可用性は、アクティブ/パッシブのサーバー クラスター構成で構成されている 2 つ以上のデータベース コンピューターで構成されます。 これらのコンピューターが共通のディスク リソースを共有 (など、RAID 1 + 0 SCSI ディスク アレイやストレージ エリア ネットワーク) Windows クラスタ リングを使用してバックアップの冗長性とフォールト トレランスを提供します。  
  
-   **アクティブ/アクティブ**します。 Windows クラスタ リングと SQL Server を使用すると、1 つまたは複数の SQL Server インスタンスを「アクティブ」で実行されて、クラスターの各ノードのアクティブ/アクティブ モードで SQL Server を実行できます。 たとえば、これにより他のノードで 1 つのノードおよびその他のすべての BizTalk Server データベースにメッセージ ボックス データベースを使用します。 クラスターのハードウェア使用率を最大化することができますが、アクティブ/アクティブ SQL Server の構成を注意して使用する必要があります。  
  
     各ノードに同時に負荷を処理できるすべての SQL Server インスタンスの SQL Server クラスター ノードのフェールオーバー シナリオ中にしますか。 十分な CPU リソースはありますか。 十分なメモリはありますか。 ネットワーク帯域幅について説明します。 ディスク I/O の競合ですか。  
  
     これらは、アクティブ/アクティブ クラスターで SQL Server は、BizTalk アプリケーションの適切なかどうかを決定するために回答する必要がある質問の一部です。 1 つのノードはフェールオーバー シナリオでは、すべての SQL Server インスタンスを処理できないと判断された場合、別の方法では、アクティブ/アクティブ/パッシブ クラスタ リングを使用します。  
  
-   **アクティブ/アクティブ/パッシブ**します。 実行時の環境では、BizTalk 管理データベース、メッセージ ボックス データベース、追跡分析サービス データベース、BAM 分析データベース、BAM スター スキーマ データベース、BAM プライマリ インポート データベース、および BAM アーカイブ データベースへの書き込み処理が行われます。 したがって、これらのデータベースを障害から保護することが特に重要となります。当然、どのデータベースをクラスター化するかという判断において、より高い優先順位が付けられることになります。 その他のデータベースに対する書き込みは、ユーザーまたはツールによってのみ行われます。 メッセージ ボックス データベースの場合は、アクティブ/アクティブ/パッシブまたはアクティブ/アクティブ/アクティブ/パッシブ構成で必要なハードウェアを最小限に抑えるを検討できます。  
  
> [!NOTE]  
>  SQL Server Standard Edition では、2 ノード フェールオーバー クラスターをサポートします。 SQL Server のアクティブ/アクティブ/パッシブ構成を使用する場合は、Enterprise Edition を使用する必要があります。  
  
## <a name="procedures-for-clustering-the-databases"></a>データベースをクラスター化するための手順  
 BizTalk Server データベースをクラスタ リングを開始する前に、次の前提条件を満たすことを確認します。  
  
-   BizTalk Server 環境のドメイン グループを作成する場合は、グローバル ドメイン アカウントを作成する必要があります。  
  
-   インストールして、BizTalk Server を構成する前に、SQL Server クラスターを構成します。 参照してください[Windows Server のフェールオーバー クラスタ リング (WSFC) を SQL Server](https://docs.microsoft.com/sql/sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server)または[Always On フェールオーバー クラスター インスタンス (SQL Server)](https://docs.microsoft.com/sql/sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server)します。  
  
-   さらに、マスター シークレット サーバーをクラスター化する場合は、マスター シークレット サーバーを最初に構成しておく必要があります。 参照してください[マスター シークレット サーバーの高可用性](../technical-guides/high-availability-for-the-master-secret-server.md)します。  
  
#### <a name="run-biztalk-configuration"></a>BizTalk 構成を実行します。  
  
1. BizTalk Server は、ランタイム サーバーをインストールします。  
  
2. **[BizTalk Server 構成]** を開きます。  
  
3. カスタム構成を適用するを参照してください。[のインポートとエクスポートの BizTalk Server 構成](../install-and-config-guides/import-and-export-biztalk-server-configuration.md)します。 BizTalk Server データベースで SQL Server クラスターの名前を入力します。 SQL Server クラスターを指定する、**データベース**構成のダイアログ。  
  
4. BizTalk Server 構成を使用して、完了、[カスタム構成](../install-and-config-guides/configure-biztalk-server.md)します。
  
   BizTalk Server データベースをクラスタ リングの詳細については、次を参照してください。 [Improving Fault Tolerance in Windows Server 2008 フェールオーバー クラスターまたは Windows Server 2003 サーバー クラスターを使用して BizTalk Server](https://www.microsoft.com/download/details.aspx?id=2290)します。  
  
## <a name="behavior-of-biztalk-host-instances-during-sql-server-failover"></a>SQL Server フェールオーバー時の BizTalk ホスト インスタンスの動作  
 SQL Server フェールオーバー時の BizTalk ホスト インスタンスの動作の詳細については、次を参照してください。[動作の BizTalk Server ホスト インスタンスを SQL Server フェールオーバー時](../core/behavior-of-biztalk-server-host-instances-during-sql-server-failover.md)します。  
  
## <a name="using-sql-server-database-mirroring"></a>SQL Server データベース ミラーリングの使用  
 詳細については、BizTalk Server データベースのクラスタ リングに関する SQL Server データベース ミラーリングを使用して、次を参照してください。 [SQL Server データベース ミラーリング、ボリューム シャドウ コピー サービス、および AlwaysOn](../core/sql-server-database-mirroring-volume-shadow-copy-service-and-alwayson.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server データベースのスケール アウト](../technical-guides/scaling-out-the-biztalk-server-databases.md)