---
title: WCF サービス モデルを使用して Oracle E-business Suite での要求のセットを呼び出す |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb6ec551-c069-4133-add5-2ba83d20405d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec243c1d1ed1093241e4dc6120c3703fbf2e4542
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965184"
---
# <a name="invoke-request-sets-in-oracle-e-business-suite-using-the-wcf-service-model"></a><span data-ttu-id="68d46-102">WCF サービス モデルを使用して Oracle E-business Suite での要求のセットをを呼び出す</span><span class="sxs-lookup"><span data-stu-id="68d46-102">Invoke request sets in Oracle E-Business Suite using the WCF service model</span></span>
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]<span data-ttu-id="68d46-103">Oracle E-business Suite で要求のセットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="68d46-103"> enables you to execute request sets in Oracle E-Business Suite.</span></span> <span data-ttu-id="68d46-104">セットは、1 つまたは複数の段階的に分けられ、各ステージには、一連レポートと同時実行プログラムにはが含まれています。 を要求します。</span><span class="sxs-lookup"><span data-stu-id="68d46-104">Request sets are divided into one or more stages, and each stage contains a set of reports and concurrent programs.</span></span> <span data-ttu-id="68d46-105">アダプターが要求のセットをサポートする方法の詳細については、次を参照してください。[要求設定に対する操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md)です。</span><span class="sxs-lookup"><span data-stu-id="68d46-105">For more information about how the adapter supports request sets, see [Operations on Request Sets](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md).</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="68d46-106">WCF クライアント クラス</span><span class="sxs-lookup"><span data-stu-id="68d46-106">The WCF Client Class</span></span>  
 <span data-ttu-id="68d46-107">要求の呼び出し設定用に生成、WCF クライアントの名前、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]次の表に記載されています。</span><span class="sxs-lookup"><span data-stu-id="68d46-107">The name of the WCF client generated for invoking the request sets by the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is listed in the following table.</span></span>  
  
|<span data-ttu-id="68d46-108">成果物</span><span class="sxs-lookup"><span data-stu-id="68d46-108">Artifact</span></span>|<span data-ttu-id="68d46-109">WCF クライアント名</span><span class="sxs-lookup"><span data-stu-id="68d46-109">WCF Client Name</span></span>|  
|--------------|---------------------|  
|<span data-ttu-id="68d46-110">要求のセット</span><span class="sxs-lookup"><span data-stu-id="68d46-110">Request Set</span></span>|<span data-ttu-id="68d46-111">RequestSets_ [APP_NAME] クライアント</span><span class="sxs-lookup"><span data-stu-id="68d46-111">RequestSets_[APP_NAME]Client</span></span>|  
  
 <span data-ttu-id="68d46-112">[構成]、Oracle E-business Suite アプリケーションの実際の名前を =たとえば、SQLAP です。</span><span class="sxs-lookup"><span data-stu-id="68d46-112">[APP_NAME] = Actual name of the Oracle E-Business Suite application; for example, SQLAP.</span></span>  
  
### <a name="method-signature-for-invoking-request-sets"></a><span data-ttu-id="68d46-113">要求のセットを呼び出すためのメソッド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="68d46-113">Method Signature for Invoking Request Sets</span></span>  
 <span data-ttu-id="68d46-114">次の表は、要求のセットに対してメソッド署名を示します。</span><span class="sxs-lookup"><span data-stu-id="68d46-114">The following table shows the method signature for request sets.</span></span>  
  
|<span data-ttu-id="68d46-115">操作</span><span class="sxs-lookup"><span data-stu-id="68d46-115">Operation</span></span>|<span data-ttu-id="68d46-116">メソッド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="68d46-116">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="68d46-117">要求のセット</span><span class="sxs-lookup"><span data-stu-id="68d46-117">Request Set</span></span>|<span data-ttu-id="68d46-118">パブリック\<型を返す\>\<要求セット名\>(param 1、param 2、...)</span><span class="sxs-lookup"><span data-stu-id="68d46-118">public \<return type\> \<request set name\>(param 1, param 2, …)</span></span>|  
  
 <span data-ttu-id="68d46-119">たとえば、次のコードにはメソッド シグネチャに関するの WCF クライアント クラスを生成、 **reqset_singlestage**セットを要求します。</span><span class="sxs-lookup"><span data-stu-id="68d46-119">As an example, the following code shows the method signatures for a WCF client class generated for the **reqset_singlestage** request set.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="68d46-120">これにより、カスタム要求セットはあり、Oracle E-business ソリューション インスタンスで使用可能なことができない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="68d46-120">This is a custom request set and might not be available on your Oracle E-Business Solution instance.</span></span>  
  
```  
public partial class RequestSets_SQLAPClient : System.ServiceModel.ClientBase<RequestSets_SQLAP>, RequestSets_SQLAP{      
  
    public string REQSTG(  
      schemas.microsoft.com.OracleEBS._2008._05.Options.SetRelClassOptions SetRelClassOptions,  
      schemas.microsoft.com.OracleEBS._2008._05.Options.SetPrintOptions SetPrintOptions,   
      schemas.microsoft.com.OracleEBS._2008._05.Options.SetRepeatOptions SetRepeatOptions,   
      schemas.microsoft.com.OracleEBS._2008._05.Options.SetNlsOptions SetNlsOptions,  
      string StartTime,  
      schemas.microsoft.com.OracleEBS._2008._05.RequestSetStage.SQLAP.REQSTG.set1 set1_set1);  
}  
```  
  
 <span data-ttu-id="68d46-121">このスニペットで**RequestSets_SQLAPClient**によって生成された OracleEBSBindingClient.cs で WCF クラスの名前を指定します、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="68d46-121">In this snippet, **RequestSets_SQLAPClient** is the name of the WCF class in the OracleEBSBindingClient.cs generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="68d46-122">**REQSTG**要求セットに呼び出すメソッドの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="68d46-122">**REQSTG** is the name of the method to invoke the request set.</span></span>  
  
## <a name="creating-a-wcf-client-to-invoke-request-sets"></a><span data-ttu-id="68d46-123">要求セットを呼び出す、WCF クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="68d46-123">Creating a WCF Client to Invoke Request Sets</span></span>  
 <span data-ttu-id="68d46-124">WCF クライアントを使用して Oracle E-business Suite で操作の実行に必要なアクションの汎用的なセットは、一連のタスクで説明されている[Oracle E-business Suite アダプターで WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="68d46-124">The generic set of actions required to perform an operation on Oracle E-Business Suite using a WCF client involves a set of tasks described in [Overview of the WCF service model with the Oracle E-Business Suite adapter](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md).</span></span> <span data-ttu-id="68d46-125">このセクションを呼び出すための WCF クライアントを作成する方法について説明、 **reqset_singlestage**セットを要求します。</span><span class="sxs-lookup"><span data-stu-id="68d46-125">This section describes how to create a WCF client to invoke the **reqset_singlestage** request set.</span></span>  
  
#### <a name="to-create-a-wcf-client"></a><span data-ttu-id="68d46-126">WCF クライアントを作成するには</span><span class="sxs-lookup"><span data-stu-id="68d46-126">To create a WCF client</span></span>  
  
1.  <span data-ttu-id="68d46-127">Visual Studio で Visual c# プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="68d46-127">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="68d46-128">このトピックでは、コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="68d46-128">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="68d46-129">WCF クライアント クラスを生成、 **reqset_singlestage**セットを要求します。</span><span class="sxs-lookup"><span data-stu-id="68d46-129">Generate the WCF client class for the **reqset_singlestage** request set.</span></span> <span data-ttu-id="68d46-130">詳細については、WCF クライアント クラスを生成する、次を参照してください。 [WCF クライアントまたは Oracle E-business Suite ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="68d46-130">For more information about generating a WCF client class, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="68d46-131">WCF クライアント クラスを生成する前に必ず設定してください、 **EnableBizTalkCompatibilityMode**プロパティを false にバインドします。</span><span class="sxs-lookup"><span data-stu-id="68d46-131">Before generating the WCF client class, make sure you set the **EnableBizTalkCompatibilityMode** binding property to false.</span></span>  
  
3.  <span data-ttu-id="68d46-132">ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.OracleEBS`と`Microsoft.ServiceModel.Channels`です。</span><span class="sxs-lookup"><span data-stu-id="68d46-132">In the Solution Explorer, add reference to `Microsoft.Adapters.OracleEBS` and `Microsoft.ServiceModel.Channels`.</span></span>  
  
4.  <span data-ttu-id="68d46-133">Program.cs ファイルを開き、次の名前空間を追加します。</span><span class="sxs-lookup"><span data-stu-id="68d46-133">Open the Program.cs file and add the following namespaces:</span></span>  
  
    -   `Microsoft.Adapters.OracleEBS`  
  
    -   `System.ServiceModel`  
  
5.  <span data-ttu-id="68d46-134">Program.cs ファイルを開き、次のスニペットの説明に従って、クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="68d46-134">Open the Program.cs file and create a client as described in the snippet below.</span></span>  
  
    ```  
    OracleEBSBinding binding = new OracleEBSBinding();  
    EndpointAddress address = new EndpointAddress("oracleebs://ebs_instance_name");  
    RequestSets_SQLAPClient client = new RequestSets_SQLAPClient(binding, address);  
    ```  
  
     <span data-ttu-id="68d46-135">このスニペットで`RequestSets_SQLAPClient`OracleEBSBindingClient.cs で定義された WCF クライアントです。</span><span class="sxs-lookup"><span data-stu-id="68d46-135">In this snippet, `RequestSets_SQLAPClient` is the WCF client defined in OracleEBSBindingClient.cs.</span></span> <span data-ttu-id="68d46-136">このファイルにより生成されて、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="68d46-136">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="68d46-137">このスニペットでは、アプリケーション コードで明示的にバインドとエンドポイント アドレスを指定するだけです。</span><span class="sxs-lookup"><span data-stu-id="68d46-137">In this snippet, you explicitly specify the binding and endpoint address in your application code.</span></span> <span data-ttu-id="68d46-138">アプリケーション構成ファイルから、app.config、によって生成されるも、これらの値を使用することも、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="68d46-138">You can also use these values from the application configuration file, app.config, also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="68d46-139">クライアント バインディングを指定するさまざまな方法の詳細については、次を参照してください。 [for Oracle E-business Suite バインド クライアントを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)です。</span><span class="sxs-lookup"><span data-stu-id="68d46-139">For more information about the different ways of specifying client binding, see [Configure a client binding for the Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md).</span></span>  
  
6.  <span data-ttu-id="68d46-140">クライアントの資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="68d46-140">Set the credentials for the client.</span></span>  
  
    ```  
    client.ClientCredentials.UserName.UserName = "myuser";  
    client.ClientCredentials.UserName.Password = "mypassword";  
    ```  
  
7.  <span data-ttu-id="68d46-141">Oracle E-business Suite アプリケーションで要求のセットを起動するため、アプリケーションのコンテキストを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68d46-141">Because you are invoking request sets in an Oracle E-Business Suite application, you must set the application context.</span></span> <span data-ttu-id="68d46-142">この例では、アプリケーションのコンテキストを設定するを指定する、 **OracleUserName**、 **OraclePassword**、および**OracleEBSResponsibilityName**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="68d46-142">In this example, to set the application context, you specify the **OracleUserName**, **OraclePassword**, and **OracleEBSResponsibilityName** binding properties.</span></span> <span data-ttu-id="68d46-143">アプリケーション コンテキストの詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。</span><span class="sxs-lookup"><span data-stu-id="68d46-143">For more information about application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
    ```  
    binding.OracleUserName = "myOracleEBSUserName";  
    binding.OraclePassword = "myOracleEBSPassword";  
    binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
    ```  
  
8.  <span data-ttu-id="68d46-144">次のスニペット」の説明に従って、クライアントを開きます。</span><span class="sxs-lookup"><span data-stu-id="68d46-144">Open the client as described in the snippet below:</span></span>  
  
    ```  
    try  
    {  
       Console.WriteLine("Opening Client...");  
       client.Open();  
    }  
    catch (Exception ex)  
    {  
       Console.WriteLine("Exception: " + ex.Message);  
       throw;  
    }  
    ```  
  
9. <span data-ttu-id="68d46-145">呼び出す、 **reqset_singlestage**セットを要求します。</span><span class="sxs-lookup"><span data-stu-id="68d46-145">Invoke the **reqset_singlestage** request set.</span></span>  
  
    ```  
    string RequestID;  
  
    schemas.microsoft.com.OracleEBS._2008._05.RequestSetStage.SQLAP.REQSTG.set1 param =  
        new schemas.microsoft.com.OracleEBS._2008._05.RequestSetStage.SQLAP.REQSTG.set1();  
  
    param.INSPARAMPROG = new schemas.microsoft.com.OracleEBS._2008._05.RequestSetConcurrentProgram.SQLAP.REQSTG.set1.SQLAP1.INSPARAMPROG();  
    param.INSPARAMPROG.p_id = "123";  
    param.INSPARAMPROG.p_name = "MyName";  
  
    try  
    {  
        Console.WriteLine("Invoking the reqset_singlestage request set");  
        RequestID = client.REQSTG(null, null, null, null, null, param);  
        Console.WriteLine("The request ID generated for the request set is : " + RequestID);  
        Console.WriteLine("*****************************************************************");  
        Console.WriteLine("\nHit <RETURN> to end");  
        Console.ReadLine();  
    }  
    catch (Exception ex)  
    {  
        Console.WriteLine("Exception : " + ex);  
        throw;  
    }  
    ```  
  
10. <span data-ttu-id="68d46-146">次のスニペット」の説明に従って、クライアントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="68d46-146">Close the client as described in the snippet below:</span></span>  
  
    ```  
    client.Close();  
    ```  
  
11. <span data-ttu-id="68d46-147">プロジェクトをビルドし、それを実行します。</span><span class="sxs-lookup"><span data-stu-id="68d46-147">Build the project and then run it.</span></span> <span data-ttu-id="68d46-148">アプリケーションを起動、 **reqset_singlestage**要求が設定され、コンソールに書き込まれますが、要求の ID を返します。</span><span class="sxs-lookup"><span data-stu-id="68d46-148">The application invokes the **reqset_singlestage** request set and returns a request ID, which is written to the console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68d46-149">参照</span><span class="sxs-lookup"><span data-stu-id="68d46-149">See Also</span></span>  
 [<span data-ttu-id="68d46-150">WCF サービス モデルを使用して Oracle E-business Suite アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="68d46-150">Develop Oracle E-Business Suite applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)