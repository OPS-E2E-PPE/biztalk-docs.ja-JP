---
title: '手順 1: EAIOrchestration プロジェクトをソリューションに追加する |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1c9aa0d9-2075-4c7e-8baf-1ecd2721859a
caps.latest.revision: 42
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3b8e2b9c197e01ed695311c67bc79cf5056c4d1
ms.sourcegitcommit: 9b93ee2a019bef8d482626cf5525a6b95509b135
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2018
ms.locfileid: "22276866"
---
# <a name="step-1-add-eaiorchestration-project-to-the-solution"></a><span data-ttu-id="48127-102">ステップ 1: EAIOrchestration プロジェクトのソリューションへの追加</span><span class="sxs-lookup"><span data-stu-id="48127-102">Step 1: Add EAIOrchestration Project to the Solution</span></span>
<span data-ttu-id="48127-103">![手順 4 の 1](../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")</span><span class="sxs-lookup"><span data-stu-id="48127-103">![Step 1 of 4](../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")</span></span>  
  
 <span data-ttu-id="48127-104">**所要時間:** 5 分</span><span class="sxs-lookup"><span data-stu-id="48127-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="48127-105">**目標:** では、EAI ソリューションに 2 つ目のプロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="48127-105">**Objective:** In this step, you add a second project to the EAI solution.</span></span> <span data-ttu-id="48127-106">新しいプロジェクトにオーケストレーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="48127-106">Then you add an orchestration to the new project.</span></span>  
  
 <span data-ttu-id="48127-107">**目的:** オーケストレーション用に別のプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="48127-107">**Purpose:** You create a separate project for the orchestration.</span></span> <span data-ttu-id="48127-108">これは、ソリューションの開発に複数のスタッフが携わっている場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="48127-108">This is helpful when you have several different people working on one solution.</span></span> <span data-ttu-id="48127-109">このレッスンでは、新しいオーケストレーションを使用してビジネス プロセスを自動化します。</span><span class="sxs-lookup"><span data-stu-id="48127-109">You use the new orchestration to automate the business process in this lesson.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="48127-110">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="48127-110">Prerequisites</span></span>  
 <span data-ttu-id="48127-111">このステップを開始する前に、以下の要件を確認してください。</span><span class="sxs-lookup"><span data-stu-id="48127-111">Note the following requirements before you begin this step:</span></span>  
  
-   <span data-ttu-id="48127-112">この手順を開始する前に行う必要があります[レッスン 1: スキーマの定義およびマップ](../core/lesson-1-define-schemas-and-a-map.md)します。</span><span class="sxs-lookup"><span data-stu-id="48127-112">Before you begin this step you must complete [Lesson 1: Define Schemas and a Map](../core/lesson-1-define-schemas-and-a-map.md).</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="48127-113">手順</span><span class="sxs-lookup"><span data-stu-id="48127-113">Procedures</span></span>  
 <span data-ttu-id="48127-114">閉じた場合は、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ウィンドウでの Visual Studio プロジェクトを開く"には」の手順に従ってください[手順 2: 在庫要求スキーマの作成](../core/step-2-create-the-inventory-request-schema.md)を開きます。</span><span class="sxs-lookup"><span data-stu-id="48127-114">If you have closed the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] window, follow the procedure “To open the Visual Studio project” in [Step 2: Create the Inventory Request Schema](../core/step-2-create-the-inventory-request-schema.md) to open it.</span></span>  
  
#### <a name="to-add-another-project-to-your-solution"></a><span data-ttu-id="48127-115">ソリューションに別のプロジェクトを追加するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="48127-115">To add another project to your solution</span></span>  
  
1.  <span data-ttu-id="48127-116">Visual Studio からの**ファイル**メニューで、**追加**、順にクリックします**新しいプロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="48127-116">From Visual Studio, on the **File** menu, point to **Add**, and then click **New Project**.</span></span>  
  
2.  <span data-ttu-id="48127-117">**新しいプロジェクト** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="48127-117">In the **New Project** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="48127-118">プロパティ</span><span class="sxs-lookup"><span data-stu-id="48127-118">Use this</span></span>|<span data-ttu-id="48127-119">目的</span><span class="sxs-lookup"><span data-stu-id="48127-119">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="48127-120">**インストール済みテンプレート**</span><span class="sxs-lookup"><span data-stu-id="48127-120">**Installed Templates**</span></span>|<span data-ttu-id="48127-121">クリックして**BizTalk プロジェクト**、 をクリックし、**空の BizTalk Server プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="48127-121">Click **BizTalk Projects**, and then click **Empty BizTalk Server Project**.</span></span>|  
    |<span data-ttu-id="48127-122">**名前**</span><span class="sxs-lookup"><span data-stu-id="48127-122">**Name**</span></span>|<span data-ttu-id="48127-123">「`EAIOrchestration`.</span><span class="sxs-lookup"><span data-stu-id="48127-123">Type `EAIOrchestration`.</span></span>|  
    |<span data-ttu-id="48127-124">**場所**</span><span class="sxs-lookup"><span data-stu-id="48127-124">**Location**</span></span>|<span data-ttu-id="48127-125">「`C:\BTSTutorials\EAISolution`.</span><span class="sxs-lookup"><span data-stu-id="48127-125">Type `C:\BTSTutorials\EAISolution`.</span></span>|  
  
3.  <span data-ttu-id="48127-126">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="48127-126">Click **OK**.</span></span>  
  
#### <a name="to-add-an-orchestration"></a><span data-ttu-id="48127-127">オーケストレーションを追加するには</span><span class="sxs-lookup"><span data-stu-id="48127-127">To add an orchestration</span></span>  
  
1.  <span data-ttu-id="48127-128">ソリューション エクスプ ローラーで右クリック**EAIOrchestration**、 をポイント**追加**、 をクリックし、**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="48127-128">In Solution Explorer, right-click **EAIOrchestration**, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="48127-129">**新しい項目の追加 - EAIOrchestration**  ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="48127-129">In the **Add New Item - EAIOrchestration** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="48127-130">プロパティ</span><span class="sxs-lookup"><span data-stu-id="48127-130">Use this</span></span>|<span data-ttu-id="48127-131">目的</span><span class="sxs-lookup"><span data-stu-id="48127-131">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="48127-132">**インストール済みテンプレート**</span><span class="sxs-lookup"><span data-stu-id="48127-132">**Installed Templates**</span></span>|<span data-ttu-id="48127-133">クリックして**オーケストレーション ファイル**、 をクリックし、 **BizTalk オーケストレーション**します。</span><span class="sxs-lookup"><span data-stu-id="48127-133">Click **Orchestration Files**, and then click **BizTalk Orchestration**.</span></span>|  
    |<span data-ttu-id="48127-134">**名前**</span><span class="sxs-lookup"><span data-stu-id="48127-134">**Name**</span></span>|<span data-ttu-id="48127-135">型**EAIProcess.odx**します。</span><span class="sxs-lookup"><span data-stu-id="48127-135">Type **EAIProcess.odx**.</span></span>|  
  
3.  <span data-ttu-id="48127-136">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="48127-136">Click **Add**.</span></span>  
  
     <span data-ttu-id="48127-137">オーケストレーション デザイナーが開きます。</span><span class="sxs-lookup"><span data-stu-id="48127-137">Orchestration Designer opens.</span></span> <span data-ttu-id="48127-138">オーケストレーション デザイナーに EAIProcess オーケストレーションが表示されている状態を次に示します。</span><span class="sxs-lookup"><span data-stu-id="48127-138">The following figure shows Orchestration Designer with the EAIProcess orchestration.</span></span>  
  
     <span data-ttu-id="48127-139">![新しいオーケストレーション](../core/media/tut1-eaiprocess.gif "Tut1_EAIProcess")</span><span class="sxs-lookup"><span data-stu-id="48127-139">![New orchestration](../core/media/tut1-eaiprocess.gif "Tut1_EAIProcess")</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="48127-140">でしただけ何か。</span><span class="sxs-lookup"><span data-stu-id="48127-140">What did I just do?</span></span>  
 <span data-ttu-id="48127-141">この手順では、EAI ソリューションに 2 番目のプロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="48127-141">In this step, you added a second project to the EAI solution.</span></span> <span data-ttu-id="48127-142">新しいプロジェクトにオーケストレーションを追加しました。</span><span class="sxs-lookup"><span data-stu-id="48127-142">Then you added an orchestration to the new project.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="48127-143">次の手順</span><span class="sxs-lookup"><span data-stu-id="48127-143">Next Steps</span></span>  
 <span data-ttu-id="48127-144">ビジネス プロセスを定義した[手順 2: ビジネス プロセスの定義](../core/step-2-define-the-business-process.md)します。</span><span class="sxs-lookup"><span data-stu-id="48127-144">You define the business process in [Step 2: Define the Business Process](../core/step-2-define-the-business-process.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48127-145">参照</span><span class="sxs-lookup"><span data-stu-id="48127-145">See Also</span></span>  
 <span data-ttu-id="48127-146">[手順 2: ビジネス プロセスを定義します。](../core/step-2-define-the-business-process.md) </span><span class="sxs-lookup"><span data-stu-id="48127-146">[Step 2: Define the Business Process](../core/step-2-define-the-business-process.md) </span></span>  
 <span data-ttu-id="48127-147">[手順 3: オーケストレーションのポートを追加します。](../core/step-3-add-ports-to-the-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="48127-147">[Step 3: Add Ports to the Orchestration](../core/step-3-add-ports-to-the-orchestration.md) </span></span>  
 [<span data-ttu-id="48127-148">手順 4: EAIOrchestration プロジェクトのビルド</span><span class="sxs-lookup"><span data-stu-id="48127-148">Step 4: Build the EAIOrchestration Project</span></span>](../core/step-4-build-the-eaiorchestration-project.md)