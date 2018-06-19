---
title: SQL アダプターで WCF サービス モデルの概要 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7641bcc7-3845-4914-9b1b-cb86b998ea6d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3afbf1822945f0a47b09a93b3ac3cc2f8ac8653d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222890"
---
# <a name="overview-of-the-wcf-service-model-with-the-sql-adapter"></a><span data-ttu-id="66bf6-102">SQL アダプターで WCF サービス モデルの概要</span><span class="sxs-lookup"><span data-stu-id="66bf6-102">Overview of the WCF service model with the SQL adapter</span></span>
<span data-ttu-id="66bf6-103">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]は WCF サービスとしての SQL Server 操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="66bf6-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] exposes a SQL Server operation as a WCF service.</span></span> <span data-ttu-id="66bf6-104">ストアド プロシージャを呼び出す例については、SQL Server の成果物の操作を実行するには、さらに、SQL Server で操作を実行すると、アダプターでの操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="66bf6-104">To perform operations on SQL Server artifacts, for example to invoke a stored procedure, you invoke an operation on the adapter, which, in turn, performs the operation on the SQL Server.</span></span> <span data-ttu-id="66bf6-105">したがって、コードは、アダプターによって提示される WCF サービスのクライアントとして機能します。</span><span class="sxs-lookup"><span data-stu-id="66bf6-105">Your code therefore acts as a client to the WCF service presented by the adapter.</span></span>  
  
 <span data-ttu-id="66bf6-106">[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]サービス モデルでは、クライアントとサービス間に存在するサービス コントラクトは、.NET インターフェイスとして表されます、操作は、このインターフェイスのメソッドとして表されます。</span><span class="sxs-lookup"><span data-stu-id="66bf6-106">In the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] service model, the service contract that exists between a client and a service is represented as a .NET interface, and operations are represented as methods on this interface.</span></span> <span data-ttu-id="66bf6-107">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] WCF が使用するアダプターを公開するメタデータから対象となる操作について、このインターフェイスを生成するツールを提供します。</span><span class="sxs-lookup"><span data-stu-id="66bf6-107">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] and WCF provide tools that enable you to generate this interface for targeted operations from the metadata that the adapter exposes.</span></span> <span data-ttu-id="66bf6-108">これらのツールでは、サービス インターフェイスの公開操作の呼び出しに使用できる WCF クライアント クラスも作成します。</span><span class="sxs-lookup"><span data-stu-id="66bf6-108">These tools also create a WCF client class that can be used to invoke the operations exposed in the service interface.</span></span> <span data-ttu-id="66bf6-109">クライアント アプリケーションは、アダプターの操作の呼び出しに WCF クライアント クラスのメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="66bf6-109">A client application can call the methods of the WCF client class to invoke operations on the adapter.</span></span> <span data-ttu-id="66bf6-110">受信操作を受信するサービスを実装する、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、受信操作に対して生成されたインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="66bf6-110">To implement a service to receive inbound operations from the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you implement the interface generated for the inbound operations.</span></span>  
  
 <span data-ttu-id="66bf6-111">次のセクションでは、モデルを使用して、WCF サービスと WCF クライアントの操作を呼び出す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="66bf6-111">The following section explains how to use the WCF service model to invoke operations with a WCF client.</span></span>  
  
## <a name="invoking-operations-on-the-sql-server-with-a-wcf-client"></a><span data-ttu-id="66bf6-112">WCF クライアントで SQL Server での操作を呼び出す</span><span class="sxs-lookup"><span data-stu-id="66bf6-112">Invoking Operations on the SQL Server with a WCF Client</span></span>  
 <span data-ttu-id="66bf6-113">モデルを使用して、WCF サービスで操作を呼び出す、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、まず対象の操作用の WCF クライアント クラスを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66bf6-113">To use the WCF service model to invoke operations on the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you must first generate a WCF client class for the target operations.</span></span> <span data-ttu-id="66bf6-114">WCF クライアントは、このクラスのインスタンスを作成し、SQL Server のシステムでこれらの操作を実行するには、そのメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="66bf6-114">You can then create an instance of this class, a WCF client, and call its methods to perform these operations on the SQL Server system.</span></span> <span data-ttu-id="66bf6-115">このセクションでは、一般的な .NET アダプター クライアント アプリケーションの外観方法の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="66bf6-115">This section provides an outline of how a typical .NET adapter client application looks like.</span></span> <span data-ttu-id="66bf6-116">アダプターを使用して、SQL Server データベースに対して別の操作を実行する方法の詳細な説明については、特定のトピックで提供されます。</span><span class="sxs-lookup"><span data-stu-id="66bf6-116">Detailed explanations on how to perform different operations on the SQL Server database using the adapter are provided in specific topics.</span></span>  
  
#### <a name="to-invoke-operations-on-the-sql-adapter"></a><span data-ttu-id="66bf6-117">SQL アダプターでの操作を呼び出す</span><span class="sxs-lookup"><span data-stu-id="66bf6-117">To invoke operations on the SQL adapter</span></span>  
  
1.  <span data-ttu-id="66bf6-118">WCF クライアント クラスとヘルパー コードを生成します。</span><span class="sxs-lookup"><span data-stu-id="66bf6-118">Generate a WCF client class and helper code.</span></span> <span data-ttu-id="66bf6-119">使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]操作する SQL Server のデータベース成果物を対象とした WCF クライアント クラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="66bf6-119">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]to generate a WCF client class targeted at the SQL Server database artifacts with which you want to work.</span></span> <span data-ttu-id="66bf6-120">WCF クライアントを生成する方法の詳細については、次を参照してください。 [SQL Server の成果物のために、WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="66bf6-120">For more information about how to generate a WCF client, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
2.  <span data-ttu-id="66bf6-121">WCF クライアント インスタンスを作成し、WCF クライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="66bf6-121">Create a WCF client instance and configure the WCF client.</span></span> <span data-ttu-id="66bf6-122">WCF クライアントを構成すると、バインディングと、クライアントが使用するエンドポイント アドレス (接続 URI) を指定することがあります。</span><span class="sxs-lookup"><span data-stu-id="66bf6-122">Configuring the WCF client involves specifying the binding and endpoint address (connection URI) that the client will use.</span></span> <span data-ttu-id="66bf6-123">これは、コードで命令として記述または構成で宣言によって行うことができます。</span><span class="sxs-lookup"><span data-stu-id="66bf6-123">You can do this either imperatively in code or declaratively in configuration.</span></span> <span data-ttu-id="66bf6-124">次のコードを作成する WCF クライアントを対象とする、**選択**での操作、**従業員**SQL Server データベースのテーブルにします。</span><span class="sxs-lookup"><span data-stu-id="66bf6-124">The following code creates a WCF client that targets the **Select** operation on the **Employee** table in a SQL Server database.</span></span> <span data-ttu-id="66bf6-125">また、SQL Server データベースの資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="66bf6-125">It also sets the credentials for the SQL Server database.</span></span> <span data-ttu-id="66bf6-126">WCF クライアントは、構成から初期化されます。</span><span class="sxs-lookup"><span data-stu-id="66bf6-126">The WCF client is initialized from configuration.</span></span>  
  
    ```  
    TableOp_dbo_EmployeeClient client = new TableOp_dbo_EmployeeClient("SqlAdapterBinding_TableOp_dbo_Employee"); //picking the binding and address from the app.config  
  
    client.ClientCredentials.UserName.UserName = "myuser";  
    client.ClientCredentials.UserName.Password = "mypassword";  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="66bf6-127">コードでクライアントのバインディングとエンドポイント アドレスを指定するか、app.config 構成ファイルで宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="66bf6-127">You can either specify the client binding and endpoint address in the code or declare it in the app.config configuration file.</span></span> <span data-ttu-id="66bf6-128">上記のコード スニペットは、後者は使用します。</span><span class="sxs-lookup"><span data-stu-id="66bf6-128">The preceding code snippet uses the latter.</span></span> <span data-ttu-id="66bf6-129">いずれかのアプローチを使用する方法の詳細については、次を参照してください。 [SQL アダプタのクライアントのバインディングを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="66bf6-129">For more information on how to use either approaches, see [Configure a Client Binding for the SQL Adapter](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md).</span></span>  
  
3.  <span data-ttu-id="66bf6-130">WCF クライアントを開きます。</span><span class="sxs-lookup"><span data-stu-id="66bf6-130">Open the WCF client.</span></span>  
  
    ```  
    client.Open();  
    ```  
  
4.  <span data-ttu-id="66bf6-131">SQL server データベースでの選択操作を実行する前の手順で作成された WCF クライアントでメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="66bf6-131">Invoke methods on the WCF client created in preceding step to perform a Select operation on the SQL server database.</span></span> <span data-ttu-id="66bf6-132">次のコードでは、SQL Server データベース テーブルの SELECT ステートメントを呼び出す、WCF クライアントの選択メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="66bf6-132">The following code invokes the Select method of the WCF client to invoke the SELECT statement on a SQL Server database table.</span></span>  
  
    ```  
    client.Select("*", "where [Name] = ‘John Smith’");  
    ```  
  
5.  <span data-ttu-id="66bf6-133">WCF クライアントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="66bf6-133">Close the WCF client.</span></span>  
  
    ```  
    client.Close();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="66bf6-134">参照</span><span class="sxs-lookup"><span data-stu-id="66bf6-134">See Also</span></span>  
[<span data-ttu-id="66bf6-135">WCF サービス モデルを使用して SQL アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="66bf6-135">Develop SQL applications using the WCF Service model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)