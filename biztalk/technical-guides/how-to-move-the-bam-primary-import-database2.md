---
title: BAM プライマリ インポートの Database2 を移動する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bc4f2656-2faa-4503-9551-05e1b6eceb1a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe36c4a8b9aa6d081ebde854e6a4c57f9492df67
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50753210"
---
# <a name="how-to-move-the-bam-primary-import-database"></a>BAM プライマリ インポート データベースを移動する方法
ここでは、BAM プライマリ インポート データベースを他のサーバーに移動する手順について説明します。 エンド ツー エンドのシナリオの観点から BAM プライマリ インポート データベースの移動にも 2 つの主要な手順が含まれます。  
  
-   [BAM プライマリ インポート データベースを移動します。](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_MovingBAMPI)  
  
-   [新しい BAM プライマリ インポート データベースへの参照を更新しています](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_BAMPIRef)  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行するには、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin 固定サーバー ロールのメンバーであるアカウントを使用してログオンする必要があります。  
  
##  <a name="BKMK_MovingBAMPI"></a> BAM プライマリ インポート データベースを移動します。  
 BAM プライマリ インポート データベースを移動する次の手順で、手順に従います。  
  
#### <a name="to-move-the-bam-primary-import-database"></a>BAM プライマリ インポート データベースを移動するには  
  
1. すべての BAM キューブ更新およびデータ保守 SSIS パッケージを停止するか、BAM プライマリ インポート データベースを復元するまで実行を防ぐ。  
  
2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サービスをすべて停止します。 詳細については、トピックを参照してください。[方法を開始、停止、一時停止、再開、または BizTalk Server サービスを再起動](http://go.microsoft.com/fwlink/?LinkId=154394)(<http://go.microsoft.com/fwlink/?LinkId=154394>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
3. IIS サービスを停止します。  
  
4. BAM 警告 Notification service を停止します。  
  
   1.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
   2.  コマンド プロンプトで、次のように入力します。  
  
        **net stop NS$ BamAlerts**  
  
5. BAM プライマリをバックアップするには、古いサーバー上のデータベースをインポートします。 データベースをバックアップする方法については次の手順については、データベースのバックアップの手順については、[方法:、データベースのバックアップ (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (<http://go.microsoft.com/fwlink/?LinkId=156510>) で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]オンライン ブックの「します。  
  
6. BAM プライマリ インポート データベースのコピーを新しい[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューター。  
  
7. 新しいサーバーで、BAM プライマリ インポート データベースを復元します。 データベースを復元する方法の指示に従って、データベースを復元する手順についての[方法: データベースのバックアップ (SQL Server Management Studio) 復元](http://go.microsoft.com/fwlink/?LinkId=156511)(<http://go.microsoft.com/fwlink/?LinkId=156511>) で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]オンライン ブックの「します。  
  
   > [!NOTE]  
   >  BAM プライマリ インポート データベースをバックアップから復元する場合は、BAM プライマリよりも古いバックアップを使用して BAM アーカイブ、BAM スター スキーマ、および BAM 分析データベースも復元する必要があります。  
  
##  <a name="BKMK_BAMPIRef"></a> 新しい BAM プライマリ インポート データベースへの参照を更新しています  
 データベースを移動した後は、新しい BAM プライマリ インポート データベースへのすべての参照を更新する必要があります。 次の参照を更新する必要があります。  
  
-   新しいサーバー名では、すべての BizTalk データベースを更新します。 UpdateDatabase.vbs のスクリプトを使用して行うことができます。 参照してください[BizTalk データベースを新しいサーバー名で更新する](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdateDB)します。  
  
-   BAM ポータルの Web.config ファイルを更新します。 参照してください[BAM ポータルの Web.config ファイルを更新する](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_Config)します。  
  
-   すべての BAM ライブ データの Microsoft Excel ファイルで BAM プライマリ インポート データベースへの参照を更新します。 参照してください[BAM ライブ データの Microsoft Excel ファイル内の参照を更新する](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdateExcel)します。  
  
-   すべての BAM analysis の SSIS パッケージで新しいサーバーおよびデータベース名を更新します。 参照してください[サーバーとすべての BAM SSIS パッケージ内のデータベース名を更新する](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdatePckg)します。  
  
-   サーバーとデータベースの新しい名前のデータ ソースのすべての OLAP キューブを更新します。 参照してください[サーバーおよびすべての OLAP キューブのデータ ソース内のデータベース名を更新する](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdateDSOLAP)します。  
  
###  <a name="BKMK_UpdateDB"></a> BizTalk データベースを新しいサーバー名で更新するには  
  
1. BizTalk Server を実行するコンピューター上には、次のフォルダーを参照してください。  
  
   - 場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 ビット バージョンの Windows Server にインストールされます。  
  
      **%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\bins32\Schema\Restore**  
  
   - 場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 ビット バージョンの Windows Server にインストールされます。  
  
      **%ProgramFiles%\Microsoft BizTalk Server 2010\Schema\Restore**  
  
2. 右クリック**SampleUpdateInfo.xml**、 をクリックし、**編集**します。  
  
3. BizTalkMgmtDb、OldPrimaryImportDatabase、PrimaryImportDatabase、ArchivingDatabase、AnalysisDatabase、StarSchemaDatabase、および Alert を除いて、すべてのデータベース セクションをコメント アウトします。  
  
4. `OldPrimaryImportDatabase` 、ファイルのセクションの`ServerName`プロパティ、置き換える**SourceServer**データベースが存在する既存のサーバーの名前に置き換えます。  
  
5. `PrimaryImportDatabase` 、ファイルのセクションの`ServerName`プロパティ、置き換える**DestinationServer**を BAM プライマリ インポート データベースを移動するサーバーの名前  
  
6. BizTalkMgmtDb、ArchivingDatabase、AnalysisDatabase、StarSchemaDatabase、および警告のセクションでは、設定"SourceServer"と"Destination Server"既存のサーバーの名前にこれらのデータベースが存在します。  
  
   > [!IMPORTANT]
   >  送信元システムおよび送信先システムの名前は、引用符で囲んでください。  
   > 
   > [!NOTE]
   >  いずれかの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースの名前を変更した場合、それに応じてデータベース名も更新する必要があります。  
  
7. ファイルの編集を終了したら、このファイルを保存して閉じます。  
  
8. をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
9. コマンド プロンプトで、次のディレクトリに移動します  
  
   - 場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 ビット バージョンの Windows Server にインストールされます。  
  
      **%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Schema\Restore**  
  
   - 場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 ビット バージョンの Windows Server にインストールされます。  
  
      **%ProgramFiles%\Microsoft BizTalk Server 2010\Schema\Restore**  
  
10. コマンド プロンプトで、次のように入力します。  
  
     **cscript UpdateDatabase.vbs SampleUpdateInfo.xml**  
  
###  <a name="BKMK_Config"></a> BAM ポータルの Web.config ファイルを更新するには  
  
1.  BizTalk Server を実行するコンピューター上で Web.config ファイルを更新 **\<ドライブ\>: BizTalk Server 2010\BAMPortal\BAMManagementService\Web.Config \Program Files\Microsoft** します。Web.config の次のセクションでサーバーとデータベースの名前を更新します。  
  
    ```  
    <appSettings>  
      <add key="BamServer" value="<ServerName>" />  
      <add key="BamDatabase" value="<DatabaseName>" />  
    </appSettings>  
    ```  
  
2.  BizTalk Server を実行するコンピューター上で Web.config ファイルを更新 **\<ドライブ\>: BizTalk Server 2010\BAMPortal\BAMQueryService\Web.Config \Program Files\Microsoft** します。Web.config の次のセクションでサーバーとデータベースの名前を更新します。  
  
    ```  
    <appSettings>  
      <add key="BamServer" value="<ServerName>" />  
      <add key="BamDatabase" value="<DatabaseName>" />  
      <add key="MaxResultRows" value="2000" />  
    </appSettings>  
    ```  
  
3.  保存して、ファイルを閉じます。  
  
###  <a name="BKMK_UpdateExcel"></a> BAM ライブ データの Microsoft Excel ファイル内の参照を更新するには  
  
1. Excel ライブ データ ファイルを開きます。 ファイル名の末尾は _LiveData.xls となっています。  
  
2. **BAM**  メニューのをクリックして**BAM データベースの接続**します。  
  
3. **BAM データベースの選択** ダイアログ ボックスに、入力、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューターおよび BAMPrimaryImport データベース、およびクリックして **[ok]**。  
  
4. **ファイル** メニューのをクリックして**閉じて Microsoft Excel へ戻る**します。  
  
5. **[ファイル]** メニューの **[保存]** をクリックします。  
  
###  <a name="BKMK_UpdatePckg"></a> サーバーとすべての BAM SSIS パッケージ内のデータベース名を更新するには  
  
1.  すべての BAM 分析 SSIS パッケージには「bam_an _」または「bam_dm _」プレフィックスでサーバーとデータベースの名前を更新します。 これを行うには、次のようにクリックします**開始**、 をクリック**すべてのプログラム**、 をクリック**Microsoft SQL Server 2008 R2**または**Microsoft SQL Server 2008 SP1**、順にクリックします。**SQL Server Business Intelligence Development Studio**します。  
  
2.  SQL Server Business Intelligence Development Studio で、プロジェクトを新規作成します。 をクリックして**ファイル**、 をクリックして**新規**、クリックして**プロジェクト**です。  
  
3.  **新しいプロジェクト**] ダイアログ ボックスで、**プロジェクトの種類**ボックスで、[**ビジネス インテリジェンス プロジェクト**します。 右側のウィンドウでの**テンプレート**ボックスで、 **Integration Services プロジェクト**、順にクリックします**OK**。  
  
4.  **Integration Services プロジェクト** ダイアログ ボックスで、ソリューション エクスプ ローラーで右クリックして**SSIS パッケージ**、順にクリックします**既存パッケージの追加**します。  
  
5.  **既存パッケージのコピーの追加** ダイアログ ボックスで、 **Server**ドロップダウン リスト ボックスで、bam_an _ を含むサーバーを選択します。\*と bam_dm _\*パッケージ。  
  
6.  **パッケージ パス**、省略記号ボタンをクリックします。  
  
7.  **SSIS パッケージ** ダイアログ ボックスで、更新、 をクリックするパッケージを選択**ok**、順にクリックします**OK**します。  
  
     これで、パッケージがソリューション エクスプローラにリストされました。  
  
8.  ソリューション エクスプ ローラーで、前の手順で追加したパッケージをダブルクリックします。 **接続マネージャー** (画面の下半分に利用可能) タブで、データ ソース番号 1 (BAMPrimaryImport データベース) をダブルクリックします。  
  
9. **接続マネージャー**  ダイアログ ボックスで、**サーバー名**ボックスに、サーバーの名前を入力し、 をクリックし、 **OK**します。  
  
10. をクリックして、**パッケージ エクスプ ローラー**  タブで、ダブルクリックして、**変数**フォルダー、しの値を更新、 **PrimaryImportDatabase**と**PrimaryImportServer**変数。 新しいサーバーやデータベースを指定する値を更新する必要があります。  
  
    > [!NOTE]  
    >  すべてのパッケージを更新するには、手順 4 ~ 10 を繰り返します。  
  
11. クリックしてから**ファイル** メニューをクリック**すべて保存**します。  
  
12. SQL Server Management Studio を起動します。 クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 R2**または**Microsoft SQL Server 2008 SP1**順にクリックします**SQL Server Management Studio**します。  
  
13. **サーバーへの接続** ダイアログ ボックスから、**サーバー**型のドロップダウン リスト、選択**Integration Services**。  
  
14. サーバー名とサーバー をクリックして接続する資格情報を指定**OK**します。  
  
15. **オブジェクト エクスプ ローラー**、展開**Integration Services**、展開**格納されたパッケージ**、 をクリックし、 **MSDB**します。  
  
16. **オブジェクト エクスプ ローラーの詳細** タブで、先ほど更新したパッケージを右クリックし、をクリックし、**パッケージのインポート**します。  
  
17. **パッケージのインポート** ダイアログ ボックスから、**パッケージの場所**ドロップダウン リストで、**ファイル システム**します。  
  
18. **パッケージ パス**で、保存したプロジェクトに移動し、.dtsx ファイルをクリックして、インポートするパッケージを選択**オープン**します。  
  
19. 自動的に、ボックスに入力して [パッケージ名] ボックス内をクリックします。  
  
    > [!NOTE]  
    >  すべてのパッケージを更新するには、手順 16 ~ 19 を繰り返します。  
  
20. をクリックして **[ok]**、順にクリック**はい**を上書きします。  
  
21. すべての BAM キューブ更新およびデータ保守 SSIS パッケージを有効にします。  
  
###  <a name="BKMK_UpdateDSOLAP"></a> サーバーおよびすべての OLAP キューブのデータ ソース内のデータベース名を更新するには  
  
1. すべての OLAP キューブのデータ ソースのサーバーおよびデータベース名を更新します。 これを行うには、次のようにクリックします**開始**、 をクリック**すべてのプログラム**、 をクリック**Microsoft SQL Server 2008 R2**または**Microsoft SQL Server 2008 SP1**、順にクリックします。**SQL Server Management Studio**します。  
  
2. **サーバーへの接続** ダイアログ ボックスの**サーバーの種類**ドロップダウン リストを**Analysis Services**認証方法を選択して、サーバー名を指定 (および資格情報の入力が必要な場合)、をクリックし、 **Connect**します。  
  
3. オブジェクト エクスプ ローラーで、**データベース**、展開**BAMAnalysis**、展開**データソース**、データ ソースをダブルクリックします。  
  
4. **データ ソースのプロパティ** ダイアログ ボックスで、省略記号ボタンをクリックします **(...)。** に対して、**接続文字列**プロパティ。  
  
5. **接続マネージャー**  ダイアログ ボックスで、**サーバー名**ボックスを BAMPrimaryImport データベースをホストするサーバーの名前を入力し、をクリックして**OK**順にクリックします**Ok**します。  
  
6. すべて開始[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サービス。 詳細については、トピックを参照してください。[方法を開始、停止、一時停止、再開、または BizTalk Server サービスを再起動](http://go.microsoft.com/fwlink/?LinkId=154394)(<http://go.microsoft.com/fwlink/?LinkId=154394>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
7. IIS サービスを開始します。  
  
8. BAM 警告 Notification service を開始します。  
  
   1.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
   2.  コマンド プロンプトで、次のように入力します。  
  
        **Net start NS$ BamAlerts**  
  
9. すべての不完全なトレース インスタンスを解決します。  不完全な BAM アクティビティ インスタンスの解決方法の詳細については、次を参照してください。[不完全なアクティビティ インスタンスの解決方法](http://go.microsoft.com/fwlink/?LinkId=151475)(http://go.microsoft.com/fwlink/?LinkId=151475)します。  
  
## <a name="see-also"></a>参照  
 [データベースの移動](../technical-guides/moving-databases.md)