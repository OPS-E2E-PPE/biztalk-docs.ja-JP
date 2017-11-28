---
title: "WCF サービス モデルを使用して Oracle E-business Suite で ExecuteReader、ExecuteScalar、ExecuteNonQuery 操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54c42db1-9a4d-4003-af69-f75ff48b575a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eaffcdc59cd6093feababc8319c1f9f1964a0d05
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="executereader-executescalar-or-executenonquery-operations-in-oracle-e-business-suite-using-the-wcf-service-model"></a><span data-ttu-id="2cca6-102">WCF サービス モデルを使用して Oracle E-business Suite で ExecuteReader、ExecuteScalar、ExecuteNonQuery 操作</span><span class="sxs-lookup"><span data-stu-id="2cca6-102">ExecuteReader, ExecuteScalar, or ExecuteNonQuery operations in Oracle E-Business Suite using the WCF service model</span></span>
<span data-ttu-id="2cca6-103">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]などの一般的な操作を公開する**ExecuteNonQuery**、 **ExecuteReader**、および**ExecuteScalar**です。</span><span class="sxs-lookup"><span data-stu-id="2cca6-103">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] exposes generic operations such as **ExecuteNonQuery**, **ExecuteReader**, and **ExecuteScalar**.</span></span> <span data-ttu-id="2cca6-104">これらの操作を使用して、Oracle E-business Suite で任意のステートメントを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="2cca6-104">You can use these operations to execute any statement on Oracle E-Business Suite.</span></span> <span data-ttu-id="2cca6-105">これらの操作は、ステートメントの取得応答の種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="2cca6-105">These operations differ based on the kind of response you get for the statement.</span></span> <span data-ttu-id="2cca6-106">アダプターがこれらの操作をサポートする方法の詳細については、次を参照してください。 [ExecuteNonQuery、ExecuteReader、および ExecuteScalar 操作のサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)です。</span><span class="sxs-lookup"><span data-stu-id="2cca6-106">For more information about how the adapter supports these operations, see [Support for ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md).</span></span>  
  
 <span data-ttu-id="2cca6-107">このトピックは、実行する方法を示します、 **ExecuteReader**操作を使用して、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] WCF サービス モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="2cca6-107">This topic demonstrates how to perform an **ExecuteReader** operation using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] using the WCF service model.</span></span> <span data-ttu-id="2cca6-108">実行するには、このトピックで説明する手順の同じセットを行うことができる**ExecuteNonQuery**と**ExecuteScalar**操作します。</span><span class="sxs-lookup"><span data-stu-id="2cca6-108">You can follow the same set of procedures described in this topic to perform **ExecuteNonQuery** and **ExecuteScalar** operations.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="2cca6-109">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="2cca6-109">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="2cca6-110">このトピックの例を実行、 **ExecuteReader** MS_SAMPLE_EMPLOYEE インターフェイス テーブルでの選択操作を実行する操作。</span><span class="sxs-lookup"><span data-stu-id="2cca6-110">The example in this topic performs an **ExecuteReader** operation to perform a SELECT operation on the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="2cca6-111">サンプルに用意されているスクリプトを実行して、テーブルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="2cca6-111">The table is created by running the script provided with the samples.</span></span> <span data-ttu-id="2cca6-112">サンプルの詳細については、次を参照してください。 [Oracle EBS アダプター用のサンプル](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="2cca6-112">For more information about samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="2cca6-113">サンプルは、 **ExecuteReader**、これは、このトピックの内容に基づいても付属、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サンプルです。</span><span class="sxs-lookup"><span data-stu-id="2cca6-113">A sample, **ExecuteReader**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="2cca6-114">WCF クライアント クラス</span><span class="sxs-lookup"><span data-stu-id="2cca6-114">The WCF Client Class</span></span>  
 <span data-ttu-id="2cca6-115">呼び出すに一般的な操作 (ExecuteNonQuery、ExecuteReader、または ExecuteScalar) を使用して生成された WCF クライアントの名前、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]次の表に記載されています。</span><span class="sxs-lookup"><span data-stu-id="2cca6-115">The name of the WCF client generated for invoking generic operations (ExecuteNonQuery, ExecuteReader, or ExecuteScalar) using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is listed in the following table.</span></span>  
  
|<span data-ttu-id="2cca6-116">操作</span><span class="sxs-lookup"><span data-stu-id="2cca6-116">Operations</span></span>|<span data-ttu-id="2cca6-117">WCF クライアント名</span><span class="sxs-lookup"><span data-stu-id="2cca6-117">WCF Client Name</span></span>|  
|----------------|---------------------|  
|<span data-ttu-id="2cca6-118">ExecuteNonQuery、ExecuteReader、または ExecuteScalar</span><span class="sxs-lookup"><span data-stu-id="2cca6-118">ExecuteNonQuery, ExecuteReader, or ExecuteScalar</span></span>|<span data-ttu-id="2cca6-119">GenericOperation_Client</span><span class="sxs-lookup"><span data-stu-id="2cca6-119">GenericOperation_Client</span></span>|  
  
### <a name="method-signature-for-invoking-generic-operations"></a><span data-ttu-id="2cca6-120">一般的な操作を呼び出すためのメソッド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="2cca6-120">Method Signature for Invoking Generic Operations</span></span>  
 <span data-ttu-id="2cca6-121">次の表は、汎用的な操作の呼び出しに公開されるメソッドのシグネチャを示します。</span><span class="sxs-lookup"><span data-stu-id="2cca6-121">The following table shows the signature for the method exposed to invoke the generic operations.</span></span>  
  
|<span data-ttu-id="2cca6-122">操作</span><span class="sxs-lookup"><span data-stu-id="2cca6-122">Operation</span></span>|<span data-ttu-id="2cca6-123">メソッド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="2cca6-123">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="2cca6-124">ExecuteNonQuery</span><span class="sxs-lookup"><span data-stu-id="2cca6-124">ExecuteNonQuery</span></span>|<span data-ttu-id="2cca6-125">int ExecuteNonQuery (string、string[] OutputRefCursorNames、System.Data.DataSet:operator[] OutputRefCursors アウト クエリ)</span><span class="sxs-lookup"><span data-stu-id="2cca6-125">int ExecuteNonQuery(string Query, string[] OutputRefCursorNames, out System.Data.DataSet[] OutputRefCursors)</span></span>|  
|<span data-ttu-id="2cca6-126">ExecuteReader</span><span class="sxs-lookup"><span data-stu-id="2cca6-126">ExecuteReader</span></span>|<span data-ttu-id="2cca6-127">System.Data.DataSet ExecuteReader(string Query)</span><span class="sxs-lookup"><span data-stu-id="2cca6-127">System.Data.DataSet ExecuteReader(string Query)</span></span>|  
|<span data-ttu-id="2cca6-128">ExecuteScalar</span><span class="sxs-lookup"><span data-stu-id="2cca6-128">ExecuteScalar</span></span>|<span data-ttu-id="2cca6-129">文字列 ExecuteScalar(string Query)</span><span class="sxs-lookup"><span data-stu-id="2cca6-129">string ExecuteScalar(string Query)</span></span>|  
  
 <span data-ttu-id="2cca6-130">例として、汎用操作メソッドのシグネチャは次のコード スニペットに示します。</span><span class="sxs-lookup"><span data-stu-id="2cca6-130">As an example, the signature for the generic operation methods is shown in the following code snippet.</span></span>  
  
```  
public partial class GenericOperation_Client : System.ServiceModel.ClientBase<GenericOperation_>, GenericOperation_ {  
  public int ExecuteNonQuery(string Query, string[] OutputRefCursorNames, out System.Data.DataSet[] OutputRefCursors);  
  public System.Data.DataSet ExecuteReader(string Query);  
  public string ExecuteScalar(string Query);  
}  
```  
  
 <span data-ttu-id="2cca6-131">このコードで</span><span class="sxs-lookup"><span data-stu-id="2cca6-131">In this snippet,</span></span>  
  
-   <span data-ttu-id="2cca6-132">`GenericOperation_Client`クラスの名前です。</span><span class="sxs-lookup"><span data-stu-id="2cca6-132">`GenericOperation_Client` is the name of the class.</span></span> <span data-ttu-id="2cca6-133">このクラスは、汎用の操作では、ExecuteReader を呼び出すクライアントを作成する使用されます。</span><span class="sxs-lookup"><span data-stu-id="2cca6-133">This class is used to create a client to invoke the generic operation, ExecuteReader.</span></span>  
  
-   <span data-ttu-id="2cca6-134">`public System.Data.DataSet ExecuteReader(string Query)`MS_SAMPLE_EMPLOYEE インターフェイス テーブルに対して SELECT ステートメントを実行するために呼び出さメソッドです。</span><span class="sxs-lookup"><span data-stu-id="2cca6-134">`public System.Data.DataSet ExecuteReader(string Query)` is the method that you invoke to perform a SELECT statement on the MS_SAMPLE_EMPLOYEE interface table.</span></span>  
  
## <a name="creating-a-wcf-client-to-invoke-an-executereader-operation"></a><span data-ttu-id="2cca6-135">ExecuteReader 操作を呼び出す、WCF クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="2cca6-135">Creating a WCF Client to Invoke an ExecuteReader Operation</span></span>  
 <span data-ttu-id="2cca6-136">WCF クライアントを使用して Oracle E-business Suite で操作の実行に必要なアクションの汎用的なセットは、一連のタスクで説明されている[Oracle E-business Suite アダプターで WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="2cca6-136">The generic set of actions required to perform an operation on Oracle E-Business Suite using a WCF client involves a set of tasks described in [Overview of the WCF service model with the Oracle E-Business Suite adapter](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md).</span></span> <span data-ttu-id="2cca6-137">このセクションを呼び出すための WCF クライアントを作成する方法について説明、 **ExecuteReader**操作します。</span><span class="sxs-lookup"><span data-stu-id="2cca6-137">This section describes how to create a WCF client to invoke the **ExecuteReader** operation.</span></span>  
  
#### <a name="to-create-a-wcf-client-to-invoke-executereader-operation"></a><span data-ttu-id="2cca6-138">ExecuteReader 操作を呼び出す WCF クライアントを作成するには</span><span class="sxs-lookup"><span data-stu-id="2cca6-138">To create a WCF client to invoke ExecuteReader operation</span></span>  
  
1.  <span data-ttu-id="2cca6-139">Visual Studio で Visual c# プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="2cca6-139">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="2cca6-140">このトピックでは、コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="2cca6-140">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="2cca6-141">WCF クライアント クラスを生成、 **ExecuteReader**汎用的な操作です。</span><span class="sxs-lookup"><span data-stu-id="2cca6-141">Generate the WCF client class for the **ExecuteReader** generic operation.</span></span> <span data-ttu-id="2cca6-142">使用して、Oracle E-business Suite に接続するときは、この操作は、ルート ノードで使用可能な[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="2cca6-142">This operation is available under the root node when you connect to the Oracle E-Business Suite using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="2cca6-143">詳細については、WCF クライアント クラスを生成する、次を参照してください。 [WCF クライアントまたは Oracle E-business Suite ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="2cca6-143">For more information about generating a WCF client class, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="2cca6-144">WCF クライアント クラスを生成する前に必ず設定してください、 **EnableBizTalkCompatibilityMode**プロパティを false にバインドします。</span><span class="sxs-lookup"><span data-stu-id="2cca6-144">Before generating the WCF client class, make sure you set the **EnableBizTalkCompatibilityMode** binding property to false.</span></span>  
  
3.  <span data-ttu-id="2cca6-145">ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.OracleEBS`と`Microsoft.ServiceModel.Channels`です。</span><span class="sxs-lookup"><span data-stu-id="2cca6-145">In the Solution Explorer, add reference to `Microsoft.Adapters.OracleEBS` and `Microsoft.ServiceModel.Channels`.</span></span>  
  
4.  <span data-ttu-id="2cca6-146">Program.cs ファイルを開き、次の名前空間を追加します。</span><span class="sxs-lookup"><span data-stu-id="2cca6-146">Open the Program.cs file and add the following namespaces:</span></span>  
  
    -   `Microsoft.Adapters.OracleEBS`  
  
    -   `System.ServiceModel`  
  
5.  <span data-ttu-id="2cca6-147">Program.cs ファイルでは、次のスニペット」の説明に従って、クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="2cca6-147">In the Program.cs file, create a client as described in the snippet below.</span></span>  
  
    ```  
    OracleEBSBinding binding = new OracleEBSBinding();  
    EndpointAddress address = new EndpointAddress("oracleebs://ebs-72-11");  
    GenericOperation_Client client = new GenericOperation_Client(binding, address);  
    ```  
  
     <span data-ttu-id="2cca6-148">このスニペットで`GenericOperation_Client`OracleEBSBindingClient.cs で定義された WCF クライアントです。</span><span class="sxs-lookup"><span data-stu-id="2cca6-148">In this snippet, `GenericOperation_Client` is the WCF client defined in OracleEBSBindingClient.cs.</span></span> <span data-ttu-id="2cca6-149">このファイルにより生成されて、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="2cca6-149">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2cca6-150">このスニペットでは、アプリケーション コードで明示的にバインドとエンドポイント アドレスを指定するだけです。</span><span class="sxs-lookup"><span data-stu-id="2cca6-150">In this snippet, you explicitly specify the binding and endpoint address in your application code.</span></span> <span data-ttu-id="2cca6-151">これらの値を使用するには、アプリケーション構成ファイルから、app.config、によって生成されるも、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="2cca6-151">You can use these values from the application configuration file, app.config, also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="2cca6-152">クライアント バインディングを指定するさまざまな方法の詳細については、次を参照してください。 [for Oracle E-business Suite バインド クライアントを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)です。</span><span class="sxs-lookup"><span data-stu-id="2cca6-152">For more information about the different ways of specifying client binding, see [Configure a client binding for the Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md).</span></span>  
  
6.  <span data-ttu-id="2cca6-153">クライアントの資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="2cca6-153">Set the credentials for the client.</span></span>  
  
    ```  
    client.ClientCredentials.UserName.UserName = "myuser";  
    client.ClientCredentials.UserName.Password = "mypassword";  
    ```  
  
7.  <span data-ttu-id="2cca6-154">インターフェイス テーブルに対する操作を実行しているため、アプリケーションのコンテキストを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2cca6-154">Because you are performing an operation on an interface table, you must set the application context.</span></span> <span data-ttu-id="2cca6-155">この例では、アプリケーションのコンテキストを設定するを指定する、 **OracleUserName**、 **OraclePassword**、および**OracleEBSResponsibilityName**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="2cca6-155">In this example, to set the application context, you specify the **OracleUserName**, **OraclePassword**, and **OracleEBSResponsibilityName** binding properties.</span></span> <span data-ttu-id="2cca6-156">アプリケーション コンテキストの詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。</span><span class="sxs-lookup"><span data-stu-id="2cca6-156">For more information about application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
    ```  
    binding.OracleUserName = "myOracleEBSUserName";  
    binding.OraclePassword = "myOracleEBSPassword";  
    binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
    ```  
  
8.  <span data-ttu-id="2cca6-157">次のスニペット」の説明に従って、クライアントを開きます。</span><span class="sxs-lookup"><span data-stu-id="2cca6-157">Open the client as described in the snippet below:</span></span>  
  
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
  
9. <span data-ttu-id="2cca6-158">呼び出す、 **ExecuteReader** MS_SAMPLE_EMPLOYEE テーブルに対する選択操作を実行するための操作です。</span><span class="sxs-lookup"><span data-stu-id="2cca6-158">Invoke the **ExecuteReader** operation for performing the SELECT operation on MS_SAMPLE_EMPLOYEE table.</span></span> <span data-ttu-id="2cca6-159">ExecuteReader 操作を呼び出す前に追加する必要があります、`System.Data`名前空間をコードにします。</span><span class="sxs-lookup"><span data-stu-id="2cca6-159">Before you invoke the ExecuteReader operation, you must add the `System.Data` namespace to your code.</span></span>  
  
    ```  
    string query = "SELECT * FROM MS_SAMPLE_EMPLOYEE";  
    DataSet ds = client.ExecuteReader(query);  
  
    Console.WriteLine("Invoking the SELECT statement using ExecuteReader");  
    Console.WriteLine("*****************************************************");  
    foreach (DataTable tab in ds.Tables)  
    {  
       foreach (DataRow row in tab.Rows)  
       {  
          Console.WriteLine("The details of the employee are: ");  
          for (int i = 0; i < tab.Columns.Count; i++)  
          {  
             Console.WriteLine(row[i]);  
          }  
          Console.WriteLine();  
       }  
    }  
    Console.WriteLine("*****************************************************");  
    Console.ReadLine();  
  
    ```  
  
10. <span data-ttu-id="2cca6-160">次のスニペット」の説明に従って、クライアントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="2cca6-160">Close the client as described in the snippet below:</span></span>  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
11. <span data-ttu-id="2cca6-161">プロジェクトをビルドし、それを実行します。</span><span class="sxs-lookup"><span data-stu-id="2cca6-161">Build the project and then run it.</span></span> <span data-ttu-id="2cca6-162">MS_SAMPLE_EMPLOYEE テーブル内のすべてのレコードは、コンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2cca6-162">All the records in the MS_SAMPLE_EMPLOYEE table are displayed on the console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cca6-163">参照</span><span class="sxs-lookup"><span data-stu-id="2cca6-163">See Also</span></span>  
 [<span data-ttu-id="2cca6-164">WCF サービス モデルを使用して Oracle E-business Suite アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="2cca6-164">Develop Oracle E-Business Suite applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)