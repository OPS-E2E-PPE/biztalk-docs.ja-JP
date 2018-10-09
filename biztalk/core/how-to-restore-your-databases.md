---
title: データベースの復元 |Microsoft Docs
description: SQL エージェント ジョブ, を使用して、UpdateDatabase.vbs と UpdateRegistry.vbs スクリプトの実行など、BizTalk Server データベースを復元する手順を参照してください。 また、BizTalk 管理コンソールで、SQL Server インスタンス名の更新を含む、データベースの復元後の対処方法を参照してください。
ms.custom: ''
ms.date: 09/30/18
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
ms.openlocfilehash: c318511902b31ffbe3fab4e055bdbf097d0f6865
ms.sourcegitcommit: 51ce182c5b71d3999a3920dd884bc9ec8334a899
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "48575685"
---
# <a name="how-to-restore-your-databases"></a>データベースを復元する方法
データベース間のトランザクション状態の一貫性を保証するには、すべてのデータベースを同じマークに復元する必要があります。 参照してください[マークされたトランザクション、完全バックアップ、バックアップとログ バックアップ](../core/marked-transactions-full-backups-and-log-backups.md)します。  
  
 送信先システムにあるサーバーが 1 つだけの場合は、(最新のセットを除く) すべてのログのバックアップ セットが復元されていることを確認します。 参照してください[バックアップを復元の履歴を表示する](../core/viewing-the-history-of-restored-backups.md)します。 すべてのログ バックアップ セットの復元が完了していない場合、復元ジョブが現在実行中でなければ、ジョブを実行します (必要に応じて手動で)。 復元できる未処理のバックアップ セットがある場合は、ジョブにまで処理すべて復元します。  
  
 送信先システムに複数のサーバーがある場合は、すべてのサーバーの復元を同じバックアップ セットで行う必要があります。 各サーバーで復元の履歴を表示し、設定が復元された最新のログ バックアップが、すべてのサーバーで同じであるかどうかを確認します。 同一の最新ログ バックアップ セットで復元されていないサーバーがある場合は、そのサーバーに対する復元ジョブを手動で実行する必要があります。  
  
 すべてのサーバーが同じバックアップ セットになったら、最後のセットは手動で復元できます。  
  
 adm_BackupHistory テーブルは、ソース システムのログ配布プロセスの中心的な履歴ポイントです。 実行されたバックアップ作業はすべてこのテーブルに記録されます。 送信先システムにあるすべてのサーバーは、復元作業の実行に必要な情報を受け取るためにこのテーブルから読み取ります。  
  
> [!NOTE]
>  - BAM プライマリ インポート データベースをバックアップから復元する場合は、BAM プライマリよりも古いバックアップを使用して BAM アーカイブ、BAM スター スキーマ、および BAM 分析データベースも復元する必要があります。 参照してください[のバックアップと復元 BAM](../core/backing-up-and-restoring-bam.md)します。  
>  - 送信元データベースの完全バックアップまたはログ バックアップを BizTalk Server のバックアップ ジョブで使用した保存場所から移動する場合は、LogFileLocation または DBFileLocation の値として、送信先システムが完全/ログ バックアップ ファイルを読み取るための新しい場所を設定します。これにより、送信先システムにある bts_LogShippingDatabases テーブルで、送信元データベースに関連付けられた行が更新されます。 bts_ConfigureBtsLogShipping ストアド プロシージャを実行すると、このテーブルに値が入力されます。 これらの列は既定で Null に設定されます。この値は、adm_BackupHistory テーブルに記録されている場所から送信先システムがバックアップ ファイルを読み取ることを意味します。  
>  - バックアップ ファイルのコピーは、常に安全な場所に保管してください。 ログ バックアップがあっても、バックアップ ファイルがなければデータベースを復元することはできません。  
  
## <a name="prerequisites"></a>前提条件  
 SQL Server ロールの sysadmin に属するアカウントを使用して、SQL Server にログインします。  
  
## <a name="restore-your-databases"></a>データベースを復元します。  
  
1. 送信先システムで開く**SQL Server Management Studio**、し、SQL Server に接続します。  
  
2. **[SQL Server エージェント]** を展開し、**[ジョブ]** を展開します。 次の操作を行います。  
  
   1. 右クリックし、 **BTS ログの配布 - バックアップ履歴の取得**ジョブし、選択**を無効にする**します。 状態が [成功] に変わります。  
  
   2. 右クリックし、 **BTS ログの配布 - データベースの復元**ジョブし、選択**を無効にする**します。 状態が [成功] に変わります。  
  
   3. 右クリックし、 **BTS ログの配布 - マークまで復元**選択**ステップでジョブを開始**します。 選択**ステップ ID 1**選択**開始**します。  
  
       状態が変わると**成功**、BizTalk Server データベースと SQL Server エージェント ジョブが送信先システムに復元されます。  
  
   > [!IMPORTANT]
   >  場合、**状態**エラー原因を特定する [メッセージ] フィールドに、リンクを選択します。 これらのジョブを続行するには、状態が [成功] になっていることが必要です。  
  
3. SampleUpdateInfo.xml ファイルを編集する BizTalk Server でコマンド プロンプトを開きに移動します。  
  
    32 ビット コンピューター: `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`  
  
    64 ビット コンピューター: `%SystemDrive%\Program Files (x86)\Microsoft BizTalk Server <version>\Bins32\Schema\Restore`  
  
4. コマンド プロンプトで、次のように入力します。  
  
    `cscript UpdateDatabase.vbs SampleUpdateInfo.xml`  
  
    このスクリプトにより、他のデータベースの場所に関する情報を格納しているテーブルがすべて更新されます。  
  
   > [!IMPORTANT]
   >  - UpdateDatabase.vbs を実行**1 つ**BizTalk グループ内のサーバー。  
   >  - 64 ビット コンピューターの場合は、UpdateDatabase.vbs を 64 ビット コマンド プロンプトから実行する必要があります。 64 ビット コンピューターにおける既定のコマンド プロンプトは、64 ビット コマンド プロンプト (%SystemDrive%\windows\System32\cmd.exe) であることに注意してください。  
   >  - BizTalk の EDI エンジンが必要としない SampleUpdateInfo.xml 独自の変更のいずれかのデータベースを復元します。  これは、EDI テーブルにアクセスする、BizTalkDTADb データベースへの接続に依存します。  
  
5. 編集した SampleUpdateInfo.xml ファイルを次のフォルダーにコピー**すべて**この BizTalk グループに BizTalk Server を実行しているコンピューター。  
  
    32 ビット コンピューター: コピー `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`  
  
    64 ビット コンピューター: コピー `%SystemDrive%\Program Files (x86)\Microsoft BizTalk Server <version>\Bins32\Schema\Restore`  
  
6. **各**BizTalk Server グループ内のコンピューターが、コマンド プロンプトを開きに移動します。  
  
    32 ビット コンピューター: `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`  
  
    64 ビット コンピューター: `%SystemDrive%\Program Files (x86)Microsoft BizTalk Server <version>\Bins32\Schema\Restore`  
  
7. コマンド プロンプトで、次のように入力します。  
  
    `cscript UpdateRegistry.vbs SampleUpdateInfo.xml`  
  
    このスクリプトにより、他のデータベースの場所に関する情報を格納しているすべてのレジストリ エントリが更新されます。  
  
   > [!IMPORTANT]
   >  - UpdateRegistry.vbs を実行**すべて**BizTalk グループ内のサーバー。  
   >  - 64 ビット コンピューターの場合は、UpdateRegistry.vbs を 64 ビット コマンド プロンプトから実行する必要があります。  64 ビット コンピューターにおける既定のコマンド プロンプトは、64 ビット コマンド プロンプト (%SystemDrive%\windows\System32\cmd.exe) であることに注意してください。  
  
8. すべての BizTalk Server サービスを再起動します。 参照してください[Services を開始、停止、一時停止、再開、または BizTalk Server を再起動する方法](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)します。  
  
9. データベースを復元した後で、Windows Management Instrumentation サービスを再起動します。  
  
    1.  開いている**services.msc**します。  
  
    2.  右クリックして**Windows Management Instrumentation**、し、**再起動**します。  
  
10. 開いている**BizTalk Server 管理**します。 次の操作を行います。  
  
    1. 右クリックし、 **BizTalk グループ**選択**削除**します。  
  
    2. 右クリック**BizTalk Server 管理**選択**既存グループへの接続**します。  
  
    3. **SQL Server 名**、BizTalk 管理データベースをホストする SQL Server インスタンスの名前を選択します。 SQL Server インスタンスを選択すると、BizTalk Server コンピューターに BizTalk Server データベースが自動的に検出します。  
  
    4. **データベース名**、BizTalk 管理データベースを選択します (**BizTalkMgmtDb**既定で)、し、 **OK**。  
  
       BizTalk Server 管理コンソールでは、管理コンソールに、BizTalk グループを追加します。  
  
       BizTalk Server では、今すぐが復元され、実行する必要があります。 次に、新しい移行先サーバーへのバックアップの書き込みを開始する BizTalk Server のバックアップ ジョブを構成します。 また、新しい送信先システムの再構成も必要です。  

## <a name="important"></a>重要

- データベースを復元した後、ルール エンジンを使用する場合、BizTalk Server グループのすべてのサーバーでは、ルール エンジン更新サービスを再起動する必要があります。 参照してください[Services を開始、停止、一時停止、再開、または BizTalk Server を再起動する方法](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)します。  
- BAM を使用している場合は、BAM データベースを復元する時間がようになりました。 参照してください[のバックアップと復元 BAM](../core/backing-up-and-restoring-bam.md)します。  
- データベースを移動する、BizTalk EDI または RosettaNet アクセラレータを使用している場合は、いくつかの SQL ポートは、BizTalk データベースに対してセットアップにする可能性があります。 バインドのエクスポート、古いデータベース リンクでは、検索し、データベースへのリンクを適宜置換します。 

## <a name="next-steps"></a>次の手順  
 [バックアップおよび BAM を復元します。](../core/backing-up-and-restoring-bam.md)  
  
## <a name="see-also"></a>参照  
 [バックアップ BizTalk Server ジョブを構成します。](../core/how-to-configure-the-backup-biztalk-server-job.md)   
 [ログ配布用に送信先システムを構成する](../core/how-to-configure-the-destination-system-for-log-shipping.md)
