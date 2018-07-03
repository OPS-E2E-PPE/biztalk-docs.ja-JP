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
ms.openlocfilehash: fe06da3c9aa53fcf55acab05cdefaef8b3d1293e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002419"
---
# <a name="create-a-channel-using-the-sql-adapter"></a>SQL アダプタを使用するチャネルを作成します。
WCF チャネル モデルで、SQL Server データベースに対する操作を呼び出すし、によって SOAP メッセージを交換することで、結果が表示される、 [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] WCF チャネルを経由します。  
  
- いずれかを使用して送信操作を呼び出す、 **IRequestChannel**または**IOutputChannel**アダプターにメッセージを送信します。  
  
- 経由でメッセージを受信して受信操作のメッセージを受信する、 **IInputChannel**の**ポーリング**、 **TypedPolling**、または**通知**操作。  
  
  このトピックの手順では、作成して、受信と送信操作に使用されるチャネル形状を構成する方法に関する情報を提供します。  
  
## <a name="creating-outbound-client-channels"></a>送信 (クライアント) チャネルを作成します。  
 いずれかを使用することができます、 **IRequestChannel**または**IOutputChannel**上の SQL Server データベース操作を呼び出します。 作成する最初のどちらの場合、 **System.ServiceModel.ChannelFactory**適切なインターフェイスを使用します。 チャネルを作成するのにファクトリを使用します。 チャネルを作成した後は、アダプターの操作の呼び出しに使用できます。  
  
#### <a name="to-create-and-open-an-outbound-channel"></a>作成し、送信チャネルを開く  
  
1. 作成しのインスタンスを初期化**ChannelFactory**エンドポイントとバインディングを使用して必要なチャネル形状にします。 エンドポイントは、SQL Server 接続 URI を指定し、バインディングのインスタンスである**sqlBinding**します。  
  
2. チャネル ファクトリを使用して SQL Server の資格情報を提供、**資格情報**プロパティ。  
  
3. チャネル ファクトリを開きます。  
  
4. 呼び出すことによって、チャネルのインスタンスを取得、 **CreateChannel**チャネル ファクトリ メソッド。  
  
5. チャネルを開きます。  
  
   コードまたは構成からバインディングとエンドポイント アドレスを指定できます。  
  
### <a name="specifying-the-binding-and-endpoint-address-in-code"></a>バインディングとエンドポイント アドレスを指定するコード  
 次のコード例は、作成する方法を示します、 **IRequestChannel**コードでバインディングとエンドポイント アドレスを指定しています。 作成するコード、 **IOutputChannel**する必要がありますを指定する以外には、同じ、 **IOutputChannel**のためのインターフェイス、 **ChannelFactory**チャネルの種類とします。  
  
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
  
### <a name="specifying-the-binding-and-endpoint-address-in-configuration"></a>構成では、バインディングとエンドポイント アドレスを指定します。  
 次のコード例では、構成で指定されたクライアント エンドポイントからチャネル ファクトリを作成する方法を示します。  
  
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
  
#### <a name="the-configuration-settings"></a>構成設定  
 次のコードでは、前の例に使用される構成設定を示します。 "System.ServiceModel.Channels.IRequestChannel"または"System.ServiceModel.Channels.IOutputChannel"を作成するチャネル形状の種類に応じて、クライアント エンドポイントのコントラクトがある必要があります。  
  
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
  
## <a name="creating-inbound-service-channels"></a>受信 (サービス) チャネルを作成します。  
 構成する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]のインスタンスにバインドのプロパティを設定して、SQL Server データベース テーブルとビューをポーリングする**sqlBinding**します。 取得できますチャネル リスナーを作成し、このバインディングを使用する、 **IInputChannel**を受信するチャネル、**ポーリング**、 **TypedPolling**、または**通知**アダプターから操作します。  
  
#### <a name="to-create-and-open-an-iinputchannel-to-receive-inbound-operations"></a>作成して開く、IInputChannel 受信操作を受信するには  
  
1. インスタンスを作成**SQLBinding**します。  
  
2. 受信操作に必要なバインドのプロパティを設定します。 たとえば、**ポーリング**操作には、少なくともを設定する必要があります、 **InboundOperationType**、 **PolledDataAvailableStatement**、および**PollingStatement**バインドのプロパティを構成する、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL Server データベースをポーリングします。  
  
3. 呼び出してチャネル リスナーを作成して**BuildChannelListener\<IInputChannel\>** メソッドを**SQLBinding**します。 このメソッドにパラメーターの 1 つとして、SQL Server の接続 URI を指定します。  
  
4. リスナーを開きます。  
  
5. 取得、 **IInputChannel**チャネルを呼び出すことによって、 **AcceptChannel**メソッド リスナーをします。  
  
6. チャネルを開きます。  
  
   次のコードは、チャネル リスナーを作成し、取得する方法を示しています、 **IInputChannel**アダプターからのデータ変更メッセージを受信します。  
  
> [!IMPORTANT]
>  [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]受信の一方向のみをサポートします。 そのため、使用する必要があります**IInputChannel** SQL Server からの受信操作のメッセージを受信します。  
  
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
  
## <a name="see-also"></a>参照  
[WCF チャネル モデルを使用してアプリケーションを開発する](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)