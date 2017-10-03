---
title: "BAM スター スキーマ Database2 を移動する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6832ac2-c8c5-4515-883e-26d125d6ace0
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00567514d3a3ce197065ffdfbf499ebba46c6b06
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-move-the-bam-star-schema-database"></a>BAM スター スキーマ データベースを移動する方法
ここでは、BAM スター スキーマ データベースを他のサーバーに移動する手順について説明します。  エンド ツー エンドのシナリオの観点から、BAM スター スキーマ データベースの移動にも 2 つの主要な手順が含まれます。  
  
-   [BAM スター スキーマ データベースを移動します。](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarMoveDB)  
  
-   [新しい BAM スター スキーマ データベースへの参照を更新](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdate)  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行するには、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin 固定サーバー ロールのメンバーであるアカウントを使用してログオンする必要があります。  
  
##  <a name="BKMK_StarMoveDB"></a>BAM スター スキーマ データベースを移動します。  
 BAM スター スキーマ データベースを移動する次の手順で、手順を実行します。  
  
#### <a name="to-move-the-bam-star-schema-database"></a>BAM スター スキーマ データベースを移動するには  
  
1.  BAM キューブ更新/データ保守 SSIS パッケージをすべて停止するか、BAM スター スキーマ データベースの復元が完了するまで実行を回避します。  
  
2.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サービスをすべて停止します。 詳細については、トピックを参照してください。[開始方法、停止、一時停止、再開、または BizTalk Server サービスを再起動](http://go.microsoft.com/fwlink/?LinkId=154394)(http://go.microsoft.com/fwlink/?LinkId=154394) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
3.  IIS サービスを停止します。  
  
4.  BAM 警告 Notification service を停止します。  
  
    1.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
    2.  コマンド プロンプトで、次のように入力します。  
  
         **Net stop NS$ BamAlerts**  
  
5.  古いサーバーで、BAM スター スキーマ データベースをバックアップします。 データベースをバックアップする方法の手順についてに記載された手順に従います[する方法:、データベースのバックアップ (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (http://go.microsoft.com/fwlink/?LinkId=156510) で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]オンライン ブック、データベースをバックアップする方法です。  
  
6.  新しい BAM スター スキーマ データベースをコピー[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューター。  
  
7.  新しいサーバーで、BAM スター スキーマ データベースを復元します。 データベースを復元する方法について以下に記載された手順[する方法: データベースのバックアップ (SQL Server Management Studio) を復元](http://go.microsoft.com/fwlink/?LinkId=156511)(http://go.microsoft.com/fwlink/?LinkId=156511) で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースを復元する方法のオンライン ブック。  
  
##  <a name="BKMK_StarUpdate"></a>新しい BAM スター スキーマ データベースへの参照を更新  
 データベースを移動した後は、新しい BAM スター スキーマ データベースに対するすべての参照を更新する必要があります。 次の参照を更新する必要があります。  
  
-   新しいデータベースとサーバーの名前で、BAM 構成を更新します。 参照してください[BAM 構成を更新する](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdateBAMConfig)です。  
  
-   すべての BAM analysis の SSIS パッケージで新しいサーバーおよびデータベース名を更新します。 参照してください[サーバーとすべての BAM SSIS パッケージ内のデータベース名を更新する](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdateRef)です。  
  
-   サーバーとデータベースの新しい名前のデータ ソースに、OLAP 以外のすべてのキューブを更新します。 参照してください[サーバーと、OLAP 以外のすべてのキューブのデータ ソースのデータベース名を更新する](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_UpdateDS_non_OLAP)です。  
  
###  <a name="BKMK_StarUpdateBAMConfig"></a>BAM 構成を更新するには  
  
1.  BAM を復元するときに使用する .xml ファイルのコピーを用意します。  
  
    1.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
    2.  [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] が動作しているコンピューターで、次のフォルダーを参照します。  
  
        -   場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が 64 ビット バージョンの Windows Server にインストールされています。  
  
             **%Programfiles (x86) %\Microsoft BizTalk Server 2010 \tracking**  
  
        -   場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が 32 ビット バージョンの Windows Server にインストールされています。  
  
             **%ProgramFiles%\Microsoft BizTalk Server 2010 \tracking**  
  
    3.  コマンド プロンプトで、次のように入力します。  
  
         **Bm.exe get-config –filename:BAMConfiguration.xml-サーバー:\<サーバー名 >-データベース:\<データベース >**  
  
        > [!NOTE]  
        >  このコマンドを実行するときに、サーバーの構成情報の取得元の実際の名前に置き換える\<servername >の構成情報の取得元のデータベースの実際の名前を使用して\<データベース >。 詳細については、BAM 管理 (BM) ユーティリティを使用して、次を参照してください。[インフラストラクチャ管理コマンド](http://go.microsoft.com/fwlink/?LinkId=156516)(http://go.microsoft.com/fwlink/?LinkId=156516) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
2.  BAMConfiguration.xml ファイルを編集し、変更、 **ServerName**で、`<DeploymentUnit Name="StarSchemaDatabase">`セクションに新しいサーバーの名前。  
  
3.  BAMConfiguration.xml ファイルを保存して閉じます。  
  
4.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
5.  [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] が動作しているコンピューターで、次のフォルダーを参照します。  
  
    -   場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が 64 ビット バージョンの Windows Server にインストールされています。  
  
         **%Programfiles (x86) %\Microsoft BizTalk Server 2010 \tracking**  
  
    -   場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が 32 ビット バージョンの Windows Server にインストールされています。  
  
         **%ProgramFiles%\Microsoft BizTalk Server 2010 \tracking**  
  
6.  コマンド プロンプトで、次のように入力します。  
  
     **bm.exe 更新-config-FileName:BAMConfiguration.xml**  
  
###  <a name="BKMK_StarUpdateRef"></a>サーバーとすべての BAM SSIS パッケージ内のデータベース名を更新するには  
  
1.  すべての BAM 分析 SSIS パッケージ「bam_an _」で始まるサーバーおよびデータベース名を更新します。 これを行うには、をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 R2**または**Microsoft SQL Server 2008 SP1**をクリックし、**SQL Server Business Intelligence Development Studio**です。  
  
2.  SQL Server Business Intelligence Development Studio で、プロジェクトを新規作成します。 をクリックして**ファイル**、 をクリックして**新規**、クリックして**プロジェクト**です。  
  
3.  **新しいプロジェクト** ダイアログ ボックスで、**プロジェクトの種類**ボックスで、クリックして**ビジネス インテリジェンス プロジェクト**です。 右側のウィンドウで、**テンプレート**ボックスで、をクリックして**Integration Services プロジェクト**、クリックして**[ok]**です。  
  
4.  **Integration Services プロジェクト**ダイアログ ボックスで、ソリューション エクスプ ローラーで右クリックし**SSIS パッケージ**、クリックして**既存のパッケージの追加**です。  
  
5.  **既存のパッケージのコピーを追加** ダイアログ ボックスで、**サーバー**ドロップダウン リスト ボックスで、bam_an _ のパッケージを含むサーバーを選択します。  
  
6.  **パッケージ パス**、省略記号ボタンをクリックします。  
  
7.  **SSIS パッケージ** ダイアログ ボックスで、更新するには、をクリックするパッケージを選択**ok**、順にクリック**OK**です。  
  
     これで、パッケージがソリューション エクスプローラにリストされました。  
  
8.  ソリューション エクスプ ローラーで、前の手順で追加したパッケージをダブルクリックします。 **接続マネージャー** (画面の下半分に使用可能) タブで、データ ソース番号 2 (BAMStarSchema データベース) をダブルクリックします。  
  
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
  
23. すべての BAM キューブ更新およびデータ保守 SSIS パッケージを有効にします。  
  
###  <a name="BKMK_UpdateDS_non_OLAP"></a>サーバーと、OLAP 以外のすべてのキューブのデータ ソースのデータベース名を更新するには  
  
1.  すべての OLAP キューブのデータ ソースにサーバーおよびデータベース名を更新します。 これを行うには、をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 R2**または**Microsoft SQL Server 2008 SP1**をクリックし、**SQL Server Management Studio**です。  
  
2.  **サーバーへの接続** ダイアログ ボックスの**サーバーの種類**ドロップダウン リストを選択**Analysis Services**サーバー名を指定、認証方法を選択します (および資格情報を提供に必要な場合) をクリックし、**接続**です。  
  
3.  オブジェクト エクスプ ローラーで、**データベース**、展開**BAMAnalysis**、展開**データ ソース**、データ ソースをダブルクリックします。  
  
4.  **データ ソースのプロパティ** ダイアログ ボックスで、省略記号ボタンをクリックして**(...)**に対して、**接続文字列**プロパティです。  
  
5.  **接続マネージャー**  ダイアログ ボックスで、**サーバー名**ボックスを BAMStarSchema データベースをホストしているサーバーの名前を入力し、をクリックして**OK**をクリックして**OK**です。  
  
6.  すべて開始[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]services です。 詳細については、トピックを参照してください。[開始方法、停止、一時停止、再開、または BizTalk Server サービスを再起動](http://go.microsoft.com/fwlink/?LinkId=154394)(http://go.microsoft.com/fwlink/?LinkId=154394) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
7.  IIS サービスを開始します。  
  
8.  BAM 警告 Notification service を開始します。  
  
    1.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
    2.  コマンド プロンプトで、次のように入力します。  
  
         **Net start NS$ BamAlerts**  
  
9. 不完全なアクティビティ インスタンスを解決します。  不完全な BAM アクティビティ インスタンスを解決する方法については、次を参照してください。[不完全なアクティビティ インスタンスの解決方法](http://go.microsoft.com/fwlink/?LinkId=151475)(http://go.microsoft.com/fwlink/?LinkId=151475)。  
  
> [!TIP]  
>  お勧めとしても、BAMStarSchema データベースをホストするサーバーに bam_an _ * SSIS パッケージを移動する必要があります。  
  
## <a name="see-also"></a>参照  
 [データベースの移動](../technical-guides/moving-databases.md)