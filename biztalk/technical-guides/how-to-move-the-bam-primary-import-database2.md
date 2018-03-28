---
title: BAM プライマリ インポート Database2 を移動する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bc4f2656-2faa-4503-9551-05e1b6eceb1a
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd6abeeb04521e95b32b4d6007dcc7f1f532bdbb
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-move-the-bam-primary-import-database"></a>BAM プライマリ インポート データベースを移動する方法
ここでは、BAM プライマリ インポート データベースを他のサーバーに移動する手順について説明します。 エンド ツー エンドのシナリオの観点から BAM プライマリ インポート データベースの移動にも 2 つの主要な手順が含まれます。  
  
-   [BAM プライマリ インポート データベースを移動します。](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_MovingBAMPI)  
  
-   [新しい BAM プライマリ インポート データベースへの参照を更新](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_BAMPIRef)  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行するには、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin 固定サーバー ロールのメンバーであるアカウントを使用してログオンする必要があります。  
  
##  <a name="BKMK_MovingBAMPI"></a> BAM プライマリ インポート データベースを移動します。  
 BAM プライマリ インポート データベースを移動する次の手順で、手順を実行します。  
  
#### <a name="to-move-the-bam-primary-import-database"></a>BAM プライマリ インポート データベースを移動するには  
  
1.  すべての BAM キューブ更新およびデータ保守 SSIS パッケージを停止するか、BAM プライマリ インポート データベースを復元が完了するまで実行されないように措置を講じます。  
  
2.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サービスをすべて停止します。 詳細については、トピックを参照してください。[開始方法、停止、一時停止、再開、または BizTalk Server サービスを再起動](http://go.microsoft.com/fwlink/?LinkId=154394)(http://go.microsoft.com/fwlink/?LinkId=154394)で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
3.  IIS サービスを停止します。  
  
4.  BAM 警告 Notification service を停止します。  
  
    1.  をクリックして **開始**, 、 をクリックして **実行**, 、型 **cmd**, 、 をクリックし、 **ok**します。  
  
    2.  コマンド プロンプトで、次のように入力します。  
  
         **Net stop NS$BamAlerts**  
  
5.  BAM プライマリをバックアップには、古いサーバー上のデータベースをインポートします。 データベースをバックアップする方法の手順については、指示に従ってデータベースをバックアップする方法[する方法:、データベースのバックアップ (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (http://go.microsoft.com/fwlink/?LinkId=156510)で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]オンライン ブック。  
  
6.  BAM プライマリ インポート データベースに新しいコピー[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューター。  
  
7.  新しいサーバーで、BAM プライマリ インポート データベースを復元します。 データベースを復元する方法の指示に従って、データベースを復元する方法についての[する方法: データベースのバックアップ (SQL Server Management Studio) を復元](http://go.microsoft.com/fwlink/?LinkId=156511)(http://go.microsoft.com/fwlink/?LinkId=156511)で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]オンライン ブック。  
  
    > [!NOTE]  
    >  BAM プライマリ インポート データベースをバックアップから復元する場合は、BAM プライマリよりも古いバックアップを使用して BAM アーカイブ、BAM スター スキーマ、および BAM 分析データベースも復元する必要があります。  
  
##  <a name="BKMK_BAMPIRef"></a> 新しい BAM プライマリ インポート データベースへの参照を更新  
 データベースを移動した後は、新しい BAM プライマリ インポート データベースへすべての参照を更新する必要があります。 次の参照を更新する必要があります。  
  
-   新しいサーバー名では、すべての BizTalk データベースを更新します。 UpdateDatabase.vbs のスクリプトを使用して行うことができます。 参照してください[BizTalk データベースを新しいサーバー名で更新する](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdateDB)です。  
  
-   BAM ポータルの Web.config ファイルを更新します。 参照してください[、BAM ポータルの Web.config ファイルを更新する](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_Config)です。  
  
-   すべての BAM ライブ データの Microsoft Excel ファイルで BAM プライマリ インポート データベースへの参照を更新します。 参照してください[BAM ライブ データの Microsoft Excel ファイル内の参照を更新する](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdateExcel)です。  
  
-   すべての BAM analysis の SSIS パッケージで新しいサーバーおよびデータベース名を更新します。 参照してください[サーバーとすべての BAM SSIS パッケージ内のデータベース名を更新する](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdatePckg)です。  
  
-   サーバーとデータベースの新しい名前のデータ ソースのすべての OLAP キューブを更新します。 参照してください[サーバーとすべての OLAP キューブのデータ ソースのデータベース名を更新する](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdateDSOLAP)です。  
  
###  <a name="BKMK_UpdateDB"></a> 新しいサーバー名で BizTalk データベースを更新するには  
  
1.  BizTalk Server を実行するコンピューター上には、次のフォルダーを参照してください。  
  
    -   場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が 64 ビット バージョンの Windows Server にインストールされています。  
  
         **%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\bins32\Schema\Restore**  
  
    -   場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が 32 ビット バージョンの Windows Server にインストールされています。  
  
         **%ProgramFiles%\Microsoft BizTalk Server 2010\Schema\Restore**  
  
2.  右クリック **SampleUpdateInfo.xml**, 、クリックして **編集**します。  
  
3.  BizTalkMgmtDb、OldPrimaryImportDatabase、PrimaryImportDatabase、ArchivingDatabase、AnalysisDatabase、StarSchemaDatabase、および Alert を除いて、すべてのデータベース セクションをコメント アウトします。  
  
4.  `OldPrimaryImportDatabase` 、ファイルのセクションの`ServerName`プロパティ、置換**SourceServer**データベースが存在する既存のサーバーの名前に置き換えます。  
  
5.  `PrimaryImportDatabase` 、ファイルのセクションの`ServerName`プロパティ、置換**DestinationServer**を BAM プライマリ インポート データベースを移動したサーバーの名前  
  
6.  BizTalkMgmtDb、ArchivingDatabase、AnalysisDatabase、StarSchemaDatabase、および警告のセクションでは、設定"SourceServer"と"Destination Server"、既存のサーバーの名前にこれらのデータベースが存在します。  
  
    > [!IMPORTANT]  
    >  送信元システムおよび送信先システムの名前は、引用符で囲んでください。  
  
    > [!NOTE]  
    >  いずれかの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースの名前を変更した場合、それに応じてデータベース名も更新する必要があります。  
  
7.  ファイルの編集を終了したら、このファイルを保存して閉じます。  
  
8.  をクリックして **開始**, 、 をクリックして **実行**, 、型 **cmd**, 、 をクリックし、 **ok**します。  
  
9. コマンド プロンプトで、次のディレクトリに移動します  
  
    -   場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が 64 ビット バージョンの Windows Server にインストールされています。  
  
         **%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Schema\Restore**  
  
    -   場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が 32 ビット バージョンの Windows Server にインストールされています。  
  
         **%ProgramFiles%\Microsoft BizTalk Server 2010\Schema\Restore**  
  
10. コマンド プロンプトで、次のように入力します。  
  
     **cscript UpdateDatabase.vbs SampleUpdateInfo.xml**  
  
###  <a name="BKMK_Config"></a> BAM ポータルの Web.config ファイルを更新するには  
  
1.  BizTalk Server を実行するコンピューター上には、下にある Web.config ファイルを更新**\<ドライブ\>: \Program Files\Microsoft BizTalk Server 2010\BAMPortal\BAMManagementService\Web.Config**です。Web.config の次のセクションではサーバーおよびデータベース名を更新します。  
  
    ```  
    <appSettings>  
      <add key="BamServer" value="<ServerName>" />  
      <add key="BamDatabase" value="<DatabaseName>" />  
    </appSettings>  
    ```  
  
2.  BizTalk Server を実行するコンピューター上には、下にある Web.config ファイルを更新**\<ドライブ\>: \Program Files\Microsoft BizTalk Server 2010\BAMPortal\BAMQueryService\Web.Config**です。Web.config の次のセクションではサーバーおよびデータベース名を更新します。  
  
    ```  
    <appSettings>  
      <add key="BamServer" value="<ServerName>" />  
      <add key="BamDatabase" value="<DatabaseName>" />  
      <add key="MaxResultRows" value="2000" />  
    </appSettings>  
    ```  
  
3.  保存してファイルを閉じます。  
  
###  <a name="BKMK_UpdateExcel"></a> BAM ライブ データの Microsoft Excel ファイル内の参照を更新するには  
  
1.  Excel ライブ データ ファイルを開きます。 ファイル名の末尾は _LiveData.xls となっています。  
  
2.  **BAM**  メニューのをクリックして **BAM データベースの接続**します。  
  
3.  **[BAM データベースの**] ダイアログ ボックスに、入力、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューターおよび BAMPrimaryImport データベース、およびをクリックして**OK**です。  
  
4.  **ファイル**  メニューのをクリックして **を閉じるし、Microsoft Excel へ戻る**します。  
  
5.  **[ファイル]** メニューの **[保存]**をクリックします。  
  
###  <a name="BKMK_UpdatePckg"></a> サーバーとすべての BAM SSIS パッケージ内のデータベース名を更新するには  
  
1.  すべての BAM 分析 SSIS パッケージが付きます。「bam_an _」または「bam_dm _」ではサーバーおよびデータベース名を更新します。 これを行うには、をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 R2**または**Microsoft SQL Server 2008 SP1**をクリックし、**SQL Server Business Intelligence Development Studio**です。  
  
2.  SQL Server Business Intelligence Development Studio で、プロジェクトを新規作成します。 クリックして **ファイル**, 、 をクリックして **新規**, 、 をクリックし、 **プロジェクト**します。  
  
3.  **新しいプロジェクト** ダイアログ ボックスで、**プロジェクトの種類**ボックスで、クリックして**ビジネス インテリジェンス プロジェクト**です。 右側のウィンドウでの**テンプレート**ボックスで、をクリックして**Integration Services プロジェクト**をクリックし、 **[ok]**です。  
  
4.  **Integration Services プロジェクト**ダイアログ ボックスで、ソリューション エクスプ ローラーで右クリックし**SSIS パッケージ**、クリックして**既存のパッケージの追加**です。  
  
5.  **既存のパッケージのコピーを追加** ダイアログ ボックスで、**サーバー**ドロップダウン リスト ボックスで、bam_an _ *、bam_dm _ * パッケージを含むサーバーを選択します。  
  
6.  **パッケージ パス**, 、省略記号ボタンをクリックします。  
  
7.  **SSIS パッケージ** ダイアログ ボックスで、更新するには、をクリックするパッケージを選択**ok**、順にクリック**OK**です。  
  
     これで、パッケージがソリューション エクスプローラにリストされました。  
  
8.  ソリューション エクスプ ローラーで、前の手順で追加したパッケージをダブルクリックします。 **接続マネージャー** (画面の下半分に使用可能) タブで、データ ソース番号 1 (BAMPrimaryImport データベース) をダブルクリックします。  
  
9. **接続マネージャー**  ダイアログ ボックスで、**サーバー名**ボックスで、サーバーの名前を入力し、をクリックして**OK**です。  
  
10. クリックして、**パッケージ エクスプ ローラー**  タブをダブルクリックして、**変数**フォルダー、しの値を更新、 **PrimaryImportDatabase**と**PrimaryImportServer**変数。 新しいサーバーやデータベースを指定する値を更新する必要があります。  
  
    > [!NOTE]  
    >  手順 4 ~ 10 を更新するすべてのパッケージを繰り返します。  
  
11. クリックしてから**ファイル** メニューをクリックして**すべて保存**です。  
  
12. SQL Server Management Studio を起動します。 をクリックして**開始**、 をクリックして**すべてのプログラム**をクリックして**Microsoft SQL Server 2008 R2**または**Microsoft SQL Server 2008 SP1**をクリックして**SQL Server Management Studio**です。  
  
13. **サーバーへの接続** ダイアログ ボックスから、**サーバー**の種類のドロップダウン リスト、選択**Integration Services**です。  
  
14. サーバー名をクリックして、サーバーへの接続に資格情報を指定**OK**です。  
  
15. **オブジェクト エクスプ ローラー**、展開**Integration Services**、展開**格納されたパッケージ**、クリックして**MSDB**です。  
  
16. **オブジェクト エクスプ ローラーの詳細**タブ、以前に更新したパッケージを右クリックし、をクリックして**パッケージのインポート**です。  
  
17. **パッケージのインポート** ダイアログ ボックスから、**パッケージの場所**ドロップダウン リストで、**ファイル システム**です。  
  
18. **パッケージ パス**、保存したプロジェクトに移動し、.dtsx ファイルをインポートして、をクリックするパッケージを選択**開く**です。  
  
19. パッケージ名 ボックスに自動的に入力のボックス内をクリックします。  
  
    > [!NOTE]  
    >  手順 16 ~ 19 を更新するすべてのパッケージを繰り返します。  
  
20. をクリックして **OK**, 、順にクリック **はい** を上書きします。  
  
21. すべての BAM キューブ更新およびデータ保守 SSIS パッケージを有効にします。  
  
###  <a name="BKMK_UpdateDSOLAP"></a> サーバーとすべての OLAP キューブのデータ ソースのデータベース名を更新するには  
  
1.  すべての OLAP キューブのデータ ソースのサーバーおよびデータベース名を更新します。 これを行うには、をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 R2**または**Microsoft SQL Server 2008 SP1**をクリックし、**SQL Server Management Studio**です。  
  
2.  **サーバーへの接続** ダイアログ ボックスの**サーバーの種類**ドロップダウン リストを選択**Analysis Services**サーバー名を指定、認証方法を選択します (および資格情報を提供に必要な場合) をクリックし、**接続**です。  
  
3.  オブジェクト エクスプ ローラーで、**データベース**、展開**BAMAnalysis**、展開**データ ソース**、データ ソースをダブルクリックします。  
  
4.  **データ ソースのプロパティ** ダイアログ ボックスで、省略記号ボタンをクリックして**(...)**に対して、**接続文字列**プロパティです。  
  
5.  **接続マネージャー**  ダイアログ ボックスで、**サーバー名**ボックスを BAMPrimaryImport データベースをホストしているサーバーの名前を入力し、をクリックして**OK**をクリックして**Ok**です。  
  
6.  すべて開始[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]services です。 詳細については、トピックを参照してください。[開始方法、停止、一時停止、再開、または BizTalk Server サービスを再起動](http://go.microsoft.com/fwlink/?LinkId=154394)(http://go.microsoft.com/fwlink/?LinkId=154394)で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
7.  IIS サービスを開始します。  
  
8.  BAM 警告 Notification service を開始します。  
  
    1.  をクリックして **開始**, 、 をクリックして **実行**, 、型 **cmd**, 、 をクリックし、 **ok**します。  
  
    2.  コマンド プロンプトで、次のように入力します。  
  
         **Net start NS$ BamAlerts**  
  
9. 不完全なアクティビティ インスタンスを解決します。  不完全な BAM アクティビティ インスタンスを解決する方法については、次を参照してください。[不完全なアクティビティ インスタンスの解決方法](http://go.microsoft.com/fwlink/?LinkId=151475)(http://go.microsoft.com/fwlink/?LinkId=151475)です。  
  
## <a name="see-also"></a>参照  
 [データベースの移動](../technical-guides/moving-databases.md)