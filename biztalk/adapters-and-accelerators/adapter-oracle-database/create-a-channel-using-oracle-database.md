---
title: Oracle データベースを使用するチャネルの作成 |Microsoft Docs
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
ms.openlocfilehash: 18d3964cabfec2b1e33813e3811bfeb696cd4280
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972243"
---
# <a name="create-a-channel-using-oracle-database"></a>Oracle データベースを使用してチャネルを作成します。
WCF チャネル モデルで、Oracle データベースに対する操作を呼び出すし、ポーリング クエリの結果を受信するには、SOAP メッセージを交換する、 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] WCF チャネルを経由します。  
  
- いずれかを使用して操作 (送信操作) を呼び出し、 **IRequestChannel**または**IOutputChannel**アダプターにメッセージを送信します。  
  
- を介して POLLINGSTMT メッセージを受信してポーリングに基づいたデータ変更メッセージを受信する、 **IInputChannel**します。  
  
  このセクションのトピックでは、作成して、受信と送信操作に使用されるチャネル形状を構成する方法に関する情報を提供します。  
  
## <a name="creating-outbound-client-channels"></a>送信 (クライアント) チャネルを作成します。  
 いずれかを使用することができます、 **IRequestChannel**または**IOutputChannel** Oracle データベースで操作を呼び出します。 作成する最初のどちらの場合、 **System.ServiceModel.ChannelFactory**適切なインターフェイスを使用します。 チャネルを作成するのにファクトリを使用します。 チャネルを作成した後は、アダプターの操作の呼び出しに使用できます。  
  
#### <a name="to-create-and-open-an-outbound-channel"></a>作成し、送信チャネルを開く  
  
1. 作成しのインスタンスを初期化**ChannelFactory**エンドポイントとバインディングを使用して必要なチャネル形状にします。 エンドポイントは、Oracle の接続 URI を指定し、バインディングのインスタンスである**OracleDBBinding**します。  
  
2. 使用してチャネル ファクトリの Oracle 資格情報を提供、**資格情報**プロパティ。  
  
3. チャネル ファクトリを開きます。  
  
4. 呼び出すことによって、チャネルのインスタンスを取得、 **CreateChannel**チャネル ファクトリ メソッド。  
  
5. チャネルを開きます。  
  
   コードまたは構成からバインディングとエンドポイント アドレスを指定できます。  
  
### <a name="specifying-the-binding-and-endpoint-address-in-code"></a>バインディングとエンドポイント アドレスを指定するコード  
 次のコード例は、作成する方法を示します、 **IRequestChannel**コードでバインディングとエンドポイント アドレスを指定しています。 作成するコード、 **IOutputChannel**する必要がありますを指定する以外には、同じ、 **IOutputChannel**のためのインターフェイス、 **ChannelFactory**チャネルの種類とします。  
  
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
  
### <a name="specifying-the-binding-and-endpoint-address-in-configuration"></a>構成では、バインディングとエンドポイント アドレスを指定します。  
 次のコード例では、構成で指定されたクライアント エンドポイントからチャネル ファクトリを作成する方法を示します。  
  
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
  
#### <a name="the-configuration-settings"></a>構成設定  
 次のコードでは、前の例に使用される構成設定を示します。 "System.ServiceModel.Channels.IRequestChannel"または"System.ServiceModel.Channels.IRequestChannel"を作成するチャネル形状の種類に応じて、クライアント エンドポイントのコントラクトがある必要があります。  
  
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
  
### <a name="creating-inbound-service-channels"></a>受信 (サービス) チャネルを作成します。  
 構成する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]のインスタンスにバインドのプロパティを設定して、Oracle データベースのテーブルとビューをポーリングする**OracleDBBinding**します。 取得できますチャネル リスナーを作成し、このバインディングを使用する、 **IInputChannel**アダプターからの受信操作のメッセージを受信するチャネル。  
  
##### <a name="to-create-and-open-an-iinputchannel-to-receive-messages-for-inbound-operations"></a>作成して開く、IInputChannel の受信操作のメッセージを受信するには  
  
1. インスタンスを作成**OracleDBBinding**します。  
  
2. 受信操作に必要なバインドのプロパティを設定します。 たとえば、POLLINGSTMT 操作の場合に、少なくとも必要があります設定する、 **InboundOperationType**、 **PollingStatement**と**PollingInterval**プロパティのバインド構成、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースをポーリングします。  
  
3. 使用してバインド パラメーターのコレクションを作成、 **BindingParameterCollection**クラスし、資格情報を設定します。  
  
4. 呼び出してチャネル リスナーを作成して**BuildChannelListener\<IInputChannel\>** メソッドを**OracleDBBinding**します。 このメソッドにパラメーターの 1 つとして、Oracle の接続 URI を指定します。 Oracle の接続 URI の詳細については、[Oracle Database 接続 URI の作成](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)を参照してください。  
  
5. リスナーを開きます。  
  
6. 取得、 **IInputChannel**チャネルを呼び出すことによって、 **AcceptChannel**メソッド リスナーをします。  
  
7. チャネルを開きます。  
  
   次のコードは、チャネル リスナーを作成し、取得する方法を示しています、 **IInputChannel**に POLLINGSTMT 操作を使用して、アダプターからメッセージを受信します。  
  
> [!NOTE]
>  [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]受信の一方向のみをサポートします。 そのため、Oracle データベースからの受信操作のメッセージを受信 IInputChannel を使用する必要があります。  
  
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
  
## <a name="see-also"></a>参照  
 [WCF チャネル モデルを使用して Oracle データベース アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)