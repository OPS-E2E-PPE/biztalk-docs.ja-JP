---
title: BizTalk Adapters for Enterprise Applications インストール |Microsoft Docs
description: 要件と BizTalk Server では、JD Edwards OneWorld では、JD Edwards EnterpriseOne では、PeopleSoft Enterprise、TIBCO Rendezvous では、TIBCO Enterprise Message Service のインストール手順
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
ms.openlocfilehash: 7777b7027e51460e79a6dff6a591d8faa4fe57e3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987523"
---
# <a name="install-and-configure-the-microsoft-biztalk-adapters-for-enterprise-applications"></a>インストールし、Microsoft BizTalk Adapters for Enterprise Applications に構成します。 
  
 Microsoft BizTalk Adapters for Enterprise Applications には、次のアダプターが含まれています。  
  
-   Microsoft BizTalk Adapter for JD Edwards OneWorld  
  
-   Microsoft BizTalk Adapter for JD Edwards EnterpriseOne  
  
-   Microsoft BizTalk Adapter for PeopleSoft Enterprise  
  
-   Microsoft BizTalk Adapter for TIBCO Rendezvous  
  
-   Microsoft BizTalk Adapter for TIBCO Enterprise Message Service  


> [!IMPORTANT]
> - 構成変更を加える前に、すべてのデータをバックアップします。
> - 構成変更を加える前に、特定のエンタープライズ アプリケーションを経験するある必要があります。
  
## <a name="supported-versions--requirements"></a>サポートされているバージョンと要件

||要件|  
|---|---|
|オペレーティング システム|アダプターには、BizTalk Server と同じ OS がサポートされています。<ul><li>[BizTalk Server 2016 の要件](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)</li><li>[BizTalk Server 2013 R2/2013 の要件](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md)</li></ul>|
|サポートされている enterprise システム|[サポートされている基幹業務 (LOB) とエンタープライズ システム](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)サポートされているバージョンを一覧表示 |
|JD Edwards OneWorld XE | <ul><li>Windows 上の JD Edwards エンタープライズ サーバー</li><li>Windows 上の JD Edwards Deployment サーバー</li></ul>|
|JD Edwards EnterpriseOne | アダプターは、データベースのドライバーが必要になる JDBC を使用して、JD Edwards EnterpriseOne API を呼び出します。 JD Edwards EnterpriseOne を SQL データベースとともにインストールする場合、MS-SQL のドライバーが必要です。 同様に、Oracle データベースを JD Edwards EnterpriseOne をインストールした場合に、Oracle ドライバーを必要または、DB2 ドライバーが必要な DB2 データベースをインストールした場合。 |
|PeopleSoft Enterprise | <ul><li>Sun Systems Java Development Kit (JDK)</li><li>PeopleSoft ツール リリース</li><li>PeopleSoft アプリケーションをリリースします。</li><li>このアダプターには、PeopleSoft アプリケーションへの変更が必要です。 コンポーネント インターフェイスを使用するには、PeopleSoft にカスタム コンポーネント インターフェイスの GET_CI_INFO をアップロードします。 GET_CI_INFO.pc は Program files \common files \microsoft BizTalk adapters Enterprise Applications\PeopleSoft Enterprise(r) \Config\ です。</li></ul>|
|TIBCO Rendezvous | <ul><li>TIBCO Rendezvous の実行時コンポーネントは、BizTalk Adapter for TIBCO Rendezvous が実行されているコンピューターにインストールする必要があります。</li><li>TIBCO Rendezvous のライセンスは、BizTalk Adapter for TIBCO Rendezvous が実行されているコンピューターで構成される必要があります。</li><li>TIBCO Rendezvous のバイナリ ディレクトリが、環境変数の PATH の値、または BizTalk Server の各 Rendezvous ポートで指定されて、アダプターに認識されている必要があります。 これは、Rendezvous のアセンブリが、そのライブラリと実行可能ファイルを見つけるために必要です。</li></ul>|
|TIBCO Enterprise Message Service | Enterprise Message Service (EMS) のバージョン 5.x 以降、クライアント SDK (TIBCO EMS c# API を使用) が含まれています。 BizTalk Adapter for TIBCO EMS では、これを使用して、サーバーと通信します。 |


## <a name="jd-edwards-oneworld-xe"></a>JD Edwards OneWorld XE

このセクションでには、BizTalk Server と JD Edwards OneWorld XE の Microsoft BizTalk Adapter の使用に関する重要な情報が含まれています。
  
### <a name="create-the-jar-files"></a>JAR ファイルを作成します。
 ここでは、Microsoft BizTalk Adapter for JD Edwards OneWorld を操作するための JD Edwards OneWorld の要件について説明します。  
  
#### <a name="jar-files-and-the-classpath"></a>JAR ファイルと CLASSPATH  
 JD Edwards OneWorld JAR ファイルは、アダプターに使用可能なである必要があります。 たとえば、バージョンの B7.3.3.3 に接続する場合、次の jar ファイルが必要です。 接続するサーバーに応じて、jar ファイルの一覧を変更する可能性があります。
  
- Connector.jar    
- Kernel.jar  
  
  これらのファイルは、JD Edwards OneWorld を実行しているコンピューターの次の場所にあります。  
  
- JD Edwards OneWorld XE_install_Directory\System\classes\Connector.jar    
- JD Edwards OneWorld XE_install_Directory\System\classes\Kernel.jar  
  
  これらのファイルは任意の場所にコピーできますが、JAR ファイルの場所は CLASSPATH に指定する必要があります。 CLASSPATH には、ファイルの完全なパスと JAR ファイルの名前の両方 (セミコロンで区切る) を含める必要があります。  
  
  BizTalk Adapter for JD Edwards OneWorld では、JD Edwards OneWorld で使用するための JDEJAccess JAR ファイルを提供します。 既定では、JDEJAccess.jar ファイルが参照されている*Program files \common files \microsoft BizTalk Adapters for Enterprise applications \j.d. します。Edwards OneWorld(r) \classes\JDEJAccess.jar*します。 
  
> [!NOTE]
>  BizTalk Adapter for JD Edwards OneWorld を使用するには、jdeinterop.ini ファイルの登録を確認する必要があります。 このファイルへのパスを含めることを確認、 **JDE トランスポートのプロパティ**で BizTalk Server 送信ポートを作成するときのページします。 詳細については、「カスタマイズ jdeinterop.ini ファイル」を参照してください。  
  
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
  
### <a name="verify-your-setup"></a>設定を確認します。  
  
1.  サービス パック番号を含む、サポートされているバージョンを使用して ([サポートされている基幹業務 (LOB) とエンタープライズ システム](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx))。 サービス パック (ESU および ASU) では、システム バイナリを更新します。 前提条件のサービス パックには、インポート用の ASU/ESU というメニューの選択項目が用意されています。  
  
2.  C ドライブとは異なる場合、ログ記録の適切なドライブを使用する jdeinterop.ini ファイルを構成します。たとえば、ディレクトリの TEMP ディレクトリが領域外の場合に、JD Edwards OneWorld の更新が失敗します。  
  
3.  JD Edwards OneWorld のフィールドの左右の埋め込み用の構成ファイルを追加する必要があるかどうかを判断します。  
  
4.  コンピューター上の任意のプログラムから javac コマンドと java コマンドを有効にするには、JAVA_HOME 環境変数が Java Development Kit (JDK) のインストール場所を指していることを確認します。  
  
5.  CLASSPATH 環境変数が設定されていることを確認します。 これにより、BizTalk Adapter for JD Edwards OneWorld を Kernel.jar と Connect.jar ファイルを検索できます。  
  
    JAR ファイルのパスは、大文字小文字が区別されます。  
  
6.  次のコマンド (大文字小文字が区別されます) を入力して、環境をテストします。  
  
    ```  
    javap -s -p com.microsoft.jde.JDEJAccess  
    ```  
  
7.  指定するコマンドの javap は、Java クラス ファイルの逆アセンブラーです。  
  
    ```  
    http://java.sun.com/j2se/1.3/docs/tooldocs/solaris/javap.html  
    ```  
  
8.  `javap`コマンド クラス ファイルを逆アセンブルします。 その出力は、使用するオプションによって異なります。 オプションが使用されていない場合、javap は、保護されているパッケージとパブリック フィールドとそれに渡されるクラスのメソッドを出力します。 javap では、その出力を stdout に出力します。  
  
     エラーがなければ、すべての Java ファイルとそれらの依存関係は CLASSPATH にあります。  
  
9. ローカル ホスト ファイルを構成することで、DNS 解決を設定 (*C:\WINNT\system32\drivers\etc\hosts*)、JD Edwards OneWorld システムのサーバーの名前に置き換えます。  
  
### <a name="create-and-install-the-custom-package"></a>作成し、カスタム パッケージをインストールします。  
BizTalk Adapter for JD Edwards OneWorld の使用に BTSREL カスタム パッケージをインストールします。 このセクションについて説明します。  
  
-   JD Edwards OneWorld のカスタム パッケージの作成プロセス  
-   作成して、BTSREL をインストールする方法  
-   JD Edwards OneWorld で作成された BTSREL オブジェクト
  
> [!NOTE]
>  BTSREL.exe はカスタム パッケージです (JD Edwards OneWorld の用語では、自動化されたソフトウェア更新プログラム (ASU))。 このパッケージには、メタデータを抽出するためのビジネス関数が含まれています。 カスタム パッケージは、JD Edwards OneWorld の特定の構成とバージョン用に作成してください。  
  
#### <a name="define-a-custom-package"></a>カスタム パッケージを定義します。  
 カスタム パッケージとは、リリース後の成果物であり、法規制の変更や機能強化などの特定の目的のためのソフトウェア変更を提供します。 これらのカスタム パッケージは、特定の機能向けに作成されます。 たとえば、BTSREL はメタデータを抽出するために作成されます。 BTSREL カスタム パッケージをインストールすると、JD Edwards OneWorld 環境内の選択したモジュールが更新されます。 更新を行うには、適切な JD Edwards OneWorld の環境に BTSREL オブジェクトをマージする必要があります。 BTSREL によって更新されるモジュールの詳細な一覧については、「モジュールの一覧」を参照してください。  
  
#### <a name="install-the-btsrel-custom-package"></a>BTSREL カスタム パッケージをインストールします。   
ダウンロード[BTSREL](https://www.microsoft.com/download/details.aspx?id=56113)します。 展開サーバーにインストールし、エンタープライズ サーバーに配置します。  
  
 既存の BTSREL.exe パッケージは、B7333 バージョンと直接動作します。 パッケージがし B7334 バージョンでは、作業をするには。  
  
1. BTSREL.exe をダウンロードして、BTSREL.exe の内容を作業フォルダーに展開します。  
  
2. 両方を変更、 **ReleaseLevelRequired**と**リリース**B7334 に Deployment.Inf ファイル内の値。  
  
3. セットアップを実行します。  
  
   BTSREL をインストールするには次が必要です。  
  
-   展開サーバーのインストール    
-   Installation Workbench  
  
#### <a name="install-btsrel-on-the-deployment-server"></a>展開サーバー上の BTSREL をインストールします。  
 カスタムでは、Windows オペレーティング システムでは、上でのみ機能をパッケージ化し、展開サーバーで使用されます。 展開サーバー上に構築され、エンタープライズ サーバーに配置しする必要があります。 エンタープライズ サーバーは、通常実稼働サーバーで、Windows または UNIX のオペレーティング システムのいずれかの上に存在します。  
  
> [!NOTE]
>  ASU を JD Edwards OneWorld デプロイメント サーバーに適用する場合であることを確認**Update**モード。 **実証**モードが一方、ASU にバグがないことを確認**Update** ASU を適用するときのモードを指定します。  
  
1.  ユーザーと展開サーバーへのサインイン**JDE**します。  
  
2.  デプロイメント サーバー (root) の /B7 フォルダーに BTSREL という新しいフォルダーを作成します。  
  
3.  BTSREL.exe を新しく作成した BTSREL フォルダーにコピーします。  
  
4.  BTSREL.exe を .../B7/BTSREL フォルダーで実行します。 インストールのマネージャーが自動的に開始されます。  
  
5.  セットアップ ウィンドウで、選択**次**、し、**完了**。 インストールが成功した場合、メッセージが表示されます。  
  
6.  として JDEPLAN 環境にサインイン、**JDE** JD Edwards OneWorld デプロイメント サーバー上のユーザー。  
  
    1.  SAR #4533357 が含まれる電子的ソフトウェア更新プログラム (ESU) がシステムにインストールされていない場合は、選択**ソフトウェア更新プログラムの**から、**システム インストール ツール**メニュー (GH9612)。  
  
    2.  オプション 1 に 02 と入力します、**処理オプション**パネル。  
  
    3.  SAR #4533357 が含まれる ESU がシステムにインストールされている場合は、選択**アプリケーション ソフトウェアの更新**から、**システム インストール ツール**メニュー (GH9612)。  
  
#### <a name="install-btsrel-on-the-jd-edwards-oneworld-workbench"></a>JD Edwards OneWorld WorkBench に BTSREL をインストールします。  
   
1.  **アプリケーションの更新操作**画面、BTSREL 更新プログラムをダブルクリックし、選択**次**します。  
  
2.  更新プログラムをインストールするを必要とする環境をダブルクリックし、選択**次**します。  
  
    1.  確認**無人 Workbench**ソフトウェアの更新を自動モードで実行する場合。  
  
    2.  選択**バックアップ**(その元の仕様を復元することができます) の仕様のバックアップを修正する場合。  
  
3.  **インストール プラン操作**画面をインストールする更新プログラムの計画を選択し、**選択**。  
  
4.  インストールが完了したら、自動生成されるエラーに関する PDF を確認してください。  
  
    > [!NOTE]
    >  エラーが発生した場合、トラブルシューティングのヒントについては『JD Edwards OneWorld Software Update Guide』を確認するか、または JD Edwards OneWorld に直接お問い合わせください。  
  
5.  「に手動で登録、ビジネス関数ライブラリ」このセクションに含まれている手順を使用して、ビジネス関数ライブラリを手動で登録します。  
  
#### <a name="uninstall-the-custom-package"></a>カスタム パッケージをアンインストールします。  
 カスタム パッケージのアンインストールには要件はありません。 ただし、システムをクリーンアップする場合は、異なる方法でアンインストールすることができます。 をアンインストールした後、次のメソッドのいずれかを使用してパッケージを再構築します。  
  
- JD Edwards OneWorld Deployment サーバー、Gh8612 を使用して、— P96470 の**行**メニューの **更新**、し、**アンインストール**します。    
- すべてのカスタム オブジェクト (BTSREL) をクライアント コンピューターにチェック アウトしてから、それらを削除します。    
- データベースの前のスナップショットを適用します。  
  
  クリーンアップ中に、JD Edwards OneWorld の他のオブジェクトに対する他のすべての変更を確認します。  
  
#### <a name="manually-register-the-business-function-library"></a>ビジネス関数ライブラリを手動で登録します。  
 JD Edwards OneWorld 製品のパッケージ化プロセスの制限のために、BizTalk Adapter for JD Edwards OneWorld 用のカスタムのビジネス関数ライブラリ DLL を JD Edwards OneWorld に手動で登録する必要があります。 このプロセスは、次の手順で構成されます。
  
##### <a name="step-1-create-the-custom-business-function-library"></a>手順 1: カスタム ビジネス関数ライブラリを作成します。  
 JD Edwards OneWorld Object Management Workbench (OMW) を使用して、カスタムのビジネス関数ライブラリを作成します。 次の手順で初期セットアップを実行して、すべてのプラットフォームに適用されます。  
  
1.  Object Management Workbench を起動 (高速なパス:「OMW」。 またはメニュー選択: GH902 オブジェクト: P98220)。  
  
2.  選択**追加**のオプションを選択および**ビジネス関数ライブラリ**します。  
  
3.  新しいビジネス関数ライブラリ オブジェクトに関する次の情報を入力します。  
  
    -   **名前:** ACBLIB    
    -   **説明:** Microsoft DLL    
    -   **製品コード:** 55    
    -   **製品システム コード:** 55  
  
4.  **[OK]** を選択します。  
  
##### <a name="step-2-rebuild-libraries-from-the-deployment-server"></a>手順 2: 配置サーバーからライブラリを再構築します。  
各プラットフォームの初期セットアップでは、次の手順を完了します。  
  
1.  BusBuild プログラムをスタンドアロン モードで起動する**開始**を選択します**実行**、し、 **busbuild.exe**します。
  
2.  JD Edwards OneWorld にパスコード (PY7333、PD7333、または DV7333) でサインインします。  
  
3.  **ライブラリの再構築**一覧で、、**ビルド**します。  
  
##### <a name="step-3-copy-the-custom-dll"></a>手順 3: カスタム DLL をコピーします。  
 カスタムの DLL をパスコード ディレクトリから JD Edwards OneWorld の展開サーバーと JD Edwards OneWorld Enterprise サーバーは、親パッケージのディレクトリにコピーします。
  
**で、JD Edwards OneWorld XE Deployment サーバー**  
  
1.  ACBLIB.dll を DV7333\bin32 から DV7333\Packages\DV7333FA\bin32 にコピーします。  
  
2.  ACBLIB.def、ACBLIB.dmp、および ACBLIB.mak を DV7333\obj フォルダーから DV7333\Packages\DV7333FA\obj フォルダーにコピーします。  
  
3.  ACBLIB.exp、ACBLIB.lib、および sACBLIB.lib を DV7333\lib32 フォルダーから DV7333\Packages\DV7333FA\lib32 フォルダーにコピーします。  
  
**JD Edwards OneWorld Enterprise サーバー**  
  
各ディレクトリとファイルを作成した後、アクセス許可を確認します。  
  
1.  ディレクトリ DV7333FA\obj ACBLIB 作成\\です。  
  
2.  ACBLIB DV7333FA\source 下のディレクトリを作成します。  
  
3.  b5500900.c を、デプロイメント サーバーの DV7333\source ディレクトリから DV7333FA\source\ACBLIB ディレクトリに FTP で転送します。  
  
4.  FTP の b5500900.h は展開サーバー DV7333\include ディレクトリ DV7333FA\include ディレクトリにします。  
  
##### <a name="step-4-build-a-full-package"></a>手順 4: 完全なパッケージをビルドします。  
 JD Edwards のパッケージのビルド プロセスの制限のための環境を BTSREL 更新を適用するまたは更新プログラム パッケージのビルドが正常に動作しない完全なパッケージをビルドします。 フル パッケージ ビルドをビルドする方法については、JD Edwards のドキュメントを参照してください。  
  
> [!NOTE]
>  JD Edwards OneWorld の ASU/ESU を適用した場合、ASU/ESU では通常新しいライブラリとビジネス関数は作成されません。 そのため、プロセスは単純な。 ただし、BizTalk Adapter for JD Edwards OneWorld のカスタム パッケージは、新しいライブラリを作成します。 そのため、追加の手順を実行する必要がありますなど、手動でディレクトリを作成し、フル パッケージ ビルドを実行します。  
  
#### <a name="modules-list"></a>モジュールの一覧  
 BTSREL カスタム パッケージは、JD Edwards OneWorld で、次のオブジェクトを作成します。 BTSREL には、メタデータを抽出するためのビジネス関数と、データ型をテストするためのカスタム関数が含まれています。  
  
> [!NOTE]
>  JD Edwards OneWorld の更新プログラムには 1 つのバグがあります。 すべてのビジネスとユーザー定義関数を持っていない場合は、更新プログラム パッケージのビルドではなく、フル パッケージ ビルドを完了したことを確認します。  
>  
>  ファイルが一覧から失われた場合 (たとえば、ACBTEST の下にはすべてがあるが、その上には何もない場合)、データ辞書 (DD) の項目が失われた可能性があります。 移動できます**データ項目と作業**不足しているファイルを探します。  
>   
>  これらは ACBCHAR01、ACBDATE01、ADBINT01、ACBMATH01、および、ACBSTR01 などの他の項目がない場合は、*プライマリ データ要素*します。 オブジェクトをプランナーから DEV にマージすると、多数のレポートがバックグラウンドで実行されます。 マージのレポートを開いて、エラーを探すことができます。 レポートにはすべての項目が一覧表示され、エラーまたは警告なしで完了したことが示されます。 この検証を使用すれば、すべての項目が考慮されているため、作業を続行できます。  
  
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
  
-   D5500900 - コントロール BROKER データ構造体  
  
-   D5500900A - コントロール BROKER データ構造体  
  
-   D5500900B - フェッチ価格データ構造体  
  
-   D5500900C - 顧客ステータスのデータ構造の取得  
  
-   D5500900D - 顧客ステータス データ構造体のセット  
  
-   D5500900E - 更新プログラムの販売注文の状態データ構造体  
  
-   D5500900F - 整数のテスト  
  
-   D5500900G - テスト文字列  
  
-   D5500900H - 日付のテスト  
  
-   D5500900I - テスト CHAR  
  
-   D5500900J - 数学数値のテスト  
  
-   D5500900K - 日付 2 のテスト  
  
#### <a name="customize-the-jdeinteropini-file"></a>Jdeinterop.ini ファイルをカスタマイズします。  
 Connector.jar および Kernel.jar で JD Edwards OneWorld XE コネクタ クラスでは、jdeinterop.ini の構成ファイルを使用することが必要です。 このファイルは、JD Edwards OneWorld ソフトウェアで定義されており、その用語を使用します。 JD Edwards Interoperability Guide Release OneWorld では、目的と用語のこのファイルの詳細についてを提供可能性があります。 サンプルの jdeinterop.ini ファイルがある *< Adapter_Installation > \config\jde*します。  
  
定義されているパラメーター値と一致する jdeinterop.ini の更新、**トランスポートのプロパティ**画面。 複数の JD Edwards OneWorld 論理システムで、それらのパラメーターに互換性がある場合は、同じ jdeinterop.ini ファイルを共有できます。 一般に、2 つの論理システムは、2 つの異なる JD Edwards OneWorld コンピューター をポイントして、jdeinterop.ini の 2 つの異なるコピーが必要です。  
  
> [!NOTE]
>  Jdeinterop.ini でログ記録をオフにする必要があり、さまざまなログ ファイルのパラメーターは無視してもします。  
  
 次の表は、jdeinterop.ini ファイルにある各設定を項目化したものです。 情報は、セクション別に構成されています。 たとえば [JDENET] と各セクションは、JD Edwards OneWorld ソフトウェア内で出現する順序で一覧表示されています。  
  
#### <a name="jdeinteropini-file-settings"></a>jdeinterop.ini ファイルの設定
  
|セクション|パラメーターと説明|  
|-------------|-------------------------------|  
|[JDENET]|**EnterpriseServerTimeout.** エンタープライズ サーバーへの要求のタイムアウト値 (ミリ秒単位)。 既定のサイズは 120000 です。<br /><br /> **maxPoolSize.** JDENET ソケット接続のプール サイズ。 既定のサイズは、30 です。|  
|[SERVER]|**glossaryTextServer.** 用語集のテキスト情報を提供する、エンタープライズ サーバーとポート。 これは、エラーに関する説明テキストを返すサーバーです。 これは多くの場合、JD Edwards OneWorld アプリケーション サーバーと同じホストとポートです。 別のサポート対象言語エンコード用の複数の用語集サーバーが存在する場合があります。 たとえば、JDED:6010 または actsrv1:6009 です。 これらの値は、[System Definition] \(システム定義) に設定されている値と一致している必要があります。<br /><br /> **codePage.** エンコード スキームです。 既定値は、1252 です。<br /><br /> 1252 英語および西ヨーロッパ<br /><br /> -932 日本語<br /><br /> -950 繁体字中国語<br /><br /> -936 簡体字中国語<br /><br /> -949 韓国語|  
|[ログ]|**log = c:\jas.log します。** ログ ファイルの場所。 このパラメーターは無視してかまいません。<br /><br /> **debuglog = c:\jasdebug.log します。** デバッグ ログ ファイルの場所。 このパラメーターは無視してかまいません。<br /><br /> **デバッグします。** JDENET デバッグがオンかどうかが決定されます。 既定では FALSE です。|  
|[デバッグ]|**JobFile = c:\Interop.log します。** エラー ファイルの場所。 このパラメーターは無視してかまいません。<br /><br /> **DebugFile = c:\InteropDebug.log します。** デバッグ ファイルの場所。 このパラメーターは無視してかまいません。<br /><br /> **log = c:\net.log します。** ログ ファイルの場所。 このパラメーターは無視してかまいません。<br /><br /> **debugLevel = 0 - 12。** デバッグ レベル。 このパラメーターは無視してかまいません。 このパラメーターでは、COM サーバーのみで、指定されたログ ファイル内の COM コネクタと Callobject コンポーネントによって提供されるトレースのレベルを定義します。<br /><br /> -None は 0。 ログ記録が無効になり、エラーのみが JobFile に書き込まれます。<br /><br /> -2 つのエラー (エラー メッセージ)<br /><br /> -4: システム エラー (例外メッセージ)<br /><br /> -6: 警告情報<br /><br /> -8: 最小トレース (キー操作。 たとえば、ログオン、ログオフ、ビジネス関数の呼び出し。)<br /><br /> -10 のトラブルシューティングの情報 (ヘルプ)。<br /><br /> -12 の完全なデバッグ情報 (すべてを記録する)<br /><br /> -既定では、トレースを有効にする必要はありませんが、トレースは、コードをデバッグする場合に便利です。<br /><br /> -NetTraceLevel = 0。 トレース レベル。 このパラメーターは無視してかまいません。 COM サーバーのみで、指定されたログ ファイルでは、ThinNet コンポーネントによって提供されるトレースのレベルを定義します。 奇数の値は、レベルを今後追加するために予約されています。<br /><br /> -次の一覧には、さらに多くのデバッグ レベルについて説明します。<br /><br /> -0 トレースなし<br /><br /> -1 レコードのプロセス ID、スレッド ID、および新しい接続が追加され、ソケット プールが検索されるときに利用可能なソケット ステータスを参照してください。<br /><br /> -2 では、トレース レベル 1 の情報が含まれますも、接続マネージャー クラスで行われたすべての呼び出しをトレースします。<br /><br /> -3 には、トレース レベル 2、およびもトレース getPort() 呼び出しおよび getHost() 呼び出しですべての情報が含まれます。|  
|[INTEROP]|**enterpriseServer.** この値は、ホスト サーバーの名前です。 この値が同じ値で入力するかどうかを確認、**ホスト名**フィールドに、 **JDE 資格情報**セクション**システム定義**で、 **トランスポートのプロパティ** ダイアログ ボックス。 既定では JDED です。<br /><br /> **ポート。** この値は、データの交換に使用されるポート番号です。 この値が同じ値で入力するかどうかを確認、**ポート番号**フィールドに、JD Edwards**資格情報**セクション、**トランスポートのプロパティ、システム定義**. たとえば、6010 や 6009 です。 設定された値が一致する必要があります**システム定義**します。<br /><br /> **inactive_timeout**します。 自動コミット モードのトランザクションのタイムアウト値 (ミリ秒単位)。 ユーザーがこの時間 (ミリ秒単位) の間アクティブでなかった場合は、相互運用サーバーによってそのユーザーがログオフされます。 この値は、より短い時間に変更できます。 既定では 1200000 です。<br /><br /> **manual_timeout します。** 手動コミット モードでのトランザクションのミリ秒のタイムアウト値。 既定では 120000 です。<br /><br /> **リポジトリ。** Connector.jar と Kernel.jar が含まれたディレクトリの場所を指します。 UNIX では、これは完全なパスです。|  
|[CORBA]|このパラメーターは無視してかまいません。<br /><br /> **マルチ スレッドです。** 設定は無視できます。 CORBA でマルチスレッド サポートの場合は 1 に設定されます。<br /><br /> Objects= CORBA::Connector;CORBA::OneWorldVersion<br /><br /> CORBA サーバーで起動時に作成するオブジェクトを定義します。 -DIORFILENAME が置き換えられますコマンド ライン オプションをたとえば =: CORBA::Connector=connector.ior します。|  
  
## <a name="jd-edwards-enterpriseone"></a>JD Edwards EnterpriseOne  
このセクションでには、BizTalk Server と JD Edwards EnterpriseOne の Microsoft BizTalk Adapter の使用に関する重要な情報が含まれています。
  
### <a name="execute-a-jd-edwards-enterpriseone-master-business-function"></a>JD Edwards EnterpriseOne のマスター ビジネス関数を実行します。  
 BizTalk Adapter for JD Edwards EnterpriseOne を使用して、住所録、購買オーダー、受注オーダーなどの JD Edwards EnterpriseOne のマスター ビジネス関数を呼び出すことができます。 このアダプターは、JD Edwards EnterpriseOne を BizTalk Server と接続するための統合作業の一部として使用することもできます。  
  
##### <a name="access-data-stored-in-jd-edwards-enterpriseone"></a>JD Edwards EnterpriseOne に格納されているデータにアクセス  
 このアダプターでは、BizTalk Server アプリケーションで次のいずれかを使用して、JD Edwards EnterpriseOne との通信およびトランザクションの交換を可能にするために、XML メッセージを受け入れます。  
  
-   **送信アダプター**、JD Edwards EnterpriseOne にメッセージを送信する静的な送信請求-応答の送信ポートを使用し、応答が必要です。    
-   **受信アダプター**、静的な一方向の受信ポートを使用する JD Edwards EnterpriseOne からメッセージを受信します。  
  
### <a name="interoperability-framework"></a>相互運用性フレームワーク  
 JD Edwards EnterpriseOne では、その相互運用性フレームワークを通じて各システムとの統合に備えます。 アダプターでは、JD Edwards EnterpriseOne のフレームワークを使用して、さまざまな統合、最大限の柔軟性と機能を提供するアクセス メソッドを利用しています。  
  
 BizTalk Adapter for JD Edwards EnterpriseOne では、次の統合アクセス方法がサポートされています。  
  
- JD Edwards EnterpriseOne ThinNet API    
- JD Edwards EnterpriseOne XML    
- JD Edwards EnterpriseOne の未編集トランザクション テーブル (Z テーブル)  
  
  アダプターでは、JD Edwards EnterpriseOne ThinNet API を使用して、JD Edwards EnterpriseOne アプリケーションと通信します。 アダプターでは、ThinNet API を使用することによって、1 つの作業単位 (UOW) で 1 つのマスター ビジネス関数 (MBF) を呼び出すことができます。 MBF が失敗した場合、UOW 全体が失敗します。 これによって、部分的な更新が防止されます。 データ、ビジネス ルール、および基になるデータベースへの通信の検証は、JD Edwards EnterpriseOne アプリケーションによって処理されます。  
  
#### <a name="jd-edwards-outbound-processing-framework"></a>JD Edwards の送信処理フレームワーク  
 送信プロセスでは、特定の MBF が JD Edwards EnterpriseOne 環境で実行されると、イベントが開始します。 MBF では、このイベントに必要な情報を適切なインターフェイス テーブルに書き込んでから、イベントが発生したことをサブシステム バッチ関数 (BF) に通知します。 次に、サブシステム BF では、イベントに関するエントリをサブシステムのデータ キューに含めます。  
  
 送信サブシステムでは、データ キューのエントリを取得し、通知すべき外部プロセスがないか、データ エクスポートの制御テーブルを検索します。 次に送信サブシステムでは、その通知で BizTalk Adapter for JD Edwards EnterpriseOne のリスナーを呼び出します。 このリスナーでは、通知をジェネレーターに渡します。 次にジェネレーターでは、JD Edwards EnterpriseOne ThinNet API を使用して、インターフェイス テーブルから適切な情報を取得します。  
  
### <a name="set-string-justification-in-jdearglist"></a>Jdearglist で一連の文字列の位置  
 右揃えになり左側として特定の文字列引数を構成するには、j. d. で埋められます。 Edwards EnterpriseOne の jdearglist.txt ファイル; にアクセスするどのようなビジネス機能を知る必要があります。具体的には、呼び出したいビジネス関数のどのフィールドが必要です。  
  
 オーケストレーションでバインド (スキーマ) を生成する前に、jdearglist.txt を更新する必要があります。 文字列値"処理"セクションに記載されている、jdearglist.txt ファイルを更新するための手順です。  
  
 ログに jdearglist.txt の警告メッセージを受信する場合、その目的は、jdearglist.txt がないことを通知するためにです。 ただし、SalesOrder または PurchaseOrder ビジネス関数を実行している場合、パスにそのファイルがある必要があります。 または機能しません。  
  
### <a name="understand-jdeinteropini"></a>Jdeinterop.ini を理解します。  
 Connector.jar および Kernel.jar で JD Edwards EnterpriseOne コネクタ クラスでは、jdeinterop.ini という名前の構成ファイルを使用することが必要です。 このファイルは、JD Edwards EnterpriseOne ソフトウェアで定義され、その用語を使用します。 目的と用語のこのファイルの詳細については、JD Edwards の相互運用性ガイドを参照してください。 サンプルの jdeinterop.ini ファイルがある: Program files \ Microsoft BizTalk Adapters for Enterprise applications \ j. d. Edwards EnterpriseOne(r) \config します。  
  
 やり取りするために手動でこのファイルを編集することはお勧めできません、**トランスポートのプロパティ** ダイアログ ボックスの送信ポート - としてマークされているフィールドなどの **< BizTalk によって構成された\>**.  
  
## <a name="peoplesoft-enterprise"></a>PeopleSoft Enterprise  
このセクションには、BizTalk Server と PeopleSoft Enterprise の Microsoft BizTalk Adapter の使用に関する重要な情報が含まれます。
  
### <a name="receive-handler-peoplesoft-requirements"></a>受信ハンドラー PeopleSoft の要件  
 PeopleSoft Integration Broker が、BizTalk Server と通信可能である必要があります。 次のことが既存の PeopleSoft 環境ですでに実行済みの可能性があるため、既存のノードを再利用できる可能性があります。このため、PeopleSoft のシステム管理者から HTTP の仕様を入手する以外に何も行う必要はないかもしれません。 詳細については、PeopleSoft のドキュメントを参照してください。  

次の手順では、PeopleSoft を実行する概要を提供します。  
  
1.  メッセージを設定し、アクティブにし、アプリケーション デザイナーを使用します。  
  
2.  PeopleSoft integration.gateway.properties ファイルに対して、1 回限りの変更を行います。  
  
3.  作成し、ゲートウェイと HTTP のアクティブ化するノードを構成します。
  
    -   ノードでは、LOCATION_SYNC メカニズムなどのなんらかのトリガー メソッドを使用する必要があります。   
    -   ノードでは、HTTP を使用する必要があります。    
    -   ノードでは、イベントの送信先のホストとポートを指示している必要があります。  
  
### <a name="send-handler-peoplesoft-requirements"></a>送信ハンドラー PeopleSoft の要件  
 BizTalk Adapter for PeopleSoft Enterprise は、Java API を使用してアクセスを提供するカスタム コンポーネント インターフェイス (CI) で構成されます。 カスタム CI オブジェクトの**GET_CI_INFO**で BizTalk Adapter for PeopleSoft Enterprise のために必要なメタデータ情報を提供する PeopleSoft ツールを使用して PeopleSoft システムにデプロイされます。 詳細については、PeopleSoft のドキュメントを参照してください。  
  
 カスタム コンポーネント インターフェイスをアップロードするのは 1 回だけです。 このファイルの GET_CI_INFO.pc は製品に付属しており、アダプターを使用して CI を参照するには、PeopleSoft システムにインストールする必要があります。 PeopleSoft アプリケーション デザイナにアクセスできる必要がありますが、アプリケーション デザイナは、BizTalk Server コンピューターの近くに存在する必要はありません。 アプリケーション デザイナーを使用して、参照する PeopleSoft コンピューターにカスタム CI をアップロードします。  
  
 環境変数 CLASSPATH を設定する必要がありますので、PeopleSoft コンピューターへのアクセスが必要 (またはその情報を設定、**トランスポートのプロパティ**ウィンドウ) PeopleSoft PSJOA/psjoa.jar ファイルを指すようにします。  
  
### <a name="set-environment-variable-and-use-component-interface"></a>環境変数を設定し、コンポーネント インターフェイスの使用  
PeopleSoft の詳細については、PeopleSoft のドキュメントを参照してください。  
  
#### <a name="set-classpath-environment-variable"></a>ClassPath 環境変数な設定  

**JAVA_HOME を更新します。**    
  
 たとえば、JDK のインストール をポイントする JAVA_HOME 変数を設定します。  
  
```  
set JAVA_HOME=C:\j2sdk1.4.2_06  
```  
  
 **CLASSPATH を更新します。**  
  
使用するには、コンポーネント インターフェイス (PeopleSoft 8 のみ)、クラスパスに含める、PeopleSoft コンポーネント インターフェイスを更新する必要があります jar ファイルを使用します。
  
1. **コントロール パネルの **オープン**システム**します。  
  
2. **詳細設定**  タブで **環境変数**、し、**クラスパス**します。  
  
3. パスを追加します。 たとえば、次のように入力します。  
  
   ```  
   <PeopleSoft_Home>\web\PSJOA\psjoa.jar  
   ```  
  
   BizTalk Adapter for PeopleSoft Enterprise では、psjoa.jar ファイルが必要です。 これは、送信ポートの作成時に実行されます。 詳細については、アダプターのドキュメントの「Setting Transport Properties in PeopleSoft System」(PeopleSoft システムでのトランスポートのプロパティの設定) を参照してください。  
  
> [!NOTE]
>  BizTalk Adapter for PeopleSoft Enterprise で正しい DLL を取得するように、これらのディレクトリの 1 つだけを PATH に保持させます。 PeopleSoft の目的のバージョンに対して環境を正しくセットアップできないと、トレースが困難なエラーになるおそれがあります。  
  
#### <a name="use-component-interfaces"></a>コンポーネント インターフェイスの使用  
  
<a name="BKMK_CustomCI"></a>   
##### <a name="upload-a-custom-ci-into-peoplesoft"></a>PeopleSoft へのカスタム CI をアップロードします。  
 BizTalk Adapter for PeopleSoft Enterprise では、PeopleSoft アプリケーションに対する変更が必要です。 コンポーネント インターフェイスを使用するには、PeopleSoft に、カスタム コンポーネント インターフェイスの GET_CI_INFO をアップロードする必要があります。 アダプターを使用するには、最初のセットアップ時に GET_CI_INFO をインポートする必要があるだけです。 アダプターでは GET_CI_INFO を使用して、PeopleSoft 内の他の既存のコンポーネント インターフェイスについての情報を取得します。  
  
 このセクションでは、カスタム コンポーネント インターフェイスで PeopleSoft コンポーネント インターフェイスを参照することができますを手動でインポートする方法について説明します。 カスタム メソッドでは、コンポーネント インターフェイスがインストールされている、そのコンポーネント インターフェイスのプロパティを使用したり変更したりしないことに注意してください。 カスタム コンポーネント インターフェイスをインポートするには、次の方法のいずれかを使用できます。  
  
- カスタム メソッドをインポートするためのコンポーネントを新規に作成します。  
  
- キーが含まれていない既存のコンポーネント (たとえば、INSTALLATION_RS) を使用します。  
  
  単純なコンポーネント インターフェイスには、キーを含めないでください。 特定のコンポーネント インターフェイスにキーが含まれているかどうかが不明な場合は、SQL クエリ ツールを使用して、次の簡潔な SQL ステートメントを実行できます。 キーのないアプリケーションのすべてのコンポーネント インターフェイスの一覧を提示します。  
  
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
 PeopleSoft、アプリケーション デザイナーを使用して、新しいコンポーネント インターフェイスを作成する次の手順に従います。
  
1. 開く、 **PeopleSoft アプリケーション デザイナ**します。  
  
2. 3 層の接続の種類を入力し、クリックして**OK**します。 たとえば、アプリケーション サーバーを一覧から選択します。  
  
3. アプリケーション デザイナーでの**ファイル**メニューの **新規**します。  
  
4. **新規**ダイアログ ボックスで、**コンポーネント インターフェイス**、順にクリックします**OK**します。  
  
5. **[選択]** をクリックします。  
  
6. すべてのコンポーネントの一覧で、任意の単純なコンポーネントを選択します。 たとえば、INSTALLATION_RS または作成した新しい PeopleSoft コンポーネントを選択します。  
  
   カスタム メソッドがないを使用して、またはにインストールされているコンポーネント インターフェイスのプロパティを変更しないでください。  
  
   この単純なコンポーネント インターフェイスでは、キーを含めることはできません。 特定のコンポーネント インターフェイスにキーが含まれているかどうかが不明な場合は、SQL クエリ ツールを使用して、次の簡潔な SQL ステートメントを実行できます。 キーのないアプリケーションのすべてのコンポーネント インターフェイスの一覧できます。  
  
```  
select distinct BCNAME from PSBCITEM bc1 where not exists (select 1 from PSBCITEM bc2 where bc1.BCNAME = bc2.BCNAME and bc2.BCTYPE in (1, 2))  
```  
  
> [!NOTE]
>  BizTalk adapter for PeopleSoft Enterprise のカスタム メソッドを格納するための一意の単純なコンポーネントを作成する PeopleSoft のドキュメントをフォローすることもできます。  
  
 GET_CI_INFO にキーがないことを確認するには、PeopleTools アプリケーション デザイナのコンポーネント インターフェイスのテスト ツールを実行します。  
  
##### <a name="check-component-interface"></a>コンポーネント インターフェイスを確認してください。  
 Microsoft BizTalk Adapter for PeopleSoft の GET_CI_INFO の PeopleSoft システムへのアップロードが完了しました。 GET_CI_INFO は、ユーザー定義のカスタム コンポーネント インターフェイスです。 このインターフェイスには、ユーザー定義メソッドが含まれています。 GET_CI_INFO コンポーネント インターフェイスを使用すれば、Microsoft アダプター ウィザードによって、PeopleSoft システム内のコンポーネント インターフェイスを参照できます。 GET_CI_INFO を検索して展開し、そのユーザー定義メソッドを表示できます。  
  
> [!NOTE]
>  ユーザー定義メソッドの詳細については、アダプターのドキュメントの「PeopleSoft:: コンポーネント インターフェイス ユーザー定義メソッド」を参照してください。  
  
##### <a name="set-the-component-interface-security"></a>コンポーネント インターフェイスのセキュリティを設定します。  
 カスタムの GET_CI_INFO PeopleSoft コンポーネント インターフェイスを PeopleSoft にインストールした後は、セキュリティ設定を設定**GetCINamespace**、 **GetDetails**、および**GetCollections**BizTalk Adapter for PeopleSoft Enterprise のメソッド。 これは、カスタム コンポーネントまたはユーザー定義メソッドの作成時の標準的な手法です。  
  
> [!NOTE]
>  次の手順では、サポートされているすべてのモードで、サポートされている PeopleSoft のすべてのリリースのセキュリティを構成する方法について説明します。  
>   
>  コンポーネント インターフェイスのセキュリティを構成するには  
  
1.  をポイント**PeopleTools**、 をポイント**セキュリティ**、 をポイント**アクセス許可とロール**、し、**アクセス許可リスト**します。  
  
2.  **セキュリティの維持**ウィンドウで、 をクリックして**検索**、関連する選択**アクセス許可の一覧**、し、一覧から適切なハイパーリンクをクリックします。  
  
3.  **アクセス許可リスト**、右側のペインが横に、右矢印をクリックして、 **sign-on Times**タブを表示する、**コンポーネント インターフェイス**タブ。  
  
4.  をクリックして、**コンポーネント インターフェイス**タブ。  
  
5.  新しい行を追加するプラス記号 (+) をクリックする、**コンポーネント インターフェイス**一覧。  
  
6.  選択、 **GET_CI_INFO**コンポーネントのインターフェイス、およびクリック**編集**します。  
  
7.  メソッドに設定する**へのフル アクセス**、 をクリックして **(すべて) のフル アクセス**、順にクリックします**OK**します。  
  
8.  一番下までスクロール、**コンポーネント インターフェイス**ウィンドウ、およびクリック**保存**します。  
  
##### <a name="test-the-component-interface"></a>コンポーネント インターフェイスをテストします。  
 BizTalk Adapter for PeopleSoft Enterprise とともに提供される GET_CI_INFO コンポーネント インターフェイスのセキュリティの構成が完了しました。 PeopleSoft コンポーネント インターフェイスの準備が完了し、PeopleSoft コンポーネント インターフェイスを参照できます。  
  
 アプリケーション デザイナでコンポーネント インターフェイスをテストするには、次の手順を実行します。  
  
 コンポーネント インターフェイスをテストするには  
  
1.  開始、 **PeopleSoft アプリケーション デザイナ**します。  
  
2.  **ファイル**メニューで、**オープン**、し、**定義コンポーネント インターフェイスを =** します。  
  
3.  コンポーネント インターフェイスのリストから選択**GET_CI_INFO CI**します。  
  
4.  GET_CI_INFO を開いた後、コンポーネント インターフェイスの定義の右側のペイン内を右クリックし、 **Test Component Interface**します。  
  
**Component Interface Tester**ウィンドウが開きます。 キーは一覧表示されないはずです。 GET_CI_INFO にキーが含まれる場合、または別のオプションの選択がある場合は、デザイナーに戻り、アプリケーション、および GET_CI_INFO からすべてのキーを削除します。  
  
## <a name="install-steps"></a>インストール手順
 インストールする前に BizTalk Server のことを確認して、アダプターのすべてのソフトウェア前提条件がインストールされています。 Setup を実行する前に、すべてのアプリケーションを閉じることをお勧めします。  
  
1.  BizTalk Server を実行**Setup.exe**を選択します**Microsoft BizTalk アダプターのインストール**、選択と**Microsoft BizTalk Adapters for Enterprise Applications インストール**します。  
  
    > [!NOTE]
    >  - 次のコマンドを使用して、サイレント インストールを実行することもできます。: msiexec/i < msi\> /qn/l * < logfile\> --場所 < ログ ファイル\>は省略可能ではインストールの失敗が発生した場合に便利です。  
    >  - このインストールでは、PATH 環境変数が更新されます。 正しい変数を使用していることを確認するには、インストールのコマンド ウィンドウを閉じて、変数を更新します。  
  
2.  そのまま使用、**使用許諾契約書**を選択し、**次**します。
  
3.  入力、**顧客情報**を選択し、**次**します。  
  
4.  選択、**完了**または**カスタム**インストール。 
  
    -   **完全な**: Microsoft BizTalk Adapters for Enterprise Applications、すべてのプログラム機能がインストールされ、開発と実行時に使用されます。  
  
    -   **カスタム**: アダプターと機能をインストールしてがインストールされているを選択します。  
  
    対象を設定するには、次のように選択します。**参照**、し、インストール パスを設定します。  
  
    選択**次**を続行します。  
  
5. **インストール**、選択と**完了**を完了するとします。  
  
> [!IMPORTANT]
>  インストール中に、次のエラーが発生する可能性があります。  
>   
>  `Error 1609. An error occurred while applying security settings. CREATOR OWNER is not a valid user or group`  
>   
>  このエラーを回避するには、次の操作をインストールを再実行します。  
>   
>  1. コマンド プロンプトを開く
>  2. 型:`net user "CREATOR OWNER" /add`します。 これは、CREATOR OWNER と呼ばれる新しいユーザーを作成します。
>  3. 型:`net localgroup Users /add`します。 これは、ユーザーと呼ばれる新しいグループを作成します。
  
BizTalk Server にアダプターを追加するには、このトピックの「BizTalk 管理者へのアダプターの追加」を参照してください。

## <a name="add-adapters-to-biztalk-admin"></a>BizTalk 管理者にアダプターを追加します。
  
> [!NOTE]
>  (ランタイムのみのインストールを 1 台のコンピューター、および他のコンピューター管理ツールのみのインストール) を複数コンピューター環境に BizTalk をインストールする場合、両方のコンピューターで for Enterprise Applications の BizTalk アダプターをインストールする必要があります。  
  
1.  BizTalk Server 管理コンソールを開き、展開**Microsoft BizTalk Server**、順に展開**プラットフォームの設定**します。  
  
2.  右クリックして**アダプター**を選択します**新規**、し、**アダプター**します。  
  
3.  などの名前を入力します**PeopleSoft**します。  
  
4.  入力した名前を選択、**アダプター**一覧**OK**します。  
   
## <a name="post-install---jd-edwards-oneworld"></a>インストール後、JD Edwards OneWorld  
 Microsoft BizTalk Adapter for JD Edwards OneWorld は、サポートされているデータベースおよびサーバー システムと Microsoft BizTalk Server とのインターフェイスとなる送信アダプターで構成されています。 送信アダプターでは、BizTalk Server からサーバー システムの呼び出しを起動することができます。 送信アダプター (BizTalk Server 管理の送信ハンドラー) の構成では、SQL データベースの場所を指定します。  
  
 BizTalk Adapter for JD Edwards OneWorld の使用方法、およびそのモデルと BizTalk Server モデル間のマッピングについては、アダプターのドキュメントを参照してください。  
  
### <a name="single-sign-on"></a>シングル サインオン  
 BizTalk Adapter for JD Edwards OneWorld のエンタープライズ シングル サインオン (SSO) のサポートを提供します。 SSO の使用を選択した場合、**トランスポートのプロパティ** ページで、資格情報は SSO 資格情報データベース内の関連アプリケーションが使用されます。 関連アプリケーションとは、資格情報を必要とするバック エンドのアプリケーションを表しています。  
  
### <a name="installed-components"></a>インストールされているコンポーネント  

* アダプターのインストールでは、インストールして、グローバル アセンブリ キャッシュ (GAC) に、次のコンポーネントを登録します。 エクスプ ローラーでアセンブリ フォルダーを開くことで、登録を確認することができます (< %windir% > \assembly) を使用して、または、 `gacutil /l` Visual Studio コマンド プロンプトから。

    -   Microsoft.BizTalk.Adapters.BizUtil.dll    
    -   Microsoft.BizTalk.Adapters.JDEProperties.dll    
    -   Microsoft.BizTalk.Adapters.CoreManagement.dll    
    -   Microsoft.BizTalk.Adapters.CoreReceiver.dll    
    -   Microsoft.BizTalk.Adapters.CoreTransmitter.dll  

  
* btsTask.exe がインストールされ、展開、`Microsoft.BizTalk.Adapters.JDEProperties.dll`ファイルを GAC にします。 BizTalk Server の展開ログの結果は*\Program Files\Microsoft BizTalk Adapters for Enterprise applications \jdedeploy.html*と**jdeDeploy.xml**します。
  
* アダプターに固有のファイルがインストールされている*Program Files*と*Program files \common Files*します。  
  
* `sdk\`にインストールされている*Program の files \microsoft BizTalk Adapters for Enterprise applications \ j. d.Edwards OneWorld(r)* します。
  
* * プログラム Enterprise Applications\JD Edwards OneWorld(r) を \microsoft BizTalk Adapters\*次のファイルが含まれています。  
  
    -   classes\JDEJAccess.jar    
    -   Config\ j. d. Edwards OneWorld(r) \BTSREL.exe    
    -   Config\ j. d. Edwards OneWorld(r) \jdearglist.txt    
    -   Config\ j. d. Edwards OneWorld(r) \jdeinterop.ini  
  
* * プログラムの files \common files \microsoft BizTalk Adapters for Enterprise applications \bin\*次のファイルが含まれています。  
  
    -   Microsoft.BizTalk.Adapters.JDEProperties.dll    
    -   jdecba.dll  
  
## <a name="post-install---jd-edwards-enterpriseone"></a>インストール後、JD Edwards EnterpriseOne  
 Microsoft の BizTalk Adapter for JD Edwards EnterpriseOne には、サポートされているデータベースと BizTalk Server にサーバー システムとやり取りする送信アダプターが含まれています。 送信アダプターを使用すると、BizTalk Server からサーバー システムの呼び出しを起動することができます。  
  
 BizTalk Adapter for JD Edwards EnterpriseOne のエンタープライズ シングル サインオン (SSO) のサポートを提供します。 SSO の使用を選択した場合、**トランスポートのプロパティ** ページで、資格情報は SSO 資格情報データベース内の関連アプリケーションが使用されます。 関連アプリケーションとは、資格情報を必要とするバック エンドのアプリケーションを表しています。  
  
### <a name="installed-components"></a>インストールされているコンポーネント  
* アダプターのインストールでは、インストールして、グローバル アセンブリ キャッシュ (GAC) に、次のコンポーネントを登録します。 エクスプ ローラーでアセンブリ フォルダーを開くことで、登録を確認することができます (< %windir% > \assembly) を使用して、または、 `gacutil /l` Visual Studio コマンド プロンプトから。
  
    -   Microsoft.BizTalk.Adapters.BizUtil.dll    
    -   Microsoft.BizTalk.Adapters.JDEProperties.dll    
    -   Microsoft.BizTalk.Adapters.CoreManagement.dll    
    -   Microsoft.BizTalk.Adapters.CoreReceiver.dll    
    -   Microsoft.BizTalk.Adapters.CoreTransmitter.dll    

* アダプターに固有のファイルがインストールされている、 *Program files \common files \microsoft BizTalk Adapters for Enterprise applications \bin*フォルダー。 このフォルダーには、次のファイルが含まれています。  
  
    -   Jdecba.dll    
    -   Microsoft.BizTalk.Adapters.JDEProperties.dll  
  
* 次のファイルがインストールされている*Enterprise applications \j.d. の Program files \microsoft BizTalk Adapters します。Edwards enterpriseone (r)*:  
  
    -   Bin\BTAJDEEnterpriseOneTrace.cmd    
    -   Classes\JDEDynAccess.jar    
    -   Config\btaJDEEnterpriseOneTrace.mof    
    -   Config\jdearglist.txt    
    -   Config\jdeinterop.ini    
    -   Config\jdelog.properties    
    -   Sdk  
  
 
## <a name="post-install---peoplesoft-enterprise"></a>インストール後の PeopleSoft Enterprise  
 Microsoft BizTalk Adapter for PeopleSoft Enterprise には、サポートされているデータベースと BizTalk Server にシステムを server にやり取りする送信アダプターが含まれています。 送信アダプターを使用すると、BizTalk Server からサーバー システムの呼び出しを起動することができます。 送信アダプター (BizTalk Server 管理の送信ハンドラー) の構成では、SQL データベースの場所を指定します。  
  
 BizTalk Adapter for PeopleSoft Enterprise は、サポートのエンタープライズ シングル サインオン (SSO) を提供します。 SSO の使用を選択した場合、**トランスポートのプロパティ** ページで、資格情報は SSO 資格情報データベース内の関連アプリケーションが使用されます。 関連アプリケーションとは、資格情報を必要とするバック エンドのアプリケーションを表しています。  
  
 アダプターのインストールには、サンプルが \sdk ディレクトリに含まれています。  
  
### <a name="installed-components"></a>インストールされているコンポーネント  
* アダプターのインストールでは、インストールして、グローバル アセンブリ キャッシュ (GAC) に、次のコンポーネントを登録します。 エクスプ ローラーでアセンブリ フォルダーを開くことで、登録を確認することができます (< %windir% > \assembly) を使用して、または、 `gacutil /l` Visual Studio コマンド プロンプトから。
  
    -   Microsoft.BizTalk.Adapters.BizUtil.dll    
    -   Microsoft.BizTalk.Adapters.CoreManagement.dll    
    -   Microsoft.BizTalk.Adapters.CoreReceiver.dll    
    -   Microsoft.BizTalk.Adapters.CoreTransmitter.dll    

* アダプターに固有のファイルがインストールされている*Program Files*と*Program files \common Files*します。 次のファイルがインストールされている*Enterprise Applications\PeopleSoft Enterprise (r) の Program files \microsoft BizTalk Adapters*:
  
    -   bin\BTAPeopleSoftTrace.cmd    
    -   config\btaPeopleSoftTrace.mof    
    -   config\GET_CI_INFO.pc    
    -   config\GET_CI_INFO.pc    
    -   sdk\  
  
* *プログラムの files \common files \microsoft BizTalk Adapters for Enterprise Applications*次のファイルが含まれています。  
  
    -   bin\psosa.dll    
    -   bin\Microsoft.BizTalk.Adapters.CoreManagement.dll    
    -   bin\Microsoft.BizTalk.Adapters.CoreReceiver.dll    
    -   bin\Microsoft.BizTalk.Adapters.CoreTransmitter.dll  
  
## <a name="post-install-overview---tibco-rendezvous"></a>インストール後の TIBCO Rendezvous の概要  
 Microsoft BizTalk Adapter に TIBCO Rendezvous が含まれています、受信し、サポートされているデータベースと BizTalk Server にサーバー システムとのインターフェイスの機能を送信します。  
  
- 受信側では、サーバー システムからの送信である呼び出しをリッスンします。  
  
- 送信側を使用すると、BizTalk Server からサーバー システムの呼び出しを起動することができます。  
  
  Microsoft BizTalk Adapter for TIBCO Rendezvous を使用する方法について、およびそのモデルと、BizTalk Server モデル間のマッピングについて、アダプターのドキュメントを参照してください。  
  
### <a name="installed-components"></a>インストールされているコンポーネント  
* アダプターのインストールでは、インストールして、グローバル アセンブリ キャッシュ (GAC) に、次のコンポーネントを登録します。 エクスプ ローラーでアセンブリ フォルダーを開くことで、登録を確認することができます (< %windir% > \assembly) を使用して、または、 `gacutil /l` Visual Studio コマンド プロンプトから。 
  
    -   Microsoft.BizTalk.Adapters.TibcoRV    
    -   Microsoft.BizTalk.Adapters.TibcoRV.Common    
    -   Microsoft.BizTalk.Adapters.TibcoRV.Service    
    -   Microsoft.BizTalk.Adapters.TibRV.Properties    
    -   Microsoft.BizTalk.Adapters.TibcoEMS    
    -   Microsoft.BizTalk.Adapters.TibcoEMS.Properties    
    -   Microsoft.BizTalk.Adapters.TibcoRVManagement    
    -   Microsoft.BizTalk.Adapters.TibcoRVReceiver  
    -   Microsoft.BizTalk.Adapters.TibcoRVTransmitter  
  
* アダプターに固有のファイルがインストールされている*プログラム ファイルと Program files \common Files*します。 次のファイルがインストールされている*Enterprise applications \ TIBCO(r) Rendezvous(r) の Program files \microsoft BizTalk Adapters*:  
  
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
  
* *プログラムの files \common files \microsoft BizTalk Adapters for Enterprise Applications*次のファイルが含まれています。  
  
    -   bin\tibcorvcba.dll    
    -   Microsoft.BizTalk.Adapters.CoreManagement.dll    
    -   Microsoft.BizTalk.Adapters.CoreReceiver.dll    
    -   Microsoft.BizTalk.Adapters.CoreTransmitter.dll  
  
### <a name="add-tibcorendezvousdll-to-the-gac"></a>TIBCO を追加します。GAC に Rendezvous.dll  
 BizTalk Adapter for TIBCO Rendezvous が必要です、 **TIBCO します。Rendezvous.dll**ファイル。 必要な最小バージョンは 1.0.3036.23330 FileVersion、製品のバージョン 8.1 が付属しています。 このアセンブリがインストールされていない場合、アダプターは例外をトリガーし、適切なメッセージを記録します。  
  
 遅延バインディングを使用して、アセンブリを読み込むときに特定のバージョンの TIBCO の TIBCO Rendezvous アセンブリが失敗しないようにする必要があります。Rendezvous.dll と TIBCO します。Rendezvous.net モジュールは、ターゲット コンピューターではありません。
  
 **ランタイム コンポーネント**  
  
 TIBCO Rendezvous のランタイム コンポーネントがコンピューターにインストールされていることを確認します。 ランタイム コンポーネントは、TIBCO Rendezvous のインストール時にインストールする必要がある唯一のコンポーネントです。  

1. Visual Studio コマンド プロンプトで、TIBCO の場所にディレクトリを変更します。Rendezvous.dll ファイルです。 TIBCO Rendezvous の既定のインストールでは、この DLL のパスは**C:\TIBCO\TIBRV\BIN\TIBCO します。Rendezvous.dll**します。  
  
2. コマンド プロンプトで、次のように入力します:  
  
```
C:\TIBCO\TIBRV\BIN > gacutil /i TIBCO.Rendezvous.dll
```
  
 これにより、TIBCO.Rendezvous.dll で GAC の一覧が表示されます。 コントロール パネルで、一覧を表示するのには、開く**管理者ツール**、オープン**Microsoft .NET Framework 構成**を開き**アセンブリ キャッシュ**。  
  
## <a name="post-install---tibco-enterprise-message-service"></a>インストール後、TIBCO Enterprise Message Service  
 Microsoft BizTalk Adapter に TIBCO Enterprise Message Service (EMS) が含まれています、受信し、サポートされているデータベースと BizTalk Server にサーバー システムとのインターフェイスの機能を送信します。  
  
- 受信側では、サーバー システムからの送信である呼び出しをリッスンします。  

- 送信側を使用すると、BizTalk Server からサーバー システムの呼び出しを起動することができます。  
  
  BizTalk Adapter for TIBCO EMS を使用する方法について、およびそのモデルと、BizTalk Server モデル間のマッピングについて、アダプターのドキュメントを参照してください。  
  
### <a name="installed-components"></a>インストールされているコンポーネント  
* アダプターのインストールのインストールおよび登録され、`Microsoft.BizTalk.Adapters.TibcoEMS.dll`グローバル アセンブリ キャッシュ (GAC) 内のファイル。 エクスプ ローラーでアセンブリ フォルダーを開くことで、登録を確認することができます (< %windir% > \assembly) を使用して、または、 `gacutil /l` Visual Studio コマンド プロンプトからです。
  
* アダプターに固有のファイルがインストールされている*Program Files*と*Program files \common Files*します。 で、次のファイルがインストールされている*Enterprise Applications\TIBCO(r) Enterprise メッセージ Service(TM) の Program files \microsoft BizTalk Adapters*:  
  
    -   bin\BTATibcoEMSTrace.cmd    
    -   Microsoft.BizTalk.Adapters.TibcoEMS.dll    
    -   Config\btaTibcoEMSTrace.mof    
    -   sdk\  
  
* *プログラムの files \common files \microsoft BizTalk Adapters for Enterprise applications \bin*フォルダーには、次のファイルが含まれています。  
  
  - Microsoft.BizTalk.Adapters.CoreManagement.dll    
  - Microsoft.BizTalk.Adapters.CoreReceiver.dll    
  - Microsoft.BizTalk.Adapters.CoreTransmitter.dll  
  
    > [!NOTE]
    >  遅延バインディングを使用して、アセンブリを読み込むときに、TIBCO の特定のバージョン、TIBCO EMS のアセンブリが失敗しないようにする必要があります。EMS.dll では、ターゲット コンピューターに存在しません。  
  
### <a name="add-tibcoemsdll-api-to-the-gac"></a>TIBCO を追加します。GAC に EMS.dll API  
 BizTalk Adapter for TIBCO EMS では、TIBCO.EMS.dll を GAC に追加することが必要です。 BizTalk Adapter for TIBCO EMS は、例外をトリガーし、このアセンブリがインストールされていない場合、適切なメッセージを記録します。  
  
1. TIBCO EMS C# の #API を BizTalk コンピューターにコピーします。  
  
2. Visual Studio コマンド プロンプトでは、c# API ファイルの場所にディレクトリを変更します。  
  
3. Visual Studio コマンド プロンプトで、次のように入力します。  
  
   ```
   C:\\<TIBCO EMS Folder\>bin> gacutil /i TIBCO.EMS.dll
   ```
  
   これにより、TIBCO.EMS.dll が C:\Windows\assembly の一覧に表示されます。 または、コントロール パネルを開きます**管理者ツール**、オープン**Microsoft .NET Framework**、開き**アセンブリ キャッシュ**GAC の一覧を表示します。  
  
   **制限事項**  
  
   BizTalk Adapter for TIBCO EMS は、TIBCO を使用します。サーバーとの通信に EMS.dll します。 TIBCO.EMS.dll を使用する際の制限を次に示します。  
  
4. メッセージの圧縮は、TIBCO EMS クライアントで EMS に圧縮形式でメッセージを送信できるようには、ご利用いただけません。  
  
5. アダプターとサーバー間のメッセージの暗号化は使用できません。 TIBCO.EMS.dll では、OpenSSL ライブラリを使用した SSL 暗号化は許可されませんが、アダプターでは、ProductVersion 5.0 以降で SSL がサポートされています。  
  
6. EMS 用の管理 API は、サポートされていません。  
  
## <a name="adapter-tracing"></a>アダプターのトレース

### <a name="enable-tracing"></a>トレースを有効にします。
 Windows のトレースで使用されるファイル名は、管理者が決定します。 アプリケーションでは、オペレーティング システムに書き込み、特定のバックエンド システムのログが必要になるまで、すべてのログを無視します。 これを行うには、BizTalk Adapters for Enterprise Applications の別のコマンド ファイルを実行します。 そのコマンドの引数の 1 つは、トレース情報をキャプチャするために使用するファイルの名前です。 詳細については、(このトピック) で「トレース イベントを使用して Windows」を参照してください。
  
 トレース ファイルをインストールする * \Program Files\Microsoft BizTalk Adapters for Enterprise Applications\*します。  
  
-   bin\BTATrace.cmd    
-   config\btaTrace.mof  
  
### <a name="use-windows-trace-event"></a>Windows トレース イベントを使用します。  
 アダプターでは、エラー メッセージ、警告メッセージ、および情報メッセージを Windows イベント ビューアーに記録します。 その他のトレース メッセージを表示するには、Event Tracing for Windows (ETW) ツールを使用します。 ETW が有効である場合、このメッセージを受信する *.etl ファイルが作成されます。 このファイルはバイナリ形式であり、読み取るには変換する必要があります。 これを行うには、解釈に利用できるコンシューマー アプリケーションが必要、 \*.etl ファイル、Windows の tracerpt.exe や tracedmp.exe などです。  
  
### <a name="etw-components"></a>ETW コンポーネント
  
 Windows イベント トレーシングには 3 つのコンポーネントがあります。  
  
* **コント ローラー アプリケーション:** にアクティブとプロバイダーを非アクティブ化します。 たとえば、tracelog.exe または logman.exe です。  
  
    PATH 環境変数を、tracelog.exe の場所を指すように設定します。 これにより、BTA < アダプタ名\>トレースの呼び出しのシステムの tracelog.exe を見つけることができます。 既定で BTA < アダプタ名\>トレースは、現在のパスを検索します。  
  
    > [!NOTE]
    >  tracelog.exe は Microsoft SDK と Microsoft BizTalk Adapters for Enterprise Applications コマンドと互換性があります。 logman.exe の使い方については、logman のマニュアルを参照してください。  
  
* **コンシューマー アプリケーション:** 記録されたイベントの読み取り。  
  
    コンシューマー アプリケーションで .etl ファイル内のイベントを読み取るには、Windows イベント トレーシングでそれらのイベントを .etl ファイルにダンプする必要があります。 通常、この作業は、コントローラーがトレーシングを非アクティブ化するときに行われます。  
  
    コント ローラーに、コンシューマー アプリケーションを使用して、トレースを非アクティブ化せず、リアルタイムのオプションを使用してトレースをアクティブ化する必要があります **< リアルタイム\>=-rt**します。  
  
* **プロバイダー:** イベントを提供するために使用します。  
  
    各アダプターには、5 つの異なるプロバイダーが含まれています。 これらは Windows Management Instrumentation (WMI) に登録されます。 root\WMI\EventTrace パス内で登録プロバイダーを検索するには、WMI CIM Studio などのツールを使用します。  
  
    5 つのプロバイダーを使用すると、さまざまな種類のメッセージをログに記録できます。  
  
        -   **Receiver Logging Provider**: The <Trace element\> switch is - **receiver**.    
        -   **Receiver CastDetails Provider**: The <Trace element\> switch is - **castDetailsReceive**.    
        -   **Transmitter Logging Provider**: The <Trace element\> switch is - **transmitter**.    
        -   **Transmitter CastDetails Provider**: The <Trace element\> switch is - **castDetailsTransmit**.    
        -   **Management Logging Provider**: The <Trace element\> switch is - **management**.  
  
ETW を使用するには、特定のアダプターのコマンドを実行します。`BTA<Adapter Name\>Trace.cmd`します。 このコマンドは次のように使用します。  
  
```  
BTA<Adapter Name>Trace <Trace element> -start [-cir <MB>|   
    -seq <MB>] [-rt] logfile  
BTA<Adapter Name>Trace <Trace element> -stop  
  
```  
  
 各要素の説明は次のとおりです。  
  
**< トレース要素\>** プロバイダーの種類は、(必須)。 使用可能なオプションは次のとおりです。  
  
 **-castDetailsTransmit**  
  
 **-送信機**  
  
 **-castDetailsReceive**  
  
 **-受信機**  
  
 **-管理**  
  
 **-開始、停止:** アクティブ化またはプロバイダーを非アクティブ化します。  
  
 **-cir < MB\>:** サイズとファイルの種類。 **-cir**は循環ファイルです。 **< MB\>:** サイズ (メガバイト単位)。  
  
 **-seq < MB\>:** サイズとファイルの種類。 **-seq**はシーケンシャル ファイルです。 **< MB\>:** サイズ (メガバイト単位)。  
  
 **-rt:** でリアルタイムに設定します。  
  
 **ログ ファイル:** ログ ファイルの名前 (既定では c:\rtlog.etl) です。  
  
 以下に例を示します。  
  
```  
BTAXXXTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTAXXXTrace -transmitter -stop  
  
```  
  
> [!NOTE]
>  .etl ファイルの書式を設定するには、tracerpt.exe コマンドを使用します。  

## <a name="next-steps"></a>次のステップ
* [JD Edwards EnterpriseOne アダプター](../core/jd-edwards-enterpriseone-adapter.md)
* [JD Edwards OneWorld アダプター](../core/jd-edwards-oneworld-adapter.md)
* [PeopleSoft Enterprise アダプター](../core/peoplesoft-enterprise-adapter.md)
* [TIBCO Enterprise Message Service アダプター](../core/tibco-enterprise-message-service-adapter.md)
* [TIBCO Rendezvous アダプター](../core/tibco-rendezvous-adapter.md)
