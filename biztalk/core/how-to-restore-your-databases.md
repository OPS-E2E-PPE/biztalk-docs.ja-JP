---
title: データベースを復元する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 2016-05-10
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, log shipping
- restoring [BAM], Star Schema database, Star Schema database [BAM], restoring
- restoring, 64-bit environments
- Star Schema database [BAM], restoring
- restoring [BAM], Analysis database
- log shipping
- databases, restoring
- Archive database [BAM], restoring
- backing up, restoring
- Analysis database [BAM], restoring
- restoring [BAM], Archive database
- restoring [BAM], Star Schema database
- databases, restoring [64-bit environment]
- Primary Import database [BAM], restoring
- 64-bit environments, restoring databases
- restoring, databases
ms.assetid: 0176932a-6b3d-4502-975b-a76296189092
caps.latest.revision: 52
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6833fff893a692475e97e7722d9d65658eace0d3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255770"
---
# <a name="how-to-restore-your-databases"></a>データベースを復元する方法
データベース間のトランザクション状態の一貫性を保証するには、すべてのデータベースを同じマークに復元する必要があります。 参照してください[マークされたトランザクション、完全バックアップ、およびログ バックアップ](../core/marked-transactions-full-backups-and-log-backups.md)です。  
  
 送信先システムにあるサーバーが 1 つだけの場合は、(最新のセットを除く) すべてのログのバックアップ セットが復元されていることを確認します。 参照してください[バックアップを復元の履歴を表示する](../core/viewing-the-history-of-restored-backups.md)です。 すべてのログ バックアップ セットの復元が完了していない場合、復元ジョブが現在実行中でなければ、ジョブを実行します (必要に応じて手動で)。 復元できるは保留状態のバックアップ セットがある場合は、ジョブを処理して、復元されるまですべてします。  
  
 送信先システムに複数のサーバーがある場合は、すべてのサーバーの復元を同じバックアップ セットで行う必要があります。 各サーバーで復元の履歴を表示し、最新のログ バックアップが復元された設定がすべてのサーバーで同じであるかどうかを確認します。 同一の最新ログ バックアップ セットで復元されていないサーバーがある場合は、そのサーバーに対する復元ジョブを手動で実行する必要があります。  
  
 すべてのサーバーが同じバックアップ セットになったら、最後のセットは手動で復元できます。  
  
 adm_BackupHistory テーブルは、ソース システムのログ配布プロセスの中心的な履歴ポイントです。 実行されたバックアップ作業はすべてこのテーブルに記録されます。 送信先システムにあるすべてのサーバーは、復元作業の実行に必要な情報を受け取るためにこのテーブルから読み取ります。  
  
> [!NOTE]
>  BAM プライマリ インポート データベースをバックアップから復元する場合は、BAM プライマリよりも古いバックアップを使用して BAM アーカイブ、BAM スター スキーマ、および BAM 分析データベースも復元する必要があります。 参照してください[のバックアップと復元 BAM](../core/backing-up-and-restoring-bam.md)です。  
  
> [!NOTE]
>  送信元データベースの完全バックアップまたはログ バックアップを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブで使用した保存場所から移動する場合は、LogFileLocation または DBFileLocation の値として、送信先システムが完全/ログ バックアップ ファイルを読み取るための新しい場所を設定します。これにより、送信先システムにある bts_LogShippingDatabases テーブルで、送信元データベースに関連付けられた行が更新されます。 bts_ConfigureBtsLogShipping ストアド プロシージャを実行すると、このテーブルに値が入力されます。 これらの列は既定で Null に設定されます。この値は、adm_BackupHistory テーブルに記録されている場所から送信先システムがバックアップ ファイルを読み取ることを意味します。  
  
> [!IMPORTANT]
>  バックアップ ファイルのコピーは、常に安全な場所に保管してください。 ログ バックアップがあっても、バックアップ ファイルがなければデータベースを復元することはできません。  
  
## <a name="prerequisites"></a>前提条件  
 SQL Server ロールの sysadmin に属するアカウントを使用して、SQL Server にログインします。  
  
### <a name="to-restore-your-databases"></a>データベースを復元するには  
  
1.  送信先システムで開く**SQL Server Management Studio**に接続し、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。  
  
2.  **[SQL Server エージェント]** を展開し、**[ジョブ]** を展開します。 次の操作を行います。  
  
    1.  右クリックし、 **BTS ログの配布 - バックアップ履歴の取得**のジョブし、選択**を無効にする**です。 状態が [成功] に変わります。  
  
    2.  右クリックし、 **BTS ログの配布 - データベースの復元**のジョブし、選択**を無効にする**です。 状態が [成功] に変わります。  
  
    3.  右クリックし、 **BTS ログの配布 - マークまで復元**選択**ステップでジョブを開始**です。 選択**ステップ ID 1**選択**開始**です。  
  
         状態が変わると**成功**、SQL Server エージェント ジョブと[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースは、送信先システムに復元されます。  
  
    > [!IMPORTANT]
    >  場合、**ステータス**エラー原因を特定して、メッセージ フィールドのリンクを選択します。 これらのジョブを続行するには、状態が [成功] になっていることが必要です。  
  
3.  SampleUpdateInfo.xml ファイルを編集した [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で、コマンド プロンプトを開き、次の場所に移動します。  
  
     32 ビット コンピューター:`%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`  
  
     64 ビット コンピューター:`%SystemDrive%\Program Files (x86)\Microsoft BizTalk Server <version>\Bins32\Schema\Restore`  
  
4.  コマンド プロンプトで、次のように入力します。  
  
     `cscript UpdateDatabase.vbs SampleUpdateInfo.xml`  
  
     このスクリプトにより、他のデータベースの場所に関する情報を格納しているテーブルがすべて更新されます。  
  
    > [!IMPORTANT]
    >  -   UpdateDatabase.vbs を実行**1** BizTalk グループ内のサーバー。  
    > -   64 ビット コンピューターの場合は、UpdateDatabase.vbs を 64 ビット コマンド プロンプトから実行する必要があります。 64 ビット コンピューターにおける既定のコマンド プロンプトは、64 ビット コマンド プロンプト (%SystemDrive%\windows\System32\cmd.exe) であることに注意してください。  
    > -   BizTalk の EDI エンジンが必要としない SampleUpdateInfo.xml 独自の変更のいずれかのデータベースを復元します。  これは、EDI テーブルにアクセスする、BizTalkDTADb データベースへの接続に依存します。  
  
5.  編集した SampleUpdateInfo.xml ファイルを次のフォルダーにコピー**すべて**を実行するコンピューター[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]この BizTalk グループに。  
  
     32 ビット コンピューター: にコピー`%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`  
  
     64 ビット コンピューター: にコピー`%SystemDrive%\Program Files (x86)\Microsoft BizTalk Server <version>\Bins32\Schema\Restore`  
  
6.  **各**内のコンピューター、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ、コマンド プロンプトを開きに移動します。  
  
     32 ビット コンピューター:`%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`  
  
     64 ビット コンピューター:`%SystemDrive%Program Files (x86)Microsoft BizTalk Server <version>Bins32SchemaRestore`  
  
7.  コマンド プロンプトで、次のように入力します。  
  
     `cscript UpdateRegistry.vbs SampleUpdateInfo.xml`  
  
     このスクリプトにより、他のデータベースの場所に関する情報を格納しているすべてのレジストリ エントリが更新されます。  
  
    > [!IMPORTANT]
    >  UpdateRegistry.vbs を実行**すべて**BizTalk グループ内のサーバー。  
    >   
    >  64 ビット コンピューターの場合は、UpdateRegistry.vbs を 64 ビット コマンド プロンプトから実行する必要があります。  64 ビット コンピューターにおける既定のコマンド プロンプトは、64 ビット コマンド プロンプト (%SystemDrive%\windows\System32\cmd.exe) であることに注意してください。  
  
8.  すべての [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サービスを再起動します。 参照してください[サービスを開始、停止、一時停止、再開、または BizTalk Server を再起動するのにはどのように](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)です。  
  
9. データベースを復元した後で、Windows Management Instrumentation サービスを再起動します。  
  
    1.  開いている**services.msc**です。  
  
    2.  右クリック**Windows Management Instrumentation**、し、**再起動**です。  
  
10. 開いている**BizTalk Server 管理**です。 次の操作を行います。  
  
    1.  右クリックし、 **BizTalk グループ**選択**削除**です。  
  
    2.  右クリック**BizTalk Server 管理コンソール**選択**既存グループに接続**です。  
  
    3.  **SQL Server 名**、BizTalk 管理データベースをホストする SQL Server インスタンスの名前を選択します。 SQL Server インスタンスを選択すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によって自動的にそのコンピューター上の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースが検出されます。  
  
    4.  **データベース名**、BizTalk 管理データベースを選択 (**BizTalkMgmtDb**既定では)、し、 **OK**です。  
  
     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールによって、管理コンソールに BizTalk グループが追加されます。  
  
     これで [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が復元され、動作します。 次に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブを構成して、バックアップが新しい送信先サーバーに書き込まれるようにします。 また、新しい送信先システムの再構成も必要です。  
  
> [!IMPORTANT]
>  ルール エンジンを使用する場合は、データベースの復元後に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] グループの各サーバーでルール エンジン更新サービスを再起動する必要があります。 参照してください[サービスを開始、停止、一時停止、再開、または BizTalk Server を再起動するのにはどのように](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)です。  
  
> [!NOTE]
>  BAM を使用する場合は、この時点で BAM データベースを復元してください。 参照してください[のバックアップと復元 BAM](../core/backing-up-and-restoring-bam.md)です。  
  
## <a name="next-steps"></a>次の手順  
 [バックアップおよび BAM を復元します。](../core/backing-up-and-restoring-bam.md)  
  
## <a name="see-also"></a>参照  
 [バックアップの BizTalk Server ジョブを構成する方法](../core/how-to-configure-the-backup-biztalk-server-job.md)   
 [ログ配布用に送信先システムを構成する方法](../core/how-to-configure-the-destination-system-for-log-shipping.md)