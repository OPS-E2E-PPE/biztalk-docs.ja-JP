---
title: BizTalk Server の仮想化のパフォーマンスのテスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d09121b1-cdd6-4c01-9d69-0f1923464f0e
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f07c6bf8371e1db84ed574d7c737d4cc5b3903b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993699"
---
# <a name="testing-biztalk-server-virtualization-performance"></a><span data-ttu-id="98f00-102">BizTalk Server の仮想化のパフォーマンスをテストします。</span><span class="sxs-lookup"><span data-stu-id="98f00-102">Testing BizTalk Server Virtualization Performance</span></span>
<span data-ttu-id="98f00-103">このガイドで説明されているパフォーマンス テストのシナリオが、Microsoft テスト ラボで物理コンピューターで展開され、それぞれ個別のシステム アーキテクチャが、同じロード テストが実行されます。</span><span class="sxs-lookup"><span data-stu-id="98f00-103">Each of the performance test scenarios described in this guide were deployed on physical computers in a Microsoft test lab, and then the same load test was performed on each distinct system architecture.</span></span> <span data-ttu-id="98f00-104">各物理コンピュータ上のホスト オペレーティング システムがのフル インストール[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]Enterprise、64 ビット版で、HYPER-V サーバーの役割がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="98f00-104">The host operating system on each physical computer was a full installation of [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] Enterprise, 64-Bit Edition, with the Hyper-V server role installed.</span></span> <span data-ttu-id="98f00-105">BizTalk Server をテストするために使用する仮想マシンを使用して設定された[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]Enterprise、ゲスト オペレーティング システムと 64 ビット エディション。</span><span class="sxs-lookup"><span data-stu-id="98f00-105">The virtual machines used for testing BizTalk Server were set up with [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] Enterprise, 64-Bit Edition as the guest operating system.</span></span> <span data-ttu-id="98f00-106">SQL Server のテストに使用する仮想マシンを使用して設定された[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]Enterprise、ゲスト オペレーティング システムと 64 ビット エディション。</span><span class="sxs-lookup"><span data-stu-id="98f00-106">The virtual machine used for testing SQL Server was set up with [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] Enterprise, 64-Bit Edition as the guest operating system.</span></span> <span data-ttu-id="98f00-107">テスト シナリオ、テスト メソッド、パフォーマンス テストの結果、およびその後の分析のベスト プラクティスとガイダンスの設計、実装すると、一連の策定に使用され、仮想化を最適化する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="98f00-107">The test scenarios, test methods, performance test results, and subsequent analysis were used to formulate a series of best practices and guidance for designing, implementing, and optimizing virtualized [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
- <span data-ttu-id="98f00-108">**テストのシナリオ 1: ベースライン**– 最初のシナリオでは、物理的なハードウェアのみで実行されている BizTalk Server 環境のベースライン パフォーマンスを確立するために設計されました。</span><span class="sxs-lookup"><span data-stu-id="98f00-108">**Test Scenario 1: Baseline** – The first scenario was designed to establish baseline performance of a BizTalk Server environment running on physical hardware only.</span></span> <span data-ttu-id="98f00-109">このシナリオで BizTalk Server と SQL Server の両方がインストールされ物理ハードウェアだけで実行します。</span><span class="sxs-lookup"><span data-stu-id="98f00-109">For this scenario both BizTalk Server and SQL Server were installed and run on physical hardware only.</span></span>  
  
- <span data-ttu-id="98f00-110">**テストのシナリオ 2: 仮想 BizTalk/物理サーバーの SQL Server** -2 番目のシナリオが同じ物理サーバー上の複数のゲスト仮想マシンで BizTalk Server のホスティングのパフォーマンスに与える影響を判断するように設計されました。</span><span class="sxs-lookup"><span data-stu-id="98f00-110">**Test Scenario 2: Virtual BizTalk Server/Physical SQL Server** - The second scenario was designed to determine the performance impact of hosting BizTalk Server on multiple guest virtual machines on the same physical server.</span></span> <span data-ttu-id="98f00-111">テスト結果の構成が処理の物理マシンと同数の論理プロセッサの合計数を比較し、複数の仮想マシンから取得したすべての仮想マシンに分散します。</span><span class="sxs-lookup"><span data-stu-id="98f00-111">Test results taken from multiple virtual machine configurations were then compared to a physical machine processing with the same number of logical processors as the total number dispersed across all virtual machines.</span></span>  
  
- <span data-ttu-id="98f00-112">**テスト シナリオ 3: 仮想の BizTalk サーバー/仮想 SQL Server は別々 の物理的な HYPER-V ホスト上**-仮想化環境で BizTalk Server と SQL Server の両方を実行中のパフォーマンスに与える影響を判断する 3 番目のシナリオを行いました。</span><span class="sxs-lookup"><span data-stu-id="98f00-112">**Test Scenario 3: Virtual BizTalk Server/Virtual SQL Server on separate physical Hyper-V hosts** - The third scenario was conducted to determine the performance impact of running both BizTalk Server and SQL Server in a virtualized environment.</span></span> <span data-ttu-id="98f00-113">テストは、HYPER-V 仮想マシンで実行されている SQL Server インスタンスでホストされる BizTalk データベースで、HYPER-V 仮想マシンで実行されている BizTalk Server を使用して実行されました。</span><span class="sxs-lookup"><span data-stu-id="98f00-113">Tests were performed using BizTalk Server running on Hyper-V virtual machines with the BizTalk databases hosted on a SQL Server instance running on a Hyper-V virtual machine.</span></span> <span data-ttu-id="98f00-114">このシナリオでは、BizTalk Server の仮想マシンと SQL Server 仮想マシンに別々 の物理 HYPER-V ホストでホストされます。</span><span class="sxs-lookup"><span data-stu-id="98f00-114">For this scenario, the BizTalk Server virtual machines and the SQL Server virtual machines were hosted on separate physical Hyper-V hosts.</span></span>  
  
- <span data-ttu-id="98f00-115">**テストのシナリオ 4: サーバーの統合 - 完全な BizTalk グループを含む SQL、HYPER-V 上の 1 つの物理サーバー上に統合する**– 1 つの物理サーバーのシナリオでは、テスト アプリケーションを実行するために必要なすべて仮想マシン (Vm) がホストされています。</span><span class="sxs-lookup"><span data-stu-id="98f00-115">**Test Scenario 4: Server consolidation - Consolidating a full BizTalk Group Including SQL onto one Physical Server on Hyper-V** – In the scenario, all virtual machines (VMs) needed to run the test application are hosted on one physical server.</span></span> <span data-ttu-id="98f00-116">このシナリオでは、SQL Server と統合された環境で BizTalk Server の仮想マシン ホストのパフォーマンス コストを判断します。</span><span class="sxs-lookup"><span data-stu-id="98f00-116">The purpose of this scenario is to determine the performance costs of hosting SQL Server and BizTalk Server virtual machines in a consolidated environment.</span></span>  
  
  <span data-ttu-id="98f00-117">このセクションでは、テスト アプリケーションと各シナリオで使用されるサーバーのアーキテクチャの概要を説明し、主要業績評価指標 (Kpi) テスト中に確認されたについても説明します。</span><span class="sxs-lookup"><span data-stu-id="98f00-117">This section provides an overview of the test application and the server architecture used for each scenario and also presents key performance indicators (KPIs) observed during testing.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="98f00-118">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="98f00-118">In This Section</span></span>  
  
-   [<span data-ttu-id="98f00-119">テスト シナリオの概要</span><span class="sxs-lookup"><span data-stu-id="98f00-119">Test Scenario Overview</span></span>](../technical-guides/test-scenario-overview.md)  
  
-   [<span data-ttu-id="98f00-120">テスト シナリオ サーバーのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="98f00-120">Test Scenario Server Architecture</span></span>](../technical-guides/test-scenario-server-architecture.md)  
  
-   [<span data-ttu-id="98f00-121">テスト結果: BizTalk Server の主要業績評価指標</span><span class="sxs-lookup"><span data-stu-id="98f00-121">Test Results: BizTalk Server Key Performance Indicators</span></span>](../technical-guides/test-results-biztalk-server-key-performance-indicators.md)  
  
-   [<span data-ttu-id="98f00-122">テスト結果: SQL Server の主要業績評価指標</span><span class="sxs-lookup"><span data-stu-id="98f00-122">Test Results: SQL Server Key Performance Indicators</span></span>](../technical-guides/test-results-sql-server-key-performance-indicators.md)  
  
-   [<span data-ttu-id="98f00-123">テスト結果: ネットワークの主要業績評価指標</span><span class="sxs-lookup"><span data-stu-id="98f00-123">Test Results: Networking Key Performance Indicators</span></span>](../technical-guides/test-results-networking-key-performance-indicators.md)  
  
-   [<span data-ttu-id="98f00-124">テスト結果: メモリの主要業績評価指標</span><span class="sxs-lookup"><span data-stu-id="98f00-124">Test Results: Memory Key Performance Indicators</span></span>](../technical-guides/test-results-memory-key-performance-indicators.md)  
  
-   [<span data-ttu-id="98f00-125">テスト結果の概要</span><span class="sxs-lookup"><span data-stu-id="98f00-125">Summary of Test Results</span></span>](../technical-guides/summary-of-test-results.md)