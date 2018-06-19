---
title: WCF サービス モデルを使用して sql ストアド プロシージャの弱い型指定を呼び出して |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aaf74a40-4c03-4a4a-9b91-c21babe154fa
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ec0b8b8d022b4e96a6df4d7c0d49d8176f6cd1a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225066"
---
# <a name="invoke-weakly-typed-stored-procedures-in-sql-using-the-wcf-service-model"></a><span data-ttu-id="e36a0-102">WCF サービス モデルを使用して sql ストアド プロシージャの弱い型指定を呼び出す</span><span class="sxs-lookup"><span data-stu-id="e36a0-102">Invoke Weakly-typed Stored Procedures in SQL using the WCF Service Model</span></span>
<span data-ttu-id="e36a0-103">リストされたプロシージャを起動すると、**プロシージャ**内のノード、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]出力は次のデータセットの配列の形式でします。</span><span class="sxs-lookup"><span data-stu-id="e36a0-103">When you invoke a procedure listed under the **Procedures** node in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], the output is in the form of a DataSet array.</span></span> <span data-ttu-id="e36a0-104">このトピックでは、データセットの配列を返す SQL Server でストアド プロシージャを呼び出す、WCF クライアントを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e36a0-104">This topic provides instructions on how to create a WCF client to invoke a stored procedure in SQL Server that returns a DataSet array.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e36a0-105">ユーザー定義型の列を含むテーブルでの操作を実行する場合、必ずするを参照してください[テーブルと、SQL アダプターを使用してユーザー定義型を持つビューに対して操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)アプリケーションの開発を開始する前にします。</span><span class="sxs-lookup"><span data-stu-id="e36a0-105">If you are performing operation on tables that have columns of user-defined types, make sure you refer to [Operations on Tables and Views with User-Defined Types using the SQL adapter](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md) before you start developing your application.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="e36a0-106">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="e36a0-106">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="e36a0-107">このトピックの例では、GET_EMP_DETAILS ストアド プロシージャを使用します。</span><span class="sxs-lookup"><span data-stu-id="e36a0-107">The example in this topic uses the GET_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="e36a0-108">このストアド プロシージャは、従業員 ID を入力パラメーターとして取得し、その ID を持つ従業員をすべての対応する列を返します</span><span class="sxs-lookup"><span data-stu-id="e36a0-108">This stored procedure takes an employee ID as an input parameter and returns all the corresponding columns for the employee with that ID.</span></span> <span data-ttu-id="e36a0-109">GET_EMP_DETAILS ストアド プロシージャは、サンプルに用意されている SQL スクリプトを実行して作成されます。</span><span class="sxs-lookup"><span data-stu-id="e36a0-109">The GET_EMP_DETAILS stored procedure is created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="e36a0-110">サンプルの詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)です。</span><span class="sxs-lookup"><span data-stu-id="e36a0-110">For more information about samples, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span> <span data-ttu-id="e36a0-111">サンプルは、 **Execute_StoredProc**、これは、このトピックの内容に基づいても付属、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サンプルです。</span><span class="sxs-lookup"><span data-stu-id="e36a0-111">A sample, **Execute_StoredProc**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="e36a0-112">WCF クライアント クラス</span><span class="sxs-lookup"><span data-stu-id="e36a0-112">The WCF Client Class</span></span>  
 <span data-ttu-id="e36a0-113">ストアド プロシージャを呼び出すために生成された WCF クライアントの名前、**プロシージャ**ノードを使用して、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次の表に記載されています。</span><span class="sxs-lookup"><span data-stu-id="e36a0-113">The name of the WCF client generated for invoking stored procedures under the **Procedures** node using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is listed in the following table.</span></span>  
  
|<span data-ttu-id="e36a0-114">SQL Server のデータベース成果物</span><span class="sxs-lookup"><span data-stu-id="e36a0-114">SQL Server Database Artifact</span></span>|<span data-ttu-id="e36a0-115">WCF クライアント名</span><span class="sxs-lookup"><span data-stu-id="e36a0-115">WCF Client Name</span></span>|  
|----------------------------------|---------------------|  
|<span data-ttu-id="e36a0-116">プロシージャ (下にある、**プロシージャ**ノード)</span><span class="sxs-lookup"><span data-stu-id="e36a0-116">Procedure (under the **Procedures** node)</span></span>|<span data-ttu-id="e36a0-117">Procedures_ クライアントの [スキーマ]</span><span class="sxs-lookup"><span data-stu-id="e36a0-117">Procedures_[schema]Client</span></span>|  
  
 <span data-ttu-id="e36a0-118">[スキーマ] は; プロシージャが所属するスキーマです。たとえば"dbo"です。</span><span class="sxs-lookup"><span data-stu-id="e36a0-118">[schema] is the schema to which the procedure belongs; for example “dbo”.</span></span>  
  
### <a name="method-signature-for-invoking-stored-procedures"></a><span data-ttu-id="e36a0-119">ストアド プロシージャを呼び出すためのメソッド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="e36a0-119">Method Signature for Invoking Stored Procedures</span></span>  
 <span data-ttu-id="e36a0-120">次の表は、ストアド プロシージャを呼び出す公開されるメソッドのシグネチャを示しています。</span><span class="sxs-lookup"><span data-stu-id="e36a0-120">The following table shows the signature for the method exposed to invoke the stored procedures.</span></span>  
  
|<span data-ttu-id="e36a0-121">操作</span><span class="sxs-lookup"><span data-stu-id="e36a0-121">Operation</span></span>|<span data-ttu-id="e36a0-122">メソッド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="e36a0-122">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="e36a0-123">プロシージャ名</span><span class="sxs-lookup"><span data-stu-id="e36a0-123">Procedure name</span></span>|<span data-ttu-id="e36a0-124">System.Data.DataSet [procedure_name] (param1、param2、.\)</span><span class="sxs-lookup"><span data-stu-id="e36a0-124">System.Data.DataSet[] [procedure_name](param1, param2, …\)</span></span>|  
  
 <span data-ttu-id="e36a0-125">[procedure_name] は、プロシージャの名前たとえば GET_EMP_DETAILS</span><span class="sxs-lookup"><span data-stu-id="e36a0-125">[procedure_name] is the name of the procedure; for example GET_EMP_DETAILS</span></span>  
  
 <span data-ttu-id="e36a0-126">例として、GET_EMP_DETAILS プロシージャを呼び出すメソッドのシグネチャは次のコード スニペットに示します。</span><span class="sxs-lookup"><span data-stu-id="e36a0-126">As an example, the signature for the method to invoke the GET_EMP_DETAILS procedure is shown in the following code snippet.</span></span>  
  
```  
public partial class Procedures_dboClient : System.ServiceModel.ClientBase<Procedures_dbo>, Procedures_dbo {  
  public System.Data.DataSet[] GET_EMP_DETAILS(System.Nullable<int> emp_id, out int ReturnValue);  
}  
```  
  
 <span data-ttu-id="e36a0-127">このコードで</span><span class="sxs-lookup"><span data-stu-id="e36a0-127">In this snippet,</span></span>  
  
-   <span data-ttu-id="e36a0-128">`Procedures_dboClient`WCF クライアント クラスの名前です。</span><span class="sxs-lookup"><span data-stu-id="e36a0-128">`Procedures_dboClient` is the name of the WCF client class.</span></span> <span data-ttu-id="e36a0-129">この例では、このクラスを使用するストアド プロシージャを呼び出すクライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="e36a0-129">In this example, you use this class to create a client to invoke the stored procedure.</span></span>  
  
-   <span data-ttu-id="e36a0-130">`public System.Data.DataSet[] GET_EMP_DETAILS(System.Nullable<int> emp_id, out int ReturnValue)`この例では呼び出すメソッドは、ストアド プロシージャを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e36a0-130">`public System.Data.DataSet[] GET_EMP_DETAILS(System.Nullable<int> emp_id, out int ReturnValue)` is the method that you invoke in this example to invoke the stored procedure.</span></span> <span data-ttu-id="e36a0-131">このストアド プロシージャは、従業員 ID を取得し、データセットの配列を返します。</span><span class="sxs-lookup"><span data-stu-id="e36a0-131">This stored procedure takes an employee ID and returns a DataSet array.</span></span>  
  
## <a name="create-a-wcf-client-to-invoke-a-stored-procedure-in-sql-server"></a><span data-ttu-id="e36a0-132">SQL Server のストアド プロシージャを呼び出すための WCF クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="e36a0-132">Create a WCF Client to Invoke a Stored Procedure in SQL Server</span></span>  
 <span data-ttu-id="e36a0-133">WCF クライアントを使用して SQL Server で操作の実行に必要なアクションの汎用的なセットは、一連のタスクで説明されている[アダプターで WCF サービス モデルの概要](overview-of-the-wcf-service-model-with-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="e36a0-133">The generic set of actions required to perform an operation on SQL Server using a WCF client involves a set of tasks described in [Overview of the WCF Service Model with the Adapter](overview-of-the-wcf-service-model-with-the-sql-adapter.md).</span></span> <span data-ttu-id="e36a0-134">具体的には、WCF クライアントを呼び出すストアド プロシージャ、データセットの配列である場合に結果セットを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e36a0-134">This section specifically describes how to create a WCF client that invokes a stored procedure, the result set for which is a DataSet array.</span></span> <span data-ttu-id="e36a0-135">このトピックでは、例として、GET_EMP_DETAILS ストアド プロシージャを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e36a0-135">In this topic, as an example, you invoke the GET_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="e36a0-136">各サンプルに用意されている SQL スクリプトを実行して、このストアド プロシージャが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e36a0-136">This stored procedure is created by running the SQL script provided with each sample.</span></span>  
  
  
1.  <span data-ttu-id="e36a0-137">Visual Studio で Visual c# プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="e36a0-137">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="e36a0-138">このトピックでは、コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="e36a0-138">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="e36a0-139">GET_EMP_DETAILS ストアド プロシージャの WCF クライアント クラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="e36a0-139">Generate the WCF client class for the GET_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="e36a0-140">」の手順を選択するかどうかを確認、**プロシージャ**ノード。</span><span class="sxs-lookup"><span data-stu-id="e36a0-140">Make sure you select the procedure under the **Procedures** node.</span></span> <span data-ttu-id="e36a0-141">詳細については、WCF クライアント クラスを生成する、次を参照してください。 [SQL Server の成果物のために、WCF クライアントまたは WCF サービス コントラクトを生成](generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="e36a0-141">For more information about generating a WCF client class, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="e36a0-142">WCF クライアント クラスを生成する前に必ず設定してください、 **EnableBizTalkCompatibilityMode**プロパティを false にバインドします。</span><span class="sxs-lookup"><span data-stu-id="e36a0-142">Before generating the WCF client class, make sure you set the **EnableBizTalkCompatibilityMode** binding property to false.</span></span>  
  
3.  <span data-ttu-id="e36a0-143">ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.Sql`と`Microsoft.ServiceModel.Channels`です。</span><span class="sxs-lookup"><span data-stu-id="e36a0-143">In the Solution Explorer, add reference to `Microsoft.Adapters.Sql` and `Microsoft.ServiceModel.Channels`.</span></span>  
  
4.  <span data-ttu-id="e36a0-144">Program.cs ファイルを開き、次のスニペットの説明に従って、クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="e36a0-144">Open the Program.cs file and create a client as described in the snippet below.</span></span>  
  
    ```  
  
              Procedures_dboClient client = new Procedures_dboClient("SqlAdapterBinding_Procedures_dbo");  
  
    client.ClientCredentials.UserName.UserName = "<Enter username here>";  
    client.ClientCredentials.UserName.Password = "<Enter password here>";  
    ```  
  
     <span data-ttu-id="e36a0-145">このスニペットで`Procedures_dboClient`SqlAdapterBindingClient.cs で定義された WCF クライアントです。</span><span class="sxs-lookup"><span data-stu-id="e36a0-145">In this snippet, `Procedures_dboClient` is the WCF client defined in SqlAdapterBindingClient.cs.</span></span> <span data-ttu-id="e36a0-146">このファイルにより生成されて、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e36a0-146">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="e36a0-147">`SqlAdapterBinding_Procedures_dbo`クライアント エンドポイント構成の名前を指定、app.config で定義されます。このファイルがによって生成されても、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]バインドのプロパティおよびその他の構成設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e36a0-147">`SqlAdapterBinding_Procedures_dbo` is the name of the client endpoint configuration and is defined in the app.config. This file is also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and contains the binding properties and other configuration settings.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e36a0-148">このスニペットでは、構成ファイルからバインディングとエンドポイント アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="e36a0-148">In this snippet, you use the binding and endpoint address from the configuration file.</span></span> <span data-ttu-id="e36a0-149">これらの値は、コードで明示的に指定できます。</span><span class="sxs-lookup"><span data-stu-id="e36a0-149">You can also explicitly specify these values in your code.</span></span> <span data-ttu-id="e36a0-150">クライアント バインディングを指定するさまざまな方法の詳細については、次を参照してください。 [SQL アダプタのクライアントのバインディングを構成する](configure-a-client-binding-for-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="e36a0-150">For more information on the different ways of specifying client binding, see [Configure a Client Binding for the SQL Adapter](configure-a-client-binding-for-the-sql-adapter.md).</span></span>  
  
5.  <span data-ttu-id="e36a0-151">次のスニペット」の説明に従って、クライアントを開きます。</span><span class="sxs-lookup"><span data-stu-id="e36a0-151">Open the client as described in the snippet below:</span></span>  
  
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
  
6.  <span data-ttu-id="e36a0-152">GET_EMP_DETAILS ストアド プロシージャを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e36a0-152">Invoke the GET_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="e36a0-153">GET_EMP_DETAILS プロシージャを呼び出す前に追加する必要があります、`System.Data`名前空間をコードにします。</span><span class="sxs-lookup"><span data-stu-id="e36a0-153">Before you invoke the GET_EMP_DETAILS procedure, you must add the `System.Data` namespace to your code.</span></span>  
  
    ```  
    DataSet[] dataArray;  
    int returnCode;  
  
    try  
    {  
       Console.WriteLine("Calling a stored procedure...");  
       dataArray = client.GET_EMP_DETAILS(10001, out returnCode);  //Invoke the stored procedure  
    }  
    catch (Exception ex)  
    {  
       Console.WriteLine("Exception: " + ex.Message);  
       throw;  
    }  
    Console.WriteLine("The details for the employee with ID '10001' are:");  
    Console.WriteLine("*************************************************");  
  
    foreach (DataSet dataSet in dataArray)  
    {  
       foreach (DataTable tab in dataArray[0].Tables)  
       {  
          foreach (DataRow row in tab.Rows)  
          {  
             for (int i = 0; i < tab.Columns.Count; i++)  
             {  
                Console.WriteLine(row[i]);  
             }  
          }  
       }  
    }  
    Console.WriteLine("*************************************************");  
  
    ```  
  
7.  <span data-ttu-id="e36a0-154">次のスニペット」の説明に従って、クライアントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e36a0-154">Close the client as described in the snippet below:</span></span>  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
8.  <span data-ttu-id="e36a0-155">プロジェクトをビルドし、それを実行します。</span><span class="sxs-lookup"><span data-stu-id="e36a0-155">Build the project and then run it.</span></span> <span data-ttu-id="e36a0-156">Pr するために、従業員の詳細</span><span class="sxs-lookup"><span data-stu-id="e36a0-156">The details for the employee, for which you pr</span></span>
9.  <span data-ttu-id="e36a0-157">ovided では、ID は、コンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e36a0-157">ovided the ID, are displayed on the console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e36a0-158">参照</span><span class="sxs-lookup"><span data-stu-id="e36a0-158">See Also</span></span>  
[<span data-ttu-id="e36a0-159">WCF サービス モデルを使用してアプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="e36a0-159">Develop applications using the WCF Service model</span></span>](develop-sql-applications-using-the-wcf-service-model.md)