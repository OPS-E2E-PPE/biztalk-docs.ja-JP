---
title: 'チェックリスト: SQL Server の構成 |Microsoft ドキュメント'
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
ms.openlocfilehash: 8f6c67fcdee26afd6ec9bb1016e86a98b1cf26e8
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010291"
---
# <a name="checklist-configuring-sql-server"></a>チェックリスト: SQL Server を構成します。
用の SQL Server を準備するときに実行する手順は、BizTalk Server の実稼働環境で使用します。    
 
<a name="BKMK_Config"></a>   
## <a name="configuring-sql-server"></a>SQL Server の構成  
  
|手順|リファレンス|  
|-----------|---------------|  
|監視し、BizTalk Server データベース ファイル ディスク I/O の競合を削減します。|事前対応的に、データ ファイルとトランザクション ログ ファイルを格納するディスクのディスク I/O の使用状況を監視することをお勧めします。<br />-ことをお勧め、データ ファイルとトランザクション ログ ファイルを問題になるディスク I/O の競合の可能性を減らすために専用のドライブに配置するこれらの各します。<br />データベース ファイルとトランザクション ログ ファイルの異なる物理ディスクを分離することと、メッセージ ボックスと追跡 (DTA) データベースを分離することによってディスク I/O の競合を減らす-ことができます。<br /><br /> 詳細については、次を参照してください[監視およびデータベース入出力の競合を減らす。](monitoring-and-reducing-database-i-o-contention.md)|  
|SQL Server が適切にアライン ディスク パーティションの構成を確認してください。|ディスクのパーティションは、SQL Server のパフォーマンスがさらに BizTalk Server のパフォーマンスを向上し、向上させる待機時間が大幅に低下、可能性がありますを適切にアラインします。 反対に、固定されていないディスク パーティションに悪影響を与える I/O パフォーマンス、SQL Server と BizTalk Server のパフォーマンスが低下します。<br /><br /> どのように適切に配置されたディスク パーティションの詳細については、パフォーマンスに大きな影響を与えることができますを参照してください[SQL Server のディスク パーティションの配置のベスト プラクティス](http://go.microsoft.com/fwlink/?LinkId=154073)です。|  
|SQL Server Profiler を使用して監視するイベントを保持します。|関心があるイベントだけを監視するのにには、SQL Server Profiler を使用します。 トレースが必要になる大きすぎる場合、イベント データのサブセットのみが収集できるように、必要な情報に基づいてフィルター処理できます。 監視するイベントが多すぎると、サーバーと監視プロセスのオーバーヘッドが増え、トレース ファイルやトレース テーブルが非常に大きくなる可能性があります。特に、監視プロセスを長期にわたって実行する場合はこの可能性が高くなります。|  
|監視し、DTC ログ ファイル ディスク I/O の競合を削減します。|[監視とログ ファイルのディスク IO の競合の DTC の削減](monitoring-and-reducing-dtc-log-file-disk-i-o-contention.md)|  
|SQL Server データベースの高可用性を実現します。|[データベース可用性の計画](planning-for-database-availability.md)|  
|フェールオーバーのシナリオにアクティブ/アクティブの SQL Server クラスター構成を確認します。|[フェールオーバー シナリオに備えた SQL Server クラスター構成のレビューとテスト](reviewing-and-testing-sql-server-cluster-configuration-for-failover-scenarios.md)|  
|既定の構成設定を使用します。<br /><br /> Max Degree of Parallelism (MDOP)。<br />BizTalk Server メッセージ ボックス データベースで SQL Server 統計情報です。<br />SQL Server データベースのインデックス再構築と最適化します。|[変更しない SQL Server の設定](sql-server-settings-that-should-not-be-changed.md)|  
|SQL Server のすべてのインスタンスの起動時のパラメーターとしてトレース フラグ 1118 (TF1118) を有効にします。|TF1118 を実装することは、ほとんどすべての単一のページ割り当てを削除することで、SQL Server インスタンス間で競合を減らすのに役立ちます。 詳細については「マイクロソフト サポート技術情報の記事[tempdb データベースの同時実行制御の機能強化](https://support.microsoft.com/en-us/help/328551/concurrency-enhancements-for-the-tempdb-database)です。 <br/><br/>**注:** TF1118 参照の詳細については[TF1118 周囲誤解](https://www.sqlskills.com/blogs/paul/misconceptions-around-tf-1118/)です。 Microsoft は、次のリンクでコンテンツを所有していない、Microsoft は、コンテンツの正確性を保証していないことに注意してください。|  
|Tempdb データベースを同じサイズの BizTalk Server で使用される各 SQL Server インスタンス上の複数のデータ ファイルに分割します。|Tempdb に使用されるデータ ファイルと同じサイズのことを確認します。 SQL Server で使用される比例アルゴリズムは、データ ファイルのサイズに基づいているために、このことが重要です。 サイズの異なるデータ ファイルが作成比例アルゴリズムは複数作成する無意味にそれによって、すべてのファイル間での割り当てを展開するのではなく、グローバル アロケーション マップ (GAM) の割り当ての最も大きいファイルを使用します。データ ファイル。 一般的なガイドラインとして、サーバー上の各 CPU の 1 つのデータ ファイルを作成および必要に応じて上または下のファイルの数を調整します。 デュアルコア CPU は 2 つの CPU と見なされることに注意してください。 いかなる場合においては、データ ファイルの数を追加コアの数は、コンピューターで使用できるに関係なく 8 より大きい必要がありますできません。 Tempdb ファイルの詳細については、次を参照してください。 [tempdb のパフォーマンスを最適化する](https://docs.microsoft.com/sql/relational-databases/databases/tempdb-database)です。|  
|最小値を設定し、SQL Server で同じ値に最大サーバー メモリ instance(s)、BizTalk Server データベースをホストするします。|ホストする SQL Server を実行するコンピューター、BizTalk Server データベースは、SQL Server を実行する専用必要があります。 ホストする SQL Server を実行するコンピューター、BizTalk Server データベース場合**は**SQL Server を実行する専用、ことをお勧め、'min server memory' と 'max server memory' を指定する各 SQL Server インスタンス上のオプションを設定します。SQL Server に割り当てるメモリの固定量。 ここでは、する必要があります、'min server memory' と 'max server memory'、同じ値に設定 (SQL Server が使用される物理メモリの最大量に等しい)。 これが減少それ以外の場合にこれらの値を動的に管理する SQL Server で使用されるオーバーヘッドです。 SQL Server に割り当てるメモリの固定量を指定する SQL Server を実行する各コンピューターで、次の T-SQL コマンドを実行します。<br /><br /> sp_configure 'Max Server memory (MB)'、(最大サイズ (MB) sp_configure '最小サーバー メモリ (MB)' (最小サイズ (MB)<br /><br /> SQL Server のメモリの量を設定すると、前に、合計物理メモリから Windows Server に必要なメモリを差し引くことで適切なメモリ設定を決定します。 これは、SQL Server に割り当てるメモリの最大量です。 **注:** 場合は、トピックの説明に従って、BizTalk Server データベースもホストする SQL Server を実行するコンピューターが、エンタープライズ シングル サインオン マスター シークレットをホスト[マスター シークレット サーバーをクラスタ リング](clustering-the-master-secret-server.md)したい場合がありますエンタープライズ シングル サインオン サービスを実行可能にするための十分なメモリがあることを確認するには、この値を調整します。|  
|BizTalk 追跡データベースのサイズをアカウントします。|-メッセージを BizTalk 追跡 (DTA) データベースのサイズを決定するとき、メッセージ コンテキストの平均サイズを追加メッセージのサイズ重要である場合メッセージ サイズと比較します。<br />、BizTalk 追跡データベース内のメッセージのサイズを制限するためには昇格したプロパティの数を制限します。<br />オーケストレーション デバッガーのオプションが有効になっている場合は、オーケストレーション内の各図形の状態は、BizTalk 追跡データベースに保存されているを考慮します。|  
  
<a name="BKMK_Maintain"></a>   
## <a name="performing-sql-server-maintenance-procedures"></a>SQL Server のメンテナンスの手順を実行します。  
  
|手順|リファレンス|  
|-----------|---------------|  
|BizTalk Server データベースの自動拡張設定を定義します。|データベースの自動拡張は、特に、メッセージ ボックス データベースおよび追跡データベースのパーセンテージではなくメガバイト数が固定に設定する必要があります。 BizTalk Server アプリケーションとスループット、に応じて、メッセージ ボックス データベースおよび追跡データベースを非常に大きい取得できます。 自動拡張設定されている場合、このパーセンテージを自動拡張がかなり大きくなる場合もします。<br />ファイルのインスタント初期化では、ファイルの拡張操作のパフォーマンスに与える影響を大幅に減らすことができます。<br />-理想的には、ファイル グループをサポートするファイルのサイズを事前に割り当てられるし、可能な場合は、静的なサイズに設定する必要があります。<br /><br /> 詳細については、次を参照してください。[データベースの自動拡張設定を定義する](defining-auto-growth-settings-for-databases.md)です。|  
|BizTalk Server データベースをバックアップします。|-BizTalk Server データベースのトランザクション ログがバインド解除済みの方法で増加するを防ぐために、BizTalk Server のバックアップ ジョブを実行していることをお勧めします。<br />-定期的に BizTalk Server 環境全体を復元する必要がありますして、プロセスを慎重に文書化する必要があります。<br />古いバックアップ ファイルをアーカイブすることをお勧めします。<br /><br /> 詳細については、次を参照してください。[データベースのバックアップ](backing-up-databases.md)です。|  
|BizTalk Server の SQL エージェント ジョブを監視します。|これらのジョブの状態を監視して、エラーなく実行されていることを確認してください。 詳細については、次を参照してください。 [SQL Server エージェント ジョブの監視](monitoring-sql-server-agent-jobs.md)です。|  
|BizTalk Server 追跡およびアーカイブを有効にします。|「DTA の消去およびアーカイブ」SQL エージェント ジョブは、アーカイブして、コントロールから拡張されないように、BizTalk 追跡データベースから古いデータを削除します。 これは、正常な BizTalk Server システムの不可欠な部分です。 詳細については、次を参照してください。[消去および追跡データのアーカイブ](purging-and-archiving-tracking-data.md)です。|  
  
<a name="BKMK_Backup"></a>   
## <a name="backing-up-the-biztalk-server-databases"></a>BizTalk Server データベースのバックアップ  
  
|手順|リファレンス|  
|-----------|---------------|  
|Backup BizTalk Server の SQL エージェント ジョブが構成されていることを確認します。|参照してください[バックアップの BizTalk Server のジョブを構成します。](../core/how-to-configure-the-backup-biztalk-server-job.md)|  
|指定された日数よりも古いバックアップ ファイルを削除する Backup BizTalk Server の SQL エージェント ジョブを構成、@DaysToKeep変数。 バックアップ ファイルが削除されていない場合よりも大きくなる unbounded バックアップ ファイルを保存し、限定されたディスク容量に関連する問題が発生したディスクがいっぱいになる時間。|参照してください[バックアップの BizTalk Server のジョブを構成します。](../core/how-to-configure-the-backup-biztalk-server-job.md)|  
|Backup BizTalk Server の SQL エージェント ジョブが有効で実行中であることを確認します。|[SQL Server エージェント ジョブの監視](monitoring-sql-server-agent-jobs.md)|  
  
<a name="BKMK_Disaster"></a>   
## <a name="using-sql-server-log-shipping-for-disaster-recovery"></a>SQL Server ログ配布の障害復旧を使用します。  
  
|手順|リファレンス|  
|-----------|---------------|  
|障害回復サーバーに実稼働負荷を処理する能力があることを確認します。|参照してください[BizTalk Server のログ配布災害復旧を使用します。](using-biztalk-server-log-shipping-for-disaster-recovery.md)|  
|災害復旧ルーチンの詳細が明確になっていることを確認します。|参照してください[BizTalk Server のログ配布災害復旧を使用します。](using-biztalk-server-log-shipping-for-disaster-recovery.md)|  
|障害復旧サイトに通常のテスト、プラクティス フェールオーバーの一環として、新しい BizTalk として特にアプリケーションが配置実稼働環境でします。|参照してください[BizTalk Server のログ配布災害復旧を使用します。](using-biztalk-server-log-shipping-for-disaster-recovery.md)|  
  
<a name="BKMK_Jobs"></a>   
## <a name="monitoring-biztalk-server-sql-agent-jobs"></a>BizTalk Server SQL エージェント ジョブの監視  
  
|手順|リファレンス|  
|-----------|---------------|  
|SQL Server エージェント サービスが実行されていることを確認します。|参照してください[SQL Server エージェント ジョブの監視](monitoring-sql-server-agent-jobs.md)|  
|BizTalk Server によってインストールされる SQL Server エージェント ジョブが実行されていて正常に確認します。|参照してください[SQL Server エージェント ジョブの監視](monitoring-sql-server-agent-jobs.md)|  
|適切なタイミングで、BizTalk Server の SQL エージェント ジョブが完了することを確認します。|参照してください[SQL Server エージェント ジョブの監視](monitoring-sql-server-agent-jobs.md)|  
  
<a name="BKMK_Purge"></a>   
## <a name="purging-and-archiving-tracking-data"></a>消去および追跡データをアーカイブ  
  
|手順|リファレンス|  
|-----------|---------------|  
|SQL エージェント ジョブ「DTA の消去およびアーカイブ」が適切に構成された、有効であり、正常に完了することを確認します。|参照してください[構成 DTA Purge and Archive ジョブ](../core/how-to-configure-the-dta-purge-and-archive-job.md)です。|  
|ジョブが、受信追跡データが生成された高速の追跡データが削除できることを確認します。|参照してください[維持可能な最大の追跡スループットの測定](../core/measuring-maximum-sustainable-tracking-throughput.md)|  
|論理削除と物理削除ようにパラメーターを最適な時間の長さのデータを保持している場合を確認します。|参照してください[アーカイブ化および BizTalk 追跡データベースを削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)です。|  
|だけ古いデータを削除しないようにする必要がある場合必要があります、最初の変更をアーカイブする SQL エージェント ジョブ、ストアド プロシージャを呼び出す"dtasp_PurgeTrackingDatabase"|参照してください[BizTalk 追跡データベースからデータを削除](../core/how-to-purge-data-from-the-biztalk-tracking-database.md)です。|  
  
## <a name="next"></a>Next
  
-   [変更しない SQL Server の設定](sql-server-settings-that-should-not-be-changed.md)  
  
-   [監視およびデータベース入出力の競合を減らす](monitoring-and-reducing-database-i-o-contention.md)  
  
-   [フェールオーバー シナリオに備えた SQL Server クラスター構成のレビューとテスト](reviewing-and-testing-sql-server-cluster-configuration-for-failover-scenarios.md)  
  
-   [データベースの自動拡張設定の定義](defining-auto-growth-settings-for-databases.md)  
  
-   [データベースのバックアップ](backing-up-databases.md)  
  
-   [ディザスター リカバリーのための BizTalk Server ログ配布の使用](using-biztalk-server-log-shipping-for-disaster-recovery.md)  
  
-   [SQL Server エージェント ジョブの監視](monitoring-sql-server-agent-jobs.md)  
  
-   [追跡データの削除とアーカイブ](purging-and-archiving-tracking-data.md)