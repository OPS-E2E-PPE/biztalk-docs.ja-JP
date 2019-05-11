---
title: フェーズ 5:評価の実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d40fc64-b6cb-448b-8ea1-a6ad7302ab8b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 332073502c1b2cc358e09ce7f50338321eb42bdf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393472"
---
# <a name="phase-5-executing-the-assessment"></a><span data-ttu-id="2988f-102">フェーズ 5:評価の実行</span><span class="sxs-lookup"><span data-stu-id="2988f-102">Phase 5: Executing the Assessment</span></span>
<span data-ttu-id="2988f-103">実行フェーズは、自動化されたロード テストと、パフォーマンスのボトルネックが検出され、アドレス指定にパフォーマンス データを生成する場所です。</span><span class="sxs-lookup"><span data-stu-id="2988f-103">The Execute phase is where the performance data is generated through automated load testing and where performance bottlenecks are discovered and addressed.</span></span> <span data-ttu-id="2988f-104">このフェーズがパフォーマンスのボトルネックを削減または削除して、テストをそれにより、反復的なプロセスのパフォーマンスの評価、最適化、そしてもう一度テストします。</span><span class="sxs-lookup"><span data-stu-id="2988f-104">This phase has an iterative process whereby performance bottlenecks are reduced or eliminated by testing, evaluating performance, optimizing, and testing again.</span></span>  
  
 <span data-ttu-id="2988f-105">このトピックでは、BizTalk Server のパフォーマンス評価の実行フェーズ中に従っている通常の手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="2988f-105">This topic describes the steps that are typically followed during the Execute phase of a BizTalk Server performance assessment:</span></span>  
  
## <a name="step-1-run-automated-tests"></a><span data-ttu-id="2988f-106">手順 1:自動テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="2988f-106">Step 1: Run automated tests</span></span>  
 <span data-ttu-id="2988f-107">実行フェーズを開始するには、自動テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="2988f-107">Begin the Execute phase by running automated tests.</span></span> <span data-ttu-id="2988f-108">BizTalk Server のパフォーマンス評価は通常スループットや待機時間のテストに重点を置いていますが、ビルドの検証および機能テストに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="2988f-108">A BizTalk Server performance assessment typically focuses on throughput and/or latency testing but may include build verification and functional tests.</span></span> <span data-ttu-id="2988f-109">自動テストの実行に関する包括的な情報を参照してください。[自動テストを実装する](../technical-guides/implementing-automated-testing.md)します。</span><span class="sxs-lookup"><span data-stu-id="2988f-109">For comprehensive information about running automated testing, see [Implementing Automated Testing](../technical-guides/implementing-automated-testing.md).</span></span>  
  
## <a name="step-2-document-and-evaluate-test-results"></a><span data-ttu-id="2988f-110">手順 2:文書化し、テスト結果を評価します。</span><span class="sxs-lookup"><span data-stu-id="2988f-110">Step 2: Document and evaluate test results</span></span>  
 <span data-ttu-id="2988f-111">各テストの最後には、十分にテスト結果を文書化し、規定されたパフォーマンスの目標を満たしているかどうかを評価します。</span><span class="sxs-lookup"><span data-stu-id="2988f-111">At the conclusion of each test, thoroughly document the test results and evaluate whether the stated performance goals have been met.</span></span>  
  
## <a name="step-3-modify-the-configuration-of-biztalk-server-third-party-systems-or-solution-artifacts-to-tune-for-performance-based-on-the-test-results"></a><span data-ttu-id="2988f-112">手順 3:テスト結果に基づいてパフォーマンスをチューニングするには、BizTalk Server、サード パーティ システム、またはソリューションの成果物の構成を変更します。</span><span class="sxs-lookup"><span data-stu-id="2988f-112">Step 3: Modify the configuration of BizTalk Server, third-party systems, or solution artifacts to tune for performance based on the test results</span></span>  
 <span data-ttu-id="2988f-113">環境を最適化するのに方法について説明したスループットや待機時間の目標に到達するのに決定を行うには、テスト結果を使用します。</span><span class="sxs-lookup"><span data-stu-id="2988f-113">Use the test results to make decisions about how to optimize the environment to reach stated throughput or latency goals.</span></span>  
  
## <a name="step-4-record-all-changes-made-to-the-environment"></a><span data-ttu-id="2988f-114">手順 4:環境に加えられたすべての変更を記録します。</span><span class="sxs-lookup"><span data-stu-id="2988f-114">Step 4: Record all changes made to the environment</span></span>  
 <span data-ttu-id="2988f-115">環境に加えられた変更が十分に記載されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2988f-115">Ensure that any changes made to the environment are thoroughly documented.</span></span> <span data-ttu-id="2988f-116">変更のレコードは簡単に実稼働環境の変更を適用することし、場合、変更の取り消しを可能になる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2988f-116">A record of the changes will allow you to easily apply the changes in the production environment and will accommodate the undoing of changes if need be.</span></span>  
  
## <a name="step-5-repeat-this-cycle-until-goals-are-achieved"></a><span data-ttu-id="2988f-117">手順 5:目標を達成するまでこのサイクルを繰り返します</span><span class="sxs-lookup"><span data-stu-id="2988f-117">Step 5: Repeat this cycle until goals are achieved</span></span>  
 <span data-ttu-id="2988f-118">テスト、評価、結果を文書化し、環境を最適化する、目的のパフォーマンス目標に達するまでは、環境への変更を文書化、サイクルを続行します。</span><span class="sxs-lookup"><span data-stu-id="2988f-118">Continue the cycle of testing, evaluating and documenting results, optimizing the environment, and documenting changes to the environment until the desired performance goals are reached.</span></span>  
  
## <a name="step-6-summarize-test-results-at-the-end-of-each-day"></a><span data-ttu-id="2988f-119">手順 6:1 日の最後にテスト結果を要約します。</span><span class="sxs-lookup"><span data-stu-id="2988f-119">Step 6: Summarize test results at the end of each day</span></span>  
 <span data-ttu-id="2988f-120">1 日の最後に進行状況、テスト結果の「概要」を完了します。</span><span class="sxs-lookup"><span data-stu-id="2988f-120">Complete an “executive summary” of the test results and progress made at the end of each day.</span></span> <span data-ttu-id="2988f-121">概要を含む電子メールをコンパイルし、全員が行われているの進行状況の通知が常にパフォーマンスの評価ですべての利害関係者に送信します。</span><span class="sxs-lookup"><span data-stu-id="2988f-121">Compile an e-mail that contains the summary, and send to all stakeholders in the performance assessment to keep everyone informed of progress that is being made.</span></span>  
  
## <a name="step-7-update-the-project-plan-as-timeline-goals-are-met"></a><span data-ttu-id="2988f-122">手順 7:タイムラインの目標を満たしていると、プロジェクト計画を更新します。</span><span class="sxs-lookup"><span data-stu-id="2988f-122">Step 7: Update the project plan as timeline goals are met</span></span>  
 <span data-ttu-id="2988f-123">計画フェーズで開発されたタイムラインは、パフォーマンス評価の全体的な進行状況の適切な参照です。</span><span class="sxs-lookup"><span data-stu-id="2988f-123">The timeline developed in the Plan phase is a good reference for the overall progress of the performance assessment.</span></span> <span data-ttu-id="2988f-124">進行状況をすべての関係者に通信するために必要に応じて、このタイムラインを更新します。</span><span class="sxs-lookup"><span data-stu-id="2988f-124">Update this timeline as necessary to communicate the progress to all stakeholders.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2988f-125">参照</span><span class="sxs-lookup"><span data-stu-id="2988f-125">See Also</span></span>  
 [<span data-ttu-id="2988f-126">パフォーマンス評価のフェーズ</span><span class="sxs-lookup"><span data-stu-id="2988f-126">Phases of a Performance Assessment</span></span>](../technical-guides/phases-of-a-performance-assessment.md)