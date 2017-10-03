---
title: "指向ソリューションのスタブ バージョンのサービスをインストールする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IIS, installing virtual directories [service solutions]
- service solution tutorial, IIS virtual directories
- service solution tutorial, stub version
- deploying, BAM solutions [service solutions]
- service solution tutorial, solutions [BAM]
- service solution tutorial, service solutions
- SSO, configuring
- IBM WebSphere MQ Client
- service solution tutorial, IBM WebSphere MQ Client
- installing, tutorials
- service solutions, deploying
- service solution tutorial, SSO
- BAM, deploying solutions
- service solution tutorial, building solutions
- service solution tutorial, installing
ms.assetid: 45de7681-4df0-47a4-a02c-509140423a1e
caps.latest.revision: "53"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c000c733097bffa58f652801b459c429df149e56
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-install-the-stub-version-of-the-service-oriented-solution"></a>サービス指向ソリューションのスタブ バージョンのインストール方法
次の手順では、サービス指向ソリューションのスタブ バージョンをインストールするための事前準備を行う方法およびコンピューターにソリューションをインストールする方法について説明します。  
  
-   [サービス指向ソリューションのスタブ バージョンをインストールするコンピューターを準備します。](#step1)  
  
-   [IBM WebSphere MQ Client for Windows をインストールします。](#step3)  
  
-   [サービス指向ソリューションの IIS で仮想ディレクトリを作成します。](#step5)  
  
-   [ビルド サービス指向ソリューション](#step7)  
  
-   [SSO データベース内のエンタープライズ シングル サインオン (SSO) エントリと値を作成します。](#step9)  
  
-   [サービス指向ソリューションの BAM 定義を展開します。](#step11)  
  
-   [配置サービス指向ソリューション](#step13)  
  
##  <a name="step1"></a>サービス指向ソリューションのスタブ バージョンをインストールするコンピューターを準備します。  
  
#### <a name="to-prepare-the-computer-for-installing-the-stub-version-of-the-service-oriented-solution"></a>サービス指向ソリューションのスタブ バージョンをコンピューターにインストールするための準備を行うには  
  
1.  確認して、 **Default Web Site** ASP.NET を使用するように構成が 2.X です。  
  
    1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、クリックして**インターネット インフォメーション サービス (IIS) マネージャー**.  
  
    2.  **インターネット インフォメーション サービス (IIS) マネージャー**、マシン名を展開**サイト**、展開**Default Web Site**、展開**aspnet_client**、展開**[system_web]**です。  
  
    3.  サブフォルダーが 2.X であることを確認します。  
  
2.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリック**Services**です。 使用して、 **Services**コンソールで、次のサービスが実行されていることを確認してください。  
  
    -   **World Wide Web 発行**  
  
3.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、 をクリックして**コンピューターの管理**コンソール、および追加し、ローカルの Administrators グループに BizTalk サービス アカウント。  
  
4.  Windows SharePoint Services をインストールした場合は、(ルート) を除外する、**既定の Web サイト**Windows SharePoint Services 管理パスから次のようにします をクリック**開始**、 をポイント**すべてのプログラム。**、指す**管理ツール**、順にクリック**SharePoint サーバーの全体管理**です。  
  
    1.  **仮想サーバーの構成****仮想サーバーの設定を構成する**です。  
  
    2.  **仮想サーバーのリスト**] ページで [**既定の Web サイト**です。  
  
    3.  **仮想サーバーの設定**] ページで [**管理パスの定義**です。  
  
    4.  **インクルード パス**のセクションで、**管理パスの定義** ページで、**ルート** をクリックし、**選択したパスの削除**です。  
  
    5.  コマンド プロンプトで IISReset コマンドを実行します。  
  
5.  コンピュータからログオフして、BizTalk サービス アカウントを使用してコンピュータにログオンします。  
  
6.  コマンド プロンプトを開いて、次のコマンドを入力し、<localizedText>Enter</localizedText> キーを押して、%BTSSolutionsPath% 環境変数を設定します。 次に、コマンド プロンプトを終了します。  
  
    -   setx BTSSolutionsPath "[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Scenarios"  
  
        > [!NOTE]
        >  64 ビット コンピューターを使用する場合は、「%ProgramFiles%」の代わりに「%ProgramFiles%(x86)」と入力してください。  
  
        > [!NOTE]
        >  SETX コマンドの詳細については、Microsoft TechNet Web サイトを参照してください。 [http://go.microsoft.com/fwlink/?LinkId=67831](http://go.microsoft.com/fwlink/?LinkId=67831)です。  
  
##  <a name="step3"></a>IBM WebSphere MQ Client for Windows をインストールします。  
  
#### <a name="to-install-the-ibm-websphere-mq-client-for-windows"></a>IBM WebSphere MQ Client for Windows をインストールするには  
  
1.  IBM WebSphere MQ Client for Windows の最新バージョンをダウンロードします。  
  
    > [!NOTE]
    >  このソリューションのスタブ バージョンで IBM WebSphere Server を使用しない場合でも、クライアント アプリケーションは、IBM WebSphere MQ Client for Windows から提供される amqmdnet.dll ファイルを参照します。このため、IBM WebSphere MQ Client for Windows をインストールする必要があります。 スタブ バージョンのクライアントは、この DLL の API を実際に呼び出しません。 クライアント アプリケーションをコンパイルおよび実行する場合のみ、この DLL が必要です。 IBM Web サイトから IBM WebSphere MQ Client for Windows をダウンロードできます。  
  
2.  IBM WebSphere MQ Client for Windows をインストールします。  
  
    > [!NOTE]
    >  IBM WebSphere MQ Client for Windows を構成する必要はありません。 すべて既定の設定のままにします。  
  
3.  .NET アセンブリの WebSphere MQ クラスをグローバル アセンブリ キャッシュ (GAC) に追加します。  
  
    1.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプトでディレクトリに移動\<IBM MQSeries インストール ディレクトリ > \bin です。  
  
    2.  次のコマンドを実行します (gacutil.exe が PATH 環境変数にあることを確認してください)。  
  
         `gacutil.exe /i amqmdnet.dll`  
  
##  <a name="step5"></a>サービス指向ソリューションの IIS で仮想ディレクトリを作成します。  
  
#### <a name="to-create-the-virtual-directories-in-iis-for-the-service-oriented-solution"></a>サービス指向ソリューションの IIS に仮想ディレクトリを作成するには  
  
1.  **インターネット インフォメーション サービス (IIS) マネージャー**を右クリックして**アプリケーション プール****アプリケーション プールの追加**です。  
  
     **アプリケーション プールの追加** ダイアログ ボックスで、「`SSOStubAppPool`で、**名前**テキスト ボックス、およびクリック**ok**です。  
  
     サービス指向ソリューションで使用する仮想ディレクトリには、スタブ バージョンのオーケストレーション用に公開する Web サービス、スタブ SAP Web サービス、スタブ Payment Tracker Web サービス、スタブ Pending Transaction Web サービスが含まれます。  
  
2.  **インターネット インフォメーション サービス (IIS) マネージャー**作成したアプリケーション プールを右クリックし、クリックして**詳細設定**です。  
  
3.  右側に列をクリックして、 **Identity**プロパティ、クリックして、省略記号 (**.**) ボタンをクリックします。  
  
4.  **アプリケーション プール Id**ダイアログ ボックスで、**カスタム アカウント**オプションをクリックして**設定**です。  
  
5.  **資格情報の設定**ダイアログ ボックスで、ユーザー名とパスワードを指定、パスワードを確認して、をクリックして**OK**です。  
  
    > [!NOTE]
    >  このユーザーには、オーケストレーション プロキシ Web サービスを実行する権限が必要です。また、BizTalk Server 管理者グループ、SSO 管理者グループ、または SSO 関連管理者グループのいずれかにこのユーザーを追加する必要があります。  
  
6.  をクリックして**OK**を閉じる、**アプリケーション プール Id**  ダイアログ ボックス。  
  
7.  **[OK]** をクリックして **[詳細設定]** ダイアログ ボックスを閉じます。  
  
8.  **インターネット インフォメーション サービス (IIS) マネージャー**、展開**Websites**を右クリックし、**既定の Web サイト**、 をポイント**新規**とをクリックして**仮想ディレクトリ**を実行する**仮想ディレクトリの作成ウィザード**です。  
  
    1.  使用して、**仮想ディレクトリの作成ウィザード**、アダプター バージョン用の Web サービス プロキシの次の仮想ディレクトリを作成します。  
  
         Alias = Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub  
  
         パス = \<BizTalk インストール ディレクトリ > \SDK\Scenarios\SO\BTSSoln\OrchProxy\Stub  
  
         Access Permissions = Read, Run scripts  
  
    2.  使用して、**仮想ディレクトリの作成ウィザード**、アダプター バージョン用の Web サービス プロキシの次の仮想ディレクトリを作成します。  
  
         Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP  
  
         パス = \<BizTalk インストール ディレクトリ > \SDK\Scenarios\SO\BTSSoln\StubWebServices\SAP  
  
         Access Permissions = Read, Run scripts  
  
    3.  使用して、**仮想ディレクトリの作成ウィザード**、アダプター バージョン用の Web サービス プロキシの次の仮想ディレクトリを作成します。  
  
         Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions  
  
         パス = \<BizTalk インストール ディレクトリ > \SDK\Scenarios\SO\BTSSoln\StubWebServices\PendingTrans  
  
         Access Permissions = Read, Run scripts  
  
    4.  使用して、**仮想ディレクトリの作成ウィザード**、アダプター バージョン用の Web サービス プロキシの次の仮想ディレクトリを作成します。  
  
         Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubPaymentTracker  
  
         パス = \<BizTalk インストール ディレクトリ > \SDK\Scenarios\SO\BTSSoln\StubWebServices\PaymentTrack  
  
         Access Permissions = Read, Run scripts  
  
9. **インターネット インフォメーション サービス (IIS) マネージャー**、展開**Web サイト、**展開、 **Default Web Site**を右クリックしてMicrosoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub をクリックして**プロパティ**、し、次のように設定を変更します。  
  
    1.  **仮想ディレクトリ** タブで、設定、**アプリケーション プール**に**SSOStubAppPool**で作成しました。  
  
    2.  をクリックして**ディレクトリ セキュリティ** タブで、をクリックして**編集**で、**認証とアクセス制御**グループ ボックスで、**統合 Windows 認証のみ有効になっている**、し、その他のオフ**認証アクセス**チェック ボックスをオンします。 をクリックして**OK**を終了します。  
  
10. **インターネット インフォメーション サービス (IIS) マネージャー**、展開**Web サイト、**展開、 **Default Web Site**を右クリックしてMicrosoft.Samples.BizTalk.WoodgroveBank.StubSAP をクリックして**プロパティ**、し、次のように設定を変更します。  
  
    1.  **仮想ディレクトリ** タブで、設定、**アプリケーション プール**に**SSOStubAppPool**で作成しました。  
  
    2.  をクリックして**ディレクトリ セキュリティ**] タブで、をクリックして**編集**で、**認証とアクセス制御**ボックスで、グループ化し、[ **の匿名アクセスの有効化**. をクリックして**OK**を終了します。  
  
11. **インターネット インフォメーション サービス (IIS) マネージャー**、展開**Web サイト、**展開、 **Default Web Site**を右クリックしてMicrosoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions をクリックして**プロパティ**、し、次のように設定を変更します。  
  
    1.  **仮想ディレクトリ** タブで、設定、**アプリケーション プール**に**SSOStubAppPool**で作成しました。  
  
    2.  をクリックして**ディレクトリ セキュリティ**] タブで、をクリックして**編集**で、**認証とアクセス制御**ボックスで、グループ化し、[ **の匿名アクセスの有効化**. をクリックして**OK**を終了します。  
  
12. **インターネット インフォメーション サービス (IIS) マネージャー**、展開**Web サイト、**展開、 **Default Web Site**を右クリックしてMicrosoft.Samples.BizTalk.WoodgroveBank.StubPaymentTracker をクリックして**プロパティ**、し、次のように設定を変更します。  
  
    1.  **仮想ディレクトリ** タブで、設定、**アプリケーション プール**に**SSOStubAppPool**で作成しました。  
  
    2.  をクリックして**ディレクトリ セキュリティ**] タブで、をクリックして**編集**で、**認証とアクセス制御**ボックスで、グループ化し、[ **の匿名アクセスの有効化**. をクリックして**OK**を終了します。  
  
##  <a name="step7"></a>ビルド サービス指向ソリューション  
  
#### <a name="to-build-the-service-oriented-solution"></a>サービス指向ソリューションをビルドするには  
  
1.  開始**Visual Studio コマンド プロンプト**です。  
  
    > [!NOTE]
    >  ファイルに**%BTSInstallPath%\Scenarios\SO\BTSSoln\OrchProxy\Inline\app_code\customerserviceport.asmx.cs**と**%BTSInstallPath%\Scenarios\SO\BTSSoln\OrchProxy\Stub\app_code\customerserviceport.asmx.cs**17f20caea2afcc8c のすべてのインスタンスを a1054514fc67bded に置き換えます。  
  
2.  Visual Studio コマンド プロンプトで、ディレクトリを %BTSSolutionsPath%\SO\BTSSoln フォルダーに変更し、次のコマンドを実行して、サービス指向ソリューションのスタブ バージョンをビルドします。  
  
    -   `SetupBTSSoln.bat`  
  
    > [!NOTE]
    >  次に示すファイルで、17f20caea2afcc8c のすべてのインスタンスを現在の公開キー トークンに置き換えます。  
    >   
    >  -   %BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\Aggregate_To_CustomerServiceResponse.btm.cs  
    > -   %BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\Aggregate_To_ErrorResponse.btm.cs  
    > -   %BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_CreditLimitResponse.btm.cs  
    > -   %BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_CustomerServiceResponseDenied.btm.cs  
    > -   %BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_LastPaymentResponseTimeout.btm.cs  
    > -   %BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_PendingTransactionResponse.btm.cs  
  
##  <a name="step9"></a>SSO データベース内のエンタープライズ シングル サインオン (SSO) エントリと値を作成します。  
  
#### <a name="to-create-the-enterprise-single-sign-on-sso-entries-and-values-in-the-sso-database"></a>エンタープライズ シングル サインオン (SSO) エントリおよび SSO データベースの値を作成するには  
  
1.  コマンド プロンプトを開いて、現在のディレクトリを %BTSSolutionsPath%\SO\BTSSoln\Scripts に変更し、次のコマンドを実行して、エンタープライズ シングル サインオン (SSO) フォルダーに使用する PATH 環境変数を設定します。  
  
    -   `Set PATH=%PATH%;%ProgramFiles%\"Common Files\Enterprise Single Sign-On"`  
  
2.  コマンド プロンプトで、ディレクトリを %BTSSolutionsPath%\SO\BTSSoln\Scripts フォルダーに変更します。次に、メモ帳で ConfigStoreApp.xml を開き、ファイルの内容を確認します。  
  
    > [!NOTE]
    >  このファイルは、このシナリオで構成パラメーターを保存するために使用する SSO の構成ストア アプリケーションを定義します。 構成パラメーターのものが、**タイムアウト**(すべて次の 3 つのバージョンで) SAP と通信するために使用される値。 このファイルへの変更は、不要です。  
  
3.  コマンド プロンプトで、次のコマンドを実行して、SSO 構成ストア アプリケーションを作成します。  
  
    -   `ssomanage -createapps ConfigStoreApp.xml`  
  
4.  コマンド プロンプトで、メモ帳を使用して SetConfigValuesInSSO.cmd を開き、ファイルの内容を確認します。  
  
    > [!NOTE]
    >  このコマンド ファイルは、SSO データベース内の構成パラメーターの値を設定します。 コマンド ファイルの最初にローカル変数の値を設定する SET ステートメントがいくつか含まれます。 **SAPAdapterTimeout**、 **PendingTransactionsAdapterTimeout**、および**PaymentTrackingAdapterTimeout**値、スタブとアダプターのバージョンで使用されます。 他の値は、インライン バージョンで使用されます。 スタブ バージョンの場合、このファイルへの変更は不要です。  
  
5.  コマンド プロンプトで次のように入力します。 `SetConfigValuesInSSO.cmd`、し、ENTER キーを押して、SSO 構成ストア アプリケーションの値を格納します。  
  
6.  コマンド プロンプトで、次のコマンドを実行し、SSO のチケットを有効にします。  
  
    -   `ssomanage -tickets yes yes`  
  
##  <a name="step11"></a>サービス指向ソリューションの BAM 定義を展開します。  
  
#### <a name="to-deploy-the-bam-definition-for-the-service-oriented-solution"></a>サービス指向ソリューションの BAM 定義を展開するには  
  
1.  コマンド プロンプトで次のコマンドを入力し、&lt;localizedText&gt;Enter&lt;/localizedText&gt; キーを押します。 これには、BAM ユーティリティを検索するパスを設定します。  
  
    -   SET PATH=%PATH%;%programfiles%\Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]\Tracking  
  
2.  コマンド プロンプトで、ディレクトリを %BTSSolutions%\SO\BTSSoln\BAM フォルダーに変更し、次のコマンドを入力して Enter キーを押します。  
  
    -   `bm deploy-all -DefinitionFile:ServiceLevelTracking.xml`  
  
        > [!NOTE]
        >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
##  <a name="step13"></a>配置サービス指向ソリューション  
  
#### <a name="to-deploy-the-service-oriented-solution"></a>サービス指向ソリューションを展開するには  
  
1.  コマンド プロンプトを開き、ディレクトリを %BTSSolutionsPath%\SO\BTSSoln\Scripts フォルダーに変更します。  
  
2.  変更、 **DeployStubBinding.cmd**ファイルで、"release"と"debug"と"development"のすべてのインスタンス。  
  
3.  コマンド プロンプトを開き、ディレクトリを %BTSSolutionsPath%\SO\BTSSoln\Scripts フォルダーに変更します。 次のコマンドを入力し、Enter キーを押します。  
  
    -   `DeployStubBinding.cmd`  
  
4.  コマンド プロンプトで、次のコマンドを実行し、スタブ バージョンのオーケストレーションを開始します。  
  
    -   `Startstub.vbs`  
  
## <a name="next-steps"></a>次の手順  
 サービス指向ソリューションのスタブ バージョンがどのように動作するかをテストする[サービス指向ソリューションの実行方法](../core/how-to-run-the-service-oriented-solution.md)です。  
  
## <a name="see-also"></a>参照  
 [サービス指向ソリューションをインストールする前に](../core/before-installing-the-service-oriented-solution.md)   
 [指向ソリューションのインライン バージョンおよびアダプター バージョンのサービスをインストールする方法](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md)   
 [開発者のコンピュータ設定、サービス指向ソリューション](../core/developer-machine-setup-for-the-service-oriented-solution.md)