---
title: データベースの事前構成 Optimizations2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8c525c3a-249c-4694-b287-a8c35a6aa524
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b5486c3a18473998a11a98f6741097d2f751128
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399565"
---
# <a name="pre-configuration-database-optimizations"></a>前の構成データベースの最適化
ため、BizTalk Server 環境で SQL Server が果たす重要な役割が何よりも重要な SQL Server は、最適なパフォーマンス用に構成されている/調整します。 実行する SQL Server は、チューニングしない場合は、BizTalk Server で使用されるデータベースがボトルネックになり、BizTalk Server 環境の全体的なパフォーマンスが低下します。 このトピックでは、BizTalk Server をインストールして、BizTalk Server データベースを構成する前に従う必要がありますをいくつかの SQL Server パフォーマンスの最適化について説明します。  
  
## <a name="set-ntfs-file-allocation-unit"></a>NTFS ファイル アロケーション ユニットを設定します。  
 SQL Server では、そのデータを格納する**エクステント**、物理的に連続する 8 個の 8 K ページ (64 kb) のコレクションであります。 そのため、ディスクのパフォーマンスを最適化するために、NTFS アロケーション ユニット サイズ 64 KB を「ディスク構成のベスト プラクティス」で説明されているように設定[展開前 I/O のベスト プラクティス](https://msdn.microsoft.com/library/cc966412.aspx)します。  
  
## <a name="considerations-for-the-version-and-edition-of-sql-server"></a>バージョンおよびエディションの SQL Server に関する考慮事項  
 さまざまなバージョンおよびエディションの[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]のパフォーマンスに影響するさまざまな機能を提供、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。 たとえば、条件は負荷の高いの 32 ビット バージョンで利用可能なデータベース ロックの数[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]過ぎる可能性のある、BizTalk ソリューションのパフォーマンスに悪影響は。 テスト環境で"ロック"の範囲外のエラーが発生した場合、64 ビット バージョンの SQL Server でメッセージ ボックス データベースを格納していることを検討してください。 使用可能なロックの数は、64 ビット バージョンの SQL Server で大幅に高くなっています。  
  
 BizTalk 環境に必要なデータベース エンジンの機能を決定する場合は、次の表を検討してください。 大規模なエンタープライズ レベルのソリューションをクラスタ リングを必要とするサポート、BizTalk Server ログ配布のサポート、または Analysis Services がサポートし、ホストする SQL Server Enterprise Edition が必要がある、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース。   

 SQL Server のエディションでサポートされる機能の完全な一覧を参照してください。 [SQL Server のエディションとサポートされる機能](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016)します。
  
## <a name="database-planning-considerations"></a>データベースの計画に関する考慮事項  
 高速ストレージ (SAN ディスクを高速または高速な SCSI ディスクなど) 上にある SQL Server データベースをホストすることをお勧めします。 RAID 5 ではなく、RAID 10 (1 + 0) は、raid 5 は書き込みで低速であるためお勧めします。 このような場合も raid 選択が重要新しい SAN ディスク非常に大きなメモリ キャッシュがあります。 パフォーマンスを向上させるには、データベースおよびログ ファイルが別の物理ディスクに配置できます。  
  
 記憶域エリア ネットワーク (SAN) を使用する場合、ホスト バス アダプター (HBA) のキューの深さのチューニングも検討します。 I/O のスループットに影響する可能性が大幅にし、そのボックス外の値を SQL Server のための十分なできます。 テストは、64 のキューの深さがない場合は、特定のベンダーの推奨事項の適切な開始点として使用されますが、最適な値を決定するために必要  
  
## <a name="install-the-latest-service-pack-and-cumulative-updates-for-sql-server"></a>SQL Server の最新の service pack と累積的更新プログラムをインストールします。  
 SQL Server と .NET Framework の最新のサービス パックには、最新のサービス パックと最新の累積的更新プログラムをインストールします。  
  
## <a name="install-sql-service-packs-and-cumulative-updates-on-both-biztalk-server-and-sql-server"></a>BizTalk Server と SQL Server の両方で SQL サービス パックや累積的更新プログラムをインストールします。  
 SQL Server のサービス パックまたは累積的更新プログラムをインストールするときにも、サービス パックまたは累積更新プログラムをインストール、BizTalk Server コンピューター。 BizTalk Server では、SQL Server サービス パックや累積的更新プログラムによって更新される SQL クライアント コンポーネントを使用します。  
  
## <a name="consider-using-a-fast-solid-state-drive-ssd-to-house-the-sql-server-tembdb"></a>SQL Server tembdb を格納するための高速なソリッド ステート ドライブ (SSD) の使用を検討します。  
 TempDB を格納するための 1 つまたは複数のソリッド ステート ディスク (SSD) ドライブを使用してください。 SSD ドライブは、従来のハード ドライブ上の大幅なパフォーマンスの利点を提供し、主流の市場に参入するように価格ですぐに削除します。 TempDB のパフォーマンスは全体の重要な要因が多いため[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]パフォーマンス、ドライブの追加の初期コストは多くの場合、すばやくによって削減全体的な増加[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]パフォーマンス、特にエンタープライズ アプリケーションを実行する場合対象の[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]パフォーマンスが重要です。  
  
## <a name="consider-implementing-the-sql-server-2008-r2-data-collector-and-management-data-warehouse"></a>SQL Server 2008 R2 のデータ コレクターと管理データ ウェアハウスの実装を検討してください。  
 SQL Server 2008 R2 は、新しいの使用に対応環境とデータベースのパフォーマンスを収集するには、データ コレクターや管理データ ウェアハウスに関連したテストと傾向の分析のためのデータ。 データ コレクターは、指定した管理データ ウェアハウスに収集されたすべてのデータを保持します。 これはパフォーマンスの最適化ではありませんこれがパフォーマンスの問題の分析に有用になります。  
  
## <a name="grant-the-account-which-is-used-for-sql-server-the-windows-lock-pages-in-memory-privilege"></a>SQL Server の Windows のロックの Pages In Memory 特権に使用されるアカウントに付与します。  
 Windows Lock Pages in Memory 特権を SQL Server のサービス アカウントを付与します。 これは、SQL Server プロセスのバッファー プール メモリのページングから物理メモリにバッファー プールに割り当てられたメモリをロックすることにより、Windows オペレーティング システムを防ぐために実行する必要があります。  
  
 Windows のポリシーで、ラボ環境で**Lock Pages in Memory**オプションが既定で有効にします。 参照してください[Lock Pages in Memory オプションを有効にする](https://docs.microsoft.com/sql/database-engine/configure-windows/enable-the-lock-pages-in-memory-option-windows)します。  
  
> [!IMPORTANT]  
>  SQL Server のサービス アカウントに Windows Lock Pages in Memory 特権を許可するときに、いくつかの制限が適用されます。 次を参照してください。 
>   
> - [バッファー プール拡張](https://docs.microsoft.com/sql/database-engine/configure-windows/buffer-pool-extension)  
> - [Lock Pages in Memory オプションを有効にします。 ](https://docs.microsoft.com/sql/database-engine/configure-windows/enable-the-lock-pages-in-memory-option-windows)  
  
## <a name="grant-the-semanagevolumename-right-to-the-sql-server-service-account"></a>SQL Server のサービス アカウントの権限を SE_MANAGE_VOLUME_NAME を付与します。  
 SQL Server サービスを実行しているアカウントは、' ボリュームの保守タスクを実行する ' Windows 特権を持つことを確認するか、グループに属していることを確認します。 データベースの自動拡張がある場合は、このファイルの瞬時初期化の確保最適なパフォーマンスによりします。  
  
## <a name="set-min-and-max-server-memory"></a>Min と Max Server Memory を設定します。  
 ホストする SQL Server を実行するコンピューター、BizTalk Server データベースを SQL Server を実行する専用必要があります。 'Min server memory' と各 SQL Server インスタンス '最大サーバー メモリ' オプションが設定を固定するメモリ量を指定することが推奨をホストする SQL Server を実行するコンピューター、BizTalk Server データベースは専用の SQL Server を実行するときにSQL Server に割り当てます。 この場合、する必要があります設定する"min server memory"と"max server memory"を同じ値 (SQL Server を使用する物理メモリの最大量に等しい)。 これが減少オーバーヘッドはそれ以外の場合これらの値を動的に管理する SQL Server によって使用されます。 SQL Server に割り当てるメモリの固定量を指定する SQL Server を実行している各コンピューターで、次の T-SQL コマンドを実行します。  
  
```  
sp_configure ‘Max Server memory (MB)’,(max size in MB)  
sp_configure ‘Min Server memory (MB)’,(min size in MB)  
```  
  
 SQL Server のメモリの量を設定する前に、Windows Server に必要な合計物理メモリからメモリを差し引くことで、適切なメモリ設定を決定します。 これは、SQL Server に割り当てるメモリの最大量です。  
  
> [!NOTE]  
>  ホストする SQL Server を実行するコンピューター、BizTalk Server データベースも、エンタープライズ シングル サインオン マスター シークレット サーバーをホストし場合エンタープライズ シングル サインオンを実行するための十分なメモリがあることを確認するには、この値を調整するにはサービス。 マスター シークレット サーバーの高可用性を実現する SQL Server クラスターでエンタープライズ シングル サインオン サービスのクラスター化されたインスタンスを実行するは珍しい方法ではありません。 参照してください[マスター シークレット サーバーをクラスタ リング](../technical-guides/clustering-the-master-secret-server.md)  
  
## <a name="split-the-tempdb-database-into-multiple-data-files-of-equal-size-on-each-sql-server-instance-used-by-biztalk-server"></a>Tempdb データベースを BizTalk Server で使用される各 SQL Server インスタンスに等しいサイズの複数のデータ ファイルに分割します。  
 SQL Server で使用される、比例書き込みアルゴリズムは、データ ファイルのサイズに基づいているために、tempdb に使用されるデータ ファイルが同じサイズのことが重要です。 サイズの異なるデータ ファイルが作成、比例書き込みアルゴリズムは、一番大きいファイルを複数のデータ ファイルを作成する目的にそぐわなくなりますそれによって、すべてのファイル間の割り当てを展開するのではなく、GAM 割り当てを使用します。 Tempdb データ ファイルの最適な数は、tempdb でラッチの競合の程度によって異なります。 一般則としてデータ ファイルの数は、Cpu の数が 8 には、プロセッサ コア/Cpu の数と等しく以下する必要があります。 8 個を超える cpu を搭載したサーバーでは、Cpu の数の半分のデータ ファイルの作成 (ここでも、のみがあるラッチの競合)。  
  
 このラボ環境では、次のスクリプトを使用して、100 MB の増加に 1024 MB のファイル サイズがそれぞれの 8 つの TempDB データ ファイルと 100 MB の増加に 512 MB のログ ファイルを作成しました。 データ ファイルはドライブ: %m: に移動し、ログ ファイルは、操作をドライブに移動されます。  
  
> [!IMPORTANT]  
>  このスクリプトは、デモまたは教育目的にのみのためのものでは、ご自身の責任で使用される「とは、」です。 、Microsoft では、このスクリプトの使用はサポートされていないと、このスクリプトの適合性に関する Microsoft の保証がありません。  
  
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
  
 SQL Server 2008 の利用状況モニターまたはで説明されている SQL Server 2005 Performance Dashboard Reports を使用して、 [SQL Server のパフォーマンスの監視](../technical-guides/monitoring-sql-server-performance.md)ラッチの競合の問題を特定します。  
  
## <a name="manually-set-sql-server-process-affinity"></a>SQL Server プロセスの関係を手動で設定します。  
 プロセス関係オプションは、16 個以上の Cpu を持つ非 NUMA コンピューターで実行されているハイエンドのエンタープライズ レベルの SQL Server 環境のパフォーマンス強化を提供できます。 これは、メッセージ ボックス データベース内の共有テーブルでの競合がある高スループットの BizTalk 環境に特に当てはまります。 ラボ環境で使用されていた SQL Server コンピューターの NUMA 対応でしたおよび 16 コア、パフォーマンスを最適化する必要があるので、プロセスの関係を設定する次のコマンドを使いました。  
  
 **0 から 15 に SQL Server プロセスの関係を手動で設定するには**  
  
```  
ALTER SERVER CONFIGURATION  
SET PROCESS AFFINITY CPU = 0 to 15  
```  
  
 詳細については、次を参照してください。 [ALTER SERVER CONFIGURATION (TRANSACT-SQL)](https://docs.microsoft.com/sql/t-sql/statements/alter-server-configuration-transact-sql)します。
  
## <a name="configure-msdtc"></a>MSDTC の構成  
 SQL Server と BizTalk Server 間のトランザクションを促進するには、Microsoft 分散トランザクション コーディネーター (MS DTC) を有効にする必要があります。 SQL Server 上で MSDTC を構成するには、トピックを参照して[オペレーティング システムのパフォーマンスを向上させるための一般的なガイドライン](../technical-guides/general-guidelines-for-improving-operating-system-performance.md)します。  
  
## <a name="enable-trace-flag-t1118-as-a-startup-parameter-for-all-instances-of-sql-server"></a>SQL Server のすべてのインスタンスの起動時のパラメーターとしてトレース フラグ-t1118 を実装を有効にします。  
 トレースを実装する – フラグ-t1118 を実装では、ほぼすべての単一ページの割り当てを削除することで、SQL Server インスタンス間で競合を減らすことができます。 詳細については、次を参照してください。 [KB 328551。[PRB]:Tempdb データベースの同時実行制御の強化](https://support.microsoft.com/help/328551/concurrency-enhancements-for-the-tempdb-database)します。
  
## <a name="do-not-change-default-sql-server-settings-for-max-degree-of-parallelism-sql-server-statistics-or-database-index-rebuilds-and-defragmentation"></a>Max degree of parallelism、SQL Server の統計、またはデータベースのインデックス再構築と最適化の既定の SQL Server 設定を変更しません。  
 SQL Server インスタンスには、BizTalk Server データベースを格納する場合、は、特定の SQL Server 設定を変更しないでください。 具体的には、並列処理の最大限度の SQL Server、SQL Server の統計をメッセージ ボックス データベースとデータベースのインデックスの設定を再構築し、最適化を変更しないでください。 参照してください[SQL Server の設定を変更しないでください](../technical-guides/sql-server-settings-that-should-not-be-changed.md)します。
  
## <a name="see-also"></a>参照  
 [データベース パフォーマンスの最適化](../technical-guides/optimizing-database-performance.md)
