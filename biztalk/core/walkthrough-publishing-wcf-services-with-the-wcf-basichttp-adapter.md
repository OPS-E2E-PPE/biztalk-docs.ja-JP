---
title: 'チュートリアル: Wcf-basichttp アダプターを使用した WCF サービスの発行 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tutorials, publishing
- WCF adapters, tutorials
- publishing, WCF services
- WCF-BasicHttp adapters, tutorials
- publishing, tutorials
- WCF services, publishing
- tutorials, WCF adapters
ms.assetid: 43b76215-9cb0-47ab-a085-c4cf265410f9
caps.latest.revision: 72
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3721080fa296ab5e44ee72c2757461843cfb52bd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979779"
---
# <a name="walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter"></a>チュートリアル: Wcf-basichttp アダプターを使用した WCF サービスの発行
## <a name="introduction"></a>概要  
 このチュートリアルでは、BizTalk WCF サービス公開ウィザードおよび WCF-BasicHttp アダプターを使用して、[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] サービスを BizTalk オーケストレーションとして公開します。 WCF-BasicHttp アダプターを使用して [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] エンドポイントを公開することで、BizTalk オーケストレーションは、別の Web サービスや [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] アプリケーションなどの外部クライアントに、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスとして認識されます。 WCF-BasicHttp アダプターは、受信アダプターと送信アダプターの 2 つで構成されます。 このサンプルでは、このアダプターの受信側のみを使用し、HTTP または HTTPS プロトコルを使用して [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] クライアント アプリケーションからの WCF サービス要求を受信します。  
  
 Wcf-basichttp アダプターを使用して、 **BasicHttpBinding**間の仲介役として機能する Web サービスの最初のリリースと互換性のあるトランスポート/プロトコル スタック実装を提供するバインディング[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]機能します。 テキスト エンコードの HTTP または HTTPS トランスポートを使用して、WS-I 基本プロファイル 1.1 に準拠する ASMX ベースのレガシー Web サービスおよびクライアントと通信します。 WCF-BasicHttp アダプターを使用して、WS-* プロトコルによってサポートされる高度な Web 通信機能を利用することはできません。 それが必要な場合は、WCF-WSHttp アダプターを使用してください。  
  
 このチュートリアルでは、WCF-BasicHttp 受信場所を作成してオーケストレーションを [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスとして公開する方法を示します。  [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスの分離されたホスティングを提供するように、インターネット インフォメーション サービス (IIS) を構成します。  クライアント アプリケーションは、外部クライアントが公開された [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスをインターネット経由で呼び出してその機能を使用する方法を示す例として、公開された [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] オーケストレーションを呼び出します。  
  
 このチュートリアルを完了すると、次のタスクを実行できるようになります。  
  
- Visual Studio 内で使用して、**デプロイ**を展開するコマンド、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービスのローカル インスタンスに BizTalk アセンブリ内の BizTalk オーケストレーションの形式で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 Visual Studio からの展開では、オーケストレーション、パイプライン、スキーマ、マップなど、BizTalk ソリューションで使用されるリソースを含むアセンブリと共に生成される BizTalk アプリケーションが作成されます。  
  
- 展開後、BizTalk オーケストレーションは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを介して構成および制御できます。 このチュートリアルでは、WCF-BasicHttp 受信場所を、BizTalk [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービス公開ウィザードで作成される [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスに送信される受信メッセージを受け取るように構成します。 受信場所は、IIS の BizTalk 分離ホストによってホストされ、受信要求を処理する [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスとして機能します。  
  
> [!NOTE]
>  このチュートリアルでは、BizTalk WCF サービス公開ウィザードや BizTalk Web サービス公開ウィザードを使用して、BizTalk オーケストレーションとスキーマを [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] アダプターで [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスとして公開します。 使用するオーケストレーションとスキーマを SOAP アダプターを使用した Web サービスとして公開するには**BizTalk WCF 公開ウィザード**や**BizTalk Web サービス公開ウィザード**します。  
  
## <a name="prerequisites"></a>前提条件  
 このサンプルの手順を実行するには、使用する環境が次の前提条件を満たしている必要があります。  
  
- アセンブリをビルドし、展開プロセスと、サンプルを実行するコンピューターを実行するコンピューターの両方では、Microsoft Windows Server 2008 SP2 または Windows Server 2008 R2、Microsoft .NET Framework 4、および Microsoft BizTalk Server が必要です。  
  
- アセンブリのビルドと展開プロセスの実行に使用するコンピューターには、Microsoft Visual Studio が必要です。  
  
- サンプルを実行するコンピューターには、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] アダプターと [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 管理ツールが必要です。 これらは、Microsoft BizTalk Server のセットアップ時にインストールするオプションです。  
  
- 管理タスクの実行に使用するコンピューターで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソール内の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーション設定を構成するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーであるユーザー アカウントとして実行する必要があります。 また、アプリケーションの展開、ホスト インスタンスの管理、およびその他の必要なタスクを実行するには、このユーザー アカウントはローカル管理者グループのメンバーである必要もあります。  
  
- 必要とする任意のコンピューターで[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]機能により、1 回限りのセットアップの手順を完了、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サンプル[ http://go.microsoft.com/fwlink/?LinkId=135510](http://go.microsoft.com/fwlink/?LinkId=135510)します。  
  
- サンプルを実行してバインドまたは .msi ファイルを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にインポートするコンピューターで、ホストが信頼されているホストではないことを確認します。信頼されているホストの場合、インポートは失敗します。  
  
- チュートリアルのコードをダウンロードし、コンピューターに展開する必要があります。 このチュートリアルでは全体の一部[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]アダプター チュートリアル パッケージ。 ファイルをダウンロードする**WCFAdapterWalkthroughs.exe**から、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]デベロッパー センター [ http://go.microsoft.com/fwlink/?LinkId=194140](http://go.microsoft.com/fwlink/?LinkId=194140)します。  
  
### <a name="to-deploy-the-sample-biztalk-solution-biztalkapp"></a>サンプル BizTalk ソリューションの BizTalkApp を展開するには  
  
1. 自己解凍形式実行**WCFBasicHttpReceiveAdapter.exe**ファイルを開き、ファイルを**C:\WCFBasicHttpReceiveAdapter**フォルダー。  
  
2. Microsoft Visual studio で開く、 **C:\WCFBasicHttpReceiveAdapter\WCFBasicHttpReceiveAdapter.sln**ファイル。  
  
3. **Microsoft.Samples.BizTalk.WCFBasicHttpReceiveAdapter.BizTalkApp**アセンブリに含まれる、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]オーケストレーション、マップ、および 2 つのスキーマ。 GAC にインストールする必要があり、する必要があります、厳密な名前キー ファイルこれを行うにします。 右クリックし、 **BizTalkApp**プロジェクトをクリックして**プロパティ**します。 **プロパティ**] ページで [**署名**を選択し、**アセンブリに署名**します。 下向きの矢印をクリックして、**厳密な名前キー ファイルを選択して**ドロップダウン リストでは、 をクリックして**\<新規\>**、入力と`keyfile.snk`で、**キー ファイル名**テキスト ボックス。 オフに**キーファイルをパスワードで保護する**、順にクリックします**OK**。  
  
4. ソリューション エクスプ ローラーで右クリックし、 **[biztalkapp]** プロジェクトをクリックして**リビルド**。  
  
   > [!NOTE]
   >  しないで、**ソリューションのビルド**、または構築、 **WCFClient**この時点でアプリケーション。 **WCFClient**この時点で、サンプルでビルドする準備ができています。  
  
5. 展開**BizTalkApp**を開き**DeliveryProcess.odx**を確認します。 オーケストレーションは、WCF-BasicHttp アダプターを使用して HTTP で [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 要求を受け取ります。 その後、変換マップを使用して要求を変更し、再び同じ [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] アダプターを使用して応答を送信します。  
  
   1.  このオーケストレーションは、WCF-BasicHttp アダプターによって公開される論理要求 - 応答ポートを備えています。 このポートは、後の手順で物理ポートにバインドされます。  
  
   2.  最上位ノードを右クリックして**DeliveryProcess.odx**クリックして、デザイナーのウィンドウで**プロパティ**します。 確認、**型修飾子**ポートの種類のプロパティは**パブリック**します。  
  
6. ソリューション エクスプ ローラーで右クリック**BizTalkApp**、 をクリックし、**プロパティ**します。  
  
   1.  BizTalk 管理データベースがローカルでホストされていない場合は、変更、 **Server**プロパティ別のデータベース サーバーを使用する場合。 をクリックして、**展開**タブをクリックし、変更、**サーバー**プロパティをデータベース サーバーをポイントします。  
  
   2.  必ず、**アプリケーション名**プロパティに設定されて**WCFBasicHttpReceiveAdapter**。 これは、BizTalk ソリューションを展開する BizTalk アプリケーションの名前です。  
  
   3.  ソリューション エクスプ ローラーで右クリックして**biztalkapp**、 をクリックし、**デプロイ**します。 ローカルに展開しない場合は、リモート接続を許可するように SQL Server を構成する必要があります。 詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=194141](http://go.microsoft.com/fwlink/?LinkId=194141)します。  
  
### <a name="to-publish-the-sample-orchestration-by-using-the-biztalk-wcf-service-publishing-wizard"></a>BizTalk WCF サービス公開ウィザードを使用して、サンプル オーケストレーションを公開するには  
  
1. この手順では、新しく展開されたオーケストレーション アセンブリを取得し、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスとして公開します。 これを行うには、次のようにクリックします**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、 をクリックし、 **BizTalk WCF サービス公開ウィザード**。  
  
2. **BizTalk WCF サービス公開ウィザードへようこそ**] ページで [**次**します。  
  
3. **WCF サービスの種類** ページで、次の操作の種類を指定する実行[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]を発行するサービスと BizTalk の受信エンドポイント[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]メッセージ、およびクリック **[次へ]**:  
  
   1. 選択、**サービス エンドポイント**オプションは、公開すること、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]アセンブリ内のオーケストレーションからサービス。 選択**Wcf-basichttp**から、**アダプター名 (トランスポートの種類)** ドロップダウン リスト。  
  
   2. 選択、**メタデータ エンドポイントを有効にする**チェック ボックスを[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]受信場所が IIS によってホストされている発行その[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービス メタデータ。 このチェック ボックスの設定を選択すると、 **httpGetEnabled**の属性、 \< **serviceMetadata** \>要素`true`Web.Config でします。このメタデータは、HTTP/GET 要求によって要求された場合に取得されます。 後で、SvcUtil.exe ツールを使用してプロキシ クラスを使用して呼び出すクライアント コードを生成するには、このデータを取得するが、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービス。  
  
   3. 選択、**次のアプリケーションを作成する BizTalk 受信場所**Wcf-basichttp アダプターの場合は、各生成 .svc ファイルに対応する場所と受信ポートを作成するオプション。 BizTalk アプリケーション名を選択**WCFBasicHttpReceiveAdapter**、受信ポートと受信場所が生成 をクリックし、**次**します。  
  
       ウィザードが、関連付けられている受信場所を表すバインド ファイル Binding.XML を作成します。 このファイルは、Web ディレクトリに格納され、後で [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを介して手動でインポートすることができます。  
  
      > [!NOTE]
      >  ここで、展開した BizTalk アプリケーションを選択しない場合は、既定のアプリケーションが選択されます。  
  
4. **WCF サービスの作成**] ページで、[ **BizTalk オーケストレーションの WCF サービスとして発行**、順にクリックします**次**します。 これにより、次の手順で指定するオーケストレーションが [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスとして公開されます。  
  
5. 公開するオーケストレーションを含むアセンブリを選択します。 **BizTalk アセンブリ** ページの 、 **BizTalk アセンブリ ファイル (\*.dll)** テキスト ボックスで、をクリックして**参照**を参照する、 **C:\WCFBasicHttpReceiveAdapter\BizTalkApp\bin\Development**フォルダーをダブルクリックして、 **Microsoft.Samples.BizTalk.WCFBasicHttpReceiveAdapter.BizTalkApp**サンプルを含むアセンブリオーケストレーションを公開する をクリックして**オープン**、順にクリックします**次**します。  
  
6. **オーケストレーションおよびポート**ことを確認します ページで、**ポート: DeliveryRequestPort**ノード ページで、選択されている場合をクリックして**次**します。 このノードを選択すると、対応する上位レベルのノードがも選択されていることを意味します。 このポートは、WCF-BasicHttp アダプターをホストする要求 - 応答の受信場所で公開されます。  
  
7. **WCF サービスのプロパティ**ページで、**ターゲット**の名前空間、 **WCF サービス**テキスト ボックスに、この公開された URI を入力[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービスを使用してクリックして**次**します。 このチュートリアルでは、既定の URI のままに"**<http://tempuri.org/>"** のターゲット名前空間、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービスのテキスト ボックス。  
  
8. **WCF サービスの場所** ページで、次の場所を指定する操作を実行、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービスを作成、およびクリックして**次**:  
  
   1. **場所**テキスト ボックスに「Web ディレクトリ名、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービスが実行される、または [] をクリックして**参照**Web ディレクトリを選択します。 このチュートリアルでは、アセンブリ名は、仮想ディレクトリと同じであるため、既定の場所のまま (**<http://localhost/Microsoft.Samples.BizTalk.WCFBasicHttpReceiveAdapter.BizTalkApp>**) で、**場所**テキスト ボックス。  
  
   2. 選択、 **WCF サービスへの匿名アクセスを許可する**オプションをクリックして**次**。 このオプションを選択すると、作成された仮想ディレクトリへの匿名アクセスが許可されます。 このチュートリアルでは、認証なしでトランスポート セキュリティ モードを使用するため、このオプションは、このウィザードで作成する Web アプリケーションの匿名認証を許可するのには選択する必要があります。  
  
9. **WCF サービスの概要**] ページで [**作成**を作成する、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービス。 この手順では、指定した Web ディレクトリを通じて使用できる、指定したオーケストレーション用の受信ポートを作成します。  
  
10. **BizTalk WCF サービス公開ウィザードの完了**] ページで [**完了**します。  
  
### <a name="to-enable-the-sample-biztalk-application"></a>サンプル BizTalk アプリケーションを有効にするには  
  
1. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[**アプリケーション**、展開**WCFBasicHttpReceiveAdapter**、展開**オーケストレーション**、を右クリックして **[Deliveryprocess]** オーケストレーション、] をクリックして**プロパティ**、し、バインド情報を次のように構成します。  
  
   1. **オーケストレーションのプロパティ**ダイアログ ボックスで、をクリックして**バインド**、し、設定**ホスト**に**BizTalkServerApplication**。  
  
   2. **オーケストレーションのプロパティ**] ダイアログ ボックスで、[受信ポートを**DeliveryRequestPort**にバインドします。 このチュートリアルでは、選択、受信はポートを BizTalk[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービス公開ウィザードが前の手順で作成され、順にクリックします**OK**します。  
  
3. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックして**WCFBasicHttpReceiveAdapter**、 をクリックして**開始**、順にクリックします**開始**で、**開始アプリケーション** ダイアログ ボックス。  
  
### <a name="to-configure-the-web-application-hosting-the-published-wcf-service"></a>公開された WCF サービスをホストする Web アプリケーションを構成するには  
  
1. クリックして**開始**、 をポイント**管理者ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) 7.0 マネージャー**します。  
  
2. IIS マネージャーで、展開**サイト**、展開**既定の Web サイト**、Web アプリケーションを展開し**Microsoft.Samples.BizTalk.WCFBasicHttpReceiveAdapter.BizTalkApp**を**BizTalk WCF サービス公開ウィザード**を作成します。  
  
3. このサービスが実行されるアプリケーション プールを作成します。 右クリック**アプリケーション プール**、 をクリックして**アプリケーション プールの追加**、アプリケーション プールの名前を入力し、 **OK**します。  
  
4. 展開**アプリケーション プール**作成したアプリケーション プールを右クリックし、**詳細設定**します。 **プロセス モデル**セクションで、これにアクセスするアカウントを入力、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースで、 **Identity**フィールド。  
  
5. IIS マネージャーで、**コンテンツ ビュー**します。  右側のウィンドウで右クリックし、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービスの .svc ファイルを**BizTalk WCF サービス公開ウィザード**作成され、クリックして**参照**します。 これにより、Internet Explorer が開き、実行対象の [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスが正しく作成されたことを示すページが表示されます。 このページには、完全な WSDL アドレスも含まれます。サービス メタデータ ツール (svcutil.exe) で、このアドレスをコピーして使用することで、サービスのクライアント アプリケーションを作成するために使用できるプロキシ コードおよび構成ファイルを取得できます。  
  
6. 前の手順で Internet Explorer が表示されるページで、完全な WSDL アドレスを使用して SvcUtil.exe コマンドラインをクリップボードにコピーします。  
  
### <a name="to-create-the-proxy-class-for-the-sample-wcf-client-application-wcfclient"></a>サンプル クライアント アプリケーション WCFClient のプロキシ クラスを作成するには  
  
1. [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] クライアントのサンプル アプリケーションが [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスを呼び出すことができるようにプロキシ クラスを作成します。 プロキシは必ずしも必要ではありませんが、手動によるコードの記述は非常に複雑なので、プロキシを作成することをお勧めします。 開く、 **Visual Studio コマンド プロンプト**に移動し、 **C:\WCFBasicHttpReceiveAdapter\WCFClient**プロキシ クラスおよびアプリケーション構成ファイルを配置するフォルダー。  
  
2. 貼り付け、 **svcutil.exe**前の手順でコピーして、ヒットした完全な WSDL アドレスを使用してコマンドライン **」と入力**プロキシ クラスおよびアプリケーション構成ファイルを作成します。 このコマンドラインを作成します**BizTalkServiceInstance.cs**プロキシ クラスと**output.config**アプリケーション構成ファイル。  
  
3. ソリューション エクスプ ローラーで、Visual Studio で右クリック**WCFClient**、 をポイント**追加**、 をクリックし、**既存項目の**します。  
  
4. **既存項目の追加** ダイアログ ボックスで、参照、 **WCFClient**フォルダーで、**すべてのファイル (\*.\*)** で、**ファイルの種類**ドロップダウン リストで、 **BizTalkServiceInstance.cs**と**output.config**ファイル、および順にクリックします**追加**します。  
  
5. **WCFClient**プロジェクトで、展開**参照**、いることを確認し、 **WCFClient**プロジェクトには、 **System.ServiceModel**としてその参照の 1 つ。  
  
6. 展開、 **WCFClient**プロジェクトを右クリックして**output.config**、 をクリックして**の名前を変更**、し、入力**App.config**の新しい名前。  
  
7. ダブルクリック**Program.cs** 、公開されたを呼び出す方法を確認する[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービスによって生成されたプロキシ クラスを使用して**Svcutil.exe**します。 呼び出しをインスタンス化および呼び出す、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]のコーディングを使用してわかりやすくするためにローカルな呼び出しをサービスが表示されて、 **Microsoft_Samples_BizTalk_WCFBasicHttpReceiveAdapter_BizTalkApp_DeliveryProcess_DeliveryRequestPortClient**クラス。 リモート [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスの呼び出しを行うために必要な追加コードはありません。  
  
8. Visual Studio での**デバッグ** メニューのをクリックして**デバッグなしで開始**して WCFClient を実行します。 クライアント コードは、DeliveryItem メッセージを作成し、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスの呼び出しを行って、Address、ProductID、および Amount を渡します。  
  
   ```  
   DeliveryItem deliveryRequestItem = new DeliveryItem();  
   deliveryRequestItem.Address = "One Microsoft Way";  
   deliveryRequestItem.ProductID = "00A120c";  
   deliveryRequestItem.Amount = "300";  
   DeliveryRequestPortClient deliveryProcessClient = new DeliveryRequestPortClient("BasicHttpBinding_ITwoWayAsync");  
   DeliveryItem1 deliveryConfirmation = deliveryProcessClient.Submit(deliveryRequestItem);  
   ```  
  
    クライアントが、公開された [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスから応答メッセージを正常に受信すると、配信確認番号 (ProductID と Address を連結したもの) が応答メッセージに表示されます。  
  
    **DeliveryRequestItem で呼び出される送信操作**  
  
    **返信される配信確認番号: 00A120c300One Microsoft Way**  
  
    **続行する任意のキーを押してください.**  
  
## <a name="see-also"></a>参照  
 [BizTalk WCF サービス公開ウィザードを使用してオーケストレーションを WCF サービスとして公開する方法](../core/publish-orchestrations-as-wcf-services--biztalk-wcf-service-publishing-wizard.md)