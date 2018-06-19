---
title: BAM アーカイブ データベース 1 に移動する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e371321c-6b8d-4be6-a6d2-926f6218db01
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 383aef74519f7527383d9f681f83ace2e515eba7
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "26009819"
---
# <a name="how-to-move-the-bam-archive-database"></a>BAM アーカイブ データベースを移動する方法
ここでは、BAM アーカイブ データベースを他のサーバーに移動する手順について説明します。  エンド ツー エンドのシナリオの観点から BAM アーカイブ データベースの移動にも 2 つの主要な手順が含まれます。  
  
-   [BAM アーカイブ データベースを移動します。](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_MovingArch)  
  
-   [新しい BAM アーカイブ データベースへの参照を更新](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArch)  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行するには、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin 固定サーバー ロールのメンバーであるアカウントを使用してログオンする必要があります。  
  
##  <a name="BKMK_MovingArch"></a> BAM アーカイブ データベースを移動します。  
 BAM アーカイブ データベースを移動する次の手順で、手順を実行します。  
  
#### <a name="to-move-the-bam-archive-database"></a>BAM アーカイブ データベースを移動するには  
  
1.  すべての BAM キューブ更新およびデータ保守 SSIS パッケージを停止するか、BAM アーカイブ データベースを復元が完了するまで実行されないように措置を講じます。  
  
2.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サービスをすべて停止します。 詳細については、トピックを参照してください。[開始方法、停止、一時停止、再開、または BizTalk Server サービスを再起動](http://go.microsoft.com/fwlink/?LinkId=154394)(http://go.microsoft.com/fwlink/?LinkId=154394)で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
3.  IIS サービスを停止します。  
  
4.  BAM 警告 Notification service を停止します。  
  
    1.  をクリックして **開始**, 、 をクリックして **実行**, 、型 **cmd**, 、 をクリックし、 **ok**します。  
  
    2.  コマンド プロンプトで、次のように入力します。  
  
         **Net stop NS$BamAlerts**  
  
5.  古いサーバーで、BAM アーカイブ データベースをバックアップします。 データベースをバックアップする方法の手順についてに記載された手順に従います[する方法:、データベースのバックアップ (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (http://go.microsoft.com/fwlink/?LinkId=156510)で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]オンライン ブック、データベースをバックアップする方法です。  
  
6.  BAM アーカイブ データベースに新しいコピー[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューター。  
  
7.  新しいサーバーで、BAM アーカイブ データベースを復元します。 データベースを復元する方法について以下に記載された手順[する方法: データベースのバックアップ (SQL Server Management Studio) を復元](http://go.microsoft.com/fwlink/?LinkId=156511)(http://go.microsoft.com/fwlink/?LinkId=156511)で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースを復元する方法のオンライン ブック。  
  
##  <a name="BKMK_UpdateArch"></a> 新しい BAM アーカイブ データベースへの参照を更新  
 データベースを移動した後は、新しい BAM アーカイブ データベースにすべての参照を更新する必要があります。 次の参照を更新する必要があります。  
  
-   新しいデータベースとサーバーの名前で、BAM 構成を更新します。 参照してください[BAM 構成を更新する](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArchConfig)です。  
  
-   すべての BAM analysis の SSIS パッケージで新しいサーバーおよびデータベース名を更新します。 参照してください[サーバーとすべての BAM SSIS パッケージ内のデータベース名を更新する](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArchSSIS)です。  
  
###  <a name="BKMK_UpdateArchConfig"></a> BAM 構成を更新するには  
  
1.  BAM を復元するときに使用する .xml ファイルのコピーを用意します。  
  
    1.  をクリックして **開始**, 、 をクリックして **実行**, 、型 **cmd**, 、 をクリックし、 **ok**します。  
  
    2.  BizTalk Server を実行するコンピューター上には、次のフォルダーを参照してください。  
  
        -   場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が 64 ビット バージョンの Windows Server にインストールされています。  
  
             **%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**  
  
        -   場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が 32 ビット バージョンの Windows Server にインストールされています。  
  
             **%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**  
  
    3.  コマンド プロンプトで、次のように入力します。  
  
         **Bm.exe get-config –filename:BAMConfiguration.xml -server:\<servername\> -database:\<database\>**  
  
        > [!NOTE]  
        >  このコマンドを実行するときに、サーバーの構成情報の取得元の実際の名前に置き換える\<servername\>の構成情報の取得元のデータベースの実際の名前を使用してください\<データベース\>です。 詳細については、BAM 管理 (BM) ユーティリティを使用して、次を参照してください。[インフラストラクチャ管理コマンド](http://go.microsoft.com/fwlink/?LinkId=156516)(http://go.microsoft.com/fwlink/?LinkId=156516)で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
2.  BAMConfiguration.xml ファイルを編集し、変更、 **ServerName**で、`<DeploymentUnit Name="ArchivingDatabase">`セクションに新しいサーバーの名前。  
  
3.  BAMConfiguration.xml ファイルを保存して閉じます。  
  
4.  をクリックして **開始**, 、 をクリックして **実行**, 、型 **cmd**, 、 をクリックし、 **ok**します。  
  
5.  BizTalk Server を実行するコンピューター上には、次のフォルダーを参照してください。  
  
    -   場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が 64 ビット バージョンの Windows Server にインストールされています。  
  
         **%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**  
  
    -   場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が 32 ビット バージョンの Windows Server にインストールされています。  
  
         **%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**  
  
6.  コマンド プロンプトで、次のように入力します。  
  
     **bm.exe update-config -FileName:BAMConfiguration.xml**  
  
###  <a name="BKMK_UpdateArchSSIS"></a> サーバーとすべての BAM SSIS パッケージ内のデータベース名を更新するには  
  
1.  すべての BAM 分析 SSIS パッケージ「bam_dm _」で始まるサーバーおよびデータベース名を更新します。 これを行うには、をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 R2**または**Microsoft SQL Server 2008 SP1**をクリックし、**SQL Server Business Intelligence Development Studio**です。  
  
2.  SQL Server Business Intelligence Development Studio で、プロジェクトを新規作成します。 クリックして **ファイル**, 、 をクリックして **新規**, 、 をクリックし、 **プロジェクト**します。  
  
3.  **新しいプロジェクト** ダイアログ ボックスで、**プロジェクトの種類**ボックスで、クリックして**ビジネス インテリジェンス プロジェクト**です。 右側のウィンドウで、**テンプレート**ボックスで、をクリックして**Integration Services プロジェクト**、クリックして **[ok]** です。  
  
4.  **Integration Services プロジェクト**ダイアログ ボックスで、ソリューション エクスプ ローラーで右クリックし**SSIS パッケージ**、クリックして**既存のパッケージの追加**です。  
  
5.  **既存のパッケージのコピーを追加** ダイアログ ボックスで、**サーバー**ドロップダウン リスト ボックスで、bam_dm _ のパッケージを含むサーバーを選択します。  
  
6.  **パッケージ パス**, 、省略記号ボタンをクリックします。  
  
7.  **SSIS パッケージ** ダイアログ ボックスで、更新するには、をクリックするパッケージを選択**ok**、順にクリック**OK**です。  
  
     これで、パッケージがソリューション エクスプローラにリストされました。  
  
8.  ソリューション エクスプ ローラーで、前の手順で追加したパッケージをダブルクリックします。 **接続マネージャー** (画面の下半分に使用可能) タブで、データ ソース番号 2 (BAMArchive データベース) をダブルクリックします。  
  
9. **接続マネージャー**  ダイアログ ボックスで、**サーバー名**ボックスで、サーバーの名前を入力し、をクリックして**OK**です。  
  
    > [!NOTE]  
    >  データ ソース数 3 (MSDB データベース) に、この手順を繰り返します。  
  
10. クリックして、**パッケージ エクスプ ローラー**  タブをダブルクリックして、**変数**フォルダー、しの値を更新、 **ArchivingDatabase**、 **ArchivingServer**、 **PrimaryImportDatabase**、および**PrimaryImportServer**変数。 新しいサーバーやデータベースを指定する値を更新する必要があります。  
  
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
  
21. すべて開始[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]services です。 詳細については、トピックを参照してください。[開始方法、停止、一時停止、再開、または BizTalk Server サービスを再起動](http://go.microsoft.com/fwlink/?LinkId=154394)(http://go.microsoft.com/fwlink/?LinkId=154394)で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
22. IIS サービスを開始します。  
  
23. BAM 警告 Notification service を開始します。  
  
    1.  をクリックして **開始**, 、 をクリックして **実行**, 、型 **cmd**, 、 をクリックし、 **ok**します。  
  
    2.  コマンド プロンプトで、次のように入力します。  
  
         **Net start NS$ BamAlerts**  
  
24. すべての BAM キューブ更新およびデータ保守 SSIS パッケージを有効にします。  
  
> [!TIP]  
>  お勧めとしても、BAMArchive データベースをホストするサーバーに bam_dm _ * SSIS パッケージを移動する必要があります。  
  
## <a name="see-also"></a>参照  
 [データベースの移動](../technical-guides/moving-databases.md)