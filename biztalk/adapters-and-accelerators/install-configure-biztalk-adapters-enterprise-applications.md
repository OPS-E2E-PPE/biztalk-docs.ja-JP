---
title: BizTalk Adapters for Enterprise Applications インストール |Microsoft ドキュメント
description: 要件と BizTalk Server では、JD Edwards OneWorld、JD Edwards EnterpriseOne では、PeopleSoft Enterprise、TIBCO Rendezvous および TIBCO Enterprise Message Service のインストール手順
ms.custom: ''
ms.date: 10/13/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fa1a09f3d9fa531cee51ecd0e94b99ab972ba13
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "23450531"
---
# <a name="install-and-configure-the-microsoft-biztalk-adapters-for-enterprise-applications"></a>インストールし、エンタープライズ アプリケーション用の Microsoft BizTalk Adapters の構成 
  
 Microsoft BizTalk Adapters for Enterprise Applications には、次のアダプターが含まれています。  
  
-   Microsoft BizTalk Adapter for JD Edwards OneWorld  
  
-   Microsoft BizTalk Adapter for JD Edwards EnterpriseOne  
  
-   Microsoft BizTalk Adapter for PeopleSoft Enterprise  
  
-   Microsoft BizTalk Adapter for TIBCO Rendezvous  
  
-   Microsoft BizTalk Adapter for TIBCO Enterprise Message Service  


> [!IMPORTANT]
> - 構成の変更を行う前に、すべてのデータのバックアップします。
> - 構成の変更を行う前に、特定のエンタープライズ アプリケーションと経験豊富なをする必要があります。
  
## <a name="supported-versions--requirements"></a>サポートされているバージョンと要件

||必要条件|  
|---|---|
|オペレーティング システム|アダプターには、BizTalk Server と同じ OS がサポートされています。<ul><li>[BizTalk Server 2016 の要件](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)</li><li>[BizTalk Server 2013 R2/2013 の要件](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md)</li></ul>|
|サポートされているエンタープライズ システム|[サポートされている基幹業務 (LOB) とエンタープライズ システム](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)サポートされているバージョンを一覧表示 |
|JD Edwards OneWorld XE | <ul><li>Windows 上の JD Edwards エンタープライズ サーバー</li><li>Windows 上の JD Edwards Deployment サーバー</li></ul>|
|JD Edwards EnterpriseOne | アダプターは、データベースのドライバーが必要になる JDBC を使用して、JD Edwards EnterpriseOne API を呼び出します。 JD Edwards EnterpriseOne を SQL データベースとともにインストールする場合、MS-SQL のドライバーが必要です。 同様に、Oracle データベースと JD Edwards EnterpriseOne をインストールする場合に、Oracle のドライバーを必要または、DB2 のドライバーが必要な場合は、DB2 データベースとともにインストールします。 |
|PeopleSoft Enterprise | <ul><li>Sun Systems Java Development Kit (JDK)</li><li>PeopleSoft ツール リリース</li><li>PeopleSoft アプリケーションをリリースします。</li><li>このアダプターには、PeopleSoft アプリケーションへの変更が必要です。 コンポーネント インターフェイスを使用するのには、PeopleSoft にカスタム コンポーネント インターフェイスの GET_CI_INFO をアップロードします。 GET_CI_INFO.pc is in Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\PeopleSoft Enterprise(r)\Config\.</li></ul>|
|TIBCO Rendezvous | <ul><li>TIBCO Rendezvous の実行時コンポーネントは、BizTalk Adapter for TIBCO Rendezvous を実行しているコンピューターにインストールする必要があります。</li><li>TIBCO Rendezvous のライセンスは、BizTalk Adapter for TIBCO Rendezvous を実行しているコンピューターで構成する必要があります。</li><li>TIBCO Rendezvous のバイナリ ディレクトリが、環境変数の PATH の値、または BizTalk Server の各 Rendezvous ポートで指定されて、アダプターに認識されている必要があります。 これは、Rendezvous のアセンブリが、そのライブラリと実行可能ファイルを見つけるために必要です。</li></ul>|
|TIBCO Enterprise Message Service | Enterprise Message Service (EMS) バージョン 5.x 以降、クライアント SDK (TIBCO EMS c# API を使用) が含まれています。 BizTalk Adapter for TIBCO EMS では、これを使用して、サーバーと通信します。 |


## <a name="jd-edwards-oneworld-xe"></a>JD Edwards OneWorld XE

このセクションには、BizTalk Server と JD Edwards OneWorld XE を Microsoft BizTalk Adapter の使用に関する重要な情報が含まれます。
  
### <a name="create-the-jar-files"></a>JAR ファイルを作成します。
 ここでは、Microsoft BizTalk Adapter for JD Edwards OneWorld を操作するための JD Edwards OneWorld の要件について説明します。  
  
#### <a name="jar-files-and-the-classpath"></a>JAR ファイルと CLASSPATH  
 JD Edwards OneWorld JAR ファイルは、アダプターを使用できなければなりません。 たとえば、バージョンの B7.3.3.3 に接続する場合、次の jar ファイルが必要です。 接続するサーバーに応じて、jar ファイルの一覧を変更する可能性があります。
  
-   Connector.jar    
-   Kernel.jar  
  
 これらのファイルは、JD Edwards OneWorld を実行しているコンピューターの次の場所にあります。  
  
-   JD Edwards OneWorld XE_install_Directory\System\classes\Connector.jar    
-   JD Edwards OneWorld XE_install_Directory\System\classes\Kernel.jar  
  
 これらのファイルは任意の場所にコピーできますが、JAR ファイルの場所は CLASSPATH に指定する必要があります。 CLASSPATH には、ファイルの完全なパスと JAR ファイルの名前の両方 (セミコロンで区切る) を含める必要があります。  
  
 BizTalk Adapter for JD Edwards OneWorld では、JD Edwards OneWorld 用 JDEJAccess JAR ファイルを提供します。 既定では、JDEJAccess.jar ファイルはから参照*Program files \common files の \microsoft BizTalk Adapters for Enterprise applications \j.d. です。Edwards OneWorld(r) \classes\JDEJAccess.jar*です。 
  
> [!NOTE]
>  BizTalk Adapter for JD Edwards OneWorld を使用するには、jdeinterop.ini ファイルの登録を確認する必要があります。 このファイルへのパスを含めることを確認してください、 **JDE トランスポート プロパティ**ページを BizTalk Server で、送信ポートを作成する場合。 詳細については、「カスタマイズ jdeinterop.ini ファイル」を参照してください。  
  
#### <a name="create-the-btslibinteropjar-file"></a>BTSLIBinterop.jar ファイルを作成します。  
ファイルを作成し、アダプターによってアクセスできることを確認します。 次の例をガイドとして使用します。  
  
1.  次のコードが含まれた BTSLIB.cmd ファイルを作成します。  
  
    ```  
    define library BTSLIB  
    login  
    library BTSLIB  
    interface JDEAdapter  
    import B5500900  
    build  
    logout  
    ```  
  
2.  次のコマンドを実行します。  
  
    ```  
    GenJava  /cmd  .\BTSLIB.cmd  
    ```  
  
### <a name="verify-your-setup"></a>セットアップを確認してください。  
  
1.  サービス パック番号を含む、サポートされているバージョンを使用して ([サポートされている行業務 (LOB) とエンタープライズ システム](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx))。 サービス パック (ESU および ASU) では、システム バイナリを更新します。 前提条件のサービス パックには、インポート用の ASU/ESU というメニューの選択項目が用意されています。  
  
2.  ドライブ C と異なる場合に、ログ記録に正しいドライブを使用する jdeinterop.ini ファイルを構成します。たとえば、TEMP ディレクトリが領域不足の場合に、JD Edwards OneWorld の更新が失敗します。  
  
3.  JD Edwards OneWorld のフィールドの左右の埋め込み用の構成ファイルを追加する必要があるかどうかを判断します。  
  
4.  コンピューター上の任意のプログラムから javac コマンドと java コマンドを有効にするには、JAVA_HOME 環境変数が Java Development Kit (JDK) のインストール場所を指していることを確認します。  
  
5.  CLASSPATH 環境変数が設定されていることを確認します。 これにより、BizTalk Adapter for JD Edwards OneWorld Kernel.jar と Connect.jar ファイルを配置できます。  
  
    JAR ファイルのパスは、大文字小文字が区別されます。  
  
6.  次のコマンド (大文字小文字が区別されます) を入力して、環境をテストします。  
  
    ```  
    javap -s -p com.microsoft.jde.JDEJAccess  
    ```  
  
7.  指定するコマンドの javap は、Java クラス ファイルの逆アセンブラーです。  
  
    ```  
    http://java.sun.com/j2se/1.3/docs/tooldocs/solaris/javap.html  
    ```  
  
8.  `javap`コマンドは、クラス ファイルを逆アセンブルします。 その出力は、使用するオプションによって異なります。 オプションが使用されていない場合、javap は、保護されているパッケージおよびパブリック フィールドに、渡されるクラスのメソッドを出力します。 javap では、その出力を標準出力を出力します。  
  
     エラーがなければ、すべての Java ファイルとそれらの依存関係は CLASSPATH にあります。  
  
9. ローカル ホスト ファイルを構成することによって、DNS 解決を設定 (*C:\WINNT\system32\drivers\etc\hosts*)、JD Edwards OneWorld システムのサーバーの名前に置き換えます。  
  
### <a name="create-and-install-the-custom-package"></a>作成し、カスタム パッケージをインストール  
JD Edwards OneWorld の BizTalk アダプターを使用するには、BTSREL カスタム パッケージをインストールします。 このセクションの内容について説明します。  
  
-   JD Edwards OneWorld のカスタム パッケージの作成プロセス  
-   作成して、BTSREL をインストールする方法  
-   JD Edwards OneWorld で作成された BTSREL オブジェクト
  
> [!NOTE]
>  BTSREL.exe はカスタム パッケージです (JD Edwards OneWorld の用語では、自動化されたソフトウェア更新プログラム (ASU))。 このパッケージには、メタデータを抽出するためのビジネス関数が含まれています。 カスタム パッケージは、JD Edwards OneWorld の特定の構成とバージョン用に作成してください。  
  
#### <a name="define-a-custom-package"></a>カスタム パッケージを定義します。  
 カスタム パッケージとは、リリース後の成果物であり、法規制の変更や機能強化などの特定の目的のためのソフトウェア変更を提供します。 これらのカスタム パッケージは、特定の機能向けに作成されます。 たとえば、BTSREL はメタデータを抽出するために作成されます。 BTSREL カスタム パッケージをインストールすると、JD Edwards OneWorld 環境内の選択したモジュールが更新されます。 更新を行うには、適切な JD Edwards OneWorld の環境に BTSREL オブジェクトをマージする必要があります。 BTSREL によって更新されるモジュールの詳細な一覧については、「モジュールの一覧」を参照してください。  
  
#### <a name="install-the-btsrel-custom-package"></a>BTSREL カスタム パッケージをインストールします。   
ダウンロード[BTSREL](https://www.microsoft.com/download/details.aspx?id=56113)です。 展開サーバーにインストールし、エンタープライズ サーバーに配置します。  
  
 既存の BTSREL.exe パッケージは、B7333 バージョンと直接動作します。 パッケージ、B7334 バージョンを使用するには。  
  
1.  BTSREL.exe をダウンロードして、BTSREL.exe の内容を作業フォルダーに展開します。  
  
2.  両方の変更、 **ReleaseLevelRequired**と**リリース**B7334 に Deployment.Inf ファイルの値。  
  
3.  セットアップを実行します。  
  
 BTSREL をインストールするには次が必要です。  
  
-   展開サーバーのインストール    
-   Installation Workbench  
  
#### <a name="install-btsrel-on-the-deployment-server"></a>配置先のサーバーに BTSREL をインストールします。  
 カスタムの Windows オペレーティング システムでのみ機能をパッケージ化し、は、デプロイメント サーバーとともに使用します。 配置サーバー上に構築され、し、エンタープライズ サーバーに展開する必要があります。 エンタープライズ サーバーは、通常実稼働サーバーで、Windows または UNIX のオペレーティング システムのいずれかの上に存在します。  
  
> [!NOTE]
>  ASU を JD Edwards OneWorld デプロイメント サーバーに適用すると、であることを確認してください**更新**モード。 **実証**モードが一方では ASU にバグがないことを確認**更新**ASU を適用するときのモードを指定します。  
  
1.  ユーザーと展開サーバーへのサインイン**JDE**です。  
  
2.  デプロイメント サーバー (root) の /B7 フォルダーに BTSREL という新しいフォルダーを作成します。  
  
3.  BTSREL.exe を新しく作成した BTSREL フォルダーにコピーします。  
  
4.  BTSREL.exe を .../B7/BTSREL フォルダーで実行します。 インストールのマネージャーを自動的に開始します。  
  
5.  セットアップ ウィンドウで、次のように選択します。**次**、し、**完了**です。 インストールが成功した場合、メッセージが表示されます。  
  
6.  として JDEPLAN 環境にサインイン、**JDE** JD Edwards OneWorld デプロイメント サーバー上のユーザーです。  
  
    1.  SAR #4533357 が含まれる電子的なソフトウェア更新プログラム (ESU) がシステムにインストールされていない場合は、選択**ソフトウェア更新プログラムの**から、**システム インストール ツール**メニュー (GH9612)。  
  
    2.  オプション 1 に 02 と入力、**処理オプション**パネルです。  
  
    3.  SAR #4533357 が含まれる ESU がシステムにインストールされている場合は、選択**アプリケーション ソフトウェアの更新**から、**システム インストール ツール**メニュー (GH9612)。  
  
#### <a name="install-btsrel-on-the-jd-edwards-oneworld-workbench"></a>JD Edwards OneWorld WorkBench に BTSREL をインストールします。  
   
1.  **アプリケーションの更新を使用**画面、BTSREL 更新プログラムをダブルクリックし、選択**次**です。  
  
2.  更新プログラムをインストールするには、必要とする環境をダブルクリックし、選択**次**です。  
  
    1.  確認**自動ワークベンチ**ソフトウェアの更新を自動モードで実行する場合。  
  
    2.  選択**バックアップ**する仕様のバックアップ (ようにする場合、元の仕様を復元することができます)。  
  
3.  **作業時間とインストールの計画**画面で、インストールする場合は、更新プログラムのプランを選択し、**選択**です。  
  
4.  インストールが完了したら、自動生成されるエラーに関する PDF を確認してください。  
  
    > [!NOTE]
    >  エラーが発生した場合、トラブルシューティングのヒントについては『JD Edwards OneWorld Software Update Guide』を確認するか、または JD Edwards OneWorld に直接お問い合わせください。  
  
5.  「に手動で登録、ビジネス関数ライブラリ」このセクションで説明されている手順を使用して、ビジネス関数ライブラリを手動で登録します。  
  
#### <a name="uninstall-the-custom-package"></a>カスタム パッケージをアンインストールします。  
 カスタム パッケージのアンインストールには要件はありません。 ただし、システムをクリーンアップする場合は、異なる方法でアンインストールすることができます。 をアンインストールした後は、次のいずれかを使用してパッケージを再構築します。  
  
-   JD Edwards OneWorld Deployment サーバー、Gh8612 を使用して — P96470 の**行**メニューの **更新**、し、**アンインストール**です。    
-   すべてのカスタム オブジェクト (BTSREL) をクライアント コンピューターにチェック アウトしてから、それらを削除します。    
-   データベースの前のスナップショットを適用します。  
  
 クリーンアップ中に、JD Edwards OneWorld の他のオブジェクトに対する他のすべての変更を確認します。  
  
#### <a name="manually-register-the-business-function-library"></a>ビジネス関数ライブラリを手動で登録します。  
 JD Edwards OneWorld 製品のパッケージ化プロセスの制限のために、BizTalk Adapter for JD Edwards OneWorld 用のカスタムのビジネス関数ライブラリ DLL を JD Edwards OneWorld に手動で登録する必要があります。 このプロセスは、次の手順で構成されます。
  
##### <a name="step-1-create-the-custom-business-function-library"></a>手順 1: カスタム ビジネス関数ライブラリを作成します。  
 JD Edwards OneWorld Object Management Workbench (OMW) を使用して、カスタムのビジネス関数ライブラリを作成します。 次の手順では、初期のセットアップで行う必要があり、すべてのプラットフォームに適用します。  
  
1.  Object Management Workbench を起動 (高速なパス:「OMW」。 またはメニュー選択: GH902 オブジェクト: P98220)。  
  
2.  選択**追加**、オプションを選択して**ビジネス関数ライブラリ**です。  
  
3.  新しいビジネス関数ライブラリ オブジェクトに関する次の情報を入力します。  
  
    -   **[名前]:** ACBLIB    
    -   **説明:** Microsoft DLL    
    -   **製品コード:** 55    
    -   **製品システム コード:** 55  
  
4.  **[OK]** を選択します。  
  
##### <a name="step-2-rebuild-libraries-from-the-deployment-server"></a>手順 2: 配置先のサーバーからライブラリを再構築します。  
各プラットフォームの初期セットアップで次の手順を実行します。  
  
1.  BusBuild プログラムをスタンドアロン モードで起動するには、選択**開始****実行**、し、 **busbuild.exe**です。
  
2.  JD Edwards OneWorld にパスコード (PY7333、PD7333、または DV7333) でサインインします。  
  
3.  **ライブラリの再構築**一覧で、、**ビルド**です。  
  
##### <a name="step-3-copy-the-custom-dll"></a>手順 3: カスタムの DLL をコピーします。  
 JD Edwards OneWorld デプロイメント サーバーと JD Edwards OneWorld Enterprise サーバーは、親パッケージのディレクトリをパスコード ディレクトリからカスタムの DLL をコピーします。
  
**JD Edwards OneWorld XE Deployment サーバー**  
  
1.  ACBLIB.dll を DV7333\bin32 から DV7333\Packages\DV7333FA\bin32 にコピーします。  
  
2.  ACBLIB.def、ACBLIB.dmp、および ACBLIB.mak を DV7333\obj フォルダーから DV7333\Packages\DV7333FA\obj フォルダーにコピーします。  
  
3.  ACBLIB.exp、ACBLIB.lib、および sACBLIB.lib を DV7333\lib32 フォルダーから DV7333\Packages\DV7333FA\lib32 フォルダーにコピーします。  
  
**JD Edwards OneWorld Enterprise サーバー**  
  
各ディレクトリとファイルを作成した後、アクセス許可を確認します。  
  
1.  ACBLIB DV7333FA\obj 下のディレクトリを作成\\です。  
  
2.  ACBLIB DV7333FA\source 下のディレクトリを作成します。  
  
3.  b5500900.c を、デプロイメント サーバーの DV7333\source ディレクトリから DV7333FA\source\ACBLIB ディレクトリに FTP で転送します。  
  
4.  FTP の b5500900.h は、展開サーバー DV7333\include ディレクトリ DV7333FA\include ディレクトリにします。  
  
##### <a name="step-4-build-a-full-package"></a>手順 4: 完全なパッケージをビルドします。  
 JD Edwards のパッケージのビルド プロセスの制限のための環境を BTSREL 更新を適用するまたは更新プログラム パッケージ ビルドが正常に動作しない完全なパッケージをビルドします。 フル パッケージ ビルドをビルドする方法については、JD Edwards のドキュメントを参照してください。  
  
> [!NOTE]
>  JD Edwards OneWorld の ASU/ESU を適用した場合、ASU/ESU では通常新しいライブラリとビジネス関数は作成されません。 そのため、プロセスは単純な。 ただし、BizTalk Adapter for JD Edwards OneWorld のカスタム パッケージは新しいライブラリを作成します。 そのため、追加の手順を実行する必要があります (など) に手動でディレクトリを作成し、フル パッケージ ビルドを実行します。  
  
#### <a name="modules-list"></a>モジュールの一覧  
 BTSREL カスタム パッケージは、JD Edwards OneWorld の次のオブジェクトを作成します。 BTSREL には、メタデータを抽出するためのビジネス関数と、データ型をテストするためのカスタム関数が含まれています。  
  
> [!NOTE]
>  JD Edwards OneWorld の更新プログラムには 1 つのバグがあります。 すべてのビジネスとユーザー定義関数を持っていない場合は、更新プログラム パッケージ ビルドではなく、フル パッケージ ビルドを完了したことを確認します。  
>  
>  ファイルが一覧から失われた場合 (たとえば、ACBTEST の下にはすべてがあるが、その上には何もない場合)、データ辞書 (DD) の項目が失われた可能性があります。 移動して**データ項目と作業**し、不足しているファイルを探します。  
>   
>  これらは ACBCHAR01、ACBDATE01、ADBINT01、ACBMATH01、ACBSTR01、およびなどその他の項目がない場合は、*プライマリ データ要素*です。 オブジェクトをプランナーから DEV にマージすると、多数のレポートがバックグラウンドで実行されます。 マージのレポートを開いて、エラーを探すことができます。 レポートにはすべての項目が一覧表示され、エラーまたは警告なしで完了したことが示されます。 この検証を使用すれば、すべての項目が考慮されているため、作業を続行できます。  
  
-   ACBCHAR01 - 文字型 01 のテスト  
  
-   ACBCUST - ACB 顧客 ID  
  
-   ACBDATE01 - 日付型 01 のテスト  
  
-   ACBDEF - ACB 関数の種類の定義  
  
-   ACBFCNT - ACB 関数名の一覧の数  
  
-   ACBFUNC - ACB 関数名の一覧  
  
-   ACBFUNCN - ACB 関数名  
  
-   ACBINT01 - 整数型 01 のテスト  
  
-   ACBLIB - ブローカー ライブラリの制御  
  
-   ACBMATH01 - 数学型 01 のテスト  
  
-   ACBNEWS - ACB の新しいステータス  
  
-   ACBORDER - ACB 注文番号  
  
-   ACBPRC - ACB 品目の価格  
  
-   ACBPROD - ACB 製品 ID  
  
-   ACBQTY - ACB 品目の数量  
  
-   ACBRES - ACB 結果のインジケーター  
  
-   ACBSTAT - ACB ステータス  
  
-   ACBSTR01 - テスト用文字列型 01  
  
-   ACBTEST - ACB テスト画面  
  
-   ACBTEST2 - ACB テスト画面 2  
  
-   ACBTEST3 - ACB テスト画面 3  
  
-   B5500900 - ブローカー サポート モジュールの制御  
  
-   D5500900 - 制御ブローカー データ構造体  
  
-   D5500900A - 制御ブローカー データ構造体  
  
-   D5500900B - フェッチ価格データ構造体  
  
-   D5500900C - 顧客ステータスのデータ構造の取得  
  
-   D5500900D - 顧客ステータスのデータ構造のセット  
  
-   D5500900E - 更新プログラムの販売注文ステータスのデータ構造体  
  
-   D5500900F - 整数のテスト  
  
-   D5500900G - テスト文字列  
  
-   D5500900H - 日付のテスト  
  
-   D5500900I - テスト CHAR  
  
-   D5500900J - 数学数値のテスト  
  
-   D5500900K - 日付 2 のテスト  
  
#### <a name="customize-the-jdeinteropini-file"></a>Jdeinterop.ini ファイルをカスタマイズします。  
 Connector.jar および Kernel.jar で JD Edwards OneWorld XE コネクタ クラスでは、jdeinterop.ini 構成ファイルを使用することが必要です。 このファイルは、JD Edwards OneWorld ソフトウェアで定義されており、その用語を使用します。 JD Edwards Interoperability Guide Release OneWorld には、目的と用語のこのファイルの詳細についてを説明可能性があります。 サンプルの jdeinterop.ini ファイルがある *< Adapter_Installation > \config\jde*です。  
  
定義されているパラメーター値に一致する jdeinterop.ini の更新、**トランスポートのプロパティ**画面。 複数の JD Edwards OneWorld 論理システムで、それらのパラメーターに互換性がある場合は、同じ jdeinterop.ini ファイルを共有できます。 一般に、2 つの論理システムは、次の 2 つの異なる JD Edwards OneWorld コンピューター をポイントして、jdeinterop.ini の 2 つの異なるコピーが必要です。  
  
> [!NOTE]
>  Jdeinterop.ini でログ記録をオフにする必要があり、さまざまなログ ファイルのパラメーターを無視しても安全です。  
  
 次の表は、jdeinterop.ini ファイルにある各設定を項目化したものです。 情報は、セクション別に構成されています。 たとえば [JDENET] と各セクションは、JD Edwards OneWorld ソフトウェア内で出現する順序で一覧表示されています。  
  
#### <a name="jdeinteropini-file-settings"></a>jdeinterop.ini file settings
  
|セクション|パラメーターと説明|  
|-------------|-------------------------------|  
|[JDENET]|**EnterpriseServerTimeout.** エンタープライズ サーバーへの要求のタイムアウト値 (ミリ秒単位)。 既定のサイズは 120000 です。<br /><br /> **maxPoolSize.** JDENET ソケット接続のプール サイズ。 既定のサイズは、30 です。|  
|[サーバー]|**glossaryTextServer.** 用語集のテキスト情報を提供する、エンタープライズ サーバーとポート。 これは、エラーに関する説明テキストを返すサーバーです。 これは多くの場合、JD Edwards OneWorld アプリケーション サーバーと同じホストとポートです。 別のサポート対象言語エンコード用の複数の用語集サーバーが存在する場合があります。 たとえば、JDED:6010 または actsrv1:6009 です。 これらの値は、[System Definition] \(システム定義) に設定されている値と一致している必要があります。<br /><br /> **codePage.** エンコード スキームです。 既定値は、1252 です。<br /><br /> 1252 英語および西ヨーロッパ<br /><br /> -932 日本語<br /><br /> -950 繁体字中国語<br /><br /> -936 簡体字中国語<br /><br /> -949 韓国語|  
|[LOGS]|**log= c:\jas.log.** ログ ファイルの場所です。 このパラメーターは無視してかまいません。<br /><br /> **debuglog= c:\jasdebug.log.** デバッグ ログ ファイルの場所。 このパラメーターは無視してかまいません。<br /><br /> **デバッグします。** JDENET デバッグがオンかどうかが決定されます。 既定値は FALSE です。|  
|[デバッグ]|**JobFile= c:\Interop.log.** エラー ファイルの場所。 このパラメーターは無視してかまいません。<br /><br /> **DebugFile= c:\InteropDebug.log.** デバッグ ファイルの場所です。 このパラメーターは無視してかまいません。<br /><br /> **log= c:\net.log.** ログ ファイルの場所です。 このパラメーターは無視してかまいません。<br /><br /> **debugLevel= 0 - 12.** デバッグ レベル。 このパラメーターは無視してかまいません。 このパラメーターでは、COM サーバーのみで、指定されたログ ファイル内の COM コネクタと Callobject コンポーネントによって提供されるトレースのレベルを定義します。<br /><br /> -なし。 ログ記録が無効になり、エラーのみが JobFile に書き込まれます。<br /><br /> 2 つのエラー (エラー メッセージ)<br /><br /> -4: システム エラー (例外メッセージ)<br /><br /> -6: 警告情報<br /><br /> -8: 最小トレース (キー操作。 たとえば、ログオン、ログオフ、ビジネス関数の呼び出し。)<br /><br /> -10: トラブルシューティング情報 (ヘルプ)。<br /><br /> -12 の完全なデバッグ情報 (すべてログに記録)<br /><br /> -既定では、トレースを有効にする必要はありませんが、トレースは、コードをデバッグするときに便利です。<br /><br /> -NetTraceLevel 0 を = です。 トレース レベル。 このパラメーターは無視してかまいません。 COM サーバーのみで、指定されたログ ファイルで ThinNet コンポーネントによって提供されるトレースのレベルを定義します。 奇数の値は、レベルを今後追加するために予約されています。<br /><br /> -次の一覧には、さらに多くのデバッグ レベルについて説明します。<br /><br /> -0 トレースなし<br /><br /> -レコードのプロセス ID、スレッド ID、および新しい接続が追加され、ソケット プールが検索されるときに利用可能なソケット ステータス 1 の参照。<br /><br /> -2 では、トレース レベル 1 の情報が含まれますも、接続マネージャー クラスで加えられたすべての呼び出しをトレースします。<br /><br /> -3 には、トレース レベル 2、また、トレース getPort() 呼び出しおよび getHost() 呼び出し内のすべての情報が含まれます。|  
|[INTEROP]|**enterpriseServer.** この値は、ホスト サーバーの名前です。 この値が同じ値に入力するかどうかを確認、**ホスト名**フィールドで、 **JDE 資格情報**」の「**システム定義**で、 **トランスポートのプロパティ** ダイアログ ボックス。 既定値は、JDED です。<br /><br /> **ポートです。** この値は、データの交換に使用されるポート番号です。 この値が同じ値に入力するかどうかを確認、**ポート番号**フィールドに、JD Edwards**資格情報**」の「、**トランスポートのプロパティ、システム定義**. たとえば、6010 または 6009 です。 値が一致する必要がありますで設定されている**システム定義**です。<br /><br /> **inactive_timeout**です。 自動コミット モードのトランザクションのタイムアウト値 (ミリ秒単位)。 ユーザーがこの時間 (ミリ秒単位) の間アクティブでなかった場合は、相互運用サーバーによってそのユーザーがログオフされます。 この値は、より短い時間に変更できます。 既定値は、1200000 です。<br /><br /> **manual_timeout.** 手動コミット モードでのトランザクションのミリ秒単位のタイムアウト値。 既定値は、120000 です。<br /><br /> **リポジトリ。** Connector.jar と Kernel.jar が含まれたディレクトリの場所を指します。 UNIX では、これは完全なパスです。|  
|[CORBA]|このパラメーターは無視してかまいません。<br /><br /> **マルチ スレッドです。** 設定は無視できます。 CORBA でマルチスレッド サポートの場合は 1 に設定されます。<br /><br /> Objects= CORBA::Connector;CORBA::OneWorldVersion<br /><br /> CORBA サーバーで起動時に作成するオブジェクトを定義します。 -DIORFILENAME 置き換えますコマンド ライン オプションをたとえば =: CORBA::Connector=connector.ior です。|  
  
## <a name="jd-edwards-enterpriseone"></a>JD Edwards EnterpriseOne  
このセクションには、キー使用の詳細について、Microsoft BizTalk Adapter for JD Edwards EnterpriseOne を BizTalk Server が含まれています。
  
### <a name="execute-a-jd-edwards-enterpriseone-master-business-function"></a>JD Edwards EnterpriseOne のマスター ビジネス関数を実行します。  
 BizTalk Adapter for JD Edwards EnterpriseOne を使用して、住所録、購買オーダー、受注オーダーなどの JD Edwards EnterpriseOne のマスター ビジネス関数を呼び出すことができます。 このアダプターは、JD Edwards EnterpriseOne を BizTalk Server と接続するための統合作業の一部として使用することもできます。  
  
##### <a name="access-data-stored-in-jd-edwards-enterpriseone"></a>JD Edwards EnterpriseOne に格納されているデータにアクセス  
 このアダプターでは、BizTalk Server アプリケーションで次のいずれかを使用して、JD Edwards EnterpriseOne との通信およびトランザクションの交換を可能にするために、XML メッセージを受け入れます。  
  
-   **送信アダプター**、JD Edwards EnterpriseOne にメッセージを送信する静的な送信請求-応答の送信ポートを使用し、応答を待機します。    
-   **受信アダプター**、静的な一方向の受信ポートを使用して JD Edwards EnterpriseOne からメッセージを受信します。  
  
### <a name="interoperability-framework"></a>相互運用フレームワーク  
 JD Edwards EnterpriseOne では、その相互運用性フレームワークを通じて各システムとの統合に備えます。 アダプターは、さまざまな統合、最大限の柔軟性と機能を提供するアクセス メソッドを利用して JD Edwards EnterpriseOne フレームワークを使用します。  
  
 BizTalk Adapter for JD Edwards EnterpriseOne では、次の統合アクセス方法がサポートされています。  
  
-   JD Edwards EnterpriseOne ThinNet API    
-   JD Edwards EnterpriseOne XML    
-   JD Edwards EnterpriseOne の未編集トランザクション テーブル (Z テーブル)  
  
 アダプターでは、JD Edwards EnterpriseOne ThinNet API を使用して、JD Edwards EnterpriseOne アプリケーションと通信します。 アダプターでは、ThinNet API を使用することによって、1 つの作業単位 (UOW) で 1 つのマスター ビジネス関数 (MBF) を呼び出すことができます。 MBF が失敗した場合、UOW 全体が失敗します。 これによって、部分的な更新が防止されます。 データ、ビジネス ルール、および基になるデータベースへの通信の検証は、JD Edwards EnterpriseOne アプリケーションによって処理されます。  
  
#### <a name="jd-edwards-outbound-processing-framework"></a>JD Edwards の送信処理フレームワーク  
 送信プロセスでは、特定の MBF が JD Edwards EnterpriseOne 環境で実行されると、イベントが開始します。 MBF では、このイベントに必要な情報を適切なインターフェイス テーブルに書き込んでから、イベントが発生したことをサブシステム バッチ関数 (BF) に通知します。 次に、サブシステム BF では、イベントに関するエントリをサブシステムのデータ キューに含めます。  
  
 送信サブシステムでは、データ キューのエントリを取得し、通知すべき外部プロセスがないか、データ エクスポートの制御テーブルを検索します。 次に送信サブシステムでは、その通知で BizTalk Adapter for JD Edwards EnterpriseOne のリスナーを呼び出します。 このリスナーでは、通知をジェネレーターに渡します。 次にジェネレーターでは、JD Edwards EnterpriseOne ThinNet API を使用して、インターフェイス テーブルから適切な情報を取得します。  
  
### <a name="set-string-justification-in-jdearglist"></a>Jdearglist で文字列の位置揃えの設定  
 J. d. に埋め込まれた右揃えになり左側として特定の文字列引数を構成するには Edwards EnterpriseOne の jdearglist.txt ファイル; にアクセスするどのようなビジネス関数を知る必要があります。具体的には、呼び出したいビジネス関数のどのフィールドを知る必要があります。  
  
 オーケストレーションでバインド (スキーマ) を生成する前に、jdearglist.txt を更新する必要があります。 「文字列の値を処理する」セクションに記載されている、jdearglist.txt を更新するための手順です。  
  
 ログに jdearglist.txt の警告メッセージを受信する場合、その目的は、jdearglist.txt が不足していることを知らせるです。 ただし、SalesOrder または PurchaseOrder ビジネス関数を実行している場合は、そのファイルのパスにする必要があります。 または機能しません。  
  
### <a name="understand-jdeinteropini"></a>Jdeinterop.ini を理解します。  
 Connector.jar および Kernel.jar で JD Edwards EnterpriseOne コネクタ クラスでは、jdeinterop.ini という名前の構成ファイルを使用することが必要です。 このファイルは、JD Edwards EnterpriseOne ソフトウェアによって定義され、その用語を使用します。 目的と用語のこのファイルの詳細については、JD Edwards の相互運用性ガイドを参照してください。 サンプルの jdeinterop.ini ファイルがある: Program files \ の Microsoft BizTalk Adapters for Enterprise applications \ j. d. Edwards EnterpriseOne(r)\config.  
  
 やり取りするために手動でこのファイルを編集することはお勧めできません、**トランスポートのプロパティ**--としてマークされたフィールドなどの送信ポートのダイアログ ボックス **< BizTalk によって構成された\>**.  
  
## <a name="peoplesoft-enterprise"></a>PeopleSoft Enterprise  
このセクションには、キー使用の詳細について、Microsoft BizTalk Adapter for PeopleSoft Enterprise を BizTalk Server が含まれています。
  
### <a name="receive-handler-peoplesoft-requirements"></a>受信ハンドラー PeopleSoft の要件  
 PeopleSoft Integration Broker が、BizTalk Server と通信可能である必要があります。 次のことが既存の PeopleSoft 環境ですでに実行済みの可能性があるため、既存のノードを再利用できる可能性があります。このため、PeopleSoft のシステム管理者から HTTP の仕様を入手する以外に何も行う必要はないかもしれません。 詳細については、PeopleSoft のドキュメントを参照してください。  

次の手順では、PeopleSoft を実行する概要を説明します。  
  
1.  メッセージを設定し、アプリケーション デザイナーをアクティブにします。  
  
2.  PeopleSoft integration.gateway.properties ファイルに対して、1 回限りの変更を行います。  
  
3.  作成し、ゲートウェイと HTTP のアクティブ化するノードを構成します。
  
    -   ノードでは、LOCATION_SYNC メカニズムなどのなんらかのトリガー メソッドを使用する必要があります。   
    -   ノードでは、HTTP を使用する必要があります。    
    -   ノードでは、イベントの送信先のホストとポートを指示している必要があります。  
  
### <a name="send-handler-peoplesoft-requirements"></a>送信ハンドラー PeopleSoft の要件  
 BizTalk Adapter for PeopleSoft Enterprise は、Java API を通じてアクセスを提供するカスタム コンポーネント インターフェイス (CI) で構成されます。 カスタム CI オブジェクトの**GET_CI_INFO**で BizTalk Adapter for PeopleSoft Enterprise のために必要なメタデータ情報を提供する PeopleSoft ツールを使用して、PeopleSoft システムに展開します。 詳細については、PeopleSoft のドキュメントを参照してください。  
  
 カスタム コンポーネント インターフェイスをアップロードするのは 1 回だけです。 このファイルの GET_CI_INFO.pc は製品に付属しており、アダプターを使用して CI を参照するには、PeopleSoft システムにインストールする必要があります。 PeopleSoft アプリケーション デザイナにアクセスできる必要がありますが、アプリケーション デザイナは、BizTalk Server コンピューターの近くに存在する必要はありません。 参照する PeopleSoft コンピューターにカスタム CI をアップロードするのにには、アプリケーション デザイナーを使用します。  
  
 環境変数 CLASSPATH を設定する必要がありますのでから PeopleSoft コンピューターにアクセスする必要があります (情報を設定または、**トランスポートのプロパティ**ウィンドウ) PeopleSoft PSJOA/psjoa.jar ファイルを指定します。  
  
### <a name="set-environment-variable-and-use-component-interface"></a>環境変数を設定して、コンポーネント インターフェイスを使用  
PeopleSoft の詳細については、PeopleSoft のドキュメントを参照してください。  
  
#### <a name="set-classpath-environment-variable"></a>ClassPath 環境変数を設定します。  

**JAVA_HOME を更新します。**    
  
 たとえば、JDK インストールを指すように JAVA_HOME 変数を設定します。  
  
```  
set JAVA_HOME=C:\j2sdk1.4.2_06  
```  
  
 **CLASSPATH を更新します。**  
  
使用するには、コンポーネント インターフェイス (PeopleSoft 8 のみ) する必要があります、クラスパスを PeopleSoft コンポーネント インターフェイスを含める jar ファイル更新します。
  
1.  **コントロール パネルの **、開かれている**システム**です。  
  
2.  **詳細**] タブで、**環境変数**、し、[**クラスパス**です。  
  
3.  パスを追加します。 たとえば、次のように入力します。  
  
    ```  
    <PeopleSoft_Home>\web\PSJOA\psjoa.jar  
    ```  
  
 BizTalk Adapter for PeopleSoft Enterprise では、psjoa.jar ファイルが必要です。 これは、送信ポートの作成時に実行されます。 詳細については、アダプターのドキュメントの「Setting Transport Properties in PeopleSoft System」(PeopleSoft システムでのトランスポートのプロパティの設定) を参照してください。  
  
> [!NOTE]
>  BizTalk Adapter for PeopleSoft Enterprise で正しい DLL を取得するように、これらのディレクトリの 1 つだけを PATH に保持させます。 PeopleSoft の目的のバージョンに対して環境を正しくセットアップできないと、トレースが困難なエラーになるおそれがあります。  
  
#### <a name="use-component-interfaces"></a>コンポーネント インターフェイスの使用  
  
<a name="BKMK_CustomCI"></a>   
##### <a name="upload-a-custom-ci-into-peoplesoft"></a>PeopleSoft にカスタム CI をアップロードします。  
 BizTalk Adapter for PeopleSoft Enterprise では、PeopleSoft アプリケーションに対する変更が必要です。 コンポーネント インターフェイスを使用するには、PeopleSoft に、カスタム コンポーネント インターフェイスの GET_CI_INFO をアップロードする必要があります。 アダプターを使用するには、最初のセットアップ時に GET_CI_INFO をインポートする必要があるだけです。 アダプターでは GET_CI_INFO を使用して、PeopleSoft 内の他の既存のコンポーネント インターフェイスについての情報を取得します。  
  
 このセクションでは、カスタム コンポーネント インターフェイスで PeopleSoft コンポーネント インターフェイスを参照することのできるを手動でインポートする方法について説明します。 カスタム メソッドでは、コンポーネント インターフェイスがインストールされている、そのコンポーネント インターフェイスのプロパティを使用したり変更したりしないことに注意してください。 カスタム コンポーネント インターフェイスをインポートするには、次の方法のいずれかを使用できます。  
  
-   カスタム メソッドをインポートするためのコンポーネントを新規に作成します。  
  
-   キーが含まれていない既存のコンポーネント (たとえば、INSTALLATION_RS) を使用します。  
  
 単純なコンポーネント インターフェイスには、キーを含めないでください。 特定のコンポーネント インターフェイスにキーが含まれているかどうかが不明な場合は、SQL クエリ ツールを使用して、次の簡潔な SQL ステートメントを実行できます。 これは、キーのないアプリケーションのすべてのコンポーネント インターフェイスの一覧を表示します。  
  
```  
select distinct BCNAME  
from PSBCITEM bc1  
where not exists  
(select 1  
from PSBCITEM bc2  
where bc1.BCNAME = bc2.BCNAME  
and bc2.BCTYPE in (1, 2))  
```  
  
 PeopleSoft のドキュメントに従って、BizTalk Adapter for PeopleSoft Enterprise のカスタム メソッドを格納するための一意の単純なコンポーネントを作成することができます。 また、既存のコンポーネント インターフェイスの 1 つを複製して、それをカスタム メソッドの格納に使用することもできます。  
  
 GET_CI_INFO にキーがないことを確認するには、PeopleTools アプリケーション デザイナのコンポーネント インターフェイスのテスト ツールを実行します。  
  
<a name="BKMK_NewCom"></a>   
##### <a name="create-a-new-component-interface"></a>新しいコンポーネント インターフェイスを作成します。  
 PeopleSoft アプリケーション デザイナを使用して、新しいコンポーネント インターフェイスを作成する手順に従います。
  
1.  開く、 **PeopleSoft アプリケーション デザイナ**です。  
  
2.  3 層の接続の種類を入力し、クリックして**OK**です。 たとえば、アプリケーション サーバーを一覧から選択します。  
  
3.  アプリケーション デザイナーでの**ファイル**メニューの **新規**です。  
  
4.  **新規** ダイアログ ボックスで、 **コンポーネント インターフェイス**, 、 をクリックし、 **OK**します。  
  
5.  **[選択]** をクリックします。  
  
6.  すべてのコンポーネントの一覧で、任意の単純なコンポーネントを選択します。 たとえば、INSTALLATION_RS または作成した新しい PeopleSoft コンポーネントを選択します。  
  
 カスタム メソッド使用またはにインストールされているコンポーネント インターフェイスのプロパティを変更します。  
  
 この単純なコンポーネント インターフェイスでは、キーを含めることはできません。 特定のコンポーネント インターフェイスにキーが含まれているかどうかが不明な場合は、SQL クエリ ツールを使用して、次の簡潔な SQL ステートメントを実行できます。 これは、キーのないアプリケーションのすべてのコンポーネント インターフェイスの一覧を表示します。  
  
```  
select distinct BCNAME from PSBCITEM bc1 where not exists (select 1 from PSBCITEM bc2 where bc1.BCNAME = bc2.BCNAME and bc2.BCTYPE in (1, 2))  
```  
  
> [!NOTE]
>  BizTalk adapter for PeopleSoft Enterprise のカスタム メソッドを格納するための一意の単純なコンポーネントを作成する PeopleSoft のドキュメントも行うことができます。  
  
 GET_CI_INFO にキーがないことを確認するには、PeopleTools アプリケーション デザイナのコンポーネント インターフェイスのテスト ツールを実行します。  
  
##### <a name="check-component-interface"></a>コンポーネント インターフェイスをチェックします。  
 Microsoft BizTalk Adapter for PeopleSoft の GET_CI_INFO の PeopleSoft システムへのアップロードが完了しました。 GET_CI_INFO は、ユーザー定義のカスタム コンポーネント インターフェイスです。 このインターフェイスには、ユーザー定義メソッドが含まれています。 GET_CI_INFO コンポーネント インターフェイスを使用すれば、Microsoft アダプター ウィザードによって、PeopleSoft システム内のコンポーネント インターフェイスを参照できます。 GET_CI_INFO を検索して展開し、そのユーザー定義メソッドを表示できます。  
  
> [!NOTE]
>  ユーザー定義メソッドの詳細については、アダプターのドキュメントの「PeopleSoft:: コンポーネント インターフェイス ユーザー定義メソッド」を参照してください。  
  
##### <a name="set-the-component-interface-security"></a>コンポーネント インターフェイスのセキュリティを設定します。  
 カスタムの GET_CI_INFO PeopleSoft コンポーネント インターフェイスを PeopleSoft にインストールすると後のセキュリティ設定の**GetCINamespace**、 **GetDetails**、および**GetCollections**BizTalk Adapter for PeopleSoft Enterprise のメソッドです。 これは、カスタム コンポーネントまたはユーザー定義メソッドの作成時の標準的な手法です。  
  
> [!NOTE]
>  次の手順では、サポートされているすべてのモードで、サポートされている PeopleSoft のすべてのリリースのセキュリティを構成する方法について説明します。  
>   
>  コンポーネント インターフェイスのセキュリティを構成するには  
  
1.  をポイント**PeopleTools**、 をポイント**セキュリティ**、 をポイント**アクセス許可とロール**、し、 **Permission Lists**です。  
  
2.  **セキュリティの維持**ウィンドウで、 をクリックして**検索**、関連する選択**アクセス許可の一覧**、し、一覧から適切なハイパーリンクをクリックします。  
  
3.  **アクセス許可リスト**、右側のペインが横に、右矢印をクリックして、 **sign-on Times**を表示するタブ、**コンポーネント インターフェイス**タブです。  
  
4.  クリックして、 **コンポーネント インターフェイス**  タブをクリックします。  
  
5.  新しい行を追加するには、プラス記号 (+) をクリックする、**コンポーネント インターフェイス** ボックスの一覧です。  
  
6.  選択、 **GET_CI_INFO**クリックしてコンポーネント インターフェイス**編集**です。  
  
7.  メソッドに設定する**フル アクセス**、 をクリックして**Full Access (All)**、クリックして**ok**です。  
  
8.  一番下までスクロール、**コンポーネント インターフェイス**ウィンドウ、およびクリック**保存**です。  
  
##### <a name="test-the-component-interface"></a>コンポーネント インターフェイスをテストします。  
 BizTalk Adapter for PeopleSoft Enterprise とともに提供される GET_CI_INFO コンポーネント インターフェイスのセキュリティの構成が完了しました。 PeopleSoft コンポーネント インターフェイスの準備が完了し、PeopleSoft コンポーネント インターフェイスを参照できます。  
  
 アプリケーション デザイナでコンポーネント インターフェイスをテストするには、次の手順を実行します。  
  
 コンポーネント インターフェイスをテストするには  
  
1.  開始、 **PeopleSoft アプリケーション デザイナ**です。  
  
2.  **ファイル**] メニューのをポイント**開く**、し、[**定義コンポーネント インターフェイスを =** です。  
  
3.  コンポーネント インターフェイスのリストから選択**GET_CI_INFO CI**です。  
  
4.  GET_CI_INFO を開いた後に、コンポーネント インターフェイス定義の右側のペイン内を右クリックしを選択し、 **Test Component Interface**です。  
  
**Component Interface Tester**ウィンドウが開きます。 キーは一覧表示されないはずです。 GET_CI_INFO にキーが含まれている場合、または別のオプションの選択がある場合は、アプリケーション デザイナーに戻るし、GET_CI_INFO からすべてのキーを削除します。  
  
## <a name="install-steps"></a>インストール手順
 インストールする前にすることを確認して BizTalk Server と、アダプターのすべてのソフトウェア前提条件がインストールされています。 Setup を実行する前に、すべてのアプリケーションを閉じることをお勧めします。  
  
1.  BizTalk Server を実行**Setup.exe****インストール Microsoft BizTalk Adapters**を選択し、 **Microsoft BizTalk Adapters for Enterprise Applications をインストール**。  
  
    > [!NOTE]
    >  - 次のコマンドを使用して、サイレント インストールを実行することもできます: msiexec/i < msi\> /qn/l * < logfile\> --場所 < ログ ファイル\>はオプションですが、インストールの失敗が発生した場合に便利です。  
    >  - このインストールでは、PATH 環境変数が更新されます。 正しい変数を使用していることを確認するには、インストールのコマンド ウィンドウを閉じて、変数を更新します。  
  
2.  受け入れる、**使用許諾契約書**を選択し、**次**です。
  
3.  入力、**顧客情報**を選択し、**次**です。  
  
4.  選択、**完了**または**カスタム**インストール。 
  
    -   **完全な**: エンタープライズ アプリケーションの場合、すべてのプログラム機能では、すべての Microsoft BizTalk Adapters をインストールし、開発と実行時に使用します。  
  
    -   **カスタム**: アダプターと機能をインストールしてインストールされているを選択します。  
  
    変換先を設定するには、次のように選択します。**参照**、し、インストール パスを設定します。  
  
    選択**次**を続行します。  
  
5. **インストール**を選択して**完了**を完了するとします。  
  
> [!IMPORTANT]
>  インストール中に次のエラーが発生した可能性があります。  
>   
>  `Error 1609. An error occurred while applying security settings. CREATOR OWNER is not a valid user or group`  
>   
>  このエラーを回避する、次の操作をもう一度インストールを実行します。  
>   
>  1. コマンド プロンプトを開きます
>  2. 型:`net user "CREATOR OWNER" /add`です。 これにより、CREATOR OWNER と呼ばれる新しいユーザーが作成されます。
>  3. 型:`net localgroup Users /add`です。 これにより、ユーザーと呼ばれる新しいグループが作成されます。
  
BizTalk Server にアダプターを追加するには、このトピック内の「BizTalk 管理者にアダプターを追加する」を参照してください。

## <a name="add-adapters-to-biztalk-admin"></a>BizTalk 管理者にアダプターを追加します。
  
> [!NOTE]
>  (1 台のコンピューター上のランタイムのみのインストールと別のコンピューター上の管理ツールのみインストール) の複数コンピューター環境に BizTalk をインストールする場合は、両方のコンピューターで for Enterprise Applications BizTalk アダプターをインストールする必要があります。  
  
1.  BizTalk Server 管理コンソールを開き、展開**Microsoft BizTalk Server**の順に展開および**プラットフォームの設定**です。  
  
2.  右クリック**アダプター****新規**、し、**アダプター**です。  
  
3.  などの名前を入力**PeopleSoft**です。  
  
4.  入力した名前を選択、**アダプター**一覧**OK**です。  
   
## <a name="post-install---jd-edwards-oneworld"></a>ポスト インストール-JD Edwards OneWorld  
 Microsoft BizTalk Adapter for JD Edwards OneWorld は、サポートされているデータベースおよびサーバー システムと Microsoft BizTalk Server とのインターフェイスとなる送信アダプターで構成されています。 送信アダプターでは、BizTalk Server からサーバー システムの呼び出しを起動することができます。 送信アダプター (BizTalk Server 管理の送信ハンドラー) の構成では、SQL データベースの場所を指定します。  
  
 BizTalk Adapter for JD Edwards OneWorld の使用方法、およびそのモデルと BizTalk Server モデル間のマッピングについては、アダプターのドキュメントを参照してください。  
  
### <a name="single-sign-on"></a>シングル サインオン  
 BizTalk Adapter for JD Edwards OneWorld のエンタープライズ シングル サインオン (SSO) のサポートを提供します。 SSO の使用を選択した場合、**トランスポートのプロパティ** ページで、資格情報は SSO 資格情報データベース内の関連アプリケーションが使用されます。 関連アプリケーションとは、資格情報を必要とするバック エンドのアプリケーションを表しています。  
  
### <a name="installed-components"></a>インストールされているコンポーネント  

* アダプターのインストールでは、インストールし、グローバル アセンブリ キャッシュ (GAC) に、次のコンポーネントを登録します。 エクスプ ローラーで、アセンブリ フォルダーを開くことによって、登録を確認することができます (< %windir% > \assembly) を使用して、または、 `gacutil /l` Visual Studio コマンド プロンプトから。

    -   Microsoft.BizTalk.Adapters.BizUtil.dll    
    -   Microsoft.BizTalk.Adapters.JDEProperties.dll    
    -   Microsoft.BizTalk.Adapters.CoreManagement.dll    
    -   Microsoft.BizTalk.Adapters.CoreReceiver.dll    
    -   Microsoft.BizTalk.Adapters.CoreTransmitter.dll  

  
* btsTask.exe をインストールして、展開、`Microsoft.BizTalk.Adapters.JDEProperties.dll`ファイルを GAC にします。 BizTalk Server 展開ログの結果は*\Program Files\Microsoft BizTalk Adapters for Enterprise applications \jdedeploy.html*と**jdeDeploy.xml**です。
  
* アダプターに固有のファイルがインストールされている*Program Files*と*Program files \common Files*です。  
  
* `sdk\`がインストールされている*Enterprise applications \ j. d. の Program files \microsoft BizTalk AdaptersEdwards OneWorld(r)* です。
  
* * Program エンタープライズ Applications\JD Edwards OneWorld(r) for files \microsoft BizTalk Adapters\*次のファイルが含まれています。  
  
    -   classes\JDEJAccess.jar    
    -   Config\ J.D. Edwards OneWorld(r) \BTSREL.exe    
    -   Config\ J.D. Edwards OneWorld(r) \jdearglist.txt    
    -   Config\ J.D. Edwards OneWorld(r) \jdeinterop.ini  
  
* * プログラムの files \common files \microsoft BizTalk Adapters for Enterprise applications \bin\*次のファイルが含まれています。  
  
    -   Microsoft.BizTalk.Adapters.JDEProperties.dll    
    -   jdecba.dll  
  
## <a name="post-install---jd-edwards-enterpriseone"></a>ポスト インストール-JD Edwards EnterpriseOne  
 Microsoft BizTalk Adapter for JD Edwards EnterpriseOne には、サポートされているデータベースと BizTalk Server へのサーバー システムとのインターフェイスとなる送信アダプターが含まれています。 送信アダプターを使用すると、BizTalk Server からサーバー システムの呼び出しを起動することができます。  
  
 BizTalk Adapter for JD Edwards EnterpriseOne では、エンタープライズ シングル サインオン (SSO) のサポートを提供します。 SSO の使用を選択した場合、**トランスポートのプロパティ** ページで、資格情報は SSO 資格情報データベース内の関連アプリケーションが使用されます。 関連アプリケーションとは、資格情報を必要とするバック エンドのアプリケーションを表しています。  
  
### <a name="installed-components"></a>インストールされているコンポーネント  
* アダプターのインストールでは、インストールし、グローバル アセンブリ キャッシュ (GAC) に、次のコンポーネントを登録します。 エクスプ ローラーで、アセンブリ フォルダーを開くことによって、登録を確認することができます (< %windir% > \assembly) を使用して、または、 `gacutil /l` Visual Studio コマンド プロンプトから。
  
    -   Microsoft.BizTalk.Adapters.BizUtil.dll    
    -   Microsoft.BizTalk.Adapters.JDEProperties.dll    
    -   Microsoft.BizTalk.Adapters.CoreManagement.dll    
    -   Microsoft.BizTalk.Adapters.CoreReceiver.dll    
    -   Microsoft.BizTalk.Adapters.CoreTransmitter.dll    

* アダプターに固有のファイルがインストールされている、 *Program files \common files \microsoft BizTalk Adapters for Enterprise applications \bin*フォルダーです。 このフォルダーには、次のファイルが含まれています。  
  
    -   Jdecba.dll    
    -   Microsoft.BizTalk.Adapters.JDEProperties.dll  
  
* 次のファイルがインストールされている*Enterprise applications \j.d. の Program files \microsoft BizTalk Adapters です。Edwards EnterpriseOne(r)*:  
  
    -   Bin\BTAJDEEnterpriseOneTrace.cmd    
    -   Classes\JDEDynAccess.jar    
    -   Config\btaJDEEnterpriseOneTrace.mof    
    -   Config\jdearglist.txt    
    -   Config\jdeinterop.ini    
    -   Config\jdelog.properties    
    -   Sdk  
  
 
## <a name="post-install---peoplesoft-enterprise"></a>ポスト インストール-PeopleSoft Enterprise  
 Microsoft BizTalk Adapter for PeopleSoft Enterprise には、サポートされているデータベースと BizTalk Server へのサーバー システムのインターフェイスと送信アダプターが含まれています。 送信アダプターを使用すると、BizTalk Server からサーバー システムの呼び出しを起動することができます。 送信アダプター (BizTalk Server 管理の送信ハンドラー) の構成では、SQL データベースの場所を指定します。  
  
 BizTalk Adapter for PeopleSoft Enterprise では、エンタープライズ シングル サインオン (SSO) のサポートを提供します。 SSO の使用を選択した場合、**トランスポートのプロパティ** ページで、資格情報は SSO 資格情報データベース内の関連アプリケーションが使用されます。 関連アプリケーションとは、資格情報を必要とするバック エンドのアプリケーションを表しています。  
  
 アダプターのインストールには、サンプルが \sdk ディレクトリに含まれています。  
  
### <a name="installed-components"></a>インストールされているコンポーネント  
* アダプターのインストールでは、インストールし、グローバル アセンブリ キャッシュ (GAC) に、次のコンポーネントを登録します。 エクスプ ローラーで、アセンブリ フォルダーを開くことによって、登録を確認することができます (< %windir% > \assembly) を使用して、または、 `gacutil /l` Visual Studio コマンド プロンプトから。
  
    -   Microsoft.BizTalk.Adapters.BizUtil.dll    
    -   Microsoft.BizTalk.Adapters.CoreManagement.dll    
    -   Microsoft.BizTalk.Adapters.CoreReceiver.dll    
    -   Microsoft.BizTalk.Adapters.CoreTransmitter.dll    

* アダプターに固有のファイルがインストールされている*Program Files*と*Program files \common Files*です。 次のファイルがインストールされている*Enterprise Applications\PeopleSoft Enterprise (r) の Program files \microsoft BizTalk Adapters*:
  
    -   bin\BTAPeopleSoftTrace.cmd    
    -   config\btaPeopleSoftTrace.mof    
    -   config\GET_CI_INFO.pc    
    -   config\GET_CI_INFO.pc    
    -   sdk\  
  
* *Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications* contains the following files:  
  
    -   bin\psosa.dll    
    -   bin\Microsoft.BizTalk.Adapters.CoreManagement.dll    
    -   bin\Microsoft.BizTalk.Adapters.CoreReceiver.dll    
    -   bin\Microsoft.BizTalk.Adapters.CoreTransmitter.dll  
  
## <a name="post-install-overview---tibco-rendezvous"></a>インストール後の TIBCO Rendezvous の概要  
 Microsoft BizTalk Adapter 受信データ TIBCO Rendezvous が含まれています、サポートされているデータベースと BizTalk Server へのサーバー システムとのインターフェイスの機能を送信します。  
  
-   受信側では、サーバー システムからの送信である呼び出しをリッスンします。  
  
-   送信側を使用すると、BizTalk Server からサーバー システムの呼び出しを起動することができます。  
  
 Microsoft BizTalk Adapter for TIBCO Rendezvous を使用する方法の詳細とそのモデルと、BizTalk Server モデル間のマッピングについて、アダプターのドキュメントを参照してください。  
  
### <a name="installed-components"></a>インストールされているコンポーネント  
* アダプターのインストールでは、インストールし、グローバル アセンブリ キャッシュ (GAC) に、次のコンポーネントを登録します。 エクスプ ローラーで、アセンブリ フォルダーを開くことによって、登録を確認することができます (< %windir% > \assembly) を使用して、または、 `gacutil /l` Visual Studio コマンド プロンプトから。 
  
    -   Microsoft.BizTalk.Adapters.TibcoRV    
    -   Microsoft.BizTalk.Adapters.TibcoRV.Common    
    -   Microsoft.BizTalk.Adapters.TibcoRV.Service    
    -   Microsoft.BizTalk.Adapters.TibRV.Properties    
    -   Microsoft.BizTalk.Adapters.TibcoEMS    
    -   Microsoft.BizTalk.Adapters.TibcoEMS.Properties    
    -   Microsoft.BizTalk.Adapters.TibcoRVManagement    
    -   Microsoft.BizTalk.Adapters.TibcoRVReceiver  
    -   Microsoft.BizTalk.Adapters.TibcoRVTransmitter  
  
* アダプターに固有のファイルがインストールされている*プログラム ファイルおよび Program files \common Files*です。 次のファイルがインストールされている*Enterprise applications \ TIBCO(r) Rendezvous(r) の Program files \microsoft BizTalk Adapters*:  
  
    -   bin\BTATibcoRVTrace.cmd    
    -   bin\mbaRV.exe    
    -   bin\Microsoft.BizTalk.Adapters.TibcoRV.Common.dll    
    -   bin\Microsoft.BizTalk.Adapters.TibcoRV.dll    
    -   bin\Microsoft.BizTalk.Adapters.TibcoRV.Service.dll    
    -   bin\Microsoft.BizTalk.Adapters.BizUtil.dll    
    -   bin\Microsoft.BizTalk.Adapters.CoreManagement.dll    
    -   bin\Microsoft.BizTalk.Adapters.CoreReceiver.dll    
    -   bin\Microsoft.BizTalk.Adapters.CoreTransmitter.dll    
    -   bin\Microsoft.BizTalk.Adapters.TibRV.Properties.dll    
    -   Config\btaTibcoRVTrace.mof    
    -   sdk\  
  
* *Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications* contains the following files:  
  
    -   bin\tibcorvcba.dll    
    -   Microsoft.BizTalk.Adapters.CoreManagement.dll    
    -   Microsoft.BizTalk.Adapters.CoreReceiver.dll    
    -   Microsoft.BizTalk.Adapters.CoreTransmitter.dll  
  
### <a name="add-tibcorendezvousdll-to-the-gac"></a>TIBCO を追加します。GAC に Rendezvous.dll  
 BizTalk Adapter for TIBCO Rendezvous が必要です、 **TIBCO です。Rendezvous.dll**ファイル。 必要な最小バージョンは 1.0.3036.23330 FileVersion、製品のバージョン 8.1 に付属しています。 このアセンブリがインストールされていない場合、アダプターは例外をトリガーし、適切なメッセージを記録します。  
  
 遅延バインディングを使用して、アセンブリを読み込むときに、TIBCO の特定のバージョンの TIBCO Rendezvous アセンブリが失敗しないようにする必要があります。Rendezvous.dll と TIBCO です。Rendezvous.net モジュールは、ターゲット コンピューターではありません。
  
 **ランタイム コンポーネント**  
  
 TIBCO Rendezvous のランタイム コンポーネントがコンピューターにインストールされていることを確認します。 ランタイム コンポーネントは、TIBCO Rendezvous のインストール時にインストールする必要がある唯一のコンポーネントです。  

1. Visual Studio コマンド プロンプトで、TIBCO の場所にディレクトリを変更します。Rendezvous.dll ファイルです。 TIBCO Rendezvous の既定のインストールでは、この DLL のパスは**C:\TIBCO\TIBRV\BIN\TIBCO です。Rendezvous.dll**です。  
  
2. コマンド プロンプトで、次のように入力します:  
  
```
C:\TIBCO\TIBRV\BIN > gacutil /i TIBCO.Rendezvous.dll
```
  
 これにより、TIBCO.Rendezvous.dll で GAC の一覧が表示されます。 表示するには、一覧では、コントロール パネルの 開く**管理者ツール**、開かれている**Microsoft .NET Framework 構成**、開き、**アセンブリ キャッシュ**です。  
  
## <a name="post-install---tibco-enterprise-message-service"></a>インストール後、TIBCO Enterprise Message Service  
 Microsoft BizTalk Adapter 受信データ TIBCO Enterprise Message Service (EMS) が含まれています、サポートされているデータベースと BizTalk Server へのサーバー システムとのインターフェイスの機能を送信します。  
  
-   受信側では、サーバー システムからの送信である呼び出しをリッスンします。  

-   送信側を使用すると、BizTalk Server からサーバー システムの呼び出しを起動することができます。  
  
 BizTalk Adapter for TIBCO EMS を使用する方法の詳細とそのモデルと、BizTalk Server モデル間のマッピングについて、アダプターのドキュメントを参照してください。  
  
### <a name="installed-components"></a>インストールされているコンポーネント  
* アダプターのインストールのインストールおよび登録され、`Microsoft.BizTalk.Adapters.TibcoEMS.dll`グローバル アセンブリ キャッシュ (GAC) 内のファイルです。 エクスプ ローラーで、アセンブリ フォルダーを開くことによって、登録を確認することができます (< %windir% > \assembly) を使用して、または、 `gacutil /l` Visual Studio コマンド プロンプトからです。
  
* アダプターに固有のファイルがインストールされている*Program Files*と*Program files \common Files*です。 次のファイルがインストールされている*エンタープライズ Applications\TIBCO(r) エンタープライズ メッセージ Service(TM) の Program files \microsoft BizTalk Adapters*:  
  
    -   bin\BTATibcoEMSTrace.cmd    
    -   Microsoft.BizTalk.Adapters.TibcoEMS.dll    
    -   Config\btaTibcoEMSTrace.mof    
    -   sdk\  
  
* *Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\bin* folder contains the following files:  
  
    -   Microsoft.BizTalk.Adapters.CoreManagement.dll    
    -   Microsoft.BizTalk.Adapters.CoreReceiver.dll    
    -   Microsoft.BizTalk.Adapters.CoreTransmitter.dll  
  
    > [!NOTE]
    >  遅延バインディングを使用して、アセンブリを読み込むときに、TIBCO の特定のバージョンの TIBCO EMS アセンブリが失敗しないようにする必要があります。EMS.dll では、ターゲット コンピューターに存在しません。  
  
### <a name="add-tibcoemsdll-api-to-the-gac"></a>TIBCO を追加します。GAC に EMS.dll API  
 BizTalk Adapter for TIBCO EMS では、TIBCO.EMS.dll を GAC に追加することが必要です。 BizTalk Adapter for TIBCO EMS は、例外が発生し、このアセンブリがインストールされていない場合、適切なメッセージをログに記録します。  
  
1.  TIBCO EMS C# #API を BizTalk コンピューターにコピーします。  
  
2.  Visual Studio コマンド プロンプト では、c# API ファイルの場所にディレクトリを変更します。  
  
3.  Visual Studio コマンド プロンプトで、次のように入力します。  
  
    ```
    C:\\<TIBCO EMS Folder\>bin> gacutil /i TIBCO.EMS.dll
    ```
  
 これにより、TIBCO.EMS.dll が C:\Windows\assembly の一覧に表示されます。 または、コントロール パネルを開きます**管理者ツール**、開かれている**Microsoft .NET Framework**、再度開き、**アセンブリ キャッシュ**GAC の一覧を表示します。  
  
 **制限事項**  
  
 BizTalk Adapter for TIBCO EMS は、TIBCO を使用します。サーバーと通信するために EMS.dll です。 TIBCO.EMS.dll を使用する際の制限を次に示します。  
  
1.  TIBCO EMS クライアントで EMS に圧縮形式でメッセージを送信できるように、メッセージの圧縮は使用できません。  
  
2.  アダプターとサーバー間のメッセージの暗号化は使用できません。 TIBCO.EMS.dll では、OpenSSL ライブラリを使用した SSL 暗号化は許可されませんが、アダプターでは、ProductVersion 5.0 以降で SSL がサポートされています。  
  
3.  EMS 用の管理 API は、サポートされていません。  
  
## <a name="adapter-tracing"></a>アダプターのトレース

### <a name="enable-tracing"></a>トレースを有効にします。
 Windows のトレースで使用されるファイル名は、管理者が決定します。 アプリケーションでは、オペレーティング システムに書き込み、特定のバックエンド システムのログが必要になるまで、すべてのログを無視します。 これを行うには、BizTalk Adapters for Enterprise Applications の別のコマンド ファイルを実行します。 そのコマンドの引数の 1 つは、トレース情報をキャプチャするために使用するファイルの名前です。 詳細については、「Windows トレース イベントの」(」を参照) を参照してください。
  
 トレース ファイルをインストールする * \Program Files\Microsoft BizTalk Adapters for Enterprise Applications\*です。  
  
-   bin\BTATrace.cmd    
-   config\btaTrace.mof  
  
### <a name="use-windows-trace-event"></a>Windows トレース イベントを使用します。  
 アダプターでは、エラー メッセージ、警告メッセージ、および情報メッセージを Windows イベント ビューアーに記録します。 その他のトレース メッセージを表示するには、Event Tracing for Windows (ETW) ツールを使用します。 ETW が有効である場合、このメッセージを受信する *.etl ファイルが作成されます。 このファイルはバイナリ形式であり、読み取るには変換する必要があります。 これを行うには、解釈に利用できるコンシューマー アプリケーションが必要、 \*.etl ファイル、Windows tracerpt.exe や tracedmp.exe などです。  
  
### <a name="etw-components"></a>ETW コンポーネント
  
 Windows イベント トレーシングには 3 つのコンポーネントがあります。  
  
* **コント ローラー アプリケーション:** にアクティブとプロバイダーを非アクティブ化します。 たとえば、tracelog.exe または logman.exe です。  
  
    PATH 環境変数を、tracelog.exe の場所を指すように設定します。 これにより、その BTA < アダプター名\>Trace の呼び出しは、システムの tracelog.exe を見つけることができます。 既定では、BTA < Adapter 名前\>トレースは、現在のパスを検索します。  
  
    > [!NOTE]
    >  tracelog.exe は Microsoft SDK おり、Microsoft BizTalk Adapters for Enterprise Applications コマンドと互換性があります。 logman.exe の使い方については、logman のマニュアルを参照してください。  
  
* **コンシューマー アプリケーション:** 記録されたイベントの読み取り。  
  
    コンシューマー アプリケーションで .etl ファイル内のイベントを読み取るには、Windows イベント トレーシングでそれらのイベントを .etl ファイルにダンプする必要があります。 通常、この作業は、コントローラーがトレーシングを非アクティブ化するときに行われます。  
  
    コンシューマー アプリケーションを使用して、トレースを非アクティブにせず、リアルタイムのオプションを使用してトレースで、コント ローラーによってアクティブ化する必要があります **< リアルタイム\> =-rt**します。  
  
* **プロバイダー:** イベントを提供するために使用します。  
  
    各アダプターには、5 つの異なるプロバイダーが含まれています。 これらは Windows Management Instrumentation (WMI) に登録されます。 root\WMI\EventTrace パス内で登録プロバイダーを検索するには、WMI CIM Studio などのツールを使用します。  
  
    5 つのプロバイダーを使用すると、さまざまな種類のメッセージをログに記録できます。  
  
        -   **Receiver Logging Provider**: The <Trace element\> switch is - **receiver**.    
        -   **Receiver CastDetails Provider**: The <Trace element\> switch is - **castDetailsReceive**.    
        -   **Transmitter Logging Provider**: The <Trace element\> switch is - **transmitter**.    
        -   **Transmitter CastDetails Provider**: The <Trace element\> switch is - **castDetailsTransmit**.    
        -   **Management Logging Provider**: The <Trace element\> switch is - **management**.  
  
ETW を使用するには、特定のアダプターのコマンドを実行します。`BTA<Adapter Name\>Trace.cmd`です。 このコマンドは次のように使用します。  
  
```  
BTA<Adapter Name>Trace <Trace element> -start [-cir <MB>|   
    -seq <MB>] [-rt] logfile  
BTA<Adapter Name>Trace <Trace element> -stop  
  
```  
  
 各要素の説明は次のとおりです。  
  
**< トレース要素\>** プロバイダーの種類は、(必須)。 使用可能なオプションは次のとおりです。  
  
 **-castDetailsTransmit**  
  
 **-送信機能**  
  
 **-castDetailsReceive**  
  
 **-受信者**  
  
 **管理**  
  
 **-開始、停止:** アクティブ化またはプロバイダーを非アクティブ化します。  
  
 **-cir < MB\>:** サイズおよびファイルの種類。 **-cir** は循環ファイルです。 **< MB\>:** サイズ (メガバイト単位)。  
  
 **-seq < MB\>:** サイズおよびファイルの種類。 **-seq** シーケンシャル ファイルです。 **< MB\>:** サイズ (メガバイト単位)。  
  
 **-rt:** でリアルタイムに設定します。  
  
 **ログ ファイル:** ログ ファイルの名前 (既定では c:\rtlog.etl) です。  
  
 以下に例を示します。  
  
```  
BTAXXXTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTAXXXTrace -transmitter -stop  
  
```  
  
> [!NOTE]
>  .etl ファイルの書式を設定するには、tracerpt.exe コマンドを使用します。  

## <a name="next-steps"></a>次の手順
* [JD Edwards EnterpriseOne アダプター](../core/jd-edwards-enterpriseone-adapter.md)
* [JD Edwards OneWorld アダプター](../core/jd-edwards-oneworld-adapter.md)
* [PeopleSoft Enterprise アダプター](../core/peoplesoft-enterprise-adapter.md)
* [TIBCO Enterprise Message Service アダプタ](../core/tibco-enterprise-message-service-adapter.md)
* [TIBCO Rendezvous アダプター](../core/tibco-rendezvous-adapter.md)
