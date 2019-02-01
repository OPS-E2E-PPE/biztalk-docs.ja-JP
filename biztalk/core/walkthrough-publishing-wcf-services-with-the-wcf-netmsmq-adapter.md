---
title: 'チュートリアル: Wcf-netmsmq アダプターを使用した WCF サービスの発行 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e623b6dc-32e5-467c-bb7d-68b7a75723c1
caps.latest.revision: 46
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45f8b47b60663348c48ca398cedca464b3a2dd6b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995835"
---
# <a name="walkthrough-publishing-wcf-services-with-the-wcf-netmsmq-adapter"></a>チュートリアル: Wcf-netmsmq アダプターを使用した WCF サービスの発行
  
> [!NOTE]
>  アダプターの詳細については、次を参照してください。 [BizTalk Server のアダプター](../core/adapters-in-biztalk-server.md)します。  
  
## <a name="introduction"></a>概要
  
 BizTalk server のオーケストレーションとしてパブリッシュできます、[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)]サービス。 BizTalk の受信場所を通じて、オーケストレーションにより [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] エンドポイントを公開し、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] クライアントから呼び出せるようにします。 **BizTalk WCF サービス公開ウィザード**オーケストレーション、受信場所として公開する簡単な方法を提供します。  
  
 Wcf-netmsmq アダプターを使用して、 **NetMsmqBinding**基になるトランスポートとして Microsoft メッセージ キュー (MSMQ とも呼ばれます) を使用するためのサポートを提供するバインディング。 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスのクライアントは、WCF-NetMSMQ アダプターを使用するように構成された受信場所を使用して、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] メッセージを MSMQ キューに送信します。 アダプターは MSMQ キューから [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] メッセージを取得し、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 形式に変換して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] メッセージ ボックス データベースに書き込みます。  
  
 このチュートリアルでは、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] クライアント コンソール アプリケーションが WCF-NetMsmq アダプターを使用して、.NET コンソール アプリケーションでホストされている [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスと MSMQ メッセージ キューを介して通信する方法を示します。 BizTalk WCF サービス公開ウィザードで受信場所にメタデータを公開する方法について説明します。 公開メタデータをサポートするように Web アプリケーションを構成する方法についても説明します。  
  
 このチュートリアルを完了すると、次のタスクを実行できるようになります。  
  
- Visual Studio 内で使用して、**デプロイ**コマンドのローカル インスタンスに BizTalk アセンブリを展開する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 これにより、アセンブリが含まれた BizTalk アプリケーションが作成されます。 BizTalk アセンブリには、オーケストレーション、パイプライン、スキーマ、マップなど、BizTalk ソリューションで使用するリソース情報が含まれます。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールから、公開した [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスをホストするように WCF-NetMsmq 受信場所を構成する。  
  
- **BizTalk WCF サービス公開ウィザード**、既存の受信場所のメタデータを公開する Web アプリケーションを作成します。 このメタデータは、メッセージを受信場所に送信するクライアントによって使用されます。  
  
## <a name="prerequisites"></a>必須コンポーネント  
 このサンプルの手順を実行するには、使用する環境が次の前提条件を満たしている必要があります。  
  
- アセンブリをビルドし、展開プロセスと、サンプルを実行するコンピューターを実行するコンピューターの両方では、Microsoft Windows Server、.NET Framework、および BizTalk Server が必要です。  
  
- アセンブリのビルドと展開プロセスの実行に使用するコンピューターには、Microsoft Visual Studio が必要です。  
  
- サンプルを実行するコンピューターには、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] アダプターと [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 管理ツールが必要です。 これらは、Microsoft BizTalk Server のセットアップ時にインストールするオプションです。  
  
- 管理タスクの実行に使用するコンピューターで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソール内の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーション設定を構成するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーであるユーザー アカウントとして実行する必要があります。 また、アプリケーションの展開、ホスト インスタンスの管理、およびその他の必要なタスクを実行するには、このユーザー アカウントはローカル管理者グループのメンバーである必要もあります。  
  
- 必要とする任意のコンピューターで[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]機能により、1 回限りのセットアップの手順を完了、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サンプル[ http://go.microsoft.com/fwlink/?LinkId=135510](http://go.microsoft.com/fwlink/?LinkId=135510)します。  
  
- サンプルを実行してバインドまたは .msi ファイルを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にインポートするコンピューターで、ホストが信頼されているホストではないことを確認します。信頼されているホストの場合、インポートは失敗します。  
  
- チュートリアルのコードをダウンロードし、コンピューターに展開する必要があります。 このチュートリアルでは全体の一部[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]アダプター チュートリアル パッケージ。 ファイルをダウンロードする**WCFAdapterWalkthroughs.exe**から、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]デベロッパー センター [ http://go.microsoft.com/fwlink/?LinkId=194140](http://go.microsoft.com/fwlink/?LinkId=194140)します。  
  
## <a name="build-and-deploy-the-biztalk-solution-biztalkapp"></a>ビルドし、BizTalk ソリューションの BizTalkApp を展開します。  
  
1.  抽出する WCFNetMsmqAdapterPublishing.exe **C:\WCFNetMsmqAdapterPublishing**します。  
  
2.  Visual Studio で開く、 **WCFNetMsmqAdapterPublishing.sln**ファイル。  
  
3.  ソリューション エクスプ ローラーで、 **BizTalkApp**を開き**OrderProcess.odx**を確認します。 サンプル オーケストレーションは注文要求メッセージを受信し、注文応答メッセージを返します。  
  
4.  **BizTalkApp**アセンブリを GAC にインストールする必要があります、展開プロセスを完了する厳密な名前キー ファイルは必要があります。 右クリックし、 **BizTalkApp**プロジェクトをクリックして**プロパティ**します。 **プロパティ**] ページで [**署名**を選択し、**アセンブリに署名**します。 下向きの矢印をクリックして、**厳密な名前キー ファイルを選択して**ドロップダウン リストでは、 をクリックして**\<新規\>** 入力と`keyfile.snk`で、**キー ファイル名**テキスト ボックス。 オフに**キーファイルをパスワードで保護する**、順にクリックします**OK**。  
  
5.  をクリックして、**展開**タブをクリックし、変更、 **Server**プロパティだけでなく、BizTalk 管理データベースを別のデータベース サーバーを使用する場合**LOCALHOST**します。  確認**BizTalk アプリケーション**値に設定されて**WCFNetMsmqAdapterPublishing**します。 確認**グローバル アセンブリ キャッシュにインストール**に設定されている**True**します。  
  
6.  ソリューション エクスプ ローラーで右クリックし、 **[biztalkapp]** プロジェクトをクリックして**リビルド**します。  
  
7.  ソリューション エクスプ ローラーで右クリックして**biztalkapp**、 をクリックし、**デプロイ**します。  
  
## <a name="configure-the-application"></a>アプリケーションの構成  
  
1. 次の手順で、Microsoft メッセージ キュー (MSMQ) コンポーネントがコンピューターにインストールされていることを確認します。  
  
   1.  をクリックして**開始**を右クリックして**コンピューター**、順にクリックします**管理**を開く**サーバー マネージャー**します。  
  
   2.  展開、**機能**ノード。  場合**メッセージ キュー**は右クリックしてインストールされていない**機能**を選択し、**機能の追加**します。 確認**メッセージ キュー**、 をクリックして**次**、順にクリックします**インストール**そのシステムで MSMQ をインストールします。  
  
2. 次の手順で、メッセージ キュー サービスがコンピューターで開始され、WCF-NetMsmq アダプターで使用できることを確認します。  
  
   1.  クリックして**開始**、 をポイント**管理ツール**、順にクリックします**サービス**します。  
  
   2.  **サービス**、ことを確認、**状態**の**メッセージ キュー**サービスは**開始**します。 サービスが開始されていない場合は右クリック**メッセージ キュー**、 をクリックし、**開始**します。  
  
3. WCF-NetMsmq がクライアントからの受信 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] メッセージを取得する元となる、受信場所が使用するターゲット キューを作成します。  
  
   1.  クリックして**開始**、 をポイント**管理ツール**、順にクリックします**コンピュータの管理**します。  
  
   2.  **コンピュータの管理**、展開**サービスとアプリケーション**、展開**メッセージ キュー**、右クリック**専用キュー**、 をポイント**新規**、 をクリックし、**プライベート キュー**します。  
  
   3.  **新しい専用キュー**ダイアログ ボックスに「`WCFNetMsmqAdapterPublishing`で、**キュー名**テキスト ボックスで、、**トランザクション**チェック ボックスをオンにして **[ok]**.  
  
4. 次の手順に従って、サンプル アプリケーションの WCF-NetMsmq 受信場所を作成します。  
  
   1. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
   2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、**BizTalk グループ**、展開**アプリケーション**、展開**WCFNetMsmqAdapterPublishing**を右クリックして**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート。**  
  
   3. **受信ポートのプロパティ** ダイアログ ボックスで、**名前**テキスト ボックスに「 `WCFNetMsmqAdapterPublishing.ReceivePurchaseOrder`、順にクリックします**OK**します。  
  
   4. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリック **[wcfnetmsmqadapterpublishing.receivepurchaseorder]**、 をポイント**新規**、順にクリックします**受信場所**.  
  
   5. **受信場所のプロパティ** ダイアログ ボックスで、**名前**テキスト ボックスに「`WCFNetMsmqAdapterPublishing.ReceivePurchaseOrder.NetMsmq`します。  
  
   6. **受信場所のプロパティ** ダイアログ ボックスで、**トランスポート**の横**型**、 **Wcf-netmsmq**から、ドロップダウン リスト、およびクリック**構成**します。  
  
   7. **Wcf-netmsmq トランスポートのプロパティ** ダイアログ ボックスで、**全般** タブで、**アドレス (URI)** テキスト ボックスに「 `net.msmq://localhost/private/WCFNetMsmqAdapterPublishing`。  
  
   8. **Wcf-netmsmq トランスポートのプロパティ** ダイアログ ボックスで、**バインド** タブで、ことを確認します、**トランザクション** チェック ボックスをオンします。  
  
      > [!NOTE]
      >  ターゲット キューをトランザクション キューとして作成したため、このチェック ボックスをオンにする必要があります。 このチェック ボックスがオンになっていない場合、受信場所のトランザクション要件と基になる MSMQ キューのトランザクション要件との間に不一致が生じるため、受信場所が有効になりません。  
  
   9. **Wcf-netmsmq トランスポートのプロパティ** ダイアログ ボックスで、**セキュリティ** タブで  **None**から、**セキュリティ モード**ドロップダウン リスト.  
  
      > [!NOTE]
      >  このチュートリアルでは、MSMQ は、[!INCLUDE[btsAD](../includes/btsad-md.md)] 統合を無効にしてコンピューターにインストールされていると想定しています。 既定値は**WindowsDomain**、用、 **MSMQ 認証モード**プロパティが使用可能な場合に[!INCLUDE[btsAD](../includes/btsad-md.md)]統合が有効になります。  
  
   10. **受信場所のプロパティ**ダイアログ ボックスで、をクリックして**OK**します。  
  
5. サンプル アプリケーションの FILE 送信ポートを作成します。 このポートは、サービスの基となるオーケストレーションの注文書からの応答をルーティングします。  
  
   1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[ **WCFNetMsmqAdapterPublishing**を右クリックして**送信ポート**、] をポイント**新規**をクリックして**静的な一方向送信ポート**します。  
  
   2. **送信ポートのプロパティ** ダイアログ ボックスで、**名前**テキスト ボックスに「`WCFNetMsmqAdapterPublishing.SendPurchaseOrder.File`します。  
  
   3. **送信ポートのプロパティ** ダイアログ ボックスで、**トランスポート**の横**型**を選択します**ファイル**ドロップダウン リストからしクリックして**構成**します。  
  
   4. **FILE トランスポートのプロパティ** ダイアログ ボックスの 、**全般** タブで、**先フォルダー**テキスト ボックスに「 `C:\WCFNetMsmqAdapterPublishing\Out`、順にクリックします**ok**.  
  
   5. **送信ポートのプロパティ**ダイアログ ボックスで、をクリックして**OK**します。  
  
6. 次の手順で、サンプル アプリケーションのホスト名とバインドを指定します。  
  
   1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、**WCFNetMsmqAdapterPublishing**、展開**オーケストレーション**は、サンプル オーケストレーションを右クリックし、**プロパティ**、 をクリックして**バインド**、設定と**ホスト**に**BizTalkServerApplication**または別の適切なホスト。  
  
   2. **オーケストレーションのプロパティ**ダイアログ ボックスで、 **WCFNetMsmqAdapterPublishing.ReceivePurchaseOrder**から、**受信ポート**のドロップダウンリスト**PurchaseOrderRequestPort**します。  
  
   3. **オーケストレーションのプロパティ**ダイアログ ボックスで、 **WCFNetMsmqAdapterPublishing.SendPurchaseOrder.File**から、**送信ポート/送信ポート グループ**ドロップダウン リスト**PurchaseOrderResponsePort**します。  
  
   4. **オーケストレーションのプロパティ**ダイアログ ボックスで、をクリックして **[ok]** 構成を保存します。  
  
## <a name="publish-the-metadata-for-the-wcf-netmsmq-receive-location"></a>Wcf-netmsmq 受信場所のメタデータを公開します。  
  
1. クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk WCF サービス公開ウィザード**します。  
  
2. **BizTalk WCF サービス公開ウィザードへようこそ**] ページで [**次**します。  
  
3. **WCF サービスの種類** ページで、、**メタデータのみのエンドポイント (MEX)** WCFNetMsmq のメタデータを公開する チェック ボックスの受信場所。 選択**WCFNetMsmqAdapterPublishing.ReceivePurchaseOrder.NetMsmq**から、**受信場所のメタデータを公開**ドロップダウン リスト、およびクリック **[次へ]** します。  
  
4. **WCF サービスの作成**] ページで、[ **BizTalk オーケストレーションの WCF サービスとして発行**、順にクリックします**次**します。  
  
5. **BizTalk アセンブリ** ページの 、 **BizTalk アセンブリ ファイル (\*.dll)** テキスト ボックスで、をクリックして**参照**を参照する、 **C:\WCFNetMsmqAdapterPublishing\BizTalkApp\bin\Development**フォルダー をクリックし、サンプル オーケストレーションを含むアセンブリをダブルクリックして**次**します。  
  
6. **オーケストレーションおよびポート**ことを確認します ページで、**ポート: PurchaseOrderRequestPort**ノード ページで、選択されている場合をクリックして**次**します。  
  
    受信ポートの MEX が公開され、メッセージを受信場所に送信するためにクライアントによって使用されます。  
  
7. **WCF サービスのプロパティ**ページで、 **WCF サービスのターゲットの名前空間**テキスト ボックスに、この公開された URI を入力[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]を使用するサービスをクリックして **[次へ]**. このチュートリアルでは、既定の URI のままに`http://tempuri.org/`します。  
  
8. **WCF サービスの場所** ページで、次の場所を指定する操作を実行、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービスを作成、およびクリックして**次**:  
  
   1. **場所**テキスト ボックスに「Web ディレクトリ名、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービスが実行されるか、クリック**参照**Web ディレクトリを選択します。 このチュートリアルでは、既定の場所のままに (http://localhost/<em>\<BizTalk アセンブリ名\></em>) で、**場所**テキスト ボックス。  
  
   2. 選択、 **WCF サービスへの匿名アクセスを許可する**オプション。 : このオプションでは、作成した仮想ディレクトリに匿名アクセスを追加します。 このウィザードで作成される Web アプリケーションに匿名認証を許可するには、このオプションをオンにする必要があります。  
  
9. **WCF サービスの概要**] ページで [**作成**を作成する、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービス。  
  
10. **BizTalk WCF サービス公開ウィザードの完了**] ページで [**完了**します。  
  
## <a name="configure-the-web-application-hosting-the-published-metadata-service"></a>公開したメタデータ サービスをホストする Web アプリケーションを構成します。  
  
1. コマンド プロンプトを開きに移動、 **C:\inetpub\wwwroot\Microsoft.Samples.BizTalk.WCF.NetMsmqPublishing.BizTalkApp**フォルダー場所、 **BizTalk WCF サービス公開ウィザード**作成、 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービス。 開く、 **Web.config**メモ帳を使用したファイルします。  
  
2. メモ帳で、次の行を追加、 **\<system.web\>** 要素。  
  
   ```  
   <trust level="Full" originUrl="" />  
   ```  
  
   > [!NOTE]
   >  この設定は省略可能です。 この設定により、公開された [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスをホストする ASP.NET アプリケーションに対して、オペレーティング システムのセキュリティの対象であるすべてのリソースへのアクセス権限が付与されます。  
  
3. 次の手順に従い、公開された [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスを Internet Explorer を使用してテストします。  
  
   1. クリックして**開始**、 をポイント**管理者ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**します。  
  
   2. IIS マネージャーでは、このサービスが実行される BizTalk データベースの適切なアクセス許可を持つアプリケーション プールを作成します。 右クリック**アプリケーション プール**、 をクリックして**アプリケーション プールの追加**、アプリケーション プールの名前を入力し、 **OK**します。  
  
   3. 展開**アプリケーション プール**作成したアプリケーション プールを右クリックし、**詳細設定**します。 **プロセス モデル**セクションで、これにアクセスするアカウントを入力、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースで、 **Identity**フィールド。  
  
   4. 展開**Web サイト**、展開**既定の Web サイト**、BizTalk WCF サービス公開ウィザードを作成した Web アプリケーションを展開します。  
  
   5. IIS マネージャーで、中央のウィンドウでクリックして**コンテンツ ビュー**アプリケーションのファイルを表示します。  
  
   6. 右クリックし、 **Microsoft_Samples_BizTalk_WCF_NetMsmqPublishing_BizTalkApp_OrderProcess_PurchaseOrderRequestPort.svc**サービス ファイルを**BizTalk WCF サービス公開ウィザード**クリックして作成されると、**参照**します。 表示する Internet Explorer が開きます、 **BizTalkServerInstance サービス**ことを示すページのインスタンス、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービスが実行されています。 ページには、コピーして、サービス メタデータ ツール (svcutil.exe) を使用した完全な WSDL アドレスが表示されます。 または、から Visual Studio で、プロキシを取得するコードを構成するファイルとサービスのクライアント アプリケーションを作成するために使用できます。  
  
   7. 完全な WSDL アドレスを持つコマンドラインをクリップボードにコピー **BizTalkServerInstance サービス**前の手順で Internet Explorer を表示するページ。  
  
       **svcutil.exe http://localhost/Microsoft.Samples.BizTalk.WCF.NetMsmqPublishing.BizTalkApp/Microsoft_Samples_BizTalk_WCF_NetMsmqPublishing_BizTalkApp_OrderProcess_PurchaseOrderRequestPort.svc?wsdl**  
  
## <a name="build-the-client-application"></a>クライアント アプリケーションをビルドします。  
  
1. 管理者として Visual Studio コマンド プロンプトを開きに移動、 **C:\WCFNetMsmqAdapterPublishing\WCFClient**フォルダー。 このフォルダーに、プロキシ クラスおよびアプリケーション構成ファイルが保存されます。  
  
2. 前の手順でコピーした、完全な WSDL アドレスを含む svcutil.exe コマンド ラインを貼り付け、Enter キーを押します。 これは、プロキシ クラスを作成します**BizTalkServiceInstance.cs**、およびアプリケーション構成ファイル、 **output.config**します。コマンド プロンプト ウィンドウは、最後のセクションで使用するため開いたままにします。  
  
3. ソリューション エクスプ ローラーで、Visual Studio で右クリック**WCFClient**、 をポイント**追加**、 をクリックし、**既存項目の**します。  
  
4. **既存項目の追加** ダイアログ ボックスで、参照、 **WCFClient**フォルダーで、**すべてのファイル (\*.\*)** で、**ファイルの種類**ドロップダウン リストで、 **BizTalkServiceInstance.cs**と**output.config**ファイル、および順にクリックします**追加**します。  
  
5. 展開**WCFClient**、右クリックして**output.config**、 をクリックして**の名前を変更**、し、入力`App.config`新しい名前として。  
  
6. ダブルクリック**Program.cs** 、公開されたを呼び出す方法を確認する[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]svcutil.exe によって生成されたプロキシ クラスを使用してサービスを提供します。  
  
7. 展開**参照**、いることを確認し、 **WCFClient**プロジェクトには、 **System.ServiceModel.dll**参照。  
  
8. 右クリックし、 **WCFClient**順に選択して**ビルド**します。 次のセクションに、開くおよび移動に、Visual Studio を保持します。  
  
## <a name="test-the-sample-solution-with-the-wcf-netmsmq-adapter"></a>Wcf-netmsmq アダプターを使用したサンプル ソリューションをテストします。  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、 **WCFNetMsmqAdapterPublishing**アプリケーション、およびクリック**開始**します。 **開始**ダイアログ ボックスで、をクリックして**開始**します。  
  
2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、**プラットフォームの設定**、展開**ホスト インスタンス**を右クリックして**BizTalkServerApplication**またはその他クリックして、ホスト インスタンスを適切な**再起動**します。 このステップは必須ではありませんが、この時点でサンプルが正しく動作することを確認しておくことをお勧めします。  
  
3. Visual Studio での**デバッグ** メニューのをクリックして**デバッグなしで開始**WCFClient アプリケーションを実行します。 この操作で、サンプル メッセージが WCF-NetMsmq 受信場所に送信されます。 メッセージが送信されたことを示す次の出力メッセージが表示されます。  
  
    **Wcf-netmsmq 送信操作の呼び出しの受信場所**  
  
    **WCF クライアント アプリケーションを終了する任意のキーを押します**  
  
4. 任意のキーを押して、WCFClient アプリケーションを閉じてください。  
  
5. Visual Studio コマンド プロンプトで、 **C:\WCFNetMsmqAdapterPublishing\Out**フォルダーを確認して、応答メッセージを返信 WCFClient アプリケーションが存在するとします。  
  
6. インターネット エクスプ ローラーとビューで開きます {GUID} .xml ファイルをダブルクリックして、 **OrderID**値がサービスによって処理されます。  
  
## <a name="see-also"></a>参照  
 [構成、Wcf-netmsmq 受信場所](../core/how-to-configure-a-wcf-netmsmq-receive-location.md)   
 [WCF アダプターのチュートリアル](../core/wcf-adapter-walkthroughs.md)   
 [WCF 受信アダプタへのサービス メタデータの公開](../core/publishing-service-metadata-for-the-wcf-receive-adapters.md)