---
title: "BizTalk Server の仮想化のパフォーマンスのテスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d09121b1-cdd6-4c01-9d69-0f1923464f0e
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d45567918cebd18bfea7bf30f31b299f6bed02d
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="testing-biztalk-server-virtualization-performance"></a><span data-ttu-id="149bd-102">BizTalk Server の仮想化のパフォーマンスをテストします。</span><span class="sxs-lookup"><span data-stu-id="149bd-102">Testing BizTalk Server Virtualization Performance</span></span>
<span data-ttu-id="149bd-103">Microsoft テスト ラボで物理コンピューターに展開されたそれぞれのこのガイドで説明されているパフォーマンス テストのシナリオと、それぞれ個別のシステム アーキテクチャが同じロード テストが実行されます。</span><span class="sxs-lookup"><span data-stu-id="149bd-103">Each of the performance test scenarios described in this guide were deployed on physical computers in a Microsoft test lab, and then the same load test was performed on each distinct system architecture.</span></span> <span data-ttu-id="149bd-104">各物理コンピュータ上のホスト オペレーティング システムがのフル インストールであった[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]Enterprise、64 ビット版で、HYPER-V サーバーの役割がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="149bd-104">The host operating system on each physical computer was a full installation of [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] Enterprise, 64-Bit Edition, with the Hyper-V server role installed.</span></span> <span data-ttu-id="149bd-105">BizTalk Server をテストするために使用する仮想マシンに設定された[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]Enterprise、ゲスト オペレーティング システムと 64 ビット エディションです。</span><span class="sxs-lookup"><span data-stu-id="149bd-105">The virtual machines used for testing BizTalk Server were set up with [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] Enterprise, 64-Bit Edition as the guest operating system.</span></span> <span data-ttu-id="149bd-106">SQL Server をテストするために使用するバーチャル マシンで設定した[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]Enterprise、ゲスト オペレーティング システムと 64 ビット エディションです。</span><span class="sxs-lookup"><span data-stu-id="149bd-106">The virtual machine used for testing SQL Server was set up with [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] Enterprise, 64-Bit Edition as the guest operating system.</span></span> <span data-ttu-id="149bd-107">一連のベスト プラクティスとの設計、実装、ガイダンスの策定に使用されたテストのシナリオ、テスト メソッド、パフォーマンス テストの結果、およびその後の分析と仮想化を最適化して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="149bd-107">The test scenarios, test methods, performance test results, and subsequent analysis were used to formulate a series of best practices and guidance for designing, implementing, and optimizing virtualized [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="149bd-108">**テストのシナリオ 1: ベースライン**– 最初のシナリオは、物理ハードウェアのみで実行されている BizTalk Server 環境のベースライン パフォーマンスを確立するために設計されました。</span><span class="sxs-lookup"><span data-stu-id="149bd-108">**Test Scenario 1: Baseline** – The first scenario was designed to establish baseline performance of a BizTalk Server environment running on physical hardware only.</span></span> <span data-ttu-id="149bd-109">このシナリオで BizTalk Server と SQL Server の両方がインストールされているし、のみ、物理ハードウェア上で実行します。</span><span class="sxs-lookup"><span data-stu-id="149bd-109">For this scenario both BizTalk Server and SQL Server were installed and run on physical hardware only.</span></span>  
  
-   <span data-ttu-id="149bd-110">**テストのシナリオ 2: 仮想 BizTalk/物理サーバーの SQL Server** -2 番目のシナリオは、同じ物理サーバー上の複数のゲスト仮想マシンで BizTalk Server のホスティングのパフォーマンスの影響を確認するように設計されました。</span><span class="sxs-lookup"><span data-stu-id="149bd-110">**Test Scenario 2: Virtual BizTalk Server/Physical SQL Server** - The second scenario was designed to determine the performance impact of hosting BizTalk Server on multiple guest virtual machines on the same physical server.</span></span> <span data-ttu-id="149bd-111">すべての仮想マシンに分散したテスト結果の構成が、物理マシンの処理に合計数と同数の論理プロセッサと比較し、複数の仮想マシンから取得します。</span><span class="sxs-lookup"><span data-stu-id="149bd-111">Test results taken from multiple virtual machine configurations were then compared to a physical machine processing with the same number of logical processors as the total number dispersed across all virtual machines.</span></span>  
  
-   <span data-ttu-id="149bd-112">**テスト シナリオ 3: 仮想の BizTalk サーバー/仮想 SQL Server は別の物理的な HYPER-V ホストで**-3 番目のシナリオは、仮想化環境で BizTalk Server と SQL Server の両方を実行するパフォーマンスの影響を判断する実施されています。</span><span class="sxs-lookup"><span data-stu-id="149bd-112">**Test Scenario 3: Virtual BizTalk Server/Virtual SQL Server on separate physical Hyper-V hosts** - The third scenario was conducted to determine the performance impact of running both BizTalk Server and SQL Server in a virtualized environment.</span></span> <span data-ttu-id="149bd-113">テストは、HYPER-V 仮想マシンで実行されている SQL Server インスタンスでホストされる BizTalk データベースで HYPER-V 仮想マシンで実行される BizTalk Server を使用して実行されました。</span><span class="sxs-lookup"><span data-stu-id="149bd-113">Tests were performed using BizTalk Server running on Hyper-V virtual machines with the BizTalk databases hosted on a SQL Server instance running on a Hyper-V virtual machine.</span></span> <span data-ttu-id="149bd-114">このシナリオでは、BizTalk Server の仮想マシンと SQL Server 仮想マシンに別の物理的な HYPER-V ホストでホストされます。</span><span class="sxs-lookup"><span data-stu-id="149bd-114">For this scenario, the BizTalk Server virtual machines and the SQL Server virtual machines were hosted on separate physical Hyper-V hosts.</span></span>  
  
-   <span data-ttu-id="149bd-115">**テストのシナリオ 4: サーバーの統合 - 完全 BizTalk グループを含む SQL HYPER-V 上の 1 つの物理サーバー上に統合する**– 1 つの物理サーバーのシナリオでは、すべての仮想マシン (Vm) をテスト アプリケーションを実行する必要がホストされています。</span><span class="sxs-lookup"><span data-stu-id="149bd-115">**Test Scenario 4: Server consolidation - Consolidating a full BizTalk Group Including SQL onto one Physical Server on Hyper-V** – In the scenario, all virtual machines (VMs) needed to run the test application are hosted on one physical server.</span></span> <span data-ttu-id="149bd-116">このシナリオの目的では、SQL Server と統合された環境で BizTalk Server の仮想マシンをホストしている場合のパフォーマンス コストを決定します。</span><span class="sxs-lookup"><span data-stu-id="149bd-116">The purpose of this scenario is to determine the performance costs of hosting SQL Server and BizTalk Server virtual machines in a consolidated environment.</span></span>  
  
 <span data-ttu-id="149bd-117">このセクションでは、テスト アプリケーションおよびシナリオごとに使用されるサーバーのアーキテクチャの概要を説明し、主要業績評価指標 (Kpi) のテスト中に観察されたについても説明します。</span><span class="sxs-lookup"><span data-stu-id="149bd-117">This section provides an overview of the test application and the server architecture used for each scenario and also presents key performance indicators (KPIs) observed during testing.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="149bd-118">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="149bd-118">In This Section</span></span>  
  
-   [<span data-ttu-id="149bd-119">テスト シナリオの概要</span><span class="sxs-lookup"><span data-stu-id="149bd-119">Test Scenario Overview</span></span>](../technical-guides/test-scenario-overview.md)  
  
-   [<span data-ttu-id="149bd-120">テスト シナリオ サーバーのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="149bd-120">Test Scenario Server Architecture</span></span>](../technical-guides/test-scenario-server-architecture.md)  
  
-   [<span data-ttu-id="149bd-121">テスト結果: BizTalk Server の主要業績評価指標</span><span class="sxs-lookup"><span data-stu-id="149bd-121">Test Results: BizTalk Server Key Performance Indicators</span></span>](../technical-guides/test-results-biztalk-server-key-performance-indicators.md)  
  
-   [<span data-ttu-id="149bd-122">テスト結果: SQL Server の主要業績評価指標</span><span class="sxs-lookup"><span data-stu-id="149bd-122">Test Results: SQL Server Key Performance Indicators</span></span>](../technical-guides/test-results-sql-server-key-performance-indicators.md)  
  
-   [<span data-ttu-id="149bd-123">テスト結果: ネットワークの主要業績評価指標</span><span class="sxs-lookup"><span data-stu-id="149bd-123">Test Results: Networking Key Performance Indicators</span></span>](../technical-guides/test-results-networking-key-performance-indicators.md)  
  
-   [<span data-ttu-id="149bd-124">テスト結果: メモリの主要業績評価指標</span><span class="sxs-lookup"><span data-stu-id="149bd-124">Test Results: Memory Key Performance Indicators</span></span>](../technical-guides/test-results-memory-key-performance-indicators.md)  
  
-   [<span data-ttu-id="149bd-125">テスト結果の概要</span><span class="sxs-lookup"><span data-stu-id="149bd-125">Summary of Test Results</span></span>](../technical-guides/summary-of-test-results.md)