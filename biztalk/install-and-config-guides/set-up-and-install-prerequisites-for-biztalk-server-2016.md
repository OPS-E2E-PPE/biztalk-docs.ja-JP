---
title: "設定し、BizTalk Server 2016 の前提条件のインストール |Microsoft ドキュメント"
description: "インストールして、必要なソフトウェアと BizTalk Server 2016 用の設定を構成する手順"
author: MandiOhlinger
manager: anneta
ms.prod: biztalk-server
ms.custom: 
ms.date: 08/15/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aa70b621-903a-4cfa-9cb0-c6a82ed8f733
caps.latest.revision: "11"
ms.author: mandia
ms.openlocfilehash: bee25a841d7f434fd5366f483b0b5544462d29fd
ms.sourcegitcommit: 5355a25d120d094778fb8f68ea14cab55c68d292
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2017
---
# <a name="set-up-and-install-prerequisites-for-biztalk-server-2016"></a>BizTalk Server 2016 のセットアップとインストールの前提条件
サーバーのセットアップとソフトウェアのインストール/構成の前提条件。

## <a name="join-the-local-administrators-group"></a>ローカルの Administrators グループへの参加
BizTalk Server をインストールして構成するには、ローカル コンピューターで管理者アカウントを利用してサーバーにサインインします。 BizTalk Server を管理しているユーザー アカウントがあれば、それをローカル Administrators グループに追加します。

1.  [スタート] メニューで **[コンピューターの管理]** を開きます。

    * あるいは、**[管理ツール]** を開き、**[コンピューターの管理]** を選択します。
    * あるいは、**[サーバー マネージャー]** を開き、**[ツール]** を選択し、**[コンピューターの管理]** を選択します。
  
2.  **[ローカル ユーザーとグループ]** を展開し、**[グループ]** を選択します。
3.  **[監理者]** グループを右クリックし、**[グループに追加]** を選択します。 アカウントを**追加**し、**[OK]** を選択して変更を保存します。 

## <a name="change-the-computer-name-to-less-than-15-characters-optional"></a>コンピューター名を 15 文字以下に変更します (省略可能)。
コンピューター名が 15 文字より長い場合は、BizTalk Server の構成は失敗します。 コンピューター名を変更するには:

1.  **[サーバー マネージャー]** > **[ダッシュボード]** で **[ローカル サーバー]** を選択します。 
2.  **[プロパティ]** で、コンピューターの名前プロパティを選択し、変更します。
3. コンピューターを再起動します。 

**関連項目**: Windows PowerShell [Rename-Computer](https://technet.microsoft.com/library/hh849792.aspx)

## <a name="enable-network-dtc-access"></a>ネットワーク DTC アクセスを有効にする
BizTalk と SQL Server が別々のコンピューターにインストールされている場合、BizTalk Server と SQL Server でネットワーク DTC アクセスを有効にします。 

1. [スタート] メニューで、"dcomcnfg" を開きます。

    * あるいは、**[管理ツール]** を開き、**[コンポーネント サービス]** を選択します。
    * あるいは、**[サーバー マネージャー]** を開き、**[ツール]** を選択し、**[コンポーネント サービス]** を選択します。
  
2. **[コンポーネント サービス]**、**[コンピューター]**、**[マイ コンピューター]**、**[分散トランザクション コーディネーター]** の順に展開します。
3. **[ローカル DTC]** を右クリックし、**[プロパティ]** を選択します。
4. **[セキュリティ]** タブに移動し、次の項目を確認します。  
    * ネットワーク DTC アクセス
    * 受信を許可する
    * 送信を許可する
    * 認証を必要としない
5. [ **OK**] を選択します。 MS DTC を再起動するメッセージが表示されたら、選択**はい**です。 

追加の設定が必要な場合、「[MSDTC を使用した問題のトラブルシューティング](../core/troubleshooting-problems-with-msdtc.md)」を参照してください。

## <a name="configure-the-application-event-log-optional"></a>(省略可能) アプリケーション イベント ログを構成します。

BizTalk Server のセットアップを実行すると、イベントの記録がアプリケーション イベント ログに保存されます。 インストールされる BizTalk Server の機能によっては、ログの空き領域を超える大きさのログが作成されることもあります。 セットアップ中にアプリケーション イベント ログの領域が不足すると、インストールは失敗します。 アプリケーション イベント ログの設定を変更すれば、この失敗を回避できます。

1. [スタート] メニューで、**[イベント ビューアー]** を開きます。

    * あるいは、**[管理ツール]** を開き、**[イベント ビューアー]** を選択します。
    * あるいは、**[サーバー マネージャー]** を開き、**[ツール]** を選択し、**[イベント ビューアー]** を選択します。
  
2. **[Windows ログ]** を展開し、**[アプリケーション]** を右クリックして **[プロパティ]** を選択します。 
3. 使用可能な空き領域を確認するには、**[ログ サイズ]** と **[最大ログ サイズ]** のプロパティを比較します。 

    * 空き領域を増やすには、**[最大ログ サイズ]** の数値を増やします。
    * ログの空き領域がなくなったときに古いイベントが上書きされるようにするには、**[必要に応じてイベントを上書きする]** を選択します。
    * ログ イベントを消去するには、**[ログの消去]** を選択します。

4. [ **OK**] を選択します。

## <a name="edge-cant-be-opened-using-the-built-in-administrator-account-optional"></a>エッジは、ビルトイン Administrator アカウント (省略可能) を使用して開くことができません。

Edge の利用時に次のメッセージが表示されます:  
`Microsoft Edge can't be opened using the Built-in Administrator account. Sign in with a different account and try again.`

ビルトイン Administrator アカウントで Edge を開くには:

1. [スタート] メニューで、**[ローカル セキュリティ ポリシー]** を開きます。 あるいは、**[サーバー マネージャー]** を開き、**[ツール]** を選択し、**[ローカル セキュリティ ポリシー]** を選択します。
2.  **[ローカル ポリシー]** を展開し、**[セキュリティ オプション]** を選択します。 
3.  **[ユーザー アカウント制御: ビルトイン Administrator アカウントのための管理者承認モード]** ポリシーに移動し、ポリシーを**有効にします**。 
4. **[OK]** を選択し、コンピューターを再起動します。

## <a name="install-windows-updates"></a>Windows の更新プログラムをインストールする

必ず最新の重要な Windows 更新プログラムをインストールしてください。 

1. [スタート] メニューで、**[Windows の更新プログラム]** を開き、更新がないか確認します。 **[設定]** を開き、**[更新とセキュリティ]** を選択することもできます。
2. 更新プログラムのインストール後、コンピューターを再起動する必要がある場合があります。

## <a name="enable-internet-information-services-iis"></a>インターネット インフォメーション サービス (IIS) を有効にする
BizTalk Server の機能のうち、IIS を必要とするものは次のとおりです。

- HTTP アダプター
- SOAP アダプター
- Windows SharePoint Services アダプター
- SSL (Secure Sockets Layer) 暗号化
- BAM ポータル
- EDI 

IIS は**役割**または**機能**としてオペレーティング システムに付属します。OS によって役割または機能になります。 インストール方法:

1. [スタート] メニューで、**[Windows の機能の有効化または無効化]** をクリックします。 あるいは、**[サーバー マネージャー]** を開き、**[管理]** を選択し、**[役割と機能の追加]** を選択します。
2. **[インターネット インフォメーション サービス]** または **[Web サーバー (IIS)]** を選択します。 既定でオンになっているオプションのほか、次の項目も選択します: 

    **Windows 10**
    - **[Web 管理ツール]** で、次の項目もオンにします:  
        - IIS 6 管理互換
        - IIS 6 管理コンソール
        - IIS 6 スクリプト ツール (adsutil.vbs のインストール)
        - IIS メタベースおよび IIS 6 構成との互換性
        - IIS 管理コンソール
    - **[World Wide Web サービス]** で **[セキュリティ]** を展開し、次の項目もオンにします:
        - 基本認証
        - [Windows 認証]    

    **Windows Server**
    - **[セキュリティ]** で、次の項目もオンにします: 
        - 基本認証
        - [Windows 認証]    
    - **[管理ツール]** で、次の項目もオンにします:  
        - IIS 管理コンソール
        - IIS 6 管理互換
        - IIS 6 メタベース互換性
        - IIS 6 管理コンソール
        - IIS 6 スクリプト ツール (adsutil.vbs のインストール)

3. インストールを続行します。コンピューターの再起動が求められたら再起動します。 

**関連項目**: [Windows 8 または Windows Server 2012](http://www.iis.net/learn/get-started/whats-new-in-iis-8/installing-iis-8-on-windows-server-2012) に IIS をインストールする


## <a name="running-the-bam-portal-in-a-64-bit-environment-optional"></a>64 ビット環境で BAM ポータルを実行する (省略可能)
BAM ポータルを使用しない場合は、このセクションを省略できます。 

BAM ポータルは、32 ビット モードで動作します。 64 ビット環境でインターネット インフォメーション サービス (IIS) を使用している場合は、32 ビット モードで実行するアプリケーション プールを設定します。 

#### <a name="using-adsutilvbs"></a>adsutil.vbs を利用する
1.  管理者としてコマンド プロンプトを開きます。 
2.  コマンド プロンプトで、次のように入力します:  
    `cscript c:\inetpub\adminscripts\adsutil.vbs SET W3SVC/AppPools/Enable32bitAppOnWin64 1`
3. Enter を選択します。

#### <a name="using-iis-manager"></a>IIS マネージャーを利用する
1. [スタート] メニューで、"inetmgr" を開きます。
2.  コンピューター名を展開して、**[アプリケーション プール]** を選択します。
3.  **[DefaultAppPool]** を右クリックし、**[詳細設定]** を選択します。 
4.  **[32 ビット アプリケーションの有効化]** の値を **[True]** に変更します。 
5.  [**OK**] を選択します。

## <a name="install-windows-identity-foundation-wif-optional"></a>Windows Identity Foundation をインストールする (省略可能)
SharePoint Services アダプターを使用する場合、BizTalk Server には、WIF が必要です。 SharePoint Services アダプターを使用しない場合、このセクションを省略できます。

Windows Identity Foundation はオペレーティング システムに**機能**として付属します。

1. [スタート] メニューで、**[Windows の機能の有効化または無効化]** をクリックします。 あるいは、**[サーバー マネージャー]** を開き、**[管理]** を選択し、**[役割と機能の追加]** を選択します。
2. **[Windows Identity Foundation 3.5]** を選択し、インストールを続行します。 
3. 再起動を促すメッセージが表示されたら、コンピューターを再起動します。

## <a name="install-and-configure-smtp-server-optional"></a>SMTP サーバーのインストールと構成 (省略可能)
BAM 警告を使用する場合、BizTalk Server には、SMTP サーバーが必要です。 BAM 警告を使用しない場合、このセクションを省略できます。

SQL Server Database Mail では SMTP サーバーを使用して BAM 警告を送信します。 SMTP サーバーは BizTalk Server のローカル、または IIS のインストールされた別のサーバーにインストールできます。 SMTP サーバーは、Windows 8.1 や Windows 10 のようなクライアント オペレーティング システムでは利用できません。 

SMTP サーバーは**機能**としてサーバー オペレーティング システムに付属します。

1. [スタート] メニューで、**[Windows の機能の有効化または無効化]** をクリックします。 あるいは、**[サーバー マネージャー]** を開き、**[管理]** を選択し、**[役割と機能の追加]** を選択します。
2. **[SMTP サーバー]** を選択し、インストールを続行します。 
3. 再起動を促すメッセージが表示されたら、コンピューターを再起動します。

## <a name="install-microsoft-office-excel-2016-or-excel-2013-optional"></a>Microsoft Office Excel 2016 または Excel 2013 をインストールする (省略可能)
ビジネス アクティビティ監視 (BAM) を使用する場合、BizTalk Server には、Excel が必要です。 BAM を使用しない場合、このセクションを省略できます。

BAM の Office Excel では、監視するビジネス プロセスを定義します。 この BAM Excel ブックでは、BAM によって収集されたデータをどのようにビジネス ユーザーの画面に表示するかを定義することもできます。

> [!IMPORTANT] 
> * BizTalk Server は、32 ビット版の Microsoft Office のみをサポートします。 
> * BAM.xla を Excel に正しく読み込むには、(**[Office 共有機能]** の下の) **[Visual Basic for Applications]** をインストールします。 インストールしない場合、次のエラーが表示されることがあります: `This workbook has lost its VBA project, ActiveX controls and any other programmability-related features.`

#### <a name="install-excel-2016"></a>Excel 2016 をインストールする

Office 2016 は "クイック実行" または "C2R インストーラー" でインストールされます。 C2R インストールでは、Office 内のすべてのプログラムがダウンロードされ、インストールされます。 BAM の場合、必要なのは Excel のみです。 この問題を回避するには、[Office 2016 展開ツール](https://www.microsoft.com/download/details.aspx?id=49117)をダウンロードしてインストールし、C2R インストーラーをカスタマイズします。

1. [Office 2016 展開ツール](https://www.microsoft.com/download/details.aspx?id=49117)をダウンロードし、インストールします。
2. 解凍した Office 2016 展開ツール ファイルが含まれるフォルダーで、メモ帳などのテキスト エディターで **configuration.xml** ファイルを開きます。
3. `<Configuration>` セクションを次のように置換します。  

    ```
    <Configuration>
    <Add SourcePath="D:\" OfficeClientEdition="32">
    <Product ID="O365ProPlusRetail" >
      <Language ID="en-us" />
      <ExcludeApp ID="Access" />
      <ExcludeApp ID="Groove" />
      <ExcludeApp ID="InfoPath" />
      <ExcludeApp ID="Lync" />
      <ExcludeApp ID="OneDrive" />
      <ExcludeApp ID="OneNote" />
      <ExcludeApp ID="Outlook" />
      <ExcludeApp ID="PowerPoint" />
      <ExcludeApp ID="Project" />
      <ExcludeApp ID="Publisher" />
      <ExcludeApp ID="SharePointDesigner" />
      <ExcludeApp ID="Visio" />
      <ExcludeApp ID="Word" />
    </Product>
    </Add>
    </Configuration>
    ```
    
    “SourcePath” を Office 2016 ISO ファイルの場所に置換します。
4. Office 2016 展開ツール ファイルが含まれるフォルダーで、**SHIFT** キーを押したままフォルダー内の何もない領域を右クリックします。 **[コマンド ウィンドウをここで開く]** を選択します。 
5. を入力し、Excel インストールを開始します。  
  `setup.exe /configure configuration.xml`

    > [!TIP]
    > `setup.exe /download configuration.xml` は必要な Office セットアップ ファイルをダウンロードします。
 
6. [Excel] を選択し、インストールを続行します。 
 
**関連項目**: [Office 展開ツールのオプションの構成](https://technet.microsoft.com/library/jj219426.aspx)と [Office 2016 または 2013 のインストール](https://support.office.com/article/Install-Office-on-your-PC-or-Mac-4414eaaf-0478-48be-9c42-23adc4716658)

#### <a name="install-excel-2013"></a>Excel 2013 をインストールする
1. Microsoft Office のセットアップを実行します。
2. **[カスタム インストール]** を選択し、[Excel] を選択します。
3. インストールを続行します。   

## <a name="install-visual-c-redistributable-package"></a>Visual C 再頒布可能パッケージをインストールします。

ダウンロードしてインストール、 [Visual C 再頒布可能パッケージ](https://support.microsoft.com/help/3179560/update-for-visual-c-2013-and-visual-c-redistributable-package)です。 Visual Studio 2015 が使用されている場合でも、2013 バージョンが必要です。

[Visual C をダウンロード](https://support.microsoft.com/help/2977003/the-latest-supported-visual-c-downloads)使用可能なすべてのバージョンを一覧表示します。

## <a name="install-visual-studio-2015-optional"></a>Visual Studio 2015 をインストールします (省略可能)。
開発ツールで BizTalk プロジェクトを作成するために、BizTalk Server は Visual Studio を必要とします。 これがステージングまたは運用サーバーの場合、あるいは BizTalk 開発を行っていない場合、このセクションを省略できます。

Visual Studio Enterprise Edition が推奨されますが、Professional 版と Community 版もサポートされています。 

1. Visual Studio のセットアップを管理者として実行します。
2. **既定**のインストールを選択します。 BizTalk Server は、オプション機能を必要としません。

    > [!NOTE]
    > BizTalk プロジェクト以外でも Visual Studio を使用する場合、**カスタム** インストールを選択して他の機能をインストールします。 一般的に使用される機能に、Microsoft Web Developer Tools、Microsoft Office Developer Tools、PowerShell Tools for Visual Studio、ClickOnce Publishing Tools があります。
 
3. インストールを続行します。コンピューターの再起動が求められたら再起動します。

**関連項目**: [Visual Studio のインストール](https://msdn.microsoft.com/library/e2h7fzkw.aspx)

> [!IMPORTANT]
> - BizTalk Server をインストールする前に Visual Studio をインストールし、その後 Visual Studio Team Explorer にアップグレードする場合、BizTalk Server インストールの修復が必要になることがあります。
> - Visual Studio では、Microsoft SQL Server Express は自動的にインストールされますが、BizTalk Server では使用しません。 Microsoft SQL Server Express をアンインストールします。 Microsoft SQL Server Compact もアンインストールできます。  
> - BizTalk Server 開発ツールは、Visual Studio をベースとして動作します。 BizTalk Server 開発ツールと SDK をインストールする前に、少なくとも Microsoft Visual C#® .NET コンポーネントをインストールしてください。
> - BizTalk Server ランタイムには、.NET Framework 4.6 が必要です。 Windows Communication Foundation (WCF) アダプターまたは WCF インターセプターがインストールされている場合、.NET Framework 3.0 が必要

#### <a name="uninstall-sql-server-express"></a>SQL Server Express をアンインストールする
1. [スタート] メニューで、**[プログラムと機能]** を開きます。 あるいは、**[コントロール パネル]** を開いて **[プログラムのアンインストール]** を選択します。
2. アンインストール: 
    - Microsoft SQL Server 2014 Express LocalDb
    - Microsoft SQL Server Compact 4.0 SP1 x64 ENU
    - Microsoft SQL Server 2016 LocalDB (SQL Server 2016 Express LocalDB)
    
3. アンインストールを続行します。コンピューターの再起動が求められたら再起動します。 

## <a name="install-sql-server-2016"></a>SQL Server 2016 のインストール
BizTalk Server には SQL Server が必要です。 SQL Server は、BizTalk と同じコンピューターにインストールすることも、別のコンピューターにインストールすることもできます。 ほとんどの運用環境では、BizTalk と SQL を別々のサーバーにインストールします。 

> [!IMPORTANT]
> - SQL Server Express Edition は推奨されず、サポートされていません。 Express Edition には、BizTalk Server に必要な特定の機能が含まれていません。
> - BizTalk Server は SQL Standard Edition をサポートしています。 ただし、ビジネス アクティビティの監視のリアルタイム集計 (BAM RTA) を使用するには、SQL Server Enterprise Edition をインストールします。 BAM リアルタイム集計 (RTA) は、SQL Server の Standard Edition ではサポートされません。
> - BizTalk Server SDK の全機能を使用する場合や、Visual Studio から BizTalk Server アプリケーションを展開する場合には、SQL Server 開発ツールをインストールします。
> - BizTalk Server では、バイナリ照合順序を除く、大文字と小文字を区別する/区別しないすべての SQL Server 照合順序がサポートされています。 バイナリ照合順序はサポートされません。

**特定のインストール手順については、次を参照してください。** [SQL Server 2016 のインストール](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup)または[SQL Server 2014 のインストール](https://msdn.microsoft.com/library/bb500469(v=sql.120).aspx)です。

1. SQL Server のインストールを開始します。 
2. 機能セットアップ中に、以下の項目を選択します。
    - データベース エンジン サービス
        - SQL Server のレプリケーション
        - R Services (In-database) (**省略可能な**; でヒント[SQL Server R Services](https://docs.microsoft.com/sql/advanced-analytics/r/sql-server-r-services))
        - 検索のためのフルテキスト抽出とセマンティック抽出
    - Analysis Services
    - Reporting Services - ネイティブ
    - 共有機能
        - クライアント ツール接続
        - Integration Services

    > [!NOTE]
    > **SQL Server Data Tools** は SQL Server の既定インストールには含まれていません。 必須ではありませんが、[SQL Server Data Tools (SSDT)](https://docs.microsoft.com/sql/ssdt/download-sql-server-data-tools-ssdt) でダウンロードできます。 [**SQL Server Management Studio (SSMS)**](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms) をダウンロードします。これは、Azure SQL Database を含め、サポートされているあらゆるバージョンの SQL Server で動作します。 

3. インストールを続行します。コンピューターの再起動が求められたら再起動します。

## <a name="disable-shared-memory"></a>共有メモリを無効にします。

1. [**SQL Server 構成マネージャー**] を開きます。
2. SQL Server 構成マネージャーで、展開**SQL Server ネットワーク構成**、し、 **MSSQLSERVER のプロトコル**です。
3. [**共有メモリ**] を右クリックし、[**無効**] を選択します。
4. 選択**SQL Server サービス**、SQL を右クリックして**Server (MSSQLSERVER)**、し、**停止**です。 右クリックし、サービスが停止したら、 **SQL Server (MSSQLSERVER)**、し、**開始**です。
5. **SQL Server 構成マネージャー**を終了します。

通常、共有メモリ プロトコルには、SQL Server と同じコンピューターにインストールされているクライアント (BizTalk Server) のみに影響します。 ある種のストレス条件下では (たとえば、同じコンピューターから複数のクライアントが SQL Server にアクセスしている場合)、SQL Server の共有メモリ プロトコルが原因で BizTalk Server のパフォーマンスが低下することがあります。 共有メモリ ネットワーク プロトコルを無効にすると、この解決します。

> [!TIP]
> SQL Server エージェントが共有メモリを無効にした後を開始し、確認に失敗したかどうか[SQL Server 用 ODBC Driver 13.1](https://www.microsoft.com/download/details.aspx?id=53339)がインストールされています。

## <a name="install-sql-xml-4"></a>SQL XML 4 をインストールします。
BizTalk Server ランタイム、管理ツール、および BAM で必要です。 

ダウンロードしてインストール[SqlXml 4.0](https://www.microsoft.com/download/details.aspx?id=30403)です。

## <a name="configure-sql-server-database-mail-optional"></a>SQL Server データベース メールを構成する (省略可能)
BAM 警告を使用する場合、BizTalk Server には、SQL Server Database Mail が必要です。 BAM 警告を使用しない場合は、このセクションはスキップしてください。 

**関連項目**: [データベース メール](https://docs.microsoft.com/sql/relational-databases/database-mail/database-mail)に詳細があります。

> [!IMPORTANT]
> - SMTP サーバーのサーバー名と TCP ポート番号を知っている必要があります。 この同じコンピューターでは IIS と SMTP サーバーをインストールした場合、ローカル SMTP サーバーを使用します。 SMTP サーバーが認証を必要とする場合、ユーザー名とパスワードを用意します。
> - BAM ポータルと BAM 警告は別々の機能です。 BAM 警告を使用している場合、SQL Server Database Mail が必要です。 BAM 警告を使用していない場合、SQL Server Database Mail は必要ありません。

**特定の構成手順については、次を参照してください。**: 構成[SQL Server 2016 データベース メール](https://docs.microsoft.com/sql/relational-databases/database-mail/configure-database-mail)または[SQL Server 2014 データベース メール](https://msdn.microsoft.com/library/hh245116(v=sql.120).aspx)です。

   
テスト メールを送信するには: 
1.  **[データベース メール]** を右クリックし、**[テスト電子メールの送信]** を選択します。 
2.  **[宛先:]** メール アドレスを入力し、**[テスト電子メールの送信]** を選択します。  
 
**[宛先:]** の受信者がメールを受信すると、データベース メールが構成されます。 

## <a name="install-winscp-optional"></a>(省略可能) WinSCP をインストールします。
FTP アダプタで必要です。 FTP アダプターを使用しない場合は、このセクションをスキップします。 

ダウンロードしてインストール[WinSCP](http://winscp.net)です。 

## <a name="next-step"></a>次の手順
[BizTalk Server 2016](../install-and-config-guides/install-biztalk-server-2016.md) をインストールします。
