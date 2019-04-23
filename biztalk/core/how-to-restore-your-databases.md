---
title: データベースの復元 |Microsoft Docs
description: SQL エージェント ジョブ, を使用して、UpdateDatabase.vbs と UpdateRegistry.vbs スクリプトの実行など、BizTalk Server データベースを復元する手順を参照してください。 また、BizTalk 管理コンソールで、SQL Server インスタンス名の更新を含む、データベースの復元後の対処方法を参照してください。
ms.custom: ''
ms.date: 04/22/19
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0176932a-6b3d-4502-975b-a76296189092
caps.latest.revision: 52
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3213b22cb82d807b392e43d09b64a24cbc519cf
ms.sourcegitcommit: 5c3994bc9ccd688f3df74e2a49f84ada4baf5dfd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "60164512"
---
# <a name="restore-your-databases---biztalk-server"></a>BizTalk Server のデータベースを復元します。
データベース間のトランザクション状態の一貫性を保証するには、すべてのデータベースを同じマークに復元する必要があります。 参照してください[マークされたトランザクション、完全バックアップ、バックアップとログ バックアップ](../core/marked-transactions-full-backups-and-log-backups.md)します。  
  
 送信先システムに 1 つのサーバーがある場合は、すべての (最新のセット) を除くログのバックアップ セットが復元されたことを確認します。 参照してください[バックアップを復元の履歴を表示する](../core/viewing-the-history-of-restored-backups.md)します。 すべてのログ バックアップ セットが復元されていないか、復元ジョブが実行されていない場合は、(手動で必要な場合)、復元ジョブを実行します。 復元できる未処理のバックアップ セットがある場合は、ジョブにまで処理すべて復元します。  
  
 送信先システムに複数のサーバーがある場合、同じバックアップ セットへのすべてのサーバーを復元する必要があります。 各サーバーで復元の履歴を表示し、設定が復元された最新のログ バックアップが、すべてのサーバーで同じであるかどうかを確認します。 そうでない場合は、復元された最新のログ バックアップ セットが必要な各サーバーで復元ジョブを手動で実行する必要があります。  
  
 同じバックアップ セット上のすべてのサーバーに配置されて、最終的なセットを手動で復元できます。  
  
 Adm_BackupHistory テーブルは、ソース システムのログ配布プロセスの中心的な履歴ポイントです。 すべてのバックアップ実行される作業は、このテーブルに記録されます。 送信先システムにあるすべてのサーバーは、復元作業を実行するための情報を受信するには、このテーブルから読み取ります。  

## <a name="before-you-begin"></a>アンインストールの準備

- BAM プライマリ インポート データベースをバックアップから復元する場合は、BAM プライマリよりも古いバックアップを使用して BAM アーカイブ、BAM スター スキーマ、および BAM 分析データベースも復元する必要があります。 参照してください[のバックアップと復元 BAM](../core/backing-up-and-restoring-bam.md)します。  
- 完全な移動、BizTalk Server のバックアップ ジョブがそれらに配置する場所からのソース データベースのバックアップ ログに記録するかを設定して送信先システムで bts_LogShippingDatabases テーブルでは、そのデータベースに関連付けられている行を更新する必要があります、LogFileLocation または dbfilelocation の値として、送信先システムが完全/ログ バックアップ ファイルを読み取る新しい場所にします。 Bts_ConfigureBtsLogShipping ストアド プロシージャを実行すると、このテーブルが設定されます。 既定では、これらの列は、送信先システムが、adm_BackupHistory テーブルに格納されている場所から、バックアップ ファイルを読み取ることを示します null に設定されます。  
- 常に安全な場所にバックアップ ファイルのコピーを保持します。 ログ バックアップがある場合でもバックアップ ファイルがない場合、データベースを復元することはできません。  
  
## <a name="prerequisites"></a>前提条件  
SQL Server の sysadmin SQL Server ロールのメンバーであるアカウントを使用してにサインインします。  
  
## <a name="restore-your-databases"></a>データベースを復元します。  
  
1. 送信先システムで開く**SQL Server Management Studio**、し、SQL Server に接続します。  
  
2. 展開**SQL Server エージェント**、展開と**ジョブ**します。 次の操作を行います。  
  
   1. 右クリックし、 **BTS ログの配布 - バックアップ履歴の取得**ジョブし、選択**を無効にする**します。 成功状態を変更します。  
  
   2. 右クリックし、 **BTS ログの配布 - データベースの復元**ジョブし、選択**を無効にする**します。 成功状態を変更します。  
  
   3. 右クリックし、 **BTS ログの配布 - マークまで復元**選択**ステップでジョブを開始**します。 選択**ステップ ID 1**選択**開始**します。  
  
       状態が変わると**成功**、BizTalk Server データベースと SQL Server エージェント ジョブが送信先システムに復元されます。  
  
   > [!IMPORTANT]
   >  場合、**状態**エラー原因を特定する [メッセージ] フィールドに、リンクを選択します。 これらのジョブは、続行する前に、成功の状態が必要です。  
  
3. SampleUpdateInfo.xml ファイルを編集する BizTalk Server でコマンド プロンプトを開きに移動します。  
  
    32 ビット コンピューター: `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`  
  
    64 ビット コンピューター: `%SystemDrive%\Program Files (x86)\Microsoft BizTalk Server <version>\Bins32\Schema\Restore`  
  
4. コマンド プロンプトで、次のように入力します。
  
    `cscript UpdateDatabase.vbs SampleUpdateInfo.xml`

    > [!NOTE]
    > SQL Server 2016 環境を使用する場合は、UpdateDatabase.vbs で MSOLEDBSQL を使用する必要があります。 UpdateDatabase.vbs に移動`conn.Provider = "SQLOLEDB"`します。 変更`SQLOLEDB`に`MSOLEDBSQL`します。 それ以外の場合、スクリプトがエラーで失敗可能性があります:`SQL Server: Invalid connection string attribute`します。
    > 
    > [ダウンロード MSOLEDBSQL](https://www.microsoft.com/download/details.aspx?id=56730)します。
    > 
    > このスクリプトでは、他のデータベースの場所に関する情報を格納するすべてのテーブルを更新します。
  
    > [!IMPORTANT]
    >  - UpdateDatabase.vbs を実行**1 つ**BizTalk グループ内のサーバー。  
    >  - を 64 ビット コンピューターで UpdateDatabase.vbs を 64 ビット コマンド プロンプトから実行する必要があります。 64 ビット コンピューターで既定のコマンド プロンプトは 64 ビット コマンド プロンプトでは、%systemdrive%\windows\system32\cmd.exe にあることに注意してください。  
    >  - データベースを復元するときに SampleUpdateInfo.xml 独自の変更のいずれかの BizTalk の EDI エンジンは必要ありません。  これは、EDI テーブルにアクセスする、BizTalkDTADb データベースへの接続に依存します。  
  
5. 編集した SampleUpdateInfo.xml ファイルを次のフォルダーにコピー**すべて**この BizTalk グループに BizTalk Server を実行しているコンピューター。  
  
    32 ビット コンピューター:コピーするには `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`  
  
    64 ビット コンピューター:コピーするには `%SystemDrive%\Program Files (x86)\Microsoft BizTalk Server <version>\Bins32\Schema\Restore`  
  
6. **各**BizTalk Server グループ内のコンピューターが、コマンド プロンプトを開きに移動します。  
  
    32 ビット コンピューター: `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`  
  
    64 ビット コンピューター: `%SystemDrive%\Program Files (x86)Microsoft BizTalk Server <version>\Bins32\Schema\Restore`  
  
7. コマンド プロンプトで、次のように入力します。  
  
    `cscript UpdateRegistry.vbs SampleUpdateInfo.xml`  
  
    このスクリプトでは、他のデータベースの場所に関する情報を格納するすべてのレジストリ エントリを更新します。  
  
   > [!IMPORTANT]
   >  - UpdateRegistry.vbs を実行**すべて**BizTalk グループ内のサーバー。  
   >  - 64 ビット コンピューターでは、64 ビット コマンド プロンプトから UpdateRegistry.vbs を実行する必要があります。  64 ビット コンピューターで既定のコマンド プロンプトは 64 ビット コマンド プロンプトには、%systemdrive%\windows\system32\cmd.exe にあることに注意してください。  
  
8. すべての BizTalk Server サービスを再起動します。 参照してください[Services を開始、停止、一時停止、再開、または BizTalk Server を再起動する方法](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)します。  
  
9. データベースを復元した後、Windows Management Instrumentation サービスを再起動します。  
  
    1.  開いている**services.msc**します。  
  
    2.  右クリックして**Windows Management Instrumentation**、し、**再起動**します。  
  
10. 開いている**BizTalk Server 管理**します。 次の操作を行います。  
  
    1. 右クリックし、 **BizTalk グループ**選択**削除**します。  
  
    2. 右クリック**BizTalk Server 管理**選択**既存グループへの接続**します。  
  
    3. **SQL Server 名**、BizTalk 管理データベースをホストする SQL Server インスタンスの名前を選択します。 SQL Server インスタンスを選択すると、BizTalk Server コンピューターに BizTalk Server データベースが自動的に検出します。  
  
    4. **データベース名**、BizTalk 管理データベースを選択します (**BizTalkMgmtDb**既定で)、し、 **OK**。  
  
       BizTalk Server 管理コンソールでは、管理コンソールに、BizTalk グループを追加します。  
  
       BizTalk Server では、今すぐが復元され、実行する必要があります。 次に、新しい移行先サーバーへのバックアップの書き込みを開始する BizTalk Server のバックアップ ジョブを構成します。 新しい送信先システムを再構成する必要があります。  

## <a name="important"></a>重要

- データベースを復元した後、ルール エンジンを使用する場合、BizTalk Server グループのすべてのサーバーでは、ルール エンジン更新サービスを再起動する必要があります。 参照してください[Services を開始、停止、一時停止、再開、または BizTalk Server を再起動する方法](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)します。  
- BAM を使用している場合は、BAM データベースを復元する時間がようになりました。 参照してください[のバックアップと復元 BAM](../core/backing-up-and-restoring-bam.md)します。  
- データベースを移動する、BizTalk EDI または RosettaNet アクセラレータを使用している場合は、いくつかの SQL ポートは、BizTalk データベースに対してセットアップにする可能性があります。 バインドのエクスポート、古いデータベース リンクでは、検索し、データベースへのリンクを適宜置換します。 

## <a name="next-steps"></a>次の手順  
 [BAM のバックアップと復元](../core/backing-up-and-restoring-bam.md)  
  
## <a name="see-also"></a>参照  

 [バックアップ BizTalk Server ジョブを構成します。](../core/how-to-configure-the-backup-biztalk-server-job.md)   
 [ログ配布用に送信先システムを構成する](../core/how-to-configure-the-destination-system-for-log-shipping.md)

