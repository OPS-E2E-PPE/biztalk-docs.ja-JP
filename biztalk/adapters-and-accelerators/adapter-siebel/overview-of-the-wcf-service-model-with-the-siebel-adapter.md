---
title: Siebel アダプターと WCF サービス モデルの概要 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- how to, invoke operations on the Siebel system with a WCF client
- WCF service model, overview of
ms.assetid: 0e812473-0f50-4972-8b07-ec8edc2ef000
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c638255b103a9c588f22d6ddcb2a75b81619b73
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222114"
---
# <a name="overview-of-the-wcf-service-model-with-the-siebel-adapter"></a><span data-ttu-id="8d753-102">Siebel アダプターと WCF サービス モデルの概要</span><span class="sxs-lookup"><span data-stu-id="8d753-102">Overview of the WCF service model with the Siebel adapter</span></span>
<span data-ttu-id="8d753-103">[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]を WCF サービスとしての Siebel システムを公開します。</span><span class="sxs-lookup"><span data-stu-id="8d753-103">The [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] exposes a Siebel system as a WCF service.</span></span> <span data-ttu-id="8d753-104">Siebel ビジネス サービスのメソッドを呼び出す例については、Siebel システムのアイテムに対して操作を実行するには、さらに、Siebel システムで操作を実行すると、アダプターでの操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8d753-104">To perform operations on Siebel system artifacts, for example to invoke a method of a Siebel business service, you invoke an operation on the adapter, which, in turn, performs the operation on the Siebel system.</span></span> <span data-ttu-id="8d753-105">したがって、コードは、アダプターによって提示される WCF サービスのクライアントとして機能します。</span><span class="sxs-lookup"><span data-stu-id="8d753-105">Your code therefore acts as a client to the WCF service presented by the adapter.</span></span>  
  
 <span data-ttu-id="8d753-106">[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]サービス モデルでは、クライアントとサービス間に存在するサービス コントラクトは、.NET インターフェイスとして表されます、操作は、このインターフェイスのメソッドとして表されます。</span><span class="sxs-lookup"><span data-stu-id="8d753-106">In the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] service model, the service contract that exists between a client and a service is represented as a .NET interface, and operations are represented as methods on this interface.</span></span> <span data-ttu-id="8d753-107">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] WCF が使用するアダプターを公開するメタデータから対象となる操作について、このインターフェイスを生成するツールを提供します。</span><span class="sxs-lookup"><span data-stu-id="8d753-107">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] and WCF provide tools that enable you to generate this interface for targeted operations from the metadata that the adapter exposes.</span></span> <span data-ttu-id="8d753-108">これらのツールでは、サービス インターフェイスの公開操作の呼び出しに使用できる WCF クライアント クラスも作成します。</span><span class="sxs-lookup"><span data-stu-id="8d753-108">These tools also create a WCF client class that can be used to invoke the operations exposed in the service interface.</span></span> <span data-ttu-id="8d753-109">クライアント アプリケーションは、アダプターの操作の呼び出しに WCF クライアント クラスのメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="8d753-109">A client application can call the methods of the WCF client class to invoke operations on the adapter.</span></span>  
  
 <span data-ttu-id="8d753-110">次のセクションでは、モデルを使用して、WCF サービスと WCF クライアントの操作を呼び出す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8d753-110">The following section explains how to use the WCF service model to invoke operations with a WCF client.</span></span>  
  
## <a name="invoking-operations-on-the-siebel-system-with-a-wcf-client"></a><span data-ttu-id="8d753-111">WCF クライアントと Siebel システムの操作を呼び出す</span><span class="sxs-lookup"><span data-stu-id="8d753-111">Invoking Operations on the Siebel System with a WCF Client</span></span>  
 <span data-ttu-id="8d753-112">モデルを使用して、WCF サービスで操作を呼び出す、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]、まず対象の操作用の WCF クライアント クラスを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d753-112">To use the WCF service model to invoke operations on the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], you must first generate a WCF client class for the target operations.</span></span> <span data-ttu-id="8d753-113">このクラスでは、WCF クライアントのインスタンスを作成し、Siebel システムでこれらの操作を実行するには、そのメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="8d753-113">You can then create an instance of this class, a WCF client, and call its methods to perform these operations on the Siebel system.</span></span>  
  
#### <a name="to-invoke-operations-on-the-siebel-adapter"></a><span data-ttu-id="8d753-114">Siebel アダプターの操作を呼び出す</span><span class="sxs-lookup"><span data-stu-id="8d753-114">To invoke operations on the Siebel adapter</span></span>  
  
1.  <span data-ttu-id="8d753-115">WCF クライアント クラスとヘルパー コードを生成します。</span><span class="sxs-lookup"><span data-stu-id="8d753-115">Generate a WCF client class and helper code.</span></span> <span data-ttu-id="8d753-116">使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または、ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) Siebel システムの成果物を対象と WCF クライアント クラスを生成する作業します。</span><span class="sxs-lookup"><span data-stu-id="8d753-116">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe) to generate a WCF client class targeted at the Siebel system artifacts with which you want to work.</span></span> <span data-ttu-id="8d753-117">WCF クライアントを生成する方法の詳細については、次を参照してください。 [Siebel ソリューションの成果物のため、WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="8d753-117">For more information about how to generate a WCF client, see [Generate a WCF Client or a WCF service contract for Siebel Solution Artifacts](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md).</span></span>  
  
2.  <span data-ttu-id="8d753-118">WCF クライアント インスタンスを作成し、WCF クライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="8d753-118">Create a WCF client instance and configure the WCF client.</span></span> <span data-ttu-id="8d753-119">WCF クライアントを構成すると、バインディングと、クライアントが使用するエンドポイント アドレス (接続 URI) を指定することがあります。</span><span class="sxs-lookup"><span data-stu-id="8d753-119">Configuring the WCF client involves specifying the binding and endpoint address (connection URI) that the client will use.</span></span> <span data-ttu-id="8d753-120">これは、コードで命令として記述または構成で宣言によって行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8d753-120">You can do this either imperatively in code or declaratively in configuration.</span></span> <span data-ttu-id="8d753-121">WCF クライアントを構成する方法の詳細については、次を参照してください。 [Siebel システムの WCF クライアントを構成する](../../adapters-and-accelerators/adapter-siebel/configure-a-wcf-client-for-a-siebel-system.md)です。</span><span class="sxs-lookup"><span data-stu-id="8d753-121">For more information about how to configure the WCF client, see [Configure a WCF Client for a Siebel System](../../adapters-and-accelerators/adapter-siebel/configure-a-wcf-client-for-a-siebel-system.md).</span></span> <span data-ttu-id="8d753-122">次のコードでは、タイムスタンプの Siebel ビジネス サービスを対象とする WCF クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="8d753-122">The following code creates a WCF client that targets the Siebel TimeStamp business service.</span></span> <span data-ttu-id="8d753-123">また、Siebel システムの資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="8d753-123">It also sets the credentials for the Siebel system.</span></span> <span data-ttu-id="8d753-124">WCF クライアントは、構成から初期化されます。</span><span class="sxs-lookup"><span data-stu-id="8d753-124">The WCF client is initialized from configuration.</span></span>  
  
    ```  
    BusinessServices_TimeStamp_OperationClient client =  
        new BusinessServices_TimeStamp_OperationClient("SiebelBinding_BusinessServices_TimeStamp_Operation");  
  
    client.ClientCredentials.UserName.UserName = "YourUserName";  
    client.ClientCredentials.UserName.Password = "YourPassword";  
    ```  
  
3.  <span data-ttu-id="8d753-125">WCF クライアントを開きます。</span><span class="sxs-lookup"><span data-stu-id="8d753-125">Open the WCF client.</span></span>  
  
    ```  
    client.Open();  
    ```  
  
4.  <span data-ttu-id="8d753-126">Siebel システムに対して操作を実行する手順 2. で作成された WCF クライアントでメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8d753-126">Invoke methods on the WCF client created in step 2 to perform operations on the Siebel system.</span></span> <span data-ttu-id="8d753-127">次のコードを呼び出す、 **Execute**メソッドを呼び出す、WCF クライアントの**Execute** Siebel システムのタイムスタンプのビジネス サービスのメソッドです。</span><span class="sxs-lookup"><span data-stu-id="8d753-127">The following code invokes the **Execute** method of the WCF client to invoke the **Execute** method of the TimeStamp business service on the Siebel system.</span></span>  
  
    ```  
    // Create a parameter to hold the results and then invoke the Execute method of the TimeStamp business service.  
    microsoft.lobservices.siebel._2007._03.BusinessServices.TimeStamp.ExecuteResponseRecord er;  
    er = client.Execute();  
    ```  
  
5.  <span data-ttu-id="8d753-128">WCF クライアントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="8d753-128">Close the WCF client.</span></span>  
  
    ```  
    client.Close();  
    ```  
  
 <span data-ttu-id="8d753-129">Siebel ビジネス サービス メソッドの呼び出しの詳細については、次を参照してください[WCF サービス モデルを使用して、Siebel アダプターのビジネス サービス メソッドの呼び出し。](../../adapters-and-accelerators/adapter-siebel/run-business-service-methods-with-the-siebel-adapter-using-a-wcf-service.md)</span><span class="sxs-lookup"><span data-stu-id="8d753-129">For more information about invoking Siebel business service methods, see [Invoke Business Service Methods with the Siebel adapter using the WCF Service Model](../../adapters-and-accelerators/adapter-siebel/run-business-service-methods-with-the-siebel-adapter-using-a-wcf-service.md)</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8d753-130">参照</span><span class="sxs-lookup"><span data-stu-id="8d753-130">See Also</span></span>  
 [<span data-ttu-id="8d753-131">WCF サービス モデルを使用して Siebel アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="8d753-131">Develop Siebel Applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)