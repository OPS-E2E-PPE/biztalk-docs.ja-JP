---
title: Siebel システム用の WCF クライアントの構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- how to, create a WCF client by specifying binding and endpoint address in a configuration file
- how to, create a WCF client by specifying binding and endpoint address in code
- WCF service model, configuring a WCF client for a Siebel system
ms.assetid: 6b4c5b06-d5ff-4dbf-8dc2-89c547a59864
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04d122c3300f3c1e52194a10332fbb7fb6c45d81
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963608"
---
# <a name="configure-a-wcf-client-for-a-siebel-system"></a>Siebel システム用の WCF クライアントを構成します。
WCF クライアント クラスを生成した後を WCF クライアント (インスタンス) を作成し、使用するには、そのメソッドを呼び出す、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。 操作用の WCF クライアント クラスとヘルパー コードを生成する方法についてを[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]公開を参照してください[WCF クライアントまたは Siebel ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)です。  
  
 WCF クライアントを作成するには、エンドポイント アドレスとバインディングを指定する必要があります。 エンドポイントのアドレスは、Siebel の有効な接続 URI を含める必要があり、バインディングは、Siebel のバインドのインスタンスである必要があります (**SiebelBinding**)。 Siebel 接続 URI の詳細については、次を参照してください。 [Visual Studio での Siebel システムへの接続](../../adapters-and-accelerators/adapter-siebel/connect-to-the-siebel-system-in-visual-studio.md)です。  
  
 コードまたは構成ファイルでは、Siebel のバインドとエンドポイント アドレスを指定できます。 使用すると、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]プロジェクトの作成も構成ファイル (app.config) で WCF クライアント クラスを生成します。 このファイルには、バインドのプロパティおよび接続情報 (資格情報) を除くで Siebel システムに接続するときに指定したを反映する構成設定が含まれています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
## <a name="specifying-the-binding-and-endpoint-address-in-code"></a>コードでのバインディングとエンドポイント アドレスの指定  
 次のコードでは、コード内のバインディングとエンドポイント アドレスを指定することによって、WCF クライアントを作成する方法を示します。 Siebel の資格情報を使用して指定することをお勧め、 **ClientCredentials**接続エンドポイントのアドレスに指定された URI ではなく、WCF クライアントのプロパティです。  
  
```  
// A WCF client that targets the TimeStamp business service is created  
// by using a binding object and endpoint address  
SiebelBinding sblBinding = new SiebelBinding();  
EndpointAddress sblAddress = new EndpointAddress("siebel://Siebel_server:1234?SiebelObjectManager=obj_mgr&SiebelEnterpriseServer=ent_server&Language=enu");  
  
BusinessServices_TimeStamp_OperationClient client =   
    new BusinessServices_TimeStamp_OperationClient(sblBinding, sblAddress);  
  
    client.ClientCredentials.UserName.UserName = "SADMIN";  
    client.ClientCredentials.UserName.Password = "SADMIN";  
  
    client.Open();  
```  
  
## <a name="specifying-the-binding-and-endpoint-address-in-a-configuration-file"></a>構成ファイルでのバインディングとエンドポイント アドレスの指定  
 次のコードでは、app.config ファイルでバインディングとエンドポイント アドレスを指定して、WCF クライアントを作成する方法を示します。  
  
```  
// A WCF client that targets the TimeStamp business service is created  
// by specifying the client endpoint information in app.config  
BusinessServices_TimeStamp_OperationClient client =   
    new BusinessServices_TimeStamp_OperationClient("SiebelBinding_BusinessServices_TimeStamp_Operation");  
  
client.ClientCredentials.UserName.UserName = "SADMIN";  
client.ClientCredentials.UserName.Password = "SADMIN";  
  
client.Open();  
```  
  
### <a name="the-appconfig-file"></a>App.config ファイル  
 次の XML は、タイムスタンプのビジネス サービスの作成、構成ファイル、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 このファイルには、前の例で参照されているクライアント エンドポイント構成が含まれています。  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    <system.serviceModel>  
        <bindings>  
            <siebelBinding>  
                <binding name="SiebelBinding" closeTimeout="00:01:00" openTimeout="00:01:00"  
                    receiveTimeout="00:10:00" sendTimeout="00:01:00" enableBizTalkCompatibilityMode="false"  
                    enablePerformanceCounters="false" enableConnectionPooling="true"  
                    maxConnectionsPerSystem="5" idleConnectionTimeout="00:01:00"  
                    acceptCredentialsInUri="false" />  
            </siebelBinding>  
        </bindings>  
        <client>  
            <endpoint address="siebel://Siebel_server:1234?SiebelObjectManager=obj_mgr&SiebelEnterpriseServer=ent_server&Language=enu"  
                binding="siebelBinding" bindingConfiguration="SiebelBinding"  
                contract="BusinessServices_TimeStamp_Operation" name="SiebelBinding_BusinessServices_TimeStamp_Operation" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
 プロジェクトに複数の WCF クライアントがある場合があります複数のクライアント構成ファイルで定義されているエンドポイント エントリ。 各 WCF クライアント エントリが設定されます、バインド構成とターゲット Siebel の成果物; に基づいて一意の名前たとえば、"SiebelBinding_BusinessServices_TimeStamp_Operation"です。 場合は、プロジェクトで、WCF クライアントを作成する複数回接続すると、複数のバインド構成エントリが作成接続ごとに 1 つです。 これらのバインディングの構成エントリの名前は次のようになります: SiebelBinding、SiebelBinding1、SiebelBinding2 などです。 特定の接続中に作成される各クライアント エンドポイント エントリでは、その接続中に作成されたバインド エントリを参照します。  
  
## <a name="see-also"></a>参照  
 [WCF サービス モデルを使用して Siebel アプリケーションを開発します。](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)