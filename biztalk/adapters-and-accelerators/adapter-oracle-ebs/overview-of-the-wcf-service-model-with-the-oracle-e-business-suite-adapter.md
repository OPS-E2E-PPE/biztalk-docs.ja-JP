---
title: Oracle E-business Suite アダプターで WCF サービス モデルの概要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aeeac8a4-a4bc-4963-951c-0c806e232f1e
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b0a76ea41151e50b90d060ea60654b2c3287201
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375051"
---
# <a name="overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="6faed-102">Oracle E-business Suite アダプターで WCF サービス モデルの概要</span><span class="sxs-lookup"><span data-stu-id="6faed-102">Overview of the WCF service model with the Oracle E-Business Suite adapter</span></span>
<span data-ttu-id="6faed-103">[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] WCF サービスとして、Oracle E-business Suite システムを公開します。</span><span class="sxs-lookup"><span data-stu-id="6faed-103">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] exposes an Oracle E-Business Suite system as a WCF service.</span></span> <span data-ttu-id="6faed-104">、ストアド プロシージャを呼び出す例については、Oracle E-business Suite の成果物に対して操作を実行するには、さらに、Oracle E-business suite 操作を実行すると、アダプターでの操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6faed-104">To perform operations on Oracle E-Business Suite artifacts, for example to invoke a stored procedure, you invoke an operation on the adapter, which, in turn, performs the operation on the Oracle E-Business Suite.</span></span> <span data-ttu-id="6faed-105">コードは、アダプターによって提示される WCF サービスのクライアントとして機能します。</span><span class="sxs-lookup"><span data-stu-id="6faed-105">Your code acts as a client to the WCF service presented by the adapter.</span></span>  
  
 <span data-ttu-id="6faed-106">[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]サービス モデルでは、クライアントとサービス間に存在するサービス コントラクトは、.NET インターフェイスとして表されます、操作はこのインターフェイスのメソッドとして表されます。</span><span class="sxs-lookup"><span data-stu-id="6faed-106">In the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] service model, the service contract that exists between a client and a service is represented as a .NET interface, and operations are represented as methods on this interface.</span></span> <span data-ttu-id="6faed-107">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] WCF アダプターを公開するメタデータからの対象となる操作には、このインターフェイスを生成するためのツールを提供するとします。</span><span class="sxs-lookup"><span data-stu-id="6faed-107">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] and WCF provide tools that enable you to generate this interface for targeted operations from the metadata that the adapter exposes.</span></span> <span data-ttu-id="6faed-108">これらのツールでは、サービス インターフェイスで公開されている操作の呼び出しに使用できる WCF クライアント クラスも作成します。</span><span class="sxs-lookup"><span data-stu-id="6faed-108">These tools also create a WCF client class that can be used to invoke the operations exposed in the service interface.</span></span> <span data-ttu-id="6faed-109">クライアント アプリケーションでは、アダプターの操作を呼び出すための WCF クライアント クラスのメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="6faed-109">A client application can call the methods of the WCF client class to invoke operations on the adapter.</span></span>  
  
 <span data-ttu-id="6faed-110">次のセクションでは、WCF クライアントでの操作を呼び出す、WCF サービス モデルを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6faed-110">The following section explains how to use the WCF service model to invoke operations with a WCF client.</span></span>  
  
## <a name="invoking-operations-on-the-oracle-e-business-suite-with-a-wcf-client"></a><span data-ttu-id="6faed-111">WCF クライアントでの Oracle E-business Suite での操作を呼び出す</span><span class="sxs-lookup"><span data-stu-id="6faed-111">Invoking Operations on the Oracle E-Business Suite with a WCF Client</span></span>  
 <span data-ttu-id="6faed-112">WCF サービス モデルを使用して、操作を呼び出してする、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]、まずターゲットの WCF クライアント クラスを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6faed-112">To use the WCF service model to invoke operations on the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], you must first generate a WCF client class for the target operations.</span></span> <span data-ttu-id="6faed-113">WCF クライアントでは、このクラスのインスタンスを作成し、Oracle E-business Suite でこれらの操作を実行するには、そのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6faed-113">You can then create an instance of this class, a WCF client, and call its methods to perform these operations on the Oracle E-Business Suite.</span></span>  
  
#### <a name="to-invoke-operations-on-the-oracle-e-business-adapter"></a><span data-ttu-id="6faed-114">Oracle E-business アダプターの操作を呼び出す</span><span class="sxs-lookup"><span data-stu-id="6faed-114">To invoke operations on the Oracle E-Business adapter</span></span>  
  
1. <span data-ttu-id="6faed-115">WCF クライアント クラスとヘルパー コードを生成します。</span><span class="sxs-lookup"><span data-stu-id="6faed-115">Generate a WCF client class and helper code.</span></span> <span data-ttu-id="6faed-116">使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または、ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) Oracle E-business Suite の成果物を対象とした WCF クライアント クラスを生成する作業します。</span><span class="sxs-lookup"><span data-stu-id="6faed-116">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe) to generate a WCF client class targeted at Oracle E-Business Suite artifacts with which you want to work.</span></span> <span data-ttu-id="6faed-117">WCF クライアントを生成する方法の詳細については、次を参照してください。 [Oracle E-business ソリューションの成果物の WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)します。</span><span class="sxs-lookup"><span data-stu-id="6faed-117">For more information about how to generate a WCF client, see [Generate a WCF Client or a WCF Service Contract for Oracle E-Business Solution Artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  
  
2. <span data-ttu-id="6faed-118">WCF クライアントのインスタンスを作成し、WCF クライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="6faed-118">Create a WCF client instance and configure the WCF client.</span></span> <span data-ttu-id="6faed-119">WCF クライアントを構成するには、バインドと、クライアントが使用するエンドポイント アドレス (URI の接続) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6faed-119">Configuring the WCF client involves specifying the binding and endpoint address (connection URI) that the client will use.</span></span> <span data-ttu-id="6faed-120">コードで強制的に、または構成で宣言的に、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6faed-120">You can do this either imperatively in code or declaratively in configuration.</span></span> <span data-ttu-id="6faed-121">次のコード作成、WCF クライアントを対象とする、**顧客インターフェイス**で同時実行プログラム、 **Receivables** Oracle E-business Suite でのアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="6faed-121">The following code creates a WCF client that targets the **Customer Interface** concurrent program in the **Receivables** application in the Oracle E-Business Suite.</span></span> <span data-ttu-id="6faed-122">また、Oracle E-business Suite の資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="6faed-122">It also sets the credentials for the Oracle E-Business Suite.</span></span> <span data-ttu-id="6faed-123">WCF クライアントは、構成から初期化されます。</span><span class="sxs-lookup"><span data-stu-id="6faed-123">The WCF client is initialized from configuration.</span></span>  
  
   ```  
   ConcurrentPrograms_ARClient client = new ConcurrentPrograms_ARClient("OracleEBSBinding_ConcurrentPrograms_AR"); //picking the binding and address from app.config  
  
   client.ClientCredentials.UserName.UserName = "myuser";  
   client.ClientCredentials.UserName.Password = "mypassword";  
   ```  
  
   > [!NOTE]
   >  <span data-ttu-id="6faed-124">コードでクライアント バインディングとエンドポイント アドレスを指定するか、app.config 構成ファイルで宣言します。</span><span class="sxs-lookup"><span data-stu-id="6faed-124">You can either specify the client binding and endpoint address in the code or declare it in the app.config configuration file.</span></span> <span data-ttu-id="6faed-125">上記のコード スニペットは、後者は使用します。</span><span class="sxs-lookup"><span data-stu-id="6faed-125">The preceding code snippet uses the latter.</span></span> <span data-ttu-id="6faed-126">いずれかのアプローチを使用する方法の詳細については、次を参照してください。[クライアント バインディングを構成する、Oracle E-business suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)します。</span><span class="sxs-lookup"><span data-stu-id="6faed-126">For more information on how to use either approaches, see [Configure a Client Binding for the Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md).</span></span>  
  
3. <span data-ttu-id="6faed-127">WCF クライアントを開きます。</span><span class="sxs-lookup"><span data-stu-id="6faed-127">Open the WCF client.</span></span>  
  
   ```  
   client.Open();  
   ```  
  
4. <span data-ttu-id="6faed-128">Oracle E-business suite 操作を実行する手順 2. で作成された WCF クライアントでメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6faed-128">Invoke methods on the WCF client created in step 2 to perform operations on the Oracle E-Business Suite.</span></span> <span data-ttu-id="6faed-129">次のコードを呼び出す、**顧客インターフェイス**で同時実行プログラム、 **Receivables** Oracle E-business Suite でのアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="6faed-129">The following code invokes the **Customer Interface** concurrent program in the **Receivables** application in the Oracle E-Business Suite.</span></span>  
  
   ```  
   string Result = client.RACUST(null, null, null, description, null, recipro_cust, org_id);  
   ```  
  
    <span data-ttu-id="6faed-130">**RACUST**顧客インターフェイスの同時実行プログラムの実際の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6faed-130">**RACUST** is the actual name of the Customer Interface concurrent program.</span></span> <span data-ttu-id="6faed-131">**顧客インターフェイス**同時実行プログラムの表示名です。</span><span class="sxs-lookup"><span data-stu-id="6faed-131">**Customer Interface** is the friendly name of the concurrent program.</span></span>  
  
5. <span data-ttu-id="6faed-132">WCF クライアントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="6faed-132">Close the WCF client.</span></span>  
  
   ```  
   client.Close();  
   ```  
  
## <a name="see-also"></a><span data-ttu-id="6faed-133">参照</span><span class="sxs-lookup"><span data-stu-id="6faed-133">See Also</span></span>  
 [<span data-ttu-id="6faed-134">WCF チャネル モデルを使用して Oracle E-business Suite アプリケーションの開発します。</span><span class="sxs-lookup"><span data-stu-id="6faed-134">Develop Oracle E-Business Suite Applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)