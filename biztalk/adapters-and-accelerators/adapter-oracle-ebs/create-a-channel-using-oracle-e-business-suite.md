---
title: Oracle E-business Suite を使用してチャネルを作成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d18b7c2f-a43e-4499-ba94-4955dd5fe641
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 947dc1a0a2b602d1dbcce032f721998b9fc84a84
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984643"
---
# <a name="create-a-channel-using-oracle-e-business-suite"></a><span data-ttu-id="5b029-102">Oracle E-business Suite を使用してチャネルを作成します。</span><span class="sxs-lookup"><span data-stu-id="5b029-102">Create a channel using Oracle E-Business Suite</span></span>
<span data-ttu-id="5b029-103">WCF チャネル モデルで Oracle E-business suite 操作の呼び出しし、結果を受信するには、SOAP メッセージを交換する、 [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] WCF チャネルを経由します。</span><span class="sxs-lookup"><span data-stu-id="5b029-103">In the WCF channel model, you invoke operations on the Oracle E-Business Suite and receive the results by exchanging SOAP messages with the [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] over a WCF channel.</span></span>  
  
- <span data-ttu-id="5b029-104">いずれかを使用して操作 (送信操作) を呼び出し、 **IRequestChannel**または**IOutputChannel**アダプターにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="5b029-104">You invoke operations (outbound operations) by using either an **IRequestChannel** or an **IOutputChannel** to send messages to the adapter.</span></span>  
  
- <span data-ttu-id="5b029-105">受信操作のメッセージを受信する**IInputChannel**します。</span><span class="sxs-lookup"><span data-stu-id="5b029-105">You receive messages for inbound operations over an **IInputChannel**.</span></span>  
  
  <span data-ttu-id="5b029-106">このセクションのトピックでは、作成して、受信と送信操作に使用されるチャネル形状を構成する方法に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="5b029-106">The topics in this section provide information about how to create and configure channel shapes that are used for inbound and outbound operations.</span></span>  
  
## <a name="creating-outbound-client-channels"></a><span data-ttu-id="5b029-107">送信 (クライアント) チャネルを作成します。</span><span class="sxs-lookup"><span data-stu-id="5b029-107">Creating Outbound (Client) Channels</span></span>  
 <span data-ttu-id="5b029-108">いずれかを使用することができます、 **IRequestChannel**または**IOutputChannel** Oracle E-business suite 操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="5b029-108">You can use either an **IRequestChannel** or an **IOutputChannel** to invoke operations on the Oracle E-Business Suite.</span></span> <span data-ttu-id="5b029-109">作成する最初のどちらの場合、 **System.ServiceModel.ChannelFactory**適切なインターフェイスを使用します。</span><span class="sxs-lookup"><span data-stu-id="5b029-109">In either case, you first create a **System.ServiceModel.ChannelFactory** using the appropriate interface.</span></span> <span data-ttu-id="5b029-110">チャネルを作成するのにファクトリを使用します。</span><span class="sxs-lookup"><span data-stu-id="5b029-110">You then use the factory to create the channel.</span></span> <span data-ttu-id="5b029-111">チャネルを作成した後は、アダプターの操作の呼び出しに使用できます。</span><span class="sxs-lookup"><span data-stu-id="5b029-111">After you have created the channel you can use it to invoke operations on the adapter.</span></span>  
  
#### <a name="to-create-and-open-an-outbound-channel"></a><span data-ttu-id="5b029-112">作成し、送信チャネルを開く</span><span class="sxs-lookup"><span data-stu-id="5b029-112">To create and open an outbound channel</span></span>  
  
1. <span data-ttu-id="5b029-113">作成しのインスタンスを初期化**ChannelFactory**エンドポイントとバインディングを使用して必要なチャネル形状にします。</span><span class="sxs-lookup"><span data-stu-id="5b029-113">Create and initialize an instance of **ChannelFactory** for the desired channel shape by using an endpoint and a binding.</span></span> <span data-ttu-id="5b029-114">Oracle E-business Suite 接続 URI を指定する、エンドポイントとバインディングのインスタンスでは**OracleEBSBinding**します。</span><span class="sxs-lookup"><span data-stu-id="5b029-114">The endpoint specifies an Oracle E-Business Suite connection URI and the binding is an instance of **OracleEBSBinding**.</span></span>  
  
2. <span data-ttu-id="5b029-115">チャネル ファクトリを使用して Oracle E-business Suite の資格情報を提供、**資格情報**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="5b029-115">Provide Oracle E-Business Suite credentials for the channel factory by using the **Credentials** property.</span></span>  
  
3. <span data-ttu-id="5b029-116">チャネル ファクトリを開きます。</span><span class="sxs-lookup"><span data-stu-id="5b029-116">Open the channel factory.</span></span>  
  
4. <span data-ttu-id="5b029-117">呼び出すことによって、チャネルのインスタンスを取得、 **CreateChannel**チャネル ファクトリ メソッド。</span><span class="sxs-lookup"><span data-stu-id="5b029-117">Get an instance of the channel by invoking the **CreateChannel** method on the channel factory.</span></span>  
  
5. <span data-ttu-id="5b029-118">チャネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="5b029-118">Open the channel.</span></span>  
  
   <span data-ttu-id="5b029-119">コードまたは構成からバインディングとエンドポイント アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="5b029-119">You can specify the binding and endpoint address in your code or from configuration.</span></span>  
  
### <a name="specifying-the-binding-and-endpoint-address-in-code"></a><span data-ttu-id="5b029-120">バインディングとエンドポイント アドレスを指定するコード</span><span class="sxs-lookup"><span data-stu-id="5b029-120">Specifying the Binding and Endpoint Address in Code</span></span>  
 <span data-ttu-id="5b029-121">次のコード例は、作成する方法を示します、 **IRequestChannel**コードでバインディングとエンドポイント アドレスを指定しています。</span><span class="sxs-lookup"><span data-stu-id="5b029-121">The following code example shows how to create an **IRequestChannel** by specifying the binding and endpoint address in code.</span></span> <span data-ttu-id="5b029-122">作成するコード、 **IOutputChannel**する必要がありますを指定する以外には、同じ、 **IOutputChannel**のためのインターフェイス、 **ChannelFactory**チャネルの種類とします。</span><span class="sxs-lookup"><span data-stu-id="5b029-122">The code to create an **IOutputChannel** is the same except that you must specify an **IOutputChannel** interface for the **ChannelFactory** and channel type.</span></span>  
  
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
  
### <a name="specifying-the-binding-and-endpoint-address-in-configuration"></a><span data-ttu-id="5b029-123">構成では、バインディングとエンドポイント アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="5b029-123">Specifying the Binding and Endpoint Address in Configuration</span></span>  
 <span data-ttu-id="5b029-124">次のコード例では、構成で指定されたクライアント エンドポイントからチャネル ファクトリを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5b029-124">The following code example shows how to create a channel factory from a client endpoint specified in configuration.</span></span>  
  
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
  
#### <a name="the-configuration-settings"></a><span data-ttu-id="5b029-125">構成設定</span><span class="sxs-lookup"><span data-stu-id="5b029-125">The Configuration Settings</span></span>  
 <span data-ttu-id="5b029-126">次のコードでは、前の例に使用される構成設定を示します。</span><span class="sxs-lookup"><span data-stu-id="5b029-126">The following code shows the configuration settings used for the preceding example.</span></span> <span data-ttu-id="5b029-127">"System.ServiceModel.Channels.IRequestChannel"または"System.ServiceModel.Channels.IOutputChannel"を作成するチャネル形状の種類に応じて、クライアント エンドポイントのコントラクトがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b029-127">The contract for the client endpoint must be "System.ServiceModel.Channels.IRequestChannel" or "System.ServiceModel.Channels.IOutputChannel" depending on the kind of channel shape that you want to create.</span></span>  
  
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
  
### <a name="creating-inbound-service-channels"></a><span data-ttu-id="5b029-128">受信 (サービス) チャネルを作成します。</span><span class="sxs-lookup"><span data-stu-id="5b029-128">Creating Inbound (Service) Channels</span></span>  
 <span data-ttu-id="5b029-129">構成する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]のインスタンスにバインドのプロパティを設定して、Oracle データベースのテーブルとビューをポーリングする**OracleEBSBinding**します。</span><span class="sxs-lookup"><span data-stu-id="5b029-129">You configure the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to poll the Oracle database tables and views by setting binding properties on an instance of **OracleEBSBinding**.</span></span> <span data-ttu-id="5b029-130">取得できますチャネル リスナーを作成し、このバインディングを使用する、 **IInputChannel**アダプターから受信操作を受信するチャネル。</span><span class="sxs-lookup"><span data-stu-id="5b029-130">You then use this binding to build a channel listener from which you can get an **IInputChannel** channel to receive inbound operations from the adapter.</span></span>  
  
##### <a name="to-create-and-open-an-iinputchannel-to-receive-messages-for-inbound-operations"></a><span data-ttu-id="5b029-131">作成して開く、IInputChannel の受信操作のメッセージを受信するには</span><span class="sxs-lookup"><span data-stu-id="5b029-131">To create and open an IInputChannel to receive messages for inbound operations</span></span>  
  
1. <span data-ttu-id="5b029-132">インスタンスを作成**OracleEBSBinding**します。</span><span class="sxs-lookup"><span data-stu-id="5b029-132">Create an instance of **OracleEBSBinding**.</span></span>  
  
2. <span data-ttu-id="5b029-133">受信操作に必要なバインドのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="5b029-133">Set the binding properties required for the inbound operation.</span></span> <span data-ttu-id="5b029-134">たとえば、ポーリング操作の場合に、少なくとも必要があります設定する、 **InboundOperationType**、 **PolledDataAvailableStatement**、 **PollingAction**、および、 **PollingInput**バインドのプロパティを構成する、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle データベースをポーリングします。</span><span class="sxs-lookup"><span data-stu-id="5b029-134">For example, for a polling operation, at a minimum you must set the **InboundOperationType**, **PolledDataAvailableStatement**, **PollingAction**, and the **PollingInput** binding properties to configure the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to poll the Oracle database.</span></span>  
  
3. <span data-ttu-id="5b029-135">使用してバインド パラメーターのコレクションを作成、 **BindingParameterCollection**クラスし、資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="5b029-135">Create a binding parameter collection using the **BindingParameterCollection** class and set the credentials.</span></span>  
  
4. <span data-ttu-id="5b029-136">呼び出してチャネル リスナーを作成して**BuildChannelListener\<IInputChannel\>** メソッドを**OracleEBSBinding**します。</span><span class="sxs-lookup"><span data-stu-id="5b029-136">Create a channel listener by invoking **BuildChannelListener\<IInputChannel\>** method on the **OracleEBSBinding**.</span></span> <span data-ttu-id="5b029-137">このメソッドにパラメーターの 1 つとして、Oracle の接続 URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="5b029-137">You specify the Oracle connection URI as one of the parameters to this method.</span></span>  
  
5. <span data-ttu-id="5b029-138">リスナーを開きます。</span><span class="sxs-lookup"><span data-stu-id="5b029-138">Open the listener.</span></span>  
  
6. <span data-ttu-id="5b029-139">取得、 **IInputChannel**チャネルを呼び出すことによって、 **AcceptChannel**メソッド リスナーをします。</span><span class="sxs-lookup"><span data-stu-id="5b029-139">Get an **IInputChannel** channel by invoking the **AcceptChannel** method on listener.</span></span>  
  
7. <span data-ttu-id="5b029-140">チャネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="5b029-140">Open the channel.</span></span>  
  
   <span data-ttu-id="5b029-141">次のコードは、チャネル リスナーを作成し、取得する方法を示しています、 **IInputChannel**アダプターからの受信操作のメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="5b029-141">The following code shows how to create a channel listener and get an **IInputChannel** to receive messages for inbound operations from the adapter.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5b029-142">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]受信の一方向のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="5b029-142">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] only supports one-way receive.</span></span> <span data-ttu-id="5b029-143">そのため、使用する必要があります**IInputChannel** Oracle E-business Suite からの受信操作のメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="5b029-143">So, you must use **IInputChannel** to receive messages for inbound operations from Oracle E-Business Suite.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5b029-144">参照</span><span class="sxs-lookup"><span data-stu-id="5b029-144">See Also</span></span>  
 [<span data-ttu-id="5b029-145">WCF チャネル モデルを使用して Oracle E-business Suite のアプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="5b029-145">Develop Oracle E-Business Suite applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)