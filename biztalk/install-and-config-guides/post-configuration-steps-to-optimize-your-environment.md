---
title: "お客様の環境を最適化するために後の構成手順 |Microsoft ドキュメント"
description: "インストールして、BizTalk Server を構成した後に完了するタスクを含む SQL エージェント ジョブの構成、EDI スキーマをインストール、ホストとホスト インスタンス、および BizTalk Server の詳細を作成します。"
ms.custom: 
ms.prod: biztalk-server
ms.date: 09/27/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0fef6ea-e7cc-4ea9-936d-5d638bc43feb
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad09a989bf3bcf85e41ce8165a9834a22520ba8b
ms.sourcegitcommit: 5355a25d120d094778fb8f68ea14cab55c68d292
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2017
---
# <a name="post-configuration-steps-to-optimize-your-environment"></a>環境を最適化するための構成後の手順
パフォーマンスを向上させ、BizTalk 環境を維持し、EDI スキーマをインストールする場合に役立つ構成後の手順です。

## <a name="disable-shared-memory-protocol-in-sql-server"></a>SQL Server の共有メモリ プロトコルを無効にする

1. **[SQL Server 構成マネージャー]** を開きます。
2. **[SQL Server ネットワークの構成]** を展開し、**[MSSQLSERVER のプロトコル]** を選択します。
3. **[共有メモリ]** を右クリックし、**[無効]** を選択します。
4. **[SQL Server サービス]** を選択し、**[SQL Server (MSSQLServer)]** を右クリックして、**[再起動]** を選択します。
5. **SQL Server 構成マネージャー**を終了します。

## <a name="configure-the-sql-agent-jobs"></a>SQL エージェント ジョブを構成する

1. **SQL Server Management Studio** を起動し、**データベース エンジン**に接続します。
2. **[SQL Server エージェント]** を展開し、**[ジョブ]** を展開します。 次のジョブを構成します。  

    ジョブ名  |説明  |必要な理由  
    ---------|---------|---------
    Backup BizTalk Server | BizTalk Server データベースとログ ファイルをバックアップします。 このジョブを構成するときに、回数やファイルの場所などのパラメーターを指定します。<br/><br/>以下のリンクで、SQL エージェント ジョブとそのパラメーターについて説明しています。<br/><br/>[BizTalk Server データベースのバックアップと復元](../core/backing-up-and-restoring-biztalk-server-databases.md)<br/>[BizTalk Server のバックアップ ジョブを構成する方法](../core/how-to-configure-the-backup-biztalk-server-job.md)|この SQL エージェント ジョブでは、トランザクション ログの切り捨ても行います。これによりパフォーマンスが向上します。<br/><br/>このジョブでは、バックアップ ファイルは削除されません。古いファイルも削除されません。 バックアップ ファイルを削除する方法については、「Microsoft BizTalk Server データベース サーバーでバックアップ ファイルが長期的に蓄積すると、"Backup BizTalk Server" ジョブが失敗する」を参照してください。
    DTA Purge and Archive |BizTalk Server 追跡データベース (BizTalkDTADb) の切り捨てとアーカイブを行います。 このジョブを構成するときに、完了したインスタンスを保持する日数や全データを保持する日数などのパラメーターを指定します。<br/><br/>以下のリンクで、SQL エージェント ジョブとそのパラメーターについて説明しています。 <br/><br/>[BizTalk 追跡データベースのアーカイブおよび削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)<br/>[DTA Purge and Archive ジョブを構成する方法](../core/how-to-configure-the-dta-purge-and-archive-job.md)|この SQL エージェント ジョブは、追跡ホストを維持し、追跡イベントを削除することで、パフォーマンスに直接影響を及ぼします。

## <a name="maintain-your-backup-files"></a>バックアップ ファイルを維持する

BizTalk Server の場合、バックアップ ファイルを削除するジョブは含まれません。 したがって、バックアップ ファイルを維持する方法は自由です。 多くのユーザーは sp_DeleteBackupHistoryAndFiles ストアド プロシージャを作成し、BizTalk Server のバックアップ ジョブで直接このストアド プロシージャを呼び出します。 一部のユーザーはメンテナンス プランを作成します。 お好きな方法を選択してください。 このトピックでは両方のオプションを示します。

#### <a name="option-1-create-the-spdeletebackuphistoryandfiles-stored-procedure"></a>オプション 1: sp_DeleteBackupHistoryAndFiles ストアド プロシージャの作成

1. SQL Server Management Studio で、BizTalk 管理データベース (BizTalkMgmtDb) を選択します。 
2. **[新しいクエリ]** を選択し、次の T-SQL スクリプトを実行して sp_DeleteBackupHistoryAndFiles ストアド プロシージャを作成します。 

    ```
    CREATE PROCEDURE [dbo].[sp_DeleteBackupHistoryAndFiles] @DaysToKeep smallint = null
    AS

    BEGIN
    set nocount on
    IF @DaysToKeep IS NULL OR @DaysToKeep \<= 1
    RETURN
    /*
    Only delete full sets
    If a set spans a day in such a way that some items fall into the deleted group and the other does not, do not delete the set
    */

    DECLARE DeleteBackupFiles CURSOR
    FOR SELECT 'del "' + [BackupFileLocation] + '\' + [BackupFileName] + '"' FROM [adm_BackupHistory]
    WHERE  datediff( dd, [BackupDateTime], getdate() ) >= @DaysToKeep
    AND [BackupSetId] NOT IN ( SELECT [BackupSetId] FROM [dbo].[adm_BackupHistory] [h2] WHERE [h2].[BackupSetId] = [BackupSetId] AND datediff( dd, [h2].[BackupDateTime], getdate() ) < @DaysToKeep )
 
    DECLARE @cmd varchar(400)
    OPEN DeleteBackupFiles
    FETCH NEXT FROM DeleteBackupFiles INTO @cmd
    WHILE (@@fetch_status <> -1)
    BEGIN
        IF (@@fetch_status <> -2)
        BEGIN
            EXEC master.dbo.xp_cmdshell @cmd, NO_OUTPUT
            delete from [adm_BackupHistory] WHERE CURRENT OF DeleteBackupFiles
            print @cmd
        END
        FETCH NEXT FROM DeleteBackupFiles INTO @cmd
    END

    CLOSE DeleteBackupFiles
    DEALLOCATE DeleteBackupFiles
    END
    GO
    ```

3. BizTalk Server のバックアップ ジョブを開き、**[ステップ]** を選択します。
4. **[バックアップ履歴のクリア]** ステップを編集し、以前の *sp_DeleteBackupHistory* ストアド プロシージャではなく、新しい *sp_DeleteBackupHistoryAndFiles* を呼び出すようにします。
5. **[OK]** を選択して変更を保存します。

#### <a name="option-2-create-a-maintenance-plan"></a>オプション 2: メンテナンス プランの作成

1. SQL Server Management Studio で、**[管理]** を展開し、**[メンテナンス プラン]** を右クリックして **[メンテナンス プラン ウィザード]** を選択します。
2. プランに名前 (*バックアップ ファイルの削除*など) を付け、**[スケジュール]** の横の **[変更]** ボタンを選択します。
3. バックアップ ファイルを削除する頻度を選択します。 これらの設定は完全にユーザーの自由です。 **[OK]**、**[次へ]** の順に選択します。
4. **[メンテナンス クリーンアップ タスク]**、**[次へ]** の順に選択します。
5. **[クリーンアップ タスク]** ウィンドウで、**[フォルダーを検索し、拡張子に基づいてファイルを削除する]** に移動し、バックアップ フォルダー (f:\BizTalkBackUps など) を選択して、ファイル拡張子として **.bak** を入力します。 経過期間に基づいてファイルを削除することもできます。 たとえば、3 週間が経過したファイルを削除する場合は、3 と入力します。 **[次へ]** を選択します。
6. ウィザードでの操作が完了したら、必要な追加情報を入力します。 **[完了]** を選択します。

  
## <a name="install-edi-schemas-and-more-edi-as2-configuration"></a>EDI スキーマのインストールおよび EDI AS2 の追加構成
 EANCOM、EDIFACT、HIPAA、および X12 のスキーマ ファイルは、MicrosoftEdiXSDTemplates.exe という名前の自己展開型の実行可能ファイルに含まれています。 EDI ソリューションを作成するには、これらのファイルを抽出し、プロジェクトと共に配置します。 これらのファイルをインストールして抽出するには、次のようにします。  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] インストールを実行し、**開発ツールおよび SDK** コンポーネントをインストールします。 このコンポーネントは、MicrosoftEdiXSDTemplates.exe EDI スキーマ ファイルを \XSD_Schema\EDI フォルダーにダウンロードします。  
  
    > [!NOTE]
    > [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] をアップグレードすると、環境内の MicrosoftEdiXSDTemplates.exe ファイルが、アップグレードに関連付けられた新しい MicrosoftEdiXSDTemplates.exe ファイルに置き換えられます。 前のスキーマが必要な場合は、前の MicrosoftEdiXSDTemplates.exe ファイルをバックアップします。  
  
    > [!NOTE] 
    > [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] を新しいビルドにアップグレードするときにメッセージ スキーマをアップグレードすると、更新されたスキーマを使用するときに問題が発生したり、追加の更新手順が必要になったりする場合があります。 「[アプリケーションの更新に関する重要な考慮事項](../core/important-considerations-for-updating-applications.md)」の「スキーマを更新する際の考慮事項」セクションを参照してください。
  
2.  [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\XSD_Schema\EDI に移動し、MicrosoftEdiXSDTemplates.exe をダブルクリックします。  
  
3.  スキーマを [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\XSD_Schema\EDI に抽出します。 スキーマを抽出すると、EANCOM、EDIFACT、HIPAA、および X12 のフォルダーに格納されます。  
  
#### <a name="add-a-reference-to-the-biztalk-server-edi-application"></a>BizTalk Server EDI アプリケーションへの参照を追加する  
 EDI スキーマ、パイプライン、およびオーケストレーションは **BizTalk EDI アプリケーション**に展開されます。 他のアプリケーションを EDI アプリケーションとして使用するには、**BizTalk EDI アプリケーション**への参照を追加します。 手順:  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、**[アプリケーション]** を展開します。 EDI で使用するアプリケーション (*BizTalk アプリケーション 1* など) を右クリックして、**[追加]**、**[参照]** の順に選択します。  
  
2.  **[BizTalk EDI アプリケーション]** を選択し、**[OK]** を選択して変更を保存します。  
  
> [!TIP]
>  他のアプリケーションへの参照を表示するには、任意のアプリケーションを右クリックし **[プロパティ]** を選択します。 **[参照]** を選択します。 新しい参照を追加して、既存の参照を削除することもできます。  
  
> [!NOTE]
>  BizTalk EDI アプリケーションにカスタム アイテムを追加しないでください。 このアプリケーションはそのままにしておくことをお勧めします。  
  
#### <a name="start-batch-orchestrations"></a>バッチ オーケストレーションを開始する  
 パーティが EDI バッチを送受信できるようにするには、バッチ処理オーケストレーションを開始します。 これらのオーケストレーションは、インストール ウィザードや構成ウィザードでは開始されません。 手順:  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、**[BizTalk EDI アプリケーション]** を展開し、**[オーケストレーション]** を選択します。  
  
2.  次のオーケストレーションをそれぞれ右クリックし、**[開始]** を選択します。  
  
    -   Microsoft.BizTalk.Edi.BatchSuspendOrchestration.BatchElementSuspendService (アセンブリ: Microsoft.BizTalk.Edi.BatchingOrchestration.dll)  
  
    -   Microsoft.BizTalk.Edi.BatchingOrchestration.BatchingService (アセンブリ: Microsoft.BizTalk.Edi.BatchingOrchestration.dll)  
  
    -   Microsoft.BizTalk.Edi.RoutingOrchestration.BatchRoutingService (アセンブリ: Microsoft.BizTalk.Edi.RoutingOrchestration.dll)  
  
> [!NOTE]
>  EDI バッチ処理オーケストレーションは、EDI バッチを送受信する場合にのみ開始する必要があります。 システムが EDI バッチの送受信を行わないときに開始すると、システム パフォーマンスに影響することがあります。  
  
#### <a name="migrate-edi-artifacts-from-a-previous-biztalk-version"></a>以前の BizTalk バージョンからの EDI アイテムを移行します。  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2010 以降のバージョンでの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] での取引先の管理方法が更新されました。 以前の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] バージョンでは、パーティは取引先でのみ作成され、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をホストするパートナーでは作成されませんでした。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2010 以降では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をホストするパートナーを含むすべての取引先に関してパーティーを作成する必要があります。 以前の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] バージョンでは、エンコード (X12 および EDIFACT) とトランスポート (AS2) プロトコルのプロパティはパーティ レベルで定義されています。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2010 以降のバージョンでは、これらのプロパティはアグリーメントを通じて定義されます。  
  
 以前のバージョンからパーティー データを移行するため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には [パーティー移行ツール] があります。 移行パスには以下のものがあります。  
  
|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] バージョン|移行パス|  
|---------------------------------------------------------------------------------------|--------------------|  
|**[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]**|BizTalk Server 2009 にアップグレードします。 次に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013/2013 R2 のパーティ移行ツールを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013/2013 R2 に移行します。<br /><br /> **あるいは**、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013/2013 R2 のパーティ移行ツールを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2010 に移行します。 次に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013/2013 R2 にアップグレードします。|  
|**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2009**|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013/2013 R2 のパーティー移行ツールを使用して、直接 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013/2013 R2 に移行する。|  
|**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2010**|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013/2013 R2 にアップグレードする。|  
  
 パーティ移行ツールは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] メディアの \PartyMigrationTool フォルダーの中から入手できます。  

  
## <a name="install-biztalk-health-monitor-bhm"></a>BizTalk Health Monitor (BHM) をインストールする

BizTalk Health Monitor では、メッセージ ボックス ビューアー レポートの作成と表示、カスタム クエリの作成、ターミネータ タスクの実行、複数の BizTalk 環境の監視などを行うダッシュボードが提供されます。 BizTalk 環境の担当者は、このツールをインストールし、BizTalk 環境の正常性を確認する場合や、維持する場合にも使用することをお勧めします。

主要リンク:

[BHM のダウンロード](https://www.microsoft.com/download/details.aspx?id=43716)  
[BHM のインストール](http://social.technet.microsoft.com/wiki/contents/articles/26466.biztalk-server-how-to-install-the-new-biztalk-health-monitor-snap-in.aspx)  
[BHM の公式ブログ](https://blogs.msdn.microsoft.com/biztalkhealthmonitor/)

## <a name="create-your-hosts-and-host-instances"></a>ホストとホスト インスタンスを作成する
いくつかのキー タスクを個別のホストに分割することをお勧めします。 たとえば、常に追跡専用の個別のホストを作成します。 メッセージの受信専用に別のホスト/ホスト インスタンス、メッセージの送信用に別のホスト/ホスト インスタンス、オーケストレーション用に別のホスト/ホスト インスタンスを作成します。 

このような場合、多くの推奨事項があります。 作業を開始する場合の推奨事項は以下のとおりです。 

[BizTalk ホストとホスト インスタンスの管理](../core/managing-biztalk-hosts-and-host-instances.md)  
[BizTalk ホストの高可用性](../core/providing-high-availability-for-biztalk-hosts.md)  
[ベスト プラクティス: BizTalk Server ホストとホスト インスタンスの作成および構成](http://social.technet.microsoft.com/wiki/contents/articles/19701.biztalk-server-best-practices-create-and-configure-biztalk-server-host-and-host-instances.aspx)  
[同じコンピューターの複数のホストでのオーケストレーションの実行](http://social.technet.microsoft.com/wiki/contents/articles/31183.biztalk-server-running-orchestrations-in-multiple-hosts-on-the-same-computer.aspx)  
[PowerShell を作成し、BizTalk Server ホスト、ホスト インスタンスおよびハンドラーを構成するには](https://gallery.technet.microsoft.com/PowerShell-to-Configure-43d77916)  
[TechNet Wiki の BizTalk Server リソース](http://social.technet.microsoft.com/wiki/contents/articles/2240.biztalk-server-resources-on-the-technet-wiki.aspx)
