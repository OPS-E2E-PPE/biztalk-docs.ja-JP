---
title: ログ配布用に送信先システムを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 2015-12-03
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, log shipping
- system failures, preventing
- log shipping
- databases, backing up
- backing up, databases
- system failures, backing up
- backing up, system failures
ms.assetid: 7b4425f5-b105-4fb2-a503-94ca1e75ad55
caps.latest.revision: 54
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58951da7a59b041ef97b2b93e5153cc27d517b0e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340860"
---
# <a name="how-to-configure-the-destination-system-for-log-shipping"></a>ログ配布用に送信先システムを構成する方法
ログ配布は、システム障害が発生した場合、ダウンタイムを短縮するスタンバイ サーバーの機能を提供します。 ログ配布を使用すると、ソース システムから送信先システムにトランザクション ログを自動的に送信できます。 送信先システムでトランザクション ログの復元、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース; ソース データベースと密接に同期を維持することです。  
  
 ログ配布は、1 台のサーバーと分散型サーバー環境の両方で機能します。 サーバーまたはライブ データが含まれているサーバーのグループは、ソース (またはプライマリ) と呼ばれるはシステム。 サーバーまたはデータベースのバックアップ ソースで生成されたファイル (またはプライマリ) システムの復元に使用されるサーバーのグループが先 (またはセカンダリ) と呼ばれるシステム。  
  
 [ログ配布について](https://docs.microsoft.com/sql/database-engine/log-shipping/about-log-shipping-sql-server)ドキュメントを sql には、特定の詳細情報を提供します。  
  
 次の手順を使用すると、1 つのソース システムの 1 つのサーバーで構成されるターゲット システムを作成します。 送信先システムに複数のサーバーが含まれている場合は、各送信先サーバーで手順を繰り返します。  
  
> [!IMPORTANT]
>  常に安全な場所にバックアップ ファイルのコピーを保持します。 ログ バックアップがある場合でもバックアップ ファイルがない場合、データベースを復元することはできません。  
  
## <a name="prerequisites"></a>前提条件  
* メンバーとしてサインイン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。  
  
* 送信元と送信先システムで同じバージョンの SQL Server を使用します。 SQL Server は、元とコピー先のシステムで、同じ相対的場所にインストールする必要があります。  
  
* SQL トランザクション ログのディレクトリ (します。LDF ファイル)、ソース システムする必要がありますも、送信先システムに存在します。 送信先システムでこのディレクトリでない場合は、同じ名前と、ソース システム上とアクセス許可を持つ、ディレクトリを作成します。  
  
### <a name="configure-the-destination-system-for-log-shipping"></a>ログ配布用に送信先システムを構成します。  
  
1. 送信先システムで開く**SQL Server Management Studio**、し、SQL Server に接続します。 選択**マスター**から利用可能なデータベースです。  
  
2. **ファイル**] メニューの [**オープン**次の SQL スクリプト。  
  
   ```    
   %SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\LogShipping_Destination_Schema.sql  
   ```  
  
3. **クエリ**メニューの  **Execute**します。  
  
    *LogShipping_Destination_Schema*され、送信先システムでソース データベースの復元に使用するテーブルを再作成します。 データベース復旧中、ソース システムの BizTalkMgmtDb データベースからインポートされたバックアップ履歴のコピーの一覧を格納するテーブルが含まれ、SQL Server エージェント ジョブに関する情報を構成するソース データベースに対して実行します。  
  
4. **ファイル**] メニューの [**オープン**次の SQL スクリプト。  
  
   ```    
   %SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\LogShipping_Destination_Logic.sql  
   ```  
  
5. **クエリ**メニューの  **Execute**します。  
  
6. 送信先システムとして指定したコンピューターまたはコンピューターで開く**SQL Server Management Studio**し、SQL Server に接続します。  
  
7. 選択**新しいクエリ**します。 クエリ ウィンドウで、次のコマンドを貼り付けます。  
  
   ```  
   exec bts_ConfigureBizTalkLogShipping @nvcDescription = '<MyLogShippingSolution>',  
   @nvcMgmtDatabaseName = '<BizTalkServerManagementDatabaseName>',  
   @nvcMgmtServerName = '<BizTalkServerManagementDatabaseServer>',  
   @SourceServerName = null, -- null indicates that this destination server restores all databases  
   @fLinkServers = 1 -- 1 automatically links the server to the management database  
   ```  
  
    そうしたら：  
  
   1.  送信先システムで有効にする **[Ad Hoc Distributed Queries](https://docs.microsoft.com/sql/database-engine/configure-windows/server-configuration-options-sql-server)** します。  
  
   2.  クエリ ウィンドウに、 *\<MyLogShippingSolution\>* わかりやすい説明を単一引用符で囲みます。  
  
   3.  クエリ ウィンドウに、 *\<BizTalkServerManagementDatabaseName\>* と*\<BizTalkServerManagementDatabaseServer\>* で名前と、単一引用符で囲まれたソース BizTalk 管理データベースの場所。  
  
   > [!NOTE]
   >  1 つ以上のソース サーバーがある場合は、独自の移行先サーバーに各送信元サーバーを復元できます。 各送信先サーバーでの **@SourceServerName = null**パラメーター、置換*null*適切なソース サーバーの名前を単一引用符で囲みます (たとえば、  **@SourceServerName = 'MySourceServer'**)。  
  
8. **クエリ**メニューの  **Execute**します。  
  
   > [!IMPORTANT]
   >  クエリに失敗した場合、クエリの問題を修正した後に、送信先システムを再構成するには、この手順の手順 1 から始める必要があります。  
  
   > [!NOTE]
   >  送信先システムで、復元ジョブは、ソース データベース サーバーに存在していた、同じ場所に復元された各データベースのログとデータ ファイルを再作成しようとします。  
  
9. 送信先システムで**SQL Server Management Studio**、展開**SQL Server エージェント**、展開と**ジョブ**します。  
  
     詳細ペインでは、3 つの新しいジョブがあります。  
  
   - **BTS ログの配布のバックアップ履歴の取得**  
  
      この BizTalk ジョブは、元のバックアップ履歴レコードを送信先に移動します。 なるは、既定では 1 分ごとに実行する予定です。 先に、ソースから履歴レコードを移動するためにできる限り頻繁にこのジョブが実行されます。 ソース システムにシステムに障害が発生した場合は、送信先システムとして識別されるサーバーは、既にインポートされている履歴レコードを処理し続けます。  
  
   - **BTS Server のログ配布データベースの復元**  
  
      この BizTalk ジョブは、移行先サーバーに、ソースとして指定したデータベースのバックアップ ファイルを復元します。 なるは、既定では 1 分ごとに実行する予定です。 このジョブは、復元するバックアップ ファイルがある限り、完了することがなく継続的に実行されます。 追加の予防措置としてジョブを実行できますこのので、さらにタスクが完了したことを確認します。  
  
   - **BTS ログのマークまで復元の配布**  
  
      この BizTalk ジョブは、最後のログ バックアップ内のマークまでにすべてのデータベースを復元します。 これによりはすべて、データベースのトランザクション上一貫性のある状態であります。 さらに、このジョブがソース システムになっていた送信先システムで SQL Server エージェント ジョブのすべての演算子を作成します再します。  
  
     > [!IMPORTANT]
     >  失敗しないことを確認します。 これらのジョブを監視する必要があります。  
  
10. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で、次のフォルダーに移動します。  
  
     32 ビット コンピューター: %SystemDrive%\Program files \microsoft BizTalk Server\<バージョン\>\Schema\Restore  
  
     64 ビット コンピューター: %SystemDrive%\Program Files (x86) \Microsoft BizTalk Server\<バージョン\>\Bins32\Schema\Restore  
  
11. 右クリック**SampleUpdateInfo.xml**、選び**編集**します。 次の操作を行います。  
  
    -   すべてのインスタンスを置き換える **"SourceServer"** ソース システムの名前に置き換えます。  
  
    -   すべてのインスタンスを置き換える **"DestinationServer"** 送信先システムの名前に置き換えます。  
  
    > [!IMPORTANT]
    >  送信元システムおよび送信先システムの名前は、引用符で囲んでください。  
    > 
    > [!NOTE]
    >  いずれかの名前を変更した場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース、XML ファイル内のデータベース名を更新することも必要があります。  
    > 
    > [!NOTE]
    >  BAM を構成している場合は、次の行を追加する必要があります、 **OtherDatabases**のセクション、 **SampleUpdateInfo.xml** BAMAlertsApplication、BAMAlertsNSMain データベースのファイル。   
    > `<Database Name="BAM Alerts Application DB" oldDBName="BAMAlertsApplication" oldDBServer="SourceServer" newDBName=" BAMAlertsApplication" newDBServer="DestinationServer"/>`  
    > `<Database Name="BAM Alerts Instance DB" oldDBName="BAMAlertsNSMain" oldDBServer="SourceServer" newDBName="BAMAlertsNSMain" newDBServer="DestinationServer"/>`  
    > 
    >  これら 2 つのデータベースの既定の名前を変更した場合は、実際のデータベース名を使用してください。  
  
12. 複数のメッセージ ボックス データベースがある場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システムは、リストに別の MessageBoxDB 行を追加し、設定**IsMaster =「0」** マスター以外のデータベースにします。  
  
13. BAM またはルール エンジンを使用している場合は、必要に応じてこれらの行をコメント解除します。  
  
14. すべてのカスタム データベースがあれば、下に追加、 **\<OtherDatabases\>** セクション。 参照してください[カスタム データベースをバックアップする方法](../core/how-to-back-up-custom-databases.md)します。  
  
15. ファイルの編集を終了したら、ファイルを保存して閉じます。  
  
## <a name="next-steps"></a>次の手順  
 [データベースを復元する方法](../core/how-to-restore-your-databases.md)  
  
## <a name="see-also"></a>参照  
 [バックアップ BizTalk Server ジョブを構成する方法](../core/how-to-configure-the-backup-biztalk-server-job.md)   
 [バックアップ BizTalk Server のジョブをスケジュールする方法](../core/how-to-schedule-the-backup-biztalk-server-job.md)   
 [カスタム データベースをバックアップする方法](../core/how-to-back-up-custom-databases.md)