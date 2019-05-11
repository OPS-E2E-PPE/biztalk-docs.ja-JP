---
title: テスト結果。主要業績評価指標のネットワーク |Microsoft Docs
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
ms.openlocfilehash: fdf346b1a13838ca8e3ba3cbd8ec208e33670f6c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400657"
---
# <a name="test-results-networking-key-performance-indicators"></a><span data-ttu-id="23e7b-102">テスト結果。ネットワー キング主要業績評価指標</span><span class="sxs-lookup"><span data-stu-id="23e7b-102">Test Results: Networking Key Performance Indicators</span></span>
<span data-ttu-id="23e7b-103">このトピックでは、ネットワーク主要業績評価指標 (KPI) テスト シナリオの中に確認されたをまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="23e7b-103">This topic summarizes Network Key Performance Indicators (KPI) observed during the test scenarios.</span></span> <span data-ttu-id="23e7b-104">これらのテストで測定した、ネットワーク パフォーマンスの評価、 **\Network Interface (\*) \Bytes total/sec**パフォーマンス モニター カウンターおよび測定することによって、 **SQL Network interface \bytes total/sec (Avg)** VSTS 2008 ロード テスト コント ローラーによって返されます。</span><span class="sxs-lookup"><span data-stu-id="23e7b-104">These tests evaluated Network Performance as measured by the **\Network Interface(\*)\Bytes Total/sec** performance monitor counter and by measuring the **SQL Network Interface\Bytes Total/sec (Avg )** returned by the VSTS 2008 Load Test Controller.</span></span>  
  
## <a name="summary-of-network-key-performance-indicators"></a><span data-ttu-id="23e7b-105">ネットワークの主要業績評価指標の概要</span><span class="sxs-lookup"><span data-stu-id="23e7b-105">Summary of Network Key Performance Indicators</span></span>  
 <span data-ttu-id="23e7b-106">**比較のネットワー キング主要業績評価指標 –** HYPER-V 仮想マシンで実行されている BizTalk Server のネットワーク スループットが範囲から約 70% に 96% のネットワーク スループット、物理的な BizTalk Server で行うことに監視、、特定のテスト環境によって異なります。</span><span class="sxs-lookup"><span data-stu-id="23e7b-106">**Comparison of Networking Key Performance Indicators –** Network throughput for BizTalk Server running on Hyper-V virtual machines was observed to range from approximately 70% to 96% of the network throughput achieved on the physical BizTalk Servers, depending on the particular test environment.</span></span> <span data-ttu-id="23e7b-107">HYPER-V 仮想マシンで実行されている SQL Server のネットワーク スループットがから約 68% から 81% のネットワーク スループットを特定のテスト環境に応じてもう一度、物理 SQL Server で行うことの範囲に確認されました。</span><span class="sxs-lookup"><span data-stu-id="23e7b-107">Network throughput for SQL Server running on a Hyper-V virtual machine was observed to range from approximately 68% to 81% of the network throughput achieved on the physical SQL Server, again depending on the particular test environment.</span></span> <span data-ttu-id="23e7b-108">観察されたネットワークのスループット単位のデルタは、HYPER-V ハイパーバイザーのリソース要件に起因ことができます。</span><span class="sxs-lookup"><span data-stu-id="23e7b-108">The delta in the observed network throughput can be attributed to the resource requirements of the Hyper-V Hypervisor.</span></span>  
  
 <span data-ttu-id="23e7b-109">次の手順では、[ネットワーク最適化](../technical-guides/network-optimizations.md)によって測定される、HYPER-V 仮想マシン上のネットワーク スループットを最大化する**\Network Interface (\*) \Bytes total/sec**</span><span class="sxs-lookup"><span data-stu-id="23e7b-109">Follow the steps in [Network Optimizations](../technical-guides/network-optimizations.md) to maximize network throughput on Hyper-V virtual machines as measured by **\Network Interface(\*)\Bytes Total/sec**</span></span>  
  
 <span data-ttu-id="23e7b-110">次の図は、さまざまなテスト プラットフォームのネットワーク パフォーマンスを示しています。</span><span class="sxs-lookup"><span data-stu-id="23e7b-110">The graphic below illustrates the network performance on the various test platforms:</span></span>  
  
 <span data-ttu-id="23e7b-111">![主要業績評価指標をネットワーク](../technical-guides/media/networkkpi.gif "NetworkKPI")</span><span class="sxs-lookup"><span data-stu-id="23e7b-111">![Networking Key Performance Indicators](../technical-guides/media/networkkpi.gif "NetworkKPI")</span></span>  
  
 <span data-ttu-id="23e7b-112">次の表は、収集された KPI の各構成の相対的なパフォーマンスを示しています。</span><span class="sxs-lookup"><span data-stu-id="23e7b-112">The table below illustrates the relative performance of the collected KPI’s for each configuration.</span></span> <span data-ttu-id="23e7b-113">各結果セットは KPI のベースライン構成の割合として計算されます。</span><span class="sxs-lookup"><span data-stu-id="23e7b-113">Each result set is calculated as a percentage of the Baseline configuration KPI</span></span>  
  
|<span data-ttu-id="23e7b-114">KPI (KPI)</span><span class="sxs-lookup"><span data-stu-id="23e7b-114">KPI</span></span>|<span data-ttu-id="23e7b-115">仮想 BizTalk/物理 SQL</span><span class="sxs-lookup"><span data-stu-id="23e7b-115">Virtual BizTalk/Physical SQL</span></span>|<span data-ttu-id="23e7b-116">個別のホスト上の仮想 BizTalk/仮想 SQL</span><span class="sxs-lookup"><span data-stu-id="23e7b-116">Virtual BizTalk/Virtual SQL on separate Hosts</span></span>|<span data-ttu-id="23e7b-117">統合環境で仮想 BizTalk/仮想 SQL</span><span class="sxs-lookup"><span data-stu-id="23e7b-117">Virtual BizTalk/Virtual SQL on Consolidated environment</span></span>|  
|---------|-----------------------------------|----------------------------------------------------|--------------------------------------------------------------|  
|<span data-ttu-id="23e7b-118">\Network Interface(\*)\Bytes Total/sec (Total Avg Across all BizTalk Servers)</span><span class="sxs-lookup"><span data-stu-id="23e7b-118">\Network Interface(\*)\Bytes Total/sec (Total Avg Across all BizTalk Servers)</span></span>|<span data-ttu-id="23e7b-119">96%</span><span class="sxs-lookup"><span data-stu-id="23e7b-119">96%</span></span>|<span data-ttu-id="23e7b-120">82.1%</span><span class="sxs-lookup"><span data-stu-id="23e7b-120">82.1%</span></span>|<span data-ttu-id="23e7b-121">70.2%</span><span class="sxs-lookup"><span data-stu-id="23e7b-121">70.2%</span></span>|  
|<span data-ttu-id="23e7b-122">SQL Network interface \bytes total/sec (Avg)</span><span class="sxs-lookup"><span data-stu-id="23e7b-122">SQL Network Interface\Bytes Total/sec (Avg )</span></span>|<span data-ttu-id="23e7b-123">95.5%</span><span class="sxs-lookup"><span data-stu-id="23e7b-123">95.5%</span></span>|<span data-ttu-id="23e7b-124">81.2%</span><span class="sxs-lookup"><span data-stu-id="23e7b-124">81.2%</span></span>|<span data-ttu-id="23e7b-125">68.4%</span><span class="sxs-lookup"><span data-stu-id="23e7b-125">68.4%</span></span>|  
  
 <span data-ttu-id="23e7b-126">ネットワーク パフォーマンスを評価する方法の詳細については、次を参照してください。、**ネットワーク パフォーマンスを測定する**」の「[チェックリスト。HYPER-V のパフォーマンスを測定する](../technical-guides/checklist-measuring-performance-on-hyper-v.md)します。</span><span class="sxs-lookup"><span data-stu-id="23e7b-126">For more information about how to evaluate Network performance, see the **Measuring Network Performance** section of the topic [Checklist: Measuring Performance on Hyper-V](../technical-guides/checklist-measuring-performance-on-hyper-v.md).</span></span>