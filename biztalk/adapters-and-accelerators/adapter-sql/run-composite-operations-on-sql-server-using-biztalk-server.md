---
title: BizTalk Server を使用して SQL Server での複合操作の実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 86fd2aa1-20c7-4b58-9f35-83ba0c959cf1
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a229918f677c3cd0949a961d3fc12c5ad92705e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367966"
---
# <a name="run-composite-operations-on-sql-server-using-biztalk-server"></a><span data-ttu-id="50c66-102">BizTalk Server を使用して SQL Server での複合操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="50c66-102">Run composite operations on SQL Server using BizTalk Server</span></span>
<span data-ttu-id="50c66-103">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]アダプター クライアントが SQL Server データベースでの複合操作を実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="50c66-103">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] enables adapter clients to perform composite operations on the SQL Server database.</span></span> <span data-ttu-id="50c66-104">複合操作を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="50c66-104">A composite operation can include:</span></span>  
  
- <span data-ttu-id="50c66-105">挿入、更新、および削除操作です。</span><span class="sxs-lookup"><span data-stu-id="50c66-105">Insert, Update, and Delete operations.</span></span> <span data-ttu-id="50c66-106">選択操作は複合操作の一部としてサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="50c66-106">A Select operation is not supported as part of a composite operation.</span></span>  
  
- <span data-ttu-id="50c66-107">ストアド プロシージャの操作として実行します。</span><span class="sxs-lookup"><span data-stu-id="50c66-107">Stored procedures executed as operations.</span></span>  
  
  <span data-ttu-id="50c66-108">1 つの複合操作では、任意の順序でこれらの操作の任意の数を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="50c66-108">A single composite operation can have any number of these operations, in any order.</span></span> <span data-ttu-id="50c66-109">たとえば、2 つの挿入操作の後に、削除操作と最後に、ストアド プロシージャの実行することができます。</span><span class="sxs-lookup"><span data-stu-id="50c66-109">For example, you can have two Insert operations followed by a Delete operation, and finally a stored procedure execution.</span></span> <span data-ttu-id="50c66-110">また、さまざまなオペレーションを別のデータベース テーブルまたはビューを対象とすることができます。</span><span class="sxs-lookup"><span data-stu-id="50c66-110">Also, you can have different operations targeting different database tables or views.</span></span> <span data-ttu-id="50c66-111">アダプターが複合操作をサポートする方法の詳細については、次を参照してください。[複合操作の実行、SQL アダプターを使用して SQL Server で](../../adapters-and-accelerators/adapter-sql/run-composite-operations-in-sql-server-using-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="50c66-111">For more information about how the adapter supports composite operations, see [Run composite operations in SQL Server using the SQL adapter](../../adapters-and-accelerators/adapter-sql/run-composite-operations-in-sql-server-using-the-sql-adapter.md).</span></span> <span data-ttu-id="50c66-112">複合操作の SOAP メッセージの構造については、次を参照してください。[複合操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md)します。</span><span class="sxs-lookup"><span data-stu-id="50c66-112">For information about the structure of the SOAP message for composite operations, see [Message Schemas for Composite Operations](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="50c66-113">ユーザー定義型の列を含むテーブルに対して操作を実行している場合ことを確認するを参照してください[テーブルと、SQL アダプターを使用してユーザー定義型を持つビューで操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)アプリケーションの開発を開始する前にします。</span><span class="sxs-lookup"><span data-stu-id="50c66-113">If you are performing operation on tables that have columns of user-defined types, make sure you refer to [Operations on Tables and Views with User-Defined Types using the SQL adapter](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md) before you start developing your application.</span></span>  
  
## <a name="how-to-perform-composite-operations-on-sql-server"></a><span data-ttu-id="50c66-114">SQL Server での複合操作を実行する方法</span><span class="sxs-lookup"><span data-stu-id="50c66-114">How to Perform Composite Operations on SQL Server</span></span>  
 <span data-ttu-id="50c66-115">SQL Server を使用して、操作を実行する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明されている手順のタスクが含まれます[SQL アダプターを使用した BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="50c66-115">Performing an operation on SQL Server using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] involves procedural tasks described in [Building blocks to develop BizTalk applications with the SQL adapter](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md).</span></span> <span data-ttu-id="50c66-116">これらのタスクは SQL Server データベースでの複合操作を行うには。</span><span class="sxs-lookup"><span data-stu-id="50c66-116">To perform composite operations on the SQL Server database, these tasks are:</span></span>  
  
1. <span data-ttu-id="50c66-117">BizTalk プロジェクトを作成し、呼び出すすべての操作のスキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="50c66-117">Create a BizTalk project, and generate schema for all the operations you want to invoke.</span></span>  
  
2. <span data-ttu-id="50c66-118">前の手順で生成したすべてのスキーマへの参照が含まれるスキーマ ファイルを手動で作成します。</span><span class="sxs-lookup"><span data-stu-id="50c66-118">Manually create a schema file that includes references to all the schemas you generated in the previous step.</span></span>  
  
3. <span data-ttu-id="50c66-119">SQL Server データベースからメッセージを送受信するための BizTalk プロジェクトでは、メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="50c66-119">Create messages in the BizTalk project for sending and receiving messages from the SQL Server database.</span></span> <span data-ttu-id="50c66-120">これらのメッセージは、前の手順で作成した要求と応答のスキーマに準拠する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50c66-120">These messages must conform to the request and response schema you created in the previous step.</span></span>  
  
4. <span data-ttu-id="50c66-121">SQL Server データベースでの複合操作を呼び出すオーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="50c66-121">Create an orchestration to invoke the composite operation on the SQL Server database.</span></span>  
  
5. <span data-ttu-id="50c66-122">ビルドし、BizTalk プロジェクトを配置します。</span><span class="sxs-lookup"><span data-stu-id="50c66-122">Build and deploy the BizTalk project.</span></span>  
  
6. <span data-ttu-id="50c66-123">BizTalk 物理を作成してアプリケーションの送信および受信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="50c66-123">Configure the BizTalk application by creating physical send and receive ports.</span></span>  
  
7. <span data-ttu-id="50c66-124">BizTalk アプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="50c66-124">Start the BizTalk application.</span></span>  
  
   <span data-ttu-id="50c66-125">このトピックでは、これらのタスクを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="50c66-125">This topic provides instructions on how to perform these tasks.</span></span>  
  
## <a name="sample-based-on-this-topic"></a><span data-ttu-id="50c66-126">このトピックに基づくサンプル</span><span class="sxs-lookup"><span data-stu-id="50c66-126">Sample Based on This Topic</span></span>  
 <span data-ttu-id="50c66-127">サンプル CompositeOperations、このトピックの「に基づいてが付属、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="50c66-127">A sample, CompositeOperations, based on this topic is provided with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="50c66-128">詳細については、次を参照してください。 [SQL アダプタのサンプル](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="50c66-128">For more information, see [Samples for the SQL adapter](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).</span></span>  
  
## <a name="generating-schema"></a><span data-ttu-id="50c66-129">スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="50c66-129">Generating Schema</span></span>  
 <span data-ttu-id="50c66-130">このトピックで、複合操作を実行する方法を示す、次のタスクで実行されます指定された順序。</span><span class="sxs-lookup"><span data-stu-id="50c66-130">In this topic, to demonstrate how to perform composite operations, the following tasks will be performed in the order specified:</span></span>  
  
- <span data-ttu-id="50c66-131">EMPLOYEE テーブルにレコードを挿入します。</span><span class="sxs-lookup"><span data-stu-id="50c66-131">Insert record into the EMPLOYEE table.</span></span>  
  
- <span data-ttu-id="50c66-132">GET_LAST_EMP_DATA ストアド プロシージャを呼び出すことによって、挿入された最後のレコードのすべての列を取得します。</span><span class="sxs-lookup"><span data-stu-id="50c66-132">Retrieve all the columns for the last inserted record by invoking the GET_LAST_EMP_DATA stored procedure.</span></span>  
  
- <span data-ttu-id="50c66-133">EMPLOYEE テーブルからレコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="50c66-133">Delete the record from the EMPLOYEE table.</span></span>  
  
  <span data-ttu-id="50c66-134">EMPLOYEE テーブルを作成するサンプルに付属のスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="50c66-134">Run the scripts provided with the samples to create the EMPLOYEE table.</span></span> <span data-ttu-id="50c66-135">サンプルの詳細については、次を参照してください。[スキーマのサンプル](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="50c66-135">For more information about the samples, see [Schema Samples](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md).</span></span>  
  
  <span data-ttu-id="50c66-136">BizTalk プロジェクトを作成して使用する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]これらの操作のスキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="50c66-136">You must create a BizTalk project and use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] to generate the schema for these operations.</span></span> <span data-ttu-id="50c66-137">参照してください[SQL アダプターを使用して Visual Studio での SQL Server 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)スキーマを生成する方法についての詳細。</span><span class="sxs-lookup"><span data-stu-id="50c66-137">See [Retrieving Metadata for SQL Server Operations in Visual Studio using the SQL adapter](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md) for more information about how to generate schemas.</span></span>  
  
## <a name="creating-a-composite-schema-definition"></a><span data-ttu-id="50c66-138">複合のスキーマ定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="50c66-138">Creating a Composite Schema Definition</span></span>  
 <span data-ttu-id="50c66-139">個々 の操作用に作成したスキーマを参照する複合スキーマを作成する必要がありますようになりました。</span><span class="sxs-lookup"><span data-stu-id="50c66-139">You must now create a composite schema that references the schemas you created for the individual operations.</span></span> <span data-ttu-id="50c66-140">複合のスキーマ定義を作成する次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="50c66-140">Perform the following steps to create a composite schema definition.</span></span>  
  
#### <a name="to-add-a-composite-schema-definition"></a><span data-ttu-id="50c66-141">複合のスキーマ定義を追加するには</span><span class="sxs-lookup"><span data-stu-id="50c66-141">To add a composite schema definition</span></span>  
  
1. <span data-ttu-id="50c66-142">スキーマ ファイルを BizTalk プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="50c66-142">Add a schema file to the BizTalk project.</span></span> <span data-ttu-id="50c66-143">プロジェクト名を右クリックし、[**追加**、] をクリックし、**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="50c66-143">Right-click the project name, point to **Add**, and then click **New Item**.</span></span> <span data-ttu-id="50c66-144">**新しい項目の追加**] ダイアログ ボックスから、**カテゴリ**ボックスで、[**スキーマ ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="50c66-144">In the **Add New Item** dialog box, from the **Categories** box, click **Schema Files**.</span></span> <span data-ttu-id="50c66-145">**テンプレート**ボックスで、**スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="50c66-145">From the **Templates** box, click **Schema**.</span></span> <span data-ttu-id="50c66-146">スキーマ ファイルの名前を指定し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="50c66-146">Specify a name for the schema file, and then click **OK**.</span></span>  
  
    <span data-ttu-id="50c66-147">この例で、スキーマ ファイル名を指定`CompositeSchema.xsd`します。</span><span class="sxs-lookup"><span data-stu-id="50c66-147">For this example, specify the schema file name as `CompositeSchema.xsd`.</span></span>  
  
2. <span data-ttu-id="50c66-148">実行するさまざまな操作の生成スキーマへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="50c66-148">Add references to the schema generated for the different operations that you want to perform.</span></span> <span data-ttu-id="50c66-149">この例では、操作に対して生成されたさまざまなスキーマは。</span><span class="sxs-lookup"><span data-stu-id="50c66-149">In this example, the different schemas generated for operations are:</span></span>  
  
   - <span data-ttu-id="50c66-150">TableOperation.dbo.Employee.xsd、挿入または削除操作です。</span><span class="sxs-lookup"><span data-stu-id="50c66-150">TableOperation.dbo.Employee.xsd, for Insert and Delete operations.</span></span>  
  
   - <span data-ttu-id="50c66-151">Procedure.dbo.xsd、GET_LAST_EMP_DATA のストアド プロシージャをします。</span><span class="sxs-lookup"><span data-stu-id="50c66-151">Procedure.dbo.xsd, for the GET_LAST_EMP_DATA stored procedure.</span></span>  
  
     <span data-ttu-id="50c66-152">参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="50c66-152">To add references:</span></span>  
  
   1.  <span data-ttu-id="50c66-153">ルートを右クリックして**\<スキーマ\>** CompositeSchema.xsd をクリックしますノード**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="50c66-153">Right-click the root **\<Schema\>** node in the CompositeSchema.xsd, and click **Properties**.</span></span>  
  
   2.  <span data-ttu-id="50c66-154">**プロパティ**ボックスで、省略記号ボタンをクリックします **([...])。** に対して、 **Imports**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="50c66-154">In the **Property** box, click the ellipsis button **(…)** against the **Imports** property.</span></span>  
  
        <span data-ttu-id="50c66-155">![スキーマの定義をインポート](../../adapters-and-accelerators/adapter-oracle-database/media/d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca.gif "d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca")</span><span class="sxs-lookup"><span data-stu-id="50c66-155">![Import schema definitions](../../adapters-and-accelerators/adapter-oracle-database/media/d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca.gif "d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca")</span></span>  
  
   3.  <span data-ttu-id="50c66-156">**インポート**] ダイアログ ボックスから、**として新しいスキーマのインポート**一覧で、[ **XSD のインポート**、順にクリックします**追加**します。</span><span class="sxs-lookup"><span data-stu-id="50c66-156">In the **Imports** dialog box, from the **Import new schema as** list, select **XSD Import**, and then click **Add**.</span></span>  
  
   4.  <span data-ttu-id="50c66-157">**BizTalk 型の選択** ダイアログ ボックスで、BizTalk プロジェクト名のノードを展開し、展開**スキーマ**、しをインポートするスキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="50c66-157">In the **BizTalk Type Picker** dialog box, expand the BizTalk project name node, expand **Schemas**, and then select the schema you want to import.</span></span> <span data-ttu-id="50c66-158">この例では、< BizTalk_project_name > を選択します。TableOperation_dbo_Employee します。</span><span class="sxs-lookup"><span data-stu-id="50c66-158">For this example, select <BizTalk_project_name>.TableOperation_dbo_Employee.</span></span> <span data-ttu-id="50c66-159">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50c66-159">Click **OK**.</span></span>  
  
        <span data-ttu-id="50c66-160">< BizTalk_project_name > をインポートするには、この手順を繰り返します。Procedure_dbo すぎます。</span><span class="sxs-lookup"><span data-stu-id="50c66-160">Repeat this step to import <BizTalk_project_name>.Procedure_dbo too.</span></span>  
  
   5.  <span data-ttu-id="50c66-161">**インポート**ダイアログ ボックスで、をクリックして**OK**。</span><span class="sxs-lookup"><span data-stu-id="50c66-161">In the **Imports** dialog box, click **OK**.</span></span>  
  
3. <span data-ttu-id="50c66-162">ルート スキーマ ノードには、2 つの子ノードを追加します。</span><span class="sxs-lookup"><span data-stu-id="50c66-162">Add two child nodes to the root schema node.</span></span> <span data-ttu-id="50c66-163">1 つの子ノードは、複合操作を実行するための要求スキーマに対応します。</span><span class="sxs-lookup"><span data-stu-id="50c66-163">One child node corresponds to the request schema for performing the composite operation.</span></span> <span data-ttu-id="50c66-164">その他の子ノードは、応答スキーマに対応します。</span><span class="sxs-lookup"><span data-stu-id="50c66-164">The other child node corresponds to the response schema.</span></span> <span data-ttu-id="50c66-165">要求スキーマに対応するノードは、任意の名前を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="50c66-165">The node that corresponds to the request schema can have any name.</span></span> <span data-ttu-id="50c66-166">応答スキーマに対応するノードには、< request_schema_node > 応答を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="50c66-166">The node that corresponds to the response schema must be called <request_schema_node>Response.</span></span> <span data-ttu-id="50c66-167">この例では、要求スキーマのノードとしてを呼び出し、**要求**します。</span><span class="sxs-lookup"><span data-stu-id="50c66-167">For this example, we will call the request schema node as **Request**.</span></span> <span data-ttu-id="50c66-168">そのため、応答スキーマのノードと呼びます**RequestResponse**します。</span><span class="sxs-lookup"><span data-stu-id="50c66-168">So, the response schema node is called **RequestResponse**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="50c66-169">既定で、**ルート**ノードは、新しいスキーマ ファイルにも追加されます。</span><span class="sxs-lookup"><span data-stu-id="50c66-169">By default, a **Root** node is also added to a new schema file.</span></span> <span data-ttu-id="50c66-170">名前を変更することができます、**ルート**ノード**要求**します。</span><span class="sxs-lookup"><span data-stu-id="50c66-170">You can rename the **Root** node to **Request**.</span></span> <span data-ttu-id="50c66-171">ノードの名前を変更するノード名を右クリックし、をクリックして**の名前を変更**します。</span><span class="sxs-lookup"><span data-stu-id="50c66-171">To rename a node, right-click the node name and click **Rename**.</span></span>  
  
    <span data-ttu-id="50c66-172">下のノードを追加する、 **\<スキーマ\>** ノード。</span><span class="sxs-lookup"><span data-stu-id="50c66-172">To add a node under the **\<Schema\>** node:</span></span>  
  
   1.  <span data-ttu-id="50c66-173">右クリックし、 **\<スキーマ\>** に**スキーマ ノードの挿入**、 をクリック**子レコード**します。</span><span class="sxs-lookup"><span data-stu-id="50c66-173">Right-click the **\<Schema\>** node, point to **Insert Schema Node**, and click **Child Record**.</span></span>  
  
   2.  <span data-ttu-id="50c66-174">新しいノードの名前を変更**RequestResponse**します。</span><span class="sxs-lookup"><span data-stu-id="50c66-174">Rename the new node to **RequestResponse**.</span></span>  
  
4. <span data-ttu-id="50c66-175">下の子ノードを追加、**要求**複合操作の一部として実行する各操作の要求スキーマに対応するノード。</span><span class="sxs-lookup"><span data-stu-id="50c66-175">Add child nodes under the **Request** node that correspond to the request schema for each operation that you will perform as part of the composite operation.</span></span> <span data-ttu-id="50c66-176">この例では、次に対応する子ノードを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50c66-176">For this example, you must add child nodes corresponding to the following:</span></span>  
  
   -   <span data-ttu-id="50c66-177">挿入し、EMPLOYEE テーブルに対する操作を削除します。</span><span class="sxs-lookup"><span data-stu-id="50c66-177">Insert and Delete operations on the EMPLOYEE table.</span></span>  
  
   -   <span data-ttu-id="50c66-178">GET_LAST_EMP_DATA はストアド プロシージャです。</span><span class="sxs-lookup"><span data-stu-id="50c66-178">GET_LAST_EMP_DATA stored procedure.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="50c66-179">操作を実行するのと同じ順序でノードを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50c66-179">You must add the nodes in the same order in which you want to perform the operations.</span></span> <span data-ttu-id="50c66-180">など、レコードを挿入し、ストアド プロシージャを実行し、挿入操作のノードを追加する必要があります最初のレコードを削除する場合は、後に、ストアド プロシージャのノードと最後に、削除操作のノード。</span><span class="sxs-lookup"><span data-stu-id="50c66-180">For example, if you want to insert a record, then execute a stored procedure, and then delete a record you must first add a node for the Insert operation, followed by a node for the stored procedure, and finally a node for the Delete operation.</span></span>  
  
    <span data-ttu-id="50c66-181">子ノードを追加する、**要求**ノード。</span><span class="sxs-lookup"><span data-stu-id="50c66-181">To add child nodes to the **Request** node:</span></span>  
  
   1.  <span data-ttu-id="50c66-182">右クリックし、**要求**に**スキーマ ノードの挿入**、 をクリックし、**子レコード**します。</span><span class="sxs-lookup"><span data-stu-id="50c66-182">Right-click the **Request** node, point to **Insert Schema Node**, and then click  **Child Record**.</span></span>  
  
        <span data-ttu-id="50c66-183">![スキーマの子ノードの挿入](../../adapters-and-accelerators/adapter-oracle-database/media/58992131-13a6-45c3-9513-5c0995091fae.gif "58992131-13a6-45c3-9513-5c0995091fae")</span><span class="sxs-lookup"><span data-stu-id="50c66-183">![Insert child nodes for a schema](../../adapters-and-accelerators/adapter-oracle-database/media/58992131-13a6-45c3-9513-5c0995091fae.gif "58992131-13a6-45c3-9513-5c0995091fae")</span></span>  
  
   2.  <span data-ttu-id="50c66-184">複合操作の一環として実行する操作の要求スキーマに対応するレコードの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="50c66-184">Rename the record to correspond to a request schema for an operation that you perform as part of the composite operation.</span></span> <span data-ttu-id="50c66-185">たとえば、"Insert"するノードの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="50c66-185">For example, rename the node to “Insert”.</span></span>  
  
   3.  <span data-ttu-id="50c66-186">マップ、**挿入**EMPLOYEE テーブルに対する挿入操作の要求スキーマのノード。</span><span class="sxs-lookup"><span data-stu-id="50c66-186">Map the **Insert** node to the request schema for the Insert operation on the EMPLOYEE table.</span></span> <span data-ttu-id="50c66-187">これを行うを右クリックし、**挿入**ノード、およびクリック**プロパティ**。</span><span class="sxs-lookup"><span data-stu-id="50c66-187">To do so, right-click the **Insert** node, and click **Properties**.</span></span> <span data-ttu-id="50c66-188">**プロパティ**] ボックスから、 **Data Structure Type**一覧で、[ **Insert (リファレンス)** します。</span><span class="sxs-lookup"><span data-stu-id="50c66-188">In the **Properties** box, from the **Data Structure Type** list, select **Insert (Reference)**.</span></span>  
  
        <span data-ttu-id="50c66-189">![要求スキーマに子ノードをマップ](../../adapters-and-accelerators/adapter-sql/media/5ace18be-0fe8-44c6-bd2f-cb19035494b5.gif "5ace18be-0fe8-44c6-bd2f-cb19035494b5")</span><span class="sxs-lookup"><span data-stu-id="50c66-189">![Map child nodes to the request schema](../../adapters-and-accelerators/adapter-sql/media/5ace18be-0fe8-44c6-bd2f-cb19035494b5.gif "5ace18be-0fe8-44c6-bd2f-cb19035494b5")</span></span>  
  
   4.  <span data-ttu-id="50c66-190">GET_LAST_EMP_DATA ストアド プロシージャと削除操作の要求スキーマのノードを追加するには、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="50c66-190">Repeat these steps to add nodes for the request schemas for GET_LAST_EMP_DATA stored procedure and the Delete operation.</span></span> <span data-ttu-id="50c66-191">ノード名を指定し、次の表で説明したように、それらを対応するスキーマにマップします。</span><span class="sxs-lookup"><span data-stu-id="50c66-191">Specify the node names and map them to the corresponding schema as mentioned in the following table.</span></span>  
  
       |<span data-ttu-id="50c66-192">ノード名</span><span class="sxs-lookup"><span data-stu-id="50c66-192">Node name</span></span>|<span data-ttu-id="50c66-193">スキーマにマップ</span><span class="sxs-lookup"><span data-stu-id="50c66-193">Mapped to schema</span></span>|  
       |---------------|----------------------|  
       |<span data-ttu-id="50c66-194">GET_LAST_EMP_DATA</span><span class="sxs-lookup"><span data-stu-id="50c66-194">GET_LAST_EMP_DATA</span></span>|<span data-ttu-id="50c66-195">GET_LAST_EMP_DATA (リファレンス)</span><span class="sxs-lookup"><span data-stu-id="50c66-195">GET_LAST_EMP_DATA (Reference)</span></span>|  
       |<span data-ttu-id="50c66-196">DELETE</span><span class="sxs-lookup"><span data-stu-id="50c66-196">Delete</span></span>|<span data-ttu-id="50c66-197">削除 (リファレンス)</span><span class="sxs-lookup"><span data-stu-id="50c66-197">Delete (Reference)</span></span>|  
  
5. <span data-ttu-id="50c66-198">下の子ノードを追加、 **RequestResponse**複合操作の一部として実行する各操作の応答スキーマに対応するノード。</span><span class="sxs-lookup"><span data-stu-id="50c66-198">Add child nodes under the **RequestResponse** node that correspond to the response schema for each operation that you will perform as part of the composite operation.</span></span> <span data-ttu-id="50c66-199">この例では、次に対応する子ノードを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50c66-199">For this example, you must add child nodes corresponding to the following:</span></span>  
  
   -   <span data-ttu-id="50c66-200">挿入し、EMPLOYEE テーブルに対する操作を削除します。</span><span class="sxs-lookup"><span data-stu-id="50c66-200">Insert and Delete operations on the EMPLOYEE table.</span></span>  
  
   -   <span data-ttu-id="50c66-201">GET_LAST_EMP_DATA はストアド プロシージャです。</span><span class="sxs-lookup"><span data-stu-id="50c66-201">GET_LAST_EMP_DATA stored procedure.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="50c66-202">下の子ノードと同じ順序で子ノードを追加する必要があります、**要求**ノード。</span><span class="sxs-lookup"><span data-stu-id="50c66-202">You must add the child nodes in the same order as the child nodes under the **Request** node.</span></span>  
  
    <span data-ttu-id="50c66-203">子ノードを追加する、 **RequestResponse**ノード。</span><span class="sxs-lookup"><span data-stu-id="50c66-203">To add child nodes to the **RequestResponse** node:</span></span>  
  
   1.  <span data-ttu-id="50c66-204">右クリックし、 **RequestResponse**に**スキーマ ノードの挿入**、 をクリック**子レコード**します。</span><span class="sxs-lookup"><span data-stu-id="50c66-204">Right-click the **RequestResponse** node, point to **Insert Schema Node**, and click **Child Record**.</span></span>  
  
   2.  <span data-ttu-id="50c66-205">複合操作の一環として実行する操作の応答スキーマに対応するレコードの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="50c66-205">Rename the record to correspond to a response schema for an operation that you perform as part of the composite operation.</span></span> <span data-ttu-id="50c66-206">たとえば、"InsertResponse"するノードの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="50c66-206">For example, rename the node to “InsertResponse”.</span></span>  
  
   3.  <span data-ttu-id="50c66-207">マップ、 **InsertResponse**を EMPLOYEE テーブルに対する挿入操作の応答スキーマのノード。</span><span class="sxs-lookup"><span data-stu-id="50c66-207">Map the **InsertResponse** node to the response schema for the Insert operation on the EMPLOYEE table.</span></span> <span data-ttu-id="50c66-208">これを行うを右クリックし、 **InsertResponse**ノード、およびクリック**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="50c66-208">To do so, right-click the **InsertResponse** node, and click **Properties**.</span></span> <span data-ttu-id="50c66-209">**プロパティ**] ボックスから、 **Data Structure Type**一覧で、[ **InsertResponse (リファレンス)** します。</span><span class="sxs-lookup"><span data-stu-id="50c66-209">In the **Properties** box, from the **Data Structure Type** list, select **InsertResponse (Reference)**.</span></span>  
  
   4.  <span data-ttu-id="50c66-210">GET_LAST_EMP_DATA ストアド プロシージャと削除操作の応答スキーマのノードを追加するには、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="50c66-210">Repeat these steps to add nodes for the response schemas for the GET_LAST_EMP_DATA stored procedure and the Delete operation.</span></span> <span data-ttu-id="50c66-211">ノード名を指定し、次の表で説明したように、それらを対応するスキーマにマップします。</span><span class="sxs-lookup"><span data-stu-id="50c66-211">Specify the node names and map them to the corresponding schema as mentioned in the following table.</span></span>  
  
       |<span data-ttu-id="50c66-212">ノード名</span><span class="sxs-lookup"><span data-stu-id="50c66-212">Node name</span></span>|<span data-ttu-id="50c66-213">スキーマにマップ</span><span class="sxs-lookup"><span data-stu-id="50c66-213">Mapped to schema</span></span>|  
       |---------------|----------------------|  
       |<span data-ttu-id="50c66-214">GET_LAST_EMP_DATAResponse</span><span class="sxs-lookup"><span data-stu-id="50c66-214">GET_LAST_EMP_DATAResponse</span></span>|<span data-ttu-id="50c66-215">GET_LAST_EMP_DATAResponse (リファレンス)</span><span class="sxs-lookup"><span data-stu-id="50c66-215">GET_LAST_EMP_DATAResponse (Reference)</span></span>|  
       |<span data-ttu-id="50c66-216">DeleteResponse</span><span class="sxs-lookup"><span data-stu-id="50c66-216">DeleteResponse</span></span>|<span data-ttu-id="50c66-217">DeleteResponse (リファレンス)</span><span class="sxs-lookup"><span data-stu-id="50c66-217">DeleteResponse (Reference)</span></span>|  
  
6. <span data-ttu-id="50c66-218">保存、 **CompositeSchema.xsd**ファイル。</span><span class="sxs-lookup"><span data-stu-id="50c66-218">Save the **CompositeSchema.xsd** file.</span></span>  
  
## <a name="defining-messages-and-message-types"></a><span data-ttu-id="50c66-219">メッセージおよびメッセージの種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="50c66-219">Defining Messages and Message Types</span></span>  
 <span data-ttu-id="50c66-220">最後の手順で作成した複合スキーマでは、オーケストレーション内のメッセージに必要な「型」について説明します。</span><span class="sxs-lookup"><span data-stu-id="50c66-220">The composite schema that you created in the last step describes the “types” required for the messages in an orchestration.</span></span> <span data-ttu-id="50c66-221">メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。</span><span class="sxs-lookup"><span data-stu-id="50c66-221">A message is typically a variable, the type for which is defined by the corresponding schema.</span></span> <span data-ttu-id="50c66-222">オーケストレーションのメッセージを作成し、前の手順で作成したスキーマにそれらをリンクする必要がありますようになりました。</span><span class="sxs-lookup"><span data-stu-id="50c66-222">You must now create messages for the orchestration and link them to schema you created in the previous step.</span></span>  
  
#### <a name="to-create-messages-and-link-to-schema"></a><span data-ttu-id="50c66-223">メッセージを作成し、スキーマにリンクするには</span><span class="sxs-lookup"><span data-stu-id="50c66-223">To create messages and link to schema</span></span>  
  
1.  <span data-ttu-id="50c66-224">オーケストレーションを BizTalk プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="50c66-224">Add an orchestration to the BizTalk project.</span></span> <span data-ttu-id="50c66-225">ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックして**追加**、 をクリックし、**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="50c66-225">From Solution Explorer, right-click the BizTalk project name, point to **Add**, and then click **New Item**.</span></span> <span data-ttu-id="50c66-226">BizTalk オーケストレーションの名前を入力し、クリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="50c66-226">Type a name for the BizTalk orchestration, and then click **Add**.</span></span>  
  
2.  <span data-ttu-id="50c66-227">開いていない場合は、BizTalk プロジェクトのオーケストレーションの種類 ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="50c66-227">Open the Orchestration View window of the BizTalk project, if it is not already open.</span></span> <span data-ttu-id="50c66-228">これを行うには、次のようにクリックします。**ビュー**、 をポイント**その他の Windows**、順にクリックします**オーケストレーション**します。</span><span class="sxs-lookup"><span data-stu-id="50c66-228">To do so, click **View**, point to **Other Windows**, and then click **Orchestration View**.</span></span>  
  
3.  <span data-ttu-id="50c66-229">オーケストレーション ビューで右クリックして**メッセージ**、 をクリックし、**新しいメッセージ**します。</span><span class="sxs-lookup"><span data-stu-id="50c66-229">In Orchestration View, right-click **Messages**, and then click **New Message**.</span></span>  
  
4.  <span data-ttu-id="50c66-230">新しく作成されたメッセージを右クリックし、**プロパティ ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="50c66-230">Right-click the newly created message, and then select **Properties Window**.</span></span>  
  
5.  <span data-ttu-id="50c66-231">**プロパティ**のウィンドウ、 **Message_1**次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="50c66-231">In the **Properties** pane for the **Message_1**, do the following:</span></span>  
  
    |<span data-ttu-id="50c66-232">プロパティ</span><span class="sxs-lookup"><span data-stu-id="50c66-232">Use this</span></span>|<span data-ttu-id="50c66-233">目的</span><span class="sxs-lookup"><span data-stu-id="50c66-233">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="50c66-234">[Identifier]</span><span class="sxs-lookup"><span data-stu-id="50c66-234">Identifier</span></span>|<span data-ttu-id="50c66-235">「`Request`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="50c66-235">Type `Request`</span></span>|  
    |<span data-ttu-id="50c66-236">メッセージ型</span><span class="sxs-lookup"><span data-stu-id="50c66-236">Message Type</span></span>|<span data-ttu-id="50c66-237">ドロップダウン リストから展開**スキーマ**、し、 *CompositeOp.CompositeSchema.Request*CompositeOp は、BizTalk プロジェクトの名前です。</span><span class="sxs-lookup"><span data-stu-id="50c66-237">From the drop-down list, expand **Schemas**, and then select *CompositeOp.CompositeSchema.Request*, where CompositeOp is the name of your BizTalk project.</span></span> <span data-ttu-id="50c66-238">CompositeSchema は複合操作用に手動で作成したスキーマを示します。</span><span class="sxs-lookup"><span data-stu-id="50c66-238">CompositeSchema is the schema you created manually for the composite operations.</span></span>|  
  
6.  <span data-ttu-id="50c66-239">新しいメッセージを作成する 2 の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="50c66-239">Repeat step 2 to create a new message.</span></span> <span data-ttu-id="50c66-240">**プロパティ**ウィンドウで、新しいメッセージの場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="50c66-240">In the **Properties** pane for the new message, do the following:</span></span>  
  
    |<span data-ttu-id="50c66-241">プロパティ</span><span class="sxs-lookup"><span data-stu-id="50c66-241">Use this</span></span>|<span data-ttu-id="50c66-242">目的</span><span class="sxs-lookup"><span data-stu-id="50c66-242">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="50c66-243">[Identifier]</span><span class="sxs-lookup"><span data-stu-id="50c66-243">Identifier</span></span>|<span data-ttu-id="50c66-244">「`Response`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="50c66-244">Type `Response`</span></span>|  
    |<span data-ttu-id="50c66-245">メッセージ型</span><span class="sxs-lookup"><span data-stu-id="50c66-245">Message Type</span></span>|<span data-ttu-id="50c66-246">ドロップダウン リストから展開**スキーマ**、し、 *CompositeOp.CompositeSchema.RequestResponse*します。</span><span class="sxs-lookup"><span data-stu-id="50c66-246">From the drop-down list, expand **Schemas**, and then select *CompositeOp.CompositeSchema.RequestResponse*.</span></span>|  
  
## <a name="setting-up-the-orchestration"></a><span data-ttu-id="50c66-247">オーケストレーションのセットアップ</span><span class="sxs-lookup"><span data-stu-id="50c66-247">Setting up the Orchestration</span></span>  
 <span data-ttu-id="50c66-248">使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]の SQL Server での複合操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="50c66-248">You must create a BizTalk orchestration to use [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] for performing composite operations on SQL Server.</span></span> <span data-ttu-id="50c66-249">このオーケストレーションでの要求メッセージを削除する、定義されている受信場所。</span><span class="sxs-lookup"><span data-stu-id="50c66-249">In this orchestration, you drop a request message at a defined receive location.</span></span> <span data-ttu-id="50c66-250">要求メッセージは、先ほど作成した複合スキーマに準拠する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50c66-250">The request message must conform to the composite schema you created earlier.</span></span> <span data-ttu-id="50c66-251">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]がこのメッセージを使用して、SQL Server に渡します。</span><span class="sxs-lookup"><span data-stu-id="50c66-251">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] consumes this message and passes it on to SQL Server.</span></span> <span data-ttu-id="50c66-252">SQL Server からの応答は、別の場所に保存されます。</span><span class="sxs-lookup"><span data-stu-id="50c66-252">The response from SQL Server is saved to another location.</span></span> <span data-ttu-id="50c66-253">送信を含めるし、受信図形を SQL Server にメッセージを送信し、それぞれ、応答を受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50c66-253">You must include Send and Receive shapes to send messages to SQL Server and receive responses, respectively.</span></span> <span data-ttu-id="50c66-254">複合操作を実行するための基本的なオーケストレーションには、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="50c66-254">A basic orchestration for performing composite operations resembles the following:</span></span>  
  
 <span data-ttu-id="50c66-255">![複合操作を実行するオーケストレーション](../../adapters-and-accelerators/adapter-oracle-database/media/4a1ecae7-8bf2-4c8a-a413-34d6a402cbfb.gif "4a1ecae7-8bf2-4c8a-a413-34d6a402cbfb")</span><span class="sxs-lookup"><span data-stu-id="50c66-255">![Orchestration to peform composite operations](../../adapters-and-accelerators/adapter-oracle-database/media/4a1ecae7-8bf2-4c8a-a413-34d6a402cbfb.gif "4a1ecae7-8bf2-4c8a-a413-34d6a402cbfb")</span></span>  
  
### <a name="adding-message-shapes"></a><span data-ttu-id="50c66-256">メッセージの構築図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="50c66-256">Adding Message Shapes</span></span>  
 <span data-ttu-id="50c66-257">メッセージの構築図形のごとに、次のプロパティを指定することを確認します。</span><span class="sxs-lookup"><span data-stu-id="50c66-257">Make sure you specify the following properties for each of the message shapes.</span></span> <span data-ttu-id="50c66-258">図形の列に示した名前は、単に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。</span><span class="sxs-lookup"><span data-stu-id="50c66-258">The names listed in the Shape column are the names of the message shapes as displayed in the just-mentioned orchestration.</span></span>  
  
|<span data-ttu-id="50c66-259">図形</span><span class="sxs-lookup"><span data-stu-id="50c66-259">Shape</span></span>|<span data-ttu-id="50c66-260">図形の種類</span><span class="sxs-lookup"><span data-stu-id="50c66-260">Shape Type</span></span>|<span data-ttu-id="50c66-261">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="50c66-261">Properties</span></span>|  
|-----------|----------------|----------------|  
|<span data-ttu-id="50c66-262">ReceiveMessage</span><span class="sxs-lookup"><span data-stu-id="50c66-262">ReceiveMessage</span></span>|<span data-ttu-id="50c66-263">Receive</span><span class="sxs-lookup"><span data-stu-id="50c66-263">Receive</span></span>|<span data-ttu-id="50c66-264">-設定**名前**に*ReceiveMessage*</span><span class="sxs-lookup"><span data-stu-id="50c66-264">-   Set **Name** to *ReceiveMessage*</span></span><br /><span data-ttu-id="50c66-265">-設定**アクティブ**に*は True。*</span><span class="sxs-lookup"><span data-stu-id="50c66-265">-   Set **Activate** to *True*</span></span>|  
|<span data-ttu-id="50c66-266">SendMessage</span><span class="sxs-lookup"><span data-stu-id="50c66-266">SendMessage</span></span>|<span data-ttu-id="50c66-267">Send</span><span class="sxs-lookup"><span data-stu-id="50c66-267">Send</span></span>|<span data-ttu-id="50c66-268">-設定**名前**に*SendMessage*</span><span class="sxs-lookup"><span data-stu-id="50c66-268">-   Set **Name** to *SendMessage*</span></span>|  
|<span data-ttu-id="50c66-269">ReceiveResponse</span><span class="sxs-lookup"><span data-stu-id="50c66-269">ReceiveResponse</span></span>|<span data-ttu-id="50c66-270">Receive</span><span class="sxs-lookup"><span data-stu-id="50c66-270">Receive</span></span>|<span data-ttu-id="50c66-271">-設定**名前**に*ReceiveResponse*</span><span class="sxs-lookup"><span data-stu-id="50c66-271">-   Set **Name** to *ReceiveResponse*</span></span><br /><span data-ttu-id="50c66-272">-設定**アクティブ**に*False*</span><span class="sxs-lookup"><span data-stu-id="50c66-272">-   Set **Activate** to *False*</span></span>|  
|<span data-ttu-id="50c66-273">SendResponse</span><span class="sxs-lookup"><span data-stu-id="50c66-273">SendResponse</span></span>|<span data-ttu-id="50c66-274">Send</span><span class="sxs-lookup"><span data-stu-id="50c66-274">Send</span></span>|<span data-ttu-id="50c66-275">-設定**名前**に*SendResponse*</span><span class="sxs-lookup"><span data-stu-id="50c66-275">-   Set **Name** to *SendResponse*</span></span>|  
  
### <a name="adding-ports"></a><span data-ttu-id="50c66-276">ポートの追加</span><span class="sxs-lookup"><span data-stu-id="50c66-276">Adding Ports</span></span>  
 <span data-ttu-id="50c66-277">論理ポートごとに、次のプロパティを指定することを確認します。</span><span class="sxs-lookup"><span data-stu-id="50c66-277">Make sure you specify the following properties for each of the logical ports.</span></span> <span data-ttu-id="50c66-278">ポート列に示した名前は、オーケストレーションで表示されているポートの名前です。</span><span class="sxs-lookup"><span data-stu-id="50c66-278">The names listed in the Port column are the names of the ports as displayed in the orchestration.</span></span>  
  
|<span data-ttu-id="50c66-279">Port</span><span class="sxs-lookup"><span data-stu-id="50c66-279">Port</span></span>|<span data-ttu-id="50c66-280">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="50c66-280">Properties</span></span>|  
|----------|----------------|  
|<span data-ttu-id="50c66-281">MessageIn</span><span class="sxs-lookup"><span data-stu-id="50c66-281">MessageIn</span></span>|<span data-ttu-id="50c66-282">-設定**識別子**に*MessageIn*</span><span class="sxs-lookup"><span data-stu-id="50c66-282">-   Set **Identifier** to *MessageIn*</span></span><br /><span data-ttu-id="50c66-283">-設定**型**に*MessageInType*</span><span class="sxs-lookup"><span data-stu-id="50c66-283">-   Set **Type** to *MessageInType*</span></span><br /><span data-ttu-id="50c66-284">-設定**通信パターン**に*一方向*</span><span class="sxs-lookup"><span data-stu-id="50c66-284">-   Set **Communication Pattern** to *One-Way*</span></span><br /><span data-ttu-id="50c66-285">-設定**通信方向**に*受信*</span><span class="sxs-lookup"><span data-stu-id="50c66-285">-   Set **Communication Direction** to *Receive*</span></span>|  
|<span data-ttu-id="50c66-286">LOBPort</span><span class="sxs-lookup"><span data-stu-id="50c66-286">LOBPort</span></span>|<span data-ttu-id="50c66-287">-設定**識別子**に*LOBPort*</span><span class="sxs-lookup"><span data-stu-id="50c66-287">-   Set **Identifier** to *LOBPort*</span></span><br /><span data-ttu-id="50c66-288">-設定**型**に*LOBPortType*</span><span class="sxs-lookup"><span data-stu-id="50c66-288">-   Set **Type** to *LOBPortType*</span></span><br /><span data-ttu-id="50c66-289">-設定**通信パターン**に*要求-応答*</span><span class="sxs-lookup"><span data-stu-id="50c66-289">-   Set **Communication Pattern** to *Request-Response*</span></span><br /><span data-ttu-id="50c66-290">-設定**通信方向**に*送受信*</span><span class="sxs-lookup"><span data-stu-id="50c66-290">-   Set **Communication Direction** to *Send-Receive*</span></span>|  
|<span data-ttu-id="50c66-291">ResponseOut</span><span class="sxs-lookup"><span data-stu-id="50c66-291">ResponseOut</span></span>|<span data-ttu-id="50c66-292">-設定**識別子**に*ResponseOut*</span><span class="sxs-lookup"><span data-stu-id="50c66-292">-   Set **Identifier** to *ResponseOut*</span></span><br /><span data-ttu-id="50c66-293">-設定**型**に*ResponseOutType*</span><span class="sxs-lookup"><span data-stu-id="50c66-293">-   Set **Type** to *ResponseOutType*</span></span><br /><span data-ttu-id="50c66-294">-設定**通信パターン**に*一方向*</span><span class="sxs-lookup"><span data-stu-id="50c66-294">-   Set **Communication Pattern** to *One-Way*</span></span><br /><span data-ttu-id="50c66-295">-設定**通信方向**に*送信*</span><span class="sxs-lookup"><span data-stu-id="50c66-295">-   Set **Communication Direction** to *Send*</span></span>|  
  
### <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a><span data-ttu-id="50c66-296">アクション図形は、メッセージを指定し、ポートに接続</span><span class="sxs-lookup"><span data-stu-id="50c66-296">Specify Messages for Action Shapes, and Connect Them to Ports</span></span>  
 <span data-ttu-id="50c66-297">次の表では、プロパティとアクション図形のメッセージを指定して、メッセージ ポートにリンクを設定する必要があります、値を指定します。</span><span class="sxs-lookup"><span data-stu-id="50c66-297">The following table specifies the properties and their values that you should set to specify messages for action shapes and to link the messages to the ports.</span></span> <span data-ttu-id="50c66-298">図形の列に示した名前は、前に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。</span><span class="sxs-lookup"><span data-stu-id="50c66-298">The names listed in the Shape column are the names of the message shapes as displayed in the orchestration mentioned earlier.</span></span>  
  
|<span data-ttu-id="50c66-299">図形</span><span class="sxs-lookup"><span data-stu-id="50c66-299">Shape</span></span>|<span data-ttu-id="50c66-300">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="50c66-300">Properties</span></span>|  
|-----------|----------------|  
|<span data-ttu-id="50c66-301">ReceiveMessage</span><span class="sxs-lookup"><span data-stu-id="50c66-301">ReceiveMessage</span></span>|<span data-ttu-id="50c66-302">-設定**メッセージ**に*要求*</span><span class="sxs-lookup"><span data-stu-id="50c66-302">-   Set **Message** to *Request*</span></span><br /><span data-ttu-id="50c66-303">-設定**操作**に*MessageIn.CompositeOp.Request*</span><span class="sxs-lookup"><span data-stu-id="50c66-303">-   Set **Operation** to *MessageIn.CompositeOp.Request*</span></span>|  
|<span data-ttu-id="50c66-304">SendMessage</span><span class="sxs-lookup"><span data-stu-id="50c66-304">SendMessage</span></span>|<span data-ttu-id="50c66-305">-設定**メッセージ**に*要求*</span><span class="sxs-lookup"><span data-stu-id="50c66-305">-   Set **Message** to *Request*</span></span><br /><span data-ttu-id="50c66-306">-設定**操作**に*LOBPort.CompositeOp.Request*</span><span class="sxs-lookup"><span data-stu-id="50c66-306">-   Set **Operation** to *LOBPort.CompositeOp.Request*</span></span>|  
|<span data-ttu-id="50c66-307">ReceiveResponse</span><span class="sxs-lookup"><span data-stu-id="50c66-307">ReceiveResponse</span></span>|<span data-ttu-id="50c66-308">-設定**メッセージ**に*応答*</span><span class="sxs-lookup"><span data-stu-id="50c66-308">-   Set **Message** to *Response*</span></span><br /><span data-ttu-id="50c66-309">-設定**操作**に*LOBPort.CompositeOp.Response*</span><span class="sxs-lookup"><span data-stu-id="50c66-309">-   Set **Operation** to *LOBPort.CompositeOp.Response*</span></span>|  
|<span data-ttu-id="50c66-310">SendResponse</span><span class="sxs-lookup"><span data-stu-id="50c66-310">SendResponse</span></span>|<span data-ttu-id="50c66-311">-設定**メッセージ**に*応答*</span><span class="sxs-lookup"><span data-stu-id="50c66-311">-   Set **Message** to *Response*</span></span><br /><span data-ttu-id="50c66-312">-設定**操作**に*ResponseOut.CompositeOp.Request*</span><span class="sxs-lookup"><span data-stu-id="50c66-312">-   Set **Operation** to *ResponseOut.CompositeOp.Request*</span></span>|  
  
 <span data-ttu-id="50c66-313">これらのプロパティを指定したら、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。</span><span class="sxs-lookup"><span data-stu-id="50c66-313">After you have specified these properties, the message shapes and ports are connected and your orchestration is complete.</span></span>  
  
 <span data-ttu-id="50c66-314">ここで、BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="50c66-314">You must now build the BizTalk solution and deploy it to a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="50c66-315">詳細については、次を参照してください。[を実行しているオーケストレーションのビルドと](../../core/building-and-running-orchestrations.md)します。</span><span class="sxs-lookup"><span data-stu-id="50c66-315">For more information, see [Building and Running Orchestrations](../../core/building-and-running-orchestrations.md).</span></span>
  
## <a name="configuring-the-biztalk-application"></a><span data-ttu-id="50c66-316">BizTalk アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="50c66-316">Configuring the BizTalk Application</span></span>  
 <span data-ttu-id="50c66-317">[オーケストレーション] ペインで先ほど作成したオーケストレーションが表示されている BizTalk プロジェクトを配置した後、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="50c66-317">After you have deployed the BizTalk project, the orchestration you created earlier is listed under the Orchestrations pane in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="50c66-318">使用する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールにアプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="50c66-318">You must use the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to configure the application.</span></span> <span data-ttu-id="50c66-319">チュートリアルについては、次を参照してください。[チュートリアル。基本的な BizTalk アプリケーション展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)します。</span><span class="sxs-lookup"><span data-stu-id="50c66-319">For a walkthrough, see [Walkthrough: Deploying a Basic BizTalk Application](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).</span></span>
  
 <span data-ttu-id="50c66-320">アプリケーションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50c66-320">Configuring an application involves:</span></span>  
  
- <span data-ttu-id="50c66-321">アプリケーションのホストを選択します。</span><span class="sxs-lookup"><span data-stu-id="50c66-321">Selecting a host for the application.</span></span>  
  
- <span data-ttu-id="50c66-322">物理ポートにオーケストレーションで作成したポートのマッピング、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="50c66-322">Mapping the ports that you created in your orchestration to physical ports in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="50c66-323">このオーケストレーションの次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="50c66-323">For this orchestration you must:</span></span>  
  
  - <span data-ttu-id="50c66-324">ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポートでの場所を定義します。</span><span class="sxs-lookup"><span data-stu-id="50c66-324">Define a location on the hard disk and a corresponding file port where you will drop a request message.</span></span> <span data-ttu-id="50c66-325">BizTalk オーケストレーションは要求メッセージを使用し、SQL Server データベースに送信します。</span><span class="sxs-lookup"><span data-stu-id="50c66-325">The BizTalk orchestration will consume the request message and send it to the SQL Server database.</span></span>  
  
  - <span data-ttu-id="50c66-326">ハード ディスクと、対応するファイル ポートを BizTalk オーケストレーションが、SQL Server データベースからの応答を含む応答メッセージをドロップする場所の場所を定義します。</span><span class="sxs-lookup"><span data-stu-id="50c66-326">Define a location on the hard disk and a corresponding file port where the BizTalk orchestration will drop the response message containing the response from the SQL Server database.</span></span>  
  
  - <span data-ttu-id="50c66-327">SQL Server データベースにメッセージを送信する物理 Wcf-custom または WCF-SQL 送信ポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="50c66-327">Define a physical WCF-Custom or WCF-SQL send port to send messages to the SQL Server database.</span></span> <span data-ttu-id="50c66-328">複合操作の一部が単一のトランザクションで実行されるようが含まれている操作を確認するため、 **UseAmbientTransaction**に設定されているプロパティのバインド**True**します。</span><span class="sxs-lookup"><span data-stu-id="50c66-328">Because the operations that are being as part of the composite operation are executed in a single transaction, make sure the **UseAmbientTransaction** binding property is set to **True**.</span></span>  
  
     <span data-ttu-id="50c66-329">送信ポートでアクションを指定することも必要があります。</span><span class="sxs-lookup"><span data-stu-id="50c66-329">You must also specify the action in the send port.</span></span> <span data-ttu-id="50c66-330">複合操作のアクションは、"**CompositeOperation**"。</span><span class="sxs-lookup"><span data-stu-id="50c66-330">The action for a composite operation is “**CompositeOperation**”.</span></span> <span data-ttu-id="50c66-331">ポートを作成する方法については、次を参照してください。 [SQL アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="50c66-331">For information about how to create ports, see [Manually configure a physical port binding to the SQL adapter](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md).</span></span> <span data-ttu-id="50c66-332">ポートのアクションを指定する方法の詳細については、次を参照してください。 [SQL アダプタの SOAP アクションを構成する](../../adapters-and-accelerators/adapter-sql/configure-the-soap-action-for-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="50c66-332">For more information about how to specify actions for ports, see [Configure the SOAP action for the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-the-soap-action-for-the-sql-adapter.md).</span></span>
  
    > [!NOTE]
    >  <span data-ttu-id="50c66-333">使用して、スキーマの生成、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。</span><span class="sxs-lookup"><span data-stu-id="50c66-333">Generating the schema using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] also creates a binding file that contains information about the ports and the actions to be set for those ports.</span></span> <span data-ttu-id="50c66-334">このバインド ファイルをインポートすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール (発信) の送信ポートを作成したり (着信) 用のポートを受信します。</span><span class="sxs-lookup"><span data-stu-id="50c66-334">You can import this binding file from the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to create send ports (for outbound calls) or receive ports (for inbound calls).</span></span> <span data-ttu-id="50c66-335">詳細については、次を参照してください。 [SQL アダプターを使用するポートのバインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="50c66-335">For more information, see [Configure a physical port binding using a port binding file to use the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md).</span></span> <span data-ttu-id="50c66-336">Wcf-custom または WCF-SQL 送信ポートでアクションがで選択したすべての操作に関連する動的アクションに設定されている場合、このバインド ファイルをインポートする、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]スキーマの生成中にします。</span><span class="sxs-lookup"><span data-stu-id="50c66-336">If you import this binding file, the action on the WCF-Custom or WCF-SQL send port is set to a dynamic action involving all the operations you selected in the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] while generating the schema.</span></span> <span data-ttu-id="50c66-337">複合操作の場合は、"CompositeOperation"で動的アクションを置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="50c66-337">For a composite operation, you must replace the dynamic action with “CompositeOperation”.</span></span>  
  
## <a name="starting-the-application"></a><span data-ttu-id="50c66-338">アプリケーションの起動</span><span class="sxs-lookup"><span data-stu-id="50c66-338">Starting the Application</span></span>  
 <span data-ttu-id="50c66-339">SQL Server データベースでの複合演算を実行する BizTalk アプリケーションを起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50c66-339">You must start the BizTalk application for performing composite operations on the SQL Server database.</span></span> <span data-ttu-id="50c66-340">BizTalk アプリケーションを開始する手順については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)します。</span><span class="sxs-lookup"><span data-stu-id="50c66-340">For instructions on starting a BizTalk application, see [How to Start an Orchestration](../../core/how-to-start-an-orchestration.md).</span></span>
  
 <span data-ttu-id="50c66-341">この段階で、ことを確認します。</span><span class="sxs-lookup"><span data-stu-id="50c66-341">At this stage, make sure:</span></span>  
  
-   <span data-ttu-id="50c66-342">ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。</span><span class="sxs-lookup"><span data-stu-id="50c66-342">The FILE receive port to receive request messages for the orchestration is running.</span></span>  
  
-   <span data-ttu-id="50c66-343">オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。</span><span class="sxs-lookup"><span data-stu-id="50c66-343">The FILE send port to receive the response messages from the orchestration is running.</span></span>  
  
-   <span data-ttu-id="50c66-344">SQL Server データベースにメッセージを送信する Wcf-custom または WCF-SQL 送信ポートが実行されています。</span><span class="sxs-lookup"><span data-stu-id="50c66-344">The WCF-Custom or WCF-SQL send port to send messages to the SQL Server database is running.</span></span>  
  
-   <span data-ttu-id="50c66-345">操作の BizTalk オーケストレーションが実行されています。</span><span class="sxs-lookup"><span data-stu-id="50c66-345">The BizTalk orchestration for the operation is running.</span></span>  
  
## <a name="executing-the-operation"></a><span data-ttu-id="50c66-346">操作の実行</span><span class="sxs-lookup"><span data-stu-id="50c66-346">Executing the Operation</span></span>  
 <span data-ttu-id="50c66-347">ファイルに要求メッセージを削除する必要があります、アプリケーションを実行した後の受信場所。</span><span class="sxs-lookup"><span data-stu-id="50c66-347">After you run the application, you must drop a request message to the FILE receive location.</span></span> <span data-ttu-id="50c66-348">要求メッセージのスキーマは、先ほど作成した複合操作のスキーマに準拠する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50c66-348">The schema for the request message must conform to the schema for the composite operations you created earlier.</span></span> <span data-ttu-id="50c66-349">たとえば、EMPLOYEE テーブルにレコードを挿入、GET_LAST_EMP_DATA ストアド プロシージャを呼び出すし、EMPLOYEE テーブルからレコードを削除する要求メッセージには。</span><span class="sxs-lookup"><span data-stu-id="50c66-349">For example, a request message that inserts a record in the EMPLOYEE table, invokes the GET_LAST_EMP_DATA stored procedure, and deletes a record from the EMPLOYEE table is:</span></span>  
  
```  
<Request xmlns="http://CompositeTest.CompositeSchema">  
  <Insert xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
    <Rows>  
      <Employee xmlns="http://schemas.microsoft.com/Sql/2008/05/Types/Tables/dbo">  
        <Name>John</Name>  
        <Designation>Manager</Designation>  
        <Salary>100000</Salary>  
      </Employee>  
    </Rows>  
  </Insert>  
  <GET_LAST_EMP_DATA xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/dbo" />  
  <Delete xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
    <Rows>  
      <Employee xmlns="http://schemas.microsoft.com/Sql/2008/05/Types/Tables/dbo">  
        <Name>John</Name>  
      </Employee>  
    </Rows>  
  </Delete>  
</Request>  
```  
  
 <span data-ttu-id="50c66-350">参照してください[複合操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md)を使用して、データベースの SQL Server での複合操作を実行するための要求メッセージ スキーマの詳細については、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="50c66-350">See [Message Schemas for Composite Operations](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md) for more information about the request message schema for performing composite operations on the SQL Server database using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
 <span data-ttu-id="50c66-351">オーケストレーションはメッセージを使用し、SQL Server データベースに送信します。</span><span class="sxs-lookup"><span data-stu-id="50c66-351">The orchestration consumes the message and sends it to the SQL Server database.</span></span> <span data-ttu-id="50c66-352">SQL Server データベースからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。</span><span class="sxs-lookup"><span data-stu-id="50c66-352">The response from the SQL Server database is saved at the other FILE location defined as part of the orchestration.</span></span> <span data-ttu-id="50c66-353">たとえば、前の要求メッセージの SQL Server データベースからの応答には。</span><span class="sxs-lookup"><span data-stu-id="50c66-353">For example, the response from the SQL Server database for the preceding request message is:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<RequestResponse xmlns="http://CompositeTest.CompositeSchema">  
  <InsertResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
    <InsertResult>  
      <long xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">10080</long>   
    </InsertResult>  
  </InsertResponse>  
  <GET_LAST_EMP_DATAResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/dbo">  
    <GET_LAST_EMP_DATAResult>  
      <DataSet xmlns="http://schemas.datacontract.org/2004/07/System.Data">  
        <xs:schema id="NewDataSet" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
          <xs:element msdata:IsDataSet="true" name="NewDataSet">  
            <xs:complexType>  
              <xs:sequence>  
                <xs:element minOccurs="0" maxOccurs="unbounded" name="NewTable">  
                  <xs:complexType>  
                    <xs:sequence>  
                      <xs:element minOccurs="0" name="Employee_ID" type="xs:int" />   
                      <xs:element minOccurs="0" name="Name" type="xs:string" />   
                      <xs:element minOccurs="0" name="DOJ" type="xs:dateTime" />   
                      <xs:element minOccurs="0" name="Designation" type="xs:string" />   
                      <xs:element minOccurs="0" name="Job_Description" type="xs:string" />   
                      <xs:element minOccurs="0" name="Photo" type="xs:base64Binary" />   
                      <xs:element minOccurs="0" name="Rating" type="xs:string" />   
                      <xs:element minOccurs="0" name="Salary" type="xs:decimal" />   
                      <xs:element minOccurs="0" name="Last_Modified" type="xs:base64Binary" />   
                    </xs:sequence>  
                  </xs:complexType>  
                </xs:element>  
              </xs:sequence>  
            </xs:complexType>  
          </xs:element>  
        </xs:schema>  
        <diffgr:diffgram xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
          <NewDataSet xmlns="">  
            <NewTable>  
              <Employee_ID>10080</Employee_ID>   
              <Name>John</Name>   
              <Designation>Manager</Designation>   
              <Salary>100000.00</Salary>   
              <Last_Modified>AAAAAAAAF40=</Last_Modified>   
            </NewTable>  
          </NewDataSet>  
        </diffgr:diffgram>  
      </DataSet>  
    </GET_LAST_EMP_DATAResult>  
    <ReturnValue>0</ReturnValue>   
  </GET_LAST_EMP_DATAResponse>  
  <DeleteResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
    <DeleteResult>1</DeleteResult>   
  </DeleteResponse>  
</RequestResponse>  
```  
  
 <span data-ttu-id="50c66-354">前の応答には、複合操作の一部として実行されるさまざまな操作を対応する複数の結果セットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="50c66-354">The preceding response contains multiple result sets corresponding the different operations performed as part of the composite operation.</span></span> <span data-ttu-id="50c66-355">たとえば、`InsertResult`要素には、新しく追加されたレコードの一意の識別子、10080 が含まれています。</span><span class="sxs-lookup"><span data-stu-id="50c66-355">For example, the `InsertResult` element contains 10080, which is the unique identifier for the newly added record.</span></span>  
  
## <a name="best-practices"></a><span data-ttu-id="50c66-356">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="50c66-356">Best Practices</span></span>  
 <span data-ttu-id="50c66-357">展開し、BizTalk プロジェクトの構成後は、バインド ファイルと呼ばれる XML ファイル構成設定をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="50c66-357">After you have deployed and configured the BizTalk project, you can export configuration settings to an XML file called the binding file.</span></span> <span data-ttu-id="50c66-358">バインド ファイルを生成した、送信ポートなどの項目を作成し、同じオーケストレーション用のポートを受信する必要はありませんように構成設定、ファイルからインポートできます。</span><span class="sxs-lookup"><span data-stu-id="50c66-358">Once you generate a binding file, you can import the configuration settings from the file, so that you do not need to create items such as send ports and receive ports for the same orchestration.</span></span> <span data-ttu-id="50c66-359">バインド ファイルの詳細については、次を参照してください。[アダプターのバインドを再利用](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)します。</span><span class="sxs-lookup"><span data-stu-id="50c66-359">For more information about binding files, see [Reuse adapter bindings](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="50c66-360">参照</span><span class="sxs-lookup"><span data-stu-id="50c66-360">See Also</span></span>  
[<span data-ttu-id="50c66-361">SQL アダプターを使用して BizTalk アプリケーションを開発する</span><span class="sxs-lookup"><span data-stu-id="50c66-361">Develop BizTalk applications using the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)