---
title: インラインをインストールし、アダプター バージョンのサービス指向ソリューション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6050cfe9-4e94-4a55-8b24-fbcc74d9e8f4
caps.latest.revision: 97
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fdbdb61d37f6828f6e738d438fe9087acbc4d26c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019543"
---
# <a name="how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution"></a>サービス指向ソリューションのインライン バージョンおよびアダプター バージョンをインストールする方法
次の手順では、サービス指向ソリューションのインライン バージョンおよびアダプタ バージョンをコンピュータにインストールするための準備を行う方法、およびコンピュータにソリューションをインストールする方法について説明します。  

> [!NOTE]
>  - サービス指向ソリューションはフォルダーにある\< *BizTalk Server のインストール フォルダー*\>\SDK\Scenarios\SO です。  
>  - このソリューションに対応するメインフレームがない場合、ポートのバインドを変更して、Pending Transactions のスタブ Web サービスを使用できます。 メインフレームのトランザクションをエミュレートするため、Web サービスは、ローカルにトランザクションを生成します。  

##  <a name="step1"></a> サービス指向ソリューションのアダプターとインライン バージョンをインストールするコンピューターを準備します。  

1. Windows SharePoint Services をインストールした場合を除外する (ルート) の既定の Web サイトの Windows SharePoint Services 管理パスから次のようにします をクリック**開始**、 をポイント**すべてのプログラム**、 をポイント。**管理ツール**、 をクリックし、 **SharePoint Central Administration**します。  

   1.  **仮想サーバーの構成**、**仮想サーバー設定を構成**します。  

   2.  **仮想サーバーのリスト**] ページで [**既定の Web サイト**します。  

   3.  **仮想サーバーの設定**] ページで [**管理パスの定義**します。  

   4.  **インクルード パス**のセクション、**管理パスの定義**] ページで、[**ルート**順にクリックします**選択したパスの削除**します。  

   5.  コマンド プロンプトで IISReset コマンドを実行します。  

2. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、 をクリックして**コンピュータの管理**コンソール、および追加し、ローカルの Administrators グループに BizTalk サービス アカウント。  

3. コンピュータからログオフして、BizTalk サービス アカウントを使用してコンピュータにログオンします。  

4. コマンド プロンプトで、次のコマンドを入力し、&lt;localizedText&gt;Enter&lt;/localizedText&gt; キーを押して、%BTSSolutionsPath% 環境変数を設定します。 次に、コマンド プロンプトを終了します。  

   - setx BTSSolutionsPath [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Scenarios"  

     > [!NOTE]
     >  64 ビット コンピューターを使用する場合は、「%ProgramFiles%」の代わりに「%ProgramFiles%(x86)」と入力してください。  

     > [!NOTE]
     >  SETX コマンドの詳細については、Microsoft TechNet Web サイトを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=67831](http://go.microsoft.com/fwlink/?LinkId=67831)します。  

##  <a name="step3"></a> サービス指向ソリューションのスタブ バージョンを削除します。  

1. オープン、 **BizTalk Server 管理コンソール**次のように: クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリックします**BizTalk Server 管理**します。  

2. **BizTalk Server 管理コンソール**、展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、右クリック**btsscn.so.customerservice**、 をクリックし、**停止**します。 **アプリケーションを停止**ダイアログ ボックスで、**完全停止 - インスタンスを終了**、 をクリックし、**停止**します。  

   > [!NOTE]
   >  インライン バージョンおよびアダプター バージョンをインストールするために、スタブ バージョンを削除する必要はありません。 すべてのバージョンを一緒に配置する場合は、この手順を省略できます。  

3. コマンド プロンプトを開いて次のコマンドを入力し、&lt;localizedText&gt;Enter&lt;/localizedText&gt; キーを押します。 このコマンドは、既定のスクリプト ホストを CScript.exe に変更します。  

   -   `cscript /H:CScript`  

4. コマンド プロンプトで、現在のディレクトリを %BTSSolutonsPath%\SO\BTSSoln\Scripts フォルダーに変更し、次のコマンドを入力して &lt;localizedText&gt;Enter&lt;/localizedText&gt; キーを押します。  

   -   `UnEnlistStub.vbs`  

5. コマンド プロンプトで次のコマンドを入力し、ENTER キーを押します。  

   -   `UndeployStub.vbs`  

6. コマンド プロンプトで、次のコマンドを実行します。  

    SET PATH=%PATH%;[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking"  

    これで、BAM ユーティリティを参照するためのパスが設定されます。  

   > [!NOTE]
   >  64 ビット コンピューターを使用している場合は、入力`%ProgramFiles(x86)%`の代わりに`%ProgramFiles%`します。  

7. コマンド プロンプトで、ディレクトリを %BTSSolutionsPath%\SO\BTSSoln\BAM フォルダーに変更し、次のコマンドを実行します。  

   -   `bm remove-all -DefinitionFile:ServiceLevelTracking.xml`  

8. コマンド プロンプトでディレクトリを変更する\<*エンタープライズ シングル サインオンのインストール ディレクトリ*\>、し、次のコマンドを実行します。  

   -   `ssomanage -tickets no no`  

9. コマンド プロンプトで次のコマンドを実行し、WoodgroveBank.CustomerService SSO 関連アプリケーションを削除します。  

    -   `ssomanage -deleteapp WoodgroveBank.CustomerService`  

10. コマンド プロンプトで次のコマンドを実行し、スタブ バージョンで使用される Web サイトを削除します。 Iisvdir.vbs の詳細については、Microsoft TechNet Web サイトを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=67830](http://go.microsoft.com/fwlink/?LinkId=67830)します。  

    -   `iisvdir /delete W3SVC/1/ROOT/Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub`  

    -   `iisvdir /delete W3SVC/1/ROOT/Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP`  

    -   `iisvdir /delete W3SVC/1/ROOT/Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions`  

    -   `iisvdir /delete W3SVC/1/ROOT/Microsoft.Samples.BizTalk.WoodgroveBank.StubPaymentTracker`  

11. 次のようにインターネット インフォメーション サービス (IIS) マネージャーを起動: をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**をクリックして**インターネット インフォメーション サービス (IIS) マネージャー**します。  

    -   展開、**アプリケーション プール**、以前の Web アプリケーション用に作成したアプリケーション プールを右クリックし、をクリックして**削除**、順にクリックします**OK**確認でダイアログ ボックス。  

12. をクリックして**開始**、 をポイント**コントロール パネル**、 をクリックして**プログラム追加と削除**、IBM WebSphere MQ Client for Windows をアンインストールします。  

13. 開始**Visual Studio コマンド プロンプト**し、スタブ バージョン用にインストールした amqmdnet.dll を削除するのには、次のコマンドを実行します。  

    -   `gacutil /u amqmdnet`  

##  <a name="step5"></a> アクセスするサービス指向ソリューションのバックエンド システムを準備します。  

1. ローカル コンピューターの Windows Server 用の IBM WebSphere MQ をインストールします。  

   1.  すべての設定を既定のままにします。 セットアップ、**構成の既定の**の最後に、 **WebSphere MQ のウィザードの準備**します。 キュー マネージャーは qm _ という\<*コンピューター名*\>します。  

   2.  フィックス パック 10 (CSD10) をインストールします。 すべての設定を既定のままにします。  

2. MQSeries エージェントをインストールします。  

   1.  BizTalk Server のセットアップ プログラムを再実行します。  

   2.  **プログラムのメンテナンス**] ページで、[**変更**、順にクリックします**次**します。  

   3.  **コンポーネントのインストール** ページで、展開、**追加ソフトウェア**ノードをクリックして**MQSeries エージェント**します。  

   4.  **完了**ことを確認します ページで、 **BizTalk MQSeries エージェント構成のウィザードを起動**が選択されていません。  

   > [!NOTE]
   >  **MQSeries エージェント**for Windows がインストールされているチェック ボックスが、IBM WebSphere MQ の後にのみアクティブ化します。  

3. 開く、 **Visual Studio コマンド プロンプト**、ディレクトリに移動、 \< *IBM MQSeries インストール ディレクトリ*\>\bin フォルダー、および次のコマンドを実行します。  

   -   `gacutil /i amqmdnet.dll`  

4. メインフレームにアクセスするために Microsoft Host Integration Server 2004 をインストールする場合、Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] をインストールします。 セットアップ プログラムでの**オプション**] ページで、[ **Visual c# .NET**、し、その他のコンポーネントのチェック ボックスをオフします。 以外のコンポーネントをインストールする必要はありませんが、 **Visual c# .NET**します。  

   > [!NOTE]
   >  Host Integration Server 2004 の TI デザイナーを使用する場合、[!INCLUDE[btsVStudioNet2003](../includes/btsvstudionet2003-md.md)] が必要です。  

5. インストールし、メインフレームにアクセスする必要がある場合は、Microsoft Host Integration Server 2004 を構成します。 すべての設定を既定のままにします。  

#### <a name="create-the-mqseries-queues"></a>MQSeries キューを作成します。  

1.  WebSphere MQ エクスプ ローラーを開き、展開**キュー マネージャー**、キューを作成するキュー マネージャーを展開します。 通常、キュー マネージャーはという名前が qm _\<*コンピューター名*\>します。  

2.  WebSphere MQ エクスプ ローラーで右クリックして**キュー**、 をポイント**新規**、 をクリックして**ローカル キュー**のアダプター バージョン用の次のローカル キューを作成し、解決方法:  

    -   AdapterSOAInputQueue  

    -   AdapterSOAOutputQueue  

    > [!NOTE]
    >  キューでは MQSeries クラスターを共有できますが、これは必須ではありません。  

    > [!NOTE]
    >  MQSeries キュー マネージャーの名前およびキューの名前では、大文字と小文字が区別されます。  

3.  前のステップを繰り返して、インライン バージョン用の次のローカル キューを作成します。  

    -   InlineSOAOutputQueue  

    -   InlineSOAInputQueue  

4.  前のステップを繰り返して、Payment Tracker シミュレーター用の次のローカル キューを作成します  (Payment Tracker シミュレーターはアダプター バージョンおよびインライン バージョンの両方で使用されます)。  

    -   LastPaymentsInputQueue  

    -   LastPaymentsOutputQueue  

#### <a name="complete-configuration-of-the-mqseries-adapter"></a>MQSeries アダプターの構成を完了  

1. クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk MQSeries エージェント構成ウィザード**します。  

2. **へようこそ**  ページで **次**します。  

3. **アプリケーション Id** ] ページで、[**このユーザー**、ユーザー名とパスワードを入力します。 MQSeries エージェントの COM+ アプリケーションは、このユーザー アカウントで実行されます。 このチュートリアルでは、BizTalk サービスが使用するユーザー アカウントとして同じものを使用します。 ない場合、ユーザー アカウントに、MQSeries アダプターをホストする BizTalk サービスを追加する必要があります、 **CreatorOwner** COM + アプリケーションの役割。  

4. をクリックして**はい**上、 **MQSConfigWiz**  ダイアログ ボックスで、前の手順で入力したユーザー アカウントに管理者特権が求められた場合。  

5. **ロールの名前**] ページで [**次**します。  

6. **MQSAgent COM + アプリケーションを作成する**] ページで [ **[次へ]**、順にクリックします**完了**で、**完了**ページ。  

#### <a name="configure-the-mainframe-cics-application"></a>メインフレームの CICS アプリケーションを構成します。  

1.  メモ帳を使用して %BTSSolutionsPath%\SO\MFAccess\HISTIComponent フォルダーの bizcbl.txt とその "コピー ブック" (MainFrameProgramVTCS2Description.txt) を開き、内容を確認します。  

    -   bizcbl.txt には、アカウント番号入力からランダム アカウント ステートメントを返す COBOL プロシージャが記述されています。  

    -   MainFrameProgramVTCS2Descriptoin.txt には、入出力データ情報を記述する COMMAREA が記述されています。 COMMAREA は、呼び出し元プログラムと呼び出し先プログラムの間でデータをやり取りするために使用する連続したメモリ ブロックです。  

    > [!NOTE]
    >  TI デザイナー プラグインを使用した Visual Studio を使用してトランザクション インテグレーター (TI) メタデータ ファイルを生成するのにコピー ブックを使用することもできます。  

    > [!NOTE]
    >  以降のステップは正常な配置を行うために非常に重要な操作ですが、一般的には BizTalk Server 開発者は行いません。 メインフレームの担当者に依頼して、メインフレーム環境を適切に構成する必要があります。 このチュートリアルで必要なソフトウェアは、一般的にほとんどのメインフレーム環境にインストールされています。 最小のメインフレーム オペレーティング システムの環境の詳細については、Host Integration Server のマニュアルを参照してください。  

2.  FTP などを使用して、ホストに COBOL コードをコピーします。  

3.  COBOL コードとコピー ブックをコンパイルします。 次のコードは、COBOL コンパイラ用のジョブ制御言語 (JCL) のサンプルです。  

    ```  
    //COB      EXEC PGM=IGYCRCTL,  
    //            PARM=&COBPARM,  
    //            REGION=&REG  
    //STEPLIB  DD DSN=&COMPINDX..SIGYCOMP,DISP=SHR  
    //SYSLIB   DD DSN=&INDEX..SDFHCOB,DISP=SHR  
    //         DD DSN=&INDEX..SDFHMAC,DISP=SHR  
    //         DD DSN=&HLQ..&COMP..COBCOPY,DISP=SHR  
    //SYSPRINT DD SYSOUT=&OUTC  
    //*SYSPRINT DD DSN=&&INPUT,DISP=(,PASS),UNIT=SYSDA,  
    //*         SPACE=(TRK,(100,50)),  
    //*         DCB=(DSORG=PS,LRECL=121,BLKSIZE=2420,RECFM=FBA)  
    //SYSIN    DD DSN=&&SYSCIN,DISP=(OLD,DELETE)  
    //SYSLIN   DD DSN=&&LOADSET,  
    //            DISP=(MOD,PASS),  
    //            UNIT=&WORK,  
    //            SPACE=(80,(250,100))  
    //SYSUT1   DD UNIT=&WORK,SPACE=(460,(350,150))  
    //SYSUT2   DD UNIT=&WORK,SPACE=(460,(350,150))  
    //SYSUT3   DD UNIT=&WORK,SPACE=(460,(350,150))  
    //SYSUT4   DD UNIT=&WORK,SPACE=(460,(350,150))  
    //SYSUT5   DD UNIT=&WORK,SPACE=(460,(350,150))  
    //SYSUT6   DD UNIT=&WORK,SPACE=(460,(350,150))  
    //SYSUT7   DD UNIT=&WORK,SPACE=(460,(350,150))  
    ```  

4.  コンパイルしたソースをリンク編集して、実行可能ファイルを作成します。 次のコードは、COBOL リンク編集用の JCL のサンプルです。  

    ```  
    //LKED     EXEC PGM=IEWL,REGION=&REG,  
    //            PARM=&LNKPARM,COND=(5,LT,COB)  
    //SYSLIB   DD DSN=&INDEX..SDFHLOAD,DISP=SHR  
    //         DD DSN=CEE.SCEELKED,DISP=SHR  
    //         DD DSN=&TCPINDX..SEZATCP,DISP=SHR  
    //SYSLMOD  DD DSN=&LMINDX..&COMP..LOADLIB,DISP=SHR  
    //SYSUT1   DD UNIT=&WORK,  
    //            DCB=BLKSIZE=1024,  
    //            SPACE=(1024,(200,20))  
    //SYSPRINT DD SYSOUT=&OUTC  
    //SYSLIN   DD DSN=&&LOADSET,DISP=(OLD,DELETE)  
    //         DD DSN=&&COPYLINK,DISP=(OLD,DELETE)  
    ```  

5.  CICS メインフレーム アプリケーションを構成します。  

    -   このステップでは、メインフレーム システム プログラマまたは CICS 開発者が TCPIPSERVICE、セッション、接続、トランザクション、およびプログラム リソース定義をインストールする必要があります。  

    -   メインフレーム管理者に、IP アドレス、ポート番号、およびアクセス可能なプログラムへのリンク名を問い合わせてください。  

        > [!NOTE]
        >  このチュートリアルは、メインフレームで CICS アプリケーションを使用し、トランザクション用のプログラミング モデルが TCP/IP (Enhanced Listener Mode (ELM) リンク) であることを前提としています。  

##  <a name="step7"></a> セキュリティで保護されたソケット レイヤー (SSL) の Web サーバーを構成します。  

#### <a name="install-certificate-services"></a>証明書サービスをインストールします。  

1.  クリックして**開始**、] をポイント**コントロール パネルの [**、順にクリックします**プログラム追加と削除**します。  

2.  **プログラム追加と削除**ダイアログ ボックスで、をクリックして**Windows コンポーネントの追加/削除**します。  

3.  **Windows コンポーネント ウィザード**を選択します、**証明書サービス**、 をクリックして**次へ**、次の画面に表示される手順については、インストールを完了します。  

#### <a name="create-a-certificate-request"></a>証明書の要求を作成します。  

1.  **インターネット インフォメーション サービス (IIS) マネージャー**、展開**Websites**を右クリックし、**既定の Web サイト**、 をクリックして**プロパティ**、をクリックして、**ディレクトリ セキュリティ**タブをクリックし、をクリックし、**サーバー証明書**します。  

2.  **ようこそ**のページ、 **Web サーバー証明書ウィザード**、 をクリックして**次**。  

3.  **サービス証明書**] ページで、[**新しい証明書を作成**、順にクリックします**次**します。  

4.  **証明書の要求**] ページで [**要求を次に、準備しますが、後で送信**、順にクリックします**次**。  

5.  **名とセキュリティ設定** ページで、すべての設定の既定では、保持してクリックして**次へ**します。  

6.  **組織情報**ページで、会社の組織と組織単位の名前を入力し、クリックして **[次へ]** します。  

7.  **サイトの一般名** ページで、コンピューター名を入力、**共通名**ボックスをクリックして**次**。  

8.  **地理情報** ページで、地理的な情報を入力してをクリックし、**次**します。  

9. **証明書要求ファイル名**ページで、入力`c:\certreq.txt`で、**ファイル名**ボックスをクリックして**次**。  

10. **要求ファイルの概要**] ページで [ **[次へ]**、順にクリックします**完了**上、**完了**ページ。  

#### <a name="submit-the-certificate-request-to-the-certification-authority"></a>証明機関に証明書の要求を送信します。  

1.  Internet explorer のアドレス ボックスに入力`http://localhost/certsrvt`、し、ENTER キーを押します。  

2.  **ようこそ**] ページで [**証明書を要求**、順にクリックします**高度な証明書の要求**で、**証明書を要求**ページです。  

3.  **証明書要求の高度な**] ページで [ **base64 を使用して証明書要求を PKCS #10 ファイルまたは base64 でエンコードされた PKCS #7 ファイルを使用して更新の要求をエンコードされた送信**。  

4.  "証明書の要求を作成するには"に貼り付ける手順で作成した c:\certreq.txt からすべてのテキストをコピー、**保存要求**ボックスに、**証明書の要求または更新の要求を送信**クリックして、ページの**送信**します。  

#### <a name="issue-a-certificate-using-certification-authority-management-tool"></a>証明機関管理ツールを使用して証明書を発行します。  

1.  クリックして**開始**、 をポイント**管理ツール**、順にクリックします**証明機関**します。  

2.  **証明機関**コンソールで、証明機関の名前を展開し、展開、**保留中の要求**、前の手順では、ポイントに送信した証明書の要求を右クリックして**すべてのタスク**、 をクリックし、**問題**します。  

3.  閉じる、**証明機関**コンソール。  

#### <a name="download-the-certificate-to-the-web-server"></a>Web サーバー証明書をダウンロードします。  

1.  Internet explorer のアドレス ボックスに入力`http://localhost/certsrvt`、し、ENTER キーを押します。  

2.  **ようこそ**] ページで [**保留中の証明書の要求の状態を表示**します。  

3.  **保留中の証明書要求の状態を表示**] ページで、証明書を [**要求**「証明書要求を作成するには」の手順で作成しました。  

4.  **証明書は発行**ページで、エンコード方式のいずれかを選択し、クリックして**証明書のダウンロード**します。  

5.  **セキュリティ警告**ダイアログ ボックスで、をクリックして**保存**、し、証明書を c:\certnew.cer として保存します。  

#### <a name="install-the-certificate-to-the-web-server"></a>Web サーバーに証明書をインストールします。  

1.  **インターネット インフォメーション サービス (IIS) マネージャー**、展開**Websites**を右クリックし、**既定の Web サイト**証明書の要求を作成する元のしクリックして**プロパティ**します。  

2.  **プロパティ**ダイアログ ボックスで、をクリックして、**ディレクトリ セキュリティ** タブをクリックして**サーバー証明書**します。  

3.  **ようこそ**のページ、 **Web サーバー証明書ウィザード**、 をクリックして**次**。  

4.  **保留中の証明書要求**] ページで、[**保留中の要求を処理し、証明書をインストール**、順にクリックします**次**します。  

5.  **保留中の要求を処理**ページで、入力`c:\certnew.cer`で、**パスとファイル名**テキスト ボックス、およびクリック **[次へ]** します。  

6.  をクリックして **[次へ]** で、 **SSL ポート**] ページで [ **[次へ]** 上、**証明書の概要**ページをクリックして **[完了]** 上、**確認**ページ。  

    > [!NOTE]
    >  このチュートリアルでは、証明書サービスと Web サーバーの両方を同じコンピューターにインストールするため、ローカル コンピューターの信頼されたルート証明機関のストアにサーバー証明書をインストールする必要はありません。  

##  <a name="step9"></a> バックエンド システム用の Web サービスを作成します。  

1.  **インターネット インフォメーション サービス (IIS) マネージャー**、右クリックして**アプリケーション プール**を選択します**新規**、し、 **のアプリケーションプール**.  

    > [!NOTE]
    >  サービス指向ソリューションでは、この Web サービスを使用してメインフレームにアクセスします。  

2.  **新しいアプリケーション プールの追加** ダイアログ ボックスに、入力、**アプリケーション プール ID** (任意の値)、順にクリックします**OK**。  

3.  **インターネット インフォメーション サービス (IIS) マネージャー**作成したアプリケーション プールを右クリックし、**プロパティ**します。  

4.  **プロパティ** ページで、をクリックして、 **Identity**  タブで **構成可能**、入力、**ユーザー名**と**パスワード**、 をクリックし、 **OK**します。 このチュートリアルでは、BizTalk サービスが使用するユーザー アカウントとして同じものを使用します。  

#### <a name="create-the-pendingtransactions-web-service-for-runtime"></a>ランタイム用の PendingTransactions Web サービスを作成します。  

1.  **インターネット インフォメーション サービス (IIS) マネージャー**、展開**Websites**を右クリックし、**既定の Web サイト**、 をポイント**新規**とクリックして**仮想ディレクトリ**を実行する**仮想ディレクトリの作成ウィザード**します。  

     使用して、**仮想ディレクトリの作成ウィザード**、スタブ SAP Web サービスの次の仮想ディレクトリを作成します。  

     Alias = Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactions  

     PATH = \<*BizTalk Install Directory*\>\SDK\Scenarios\SO\MFAccess\PendingTransactions  

     Access Permissions = Read, Run scripts  

2.  **インターネット インフォメーション サービス (IIS) マネージャー**、展開**Websites**、展開、**既定の Web サイト**、右クリッククリックして、Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactions**プロパティ**します。  

    1.  **ディレクトリ セキュリティ**] タブで [**編集**を変更する**認証とアクセス制御**します。 選択**基本認証 (パスワードはクリア テキストで送信)**、他をオフにし**認証アクセス**チェック ボックスをオンします。 をクリックして**OK**を閉じる、**認証方法** ダイアログ ボックス。  

    2.  **ディレクトリ セキュリティ** タブで **編集**下、**セキュリティで保護された通信**ボックスで、グループ化し、確認**セキュリティで保護されたチャネル (SSL)** で、**セキュリティ保護された通信** ダイアログ ボックス。  

    3.  **仮想ディレクトリ**タブで、設定、**アプリケーション プール**「Pending Transaction Web サービスの新しい IIS アプリケーション プールを作成するには」の手順で作成したアプリケーション プールにします。  

#### <a name="create-the-pendingtransactions-web-service-for-development-environment"></a>開発環境用の PendingTransactions Web サービスを作成します。  

1. **インターネット インフォメーション サービス (IIS) マネージャー**、展開**Websites**を右クリックし、**既定の Web サイト**、 をポイント**新規**とクリックして**仮想ディレクトリ**を実行する**仮想ディレクトリの作成ウィザード**します。  

    使用して、**仮想ディレクトリの作成ウィザード**、スタブ SAP Web サービスの次の仮想ディレクトリを作成します。  

    Alias = PendingTransactions  

    PATH = \<*BizTalk Install Directory*\>\SDK\Scenarios\SO\MFAccess\PendingTransactions  

    Access Permissions = Read, Run scripts  

2. **インターネット インフォメーション サービス (IIS) マネージャー**、展開**Websites**、展開、**既定の Web サイト**PendingTransactions を右クリックし、をクリックして**プロパティ**します。  

   1. **ディレクトリ セキュリティ**] タブで [**編集**を変更する**認証とアクセス制御**します。 選択**への匿名アクセスを有効にする**します。 クリックして**OK**を終了します。  

      > [!NOTE]
      >  開発環境用の PendingTransactions Web アプリケーションは [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で使用します。 この Web アプリケーションは実稼働環境では不要です。  

   2. **仮想ディレクトリ**タブで、設定、**アプリケーション プール**「Pending Transaction Web サービスの新しい IIS アプリケーション プールを作成するには」の手順で作成したアプリケーション プールにします。  

#### <a name="create-the-stub-sap-web-service"></a>スタブ SAP Web サービスを作成します。  

1.  **インターネット インフォメーション サービス (IIS) マネージャー**、展開**Websites**を右クリックし、**既定の Web サイト**、 をポイント**新規**とクリックして**仮想ディレクトリ**を実行する**仮想ディレクトリの作成ウィザード**します。  

     使用して、**仮想ディレクトリの作成ウィザード**、スタブ SAP Web サービスの次の仮想ディレクトリを作成します。  

     Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP  

     PATH = \<*BizTalk Install Directory*\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\SAP  

     Access Permissions = Read, Run scripts  

2.  **インターネット インフォメーション サービス (IIS) マネージャー**、展開**Websites**、展開、**既定の Web サイト**、右クリックMicrosoft.Samples.BizTalk.WoodgroveBank.StubSAP、 をクリックして**プロパティ**、し、次のように設定を変更します。  

    1.  **仮想ディレクトリ**タブで、設定、**アプリケーション プール**に\< *YourAppPool* \>新しい IIS を作成するには」の手順で作成しました。アプリケーション プールを Pending Transaction Web サービス"。  

    2.  **ディレクトリ セキュリティ** タブで **編集**で、**認証とアクセス制御**ボックスで、グループ化し、 **への匿名アクセスを有効にします。**. クリックして**OK**を終了します。  

##  <a name="step11"></a> サービス指向ソリューション用の TI コンポーネントを作成します。  

#### <a name="create-a-com-application-for-the-ti-component"></a>TI コンポーネントの COM + アプリケーションを作成します。  

1.  コマンド プロンプトで %systemroot%\system32\com\comexp.msc を実行します。  

2.  **コンポーネント サービス**コンソールで、**コンポーネント サービス**、展開**コンピューター**、展開**マイ コンピューター**を右クリックして**COM + アプリケーション**、 をポイント**新規**、 をクリックし、**アプリケーション**します。  

    1.  **へようこそ**  ページで  **次へ**、順にクリックします**空のアプリケーションを作成**上、**インストールまたは新しいアプリケーションを作成**ページ。  

    2.  型`BTSScn SO TI Component`で、**新しいアプリケーションの名前を入力**ボックスで、**サーバー アプリケーション**として**ライセンス認証の種類**、 をクリックし、 **次へ**.  

    3.  **アカウント**のグループ ボックス、**アプリケーション Id の設定**] ページで、[**このユーザー**、ユーザー名とパスワードを入力し、**ユーザー**と**パスワード**ボックス。 作成する COM+ アプリケーションは、このユーザー アカウントで実行されます。 このユーザー アカウントは、ローカルの HIS Runtime Users グループのメンバーである必要があります。 このチュートリアルでは、BizTalk サービスが使用するユーザー アカウントとして同じものを使用します。  

    4.  **アプリケーション ロールの追加**] ページで [**次**します。  

    5.  **ロールにユーザーの追加** ページで、展開**CreatorOwner**、 をクリックして**ユーザー**、順にクリックします**追加**します。  

    6.  **[ユーザーまたはグループ**] ダイアログ ボックスで、メインフレームにアクセスするために使用されるユーザー アカウントを選択します。 このチュートリアルでは、UserID ローカル アカウントを追加します。  

        > [!NOTE]
        >  TI コンポーネントを使用して CICS トランザクションにアクセスする場合、.NET リモート コンポーネントをホストしている COM+ アプリケーションまたは Web アプリケーションを使用できます。 このチュートリアルではメインフレームへのアクセスに TI コンポーネント用の COM+ アプリケーションおよび COM 相互運用を使用して、パフォーマンスを向上させます。  

    7.  **完了**] ページで [**完了**します。  

#### <a name="create-a-remote-environment-to-access-the-mainframe"></a>メインフレームにアクセスするリモート環境を作成します。  

1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Host Integration Server 2004**、順にクリックします**TI マネージャー**します。  

2.  **TI マネージャー**コンソールで、**トランザクション インテグレーター (構成)**、展開**Windows Initiated Processing**、右クリックして**リモート環境**、 をポイント**新規**、 をクリックし、**リモート環境**します。  

    1.  **へようこそ**  ページで **次**します。  

    2.  **新しいリモート環境の構成**ページで、入力、**リモート アプリケーション名**、順にクリックします**次**します。 このチュートリアルでは、Mainframe_TCP という名前を使用します。  

    3.  **ホスト環境の構成とプログラミング モデル** ページで、 **CICS**の**ターゲット ホスト**と**ELM リンク**の**プログラミング モデル**、 をクリックし、**次**します。  

    4.  **エンドポイント TCP/IP の構成**にメインフレームの IP アドレスを入力 ページで、 **IP/DNS アドレス**ボックスをクリックして**編集**ポート番号を追加します。 HIS COM は、このエンドポイント アドレスを使用してトランザクションにアクセスします。  

    5.  **完了**] ページで [**完了**します。  

#### <a name="create-the-ti-component-for-the-service-oriented-solution"></a>サービス指向ソリューションの TI コンポーネントの作成します。  

1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Host Integration Server 2004**、順にクリックします**TI マネージャー**します。  

2.  **TI マネージャー**コンソールで、[**トランザクション インテグレーター (構成)**、] をクリックして**Windows Initiated Processing**、順にクリックします**オブジェクト**. 右クリック**オブジェクト**、 をクリックして**新規**、 をクリックし、**オブジェクト**します。  

    1.  **へようこそ**  ページで **次**します。  

    2.  **指定または検索オブジェクト** ページで **参照**、%BTSSolutionsPath%\SO\MFAccess\HISTIComponent フォルダーの SOHISTIUsingCOM.TLB を選択し、クリックして**次へ**.  

    3.  **COM オブジェクトの環境特性の定義** ページで、 **BTSScn SO TI Component**の**COM + アプリケーション**、 をクリックし、 **次へ**.  

    4.  **リモート環境の定義** ページで、前の手順で作成したリモート環境を選択して、**リモート環境では、次へ を順にクリックします。**  

    5.  **WIP オブジェクトの作成**] ページで [ **[次へ]**、順にクリックします**完了**上、**完了**ページ。  

#### <a name="test-the-connectivity-to-the-mainframe"></a>メインフレームへの接続をテストします。  

1.  Windows エクスプローラーで %BTSSolutionsPath%\SO\MFAccess\HISTISimpleTester フォルダーを開き、Interop.SOHISTIUsingCOM.dll.reg ファイルをダブルクリックします。 これにより、ランタイム呼び出し可能ラッパー (RCW) を経由して TI コンポーネントを呼び出す HISTISimpleTester アプリケーションのレジストリ値が追加されます。  

2.  Windows エクスプローラーで %BTSSolutionsPath%\SO\MFAccess\ フォルダーを開き、SetupMFAccess.bat を実行します。  

3.  Windows エクスプローラーで %BTSSolutionsPath%\SO\MFAccess\HISTISimpleTester\bin\Debug フォルダーに移動し、BTSScnSOHISTIComponentSimpleTester.exe を実行します。  

    -   HISTISimpleTester アプリケーションで次のようにクリックします。 **Call Mainframe Program - COM を使用して**します。 メインフレームで実行されている COBOL アプリケーションから、5 レコードが返されます。  

##  <a name="step13"></a> Web サービス、オーケストレーション用の仮想ディレクトリを作成します。  

1.  **インターネット インフォメーション サービス (IIS) マネージャー**、右クリックして**アプリケーション プール**を選択します**新規**、し、 **のアプリケーションプール**.  

    1.  **新しいアプリケーション プールの追加** ダイアログ ボックスに、入力、**アプリケーション プール ID** (任意の値)、順にクリックします**OK**。  

    2.  作成したアプリケーション プールを右クリックし、**プロパティ**します。  

    3.  **プロパティ** ページで、をクリックして、 **Identity**  タブで **構成可能**、入力、**ユーザー名**と**パスワード**、 をクリックし、 **OK**します。 このチュートリアルでは、BizTalk サービスが使用しているユーザー アカウントを使用します。  

    > [!NOTE]
    >  このユーザーには、オーケストレーション プロキシ Web サービスを実行する権限が必要です。また、BizTalk Server 管理者グループ、SSO 管理者グループ、または SSO 関連管理者グループのいずれかにこのユーザーを追加する必要があります。  

2.  **インターネット インフォメーション サービス (IIS) マネージャー**、展開**Websites**を右クリックし、**既定の Web サイト**、 をポイント**新規**とクリックして**仮想ディレクトリ**を実行する**仮想ディレクトリの作成ウィザード**します。  

     使用して、**仮想ディレクトリの作成ウィザード**、アダプター バージョンの Web サービス プロキシの次の仮想ディレクトリを作成します。  

     Alias = Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Adapter  

     PATH = \<*BizTalk Install Directory*\>\SDK\Scenarios\SO\BTSSoln\OrchProxy\Adapter  

     Access Permissions = Read, Run scripts  

3.  **インターネット インフォメーション サービス (IIS) マネージャー**、展開**Web サイト、** 展開、**既定の Web サイト**、右クリックMicrosoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Adapter、 をクリックして**プロパティ**、し、次のように設定を変更します。  

    1.  **仮想ディレクトリ**タブで、設定、**アプリケーション プール**に\< *YourAppPool* \>前の手順で作成しました。  

    2.  **ディレクトリ セキュリティ**] タブで [**編集**で、**認証とアクセス制御**グループ ボックスで、**統合 Windows 認証のみ有効になっている**、し、その他のオプションをオフ**認証アクセス**チェック ボックスをオンします。 クリックして**OK**を終了します。  

4.  **インターネット インフォメーション サービス (IIS) マネージャー**、展開**Websites**を右クリックし、**既定の Web サイト**、 をポイント**新規**とクリックして**仮想ディレクトリ**を実行する**仮想ディレクトリの作成ウィザード**します。  

     使用して、**仮想ディレクトリの作成ウィザード**、インライン バージョン用の Web サービス プロキシの次の仮想ディレクトリを作成します。  

     Alias = Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Inline  

     PATH = \<*BizTalk Install Directory*\>\SDK\Scenarios\SO\BTSSoln\OrchProxy\Inline  

     Access Permissions = Read, Run scripts  

5.  **インターネット インフォメーション サービス (IIS) マネージャー**、展開**Websites**、展開、**既定の Web サイト**、右クリックMicrosoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Inline、 をクリックして**プロパティ**、し、次のように設定を変更します。  

    1.  **仮想ディレクトリ**タブで、設定、**アプリケーション プール**に\< *YourAppPool* \>で作成しました。  

    2.  をクリックして**ディレクトリ セキュリティ**] タブで [**編集**で、**認証とアクセス制御**グループ ボックスで、**統合 Windows 認証のみ有効になっている**、し、その他のオプションをオフ**認証アクセス**チェック ボックスをオンします。 クリックして**OK**を終了します。  

##  <a name="step15"></a> ビルド サービス指向ソリューション  

-   コマンド プロンプトでディレクトリを変更します BTSSolutionsPath%\SO\BTSSoln、型 % `SetupBTSSoln.bat`、し、ENTER キーを押します。 SetupBTSSoln.bat では、次のタスクが実行されます。  

    -   SO ソリューションのアセンブリに署名するためには、一意の厳密な名前キー (SNK) を作成します。  

    -   SNK から公開キー トークンを抽出し、公開キー トークンを使用してバインド ファイルを更新します。  

    -   SO ソリューションをビルドします。  

    -   %BTSSolutionsPath%\Common フォルダーに SSOApplicationConfig を作成します。  

##  <a name="step17"></a> SSO 関連アプリケーションを作成します。  

1. コマンド プロンプトを開いて、ディレクトリを %BTSSolutionsPath%\SO\BTSSoln\Scripts フォルダーに変更します。  

2. コマンド プロンプトで、メモ帳を使用して PendTransAffApp.xml を開き、内容を確認します。 このファイルへの変更は、不要です。  

   > [!NOTE]
   >  PendTransAffApp.xml では、Pending Transactions バックエンド システム用の SSO 関連アプリケーション WoodgroveBank.PendingTransactions が定義されています。 また、SSO 関連アプリケーションのユーザー グループと管理者グループも定義されています。 このチュートリアルでは、使用**BizTalk Application Users**と**BizTalk Server 管理者**します。  
   >   
   >  SSO 関連アプリケーションのさまざまなグループを使用する場合は、Active Directory で (任意の名前) を持つ Windows グループを作成し、変更する必要があります、 **appAdminAccount**と**上記の appUserAccount**PendTransAffApp.xml 内のノード。 これを行う場合は、値を設定する必要があります**groupApp**属性の**フラグ**を"yes"のノード。  
   >   
   >  SSO 関連アプリケーションの詳細については、[SSO 関連アプリケーション](../core/sso-affiliate-applications.md)を参照してください。  

3. コマンド プロンプトで、メモ帳を使用して PendTransUserMap.xml ファイルを開き、次のように編集します。  

   ```  
   <mapping>  
     <windowsDomain><DomainName></windowsDomain>  
     <windowsUserId><UserID></windowsUserId>  
     <externalUserId><ExternalUserID></externalUserId>  
   </mapping>  
   ```  

   > [!NOTE]
   >  PendTransUserMap.xml ファイルには、Pending Transactions バックエンド システム用のユーザー マッピングが保存されています。  

   > [!NOTE]
   >  **ExternalUserId**ノード、Pending Transactions バックエンド システムの外部ユーザー ID を使用します。 このチュートリアルでは、外部 ID として UserID を使用します。  

   > [!NOTE]
   >  **WindowsUserId**ノード、ユーザー名を入力する名前、 **externalUserId**にマップされます。 ドメイン グループとドメイン ユーザー アカウントの両方を使用できます。 このユーザーは、Pending Transactions バックエンド システムの使用が許可されたグループのメンバーである必要があります。 このチュートリアルでは、BizTalk サービスのユーザー名を使用します。  

   > [!NOTE]
   >  **WindowsDomain**ノードのドメイン名を入力、 **windowsUserId**します。  

4. コマンド プロンプトで、メモ帳を使用して PmntTrckAffApp.xml ファイルを開き、ファイルの内容を確認します。 このファイルへの変更は、不要です。  

   > [!NOTE]
   >  PmntTrckAffApp.xml では、Payment Tracker バックエンド システム用の SSO 関連アプリケーション WoodgroveBank.PaymentTracker が定義されています。  

5. コマンド プロンプトで、メモ帳を使用して PmntTrckUserMap.xml ファイルを開き、次のように編集します。  

   ```  
   <mapping>  
     <windowsDomain><DomainName></windowsDomain>  
     <windowsUserId><UserID></windowsUserId>  
     <externalUserId><ExternalUserID></externalUserId>  
   </mapping>  
   ```  

   > [!NOTE]
   >  Payment Tracker SSO 関連アプリケーションは MQSeries アダプターによって使用され、マップされた外部ユーザー IDおよびパスワードが MQSeries ヘッダー プロパティを使用して送信されます。 MQSeries アダプターが実行されている場合、MQSeries サーバーは BizTalk サービス アカウントのみを検証します。 外部ユーザーの資格情報は検証しません。  
   >   
   >  SSO の詳細については、MQSeries アダプターのアプリケーションを関連付ける、参照してください[MQSeries アダプター受信場所の構成、送信ポートを](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)します。  

   > [!NOTE]
   >  PmntTrckUserMap.xml ファイルには、Payment Tracker バックエンド システム用の SSO ユーザー マッピングが保存されています。 Payment Tracker シミュレーター プログラムでは、ユーザー認証が成功する条件と失敗する条件の両方がシミュレートされます。  
   >   
   >  プログラムの文字で始まるすべてのユーザー Id の認証に成功**PT** (たとえば、 **PTUserID**)、任意のユーザーで始まらない Id 認証に失敗して**PT**. このため、テストする条件に応じて、適切なユーザー ID を選択できます。 全体を繰り返すこともできます**マッピング**各ユーザー ID のノードと同じファイルで複数のマッピングを定義します。  

   > [!NOTE]
   >  **ExternalUserId**ノード、Payment Tracker バックエンド システムの外部ユーザー ID を入力します。 このチュートリアルでは、外部 ID として PTUserID を使用します。  

   > [!NOTE]
   >  **WindowsUserId**ノード、ユーザー名を入力する名前、 **externalUserId**にマップされます。 このユーザーは、Payment Tracker バックエンド システムの使用が許可されたグループのメンバーである必要があります。 このチュートリアルでは、BizTalk サービスのユーザー名を使用します。  

   > [!NOTE]
   >  **WindowsDomain**ノードのドメイン名を入力、 **windowsUserId**します。  

6. コマンド プロンプトで、メモ帳を使用して ConfigStoreApp.xml ファイルを開き、ファイルの内容を確認します。  

    このファイルは、このシナリオで構成パラメータを保存するために使用する SSO の構成ストア アプリケーションを定義します。 一部の構成パラメーターには、アダプター バージョンとインライン バージョンの両方の SAP との通信時に使用されるタイムアウト値と、インライン バージョンの使用時に使用するキュー マネージャーの名前およびキューが含まれます。 このファイルへの変更は、不要です。  

7. コマンド プロンプトで、メモ帳を使用して SetConfigValuesInSSO.cmd ファイルを開き、次の表に従ってファイルの内容を確認および変更します。  

   > [!NOTE]
   >  このコマンド ファイルは、SSO データベースの構成パラメーターの値を設定します。 コマンド ファイルの最初にローカル変数の値を割り当てる SET ステートメントがいくつか含まれます。  
   >   
   >  SAPAdapterTimeout、PendingTransactionsAdapterTimeout、および PaymentTrackingAdapterTimeout の値は、アダプター バージョンで使用されます。 他の値は、インライン バージョンで使用されます。  

   > [!NOTE]
   >  入力することができます""(2 つの二重引用符) マークされている既定値の\<ユーザー指定の\>次の表にします。  

   |                パラメーター                 |                                                 既定値                                                 |                                                                                                                説明                                                                                                                 |
   |------------------------------------------|---------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |            SAPAdapterTimeout             |                                                     20000                                                     |                                                                                        SAP バックエンドに対する要求の最大タイムアウト (ミリ秒)。                                                                                         |
   |             SAPInlineTimeout             |                                                     20000                                                     |                                                                                        SAP バックエンドに対する要求の最大タイムアウト (ミリ秒)。                                                                                         |
   |            SAPInlineHostName             |                                              \<指定されたユーザー\>                                               |                                                                                                          SAP バックエンド識別子。                                                                                                           |
   |          SAPInlineClientNumber           |                                              \<指定されたユーザー\>                                               |                                                                                                             SAP クライアント番号。                                                                                                              |
   |          SAPInlineSystemNumber           |                                              \<指定されたユーザー\>                                               |                                                                                                             SAP システム番号。                                                                                                              |
   |            SAPInlineUserName             |                                              \<指定されたユーザー\>                                               |                                                                                             SAP バックエンドへの接続に使用するユーザー名。                                                                                              |
   |            SAPInlinePassword             |                                              \<指定されたユーザー\>                                               |                                                                                              SAP バックエンドへの接続に使用するパスワード。                                                                                              |
   |    PendingTransactionsAdapterTimeout     |                                                     20000                                                     |                                                                                 Pending Transactions サーバーに対する要求の最大タイムアウト (ミリ秒)。                                                                                 |
   |     PendingTransactionsInlineTimeout     |                                                     20000                                                     |                                                                                 Pending Transactions サーバーに対する要求の最大タイムアウト (ミリ秒)。                                                                                 |
   |       PendingTransactionsInlineURL       | https://\<*コンピューター名*\>/Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactions/PendTransWS.asmx |              Pending Transactions サービスの URL。 \<*コンピューター名*\>と一致する必要があります、**共通名**「証明書要求を作成するには」の手順でします。 "Localhost"を使用する必要があります\<*コンピューター名*\>します。               |
   | PendingTransactionsInlineSSOAffiliateApp |                                       WoodgroveBank.PendingTransactions                                       |                                                                                                 Pending Transactions SSO アプリケーション名。                                                                                                  |
   |      PaymentTrackingAdapterTimeout       |                                                     20000                                                     |                                                                                   Payment Tracking システムに対する要求の最大タイムアウト (ミリ秒)。                                                                                   |
   |       PaymentTrackingInlineTimeout       |                                                     20000                                                     |                                                                                   Payment Tracking システムに対する要求の最大タイムアウト (ミリ秒)。                                                                                   |
   |      PaymentTrackingInlineQManager       |                          \<ユーザーの指定された\>(通常は qm _\<*コンピューター名*\>)。                          |                                                                                                        MQSeries キュー マネージャーの名前。                                                                                                         |
   | PaymentTrackingInlineMQChannelDefinition |                                  " " (二重引用符を 2 つ入力してください)                                   | ローカルの場合は空の文字列。または、リモート MQ サーバーのフォーマットされたチャネル名。 IBM WebSphere MQ の構成ですべての既定の設定を保持する場合、チャネルの定義になる時\<*コンピューター名*\>/tcp/\<*コンピューター名*\>(1414) です。 |
   |    PaymentTrackingInlineRequestQueue     |                                            LastPaymentsInputQueue                                             |                                                                                              Payment Tracking 要求用の MQ キュー名。                                                                                               |
   |    PaymentTrackingInlineResponseQueue    |                                            LastPaymentsOutputQueue                                            |                                                                                              Payment Tracking 応答用の MQ キュー名。                                                                                              |
   |   PaymentTrackingInlineSSOAffiliateApp   |                                         WoodgroveBank.PaymentTracker                                          |                                                                                                   Payment Tracking SSO アプリケーション名。                                                                                                    |
   |           StubSAPWebServiceURL           |                http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP/StubSAPWS.asmx                |                                                                                          Credit Limit SAP システムのスタブ Web サービス URL。                                                                                           |


8. コマンド プロンプトで次のコマンドを実行して、PATH 環境変数を設定します。  

   -   `SET PATH=%PATH%;"%CommonProgramFiles%\Enterprise Single Sign-On"`  

9. コマンド プロンプトで CreateInitialConfigInSSO.cmd を実行します。 SSO 関連アプリケーション、SSO 構成ストア アプリケーション、および関連アプリケーションのユーザー マッピングを作成します。 その後で、SetConfigValuesInSSO.cmd が実行され、SSO 構成ストア アプリケーションに構成値が格納されます。  

10. コマンド プロンプトで次のコマンドを実行して、Pending Transactions 関連アプリケーション用のユーザー資格情報を設定します。 使用して、 \< **DomainName** \>と\< **UserID** \> 、PendTransUserMap.xml に定義されている、 \<WindowsDomain\> \\< WindowsUserId\>します。 このコマンドでは、このチュートリアルで使用している外部ユーザー (UserID) のパスワードの入力が求められます。  

    -   `ssomanage -setcredentials <WindowsDomain>\<WindowsUserId> WoodgroveBank.PendingTransactions`  

11. コマンド プロンプトで次のコマンドを実行して、Payment Tracker 関連アプリケーション用のユーザー資格情報を設定します。 使用して、 \< **DomainName** \>と\< **UserID** \> 、PmntTrckUserMap.xml に定義されている、 \<WindowsDomain\> \\< WindowsUserId\>します。 このコマンドでは、このチュートリアルで使用している外部ユーザー (PTUserID) のパスワードの入力が求められます。  

    > [!NOTE]
    >  Payment Tracker シミュレーターは、外部ユーザー資格情報の検証を行いません。 PTUserID のパスワードとして任意の値を入力できます。  

    -   `ssomanage -setcredentials < WindowsDomain >\< WindowsUserId > WoodgroveBank.PaymentTracker`  

##  <a name="step19"></a> サービス指向ソリューションの BAM 定義ファイルをデプロイします。  

1. コマンド プロンプトを開いて、次のコマンドを入力し、&lt;localizedText&gt;Enter&lt;/localizedText&gt; キーを押して、BAM ユーティリティを参照するためのパスを設定します。  

   - SET PATH=%PATH%;[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking"  

2. コマンド プロンプトで、ディレクトリを %BTSSolutionsPath%\SO\BTSSoln\BAM に変更し、次のコマンドを入力して &lt;localizedText&gt;Enter&lt;/localizedText&gt; キーを押します。  

   -   `bm deploy-all -DefinitionFile:ServiceLevelTracking.xml`  

##  <a name="step21"></a> デプロイ サービス指向ソリューション  

#### <a name="update-the-binding-files-for-the-service-oriented-solution"></a>サービス指向ソリューションのバインド ファイルを更新します。  

1. コマンド プロンプトで、ディレクトリを %BTSSolutionsPath%\SO\BTSSoln\Scripts フォルダーに変更します。次に、メモ帳を使用して Deployallbinding.xml を開き、次のように編集します。  

   -   SET MGMT_DB_SERVER のサーバー名および MBMT_DB を、BizTalk Server が使用するサーバー名およびデータベースに変更します。  

   -   SOLNDIR 変数の値を "%BTSSolutionsPath%\SO\BTSSoln" に変更します。  

2. コマンド プロンプトで、ディレクトリを %BTSSolutionsPath%\SO\BTSSoln\Bindings フォルダーに変更します。  

3. アダプター バージョンの場合は、メモ帳を使用して AdapterSOAOrchBindings.xml を開き、次のように編集します。  

   - すべての出現箇所を置き換える *_MQ_SERVER_NAME\\*  \_ MQSeries サーバー名に置き換えます。  

   - すべての出現箇所を置き換える *_MQ_QMANAGER_NAME\\*  \_ MQSeries キュー マネージャーの名前。  

   - すべての出現箇所を置き換える *_PT_WS_SERVER_NAME\\*  \_文字列で"\<アドレス\>https://\_*PT_WS_SERVER_NAME\\* \_"を Pending Transactions Web サービスが展開されているサーバーの名前。 サーバー名が一致する必要があります、**共通名**Web サーバーの SSL の構成"するには」の手順でします。 localhost を使用しないでください。  

   > [!NOTE]
   >  バインド ファイル AdapterSOAOrchBindings.xml はスタブ Web サービスを、  
   > 
   > 1. Credit Limit バックエンド SAP システム  
   >    2.  Payment Tracking バックエンド システムとの統合を行う MQSeries アダプター  
   >    3.  HIS TI .NET コンポーネントを呼び出してメインフレーム バックエンド システムとの統合を行う Pending Transactions Web サービスとして使用します。  
   > 
   >    メインフレームを使用しない場合は、スタブ Web サービスを使用して Pending Transactions システム用のデータを生成する必要があります。  

4. インライン バージョンの場合は、メモ帳を使用して InlineSOAOrchBindings.xml を開き、次のように編集します。  

   - すべての出現箇所を置き換える *_MQ_SERVER_NAME\\*  \_ MQSeries サーバー名に置き換えます。  

   - すべての出現箇所を置き換える *_MQ_QMANAGER_NAME\\*  \_ MQSeries キュー マネージャーの名前。  

#### <a name="deploy-the-service-oriented-solution"></a>サービス指向ソリューションをデプロイします。  

-   コマンド プロンプトで、ディレクトリを %BTSSolutionsPath%\SO\BTSSoln\Scripts フォルダーに変更し、次のコマンドを入力して &lt;localizedText&gt;Enter&lt;/localizedText&gt; キーを押します。  

    -   `Deployallbinding.cmd`  

    > [!NOTE]
    >  Deployallbinding.cmd を実行すると、BTSScn.SO.CustomerService という名前の BizTalk アプリケーションが作成され、アダプター バージョンおよびインライン バージョン用のバインド ファイルがインポートされます。  

##  <a name="step23"></a> メインフレームが利用できない場合は、スタブ Pending Transactions Web サービスを構成します。  

#### <a name="configure-the-stub-pending-transactions-web-service-for-using-the-adapter-version-without-a-mainframe"></a>スタブ Pending Transactions Web サービス (メインフレームを使用せず、アダプター バージョンを使用して) 用の構成します。  

1.  **インターネット インフォメーション サービス (IIS) マネージャー**、展開**Websites**を右クリックし、**既定の Web サイト**、 をポイント**新規**とクリックして**仮想ディレクトリ**を実行する**仮想ディレクトリの作成ウィザード**します。  

     使用して、**仮想ディレクトリの作成ウィザード**、スタブ Pending Transactions Web サービス アダプター バージョンのための次の仮想ディレクトリを作成します。  

     Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions  

     PATH = \<*BizTalk Install Directory*\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PendingTrans  

     Access Permissions = Read, Run scripts  

2.  **インターネット インフォメーション サービス (IIS) マネージャー**、展開**Websites**、展開、**既定の Web サイト**、右クリックMicrosoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions、 をクリックして**プロパティ**、し、次の手順を使用して設定を変更、**プロパティ** ダイアログ ボックス。  

    1.  **仮想ディレクトリ**タブで、設定、**アプリケーション プール**に\< *YourAppPool* \>仮想を作成するには」の手順で作成します。IIS でのディレクトリ ソリューション"。  

    2.  **ディレクトリ セキュリティ** タブで **編集**で、**認証とアクセス制御**ボックスで、グループ化し、 **への匿名アクセスを有効にします。**. クリックして**OK**を終了します。  

3.  **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**展開し [btsscn.so.customerservice]、[**送信ポート**、右クリック **[pendingtransactionsolicitresponseport]**、] をクリックし、**プロパティ**します。  

    1.  **全般** ページで **構成**を表示する、**トランスポートのプロパティ** ダイアログ ボックスし、変更、 **Web サービスの URL**にスタブ Pending Transaction Web サービスをたとえば。  

         `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions/StubPendTransWS.asmx`  

    2.  すべてのダイアログ ボックスを閉じます。  

#### <a name="configure-the-stub-pending-transactions-web-service-for-using-the-inline-version-without-a-mainframe"></a>スタブ Pending Transactions Web サービス (メインフレームを使用せず、インライン バージョンを使用して) 用の構成します。  

1.  **インターネット インフォメーション サービス (IIS) マネージャー**、展開**Websites**を右クリックし、**既定の Web サイト**、 をポイント**新規**とクリックして**仮想ディレクトリ**を実行する**仮想ディレクトリの作成ウィザード**します。  

     使用して、**仮想ディレクトリの作成ウィザード**、スタブ Pending Transactions Web サービス アダプター バージョンのための次の仮想ディレクトリを作成します。  

     Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions  

     PATH = \<*BizTalk Install Directory*\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PendingTrans  

     Access Permissions = Read, Run scripts  

2.  **インターネット インフォメーション サービス (IIS) マネージャー**、展開**Websites**、展開、**既定の Web サイト**、右クリックMicrosoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions、 をクリックして**プロパティ**、し、次のように設定を変更します。  

    1.  **仮想ディレクトリ**タブで、設定、**アプリケーション プール**に\< *YourAppPool* \>仮想を作成するには」の手順で作成します。IIS でのディレクトリ ソリューション"。  

    2.  **ディレクトリ セキュリティ** タブで **編集**で、**認証とアクセス制御**ボックスで、グループ化し、 **への匿名アクセスを有効にします。**. クリックして**OK**を終了します。  

3.  コマンド プロンプトを開いて、ディレクトリを %BTSSolutionsPath%\SO\BTSSoln\Scripts フォルダーに変更します。  

4.  コマンド プロンプトで、メモ帳を使用して SetConfigValuesInSSO.cmd ファイルを開くしの値を設定、 **PendingTransactionsInlineURL**スタブ Pending Transaction Web サービスの URL にします。  

    -   `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions/StubPendTransWS.asmx`  

5.  コマンド プロンプトで「`SetConfigValuesInSSO.cmd`」と入力し、Enter キーを押します。  

##  <a name="step25"></a> 開始、サービス指向ソリューション  

1.  コマンド プロンプトを開き、ディレクトリを %BTSSolutionsPath%\SO\BTSSoln\Scripts フォルダーに変更して、次のコマンドを入力し Enter キーを押します。これにより、インライン バージョンおよびアダプター バージョン用のすべてのオーケストレーションが開始されます。  

    -   `startAll.vbs`  

2.  サービス指向ソリューションを実行します。 ソリューションの実行の詳細については、[サービス指向ソリューションを実行する方法](../core/how-to-run-the-service-oriented-solution.md)を参照してください。  

## <a name="next-steps"></a>次の手順  
 サービス指向ソリューションのインラインおよびアダプター バージョンをテストする[サービス指向ソリューションを実行する方法](../core/how-to-run-the-service-oriented-solution.md)します。  

## <a name="see-also"></a>参照  
 [サービス指向ソリューションをインストールする前に](../core/before-installing-the-service-oriented-solution.md)   
 [指向ソリューションのスタブ バージョンのサービスをインストールする方法](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md)   
 [サービス指向ソリューションに対する開発者のコンピューター設定](../core/developer-machine-setup-for-the-service-oriented-solution.md)