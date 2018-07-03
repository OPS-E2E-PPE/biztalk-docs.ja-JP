---
title: ビジネス プロセス管理ソリューションをインストールする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installing, examples
- process management solution tutorial, installing
- process management solution tutorial, deployment prerequisites
ms.assetid: 930f3bb1-05e6-4b02-852d-6139aaf341f0
caps.latest.revision: 61
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e341392e65509568e995f711abcdddd6eb39cbb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007623"
---
# <a name="how-to-install-the-business-process-management-solution"></a>ビジネス プロセス管理ソリューションのインストール方法
次の手順では、ビジネス プロセス管理 (BPM) ソリューションをコンピューターにインストールするための準備方法と、このコンピューターにソリューションをインストールする方法について説明します。  
  
-   [ビジネス プロセス管理ソリューションをインストールするコンピューターを準備します。](#step1)  
  
     準備手順では、受信ポートと送信ポートによって使用される SQL データベース、フォルダー、およびキューを作成します。 また、クライアント アプリケーションである CSRWebApp および OrderBroker プロキシ Web サービスに使用する 2 つの仮想ディレクトリを作成します。  
  
-   [ビジネス プロセス管理ソリューションをインストールするのには、コンピューターを構成します。](#step3)  
  
-   [ビジネス プロセス管理ソリューションのインストール](#step5)  
  
> [!NOTE]
>  ソリューションを展開するには、いくつかのバッチ ファイルを実行します。 スクリプトが正常終了したことを確認できるように、バッチ ファイルの出力をテキスト ファイルにリダイレクトすることをお勧めします。  
  
##  <a name="step1"></a> ビジネス プロセス管理ソリューションをインストールするコンピューターを準備します。  
  
#### <a name="to-prepare-the-computer-for-installing-the-business-process-management-solution"></a>ビジネス プロセス管理ソリューションをコンピューターにインストールするための準備を行うには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**サービス**します。 使用して、**サービス**コンソールで、次のサービスが実行されていることを確認します。  
  
    -   **FTP 発行**  
  
    -   **メッセージ キュー**  
  
    -   **World Wide Web の発行**  
  
2.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、 をクリックして**コンピュータの管理**コンソール、および追加し、ローカルの Administrators グループに BizTalk サービス アカウント。  
  
3.  Windows SharePoint Services をインストールした場合の (ルート) を除外する、**既定の Web サイト**Windows SharePoint Services 管理パスから次のようにします をクリック**開始**、 をポイント**すべてのプログラム。**、 をポイント**管理ツール**、 をクリックし、 **SharePoint Central Administration**します。  
  
    1.  **仮想サーバーの構成**、**仮想サーバー設定を構成**します。  
  
    2.  **仮想サーバーのリスト**] ページで [**既定の Web サイト**します。  
  
    3.  **仮想サーバーの設定**] ページで [**管理パスの定義**します。  
  
    4.  **インクルード パス**のセクション、**管理パスの定義**] ページで、[**ルート**順にクリックします**選択したパスの削除**します。  
  
    5.  コマンド プロンプトで IISReset コマンドを実行します。  
  
##  <a name="step3"></a> ビジネス プロセス管理ソリューションをインストールするのには、コンピューターを構成します。  
  
#### <a name="to-configure-the-computer-for-installing-the-business-process-management-solution"></a>ビジネス プロセス管理ソリューションをコンピューターにインストールするための構成を行うには  
  
1.  コンピュータからログオフして、BizTalk サービス アカウントを使用してコンピュータにログオンします。  
  
2.  コマンド プロンプトを開き、次のコマンドを入力して Enter キーを押し、%BTSSolutionsPath% 環境変数に E2E ソリューションのベース フォルダーを設定します。 次に、コマンド プロンプトを終了します。  
  
    -   `setx BTSSolutionsPath "%ProgramFiles%\Microsoft BizTalk Server 2009\SDK\Scenarios"`  
  
        > [!NOTE]
        >  64 ビット コンピューターを使用する場合は、「%ProgramFiles%」の代わりに「%ProgramFiles%(x86)」と入力してください。  
  
        > [!NOTE]
        >  SETX コマンドの詳細については、Microsoft TechNet Web サイトを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=67831](http://go.microsoft.com/fwlink/?LinkId=67831)します。  
  
3.  コマンド プロンプトを開き、現在のディレクトリを %BTSSolutionsPath%\BPM\HistoryDB フォルダーに型に変更`CreateDatabase.cmd`、履歴データベースを作成するには ENTER キーを押します。  
  
    > [!NOTE]
    >  SQL 送信アダプターのハンドラーとして指定されたホストを実行するユーザーには、SouthridgeVideoHistory データベースのストアド プロシージャを実行する権限が必要です。  
  
4.  コマンド プロンプトで次のコマンドを実行し、既定のスクリプト ホストを CScript.exe に変更します。  
  
    -   `CScript /H:CScript`  
  
5.  コマンド プロンプトで、次のコマンドを実行して、CSRWebApp Web アプリケーションを作成します。  
  
    -   `iisvdir /create "Default Web Site" CSRWebApp "%BTSSolutionsPath%\BPM\CSRWebApp"`  
  
        > [!NOTE]
        >  Iisvdir.vbs の詳細については、Microsoft TechNet Web サイトを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=67830](http://go.microsoft.com/fwlink/?LinkId=67830)します。  
  
6.  コマンド プロンプトで、次のコマンドを実行し、OrderBroker_Proxy の新しい IIS 仮想ディレクトリを作成します。  
  
    -   `iisvdir /create "Default Web Site" BTSScn.BPM.OrderBroker_Proxy "%BTSSolutionsPath%\BPM\OrderBroker_Proxy"`  
  
    > [!NOTE]
    >  Web アプリケーションは、インターネット インフォメーション サービス (IIS) マネージャーを使用して作成することができます。 IIS 7.0 でアプリケーションを作成する方法の詳細については、IIS 7.0 ドキュメントを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=59263](http://go.microsoft.com/fwlink/?LinkId=59263)します。  
  
7.  新しい IIS アプリケーション プールを作成し、次のように、BizTalk 分離ホスト ユーザー グループと IIS_WPG グループのメンバーであるユーザーとしてその id を設定します。  
  
    1.  インターネット インフォメーション サービス (IIS) マネージャーで、右クリックして**アプリケーション プール**を選択します**新規**、し、**アプリケーション プール**します。  
  
    2.  型、**アプリケーション プール ID** (任意の値)、順にクリックします**OK**します。  
  
    3.  アプリケーション プールを選択し、作成したを右クリックして**詳細設定**します。  
  
    4.  展開**プロセス モデル**、右側の列をクリックして、 **Identity**を設定して、クリックして **.**  
  
    5.  ユーザー アカウントを選択します (いずれかを**ビルトイン アカウント**または**カスタム アカウント**) を作成して、windows \temp ディレクトリにファイルを実行する権限を持っています。 BizTalk を構成した際に、BizTalk 分離ホスト ユーザー グループに追加されるユーザーに対して、これらの権限が設定されています。 したがって、望ましいのは、同じユーザーを指定することです。  
  
8.  インターネット インフォメーション サービス (IIS) マネージャーで、展開**Websites**、展開**既定の Web サイト**を右クリックして**BTSScn.BPM.OrderBroker_Proxy** をポイント**アプリケーションの管理**、 をクリックし、**詳細設定**します。  
  
9. 設定**アプリケーション プール**前の手順で作成したアプリケーション プールにします。  
  
10. 前の 2 つの手順を繰り返して、 **CSRWebApp**アプリケーション。  
  
11. これらの変更が直ちに有効になるように、IIS をリセットします。 これを行うには、次のように実行します。 **iisreset**コマンド プロンプトでします。  
  
12. コマンド プロンプトで、現在のフォルダーを %btssolutionspath%\bpm\scripts、型に変更`CreateQueues.vbs`、し、次のプライベート キューを作成するには ENTER キーを押します。  
  
    |名前|トランザクション|トランザクション プロトコル|  
    |----------|-------------------|--------------------------|  
    |ToFacilitiesQ|はい|ネイティブ|  
    |FromFacilitiesQ|はい|ネイティブ|  
    |FromFixedOrdersQ|はい|ネイティブ|  
    |ToServicingSystemQ|はい|ネイティブ|  
    |ToCSRSystemQ|いいえ|HTTP|  
    |ToVendorSystemQ|いいえ|HTTP|  
  
    > [!NOTE]
    >  使用することができます**コンピュータの管理**スナップインで、キューを作成します。 プライベート キューを作成する方法の詳細については、メッセージ キュー ドキュメントを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=59264](http://go.microsoft.com/fwlink/?LinkId=59264)します。 MSMQ 3.0 をインストールする方法の詳細については、メッセージ キュー ドキュメントを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=59265](http://go.microsoft.com/fwlink/?LinkId=59265)します。  
  
13. コマンド プロンプトで、現在のフォルダーを %btssolutionspath%\bpm\scripts、型に変更`CreateTestDirectories.cmd`、し、ENTER キーを押します。  
  
    -   次のフォルダーが %SystemDrive%\BPMTest フォルダーに作成されます。  
  
         CSRResponse-DSP  
  
         VendorResponse-DSP  
  
         OrderErrors-SP  
  
         ErrorResponse-RP-TestRL  
  
         Facilities-SP  
  
         Facilities-RP-TestRL  
  
         HistoryInsert-SP  
  
         HistoryUpdate-SP  
  
         Order-RP-TestRL  
  
         ServicingSystem-SP  
  
         Vendor-RP-TestRL  
  
         BizTalkErrors-SP  
  
    -   FromVendor フォルダーは、%SystemDrive%\Inetpub\ftproot フォルダーに作成されます。  
  
        > [!NOTE]
        >  Windows システムのインストール先が C ドライブでない場合は、%SystemDrive% を C: に置き換えてください。 フォルダー名は、BPM ソリューションが提供するバインド ファイルのアドレスに一致させる必要があります。  
  
        > [!NOTE]
        >  BizTalk サービス アカウントには、FromVendor フォルダーへの読み取り/書き込み権限が必要です。  
  
##  <a name="step5"></a> ビジネス プロセス管理ソリューションをインストールします。  
  
#### <a name="to-install-the-business-process-management-solution"></a>ビジネス プロセス管理ソリューションをインストールするには  
  
1. コマンド プロンプトで、現在のフォルダーを %btssolutionspath%\bpm、型に変更`SetupBPM.bat`、し、ENTER キーを押します。  
  
   > [!NOTE]
   >  SetupBPM.bat ファイルを実行する前に **%BTSInstallPath%/SDK/Scenarios/BPM/CSDWebApp/App_WebReferences/SouthridgeVideo_OrderBroker/OrderBrokerOrch_OrderPort.wsdl**と **%BTSInstallPath%/SDK/Scenarios/BPM/OrderBroker_Proxy/App_Code/OrderBrokerOrch_OrderPort.asmx.cs**8f8bbebbb3fb375a のすべてのインスタンスを XXXXXXXXXXXXXXXX に置き換えます。  
  
    SetupBPM.bat では、次のタスクが実行されます。  
  
   1.  BPM ソリューションのアセンブリに署名するための、一意の厳密な名前のキー (SNK) を作成します。  
  
   2.  SNK から公開キー トークンを抽出します。  
  
   3.  公開キー トークンを使用してバインド ファイルを更新します。  
  
   4.  BPM ソリューションを作成し、OpsAdapter をインストールします。  
  
   5.  %BTSSolutionsPath%\Common フォルダーに SSOApplicationConfig を作成します。  
  
2. ビジネス ルール エンジン展開ウィザードを使用して、Southridge Video ビジネス ルールを展開します。  
  
   1. クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリックします**ビジネス ルール エンジン展開ウィザード**します。  
  
      > [!NOTE]
      >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**します。  
  
   2. **へようこそ**  ページで **次**します。  
  
   3. **展開タスク**] ページで、[**インポート ポリシー/ボキャブラリをファイルからデータベースに発行し、**、順にクリックします**次**。  
  
   4. **ポリシー ストア** ページでその他のすべての設定の既定では、保持してクリックして**次**。  
  
   5. **インポート ルール エンジン ポリシー/ボキャブラリ ファイル** ページで **参照**%BTSSolutionsPath%\BPM\Rules フォルダーの DecodeAndValidateOrderRules.xml ファイルを選択し、をクリックして**次**します。  
  
   6. **準備ができて**] ページで [ **[次へ]**、し、**ポリシー/ボキャブラリのインポート**] ページで [ **[次へ]**  
  
   7. [完了] ページで、次のように選択します。**ウィザードを再度実行**をクリックしてウィザードを再度開いて**完了**。  
  
   8. **へようこそ**  ページで **次**します。  
  
   9. **展開タスク**] ページで、[ **[deploypolicy]**、順にクリックします**次**します。  
  
   10. **ポリシー ストア** ページでその他のすべての設定の既定では、保持してクリックして**次**。  
  
   11. **ポリシーの展開**] ページで、[ **DecodeAndValidateOrder 1.0**で、**ルール エンジン ポリシー**ドロップダウン リスト、およびクリック **[次へ]**.  
  
   12. **準備ができて**] ページで [ **[次へ]**、し、**ポリシーの展開**] ページで [ **[次へ]**。  
  
   13. [完了] ページで、次のようにクリックします。**完了**します。  
  
3. BPM ソリューションを 64 ビット コンピューターにインストールする場合は、次の操作を行います。  
  
   1.  次の 32 ビット コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`%SYSTEMROOT%\SYSWOW64\CMD.EXE`、し、ENTER キーを押します。  
  
   2.  32 ビット コマンド プロンプトで、ディレクトリを %BTSSolutionsPath%\BPM\Scripts フォルダーに変更します。  
  
   3.  メモ帳で CreateSouthridgeVideoApplication.cmd を開き、"%CommonProgramFiles%\Enterprise Single Sign-On\ssomanage.exe" を "%SystemDrive%\Program Files\Common Files\Enterprise Single Sign-On\ssomanage.exe" に置き換えます。  
  
       > [!NOTE]
       >  32 ビット コマンド プロンプトでは、%CommonProgramFiles% 変数が "%ProgramFiles(x86)%\Common Files" に変わります。 SSO 管理ユーティリティは 64 ビット コンピューターでも %ProgramFiles% にインストールされるので、パスを修正する必要があります。 DeployBPM.cmd は、CreateSouthridgeVideoApplication.cmd を呼び出します。  
  
   4.  32 ビット コマンド プロンプトで、入力型`DeployBPM.cmd`、し、ENTER キーを押します。  
  
       > [!NOTE]
       >  DeployBPM.cmd は、32 ビット コマンド プロンプトで実行する必要があります。cscript.exe の x86 バージョンを必要とする x86 オブジェクトにアクセスする VB スクリプトが含まれているためです。  
  
4. コマンド プロンプトで、現在のフォルダーを %btssolutionspath%\bpm\scripts、型に変更`DeployBPM.cmd`、し、ENTER キーを押します。 DeployBPM.cmd は、次のタスクを実行します。  
  
   1.  BPM ソリューションのための BizTalk アプリケーションを作成します。  
  
   2.  アプリケーション間の参照を追加します。  
  
   3.  バインド ファイルをインポートします。  
  
   4.  BAM 定義ファイルを展開します。  
  
   5.  SouthridgeVideo イベント ソースを登録します。  
  
   6.  シングル サインオン (SSO) 関連アプリケーションを作成し、SSO アプリケーションの構成値を保存します。  
  
5. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
   1.  **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、展開**BTSScn.BPM.OrderBrokerApp**、展開**受信場所**、右クリックして**ベンダー-RL RP**、し、[プロパティ] をクリックします。  
  
   2.  **プロパティ**ダイアログ ボックスで、をクリックして**構成**、として、次の表値を入力し、**トランスポートのプロパティ** ダイアログ ボックス。  
  
       |プロパティ名|値|  
       |-------------------|-----------|  
       |**[サーバー]**|`localhost`|  
       |**[ユーザー名]**|\<*BizTalk サービス アカウント名*\>|  
       |**Password**|\<*BizTalk サービス アカウントのパスワード*\>|  
  
6. BPM ソリューションを実行します。 ソリューションの実行の詳細については、次を参照してください。 [、ビジネス プロセス管理ソリューションを実行する方法](../core/how-to-run-the-business-process-management-solution.md)します。  
  
## <a name="next-steps"></a>次の手順  
 ビジネス管理ソリューションがでどのように動作するかをテストする[、ビジネス プロセス管理ソリューションを実行する方法](../core/how-to-run-the-business-process-management-solution.md)します。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションをインストールする前に](../core/before-installing-the-business-process-management-solution.md)   
 [ビジネス プロセス管理ソリューションに対する開発者のコンピューター設定](../core/developer-machine-setup-for-the-business-process-management-solution.md)