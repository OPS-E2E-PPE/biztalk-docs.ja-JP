---
title: "SQL アダプターを使用してチャネルを作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e86398f6-c835-46f8-814f-31e43b18970e
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c31146310b8c8b559fcd93d19362679b060cb42
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="create-a-channel-using-the-sql-adapter"></a>SQL アダプターを使用して、チャネルを作成します。
WCF チャネル モデルで、SQL Server データベースに対する操作を呼び出すし、SOAP メッセージを交換することで、結果を受け取る、 [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] WCF チャネルを経由します。  
  
-   いずれかを使用して送信操作を呼び出し、 **IRequestChannel**または**IOutputChannel**アダプターにメッセージを送信します。  
  
-   経由でメッセージを受信して受信操作用のメッセージを受信する、 **IInputChannel**の**ポーリング**、 **TypedPolling**、または**通知**操作します。  
  
 このトピックの手順では、作成して、着信および発信の操作に使用されるチャネル形状を構成する方法に関する情報を提供します。  
  
## <a name="creating-outbound-client-channels"></a>送信 (クライアント) チャネルを作成します。  
 いずれかを使用することができます、 **IRequestChannel**または**IOutputChannel** SQL Server データベースで操作を呼び出します。 作成する最初のどちらの場合、 **System.ServiceModel.ChannelFactory**適切なインターフェイスを使用します。 チャネルを作成するのにファクトリを使用します。 チャネルを作成した後は、アダプターの操作の呼び出しに使用できます。  
  
#### <a name="to-create-and-open-an-outbound-channel"></a>作成および送信チャネルを開く  
  
1.  作成しのインスタンスを初期化**ChannelFactory**のエンドポイントとバインディングを使用して必要なチャネル形状です。 エンドポイントは、SQL Server の接続 URI を指定し、バインディングは、インスタンスの**sqlBinding**です。  
  
2.  使用してチャネル ファクトリの SQL Server 資格情報を提供、**資格情報**プロパティです。  
  
3.  チャネル ファクトリを開きます。  
  
4.  呼び出すことによって、チャネルのインスタンスを取得、 **CreateChannel**チャネル ファクトリでのメソッドです。  
  
5.  チャネルを開きます。  
  
 コードまたは構成からバインディングとエンドポイント アドレスを指定できます。  
  
### <a name="specifying-the-binding-and-endpoint-address-in-code"></a>コードでのバインディングとエンドポイント アドレスの指定  
 次のコード例を作成する方法を示しています、 **IRequestChannel**コード内のバインドとエンドポイント アドレスを指定することによってです。 作成するコード、 **IOutputChannel**同じですが、指定する必要があります、 **IOutputChannel**のためのインターフェイス、 **ChannelFactory**チャネルの種類とします。  
  
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
  
### <a name="specifying-the-binding-and-endpoint-address-in-configuration"></a>構成でバインディングとエンドポイント アドレスを指定します。  
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
 次のコードは、前述の例で使用される構成設定を示しています。 クライアント エンドポイントのコントラクトには、"System.ServiceModel.Channels.IRequestChannel"または"System.ServiceModel.Channels.IOutputChannel"を作成するチャネル形状の種類に応じてをする必要があります。  
  
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
 構成する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]インスタンス上のバインドのプロパティを設定して、SQL Server データベースのテーブルとビューをポーリングする**sqlBinding**です。 取得できますチャネル リスナーを作成し、このバインディングを使用する、 **IInputChannel**を受信するチャネル、**ポーリング**、 **TypedPolling**、または**通知**アダプターから操作します。  
  
#### <a name="to-create-and-open-an-iinputchannel-to-receive-inbound-operations"></a>作成して、受信操作を受信する、IInputChannel を開く  
  
1.  インスタンスを作成する**SQLBinding**です。  
  
2.  受信操作に必要なバインドのプロパティを設定します。 たとえば、**ポーリング**に設定する必要が少なくとも、操作、 **InboundOperationType**、 **PolledDataAvailableStatement**、および**PollingStatement**バインドのプロパティを構成するのには[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を SQL Server データベースをポーリングします。  
  
3.  呼び出してチャネル リスナーを作成する**BuildChannelListener\<IInputChannel\>** メソッドを**SQLBinding**です。 このメソッドに渡すパラメーターの 1 つとして、SQL Server の接続 URI を指定します。  
  
4.  リスナーを開きます。  
  
5.  取得、 **IInputChannel**チャネルを呼び出すことによって、 **AcceptChannel**リスナーのメソッドです。  
  
6.  チャネルを開きます。  
  
 次のコードは、チャネル リスナーを作成し、取得する方法を示します、 **IInputChannel**アダプターからメッセージのデータ変更を受信します。  
  
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