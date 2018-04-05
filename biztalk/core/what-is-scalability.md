---
title: スケーラビリティについて | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- scaling, scalability
ms.assetid: ac6acefd-864a-4f22-a136-a1951fe71e96
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a6208319fb8c195558101433cd1668ab0e0f064
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-scalability"></a><span data-ttu-id="60868-103">スケーラビリティについて</span><span class="sxs-lookup"><span data-stu-id="60868-103">What Is Scalability?</span></span>
<span data-ttu-id="60868-104">スケーラブルなシステムは必要に応じて拡張できます。</span><span class="sxs-lookup"><span data-stu-id="60868-104">Scalability is the ability of a system to expand to meet your business needs.</span></span> <span data-ttu-id="60868-105">システムを拡張するということは、アプリケーションをあまり変更せずにハードウェアの追加やアップグレードを行うことです。</span><span class="sxs-lookup"><span data-stu-id="60868-105">You scale a system by adding extra hardware or by upgrading the existing hardware without changing much of the application.</span></span> <span data-ttu-id="60868-106">BizTalk Server システムでは、スケーラビリティとは、拡張によってスループットの向上や待機時間の短縮を達成できる能力を意味します。</span><span class="sxs-lookup"><span data-stu-id="60868-106">In the context of a BizTalk Server system, scalability refers to the ability of BizTalk to scale as your throughput needs increase, and if you need to reduce latency times.</span></span>  
  
 <span data-ttu-id="60868-107">BizTalk のさまざまなコンポーネントを調整して最適化した後でも、BizTalk コンピューターやメッセージ ボックス データベースでボトルネックが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="60868-107">After you optimize and tune various components of BizTalk, you might still encounter bottlenecks on BizTalk computers or on the MessageBox database.</span></span> <span data-ttu-id="60868-108">BizTalk 環境でよく発生するボトルネックには、CPU、メモリ、IO およびロックの競合ボトルネックがあります。</span><span class="sxs-lookup"><span data-stu-id="60868-108">The types of bottlenecks that usually occur in BizTalk environments are CPU, memory, IO and lock contention bottlenecks.</span></span> <span data-ttu-id="60868-109">既存のトポロジでボトルネックが発生するようになったら、ハードウェアの追加やアップグレードを検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60868-109">When you start to encounter bottlenecks, you may need to either upgrade the hardware or add new hardware into the existing topology.</span></span> <span data-ttu-id="60868-110">さいわい、BizTalk Server はスケール アップやスケール アウトが簡単にできるアーキテクチャです。たとえば、複数の BizTalk Server コンピューターやメッセージ ボックス データベースの追加が可能です。</span><span class="sxs-lookup"><span data-stu-id="60868-110">Fortunately, BizTalk Server architecture enables you to easily scale-up and scale-out. For example, you can add multiple BizTalk Server computers into the group and also add extra MessageBox databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60868-111">参照</span><span class="sxs-lookup"><span data-stu-id="60868-111">See Also</span></span>  
 <span data-ttu-id="60868-112">[BizTalk Server 層のスケール アウト](../core/scaling-out-the-biztalk-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="60868-112">[Scaling Out the BizTalk Server Tier](../core/scaling-out-the-biztalk-server-tier.md) </span></span>  
 <span data-ttu-id="60868-113">[SQL Server 層のスケール アウト](../core/scaling-out-the-sql-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="60868-113">[Scaling Out the SQL Server Tier](../core/scaling-out-the-sql-server-tier.md) </span></span>  
 <span data-ttu-id="60868-114">[BizTalk Server 層のスケール アップ](../core/scaling-up-the-biztalk-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="60868-114">[Scaling Up the BizTalk Server Tier](../core/scaling-up-the-biztalk-server-tier.md) </span></span>  
 <span data-ttu-id="60868-115">[SQL Server 層のスケール アップ](../core/scaling-up-the-sql-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="60868-115">[Scaling Up the SQL Server Tier](../core/scaling-up-the-sql-server-tier.md) </span></span>  
 <span data-ttu-id="60868-116">[スケール アウト受信ホスト](../core/scaled-out-receiving-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="60868-116">[Scaled-Out Receiving Hosts](../core/scaled-out-receiving-hosts.md) </span></span>  
 <span data-ttu-id="60868-117">[スケール アウトされた処理ホスト](../core/scaled-out-processing-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="60868-117">[Scaled-Out Processing Hosts](../core/scaled-out-processing-hosts.md) </span></span>  
 <span data-ttu-id="60868-118">[スケール アウトされた送信ホスト](../core/scaled-out-sending-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="60868-118">[Scaled-Out Sending Hosts](../core/scaled-out-sending-hosts.md) </span></span>  
 <span data-ttu-id="60868-119">[Windows Server クラスターを使用して BizTalk Server Hosts2 の高可用性を実現するには](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="60868-119">[Using Windows Server Cluster to Provide High Availability for BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span></span>  
 <span data-ttu-id="60868-120">[スケール アウト データベース](../core/scaled-out-databases.md) </span><span class="sxs-lookup"><span data-stu-id="60868-120">[Scaled-Out Databases](../core/scaled-out-databases.md) </span></span>  
 [<span data-ttu-id="60868-121">BizTalk Server データベースをクラスタ リング</span><span class="sxs-lookup"><span data-stu-id="60868-121">Clustering the BizTalk Server Databases</span></span>](../core/clustering-the-biztalk-server-databases1.md)