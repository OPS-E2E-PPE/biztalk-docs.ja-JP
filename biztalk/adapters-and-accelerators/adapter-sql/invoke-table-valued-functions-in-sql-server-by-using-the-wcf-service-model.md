---
title: "WCF サービス モデルを使用して SQL Server でのテーブル値関数を呼び出す |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48688bcc-36b4-4cc1-b078-17e7a5e1cf8c
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a736a82e57f71568f8718a6e4d41e7b649004120
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invoke-table-valued-functions-in-sql-server-by-using-the-wcf-service-model"></a><span data-ttu-id="90815-102">WCF サービス モデルを使用して SQL Server でのテーブル値関数を呼び出す</span><span class="sxs-lookup"><span data-stu-id="90815-102">Invoke Table-Valued Functions in SQL Server by Using the WCF Service Model</span></span>
<span data-ttu-id="90815-103">使用することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]モデルを使用して、WCF サービスを SQL Server でのテーブル値関数を呼び出す .NET アプリケーションでします。</span><span class="sxs-lookup"><span data-stu-id="90815-103">You can use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in a .NET application using the WCF service model to invoke table-valued functions in SQL Server.</span></span> <span data-ttu-id="90815-104">アダプターは、SQL サーバー上で直接呼び出すことのできるメソッドとして、テーブル値関数を公開します。</span><span class="sxs-lookup"><span data-stu-id="90815-104">The adapter exposes the table-valued functions as methods that can be invoked directly on SQL Server.</span></span> <span data-ttu-id="90815-105">アダプターがスカラー関数をサポートする方法の詳細については、次を参照してください。 [SQL アダプターを使用して SQL Server で Execute Table-Valued 関数](../../adapters-and-accelerators/adapter-sql/execute-table-valued-functions-in-sql-server-using-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="90815-105">For more information about how the adapter supports scalar functions, see [Execute Table-Valued Functions in SQL Server using the SQL adapter](../../adapters-and-accelerators/adapter-sql/execute-table-valued-functions-in-sql-server-using-the-sql-adapter.md).</span></span>  
  
 <span data-ttu-id="90815-106">このトピックでは、SQL Server データベース内で、TVF_EMPLOYEE 関数を呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="90815-106">This topic demonstrates how to invoke the TVF_EMPLOYEE function in a SQL Server database.</span></span> <span data-ttu-id="90815-107">TVF_EMPLOYEE 関数が受け取る内の従業員の指定、**従業員**テーブルが表示され、従業員のレコードを返します。</span><span class="sxs-lookup"><span data-stu-id="90815-107">The TVF_EMPLOYEE function takes the designation of an employee in the **Employee** table and returns the record for the employee.</span></span> <span data-ttu-id="90815-108">TVF_EMPLOYEE 関数および**従業員**サンプルに用意されている SQL スクリプトを実行してテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="90815-108">The TVF_EMPLOYEE function and the **Employee** table are created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="90815-109">詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)です。</span><span class="sxs-lookup"><span data-stu-id="90815-109">For more information, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="90815-110">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="90815-110">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="90815-111">このトピックの例で TVF_EMPLOYEE テーブル値関数が呼び出される、**従業員**テーブル。</span><span class="sxs-lookup"><span data-stu-id="90815-111">The example in this topic invoked the TVF_EMPLOYEE table-valued function on the **Employee** table.</span></span> <span data-ttu-id="90815-112">TVF_EMPLOYEE 関数および**従業員**サンプルに用意されている SQL スクリプトを実行してテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="90815-112">TVF_EMPLOYEE function and the **Employee** table are created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="90815-113">サンプルは、 **TableFunction_ServiceModel**、これは、このトピックの内容に基づいても付属、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サンプルです。</span><span class="sxs-lookup"><span data-stu-id="90815-113">A sample, **TableFunction_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span> <span data-ttu-id="90815-114">詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)です。</span><span class="sxs-lookup"><span data-stu-id="90815-114">For more information, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="90815-115">WCF クライアント クラス</span><span class="sxs-lookup"><span data-stu-id="90815-115">The WCF Client Class</span></span>  
 <span data-ttu-id="90815-116">SQL Server を使用してスカラー関数を呼び出すことの生成、WCF クライアントの名前、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次の表に記載されています。</span><span class="sxs-lookup"><span data-stu-id="90815-116">The name of the WCF client generated for invoking the scalar function in SQL Server using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is listed in the following table.</span></span>  
  
|<span data-ttu-id="90815-117">SQL Server のデータベース成果物</span><span class="sxs-lookup"><span data-stu-id="90815-117">SQL Server Database Artifact</span></span>|<span data-ttu-id="90815-118">WCF クライアント名</span><span class="sxs-lookup"><span data-stu-id="90815-118">WCF Client Name</span></span>|  
|----------------------------------|---------------------|  
|<span data-ttu-id="90815-119">テーブル値関数</span><span class="sxs-lookup"><span data-stu-id="90815-119">Table-valued function</span></span>|<span data-ttu-id="90815-120">[スキーマ] TableValuedFunctions_ クライアント</span><span class="sxs-lookup"><span data-stu-id="90815-120">TableValuedFunctions_[SCHEMA]Client</span></span>|  
  
 <span data-ttu-id="90815-121">[スキーマ]; SQL Server のコレクション アイテムを =たとえば、dbo します。</span><span class="sxs-lookup"><span data-stu-id="90815-121">[SCHEMA] = Collection of SQL Server artifacts; for example, dbo.</span></span>  
  
### <a name="method-signature-for-invoking-table-valued-functions"></a><span data-ttu-id="90815-122">テーブル値関数を呼び出すためのメソッド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="90815-122">Method Signature for Invoking Table-valued Functions</span></span>  
 <span data-ttu-id="90815-123">次の表は、テーブルの基本的な操作について、メソッド シグネチャを示します。</span><span class="sxs-lookup"><span data-stu-id="90815-123">The following table shows the method signatures for the basic operations on a table.</span></span> <span data-ttu-id="90815-124">署名は、ビューの名前空間と名前のテーブルを置換する点を除いて、表示は、同じです。</span><span class="sxs-lookup"><span data-stu-id="90815-124">The signatures are the same for a view, except that the view namespace and name replace those of the table.</span></span>  
  
|<span data-ttu-id="90815-125">操作</span><span class="sxs-lookup"><span data-stu-id="90815-125">Operation</span></span>|<span data-ttu-id="90815-126">メソッド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="90815-126">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="90815-127">テーブル値関数の名前</span><span class="sxs-lookup"><span data-stu-id="90815-127">Table-valued function name</span></span>|<span data-ttu-id="90815-128">パブリックの名前空間 [FUNCTION_NAME] [FUNCTION_NAME] (param1、param2、.\)</span><span class="sxs-lookup"><span data-stu-id="90815-128">public [NAMESPACE][FUNCTION_NAME][] [FUNCTION_NAME](param1, param2, …\)</span></span>|  
  
 <span data-ttu-id="90815-129">[名前空間] schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE など、名前空間を =</span><span class="sxs-lookup"><span data-stu-id="90815-129">[NAMESPACE] = The namespace, for example, schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE</span></span>  
  
 <span data-ttu-id="90815-130">[FUNCTION_NAME]、テーブル値関数の名前を = です。</span><span class="sxs-lookup"><span data-stu-id="90815-130">[FUNCTION_NAME] = Name of the table-valued function.</span></span>  
  
 <span data-ttu-id="90815-131">たとえば、次のコードにはメソッド シグネチャに関するの WCF クライアント クラスを生成、 **TVF_EMPLOYEE**をパラメーターとしての従業員の表記を取得し、従業員が返されます、dbo スキーマ内のスカラー関数レコードです。</span><span class="sxs-lookup"><span data-stu-id="90815-131">As an example, the following code shows the method signatures for a WCF client class generated for the **TVF_EMPLOYEE** scalar functions, in the dbo schema, which takes the employee designation as a parameter and returns the employee record.</span></span>  
  
```  
public partial class TableValuedFunctions_dboClient : System.ServiceModel.ClientBase<TableValuedFunctions_dbo>, TableValuedFunctions_dbo {      
    public schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE[] TVF_EMPLOYEE(string emp_desig);  
}  
```  
  
 <span data-ttu-id="90815-132">このスニペットで**TableValuedFunctions_dboClient**によって生成された SqlAdapterBindingClient.cs で WCF クラスの名前を指定します、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="90815-132">In this snippet, **TableValuedFunctions_dboClient** is the name of the WCF class in the SqlAdapterBindingClient.cs generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
### <a name="parameters-for-invoking-table-valued-functions"></a><span data-ttu-id="90815-133">テーブル値関数の呼び出しのパラメーター</span><span class="sxs-lookup"><span data-stu-id="90815-133">Parameters for Invoking Table-valued Functions</span></span>  
 <span data-ttu-id="90815-134">によって公開されるメソッドのパラメーター、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を呼び出す、テーブル値関数は、SQL Server で、関数定義で定義されたパラメーターと同じです。</span><span class="sxs-lookup"><span data-stu-id="90815-134">The parameters for the methods exposed by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to invoke a table-valued function are the same as the parameters defined in the function definition in SQL Server.</span></span> <span data-ttu-id="90815-135">たとえば、パラメーター TVF_EMPLOYEE テーブル値関数を呼び出す emp_desig は、従業員の表記を取得します。</span><span class="sxs-lookup"><span data-stu-id="90815-135">For example, the parameter for invoking the TVF_EMPLOYEE table-valued function is emp_desig and takes an employee’s designation.</span></span>  
  
 <span data-ttu-id="90815-136">ここでも、テーブル値関数の戻り値は、SQL Server 内で関数定義で定義されている戻り値と同じです。</span><span class="sxs-lookup"><span data-stu-id="90815-136">Again, the return value for a table-valued function is same as the return value defined in the function definition in SQL Server.</span></span> <span data-ttu-id="90815-137">たとえば、TVF_EMPLOYEE 関数の戻り値は type[] schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE のレコードの配列です。</span><span class="sxs-lookup"><span data-stu-id="90815-137">For example, the return value for the TVF_EMPLOYEE function is an array of records of type schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE[].</span></span>  
  
## <a name="creating-a-wcf-client-to-invoke-table-valued-functions"></a><span data-ttu-id="90815-138">テーブル値関数を呼び出すための WCF クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="90815-138">Creating a WCF Client to Invoke Table-valued Functions</span></span>  
 <span data-ttu-id="90815-139">WCF クライアントを使用して SQL Server で操作の実行に必要なアクションの汎用的なセットは、一連のタスクで説明されている[SQL アダプターで WCF サービス モデルの概要](overview-of-the-wcf-service-model-with-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="90815-139">The generic set of actions required to perform an operation on SQL Server using a WCF client involves a set of tasks described in [Overview of the WCF Service Model with the SQL Adapter](overview-of-the-wcf-service-model-with-the-sql-adapter.md).</span></span> <span data-ttu-id="90815-140">このセクションを呼び出すための WCF クライアントを作成する方法について説明、 **TVF_EMPLOYEE**テーブル値関数です。</span><span class="sxs-lookup"><span data-stu-id="90815-140">This section describes how to create a WCF client to invoke the **TVF_EMPLOYEE** table-valued function.</span></span>  
  
 
1.  <span data-ttu-id="90815-141">Visual c# プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsVStudioNoVersion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="90815-141">Create a Visual C# project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsVStudioNoVersion-md.md)].</span></span> <span data-ttu-id="90815-142">このトピックでは、コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="90815-142">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="90815-143">WCF クライアント クラスを生成、 **TVF_EMPLOYEE**スカラー関数です。</span><span class="sxs-lookup"><span data-stu-id="90815-143">Generate the WCF client class for the **TVF_EMPLOYEE** scalar function.</span></span> <span data-ttu-id="90815-144">詳細については、WCF クライアント クラスを生成する、次を参照してください。 [SQL Server の成果物のために、WCF クライアントまたは WCF サービス コントラクトを生成](generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="90815-144">For more information about generating a WCF client class, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
3.  <span data-ttu-id="90815-145">ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.Sql`と`Microsoft.ServiceModel.Channels`です。</span><span class="sxs-lookup"><span data-stu-id="90815-145">In the Solution Explorer, add reference to `Microsoft.Adapters.Sql` and `Microsoft.ServiceModel.Channels`.</span></span>  
  
4.  <span data-ttu-id="90815-146">Program.cs を開き、次のスニペットの説明に従って、クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="90815-146">Open the Program.cs and create a client as described in the snippet below.</span></span>  
  
    ```  
  
              TableValuedFunctions_dboClient client = new TableValuedFunctions_dboClient("SqlAdapterBinding_TableValuedFunctions_dbo");  
    client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
    client.ClientCredentials.UserName.Password = "<Enter password here>";  
    ```  
  
     <span data-ttu-id="90815-147">このスニペットで`TableValuedFunctions_dboClient`SqlAdapterBindingClient.cs で定義された WCF クライアントです。</span><span class="sxs-lookup"><span data-stu-id="90815-147">In this snippet, `TableValuedFunctions_dboClient` is the WCF client defined in SqlAdapterBindingClient.cs.</span></span> <span data-ttu-id="90815-148">このファイルにより生成されて、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="90815-148">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="90815-149">`SqlAdapterBinding_TableValuedFunctions_dbo`クライアント エンドポイント構成の名前を指定、app.config で定義されます。このファイルがによって生成されても、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]バインドのプロパティおよびその他の構成設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="90815-149">`SqlAdapterBinding_TableValuedFunctions_dbo` is the name of the client endpoint configuration and is defined in the app.config. This file is also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and contains the binding properties and other configuration settings.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="90815-150">このスニペットでは、構成ファイルからバインディングとエンドポイント アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="90815-150">In this snippet, you use the binding and endpoint address from the configuration file.</span></span> <span data-ttu-id="90815-151">これらの値は、コードで明示的に指定できます。</span><span class="sxs-lookup"><span data-stu-id="90815-151">You can also explicitly specify these values in your code.</span></span> <span data-ttu-id="90815-152">クライアント バインディングを指定し、さまざまな方法の詳細については、次を参照してください。 [SQL アダプタのクライアントのバインディングを構成する](configure-a-client-binding-for-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="90815-152">For more information on the different ways of specifying then client binding, see [Configure a Client Binding for the SQL Adapter](configure-a-client-binding-for-the-sql-adapter.md).</span></span>  
  
5.  <span data-ttu-id="90815-153">次のスニペット」の説明に従って、クライアントを開きます。</span><span class="sxs-lookup"><span data-stu-id="90815-153">Open the client as described in the snippet below:</span></span>  
  
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
  
6.  <span data-ttu-id="90815-154">呼び出す、 **TVF_EMPLOYEE** "Manager"表記を持つすべての従業員レコードを取得します。</span><span class="sxs-lookup"><span data-stu-id="90815-154">Invoke the **TVF_EMPLOYEE** function to retrieve all the employee records having the “Manager” designation.</span></span>  
  
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
  
7.  <span data-ttu-id="90815-155">次のスニペット」の説明に従って、クライアントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="90815-155">Close the client as described in the snippet below:</span></span>  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
8.  <span data-ttu-id="90815-156">プロジェクトをビルドし、それを実行します。</span><span class="sxs-lookup"><span data-stu-id="90815-156">Build the project and then run it.</span></span> <span data-ttu-id="90815-157">アプリケーションでは、従業員 ID、名、および"Manager"が指定のすべての従業員の給与が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90815-157">The application displays the employee ID, name, and salary of all the employees with a “Manager” designation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90815-158">参照</span><span class="sxs-lookup"><span data-stu-id="90815-158">See Also</span></span>  
[<span data-ttu-id="90815-159">WCF サービス モデルを使用してアプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="90815-159">Develop applications using the WCF Service model</span></span>](develop-sql-applications-using-the-wcf-service-model.md)