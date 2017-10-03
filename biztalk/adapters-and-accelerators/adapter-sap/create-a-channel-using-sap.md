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
# <a name="create-a-channel-using-sap"></a>SAP を使用して、チャネルを作成します。
WCF チャネル モデルでの SAP システムに対する操作を呼び出すまたは SOAP メッセージを交換することで、SAP システムからメッセージを受信、 [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] WCF チャネルを経由します。  
  
-   いずれかを使用して操作 (送信操作) を呼び出し、 **IRequestChannel**または**IOutputChannel**アダプターにメッセージを送信するには  
  
-   (からトリガーされた SAP システム) 経由でメッセージを受信する、 **IReplyChannel**です。  
  
 このセクションのトピックでは、作成して、着信および発信の操作に使用されるチャネル形状を構成する方法に関する情報を提供します。  
  
## <a name="creating-outbound-client-channels"></a>送信 (クライアント) チャネルを作成します。  
 いずれかを使用することができます、 **IRequestChannel**または**IOutputChannel** SAP システムでの操作を呼び出します。 作成する最初のどちらの場合、 **System.ServiceModel.ChannelFactory**適切なインターフェイスを使用します。 チャネルを作成するのにファクトリを使用します。 チャネルを作成した後は、アダプターの操作の呼び出しに使用できます。  
  
#### <a name="to-create-and-open-an-outbound-channel"></a>作成および送信チャネルを開く  
  
1.  作成しのインスタンスを初期化**ChannelFactory**のエンドポイントとバインディングを使用して必要なチャネル形状です。 エンドポイントは SAP 接続 URI を指定し、バインディングは、インスタンスの**SAPDBBinding**です。 (チャネル ファクトリを開く前に必要なすべてのバインドのプロパティを設定します。)  
  
2.  使用してチャネル ファクトリの SAP 資格情報を提供、 **ClientCredentials**プロパティです。  
  
3.  チャネル ファクトリを開きます。  
  
4.  呼び出すことによって、チャネルのインスタンスを取得、 **CreateChannel**チャネル ファクトリでのメソッドです。  
  
5.  チャネルを開きます。  
  
 コードまたは構成からバインディングとエンドポイント アドレスを指定できます。  
  
### <a name="specifying-the-binding-and-endpoint-address-in-code"></a>コードでのバインディングとエンドポイント アドレスの指定  
 次のコード例を作成する方法を示しています、 **IRequestChannel**コード内のバインドとエンドポイント アドレスを指定することによってです。 作成するコード、 **IOutputChannel**同じですが、指定する必要があります、 **IOutputChannel**のためのインターフェイス、 **ChannelFactory**チャネルの種類とします。  
  
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
  
### <a name="specifying-the-binding-and-endpoint-address-in-configuration"></a>構成でバインディングとエンドポイント アドレスを指定します。  
 次のコード例では、構成で指定されたクライアント エンドポイントからチャネル ファクトリを作成する方法を示します。  
  
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
  
#### <a name="the-configuration-settings"></a>構成設定  
 次のコードは、前述の例で使用される構成設定を示しています。 クライアント エンドポイントのコントラクトには、"System.ServiceModel.Channels.IRequestChannel"または"System.ServiceModel.Channels.IRequestChannel"を作成するチャネル形状の種類に応じてをする必要があります。  
  
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
  
### <a name="creating-inbound-service-channels"></a>受信 (サービス) チャネルを作成します。  
 インスタンス上のバインドのプロパティを設定して、SAP システムから受信メッセージを受信するアダプターを構成する**SAPBinding**です。 取得できますチャネル リスナーを作成し、このバインディングを使用する、 **IReplyChannel**アダプターからの受信操作へのチャネル。  
  
##### <a name="to-create-and-open-an-ireplychannel-to-receive-data-changed-notifications"></a>作成し、受信データの変更通知を IReplyChannel を開く  
  
1.  インスタンスを作成する**SAPBinding**です。  
  
2.  受信する操作に必要なすべてのバインドのプロパティを設定します。 設定して、 **AcceptCredentialsInUri**プロパティをバインドします。  
  
3.  作成、 **BindingParameterCollection**を追加し、 **InboundActionCollection**を受信する操作のアクションを格納しています。 アダプターでは、その他のすべての操作の SAP システムに例外を返します。 このステップは省略可能です。 詳細については、次を参照してください。 [WCF チャネル モデルを使用して SAP システムからの受信操作の受信](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md)です。  
  
4.  呼び出してチャネル リスナーを作成する**BuildChannelListener\<IReplyChannel >**メソッドを**SAPBinding**です。 このメソッドにパラメーターの 1 つとしては、SAP 接続 URI を指定します。 接続 URI は、SAP システムで、RFC 変換先のパラメーターを含める必要があります。 SAP 接続 URI の詳細については、次を参照してください。、 [SAP システムの接続 URI を作成する](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。 作成した場合、 **BindingParameterCollection**手順 3. も指定するこのチャネル リスナーを作成するときにします。  
  
5.  リスナーを開きます。  
  
6.  取得、 **IReplyChannel**チャネルを呼び出すことによって、 **AcceptChannel**リスナーのメソッドです。  
  
7.  チャネルを開きます。  
  
 次のコードは、チャネル リスナーを作成し、取得する方法を示します、 **IReplyChannel**アダプターからの受信操作にします。  
  
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
  
## <a name="see-also"></a>参照  
[WCF チャネル モデルを使用してアプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)