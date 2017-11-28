---
title: "バックアップの BizTalk Server のジョブを構成する |Microsoft ドキュメント"
description: 
ms.custom: 
ms.date: 11/22/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 026622c9-fcb4-4db0-af48-1379feb30372
caps.latest.revision: "42"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1afb4f28584d65401220761dcee626fe63f913b
ms.sourcegitcommit: f4c0d7bc4b617688c643101a34062db90014851a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2017
---
# <a name="configure-the-backup-biztalk-server-job"></a>バックアップの BizTalk Server のジョブを構成します。
インストールし、BizTalk Server を構成した後は、バックアップを構成する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データをバックアップするジョブです。 

**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]Feature Pack 2**データベースのバックアップおよび、ログ ファイルを Azure blob ストレージ アカウントにすることができます。 


## <a name="overview"></a>概要
**Backup BizTalk Server (BizTalkMgmtDb)**ジョブには、次の手順が含まれています。

-   手順 1 –**セット圧縮オプション**: を有効にするか、バックアップ中に圧縮を無効にします。

-   手順 2 – **BackupFull**: 完全なデータベース、BizTalk Server データベースのバックアップの実行

-   手順 3 – **MarkAndBackUpLog**: BizTalk Server データベースのログ バックアップ

-   手順 4 –**バックアップ履歴をクリア**: バックアップ履歴が保持される期間を選択

このジョブを構成するのには、する必要があります。  
  
-   プライマリ サーバーと移行先の SQL Server とその他のバックアップ オプションを確認します。
  
-   データベースをバックアップする Windows ユーザー アカウントを選択し、このアカウントに SQL Server ログインの作成
  
-   SQL Server ログインを BizTalk Server データベース内の BTS_BACKUP_USERS データベース ロールにマップします。
  
-   すべてのノードで MSDTC サービスをアクティブにします。 それ以外の場合、ソース ノードと送信先ノード間のリンク サーバーの追加は失敗します。
  
## <a name="before-you-begin"></a>アンインストールの準備  
  
-   特定の構成およびバックアップ操作には、sysadmin SQL Server ロールのメンバーシップが必要とします。 バックアップするには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースが SQL Server の sysadmin サーバー ロールのメンバーであるアカウントを使用して、プライマリ サーバーにサインインします。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成では、BTS_BACKUP_USERS データベース ロールを追加します。 データベースをバックアップに使用するユーザー アカウントには、プライマリ サーバーを除く、バックアップには、関連するすべての SQL Server のシステム管理者 (sysadmin SQL Server ロール) のアクセス許可は不要です。  
  
-   実行に使用するサインイン アカウントを決める、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースのバックアップ。 ローカル アカウントを使用することができ、1 つ以上のアカウントを使用することができます。 一般に簡素化され、この目的専用の専用の 1 つの Windows ドメイン ユーザー アカウントを作成する方が安全です。 このユーザー用の SQL Server ログオン アカウントを構成し、バックアップ プロセスに参加するすべての SQL Server について、プライマリ (送信元) サーバーかセカンダリ (送信先) サーバーかにかかわらず、ユーザーを SQL Server ログインにマップする必要があります。 各 BizTalk BTS_BACKUP_USERS データベース ロールにこのユーザーを割り当てる、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]をバックアップするデータベースします。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブでは、期限切れのバックアップ ファイルが削除されないので、ディスク領域を節約するにはこれらのバックアップ ファイルを手動で管理する必要があります。 データベースの完全バックアップを新規作成した後で、プライマリ ディスクの領域を再利用できるように、期限切れのバックアップ ファイルをアーカイブ ストレージ デバイスに移動します。 参照してください、 [SSIS パッケージ](http://www.biztalkbill.com/2015/05/26/ssis-packages-to-help-management-biztalk-server-environments/)をこれらのファイルを管理します。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]BizTalk 追跡データベースに直接追跡データは書き込まれませんなくメッセージ ボックス データベースにデータをキャッシュしてから、BizTalk 追跡データベースに移動します。 メッセージ ボックス データの損失が発生した場合は、追跡データも一部が失われている可能性があります。  
  
## <a name="prerequisites"></a>前提条件  
* SQL Server の sysadmin SQL Server ロールのメンバーであるアカウントを使用してにサインインします。  
  
* SQL Server エージェント サービスは、SQL Server の各インスタンス上にユーザー ログインがマップされたドメイン アカウントまたはローカル アカウントで実行されるように構成します。ローカル アカウントも使用できますが、ドメイン アカウントの使用をお勧めします。  

* Azure blob ストレージ アカウントを使用する必要があります、[汎用ストレージ アカウント](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account#create-a-storage-account)、blob ストレージ アカウント内のコンテナー、[共有アクセス署名](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url#SAS)(SAS)、および[SQL 資格情報SAS を使用して](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url#credential)です。 作成した後、blob サービス エンドポイントの URL、https:// のようなものであるがある*yourstorageaccount*.blob.core.windows.net/*containername*です。 

    > [!TIP]
    > 既存の blob ストレージ アカウント、SAS を使用して構成していない場合、 [SAS PowerShell スクリプト](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url#SAS)およびコンテナーを作成できます。 [SQL Server Backup to URL](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url)概要については、および特定の手順を示します。
  
## <a name="configure-the-job"></a>ジョブを構成します。  
  
1.  BizTalk 管理データベースをホストする SQL Server で開く**SQL Server Management Studio**に接続し、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。  
  
2.  **[SQL Server エージェント]** を展開し、**[ジョブ]** を展開します。  
  
3.  右クリック**Backup BizTalk Server (BizTalkMgmtDb)**選択**プロパティ**です。 ジョブのプロパティで選択**手順**です。  
  
4.  選択、 **Set Compression Option**ステップ、および選択**編集**:  

    このステップでは、`sp_SetBackupCompression`ストアド プロシージャに値を設定する BizTalk 管理データベース (BizTalkMgmtDb) で、`adm_BackupSettings`テーブル。 ストアド プロシージャが 1 つのパラメーター:  **@bCompression**です。 既定では、その設定は**0** (バックアップの圧縮がオフ)。 圧縮を適用する値に変更**1**:  
  
    ```  
    exec [dbo].[sp_SetBackupCompression] @bCompression = 1 /*0 - Do not use Compression, 1 - Use Compression */  
    ```  
  
     **[OK]** を選択します。  
  
5.  選択、 **BackupFull**ステップ、および選択**編集**です。 **コマンド**ボックスで、パラメーター値を更新します。  
  
    1. **頻度**: 既定値は**d** (毎日) です。 これは推奨される設定です。 その他の値を含める**h** (1 時間ごと)、 **w** (毎週)、 **m** (毎月)、または**y** (毎年)。  
  
    2. **名前**: 既定値は**BTS**です。 この名前は、バックアップ ファイル名の一部として使用されます。  
  
    3. **バックアップ ファイルの場所**: 置換 '*\<先のパス >*' 完全なパス (パスは、単一引用符を含める必要があります) へのバックアップを作成するフォルダー、コンピューター、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース、または Azure blob ストレージ アカウントに blob サービス エンドポイントの URL。  

        > [!IMPORTANT]
        > - ローカルのパスを入力するかどうかは、ターゲット システム上の同じフォルダーにすべてのファイルを手動でコピーする必要があるされるたびにバックアップ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブを新しいファイルを作成します。  
        >   
        >      リモート パスを使用するには、UNC 共有をように入力\\ \\  *\<ServerName >*\\*\<SharedDrive >*\\、ここで *\<ServerName >* 、ファイル サーバーの名前を指定し、  *\<SharedDrive >*共有ドライブまたはフォルダーの名前を指定します。  
        >   
        >      ネットワーク経由でデータをバックアップする場合は、ネットワークの影響を受けます。 リモートの場所を使用する場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブの完了時にバックアップが成功したかどうか確認します。  
        > - データ損失の可能性を回避するには、バックアップ ディスクを、データベースのデータ ディスクおよびログ ディスクとは異なるディスクに構成します。 これは、データやログのディスクに障害が発生した場合にバックアップにアクセスするために必須です。  
        > - Azure blob アカウントへのバックアップの入力と、 **Blob サービスのエンドポイント**、blob サービスのプロパティにリストされている URL とコンテナー名、 [Azure ポータル](https://portal.azure.com)です。

    4. 省略可。 **部分バックアップ障害の後に完全バックアップの force** (@ForceFullBackupAfterPartialSetFailure): 既定値は**0**します。 ログのバックアップに失敗した場合、次の完全バックアップの間隔に到達するまで、完全バックアップは実行されませんでした。 置き換える**1**ログ バックアップの失敗が発生するたびに、完全バックアップが実行された場合。
    
    5. 省略可。 **バックアップ プロセスの実行のローカル時刻を 1 時間**(@BackupHour)。 既定値は**NULL**です。 バックアップ ジョブに関連付けられていないのタイム ゾーン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]時刻 (0000) のコンピューター、および午前 0 時 (utc) で実行されます。 する場合のタイム ゾーンでの特定の時間にバックアップ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターが現地時間として整数値を 0 (深夜) から 23 (11 PM) に入力します。 

    6. 省略可。 **ローカル時刻を使用して**(@UseLocalTime): ローカル時刻を使用する手順を示します。 既定値は**0**、現在の UTC 時刻 – GETUTCDATE() – 2007-05-04 01:34:11.933 を使用しています。 場合設定**1**、ローカル時刻 – GETDATE() – 2007-05-03 18:34:11.933 を使用して、
  
    次の例では、毎日のバックアップが午前 2 は、作成され、m:\ ドライブに格納されています。  
  
    ```  
    exec [dbo].[sp_BackupAllFull_Schedule]   
    'd' /* Frequency */,   
    'BTS' /* Name */,   
    'm:\BizTalkBackups' /* location of backup files */,   
    '0' /* 0 (default) or 1 ForceFullBackupAfterPartialSetFailure */,   
    '2' /* local time hour for the backup process to run */  
    ```  

    次の例では、毎週のバックアップは UTC 時刻で午前 0 時に作成され、Azure blob アカウントに格納されています。 

    ```  
    exec [dbo].[sp_BackupAllFull_Schedule]   
    'w' /* Frequency */,   
    'BTS' /* Name */,   
    'http://yourstorageaccount.blob.core.windows.net/yourcontainer/' /* location of backup files */,   
    '1' /* 0 (default) or 1 ForceFullBackupAfterPartialSetFailure */
    ```  

     **[OK]** を選択します。  
  
6.  選択、 **MarkAndBackupLog**ステップ、および選択**編集**です。 **コマンド**ボックスで、パラメーター値を更新します。  
  
    1.  **@MarkName**: これは、バックアップ ファイルの名前付け規則の一部: <Server Name>  _<Database Name> **_ログ_**< Log Mark Name >_<Timestamp>  
    
    2.  **@BackupPath**: 完全な宛先 (単一引用符を含む)、コンピューターおよびフォルダー パスに格納する、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 、データベースのログ、または Azure blob ストレージ アカウントとコンテナー。 *\<先のパス >*ローカルまたは別のサーバーへの UNC パスにもなります。  
  
     MarkAndBackupLog ステップで、バックアップのログをマークした後、バックアップします。  
  
    > [!IMPORTANT]
    >  回避する**データ損失の可能性**および**パフォーマンスを向上させる**、 *\<先のパス >*別のコンピューター、またはハード ドライブに設定する必要があります元のデータベース ログを格納するために使用されると異なる。  
  
     **[OK]** を選択します。  
  
7.  選択、 **Clear Backup History**ステップ、および選択**編集**です。 **コマンド**ボックスで、パラメーター値を更新します。  
  
    1.  **@DaysToKeep**: 既定値は**14 日間**です。 バックアップ履歴が保持される期間決定、`Adm_BackupHistory`テーブル。 管理は、定期的にバックアップ履歴の消去、`Adm_BackupHistory`適切なサイズにテーブルです。 
    
    2.  省略可。 **@UseLocalTime**: ローカル時刻を使用する手順を説明します。 既定値は 0 です。 現在の UTC 時刻 – GETUTCDATE() – 2007-05-04 01:34:11.933 を使用します。 かどうか 1 に設定を使用してローカル時刻 – GETDATE() – 2007-05-03 18:34:11.933
  
    ```  
    exec [dbo].[sp_DeleteBackupHistory] @DaysToKeep=14, @UseLocalTime =1 
    ```  
  
    > [!NOTE]
    >  この手順**しない**バックアップ ファイルの保存先のパスから削除します。  
    
     選択**OK**してすべてのプロパティ ウィンドウを閉じます。  
  
8.  省略可。 バックアップのスケジュールを変更します。 参照してください[バックアップの BizTalk Server のジョブをスケジュールする方法](../core/how-to-schedule-the-backup-biztalk-server-job.md)です。  
  
    > [!NOTE]
    >  バックアップ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブが初めて構成することを実行します。 既定では、後続の実行、バックアップ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブは 1 日に 1 回完全バックアップを完了して、15 分ごとにログ バックアップを完了します。  
  
9. 右クリックし、 **Backup BizTalk Server**ジョブ、および選択**を有効にする**です。 状態に変更する必要があります**成功**です。  

## <a name="execute-backupsetupallprocssql-and-logshippingdestinationlogicsql"></a>Backup_Setup_All_Procs.sql および LogShipping_Destination_Logic.sql を実行します。

**[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]機能パック 2 (FP2)**で Backup_Setup_All_Procs.sql および LogShipping_Destination_Logic.sql スクリプトを使用する`\Program Files (x86)\Microsoft BizTalk Server *your version*\Schema`です。 

BizTalk Server のバックアップ ジョブが既に構成されているし、切り替えたい場合は、Azure を使用する (ディスク) ではなく blob も、次の操作します。 

1. SQL Server を実行、 `Backup_Setup_All_Procs.sql` BizTalk Server のバックアップ ジョブでバックアップされているすべてのカスタム データベースに対してスクリプト。 既定では、FP2 自動的に更新プログラムの BizTalk データベースです。カスタム データベースは更新されません (それらのデータベースで、 `adm_OtherBackupDatabases` BizTalkMgmtDb 内のテーブル)。

    [バックアップをカスタム データベース](how-to-back-up-custom-databases.md)カスタム データベースの詳細を提供します。 

2. **使用する場合[ログ配布](log-shipping.md)**、SQL Server 内で、送信先システムで LogShipping_Destination_Logic.sql スクリプトを実行します。 使用しない場合は、ログ配布、し、このスクリプトを実行しないでください。

    [ログ配布の送信先システムを構成する](how-to-configure-the-destination-system-for-log-shipping.md)送信先システムで詳細を提供します。

## <a name="spforcefullbackup-stored-procedure"></a>sp_ForceFullBackup ストアド プロシージャ  
  
**Sp_ForceFullBackup**ストアド プロシージャ、 **BizTalkMgmtDb**データベースは、アドホックのデータとログ ファイルの完全バックアップを実行するために使用できます。 ストアド プロシージャで、adm_ForceFullBackup テーブルの値を 1 にして更新します。 次回のバックアップ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブを実行すると、データベースの完全バックアップ セットを作成します。  
  
## <a name="next-steps"></a>次の手順  
 [ログ配布の送信先システムを構成します。](../core/how-to-configure-the-destination-system-for-log-shipping.md)   
 [BizTalk Server のバックアップ ジョブのスケジュールを設定する](../core/how-to-schedule-the-backup-biztalk-server-job.md)  
 [Azure ストレージ アカウント](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account)  
 [SQL Server Backup to URL](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url)
