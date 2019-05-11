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
# <a name="configure-a-client-binding-for-the-sql-adapter"></a><span data-ttu-id="7d26e-102">SQL アダプタのクライアントのバインディングを構成します。</span><span class="sxs-lookup"><span data-stu-id="7d26e-102">Configure a Client Binding for the SQL Adapter</span></span>
<span data-ttu-id="7d26e-103">WCF クライアント クラスを生成した後は、WCF クライアント (インスタンス) の作成し、使用するメソッドの呼び出し、[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7d26e-103">After you have generated the WCF client class, you can create a WCF client (instance) and invoke its methods to consume the [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)].</span></span> <span data-ttu-id="7d26e-104">操作のための WCF クライアント クラスとヘルパー コードを生成する方法についてを[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]公開を参照してください[SQL Server のアイテムの WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)します。</span><span class="sxs-lookup"><span data-stu-id="7d26e-104">For information about how to generate the WCF client class and helper code for operations that the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] exposes, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
 <span data-ttu-id="7d26e-105">WCF クライアントを作成するには、エンドポイント アドレスとバインディングを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d26e-105">To create the WCF client, you must specify an endpoint address and a binding.</span></span> <span data-ttu-id="7d26e-106">エンドポイント アドレスが有効な SQL 接続の URI を含める必要があり、バインド SQL バインディングのインスタンスである必要があります (**sqlBinding**)。</span><span class="sxs-lookup"><span data-stu-id="7d26e-106">The endpoint address must contain a valid SQL connection URI, and the binding must be an instance of a SQL Binding (**sqlBinding**).</span></span> <span data-ttu-id="7d26e-107">SQL 接続 URI の詳細については、次を参照してください。 [SQL Server 接続 URI の作成](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="7d26e-107">For more information about the SQL connection URI, see [Create the SQL Server connection URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span> <span data-ttu-id="7d26e-108">接続 URI の一部として、ユーザーの資格情報を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d26e-108">You must specify the user credentials as part of the connection URI.</span></span> <span data-ttu-id="7d26e-109">使用すること、 **ClientCredentials**このトピックで説明したように、WCF クライアントのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="7d26e-109">You may use the **ClientCredentials** property of the WCF client, as explained in this topic.</span></span>  
  
 <span data-ttu-id="7d26e-110">コードまたは構成ファイルでは、SQL バインディングとエンドポイント アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7d26e-110">You can specify the SQL binding and the endpoint address in your code or in a configuration file.</span></span> <span data-ttu-id="7d26e-111">使用すると、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]プロジェクトの作成も構成ファイル (app.config) で WCF クライアント クラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="7d26e-111">When you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate the WCF client class, a configuration file (app.config) is also created for your project.</span></span> <span data-ttu-id="7d26e-112">このファイルに情報を反映するバインドのプロパティと接続 (資格情報) を除くと SQL database に接続するときに指定した構成設定が含まれています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7d26e-112">This file contains configuration settings that reflect the binding properties and connection information (except credentials) that you specified when you connected to the SQL database with the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
## <a name="specifying-the-binding-and-endpoint-address-in-code"></a><span data-ttu-id="7d26e-113">バインディングとエンドポイント アドレスを指定するコード</span><span class="sxs-lookup"><span data-stu-id="7d26e-113">Specifying the Binding and Endpoint Address in Code</span></span>  
 <span data-ttu-id="7d26e-114">次のコードを使用して、コードでバインディングとエンドポイント アドレスを指定することで、WCF クライアントを作成する方法を示しています、 **ClientCredentials** WCF クライアントのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="7d26e-114">The following code shows how to create a WCF client by specifying the binding and endpoint address in code by using the **ClientCredentials** property of the WCF client.</span></span>  
  
```  
SqlAdapterBinding binding = new SqlAdapterBinding();  
EndpointAddress sqlAddress = new EndpointAddress("mssql://<sql_server_name>//<database_name>?");  
  
TableOp_dbo_CustomerClient client = new TableOp_dbo_CustomerClient (binding, sqlAddress);  
  
client.ClientCredentials.UserName.UserName = "USER";  
client.ClientCredentials.UserName.Password = "PASSWORD";  
  
client.Open();  
```  
  
## <a name="specifying-the-binding-and-endpoint-address-in-a-configuration-file"></a><span data-ttu-id="7d26e-115">構成ファイルでバインディングとエンドポイント アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="7d26e-115">Specifying the Binding and Endpoint Address in a Configuration File</span></span>  
 <span data-ttu-id="7d26e-116">次のコードでは、app.config ファイルでバインディングとエンドポイント アドレスを指定することで、WCF クライアントを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7d26e-116">The following code shows how to create a WCF client by specifying the binding and endpoint address in an app.config file.</span></span>  
  
```  
TableOp_dbo_CustomerClient client = new TableOp_dbo_CustomerClient("SqlAdapterBinding_TableOp_dbo_Customer");  
  
client.ClientCredentials.UserName.UserName = "USER";  
client.ClientCredentials.UserName.Password = "PASSWORD";  
  
client.Open();  
```  
  
 <span data-ttu-id="7d26e-117">次の XML は、Customer テーブルの作成、構成ファイル、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7d26e-117">The following XML shows the configuration file created for the Customer table by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="7d26e-118">このファイルには、前の例で参照されているクライアント エンドポイント構成が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7d26e-118">This file contains the client endpoint configuration referenced in the preceding example.</span></span>  
  
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
  
 <span data-ttu-id="7d26e-119">プロジェクトには、複数の WCF クライアントがある場合があります複数のクライアント構成ファイルで定義されているエンドポイントのエントリ。</span><span class="sxs-lookup"><span data-stu-id="7d26e-119">If a project has more than one WCF client, there will be multiple client endpoint entries defined in the configuration file.</span></span> <span data-ttu-id="7d26e-120">WCF クライアントの各エントリは、バインド構成とターゲットの SQL Server の成果物; に基づいて一意の名前になりますたとえば、"`SqlAdapterBinding_TableOp_dbo_Customer`"。</span><span class="sxs-lookup"><span data-stu-id="7d26e-120">Each WCF client entry will have a unique name based on its binding configuration and target SQL Server artifact; for example, "`SqlAdapterBinding_TableOp_dbo_Customer`".</span></span> <span data-ttu-id="7d26e-121">プロジェクトで、WCF クライアントを作成するための複数回を接続する場合は、複数のバインド構成エントリが作成されます、接続ごとに 1 つ。</span><span class="sxs-lookup"><span data-stu-id="7d26e-121">If you connect multiple times to create the WCF clients in your project, multiple binding configuration entries will be created, one for each connection.</span></span> <span data-ttu-id="7d26e-122">これらのバインド構成エントリは次の方法で名前が付けられます。SqlAdapterBinding、SqlAdapterBinding1、しにします。</span><span class="sxs-lookup"><span data-stu-id="7d26e-122">These binding configuration entries will be named in the following manner: SqlAdapterBinding, SqlAdapterBinding1, and so on.</span></span> <span data-ttu-id="7d26e-123">特定の接続中に作成される各クライアントのエンドポイント エントリは、その接続中に作成されたバインド エントリを参照します。</span><span class="sxs-lookup"><span data-stu-id="7d26e-123">Each client endpoint entry created during a specific connection will reference the binding entry created during that connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d26e-124">参照</span><span class="sxs-lookup"><span data-stu-id="7d26e-124">See Also</span></span>  
<span data-ttu-id="7d26e-125">[WCF サービス モデルを使用して SQL アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md) </span><span class="sxs-lookup"><span data-stu-id="7d26e-125">[Develop SQL applications using the WCF Service model](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md) </span></span>  
 <span data-ttu-id="7d26e-126">[SQL Server のアイテムの WCF クライアントまたは WCF サービス コントラクトを生成します。](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md) </span><span class="sxs-lookup"><span data-stu-id="7d26e-126">[Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md) </span></span>  
[<span data-ttu-id="7d26e-127">SQL Server 接続 URI を作成します。</span><span class="sxs-lookup"><span data-stu-id="7d26e-127">Create the SQL Server connection URI</span></span>](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)