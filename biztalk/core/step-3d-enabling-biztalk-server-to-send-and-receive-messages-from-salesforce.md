---
title: "3d をステップ: BizTalk Server で Salesforce からのメッセージの送受信を有効にする |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 470c4a72-1e97-4493-8958-33a13f793ffd
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c38a58e376bbc8908ff0fe578aa54cbb009c58d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3d-enabling-biztalk-server-to-send-and-receive-messages-from-salesforce"></a>BizTalk Server で Salesforce からのメッセージの送受信を有効にする手順 3 d:
REST インターフェイスを使用してメッセージを送信する際は、Salesforce で認証する必要があります。 Salesforce でサポートされている REST 呼び出しのための認証方法は、Salesforce の REST インターフェイスの起動に使用する WCF-WebHttp アダプターの既定では利用できません。 そのため、カスタムの WCF エンドポイントの動作を作成し、Salesforce REST インターフェイスを起動するよう構成した WCF-WebHttp 送信アダプターにアタッチします。  
  
 同様に、Salesforce から受信する XML 応答には名前空間が含まれません。 応答スキーマに対して応答メッセージを処理する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、応答メッセージにターゲットの名前空間を含める必要があります。 そのため、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] を使用してカスタムのパイプラインを作成し、応答メッセージに名前空間を追加します。 その後、このカスタムのパイプラインを、要求 - 応答の WCF-WebHttp 送信ポートの受信パイプラインとして使用します。  
  
## <a name="add-a-custom-wcf-behavior-for-salesforce-authentication"></a>Salesforce 認証用のカスタム WCF 動作の追加  
 Salesforce には Salesforce で認証するクライアント アプリケーションのためのさまざまなオプションが用意されています。 として Salesforce 用語が使用されます、[ユーザー名とパスワード](http://go.microsoft.com/fwlink/?LinkId=287082)フローします。 WCF では、クライアント側で使用すると、作成[メッセージ インスペクタ](http://msdn.microsoft.com/library/aa717047\(v=VS.90\).aspx)送信される前に、または受信した後にメッセージを変更します。 メッセージ インスペクタはクライアント ランタイムの拡張機能であり、動作として構成します。 次に、動作は動作拡張機能の要素に追加されます。 この動作拡張機能の要素は要素名を付けて machine.config に登録され、WCF ポート上のカスタム動作として構成できるようになります。 詳細については、次を参照してください。[をカスタム動作で WCF の拡張](http://msdn.microsoft.com/magazine/cc163302.aspx)です。 この方法を用いて、Salesforce で認証を行うためのユーザー名 - 認証フローを組み込みます。 主に次のような手順を実行します。  
  
-   Salesforce 認証エンドポイントに HTTP POST 呼び出しを行い、アクセス トークンを受信するメッセージ インスペクタを作成します。 その後メッセージ インスペクタは、Salesforce に送信されるクエリ メッセージの認証ヘッダーの値として認証トークンを追加します。 さらに、メッセージ インスペクタは、受信した応答が XML 形式になるように、要求メッセージに Accept ヘッダーを追加します。 それ以外の場合は、Salesforce は既定の JSON 形式でメッセージを送信します。  
  
-   メッセージ インスペクタをクライアント エンドポイントに適用するためのエンドポイントの動作を作成します。  
  
-   エンドポイントの動作構成を可能にする動作拡張機能の要素を作成します。  
  
#### <a name="to-create-a-message-inspector"></a>メッセージ インスペクタを作成するには  
  
1.  一部として、 **BtsSalesforceIntegration** Visual Studio で、ソリューションは、c# クラス ライブラリを作成します。 名前を付けます`Microsoft.BizTalk.Adapter.Behaviors`し、次の名前空間を追加します。  
  
    ```  
    using System.ServiceModel.Description;  
    using System.ServiceModel.Dispatcher;  
    using System.ServiceModel.Channels;  
    using System.Xml;  
    using System.Net;  
    using System.IO;  
    using System.ServiceModel.Configuration;  
    using System.Configuration;  
    using System.Web.Script.Serialization;  
    ```  
  
2.  ソリューション エクスプローラーから、`System.ServiceModel`、`System.Web.Extensions`、`System.Configuration` への参照を追加します。  
  
3.  次のプロパティを持つクラス `SalesforceOAuthToken` を追加します。 このクラスは、Salesforce から受信する認証トークンを表しています。  
  
    ```  
    public class SalesforceOAuthToken  
    {  
        public string id { get; set; }  
        public string issued_at { get; set; }  
        public string refresh_token { get; set; }  
        public string instance_url { get; set; }  
        public string signature { get; set; }  
        public string access_token { get; set; }  
    }  
    ```  
  
4.  `SalesforceRESTSecurityBehavior` と `IClientMessageInspector` を実装するクラス `IEndpointBehavior` を追加します。 このクラスは `HttpPost()` メソッドおよび `FetchOAuthToken()` メソッドを含みます。これらのメソッドは Salesforce 認証エンドポイントに対して HTTP POST 呼び出しを行い、認証トークンを抽出します。  
  
     `SalesforceRESTSecurityBehavior` クラスは `IClientMessageInspector` インターフェイスを実装することから、`AfterReceiveReply()` と `BeforeSendRequest()` の 2 つのメソッドを実装する必要があります。 このシナリオでは、`AfterReceiverReply()` メソッドに対しては何もする必要はありません。 ただし、`BeforeSendRequest()` メソッドは `FetchOAuthToken()` メソッドを呼び出し、このメソッドは `HttpPost()` メソッドを呼び出します。 その後、`BeforeSendRequest()` メソッドはメッセージ ヘッダーの一部として認証トークンを追加します。 さらに、 **Accept** Salesforce から受信した応答が XML 形式であることを確認するヘッダー。  
  
     `IEndpointBehavior` の実装では、単にメッセージ インスペクタがクライアントのエンドポイントの動作に追加されます。  
  
    ```  
    public class SalesforceRESTSecurityBehavior : IClientMessageInspector, IEndpointBehavior  
    {  
        // Some constants  
        private static string SalesforceAuthEndpoint = "https://login.salesforce.com/services/oauth2/token";  
  
        // Configuration Properties  
        private string username_;  
        private string password_;  
        private string consumerKey_;  
        private string consumerSecret_;  
        private int sessionTimeout_;  
  
        // Private Properties  
        private SalesforceOAuthToken token_;  
        private DateTime tokenExpiryTime_;  
  
        public SalesforceRESTSecurityBehavior(  
            string username,  
            string password,  
            string consumerKey,  
            string consumerSecret,  
            int sessionTimeout)  
        {  
            this.username_ = username;  
            this.password_ = password;  
            this.consumerKey_ = consumerKey;  
            this.consumerSecret_ = consumerSecret;  
            this.sessionTimeout_ = sessionTimeout;  
        }  
  
        private void FetchOAuthToken()  
        {  
            if ((tokenExpiryTime_ == null) || (tokenExpiryTime_.CompareTo(DateTime.Now) <= 0))  
            {  
                StringBuilder body = new StringBuilder();  
                body.Append("grant_type=password&")  
                    .Append("client_id=" + consumerKey_ + "&")  
                    .Append("client_secret=" + consumerSecret_ + "&")  
                    .Append("username=" + username_ + "&")  
                    .Append("password=" + password_);  
  
                string result;  
  
                try  
                {  
                    result = HttpPost(SalesforceAuthEndpoint, body.ToString());  
                }  
                catch (WebException)  
                {  
                    // do something  
                    return;  
                }  
  
                // Convert the JSON response into a token object  
                JavaScriptSerializer ser = new JavaScriptSerializer();  
                this.token_ = ser.Deserialize<SalesforceOAuthToken>(result);  
                this.tokenExpiryTime_ = DateTime.Now.AddSeconds(this.sessionTimeout_);  
            }  
        }  
  
        public string HttpPost(string URI, string Parameters)  
        {  
            WebRequest req = WebRequest.Create(URI);  
            req.ContentType = "application/x-www-form-urlencoded";  
            req.Method = "POST";  
  
            // Add parameters to post  
            byte[] data = Encoding.ASCII.GetBytes(Parameters);  
            req.ContentLength = data.Length;  
            System.IO.Stream os = req.GetRequestStream();  
            os.Write(data, 0, data.Length);  
            os.Close();  
  
            // Do the post and get the response.  
            System.Net.WebResponse resp = null;  
            resp = req.GetResponse();  
  
            StreamReader sr = new StreamReader(resp.GetResponseStream());  
            return sr.ReadToEnd().Trim();  
        }  
        #region IClientMessageInspector  
  
        public void AfterReceiveReply(ref System.ServiceModel.Channels.Message reply, object correlationState)  
        {  
            // do nothing  
        }  
        public object BeforeSendRequest(ref System.ServiceModel.Channels.Message request, System.ServiceModel.IClientChannel channel)  
        {  
            // We are going to send a request to Salesforce  
            // Overview:  
            // This behavior will do the following:  
            // (1) Fetch Token from Salesforce, if required  
            // (2) Add the token to the message  
            // (3) Insert an Http Accept header so we get XML data in response, instead of JSON, which is default  
            // Reference: http://www.salesforce.com/us/developer/docs/api_rest/index.htm  
            //  
            // (1) Authentication with Salesforce  
            // (2) The token is added to the HTTP Authorization Header   
            // (3) Add the Accept Header  
            //  
  
            HttpRequestMessageProperty httpRequest = null;  
  
            if (request.Properties.ContainsKey(HttpRequestMessageProperty.Name))  
            {  
                httpRequest = request.Properties[HttpRequestMessageProperty.Name] as HttpRequestMessageProperty;  
            }  
  
            if (httpRequest == null)  
            {  
                // NOTE: Ideally, we shouldn’t get here for WebHttp  
                httpRequest = new HttpRequestMessageProperty()  
                {  
                    Method = "GET",  
                    SuppressEntityBody = true  
                };  
                request.Properties.Add(HttpRequestMessageProperty.Name, httpRequest);  
            }  
  
            WebHeaderCollection headers = httpRequest.Headers;  
            FetchOAuthToken();  
  
            headers.Add(HttpRequestHeader.Authorization, "OAuth " + this.token_.access_token);  
            headers.Add(HttpRequestHeader.Accept, "application/xml");  
  
            return null;  
        }  
  
        #endregion IClientMessageInspector  
  
        #region IEndpointBehavior  
  
        public void AddBindingParameters(ServiceEndpoint endpoint, System.ServiceModel.Channels.BindingParameterCollection bindingParameters)  
        {  
            // do nothing  
        }  
  
        public void ApplyClientBehavior(ServiceEndpoint endpoint, ClientRuntime clientRuntime)  
        {  
            clientRuntime.MessageInspectors.Add(this);  
        }  
  
        public void ApplyDispatchBehavior(ServiceEndpoint endpoint, EndpointDispatcher endpointDispatcher)  
        {  
            // do nothing  
        }  
  
        public void Validate(ServiceEndpoint endpoint)  
        {  
            // do nothing  
        }  
  
        #endregion IEndpointBehavior  
    }  
    ```  
  
5.  前の手順では、クライアント エンドポイントにメッセージ インスペクタを適用する動作のクラスを作成しました。 次に、この動作で Salesforce に要求メッセージを送信する WCF-WebHttp アダプターを構成できるようにする必要があります。 この動作を構成に使用できるようにするには、次の 2 つを実行する必要があります。  
  
    -   `BehaviorExtensionElement` から派生するクラスを作成する  
  
    -   BehavaiorExtensionElement を登録、\<拡張子 >\\< behaviorExtensions\>要素名を使用して、machine.config 内の要素。  
  
     さらに、WCF-WebHttp アダプターの構成 UI から使用できるように、このクラスに構成プロパティを追加します。  
  
    ```  
    public class SalesforceRESTBehaviorElement : BehaviorExtensionElement  
    {  
        public override Type BehaviorType  
        {  
            get { return typeof(SalesforceRESTSecurityBehavior); }  
        }  
  
        protected override object CreateBehavior()  
        {  
            return new SalesforceRESTSecurityBehavior(Username, Password, ConsumerKey, ConsumerSecret, SessionTimeout);  
        }  
  
        [ConfigurationProperty("username", IsRequired = true)]  
        public string Username  
        {  
            get { return (string)this["username"]; }  
            set { this["username"] = value; }  
        }  
  
        [ConfigurationProperty("password", IsRequired = true)]  
        public string Password  
        {  
            get { return (string)this["password"]; }  
            set { this["password"] = value; }  
        }  
  
        [ConfigurationProperty("consumerKey", IsRequired = true)]  
        public string ConsumerKey  
        {  
            get { return (string)this["consumerKey"]; }  
            set { this["consumerKey"] = value; }  
        }  
  
        [ConfigurationProperty("consumerSecret", IsRequired = true)]  
        public string ConsumerSecret  
        {  
            get { return (string)this["consumerSecret"]; }  
            set { this["consumerSecret"] = value; }  
        }  
  
        [ConfigurationProperty("sessionTimeout", IsRequired = false, DefaultValue = 300)]  
        public int SessionTimeout  
        {  
            get { return (int)this["sessionTimeout"]; }  
            set { this["sessionTimeout"] = value; }  
        }  
    }  
    ```  
  
6.  厳密な名前のキー ファイルをプロジェクトに追加し、プロジェクトを構築します。 プロジェクトが正常に構築されたら、アセンブリ `Microsoft.BizTalk.Adapter.Behaviors` をGAC に追加します。  
  
7.  次のエントリを、System.ServiceModel\Extensions\BehaviorExtensions にある machine.config に追加します。  
  
    ```  
    <add name="Microsoft.BizTalk.Adapter.Behaviors.Demo.Salesforce" type="Microsoft.BizTalk.Adapter.Behaviors.SalesforceRESTBehaviorElement, Microsoft.BizTalk.Adapter.Behaviors, Version=1.0.0.0, Culture=neutral, PublicKeyToken=45bd7fe67ef032db"/>  
    ```  
  
     GAC からアセンブリ用の公開キー トークンを抽出します。 また、このアプリケーションを 64 ビット コンピューターで作成する場合は、machine.config の 32 ビットおよび 64 ビット バージョンの両方にこのエントリを追加する必要があります。  
  
## <a name="add-a-custom-pipeline-to-add-namespace-to-the-salesforce-response"></a>Salesforce 応答に名前空間を追加するためのカスタム パイプラインを追加する  
 Salesforce から受け取る応答には名前空間が含まれません。 ただし、応答スキーマ (QueryResult.xsd) に対して応答メッセージを処理するには、Salesforce 応答に名前空間を含める必要があります。 このセクションでは、カスタム パイプラインを作成し、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] に同梱のカスタム パイプライン コンポーネントを使用して、応答メッセージに名前空間を追加します。 このカスタム パイプラインは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーションとともに展開され、WCF-WebHttp アダプターの構成の際に、受信パイプラインとして使用されます。  
  
 ここでの手順を実行する前に、このアプリケーションを作成するコンピューターに [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] がインストールされ、構成されていることを確認します。  
  
#### <a name="to-add-a-custom-pipeline"></a>カスタム パイプラインを追加するには  
  
1.  内で、 **BtsSalesforceIntegration**ソリューションでは、新規作成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクト。 プロジェクトに名前を`CustomPipeline`です。  
  
2.  内で、 **CustomPipeline**プロジェクトに新しい受信パイプラインを追加します。 パイプラインの名前`AddNamespace.btp`です。  
  
3.  内で、**デコード**、ツールボックスから、パイプラインのステージにドラッグ アンド ドロップ、 **ESB 追加 Namespace**パイプライン コンポーネントです。 内で、**逆アセンブル**ステージにドラッグ アンド ドロップ、 **XML 逆アセンブラー**パイプライン コンポーネントです。  
  
    > [!NOTE]
    >  場合、 **ESB 追加 Namespace**パイプライン コンポーネントがツールボックスに表示されていない、追加することができます。 右クリックし、 **BizTalk パイプライン コンポーネント** タブをクリックして**アイテムの選択**です。 **ツールボックス アイテムの選択**ダイアログ ボックスで、をクリックして、 **BizTalk パイプライン コンポーネント** タブで、チェック ボックスをオン**ESB 追加 Namespace**コンポーネント、をクリックして**OK**です。  
  
4.  厳密な名前のキー ファイルをプロジェクトに追加し、プロジェクトを保存します。  
  
5.  右クリックし、 **CustomPipeline**プロジェクトし、選択**プロパティ**です。 **展開** タブの**アプリケーション名**、入力`SalesforceIntegration`です。  
  
6.  プロジェクトへの変更を保存します。  
  
 このトピックでは、Salesforce で認証するためのカスタム動作を追加し、Salesforce 応答に名前空間を追加するためのカスタム パイプラインを追加しました。 これらのカスタム コンポーネントは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで物理ポートを構成する際に使用します。  
  
## <a name="see-also"></a>参照  
 [手順 3: Visual Studio での BizTalk Server ソリューションを作成します。](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)