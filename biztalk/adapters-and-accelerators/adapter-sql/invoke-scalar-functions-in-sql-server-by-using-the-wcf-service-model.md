---
title: "WCF サービス モデルを使用して SQL Server のスカラー関数を呼び出す |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a331e275-3c81-41a8-9ba1-3a801ebc259a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0303378f6e265d3b5d86a1aa9cd4fb1e88df86fc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invoke-scalar-functions-in-sql-server-by-using-the-wcf-service-model"></a><span data-ttu-id="41328-102">WCF サービス モデルを使用して SQL Server のスカラー関数を呼び出す</span><span class="sxs-lookup"><span data-stu-id="41328-102">Invoke Scalar Functions in SQL Server by Using the WCF Service Model</span></span>
<span data-ttu-id="41328-103">使用することができます、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL Server のスカラー関数を呼び出す、WCF サービス モデルを使用して .NET アプリケーションでします。</span><span class="sxs-lookup"><span data-stu-id="41328-103">You can use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in a .NET application using the WCF service model to invoke scalar functions in SQL Server.</span></span> <span data-ttu-id="41328-104">アダプターは、SQL サーバー上で直接呼び出すことのできるメソッドとして、スカラー関数を公開します。</span><span class="sxs-lookup"><span data-stu-id="41328-104">The adapter exposes the scalar functions as methods that can be invoked directly on SQL Server.</span></span> <span data-ttu-id="41328-105">アダプターがスカラー関数をサポートする方法の詳細については、次を参照してください。[実行スカラー関数は、SQL アダプターを使用して SQL Server](../../adapters-and-accelerators/adapter-sql/execute-scalar-functions-in-sql-server-using-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="41328-105">For more information about how the adapter supports scalar functions, see [Execute Scalar Functions in SQL Server using the SQL adapter](../../adapters-and-accelerators/adapter-sql/execute-scalar-functions-in-sql-server-using-the-sql-adapter.md).</span></span>  
  
## <a name="how-this-topic-demonstrates-invoking-scalar-functions-using-the-wcf-service-model"></a><span data-ttu-id="41328-106">どのように、このトピックでは、WCF サービス モデルを使用してスカラー関数の呼び出しを示しています</span><span class="sxs-lookup"><span data-stu-id="41328-106">How This Topic Demonstrates Invoking Scalar Functions Using the WCF Service Model</span></span>  
 <span data-ttu-id="41328-107">このトピックでは、SQL Server データベース内で、GET_EMP_ID 関数を呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="41328-107">This topic demonstrates how to invoke the GET_EMP_ID function in a SQL Server database.</span></span> <span data-ttu-id="41328-108">GET_EMP_ID 関数が受け取る内の従業員の指定、**従業員**テーブルが表示され、対応する従業員 ID を返します。</span><span class="sxs-lookup"><span data-stu-id="41328-108">The GET_EMP_ID function takes the designation of an employee in the **Employee** table and returns the corresponding employee ID.</span></span> <span data-ttu-id="41328-109">GET_EMP_ID 関数および**従業員**サンプルに用意されている SQL スクリプトを実行してテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="41328-109">The GET_EMP_ID function and the **Employee** table are created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="41328-110">詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)です。</span><span class="sxs-lookup"><span data-stu-id="41328-110">For more information, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="41328-111">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="41328-111">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="41328-112">このトピックの例では、Employee テーブルに対して GET_EMP_ID スカラー関数が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="41328-112">The example in this topic invoked the GET_EMP_ID scalar function on the Employee table.</span></span> <span data-ttu-id="41328-113">GET_EMP_ID 関数および**従業員**サンプルに用意されている SQL スクリプトを実行してテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="41328-113">The GET_EMP_ID function and the **Employee** table are created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="41328-114">サンプルは、 **ScalarFunction_ServiceModel**、これは、このトピックの内容に基づいても付属、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サンプルです。</span><span class="sxs-lookup"><span data-stu-id="41328-114">A sample, **ScalarFunction_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span> <span data-ttu-id="41328-115">詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)です。</span><span class="sxs-lookup"><span data-stu-id="41328-115">For more information, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="41328-116">WCF クライアント クラス</span><span class="sxs-lookup"><span data-stu-id="41328-116">The WCF Client Class</span></span>  
 <span data-ttu-id="41328-117">SQL Server を使用してスカラー関数を呼び出すことの生成、WCF クライアントの名前、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次の表に記載されています。</span><span class="sxs-lookup"><span data-stu-id="41328-117">The name of the WCF client generated for invoking the scalar function in SQL Server using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is listed in the following table.</span></span>  
  
|<span data-ttu-id="41328-118">SQL Server のデータベース成果物</span><span class="sxs-lookup"><span data-stu-id="41328-118">SQL Server Database Artifact</span></span>|<span data-ttu-id="41328-119">WCF クライアント名</span><span class="sxs-lookup"><span data-stu-id="41328-119">WCF Client Name</span></span>|  
|----------------------------------|---------------------|  
|<span data-ttu-id="41328-120">スカラー関数</span><span class="sxs-lookup"><span data-stu-id="41328-120">Scalar function</span></span>|<span data-ttu-id="41328-121">[スキーマ] ScalarFunctions_ クライアント</span><span class="sxs-lookup"><span data-stu-id="41328-121">ScalarFunctions_[SCHEMA]Client</span></span>|  
  
 <span data-ttu-id="41328-122">[スキーマ]; SQL Server のコレクション アイテムを =たとえば、dbo します。</span><span class="sxs-lookup"><span data-stu-id="41328-122">[SCHEMA] = Collection of SQL Server artifacts; for example, dbo.</span></span>  
  
### <a name="method-signature-for-invoking-scalar-functions"></a><span data-ttu-id="41328-123">スカラー関数の呼び出しのメソッドの署名</span><span class="sxs-lookup"><span data-stu-id="41328-123">Method Signature for Invoking Scalar Functions</span></span>  
 <span data-ttu-id="41328-124">次の表は、テーブルの基本的な操作について、メソッド シグネチャを示します。</span><span class="sxs-lookup"><span data-stu-id="41328-124">The following table shows the method signatures for the basic operations on a table.</span></span> <span data-ttu-id="41328-125">署名は、ビューの名前空間と名前のテーブルを置換する点を除いて、表示は、同じです。</span><span class="sxs-lookup"><span data-stu-id="41328-125">The signatures are the same for a view, except that the view namespace and name replace those of the table.</span></span>  
  
|<span data-ttu-id="41328-126">操作</span><span class="sxs-lookup"><span data-stu-id="41328-126">Operation</span></span>|<span data-ttu-id="41328-127">メソッド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="41328-127">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="41328-128">スカラー関数の名前</span><span class="sxs-lookup"><span data-stu-id="41328-128">Scalar function name</span></span>|<span data-ttu-id="41328-129">パブリック*< return_type >**< scalar_function_name >*(param1、param2、...)</span><span class="sxs-lookup"><span data-stu-id="41328-129">public *<return_type>**<scalar_function_name>*(param1, param2, …)</span></span>|  
  
 <span data-ttu-id="41328-130">\<*retrun_type*> =、関数定義で定義されている戻り値の型</span><span class="sxs-lookup"><span data-stu-id="41328-130">\<*retrun_type*> = Return type defined in the function definition</span></span>  
  
 <span data-ttu-id="41328-131">\<*scalar_function_name*> = スカラー関数の名前。</span><span class="sxs-lookup"><span data-stu-id="41328-131">\<*scalar_function_name*> = Name of the scalar function.</span></span>  
  
 <span data-ttu-id="41328-132">たとえば、次のコードにはメソッド シグネチャに関するの WCF クライアント クラスを生成、 **GET_EMP_ID**をパラメーターとしての従業員の表記を取得し、ID (従業員を返します、dbo スキーマ内のスカラー関数整数)。</span><span class="sxs-lookup"><span data-stu-id="41328-132">As an example, the following code shows the method signatures for a WCF client class generated for the **GET_EMP_ID** scalar functions, in the dbo schema, which takes the employee designation as a parameter and returns an employee ID (integer).</span></span>  
  
```  
public partial class ScalarFunctions_dboClient : System.ServiceModel.ClientBase<ScalarFunctions_dbo>, ScalarFunctions_dbo {      
    public System.Nullable<int> GET_EMP_ID(string emp_desig);  
}  
```  
  
 <span data-ttu-id="41328-133">このスニペットで**ScalarFunctions_dboClient**によって生成された SqlAdapterBindingClient.cs で WCF クラスの名前を指定します、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="41328-133">In this snippet, **ScalarFunctions_dboClient** is the name of the WCF class in the SqlAdapterBindingClient.cs generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
### <a name="parameters-for-invoking-scalar-functions"></a><span data-ttu-id="41328-134">スカラー関数の呼び出しのパラメーター</span><span class="sxs-lookup"><span data-stu-id="41328-134">Parameters for Invoking Scalar Functions</span></span>  
 <span data-ttu-id="41328-135">によって公開されるメソッドのパラメーター、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を呼び出すのスカラー関数は、SQL Server のスカラー関数の定義で定義されたパラメーターと同じです。</span><span class="sxs-lookup"><span data-stu-id="41328-135">The parameters for the methods exposed by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to invoke a scalar function are the same as the parameters defined in the scalar function definition in SQL Server.</span></span> <span data-ttu-id="41328-136">たとえば、パラメーター GET_EMP_ID スカラー関数を呼び出す emp_desig は、従業員の表記を取得します。</span><span class="sxs-lookup"><span data-stu-id="41328-136">For example, the parameter for invoking the GET_EMP_ID scalar function is emp_desig and takes an employee’s designation.</span></span>  
  
 <span data-ttu-id="41328-137">もう一度、スカラー関数の戻り値は、SQL Server のスカラー関数の定義で定義されている戻り値と同じです。</span><span class="sxs-lookup"><span data-stu-id="41328-137">Again, the return value for a scalar function is same as the return value defined in the scalar function definition in SQL Server.</span></span> <span data-ttu-id="41328-138">たとえば、GET_EMP_ID 関数の戻り値は、整数型の従業員の ID です。</span><span class="sxs-lookup"><span data-stu-id="41328-138">For example, the return value for the GET_EMP_ID function is an employee’s ID of type integer.</span></span>  
  
## <a name="creating-a-wcf-client-to-invoke-scalar-functions"></a><span data-ttu-id="41328-139">スカラー関数を呼び出す、WCF クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="41328-139">Creating a WCF Client to Invoke Scalar Functions</span></span>  
 <span data-ttu-id="41328-140">WCF クライアントを使用して SQL Server で操作の実行に必要なアクションの汎用的なセットは、一連のタスクで説明されている[SQL アダプターで WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="41328-140">The generic set of actions required to perform an operation on SQL Server using a WCF client involves a set of tasks described in [Overview of the WCF Service Model with the SQL Adapter](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md).</span></span> <span data-ttu-id="41328-141">このセクションを呼び出すための WCF クライアントを作成する方法について説明、 **GET_EMP_ID**スカラー関数です。</span><span class="sxs-lookup"><span data-stu-id="41328-141">This section describes how to create a WCF client to invoke the **GET_EMP_ID** scalar function.</span></span>  
  
#### <a name="to-create-a-wcf-client"></a><span data-ttu-id="41328-142">WCF クライアントを作成するには</span><span class="sxs-lookup"><span data-stu-id="41328-142">To create a WCF client</span></span>  
  
1.  <span data-ttu-id="41328-143">Visual c# プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="41328-143">Create a Visual C# project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="41328-144">このトピックでは、コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="41328-144">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="41328-145">WCF クライアント クラスを生成、 **GET_EMP_ID**スカラー関数です。</span><span class="sxs-lookup"><span data-stu-id="41328-145">Generate the WCF client class for the **GET_EMP_ID** scalar function.</span></span> <span data-ttu-id="41328-146">詳細については、WCF クライアント クラスを生成する、次を参照してください。 [SQL Server の成果物のために、WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="41328-146">For more information about generating a WCF client class, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
3.  <span data-ttu-id="41328-147">ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.Sql`と`Microsoft.ServiceModel.Channels`です。</span><span class="sxs-lookup"><span data-stu-id="41328-147">In the Solution Explorer, add reference to `Microsoft.Adapters.Sql` and `Microsoft.ServiceModel.Channels`.</span></span>  
  
4.  <span data-ttu-id="41328-148">Program.cs を開き、次のスニペットの説明に従って、クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="41328-148">Open the Program.cs and create a client as described in the snippet below.</span></span>  
  
    ```  
  
              ScalarFunctions_dboClient client = new ScalarFunctions_dboClient("SqlAdapterBinding_ScalarFunctions_dbo");  
    client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
    client.ClientCredentials.UserName.Password = "<Enter password here>";  
    ```  
  
     <span data-ttu-id="41328-149">このスニペットで`ScalarFunctions_dboClient`SqlAdapterBindingClient.cs で定義された WCF クライアントです。</span><span class="sxs-lookup"><span data-stu-id="41328-149">In this snippet, `ScalarFunctions_dboClient` is the WCF client defined in SqlAdapterBindingClient.cs.</span></span> <span data-ttu-id="41328-150">このファイルにより生成されて、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="41328-150">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="41328-151">`SqlAdapterBinding_ScalarFunctions_dbo`クライアント エンドポイント構成の名前を指定、app.config で定義されます。このファイルがによって生成されても、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]バインドのプロパティおよびその他の構成設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="41328-151">`SqlAdapterBinding_ScalarFunctions_dbo` is the name of the client endpoint configuration and is defined in the app.config. This file is also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and contains the binding properties and other configuration settings.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="41328-152">このスニペットでは、構成ファイルからバインディングとエンドポイント アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="41328-152">In this snippet, you use the binding and endpoint address from the configuration file.</span></span> <span data-ttu-id="41328-153">これらの値は、コードで明示的に指定できます。</span><span class="sxs-lookup"><span data-stu-id="41328-153">You can also explicitly specify these values in your code.</span></span> <span data-ttu-id="41328-154">クライアント バインディングを指定し、さまざまな方法の詳細については、次を参照してください。 [SQL アダプタのクライアントのバインディングを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="41328-154">For more information on the different ways of specifying then client binding, see [Configure  a Client Binding for the SQL Adapter](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md).</span></span>  
  
5.  <span data-ttu-id="41328-155">次のスニペット」の説明に従って、クライアントを開きます。</span><span class="sxs-lookup"><span data-stu-id="41328-155">Open the client as described in the snippet below:</span></span>  
  
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
  
6.  <span data-ttu-id="41328-156">呼び出す、 **GET_EMP_ID** "Manager"としての表記である従業員の ID を取得する関数。</span><span class="sxs-lookup"><span data-stu-id="41328-156">Invoke the **GET_EMP_ID** function to retrieve the ID for an employee with the designation as “Manager”.</span></span>  
  
    ```  
    Console.WriteLine("Invoking the GET_EMP_ID function");  
    string emp_designation = "Manager";  
    try  
    {  
          System.Nullable<int> emp_id = client.GET_EMP_ID(emp_designation);  
          Console.WriteLine("The Employee ID for the employee with 'Manager' designation is:" + emp_id);  
    }  
    catch (Exception e)  
    {  
          Console.WriteLine("Exception: " + e.Message);  
          throw;  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="41328-157">わかりやすくするため、**従業員**テーブルが"Manager"表記で従業員が 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="41328-157">For the sake of simplicity, the **Employee** table has only one employee with “Manager” designation.</span></span> <span data-ttu-id="41328-158">対象のテーブルに同じ指定を持つ複数の従業員がある場合は、それに従って関数を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41328-158">If your target table has more employees with the same designation, you must define the function accordingly.</span></span>  
  
7.  <span data-ttu-id="41328-159">次のスニペット」の説明に従って、クライアントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="41328-159">Close the client as described in the snippet below:</span></span>  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
8.  <span data-ttu-id="41328-160">プロジェクトをビルドし、それを実行します。</span><span class="sxs-lookup"><span data-stu-id="41328-160">Build the project and then run it.</span></span> <span data-ttu-id="41328-161">アプリケーションには、"Manager"グループの指定には、従業員の従業員 ID が表示されます。</span><span class="sxs-lookup"><span data-stu-id="41328-161">The application displays the employee ID of the employee with the designation of “Manager”.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41328-162">参照</span><span class="sxs-lookup"><span data-stu-id="41328-162">See Also</span></span>  
[<span data-ttu-id="41328-163">WCF サービス モデルを使用してアプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="41328-163">Develop applications using the WCF Service model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)