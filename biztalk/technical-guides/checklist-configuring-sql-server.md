---
title: "チェックリスト: SQL Server の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: edd20f24-8a72-40b7-abee-81fbd3ceefda
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce0eff1dab6afe81c55f4cffa08c4839762e82ea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-configuring-sql-server"></a>チェックリスト: SQL Server を構成します。
このトピックを準備する際に従う必要のある手順について説明[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]または[!INCLUDE[btsSQLServer2005](../includes/btssqlserver2005-md.md)]で使用するため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実稼働環境。  
  
-   [チェックリスト: SQL Server を構成します。](../technical-guides/checklist-configuring-sql-server.md)  
  
-   [SQL Server のメンテナンスの手順を実行します。](../technical-guides/checklist-configuring-sql-server.md#BKMK_Maintain)  
  
-   [BizTalk Server データベースのバックアップ](../technical-guides/checklist-configuring-sql-server.md#BKMK_Backup)  
  
-   [SQL Server ログ配布の障害復旧を使用します。](../technical-guides/checklist-configuring-sql-server.md#BKMK_Disaster)  
  
-   [BizTalk Server SQL エージェント ジョブの監視](../technical-guides/checklist-configuring-sql-server.md#BKMK_Jobs)  
  
-   [消去および追跡データをアーカイブ](../technical-guides/checklist-configuring-sql-server.md#BKMK_Purge)  
  
<a name="BKMK_Config"></a>   
## <a name="configuring-sql-server"></a>SQL Server の構成  
  
|手順|リファレンス|  
|-----------|---------------|  
|監視し、削減[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース ファイルのディスク I/O の競合。|事前対応的に、データ ファイルとトランザクション ログ ファイルを格納するディスクのディスク I/O の使用状況を監視することをお勧めします。<br />-ことをお勧め、データ ファイルとトランザクション ログ ファイルを問題になるディスク I/O の競合の可能性を減らすために専用のドライブに配置するこれらの各します。<br />データベース ファイルとトランザクション ログ ファイルの異なる物理ディスクを分離することと、メッセージ ボックスと追跡 (DTA) データベースを分離することによってディスク I/O の競合を減らす-ことができます。<br /><br /> 詳細については、次を参照してください[監視およびデータベース入出力の競合を減らす。](~/technical-guides/monitoring-and-reducing-database-i-o-contention.md)|  
|確認[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]が適切にアライン ディスク パーティションに構成されています。|適切に配置されたディスク パーティションを向上させるための待機時間が大幅に低下が生じる、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 、パフォーマンスがさらに向上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パフォーマンス。 反対に、固定されていないディスク パーティションに悪影響を与える I/O パフォーマンス、低下、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]と[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パフォーマンス。<br /><br /> どのように適切に配置されたディスク パーティションの詳細については、パフォーマンスに大きな影響を与えることができますを参照してください["ディスク パーティションの配置ベスト プラクティスの SQL Server"](http://go.microsoft.com/fwlink/?LinkId=154073) (http://go.microsoft.com/fwlink/?LinkId=154073)。|  
|SQL Server Profiler を使用して監視するイベントを保持します。|関心があるイベントだけを監視するのにには、SQL Server Profiler を使用します。 トレースが必要になる大きすぎる場合、イベント データのサブセットのみが収集できるように、必要な情報に基づいてフィルター処理できます。 監視するイベントが多すぎると、サーバーと監視プロセスのオーバーヘッドが増え、トレース ファイルやトレース テーブルが非常に大きくなる可能性があります。特に、監視プロセスを長期にわたって実行する場合はこの可能性が高くなります。|  
|監視し、DTC ログ ファイル ディスク I/O の競合を削減します。|[監視とログ ファイルのディスク IO の競合の DTC の削減](~/technical-guides/monitoring-and-reducing-dtc-log-file-disk-i-o-contention.md)|  
|高い可用性を実現、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース。|[データベースの可用性の計画](~/technical-guides/planning-for-database-availability.md)|  
|フェールオーバーのシナリオにアクティブ/アクティブの SQL Server クラスター構成を確認します。|[レビューし、テスト フェールオーバーのシナリオに SQL Server クラスターの構成](~/technical-guides/reviewing-and-testing-sql-server-cluster-configuration-for-failover-scenarios.md)|  
|既定の構成設定を使用します。<br /><br /> Max Degree of Parallelism (MDOP)。<br />-   [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]統計情報、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックス データベースです。<br />-   [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースのインデックス再構築と最適化します。|[SQL Server の設定を変更しないでください。](~/technical-guides/sql-server-settings-that-should-not-be-changed.md)|  
|すべてのインスタンスの起動時のパラメーターとしてトレース フラグ 1118 (TF1118) を有効にする[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。|間で競合を減らし、TF1118 を実装する、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ほとんどすべての単一のページ割り当てを削除することでインスタンス。 詳細については「マイクロソフト サポート技術情報の記事 328551、 ["同時実行の tempdb データベースの機能強化"](http://go.microsoft.com/fwlink/?LinkId=153694) (http://go.microsoft.com/fwlink/?LinkId=153694)。 **注:** TF1118 参照の詳細については["誤解周囲 TF1118"](http://go.microsoft.com/fwlink/?LinkId=158271) (http://go.microsoft.com/fwlink/?LinkId=158271)。 Microsoft は、次のリンクでコンテンツを所有していない、Microsoft は、コンテンツの正確性を保証していないことに注意してください。|  
|Tempdb データベースをそれぞれに等しいサイズの複数のデータ ファイルに分割[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスによって使用される[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。|Tempdb に使用されるデータ ファイルと同じサイズのことを確認します。 これは重要な比例アルゴリズムで使用[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データ ファイルのサイズに基づきます。 サイズの異なるデータ ファイルが作成比例アルゴリズムは複数作成する無意味にそれによって、すべてのファイル間での割り当てを展開するのではなく、グローバル アロケーション マップ (GAM) の割り当ての最も大きいファイルを使用します。データ ファイル。 一般的なガイドラインとして、サーバー上の各 CPU の 1 つのデータ ファイルを作成および必要に応じて上または下のファイルの数を調整します。 デュアルコア CPU は 2 つの CPU と見なされることに注意してください。 いかなる場合においては、データ ファイルの数を追加コアの数は、コンピューターで使用できるに関係なく 8 より大きい必要がありますできません。 Tempdb ファイルの詳細については、次を参照してください。 [tempdb のパフォーマンスを最適化する](http://go.microsoft.com/fwlink/?LinkId=158272)(http://go.microsoft.com/fwlink/?LinkId=158272) で、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ドキュメント。|  
|実行している場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実行しているコンピューター上にあるデータベースをホストしていると[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]で十分な物理メモリのインスタンスを構成する[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Address Windowing Extensions (AWE) メモリを使用します。|X86 コンピューター、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 2 GB を超える物理メモリを使用するように構成する必要があります。 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Microsoft Windows Address Windowing Extensions (AWE) を最大 32 GB のメモリをアドレスを使用するためのサポートが含まれます。 AWE で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]他のアプリケーションとオペレーティング システムの使用されていないメモリを予約できます。 ただし、このメモリを使用する各インスタンスは、必要なメモリを割り当てる必要がありますに静的にします。 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データ キャッシュと実行可能ファイル、ドライバー、Dll、およびなどのメモリを割り当てられているこの AWE のみ使用できます。 詳細については、以下をご覧ください。<br /><br /> Microsoft サポート技術情報の記事 274750、 [「2 GB を超える物理メモリを使用する SQL Server を構成する方法」](http://go.microsoft.com/fwlink/?LinkId=153718) (http://go.microsoft.com/fwlink/?LinkId=153718).<br />-   [AWE を使用して](http://go.microsoft.com/fwlink/?LinkId=153720)(http://go.microsoft.com/fwlink/?LinkId=153720) で、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ドキュメント。<br />-   [SQL Server の AWE メモリを有効にする](http://go.microsoft.com/fwlink/?LinkId=158273)(http://go.microsoft.com/fwlink/?LinkId=158273) で、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ドキュメント。|  
|上の同じ値を最小値と最大サーバー メモリの設定、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s) をホストする、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。|実行するコンピューター[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]をホストする、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実行中にデータベースで占有できる必要があります[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。 ときに実行しているコンピューター[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]をホストする、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース**は**を実行する専用[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]、ことをお勧め、'min server memory' と 'max server memory' オプションをそれぞれ[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスに割り当てるメモリの固定量を指定する設定[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。 ここでは、する必要があります、'min server memory' と 'max server memory'、同じ値に設定 (SQL Server が使用される物理メモリの最大量に等しい)。 これが減少してそれ以外の場合に使用されるオーバーヘッド[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]これらの値を動的に管理します。 実行している各コンピューターで、次の T-SQL コマンドを実行[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]に割り当てるメモリの固定量を指定する[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]:<br /><br /> sp_configure 'Max Server memory (MB)'、(最大サイズ (MB) sp_configure '最小サーバー メモリ (MB)' (最小サイズ (MB)<br /><br /> メモリの量を設定する前に[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]、合計物理メモリから Windows Server に必要なメモリを差し引くことで、適切なメモリ設定を決定します。 これは、最大メモリ量を割り当てることができます[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。 **注:**場合を実行するコンピューター[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]をホストする、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースは、トピックの説明に従っても、エンタープライズ シングル サインオン マスター シークレットをホスト[マスター シークレット サーバーをクラスタ リング](~/technical-guides/clustering-the-master-secret-server.md)し、エンタープライズ シングル サインオン サービスを実行可能にするための十分なメモリがあることを確認するには、この値を調整する必要があります。|  
|BizTalk 追跡データベースのサイズをアカウントします。|-メッセージを BizTalk 追跡 (DTA) データベースのサイズを決定するとき、メッセージ コンテキストの平均サイズを追加メッセージのサイズ重要である場合メッセージ サイズと比較します。<br />、BizTalk 追跡データベース内のメッセージのサイズを制限するためには昇格したプロパティの数を制限します。<br />オーケストレーション デバッガーのオプションが有効になっている場合は、オーケストレーション内の各図形の状態は、BizTalk 追跡データベースに保存されているを考慮します。|  
  
<a name="BKMK_Maintain"></a>   
## <a name="performing-sql-server-maintenance-procedures"></a>SQL Server のメンテナンスの手順を実行します。  
  
|手順|リファレンス|  
|-----------|---------------|  
|自動拡張設定を定義、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。|データベースの自動拡張は、特に、メッセージ ボックス データベースおよび追跡データベースのパーセンテージではなくメガバイト数が固定に設定する必要があります。 BizTalk Server アプリケーションとスループット、に応じて、メッセージ ボックス データベースおよび追跡データベースを非常に大きい取得できます。 自動拡張設定されている場合、このパーセンテージを自動拡張がかなり大きくなる場合もします。<br />ファイルのインスタント初期化では、ファイルの拡張操作のパフォーマンスに与える影響を大幅に減らすことができます。<br />-理想的には、ファイル グループをサポートするファイルのサイズを事前に割り当てられるし、可能な場合は、静的なサイズに設定する必要があります。<br /><br /> 詳細については、次を参照してください。[データベースの自動拡張設定を定義する](~/technical-guides/defining-auto-growth-settings-for-databases.md)です。|  
|バックアップを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース|に実行中お勧め、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を防ぐためにバックアップ ジョブ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース トランザクション ログの境界のない方法で拡張します。<br />全体を復元する必要があります-[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を定期的におよび、環境は、プロセスを文書慎重に必要があります。<br />古いバックアップ ファイルをアーカイブすることをお勧めします。<br /><br /> 詳細については、次を参照してください。[データベースのバックアップ](~/technical-guides/backing-up-databases.md)です。|  
|モニター、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SQL エージェント ジョブ。|これらのジョブの状態を監視して、エラーなく実行されていることを確認してください。 詳細については、次を参照してください。 [SQL Server エージェント ジョブの監視](~/technical-guides/monitoring-sql-server-agent-jobs.md)です。|  
|有効にする[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]追跡およびアーカイブ|「DTA の消去およびアーカイブ」SQL エージェント ジョブは、アーカイブして、コントロールから拡張されないように、BizTalk 追跡データベースから古いデータを削除します。 これは、正常なために不可欠な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システムです。 詳細については、次を参照してください。[消去および追跡データのアーカイブ](~/technical-guides/purging-and-archiving-tracking-data.md)です。|  
  
<a name="BKMK_Backup"></a>   
## <a name="backing-up-the-biztalk-server-databases"></a>BizTalk Server データベースのバックアップ  
  
|手順|リファレンス|  
|-----------|---------------|  
|いることを確認、バックアップ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SQL エージェント ジョブを構成します。|-参照[「バックアップの BizTalk Server ジョブを構成する方法」](http://go.microsoft.com/fwlink/?LinkId=153813) (http://go.microsoft.com/fwlink/?LinkId=153813)。<br />-参照[データベースのバックアップ](~/technical-guides/backing-up-databases.md)です。|  
|バックアップを構成する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で指定された日数よりも古いバックアップ ファイルを削除する SQL エージェント ジョブ、@DaysToKeep変数。 バックアップ ファイルが削除されていない場合よりも大きくなる unbounded バックアップ ファイルを保存し、限定されたディスク容量に関連する問題が発生したディスクがいっぱいになる時間。|Microsoft サポート技術情報の記事 982546 を参照してください[バックアップ ファイルが Microsoft BizTalk Dababase server 時間の経過と共に蓄積されるときに、"Backup BizTalk Server"ジョブが失敗した](http://go.microsoft.com/fwlink/?LinkId=202858)(http://go.microsoft.com/fwlink/?LinkId=202858)。|  
|いることを確認、バックアップ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SQL エージェント ジョブが有効で実行中です。|[SQL Server エージェント ジョブの監視](~/technical-guides/monitoring-sql-server-agent-jobs.md)|  
  
<a name="BKMK_Disaster"></a>   
## <a name="using-sql-server-log-shipping-for-disaster-recovery"></a>SQL Server ログ配布の障害復旧を使用します。  
  
|手順|リファレンス|  
|-----------|---------------|  
|障害回復サーバーに実稼働負荷を処理する能力があることを確認します。|参照してください[BizTalk Server のログ配布災害復旧を使用します。](~/technical-guides/using-biztalk-server-log-shipping-for-disaster-recovery.md)|  
|災害復旧ルーチンの詳細が明確になっていることを確認します。|参照してください[BizTalk Server のログ配布災害復旧を使用します。](~/technical-guides/using-biztalk-server-log-shipping-for-disaster-recovery.md)|  
|障害復旧サイトに通常のテスト、プラクティス フェールオーバーの一環として、新しい BizTalk として特にアプリケーションが配置実稼働環境でします。|参照してください[BizTalk Server のログ配布災害復旧を使用します。](~/technical-guides/using-biztalk-server-log-shipping-for-disaster-recovery.md)|  
  
<a name="BKMK_Jobs"></a>   
## <a name="monitoring-biztalk-server-sql-agent-jobs"></a>BizTalk Server SQL エージェント ジョブの監視  
  
|手順|リファレンス|  
|-----------|---------------|  
|SQL Server エージェント サービスが実行されていることを確認します。|参照してください[SQL Server エージェント ジョブの監視](~/technical-guides/monitoring-sql-server-agent-jobs.md)|  
|によって、SQL Server エージェント ジョブがインストールされていることを確認[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が有効で、正常に実行します。|参照してください[SQL Server エージェント ジョブの監視](~/technical-guides/monitoring-sql-server-agent-jobs.md)|  
|いることを確認、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SQL エージェント ジョブは、適切なタイミングで作業を完了します。|参照してください[SQL Server エージェント ジョブの監視](~/technical-guides/monitoring-sql-server-agent-jobs.md)|  
  
<a name="BKMK_Purge"></a>   
## <a name="purging-and-archiving-tracking-data"></a>消去および追跡データをアーカイブ  
  
|手順|リファレンス|  
|-----------|---------------|  
|SQL エージェント ジョブ「DTA の消去およびアーカイブ」が適切に構成された、有効であり、正常に完了することを確認します。|参照してください[「How to 構成 DTA Purge and Archive ジョブ」](http://go.microsoft.com/fwlink/?LinkId=153814) (http://go.microsoft.com/fwlink/?LinkId=153814)。|  
|ジョブが、受信追跡データが生成された高速の追跡データが削除できることを確認します。|参照してください[「維持可能な最大の追跡スループットの測定」](http://go.microsoft.com/fwlink/?LinkId=153815) (http://go.microsoft.com/fwlink/?LinkId=153815)。|  
|論理削除と物理削除ようにパラメーターを最適な時間の長さのデータを保持している場合を確認します。|参照してください[「アーカイブおよび BizTalk 追跡データベースの消去」](http://go.microsoft.com/fwlink/?LinkId=153816) (http://go.microsoft.com/fwlink/?LinkId=153816)。|  
|だけ古いデータを削除しないようにする必要がある場合必要があります、最初の変更をアーカイブする SQL エージェント ジョブ、ストアド プロシージャを呼び出す"dtasp_PurgeTrackingDatabase"|参照してください[「BizTalk 追跡データベースからデータを削除する方法」](http://go.microsoft.com/fwlink/?LinkId=153817) (http://go.microsoft.com/fwlink/?LinkId=153817)。|  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SQL Server の設定を変更しないでください。](~/technical-guides/sql-server-settings-that-should-not-be-changed.md)  
  
-   [監視およびデータベース入出力の競合を減らす](~/technical-guides/monitoring-and-reducing-database-i-o-contention.md)  
  
-   [レビューし、テスト フェールオーバーのシナリオに SQL Server クラスターの構成](~/technical-guides/reviewing-and-testing-sql-server-cluster-configuration-for-failover-scenarios.md)  
  
-   [データベースの自動拡張設定を定義します。](~/technical-guides/defining-auto-growth-settings-for-databases.md)  
  
-   [データベースのバックアップ](~/technical-guides/backing-up-databases.md)  
  
-   [BizTalk Server のログ配布災害復旧を使用します。](~/technical-guides/using-biztalk-server-log-shipping-for-disaster-recovery.md)  
  
-   [SQL Server エージェント ジョブの監視](~/technical-guides/monitoring-sql-server-agent-jobs.md)  
  
-   [消去および追跡データをアーカイブ](~/technical-guides/purging-and-archiving-tracking-data.md)