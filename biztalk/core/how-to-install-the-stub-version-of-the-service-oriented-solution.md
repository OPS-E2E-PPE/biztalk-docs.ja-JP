---
title: 指向ソリューションのスタブ バージョンのサービスをインストールする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 53
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d42b559afb89c931aec44080beaa4c00dea89ba2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023664"
---
# <a name="how-to-install-the-stub-version-of-the-service-oriented-solution"></a>サービス指向ソリューションのスタブ バージョンのインストール方法
次の手順では、サービス指向ソリューションのスタブ バージョンをインストールするための事前準備を行う方法およびコンピューターにソリューションをインストールする方法について説明します。  
  
-   [サービス指向ソリューションのスタブ バージョンをインストールするコンピューターを準備します。](#step1)  
  
-   [IBM WebSphere MQ Client for Windows をインストールします。](#step3)  
  
-   [仮想ディレクトリが IIS でサービス指向ソリューションの作成します。](#step5)  
  
-   [ビルド サービス指向ソリューション](#step7)  
  
-   [SSO データベース内のエンタープライズ シングル サインオン (SSO) エントリと値を作成します。](#step9)  
  
-   [サービス指向ソリューションの BAM 定義を展開します。](#step11)  
  
-   [サービス指向ソリューションの展開](#step13)  
  
##  <a name="step1"></a> サービス指向ソリューションのスタブ バージョンをインストールするコンピューターを準備します。  
  
#### <a name="to-prepare-the-computer-for-installing-the-stub-version-of-the-service-oriented-solution"></a>サービス指向ソリューションのスタブ バージョンをコンピューターにインストールするための準備を行うには  
  
1. 必ず、**既定の Web サイト**ASP.NET を使用するように構成 2.X。  
  
   1.  クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**.  
  
   2.  **インターネット インフォメーション サービス (IIS) マネージャー**、マシン名を展開**サイト**、展開**既定の Web サイト**、展開**aspnet_client**、展開 **[system_web]** します。  
  
   3.  サブフォルダーが 2.X であることを確認します。  
  
2. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**サービス**します。 使用して、**サービス**コンソールで、次のサービスが実行されていることを確認します。  
  
   -   **World Wide Web の発行**  
  
3. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、 をクリックして**コンピュータの管理**コンソール、および追加し、ローカルの Administrators グループに BizTalk サービス アカウント。  
  
4. Windows SharePoint Services をインストールした場合の (ルート) を除外する、**既定の Web サイト**Windows SharePoint Services 管理パスから次のようにします をクリック**開始**、 をポイント**すべてのプログラム。**、 をポイント**管理ツール**、 をクリックし、 **SharePoint Central Administration**します。  
  
   1.  **仮想サーバーの構成**、**仮想サーバー設定を構成**します。  
  
   2.  **仮想サーバーのリスト**] ページで [**既定の Web サイト**します。  
  
   3.  **仮想サーバーの設定**] ページで [**管理パスの定義**します。  
  
   4.  **インクルード パス**のセクション、**管理パスの定義**] ページで、[**ルート**順にクリックします**選択したパスの削除**します。  
  
   5.  コマンド プロンプトで IISReset コマンドを実行します。  
  
5. コンピュータからログオフして、BizTalk サービス アカウントを使用してコンピュータにログオンします。  
  
6. コマンド プロンプトを開いて、次のコマンドを入力し、<localizedText>Enter</localizedText> キーを押して、%BTSSolutionsPath% 環境変数を設定します。 次に、コマンド プロンプトを終了します。  
  
   - setx BTSSolutionsPath "[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Scenarios"  
  
     > [!NOTE]
     >  64 ビット コンピューターを使用する場合は、「%ProgramFiles%」の代わりに「%ProgramFiles%(x86)」と入力してください。  
  
     > [!NOTE]
     >  SETX コマンドの詳細については、Microsoft TechNet Web サイトを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=67831](http://go.microsoft.com/fwlink/?LinkId=67831)します。  
  
##  <a name="step3"></a> IBM WebSphere MQ Client for Windows をインストールします。  
  
#### <a name="to-install-the-ibm-websphere-mq-client-for-windows"></a>IBM WebSphere MQ Client for Windows をインストールするには  
  
1. IBM WebSphere MQ Client for Windows の最新バージョンをダウンロードします。  
  
   > [!NOTE]
   >  このソリューションのスタブ バージョンで IBM WebSphere Server を使用しない場合でも、クライアント アプリケーションは、IBM WebSphere MQ Client for Windows から提供される amqmdnet.dll ファイルを参照します。このため、IBM WebSphere MQ Client for Windows をインストールする必要があります。 スタブ バージョンのクライアントは、この DLL の API を実際に呼び出しません。 クライアント アプリケーションをコンパイルおよび実行する場合のみ、この DLL が必要です。 IBM Web サイトから IBM WebSphere MQ Client for Windows をダウンロードできます。  
  
2. IBM WebSphere MQ Client for Windows をインストールします。  
  
   > [!NOTE]
   >  IBM WebSphere MQ Client for Windows を構成する必要はありません。 すべて既定の設定のままにします。  
  
3. .NET アセンブリの WebSphere MQ クラスをグローバル アセンブリ キャッシュ (GAC) に追加します。  
  
   1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプトでディレクトリに移動\<IBM MQSeries インストール ディレクトリ\>\bin です。  
  
   2. 次のコマンドを実行します (gacutil.exe が PATH 環境変数にあることを確認してください)。  
  
       `gacutil.exe /i amqmdnet.dll`  
  
##  <a name="step5"></a> 仮想ディレクトリが IIS でサービス指向ソリューションの作成します。  
  
#### <a name="to-create-the-virtual-directories-in-iis-for-the-service-oriented-solution"></a>サービス指向ソリューションの IIS に仮想ディレクトリを作成するには  
  
1.  **インターネット インフォメーション サービス (IIS) マネージャー**を右クリックして**アプリケーション プール**、**アプリケーション プールの追加**します。  
  
     **アプリケーション プールの追加**ダイアログ ボックスに「`SSOStubAppPool`で、**名前**テキスト ボックス、およびクリック**ok**します。  
  
     サービス指向ソリューションで使用する仮想ディレクトリには、スタブ バージョンのオーケストレーション用に公開する Web サービス、スタブ SAP Web サービス、スタブ Payment Tracker Web サービス、スタブ Pending Transaction Web サービスが含まれます。  
  
2.  **インターネット インフォメーション サービス (IIS) マネージャー**作成したアプリケーション プールを右クリックし、クリックして**詳細設定**します。  
  
3.  右側に列をクリックして、 **Identity**プロパティ、クリックして、省略記号 (**...**) ボタンをクリックします。  
  
4.  **アプリケーション プール Id**ダイアログ ボックスで、**カスタム アカウント**オプションをクリックして**設定**します。  
  
5.  **資格情報の設定**ダイアログ ボックスで、ユーザー名とパスワードを指定、パスワードの確認 をクリックし、 **OK**します。  
  
    > [!NOTE]
    >  このユーザーには、オーケストレーション プロキシ Web サービスを実行する権限が必要です。また、BizTalk Server 管理者グループ、SSO 管理者グループ、または SSO 関連管理者グループのいずれかにこのユーザーを追加する必要があります。  
  
6.  をクリックして**OK**を閉じる、**アプリケーション プール Id**  ダイアログ ボックス。  
  
7.  **[OK]** をクリックして **[詳細設定]** ダイアログ ボックスを閉じます。  
  
8.  **インターネット インフォメーション サービス (IIS) マネージャー**、展開**Websites**を右クリックし、**既定の Web サイト**、 をポイント**新規**とクリックして**仮想ディレクトリ**を実行する**仮想ディレクトリの作成ウィザード**します。  
  
    1.  使用して、**仮想ディレクトリの作成ウィザード**、アダプター バージョンの Web サービス プロキシの次の仮想ディレクトリを作成します。  
  
         Alias = Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub  
  
         パス = \<BizTalk インストール ディレクトリ\>\SDK\Scenarios\SO\BTSSoln\OrchProxy\Stub  
  
         Access Permissions = Read, Run scripts  
  
    2.  使用して、**仮想ディレクトリの作成ウィザード**、アダプター バージョンの Web サービス プロキシの次の仮想ディレクトリを作成します。  
  
         Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP  
  
         パス = \<BizTalk インストール ディレクトリ\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\SAP  
  
         Access Permissions = Read, Run scripts  
  
    3.  使用して、**仮想ディレクトリの作成ウィザード**、アダプター バージョンの Web サービス プロキシの次の仮想ディレクトリを作成します。  
  
         Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions  
  
         パス = \<BizTalk インストール ディレクトリ\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PendingTrans  
  
         Access Permissions = Read, Run scripts  
  
    4.  使用して、**仮想ディレクトリの作成ウィザード**、アダプター バージョンの Web サービス プロキシの次の仮想ディレクトリを作成します。  
  
         Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubPaymentTracker  
  
         パス = \<BizTalk インストール ディレクトリ\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PaymentTrack  
  
         Access Permissions = Read, Run scripts  
  
9. **インターネット インフォメーション サービス (IIS) マネージャー**、展開**Web サイト、** 展開、**既定の Web サイト**、右クリックMicrosoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub、 をクリックして**プロパティ**、し、次のように設定を変更します。  
  
    1.  **仮想ディレクトリ**タブで、設定、**アプリケーション プール**に**SSOStubAppPool**で作成しました。  
  
    2.  をクリックして**ディレクトリ セキュリティ**] タブで [**編集**で、**認証とアクセス制御**グループ ボックスで、**統合 Windows 認証のみ有効になっている**、し、その他のオプションをオフ**認証アクセス**チェック ボックスをオンします。 クリックして**OK**を終了します。  
  
10. **インターネット インフォメーション サービス (IIS) マネージャー**、展開**Web サイト、** 展開、**既定の Web サイト**、右クリックMicrosoft.Samples.BizTalk.WoodgroveBank.StubSAP、 をクリックして**プロパティ**、し、次のように設定を変更します。  
  
    1.  **仮想ディレクトリ**タブで、設定、**アプリケーション プール**に**SSOStubAppPool**で作成しました。  
  
    2.  をクリックして**ディレクトリ セキュリティ** タブで **編集**で、**認証とアクセス制御**ボックスで、グループ化し、 **の匿名アクセスの有効化**. クリックして**OK**を終了します。  
  
11. **インターネット インフォメーション サービス (IIS) マネージャー**、展開**Web サイト、** 展開、**既定の Web サイト**、右クリックMicrosoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions、 をクリックして**プロパティ**、し、次のように設定を変更します。  
  
    1.  **仮想ディレクトリ**タブで、設定、**アプリケーション プール**に**SSOStubAppPool**で作成しました。  
  
    2.  をクリックして**ディレクトリ セキュリティ** タブで **編集**で、**認証とアクセス制御**ボックスで、グループ化し、 **の匿名アクセスの有効化**. クリックして**OK**を終了します。  
  
12. **インターネット インフォメーション サービス (IIS) マネージャー**、展開**Web サイト、** 展開、**既定の Web サイト**、右クリックMicrosoft.Samples.BizTalk.WoodgroveBank.StubPaymentTracker、 をクリックして**プロパティ**、し、次のように設定を変更します。  
  
    1.  **仮想ディレクトリ**タブで、設定、**アプリケーション プール**に**SSOStubAppPool**で作成しました。  
  
    2.  をクリックして**ディレクトリ セキュリティ** タブで **編集**で、**認証とアクセス制御**ボックスで、グループ化し、 **の匿名アクセスの有効化**. クリックして**OK**を終了します。  
  
##  <a name="step7"></a> ビルド サービス指向ソリューション  
  
#### <a name="to-build-the-service-oriented-solution"></a>サービス指向ソリューションを構築するには  
  
1. 開始**Visual Studio コマンド プロンプト**します。  
  
   > [!NOTE]
   >  ファイルに **%BTSInstallPath%\Scenarios\SO\BTSSoln\OrchProxy\Inline\app_code\customerserviceport.asmx.cs**と **%BTSInstallPath%\Scenarios\SO\BTSSoln\OrchProxy\Stub\app_code\customerserviceport.asmx.cs**17f20caea2afcc8c のすべてのインスタンスを a1054514fc67bded に置き換えます。  
  
2. Visual Studio コマンド プロンプトで、ディレクトリを %BTSSolutionsPath%\SO\BTSSoln フォルダーに変更し、次のコマンドを実行して、サービス指向ソリューションのスタブ バージョンをビルドします。  
  
   -   `SetupBTSSoln.bat`  
  
   > [!NOTE]
   >  次に示すファイルで、17f20caea2afcc8c のすべてのインスタンスを現在の公開キー トークンに置き換えます。  
   > 
   > - %BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\Aggregate_To_CustomerServiceResponse.btm.cs  
   >   -   %BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\Aggregate_To_ErrorResponse.btm.cs  
   >   -   %BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_CreditLimitResponse.btm.cs  
   >   -   %BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_CustomerServiceResponseDenied.btm.cs  
   >   -   %BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_LastPaymentResponseTimeout.btm.cs  
   >   -   %BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_PendingTransactionResponse.btm.cs  
  
##  <a name="step9"></a> SSO データベース内のエンタープライズ シングル サインオン (SSO) エントリと値を作成します。  
  
#### <a name="to-create-the-enterprise-single-sign-on-sso-entries-and-values-in-the-sso-database"></a>エンタープライズ シングル サインオン (SSO) エントリおよび SSO データベースの値を作成するには  
  
1.  コマンド プロンプトを開いて、現在のディレクトリを %BTSSolutionsPath%\SO\BTSSoln\Scripts に変更し、次のコマンドを実行して、エンタープライズ シングル サインオン (SSO) フォルダーに使用する PATH 環境変数を設定します。  
  
    -   `Set PATH=%PATH%;%ProgramFiles%\"Common Files\Enterprise Single Sign-On"`  
  
2.  コマンド プロンプトで、ディレクトリを %BTSSolutionsPath%\SO\BTSSoln\Scripts フォルダーに変更します。次に、メモ帳で ConfigStoreApp.xml を開き、ファイルの内容を確認します。  
  
    > [!NOTE]
    >  このファイルは、このシナリオで構成パラメーターを保存するために使用する SSO の構成ストア アプリケーションを定義します。 一部の構成パラメーターを含める、**タイムアウト**(のすべての 3 つのバージョン) SAP との通信に使用される値。 このファイルへの変更は、不要です。  
  
3.  コマンド プロンプトで、次のコマンドを実行して、SSO 構成ストア アプリケーションを作成します。  
  
    -   `ssomanage -createapps ConfigStoreApp.xml`  
  
4.  コマンド プロンプトで、メモ帳を使用して SetConfigValuesInSSO.cmd を開き、ファイルの内容を確認します。  
  
    > [!NOTE]
    >  このコマンド ファイルは、SSO データベース内の構成パラメーターの値を設定します。 コマンド ファイルの最初にローカル変数の値を設定する SET ステートメントがいくつか含まれます。 **SAPAdapterTimeout**、 **PendingTransactionsAdapterTimeout**、および**PaymentTrackingAdapterTimeout**値、スタブとアダプターのバージョンで使用されます。 他の値は、インライン バージョンで使用されます。 スタブ バージョンの場合、このファイルへの変更は不要です。  
  
5.  コマンド プロンプトで「 `SetConfigValuesInSSO.cmd`、し、enter キーを押して、SSO 構成ストア アプリケーションで値を格納します。  
  
6.  コマンド プロンプトで、次のコマンドを実行し、SSO のチケットを有効にします。  
  
    -   `ssomanage -tickets yes yes`  
  
##  <a name="step11"></a> サービス指向ソリューションの BAM 定義を展開します。  
  
#### <a name="to-deploy-the-bam-definition-for-the-service-oriented-solution"></a>サービス指向ソリューションの BAM 定義を展開するには  
  
1.  コマンド プロンプトで次のコマンドを入力し、&lt;localizedText&gt;Enter&lt;/localizedText&gt; キーを押します。 これは、BAM ユーティリティへのパスを設定します。  
  
    -   セット PATH=%PATH%;%programfiles%\Microsoft BizTalk Server\Tracking  
  
2.  コマンド プロンプトで、ディレクトリを %BTSSolutions%\SO\BTSSoln\BAM フォルダーに変更し、次のコマンドを入力して Enter キーを押します。  
  
    -   `bm deploy-all -DefinitionFile:ServiceLevelTracking.xml`  
  
        > [!NOTE]
        >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
##  <a name="step13"></a> デプロイ サービス指向ソリューション  
  
#### <a name="to-deploy-the-service-oriented-solution"></a>サービス指向ソリューションをデプロイするには  
  
1.  コマンド プロンプトを開き、ディレクトリを %BTSSolutionsPath%\SO\BTSSoln\Scripts フォルダーに変更します。  
  
2.  変更、 **DeployStubBinding.cmd** "debug"と「開発」のすべてのインスタンスを「リリース」に置き換えることによりファイル。  
  
3.  コマンド プロンプトを開き、ディレクトリを %BTSSolutionsPath%\SO\BTSSoln\Scripts フォルダーに変更します。 次のコマンドを入力し、Enter キーを押します。  
  
    -   `DeployStubBinding.cmd`  
  
4.  コマンド プロンプトで、次のコマンドを実行し、スタブ バージョンのオーケストレーションを開始します。  
  
    -   `Startstub.vbs`  
  
## <a name="next-steps"></a>次の手順  
 サービス指向ソリューションのスタブ バージョンがどのように動作するかをテストする[サービス指向ソリューションを実行する方法](../core/how-to-run-the-service-oriented-solution.md)します。  
  
## <a name="see-also"></a>参照  
 [サービス指向ソリューションをインストールする前に](../core/before-installing-the-service-oriented-solution.md)   
 [指向ソリューションのインライン バージョンおよびアダプター バージョンのサービスをインストールする方法](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md)   
 [サービス指向ソリューションに対する開発者のコンピューター設定](../core/developer-machine-setup-for-the-service-oriented-solution.md)