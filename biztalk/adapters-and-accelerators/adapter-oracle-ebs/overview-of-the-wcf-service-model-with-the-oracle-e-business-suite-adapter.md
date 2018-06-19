---
title: Oracle E-business Suite アダプターで WCF サービス モデルの概要 |Microsoft ドキュメント
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
ms.openlocfilehash: f40b22865ca45cbd10823f6c514f75e5965f1df5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216450"
---
# <a name="overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="defa7-102">Oracle E-business Suite アダプターで WCF サービス モデルの概要</span><span class="sxs-lookup"><span data-stu-id="defa7-102">Overview of the WCF service model with the Oracle E-Business Suite adapter</span></span>
<span data-ttu-id="defa7-103">[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]を WCF サービスとして、Oracle E-business Suite システムを公開します。</span><span class="sxs-lookup"><span data-stu-id="defa7-103">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] exposes an Oracle E-Business Suite system as a WCF service.</span></span> <span data-ttu-id="defa7-104">ストアド プロシージャを呼び出す例については、Oracle E-business Suite アイテムに対して操作を実行するには、さらに、Oracle E-business Suite で操作を実行すると、アダプターでの操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="defa7-104">To perform operations on Oracle E-Business Suite artifacts, for example to invoke a stored procedure, you invoke an operation on the adapter, which, in turn, performs the operation on the Oracle E-Business Suite.</span></span> <span data-ttu-id="defa7-105">コードは、アダプターによって提示される WCF サービスのクライアントとして機能します。</span><span class="sxs-lookup"><span data-stu-id="defa7-105">Your code acts as a client to the WCF service presented by the adapter.</span></span>  
  
 <span data-ttu-id="defa7-106">[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]サービス モデルでは、クライアントとサービス間に存在するサービス コントラクトは、.NET インターフェイスとして表されます、操作は、このインターフェイスのメソッドとして表されます。</span><span class="sxs-lookup"><span data-stu-id="defa7-106">In the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] service model, the service contract that exists between a client and a service is represented as a .NET interface, and operations are represented as methods on this interface.</span></span> <span data-ttu-id="defa7-107">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] WCF が使用するアダプターを公開するメタデータから対象となる操作について、このインターフェイスを生成するツールを提供します。</span><span class="sxs-lookup"><span data-stu-id="defa7-107">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] and WCF provide tools that enable you to generate this interface for targeted operations from the metadata that the adapter exposes.</span></span> <span data-ttu-id="defa7-108">これらのツールでは、サービス インターフェイスの公開操作の呼び出しに使用できる WCF クライアント クラスも作成します。</span><span class="sxs-lookup"><span data-stu-id="defa7-108">These tools also create a WCF client class that can be used to invoke the operations exposed in the service interface.</span></span> <span data-ttu-id="defa7-109">クライアント アプリケーションは、アダプターの操作の呼び出しに WCF クライアント クラスのメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="defa7-109">A client application can call the methods of the WCF client class to invoke operations on the adapter.</span></span>  
  
 <span data-ttu-id="defa7-110">次のセクションでは、モデルを使用して、WCF サービスと WCF クライアントの操作を呼び出す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="defa7-110">The following section explains how to use the WCF service model to invoke operations with a WCF client.</span></span>  
  
## <a name="invoking-operations-on-the-oracle-e-business-suite-with-a-wcf-client"></a><span data-ttu-id="defa7-111">WCF クライアントと Oracle E-business Suite での操作を呼び出す</span><span class="sxs-lookup"><span data-stu-id="defa7-111">Invoking Operations on the Oracle E-Business Suite with a WCF Client</span></span>  
 <span data-ttu-id="defa7-112">モデルを使用して、WCF サービスで操作を呼び出す、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]、まず対象の操作用の WCF クライアント クラスを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="defa7-112">To use the WCF service model to invoke operations on the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], you must first generate a WCF client class for the target operations.</span></span> <span data-ttu-id="defa7-113">このクラスでは、WCF クライアントのインスタンスを作成し、Oracle E-business Suite でこれらの操作を実行するには、そのメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="defa7-113">You can then create an instance of this class, a WCF client, and call its methods to perform these operations on the Oracle E-Business Suite.</span></span>  
  
#### <a name="to-invoke-operations-on-the-oracle-e-business-adapter"></a><span data-ttu-id="defa7-114">Oracle E-business アダプターの操作を呼び出す</span><span class="sxs-lookup"><span data-stu-id="defa7-114">To invoke operations on the Oracle E-Business adapter</span></span>  
  
1.  <span data-ttu-id="defa7-115">WCF クライアント クラスとヘルパー コードを生成します。</span><span class="sxs-lookup"><span data-stu-id="defa7-115">Generate a WCF client class and helper code.</span></span> <span data-ttu-id="defa7-116">使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または、ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) Oracle E-business Suite の成果物を対象と WCF クライアント クラスを生成する作業します。</span><span class="sxs-lookup"><span data-stu-id="defa7-116">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe) to generate a WCF client class targeted at Oracle E-Business Suite artifacts with which you want to work.</span></span> <span data-ttu-id="defa7-117">WCF クライアントを生成する方法の詳細については、次を参照してください。 [Oracle E ビジネス ソリューションの成果物の WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="defa7-117">For more information about how to generate a WCF client, see [Generate a WCF Client or a WCF Service Contract for Oracle E-Business Solution Artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  
  
2.  <span data-ttu-id="defa7-118">WCF クライアント インスタンスを作成し、WCF クライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="defa7-118">Create a WCF client instance and configure the WCF client.</span></span> <span data-ttu-id="defa7-119">WCF クライアントを構成すると、バインディングと、クライアントが使用するエンドポイント アドレス (接続 URI) を指定することがあります。</span><span class="sxs-lookup"><span data-stu-id="defa7-119">Configuring the WCF client involves specifying the binding and endpoint address (connection URI) that the client will use.</span></span> <span data-ttu-id="defa7-120">これは、コードで命令として記述または構成で宣言によって行うことができます。</span><span class="sxs-lookup"><span data-stu-id="defa7-120">You can do this either imperatively in code or declaratively in configuration.</span></span> <span data-ttu-id="defa7-121">次のコードを作成する WCF クライアントを対象とする、**顧客インターフェイス**で同時実行プログラム、**債権**Oracle E-business suite アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="defa7-121">The following code creates a WCF client that targets the **Customer Interface** concurrent program in the **Receivables** application in the Oracle E-Business Suite.</span></span> <span data-ttu-id="defa7-122">また、Oracle E-business Suite の資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="defa7-122">It also sets the credentials for the Oracle E-Business Suite.</span></span> <span data-ttu-id="defa7-123">WCF クライアントは、構成から初期化されます。</span><span class="sxs-lookup"><span data-stu-id="defa7-123">The WCF client is initialized from configuration.</span></span>  
  
    ```  
    ConcurrentPrograms_ARClient client = new ConcurrentPrograms_ARClient("OracleEBSBinding_ConcurrentPrograms_AR"); //picking the binding and address from app.config  
  
    client.ClientCredentials.UserName.UserName = "myuser";  
    client.ClientCredentials.UserName.Password = "mypassword";  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="defa7-124">コードでクライアントのバインディングとエンドポイント アドレスを指定するか、app.config 構成ファイルで宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="defa7-124">You can either specify the client binding and endpoint address in the code or declare it in the app.config configuration file.</span></span> <span data-ttu-id="defa7-125">上記のコード スニペットは、後者は使用します。</span><span class="sxs-lookup"><span data-stu-id="defa7-125">The preceding code snippet uses the latter.</span></span> <span data-ttu-id="defa7-126">いずれかのアプローチを使用する方法の詳細については、次を参照してください。 [for Oracle E-business Suite には、クライアント バインディングを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)です。</span><span class="sxs-lookup"><span data-stu-id="defa7-126">For more information on how to use either approaches, see [Configure a Client Binding for the Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md).</span></span>  
  
3.  <span data-ttu-id="defa7-127">WCF クライアントを開きます。</span><span class="sxs-lookup"><span data-stu-id="defa7-127">Open the WCF client.</span></span>  
  
    ```  
    client.Open();  
    ```  
  
4.  <span data-ttu-id="defa7-128">Oracle E-business Suite での操作を実行する手順 2. で作成された WCF クライアントでメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="defa7-128">Invoke methods on the WCF client created in step 2 to perform operations on the Oracle E-Business Suite.</span></span> <span data-ttu-id="defa7-129">次のコードを呼び出す、**顧客インターフェイス**でプログラムを同時、**債権**Oracle E-business suite アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="defa7-129">The following code invokes the **Customer Interface** concurrent program in the **Receivables** application in the Oracle E-Business Suite.</span></span>  
  
    ```  
    string Result = client.RACUST(null, null, null, description, null, recipro_cust, org_id);  
    ```  
  
     <span data-ttu-id="defa7-130">**RACUST**顧客インターフェイスの同時実行プログラムの実際の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="defa7-130">**RACUST** is the actual name of the Customer Interface concurrent program.</span></span> <span data-ttu-id="defa7-131">**お客様のインターフェイス**同時実行プログラムのわかりやすい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="defa7-131">**Customer Interface** is the friendly name of the concurrent program.</span></span>  
  
5.  <span data-ttu-id="defa7-132">WCF クライアントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="defa7-132">Close the WCF client.</span></span>  
  
    ```  
    client.Close();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="defa7-133">参照</span><span class="sxs-lookup"><span data-stu-id="defa7-133">See Also</span></span>  
 [<span data-ttu-id="defa7-134">WCF チャネル モデルを使用して Oracle E-business Suite アプリケーションの開発します。</span><span class="sxs-lookup"><span data-stu-id="defa7-134">Develop Oracle E-Business Suite Applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)