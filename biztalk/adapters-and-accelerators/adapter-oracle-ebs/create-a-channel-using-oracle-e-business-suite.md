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
# <a name="create-a-channel-using-oracle-e-business-suite"></a>Oracle E-business Suite を使用して、チャネルを作成します。
モデルでは、WCF チャネル、Oracle E-business Suite に対する操作を呼び出すし、SOAP メッセージを交換することで、結果を受け取る、 [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] WCF チャネルを経由します。  
  
-   いずれかを使用して操作 (送信操作) を呼び出し、 **IRequestChannel**または**IOutputChannel**アダプターにメッセージを送信します。  
  
-   受信操作のメッセージを受信する**IInputChannel**です。  
  
 このセクションのトピックでは、作成して、着信および発信の操作に使用されるチャネル形状を構成する方法に関する情報を提供します。  
  
## <a name="creating-outbound-client-channels"></a>送信 (クライアント) チャネルを作成します。  
 いずれかを使用することができます、 **IRequestChannel**または**IOutputChannel** Oracle E-business Suite での操作を呼び出します。 作成する最初のどちらの場合、 **System.ServiceModel.ChannelFactory**適切なインターフェイスを使用します。 チャネルを作成するのにファクトリを使用します。 チャネルを作成した後は、アダプターの操作の呼び出しに使用できます。  
  
#### <a name="to-create-and-open-an-outbound-channel"></a>作成および送信チャネルを開く  
  
1.  作成しのインスタンスを初期化**ChannelFactory**のエンドポイントとバインディングを使用して必要なチャネル形状です。 エンドポイントは、Oracle E-business Suite 接続 URI を指定し、バインディングは、インスタンスの**OracleEBSBinding**です。  
  
2.  使用してチャネル ファクトリの Oracle E-business Suite の資格情報を提供、**資格情報**プロパティです。  
  
3.  チャネル ファクトリを開きます。  
  
4.  呼び出すことによって、チャネルのインスタンスを取得、 **CreateChannel**チャネル ファクトリでのメソッドです。  
  
5.  チャネルを開きます。  
  
 コードまたは構成からバインディングとエンドポイント アドレスを指定できます。  
  
### <a name="specifying-the-binding-and-endpoint-address-in-code"></a>コードでのバインディングとエンドポイント アドレスの指定  
 次のコード例を作成する方法を示しています、 **IRequestChannel**コード内のバインドとエンドポイント アドレスを指定することによってです。 作成するコード、 **IOutputChannel**同じですが、指定する必要があります、 **IOutputChannel**のためのインターフェイス、 **ChannelFactory**チャネルの種類とします。  
  
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
  
### <a name="creating-inbound-service-channels"></a>受信 (サービス) チャネルを作成します。  
 構成する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]インスタンス上のバインドのプロパティを設定して、Oracle データベースのテーブルとビューをポーリングする**OracleEBSBinding**です。 取得できますチャネル リスナーを作成し、このバインディングを使用する、 **IInputChannel**アダプターから受信操作を受信するチャネル。  
  
##### <a name="to-create-and-open-an-iinputchannel-to-receive-messages-for-inbound-operations"></a>作成し、受信操作のメッセージを受信する IInputChannel を開く  
  
1.  インスタンスを作成する**OracleEBSBinding**です。  
  
2.  受信操作に必要なバインドのプロパティを設定します。 たとえば、ポーリング操作の場合に、少なくとも必要があります設定する、 **InboundOperationType**、 **PolledDataAvailableStatement**、 **PollingAction**、および、 **PollingInput**バインドのプロパティを構成するのには[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]Oracle データベースをポーリングします。  
  
3.  バインディング パラメーター コレクションを使用して、作成、 **BindingParameterCollection**クラスし、資格情報を設定します。  
  
4.  呼び出してチャネル リスナーを作成する**BuildChannelListener\<IInputChannel\>** メソッドを**OracleEBSBinding**です。 このメソッドに渡すパラメーターの 1 つとして、Oracle の接続 URI を指定します。  
  
5.  リスナーを開きます。  
  
6.  取得、 **IInputChannel**チャネルを呼び出すことによって、 **AcceptChannel**リスナーのメソッドです。  
  
7.  チャネルを開きます。  
  
 次のコードは、チャネル リスナーを作成し、取得する方法を示します、 **IInputChannel**アダプターからの受信操作のメッセージを受信します。  
  
> [!IMPORTANT]
>  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]受信の一方向のみをサポートします。 そのため、使用する必要があります**IInputChannel** Oracle E-business Suite からの受信操作のメッセージを受信します。  
  
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
  
## <a name="see-also"></a>参照  
 [WCF チャネル モデルを使用して Oracle E-business Suite アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)