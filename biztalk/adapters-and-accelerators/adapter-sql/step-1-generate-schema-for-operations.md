---
title: "手順 1: 操作のスキーマを生成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 63218a5e-9af2-40af-9992-ac5e204d2832
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16372bd950088b89f8e7808cda751f5fc3833944
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-generate-schema-for-operations"></a><span data-ttu-id="b2002-102">手順 1: 操作のスキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="b2002-102">Step 1: Generate Schema for Operations</span></span>
<span data-ttu-id="b2002-103">![2 の手順 1.](../../adapters-and-accelerators/adapter-sql/media/step-1of2.gif "Step_1of2")</span><span class="sxs-lookup"><span data-stu-id="b2002-103">![Step 1 of 2](../../adapters-and-accelerators/adapter-sql/media/step-1of2.gif "Step_1of2")</span></span>  
  
 <span data-ttu-id="b2002-104">**所要時間:** 5 分</span><span class="sxs-lookup"><span data-stu-id="b2002-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="b2002-105">**目標:**で SQL Server データベースを使用して、実行する操作のスキーマを生成するこの手順で、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="b2002-105">**Objective:** In this step, you generate schemas for the operations that you perform on the SQL Server database using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="b2002-106">このチュートリアルでは、次のスキーマを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2002-106">For this tutorial, you must generate schema for the following:</span></span>  
  
-   <span data-ttu-id="b2002-107">**通知**(受信操作)。</span><span class="sxs-lookup"><span data-stu-id="b2002-107">**Notification** (inbound operation).</span></span>  
  
-   <span data-ttu-id="b2002-108">**UPDATE_EMPLOYEE**ストアド プロシージャ (送信操作)。</span><span class="sxs-lookup"><span data-stu-id="b2002-108">**UPDATE_EMPLOYEE** stored procedure (outbound operation).</span></span>  
  
-   <span data-ttu-id="b2002-109">**挿入**での操作、 **Purchase_Order**テーブル (送信操作)。</span><span class="sxs-lookup"><span data-stu-id="b2002-109">**Insert** operation on the **Purchase_Order** table (outbound operation).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b2002-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="b2002-110">Prerequisites</span></span>  
 <span data-ttu-id="b2002-111">このチュートリアルを続行する前に確認します。</span><span class="sxs-lookup"><span data-stu-id="b2002-111">Before you proceed with the tutorial, make sure:</span></span>  
  
-   <span data-ttu-id="b2002-112">内の手順を完了する必要があります[Before You 開発 BizTalk Applications](http://msdn.microsoft.com/library/3539741d-5266-43d4-9b7b-73e82f0ed4f6)です。</span><span class="sxs-lookup"><span data-stu-id="b2002-112">You must have completed the steps in [Before You Develop BizTalk Applications](http://msdn.microsoft.com/library/3539741d-5266-43d4-9b7b-73e82f0ed4f6).</span></span>  
  
-   <span data-ttu-id="b2002-113">BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2002-113">You must log on as a member of the BizTalk Server Administrators group.</span></span>  
  
### <a name="to-generate-schema-for-operations"></a><span data-ttu-id="b2002-114">操作のスキーマを生成するには</span><span class="sxs-lookup"><span data-stu-id="b2002-114">To generate schema for operations</span></span>  
  
1.  <span data-ttu-id="b2002-115">新しい BizTalk プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="b2002-115">Create a new BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="b2002-116">このチュートリアルでは、名前とプロジェクト`Employee_PurchaseOrder`です。</span><span class="sxs-lookup"><span data-stu-id="b2002-116">For this tutorial, name the project as `Employee_PurchaseOrder`.</span></span>  
  
2.  <span data-ttu-id="b2002-117">ADAPTER_SAMPLES SQL Server データベースへの接続、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="b2002-117">Connect to the ADAPTER_SAMPLES SQL Server database using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span> <span data-ttu-id="b2002-118">使用して接続する方法についての[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を参照してください[Visual Studio を使用してアダプター サービスの使用とアドインでの SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)です。</span><span class="sxs-lookup"><span data-stu-id="b2002-118">For instructions on how to connect using [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], see [Connect to SQL Server in Visual Studio Using Consume Adapter Service Add-in](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b2002-119">SQL Server を使用してに接続することも、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="b2002-119">You can also connect to SQL Server using the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="b2002-120">ただし、このチュートリアルでは使用する、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="b2002-120">However, for this tutorial you will use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span>  
  
3.  <span data-ttu-id="b2002-121">スキーマを生成、**通知**操作を受信します。</span><span class="sxs-lookup"><span data-stu-id="b2002-121">Generate schema for the **Notification** inbound operation.</span></span>  
  
    1.  <span data-ttu-id="b2002-122">ADAPTER_SAMPLES データベースに接続した後、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]から、**選択コントラクト型**一覧で、選択**サービス (入力方向の操作)**です。</span><span class="sxs-lookup"><span data-stu-id="b2002-122">After connecting to the ADAPTER_SAMPLES database, in the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], from the **Select contract type** list, select **Service (Inbound operations)**.</span></span>  
  
    2.  <span data-ttu-id="b2002-123">**カテゴリを選択**ボックスで、ルート ノードをクリックして (**/**)。</span><span class="sxs-lookup"><span data-stu-id="b2002-123">From the **Select a category** box, click the root node (**/**).</span></span>  
  
    3.  <span data-ttu-id="b2002-124">**利用可能なカテゴリと操作**ボックスで、**通知** をクリック**追加**です。</span><span class="sxs-lookup"><span data-stu-id="b2002-124">From the **Available categories and operations** box, select **Notification** and click **Add**.</span></span> <span data-ttu-id="b2002-125">**通知**操作が表示されます、**カテゴリと操作を追加**ボックス。</span><span class="sxs-lookup"><span data-stu-id="b2002-125">The **Notification** operation is now displayed in the **Added categories and operations** box.</span></span> <span data-ttu-id="b2002-126">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b2002-126">Click **OK**.</span></span>  
  
4.  <span data-ttu-id="b2002-127">スキーマを生成、 **UPDATE_EMPLOYEE**でストアド プロシージャと挿入操作**Purchase_Order**テーブル。</span><span class="sxs-lookup"><span data-stu-id="b2002-127">Generate schema for the **UPDATE_EMPLOYEE** stored procedure and the Insert operation on **Purchase_Order** table.</span></span>  
  
    1.  <span data-ttu-id="b2002-128">手順 2 を使用して SQL サーバーで ADAPTER_SAMPLES データベースへの接続を繰り返し、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="b2002-128">Repeat step 2 to connect to ADAPTER_SAMPLES database in SQL Server using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="b2002-129">同時に受信および送信操作のスキーマを生成することはできません。</span><span class="sxs-lookup"><span data-stu-id="b2002-129">You cannot generate schema for inbound and outbound operations at the same time.</span></span> <span data-ttu-id="b2002-130">そのため、手順 3. をクリックした後**OK**のスキーマを生成する**通知**操作、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を閉じます。</span><span class="sxs-lookup"><span data-stu-id="b2002-130">Hence, in step 3, after you click **OK** to generate the schema for **Notification** operation, the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] closes.</span></span> <span data-ttu-id="b2002-131">送信操作のスキーマを生成する SQL Server データベースに再接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2002-131">You must reconnect to the SQL Server database to generate schema for outbound operations.</span></span>  
  
    2.  <span data-ttu-id="b2002-132">**選択コントラクト型**一覧で、選択**クライアント (送信操作)**です。</span><span class="sxs-lookup"><span data-stu-id="b2002-132">From the **Select contract type** list, select **Client (Outbound operations)**.</span></span>  
  
    3.  <span data-ttu-id="b2002-133">**カテゴリを選択**ボックスで、クリックして、 **Strongly-Typed プロシージャ**ノード。</span><span class="sxs-lookup"><span data-stu-id="b2002-133">From the **Select a category** box, click the **Strongly-Typed Procedures** node.</span></span> <span data-ttu-id="b2002-134">**利用可能なカテゴリと操作**s ボックスで、 **UPDATE_EMPLOYEE**、クリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="b2002-134">From the **Available categories and operation**s box, select **UPDATE_EMPLOYEE**, and then click **Add**.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="b2002-135">**UPDATE_EMPLOYEE**で使用可能なストアド プロシージャも、**プロシージャ**ノード。</span><span class="sxs-lookup"><span data-stu-id="b2002-135">The **UPDATE_EMPLOYEE** stored procedure is also available under the **Procedures** node.</span></span> <span data-ttu-id="b2002-136">ただしから対象のストアド プロシージャのスキーマを生成するかどうか、**プロシージャ**ノード、応答メッセージのスキーマは使用できないデザイン時に、ストアド プロシージャを実行した後、応答メッセージを受け取りました。</span><span class="sxs-lookup"><span data-stu-id="b2002-136">However, if you generate schema for the stored procedure from under the **Procedures** node, the response message schema is not available at design-time but is received with the response message after you execute the stored procedure.</span></span>  
        >   
        >  <span data-ttu-id="b2002-137">このチュートリアルでは、ストアド プロシージャは、挿入操作の入力スキーマの応答スキーマをマップは、 **Purchase_Order**テーブル。</span><span class="sxs-lookup"><span data-stu-id="b2002-137">In this tutorial, you will map the response schema of the stored procedure to the input schema of the Insert operation on the **Purchase_Order** table.</span></span> <span data-ttu-id="b2002-138">そのため、必要がありますのスキーマ、 **UPDATE_EMPLOYEE**デザイン時とするストアド プロシージャから対象のストアド プロシージャを選択する必要があります、 **Strongly-Typed プロシージャ**です。</span><span class="sxs-lookup"><span data-stu-id="b2002-138">Therefore, you will need the schema for the **UPDATE_EMPLOYEE** stored procedure at design-time and you must select the stored procedure from under the **Strongly-Typed Procedures**.</span></span> <span data-ttu-id="b2002-139">これにより、デザイン時に、ストアド プロシージャのスキーマが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2002-139">By doing so, you will get the schema of the stored procedure at design-time.</span></span>  
  
    4.  <span data-ttu-id="b2002-140">**カテゴリを選択**ボックスで、展開、**テーブル** ノードのノードをクリックして**Purchase_Order**テーブル。</span><span class="sxs-lookup"><span data-stu-id="b2002-140">From the **Select a category** box, expand the **Tables** node, and click the node for **Purchase_Order** table.</span></span> <span data-ttu-id="b2002-141">**利用可能なカテゴリと操作**s ボックスで、**挿入**、 をクリックして**追加**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="b2002-141">From the **Available categories and operation**s box, select **Insert**, click **Add**, and then click **OK**.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="b2002-142">でしただけは何ですか。</span><span class="sxs-lookup"><span data-stu-id="b2002-142">What did I just do?</span></span>  
 <span data-ttu-id="b2002-143">このステップでのスキーマを生成した**通知**(受信操作)、 **UPDATE_EMPLOYEE**ストアド プロシージャ、および**挿入**での操作、 **Purchase_Order**テーブル。</span><span class="sxs-lookup"><span data-stu-id="b2002-143">In this step, you generated schemas for **Notification** (inbound operation), **UPDATE_EMPLOYEE** stored procedure, and **Insert** operation on the **Purchase_Order** table.</span></span> <span data-ttu-id="b2002-144">スキーマを生成した後、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]次のファイルを BizTalk プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="b2002-144">After you generate the schema, the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] adds the following files to your BizTalk project:</span></span>  
  
-   <span data-ttu-id="b2002-145">SQL Server 上の操作の呼び出しに要求メッセージのスキーマが含まれる XSD ファイル。</span><span class="sxs-lookup"><span data-stu-id="b2002-145">XSD files that contain schema for the request message to invoke operations on SQL Server.</span></span>  
  
-   <span data-ttu-id="b2002-146">XML バインド ファイルを作成 Wcf-custom 送信ポートと受信ポートで使用できる[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="b2002-146">XML binding files that you can use to create WCF-Custom send and receive ports in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="b2002-147">スキーマの生成の詳細については、次を参照してください。[参照、検索、および SQL アダプターを使用して SQL 操作のメタデータを取得](../../adapters-and-accelerators/adapter-sql/browse-search-and-get-metadata-for-sql-operations-using-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="b2002-147">For more information about generating schemas, see [Browse, search, and get metadata for SQL operations using the SQL adapter](../../adapters-and-accelerators/adapter-sql/browse-search-and-get-metadata-for-sql-operations-using-the-sql-adapter.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="b2002-148">次の手順</span><span class="sxs-lookup"><span data-stu-id="b2002-148">Next Steps</span></span>  
 <span data-ttu-id="b2002-149">内のスキーマの BizTalk プロジェクトでメッセージを作成する[手順 2: BizTalk オーケストレーションのメッセージの作成](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md)です。</span><span class="sxs-lookup"><span data-stu-id="b2002-149">You create messages in the BizTalk project for the schemas in [Step 2: Create Messages for BizTalk Orchestrations](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2002-150">参照</span><span class="sxs-lookup"><span data-stu-id="b2002-150">See Also</span></span>  
 [<span data-ttu-id="b2002-151">レッスン 1: スキーマを生成し、メッセージ作成</span><span class="sxs-lookup"><span data-stu-id="b2002-151">Lesson 1: Generate Schemas and Create Messages</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md)