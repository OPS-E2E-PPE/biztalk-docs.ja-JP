---
title: "事前構成データベース Optimizations2 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8c525c3a-249c-4694-b287-a8c35a6aa524
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f863ae780dd99a7f0aa7d9acc3884f860686c86
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="pre-configuration-database-optimizations"></a>事前構成データベースの最適化
SQL Server が BizTalk Server 環境で再生される重要な役割、ためことが最も重要 SQL Server では、パフォーマンスを最適に構成されているチューニングできることです。 SQL Server が正しく実行するチューニングされなかった場合は、BizTalk Server で使用するデータベースがボトルネックになり、BizTalk Server 環境の全体的なパフォーマンスが低下します。 このトピックでは、BizTalk Server をインストールして、BizTalk Server データベースを構成する前に従う必要があります複数の SQL Server パフォーマンス最適化機能について説明します。  
  
## <a name="set-ntfs-file-allocation-unit"></a>NTFS ファイル アロケーション ユニットを設定します。  
 SQL Server では、そのデータを格納する**エクステント**、物理的に連続する 8 つの 8 K ページ、または 64 KB のコレクションであります。 そのため、ディスクのパフォーマンスを最適化するために、NTFS アロケーション ユニット サイズ 64 KB をに従って設定、「ディスク構成のベスト プラクティス」で[デプロイメント前 I/O のベスト プラクティス](https://msdn.microsoft.com/library/cc966412.aspx)です。  
  
## <a name="considerations-for-the-version-and-edition-of-sql-server"></a>バージョンおよびエディションの SQL Server に関する考慮事項  
 さまざまなバージョンおよびエディションの[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]のパフォーマンスに影響を与えるさまざまな機能を提供、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。 などの状況で負荷の高いの 32 ビット バージョンで利用可能なデータベース ロック数[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]過ぎる可能性のある、これは、BizTalk ソリューションのパフォーマンスを低下させます。 テスト環境でロックの範囲外"エラーが発生した場合、64 ビット バージョンの SQL Server にメッセージ ボックス データベースを格納していることを検討してください。 64 ビット バージョンの SQL Server では、使用できるロックの数が大幅に増えます。  
  
 BizTalk 環境に必要なデータベース エンジンの機能を決定する場合は、次の表を検討してください。 大規模なクラスタ リングが必要なエンタープライズ レベルのソリューションをサポート、BizTalk Server のログ配布のサポート、または Analysis Services がサポートしてホストする SQL Server Enterprise Edition が必要があります、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース。   

 SQL Server のエディションでサポートされる機能の完全な一覧を参照してください。 [SQL Server のエディションとサポートされる機能](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016)します。
  
## <a name="database-planning-considerations"></a>データベースの計画に関する考慮事項  
 (たとえば、高速な SAN ディスクまたは高速の SCSI ディスクなど) の高速記憶域上にある SQL Server データベースをホストすることをお勧めします。 RAID 5 ではなく RAID 10 (1 + 0) は、raid 5 は、書き込みに遅いのでお勧めします。 新しい SAN ディスクに非常に大きなメモリ キャッシュ、があるは、このような場合、raid 選択重要ではないためです。 パフォーマンスを向上させるには、データベースおよびログ ファイルが別々 の物理ディスクに配置できます。  
  
 記憶域エリア ネットワーク (SAN) を使用する場合に、ホスト バス アダプター (HBA) のキューの深さをチューニングも検討します。 I/O のスループットに影響する可能性が大幅にあり、外のボックスの値は SQL Server の不十分であることができます。 テストが最適な値を確認する必要がない場合は、特定の仕入先推奨事項の適切な開始点として通常 64 のキューの深さは受け入れられます  
  
## <a name="install-the-latest-service-pack-and-cumulative-updates-for-sql-server"></a>SQL Server の最新の service pack と累積的な更新プログラムをインストールします。  
 SQL Server と .NET Framework の最新のサービス パックの最新のサービス パックと最新の累積的更新プログラムをインストールします。  
  
## <a name="install-sql-service-packs-and-cumulative-updates-on-both-biztalk-server-and-sql-server"></a>BizTalk Server と SQL Server の両方で SQL サービス パックと累積更新プログラムをインストールします。  
 SQL Server のサービス パックまたは累積的更新プログラムをインストールするときにもインストール service pack または累積更新プログラム、BizTalk Server コンピューター。 BizTalk Server では、SQL Server サービス パックおよび累積的な更新プログラムによって更新される SQL クライアント コンポーネントを使用します。  
  
## <a name="consider-using-a-fast-solid-state-drive-ssd-to-house-the-sql-server-tembdb"></a>SQL Server tembdb を格納するに高速ソリッド ステート ドライブ (SSD) を使用してください。  
 TempDB を格納する 1 つまたは複数の実線状態ディスク (SSD) ドライブを使用してください。 SSD ドライブは、従来のハード ドライブ上の大幅なパフォーマンスの利点があり、主流市場を入力するように価格で迅速に削除します。 TempDB のパフォーマンスは多くの場合、全体の重要な要因であるため[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]パフォーマンス、ドライブの初期コストをかけるは多くの場合、すばやくによって削減全体的な増加[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]特にエンタープライズ アプリケーションの実行時のパフォーマンス対象の[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]パフォーマンスが重要です。  
  
## <a name="consider-implementing-the-sql-server-2008-r2-data-collector-and-management-data-warehouse"></a>SQL Server 2008 R2 のデータ コレクターと管理データ ウェアハウスを実装することを検討してください。  
 SQL Server 2008 R2 は、新しいの使用に対応環境/データベースのパフォーマンスを収集するには、データ コレクターや管理データ ウェアハウスに関連したテストと傾向分析のためのデータ。 データ コレクターは、指定の管理データ ウェアハウスに収集されたすべてのデータを保持します。 これはパフォーマンスの最適化ではありませんは、パフォーマンスの問題の分析に役立つこれになります。  
  
## <a name="grant-the-account-which-is-used-for-sql-server-the-windows-lock-pages-in-memory-privilege"></a>Windows Lock Pages Memory 特権 In SQL Server に使用されるアカウントに付与します。  
 Windows Lock Pages in Memory 特権を SQL Server サービス アカウントを付与します。 これは、物理メモリにバッファー プールに割り当てられているメモリをロックすることにより、SQL Server プロセスのバッファー プール メモリのページングから Windows オペレーティング システムを防ぐために行う必要があります。  
  
 Windows のポリシーで、ラボ環境で**Lock Pages in Memory**オプションが既定で有効にします。 参照してください[Lock Pages in Memory オプションを有効にする](https://docs.microsoft.com/sql/database-engine/configure-windows/enable-the-lock-pages-in-memory-option-windows)です。  
  
> [!IMPORTANT]  
>  SQL Server サービス アカウントの Windows Lock Pages in Memory 特権を付与するときに、いくつかの制限が適用されます。 次を参照してください。 
>   
> - [バッファー プール拡張](https://docs.microsoft.com/sql/database-engine/configure-windows/buffer-pool-extension)  
> - [Lock Pages in Memory オプションを有効にします。](https://docs.microsoft.com/sql/database-engine/configure-windows/enable-the-lock-pages-in-memory-option-windows)  
  
## <a name="grant-the-semanagevolumename-right-to-the-sql-server-service-account"></a>SQL Server サービス アカウントの権限を SE_MANAGE_VOLUME_NAME を与える  
 SQL Server サービスを実行しているアカウントは、' ボリュームの保守タスクを実行する ' Windows 特権を持つことを確認またはグループに属していることを確認します。 これによって、ファイルの瞬時初期化の確保最適なパフォーマンス、データベースの自動拡張する場合。  
  
## <a name="set-min-and-max-server-memory"></a>Min および Max Server Memory を設定します。  
 ホストする SQL Server を実行するコンピューター、BizTalk Server データベースは、SQL Server を実行する専用必要があります。 'Min server memory' と各 SQL Server インスタンス上の 'max server memory' オプションが設定を固定するメモリ量を指定することが推奨をホストする SQL Server を実行するコンピューターの BizTalk Server データベースは専用 SQL Server を実行して、SQL Server に割り当てます。 この場合、する必要があります"min server memory"と"max server memory"、同じ値に設定 (SQL Server が使用される物理メモリの最大量に等しい)。 これが減少それ以外の場合にこれらの値を動的に管理する SQL Server で使用されるオーバーヘッドです。 SQL Server に割り当てるメモリの固定量を指定する SQL Server を実行する各コンピューターで、次の T-SQL コマンドを実行します。  
  
```  
sp_configure ‘Max Server memory (MB)’,(max size in MB)  
sp_configure ‘Min Server memory (MB)’,(min size in MB)  
```  
  
 SQL Server のメモリの量を設定すると、前に、合計物理メモリから Windows Server に必要なメモリを差し引くことで適切なメモリ設定を決定します。 これは、SQL Server に割り当てるメモリの最大量です。  
  
> [!NOTE]  
>  ホストする SQL Server を実行するコンピューターの BizTalk Server データベースもホストする場合、エンタープライズ シングル サインオン マスター シークレット サーバー、したい場合があります、エンタープライズ シングル サインオンを実行するための十分なメモリがあることを確認するには、この値を調整するにはサービス。 マスター シークレット サーバーの高可用性を実現する SQL Server クラスターでクラスター化されたエンタープライズ シングル サインオン サービスのインスタンスを実行することは珍しくの実習ではないです。 参照してください[マスター シークレット サーバーをクラスタ リング](../technical-guides/clustering-the-master-secret-server.md)  
  
## <a name="split-the-tempdb-database-into-multiple-data-files-of-equal-size-on-each-sql-server-instance-used-by-biztalk-server"></a>Tempdb データベースを同じサイズの BizTalk Server で使用される各 SQL Server インスタンス上の複数のデータ ファイルに分割します。  
 SQL Server で使用される比例アルゴリズムは、データ ファイルのサイズに基づいているために、ことを確認するための tempdb データ ファイルと同じサイズのことが重要です。 サイズの異なるデータ ファイルが作成する場合、比例アルゴリズムは、それによってが無意味に複数のデータ ファイルを作成するすべてのファイル間での割り当てを展開するのではなく、GAM の割り当ての最大のファイルを使用します。 最適な数の tempdb データ ファイルは、ラッチの競合が tempdb での程度によって異なります。 一般的な則としてデータ ファイルの数は、ここで、Cpu の数は 8 プロセッサ コアと Cpu の数以下する必要があります。 8 個を超える cpu を搭載したサーバーでは、Cpu の数の半分のデータ ファイルの作成 (ここでも、のみがあるラッチの競合)。  
  
 このラボ環境では、次のスクリプトを使用して、ファイル サイズが 100 MB の増加に 1024 MB のそれぞれが 8 の TempDB データ ファイルと 100 MB の増加に 512 MB のログ ファイルを作成しました。 データ ファイルが: %m: ドライブに移動され、ログ ファイルは、i: ドライブに移動されます。  
  
> [!IMPORTANT]  
>  このスクリプトは、提供「としては、」デモまたは演習目的でのみ、向けし、各自の責任で使用されます。 、Microsoft では、このスクリプトの使用はサポートされていないと、Microsoft がこのスクリプトの適合性に関して保証を行いません。  
  
```  
--<<<<<<<<<<----------------------------------------------------------------->>>>>>>>>>--  
-- Use of included script samples are subject to the terms specified at   
-- http://www.microsoft.com/info/cpyright.htm  
--<<<<<<<<<<----------------------------------------------------------------->>>>>>>>>>--  
--***Instructions***  
-- 1. If running the script from a remote server, change the context in SSMS to target instance  
-- 2. Enable SQLCMD mode (add & click toolbar button or toggle by clicking Query > SQLCMD Mode)  
-- 3. Commence execution of scripts (recommend running statements discretely to more easily remedy potential problems)  
-- 4. Examine servername & temp configuration  
-- 5. If necessary, 1) Replace instance name in path to reflect target instance *all throughout script*  
      --            2) Modify root drives to reflect drives designated for data & log (folder creation *and* ALTER DB statements)  
-- 6. Resume script execution  
-- 7. If necessary, create new folders  
-- 8. Modify/Add data & log files   
-- 9. Recycle SQL service using sqlservermanager10.msc  
--10. Examine results & if appropriate, delete original tempdb data log files   
 --(if they were "moved", the original files aren't automatically deleted)  
  
--<<<<<<<<<<----------------------------------------------------------------->>>>>>>>>>--  
--1. If running the script from a remote server, change the context in SSMS to target instance  
--2. Enable SQLCMD mode (add & click toolbar button or toggle by clicking Query > SQLCMD Mode)  
--3. Commence execution of scripts (recommend running statements discretely to more easily remedy potential problems)  
--4. Examine servername & temp configuration  
SELECT @@SERVERNAME  
EXEC dbo.sp_helpdb tempdb  
--tempdev   1   C:\tempdb.mdf   PRIMARY  8192 KB  Unlimited  10%  data only  
--templog   2   C:\templog.ldf  NULL      512 KB  Unlimited  10%  log only  
GO  
--5. If necessary, 1) Replace instance name in path to reflect target instance *all throughout script*  
     --            2) Modify root drives to reflect drives designated for data & log (folder creation *and* ALTER DB statements)  
--6. Resume script execution  
--7. If necessary, create new folders  
--!!md H:\MSSQL10.<instance>  
--!!md H:\MSSQL10.<instance>\MSSQL  
--!!md H:\MSSQL10.<instance>\MSSQL\DATA  
GO  
-- 8. Modify/Add data & log files   
 --note: even if the out-of-box mdf is already where it needs to be,   
   --the first command is necessary to modify size & filegrowth  
ALTER DATABASE tempdb MODIFY FILE (NAME = tempdev  , FILENAME = 'H:\tempdb.mdf'   , SIZE = 1024MB , FILEGROWTH = 100MB)  
ALTER DATABASE tempdb ADD FILE    (NAME = tempdat2 , FILENAME = 'H:\tempdat2.ndf' , SIZE = 1024MB , FILEGROWTH = 100MB)  
ALTER DATABASE tempdb ADD FILE    (NAME = tempdat3 , FILENAME = 'H:\tempdat3.ndf' , SIZE = 1024MB , FILEGROWTH = 100MB)  
ALTER DATABASE tempdb ADD FILE    (NAME = tempdat4 , FILENAME = 'H:\tempdat4.ndf' , SIZE = 1024MB , FILEGROWTH = 100MB)  
ALTER DATABASE tempdb ADD FILE    (NAME = tempdat5 , FILENAME = 'H:\tempdat5.ndf' , SIZE = 1024MB , FILEGROWTH = 100MB)  
ALTER DATABASE tempdb ADD FILE    (NAME = tempdat6 , FILENAME = 'H:\tempdat6.ndf' , SIZE = 1024MB , FILEGROWTH = 100MB)  
ALTER DATABASE tempdb ADD FILE    (NAME = tempdat7 , FILENAME = 'H:\tempdat7.ndf' , SIZE = 1024MB , FILEGROWTH = 100MB)  
ALTER DATABASE tempdb ADD FILE    (NAME = tempdat8 , FILENAME = 'H:\tempdat8.ndf' , SIZE = 1024MB , FILEGROWTH = 100MB)  
GO  
ALTER DATABASE tempdb MODIFY FILE (NAME = templog , FILENAME = 'I:\templog.ldf', SIZE =  512MB , FILEGROWTH = 100MB)  
GO  
--8b. Modify log file:  modify drive & instance name to reflect designated destination for tempdb log   
--!!md I:\MSSQL10.<instance>  
--!!md I:\MSSQL10.<instance>\MSSQL  
--!!md I:\MSSQL10.<instance>\MSSQL\DATA  
GO  
-- 9. Recycle SQL service in SQL Server Services node of sqlservermanager10.msc  
    --note, if running script from a UNC share, SSMS will report an error,   
      --but SQL Server Configuration Manager will open if its location is in %path%  
!!sqlservermanager10.msc  
  
--10. Examine results & if appropriate, delete original tempdb data log files   
 --(if they were "moved", the original files aren't automatically deleted)  
EXEC dbo.sp_helpdb tempdb  
--!!del C:\tempdb.mdf     
--!!del C:\templog.ldf  
GO  
  
```  
  
 SQL Server 2008 の利用状況モニターまたはで説明されている SQL Server 2005 Performance Dashboard Reports を使用して[SQL Server のパフォーマンスの監視](../technical-guides/monitoring-sql-server-performance.md)ラッチの競合の問題を特定します。  
  
## <a name="manually-set-sql-server-process-affinity"></a>SQL Server プロセスの関係を手動で設定します。  
 プロセス関係オプションは、16 個以上の Cpu を持つ非 NUMA コンピューターで実行されている、エンタープライズ レベルのハイエンドの SQL Server 環境のパフォーマンスが向上を提供できます。 これは、メッセージ ボックス データベース内の共有のテーブルでの競合がある高スループットの BizTalk 環境で特に当てはまります。 このラボ環境で使用された SQL Server コンピューターを選択して NUMA 対応インポートされなかったが、パフォーマンスを最適化するために、16 コア、ために、次のコマンドを使用して、プロセス関係の設定に。  
  
 **0 から 15 に SQL Server プロセスの関係を手動で設定するには**  
  
```  
ALTER SERVER CONFIGURATION  
SET PROCESS AFFINITY CPU = 0 to 15  
```  
  
 詳細については、次を参照してください。 [ALTER SERVER CONFIGURATION (TRANSACT-SQL)](https://docs.microsoft.com/sql/t-sql/statements/alter-server-configuration-transact-sql)です。
  
## <a name="configure-msdtc"></a>MSDTC を構成します。  
 SQL Server と BizTalk Server の間でトランザクションを容易にするため、Microsoft 分散トランザクション コーディネーター (MS DTC) を有効にする必要があります。 SQL Server で MSDTC を構成するには、トピックを参照して[オペレーティング システムのパフォーマンスを向上させるための一般的なガイドライン](../technical-guides/general-guidelines-for-improving-operating-system-performance.md)です。  
  
## <a name="enable-trace-flag-t1118-as-a-startup-parameter-for-all-instances-of-sql-server"></a>SQL Server のすべてのインスタンスの起動時のパラメーターとしてトレース フラグ-t1118 を実装を有効にします。  
 トレースを実装するフラグ –-t1118 を実装では、ほとんどすべての単一のページ割り当てを削除することで、SQL Server インスタンス間での競合を減らすことができます。 詳細については、次を参照してください。 [KB 328551: PRB: tempdb データベースの同時実行制御の機能強化](https://support.microsoft.com/help/328551/concurrency-enhancements-for-the-tempdb-database)です。
  
## <a name="do-not-change-default-sql-server-settings-for-max-degree-of-parallelism-sql-server-statistics-or-database-index-rebuilds-and-defragmentation"></a>Max degree of parallelism、SQL Server 統計情報、またはデータベースのインデックス再構築と最適化の既定の SQL Server 設定を変更しません。  
 SQL Server インスタンスには、BizTalk Server データベースを格納する場合、は、変更すべき特定の SQL Server の設定です。 具体的には、SQL Server max degree of parallelism、メッセージ ボックス データベース、およびデータベースのインデックスの設定 SQL Server の統計を再構築し、最適化は変更できません。 参照してください[が変更されない SQL Server の設定](../technical-guides/sql-server-settings-that-should-not-be-changed.md)です。
  
## <a name="see-also"></a>参照  
 [データベース パフォーマンスの最適化](../technical-guides/optimizing-database-performance.md)
