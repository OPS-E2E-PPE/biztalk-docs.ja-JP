---
title: '手順 1: EAISchemas プロジェクトの作成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a14ee61-fa27-4f03-997e-42c34a77afee
caps.latest.revision: 55
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb51c936edfcc20009048abcb90bb8ead72fd11c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974459"
---
# <a name="step-1-create-eaischemas-project"></a><span data-ttu-id="57d9e-102">ステップ 1: EAISchemas プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="57d9e-102">Step 1: Create EAISchemas Project</span></span>
<span data-ttu-id="57d9e-103">![手順 5 の 1](../core/media/step-1of5.gif "Step_1of5")</span><span class="sxs-lookup"><span data-stu-id="57d9e-103">![Step 1 of 5](../core/media/step-1of5.gif "Step_1of5")</span></span>  

 <span data-ttu-id="57d9e-104">**所要時間:** 5 分</span><span class="sxs-lookup"><span data-stu-id="57d9e-104">**Time to complete:** 5 minutes</span></span>  

 <span data-ttu-id="57d9e-105">**目標:** この手順で作成する新しい[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューションとプロジェクト。</span><span class="sxs-lookup"><span data-stu-id="57d9e-105">**Objective:** In this step, you create a new [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] solution and a project.</span></span>  

 <span data-ttu-id="57d9e-106">**目的:** の一部またはすべてを作成する BizTalk プロジェクト システムを使用して、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]アプリケーションやビジネス ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="57d9e-106">**Purpose:** You use the BizTalk project system to create part or all of a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] application or business solution.</span></span> <span data-ttu-id="57d9e-107">ソリューションの中核となる要素は、スキーマ、オーケストレーション、Web メッセージの種類、クラス、パイプライン、マップ、参照などの項目の集合である BizTalk プロジェクトです。ユーザーは、これらの項目をビルドしてアセンブリを生成し、生成したアセンブリを展開します。</span><span class="sxs-lookup"><span data-stu-id="57d9e-107">The core element of any such solution is a BizTalk project—a collection of items, such as schemas, orchestrations, Web message types, classes, pipelines, maps, and references that you can build and generate into an assembly before deploying it.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="57d9e-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="57d9e-108">Prerequisites</span></span>  
 <span data-ttu-id="57d9e-109">このステップを開始する前に、以下の要件を確認してください。</span><span class="sxs-lookup"><span data-stu-id="57d9e-109">Note the following requirements before you begin this step:</span></span>  

-   <span data-ttu-id="57d9e-110">この手順を開始する前に、手順を完了する必要があります[チュートリアルを開始する前に](../core/before-you-begin-the-tutorial.md)します。</span><span class="sxs-lookup"><span data-stu-id="57d9e-110">Before you begin this step you must complete the steps in [Before You Begin the Tutorial](../core/before-you-begin-the-tutorial.md).</span></span>  

## <a name="procedures"></a><span data-ttu-id="57d9e-111">手順</span><span class="sxs-lookup"><span data-stu-id="57d9e-111">Procedures</span></span>  

#### <a name="to-create-a-new-visual-studio-solutionproject"></a><span data-ttu-id="57d9e-112">Visual Studio の新しいソリューションとプロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="57d9e-112">To create a new Visual Studio solution/project</span></span>  

1. <span data-ttu-id="57d9e-113">開始**Microsoft Visual Studio**します。</span><span class="sxs-lookup"><span data-stu-id="57d9e-113">Start **Microsoft Visual Studio**.</span></span>  

2. <span data-ttu-id="57d9e-114">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], の **ファイル** メニューをポイント **新規**, 、クリックして **プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="57d9e-114">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  

3. <span data-ttu-id="57d9e-115">**新しいプロジェクト** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="57d9e-115">In the **New Project** dialog box, do the following:</span></span>  


   |             <span data-ttu-id="57d9e-116">プロパティ</span><span class="sxs-lookup"><span data-stu-id="57d9e-116">Use this</span></span>              |                                <span data-ttu-id="57d9e-117">目的</span><span class="sxs-lookup"><span data-stu-id="57d9e-117">To do this</span></span>                                |
   |-----------------------------------|--------------------------------------------------------------------------|
   |      <span data-ttu-id="57d9e-118">**インストール済みテンプレート**</span><span class="sxs-lookup"><span data-stu-id="57d9e-118">**Installed Templates**</span></span>      | <span data-ttu-id="57d9e-119">クリックして**BizTalk プロジェクト**、 をクリックし、**空の BizTalk Server プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="57d9e-119">Click **BizTalk Projects**, then click **Empty BizTalk Server Project**.</span></span> |
   |             <span data-ttu-id="57d9e-120">**名前**</span><span class="sxs-lookup"><span data-stu-id="57d9e-120">**Name**</span></span>              |                           <span data-ttu-id="57d9e-121">型**EAISchemas**します。</span><span class="sxs-lookup"><span data-stu-id="57d9e-121">Type **EAISchemas**.</span></span>                           |
   |           <span data-ttu-id="57d9e-122">**場所**</span><span class="sxs-lookup"><span data-stu-id="57d9e-122">**Location**</span></span>            |                      <span data-ttu-id="57d9e-123">型**C:\tutorial\Lessons**します。</span><span class="sxs-lookup"><span data-stu-id="57d9e-123">Type **C:\tutorial\Lessons**.</span></span>                       |
   |         <span data-ttu-id="57d9e-124">**[ソリューション名]**</span><span class="sxs-lookup"><span data-stu-id="57d9e-124">**Solution Name**</span></span>         |                          <span data-ttu-id="57d9e-125">型**EAISolution**します。</span><span class="sxs-lookup"><span data-stu-id="57d9e-125">Type **EAISolution**.</span></span>                           |
   | <span data-ttu-id="57d9e-126">**ソリューションのディレクトリを作成します。**</span><span class="sxs-lookup"><span data-stu-id="57d9e-126">**Create directory for solution**</span></span> |                                <span data-ttu-id="57d9e-127">(選択)</span><span class="sxs-lookup"><span data-stu-id="57d9e-127">(selected)</span></span>                                |


4. <span data-ttu-id="57d9e-128">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="57d9e-128">Click **OK**.</span></span>  

5. <span data-ttu-id="57d9e-129">**[ファイル]** メニューの **[すべてを保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="57d9e-129">On the **File** menu, click **Save All**.</span></span>  

## <a name="what-did-i-just-do"></a><span data-ttu-id="57d9e-130">でしただけ何か。</span><span class="sxs-lookup"><span data-stu-id="57d9e-130">What did I just do?</span></span>  
 <span data-ttu-id="57d9e-131">このステップでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で、新しいプロジェクトと [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ソリューションを開きました。</span><span class="sxs-lookup"><span data-stu-id="57d9e-131">In this step, you opened a new project and a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  

## <a name="next-steps"></a><span data-ttu-id="57d9e-132">次の手順</span><span class="sxs-lookup"><span data-stu-id="57d9e-132">Next Steps</span></span>  
 <span data-ttu-id="57d9e-133">在庫補充要求メッセージ用スキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="57d9e-133">You create the schema for the inventory replenishment request message.</span></span>  

## <a name="see-also"></a><span data-ttu-id="57d9e-134">参照</span><span class="sxs-lookup"><span data-stu-id="57d9e-134">See Also</span></span>  
 <span data-ttu-id="57d9e-135">[このチュートリアルを開始する前に](../core/before-you-begin-the-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="57d9e-135">[Before You Begin the Tutorial](../core/before-you-begin-the-tutorial.md) </span></span>  
 <span data-ttu-id="57d9e-136">[手順 2: 在庫要求スキーマを作成します。](../core/step-2-create-the-inventory-request-schema.md) </span><span class="sxs-lookup"><span data-stu-id="57d9e-136">[Step 2: Create the Inventory Request Schema](../core/step-2-create-the-inventory-request-schema.md) </span></span>  
 <span data-ttu-id="57d9e-137">[手順 3: 要求拒否スキーマを作成します。](../core/step-3-create-the-request-decline-schema.md) </span><span class="sxs-lookup"><span data-stu-id="57d9e-137">[Step 3: Create the Request Decline Schema](../core/step-3-create-the-request-decline-schema.md) </span></span>  
 <span data-ttu-id="57d9e-138">[手順 4: マップを作成します。](../core/step-4-create-the-map.md) </span><span class="sxs-lookup"><span data-stu-id="57d9e-138">[Step 4: Create the Map](../core/step-4-create-the-map.md) </span></span>  
 <span data-ttu-id="57d9e-139">[手順 5: EAISchemas プロジェクトをビルドします。](../core/step-5-build-the-eaischemas-project.md) </span><span class="sxs-lookup"><span data-stu-id="57d9e-139">[Step 5: Build the EAISchemas Project](../core/step-5-build-the-eaischemas-project.md) </span></span>  
 <span data-ttu-id="57d9e-140">[開発者ツール](../core/developer-tools.md) </span><span class="sxs-lookup"><span data-stu-id="57d9e-140">[Developer Tools](../core/developer-tools.md) </span></span>  
 [<span data-ttu-id="57d9e-141">BizTalk プロジェクトの操作</span><span class="sxs-lookup"><span data-stu-id="57d9e-141">Working with BizTalk Projects</span></span>](../core/working-with-biztalk-projects.md)