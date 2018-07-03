---
title: バックアップ BizTalk Server ジョブの構成 |Microsoft Docs
description: ''
ms.custom: ''
ms.date: 11/22/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 026622c9-fcb4-4db0-af48-1379feb30372
caps.latest.revision: 42
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64a6222ffbabad54d8908a7d8da5517786d9a0cc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981091"
---
# <a name="configure-the-backup-biztalk-server-job"></a>バックアップ BizTalk Server ジョブを構成します。
インストールして、BizTalk Server を構成した後は、バックアップを構成する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データをバックアップするジョブ。 

**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]Feature Pack 2**データベースをバックアップしてファイルを Azure blob ストレージ アカウントにログインします。 


## <a name="overview"></a>概要
**BizTalk Server のバックアップ (BizTalkMgmtDb)** ジョブには、次の手順が含まれています。

-   手順 1 –**圧縮オプションのセット**: を有効にするか、バックアップ中に圧縮を無効にします。

-   手順 2 – **BackupFull**: 完全なデータベース、BizTalk Server データベースのバックアップの実行

-   手順 3 – **MarkAndBackUpLog**: BizTalk Server データベースのログをバックアップします。

-   手順 4 –**バックアップ履歴を消去する**: バックアップの履歴が保持される期間を選択

このジョブを構成するには、する必要があります。  
  
-   プライマリ サーバーと移行先の SQL サーバーとその他のバックアップ オプション
  
-   データベースをバックアップする Windows ユーザー アカウントを選択し、このアカウントの SQL Server ログインを作成
  
-   SQL Server ログインを BizTalk Server データベース内の BTS_BACKUP_USERS データベース ロールにマップします。
  
-   すべてのノードで MSDTC サービスをアクティブにします。 それ以外の場合、ソース ノードと宛先ノードの間のリンク サーバーの追加は失敗します。
  
## <a name="before-you-begin"></a>アンインストールの準備  
  
- 特定の構成およびバックアップ操作には、sysadmin SQL Server ロールのメンバーシップが必要とします。 バックアップするため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースが SQL Server の sysadmin サーバー ロールのメンバーであるアカウントを使用して、プライマリ サーバーにサインインします。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 構成では、BTS_BACKUP_USERS データベース ロールに追加します。 データベース バックアップに使用するユーザー アカウントでは、プライマリ サーバーを除いて、バックアップに関係するすべての SQL Server のシステム管理者 (sysadmin SQL Server ロール) のアクセス許可は必要ありません。  
  
- 実行に使用するサインイン アカウントを決定する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースのバックアップ。 ローカル アカウントを使用して、1 つ以上のアカウントを使用することができます。 一般に簡素化され、この用途専用で専用の 1 つの Windows ドメイン ユーザー アカウントを作成した方が安全です。 このユーザー用の SQL Server ログオン アカウントを構成し、バックアップ プロセスに参加するすべての SQL Server について、プライマリ (送信元) サーバーかセカンダリ (送信先) サーバーかにかかわらず、ユーザーを SQL Server ログインにマップする必要があります。 各 BizTalk BTS_BACKUP_USERS データベース ロールにこのユーザーを割り当てる、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]をバックアップするデータベースします。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブでは、期限切れのバックアップ ファイルが削除されないので、ディスク領域を節約するにはこれらのバックアップ ファイルを手動で管理する必要があります。 データベースの完全バックアップを新規作成した後で、プライマリ ディスクの領域を再利用できるように、期限切れのバックアップ ファイルをアーカイブ ストレージ デバイスに移動します。 参照してください、 [SSIS パッケージ](http://www.biztalkbill.com/2015/05/26/ssis-packages-to-help-management-biztalk-server-environments/)これらのファイルを管理します。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] BizTalk 追跡データベースに直接追跡データを書き込みませんなく、メッセージ ボックス データベースにデータをキャッシュしてから、BizTalk 追跡データベースに移動します。 メッセージ ボックス データの損失が発生した場合は、追跡データも一部が失われている可能性があります。  
  
## <a name="prerequisites"></a>前提条件  
* SQL Server の sysadmin SQL Server ロールのメンバーであるアカウントを使用してにサインインします。  
  
* SQL Server エージェント サービスは、SQL Server の各インスタンス上にユーザー ログインがマップされたドメイン アカウントまたはローカル アカウントで実行されるように構成します。ローカル アカウントも使用できますが、ドメイン アカウントの使用をお勧めします。  

* Azure blob ストレージ アカウントを使用する必要が、 [general purpose ストレージ アカウント](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account#create-a-storage-account)、blob ストレージ アカウント内のコンテナーを[共有アクセス署名](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url#SAS)(SAS) と[SQL 資格情報SAS を使って](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url#credential)します。 作成されると、blob サービス エンドポイントの URL、https:// ようなものであるがある<em>yourstorageaccount</em>.blob.core.windows.net/*containername*します。 

    > [!TIP]
    > 既存の blob ストレージ アカウントの SAS を使用して構成していない場合、 [SAS PowerShell スクリプト](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url#SAS)およびコンテナーを作成できます。 [SQL Server Backup to URL](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url)概要についてと具体的な手順を提供します。
  
## <a name="configure-the-job"></a>ジョブを構成します。  
  
1. BizTalk 管理データベースをホストする SQL Server で開きます**SQL Server Management Studio**に接続して、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。  
  
2. **[SQL Server エージェント]** を展開し、**[ジョブ]** を展開します。  
  
3. 右クリック**BizTalk Server のバックアップ (BizTalkMgmtDb)** 選択**プロパティ**します。 ジョブのプロパティで選択**手順**します。  
  
4. 選択、 **Set Compression Option**手順、および選択**編集**:  

   このステップでは、`sp_SetBackupCompression`で値を設定する BizTalk 管理データベース (BizTalkMgmtDb) にストアド プロシージャ、`adm_BackupSettings`テーブル。 ストアド プロシージャが 1 つのパラメーター:  <strong>@bCompression</strong>します。 既定では、設定が**0** (バックアップの圧縮はオフ)。 圧縮を適用する値に変更**1**:  
  
   ```  
   exec [dbo].[sp_SetBackupCompression] @bCompression = 1 /*0 - Do not use Compression, 1 - Use Compression */  
   ```  
  
    **[OK]** を選択します。  
  
5. 選択、 **BackupFull**手順、および選択**編集**します。 **コマンド**ボックスに、パラメーター値を更新します。  
  
   1. **頻度**: 既定値は**d** (毎日) です。 これは推奨の設定。 その他の値が含まれます**h** (時間)、 **w** (毎週)、 **m** (毎月)、または**y** (年単位)。  
  
   2. **名前**: 既定値は**BTS**します。 この名前は、バックアップ ファイル名の一部として使用されます。  
  
   3. **バックアップ ファイルの場所**: 置換 '*\<宛先パス\>*' をコンピューターと、をバックアップするフォルダーに完全パス(パスは、単一引用符を含める必要があります)で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース、または Azure blob storage アカウントに blob サービス エンドポイントの URL。  

      > [!IMPORTANT]
      > - ローカル パスを入力するかどうかは、ターゲット システム上の同じフォルダーにすべてのファイルを手動でコピーする必要があるたびに、バックアップ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブには、新しいファイルが作成されます。  
      > 
      >      リモート パスを使用するには、UNC 共有をなど入力\\ \\  *\<ServerName\>*\\*\<SharedDrive\>* \\ここで、 *\<ServerName\>* 、ファイル サーバーの名前を指定し、 *\<SharedDrive\>* 共有ドライブまたはフォルダーの名前を指定します。  
      > 
      >      ネットワーク経由でデータをバックアップする場合は、ネットワークの影響を受けます。 リモートの場所を使用する場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブの完了時にバックアップが成功したかどうか確認します。  
      > - データ損失の可能性を回避するには、バックアップ ディスクを、データベースのデータ ディスクおよびログ ディスクとは異なるディスクに構成します。 これは、データやログのディスクに障害が発生した場合にバックアップにアクセスするために必須です。  
      > - Azure blob アカウントへのバックアップの入力と、 **Blob service エンドポイント**で、blob サービスのプロパティに示されている URL と、コンテナー名、 [Azure portal](https://portal.azure.com)。

   4. 任意。 **部分バックアップに失敗した後、完全バックアップを強制**(@ForceFullBackupAfterPartialSetFailure): 既定値は**0**します。 ログ バックアップに失敗した場合、次の完全バックアップ間隔に達するまで、完全バックアップは実行しません。 置き換える**1**ログ バックアップの失敗が発生するたびに、完全バックアップが実行された場合。
    
   5. 任意。 **バックアップ プロセスの実行をローカル時刻に 1 時間**(@BackupHour): 既定値は**NULL**します。 バックアップ ジョブのタイム ゾーンに関連付けられていない、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューター、および実行時の午前 0 時 (utc) 時刻 (0000)。 する場合、特定の時間のタイム ゾーンでのバックアップ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターが現地時間として整数値を 0 (深夜) から 23 (11 PM) に入力します。 

   6. 任意。 **ローカル時刻を使用して、** (@UseLocalTime): ローカル時刻を使用する手順を示します。 既定値は**0**、現在の UTC 時刻 – GETUTCDATE() – 2007-05-04 01:34:11.933 を使用しています。 場合設定**1**、現地時刻 – GETDATE() – 2007-05-03 18:34:11.933 を使用して、
  
   次の例では、毎日のバックアップが午前 2 時に作成され、m:\ ドライブに格納されています。  
  
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
  
6. 選択、 **MarkAndBackupLog**手順、および選択**編集**します。 **コマンド**ボックスに、パラメーター値を更新します。  
  
   1. <strong>@MarkName</strong>: これは、バックアップ ファイルの名前付け規則の一部:\<サーバー名\>\_\<データベース名\>**\_ログ\_** \<ログ マーク名\> \_\<タイムスタンプ\>  
    
   2. <strong>@BackupPath</strong>: コンピューターに格納するフォルダー完全な宛先パス (単一引用符を含む)、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース ログ、または Azure blob ストレージ アカウントとコンテナー。 *\<宛先パス\>* ローカルまたは別のサーバーへの UNC パスにすることもできます。  
  
      MarkAndBackupLog ステップで、バックアップのログをマークした後、バックアップします。  
  
   > [!IMPORTANT]
   >  回避するために**データ損失の可能性**および**パフォーマンスの向上**、 *\<宛先パス\>* 別のコンピューターに設定する必要がありますまたは、ハード ドライブ、元のデータベース ログの格納で使用したものと異なる。  
  
    **[OK]** を選択します。  
  
7. 選択、 **Clear Backup History**手順、および選択**編集**します。 **コマンド**ボックスに、パラメーター値を更新します。  
  
   1. <strong>@DaysToKeep</strong>: 既定値は**14 日間**します。 バックアップ履歴が保持される期間決定、`Adm_BackupHistory`テーブル。 定期的にバックアップ履歴の消去維持、`Adm_BackupHistory`テーブルに適切なサイズ。 
    
   2. 任意。 <strong>@UseLocalTime</strong>: ローカル時刻を使用する手順を伝えます。 既定値は 0 です。 現在の UTC 時刻 – GETUTCDATE() – 2007-05-04 01:34:11.933 を使用します。 かどうか 1 に設定すると、次を使用してローカル時刻 – GETDATE() – 2007-05-03 18:34:11.933
  
   ```  
   exec [dbo].[sp_DeleteBackupHistory] @DaysToKeep=14, @UseLocalTime =1 
   ```  
  
   > [!NOTE]
   >  この手順**しない**デプロイ先のパスからバックアップ ファイルを削除します。  
    
    選択**OK**してすべてのプロパティ ウィンドウを閉じます。  
  
8. 任意。 バックアップのスケジュールを変更します。 参照してください[バックアップ BizTalk Server のジョブをスケジュールする方法](../core/how-to-schedule-the-backup-biztalk-server-job.md)します。  
  
   > [!NOTE]
   >  バックアップ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブが初めて構成することを実行します。 既定では、その後の実行、バックアップ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブは 1 日に 1 回完全バックアップを完了して、15 分ごとにログ バックアップを完了します。  
  
9. 右クリックし、 **Backup BizTalk Server**ジョブ、および選択**を有効にする**します。 状態に変更する必要があります**成功**します。  

## <a name="execute-backupsetupallprocssql-and-logshippingdestinationlogicsql"></a>Backup_Setup_All_Procs.sql および LogShipping_Destination_Logic.sql を実行します。

**[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 2 (FP2)** で Backup_Setup_All_Procs.sql および LogShipping_Destination_Logic.sql スクリプト`\Program Files (x86)\Microsoft BizTalk Server *your version*\Schema`します。 

BizTalk Server のバックアップ ジョブが既に構成されているし、切り替えたい場合 (ディスク) ではなく blob に Azure を使用しも、次の操作を行います。 

1. SQL Server では、実行、`Backup_Setup_All_Procs.sql`が BizTalk Server のバックアップ ジョブによってバックアップされているすべてのカスタム データベースに対してスクリプト。 既定では、FP2 自動的に更新プログラムの BizTalk データベースすべてのカスタム データベースは更新されません (これらのデータベースで、 `adm_OtherBackupDatabases` BizTalkMgmtDb 内のテーブル)。

    [バックアップをカスタム データベース](how-to-back-up-custom-databases.md)カスタム データベース詳細が示されます。 

2. **使用する場合[ログ配布](log-shipping.md)**、SQL Server 内で、送信先システムで LogShipping_Destination_Logic.sql スクリプトを実行します。 使用しない場合は、ログ配布、し、このスクリプトを実行しないでください。

    [ログ配布の送信先システムを構成する](how-to-configure-the-destination-system-for-log-shipping.md)送信先システムで詳細を提供します。

## <a name="spforcefullbackup-stored-procedure"></a>sp_ForceFullBackup ストアド プロシージャ  
  
**Sp_ForceFullBackup**ストアド プロシージャ、 **BizTalkMgmtDb**データベースは、アドホックのデータとログ ファイルの完全バックアップを実行するために使用できます。 ストアド プロシージャで、adm_ForceFullBackup テーブルの値を 1 にして更新します。 次回のバックアップ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブが実行されると、データベースの完全バックアップ セットが作成されます。  
  
## <a name="next-steps"></a>次の手順  
 [ログ配布用の送信先システムを構成します。](../core/how-to-configure-the-destination-system-for-log-shipping.md)   
 [BizTalk Server のバックアップ ジョブのスケジュールを設定する](../core/how-to-schedule-the-backup-biztalk-server-job.md)  
 [Azure ストレージ アカウント](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account)  
 [SQL Server Backup to URL](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url)
