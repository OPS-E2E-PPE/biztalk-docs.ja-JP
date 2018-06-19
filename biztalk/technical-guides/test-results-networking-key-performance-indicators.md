---
title: 'テスト結果: ネットワー キング主要業績評価指標 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9bdbc2df-9d19-4ae8-b540-ec1b9a7cdbe9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3eb4e10c739178e6cd923f65b51f982e05ab7f56
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "22302586"
---
# <a name="test-results-networking-key-performance-indicators"></a><span data-ttu-id="088af-102">テスト結果: ネットワー キング主要業績評価指標</span><span class="sxs-lookup"><span data-stu-id="088af-102">Test Results: Networking Key Performance Indicators</span></span>
<span data-ttu-id="088af-103">このトピックでは、ネットワーク主要業績評価指標 (KPI)、テスト シナリオで監視された概要を示します。</span><span class="sxs-lookup"><span data-stu-id="088af-103">This topic summarizes Network Key Performance Indicators (KPI) observed during the test scenarios.</span></span> <span data-ttu-id="088af-104">これらのテスト評価のネットワークのパフォーマンスによって測定される、 **\Network インターフェイス (\*) \Bytes total/sec**パフォーマンス モニター カウンター、および測定することによって、 **SQL Network interface \bytes total/sec (Avg)** VSTS 2008 ロード テスト コント ローラーによって返されます。</span><span class="sxs-lookup"><span data-stu-id="088af-104">These tests evaluated Network Performance as measured by the **\Network Interface(\*)\Bytes Total/sec** performance monitor counter and by measuring the **SQL Network Interface\Bytes Total/sec (Avg )** returned by the VSTS 2008 Load Test Controller.</span></span>  
  
## <a name="summary-of-network-key-performance-indicators"></a><span data-ttu-id="088af-105">ネットワークの主要業績評価指標の概要</span><span class="sxs-lookup"><span data-stu-id="088af-105">Summary of Network Key Performance Indicators</span></span>  
 <span data-ttu-id="088af-106">**ネットワー キング主要業績評価指標-の比較**HYPER-V 仮想マシンで実行されている BizTalk Server のネットワーク スループットが確認された範囲にから約 70% から 96% の物理 BizTalk サーバーで達成されるネットワーク スループット、特定のテスト環境に応じて。</span><span class="sxs-lookup"><span data-stu-id="088af-106">**Comparison of Networking Key Performance Indicators –** Network throughput for BizTalk Server running on Hyper-V virtual machines was observed to range from approximately 70% to 96% of the network throughput achieved on the physical BizTalk Servers, depending on the particular test environment.</span></span> <span data-ttu-id="088af-107">HYPER-V 仮想マシンで実行されている SQL Server のネットワーク スループットがから約 68% から 81% の物理 SQL server の特定のテスト環境に応じて再び達成されるネットワーク スループットの範囲内に確認されました。</span><span class="sxs-lookup"><span data-stu-id="088af-107">Network throughput for SQL Server running on a Hyper-V virtual machine was observed to range from approximately 68% to 81% of the network throughput achieved on the physical SQL Server, again depending on the particular test environment.</span></span> <span data-ttu-id="088af-108">観察対象のネットワークのスループットのデルタは、HYPER-V ハイパーバイザーのリソース要件を属性付けすることができます。</span><span class="sxs-lookup"><span data-stu-id="088af-108">The delta in the observed network throughput can be attributed to the resource requirements of the Hyper-V Hypervisor.</span></span>  
  
 <span data-ttu-id="088af-109">手順に従います[ネットワーク最適化](../technical-guides/network-optimizations.md)によって測定される、HYPER-V 仮想マシン上のネットワーク スループットを最大化**\Network インターフェイス (\*) \Bytes total/sec**</span><span class="sxs-lookup"><span data-stu-id="088af-109">Follow the steps in [Network Optimizations](../technical-guides/network-optimizations.md) to maximize network throughput on Hyper-V virtual machines as measured by **\Network Interface(\*)\Bytes Total/sec**</span></span>  
  
 <span data-ttu-id="088af-110">次の図は、さまざまなテスト プラットフォームでは、ネットワークのパフォーマンスを示しています。</span><span class="sxs-lookup"><span data-stu-id="088af-110">The graphic below illustrates the network performance on the various test platforms:</span></span>  
  
 <span data-ttu-id="088af-111">![ネットワー キング主要業績評価指標](../technical-guides/media/networkkpi.gif "NetworkKPI")</span><span class="sxs-lookup"><span data-stu-id="088af-111">![Networking Key Performance Indicators](../technical-guides/media/networkkpi.gif "NetworkKPI")</span></span>  
  
 <span data-ttu-id="088af-112">次の表は、収集される KPI のそれぞれの構成の相対的なパフォーマンスを示しています。</span><span class="sxs-lookup"><span data-stu-id="088af-112">The table below illustrates the relative performance of the collected KPI’s for each configuration.</span></span> <span data-ttu-id="088af-113">各結果セットは、KPI の基準構成の割合として計算されます。</span><span class="sxs-lookup"><span data-stu-id="088af-113">Each result set is calculated as a percentage of the Baseline configuration KPI</span></span>  
  
|<span data-ttu-id="088af-114">KPI (KPI)</span><span class="sxs-lookup"><span data-stu-id="088af-114">KPI</span></span>|<span data-ttu-id="088af-115">仮想 BizTalk/物理 SQL</span><span class="sxs-lookup"><span data-stu-id="088af-115">Virtual BizTalk/Physical SQL</span></span>|<span data-ttu-id="088af-116">個別のホスト上の仮想 BizTalk/仮想 SQL</span><span class="sxs-lookup"><span data-stu-id="088af-116">Virtual BizTalk/Virtual SQL on separate Hosts</span></span>|<span data-ttu-id="088af-117">統合環境で仮想 BizTalk/仮想 SQL</span><span class="sxs-lookup"><span data-stu-id="088af-117">Virtual BizTalk/Virtual SQL on Consolidated environment</span></span>|  
|---------|-----------------------------------|----------------------------------------------------|--------------------------------------------------------------|  
|<span data-ttu-id="088af-118">\Network Interface(\*)\Bytes Total/sec (Total Avg Across all BizTalk Servers)</span><span class="sxs-lookup"><span data-stu-id="088af-118">\Network Interface(\*)\Bytes Total/sec (Total Avg Across all BizTalk Servers)</span></span>|<span data-ttu-id="088af-119">96%</span><span class="sxs-lookup"><span data-stu-id="088af-119">96%</span></span>|<span data-ttu-id="088af-120">82.1%</span><span class="sxs-lookup"><span data-stu-id="088af-120">82.1%</span></span>|<span data-ttu-id="088af-121">70.2%</span><span class="sxs-lookup"><span data-stu-id="088af-121">70.2%</span></span>|  
|<span data-ttu-id="088af-122">SQL Network Interface\Bytes Total/sec (Avg )</span><span class="sxs-lookup"><span data-stu-id="088af-122">SQL Network Interface\Bytes Total/sec (Avg )</span></span>|<span data-ttu-id="088af-123">95.5%</span><span class="sxs-lookup"><span data-stu-id="088af-123">95.5%</span></span>|<span data-ttu-id="088af-124">81.2%</span><span class="sxs-lookup"><span data-stu-id="088af-124">81.2%</span></span>|<span data-ttu-id="088af-125">68.4%</span><span class="sxs-lookup"><span data-stu-id="088af-125">68.4%</span></span>|  
  
 <span data-ttu-id="088af-126">ネットワークのパフォーマンスを評価する方法の詳細については、次を参照してください。、**ネットワーク パフォーマンスの測定**」の「[チェックリスト: Hyper-v でのパフォーマンスの測定](../technical-guides/checklist-measuring-performance-on-hyper-v.md)です。</span><span class="sxs-lookup"><span data-stu-id="088af-126">For more information about how to evaluate Network performance, see the **Measuring Network Performance** section of the topic [Checklist: Measuring Performance on Hyper-V](../technical-guides/checklist-measuring-performance-on-hyper-v.md).</span></span>