---
title: 'チュートリアル: Wcf-basichttp アダプターで WCF サービスの使用 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d280198-ba55-4937-91c9-19d6d0ed3194
caps.latest.revision: 49
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3c85d550e7a1429e18035629517017c90b44c9e
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
ms.locfileid: "26010979"
---
# <a name="walkthrough-consuming-wcf-services-with-the-wcf-basichttp-adapter"></a>チュートリアル: Wcf-basichttp アダプターで WCF サービスの使用
  
> [!NOTE]
>  アダプターの詳細については、次を参照してください。 [BizTalk Server のアダプター](../core/adapters-in-biztalk-server.md)です。  
  
## <a name="introduction"></a>概要
  
 このチュートリアルでは、インターネット インフォメーション サービス (IIS) の内部でホストされている [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] サービスを、BizTalk メッセージングと WCF-BasicHttp 送信アダプターを使用して利用します。 このアダプターを使用して、 **BasicHttpBinding** Microsoft 間の仲介役として機能する Web サービスの以前のバージョンと互換性のあるトランスポート/プロトコル スタックを実装するバインド[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]機能します。 オーケストレーションは、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] アダプターを使用する送信ポートにバインドして、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスを呼び出し、論理ビジネス プロセス内でその機能を活用できます。  
  
 WCF-BasicHttp アダプターは、受信アダプターと送信アダプターの 2 つで構成されます。 このサンプルでは、このアダプターの送信側のみを使用し、HTTP プロトコルを使用して [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスへの WCF サービス要求を行います。  送信請求 - 応答送信ポートの場合、送信アダプターは [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスに送信して、結果の応答を受信します。  逆に、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 受信アダプターを使用すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションを公開し、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] クライアント アプリケーションによって外部的に呼び出すことができます。 参照してください、 [WCF サービスの公開](../core/publishing-wcf-services.md)の詳細。  
  
 このチュートリアルを完了すると、次のタスクを実行できるようになります。  
  
-   内から[!INCLUDE[btsCoName](../includes/btsconame-md.md)]Visual Studio を使用して、**展開**コマンドを含むアセンブリを展開する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューションおよび[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービスのローカル インスタンスを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。 これにより、アセンブリが含まれた BizTalk アプリケーションが作成されます。  
  
-   Visual Studio を使用して、 **BizTalk WCF サービス使用ウィザード**を生成する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]スキーマと型を使用するために必要な[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービス。 論理ポートへのバインドに使用できる空のオーケストレーションも生成されます。 このオーケストレーションは、スキーマおよび型と共にコンパイルおよび展開されます。 ただし、これは単なる純粋な [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] メッセージング シナリオなので、オーケストレーション ワークフロー処理は空で、このサンプルでは使用されません。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールから、WCF-BasicHttp 送信ポートを使用するコンテンツ ベースのルーティングを構成する。 構成、 **SOAPAction**ヘッダーをターゲット[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービスが受信します。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールからフィルター式を構成し、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスが送信する可能性のある SOAP エラー メッセージが出力フォルダーにルーティングされるようにする。  
  
-   インターネット インフォメーション サービス (IIS) マネージャーから、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスをホストする Web アプリケーションを構成し、そのメタデータを公開する。 有効にした後、 **BizTalk WCF サービス使用ウィザード**にアクセスするには、型およびスキーマを生成するには、このメタデータを取得できます、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービス。  
  
## <a name="prerequisites"></a>前提条件  
 このサンプルの手順を実行するには、使用する環境が次の前提条件を満たしている必要があります。  
  
-   サンプルを実行するコンピューターと、アセンブリをビルドおよび展開プロセスを実行するコンピューターの両方の必要な Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]、Microsoft [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)]、および Microsoft BizTalk Server です。  
  
-   アセンブリのビルドと展開プロセスの実行に使用するコンピューターには、Microsoft Visual Studio が必要です。  
  
-   サンプルを実行するコンピューターには、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] アダプターと [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 管理ツールが必要です。 これらは、Microsoft BizTalk Server のセットアップ時にインストールするオプションです。  
  
-   管理タスクの実行に使用するコンピューターで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソール内の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーション設定を構成するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーであるユーザー アカウントとして実行する必要があります。 また、アプリケーションの展開、ホスト インスタンスの管理、およびその他の必要なタスクを実行するには、このユーザー アカウントはローカル管理者グループのメンバーである必要もあります。  
  
-   必要とする任意のコンピューターで[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]、機能の 1 回限りのセットアップの手順を完了、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]ではサンプル[ http://go.microsoft.com/fwlink/?LinkId=135510](http://go.microsoft.com/fwlink/?LinkId=135510)です。  
  
-   サンプルを実行してバインドまたは .msi ファイルを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にインポートするコンピューターで、ホストが信頼されているホストではないことを確認します。信頼されているホストの場合、インポートは失敗します。  
  
-   このチュートリアルのコードをダウンロードし、お使いのコンピューターに展開する必要があります。  このチュートリアルでは、全体の一部[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]アダプター チュートリアル パッケージです。 ファイルをダウンロードする**WCFAdapterWalkthroughs.exe**から、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]デベロッパー センター[http://go.microsoft.com/fwlink/?LinkId=194140](http://go.microsoft.com/fwlink/?LinkId=194140)です。  
  
## <a name="deploy-the-sample-wcf-service"></a>サンプル WCF サービスを展開します。  
  
1.  自己解凍形式実行 **WCFBasicHttpSendAdapter.exe** ファイルし、ファイルを **C:\WCFBasicHttpSendAdapter** フォルダーです。  
  
2.  開く、 **C:\WCFBasicHttpSendAdapter\WCFBasicHttpSendAdapter.sln** Visual Studio でします。  
  
3.  ソリューション エクスプ ローラーで、 **BasicHttpWCFServiceConsuming** プロジェクトです。 このプロジェクトは、送信ポートにより呼び出される [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスです。 インターネット インフォメーション サービス (IIS) を使用して管理対象ホスト環境でホストされます。 IIS のホスティングでは、メッセージベースのアクティブ化を使用して、サービスのアクティブ化と有効期間を管理します。 展開 **App_Code**, 、クリックして **OrderProcess.cs** を確認します。 これは、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービスを介して発注要求メッセージを受信する、 **OrderRequest**メソッドです。 OrderProcess.cs ファイルには、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスのインターフェイスの定義と実装が含まれます。 これは、注文を返します経由で応答メッセージ、 **OrderResponse** メソッドです。  
  
4.  OrderProcess.svc ファイルを確認します。 このファイルは 1 行だけで、クライアント アプリケーション用のサービスをアクティブ化するように IIS に指示します。 **@ServiceHost**サービスをホストするための属性が内の拡張ポイント、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]プログラミング モデルです。 ファクトリ パターンを使用して**ServiceHostFactory**のインスタンスを作成する**ServiceHost**のインスタンスと、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]着信要求を処理するサービスです。 このインスタンスのインスタンス化の基に、 **ServiceBehaviorAttribute.ConcurrencyMode** プロパティで、サービスが 1 つのスレッド、複数のスレッド、または再入可能呼び出しをサポートするかどうかを決定します。 インスタンス化はによっても決定、 **ServiceBehavior.InstanceMode** を 1 つのインスタンスを作成する場合の呼び出しごと (ステートレス)、1 つのインスタンスはすべての呼び出し元 (シングルトン) になる場合、またはセッション (ステートフル) ごとに 1 つのインスタンスを作成する場合を決定するプロパティです。  
  
    ```  
    <%@ServiceHost language=c# Debug="true" Service="Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BasicHttpWcfServiceConsuming.OrderProcessServiceType" %>  
    ```  
  
5.  ソリューション エクスプ ローラーで、Visual Studio で開きます**Web.config**を確認します。 IIS でホストされるときは、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスは、コンソール アプリケーションでホストされるときの app.config ファイルではなく、Web.config ファイルを使用して構成されます。  
  
    -   確認して、 **httpGetEnabled**の属性、 \< **serviceMetaData** \>要素に設定されている`true`できるように、 **BizTalk WCF サービスウィザードを使用**サービスのメタデータを使用することができます。  
  
    -   確認して、**モード**の属性、 \<**セキュリティ**\>要素に設定されている**None**です。 このチュートリアルを使用するため、 **None** セキュリティ モードと Web のこのサービスをホストするアプリケーションは、匿名アクセスを許可するように構成する必要があります。  
  
6.  **Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BasicHttpWcfServiceConsuming** アセンブリを GAC にインストールする必要があります、厳密な名前キー ファイルを展開プロセスを完了する必要があります。 右クリックし、 **BasicHttpWcfServiceConsuming** [プロジェクト] をクリックして **プロパティ**します。 **プロパティ** ] ページで [ **署名**, を選択して **アセンブリに署名**します。 下矢印をクリックして、**厳密な名前キー ファイルを選択して**ドロップダウン リスト をクリックして**\<新規\>**、入力と`keyfile.snk`で、**キー ファイル名** テキスト ボックス。  オフに **パスワードでキー ファイルを保護する**, 、 をクリックし、 **ok**します。  
  
7.  ソリューション エクスプ ローラーで右クリック **BasicHttpWcfServiceConsuming**, 、クリックして **を再構築**します。  
  
8.  内容をコピーする Windows エクスプ ローラーを使用して **C:\WCFBasicHttpSendAdapter\BasicHttpWCFServiceConsuming** に、 **C:\InetPub\wwwroot** フォルダーです。  
  
9. 次の手順に従い、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスをホストする Web アプリケーションを構成します。  
  
    1.  をクリックして **開始**, 、 をポイント **管理者ツール**, 、順にクリック **インターネット インフォメーション サービス (IIS) マネージャー**します。  
  
    2.  このサービスが実行されるアプリケーション プールを作成します。 右クリックし **アプリケーション プール**, 、 をクリックして **アプリケーション プールの追加...**, 、アプリケーション プールの名前を入力し、クリックして **OK**します。  
  
    3.  展開 **アプリケーション プール**, 、作成したアプリケーション プールを右クリックし、 **の詳細設定**します。 **プロセス モデル**セクションで、アクセスを許可されているアカウントを入力して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースで、 **Identity**フィールドです。  
  
    4.  展開**サイト**、展開**既定の Web サイト**を右クリックして**BasicHttpWCFServiceConsuming**、クリックして**アプリケーションへの変換**この Web アプリケーションを作成する[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービス。  
  
    5.  **アプリケーションへの変換** ダイアログ ボックスで、をクリックして **選択** を以前に作成されたアプリケーション プールを選択し、をクリックして **[ok]** します。  
  
    6.  [機能ビュー] をクリックして、 **認証** アイコンいることを確認し、 **匿名認証** オプションは、 **有効になっている**します。 これをサポートしている[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]を使用するサービス、 **None**セキュリティ モード。  
  
10. 次の手順に従い、公開した [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスをテストします。  
  
    1.  IIS マネージャーで、展開 **Websites**, 、順に展開 **BasicHttpWCFServiceConsuming**します。  
  
    2.  IIS マネージャーで、右側のウィンドウで右クリックし **OrderProcess.svc**, 、クリックして **参照**します。 表示する Internet Explorer が開き、 **OrderProcessServiceType Service**を実行が正常に作成を示すページ[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービス。 このページには、完全な WSDL アドレスも含まれます。サービス メタデータ ツール (svcutil.exe) で、このアドレスをコピーして使用することで、サービスのクライアント アプリケーションを開発するために使用できるプロキシ コードおよび構成ファイルを作成できます。  
  
    3.  完全な WSDL アドレスをシステム クリップボードにコピーします。 コピーしない、 **"svcutil.exe"** 一部: **http://localhost/BasicHttpWcfServiceConsuming/OrderProcess.svc?wsdl**  
  
## <a name="add-the-schemas-and-types-for-the-wcf-basichttp-adapter-to-the-sample-biztalk-application"></a>サンプル BizTalk アプリケーションに、スキーマと Wcf-basichttp アダプターの種類を追加します。  
  
1.  アダプターは [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスを呼び出すので、メタデータを使用してそのサービスに対してその呼び出しを実行する方法について、スキーマおよび型の情報を必要とします。 **BizTalkApp**を消費するアーティファクトを提供、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービス。 Visual Studio で、ソリューション エクスプ ローラーで右クリックし**BizTalkApp**をクリックして**追加**、順にクリック**生成した項目の追加**です。  
  
2.  **生成した項目の追加** ダイアログ ボックスで、 **テンプレート**  セクションの  **WCF サービスの使用**, 、 をクリックし、 **追加**します。  
  
3.  **BizTalk WCF サービス使用ウィザードへようこそ** ] ページで [ **次**します。 このウィザードは、メタデータを読み取り、スキーマと型を作成します。  
  
4.  **メタデータ ソース** ] ページで、[、 **Metadata Exchange (MEX) エンドポイント** オプションを前の手順でクリップボードにコピーした URL からメタデータを使用して、をクリックする **次**します。  
  
5.  **メタデータ エンドポイント** ページで、前の手順でコピーした完全な WSDL アドレスを貼り付けます、**メタデータ アドレス**クリックしてドロップダウン リスト、**取得**を取得するにはこのサンプルのメタデータ ドキュメント[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービス。 により、メタデータの取得、 **次**  ボタンをクリックします。 **[次へ]** をクリックして次に進みます。  
  
6.  **WCF サービス メタデータの概要のインポート**  ページで、設定内容を確認します。 このダイアログ ボックスには、インポート対象のメタデータの名前空間、XSD、および WSDL の概要が表示されます。 また、インポート処理中にオーケストレーション (.odx)、バインド (.xml)、およびスキーマ (.xsd) ファイルが書き込まれる場所を示します。 をクリックして**インポート**BizTalk アイテムと、サンプルを使用するために使用される型を作成する[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービス。  
  
7.  **BizTalk WCF サービス使用ウィザードを完了する** ] ページで [ **完了**します。  
  
8.  Visual Studio で、ソリューション エクスプ ローラーで、 **BizTalk WCF サービス使用ウィザード**次のファイルが生成されます。  
  
    -   オーケストレーション ファイル **OrderProcessServiceType.odx**します。 このオーケストレーションにはワークフロー ステージはありません。 ただし、オーケストレーションに追加し、論理ポートにバインドして、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスを使用できます。 オーケストレーションには、このサンプルで使用されるポートの種類やマルチパート メッセージの種類などの BizTalk の重要な型が含まれます。 この情報を表示する をダブルクリック、 **OrderProcessServiceType.odx** オーケストレーションします。 クリックして **ビュー**, 、 をクリックして **その他のウィンドウ**, 、 をクリック **オーケストレーションの種類**します。 展開 **型**, 、展開 **ポートの種類**, 、順に展開 **IOrderProcess**します。 表示されます、 **送信** メソッドです。 そのメソッドを展開して表示されます、 **OrderRequest** と **OrderResponse** ポートの種類。 各ポートの種類およびビューをクリックして、 **説明** フィールド入力と出力メッセージのプロパティ ブラウザーと各種の WSDL を参照してください。 をクリックして **マルチパート メッセージの種類** を表示し、 **OrderRequest** と **OrderResponse** マルチパート メッセージの種類。 クリックして、 **説明** フィールドとビューの WDSL メッセージの各メッセージの種類の名前。  
  
    -   2 つのスキーマ ファイルが生成されます。 最初のスキーマ ファイル (**OrderProcessServiceType_biztalk_WCF_basichttpsendadapter_basichttpWCFserviceconsuming.xsd**) を定義するメッセージの種類、サンプル[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービスで使用します。 使用して、 **OrderID** フィールドが両方とも  **OrderRequest** と **OrderResponse** 呼び出しです。  
  
    -   2 番目のスキーマ ファイル (**OrderProcessServiceType_schemas_microsoft_com_2003_10_Serialization.xsd**) によってエクスポートされた[DataContractSerializer](http://go.microsoft.com/fwlink/?LinkId=81722)の型、要素、および属性を名前空間、http://schemas.microsoft.com/2003/10/Serialization/です。  
  
    -   2 つのバインド ファイルが生成され、BizTalk アプリケーションの作成後で使用される: **OrderProcessServiceType.BindingInfo.xml** と **OrderProcessServiceType_Custom.BindingInfo.xml**します。 通常は、非カスタム バインド ファイルを使用します。 ただし、カスタム バインド要素を使用する一部の特別な状況では、カスタム バインド ファイルを使用します。 カスタム バインド要素は、アプリケーション用の送信ポートを作成します。 ダブルクリックして、 **OrderProcessServiceType.BindingInfo.xml**ファイルを検索して、 **SendPort**定義の行、およびレビューにこのバインドをインポートするときに作成される送信ポートのファイル[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
        ```  
        <SendPort Name="WCFSendPort_OrderProcessServiceType_ServiceEndpoint" …  >  
        ```  
  
    -   [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] アダプターを使用する送信ポートは、メタデータで記述されているサンプルの [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスを使用するために、これらのファイルを使用します。  
  
## <a name="deploy-the-sample-biztalk-solution-biztalkapp"></a>サンプル BizTalk ソリューションの BizTalkApp を展開します。  
  
1.  次の手順に従い、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーションを展開します。  
  
    1.  Visual Studio で、ソリューション エクスプ ローラーで右クリック**BizTalkApp**、クリックして**プロパティ**です。  
  
    2.  **プロジェクト デザイナー**ウィンドウで、をクリックして**展開**タブをクリックし、変更、**サーバー**の別のデータベース サーバーを使用する場合は、プロパティ、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理データベース。 アプリケーション名を確認して **WCFBasicHttpSendAdapter**します。  
  
    3.  Visual Studio で、ソリューション エクスプ ローラーで右クリック**BizTalkApp**、順にクリック**リビルド**です。  
  
    4.  Visual Studio で、ソリューション エクスプ ローラーで右クリック**BizTalkApp**、クリックして**展開**です。  これは、Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BizTalkApp アセンブリとを展開、GAC に成果物、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]という名前のアプリケーション**WCFBasicHttpSendAdapter**です。  
  
2.  次の手順に従い、BizTalk アプリケーションの WCF-BasicHttp 送信ポートを構成します。  
  
    1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
    2.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[ **BizTalk グループ**、展開**アプリケーション**を右クリックして**WCFBasicHttpSendAdapter** ]をポイント**インポート**、クリックして**バインド**です。  
  
    3.  **バインドのインポート**  ダイアログ ボックスで、 **C:\WCFBasicHttpSendAdapter\BizTalkApp** フォルダーを選択 **OrderProcessServiceType.BindingInfo.xml**, 、 をクリックし、 **開く**します。 これは作成されたバインド ファイルの 1 つ、 **BizTalk WCF サービス使用ウィザード** 以前です。 こうと、 **WCFSendPort_OrderProcessServiceType_ServiceEndpoint** ポートを送信します。  
  
    4.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **WCFBasicHttpSendAdapter**、クリックして**送信ポート**です。  
  
    5.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールの右側のペインをダブルクリックして**WCFSendPort_OrderProcessServiceType_ServiceEndpoint**、バインド ファイルをインポートすることで作成されました。OrderProcessServiceType.BindingInfo.xml です。 すると、 **送信ポートのプロパティ**  ダイアログ ボックス。  
  
    6.  **送信ポートのプロパティ**  ダイアログ ボックスをクリックして **構成**します。  
  
    7.  **全般** レビュー タブ、 **アドレス** フィールド **http://localhost/BasicHttpWcfServiceConsuming/OrderProcess.svc**します。 これは、WCF-BasicHttp アダプターが呼び出す、IIS でホストされている [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスのアドレスです。  
  
    8.  内容を確認、 **SOAP アクション ヘッダー/アクション** テキスト ボックス。  
  
        ```  
        <BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
          <Operation Name="Submit" Action="http://Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BasicHttpWcfServiceConsuming/IOrderProcess/Submit" />  
        </BtsActionMapping>  
        ```  
  
         このフィールドは、送信 SOAP HTTP 要求メッセージの目的を示します。 ここでは、Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BasicHttpWcfServiceConsuming 名前空間の IOrderProcess インターフェイスで送信操作を呼び出します。  
  
        > [!NOTE]
        >  バインド ファイルで、 **BizTalk WCF サービス使用ウィザード** アクション マッピング形式の使用を生成、 **StaticAction** プロパティです。 WCF 送信メッセージを WCF サービスに送信するアダプターのコンテンツ ベース ルーティングを使用する場合は、設定する必要があります。、 **BTS します。操作** コンテンツ ベースのルーティングに使用するフィールドとアクション マッピング形式のパイプライン コンポーネントのプロパティです。 または、コンテンツ ベースのルーティングに対しシングル アクション形式も使用できます。 このチュートリアルでは、シングル アクション形式を使用します。 シングル アクション形式とアクション マッピング形式の詳細については、次を参照してください。、 **Wcf-basichttp トランスポートのプロパティ ダイアログ ボックス、送信、一般的な**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。  
  
    9. をクリックして**OK**に戻るには 2 回、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
3.  一方向の静的受信ポートおよび FILE 受信場所を作成します。 受信ポートとは、1 つ以上の受信場所に対する論理的なコンテナーです。 ファイル アダプターによって選択されたサンプル [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] メッセージをここにドロップしてから、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスに送信します。  
  
    1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[ **WCFBasicHttpSendAdapter**を右クリックして**受信ポート**、] をポイント**新規**、クリックして**一方向受信ポート**です。  
  
    2.  **受信ポートのプロパティ** ダイアログ ボックスで、 **名前** テキスト ボックスに「 `WCFBasicSendAdapter.ReceivePurchaseOrder`, 、 をクリックし、 **ok**します。  
  
    3.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックして**WCFBasicHttpSendAdapter.ReceivePurchaseOrder**、 をポイント**新規**、クリックして**受信場所の**.  
  
    4.  **受信場所のプロパティ** ダイアログ ボックスで、 **名前** テキスト ボックスに「 `WCFBasicSendAdapter.ReceivePurchaseOrder.FILE`します。  
  
    5.  **受信場所のプロパティ** ダイアログ ボックスで、 **トランスポート** 横 **型**,  **ファイル** クリックしてドロップダウン リストから **構成**します。  
  
    6.  **FILE トランスポートのプロパティ**  ダイアログ ボックスの 、 **全般**   タブの 、 **受信フォルダー** テキスト ボックスに「 `C:\WCFBasicHttpSendAdapter\OrderRequestIn`, 、 をクリックし、 **ok**します。  
  
    7.  **受信場所のプロパティ** ダイアログ ボックスで、をクリックして **OK**します。  
  
4.  前のステップで作成した FILE 受信場所から WCF-BasicHttp 送信ポートにメッセージをルーティングするフィルターを作成します。 ポートに関連付けられたフィルターは SQL の "where" 句と同じように機能し、true と評価されるとメッセージがそのポートに送られます。  
  
    1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[ **WCFBasicHttpSendAdapter**、] をクリックして**送信ポート**、順にダブルクリック**WCFSendPort_OrderProcessServiceType_ServiceEndpoint**です。  
  
    2.  **送信ポートのプロパティ**  ダイアログ ボックスで、 **フィルター**  タブで  **BTS します。ReceivePortName** で、 **プロパティ** フィールドに「 `WCFBasicSendAdapter.ReceivePurchaseOrder` で、 **値** フィールドをクリック **OK**します。 このフィルター式は、受信メッセージを WCFBasicSendAdapter.ReceivePurchaseOrder 受信ポートからこの WCF-BasicHttp 送信ポートにルーティングします。  
  
5.  サンプル アプリケーションの 2 つの FILE 送信ポートを作成します。 最初の送信ポートは、出力応答メッセージを [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスから FILE ポートに送信します。 2 番目の送信ポートは、クライアントに対して定義されている [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスから送信されるエラー メッセージを処理するために使用されます。  
  
    1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[ **WCFBasicHttpSendAdapter**を右クリックして**送信ポート**、] をポイント**新規**、クリックして**静的な一方向送信ポート**です。  
  
    2.  **送信ポートのプロパティ** ダイアログ ボックスで、 **名前** テキスト ボックスに「 `WCFBasicSendAdapter.SendPurchaseOrder.FILE`します。  
  
    3.  **送信ポートのプロパティ** ダイアログ ボックスで、 **トランスポート** 選択の種類の横にあるセクション **ファイル** クリックしてドロップダウン リストから **構成**します。  
  
    4.  **FILE トランスポートのプロパティ**  ダイアログ ボックスの 、 **全般**  タブの 、 **インストール先フォルダー** テキスト ボックスに「 `C:\WCFBasicHttpSendAdapter\OrderResponseOut`, 、 をクリックし、 **ok**します。  
  
    5.  **送信ポートのプロパティ** ダイアログ ボックスで、**フィルター** ] タブで [ **BTS です。MessageType**で、**プロパティ**フィールドに「`http://Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BasicHttpWCFServiceConsuming#OrderResponse`で、**値**サンプルからの応答メッセージの種類を指定するフィールド[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービス、およびをクリックして**OK**です。 このフィルター式は、応答メッセージをサンプル [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスからこの FILE 送信ポートにルーティングします。 送信ポートは、フィルターのプロパティで種類を指定することにより、種類が OrderResponse のメッセージをサブスクライブします。 これは、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスからの応答メッセージのメッセージの種類です。  
  
    6.  **送信ポートのプロパティ** ダイアログ ボックスで、をクリックして **OK**します。  
  
    7.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[ **WCFBasicHttpSendAdapter**を右クリックして**送信ポート**、] をポイント**新規**、クリックして**静的な一方向送信ポート**です。  
  
    8.  **送信ポートのプロパティ** ダイアログ ボックスで、 **名前** テキスト ボックスに「 `WCFAdapterErrorSend.FILE`します。  
  
    9. **送信ポートのプロパティ** ダイアログ ボックスで、 **トランスポート** 横 **型**,  **ファイル** クリックしてドロップダウン リストから **構成**します。  
  
    10. **FILE トランスポートのプロパティ**  ダイアログ ボックスの 、 **全般**  タブの 、 **インストール先フォルダー** テキスト ボックスに「 `C:\WCFBasicHttpSendAdapter\WCFAdapterErrorOut\`, 、 をクリックし、 **ok**します。  
  
    11. **送信ポートのプロパティ**  ダイアログ ボックスで、 **フィルター**  タブで  **WCF です。IsFault** で、 **プロパティ** フィールドに「 `True` で、 **値** フィールドをクリック **OK**します。 アプリケーション内で、例外またはエラーをチェックして検出できる、 **WCF です。IsFault** 呼び出し元に送信されるメッセージのプロパティです。 このプロパティに設定されます **True** 送信されるメッセージが SOAP エラー メッセージである場合。 このフィルター式は、エラー メッセージをサンプル [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスからこの FILE 送信ポートにルーティングします。  
  
6.  次の手順で、サンプル アプリケーションのホスト名とバインドを指定します。  
  
     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[ **WCFBasicHttpSendAdapter**、展開**オーケストレーション**を右クリックし、 **Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BizTalkApp.OrderProcessServiceTypeClient**オーケストレーションをクリックして**プロパティ**、] をクリックして**バインド**設定してください**ホスト**に**BizTalkServerApplication**、順にクリック**OK**構成を保存します。  
  
## <a name="test-the-sample-solution-with-the-wcf-basichttp-send-adapter"></a>テスト サンプル ソリューションで、Wcf-basichttp 送信アダプター  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックして**WCFBasicHttpSendAdapter**、順にクリック**開始**です。  
  
2.  **開始** ダイアログ ボックスで、をクリックして **開始**します。  
  
3.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、**プラットフォームの設定**、展開**ホスト インスタンス**を右クリックして**BizTalkServerApplication**または別クリックして、ホスト インスタンスの適切な**再起動**です。  
  
4.  コマンド プロンプト ウィンドウで「を開く **iisreset** を IIS とその依存サービスをリサイクルし、ENTER キーを押します。  
  
5.  コマンド プロンプトで次のようにコピーします。 **C:\WCFBasicHttpSendAdapter\TestData\WCFBasicSendAdapter.OrderRequest.Sample.xml** に、 **C:\WCFBasicHttpSendAdapter\OrderRequestIn** フォルダーです。 このメッセージは、双方向にルーティング **WcfSendPort_OrderProcessServiceType_ServiceEndpoint** 静的な送信請求-応答送信ポート。  この双方向の送信側の送信ポートの呼び出し**送信**メソッドを[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]IIS でホストされるサービスです。 応答のポートに、結果が返される、 **WcfSendPort_OrderProcessServiceType_ServiceEndpoint** ポートを送信します。  **WCFBasicSendAdapter.SendPurchaseOrder.FILE**送信ポートには、メッセージの種類がトリガーされるサブスクリプション **http://Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BasicHttpWCFServiceConsuming#OrderResponse**です。正常に処理されたメッセージが表示されに書き込む、 **C:\WCFBasicHttpSendAdapter\OrderResponseOut**フォルダーです。  
  
6.  チェック、 **C:\WCFBasicHttpSendAdapter\OrderResponseOut**からの応答メッセージ用のフォルダー、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービス。  
  
7.  コマンド プロンプトで **C:\WCFBasicHttpSendAdapter\TestData\WCFBasicSendAdapter.OrderRequest.Invalid.xml** に、 **C:\WCFBasicHttpSendAdapter\OrderRequestIn** フォルダーです。 このメッセージには無効な名前空間が含まれており、そのため [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスはエラー メッセージを返します。  
  
8.  チェック、 **C:\WCFBasicHttpSendAdapter\WCFAdapterErrorOut**からのエラー メッセージを含む XML ファイルのフォルダー、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービス。 見て、 \< **faultstring** \>フィールドに無効なメッセージ本文のエラー メッセージの原因を表示します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル: Wcf-basichttp アダプタを使用して WCF サービスの発行](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)   
 [BizTalk WCF サービス使用ウィザードを使用して WCF サービスを使用する方法](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md)   
 [WCF アダプターのメッセージ本文の指定](../core/specifying-the-message-body-for-the-wcf-adapters.md)