---
title: クライアント バインディングを SQL アダプターの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 146e6f51-e33b-45be-a302-8c9250e79501
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e0ad6198cb91da58648325c2c73b84d8d7e30404
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370357"
---
# <a name="configure-a-client-binding-for-the-sql-adapter"></a>SQL アダプタのクライアントのバインディングを構成します。
WCF クライアント クラスを生成した後は、WCF クライアント (インスタンス) の作成し、使用するメソッドの呼び出し、[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]します。 操作のための WCF クライアント クラスとヘルパー コードを生成する方法についてを[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]公開を参照してください[SQL Server のアイテムの WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)します。  
  
 WCF クライアントを作成するには、エンドポイント アドレスとバインディングを指定する必要があります。 エンドポイント アドレスが有効な SQL 接続の URI を含める必要があり、バインド SQL バインディングのインスタンスである必要があります (**sqlBinding**)。 SQL 接続 URI の詳細については、次を参照してください。 [SQL Server 接続 URI の作成](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)です。 接続 URI の一部として、ユーザーの資格情報を指定する必要があります。 使用すること、 **ClientCredentials**このトピックで説明したように、WCF クライアントのプロパティ。  
  
 コードまたは構成ファイルでは、SQL バインディングとエンドポイント アドレスを指定できます。 使用すると、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]プロジェクトの作成も構成ファイル (app.config) で WCF クライアント クラスを生成します。 このファイルに情報を反映するバインドのプロパティと接続 (資格情報) を除くと SQL database に接続するときに指定した構成設定が含まれています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
## <a name="specifying-the-binding-and-endpoint-address-in-code"></a>バインディングとエンドポイント アドレスを指定するコード  
 次のコードを使用して、コードでバインディングとエンドポイント アドレスを指定することで、WCF クライアントを作成する方法を示しています、 **ClientCredentials** WCF クライアントのプロパティ。  
  
```  
SqlAdapterBinding binding = new SqlAdapterBinding();  
EndpointAddress sqlAddress = new EndpointAddress("mssql://<sql_server_name>//<database_name>?");  
  
TableOp_dbo_CustomerClient client = new TableOp_dbo_CustomerClient (binding, sqlAddress);  
  
client.ClientCredentials.UserName.UserName = "USER";  
client.ClientCredentials.UserName.Password = "PASSWORD";  
  
client.Open();  
```  
  
## <a name="specifying-the-binding-and-endpoint-address-in-a-configuration-file"></a>構成ファイルでバインディングとエンドポイント アドレスを指定します。  
 次のコードでは、app.config ファイルでバインディングとエンドポイント アドレスを指定することで、WCF クライアントを作成する方法を示します。  
  
```  
TableOp_dbo_CustomerClient client = new TableOp_dbo_CustomerClient("SqlAdapterBinding_TableOp_dbo_Customer");  
  
client.ClientCredentials.UserName.UserName = "USER";  
client.ClientCredentials.UserName.Password = "PASSWORD";  
  
client.Open();  
```  
  
 次の XML は、Customer テーブルの作成、構成ファイル、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 このファイルには、前の例で参照されているクライアント エンドポイント構成が含まれています。  
  
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
            <endpoint address="mssql://<sql_server_name>//<database_name>?" binding="sqlBinding"  
                bindingConfiguration="SqlAdapterBinding" contract="TableOp_dbo_Customer"  
                name="SqlAdapterBinding_TableOp_dbo_Customer" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
 プロジェクトには、複数の WCF クライアントがある場合があります複数のクライアント構成ファイルで定義されているエンドポイントのエントリ。 WCF クライアントの各エントリは、バインド構成とターゲットの SQL Server の成果物; に基づいて一意の名前になりますたとえば、"`SqlAdapterBinding_TableOp_dbo_Customer`"。 プロジェクトで、WCF クライアントを作成するための複数回を接続する場合は、複数のバインド構成エントリが作成されます、接続ごとに 1 つ。 これらのバインド構成エントリは次の方法で名前が付けられます。SqlAdapterBinding、SqlAdapterBinding1、しにします。 特定の接続中に作成される各クライアントのエンドポイント エントリは、その接続中に作成されたバインド エントリを参照します。  
  
## <a name="see-also"></a>参照  
[WCF サービス モデルを使用して SQL アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)   
 [SQL Server のアイテムの WCF クライアントまたは WCF サービス コントラクトを生成します。](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)   
[SQL Server 接続 URI を作成します。](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)