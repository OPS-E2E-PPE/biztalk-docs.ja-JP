---
title: 構成後の手順、環境を最適化する |Microsoft Docs
description: インストールして、BizTalk Server を構成した後に完了するタスクを含む SQL エージェント ジョブの構成、EDI スキーマをインストール、ホストとホスト インスタンス、および BizTalk Server では、複数の作成
ms.custom: ''
ms.prod: biztalk-server
ms.date: 09/27/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0fef6ea-e7cc-4ea9-936d-5d638bc43feb
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3562487e70557ec57a686d8b0109f61eccaa8dce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394015"
---
# <a name="post-configuration-steps-to-optimize-your-environment"></a>構成後の手順、環境を最適化するには
パフォーマンスを向上させるための構成後の手順では、BizTalk 環境を維持し、EDI スキーマをインストールします。

## <a name="disable-shared-memory-protocol-in-sql-server"></a>SQL Server 共有メモリ プロトコルを無効にします。

1. **[SQL Server 構成マネージャー]** を開きます。
2. 展開**SQL Server ネットワーク構成**、選び**MSSQLSERVER のプロトコル**します。
3. 右クリック**共有メモリ**、選び**を無効にする**します。
4. 選択**SQL Server サービス**を右クリックして**SQL Server (MSSQLServer)** を選択し、**再起動**します。
5. **SQL Server 構成マネージャー**を終了します。

## <a name="configure-the-sql-agent-jobs"></a>SQL エージェント ジョブを構成します。

1. **SQL Server Management Studio**への接続と**データベース エンジン**します。
2. 展開**SQL Server エージェント**、展開と**ジョブ**します。 次のジョブを構成します。  

    ジョブ名  |説明  |必要である理由  
    ---------|---------|---------
    BizTalk Server をバックアップします。 | BizTalk Server データベースとログ ファイルをバックアップします。 ジョブを構成するときは、頻度とファイルの場所などのパラメーターを指定します。<br/><br/>次のリンクでは、SQL エージェント ジョブとそのパラメーターについて説明します。<br/><br/>[バックアップおよび BizTalk Server データベースを復元します。](../core/backing-up-and-restoring-biztalk-server-databases.md)<br/>[BizTalk Server のバックアップ ジョブを構成する方法](../core/how-to-configure-the-backup-biztalk-server-job.md)|この SQL エージェント ジョブには、パフォーマンスを向上させることができます、トランザクション ログも切り捨てます。<br/><br/>このジョブの削除または古いなど、バックアップ ファイルの削除はされません。 バックアップ ファイルを削除するには、"Backup BizTalk Server"バックアップ ファイルは、Microsoft BizTalk Server データベース サーバーでの時間の経過と共に蓄積ジョブが失敗を参照してください。
    DTA Purge and Archive |切り捨てし、BizTalk Server 追跡 (BizTalkDTADb) データベースをアーカイブします。 完了したインスタンスを保持する日数などのパラメーターを決定するジョブを構成するときに、すべてのデータを保持する日数。<br/><br/>次のリンクでは、SQL エージェント ジョブとそのパラメーターについて説明します。 <br/><br/>[BizTalk 追跡データベースのアーカイブおよび削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)<br/>[構成の DTA Purge and Archive ジョブをする方法](../core/how-to-configure-the-dta-purge-and-archive-job.md)|この SQL エージェント ジョブは、追跡ホストの管理と追跡イベントを削除して、パフォーマンスを直接影響します。

## <a name="maintain-your-backup-files"></a>バックアップ ファイルを維持します。

BizTalk Server では、バックアップ ファイルを削除するジョブは含まれません。 その結果、バックアップ ファイルを維持する方法は自由です。 多くのユーザーは sp_DeleteBackupHistoryAndFiles ストアド プロシージャを作成し、BizTalk Server のバックアップ ジョブで直接このストアド プロシージャを呼び出します。 一部のユーザーは、メンテナンス プランを作成します。 あなたです。 このトピックでは、両方のオプションを使用します。

#### <a name="option-1-create-the-spdeletebackuphistoryandfiles-stored-procedure"></a>オプション 1:Sp_DeleteBackupHistoryAndFiles ストアド プロシージャを作成します。

1. SQL Server Management studio では、BizTalk 管理データベース (BizTalkMgmtDb) を選択します。 
2. 選択**新しいクエリ**、次の T-SQL スクリプトを実行すると、sp_DeleteBackupHistoryAndFiles ストアド プロシージャと。 

    ```
    CREATE PROCEDURE [dbo].[sp_DeleteBackupHistoryAndFiles] @DaysToKeep smallint = null
    AS

    BEGIN
    set nocount on
    IF @DaysToKeep IS NULL OR @DaysToKeep <= 1
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

3. BizTalk Server のバックアップ ジョブを開き、選択**手順**します。
4. 編集、 **Clear Backup History**ステップを呼び出す新しいよう*sp_DeleteBackupHistoryAndFiles*ストアド プロシージャではなく、以前*sp_DeleteBackupHistory*ストアド プロシージャです。
5. **[OK]** を選択して変更を保存します。

#### <a name="option-2-create-a-maintenance-plan"></a>オプション 2:メンテナンス プランを作成します。

1. SQL Server Management studio で展開**管理**を右クリックして**メンテナンス プラン**、選択と**メンテナンス プラン ウィザード**します。
2. プランの名前 (たとえば、名前を付けます*バックアップ ファイルの削除*)、し、、**変更**横に**スケジュール**。
3. バックアップ ファイルを削除する頻度を選択します。 これらの設定は、ユーザーが決定できますは完全にします。 **[OK]** を選択し、 **[次へ]** を選択します。
4. 選択**メンテナンス クリーンアップ タスク**を選択し、**次**します。
5. **クリーンアップ タスク**ウィンドウに移動して**フォルダーを検索し、ファイルを削除しています.**、バックアップ フォルダー (f:\BizTalkBackUps など) を選択し、入力、 **.bak**ファイル拡張子に対応します。 経過期間に基づいてファイルを削除することもできます。 たとえば、3 週間以上経過したファイルを削除する場合は、3 を入力します。 **[次へ]** を選択します。
6. ウィザードを完了し、必要な追加情報を入力します。 **[完了]** を選択します。


## <a name="install-edi-schemas-and-more-edi-as2-configuration"></a>EDI スキーマおよび EDI AS2 の追加構成をインストールします。
 EANCOM、EDIFACT、HIPAA、および X12 スキーマ ファイルは MicrosoftEdiXSDTemplates.exe という名前の自己解凍実行可能ファイルに含まれています。 EDI ソリューションを作成するには、これらのファイルを抽出し、プロジェクトと共に配置します。 インストールし、これらのファイルを抽出します。  

1. 実行、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]のインストールと、インストール、**開発ツールおよび SDK**コンポーネント。 このコンポーネントは、MicrosoftEdiXSDTemplates.exe EDI スキーマ ファイルを \XSD_Schema\EDI フォルダーにダウンロードします。  

   > [!NOTE]
   > アップグレードする場合は[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]のインストール内の MicrosoftEdiXSDTemplates.exe ファイルがアップグレードに関連付けられた新しい MicrosoftEdiXSDTemplates.exe ファイルに置き換えられます。 必要がある場合、前のスキーマでは、前の MicrosoftEdiXSDTemplates.exe ファイルをバックアップします。  
   > 
   > [!NOTE]
   > アップグレードするときに、メッセージ スキーマをアップグレードする場合[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]それ以降のビルドに更新されたスキーマを使用して問題が発生する可能性がありますまたは追加の更新手順を実行する必要があります。 「に関する考慮事項のスキーマの更新」セクションを参照してください[アプリケーションの更新に関する重要な考慮事項](../core/important-considerations-for-updating-applications.md)

2. 移動して[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\XSD_Schema\EDI、MicrosoftEdiXSDTemplates.exe をダブルクリックします。  

3. スキーマを抽出[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\XSD_Schema\EDI です。 スキーマを抽出するときは EANCOM、EDIFACT、HIPAA、および X12 に格納されているフォルダー。  

#### <a name="add-a-reference-to-the-biztalk-server-edi-application"></a>BizTalk Server EDI アプリケーションへの参照を追加します。  
 EDI スキーマ、パイプライン、およびオーケストレーションの展開、 **BizTalk EDI アプリケーション**します。 その他のアプリケーションを EDI アプリケーションとしてを使用するへの参照を追加、 **BizTalk EDI アプリケーション**します。 手順:  

1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開**アプリケーション**します。 EDI を使用するアプリケーションを右クリックして (など*BizTalk アプリケーション 1*) を選択します**追加**、し、**参照**します。  

2. 選択**BizTalk EDI アプリケーション**を選択し、 **OK**変更を保存します。  

> [!TIP]
>  その他のアプリケーションへの参照を表示するには、任意のアプリケーションを右クリックして**プロパティ**します。 選択**参照**します。 新しい参照の追加もおよび既存の参照を削除できます。  

> [!NOTE]
>  BizTalk EDI アプリケーションするカスタム アーティファクトを追加しないでください。 このアプリケーションとしてのままにすることをお勧め-です。  

#### <a name="start-batch-orchestrations"></a>バッチ オーケストレーションを開始します。  
 EDI バッチを送受信するパーティを有効にした場合は、バッチ処理オーケストレーションを開始します。 構成ウィザードまたはインストール ウィザードでは、これらのオーケストレーションは開始されません。 手順:  

1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開**BizTalk EDI アプリケーション**、選び**オーケストレーション**します。  

2. 次のオーケストレーションのそれぞれを右クリックして**開始**:  

   -   Microsoft.BizTalk.Edi.BatchSuspendOrchestration.BatchElementSuspendService (アセンブリ。Microsoft.BizTalk.Edi.BatchingOrchestration.dll)  

   -   Microsoft.BizTalk.Edi.BatchingOrchestration.BatchingService (アセンブリ。Microsoft.BizTalk.Edi.BatchingOrchestration.dll)  

   -   Microsoft.BizTalk.Edi.RoutingOrchestration.BatchRoutingService (アセンブリ。Microsoft.BizTalk.Edi.RoutingOrchestration.dll)  

> [!NOTE]
>  EDI バッチ処理オーケストレーションは、EDI バッチを送受信する場合にのみ開始する必要があります。 システムの受信または EDI バッチを送信されていないときに開始すると、システムのパフォーマンスが影響する可能性があります。  

#### <a name="migrate-edi-artifacts-from-a-previous-biztalk-version"></a>以前の BizTalk バージョンからの EDI アイテムを移行します。  
 取引がで管理されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で更新された[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]2010 以降のバージョン。 前の[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]バージョンでは、取引先、およびホストするパートナーではなくのみパーティが作成された[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]すべての取引先に関して、ホストするパートナーを含む、パーティーを作成する必要があります 2010 以降、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 以前[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]バージョンでは、エンコード (X12 および EDIFACT)、トランスポート (AS2) プロトコルのプロパティはパーティ レベルで定義されます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2010 以降のバージョンでは、これらのプロパティはアグリーメントを通じて定義されます。  

 以前のバージョンからパーティ データを移行する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]はパーティ移行ツールが含まれています。 次の移行パスを検討してください。  


| [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] バージョン  |                                                                                                                                                                                                                                                                                                                                     移行パス                                                                                                                                                                                                                                                                                                                                      |
|---------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      **[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]**       | BizTalk Server 2009 にアップグレードします。 含まれているパーティ移行ツールを使用して、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013/2013 R2 に移行する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]2013/2013 R2。<br /><br /> **または**に付属するパーティ移行ツールを使用して、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013/2013 R2 に移行する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]2010。 アップグレードし、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013/2013 R2。 |
| **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2009** |                                                                                                                                                                                                           含まれているパーティ移行ツールを使用して、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013/2013 R2 に直接移行する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]2013/2013 R2。                                                                                                                                                                                                            |
| **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2010** |                                                                                                                                                                                                                                                                                       アップグレード[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]2013/2013 R2。                                                                                                                                                                                                                                                                                       |

 パーティ移行ツールで使用できる、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メディアの \PartyMigrationTool フォルダー。  


## <a name="install-biztalk-health-monitor-bhm"></a>BizTalk Health Monitor (BHM) のインストールします。

BizTalk Health Monitor では、ダッシュ ボードを作成し、メッセージ ボックス ビューアー レポートの表示、カスタム クエリを作成、ターミネータ タスクの実行、複数の BizTalk 環境の監視を提供します。 BizTalk 環境を担当する場合は、インストールしてこのツールを使用して、BizTalk 環境の正常性を確認して維持もお勧めします。

主要リンク:

[BHM をダウンロードします。](https://www.microsoft.com/download/details.aspx?id=43716)  
[BHM をインストールします。](http://social.technet.microsoft.com/wiki/contents/articles/26466.biztalk-server-how-to-install-the-new-biztalk-health-monitor-snap-in.aspx)  
[BHM の公式ブログ](https://blogs.msdn.microsoft.com/biztalkhealthmonitor/)

## <a name="create-your-hosts-and-host-instances"></a>ホストとホスト インスタンスを作成します。
いくつか重要なタスクを別々 のホストに分離することをお勧めします。 たとえば、常に追跡専用は個別のホストを作成します。 メッセージの受信に注目したインスタンス、メッセージを送信する別のホスト/ホスト インスタンスおよびオーケストレーションの別のホスト/ホスト インスタンスは、別のホスト/ホストを作成します。 

この領域で多くの推奨事項があります。 開始するため、いくつか次に示します。 

[BizTalk ホストとホスト インスタンスの管理](../core/managing-biztalk-hosts-and-host-instances.md)  
[BizTalk ホストの高可用性を実現します。](../core/providing-high-availability-for-biztalk-hosts.md)  
[ベスト プラクティス:作成し、BizTalk Server を構成するホストとホスト](http://social.technet.microsoft.com/wiki/contents/articles/19701.biztalk-server-best-practices-create-and-configure-biztalk-server-host-and-host-instances.aspx)  
[同じコンピューターに複数のホストでオーケストレーションの実行](http://social.technet.microsoft.com/wiki/contents/articles/31183.biztalk-server-running-orchestrations-in-multiple-hosts-on-the-same-computer.aspx)  
[PowerShell を作成し、BizTalk Server ホスト、ホスト インスタンスおよびハンドラーの構成](https://gallery.technet.microsoft.com/PowerShell-to-Configure-43d77916)  
[TechNet Wiki の BizTalk Server リソース](http://social.technet.microsoft.com/wiki/contents/articles/2240.biztalk-server-resources-on-the-technet-wiki.aspx)
