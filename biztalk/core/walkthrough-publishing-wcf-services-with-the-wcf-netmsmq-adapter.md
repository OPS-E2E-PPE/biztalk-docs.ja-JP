---
title: "チュートリアル: Wcf-netmsmq アダプタを使用して WCF サービスを発行する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e623b6dc-32e5-467c-bb7d-68b7a75723c1
caps.latest.revision: "46"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7c80859e83d915d835aa99b0456ca763ed267f4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-publishing-wcf-services-with-the-wcf-netmsmq-adapter"></a>チュートリアル: Wcf-netmsmq アダプタを使用して WCF サービスの発行
  
> [!NOTE]
>  アダプターの詳細については、次を参照してください。 [BizTalk Server のアダプター](../core/adapters-in-biztalk-server.md)です。  
  
## <a name="introduction"></a>概要
  
 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] では、オーケストレーションを [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] サービスとして公開できます。 BizTalk の受信場所を通じて、オーケストレーションにより [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] エンドポイントを公開し、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] クライアントから呼び出せるようにします。 **BizTalk WCF サービス公開ウィザード**オーケストレーション、受信場所として公開する簡単な方法を提供します。  
  
 Wcf-netmsmq アダプターを使用して、 **NetMsmqBinding**基になるトランスポートとして Microsoft メッセージ キュー (MSMQ とも呼ばれます) を使用するためのサポートを提供するバインディング。 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスのクライアントは、WCF-NetMSMQ アダプターを使用するように構成された受信場所を使用して、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] メッセージを MSMQ キューに送信します。 アダプターは MSMQ キューから [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] メッセージを取得し、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 形式に変換して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] メッセージ ボックス データベースに書き込みます。  
  
 このチュートリアルでは、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] クライアント コンソール アプリケーションが WCF-NetMsmq アダプターを使用して、.NET コンソール アプリケーションでホストされている [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスと MSMQ メッセージ キューを介して通信する方法を示します。 BizTalk WCF サービス公開ウィザードで受信場所にメタデータを公開する方法について説明します。 公開メタデータをサポートするように Web アプリケーションを構成する方法についても説明します。  
  
 このチュートリアルを完了すると、次のタスクを実行できるようになります。  
  
-   内から[!INCLUDE[vs2010](../includes/vs2010-md.md)]を使用して、**展開**のローカル インスタンスに BizTalk アセンブリを展開するコマンドを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。 これにより、アセンブリが含まれた BizTalk アプリケーションが作成されます。 BizTalk アセンブリには、オーケストレーション、パイプライン、スキーマ、マップなど、BizTalk ソリューションで使用するリソース情報が含まれます。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールから、公開した [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスをホストするように WCF-NetMsmq 受信場所を構成する。  
  
-   **BizTalk WCF サービス公開ウィザード**、既存の受信場所用にメタデータを公開する Web アプリケーションを作成します。 このメタデータは、メッセージを受信場所に送信するクライアントによって使用されます。  
  
## <a name="prerequisites"></a>前提条件  
 このサンプルの手順を実行するには、使用する環境が次の前提条件を満たしている必要があります。  
  
-   サンプルを実行するコンピューターと、アセンブリをビルドおよび展開プロセスを実行するコンピューターの両方の必要な Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]、Microsoft [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)]、および Microsoft[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]です。  
  
-   アセンブリのビルドと展開プロセスの実行に使用するコンピューターには、Microsoft [!INCLUDE[vs2010](../includes/vs2010-md.md)] が必要です。  
  
-   サンプルを実行するコンピューターには、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] アダプターと [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 管理ツールが必要です。 これらは、Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] のセットアップ時にインストールするオプションです。  
  
-   管理タスクの実行に使用するコンピューターで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソール内の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーション設定を構成するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーであるユーザー アカウントとして実行する必要があります。 また、アプリケーションの展開、ホスト インスタンスの管理、およびその他の必要なタスクを実行するには、このユーザー アカウントはローカル管理者グループのメンバーである必要もあります。  
  
-   必要とする任意のコンピューターで[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]、機能の 1 回限りのセットアップの手順を完了、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]ではサンプル[http://go.microsoft.com/fwlink/?LinkId=135510](http://go.microsoft.com/fwlink/?LinkId=135510)です。  
  
-   サンプルを実行してバインドまたは .msi ファイルを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にインポートするコンピューターで、ホストが信頼されているホストではないことを確認します。信頼されているホストの場合、インポートは失敗します。  
  
-   チュートリアルのコードをダウンロードし、コンピューターに展開する必要があります。 このチュートリアルでは、全体の一部[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]アダプター チュートリアル パッケージです。 ファイルをダウンロードする**WCFAdapterWalkthroughs.exe**から、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]デベロッパー センター [http://go.microsoft.com/fwlink/?LinkId=194140](http://go.microsoft.com/fwlink/?LinkId=194140)です。  
  
## <a name="build-and-deploy-the-biztalk-solution-biztalkapp"></a>ビルドし、BizTalk ソリューションの BizTalkApp を展開  
  
1.  抽出する WCFNetMsmqAdapterPublishing.exe **C:\WCFNetMsmqAdapterPublishing**です。  
  
2.  [!INCLUDE[vs2010](../includes/vs2010-md.md)]を開き、 **WCFNetMsmqAdapterPublishing.sln**ファイル。  
  
3.  ソリューション エクスプ ローラーで、 **BizTalkApp**、開き、 **OrderProcess.odx**を確認します。 サンプル オーケストレーションは発注要求メッセージを受信し、注文応答メッセージを返します。  
  
4.  **BizTalkApp**アセンブリを GAC にインストールする必要があります、厳密な名前キー ファイルを展開プロセスを完了する必要があります。 右クリックし、 **BizTalkApp**プロジェクトをクリックして**プロパティ**です。 **プロパティ**] ページで [**署名**を選択し、**アセンブリに署名**です。 下向きの矢印をクリックして、**厳密な名前キー ファイルを選択して**ドロップダウン リストをクリックして**\<新規 >**を入力し、`keyfile.snk`で、**キー ファイルの名前** テキスト ボックス。 オフに**キーファイルをパスワードで保護する**、順にクリック**OK**です。  
  
5.  クリックして、**展開**タブをクリックし、変更、**サーバー**プロパティだけでなく、BizTalk 管理データベースを別のデータベース サーバーを使用する場合**LOCALHOST**です。  確認**BizTalk アプリケーション**に値が設定されている**WCFNetMsmqAdapterPublishing**です。 確認**グローバル アセンブリ キャッシュにインストール**に設定されている**True**です。  
  
6.  ソリューション エクスプ ローラーで右クリックし、 **BizTalkApp**プロジェクトし、をクリックして**リビルド**です。  
  
7.  ソリューション エクスプ ローラーで右クリック**BizTalkApp**、クリックして**展開**です。  
  
## <a name="configure-the-application"></a>アプリケーションの構成  
  
1.  次の手順で、Microsoft メッセージ キュー (MSMQ) コンポーネントがコンピューターにインストールされていることを確認します。  
  
    1.  をクリックして**開始**を右クリックして**コンピューター**、順にクリック**管理**を開くには**サーバー マネージャー**です。  
  
    2.  展開して、**機能**ノード。  場合**メッセージ キュー**がインストールされていないを右クリックして**機能**を選択し、**機能の追加**です。 確認**メッセージ キュー**、をクリックして**[次へ]**、順にクリック**インストール**そのシステムで MSMQ をインストールします。  
  
2.  次の手順で、メッセージ キュー サービスがコンピューターで開始され、WCF-NetMsmq アダプターで使用できることを確認します。  
  
    1.  をクリックして**開始**、をポイント**管理ツール**、順にクリック**Services**。  
  
    2.  **Services**、ことを確認して、**ステータス**の**メッセージ キュー**サービスは**Started**です。 サービスが開始されていない場合は右クリック**メッセージ キュー**、クリックして**開始**です。  
  
3.  WCF-NetMsmq がクライアントからの受信 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] メッセージを取得する元となる、受信場所が使用するターゲット キューを作成します。  
  
    1.  をクリックして**開始**、をポイント**管理ツール**、順にクリック**コンピューターの管理**です。  
  
    2.  **コンピューターの管理**、展開**サービスとアプリケーション**、展開**メッセージ キュー**を右クリックして**専用キュー**、をポイント**新規**、クリックして**プライベート キュー**です。  
  
    3.  **新しい専用キュー**  ダイアログ ボックスで、「`WCFNetMsmqAdapterPublishing`で、**キュー名**テキスト ボックスで、、**トランザクション**チェック ボックスをクリックしてして**OK**.  
  
4.  次の手順に従って、サンプル アプリケーションの WCF-NetMsmq 受信場所を作成します。  
  
    1.  をクリックして**開始**、をポイント**すべてのプログラム**、をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
    2.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **BizTalk グループ**、展開**アプリケーション**、展開**WCFNetMsmqAdapterPublishing**を右クリックして**受信ポート**、指す**新規**、順にクリック**一方向の受信ポート。**  
  
    3.  **受信ポートのプロパティ** ダイアログ ボックスで、**名前**テキスト ボックスで、「 `WCFNetMsmqAdapterPublishing.ReceivePurchaseOrder`、クリックしてして**ok**です。  
  
    4.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックして**[wcfnetmsmqadapterpublishing.receivepurchaseorder]**、をポイント**新規**、クリックして**受信場所**.  
  
    5.  **受信場所のプロパティ** ダイアログ ボックスで、**名前**テキスト ボックスで、「`WCFNetMsmqAdapterPublishing.ReceivePurchaseOrder.NetMsmq`です。  
  
    6.  **受信場所のプロパティ**] ダイアログ ボックスで、**トランスポート**横**型**[ **Wcf-netmsmq**から、クリックしてドロップダウン リスト、**構成**です。  
  
    7.  **Wcf-netmsmq トランスポートのプロパティ** ダイアログ ボックスで、**全般** タブの 、**アドレス (URI)**テキスト ボックスで、「`net.msmq://localhost/private/WCFNetMsmqAdapterPublishing`です。  
  
    8.  **Wcf-netmsmq トランスポートのプロパティ**ダイアログ ボックスの**バインド** タブで、ことを確認して、**トランザクション** チェック ボックスをオンします。  
  
        > [!NOTE]
        >  対象のキューをトランザクション キューとして作成したため、このチェック ボックスをオンにする必要があります。 このチェック ボックスがオンになっていない場合、受信場所のトランザクション要件と基になる MSMQ キューのトランザクション要件との間に不一致が生じるため、受信場所が有効になりません。  
  
    9. **Wcf-netmsmq トランスポートのプロパティ** ダイアログ ボックスで、**セキュリティ** タブで **なし**から、**セキュリティ モード**ドロップダウン リスト.  
  
        > [!NOTE]
        >  このチュートリアルでは、MSMQ は、[!INCLUDE[btsAD](../includes/btsad-md.md)] 統合を無効にしてコンピューターにインストールされていると想定しています。 既定値は**WindowsDomain**の**MSMQ 認証モード**プロパティは使用可能な場合に[!INCLUDE[btsAD](../includes/btsad-md.md)]統合が有効にします。  
  
    10. **受信場所のプロパティ**ダイアログ ボックスで、をクリックして**OK**です。  
  
5.  サンプル アプリケーションの FILE 送信ポートを作成します。 このポートは、サービスの基となるオーケストレーションの注文書からの応答をルーティングします。  
  
    1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **WCFNetMsmqAdapterPublishing**を右クリックして**送信ポート**、をポイント**新規**をクリックして**静的な一方向送信ポート**です。  
  
    2.  **送信ポートのプロパティ** ダイアログ ボックスで、**名前**テキスト ボックスで、「`WCFNetMsmqAdapterPublishing.SendPurchaseOrder.File`です。  
  
    3.  **送信ポートのプロパティ**] ダイアログ ボックスで、**トランスポート**セクションの横に**型**[**ファイル**ドロップダウン リストから、し、をクリックして**構成**です。  
  
    4.  **FILE トランスポートのプロパティ**ダイアログ ボックスの**全般**] タブの [、**コピー先フォルダー**テキスト ボックスで、「 `C:\WCFNetMsmqAdapterPublishing\Out`、順にクリック**ok**.  
  
    5.  **送信ポートのプロパティ**ダイアログ ボックスで、をクリックして**OK**です。  
  
6.  次の手順で、サンプル アプリケーションのホスト名とバインドを指定します。  
  
    1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **WCFNetMsmqAdapterPublishing**、展開**オーケストレーション**サンプル オーケストレーションを右クリックしをクリックして**のプロパティ**をクリックして**バインド**、設定と**ホスト**に**BizTalkServerApplication**または別の適切なホストです。  
  
    2.  **オーケストレーションのプロパティ**ダイアログ ボックスで、 **WCFNetMsmqAdapterPublishing.ReceivePurchaseOrder**から、**受信ポート**のドロップダウンリスト**PurchaseOrderRequestPort**です。  
  
    3.  **オーケストレーションのプロパティ**ダイアログ ボックスで、 **WCFNetMsmqAdapterPublishing.SendPurchaseOrder.File**から、**送信ポート/送信ポート グループ**ドロップダウン リスト**PurchaseOrderResponsePort**です。  
  
    4.  **オーケストレーションのプロパティ**ダイアログ ボックスで、をクリックして**OK**構成を保存します。  
  
## <a name="publish-the-metadata-for-the-wcf-netmsmq-receive-location"></a>Wcf-netmsmq 受信場所のメタデータを公開します。  
  
1.  をクリックして**開始**、をポイント**すべてのプログラム**、をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk WCF サービス公開ウィザード**です。  
  
2.  **BizTalk WCF サービス公開ウィザードへようこそ** ページで、をクリックして**次**です。  
  
3.  **WCF サービスの種類** ページで、、**メタデータのみのエンドポイント (MEX)** WCFNetMsmq のメタデータを公開する チェック ボックスの受信場所。 選択**WCFNetMsmqAdapterPublishing.ReceivePurchaseOrder.NetMsmq**から、**受信場所のメタデータを公開**クリックしてドロップダウン リスト、**次**です。  
  
4.  **WCF サービスの作成**] ページで、[ **BizTalk オーケストレーションの WCF サービスとして発行**、クリックして**[次へ]**です。  
  
5.  **BizTalk アセンブリ**] ページの [、 **BizTalk アセンブリ ファイル (\*.dll)**テキスト ボックスで、をクリックして**参照**を参照する、 **C:\WCFNetMsmqAdapterPublishing\BizTalkApp\bin\Development**フォルダーで、をクリックし、サンプル オーケストレーションを含むアセンブリをダブルクリックして**次**です。  
  
6.  **オーケストレーションとポート** ページで、ことを確認して、**ポート: PurchaseOrderRequestPort**ノードがページで、選択されているしをクリックして**次**です。  
  
     受信ポートの MEX が公開され、メッセージを受信場所に送信するためにクライアントによって使用されます。  
  
7.  **WCF サービスのプロパティ**] ページの [、 **WCF サービスのターゲットの名前空間**テキスト ボックスに入力する、この公開された URI[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービスが使用すると、クリックして**次へ**. このチュートリアルでは、既定の URI を選択したままに`http://tempuri.org/`です。  
  
8.  **WCF サービスの場所** ページで、次の場所を指定する操作を実行、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービスを作成して、をクリックする**次**:  
  
    1.  **場所**テキスト ボックスで、「Web ディレクトリ名、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービスが実行されるかをクリックして**参照**Web ディレクトリを選択します。 このチュートリアルでは、既定の場所を選択したままに (http://localhost/*\<BizTalk アセンブリ名 >*) で、**場所**テキスト ボックス。  
  
    2.  選択、 **WCF サービスへの匿名アクセスを許可する**オプション。 : このオプションでは、作成した仮想ディレクトリに匿名アクセスを追加します。 このウィザードで作成される Web アプリケーションに匿名認証を許可するには、このオプションをオンにする必要があります。  
  
9. **WCF サービスの概要**] ページで [**作成**を作成する、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービス。  
  
10. **BizTalk WCF サービス公開ウィザードの完了**] ページで [**完了**です。  
  
## <a name="configure-the-web-application-hosting-the-published-metadata-service"></a>公開したメタデータ サービスをホストする Web アプリケーションを構成します。  
  
1.  コマンド プロンプトを開きに移動、 **C:\inetpub\wwwroot\Microsoft.Samples.BizTalk.WCF.NetMsmqPublishing.BizTalkApp**フォルダー場所、 **BizTalk WCF サービス公開ウィザード**作成、 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービス。 開く、 **Web.config**ファイルのメモ帳を使用します。  
  
2.  メモ帳で、内部の次の行を追加、  **\<system.web >**要素。  
  
    ```  
    <trust level="Full" originUrl="" />  
    ```  
  
    > [!NOTE]
    >  この設定は省略可能です。 この設定により、公開された [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスをホストする ASP.NET アプリケーションに対して、オペレーティング システムのセキュリティの対象であるすべてのリソースへのアクセス権限が付与されます。  
  
3.  次の手順に従い、公開された [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスを Internet Explorer を使用してテストします。  
  
    1.  をクリックして**開始**、をポイント**管理者ツール**、順にクリック**インターネット インフォメーション サービス (IIS) マネージャー**です。  
  
    2.  IIS マネージャーでは、BizTalk データベースの正しいアクセス許可を持つこのサービスが実行されるアプリケーション プールを作成します。 右クリック**アプリケーション プール**、をクリックして**アプリケーション プールの追加**アプリケーション プールの名前を入力し、クリックして**OK**です。  
  
    3.  展開**アプリケーション プール**作成したアプリケーション プールを右クリックし、**詳細設定**です。 **プロセス モデル**セクションで、アクセスを許可されているアカウントを入力して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースで、 **Identity**フィールドです。  
  
    4.  展開**Web サイト**、展開**既定の Web サイト**、し、BizTalk WCF サービス公開ウィザードを作成した Web アプリケーションを展開します。  
  
    5.  IIS マネージャーで、中央のウィンドウでをクリックして**コンテンツ ビュー**アプリケーションのファイルを表示します。  
  
    6.  右クリックし、 **Microsoft_Samples_BizTalk_WCF_NetMsmqPublishing_BizTalkApp_OrderProcess_PurchaseOrderRequestPort.svc**サービス ファイルを**BizTalk WCF サービス公開ウィザード**作成され、をクリックして**参照**です。 表示する Internet Explorer が開き、 **BizTalkServerInstance サービス**ことを示すページのインスタンス、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービスが実行されています。 このページには、完全な WSDL アドレスも含まれます。サービス メタデータ ツール (svcutil.exe) を使用して、または [!INCLUDE[vs2010](../includes/vs2010-md.md)] 内からこのアドレスをコピーして使用することで、サービスのクライアント アプリケーションを作成するために使用できるプロキシ コードおよび構成ファイルを取得できます。  
  
    7.  完全な WSDL アドレスを使用してコマンドラインをクリップボードにコピー **BizTalkServerInstance サービス**ページが前の手順で Internet Explorer が示されます。  
  
         **svcutil.exe http://localhost/Microsoft.Samples.BizTalk.WCF.NetMsmqPublishing.BizTalkApp/Microsoft_Samples_BizTalk_WCF_NetMsmqPublishing_BizTalkApp_OrderProcess_PurchaseOrderRequestPort.svc?wsdl**  
  
## <a name="build-the-client-application"></a>クライアント アプリケーションをビルドします。  
  
1.  開く、[!INCLUDE[vs2010](../includes/vs2010-md.md)]コマンド プロンプトを管理者に移動して、 **C:\WCFNetMsmqAdapterPublishing\WCFClient**フォルダーです。 このフォルダーに、プロキシ クラスおよびアプリケーション構成ファイルが保存されます。  
  
2.  前の手順でコピーした、完全な WSDL アドレスを含む svcutil.exe コマンド ラインを貼り付け、Enter キーを押します。 これは、クラスを作成、プロキシ、 **BizTalkServiceInstance.cs**、およびアプリケーション構成ファイル、 **output.config**です。コマンド プロンプト ウィンドウは、最後のセクションで使用するため開いたままにします。  
  
3.  [!INCLUDE[vs2010](../includes/vs2010-md.md)]、ソリューション エクスプ ローラーで右クリック**WCFClient**、をポイント**追加**、順にクリック**既存項目の**します。  
  
4.  **既存項目の追加**ダイアログ ボックスを参照、 **WCFClient**フォルダーを選択**すべてのファイル (\*.\*)**で、**ファイルの種類**ドロップダウン リストで、 **BizTalkServiceInstance.cs**と**output.config**ファイル、および  をクリックして**追加**です。  
  
5.  展開**WCFClient**を右クリックして**output.config**、 をクリックして**の名前を変更**、し、入力`App.config`新しい名前として。  
  
6.  ダブルクリックして**Program.cs**を呼び出して、公開された方法を確認する[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]svcutil.exe によって生成されたプロキシ クラスを使用してサービスを提供します。  
  
7.  展開**参照**、いることを確認し、 **WCFClient**プロジェクトが**System.ServiceModel.dll**参照します。  
  
8.  右クリックし、 **WCFClient**プロジェクトし、選択**ビルド**です。 [!INCLUDE[vs2010](../includes/vs2010-md.md)] を開いたままにして、次のセクションに進みます。  
  
## <a name="test-the-sample-solution-with-the-wcf-netmsmq-adapter"></a>Wcf-netmsmq アダプターを使用するサンプル ソリューションをテストします。  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、 **[wcfnetmsmqadapterpublishing]**アプリケーション、およびクリック**開始**です。 **開始**ダイアログ ボックスで、をクリックして**開始**です。  
  
2.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、**プラットフォームの設定**、展開**ホスト インスタンス**を右クリックして**BizTalkServerApplication**または別クリックして、ホスト インスタンスの適切な**再起動**です。 このステップは必須ではありませんが、この時点でサンプルが正しく動作することを確認しておくことをお勧めします。  
  
3.  [!INCLUDE[vs2010](../includes/vs2010-md.md)]の**デバッグ** メニューのをクリックして**デバッグなしで開始**WCFClient アプリケーションを実行します。 この操作で、サンプル メッセージが WCF-NetMsmq 受信場所に送信されます。 メッセージが送信されたことを示す次の出力メッセージが表示されます。  
  
     **Wcf-netmsmq 送信操作の呼び出しの受信場所**  
  
     **任意のキーを押して WCF クライアント アプリケーションを閉じる**  
  
4.  任意のキーを押して、WCFClient アプリケーションを閉じてください。  
  
5.  [!INCLUDE[vs2010](../includes/vs2010-md.md)]コマンド プロンプトに移動して、 **C:\WCFNetMsmqAdapterPublishing\Out**フォルダー、し確認応答メッセージを返信 WCFClient アプリケーションが存在します。  
  
6.  Internet Explorer とビューで開く {GUID} .xml ファイルをダブルクリックして、 **OrderID**値は、サービスによって処理されます。  
  
## <a name="see-also"></a>参照  
 [構成、Wcf-netmsmq 受信場所](../core/how-to-configure-a-wcf-netmsmq-receive-location.md)   
 [WCF アダプターのチュートリアル](../core/wcf-adapter-walkthroughs.md)   
 [受信アダプターの wcf サービス メタデータの公開](../core/publishing-service-metadata-for-the-wcf-receive-adapters.md)