---
title: 'テスト結果: メモリ主要業績評価指標 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 224c40e5-08a7-4d30-b03a-4b6add5cde1f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4edf88023ee9e30e7fd0c808346b6231112f8ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22301874"
---
# <a name="test-results-memory-key-performance-indicators"></a><span data-ttu-id="654f8-102">テスト結果: メモリ主要業績評価指標</span><span class="sxs-lookup"><span data-stu-id="654f8-102">Test Results: Memory Key Performance Indicators</span></span>
<span data-ttu-id="654f8-103">このトピックでは、メモリ主要業績評価指標 (KPI)、テスト シナリオで監視された概要を示します。</span><span class="sxs-lookup"><span data-stu-id="654f8-103">This topic summarizes Memory Key Performance Indicators (KPI) observed during the test scenarios.</span></span> <span data-ttu-id="654f8-104">これらのテストで測定された使用可能なメモリの評価、 **\Memory\Available Mbytes**パフォーマンス モニター カウンターです。</span><span class="sxs-lookup"><span data-stu-id="654f8-104">These tests evaluated available memory as measured by the **\Memory\Available Mbytes** performance monitor counter.</span></span>  
  
## <a name="summary-of-memory-key-performance-indicators"></a><span data-ttu-id="654f8-105">メモリ主要業績評価指標の概要</span><span class="sxs-lookup"><span data-stu-id="654f8-105">Summary of Memory Key Performance Indicators</span></span>  
 <span data-ttu-id="654f8-106">**メモリ主要業績評価指標-の比較**SQL Server と BizTalk Server によって測定に使用できるメモリの合計、 **\Memory\Available Mbytes**パフォーマンス モニター カウンターがすべてにわたって一貫性シナリオをテストします。</span><span class="sxs-lookup"><span data-stu-id="654f8-106">**Comparison of Memory Key Performance Indicators –** Total memory available to SQL Server and BizTalk Server as measured by the **\Memory\Available Mbytes** performance monitor counter was fairly consistent across all test scenarios.</span></span> <span data-ttu-id="654f8-107">物理的な BizTalk Server コンピューターと仮想マシンで実行されている BizTalk Server コンピューターで利用できるメモリの平均に利用可能なメモリの平均差は 2 つの BizTalk Server コンピューターがテストに使用したという事実が原因3 つの中に仮想マシンで実行されている BizTalk Server コンピューターは、テストに使用しました。</span><span class="sxs-lookup"><span data-stu-id="654f8-107">The difference in the average memory available to the physical BizTalk Server computers and the average memory available to the BizTalk Server computers running on virtual machines is due to the fact that two physical BizTalk Server computers were used for testing while three BizTalk Server computers running on virtual machines were used for testing.</span></span>  
  
 <span data-ttu-id="654f8-108">次の図は、さまざまなテスト プラットフォームでは、メモリのパフォーマンスを示しています。</span><span class="sxs-lookup"><span data-stu-id="654f8-108">The graphic below illustrates Memory performance on the various test platforms:</span></span>  
  
 <span data-ttu-id="654f8-109">![メモリ主要業績評価指標](../technical-guides/media/memorykpi.gif "MemoryKPI")</span><span class="sxs-lookup"><span data-stu-id="654f8-109">![Memory Key Performance Indicators](../technical-guides/media/memorykpi.gif "MemoryKPI")</span></span>  
  
 <span data-ttu-id="654f8-110">次の表は、収集される KPI のそれぞれの構成の相対的なパフォーマンスを示しています。</span><span class="sxs-lookup"><span data-stu-id="654f8-110">The table below illustrates the relative performance of the collected KPI’s for each configuration.</span></span> <span data-ttu-id="654f8-111">各結果セットは、KPI の基準構成の割合として計算されます。</span><span class="sxs-lookup"><span data-stu-id="654f8-111">Each result set is calculated as a percentage of the Baseline configuration KPI</span></span>  
  
|<span data-ttu-id="654f8-112">KPI (KPI)</span><span class="sxs-lookup"><span data-stu-id="654f8-112">KPI</span></span>|<span data-ttu-id="654f8-113">仮想 BizTalk/物理 SQL</span><span class="sxs-lookup"><span data-stu-id="654f8-113">Virtual BizTalk/Physical SQL</span></span>|<span data-ttu-id="654f8-114">個別のホスト上の仮想 BizTalk/仮想 SQL</span><span class="sxs-lookup"><span data-stu-id="654f8-114">Virtual BizTalk/Virtual SQL on separate Hosts</span></span>|<span data-ttu-id="654f8-115">統合環境で仮想 BizTalk/仮想 SQL</span><span class="sxs-lookup"><span data-stu-id="654f8-115">Virtual BizTalk/Virtual SQL on Consolidated environment</span></span>|  
|---------|-----------------------------------|----------------------------------------------------|--------------------------------------------------------------|  
|<span data-ttu-id="654f8-116">SQL Server 使用可能なメモリ (Mbytes) 各サーバー</span><span class="sxs-lookup"><span data-stu-id="654f8-116">SQL Server Available Memory (Mbytes) Per Server</span></span>|<span data-ttu-id="654f8-117">100.1%</span><span class="sxs-lookup"><span data-stu-id="654f8-117">100.1%</span></span>|<span data-ttu-id="654f8-118">97.1%</span><span class="sxs-lookup"><span data-stu-id="654f8-118">97.1%</span></span>|<span data-ttu-id="654f8-119">103.2%</span><span class="sxs-lookup"><span data-stu-id="654f8-119">103.2%</span></span>|  
|<span data-ttu-id="654f8-120">BizTalk の合計使用可能なメモリ (バイト)</span><span class="sxs-lookup"><span data-stu-id="654f8-120">Total BizTalk Available Memory (Mbytes)</span></span>|<span data-ttu-id="654f8-121">88.3%</span><span class="sxs-lookup"><span data-stu-id="654f8-121">88.3%</span></span>|<span data-ttu-id="654f8-122">95.9%</span><span class="sxs-lookup"><span data-stu-id="654f8-122">95.9%</span></span>|<span data-ttu-id="654f8-123">96%</span><span class="sxs-lookup"><span data-stu-id="654f8-123">96%</span></span>|  
|<span data-ttu-id="654f8-124">サーバーあたりの平均/BizTalk 使用可能なメモリ (バイト)</span><span class="sxs-lookup"><span data-stu-id="654f8-124">Average Per Server / BizTalk Available Memory (Mbytes)</span></span>|<span data-ttu-id="654f8-125">58.9%</span><span class="sxs-lookup"><span data-stu-id="654f8-125">58.9%</span></span>|<span data-ttu-id="654f8-126">63.9%</span><span class="sxs-lookup"><span data-stu-id="654f8-126">63.9%</span></span>|<span data-ttu-id="654f8-127">64%</span><span class="sxs-lookup"><span data-stu-id="654f8-127">64%</span></span>|  
  
 <span data-ttu-id="654f8-128">メモリのパフォーマンスを評価する方法の詳細については、次を参照してください。、**メモリ パフォーマンスの測定**」の「[チェックリスト: Hyper-v でのパフォーマンスの測定](../technical-guides/checklist-measuring-performance-on-hyper-v.md)です。</span><span class="sxs-lookup"><span data-stu-id="654f8-128">For more information about how to evaluate Memory performance, see the **Measuring Memory Performance** section of the topic [Checklist: Measuring Performance on Hyper-V](../technical-guides/checklist-measuring-performance-on-hyper-v.md).</span></span>