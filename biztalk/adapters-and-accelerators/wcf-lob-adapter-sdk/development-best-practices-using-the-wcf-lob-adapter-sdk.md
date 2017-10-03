---
title: "WCF LOB Adapter SDK を使用して、開発のベスト プラクティス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8ea3a13b-e41f-4920-bf0d-26f7bb145aa3
caps.latest.revision: "28"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9786896a4a5983a438dd855dcc858ba4485cbc1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="development-best-practices-using-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="84f19-102">WCF LOB Adapter SDK を使用して、開発のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="84f19-102">Development best practices using the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="84f19-103">このトピックの「ベスト プラクティスを使用するには、アプリケーションおよびアダプターを向上させるためにします。</span><span class="sxs-lookup"><span data-stu-id="84f19-103">You can use the best practices in this topic to improve your applications and adapters.</span></span>  
  
## <a name="call-abort-before-close-on-channel-exception"></a><span data-ttu-id="84f19-104">チャネルの例外で終了する前に中止を呼び出す</span><span class="sxs-lookup"><span data-stu-id="84f19-104">Call Abort Before Close on Channel Exception</span></span>  
 <span data-ttu-id="84f19-105">WCF チャネル モデルを使用するアプリケーションを記述するときに呼び出す必要は`IRequestChannel.Abort`呼び出す前に`ChannelFactory.Close`です。</span><span class="sxs-lookup"><span data-stu-id="84f19-105">When you write an application that uses the WCF channel model, you should call `IRequestChannel.Abort` before calling `ChannelFactory.Close`.</span></span> <span data-ttu-id="84f19-106">そうしない場合`ChannelFactory.Close`例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="84f19-106">If you do not, `ChannelFactory.Close` throws an exception.</span></span>  
  
 <span data-ttu-id="84f19-107">次の例では、チャネルの操作が try ブロックと catch ブロック内でしようとしました。</span><span class="sxs-lookup"><span data-stu-id="84f19-107">In the following example, channel operations are attempted within a try/catch block.</span></span> <span data-ttu-id="84f19-108">例外が発生する場合、チャネルは中止されます。</span><span class="sxs-lookup"><span data-stu-id="84f19-108">If an exception occurs, the channel is aborted.</span></span>  
  
```csharp  
ChannelFactory<IRequestChannel> cf = new  ChannelFactory<IRequestChannel>();  
IRequestChannel channel = null;  
try  
{  
  cf.Open();  
  channel = cf.CreateChannel();  
  channel.Open();  
  channel.Request();// This causes the channel to go into a faulted state.  
  channel.Close();  
}  
catch (Exception e)  
{  
  // Abort the channel if we have one  
  if(channel != null)  
    channel.Abort();  
}  
finally  
{  
  if (cf.State == CommunicationState.Opened)  
  {  
    cf.Close(); // It throws an exception that the channel is in a faulted state.  
  }  
}  
```  
  
## <a name="implement-both-asynchronous-and-synchronous-handlers"></a><span data-ttu-id="84f19-109">非同期および同期の両方のハンドラーを実装します。</span><span class="sxs-lookup"><span data-stu-id="84f19-109">Implement Both Asynchronous and Synchronous Handlers</span></span>  
 <span data-ttu-id="84f19-110">可能な場合、アダプターで非同期および同期の両方のハンドラーを実装します。</span><span class="sxs-lookup"><span data-stu-id="84f19-110">If possible, implement both asynchronous and synchronous handlers in your adapter.</span></span> <span data-ttu-id="84f19-111">アダプターがのみ同期呼び出しを実装する場合、大量のメッセージ、またはマルチ スレッド環境で、アダプターを使用する場合の処理時にブロックの問題に遭遇する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="84f19-111">If your adapter only implements synchronous calls, you may run into blocking issues when processing a large volume of messages or when the adapter is used in a multithreaded environment.</span></span>  
  
## <a name="use-connection-pooling"></a><span data-ttu-id="84f19-112">接続プールを使用します。</span><span class="sxs-lookup"><span data-stu-id="84f19-112">Use Connection Pooling</span></span>  
 <span data-ttu-id="84f19-113">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]既定で接続プール機能をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="84f19-113">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] supports connection pooling by default.</span></span> <span data-ttu-id="84f19-114">ただし、アダプター開発者プールのプロパティはバインドのプロパティとして公開する決定をします。</span><span class="sxs-lookup"><span data-stu-id="84f19-114">However, it is up to the adapter developer to determine which connection pooling properties to expose as binding properties.</span></span> <span data-ttu-id="84f19-115">内で使用可能な接続プール設定が定義されている`Microsoft.ServiceModel.Channels.Common.ConnectionPoolSettings`です。</span><span class="sxs-lookup"><span data-stu-id="84f19-115">The available Connection Pool settings are defined within `Microsoft.ServiceModel.Channels.Common.ConnectionPoolSettings`.</span></span>  
  
 <span data-ttu-id="84f19-116">内のオプションはありません、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を簡単にこれらのプロパティとしてアダプター接続のプロパティを公開します。</span><span class="sxs-lookup"><span data-stu-id="84f19-116">There are no options within the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] to easily expose these properties as adapter connection properties.</span></span> <span data-ttu-id="84f19-117">アダプター開発者は、アダプターの実装でプロパティを手動で定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84f19-117">The adapter developer must manually define the properties in the adapter implementation.</span></span>  
  
```csharp  
public CustomAdapter(): base()  
{  
   this.Settings.ConnectionPool.EnablePooling = true;  
   this.Settings.ConnectionPool.HandlersShareSameConnection = true;  
   this.Settings.ConnectionPool.MaxConnectionsPerSystem = 50;  
   this.Settings.ConnectionPool.MaxAvailableConnections = 5;  
}  
```  
  
## <a name="ensure-that-the-adapter-supports-two-way-operations"></a><span data-ttu-id="84f19-118">アダプターが双方向の操作をサポートしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="84f19-118">Ensure That the Adapter Supports Two-Way Operations</span></span>  
 <span data-ttu-id="84f19-119">アダプターは BizTalk Server から呼び出されると、場合でも、戻り値は void、双方向の操作をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="84f19-119">If your adapter is called from BizTalk Server, it must support two-way operations, even if the return value is void.</span></span> <span data-ttu-id="84f19-120">これは BizTalk Server で、出力方向の要求から返された応答を要求するためと、アダプターには、一方向操作のみを実装する場合に例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="84f19-120">This is because BizTalk Server expects a response returned from any outgoing request, and throws an exception if your adapter only implements one-way operations.</span></span>  
  
 <span data-ttu-id="84f19-121">Void を返す要求-応答コントラクトの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="84f19-121">Here is an example of a request-response contract that returns void.</span></span>  
  
```csharp  
[ServiceContract(Namespace=”Http:Microsoft.BizTalk.Samples.WCFAdapterSample”)]  
public interface ICalculator  
{  
   [OperationContract]  
   void Add(double n1, double n2);  
}  
```  
  
## <a name="implement-tracing"></a><span data-ttu-id="84f19-122">トレースを実装します。</span><span class="sxs-lookup"><span data-stu-id="84f19-122">Implement Tracing</span></span>  
 <span data-ttu-id="84f19-123">開発サイクル中にないように思えますコードをステップ実行して、問題をデバッグするため、トレースを使用しているアダプターを追加するのには重要です。</span><span class="sxs-lookup"><span data-stu-id="84f19-123">During the development cycle, it might not seem important to add tracing to your adapter, since you can step through the code and debug any problems.</span></span> <span data-ttu-id="84f19-124">ただし、実稼働環境で、アダプターがインストールされると、できない問題を特定する実行時のデバッグを使用します。</span><span class="sxs-lookup"><span data-stu-id="84f19-124">However, once the adapter is installed in a production environment, you might not be able to use run-time debugging to isolate problems.</span></span> <span data-ttu-id="84f19-125">アダプター全体でトレースを有効にした場合、障害が発生している場所の特定に使用できます。</span><span class="sxs-lookup"><span data-stu-id="84f19-125">If you have enabled tracing throughout your adapter, it can be used to isolate where failures are occurring.</span></span>  
  
 <span data-ttu-id="84f19-126">参照してください[WCF LOB Adapter SDK を持つアダプターのトレース](../../adapters-and-accelerators/wcf-lob-adapter-sdk/trace-an-adapter-with-the-wcf-lob-adapter-sdk.md)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="84f19-126">See [Trace an adapter with the WCF LOB Adapter SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/trace-an-adapter-with-the-wcf-lob-adapter-sdk.md) for further details.</span></span>  
  
## <a name="use-uri-properties-for-frequently-changed-settings"></a><span data-ttu-id="84f19-127">URI のプロパティ設定を使用して頻繁に変更されます。</span><span class="sxs-lookup"><span data-stu-id="84f19-127">Use URI Properties for Frequently Changed Settings</span></span>  
 <span data-ttu-id="84f19-128">バインドまたは URI プロパティとしてカスタム プロパティを公開するかどうかを決定する際に、多くの場合、値が変更された場合は、URI プロパティを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="84f19-128">When deciding whether to expose a custom property as a binding or URI property, it is recommended to use a URI property if the value changes often.</span></span> <span data-ttu-id="84f19-129">バインドのプロパティは、めったに変化する値を予約する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84f19-129">Binding properties should be reserved for values that rarely change.</span></span>  
  
 <span data-ttu-id="84f19-130">例バインディング プロパティは、すべての接続で使用されるデータベース サーバー名になります。</span><span class="sxs-lookup"><span data-stu-id="84f19-130">An example binding property would be a database server name that is used by all connections.</span></span> <span data-ttu-id="84f19-131">URI プロパティの使用例は、特定のテーブルまたはその特定の接続で使用するストアド プロシージャになります。</span><span class="sxs-lookup"><span data-stu-id="84f19-131">An example URI property would be a specific table or stored procedure to be used by that specific connection.</span></span>  
  
## <a name="do-not-pass-user-name-or-password-values-in-the-uri"></a><span data-ttu-id="84f19-132">URI にユーザー名またはパスワードの値を渡すされません。</span><span class="sxs-lookup"><span data-stu-id="84f19-132">Do Not Pass User Name or Password Values in the URI</span></span>  
 <span data-ttu-id="84f19-133">使用する場合、アダプターは、呼び出し元の資格情報を必要とするをお勧め、 **ClientCredentials** URI の一部としてクライアントの資格情報を渡す代わりに資格情報の値を取得するクラス。</span><span class="sxs-lookup"><span data-stu-id="84f19-133">If your adapter requires the caller’s credentials, it is recommended to use the **ClientCredentials** class to retrieve credential values instead of passing client credentials as part of the URI.</span></span> <span data-ttu-id="84f19-134">**ClientCredentials**クラスより安全な方法でクライアントからサービスに資格情報を渡すためのものでは、WCF の標準機能です。</span><span class="sxs-lookup"><span data-stu-id="84f19-134">The **ClientCredentials** class is a standard feature of WCF that is intended for passing credential information from the client to the service in a more secure manner.</span></span> <span data-ttu-id="84f19-135">URI 文字列の一部として、ユーザー情報を渡すと、転送中にユーザー情報が公開する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="84f19-135">Passing the user information as part of the URI string may expose the user information while in transit.</span></span>  
  
 <span data-ttu-id="84f19-136">資格情報を渡す場合の推奨される方法は、次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="84f19-136">The recommended methods of passing credentials are shown in the following table.</span></span>  
  
|<span data-ttu-id="84f19-137">方法</span><span class="sxs-lookup"><span data-stu-id="84f19-137">Method</span></span>|<span data-ttu-id="84f19-138">Description</span><span class="sxs-lookup"><span data-stu-id="84f19-138">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="84f19-139">デザイン時</span><span class="sxs-lookup"><span data-stu-id="84f19-139">Design time</span></span>|<span data-ttu-id="84f19-140">使用する場合、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]アダプタでは、クライアント資格情報の種類を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="84f19-140">When using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], you can specify the client credential types that the adapter supports.</span></span>|  
|<span data-ttu-id="84f19-141">実行時</span><span class="sxs-lookup"><span data-stu-id="84f19-141">Run time</span></span>|<span data-ttu-id="84f19-142">生成された .NET CLR プロキシを使用する場合できるプログラムでクライアント資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="84f19-142">When using a generated .NET CLR proxy, you can programmatically set the client credentials.</span></span><br /><br /> `static void Main(string[] args) {    EchoServiceClient client = new EchoServiceClient();    client.ClientCredentials.UserName.UserName = "TestUser";    client.ClientCredentials.UserName.Password = "TestPassword";    string response=client.EchoString("Test String"); }`<br /><br /> <span data-ttu-id="84f19-143">代わりに、チャネルと直接対話する必要がある場合 WCF チャネル モデルを使用してチャネル ファクトリを作成するときに、クライアントの資格情報を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="84f19-143">Alternatively, if you need to interact with the channel directly, you can use the WCF channel model to specify the client credentials when creating a channel factory.</span></span><br /><br /> `EchoAdapterBinding binding = new EchoAdapterBinding(); binding.Count = 3; ClientCredentials clientCredentials = new ClientCredentials(); clientCredentials.UserName.UserName = "TestUser"; clientCredentials.UserName.Password = "TestPassword"; BindingParameterCollection bindingParms = new BindingParameterCollection(); bindingParms.Add(clientCredentials); EndpointAddress address = new EndpointAddress("echo://"); IChannelFactory<IRequestChannel> requestChannelFactory = binding.BuildChannelFactory<IRequestChannel>(bindingParms); requestChannelFactory.Open();`|  
|<span data-ttu-id="84f19-144">WCF の構成</span><span class="sxs-lookup"><span data-stu-id="84f19-144">WCF configuration</span></span>|<span data-ttu-id="84f19-145">クライアント構成ファイルで追加、 \<endpointBehaviors > 要素を含む\<clientCredentials >。</span><span class="sxs-lookup"><span data-stu-id="84f19-145">In the client configuration file, add an \<endpointBehaviors> element that includes \<clientCredentials>.</span></span><br /><br /> `<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">       <system.serviceModel>           . . . . .           <behaviors>             <endpointBehaviors>               <behavior name="clientEndpointCredential">                 <clientCredentials>                   <windows allowNtlm="false" allowedImpersonationLevel="Delegation" />                    </clientCredentials>               </behavior>             </endpointBehaviors>           </behaviors>       </system.serviceModel>   </configuration>`|  
|<span data-ttu-id="84f19-146">BizTalk の使用</span><span class="sxs-lookup"><span data-stu-id="84f19-146">Using BizTalk</span></span>|<span data-ttu-id="84f19-147">追加することができますを使用してアダプターを使用する WCF アダプターを使用する場合、 **clientCredentials**で動作拡張機能、**動作**タブです。これを追加した後は、エンドポイントの動作で目的のクライアント資格情報を設定できます。</span><span class="sxs-lookup"><span data-stu-id="84f19-147">When using the WCF adapter to consume your adapter, you can add the **clientCredentials** behavior extension on the **Behavior** tab. Once this has been added, you can set the desired client credentials in the endpoint behavior.</span></span>|  
  
## <a name="do-not-return-both-strongdatasettype-and-weakdatasettype"></a><span data-ttu-id="84f19-148">両方を返さない StrongDataSetType と WeakDataSetType</span><span class="sxs-lookup"><span data-stu-id="84f19-148">Do Not Return Both StrongDataSetType and WeakDataSetType</span></span>  
 <span data-ttu-id="84f19-149">アダプターが返された場合、 `DataSet`、いずれかの方法`Microsoft.ServiceModel.Channels.Common.QualifiedType.StrongDataSetType%2A`または`Microsoft.ServiceModel.Channels.Common.QualifiedType.WeakDataSetType%2A`は、同時に両方を使用しません。</span><span class="sxs-lookup"><span data-stu-id="84f19-149">If your adapter returns a `DataSet`, use either `Microsoft.ServiceModel.Channels.Common.QualifiedType.StrongDataSetType%2A` or `Microsoft.ServiceModel.Channels.Common.QualifiedType.WeakDataSetType%2A`, but do not use both at the same time.</span></span> <span data-ttu-id="84f19-150">両方の種類によって生成される名前空間とルート ノード名が同じであり、WSDL で同時に存在できません。</span><span class="sxs-lookup"><span data-stu-id="84f19-150">The root node name and namespace produced by both types are identical, and cannot exist simultaneously in a WSDL.</span></span>  
  
 <span data-ttu-id="84f19-151">中に`WeakDataSetType`と`StrongDataSetType`両方を表す、 `System.Data.DataSet`、`StrongDataSetType`として生成されたプロキシが表示されるため、.NET アプリケーションで使用する方が簡単`System.Data.Dataset`です。</span><span class="sxs-lookup"><span data-stu-id="84f19-151">While `WeakDataSetType` and `StrongDataSetType` both represent a `System.Data.DataSet`, `StrongDataSetType` is easier to use in .NET applications, since the proxy generated appears as `System.Data.Dataset`.</span></span> <span data-ttu-id="84f19-152">によって生成されたプロキシ`WeakDataSetType`は`XmlElement[]`、これは .NET アプリケーションで使用することは困難です。</span><span class="sxs-lookup"><span data-stu-id="84f19-152">The proxy generated by `WeakDataSetType` is `XmlElement[]`, which is more difficult to use in a .NET application.</span></span>  <span data-ttu-id="84f19-153">BizTalk Server から返されたスキーマを使用できない`StrongDataSet`を使用することが、`WeakDataSetType`です。</span><span class="sxs-lookup"><span data-stu-id="84f19-153">BizTalk Server cannot consume the schema returned from `StrongDataSet`, but is able to consume `WeakDataSetType`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="84f19-154">`StrongDataSetType``WeakDataSetType`のみ、クライアント アプリケーションがアダプターによって渡された XML メッセージを解釈する方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="84f19-154">`StrongDataSetType` and `WeakDataSetType` only control how the client application interprets the XML messages passed by the adapter.</span></span> <span data-ttu-id="84f19-155">XML メッセージは、型の指定に関係なく同じです。</span><span class="sxs-lookup"><span data-stu-id="84f19-155">The XML message is the same regardless of which type is specified.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="84f19-156">返すときに`StrongDataSetType`、設定する必要があります`Microsoft.ServiceModel.Channels.Common.MetadataSettings.CompileWsdl%2A`に`false`です。</span><span class="sxs-lookup"><span data-stu-id="84f19-156">When returning `StrongDataSetType`, you must set `Microsoft.ServiceModel.Channels.Common.MetadataSettings.CompileWsdl%2A` to `false`.</span></span> <span data-ttu-id="84f19-157">設定すると`true`、既定値、`XmlSchemaSet::Compile`が呼び出された内アダプター WSDL でエラーがないことを確認するには、ただし、スキーマによって生成される`StrongDataSetType`で例外が生成されます`XmlSchemaSet`です。</span><span class="sxs-lookup"><span data-stu-id="84f19-157">When set to `true`, the default, `XmlSchemaSet::Compile` is called within the adapter to ensure there are no errors in the WSDL, however the schema produced by `StrongDataSetType` generates an exception in `XmlSchemaSet`.</span></span>  
>   
>  <span data-ttu-id="84f19-158">設定`CompileWsdl`に`false`バイパス プロキシの生成中に、アダプターと検証内での WSDL スキーマ検証が行われます。</span><span class="sxs-lookup"><span data-stu-id="84f19-158">Setting `CompileWsdl` to `false` bypasses WSDL schema validation within the adapter and validation occurs during proxy generation.</span></span>  <span data-ttu-id="84f19-159">Svcutil.exe などのユーティリティは、両方のプロキシを生成できません`StrongDataSetType`と`WeakDataSetType`です。</span><span class="sxs-lookup"><span data-stu-id="84f19-159">Utilities such as svcutil.exe are able to generate a proxy for both `StrongDataSetType` and `WeakDataSetType`.</span></span>  
  
 <span data-ttu-id="84f19-160">BizTalk と .NET の両方の環境を操作するには、環境内で使用される 2 つの戻り値の型の間で切り替えを可能にするバインディングのプロパティを実装することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="84f19-160">To work with both BizTalk and .NET environments, consider implementing a binding property that allows switching between the two return types as dictated by the environment.</span></span>  
  
```csharp  
internal static QualifiedType GetDataSetQualifiedType(MyAdapterBindingProperties bindingProperties)  
{  
   if (bindingProperties.EnableBizTalkCompatibility)  
      return QualifiedType.WeakDataSetType;  
   else  
      return QualifiedType.StrongDataSetType;  
}  
```  
  
## <a name="create-meaningful-xsd-schema-names-in-biztalk-server"></a><span data-ttu-id="84f19-161">BizTalk Server で意味のある XSD スキーマの名前を作成します。</span><span class="sxs-lookup"><span data-stu-id="84f19-161">Create Meaningful XSD Schema Names in BizTalk Server</span></span>  
 <span data-ttu-id="84f19-162">使用する場合、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]デザイン時ツール、BizTalk プロジェクトで生成される XSD スキーマの名前が作成されたを使用して、`DefaultXsdFileNamePrefix`プロパティ、 `fileNameHint` WSDL 内の注釈と、必要に応じて、一意の整数値。</span><span class="sxs-lookup"><span data-stu-id="84f19-162">When using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] design-time tool, the name of the XSD schema generated in your BizTalk project is created using the `DefaultXsdFileNamePrefix` property, the `fileNameHint` annotation in the WSDL and, if required, a unique integer value.</span></span>  
  
 <span data-ttu-id="84f19-163">たとえば場合、 `DefaultXsdFileNamePrefix` "MyAdapter"に設定されていると、`fileNameHint`注釈が"Stream"に設定されている、MyAdapterStream.xsd の名前は、XSD スキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="84f19-163">For example, if `DefaultXsdFileNamePrefix` is set to “MyAdapter” and the `fileNameHint` annotation is set to “Stream”, the XSD schema created is named MyAdapterStream.xsd.</span></span>  
  
```  
\<xs:schema elementFormDefault='qualified' targetNamespace='http://schemas.microsoft.com/Message' xmlns:xs='http://www.w3.org/2001/XMLSchema' xmlns:tns='http://schemas.microsoft.com/Message'>  
\<xs:annotation>  
\<xs:appinfo>  
\<fileNameHint xmlns='http://schemas.microsoft.com/servicemodel/adapters/metadata/xsd'>Stream</fileNameHint>  
\</xs:appinfo>  
\</xs:annotation>  
\<xs:simpleType name='StreamBody'>  
\<xs:restriction base='xs:base64Binary' />  
\</xs:simpleType>  
\</xs:schema>  
  
```  
  
> [!NOTE]
>  <span data-ttu-id="84f19-164">既定値の`DefaultXsdFileNamePrefix`バインディングの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="84f19-164">The default value of `DefaultXsdFileNamePrefix` is the name of your binding.</span></span> <span data-ttu-id="84f19-165">別の値を指定するには、オーバーライド`DefaultXsdFileNamePrefix`から派生するアダプター クラスに`Microsoft.ServiceModel.Channels.Common.AdapterBinding`です。</span><span class="sxs-lookup"><span data-stu-id="84f19-165">To specify a different value, override `DefaultXsdFileNamePrefix` in your Adapter class that is derived from `Microsoft.ServiceModel.Channels.Common.AdapterBinding`.</span></span>  
  
 <span data-ttu-id="84f19-166">2 つの可能なメソッドを追加する、`fileNameHint`スキーマに注釈を: エクスポートを上書きしています.スキーマ メソッド OperationMetadata\TypeMetadata またはアダプターの IWsdlRetrieval 実装をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="84f19-166">There are two possible methods to add the `fileNameHint` annotation to the schema: override the Export…Schema methods on OperationMetadata\TypeMetadata or override the IWsdlRetrieval implementation of the adapter.</span></span> <span data-ttu-id="84f19-167">いずれかの方法は、基本実装を呼び出すし、スキーマ コレクション内のスキーマに注釈を追加します。</span><span class="sxs-lookup"><span data-stu-id="84f19-167">For either method, you can call the base implementation and then add the annotation to the schemas in the schema collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="84f19-168">エクスポートをオーバーライドする場合.スキーマ メソッド、同じスキーマに複数の操作/型定義がある可能性がありますアダプターはことを確認の複数の発生、`fileNameHints`同じスキーマで注釈の競合は発生しません。</span><span class="sxs-lookup"><span data-stu-id="84f19-168">When overriding the Export…Schema methods, there may be multiple operation/type definitions in the same schema; the adapter should make sure that multiple occurrences of the `fileNameHints` annotation in the same schema do not conflict.</span></span> <span data-ttu-id="84f19-169">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]最初に見つかった位置を使用して`fileNameHint`スキーマ内で複数回に発生する場合。</span><span class="sxs-lookup"><span data-stu-id="84f19-169">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] uses the first occurrence of `fileNameHint` if it occurs multiple times within a schema.</span></span>  
  
 <span data-ttu-id="84f19-170">次の例では、IWsdlRetrieval を使用に追加されて、`fileNameHint`に WSDL 注釈。</span><span class="sxs-lookup"><span data-stu-id="84f19-170">In the following example, IWsdlRetrieval is used to add the `fileNameHint` annotation to the WSDL.</span></span>  
  
```csharp  
sealed class MyAdapterWsdlRetrieval : IWsdlRetrieval  
{  
   IWsdlRetrieval mBaseWsdlRetrieval;  
   public MyAdapterWsdlRetrieval(IWsdlRetrieval baseWsdlRetrieval)  
   {  
      mBaseWsdlRetrieval = baseWsdlRetrieval;  
   }  
  
   ServiceDescription IWsdlRetrieval.GetWsdl(Microsoft.ServiceModel.Channels.MetadataRetrievalNode[] nodes, Uri uri, TimeSpan timeout)  
   {  
      ServiceDescription baseDesc = mBaseWsdlRetrieval.GetWsdl(nodes, uri, timeout);  
      foreach (XmlSchema schema in baseDesc.Types.Schemas)  
      {  
         CreateFileNameHint(schema);  
      }  
      return baseDesc;  
   }  
  
   void CreateFileNameHint(XmlSchema schema)  
   {  
      string targetNamespace = schema.TargetNamespace;  
      if (string.IsNullOrEmpty(targetNamespace))  
         return;  
      string fileNameHint = null;  
      //determine the filename based on namespace  
      if (targetNamespace.StartsWith("myadapter:// adapters.samples.myadaptpter/HelloWorld"))  
      {  
         fileNameHint = "HelloWorld";  
      }  
      if (targetNamespace.StartsWith("myadapter:// adapters.samples.myadapter/Hello"))  
      {  
         fileNameHint = "Hello";  
      }  
      //create the annotation and populate it with fileNameHint  
      XmlSchemaAnnotation annotation = new XmlSchemaAnnotation();  
      XmlSchemaAppInfo appInfo = new XmlSchemaAppInfo();  
      XmlDocument doc = new XmlDocument();  
      XmlNode[] fileNameHintNodes = new XmlNode[1];  
      fileNameHintNodes[0] = doc.CreateElement(null, "fileNameHint", "http://schemas.microsoft.com/servicemodel/adapters/metadata/xsd");  
      fileNameHintNodes[0].AppendChild(doc.CreateTextNode(fileNameHint));  
      appInfo.Markup = fileNameHintNodes;  
      annotation.Items.Add(appInfo);  
      schema.Items.Insert(0, annotation);  
   }  
```  
  
## <a name="do-not-modify-adapterenvironmentsettings-during-processing"></a><span data-ttu-id="84f19-171">処理中に AdapterEnvironmentSettings は変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="84f19-171">Do Not Modify AdapterEnvironmentSettings During Processing</span></span>  
 <span data-ttu-id="84f19-172">アダプターはのみに設定する必要があります、 **AdapterEnvironmentSettings**、 **ConnectionPoolManager**、**接続プール**、および**CommonCacheSize**アダプターの初期化中にし、実行中のインスタンスの値を変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="84f19-172">The adapter should only set the **AdapterEnvironmentSettings**, **ConnectionPoolManager**, **ConnectionPool**, and **CommonCacheSize** during adapter initialization and should not attempt to modify the values for a running instance.</span></span>  
  
 <span data-ttu-id="84f19-173">これらの設定は、現在実行中のアダプター インスタンスで変更が場合、これが原因で接続を現在実行中の構成設定を上書きして新しい接続。</span><span class="sxs-lookup"><span data-stu-id="84f19-173">If these settings are modified on a currently running adapter instance, this may result in new connections overwriting configuration settings for currently executing connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84f19-174">参照</span><span class="sxs-lookup"><span data-stu-id="84f19-174">See Also</span></span>  
 [<span data-ttu-id="84f19-175">WCF LOB Adapter SDK を使用して、開発のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="84f19-175">Development best practices using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/development-best-practices-using-the-wcf-lob-adapter-sdk.md)