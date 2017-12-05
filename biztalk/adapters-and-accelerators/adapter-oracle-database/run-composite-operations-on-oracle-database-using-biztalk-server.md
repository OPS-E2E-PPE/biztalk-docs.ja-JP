---
title: "BizTalk Server を使用して Oracle データベースでの複合操作を実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bf47d95e-cdf1-4c9b-a15a-7cf123d0ea6d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41bb09a2bdece47795eabc91bf5e87ebba7deaa7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="run-composite-operations-on-oracle-database-using-biztalk-server"></a><span data-ttu-id="377e3-102">BizTalk Server を使用して Oracle データベースでの複合操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="377e3-102">Run Composite Operations on Oracle Database using BizTalk Server</span></span>
<span data-ttu-id="377e3-103">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アダプター クライアントが Oracle データベースでの複合操作を実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="377e3-103">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] enables adapter clients to perform composite operations on Oracle database.</span></span> <span data-ttu-id="377e3-104">複合操作を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="377e3-104">A composite operation can include:</span></span>  
  
-   <span data-ttu-id="377e3-105">挿入、更新、削除、およびテーブルおよびビューの操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="377e3-105">Insert, Update, Delete, and Select operations on tables and views.</span></span>  
  
-   <span data-ttu-id="377e3-106">ストアド プロシージャおよび関数、内部または外部パッケージです。</span><span class="sxs-lookup"><span data-stu-id="377e3-106">Stored procedures and functions, inside or outside a package.</span></span>  
  
 <span data-ttu-id="377e3-107">1 つの複合操作は、任意の順序でこれらの操作の任意の数を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="377e3-107">A single composite operation can have any number of these operations, in any order.</span></span> <span data-ttu-id="377e3-108">たとえば、2 つの insert、delete、およびストアド プロシージャの実行の最後に続くことができます。</span><span class="sxs-lookup"><span data-stu-id="377e3-108">For example, you can have two inserts followed by a delete, and finally a stored procedure execution.</span></span> <span data-ttu-id="377e3-109">また、さまざまな操作が別のデータベース テーブルまたはビューを対象とすることができます。</span><span class="sxs-lookup"><span data-stu-id="377e3-109">Also, you can have different operations targeting different database tables or views.</span></span> <span data-ttu-id="377e3-110">アダプターが複合操作をサポートする方法の詳細については、次を参照してください。 [Oracle データベースでの複合操作の実行](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-in-oracle-database.md)です。</span><span class="sxs-lookup"><span data-stu-id="377e3-110">For more information about how the adapter supports composite operations, see [Performing Composite Operations in Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-in-oracle-database.md).</span></span> <span data-ttu-id="377e3-111">複合操作用の SOAP メッセージの構造については、次を参照してください。[複合操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-composite-operation2.md)です。</span><span class="sxs-lookup"><span data-stu-id="377e3-111">For information about the structure of the SOAP message for composite operations, see [Message Schemas for the Composite Operation](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-composite-operation2.md).</span></span>  
  
## <a name="how-to-perform-composite-operations-on-oracle-database"></a><span data-ttu-id="377e3-112">Oracle データベースでの複合操作を実行する方法</span><span class="sxs-lookup"><span data-stu-id="377e3-112">How to Perform Composite Operations on Oracle Database?</span></span>  
 <span data-ttu-id="377e3-113">使用して Oracle データベースでの操作を実行する[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明した手順のタスクでは、[の Oracle データベースと BizTalk アプリケーションを開発する基盤](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)です。</span><span class="sxs-lookup"><span data-stu-id="377e3-113">Performing an operation on Oracle database using [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] involves procedural tasks described in [Building blocks to develop BizTalk Applications with Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md).</span></span> <span data-ttu-id="377e3-114">Oracle データベースでの複合操作を実行するには、これらのタスクです。</span><span class="sxs-lookup"><span data-stu-id="377e3-114">To perform composite operations on Oracle database, these tasks are:</span></span>  
  
1.  <span data-ttu-id="377e3-115">BizTalk プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]し、呼び出し先のすべての操作のスキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="377e3-115">Create a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and generate schema for all the operations you want to invoke.</span></span>  
  
2.  <span data-ttu-id="377e3-116">前の手順で生成したすべてのスキーマへの参照を含むスキーマ ファイルを手動で作成します。</span><span class="sxs-lookup"><span data-stu-id="377e3-116">Manually create a schema file that includes references to all the schemas you generated in the previous step.</span></span>  
  
3.  <span data-ttu-id="377e3-117">Oracle データベースからメッセージを送受信するための BizTalk プロジェクトでメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="377e3-117">Create messages in the BizTalk project for sending and receiving messages from Oracle database.</span></span> <span data-ttu-id="377e3-118">これらのメッセージは、前の手順で作成した要求と応答のスキーマに準拠する必要があります。</span><span class="sxs-lookup"><span data-stu-id="377e3-118">These messages must conform to the request and response schema you created in the previous step.</span></span>  
  
4.  <span data-ttu-id="377e3-119">Oracle データベースで複合操作を呼び出すオーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="377e3-119">Create an orchestration to invoke the composite operation on Oracle database.</span></span>  
  
5.  <span data-ttu-id="377e3-120">構築し、BizTalk プロジェクトを展開します。</span><span class="sxs-lookup"><span data-stu-id="377e3-120">Build and deploy the BizTalk project.</span></span>  
  
6.  <span data-ttu-id="377e3-121">BizTalk アプリケーションを作成する物理送信ポートと受信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="377e3-121">Configure the BizTalk application by creating physical send and receive ports.</span></span>  
  
7.  <span data-ttu-id="377e3-122">BizTalk アプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="377e3-122">Start the BizTalk application.</span></span>  
  
 <span data-ttu-id="377e3-123">このトピックでは、これらのタスクを実行する方法についてを説明します。</span><span class="sxs-lookup"><span data-stu-id="377e3-123">This topic provides instructions on how to perform these tasks.</span></span>  
  
## <a name="generating-schema"></a><span data-ttu-id="377e3-124">スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="377e3-124">Generating Schema</span></span>  
 <span data-ttu-id="377e3-125">このトピックでは、複合操作を実行する方法を示すは実行します同じ順序で次のタスク。</span><span class="sxs-lookup"><span data-stu-id="377e3-125">In this topic, to demonstrate how to perform composite operations, we will perform the following tasks in the same order:</span></span>  
  
-   <span data-ttu-id="377e3-126">ACCOUNTACTIVITY テーブルにレコードを挿入します。</span><span class="sxs-lookup"><span data-stu-id="377e3-126">Insert record into the ACCOUNTACTIVITY table.</span></span>  
  
-   <span data-ttu-id="377e3-127">ACCOUNT_PKG パッケージ内で GET_ALL_ACTIVITY プロシージャを呼び出すことによって、ACCOUNTACTIVITY テーブル内のすべてのレコードを取得します。</span><span class="sxs-lookup"><span data-stu-id="377e3-127">Retrieve all the records in the ACCOUNTACTIVITY table by invoking the GET_ALL_ACTIVITY procedure within the ACCOUNT_PKG package.</span></span>  
  
-   <span data-ttu-id="377e3-128">ACCOUNTACTIVITY テーブルからレコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="377e3-128">Delete the record from the ACCOUNTACTIVITY table.</span></span>  
  
 <span data-ttu-id="377e3-129">ACCOUNTACTIVITY テーブルを作成するサンプルに用意されているスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="377e3-129">Run the scripts provided with the samples to create the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="377e3-130">サンプルの詳細については、次を参照してください。[スキーマのサンプル](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)です。</span><span class="sxs-lookup"><span data-stu-id="377e3-130">For more information about the samples, see [Schema Samples](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md).</span></span>  
  
 <span data-ttu-id="377e3-131">BizTalk プロジェクトを作成して使用する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="377e3-131">You must create a BizTalk project and use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] to generate the schema.</span></span> <span data-ttu-id="377e3-132">参照してください[Visual Studio での Oracle データベース操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)スキーマを生成する方法についての詳細。</span><span class="sxs-lookup"><span data-stu-id="377e3-132">See [Retrieve metadata for Oracle Database operations in Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md) for more information about how to generate schemas.</span></span>  
  
## <a name="creating-a-composite-schema-definition"></a><span data-ttu-id="377e3-133">複合のスキーマ定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="377e3-133">Creating a Composite Schema Definition</span></span>  
 <span data-ttu-id="377e3-134">今すぐに複合スキーマを作成する必要があります、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]個々 の操作用に作成したスキーマを参照する BizTalk プロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="377e3-134">You must now create a composite schema in the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] BizTalk project that references the schemas you created for the individual operations.</span></span> <span data-ttu-id="377e3-135">複合のスキーマ定義を作成する次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="377e3-135">Perform the following steps to create a composite schema definition.</span></span>  
  
#### <a name="to-add-a-composite-schema-definition"></a><span data-ttu-id="377e3-136">複合のスキーマ定義を追加するには</span><span class="sxs-lookup"><span data-stu-id="377e3-136">To add a composite schema definition</span></span>  
  
1.  <span data-ttu-id="377e3-137">BizTalk プロジェクトにスキーマ ファイルを追加[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="377e3-137">Add a schema file to the BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="377e3-138">ソリューション名を右クリックし、**追加**、クリックして**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="377e3-138">Right-click the solution name, point to **Add**, and then click **New Item**.</span></span> <span data-ttu-id="377e3-139">**新しい項目の追加** ダイアログ ボックスから、**カテゴリ**ボックスで、クリックして**スキーマ ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="377e3-139">In the **Add New Item** dialog box, from the **Categories** box, click **Schema Files**.</span></span> <span data-ttu-id="377e3-140">**テンプレート**ボックスで、クリックして**スキーマ**です。</span><span class="sxs-lookup"><span data-stu-id="377e3-140">From the **Templates** box, click **Schema**.</span></span> <span data-ttu-id="377e3-141">スキーマ ファイルの名前を指定し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="377e3-141">Specify a name for the schema file and click **OK**.</span></span>  
  
     <span data-ttu-id="377e3-142">この例で、ファイルとスキーマ名を指定`CompositeSchema.xsd`です。</span><span class="sxs-lookup"><span data-stu-id="377e3-142">For this example, specify the schema file name as `CompositeSchema.xsd`.</span></span>  
  
2.  <span data-ttu-id="377e3-143">実行する別の操作の生成スキーマへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="377e3-143">Add references to the schema generated for the different operations that you want to perform.</span></span> <span data-ttu-id="377e3-144">この例では操作に対して生成されるさまざまなスキーマには。</span><span class="sxs-lookup"><span data-stu-id="377e3-144">In this example, the different schemas generated for operations are:</span></span>  
  
    -   <span data-ttu-id="377e3-145">OracleDBBinding.xsd、ACCOUNTACTIVITY テーブルに対する挿入および削除の操作です。</span><span class="sxs-lookup"><span data-stu-id="377e3-145">OracleDBBinding.xsd, for Insert and Delete operations on ACCOUNTACTIVITY table.</span></span>  
  
    -   <span data-ttu-id="377e3-146">OracleDBBinding2.xsd、GET_ALL_ACTIVITY プロシージャです。</span><span class="sxs-lookup"><span data-stu-id="377e3-146">OracleDBBinding2.xsd, for the GET_ALL_ACTIVITY procedure.</span></span>  
  
     <span data-ttu-id="377e3-147">参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="377e3-147">To add references:</span></span>  
  
    1.  <span data-ttu-id="377e3-148">ルートを右クリックして**\<スキーマ\>** CompositeSchema.xsd、およびクリック ノード**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="377e3-148">Right-click the root **\<Schema\>** node in the CompositeSchema.xsd, and click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="377e3-149">**プロパティ**ボックスで、省略記号ボタンをクリックして**([...])**に対して、 **Imports**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="377e3-149">In the **Property** box, click the ellipsis button **(…)** against the **Imports** property.</span></span>  
  
         <span data-ttu-id="377e3-150">![スキーマ定義をインポート](../../adapters-and-accelerators/adapter-oracle-database/media/d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca.gif "d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca")</span><span class="sxs-lookup"><span data-stu-id="377e3-150">![Import schema definitions](../../adapters-and-accelerators/adapter-oracle-database/media/d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca.gif "d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca")</span></span>  
  
    3.  <span data-ttu-id="377e3-151">**Imports** ] ダイアログ ボックスから、**として新しいスキーマのインポート**一覧で、[ **XSD のインポート**、順にクリック**追加**です。</span><span class="sxs-lookup"><span data-stu-id="377e3-151">In the **Imports** dialog box, from the **Import new schema as** list, select **XSD Import**, and then click **Add**.</span></span>  
  
    4.  <span data-ttu-id="377e3-152">**BizTalk 型の選択** ダイアログ ボックスで、BizTalk プロジェクト名 ノードを展開し、展開**スキーマ**、し、インポートするスキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="377e3-152">In the **BizTalk Type Picker** dialog box, expand the BizTalk project name node, expand **Schemas**, and then select the schema you want to import.</span></span> <span data-ttu-id="377e3-153">この例では、< BizTalk_project_name > を選択します。OracleDBBinding.xsd です。</span><span class="sxs-lookup"><span data-stu-id="377e3-153">For this example, select <BizTalk_project_name>.OracleDBBinding.xsd.</span></span> <span data-ttu-id="377e3-154">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="377e3-154">Click **OK**.</span></span>  
  
         <span data-ttu-id="377e3-155">< BizTalk_project_name > をインポートするには、この手順を繰り返します。OracleDBBinding2.xsd すぎます。</span><span class="sxs-lookup"><span data-stu-id="377e3-155">Repeat this step to import <BizTalk_project_name>.OracleDBBinding2.xsd too.</span></span>  
  
    5.  <span data-ttu-id="377e3-156">**Imports**ダイアログ ボックスで、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="377e3-156">In the **Imports** dialog box, click **OK**.</span></span>  
  
3.  <span data-ttu-id="377e3-157">ルート スキーマ ノードに 2 つの子ノードを追加します。</span><span class="sxs-lookup"><span data-stu-id="377e3-157">Add two child nodes to the root schema node.</span></span> <span data-ttu-id="377e3-158">1 つの子ノードは、複合操作を実行するため、要求スキーマに対応します。</span><span class="sxs-lookup"><span data-stu-id="377e3-158">One child node corresponds to the request schema for performing the composite operation.</span></span> <span data-ttu-id="377e3-159">その他の子ノードは、応答スキーマに対応します。</span><span class="sxs-lookup"><span data-stu-id="377e3-159">The other child node corresponds to the response schema.</span></span> <span data-ttu-id="377e3-160">Request スキーマに対応するノードには、任意の名前を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="377e3-160">The node that corresponds to the request schema can have any name.</span></span> <span data-ttu-id="377e3-161">応答スキーマに対応するノードには、< request_schema_node > 応答を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="377e3-161">The node that corresponds to the response schema must be called <request_schema_node>Response.</span></span> <span data-ttu-id="377e3-162">この例として、要求スキーマのノードを呼び出しては**要求**です。</span><span class="sxs-lookup"><span data-stu-id="377e3-162">For this example, we will call the request schema node as **Request**.</span></span> <span data-ttu-id="377e3-163">そのため、応答スキーマのノードと呼びます**RequestResponse**です。</span><span class="sxs-lookup"><span data-stu-id="377e3-163">So, the response schema node is called **RequestResponse**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="377e3-164">既定では、**ルート**ノードが新しいスキーマ ファイルにも追加します。</span><span class="sxs-lookup"><span data-stu-id="377e3-164">By default, a **Root** node is also added to a new schema file.</span></span> <span data-ttu-id="377e3-165">名前を変更することができます、**ルート**ノード**要求**です。</span><span class="sxs-lookup"><span data-stu-id="377e3-165">You can rename the **Root** node to **Request**.</span></span> <span data-ttu-id="377e3-166">ノードの名前を変更するノード名を右クリックし、をクリックして**の名前を変更**です。</span><span class="sxs-lookup"><span data-stu-id="377e3-166">To rename a node, right-click the node name and click **Rename**.</span></span>  
  
     <span data-ttu-id="377e3-167">下のノードを追加する、 **\<スキーマ\>**ノード。</span><span class="sxs-lookup"><span data-stu-id="377e3-167">To add a node under the **\<Schema\>** node:</span></span>  
  
    1.  <span data-ttu-id="377e3-168">右クリックし、 **\<スキーマ\>**に**スキーマ ノードの挿入**、 をクリック**子レコード**です。</span><span class="sxs-lookup"><span data-stu-id="377e3-168">Right-click the **\<Schema\>** node, point to **Insert Schema Node**, and click **Child Record**.</span></span>  
  
    2.  <span data-ttu-id="377e3-169">新しいノードの名前を**RequestResponse**です。</span><span class="sxs-lookup"><span data-stu-id="377e3-169">Rename the new node to **RequestResponse**.</span></span>  
  
4.  <span data-ttu-id="377e3-170">下に子ノードを追加、**要求**複合操作の一部として実行する各操作の要求スキーマに対応するノードです。</span><span class="sxs-lookup"><span data-stu-id="377e3-170">Add child nodes under the **Request** node that correspond to the request schema for each operation that you will perform as part of the composite operation.</span></span> <span data-ttu-id="377e3-171">この例では、次に対応する子ノードを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="377e3-171">For this example, you must add child nodes corresponding to the following:</span></span>  
  
    -   <span data-ttu-id="377e3-172">挿入し、ACCOUNTACTIVITY テーブルに対する操作を削除します。</span><span class="sxs-lookup"><span data-stu-id="377e3-172">Insert and Delete operations on the ACCOUNTACTIVITY table.</span></span>  
  
    -   <span data-ttu-id="377e3-173">GET_ALL_ACTIVITY プロシージャです。</span><span class="sxs-lookup"><span data-stu-id="377e3-173">GET_ALL_ACTIVITY procedure.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="377e3-174">操作を実行する同じ順序でのノードを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="377e3-174">You must add the nodes in the same order in which you want to perform the operations.</span></span> <span data-ttu-id="377e3-175">たとえば、レコードを挿入し、ストアド プロシージャを実行し、挿入操作のノードを追加する必要があります最初のレコードを削除する場合は、後に、ストアド プロシージャのノードと最後に、削除操作のノード。</span><span class="sxs-lookup"><span data-stu-id="377e3-175">For example, if you want to insert a record, then execute a stored procedure, and then delete a record you must first add a node for the Insert operation, followed by a node for the stored procedure, and finally a node for the Delete operation.</span></span>  
  
     <span data-ttu-id="377e3-176">子ノードを追加する、**要求**ノード。</span><span class="sxs-lookup"><span data-stu-id="377e3-176">To add child nodes to the **Request** node:</span></span>  
  
    1.  <span data-ttu-id="377e3-177">右クリックし、**要求**に**スキーマ ノードの挿入**、順にクリック**子レコード**です。</span><span class="sxs-lookup"><span data-stu-id="377e3-177">Right-click the **Request** node, point to **Insert Schema Node**, and then click  **Child Record**.</span></span>  
  
         <span data-ttu-id="377e3-178">![スキーマの子ノードの挿入](../../adapters-and-accelerators/adapter-oracle-database/media/58992131-13a6-45c3-9513-5c0995091fae.gif "58992131-13a6-45c3-9513-5c0995091fae")</span><span class="sxs-lookup"><span data-stu-id="377e3-178">![Insert child nodes for a schema](../../adapters-and-accelerators/adapter-oracle-database/media/58992131-13a6-45c3-9513-5c0995091fae.gif "58992131-13a6-45c3-9513-5c0995091fae")</span></span>  
  
    2.  <span data-ttu-id="377e3-179">複合操作の一部として実行する操作の要求スキーマに対応するレコードの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="377e3-179">Rename the record to correspond to a request schema for an operation that you perform as part of the composite operation.</span></span> <span data-ttu-id="377e3-180">たとえば、"Insert"するノードの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="377e3-180">For example, rename the node to “Insert”.</span></span>  
  
    3.  <span data-ttu-id="377e3-181">マップ、**挿入**ACCOUNTACTIVITY テーブルに対する挿入操作の要求スキーマのノードです。</span><span class="sxs-lookup"><span data-stu-id="377e3-181">Map the **Insert** node to the request schema for the Insert operation on the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="377e3-182">これを行うを右クリックし、**挿入** ノードをクリック**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="377e3-182">To do so, right-click the **Insert** node, and click **Properties**.</span></span> <span data-ttu-id="377e3-183">**プロパティ**] ボックスから、 **Data Structure Type**一覧で、[**挿入 (参照)**です。</span><span class="sxs-lookup"><span data-stu-id="377e3-183">In the **Properties** box, from the **Data Structure Type** list, select **Insert (Reference)**.</span></span>  
  
         <span data-ttu-id="377e3-184">![要求スキーマに子ノードをマップ](../../adapters-and-accelerators/adapter-oracle-database/media/b4ebd3c7-14e5-4c37-abd7-83f0b4db4c9e.gif "b4ebd3c7-14e5-4c37-abd7-83f0b4db4c9e")</span><span class="sxs-lookup"><span data-stu-id="377e3-184">![Map child nodes to request schema](../../adapters-and-accelerators/adapter-oracle-database/media/b4ebd3c7-14e5-4c37-abd7-83f0b4db4c9e.gif "b4ebd3c7-14e5-4c37-abd7-83f0b4db4c9e")</span></span>  
  
    4.  <span data-ttu-id="377e3-185">GET_ALL_ACTIVITY ストアド プロシージャおよび削除操作の要求スキーマのノードを追加する手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="377e3-185">Repeat these steps to add nodes for the request schemas for GET_ALL_ACTIVITY stored procedure and the Delete operation.</span></span> <span data-ttu-id="377e3-186">ノード名を指定し、次の表で説明したように、対応するスキーマにマップします。</span><span class="sxs-lookup"><span data-stu-id="377e3-186">Specify the node names and map them to the corresponding schema as mentioned in the following table.</span></span>  
  
        |<span data-ttu-id="377e3-187">ノード名</span><span class="sxs-lookup"><span data-stu-id="377e3-187">Node name</span></span>|<span data-ttu-id="377e3-188">スキーマにマップされています。</span><span class="sxs-lookup"><span data-stu-id="377e3-188">Mapped to schema</span></span>|  
        |---------------|----------------------|  
        |<span data-ttu-id="377e3-189">GET_ALL_ACTIVITY</span><span class="sxs-lookup"><span data-stu-id="377e3-189">GET_ALL_ACTIVITY</span></span>|<span data-ttu-id="377e3-190">GET_ALL_ACTIVITY (参照)</span><span class="sxs-lookup"><span data-stu-id="377e3-190">GET_ALL_ACTIVITY (Reference)</span></span>|  
        |<span data-ttu-id="377e3-191">DELETE</span><span class="sxs-lookup"><span data-stu-id="377e3-191">Delete</span></span>|<span data-ttu-id="377e3-192">削除 (参照)</span><span class="sxs-lookup"><span data-stu-id="377e3-192">Delete (Reference)</span></span>|  
  
5.  <span data-ttu-id="377e3-193">下に子ノードを追加、 **RequestResponse**複合操作の一部として実行する各操作の応答スキーマに対応するノードです。</span><span class="sxs-lookup"><span data-stu-id="377e3-193">Add child nodes under the **RequestResponse** node that correspond to the response schema for each operation that you will perform as part of the composite operation.</span></span> <span data-ttu-id="377e3-194">この例では、次に対応する子ノードを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="377e3-194">For this example, you must add child nodes corresponding to the following:</span></span>  
  
    -   <span data-ttu-id="377e3-195">挿入し、ACCOUNTACTIVITY テーブルに対する操作を削除します。</span><span class="sxs-lookup"><span data-stu-id="377e3-195">Insert and Delete operations on the ACCOUNTACTIVITY table.</span></span>  
  
    -   <span data-ttu-id="377e3-196">GET_ALL_ACTIVITY はストアド プロシージャです。</span><span class="sxs-lookup"><span data-stu-id="377e3-196">GET_ALL_ACTIVITY stored procedure.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="377e3-197">下の子ノードと同じ順序で子ノードを追加する必要があります、**要求**ノード。</span><span class="sxs-lookup"><span data-stu-id="377e3-197">You must add the child nodes in the same order as the child nodes under the **Request** node.</span></span>  
  
     <span data-ttu-id="377e3-198">子ノードを追加する、 **RequestResponse**ノード。</span><span class="sxs-lookup"><span data-stu-id="377e3-198">To add child nodes to the **RequestResponse** node:</span></span>  
  
    1.  <span data-ttu-id="377e3-199">右クリックし、 **RequestResponse**に**スキーマ ノードの挿入**、 をクリック**子レコード**です。</span><span class="sxs-lookup"><span data-stu-id="377e3-199">Right-click the **RequestResponse** node, point to **Insert Schema Node**, and click **Child Record**.</span></span>  
  
    2.  <span data-ttu-id="377e3-200">複合操作の一部として実行する操作の応答スキーマに対応するレコードの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="377e3-200">Rename the record to correspond to a response schema for an operation that you perform as part of the composite operation.</span></span> <span data-ttu-id="377e3-201">たとえば、"InsertResponse"するノードの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="377e3-201">For example, rename the node to “InsertResponse”.</span></span>  
  
    3.  <span data-ttu-id="377e3-202">マップ、 **InsertResponse** ACCOUNTACTIVITY テーブルに対する挿入操作用の応答スキーマにノードです。</span><span class="sxs-lookup"><span data-stu-id="377e3-202">Map the **InsertResponse** node to the response schema for the Insert operation on the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="377e3-203">これを行うを右クリックし、 **InsertResponse**ノード、およびクリック**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="377e3-203">To do so, right-click the **InsertResponse** node, and click **Properties**.</span></span> <span data-ttu-id="377e3-204">**プロパティ**] ボックスから、 **Data Structure Type**一覧で、[ **InsertResponse (参照)**です。</span><span class="sxs-lookup"><span data-stu-id="377e3-204">In the **Properties** box, from the **Data Structure Type** list, select **InsertResponse (Reference)**.</span></span>  
  
    4.  <span data-ttu-id="377e3-205">GET_ALL_ACTIVITY ストアド プロシージャおよび削除操作の応答スキーマのノードを追加する手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="377e3-205">Repeat these steps to add nodes for the response schemas for the GET_ALL_ACTIVITY stored procedure and the Delete operation.</span></span> <span data-ttu-id="377e3-206">ノード名を指定し、次の表で説明したように、対応するスキーマにマップします。</span><span class="sxs-lookup"><span data-stu-id="377e3-206">Specify the node names and map them to the corresponding schema as mentioned in the following table.</span></span>  
  
        |<span data-ttu-id="377e3-207">ノード名</span><span class="sxs-lookup"><span data-stu-id="377e3-207">Node name</span></span>|<span data-ttu-id="377e3-208">スキーマにマップされています。</span><span class="sxs-lookup"><span data-stu-id="377e3-208">Mapped to schema</span></span>|  
        |---------------|----------------------|  
        |<span data-ttu-id="377e3-209">GET_ALL_ACTIVITYResponse</span><span class="sxs-lookup"><span data-stu-id="377e3-209">GET_ALL_ACTIVITYResponse</span></span>|<span data-ttu-id="377e3-210">GET_ALL_ACTIVITYResponse (参照)</span><span class="sxs-lookup"><span data-stu-id="377e3-210">GET_ALL_ACTIVITYResponse (Reference)</span></span>|  
        |<span data-ttu-id="377e3-211">DeleteResponse</span><span class="sxs-lookup"><span data-stu-id="377e3-211">DeleteResponse</span></span>|<span data-ttu-id="377e3-212">DeleteResponse (参照)</span><span class="sxs-lookup"><span data-stu-id="377e3-212">DeleteResponse (Reference)</span></span>|  
  
6.  <span data-ttu-id="377e3-213">保存、 **CompositeSchema.xsd**ファイル。</span><span class="sxs-lookup"><span data-stu-id="377e3-213">Save the **CompositeSchema.xsd** file.</span></span>  
  
## <a name="defining-messages-and-message-types"></a><span data-ttu-id="377e3-214">メッセージとメッセージの種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="377e3-214">Defining Messages and Message Types</span></span>  
 <span data-ttu-id="377e3-215">最後の手順で作成した複合スキーマでは、オーケストレーション内のメッセージに必要な「型」について説明します。</span><span class="sxs-lookup"><span data-stu-id="377e3-215">The composite schema that you created in the last step describes the “types” required for the messages in an orchestration.</span></span> <span data-ttu-id="377e3-216">メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。</span><span class="sxs-lookup"><span data-stu-id="377e3-216">A message is typically a variable, the type for which is defined by the corresponding schema.</span></span> <span data-ttu-id="377e3-217">オーケストレーションのメッセージを作成し、それらを前の手順で作成したスキーマにリンクする必要がありますようになりました。</span><span class="sxs-lookup"><span data-stu-id="377e3-217">You must now create messages for the orchestration and link them to schema you created in the previous step.</span></span>  
  
#### <a name="to-create-messages-and-link-to-schema"></a><span data-ttu-id="377e3-218">メッセージを作成し、スキーマにリンクするには</span><span class="sxs-lookup"><span data-stu-id="377e3-218">To create messages and link to schema</span></span>  
  
1.  <span data-ttu-id="377e3-219">オーケストレーションを BizTalk プロジェクトに追加[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="377e3-219">Add an orchestration to the BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="377e3-220">ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックし、**追加**、クリックして**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="377e3-220">From Solution Explorer, right-click the BizTalk project name, point to **Add**, and then click **New Item**.</span></span> <span data-ttu-id="377e3-221">BizTalk オーケストレーションの名前を入力し、クリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="377e3-221">Type a name for the BizTalk orchestration, and then click **Add**.</span></span>  
  
2.  <span data-ttu-id="377e3-222">まだ開いていない場合は、BizTalk プロジェクトのオーケストレーションの種類 ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="377e3-222">Open the Orchestration View window of the BizTalk project, if it is not already open.</span></span> <span data-ttu-id="377e3-223">これを行うには、をクリックして**ビュー**、 をポイント**その他のウィンドウ**、順にクリック**オーケストレーション ビュー**です。</span><span class="sxs-lookup"><span data-stu-id="377e3-223">To do so, click **View**, point to **Other Windows**, and then click **Orchestration View**.</span></span>  
  
3.  <span data-ttu-id="377e3-224">オーケストレーション ビューで右クリック**メッセージ**、クリックして**新しいメッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="377e3-224">In Orchestration View, right-click **Messages**, and then click **New Message**.</span></span>  
  
4.  <span data-ttu-id="377e3-225">新しく作成されたメッセージを右クリックし [**プロパティ] ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="377e3-225">Right-click the newly created message, and then select **Properties Window**.</span></span>  
  
5.  <span data-ttu-id="377e3-226">**プロパティ**のウィンドウ、 **Message_1**を次の操作します。</span><span class="sxs-lookup"><span data-stu-id="377e3-226">In the **Properties** pane for the **Message_1**, do the following:</span></span>  
  
    |<span data-ttu-id="377e3-227">プロパティ</span><span class="sxs-lookup"><span data-stu-id="377e3-227">Use this</span></span>|<span data-ttu-id="377e3-228">目的</span><span class="sxs-lookup"><span data-stu-id="377e3-228">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="377e3-229">[Identifier]</span><span class="sxs-lookup"><span data-stu-id="377e3-229">Identifier</span></span>|<span data-ttu-id="377e3-230">「`Request`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="377e3-230">Type `Request`</span></span>|  
    |<span data-ttu-id="377e3-231">メッセージの種類</span><span class="sxs-lookup"><span data-stu-id="377e3-231">Message Type</span></span>|<span data-ttu-id="377e3-232">ドロップダウン リストから、展開**スキーマ**、し、 *Composite_Op.CompositeSchema.Request*Composite_Op は、BizTalk プロジェクトの名前。</span><span class="sxs-lookup"><span data-stu-id="377e3-232">From the drop-down list, expand **Schemas**, and then select *Composite_Op.CompositeSchema.Request*, where Composite_Op is the name of your BizTalk project.</span></span> <span data-ttu-id="377e3-233">CompositeSchema は、複合操作用に手動で作成したスキーマです。</span><span class="sxs-lookup"><span data-stu-id="377e3-233">CompositeSchema is the schema you created manually for the composite operations.</span></span>|  
  
6.  <span data-ttu-id="377e3-234">新しいメッセージを作成する 2 の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="377e3-234">Repeat step 2 to create a new message.</span></span> <span data-ttu-id="377e3-235">**プロパティ**新しいメッセージ ウィンドウ、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="377e3-235">In the **Properties** pane for the new message, do the following:</span></span>  
  
    |<span data-ttu-id="377e3-236">プロパティ</span><span class="sxs-lookup"><span data-stu-id="377e3-236">Use this</span></span>|<span data-ttu-id="377e3-237">目的</span><span class="sxs-lookup"><span data-stu-id="377e3-237">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="377e3-238">[Identifier]</span><span class="sxs-lookup"><span data-stu-id="377e3-238">Identifier</span></span>|<span data-ttu-id="377e3-239">「`Response`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="377e3-239">Type `Response`</span></span>|  
    |<span data-ttu-id="377e3-240">メッセージの種類</span><span class="sxs-lookup"><span data-stu-id="377e3-240">Message Type</span></span>|<span data-ttu-id="377e3-241">ドロップダウン リストから、展開**スキーマ**、し、 *Composite_Op.CompositeSchema.RequestResponse*です。</span><span class="sxs-lookup"><span data-stu-id="377e3-241">From the drop-down list, expand **Schemas**, and then select *Composite_Op.CompositeSchema.RequestResponse*.</span></span>|  
  
## <a name="setting-up-the-orchestration"></a><span data-ttu-id="377e3-242">オーケストレーションを設定します。</span><span class="sxs-lookup"><span data-stu-id="377e3-242">Setting up the Orchestration</span></span>  
 <span data-ttu-id="377e3-243">使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Oracle データベースでの複合操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="377e3-243">You must create a BizTalk orchestration to use [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] for performing composite operations on Oracle database.</span></span> <span data-ttu-id="377e3-244">このオーケストレーションでの要求メッセージを削除する受信場所が、定義されています。</span><span class="sxs-lookup"><span data-stu-id="377e3-244">In this orchestration, you drop a request message at a defined receive location.</span></span> <span data-ttu-id="377e3-245">要求メッセージは、先ほど作成した複合スキーマに準拠する必要があります。</span><span class="sxs-lookup"><span data-stu-id="377e3-245">The request message must conform to the composite schema you created earlier.</span></span> <span data-ttu-id="377e3-246">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]このメッセージを消費し、Oracle データベースに渡します。</span><span class="sxs-lookup"><span data-stu-id="377e3-246">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] consumes this message and passes it on to Oracle database.</span></span> <span data-ttu-id="377e3-247">Oracle データベースからの応答は、別の場所に保存されます。</span><span class="sxs-lookup"><span data-stu-id="377e3-247">The response from Oracle database is saved to another location.</span></span> <span data-ttu-id="377e3-248">送信を含めるし、受信図形を Oracle データベースにメッセージを送信し、それぞれ、応答を受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="377e3-248">You must include Send and Receive shapes to send messages to Oracle database and receive responses, respectively.</span></span> <span data-ttu-id="377e3-249">複合操作を実行するための基本的なオーケストレーションには、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="377e3-249">A basic orchestration for performing composite operations resembles the following:</span></span>  
  
 <span data-ttu-id="377e3-250">![複合操作を実行するオーケストレーション](../../adapters-and-accelerators/adapter-oracle-database/media/4a1ecae7-8bf2-4c8a-a413-34d6a402cbfb.gif "4a1ecae7-8bf2-4c8a-a413-34d6a402cbfb")</span><span class="sxs-lookup"><span data-stu-id="377e3-250">![Orchestration to peform composite operations](../../adapters-and-accelerators/adapter-oracle-database/media/4a1ecae7-8bf2-4c8a-a413-34d6a402cbfb.gif "4a1ecae7-8bf2-4c8a-a413-34d6a402cbfb")</span></span>  
  
### <a name="adding-message-shapes"></a><span data-ttu-id="377e3-251">メッセージの構築図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="377e3-251">Adding Message Shapes</span></span>  
 <span data-ttu-id="377e3-252">メッセージの構築図形のごとに、次のプロパティを指定することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="377e3-252">Make sure you specify the following properties for each of the message shapes.</span></span> <span data-ttu-id="377e3-253">図形 列に表示名は、単に記載されているオーケストレーションに表示されるメッセージの構築図形の名前です。</span><span class="sxs-lookup"><span data-stu-id="377e3-253">The names listed in the Shape column are the names of the message shapes as displayed in the just-mentioned orchestration.</span></span>  
  
|<span data-ttu-id="377e3-254">図形</span><span class="sxs-lookup"><span data-stu-id="377e3-254">Shape</span></span>|<span data-ttu-id="377e3-255">図形の種類</span><span class="sxs-lookup"><span data-stu-id="377e3-255">Shape Type</span></span>|<span data-ttu-id="377e3-256">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="377e3-256">Properties</span></span>|  
|-----------|----------------|----------------|  
|<span data-ttu-id="377e3-257">ReceiveMessage</span><span class="sxs-lookup"><span data-stu-id="377e3-257">ReceiveMessage</span></span>|<span data-ttu-id="377e3-258">Receive</span><span class="sxs-lookup"><span data-stu-id="377e3-258">Receive</span></span>|<span data-ttu-id="377e3-259">-設定**名前**に*ReceiveMessage*</span><span class="sxs-lookup"><span data-stu-id="377e3-259">-   Set **Name** to *ReceiveMessage*</span></span><br /><span data-ttu-id="377e3-260">-設定**アクティブ**に*は True。*</span><span class="sxs-lookup"><span data-stu-id="377e3-260">-   Set **Activate** to *True*</span></span>|  
|<span data-ttu-id="377e3-261">SendMessage</span><span class="sxs-lookup"><span data-stu-id="377e3-261">SendMessage</span></span>|<span data-ttu-id="377e3-262">Send</span><span class="sxs-lookup"><span data-stu-id="377e3-262">Send</span></span>|<span data-ttu-id="377e3-263">-設定**名前**に*SendMessage*</span><span class="sxs-lookup"><span data-stu-id="377e3-263">-   Set **Name** to *SendMessage*</span></span>|  
|<span data-ttu-id="377e3-264">ReceiveResponse</span><span class="sxs-lookup"><span data-stu-id="377e3-264">ReceiveResponse</span></span>|<span data-ttu-id="377e3-265">Receive</span><span class="sxs-lookup"><span data-stu-id="377e3-265">Receive</span></span>|<span data-ttu-id="377e3-266">-設定**名前**に*ReceiveResponse*</span><span class="sxs-lookup"><span data-stu-id="377e3-266">-   Set **Name** to *ReceiveResponse*</span></span><br /><span data-ttu-id="377e3-267">-設定**アクティブ**に*False*</span><span class="sxs-lookup"><span data-stu-id="377e3-267">-   Set **Activate** to *False*</span></span>|  
|<span data-ttu-id="377e3-268">SendResponse</span><span class="sxs-lookup"><span data-stu-id="377e3-268">SendResponse</span></span>|<span data-ttu-id="377e3-269">Send</span><span class="sxs-lookup"><span data-stu-id="377e3-269">Send</span></span>|<span data-ttu-id="377e3-270">-設定**名前**に*SendResponse*</span><span class="sxs-lookup"><span data-stu-id="377e3-270">-   Set **Name** to *SendResponse*</span></span>|  
  
### <a name="adding-ports"></a><span data-ttu-id="377e3-271">ポートの追加</span><span class="sxs-lookup"><span data-stu-id="377e3-271">Adding Ports</span></span>  
 <span data-ttu-id="377e3-272">論理ポートごとに、次のプロパティを指定することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="377e3-272">Make sure you specify the following properties for each of the logical ports.</span></span> <span data-ttu-id="377e3-273">ポート列に表示される名前は、オーケストレーションで表示されているポートの名前です。</span><span class="sxs-lookup"><span data-stu-id="377e3-273">The names listed in the Port column are the names of the ports as displayed in the orchestration.</span></span>  
  
|<span data-ttu-id="377e3-274">ポート</span><span class="sxs-lookup"><span data-stu-id="377e3-274">Port</span></span>|<span data-ttu-id="377e3-275">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="377e3-275">Properties</span></span>|  
|----------|----------------|  
|<span data-ttu-id="377e3-276">MessageIn</span><span class="sxs-lookup"><span data-stu-id="377e3-276">MessageIn</span></span>|<span data-ttu-id="377e3-277">-設定**識別子**に*MessageIn*</span><span class="sxs-lookup"><span data-stu-id="377e3-277">-   Set **Identifier** to *MessageIn*</span></span><br /><span data-ttu-id="377e3-278">-設定**型**に*MessageInType*</span><span class="sxs-lookup"><span data-stu-id="377e3-278">-   Set **Type** to *MessageInType*</span></span><br /><span data-ttu-id="377e3-279">-設定**通信パターン**に*一方向*</span><span class="sxs-lookup"><span data-stu-id="377e3-279">-   Set **Communication Pattern** to *One-Way*</span></span><br /><span data-ttu-id="377e3-280">-設定**通信方向**に*受信*</span><span class="sxs-lookup"><span data-stu-id="377e3-280">-   Set **Communication Direction** to *Receive*</span></span>|  
|<span data-ttu-id="377e3-281">LOBPort</span><span class="sxs-lookup"><span data-stu-id="377e3-281">LOBPort</span></span>|<span data-ttu-id="377e3-282">-設定**識別子**に*LOBPort*</span><span class="sxs-lookup"><span data-stu-id="377e3-282">-   Set **Identifier** to *LOBPort*</span></span><br /><span data-ttu-id="377e3-283">-設定**型**に*LOBPortType*</span><span class="sxs-lookup"><span data-stu-id="377e3-283">-   Set **Type** to *LOBPortType*</span></span><br /><span data-ttu-id="377e3-284">-設定**通信パターン**に*要求-応答*</span><span class="sxs-lookup"><span data-stu-id="377e3-284">-   Set **Communication Pattern** to *Request-Response*</span></span><br /><span data-ttu-id="377e3-285">-設定**通信方向**に*送受信*</span><span class="sxs-lookup"><span data-stu-id="377e3-285">-   Set **Communication Direction** to *Send-Receive*</span></span>|  
|<span data-ttu-id="377e3-286">ResponseOut</span><span class="sxs-lookup"><span data-stu-id="377e3-286">ResponseOut</span></span>|<span data-ttu-id="377e3-287">-設定**識別子**に*ResponseOut*</span><span class="sxs-lookup"><span data-stu-id="377e3-287">-   Set **Identifier** to *ResponseOut*</span></span><br /><span data-ttu-id="377e3-288">-設定**型**に*ResponseOutType*</span><span class="sxs-lookup"><span data-stu-id="377e3-288">-   Set **Type** to *ResponseOutType*</span></span><br /><span data-ttu-id="377e3-289">-設定**通信パターン**に*一方向*</span><span class="sxs-lookup"><span data-stu-id="377e3-289">-   Set **Communication Pattern** to *One-Way*</span></span><br /><span data-ttu-id="377e3-290">-設定**通信方向**に*送信*</span><span class="sxs-lookup"><span data-stu-id="377e3-290">-   Set **Communication Direction** to *Send*</span></span>|  
  
### <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a><span data-ttu-id="377e3-291">アクション図形のメッセージを指定して、ポートへの接続</span><span class="sxs-lookup"><span data-stu-id="377e3-291">Specify Messages for Action Shapes, and Connect Them to Ports</span></span>  
 <span data-ttu-id="377e3-292">次の表は、プロパティとアクション図形のメッセージを指定して、メッセージ、ポートにリンクを設定する必要があります、値を指定します。</span><span class="sxs-lookup"><span data-stu-id="377e3-292">The following table specifies the properties and their values that you should set to specify messages for action shapes and to link the messages to the ports.</span></span> <span data-ttu-id="377e3-293">図形 列に表示名は、既に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。</span><span class="sxs-lookup"><span data-stu-id="377e3-293">The names listed in the Shape column are the names of the message shapes as displayed in the orchestration mentioned earlier.</span></span>  
  
|<span data-ttu-id="377e3-294">図形</span><span class="sxs-lookup"><span data-stu-id="377e3-294">Shape</span></span>|<span data-ttu-id="377e3-295">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="377e3-295">Properties</span></span>|  
|-----------|----------------|  
|<span data-ttu-id="377e3-296">ReceiveMessage</span><span class="sxs-lookup"><span data-stu-id="377e3-296">ReceiveMessage</span></span>|<span data-ttu-id="377e3-297">-設定**メッセージ**に*要求*</span><span class="sxs-lookup"><span data-stu-id="377e3-297">-   Set **Message** to *Request*</span></span><br /><span data-ttu-id="377e3-298">-設定**操作**に*MessageIn.CompositeOp.Request*</span><span class="sxs-lookup"><span data-stu-id="377e3-298">-   Set **Operation** to *MessageIn.CompositeOp.Request*</span></span>|  
|<span data-ttu-id="377e3-299">SendMessage</span><span class="sxs-lookup"><span data-stu-id="377e3-299">SendMessage</span></span>|<span data-ttu-id="377e3-300">-設定**メッセージ**に*要求*</span><span class="sxs-lookup"><span data-stu-id="377e3-300">-   Set **Message** to *Request*</span></span><br /><span data-ttu-id="377e3-301">-設定**操作**に*LOBPort.CompositeOp.Request*</span><span class="sxs-lookup"><span data-stu-id="377e3-301">-   Set **Operation** to *LOBPort.CompositeOp.Request*</span></span>|  
|<span data-ttu-id="377e3-302">ReceiveResponse</span><span class="sxs-lookup"><span data-stu-id="377e3-302">ReceiveResponse</span></span>|<span data-ttu-id="377e3-303">-設定**メッセージ**に*応答*</span><span class="sxs-lookup"><span data-stu-id="377e3-303">-   Set **Message** to *Response*</span></span><br /><span data-ttu-id="377e3-304">-設定**操作**に*LOBPort.CompositeOp.Response*</span><span class="sxs-lookup"><span data-stu-id="377e3-304">-   Set **Operation** to *LOBPort.CompositeOp.Response*</span></span>|  
|<span data-ttu-id="377e3-305">SendResponse</span><span class="sxs-lookup"><span data-stu-id="377e3-305">SendResponse</span></span>|<span data-ttu-id="377e3-306">-設定**メッセージ**に*応答*</span><span class="sxs-lookup"><span data-stu-id="377e3-306">-   Set **Message** to *Response*</span></span><br /><span data-ttu-id="377e3-307">-設定**操作**に*ResponseOut.CompositeOp.Request*</span><span class="sxs-lookup"><span data-stu-id="377e3-307">-   Set **Operation** to *ResponseOut.CompositeOp.Request*</span></span>|  
  
 <span data-ttu-id="377e3-308">これらのプロパティを指定した後、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。</span><span class="sxs-lookup"><span data-stu-id="377e3-308">After you have specified these properties, the message shapes and ports are connected and your orchestration is complete.</span></span>  
  
 <span data-ttu-id="377e3-309">今すぐ BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="377e3-309">You must now build the BizTalk solution and deploy it to a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="377e3-310">詳細については、次を参照してください。[のビルドおよび実行されているオーケストレーション](../../core/building-and-running-orchestrations.md)です。</span><span class="sxs-lookup"><span data-stu-id="377e3-310">For more information, see [Building and Running Orchestrations](../../core/building-and-running-orchestrations.md).</span></span>  
  
## <a name="configuring-the-biztalk-application"></a><span data-ttu-id="377e3-311">BizTalk アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="377e3-311">Configuring the BizTalk Application</span></span>  
 <span data-ttu-id="377e3-312">[オーケストレーション] ペインで以前に作成したオーケストレーションが表示されている BizTalk プロジェクトを配置した後、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="377e3-312">After you have deployed the BizTalk project, the orchestration you created earlier is listed under the Orchestrations pane in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="377e3-313">使用する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="377e3-313">You must use the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to configure the application.</span></span> <span data-ttu-id="377e3-314">チュートリアルについては、次を参照してください。[チュートリアル: 基本的な BizTalk アプリケーションの展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)です。</span><span class="sxs-lookup"><span data-stu-id="377e3-314">For a walkthrough, see [Walkthrough: Deploying a Basic BizTalk Application](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).</span></span>
  
 <span data-ttu-id="377e3-315">アプリケーションの構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="377e3-315">Configuring an application involves:</span></span>  
  
-   <span data-ttu-id="377e3-316">アプリケーションのホストを選択します。</span><span class="sxs-lookup"><span data-stu-id="377e3-316">Selecting a host for the application.</span></span>  
  
-   <span data-ttu-id="377e3-317">物理ポートにオーケストレーションで作成したポートのマッピング、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="377e3-317">Mapping the ports that you created in your orchestration to physical ports in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="377e3-318">このオーケストレーションの次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="377e3-318">For this orchestration you must:</span></span>  
  
    -   <span data-ttu-id="377e3-319">ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポート上の場所を定義します。</span><span class="sxs-lookup"><span data-stu-id="377e3-319">Define a location on the hard disk and a corresponding file port where you will drop a request message.</span></span> <span data-ttu-id="377e3-320">BizTalk オーケストレーションは、要求メッセージを消費し、Oracle データベースに送信します。</span><span class="sxs-lookup"><span data-stu-id="377e3-320">The BizTalk orchestration will consume the request message and send it to Oracle database.</span></span>  
  
    -   <span data-ttu-id="377e3-321">ハード ディスクと、対応する file ポートを BizTalk オーケストレーションが Oracle データベースからの応答を含む応答メッセージをドロップする場所に場所を定義します。</span><span class="sxs-lookup"><span data-stu-id="377e3-321">Define a location on the hard disk and a corresponding file port where the BizTalk orchestration will drop the response message containing the response from Oracle database.</span></span>  
  
    -   <span data-ttu-id="377e3-322">Oracle データベースにメッセージを送信する物理 Wcf-custom または Wcf-oracledb 送信ポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="377e3-322">Define a physical WCF-Custom or WCF-OracleDB send port to send messages to Oracle database.</span></span> <span data-ttu-id="377e3-323">操作の場合は、単一のトランザクションで複合操作の一部が実行されるとしていることを確認するため、 **UseAmbientTransaction**に設定されているプロパティのバインド**True**です。</span><span class="sxs-lookup"><span data-stu-id="377e3-323">Because the operations that are being as part of the composite operation are executed in a single transaction, make sure the **UseAmbientTransaction** binding property is set to **True**.</span></span>  
  
         <span data-ttu-id="377e3-324">送信ポートでアクションを指定することもあります。</span><span class="sxs-lookup"><span data-stu-id="377e3-324">You must also specify the action in the send port.</span></span> <span data-ttu-id="377e3-325">複合操作のアクションは、"http://Microsoft.LobServices.OracleDB/2007/03/CompositeOperation"です。</span><span class="sxs-lookup"><span data-stu-id="377e3-325">The action for a composite operation is “http://Microsoft.LobServices.OracleDB/2007/03/CompositeOperation”.</span></span> <span data-ttu-id="377e3-326">ポートを作成する方法については、次を参照してください。 [Oracle データベース アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="377e3-326">For information about how to create ports, see [Manually configure a physical port binding to the Oracle Database Adapter](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md).</span></span> <span data-ttu-id="377e3-327">ポートのアクションを指定する方法の詳細については、次を参照してください。 [Oracle データベースの SOAP アクションを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-soap-action-for-oracle-database.md)です。</span><span class="sxs-lookup"><span data-stu-id="377e3-327">For more information about how to specify actions for ports, see [Configure the SOAP action for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-soap-action-for-oracle-database.md).</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="377e3-328">使用してスキーマを生成する、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。</span><span class="sxs-lookup"><span data-stu-id="377e3-328">Generating the schema using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] also creates a binding file that contains information about the ports and the actions to be set for those ports.</span></span> <span data-ttu-id="377e3-329">このバインド ファイルをインポートすることができます、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] (着信) の受信ポートを (発信) の送信ポートを作成または管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="377e3-329">You can import this binding file from the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to create send ports (for outbound calls) or receive ports (for inbound calls).</span></span> <span data-ttu-id="377e3-330">詳細については、次を参照してください。 [Oracle データベースへのポートのバインド ファイルを使用して物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)です。</span><span class="sxs-lookup"><span data-stu-id="377e3-330">For more information, see [Configure a physical port binding using a port binding file to Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md).</span></span> <span data-ttu-id="377e3-331">選択したすべての操作に関連する動的なアクションには、送信ポートでアクションが設定されているこのバインド ファイルをインポートする場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]スキーマの生成中にします。</span><span class="sxs-lookup"><span data-stu-id="377e3-331">If you import this binding file, the action on the send port is set to a dynamic action involving all the operations you selected in the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] while generating the schema.</span></span> <span data-ttu-id="377e3-332">複合操作では、"http://Microsoft.LobServices.OracleDB/2007/03/CompositeOperation"がある動的アクションを置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="377e3-332">For a composite operation, you must replace the dynamic action with “http://Microsoft.LobServices.OracleDB/2007/03/CompositeOperation”.</span></span>  
  
## <a name="starting-the-application"></a><span data-ttu-id="377e3-333">アプリケーションの起動</span><span class="sxs-lookup"><span data-stu-id="377e3-333">Starting the Application</span></span>  
 <span data-ttu-id="377e3-334">Oracle データベースでの複合操作を実行する BizTalk アプリケーションを起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="377e3-334">You must start the BizTalk application for performing composite operations on Oracle database.</span></span> <span data-ttu-id="377e3-335">BizTalk アプリケーションの起動方法の詳細については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)です。</span><span class="sxs-lookup"><span data-stu-id="377e3-335">For instructions on starting a BizTalk application, see [How to Start an Orchestration](../../core/how-to-start-an-orchestration.md).</span></span>  
  
 <span data-ttu-id="377e3-336">この段階で確認します。</span><span class="sxs-lookup"><span data-stu-id="377e3-336">At this stage, make sure:</span></span>  
  
-   <span data-ttu-id="377e3-337">ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。</span><span class="sxs-lookup"><span data-stu-id="377e3-337">The FILE receive port to receive request messages for the orchestration is running.</span></span>  
  
-   <span data-ttu-id="377e3-338">オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。</span><span class="sxs-lookup"><span data-stu-id="377e3-338">The FILE send port to receive the response messages from the orchestration is running.</span></span>  
  
-   <span data-ttu-id="377e3-339">Oracle データベースにメッセージを送信する Wcf-custom または Wcf-oracledb 送信ポートが実行されています。</span><span class="sxs-lookup"><span data-stu-id="377e3-339">The WCF-Custom or WCF-OracleDB send port to send messages to Oracle database is running.</span></span>  
  
-   <span data-ttu-id="377e3-340">操作の BizTalk オーケストレーションが実行されています。</span><span class="sxs-lookup"><span data-stu-id="377e3-340">The BizTalk orchestration for the operation is running.</span></span>  
  
## <a name="executing-the-operation"></a><span data-ttu-id="377e3-341">操作の実行</span><span class="sxs-lookup"><span data-stu-id="377e3-341">Executing the Operation</span></span>  
 <span data-ttu-id="377e3-342">アプリケーションを実行した後、ファイルに要求メッセージをドロップする必要がありますの受信場所。</span><span class="sxs-lookup"><span data-stu-id="377e3-342">After you run the application, you must drop a request message to the FILE receive location.</span></span> <span data-ttu-id="377e3-343">要求メッセージのスキーマは、先ほど作成した複合操作のスキーマに準拠する必要があります。</span><span class="sxs-lookup"><span data-stu-id="377e3-343">The schema for the request message must conform to the schema for the composite operations you created earlier.</span></span> <span data-ttu-id="377e3-344">たとえば、ACCOUNTACTIVITY テーブルにレコードを挿入、GET_ALL_ACTIVITY ストアド プロシージャを呼び出すし、ACCOUNTACTIVITY テーブルからレコードを削除する要求メッセージには。</span><span class="sxs-lookup"><span data-stu-id="377e3-344">For example, a request message that inserts a record in the ACCOUNTACTIVITY table, invokes the GET_ALL_ACTIVITY stored procedure, and deletes a record from the ACCOUNTACTIVITY table is:</span></span>  
  
```  
<Request xmlns="http://Composite_Op.CompositeSchema">  
  <Insert xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY">  
    <RECORDSET>  
      <ACCOUNTACTIVITYRECORDINSERT>  
        <TID>1</TID>  
        <ACCOUNT>100001</ACCOUNT>  
        <AMOUNT>1500</AMOUNT>  
        <DESCRIPTION></DESCRIPTION>  
        <TRANSDATE>2008-06-21T15:52:19</TRANSDATE>  
        <PROCESSED>n</PROCESSED>  
      </ACCOUNTACTIVITYRECORDINSERT >  
    </RECORDSET>  
  </Insert>  
  <GET_ALL_ACTIVITY xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG"/>  
  <Delete xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY">  
    <FILTER>WHERE AMOUNT = 1500</FILTER>  
  </Delete>  
</Request>  
```  
  
 <span data-ttu-id="377e3-345">上記の要求メッセージは、最初のレコードを挿入して、ACCOUNTACTIVITY テーブルのすべてのレコードを取得する GET_ALL_ACTIVITY プロシージャを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="377e3-345">The preceding request message first inserts a record and then invokes the GET_ALL_ACTIVITY procedure to get all the records in the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="377e3-346">次に、挿入されたレコードは、フィルター句を指定することによって削除されます。</span><span class="sxs-lookup"><span data-stu-id="377e3-346">Then, the inserted record is deleted by specifying a FILTER clause.</span></span> <span data-ttu-id="377e3-347">参照してください[複合操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-composite-operation2.md)Oracle に対する複合操作を実行するための要求メッセージ スキーマの詳細については、データベースを使用して、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="377e3-347">See [Message Schemas for the Composite Operation](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-composite-operation2.md) for more information about the request message schema for performing composite operations on Oracle database using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
 <span data-ttu-id="377e3-348">オーケストレーションはメッセージを使用して、Oracle データベースに送信します。</span><span class="sxs-lookup"><span data-stu-id="377e3-348">The orchestration consumes the message and sends it to Oracle database.</span></span> <span data-ttu-id="377e3-349">Oracle データベースからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。</span><span class="sxs-lookup"><span data-stu-id="377e3-349">The response from Oracle database is saved at the other FILE location defined as part of the orchestration.</span></span> <span data-ttu-id="377e3-350">たとえば、次のよう、上記の要求メッセージ用の Oracle データベースからの応答。</span><span class="sxs-lookup"><span data-stu-id="377e3-350">For example, the response from Oracle database for the preceding request message resembles the following:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<RequestResponse xmlns="http://Composite_Op.CompositeSchema">  
  <InsertResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOOT/Table/ACCOUNTACTIVITY">  
    <InsertResult>1</InsertResult>   
  </InsertResponse>  
  <GET_ALL_ACTIVITYResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
    <ALLRECS>  
      <xs:schema id="NewDataSet" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
        <xs:element msdata:IsDataSet="true" name="NewDataSet">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element minOccurs="0" maxOccurs="unbounded" name="NewTable">  
                <xs:complexType>  
                  <xs:sequence>  
                    <xs:element minOccurs="0" name="TID" type="xs:decimal" />   
                    <xs:element minOccurs="0" name="ACCOUNT" type="xs:decimal" />   
                    <xs:element minOccurs="0" name="AMOUNT" type="xs:decimal" />   
                    <xs:element minOccurs="0" name="DESCRIPTION" type="xs:string" />   
                    <xs:element minOccurs="0" name="TRANSDATE" type="xs:dateTime" />   
                    <xs:element minOccurs="0" name="PROCESSED" type="xs:string" />   
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
            ......   
            ......   
          </NewTable>  
          ......  
          ......  
          <NewTable>  
            <TID>10</TID>   
            <ACCOUNT>100001</ACCOUNT>   
            <AMOUNT>1000</AMOUNT>   
            <TRANSDATE>2008-07-28T21:39:57</TRANSDATE>   
            <PROCESSED>n</PROCESSED>   
          </NewTable>  
        </NewDataSet>  
      </diffgr:diffgram>  
    </ALLRECS>  
  </GET_ALL_ACTIVITYResponse>  
  <DeleteResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY">  
    <DeleteResult>1</DeleteResult>   
  </DeleteResponse>  
</RequestResponse>  
```  
  
 <span data-ttu-id="377e3-351">前の応答には、複合操作の一部として実行されるさまざまな操作を対応する複数の結果セットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="377e3-351">The preceding response contains multiple result sets corresponding the different operations performed as part of the composite operation.</span></span> <span data-ttu-id="377e3-352">たとえば、`InsertResult`要素には、'1'、挿入操作によって挿入された行の数を示すが含まれています。</span><span class="sxs-lookup"><span data-stu-id="377e3-352">For example, the `InsertResult` element contains ‘1’, indicating the number of rows inserted by the Insert operation.</span></span> <span data-ttu-id="377e3-353">同様に、`DeleteResult`要素には、'1'、削除操作によって削除された行の数を示すが含まれています。</span><span class="sxs-lookup"><span data-stu-id="377e3-353">Similarly, the `DeleteResult` element contains ‘1’, indicating the number of rows deleted by the Delete operation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="377e3-354">複合操作を実行中にタイムアウトの問題が発生した場合、可能性があります接続の数が関係する複合操作の操作の数より少ない。</span><span class="sxs-lookup"><span data-stu-id="377e3-354">If you experience time-out issues while executing a composite operation then it could be because the number of connections is less than the number of operations in a composite operation involving:</span></span>  
>   
>  -   <span data-ttu-id="377e3-355">BFILE、BLOB、CLOB、NCLOB、および REF CURSOR とアウトを含むストアド プロシージャまたは IN OUT パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="377e3-355">Stored procedures containing BFILE, BLOB, CLOB, NCLOB, and REF CURSOR as OUT or IN OUT parameters.</span></span>  
> -   <span data-ttu-id="377e3-356">操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="377e3-356">Select operation.</span></span>  
>   
>  <span data-ttu-id="377e3-357">この問題を解決するには、ある複合操作では、このような操作の"n"の数がある場合は、指定した値を確認する必要があります、 **MinPoolSize** "n+1"プロパティのバインドは以上です。</span><span class="sxs-lookup"><span data-stu-id="377e3-357">To resolve this issue, you must ensure that if there are “n” number of such operations in a composite operation, the value specified for the **MinPoolSize** binding property is “n+1” or greater.</span></span> <span data-ttu-id="377e3-358">詳細については、 **MinPoolSize**バインディング プロパティを参照してください[バインドのプロパティの使用](https://msdn.microsoft.com/library/dd788467.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="377e3-358">For more information about the **MinPoolSize** binding property, see [Working with binding properties](https://msdn.microsoft.com/library/dd788467.aspx).</span></span>  
  
## <a name="best-practices"></a><span data-ttu-id="377e3-359">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="377e3-359">Best Practices</span></span>  
 <span data-ttu-id="377e3-360">展開して、BizTalk プロジェクトを構成することが後、は、バインド ファイルと呼ばれる XML ファイルに構成設定をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="377e3-360">After you have deployed and configured the BizTalk project, you can export configuration settings to an XML file called the binding file.</span></span> <span data-ttu-id="377e3-361">バインド ファイルを生成したできるように、送信ポートなどの項目を作成し、同じオーケストレーション用のポートを受信する必要はありません、ファイルから構成設定をインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="377e3-361">Once you generate a binding file, you can import the configuration settings from the file, so that you do not need to create items such as send ports and receive ports for the same orchestration.</span></span> <span data-ttu-id="377e3-362">バインド ファイルの詳細については、次を参照してください。[アダプターのバインドが Oracle データベースの再利用](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)です。</span><span class="sxs-lookup"><span data-stu-id="377e3-362">For more information about binding files, see [Reuse Oracle Database adapter bindings](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="377e3-363">参照</span><span class="sxs-lookup"><span data-stu-id="377e3-363">See Also</span></span>  
[<span data-ttu-id="377e3-364">Oracle データベースと BizTalk アプリケーションを開発する構成要素</span><span class="sxs-lookup"><span data-stu-id="377e3-364">Building Blocks to Develop BizTalk Applications with Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)