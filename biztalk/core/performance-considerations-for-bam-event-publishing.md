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
ms.openlocfilehash: e01292443316088986ee0897cf180b1e26b103ae
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395291"
---
# <a name="performance-considerations-for-bam-event-publishing"></a><span data-ttu-id="99feb-102">BAM イベントを公開する際のパフォーマンスに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="99feb-102">Performance Considerations for BAM Event Publishing</span></span>
<span data-ttu-id="99feb-103">BAM では、ビジネス イベントの公開形式として、次に示す 2 種類の形式がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="99feb-103">BAM supports two forms of business event publishing:</span></span>  
  
- <span data-ttu-id="99feb-104">同期</span><span class="sxs-lookup"><span data-stu-id="99feb-104">Synchronous</span></span>  
  
- <span data-ttu-id="99feb-105">非同期</span><span class="sxs-lookup"><span data-stu-id="99feb-105">Asynchronous</span></span>  
  
  <span data-ttu-id="99feb-106">次の図に、これら 2 つのモデルを示します。</span><span class="sxs-lookup"><span data-stu-id="99feb-106">The following diagram illustrates the two models.</span></span>  
  
  <span data-ttu-id="99feb-107">![](../core/media/bam-topologies.gif "bam_topologies")</span><span class="sxs-lookup"><span data-stu-id="99feb-107">![](../core/media/bam-topologies.gif "bam_topologies")</span></span>  
  <span data-ttu-id="99feb-108">BAM トポロジ</span><span class="sxs-lookup"><span data-stu-id="99feb-108">BAM Topologies</span></span>  
  
  <span data-ttu-id="99feb-109">同期形式は管理とコードからの実行が容易ですが、非同期形式の方がパフォーマンスに優れています。</span><span class="sxs-lookup"><span data-stu-id="99feb-109">The synchronous approach is much simpler for management and using from code, while the asynchronous approach allows for better performance.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="99feb-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="99feb-110">In This Section</span></span>  
  
-   [<span data-ttu-id="99feb-111">同期ビジネス イベントの追跡</span><span class="sxs-lookup"><span data-stu-id="99feb-111">Synchronous Business Event Tracking</span></span>](../core/synchronous-business-event-tracking.md)  
  
-   [<span data-ttu-id="99feb-112">非同期ビジネス イベントの追跡</span><span class="sxs-lookup"><span data-stu-id="99feb-112">Asynchronous Business Event Tracking</span></span>](../core/asynchronous-business-event-tracking.md)