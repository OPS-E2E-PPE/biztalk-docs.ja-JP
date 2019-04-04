---
title: 'チュートリアル: Wcf-basichttp アダプターを使用した WCF サービスの使用 |Microsoft Docs'
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
ms.openlocfilehash: 2d72ccdb39bec5e063f48206df0bfcc54364d11c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981427"
---
# <a name="walkthrough-consuming-wcf-services-with-the-wcf-basichttp-adapter"></a>チュートリアル: Wcf-basichttp アダプターを使用した WCF サービスの使用
  
> [!NOTE]
>  アダプターの詳細については、[BizTalk Server のアダプター](../core/adapters-in-biztalk-server.md)を参照してください。  
  
## <a name="introduction"></a>概要
  
 このチュートリアルでは、インターネット インフォメーション サービス (IIS) の内部でホストされている [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] サービスを、BizTalk メッセージングと WCF-BasicHttp 送信アダプターを使用して利用します。 このアダプターを使用して、 **BasicHttpBinding** Microsoft の間のブリッジとして機能する Web サービスの以前のバージョンと互換性のあるトランスポート/プロトコル スタックを実装するバインド[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]機能。 オーケストレーションは、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] アダプターを使用する送信ポートにバインドして、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスを呼び出し、論理ビジネス プロセス内でその機能を活用できます。  
  
 WCF-BasicHttp アダプターは、受信アダプターと送信アダプターの 2 つで構成されます。 このサンプルでは、このアダプターの送信側のみを使用し、HTTP プロトコルを使用して [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスへの WCF サービス要求を行います。  送信請求 - 応答送信ポートの場合、送信アダプターは [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスに送信して、結果の応答を受信します。  逆に、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 受信アダプターを使用すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションを公開し、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] クライアント アプリケーションによって外部的に呼び出すことができます。 参照してください、 [WCF サービスの公開](../core/publishing-wcf-services.md)の追加情報。  
  
 このチュートリアルを完了すると、次のタスクを実行できるようになります。  
  
- 内から[!INCLUDE[btsCoName](../includes/btsconame-md.md)]Visual Studio を使用して、**デプロイ**を含むアセンブリを展開するコマンド、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューションと[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービスのローカル インスタンスを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 これにより、アセンブリが含まれた BizTalk アプリケーションが作成されます。  
  
- Visual Studio 内で使用して、 **BizTalk WCF サービス使用ウィザード**を生成する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]スキーマと型を使用するために必要な[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービス。 論理ポートへのバインドに使用できる空のオーケストレーションも生成されます。 このオーケストレーションは、スキーマおよび型と共にコンパイルおよび展開されます。 ただし、これは単なる純粋な [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] メッセージング シナリオなので、オーケストレーション ワークフロー処理は空で、このサンプルでは使用されません。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールから、WCF-BasicHttp 送信ポートを使用するコンテンツ ベースのルーティングを構成する。 構成、 **SOAPAction**ヘッダーをターゲット[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービスが受信します。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールからフィルター式を構成し、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスが送信する可能性のある SOAP エラー メッセージが出力フォルダーにルーティングされるようにする。  
  
- インターネット インフォメーション サービス (IIS) マネージャーから、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスをホストする Web アプリケーションを構成し、そのメタデータを公開する。 有効にした後、 **BizTalk WCF サービス使用ウィザード**にアクセスするには、型およびスキーマを生成するには、このメタデータを取得することができます、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービス。  
  
## <a name="prerequisites"></a>必須コンポーネント  
 このサンプルの手順を実行するには、使用する環境が次の前提条件を満たしている必要があります。  
  
- アセンブリをビルドし、展開プロセスを実行するコンピューターと、サンプルを実行しているコンピューターの両方の必要な Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]、Microsoft [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)]、および Microsoft BizTalk Server です。  
  
- アセンブリのビルドと展開プロセスの実行に使用するコンピューターには、Microsoft Visual Studio が必要です。  
  
- サンプルを実行するコンピューターには、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] アダプターと [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 管理ツールが必要です。 これらは、Microsoft BizTalk Server のセットアップ時にインストールするオプションです。  
  
- 管理タスクの実行に使用するコンピューターで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソール内の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーション設定を構成するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーであるユーザー アカウントとして実行する必要があります。 また、アプリケーションの展開、ホスト インスタンスの管理、およびその他の必要なタスクを実行するには、このユーザー アカウントはローカル管理者グループのメンバーである必要もあります。  
  
- 必要とする任意のコンピューターで[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]機能により、1 回限りのセットアップの手順を完了、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サンプル[ http://go.microsoft.com/fwlink/?LinkId=135510](http://go.microsoft.com/fwlink/?LinkId=135510)します。  
  
- サンプルを実行してバインドまたは .msi ファイルを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にインポートするコンピューターで、ホストが信頼されているホストではないことを確認します。信頼されているホストの場合、インポートは失敗します。  
  
- チュートリアルのコードをダウンロードし、コンピューターに展開する必要があります。  このチュートリアルでは全体の一部[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]アダプター チュートリアル パッケージ。 ファイルをダウンロードする**WCFAdapterWalkthroughs.exe**から、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]デベロッパー センター[http://go.microsoft.com/fwlink/?LinkId=194140](http://go.microsoft.com/fwlink/?LinkId=194140)します。  
  
## <a name="deploy-the-sample-wcf-service"></a>サンプル WCF サービスをデプロイします。  
  
1. 自己解凍形式実行**WCFBasicHttpSendAdapter.exe**ファイルを開き、ファイルを**C:\WCFBasicHttpSendAdapter**フォルダー。  
  
2. 開く、 **C:\WCFBasicHttpSendAdapter\WCFBasicHttpSendAdapter.sln** Visual Studio でします。  
  
3. ソリューション エクスプ ローラーで、 **BasicHttpWCFServiceConsuming**プロジェクト。 このプロジェクトは、送信ポートにより呼び出される [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスです。 インターネット インフォメーション サービス (IIS) を使用してマネージド ホスト環境でホストされます。 IIS のホスティングでは、メッセージベースのアクティブ化を使用して、サービスのアクティブ化と有効期間を管理します。 展開**App_Code**を開き**OrderProcess.cs**を確認します。 これは、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービスを介して発注要求メッセージの受信、 **OrderRequest**メソッド。 OrderProcess.cs ファイルには、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスのインターフェイスの定義と実装が含まれます。 これは、注文を返しますを通じて応答メッセージ、 **OrderResponse**メソッド。  
  
4. OrderProcess.svc ファイルを確認します。 このファイルは 1 行だけで、クライアント アプリケーション用のサービスをアクティブ化するように IIS に指示します。 <strong>@ServiceHost</strong>サービスをホストするために使用する属性が内の拡張ポイント、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]プログラミング モデル。 ファクトリ パターンを使用して**ServiceHostFactory**のインスタンスを作成する**ServiceHost**のインスタンスと、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]受信要求を処理するサービス。 このインスタンスのインスタンス化がに基づいて、 **ServiceBehaviorAttribute.ConcurrencyMode**プロパティで、サービスが 1 つのスレッドでは、複数のスレッド、または再入可能呼び出しをサポートするかどうかを決定します。 インスタンス化がによっても決定されます、 **ServiceBehavior.InstanceMode**プロパティは、1 つのインスタンスを作成する場合の呼び出しごと (ステートレス)、1 つだけのインスタンスはすべての呼び出し元 (シングルトン) になる場合、または場合を決定する 1 つのインスタンスセッション (ステートフル) ごとに作成されます。  
  
   ```  
   <%@ServiceHost language=c# Debug="true" Service="Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BasicHttpWcfServiceConsuming.OrderProcessServiceType" %>  
   ```  
  
5. ソリューション エクスプ ローラーで、Visual Studio で開きます**Web.config**を確認します。 IIS でホストされるときは、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスは、コンソール アプリケーションでホストされるときの app.config ファイルではなく、Web.config ファイルを使用して構成されます。  
  
   -   確認、 **httpGetEnabled**の属性、 \< **serviceMetaData** \>要素に設定されて`true`ように、 **BizTalk WCF サービス使用ウィザード**サービスのメタデータを使用することができます。  
  
   -   確認、**モード**の属性、 \<**セキュリティ**\>要素に設定されて**None**します。 このチュートリアルを使用するため、 **None**セキュリティ モードでは、Web のこのサービスをホスト アプリケーションは、匿名アクセスを許可するように構成する必要があります。  
  
6. **Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BasicHttpWcfServiceConsuming**アセンブリを GAC にインストールする必要があります、展開プロセスを完了する厳密な名前キー ファイルは必要があります。 右クリックし、 **BasicHttpWcfServiceConsuming**プロジェクトをクリックして**プロパティ**します。 **プロパティ**] ページで [**署名**を選択し、**アセンブリに署名**します。 下向きの矢印をクリックして、**厳密な名前キー ファイルを選択して**ドロップダウン リストでは、 をクリックして**\<新規\>**、入力と`keyfile.snk`で、**キー ファイル名**テキスト ボックス。  オフに**キーファイルをパスワードで保護する**、順にクリックします**OK**。  
  
7. ソリューション エクスプ ローラーで右クリック**BasicHttpWcfServiceConsuming**、 をクリックし、**リビルド**します。  
  
8. 内容をコピーして Windows Explorer を使用して**C:\WCFBasicHttpSendAdapter\BasicHttpWCFServiceConsuming**を**C:\InetPub\wwwroot**フォルダー。  
  
9. 次の手順に従い、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスをホストする Web アプリケーションを構成します。  
  
   1. クリックして**開始**、 をポイント**管理者ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**します。  
  
   2. このサービスが実行されるアプリケーション プールを作成します。 右クリックして**アプリケーション プール**、 をクリックして**アプリケーション プールの追加.**、アプリケーション プールの名前を入力し、 **OK**します。  
  
   3. 展開**アプリケーション プール**作成したアプリケーション プールを右クリックし、**詳細設定**します。 **プロセス モデル**セクションで、これにアクセスするアカウントを入力、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースで、 **Identity**フィールド。  
  
   4. 展開**サイト**、展開**既定の Web サイト**を右クリックして**BasicHttpWCFServiceConsuming**、 をクリックし、 **アプリケーションへの変換**この Web アプリケーションを作成する[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービス。  
  
   5. **アプリケーションへの変換**ダイアログ ボックスで、をクリックして**選択**を以前に作成したアプリケーション プールを選択し、をクリックし、 **[ok]**。  
  
   6. 機能ビューで、クリックして、**認証**アイコンいることを確認し、**匿名認証**オプションは**有効になっている**します。 これはサポート[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]を使用したサービス、 **None**セキュリティ モード。  
  
10. 次の手順に従い、公開した [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスをテストします。  
  
    1. IIS マネージャーで、展開**Websites**、順に展開**BasicHttpWCFServiceConsuming**します。  
  
    2. IIS マネージャーで、右側のウィンドウで右クリックして**OrderProcess.svc**、 をクリックし、**参照**します。 表示する Internet Explorer が開きます、 **OrderProcessServiceType Service** 、実行が正常に作成を示すページ[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービス。 このページには、完全な WSDL アドレスも含まれます。サービス メタデータ ツール (svcutil.exe) で、このアドレスをコピーして使用することで、サービスのクライアント アプリケーションを開発するために使用できるプロキシ コードおよび構成ファイルを作成できます。  
  
    3. 完全な WSDL アドレスをシステム クリップボードにコピーします。 コピーしないでください、 **"svcutil.exe"** 一部。 **http://localhost/BasicHttpWcfServiceConsuming/OrderProcess.svc?wsdl**  
  
## <a name="add-the-schemas-and-types-for-the-wcf-basichttp-adapter-to-the-sample-biztalk-application"></a>サンプル BizTalk アプリケーションに、スキーマと Wcf-basichttp アダプターの種類を追加します。  
  
1. アダプターは [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスを呼び出すので、メタデータを使用してそのサービスに対してその呼び出しを実行する方法について、スキーマおよび型の情報を必要とします。 **[Biztalkapp]** を使用するアイテムを提供します、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービス。 ソリューション エクスプ ローラーで、Visual Studio で右クリック**biztalkapp**、 をクリックして**追加**、 をクリックし、**生成した項目の追加**します。  
  
2. **生成した項目の追加** ダイアログ ボックスで、**テンプレート**セクションで、 **Consume WCF サービス**、 をクリックし、**追加**します。  
  
3. **BizTalk WCF サービス使用ウィザードへようこそ**] ページで [**次**します。 このウィザードは、メタデータを読み取り、スキーマと型を作成します。  
  
4. **メタデータ ソース**] ページで、[、 **Metadata Exchange (MEX) エンドポイント** 、前の手順でクリップボードにコピーしたURLからメタデータを使用するオプション**次**します。  
  
5. **メタデータ エンドポイント** ページで、前の手順でコピーした完全な WSDL アドレスを貼り付けます、**メタデータ アドレス**ドロップダウン リスト、およびクリック**取得**を取得するにはサンプルのメタデータ ドキュメント[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービス。 により、メタデータの取得、**次**ボタンをクリックします。 **[次へ]** をクリックして次に進みます。  
  
6. **WCF サービス メタデータの概要のインポート**ページで、設定を確認します。 このダイアログ ボックスには、インポート対象のメタデータの名前空間、XSD、および WSDL の概要が表示されます。 また、インポート処理中にオーケストレーション (.odx)、バインド (.xml)、およびスキーマ (.xsd) ファイルが書き込まれる場所も表示されます。 クリックして**インポート**BizTalk アイテムと、サンプルを使用するために使用される型を作成する[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービス。  
  
7. **BizTalk WCF サービス使用ウィザードの完了**] ページで [**完了**します。  
  
8. ソリューション エクスプ ローラーで、Visual Studio で、 **BizTalk WCF サービス使用ウィザード**次のファイルが生成されます。  
  
   - オーケストレーション ファイル**OrderProcessServiceType.odx**します。 このオーケストレーションにはワークフロー ステージはありません。 ただし、オーケストレーションに追加し、論理ポートにバインドして、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスを使用できます。 オーケストレーションには、このサンプルで使用されるポートの種類やマルチパート メッセージの種類などの BizTalk の重要な型が含まれます。 この情報を表示するには、ダブルクリック、 **OrderProcessServiceType.odx**オーケストレーションします。 をクリックして**ビュー**、 をクリックして**その他の Windows**、 をクリック**オーケストレーション**します。 展開**型**、展開**ポートの種類**、順に展開**IOrderProcess**します。 表示されます、**送信**メソッド。 そのメソッドを展開して表示されます、 **OrderRequest**と**OrderResponse**ポートの種類。 各ポートの種類およびビューをクリックします。 その**説明**フィールド入力と出力メッセージのプロパティ ブラウザーで、各種の WSDL を参照してください。 クリックして**マルチパート メッセージの種類**を表示し、 **OrderRequest**と**OrderResponse**マルチパート メッセージの種類。 をクリックして、**説明**フィールドとビューの WDSL メッセージの各メッセージの種類名。  
  
   - 2 つのスキーマ ファイルが生成されます。 最初のスキーマ ファイル (**OrderProcessServiceType_biztalk_WCF_basichttpsendadapter_basichttpWCFserviceconsuming.xsd**) を定義するメッセージの種類、サンプル[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービスで使用します。 使用して、 **OrderID**両方でフィールド**OrderRequest**と**OrderResponse**呼び出し。  
  
   - 2 番目のスキーマ ファイル (**OrderProcessServiceType_schemas_microsoft_com_2003_10_Serialization.xsd**) によってエクスポート[DataContractSerializer](http://go.microsoft.com/fwlink/?LinkId=81722)型、要素、および属性から、名前空間、 http://schemas.microsoft.com/2003/10/Serialization/ します。  
  
   - BizTalk アプリケーションの作成後で使用される、2 つのバインド ファイルが生成されます: **OrderProcessServiceType.BindingInfo.xml**と**OrderProcessServiceType_Custom.BindingInfo.xml**します。 通常は、非カスタム バインド ファイルを使用します。 ただし、カスタム バインド要素を使用する一部の特別な状況では、カスタム バインド ファイルを使用します。 カスタム バインド要素は、アプリケーション用の送信ポートを作成します。 ダブルクリックして、 **OrderProcessServiceType.BindingInfo.xml**ファイルを検索、 **SendPort**定義線、およびレビューにこのバインドをインポートするときに作成される送信ポートのファイル[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
     ```  
     <SendPort Name="WCFSendPort_OrderProcessServiceType_ServiceEndpoint" …  >  
     ```  
  
   - [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] アダプターを使用する送信ポートは、メタデータで記述されているサンプルの [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスを使用するために、これらのファイルを使用します。  
  
## <a name="deploy-the-sample-biztalk-solution-biztalkapp"></a>サンプル BizTalk ソリューションの BizTalkApp を展開します。  
  
1. 次の手順に従い、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーションを展開します。  
  
   1. ソリューション エクスプ ローラーで、Visual Studio で右クリック**BizTalkApp**、 をクリックし、**プロパティ**します。  
  
   2. **プロジェクト デザイナー**ウィンドウで、をクリックして**展開**タブをクリックし、変更、 **Server**プロパティの別のデータベース サーバーを使用する場合、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理データベース。 アプリケーション名を確認して**WCFBasicHttpSendAdapter**します。  
  
   3. ソリューション エクスプ ローラーで、Visual Studio で右クリック**BizTalkApp**、順にクリックします**リビルド**します。  
  
   4. ソリューション エクスプ ローラーで、Visual Studio で右クリック**biztalkapp**、 をクリックし、**デプロイ**します。  Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BizTalkApp アセンブリを GAC され、アイテムをこれにより、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]という名前のアプリケーション**WCFBasicHttpSendAdapter**します。  
  
2. 次の手順に従い、BizTalk アプリケーションの WCF-BasicHttp 送信ポートを構成します。  
  
   1. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
   2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[ **BizTalk グループ**、展開**アプリケーション**を右クリックして**WCFBasicHttpSendAdapter**を指す**インポート**、] をクリックし、**バインド**します。  
  
   3. **バインドのインポート** ダイアログ ボックスに移動して、 **C:\WCFBasicHttpSendAdapter\BizTalkApp**フォルダーで、 **OrderProcessServiceType.BindingInfo.xml**、順にクリックします**オープン**します。 これはによって作成されたバインド ファイルの 1 つ、 **BizTalk WCF サービス使用ウィザード**以前。 これを作成、 **WCFSendPort_OrderProcessServiceType_ServiceEndpoint**ポートを送信します。  
  
   4. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[ **WCFBasicHttpSendAdapter**、] をクリックし、**送信ポート**します。  
  
   5. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]右側のウィンドウで、管理コンソール をダブルクリックします**WCFSendPort_OrderProcessServiceType_ServiceEndpoint**、バインド ファイルをインポートすることによって作成されました。OrderProcessServiceType.BindingInfo.xml します。 すると、**送信ポートのプロパティ** ダイアログ ボックス。  
  
   6. **送信ポートのプロパティ**ダイアログ ボックスで、をクリックして**構成**します。  
  
   7. **全般**レビューのタブ、**アドレス (uri)** フィールド **<http://localhost/BasicHttpWcfServiceConsuming/OrderProcess.svc>** します。 これは、WCF-BasicHttp アダプターが呼び出す、IIS でホストされている [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスのアドレスです。  
  
   8. 内容を確認、 **SOAP アクション ヘッダー/アクション**テキスト ボックス。  
  
      ```  
      <BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
        <Operation Name="Submit" Action="http://Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BasicHttpWcfServiceConsuming/IOrderProcess/Submit" />  
      </BtsActionMapping>  
      ```  
  
       このフィールドは、送信 SOAP HTTP 要求メッセージの目的を示します。 ここでは、Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BasicHttpWcfServiceConsuming 名前空間の IOrderProcess インターフェイスで送信操作を呼び出します。  
  
      > [!NOTE]
      >  バインド ファイルで、 **BizTalk WCF サービス使用ウィザード**アクション マッピング形式の使用を生成、 **StaticAction**プロパティ。 設定する必要があります、WCF 送信アダプターの WCF サービスにメッセージを送信するコンテンツ ベース ルーティングを使用する場合、 **BTS します。操作**コンテンツ ベースのルーティングに使用するフィールドとアクション マッピング形式のパイプライン コンポーネントのプロパティ。 または、コンテンツ ベースのルーティングに対しシングル アクション形式も使用できます。 このチュートリアルでは、シングル アクション形式を使用します。 シングル アクション形式とアクション マッピング形式の詳細については、、 **Wcf-basichttp トランスポートのプロパティ ダイアログ ボックス、送信、一般的な**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]を参照してください。  
  
   9. クリックして**OK**に戻るには 2 回、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
3. 一方向の静的受信ポートおよび FILE 受信場所を作成します。 受信ポートとは、1 つ以上の受信場所に対する論理的なコンテナーです。 ファイル アダプターによって選択されたサンプル [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] メッセージをここにドロップしてから、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスに送信します。  
  
   1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[ **WCFBasicHttpSendAdapter**、右クリックして**受信ポート**、] をポイント**新規**、順にクリックします**一方向受信ポート**します。  
  
   2. **受信ポートのプロパティ** ダイアログ ボックスで、**名前**テキスト ボックスに「 `WCFBasicSendAdapter.ReceivePurchaseOrder`、順にクリックします**OK**します。  
  
   3. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックして**WCFBasicHttpSendAdapter.ReceivePurchaseOrder**、 をポイント**新規**、順にクリックします**受信場所**.  
  
   4. **受信場所のプロパティ** ダイアログ ボックスで、**名前**テキスト ボックスに「`WCFBasicSendAdapter.ReceivePurchaseOrder.FILE`します。  
  
   5. **受信場所のプロパティ** ダイアログ ボックスで、**トランスポート**の横**型**を選択します**ファイル**ドロップダウン リストからクリックして**構成**します。  
  
   6. **FILE トランスポートのプロパティ** ダイアログ ボックスで、**全般** タブで、**受信フォルダー**テキスト ボックスに「 `C:\WCFBasicHttpSendAdapter\OrderRequestIn`、順にクリックします**ok**.  
  
   7. **受信場所のプロパティ**ダイアログ ボックスで、をクリックして**OK**します。  
  
4. 前のステップで作成した FILE 受信場所から WCF-BasicHttp 送信ポートにメッセージをルーティングするフィルターを作成します。 ポートに関連付けられたフィルターは SQL の "where" 句と同じように機能し、true と評価されるとメッセージがそのポートに送られます。  
  
   1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[ **WCFBasicHttpSendAdapter**、] をクリックして**送信ポート**、し、ダブルクリック**WCFSendPort_OrderProcessServiceType_ServiceEndpoint**します。  
  
   2. **送信ポートのプロパティ** ダイアログ ボックスで、**フィルター**  タブで  **BTS します。ReceivePortName**で、**プロパティ**フィールドに「`WCFBasicSendAdapter.ReceivePurchaseOrder`で、**値**フィールドをクリックして**OK**します。 このフィルター式は、受信メッセージを WCFBasicSendAdapter.ReceivePurchaseOrder 受信ポートからこの WCF-BasicHttp 送信ポートにルーティングします。  
  
5. サンプル アプリケーションの 2 つの FILE 送信ポートを作成します。 最初の送信ポートは、出力応答メッセージを [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスから FILE ポートに送信します。 2 番目の送信ポートは、クライアントに対して定義されている [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスから送信されるエラー メッセージを処理するために使用されます。  
  
   1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[ **WCFBasicHttpSendAdapter**、右クリックして**送信ポート**、] をポイント**新規**、順にクリックします**静的な一方向送信ポート**します。  
  
   2. **送信ポートのプロパティ** ダイアログ ボックスで、**名前**テキスト ボックスに「`WCFBasicSendAdapter.SendPurchaseOrder.FILE`します。  
  
   3. **送信ポートのプロパティ** ダイアログ ボックスで、**トランスポート**選択の種類の横にあるセクション**ファイル**クリックしてドロップダウン リストから**構成**.  
  
   4. **FILE トランスポートのプロパティ** ダイアログ ボックスの 、**全般** タブで、**先フォルダー**テキスト ボックスに「 `C:\WCFBasicHttpSendAdapter\OrderResponseOut`、順にクリックします**ok**.  
  
   5. **送信ポートのプロパティ** ダイアログ ボックスで、**フィルター** ] タブで [ **BTS します。MessageType**で、**プロパティ**フィールドに「`http://Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BasicHttpWCFServiceConsuming#OrderResponse`で、**値**サンプルからの応答メッセージの種類を指定するフィールド[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービス、およびクリックして**OK**します。 このフィルター式は、応答メッセージをサンプル [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスからこの FILE 送信ポートにルーティングします。 送信ポートは、フィルターのプロパティで種類を指定することにより、種類が OrderResponse のメッセージをサブスクライブします。 これは、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスからの応答メッセージのメッセージの種類です。  
  
   6. **送信ポートのプロパティ**ダイアログ ボックスで、をクリックして**OK**します。  
  
   7. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[ **WCFBasicHttpSendAdapter**、右クリックして**送信ポート**、] をポイント**新規**、順にクリックします**静的な一方向送信ポート**します。  
  
   8. **送信ポートのプロパティ** ダイアログ ボックスで、**名前**テキスト ボックスに「`WCFAdapterErrorSend.FILE`します。  
  
   9. **送信ポートのプロパティ** ダイアログ ボックスで、**トランスポート**の横**型**を選択します**ファイル**ドロップダウン リストからしクリックして**構成**します。  
  
   10. **FILE トランスポートのプロパティ** ダイアログ ボックスの 、**全般** タブで、**先フォルダー**テキスト ボックスに「 `C:\WCFBasicHttpSendAdapter\WCFAdapterErrorOut\`、順にクリックします**ok**.  
  
   11. **送信ポートのプロパティ** ダイアログ ボックスで、**フィルター**  タブで  **WCF です。IsFault**で、**プロパティ**フィールドに「`True`で、**値**フィールドをクリックして**OK**します。 アプリケーション内で、例外またはエラーをチェックで検出できる、 **WCF です。IsFault**呼び出し元に送信されるメッセージのプロパティ。 このプロパティに設定する**True**送信されるメッセージが SOAP エラー メッセージの場合。 このフィルター式は、エラー メッセージをサンプル [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスからこの FILE 送信ポートにルーティングします。  
  
6. 次の手順で、サンプル アプリケーションのホスト名とバインドを指定します。  
  
    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **WCFBasicHttpSendAdapter**、展開**オーケストレーション**を右クリックし、 **Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BizTalkApp.OrderProcessServiceTypeClient**オーケストレーション、 をクリックして**プロパティ**、 をクリックして**バインド**設定**ホスト**に**BizTalkServerApplication**、順にクリックします**OK**構成を保存します。  
  
## <a name="test-the-sample-solution-with-the-wcf-basichttp-send-adapter"></a>テスト サンプル ソリューションで、Wcf-basichttp 送信アダプター  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリック**WCFBasicHttpSendAdapter**、順にクリックします**開始**します。  
  
2. **開始**ダイアログ ボックスで、をクリックして**開始**します。  
  
3. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、**プラットフォームの設定**、展開**ホスト インスタンス**を右クリックして**BizTalkServerApplication**またはその他クリックして、ホスト インスタンスを適切な**再起動**します。  
  
4. コマンド プロンプト ウィンドウで「を開く**iisreset**に IIS とその依存サービスをリサイクルし、ENTER キーを押します。  
  
5. コマンド プロンプトで次のようにコピーします。 **C:\WCFBasicHttpSendAdapter\TestData\WCFBasicSendAdapter.OrderRequest.Sample.xml**を、 **C:\WCFBasicHttpSendAdapter\OrderRequestIn**フォルダー。 このメッセージは、双方向にルーティング**WcfSendPort_OrderProcessServiceType_ServiceEndpoint**静的な送信請求-応答送信ポート。  この双方向の送信側は送信ポート呼び出し**送信**メソッドを[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]IIS でホストされるサービスです。 応答のポートに、結果が返されます、 **WcfSendPort_OrderProcessServiceType_ServiceEndpoint**ポートを送信します。  **WCFBasicSendAdapter.SendPurchaseOrder.FILE**送信ポートには、メッセージの種類がの場合にトリガーされるサブスクリプション **<http://Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BasicHttpWCFServiceConsuming#OrderResponse>** します。正常に処理されたメッセージを取得し、書き込むため、 **C:\WCFBasicHttpSendAdapter\OrderResponseOut**フォルダー。  
  
6. チェック、 **C:\WCFBasicHttpSendAdapter\OrderResponseOut**フォルダーからの応答メッセージ、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービス。  
  
7. コマンド プロンプトで**C:\WCFBasicHttpSendAdapter\TestData\WCFBasicSendAdapter.OrderRequest.Invalid.xml**を**C:\WCFBasicHttpSendAdapter\OrderRequestIn**フォルダー。 このメッセージには無効な名前空間が含まれており、そのため [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスはエラー メッセージを返します。  
  
8. チェック、 **C:\WCFBasicHttpSendAdapter\WCFAdapterErrorOut**からのエラー メッセージを含む XML ファイルのフォルダー、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービス。 見て、 \< **faultstring** \>フィールドに、無効なメッセージ本文のエラー メッセージの原因を表示します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル: Wcf-basichttp アダプターを使用した WCF サービスの発行](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)   
 [BizTalk WCF サービス使用ウィザードを使用して WCF サービスを使用する方法](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md)   
 [WCF アダプターのメッセージ本文の指定](../core/specifying-the-message-body-for-the-wcf-adapters.md)