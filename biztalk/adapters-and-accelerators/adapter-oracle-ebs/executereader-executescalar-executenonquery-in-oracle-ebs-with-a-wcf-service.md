---
title: WCF サービス モデルを使用して Oracle E-business Suite で ExecuteReader、executescalar、ExecuteNonQuery 操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 54c42db1-9a4d-4003-af69-f75ff48b575a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0286de636c2ad9fb50fabafe73b5257d18cf70b2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993179"
---
# <a name="executereader-executescalar-or-executenonquery-operations-in-oracle-e-business-suite-using-the-wcf-service-model"></a><span data-ttu-id="b4d7e-102">WCF サービス モデルを使用して Oracle E-business Suite で ExecuteReader、executescalar、ExecuteNonQuery 操作</span><span class="sxs-lookup"><span data-stu-id="b4d7e-102">ExecuteReader, ExecuteScalar, or ExecuteNonQuery operations in Oracle E-Business Suite using the WCF service model</span></span>
<span data-ttu-id="b4d7e-103">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]などの一般的な操作を公開する**ExecuteNonQuery**、 **ExecuteReader**、および**ExecuteScalar**します。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-103">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] exposes generic operations such as **ExecuteNonQuery**, **ExecuteReader**, and **ExecuteScalar**.</span></span> <span data-ttu-id="b4d7e-104">これらの操作を使用して、Oracle E-business Suite で任意のステートメントを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-104">You can use these operations to execute any statement on Oracle E-Business Suite.</span></span> <span data-ttu-id="b4d7e-105">これらの操作は、応答するためのステートメントの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-105">These operations differ based on the kind of response you get for the statement.</span></span> <span data-ttu-id="b4d7e-106">アダプターがこれらの操作をサポートする方法の詳細については、次を参照してください。 [ExecuteNonQuery、ExecuteReader、ExecuteScalar 操作のサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)します。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-106">For more information about how the adapter supports these operations, see [Support for ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md).</span></span>  
  
 <span data-ttu-id="b4d7e-107">このトピックでは、実行する方法を示します、 **ExecuteReader**操作を使用して、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] WCF サービス モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-107">This topic demonstrates how to perform an **ExecuteReader** operation using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] using the WCF service model.</span></span> <span data-ttu-id="b4d7e-108">実行するには、このトピックで説明する手順の同じセットを利用できる**ExecuteNonQuery**と**ExecuteScalar**操作。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-108">You can follow the same set of procedures described in this topic to perform **ExecuteNonQuery** and **ExecuteScalar** operations.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="b4d7e-109">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="b4d7e-109">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="b4d7e-110">このトピックの例では、 **ExecuteReader** MS_SAMPLE_EMPLOYEE インターフェイス テーブルでの選択操作を実行する操作。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-110">The example in this topic performs an **ExecuteReader** operation to perform a SELECT operation on the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="b4d7e-111">サンプルに付属のスクリプトを実行して、テーブルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-111">The table is created by running the script provided with the samples.</span></span> <span data-ttu-id="b4d7e-112">サンプルの詳細については、次を参照してください。 [Oracle EBS アダプター用のサンプル](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-112">For more information about samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="b4d7e-113">サンプルについては、 **ExecuteReader**、これは、このトピックに基づいてがで提供されていることも、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-113">A sample, **ExecuteReader**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="b4d7e-114">WCF クライアント クラス</span><span class="sxs-lookup"><span data-stu-id="b4d7e-114">The WCF Client Class</span></span>  
 <span data-ttu-id="b4d7e-115">一般的な操作 (ExecuteNonQuery、ExecuteReader、ExecuteScalar のいずれか) を使用してを呼び出すために生成された WCF クライアントの名前、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]次の表に記載されています。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-115">The name of the WCF client generated for invoking generic operations (ExecuteNonQuery, ExecuteReader, or ExecuteScalar) using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is listed in the following table.</span></span>  
  
|<span data-ttu-id="b4d7e-116">操作</span><span class="sxs-lookup"><span data-stu-id="b4d7e-116">Operations</span></span>|<span data-ttu-id="b4d7e-117">WCF クライアント名</span><span class="sxs-lookup"><span data-stu-id="b4d7e-117">WCF Client Name</span></span>|  
|----------------|---------------------|  
|<span data-ttu-id="b4d7e-118">ExecuteNonQuery、ExecuteReader、ExecuteScalar</span><span class="sxs-lookup"><span data-stu-id="b4d7e-118">ExecuteNonQuery, ExecuteReader, or ExecuteScalar</span></span>|<span data-ttu-id="b4d7e-119">GenericOperation_Client</span><span class="sxs-lookup"><span data-stu-id="b4d7e-119">GenericOperation_Client</span></span>|  
  
### <a name="method-signature-for-invoking-generic-operations"></a><span data-ttu-id="b4d7e-120">一般的な操作を呼び出すためのメソッド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="b4d7e-120">Method Signature for Invoking Generic Operations</span></span>  
 <span data-ttu-id="b4d7e-121">次の表では、汎用的な操作の呼び出しに公開されるメソッドのシグネチャを示します。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-121">The following table shows the signature for the method exposed to invoke the generic operations.</span></span>  
  
|<span data-ttu-id="b4d7e-122">演算</span><span class="sxs-lookup"><span data-stu-id="b4d7e-122">Operation</span></span>|<span data-ttu-id="b4d7e-123">メソッド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="b4d7e-123">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="b4d7e-124">ExecuteNonQuery</span><span class="sxs-lookup"><span data-stu-id="b4d7e-124">ExecuteNonQuery</span></span>|<span data-ttu-id="b4d7e-125">int ExecuteNonQuery (string、string[] OutputRefCursorNames、System.Data.DataSet:operator[] OutputRefCursors アウト クエリ)</span><span class="sxs-lookup"><span data-stu-id="b4d7e-125">int ExecuteNonQuery(string Query, string[] OutputRefCursorNames, out System.Data.DataSet[] OutputRefCursors)</span></span>|  
|<span data-ttu-id="b4d7e-126">ExecuteReader</span><span class="sxs-lookup"><span data-stu-id="b4d7e-126">ExecuteReader</span></span>|<span data-ttu-id="b4d7e-127">System.Data.DataSet ExecuteReader(string Query)</span><span class="sxs-lookup"><span data-stu-id="b4d7e-127">System.Data.DataSet ExecuteReader(string Query)</span></span>|  
|<span data-ttu-id="b4d7e-128">ExecuteScalar</span><span class="sxs-lookup"><span data-stu-id="b4d7e-128">ExecuteScalar</span></span>|<span data-ttu-id="b4d7e-129">文字列 ExecuteScalar(string Query)</span><span class="sxs-lookup"><span data-stu-id="b4d7e-129">string ExecuteScalar(string Query)</span></span>|  
  
 <span data-ttu-id="b4d7e-130">例として、汎用の操作メソッドのシグネチャを次のコード スニペットに示します。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-130">As an example, the signature for the generic operation methods is shown in the following code snippet.</span></span>  
  
```  
public partial class GenericOperation_Client : System.ServiceModel.ClientBase<GenericOperation_>, GenericOperation_ {  
  public int ExecuteNonQuery(string Query, string[] OutputRefCursorNames, out System.Data.DataSet[] OutputRefCursors);  
  public System.Data.DataSet ExecuteReader(string Query);  
  public string ExecuteScalar(string Query);  
}  
```  
  
 <span data-ttu-id="b4d7e-131">このスニペットで</span><span class="sxs-lookup"><span data-stu-id="b4d7e-131">In this snippet,</span></span>  
  
-   <span data-ttu-id="b4d7e-132">`GenericOperation_Client` クラスの名前です。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-132">`GenericOperation_Client` is the name of the class.</span></span> <span data-ttu-id="b4d7e-133">このクラスは、汎用の操作では、ExecuteReader を呼び出すクライアントを作成するに使用されます。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-133">This class is used to create a client to invoke the generic operation, ExecuteReader.</span></span>  
  
-   <span data-ttu-id="b4d7e-134">`public System.Data.DataSet ExecuteReader(string Query)` 呼び出す MS_SAMPLE_EMPLOYEE インターフェイス テーブルに対して SELECT ステートメントを実行する方法です。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-134">`public System.Data.DataSet ExecuteReader(string Query)` is the method that you invoke to perform a SELECT statement on the MS_SAMPLE_EMPLOYEE interface table.</span></span>  
  
## <a name="creating-a-wcf-client-to-invoke-an-executereader-operation"></a><span data-ttu-id="b4d7e-135">ExecuteReader 操作を呼び出す、WCF クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-135">Creating a WCF Client to Invoke an ExecuteReader Operation</span></span>  
 <span data-ttu-id="b4d7e-136">汎用的な一連の WCF クライアントを使用して Oracle E-business Suite での操作を実行するために必要なアクションは、一連のタスクで説明されている[Oracle E-business Suite アダプターで WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-136">The generic set of actions required to perform an operation on Oracle E-Business Suite using a WCF client involves a set of tasks described in [Overview of the WCF service model with the Oracle E-Business Suite adapter](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md).</span></span> <span data-ttu-id="b4d7e-137">このセクションを呼び出す、WCF クライアントを作成する方法を説明します、 **ExecuteReader**操作。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-137">This section describes how to create a WCF client to invoke the **ExecuteReader** operation.</span></span>  
  
#### <a name="to-create-a-wcf-client-to-invoke-executereader-operation"></a><span data-ttu-id="b4d7e-138">ExecuteReader 操作を呼び出す、WCF クライアントを作成するには</span><span class="sxs-lookup"><span data-stu-id="b4d7e-138">To create a WCF client to invoke ExecuteReader operation</span></span>  
  
1. <span data-ttu-id="b4d7e-139">Visual Studio で Visual c# プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-139">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="b4d7e-140">このトピックでは、コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-140">For this topic, create a console application.</span></span>  
  
2. <span data-ttu-id="b4d7e-141">WCF クライアント クラスを生成、 **ExecuteReader**ジェネリック操作。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-141">Generate the WCF client class for the **ExecuteReader** generic operation.</span></span> <span data-ttu-id="b4d7e-142">使用して、Oracle E-business Suite に接続するときは、この操作は、ルート ノードで使用可能な[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-142">This operation is available under the root node when you connect to the Oracle E-Business Suite using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="b4d7e-143">WCF クライアント クラスを生成する詳細については、次を参照してください。 [WCF クライアントまたは Oracle E-business Suite ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)します。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-143">For more information about generating a WCF client class, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="b4d7e-144">WCF クライアント クラスを生成する前に必ず設定して、 **EnableBizTalkCompatibilityMode**プロパティを false にバインドします。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-144">Before generating the WCF client class, make sure you set the **EnableBizTalkCompatibilityMode** binding property to false.</span></span>  
  
3. <span data-ttu-id="b4d7e-145">ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.OracleEBS`と`Microsoft.ServiceModel.Channels`します。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-145">In the Solution Explorer, add reference to `Microsoft.Adapters.OracleEBS` and `Microsoft.ServiceModel.Channels`.</span></span>  
  
4. <span data-ttu-id="b4d7e-146">Program.cs ファイルを開き、次の名前空間を追加します。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-146">Open the Program.cs file and add the following namespaces:</span></span>  
  
   -   `Microsoft.Adapters.OracleEBS`  
  
   -   `System.ServiceModel`  
  
5. <span data-ttu-id="b4d7e-147">Program.cs ファイルでは、以下のスニペットの説明に従って、クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-147">In the Program.cs file, create a client as described in the snippet below.</span></span>  
  
   ```  
   OracleEBSBinding binding = new OracleEBSBinding();  
   EndpointAddress address = new EndpointAddress("oracleebs://ebs-72-11");  
   GenericOperation_Client client = new GenericOperation_Client(binding, address);  
   ```  
  
    <span data-ttu-id="b4d7e-148">このスニペットで`GenericOperation_Client`OracleEBSBindingClient.cs で定義されている WCF クライアントです。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-148">In this snippet, `GenericOperation_Client` is the WCF client defined in OracleEBSBindingClient.cs.</span></span> <span data-ttu-id="b4d7e-149">このファイルがによって生成された、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-149">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="b4d7e-150">このスニペットでは、アプリケーション コードで明示的にバインディングとエンドポイント アドレスを指定するだけ。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-150">In this snippet, you explicitly specify the binding and endpoint address in your application code.</span></span> <span data-ttu-id="b4d7e-151">これらの値を使用するには、アプリケーション構成ファイルから app.config、によって生成されることも、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-151">You can use these values from the application configuration file, app.config, also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="b4d7e-152">クライアント バインディングを指定する、さまざまな方法の詳細については、次を参照してください。 [Oracle E-business suite バインド クライアントを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)します。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-152">For more information about the different ways of specifying client binding, see [Configure a client binding for the Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md).</span></span>  
  
6. <span data-ttu-id="b4d7e-153">クライアントの資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-153">Set the credentials for the client.</span></span>  
  
   ```  
   client.ClientCredentials.UserName.UserName = "myuser";  
   client.ClientCredentials.UserName.Password = "mypassword";  
   ```  
  
7. <span data-ttu-id="b4d7e-154">インターフェイス テーブルで操作を実行しているため、アプリケーションのコンテキストを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-154">Because you are performing an operation on an interface table, you must set the application context.</span></span> <span data-ttu-id="b4d7e-155">この例で、アプリケーションのコンテキストの設定を指定する、 **OracleUserName**、 **OraclePassword**、および**OracleEBSResponsibilityName**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-155">In this example, to set the application context, you specify the **OracleUserName**, **OraclePassword**, and **OracleEBSResponsibilityName** binding properties.</span></span> <span data-ttu-id="b4d7e-156">アプリケーションのコンテキストの詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)します。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-156">For more information about application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
   ```  
   binding.OracleUserName = "myOracleEBSUserName";  
   binding.OraclePassword = "myOracleEBSPassword";  
   binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
   ```  
  
8. <span data-ttu-id="b4d7e-157">次のスニペットで説明されているように、クライアントを開きます。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-157">Open the client as described in the snippet below:</span></span>  
  
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
  
9. <span data-ttu-id="b4d7e-158">呼び出す、 **ExecuteReader** MS_SAMPLE_EMPLOYEE テーブルに対する SELECT 操作を実行するための操作。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-158">Invoke the **ExecuteReader** operation for performing the SELECT operation on MS_SAMPLE_EMPLOYEE table.</span></span> <span data-ttu-id="b4d7e-159">追加する必要があります ExecuteReader 操作を呼び出す前に、`System.Data`をコードに名前空間。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-159">Before you invoke the ExecuteReader operation, you must add the `System.Data` namespace to your code.</span></span>  
  
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
  
10. <span data-ttu-id="b4d7e-160">次のスニペットの説明に従って、クライアントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-160">Close the client as described in the snippet below:</span></span>  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
11. <span data-ttu-id="b4d7e-161">プロジェクトをビルドし、それを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-161">Build the project and then run it.</span></span> <span data-ttu-id="b4d7e-162">MS_SAMPLE_EMPLOYEE テーブル内のすべてのレコードは、コンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-162">All the records in the MS_SAMPLE_EMPLOYEE table are displayed on the console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4d7e-163">参照</span><span class="sxs-lookup"><span data-stu-id="b4d7e-163">See Also</span></span>  
 [<span data-ttu-id="b4d7e-164">WCF サービス モデルを使用して Oracle E-business Suite のアプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="b4d7e-164">Develop Oracle E-Business Suite applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)