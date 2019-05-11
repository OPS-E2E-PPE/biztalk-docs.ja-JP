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
ms.openlocfilehash: 084d24b5b1eb3e3a19ca7a8ee04af268a8f0a91c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395608"
---
# <a name="project-planning-recommendations-by-phase"></a><span data-ttu-id="8b012-102">フェーズごとのプロジェクト計画の推奨事項</span><span class="sxs-lookup"><span data-stu-id="8b012-102">Project Planning Recommendations by Phase</span></span>
<span data-ttu-id="8b012-103">今日、それぞれ独自の方法、利点、および制限事項とのソフトウェア開発ライフ サイクル モデルを数多くあります。</span><span class="sxs-lookup"><span data-stu-id="8b012-103">There are a number of software development lifecycle models in existence today, each with their own approaches, benefits, and limitations.</span></span> <span data-ttu-id="8b012-104">このセクションの目的が正常に適切に計画する際に役立つ推奨事項のセットを提供する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]開発プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="8b012-104">The goal of this section is to provide a set of recommendations that will help you plan appropriately for a successful [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] development project.</span></span>  
  
 <span data-ttu-id="8b012-105">このセクションでは、Microsoft の幅広く採用されているライフ サイクル モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="8b012-105">In this section, we use the lifecycle model employed broadly at Microsoft.</span></span> <span data-ttu-id="8b012-106">このモデルは、ウォーター フォールのライフ サイクル モデルとの反復的な組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="8b012-106">This model is a combination of iterative and waterfall lifecycle models.</span></span>  
  
 <span data-ttu-id="8b012-107">このモデルでは、境界が一連のプロジェクトのマイルス トーンを定義する 5 つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="8b012-107">In this model, there are five phases whose boundaries define a sequential set of milestones for the project.</span></span> <span data-ttu-id="8b012-108">実行の順序で、各フェーズは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8b012-108">The phases, in order of execution, are as follows:</span></span>  
  
- <span data-ttu-id="8b012-109">**要件**します。</span><span class="sxs-lookup"><span data-stu-id="8b012-109">**Requirements**.</span></span> <span data-ttu-id="8b012-110">ユーザー要件は、ビルドされる内容を定義する機能仕様に取り込まれます。</span><span class="sxs-lookup"><span data-stu-id="8b012-110">User requirements are captured in functional specifications that define what is to be built.</span></span>  
  
- <span data-ttu-id="8b012-111">**デザイン**します。</span><span class="sxs-lookup"><span data-stu-id="8b012-111">**Design**.</span></span> <span data-ttu-id="8b012-112">機能の要件に基づき、物理設計仕様を作成し、設計のアイデアを確認し、プラットフォームの機能を調査するプロトタイピングが行わします。</span><span class="sxs-lookup"><span data-stu-id="8b012-112">Based on the functional requirements, physical design specifications are created and prototyping is conducted to verify design ideas and investigate platform capabilities.</span></span>  
  
- <span data-ttu-id="8b012-113">**実装**します。</span><span class="sxs-lookup"><span data-stu-id="8b012-113">**Implementation**.</span></span> <span data-ttu-id="8b012-114">デザインと機能仕様を使用して、ソフトウェアのコーディングは行われます。</span><span class="sxs-lookup"><span data-stu-id="8b012-114">Using the design and functional specifications, the software coding is done.</span></span>  
  
- <span data-ttu-id="8b012-115">**検証**です。</span><span class="sxs-lookup"><span data-stu-id="8b012-115">**Verification**.</span></span> <span data-ttu-id="8b012-116">これは、仕様に従って実行されることを確認するソフトウェアのテストのプロセスです。</span><span class="sxs-lookup"><span data-stu-id="8b012-116">This is the process of testing the software to verify that it performs according to the specifications.</span></span>  
  
- <span data-ttu-id="8b012-117">**リリース**します。</span><span class="sxs-lookup"><span data-stu-id="8b012-117">**Release**.</span></span> <span data-ttu-id="8b012-118">ソフトウェアが完全に検証された後まとめられ、ユーザーにリリース用に準備します。</span><span class="sxs-lookup"><span data-stu-id="8b012-118">After the software has been fully verified, it is packed and prepared for release to users.</span></span>  
  
  <span data-ttu-id="8b012-119">次の図は、このプロジェクトの計画サイクルを示します。</span><span class="sxs-lookup"><span data-stu-id="8b012-119">The following figure shows this project planning cycle.</span></span>  
  
  <span data-ttu-id="8b012-120">![フェーズごとの計画に関する推奨事項をプロジェクト](../core/media/planningbyphase.gif "PlanningByPhase")</span><span class="sxs-lookup"><span data-stu-id="8b012-120">![Project Planning Recommendations by Phase](../core/media/planningbyphase.gif "PlanningByPhase")</span></span>  
  
  <span data-ttu-id="8b012-121">ほとんどは、これらのフェーズの期間が重複し、通常のサブフェーズがある場合。</span><span class="sxs-lookup"><span data-stu-id="8b012-121">Most, if not all, of these phases overlap in time and there are typically iterative sub-phases.</span></span> <span data-ttu-id="8b012-122">たとえば、製品の機能のサブセットの実装を完了するが一般的と検証が次のサブの実装の機能の設定中に、そのサブセットの開始を受けています。</span><span class="sxs-lookup"><span data-stu-id="8b012-122">For example, it is common to complete implementation of a sub-set of the product features and for verification to begin on that subset while implementation of the next sub set of features is under way.</span></span> <span data-ttu-id="8b012-123">そのため、このセクションでは、推奨事項は、特定のフェーズに関連付けられた、という意図が並列で実行できないことを意味するものでなくではなく、推奨事項する必要がありますを考慮して、相対的な順序の一部を把握するには計画します。</span><span class="sxs-lookup"><span data-stu-id="8b012-123">Therefore, while the recommendations in this section are associated with certain phases, the intention is not to imply that they cannot happen in parallel, but rather to give some idea of the relative order that the recommendations should be considered and factored into planning.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8b012-124">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8b012-124">In This Section</span></span>  
  
-   [<span data-ttu-id="8b012-125">要件フェーズの推奨事項</span><span class="sxs-lookup"><span data-stu-id="8b012-125">Requirements Phase Recommendations</span></span>](../core/requirements-phase-recommendations.md)  
  
-   [<span data-ttu-id="8b012-126">設計フェーズの推奨事項</span><span class="sxs-lookup"><span data-stu-id="8b012-126">Design Phase Recommendations</span></span>](../core/design-phase-recommendations.md)  
  
-   [<span data-ttu-id="8b012-127">実装フェーズの推奨事項</span><span class="sxs-lookup"><span data-stu-id="8b012-127">Implementation Phase Recommendations</span></span>](../core/implementation-phase-recommendations.md)  
  
-   [<span data-ttu-id="8b012-128">検証フェーズの推奨事項</span><span class="sxs-lookup"><span data-stu-id="8b012-128">Verification Phase Recommendations</span></span>](../core/verification-phase-recommendations.md)  
  
-   [<span data-ttu-id="8b012-129">リリース フェーズの推奨事項</span><span class="sxs-lookup"><span data-stu-id="8b012-129">Release Phase Recommendations</span></span>](../core/release-phase-recommendations.md)