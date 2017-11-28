---
title: "オーケストレーションの退避のパフォーマンス カウンター |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3ab92e0e-6a33-4aaa-ab14-0c82322b04d5
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e81052f0061ff4ad802a084536c09d48cb6cb55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="orchestration-dehydration-performance-counters"></a><span data-ttu-id="ad447-102">オーケストレーションの退避のパフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="ad447-102">Orchestration Dehydration Performance Counters</span></span>
<span data-ttu-id="ad447-103">次の表に、退避の動作を監視するために使用される、オーケストレーション エンジンのパフォーマンス カウンターを示します。</span><span class="sxs-lookup"><span data-stu-id="ad447-103">The following table lists the names of Orchestration Engine performance counters that are specific to monitoring the behavior of dehydration.</span></span> <span data-ttu-id="ad447-104">パフォーマンス モニターを使用すると、これらのカウンターを監視しながら退避パラメーターを調整できます。</span><span class="sxs-lookup"><span data-stu-id="ad447-104">Use Performance Monitor to watch these counters while tuning your dehydration parameters.</span></span>  
  
|<span data-ttu-id="ad447-105">退避のパフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="ad447-105">Dehydration Performance Counter</span></span>|<span data-ttu-id="ad447-106">Description</span><span class="sxs-lookup"><span data-stu-id="ad447-106">Description</span></span>|  
|-------------------------------------|-----------------|  
|<span data-ttu-id="ad447-107">Dehydratable orchestrations</span><span class="sxs-lookup"><span data-stu-id="ad447-107">Dehydratable orchestrations</span></span>|<span data-ttu-id="ad447-108">ホスト インスタンスが現在ホストしている、待避可能なオーケストレーション インスタンスの数。</span><span class="sxs-lookup"><span data-stu-id="ad447-108">Number of orchestrations instances that can be dehydrated which are currently hosted by the host instance.</span></span>|  
|<span data-ttu-id="ad447-109">Dehydrating orchestrations</span><span class="sxs-lookup"><span data-stu-id="ad447-109">Dehydrating orchestrations</span></span>|<span data-ttu-id="ad447-110">待避処理中のオーケストレーション数。</span><span class="sxs-lookup"><span data-stu-id="ad447-110">Number of orchestrations that are in the process of dehydrating.</span></span>|  
|<span data-ttu-id="ad447-111">Dehydration cycle in progress</span><span class="sxs-lookup"><span data-stu-id="ad447-111">Dehydration cycle in progress</span></span>|<span data-ttu-id="ad447-112">待避サイクルが現在進行中であるかどうか。</span><span class="sxs-lookup"><span data-stu-id="ad447-112">Indicates whether there is a dehydration cycle currently in progress.</span></span>|  
|<span data-ttu-id="ad447-113">Dehydration cycles</span><span class="sxs-lookup"><span data-stu-id="ad447-113">Dehydration cycles</span></span>|<span data-ttu-id="ad447-114">完了した待避サイクルの数。</span><span class="sxs-lookup"><span data-stu-id="ad447-114">Number of dehydration cycles completed.</span></span>|  
|<span data-ttu-id="ad447-115">Dehydration threshold</span><span class="sxs-lookup"><span data-stu-id="ad447-115">Dehydration threshold</span></span>|<span data-ttu-id="ad447-116">オーケストレーションを待避する頻度を決定するしきい値 (ミリ秒)。</span><span class="sxs-lookup"><span data-stu-id="ad447-116">Number in milliseconds that determines how aggressively orchestrations are being dehydrated.</span></span> <span data-ttu-id="ad447-117">オーケストレーション エンジンによって推定された待避可能時間が、このしきい値を超えた場合、インスタンス待避されます。</span><span class="sxs-lookup"><span data-stu-id="ad447-117">If the orchestration engine predicts that an instance will be dehydratable for an amount of time longer than this threshold, it will dehydrate the instance.</span></span>|  
|<span data-ttu-id="ad447-118">Orchestrations dehydrated</span><span class="sxs-lookup"><span data-stu-id="ad447-118">Orchestrations dehydrated</span></span>|<span data-ttu-id="ad447-119">ホスト インスタンスの起動以降に待避されたオーケストレーション インスタンスの数。</span><span class="sxs-lookup"><span data-stu-id="ad447-119">Number of orchestration instances dehydrated since the host instance started.</span></span>|  
|<span data-ttu-id="ad447-120">Orchestrations dehydrated/sec</span><span class="sxs-lookup"><span data-stu-id="ad447-120">Orchestrations dehydrated/sec</span></span>|<span data-ttu-id="ad447-121">1 秒あたりの平均待避数。</span><span class="sxs-lookup"><span data-stu-id="ad447-121">Average number dehydrated per second.</span></span>|  
|<span data-ttu-id="ad447-122">Orchestrations rehydrated</span><span class="sxs-lookup"><span data-stu-id="ad447-122">Orchestrations rehydrated</span></span>|<span data-ttu-id="ad447-123">ホスト インスタンスの起動以降に復元されたオーケストレーション インスタンスの数。</span><span class="sxs-lookup"><span data-stu-id="ad447-123">Number of orchestration instances rehydrated since the host instance started.</span></span>|  
|<span data-ttu-id="ad447-124">Orchestrations rehydrated/sec</span><span class="sxs-lookup"><span data-stu-id="ad447-124">Orchestrations rehydrated/sec</span></span>|<span data-ttu-id="ad447-125">1 秒あたりに復元した数の平均値</span><span class="sxs-lookup"><span data-stu-id="ad447-125">Average number rehydrated per second</span></span>|  
|<span data-ttu-id="ad447-126">Orchestrations scheduled for dehydration</span><span class="sxs-lookup"><span data-stu-id="ad447-126">Orchestrations scheduled for dehydration</span></span>|<span data-ttu-id="ad447-127">保留中の待避要求が存在する、待避可能なオーケストレーション数。</span><span class="sxs-lookup"><span data-stu-id="ad447-127">Number of dehydratable orchestrations for which there is a dehydration request pending.</span></span>|