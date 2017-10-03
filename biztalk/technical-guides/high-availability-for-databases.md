---
title: "データベースの高可用性 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 63813d87-1ce4-4645-bb2a-d55e413fcace
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 415b1bbe86df1b7ee3feaeec13c889dfe2a4a902
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="high-availability-for-databases"></a>データベースの高可用性
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]大きく依存している[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データ ストアとデータの永続化します。 その他すべての [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンポーネントおよびホストにも、多種多様な業務アプリケーション (メッセージの受信、処理、ルーティングなど) を統合するプロセスにおいて、それぞれ固有の役割がありますが、この作業をディスクに取り込み、維持するという役割は、データベース コンピューターにあります。 たとえば、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が受信メッセージを受け取ると、受信ホストがそれをメッセージ ボックス データベースに保存して初めて、他のホストがメッセージを取得し、オーケストレーション処理を実行したり、送信したりできるようになります。 場合は、BizTalk ソリューションにオーケストレーション、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] (処理ホスト) は、ビジネス プロセスを実行し、オーケストレーションの完了後に、メッセージをメッセージ ボックス データベースに保存します。 ホストにメッセージをルーティングします。 その後、送信ホストが、そのメッセージをデータベースから取り出し、適切な送信アダプターを使って外部のアプリケーションに送信します。  
  
 高可用性を実現する、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 、データベースを使用して Windows クラスタ リングを実行している 2 つ以上のコンピューターを構成する[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]サーバー クラスターを作成します。 このように、サーバーをクラスター化することにより、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースの冗長性とフォールト トレランス性が向上します。 複数のコンピューターを並列に運用して可用性とスケーラビリティを高めようとする負荷分散クラスタリングとは異なり、サーバー クラスタリングでは通常、2 台のデータベース コンピューターをアクティブ/パッシブ構成で使用します。この構成では、一方のコンピューターが他方のコンピューターのバックアップ リソースを提供します。  
  
 次の図は、アクティブ/パッシブ構成のサーバー クラスタリングによって高可用性を実現した [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のデータベース層を示しています。  
  
 ![BizTalk Server のデータベース層](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")  
  
 アクティブ側のデータベース コンピューターでエラーや障害が発生した場合、障害の起きたコンピューターが復旧するまでの間、パッシブ側のコンピューターがアクティブになり、データベース リソースの管理を引き継ぎます。 データベース サービスは、フェールオーバーしデータ接続を新しいアクティブなコンピューターに復元され、継続して機能する BizTalk アプリケーションを有効にします。  
  
## <a name="biztalk-server-databases"></a>BizTalk Server データベース  
 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]でいくつかのデータベースがインストールされる[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。 次の表に、一般的な使用上の特性、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。  
  
|データベース|既定のデータベース名|使用状況特性|  
|--------------|---------------------------|---------------------------|  
|管理データベース|BizTalkMgmtDb|このデータベース ハンドル使用率の低いは読み取りおよび書き込み操作です。|  
|メッセージ ボックス データベース|BizTalkMsgBoxDb|このデータベース ハンドルの使用率の高いは、読み取りおよび書き込み操作です。|  
|追跡データベース|BizTalkDTADb|このデータベースは、追跡するために構成データの量に応じて可能性のある使用率の高い書き込み操作を処理し、使用率の低い読み取り操作します。|  
|SSO データベース|SSODB|このデータベース ハンドル使用率の低いは読み取りおよび書き込み操作です。|  
|BAM 分析データベース|BAMAnalysis|これは、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Services データベースのハンドル可能性のある使用率の高い読み取りおよび書き込み操作の実行の監視のレベルに応じて、します。|  
|BAM スター スキーマ データベース|BAMStarSchema|これは、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Services データベースのハンドル可能性のある使用率の高い読み取りおよび書き込み操作の実行の監視のレベルに応じて、します。|  
|BAM プライマリ インポート データベース|BAMPrimaryImport|これは、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Services データベースのハンドル可能性のある使用率の高い読み取りおよび書き込み操作の実行の監視のレベルに応じて、します。|  
|BAM アーカイブ データベース|BAMArchive|これは、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Services データベースのハンドル可能性のある使用率の高い読み取りおよび書き込み操作の実行の監視のレベルに応じて、します。|  
|ルール エンジン データベース|BizTalkRuleEngineDb|このデータベースは、ルールを更新する場合を除き、可能性のある使用率の低い読み取りおよび書き込み操作を処理します。|  
|Analysis Services データベースの追跡|BizTalkAnalysisDb|これは、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Services データベースのハンドルの使用率の高い読み取りおよび書き込み操作です。|  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム操作は、通常、最初の 4 つのデータベース (管理データベース、メッセージ ボックス データベース、追跡データベース、および SSO データベース) を使用します。 によっては、これらのデータベースに対するトラフィックに配置できますが使用されている別のコンピューターに[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。 によって、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を使用して、機能の表に、他のデータベースの一部またはすべてを持つ可能性があります。 スケール アウトし、必要に応じて、これらのデータベースをクラスターできます。  
  
 良いに従うことを確認してください[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースごとに別々 のディスクの使用などの展開のプラクティスです。 詳細については[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]展開のベスト プラクティスを参照してください[ホワイト ペーパー: 高可用性: Always On Technologies](http://go.microsoft.com/fwlink/?LinkId=156812) (http://go.microsoft.com/fwlink/?LinkId=156812)。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース、ことをお勧め、次を実行します。  
  
-   **フェールオーバー クラスタ リング設定**です。 フェールオーバー クラスタ リングにより[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]のインスタンスの処理を自動的に切り替える[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]稼働中のサーバーに障害が発生したサーバーからです。  
  
     BAM プライマリ インポート データベースは、イベント データを収集します。 障害が発生した場合、前回のバックアップ以降に BAM プライマリ インポート データベースに書き込まれたデータが失われます。 失われたイベントを再生成する方法はありません、ためには、BAM プライマリ インポート データベースに対してフェールオーバー クラスタ リングを有効にすることが特に重要です。  
  
-   **使用して SQL Server RAID 1 + 0 (独立したディスクの冗長アレイ)**、特に、メッセージ ボックス データベースおよび BAM プライマリ インポート データベースのです。  
  
 バックアップする方法については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースを参照してください[災害復旧のためのベスト プラクティス](../technical-guides/best-practices-for-disaster-recovery.md)です。  
  
> [!NOTE]  
>  Microsoft[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]と[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]データベースが使用可能なである確率を高めるためのデータベース ミラーリングと呼ばれるソフトウェア ソリューションを提供します。 使用[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースがミラー化されていない、Microsoft の高可用性を確保するためのサポートされているソリューション[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースでトランザクションの一貫性を維持する潜在的な問題があるため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。  
>   
>  データベース ミラーリングとデータベースにまたがるトランザクションの詳細については[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]を参照してください[http://go.microsoft.com/fwlink/?LinkId=87977](http://go.microsoft.com/fwlink/?LinkId=87977)です。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースをインストールする必要があります、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]災害復旧の目的には、高可用性を確保して、ログ配布にクラスターを利用する必要があります。  
>   
>  ログ配布の詳細については、次を参照してください[新機能は、BizTalk Server ログ配布しますか?。](../technical-guides/what-is-biztalk-server-log-shipping.md)  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk Server Databases2 をクラスタ リング](../technical-guides/clustering-the-biztalk-server-databases2.md)  
  
-   [BizTalk Server データベースのスケール アウト](../technical-guides/scaling-out-the-biztalk-server-databases.md)  
  
## <a name="see-also"></a>参照  
 [高 Availability2 の計画](../technical-guides/planning-for-high-availability2.md)   
 [BizTalk ホストの高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)   
 [マスター シークレット サーバーの高可用性](../technical-guides/high-availability-for-the-master-secret-server.md)   
 [災害復旧](../technical-guides/disaster-recovery.md)