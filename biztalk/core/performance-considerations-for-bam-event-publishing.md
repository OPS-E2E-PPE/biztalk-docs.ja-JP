---
title: BAM イベントの発行のパフォーマンスに関する考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance, BAM
- publishing, BAM
- BAM, publishing
- events, tracking [BAM]
- BAM, event tracking
- BAM, performance
ms.assetid: 5a99e61a-a3d9-47fd-a933-2297f79817a5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c031f9a3325eda9cbcf865eaf72d1d9e100616c7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997539"
---
# <a name="performance-considerations-for-bam-event-publishing"></a><span data-ttu-id="60e83-102">BAM イベントを公開する際のパフォーマンスに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="60e83-102">Performance Considerations for BAM Event Publishing</span></span>
<span data-ttu-id="60e83-103">BAM では、ビジネス イベントの公開形式として、次に示す 2 種類の形式がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="60e83-103">BAM supports two forms of business event publishing:</span></span>  
  
- <span data-ttu-id="60e83-104">同期</span><span class="sxs-lookup"><span data-stu-id="60e83-104">Synchronous</span></span>  
  
- <span data-ttu-id="60e83-105">非同期</span><span class="sxs-lookup"><span data-stu-id="60e83-105">Asynchronous</span></span>  
  
  <span data-ttu-id="60e83-106">次の図に、これら 2 つのモデルを示します。</span><span class="sxs-lookup"><span data-stu-id="60e83-106">The following diagram illustrates the two models.</span></span>  
  
  <span data-ttu-id="60e83-107">![](../core/media/bam-topologies.gif "bam_topologies")</span><span class="sxs-lookup"><span data-stu-id="60e83-107">![](../core/media/bam-topologies.gif "bam_topologies")</span></span>  
  <span data-ttu-id="60e83-108">BAM トポロジ</span><span class="sxs-lookup"><span data-stu-id="60e83-108">BAM Topologies</span></span>  
  
  <span data-ttu-id="60e83-109">同期形式は管理とコードからの実行が容易ですが、非同期形式の方がパフォーマンスに優れています。</span><span class="sxs-lookup"><span data-stu-id="60e83-109">The synchronous approach is much simpler for management and using from code, while the asynchronous approach allows for better performance.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="60e83-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="60e83-110">In This Section</span></span>  
  
-   [<span data-ttu-id="60e83-111">同期ビジネス イベントの追跡</span><span class="sxs-lookup"><span data-stu-id="60e83-111">Synchronous Business Event Tracking</span></span>](../core/synchronous-business-event-tracking.md)  
  
-   [<span data-ttu-id="60e83-112">非同期ビジネス イベントの追跡</span><span class="sxs-lookup"><span data-stu-id="60e83-112">Asynchronous Business Event Tracking</span></span>](../core/asynchronous-business-event-tracking.md)