---
title: "バックアップの BizTalk Server ジョブを構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tracking database, backing up
- backing up, Tracking database
- backing up, user accounts
- backing up, MessageBox database
- databases, backing up
- MessageBox database, backing up
- backing up, databases
- backing up, prerequisites
- configuring, backup jobs
- backing up, warnings
- backing up, backup jobs
- user accounts, backing up
- backing up, configuring
ms.assetid: 026622c9-fcb4-4db0-af48-1379feb30372
caps.latest.revision: "42"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 488e76c3d29c58107e85ad58ed4fad50de671315
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-backup-biztalk-server-job"></a>BizTalk Server のバックアップ ジョブを構成する方法
このトピックでは、BizTalk Server のバックアップ ジョブを構成するために必要な手順を説明します。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をバックアップする前に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブを構成する必要があります。 バックアップを構成するには、次のタスクのほとんどまたはすべてを実行する必要があります。  
  
-   SQL Server エージェントを編集**Backup BizTalk Server (BizTalkMgmtDb)**ジョブをプライマリ サーバーと移行先の SQL Server とその他のバックアップ オプションを識別します。  
  
-   データベースのバックアップに使用する Windows ユーザー アカウントを選択し、このアカウントの SQL Server ログインを作成します。  
  
-   BizTalk Server データベースの BTS_BACKUP_USERS データベース ロールには、SQL Server ログインをマップします。  
  
-   すべてのノードで MSDTC サービスをアクティブにします。 それ以外の場合、ソース ノードと送信先ノード間のリンク サーバーの追加は失敗します。  
  
## <a name="before-you-begin"></a>アンインストールの準備  
  
-   この操作のような特定の構成およびバックアップ操作には、sysadmin SQL Server ロールのメンバーシップが必要です。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースをバックアップするには、プライマリ サーバー上の SQL Server の sysadmin サーバー ロールに属するアカウントでプライマリ サーバーにログオンする必要があります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 構成には BTS_BACKUP_USERS という名前のデータベース ロールが追加されているため、データベースのバックアップに使用するユーザー アカウントは、プライマリ サーバーを除いて、バックアップに関係するすべての SQL Server 上でのシステム管理者 (sysadmin SQL Server ロール) のアクセス許可を必要としません。  
  
-   実行に使用するログイン アカウントを決定する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースのバックアップ。 ローカル アカウントを使用できます。複数のアカウントを使用できますが、通常は、この目的に限定した専用の Windows ドメイン ユーザー アカウントを 1 つ作成する方が簡単で安全です。 このユーザー用の SQL Server ログオン アカウントを構成し、バックアップ プロセスに参加するすべての SQL Server について、プライマリ (送信元) サーバーかセカンダリ (送信先) サーバーかにかかわらず、ユーザーを SQL Server ログインにマップする必要があります。 各 BizTalk BTS_BACKUP_USERS データベース ロールにこのユーザーを割り当てる、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]をバックアップするデータベースします。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブでは、期限切れのバックアップ ファイルが削除されないので、ディスク領域を節約するにはこれらのバックアップ ファイルを手動で管理する必要があります。 データベースの完全バックアップを新規作成した後で、プライマリ ディスクの領域を再利用できるように、期限切れのバックアップ ファイルをアーカイブ ストレージ デバイスに移動します。 "BizTalk Bill"は、ダウンロード可能な[SSIS パッケージ](http://www.biztalkbill.com/2015/05/26/ssis-packages-to-help-management-biztalk-server-environments/)をこれらのファイルを管理します。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、追跡データを BizTalk 追跡データベースに直接書き込むのではなく、メッセージボックス データベースにデータをキャッシュしてから、BizTalk 追跡データベースに移動します。 メッセージ ボックス データの損失が発生した場合は、追跡データも一部が失われている可能性があります。  
  
## <a name="prerequisites"></a>前提条件  
* SQL Server の sysadmin SQL Server ロールのメンバーであるアカウントを使用してにサインインします。  
  
* SQL Server エージェント サービスは、SQL Server の各インスタンス上にユーザー ログインがマップされたドメイン アカウントまたはローカル アカウントで実行されるように構成します。ローカル アカウントも使用できますが、ドメイン アカウントの使用をお勧めします。  
  
## <a name="configure-the-backup-biztalk-server-job"></a>BizTalk Server のバックアップ ジョブを構成します。  
  
1.  BizTalk 管理データベースをホストする SQL Server で開く**SQL Server Management Studio**に接続し、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。  
  
2.  **[SQL Server エージェント]** を展開し、**[ジョブ]** を展開します。  
  
3.  右クリック**Backup BizTalk Server (BizTalkMgmtDb)**選択**プロパティ**です。 ジョブのプロパティで選択**手順**です。  
  
4.  選択、 **Set Compression Option**  を選択**編集**です。 **コマンド**ボックスで、値を 1 に変更します。  
  
    ```  
    exec [dbo].[sp_SetBackupCompression] @bCompression = 1 /*0 - Do not use Compression, 1 - Use Compression */  
    ```  
  
     [ **OK**] を選択します。  
  
5.  選択、 **BackupFull**  を選択**編集**です。 **コマンド**ボックスで、パラメーターの値を編集します。  
  
    1.  **頻度**: 既定値は**d** (毎日) です。 この設定をお勧めします。 その他の値を含める**h** (1 時間ごと)、 **w** (毎週)、 **m** (毎月)、または**y** (毎年)。  
  
    2.  **名前**: 既定値は**BTS**です。 この名前は、バックアップ ファイル名の一部として使用されます。  
  
    3.  **バックアップ ファイルの場所**: 置換 '*\<先のパス >*' 完全なパス (パスは、単一引用符を含める必要があります) へのバックアップを作成するフォルダー、コンピューター、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。  
  
        > [!IMPORTANT]
        >  -   ローカル パスを指定した場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブでファイルが新規作成されるたびに、すべてのファイルを送信先システムの同じフォルダーに手動でコピーする必要があります。  
        >   
        >      リモート パスを指定するには、UNC 共有をように入力\\ \\  *\<ServerName >*\\*\<SharedDrive >* \\、ここで *\<ServerName >* 、ファイル サーバーの名前を指定し、  *\<SharedDrive >*共有ドライブまたはフォルダーの名前を指定します。  
        >   
        >      ネットワーク経由でデータをバックアップする場合は、ネットワークの影響を受けます。 リモートの場所を使用する場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブの完了時にバックアップが成功したかどうか確認します。  
        > -   データ損失の可能性を回避するには、バックアップ ディスクを、データベースのデータ ディスクおよびログ ディスクとは異なるディスクに構成します。 これは、データやログのディスクに障害が発生した場合にバックアップにアクセスするために必須です。  
  
    4.  **部分バックアップ障害の後に完全バックアップの force**: 既定値は**0**が指定されていないときにすることを意味する場合、ログ バックアップは失敗し、[次へ] の完全バックアップの間隔に達するまで完全バックアップは実行されません。 置き換える**1**完全バックアップをログ バックアップの失敗が発生するたびに行う場合します。  
  
    5.  **バックアップ プロセスの実行のローカル時刻を 1 時間**: 既定値は NULL 指定しない場合、つまり、そのバックアップ ジョブに関連付けられていないのタイム ゾーン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]タイム (0000) のコンピューターとそのための午前 0 時 (utc) で実行されます。 特定の時刻のタイム ゾーンで実行するバックアップを作成する場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューター、整数値 0 (深夜) から 23 (11 PM) として入力のローカル時刻の時間、 **BackupHour**パラメーター。  
  
     次の例では、毎日のバックアップが午前 2 時に作成され、ドライブ m:\ に保存されます。  
  
    ```  
    exec [dbo].[sp_BackupAllFull_Schedule]   
    'd' /* Frequency */,   
    'BTS' /* Name */,   
    'm:\BizTalkBackups' /* location of backup files */,   
    0 /* 0 (default) or 1 ForceFullBackupAfterPartialSetFailure */,   
    '2' /* local time hour for the backup process to run */  
    ```  
  
     [ **OK**] を選択します。  
  
6.  選択、 **MarkAndBackupLog**  を選択**編集**です。 **コマンド**ボックスで、置き換える**'***\<先のパス >***'**への完全パス (単一引用符を含む) で、コンピューターおよび保存するフォルダー、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース ログ。 *\<先のパス >*ローカル パスまたは別のサーバーへの UNC パスになる可能性があります。  
  
     MarkAndBackupLog ステップで、バックアップのログをマークした後、バックアップします。  
  
    > [!IMPORTANT]
    >  データ損失の可能性を回避する、 *\<先のパス >*元のデータベースのログを使用するコンピューターとは異なるデータベース ログを格納するコンピューターを指定する必要があります。  
  
     [ **OK**] を選択します。  
  
7.  選択、 **Clear Backup History**  を選択**編集**です。 **コマンド**ボックスで、変更**DaysToKeep =***\<番号 >*バックアップ履歴を保持する日数を指定します。  
  
    ```  
    exec [dbo].[sp_DeleteBackupHistory] @DaysToKeep=14  
    ```  
  
    > [!NOTE]
    >  **DaysToKeep**バックアップ履歴が保持される期間、Adm_BackupHistory テーブルにパラメーターを指定します。 定期的にバックアップ履歴を消去すると、Adm_BackupHistory テーブルを適切なサイズで維持することができます。 既定値、 **DaysToKeep**パラメーターが 14 日間です。  
  
     選択**OK**してすべてのプロパティ ウィンドウを閉じます。  
  
8.  省略可。 バックアップのスケジュールを変更します。 参照してください[バックアップの BizTalk Server のジョブをスケジュールする方法](../core/how-to-schedule-the-backup-biztalk-server-job.md)です。  
  
    > [!NOTE]
    >  バックアップ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブが初めて構成することを実行します。 既定でそれ以降は、Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] により完全バックアップが 1 日 1 回実行され、ログ バックアップが 15 分ごとに実行されます。  
  
9. 右クリックし、 **Backup BizTalk Server**のジョブし、選択**を有効にする**です。 状態に変更する必要があります**成功**です。  
  
## <a name="spforcefullbackup-stored-procedure"></a>sp_ForceFullBackup ストアド プロシージャ  
  
> [!NOTE]
>  BizTalkMgmtDb データベースの sp_ForceFullBackup ストアド プロシージャを使用すれば、データ ファイルとログ ファイルの完全バックアップを随時実行できます。 ストアド プロシージャで、adm_ForceFullBackup テーブルの値を 1 にして更新します。 次回のバックアップ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブを実行すると、データベースの完全バックアップ セットを作成します。  
  
## <a name="next-steps"></a>次の手順  
 [ログ配布用に送信先システムを構成する方法](../core/how-to-configure-the-destination-system-for-log-shipping.md)  
  
## <a name="see-also"></a>参照  
 [バックアップの BizTalk Server のジョブをスケジュールする方法](../core/how-to-schedule-the-backup-biztalk-server-job.md)