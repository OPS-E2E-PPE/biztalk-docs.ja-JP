---
title: 手順 5:EAISchemas プロジェクトのビルド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c20cd368-7446-4861-8d71-5bc25ce408a2
caps.latest.revision: 41
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b82d7b4d322464cb873e47e0e15e57c6f68f51d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244304"
---
# <a name="step-5-build-the-eaischemas-project"></a><span data-ttu-id="f5e27-102">手順 5:EAISchemas プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="f5e27-102">Step 5: Build the EAISchemas Project</span></span>
<span data-ttu-id="f5e27-103">![手順 5 の 5](../core/media/step-5of5.gif "Step_5of5")</span><span class="sxs-lookup"><span data-stu-id="f5e27-103">![Step 5 of 5](../core/media/step-5of5.gif "Step_5of5")</span></span>  
  
 <span data-ttu-id="f5e27-104">**所要時間:** 6 分</span><span class="sxs-lookup"><span data-stu-id="f5e27-104">**Time to complete:** 6 minutes</span></span>  
  
 <span data-ttu-id="f5e27-105">**目標:** この手順では、EAISchemas プロジェクトをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="f5e27-105">**Objective:** In this step, you compile the EAISchemas project.</span></span>  
  
 <span data-ttu-id="f5e27-106">**目的:** Microsoft BizTalk Server と .NET Framework の最も重要な側面はすべての BizTalk Server アイテムです。マップやスキーマ、オーケストレーション、パイプライン、.NET アセンブリにコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="f5e27-106">**Purpose:** The most important aspect of Microsoft BizTalk Server and the .NET Framework is that all BizTalk Server artifacts; maps, schemas, orchestrations, and pipelines, get compiled into .NET assemblies.</span></span> <span data-ttu-id="f5e27-107">この設計の 2 つの最も重要な意味は、これらのアセンブリが厳密な名前は、必要し、そのため、それらも .NET のバージョン管理の規則に従うことです。</span><span class="sxs-lookup"><span data-stu-id="f5e27-107">The two most important implications of this design are that these assemblies must have strong names, and because of that, they also follow .NET versioning rules.</span></span> <span data-ttu-id="f5e27-108">これの主な影響は、別の .NET プロジェクトまたはアセンブリ (BizTalk プロジェクトを含む) の特定のバージョンに対して構築されると、BizTalk プロジェクトは、そのバージョンを使用して、新しいバージョンに対して再構築されるまでは引き続きです。</span><span class="sxs-lookup"><span data-stu-id="f5e27-108">The main implication of this is that a BizTalk project, once built against a particular version of another .NET project or assembly (including BizTalk projects), continues to use that version until it has been rebuilt against a newer version.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f5e27-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="f5e27-109">Prerequisites</span></span>  
 <span data-ttu-id="f5e27-110">このステップを開始する前に、以下の要件を確認してください。</span><span class="sxs-lookup"><span data-stu-id="f5e27-110">Note the following requirements before you begin this step:</span></span>  
  
-   <span data-ttu-id="f5e27-111">この手順を開始する前に、次の手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5e27-111">Before you begin this step you must complete the following steps:</span></span>  
  
    -   [<span data-ttu-id="f5e27-112">ステップ 1: EAISchemas プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="f5e27-112">Step 1: Create EAISchemas Project</span></span>](../core/step-1-create-eaischemas-project.md)  
  
    -   [<span data-ttu-id="f5e27-113">手順 2:在庫要求スキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="f5e27-113">Step 2: Create the Inventory Request Schema</span></span>](../core/step-2-create-the-inventory-request-schema.md) 
  
    -   [<span data-ttu-id="f5e27-114">ステップ 3:要求拒否スキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="f5e27-114">Step 3: Create the Request Decline Schema</span></span>](../core/step-3-create-the-request-decline-schema.md)  
  
    -   [<span data-ttu-id="f5e27-115">手順 4:マップを作成します。</span><span class="sxs-lookup"><span data-stu-id="f5e27-115">Step 4: Create the Map</span></span>](../core/step-4-create-the-map.md)  
  
## <a name="procedures"></a><span data-ttu-id="f5e27-116">手順</span><span class="sxs-lookup"><span data-stu-id="f5e27-116">Procedures</span></span>  
  
#### <a name="to-build-the-eaischemas-project"></a><span data-ttu-id="f5e27-117">EAISchemas プロジェクトをビルドするには</span><span class="sxs-lookup"><span data-stu-id="f5e27-117">To build the EAISchemas project</span></span>  
  
1.  <span data-ttu-id="f5e27-118">ソリューション エクスプ ローラーで右クリックして**EAISchemas**、 をクリックし、**ビルド**します。</span><span class="sxs-lookup"><span data-stu-id="f5e27-118">In Solution Explorer, right-click **EAISchemas**, and then click **Build**.</span></span>  
  
     <span data-ttu-id="f5e27-119">画面の下部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f5e27-119">The bottom of the screen should display:</span></span>  
  
    ```  
    ========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==========  
    ```  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="f5e27-120">でしただけ何か。</span><span class="sxs-lookup"><span data-stu-id="f5e27-120">What did I just do?</span></span>  
 <span data-ttu-id="f5e27-121">この手順では、アセンブリ ファイル (DLL) を生成する EAISchemas プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="f5e27-121">In this step, you built the EAISchemas project to generate an assembly file (DLL).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f5e27-122">次の手順</span><span class="sxs-lookup"><span data-stu-id="f5e27-122">Next Steps</span></span>  
 <span data-ttu-id="f5e27-123">承認条件は、在庫補充要求メッセージの内容を評価するビジネス プロセスを作成する[レッスン 2。ビジネス プロセスの定義](../core/lesson-2-define-the-business-process.md)します。</span><span class="sxs-lookup"><span data-stu-id="f5e27-123">You create the business process that evaluates the contents of the inventory replenishment request message against approval criteria in [Lesson 2: Define the Business Process](../core/lesson-2-define-the-business-process.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5e27-124">参照</span><span class="sxs-lookup"><span data-stu-id="f5e27-124">See Also</span></span>  
 <span data-ttu-id="f5e27-125">[ステップ 1: EAISchemas プロジェクトを作成します。](../core/step-1-create-eaischemas-project.md) </span><span class="sxs-lookup"><span data-stu-id="f5e27-125">[Step 1: Create EAISchemas Project](../core/step-1-create-eaischemas-project.md) </span></span>  
 <span data-ttu-id="f5e27-126">[手順 2:在庫要求スキーマを作成します。](../core/step-2-create-the-inventory-request-schema.md) </span><span class="sxs-lookup"><span data-stu-id="f5e27-126">[Step 2: Create the Inventory Request Schema](../core/step-2-create-the-inventory-request-schema.md) </span></span>  
 <span data-ttu-id="f5e27-127">[ステップ 3:要求拒否スキーマを作成します。](../core/step-3-create-the-request-decline-schema.md) </span><span class="sxs-lookup"><span data-stu-id="f5e27-127">[Step 3: Create the Request Decline Schema](../core/step-3-create-the-request-decline-schema.md) </span></span>  
 [<span data-ttu-id="f5e27-128">手順 4:マップを作成します。</span><span class="sxs-lookup"><span data-stu-id="f5e27-128">Step 4: Create the Map</span></span>](../core/step-4-create-the-map.md)