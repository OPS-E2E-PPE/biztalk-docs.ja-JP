---
title: WCF サービス モデルを使用して SQL Server でのテーブル値関数を呼び出す |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48688bcc-36b4-4cc1-b078-17e7a5e1cf8c
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4243973f6e6b04cddec14261d5b1acedff4b9e0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989163"
---
# <a name="invoke-table-valued-functions-in-sql-server-by-using-the-wcf-service-model"></a><span data-ttu-id="6b8e8-102">WCF サービス モデルを使用して SQL Server でのテーブル値関数を呼び出す</span><span class="sxs-lookup"><span data-stu-id="6b8e8-102">Invoke Table-Valued Functions in SQL Server by Using the WCF Service Model</span></span>
<span data-ttu-id="6b8e8-103">使用することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で SQL Server でのテーブル値関数を呼び出すための WCF サービス モデルを使用して .NET アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-103">You can use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in a .NET application using the WCF service model to invoke table-valued functions in SQL Server.</span></span> <span data-ttu-id="6b8e8-104">アダプターは、SQL サーバー上で直接呼び出すことができるメソッドとして、テーブル値関数を公開します。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-104">The adapter exposes the table-valued functions as methods that can be invoked directly on SQL Server.</span></span> <span data-ttu-id="6b8e8-105">アダプターがスカラー関数をサポートする方法の詳細については、次を参照してください。 [SQL アダプターを使用して SQL Server での Execute Table-Valued 関数](../../adapters-and-accelerators/adapter-sql/execute-table-valued-functions-in-sql-server-using-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-105">For more information about how the adapter supports scalar functions, see [Execute Table-Valued Functions in SQL Server using the SQL adapter](../../adapters-and-accelerators/adapter-sql/execute-table-valued-functions-in-sql-server-using-the-sql-adapter.md).</span></span>  
  
 <span data-ttu-id="6b8e8-106">このトピックでは、SQL Server データベースで TVF_EMPLOYEE 関数を呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-106">This topic demonstrates how to invoke the TVF_EMPLOYEE function in a SQL Server database.</span></span> <span data-ttu-id="6b8e8-107">TVF_EMPLOYEE 関数は、従業員の指定、**従業員**テーブルが表示され、従業員のレコードを返します。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-107">The TVF_EMPLOYEE function takes the designation of an employee in the **Employee** table and returns the record for the employee.</span></span> <span data-ttu-id="6b8e8-108">TVF_EMPLOYEE 関数と**従業員**サンプルで提供される SQL スクリプトを実行してテーブルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-108">The TVF_EMPLOYEE function and the **Employee** table are created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="6b8e8-109">詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-109">For more information, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="6b8e8-110">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="6b8e8-110">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="6b8e8-111">このトピックの例で TVF_EMPLOYEE テーブル値関数が呼び出される、**従業員**テーブル。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-111">The example in this topic invoked the TVF_EMPLOYEE table-valued function on the **Employee** table.</span></span> <span data-ttu-id="6b8e8-112">TVF_EMPLOYEE 関数と**従業員**サンプルで提供される SQL スクリプトを実行してテーブルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-112">TVF_EMPLOYEE function and the **Employee** table are created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="6b8e8-113">サンプルについては、 **TableFunction_ServiceModel**、これは、このトピックに基づいてがで提供されていることも、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-113">A sample, **TableFunction_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span> <span data-ttu-id="6b8e8-114">詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-114">For more information, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="6b8e8-115">WCF クライアント クラス</span><span class="sxs-lookup"><span data-stu-id="6b8e8-115">The WCF Client Class</span></span>  
 <span data-ttu-id="6b8e8-116">SQL Server を使用してスカラー関数を呼び出すために生成された WCF クライアントの名前、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次の表に記載されています。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-116">The name of the WCF client generated for invoking the scalar function in SQL Server using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is listed in the following table.</span></span>  
  
|<span data-ttu-id="6b8e8-117">SQL Server データベースの成果物</span><span class="sxs-lookup"><span data-stu-id="6b8e8-117">SQL Server Database Artifact</span></span>|<span data-ttu-id="6b8e8-118">WCF クライアント名</span><span class="sxs-lookup"><span data-stu-id="6b8e8-118">WCF Client Name</span></span>|  
|----------------------------------|---------------------|  
|<span data-ttu-id="6b8e8-119">テーブル値関数</span><span class="sxs-lookup"><span data-stu-id="6b8e8-119">Table-valued function</span></span>|<span data-ttu-id="6b8e8-120">[スキーマ] TableValuedFunctions_ クライアント</span><span class="sxs-lookup"><span data-stu-id="6b8e8-120">TableValuedFunctions_[SCHEMA]Client</span></span>|  
  
 <span data-ttu-id="6b8e8-121">[スキーマ] コレクションの SQL Server のアイテム、=たとえば、dbo です。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-121">[SCHEMA] = Collection of SQL Server artifacts; for example, dbo.</span></span>  
  
### <a name="method-signature-for-invoking-table-valued-functions"></a><span data-ttu-id="6b8e8-122">テーブル値関数を呼び出すためのメソッド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="6b8e8-122">Method Signature for Invoking Table-valued Functions</span></span>  
 <span data-ttu-id="6b8e8-123">次の表では、テーブルに対する基本操作のメソッド シグネチャを示します。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-123">The following table shows the method signatures for the basic operations on a table.</span></span> <span data-ttu-id="6b8e8-124">署名は、ビューの名前空間と名前のテーブルを置換する点を除いて表示は、同じです。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-124">The signatures are the same for a view, except that the view namespace and name replace those of the table.</span></span>  
  
|<span data-ttu-id="6b8e8-125">演算</span><span class="sxs-lookup"><span data-stu-id="6b8e8-125">Operation</span></span>|<span data-ttu-id="6b8e8-126">メソッド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="6b8e8-126">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="6b8e8-127">テーブル値関数の名前</span><span class="sxs-lookup"><span data-stu-id="6b8e8-127">Table-valued function name</span></span>|<span data-ttu-id="6b8e8-128">パブリック名前空間 [FUNCTION_NAME] [FUNCTION_NAME] (param1、param2、.\)</span><span class="sxs-lookup"><span data-stu-id="6b8e8-128">public [NAMESPACE][FUNCTION_NAME][] [FUNCTION_NAME](param1, param2, …\)</span></span>|  
  
 <span data-ttu-id="6b8e8-129">[NAMESPACE] 名前空間、たとえば、schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE を =</span><span class="sxs-lookup"><span data-stu-id="6b8e8-129">[NAMESPACE] = The namespace, for example, schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE</span></span>  
  
 <span data-ttu-id="6b8e8-130">[FUNCTION_NAME] = テーブル値関数の名前。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-130">[FUNCTION_NAME] = Name of the table-valued function.</span></span>  
  
 <span data-ttu-id="6b8e8-131">WCF クライアント クラスを生成の例として、次のコードがメソッド シグネチャを示します、 **TVF_EMPLOYEE**をパラメーターとしての従業員の表記を取得し、従業員が返されます、dbo スキーマ内のスカラー関数レコードです。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-131">As an example, the following code shows the method signatures for a WCF client class generated for the **TVF_EMPLOYEE** scalar functions, in the dbo schema, which takes the employee designation as a parameter and returns the employee record.</span></span>  
  
```  
public partial class TableValuedFunctions_dboClient : System.ServiceModel.ClientBase<TableValuedFunctions_dbo>, TableValuedFunctions_dbo {      
    public schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE[] TVF_EMPLOYEE(string emp_desig);  
}  
```  
  
 <span data-ttu-id="6b8e8-132">このスニペットで**TableValuedFunctions_dboClient**によって生成された SqlAdapterBindingClient.cs で WCF クラスの名前を指定します、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-132">In this snippet, **TableValuedFunctions_dboClient** is the name of the WCF class in the SqlAdapterBindingClient.cs generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
### <a name="parameters-for-invoking-table-valued-functions"></a><span data-ttu-id="6b8e8-133">テーブル値関数の呼び出しのパラメーター</span><span class="sxs-lookup"><span data-stu-id="6b8e8-133">Parameters for Invoking Table-valued Functions</span></span>  
 <span data-ttu-id="6b8e8-134">によって公開されるメソッドのパラメーター、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を呼び出す、テーブル値関数は、SQL Server で、関数定義で定義されているパラメーターと同じです。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-134">The parameters for the methods exposed by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to invoke a table-valued function are the same as the parameters defined in the function definition in SQL Server.</span></span> <span data-ttu-id="6b8e8-135">たとえば、TVF_EMPLOYEE テーブル値関数を呼び出すためのパラメーターは emp_desig は、従業員の指定を済みます。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-135">For example, the parameter for invoking the TVF_EMPLOYEE table-valued function is emp_desig and takes an employee’s designation.</span></span>  
  
 <span data-ttu-id="6b8e8-136">ここでも、テーブル値関数の戻り値は、SQL Server での関数定義で定義されている戻り値と同じです。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-136">Again, the return value for a table-valued function is same as the return value defined in the function definition in SQL Server.</span></span> <span data-ttu-id="6b8e8-137">たとえば、TVF_EMPLOYEE 関数の戻り値は type[] schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE のレコードの配列です。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-137">For example, the return value for the TVF_EMPLOYEE function is an array of records of type schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE[].</span></span>  
  
## <a name="creating-a-wcf-client-to-invoke-table-valued-functions"></a><span data-ttu-id="6b8e8-138">テーブル値関数を呼び出すための WCF クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-138">Creating a WCF Client to Invoke Table-valued Functions</span></span>  
 <span data-ttu-id="6b8e8-139">WCF クライアントを使用して SQL Server で操作の実行に必要なアクションの汎用的なセットは、一連のタスクで説明されている[SQL アダプターを使用した WCF サービス モデルの概要](overview-of-the-wcf-service-model-with-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-139">The generic set of actions required to perform an operation on SQL Server using a WCF client involves a set of tasks described in [Overview of the WCF Service Model with the SQL Adapter](overview-of-the-wcf-service-model-with-the-sql-adapter.md).</span></span> <span data-ttu-id="6b8e8-140">このセクションを呼び出す、WCF クライアントを作成する方法を説明します、 **TVF_EMPLOYEE**テーブル値関数。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-140">This section describes how to create a WCF client to invoke the **TVF_EMPLOYEE** table-valued function.</span></span>  
  
 
1. <span data-ttu-id="6b8e8-141">Visual c# プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsVStudioNoVersion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-141">Create a Visual C# project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsVStudioNoVersion-md.md)].</span></span> <span data-ttu-id="6b8e8-142">このトピックでは、コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-142">For this topic, create a console application.</span></span>  
  
2. <span data-ttu-id="6b8e8-143">WCF クライアント クラスを生成、 **TVF_EMPLOYEE**スカラー関数。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-143">Generate the WCF client class for the **TVF_EMPLOYEE** scalar function.</span></span> <span data-ttu-id="6b8e8-144">WCF クライアント クラスを生成する詳細については、次を参照してください。 [SQL Server のアイテムの WCF クライアントまたは WCF サービス コントラクトを生成](generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)します。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-144">For more information about generating a WCF client class, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
3. <span data-ttu-id="6b8e8-145">ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.Sql`と`Microsoft.ServiceModel.Channels`します。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-145">In the Solution Explorer, add reference to `Microsoft.Adapters.Sql` and `Microsoft.ServiceModel.Channels`.</span></span>  
  
4. <span data-ttu-id="6b8e8-146">Program.cs を開き、次のスニペットの説明に従って、クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-146">Open the Program.cs and create a client as described in the snippet below.</span></span>  
  
   ```  
  
             TableValuedFunctions_dboClient client = new TableValuedFunctions_dboClient("SqlAdapterBinding_TableValuedFunctions_dbo");  
   client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
   client.ClientCredentials.UserName.Password = "<Enter password here>";  
   ```  
  
    <span data-ttu-id="6b8e8-147">このスニペットで`TableValuedFunctions_dboClient`SqlAdapterBindingClient.cs で定義されている WCF クライアントです。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-147">In this snippet, `TableValuedFunctions_dboClient` is the WCF client defined in SqlAdapterBindingClient.cs.</span></span> <span data-ttu-id="6b8e8-148">このファイルがによって生成された、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-148">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="6b8e8-149">`SqlAdapterBinding_TableValuedFunctions_dbo` クライアント エンドポイント構成の名前を指定され、app.config で定義されます。このファイルがによって生成されても、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]バインドのプロパティとその他の構成設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-149">`SqlAdapterBinding_TableValuedFunctions_dbo` is the name of the client endpoint configuration and is defined in the app.config. This file is also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and contains the binding properties and other configuration settings.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6b8e8-150">このスニペットでは、構成ファイルからバインドおよびエンドポイント アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-150">In this snippet, you use the binding and endpoint address from the configuration file.</span></span> <span data-ttu-id="6b8e8-151">これらの値は、コードで明示的に指定できます。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-151">You can also explicitly specify these values in your code.</span></span> <span data-ttu-id="6b8e8-152">クライアント バインディングを指定し、さまざまな方法の詳細については、次を参照してください。 [SQL アダプタのクライアントのバインディングを構成する](configure-a-client-binding-for-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-152">For more information on the different ways of specifying then client binding, see [Configure a Client Binding for the SQL Adapter](configure-a-client-binding-for-the-sql-adapter.md).</span></span>  
  
5. <span data-ttu-id="6b8e8-153">次のスニペットで説明されているように、クライアントを開きます。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-153">Open the client as described in the snippet below:</span></span>  
  
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
  
6. <span data-ttu-id="6b8e8-154">呼び出す、 **TVF_EMPLOYEE** "Manager"の指定を持つすべての従業員レコードを取得します。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-154">Invoke the **TVF_EMPLOYEE** function to retrieve all the employee records having the “Manager” designation.</span></span>  
  
   ```  
   Console.WriteLine("Invoking the TVF_EMPLOYEE function");  
   schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE[] emp_details;  
   string emp_designation = "Manager";  
  
   try  
   {  
       emp_details = client.TVF_EMPLOYEE(emp_designation);  
   }  
   catch (Exception e)  
   {  
       Console.WriteLine("Exception: " + e.Message);  
       throw;  
   }  
   Console.WriteLine("The details for the employee with the 'Manager' designation are:");  
   Console.WriteLine("*******************************************************************");  
   for (int i = 0; i < emp_details.Length; i++)  
   {  
       Console.WriteLine("Employee ID        : " + emp_details[i].Employee_ID);  
       Console.WriteLine("Employee Name      : " + emp_details[i].Name);  
       Console.WriteLine("Employee Desigation: " + emp_details[i].Designation);  
       Console.WriteLine("Employee Salary    : " + emp_details[i].Salary);  
       Console.WriteLine();  
   }  
   ```  
  
7. <span data-ttu-id="6b8e8-155">次のスニペットの説明に従って、クライアントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-155">Close the client as described in the snippet below:</span></span>  
  
   ```  
   client.Close();  
   Console.WriteLine("Press any key to exit...");  
   Console.ReadLine();  
   ```  
  
8. <span data-ttu-id="6b8e8-156">プロジェクトをビルドし、それを実行します。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-156">Build the project and then run it.</span></span> <span data-ttu-id="6b8e8-157">アプリケーションでは、従業員 ID、名、および"Manager"指定付きのすべての従業員の給与が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b8e8-157">The application displays the employee ID, name, and salary of all the employees with a “Manager” designation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b8e8-158">参照</span><span class="sxs-lookup"><span data-stu-id="6b8e8-158">See Also</span></span>  
[<span data-ttu-id="6b8e8-159">WCF サービス モデルを使用してアプリケーションを開発する</span><span class="sxs-lookup"><span data-stu-id="6b8e8-159">Develop applications using the WCF Service model</span></span>](develop-sql-applications-using-the-wcf-service-model.md)