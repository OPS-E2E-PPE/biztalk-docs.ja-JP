---
title: SAP アダプターで WCF サービス モデルの概要 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, overview of using
ms.assetid: 02a4b43e-ade0-4dba-b8f6-074bca7cbe5c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da5b2f7cc8e38eb8afd211a2008c0f740760cd4f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218570"
---
# <a name="overview-of-the-wcf-service-model-with-the-sap-adapter"></a><span data-ttu-id="00e36-102">SAP アダプターで WCF サービス モデルの概要</span><span class="sxs-lookup"><span data-stu-id="00e36-102">Overview of the WCF service model with the SAP adapter</span></span>
<span data-ttu-id="00e36-103">操作を使用する際にする、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]サーフェスは、コードは、機能、クライアントと、アダプターにサービスのどちらかです。</span><span class="sxs-lookup"><span data-stu-id="00e36-103">When you consume operations that the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] surfaces, your code acts either as a client or a service to the adapter.</span></span>  
  
 <span data-ttu-id="00e36-104">コードは、次のような SAP システムの操作を呼び出すクライアントとして機能します。</span><span class="sxs-lookup"><span data-stu-id="00e36-104">Your code acts as a client to invoke the following kinds of operations on the SAP system:</span></span>  
  
-   <span data-ttu-id="00e36-105">リモート関数呼び出し (RFC) を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="00e36-105">Invoke a Remote Function Call (RFC).</span></span>  
  
-   <span data-ttu-id="00e36-106">トランザクション リモート関数呼び出し (tRFC) を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="00e36-106">Invoke a Transactional Remote Function Call (tRFC).</span></span>  
  
-   <span data-ttu-id="00e36-107">プログラミング インターフェイス (BAPI) ビジネス アプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="00e36-107">Invoke a Business Application Programming Interface (BAPI).</span></span>  
  
-   <span data-ttu-id="00e36-108">中間ドキュメント (IDOC) を送信します。</span><span class="sxs-lookup"><span data-stu-id="00e36-108">Send an Intermediate Document (IDOC)</span></span>  
  
 <span data-ttu-id="00e36-109">コードは、次のような操作を受信するサービスとして動作します。</span><span class="sxs-lookup"><span data-stu-id="00e36-109">Your code acts as a service to receive the following kinds of operations:</span></span>  
  
-   <span data-ttu-id="00e36-110">RFC (RFC サーバー) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="00e36-110">Receive an RFC (RFC server)</span></span>  
  
-   <span data-ttu-id="00e36-111">TRFC (tRFC サーバー) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="00e36-111">Receive a tRFC (tRFC server)</span></span>  
  
-   <span data-ttu-id="00e36-112">IDOC を受信します。</span><span class="sxs-lookup"><span data-stu-id="00e36-112">Receive an IDOC.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00e36-113">Bapi のビジネス オブジェクト リポジトリ (どれ) に配置されているビジネス オブジェクト上の SAP システムで公開されたメソッドであるために、Bapi を受信できません。</span><span class="sxs-lookup"><span data-stu-id="00e36-113">Because BAPIs are methods exposed by the SAP system on business objects located in the Business Object Repository (BOR), you cannot receive BAPIs.</span></span>  
  
 <span data-ttu-id="00e36-114">[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]サービス モデルでは、クライアントとサービス間に存在するサービス コントラクトは、.NET インターフェイスとして表されます、操作は、このインターフェイスのメソッドとして表されます。</span><span class="sxs-lookup"><span data-stu-id="00e36-114">In the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] service model, the service contract that exists between a client and a service is represented as a .NET interface, and operations are represented as methods on this interface.</span></span> <span data-ttu-id="00e36-115">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] WCF が使用するアダプターを公開するメタデータから対象となる操作について、このインターフェイスを生成するツールを提供します。</span><span class="sxs-lookup"><span data-stu-id="00e36-115">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] and WCF provide tools that enable you to generate this interface for targeted operations from the metadata that the adapter exposes.</span></span> <span data-ttu-id="00e36-116">これらのツールでは、サービス インターフェイスの公開操作の呼び出しに使用できる WCF クライアント クラスも作成します。</span><span class="sxs-lookup"><span data-stu-id="00e36-116">These tools also create a WCF client class that can be used to invoke the operations exposed in the service interface.</span></span> <span data-ttu-id="00e36-117">クライアント アプリケーションは、アダプターの操作の呼び出しに WCF クライアント クラスのメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="00e36-117">A client application can call the methods of the WCF client class to invoke operations on the adapter.</span></span> <span data-ttu-id="00e36-118">操作を受信するサービスを実装する、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]ターゲットの操作に対して生成されたインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="00e36-118">To implement a service to receive operations from the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], you implement the interface generated for the target operation.</span></span>  
  
 <span data-ttu-id="00e36-119">次のセクションでは、モデルを使用して、WCF サービスのクライアントとサービスのコードを作成する方法を説明する、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="00e36-119">The following sections explain how to use the WCF service model to create client and service code for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="creating-a-wcf-client-and-invoking-operations-on-sap"></a><span data-ttu-id="00e36-120">WCF クライアントを作成して、SAP で操作を呼び出すこと</span><span class="sxs-lookup"><span data-stu-id="00e36-120">Creating a WCF Client and Invoking Operations on SAP</span></span>  
 <span data-ttu-id="00e36-121">モデルを使用して、WCF サービスで操作を呼び出す、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]、まず対象の操作用の WCF クライアント クラスを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00e36-121">To use the WCF service model to invoke operations on the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], you must first generate a WCF client class for the target operations.</span></span> <span data-ttu-id="00e36-122">このクラスでは、WCF クライアントのインスタンスを作成し、SAP システムでの操作を実行するには、そのメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="00e36-122">You can then create an instance of this class, a WCF client, and call its methods to perform operations on the SAP system.</span></span>  
  
#### <a name="to-invoke-operations-on-the-sap-adapter"></a><span data-ttu-id="00e36-123">SAP アダプターの操作を呼び出す</span><span class="sxs-lookup"><span data-stu-id="00e36-123">To invoke operations on the SAP adapter</span></span>  
  
1.  <span data-ttu-id="00e36-124">WCF クライアント クラスとヘルパー コードを生成します。</span><span class="sxs-lookup"><span data-stu-id="00e36-124">Generate a WCF client class and helper code.</span></span> <span data-ttu-id="00e36-125">使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または、ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を SAP システムの成果物を対象と WCF クライアント クラスを生成する作業します。</span><span class="sxs-lookup"><span data-stu-id="00e36-125">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe) to generate a WCF client class targeted at the SAP system artifacts with which you want to work.</span></span> <span data-ttu-id="00e36-126">WCF クライアントを生成する方法の詳細については、次を参照してください。 [WCF クライアントまたは SAP ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="00e36-126">For more information about how to generate a WCF client, see [Generate a WCF client or a WCF service contract for SAP solution artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span></span>  
  
2.  <span data-ttu-id="00e36-127">クライアントのバインディングを指定することによって、WCF クライアントのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="00e36-127">Create a WCF client instance by specifying a client binding.</span></span> <span data-ttu-id="00e36-128">クライアントのバインディングを指定するには、バインドと WCF クライアントが使用するエンドポイント アドレスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00e36-128">Specifying a client binding involves specifying the binding and endpoint address that the WCF client will use.</span></span> <span data-ttu-id="00e36-129">これは、コードで命令として記述または構成で宣言によって行うことができます。</span><span class="sxs-lookup"><span data-stu-id="00e36-129">You can do this either imperatively in code or declaratively in configuration.</span></span> <span data-ttu-id="00e36-130">クライアントのバインディングを指定する方法の詳細については、次を参照してください。[クライアントを、SAP システムのバインド構成](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md)です。</span><span class="sxs-lookup"><span data-stu-id="00e36-130">For more information about how to specify a client binding, see [Configure a client binding for the SAP system](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md).</span></span> <span data-ttu-id="00e36-131">次のコードでは、SAP システムで RFC を呼び出すために使用できる WCF クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="00e36-131">The following code creates a WCF client that can be used to invoke an RFC on the SAP system.</span></span> <span data-ttu-id="00e36-132">また、SAP システムの資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="00e36-132">It also sets the credentials for the SAP system.</span></span> <span data-ttu-id="00e36-133">WCF クライアントは、構成から初期化されます。</span><span class="sxs-lookup"><span data-stu-id="00e36-133">The WCF client is initialized from configuration.</span></span>  
  
    ```  
    RfcClient rfcClient = new RfcClient("SAPBinding_Rfc");  
  
    rfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
    rfcClient.ClientCredentials.UserName.Password = "YourPassword";  
    ```  
  
3.  <span data-ttu-id="00e36-134">WCF クライアントを開きます。</span><span class="sxs-lookup"><span data-stu-id="00e36-134">Open the WCF client.</span></span>  
  
    ```  
    rfcClient.Open();  
    ```  
  
4.  <span data-ttu-id="00e36-135">SAP システムでの操作を実行する手順 2. で作成された WCF クライアントでメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="00e36-135">Invoke methods on the WCF client created in step 2 to perform operations on the SAP system.</span></span> <span data-ttu-id="00e36-136">次のコードを呼び出す、 **SD_RFC_CUSTOMER_GET**を SAP システムで RFC を呼び出す、WCF クライアントのメソッドです。</span><span class="sxs-lookup"><span data-stu-id="00e36-136">The following code invokes the **SD_RFC_CUSTOMER_GET** method of the WCF client to invoke the RFC on the SAP system.</span></span>  
  
    ```  
    microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[] customers =   
        new microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[0];  
  
    rfcClient.SD_RFC_CUSTOMER_GET(string.Empty, "AB*", ref customers);  
    ```  
  
5.  <span data-ttu-id="00e36-137">WCF クライアントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="00e36-137">Close the WCF client.</span></span>  
  
    ```  
    rfcClient.Close();  
  
    ```  
  
## <a name="creating-and-implementing-a-wcf-service-by-using-the-sap-adapter"></a><span data-ttu-id="00e36-138">作成して、SAP アダプターを使用して WCF サービスの実装</span><span class="sxs-lookup"><span data-stu-id="00e36-138">Creating and Implementing a WCF Service by Using the SAP Adapter</span></span>  
 <span data-ttu-id="00e36-139">モデルを使用して、WCF サービスからの操作を受信する、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]、最初に、.NET (WCF サービス コントラクトとも呼ばれます) を表すインターフェイスによって公開されるサービス コントラクトを生成する必要があります、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]操作します。</span><span class="sxs-lookup"><span data-stu-id="00e36-139">To use the WCF service model to receive operations from the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], you must first generate the .NET interface (also called the WCF service contract) that represents the service contract exposed by the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] for the operation.</span></span> <span data-ttu-id="00e36-140">これを行う方法の詳細については、次を参照してください。 [WCF クライアントまたは SAP ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="00e36-140">For more information about how to do this, see [Generate a WCF client or a WCF service contract for SAP solution artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span></span>  
  
 <span data-ttu-id="00e36-141">WCF サービスを実装するには、生成されたインターフェイスを実装することで。</span><span class="sxs-lookup"><span data-stu-id="00e36-141">You then implement a WCF service by implementing the generated interface.</span></span> <span data-ttu-id="00e36-142">このクラスには、操作を処理して、アダプターに応答を返すビジネス ロジックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="00e36-142">This class contains the business logic to process the operation and return a response to the adapter.</span></span> <span data-ttu-id="00e36-143">サービス ホストを使用して (**System.ServiceModel.ServiceHost**) をこのサービスのインスタンスをホストします。</span><span class="sxs-lookup"><span data-stu-id="00e36-143">Then you use a service host (**System.ServiceModel.ServiceHost**) to host an instance of this service.</span></span>  
  
#### <a name="to-create-and-implement-a-wcf-service"></a><span data-ttu-id="00e36-144">作成して、WCF サービスを実装するには</span><span class="sxs-lookup"><span data-stu-id="00e36-144">To create and implement a WCF service</span></span>  
  
1.  <span data-ttu-id="00e36-145">WCF サービス コントラクトとヘルパー クラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="00e36-145">Generate a WCF service contract and helper classes.</span></span> <span data-ttu-id="00e36-146">使用して、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または svcutil.exe を操作する SAP システムのアイテムを対象とした WCF サービス コントラクト (インターフェイス) を生成します。</span><span class="sxs-lookup"><span data-stu-id="00e36-146">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or svcutil.exe to generate a WCF service contract (interface) targeted at the SAP system artifacts with which you want to work.</span></span> <span data-ttu-id="00e36-147">WCF クライアントを生成する方法の詳細については、次を参照してください。 [WCF クライアントまたは SAP ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="00e36-147">For more information about how to generate a WCF client, see [Generate a WCF client or a WCF service contract for SAP solution artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span></span>  
  
2.  <span data-ttu-id="00e36-148">手順 1. で生成されたインターフェイスとヘルパー クラスからの WCF サービスを実装します。</span><span class="sxs-lookup"><span data-stu-id="00e36-148">Implement a WCF service from the interface and helper classes generated in step 1.</span></span> <span data-ttu-id="00e36-149">その操作を処理するメソッドがエラーを返す、SAP システムに例外をスローできます操作のデータの処理エラーが発生した場合それ以外の場合、メソッドは、操作を適切な応答が (生成) クラスのインスタンスを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="00e36-149">If an error is encountered processing the data for the operation, the method that handles that operation can throw an exception to return a fault to the SAP system; otherwise the method must return an instance of the appropriate (generated) response class for the operation.</span></span> <span data-ttu-id="00e36-150">次のように、WCF サービス クラスを属性する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00e36-150">You must attribute the WCF service class as follows:</span></span>  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    ```  
  
    1.  <span data-ttu-id="00e36-151">使用した場合、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]インターフェイスを生成するには、直接、適切なメソッドで、生成されたロジックを実装できる**SAPBindingService**クラスです。</span><span class="sxs-lookup"><span data-stu-id="00e36-151">If you used the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate the interface, you can implement your logic directly in the appropriate method in the generated **SAPBindingService** class.</span></span> <span data-ttu-id="00e36-152">このクラスは、SAPBindingService.cs で確認できます。</span><span class="sxs-lookup"><span data-stu-id="00e36-152">This class can be found in SAPBindingService.cs.</span></span> <span data-ttu-id="00e36-153">次のコードでサブ クラス、 **SAPBindingService**クラスです。</span><span class="sxs-lookup"><span data-stu-id="00e36-153">The following code sub-classes the **SAPBindingService** class.</span></span>  
  
        ```  
        [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single,UseSynchronizationContext = false)]  
        class RfcServerClass : SAPBindingNamespace.SAPBindingService  
        {  
            public override Z_RFC_MKD_ADDResponse Z_RFC_MKD_ADD(Z_RFC_MKD_ADDRequest request)  
            {  
                // If either parameter is null throw an exception   
                if (request.X == null || request.Y == null)  
                    throw new System.ArgumentNullException();  
  
                // Add the two operands  
                int result = (int) (request.X + request.Y);  
  
                return new Z_RFC_MKD_ADDResponse(result);  
            }  
        }  
        ```  
  
    2.  <span data-ttu-id="00e36-154">Svcutil.exe を使用して、インターフェイスを生成した場合は、インターフェイスを実装するクラスを作成し、このクラスの appropriatemethod で、ロジックを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00e36-154">If you used svcutil.exe to generate the interface, you must create a class that implements the interface and implement your logic in the appropriatemethod of this class.</span></span>  
  
3.  <span data-ttu-id="00e36-155">手順 2 で作成した WCF サービスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="00e36-155">Create an instance of the WCF service created in step 2.</span></span>  
  
    ```  
    // create service instance  
    RfcServerClass rfcServerInstance = new RfcServerClass();  
    ```  
  
4.  <span data-ttu-id="00e36-156">インスタンスを作成する**System.ServiceModel.ServiceHost** WCF サービスと基本接続 URI を使用しています。</span><span class="sxs-lookup"><span data-stu-id="00e36-156">Create an instance of **System.ServiceModel.ServiceHost** by using the WCF service and a base connection URI.</span></span> <span data-ttu-id="00e36-157">基本の接続 URI には、userinfoparams またはクエリ文字列を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="00e36-157">The base connection URI cannot contain userinfoparams or a query_string.</span></span>  
  
    ```  
    // Enable service host  
    Uri[] baseUri = new Uri[] { new Uri("sap://a/YourSAPHost/00") };  
    ServiceHost srvHost = new ServiceHost(pollingInstance, baseUri);  
    ```  
  
5.  <span data-ttu-id="00e36-158">作成、 **SAPBinding**し、バインドのプロパティを設定して、操作のように構成します。</span><span class="sxs-lookup"><span data-stu-id="00e36-158">Create an **SAPBinding** and configure it for the operation by setting its binding properties.</span></span> <span data-ttu-id="00e36-159">これは、コードで明示的にまたは構成で宣言によって行うことができます。</span><span class="sxs-lookup"><span data-stu-id="00e36-159">You can do this either explicitly in code or declaratively in configuration.</span></span> <span data-ttu-id="00e36-160">設定する必要がありますには、少なくとも**AcceptCredentialsInUri**に**true**です。</span><span class="sxs-lookup"><span data-stu-id="00e36-160">At a minimum, you must set **AcceptCredentialsInUri** to **true**.</span></span>  
  
    ```  
    // Create and configure a binding for the service endpoint. NOTE: binding  
    // parameters are set here for clarity, but these are already set in the  
    // the generated configuration file  
    SAPBinding binding = new SAPBinding();  
  
    // The credentials are included in the connection URI, so set this property to true  
    binding.AcceptCredentialsInUri = true;  
    ```  
  
6.  <span data-ttu-id="00e36-161">サービス ホストにサービス エンドポイントを追加します。</span><span class="sxs-lookup"><span data-stu-id="00e36-161">Add a service endpoint to the service host.</span></span> <span data-ttu-id="00e36-162">これを行うには :</span><span class="sxs-lookup"><span data-stu-id="00e36-162">To do this:</span></span>  
  
    -   <span data-ttu-id="00e36-163">手順 5. で作成したバインディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="00e36-163">Use the binding created in step 5.</span></span>  
  
    -   <span data-ttu-id="00e36-164">接続の資格情報が含まれており、リスナーの接続を指定する URI を指定して (SAP のゲートウェイ、ゲートウェイ サービスとプログラム ID)、query_string にします。</span><span class="sxs-lookup"><span data-stu-id="00e36-164">Specify a connection URI that contains credentials and specifies a listener connection (SAP gateway, gateway service and program ID) in the query_string.</span></span> <span data-ttu-id="00e36-165">SAP 接続 URI の詳細については、次を参照してください。 [SAP システム接続 URI を作成する](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="00e36-165">For more information about the SAP connection URI, see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
    -   <span data-ttu-id="00e36-166">サービス コントラクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="00e36-166">Specify the service contract.</span></span> <span data-ttu-id="00e36-167">これは、WCF サービス コントラクトを表すインターフェイスの名前です。</span><span class="sxs-lookup"><span data-stu-id="00e36-167">This is the name of the interface that represents the WCF service contract.</span></span> <span data-ttu-id="00e36-168">Rfc、"Rfc"です。</span><span class="sxs-lookup"><span data-stu-id="00e36-168">For RFCs, it is "Rfc".</span></span>  
  
    ```  
    // Add service endpoint   
    // NOTE: The contract for the service endpoint is "Rfc".  
    //       This is the generated WCF service contract (interface) -- see SAPBindingInterface.cs.  
    Uri serviceUri = new Uri("sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?ListenerGwServ=SAPGW00&ListenerGwHost=YourSapHost&ListenerProgramId=SAPAdapter");  
    srvHost.AddServiceEndpoint("Rfc", binding, serviceUri);  
    ```  
  
7.  <span data-ttu-id="00e36-169">SAP システムから、操作を受信するには、サービス ホストを開きます。</span><span class="sxs-lookup"><span data-stu-id="00e36-169">To receive the operation from the SAP system, open the service host.</span></span> <span data-ttu-id="00e36-170">SAP システムにプログラムの ID と手順 6. で、サービス URI で指定されたシステム上の操作が呼び出されるたびに、WCF サービスが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="00e36-170">Your WCF service will be invoked whenever the SAP system invokes the operation on the program ID and system specified in the service URI in step 6.</span></span>  
  
    ```  
    // Open the service host to begin receiving the operation.  
    srvHost.Open();  
    ```  
  
8.  <span data-ttu-id="00e36-171">操作の受信を停止するには、サービス ホストを閉じます。</span><span class="sxs-lookup"><span data-stu-id="00e36-171">To stop receiving the operation, close the service host.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="00e36-172">アダプターは、サービス ホストが閉じられるまで、操作を受信し続けます。</span><span class="sxs-lookup"><span data-stu-id="00e36-172">The adapter will continue to receive the operation until the service host is closed.</span></span> <span data-ttu-id="00e36-173">操作を受信する必要がなくなったときに常に、サービス ホストを閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="00e36-173">You should always close the service host when you no longer want to receive the operation.</span></span>  
  
    ```  
    srvHost.Close();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="00e36-174">参照</span><span class="sxs-lookup"><span data-stu-id="00e36-174">See Also</span></span>  
[<span data-ttu-id="00e36-175">WCF サービス モデルを使用して SAP アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="00e36-175">Develop SAP applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)