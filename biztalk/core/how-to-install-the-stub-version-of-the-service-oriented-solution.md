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
ms.openlocfilehash: 8ecb7da2662649fe9744c5a4744b50834b2b87bf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336986"
---
# <a name="how-to-install-the-stub-version-of-the-service-oriented-solution"></a>指向ソリューションのスタブ バージョンのサービスをインストールする方法
次の手順では、サービス指向ソリューションのスタブ バージョンをインストールする前に、コンピューターを準備する方法と、コンピューターにソリューションをインストールする方法について説明します。  
  
-   [サービス指向ソリューションのスタブ バージョンをインストールするコンピューターを準備します。](#step1)  
  
-   [IBM WebSphere MQ Client for Windows をインストールします。](#step3)  
  
-   [仮想ディレクトリが IIS でサービス指向ソリューションの作成します。](#step5)  
  
-   [ビルド サービス指向ソリューション](#step7)  
  
-   [SSO データベース内のエンタープライズ シングル サインオン (SSO) エントリと値を作成します。](#step9)  
  
-   [サービス指向ソリューションの BAM 定義を展開します。](#step11)  
  
-   [サービス指向ソリューションの展開](#step13)  
  
##  <a name="step1"></a> サービス指向ソリューションのスタブ バージョンをインストールするコンピューターを準備します。  
  
#### <a name="to-prepare-the-computer-for-installing-the-stub-version-of-the-service-oriented-solution"></a>サービス指向ソリューションのスタブ バージョンをインストールするため、コンピューターを準備するには  
  
1. 必ず、**既定の Web サイト**ASP.NET を使用するように構成 2.X。  
  
   1.  クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**.  
  
   2.  **インターネット インフォメーション サービス (IIS) マネージャー**、マシン名を展開**サイト**、展開**既定の Web サイト**、展開**aspnet_client**、展開 **[system_web]** します。  
  
   3.  サブフォルダーが 2.X であることを確認します。  
  
2. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**サービス**します。 使用して、**サービス**コンソールで、次のサービスが実行されていることを確認します。  
  
   -   **World Wide Web の発行**  
  
3. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、 をクリックして**コンピュータの管理**コンソール、および追加し、ローカルの Administrators グループに BizTalk サービス アカウント。  
  
4. Windows SharePoint Services をインストールした場合の (ルート) を除外する、**既定の Web サイト**Windows SharePoint Services 管理パスから次のようにします。をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**SharePoint Central Administration**。  
  
   1.  **仮想サーバーの構成**、**仮想サーバー設定を構成**します。  
  
   2.  **仮想サーバーのリスト**] ページで [**既定の Web サイト**します。  
  
   3.  **仮想サーバーの設定**] ページで [**管理パスの定義**します。  
  
   4.  **インクルード パス**のセクション、**管理パスの定義**] ページで、[**ルート**順にクリックします**選択したパスの削除**します。  
  
   5.  コマンド プロンプトで IISReset コマンドを実行します。  
  
5. コンピュータからログオフして、BizTalk サービス アカウントを使用してコンピュータにログオンします。  
  
6. コマンド プロンプトを開き、次のコマンドを入力し、enter キーを押して、%btssolutionspath% 環境変数を設定します。 次に、コマンド プロンプトを終了します。  
  
   - setx %btssolutionspath%"[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Scenarios"  
  
     > [!NOTE]
     >  64 ビット コンピューターを使用する場合は、「%ProgramFiles%」の代わりに「%ProgramFiles%(x86)」と入力してください。  
  
     > [!NOTE]
     >  SETX コマンドの詳細については、Microsoft TechNet Web サイトを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=67831](http://go.microsoft.com/fwlink/?LinkId=67831)します。  
  
##  <a name="step3"></a> IBM WebSphere MQ Client for Windows をインストールします。  
  
#### <a name="to-install-the-ibm-websphere-mq-client-for-windows"></a>IBM WebSphere MQ Client for Windows をインストールするには  
  
1. IBM WebSphere MQ Client for Windows の最新バージョンをダウンロードします。  
  
   > [!NOTE]
   >  ソリューションのスタブ バージョンで IBM WebSphere Server を必要としない場合でも、クライアント アプリケーションはインストールする必要がありますので、IBM WebSphere MQ Client for Windows、によって提供される amqmdnet.dll ファイルを参照します。 スタブ バージョンのクライアントでは、API は実際には、DLL で呼び出されません。 コンパイルして、クライアント アプリケーションの実行にのみ必要になります。 IBM Web サイトから IBM WebSphere MQ Client for Windows をダウンロードできます。  
  
2. IBM WebSphere MQ Client for Windows をインストールします。  
  
   > [!NOTE]
   >  IBM WebSphere MQ Client for Windows を構成する必要はありません。 すべての既定の設定を保持します。  
  
3. グローバル アセンブリ キャッシュ (GAC) に .NET アセンブリの WebSphere MQ クラスを追加します。  
  
   1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプトでディレクトリに移動\<IBM MQSeries インストール ディレクトリ\>\bin です。  
  
   2. 次のコマンドを実行します (gacutil.exe が path 環境ことを確認してください)。  
  
       `gacutil.exe /i amqmdnet.dll`  
  
##  <a name="step5"></a> 仮想ディレクトリが IIS でサービス指向ソリューションの作成します。  
  
#### <a name="to-create-the-virtual-directories-in-iis-for-the-service-oriented-solution"></a>サービス指向ソリューションの IIS を仮想ディレクトリを作成するには  
  
1.  **インターネット インフォメーション サービス (IIS) マネージャー**を右クリックして**アプリケーション プール**、**アプリケーション プールの追加**します。  
  
     **アプリケーション プールの追加**ダイアログ ボックスに「`SSOStubAppPool`で、**名前**テキスト ボックス、およびクリック**ok**します。  
  
     スタブ バージョンのオーケストレーション、スタブ SAP Web サービス、スタブ Payment Tracker Web サービス、およびスタブ Pending Transaction Web サービスのサービス指向ソリューションで使用が公開された Web が含まれている仮想ディレクトリ サービスします。  
  
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
  
         PATH = \<BizTalk Install Directory\>\SDK\Scenarios\SO\BTSSoln\OrchProxy\Stub  
  
         Access Permissions = Read, Run scripts  
  
    2.  使用して、**仮想ディレクトリの作成ウィザード**、アダプター バージョンの Web サービス プロキシの次の仮想ディレクトリを作成します。  
  
         Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP  
  
         PATH = \<BizTalk Install Directory\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\SAP  
  
         Access Permissions = Read, Run scripts  
  
    3.  使用して、**仮想ディレクトリの作成ウィザード**、アダプター バージョンの Web サービス プロキシの次の仮想ディレクトリを作成します。  
  
         Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions  
  
         PATH = \<BizTalk Install Directory\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PendingTrans  
  
         Access Permissions = Read, Run scripts  
  
    4.  使用して、**仮想ディレクトリの作成ウィザード**、アダプター バージョンの Web サービス プロキシの次の仮想ディレクトリを作成します。  
  
         エイリアス Microsoft.Samples.BizTalk.WoodgroveBank.StubPaymentTracker を =  
  
         PATH = \<BizTalk Install Directory\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PaymentTrack  
  
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
  
2. Visual Studio コマンド プロンプトでディレクトリを %BTSSolutionsPath%\SO\BTSSoln フォルダーに変更し、サービス指向ソリューションのスタブ バージョンをビルドする次のコマンドを実行します。  
  
   -   `SetupBTSSoln.bat`  
  
   > [!NOTE]
   >  以下のファイルで、17f20caea2afcc8c のすべてのインスタンスを現在の公開キー トークンに置き換えます。  
   > 
   > - %BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\Aggregate_To_CustomerServiceResponse.btm.cs  
   >   -   %BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\Aggregate_To_ErrorResponse.btm.cs  
   >   -   %BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_CreditLimitResponse.btm.cs  
   >   -   %BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_CustomerServiceResponseDenied.btm.cs  
   >   -   %BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_LastPaymentResponseTimeout.btm.cs  
   >   -   %BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_PendingTransactionResponse.btm.cs  
  
##  <a name="step9"></a> SSO データベース内のエンタープライズ シングル サインオン (SSO) エントリと値を作成します。  
  
#### <a name="to-create-the-enterprise-single-sign-on-sso-entries-and-values-in-the-sso-database"></a>SSO データベースで、エンタープライズ シングル サインオン (SSO) エントリと値を作成するには  
  
1.  コマンド プロンプトを開き、BTSSolutionsPath%\SO\BTSSoln\Scripts % に現在のディレクトリを変更し、エンタープライズ シングル サインオン フォルダーのパスの環境を設定するのには、次のコマンドを実行します。  
  
    -   `Set PATH=%PATH%;%ProgramFiles%\"Common Files\Enterprise Single Sign-On"`  
  
2.  コマンド プロンプトでディレクトリを %BTSSolutionsPath%\SO\BTSSoln\Scripts フォルダーに変更を開いて、メモ帳で ConfigStoreApp.xml ファイルの内容を確認します。  
  
    > [!NOTE]
    >  このファイルは、構成パラメーターを格納するシナリオを使用して sso 構成ストアのアプリケーションを定義します。 一部の構成パラメーターを含める、**タイムアウト**(のすべての 3 つのバージョン) SAP との通信に使用される値。 このファイルへの変更は、不要です。  
  
3.  コマンド プロンプトで、SSO 構成ストア アプリケーションを作成するには、次のコマンドを実行します。  
  
    -   `ssomanage -createapps ConfigStoreApp.xml`  
  
4.  コマンド プロンプトで メモ帳を使用して SetConfigValuesInSSO.cmd を開き、ファイルの内容を確認  
  
    > [!NOTE]
    >  このコマンド ファイルは、SSO データベース内の構成パラメーターの値を設定します。 コマンド ファイルの先頭で、ローカル変数に値を設定するいくつかの set ステートメントが含まれています。 **SAPAdapterTimeout**、 **PendingTransactionsAdapterTimeout**、および**PaymentTrackingAdapterTimeout**値、スタブとアダプターのバージョンで使用されます。 他の値は、インライン バージョンで使用されます。 このファイルに対する変更は、スタブ バージョンの場合ではありません。  
  
5.  コマンド プロンプトで「 `SetConfigValuesInSSO.cmd`、し、enter キーを押して、SSO 構成ストア アプリケーションで値を格納します。  
  
6.  コマンド プロンプトで、SSO のチケットを有効にするのには、次のコマンドを実行します。  
  
    -   `ssomanage -tickets yes yes`  
  
##  <a name="step11"></a> サービス指向ソリューションの BAM 定義を展開します。  
  
#### <a name="to-deploy-the-bam-definition-for-the-service-oriented-solution"></a>サービス指向ソリューションの BAM 定義を展開するには  
  
1.  コマンド プロンプトで次のコマンドを入力し、ENTER キーを押します。 これは、BAM ユーティリティへのパスを設定します。  
  
    -   SET PATH=%PATH%;%programfiles%\Microsoft BizTalk Server\Tracking  
  
2.  コマンド プロンプトで %BTSSolutionsPath%\SO\BTSSoln\BAM フォルダーにディレクトリを変更して、次のコマンドを入力し、ENTER キーを押します。  
  
    -   `bm deploy-all -DefinitionFile:ServiceLevelTracking.xml`  
  
        > [!NOTE]
        >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
##  <a name="step13"></a> デプロイ サービス指向ソリューション  
  
#### <a name="to-deploy-the-service-oriented-solution"></a>サービス指向ソリューションをデプロイするには  
  
1.  コマンド プロンプトを開き、ディレクトリを %BTSSolutionsPath%\SO\BTSSoln\Scripts フォルダーに変更します。  
  
2.  変更、 **DeployStubBinding.cmd** "debug"と「開発」のすべてのインスタンスを「リリース」に置き換えることによりファイル。  
  
3.  コマンド プロンプトを開き、ディレクトリを %BTSSolutionsPath%\SO\BTSSoln\Scripts フォルダーに変更します。 次のコマンドを入力し、Enter キーを押します。  
  
    -   `DeployStubBinding.cmd`  
  
4.  コマンド プロンプトでは、スタブ バージョン用のオーケストレーションを開始するには、次のコマンドを実行します  
  
    -   `Startstub.vbs`  
  
## <a name="next-steps"></a>次の手順  
 サービス指向ソリューションのスタブ バージョンがどのように動作するかをテストする[サービス指向ソリューションを実行する方法](../core/how-to-run-the-service-oriented-solution.md)します。  
  
## <a name="see-also"></a>参照  
 [サービス指向ソリューションをインストールする前に](../core/before-installing-the-service-oriented-solution.md)   
 [指向ソリューションのインライン バージョンおよびアダプター バージョンのサービスをインストールする方法](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md)   
 [サービス指向ソリューションに対する開発者のコンピューター設定](../core/developer-machine-setup-for-the-service-oriented-solution.md)