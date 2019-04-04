---
title: SQL アダプターを使用した WCF サービス モデルの概要 |Microsoft Docs
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
ms.openlocfilehash: 121b425abe1c7c34ba75e535799770031b931525
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997331"
---
# <a name="overview-of-the-wcf-service-model-with-the-sql-adapter"></a><span data-ttu-id="a191b-102">SQL アダプターを使用した WCF サービス モデルの概要</span><span class="sxs-lookup"><span data-stu-id="a191b-102">Overview of the WCF service model with the SQL adapter</span></span>
<span data-ttu-id="a191b-103">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] WCF サービスとしての SQL Server の操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="a191b-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] exposes a SQL Server operation as a WCF service.</span></span> <span data-ttu-id="a191b-104">、ストアド プロシージャを呼び出す例については、SQL Server のアイテムに対して操作を実行するには、さらに、SQL Server 上の操作を実行すると、アダプターでの操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a191b-104">To perform operations on SQL Server artifacts, for example to invoke a stored procedure, you invoke an operation on the adapter, which, in turn, performs the operation on the SQL Server.</span></span> <span data-ttu-id="a191b-105">そのため、コードは、アダプターによって提示される WCF サービスのクライアントとして機能します。</span><span class="sxs-lookup"><span data-stu-id="a191b-105">Your code therefore acts as a client to the WCF service presented by the adapter.</span></span>  
  
 <span data-ttu-id="a191b-106">[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]サービス モデルでは、クライアントとサービス間に存在するサービス コントラクトは、.NET インターフェイスとして表されます、操作はこのインターフェイスのメソッドとして表されます。</span><span class="sxs-lookup"><span data-stu-id="a191b-106">In the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] service model, the service contract that exists between a client and a service is represented as a .NET interface, and operations are represented as methods on this interface.</span></span> <span data-ttu-id="a191b-107">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] WCF アダプターを公開するメタデータからの対象となる操作には、このインターフェイスを生成するためのツールを提供するとします。</span><span class="sxs-lookup"><span data-stu-id="a191b-107">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] and WCF provide tools that enable you to generate this interface for targeted operations from the metadata that the adapter exposes.</span></span> <span data-ttu-id="a191b-108">これらのツールでは、サービス インターフェイスで公開されている操作の呼び出しに使用できる WCF クライアント クラスも作成します。</span><span class="sxs-lookup"><span data-stu-id="a191b-108">These tools also create a WCF client class that can be used to invoke the operations exposed in the service interface.</span></span> <span data-ttu-id="a191b-109">クライアント アプリケーションでは、アダプターの操作を呼び出すための WCF クライアント クラスのメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="a191b-109">A client application can call the methods of the WCF client class to invoke operations on the adapter.</span></span> <span data-ttu-id="a191b-110">受信操作を受信するサービスを実装するために、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、受信操作に対して生成されたインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="a191b-110">To implement a service to receive inbound operations from the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you implement the interface generated for the inbound operations.</span></span>  
  
 <span data-ttu-id="a191b-111">次のセクションでは、WCF クライアントでの操作を呼び出す、WCF サービス モデルを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a191b-111">The following section explains how to use the WCF service model to invoke operations with a WCF client.</span></span>  
  
## <a name="invoking-operations-on-the-sql-server-with-a-wcf-client"></a><span data-ttu-id="a191b-112">WCF クライアントでの SQL Server での操作を呼び出す</span><span class="sxs-lookup"><span data-stu-id="a191b-112">Invoking Operations on the SQL Server with a WCF Client</span></span>  
 <span data-ttu-id="a191b-113">WCF サービス モデルを使用して、操作を呼び出してする、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、まずターゲットの WCF クライアント クラスを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a191b-113">To use the WCF service model to invoke operations on the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you must first generate a WCF client class for the target operations.</span></span> <span data-ttu-id="a191b-114">WCF クライアントでは、このクラスのインスタンスを作成し、SQL Server システムでこれらの操作を実行するには、そのメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="a191b-114">You can then create an instance of this class, a WCF client, and call its methods to perform these operations on the SQL Server system.</span></span> <span data-ttu-id="a191b-115">このセクションでは、一般的な .NET アダプター クライアント アプリケーションの外観の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="a191b-115">This section provides an outline of how a typical .NET adapter client application looks like.</span></span> <span data-ttu-id="a191b-116">アダプターを使用して SQL Server データベースでさまざまな操作を実行する方法の詳細な説明については、特定のトピックで提供されます。</span><span class="sxs-lookup"><span data-stu-id="a191b-116">Detailed explanations on how to perform different operations on the SQL Server database using the adapter are provided in specific topics.</span></span>  
  
#### <a name="to-invoke-operations-on-the-sql-adapter"></a><span data-ttu-id="a191b-117">SQL アダプターの操作を呼び出す</span><span class="sxs-lookup"><span data-stu-id="a191b-117">To invoke operations on the SQL adapter</span></span>  
  
1. <span data-ttu-id="a191b-118">WCF クライアント クラスとヘルパー コードを生成します。</span><span class="sxs-lookup"><span data-stu-id="a191b-118">Generate a WCF client class and helper code.</span></span> <span data-ttu-id="a191b-119">使用して、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]WCF クライアント クラスを生成する作業する SQL Server データベースのアイテムを対象としました。</span><span class="sxs-lookup"><span data-stu-id="a191b-119">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]to generate a WCF client class targeted at the SQL Server database artifacts with which you want to work.</span></span> <span data-ttu-id="a191b-120">WCF クライアントを生成する方法の詳細については、[SQL Server のアイテムの WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a191b-120">For more information about how to generate a WCF client, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
2. <span data-ttu-id="a191b-121">WCF クライアントのインスタンスを作成し、WCF クライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="a191b-121">Create a WCF client instance and configure the WCF client.</span></span> <span data-ttu-id="a191b-122">WCF クライアントを構成するには、バインドと、クライアントが使用するエンドポイント アドレス (URI の接続) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a191b-122">Configuring the WCF client involves specifying the binding and endpoint address (connection URI) that the client will use.</span></span> <span data-ttu-id="a191b-123">コードで強制的に、または構成で宣言的に、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a191b-123">You can do this either imperatively in code or declaratively in configuration.</span></span> <span data-ttu-id="a191b-124">次のコード作成、WCF クライアントを対象とする、**選択**操作、**従業員**SQL Server データベースのテーブル。</span><span class="sxs-lookup"><span data-stu-id="a191b-124">The following code creates a WCF client that targets the **Select** operation on the **Employee** table in a SQL Server database.</span></span> <span data-ttu-id="a191b-125">また、SQL Server データベースの資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="a191b-125">It also sets the credentials for the SQL Server database.</span></span> <span data-ttu-id="a191b-126">WCF クライアントは、構成から初期化されます。</span><span class="sxs-lookup"><span data-stu-id="a191b-126">The WCF client is initialized from configuration.</span></span>  
  
   ```  
   TableOp_dbo_EmployeeClient client = new TableOp_dbo_EmployeeClient("SqlAdapterBinding_TableOp_dbo_Employee"); //picking the binding and address from the app.config  
  
   client.ClientCredentials.UserName.UserName = "myuser";  
   client.ClientCredentials.UserName.Password = "mypassword";  
   ```  
  
   > [!NOTE]
   >  <span data-ttu-id="a191b-127">コードでクライアント バインディングとエンドポイント アドレスを指定するか、app.config 構成ファイルで宣言します。</span><span class="sxs-lookup"><span data-stu-id="a191b-127">You can either specify the client binding and endpoint address in the code or declare it in the app.config configuration file.</span></span> <span data-ttu-id="a191b-128">上記のコード スニペットは、後者は使用します。</span><span class="sxs-lookup"><span data-stu-id="a191b-128">The preceding code snippet uses the latter.</span></span> <span data-ttu-id="a191b-129">いずれかのアプローチを使用する方法の詳細については、[クライアント バインディングを構成、SQL アダプターの](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a191b-129">For more information on how to use either approaches, see [Configure a Client Binding for the SQL Adapter](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md).</span></span>  
  
3. <span data-ttu-id="a191b-130">WCF クライアントを開きます。</span><span class="sxs-lookup"><span data-stu-id="a191b-130">Open the WCF client.</span></span>  
  
   ```  
   client.Open();  
   ```  
  
4. <span data-ttu-id="a191b-131">SQL server データベースでの選択操作を実行する前の手順で作成された WCF クライアントでメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a191b-131">Invoke methods on the WCF client created in preceding step to perform a Select operation on the SQL server database.</span></span> <span data-ttu-id="a191b-132">次のコードでは、SQL Server データベース テーブルに SELECT ステートメントを呼び出す、WCF クライアントの選択メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a191b-132">The following code invokes the Select method of the WCF client to invoke the SELECT statement on a SQL Server database table.</span></span>  
  
   ```  
   client.Select("*", "where [Name] = ‘John Smith’");  
   ```  
  
5. <span data-ttu-id="a191b-133">WCF クライアントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="a191b-133">Close the WCF client.</span></span>  
  
   ```  
   client.Close();  
   ```  
  
## <a name="see-also"></a><span data-ttu-id="a191b-134">参照</span><span class="sxs-lookup"><span data-stu-id="a191b-134">See Also</span></span>  
[<span data-ttu-id="a191b-135">WCF サービス モデルを使用して SQL アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="a191b-135">Develop SQL applications using the WCF Service model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)