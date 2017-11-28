---
title: "手順 1: EAIOrchestration プロジェクトをソリューションに追加する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c9aa0d9-2075-4c7e-8baf-1ecd2721859a
caps.latest.revision: "42"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3b8e2b9c197e01ed695311c67bc79cf5056c4d1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-add-eaiorchestration-project-to-the-solution"></a><span data-ttu-id="b6480-102">ステップ 1: EAIOrchestration プロジェクトのソリューションへの追加</span><span class="sxs-lookup"><span data-stu-id="b6480-102">Step 1: Add EAIOrchestration Project to the Solution</span></span>
<span data-ttu-id="b6480-103">![4 のステップ 1](../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")</span><span class="sxs-lookup"><span data-stu-id="b6480-103">![Step 1 of 4](../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")</span></span>  
  
 <span data-ttu-id="b6480-104">**所要時間:** 5 分</span><span class="sxs-lookup"><span data-stu-id="b6480-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="b6480-105">**目標:**ここでは、EAI ソリューションに 2 番目のプロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="b6480-105">**Objective:** In this step, you add a second project to the EAI solution.</span></span> <span data-ttu-id="b6480-106">新しいプロジェクトにオーケストレーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="b6480-106">Then you add an orchestration to the new project.</span></span>  
  
 <span data-ttu-id="b6480-107">**目的:**オーケストレーションに別のプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="b6480-107">**Purpose:** You create a separate project for the orchestration.</span></span> <span data-ttu-id="b6480-108">これは、ソリューションの開発に複数のスタッフが携わっている場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="b6480-108">This is helpful when you have several different people working on one solution.</span></span> <span data-ttu-id="b6480-109">このレッスンでは、新しいオーケストレーションを使用してビジネス プロセスを自動化します。</span><span class="sxs-lookup"><span data-stu-id="b6480-109">You use the new orchestration to automate the business process in this lesson.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b6480-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="b6480-110">Prerequisites</span></span>  
 <span data-ttu-id="b6480-111">このステップを開始する前に、以下の要件を確認してください。</span><span class="sxs-lookup"><span data-stu-id="b6480-111">Note the following requirements before you begin this step:</span></span>  
  
-   <span data-ttu-id="b6480-112">この手順を開始する前に行う必要があります[レッスン 1: 定義のスキーマとマップ](../core/lesson-1-define-schemas-and-a-map.md)です。</span><span class="sxs-lookup"><span data-stu-id="b6480-112">Before you begin this step you must complete [Lesson 1: Define Schemas and a Map](../core/lesson-1-define-schemas-and-a-map.md).</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="b6480-113">手順</span><span class="sxs-lookup"><span data-stu-id="b6480-113">Procedures</span></span>  
 <span data-ttu-id="b6480-114">閉じた場合は、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ウィンドウの Visual Studio プロジェクトを開く"には」の手順に従ってください[手順 2: 在庫要求スキーマの作成](../core/step-2-create-the-inventory-request-schema.md)を開きます。</span><span class="sxs-lookup"><span data-stu-id="b6480-114">If you have closed the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] window, follow the procedure “To open the Visual Studio project” in [Step 2: Create the Inventory Request Schema](../core/step-2-create-the-inventory-request-schema.md) to open it.</span></span>  
  
#### <a name="to-add-another-project-to-your-solution"></a><span data-ttu-id="b6480-115">ソリューションに別のプロジェクトを追加するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b6480-115">To add another project to your solution</span></span>  
  
1.  <span data-ttu-id="b6480-116">Visual Studio から、上、**ファイル** メニューのをポイント**追加**、順にクリック**新しいプロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="b6480-116">From Visual Studio, on the **File** menu, point to **Add**, and then click **New Project**.</span></span>  
  
2.  <span data-ttu-id="b6480-117">**新しいプロジェクト** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="b6480-117">In the **New Project** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="b6480-118">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b6480-118">Use this</span></span>|<span data-ttu-id="b6480-119">目的</span><span class="sxs-lookup"><span data-stu-id="b6480-119">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="b6480-120">**インストールされたテンプレート**</span><span class="sxs-lookup"><span data-stu-id="b6480-120">**Installed Templates**</span></span>|<span data-ttu-id="b6480-121">をクリックして**BizTalk プロジェクト**、クリックして**空の BizTalk Server プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="b6480-121">Click **BizTalk Projects**, and then click **Empty BizTalk Server Project**.</span></span>|  
    |<span data-ttu-id="b6480-122">**名前**</span><span class="sxs-lookup"><span data-stu-id="b6480-122">**Name**</span></span>|<span data-ttu-id="b6480-123">「`EAIOrchestration`.</span><span class="sxs-lookup"><span data-stu-id="b6480-123">Type `EAIOrchestration`.</span></span>|  
    |<span data-ttu-id="b6480-124">**場所**</span><span class="sxs-lookup"><span data-stu-id="b6480-124">**Location**</span></span>|<span data-ttu-id="b6480-125">「`C:\BTSTutorials\EAISolution`.</span><span class="sxs-lookup"><span data-stu-id="b6480-125">Type `C:\BTSTutorials\EAISolution`.</span></span>|  
  
3.  <span data-ttu-id="b6480-126">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b6480-126">Click **OK**.</span></span>  
  
#### <a name="to-add-an-orchestration"></a><span data-ttu-id="b6480-127">オーケストレーションを追加するには</span><span class="sxs-lookup"><span data-stu-id="b6480-127">To add an orchestration</span></span>  
  
1.  <span data-ttu-id="b6480-128">ソリューション エクスプ ローラーで右クリック**EAIOrchestration**、 をポイント**追加**、クリックして**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="b6480-128">In Solution Explorer, right-click **EAIOrchestration**, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="b6480-129">**新しい項目の追加 - EAIOrchestration**  ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="b6480-129">In the **Add New Item - EAIOrchestration** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="b6480-130">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b6480-130">Use this</span></span>|<span data-ttu-id="b6480-131">目的</span><span class="sxs-lookup"><span data-stu-id="b6480-131">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="b6480-132">**インストールされたテンプレート**</span><span class="sxs-lookup"><span data-stu-id="b6480-132">**Installed Templates**</span></span>|<span data-ttu-id="b6480-133">をクリックして**オーケストレーション ファイル**、クリックして**BizTalk オーケストレーション**です。</span><span class="sxs-lookup"><span data-stu-id="b6480-133">Click **Orchestration Files**, and then click **BizTalk Orchestration**.</span></span>|  
    |<span data-ttu-id="b6480-134">**名前**</span><span class="sxs-lookup"><span data-stu-id="b6480-134">**Name**</span></span>|<span data-ttu-id="b6480-135">型**EAIProcess.odx**です。</span><span class="sxs-lookup"><span data-stu-id="b6480-135">Type **EAIProcess.odx**.</span></span>|  
  
3.  <span data-ttu-id="b6480-136">**[追加]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b6480-136">Click **Add**.</span></span>  
  
     <span data-ttu-id="b6480-137">オーケストレーション デザイナーが開きます。</span><span class="sxs-lookup"><span data-stu-id="b6480-137">Orchestration Designer opens.</span></span> <span data-ttu-id="b6480-138">オーケストレーション デザイナーに EAIProcess オーケストレーションが表示されている状態を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b6480-138">The following figure shows Orchestration Designer with the EAIProcess orchestration.</span></span>  
  
     <span data-ttu-id="b6480-139">![新しいオーケストレーション](../core/media/tut1-eaiprocess.gif "Tut1_EAIProcess")</span><span class="sxs-lookup"><span data-stu-id="b6480-139">![New orchestration](../core/media/tut1-eaiprocess.gif "Tut1_EAIProcess")</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="b6480-140">でしただけは何ですか。</span><span class="sxs-lookup"><span data-stu-id="b6480-140">What did I just do?</span></span>  
 <span data-ttu-id="b6480-141">このステップでは、EAI ソリューションに 2 番目のプロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="b6480-141">In this step, you added a second project to the EAI solution.</span></span> <span data-ttu-id="b6480-142">新しいプロジェクトにオーケストレーションを追加しました。</span><span class="sxs-lookup"><span data-stu-id="b6480-142">Then you added an orchestration to the new project.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="b6480-143">次の手順</span><span class="sxs-lookup"><span data-stu-id="b6480-143">Next Steps</span></span>  
 <span data-ttu-id="b6480-144">ビジネス プロセスを定義した[手順 2: ビジネス プロセスの定義](../core/step-2-define-the-business-process.md)です。</span><span class="sxs-lookup"><span data-stu-id="b6480-144">You define the business process in [Step 2: Define the Business Process](../core/step-2-define-the-business-process.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6480-145">参照</span><span class="sxs-lookup"><span data-stu-id="b6480-145">See Also</span></span>  
 <span data-ttu-id="b6480-146">[手順 2: ビジネス プロセスを定義します。](../core/step-2-define-the-business-process.md) </span><span class="sxs-lookup"><span data-stu-id="b6480-146">[Step 2: Define the Business Process](../core/step-2-define-the-business-process.md) </span></span>  
 <span data-ttu-id="b6480-147">[手順 3: オーケストレーションのポートを追加します。](../core/step-3-add-ports-to-the-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="b6480-147">[Step 3: Add Ports to the Orchestration](../core/step-3-add-ports-to-the-orchestration.md) </span></span>  
 [<span data-ttu-id="b6480-148">手順 4: EAIOrchestration プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="b6480-148">Step 4: Build the EAIOrchestration Project</span></span>](../core/step-4-build-the-eaiorchestration-project.md)