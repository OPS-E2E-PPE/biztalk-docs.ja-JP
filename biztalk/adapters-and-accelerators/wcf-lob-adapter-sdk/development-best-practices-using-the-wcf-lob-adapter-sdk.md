---
title: WCF LOB Adapter SDK を使用して開発のベスト プラクティス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ea3a13b-e41f-4920-bf0d-26f7bb145aa3
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f42980d93c7872811ea26fb9fc21a97f7e4e8e2d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991323"
---
# <a name="development-best-practices-using-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="af30a-102">WCF LOB Adapter SDK を使用して開発のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="af30a-102">Development best practices using the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="af30a-103">このトピックの「ベスト プラクティスを使用するには、アプリケーションおよびアダプターを向上させるためにします。</span><span class="sxs-lookup"><span data-stu-id="af30a-103">You can use the best practices in this topic to improve your applications and adapters.</span></span>  

## <a name="call-abort-before-close-on-channel-exception"></a><span data-ttu-id="af30a-104">チャネルの例外で終了する前に中止を呼び出す</span><span class="sxs-lookup"><span data-stu-id="af30a-104">Call Abort Before Close on Channel Exception</span></span>  
 <span data-ttu-id="af30a-105">WCF チャネル モデルを使用するアプリケーションを記述するときに呼び出す必要があります`IRequestChannel.Abort`呼び出す前に`ChannelFactory.Close`します。</span><span class="sxs-lookup"><span data-stu-id="af30a-105">When you write an application that uses the WCF channel model, you should call `IRequestChannel.Abort` before calling `ChannelFactory.Close`.</span></span> <span data-ttu-id="af30a-106">表示されない場合、`ChannelFactory.Close`例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="af30a-106">If you do not, `ChannelFactory.Close` throws an exception.</span></span>  

 <span data-ttu-id="af30a-107">次の例では、チャネルの操作は、try/catch ブロック内で試行されます。</span><span class="sxs-lookup"><span data-stu-id="af30a-107">In the following example, channel operations are attempted within a try/catch block.</span></span> <span data-ttu-id="af30a-108">例外が発生する場合、チャネルは中止されます。</span><span class="sxs-lookup"><span data-stu-id="af30a-108">If an exception occurs, the channel is aborted.</span></span>  

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

## <a name="implement-both-asynchronous-and-synchronous-handlers"></a><span data-ttu-id="af30a-109">非同期と同期の両方のハンドラーを実装します。</span><span class="sxs-lookup"><span data-stu-id="af30a-109">Implement Both Asynchronous and Synchronous Handlers</span></span>  
 <span data-ttu-id="af30a-110">可能であればでは、アダプター ハンドラーを非同期と同期の両方を実装します。</span><span class="sxs-lookup"><span data-stu-id="af30a-110">If possible, implement both asynchronous and synchronous handlers in your adapter.</span></span> <span data-ttu-id="af30a-111">アダプターは、同期呼び出しのみを実装する場合は、大量のメッセージ、またはマルチ スレッド環境で、アダプターを使用する場合の処理時にブロックの問題に実行できます。</span><span class="sxs-lookup"><span data-stu-id="af30a-111">If your adapter only implements synchronous calls, you may run into blocking issues when processing a large volume of messages or when the adapter is used in a multithreaded environment.</span></span>  

## <a name="use-connection-pooling"></a><span data-ttu-id="af30a-112">接続プールを使用します。</span><span class="sxs-lookup"><span data-stu-id="af30a-112">Use Connection Pooling</span></span>  
 <span data-ttu-id="af30a-113">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]接続が既定でプールをサポートします。</span><span class="sxs-lookup"><span data-stu-id="af30a-113">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] supports connection pooling by default.</span></span> <span data-ttu-id="af30a-114">ただし、アダプター開発者がバインドのプロパティとして公開するプロパティをプールする接続の決定までなります。</span><span class="sxs-lookup"><span data-stu-id="af30a-114">However, it is up to the adapter developer to determine which connection pooling properties to expose as binding properties.</span></span> <span data-ttu-id="af30a-115">内で使用可能な接続プール設定が定義されている`Microsoft.ServiceModel.Channels.Common.ConnectionPoolSettings`します。</span><span class="sxs-lookup"><span data-stu-id="af30a-115">The available Connection Pool settings are defined within `Microsoft.ServiceModel.Channels.Common.ConnectionPoolSettings`.</span></span>  

 <span data-ttu-id="af30a-116">内のオプションがない、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を簡単にこれらのプロパティとしてアダプターの接続プロパティを公開します。</span><span class="sxs-lookup"><span data-stu-id="af30a-116">There are no options within the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] to easily expose these properties as adapter connection properties.</span></span> <span data-ttu-id="af30a-117">アダプター開発者は、アダプターの実装で、プロパティを手動で定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af30a-117">The adapter developer must manually define the properties in the adapter implementation.</span></span>  

```csharp  
public CustomAdapter(): base()  
{  
   this.Settings.ConnectionPool.EnablePooling = true;  
   this.Settings.ConnectionPool.HandlersShareSameConnection = true;  
   this.Settings.ConnectionPool.MaxConnectionsPerSystem = 50;  
   this.Settings.ConnectionPool.MaxAvailableConnections = 5;  
}  
```  

## <a name="ensure-that-the-adapter-supports-two-way-operations"></a><span data-ttu-id="af30a-118">アダプターが双方向の操作をサポートしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="af30a-118">Ensure That the Adapter Supports Two-Way Operations</span></span>  
 <span data-ttu-id="af30a-119">アダプターは BizTalk Server から呼び出されると、戻り値は void 場合でも、双方向の操作をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="af30a-119">If your adapter is called from BizTalk Server, it must support two-way operations, even if the return value is void.</span></span> <span data-ttu-id="af30a-120">これは、BizTalk Server が任意の発信要求から返される応答を期待しているためと、アダプターのみ一方向の操作を実装している場合に例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="af30a-120">This is because BizTalk Server expects a response returned from any outgoing request, and throws an exception if your adapter only implements one-way operations.</span></span>  

 <span data-ttu-id="af30a-121">Void を返す要求-応答コントラクトの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="af30a-121">Here is an example of a request-response contract that returns void.</span></span>  

```csharp  
[ServiceContract(Namespace=”Http:Microsoft.BizTalk.Samples.WCFAdapterSample”)]  
public interface ICalculator  
{  
   [OperationContract]  
   void Add(double n1, double n2);  
}  
```  

## <a name="implement-tracing"></a><span data-ttu-id="af30a-122">トレースを実装します。</span><span class="sxs-lookup"><span data-stu-id="af30a-122">Implement Tracing</span></span>  
 <span data-ttu-id="af30a-123">開発サイクル中にないかもしれません、コードをステップ実行して問題をデバッグするために、トレースをアダプターを追加してください。</span><span class="sxs-lookup"><span data-stu-id="af30a-123">During the development cycle, it might not seem important to add tracing to your adapter, since you can step through the code and debug any problems.</span></span> <span data-ttu-id="af30a-124">ただし、アダプターが、運用環境でインストールされると、実行時のデバッグを使用して、問題を特定することができません。</span><span class="sxs-lookup"><span data-stu-id="af30a-124">However, once the adapter is installed in a production environment, you might not be able to use run-time debugging to isolate problems.</span></span> <span data-ttu-id="af30a-125">アダプター全体でトレースを有効にした場合は、エラーが発生している場所を特定する使用できます。</span><span class="sxs-lookup"><span data-stu-id="af30a-125">If you have enabled tracing throughout your adapter, it can be used to isolate where failures are occurring.</span></span>  

 <span data-ttu-id="af30a-126">参照してください[WCF LOB Adapter SDK のアダプターのトレース](../../adapters-and-accelerators/wcf-lob-adapter-sdk/trace-an-adapter-with-the-wcf-lob-adapter-sdk.md)の詳細。</span><span class="sxs-lookup"><span data-stu-id="af30a-126">See [Trace an adapter with the WCF LOB Adapter SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/trace-an-adapter-with-the-wcf-lob-adapter-sdk.md) for further details.</span></span>  

## <a name="use-uri-properties-for-frequently-changed-settings"></a><span data-ttu-id="af30a-127">URI のプロパティを使用して、変更頻度の高い設定</span><span class="sxs-lookup"><span data-stu-id="af30a-127">Use URI Properties for Frequently Changed Settings</span></span>  
 <span data-ttu-id="af30a-128">カスタム プロパティをバインドまたは URI のプロパティとして公開するかどうかを決定する際は、多くの場合、値が変更された場合は、URI プロパティを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="af30a-128">When deciding whether to expose a custom property as a binding or URI property, it is recommended to use a URI property if the value changes often.</span></span> <span data-ttu-id="af30a-129">バインドのプロパティは、ほとんど変更されない値を予約する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af30a-129">Binding properties should be reserved for values that rarely change.</span></span>  

 <span data-ttu-id="af30a-130">バインド プロパティの例は、すべての接続で使用されるデータベース サーバー名になります。</span><span class="sxs-lookup"><span data-stu-id="af30a-130">An example binding property would be a database server name that is used by all connections.</span></span> <span data-ttu-id="af30a-131">URI のプロパティの使用例は、特定のテーブルまたはその特定の接続で使用されるストアド プロシージャになります。</span><span class="sxs-lookup"><span data-stu-id="af30a-131">An example URI property would be a specific table or stored procedure to be used by that specific connection.</span></span>  

## <a name="do-not-pass-user-name-or-password-values-in-the-uri"></a><span data-ttu-id="af30a-132">URI のユーザー名またはパスワードの値を渡すされません。</span><span class="sxs-lookup"><span data-stu-id="af30a-132">Do Not Pass User Name or Password Values in the URI</span></span>  
 <span data-ttu-id="af30a-133">使用する場合は、アダプターは、呼び出し元の資格情報を必要とするをお勧め、 **ClientCredentials** URI の一部としてクライアントの資格情報を渡す代わりに資格情報の値を取得するクラス。</span><span class="sxs-lookup"><span data-stu-id="af30a-133">If your adapter requires the caller’s credentials, it is recommended to use the **ClientCredentials** class to retrieve credential values instead of passing client credentials as part of the URI.</span></span> <span data-ttu-id="af30a-134">**ClientCredentials**クラスより安全な方法でクライアントからサービスに資格情報を渡すためのものでは、WCF の標準的な機能です。</span><span class="sxs-lookup"><span data-stu-id="af30a-134">The **ClientCredentials** class is a standard feature of WCF that is intended for passing credential information from the client to the service in a more secure manner.</span></span> <span data-ttu-id="af30a-135">URI 文字列の一部として、ユーザー情報を渡すと、転送中にユーザー情報を公開できます。</span><span class="sxs-lookup"><span data-stu-id="af30a-135">Passing the user information as part of the URI string may expose the user information while in transit.</span></span>  

 <span data-ttu-id="af30a-136">資格情報を渡す場合の推奨される方法は、次の表に表示されます。</span><span class="sxs-lookup"><span data-stu-id="af30a-136">The recommended methods of passing credentials are shown in the following table.</span></span>  


|      <span data-ttu-id="af30a-137">方法</span><span class="sxs-lookup"><span data-stu-id="af30a-137">Method</span></span>       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              <span data-ttu-id="af30a-138">説明</span><span class="sxs-lookup"><span data-stu-id="af30a-138">Description</span></span>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    <span data-ttu-id="af30a-139">デザイン時</span><span class="sxs-lookup"><span data-stu-id="af30a-139">Design time</span></span>    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                <span data-ttu-id="af30a-140">使用する場合、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]アダプターがサポートされるクライアント資格情報の種類を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="af30a-140">When using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], you can specify the client credential types that the adapter supports.</span></span>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|     <span data-ttu-id="af30a-141">実行時</span><span class="sxs-lookup"><span data-stu-id="af30a-141">Run time</span></span>      | <span data-ttu-id="af30a-142">生成された .NET CLR プロキシを使用して、プログラムで設定できますクライアント資格情報。</span><span class="sxs-lookup"><span data-stu-id="af30a-142">When using a generated .NET CLR proxy, you can programmatically set the client credentials.</span></span><br /><br /> `static void Main(string[] args) {    EchoServiceClient client = new EchoServiceClient();    client.ClientCredentials.UserName.UserName = "TestUser";    client.ClientCredentials.UserName.Password = "TestPassword";    string response=client.EchoString("Test String"); }`<br /><br /> <span data-ttu-id="af30a-143">代わりに、チャネルと直接対話する必要がある場合は、チャネル ファクトリを作成するときに、クライアントの資格情報を指定する WCF チャネル モデルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="af30a-143">Alternatively, if you need to interact with the channel directly, you can use the WCF channel model to specify the client credentials when creating a channel factory.</span></span><br /><br /> `EchoAdapterBinding binding = new EchoAdapterBinding(); binding.Count = 3; ClientCredentials clientCredentials = new ClientCredentials(); clientCredentials.UserName.UserName = "TestUser"; clientCredentials.UserName.Password = "TestPassword"; BindingParameterCollection bindingParms = new BindingParameterCollection(); bindingParms.Add(clientCredentials); EndpointAddress address = new EndpointAddress("echo://"); IChannelFactory<IRequestChannel> requestChannelFactory = binding.BuildChannelFactory<IRequestChannel>(bindingParms); requestChannelFactory.Open();` |
| <span data-ttu-id="af30a-144">WCF の構成</span><span class="sxs-lookup"><span data-stu-id="af30a-144">WCF configuration</span></span> |                                                                                                                                                                                                                                               <span data-ttu-id="af30a-145">クライアント構成ファイルで、追加、 \<endpointBehaviors\>要素が含まれる\<clientCredentials\>します。</span><span class="sxs-lookup"><span data-stu-id="af30a-145">In the client configuration file, add an \<endpointBehaviors\> element that includes \<clientCredentials\>.</span></span><br /><br /> `<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">       <system.serviceModel>           . . . . .           <behaviors>             <endpointBehaviors>               <behavior name="clientEndpointCredential">                 <clientCredentials>                   <windows allowNtlm="false" allowedImpersonationLevel="Delegation" />                    </clientCredentials>               </behavior>             </endpointBehaviors>           </behaviors>       </system.serviceModel>   </configuration>`                                                                                                                                                                                                                                               |
|   <span data-ttu-id="af30a-146">BizTalk を使用します。</span><span class="sxs-lookup"><span data-stu-id="af30a-146">Using BizTalk</span></span>   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                 <span data-ttu-id="af30a-147">追加することができますを使用してアダプターを使用する WCF アダプターを使用する場合、 **clientCredentials**で動作拡張機能、**動作**タブ。これが追加されたらは、エンドポイントの動作で目的のクライアント資格情報を設定できます。</span><span class="sxs-lookup"><span data-stu-id="af30a-147">When using the WCF adapter to consume your adapter, you can add the **clientCredentials** behavior extension on the **Behavior** tab. Once this has been added, you can set the desired client credentials in the endpoint behavior.</span></span>                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |

## <a name="do-not-return-both-strongdatasettype-and-weakdatasettype"></a><span data-ttu-id="af30a-148">両方が返されない StrongDataSetType と WeakDataSetType</span><span class="sxs-lookup"><span data-stu-id="af30a-148">Do Not Return Both StrongDataSetType and WeakDataSetType</span></span>  
 <span data-ttu-id="af30a-149">アダプターに返された場合、 `DataSet`、いずれかを使用して、`Microsoft.ServiceModel.Channels.Common.QualifiedType.StrongDataSetType%2A`または`Microsoft.ServiceModel.Channels.Common.QualifiedType.WeakDataSetType%2A`同時に両方は使用しません。</span><span class="sxs-lookup"><span data-stu-id="af30a-149">If your adapter returns a `DataSet`, use either `Microsoft.ServiceModel.Channels.Common.QualifiedType.StrongDataSetType%2A` or `Microsoft.ServiceModel.Channels.Common.QualifiedType.WeakDataSetType%2A`, but do not use both at the same time.</span></span> <span data-ttu-id="af30a-150">両方の種類によって生成された名前空間とルート ノードの名前が同じであり、WSDL で同時に存在できません。</span><span class="sxs-lookup"><span data-stu-id="af30a-150">The root node name and namespace produced by both types are identical, and cannot exist simultaneously in a WSDL.</span></span>  

 <span data-ttu-id="af30a-151">中に`WeakDataSetType`と`StrongDataSetType`両方を表す、 `System.Data.DataSet`、`StrongDataSetType`として生成されたプロキシが表示されるため、.NET アプリケーションで使いやすく、`System.Data.Dataset`します。</span><span class="sxs-lookup"><span data-stu-id="af30a-151">While `WeakDataSetType` and `StrongDataSetType` both represent a `System.Data.DataSet`, `StrongDataSetType` is easier to use in .NET applications, since the proxy generated appears as `System.Data.Dataset`.</span></span> <span data-ttu-id="af30a-152">によって生成されたプロキシ`WeakDataSetType`は`XmlElement[]`、.NET アプリケーションで使用することが困難であります。</span><span class="sxs-lookup"><span data-stu-id="af30a-152">The proxy generated by `WeakDataSetType` is `XmlElement[]`, which is more difficult to use in a .NET application.</span></span>  <span data-ttu-id="af30a-153">BizTalk Server から返されたスキーマを使用できない`StrongDataSet`が使用できるように`WeakDataSetType`します。</span><span class="sxs-lookup"><span data-stu-id="af30a-153">BizTalk Server cannot consume the schema returned from `StrongDataSet`, but is able to consume `WeakDataSetType`.</span></span>  

> [!NOTE]
>  <span data-ttu-id="af30a-154">`StrongDataSetType` `WeakDataSetType`のみ、クライアント アプリケーションがアダプターによって渡される XML メッセージを解釈する方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="af30a-154">`StrongDataSetType` and `WeakDataSetType` only control how the client application interprets the XML messages passed by the adapter.</span></span> <span data-ttu-id="af30a-155">XML メッセージでは、型の指定に関係なく同じです。</span><span class="sxs-lookup"><span data-stu-id="af30a-155">The XML message is the same regardless of which type is specified.</span></span>  

> [!NOTE]
>  <span data-ttu-id="af30a-156">返すときに`StrongDataSetType`を設定する必要があります`Microsoft.ServiceModel.Channels.Common.MetadataSettings.CompileWsdl%2A`に`false`します。</span><span class="sxs-lookup"><span data-stu-id="af30a-156">When returning `StrongDataSetType`, you must set `Microsoft.ServiceModel.Channels.Common.MetadataSettings.CompileWsdl%2A` to `false`.</span></span> <span data-ttu-id="af30a-157">設定すると`true`、既定値は、`XmlSchemaSet::Compile`が呼び出されます内、WSDL でエラーがないことを確認するアダプター、ただし、スキーマによって生成された`StrongDataSetType`で例外が発生する`XmlSchemaSet`。</span><span class="sxs-lookup"><span data-stu-id="af30a-157">When set to `true`, the default, `XmlSchemaSet::Compile` is called within the adapter to ensure there are no errors in the WSDL, however the schema produced by `StrongDataSetType` generates an exception in `XmlSchemaSet`.</span></span>  
>   
>  <span data-ttu-id="af30a-158">設定`CompileWsdl`に`false`バイパス プロキシの生成中に、アダプターと検証の WSDL スキーマの検証が行われます。</span><span class="sxs-lookup"><span data-stu-id="af30a-158">Setting `CompileWsdl` to `false` bypasses WSDL schema validation within the adapter and validation occurs during proxy generation.</span></span>  <span data-ttu-id="af30a-159">Svcutil.exe などのユーティリティは、両方のプロキシを生成する`StrongDataSetType`と`WeakDataSetType`します。</span><span class="sxs-lookup"><span data-stu-id="af30a-159">Utilities such as svcutil.exe are able to generate a proxy for both `StrongDataSetType` and `WeakDataSetType`.</span></span>  

 <span data-ttu-id="af30a-160">BizTalk および .NET の両方の環境を操作するには、環境に従い、2 つの戻り値の型を切り替えることができますをバインド プロパティの実装を検討してください。</span><span class="sxs-lookup"><span data-stu-id="af30a-160">To work with both BizTalk and .NET environments, consider implementing a binding property that allows switching between the two return types as dictated by the environment.</span></span>  

```csharp  
internal static QualifiedType GetDataSetQualifiedType(MyAdapterBindingProperties bindingProperties)  
{  
   if (bindingProperties.EnableBizTalkCompatibility)  
      return QualifiedType.WeakDataSetType;  
   else  
      return QualifiedType.StrongDataSetType;  
}  
```  

## <a name="create-meaningful-xsd-schema-names-in-biztalk-server"></a><span data-ttu-id="af30a-161">BizTalk Server で意味のある XSD スキーマの名前を作成します。</span><span class="sxs-lookup"><span data-stu-id="af30a-161">Create Meaningful XSD Schema Names in BizTalk Server</span></span>  
 <span data-ttu-id="af30a-162">使用する場合、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]デザイン時ツール、BizTalk プロジェクトで生成される XSD スキーマの名前を使用して作成、`DefaultXsdFileNamePrefix`プロパティ、 `fileNameHint` WSDL 注釈と、必要に応じて、一意の整数値。</span><span class="sxs-lookup"><span data-stu-id="af30a-162">When using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] design-time tool, the name of the XSD schema generated in your BizTalk project is created using the `DefaultXsdFileNamePrefix` property, the `fileNameHint` annotation in the WSDL and, if required, a unique integer value.</span></span>  

 <span data-ttu-id="af30a-163">たとえば場合、 `DefaultXsdFileNamePrefix` "MyAdapter"に設定されている、`fileNameHint`注釈が"Stream"に設定されている、MyAdapterStream.xsd の名前は、XSD スキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="af30a-163">For example, if `DefaultXsdFileNamePrefix` is set to “MyAdapter” and the `fileNameHint` annotation is set to “Stream”, the XSD schema created is named MyAdapterStream.xsd.</span></span>  

```  
<xs:schema elementFormDefault='qualified' targetNamespace='http://schemas.microsoft.com/Message' xmlns:xs='http://www.w3.org/2001/XMLSchema' xmlns:tns='http://schemas.microsoft.com/Message'>  
<xs:annotation>  
<xs:appinfo>  
<fileNameHint xmlns='http://schemas.microsoft.com/servicemodel/adapters/metadata/xsd'>Stream</fileNameHint>  
</xs:appinfo>  
</xs:annotation>  
<xs:simpleType name='StreamBody'>  
<xs:restriction base='xs:base64Binary' />  
</xs:simpleType>  
</xs:schema>  

```  

> [!NOTE]
>  <span data-ttu-id="af30a-164">既定値`DefaultXsdFileNamePrefix`バインディングの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="af30a-164">The default value of `DefaultXsdFileNamePrefix` is the name of your binding.</span></span> <span data-ttu-id="af30a-165">別の値を指定するには、オーバーライド`DefaultXsdFileNamePrefix`アダプター クラスから派生したで`Microsoft.ServiceModel.Channels.Common.AdapterBinding`します。</span><span class="sxs-lookup"><span data-stu-id="af30a-165">To specify a different value, override `DefaultXsdFileNamePrefix` in your Adapter class that is derived from `Microsoft.ServiceModel.Channels.Common.AdapterBinding`.</span></span>  

 <span data-ttu-id="af30a-166">追加する 2 つの方法がある、`fileNameHint`スキーマに注釈: エクスポートをオーバーライドしています.OperationMetadata\TypeMetadata またはアダプターの IWsdlRetrieval 実装をオーバーライド スキーマ メソッドします。</span><span class="sxs-lookup"><span data-stu-id="af30a-166">There are two possible methods to add the `fileNameHint` annotation to the schema: override the Export…Schema methods on OperationMetadata\TypeMetadata or override the IWsdlRetrieval implementation of the adapter.</span></span> <span data-ttu-id="af30a-167">いずれかの方法は、基本実装を呼び出すし、スキーマ コレクションのスキーマに注釈を追加します。</span><span class="sxs-lookup"><span data-stu-id="af30a-167">For either method, you can call the base implementation and then add the annotation to the schemas in the schema collection.</span></span>  

> [!NOTE]
>  <span data-ttu-id="af30a-168">エクスポートをオーバーライドするときにしています.スキーマ メソッドでは、同じスキーマに複数の操作/型定義である可能性がありますアダプターを確認してくださいを複数回出現、`fileNameHints`同じスキーマで注釈が競合しません。</span><span class="sxs-lookup"><span data-stu-id="af30a-168">When overriding the Export…Schema methods, there may be multiple operation/type definitions in the same schema; the adapter should make sure that multiple occurrences of the `fileNameHints` annotation in the same schema do not conflict.</span></span> <span data-ttu-id="af30a-169">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]最初に見つかった位置を使用して`fileNameHint`スキーマ内で複数回に発生する場合。</span><span class="sxs-lookup"><span data-stu-id="af30a-169">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] uses the first occurrence of `fileNameHint` if it occurs multiple times within a schema.</span></span>  

 <span data-ttu-id="af30a-170">追加する次の例では、IWsdlRetrieval が使用される、`fileNameHint`を WSDL 注釈。</span><span class="sxs-lookup"><span data-stu-id="af30a-170">In the following example, IWsdlRetrieval is used to add the `fileNameHint` annotation to the WSDL.</span></span>  

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

## <a name="do-not-modify-adapterenvironmentsettings-during-processing"></a><span data-ttu-id="af30a-171">処理中に AdapterEnvironmentSettings は変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="af30a-171">Do Not Modify AdapterEnvironmentSettings During Processing</span></span>  
 <span data-ttu-id="af30a-172">アダプターはのみに設定する必要があります、 **AdapterEnvironmentSettings**、 **ConnectionPoolManager**、 **ConnectionPool**、および**CommonCacheSize**アダプターの初期化中にし、実行中のインスタンスの値を変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="af30a-172">The adapter should only set the **AdapterEnvironmentSettings**, **ConnectionPoolManager**, **ConnectionPool**, and **CommonCacheSize** during adapter initialization and should not attempt to modify the values for a running instance.</span></span>  

 <span data-ttu-id="af30a-173">これらの設定を変更するには、現在実行中のアダプター インスタンスで、現在実行中の接続の構成設定を上書きする新しい接続でこれが原因します。</span><span class="sxs-lookup"><span data-stu-id="af30a-173">If these settings are modified on a currently running adapter instance, this may result in new connections overwriting configuration settings for currently executing connections.</span></span>  

## <a name="see-also"></a><span data-ttu-id="af30a-174">参照</span><span class="sxs-lookup"><span data-stu-id="af30a-174">See Also</span></span>  
 [<span data-ttu-id="af30a-175">WCF LOB Adapter SDK を使用して開発のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="af30a-175">Development best practices using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/development-best-practices-using-the-wcf-lob-adapter-sdk.md)