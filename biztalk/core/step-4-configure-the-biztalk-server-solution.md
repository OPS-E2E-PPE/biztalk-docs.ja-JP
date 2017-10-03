---
title: "手順 4: BizTalk Server ソリューションの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d60e6a82-51af-41e5-a755-5f337492ba2f
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6587e0a8ff84b352ba6f029a7687139daabb72a9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-configure-the-biztalk-server-solution"></a>手順 4: BizTalk Server ソリューションを構成します。
前の手順では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーションを作成、展開して Salesforce の通知を [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で受信し、詳細を内部設置型の SQL Server データベースに挿入できるようになりました。 この手順では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールでアプリケーションを構成します。 アプリケーションの構成は、主にオーケストレーションで作成した論理ポートに対応する物理ポートの作成です。 また、物理ポートの論理ポートへのバインドも関係します。 以下の手順に従って [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーションを構成します。  
  
-   Salesforce から営業案件通知を受信する、要求 - 応答 WCF-BasicHttpRelay 受信場所を構成します。  
  
-   Salesforce にクエリを送信して受信した営業案件通知に関連する商品の詳細を取得するための、要求 - 応答 WCF-WebHttp 送信ポートを構成します。 この送信ポートでは、Salesforce からのクエリの応答も受信します。  
  
-   Salesforce からのクエリの応答を内部設置型の SQL Server データベースに挿入するための一方向の WCF-SQL 送信ポートを構成します。  
  
-   オーケストレーションの論理ポートと [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで作成した物理ポートを関連付けて、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーションを構成します。  
  
### <a name="to-configure-the-wcf-basichttprelay-receive-location"></a>Wcf-basichttprelay 受信場所を構成します。  
  
1.  開く、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 [アプリケーション] ノードを展開し、検索、 **SalesforceIntegration**アプリケーションです。 このアプリケーションは、Visual Studio から [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロジェクトを展開した時に作成されます。  
  
2.  展開、 **SalesforceIntegration**アプリケーションを右クリックして**受信ポート**、 をポイント**新規**、クリックして**要求-応答受信ポート**. ポート名を指定`ReceiveOppNotification`左側のペインからをクリックして**受信場所**です。  
  
3.  [受信場所のプロパティ] ダイアログ ボックスで、次の値を指定します。  
  
    |||  
    |-|-|  
    |名前|入力`ReceiveOppNotification`です。|  
    |型|選択**Wcf-basichttprelay**|  
    |受信ハンドラー|選択**BizTalkServerApplication**|  
    |[受信パイプライン]|選択**[xmlreceive]**|  
    |送信パイプライン|選択**PassThruTransmit**|  
  
     をクリックして**構成**に対して、ポートの種類。  
  
4.  [WCF-BasicHttpRelay トランスポートのプロパティ] ダイアログ ボックスで、次の値を指定します。  
  
    1.  **全般** タブの**アドレス (URI)**、入力`https://btssalesforce.servicebus.windows.net/notifications/opportunity`です。 ここでは、 **btssalesforce**で作成した名前空間は、[手順 1: サービス バスの Namespace を作成する](../core/step-1-create-a-service-bus-namespace.md)です。 Salesforce でワークフローを作成するときに指定した同じ url を指定した URL[手順 2: Salesforce システムのセットアップ](../core/step-2-set-up-the-salesforce-system.md)です。 営業案件のステージが Closed Won に設定するたびに Salesforce を送信する通知 URL にワークフローを設定する*https://btssalesforce.servicebus.windows.net/notifications/opportunity*です。 ここでは、受信場所の構成の一部として同じ URL を指定します。 受信場所が有効になると、URL で指定されたリレー エンドポイントが [!INCLUDE[winazure](../includes/winazure-md.md)] に作成されます。  
  
    2.  **セキュリティ**タブで、次を指定します。  
  
        -   **セキュリティ モード****トランスポート**および**クライアント認証の種類をリレー**を選択**なし**です。  
  
        -   選択、**有効にするサービスの検出**内のサービス動作を公開する チェック ボックス、[サービス レジストリ](http://msdn.microsoft.com/library/windowsazure/dd582704.aspx)です。 指定して、**表示名**を示す名前をレジストリに、サービスを公開します。 設定することができます、**検出モード**公開または非公開にします。 このチュートリアルでは、次のように設定します。**表示名**に`SF Outbound Notification`と**検出モード**に**パブリック**です。  
  
        -   [アクセス制御サービス] で、をクリックして**編集**です。 **アクセス制御サービス STS Uri**、入力`https://btssalesforce-sb.accesscontrol.windows.net/`です。 **発行者名**と**発行者キー**で保存した値を入力して[手順 1: サービス バスの Namespace を作成する](../core/step-1-create-a-service-bus-namespace.md)の**既定のユーザー**と**既定のキー**フィールドです。  
  
    3.  をクリックして**OK**すべての開いているダイアログ ボックスを終了するまでです。  
  
### <a name="to-configure-the-wcf-webhttp-send-port"></a>Wcf-webhttp 送信ポートを構成するには  
  
1.  展開、 **SalesforceIntegration**アプリケーションを右クリックして**送信ポート**、 をポイント**新規**、クリックして**静的な送信請求-応答送信ポート**.  
  
2.  [送信ポートのプロパティ] ダイアログ ボックスで、次の値を指定します。  
  
    |||  
    |-|-|  
    |名前|入力`SalesforceREST`です。|  
    |型|選択**Wcf-webhttp**|  
    |[送信ハンドラー]|選択**BizTalkServerApplication**|  
    |送信パイプライン|選択**PassThruTransmit**|  
    |[受信パイプライン]|選択**AddNamespace**パイプラインの構成に、パイプラインに対して省略記号ボタンをクリックします。<br /><br /> -**ステージ 1: デコード**の**NamespaceBase**、入力`http://BtsSalesforceIntegration.QueryResult`です。 これで作成した QueryResult.xsd スキーマの名前空間[手順 3 b: Wcf-webhttp アダプターを使用して Salesforce から営業案件の詳細を取得](../core/step-3b-retrieve-opportunities-from-salesforce-using-the-wcf-webhttp-adapter.md)です。 ときに、 **AddNamespace**受信パイプラインが Salesforce からの応答を受け取るが応答メッセージにこの名前空間を追加します。 既定では、Salesforce からの応答メッセージには名前空間は含まれません。<br />     **NamespacePrefix**、入力`sf`です。<br />-**段階 2: 逆アセンブル**、既定値を受け入れるし、をクリックして**OK**です。|  
  
     [送信ポートのプロパティ] ダイアログ ボックスで、をクリックして**構成**に対して、ポートの種類。  
  
3.  [WCF-WebHttp トランスポートのプロパティ] ダイアログ ボックスで、次の値を指定します。  
  
    1.  **[全般]** タブで、次の操作を行います。  
  
        -   **アドレス (URI)**、入力`https://<Salesforce_instance_name>.salesforce.com/services/data/v24.0`です。 Salesforce のインスタンス名は、Salesforce.com ポータルを開いている場所のアドレス バーの https:// と Salesforce.com の間のテキストをコピーして取得できます。 たとえば、Salesforce ポータルの URL は*https://**na15**.salesforce.com/home/home.jsp*、Salesforce のインスタンス名は**na15**.  
  
        -   **HTTP メソッドと URL マッピング**ボックスで、次を指定します。  
  
            ```  
            <BtsHttpUrlMapping>  
            <Operation Method="GET" Url="/query?q={VAR}" />  
            </BtsHttpUrlMapping>  
            ```  
  
             この設定を使用する方法を次に示します: クエリを実行する Salesforce の詳細については、営業案件通知を取得するため、Salesforce REST エンドポイントに対する GET 操作を実行する必要があります (で指定されている、**アドレス**フィールド) を追加し、営業案件の詳細を取得するクエリ。 つまり、URL は次のようになります。  
  
            ```  
            https://na15.salesforce.com/services/data/v24.0/query?q=<query_string>  
            ```  
  
             一部として、Salesforce REST エンドポイントが既にあること、**アドレス (URI)**フィールドです。 したがっての一部として**HTTP メソッドと URL マッピング**GET メソッドを使用し、追加することを指定プロパティ、 **{VAR}**変数として。  
  
        -   **変数マッピング**ボックスで、クリックして**編集**です。 このボックスで指定する方法の値、 **{VAR}**実行時に変数を推測します。  
  
             [手順 3b.: Wcf-webhttp アダプターを使用して Salesforce から営業案件の詳細を取得](../core/step-3b-retrieve-opportunities-from-salesforce-using-the-wcf-webhttp-adapter.md)、結果としてクエリのプロパティを昇格したこと、 **PropertySchema.xsd**です。 使用して、**クエリ**URL の {VAR} 変数にその要素をマップすることによって、クエリ文字列を渡すには、そのスキーマ内の要素。  
  
             変数のマッピング ダイアログ ボックスで、**変数**列は、前に指定した、たとえば、変数の名前を一覧表示**VAR**です。 **プロパティ名**列、変数に渡されるクエリ文字列のある、昇格させたプロパティの名前を指定します。 このチュートリアルでは、そのプロパティの名前は**クエリ**です。 最後に、**プロパティ Namespace**、名前空間を指定、 **PropertySchema.xsd**、これは`https://BtsSalesforceIntegration.PropertySchema`します。 **[OK]**をクリックします。  
  
             ![WCF &#45; の [全般] タブWebHttp アダプター](../core/media/bts-sf-webhttp-general.jpg "BTS_SF_WebHttp_General")  
  
    2.  **セキュリティ**] タブの**セキュリティ モード**[**トランスポート**です。  
  
    3.  **動作** タブで作成したカスタム動作を使用して[ステップ 3 d: を有効にする BizTalk Server 送信し、Salesforce からのメッセージを受信する](../core/step-3d-enabling-biztalk-server-to-send-and-receive-messages-from-salesforce.md)Salesforce で認証します。 この動作を使用するには、次の操作を行います。  
  
        -   右クリック**EndpointBehavior**し、**拡張機能を追加**です。  
  
        -   **動作拡張機能の選択**ダイアログ ボックスで、 **Microsoft.BizTalk.Adapter.Behaviors.Demo.Salesforce**です。 この動作名は、machine.config に動作を追加する際に使用しました。  
  
        -   新しく追加した動作を選択して、次の値を指定します。  
  
            |||  
            |-|-|  
            |consumerKey (必須)|Salesforce アカウントのコンシューマー キーを指定します。 コンシューマー キーを取得するには、Salesforce の接続型アプリケーションで作成したに移動して[手順 2: Salesforce システムのセットアップ](../core/step-2-set-up-the-salesforce-system.md)です。|  
            |consumerSecret (必須)|コンシューマー、Salesforce からシークレットは、接続で作成したアプリケーション取得[手順 2: Salesforce システムのセットアップ](../core/step-2-set-up-the-salesforce-system.md)です。|  
            |パスワード (必須)|Salesforce アカウントのパスワードを指定します。 サード パーティのアプリケーションから Salesforce に接続するには、パスワードの後にセキュリティ トークンが続く形式のパスワードを指定する必要があります。 たとえば、パスワードが**パスワード**トークンが**XXXXXX**、入力する必要があります`passwordXXXXXX`です。|  
            |sessionTimeout|既定の値は「300」になっています。|  
            |Username (必須)|Salesforce デベロッパーのログイン アカウントを指定します。|  
  
             ![WCF &#45; の [動作] タブWebHttp アダプター](../core/media/bts-sf-webhttp-behavior.jpg "BTS_SF_WebHttp_Behavior")  
  
    4.  **メッセージ** タブの **送信メッセージ** ボックスの**動詞の本文を抑制**、入力`GET`です。 こうすることで、GET メソッドで Salesforce に送信されるリクエストにメッセージ ペイロードがないことを確認できます。  
  
    5.  をクリックして**OK**すべての開いているダイアログ ボックスを終了するまでです。  
  
### <a name="to-configure-the-wcf-sql-send-port"></a>WCF-SQL 送信ポートを構成するには  
  
1.  展開、 **SalesforceIntegration**アプリケーションを右クリックして**送信ポート**、 をポイント**新規**、クリックして**静的の一方向送信ポート**.  
  
2.  [送信ポートのプロパティ] ダイアログ ボックスで、次の値を指定します。  
  
    |||  
    |-|-|  
    |名前|入力`SendToSQL`です。|  
    |型|選択**WCF-SQL**|  
    |[送信ハンドラー]|選択**BizTalkServerApplication**|  
    |送信パイプライン|選択**[xmltransmit]**|  
  
     [送信ポートのプロパティ] ダイアログ ボックスで、をクリックして**構成**に対して、ポートの種類。  
  
3.  [WCF-SQL トランスポートのプロパティ ] ダイアログ ボックスで、次の値を指定します。  
  
    1.  **[全般]** タブで、次の操作を行います。  
  
        -   `Endpoint Address`をクリックして**構成**です。 **InitialCatalog**プロパティ、Salesforce 応答からのデータを入力する必要がありますテーブルを含むデータベース名を指定します。 このチュートリアルとこの値を入力してください。`Orders`です。 **サーバー**プロパティ、SQL Server データベースがインストールされているサーバー名を入力します。  
  
        -   **SOAP アクション ヘッダー**に挿入するために使用するアクションを指定、 **OrderDetails**テーブル。 入力する必要があります`TableOp/Insert/dbo/OrderDetails`です。  
  
    2.  [資格情報] タブで、内容をすべて空白のままにすると、アダプターは Windows 認証を使用して SQL Server データベースに接続します。 他の認証形式を使用したい場合は、関連する値を指定することもできます。  
  
    3.  をクリックして**OK**すべての開いているダイアログ ボックスを終了するまでです。  
  
### <a name="to-configure-the-biztalk-server-application"></a>BizTalk Server アプリケーションを構成するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、 **SalesforceIntegration**アプリケーション、およびクリック**構成**です。  
  
2.  アプリケーションの構成 ダイアログ ボックスで、選択、 **NotificationServiceClient**オーケストレーション、右側のウィンドウから次の操作。  
  
    1.  ホストで、次のように選択します。 **BizTalkServerApplication**です。  
  
    2.  論理受信ポート**SalesforceNotificationPort**を物理受信ポート、 **ReceiveOppNotification**です。  
  
    3.  論理送信ポートにマップする**SalesforceRESTInterface**を物理送信ポート、 **SalesforceREST**です。  
  
    4.  論理送信ポートにマップする**SendToSQL**を物理送信ポート、 **SendToSQL**です。  
  
     **[OK]**をクリックします。  
  
3.  右クリックし、 **SalesforceIntegration**アプリケーションをクリックして**開始**です。 起動、 **NotificationServiceClient**オーケストレーション、受信場所を有効にし、送信ポートを開始します。  
  
 このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールでオーケストレーションの論理ポートを物理ポートと関連付けて、ソリューションの構成を完了しました。