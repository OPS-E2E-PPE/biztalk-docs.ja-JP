---
title: チェックリスト:SQL Server の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: edd20f24-8a72-40b7-abee-81fbd3ceefda
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11ddb15c9086d8aeadf65da399a99598ae91a895
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291460"
---
# <a name="checklist-configuring-sql-server"></a>チェックリスト:SQL Server の構成
用の SQL Server を準備するときに実行する手順は、BizTalk Server の運用環境で使用します。    
 
<a name="BKMK_Config"></a>   
## <a name="configuring-sql-server"></a>SQL Server の構成  
  
|手順|リファレンス|  
|-----------|---------------|  
|監視し、BizTalk Server データベース ファイル ディスク I/O の競合を削減します。|-は、事前にデータとトランザクション ログ ファイルを格納するディスクのディスク I/O の使用状況を監視することお勧めします。<br />-推奨されるデータ ファイルとトランザクション ログ ファイルの問題になるディスク I/O の競合の可能性を低減する専用のドライブに配置するこれらの各します。<br />データベース ファイルとトランザクション ログ ファイルの異なる物理ディスクを分離することと、メッセージ ボックスおよび追跡 (DTA) データベースを分離することによって、ディスク I/O の競合を削減-できます。<br /><br /> 詳細については、次を参照してください[監視とデータベースの IO 競合の削減。](monitoring-and-reducing-database-i-o-contention.md)|  
|SQL Server が正しく調整のディスク パーティション上に構成されていることを確認します。|ディスク パーティションがさらに、BizTalk Server のパフォーマンスが向上する SQL Server のパフォーマンスが向上する待機時間の大幅な削減になる可能性がありますが正しく調整します。 反対に、固定されていないディスク パーティションには、I/O パフォーマンス、SQL Server と BizTalk Server のパフォーマンスが低下できます低下します。<br /><br /> どのように適切に配置されたディスク パーティションの詳細については、パフォーマンスに大きな影響を与えることができます、参照してください[SQL Server のディスク パーティションの配置のベスト プラクティス](http://go.microsoft.com/fwlink/?LinkId=154073)します。|  
|SQL Server Profiler を使用して監視するイベントを保持します。|これで必要なイベントのみを監視するのにには、SQL Server Profiler を使用します。 トレースが大きくなりすぎた、イベント データのサブセットのみが収集されるように表示情報に基づいたがフィルター処理できます。 監視するイベントが多すぎると、サーバーと監視プロセスのオーバーヘッドが増え、トレース ファイルやトレース テーブルが非常に大きくなる可能性があります。特に、監視プロセスを長期にわたって実行する場合はこの可能性が高くなります。|  
|監視し、DTC ログ ファイルのディスク I/O の競合を削減します。|[監視と DTC ログ ファイルのディスク IO の競合を軽減](monitoring-and-reducing-dtc-log-file-disk-i-o-contention.md)|  
|SQL Server データベースの高可用性を提供します。|[データベース可用性の計画](planning-for-database-availability.md)|  
|フェールオーバーのシナリオにアクティブ/アクティブ SQL Server クラスターの構成を確認します。|[フェールオーバー シナリオに備えた SQL Server クラスター構成のレビューとテスト](reviewing-and-testing-sql-server-cluster-configuration-for-failover-scenarios.md)|  
|既定の構成設定を使用します。<br /><br /> 並列処理 (MDOP) の最大次数。<br />、BizTalk Server メッセージ ボックス データベースで SQL Server の統計。<br />-SQL Server データベースのインデックス再構築し、最適化します。|[変更しない SQL Server の設定](sql-server-settings-that-should-not-be-changed.md)|  
|SQL Server のすべてのインスタンスの起動時のパラメーターとしてトレース フラグ 1118 (TF1118) を有効にします。|TF1118 を実装する、ほぼすべての単一ページの割り当てを削除することで、SQL Server インスタンス間で競合を軽減できます。 詳細については「マイクロソフト サポート技術情報の記事[tempdb データベースの同時実行制御の強化](https://support.microsoft.com/en-us/help/328551/concurrency-enhancements-for-the-tempdb-database)します。 <br/><br/>**注:** TF1118 の詳細については、次を参照してください。 [TF1118 誤解](https://www.sqlskills.com/blogs/paul/misconceptions-around-tf-1118/)します。 このリンクにあるコンテンツが Microsoft によって所有されていないと、Microsoft は、コンテンツの精度を保証しないことに注意してください。|  
|Tempdb データベースを BizTalk Server で使用される各 SQL Server インスタンスに等しいサイズの複数のデータ ファイルに分割します。|Tempdb に使用されるデータ ファイルと同じサイズのことを確認します。 SQL Server で使用される、比例書き込みアルゴリズムは、データ ファイルのサイズに基づいているために、このことが重要です。 比例書き込みアルゴリズムは、最も大きなファイルを複数作成する目的にそぐわなくなりますそれによって、すべてのファイルに割り当てのではなく、グローバル アロケーション マップ (GAM) の割り当ての詳細についてを使用して、サイズの異なるデータ ファイルを作成する場合データ ファイル。 一般的なガイドラインとして、サーバー上の各 CPU の 1 つのデータ ファイルを作成し、必要に応じてアップまたはスケール ダウンのファイルの数を調整します。 デュアル コア CPU が 2 つの Cpu があると見なされることに注意してください。 いずれの場合も、データ ファイルの数を追加のコア数は、コンピューターに関係なく 8 より大きい必要がありますできません。 Tempdb ファイルの詳細については、次を参照してください。 [tempdb のパフォーマンスを最適化する](https://docs.microsoft.com/sql/relational-databases/databases/tempdb-database)します。|  
|最小値を設定し、インスタンスをホストする BizTalk Server データベースの最大サーバー メモリ、SQL Server の同じ値にします。|ホストする SQL Server を実行するコンピューター、BizTalk Server データベースを SQL Server を実行する専用必要があります。 ときにコンピューターをホストする SQL Server を実行して、BizTalk Server データベース**は**専用の SQL Server を実行していることをお勧め 'min server memory' と 'max server memory' を指定する各 SQL Server インスタンス上のオプションを設定します。SQL Server に割り当てるメモリの固定量。 この場合、する必要があります設定する 'min server memory' と 'max server memory' に同じ値 (SQL Server を使用する物理メモリの最大量に等しい)。 これが減少オーバーヘッドはそれ以外の場合これらの値を動的に管理する SQL Server によって使用されます。 SQL Server に割り当てるメモリの固定量を指定する SQL Server を実行している各コンピューターで、次の T-SQL コマンドを実行します。<br /><br /> sp_configure 'Max Server memory (MB)'、(最大サイズ (mb)) sp_configure 'Min Server memory (MB)' (最小サイズ (mb))<br /><br /> SQL Server のメモリの量を設定する前に、Windows Server に必要な合計物理メモリからメモリを差し引くことで、適切なメモリ設定を決定します。 これは、SQL Server に割り当てるメモリの最大量です。 **注:** 場合は、トピックの説明に従って、BizTalk Server データベースもホストする SQL Server を実行するコンピューターが、エンタープライズ シングル サインオン マスター シークレットをホスト[マスター シークレット サーバーをクラスタ リング](clustering-the-master-secret-server.md)し、この値を調整する必要がありますエンタープライズ シングル サインオン サービスの実行可能にするための十分なメモリがあることを確認します。|  
|BizTalk 追跡データベースのサイズをアカウントします。|-メッセージを BizTalk 追跡 (DTA) データベースのサイズを決定するには、ときにメッセージ コンテキストの平均サイズに追加メッセージのサイズが大幅にある場合メッセージ サイズと比較します。<br />、BizTalk 追跡データベース内のメッセージのサイズを制限するには昇格したプロパティの数を制限します。<br />-オーケストレーション デバッガーのオプションが有効になっている場合は、オーケストレーション内の各図形の状態は、BizTalk 追跡データベースに保存されているアカウントを考慮します。|  
  
<a name="BKMK_Maintain"></a>   
## <a name="performing-sql-server-maintenance-procedures"></a>SQL Server のメンテナンスの手順を実行します。  
  
|手順|リファレンス|  
|-----------|---------------|  
|BizTalk Server データベースの自動拡張設定を定義します。|データベース自動拡張は、特にメッセージ ボックス データベースおよび追跡データベースの固定数のパーセンテージではなく、メガバイト単位に設定する必要があります。 BizTalk Server アプリケーションとスループットに応じて、メッセージ ボックス データベースと追跡データベースを非常に大きく取得できます。 自動拡張がパーセンテージに設定されている場合、自動拡張できます大幅もあります。<br />のファイル瞬時初期化は、ファイルの拡張操作のパフォーマンスに与える影響を大幅に削減できます。<br />-理想的には、ファイル グループをサポートしているファイルのサイズを事前に割り当てられるし、可能な場合は、静的なサイズに設定する必要があります。<br /><br /> 詳細については、次を参照してください。[データベースの自動拡張設定を定義する](defining-auto-growth-settings-for-databases.md)します。|  
|BizTalk Server データベースをバックアップします。|-は、BizTalk Server データベースのトランザクション ログが無制限で拡大するを防ぐために BizTalk Server のバックアップ ジョブを実行しているお勧めします。<br />-慎重にプロセスを文書化する必要があり、を定期的に、BizTalk Server 環境全体を復元する必要があります。<br />-は、古いバックアップ ファイルをアーカイブすることお勧めします。<br /><br /> 詳細については、次を参照してください。[データベースのバックアップ](backing-up-databases.md)します。|  
|BizTalk Server は SQL エージェント ジョブを監視します。|これらのジョブの状態を監視し、エラーなく実行されていることを確認します。 詳細については、次を参照してください。 [SQL Server エージェント ジョブの監視](monitoring-sql-server-agent-jobs.md)します。|  
|BizTalk Server 追跡およびアーカイブを有効にします。|「DTA の消去およびアーカイブ」の SQL エージェント ジョブをアーカイブしてからほど大きく抑える、BizTalk 追跡データベースから古いデータを削除します。 これは、正常な BizTalk Server システムに不可欠です。 詳細については、次を参照してください。[消去および追跡データのアーカイブ](purging-and-archiving-tracking-data.md)します。|  
  
<a name="BKMK_Backup"></a>   
## <a name="backing-up-the-biztalk-server-databases"></a>BizTalk Server データベースをバックアップします。  
  
|手順|リファレンス|  
|-----------|---------------|  
|バックアップ BizTalk Server は SQL エージェント ジョブが構成されていることを確認します。|参照してください[バックアップ BizTalk Server ジョブを構成します。](../core/how-to-configure-the-backup-biztalk-server-job.md)|  
|指定された日数より古いバックアップ ファイルを削除するバックアップ BizTalk Server は SQL エージェント ジョブを構成、@DaysToKeep変数。 バックアップ ファイルが削除されない場合ディスク容量が制限に関連する問題になり、バックアップ ファイルが含まれているディスクがいっぱいにする時間の経過と共に unbounded できます拡張します。|参照してください[バックアップ BizTalk Server ジョブを構成します。](../core/how-to-configure-the-backup-biztalk-server-job.md)|  
|バックアップ BizTalk Server は SQL エージェント ジョブが有効で実行されていることを確認します。|[SQL Server エージェント ジョブの監視](monitoring-sql-server-agent-jobs.md)|  
  
<a name="BKMK_Disaster"></a>   
## <a name="using-sql-server-log-shipping-for-disaster-recovery"></a>SQL Server ログ配布のディザスター リカバリーを使用します。  
  
|手順|リファレンス|  
|-----------|---------------|  
|ディザスター リカバリー server に運用環境の負荷を処理する能力があることを確認します。|参照してください[BizTalk Server ログ配布のディザスター リカバリーを使用します。](using-biztalk-server-log-shipping-for-disaster-recovery.md)|  
|ディザスター リカバリ ルーチンの詳細がも記載されていることを確認します。|参照してください[BizTalk Server ログ配布のディザスター リカバリーを使用します。](using-biztalk-server-log-shipping-for-disaster-recovery.md)|  
|ディザスター リカバリー サイトに通常のテスト、実際にフェールオーバーの一環として、新しい BizTalk として特にアプリケーションが配置実稼働環境でします。|参照してください[BizTalk Server ログ配布のディザスター リカバリーを使用します。](using-biztalk-server-log-shipping-for-disaster-recovery.md)|  
  
<a name="BKMK_Jobs"></a>   
## <a name="monitoring-biztalk-server-sql-agent-jobs"></a>BizTalk Server SQL エージェント ジョブの監視  
  
|手順|リファレンス|  
|-----------|---------------|  
|SQL Server エージェント サービスが実行されていることを確認します。|参照してください[SQL Server エージェント ジョブの監視](monitoring-sql-server-agent-jobs.md)|  
|BizTalk Server によってインストールされる SQL Server エージェント ジョブが実行されていて正常に確認します。|参照してください[SQL Server エージェント ジョブの監視](monitoring-sql-server-agent-jobs.md)|  
|適切なタイミングで、BizTalk Server の SQL エージェント ジョブが完了することを確認します。|参照してください[SQL Server エージェント ジョブの監視](monitoring-sql-server-agent-jobs.md)|  
  
<a name="BKMK_Purge"></a>   
## <a name="purging-and-archiving-tracking-data"></a>削除とアーカイブ データの追跡  
  
|手順|リファレンス|  
|-----------|---------------|  
|SQL エージェント ジョブ「DTA の消去およびアーカイブ」が適切に構成された、有効化、および正常に完了することを確認します。|参照してください[構成 DTA Purge and Archive ジョブ](../core/how-to-configure-the-dta-purge-and-archive-job.md)します。|  
|ジョブが追跡データを受信した追跡データが生成された高速消去できることを確認します。|参照してください[維持可能な最大の追跡スループットの測定](../core/measuring-maximum-sustainable-tracking-throughput.md)|  
|論理削除と時間の最適な長さのデータを保持することを確認する物理削除パラメーターを確認します。|参照してください[アーカイブおよび BizTalk 追跡データベースの削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)します。|  
|古いデータを消去しないだけの場合必要があります、最初の変更を保存する SQL エージェント ジョブ"dtasp_PurgeTrackingDatabase"ストアド プロシージャを呼び出す|参照してください[BizTalk 追跡データベースからデータを削除](../core/how-to-purge-data-from-the-biztalk-tracking-database.md)します。|  
  
## <a name="next"></a>Next
  
-   [変更しない SQL Server の設定](sql-server-settings-that-should-not-be-changed.md)  
  
-   [監視とデータベースの IO の競合を軽減](monitoring-and-reducing-database-i-o-contention.md)  
  
-   [フェールオーバー シナリオに備えた SQL Server クラスター構成のレビューとテスト](reviewing-and-testing-sql-server-cluster-configuration-for-failover-scenarios.md)  
  
-   [データベースの自動拡張設定の定義](defining-auto-growth-settings-for-databases.md)  
  
-   [データベースのバックアップ](backing-up-databases.md)  
  
-   [ディザスター リカバリーのための BizTalk Server ログ配布の使用](using-biztalk-server-log-shipping-for-disaster-recovery.md)  
  
-   [SQL Server エージェント ジョブの監視](monitoring-sql-server-agent-jobs.md)  
  
-   [追跡データの削除とアーカイブ](purging-and-archiving-tracking-data.md)