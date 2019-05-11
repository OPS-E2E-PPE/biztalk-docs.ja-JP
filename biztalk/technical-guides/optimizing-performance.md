---
title: パフォーマンスの最適化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bafa119b-187e-4595-a673-358dc0a109b7
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf9354e1b7b8d40452e492b3801d73f1669c37ef
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291345"
---
# <a name="optimizing-performance"></a><span data-ttu-id="b4d63-102">パフォーマンスの最適化</span><span class="sxs-lookup"><span data-stu-id="b4d63-102">Optimizing Performance</span></span>
<span data-ttu-id="b4d63-103">Windows オペレーティング システム、SQL Server の既定のインストール[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、IIS は、運用環境に最適なパフォーマンスを提供する大幅に最適化と[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。</span><span class="sxs-lookup"><span data-stu-id="b4d63-103">A default installation of the Windows operating system, SQL Server, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and IIS can be significantly optimized to provide optimal performance for a production [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="b4d63-104">WCF 構成のパラメーターは、大幅に向上したパフォーマンスを提供する既定の設定も調整できます。</span><span class="sxs-lookup"><span data-stu-id="b4d63-104">WCF configuration parameters can also be tuned from the default settings to provide significantly improved performance.</span></span> <span data-ttu-id="b4d63-105">このセクションで、運用環境をデプロイするときに従う必要がありますを特定のパフォーマンスの最適化を提供して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューション。</span><span class="sxs-lookup"><span data-stu-id="b4d63-105">This section provides specific performance optimizations that should be followed when deploying a production [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b4d63-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b4d63-106">In This Section</span></span>  
  
-   [<span data-ttu-id="b4d63-107">オペレーティング システムのパフォーマンスの最適化</span><span class="sxs-lookup"><span data-stu-id="b4d63-107">Optimizing Operating System Performance</span></span>](../technical-guides/optimizing-operating-system-performance.md)  
  
-   [<span data-ttu-id="b4d63-108">ネットワーク パフォーマンスの最適化</span><span class="sxs-lookup"><span data-stu-id="b4d63-108">Optimizing Network Performance</span></span>](../technical-guides/optimizing-network-performance.md)  
  
-   [<span data-ttu-id="b4d63-109">IIS パフォーマンスの最適化</span><span class="sxs-lookup"><span data-stu-id="b4d63-109">Optimizing IIS Performance</span></span>](../technical-guides/optimizing-iis-performance.md)  
  
-   [<span data-ttu-id="b4d63-110">データベース パフォーマンスの最適化</span><span class="sxs-lookup"><span data-stu-id="b4d63-110">Optimizing Database Performance</span></span>](../technical-guides/optimizing-database-performance.md)  
  
-   [<span data-ttu-id="b4d63-111">BizTalk Server パフォーマンスの最適化</span><span class="sxs-lookup"><span data-stu-id="b4d63-111">Optimizing BizTalk Server Performance</span></span>](../technical-guides/optimizing-biztalk-server-performance.md)  
  
-   [<span data-ttu-id="b4d63-112">オーケストレーション パフォーマンスの最適化</span><span class="sxs-lookup"><span data-stu-id="b4d63-112">Optimizing Orchestration Performance</span></span>](../technical-guides/optimizing-orchestration-performance.md)  
  
-   [<span data-ttu-id="b4d63-113">WCF Web Service パフォーマンスの最適化</span><span class="sxs-lookup"><span data-stu-id="b4d63-113">Optimizing WCF Web Service Performance</span></span>](../technical-guides/optimizing-wcf-web-service-performance.md)  
  
-   [<span data-ttu-id="b4d63-114">BizTalk Server アプリケーションの最適化</span><span class="sxs-lookup"><span data-stu-id="b4d63-114">Optimizing BizTalk Server Applications</span></span>](../technical-guides/optimizing-biztalk-server-applications.md)  
  
-   [<span data-ttu-id="b4d63-115">Windows PowerShell スクリプト</span><span class="sxs-lookup"><span data-stu-id="b4d63-115">Windows PowerShell Scripts</span></span>](../technical-guides/windows-powershell-scripts.md)