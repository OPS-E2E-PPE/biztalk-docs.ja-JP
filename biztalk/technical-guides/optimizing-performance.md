---
title: "パフォーマンスの最適化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bafa119b-187e-4595-a673-358dc0a109b7
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e79c318d7cd12d799459535914046da98819561
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="optimizing-performance"></a><span data-ttu-id="ad540-102">パフォーマンスの最適化</span><span class="sxs-lookup"><span data-stu-id="ad540-102">Optimizing Performance</span></span>
<span data-ttu-id="ad540-103">Windows オペレーティング システム、SQL Server の既定のインストール[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、実稼働の最適なパフォーマンスを提供する、IIS を大幅に最適化できますと[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。</span><span class="sxs-lookup"><span data-stu-id="ad540-103">A default installation of the Windows operating system, SQL Server, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and IIS can be significantly optimized to provide optimal performance for a production [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="ad540-104">WCF 構成パラメーターは、パフォーマンスが大幅に向上を提供する既定の設定からチューニングできます。</span><span class="sxs-lookup"><span data-stu-id="ad540-104">WCF configuration parameters can also be tuned from the default settings to provide significantly improved performance.</span></span> <span data-ttu-id="ad540-105">このセクションでは特定のパフォーマンスの最適化、実稼働環境を展開するときに従う必要がありますを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="ad540-105">This section provides specific performance optimizations that should be followed when deploying a production [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ad540-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ad540-106">In This Section</span></span>  
  
-   [<span data-ttu-id="ad540-107">オペレーティング システムのパフォーマンスを最適化します。</span><span class="sxs-lookup"><span data-stu-id="ad540-107">Optimizing Operating System Performance</span></span>](../technical-guides/optimizing-operating-system-performance.md)  
  
-   [<span data-ttu-id="ad540-108">ネットワーク パフォーマンスを最適化します。</span><span class="sxs-lookup"><span data-stu-id="ad540-108">Optimizing Network Performance</span></span>](../technical-guides/optimizing-network-performance.md)  
  
-   [<span data-ttu-id="ad540-109">IIS のパフォーマンスを最適化します。</span><span class="sxs-lookup"><span data-stu-id="ad540-109">Optimizing IIS Performance</span></span>](../technical-guides/optimizing-iis-performance.md)  
  
-   [<span data-ttu-id="ad540-110">データベースのパフォーマンスを最適化します。</span><span class="sxs-lookup"><span data-stu-id="ad540-110">Optimizing Database Performance</span></span>](../technical-guides/optimizing-database-performance.md)  
  
-   [<span data-ttu-id="ad540-111">BizTalk Server のパフォーマンスを最適化します。</span><span class="sxs-lookup"><span data-stu-id="ad540-111">Optimizing BizTalk Server Performance</span></span>](../technical-guides/optimizing-biztalk-server-performance.md)  
  
-   [<span data-ttu-id="ad540-112">オーケストレーションのパフォーマンスを最適化します。</span><span class="sxs-lookup"><span data-stu-id="ad540-112">Optimizing Orchestration Performance</span></span>](../technical-guides/optimizing-orchestration-performance.md)  
  
-   [<span data-ttu-id="ad540-113">WCF Web サービスのパフォーマンスを最適化します。</span><span class="sxs-lookup"><span data-stu-id="ad540-113">Optimizing WCF Web Service Performance</span></span>](../technical-guides/optimizing-wcf-web-service-performance.md)  
  
-   [<span data-ttu-id="ad540-114">BizTalk Server アプリケーションの最適化</span><span class="sxs-lookup"><span data-stu-id="ad540-114">Optimizing BizTalk Server Applications</span></span>](../technical-guides/optimizing-biztalk-server-applications.md)  
  
-   [<span data-ttu-id="ad540-115">Windows PowerShell スクリプト</span><span class="sxs-lookup"><span data-stu-id="ad540-115">Windows PowerShell Scripts</span></span>](../technical-guides/windows-powershell-scripts.md)