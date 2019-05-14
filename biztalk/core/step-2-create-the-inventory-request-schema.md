---
title: 手順 2:在庫要求スキーマの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0fa9ad9f-b815-4baf-8299-556869b8dde7
caps.latest.revision: 45
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0729083983aad67ad751aa3dd25d63c6a4c031f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392747"
---
# <a name="step-2-create-the-inventory-request-schema"></a><span data-ttu-id="edbb1-102">手順 2:在庫要求スキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="edbb1-102">Step 2: Create the Inventory Request Schema</span></span>
<span data-ttu-id="edbb1-103">![手順 5 の 2](../core/media/step-2of5.gif "Step_2of5")</span><span class="sxs-lookup"><span data-stu-id="edbb1-103">![Step 2 of 5](../core/media/step-2of5.gif "Step_2of5")</span></span>  

 <span data-ttu-id="edbb1-104">**所要時間:** 7 分</span><span class="sxs-lookup"><span data-stu-id="edbb1-104">**Time to complete:** 7 minutes</span></span>  

 <span data-ttu-id="edbb1-105">**目標:** この手順では、在庫補充メッセージのスキーマを定義します。</span><span class="sxs-lookup"><span data-stu-id="edbb1-105">**Objective:** In this step, you define the schema of the inventory replenishment message.</span></span>  <span data-ttu-id="edbb1-106">倉庫システムでは、在庫の補充を要求するためには、このメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="edbb1-106">The warehouse system sends this message for requesting inventory replenishment.</span></span>  <span data-ttu-id="edbb1-107">これは、このプロジェクトを作成する必要があります、2 つのスキーマのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="edbb1-107">This is one of the two schemas you must create for this project.</span></span>  

 <span data-ttu-id="edbb1-108">**目的:** XML は、構造体だけでなくと標準化されたマークアップ コードを使用して情報を識別しますが、スキーマを使用する機能もあります。</span><span class="sxs-lookup"><span data-stu-id="edbb1-108">**Purpose:** XML not only structures and identifies information with standardized markup codes, but also has the ability to use schemas.</span></span> <span data-ttu-id="edbb1-109">スキーマは、他の XML ドキュメントによってディクショナリのように機能し、参照として提供される XML ドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="edbb1-109">A schema is an XML document that works like a dictionary and is used as a reference by other XML documents.</span></span> <span data-ttu-id="edbb1-110">スキーマ コードは、XML 要素のスペルおよびこれらの要素で囲まれているデータの種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="edbb1-110">The schema code defines the spelling of XML elements and the type of data enclosed by those elements.</span></span> <span data-ttu-id="edbb1-111">スキーマを使用して XML 文書化し、情報の種類と構造が正しいことを確実に処理するプログラムの簡単な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="edbb1-111">Using schemas provides an easy way for a program to process XML documents and ensures that the structure and type of information is correct.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="edbb1-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="edbb1-112">Prerequisites</span></span>  
 <span data-ttu-id="edbb1-113">このステップを開始する前に、以下の要件を確認してください。</span><span class="sxs-lookup"><span data-stu-id="edbb1-113">Note the following requirements before you begin this step:</span></span>  

-   <span data-ttu-id="edbb1-114">この手順を開始する前に行う必要があります[手順 1。EAISchemas プロジェクトの作成](../core/step-1-create-eaischemas-project.md)です。</span><span class="sxs-lookup"><span data-stu-id="edbb1-114">Before you begin this step you must complete [Step 1: Create EAISchemas Project](../core/step-1-create-eaischemas-project.md).</span></span>  

## <a name="procedures"></a><span data-ttu-id="edbb1-115">手順</span><span class="sxs-lookup"><span data-stu-id="edbb1-115">Procedures</span></span>  
 <span data-ttu-id="edbb1-116">[手順 1。EAISchemas プロジェクトの作成](../core/step-1-create-eaischemas-project.md)、新しく作成した[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="edbb1-116">In [Step 1: Create EAISchemas Project](../core/step-1-create-eaischemas-project.md), you created a new [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project.</span></span>  <span data-ttu-id="edbb1-117">閉じた場合、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ウィンドウで、プロジェクトを開いて、次の手順を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="edbb1-117">If you close the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] window, you can use the following procedure to open the project.</span></span>  <span data-ttu-id="edbb1-118">それ以外の場合、"Visual Studio プロジェクトを開く"に、この手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="edbb1-118">Otherwise, you can skip this procedure, “To open the Visual Studio project”.</span></span>  

#### <a name="to-open-the-visual-studio-project"></a><span data-ttu-id="edbb1-119">Visual Studio プロジェクトを開く</span><span class="sxs-lookup"><span data-stu-id="edbb1-119">To open the Visual Studio project</span></span>  

1. <span data-ttu-id="edbb1-120">開始**Microsoft Visual Studio**します。</span><span class="sxs-lookup"><span data-stu-id="edbb1-120">Start **Microsoft Visual Studio**.</span></span>  

2. <span data-ttu-id="edbb1-121">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]の**ファイル**メニューで、**オープン**、 をクリックし、**プロジェクト/ソリューション**。</span><span class="sxs-lookup"><span data-stu-id="edbb1-121">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  

3. <span data-ttu-id="edbb1-122">**プロジェクトを開く** ダイアログ ボックスを参照、 **C:\BTSTutorials\EAISolution\EAISolution.sln**ソリューション ファイル、およびクリック**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="edbb1-122">In the **Open Project** dialog box, browse to the **C:\BTSTutorials\EAISolution\EAISolution.sln** solution file, and then click **Open**.</span></span>  

   <span data-ttu-id="edbb1-123">次の手順では、在庫補充メッセージ用のプロジェクトに新しいスキーマ ファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="edbb1-123">In the following procedure, you add a new schema file to the project for the inventory replenishment message.</span></span>  

#### <a name="to-add-a-new-schema-to-the-project"></a><span data-ttu-id="edbb1-124">新しいスキーマをプロジェクトに追加するには</span><span class="sxs-lookup"><span data-stu-id="edbb1-124">To add a new schema to the project</span></span>  

1. <span data-ttu-id="edbb1-125">ソリューション エクスプ ローラーで右クリックし、 **EAISchemas**プロジェクトをポイントして、**追加**、 をクリックし、**新しい項目の**。</span><span class="sxs-lookup"><span data-stu-id="edbb1-125">In Solution Explorer, right-click the **EAISchemas** project, point to **Add**, and then click **New Item**.</span></span>  

2. <span data-ttu-id="edbb1-126">**新しい項目の追加 - EAISchemas**  ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="edbb1-126">In the **Add New Item - EAISchemas** dialog box, do the following:</span></span>  


   |        <span data-ttu-id="edbb1-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="edbb1-127">Use this</span></span>         |                   <span data-ttu-id="edbb1-128">目的</span><span class="sxs-lookup"><span data-stu-id="edbb1-128">To do this</span></span>                   |
   |-------------------------|------------------------------------------------|
   | <span data-ttu-id="edbb1-129">**インストール済みテンプレート**</span><span class="sxs-lookup"><span data-stu-id="edbb1-129">**Installed Templates**</span></span> | <span data-ttu-id="edbb1-130">クリックして**スキーマ ファイル**、 をクリックし、**スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="edbb1-130">Click **Schema Files**, then click **Schema**.</span></span> |
   |        <span data-ttu-id="edbb1-131">**名前**</span><span class="sxs-lookup"><span data-stu-id="edbb1-131">**Name**</span></span>         |             <span data-ttu-id="edbb1-132">型**Request.xsd**します。</span><span class="sxs-lookup"><span data-stu-id="edbb1-132">Type **Request.xsd**.</span></span>              |


3. <span data-ttu-id="edbb1-133">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="edbb1-133">Click **Add**.</span></span> <span data-ttu-id="edbb1-134">スキーマ ツリーと XSD ペインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="edbb1-134">The schema tree and XSD pane appear.</span></span> <span data-ttu-id="edbb1-135">この領域[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk エディターと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="edbb1-135">This area of [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] is referred to as BizTalk Editor.</span></span> <span data-ttu-id="edbb1-136">さらに、ソリューション エクスプ ローラーでは、EAISchemas プロジェクトの下に新しいスキーマが表示されます。</span><span class="sxs-lookup"><span data-stu-id="edbb1-136">In addition, your new schema appears in Solution Explorer below the EAISchemas project.</span></span>  

    <span data-ttu-id="edbb1-137">![BizTalk プロジェクトのさまざまな部分](../core/media/differentpartsofbiztalkserver.gif "DifferentpartsofBizTalkServer")</span><span class="sxs-lookup"><span data-stu-id="edbb1-137">![Different Parts of BizTalk Project](../core/media/differentpartsofbiztalkserver.gif "DifferentpartsofBizTalkServer")</span></span>  

#### <a name="to-add-elements-to-the-schema"></a><span data-ttu-id="edbb1-138">スキーマの要素を追加するには</span><span class="sxs-lookup"><span data-stu-id="edbb1-138">To add elements to the schema</span></span>  

1. <span data-ttu-id="edbb1-139">スキーマ ツリーで、をクリックして、**ルート**ノード。</span><span class="sxs-lookup"><span data-stu-id="edbb1-139">In schema tree, click the **Root** node.</span></span>  

2. <span data-ttu-id="edbb1-140">プロパティ ペインでの値を変更、**ノード名**プロパティを`Request`、し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="edbb1-140">In the Properties pane, change the value of the **Node Name** property to `Request`, and then press ENTER.</span></span>  

3. <span data-ttu-id="edbb1-141">スキーマ ツリーで、右クリックし、**要求**に**スキーマ ノードの挿入**、 をクリックし、**子レコード**。</span><span class="sxs-lookup"><span data-stu-id="edbb1-141">In schema tree, right-click the **Request** node, point to **Insert Schema Node**, and then click **Child Record**.</span></span>  

4. <span data-ttu-id="edbb1-142">型`Header`として、新しいレコードの名前、子、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="edbb1-142">Type `Header` as the new name for the child record, and then press ENTER.</span></span>  

5. <span data-ttu-id="edbb1-143">手順 3. および 4. を 2 つ目の子を作成するレコードを繰り返して、**要求**ノード、名前を付けます`Items`。</span><span class="sxs-lookup"><span data-stu-id="edbb1-143">Repeat step 3 and 4 to create a second child record for the **Request** node, and name it `Items`.</span></span>  

6. <span data-ttu-id="edbb1-144">スキーマ ツリーで、右クリックし、**ヘッダー**に**スキーマ ノードの挿入**、 をクリックし、**子フィールド要素**。</span><span class="sxs-lookup"><span data-stu-id="edbb1-144">In schema tree, right-click the **Header** node, point to **Insert Schema Node**, and then click **Child Field Element**.</span></span>  

7. <span data-ttu-id="edbb1-145">型`ReqID`要素、および、ENTER キーを押して新しい名前として。</span><span class="sxs-lookup"><span data-stu-id="edbb1-145">Type `ReqID` as the new name for the element, and then press ENTER.</span></span>  

8. <span data-ttu-id="edbb1-146">手順 6 と 7 を作成する 2 つ目の子フィールド要素、**ヘッダー**ノード、名前を付けます`OrderDate`します。</span><span class="sxs-lookup"><span data-stu-id="edbb1-146">Repeat step 6 and 7 to create a second child field element for the **Header** node, and name it `OrderDate`.</span></span>

9. <span data-ttu-id="edbb1-147">手順 6 と 7 を作成する 3 つ目の子フィールド要素、**ヘッダー**ノード、名前を付けます`GrandTotal`します。</span><span class="sxs-lookup"><span data-stu-id="edbb1-147">Repeat step 6 and 7 to create a third child field element for the **Header** node, and name it `GrandTotal`.</span></span>

10. <span data-ttu-id="edbb1-148">スキーマ ツリーで、右クリックし、**項目**に**スキーマ ノードの挿入**、 をクリックし、**子レコード**。</span><span class="sxs-lookup"><span data-stu-id="edbb1-148">In schema tree, right-click the **Items** node, point to **Insert Schemas Node**, and then click **Child Record**.</span></span>  

11. <span data-ttu-id="edbb1-149">型`Item`として、新しいレコードの名前、子、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="edbb1-149">Type `Item` as the new name for the child record, and then press ENTER.</span></span>  

12. <span data-ttu-id="edbb1-150">スキーマ ツリーで、右クリックし、**項目**ノードで、次の子フィールド要素を追加。</span><span class="sxs-lookup"><span data-stu-id="edbb1-150">In schema tree, right-click the **Item** node, and add the following child field elements:</span></span>  

    - `Description`  

    - `Quantity`  

    - `UnitPrice`  

      <span data-ttu-id="edbb1-151">完成した Request.xsd は、次の図のようになります。</span><span class="sxs-lookup"><span data-stu-id="edbb1-151">The completed Request.xsd should look similar to the following figure.</span></span>  

      <span data-ttu-id="edbb1-152">![要求スキーマを使用して、ソリューション エクスプ ローラー](../core/media/solutionexplorerwiththerequestschema.gif "SolutionExplorerwiththeRequestSchema")</span><span class="sxs-lookup"><span data-stu-id="edbb1-152">![Solution Explorer with the Request Schema](../core/media/solutionexplorerwiththerequestschema.gif "SolutionExplorerwiththeRequestSchema")</span></span>  

    <span data-ttu-id="edbb1-153">スキーマにノードを追加すると、それらのプロパティは既定値のセットが提供されます。</span><span class="sxs-lookup"><span data-stu-id="edbb1-153">When you add nodes to a schema, BizTalk Editor gives a set of default values for their properties.</span></span>  <span data-ttu-id="edbb1-154">要件に基づいてそれらを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="edbb1-154">You must configure them based on the requirements.</span></span>  

#### <a name="to-configure-the-elements"></a><span data-ttu-id="edbb1-155">要素を構成するには</span><span class="sxs-lookup"><span data-stu-id="edbb1-155">To configure the elements</span></span>  

1. <span data-ttu-id="edbb1-156">スキーマ ツリーで、次のようにクリックします。 **OrderDate**をオンにします。</span><span class="sxs-lookup"><span data-stu-id="edbb1-156">In schema tree, click **OrderDate** to select it.</span></span>  

2. <span data-ttu-id="edbb1-157">プロパティ ペインで次のように変更します。**データ型**に**xs:dateTime**します。</span><span class="sxs-lookup"><span data-stu-id="edbb1-157">In the Properties pane, change **Data Type** to **xs:dateTime**.</span></span>  

3. <span data-ttu-id="edbb1-158">1 と 2 は、次のプロパティを構成する手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="edbb1-158">Repeat step 1 and 2 to configure the following properties:</span></span>  

   |<span data-ttu-id="edbb1-159">要素</span><span class="sxs-lookup"><span data-stu-id="edbb1-159">Element</span></span>|<span data-ttu-id="edbb1-160">プロパティ</span><span class="sxs-lookup"><span data-stu-id="edbb1-160">Property</span></span>|<span data-ttu-id="edbb1-161">値</span><span class="sxs-lookup"><span data-stu-id="edbb1-161">Value</span></span>|  
   |-------------|--------------|-----------|  
   |<span data-ttu-id="edbb1-162">**[総計]**</span><span class="sxs-lookup"><span data-stu-id="edbb1-162">**GrandTotal**</span></span>|<span data-ttu-id="edbb1-163">**[データ型]**</span><span class="sxs-lookup"><span data-stu-id="edbb1-163">**Data Type**</span></span>|<span data-ttu-id="edbb1-164">**Xs:decimal**</span><span class="sxs-lookup"><span data-stu-id="edbb1-164">**Xs:decimal**</span></span>|  
   |<span data-ttu-id="edbb1-165">**アイテム**</span><span class="sxs-lookup"><span data-stu-id="edbb1-165">**Item**</span></span>|<span data-ttu-id="edbb1-166">**Max Occurs します。**</span><span class="sxs-lookup"><span data-stu-id="edbb1-166">**Max Occurs**</span></span>|<span data-ttu-id="edbb1-167">**無制限**</span><span class="sxs-lookup"><span data-stu-id="edbb1-167">**Unbounded**</span></span>|  
   |<span data-ttu-id="edbb1-168">**アイテム**</span><span class="sxs-lookup"><span data-stu-id="edbb1-168">**Item**</span></span>|<span data-ttu-id="edbb1-169">**Min Occurs します。**</span><span class="sxs-lookup"><span data-stu-id="edbb1-169">**Min Occurs**</span></span>|<span data-ttu-id="edbb1-170">**1**</span><span class="sxs-lookup"><span data-stu-id="edbb1-170">**1**</span></span>|  
   |<span data-ttu-id="edbb1-171">**数量**</span><span class="sxs-lookup"><span data-stu-id="edbb1-171">**Quantity**</span></span>|<span data-ttu-id="edbb1-172">**[データ型]**</span><span class="sxs-lookup"><span data-stu-id="edbb1-172">**Data Type**</span></span>|<span data-ttu-id="edbb1-173">**xs:unsignedInt**</span><span class="sxs-lookup"><span data-stu-id="edbb1-173">**xs:unsignedInt**</span></span>|  

   <span data-ttu-id="edbb1-174">スキーマでは、多くの要素を使用できますが、アプリケーションは、データ処理のうちのいくつかを使用することのみ必要があります。</span><span class="sxs-lookup"><span data-stu-id="edbb1-174">A schema can have many elements, but your application may only require that you use a few of them for your data processing.</span></span> <span data-ttu-id="edbb1-175">コンピューター リソースを保存するには、BizTalk Server は、各スキーマ要素を自動的に読み取りますしません。</span><span class="sxs-lookup"><span data-stu-id="edbb1-175">To save computer resources, BizTalk Server doesn't automatically read each schema element.</span></span> <span data-ttu-id="edbb1-176">BizTalk Server の特定の要素からデータを読み取る場合は、プロパティを昇格する BizTalk エディターを使用して、その要素を識別する必要があります。</span><span class="sxs-lookup"><span data-stu-id="edbb1-176">If you want BizTalk Server to read data from a specific element, you must identify that element by using BizTalk Editor to promote its properties.</span></span>  

   <span data-ttu-id="edbb1-177">オーケストレーション内に作成する[レッスン 2。ビジネス プロセスの定義](../core/lesson-2-define-the-business-process.md)メッセージをルーティングするための GrandTotal フィールドに基づきます。</span><span class="sxs-lookup"><span data-stu-id="edbb1-177">The orchestration that we will create in [Lesson 2: Define the Business Process](../core/lesson-2-define-the-business-process.md) will base on the GrandTotal field to route messages.</span></span>  <span data-ttu-id="edbb1-178">したがって、GrandTotal フィールドで昇格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="edbb1-178">So we must promote the GrandTotal field.</span></span>  

#### <a name="to-promote-an-element"></a><span data-ttu-id="edbb1-179">要素を昇格するには</span><span class="sxs-lookup"><span data-stu-id="edbb1-179">To promote an element</span></span>  

1.  <span data-ttu-id="edbb1-180">スキーマ ツリーで、右クリックして**GrandTotal**、 をポイント**昇格**、 をクリックし、**クイック昇格**します。</span><span class="sxs-lookup"><span data-stu-id="edbb1-180">In Schema tree, right-click **GrandTotal**, point to **Promote**, and then click **Quick Promotions**.</span></span>  

2.  <span data-ttu-id="edbb1-181">をクリックして**OK**プロパティ スキーマを追加することを確認します。</span><span class="sxs-lookup"><span data-stu-id="edbb1-181">Click **OK** to acknowledge adding a property schema.</span></span>  

3.  <span data-ttu-id="edbb1-182">**[ファイル]** メニューの **[すべてを保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="edbb1-182">On the **File** menu, click **Save All**.</span></span>  

## <a name="what-did-i-just-do"></a><span data-ttu-id="edbb1-183">でしただけ何か。</span><span class="sxs-lookup"><span data-stu-id="edbb1-183">What did I just do?</span></span>  
 <span data-ttu-id="edbb1-184">この手順では、倉庫の在庫補充メッセージ スキーマを定義します。</span><span class="sxs-lookup"><span data-stu-id="edbb1-184">In this step, you defined the warehouse inventory replenishment message schema.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="edbb1-185">次の手順</span><span class="sxs-lookup"><span data-stu-id="edbb1-185">Next Steps</span></span>  
 <span data-ttu-id="edbb1-186">要求拒否メッセージのスキーマを定義します。</span><span class="sxs-lookup"><span data-stu-id="edbb1-186">You define the request decline message schema.</span></span>  

## <a name="see-also"></a><span data-ttu-id="edbb1-187">参照</span><span class="sxs-lookup"><span data-stu-id="edbb1-187">See Also</span></span>  
 <span data-ttu-id="edbb1-188">[ステップ 1: EAISchemas プロジェクトを作成します。](../core/step-1-create-eaischemas-project.md) </span><span class="sxs-lookup"><span data-stu-id="edbb1-188">[Step 1: Create EAISchemas Project](../core/step-1-create-eaischemas-project.md) </span></span>  
 <span data-ttu-id="edbb1-189">[ステップ 3:要求拒否スキーマを作成します。](../core/step-3-create-the-request-decline-schema.md) </span><span class="sxs-lookup"><span data-stu-id="edbb1-189">[Step 3: Create the Request Decline Schema](../core/step-3-create-the-request-decline-schema.md) </span></span>  
 <span data-ttu-id="edbb1-190">[手順 4:マップを作成します。](../core/step-4-create-the-map.md) </span><span class="sxs-lookup"><span data-stu-id="edbb1-190">[Step 4: Create the Map](../core/step-4-create-the-map.md) </span></span>  
 <span data-ttu-id="edbb1-191">[手順 5:EAISchemas プロジェクトをビルドします。](../core/step-5-build-the-eaischemas-project.md) </span><span class="sxs-lookup"><span data-stu-id="edbb1-191">[Step 5: Build the EAISchemas Project](../core/step-5-build-the-eaischemas-project.md) </span></span>  
 <span data-ttu-id="edbb1-192">[BizTalk エディターを使用してスキーマを作成します。](../core/creating-schemas-using-biztalk-editor.md) </span><span class="sxs-lookup"><span data-stu-id="edbb1-192">[Creating Schemas Using BizTalk Editor](../core/creating-schemas-using-biztalk-editor.md) </span></span>  
 [<span data-ttu-id="edbb1-193">BizTalk メッセージ コンテキストのプロパティについて</span><span class="sxs-lookup"><span data-stu-id="edbb1-193">About BizTalk Message Context Properties</span></span>](../core/about-biztalk-message-context-properties.md)
