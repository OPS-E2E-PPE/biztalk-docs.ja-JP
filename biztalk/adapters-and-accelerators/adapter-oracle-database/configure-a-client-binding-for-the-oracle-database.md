---
title: Oracle データベースのバインディングをクライアントの構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- client binding, specifying in code
- WCF client, creating
- client binding, specifying in configuration file
ms.assetid: f18c7296-c28a-4dec-9514-5299c8c2dffe
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7de5eeb9a7b0022ce4da5f56591e863f48bd0b61
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214610"
---
# <a name="configure-a-client-binding-for-the-oracle-database"></a><span data-ttu-id="85e96-102">Oracle データベースのバインド、クライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="85e96-102">Configure a client binding for the Oracle Database</span></span>
<span data-ttu-id="85e96-103">WCF クライアント クラスを生成した後を WCF クライアント (インスタンス) を作成し、使用するには、そのメソッドを呼び出す、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="85e96-103">After you have generated the WCF client class, you can create a WCF client (instance) and invoke its methods to consume the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="85e96-104">操作用の WCF クライアント クラスとヘルパー コードを生成する方法についてを[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]公開を参照してください[Oracle データベース ソリューションの成果物の WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="85e96-104">For information about how to generate the WCF client class and helper code for operations that the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] exposes, see [Generate a WCF Client or a WCF Service Contract for Oracle Database Solution Artifacts](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md).</span></span>  
  
 <span data-ttu-id="85e96-105">WCF クライアントを作成するには、エンドポイント アドレスとバインディングを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85e96-105">To create the WCF client, you must specify an endpoint address and a binding.</span></span> <span data-ttu-id="85e96-106">エンドポイントのアドレスは有効な Oracle 接続 URI を含める必要があり、バインディングは、Oracle DB バインディングのインスタンスである必要があります (**OracleDBBinding**)。</span><span class="sxs-lookup"><span data-stu-id="85e96-106">The endpoint address must contain a valid Oracle connection URI, and the binding must be an instance of an Oracle DB Binding (**OracleDBBinding**).</span></span> <span data-ttu-id="85e96-107">Oracle の接続 URI の詳細については、次を参照してください。 [Oracle Database 接続 URI を作成する](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="85e96-107">For more information about the Oracle connection URI, see [Create the Oracle Database Connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span></span> <span data-ttu-id="85e96-108">接続 URI の一部としてユーザーの資格情報を指定されていないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="85e96-108">We recommend that you do not specify the user credentials as part of the connection URI.</span></span> <span data-ttu-id="85e96-109">代わりに使用することは、 **ClientCredentials**このトピックで説明したように、WCF クライアントのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="85e96-109">You may instead use the **ClientCredentials** property of the WCF client, as explained in this topic.</span></span>  
  
 <span data-ttu-id="85e96-110">コードまたは構成ファイルでは、Oracle DB のバインドとエンドポイント アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="85e96-110">You can specify the Oracle DB Binding and the endpoint address in your code or in a configuration file.</span></span> <span data-ttu-id="85e96-111">使用すると、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]プロジェクトの作成も構成ファイル (app.config) で WCF クライアント クラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="85e96-111">When you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate the WCF client class, a configuration file (app.config) is also created for your project.</span></span> <span data-ttu-id="85e96-112">このファイルには、バインドのプロパティおよび接続情報 (資格情報) を除くと Oracle データベースに接続されているときに指定したを反映する構成設定が含まれています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="85e96-112">This file contains configuration settings that reflect the binding properties and connection information (except credentials) that you specified when you connected to the Oracle database with the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
## <a name="specifying-the-binding-and-endpoint-address-in-code"></a><span data-ttu-id="85e96-113">コードでのバインディングとエンドポイント アドレスの指定</span><span class="sxs-lookup"><span data-stu-id="85e96-113">Specifying the Binding and Endpoint Address in Code</span></span>  
 <span data-ttu-id="85e96-114">次のコードでは、コード内のバインディングとエンドポイント アドレスを指定することによって、WCF クライアントを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="85e96-114">The following code shows how to create a WCF client by specifying the binding and endpoint address in code.</span></span> <span data-ttu-id="85e96-115">使用して Oracle 資格情報を指定することをお勧め、 **ClientCredentials**接続エンドポイントのアドレスに指定された URI ではなく、WCF クライアントのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="85e96-115">It is good practice to specify the Oracle credentials by using the **ClientCredentials** property of the WCF client rather than in the connection URI supplied for the endpoint address.</span></span>  
  
```  
// A WCF client that targets the /SCOTT/EMP table is created  
// by using a binding object and endpoint address  
OracleDBBinding odbBinding = new OracleDBBinding();  
EndpointAddress odbAddress = new EndpointAddress("OracleDb://ADAPTER");  
  
SCOTTTableEMPClient empClient = new SCOTTTableEMPClient(odbBinding, odbAddress);  
  
empClient.ClientCredentials.UserName.UserName = "SCOTT";  
empClient.ClientCredentials.UserName.Password = "TIGER";  
  
empClient.Open();  
```  
  
## <a name="specifying-the-binding-and-endpoint-address-in-a-configuration-file"></a><span data-ttu-id="85e96-116">構成ファイルでのバインディングとエンドポイント アドレスの指定</span><span class="sxs-lookup"><span data-stu-id="85e96-116">Specifying the Binding and Endpoint Address in a Configuration File</span></span>  
 <span data-ttu-id="85e96-117">次のコードでは、app.config ファイルでバインディングとエンドポイント アドレスを指定して、WCF クライアントを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="85e96-117">The following code shows how to create a WCF client by specifying the binding and endpoint address in an app.config file.</span></span>  
  
```  
// A WCF client that targets the /SCOTT/EMP table is created  
// by specifying the client endpoint information in app.config  
SCOTTTableEMPClient empClient = new SCOTTTableEMPClient("OracleDBBinding_SCOTT.Table.EMP");  
  
empClient.ClientCredentials.UserName.UserName = "SCOTT";  
empClient.ClientCredentials.UserName.Password = "TIGER";  
  
empClient.Open();  
```  
  
 <span data-ttu-id="85e96-118">次の XML は、構成ファイルで、EMP テーブル用に作成された、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="85e96-118">The following XML shows the configuration file created for the EMP table by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="85e96-119">このファイルには、前の例で参照されているクライアント エンドポイント構成が含まれています。</span><span class="sxs-lookup"><span data-stu-id="85e96-119">This file contains the client endpoint configuration referenced in the preceding example.</span></span>  
  
```  
\<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    \<system.serviceModel>  
        <bindings>  
            <oracleDBBinding>  
                <binding name="OracleDBBinding" closeTimeout="00:01:00" openTimeout="00:01:00"  
                    receiveTimeout="00:10:00" sendTimeout="00:01:00"  
                    dataFetchSize="65536" metadataPooling="true" statementCachePurge="false"  
                    statementCacheSize="10" longDatatypeColumnSize="32767" pollingStatement=""  
                    postPollStatement="" pollingInterval="500" useOracleConnectionPool="false"  
                    minPoolSize="1" maxPoolSize="100" incrPoolSize="5" decrPoolSize="1"  
                    connectionLifetime="0" transactionIsolationLevel="ReadCommitted"  
                    enablePerformanceCounters="false" acceptCredentialsInUri="false"  
                    enableBizTalkCompatibilityMode="false" />  
            </oracleDBBinding>  
        </bindings>  
        <client>  
            <endpoint address="oracledb://adapter/" binding="oracleDBBinding"  
                bindingConfiguration="OracleDBBinding" contract="SCOTTTableEMP"  
                name="OracleDBBinding_SCOTT.Table.EMP" />  
        </client>  
    \</system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="85e96-120">プロジェクトに複数の WCF クライアントがある場合があります複数のクライアント構成ファイルで定義されているエンドポイント エントリ。</span><span class="sxs-lookup"><span data-stu-id="85e96-120">If a project has more than one WCF client, there will be multiple client endpoint entries defined in the configuration file.</span></span> <span data-ttu-id="85e96-121">各 WCF クライアント エントリが設定されます、バインド構成とターゲットの Oracle データベース アイテム; に基づいて一意の名前たとえば、"OracleDBBinding_SCOTT です。Table.EMP"です。</span><span class="sxs-lookup"><span data-stu-id="85e96-121">Each WCF client entry will have a unique name based on its binding configuration and target Oracle database artifact; for example, "OracleDBBinding_SCOTT.Table.EMP".</span></span> <span data-ttu-id="85e96-122">場合は、プロジェクトで、WCF クライアントを作成する複数回接続すると、複数のバインド構成エントリが作成接続ごとに 1 つです。</span><span class="sxs-lookup"><span data-stu-id="85e96-122">If you connect multiple times to create the WCF clients in your project, multiple binding configuration entries will be created, one for each connection.</span></span> <span data-ttu-id="85e96-123">これらのバインディングの構成エントリの名前は次のようになります: OracleDBBinding1、OracleDBBinding2 などです。</span><span class="sxs-lookup"><span data-stu-id="85e96-123">These binding configuration entries will be named in the following manner: OracleDBBinding1, OracleDBBinding2, and so on.</span></span> <span data-ttu-id="85e96-124">特定の接続中に作成される各クライアント エンドポイント エントリでは、その接続中に作成されたバインド エントリを参照します。</span><span class="sxs-lookup"><span data-stu-id="85e96-124">Each client endpoint entry created during a specific connection will reference the binding entry created during that connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85e96-125">参照</span><span class="sxs-lookup"><span data-stu-id="85e96-125">See Also</span></span>  
 <span data-ttu-id="85e96-126">[WCF サービス モデルを使用して Oracle データベース アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md) </span><span class="sxs-lookup"><span data-stu-id="85e96-126">[Develop Oracle Database Applications by Using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md) </span></span>  
 <span data-ttu-id="85e96-127">[Oracle データベース ソリューションの成果物のための WCF クライアントまたは WCF サービス コントラクトを生成します。](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md) </span><span class="sxs-lookup"><span data-stu-id="85e96-127">[Generate a WCF Client or a WCF Service Contract for Oracle Database Solution Artifacts](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md) </span></span>  
 <span data-ttu-id="85e96-128">[Oracle Database 接続 URI を作成します。](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md) </span><span class="sxs-lookup"><span data-stu-id="85e96-128">[Create the Oracle Database Connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md) </span></span>  
 [<span data-ttu-id="85e96-129">WCF チャネル モデルを使用して Oracle データベース アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="85e96-129">Develop Oracle Database Applications by Using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)