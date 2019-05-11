---
title: BAM Analysis の Database1 を移動する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d8094153-072b-427a-b3a0-7310a37cf584
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 29ab7e205777af9403157811388e9955b0f4d08f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401817"
---
# <a name="how-to-move-the-bam-analysis-database"></a>BAM 分析データベースを移動する方法
この手順を使用すると、BAM 分析データベースを別のサーバーに移動します。  エンド ツー エンドのシナリオの観点から、BAM 分析データベースの移動にも 2 つの主要な手順が含まれます。  
  
-   [BAM 分析データベースを移動します。](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyMoveDB)  
  
-   [新しい BAM 分析データベースへの参照を更新しています](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyUpdate)  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行するには、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin 固定サーバー ロールのメンバーであるアカウントを使用してログオンする必要があります。  
  
##  <a name="BKMK_AnalyMoveDB"></a> BAM 分析データベースを移動します。  
 BAM 分析データベースを移動する次の手順で、手順に従います。  
  
#### <a name="to-move-the-bam-analysis-database"></a>BAM 分析データベースを移動するには  
  
1. 停止のすべての BAM キューブ更新およびデータ保守 SSIS パッケージ、または BAM 分析データベースを復元するまで実行されないようにします。  
  
2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サービスをすべて停止します。 詳細については、トピックを参照してください。[方法を開始、停止、一時停止、再開、または BizTalk Server サービスを再起動](http://go.microsoft.com/fwlink/?LinkId=154394)(<http://go.microsoft.com/fwlink/?LinkId=154394>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
3. IIS サービスを停止します。  
  
4. BAM 警告 Notification service を停止します。  
  
   1.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
   2.  コマンド プロンプトで、次のように入力します。  
  
        **net stop NS$ BamAlerts**  
  
5. 古いサーバー上に BAM 分析データベースをバックアップします。 データベースのバックアップの手順についてに記載された手順に従います[方法。データベースのバックアップ (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (<http://go.microsoft.com/fwlink/?LinkId=156510>) で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースをバックアップする方法のオンライン ブックの「します。  
  
6. BAM 分析データベースのコピーを新しい[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューター。  
  
7. 新しいサーバーに BAM 分析データベースを復元します。 以下の手順については、データベースを復元する方法」の手順に従って[方法。データベースのバックアップ (SQL Server Management Studio) 復元](http://go.microsoft.com/fwlink/?LinkId=156511)(<http://go.microsoft.com/fwlink/?LinkId=156511>) で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースを復元する方法のオンライン ブックの「します。  
  
##  <a name="BKMK_AnalyUpdate"></a> 新しい BAM 分析データベースへの参照を更新しています  
 データベースを移動した後は、新しい BAM 分析データベースへのすべての参照を更新する必要があります。 次の参照を更新する必要があります。  
  
-   新しいデータベースとサーバーの名前で、BAM 構成を更新します。 参照してください[BAM 構成を更新する](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyUpdateBAMConfig)します。  
  
-   すべての BAM analysis の SSIS パッケージで新しいサーバーおよびデータベース名を更新します。 参照してください[サーバーとすべての BAM SSIS パッケージ内のデータベース名を更新する](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyUpdateSSIS)します。  
  
###  <a name="BKMK_AnalyUpdateBAMConfig"></a> BAM 構成を更新するには  
  
1. BAM を復元するときに使用する .xml ファイルのコピーを用意します。  
  
   1. をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
   2. BizTalk Server を実行するコンピューター上には、次のフォルダーを参照してください。  
  
      - 場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 ビット バージョンの Windows Server にインストールされます。  
  
         **%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**  
  
      - 場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 ビット バージョンの Windows Server にインストールされます。  
  
         **%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**  
  
   3. コマンド プロンプトで、次のように入力します。  
  
       **Bm.exe get-config –filename:BAMConfiguration.xml -server:\<servername\> -database:\<database\>**  
  
      > [!NOTE]
      >  このコマンドを実行するときに、実際の構成情報の取得元のサーバーの名前に置き換えてください\<servername\>の構成情報の取得元のデータベースの実際の名前に置き換えます。\<データベース\>します。 詳細については、BAM 管理 (BM) ユーティリティを使用して、次を参照してください。[インフラストラクチャ管理コマンド](http://go.microsoft.com/fwlink/?LinkId=156516)(<http://go.microsoft.com/fwlink/?LinkId=156516>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
2. BAMConfiguration.xml ファイルを編集し、変更、 **ServerName**で、`<DeploymentUnit Name="AnalysisDatabase">`セクションを新しいサーバー名。  
  
3. BAMConfiguration.xml ファイルを保存して閉じます。  
  
4. をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
5. BizTalk Server を実行するコンピューター上には、次のフォルダーを参照してください。  
  
   - 場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 ビット バージョンの Windows Server にインストールされます。  
  
      **%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**  
  
   - 場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 ビット バージョンの Windows Server にインストールされます。  
  
      **%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**  
  
6. コマンド プロンプトで、次のように入力します。  
  
    **bm.exe update-config -FileName:BAMConfiguration.xml**  
  
###  <a name="BKMK_AnalyUpdateSSIS"></a> サーバーとすべての BAM SSIS パッケージ内のデータベース名を更新するには  
  
1. すべての BAM 分析 SSIS パッケージ「bam_an _」が付いてでサーバーとデータベースの名前を更新します。 これを行うには、次のようにクリックします**開始**、 をクリック**すべてのプログラム**、 をクリック**Microsoft SQL Server 2008 R2**または**Microsoft SQL Server 2008 SP1**、順にクリックします。**SQL Server Business Intelligence Development Studio**します。  
  
2. SQL Server Business Intelligence Development Studio で、プロジェクトを新規作成します。 をクリックして**ファイル**、 をクリックして**新規**、クリックして**プロジェクト**です。  
  
3. **新しいプロジェクト**] ダイアログ ボックスで、**プロジェクトの種類**ボックスで、[**ビジネス インテリジェンス プロジェクト**します。 右側のウィンドウで、**テンプレート**ボックスで、 **Integration Services プロジェクト**、順にクリックします**OK**。  
  
4. **Integration Services プロジェクト** ダイアログ ボックスで、ソリューション エクスプ ローラーで右クリックして**SSIS パッケージ**、順にクリックします**既存パッケージの追加**します。  
  
5. **既存パッケージのコピーの追加** ダイアログ ボックスで、 **Server**ドロップダウン リスト ボックスで bam_an _ のパッケージを格納しているサーバーを選択します。  
  
6. **パッケージ パス**、省略記号ボタンをクリックします。  
  
7. **SSIS パッケージ** ダイアログ ボックスで、更新、 をクリックするパッケージを選択**ok**、順にクリックします**OK**します。  
  
    これで、パッケージがソリューション エクスプローラにリストされました。  
  
8. ソリューション エクスプ ローラーで、前の手順で追加したパッケージをダブルクリックします。 **接続マネージャー** (画面の下半分に利用可能) タブで、データ ソース数 2 (BAMArchive データベース) をダブルクリックします。  
  
9. **接続マネージャー**  ダイアログ ボックスで、**サーバー名**ボックスに、サーバーの名前を入力し、 をクリックし、 **OK**します。  
  
    > [!NOTE]  
    >  これは、データ ソースの番号 3 (MSDB データベース) を繰り返します。  
  
10. **接続マネージャー**  タブで、データ ソース番号 4 (BAMAnalysis データベース) をダブルクリックします。 **Analysis Services 接続マネージャーの追加**ダイアログ ボックスで、をクリックして**編集**します。  
  
11. **接続マネージャー**  ダイアログ ボックスで、**サーバー名**ボックスをサーバーの名前を入力し、をクリックして**ok**、順にクリックします**OK**します。  
  
12. をクリックして、**パッケージ エクスプ ローラー**  タブで、ダブルクリックして、**変数**フォルダー、しの値を更新、 **AnalysisDatabase**、 **AnalysisServer**、 **PrimaryImportDatabase**、 **PrimaryImportServer**、 **StarSchemaDatabase**、および**StarSchemaServer**変数。 新しいサーバーやデータベースを指定する値を更新する必要があります。  
  
    > [!NOTE]  
    >  すべてのパッケージを更新するには、手順 4 ~ 12 を繰り返します。  
  
13. クリックしてから**ファイル** メニューをクリック**すべて保存**します。  
  
14. SQL Server Management Studio を起動します。 クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 R2**または**Microsoft SQL Server 2008 SP1**順にクリックします**SQL Server Management Studio**します。  
  
15. **サーバーへの接続** ダイアログ ボックスから、**サーバー**型のドロップダウン リスト、選択**Integration Services**。  
  
16. サーバー名とサーバー をクリックして接続する資格情報を指定**OK**します。  
  
17. **オブジェクト エクスプ ローラー**、展開**Integration Services**、展開**格納されたパッケージ**、 をクリックし、 **MSDB**します。  
  
18. **オブジェクト エクスプ ローラーの詳細** タブで、先ほど更新したパッケージを右クリックし、をクリックし、**パッケージのインポート**します。  
  
19. **パッケージのインポート** ダイアログ ボックスから、**パッケージの場所**ドロップダウン リストで、**ファイル システム**します。  
  
20. **パッケージ パス**で、保存したプロジェクトに移動し、.dtsx ファイルをクリックして、インポートするパッケージを選択**オープン**します。  
  
21. 自動的に、ボックスに入力して [パッケージ名] ボックス内をクリックします。  
  
    > [!NOTE]  
    >  すべてのパッケージを更新するには、手順 18 ~ 21 を繰り返します。  
  
22. をクリックして **[ok]**、順にクリック**はい**を上書きします。  
  
23. すべて開始[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サービス。 詳細については、トピックを参照してください。[方法を開始、停止、一時停止、再開、または BizTalk Server サービスを再起動](http://go.microsoft.com/fwlink/?LinkId=154394)(<http://go.microsoft.com/fwlink/?LinkId=154394>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
24. IIS サービスを開始します。  
  
25. BAM 警告 Notification service を開始します。  
  
    1.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
    2.  コマンド プロンプトで、次のように入力します。  
  
         **Net start NS$ BamAlerts**  
  
26. すべての BAM キューブ更新およびデータ保守 SSIS パッケージを有効にします。  
  
## <a name="see-also"></a>参照  
 [データベースの移動](../technical-guides/moving-databases.md)