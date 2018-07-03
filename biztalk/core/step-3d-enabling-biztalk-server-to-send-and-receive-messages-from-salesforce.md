---
title: '手順 3 d: Salesforce からのメッセージを送受信する BizTalk Server の有効化 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 470c4a72-1e97-4493-8958-33a13f793ffd
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ea447687ab6b5eeaacf990acb5467e3f67adc60
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991675"
---
# <a name="step-3d-enabling-biztalk-server-to-send-and-receive-messages-from-salesforce"></a><span data-ttu-id="d4f8c-102">手順 3 d: BizTalk Server で Salesforce からのメッセージの送受信を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-102">Step 3d: Enabling BizTalk Server to Send and Receive Messages from Salesforce</span></span>
<span data-ttu-id="d4f8c-103">REST インターフェイスを使用してメッセージを送信する際は、Salesforce で認証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-103">We must authenticate with Salesforce while sending messages using the REST interface.</span></span> <span data-ttu-id="d4f8c-104">Salesforce でサポートされている REST 呼び出しのための認証方法は、Salesforce の REST インターフェイスの起動に使用する WCF-WebHttp アダプターの既定では利用できません。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-104">The authentication methods for REST calls supported by Salesforce are not available out of the box with the WCF-WebHttp adapter, which we’ll use to invoke Salesforce’s REST interface.</span></span> <span data-ttu-id="d4f8c-105">そのため、カスタムの WCF エンドポイントの動作を作成し、Salesforce REST インターフェイスを起動するよう構成した WCF-WebHttp 送信アダプターにアタッチします。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-105">So, we’ll create a custom WCF endpoint behavior and then attach it to WCF-WebHttp send adapter that we’ll configure to invoke the Salesforce REST interface.</span></span>  
  
 <span data-ttu-id="d4f8c-106">同様に、Salesforce から受信する XML 応答には名前空間が含まれません。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-106">Similarly, the XML response received from Salesforce will not contain any namespace.</span></span> <span data-ttu-id="d4f8c-107">応答スキーマに対して応答メッセージを処理する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、応答メッセージにターゲットの名前空間を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-107">For [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to process the response message against the response schema, the response message must include the target namespace.</span></span> <span data-ttu-id="d4f8c-108">そのため、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] を使用してカスタムのパイプラインを作成し、応答メッセージに名前空間を追加します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-108">So, we’ll create a custom pipeline using the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] to add a namespace to the response message.</span></span> <span data-ttu-id="d4f8c-109">その後、このカスタムのパイプラインを、要求 - 応答の WCF-WebHttp 送信ポートの受信パイプラインとして使用します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-109">We’ll then use this custom pipeline as the receive pipeline for request-response WCF-WebHttp send port.</span></span>  
  
## <a name="add-a-custom-wcf-behavior-for-salesforce-authentication"></a><span data-ttu-id="d4f8c-110">Salesforce 認証用のカスタム WCF 動作の追加</span><span class="sxs-lookup"><span data-stu-id="d4f8c-110">Add a Custom WCF Behavior for Salesforce Authentication</span></span>  
 <span data-ttu-id="d4f8c-111">Salesforce には Salesforce で認証するクライアント アプリケーションのためのさまざまなオプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-111">Salesforce provides different options for client applications to authenticate with Salesforce.</span></span> <span data-ttu-id="d4f8c-112">どのような Salesforce の用語として使用して、[ユーザー名とパスワード](http://go.microsoft.com/fwlink/?LinkId=287082)フロー。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-112">We’ll use what Salesforce terms as the [Username-password](http://go.microsoft.com/fwlink/?LinkId=287082) flow.</span></span> <span data-ttu-id="d4f8c-113">WCF では、クライアント側で使用すると、作成[メッセージ インスペクタ](http://msdn.microsoft.com/library/aa717047\(v=VS.90\).aspx)送信される前に、または受信した後、メッセージを変更します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-113">On the client side, WCF enables you to create [Message Inspectors](http://msdn.microsoft.com/library/aa717047\(v=VS.90\).aspx) to alter messages before they are sent or after they are received.</span></span> <span data-ttu-id="d4f8c-114">メッセージ インスペクタはクライアント ランタイムの拡張機能であり、動作として構成します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-114">A message inspector is an extension to the client runtime and is configured as a behavior.</span></span> <span data-ttu-id="d4f8c-115">次に、動作は動作拡張機能の要素に追加されます。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-115">A behavior, in turn, is added to a behavior extension element.</span></span> <span data-ttu-id="d4f8c-116">この動作拡張機能の要素は要素名を付けて machine.config に登録され、WCF ポート上のカスタム動作として構成できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-116">This behavior extension element is registered in the machine.config with an element name, which makes it available to be configured as a custom behavior on a WCF port.</span></span> <span data-ttu-id="d4f8c-117">詳細については、次を参照してください。 [WCF をカスタムの動作で拡張](http://msdn.microsoft.com/magazine/cc163302.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-117">For more information, see [Extending WCF with Custom Behaviors](http://msdn.microsoft.com/magazine/cc163302.aspx).</span></span> <span data-ttu-id="d4f8c-118">この方法を用いて、Salesforce で認証を行うためのユーザー名 - 認証フローを組み込みます。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-118">We are going to use this approach to incorporate the username-authentication flow for authenticating with Salesforce.</span></span> <span data-ttu-id="d4f8c-119">主に次のような手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-119">The broad steps that we’ll follow are:</span></span>  
  
-   <span data-ttu-id="d4f8c-120">Salesforce 認証エンドポイントに HTTP POST 呼び出しを行い、アクセス トークンを受信するメッセージ インスペクタを作成します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-120">Create a message inspector that makes an HTTP POST call to the Salesforce authentication endpoint and receives an access token.</span></span> <span data-ttu-id="d4f8c-121">その後メッセージ インスペクタは、Salesforce に送信されるクエリ メッセージの認証ヘッダーの値として認証トークンを追加します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-121">The message inspector then adds the authentication token as the value of the Authorization header of the query message being sent to Salesforce.</span></span> <span data-ttu-id="d4f8c-122">さらに、メッセージ インスペクタは、受信した応答が XML 形式になるように、要求メッセージに Accept ヘッダーを追加します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-122">The message inspector also adds the Accept header to the request message so that the response received is in an XML format.</span></span> <span data-ttu-id="d4f8c-123">それ以外の場合は、Salesforce は既定の JSON 形式でメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-123">Otherwise, Salesforce sends the message in the default JSON format.</span></span>  
  
-   <span data-ttu-id="d4f8c-124">メッセージ インスペクタをクライアント エンドポイントに適用するためのエンドポイントの動作を作成します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-124">Create an endpoint behavior to apply the message inspector to the client endpoint.</span></span>  
  
-   <span data-ttu-id="d4f8c-125">エンドポイントの動作構成を可能にする動作拡張機能の要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-125">Create a behavior extension element to enable configuration of the endpoint behavior.</span></span>  
  
#### <a name="to-create-a-message-inspector"></a><span data-ttu-id="d4f8c-126">メッセージ インスペクタを作成するには</span><span class="sxs-lookup"><span data-stu-id="d4f8c-126">To create a message inspector</span></span>  
  
1. <span data-ttu-id="d4f8c-127">一部として、 **BtsSalesforceIntegration** Visual Studio で、ソリューションは、c# クラス ライブラリを作成します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-127">As part of the **BtsSalesforceIntegration** solution in Visual Studio, create a C# Class Library.</span></span> <span data-ttu-id="d4f8c-128">名前を付けます`Microsoft.BizTalk.Adapter.Behaviors`し、次の名前空間を追加します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-128">Name it `Microsoft.BizTalk.Adapter.Behaviors` and add the following namespaces:</span></span>  
  
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
  
2. <span data-ttu-id="d4f8c-129">ソリューション エクスプローラーから、`System.ServiceModel`、`System.Web.Extensions`、`System.Configuration` への参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-129">From the Solution Explorer, add references to `System.ServiceModel`, `System.Web.Extensions`, and `System.Configuration`.</span></span>  
  
3. <span data-ttu-id="d4f8c-130">次のプロパティを持つクラス `SalesforceOAuthToken` を追加します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-130">Add a class `SalesforceOAuthToken` with the following properties.</span></span> <span data-ttu-id="d4f8c-131">このクラスは、Salesforce から受信する認証トークンを表しています。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-131">This class represents the authorization token that is received from Salesforce.</span></span>  
  
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
  
4. <span data-ttu-id="d4f8c-132">`SalesforceRESTSecurityBehavior` と `IClientMessageInspector` を実装するクラス `IEndpointBehavior` を追加します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-132">Add a class `SalesforceRESTSecurityBehavior` that implements the `IClientMessageInspector` and the `IEndpointBehavior`.</span></span> <span data-ttu-id="d4f8c-133">このクラスは `HttpPost()` メソッドおよび `FetchOAuthToken()` メソッドを含みます。これらのメソッドは Salesforce 認証エンドポイントに対して HTTP POST 呼び出しを行い、認証トークンを抽出します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-133">This class includes the `HttpPost()` and `FetchOAuthToken()` methods that make an HTTP POST call to the Salesforce authentication endpoint to retrieve the authorization token.</span></span>  
  
    <span data-ttu-id="d4f8c-134">`SalesforceRESTSecurityBehavior` クラスは `IClientMessageInspector` インターフェイスを実装することから、`AfterReceiveReply()` と `BeforeSendRequest()` の 2 つのメソッドを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-134">Because the `SalesforceRESTSecurityBehavior` class implements the `IClientMessageInspector` interface, it must implement the two methods, `AfterReceiveReply()` and `BeforeSendRequest()`.</span></span> <span data-ttu-id="d4f8c-135">このシナリオでは、`AfterReceiverReply()` メソッドに対しては何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-135">For this scenario we do not need to do anything as part of the `AfterReceiverReply()` method.</span></span> <span data-ttu-id="d4f8c-136">ただし、`BeforeSendRequest()` メソッドは `FetchOAuthToken()` メソッドを呼び出し、このメソッドは `HttpPost()` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-136">However, the `BeforeSendRequest()` method invokes the `FetchOAuthToken()` method, which in turn calls the `HttpPost()` method.</span></span> <span data-ttu-id="d4f8c-137">その後、`BeforeSendRequest()` メソッドはメッセージ ヘッダーの一部として認証トークンを追加します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-137">The `BeforeSendRequest()` method then adds the authorization token as part of the message header.</span></span> <span data-ttu-id="d4f8c-138">さらに追加、 **Accept**ヘッダーを Salesforce から受信した応答が XML 形式であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-138">It also adds the **Accept** header to ensure that that the response received from Salesforce is in an XML format.</span></span>  
  
    <span data-ttu-id="d4f8c-139">`IEndpointBehavior` の実装では、単にメッセージ インスペクタがクライアントのエンドポイントの動作に追加されます。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-139">The `IEndpointBehavior` implementation simply adds the message inspector class to the client endpoint behavior.</span></span>  
  
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
  
5. <span data-ttu-id="d4f8c-140">前の手順では、クライアント エンドポイントにメッセージ インスペクタを適用する動作のクラスを作成しました。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-140">In the previous step we created a behavior class that applies the message inspector to the client endpoint.</span></span> <span data-ttu-id="d4f8c-141">次に、この動作で Salesforce に要求メッセージを送信する WCF-WebHttp アダプターを構成できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-141">We now need to make this behavior available to the configuration experience for the WCF-WebHttp adapter that will send the request message to Salesforce.</span></span> <span data-ttu-id="d4f8c-142">この動作を構成に使用できるようにするには、次の 2 つを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-142">To make this behavior available for configuration we need to do two things:</span></span>  
  
   - <span data-ttu-id="d4f8c-143">`BehaviorExtensionElement` から派生するクラスを作成する</span><span class="sxs-lookup"><span data-stu-id="d4f8c-143">Create a class that derives from the `BehaviorExtensionElement`</span></span>  
  
   - <span data-ttu-id="d4f8c-144">BehavaiorExtensionElement を登録、\<拡張\>\\< behaviorExtensions\>要素名を使用して、machine.config 内の要素。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-144">Register your BehavaiorExtensionElement in the \<extensions\>\\<behaviorExtensions\> element in the machine.config using an element name.</span></span>  
  
     <span data-ttu-id="d4f8c-145">さらに、WCF-WebHttp アダプターの構成 UI から使用できるように、このクラスに構成プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-145">We’ll also add configuration properties to this class so that they are available from the WCF-WebHttp adapter configuration UI.</span></span>  
  
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
  
6. <span data-ttu-id="d4f8c-146">厳密な名前のキー ファイルをプロジェクトに追加し、プロジェクトを構築します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-146">Add a strong name key file to the project and build the project.</span></span> <span data-ttu-id="d4f8c-147">プロジェクトが正常に構築されたら、アセンブリ `Microsoft.BizTalk.Adapter.Behaviors` をGAC に追加します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-147">Once the project builds successfully, add the assembly `Microsoft.BizTalk.Adapter.Behaviors` to the GAC.</span></span>  
  
7. <span data-ttu-id="d4f8c-148">次のエントリを、System.ServiceModel\Extensions\BehaviorExtensions にある machine.config に追加します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-148">Add the following entry in the machine.config under System.ServiceModel\Extensions\BehaviorExtensions.</span></span>  
  
   ```  
   <add name="Microsoft.BizTalk.Adapter.Behaviors.Demo.Salesforce" type="Microsoft.BizTalk.Adapter.Behaviors.SalesforceRESTBehaviorElement, Microsoft.BizTalk.Adapter.Behaviors, Version=1.0.0.0, Culture=neutral, PublicKeyToken=45bd7fe67ef032db"/>  
   ```  
  
    <span data-ttu-id="d4f8c-149">GAC からアセンブリ用の公開キー トークンを抽出します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-149">You can retrieve the public key token for the assembly from the GAC.</span></span> <span data-ttu-id="d4f8c-150">また、このアプリケーションを 64 ビット コンピューターで作成する場合は、machine.config の 32 ビットおよび 64 ビット バージョンの両方にこのエントリを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-150">Also, if you are creating this application on a 64-bit computer, you must add this entry to both 32-bit and 64-bit versions of the machine.config.</span></span>  
  
## <a name="add-a-custom-pipeline-to-add-namespace-to-the-salesforce-response"></a><span data-ttu-id="d4f8c-151">Salesforce 応答に名前空間を追加するためのカスタム パイプラインを追加する</span><span class="sxs-lookup"><span data-stu-id="d4f8c-151">Add a Custom Pipeline to Add Namespace to the Salesforce Response</span></span>  
 <span data-ttu-id="d4f8c-152">Salesforce から受け取る応答には名前空間が含まれません。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-152">The response received from Salesforce does not include a namespace.</span></span> <span data-ttu-id="d4f8c-153">ただし、応答スキーマ (QueryResult.xsd) に対して応答メッセージを処理するには、Salesforce 応答に名前空間を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-153">However, to process the response message against the response schema (QueryResult.xsd) we must include the namespace in the Salesforce response.</span></span> <span data-ttu-id="d4f8c-154">このセクションでは、カスタム パイプラインを作成し、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] に同梱のカスタム パイプライン コンポーネントを使用して、応答メッセージに名前空間を追加します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-154">In this section, we create a custom pipeline and use a custom pipeline component shipped with [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] to add a namespace to the response message.</span></span> <span data-ttu-id="d4f8c-155">このカスタム パイプラインは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーションとともに展開され、WCF-WebHttp アダプターの構成の際に、受信パイプラインとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-155">This custom pipeline is deployed with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application and will be used as the receive pipeline while configuring the WCF-WebHttp adapter.</span></span>  
  
 <span data-ttu-id="d4f8c-156">ここでの手順を実行する前に、このアプリケーションを作成するコンピューターに [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] がインストールされ、構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-156">Before performing the steps in this procedure, ensure that [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] is installed and configured on the computer where you are creating this application.</span></span>  
  
#### <a name="to-add-a-custom-pipeline"></a><span data-ttu-id="d4f8c-157">カスタム パイプラインを追加するには</span><span class="sxs-lookup"><span data-stu-id="d4f8c-157">To add a custom pipeline</span></span>  
  
1. <span data-ttu-id="d4f8c-158">内で、 **BtsSalesforceIntegration**ソリューションでは、新しい作成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-158">Within the **BtsSalesforceIntegration** solution, create a new [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span> <span data-ttu-id="d4f8c-159">プロジェクトに名前を`CustomPipeline`します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-159">Name the project `CustomPipeline`.</span></span>  
  
2. <span data-ttu-id="d4f8c-160">内で、 **CustomPipeline**プロジェクトに、新しい受信パイプラインを追加します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-160">Within the **CustomPipeline** project, add a new receive pipeline.</span></span> <span data-ttu-id="d4f8c-161">パイプラインの名前を`AddNamespace.btp`します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-161">Name the pipeline as `AddNamespace.btp`.</span></span>  
  
3. <span data-ttu-id="d4f8c-162">内で、**デコード**、ツールボックスから、パイプラインのステージをドラッグ アンド ドロップ、 **ESB 追加 Namespace**パイプライン コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-162">Within the **Decode** stage of the pipeline, from the toolbox, drag and drop the **ESB Add Namespace** pipeline component.</span></span> <span data-ttu-id="d4f8c-163">内で、**逆アセンブル**ステージにドラッグ アンド ドロップ、 **XML 逆アセンブラー**パイプライン コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-163">Within the **Disassemble** stage, drag and drop the **XML disassembler** pipeline component.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d4f8c-164">場合、 **ESB 追加 Namespace**パイプライン コンポーネントはツールボックスに表示されない、それを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-164">If the **ESB Add Namespace** pipeline component is not listed in the toolbox, you can add it.</span></span> <span data-ttu-id="d4f8c-165">右クリックし、 **BizTalk パイプライン コンポーネント**タブをクリックし、をクリックし、**アイテムの選択**します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-165">Right-click the **BizTalk Pipeline Components** tab, and then click **Choose Items**.</span></span> <span data-ttu-id="d4f8c-166">**ツールボックス アイテムの選択**ダイアログ ボックスで、をクリックして、 **BizTalk パイプライン コンポーネント** タブで、チェック ボックスをオン**ESB 追加 Namespace**コンポーネント、をクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-166">In the **Choose Toolbox Items** dialog box, click the **BizTalk Pipeline Components** tab, select the check box for **ESB Add Namespace** component, and then click **OK**.</span></span>  
  
4. <span data-ttu-id="d4f8c-167">厳密な名前のキー ファイルをプロジェクトに追加し、プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-167">Add a strong name key file to the project and save the project.</span></span>  
  
5. <span data-ttu-id="d4f8c-168">右クリックし、 **CustomPipeline**順に選択して**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-168">Right-click the **CustomPipeline** project and select **Properties**.</span></span> <span data-ttu-id="d4f8c-169">**展開** タブの**アプリケーション名**、入力`SalesforceIntegration`します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-169">In the **Deployment** tab, for **Application Name**, enter `SalesforceIntegration`.</span></span>  
  
6. <span data-ttu-id="d4f8c-170">プロジェクトへの変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-170">Save changes to the project.</span></span>  
  
   <span data-ttu-id="d4f8c-171">このトピックでは、Salesforce で認証するためのカスタム動作を追加し、Salesforce 応答に名前空間を追加するためのカスタム パイプラインを追加しました。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-171">In this topic, added a custom behavior to authenticate with Salesforce and a custom pipeline to add a namespace to the Salesforce response.</span></span> <span data-ttu-id="d4f8c-172">これらのカスタム コンポーネントは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで物理ポートを構成する際に使用します。</span><span class="sxs-lookup"><span data-stu-id="d4f8c-172">We’ll use these custom components while configuring the physical ports in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4f8c-173">参照</span><span class="sxs-lookup"><span data-stu-id="d4f8c-173">See Also</span></span>  
 [<span data-ttu-id="d4f8c-174">手順 3: Visual Studio での BizTalk Server ソリューションの作成</span><span class="sxs-lookup"><span data-stu-id="d4f8c-174">Step 3: Create the BizTalk Server Solution in Visual Studio</span></span>](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)