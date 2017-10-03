---
title: "パフォーマンスのボトルネックを特定する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: performance, bottlenecks
ms.assetid: d8b93243-e383-4c21-9c08-073a0d4f79be
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b63519c51fdfbe2c8d63496132dd9f2a2438dcad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="identifying-performance-bottlenecks"></a><span data-ttu-id="4044c-102">パフォーマンスのボトルネックの特定</span><span class="sxs-lookup"><span data-stu-id="4044c-102">Identifying Performance Bottlenecks</span></span>
<span data-ttu-id="4044c-103">理想的な状況では、システムがほぼすべての機能を利用して実行されている (使用できるリソースを効率的に使用している) 場合、維持可能なスループットが実現し、総保有コスト (TCO) を削減できます。</span><span class="sxs-lookup"><span data-stu-id="4044c-103">Ideally, when a system is running at almost full capacity (optimal utilization of available resources), sustainable throughput can be achieved, lowering total cost of ownership (TCO).</span></span>  
  
 <span data-ttu-id="4044c-104">システムが想定したとおりに動作しない場合は、問題の原因を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4044c-104">When the system does not perform as expected, it is essential to identify the source of the problem.</span></span> <span data-ttu-id="4044c-105">これらのトピックでは、識別し、パフォーマンスのボトルネックを解決する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4044c-105">These topics explain how to identify and resolve the performance bottlenecks.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4044c-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4044c-106">In This Section</span></span>  
  
-   [<span data-ttu-id="4044c-107">ボトルネックを調査する方法</span><span class="sxs-lookup"><span data-stu-id="4044c-107">How to Investigate Bottlenecks</span></span>](../core/how-to-investigate-bottlenecks.md)  
  
-   [<span data-ttu-id="4044c-108">BizTalk 層のボトルネックを特定します。</span><span class="sxs-lookup"><span data-stu-id="4044c-108">Identifying Bottlenecks in the BizTalk Tier</span></span>](../core/identifying-bottlenecks-in-the-biztalk-tier.md)  
  
-   [<span data-ttu-id="4044c-109">メッセージ ボックス データベースのボトルネックを特定する方法</span><span class="sxs-lookup"><span data-stu-id="4044c-109">How to Identify Bottlenecks in the MessageBox Database</span></span>](../core/how-to-identify-bottlenecks-in-the-messagebox-database2.md)

- [<span data-ttu-id="4044c-110">BizTalkDTADb データベースのボトルネックを特定する方法</span><span class="sxs-lookup"><span data-stu-id="4044c-110">How to Identify Bottlenecks in the BizTalkDTADb Database</span></span>](../core/how-to-identify-bottlenecks-in-the-biztalkdtadb-database.md)

- [<span data-ttu-id="4044c-111">BAM データベースのボトルネックを特定する方法</span><span class="sxs-lookup"><span data-stu-id="4044c-111">How to Identify Bottlenecks in the BAM Database</span></span>](../core/how-to-identify-bottlenecks-in-the-bam-database.md)

- [<span data-ttu-id="4044c-112">ディスクの競合を回避する方法</span><span class="sxs-lookup"><span data-stu-id="4044c-112">How to Avoid Disk Contention</span></span>](../core/how-to-avoid-disk-contention1.md)
  
-   [<span data-ttu-id="4044c-113">ボトルネックを回避するためのガイドライン</span><span class="sxs-lookup"><span data-stu-id="4044c-113">Guidelines for Avoiding Bottlenecks</span></span>](../core/guidelines-for-avoiding-bottlenecks.md)