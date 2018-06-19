---
title: 'チュートリアル: モジュール 1 - 送信および受信メッセージを Windows SharePoint Services アダプター |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows SharePoint Services, creating sites
- tutorials, Windows SharePoint Services adapters
- Windows SharePoint Services adapter tutorials, receiving messages
- security, Windows SharePoint Services
- creating, Windows SharePoint Services site
- Windows SharePoint Services, security
- Windows SharePoint Services, document libraries
- Windows SharePoint Services adapters, security
- Windows SharePoint Services
- Windows SharePoint Services adapter tutorials, sending messages
ms.assetid: 6494aef5-bb1d-4a41-8186-1d49625a1013
caps.latest.revision: 41
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8e83297233c4f8ac51ad90f488437a6c259691a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010507"
---
# <a name="walkthrough-module-1---sending-and-receiving-messages-with-the-windows-sharepoint-services-adapter"></a>チュートリアル: モジュール 1 - Windows SharePoint Services アダプターでメッセージを送受信します。
このチュートリアルでは、Windows SharePoint Services アダプターとコンテンツ ベースのルーティング (CBR) を使用してメッセージを送受信できるように Windows SharePoint Services と [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成する方法について説明します。 コンテンツ ベースのルーティングを使用すると、特定のポートに正確にバインドされたメッセージに対するメッセージ サブスクリプションが必要ではなくなります。 また、エンベロープのプロパティや受信ポートの構成プロパティに基づいてメッセージをルーティングするユーザーにとって、柔軟性も向上します。 Windows SharePoint Services アダプターの概要については、次を参照してください。 [Windows SharePoint Services アダプターは何ですか?](../core/what-is-the-windows-sharepoint-services-adapter.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するための前提条件は、次のとおりです。  
  
-   完全インストール済みで実行されている BizTalk Server のシングル サーバー配置する必要があります[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]または[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]です。  
  
 マルチ サーバー展開で Windows SharePoint Services アダプターを使用する方法については、次を参照してください。[の設定と Windows SharePoint Services アダプターを展開する](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md)です。  
  
## <a name="configure-windows-sharepoint-services"></a>Windows SharePoint Services を構成します。  
 ここでは、3 つのドキュメント ライブラリが含まれた、トップレベルの SharePoint Web サイトを作成します。 Windows SharePoint Services アダプターでは、これらのライブラリを使用して、メッセージをアップロード元のライブラリからアップロード先のライブラリに移動します。 このメッセージはドキュメント ライブラリにもアーカイブされます。 このチュートリアルで Windows Sharepoint Services アダプターによってアクセスする Windows SharePoint Services サイトを提供し、このサイトにアクセスするためのユーザー権限を設定するには、次の手順を実行する必要があります。  
  
#### <a name="create-a-windows-sharepoint-services-site"></a>Windows SharePoint Services サイトの作成  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリック**SharePoint サーバーの全体管理。**  
  
2.  **仮想サーバーの構成**をクリックして**トップレベル Web サイトを作成**です。  
  
3.  **仮想サーバーのリスト**に Windows SharePoint Services アダプターをインストールした Web サイトを選択します。 たとえば、 `Default Web Site`のようにします。  
  
4.  **Web サイトのアドレス**セクションで、 **URL 名**フィールドに「`WSSAdapterWalkthrough`です。  
  
5.  **サイト コレクションの所有者**セクションで、**ユーザー名 フィールド、** ユーザー名を入力します。 このユーザーが Web サイトの所有者になります。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の特別なアクセス許可は必要ありません。  
  
6.  **サイト コレクションの所有者**セクションで、**電子メール**フィールドに、電子メール アドレスを入力します。  
  
7.  **[OK]** をクリックします。  
  
8.  **最上位サイトが正常に作成された** ページで、先ほど作成した新しいトップレベル Web サイト をクリックします。 たとえば、 `http://<server_name>/sites/WSSAdapterWalkthrough`のようにします。  
  
9. 選択、**チーム サイト**クリックして、テンプレートの一覧からテンプレート**OK**です。 これにより、チーム Web サイトのホーム ページが開きます。  
  
#### <a name="create-a-source-document-library"></a>"アップロード元" のドキュメント ライブラリの作成  
  
1.  チーム Web サイトのホーム ページで、上部のナビゲーション バーで、クリックして**作成**です。  
  
2.  **ドキュメント ライブラリ**をクリックして**ドキュメント ライブラリ**です。  
  
3.  **名前と説明**セクションで、**名 フィールドで**型`Source`です。  
  
4.  **ナビゲーション**セクションで、**はい**クイック起動バーにこのフォーム ライブラリを表示します。  
  
5.  **ドキュメント テンプレート**セクションで、**ドキュメント テンプレート**ドロップダウン リストで、`None`です。  
  
6.  **[作成]** をクリックします。 ドキュメント ライブラリが作成され、空のライブラリにリダイレクトされます。  
  
#### <a name="create-a-destination-document-library"></a>"アップロード先" のドキュメント ライブラリの作成  
  
1.  チーム Web サイトのホーム ページで、上部のナビゲーション バーで、クリックして**作成**です。  
  
2.  **ドキュメント ライブラリ**をクリックして**ドキュメント ライブラリ**です。  
  
3.  **名前と説明**セクションで、 **Name フィールド**、型`Destination`です。  
  
4.  **ナビゲーション**セクションで、**はい**クイック起動バーにこのフォーム ライブラリを表示します。  
  
5.  **ドキュメント テンプレート**セクションで、**ドキュメント テンプレート**ドロップダウン リストで、`None`です。  
  
6.  **[作成]** をクリックします。 ドキュメント ライブラリが作成され、空のライブラリにリダイレクトされます。  
  
#### <a name="create-an-archive-document-library"></a>"アーカイブ" ドキュメント ライブラリの作成  
  
1.  チーム Web サイトのホーム ページで、上部のナビゲーション バーで、クリックして**作成**です。  
  
2.  **ドキュメント ライブラリ**をクリックして**ドキュメント ライブラリ**です。  
  
3.  **名前**し、[説明] セクションで、 **Name フィールド**、型`Archive`です。  
  
4.  **ナビゲーション**セクションで、**はい**クイック起動バーにこのフォーム ライブラリを表示します。  
  
5.  **ドキュメント テンプレート**セクションで、**ドキュメント テンプレート**ドロップダウン リストで、`None`です。  
  
6.  **[作成]** をクリックします。 ドキュメント ライブラリが作成され、空のライブラリにリダイレクトされます。  
  
7.  `WSSAdapterWalkthrough` Web サイトを閉じます。  
  
8.  閉じる、 **SharePoint サーバーの全体管理**Web サイトです。  
  
#### <a name="configure-windows-security"></a>Windows セキュリティの構成  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリック**コンピューターの管理**です。  
  
2.  コンソール ツリーで **ローカル ユーザーとグループ**、クリックして**グループ**です。  
  
3.  右クリックし、 **SharePoint Enabled Hosts**グループで、**グループに追加**、クリックして**追加**です。  
  
4.   **ダイアログ ボックスの ユーザー、コンピューター、またはグループ****を選択するオブジェクト名の入力**の下で実行し、をクリックするには、BizTalk Server ホスト インスタンスを構成しているアカウントの名前を入力**OK**です。  
  
5.  コンソール ツリーで **サービスとアプリケーション**、順にクリック**Services**です。  
  
6.  右クリック**BizTalk Service BizTalk Group: < biztalk ホスト名 >**、クリックして**再起動**です。  
  
    > [!NOTE]
    >  <BizTalk ホスト名> は、ホストの名前です。 既定では `BizTalkServerApplication` です。  
  
    > [!NOTE]
    >  サービスを再起動するまで、メンバーシップは有効になりません。  
  
7.  閉じる**コンピューターの管理**です。  
  
#### <a name="configure-sharepoint-security"></a>SharePoint セキュリティの構成  
  
1.  Web ブラウザを開き、作成したサイトの URL に移動します。 たとえば、 `http://<server_name>/sites/WSSAdapterWalkthrough`のようにします。  
  
2.  チーム Web サイトのホーム ページで、上部のナビゲーション バーで、クリックして**サイト設定**です。  
  
3.  **管理**をクリックして**ユーザーを管理する**です。  
  
4.  **[ユーザーの追加]** をクリックします。  
  
5.  **手順 1: ユーザーの選択**、アカウントの名前を入力する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]でホスト インスタンスが実行されています。  
  
6.  **手順 2: サイト グループの選択**、select、**リーダー**と**共同作成者**のチェック ボックスです。  
  
7.  **[次へ]** をクリックします。  
  
8.  クリア、**が追加されたので、これらのユーザーを通知する次のメールを送信**チェック ボックスをクリックして**完了**です。  
  
9. `WSSAdapterWalkthrough` Web サイトを閉じます。  
  
## <a name="create-and-configure-the-biztalk-server-ports"></a>BizTalk Server のポートの作成と構成  
 ここでは、Windows SharePoint Services アダプター用に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信ポート、受信場所、および送信ポートを作成および構成します。 これらのポートは、Windows Sharepoint Services アダプターによって送受信されたドキュメントが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で送受信される際のエントリ ポイントです。  
  
#### <a name="create-the-receive-port"></a>受信ポートの作成  
  
1.  をクリックして**開始**、**すべてのプログラム**、 [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソールです。**  
  
2.  展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**を右クリックして**の受信ポート**をクリックして**新規**、クリックして**一方向の受信ポートしています.**  
  
3.  **受信ポートのプロパティ**ダイアログ ボックスで、**全般**、型`FromSource`で、**名前**フィールドです。  
  
4.  **[OK]** をクリックします。  
  
#### <a name="create-the-receive-location"></a>受信場所を作成します。  
  
1.  **BizTalk 管理コンソール**を右クリックし、**受信場所**ノード、をクリックして**新規**、クリックして**一方向の受信場所**.  
  
2.  **受信ポートの選択**ダイアログ ボックスで、 `FromSource`、順にクリック**OK**です。  
  
3.  **受信場所のプロパティ**ダイアログ ボックスで、**全般**、型`SourceLocation`で、**名前**フィールドです。  
  
4.  **トランスポート**セクションで、**型**ドロップダウン リストで、`Windows``SharePoint``Services`です。  
  
5.  をクリックして**構成**Windows SharePoint Services アダプターのプロパティを構成します。  
  
6.  **アダプター Web サービス ポート**プロパティ、Windows SharePoint Services アダプター Web サービスがインストールされている仮想サーバーのポート番号を入力します。 既定では、ポート 80 です。  
  
7.  型`Archive`で、**アーカイブ場所**プロパティです。  
  
8.  型`10`で、**のポーリング間隔**プロパティです。  
  
9. SharePoint サイトに URL を入力、 **ShareP**ポイントのサイト Url プロパティです。 たとえば、 `http://<server_name>/sites/WSSAdapterWalkthrough`のようにします。  
  
10. 型`Source`の**ソース ドキュメント ライブラリ**プロパティです。  
  
11. **[OK]** をクリックします。  
  
12. **受信場所のプロパティ**ダイアログ ボックスで、`BizTalkServerApplication`として、**受信ハンドラー**です。  
  
13. **受信パイプライン**ドロップダウン リストで、`PassThruReceive`です。  
  
14. **[OK]** をクリックします。  
  
#### <a name="create-the-send-port"></a>送信ポートを作成します。  
  
1.  **BizTalk 管理コンソール**を右クリックし、**送信ポート**ノード、をクリックして**新規**、クリックして**静的な一方向送信ポート**.  
  
2.  **送信ポートのプロパティ**ダイアログ ボックスで、**全般**、型`SendToDestination`で、**名前**フィールドです。  
  
3.  **トランスポート**セクションで、`Windows SharePoint Services`の種類。  
  
4.  をクリックして**構成**Windows SharePoint Services アダプターのプロパティを構成します。  
  
5.  **アダプター Web サービス ポート**プロパティ、Windows SharePoint Services アダプター Web サービスがインストールされている仮想サーバーのポート番号を入力します。 既定では、ポート 80 です。  
  
6.  入力`Destination`の**コピー先フォルダー**プロパティです。  
  
7.  入力`PurchaseOrder1-%MessageID%.xml`の**Filename**プロパティです。  
  
8.  設定、**上書き**プロパティを`Yes`です。  
  
9. SharePoint サイトに URL を入力、 **SharePoint サイト Url**プロパティです。 たとえば、 `http://<server_name>/sites/WSSAdapterWalkthrough`のようにします。  
  
10. 設定、 **Microsoft Office 統合**プロパティを`No`です。  
  
11. **[OK]** をクリックします。  
  
12. **送信ポートのプロパティ ダイアログ ボックス**で、**送信ハンドラー**ドロップダウン リストで、`BizTalkServerApplication`です。  
  
13. **送信パイプライン**ドロップダウン リストで、`PassThruTransmit`です。  
  
14. クリックして、**フィルター**タブです。  
  
15. 選択`WSS.InListName`で、**プロパティ**フィールドです。  
  
16. 選択`==`で、**演算子**フィールドです。  
  
17. 型`Source`で、**値**フィールドです。  
  
18. **[OK]** をクリックします。  
  
## <a name="enable-and-start-the-receive-location-and-receive-port"></a>受信場所と受信ポートの有効化と開始  
 ここでは、受信場所を有効にし、受信ポートを開始します。 Windows Sharepoint Services アダプターが指定された送信ポートおよび受信場所を使用してメッセージを送受信できるようにするには、次の手順を完了する必要があります。  
  
#### <a name="enable-the-receive-location"></a>受信場所の有効化  
  
1.  **BizTalk 管理コンソール**をクリックして、**受信場所**ノード。  
  
2.  右クリック`SourceLocation`、クリックして**を有効にする**です。  
  
#### <a name="start-the-send-port"></a>送信ポートの開始  
  
1.  **BizTalk 管理コンソール**をクリックして、**送信ポート**ノード。  
  
2.  右クリック`SendToDestination`、クリックして**開始**です。  
  
3.  閉じる、 **BizTalk 管理コンソール**です。  
  
## <a name="sending-a-message-through-the-system"></a>システムからのメッセージを送信します。  
 ここでは、XML ドキュメントを作成し、Windows SharePoint Services Web サイトにアップロードします。 そのメッセージは Windows SharePoint Services アダプターによって取得され、アーカイブ ドキュメント ライブラリにアーカイブされた後、アップロード先のドキュメント ライブラリに送信されます。 この手順は、Windows SharePoint Services アダプターを使用し、SharePoint Web サイトから、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を経由して SharePoint サービス Web サイトへと送信されるドキュメント フローを示しています。  
  
#### <a name="create-a-working-directory"></a>作業ディレクトリの作成  
  
-   呼ばれる、コンピューターにディレクトリを作成**WSSAdapterWalkthrough**です。 たとえば、 `C:\WSSAdapterWalkthrough`のようにします。  
  
#### <a name="create-an-xml-file"></a>XML ファイルを作成します。  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**アクセサリ**、順にクリック**メモ帳です。**  
  
2.  次のように入力します。  
  
    ```  
    <?xml version="1.0"?>  
    <PurchaseOrder>  
        <ID>1001</ID>  
        <FirstName>John</FirstName>  
        <LastName>Doe</LastName>  
        <Amount>750</Amount>  
    </PurchaseOrder>  
    ```  
  
3.  このファイルを `PurchaseOrder1.xml` という名前で作業ディレクトリに保存します。 たとえば、 `C:\WSSAdapterWalkthrough\PurchaseOrder1.xml`のようにします。  
  
#### <a name="upload-the-xml-file"></a>XML ファイルのアップロード  
  
1.  Web ブラウザーを開き、前の作業で作成したサイトの URL に移動します。 たとえば、 `http://<server_name>/sites/WSSAdapterWalkthrough`のようにします。  
  
2.  左側にある、下にある**ドキュメント**をクリックして**ソース**です。  
  
3.  をクリックして**ドキュメントのアップロード**です。  
  
4.  **名前**ボックスで、入力するか、上記で作成した XML ファイルを参照します。 たとえば、 `C:\WSSAdapterWalkthrough\PurchaseOrder1.xml`、クリックして**を保存して閉じます**です。 これで、ファイルが一覧内に表示されるようになります。  
  
5.  ブラウザー ウィンドウを更新します。 `PurchaseOrder1.xml` ファイルは、このライブラリの一覧に表示されなくなります。  
  
    > [!NOTE]
    >  ポーリング間隔が 10 秒に設定されているため、ブラウザーを数回更新する必要がある場合があります。  
  
6.  上部のナビゲーション バーで、をクリックして**ドキュメントし、リスト**です。  
  
7.  **ドキュメント ライブラリ**をクリックして**先**です。  
  
8.  移行先ドキュメント ライブラリに表示されます、メッセージの一覧です。 また、アーカイブ ドキュメント ライブラリにアーカイブされたコピーも表示されます。  
  
    > [!NOTE]
    >  メッセージが [アップロード先のドキュメント ライブラリ] に表示されない場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの「Windows SharePoint Services アダプターのトラブルシューティング」を参照してください。  
  
## <a name="summary"></a>概要  
 このチュートリアルでは、Windows SharePoint Services アダプターとコンテンツ ベースのルーティング (CBR) を使用してメッセージを送受信できるように Windows SharePoint Services と [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成する方法について説明しました。  
  
## <a name="next-steps"></a>次の手順  
 これで、このチュートリアルを完了すると、実行、[チュートリアル: モジュール 2 - Windows SharePoint Services アダプターと Office の統合](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md)チュートリアルでは、このチュートリアルと表示を行う作業を拡張します。Windows SharePoint Services アダプターと Office に統合する方法です。  
  
## <a name="see-also"></a>参照  
 [Windows SharePoint Services アダプターとは何ですか。](../core/what-is-the-windows-sharepoint-services-adapter.md)   
 [Windows SharePoint Services アダプターのチュートリアル](../core/windows-sharepoint-services-adapter-walkthroughs.md)