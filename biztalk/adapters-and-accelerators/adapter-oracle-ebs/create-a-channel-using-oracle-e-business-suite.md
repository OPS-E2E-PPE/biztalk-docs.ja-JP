---
title: "Oracle E-business Suite を使用してチャネルを作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d18b7c2f-a43e-4499-ba94-4955dd5fe641
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d0f06a8f1e8b622574f20f331069d7ca280fc45c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="create-a-channel-using-oracle-e-business-suite"></a><span data-ttu-id="972e1-102">Oracle E-business Suite を使用して、チャネルを作成します。</span><span class="sxs-lookup"><span data-stu-id="972e1-102">Create a channel using Oracle E-Business Suite</span></span>
<span data-ttu-id="972e1-103">モデルでは、WCF チャネル、Oracle E-business Suite に対する操作を呼び出すし、SOAP メッセージを交換することで、結果を受け取る、 [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] WCF チャネルを経由します。</span><span class="sxs-lookup"><span data-stu-id="972e1-103">In the WCF channel model, you invoke operations on the Oracle E-Business Suite and receive the results by exchanging SOAP messages with the [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] over a WCF channel.</span></span>  
  
-   <span data-ttu-id="972e1-104">いずれかを使用して操作 (送信操作) を呼び出し、 **IRequestChannel**または**IOutputChannel**アダプターにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="972e1-104">You invoke operations (outbound operations) by using either an **IRequestChannel** or an **IOutputChannel** to send messages to the adapter.</span></span>  
  
-   <span data-ttu-id="972e1-105">受信操作のメッセージを受信する**IInputChannel**です。</span><span class="sxs-lookup"><span data-stu-id="972e1-105">You receive messages for inbound operations over an **IInputChannel**.</span></span>  
  
 <span data-ttu-id="972e1-106">このセクションのトピックでは、作成して、着信および発信の操作に使用されるチャネル形状を構成する方法に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="972e1-106">The topics in this section provide information about how to create and configure channel shapes that are used for inbound and outbound operations.</span></span>  
  
## <a name="creating-outbound-client-channels"></a><span data-ttu-id="972e1-107">送信 (クライアント) チャネルを作成します。</span><span class="sxs-lookup"><span data-stu-id="972e1-107">Creating Outbound (Client) Channels</span></span>  
 <span data-ttu-id="972e1-108">いずれかを使用することができます、 **IRequestChannel**または**IOutputChannel** Oracle E-business Suite での操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="972e1-108">You can use either an **IRequestChannel** or an **IOutputChannel** to invoke operations on the Oracle E-Business Suite.</span></span> <span data-ttu-id="972e1-109">作成する最初のどちらの場合、 **System.ServiceModel.ChannelFactory**適切なインターフェイスを使用します。</span><span class="sxs-lookup"><span data-stu-id="972e1-109">In either case, you first create a **System.ServiceModel.ChannelFactory** using the appropriate interface.</span></span> <span data-ttu-id="972e1-110">チャネルを作成するのにファクトリを使用します。</span><span class="sxs-lookup"><span data-stu-id="972e1-110">You then use the factory to create the channel.</span></span> <span data-ttu-id="972e1-111">チャネルを作成した後は、アダプターの操作の呼び出しに使用できます。</span><span class="sxs-lookup"><span data-stu-id="972e1-111">After you have created the channel you can use it to invoke operations on the adapter.</span></span>  
  
#### <a name="to-create-and-open-an-outbound-channel"></a><span data-ttu-id="972e1-112">作成および送信チャネルを開く</span><span class="sxs-lookup"><span data-stu-id="972e1-112">To create and open an outbound channel</span></span>  
  
1.  <span data-ttu-id="972e1-113">作成しのインスタンスを初期化**ChannelFactory**のエンドポイントとバインディングを使用して必要なチャネル形状です。</span><span class="sxs-lookup"><span data-stu-id="972e1-113">Create and initialize an instance of **ChannelFactory** for the desired channel shape by using an endpoint and a binding.</span></span> <span data-ttu-id="972e1-114">エンドポイントは、Oracle E-business Suite 接続 URI を指定し、バインディングは、インスタンスの**OracleEBSBinding**です。</span><span class="sxs-lookup"><span data-stu-id="972e1-114">The endpoint specifies an Oracle E-Business Suite connection URI and the binding is an instance of **OracleEBSBinding**.</span></span>  
  
2.  <span data-ttu-id="972e1-115">使用してチャネル ファクトリの Oracle E-business Suite の資格情報を提供、**資格情報**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="972e1-115">Provide Oracle E-Business Suite credentials for the channel factory by using the **Credentials** property.</span></span>  
  
3.  <span data-ttu-id="972e1-116">チャネル ファクトリを開きます。</span><span class="sxs-lookup"><span data-stu-id="972e1-116">Open the channel factory.</span></span>  
  
4.  <span data-ttu-id="972e1-117">呼び出すことによって、チャネルのインスタンスを取得、 **CreateChannel**チャネル ファクトリでのメソッドです。</span><span class="sxs-lookup"><span data-stu-id="972e1-117">Get an instance of the channel by invoking the **CreateChannel** method on the channel factory.</span></span>  
  
5.  <span data-ttu-id="972e1-118">チャネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="972e1-118">Open the channel.</span></span>  
  
 <span data-ttu-id="972e1-119">コードまたは構成からバインディングとエンドポイント アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="972e1-119">You can specify the binding and endpoint address in your code or from configuration.</span></span>  
  
### <a name="specifying-the-binding-and-endpoint-address-in-code"></a><span data-ttu-id="972e1-120">コードでのバインディングとエンドポイント アドレスの指定</span><span class="sxs-lookup"><span data-stu-id="972e1-120">Specifying the Binding and Endpoint Address in Code</span></span>  
 <span data-ttu-id="972e1-121">次のコード例を作成する方法を示しています、 **IRequestChannel**コード内のバインドとエンドポイント アドレスを指定することによってです。</span><span class="sxs-lookup"><span data-stu-id="972e1-121">The following code example shows how to create an **IRequestChannel** by specifying the binding and endpoint address in code.</span></span> <span data-ttu-id="972e1-122">作成するコード、 **IOutputChannel**同じですが、指定する必要があります、 **IOutputChannel**のためのインターフェイス、 **ChannelFactory**チャネルの種類とします。</span><span class="sxs-lookup"><span data-stu-id="972e1-122">The code to create an **IOutputChannel** is the same except that you must specify an **IOutputChannel** interface for the **ChannelFactory** and channel type.</span></span>  
  
```  
// Create binding -- set binding properties before you open the factory.  
OracleEBSBinding binding = new OracleEBSBinding();  
  
// Create address  
EndpointAddress address = new EndpointAddress("oracleebs://<oracleebs_instance_name>/");  
  
// Create channel factory from binding and address.  
ChannelFactory<IRequestChannel> factory =   
    new ChannelFactory<IRequestChannel>(binding, address);  
  
// Specify credentials.   
factory.Credentials.UserName.UserName = "myuser";  
factory.Credentials.UserName.Password = "mypassword";  
  
// Open factory  
factory.Open();  
  
// Get channel and open it.  
IRequestChannel channel = factory.CreateChannel();  
channel.Open();  
```  
  
### <a name="specifying-the-binding-and-endpoint-address-in-configuration"></a><span data-ttu-id="972e1-123">構成でバインディングとエンドポイント アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="972e1-123">Specifying the Binding and Endpoint Address in Configuration</span></span>  
 <span data-ttu-id="972e1-124">次のコード例では、構成で指定されたクライアント エンドポイントからチャネル ファクトリを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="972e1-124">The following code example shows how to create a channel factory from a client endpoint specified in configuration.</span></span>  
  
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
  
#### <a name="the-configuration-settings"></a><span data-ttu-id="972e1-125">構成設定</span><span class="sxs-lookup"><span data-stu-id="972e1-125">The Configuration Settings</span></span>  
 <span data-ttu-id="972e1-126">次のコードは、前述の例で使用される構成設定を示しています。</span><span class="sxs-lookup"><span data-stu-id="972e1-126">The following code shows the configuration settings used for the preceding example.</span></span> <span data-ttu-id="972e1-127">クライアント エンドポイントのコントラクトには、"System.ServiceModel.Channels.IRequestChannel"または"System.ServiceModel.Channels.IOutputChannel"を作成するチャネル形状の種類に応じてをする必要があります。</span><span class="sxs-lookup"><span data-stu-id="972e1-127">The contract for the client endpoint must be "System.ServiceModel.Channels.IRequestChannel" or "System.ServiceModel.Channels.IOutputChannel" depending on the kind of channel shape that you want to create.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    <system.serviceModel>  
        <bindings>  
            <oracleEBSBinding>  
                <binding openTimeout="00:05:00" name="OracleEBSBinding" closeTimeout="00:01:00"  
                    receiveTimeout="00:10:00" sendTimeout="00:01:00" clientCredentialType="Database"  
                    inboundOperationType="Polling" metadataPooling="true" statementCachePurge="false"  
                    statementCacheSize="10" pollWhileDataFound="false" pollingInterval="30"  
                    useOracleConnectionPool="true" minPoolSize="1" maxPoolSize="100"  
                    incrPoolSize="5" decrPoolSize="1" connectionLifetime="0" acceptCredentialsInUri="false"  
                    useAmbientTransaction="true" notifyOnListenerStart="true"  
                    notificationPort="-1" dataFetchSize="65536" longDatatypeColumnSize="0"  
                    skipNilNodes="true" maxOutputAssociativeArrayElements="32"  
                    enableSafeTyping="false" insertBatchSize="20" useSchemaInNameSpace="true"  
                    enableBizTalkCompatibilityMode="true" enablePerformanceCounters="false">  
                    <mlsSettings language="" dateFormat="" dateLanguage="" numericCharacters=""  
                        sort="" territory="" comparison="" currency="" dualCurrency=""  
                        iSOCurrency="" calendar="" lengthSemantics="" nCharConversionException="true"  
                        timeStampFormat="" timeStampTZFormat="" timeZone="" />  
                </binding>  
            </oracleEBSBinding>  
        </bindings>  
        <client>  
            <endpoint address="oracleebs://oracle_ebs_instance/" binding="oracleEBSBinding"  
                bindingConfiguration="OracleEBSBinding" contract="System.ServiceModel.Channels.IRequestChannel"  
                name="MyRequestChannel" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
### <a name="creating-inbound-service-channels"></a><span data-ttu-id="972e1-128">受信 (サービス) チャネルを作成します。</span><span class="sxs-lookup"><span data-stu-id="972e1-128">Creating Inbound (Service) Channels</span></span>  
 <span data-ttu-id="972e1-129">構成する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]インスタンス上のバインドのプロパティを設定して、Oracle データベースのテーブルとビューをポーリングする**OracleEBSBinding**です。</span><span class="sxs-lookup"><span data-stu-id="972e1-129">You configure the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to poll the Oracle database tables and views by setting binding properties on an instance of **OracleEBSBinding**.</span></span> <span data-ttu-id="972e1-130">取得できますチャネル リスナーを作成し、このバインディングを使用する、 **IInputChannel**アダプターから受信操作を受信するチャネル。</span><span class="sxs-lookup"><span data-stu-id="972e1-130">You then use this binding to build a channel listener from which you can get an **IInputChannel** channel to receive inbound operations from the adapter.</span></span>  
  
##### <a name="to-create-and-open-an-iinputchannel-to-receive-messages-for-inbound-operations"></a><span data-ttu-id="972e1-131">作成し、受信操作のメッセージを受信する IInputChannel を開く</span><span class="sxs-lookup"><span data-stu-id="972e1-131">To create and open an IInputChannel to receive messages for inbound operations</span></span>  
  
1.  <span data-ttu-id="972e1-132">インスタンスを作成する**OracleEBSBinding**です。</span><span class="sxs-lookup"><span data-stu-id="972e1-132">Create an instance of **OracleEBSBinding**.</span></span>  
  
2.  <span data-ttu-id="972e1-133">受信操作に必要なバインドのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="972e1-133">Set the binding properties required for the inbound operation.</span></span> <span data-ttu-id="972e1-134">たとえば、ポーリング操作の場合に、少なくとも必要があります設定する、 **InboundOperationType**、 **PolledDataAvailableStatement**、 **PollingAction**、および、 **PollingInput**バインドのプロパティを構成するのには[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]Oracle データベースをポーリングします。</span><span class="sxs-lookup"><span data-stu-id="972e1-134">For example, for a polling operation, at a minimum you must set the **InboundOperationType**, **PolledDataAvailableStatement**, **PollingAction**, and the **PollingInput** binding properties to configure the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to poll the Oracle database.</span></span>  
  
3.  <span data-ttu-id="972e1-135">バインディング パラメーター コレクションを使用して、作成、 **BindingParameterCollection**クラスし、資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="972e1-135">Create a binding parameter collection using the **BindingParameterCollection** class and set the credentials.</span></span>  
  
4.  <span data-ttu-id="972e1-136">呼び出してチャネル リスナーを作成する**BuildChannelListener\<IInputChannel\>** メソッドを**OracleEBSBinding**です。</span><span class="sxs-lookup"><span data-stu-id="972e1-136">Create a channel listener by invoking **BuildChannelListener\<IInputChannel\>** method on the **OracleEBSBinding**.</span></span> <span data-ttu-id="972e1-137">このメソッドに渡すパラメーターの 1 つとして、Oracle の接続 URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="972e1-137">You specify the Oracle connection URI as one of the parameters to this method.</span></span>  
  
5.  <span data-ttu-id="972e1-138">リスナーを開きます。</span><span class="sxs-lookup"><span data-stu-id="972e1-138">Open the listener.</span></span>  
  
6.  <span data-ttu-id="972e1-139">取得、 **IInputChannel**チャネルを呼び出すことによって、 **AcceptChannel**リスナーのメソッドです。</span><span class="sxs-lookup"><span data-stu-id="972e1-139">Get an **IInputChannel** channel by invoking the **AcceptChannel** method on listener.</span></span>  
  
7.  <span data-ttu-id="972e1-140">チャネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="972e1-140">Open the channel.</span></span>  
  
 <span data-ttu-id="972e1-141">次のコードは、チャネル リスナーを作成し、取得する方法を示します、 **IInputChannel**アダプターからの受信操作のメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="972e1-141">The following code shows how to create a channel listener and get an **IInputChannel** to receive messages for inbound operations from the adapter.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="972e1-142">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]受信の一方向のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="972e1-142">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] only supports one-way receive.</span></span> <span data-ttu-id="972e1-143">そのため、使用する必要があります**IInputChannel** Oracle E-business Suite からの受信操作のメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="972e1-143">So, you must use **IInputChannel** to receive messages for inbound operations from Oracle E-Business Suite.</span></span>  
  
```  
// Create a binding: specify the InboundOperationType, the PolledDataAvailableStatement, the PollingAction, and   
// the PollingInput binding properties.  
OracleEBSBinding binding = new OracleEBSBinding();  
binding.InboundOperationType = InboundOperation.Polling;  
binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE";  
binding.PollingAction = "InterfaceTables/Poll/FND/APPS/MS_SAMPLE_EMPLOYEE";  
binding.PollingInput = "SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE";  
  
// Create a binding parameter collection and set the credentials  
ClientCredentials credentials = new ClientCredentials();  
credentials.UserName.UserName = "myuser";  
credentials.UserName.Password = "mypassword";  
  
BindingParameterCollection bindingParams = new BindingParameterCollection();  
bindingParams.Add(credentials);  
  
// Get a listener from the binding and open it.  
Uri connectionUri = new Uri("oracleebs://oracle_ebs_instance/");  
IChannelListener<IInputChannel> listener = binding.BuildChannelListener<IInputChannel>(connectionUri, bindingParams);  
listener.Open();  
  
// Get a channel from the listener and open it.  
IInputChannel channel = listener.AcceptChannel();  
channel.Open();  
```  
  
## <a name="see-also"></a><span data-ttu-id="972e1-144">参照</span><span class="sxs-lookup"><span data-stu-id="972e1-144">See Also</span></span>  
 [<span data-ttu-id="972e1-145">WCF チャネル モデルを使用して Oracle E-business Suite アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="972e1-145">Develop Oracle E-Business Suite applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)