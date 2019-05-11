---
title: 手順 4:BizTalk Server ソリューションの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d60e6a82-51af-41e5-a755-5f337492ba2f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d2d0e2c04fb11432f85821ec3e5ac4b65c490b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392532"
---
# <a name="step-4-configure-the-biztalk-server-solution"></a>手順 4:BizTalk Server ソリューションを構成します。
前の手順で作成およびデプロイを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Salesforce の通知を受信するアプリケーションを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]し詳細をオンプレミスの SQL Server データベースに挿入します。 この手順でアプリケーションを構成します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 主にアプリケーションを構成するには、オーケストレーションで作成した論理ポートに対応する物理ポートを作成する必要があります。 また、物理ポートを論理ポートにバインドする必要もあります。 構成するのには、次の手順を実行します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション。  
  
- 構成要求-応答 Wcf-basichttprelay 受信場所で Salesforce から営業案件通知を受信します。  
  
- 受信した営業案件通知に関連する製品の詳細を取得するための Salesforce にクエリを送信する要求-応答 Wcf-webhttp 送信ポートを構成します。 この送信ポートは、Salesforce からも、クエリの応答を受信します。  
  
- Salesforce から、クエリの応答をオンプレミスの SQL Server データベースに挿入する一方向の WCF-SQL 送信ポートを構成します。  
  
- 構成、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーションで作成した物理ポートとオーケストレーションの論理ポートを関連付けることによって、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
### <a name="to-configure-the-wcf-basichttprelay-receive-location"></a>Wcf-basichttprelay 受信場所を構成するには  
  
1. 開く、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 [アプリケーション] ノードを展開し、検索、 **SalesforceIntegration**アプリケーション。 このアプリケーションをデプロイしたときに作成した、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Visual Studio からプロジェクト。  
  
2. 展開、 **SalesforceIntegration**アプリケーションを右クリックして**受信ポート**、 をポイント**新規**、順にクリックします**要求-応答受信ポート**. ポート名を指定`ReceiveOppNotification`左側のウィンドウから次のようにクリックします。**受信場所**します。  
  
3. 受信場所のプロパティ ダイアログ ボックスで、次の値を指定します。  
  
   |||  
   |-|-|  
   |名前|入力`ReceiveOppNotification`します。|  
   |型|選択**Wcf-basichttprelay**|  
   |受信ハンドラー|選択 **[biztalkserverapplication]**|  
   |[受信パイプライン]|選択**XMLReceive**|  
   |送信パイプライン|選択**PassThruTransmit**|  
  
    クリックして**構成**に対して、ポートの種類。  
  
4. Wcf-basichttprelay トランスポートのプロパティ ダイアログ ボックスで、次の値を指定します。  
  
   1. **全般** タブの**アドレス (URI)**、入力`https://btssalesforce.servicebus.windows.net/notifications/opportunity`です。 ここでは、 **btssalesforce**で作成した名前空間は、[手順 1。Service Bus の Namespace を作成する](../core/step-1-create-a-service-bus-namespace.md)します。 Salesforce でのワークフローの作成時に指定した同じ URL をここでは、指定した URL[手順 2。Salesforce システムを設定する](../core/step-2-set-up-the-salesforce-system.md)します。 営業案件のステージが Closed Won に設定するたびに Salesforce を送信する通知を URL にワークフローを設定する *<https://btssalesforce.servicebus.windows.net/notifications/opportunity>* します。 ここで、同じ URL の一部として受信場所の構成を指定します。 受信場所が有効になっていると、URL で指定されたリレー エンドポイントが作成[!INCLUDE[winazure](../includes/winazure-md.md)]です。  
  
   2. **セキュリティ** タブで、次を指定します。  
  
      -   **セキュリティ モード**を選択します**トランスポート**および**クライアント認証の種類をリレー**を選択します**None**します。  
  
      -   選択、**サービスの検出を有効にする**でサービスの動作を公開する チェック ボックス、[サービス レジストリ](http://msdn.microsoft.com/library/windowsazure/dd582704.aspx)します。 指定、**表示名**をレジストリにサービスを発行するの名前を示します。 設定することができます、**検出モード**パブリックまたはプライベートにします。 このチュートリアルでは、次のように設定します。**表示名**に`SF Outbound Notification`と**検出モード**に**パブリック**します。  
  
      -   アクセス制御サービス ボックスで、をクリックして**編集**します。 **アクセス制御サービス STS Uri**、入力`https://btssalesforce-sb.accesscontrol.windows.net/`します。 **発行者名**と**発行者キー**で保存した値を入力して[手順 1。Service Bus の Namespace を作成する](../core/step-1-create-a-service-bus-namespace.md)の**既定のユーザー**と**既定のキー**フィールド。  
  
   3. クリックして**OK**すべての開いているダイアログ ボックスを終了するまでです。  
  
### <a name="to-configure-the-wcf-webhttp-send-port"></a>Wcf-webhttp 送信ポートを構成するには  
  
1. 展開、 **SalesforceIntegration**アプリケーションを右クリックして**送信ポート**、 をポイント**新規**、順にクリックします**静的な送信請求-応答送信ポート**.  
  
2. 送信ポートのプロパティ ダイアログ ボックスで、次の値を指定します。  
  
   |||  
   |-|-|  
   |名前|入力`SalesforceREST`します。|  
   |型|選択**Wcf-webhttp**|  
   |送信ハンドラー|選択 **[biztalkserverapplication]**|  
   |送信パイプライン|選択**PassThruTransmit**|  
   |[受信パイプライン]|選択**AddNamespace**パイプラインを構成するパイプラインに対して省略記号ボタンをクリックします。<br /><br /> -**段階 1。デコード**の**NamespaceBase**、入力`http://BtsSalesforceIntegration.QueryResult`します。 これで作成した QueryResult.xsd スキーマの名前空間は、[手順 3 b:Wcf-webhttp アダプターを使用して Salesforce から営業案件の詳細を取得](../core/step-3b-retrieve-opportunities-from-salesforce-using-the-wcf-webhttp-adapter.md)します。 ときに、 **AddNamespace**受信パイプラインは、Salesforce から応答を受信、応答メッセージにこの名前空間を追加します。 既定では、Salesforce からの応答メッセージに任意の名前空間は含まれません。<br />     **NamespacePrefix**、入力`sf`します。<br />-**段階 2。逆アセンブル**既定値をそのまま使用し、クリックして**OK**します。|  
  
    [送信ポートのプロパティ] ダイアログ ボックスで、次のようにクリックします。**構成**に対して、ポートの種類。  
  
3. Wcf-webhttp トランスポートのプロパティ ダイアログ ボックスで、次の値を指定します。  
  
   1. **[全般]** タブで、次の操作を行います。  
  
      - **アドレス (URI)**、入力`https://<Salesforce_instance_name>.salesforce.com/services/data/v24.0`します。 Salesforce のインスタンス名を取得するには、ある Salesforce.com ポータルを開いてアドレス バーに https://、Salesforce.com の間のテキストをコピーします。 たとえば、Salesforce ポータルの URL が*https://*<em>na15</em>*.salesforce.com/home/home.jsp*、Salesforce のインスタンス名は**na15**.  
  
      - **HTTP メソッドと URL マッピング**ボックスで、次を指定します。  
  
        ```  
        <BtsHttpUrlMapping>  
        <Operation Method="GET" Url="/query?q={VAR}" />  
        </BtsHttpUrlMapping>  
        ```  
  
         この設定を使用する方法を次に示します: 営業案件通知の詳細を取得するために、Salesforce に照会する、Salesforce REST エンドポイントに対して GET 操作を実行する必要があります (で指定されている、**アドレス**フィールド) を追加し、営業案件の詳細を取得するクエリ。 そのため、URL のようになります。  
  
        ```  
        https://na15.salesforce.com/services/data/v24.0/query?q=<query_string>  
        ```  
  
         一部として、Salesforce REST エンドポイントが既にあること、**アドレス (URI)** フィールド。 そのための一部として**HTTP メソッドと URL マッピング**して GET メソッドを追加することに指定します、プロパティ、 **{VAR}** 変数として。  
  
      - **変数マッピング**ボックスで、**編集**します。 このボックスで指定する方法の値、 **{VAR}** 変数は、実行時に推測されます。  
  
         [手順 3 b:Wcf-webhttp アダプターを使用して Salesforce から営業案件の詳細を取得](../core/step-3b-retrieve-opportunities-from-salesforce-using-the-wcf-webhttp-adapter.md)、結果としてクエリのプロパティを昇格したこと、 **PropertySchema.xsd**します。 使用して、**クエリ**URL の {VAR} 変数にその要素をマップすることによって、クエリ文字列を渡すには、そのスキーマ内の要素。  
  
         変数のマッピング ダイアログ ボックスで、**変数**列は、前に指定した、たとえば、変数の名前を一覧表示**VAR**します。 **プロパティ名**列、変数に渡されるクエリ文字列のある、昇格させたプロパティの名前を指定します。 このチュートリアルではそのプロパティ名は**クエリ**します。 最後に、**プロパティ Namespace**、名前空間を指定、 **PropertySchema.xsd**、これは`https://BtsSalesforceIntegration.PropertySchema`します。 **[OK]** をクリックします。  
  
         ![WCF の [全般] タブ&#45;WebHttp アダプター](../core/media/bts-sf-webhttp-general.jpg "BTS_SF_WebHttp_General")  
  
   2. **セキュリティ** タブの**セキュリティ モード**を選択します**トランスポート**します。  
  
   3. **動作** タブで作成したカスタム動作を使用して[手順 3 d:BizTalk Server を有効にすると送信し、Salesforce からメッセージを受信する](../core/step-3d-enabling-biztalk-server-to-send-and-receive-messages-from-salesforce.md)Salesforce で認証します。 動作を使用するには、次の操作を行います。  
  
      -   右クリック **[endpointbehavior]** 選び**拡張機能の追加**します。  
  
      -   **動作拡張機能の選択**ダイアログ ボックスで、 **Microsoft.BizTalk.Adapter.Behaviors.Demo.Salesforce**します。 動作を machine.config ファイルに追加するときに、この動作名を使用していた。  
  
      -   新しく追加した動作を選択し、次の値を指定します。  
  
          |||  
          |-|-|  
          |consumerKey (必須)|Salesforce アカウントのコンシューマー キーを指定します。 コンシューマー キーを取得するで作成した、Salesforce の接続型アプリケーションに移動して[手順 2。Salesforce システムを設定する](../core/step-2-set-up-the-salesforce-system.md)します。|  
          |consumerSecret (必須)|Salesforce からシークレットのコンシューマーにで作成したアプリケーションが接続されている取得[手順 2。Salesforce システムを設定する](../core/step-2-set-up-the-salesforce-system.md)します。|  
          |パスワード (必須)|Salesforce アカウントのパスワードを指定します。 サード パーティ製アプリケーションから Salesforce に接続するには、セキュリティ トークンの後に形式のパスワードでパスワードを指定する必要があります。 たとえば、パスワードが**パスワード**トークンと**XXXXXX**、入力する必要があります`passwordXXXXXX`します。|  
          |sessionTimeout|これは、既定値は 300 です。|  
          |ユーザー名 (必須)|Salesforce デベロッパーのログイン アカウントを指定します。|  
  
           ![WCF の動作 タブ&#45;WebHttp アダプター](../core/media/bts-sf-webhttp-behavior.jpg "BTS_SF_WebHttp_Behavior")  
  
   4. **メッセージ**] タブの [**送信メッセージ**ボックスの**動詞の本文を抑制**、入力`GET`します。 これにより、GET メソッドはありませんメッセージ ペイロードで Salesforce に送信される要求です。  
  
   5. クリックして**OK**すべての開いているダイアログ ボックスを終了するまでです。  
  
### <a name="to-configure-the-wcf-sql-send-port"></a>WCF-SQL 送信ポートを構成するには  
  
1.  展開、 **SalesforceIntegration**アプリケーションを右クリックして**送信ポート**、 をポイント**新規**、順にクリックします**静的の一方向送信ポート**.  
  
2.  送信ポートのプロパティ ダイアログ ボックスで、次の値を指定します。  
  
    |||  
    |-|-|  
    |名前|入力`SendToSQL`します。|  
    |型|選択**WCF-SQL**|  
    |送信ハンドラー|選択 **[biztalkserverapplication]**|  
    |送信パイプライン|選択**XMLTransmit**|  
  
     [送信ポートのプロパティ] ダイアログ ボックスで、次のようにクリックします。**構成**に対して、ポートの種類。  
  
3.  WCF-SQL トランスポートのプロパティ ダイアログ ボックスで、次の値を指定します。  
  
    1.  **[全般]** タブで、次の操作を行います。  
  
        -   [ `Endpoint Address`、] をクリックして**構成**します。 **InitialCatalog**プロパティ、Salesforce 応答からデータを入力する必要がありますテーブルを含むデータベース名を指定します。 このチュートリアルとしては、この値を入力します。`Orders`します。 **Server**プロパティ、SQL Server データベースがインストールされているサーバー名を入力します。  
  
        -   **SOAP アクション ヘッダー**に挿入するために使用するアクションの指定、 **OrderDetails**テーブル。 入力する必要があります`TableOp/Insert/dbo/OrderDetails`します。  
  
    2.  資格情報 タブで、すべてのものを指定しない場合、アダプター Windows 認証を使用して、SQL Server データベースに接続します。 その他の形式の認証を使用する場合は、関連する値を指定できます。  
  
    3.  クリックして**OK**すべての開いているダイアログ ボックスを終了するまでです。  
  
### <a name="to-configure-the-biztalk-server-application"></a>BizTalk Server アプリケーションを構成するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックし、 **SalesforceIntegration**アプリケーション、およびクリック**構成**します。  
  
2. アプリケーションの構成 ダイアログ ボックスで、選択、 **NotificationServiceClient**オーケストレーション、右側のウィンドウから、次の操作を行います。  
  
   1. ホストで、次のように選択します。 **BizTalkServerApplication**します。  
  
   2. マップの論理受信ポート**SalesforceNotificationPort**を物理受信ポート、 **ReceiveOppNotification**します。  
  
   3. 論理送信ポートのマップ**SalesforceRESTInterface**を物理送信ポート、 **SalesforceREST**します。  
  
   4. 論理送信ポートのマップ**SendToSQL**を物理送信ポート、 **SendToSQL**します。  
  
      **[OK]** をクリックします。  
  
3. 右クリックし、 **SalesforceIntegration**アプリケーションとクリック**開始**します。 起動、 **NotificationServiceClient**オーケストレーション、受信場所を有効にし、送信ポートを開始します。  
  
   ソリューションの構成を完了しました、このトピックの「[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]オーケストレーションの論理ポートを物理ポートに関連付けることによって、管理コンソール。