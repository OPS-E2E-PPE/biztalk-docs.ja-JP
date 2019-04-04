---
title: WCF サービス モデルを使用して sql ストアド プロシージャを厳密に型指定されたを呼び出す |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d56df5f6-b046-4fe4-a5b4-b29906093beb
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b88cae88a01ea3f04da3b3672153da7d00ea7633
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966819"
---
# <a name="invoke-strongly-typed-stored-procedures-in-sql-using-wcf-service-model"></a><span data-ttu-id="aea86-102">WCF サービス モデルを使用して sql ストアド プロシージャを厳密に型指定されたを呼び出す</span><span class="sxs-lookup"><span data-stu-id="aea86-102">Invoke Strongly-typed Stored Procedures in SQL using WCF Service Model</span></span>
<span data-ttu-id="aea86-103">下に一覧表示、プロシージャを呼び出すと、 **Strongly-Typed プロシージャ**内のノード、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]出力は、厳密に型指定された結果セットの形式。</span><span class="sxs-lookup"><span data-stu-id="aea86-103">When you invoke a procedure listed under the **Strongly-Typed Procedures** node in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], the output is in the form of a strongly-typed result set.</span></span> <span data-ttu-id="aea86-104">このトピックでは、厳密に型指定された結果セットを返す SQL Server でのストアド プロシージャを呼び出す、WCF クライアントを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aea86-104">This topic provides instructions on how to create a WCF client to invoke stored procedures in SQL Server that return a strongly-typed result set.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aea86-105">ユーザー定義型の列を含むテーブルに対して操作を実行している場合ことを確認するを参照してください[テーブルとユーザー定義型を持つビューで操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)アプリケーションの開発を開始する前にします。</span><span class="sxs-lookup"><span data-stu-id="aea86-105">If you are performing operation on tables that have columns of user-defined types, make sure you refer to [Operations on Tables and Views with User-Defined Types](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md) before you start developing your application.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="aea86-106">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="aea86-106">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="aea86-107">このトピックの例では、GET_EMP_DETAILS ストアド プロシージャを使用します。</span><span class="sxs-lookup"><span data-stu-id="aea86-107">The example in this topic uses the GET_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="aea86-108">このストアド プロシージャは、入力パラメーターとして従業員 ID を受け取りし、その ID を持つ従業員のすべての対応する列を返します</span><span class="sxs-lookup"><span data-stu-id="aea86-108">This stored procedure takes an employee ID as an input parameter and returns all the corresponding columns for the employee with that ID.</span></span> <span data-ttu-id="aea86-109">GET_EMP_DETAILS ストアド プロシージャは、サンプルで提供される SQL スクリプトを実行して作成されます。</span><span class="sxs-lookup"><span data-stu-id="aea86-109">The GET_EMP_DETAILS stored procedure is created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="aea86-110">サンプルの詳細については、[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aea86-110">For more information about samples, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span> <span data-ttu-id="aea86-111">サンプルについては、 **Execute_TypedStoredProcedure**、これは、このトピックに基づいてがで提供されていることも、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="aea86-111">A sample, **Execute_TypedStoredProcedure**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="aea86-112">WCF クライアント クラス</span><span class="sxs-lookup"><span data-stu-id="aea86-112">The WCF Client Class</span></span>  
 <span data-ttu-id="aea86-113">ストアド プロシージャを呼び出すために生成された WCF クライアントの名前、 **Strongly-Typed プロシージャ**ノードを使用して、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次の表に記載されています。</span><span class="sxs-lookup"><span data-stu-id="aea86-113">The name of the WCF client generated for invoking stored procedures under the **Strongly-Typed Procedures** node using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is listed in the following table.</span></span>  
  
|<span data-ttu-id="aea86-114">SQL Server データベースの成果物</span><span class="sxs-lookup"><span data-stu-id="aea86-114">SQL Server Database Artifact</span></span>|<span data-ttu-id="aea86-115">WCF クライアント名</span><span class="sxs-lookup"><span data-stu-id="aea86-115">WCF Client Name</span></span>|  
|----------------------------------|---------------------|  
|<span data-ttu-id="aea86-116">プロシージャ (下、 **Strongly-Typed プロシージャ**ノード)</span><span class="sxs-lookup"><span data-stu-id="aea86-116">Procedure (under the **Strongly-Typed Procedures** node)</span></span>|<span data-ttu-id="aea86-117">TypedProcedures_ クライアントの [スキーマ]</span><span class="sxs-lookup"><span data-stu-id="aea86-117">TypedProcedures_[schema]Client</span></span>|  
  
 <span data-ttu-id="aea86-118">[スキーマ]; プロシージャが所属するスキーマとはたとえば"dbo"とします。</span><span class="sxs-lookup"><span data-stu-id="aea86-118">[schema] is the schema to which the procedure belongs; for example “dbo”.</span></span>  
  
### <a name="method-signature-for-invoking-stored-procedures"></a><span data-ttu-id="aea86-119">ストアド プロシージャを呼び出すためのメソッド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="aea86-119">Method Signature for Invoking Stored Procedures</span></span>  
 <span data-ttu-id="aea86-120">次の表では、ストアド プロシージャを呼び出すに公開されるメソッドのシグネチャを示します。</span><span class="sxs-lookup"><span data-stu-id="aea86-120">The following table shows the signature for the method exposed to invoke the stored procedures.</span></span>  
  
|<span data-ttu-id="aea86-121">演算</span><span class="sxs-lookup"><span data-stu-id="aea86-121">Operation</span></span>|<span data-ttu-id="aea86-122">メソッド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="aea86-122">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="aea86-123">プロシージャ名</span><span class="sxs-lookup"><span data-stu-id="aea86-123">Procedure name</span></span>|<span data-ttu-id="aea86-124">[PROC_NS][プロシージャ名](param1、param2、.\)</span><span class="sxs-lookup"><span data-stu-id="aea86-124">[PROC_NS] [procedure_name](param1, param2, …\)</span></span>|  
  
 <span data-ttu-id="aea86-125">[PROC_NS] は、プロシージャの名前空間です。たとえば schemas.microsoft.com.Sql._2008._05.ProceduresResultSets.dbo.GET_EMP_DETAILS.StoredProcedureResultSet0</span><span class="sxs-lookup"><span data-stu-id="aea86-125">[PROC_NS] is the procedure namespace; for example schemas.microsoft.com.Sql._2008._05.ProceduresResultSets.dbo.GET_EMP_DETAILS.StoredProcedureResultSet0[]</span></span>  
  
 <span data-ttu-id="aea86-126">[procedure_name] は、プロシージャの名前たとえば GET_EMP_DETAILS</span><span class="sxs-lookup"><span data-stu-id="aea86-126">[procedure_name] is the name of the procedure; for example GET_EMP_DETAILS</span></span>  
  
 <span data-ttu-id="aea86-127">たとえば、GET_EMP_DETAILS プロシージャを呼び出すメソッドのシグネチャを次のコード スニペットに示します。</span><span class="sxs-lookup"><span data-stu-id="aea86-127">As an example, the signature for the method to invoke the GET_EMP_DETAILS procedure is shown in the following code snippet.</span></span>  
  
```  
public partial class TypedProcedures_dboClient : System.ServiceModel.ClientBase<TypedProcedures_dbo>, TypedProcedures_dbo{  
public schemas.microsoft.com.Sql._2008._05.ProceduresResultSets.dbo.GET_EMP_DETAILS.StoredProcedureResultSet0[]   
  GET_EMP_DETAILS(System.Nullable<int> emp_id, out int ReturnValue);  
}  
```  
  
 <span data-ttu-id="aea86-128">このスニペットで</span><span class="sxs-lookup"><span data-stu-id="aea86-128">In this snippet,</span></span>  
  
-   <span data-ttu-id="aea86-129">`TypedProcedures_dboClient` クラスの名前です。</span><span class="sxs-lookup"><span data-stu-id="aea86-129">`TypedProcedures_dboClient` is the name of the class.</span></span> <span data-ttu-id="aea86-130">この例では、このクラスを使用してストアド プロシージャを呼び出すクライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="aea86-130">In this example, you use this class to create a client to invoke the stored procedure.</span></span>  
  
-   <span data-ttu-id="aea86-131">`public schemas.microsoft.com.Sql._2008._05.ProceduresResultSets.dbo.GET_EMP_DETAILS.StoredProcedureResultSet0[] GET_EMP_DETAILS(System.Nullable<int> emp_id, out int ReturnValue)` この例では、呼び出すメソッドは、ストアド プロシージャを起動します。</span><span class="sxs-lookup"><span data-stu-id="aea86-131">`public schemas.microsoft.com.Sql._2008._05.ProceduresResultSets.dbo.GET_EMP_DETAILS.StoredProcedureResultSet0[] GET_EMP_DETAILS(System.Nullable<int> emp_id, out int ReturnValue)` is the method that you invoke in this example to invoke the stored procedure.</span></span> <span data-ttu-id="aea86-132">このストアド プロシージャは、従業員 ID を受け取り、厳密に型指定された結果セットを返します。</span><span class="sxs-lookup"><span data-stu-id="aea86-132">This stored procedure takes an employee ID and returns a strongly-typed result set.</span></span>  
  
## <a name="creating-a-wcf-client-to-invoke-a-stored-procedure-in-sql-server"></a><span data-ttu-id="aea86-133">SQL Server でストアド プロシージャを呼び出す、WCF クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="aea86-133">Creating a WCF Client to Invoke a Stored Procedure in SQL Server</span></span>  
 <span data-ttu-id="aea86-134">WCF クライアントを使用して SQL Server で操作の実行に必要なアクションの汎用的なセットは、一連のタスクで説明されている[SQL アダプターを使用した WCF サービス モデルの概要](overview-of-the-wcf-service-model-with-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="aea86-134">The generic set of actions required to perform an operation on SQL Server using a WCF client involves a set of tasks described in [Overview of the WCF Service Model with the SQL Adapter](overview-of-the-wcf-service-model-with-the-sql-adapter.md).</span></span> <span data-ttu-id="aea86-135">具体的には、WCF クライアントを呼び出すストアド プロシージャ、これは厳密に型指定の結果セットを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aea86-135">This section specifically describes how to create a WCF client that invokes a stored procedure, the result set for which is strongly-typed.</span></span> <span data-ttu-id="aea86-136">このトピックでは、例として、GET_EMP_DETAILS ストアド プロシージャを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="aea86-136">In this topic, as an example, you invoke the GET_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="aea86-137">このストアド プロシージャは、各サンプルに用意されている SQL スクリプトを実行して作成されます。</span><span class="sxs-lookup"><span data-stu-id="aea86-137">This stored procedure is created by running the SQL script provided with each sample.</span></span>  
  
1. <span data-ttu-id="aea86-138">Visual Studio で Visual c# プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="aea86-138">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="aea86-139">このトピックでは、コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="aea86-139">For this topic, create a console application.</span></span>  
  
2. <span data-ttu-id="aea86-140">GET_EMP_DETAILS ストアド プロシージャの WCF クライアント クラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="aea86-140">Generate the WCF client class for the GET_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="aea86-141">対象のプロシージャを選択するかどうかを確認、 **Strongly-Typed プロシージャ**ノード。</span><span class="sxs-lookup"><span data-stu-id="aea86-141">Make sure you select the procedure under the **Strongly-Typed Procedures** node.</span></span> <span data-ttu-id="aea86-142">WCF クライアント クラスを生成する詳細については、[SQL Server のアイテムの WCF クライアントまたは WCF サービス コントラクトを生成](generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aea86-142">For more information about generating a WCF client class, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="aea86-143">WCF クライアント クラスを生成する前に必ず設定して、 **EnableBizTalkCompatibilityMode**プロパティを false にバインドします。</span><span class="sxs-lookup"><span data-stu-id="aea86-143">Before generating the WCF client class, make sure you set the **EnableBizTalkCompatibilityMode** binding property to false.</span></span>  
  
3. <span data-ttu-id="aea86-144">ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.Sql`と`Microsoft.ServiceModel.Channels`します。</span><span class="sxs-lookup"><span data-stu-id="aea86-144">In the Solution Explorer, add reference to `Microsoft.Adapters.Sql` and `Microsoft.ServiceModel.Channels`.</span></span>  
  
4. <span data-ttu-id="aea86-145">Program.cs ファイルを開き、次のスニペットの説明に従って、クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="aea86-145">Open the Program.cs file and create a client as described in the snippet below.</span></span>  
  
   ```  
  
             TypedProcedures_dboClient client = new TypedProcedures_dboClient("SqlAdapterBinding_TypedProcedures_dbo");  
   client.ClientCredentials.UserName.UserName = "<Enter username here>";  
   client.ClientCredentials.UserName.Password = "<Enter username here>";  
   ```  
  
    <span data-ttu-id="aea86-146">このスニペットで`TypedProcedures_dboClient`SqlAdapterBindingClient.cs で定義されている WCF クライアントです。</span><span class="sxs-lookup"><span data-stu-id="aea86-146">In this snippet, `TypedProcedures_dboClient` is the WCF client defined in SqlAdapterBindingClient.cs.</span></span> <span data-ttu-id="aea86-147">このファイルがによって生成された、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="aea86-147">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="aea86-148">`SqlAdapterBinding_TypedProcedures_dbo` クライアント エンドポイント構成の名前を指定され、app.config で定義されます。このファイルがによって生成されても、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]バインドのプロパティとその他の構成設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="aea86-148">`SqlAdapterBinding_TypedProcedures_dbo` is the name of the client endpoint configuration and is defined in the app.config. This file is also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and contains the binding properties and other configuration settings.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="aea86-149">このスニペットでは、構成ファイルからバインドおよびエンドポイント アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="aea86-149">In this snippet, you use the binding and endpoint address from the configuration file.</span></span> <span data-ttu-id="aea86-150">これらの値は、コードで明示的に指定できます。</span><span class="sxs-lookup"><span data-stu-id="aea86-150">You can also explicitly specify these values in your code.</span></span> <span data-ttu-id="aea86-151">クライアント バインディングを指定する、さまざまな方法の詳細については、[SQL アダプタのクライアントのバインディングを構成する](configure-a-client-binding-for-the-sql-adapter.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aea86-151">For more information on the different ways of specifying client binding, see [Configure a Client Binding for the SQL Adapter](configure-a-client-binding-for-the-sql-adapter.md).</span></span>  
  
5. <span data-ttu-id="aea86-152">次のスニペットで説明されているように、クライアントを開きます。</span><span class="sxs-lookup"><span data-stu-id="aea86-152">Open the client as described in the snippet below:</span></span>  
  
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
  
6. <span data-ttu-id="aea86-153">以下のスニペットの説明に従って GET_EMP_DETAILS ストアド プロシージャを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="aea86-153">Invoke the GET_EMP_DETAILS stored procedure as described in the snippet below.</span></span>  
  
   ```  
   // Create array of type as specified in the method signature  
   schemas.microsoft.com.Sql._2008._05.ProceduresResultSets.dbo.GET_EMP_DETAILS.StoredProcedureResultSet0[] resultSet =  
      new schemas.microsoft.com.Sql._2008._05.ProceduresResultSets.dbo.GET_EMP_DETAILS.StoredProcedureResultSet0[1];  
   int returnCode;  
  
   try  
   {  
      Console.WriteLine("Calling a stored procedure...");  
      resultSet = client.GET_EMP_DETAILS(10001, out returnCode);  //Invoke the stored procedure  
   }  
   catch (Exception ex)  
   {  
      Console.WriteLine("Exception: " + ex.Message);  
      throw;  
   }  
   Console.WriteLine("The details for the employee with ID '10001' are:");  
   Console.WriteLine("*************************************************");  
  
   for (int i = 0; i < resultSet.Length; i++)  
      {  
         Console.WriteLine("Employee Name        : " + resultSet[i].Name);  
         Console.WriteLine("Employee Designation : " + resultSet[i].Designation);  
         Console.WriteLine("Employee Salary      : " + resultSet[i].Salary);  
      }  
  
   Console.WriteLine("*************************************************");  
  
   ```  
  
7. <span data-ttu-id="aea86-154">次のスニペットの説明に従って、クライアントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="aea86-154">Close the client as described in the snippet below:</span></span>  
  
   ```  
   client.Close();  
   Console.WriteLine("Press any key to exit...");  
   Console.ReadLine();  
   ```  
  
8. <span data-ttu-id="aea86-155">プロジェクトをビルドし、それを実行します。</span><span class="sxs-lookup"><span data-stu-id="aea86-155">Build the project and then run it.</span></span> <span data-ttu-id="aea86-156">名前を指定、および給与の従業員 ID は、コンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="aea86-156">The name, designation, and salary for the employee ID, are displayed on the console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aea86-157">参照</span><span class="sxs-lookup"><span data-stu-id="aea86-157">See Also</span></span>  
[<span data-ttu-id="aea86-158">WCF サービス モデルを使用してアプリケーションを開発する</span><span class="sxs-lookup"><span data-stu-id="aea86-158">Develop applications using the WCF Service model</span></span>](develop-sql-applications-using-the-wcf-service-model.md)