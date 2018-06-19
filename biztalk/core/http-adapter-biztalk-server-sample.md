---
title: HTTP アダプター (BizTalk Server サンプル) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP adapters, examples
- examples, HTTP adapters
ms.assetid: f3bd8172-15c4-42fa-aa17-e4bed9d4aba4
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f09615b8038170bfdc0f9d63492e40dc1b2a0eba
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974488"
---
# <a name="http-adapter-biztalk-server-sample"></a>HTTP アダプター (BizTalk Server サンプル)
HTTP アダプターのサンプルは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で使用される要求 - 応答および送信請求 - 応答の通信パラダイムを実装する方法を示します。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 *\<パスのサンプル\>* \AdaptersDevelopment\HttpAdapter\  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|Description|  
|---------------|-----------------|  
|\Design-Time\Adapter Management|このアダプターのデザイン時の部分を実装するプロジェクトが含まれます。|  
|\Run-Time\HttpReceive|要求 - 応答アダプターの通信パターンを実装するプロジェクトが含まれます。 これは分離受信場所です。|  
|\Run-Time\HttpSend|送信請求 - 応答アダプターの通信パターンを実装するプロジェクトが含まれます。|  
  
## <a name="how-to-use-this-sample"></a>このサンプルの使用方法  
 このサンプルは、カスタム アダプターを開発するときに使用するフレームワークです。 BizTalk Server はメッセージを特定のカスタム アプリケーションに送信したり、ネイティブ アダプターが存在しないプロトコルを使用する必要がある場合があります。 サードパーティの企業は、追加のプロトコルをサポートするアダプターを作成しています。 カスタム アダプターの作成を決定する前に、プロトコルに対するアダプターが存在するかどうかを確認することをお勧めします。 通信要件をサポートするためのアダプターが見つからない場合は、独自のカスタム アダプターを開発できます。  
  
 カスタム アダプターの作成は、難しい作業になる場合があります。 このプロセスを簡略化するために、マイクロソフトはアダプター フレームワークと呼ばれる基礎を開発しました。 このフレームワークを、BizTalk Server SDK のサンプルのアダプター ソース コードと共に開発の基礎として使用できます。  詳細については、カスタム アダプターとアダプター フレームワークを参照してください、**参照**このドキュメントの最後のセクションでします。  
  
## <a name="building-and-initializing-the-sample-adapter"></a>サンプル アダプターのビルドおよび初期化  
  
> [!IMPORTANT]
>  BizTalk 環境が 64 ビットである、またはインストール場所が変更されている場合は、それに合わせて OutboundAssemblyPath、InboundAssemblyPath、および AdapterMgmtAssemblyPath を変更する必要があります。  
  
#### <a name="to-build-and-initialize-the-http-adapter-sample"></a>HTTP アダプターのサンプルをビルドして初期化するには  
  
1.  コマンド ウィンドウで、次のフォルダーに移動します。  
  
     \<*パスのサンプル*\>\AdaptersDevelopment\HttpAdapter  
  
2.  次の操作を実行する Setup.bat ファイルを実行します。  
  
    -   HTTPAdapter とそのすべての依存関係をコンパイルします。  
  
    -   アダプターの受信側で使用されるインターネット インフォメーション サービス (IIS) アプリケーションを作成します。  
  
 IIS 7.0 では、この IIS アプリケーションを実行するアプリケーション プールの ID が次のグループのメンバーであることを確認する必要があります。  
  
-   BizTalk 分離ホスト ユーザー グループ  
  
-   IIS_WPG グループ  
  
-   IIS 7.0 では、統合 .NET モードで動作するアプリケーションを移行する必要があります。 内容を含む、アプリケーション構成を移行することができます、 \<httpHandlers\> (ウィンドウを管理者として実行する必要があります)、コマンド ライン ウィンドウから、次を使用して、構成セクション。  
  
    ```  
    %systemroot%\system32\inetsrv\APPCMD.EXE migrate config "Default Web Site/HttpReceive"  
    ```  
  
-   移行したアプリケーションは、下位レベルのプラットフォームと同様に、クラシック モードと統合 .NET モードのいずれでも実行できます。  
  
> [!NOTE]
>  このサンプルを実行する前に、ビルド処理および初期化処理でエラーが報告されていないことを確認してください。  
  
> [!NOTE]
>  開き、Setup.bat ファイルを実行せずにこのサンプルのプロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して厳密な名前キーのペアを作成する必要があります。 このキー ペアは、生成されたアセンブリの署名に使用します。  
  
> [!NOTE]
>  Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。 Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。  
  
## <a name="registering-the-sample-adapter"></a>サンプル アダプターの登録  
  
#### <a name="to-register-the-http-adapter-sample"></a>HTTP アダプターのサンプルを登録するには  
  
1.  Windows エクスプ ローラーで、インストール ドライブに移動[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]に移動し、\<サンプル パス\>\AdaptersDevelopment\HTTPAdapter です。  
  
2.  サンプル アダプターをレジストリに追加するにはダブルクリック**HTTP.NET.reg**です。  
  
    > [!NOTE]
    >  HTTP.NET.reg には、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のインストール ディレクトリへのハードコードされたパスが含まれています。 既定の場所に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールしなかった場合や、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のインストールを以前のバージョンの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] からアップグレードした場合は、HTTP.NET.reg ファイルを変更して適切なパスを指定する必要があります。 "OutboundAssemblyPath" と "AdapterMgmtAssemblyPath" の値に関連付けられたパスを更新し、指定されたファイルの正しい場所を指すようにします。  
  
    > [!IMPORTANT]
    >  BizTalk を 64 ビット コンピューターにインストールする場合は、hkey_classes_root \clsid\ レジストリ エントリのすべてのインスタンスを hkey_classes_root \wow6432node\clsid\ に変更、 **HTTP.NET.reg**レジストリ ファイル。  
  
3.  **レジストリ エディター**ダイアログ ボックスで、をクリックして**はい**サンプル アダプターをレジストリに追加し、をクリックする **[ok]** です。  
  
4.  Windows エクスプ ローラーを閉じる、**ファイル** メニューのをクリックして**閉じる**です。  
  
## <a name="installing-the-sample-adapter"></a>サンプル アダプターのインストール  
  
#### <a name="to-install-the-http-adapter-sample"></a>HTTP アダプターのサンプルをインストールするには  
  
1.  クリックして、**開始**メニューの **すべてのプログラム**を選択[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、し、 **BizTalk Server 管理コンソール**です。  
  
2.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開、[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]ツリー、 **BizTalk グループ**ツリー、**プラットフォームの設定**ツリー。  
  
3.  右クリック**アダプター**をクリックして**新規**、順にクリック**アダプター**です。  
  
4.  **アダプター プロパティ** ダイアログ ボックスで、次の操作です。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |名前|型**HTTP.NET**です。|  
    |[アダプター]|選択**HTTP.NET**ドロップダウン リストからです。|  
    |Description|型**サンプル HTTP.NET アダプター**です。|  
  
5.  **[OK]** をクリックします。  
  
6.  これで、BizTalk 管理コンソールの右ウィンドウにあるアダプターの一覧にアダプターが表示されます。  
  
## <a name="stopping-and-restarting-the-host-instance"></a>ホスト インスタンスの停止と再起動  
  
#### <a name="to-stop-and-restart-the-host-instance-for-the-http-adapter-sample"></a>HTTP アダプターのサンプルのホスト インスタンスを停止して再起動するには  
  
1.  クリックして、**開始**メニューの **すべてのプログラム**を選択[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]を選択し、[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]です。  
  
2.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開、[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]ツリー、**プラットフォームの設定**、 をクリック**ホスト インスタンス**です。  
  
3.  結果ウィンドウで、ホスト インスタンス (通常は、コンピューター名) を右クリックし、をクリックして**停止**です。  
  
     ホスト インスタンスの状態に変わる**Stopped**です。  
  
4.  結果ウィンドウで、ホスト インスタンスを右クリックし、をクリックして**開始**です。  
  
 これで、アプリケーションで HTTP.NET アダプターを使用する準備が整いました。 アダプターは、の形式を構成するときに、**仮想ディレクトリ**の形式は、トランスポートのプロパティ:/httpreceive/httpreceive.aspx?optionalQueryString です。  
  
## <a name="comments"></a>コメント  
 提供される BaseAdapter クラスを使用して HTTP.NET アダプターは*\<サンプル パス\>* \AdaptersDevelopment\BaseAdapter\v1.0.2\\です。 BaseAdapter プロジェクトで提供されるクラスは、アダプターの開発を迅速化するためのものです。 提供されるクラスの詳細については、BaseAdapter コードのコメントを参照してください。  
  
## <a name="see-also"></a>参照  
 [アダプターの登録](../core/registering-an-adapter.md)   
 [アダプタ サンプル – 使用状況](../core/adapter-samples-usage.md)   
 [カスタム アダプターの開発](../core/developing-custom-adapters.md)   
 [アダプター フレームワークとは何ですか。](../core/what-is-the-adapter-framework.md)   
 [アダプター フレームワーク ツールを使用します。](../core/using-the-adapter-framework-tools.md)   
 [開発、受信アダプター](../core/developing-a-receive-adapter.md)   
 [送信アダプターの開発](../core/developing-a-send-adapter.md)   
 [カスタム アダプターを展開する方法](../core/how-to-deploy-a-custom-adapter.md)   
 [アダプターのデザインに関するヒント](../core/tips-for-designing-your-adapter.md)   
 [アダプターのデザイン時構成](../core/adapter-design-time-configuration.md)