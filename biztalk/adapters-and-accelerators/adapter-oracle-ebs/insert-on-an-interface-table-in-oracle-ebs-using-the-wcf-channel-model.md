---
title: WCF チャネル モデルを使用して Oracle E-business Suite のインターフェイス テーブルに対して挿入操作を実行 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8a2e5ee3-552b-40a2-aaa6-5391347f1146
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 703b00adeb373fe66c4a96c324f13f9c3c5ec655
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216738"
---
# <a name="run-an-insert-operation-on-an-interface-table-in-oracle-e-business-suite-using-the-wcf-channel-model"></a><span data-ttu-id="7fded-102">WCF チャネル モデルを使用して Oracle E-business suite のインターフェイス テーブルに対して挿入操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="7fded-102">Run an insert operation on an interface table in Oracle E-Business Suite using the WCF channel model</span></span>
<span data-ttu-id="7fded-103">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite のインターフェイス テーブルに対する Insert、Select、Update、および Delete の操作のセットを検出します。</span><span class="sxs-lookup"><span data-stu-id="7fded-103">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] discovers a set of Insert, Select, Update, and Delete operations on Oracle E-Business Suite interface tables.</span></span> <span data-ttu-id="7fded-104">これらの操作を使用することができますを実行して単純な Insert、Select、Update、Delete ステートメントで修飾して、Where 句は、対象のインターフェイス テーブルにします。</span><span class="sxs-lookup"><span data-stu-id="7fded-104">By using these operations, you can perform simple Insert, Select, Update, and Delete statements qualified by a Where clause on a target interface table.</span></span> <span data-ttu-id="7fded-105">このトピックでは、WCF チャネル モデルを使用してインターフェイス テーブルに対する挿入操作を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7fded-105">This topic provides instructions on how to perform an Insert operation on an interface table using the WCF channel model.</span></span>  
  
 <span data-ttu-id="7fded-106">アダプターがこれらの操作をサポートする方法の詳細については、次を参照してください。[インターフェイス テーブルとのインターフェイス ビューで操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md)です。</span><span class="sxs-lookup"><span data-stu-id="7fded-106">For more information on how the adapter supports these operations, see [Operations on Interface Tables and Interface Views](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md).</span></span> <span data-ttu-id="7fded-107">WCF チャネル モデルを使用して Oracle E-business Suite での操作を実行する方法に関する詳細については、次を参照してください。 [Oracle E-business Suite アダプターで WCF チャネル モデルの概要](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="7fded-107">For more information about how to perform operations on Oracle E-Business Suite using the WCF Channel model, see [Overview of the WCF channel model with the Oracle E-Business Suite adapter](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter.md).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="7fded-108">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="7fded-108">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="7fded-109">このトピックの例では、MS_SAMPLE_EMPLOYEE インターフェイス テーブルでの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="7fded-109">The example in this topic performs operations on the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="7fded-110">サンプルに用意されているスクリプトを実行して、テーブルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="7fded-110">The table is created by running the script provided with the samples.</span></span> <span data-ttu-id="7fded-111">サンプルの詳細については、次を参照してください。 [Oracle EBS アダプター用のサンプル](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="7fded-111">For more information about samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="7fded-112">サンプルは、 **InsertOperation**、これは、このトピックの内容に基づいても付属、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サンプルです。</span><span class="sxs-lookup"><span data-stu-id="7fded-112">A sample, **InsertOperation**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  
  
## <a name="the-insert-message"></a><span data-ttu-id="7fded-113">挿入メッセージ</span><span class="sxs-lookup"><span data-stu-id="7fded-113">The Insert Message</span></span>  
 <span data-ttu-id="7fded-114">WCF チャネル モデルを使用して Oracle E-business Suite での操作を実行するには、操作に固有の要求メッセージが必要です。</span><span class="sxs-lookup"><span data-stu-id="7fded-114">To perform operations on the Oracle E-Business Suite using the WCF channel model, you must have the request message specific to the operation.</span></span> <span data-ttu-id="7fded-115">MS_SAMPLE_EMPLOYEE インターフェイス テーブルに対する挿入操作を実行する要求メッセージには、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="7fded-115">The request message to perform an Insert operation on the MS_SAMPLE_EMPLOYEE interface table resembles the following:</span></span>  
  
```  
<Insert xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE_EMPLOYEE">  
  <RECORDSET>  
    <InsertRecord xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/TableViewRecord/APPS/MS_SAMPLE_EMPLOYEE">  
      <EMP_NO>10050</EMP_NO>  
      <NAME>John Smith</NAME>  
      <DESIGNATION>Manager</DESIGNATION>  
      <SALARY>500000</SALARY>  
      <JOIN_DATE>1999-05-31</JOIN_DATE>  
    </InsertRecord>  
  </RECORDSET>  
</Insert>  
```  
  
 <span data-ttu-id="7fded-116">この要求メッセージは、次の詳細情報を持つレコードを挿入します。</span><span class="sxs-lookup"><span data-stu-id="7fded-116">This request message inserts a record with following details:</span></span>  
  
```  
Employee Number = 10050  
Name = Tom Smith  
Designation = Manager  
Salary = 500000  
```  
  
 <span data-ttu-id="7fded-117">例: InsertRequest.xml ファイルにメッセージをコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fded-117">You must copy the message to a file, e.g. InsertRequest.xml.</span></span> <span data-ttu-id="7fded-118">このファイルは、Oracle E-business Suite を使用する要求メッセージを送信するこの例では使用、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="7fded-118">This file is used in this example to send the request message to Oracle E-Business Suite using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="7fded-119">テーブルに対する操作のメッセージ スキーマの詳細については、次を参照してください。 [Insert、Update、Delete、および選択操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md)です。</span><span class="sxs-lookup"><span data-stu-id="7fded-119">For more information about the message schema for operations on table, see [Message Schemas for Insert, Update, Delete, and Select Operations](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md).</span></span>  
  
## <a name="creating-a-wcf-channel-application"></a><span data-ttu-id="7fded-120">WCF チャネル アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="7fded-120">Creating a WCF Channel Application</span></span>  
 <span data-ttu-id="7fded-121">このセクションでは、MS_SAMPLE_EMPLOYEE インターフェイス テーブルに対して挿入操作を実行する WCF チャネル アプリケーションを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7fded-121">This section provides instructions on how to create a WCF channel application to perform an Insert operation on the MS_SAMPLE_EMPLOYEE interface table.</span></span>  
  
#### <a name="to-create-a-wcf-channel-application-for-inserting-records-into-the-table"></a><span data-ttu-id="7fded-122">テーブルにレコードを挿入するための WCF チャネル アプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="7fded-122">To create a WCF channel application for inserting records into the table</span></span>  
  
1.  <span data-ttu-id="7fded-123">Visual Studio で Visual c# プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="7fded-123">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="7fded-124">このトピックでは、コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="7fded-124">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="7fded-125">ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.OracleEBS`、 `Microsoft.ServiceModel.Channels`、 `System.ServiceModel`、および`System.Runtime.Serialization`です。</span><span class="sxs-lookup"><span data-stu-id="7fded-125">In the Solution Explorer, add reference to `Microsoft.Adapters.OracleEBS`, `Microsoft.ServiceModel.Channels`, `System.ServiceModel`, and `System.Runtime.Serialization`.</span></span>  
  
3.  <span data-ttu-id="7fded-126">Program.cs ファイルを開き、次の名前空間を追加します。</span><span class="sxs-lookup"><span data-stu-id="7fded-126">Open the Program.cs file and add the following namespaces:</span></span>  
  
    -   `Microsoft.Adapters.OracleEBS`  
  
    -   `Microsoft.ServiceModel.Channels`  
  
    -   `System.ServiceModel`  
  
    -   `System.ServiceModel.Channels`  
  
    -   `System.Xml`  
  
4.  <span data-ttu-id="7fded-127">バインドとエンドポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="7fded-127">Create the binding and endpoint.</span></span>  
  
    ```  
    OracleEBSBinding binding = new OracleEBSBinding();  
    EndpointAddress address = new EndpointAddress("oracleebs://ebs_instance_name");  
  
    ```  
  
5.  <span data-ttu-id="7fded-128">インターフェイス テーブルに対する操作を実行しているため、アプリケーションのコンテキストを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fded-128">Because you are performing an operation on an interface table, you must set the application context.</span></span> <span data-ttu-id="7fded-129">この例では、アプリケーションのコンテキストを設定するを指定する、 **OracleUserName**、 **OraclePassword**、および**OracleEBSResponsibilityName**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="7fded-129">In this example, to set the application context, you specify the **OracleUserName**, **OraclePassword**, and **OracleEBSResponsibilityName** binding properties.</span></span> <span data-ttu-id="7fded-130">アプリケーション コンテキストの詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。</span><span class="sxs-lookup"><span data-stu-id="7fded-130">For more information about application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
    ```  
    binding.OracleUserName = "myOracleEBSUserName";  
    binding.OraclePassword = "myOracleEBSPassword";  
    binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
    ```  
  
6.  <span data-ttu-id="7fded-131">作成し、チャネル ファクトリを開きます。</span><span class="sxs-lookup"><span data-stu-id="7fded-131">Create and open the channel factory.</span></span> <span data-ttu-id="7fded-132">このアプリケーションは、Oracle E-business Suite に要求メッセージを送信し、応答を受信する、そのため、IRequestChannel インターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fded-132">This application sends request message to Oracle E-Business Suite and receives a response, hence you must implement the IRequestChannel interface.</span></span>  
  
    ```  
    ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
    factory.Credentials.UserName.UserName = "<Enter user name here>";  
    factory.Credentials.UserName.Password = "<Enter password here>";  
    factory.Open();  
    ```  
  
7.  <span data-ttu-id="7fded-133">作成し、チャネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7fded-133">Create and open the channel.</span></span>  
  
    ```  
    IRequestChannel channel;  
    try  
    {  
       channel = factory.CreateChannel();  
       channel.Open();  
    }  
    catch (Exception ex)  
    {  
       Console.WriteLine("Exception :" + ex.Message);  
       throw;  
    }  
    ```  
  
8.  <span data-ttu-id="7fded-134">作成し、要求メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="7fded-134">Create and send the request message.</span></span>  
  
    ```  
    XmlReader readerIn;  
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
    Message messageIn;  
    Message messageOut;  
    try  
    {  
       messageIn = Message.CreateMessage(MessageVersion.Default, "InterfaceTables/Insert/FND/APPS/MS_SAMPLE_EMPLOYEE", readerIn);  
       messageOut = channel.Request(messageIn);  
    }  
    catch (Exception ex)  
    {  
       Console.WriteLine("Exception: " + ex.Message);  
       throw;  
    }  
  
    ```  
  
     <span data-ttu-id="7fded-135">要求メッセージを作成中にインターフェイス テーブルについて、アダプターを実行するアクションを示すメッセージのアクションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fded-135">While creating the request message, you must specify the message action that indicates the action that the adapter performs on the interface table.</span></span> <span data-ttu-id="7fded-136">メッセージのアクションは、MS_SAMPLE_EMPLOYEE テーブルに対して挿入操作を実行する`InterfaceTables/Insert/FND/APPS/MS_SAMPLE_EMPLOYEE`です。</span><span class="sxs-lookup"><span data-stu-id="7fded-136">To perform an Insert operation on the MS_SAMPLE_EMPLOYEE table, the message action is `InterfaceTables/Insert/FND/APPS/MS_SAMPLE_EMPLOYEE`.</span></span> <span data-ttu-id="7fded-137">テーブルに対するさまざまな操作のメッセージのアクションを判断する方法については、次を参照してください。 [Insert、Update、Delete、および選択操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md)です。</span><span class="sxs-lookup"><span data-stu-id="7fded-137">For information about how you can determine the message action for various operations on tables, see [Message Schemas for Insert, Update, Delete, and Select Operations](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md).</span></span>  
  
9. <span data-ttu-id="7fded-138">応答メッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="7fded-138">Get the response message.</span></span>  
  
    ```  
    XmlReader readerOut = messageOut.GetReaderAtBodyContents();  
    XmlDocument doc = new XmlDocument();  
    doc.Load(readerOut);  
    doc.Save("C:\\Response.xml");  
    ```  
  
10. <span data-ttu-id="7fded-139">メッセージ、チャネル、およびチャネル ファクトリを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7fded-139">Close the message, channel, and channel factory.</span></span>  
  
    ```  
    messageOut.Close();  
    channel.Close();  
    factory.Close();  
    ```  
  
11. <span data-ttu-id="7fded-140">プロジェクトをビルドする。</span><span class="sxs-lookup"><span data-stu-id="7fded-140">Build the project.</span></span> <span data-ttu-id="7fded-141">プロジェクトをビルドしたら、InsertRequest.xml、実行可能プロジェクトと同じ場所に、要求メッセージをコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fded-141">After building the project, you must copy the request message, InsertRequest.xml, at the same location as your project executable.</span></span> <span data-ttu-id="7fded-142">通常、この場所は、プロジェクト ディレクトリ下にある \bin\Debug\ です。</span><span class="sxs-lookup"><span data-stu-id="7fded-142">Typically, this location is \bin\Debug\ under your project directory.</span></span>  
  
12. <span data-ttu-id="7fded-143">アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="7fded-143">Run the application.</span></span> <span data-ttu-id="7fded-144">応答メッセージ、Response.xml は、アプリケーションで指定した場所に保存されます。</span><span class="sxs-lookup"><span data-stu-id="7fded-144">The response message, Response.xml, is saved at the location you specified in the application.</span></span> <span data-ttu-id="7fded-145">応答メッセージは、番号または挿入されたレコードが含まれ、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="7fded-145">The response message contains the number or records inserted and resembles the following:</span></span>  
  
    ```  
    <InsertResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE_EMPLOYEE">  
      <InsertResult>1</InsertResult>  
    </InsertResponse>  
    ```  
  
     <span data-ttu-id="7fded-146">値「1」では、1 つのレコードが MS_SAMPLE_EMPLOYEE テーブルに挿入されるを示します。</span><span class="sxs-lookup"><span data-stu-id="7fded-146">The value “1” denotes that a single record is inserted into the MS_SAMPLE_EMPLOYEE table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fded-147">参照</span><span class="sxs-lookup"><span data-stu-id="7fded-147">See Also</span></span>  
 [<span data-ttu-id="7fded-148">WCF チャネル モデルを使用して Oracle E-business Suite アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="7fded-148">Develop Oracle E-Business Suite applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)