---
title: "事前構成データベース Optimizations1 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ebd0b32a-490d-4db2-a1fc-bf3bef93aeea
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c1333f956afc4411ff8b105c777214467155ae7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="pre-configuration-database-optimizations"></a>事前構成データベースの最適化
BizTalk Server は、Microsoft SQL Server で最大 13 個の独立したデータベースの作成を必要とするデータベースを非常に大量に消費するアプリケーションです。 ため、BizTalk Server 環境で SQL Server が再生される重要な役割がきわめて重要 SQL Server では、パフォーマンスを最適に構成されているチューニングがあります。 SQL Server が正しく実行するチューニングされなかった場合は、BizTalk Server で使用するデータベースがボトルネックになり、BizTalk Server 環境の全体的なパフォーマンスが低下します。 このトピックでは、BizTalk Server をインストールして、BizTalk Server データベースを構成する前に従う必要があります複数の SQL Server パフォーマンス最適化機能について説明します。  
  
## <a name="set-ntfs-file-allocation-unit"></a>NTFS ファイル アロケーション ユニットを設定します。  
 SQL Server では、そのデータを格納する**エクステント**、8 8 K ページのグループがあります。 そのため、ディスクのパフォーマンスを最適化するために、NTFS アロケーション ユニット サイズ 64 KB に設定のベスト プラクティス記事「デプロイメント前 I/O のベスト プラクティス」で利用可能な SQL Server の"ディスク構成のベスト プラクティス"セクションで説明した[http://go.microsoft.com/fwlink/ しますか。LinkId = 140818](http://go.microsoft.com/fwlink/?LinkId=140818)です。 SQL Server のページとエクステントの詳細については、次を参照してください。、[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]オンライン ブックの「[ページとエクステントについて](http://go.microsoft.com/fwlink/?LinkId=148939)(ハイパーリンク"http://go.microsoft.com/fwlink/?LinkId=148939"http://go.microsoft.com/fwlink/?LinkId=148939)。  
  
## <a name="database-planning-considerations"></a>データベースの計画に関する考慮事項  
 ホストすることをお勧め、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] (たとえば、高速な SAN ディスクまたは高速の SCSI ディスクなど) の高速記憶域上のデータベースです。 RAID 5 ではなく RAID 10 (1 + 0) は、raid 5 が書き込み時に遅いためお勧めします。 新しい SAN ディスクでは、このような場合は、RAID の選択は、重要ではないで非常に大きなメモリ キャッシュがあります。 パフォーマンスを向上させるには、データベースおよびログ ファイルが別々 の物理ディスクに配置できます。  
  
## <a name="install-the-latest-service-pack-and-cumulative-updates-for-sql-server"></a>SQL Server の最新の service pack と累積的な更新プログラムをインストールします。  
 SQL Server 2005 および SQL Server 2008 だけでなく、最新の .NET Framework サービス パックの最新のサービス パックと最新の累積的更新プログラムをインストールします。  
  
## <a name="install-sql-service-packs-on-both-biztalk-server-and-sql-server"></a>BizTalk Server と SQL Server の両方で SQL サービス パックをインストールします。  
 を SQL Server のサービス パックをインストールする場合も、BizTalk Server コンピューターのサービス パックをインストールします。 BizTalk Server では、SQL Server service pack で更新される SQL クライアント コンポーネントを使用します。  
  
## <a name="consider-implementing-the-sql-server-2008-data-collector-and-management-data-warehouse"></a>SQL Server 2008 のデータ コレクターと管理データ ウェアハウスを実装することを検討してください。  
 SQL Server 2008 は、新しいの使用に対応環境/データベースのパフォーマンスを収集するには、データ コレクターや管理データ ウェアハウスに関連したテストと傾向分析のためのデータ。 データ コレクターは、指定の管理データ ウェアハウスに収集されたすべてのデータを保持します。 これはパフォーマンスの最適化ではありません、これがパフォーマンスの問題の分析の役に立ちます。  
  
## <a name="grant-the-account-which-is-used-for-sql-server-the-windows-lock-pages-in-memory-privilege"></a>Windows Lock Pages Memory 特権 In SQL Server に使用されるアカウントに付与します。  
 Windows の"Lock Pages in Memory"は、SQL Server サービス アカウントに特権を付与します。 これは、物理メモリにバッファー プールに割り当てられているメモリをロックすることにより、SQL Server プロセスのバッファー プール メモリのページングから Windows オペレーティング システムを防ぐために行う必要があります。 詳細についてで Microsoft サポート技術情報の記事 914483「64 ビット バージョンの SQL Server 2005 でバッファー プール メモリのページングを削減する方法」を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=148948](http://go.microsoft.com/fwlink/?LinkId=148948)です。  
  
## <a name="grant-the-semanagevolumename-right-to-the-sql-server-service-account"></a>SQL Server サービス アカウントに SE_MANAGE_VOLUME_NAME を付与します。  
 SQL Server サービスを実行しているアカウントが「実行ボリュームの保守タスク」Windows 特権を持つことを確認またはセキュリティ グループに属していることを確認します。 これは、データベースの自動拡張する場合に最適なパフォーマンスを保証するファイルの瞬時初期化が許可されます。  
  
## <a name="set-min-and-max-server-memory"></a>Min および Max Server Memory を設定します。  
 実行するコンピューター[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]をホストする SQL Server を実行して、BizTalk Server データベースで占有できる必要があります。 "Min server memory"と各 SQL Server インスタンス上の"max server memory"オプションが設定に SQL Server に割り当てるメモリの固定量を指定することをお勧めします。 この場合、する必要があります"min server memory"と"max server memory"、同じ値に設定 (SQL Server が使用される物理メモリの最大量に等しい)。 これが減少それ以外の場合にこれらの値を動的に管理する SQL Server で使用されるオーバーヘッドです。 SQL Server に割り当てるメモリの固定量を指定するには、各 SQL Server コンピューターで、次の T-SQL コマンドを実行します。  
  
```  
sp_configure ‘Max Server memory (MB)’,(max size in MB)  
sp_configure ‘Min Server memory (MB)’,(min size in MB)  
```  
  
 SQL Server のメモリの量を設定すると、前に、合計物理メモリから Windows Server に必要なメモリを差し引くことで適切なメモリ設定を決定します。 これは、SQL Server に割り当てるメモリの最大量です。  
  
> [!NOTE]  
>  ホストする SQL Server を実行するコンピューターが、BizTalk Server データベースもホストする場合、エンタープライズ シングル サインオン マスター シークレット サーバー、したい場合があります、エンタープライズ シングル サインオンを実行するための十分なメモリがあることを確認するには、この値を調整するにはサービス。 マスター シークレット サーバーの高可用性を実現する SQL Server クラスターでクラスター化されたエンタープライズ シングル サインオン サービスのインスタンスを実行することは珍しくの実習ではないです。 エンタープライズ シングル サインオン マスター シークレット サーバーをクラスタ リングの詳細についてを参照してください"Cluster Server する方法、マスター シークレット"で、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]ドキュメント[http://go.microsoft.com/fwlink/?LinkID=106874](http://go.microsoft.com/fwlink/?LinkID=106874)です。  
  
## <a name="split-the-tempdb-database-into-multiple-data-files-of-equal-size-on-each-sql-server-instance-used-by-biztalk-server"></a>Tempdb データベースを同じサイズの BizTalk Server で使用される各 SQL Server インスタンス上の複数のデータ ファイルに分割します。  
 プロポーショナル フィル アルゴリズムを使用しているために重要なことを確認するための tempdb データ ファイルと同じサイズの[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データ ファイルのサイズに基づきます。 このアルゴリズムが、いることを確認しようとしています。[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ほぼ同時に、最大容量に届くようにそのファイル内の空き領域に比例して各ファイルの残りがいっぱいになった。 サイズの異なるデータ ファイルが作成する場合、比例アルゴリズムは、それによってが無意味に複数のデータ ファイルを作成するすべてのファイル間での割り当てを展開するのではなく、GAM の割り当ての最大のファイルを使用します。 少なくとも SQL Server に割り当てられているプロセッサの数と等しくなります tempdb データベースのデータ ファイルの数を構成する必要があります。  
  
## <a name="enable-trace-flag-t1118-as-a-startup-parameter-for-all-instances-of-sql-server"></a>SQL Server のすべてのインスタンスの起動時のパラメーターとしてトレース フラグ-t1118 を実装を有効にします。  
 トレースを実装するフラグ –-t1118 を実装では、ほとんどすべての単一のページ割り当てを削除することで、SQL Server インスタンス間での競合を減らすことができます。 詳細については、Microsoft サポート技術情報の記事 328551 を参照してください。"[prb]: tempdb データベースの同時実行制御の拡張機能"で[http://go.microsoft.com/fwlink/?LinkID=103713](http://go.microsoft.com/fwlink/?LinkID=103713)です。  
  
## <a name="do-not-change-default-sql-server-settings-for-max-degree-of-parallelism-sql-server-statistics-or-database-index-rebuilds-and-defragmentation"></a>Max degree of parallelism、SQL Server 統計情報、またはデータベースのインデックス再構築と最適化の既定の SQL Server 設定を変更しません。  
 SQL Server インスタンスには、BizTalk Server データベースを格納する場合、し、特定の SQL Server 設定する必要があります変更されません。 具体的には、SQL Server max degree of parallelism、メッセージ ボックス データベース、およびデータベースのインデックスの設定 SQL Server の統計を再構築し、最適化は変更できません。 詳細についてを参照してください「SQL Server の設定を変更しないで」で BizTalk Server Operations guide の「 [http://go.microsoft.com/fwlink/?LinkId=114358](http://go.microsoft.com/fwlink/?LinkId=114358)です。