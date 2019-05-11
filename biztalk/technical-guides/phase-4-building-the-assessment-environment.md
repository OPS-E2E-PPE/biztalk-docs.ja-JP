---
title: フェーズ 4:評価環境の構築 |Microsoft Docs
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
ms.openlocfilehash: d1b9829591af749f5e253cc7873af4ab114af542
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65249650"
---
# <a name="phase-4-building-the-assessment-environment"></a><span data-ttu-id="b7ee3-102">フェーズ 4:評価環境を構築します。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-102">Phase 4: Building the Assessment Environment</span></span>
<span data-ttu-id="b7ee3-103">パフォーマンス評価のビルド ラボの段階を使用して、前のフェーズで行われた設計の決定に準拠して、ハードウェアとソフトウェア環境をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-103">The Build lab phase of a performance assessment is used to install the hardware and software for the environment in conformance to the design decisions made in previous phases.</span></span> <span data-ttu-id="b7ee3-104">ビルド ラボ フェーズな時間がかかるので、このフェーズの前のフェーズを重複に異常はありません。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-104">Because the Build lab phase can be time consuming, it is not unusual for this phase to overlap earlier phases.</span></span> <span data-ttu-id="b7ee3-105">多くのシナリオで、アプリケーションのアーキテクチャに関する最終決定が行わには、ハードウェアとオペレーティング システムをインストールすることがあります。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-105">In many scenarios, the hardware and operating system may be installed before a final decision has been made as to the application architecture.</span></span> <span data-ttu-id="b7ee3-106">通常、パフォーマンス評価のビルド ラボの段階には、このトピックで説明したタスクが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-106">The Build lab phase of a performance assessment typically includes the tasks discussed in this topic.</span></span>  
  
## <a name="obtain-all-build-lab-infrastructure-at-least-a-week-in-advance-of-the-lab-start-date"></a><span data-ttu-id="b7ee3-107">すべてのビルド ラボ インフラストラクチャのラボの開始日の前に、少なくとも週を取得します。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-107">Obtain all build-lab infrastructure at least a week in advance of the lab start date</span></span>  
 <span data-ttu-id="b7ee3-108">少なくとも 1 週間、ラボの開始日前に、必要なハードウェアとソフトウェアの使用可能なすべてがあることを計画します。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-108">Plan to have available all of the required hardware and software at least a week before the lab start date.</span></span> <span data-ttu-id="b7ee3-109">これにより、ラボの貴重な時間が必要なインフラストラクチャの浪費されていないことが保証されます。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-109">This will ensure that valuable lab time is not wasted for want of the required infrastructure.</span></span>  
  
## <a name="configure-third-party-software-systems"></a><span data-ttu-id="b7ee3-110">サード パーティのソフトウェア システムを構成します。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-110">Configure third-party software systems</span></span>  
 <span data-ttu-id="b7ee3-111">サード パーティ システムを構築し、ラボを開始する前に構成する必要がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-111">There may be third-party systems that need to be built out and configured before the lab can begin.</span></span> <span data-ttu-id="b7ee3-112">領域の専門家 (Sme) がこれらのシステムに必要な場合は、ビルド、ラボの実行段階中にスケジュールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-112">If subject matter experts (SMEs) are required for these systems, be sure they are scheduled during the build-out and lab execution stages.</span></span> <span data-ttu-id="b7ee3-113">完全に文書化するの構築する手順を確認します。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-113">Ensure that they thoroughly document their build-out procedures.</span></span>  
  
## <a name="install-and-configure-the-biztalk-server-environment"></a><span data-ttu-id="b7ee3-114">インストールして、BizTalk Server 環境の構成</span><span class="sxs-lookup"><span data-stu-id="b7ee3-114">Install and configure the BizTalk Server environment</span></span>  
 <span data-ttu-id="b7ee3-115">BizTalk Server と必要な依存関係のソフトウェアをインストールするための詳細な手順は、[インストールおよびアップグレード ガイド](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)します。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-115">Detailed instructions for installing BizTalk Server and the required dependency software are in the [Installation and Upgrade Guides](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span></span> <span data-ttu-id="b7ee3-116">正常にインストールし、BizTalk Server 環境を構成した後、次のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-116">After successfully installing and configuring the BizTalk Server environment, complete the following tasks:</span></span>  
  
-   <span data-ttu-id="b7ee3-117">推奨事項に従って、[運用準備チェックリスト](operational-readiness-checklists.md)</span><span class="sxs-lookup"><span data-stu-id="b7ee3-117">Follow the recommendations listed in the [Operational Readiness Checklists](operational-readiness-checklists.md)</span></span>
  
-   <span data-ttu-id="b7ee3-118">推奨事項に従い[のパフォーマンスの最適化](../technical-guides/optimizing-performance.md)します。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-118">Follow the recommendations in [Optimizing Performance](../technical-guides/optimizing-performance.md).</span></span>  
  
-   <span data-ttu-id="b7ee3-119">すべてのコンピューターの時刻が正しく同期されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-119">Ensure all computer times are properly synchronized.</span></span>  
  
-   <span data-ttu-id="b7ee3-120">環境内のすべてのコンピューター間の MSDTC 機能を確認します。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-120">Verify MSDTC functionality between all computers in the environment.</span></span>  
  
-   <span data-ttu-id="b7ee3-121">本当に必要な場合を除き、カスタム トレース/ログ記録が無効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-121">Ensure any custom tracing/logging is disabled unless absolutely needed.</span></span>  
  
-   <span data-ttu-id="b7ee3-122">ロード テスト用の Visual Studio Ultimate edition をインストールします。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-122">Install the Visual Studio Ultimate edition for load testing.</span></span>  <span data-ttu-id="b7ee3-123">Visual Studio を使用して自動テストを実行する方法の詳細については、次を参照してください。[自動テストを容易にするために Visual Studio を使用して](../technical-guides/using-visual-studio-to-facilitate-automated-testing.md)します。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-123">For more information about how to perform automated testing using Visual Studio, see [Using Visual Studio to Facilitate Automated Testing](../technical-guides/using-visual-studio-to-facilitate-automated-testing.md).</span></span>  
  
-   <span data-ttu-id="b7ee3-124">必要に応じて、パフォーマンス モニター カウンターおよびログを設定します。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-124">Setup Performance Monitor counters and logs, as needed.</span></span>  
  
-   <span data-ttu-id="b7ee3-125">デバッグ コードの変更がパフォーマンス評価のスコープ内にある場合は、ソリューションをデバッグするコンピューターをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-125">Setup a debugging computer to debug the solution if code changes are within the scope of the performance assessment.</span></span>  
  
-   <span data-ttu-id="b7ee3-126">すべてのハード ドライブを最適化します。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-126">Defragment all hard drives.</span></span>  
  
-   <span data-ttu-id="b7ee3-127">ウイルス対策のリアルタイム スキャンを無効にします。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-127">Disable antivirus real time scanning.</span></span>  
  
-   <span data-ttu-id="b7ee3-128">エンタープライズ シングル サインオン マスター シークレットをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-128">Back up the Enterprise Single Sign-On Master Secret.</span></span>  
  
## <a name="install-the-biztalk-server-application-to-be-tested"></a><span data-ttu-id="b7ee3-129">テストする BizTalk Server アプリケーションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-129">Install the BizTalk Server application to be tested</span></span>  
 <span data-ttu-id="b7ee3-130">テストするアプリケーションのインストールには、通常、次の手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-130">Installation of the application to be tested will typically include the following steps:</span></span>  
  
1.  <span data-ttu-id="b7ee3-131">次に、BizTalk Server 管理コンソールを使用します。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-131">Use the BizTalk Server Administration console to do the following:</span></span>  
  
    -   <span data-ttu-id="b7ee3-132">ホストを作成します。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-132">Create Hosts</span></span>  
  
    -   <span data-ttu-id="b7ee3-133">送信/受信ハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-133">Create Send/Receive Handlers.</span></span>  
  
    -   <span data-ttu-id="b7ee3-134">ホスト インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-134">Create Host instances.</span></span>  
  
    -   <span data-ttu-id="b7ee3-135">BizTalk Server アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-135">Create BizTalk Server Applications.</span></span>  
  
2.  <span data-ttu-id="b7ee3-136">アプリケーションのインストール:</span><span class="sxs-lookup"><span data-stu-id="b7ee3-136">Application installation:</span></span>  
  
    1.  <span data-ttu-id="b7ee3-137">BizTalk Server グループに BizTalk Server のバイナリを展開します。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-137">Deploy BizTalk Server binaries to the BizTalk Server group.</span></span>  
  
    2.  <span data-ttu-id="b7ee3-138">BizTalk Server グループにバインドをインポートします。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-138">Import bindings to the BizTalk Server group.</span></span>  
  
    3.  <span data-ttu-id="b7ee3-139">すべてのボックスで GAC の BizTalk Server と BizTalk Server 以外のバイナリ。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-139">GAC BizTalk Server and non-BizTalk Server binaries on all boxes.</span></span>  
  
    4.  <span data-ttu-id="b7ee3-140">すべてのボックスに依存関係コンポーネントの存在を確認します。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-140">Ensure dependency components exist on all boxes.</span></span>  
  
3.  <span data-ttu-id="b7ee3-141">アプリケーションの依存関係をインストールします。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-141">Install dependency applications.</span></span>  
  
4.  <span data-ttu-id="b7ee3-142">BizTalk Server 管理コンソールで、トランスポートおよび物理エンドポイントを構成します。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-142">Configure transports and physical endpoints in the BizTalk Server Administration console.</span></span>  
  
5.  <span data-ttu-id="b7ee3-143">サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-143">Start services.</span></span>  
  
6.  <span data-ttu-id="b7ee3-144">基本的なスモーク テストの実行 – スモーク テストは、ソリューションの基本的な機能をテストするエンド ツー エンド機能テスト。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-144">Perform basic smoke tests – Smoke tests are end-to-end functional tests that test the basic functionality of your solution.</span></span>  
  
## <a name="implement-automated-build-and-load-testing"></a><span data-ttu-id="b7ee3-145">自動化されたビルドを実装し、ロード テスト</span><span class="sxs-lookup"><span data-stu-id="b7ee3-145">Implement automated build and load testing</span></span>  
 <span data-ttu-id="b7ee3-146">自動化ビルドおよびロード テストのプロセスの実装は、BizTalk Server のパフォーマンス評価の基盤ではほぼ間違いなくです。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-146">Implementation of an automated build and load testing process is arguably the cornerstone of a BizTalk Server performance assessment.</span></span> <span data-ttu-id="b7ee3-147">コードの変更がパフォーマンス評価のスコープ内にある場合は、自動化されたビルド プロセスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-147">An automated build process should be implemented if code changes are within the scope of the performance assessment.</span></span> <span data-ttu-id="b7ee3-148">自動化されたロード テストは、すべてのロード テストのシナリオを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-148">Automated load testing should be implemented for all load testing scenarios.</span></span> <span data-ttu-id="b7ee3-149">自動化されたビルドを実装して、ロード テストに必要な初期投資が迅速に削減、オートメーションは人的エラー対象である、日常的なビルド/テストのタスクの繰り返しを迅速かつ正確なに対応します。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-149">The initial time investment required to implement automated build and load testing is quickly recouped, automation accommodates rapid and precise repetition of mundane build/testing tasks that are subject to human error.</span></span> <span data-ttu-id="b7ee3-150">自動化されたビルドを実装して、テストのプロセスの詳細については、次を参照してください。[自動テストを実装する](../technical-guides/implementing-automated-testing.md)このガイドでします。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-150">For more information about implementing an automated build and testing process, see [Implementing Automated Testing](../technical-guides/implementing-automated-testing.md) in this guide.</span></span>  
  
## <a name="configure-performance-monitoring"></a><span data-ttu-id="b7ee3-151">パフォーマンス監視を構成します。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-151">Configure performance monitoring</span></span>  
 <span data-ttu-id="b7ee3-152">正確なパフォーマンスの監視は、パフォーマンス評価の成功に不可欠です。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-152">Accurate performance monitoring is critical to the success of the performance assessment.</span></span> <span data-ttu-id="b7ee3-153">スコープ フェーズで定義されたスループットと待機時間の目標に基づいてパフォーマンス メトリックを評価するかを判断します。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-153">Determine which performance metrics should be evaluated based on the throughput and latency goals that were defined in the Scope phase.</span></span> <span data-ttu-id="b7ee3-154">パフォーマンスの監視は、BizTalk Server 環境の各コンピューターで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-154">Performance monitoring should be performed on each computer in the BizTalk Server environment.</span></span> <span data-ttu-id="b7ee3-155">参照してください[パフォーマンス カウンター](../core/performance-counters.md)します。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-155">See [Performance Counters](../core/performance-counters.md).</span></span> <span data-ttu-id="b7ee3-156">ログのパフォーマンス分析ツール (PAL) を使用すると、視覚的に重要なパフォーマンス カウンターをグラフし、これらのカウンターのしきい値を超えた場合にアラートが生成される HTML レポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-156">Use the Performance Analysis of Logs tool (PAL) to generate HTML reports that graphically chart important performance counters and generate alerts when thresholds for these counters are exceeded.</span></span> <span data-ttu-id="b7ee3-157">S[パフォーマンス分析のログ (PAL) ツール](https://github.com/clinthuffman/PAL)します。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-157">S [Performance Analysis of Logs (PAL) tool](https://github.com/clinthuffman/PAL).</span></span>  
  
## <a name="establish-and-document-the-solutions-baseline-performance"></a><span data-ttu-id="b7ee3-158">確立して、ソリューションのベースライン パフォーマンスを文書化</span><span class="sxs-lookup"><span data-stu-id="b7ee3-158">Establish and document the solution’s baseline performance</span></span>  
 <span data-ttu-id="b7ee3-159">パフォーマンスの評価中に適用されるパフォーマンスの最適化の効果を測定できるように、ベースライン パフォーマンスを計算する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7ee3-159">Baseline performance should be calculated so that the effect of performance optimizations applied during the performance assessment can be measured.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7ee3-160">参照</span><span class="sxs-lookup"><span data-stu-id="b7ee3-160">See Also</span></span>  
 [<span data-ttu-id="b7ee3-161">パフォーマンス評価のフェーズ</span><span class="sxs-lookup"><span data-stu-id="b7ee3-161">Phases of a Performance Assessment</span></span>](../technical-guides/phases-of-a-performance-assessment.md)