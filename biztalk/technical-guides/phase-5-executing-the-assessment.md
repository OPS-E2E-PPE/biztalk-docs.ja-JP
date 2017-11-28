---
title: "フェーズ 5: 評価の実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d40fc64-b6cb-448b-8ea1-a6ad7302ab8b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fba6d49d8d69276af4282ad0a941ee1fc4d8068
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="phase-5-executing-the-assessment"></a><span data-ttu-id="b3bab-102">評価の実行フェーズ 5。</span><span class="sxs-lookup"><span data-stu-id="b3bab-102">Phase 5: Executing the Assessment</span></span>
<span data-ttu-id="b3bab-103">実行フェーズは、自動化されたロード テストでと、パフォーマンスのボトルネックが検出され、アドレス指定されるパフォーマンス データが生成される場所です。</span><span class="sxs-lookup"><span data-stu-id="b3bab-103">The Execute phase is where the performance data is generated through automated load testing and where performance bottlenecks are discovered and addressed.</span></span> <span data-ttu-id="b3bab-104">このフェーズがパフォーマンスのボトルネックを削減または削除して、テストをそれにより、反復処理のパフォーマンスの評価、最適化、およびテストをもう一度です。</span><span class="sxs-lookup"><span data-stu-id="b3bab-104">This phase has an iterative process whereby performance bottlenecks are reduced or eliminated by testing, evaluating performance, optimizing, and testing again.</span></span>  
  
 <span data-ttu-id="b3bab-105">このトピックでは、BizTalk Server のパフォーマンス評価の実行フェーズ中に続き、通常の手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="b3bab-105">This topic describes the steps that are typically followed during the Execute phase of a BizTalk Server performance assessment:</span></span>  
  
## <a name="step-1-run-automated-tests"></a><span data-ttu-id="b3bab-106">手順 1: 自動テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="b3bab-106">Step 1: Run automated tests</span></span>  
 <span data-ttu-id="b3bab-107">自動テストを実行して、実行フェーズを開始します。</span><span class="sxs-lookup"><span data-stu-id="b3bab-107">Begin the Execute phase by running automated tests.</span></span> <span data-ttu-id="b3bab-108">BizTalk Server のパフォーマンス評価は通常スループットや待機時間がテストの重点を置いていますが、ビルドの検証および機能テストに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b3bab-108">A BizTalk Server performance assessment typically focuses on throughput and/or latency testing but may include build verification and functional tests.</span></span> <span data-ttu-id="b3bab-109">自動テストの実行に関する包括的な情報は、次を参照してください。[自動テストを実装する](../technical-guides/implementing-automated-testing.md)です。</span><span class="sxs-lookup"><span data-stu-id="b3bab-109">For comprehensive information about running automated testing, see [Implementing Automated Testing](../technical-guides/implementing-automated-testing.md).</span></span>  
  
## <a name="step-2-document-and-evaluate-test-results"></a><span data-ttu-id="b3bab-110">手順 2: を文書化し、テスト結果を評価</span><span class="sxs-lookup"><span data-stu-id="b3bab-110">Step 2: Document and evaluate test results</span></span>  
 <span data-ttu-id="b3bab-111">各テストの最後に、十分にテスト結果を文書化し、示されたパフォーマンス目標が満たされているかどうかを評価します。</span><span class="sxs-lookup"><span data-stu-id="b3bab-111">At the conclusion of each test, thoroughly document the test results and evaluate whether the stated performance goals have been met.</span></span>  
  
## <a name="step-3-modify-the-configuration-of-biztalk-server-third-party-systems-or-solution-artifacts-to-tune-for-performance-based-on-the-test-results"></a><span data-ttu-id="b3bab-112">手順 3: テストの結果に基づいて、パフォーマンスをチューニングするには、BizTalk Server、サード パーティ製システム、またはソリューションの成果物の構成を変更します。</span><span class="sxs-lookup"><span data-stu-id="b3bab-112">Step 3: Modify the configuration of BizTalk Server, third-party systems, or solution artifacts to tune for performance based on the test results</span></span>  
 <span data-ttu-id="b3bab-113">提示されたスループットや待機時間の目標を達成するのに環境を最適化するのに方法に関する意思決定を行うには、テスト結果を使用します。</span><span class="sxs-lookup"><span data-stu-id="b3bab-113">Use the test results to make decisions about how to optimize the environment to reach stated throughput or latency goals.</span></span>  
  
## <a name="step-4-record-all-changes-made-to-the-environment"></a><span data-ttu-id="b3bab-114">手順 4: が環境に加えられたすべての変更を記録します。</span><span class="sxs-lookup"><span data-stu-id="b3bab-114">Step 4: Record all changes made to the environment</span></span>  
 <span data-ttu-id="b3bab-115">環境に加えられた変更が十分に記載されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b3bab-115">Ensure that any changes made to the environment are thoroughly documented.</span></span> <span data-ttu-id="b3bab-116">変更のレコードを簡単に実稼働環境の変更を適用することが、場合に、変更を元に戻してに対応する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3bab-116">A record of the changes will allow you to easily apply the changes in the production environment and will accommodate the undoing of changes if need be.</span></span>  
  
## <a name="step-5-repeat-this-cycle-until-goals-are-achieved"></a><span data-ttu-id="b3bab-117">手順 5: の目標を達成するまでこのサイクルを繰り返す</span><span class="sxs-lookup"><span data-stu-id="b3bab-117">Step 5: Repeat this cycle until goals are achieved</span></span>  
 <span data-ttu-id="b3bab-118">テスト、評価し結果を文書化、環境の最適化、目的のパフォーマンス目標に到達するまでに、環境に対する変更を文書化のサイクルを続行します。</span><span class="sxs-lookup"><span data-stu-id="b3bab-118">Continue the cycle of testing, evaluating and documenting results, optimizing the environment, and documenting changes to the environment until the desired performance goals are reached.</span></span>  
  
## <a name="step-6-summarize-test-results-at-the-end-of-each-day"></a><span data-ttu-id="b3bab-119">手順 6: 集計、毎日の最後のテスト結果</span><span class="sxs-lookup"><span data-stu-id="b3bab-119">Step 6: Summarize test results at the end of each day</span></span>  
 <span data-ttu-id="b3bab-120">毎日の最後に進行状況、テスト結果の「概要」を完了します。</span><span class="sxs-lookup"><span data-stu-id="b3bab-120">Complete an “executive summary” of the test results and progress made at the end of each day.</span></span> <span data-ttu-id="b3bab-121">概要を含む電子メールをコンパイルし、パフォーマンスの評価対象のすべての関係者に送信して行われている進行状況の通知を受け取ります足並みをします。</span><span class="sxs-lookup"><span data-stu-id="b3bab-121">Compile an e-mail that contains the summary, and send to all stakeholders in the performance assessment to keep everyone informed of progress that is being made.</span></span>  
  
## <a name="step-7-update-the-project-plan-as-timeline-goals-are-met"></a><span data-ttu-id="b3bab-122">手順 7: 目標の達成タイムラインとプロジェクト計画を更新します。</span><span class="sxs-lookup"><span data-stu-id="b3bab-122">Step 7: Update the project plan as timeline goals are met</span></span>  
 <span data-ttu-id="b3bab-123">計画フェーズで開発されたタイムラインは、パフォーマンスの評価の全体的な進行状況を適切な参照です。</span><span class="sxs-lookup"><span data-stu-id="b3bab-123">The timeline developed in the Plan phase is a good reference for the overall progress of the performance assessment.</span></span> <span data-ttu-id="b3bab-124">進行状況をすべての利害関係者に通信するために必要に応じて、このタイムラインを更新します。</span><span class="sxs-lookup"><span data-stu-id="b3bab-124">Update this timeline as necessary to communicate the progress to all stakeholders.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3bab-125">参照</span><span class="sxs-lookup"><span data-stu-id="b3bab-125">See Also</span></span>  
 [<span data-ttu-id="b3bab-126">パフォーマンス評価の段階</span><span class="sxs-lookup"><span data-stu-id="b3bab-126">Phases of a Performance Assessment</span></span>](../technical-guides/phases-of-a-performance-assessment.md)