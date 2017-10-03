---
title: "手順 5: EAISchemas プロジェクトのビルド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c20cd368-7446-4861-8d71-5bc25ce408a2
caps.latest.revision: "41"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 394d9df78f7064df8501ed43149bd26793533c47
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-5-build-the-eaischemas-project"></a><span data-ttu-id="01b7a-102">ステップ 5: EAISchemas プロジェクトのビルド</span><span class="sxs-lookup"><span data-stu-id="01b7a-102">Step 5: Build the EAISchemas Project</span></span>
<span data-ttu-id="01b7a-103">![手順 5 の 5](../core/media/step-5of5.gif "Step_5of5")</span><span class="sxs-lookup"><span data-stu-id="01b7a-103">![Step 5 of 5](../core/media/step-5of5.gif "Step_5of5")</span></span>  
  
 <span data-ttu-id="01b7a-104">**所要時間:** 6 分</span><span class="sxs-lookup"><span data-stu-id="01b7a-104">**Time to complete:** 6 minutes</span></span>  
  
 <span data-ttu-id="01b7a-105">**目標:**この手順では、EAISchemas プロジェクトをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="01b7a-105">**Objective:** In this step, you compile the EAISchemas project.</span></span>  
  
 <span data-ttu-id="01b7a-106">**目的:**を Microsoft BizTalk Server と .NET Framework の最も重要な点はすべての BizTalk Server アイテム、マップやスキーマ、オーケストレーション、パイプライン、.NET アセンブリにコンパイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="01b7a-106">**Purpose:** The most important aspect of Microsoft BizTalk Server and the .NET Framework is that all BizTalk Server artifacts; maps, schemas, orchestrations, and pipelines, get compiled into .NET assemblies.</span></span> <span data-ttu-id="01b7a-107">このしくみが意味するのは、これらのアセンブリに厳密な名前が必要であり、そのために .NET のバージョン管理規則にも従う必要が生じることです。</span><span class="sxs-lookup"><span data-stu-id="01b7a-107">The two most important implications of this design are that these assemblies must have strong names, and because of that, they also follow .NET versioning rules.</span></span> <span data-ttu-id="01b7a-108">結果として、BizTalk のプロジェクトは、別の .NET プロジェクトまたはアセンブリ (BizTalk プロジェクトを含む) の特定のバージョンに対して構築されると、新しいバージョンに対して再構築されるまではそのバージョンを使い続けることになります。</span><span class="sxs-lookup"><span data-stu-id="01b7a-108">The main implication of this is that a BizTalk project, once built against a particular version of another .NET project or assembly (including BizTalk projects), continues to use that version until it has been rebuilt against a newer version.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="01b7a-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="01b7a-109">Prerequisites</span></span>  
 <span data-ttu-id="01b7a-110">このステップを開始する前に、以下の要件を確認してください。</span><span class="sxs-lookup"><span data-stu-id="01b7a-110">Note the following requirements before you begin this step:</span></span>  
  
-   <span data-ttu-id="01b7a-111">このステップを開始する前に、次のステップを完了しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="01b7a-111">Before you begin this step you must complete the following steps:</span></span>  
  
    -   [<span data-ttu-id="01b7a-112">手順 1: EAISchemas プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="01b7a-112">Step 1: Create EAISchemas Project</span></span>](../core/step-1-create-eaischemas-project.md)  
  
    -   [<span data-ttu-id="01b7a-113">手順 2: 在庫要求スキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="01b7a-113">Step 2: Create the Inventory Request Schema</span></span>](../core/step-2-create-the-inventory-request-schema.md) 
  
    -   [<span data-ttu-id="01b7a-114">手順 3: 要求拒否スキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="01b7a-114">Step 3: Create the Request Decline Schema</span></span>](../core/step-3-create-the-request-decline-schema.md)  
  
    -   [<span data-ttu-id="01b7a-115">手順 4: マップを作成します。</span><span class="sxs-lookup"><span data-stu-id="01b7a-115">Step 4: Create the Map</span></span>](../core/step-4-create-the-map.md)  
  
## <a name="procedures"></a><span data-ttu-id="01b7a-116">手順</span><span class="sxs-lookup"><span data-stu-id="01b7a-116">Procedures</span></span>  
  
#### <a name="to-build-the-eaischemas-project"></a><span data-ttu-id="01b7a-117">EAISchemas プロジェクトをビルドするには</span><span class="sxs-lookup"><span data-stu-id="01b7a-117">To build the EAISchemas project</span></span>  
  
1.  <span data-ttu-id="01b7a-118">ソリューション エクスプ ローラーで右クリック**EAISchemas**、クリックして**ビルド**です。</span><span class="sxs-lookup"><span data-stu-id="01b7a-118">In Solution Explorer, right-click **EAISchemas**, and then click **Build**.</span></span>  
  
     <span data-ttu-id="01b7a-119">画面の下部に、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="01b7a-119">The bottom of the screen should display:</span></span>  
  
    ```  
    ========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==========  
    ```  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="01b7a-120">でしただけは何ですか。</span><span class="sxs-lookup"><span data-stu-id="01b7a-120">What did I just do?</span></span>  
 <span data-ttu-id="01b7a-121">このステップでは、EAISchemas プロジェクトをビルドし、アセンブリ ファイル (DLL) を生成しました。</span><span class="sxs-lookup"><span data-stu-id="01b7a-121">In this step, you built the EAISchemas project to generate an assembly file (DLL).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="01b7a-122">次の手順</span><span class="sxs-lookup"><span data-stu-id="01b7a-122">Next Steps</span></span>  
 <span data-ttu-id="01b7a-123">承認条件を満たすには、在庫補充要求メッセージの内容を評価するビジネス プロセスを作成する[レッスン 2: ビジネス プロセスの定義](../core/lesson-2-define-the-business-process.md)です。</span><span class="sxs-lookup"><span data-stu-id="01b7a-123">You create the business process that evaluates the contents of the inventory replenishment request message against approval criteria in [Lesson 2: Define the Business Process](../core/lesson-2-define-the-business-process.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01b7a-124">参照</span><span class="sxs-lookup"><span data-stu-id="01b7a-124">See Also</span></span>  
 <span data-ttu-id="01b7a-125">[手順 1: EAISchemas プロジェクトを作成します。](../core/step-1-create-eaischemas-project.md) </span><span class="sxs-lookup"><span data-stu-id="01b7a-125">[Step 1: Create EAISchemas Project](../core/step-1-create-eaischemas-project.md) </span></span>  
 <span data-ttu-id="01b7a-126">[手順 2: 在庫要求スキーマを作成します。](../core/step-2-create-the-inventory-request-schema.md) </span><span class="sxs-lookup"><span data-stu-id="01b7a-126">[Step 2: Create the Inventory Request Schema](../core/step-2-create-the-inventory-request-schema.md) </span></span>  
 <span data-ttu-id="01b7a-127">[手順 3: 要求拒否スキーマを作成します。](../core/step-3-create-the-request-decline-schema.md) </span><span class="sxs-lookup"><span data-stu-id="01b7a-127">[Step 3: Create the Request Decline Schema](../core/step-3-create-the-request-decline-schema.md) </span></span>  
 [<span data-ttu-id="01b7a-128">手順 4: マップを作成します。</span><span class="sxs-lookup"><span data-stu-id="01b7a-128">Step 4: Create the Map</span></span>](../core/step-4-create-the-map.md)