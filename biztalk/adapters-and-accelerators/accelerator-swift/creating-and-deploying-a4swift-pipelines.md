---
title: "作成して、A4SWIFT パイプラインを展開する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, pipelines
- deploying, pipelines
- pipelines, deploying
- pipelines, creating
ms.assetid: 2a614510-7e15-4e88-9012-fc019d3aefee
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bec21ebd5a3b32986969676a78109cad55d870cf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-and-deploying-a4swift-pipelines"></a><span data-ttu-id="a972b-102">作成して、A4SWIFT パイプラインを展開します。</span><span class="sxs-lookup"><span data-stu-id="a972b-102">Creating and Deploying A4SWIFT Pipelines</span></span>
<span data-ttu-id="a972b-103">次の図に示すように作成し、メッセージ repair and new submission の SWIFT パイプラインを展開するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a972b-103">Perform the following steps to create and deploy SWIFT pipelines for message repair and new submission, as shown in the following figure.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-pipeline-configuration.gif "A4SWIFT_Pipeline_Configuration")  
  
 <span data-ttu-id="a972b-104">**概要**</span><span class="sxs-lookup"><span data-stu-id="a972b-104">**Summary**</span></span>  
  
 <span data-ttu-id="a972b-105">次のスキーマを展開します。</span><span class="sxs-lookup"><span data-stu-id="a972b-105">Deploy the following schemas:</span></span>  
  
-   <span data-ttu-id="a972b-106">カスタムは、SWIFT 逆アセンブラのパイプラインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a972b-106">Custom receive pipeline with the SWIFT Disassembler.</span></span> <span data-ttu-id="a972b-107">BRE の検証および XML プロパティを設定すると、True、かつ、SWIFT ヘッダー スキーマ プロパティを (なし)。</span><span class="sxs-lookup"><span data-stu-id="a972b-107">Set BRE Validation and XML Validation properties to True, and the SWIFT Header Schema property to (None).</span></span>  
  
-   <span data-ttu-id="a972b-108">カスタム送信パイプラインに SWIFT アセンブラー</span><span class="sxs-lookup"><span data-stu-id="a972b-108">Custom send pipeline with the SWIFT Assembler</span></span>  
  
### <a name="to-create-a-pipeline-project"></a><span data-ttu-id="a972b-109">パイプライン プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="a972b-109">To create a pipeline project</span></span>  
  
1.  <span data-ttu-id="a972b-110">Visual Studio で、[**ファイル**、] をポイント**新規**、クリックして**プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="a972b-110">In Visual Studio, click **File**, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="a972b-111">新しいプロジェクト ダイアログ ボックスで、**プロジェクトの種類**ペインで、 **BizTalk プロジェクト**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="a972b-111">In the New Project dialog box, in the **Project types** pane, select the **BizTalk Projects** folder.</span></span>  
  
3.  <span data-ttu-id="a972b-112">**テンプレート**ペインで、**空の BizTalk Server プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="a972b-112">In the **Templates** pane, select **Empty BizTalk Server Project**.</span></span>  
  
4.  <span data-ttu-id="a972b-113">**名前**ボックスで、プロジェクト名の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a972b-113">In the **Name** box, type the name you want for the project name.</span></span>  
  
5.  <span data-ttu-id="a972b-114">**ソリューション**ボックスで、**ソリューションに追加**です。</span><span class="sxs-lookup"><span data-stu-id="a972b-114">In the **Solution** box, select **Add to Solution**.</span></span> <span data-ttu-id="a972b-115">**場所**ボックスで作成したスキーマ プロジェクトの場所を入力[A4SWIFT のスキーマを展開する](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md)です。</span><span class="sxs-lookup"><span data-stu-id="a972b-115">In the **Location** box, enter the location of the schema project that you created in [Deploying A4SWIFT Schemas](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md).</span></span>  
  
6.  <span data-ttu-id="a972b-116">をクリックして**OK**新しいプロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="a972b-116">Click **OK** to open the new project.</span></span>  
    [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="a972b-117">[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]ソリューション エクスプ ローラーに新しいプロジェクトを追加し、指定されたフォルダーにプロジェクト フォルダーとファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="a972b-117">[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] adds a new project to Solution Explorer, and creates the project folder and files in the folder specified.</span></span>  
  
7.  <span data-ttu-id="a972b-118">作成し、強力なキー ファイルをプロジェクトに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a972b-118">Create and assign a strong key file to the project.</span></span> <span data-ttu-id="a972b-119">詳細についてを参照してください「プロジェクトを作成する、厳密な名前 SWIFT」 [A4SWIFT のスキーマを展開する](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md)です。</span><span class="sxs-lookup"><span data-stu-id="a972b-119">For more information, see "To create a strong-named SWIFT project" in [Deploying A4SWIFT Schemas](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md).</span></span>  
  
### <a name="to-add-a-custom-receive-pipeline"></a><span data-ttu-id="a972b-120">カスタム受信パイプラインを追加するには</span><span class="sxs-lookup"><span data-stu-id="a972b-120">To add a custom receive pipeline</span></span>  
  
1.  <span data-ttu-id="a972b-121">ソリューション エクスプ ローラーで、パイプライン プロジェクトを右クリックし、**追加**、クリックして**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="a972b-121">In Solution Explorer, right-click your pipeline project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="a972b-122">新しい項目の追加 ダイアログ ボックスで、**パイプライン ファイル**カテゴリ ウィンドウで、選択**受信パイプライン**テンプレート ペインからです。</span><span class="sxs-lookup"><span data-stu-id="a972b-122">In the Add New Item dialog box, click **Pipeline Files** in the Categories pane, and then select **Receive Pipeline** from the Templates pane.</span></span>  
  
3.  <span data-ttu-id="a972b-123">**名前**ボックスで、パイプラインの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a972b-123">In the **Name** box, type a name for the pipeline.</span></span>  
  
4.  <span data-ttu-id="a972b-124">をクリックして**追加**BizTalk パイプライン デザイナーで空白のパイプラインを開きます。</span><span class="sxs-lookup"><span data-stu-id="a972b-124">Click **Add** to open the blank pipeline in BizTalk Pipeline Designer.</span></span>  
  
5.  <span data-ttu-id="a972b-125">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]をクリックして**ビュー**し**ツールボックス**です。</span><span class="sxs-lookup"><span data-stu-id="a972b-125">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **View** and then **Toolbox**.</span></span>  
  
6.  <span data-ttu-id="a972b-126">**BizTalk パイプライン コンポーネントのツールボックス**、ドラッグ、 **SWIFT 逆アセンブラー**を**ここにドロップ**下のボックス、**逆アセンブル**ステージ図形に**BizTalk パイプライン デザイナ**です。</span><span class="sxs-lookup"><span data-stu-id="a972b-126">From the **BizTalk Pipeline Components Toolbox**, drag the **SWIFT Disassembler** to the **Drop Here** box below the **Disassemble** stage shape in **BizTalk Pipeline Designer**.</span></span> <span data-ttu-id="a972b-127">ままにして、 **SWIFT 逆アセンブラー**で選択されて、 **BizTalk パイプライン デザイナ**です。</span><span class="sxs-lookup"><span data-stu-id="a972b-127">Leave the **SWIFT Disassembler** as selected in the **BizTalk Pipeline Designer**.</span></span>  
  
7.  <span data-ttu-id="a972b-128">**プロパティ**、いることを確認、 **BRE 検証**と**XML 検証**プロパティに設定されます**True**です。</span><span class="sxs-lookup"><span data-stu-id="a972b-128">In **Properties**, verify that the **BRE Validation** and **XML Validation** properties are set to **True**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a972b-129">SWIFT ヘッダー スキーマ プロパティを設定する必要があります**(なし)**です。</span><span class="sxs-lookup"><span data-stu-id="a972b-129">The SWIFT Header Schema property should be set to **(None)**.</span></span>  
  
8.  <span data-ttu-id="a972b-130">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]をクリックして**ファイル**、し**すべてを保存**です。</span><span class="sxs-lookup"><span data-stu-id="a972b-130">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **File**, and then **Save All**.</span></span>  
  
### <a name="to-add-a-custom-send-pipeline"></a><span data-ttu-id="a972b-131">カスタム送信パイプラインを追加するには</span><span class="sxs-lookup"><span data-stu-id="a972b-131">To add a custom send pipeline</span></span>  
  
1.  <span data-ttu-id="a972b-132">ソリューション エクスプ ローラーで右クリックし、 **SWIFTPipelines**プロジェクトをポイントし、**追加**、順にクリック**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="a972b-132">In Solution Explorer, right-click the **SWIFTPipelines** project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="a972b-133">新しい項目の追加 ダイアログ ボックスであることを確認**パイプライン ファイル**が選択されてカテゴリ ウィンドウで、**送信パイプライン**テンプレート ペインからです。</span><span class="sxs-lookup"><span data-stu-id="a972b-133">In the Add New Item dialog box, verify that **Pipeline Files** is selected in the Categories pane, and then select **Send Pipeline** from the Templates pane.</span></span>  
  
3.  <span data-ttu-id="a972b-134">**名前**ボックスで、パイプラインの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a972b-134">In the **Name** box, type a name for the pipeline.</span></span>  
  
4.  <span data-ttu-id="a972b-135">をクリックして**追加**BizTalk パイプライン デザイナーで空白のパイプラインを開きます。</span><span class="sxs-lookup"><span data-stu-id="a972b-135">Click **Add** to open the blank pipeline in BizTalk Pipeline Designer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a972b-136">BizTalk パイプライン デザイナーで空のパイプラインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a972b-136">An empty pipeline appears in the BizTalk Pipeline Designer.</span></span> [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="a972b-137">ソリューション エクスプ ローラーに SWIFTPipelines プロジェクトの下で、新しいパイプラインを追加します。</span><span class="sxs-lookup"><span data-stu-id="a972b-137"> adds the new pipeline to Solution Explorer under the SWIFTPipelines project.</span></span>  
  
5.  <span data-ttu-id="a972b-138">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]をクリックして**ビュー**し**ツールボックス**です。</span><span class="sxs-lookup"><span data-stu-id="a972b-138">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **View** and then **Toolbox**.</span></span>  
  
6.  <span data-ttu-id="a972b-139">**BizTalk パイプライン コンポーネントのツールボックス**、ドラッグ**SWIFT アセンブラー**を**ここにドロップ**下のボックス、**アセンブル**で図形をステージ**BizTalk パイプライン デザイナ**です。</span><span class="sxs-lookup"><span data-stu-id="a972b-139">In the **BizTalk Pipeline Components Toolbox**, drag **SWIFT Assembler** to the **Drop Here** box below the **Assemble** stage shape in **BizTalk Pipeline Designer**.</span></span>  
  
7.  <span data-ttu-id="a972b-140">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]をクリックして**ファイル**、し**すべてを保存**です。</span><span class="sxs-lookup"><span data-stu-id="a972b-140">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **File**, and then **Save All**.</span></span>  
  
8.  <span data-ttu-id="a972b-141">パイプライン プロジェクトを右クリックし、をクリックして**ビルド**です。</span><span class="sxs-lookup"><span data-stu-id="a972b-141">Right click the pipelines project, and then click **Build**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a972b-142">コンパイル プロセス中に表示しないようにすべてのエラーです。</span><span class="sxs-lookup"><span data-stu-id="a972b-142">During the compilation process, you should not see any failures.</span></span> <span data-ttu-id="a972b-143">場合は、エラーの原因を確認して修正して、プロジェクトを再構築します。</span><span class="sxs-lookup"><span data-stu-id="a972b-143">If you do, check the source of the error, correct it and then re-build the project.</span></span> <span data-ttu-id="a972b-144">ただし、警告が表示、可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a972b-144">You may, however, see warnings.</span></span> <span data-ttu-id="a972b-145">警告を引き起こす状況を修正することができます。</span><span class="sxs-lookup"><span data-stu-id="a972b-145">You can correct the condition leading to the warnings.</span></span> <span data-ttu-id="a972b-146">詳細についてを参照してください「パイプライン プロジェクトをビルドすることがありますで警告を表示」[その他の既知の問題](http://msdn.microsoft.com/library/bc94c781-2a56-4f80-8ecb-e654de2f6ed6)です。</span><span class="sxs-lookup"><span data-stu-id="a972b-146">For more information, see "Building a pipeline project may result in warnings" in [Miscellaneous Known Issues](http://msdn.microsoft.com/library/bc94c781-2a56-4f80-8ecb-e654de2f6ed6).</span></span>  
  
9. <span data-ttu-id="a972b-147">パイプライン プロジェクトを右クリックし、をクリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="a972b-147">Right click the pipelines project, and then click **Deploy**.</span></span>