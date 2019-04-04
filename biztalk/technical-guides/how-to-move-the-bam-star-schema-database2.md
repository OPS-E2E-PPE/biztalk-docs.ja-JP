---
title: BAM スター スキーマの Database2 を移動する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a6832ac2-c8c5-4515-883e-26d125d6ace0
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5ad0e2b649757ee591b476f29d030b2d49b8850
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017022"
---
# <a name="how-to-move-the-bam-star-schema-database"></a>BAM スター スキーマ データベースを移動する方法
ここでは、BAM スター スキーマ データベースを他のサーバーに移動する手順について説明します。  エンド ツー エンドのシナリオの観点から、BAM スター スキーマ データベースの移動にも 2 つの主要な手順が含まれます。  
  
-   [BAM スター スキーマ データベースを移動します。](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarMoveDB)  
  
-   [新しい BAM スター スキーマ データベースへの参照を更新しています](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdate)  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行するには、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin 固定サーバー ロールのメンバーであるアカウントを使用してログオンする必要があります。  
  
##  <a name="BKMK_StarMoveDB"></a> BAM スター スキーマ データベースを移動します。  
 BAM スター スキーマ データベースを移動する次の手順で、手順に従います。  
  
#### <a name="to-move-the-bam-star-schema-database"></a>BAM スター スキーマ データベースを移動するには  
  
1. BAM キューブ更新/データ保守 SSIS パッケージをすべて停止するか、BAM スター スキーマ データベースの復元が完了するまで実行を回避します。  
  
2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サービスをすべて停止します。 詳細については、トピックを参照してください。[方法を開始、停止、一時停止、再開、または BizTalk Server サービスを再起動](http://go.microsoft.com/fwlink/?LinkId=154394)(<http://go.microsoft.com/fwlink/?LinkId=154394>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
3. IIS サービスを停止します。  
  
4. BAM 警告 Notification service を停止します。  
  
   1.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
   2.  コマンド プロンプトで、次のように入力します。  
  
        **net stop NS$ BamAlerts**  
  
5. 古いサーバーで、BAM スター スキーマ データベースをバックアップします。 データベースのバックアップの手順についてに記載された手順に従います[方法:、データベースのバックアップ (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (<http://go.microsoft.com/fwlink/?LinkId=156510>) で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースをバックアップする方法のオンライン ブックの「します。  
  
6. BAM スター スキーマ データベースのコピーを新しい[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューター。  
  
7. 新しいサーバーで、BAM スター スキーマ データベースを復元します。 以下の手順については、データベースを復元する方法」の手順に従って[方法: データベース バックアップ (SQL Server Management Studio) を復元](http://go.microsoft.com/fwlink/?LinkId=156511)(<http://go.microsoft.com/fwlink/?LinkId=156511>) で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースを復元する方法のオンライン ブックの「します。  
  
##  <a name="BKMK_StarUpdate"></a> 新しい BAM スター スキーマ データベースへの参照を更新しています  
 データベースを移動した後は、新しい BAM スター スキーマ データベースに対するすべての参照を更新する必要があります。 次の参照を更新する必要があります。  
  
-   新しいデータベースとサーバーの名前で、BAM 構成を更新します。 参照してください[BAM 構成を更新する](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdateBAMConfig)します。  
  
-   すべての BAM analysis の SSIS パッケージで新しいサーバーおよびデータベース名を更新します。 参照してください[サーバーとすべての BAM SSIS パッケージ内のデータベース名を更新する](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdateRef)します。  
  
-   サーバーとデータベースの新しい名前のデータ ソースのすべての OLAP キューブを更新します。 参照してください[サーバーと OLAP 以外のすべてのキューブのデータ ソース内のデータベース名を更新する](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_UpdateDS_non_OLAP)します。  
  
###  <a name="BKMK_StarUpdateBAMConfig"></a> BAM 構成を更新するには  
  
1. BAM を復元するときに使用する .xml ファイルのコピーを用意します。  
  
   1. をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
   2. BizTalk Server を実行するコンピューター上には、次のフォルダーを参照してください。  
  
      - 場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 ビット バージョンの Windows Server にインストールされます。  
  
         **%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**  
  
      - 場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 ビット バージョンの Windows Server にインストールされます。  
  
         **%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**  
  
   3. コマンド プロンプトで、次のように入力します。  
  
       **Bm.exe config の取得 –filename:BAMConfiguration.xml-サーバー:\<servername\> -データベース:\<データベース\>**  
  
      > [!NOTE]
      >  このコマンドを実行するときに、実際の構成情報の取得元のサーバーの名前に置き換えてください\<servername\>の構成情報の取得元のデータベースの実際の名前に置き換えます。\<データベース\>します。 詳細については、BAM 管理 (BM) ユーティリティを使用して、次を参照してください。[インフラストラクチャ管理コマンド](http://go.microsoft.com/fwlink/?LinkId=156516)(<http://go.microsoft.com/fwlink/?LinkId=156516>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
2. BAMConfiguration.xml ファイルを編集し、変更、 **ServerName**で、`<DeploymentUnit Name="StarSchemaDatabase">`セクションを新しいサーバー名。  
  
3. BAMConfiguration.xml ファイルを保存して閉じます。  
  
4. をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
5. BizTalk Server を実行するコンピューター上には、次のフォルダーを参照してください。  
  
   - 場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 ビット バージョンの Windows Server にインストールされます。  
  
      **%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**  
  
   - 場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 ビット バージョンの Windows Server にインストールされます。  
  
      **%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**  
  
6. コマンド プロンプトで、次のように入力します。  
  
    **bm.exe の更新-構成-FileName:BAMConfiguration.xml**  
  
###  <a name="BKMK_StarUpdateRef"></a> サーバーとすべての BAM SSIS パッケージ内のデータベース名を更新するには  
  
1.  すべての BAM 分析 SSIS パッケージ「bam_an _」が付いてでサーバーとデータベースの名前を更新します。 これを行うには、次のようにクリックします**開始**、 をクリック**すべてのプログラム**、 をクリック**Microsoft SQL Server 2008 R2**または**Microsoft SQL Server 2008 SP1**、順にクリックします。**SQL Server Business Intelligence Development Studio**します。  
  
2.  SQL Server Business Intelligence Development Studio で、プロジェクトを新規作成します。 をクリックして**ファイル**、 をクリックして**新規**、 をクリックし、**プロジェクト**します。  
  
3.  **新しいプロジェクト**] ダイアログ ボックスで、**プロジェクトの種類**ボックスで、[**ビジネス インテリジェンス プロジェクト**します。 右側のウィンドウで、**テンプレート**ボックスで、 **Integration Services プロジェクト**、順にクリックします**OK**。  
  
4.  **Integration Services プロジェクト** ダイアログ ボックスで、ソリューション エクスプ ローラーで右クリックして**SSIS パッケージ**、順にクリックします**既存パッケージの追加**します。  
  
5.  **既存パッケージのコピーの追加** ダイアログ ボックスで、 **Server**ドロップダウン リスト ボックスで bam_an _ のパッケージを格納しているサーバーを選択します。  
  
6.  **パッケージ パス**、省略記号ボタンをクリックします。  
  
7.  **SSIS パッケージ** ダイアログ ボックスで、更新、 をクリックするパッケージを選択**ok**、順にクリックします**OK**します。  
  
     これで、パッケージがソリューション エクスプローラにリストされました。  
  
8.  ソリューション エクスプ ローラーで、前の手順で追加したパッケージをダブルクリックします。 **接続マネージャー** (画面の下半分に利用可能) タブで、データ ソース数 2 (BAMStarSchema データベース) をダブルクリックします。  
  
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
  
22. をクリックして**OK**、順にクリックします**はい**を上書きします。  
  
23. すべての BAM キューブ更新およびデータ保守 SSIS パッケージを有効にします。  
  
###  <a name="BKMK_UpdateDS_non_OLAP"></a> サーバーと OLAP 以外のすべてのキューブのデータ ソース内のデータベース名を更新するには  
  
1. すべての OLAP キューブのデータ ソースのサーバーおよびデータベース名を更新します。 これを行うには、次のようにクリックします**開始**、 をクリック**すべてのプログラム**、 をクリック**Microsoft SQL Server 2008 R2**または**Microsoft SQL Server 2008 SP1**、順にクリックします。**SQL Server Management Studio**します。  
  
2. **サーバーへの接続** ダイアログ ボックスの**サーバーの種類**ドロップダウン リストを**Analysis Services**認証方法を選択して、サーバー名を指定 (および資格情報の入力が必要な場合)、をクリックし、 **Connect**します。  
  
3. オブジェクト エクスプ ローラーで、**データベース**、展開**BAMAnalysis**、展開**データソース**、データ ソースをダブルクリックします。  
  
4. **データ ソースのプロパティ** ダイアログ ボックスで、省略記号ボタンをクリックします **(...)。** に対して、**接続文字列**プロパティ。  
  
5. **接続マネージャー**  ダイアログ ボックスで、**サーバー名**ボックスを BAMStarSchema データベースをホストするサーバーの名前を入力し、をクリックして**OK**順にクリックします**OK**します。  
  
6. すべて開始[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サービス。 詳細については、トピックを参照してください。[方法を開始、停止、一時停止、再開、または BizTalk Server サービスを再起動](http://go.microsoft.com/fwlink/?LinkId=154394)(<http://go.microsoft.com/fwlink/?LinkId=154394>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
7. IIS サービスを開始します。  
  
8. BAM 警告 Notification service を開始します。  
  
   1.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
   2.  コマンド プロンプトで、次のように入力します。  
  
        **Net start NS$ BamAlerts**  
  
9. すべての不完全なトレース インスタンスを解決します。  不完全な BAM アクティビティ インスタンスの解決方法の詳細については、[不完全なアクティビティ インスタンスの解決方法](http://go.microsoft.com/fwlink/?LinkId=151475)(http://go.microsoft.com/fwlink/?LinkId=151475)を参照してください。  
  
> [!TIP]  
>  をお勧め、BAMStarSchema データベースをホストするサーバーに bam_an _ * SSIS パッケージを移動する必要があります。  
  
## <a name="see-also"></a>参照  
 [データベースの移動](../technical-guides/moving-databases.md)