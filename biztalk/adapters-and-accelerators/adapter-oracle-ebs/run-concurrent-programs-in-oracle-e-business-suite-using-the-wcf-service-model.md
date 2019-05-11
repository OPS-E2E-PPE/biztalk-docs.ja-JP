---
title: WCF サービス モデルを使用して Oracle E-business Suite での同時実行プログラムを呼び出す |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e227c60f-f6fe-40bf-bf41-2784a4428ad0
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2265c1509a89dca7ead1b124267182bcaaa7fa0e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374656"
---
# <a name="invoke-concurrent-programs-in-oracle-e-business-suite-using-the-wcf-service-model"></a><span data-ttu-id="aa612-102">WCF サービス モデルを使用して Oracle E-business Suite での同時実行プログラムを起動します。</span><span class="sxs-lookup"><span data-stu-id="aa612-102">Invoke concurrent programs in Oracle E-Business Suite using the WCF service model</span></span>
<span data-ttu-id="aa612-103">Oracle E-business Suite では、Oracle のアプリケーションで特定の操作を実行する実行可能な同時実行プログラムを公開します。</span><span class="sxs-lookup"><span data-stu-id="aa612-103">Oracle E-Business Suite exposes concurrent programs that you can execute to perform specific operations on Oracle applications.</span></span> <span data-ttu-id="aa612-104">各 Oracle アプリケーションでは、標準の同時実行プログラム (つまり同じすべての操作では) と Oracle アプリケーションに固有の特定の同時実行プログラムのセットがあります。</span><span class="sxs-lookup"><span data-stu-id="aa612-104">Each Oracle application has a set of standard concurrent programs (that are same across all operations) and certain concurrent programs that are specific to an Oracle application.</span></span> <span data-ttu-id="aa612-105">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アダプター クライアントが呼び出すことができる操作としてすべての同時実行プログラムを公開します。</span><span class="sxs-lookup"><span data-stu-id="aa612-105">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] exposes all concurrent programs as operations that adapter clients can invoke.</span></span> <span data-ttu-id="aa612-106">アダプターが同時実行プログラムをサポートする方法の詳細については、次を参照してください。[同時実行プログラムに対する操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md)します。</span><span class="sxs-lookup"><span data-stu-id="aa612-106">For more information about how the adapter supports concurrent programs, see [Operations on Concurrent Programs](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aa612-107">そのメタデータを公開しない同時実行プログラム、については、Oracle E-business アダプターは、これらの同時実行プログラムごとに 100 の省略可能なパラメーターを公開します。</span><span class="sxs-lookup"><span data-stu-id="aa612-107">For the concurrent programs that do not expose their metadata, the Oracle E-Business adapter exposes 100 optional parameters for each of these concurrent programs.</span></span> <span data-ttu-id="aa612-108">これらの同時実行プログラムを正常に呼び出すは、ユーザーは、値を必要とする同時実行プログラムのパラメーターを把握する Oracle E-business Suite のドキュメントを参照して、それらを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa612-108">To invoke these concurrent programs successfully, the user must consult the Oracle E-Business Suite documentation to figure out the parameters for a concurrent program that require a value, and then specify them.</span></span> <span data-ttu-id="aa612-109">このような同時実行プログラムの例は、 **Journal インポート**(実際の名前。**GLLEZL**) で、**総勘定元帳**アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="aa612-109">An example of such a concurrent program is **Journal Import** (actual name: **GLLEZL**) in the **General Ledger** application.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="aa612-110">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="aa612-110">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="aa612-111">このトピックの例では、起動、 **MS_SAMPLE_COPY_EMP_DATA**後に、同時実行プログラム、 **Get_Status**同時実行プログラム、最初の同時実行プログラムの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="aa612-111">The example in this topic invokes the **MS_SAMPLE_COPY_EMP_DATA** concurrent program, followed by the **Get_Status** concurrent program to know the status of the first concurrent program.</span></span> <span data-ttu-id="aa612-112">これらの同時実行プログラムがから呼び出される、**アプリケーション オブジェクト ライブラリ**アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="aa612-112">These concurrent programs are invoked from the **Application Object Library** application.</span></span> <span data-ttu-id="aa612-113">**MS_SAMPLE_COPY_EMP_DATA**サンプルに付属のスクリプトを実行して作成されます。</span><span class="sxs-lookup"><span data-stu-id="aa612-113">The **MS_SAMPLE_COPY_EMP_DATA** is created by running the script provided with the samples.</span></span> <span data-ttu-id="aa612-114">サンプルの詳細については、次を参照してください。 [Oracle EBS アダプター用のサンプル](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="aa612-114">For more information about samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="aa612-115">サンプルについては、 **ConcurrentProgram_ServiceModel**、これは、このトピックに基づいてがで提供されていることも、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="aa612-115">A sample, **ConcurrentProgram_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="aa612-116">WCF クライアント クラス</span><span class="sxs-lookup"><span data-stu-id="aa612-116">The WCF Client Class</span></span>  
 <span data-ttu-id="aa612-117">同時実行プログラムを起動するために生成された WCF クライアントの名前、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]次の表に記載されています。</span><span class="sxs-lookup"><span data-stu-id="aa612-117">The name of the WCF client generated for invoking the concurrent programs by the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is listed in the following table.</span></span>  
  
|<span data-ttu-id="aa612-118">成果物</span><span class="sxs-lookup"><span data-stu-id="aa612-118">Artifact</span></span>|<span data-ttu-id="aa612-119">WCF クライアント名</span><span class="sxs-lookup"><span data-stu-id="aa612-119">WCF Client Name</span></span>|  
|--------------|---------------------|  
|<span data-ttu-id="aa612-120">同時実行プログラム</span><span class="sxs-lookup"><span data-stu-id="aa612-120">Concurrent Program</span></span>|<span data-ttu-id="aa612-121">[APP_NAME] ConcurrentPrograms_ クライアント</span><span class="sxs-lookup"><span data-stu-id="aa612-121">ConcurrentPrograms_[APP_NAME]Client</span></span>|  
  
 <span data-ttu-id="aa612-122">[構成] は、Oracle E-business Suite のアプリケーションの実際の名前を =たとえば、ヘルプです。</span><span class="sxs-lookup"><span data-stu-id="aa612-122">[APP_NAME] = Actual name of the Oracle E-Business Suite application; for example, FND.</span></span>  
  
### <a name="method-signature-for-invoking-concurrent-programs"></a><span data-ttu-id="aa612-123">同時実行プログラムを呼び出すためのメソッド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="aa612-123">Method Signature for Invoking Concurrent Programs</span></span>  
 <span data-ttu-id="aa612-124">次の表では、同時実行プログラムにメソッド シグネチャを示します。</span><span class="sxs-lookup"><span data-stu-id="aa612-124">The following table shows the method signature for the concurrent programs.</span></span>  
  
|<span data-ttu-id="aa612-125">演算</span><span class="sxs-lookup"><span data-stu-id="aa612-125">Operation</span></span>|<span data-ttu-id="aa612-126">メソッド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="aa612-126">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="aa612-127">同時実行プログラム</span><span class="sxs-lookup"><span data-stu-id="aa612-127">Concurrent program</span></span>|<span data-ttu-id="aa612-128">パブリック\<型を返す\>< Concurrent_program_name > (param 1、param 2、...)</span><span class="sxs-lookup"><span data-stu-id="aa612-128">public \<return type\> <Concurrent_program_name>(param 1, param 2, …)</span></span>|  
  
 <span data-ttu-id="aa612-129">WCF クライアント クラスを生成の例として、次のコードがメソッド シグネチャを示します、 **MS_SAMPLE_COPY_EMP_DATA**と**Get_Status**同時実行プログラム。</span><span class="sxs-lookup"><span data-stu-id="aa612-129">As an example, the following code shows the method signatures for a WCF client class generated for the **MS_SAMPLE_COPY_EMP_DATA** and **Get_Status** concurrent programs.</span></span>  
  
```  
public partial class ConcurrentPrograms_FNDClient : System.ServiceModel.ClientBase<ConcurrentPrograms_FND>, ConcurrentPrograms_FND {      
  
    public string MS_SAMPLE_COPY_EMP_DATA(schemas.microsoft.com.OracleEBS._2008._05.Options.SetOptions SetOptions,  
      schemas.microsoft.com.OracleEBS._2008._05.Options.SetPrintOptions SetPrintOptions,  
      schemas.microsoft.com.OracleEBS._2008._05.Options.SetRepeatOptions SetRepeatOptions,  
      string Description, string StartTime);  
  
    public bool GetStatusForConcurrentProgram(string RequestId, out string Phase, out string Status,  
      out string DevPhase, out string DevStatus, out string Message);  
}  
```  
  
 <span data-ttu-id="aa612-130">このスニペットで**ConcurrentPrograms_FNDClient**によって生成された OracleEBSBindingClient.cs で WCF クラスの名前を指定します、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="aa612-130">In this snippet, **ConcurrentPrograms_FNDClient** is the name of the WCF class in the OracleEBSBindingClient.cs generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="aa612-131">**MS_SAMPLE_COPY_EMP_DATA**同時実行プログラムを呼び出すメソッドの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="aa612-131">**MS_SAMPLE_COPY_EMP_DATA** is the name of the method to invoke the concurrent program.</span></span> <span data-ttu-id="aa612-132">**GetStatusForConcurrentProgram**最初の同時実行プログラムの状態を取得する同時実行プログラムを呼び出すメソッドの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="aa612-132">**GetStatusForConcurrentProgram** is the name of the method to invoke the concurrent program to get the status of the first concurrent program.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aa612-133">**GetStatusForConcurrentProgram**の実際の名前を指定、 **Get_Status**同時実行プログラム。</span><span class="sxs-lookup"><span data-stu-id="aa612-133">**GetStatusForConcurrentProgram** is the actual name of the **Get_Status** concurrent program.</span></span>  
  
## <a name="creating-a-wcf-client-to-invoke-concurrent-programs"></a><span data-ttu-id="aa612-134">同時実行プログラムを呼び出す、WCF クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="aa612-134">Creating a WCF Client to Invoke Concurrent Programs</span></span>  
 <span data-ttu-id="aa612-135">汎用的な一連の WCF クライアントを使用して Oracle E-business Suite での操作を実行するために必要なアクションは、一連のタスクで説明されている[Oracle E-business Suite アダプターで WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="aa612-135">The generic set of actions required to perform an operation on Oracle E-Business Suite using a WCF client involves a set of tasks described in [Overview of the WCF service model with the Oracle E-Business Suite adapter](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md).</span></span> <span data-ttu-id="aa612-136">このセクションを呼び出す、WCF クライアントを作成する方法を説明します、 **MS_SAMPLE_COPY_EMP_DATA**と**Get_Status**同時実行プログラム。</span><span class="sxs-lookup"><span data-stu-id="aa612-136">This section describes how to create a WCF client to invoke the **MS_SAMPLE_COPY_EMP_DATA** and **Get_Status** concurrent programs.</span></span>  
  
#### <a name="to-create-a-wcf-client"></a><span data-ttu-id="aa612-137">WCF クライアントを作成するには</span><span class="sxs-lookup"><span data-stu-id="aa612-137">To create a WCF client</span></span>  
  
1. <span data-ttu-id="aa612-138">Visual Studio で Visual c# プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="aa612-138">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="aa612-139">このトピックでは、コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="aa612-139">For this topic, create a console application.</span></span>  
  
2. <span data-ttu-id="aa612-140">WCF クライアント クラスを生成、 **MS_SAMPLE_COPY_EMP_DATA**と**Get_Status**同時実行プログラム。</span><span class="sxs-lookup"><span data-stu-id="aa612-140">Generate the WCF client class for the **MS_SAMPLE_COPY_EMP_DATA** and **Get_Status** concurrent programs.</span></span> <span data-ttu-id="aa612-141">WCF クライアント クラスを生成する詳細については、次を参照してください。 [WCF クライアントまたは Oracle E-business Suite ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)します。</span><span class="sxs-lookup"><span data-stu-id="aa612-141">For more information about generating a WCF client class, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="aa612-142">WCF クライアント クラスを生成する前に必ず設定して、 **EnableBizTalkCompatibilityMode**プロパティを false にバインドします。</span><span class="sxs-lookup"><span data-stu-id="aa612-142">Before generating the WCF client class, make sure you set the **EnableBizTalkCompatibilityMode** binding property to false.</span></span>  
  
3. <span data-ttu-id="aa612-143">ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.OracleEBS`と`Microsoft.ServiceModel.Channels`します。</span><span class="sxs-lookup"><span data-stu-id="aa612-143">In the Solution Explorer, add reference to `Microsoft.Adapters.OracleEBS` and `Microsoft.ServiceModel.Channels`.</span></span>  
  
4. <span data-ttu-id="aa612-144">Program.cs ファイルを開き、次の名前空間を追加します。</span><span class="sxs-lookup"><span data-stu-id="aa612-144">Open the Program.cs file and add the following namespaces:</span></span>  
  
   -   `Microsoft.Adapters.OracleEBS`  
  
   -   `System.ServiceModel`  
  
5. <span data-ttu-id="aa612-145">Program.cs ファイルを開き、次のスニペットの説明に従って、クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="aa612-145">Open the Program.cs file and create a client as described in the snippet below.</span></span>  
  
   ```  
   OracleEBSBinding binding = new OracleEBSBinding();  
   EndpointAddress address = new EndpointAddress("oracleebs://ebs_instance_name");  
   ConcurrentPrograms_FNDClient client = new ConcurrentPrograms_FNDClient(binding, address);  
   ```  
  
    <span data-ttu-id="aa612-146">このスニペットで`ConcurrentPrograms_FNDClient`OracleEBSBindingClient.cs で定義されている WCF クライアントです。</span><span class="sxs-lookup"><span data-stu-id="aa612-146">In this snippet, `ConcurrentPrograms_FNDClient` is the WCF client defined in OracleEBSBindingClient.cs.</span></span> <span data-ttu-id="aa612-147">このファイルがによって生成された、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="aa612-147">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="aa612-148">このスニペットでは、アプリケーション コードで明示的にバインディングとエンドポイント アドレスを指定するだけ。</span><span class="sxs-lookup"><span data-stu-id="aa612-148">In this snippet, you explicitly specify the binding and endpoint address in your application code.</span></span> <span data-ttu-id="aa612-149">アプリケーション構成ファイルから、app.config、によって生成されることも、これらの値を使用することも、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="aa612-149">You can also use these values from the application configuration file, app.config, also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="aa612-150">クライアント バインディングを指定する、さまざまな方法の詳細については、次を参照してください。 [Oracle E-business suite バインド クライアントを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)します。</span><span class="sxs-lookup"><span data-stu-id="aa612-150">For more information on the different ways of specifying client binding, see [Configure a client binding for the Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md).</span></span>  
  
6. <span data-ttu-id="aa612-151">クライアントの資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="aa612-151">Set the credentials for the client.</span></span>  
  
   ```  
   client.ClientCredentials.UserName.UserName = "myuser";  
   client.ClientCredentials.UserName.Password = "mypassword";  
   ```  
  
7. <span data-ttu-id="aa612-152">Oracle E-business Suite アプリケーションで同時実行プログラムを起動するため、アプリケーションのコンテキストを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa612-152">Because you are invoking concurrent programs in an Oracle E-Business Suite application, you must set the application context.</span></span> <span data-ttu-id="aa612-153">この例で、アプリケーションのコンテキストの設定を指定する、 **OracleUserName**、 **OraclePassword**、および**OracleEBSResponsibilityName**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="aa612-153">In this example, to set the application context, you specify the **OracleUserName**, **OraclePassword**, and **OracleEBSResponsibilityName** binding properties.</span></span> <span data-ttu-id="aa612-154">アプリケーションのコンテキストの詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)します。</span><span class="sxs-lookup"><span data-stu-id="aa612-154">For more information about application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
   ```  
   binding.OracleUserName = "myOracleEBSUserName";  
   binding.OraclePassword = "myOracleEBSPassword";  
   binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
   ```  
  
8. <span data-ttu-id="aa612-155">次のスニペットで説明されているように、クライアントを開きます。</span><span class="sxs-lookup"><span data-stu-id="aa612-155">Open the client as described in the snippet below:</span></span>  
  
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
  
9. <span data-ttu-id="aa612-156">呼び出す、 **MS_SAMPLE_COPY_EMP_DATA**と**Get_Status**同時実行プログラム。</span><span class="sxs-lookup"><span data-stu-id="aa612-156">Invoke the **MS_SAMPLE_COPY_EMP_DATA** and **Get_Status** concurrent programs.</span></span>  
  
    ```  
    string RequestID;  
    bool Result;  
    string Phase;  
    string Status;  
    string DevPhase;  
    string DevStatus;  
    string Message;  
  
    try  
    {  
        Console.WriteLine("Invoking the MS_SAMPLE_COPY_EMP_DATA concurrent program");  
        RequestID = client.MS_SAMPLE_COPY_EMP_DATA(null, null, null, null, null);  
        Console.WriteLine("The request ID generated for the concurrent program is : " + RequestID);  
        Console.WriteLine("********************************************************");  
        Console.WriteLine("\nWaiting for 60 seconds for the concurrent program to be complete");  
        System.Threading.Thread.Sleep(60000);  
        Console.WriteLine("\nInvoking the Get_Status concurrent program");  
        Result = client.GetStatusForConcurrentProgram(RequestID, out Phase, out Status, out DevPhase, out DevStatus, out Message);  
        Console.WriteLine("\nResult is  : " + Result);  
        Console.WriteLine("Phase is     : " + Phase);  
        Console.WriteLine("Status is    : " + Status);  
        Console.WriteLine("DevPhase is  : " + DevPhase);  
        Console.WriteLine("DevStatus is : " + DevStatus);  
        Console.WriteLine("Message is   : " + Message);  
        Console.WriteLine("********************************************************");  
        Console.WriteLine("\nHit <RETURN> to end");  
        Console.ReadLine();  
    }  
    catch (Exception ex)  
    {  
        Console.WriteLine("Exception : " + ex);  
        throw;                 
    }  
    ```  
  
10. <span data-ttu-id="aa612-157">次のスニペットの説明に従って、クライアントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="aa612-157">Close the client as described in the snippet below:</span></span>  
  
    ```  
    client.Close();  
    ```  
  
11. <span data-ttu-id="aa612-158">プロジェクトをビルドし、それを実行します。</span><span class="sxs-lookup"><span data-stu-id="aa612-158">Build the project and then run it.</span></span> <span data-ttu-id="aa612-159">アプリケーションの起動、 **MS_SAMPLE_COPY_EMP_DATA**と要求 ID を返します。</span><span class="sxs-lookup"><span data-stu-id="aa612-159">The application invokes the **MS_SAMPLE_COPY_EMP_DATA** and returns a request ID.</span></span> <span data-ttu-id="aa612-160">渡されたし、ID、 **Get_Status**同時実行プログラムの状態が最後に提供する、 **MS_SAMPLE_COPY_EMP_DATA**列プログラム。</span><span class="sxs-lookup"><span data-stu-id="aa612-160">The ID is then passed to the **Get_Status** concurrent program, which finally provides the status of the **MS_SAMPLE_COPY_EMP_DATA** column program.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa612-161">参照</span><span class="sxs-lookup"><span data-stu-id="aa612-161">See Also</span></span>  
 [<span data-ttu-id="aa612-162">WCF サービス モデルを使用して Oracle E-business Suite のアプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="aa612-162">Develop Oracle E-Business Suite applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)