---
title: スケジュール SQL Server Integration Services パッケージ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 037ae2cf-c352-4823-95df-9a723f2b5a81
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43ce70dc97de2958add5c583646b7825d981982b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001795"
---
# <a name="scheduling-sql-server-integration-services-packages"></a>SQL Server Integration Services パッケージのスケジュール設定
ユーザーは、オンライン分析処理 (OLAP) キューブに格納されたデータに基づいている BAM ビューを作成します。 キューブのデータはキューブ更新 Integration Services パッケージによって更新されるので、OLAP ビューには最新のデータが反映されます。  
  
 OLAP ビューを利用するには、このパッケージを少なくとも 1 回実行する必要があります。 継続的に保守を行うには、このパッケージを定期的に実行するようにスケジュールを設定する必要があります。  
  
> [!IMPORTANT]
>  BAM スター スキーマ データベースの復元または [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] の停止後にキューブ更新 Integration Services パッケージを実行する場合、パッケージを正常に実行するには、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 分析マネージャーでデータ ソースを最新の情報に更新するか、OLAP サービスを再開する必要があります。  
  
 保存したパッケージを 1 回または一定の間隔で特定の時刻に実行するようにスケジュールを設定できます。 以下に例を示します。  
  
- 毎日の午前 0 時です。  
  
- 毎週日曜日の午前 6 時。  
  
- 月の初日または最終日。  
  
  スケジュールが設定されたパッケージは、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] によってジョブとして実行されます。  
  
  実行する方法についての[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]、パッケージを参照してください[ http://go.microsoft.com/fwlink/?LinkId=125738](http://go.microsoft.com/fwlink/?LinkId=125738)します。  
  
> [!NOTE]
>  既定では、BAM SSIS パッケージのアーカイブとキューブ作成のログ記録が有効で、ログは msdb データベースに格納されます。 このため、BAM アクティビティが大量であったり BAM 所有の SSIS パッケージを頻繁に実行する場合、時間がたつにつれ SSIS イベント ログ データが膨大な量になる可能性があります。 これを解決するには古いログ エントリを削除します。これらのエントリの主な用途はデバッグなので削除してもかまいません。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行するには、BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-run-the-cube-update-integration-services-package"></a>キューブ更新 Integration Services パッケージを実行するには  
  
1.  クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 SP1**または**Microsoft SQL Server 2008 R2**順にクリックします**SQL Server Management Studio**します。  
  
2.  **サーバーへの接続** ダイアログ ボックスで、**サーバーの種類**ドロップダウン リストで、 **Integration Services**します。  
  
3.  **サーバー名**ドロップダウン リストで、パッケージを実行しているサーバーの名前を選択します。  
  
4.  **認証**ドロップダウン リストで、サーバーへの接続に使用する認証の種類を選択します。  
  
5.  必要に応じて、ユーザー名とパスワードを入力します。  
  
6.  **[接続]** をクリックします。  
  
7.  コンソール ツリーで、展開**Integration Services**、展開**格納されたパッケージ**、 をクリックし、 **MSDB**します。  
  
8.  右クリックし、 **bam_an _\<ビュー名\>** パッケージ化、およびクリックして**パッケージの実行**します。  
  
### <a name="to-run-the-maintaining-bam-data-integration-services-package"></a>BAM データ管理 Integration Services パッケージを実行するには  
  
1.  クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 SP1**または**Microsoft SQL Server 2008 R2**順にクリックします**SQL Server Management Studio**します。  
  
2.  **サーバーへの接続** ダイアログ ボックスで、**サーバーの種類**ドロップダウン リストで、 **Integration Services**します。  
  
3.  **サーバー名**ドロップダウン リストで、パッケージを実行しているサーバーの名前を選択します。  
  
4.  **認証**ドロップダウン リストで、サーバーへの接続に使用する認証の種類を選択します。  
  
5.  必要に応じて、ユーザー名とパスワードを入力します。  
  
6.  **[接続]** をクリックします。  
  
7.  コンソール ツリーで、展開**Integration Services**、展開**格納されたパッケージ**、 をクリックし、 **MSDB**します。  
  
8.  右クリックし、 **bam_dm _\<アクティビティ名\>** パッケージ化、およびクリックして**パッケージの実行**します。  
  
### <a name="to-schedule-the-packages-to-run-regularly"></a>パッケージを定期的に実行するようにスケジュールを設定するには  
  
1.  クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 SP1**または**Microsoft SQL Server 2008 R2**順にクリックします**SQL Server Management Studio**します。  
  
2.  **サーバーへの接続** ダイアログ ボックスで、**サーバーの種類**ドロップダウン リストで、**データベース エンジン**します。  
  
3.  **サーバー名**ドロップダウン リストで、パッケージを実行しているサーバーの名前を選択します。  
  
4.  **認証**ドロップダウン リストで、サーバーへの接続に使用する認証の種類を選択します。  
  
5.  必要に応じて、ユーザー名とパスワードを入力します。  
  
6.  **[接続]** をクリックします。  
  
7.  コンソール ツリーで、サーバーを展開し、選択**SQL Server エージェント**します。  
  
8.  場合**SQL Server エージェント**は右クリックし、無効になっています。 **SQL Server エージェント**、し、**開始**します。  
  
9. 右クリック**SQL Server エージェント**、選び**新しいジョブ**します。  
  
10. **新しいジョブ**ダイアログ ボックスで、ジョブの名前を入力、**名前**テキスト ボックス。  
  
11. **ページの選択**ウィンドウで、をクリックして**手順**、順にクリックします**新規**します。 開き、**新しいジョブ ステップ** ダイアログ ボックス。  
  
12. **ステップ名**テキスト ボックスに、ステップの識別名を入力します。  
  
13. **型**ドロップダウン リストで、 **SQL Server Integration Services パッケージ**し、**パッケージ ソース**ドロップダウン リストで、 **SSIS パッケージ ストア**.  
  
14. **Server**ドロップダウン リストで、ジョブを実行しているサーバーを選択します。  
  
15. ファイル セレクター ボタンをクリックして、**パッケージ**テキスト ボックスに、スケジュールを設定するパッケージを選択します (いずれか、 **bam_dm _\<アクティビティ名\>** または**bam_an _\<ビュー名\>** パッケージ)、順にクリックします**OK**します。  
  
16. **ページの選択**ウィンドウで、をクリックして**スケジュール**、順にクリックします**新規**します。 開き、**新しいジョブ スケジュール** ダイアログ ボックス。  
  
17. **名前**テキスト ボックスに、スケジュールの名前を入力します。  
  
18. 頻度のフィールドを使用してスケジュールを作成します。  
  
19. **[OK]** をクリックしてジョブを保存します。  
  
    > [!NOTE]
    >  SQL Server の既定以外のインスタンスで BAM が構成されている場合は、BAM_AN_POCube DTSPackage は正確にスケジュール/実行されません。 パッケージが実行を続けるためには、構成ファイルを変更する必要があります。 詳細については、ある「変更の内容の構成ファイル」セクションを参照してください[ http://go.microsoft.com/fwlink/?LinkId=196768](http://go.microsoft.com/fwlink/?LinkId=196768)します。  
  
## <a name="see-also"></a>参照  
 [BAM データベースの管理](../core/managing-bam-databases.md)