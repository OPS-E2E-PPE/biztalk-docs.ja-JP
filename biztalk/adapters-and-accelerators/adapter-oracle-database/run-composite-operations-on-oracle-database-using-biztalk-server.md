---
title: BizTalk Server を使用して Oracle データベースでの複合操作の実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bf47d95e-cdf1-4c9b-a15a-7cf123d0ea6d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e213421e7b97f6b8152be05830a381bd44e441d3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376110"
---
# <a name="run-composite-operations-on-oracle-database-using-biztalk-server"></a><span data-ttu-id="0fcd5-102">BizTalk Server を使用して Oracle データベースでの複合操作の実行します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-102">Run Composite Operations on Oracle Database using BizTalk Server</span></span>
<span data-ttu-id="0fcd5-103">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アダプター クライアントが Oracle データベースでの複合操作を実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-103">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] enables adapter clients to perform composite operations on Oracle database.</span></span> <span data-ttu-id="0fcd5-104">複合操作を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-104">A composite operation can include:</span></span>  

- <span data-ttu-id="0fcd5-105">挿入、更新、削除、およびテーブルとビューで操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-105">Insert, Update, Delete, and Select operations on tables and views.</span></span>  

- <span data-ttu-id="0fcd5-106">ストアド プロシージャおよび関数、内部または外部パッケージ。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-106">Stored procedures and functions, inside or outside a package.</span></span>  

  <span data-ttu-id="0fcd5-107">1 つの複合操作では、任意の順序でこれらの操作の任意の数を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-107">A single composite operation can have any number of these operations, in any order.</span></span> <span data-ttu-id="0fcd5-108">たとえば、2 つの insert、delete、および最後に、ストアド プロシージャの実行後にすることができます。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-108">For example, you can have two inserts followed by a delete, and finally a stored procedure execution.</span></span> <span data-ttu-id="0fcd5-109">また、さまざまなオペレーションを別のデータベース テーブルまたはビューを対象とすることができます。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-109">Also, you can have different operations targeting different database tables or views.</span></span> <span data-ttu-id="0fcd5-110">アダプターが複合操作をサポートする方法の詳細については、次を参照してください。 [Oracle データベースで複合操作を実行する](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-in-oracle-database.md)します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-110">For more information about how the adapter supports composite operations, see [Performing Composite Operations in Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-in-oracle-database.md).</span></span> <span data-ttu-id="0fcd5-111">複合操作の SOAP メッセージの構造については、次を参照してください。[複合操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-composite-operation2.md)します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-111">For information about the structure of the SOAP message for composite operations, see [Message Schemas for the Composite Operation](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-composite-operation2.md).</span></span>  

## <a name="how-to-perform-composite-operations-on-oracle-database"></a><span data-ttu-id="0fcd5-112">Oracle データベースでの複合操作を実行する方法は?</span><span class="sxs-lookup"><span data-stu-id="0fcd5-112">How to Perform Composite Operations on Oracle Database?</span></span>  
 <span data-ttu-id="0fcd5-113">使用して Oracle データベースでの操作を実行する[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明されている手順のタスクが含まれます[Oracle データベースと BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-113">Performing an operation on Oracle database using [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] involves procedural tasks described in [Building blocks to develop BizTalk Applications with Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md).</span></span> <span data-ttu-id="0fcd5-114">これらのタスクは Oracle database での複合操作を行うには。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-114">To perform composite operations on Oracle database, these tasks are:</span></span>  

1. <span data-ttu-id="0fcd5-115">BizTalk プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を呼び出したいすべての操作のスキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-115">Create a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and generate schema for all the operations you want to invoke.</span></span>  

2. <span data-ttu-id="0fcd5-116">前の手順で生成したすべてのスキーマへの参照が含まれるスキーマ ファイルを手動で作成します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-116">Manually create a schema file that includes references to all the schemas you generated in the previous step.</span></span>  

3. <span data-ttu-id="0fcd5-117">Oracle データベースからメッセージを送受信するための BizTalk プロジェクトでは、メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-117">Create messages in the BizTalk project for sending and receiving messages from Oracle database.</span></span> <span data-ttu-id="0fcd5-118">これらのメッセージは、前の手順で作成した要求と応答のスキーマに準拠する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-118">These messages must conform to the request and response schema you created in the previous step.</span></span>  

4. <span data-ttu-id="0fcd5-119">Oracle データベースでの複合操作を呼び出すオーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-119">Create an orchestration to invoke the composite operation on Oracle database.</span></span>  

5. <span data-ttu-id="0fcd5-120">ビルドし、BizTalk プロジェクトを配置します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-120">Build and deploy the BizTalk project.</span></span>  

6. <span data-ttu-id="0fcd5-121">BizTalk 物理を作成してアプリケーションの送信および受信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-121">Configure the BizTalk application by creating physical send and receive ports.</span></span>  

7. <span data-ttu-id="0fcd5-122">BizTalk アプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-122">Start the BizTalk application.</span></span>  

   <span data-ttu-id="0fcd5-123">このトピックでは、これらのタスクを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-123">This topic provides instructions on how to perform these tasks.</span></span>  

## <a name="generating-schema"></a><span data-ttu-id="0fcd5-124">スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-124">Generating Schema</span></span>  
 <span data-ttu-id="0fcd5-125">このトピックでは、複合操作を実行する方法を示すに、同じ順序で、次のタスクが実行しますされます。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-125">In this topic, to demonstrate how to perform composite operations, we will perform the following tasks in the same order:</span></span>  

- <span data-ttu-id="0fcd5-126">ACCOUNTACTIVITY テーブルにレコードを挿入します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-126">Insert record into the ACCOUNTACTIVITY table.</span></span>  

- <span data-ttu-id="0fcd5-127">ACCOUNT_PKG パッケージ内で GET_ALL_ACTIVITY プロシージャを呼び出すことによって、ACCOUNTACTIVITY テーブル内のすべてのレコードを取得します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-127">Retrieve all the records in the ACCOUNTACTIVITY table by invoking the GET_ALL_ACTIVITY procedure within the ACCOUNT_PKG package.</span></span>  

- <span data-ttu-id="0fcd5-128">ACCOUNTACTIVITY テーブルからレコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-128">Delete the record from the ACCOUNTACTIVITY table.</span></span>  

  <span data-ttu-id="0fcd5-129">ACCOUNTACTIVITY テーブルを作成するサンプルに付属のスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-129">Run the scripts provided with the samples to create the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="0fcd5-130">サンプルの詳細については、次を参照してください。[スキーマのサンプル](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-130">For more information about the samples, see [Schema Samples](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md).</span></span>  

  <span data-ttu-id="0fcd5-131">BizTalk プロジェクトを作成して使用する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-131">You must create a BizTalk project and use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] to generate the schema.</span></span> <span data-ttu-id="0fcd5-132">参照してください[Visual Studio での Oracle データベース操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)スキーマを生成する方法についての詳細。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-132">See [Retrieve metadata for Oracle Database operations in Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md) for more information about how to generate schemas.</span></span>  

## <a name="creating-a-composite-schema-definition"></a><span data-ttu-id="0fcd5-133">複合のスキーマ定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-133">Creating a Composite Schema Definition</span></span>  
 <span data-ttu-id="0fcd5-134">複合でスキーマを作成する必要が今すぐ、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]個々 の操作用に作成したスキーマを参照する BizTalk プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-134">You must now create a composite schema in the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] BizTalk project that references the schemas you created for the individual operations.</span></span> <span data-ttu-id="0fcd5-135">複合のスキーマ定義を作成する次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-135">Perform the following steps to create a composite schema definition.</span></span>  

#### <a name="to-add-a-composite-schema-definition"></a><span data-ttu-id="0fcd5-136">複合のスキーマ定義を追加するには</span><span class="sxs-lookup"><span data-stu-id="0fcd5-136">To add a composite schema definition</span></span>  

1. <span data-ttu-id="0fcd5-137">BizTalk プロジェクトにスキーマ ファイルを追加[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-137">Add a schema file to the BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="0fcd5-138">ソリューション名を右クリックし、[**追加**、] をクリックし、**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-138">Right-click the solution name, point to **Add**, and then click **New Item**.</span></span> <span data-ttu-id="0fcd5-139">**新しい項目の追加**] ダイアログ ボックスから、**カテゴリ**ボックスで、[**スキーマ ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-139">In the **Add New Item** dialog box, from the **Categories** box, click **Schema Files**.</span></span> <span data-ttu-id="0fcd5-140">**テンプレート**ボックスで、**スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-140">From the **Templates** box, click **Schema**.</span></span> <span data-ttu-id="0fcd5-141">スキーマ ファイルの名前を指定し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-141">Specify a name for the schema file and click **OK**.</span></span>  

    <span data-ttu-id="0fcd5-142">この例で、スキーマ ファイル名を指定`CompositeSchema.xsd`します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-142">For this example, specify the schema file name as `CompositeSchema.xsd`.</span></span>  

2. <span data-ttu-id="0fcd5-143">実行するさまざまな操作の生成スキーマへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-143">Add references to the schema generated for the different operations that you want to perform.</span></span> <span data-ttu-id="0fcd5-144">この例では、操作に対して生成されたさまざまなスキーマは。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-144">In this example, the different schemas generated for operations are:</span></span>  

   - <span data-ttu-id="0fcd5-145">OracleDBBinding.xsd、ACCOUNTACTIVITY テーブルに対する Insert および Delete の操作。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-145">OracleDBBinding.xsd, for Insert and Delete operations on ACCOUNTACTIVITY table.</span></span>  

   - <span data-ttu-id="0fcd5-146">OracleDBBinding2.xsd、GET_ALL_ACTIVITY プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-146">OracleDBBinding2.xsd, for the GET_ALL_ACTIVITY procedure.</span></span>  

     <span data-ttu-id="0fcd5-147">参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-147">To add references:</span></span>  

   1.  <span data-ttu-id="0fcd5-148">ルートを右クリックして **\<スキーマ\>** CompositeSchema.xsd をクリックしますノード**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-148">Right-click the root **\<Schema\>** node in the CompositeSchema.xsd, and click **Properties**.</span></span>  

   2.  <span data-ttu-id="0fcd5-149">**プロパティ**ボックスで、省略記号ボタンをクリックします **([...])。** に対して、 **Imports**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-149">In the **Property** box, click the ellipsis button **(…)** against the **Imports** property.</span></span>  

        <span data-ttu-id="0fcd5-150">![スキーマの定義をインポート](../../adapters-and-accelerators/adapter-oracle-database/media/d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca.gif "d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca")</span><span class="sxs-lookup"><span data-stu-id="0fcd5-150">![Import schema definitions](../../adapters-and-accelerators/adapter-oracle-database/media/d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca.gif "d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca")</span></span>  

   3.  <span data-ttu-id="0fcd5-151">**インポート**] ダイアログ ボックスから、**として新しいスキーマのインポート**一覧で、[ **XSD のインポート**、順にクリックします**追加**します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-151">In the **Imports** dialog box, from the **Import new schema as** list, select **XSD Import**, and then click **Add**.</span></span>  

   4.  <span data-ttu-id="0fcd5-152">**BizTalk 型の選択** ダイアログ ボックスで、BizTalk プロジェクト名のノードを展開し、展開**スキーマ**、しをインポートするスキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-152">In the **BizTalk Type Picker** dialog box, expand the BizTalk project name node, expand **Schemas**, and then select the schema you want to import.</span></span> <span data-ttu-id="0fcd5-153">この例では、< BizTalk_project_name > を選択します。OracleDBBinding.xsd します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-153">For this example, select <BizTalk_project_name>.OracleDBBinding.xsd.</span></span> <span data-ttu-id="0fcd5-154">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-154">Click **OK**.</span></span>  

        <span data-ttu-id="0fcd5-155">Repeat this step to import <BizTalk_project_name>.OracleDBBinding2.xsd too.</span><span class="sxs-lookup"><span data-stu-id="0fcd5-155">Repeat this step to import <BizTalk_project_name>.OracleDBBinding2.xsd too.</span></span>  

   5.  <span data-ttu-id="0fcd5-156">**インポート**ダイアログ ボックスで、をクリックして**OK**。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-156">In the **Imports** dialog box, click **OK**.</span></span>  

3. <span data-ttu-id="0fcd5-157">ルート スキーマ ノードには、2 つの子ノードを追加します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-157">Add two child nodes to the root schema node.</span></span> <span data-ttu-id="0fcd5-158">1 つの子ノードは、複合操作を実行するための要求スキーマに対応します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-158">One child node corresponds to the request schema for performing the composite operation.</span></span> <span data-ttu-id="0fcd5-159">その他の子ノードは、応答スキーマに対応します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-159">The other child node corresponds to the response schema.</span></span> <span data-ttu-id="0fcd5-160">要求スキーマに対応するノードは、任意の名前を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-160">The node that corresponds to the request schema can have any name.</span></span> <span data-ttu-id="0fcd5-161">応答スキーマに対応するノードには、< request_schema_node > 応答を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-161">The node that corresponds to the response schema must be called <request_schema_node>Response.</span></span> <span data-ttu-id="0fcd5-162">この例では、要求スキーマのノードとしてを呼び出し、**要求**します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-162">For this example, we will call the request schema node as **Request**.</span></span> <span data-ttu-id="0fcd5-163">そのため、応答スキーマのノードと呼びます**RequestResponse**します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-163">So, the response schema node is called **RequestResponse**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="0fcd5-164">既定で、**ルート**ノードは、新しいスキーマ ファイルにも追加されます。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-164">By default, a **Root** node is also added to a new schema file.</span></span> <span data-ttu-id="0fcd5-165">名前を変更することができます、**ルート**ノード**要求**します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-165">You can rename the **Root** node to **Request**.</span></span> <span data-ttu-id="0fcd5-166">ノードの名前を変更するノード名を右クリックし、をクリックして**の名前を変更**します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-166">To rename a node, right-click the node name and click **Rename**.</span></span>  

    <span data-ttu-id="0fcd5-167">下のノードを追加する、 **\<スキーマ\>** ノード。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-167">To add a node under the **\<Schema\>** node:</span></span>  

   1.  <span data-ttu-id="0fcd5-168">右クリックし、 **\<スキーマ\>** に**スキーマ ノードの挿入**、 をクリック**子レコード**します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-168">Right-click the **\<Schema\>** node, point to **Insert Schema Node**, and click **Child Record**.</span></span>  

   2.  <span data-ttu-id="0fcd5-169">新しいノードの名前を変更**RequestResponse**します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-169">Rename the new node to **RequestResponse**.</span></span>  

4. <span data-ttu-id="0fcd5-170">下の子ノードを追加、**要求**複合操作の一部として実行する各操作の要求スキーマに対応するノード。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-170">Add child nodes under the **Request** node that correspond to the request schema for each operation that you will perform as part of the composite operation.</span></span> <span data-ttu-id="0fcd5-171">この例では、次に対応する子ノードを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-171">For this example, you must add child nodes corresponding to the following:</span></span>  

   -   <span data-ttu-id="0fcd5-172">挿入し、ACCOUNTACTIVITY テーブルに対する操作を削除します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-172">Insert and Delete operations on the ACCOUNTACTIVITY table.</span></span>  

   -   <span data-ttu-id="0fcd5-173">GET_ALL_ACTIVITY プロシージャです。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-173">GET_ALL_ACTIVITY procedure.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="0fcd5-174">操作を実行するのと同じ順序でノードを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-174">You must add the nodes in the same order in which you want to perform the operations.</span></span> <span data-ttu-id="0fcd5-175">など、レコードを挿入し、ストアド プロシージャを実行し、挿入操作のノードを追加する必要があります最初のレコードを削除する場合は、後に、ストアド プロシージャのノードと最後に、削除操作のノード。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-175">For example, if you want to insert a record, then execute a stored procedure, and then delete a record you must first add a node for the Insert operation, followed by a node for the stored procedure, and finally a node for the Delete operation.</span></span>  

    <span data-ttu-id="0fcd5-176">子ノードを追加する、**要求**ノード。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-176">To add child nodes to the **Request** node:</span></span>  

   1.  <span data-ttu-id="0fcd5-177">右クリックし、**要求**に**スキーマ ノードの挿入**、 をクリックし、**子レコード**します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-177">Right-click the **Request** node, point to **Insert Schema Node**, and then click  **Child Record**.</span></span>  

        <span data-ttu-id="0fcd5-178">![スキーマの子ノードの挿入](../../adapters-and-accelerators/adapter-oracle-database/media/58992131-13a6-45c3-9513-5c0995091fae.gif "58992131-13a6-45c3-9513-5c0995091fae")</span><span class="sxs-lookup"><span data-stu-id="0fcd5-178">![Insert child nodes for a schema](../../adapters-and-accelerators/adapter-oracle-database/media/58992131-13a6-45c3-9513-5c0995091fae.gif "58992131-13a6-45c3-9513-5c0995091fae")</span></span>  

   2.  <span data-ttu-id="0fcd5-179">複合操作の一環として実行する操作の要求スキーマに対応するレコードの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-179">Rename the record to correspond to a request schema for an operation that you perform as part of the composite operation.</span></span> <span data-ttu-id="0fcd5-180">たとえば、"Insert"するノードの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-180">For example, rename the node to “Insert”.</span></span>  

   3.  <span data-ttu-id="0fcd5-181">マップ、**挿入**ACCOUNTACTIVITY テーブルに対する挿入操作の要求スキーマのノード。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-181">Map the **Insert** node to the request schema for the Insert operation on the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="0fcd5-182">これを行うを右クリックし、**挿入**ノード、およびクリック**プロパティ**。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-182">To do so, right-click the **Insert** node, and click **Properties**.</span></span> <span data-ttu-id="0fcd5-183">**プロパティ**] ボックスから、 **Data Structure Type**一覧で、[ **Insert (リファレンス)** します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-183">In the **Properties** box, from the **Data Structure Type** list, select **Insert (Reference)**.</span></span>  

        <span data-ttu-id="0fcd5-184">![要求スキーマに子ノードをマップ](../../adapters-and-accelerators/adapter-oracle-database/media/b4ebd3c7-14e5-4c37-abd7-83f0b4db4c9e.gif "b4ebd3c7-14e5-4c37-abd7-83f0b4db4c9e")</span><span class="sxs-lookup"><span data-stu-id="0fcd5-184">![Map child nodes to request schema](../../adapters-and-accelerators/adapter-oracle-database/media/b4ebd3c7-14e5-4c37-abd7-83f0b4db4c9e.gif "b4ebd3c7-14e5-4c37-abd7-83f0b4db4c9e")</span></span>  

   4.  <span data-ttu-id="0fcd5-185">GET_ALL_ACTIVITY ストアド プロシージャと削除操作の要求スキーマのノードを追加するには、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-185">Repeat these steps to add nodes for the request schemas for GET_ALL_ACTIVITY stored procedure and the Delete operation.</span></span> <span data-ttu-id="0fcd5-186">ノード名を指定し、次の表で説明したように、それらを対応するスキーマにマップします。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-186">Specify the node names and map them to the corresponding schema as mentioned in the following table.</span></span>  

       |<span data-ttu-id="0fcd5-187">ノード名</span><span class="sxs-lookup"><span data-stu-id="0fcd5-187">Node name</span></span>|<span data-ttu-id="0fcd5-188">スキーマにマップ</span><span class="sxs-lookup"><span data-stu-id="0fcd5-188">Mapped to schema</span></span>|  
       |---------------|----------------------|  
       |<span data-ttu-id="0fcd5-189">GET_ALL_ACTIVITY</span><span class="sxs-lookup"><span data-stu-id="0fcd5-189">GET_ALL_ACTIVITY</span></span>|<span data-ttu-id="0fcd5-190">GET_ALL_ACTIVITY (リファレンス)</span><span class="sxs-lookup"><span data-stu-id="0fcd5-190">GET_ALL_ACTIVITY (Reference)</span></span>|  
       |<span data-ttu-id="0fcd5-191">DELETE</span><span class="sxs-lookup"><span data-stu-id="0fcd5-191">Delete</span></span>|<span data-ttu-id="0fcd5-192">削除 (リファレンス)</span><span class="sxs-lookup"><span data-stu-id="0fcd5-192">Delete (Reference)</span></span>|  

5. <span data-ttu-id="0fcd5-193">下の子ノードを追加、 **RequestResponse**複合操作の一部として実行する各操作の応答スキーマに対応するノード。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-193">Add child nodes under the **RequestResponse** node that correspond to the response schema for each operation that you will perform as part of the composite operation.</span></span> <span data-ttu-id="0fcd5-194">この例では、次に対応する子ノードを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-194">For this example, you must add child nodes corresponding to the following:</span></span>  

   -   <span data-ttu-id="0fcd5-195">挿入し、ACCOUNTACTIVITY テーブルに対する操作を削除します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-195">Insert and Delete operations on the ACCOUNTACTIVITY table.</span></span>  

   -   <span data-ttu-id="0fcd5-196">GET_ALL_ACTIVITY はストアド プロシージャです。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-196">GET_ALL_ACTIVITY stored procedure.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="0fcd5-197">下の子ノードと同じ順序で子ノードを追加する必要があります、**要求**ノード。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-197">You must add the child nodes in the same order as the child nodes under the **Request** node.</span></span>  

    <span data-ttu-id="0fcd5-198">子ノードを追加する、 **RequestResponse**ノード。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-198">To add child nodes to the **RequestResponse** node:</span></span>  

   1.  <span data-ttu-id="0fcd5-199">右クリックし、 **RequestResponse**に**スキーマ ノードの挿入**、 をクリック**子レコード**します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-199">Right-click the **RequestResponse** node, point to **Insert Schema Node**, and click **Child Record**.</span></span>  

   2.  <span data-ttu-id="0fcd5-200">複合操作の一環として実行する操作の応答スキーマに対応するレコードの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-200">Rename the record to correspond to a response schema for an operation that you perform as part of the composite operation.</span></span> <span data-ttu-id="0fcd5-201">たとえば、"InsertResponse"するノードの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-201">For example, rename the node to “InsertResponse”.</span></span>  

   3.  <span data-ttu-id="0fcd5-202">マップ、 **InsertResponse**を ACCOUNTACTIVITY テーブルに対する挿入操作の応答スキーマのノード。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-202">Map the **InsertResponse** node to the response schema for the Insert operation on the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="0fcd5-203">これを行うを右クリックし、 **InsertResponse**ノード、およびクリック**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-203">To do so, right-click the **InsertResponse** node, and click **Properties**.</span></span> <span data-ttu-id="0fcd5-204">**プロパティ**] ボックスから、 **Data Structure Type**一覧で、[ **InsertResponse (リファレンス)** します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-204">In the **Properties** box, from the **Data Structure Type** list, select **InsertResponse (Reference)**.</span></span>  

   4.  <span data-ttu-id="0fcd5-205">GET_ALL_ACTIVITY ストアド プロシージャと削除操作の応答スキーマのノードを追加するには、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-205">Repeat these steps to add nodes for the response schemas for the GET_ALL_ACTIVITY stored procedure and the Delete operation.</span></span> <span data-ttu-id="0fcd5-206">ノード名を指定し、次の表で説明したように、それらを対応するスキーマにマップします。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-206">Specify the node names and map them to the corresponding schema as mentioned in the following table.</span></span>  

       |<span data-ttu-id="0fcd5-207">ノード名</span><span class="sxs-lookup"><span data-stu-id="0fcd5-207">Node name</span></span>|<span data-ttu-id="0fcd5-208">スキーマにマップ</span><span class="sxs-lookup"><span data-stu-id="0fcd5-208">Mapped to schema</span></span>|  
       |---------------|----------------------|  
       |<span data-ttu-id="0fcd5-209">GET_ALL_ACTIVITYResponse</span><span class="sxs-lookup"><span data-stu-id="0fcd5-209">GET_ALL_ACTIVITYResponse</span></span>|<span data-ttu-id="0fcd5-210">GET_ALL_ACTIVITYResponse (リファレンス)</span><span class="sxs-lookup"><span data-stu-id="0fcd5-210">GET_ALL_ACTIVITYResponse (Reference)</span></span>|  
       |<span data-ttu-id="0fcd5-211">DeleteResponse</span><span class="sxs-lookup"><span data-stu-id="0fcd5-211">DeleteResponse</span></span>|<span data-ttu-id="0fcd5-212">DeleteResponse (リファレンス)</span><span class="sxs-lookup"><span data-stu-id="0fcd5-212">DeleteResponse (Reference)</span></span>|  

6. <span data-ttu-id="0fcd5-213">保存、 **CompositeSchema.xsd**ファイル。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-213">Save the **CompositeSchema.xsd** file.</span></span>  

## <a name="defining-messages-and-message-types"></a><span data-ttu-id="0fcd5-214">メッセージおよびメッセージの種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-214">Defining Messages and Message Types</span></span>  
 <span data-ttu-id="0fcd5-215">最後の手順で作成した複合スキーマでは、オーケストレーション内のメッセージに必要な「型」について説明します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-215">The composite schema that you created in the last step describes the “types” required for the messages in an orchestration.</span></span> <span data-ttu-id="0fcd5-216">メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-216">A message is typically a variable, the type for which is defined by the corresponding schema.</span></span> <span data-ttu-id="0fcd5-217">オーケストレーションのメッセージを作成し、前の手順で作成したスキーマにそれらをリンクする必要がありますようになりました。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-217">You must now create messages for the orchestration and link them to schema you created in the previous step.</span></span>  

#### <a name="to-create-messages-and-link-to-schema"></a><span data-ttu-id="0fcd5-218">メッセージを作成し、スキーマにリンクするには</span><span class="sxs-lookup"><span data-stu-id="0fcd5-218">To create messages and link to schema</span></span>  

1. <span data-ttu-id="0fcd5-219">オーケストレーションを BizTalk プロジェクトに追加[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-219">Add an orchestration to the BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="0fcd5-220">ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックして**追加**、 をクリックし、**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-220">From Solution Explorer, right-click the BizTalk project name, point to **Add**, and then click **New Item**.</span></span> <span data-ttu-id="0fcd5-221">BizTalk オーケストレーションの名前を入力し、クリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-221">Type a name for the BizTalk orchestration, and then click **Add**.</span></span>  

2. <span data-ttu-id="0fcd5-222">開いていない場合は、BizTalk プロジェクトのオーケストレーションの種類 ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-222">Open the Orchestration View window of the BizTalk project, if it is not already open.</span></span> <span data-ttu-id="0fcd5-223">これを行うには、次のようにクリックします。**ビュー**、 をポイント**その他の Windows**、順にクリックします**オーケストレーション**します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-223">To do so, click **View**, point to **Other Windows**, and then click **Orchestration View**.</span></span>  

3. <span data-ttu-id="0fcd5-224">オーケストレーション ビューで右クリックして**メッセージ**、 をクリックし、**新しいメッセージ**します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-224">In Orchestration View, right-click **Messages**, and then click **New Message**.</span></span>  

4. <span data-ttu-id="0fcd5-225">新しく作成されたメッセージを右クリックし、**プロパティ ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-225">Right-click the newly created message, and then select **Properties Window**.</span></span>  

5. <span data-ttu-id="0fcd5-226">**プロパティ**のウィンドウ、 **Message_1**次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-226">In the **Properties** pane for the **Message_1**, do the following:</span></span>  


   |   <span data-ttu-id="0fcd5-227">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0fcd5-227">Use this</span></span>   |                                                                                                                  <span data-ttu-id="0fcd5-228">目的</span><span class="sxs-lookup"><span data-stu-id="0fcd5-228">To do this</span></span>                                                                                                                   |
   |--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |  <span data-ttu-id="0fcd5-229">[Identifier]</span><span class="sxs-lookup"><span data-stu-id="0fcd5-229">Identifier</span></span>  |                                                                                                                <span data-ttu-id="0fcd5-230">「`Request`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-230">Type `Request`</span></span>                                                                                                                 |
   | <span data-ttu-id="0fcd5-231">メッセージ型</span><span class="sxs-lookup"><span data-stu-id="0fcd5-231">Message Type</span></span> | <span data-ttu-id="0fcd5-232">ドロップダウン リストから展開**スキーマ**、し、 *Composite_Op.CompositeSchema.Request*Composite_Op は、BizTalk プロジェクトの名前です。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-232">From the drop-down list, expand **Schemas**, and then select *Composite_Op.CompositeSchema.Request*, where Composite_Op is the name of your BizTalk project.</span></span> <span data-ttu-id="0fcd5-233">CompositeSchema は複合操作用に手動で作成したスキーマを示します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-233">CompositeSchema is the schema you created manually for the composite operations.</span></span> |


6. <span data-ttu-id="0fcd5-234">新しいメッセージを作成する 2 の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-234">Repeat step 2 to create a new message.</span></span> <span data-ttu-id="0fcd5-235">**プロパティ**ウィンドウで、新しいメッセージの場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-235">In the **Properties** pane for the new message, do the following:</span></span>  

   |<span data-ttu-id="0fcd5-236">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0fcd5-236">Use this</span></span>|<span data-ttu-id="0fcd5-237">目的</span><span class="sxs-lookup"><span data-stu-id="0fcd5-237">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="0fcd5-238">[Identifier]</span><span class="sxs-lookup"><span data-stu-id="0fcd5-238">Identifier</span></span>|<span data-ttu-id="0fcd5-239">「`Response`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-239">Type `Response`</span></span>|  
   |<span data-ttu-id="0fcd5-240">メッセージ型</span><span class="sxs-lookup"><span data-stu-id="0fcd5-240">Message Type</span></span>|<span data-ttu-id="0fcd5-241">ドロップダウン リストから展開**スキーマ**、し、 *Composite_Op.CompositeSchema.RequestResponse*します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-241">From the drop-down list, expand **Schemas**, and then select *Composite_Op.CompositeSchema.RequestResponse*.</span></span>|  

## <a name="setting-up-the-orchestration"></a><span data-ttu-id="0fcd5-242">オーケストレーションのセットアップ</span><span class="sxs-lookup"><span data-stu-id="0fcd5-242">Setting up the Orchestration</span></span>  
 <span data-ttu-id="0fcd5-243">使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Oracle database での複合操作を実行するためです。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-243">You must create a BizTalk orchestration to use [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] for performing composite operations on Oracle database.</span></span> <span data-ttu-id="0fcd5-244">このオーケストレーションでの要求メッセージを削除する、定義されている受信場所。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-244">In this orchestration, you drop a request message at a defined receive location.</span></span> <span data-ttu-id="0fcd5-245">要求メッセージは、先ほど作成した複合スキーマに準拠する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-245">The request message must conform to the composite schema you created earlier.</span></span> <span data-ttu-id="0fcd5-246">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]がこのメッセージを使用して、Oracle データベースに渡します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-246">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] consumes this message and passes it on to Oracle database.</span></span> <span data-ttu-id="0fcd5-247">Oracle データベースからの応答は、別の場所に保存されます。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-247">The response from Oracle database is saved to another location.</span></span> <span data-ttu-id="0fcd5-248">送信を含めるし、受信図形を Oracle データベースにメッセージを送信し、それぞれ、応答を受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-248">You must include Send and Receive shapes to send messages to Oracle database and receive responses, respectively.</span></span> <span data-ttu-id="0fcd5-249">複合操作を実行するための基本的なオーケストレーションには、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-249">A basic orchestration for performing composite operations resembles the following:</span></span>  

 <span data-ttu-id="0fcd5-250">![複合操作を実行するオーケストレーション](../../adapters-and-accelerators/adapter-oracle-database/media/4a1ecae7-8bf2-4c8a-a413-34d6a402cbfb.gif "4a1ecae7-8bf2-4c8a-a413-34d6a402cbfb")</span><span class="sxs-lookup"><span data-stu-id="0fcd5-250">![Orchestration to peform composite operations](../../adapters-and-accelerators/adapter-oracle-database/media/4a1ecae7-8bf2-4c8a-a413-34d6a402cbfb.gif "4a1ecae7-8bf2-4c8a-a413-34d6a402cbfb")</span></span>  

### <a name="adding-message-shapes"></a><span data-ttu-id="0fcd5-251">メッセージの構築図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-251">Adding Message Shapes</span></span>  
 <span data-ttu-id="0fcd5-252">メッセージの構築図形のごとに、次のプロパティを指定することを確認します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-252">Make sure you specify the following properties for each of the message shapes.</span></span> <span data-ttu-id="0fcd5-253">図形の列に示した名前は、単に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-253">The names listed in the Shape column are the names of the message shapes as displayed in the just-mentioned orchestration.</span></span>  

|<span data-ttu-id="0fcd5-254">図形</span><span class="sxs-lookup"><span data-stu-id="0fcd5-254">Shape</span></span>|<span data-ttu-id="0fcd5-255">図形の種類</span><span class="sxs-lookup"><span data-stu-id="0fcd5-255">Shape Type</span></span>|<span data-ttu-id="0fcd5-256">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="0fcd5-256">Properties</span></span>|  
|-----------|----------------|----------------|  
|<span data-ttu-id="0fcd5-257">ReceiveMessage</span><span class="sxs-lookup"><span data-stu-id="0fcd5-257">ReceiveMessage</span></span>|<span data-ttu-id="0fcd5-258">Receive</span><span class="sxs-lookup"><span data-stu-id="0fcd5-258">Receive</span></span>|<span data-ttu-id="0fcd5-259">-設定**名前**に*ReceiveMessage*</span><span class="sxs-lookup"><span data-stu-id="0fcd5-259">-   Set **Name** to *ReceiveMessage*</span></span><br /><span data-ttu-id="0fcd5-260">-設定**アクティブ**に*は True。*</span><span class="sxs-lookup"><span data-stu-id="0fcd5-260">-   Set **Activate** to *True*</span></span>|  
|<span data-ttu-id="0fcd5-261">SendMessage</span><span class="sxs-lookup"><span data-stu-id="0fcd5-261">SendMessage</span></span>|<span data-ttu-id="0fcd5-262">Send</span><span class="sxs-lookup"><span data-stu-id="0fcd5-262">Send</span></span>|<span data-ttu-id="0fcd5-263">-設定**名前**に*SendMessage*</span><span class="sxs-lookup"><span data-stu-id="0fcd5-263">-   Set **Name** to *SendMessage*</span></span>|  
|<span data-ttu-id="0fcd5-264">ReceiveResponse</span><span class="sxs-lookup"><span data-stu-id="0fcd5-264">ReceiveResponse</span></span>|<span data-ttu-id="0fcd5-265">Receive</span><span class="sxs-lookup"><span data-stu-id="0fcd5-265">Receive</span></span>|<span data-ttu-id="0fcd5-266">-設定**名前**に*ReceiveResponse*</span><span class="sxs-lookup"><span data-stu-id="0fcd5-266">-   Set **Name** to *ReceiveResponse*</span></span><br /><span data-ttu-id="0fcd5-267">-設定**アクティブ**に*False*</span><span class="sxs-lookup"><span data-stu-id="0fcd5-267">-   Set **Activate** to *False*</span></span>|  
|<span data-ttu-id="0fcd5-268">SendResponse</span><span class="sxs-lookup"><span data-stu-id="0fcd5-268">SendResponse</span></span>|<span data-ttu-id="0fcd5-269">Send</span><span class="sxs-lookup"><span data-stu-id="0fcd5-269">Send</span></span>|<span data-ttu-id="0fcd5-270">-設定**名前**に*SendResponse*</span><span class="sxs-lookup"><span data-stu-id="0fcd5-270">-   Set **Name** to *SendResponse*</span></span>|  

### <a name="adding-ports"></a><span data-ttu-id="0fcd5-271">ポートの追加</span><span class="sxs-lookup"><span data-stu-id="0fcd5-271">Adding Ports</span></span>  
 <span data-ttu-id="0fcd5-272">論理ポートごとに、次のプロパティを指定することを確認します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-272">Make sure you specify the following properties for each of the logical ports.</span></span> <span data-ttu-id="0fcd5-273">ポート列に示した名前は、オーケストレーションで表示されているポートの名前です。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-273">The names listed in the Port column are the names of the ports as displayed in the orchestration.</span></span>  

|<span data-ttu-id="0fcd5-274">Port</span><span class="sxs-lookup"><span data-stu-id="0fcd5-274">Port</span></span>|<span data-ttu-id="0fcd5-275">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="0fcd5-275">Properties</span></span>|  
|----------|----------------|  
|<span data-ttu-id="0fcd5-276">MessageIn</span><span class="sxs-lookup"><span data-stu-id="0fcd5-276">MessageIn</span></span>|<span data-ttu-id="0fcd5-277">-設定**識別子**に*MessageIn*</span><span class="sxs-lookup"><span data-stu-id="0fcd5-277">-   Set **Identifier** to *MessageIn*</span></span><br /><span data-ttu-id="0fcd5-278">-設定**型**に*MessageInType*</span><span class="sxs-lookup"><span data-stu-id="0fcd5-278">-   Set **Type** to *MessageInType*</span></span><br /><span data-ttu-id="0fcd5-279">-設定**通信パターン**に*一方向*</span><span class="sxs-lookup"><span data-stu-id="0fcd5-279">-   Set **Communication Pattern** to *One-Way*</span></span><br /><span data-ttu-id="0fcd5-280">-設定**通信方向**に*受信*</span><span class="sxs-lookup"><span data-stu-id="0fcd5-280">-   Set **Communication Direction** to *Receive*</span></span>|  
|<span data-ttu-id="0fcd5-281">LOBPort</span><span class="sxs-lookup"><span data-stu-id="0fcd5-281">LOBPort</span></span>|<span data-ttu-id="0fcd5-282">-設定**識別子**に*LOBPort*</span><span class="sxs-lookup"><span data-stu-id="0fcd5-282">-   Set **Identifier** to *LOBPort*</span></span><br /><span data-ttu-id="0fcd5-283">-設定**型**に*LOBPortType*</span><span class="sxs-lookup"><span data-stu-id="0fcd5-283">-   Set **Type** to *LOBPortType*</span></span><br /><span data-ttu-id="0fcd5-284">-設定**通信パターン**に*要求-応答*</span><span class="sxs-lookup"><span data-stu-id="0fcd5-284">-   Set **Communication Pattern** to *Request-Response*</span></span><br /><span data-ttu-id="0fcd5-285">-設定**通信方向**に*送受信*</span><span class="sxs-lookup"><span data-stu-id="0fcd5-285">-   Set **Communication Direction** to *Send-Receive*</span></span>|  
|<span data-ttu-id="0fcd5-286">ResponseOut</span><span class="sxs-lookup"><span data-stu-id="0fcd5-286">ResponseOut</span></span>|<span data-ttu-id="0fcd5-287">-設定**識別子**に*ResponseOut*</span><span class="sxs-lookup"><span data-stu-id="0fcd5-287">-   Set **Identifier** to *ResponseOut*</span></span><br /><span data-ttu-id="0fcd5-288">-設定**型**に*ResponseOutType*</span><span class="sxs-lookup"><span data-stu-id="0fcd5-288">-   Set **Type** to *ResponseOutType*</span></span><br /><span data-ttu-id="0fcd5-289">-設定**通信パターン**に*一方向*</span><span class="sxs-lookup"><span data-stu-id="0fcd5-289">-   Set **Communication Pattern** to *One-Way*</span></span><br /><span data-ttu-id="0fcd5-290">-設定**通信方向**に*送信*</span><span class="sxs-lookup"><span data-stu-id="0fcd5-290">-   Set **Communication Direction** to *Send*</span></span>|  

### <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a><span data-ttu-id="0fcd5-291">アクション図形は、メッセージを指定し、ポートに接続</span><span class="sxs-lookup"><span data-stu-id="0fcd5-291">Specify Messages for Action Shapes, and Connect Them to Ports</span></span>  
 <span data-ttu-id="0fcd5-292">次の表では、プロパティとアクション図形のメッセージを指定して、メッセージ ポートにリンクを設定する必要があります、値を指定します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-292">The following table specifies the properties and their values that you should set to specify messages for action shapes and to link the messages to the ports.</span></span> <span data-ttu-id="0fcd5-293">図形の列に示した名前は、前に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-293">The names listed in the Shape column are the names of the message shapes as displayed in the orchestration mentioned earlier.</span></span>  

|<span data-ttu-id="0fcd5-294">図形</span><span class="sxs-lookup"><span data-stu-id="0fcd5-294">Shape</span></span>|<span data-ttu-id="0fcd5-295">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="0fcd5-295">Properties</span></span>|  
|-----------|----------------|  
|<span data-ttu-id="0fcd5-296">ReceiveMessage</span><span class="sxs-lookup"><span data-stu-id="0fcd5-296">ReceiveMessage</span></span>|<span data-ttu-id="0fcd5-297">-設定**メッセージ**に*要求*</span><span class="sxs-lookup"><span data-stu-id="0fcd5-297">-   Set **Message** to *Request*</span></span><br /><span data-ttu-id="0fcd5-298">-設定**操作**に*MessageIn.CompositeOp.Request*</span><span class="sxs-lookup"><span data-stu-id="0fcd5-298">-   Set **Operation** to *MessageIn.CompositeOp.Request*</span></span>|  
|<span data-ttu-id="0fcd5-299">SendMessage</span><span class="sxs-lookup"><span data-stu-id="0fcd5-299">SendMessage</span></span>|<span data-ttu-id="0fcd5-300">-設定**メッセージ**に*要求*</span><span class="sxs-lookup"><span data-stu-id="0fcd5-300">-   Set **Message** to *Request*</span></span><br /><span data-ttu-id="0fcd5-301">-設定**操作**に*LOBPort.CompositeOp.Request*</span><span class="sxs-lookup"><span data-stu-id="0fcd5-301">-   Set **Operation** to *LOBPort.CompositeOp.Request*</span></span>|  
|<span data-ttu-id="0fcd5-302">ReceiveResponse</span><span class="sxs-lookup"><span data-stu-id="0fcd5-302">ReceiveResponse</span></span>|<span data-ttu-id="0fcd5-303">-設定**メッセージ**に*応答*</span><span class="sxs-lookup"><span data-stu-id="0fcd5-303">-   Set **Message** to *Response*</span></span><br /><span data-ttu-id="0fcd5-304">-設定**操作**に*LOBPort.CompositeOp.Response*</span><span class="sxs-lookup"><span data-stu-id="0fcd5-304">-   Set **Operation** to *LOBPort.CompositeOp.Response*</span></span>|  
|<span data-ttu-id="0fcd5-305">SendResponse</span><span class="sxs-lookup"><span data-stu-id="0fcd5-305">SendResponse</span></span>|<span data-ttu-id="0fcd5-306">-設定**メッセージ**に*応答*</span><span class="sxs-lookup"><span data-stu-id="0fcd5-306">-   Set **Message** to *Response*</span></span><br /><span data-ttu-id="0fcd5-307">-設定**操作**に*ResponseOut.CompositeOp.Request*</span><span class="sxs-lookup"><span data-stu-id="0fcd5-307">-   Set **Operation** to *ResponseOut.CompositeOp.Request*</span></span>|  

 <span data-ttu-id="0fcd5-308">これらのプロパティを指定したら、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-308">After you have specified these properties, the message shapes and ports are connected and your orchestration is complete.</span></span>  

 <span data-ttu-id="0fcd5-309">ここで、BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-309">You must now build the BizTalk solution and deploy it to a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="0fcd5-310">詳細については、次を参照してください。[を実行しているオーケストレーションのビルドと](../../core/building-and-running-orchestrations.md)します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-310">For more information, see [Building and Running Orchestrations](../../core/building-and-running-orchestrations.md).</span></span>  

## <a name="configuring-the-biztalk-application"></a><span data-ttu-id="0fcd5-311">BizTalk アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-311">Configuring the BizTalk Application</span></span>  
 <span data-ttu-id="0fcd5-312">[オーケストレーション] ペインで先ほど作成したオーケストレーションが表示されている BizTalk プロジェクトを配置した後、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-312">After you have deployed the BizTalk project, the orchestration you created earlier is listed under the Orchestrations pane in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="0fcd5-313">使用する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールにアプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-313">You must use the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to configure the application.</span></span> <span data-ttu-id="0fcd5-314">チュートリアルについては、次を参照してください。[チュートリアル。基本的な BizTalk アプリケーション展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-314">For a walkthrough, see [Walkthrough: Deploying a Basic BizTalk Application](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).</span></span>

 <span data-ttu-id="0fcd5-315">アプリケーションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-315">Configuring an application involves:</span></span>  

- <span data-ttu-id="0fcd5-316">アプリケーションのホストを選択します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-316">Selecting a host for the application.</span></span>  

- <span data-ttu-id="0fcd5-317">物理ポートにオーケストレーションで作成したポートのマッピング、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-317">Mapping the ports that you created in your orchestration to physical ports in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="0fcd5-318">このオーケストレーションの次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-318">For this orchestration you must:</span></span>  

  - <span data-ttu-id="0fcd5-319">ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポートでの場所を定義します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-319">Define a location on the hard disk and a corresponding file port where you will drop a request message.</span></span> <span data-ttu-id="0fcd5-320">BizTalk オーケストレーションは要求メッセージを使用し、Oracle データベースに送信します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-320">The BizTalk orchestration will consume the request message and send it to Oracle database.</span></span>  

  - <span data-ttu-id="0fcd5-321">ハード ディスクと、対応するファイル ポートを BizTalk オーケストレーションが Oracle データベースからの応答を含む応答メッセージをドロップする場所の場所を定義します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-321">Define a location on the hard disk and a corresponding file port where the BizTalk orchestration will drop the response message containing the response from Oracle database.</span></span>  

  - <span data-ttu-id="0fcd5-322">Oracle データベースにメッセージを送信する物理 Wcf-custom または Wcf-oracledb 送信ポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-322">Define a physical WCF-Custom or WCF-OracleDB send port to send messages to Oracle database.</span></span> <span data-ttu-id="0fcd5-323">複合操作の一部が単一のトランザクションで実行されるようが含まれている操作を確認するため、 **UseAmbientTransaction**に設定されているプロパティのバインド**True**します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-323">Because the operations that are being as part of the composite operation are executed in a single transaction, make sure the **UseAmbientTransaction** binding property is set to **True**.</span></span>  

     <span data-ttu-id="0fcd5-324">送信ポートでアクションを指定することも必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-324">You must also specify the action in the send port.</span></span> <span data-ttu-id="0fcd5-325">複合操作のアクションは、"<http://Microsoft.LobServices.OracleDB/2007/03/CompositeOperation”>します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-325">The action for a composite operation is “<http://Microsoft.LobServices.OracleDB/2007/03/CompositeOperation”>.</span></span> <span data-ttu-id="0fcd5-326">ポートを作成する方法については、次を参照してください。 [、Oracle データベース アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-326">For information about how to create ports, see [Manually configure a physical port binding to the Oracle Database Adapter](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md).</span></span> <span data-ttu-id="0fcd5-327">ポートのアクションを指定する方法の詳細については、次を参照してください。 [Oracle データベースの SOAP アクションを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-soap-action-for-oracle-database.md)します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-327">For more information about how to specify actions for ports, see [Configure the SOAP action for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-soap-action-for-oracle-database.md).</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="0fcd5-328">使用して、スキーマの生成、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-328">Generating the schema using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] also creates a binding file that contains information about the ports and the actions to be set for those ports.</span></span> <span data-ttu-id="0fcd5-329">このバインド ファイルをインポートすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール (発信) の送信ポートを作成したり (着信) 用のポートを受信します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-329">You can import this binding file from the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to create send ports (for outbound calls) or receive ports (for inbound calls).</span></span> <span data-ttu-id="0fcd5-330">詳細については、次を参照してください。 [Oracle データベースへのポート バインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-330">For more information, see [Configure a physical port binding using a port binding file to Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md).</span></span> <span data-ttu-id="0fcd5-331">選択したすべての操作に関連する動的アクションには、送信ポートでアクションが設定されているこのバインド ファイルをインポートする場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]スキーマの生成中にします。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-331">If you import this binding file, the action on the send port is set to a dynamic action involving all the operations you selected in the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] while generating the schema.</span></span> <span data-ttu-id="0fcd5-332">複合操作の場合は、動的操作を置き換える必要があります"<http://Microsoft.LobServices.OracleDB/2007/03/CompositeOperation”>します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-332">For a composite operation, you must replace the dynamic action with “<http://Microsoft.LobServices.OracleDB/2007/03/CompositeOperation”>.</span></span>  

## <a name="starting-the-application"></a><span data-ttu-id="0fcd5-333">アプリケーションの起動</span><span class="sxs-lookup"><span data-stu-id="0fcd5-333">Starting the Application</span></span>  
 <span data-ttu-id="0fcd5-334">Oracle データベースでの複合演算を実行する BizTalk アプリケーションを起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-334">You must start the BizTalk application for performing composite operations on Oracle database.</span></span> <span data-ttu-id="0fcd5-335">BizTalk アプリケーションを開始する手順については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-335">For instructions on starting a BizTalk application, see [How to Start an Orchestration](../../core/how-to-start-an-orchestration.md).</span></span>  

 <span data-ttu-id="0fcd5-336">この段階で、ことを確認します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-336">At this stage, make sure:</span></span>  

-   <span data-ttu-id="0fcd5-337">ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-337">The FILE receive port to receive request messages for the orchestration is running.</span></span>  

-   <span data-ttu-id="0fcd5-338">オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-338">The FILE send port to receive the response messages from the orchestration is running.</span></span>  

-   <span data-ttu-id="0fcd5-339">Oracle データベースにメッセージを送信する Wcf-custom または Wcf-oracledb 送信ポートが実行されています。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-339">The WCF-Custom or WCF-OracleDB send port to send messages to Oracle database is running.</span></span>  

-   <span data-ttu-id="0fcd5-340">操作の BizTalk オーケストレーションが実行されています。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-340">The BizTalk orchestration for the operation is running.</span></span>  

## <a name="executing-the-operation"></a><span data-ttu-id="0fcd5-341">操作の実行</span><span class="sxs-lookup"><span data-stu-id="0fcd5-341">Executing the Operation</span></span>  
 <span data-ttu-id="0fcd5-342">ファイルに要求メッセージを削除する必要があります、アプリケーションを実行した後の受信場所。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-342">After you run the application, you must drop a request message to the FILE receive location.</span></span> <span data-ttu-id="0fcd5-343">要求メッセージのスキーマは、先ほど作成した複合操作のスキーマに準拠する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-343">The schema for the request message must conform to the schema for the composite operations you created earlier.</span></span> <span data-ttu-id="0fcd5-344">たとえば、ACCOUNTACTIVITY テーブルにレコードを挿入、GET_ALL_ACTIVITY ストアド プロシージャを呼び出すし、ACCOUNTACTIVITY テーブルからレコードを削除する要求メッセージには。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-344">For example, a request message that inserts a record in the ACCOUNTACTIVITY table, invokes the GET_ALL_ACTIVITY stored procedure, and deletes a record from the ACCOUNTACTIVITY table is:</span></span>  

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

 <span data-ttu-id="0fcd5-345">前の要求メッセージでは、最初のレコードを挿入して、ACCOUNTACTIVITY テーブル内のすべてのレコードを取得する GET_ALL_ACTIVITY プロシージャを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-345">The preceding request message first inserts a record and then invokes the GET_ALL_ACTIVITY procedure to get all the records in the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="0fcd5-346">次に、フィルター句を指定することによって、挿入されたレコードが削除されます。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-346">Then, the inserted record is deleted by specifying a FILTER clause.</span></span> <span data-ttu-id="0fcd5-347">参照してください[複合操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-composite-operation2.md)Oracle に対する複合操作を実行するための要求メッセージ スキーマの詳細については、データベースを使用して、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-347">See [Message Schemas for the Composite Operation](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-composite-operation2.md) for more information about the request message schema for performing composite operations on Oracle database using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  

 <span data-ttu-id="0fcd5-348">オーケストレーションはメッセージを使用し、Oracle データベースに送信します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-348">The orchestration consumes the message and sends it to Oracle database.</span></span> <span data-ttu-id="0fcd5-349">Oracle データベースからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-349">The response from Oracle database is saved at the other FILE location defined as part of the orchestration.</span></span> <span data-ttu-id="0fcd5-350">たとえば、前の要求メッセージ用の Oracle データベースからの応答は、次するようになります。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-350">For example, the response from Oracle database for the preceding request message resembles the following:</span></span>  

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

 <span data-ttu-id="0fcd5-351">前の応答には、複合操作の一部として実行されるさまざまな操作を対応する複数の結果セットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-351">The preceding response contains multiple result sets corresponding the different operations performed as part of the composite operation.</span></span> <span data-ttu-id="0fcd5-352">たとえば、`InsertResult`要素に '1'、挿入操作によって挿入された行の数を示すが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-352">For example, the `InsertResult` element contains ‘1’, indicating the number of rows inserted by the Insert operation.</span></span> <span data-ttu-id="0fcd5-353">同様に、`DeleteResult`要素に '1'、削除操作によって削除された行の数を示すが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-353">Similarly, the `DeleteResult` element contains ‘1’, indicating the number of rows deleted by the Delete operation.</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="0fcd5-354">複合操作の実行中にタイムアウトの問題が発生した場合、可能性があります接続の数が、複合操作に関連する操作の数より少ない。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-354">If you experience time-out issues while executing a composite operation then it could be because the number of connections is less than the number of operations in a composite operation involving:</span></span>  
> 
> - <span data-ttu-id="0fcd5-355">OUT、BFILE、BLOB、CLOB、NCLOB、および REF CURSOR を含むストアド プロシージャまたは IN OUT パラメーター。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-355">Stored procedures containing BFILE, BLOB, CLOB, NCLOB, and REF CURSOR as OUT or IN OUT parameters.</span></span>  
>   -   <span data-ttu-id="0fcd5-356">操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-356">Select operation.</span></span>  
> 
>   <span data-ttu-id="0fcd5-357">この問題を解決するには、複合操作では、このような操作の数を"n"がある場合は、値が指定を確認する必要があります、 **MinPoolSize** "n+1"プロパティをバインドは以上です。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-357">To resolve this issue, you must ensure that if there are “n” number of such operations in a composite operation, the value specified for the **MinPoolSize** binding property is “n+1” or greater.</span></span> <span data-ttu-id="0fcd5-358">詳細については、 **MinPoolSize**プロパティ、バインドを参照してください[バインドのプロパティの操作](https://msdn.microsoft.com/library/dd788467.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-358">For more information about the **MinPoolSize** binding property, see [Working with binding properties](https://msdn.microsoft.com/library/dd788467.aspx).</span></span>  

## <a name="best-practices"></a><span data-ttu-id="0fcd5-359">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="0fcd5-359">Best Practices</span></span>  
 <span data-ttu-id="0fcd5-360">展開し、BizTalk プロジェクトの構成後は、バインド ファイルと呼ばれる XML ファイル構成設定をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-360">After you have deployed and configured the BizTalk project, you can export configuration settings to an XML file called the binding file.</span></span> <span data-ttu-id="0fcd5-361">バインド ファイルを生成した、送信ポートなどの項目を作成し、同じオーケストレーション用のポートを受信する必要はありませんように構成設定、ファイルからインポートできます。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-361">Once you generate a binding file, you can import the configuration settings from the file, so that you do not need to create items such as send ports and receive ports for the same orchestration.</span></span> <span data-ttu-id="0fcd5-362">バインド ファイルの詳細については、次を参照してください。[再利用の Oracle データベース アダプターのバインド](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)します。</span><span class="sxs-lookup"><span data-stu-id="0fcd5-362">For more information about binding files, see [Reuse Oracle Database adapter bindings](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="0fcd5-363">参照</span><span class="sxs-lookup"><span data-stu-id="0fcd5-363">See Also</span></span>  
[<span data-ttu-id="0fcd5-364">Oracle データベースと BizTalk アプリケーションを開発する構成要素</span><span class="sxs-lookup"><span data-stu-id="0fcd5-364">Building Blocks to Develop BizTalk Applications with Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)