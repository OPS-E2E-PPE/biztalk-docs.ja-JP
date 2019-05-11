---
title: BizTalk Server 層のスケール アップ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, scaling
- scaling, examples
- scaling, scaling up
ms.assetid: 9002006a-f301-4e15-94b9-6caffd7c527c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6debecada3269374e2fd6f91a06d9e120c2538e6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308808"
---
# <a name="scaling-up-the-biztalk-server-tier"></a><span data-ttu-id="4077c-102">BizTalk Server 層のスケール アップ</span><span class="sxs-lookup"><span data-stu-id="4077c-102">Scaling Up the BizTalk Server Tier</span></span>
<span data-ttu-id="4077c-103">BizTalk 層を拡大するには、CPU、メモリ、IO、およびその他のリソースをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="4077c-103">To scale up the BizTalk tier, you upgrade the CPU, memory, IO and other resources.</span></span> <span data-ttu-id="4077c-104">次の図は、次の 4 つのプロセッサのコンピューターに 2 つのプロセッサのコンピューターから、BizTalk 層をスケールとする方法の例を示します。</span><span class="sxs-lookup"><span data-stu-id="4077c-104">The following figure shows an example of how you might scale up the BizTalk tier from a two processor computer to a four processor computer.</span></span>  
  
 <span data-ttu-id="4077c-105">![スケール&#45;を BTS](../core/media/scaleupbts.gif "ScaleUpBTS")</span><span class="sxs-lookup"><span data-stu-id="4077c-105">![Scale&#45;up BTS](../core/media/scaleupbts.gif "ScaleUpBTS")</span></span>  
  
 <span data-ttu-id="4077c-106">BizTalk 層のスケール アップのシナリオでは、スケール アウトを選択したときに似ています。</span><span class="sxs-lookup"><span data-stu-id="4077c-106">The scenarios for scaling up your BizTalk tier are similar to when you choose to scale out:</span></span>  
  
-   <span data-ttu-id="4077c-107">BizTalk Server では、ボトルネックになります。</span><span class="sxs-lookup"><span data-stu-id="4077c-107">BizTalk Server becomes a bottleneck.</span></span> <span data-ttu-id="4077c-108">次の問題のいずれかでは、ボトルネックが考えられます。</span><span class="sxs-lookup"><span data-stu-id="4077c-108">The bottleneck itself may be caused by one of the following problems:</span></span>  
  
-   <span data-ttu-id="4077c-109">CPU:シナリオでは、CPU 負荷のかかるパイプライン、マップ、またはオーケストレーションを使用する場合、BizTalk server には余分な CPU ヘッドルームはありません。</span><span class="sxs-lookup"><span data-stu-id="4077c-109">CPU: If the scenario uses CPU intensive pipelines, maps, or orchestrations, the BizTalk servers will not have any extra CPU headroom.</span></span>  
  
-   <span data-ttu-id="4077c-110">メモリと I/O:既存のコンピューター メモリ、IO、およびコンピューターの最大値に達した場合は、アップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4077c-110">Memory and I/O: If the existing computers have reached their maximum limit on memory and IO, and the computer needs to be upgraded.</span></span>  
  
-   <span data-ttu-id="4077c-111">スケール アウトは、コストが高すぎます。</span><span class="sxs-lookup"><span data-stu-id="4077c-111">Scaling out is too expensive.</span></span>  
  
-   <span data-ttu-id="4077c-112">スケール アウトの場合は、ボトルネックを解消していません。</span><span class="sxs-lookup"><span data-stu-id="4077c-112">If scale-out does not address the bottleneck.</span></span> <span data-ttu-id="4077c-113">たとえば、スケール アウト扱いません次のボトルネック。</span><span class="sxs-lookup"><span data-stu-id="4077c-113">For example, scaling out does not address the following bottlenecks:</span></span>  
  
    -   <span data-ttu-id="4077c-114">サイズの大きいメッセージの変換</span><span class="sxs-lookup"><span data-stu-id="4077c-114">Large Message Transforms</span></span>  
  
    -   <span data-ttu-id="4077c-115">インターチェンジごとのメッセージの数が多い</span><span class="sxs-lookup"><span data-stu-id="4077c-115">Large number of messages per interchange</span></span>  
  
    -   <span data-ttu-id="4077c-116">一部のパイプラインやアダプターなどの BTS コンポーネントで高いメモリ使用率</span><span class="sxs-lookup"><span data-stu-id="4077c-116">High memory utilization by some of BTS components, such as pipelines or adapters</span></span>  
  
    -   <span data-ttu-id="4077c-117">EDI などのトランスポート。</span><span class="sxs-lookup"><span data-stu-id="4077c-117">A transport, such as EDI</span></span>  
  
## <a name="when-you-cant-scale-up-the-biztalk-tier"></a><span data-ttu-id="4077c-118">ときに、BizTalk 層をスケールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="4077c-118">When You Can’t Scale Up the BizTalk Tier</span></span>  
  
-   <span data-ttu-id="4077c-119">メッセージ ボックス データベースでは、ボトルネックです。</span><span class="sxs-lookup"><span data-stu-id="4077c-119">The MessageBox database is the bottleneck.</span></span>  
  
-   <span data-ttu-id="4077c-120">アダプターがボトルネックになります。</span><span class="sxs-lookup"><span data-stu-id="4077c-120">An adapter becomes the bottleneck.</span></span> <span data-ttu-id="4077c-121">たとえば、BizTalk の受信者数を増やした後、アダプターを使用する場合ロックの競合を BizTalk アダプターがデータを抽出するバックエンド アプリケーションで増やす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4077c-121">For example, if you are using an adapter, after you increase the number of BizTalk receivers, lock contention might increase on the backend application where the BizTalk adapter is pulling data from.</span></span> <span data-ttu-id="4077c-122">これは、アダプターのスケール アップする能力を制限します。</span><span class="sxs-lookup"><span data-stu-id="4077c-122">This limits your ability to scale up the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4077c-123">参照</span><span class="sxs-lookup"><span data-stu-id="4077c-123">See Also</span></span>  
 <span data-ttu-id="4077c-124">[BizTalk Server 層のスケール アウト](../core/scaling-out-the-biztalk-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="4077c-124">[Scaling Out the BizTalk Server Tier](../core/scaling-out-the-biztalk-server-tier.md) </span></span>  
 <span data-ttu-id="4077c-125">[SQL Server 層のスケール アップ](../core/scaling-up-the-sql-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="4077c-125">[Scaling Up the SQL Server Tier](../core/scaling-up-the-sql-server-tier.md) </span></span>  
 <span data-ttu-id="4077c-126">[SQL Server 層のスケール アウト](../core/scaling-out-the-sql-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="4077c-126">[Scaling Out the SQL Server Tier](../core/scaling-out-the-sql-server-tier.md) </span></span>  
 <span data-ttu-id="4077c-127">[受信ホスト スケール アウト](../core/scaled-out-receiving-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="4077c-127">[Scaled-Out Receiving Hosts](../core/scaled-out-receiving-hosts.md) </span></span>  
 <span data-ttu-id="4077c-128">[スケール アウトされた処理ホスト](../core/scaled-out-processing-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="4077c-128">[Scaled-Out Processing Hosts](../core/scaled-out-processing-hosts.md) </span></span>  
 <span data-ttu-id="4077c-129">[スケール アウトされた送信ホスト](../core/scaled-out-sending-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="4077c-129">[Scaled-Out Sending Hosts](../core/scaled-out-sending-hosts.md) </span></span>  
 <span data-ttu-id="4077c-130">[Windows Server クラスターを使用して BizTalk Server Hosts2 の高可用性を実現するには](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="4077c-130">[Using Windows Server Cluster to Provide High Availability for BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span></span>  
 <span data-ttu-id="4077c-131">[スケール アウト データベース](../core/scaled-out-databases.md) </span><span class="sxs-lookup"><span data-stu-id="4077c-131">[Scaled-Out Databases](../core/scaled-out-databases.md) </span></span>  
 [<span data-ttu-id="4077c-132">BizTalk Server データベースのクラスタリング</span><span class="sxs-lookup"><span data-stu-id="4077c-132">Clustering the BizTalk Server Databases</span></span>](../core/clustering-the-biztalk-server-databases1.md)