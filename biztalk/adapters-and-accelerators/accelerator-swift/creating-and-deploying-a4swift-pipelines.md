---
title: A4SWIFT パイプラインの作成と |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, pipelines
- deploying, pipelines
- pipelines, deploying
- pipelines, creating
ms.assetid: 2a614510-7e15-4e88-9012-fc019d3aefee
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64c58e313b3b48b78c6a0788b9a104cff3d18d2b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378435"
---
# <a name="creating-and-deploying-a4swift-pipelines"></a><span data-ttu-id="d575c-102">A4SWIFT パイプラインの作成と</span><span class="sxs-lookup"><span data-stu-id="d575c-102">Creating and Deploying A4SWIFT Pipelines</span></span>
<span data-ttu-id="d575c-103">次の図に示すように作成してメッセージ repair and new submission は、SWIFT パイプラインをデプロイするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d575c-103">Perform the following steps to create and deploy SWIFT pipelines for message repair and new submission, as shown in the following figure.</span></span>  

 <span data-ttu-id="d575c-104">![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-pipeline-configuration.gif "A4SWIFT_Pipeline_Configuration")</span><span class="sxs-lookup"><span data-stu-id="d575c-104">![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-pipeline-configuration.gif "A4SWIFT_Pipeline_Configuration")</span></span>  

 <span data-ttu-id="d575c-105">**まとめ**</span><span class="sxs-lookup"><span data-stu-id="d575c-105">**Summary**</span></span>  

 <span data-ttu-id="d575c-106">次のスキーマを展開します。</span><span class="sxs-lookup"><span data-stu-id="d575c-106">Deploy the following schemas:</span></span>  

-   <span data-ttu-id="d575c-107">カスタムの受信、SWIFT 逆アセンブラーをパイプラインします。</span><span class="sxs-lookup"><span data-stu-id="d575c-107">Custom receive pipeline with the SWIFT Disassembler.</span></span> <span data-ttu-id="d575c-108">True、SWIFT ヘッダー スキーマ プロパティを (None) には、BRE の検証および XML の検証のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="d575c-108">Set BRE Validation and XML Validation properties to True, and the SWIFT Header Schema property to (None).</span></span>  

-   <span data-ttu-id="d575c-109">カスタム送信パイプラインに SWIFT アセンブラー</span><span class="sxs-lookup"><span data-stu-id="d575c-109">Custom send pipeline with the SWIFT Assembler</span></span>  

### <a name="to-create-a-pipeline-project"></a><span data-ttu-id="d575c-110">パイプライン プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="d575c-110">To create a pipeline project</span></span>  

1. <span data-ttu-id="d575c-111">Visual Studio で、次のようにクリックします。**ファイル**、 をポイント**新規**、 をクリックし、**プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="d575c-111">In Visual Studio, click **File**, point to **New**, and then click **Project**.</span></span>  

2. <span data-ttu-id="d575c-112">新しいプロジェクト ダイアログ ボックスで、**プロジェクトの種類**ペインで、 **BizTalk プロジェクト**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="d575c-112">In the New Project dialog box, in the **Project types** pane, select the **BizTalk Projects** folder.</span></span>  

3. <span data-ttu-id="d575c-113">**テンプレート**ペインで、**空の BizTalk Server プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="d575c-113">In the **Templates** pane, select **Empty BizTalk Server Project**.</span></span>  

4. <span data-ttu-id="d575c-114">**名前**ボックスで、プロジェクト名の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="d575c-114">In the **Name** box, type the name you want for the project name.</span></span>  

5. <span data-ttu-id="d575c-115">**ソリューション**ボックスで、**ソリューションに追加**します。</span><span class="sxs-lookup"><span data-stu-id="d575c-115">In the **Solution** box, select **Add to Solution**.</span></span> <span data-ttu-id="d575c-116">**場所**ボックスで作成したスキーマ プロジェクトの場所を入力[A4SWIFT スキーマの展開](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md)します。</span><span class="sxs-lookup"><span data-stu-id="d575c-116">In the **Location** box, enter the location of the schema project that you created in [Deploying A4SWIFT Schemas](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md).</span></span>  

6. <span data-ttu-id="d575c-117">をクリックして**OK**を新しいプロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="d575c-117">Click **OK** to open the new project.</span></span>  
   [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="d575c-118">[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] ソリューション エクスプ ローラーに新しいプロジェクトを追加し、指定したフォルダーで、プロジェクト フォルダーとファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="d575c-118">[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] adds a new project to Solution Explorer, and creates the project folder and files in the folder specified.</span></span>  

7. <span data-ttu-id="d575c-119">作成し、厳密なキー ファイルをプロジェクトに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d575c-119">Create and assign a strong key file to the project.</span></span> <span data-ttu-id="d575c-120">詳細についてを参照してください「厳密な名前の SWIFT プロジェクトを作成するには" [A4SWIFT スキーマの展開](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md)します。</span><span class="sxs-lookup"><span data-stu-id="d575c-120">For more information, see "To create a strong-named SWIFT project" in [Deploying A4SWIFT Schemas](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md).</span></span>  

### <a name="to-add-a-custom-receive-pipeline"></a><span data-ttu-id="d575c-121">カスタム受信パイプラインを追加するには</span><span class="sxs-lookup"><span data-stu-id="d575c-121">To add a custom receive pipeline</span></span>  

1. <span data-ttu-id="d575c-122">ソリューション エクスプ ローラーで、パイプライン プロジェクトを右クリックして**追加**、 をクリックし、**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="d575c-122">In Solution Explorer, right-click your pipeline project, point to **Add**, and then click **New Item**.</span></span>  

2. <span data-ttu-id="d575c-123">新しい項目の追加 ダイアログ ボックスで、**パイプライン ファイル**カテゴリ ウィンドウで選択し**受信パイプライン**テンプレート ペインから。</span><span class="sxs-lookup"><span data-stu-id="d575c-123">In the Add New Item dialog box, click **Pipeline Files** in the Categories pane, and then select **Receive Pipeline** from the Templates pane.</span></span>  

3. <span data-ttu-id="d575c-124">**名前**ボックスに、パイプラインの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="d575c-124">In the **Name** box, type a name for the pipeline.</span></span>  

4. <span data-ttu-id="d575c-125">クリックして**追加**に BizTalk パイプライン デザイナで、空のパイプラインを開きます。</span><span class="sxs-lookup"><span data-stu-id="d575c-125">Click **Add** to open the blank pipeline in BizTalk Pipeline Designer.</span></span>  

5. <span data-ttu-id="d575c-126">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、 をクリックして**ビュー**し**ツールボックス**します。</span><span class="sxs-lookup"><span data-stu-id="d575c-126">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **View** and then **Toolbox**.</span></span>  

6. <span data-ttu-id="d575c-127">**BizTalk パイプライン コンポーネントのツールボックス**、ドラッグ、 **SWIFT 逆アセンブラー**を**ここにドロップ**下のボックス、**逆アセンブル**ステージ図形に**BizTalk パイプライン デザイナ**します。</span><span class="sxs-lookup"><span data-stu-id="d575c-127">From the **BizTalk Pipeline Components Toolbox**, drag the **SWIFT Disassembler** to the **Drop Here** box below the **Disassemble** stage shape in **BizTalk Pipeline Designer**.</span></span> <span data-ttu-id="d575c-128">ままに、 **SWIFT 逆アセンブラー**として選択された状態で、 **BizTalk パイプライン デザイナ**します。</span><span class="sxs-lookup"><span data-stu-id="d575c-128">Leave the **SWIFT Disassembler** as selected in the **BizTalk Pipeline Designer**.</span></span>  

7. <span data-ttu-id="d575c-129">**プロパティ**、いることを確認、 **BRE 検証**と**XML 検証**プロパティに設定されます**True**します。</span><span class="sxs-lookup"><span data-stu-id="d575c-129">In **Properties**, verify that the **BRE Validation** and **XML Validation** properties are set to **True**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="d575c-130">SWIFT ヘッダー スキーマ プロパティに設定する必要があります **(なし)** します。</span><span class="sxs-lookup"><span data-stu-id="d575c-130">The SWIFT Header Schema property should be set to **(None)**.</span></span>  

8. <span data-ttu-id="d575c-131">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、 をクリックして**ファイル**、し**すべて保存**します。</span><span class="sxs-lookup"><span data-stu-id="d575c-131">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **File**, and then **Save All**.</span></span>  

### <a name="to-add-a-custom-send-pipeline"></a><span data-ttu-id="d575c-132">カスタム送信パイプラインを追加するには</span><span class="sxs-lookup"><span data-stu-id="d575c-132">To add a custom send pipeline</span></span>  

1. <span data-ttu-id="d575c-133">ソリューション エクスプ ローラーで右クリックし、 **SWIFTPipelines**プロジェクトをポイントして、**追加**、 をクリックし、**新しい項目の**。</span><span class="sxs-lookup"><span data-stu-id="d575c-133">In Solution Explorer, right-click the **SWIFTPipelines** project, point to **Add**, and then click **New Item**.</span></span>  

2. <span data-ttu-id="d575c-134">新しい項目の追加 ダイアログ ボックスであることを確認**パイプライン ファイル**がカテゴリ ウィンドウで選択されて **送信パイプライン**テンプレート ペインから。</span><span class="sxs-lookup"><span data-stu-id="d575c-134">In the Add New Item dialog box, verify that **Pipeline Files** is selected in the Categories pane, and then select **Send Pipeline** from the Templates pane.</span></span>  

3. <span data-ttu-id="d575c-135">**名前**ボックスに、パイプラインの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="d575c-135">In the **Name** box, type a name for the pipeline.</span></span>  

4. <span data-ttu-id="d575c-136">クリックして**追加**に BizTalk パイプライン デザイナで、空のパイプラインを開きます。</span><span class="sxs-lookup"><span data-stu-id="d575c-136">Click **Add** to open the blank pipeline in BizTalk Pipeline Designer.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="d575c-137">BizTalk パイプライン デザイナーで空のパイプラインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d575c-137">An empty pipeline appears in the BizTalk Pipeline Designer.</span></span> [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] <span data-ttu-id="d575c-138">ソリューション エクスプ ローラーに SWIFTPipelines プロジェクトの下の新しいパイプラインを追加します。</span><span class="sxs-lookup"><span data-stu-id="d575c-138">adds the new pipeline to Solution Explorer under the SWIFTPipelines project.</span></span>  

5. <span data-ttu-id="d575c-139">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、 をクリックして**ビュー**し**ツールボックス**します。</span><span class="sxs-lookup"><span data-stu-id="d575c-139">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **View** and then **Toolbox**.</span></span>  

6. <span data-ttu-id="d575c-140">**BizTalk パイプライン コンポーネントのツールボックス**、ドラッグ**SWIFT アセンブラー**を**ここにドロップ**下のボックス、**アセンブル**で図形をステージ**BizTalk パイプライン デザイナ**します。</span><span class="sxs-lookup"><span data-stu-id="d575c-140">In the **BizTalk Pipeline Components Toolbox**, drag **SWIFT Assembler** to the **Drop Here** box below the **Assemble** stage shape in **BizTalk Pipeline Designer**.</span></span>  

7. <span data-ttu-id="d575c-141">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、 をクリックして**ファイル**、し**すべて保存**します。</span><span class="sxs-lookup"><span data-stu-id="d575c-141">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **File**, and then **Save All**.</span></span>  

8. <span data-ttu-id="d575c-142">パイプライン プロジェクトを右クリックし、をクリックし、**ビルド**します。</span><span class="sxs-lookup"><span data-stu-id="d575c-142">Right click the pipelines project, and then click **Build**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="d575c-143">コンパイル プロセス中にいない、エラーが発生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d575c-143">During the compilation process, you should not see any failures.</span></span> <span data-ttu-id="d575c-144">場合は、エラーの原因を確認、修正およびプロジェクトを再ビルドします。</span><span class="sxs-lookup"><span data-stu-id="d575c-144">If you do, check the source of the error, correct it and then re-build the project.</span></span> <span data-ttu-id="d575c-145">ただし、警告が表示、可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d575c-145">You may, however, see warnings.</span></span> <span data-ttu-id="d575c-146">警告につながる条件を修正することができます。</span><span class="sxs-lookup"><span data-stu-id="d575c-146">You can correct the condition leading to the warnings.</span></span> <span data-ttu-id="d575c-147">詳細についてを参照してください「で警告結果がパイプライン プロジェクトのビルド」[その他の既知の問題](http://msdn.microsoft.com/library/bc94c781-2a56-4f80-8ecb-e654de2f6ed6)します。</span><span class="sxs-lookup"><span data-stu-id="d575c-147">For more information, see "Building a pipeline project may result in warnings" in [Miscellaneous Known Issues](http://msdn.microsoft.com/library/bc94c781-2a56-4f80-8ecb-e654de2f6ed6).</span></span>  

9. <span data-ttu-id="d575c-148">パイプライン プロジェクトを右クリックし、をクリックし、**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="d575c-148">Right click the pipelines project, and then click **Deploy**.</span></span>
