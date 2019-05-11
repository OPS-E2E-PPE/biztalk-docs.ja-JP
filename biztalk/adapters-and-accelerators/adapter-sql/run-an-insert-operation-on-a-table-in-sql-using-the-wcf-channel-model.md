---
title: WCF チャネル モデルを使用した SQL でのテーブルに対する挿入操作の実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3df95d78-3a9c-48c0-81ab-1f3206c5e3f7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0be345ab33e12068b9b5eb52fd75c65ff15361be
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367982"
---
# <a name="run-an-insert-operation-on-a-table-in-sql-using-the-wcf-channel-model"></a><span data-ttu-id="5ad1e-102">WCF チャネル モデルを使用して SQL テーブルで挿入操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-102">Run an Insert Operation on a Table in SQL using the WCF Channel Model</span></span>
<span data-ttu-id="5ad1e-103">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]一連の SQL Server データベースのテーブルおよびビューに対する Insert、Select、Update、および Delete の基本的な操作を検出します。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-103">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] discovers a set of basic Insert, Select, Update, and Delete operations on SQL Server database tables and views.</span></span> <span data-ttu-id="5ad1e-104">これらの操作を使用すると、実行の単純な SQL Insert、Select、Update、および Delete ステートメントで Where 修飾対象のテーブルまたはビューの句。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-104">By using these operations, you can perform simple SQL Insert, Select, Update, and Delete statements qualified by a Where clause on a target table or view.</span></span> <span data-ttu-id="5ad1e-105">このトピックでは、WCF チャネル モデルを使用して SQL Server データベース テーブルに対して挿入操作を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-105">This topic provides instructions on how to perform an Insert operation on a SQL Server database table using the WCF channel model.</span></span>  
  
 <span data-ttu-id="5ad1e-106">アダプターがこれらの操作をサポートする方法の詳細については、次を参照してください。 [Insert、Update、Delete、およびテーブルとビューを SQL アダプターを使用した操作の選択](../../adapters-and-accelerators/adapter-sql/insert-update-delete-and-select-on-tables-and-views-with-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-106">For more information on how the adapter supports these operations, see [Insert, Update, Delete, and Select Operations on Tables and Views with the SQL adapter](../../adapters-and-accelerators/adapter-sql/insert-update-delete-and-select-on-tables-and-views-with-the-sql-adapter.md).</span></span> <span data-ttu-id="5ad1e-107">WCF チャネル モデルを使用して SQL Server での操作を実行する方法の詳細については、次を参照してください。 [SQL アダプターを使用した WCF チャネル モデルの概要](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-channel-model-with-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-107">For more information about how to perform operations on SQL Server using the WCF Channel model, see [Overview of the WCF channel model with the SQL adapter](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-channel-model-with-the-sql-adapter.md).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="5ad1e-108">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="5ad1e-108">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="5ad1e-109">このトピックの例では、Employee テーブルに対する操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-109">The example in this topic performs operations on the Employee table.</span></span> <span data-ttu-id="5ad1e-110">サンプルで提供される SQL スクリプトを実行して、従業員テーブルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-110">The Employee table is created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="5ad1e-111">サンプルの詳細については、次を参照してください。 [SQL アダプタのサンプル](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-111">For more information about samples, see [Samples for the SQL adapter](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).</span></span> <span data-ttu-id="5ad1e-112">サンプルについては、 **EmployeeInsertOp**、これは、このトピックに基づいてがで提供されていることも、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-112">A sample, **EmployeeInsertOp**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span>  
  
## <a name="the-insert-message"></a><span data-ttu-id="5ad1e-113">挿入メッセージ</span><span class="sxs-lookup"><span data-stu-id="5ad1e-113">The Insert Message</span></span>  
 <span data-ttu-id="5ad1e-114">WCF チャネル モデルを使用して SQL Server データベースで操作を実行するには、操作に固有の要求メッセージが必要です。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-114">To perform operations on the SQL Server database using the WCF channel model, you must have the request message specific to the operation.</span></span> <span data-ttu-id="5ad1e-115">SQL Server データベースの Employee テーブルに対して挿入操作を実行する要求メッセージには、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-115">The request message to perform an Insert operation on the Employee table in the SQL Server database resembles the following:</span></span>  
  
```  
<Insert xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
  <Rows>  
    <Employee xmlns="http://schemas.microsoft.com/Sql/2008/05/Types/Tables/dbo">  
      <Name>Tom Smith</Name>  
      <Designation>Manager</Designation>  
      <Salary>500000</Salary>  
   </Employee>  
  </Rows>  
</Insert>  
```  
  
 <span data-ttu-id="5ad1e-116">この要求メッセージは、次の詳細情報を持つレコードを挿入します。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-116">This request message inserts a record with following details:</span></span>  
  
```  
Name = Tom Smith  
Designation = Manager  
Salary = 500000  
```  
  
 <span data-ttu-id="5ad1e-117">メッセージは、InsertRequest.xml など、ファイルをコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-117">You must copy the message to a file, e.g. InsertRequest.xml.</span></span> <span data-ttu-id="5ad1e-118">このファイルは、SQL Server を使用する要求メッセージを送信するこの例で使用されます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-118">This file is used in this example to send the request message to SQL Server using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="5ad1e-119">テーブルに対する操作のメッセージ スキーマの詳細については、次を参照してください。[挿入、更新、削除、およびテーブルおよびビューの選択操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)します。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-119">For more information about the message schema for operations on table, see [Message Schemas for Insert, Update, Delete, and Select Operations on Tables and Views](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md).</span></span>  
  
## <a name="creating-a-wcf-channel-application"></a><span data-ttu-id="5ad1e-120">WCF チャネル アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="5ad1e-120">Creating a WCF Channel Application</span></span>  
 <span data-ttu-id="5ad1e-121">このセクションでは、Employee テーブルに対して挿入操作を実行する WCF チャネル アプリケーションを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-121">This section provides instructions on how to create a WCF channel application to perform an Insert operation on the Employee table.</span></span>  
  
#### <a name="to-create-a-wcf-channel-application-for-inserting-records-into-the-employee-table"></a><span data-ttu-id="5ad1e-122">Employee テーブルにレコードを挿入するための WCF チャネル アプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="5ad1e-122">To create a WCF channel application for inserting records into the Employee table</span></span>  
  
1.  <span data-ttu-id="5ad1e-123">Visual Studio で Visual c# プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-123">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="5ad1e-124">このトピックでは、コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-124">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="5ad1e-125">ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.Sql`、 `Microsoft.ServiceModel.Channels`、 `System.ServiceModel`、および`System.Runtime.Serialization`します。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-125">In the Solution Explorer, add reference to `Microsoft.Adapters.Sql`, `Microsoft.ServiceModel.Channels`, `System.ServiceModel`, and `System.Runtime.Serialization`.</span></span>  
  
3.  <span data-ttu-id="5ad1e-126">Program.cs ファイルを開き、次の名前空間を追加します。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-126">Open the Program.cs file and add the following namespaces:</span></span>  
  
    -   `Microsoft.Adapters.Sql`  
  
    -   `Microsoft.ServiceModel.Channels`  
  
    -   `System.ServiceModel`  
  
    -   `System.ServiceModel.Channels`  
  
    -   `System.Xml`  
  
4.  <span data-ttu-id="5ad1e-127">バインディングとエンドポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-127">Create the binding and endpoint.</span></span>  
  
    ```  
    SqlAdapterBinding binding = new SqlAdapterBinding();  
    EndpointAddress address = new EndpointAddress("mssql://mysqlserver//mydatabase?");  
  
    ```  
  
5.  <span data-ttu-id="5ad1e-128">作成し、チャネル ファクトリを開きます。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-128">Create and open the channel factory.</span></span> <span data-ttu-id="5ad1e-129">このアプリケーションが SQL Server に要求メッセージを送信し、応答を受信、そのため、IRequestChannel インターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-129">This application sends request message to SQL Server and receives a response, hence you must implement the IRequestChannel interface.</span></span>  
  
    ```  
    ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
    factory.Credentials.UserName.UserName = "<Enter user name here>";  
    factory.Credentials.UserName.Password = "<Enter password here>";  
    factory.Open();  
    ```  
  
6.  <span data-ttu-id="5ad1e-130">作成して、チャネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-130">Create and open the channel.</span></span>  
  
    ```  
    IRequestChannel channel = factory.CreateChannel();  
    channel.Open();  
    ```  
  
7.  <span data-ttu-id="5ad1e-131">作成し、要求メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-131">Create and send the request message.</span></span>  
  
    ```  
    XmlReader readerIn;  
    Console.WriteLine("Creating the message");  
    try  
    {  
       readerIn = XmlReader.Create("InsertRequest.xml");  
       Console.WriteLine("Reader created");  
    }  
    catch (Exception ex)  
    {  
       Console.WriteLine("Exception: " + ex.Message);  
       throw;  
    }  
    Message messageIn = Message.CreateMessage(MessageVersion.Default, "TableOp/Insert/dbo/Employee", readerIn);  
    Message messageOut = channel.Request(messageIn);  
  
    ```  
  
     <span data-ttu-id="5ad1e-132">要求メッセージを作成するときに、SQL Server テーブルをアダプターを実行するアクションを示すメッセージのアクションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-132">While creating the request message, you must specify the message action that indicates the action that the adapter performs on the SQL Server table.</span></span> <span data-ttu-id="5ad1e-133">メッセージのアクションは、Employee テーブルに対して挿入操作を実行する`TableOp/Insert/dbo/Employee`します。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-133">To perform an Insert operation on the Employee table, the message action is `TableOp/Insert/dbo/Employee`.</span></span> <span data-ttu-id="5ad1e-134">テーブルに対するさまざまな操作のメッセージ アクションを決定する方法については、次を参照してください。[挿入、更新、削除、およびテーブルおよびビューの選択操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)します。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-134">For information about how you can determine the message action for various operations on tables, see [Message Schemas for Insert, Update, Delete, and Select Operations on Tables and Views](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md).</span></span>  
  
8.  <span data-ttu-id="5ad1e-135">応答メッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-135">Get the response message.</span></span>  
  
    ```  
    XmlReader readerOut = messageOut.GetReaderAtBodyContents();  
    XmlDocument doc = new XmlDocument();  
    doc.Load(readerOut);  
    doc.Save("C:\\Response.xml");  
    ```  
  
9. <span data-ttu-id="5ad1e-136">メッセージ、チャネル、およびチャネル ファクトリを閉じます。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-136">Close the message, channel, and channel factory.</span></span>  
  
    ```  
    messageOut.Close();  
    channel.Close();  
    factory.Close();  
    ```  
  
10. <span data-ttu-id="5ad1e-137">プロジェクトをビルドする。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-137">Build the project.</span></span> <span data-ttu-id="5ad1e-138">プロジェクトをビルドしたら、次のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-138">After building the project, you must perform the following tasks:</span></span>  
  
    -   <span data-ttu-id="5ad1e-139">要求メッセージ、InsertRequest.xml、実行可能ファイル、プロジェクトと同じ場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-139">Copy the request message, InsertRequest.xml, at the same location as your project executable.</span></span> <span data-ttu-id="5ad1e-140">通常、この場所は、プロジェクト ディレクトリ以下に \bin\Debug\ です。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-140">Typically, this location is \bin\Debug\ under your project directory.</span></span>  
  
    -   <span data-ttu-id="5ad1e-141">この例で使用される"Employee"テーブルには、ポイントのユーザー定義型 (UDT) の列があります。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-141">The "Employee" table used in this example has a column of Point user-defined type (UDT).</span></span> <span data-ttu-id="5ad1e-142">そのため、プロジェクトを実行する前に作成する必要がある Point UDT のアセンブリの説明に従って[ユーザー定義型](https://docs.microsoft.com/sql/relational-databases/clr-integration-database-objects-user-defined-types/creating-user-defined-types)します。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-142">So, before running the project, you must create the assembly for the Point UDT as described at [Creating User-Defined Types](https://docs.microsoft.com/sql/relational-databases/clr-integration-database-objects-user-defined-types/creating-user-defined-types).</span></span> <span data-ttu-id="5ad1e-143">DLL プロジェクトの実行可能ファイルと同じ場所にあるアセンブリをコピーすることも必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-143">You must also copy the assembly DLL at the same location as the project executable.</span></span> <span data-ttu-id="5ad1e-144">通常、この場所は、プロジェクト ディレクトリ以下に \bin\Debug\ です。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-144">Typically, this location is \bin\Debug\ under your project directory.</span></span>  
  
11. <span data-ttu-id="5ad1e-145">アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-145">Run the application.</span></span> <span data-ttu-id="5ad1e-146">Response.xml、応答メッセージは、アプリケーションで指定した場所に保存されます。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-146">The response message, Response.xml, is saved at the location you specified in the application.</span></span> <span data-ttu-id="5ad1e-147">応答メッセージは、新しく追加された従業員の ID を格納し、次のような。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-147">The response message contains the ID of the newly added employee and resembles the following:</span></span>  
  
    ```  
    <InsertResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
      <InsertResult>  
        <long xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">10006</long>  
      </InsertResult>  
    </InsertResponse>  
    ```  
  
     <span data-ttu-id="5ad1e-148">Employee テーブルには、id 列として Employee_ID 列があるために、挿入操作は、新しく挿入されたレコードの id 列の値を返します。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-148">Because the Employee table has the Employee_ID column as the identity column, the Insert operation returns the value for the identity column of the newly inserted record.</span></span> <span data-ttu-id="5ad1e-149">テーブル内に id 列がない場合、戻り値は NULL です。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-149">If there is no identity column in a table, the return value is NULL.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ad1e-150">参照</span><span class="sxs-lookup"><span data-stu-id="5ad1e-150">See Also</span></span>  
[<span data-ttu-id="5ad1e-151">WCF チャネル モデルを使用して SQL アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="5ad1e-151">Develop SQL applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)