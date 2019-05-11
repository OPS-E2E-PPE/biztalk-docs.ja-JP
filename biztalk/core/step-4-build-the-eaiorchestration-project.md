---
title: 手順 4:EAIOrchestration プロジェクトのビルド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 66e4b161-c5ac-404c-9ee5-4c0322fc40f3
caps.latest.revision: 34
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7c380d5aa68daeb6f7f05ca0846c00f1999b976
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392633"
---
# <a name="step-4-build-the-eaiorchestration-project"></a><span data-ttu-id="8b068-102">手順 4:EAIOrchestration プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="8b068-102">Step 4: Build the EAIOrchestration Project</span></span>
<span data-ttu-id="8b068-103">![手順 4 の 4](../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span><span class="sxs-lookup"><span data-stu-id="8b068-103">![Step 4 of 4](../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span></span>  
  
 <span data-ttu-id="8b068-104">**所要時間:** 5 分</span><span class="sxs-lookup"><span data-stu-id="8b068-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="8b068-105">**目標:** この手順では、EAIOrchestration プロジェクトをアセンブリにコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="8b068-105">**Objective:** In this step, you compile the EAIOrchestration project into an assembly.</span></span>  
  
 <span data-ttu-id="8b068-106">**目的:** BizTalk Server では、.NET アセンブリにコンパイルするすべての成果物が必要です。</span><span class="sxs-lookup"><span data-stu-id="8b068-106">**Purpose:** BizTalk Server requires all the artifacts to be compiled into .NET assemblies.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8b068-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="8b068-107">Prerequisites</span></span>  
 <span data-ttu-id="8b068-108">このステップを開始する前に、以下の要件を確認してください。</span><span class="sxs-lookup"><span data-stu-id="8b068-108">Note the following requirements before you begin this step:</span></span>  
  
-   <span data-ttu-id="8b068-109">この手順を開始する前に、次の手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b068-109">Before you begin this step you must complete the following steps:</span></span>  
  
    -   [<span data-ttu-id="8b068-110">ステップ 1: EAIOrchestration プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="8b068-110">Step 1: Add EAIOrchestration Project to the Solution</span></span>](../core/step-1-add-eaiorchestration-project-to-the-solution.md)  
  
    -   [<span data-ttu-id="8b068-111">手順 2:ビジネス プロセスを定義します。</span><span class="sxs-lookup"><span data-stu-id="8b068-111">Step 2: Define the Business Process</span></span>](../core/step-2-define-the-business-process.md)  
  
    -   [<span data-ttu-id="8b068-112">ステップ 3:ポートをオーケストレーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="8b068-112">Step 3: Add Ports to the Orchestration</span></span>](../core/step-3-add-ports-to-the-orchestration.md)  
  
## <a name="procedures"></a><span data-ttu-id="8b068-113">手順</span><span class="sxs-lookup"><span data-stu-id="8b068-113">Procedures</span></span>  
  
#### <a name="to-build-the-eaiorchestration-project"></a><span data-ttu-id="8b068-114">EAIOrchestration プロジェクトをビルドするには</span><span class="sxs-lookup"><span data-stu-id="8b068-114">To build the EAIOrchestration project</span></span>  
  
-   <span data-ttu-id="8b068-115">ソリューション エクスプ ローラーで右クリックして**EAIOrchestration**、 をクリックし、**ビルド**します。</span><span class="sxs-lookup"><span data-stu-id="8b068-115">In Solution Explorer, right-click **EAIOrchestration**, and then click **Build**.</span></span>  
  
     <span data-ttu-id="8b068-116">画面の下部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="8b068-116">The bottom of the screen should display:</span></span>  
  
    ```  
    ========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==========  
    ```  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="8b068-117">でしただけ何か。</span><span class="sxs-lookup"><span data-stu-id="8b068-117">What did I just do?</span></span>  
 <span data-ttu-id="8b068-118">この手順では、EAIOrchestration プロジェクトをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="8b068-118">In this step, you compiled the EAIOrchestration project.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8b068-119">次のステップ</span><span class="sxs-lookup"><span data-stu-id="8b068-119">Next steps</span></span>  
 <span data-ttu-id="8b068-120">では、EAISolution ソリューションをデプロイする[レッスン 3。ソリューションの配置](../core/lesson-3-deploy-the-solution.md)します。</span><span class="sxs-lookup"><span data-stu-id="8b068-120">You deploy the EAISolution solution in [Lesson 3: Deploy the Solution](../core/lesson-3-deploy-the-solution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b068-121">参照</span><span class="sxs-lookup"><span data-stu-id="8b068-121">See Also</span></span>  
 <span data-ttu-id="8b068-122">[ステップ 1: EAIOrchestration プロジェクトをソリューションに追加します。](../core/step-1-add-eaiorchestration-project-to-the-solution.md) </span><span class="sxs-lookup"><span data-stu-id="8b068-122">[Step 1: Add EAIOrchestration Project to the Solution](../core/step-1-add-eaiorchestration-project-to-the-solution.md) </span></span>  
 <span data-ttu-id="8b068-123">[手順 2:ビジネス プロセスを定義します。](../core/step-2-define-the-business-process.md) </span><span class="sxs-lookup"><span data-stu-id="8b068-123">[Step 2: Define the Business Process](../core/step-2-define-the-business-process.md) </span></span>  
 [<span data-ttu-id="8b068-124">ステップ 3:ポートをオーケストレーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="8b068-124">Step 3: Add Ports to the Orchestration</span></span>](../core/step-3-add-ports-to-the-orchestration.md)