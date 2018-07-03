---
title: パフォーマンス評価の段階 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 120706f9-9fa1-4f41-bd89-3b9eada940ad
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: abcf4bc5778d78d550184a8365e4d3775c3a15ba
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023032"
---
# <a name="phases-of-a-performance-assessment"></a><span data-ttu-id="dd32f-102">パフォーマンス評価のフェーズ</span><span class="sxs-lookup"><span data-stu-id="dd32f-102">Phases of a Performance Assessment</span></span>
<span data-ttu-id="dd32f-103">主な目標の 1 つ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]できるだけ多くの処理のシナリオに対応するために最大限の柔軟性を提供することです。</span><span class="sxs-lookup"><span data-stu-id="dd32f-103">One of the primary goals of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is to provide maximum flexibility for accommodating as many processing scenarios as possible.</span></span> <span data-ttu-id="dd32f-104">この柔軟性により機能の最適な使用で使用できるようにする方法を決定する BizTalk ソリューションの開発者が直面する主な課題の 1 つは[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ビジネスを満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd32f-104">Because of this great flexibility, one of the primary challenges facing developers of a BizTalk solution is to determine how to make best use of the features available in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to meet their business needs.</span></span> <span data-ttu-id="dd32f-105">このような柔軟性では、BizTalk Server ソリューションのパフォーマンスを最適化するときにという課題も伴います。</span><span class="sxs-lookup"><span data-stu-id="dd32f-105">This flexibility also poses a challenge when optimizing the performance of a BizTalk Server solution.</span></span>  
  
 <span data-ttu-id="dd32f-106">このセクションでは、BizTalk Server のパフォーマンス評価に関与して、BizTalk Server ソリューションのパフォーマンスを最適化するために使用する必要がある方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dd32f-106">This section describes the methodology that should be used to optimize the performance of a BizTalk Server solution by engaging in a BizTalk Server performance assessment.</span></span> <span data-ttu-id="dd32f-107">BizTalk Server のパフォーマンス評価は、特定の BizTalk Server ソリューションのパフォーマンスを最大化に使用されます。</span><span class="sxs-lookup"><span data-stu-id="dd32f-107">A BizTalk Server performance assessment is used to maximize the performance of a particular BizTalk Server solution.</span></span> <span data-ttu-id="dd32f-108">BizTalk Server パフォーマンスの評価から最大のメリットを得るためにパフォーマンス評価する必要があります、次 5 つ異なる手順/のフェーズに分割。</span><span class="sxs-lookup"><span data-stu-id="dd32f-108">In order to gain the maximum benefit from a BizTalk Server performance assessment, the performance assessment should be divided into the following five distinct steps/phases:</span></span>  
  
1. <span data-ttu-id="dd32f-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="dd32f-109">Scope</span></span>  
  
2. <span data-ttu-id="dd32f-110">プラン</span><span class="sxs-lookup"><span data-stu-id="dd32f-110">Plan</span></span>  
  
3. <span data-ttu-id="dd32f-111">準備</span><span class="sxs-lookup"><span data-stu-id="dd32f-111">Prepare</span></span>  
  
4. <span data-ttu-id="dd32f-112">ラボを構築します。</span><span class="sxs-lookup"><span data-stu-id="dd32f-112">Build lab</span></span>  
  
5. <span data-ttu-id="dd32f-113">Execute</span><span class="sxs-lookup"><span data-stu-id="dd32f-113">Execute</span></span>  
  
   <span data-ttu-id="dd32f-114">ここでは、これらの各フェーズで詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="dd32f-114">This topic describes each of these phases in greater detail.</span></span>  
  
   <span data-ttu-id="dd32f-115">![パフォーマンス評価プロセスのフェーズ](../technical-guides/media/assessmentprocess.gif "AssessmentProcess")</span><span class="sxs-lookup"><span data-stu-id="dd32f-115">![Phases of a performance assessment process](../technical-guides/media/assessmentprocess.gif "AssessmentProcess")</span></span>  
   <span data-ttu-id="dd32f-116">BizTalk Server のパフォーマンス評価のフェーズ</span><span class="sxs-lookup"><span data-stu-id="dd32f-116">Phases of a BizTalk Server performance assessment</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dd32f-117">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="dd32f-117">In This Section</span></span>  
  
-   <span data-ttu-id="dd32f-118">[フェーズ 1: 評価のスコープ](../technical-guides/phase-1-scoping-the-assessment.md)-パフォーマンス評価のスコープを確立するときに従う必要がある手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="dd32f-118">[Phase 1: Scoping the Assessment](../technical-guides/phase-1-scoping-the-assessment.md) - Describes the steps that should be followed when establishing the scope of the performance assessment.</span></span>  
  
-   <span data-ttu-id="dd32f-119">[フェーズ 2: 評価の計画](../technical-guides/phase-2-planning-the-assessment.md)– ソリューションのマイルス トーンのタイムラインを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dd32f-119">[Phase 2: Planning the Assessment](../technical-guides/phase-2-planning-the-assessment.md) – Describes how to create a solution milestones timeline.</span></span> <span data-ttu-id="dd32f-120">これは、ソリューションのテストに期待される目標を満たす必要があります明確に文書をマスター計画として使用されます。</span><span class="sxs-lookup"><span data-stu-id="dd32f-120">This is used as a master plan to clearly document when expected goals for the testing of the solution should be met.</span></span>  
  
-   <span data-ttu-id="dd32f-121">[フェーズ 3: が評価の準備](../technical-guides/phase-3-preparing-for-the-assessment.md)– ソリューションの詳細なアーキテクチャ図と、ソリューションによって使用されるハードウェア構成の特定の側面を提供する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dd32f-121">[Phase 3: Preparing for the Assessment](../technical-guides/phase-3-preparing-for-the-assessment.md) – Describes how to provide a detailed architectural diagram of the solution and specific aspects of the hardware configuration used by the solution.</span></span>  
  
-   <span data-ttu-id="dd32f-122">[フェーズ 4: 評価環境の構築](../technical-guides/phase-4-building-the-assessment-environment.md)– ハードウェアと以前に確立されたソリューション プラットフォームの詳細な設計に従ってアプリケーションのインストールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="dd32f-122">[Phase 4: Building the Assessment Environment](../technical-guides/phase-4-building-the-assessment-environment.md) – Describes installation of hardware and applications according to the detailed design of the solution platform that was established previously.</span></span>  
  
-   <span data-ttu-id="dd32f-123">[フェーズ 5: 評価の実行](../technical-guides/phase-5-executing-the-assessment.md)– 自動化されたロード テストと検出して、ソリューション内の任意のボトルネックを解消する方法を使用してパフォーマンス データを生成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dd32f-123">[Phase 5: Executing the Assessment](../technical-guides/phase-5-executing-the-assessment.md) – Provides information about generating performance data via automated load testing and how to detect and eliminate any bottlenecks in the solution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd32f-124">参照</span><span class="sxs-lookup"><span data-stu-id="dd32f-124">See Also</span></span>  
 [<span data-ttu-id="dd32f-125">BizTalk Server のパフォーマンス テスト手法</span><span class="sxs-lookup"><span data-stu-id="dd32f-125">BizTalk Server Performance Testing Methodology</span></span>](../technical-guides/biztalk-server-performance-testing-methodology.md)