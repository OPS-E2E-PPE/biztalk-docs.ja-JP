---
title: "BizTalk Server Databases2 をクラスタ リング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1b68bc3f-c0c4-4050-8ca3-df6dd1927637
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c84f8f6ef26c567a1bbac44df078f2df58ca9da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="clustering-the-biztalk-server-databases"></a>BizTalk Server データベースのクラスター化
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースに障害が発生すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境は正常に機能することができなくなります。 高可用性を実現するには、Microsoft を作成することができます[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]のクラスター、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース、次の図に示すようにします。  
  
 ![BizTalk Server のデータベース層](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")  
  
 高可用性ソリューションを作成する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース、する必要がありますには、少なくとも 2 台のコンピューターを実行している[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]とクラスターの共有ディスク アレイ。  
  
## <a name="clustering-options"></a>クラスタ リングのオプション  
 最適なクラスター構成の決定、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ビジネス ニーズに合わせてデータベース。 オプションの一覧を次に示します。  
  
-   **アクティブ/パッシブ**です。 高可用性、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アクティブ/パッシブのサーバー クラスター構成で構成されている 2 つ以上のデータベース コンピューターのデータベースが通常で構成されます。 これらのコンピューターに共通のディスク リソースを共有する (など、RAID 1 + 0 SCSI ディスク アレイやストレージ エリア ネットワーク) Windows クラスタ リングを使用してバックアップの冗長性とフォールト トレランスを提供します。  
  
-   **アクティブ/アクティブ**です。 Windows クラスタ リングと[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]に実行できるように[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]"active"、および実行中の 1 つまたは複数のクラスターの各ノードのあるアクティブ/アクティブ モードで[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス。 たとえば、このようにすると 1 つのノードとその他のすべてのメッセージ ボックス データベースに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]他のノード上のデータベースです。 これにより、クラスターのハードウェアの使用状況が、アクティブ/アクティブを最大限に高まります[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]構成は、注意を払って使用する必要があります。  
  
     各ノードに同時に負荷を処理できるすべての[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]をインスタンス化中に、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]クラスター ノードのフェールオーバー シナリオしますか? 十分な CPU リソースがあるか。 十分なメモリはありますか。 ネットワーク帯域幅について説明します。 ディスク I/O の競合ですか。  
  
     これらは、アクティブ/アクティブの場合を判断するために回答する必要がある質問の一部[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]クラスターが、BizTalk アプリケーションに適しています。 1 つのノードは、すべてを処理できないと判断されたかどうかは[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス、フェールオーバー シナリオでは、代わりには、アクティブ/アクティブ/パッシブ クラスタ リングを使用します。  
  
-   **アクティブ/アクティブ/パッシブ**です。 実行時の環境では、BizTalk 管理データベース、メッセージ ボックス データベース、追跡分析サービス データベース、BAM 分析データベース、BAM スター スキーマ データベース、BAM プライマリ インポート データベース、および BAM アーカイブ データベースへの書き込み処理が行われます。 したがって、これらのデータベースを障害から保護することが特に重要となります。当然、どのデータベースをクラスター化するかという判断において、より高い優先順位が付けられることになります。 その他のデータベースに対する書き込みは、ユーザーまたはツールによってのみ行われます。 メッセージ ボックス データベースの場合は、アクティブ/アクティブ/パッシブまたはアクティブ/アクティブ/アクティブ/パッシブ構成で必要なハードウェアを最小限に抑えるをすることもできます。  
  
> [!NOTE]  
>  [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]および[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]Standard Edition は、2 つのノードのフェールオーバー クラスターをサポートします。 アクティブ/アクティブ/パッシブ構成を使用するかどうかは[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]または[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]の Enterprise Edition を使用する必要があります[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。  
  
## <a name="procedures-for-clustering-the-databases"></a>データベースをクラスター化するための手順  
 クラスタ リングを開始する前に、次の前提条件を満たすかどうかを確認、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。  
  
-   ドメイン グループを作成する場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境では、グローバル ドメイン アカウントを作成する必要があります。  
  
-   構成、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]クラスターのインストールおよび構成する前に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。 クラスタ リングの詳細については[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]を参照してください[SQL Server 2008 R2 のフェールオーバー クラスタ リングの概要](http://go.microsoft.com/fwlink/?LinkId=156820)(http://go.microsoft.com/fwlink/?LinkId=156820)。  
  
-   さらに、マスター シークレット サーバーをクラスター化する場合は、マスター シークレット サーバーを最初に構成しておく必要があります。 エンタープライズ シングル サインオンの高可用性の詳細については、次を参照してください。[マスター シークレット サーバーの高可用性](../technical-guides/high-availability-for-the-master-secret-server.md)です。  
  
#### <a name="to-run-the-biztalk-server-configuration-wizard"></a>BizTalk Server の構成ウィザードを実行するには  
  
1.  ランタイム サーバーに [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] をインストールします。  
  
2.  起動して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成プログラムです。 をクリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** 、順にクリック**BizTalk Server 構成**です。  
  
3.  カスタム構成を適用する」の手順に従います[カスタム Configuration Manager の操作](http://go.microsoft.com/fwlink/?LinkId=156822)(http://go.microsoft.com/fwlink/?LinkId=156822) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。 BizTalk Server データベースで SQL Server クラスターの名前を入力するには、SQL Server クラスターを指定する、**データベース**構成のダイアログ。  
  
4.  完了、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で手順に従って構成[カスタム構成](http://go.microsoft.com/fwlink/?LinkId=156823)(http://go.microsoft.com/fwlink/?LinkId=156823) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。  
  
 クラスタ リングの詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースを参照してください[Improving Fault Tolerance in Windows Server 2008 フェールオーバー クラスターまたは Windows Server 2003 サーバー クラスターを使用して BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=156819) (http://go.microsoft.com/fwlink/?LinkId=156819)。  
  
## <a name="behavior-of-biztalk-host-instances-during-sql-server-failover"></a>SQL Server フェールオーバー時の BizTalk ホスト インスタンスの動作  
 SQL Server フェールオーバー時の BizTalk ホスト インスタンスの動作の詳細については、次を参照してください。[動作の BizTalk Server ホスト インスタンスを SQL Server フェールオーバー時](http://go.microsoft.com/fwlink/?LinkId=151287)(http://go.microsoft.com/fwlink/?LinkId=151287)。  
  
## <a name="using-sql-server-database-mirroring"></a>SQL Server データベース ミラーリングの使用  
 詳細については、BizTalk Server データベースのクラスタ リングに関する SQL Server データベース ミラーリングを使用して、次を参照してください[使用の SQL Server データベース ミラーリングまたはボリューム シャドウ コピー サービス](http://go.microsoft.com/fwlink/?LinkId=151288)(http://go.microsoft.com/fwlink/?。LinkId = 151288) BizTalk Server ヘルプの「します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server データベースのスケール アウト](../technical-guides/scaling-out-the-biztalk-server-databases.md)