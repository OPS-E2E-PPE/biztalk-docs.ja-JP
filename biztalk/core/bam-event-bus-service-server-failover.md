---
title: BAM イベント バス サービス サーバーのフェールオーバー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f12378c8-09bb-45c1-ade1-d9b20131461f
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca99e507e5f0344f7991a6e6b3c7798fb309dad4
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530596"
---
# <a name="bam-event-bus-service-server-failover"></a><span data-ttu-id="33a67-102">BAM イベント バス サービス サーバーのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="33a67-102">BAM Event Bus Service Server Failover</span></span>
<span data-ttu-id="33a67-103">BAM イベント バス サービスには、予期しない障害が発生した場合にデータを失わずに復旧して再起動するためのフォールト トレランス ロジックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="33a67-103">The BAM Event Bus service includes fault tolerance logic that enables it to recover and restart from an unexpected failure without losing any data.</span></span>  
  
 <span data-ttu-id="33a67-104">複数のコンピューターで BAM イベント バス サービスを有効にするし、サービスが失敗した場合、フェールオーバーのロジックは、BAM イベント バス サービスが終了すると、そのロジックでは、別のコンピューターで、BAM イベント バス サービスの新しいインスタンスを自動的に開始に検出されます。</span><span class="sxs-lookup"><span data-stu-id="33a67-104">When you enable the BAM Event Bus service on multiple computers, and the service fails, failover logic will detect that a BAM Event Bus service has terminated, and the logic automatically starts a new instance of the BAM Event Bus service on another computer.</span></span>  
  
 <span data-ttu-id="33a67-105">次の図は、BAM イベント バスがコンピューターでどのように処理する方法を示します。 またはネットワーク障害によって、単純な負荷を分散します。</span><span class="sxs-lookup"><span data-stu-id="33a67-105">The following figure displays how the BAM Event Bus handles computer or network failures by performing simple load balancing.</span></span> <span data-ttu-id="33a67-106">2 つのソースと変換先の 1 つは、BAM イベント バス サービスの開始前に構成されました。</span><span class="sxs-lookup"><span data-stu-id="33a67-106">Two sources and one destination were configured before the BAM Event Bus service starts.</span></span>  
  
 <span data-ttu-id="33a67-107">![](../core/media/ebiz-bam-admin-evntbuspoolfail.gif "ebiz_bam_admin_evntbuspoolfail")</span><span class="sxs-lookup"><span data-stu-id="33a67-107">![](../core/media/ebiz-bam-admin-evntbuspoolfail.gif "ebiz_bam_admin_evntbuspoolfail")</span></span>  
<span data-ttu-id="33a67-108">BAM イベント バス サービスの負荷を分散する方法</span><span class="sxs-lookup"><span data-stu-id="33a67-108">How the BAM Event Bus service load balances</span></span>  
  
 <span data-ttu-id="33a67-109">BAM イベント バス サービスの負荷は、次を実行することによって残高します。</span><span class="sxs-lookup"><span data-stu-id="33a67-109">The BAM Event Bus service load balances by performing the following:</span></span>  
  
-   <span data-ttu-id="33a67-110">**A:2 つのソース (セッション) からイベント データを処理する Server1**します。</span><span class="sxs-lookup"><span data-stu-id="33a67-110">**A: Server1 processes the event data from 2 sources (sessions)**.</span></span> <span data-ttu-id="33a67-111">Server2 で BAM イベント バス サービスのインスタンスを作成すると、前に、BAM イベント バス オーケストレーション インスタンスはサーバー 1 で作成します。</span><span class="sxs-lookup"><span data-stu-id="33a67-111">Before an instance of the BAM Event Bus service is created on Server2, a BAM Event Bus orchestration instance is created on Server1.</span></span> <span data-ttu-id="33a67-112">サーバーが検出されるその他のサーバー、およびそのため Src1 および Src2 の両方のセッションを取得します。</span><span class="sxs-lookup"><span data-stu-id="33a67-112">The server finds that there are no other servers available, and therefore picks up both sessions for Src1 and Src2.</span></span>  
  
-   <span data-ttu-id="33a67-113">**B:Server2 がオンラインになり、BAM イベント バス プールに参加**します。</span><span class="sxs-lookup"><span data-stu-id="33a67-113">**B: Server2 is brought online and joins the BAM Event Bus pool**.</span></span> <span data-ttu-id="33a67-114">Server2 で BAM イベント バス サービスのインスタンスが作成されると、Server1 は、1 つの BAM イベント バス サービス セッションを削除し、Server2 ピックアップします。</span><span class="sxs-lookup"><span data-stu-id="33a67-114">After an instance of the BAM Event Bus service is created on Server2, Server1 drops one BAM Event Bus service session and Server2 picks it up.</span></span>  
  
-   <span data-ttu-id="33a67-115">**C:サーバー 1 が失敗**します。</span><span class="sxs-lookup"><span data-stu-id="33a67-115">**C: Server1 fails**.</span></span> <span data-ttu-id="33a67-116">Server1 は、Server2 BAM イベント バス プールに参加した後に失敗します。</span><span class="sxs-lookup"><span data-stu-id="33a67-116">Server1 fails after Server2 joins the BAM Event Bus pool.</span></span>  
  
-   <span data-ttu-id="33a67-117">**D:Server2 という 2 つのソース (セッション) からイベント データを処理する**します。</span><span class="sxs-lookup"><span data-stu-id="33a67-117">**D: Server2 processes the event data from 2 sources (sessions)**.</span></span> <span data-ttu-id="33a67-118">Server2 では、Src1 および Src2 の両方のセッションを取得します。</span><span class="sxs-lookup"><span data-stu-id="33a67-118">Server2 picks up both sessions for Src1 and Src2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33a67-119">参照</span><span class="sxs-lookup"><span data-stu-id="33a67-119">See Also</span></span>  
 <span data-ttu-id="33a67-120">[BAM イベント バス サービスの管理](../core/managing-the-bam-event-bus-service.md) </span><span class="sxs-lookup"><span data-stu-id="33a67-120">[Managing the BAM Event Bus Service](../core/managing-the-bam-event-bus-service.md) </span></span>  
 <span data-ttu-id="33a67-121">[BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="33a67-121">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="33a67-122">ビジネス アクティビティの監視 (BAM)</span><span class="sxs-lookup"><span data-stu-id="33a67-122">Business Activity Monitoring (BAM)</span></span>](../core/business-activity-monitoring-bam.md)