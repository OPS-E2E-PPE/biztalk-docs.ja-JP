---
title: "BAM 分析データベース 1 に移動する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d8094153-072b-427a-b3a0-7310a37cf584
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b21168c1955db8bbbae3e29019632807231b40a1
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-move-the-bam-analysis-database"></a>BAM 分析データベースを移動する方法
ここでは、BAM 分析データベースを他のサーバーに移動する手順について説明します。  エンド ツー エンドのシナリオの観点から、BAM 分析データベースの移動にも 2 つの主要な手順が含まれます。  
  
-   [BAM 分析データベースを移動します。](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyMoveDB)  
  
-   [新しい BAM 分析データベースへの参照を更新](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyUpdate)  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行するには、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin 固定サーバー ロールのメンバーであるアカウントを使用してログオンする必要があります。  
  
##  <a name="BKMK_AnalyMoveDB"></a>BAM 分析データベースを移動します。  
 BAM 分析データベースを移動する次の手順で、手順を実行します。  
  
#### <a name="to-move-the-bam-analysis-database"></a>BAM 分析データベースを移動するには  
  
1.  すべての BAM キューブ更新およびデータ保守 SSIS パッケージを停止するか、BAM 分析データベースの復元が完了するまで実行されないように措置を講じます。  
  
2.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サービスをすべて停止します。 詳細については、トピックを参照してください。[開始方法、停止、一時停止、再開、または BizTalk Server サービスを再起動](http://go.microsoft.com/fwlink/?LinkId=154394)(http://go.microsoft.com/fwlink/?LinkId=154394) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
3.  IIS サービスを停止します。  
  
4.  BAM 警告 Notification service を停止します。  
  
    1.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
    2.  コマンド プロンプトで、次のように入力します。  
  
         **Net stop NS$ BamAlerts**  
  
5.  古いサーバーで、BAM 分析データベースをバックアップします。 データベースをバックアップする方法の手順についてに記載された手順に従います[する方法:、データベースのバックアップ (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (http://go.microsoft.com/fwlink/?LinkId=156510) で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]オンライン ブック、データベースをバックアップする方法です。  
  
6.  新しい BAM 分析データベースをコピー[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューター。  
  
7.  新しいサーバーで、BAM 分析データベースを復元します。 データベースを復元する方法について以下に記載された手順[する方法: データベースのバックアップ (SQL Server Management Studio) を復元](http://go.microsoft.com/fwlink/?LinkId=156511)(http://go.microsoft.com/fwlink/?LinkId=156511) で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースを復元する方法のオンライン ブック。  
  
##  <a name="BKMK_AnalyUpdate"></a>新しい BAM 分析データベースへの参照を更新  
 データベースを移動した後は、新しい BAM 分析データベースへすべての参照を更新する必要があります。 次の参照を更新する必要があります。  
  
-   新しいデータベースとサーバーの名前で、BAM 構成を更新します。 参照してください[BAM 構成を更新する](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyUpdateBAMConfig)です。  
  
-   すべての BAM analysis の SSIS パッケージで新しいサーバーおよびデータベース名を更新します。 参照してください[サーバーとすべての BAM SSIS パッケージ内のデータベース名を更新する](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyUpdateSSIS)です。  
  
###  <a name="BKMK_AnalyUpdateBAMConfig"></a>BAM 構成を更新するには  
  
1.  BAM を復元するときに使用する .xml ファイルのコピーを用意します。  
  
    1.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
    2.  BizTalk Server を実行するコンピューター上には、次のフォルダーを参照してください。  
  
        -   場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が 64 ビット バージョンの Windows Server にインストールされています。  
  
             **%Programfiles (x86) %\Microsoft BizTalk Server 2010 \tracking**  
  
        -   場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が 32 ビット バージョンの Windows Server にインストールされています。  
  
             **%ProgramFiles%\Microsoft BizTalk Server 2010 \tracking**  
  
    3.  コマンド プロンプトで、次のように入力します。  
  
         **Bm.exe get-config –filename:BAMConfiguration.xml-サーバー:\<servername\> -データベース:\<データベース\>**  
  
        > [!NOTE]  
        >  このコマンドを実行するときに、サーバーの構成情報の取得元の実際の名前に置き換える\<servername\>の構成情報の取得元のデータベースの実際の名前を使用してください\<データベース\>です。 詳細については、BAM 管理 (BM) ユーティリティを使用して、次を参照してください。[インフラストラクチャ管理コマンド](http://go.microsoft.com/fwlink/?LinkId=156516)(http://go.microsoft.com/fwlink/?LinkId=156516) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
2.  BAMConfiguration.xml ファイルを編集し、変更、 **ServerName**で、`<DeploymentUnit Name="AnalysisDatabase">`セクションに新しいサーバーの名前。  
  
3.  BAMConfiguration.xml ファイルを保存して閉じます。  
  
4.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
5.  BizTalk Server を実行するコンピューター上には、次のフォルダーを参照してください。  
  
    -   場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が 64 ビット バージョンの Windows Server にインストールされています。  
  
         **%Programfiles (x86) %\Microsoft BizTalk Server 2010 \tracking**  
  
    -   場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が 32 ビット バージョンの Windows Server にインストールされています。  
  
         **%ProgramFiles%\Microsoft BizTalk Server 2010 \tracking**  
  
6.  コマンド プロンプトで、次のように入力します。  
  
     **bm.exe 更新-config-FileName:BAMConfiguration.xml**  
  
###  <a name="BKMK_AnalyUpdateSSIS"></a>サーバーとすべての BAM SSIS パッケージ内のデータベース名を更新するには  
  
1.  すべての BAM 分析 SSIS パッケージ「bam_an _」で始まるサーバーおよびデータベース名を更新します。 これを行うには、をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 R2**または**Microsoft SQL Server 2008 SP1**をクリックし、**SQL Server Business Intelligence Development Studio**です。  
  
2.  SQL Server Business Intelligence Development Studio で、プロジェクトを新規作成します。 をクリックして**ファイル**、 をクリックして**新規**、クリックして**プロジェクト**です。  
  
3.  **新しいプロジェクト** ダイアログ ボックスで、**プロジェクトの種類**ボックスで、クリックして**ビジネス インテリジェンス プロジェクト**です。 右側のウィンドウで、**テンプレート**ボックスで、をクリックして**Integration Services プロジェクト**、クリックして**[ok]**です。  
  
4.  **Integration Services プロジェクト**ダイアログ ボックスで、ソリューション エクスプ ローラーで右クリックし**SSIS パッケージ**、クリックして**既存のパッケージの追加**です。  
  
5.  **既存のパッケージのコピーを追加** ダイアログ ボックスで、**サーバー**ドロップダウン リスト ボックスで、bam_an _ のパッケージを含むサーバーを選択します。  
  
6.  **パッケージ パス**、省略記号ボタンをクリックします。  
  
7.  **SSIS パッケージ** ダイアログ ボックスで、更新するには、をクリックするパッケージを選択**ok**、順にクリック**OK**です。  
  
     これで、パッケージがソリューション エクスプローラにリストされました。  
  
8.  ソリューション エクスプ ローラーで、前の手順で追加したパッケージをダブルクリックします。 **接続マネージャー** (画面の下半分に使用可能) タブで、データ ソース番号 2 (BAMArchive データベース) をダブルクリックします。  
  
9. **接続マネージャー**  ダイアログ ボックスで、**サーバー名**ボックスで、サーバーの名前を入力し、をクリックして**OK**です。  
  
    > [!NOTE]  
    >  データ ソース数 3 (MSDB データベース) に、この手順を繰り返します。  
  
10. **接続マネージャー**  タブで、データ ソース番号 4 (BAMAnalysis データベース) をダブルクリックします。 **Analysis Services 接続マネージャーの追加**ダイアログ ボックスで、をクリックして**編集**です。  
  
11. **接続マネージャー**  ダイアログ ボックスで、**サーバー名**ボックスをサーバーの名前を入力し、をクリックして**ok**、順にクリック**OK**です。  
  
12. クリックして、**パッケージ エクスプ ローラー**  タブをダブルクリックして、**変数**フォルダー、しの値を更新、 **AnalysisDatabase**、 **AnalysisServer**、 **PrimaryImportDatabase**、 **PrimaryImportServer**、 **StarSchemaDatabase**、および**StarSchemaServer**変数。 新しいサーバーやデータベースを指定する値を更新する必要があります。  
  
    > [!NOTE]  
    >  手順 4 ~ 12 を更新するすべてのパッケージを繰り返します。  
  
13. クリックしてから**ファイル** メニューをクリックして**すべて保存**です。  
  
14. SQL Server Management Studio を起動します。 をクリックして**開始**、 をクリックして**すべてのプログラム**をクリックして**Microsoft SQL Server 2008 R2**または**Microsoft SQL Server 2008 SP1**をクリックして**SQL Server Management Studio**です。  
  
15. **サーバーへの接続** ダイアログ ボックスから、**サーバー**の種類のドロップダウン リスト、選択**Integration Services**です。  
  
16. サーバー名をクリックして、サーバーへの接続に資格情報を指定**OK**です。  
  
17. **オブジェクト エクスプ ローラー**、展開**Integration Services**、展開**格納されたパッケージ**、クリックして**MSDB**です。  
  
18. **オブジェクト エクスプ ローラーの詳細**タブ、以前に更新したパッケージを右クリックし、をクリックして**パッケージのインポート**です。  
  
19. **パッケージのインポート** ダイアログ ボックスから、**パッケージの場所**ドロップダウン リストで、**ファイル システム**です。  
  
20. **パッケージ パス**、保存したプロジェクトに移動し、.dtsx ファイルをインポートして、をクリックするパッケージを選択**開く**です。  
  
21. パッケージ名 ボックスに自動的に入力のボックス内をクリックします。  
  
    > [!NOTE]  
    >  手順 18 21 ~ を更新するすべてのパッケージを繰り返します。  
  
22. をクリックして**[ok]**、順にクリック**はい**を上書きします。  
  
23. すべて開始[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]services です。 詳細については、トピックを参照してください。[開始方法、停止、一時停止、再開、または BizTalk Server サービスを再起動](http://go.microsoft.com/fwlink/?LinkId=154394)(http://go.microsoft.com/fwlink/?LinkId=154394) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
24. IIS サービスを開始します。  
  
25. BAM 警告 Notification service を開始します。  
  
    1.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
    2.  コマンド プロンプトで、次のように入力します。  
  
         **Net start NS$ BamAlerts**  
  
26. すべての BAM キューブ更新およびデータ保守 SSIS パッケージを有効にします。  
  
## <a name="see-also"></a>参照  
 [データベースの移動](../technical-guides/moving-databases.md)