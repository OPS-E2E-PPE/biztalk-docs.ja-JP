---
title: Oracle データベースを使用してチャネルを作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating a channel
- WCF channel model, creating a channel
- how to, create a channel
- channel programming, creating a channel
ms.assetid: a30156a0-5a5a-4418-be17-2e23c3716fc1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 413f62a679c0510be34289900b92188554e622c8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963680"
---
# <a name="create-a-channel-using-oracle-database"></a><span data-ttu-id="7c2a2-102">Oracle データベースを使用して、チャネルを作成します。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-102">Create a channel using Oracle Database</span></span>
<span data-ttu-id="7c2a2-103">モデルでは、WCF チャネル、Oracle データベースに対する操作を呼び出すし、SOAP メッセージを交換することで、ポーリング クエリの結果を受け取る、 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] WCF チャネルを経由します。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-103">In the WCF channel model, you invoke operations on the Oracle database and receive the results of a polling query by exchanging SOAP messages with the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] over a WCF channel.</span></span>  
  
-   <span data-ttu-id="7c2a2-104">いずれかを使用して操作 (送信操作) を呼び出し、 **IRequestChannel**または**IOutputChannel**アダプターにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-104">You invoke operations (outbound operations) by using either an **IRequestChannel** or an **IOutputChannel** to send messages to the adapter.</span></span>  
  
-   <span data-ttu-id="7c2a2-105">を介して POLLINGSTMT メッセージを受信してデータ変更のポーリングに基づいたメッセージを受信する、 **IInputChannel**です。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-105">You receive polling-based data-changed messages by receiving POLLINGSTMT messages over an **IInputChannel**.</span></span>  
  
 <span data-ttu-id="7c2a2-106">このセクションのトピックでは、作成して、着信および発信の操作に使用されるチャネル形状を構成する方法に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-106">The topics in this section provide information about how to create and configure channel shapes that are used for inbound and outbound operations.</span></span>  
  
## <a name="creating-outbound-client-channels"></a><span data-ttu-id="7c2a2-107">送信 (クライアント) チャネルを作成します。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-107">Creating Outbound (Client) Channels</span></span>  
 <span data-ttu-id="7c2a2-108">いずれかを使用することができます、 **IRequestChannel**または**IOutputChannel** Oracle データベースで操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-108">You can use either an **IRequestChannel** or an **IOutputChannel** to invoke operations on the Oracle database.</span></span> <span data-ttu-id="7c2a2-109">作成する最初のどちらの場合、 **System.ServiceModel.ChannelFactory**適切なインターフェイスを使用します。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-109">In either case, you first create a **System.ServiceModel.ChannelFactory** using the appropriate interface.</span></span> <span data-ttu-id="7c2a2-110">チャネルを作成するのにファクトリを使用します。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-110">You then use the factory to create the channel.</span></span> <span data-ttu-id="7c2a2-111">チャネルを作成した後は、アダプターの操作の呼び出しに使用できます。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-111">After you have created the channel you can use it to invoke operations on the adapter.</span></span>  
  
#### <a name="to-create-and-open-an-outbound-channel"></a><span data-ttu-id="7c2a2-112">作成および送信チャネルを開く</span><span class="sxs-lookup"><span data-stu-id="7c2a2-112">To create and open an outbound channel</span></span>  
  
1.  <span data-ttu-id="7c2a2-113">作成しのインスタンスを初期化**ChannelFactory**のエンドポイントとバインディングを使用して必要なチャネル形状です。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-113">Create and initialize an instance of **ChannelFactory** for the desired channel shape by using an endpoint and a binding.</span></span> <span data-ttu-id="7c2a2-114">エンドポイントは、Oracle 接続 URI を指定し、バインディングは、インスタンスの**OracleDBBinding**です。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-114">The endpoint specifies an Oracle connection URI and the binding is an instance of **OracleDBBinding**.</span></span>  
  
2.  <span data-ttu-id="7c2a2-115">使用してチャネル ファクトリの Oracle 資格情報を提供、**資格情報**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-115">Provide Oracle credentials for the channel factory by using the **Credentials** property.</span></span>  
  
3.  <span data-ttu-id="7c2a2-116">チャネル ファクトリを開きます。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-116">Open the channel factory.</span></span>  
  
4.  <span data-ttu-id="7c2a2-117">呼び出すことによって、チャネルのインスタンスを取得、 **CreateChannel**チャネル ファクトリでのメソッドです。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-117">Get an instance of the channel by invoking the **CreateChannel** method on the channel factory.</span></span>  
  
5.  <span data-ttu-id="7c2a2-118">チャネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-118">Open the channel.</span></span>  
  
 <span data-ttu-id="7c2a2-119">コードまたは構成からバインディングとエンドポイント アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-119">You can specify the binding and endpoint address in your code or from configuration.</span></span>  
  
### <a name="specifying-the-binding-and-endpoint-address-in-code"></a><span data-ttu-id="7c2a2-120">コードでのバインディングとエンドポイント アドレスの指定</span><span class="sxs-lookup"><span data-stu-id="7c2a2-120">Specifying the Binding and Endpoint Address in Code</span></span>  
 <span data-ttu-id="7c2a2-121">次のコード例を作成する方法を示しています、 **IRequestChannel**コード内のバインドとエンドポイント アドレスを指定することによってです。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-121">The following code example shows how to create an **IRequestChannel** by specifying the binding and endpoint address in code.</span></span> <span data-ttu-id="7c2a2-122">作成するコード、 **IOutputChannel**同じですが、指定する必要があります、 **IOutputChannel**のためのインターフェイス、 **ChannelFactory**チャネルの種類とします。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-122">The code to create an **IOutputChannel** is the same except that you must specify an **IOutputChannel** interface for the **ChannelFactory** and channel type.</span></span>  
  
```  
// Create binding -- set binding properties before you open the factory.  
OracleDBBinding odbBinding = new OracleDBBinding();  
  
// Create address.  
EndpointAddress odbAddress = new EndpointAddress("oracledb://ADAPTER/");  
  
// Create channel factory from binding and address.  
ChannelFactory<IRequestChannel> factory =   
    new ChannelFactory<IRequestChannel>(odbBinding, odbAddress);  
  
// Specify credentials.   
factory.Credentials.UserName.UserName = "SCOTT";  
factory.Credentials.UserName.Password = "TIGER";  
  
// Open factory  
factory.Open();  
  
// Get channel and open it  
IRequestChannel channel = factory.CreateChannel();  
channel.Open();  
```  
  
### <a name="specifying-the-binding-and-endpoint-address-in-configuration"></a><span data-ttu-id="7c2a2-123">構成でバインディングとエンドポイント アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-123">Specifying the Binding and Endpoint Address in Configuration</span></span>  
 <span data-ttu-id="7c2a2-124">次のコード例では、構成で指定されたクライアント エンドポイントからチャネル ファクトリを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-124">The following code example shows how to create a channel factory from a client endpoint specified in configuration.</span></span>  
  
```  
// Create channel factory from configuration.  
ChannelFactory<IRequestChannel> factory =  
new ChannelFactory<IRequestChannel>("MyRequestChannel");  
  
// Specify credentials.  
factory.Credentials.UserName.UserName = "SCOTT";  
factory.Credentials.UserName.Password = "TIGER";  
  
// Open the factory.  
factory.Open();  
  
// Get a channel and open it.  
IRequestChannel channel = factory.CreateChannel();  
channel.Open();  
```  
  
#### <a name="the-configuration-settings"></a><span data-ttu-id="7c2a2-125">構成設定</span><span class="sxs-lookup"><span data-stu-id="7c2a2-125">The Configuration Settings</span></span>  
 <span data-ttu-id="7c2a2-126">次のコードは、前述の例で使用される構成設定を示しています。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-126">The following code shows the configuration settings used for the preceding example.</span></span> <span data-ttu-id="7c2a2-127">クライアント エンドポイントのコントラクトには、"System.ServiceModel.Channels.IRequestChannel"または"System.ServiceModel.Channels.IRequestChannel"を作成するチャネル形状の種類に応じてをする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-127">The contract for the client endpoint must be "System.ServiceModel.Channels.IRequestChannel" or "System.ServiceModel.Channels.IRequestChannel" depending on the kind of channel shape that you want to create.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    <system.serviceModel>  
        <bindings>  
            <oracleDBBinding>  
                <binding name="OracleDBBinding" closeTimeout="00:01:00" openTimeout="00:01:00"  
                    receiveTimeout="00:10:00" sendTimeout="00:01:00" metadataPooling="true"  
                    statementCachePurge="false" statementCacheSize="10" pollingInterval="500"  
                    useOracleConnectionPool="true" minPoolSize="1" maxPoolSize="100"  
                    incrPoolSize="5" decrPoolSize="1" connectionLifetime="0" acceptCredentialsInUri="false"  
                    useAmbientTransaction="true" polledDataAvailableStatement="SELECT 1 FROM DUAL"  
                    pollWhileDataFound="false" notifyOnListenerStart="true" notificationPort="-1"  
                    inboundOperationType="Polling" dataFetchSize="65536" longDatatypeColumnSize="0"  
                    skipNilNodes="true" maxOutputAssociativeArrayElements="32"  
                    enableSafeTyping="false" insertBatchSize="1" useSchemaInNameSpace="true"  
                    enableBizTalkCompatibilityMode="false" enablePerformanceCounters="false" />  
            </oracleDBBinding>  
        </bindings>  
        <client>  
            <endpoint address="oracledb://adapter/" binding="oracleDBBinding"  
                bindingConfiguration="OracleDBBinding" contract="System.ServiceModel.Channels.IRequestChannel"  
                name="MyRequestChannel" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
### <a name="creating-inbound-service-channels"></a><span data-ttu-id="7c2a2-128">受信 (サービス) チャネルを作成します。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-128">Creating Inbound (Service) Channels</span></span>  
 <span data-ttu-id="7c2a2-129">構成する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]インスタンス上のバインドのプロパティを設定して、Oracle データベースのテーブルとビューをポーリングする**OracleDBBinding**です。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-129">You configure the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to poll the Oracle database tables and views by setting binding properties on an instance of **OracleDBBinding**.</span></span> <span data-ttu-id="7c2a2-130">取得できますチャネル リスナーを作成し、このバインディングを使用する、 **IInputChannel**アダプターからの受信操作のメッセージを受け取るチャネル。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-130">You then use this binding to build a channel listener from which you can get an **IInputChannel** channel to receive message for inbound operations from the adapter.</span></span>  
  
##### <a name="to-create-and-open-an-iinputchannel-to-receive-messages-for-inbound-operations"></a><span data-ttu-id="7c2a2-131">作成し、受信操作のメッセージを受信する IInputChannel を開く</span><span class="sxs-lookup"><span data-stu-id="7c2a2-131">To create and open an IInputChannel to receive messages for inbound operations</span></span>  
  
1.  <span data-ttu-id="7c2a2-132">インスタンスを作成する**OracleDBBinding**です。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-132">Create an instance of **OracleDBBinding**.</span></span>  
  
2.  <span data-ttu-id="7c2a2-133">受信操作に必要なバインドのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-133">Set the binding properties required for the inbound operation.</span></span> <span data-ttu-id="7c2a2-134">たとえば、POLLINGSTMT 操作は、最低限必要があります設定する、 **InboundOperationType**、 **PollingStatement**、および**PollingInterval**バインドのプロパティを構成、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースをポーリングします。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-134">For example, for the POLLINGSTMT operation, at a minimum you must set the **InboundOperationType**, **PollingStatement**, and **PollingInterval** binding properties to configure the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to poll the Oracle database.</span></span>  
  
3.  <span data-ttu-id="7c2a2-135">バインディング パラメーター コレクションを使用して、作成、 **BindingParameterCollection**クラスし、資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-135">Create a binding parameter collection using the **BindingParameterCollection** class and set the credentials.</span></span>  
  
4.  <span data-ttu-id="7c2a2-136">呼び出してチャネル リスナーを作成する**BuildChannelListener\<IInputChannel\>** メソッドを**OracleDBBinding**です。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-136">Create a channel listener by invoking **BuildChannelListener\<IInputChannel\>** method on the **OracleDBBinding**.</span></span> <span data-ttu-id="7c2a2-137">このメソッドに渡すパラメーターの 1 つとして、Oracle の接続 URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-137">You specify the Oracle connection URI as one of the parameters to this method.</span></span> <span data-ttu-id="7c2a2-138">Oracle の接続 URI の詳細については、次を参照してください。 [Oracle Database 接続 URI を作成する](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-138">For more information about the Oracle connection URI, see [Create the Oracle Database connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span></span>  
  
5.  <span data-ttu-id="7c2a2-139">リスナーを開きます。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-139">Open the listener.</span></span>  
  
6.  <span data-ttu-id="7c2a2-140">取得、 **IInputChannel**チャネルを呼び出すことによって、 **AcceptChannel**リスナーのメソッドです。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-140">Get an **IInputChannel** channel by invoking the **AcceptChannel** method on listener.</span></span>  
  
7.  <span data-ttu-id="7c2a2-141">チャネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-141">Open the channel.</span></span>  
  
 <span data-ttu-id="7c2a2-142">次のコードは、チャネル リスナーを作成し、取得する方法を示します、 **IInputChannel**に POLLINGSTMT 操作を使用してアダプターからメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-142">The following code shows how to create a channel listener and get an **IInputChannel** to inbound messages from the adapter using the POLLINGSTMT operation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7c2a2-143">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]受信の一方向のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-143">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] only supports one-way receive.</span></span> <span data-ttu-id="7c2a2-144">そのため、Oracle データベースからの受信操作のメッセージを受信するのに IInputChannel を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-144">So, you must use IInputChannel to receive messages for inbound operations from Oracle database.</span></span>  
  
```  
// Create a binding: specify the InboundOperationType, PollingInterval (in seconds), the PollingStatement, and  
// the PostPollStatement.  
OracleDBBinding binding = new OracleDBBinding();  
binding.InboundOperationType = InboundOperation.Polling;  
binding.PollingInterval = 30;  
binding.PollingStatement = "SELECT * FROM ACCOUNTACTIVITY FOR UPDATE";  
binding.PostPollStatement = "BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;";  
  
// Create a binding parameter collection and set the credentials  
ClientCredentials credentials = new ClientCredentials();  
credentials.UserName.UserName = "SCOTT";  
credentials.UserName.Password = "TIGER";  
  
BindingParameterCollection bindingParams = new BindingParameterCollection();  
bindingParams.Add(credentials);  
  
// Get a listener from the binding and open it.  
Uri connectionUri = new Uri("oracleDB://ADAPTER");  
IChannelListener<IInputChannel> listener = binding.BuildChannelListener<IInputChannel>(connectionUri, bindingParams);  
listener.Open();  
  
// Get a channel from the listener and open it.  
channel = listener.AcceptChannel();  
channel.Open();  
```  
  
## <a name="see-also"></a><span data-ttu-id="7c2a2-145">参照</span><span class="sxs-lookup"><span data-stu-id="7c2a2-145">See Also</span></span>  
 [<span data-ttu-id="7c2a2-146">WCF チャネル モデルを使用して Oracle データベース アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="7c2a2-146">Develop Oracle Database applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)