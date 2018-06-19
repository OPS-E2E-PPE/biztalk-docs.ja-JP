---
title: 'フェーズ 4: 評価環境を構築 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3b90d7c5-60ca-4a81-b3d9-6d4e9d91e684
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88fa45a17e1475aee989f22d2f8d1ef0d015a9ce
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008675"
---
# <a name="phase-4-building-the-assessment-environment"></a><span data-ttu-id="eeb7e-102">フェーズ 4: 評価環境を構築します。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-102">Phase 4: Building the Assessment Environment</span></span>
<span data-ttu-id="eeb7e-103">パフォーマンス評価のビルド ラボの段階を使用して、前のフェーズで行われた設計に関する決定事項への準拠のハードウェアとソフトウェア環境をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-103">The Build lab phase of a performance assessment is used to install the hardware and software for the environment in conformance to the design decisions made in previous phases.</span></span> <span data-ttu-id="eeb7e-104">ビルド ラボ フェーズできますが、時間がかかるために、このフェーズの以前のフェーズを重複に通常とは異なるはできません。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-104">Because the Build lab phase can be time consuming, it is not unusual for this phase to overlap earlier phases.</span></span> <span data-ttu-id="eeb7e-105">多くのシナリオで、アプリケーションのアーキテクチャに関する最終的な判断が行わ前に、ハードウェアとオペレーティング システムをインストールすることがあります。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-105">In many scenarios, the hardware and operating system may be installed before a final decision has been made as to the application architecture.</span></span> <span data-ttu-id="eeb7e-106">パフォーマンス評価のビルド ラボの段階には、通常、このトピックで説明したタスクが含まれます。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-106">The Build lab phase of a performance assessment typically includes the tasks discussed in this topic.</span></span>  
  
## <a name="obtain-all-build-lab-infrastructure-at-least-a-week-in-advance-of-the-lab-start-date"></a><span data-ttu-id="eeb7e-107">すべてのビルド ラボ インフラストラクチャ ラボの開始日を前もってお客様には、少なくとも 1 週間の取得します。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-107">Obtain all build-lab infrastructure at least a week in advance of the lab start date</span></span>  
 <span data-ttu-id="eeb7e-108">少なくとも週に、ラボの開始日前に、必要なハードウェアとソフトウェアの使用可能なすべてがあることを計画します。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-108">Plan to have available all of the required hardware and software at least a week before the lab start date.</span></span> <span data-ttu-id="eeb7e-109">貴重なラボの時間が必要なインフラストラクチャの浪費しないようになります。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-109">This will ensure that valuable lab time is not wasted for want of the required infrastructure.</span></span>  
  
## <a name="configure-third-party-software-systems"></a><span data-ttu-id="eeb7e-110">サード パーティ製ソフトウェア システムを構成します。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-110">Configure third-party software systems</span></span>  
 <span data-ttu-id="eeb7e-111">サードパーティ製システムを構築して、ラボを開始する前に構成する必要がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-111">There may be third-party systems that need to be built out and configured before the lab can begin.</span></span> <span data-ttu-id="eeb7e-112">領域の専門家該当がこれらのシステムに必要な場合は、ビルド出力とラボ実行段階でスケジュールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-112">If subject matter experts (SMEs) are required for these systems, be sure they are scheduled during the build-out and lab execution stages.</span></span> <span data-ttu-id="eeb7e-113">完全に文書化するの構築する手順を確認します。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-113">Ensure that they thoroughly document their build-out procedures.</span></span>  
  
## <a name="install-and-configure-the-biztalk-server-environment"></a><span data-ttu-id="eeb7e-114">インストールして、BizTalk Server 環境を構成します。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-114">Install and configure the BizTalk Server environment</span></span>  
 <span data-ttu-id="eeb7e-115">BizTalk Server と必要な依存関係のソフトウェアをインストールするための詳細な手順については、[インストールおよびアップグレード ガイド](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)です。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-115">Detailed instructions for installing BizTalk Server and the required dependency software are in the [Installation and Upgrade Guides](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span></span> <span data-ttu-id="eeb7e-116">正常にインストールし、BizTalk Server 環境を構成した後、次のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-116">After successfully installing and configuring the BizTalk Server environment, complete the following tasks:</span></span>  
  
-   <span data-ttu-id="eeb7e-117">推奨事項に従う、[運用の準備のチェックリスト](operational-readiness-checklists.md)</span><span class="sxs-lookup"><span data-stu-id="eeb7e-117">Follow the recommendations listed in the [Operational Readiness Checklists](operational-readiness-checklists.md)</span></span>
  
-   <span data-ttu-id="eeb7e-118">推奨事項に従い[のパフォーマンスの最適化](../technical-guides/optimizing-performance.md)です。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-118">Follow the recommendations in [Optimizing Performance](../technical-guides/optimizing-performance.md).</span></span>  
  
-   <span data-ttu-id="eeb7e-119">すべてのコンピューターの時刻が正しく同期されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-119">Ensure all computer times are properly synchronized.</span></span>  
  
-   <span data-ttu-id="eeb7e-120">環境内のすべてのコンピューター間で MSDTC 機能を確認します。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-120">Verify MSDTC functionality between all computers in the environment.</span></span>  
  
-   <span data-ttu-id="eeb7e-121">本当に必要な場合を除き、任意のカスタムのトレース/ログが無効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-121">Ensure any custom tracing/logging is disabled unless absolutely needed.</span></span>  
  
-   <span data-ttu-id="eeb7e-122">ロード テストのための Visual Studio Ultimate edition をインストールします。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-122">Install the Visual Studio Ultimate edition for load testing.</span></span>  <span data-ttu-id="eeb7e-123">Visual Studio を使用して自動テストを実行する方法に関する詳細については、次を参照してください。[自動テストを容易にするために Visual Studio を使用して](../technical-guides/using-visual-studio-to-facilitate-automated-testing.md)です。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-123">For more information about how to perform automated testing using Visual Studio, see [Using Visual Studio to Facilitate Automated Testing](../technical-guides/using-visual-studio-to-facilitate-automated-testing.md).</span></span>  
  
-   <span data-ttu-id="eeb7e-124">必要に応じて、パフォーマンス モニター カウンターおよびログをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-124">Setup Performance Monitor counters and logs, as needed.</span></span>  
  
-   <span data-ttu-id="eeb7e-125">デバッグ コードの変更が、パフォーマンスの評価のスコープ内にある場合は、ソリューションをデバッグするコンピューターをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-125">Setup a debugging computer to debug the solution if code changes are within the scope of the performance assessment.</span></span>  
  
-   <span data-ttu-id="eeb7e-126">すべてのハード ドライブの断片化を解消します。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-126">Defragment all hard drives.</span></span>  
  
-   <span data-ttu-id="eeb7e-127">ウイルス対策のリアルタイム スキャンを無効にします。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-127">Disable antivirus real time scanning.</span></span>  
  
-   <span data-ttu-id="eeb7e-128">エンタープライズ シングル サインオン マスター シークレットをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-128">Back up the Enterprise Single Sign-On Master Secret.</span></span>  
  
## <a name="install-the-biztalk-server-application-to-be-tested"></a><span data-ttu-id="eeb7e-129">テストする BizTalk Server アプリケーションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-129">Install the BizTalk Server application to be tested</span></span>  
 <span data-ttu-id="eeb7e-130">テストするアプリケーションのインストールには、通常、次の手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-130">Installation of the application to be tested will typically include the following steps:</span></span>  
  
1.  <span data-ttu-id="eeb7e-131">BizTalk Server 管理コンソールを使用して、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-131">Use the BizTalk Server Administration console to do the following:</span></span>  
  
    -   <span data-ttu-id="eeb7e-132">ホストを作成します。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-132">Create Hosts</span></span>  
  
    -   <span data-ttu-id="eeb7e-133">送信/受信ハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-133">Create Send/Receive Handlers.</span></span>  
  
    -   <span data-ttu-id="eeb7e-134">ホスト インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-134">Create Host instances.</span></span>  
  
    -   <span data-ttu-id="eeb7e-135">BizTalk Server アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-135">Create BizTalk Server Applications.</span></span>  
  
2.  <span data-ttu-id="eeb7e-136">アプリケーションのインストール:</span><span class="sxs-lookup"><span data-stu-id="eeb7e-136">Application installation:</span></span>  
  
    1.  <span data-ttu-id="eeb7e-137">BizTalk Server グループを BizTalk Server のバイナリを展開します。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-137">Deploy BizTalk Server binaries to the BizTalk Server group.</span></span>  
  
    2.  <span data-ttu-id="eeb7e-138">BizTalk Server グループにバインドをインポートします。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-138">Import bindings to the BizTalk Server group.</span></span>  
  
    3.  <span data-ttu-id="eeb7e-139">すべてのボックスで GAC の BizTalk Server と BizTalk Server 以外のバイナリです。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-139">GAC BizTalk Server and non-BizTalk Server binaries on all boxes.</span></span>  
  
    4.  <span data-ttu-id="eeb7e-140">依存関係コンポーネントのすべてのボックスに存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-140">Ensure dependency components exist on all boxes.</span></span>  
  
3.  <span data-ttu-id="eeb7e-141">依存アプリケーションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-141">Install dependency applications.</span></span>  
  
4.  <span data-ttu-id="eeb7e-142">BizTalk Server 管理コンソールで、トランスポートと物理エンドポイントを構成します。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-142">Configure transports and physical endpoints in the BizTalk Server Administration console.</span></span>  
  
5.  <span data-ttu-id="eeb7e-143">サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-143">Start services.</span></span>  
  
6.  <span data-ttu-id="eeb7e-144">基本的なスモーク テストの実行 – スモーク テストは、ソリューションの基本機能をテストするエンド ツー エンド機能テストします。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-144">Perform basic smoke tests – Smoke tests are end-to-end functional tests that test the basic functionality of your solution.</span></span>  
  
## <a name="implement-automated-build-and-load-testing"></a><span data-ttu-id="eeb7e-145">自動ビルドを実装し、ロード テスト</span><span class="sxs-lookup"><span data-stu-id="eeb7e-145">Implement automated build and load testing</span></span>  
 <span data-ttu-id="eeb7e-146">自動ビルドおよび負荷テスト プロセスの実装は、BizTalk Server のパフォーマンス評価のにとって重要ではほぼ間違いないです。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-146">Implementation of an automated build and load testing process is arguably the cornerstone of a BizTalk Server performance assessment.</span></span> <span data-ttu-id="eeb7e-147">コードの変更が、パフォーマンスの評価のスコープ内にある場合は、自動ビルド プロセスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-147">An automated build process should be implemented if code changes are within the scope of the performance assessment.</span></span> <span data-ttu-id="eeb7e-148">すべてのロード テスト シナリオの自動化されたロード テストを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-148">Automated load testing should be implemented for all load testing scenarios.</span></span> <span data-ttu-id="eeb7e-149">自動ビルドを実装して、ロード テストに必要な初期投資が削減すばやく、オートメーションはヒューマン エラーされる日常的なビルドまたはテストのタスクの繰り返しの高速かつ正確に対応します。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-149">The initial time investment required to implement automated build and load testing is quickly recouped, automation accommodates rapid and precise repetition of mundane build/testing tasks that are subject to human error.</span></span> <span data-ttu-id="eeb7e-150">自動ビルドを実装して、プロセスのテストに関する詳細については、次を参照してください。[自動テストを実装する](../technical-guides/implementing-automated-testing.md)このガイドでします。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-150">For more information about implementing an automated build and testing process, see [Implementing Automated Testing](../technical-guides/implementing-automated-testing.md) in this guide.</span></span>  
  
## <a name="configure-performance-monitoring"></a><span data-ttu-id="eeb7e-151">パフォーマンスの監視を構成します。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-151">Configure performance monitoring</span></span>  
 <span data-ttu-id="eeb7e-152">正確なパフォーマンスの監視は、パフォーマンスの評価の成功に不可欠です。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-152">Accurate performance monitoring is critical to the success of the performance assessment.</span></span> <span data-ttu-id="eeb7e-153">スコープ フェーズで定義されたスループットと待機時間の目標値に基づいてパフォーマンス メトリックを評価するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-153">Determine which performance metrics should be evaluated based on the throughput and latency goals that were defined in the Scope phase.</span></span> <span data-ttu-id="eeb7e-154">パフォーマンスの監視は、BizTalk Server 環境の各コンピューターで実行してください。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-154">Performance monitoring should be performed on each computer in the BizTalk Server environment.</span></span> <span data-ttu-id="eeb7e-155">参照してください[パフォーマンス カウンター](../core/performance-counters.md)です。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-155">See [Performance Counters](../core/performance-counters.md).</span></span> <span data-ttu-id="eeb7e-156">ログのパフォーマンス分析ツール (PAL) を使用すると、視覚的に重要なパフォーマンス カウンターをグラフおよびこれらのカウンターのしきい値を超えた場合にアラートが生成される HTML レポートを生成できます。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-156">Use the Performance Analysis of Logs tool (PAL) to generate HTML reports that graphically chart important performance counters and generate alerts when thresholds for these counters are exceeded.</span></span> <span data-ttu-id="eeb7e-157">S[パフォーマンス分析のログ (PAL) ツール](https://github.com/clinthuffman/PAL)です。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-157">S [Performance Analysis of Logs (PAL) tool](https://github.com/clinthuffman/PAL).</span></span>  
  
## <a name="establish-and-document-the-solutions-baseline-performance"></a><span data-ttu-id="eeb7e-158">確立して、ソリューションのベースライン パフォーマンスを文書化</span><span class="sxs-lookup"><span data-stu-id="eeb7e-158">Establish and document the solution’s baseline performance</span></span>  
 <span data-ttu-id="eeb7e-159">パフォーマンス評価中に適用されるパフォーマンスの最適化の効果を測定することができるように、パフォーマンスの基準値を計算する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eeb7e-159">Baseline performance should be calculated so that the effect of performance optimizations applied during the performance assessment can be measured.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeb7e-160">参照</span><span class="sxs-lookup"><span data-stu-id="eeb7e-160">See Also</span></span>  
 [<span data-ttu-id="eeb7e-161">パフォーマンス評価のフェーズ</span><span class="sxs-lookup"><span data-stu-id="eeb7e-161">Phases of a Performance Assessment</span></span>](../technical-guides/phases-of-a-performance-assessment.md)