---
title: フェーズごとのプロジェクト計画の推奨事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- planning, performance
- performance, planning
ms.assetid: 422f05e3-5ad4-4f47-9be3-c229a20a6ef3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70c938b8f72114b71bd5dece7c7c97ffc4df0158
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008107"
---
# <a name="project-planning-recommendations-by-phase"></a><span data-ttu-id="e32d4-102">フェーズごとのプロジェクト計画の推奨事項</span><span class="sxs-lookup"><span data-stu-id="e32d4-102">Project Planning Recommendations by Phase</span></span>
<span data-ttu-id="e32d4-103">今日、それぞれ独自の方法、利点、および制限を備えた多くのソフトウェア開発のライフサイクル モデルがあります。</span><span class="sxs-lookup"><span data-stu-id="e32d4-103">There are a number of software development lifecycle models in existence today, each with their own approaches, benefits, and limitations.</span></span> <span data-ttu-id="e32d4-104">このセクションの目的は、適切な [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 開発プロジェクトに応じた計画をサポートする一連の推奨事項について説明することです。</span><span class="sxs-lookup"><span data-stu-id="e32d4-104">The goal of this section is to provide a set of recommendations that will help you plan appropriately for a successful [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] development project.</span></span>  
  
 <span data-ttu-id="e32d4-105">このセクションでは、マイクロソフトで幅広く採用されているライフサイクル モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="e32d4-105">In this section, we use the lifecycle model employed broadly at Microsoft.</span></span> <span data-ttu-id="e32d4-106">このモデルでは、繰り返し型とウォーターフォール型のライフサイクル モデルを組み合わせています。</span><span class="sxs-lookup"><span data-stu-id="e32d4-106">This model is a combination of iterative and waterfall lifecycle models.</span></span>  
  
 <span data-ttu-id="e32d4-107">このモデルには 5 つのフェーズがあり、フェーズの境界がプロジェクトの一連のマイルストーンになります。</span><span class="sxs-lookup"><span data-stu-id="e32d4-107">In this model, there are five phases whose boundaries define a sequential set of milestones for the project.</span></span> <span data-ttu-id="e32d4-108">フェーズを実行順に次に示します。</span><span class="sxs-lookup"><span data-stu-id="e32d4-108">The phases, in order of execution, are as follows:</span></span>  
  
- <span data-ttu-id="e32d4-109">**要件**します。</span><span class="sxs-lookup"><span data-stu-id="e32d4-109">**Requirements**.</span></span> <span data-ttu-id="e32d4-110">ユーザー要件は、構築される内容を定義する機能仕様に取り込まれます。</span><span class="sxs-lookup"><span data-stu-id="e32d4-110">User requirements are captured in functional specifications that define what is to be built.</span></span>  
  
- <span data-ttu-id="e32d4-111">**デザイン**します。</span><span class="sxs-lookup"><span data-stu-id="e32d4-111">**Design**.</span></span> <span data-ttu-id="e32d4-112">また、プロトタイピングが行われ、設計のアイデアが確認されてプラットフォーム機能が調査されます。</span><span class="sxs-lookup"><span data-stu-id="e32d4-112">Based on the functional requirements, physical design specifications are created and prototyping is conducted to verify design ideas and investigate platform capabilities.</span></span>  
  
- <span data-ttu-id="e32d4-113">**実装**します。</span><span class="sxs-lookup"><span data-stu-id="e32d4-113">**Implementation**.</span></span> <span data-ttu-id="e32d4-114">設計仕様と機能仕様を使用して、ソフトウェアのコーディングが実行されます。</span><span class="sxs-lookup"><span data-stu-id="e32d4-114">Using the design and functional specifications, the software coding is done.</span></span>  
  
- <span data-ttu-id="e32d4-115">**検証**です。</span><span class="sxs-lookup"><span data-stu-id="e32d4-115">**Verification**.</span></span> <span data-ttu-id="e32d4-116">このプロセスでは、ソフトウェアをテストして、仕様に従ってソフトウェアが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e32d4-116">This is the process of testing the software to verify that it performs according to the specifications.</span></span>  
  
- <span data-ttu-id="e32d4-117">**リリース**します。</span><span class="sxs-lookup"><span data-stu-id="e32d4-117">**Release**.</span></span> <span data-ttu-id="e32d4-118">ソフトウェアをすべて検証した後、ソフトウェアはまとめられ、一般リリースに備えられます。</span><span class="sxs-lookup"><span data-stu-id="e32d4-118">After the software has been fully verified, it is packed and prepared for release to users.</span></span>  
  
  <span data-ttu-id="e32d4-119">次の図は、このプロジェクトの計画サイクルを示しています。</span><span class="sxs-lookup"><span data-stu-id="e32d4-119">The following figure shows this project planning cycle.</span></span>  
  
  <span data-ttu-id="e32d4-120">![フェーズごとの計画に関する推奨事項をプロジェクト](../core/media/planningbyphase.gif "PlanningByPhase")</span><span class="sxs-lookup"><span data-stu-id="e32d4-120">![Project Planning Recommendations by Phase](../core/media/planningbyphase.gif "PlanningByPhase")</span></span>  
  
  <span data-ttu-id="e32d4-121">これらのフェーズのほとんど (すべてではない) は期間が重複し、通常、繰り返しのサブフェーズが存在します。</span><span class="sxs-lookup"><span data-stu-id="e32d4-121">Most, if not all, of these phases overlap in time and there are typically iterative sub-phases.</span></span> <span data-ttu-id="e32d4-122">たとえば、製品機能のサブセットの実装が完了し、そのサブセットの検証が開始されたときに、次のサブセットの実装作業が平行して進んでいるということは、よくあります。</span><span class="sxs-lookup"><span data-stu-id="e32d4-122">For example, it is common to complete implementation of a sub-set of the product features and for verification to begin on that subset while implementation of the next sub set of features is under way.</span></span> <span data-ttu-id="e32d4-123">このため、このセクションの推奨事項は特定のフェーズに関連していますが、これは平行してフェーズを実行できないという意味ではなく、推奨事項を考慮して計画に含めるときには相対的な順序が存在するということを示しているだけです。</span><span class="sxs-lookup"><span data-stu-id="e32d4-123">Therefore, while the recommendations in this section are associated with certain phases, the intention is not to imply that they cannot happen in parallel, but rather to give some idea of the relative order that the recommendations should be considered and factored into planning.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e32d4-124">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e32d4-124">In This Section</span></span>  
  
-   [<span data-ttu-id="e32d4-125">要件フェーズの推奨事項</span><span class="sxs-lookup"><span data-stu-id="e32d4-125">Requirements Phase Recommendations</span></span>](../core/requirements-phase-recommendations.md)  
  
-   [<span data-ttu-id="e32d4-126">設計フェーズの推奨事項</span><span class="sxs-lookup"><span data-stu-id="e32d4-126">Design Phase Recommendations</span></span>](../core/design-phase-recommendations.md)  
  
-   [<span data-ttu-id="e32d4-127">実装フェーズの推奨事項</span><span class="sxs-lookup"><span data-stu-id="e32d4-127">Implementation Phase Recommendations</span></span>](../core/implementation-phase-recommendations.md)  
  
-   [<span data-ttu-id="e32d4-128">検証フェーズの推奨事項</span><span class="sxs-lookup"><span data-stu-id="e32d4-128">Verification Phase Recommendations</span></span>](../core/verification-phase-recommendations.md)  
  
-   [<span data-ttu-id="e32d4-129">リリース フェーズの推奨事項</span><span class="sxs-lookup"><span data-stu-id="e32d4-129">Release Phase Recommendations</span></span>](../core/release-phase-recommendations.md)