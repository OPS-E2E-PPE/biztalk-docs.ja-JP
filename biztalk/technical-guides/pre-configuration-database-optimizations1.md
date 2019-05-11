---
title: データベースの事前構成 Optimizations1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ebd0b32a-490d-4db2-a1fc-bf3bef93aeea
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30107d8cf3624e22099efb5d14daf59b4e256105
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399578"
---
# <a name="pre-configuration-database-optimizations"></a>前の構成データベースの最適化
BizTalk Server は、Microsoft SQL Server で最大 13 個の独立したデータベースの作成を必要とするデータベースを非常に大量に消費するアプリケーションです。 ため、BizTalk Server 環境で SQL Server が果たす重要な役割が何よりも重要な SQL Server では、最適なパフォーマンスが構成されているチューニングがあります。 実行する SQL Server は、チューニングしない場合は、BizTalk Server で使用されるデータベースがボトルネックになり、BizTalk Server 環境の全体的なパフォーマンスが低下します。 このトピックでは、BizTalk Server をインストールして、BizTalk Server データベースを構成する前に従う必要がありますをいくつかの SQL Server パフォーマンスの最適化について説明します。  
  
## <a name="set-ntfs-file-allocation-unit"></a>NTFS ファイル アロケーション ユニットを設定します。  
 SQL Server では、そのデータを格納する**エクステント**、8 8 K ページのグループします。 そのため、ディスクのパフォーマンスを最適化するために NTFS アロケーション ユニット サイズ 64 KB に設定のベスト プラクティスの記事「展開前 I/O のベスト プラクティス」で使用可能な SQL Server の「ディスク構成のベスト プラクティス」セクションで説明した[ http://go.microsoft.com/fwlink/?LinkId=140818](http://go.microsoft.com/fwlink/?LinkId=140818). SQL Server の詳細についてはページとエクステント トピックを参照して、SQL Server オンライン ブックの「[ページとエクステントについて](http://go.microsoft.com/fwlink/?LinkId=148939)(HYPERLINK"<http://go.microsoft.com/fwlink/?LinkId=148939>" <http://go.microsoft.com/fwlink/?LinkId=148939>)。  
  
## <a name="database-planning-considerations"></a>データベースの計画に関する考慮事項  
 ホストすることをお勧め、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]高速ストレージ (SAN ディスクを高速または高速な SCSI ディスクなど) 上のデータベース。 RAID 5 ではなく、RAID 10 (1 + 0) は、raid 5 が書き込みに低いためお勧めします。 新しい SAN ディスクでは、このような場合は、RAID の選択が重要ではないで非常に大きなメモリ キャッシュがあります。 パフォーマンスを向上させるには、データベースおよびログ ファイルが別の物理ディスクに配置できます。  
  
## <a name="install-the-latest-service-pack-and-cumulative-updates-for-sql-server"></a>SQL Server の最新の service pack と累積的更新プログラムをインストールします。  
 SQL Server 2005 と SQL Server 2008 だけでなく .NET Framework の最新のサービス パックの最新のサービス パックと最新の累積的更新プログラムをインストールします。  
  
## <a name="install-sql-service-packs-on-both-biztalk-server-and-sql-server"></a>BizTalk Server と SQL Server の両方で SQL サービス パックをインストールします。  
 SQL Server のサービス パックをインストールするときにも、BizTalk Server コンピューターにサービス パックをインストールします。 BizTalk Server では、SQL Server のサービス パックによって更新される SQL クライアント コンポーネントを使用します。  
  
## <a name="consider-implementing-the-sql-server-2008-data-collector-and-management-data-warehouse"></a>SQL Server 2008 のデータ コレクターと管理データ ウェアハウスの実装を検討してください。  
 SQL Server 2008 は、新しいの使用に対応環境とデータベースのパフォーマンスを収集するには、データ コレクターや管理データ ウェアハウスに関連したテストと傾向の分析のためのデータ。 データ コレクターは、指定した管理データ ウェアハウスに収集されたすべてのデータを保持します。 これはパフォーマンスの最適化ではありません、これがパフォーマンスの問題の分析に有用になります。  
  
## <a name="grant-the-account-which-is-used-for-sql-server-the-windows-lock-pages-in-memory-privilege"></a>SQL Server の Windows のロックの Pages In Memory 特権に使用されるアカウントに付与します。  
 SQL Server サービス アカウントに特権の Windows の"Lock Pages in Memory"を付与します。 これは、SQL Server プロセスのバッファー プール メモリのページングから物理メモリにバッファー プールに割り当てられたメモリをロックすることにより、Windows オペレーティング システムを防ぐために実行する必要があります。 詳細についてでマイクロソフト サポート技術情報の記事 914483「64 ビット バージョンの SQL Server 2005 でバッファー プール メモリのページングを削減する方法」を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=148948](http://go.microsoft.com/fwlink/?LinkId=148948)します。  
  
## <a name="grant-the-semanagevolumename-right-to-the-sql-server-service-account"></a>SQL Server サービス アカウントに SE_MANAGE_VOLUME_NAME を付与します。  
 SQL Server サービスを実行しているアカウントは、Windows の「ボリュームの保守タスクを実行する」特権を持つことを確認またはセキュリティ グループに属していることを確認します。 これにより、データベースが自動拡張する必要がある場合に最適なパフォーマンスを保証するファイルの瞬時初期化が許可されます。  
  
## <a name="set-min-and-max-server-memory"></a>Min と Max Server Memory を設定します。  
 実行するコンピューター[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]をホストする BizTalk Server データベースを SQL Server を実行する専用必要があります。 SQL Server に割り当てるメモリの固定量を指定する、"min server memory"と各 SQL Server インスタンス上の"max server memory"オプションが設定されていることをお勧めします。 この場合、する必要があります設定する"min server memory"と"max server memory"を同じ値 (SQL Server を使用する物理メモリの最大量に等しい)。 これが減少オーバーヘッドはそれ以外の場合これらの値を動的に管理する SQL Server によって使用されます。 SQL Server に割り当てるメモリの固定量を指定するには、各 SQL Server コンピューターで、次の T-SQL コマンドを実行します。  
  
```  
sp_configure ‘Max Server memory (MB)’,(max size in MB)  
sp_configure ‘Min Server memory (MB)’,(min size in MB)  
```  
  
 SQL Server のメモリの量を設定する前に、Windows Server に必要な合計物理メモリからメモリを差し引くことで、適切なメモリ設定を決定します。 これは、SQL Server に割り当てるメモリの最大量です。  
  
> [!NOTE]  
>  ホストする SQL Server を実行するコンピューター、BizTalk Server データベースも、エンタープライズ シングル サインオン マスター シークレット サーバーをホストし場合エンタープライズ シングル サインオンを実行するための十分なメモリがあることを確認するには、この値を調整するにはサービス。 マスター シークレット サーバーの高可用性を実現する SQL Server クラスターでエンタープライズ シングル サインオン サービスのクラスター化されたインスタンスを実行するは珍しい方法ではありません。 エンタープライズ シングル サインオン マスター シークレット サーバーをクラスタ リングに関する詳細についてを参照してください「方法にクラスターのマスター シークレット サーバー」で BizTalk server のマニュアル[ http://go.microsoft.com/fwlink/?LinkID=106874](http://go.microsoft.com/fwlink/?LinkID=106874)します。  
  
## <a name="split-the-tempdb-database-into-multiple-data-files-of-equal-size-on-each-sql-server-instance-used-by-biztalk-server"></a>Tempdb データベースを BizTalk Server で使用される各 SQL Server インスタンスに等しいサイズの複数のデータ ファイルに分割します。  
 比例書き込みアルゴリズムが使用されるため、tempdb に使用されるデータ ファイルが同じサイズのことを確認は重要[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]はデータ ファイルのサイズに基づきます。 このアルゴリズムが、いることを確認しようとしています。[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]塗りつぶしがほぼ同時で最大の容量に到達するようにそのファイルで空き領域に比例して各ファイルのままです。 サイズの異なるデータ ファイルが作成、比例書き込みアルゴリズムは、一番大きいファイルを複数のデータ ファイルを作成する目的にそぐわなくなりますそれによって、すべてのファイル間の割り当てを展開するのではなく、GAM 割り当てを使用します。 Tempdb データベースのデータ ファイルの数は、SQL Server に割り当てられているプロセッサの数の値以上にするように構成する必要があります。  
  
## <a name="enable-trace-flag-t1118-as-a-startup-parameter-for-all-instances-of-sql-server"></a>SQL Server のすべてのインスタンスの起動時のパラメーターとしてトレース フラグ-t1118 を実装を有効にします。  
 トレースを実装する – フラグ-t1118 を実装では、ほぼすべての単一ページの割り当てを削除することで、SQL Server インスタンス間で競合を減らすことができます。 詳細については、マイクロソフト サポート技術情報記事 328551 を参照してください。"[prb]。同時実行機能が tempdb データベースの" [ http://go.microsoft.com/fwlink/?LinkID=103713](http://go.microsoft.com/fwlink/?LinkID=103713)します。  
  
## <a name="do-not-change-default-sql-server-settings-for-max-degree-of-parallelism-sql-server-statistics-or-database-index-rebuilds-and-defragmentation"></a>Max degree of parallelism、SQL Server の統計、またはデータベースのインデックス再構築と最適化の既定の SQL Server 設定を変更しません。  
 SQL Server インスタンスには、BizTalk Server データベースを格納する場合、し、特定の SQL Server 設定する必要があります変更されません。 具体的には、並列処理の最大限度の SQL Server、SQL Server の統計をメッセージ ボックス データベースとデータベースのインデックスの設定を再構築し、最適化を変更しないでください。 詳細についてを参照してください「SQL Server の設定を変更しないこと」で BizTalk Server 運用ガイド[ http://go.microsoft.com/fwlink/?LinkId=114358](http://go.microsoft.com/fwlink/?LinkId=114358)します。