---
title: "手順 2: 在庫要求スキーマの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0fa9ad9f-b815-4baf-8299-556869b8dde7
caps.latest.revision: "45"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5199b20a75b82e12ad76b96903538487a3128668
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-create-the-inventory-request-schema"></a><span data-ttu-id="f333c-102">ステップ 2: 在庫要求スキーマの作成</span><span class="sxs-lookup"><span data-stu-id="f333c-102">Step 2: Create the Inventory Request Schema</span></span>
<span data-ttu-id="f333c-103">![手順 5 の 2](../core/media/step-2of5.gif "Step_2of5")</span><span class="sxs-lookup"><span data-stu-id="f333c-103">![Step 2 of 5](../core/media/step-2of5.gif "Step_2of5")</span></span>  
  
 <span data-ttu-id="f333c-104">**所要時間:** 7 分</span><span class="sxs-lookup"><span data-stu-id="f333c-104">**Time to complete:** 7 minutes</span></span>  
  
 <span data-ttu-id="f333c-105">**目標:**このステップでは、在庫補充メッセージのスキーマを定義します。</span><span class="sxs-lookup"><span data-stu-id="f333c-105">**Objective:** In this step, you define the schema of the inventory replenishment message.</span></span>  <span data-ttu-id="f333c-106">倉庫システムでは在庫の補充を要求するためにこのメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="f333c-106">The warehouse system sends this message for requesting inventory replenishment.</span></span>  <span data-ttu-id="f333c-107">これはこのプロジェクトに対して作成する必要のある 2 つのスキーマのうちの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="f333c-107">This is one of the two schemas you must create for this project.</span></span>  
  
 <span data-ttu-id="f333c-108">**目的:** XML は、構造体だけでなくおよび標準化されたマークアップ コードを使用して情報を識別しますが、スキーマを使用する機能も備えています。</span><span class="sxs-lookup"><span data-stu-id="f333c-108">**Purpose:** XML not only structures and identifies information with standardized markup codes, but also has the ability to use schemas.</span></span> <span data-ttu-id="f333c-109">スキーマとは、辞書のように機能し、他の XML ドキュメントによって参照として使用される XML ドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="f333c-109">A schema is an XML document that works like a dictionary and is used as a reference by other XML documents.</span></span> <span data-ttu-id="f333c-110">スキーマ コードは、XML 要素のスペルおよびこれらの要素で囲まれるデータの種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="f333c-110">The schema code defines the spelling of XML elements and the type of data enclosed by those elements.</span></span> <span data-ttu-id="f333c-111">スキーマを使用することにより、プログラムでは XML ドキュメントを簡単に処理することができ、情報の構造と種類が正しいことを保証できます。</span><span class="sxs-lookup"><span data-stu-id="f333c-111">Using schemas provides an easy way for a program to process XML documents and ensures that the structure and type of information is correct.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f333c-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="f333c-112">Prerequisites</span></span>  
 <span data-ttu-id="f333c-113">このステップを開始する前に、以下の要件を確認してください。</span><span class="sxs-lookup"><span data-stu-id="f333c-113">Note the following requirements before you begin this step:</span></span>  
  
-   <span data-ttu-id="f333c-114">この手順を開始する前に行う必要があります[手順 1: EAISchemas プロジェクトの作成](../core/step-1-create-eaischemas-project.md)です。</span><span class="sxs-lookup"><span data-stu-id="f333c-114">Before you begin this step you must complete [Step 1: Create EAISchemas Project](../core/step-1-create-eaischemas-project.md).</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="f333c-115">手順</span><span class="sxs-lookup"><span data-stu-id="f333c-115">Procedures</span></span>  
 <span data-ttu-id="f333c-116">[手順 1: EAISchemas プロジェクトの作成](../core/step-1-create-eaischemas-project.md)、新しく作成した[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="f333c-116">In [Step 1: Create EAISchemas Project](../core/step-1-create-eaischemas-project.md), you created a new [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project.</span></span>  <span data-ttu-id="f333c-117">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ウィンドウを閉じた場合は、次の手順を使用してプロジェクトを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="f333c-117">If you close the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] window, you can use the following procedure to open the project.</span></span>  <span data-ttu-id="f333c-118">閉じていない場合は、「Visual Studio プロジェクトを開くには」の手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="f333c-118">Otherwise, you can skip this procedure, “To open the Visual Studio project”.</span></span>  
  
#### <a name="to-open-the-visual-studio-project"></a><span data-ttu-id="f333c-119">Visual Studio プロジェクトを開くには</span><span class="sxs-lookup"><span data-stu-id="f333c-119">To open the Visual Studio project</span></span>  
  
1.  <span data-ttu-id="f333c-120">開始**Microsoft Visual Studio**です。</span><span class="sxs-lookup"><span data-stu-id="f333c-120">Start **Microsoft Visual Studio**.</span></span>  
  
2.  <span data-ttu-id="f333c-121">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]の**ファイル**メニューのをポイント**開く**、クリックして**プロジェクト/ソリューション**です。</span><span class="sxs-lookup"><span data-stu-id="f333c-121">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="f333c-122">**プロジェクトを開く** ダイアログ ボックスを参照、 **C:\BTSTutorials\EAISolution\EAISolution.sln**ソリューション ファイル、およびクリック**開く**です。</span><span class="sxs-lookup"><span data-stu-id="f333c-122">In the **Open Project** dialog box, browse to the **C:\BTSTutorials\EAISolution\EAISolution.sln** solution file, and then click **Open**.</span></span>  
  
 <span data-ttu-id="f333c-123">次の手順では、在庫補充メッセージ用の新しいスキーマ ファイルをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="f333c-123">In the following procedure, you add a new schema file to the project for the inventory replenishment message.</span></span>  
  
#### <a name="to-add-a-new-schema-to-the-project"></a><span data-ttu-id="f333c-124">新しいスキーマをプロジェクトに追加するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f333c-124">To add a new schema to the project</span></span>  
  
1.  <span data-ttu-id="f333c-125">ソリューション エクスプ ローラーで右クリックし、 **EAISchemas**プロジェクトをポイントし、**追加**、順にクリック**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="f333c-125">In Solution Explorer, right-click the **EAISchemas** project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="f333c-126">**新しい項目の追加 - EAISchemas**  ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="f333c-126">In the **Add New Item - EAISchemas** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="f333c-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f333c-127">Use this</span></span>|<span data-ttu-id="f333c-128">目的</span><span class="sxs-lookup"><span data-stu-id="f333c-128">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="f333c-129">**インストールされたテンプレート**</span><span class="sxs-lookup"><span data-stu-id="f333c-129">**Installed Templates**</span></span>|<span data-ttu-id="f333c-130">をクリックして**スキーマ ファイル**をクリックし、**スキーマ**です。</span><span class="sxs-lookup"><span data-stu-id="f333c-130">Click **Schema Files**, then click **Schema**.</span></span>|  
    |<span data-ttu-id="f333c-131">**名前**</span><span class="sxs-lookup"><span data-stu-id="f333c-131">**Name**</span></span>|<span data-ttu-id="f333c-132">型**Request.xsd**です。</span><span class="sxs-lookup"><span data-stu-id="f333c-132">Type **Request.xsd**.</span></span>|  
  
3.  <span data-ttu-id="f333c-133">**[追加]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f333c-133">Click **Add**.</span></span> <span data-ttu-id="f333c-134">スキーマ ツリーと XSD ペインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f333c-134">The schema tree and XSD pane appear.</span></span> <span data-ttu-id="f333c-135">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のこの領域を、BizTalk エディターといいます。</span><span class="sxs-lookup"><span data-stu-id="f333c-135">This area of [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] is referred to as BizTalk Editor.</span></span> <span data-ttu-id="f333c-136">また、ソリューション エクスプローラーでは、EAISchemas プロジェクトの下に新しいスキーマが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f333c-136">In addition, your new schema appears in Solution Explorer below the EAISchemas project.</span></span>  
  
     <span data-ttu-id="f333c-137">![BizTalk プロジェクトのさまざまな部分](../core/media/differentpartsofbiztalkserver.gif "DifferentpartsofBizTalkServer")</span><span class="sxs-lookup"><span data-stu-id="f333c-137">![Different Parts of BizTalk Project](../core/media/differentpartsofbiztalkserver.gif "DifferentpartsofBizTalkServer")</span></span>  
  
#### <a name="to-add-elements-to-the-schema"></a><span data-ttu-id="f333c-138">要素をスキーマに追加するには</span><span class="sxs-lookup"><span data-stu-id="f333c-138">To add elements to the schema</span></span>  
  
1.  <span data-ttu-id="f333c-139">スキーマ ツリーで、クリックして、**ルート**ノード。</span><span class="sxs-lookup"><span data-stu-id="f333c-139">In schema tree, click the **Root** node.</span></span>  
  
2.  <span data-ttu-id="f333c-140">値を変更、プロパティ ペインで、**ノード名**プロパティを`Request`、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="f333c-140">In the Properties pane, change the value of the **Node Name** property to `Request`, and then press ENTER.</span></span>  
  
3.  <span data-ttu-id="f333c-141">スキーマ ツリー内を右クリックし、**要求**に**スキーマ ノードの挿入**、順にクリック**子レコード**です。</span><span class="sxs-lookup"><span data-stu-id="f333c-141">In schema tree, right-click the **Request** node, point to **Insert Schema Node**, and then click **Child Record**.</span></span>  
  
4.  <span data-ttu-id="f333c-142">型`Header`子レコードとし、ENTER キーを押して新しい名前として。</span><span class="sxs-lookup"><span data-stu-id="f333c-142">Type `Header` as the new name for the child record, and then press ENTER.</span></span>  
  
5.  <span data-ttu-id="f333c-143">に対して手順 3. および 4. を 2 番目の子を作成するレコードを繰り返して、**要求**ノード、名前を付けます`Items`です。</span><span class="sxs-lookup"><span data-stu-id="f333c-143">Repeat step 3 and 4 to create a second child record for the **Request** node, and name it `Items`.</span></span>  
  
6.  <span data-ttu-id="f333c-144">スキーマ ツリー内を右クリックし、**ヘッダー**に**スキーマ ノードの挿入**、順にクリック**子フィールド要素**です。</span><span class="sxs-lookup"><span data-stu-id="f333c-144">In schema tree, right-click the **Header** node, point to **Insert Schema Node**, and then click **Child Field Element**.</span></span>  
  
7.  <span data-ttu-id="f333c-145">型`ReqID`要素、およびし、ENTER キーを押して新しい名前として。</span><span class="sxs-lookup"><span data-stu-id="f333c-145">Type `ReqID` as the new name for the element, and then press ENTER.</span></span>  
  
8.  <span data-ttu-id="f333c-146">手順 6 および 7 を 2 番目の子を作成するフィールドの要素を**ヘッダー**ノード、名前を付けます`OrderDate`です。</span><span class="sxs-lookup"><span data-stu-id="f333c-146">Repeat step 6 and 7 to create a second child field element for the **Header** node, and name it `OrderDate`.</span></span>  
  
9. <span data-ttu-id="f333c-147">スキーマ ツリー内を右クリックし、**項目**に**スキーマ ノードの挿入**、順にクリック**子レコード**です。</span><span class="sxs-lookup"><span data-stu-id="f333c-147">In schema tree, right-click the **Items** node, point to **Insert Schemas Node**, and then click **Child Record**.</span></span>  
  
10. <span data-ttu-id="f333c-148">型`Item`子レコードとし、ENTER キーを押して新しい名前として。</span><span class="sxs-lookup"><span data-stu-id="f333c-148">Type `Item` as the new name for the child record, and then press ENTER.</span></span>  
  
11. <span data-ttu-id="f333c-149">スキーマ ツリー内を右クリックし、**項目**ノード、し、次の子フィールド要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="f333c-149">In schema tree, right-click the **Item** node, and add the following child field elements:</span></span>  
  
    -   `Description`  
  
    -   `Quantity`  
  
    -   `UnitPrice`  
  
     <span data-ttu-id="f333c-150">完成した Request.xsd は、次の図のようになります。</span><span class="sxs-lookup"><span data-stu-id="f333c-150">The completed Request.xsd should look similar to the following figure.</span></span>  
  
     <span data-ttu-id="f333c-151">![ソリューション エクスプ ローラー、要求スキーマを持つ](../core/media/solutionexplorerwiththerequestschema.gif "SolutionExplorerwiththeRequestSchema")</span><span class="sxs-lookup"><span data-stu-id="f333c-151">![Solution Explorer with the Request Schema](../core/media/solutionexplorerwiththerequestschema.gif "SolutionExplorerwiththeRequestSchema")</span></span>  
  
 <span data-ttu-id="f333c-152">ノードをスキーマに追加するときは、そのプロパティの一連の既定値が提供されます。</span><span class="sxs-lookup"><span data-stu-id="f333c-152">When you add nodes to a schema, BizTalk Editor gives a set of default values for their properties.</span></span>  <span data-ttu-id="f333c-153">これらは要件に基づいて構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f333c-153">You must configure them based on the requirements.</span></span>  
  
#### <a name="to-configure-the-elements"></a><span data-ttu-id="f333c-154">要素を構成するには</span><span class="sxs-lookup"><span data-stu-id="f333c-154">To configure the elements</span></span>  
  
1.  <span data-ttu-id="f333c-155">スキーマ ツリーで、クリックして**OrderDate**をオンにします。</span><span class="sxs-lookup"><span data-stu-id="f333c-155">In schema tree, click **OrderDate** to select it.</span></span>  
  
2.  <span data-ttu-id="f333c-156">プロパティ ウィンドウで、次のように変更します。**データ型**に**xs:dateTime**です。</span><span class="sxs-lookup"><span data-stu-id="f333c-156">In the Properties pane, change **Data Type** to **xs:dateTime**.</span></span>  
  
3.  <span data-ttu-id="f333c-157">手順 1. および 2. を繰り返して次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="f333c-157">Repeat step 1 and 2 to configure the following properties:</span></span>  
  
    |<span data-ttu-id="f333c-158">要素</span><span class="sxs-lookup"><span data-stu-id="f333c-158">Element</span></span>|<span data-ttu-id="f333c-159">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f333c-159">Property</span></span>|<span data-ttu-id="f333c-160">値</span><span class="sxs-lookup"><span data-stu-id="f333c-160">Value</span></span>|  
    |-------------|--------------|-----------|  
    |<span data-ttu-id="f333c-161">**[総計]**</span><span class="sxs-lookup"><span data-stu-id="f333c-161">**GrandTotal**</span></span>|<span data-ttu-id="f333c-162">**データ型**</span><span class="sxs-lookup"><span data-stu-id="f333c-162">**Data Type**</span></span>|<span data-ttu-id="f333c-163">**Xs:decimal**</span><span class="sxs-lookup"><span data-stu-id="f333c-163">**Xs:decimal**</span></span>|  
    |<span data-ttu-id="f333c-164">**アイテム**</span><span class="sxs-lookup"><span data-stu-id="f333c-164">**Item**</span></span>|<span data-ttu-id="f333c-165">**Max Occurs します。**</span><span class="sxs-lookup"><span data-stu-id="f333c-165">**Max Occurs**</span></span>|<span data-ttu-id="f333c-166">**Unbounded**</span><span class="sxs-lookup"><span data-stu-id="f333c-166">**Unbounded**</span></span>|  
    |<span data-ttu-id="f333c-167">**アイテム**</span><span class="sxs-lookup"><span data-stu-id="f333c-167">**Item**</span></span>|<span data-ttu-id="f333c-168">**Min Occurs します。**</span><span class="sxs-lookup"><span data-stu-id="f333c-168">**Min Occurs**</span></span>|<span data-ttu-id="f333c-169">**1**</span><span class="sxs-lookup"><span data-stu-id="f333c-169">**1**</span></span>|  
    |<span data-ttu-id="f333c-170">**数量**</span><span class="sxs-lookup"><span data-stu-id="f333c-170">**Quantity**</span></span>|<span data-ttu-id="f333c-171">**データ型**</span><span class="sxs-lookup"><span data-stu-id="f333c-171">**Data Type**</span></span>|<span data-ttu-id="f333c-172">**xs:unsignedInt**</span><span class="sxs-lookup"><span data-stu-id="f333c-172">**xs:unsignedInt**</span></span>|  
  
 <span data-ttu-id="f333c-173">スキーマは数多くの要素を持つことができますが、アプリケーションではデータ処理にその一部のみしか求められない場合があります。</span><span class="sxs-lookup"><span data-stu-id="f333c-173">A schema can have many elements, but your application may only require that you use a few of them for your data processing.</span></span> <span data-ttu-id="f333c-174">コンピューターのリソースを節約するために、BizTalk サーバーでは各スキーマ要素を自動的に読み取りません。</span><span class="sxs-lookup"><span data-stu-id="f333c-174">To save computer resources, BizTalk Server doesn't automatically read each schema element.</span></span> <span data-ttu-id="f333c-175">BizTalk サーバーが特定の要素からデータを読み取るようにするには、BizTalk エディターを使用してその要素のプロパティを昇格することで、要素を識別する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f333c-175">If you want BizTalk Server to read data from a specific element, you must identify that element by using BizTalk Editor to promote its properties.</span></span>  
  
 <span data-ttu-id="f333c-176">作成するオーケストレーション[レッスン 2: ビジネス プロセスの定義](../core/lesson-2-define-the-business-process.md)は基にメッセージをルーティングするための GrandTotal フィールドです。</span><span class="sxs-lookup"><span data-stu-id="f333c-176">The orchestration that we will create in [Lesson 2: Define the Business Process](../core/lesson-2-define-the-business-process.md) will base on the GrandTotal field to route messages.</span></span>  <span data-ttu-id="f333c-177">このため、GrandTotal フィールドを昇格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f333c-177">So we must promote the GrandTotal field.</span></span>  
  
#### <a name="to-promote-an-element"></a><span data-ttu-id="f333c-178">要素を昇格するには</span><span class="sxs-lookup"><span data-stu-id="f333c-178">To promote an element</span></span>  
  
1.  <span data-ttu-id="f333c-179">スキーマ ツリー内を右クリックして**GrandTotal**、をポイント**昇格**、クリックして**クイック昇格**です。</span><span class="sxs-lookup"><span data-stu-id="f333c-179">In Schema tree, right-click **GrandTotal**, point to **Promote**, and then click **Quick Promotions**.</span></span>  
  
2.  <span data-ttu-id="f333c-180">をクリックして**OK**プロパティ スキーマを追加することを確認します。</span><span class="sxs-lookup"><span data-stu-id="f333c-180">Click **OK** to acknowledge adding a property schema.</span></span>  
  
3.  <span data-ttu-id="f333c-181">**[ファイル]** メニューの **[すべてを保存]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f333c-181">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="f333c-182">でしただけは何ですか。</span><span class="sxs-lookup"><span data-stu-id="f333c-182">What did I just do?</span></span>  
 <span data-ttu-id="f333c-183">このステップでは、倉庫の在庫補充メッセージのスキーマを定義しました。</span><span class="sxs-lookup"><span data-stu-id="f333c-183">In this step, you defined the warehouse inventory replenishment message schema.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f333c-184">次の手順</span><span class="sxs-lookup"><span data-stu-id="f333c-184">Next Steps</span></span>  
 <span data-ttu-id="f333c-185">要求拒否メッセージのスキーマを定義します。</span><span class="sxs-lookup"><span data-stu-id="f333c-185">You define the request decline message schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f333c-186">参照</span><span class="sxs-lookup"><span data-stu-id="f333c-186">See Also</span></span>  
 <span data-ttu-id="f333c-187">[手順 1: EAISchemas プロジェクトを作成します。](../core/step-1-create-eaischemas-project.md) </span><span class="sxs-lookup"><span data-stu-id="f333c-187">[Step 1: Create EAISchemas Project](../core/step-1-create-eaischemas-project.md) </span></span>  
 <span data-ttu-id="f333c-188">[手順 3: 要求拒否スキーマを作成します。](../core/step-3-create-the-request-decline-schema.md) </span><span class="sxs-lookup"><span data-stu-id="f333c-188">[Step 3: Create the Request Decline Schema](../core/step-3-create-the-request-decline-schema.md) </span></span>  
 <span data-ttu-id="f333c-189">[手順 4: マップを作成します。](../core/step-4-create-the-map.md) </span><span class="sxs-lookup"><span data-stu-id="f333c-189">[Step 4: Create the Map](../core/step-4-create-the-map.md) </span></span>  
 <span data-ttu-id="f333c-190">[手順 5: EAISchemas プロジェクトをビルドします。](../core/step-5-build-the-eaischemas-project.md) </span><span class="sxs-lookup"><span data-stu-id="f333c-190">[Step 5: Build the EAISchemas Project](../core/step-5-build-the-eaischemas-project.md) </span></span>  
 <span data-ttu-id="f333c-191">[BizTalk エディターを使用してスキーマを作成します。](../core/creating-schemas-using-biztalk-editor.md) </span><span class="sxs-lookup"><span data-stu-id="f333c-191">[Creating Schemas Using BizTalk Editor](../core/creating-schemas-using-biztalk-editor.md) </span></span>  
 [<span data-ttu-id="f333c-192">BizTalk メッセージ コンテキストのプロパティについて</span><span class="sxs-lookup"><span data-stu-id="f333c-192">About BizTalk Message Context Properties</span></span>](../core/about-biztalk-message-context-properties.md)