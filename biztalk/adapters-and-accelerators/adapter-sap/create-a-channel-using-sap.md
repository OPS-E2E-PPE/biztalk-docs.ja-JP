---
title: "SAP を使用してチャネルを作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- channel programming, creating a channel
- how to, create a channel
- creating a channel
- WCF channel model, creating a channel
ms.assetid: 24af1465-bb60-41d7-98bd-e501a981f82a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f69fbeb86cf63485591f048ef75cdcfd3d5056d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="create-a-channel-using-sap"></a><span data-ttu-id="579a9-102">SAP を使用して、チャネルを作成します。</span><span class="sxs-lookup"><span data-stu-id="579a9-102">Create a channel using SAP</span></span>
<span data-ttu-id="579a9-103">WCF チャネル モデルでの SAP システムに対する操作を呼び出すまたは SOAP メッセージを交換することで、SAP システムからメッセージを受信、 [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] WCF チャネルを経由します。</span><span class="sxs-lookup"><span data-stu-id="579a9-103">In the WCF channel model, you invoke operations on the SAP system or receive messages from the SAP system by exchanging SOAP messages with the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] over a WCF channel.</span></span>  
  
-   <span data-ttu-id="579a9-104">いずれかを使用して操作 (送信操作) を呼び出し、 **IRequestChannel**または**IOutputChannel**アダプターにメッセージを送信するには</span><span class="sxs-lookup"><span data-stu-id="579a9-104">You invoke operations (outbound operations) by using either an **IRequestChannel** or an **IOutputChannel** to send messages to the adapter</span></span>  
  
-   <span data-ttu-id="579a9-105">(からトリガーされた SAP システム) 経由でメッセージを受信する、 **IReplyChannel**です。</span><span class="sxs-lookup"><span data-stu-id="579a9-105">You receive messages (triggered from the SAP system) over an **IReplyChannel**.</span></span>  
  
 <span data-ttu-id="579a9-106">このセクションのトピックでは、作成して、着信および発信の操作に使用されるチャネル形状を構成する方法に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="579a9-106">The topics in this section provide information about how to create and configure channel shapes that are used for inbound and outbound operations.</span></span>  
  
## <a name="creating-outbound-client-channels"></a><span data-ttu-id="579a9-107">送信 (クライアント) チャネルを作成します。</span><span class="sxs-lookup"><span data-stu-id="579a9-107">Creating Outbound (Client) Channels</span></span>  
 <span data-ttu-id="579a9-108">いずれかを使用することができます、 **IRequestChannel**または**IOutputChannel** SAP システムでの操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="579a9-108">You can use either an **IRequestChannel** or an **IOutputChannel** to invoke operations on the SAP system.</span></span> <span data-ttu-id="579a9-109">作成する最初のどちらの場合、 **System.ServiceModel.ChannelFactory**適切なインターフェイスを使用します。</span><span class="sxs-lookup"><span data-stu-id="579a9-109">In either case, you first create a **System.ServiceModel.ChannelFactory** using the appropriate interface.</span></span> <span data-ttu-id="579a9-110">チャネルを作成するのにファクトリを使用します。</span><span class="sxs-lookup"><span data-stu-id="579a9-110">You then use the factory to create the channel.</span></span> <span data-ttu-id="579a9-111">チャネルを作成した後は、アダプターの操作の呼び出しに使用できます。</span><span class="sxs-lookup"><span data-stu-id="579a9-111">After you have created the channel you can use it to invoke operations on the adapter.</span></span>  
  
#### <a name="to-create-and-open-an-outbound-channel"></a><span data-ttu-id="579a9-112">作成および送信チャネルを開く</span><span class="sxs-lookup"><span data-stu-id="579a9-112">To create and open an outbound channel</span></span>  
  
1.  <span data-ttu-id="579a9-113">作成しのインスタンスを初期化**ChannelFactory**のエンドポイントとバインディングを使用して必要なチャネル形状です。</span><span class="sxs-lookup"><span data-stu-id="579a9-113">Create and initialize an instance of **ChannelFactory** for the desired channel shape by using an endpoint and a binding.</span></span> <span data-ttu-id="579a9-114">エンドポイントは SAP 接続 URI を指定し、バインディングは、インスタンスの**SAPDBBinding**です。</span><span class="sxs-lookup"><span data-stu-id="579a9-114">The endpoint specifies an SAP connection URI and the binding is an instance of **SAPDBBinding**.</span></span> <span data-ttu-id="579a9-115">(チャネル ファクトリを開く前に必要なすべてのバインドのプロパティを設定します。)</span><span class="sxs-lookup"><span data-stu-id="579a9-115">(Set any binding properties required before you open the channel factory.)</span></span>  
  
2.  <span data-ttu-id="579a9-116">使用してチャネル ファクトリの SAP 資格情報を提供、 **ClientCredentials**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="579a9-116">Provide SAP credentials for the channel factory by using the **ClientCredentials** property.</span></span>  
  
3.  <span data-ttu-id="579a9-117">チャネル ファクトリを開きます。</span><span class="sxs-lookup"><span data-stu-id="579a9-117">Open the channel factory.</span></span>  
  
4.  <span data-ttu-id="579a9-118">呼び出すことによって、チャネルのインスタンスを取得、 **CreateChannel**チャネル ファクトリでのメソッドです。</span><span class="sxs-lookup"><span data-stu-id="579a9-118">Get an instance of the channel by invoking the **CreateChannel** method on the channel factory.</span></span>  
  
5.  <span data-ttu-id="579a9-119">チャネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="579a9-119">Open the channel.</span></span>  
  
 <span data-ttu-id="579a9-120">コードまたは構成からバインディングとエンドポイント アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="579a9-120">You can specify the binding and endpoint address in your code or from configuration.</span></span>  
  
### <a name="specifying-the-binding-and-endpoint-address-in-code"></a><span data-ttu-id="579a9-121">コードでのバインディングとエンドポイント アドレスの指定</span><span class="sxs-lookup"><span data-stu-id="579a9-121">Specifying the Binding and Endpoint Address in Code</span></span>  
 <span data-ttu-id="579a9-122">次のコード例を作成する方法を示しています、 **IRequestChannel**コード内のバインドとエンドポイント アドレスを指定することによってです。</span><span class="sxs-lookup"><span data-stu-id="579a9-122">The following code example shows how to create an **IRequestChannel** by specifying the binding and endpoint address in code.</span></span> <span data-ttu-id="579a9-123">作成するコード、 **IOutputChannel**同じですが、指定する必要があります、 **IOutputChannel**のためのインターフェイス、 **ChannelFactory**チャネルの種類とします。</span><span class="sxs-lookup"><span data-stu-id="579a9-123">The code to create an **IOutputChannel** is the same except that you must specify an **IOutputChannel** interface for the **ChannelFactory** and channel type.</span></span>  
  
```  
// Create binding -- set binding properties before you open the factory.  
SAPBinding sapBinding = new SAPBinding();  
  
// Create address.  
EndpointAddress sapAddress = new EndpointAddress("sap://Client=800;lang=EN@A/YourSAPHost/00");  
  
// Create channel factory from binding and address.  
ChannelFactory<IRequestChannel> factory =   
    new ChannelFactory<IRequestChannel>(sapBinding, sapAddress);  
  
// Specify credentials.   
factory.Credentials.UserName.UserName = "YourUserName";  
factory.Credentials.UserName.Password = "YourPassword";  
  
// Open the factory  
factory.Open();  
  
// Get channel and open it.  
IRequestChannel channel = factory.CreateChannel();  
channel.Open();  
```  
  
### <a name="specifying-the-binding-and-endpoint-address-in-configuration"></a><span data-ttu-id="579a9-124">構成でバインディングとエンドポイント アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="579a9-124">Specifying the Binding and Endpoint Address in Configuration</span></span>  
 <span data-ttu-id="579a9-125">次のコード例では、構成で指定されたクライアント エンドポイントからチャネル ファクトリを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="579a9-125">The following code example shows how to create a channel factory from a client endpoint specified in configuration.</span></span>  
  
```  
// Create channel factory from configuration.  
ChannelFactory<IRequestChannel> factory =  
new ChannelFactory<IRequestChannel>("MyRequestChannel");  
  
// Specify credentials.  
factory.Credentials.UserName.UserName = "YourUserName";  
factory.Credentials.UserName.Password = "YourPassword";  
  
// Open the factory.  
factory.Open();  
  
// Get a channel and open it.  
IRequestChannel channel = factory.CreateChannel();  
channel.Open();  
```  
  
#### <a name="the-configuration-settings"></a><span data-ttu-id="579a9-126">構成設定</span><span class="sxs-lookup"><span data-stu-id="579a9-126">The Configuration Settings</span></span>  
 <span data-ttu-id="579a9-127">次のコードは、前述の例で使用される構成設定を示しています。</span><span class="sxs-lookup"><span data-stu-id="579a9-127">The following code shows the configuration settings used for the preceding example.</span></span> <span data-ttu-id="579a9-128">クライアント エンドポイントのコントラクトには、"System.ServiceModel.Channels.IRequestChannel"または"System.ServiceModel.Channels.IRequestChannel"を作成するチャネル形状の種類に応じてをする必要があります。</span><span class="sxs-lookup"><span data-stu-id="579a9-128">The contract for the client endpoint must be "System.ServiceModel.Channels.IRequestChannel" or "System.ServiceModel.Channels.IRequestChannel" depending on the kind of channel shape that you want to create.</span></span>  
  
```  
\<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    \<system.serviceModel>  
        <bindings>  
            <sapBinding>  
                <binding name="SAPBinding" closeTimeout="00:01:00" openTimeout="00:01:00"  
                    receiveTimeout="00:10:00" sendTimeout="00:01:00" enableBizTalkCompatibilityMode="false"  
                    receiveIdocFormat="Typed" enableSafeTyping="false" generateFlatFileCompatibleIdocSchema="true"  
                    maxConnectionsPerSystem="50" enableConnectionPooling="true"  
                    idleConnectionTimeout="00:15:00" flatFileSegmentIndicator="SegmentDefinition"  
                    enablePerformanceCounters="false" autoConfirmSentIdocs="false"  
                    acceptCredentialsInUri="false"  
                    padReceivedIdocWithSpaces="false" sncLibrary="" sncPartnerName="" />  
            </sapBinding>  
        </bindings>  
        <client>  
            <endpoint address="sap://CLIENT=800;LANG=EN;@a/ADAPSAP47/00?RfcSdkTrace=False&AbapDebug=False"  
                binding="sapBinding" bindingConfiguration="SAPBinding" contract="System.ServiceModel.Channels.IRequestChannel"  
                name="MyRequestChannel" />  
        </client>  
    \</system.serviceModel>  
</configuration>  
```  
  
### <a name="creating-inbound-service-channels"></a><span data-ttu-id="579a9-129">受信 (サービス) チャネルを作成します。</span><span class="sxs-lookup"><span data-stu-id="579a9-129">Creating Inbound (Service) Channels</span></span>  
 <span data-ttu-id="579a9-130">インスタンス上のバインドのプロパティを設定して、SAP システムから受信メッセージを受信するアダプターを構成する**SAPBinding**です。</span><span class="sxs-lookup"><span data-stu-id="579a9-130">You configure the adapter to receive inbound messages from an SAP system by setting binding properties on an instance of **SAPBinding**.</span></span> <span data-ttu-id="579a9-131">取得できますチャネル リスナーを作成し、このバインディングを使用する、 **IReplyChannel**アダプターからの受信操作へのチャネル。</span><span class="sxs-lookup"><span data-stu-id="579a9-131">You then use this binding to build a channel listener from which you can get an **IReplyChannel** channel to receive operations from the adapter.</span></span>  
  
##### <a name="to-create-and-open-an-ireplychannel-to-receive-data-changed-notifications"></a><span data-ttu-id="579a9-132">作成し、受信データの変更通知を IReplyChannel を開く</span><span class="sxs-lookup"><span data-stu-id="579a9-132">To create and open an IReplyChannel to Receive Data-changed Notifications</span></span>  
  
1.  <span data-ttu-id="579a9-133">インスタンスを作成する**SAPBinding**です。</span><span class="sxs-lookup"><span data-stu-id="579a9-133">Create an instance of **SAPBinding**.</span></span>  
  
2.  <span data-ttu-id="579a9-134">受信する操作に必要なすべてのバインドのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="579a9-134">Set any binding properties required for the operations you want to receive.</span></span> <span data-ttu-id="579a9-135">設定して、 **AcceptCredentialsInUri**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="579a9-135">Be sure to set the **AcceptCredentialsInUri** binding property.</span></span>  
  
3.  <span data-ttu-id="579a9-136">作成、 **BindingParameterCollection**を追加し、 **InboundActionCollection**を受信する操作のアクションを格納しています。</span><span class="sxs-lookup"><span data-stu-id="579a9-136">Create a **BindingParameterCollection** and add an **InboundActionCollection** that contains the actions of the operations that you want to receive.</span></span> <span data-ttu-id="579a9-137">アダプターでは、その他のすべての操作の SAP システムに例外を返します。</span><span class="sxs-lookup"><span data-stu-id="579a9-137">The adapter will return an exception to the SAP system for all other operations.</span></span> <span data-ttu-id="579a9-138">このステップは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="579a9-138">This step is optional.</span></span> <span data-ttu-id="579a9-139">詳細については、次を参照してください。 [WCF チャネル モデルを使用して SAP システムからの受信操作の受信](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md)です。</span><span class="sxs-lookup"><span data-stu-id="579a9-139">For more information, see [Receiving Inbound Operations from the SAP System by Using the WCF Channel Model](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md).</span></span>  
  
4.  <span data-ttu-id="579a9-140">呼び出してチャネル リスナーを作成する**BuildChannelListener\<IReplyChannel >**メソッドを**SAPBinding**です。</span><span class="sxs-lookup"><span data-stu-id="579a9-140">Create a channel listener by invoking **BuildChannelListener\<IReplyChannel>** method on the **SAPBinding**.</span></span> <span data-ttu-id="579a9-141">このメソッドにパラメーターの 1 つとしては、SAP 接続 URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="579a9-141">You specify the SAP connection URI as one of the parameters to this method.</span></span> <span data-ttu-id="579a9-142">接続 URI は、SAP システムで、RFC 変換先のパラメーターを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="579a9-142">The connection URI must contain parameters for an RFC Destination on the SAP system.</span></span> <span data-ttu-id="579a9-143">SAP 接続 URI の詳細については、次を参照してください。、 [SAP システムの接続 URI を作成する](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="579a9-143">For more information about the SAP connection URI, see The [Create the SAP System Connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span> <span data-ttu-id="579a9-144">作成した場合、 **BindingParameterCollection**手順 3. も指定するこのチャネル リスナーを作成するときにします。</span><span class="sxs-lookup"><span data-stu-id="579a9-144">If you created a **BindingParameterCollection** in step 3, you also specify this when you create the channel listener.</span></span>  
  
5.  <span data-ttu-id="579a9-145">リスナーを開きます。</span><span class="sxs-lookup"><span data-stu-id="579a9-145">Open the listener.</span></span>  
  
6.  <span data-ttu-id="579a9-146">取得、 **IReplyChannel**チャネルを呼び出すことによって、 **AcceptChannel**リスナーのメソッドです。</span><span class="sxs-lookup"><span data-stu-id="579a9-146">Get an **IReplyChannel** channel by invoking the **AcceptChannel** method on listener.</span></span>  
  
7.  <span data-ttu-id="579a9-147">チャネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="579a9-147">Open the channel.</span></span>  
  
 <span data-ttu-id="579a9-148">次のコードは、チャネル リスナーを作成し、取得する方法を示します、 **IReplyChannel**アダプターからの受信操作にします。</span><span class="sxs-lookup"><span data-stu-id="579a9-148">The following code shows how to create a channel listener and get an **IReplyChannel** to receive operations from the adapter.</span></span>  
  
```  
// Create a binding and specify any binding properties required  
// for the opreations you want to receive  
SAPBinding binding = new SAPBinding();  
  
// Set AcceptCredentialsInUri because the URI must contain credentials.  
binding.AcceptCredentialsInUri = true;  
  
// Create an InboundActionCollection and add the message actions to listen for,  
// only the actions added to the InboundActionCollection are received on the channel.  
// In this case a single action is specified: http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_ADD  
InboundActionCollection actions = new InboundActionCollection(listeneraddress);  
actions.Add("http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_ADD");  
  
// Create a BindingParameterCollection and add the InboundActionCollection  
BindingParameterCollection bpcol = new BindingParameterCollection();  
bpcol.Add(actions);  
  
// Create the channel listener by specifying  
// the binding parameter collection (to filter for the Z_RFC_MKD_ADD action) and   
// a connection URI that contains listener parameters.  
Uri listeneraddress =  
new Uri("sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?ListenerGwServ=SAPGATEWAY&ListenerGwHost=YourSAPHost&ListenerProgramId=SAPAdapter");  
listener = binding.BuildChannelListener<IReplyChannel>(connectionUri, new BindingParameterCollection());  
listener.Open();  
  
// Get a channel from the listener and open it.  
channel = listener.AcceptChannel();  
channel.Open();  
```  
  
## <a name="see-also"></a><span data-ttu-id="579a9-149">参照</span><span class="sxs-lookup"><span data-stu-id="579a9-149">See Also</span></span>  
[<span data-ttu-id="579a9-150">WCF チャネル モデルを使用してアプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="579a9-150">Develop applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)