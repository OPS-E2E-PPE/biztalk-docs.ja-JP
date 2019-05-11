---
title: スケーラビリティとは何ですか。 | Microsoft Docs
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
ms.openlocfilehash: 46d74ed168f5dcc5a0d6d314627b6381ae5c4233
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395927"
---
# <a name="what-is-scalability"></a><span data-ttu-id="ebb53-103">スケーラビリティとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="ebb53-103">What Is Scalability?</span></span>
<span data-ttu-id="ebb53-104">スケーラビリティ、ビジネス ニーズに合わせて展開するシステムの機能があります。</span><span class="sxs-lookup"><span data-stu-id="ebb53-104">Scalability is the ability of a system to expand to meet your business needs.</span></span> <span data-ttu-id="ebb53-105">追加のハードウェアを追加するか、アプリケーションの大部分を変更することがなく既存のハードウェアをアップグレードすることでは、システムを拡張します。</span><span class="sxs-lookup"><span data-stu-id="ebb53-105">You scale a system by adding extra hardware or by upgrading the existing hardware without changing much of the application.</span></span> <span data-ttu-id="ebb53-106">BizTalk Server システムのコンテキストでは、スケーラビリティは、スケールとスループットのニーズの増加、待機時間の時間を短縮する必要がある場合に BizTalk の機能を指します。</span><span class="sxs-lookup"><span data-stu-id="ebb53-106">In the context of a BizTalk Server system, scalability refers to the ability of BizTalk to scale as your throughput needs increase, and if you need to reduce latency times.</span></span>  
  
 <span data-ttu-id="ebb53-107">BizTalk のさまざまなコンポーネントを調整して最適化した後、BizTalk コンピューター上か、メッセージ ボックス データベースのボトルネックが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ebb53-107">After you optimize and tune various components of BizTalk, you might still encounter bottlenecks on BizTalk computers or on the MessageBox database.</span></span> <span data-ttu-id="ebb53-108">BizTalk 環境でよく発生するボトルネックの種類では、CPU、メモリ、IO、およびロックの競合のボトルネック。</span><span class="sxs-lookup"><span data-stu-id="ebb53-108">The types of bottlenecks that usually occur in BizTalk environments are CPU, memory, IO and lock contention bottlenecks.</span></span> <span data-ttu-id="ebb53-109">ボトルネックの発生を開始するときは、ハードウェアをアップグレードするか、既存のトポロジに新しいハードウェアを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebb53-109">When you start to encounter bottlenecks, you may need to either upgrade the hardware or add new hardware into the existing topology.</span></span> <span data-ttu-id="ebb53-110">さいわい、BizTalk Server アーキテクチャを使用すると、簡単にスケール アップおよびスケール アウトできます。たとえば、グループに複数の BizTalk Server コンピューターを追加でき、余分なメッセージ ボックス データベースにも追加できます。</span><span class="sxs-lookup"><span data-stu-id="ebb53-110">Fortunately, BizTalk Server architecture enables you to easily scale-up and scale-out. For example, you can add multiple BizTalk Server computers into the group and also add extra MessageBox databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebb53-111">参照</span><span class="sxs-lookup"><span data-stu-id="ebb53-111">See Also</span></span>  
 <span data-ttu-id="ebb53-112">[BizTalk Server 層のスケール アウト](../core/scaling-out-the-biztalk-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="ebb53-112">[Scaling Out the BizTalk Server Tier](../core/scaling-out-the-biztalk-server-tier.md) </span></span>  
 <span data-ttu-id="ebb53-113">[SQL Server 層のスケール アウト](../core/scaling-out-the-sql-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="ebb53-113">[Scaling Out the SQL Server Tier](../core/scaling-out-the-sql-server-tier.md) </span></span>  
 <span data-ttu-id="ebb53-114">[BizTalk Server 層のスケール アップ](../core/scaling-up-the-biztalk-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="ebb53-114">[Scaling Up the BizTalk Server Tier](../core/scaling-up-the-biztalk-server-tier.md) </span></span>  
 <span data-ttu-id="ebb53-115">[SQL Server 層のスケール アップ](../core/scaling-up-the-sql-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="ebb53-115">[Scaling Up the SQL Server Tier](../core/scaling-up-the-sql-server-tier.md) </span></span>  
 <span data-ttu-id="ebb53-116">[受信ホスト スケール アウト](../core/scaled-out-receiving-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="ebb53-116">[Scaled-Out Receiving Hosts](../core/scaled-out-receiving-hosts.md) </span></span>  
 <span data-ttu-id="ebb53-117">[スケール アウトされた処理ホスト](../core/scaled-out-processing-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="ebb53-117">[Scaled-Out Processing Hosts](../core/scaled-out-processing-hosts.md) </span></span>  
 <span data-ttu-id="ebb53-118">[スケール アウトされた送信ホスト](../core/scaled-out-sending-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="ebb53-118">[Scaled-Out Sending Hosts](../core/scaled-out-sending-hosts.md) </span></span>  
 <span data-ttu-id="ebb53-119">[Windows Server クラスターを使用して BizTalk Server Hosts2 の高可用性を実現するには](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="ebb53-119">[Using Windows Server Cluster to Provide High Availability for BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span></span>  
 <span data-ttu-id="ebb53-120">[スケール アウト データベース](../core/scaled-out-databases.md) </span><span class="sxs-lookup"><span data-stu-id="ebb53-120">[Scaled-Out Databases](../core/scaled-out-databases.md) </span></span>  
 [<span data-ttu-id="ebb53-121">BizTalk Server データベースのクラスタリング</span><span class="sxs-lookup"><span data-stu-id="ebb53-121">Clustering the BizTalk Server Databases</span></span>](../core/clustering-the-biztalk-server-databases1.md)