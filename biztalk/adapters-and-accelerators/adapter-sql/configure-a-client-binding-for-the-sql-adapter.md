---
title: "クライアント バインディングを SQL アダプターの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 146e6f51-e33b-45be-a302-8c9250e79501
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 947666ce63160425896564b20e91bd1fd70c95a9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="configure-a-client-binding-for-the-sql-adapter"></a><span data-ttu-id="c5410-102">SQL アダプタのクライアントのバインディングを構成します。</span><span class="sxs-lookup"><span data-stu-id="c5410-102">Configure a Client Binding for the SQL Adapter</span></span>
<span data-ttu-id="c5410-103">WCF クライアント クラスを生成した後を WCF クライアント (インスタンス) を作成し、使用するには、そのメソッドを呼び出す、[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="c5410-103">After you have generated the WCF client class, you can create a WCF client (instance) and invoke its methods to consume the [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)].</span></span> <span data-ttu-id="c5410-104">操作用の WCF クライアント クラスとヘルパー コードを生成する方法についてを[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]公開を参照してください[SQL Server の成果物のために、WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="c5410-104">For information about how to generate the WCF client class and helper code for operations that the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] exposes, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
 <span data-ttu-id="c5410-105">WCF クライアントを作成するには、エンドポイント アドレスとバインディングを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5410-105">To create the WCF client, you must specify an endpoint address and a binding.</span></span> <span data-ttu-id="c5410-106">エンドポイントのアドレスは有効な SQL 接続 URI を含める必要があり、バインディングは SQL バインディングのインスタンスである必要があります (**sqlBinding**)。</span><span class="sxs-lookup"><span data-stu-id="c5410-106">The endpoint address must contain a valid SQL connection URI, and the binding must be an instance of a SQL Binding (**sqlBinding**).</span></span> <span data-ttu-id="c5410-107">SQL 接続 URI の詳細については、次を参照してください。 [SQL Server の接続 URI を作成する](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="c5410-107">For more information about the SQL connection URI, see [Create the SQL Server connection URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span> <span data-ttu-id="c5410-108">接続 URI の一部として、ユーザーの資格情報を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5410-108">You must specify the user credentials as part of the connection URI.</span></span> <span data-ttu-id="c5410-109">使用することは、 **ClientCredentials**このトピックで説明したように、WCF クライアントのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="c5410-109">You may use the **ClientCredentials** property of the WCF client, as explained in this topic.</span></span>  
  
 <span data-ttu-id="c5410-110">コードまたは構成ファイルでは、SQL のバインディングとエンドポイント アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c5410-110">You can specify the SQL binding and the endpoint address in your code or in a configuration file.</span></span> <span data-ttu-id="c5410-111">使用すると、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]プロジェクトの作成も構成ファイル (app.config) で WCF クライアント クラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="c5410-111">When you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate the WCF client class, a configuration file (app.config) is also created for your project.</span></span> <span data-ttu-id="c5410-112">このファイルには、バインドのプロパティおよび接続情報 (資格情報) を除くと SQL データベースに接続されているときに指定したを反映する構成設定が含まれています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="c5410-112">This file contains configuration settings that reflect the binding properties and connection information (except credentials) that you specified when you connected to the SQL database with the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
## <a name="specifying-the-binding-and-endpoint-address-in-code"></a><span data-ttu-id="c5410-113">コードでのバインディングとエンドポイント アドレスの指定</span><span class="sxs-lookup"><span data-stu-id="c5410-113">Specifying the Binding and Endpoint Address in Code</span></span>  
 <span data-ttu-id="c5410-114">次のコードを使用したコードのバインドとエンドポイント アドレスを指定して、WCF クライアントを作成する方法を示しています、 **ClientCredentials** WCF クライアントのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="c5410-114">The following code shows how to create a WCF client by specifying the binding and endpoint address in code by using the **ClientCredentials** property of the WCF client.</span></span>  
  
```  
SqlAdapterBinding binding = new SqlAdapterBinding();  
EndpointAddress sqlAddress = new EndpointAddress("mssql://<sql_server_name>//<database_name>?");  
  
TableOp_dbo_CustomerClient client = new TableOp_dbo_CustomerClient (binding, sqlAddress);  
  
client.ClientCredentials.UserName.UserName = "USER";  
client.ClientCredentials.UserName.Password = "PASSWORD";  
  
client.Open();  
```  
  
## <a name="specifying-the-binding-and-endpoint-address-in-a-configuration-file"></a><span data-ttu-id="c5410-115">構成ファイルでのバインディングとエンドポイント アドレスの指定</span><span class="sxs-lookup"><span data-stu-id="c5410-115">Specifying the Binding and Endpoint Address in a Configuration File</span></span>  
 <span data-ttu-id="c5410-116">次のコードでは、app.config ファイルでバインディングとエンドポイント アドレスを指定して、WCF クライアントを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c5410-116">The following code shows how to create a WCF client by specifying the binding and endpoint address in an app.config file.</span></span>  
  
```  
TableOp_dbo_CustomerClient client = new TableOp_dbo_CustomerClient("SqlAdapterBinding_TableOp_dbo_Customer");  
  
client.ClientCredentials.UserName.UserName = "USER";  
client.ClientCredentials.UserName.Password = "PASSWORD";  
  
client.Open();  
```  
  
 <span data-ttu-id="c5410-117">次の XML は、Customer テーブルの作成、構成ファイル、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="c5410-117">The following XML shows the configuration file created for the Customer table by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="c5410-118">このファイルには、前の例で参照されているクライアント エンドポイント構成が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c5410-118">This file contains the client endpoint configuration referenced in the preceding example.</span></span>  
  
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
  
 <span data-ttu-id="c5410-119">プロジェクトに複数の WCF クライアントがある場合があります複数のクライアント構成ファイルで定義されているエンドポイント エントリ。</span><span class="sxs-lookup"><span data-stu-id="c5410-119">If a project has more than one WCF client, there will be multiple client endpoint entries defined in the configuration file.</span></span> <span data-ttu-id="c5410-120">各 WCF クライアント エントリが設定されます、バインド構成とターゲットの SQL Server アーティファクト; に基づいて一意の名前たとえば、"`SqlAdapterBinding_TableOp_dbo_Customer`"です。</span><span class="sxs-lookup"><span data-stu-id="c5410-120">Each WCF client entry will have a unique name based on its binding configuration and target SQL Server artifact; for example, "`SqlAdapterBinding_TableOp_dbo_Customer`".</span></span> <span data-ttu-id="c5410-121">場合は、プロジェクトで、WCF クライアントを作成する複数回接続すると、複数のバインド構成エントリが作成接続ごとに 1 つです。</span><span class="sxs-lookup"><span data-stu-id="c5410-121">If you connect multiple times to create the WCF clients in your project, multiple binding configuration entries will be created, one for each connection.</span></span> <span data-ttu-id="c5410-122">これらのバインディングの構成エントリの名前は次のようになります: SqlAdapterBinding、SqlAdapterBinding1 などです。</span><span class="sxs-lookup"><span data-stu-id="c5410-122">These binding configuration entries will be named in the following manner: SqlAdapterBinding, SqlAdapterBinding1, and so on.</span></span> <span data-ttu-id="c5410-123">特定の接続中に作成される各クライアント エンドポイント エントリでは、その接続中に作成されたバインド エントリを参照します。</span><span class="sxs-lookup"><span data-stu-id="c5410-123">Each client endpoint entry created during a specific connection will reference the binding entry created during that connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5410-124">参照</span><span class="sxs-lookup"><span data-stu-id="c5410-124">See Also</span></span>  
<span data-ttu-id="c5410-125">[WCF サービス モデルを使用して SQL アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md) </span><span class="sxs-lookup"><span data-stu-id="c5410-125">[Develop SQL applications using the WCF Service model](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md) </span></span>  
 <span data-ttu-id="c5410-126">[SQL Server の成果物のために、WCF クライアントまたは WCF サービス コントラクトを生成します。](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md) </span><span class="sxs-lookup"><span data-stu-id="c5410-126">[Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md) </span></span>  
[<span data-ttu-id="c5410-127">SQL Server の接続 URI を作成します。</span><span class="sxs-lookup"><span data-stu-id="c5410-127">Create the SQL Server connection URI</span></span>](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)