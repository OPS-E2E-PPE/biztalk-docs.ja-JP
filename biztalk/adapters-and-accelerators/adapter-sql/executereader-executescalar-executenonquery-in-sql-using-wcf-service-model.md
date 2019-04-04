---
title: WCF サービス モデルを使用して sql ExecuteReader、executescalar、ExecuteNonQuery 操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62f166af-b657-491b-b20d-1ae7886f27ce
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9dd50b3353aac683548f9220c441bef21776a37
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968835"
---
# <a name="executereader-executescalar-or-executenonquery-operations-in-sql-using-wcf-service-model"></a><span data-ttu-id="847e7-102">WCF サービス モデルを使用して sql ExecuteReader、executescalar、ExecuteNonQuery 操作</span><span class="sxs-lookup"><span data-stu-id="847e7-102">ExecuteReader, ExecuteScalar, or ExecuteNonQuery operations in SQL using WCF Service Model</span></span>
<span data-ttu-id="847e7-103">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]など SQL Server の一般的な操作を公開する**ExecuteNonQuery**、 **ExecuteReader**、および**ExecuteScalar**します。</span><span class="sxs-lookup"><span data-stu-id="847e7-103">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] exposes generic SQL Server operations such as **ExecuteNonQuery**, **ExecuteReader**, and **ExecuteScalar**.</span></span> <span data-ttu-id="847e7-104">これらの操作を使用して、SQL Server データベースで任意の SQL ステートメントを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="847e7-104">You can use these operations to execute any SQL statement on a SQL Server database.</span></span> <span data-ttu-id="847e7-105">これらの操作は、応答するための SQL ステートメントの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="847e7-105">These operations differ based on the kind of response you get for the SQL statement.</span></span> <span data-ttu-id="847e7-106">アダプターがこれらの操作をサポートする方法の詳細については、[ExecuteNonQuery、ExecuteReader、ExecuteScalar 操作のサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="847e7-106">For more information about how the adapter supports these operations, see [Support for ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md).</span></span>  

 <span data-ttu-id="847e7-107">このトピックでは、実行する方法を示します、 **ExecuteReader**操作を使用して、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] WCF サービス モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="847e7-107">This topic demonstrates how to perform an **ExecuteReader** operation using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] using the WCF service model.</span></span> <span data-ttu-id="847e7-108">実行するには、このトピックで説明する手順の同じセットを利用できる**ExecuteNonQuery**と**ExecuteScalar**操作。</span><span class="sxs-lookup"><span data-stu-id="847e7-108">You can follow the same set of procedures described in this topic to perform **ExecuteNonQuery** and **ExecuteScalar** operations.</span></span>  

## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="847e7-109">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="847e7-109">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="847e7-110">このトピックの例では、 **ExecuteReader**操作、ADD_EMP_DETAILS を実行するストアド プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="847e7-110">The example in this topic uses the **ExecuteReader** operation to execute the ADD_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="847e7-111">このストアド プロシージャでは、Employee テーブルにレコードを追加し、レコードの従業員 ID を返します。</span><span class="sxs-lookup"><span data-stu-id="847e7-111">This stored procedure adds a record to the Employee table and returns the employee ID for the record.</span></span> <span data-ttu-id="847e7-112">ADD_EMP_DETAILS ストアド プロシージャは、サンプルで提供される SQL スクリプトを実行して作成されます。</span><span class="sxs-lookup"><span data-stu-id="847e7-112">The ADD_EMP_DETAILS stored procedure is created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="847e7-113">サンプルの詳細については、[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="847e7-113">For more information about samples, see [Adapter samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span> <span data-ttu-id="847e7-114">サンプルについては、 **Execute_Reader**、これは、このトピックに基づいてがで提供されていることも、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="847e7-114">A sample, **Execute_Reader**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span>  

## <a name="the-wcf-client-class"></a><span data-ttu-id="847e7-115">WCF クライアント クラス</span><span class="sxs-lookup"><span data-stu-id="847e7-115">The WCF Client Class</span></span>  
 <span data-ttu-id="847e7-116">一般的な操作 (ExecuteNonQuery、ExecuteReader、ExecuteScalar のいずれか) を使用してを呼び出すために生成された WCF クライアントの名前、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次の表に記載されています。</span><span class="sxs-lookup"><span data-stu-id="847e7-116">The name of the WCF client generated for invoking generic operations (ExecuteNonQuery, ExecuteReader, or ExecuteScalar) using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is listed in the following table.</span></span>  

|<span data-ttu-id="847e7-117">操作</span><span class="sxs-lookup"><span data-stu-id="847e7-117">Operations</span></span>|<span data-ttu-id="847e7-118">WCF クライアント名</span><span class="sxs-lookup"><span data-stu-id="847e7-118">WCF Client Name</span></span>|  
|----------------|---------------------|  
|<span data-ttu-id="847e7-119">ExecuteNonQuery、ExecuteReader、ExecuteScalar</span><span class="sxs-lookup"><span data-stu-id="847e7-119">ExecuteNonQuery, ExecuteReader, or ExecuteScalar</span></span>|<span data-ttu-id="847e7-120">GenericTableOpClient</span><span class="sxs-lookup"><span data-stu-id="847e7-120">GenericTableOpClient</span></span>|  

### <a name="method-signature-for-invoking-generic-operations"></a><span data-ttu-id="847e7-121">一般的な操作を呼び出すためのメソッド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="847e7-121">Method Signature for Invoking Generic Operations</span></span>  
 <span data-ttu-id="847e7-122">次の表では、汎用的な操作の呼び出しに公開されるメソッドのシグネチャを示します。</span><span class="sxs-lookup"><span data-stu-id="847e7-122">The following table shows the signature for the method exposed to invoke the generic operations.</span></span>  

|<span data-ttu-id="847e7-123">演算</span><span class="sxs-lookup"><span data-stu-id="847e7-123">Operation</span></span>|<span data-ttu-id="847e7-124">メソッド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="847e7-124">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="847e7-125">ExecuteNonQuery</span><span class="sxs-lookup"><span data-stu-id="847e7-125">ExecuteNonQuery</span></span>|<span data-ttu-id="847e7-126">int ExecuteNonQuery (クエリ文字列)</span><span class="sxs-lookup"><span data-stu-id="847e7-126">int ExecuteNonQuery(string Query)</span></span>|  
|<span data-ttu-id="847e7-127">ExecuteReader</span><span class="sxs-lookup"><span data-stu-id="847e7-127">ExecuteReader</span></span>|<span data-ttu-id="847e7-128">System.Data.DataSet:operator[] ExecuteReader (クエリ文字列)</span><span class="sxs-lookup"><span data-stu-id="847e7-128">System.Data.DataSet[] ExecuteReader(string Query)</span></span>|  
|<span data-ttu-id="847e7-129">ExecuteScalar</span><span class="sxs-lookup"><span data-stu-id="847e7-129">ExecuteScalar</span></span>|<span data-ttu-id="847e7-130">文字列 ExecuteScalar(string Query)</span><span class="sxs-lookup"><span data-stu-id="847e7-130">string ExecuteScalar(string Query)</span></span>|  

 <span data-ttu-id="847e7-131">例として、汎用の操作メソッドのシグネチャを次のコード スニペットに示します。</span><span class="sxs-lookup"><span data-stu-id="847e7-131">As an example, the signature for the generic operation methods is shown in the following code snippet.</span></span>  

```  
public partial class GenericTableOpClient : System.ServiceModel.ClientBase<GenericTableOp>, GenericTableOp {  
  public int ExecuteNonQuery(string Query);  
  public System.Data.DataSet[] ExecuteReader(string Query);  
  public string ExecuteScalar(string Query);  
}  
```  

 <span data-ttu-id="847e7-132">このスニペットで</span><span class="sxs-lookup"><span data-stu-id="847e7-132">In this snippet,</span></span>  

-   <span data-ttu-id="847e7-133">`GenericTableOpClient` クラスの名前です。</span><span class="sxs-lookup"><span data-stu-id="847e7-133">`GenericTableOpClient` is the name of the class.</span></span> <span data-ttu-id="847e7-134">この例では、このクラスを使用する、ExecuteReader、汎用的な操作を呼び出すクライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="847e7-134">In this example, you use this class to create a client to invoke the generic operation, ExecuteReader.</span></span>  

-   <span data-ttu-id="847e7-135">`public System.Data.DataSet[] ExecuteReader(string Query)` ストアド プロシージャを ADD_EMP_DETAILS を起動するには、この例では起動されるメソッドです。</span><span class="sxs-lookup"><span data-stu-id="847e7-135">`public System.Data.DataSet[] ExecuteReader(string Query)` is the method that you invoke in this example to invoke the ADD_EMP_DETAILS stored procedure.</span></span>  

## <a name="creating-a-wcf-client-to-invoke-an-executereader-operation"></a><span data-ttu-id="847e7-136">ExecuteReader 操作を呼び出す、WCF クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="847e7-136">Creating a WCF Client to Invoke an ExecuteReader Operation</span></span>  
 <span data-ttu-id="847e7-137">WCF クライアントを使用して SQL Server で操作の実行に必要なアクションの汎用的なセットは、一連のタスクで説明されている[SQL アダプターを使用した WCF チャネル モデルの概要](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-channel-model-with-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="847e7-137">The generic set of actions required to perform an operation on SQL Server using a WCF client involves a set of tasks described in [Overview of the WCF channel model with the SQL adapter](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-channel-model-with-the-sql-adapter.md).</span></span> <span data-ttu-id="847e7-138">このセクションを起動する WCF クライアントを作成する方法を具体的に説明します、 **ExecuteReader**操作、ADD_EMP_DETAILS を実行するストアド プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="847e7-138">This section specifically describes how to create a WCF client that invokes an **ExecuteReader** operation to execute the ADD_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="847e7-139">このストアド プロシージャは、各サンプルに用意されている SQL スクリプトを実行して作成されます。</span><span class="sxs-lookup"><span data-stu-id="847e7-139">This stored procedure is created by running the SQL script provided with each sample.</span></span>  

#### <a name="to-create-a-wcf-client-to-invoke-executereader-operation"></a><span data-ttu-id="847e7-140">ExecuteReader 操作を呼び出す、WCF クライアントを作成するには</span><span class="sxs-lookup"><span data-stu-id="847e7-140">To create a WCF client to invoke ExecuteReader operation</span></span>  

1. <span data-ttu-id="847e7-141">Visual Studio で Visual c# プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="847e7-141">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="847e7-142">このトピックでは、コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="847e7-142">For this topic, create a console application.</span></span>  

2. <span data-ttu-id="847e7-143">WCF クライアント クラスを生成、 **ExecuteReader**ジェネリック操作。</span><span class="sxs-lookup"><span data-stu-id="847e7-143">Generate the WCF client class for the **ExecuteReader** generic operation.</span></span> <span data-ttu-id="847e7-144">使用して、SQL Server データベースに接続するときに、この操作は、ルート ノードで使用可能な[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="847e7-144">This operation is available under the root node when you connect to the SQL Server database using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="847e7-145">WCF クライアント クラスを生成する詳細については、[SQL Server のアイテムの WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="847e7-145">For more information about generating a WCF client class, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="847e7-146">WCF クライアント クラスを生成する前に必ず設定して、 **EnableBizTalkCompatibilityMode**プロパティを false にバインドします。</span><span class="sxs-lookup"><span data-stu-id="847e7-146">Before generating the WCF client class, make sure you set the **EnableBizTalkCompatibilityMode** binding property to false.</span></span>  

3. <span data-ttu-id="847e7-147">ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.Sql`と`Microsoft.ServiceModel.Channels`します。</span><span class="sxs-lookup"><span data-stu-id="847e7-147">In the Solution Explorer, add reference to `Microsoft.Adapters.Sql` and `Microsoft.ServiceModel.Channels`.</span></span>  

4. <span data-ttu-id="847e7-148">Program.cs ファイルを開き、次のスニペットの説明に従って、クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="847e7-148">Open the Program.cs file and create a client as described in the snippet below.</span></span>  

   ```  

           GenericTableOpClient client = new GenericTableOpClient("SqlAdapterBinding_GenericTableOp");  
   client.ClientCredentials.UserName.UserName = "<Enter username here>";  
   client.ClientCredentials.UserName.Password = "<Enter password here>";  
   ```  

    <span data-ttu-id="847e7-149">このスニペットで`GenericTableOpClient`SqlAdapterBindingClient.cs で定義されている WCF クライアントです。</span><span class="sxs-lookup"><span data-stu-id="847e7-149">In this snippet, `GenericTableOpClient` is the WCF client defined in SqlAdapterBindingClient.cs.</span></span> <span data-ttu-id="847e7-150">このファイルがによって生成された、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="847e7-150">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="847e7-151">`SqlAdapterBinding_GenericTableOp` クライアント エンドポイント構成の名前を指定され、app.config で定義されます。このファイルがによって生成されても、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]バインドのプロパティとその他の構成設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="847e7-151">`SqlAdapterBinding_GenericTableOp` is the name of the client endpoint configuration and is defined in the app.config. This file is also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and contains the binding properties and other configuration settings.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="847e7-152">このスニペットでは、構成ファイルからバインドおよびエンドポイント アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="847e7-152">In this snippet, you use the binding and endpoint address from the configuration file.</span></span> <span data-ttu-id="847e7-153">これらの値は、コードで明示的に指定できます。</span><span class="sxs-lookup"><span data-stu-id="847e7-153">You can also explicitly specify these values in your code.</span></span> <span data-ttu-id="847e7-154">クライアント バインディングを指定する、さまざまな方法の詳細については、[SQL アダプタのクライアントのバインディングを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="847e7-154">For more information on the different ways of specifying client binding, see [Configure a Client Binding for the SQL Adapter](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md).</span></span>  

5. <span data-ttu-id="847e7-155">次のスニペットで説明されているように、クライアントを開きます。</span><span class="sxs-lookup"><span data-stu-id="847e7-155">Open the client as described in the snippet below:</span></span>  

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

6. <span data-ttu-id="847e7-156">呼び出す、 **ExecuteReader** ADD_EMP_DETAILS の操作のストアド プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="847e7-156">Invoke the **ExecuteReader** operation for the ADD_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="847e7-157">追加する必要があります ExecuteReader 操作を呼び出す前に、`System.Data`をコードに名前空間。</span><span class="sxs-lookup"><span data-stu-id="847e7-157">Before you invoke the ExecuteReader operation, you must add the `System.Data` namespace to your code.</span></span>  

   ```  
   string query = "EXEC ADD_EMP_DETAILS 'Tom Smith', 'Manager', 500000";  
   DataSet[] dsArray = client.ExecuteReader(query);  

   Console.WriteLine("Invoking the ADD_EMP_DETAILS stored procedure using ExecuteReader");  
   Console.WriteLine("*****************************************************");  
   foreach (DataSet dataSet in dsArray)  
   {  
      foreach (DataTable tab in dsArray[0].Tables)  
      {  
          foreach (DataRow row in tab.Rows)  
          {  
             for (int i = 0; i < tab.Columns.Count; i++)  
             {  
                Console.WriteLine("The ID for the newly added employee is : " + row[i]);  
             }  
          }  
       }  
   }  
   Console.WriteLine("*****************************************************");  

   ```  

7. <span data-ttu-id="847e7-158">次のスニペットの説明に従って、クライアントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="847e7-158">Close the client as described in the snippet below:</span></span>  

   ```  
   client.Close();  
   Console.WriteLine("Press any key to exit...");  
   Console.ReadLine();  
   ```  

8. <span data-ttu-id="847e7-159">プロジェクトをビルドし、それを実行します。</span><span class="sxs-lookup"><span data-stu-id="847e7-159">Build the project and then run it.</span></span> <span data-ttu-id="847e7-160">新しく挿入された従業員の従業員 ID は、コンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="847e7-160">The employee ID of the newly inserted employee is displayed on the console.</span></span>
