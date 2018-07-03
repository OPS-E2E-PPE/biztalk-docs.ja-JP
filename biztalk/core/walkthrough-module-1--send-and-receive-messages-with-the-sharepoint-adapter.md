---
title: 'チュートリアル: モジュール 1 - 送信および受信メッセージを Windows SharePoint Services アダプター |Microsoft Docs'
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
ms.openlocfilehash: 320b64b75bb73e384e2a1af8281e5b578ecf0330
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986435"
---
# <a name="walkthrough-module-1---sending-and-receiving-messages-with-the-windows-sharepoint-services-adapter"></a>チュートリアル: モジュール 1 - Windows SharePoint Services アダプターでメッセージを送受信します。
このチュートリアルでは、Windows SharePoint Services アダプターとコンテンツ ベースのルーティング (CBR) を使用してメッセージを送受信できるように Windows SharePoint Services と [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成する方法について説明します。 コンテンツ ベースのルーティングを使用すると、特定のポートに正確にバインドされたメッセージに対するメッセージ サブスクリプションが必要ではなくなります。 また、エンベロープのプロパティや受信ポートの構成プロパティに基づいてメッセージをルーティングするユーザーにとって、柔軟性も向上します。 Windows SharePoint Services アダプターの概要については、次を参照してください。 [、Windows SharePoint Services アダプターとは何ですか?](../core/what-is-the-windows-sharepoint-services-adapter.md)します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するための前提条件は、次のとおりです。  
  
- 実行されている BizTalk Server の完全なインストールでのシングル サーバー配置する必要があります[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]または[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]します。  
  
  マルチ サーバー展開で Windows SharePoint Services アダプターを使用する方法の詳細については、次を参照してください。[設定と、Windows SharePoint Services アダプターを展開する](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md)します。  
  
## <a name="configure-windows-sharepoint-services"></a>Windows SharePoint Services を構成します。  
 ここでは、3 つのドキュメント ライブラリが含まれた、トップレベルの SharePoint Web サイトを作成します。 Windows SharePoint Services アダプターでは、これらのライブラリを使用して、メッセージをアップロード元のライブラリからアップロード先のライブラリに移動します。 このメッセージはドキュメント ライブラリにもアーカイブされます。 このチュートリアルで Windows Sharepoint Services アダプターによってアクセスする Windows SharePoint Services サイトを提供し、このサイトにアクセスするためのユーザー権限を設定するには、次の手順を実行する必要があります。  
  
#### <a name="create-a-windows-sharepoint-services-site"></a>Windows SharePoint Services サイトの作成  
  
1. クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**SharePoint サーバーの全体管理。**  
  
2. [**仮想サーバーの構成**、] をクリックして**トップレベル Web サイトの作成**です。  
  
3. **仮想サーバーのリスト**に、Windows SharePoint Services アダプターをインストールした Web サイトを選択します。 たとえば、 `Default Web Site`のようにします。  
  
4. **Web サイトのアドレス**セクションで、 **URL 名**フィールドに「`WSSAdapterWalkthrough`します。  
  
5. **サイト コレクションの所有者**セクションで、**ユーザー名フィールド、** ユーザー名を入力します。 このユーザーが Web サイトの所有者になります。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の特別なアクセス許可は必要ありません。  
  
6. **サイト コレクションの所有者**セクションで、**電子メール**フィールドに、電子メール アドレスを入力します。  
  
7. **[OK]** をクリックします。  
  
8. **最上位サイトが正常に作成された** ページで、先ほど作成した新しいトップレベル Web サイトをクリックします。 たとえば、 `http://<server_name>/sites/WSSAdapterWalkthrough`のようにします。  
  
9. 選択、**チーム サイト**クリックして、テンプレートの一覧からテンプレート**OK**します。 これにより、チーム Web サイトのホーム ページが開きます。  
  
#### <a name="create-a-source-document-library"></a>"アップロード元" のドキュメント ライブラリの作成  
  
1.  チーム Web サイトのホーム ページで、上部のナビゲーション バーで、次のようにクリックします。**作成**です。  
  
2.  [**ドキュメント ライブラリ**、] をクリックして**ドキュメント ライブラリ**します。  
  
3.  **名前と説明**セクションで、**名前 フィールドに**型`Source`します。  
  
4.  **ナビゲーション**セクションで、**はい**このフォーム ライブラリをクイック起動バーに表示します。  
  
5.  **ドキュメント テンプレート**セクションで、**ドキュメント テンプレート**ドロップダウン リストで、`None`します。  
  
6.  **[作成]** をクリックします。 ドキュメント ライブラリが作成され、空のライブラリにリダイレクトされます。  
  
#### <a name="create-a-destination-document-library"></a>"アップロード先" のドキュメント ライブラリの作成  
  
1.  チーム Web サイトのホーム ページで、上部のナビゲーション バーで、次のようにクリックします。**作成**です。  
  
2.  [**ドキュメント ライブラリ**、] をクリックして**ドキュメント ライブラリ**します。  
  
3.  **名前と説明**セクションで、**名前フィールド**、型`Destination`します。  
  
4.  **ナビゲーション**セクションで、**はい**このフォーム ライブラリをクイック起動バーに表示します。  
  
5.  **ドキュメント テンプレート**セクションで、**ドキュメント テンプレート**ドロップダウン リストで、`None`します。  
  
6.  **[作成]** をクリックします。 ドキュメント ライブラリが作成され、空のライブラリにリダイレクトされます。  
  
#### <a name="create-an-archive-document-library"></a>"アーカイブ" ドキュメント ライブラリの作成  
  
1.  チーム Web サイトのホーム ページで、上部のナビゲーション バーで、次のようにクリックします。**作成**です。  
  
2.  [**ドキュメント ライブラリ**、] をクリックして**ドキュメント ライブラリ**します。  
  
3.  **名前**し、[説明] セクションで、**名前フィールド**、型`Archive`します。  
  
4.  **ナビゲーション**セクションで、**はい**このフォーム ライブラリをクイック起動バーに表示します。  
  
5.  **ドキュメント テンプレート**セクションで、**ドキュメント テンプレート**ドロップダウン リストで、`None`します。  
  
6.  **[作成]** をクリックします。 ドキュメント ライブラリが作成され、空のライブラリにリダイレクトされます。  
  
7.  `WSSAdapterWalkthrough` Web サイトを閉じます。  
  
8.  閉じる、 **SharePoint Central Administration** Web サイト。  
  
#### <a name="configure-windows-security"></a>Windows セキュリティの構成  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**コンピュータの管理**します。  
  
2.  コンソール ツリーで、展開**ローカル ユーザーとグループ**、 をクリックし、**グループ**します。  
  
3.  右クリックし、 **SharePoint Enabled Hosts**グループで、[**をグループに追加**、] をクリックし、**追加**します。  
  
4.  ** ダイアログ ボックスの ユーザー、コンピューター、またはグループ****を選択するオブジェクト名の入力**をクリックして、実行には、BizTalk Server ホスト インスタンスを構成したアカウントの名前を入力**OK**します。  
  
5.  コンソール ツリーで、展開**サービスとアプリケーション**、 をクリックし、**サービス**します。  
  
6.  右クリック**BizTalk Service BizTalk Group: < biztalk ホスト名 >**、 をクリックし、**再起動**します。  
  
    > [!NOTE]
    >  <BizTalk ホスト名> は、ホストの名前です。 既定では `BizTalkServerApplication` です。  
  
    > [!NOTE]
    >  サービスを再起動するまで、メンバーシップは有効になりません。  
  
7.  閉じる**コンピュータの管理**します。  
  
#### <a name="configure-sharepoint-security"></a>SharePoint セキュリティの構成  
  
1. Web ブラウザを開き、作成したサイトの URL に移動します。 たとえば、 `http://<server_name>/sites/WSSAdapterWalkthrough`のようにします。  
  
2. チーム Web サイトのホーム ページで、上部のナビゲーション バーで、次のようにクリックします。**サイト設定**します。  
  
3. [**管理**、] をクリックして**ユーザーを管理する**します。  
  
4. **[ユーザーの追加]** をクリックします。  
  
5. **手順 1: ユーザーの選択**、アカウントの名前を入力する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホスト インスタンスを実行しています。  
  
6. **手順 2: サイト グループの選択**を選択、**リーダー**と**共同作成者**チェック ボックス。  
  
7. **[次へ]** をクリックします。  
  
8. クリア、**が追加されたことがあるので、これらのユーザーを通知する次のメールを送信**チェック ボックスをオンにして**完了**します。  
  
9. `WSSAdapterWalkthrough` Web サイトを閉じます。  
  
## <a name="create-and-configure-the-biztalk-server-ports"></a>BizTalk Server のポートの作成と構成  
 ここでは、Windows SharePoint Services アダプター用に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信ポート、受信場所、および送信ポートを作成および構成します。 これらのポートは、Windows Sharepoint Services アダプターによって送受信されたドキュメントが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で送受信される際のエントリ ポイントです。  
  
#### <a name="create-the-receive-port"></a>受信ポートの作成  
  
1. クリックして**開始**、**すべてのプログラム**、 [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理コンソール。**  
  
2. 展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**、右クリックして**の受信ポート**、 をクリックして**新規**、 をクリックし、**一方向の受信ポート.**  
  
3. **受信ポートのプロパティ**ダイアログ ボックスで、**全般**、型`FromSource`で、**名前**フィールド。  
  
4. **[OK]** をクリックします。  
  
#### <a name="create-the-receive-location"></a>受信場所を作成します。  
  
1.  **BizTalk 管理コンソール**を右クリックし、**受信場所**ノード、をクリックして**新規**、順にクリックします**一方向の受信場所**.  
  
2.  **受信ポートの選択**ダイアログ ボックスで、 `FromSource`、 をクリックし、 **OK**。  
  
3.  **受信場所のプロパティ**ダイアログ ボックスで、**全般**、型`SourceLocation`で、**名前**フィールド。  
  
4.  **トランスポート**セクションで、**型**ドロップダウン リストで、`Windows``SharePoint``Services`します。  
  
5.  クリックして**構成**Windows SharePoint Services アダプターのプロパティを構成します。  
  
6.  **アダプター Web サービス ポート**プロパティでは、Windows SharePoint Services アダプター Web サービスがインストールされている仮想サーバーのポート番号を入力します。 既定では、ポート 80 です。  
  
7.  型`Archive`で、**アーカイブ場所**プロパティ。  
  
8.  型`10`で、**のポーリング間隔**プロパティ。  
  
9. SharePoint サイトに URL を入力、 **ShareP**ポイント サイトの Url プロパティです。 たとえば、 `http://<server_name>/sites/WSSAdapterWalkthrough`のようにします。  
  
10. 型`Source`の**ソース ドキュメント ライブラリ**プロパティ。  
  
11. **[OK]** をクリックします。  
  
12. **受信場所のプロパティ**ダイアログ ボックスで、`BizTalkServerApplication`として、**受信ハンドラー**します。  
  
13. **受信パイプライン**ドロップダウン リストで、`PassThruReceive`します。  
  
14. **[OK]** をクリックします。  
  
#### <a name="create-the-send-port"></a>送信ポートを作成します。  
  
1.  **BizTalk 管理コンソール**を右クリックし、**送信ポート**ノード、をクリックして**新規**、順にクリックします**静的な一方向送信ポート**.  
  
2.  **送信ポートのプロパティ**ダイアログ ボックスで、**全般**、型`SendToDestination`で、**名前**フィールド。  
  
3.  **トランスポート**セクションで、`Windows SharePoint Services`型。  
  
4.  クリックして**構成**Windows SharePoint Services アダプターのプロパティを構成します。  
  
5.  **アダプター Web サービス ポート**プロパティでは、Windows SharePoint Services アダプター Web サービスがインストールされている仮想サーバーのポート番号を入力します。 既定では、ポート 80 です。  
  
6.  入力`Destination`の**先フォルダー**プロパティ。  
  
7.  入力`PurchaseOrder1-%MessageID%.xml`の**Filename**プロパティ。  
  
8.  設定、**上書き**プロパティを`Yes`します。  
  
9. SharePoint サイトに URL を入力、 **SharePoint サイトの Url**プロパティ。 たとえば、 `http://<server_name>/sites/WSSAdapterWalkthrough`のようにします。  
  
10. 設定、 **Microsoft Office 統合**プロパティを`No`します。  
  
11. **[OK]** をクリックします。  
  
12. **送信ポートのプロパティ ダイアログ ボックス**の**送信ハンドラー**ドロップダウン リストで、`BizTalkServerApplication`します。  
  
13. **送信パイプライン**ドロップダウン リストで、`PassThruTransmit`します。  
  
14. をクリックして、**フィルター**タブ。  
  
15. 選択`WSS.InListName`で、**プロパティ**フィールド。  
  
16. 選択`==`で、**演算子**フィールド。  
  
17. 型`Source`で、**値**フィールド。  
  
18. **[OK]** をクリックします。  
  
## <a name="enable-and-start-the-receive-location-and-receive-port"></a>受信場所と受信ポートの有効化と開始  
 ここでは、受信場所を有効にし、受信ポートを開始します。 Windows Sharepoint Services アダプターが指定された送信ポートおよび受信場所を使用してメッセージを送受信できるようにするには、次の手順を完了する必要があります。  
  
#### <a name="enable-the-receive-location"></a>受信場所の有効化  
  
1.  **BizTalk 管理コンソール**、クリックして、**受信場所**ノード。  
  
2.  右クリックして`SourceLocation`、 をクリックし、**を有効にする**します。  
  
#### <a name="start-the-send-port"></a>送信ポートの開始  
  
1.  **BizTalk 管理コンソール**、クリックして、**送信ポート**ノード。  
  
2.  右クリック`SendToDestination`、 をクリックし、**開始**します。  
  
3.  閉じる、 **BizTalk 管理コンソール**します。  
  
## <a name="sending-a-message-through-the-system"></a>システムからのメッセージを送信します。  
 ここでは、XML ドキュメントを作成し、Windows SharePoint Services Web サイトにアップロードします。 そのメッセージは Windows SharePoint Services アダプターによって取得され、アーカイブ ドキュメント ライブラリにアーカイブされた後、アップロード先のドキュメント ライブラリに送信されます。 この手順は、Windows SharePoint Services アダプターを使用し、SharePoint Web サイトから、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を経由して SharePoint サービス Web サイトへと送信されるドキュメント フローを示しています。  
  
#### <a name="create-a-working-directory"></a>作業ディレクトリの作成  
  
-   呼ばれるコンピューターにディレクトリを作成**WSSAdapterWalkthrough**します。 たとえば、 `C:\WSSAdapterWalkthrough`のようにします。  
  
#### <a name="create-an-xml-file"></a>XML ファイルを作成します。  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**アクセサリ**、順にクリックします**メモ帳。**  
  
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
  
1. Web ブラウザーを開き、前の作業で作成したサイトの URL に移動します。 たとえば、 `http://<server_name>/sites/WSSAdapterWalkthrough`のようにします。  
  
2. 左側にある [**ドキュメント**、] をクリックして**ソース**します。  
  
3. クリックして**ドキュメントのアップロード**します。  
  
4. **名前**ボックスで、入力するか、上記で作成した XML ファイルを参照します。 たとえば、 `C:\WSSAdapterWalkthrough\PurchaseOrder1.xml`、 をクリックし、**を保存して閉じます**します。 これで、ファイルが一覧内に表示されるようになります。  
  
5. ブラウザー ウィンドウを更新します。 `PurchaseOrder1.xml` ファイルは、このライブラリの一覧に表示されなくなります。  
  
   > [!NOTE]
   >  ポーリング間隔が 10 秒に設定されているため、ブラウザーを数回更新する必要がある場合があります。  
  
6. 上部のナビゲーション バーでクリックして**ドキュメントし、リスト**します。  
  
7. [**ドキュメント ライブラリ**、] をクリックして**先**します。  
  
8. アップロード先のドキュメント ライブラリに表示されます、メッセージが表示されています。 また、アーカイブ ドキュメント ライブラリにアーカイブされたコピーも表示されます。  
  
   > [!NOTE]
   >  メッセージが [アップロード先のドキュメント ライブラリ] に表示されない場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの「Windows SharePoint Services アダプターのトラブルシューティング」を参照してください。  
  
## <a name="summary"></a>まとめ  
 このチュートリアルでは、Windows SharePoint Services アダプターとコンテンツ ベースのルーティング (CBR) を使用してメッセージを送受信できるように Windows SharePoint Services と [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成する方法について説明しました。  
  
## <a name="next-steps"></a>次の手順  
 これで、このチュートリアルを完了すると、実行、[チュートリアル: モジュール 2 - Windows SharePoint Services アダプターと Office の統合](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md)チュートリアルについては、このチュートリアルと表示を行う作業の発展Windows SharePoint Services アダプターと Office を統合する方法。  
  
## <a name="see-also"></a>参照  
 [Windows SharePoint Services アダプターとは何ですか。](../core/what-is-the-windows-sharepoint-services-adapter.md)   
 [Windows SharePoint Services アダプターのチュートリアル](../core/windows-sharepoint-services-adapter-walkthroughs.md)