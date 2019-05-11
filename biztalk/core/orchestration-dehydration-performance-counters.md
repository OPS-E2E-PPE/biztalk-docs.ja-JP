---
title: オーケストレーションの退避のパフォーマンス カウンター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3ab92e0e-6a33-4aaa-ab14-0c82322b04d5
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7e00a5c6c0adb1e964d9872d048a22d1d8b7eae
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262859"
---
# <a name="orchestration-dehydration-performance-counters"></a><span data-ttu-id="0cf2b-102">オーケストレーションの退避のパフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="0cf2b-102">Orchestration Dehydration Performance Counters</span></span>
<span data-ttu-id="0cf2b-103">次の表は、オーケストレーション エンジンのパフォーマンス カウンターは、退避の動作の監視に固有の名前を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="0cf2b-103">The following table lists the names of Orchestration Engine performance counters that are specific to monitoring the behavior of dehydration.</span></span> <span data-ttu-id="0cf2b-104">パフォーマンス モニターを使用して、退避パラメーターをチューニング中にこれらのカウンターを監視します。</span><span class="sxs-lookup"><span data-stu-id="0cf2b-104">Use Performance Monitor to watch these counters while tuning your dehydration parameters.</span></span>  
  
|<span data-ttu-id="0cf2b-105">退避のパフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="0cf2b-105">Dehydration Performance Counter</span></span>|<span data-ttu-id="0cf2b-106">説明</span><span class="sxs-lookup"><span data-stu-id="0cf2b-106">Description</span></span>|  
|-------------------------------------|-----------------|  
|<span data-ttu-id="0cf2b-107">待避可能なオーケストレーション</span><span class="sxs-lookup"><span data-stu-id="0cf2b-107">Dehydratable orchestrations</span></span>|<span data-ttu-id="0cf2b-108">数、ホスト インスタンスによって現在ホストされているができるインスタンスのオーケストレーションの退避します。</span><span class="sxs-lookup"><span data-stu-id="0cf2b-108">Number of orchestrations instances that can be dehydrated which are currently hosted by the host instance.</span></span>|  
|<span data-ttu-id="0cf2b-109">オーケストレーションの退避</span><span class="sxs-lookup"><span data-stu-id="0cf2b-109">Dehydrating orchestrations</span></span>|<span data-ttu-id="0cf2b-110">待避処理中のオーケストレーションの数。</span><span class="sxs-lookup"><span data-stu-id="0cf2b-110">Number of orchestrations that are in the process of dehydrating.</span></span>|  
|<span data-ttu-id="0cf2b-111">進行中の退避サイクル</span><span class="sxs-lookup"><span data-stu-id="0cf2b-111">Dehydration cycle in progress</span></span>|<span data-ttu-id="0cf2b-112">現在進行中の退避サイクルがあるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="0cf2b-112">Indicates whether there is a dehydration cycle currently in progress.</span></span>|  
|<span data-ttu-id="0cf2b-113">退避サイクル</span><span class="sxs-lookup"><span data-stu-id="0cf2b-113">Dehydration cycles</span></span>|<span data-ttu-id="0cf2b-114">完了した退避サイクルの数。</span><span class="sxs-lookup"><span data-stu-id="0cf2b-114">Number of dehydration cycles completed.</span></span>|  
|<span data-ttu-id="0cf2b-115">退避のしきい値</span><span class="sxs-lookup"><span data-stu-id="0cf2b-115">Dehydration threshold</span></span>|<span data-ttu-id="0cf2b-116">どの程度積極的にオーケストレーションが退避されているかを決定するミリ秒数。</span><span class="sxs-lookup"><span data-stu-id="0cf2b-116">Number in milliseconds that determines how aggressively orchestrations are being dehydrated.</span></span> <span data-ttu-id="0cf2b-117">インスタンスをこのしきい値より長い時間の量の推定された待避可能するは、オーケストレーション エンジンを予測する場合、インスタンス待避されます。</span><span class="sxs-lookup"><span data-stu-id="0cf2b-117">If the orchestration engine predicts that an instance will be dehydratable for an amount of time longer than this threshold, it will dehydrate the instance.</span></span>|  
|<span data-ttu-id="0cf2b-118">退避されたオーケストレーション</span><span class="sxs-lookup"><span data-stu-id="0cf2b-118">Orchestrations dehydrated</span></span>|<span data-ttu-id="0cf2b-119">オーケストレーション インスタンスの数は、ホスト インスタンスの起動以降に待避されました。</span><span class="sxs-lookup"><span data-stu-id="0cf2b-119">Number of orchestration instances dehydrated since the host instance started.</span></span>|  
|<span data-ttu-id="0cf2b-120">Orchestrations dehydrated/sec</span><span class="sxs-lookup"><span data-stu-id="0cf2b-120">Orchestrations dehydrated/sec</span></span>|<span data-ttu-id="0cf2b-121">1 秒あたりの平均待避数。</span><span class="sxs-lookup"><span data-stu-id="0cf2b-121">Average number dehydrated per second.</span></span>|  
|<span data-ttu-id="0cf2b-122">リハイド レートされたオーケストレーション</span><span class="sxs-lookup"><span data-stu-id="0cf2b-122">Orchestrations rehydrated</span></span>|<span data-ttu-id="0cf2b-123">ホスト インスタンスの起動後にリハイド レートされたオーケストレーション インスタンスの数。</span><span class="sxs-lookup"><span data-stu-id="0cf2b-123">Number of orchestration instances rehydrated since the host instance started.</span></span>|  
|<span data-ttu-id="0cf2b-124">Orchestrations rehydrated/sec</span><span class="sxs-lookup"><span data-stu-id="0cf2b-124">Orchestrations rehydrated/sec</span></span>|<span data-ttu-id="0cf2b-125">1 秒あたりにリハイド レートされた数の平均値</span><span class="sxs-lookup"><span data-stu-id="0cf2b-125">Average number rehydrated per second</span></span>|  
|<span data-ttu-id="0cf2b-126">オーケストレーションの退避のスケジュール</span><span class="sxs-lookup"><span data-stu-id="0cf2b-126">Orchestrations scheduled for dehydration</span></span>|<span data-ttu-id="0cf2b-127">対象の保留中の退避要求が、待避可能なオーケストレーションの数。</span><span class="sxs-lookup"><span data-stu-id="0cf2b-127">Number of dehydratable orchestrations for which there is a dehydration request pending.</span></span>|