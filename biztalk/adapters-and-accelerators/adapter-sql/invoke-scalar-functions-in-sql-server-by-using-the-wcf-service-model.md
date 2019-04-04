---
title: WCF サービス モデルを使用して SQL Server のスカラー関数を呼び出す |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a331e275-3c81-41a8-9ba1-3a801ebc259a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d26d2a7b13804f621b04484f2466af727b8fbf26
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998595"
---
# <a name="invoke-scalar-functions-in-sql-server-by-using-the-wcf-service-model"></a><span data-ttu-id="898b6-102">WCF サービス モデルを使用して SQL Server のスカラー関数を呼び出す</span><span class="sxs-lookup"><span data-stu-id="898b6-102">Invoke Scalar Functions in SQL Server by Using the WCF Service Model</span></span>
<span data-ttu-id="898b6-103">使用することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で SQL Server のスカラー関数を呼び出す、WCF サービス モデルを使用して .NET アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="898b6-103">You can use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in a .NET application using the WCF service model to invoke scalar functions in SQL Server.</span></span> <span data-ttu-id="898b6-104">アダプターは、SQL サーバー上で直接呼び出すことができるメソッドとしてスカラー関数を公開します。</span><span class="sxs-lookup"><span data-stu-id="898b6-104">The adapter exposes the scalar functions as methods that can be invoked directly on SQL Server.</span></span> <span data-ttu-id="898b6-105">アダプターがスカラー関数をサポートする方法の詳細については、[SQL アダプターを使用して SQL server のスカラー関数の実行](../../adapters-and-accelerators/adapter-sql/execute-scalar-functions-in-sql-server-using-the-sql-adapter.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="898b6-105">For more information about how the adapter supports scalar functions, see [Execute Scalar Functions in SQL Server using the SQL adapter](../../adapters-and-accelerators/adapter-sql/execute-scalar-functions-in-sql-server-using-the-sql-adapter.md).</span></span>  

## <a name="how-this-topic-demonstrates-invoking-scalar-functions-using-the-wcf-service-model"></a><span data-ttu-id="898b6-106">このトピックの WCF サービス モデルを使用してスカラー関数の呼び出しがについて説明する方法</span><span class="sxs-lookup"><span data-stu-id="898b6-106">How This Topic Demonstrates Invoking Scalar Functions Using the WCF Service Model</span></span>  
 <span data-ttu-id="898b6-107">このトピックでは、SQL Server データベースで GET_EMP_ID 関数を呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="898b6-107">This topic demonstrates how to invoke the GET_EMP_ID function in a SQL Server database.</span></span> <span data-ttu-id="898b6-108">GET_EMP_ID 関数は、従業員の指定、**従業員**テーブルし、対応する従業員 ID を返します。</span><span class="sxs-lookup"><span data-stu-id="898b6-108">The GET_EMP_ID function takes the designation of an employee in the **Employee** table and returns the corresponding employee ID.</span></span> <span data-ttu-id="898b6-109">GET_EMP_ID 関数と**従業員**サンプルで提供される SQL スクリプトを実行してテーブルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="898b6-109">The GET_EMP_ID function and the **Employee** table are created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="898b6-110">詳細については、[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="898b6-110">For more information, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  

## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="898b6-111">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="898b6-111">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="898b6-112">このトピックの例では、Employee テーブルに対して GET_EMP_ID スカラー関数が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="898b6-112">The example in this topic invoked the GET_EMP_ID scalar function on the Employee table.</span></span> <span data-ttu-id="898b6-113">GET_EMP_ID 関数と**従業員**サンプルで提供される SQL スクリプトを実行してテーブルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="898b6-113">The GET_EMP_ID function and the **Employee** table are created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="898b6-114">サンプルについては、 **ScalarFunction_ServiceModel**、これは、このトピックに基づいてがで提供されていることも、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="898b6-114">A sample, **ScalarFunction_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span> <span data-ttu-id="898b6-115">詳細については、[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="898b6-115">For more information, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  

## <a name="the-wcf-client-class"></a><span data-ttu-id="898b6-116">WCF クライアント クラス</span><span class="sxs-lookup"><span data-stu-id="898b6-116">The WCF Client Class</span></span>  
 <span data-ttu-id="898b6-117">SQL Server を使用してスカラー関数を呼び出すために生成された WCF クライアントの名前、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次の表に記載されています。</span><span class="sxs-lookup"><span data-stu-id="898b6-117">The name of the WCF client generated for invoking the scalar function in SQL Server using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is listed in the following table.</span></span>  

|<span data-ttu-id="898b6-118">SQL Server データベースの成果物</span><span class="sxs-lookup"><span data-stu-id="898b6-118">SQL Server Database Artifact</span></span>|<span data-ttu-id="898b6-119">WCF クライアント名</span><span class="sxs-lookup"><span data-stu-id="898b6-119">WCF Client Name</span></span>|  
|----------------------------------|---------------------|  
|<span data-ttu-id="898b6-120">スカラー関数</span><span class="sxs-lookup"><span data-stu-id="898b6-120">Scalar function</span></span>|<span data-ttu-id="898b6-121">[スキーマ] ScalarFunctions_ クライアント</span><span class="sxs-lookup"><span data-stu-id="898b6-121">ScalarFunctions_[SCHEMA]Client</span></span>|  

 <span data-ttu-id="898b6-122">[スキーマ] コレクションの SQL Server のアイテム、=たとえば、dbo です。</span><span class="sxs-lookup"><span data-stu-id="898b6-122">[SCHEMA] = Collection of SQL Server artifacts; for example, dbo.</span></span>  

### <a name="method-signature-for-invoking-scalar-functions"></a><span data-ttu-id="898b6-123">スカラー関数を呼び出すためのメソッド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="898b6-123">Method Signature for Invoking Scalar Functions</span></span>  
 <span data-ttu-id="898b6-124">次の表では、テーブルに対する基本操作のメソッド シグネチャを示します。</span><span class="sxs-lookup"><span data-stu-id="898b6-124">The following table shows the method signatures for the basic operations on a table.</span></span> <span data-ttu-id="898b6-125">署名は、ビューの名前空間と名前のテーブルを置換する点を除いて表示は、同じです。</span><span class="sxs-lookup"><span data-stu-id="898b6-125">The signatures are the same for a view, except that the view namespace and name replace those of the table.</span></span>  


|      <span data-ttu-id="898b6-126">演算</span><span class="sxs-lookup"><span data-stu-id="898b6-126">Operation</span></span>       |                             <span data-ttu-id="898b6-127">メソッド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="898b6-127">Method Signature</span></span>                             |
|----------------------|--------------------------------------------------------------------------|
| <span data-ttu-id="898b6-128">スカラー関数の名前</span><span class="sxs-lookup"><span data-stu-id="898b6-128">Scalar function name</span></span> | <span data-ttu-id="898b6-129">パブリック *< return_type >*<em>< scalar_function_name ></em>(param1、param2、...)</span><span class="sxs-lookup"><span data-stu-id="898b6-129">public *<return_type>*<em><scalar_function_name></em>(param1, param2, …)</span></span> |

 <span data-ttu-id="898b6-130">\<*retrun_type* \>関数定義で定義されている戻り値の型を =</span><span class="sxs-lookup"><span data-stu-id="898b6-130">\<*retrun_type*\> = Return type defined in the function definition</span></span>  

 <span data-ttu-id="898b6-131">\<*scalar_function_name* \> = スカラー関数の名前。</span><span class="sxs-lookup"><span data-stu-id="898b6-131">\<*scalar_function_name*\> = Name of the scalar function.</span></span>  

 <span data-ttu-id="898b6-132">WCF クライアント クラスを生成の例として、次のコードがメソッド シグネチャを示します、 **GET_EMP_ID**をパラメーターとしての従業員の表記を取得し、ID (従業員を返します、dbo スキーマ内のスカラー関数整数)。</span><span class="sxs-lookup"><span data-stu-id="898b6-132">As an example, the following code shows the method signatures for a WCF client class generated for the **GET_EMP_ID** scalar functions, in the dbo schema, which takes the employee designation as a parameter and returns an employee ID (integer).</span></span>  

```  
public partial class ScalarFunctions_dboClient : System.ServiceModel.ClientBase<ScalarFunctions_dbo>, ScalarFunctions_dbo {      
    public System.Nullable<int> GET_EMP_ID(string emp_desig);  
}  
```  

 <span data-ttu-id="898b6-133">このスニペットで**ScalarFunctions_dboClient**によって生成された SqlAdapterBindingClient.cs で WCF クラスの名前を指定します、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="898b6-133">In this snippet, **ScalarFunctions_dboClient** is the name of the WCF class in the SqlAdapterBindingClient.cs generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  

### <a name="parameters-for-invoking-scalar-functions"></a><span data-ttu-id="898b6-134">スカラー関数の呼び出しのパラメーター</span><span class="sxs-lookup"><span data-stu-id="898b6-134">Parameters for Invoking Scalar Functions</span></span>  
 <span data-ttu-id="898b6-135">によって公開されるメソッドのパラメーター、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]関数ではスカラーを呼び出すには、SQL Server のスカラー関数の定義で定義されているパラメーターと同じです。</span><span class="sxs-lookup"><span data-stu-id="898b6-135">The parameters for the methods exposed by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to invoke a scalar function are the same as the parameters defined in the scalar function definition in SQL Server.</span></span> <span data-ttu-id="898b6-136">たとえば、GET_EMP_ID スカラー関数を呼び出すためのパラメーターは emp_desig は、従業員の指定を済みます。</span><span class="sxs-lookup"><span data-stu-id="898b6-136">For example, the parameter for invoking the GET_EMP_ID scalar function is emp_desig and takes an employee’s designation.</span></span>  

 <span data-ttu-id="898b6-137">ここでも、スカラー関数の戻り値は、SQL Server のスカラー関数の定義で定義されている戻り値と同じです。</span><span class="sxs-lookup"><span data-stu-id="898b6-137">Again, the return value for a scalar function is same as the return value defined in the scalar function definition in SQL Server.</span></span> <span data-ttu-id="898b6-138">たとえば、GET_EMP_ID 関数の戻り値は、整数型の従業員の ID。</span><span class="sxs-lookup"><span data-stu-id="898b6-138">For example, the return value for the GET_EMP_ID function is an employee’s ID of type integer.</span></span>  

## <a name="creating-a-wcf-client-to-invoke-scalar-functions"></a><span data-ttu-id="898b6-139">スカラー関数を呼び出すための WCF クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="898b6-139">Creating a WCF Client to Invoke Scalar Functions</span></span>  
 <span data-ttu-id="898b6-140">WCF クライアントを使用して SQL Server で操作の実行に必要なアクションの汎用的なセットは、一連のタスクで説明されている[SQL アダプターを使用した WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="898b6-140">The generic set of actions required to perform an operation on SQL Server using a WCF client involves a set of tasks described in [Overview of the WCF Service Model with the SQL Adapter](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md).</span></span> <span data-ttu-id="898b6-141">このセクションを呼び出す、WCF クライアントを作成する方法を説明します、 **GET_EMP_ID**スカラー関数。</span><span class="sxs-lookup"><span data-stu-id="898b6-141">This section describes how to create a WCF client to invoke the **GET_EMP_ID** scalar function.</span></span>  

#### <a name="to-create-a-wcf-client"></a><span data-ttu-id="898b6-142">WCF クライアントを作成するには</span><span class="sxs-lookup"><span data-stu-id="898b6-142">To create a WCF client</span></span>  

1. <span data-ttu-id="898b6-143">Visual c# プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="898b6-143">Create a Visual C# project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="898b6-144">このトピックでは、コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="898b6-144">For this topic, create a console application.</span></span>  

2. <span data-ttu-id="898b6-145">WCF クライアント クラスを生成、 **GET_EMP_ID**スカラー関数。</span><span class="sxs-lookup"><span data-stu-id="898b6-145">Generate the WCF client class for the **GET_EMP_ID** scalar function.</span></span> <span data-ttu-id="898b6-146">WCF クライアント クラスを生成する詳細については、[SQL Server のアイテムの WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="898b6-146">For more information about generating a WCF client class, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  

3. <span data-ttu-id="898b6-147">ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.Sql`と`Microsoft.ServiceModel.Channels`します。</span><span class="sxs-lookup"><span data-stu-id="898b6-147">In the Solution Explorer, add reference to `Microsoft.Adapters.Sql` and `Microsoft.ServiceModel.Channels`.</span></span>  

4. <span data-ttu-id="898b6-148">Program.cs を開き、次のスニペットの説明に従って、クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="898b6-148">Open the Program.cs and create a client as described in the snippet below.</span></span>  

   ```  

             ScalarFunctions_dboClient client = new ScalarFunctions_dboClient("SqlAdapterBinding_ScalarFunctions_dbo");  
   client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
   client.ClientCredentials.UserName.Password = "<Enter password here>";  
   ```  

    <span data-ttu-id="898b6-149">このスニペットで`ScalarFunctions_dboClient`SqlAdapterBindingClient.cs で定義されている WCF クライアントです。</span><span class="sxs-lookup"><span data-stu-id="898b6-149">In this snippet, `ScalarFunctions_dboClient` is the WCF client defined in SqlAdapterBindingClient.cs.</span></span> <span data-ttu-id="898b6-150">このファイルがによって生成された、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="898b6-150">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="898b6-151">`SqlAdapterBinding_ScalarFunctions_dbo` クライアント エンドポイント構成の名前を指定され、app.config で定義されます。このファイルがによって生成されても、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]バインドのプロパティとその他の構成設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="898b6-151">`SqlAdapterBinding_ScalarFunctions_dbo` is the name of the client endpoint configuration and is defined in the app.config. This file is also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and contains the binding properties and other configuration settings.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="898b6-152">このスニペットでは、構成ファイルからバインドおよびエンドポイント アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="898b6-152">In this snippet, you use the binding and endpoint address from the configuration file.</span></span> <span data-ttu-id="898b6-153">これらの値は、コードで明示的に指定できます。</span><span class="sxs-lookup"><span data-stu-id="898b6-153">You can also explicitly specify these values in your code.</span></span> <span data-ttu-id="898b6-154">クライアント バインディングを指定し、さまざまな方法の詳細については、[SQL アダプタのクライアントのバインディングを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="898b6-154">For more information on the different ways of specifying then client binding, see [Configure  a Client Binding for the SQL Adapter](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md).</span></span>  

5. <span data-ttu-id="898b6-155">次のスニペットで説明されているように、クライアントを開きます。</span><span class="sxs-lookup"><span data-stu-id="898b6-155">Open the client as described in the snippet below:</span></span>  

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

6. <span data-ttu-id="898b6-156">呼び出す、 **GET_EMP_ID** "Manager"として指定である従業員の ID を取得する関数。</span><span class="sxs-lookup"><span data-stu-id="898b6-156">Invoke the **GET_EMP_ID** function to retrieve the ID for an employee with the designation as “Manager”.</span></span>  

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
   >  <span data-ttu-id="898b6-157">わかりやすく、**従業員**テーブルが 1 つだけの従業員に"Manager"の形式。</span><span class="sxs-lookup"><span data-stu-id="898b6-157">For the sake of simplicity, the **Employee** table has only one employee with “Manager” designation.</span></span> <span data-ttu-id="898b6-158">先のテーブルに同じ指定以上の従業員がある場合は、それに応じて関数を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="898b6-158">If your target table has more employees with the same designation, you must define the function accordingly.</span></span>  

7. <span data-ttu-id="898b6-159">次のスニペットの説明に従って、クライアントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="898b6-159">Close the client as described in the snippet below:</span></span>  

   ```  
   client.Close();  
   Console.WriteLine("Press any key to exit...");  
   Console.ReadLine();  
   ```  

8. <span data-ttu-id="898b6-160">プロジェクトをビルドし、それを実行します。</span><span class="sxs-lookup"><span data-stu-id="898b6-160">Build the project and then run it.</span></span> <span data-ttu-id="898b6-161">アプリケーションでは、"Manager"の指定では、従業員の従業員 ID が表示されます。</span><span class="sxs-lookup"><span data-stu-id="898b6-161">The application displays the employee ID of the employee with the designation of “Manager”.</span></span>  

## <a name="see-also"></a><span data-ttu-id="898b6-162">参照</span><span class="sxs-lookup"><span data-stu-id="898b6-162">See Also</span></span>  
[<span data-ttu-id="898b6-163">WCF サービス モデルを使用してアプリケーションを開発する</span><span class="sxs-lookup"><span data-stu-id="898b6-163">Develop applications using the WCF Service model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)