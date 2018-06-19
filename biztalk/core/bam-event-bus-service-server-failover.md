---
title: BAM イベント バス サービス サーバーのフェールオーバー |Microsoft ドキュメント
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
ms.openlocfilehash: 5c1fafc3e97d9905a6efd0de8ff0f389c2a389bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230642"
---
# <a name="bam-event-bus-service-server-failover"></a><span data-ttu-id="fe080-102">BAM イベント バス サービス サーバーのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="fe080-102">BAM Event Bus Service Server Failover</span></span>
<span data-ttu-id="fe080-103">BAM イベント バス サービスには、予期しない障害が発生した場合にデータを失わずに復旧して再起動するためのフォールト トレランス ロジックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fe080-103">The BAM Event Bus service includes fault tolerance logic that enables it to recover and restart from an unexpected failure without losing any data.</span></span>  
  
 <span data-ttu-id="fe080-104">複数のコンピューター上で BAM イベント バス サービスが有効になっている状態でサービスが失敗した場合、フェールオーバーのロジックでは BAM イベント バス サービスが停止したことが検出され、BAM イベント バス サービスの新しいインスタンスが自動的に別のコンピューター上で開始されます。</span><span class="sxs-lookup"><span data-stu-id="fe080-104">When you enable the BAM Event Bus service on multiple computers, and the service fails, failover logic will detect that a BAM Event Bus service has terminated, and the logic automatically starts a new instance of the BAM Event Bus service on another computer.</span></span>  
  
 <span data-ttu-id="fe080-105">BAM イベント バスが単純な負荷分散によってコンピューターまたはネットワークの障害を処理する方法を、次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="fe080-105">The following figure displays how the BAM Event Bus handles computer or network failures by performing simple load balancing.</span></span> <span data-ttu-id="fe080-106">BAM イベント バス サービスの開始前には、2 つの送信元と 1 つの送信先が構成されています。</span><span class="sxs-lookup"><span data-stu-id="fe080-106">Two sources and one destination were configured before the BAM Event Bus service starts.</span></span>  
  
 ![](../core/media/ebiz-bam-admin-evntbuspoolfail.gif "ebiz_bam_admin_evntbuspoolfail")  
<span data-ttu-id="fe080-107">BAM イベント バス サービスによる負荷分散の方法</span><span class="sxs-lookup"><span data-stu-id="fe080-107">How the BAM Event Bus service load balances</span></span>  
  
 <span data-ttu-id="fe080-108">BAM イベント バス サービスによる負荷分散は、次のようにして行われます。</span><span class="sxs-lookup"><span data-stu-id="fe080-108">The BAM Event Bus service load balances by performing the following:</span></span>  
  
-   <span data-ttu-id="fe080-109">**A: Server1 は 2 つのソース (セッション) からイベント データを処理**です。</span><span class="sxs-lookup"><span data-stu-id="fe080-109">**A: Server1 processes the event data from 2 sources (sessions)**.</span></span> <span data-ttu-id="fe080-110">BAM イベント バス サービスのインスタンスがサーバー 2 で作成される前に、BAM イベント バス オーケストレーション インスタンスがサーバー 1 で作成されます。</span><span class="sxs-lookup"><span data-stu-id="fe080-110">Before an instance of the BAM Event Bus service is created on Server2, a BAM Event Bus orchestration instance is created on Server1.</span></span> <span data-ttu-id="fe080-111">サーバーは他に利用できるサービスがないことを検出し、Src1 および Src2 の両方のセッションを取得します。</span><span class="sxs-lookup"><span data-stu-id="fe080-111">The server finds that there are no other servers available, and therefore picks up both sessions for Src1 and Src2.</span></span>  
  
-   <span data-ttu-id="fe080-112">**B: Server2 がオンラインになり、BAM イベント バス プールに参加**です。</span><span class="sxs-lookup"><span data-stu-id="fe080-112">**B: Server2 is brought online and joins the BAM Event Bus pool**.</span></span> <span data-ttu-id="fe080-113">BAM イベント バス サービスがサーバー 2 で作成された後、サーバー 1 が 1 つの BAM イベント バス サービス セッションをドロップし、サーバー 2 がそれを取得します。</span><span class="sxs-lookup"><span data-stu-id="fe080-113">After an instance of the BAM Event Bus service is created on Server2, Server1 drops one BAM Event Bus service session and Server2 picks it up.</span></span>  
  
-   <span data-ttu-id="fe080-114">**C: Server1 失敗**です。</span><span class="sxs-lookup"><span data-stu-id="fe080-114">**C: Server1 fails**.</span></span> <span data-ttu-id="fe080-115">サーバー 2 が BAE イベント バス プールに参加した後、サーバー 1 が失敗します。</span><span class="sxs-lookup"><span data-stu-id="fe080-115">Server1 fails after Server2 joins the BAM Event Bus pool.</span></span>  
  
-   <span data-ttu-id="fe080-116">**D: server2 という 2 つのソース (セッション) からのイベント データを処理する**です。</span><span class="sxs-lookup"><span data-stu-id="fe080-116">**D: Server2 processes the event data from 2 sources (sessions)**.</span></span> <span data-ttu-id="fe080-117">サーバー 2 が、Src1 および Src2 の両方のセッションを取得します。</span><span class="sxs-lookup"><span data-stu-id="fe080-117">Server2 picks up both sessions for Src1 and Src2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe080-118">参照</span><span class="sxs-lookup"><span data-stu-id="fe080-118">See Also</span></span>  
 <span data-ttu-id="fe080-119">[BAM イベント バス サービスを管理します。](../core/managing-the-bam-event-bus-service.md) </span><span class="sxs-lookup"><span data-stu-id="fe080-119">[Managing the BAM Event Bus Service](../core/managing-the-bam-event-bus-service.md) </span></span>  
 <span data-ttu-id="fe080-120">[BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="fe080-120">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="fe080-121">ビジネス アクティビティ監視 (BAM)</span><span class="sxs-lookup"><span data-stu-id="fe080-121">Business Activity Monitoring (BAM)</span></span>](../core/business-activity-monitoring-bam.md)