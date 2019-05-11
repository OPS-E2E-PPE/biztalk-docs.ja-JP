---
title: SQL アダプタを使用するチャネルの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e86398f6-c835-46f8-814f-31e43b18970e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2785fa83e344db4a73f91a8c80e381ee330e401c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369911"
---
# <a name="create-a-channel-using-the-sql-adapter"></a><span data-ttu-id="21cc9-102">SQL アダプタを使用するチャネルを作成します。</span><span class="sxs-lookup"><span data-stu-id="21cc9-102">Create a channel using the SQL adapter</span></span>
<span data-ttu-id="21cc9-103">WCF チャネル モデルで、SQL Server データベースに対する操作を呼び出すし、によって SOAP メッセージを交換することで、結果が表示される、 [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] WCF チャネルを経由します。</span><span class="sxs-lookup"><span data-stu-id="21cc9-103">In the WCF channel model, you invoke operations on the SQL Server database and receive the results by exchanging SOAP messages with the [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] over a WCF channel.</span></span>  
  
- <span data-ttu-id="21cc9-104">いずれかを使用して送信操作を呼び出す、 **IRequestChannel**または**IOutputChannel**アダプターにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="21cc9-104">You invoke outbound operations by using either an **IRequestChannel** or an **IOutputChannel** to send messages to the adapter.</span></span>  
  
- <span data-ttu-id="21cc9-105">経由でメッセージを受信して受信操作のメッセージを受信する、 **IInputChannel**の**ポーリング**、 **TypedPolling**、または**通知**操作。</span><span class="sxs-lookup"><span data-stu-id="21cc9-105">You receive messages for inbound operations by receiving messages over an **IInputChannel** for **Polling**, **TypedPolling**, or **Notification** operations.</span></span>  
  
  <span data-ttu-id="21cc9-106">このトピックの手順では、作成して、受信と送信操作に使用されるチャネル形状を構成する方法に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="21cc9-106">The procedures in this topic provide information about how to create and configure channel shapes that are used for inbound and outbound operations.</span></span>  
  
## <a name="creating-outbound-client-channels"></a><span data-ttu-id="21cc9-107">送信 (クライアント) チャネルを作成します。</span><span class="sxs-lookup"><span data-stu-id="21cc9-107">Creating Outbound (Client) Channels</span></span>  
 <span data-ttu-id="21cc9-108">いずれかを使用することができます、 **IRequestChannel**または**IOutputChannel**上の SQL Server データベース操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="21cc9-108">You can use either an **IRequestChannel** or an **IOutputChannel** to invoke operations on the SQL Server database.</span></span> <span data-ttu-id="21cc9-109">作成する最初のどちらの場合、 **System.ServiceModel.ChannelFactory**適切なインターフェイスを使用します。</span><span class="sxs-lookup"><span data-stu-id="21cc9-109">In either case, you first create a **System.ServiceModel.ChannelFactory** using the appropriate interface.</span></span> <span data-ttu-id="21cc9-110">チャネルを作成するのにファクトリを使用します。</span><span class="sxs-lookup"><span data-stu-id="21cc9-110">You then use the factory to create the channel.</span></span> <span data-ttu-id="21cc9-111">チャネルを作成した後は、アダプターの操作の呼び出しに使用できます。</span><span class="sxs-lookup"><span data-stu-id="21cc9-111">After you have created the channel you can use it to invoke operations on the adapter.</span></span>  
  
#### <a name="to-create-and-open-an-outbound-channel"></a><span data-ttu-id="21cc9-112">作成し、送信チャネルを開く</span><span class="sxs-lookup"><span data-stu-id="21cc9-112">To create and open an outbound channel</span></span>  
  
1. <span data-ttu-id="21cc9-113">作成しのインスタンスを初期化**ChannelFactory**エンドポイントとバインディングを使用して必要なチャネル形状にします。</span><span class="sxs-lookup"><span data-stu-id="21cc9-113">Create and initialize an instance of **ChannelFactory** for the desired channel shape by using an endpoint and a binding.</span></span> <span data-ttu-id="21cc9-114">エンドポイントは、SQL Server 接続 URI を指定し、バインディングのインスタンスである**sqlBinding**します。</span><span class="sxs-lookup"><span data-stu-id="21cc9-114">The endpoint specifies a SQL Server connection URI and the binding is an instance of **sqlBinding**.</span></span>  
  
2. <span data-ttu-id="21cc9-115">チャネル ファクトリを使用して SQL Server の資格情報を提供、**資格情報**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="21cc9-115">Provide SQL Server credentials for the channel factory by using the **Credentials** property.</span></span>  
  
3. <span data-ttu-id="21cc9-116">チャネル ファクトリを開きます。</span><span class="sxs-lookup"><span data-stu-id="21cc9-116">Open the channel factory.</span></span>  
  
4. <span data-ttu-id="21cc9-117">呼び出すことによって、チャネルのインスタンスを取得、 **CreateChannel**チャネル ファクトリ メソッド。</span><span class="sxs-lookup"><span data-stu-id="21cc9-117">Get an instance of the channel by invoking the **CreateChannel** method on the channel factory.</span></span>  
  
5. <span data-ttu-id="21cc9-118">チャネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="21cc9-118">Open the channel.</span></span>  
  
   <span data-ttu-id="21cc9-119">コードまたは構成からバインディングとエンドポイント アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="21cc9-119">You can specify the binding and endpoint address in your code or from configuration.</span></span>  
  
### <a name="specifying-the-binding-and-endpoint-address-in-code"></a><span data-ttu-id="21cc9-120">バインディングとエンドポイント アドレスを指定するコード</span><span class="sxs-lookup"><span data-stu-id="21cc9-120">Specifying the Binding and Endpoint Address in Code</span></span>  
 <span data-ttu-id="21cc9-121">次のコード例は、作成する方法を示します、 **IRequestChannel**コードでバインディングとエンドポイント アドレスを指定しています。</span><span class="sxs-lookup"><span data-stu-id="21cc9-121">The following code example shows how to create an **IRequestChannel** by specifying the binding and endpoint address in code.</span></span> <span data-ttu-id="21cc9-122">作成するコード、 **IOutputChannel**する必要がありますを指定する以外には、同じ、 **IOutputChannel**のためのインターフェイス、 **ChannelFactory**チャネルの種類とします。</span><span class="sxs-lookup"><span data-stu-id="21cc9-122">The code to create an **IOutputChannel** is the same except that you must specify an **IOutputChannel** interface for the **ChannelFactory** and channel type.</span></span>  
  
```  
// Create binding -- set binding properties before you open the factory.  
SqlAdapterBinding sdbBinding = new SqlAdapterBinding();  
  
// Create address.  
EndpointAddress sdbAddress = new EndpointAddress("mssql://<sql_server_name>//<database_name>?");  
  
// Create channel factory from binding and address.  
ChannelFactory<IRequestChannel> factory =   
    new ChannelFactory<IRequestChannel>(sdbBinding, sdbAddress);  
  
// Specify credentials.   
factory.Credentials.UserName.UserName = "myuser";  
factory.Credentials.UserName.Password = "mypassword";  
  
// Open factory  
factory.Open();  
  
// Get channel and open it.  
IRequestChannel channel = factory.CreateChannel();  
channel.Open();  
```  
  
### <a name="specifying-the-binding-and-endpoint-address-in-configuration"></a><span data-ttu-id="21cc9-123">構成では、バインディングとエンドポイント アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="21cc9-123">Specifying the Binding and Endpoint Address in Configuration</span></span>  
 <span data-ttu-id="21cc9-124">次のコード例では、構成で指定されたクライアント エンドポイントからチャネル ファクトリを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="21cc9-124">The following code example shows how to create a channel factory from a client endpoint specified in configuration.</span></span>  
  
```  
// Create channel factory from configuration.  
ChannelFactory<IRequestChannel> factory =  
new ChannelFactory<IRequestChannel>("MyRequestChannel");  
  
// Specify credentials.  
factory.Credentials.UserName.UserName = "myuser";  
factory.Credentials.UserName.Password = "mypassword";  
  
// Open the factory.  
factory.Open();  
  
// Get a channel and open it.  
IRequestChannel channel = factory.CreateChannel();  
channel.Open();  
```  
  
#### <a name="the-configuration-settings"></a><span data-ttu-id="21cc9-125">構成設定</span><span class="sxs-lookup"><span data-stu-id="21cc9-125">The Configuration Settings</span></span>  
 <span data-ttu-id="21cc9-126">次のコードでは、前の例に使用される構成設定を示します。</span><span class="sxs-lookup"><span data-stu-id="21cc9-126">The following code shows the configuration settings used for the preceding example.</span></span> <span data-ttu-id="21cc9-127">"System.ServiceModel.Channels.IRequestChannel"または"System.ServiceModel.Channels.IOutputChannel"を作成するチャネル形状の種類に応じて、クライアント エンドポイントのコントラクトがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="21cc9-127">The contract for the client endpoint must be "System.ServiceModel.Channels.IRequestChannel" or "System.ServiceModel.Channels.IOutputChannel" depending on the kind of channel shape that you want to create.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    <system.serviceModel>  
        <bindings>  
            <sqlBinding>  
                <binding name="SqlAdapterBinding" closeTimeout="00:01:00" openTimeout="00:01:00"  
                    receiveTimeout="00:10:00" sendTimeout="00:01:00" maxConnectionPoolSize="100"  
                    encrypt="false" useAmbientTransaction="true" batchSize="20"  
                    polledDataAvailableStatement="" pollingStatement="" pollingIntervalInSeconds="30"  
                    pollWhileDataFound="false" notificationStatement="" notifyOnListenerStart="true"  
                    enableBizTalkCompatibilityMode="true" chunkSize="4194304"  
                    inboundOperationType="Polling" useDatabaseNameInXsdNamespace="false"  
                    allowIdentityInsert="false" enablePerformanceCounters="false"  
                    xmlStoredProcedureRootNodeName="" xmlStoredProcedureRootNodeNamespace="" />  
            </sqlBinding>  
        </bindings>  
        <client>  
            <endpoint address="mssql://mysqlserver//mydatabase?" binding="sqlBinding"  
                bindingConfiguration="SqlAdapterBinding" contract="System.ServiceModel.Channels.IRequestChannel"  
                name="MyRequestChannel" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="creating-inbound-service-channels"></a><span data-ttu-id="21cc9-128">受信 (サービス) チャネルを作成します。</span><span class="sxs-lookup"><span data-stu-id="21cc9-128">Creating Inbound (Service) Channels</span></span>  
 <span data-ttu-id="21cc9-129">構成する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]のインスタンスにバインドのプロパティを設定して、SQL Server データベース テーブルとビューをポーリングする**sqlBinding**します。</span><span class="sxs-lookup"><span data-stu-id="21cc9-129">You configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to poll the SQL Server database tables and views by setting binding properties on an instance of **sqlBinding**.</span></span> <span data-ttu-id="21cc9-130">取得できますチャネル リスナーを作成し、このバインディングを使用する、 **IInputChannel**を受信するチャネル、**ポーリング**、 **TypedPolling**、または**通知**アダプターから操作します。</span><span class="sxs-lookup"><span data-stu-id="21cc9-130">You then use this binding to build a channel listener from which you can get an **IInputChannel** channel to receive the **Polling**, **TypedPolling**, or **Notification** operation from the adapter.</span></span>  
  
#### <a name="to-create-and-open-an-iinputchannel-to-receive-inbound-operations"></a><span data-ttu-id="21cc9-131">作成して開く、IInputChannel 受信操作を受信するには</span><span class="sxs-lookup"><span data-stu-id="21cc9-131">To create and open an IInputChannel to receive inbound operations</span></span>  
  
1. <span data-ttu-id="21cc9-132">インスタンスを作成**SQLBinding**します。</span><span class="sxs-lookup"><span data-stu-id="21cc9-132">Create an instance of **SQLBinding**.</span></span>  
  
2. <span data-ttu-id="21cc9-133">受信操作に必要なバインドのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="21cc9-133">Set the binding properties required for inbound operation.</span></span> <span data-ttu-id="21cc9-134">たとえば、**ポーリング**操作には、少なくともを設定する必要があります、 **InboundOperationType**、 **PolledDataAvailableStatement**、および**PollingStatement**バインドのプロパティを構成する、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL Server データベースをポーリングします。</span><span class="sxs-lookup"><span data-stu-id="21cc9-134">For example, for a **Polling** operation, at a minimum you must set the **InboundOperationType**, **PolledDataAvailableStatement**, and **PollingStatement** binding properties to configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to poll the SQL Server database.</span></span>  
  
3. <span data-ttu-id="21cc9-135">呼び出してチャネル リスナーを作成して**BuildChannelListener\<IInputChannel\>** メソッドを**SQLBinding**します。</span><span class="sxs-lookup"><span data-stu-id="21cc9-135">Create a channel listener by invoking **BuildChannelListener\<IInputChannel\>** method on the **SQLBinding**.</span></span> <span data-ttu-id="21cc9-136">このメソッドにパラメーターの 1 つとして、SQL Server の接続 URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="21cc9-136">You specify the SQL Server connection URI as one of the parameters to this method.</span></span>  
  
4. <span data-ttu-id="21cc9-137">リスナーを開きます。</span><span class="sxs-lookup"><span data-stu-id="21cc9-137">Open the listener.</span></span>  
  
5. <span data-ttu-id="21cc9-138">取得、 **IInputChannel**チャネルを呼び出すことによって、 **AcceptChannel**メソッド リスナーをします。</span><span class="sxs-lookup"><span data-stu-id="21cc9-138">Get an **IInputChannel** channel by invoking the **AcceptChannel** method on listener.</span></span>  
  
6. <span data-ttu-id="21cc9-139">チャネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="21cc9-139">Open the channel.</span></span>  
  
   <span data-ttu-id="21cc9-140">次のコードは、チャネル リスナーを作成し、取得する方法を示しています、 **IInputChannel**アダプターからのデータ変更メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="21cc9-140">The following code shows how to create a channel listener and get an **IInputChannel** to receive data-changed messages from the adapter.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="21cc9-141">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]受信の一方向のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="21cc9-141">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] only supports one-way receive.</span></span> <span data-ttu-id="21cc9-142">そのため、使用する必要があります**IInputChannel** SQL Server からの受信操作のメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="21cc9-142">So, you must use **IInputChannel** to receive messages for inbound operations from SQL Server.</span></span>  
  
```  
// Create a binding: specify the InboundOperationType, the PolledDataAvailableStatement, and   
// the PollingStatement binding properties.  
SqlAdapterBinding binding = new SqlAdapterBinding();  
binding.InboundOperationType = InboundOperation.Polling;  
binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  
  
// Create a binding parameter collection and set the credentials  
ClientCredentials credentials = new ClientCredentials();  
credentials.UserName.UserName = "myuser";  
credentials.UserName.Password = "mypassword";  
  
BindingParameterCollection bindingParams = new BindingParameterCollection();  
bindingParams.Add(credentials);  
  
// Get a listener from the binding and open it.  
Uri connectionUri = new Uri("mssql://mysqlserver//mydatabase?");  
IChannelListener<IInputChannel> listener = binding.BuildChannelListener<IInputChannel>(connectionUri, bindingParams);  
listener.Open();  
  
// Get a channel from the listener and open it.  
IInputChannel channel = listener.AcceptChannel();  
channel.Open();  
```  
  
## <a name="see-also"></a><span data-ttu-id="21cc9-143">参照</span><span class="sxs-lookup"><span data-stu-id="21cc9-143">See Also</span></span>  
[<span data-ttu-id="21cc9-144">WCF チャネル モデルを使用してアプリケーションを開発する</span><span class="sxs-lookup"><span data-stu-id="21cc9-144">Develop applications using the WCF Channel model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)