---
title: クライアント バインディングを SQL アダプターの構成 |Microsoft ドキュメント
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
ms.openlocfilehash: 947666ce63160425896564b20e91bd1fd70c95a9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25962536"
---
# <a name="configure-a-client-binding-for-the-sql-adapter"></a>SQL アダプタのクライアントのバインディングを構成します。
WCF クライアント クラスを生成した後を WCF クライアント (インスタンス) を作成し、使用するには、そのメソッドを呼び出す、[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]です。 操作用の WCF クライアント クラスとヘルパー コードを生成する方法についてを[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]公開を参照してください[SQL Server の成果物のために、WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)です。  
  
 WCF クライアントを作成するには、エンドポイント アドレスとバインディングを指定する必要があります。 エンドポイントのアドレスは有効な SQL 接続 URI を含める必要があり、バインディングは SQL バインディングのインスタンスである必要があります (**sqlBinding**)。 SQL 接続 URI の詳細については、次を参照してください。 [SQL Server の接続 URI を作成する](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)です。 接続 URI の一部として、ユーザーの資格情報を指定する必要があります。 使用することは、 **ClientCredentials**このトピックで説明したように、WCF クライアントのプロパティです。  
  
 コードまたは構成ファイルでは、SQL のバインディングとエンドポイント アドレスを指定できます。 使用すると、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]プロジェクトの作成も構成ファイル (app.config) で WCF クライアント クラスを生成します。 このファイルには、バインドのプロパティおよび接続情報 (資格情報) を除くと SQL データベースに接続されているときに指定したを反映する構成設定が含まれています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
## <a name="specifying-the-binding-and-endpoint-address-in-code"></a>コードでのバインディングとエンドポイント アドレスの指定  
 次のコードを使用したコードのバインドとエンドポイント アドレスを指定して、WCF クライアントを作成する方法を示しています、 **ClientCredentials** WCF クライアントのプロパティです。  
  
```  
SqlAdapterBinding binding = new SqlAdapterBinding();  
EndpointAddress sqlAddress = new EndpointAddress("mssql://<sql_server_name>//<database_name>?");  
  
TableOp_dbo_CustomerClient client = new TableOp_dbo_CustomerClient (binding, sqlAddress);  
  
client.ClientCredentials.UserName.UserName = "USER";  
client.ClientCredentials.UserName.Password = "PASSWORD";  
  
client.Open();  
```  
  
## <a name="specifying-the-binding-and-endpoint-address-in-a-configuration-file"></a>構成ファイルでのバインディングとエンドポイント アドレスの指定  
 次のコードでは、app.config ファイルでバインディングとエンドポイント アドレスを指定して、WCF クライアントを作成する方法を示します。  
  
```  
TableOp_dbo_CustomerClient client = new TableOp_dbo_CustomerClient("SqlAdapterBinding_TableOp_dbo_Customer");  
  
client.ClientCredentials.UserName.UserName = "USER";  
client.ClientCredentials.UserName.Password = "PASSWORD";  
  
client.Open();  
```  
  
 次の XML は、Customer テーブルの作成、構成ファイル、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 このファイルには、前の例で参照されているクライアント エンドポイント構成が含まれています。  
  
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
  
 プロジェクトに複数の WCF クライアントがある場合があります複数のクライアント構成ファイルで定義されているエンドポイント エントリ。 各 WCF クライアント エントリが設定されます、バインド構成とターゲットの SQL Server アーティファクト; に基づいて一意の名前たとえば、"`SqlAdapterBinding_TableOp_dbo_Customer`"です。 場合は、プロジェクトで、WCF クライアントを作成する複数回接続すると、複数のバインド構成エントリが作成接続ごとに 1 つです。 これらのバインディングの構成エントリの名前は次のようになります: SqlAdapterBinding、SqlAdapterBinding1 などです。 特定の接続中に作成される各クライアント エンドポイント エントリでは、その接続中に作成されたバインド エントリを参照します。  
  
## <a name="see-also"></a>参照  
[WCF サービス モデルを使用して SQL アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)   
 [SQL Server の成果物のために、WCF クライアントまたは WCF サービス コントラクトを生成します。](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)   
[SQL Server の接続 URI を作成します。](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)