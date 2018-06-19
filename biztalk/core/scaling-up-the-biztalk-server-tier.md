---
title: BizTalk Server 層のスケール アップ |Microsoft ドキュメント
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
ms.openlocfilehash: d55176072cd33e20dd1024bf2d9d1c39bca4567a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270138"
---
# <a name="scaling-up-the-biztalk-server-tier"></a><span data-ttu-id="e887a-102">BizTalk Server 層のスケール アップ</span><span class="sxs-lookup"><span data-stu-id="e887a-102">Scaling Up the BizTalk Server Tier</span></span>
<span data-ttu-id="e887a-103">BizTalk 層をスケール アップするには、CPU、メモリ、I/O、およびその他のリソースをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="e887a-103">To scale up the BizTalk tier, you upgrade the CPU, memory, IO and other resources.</span></span> <span data-ttu-id="e887a-104">次の図は、BizTalk 層を 2 台のプロセッサを搭載したコンピューターから 4 台のプロセッサを搭載したコンピューターにスケール アップする方法の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="e887a-104">The following figure shows an example of how you might scale up the BizTalk tier from a two processor computer to a four processor computer.</span></span>  
  
 <span data-ttu-id="e887a-105">![スケール &#45; 最大 BTS](../core/media/scaleupbts.gif "ScaleUpBTS")</span><span class="sxs-lookup"><span data-stu-id="e887a-105">![Scale&#45;up BTS](../core/media/scaleupbts.gif "ScaleUpBTS")</span></span>  
  
 <span data-ttu-id="e887a-106">BizTalk 層のスケール アップのシナリオは、スケール アウトを選択したときのシナリオに似ています。</span><span class="sxs-lookup"><span data-stu-id="e887a-106">The scenarios for scaling up your BizTalk tier are similar to when you choose to scale out:</span></span>  
  
-   <span data-ttu-id="e887a-107">BizTalk Server がボトルネックになります。</span><span class="sxs-lookup"><span data-stu-id="e887a-107">BizTalk Server becomes a bottleneck.</span></span> <span data-ttu-id="e887a-108">ボトルネックは、次のいずれかの問題によって引き起こされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e887a-108">The bottleneck itself may be caused by one of the following problems:</span></span>  
  
-   <span data-ttu-id="e887a-109">CPU: CPU を集中的に使用するパイプライン、マップ、またはオーケストレーションをシナリオで使用する場合に、BizTalk Server に余分な CPU ヘッドルームがない。</span><span class="sxs-lookup"><span data-stu-id="e887a-109">CPU: If the scenario uses CPU intensive pipelines, maps, or orchestrations, the BizTalk servers will not have any extra CPU headroom.</span></span>  
  
-   <span data-ttu-id="e887a-110">メモリおよび I/O: 既存のコンピューターでメモリおよび I/O の最大値に達した場合は、コンピューターをアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e887a-110">Memory and I/O: If the existing computers have reached their maximum limit on memory and IO, and the computer needs to be upgraded.</span></span>  
  
-   <span data-ttu-id="e887a-111">スケール アウトは、非常にコストがかかります。</span><span class="sxs-lookup"><span data-stu-id="e887a-111">Scaling out is too expensive.</span></span>  
  
-   <span data-ttu-id="e887a-112">スケールアウトしてもボトルネックが改善されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="e887a-112">If scale-out does not address the bottleneck.</span></span> <span data-ttu-id="e887a-113">たとえば、次のボトルネックはスケール アウトでは改善されません。</span><span class="sxs-lookup"><span data-stu-id="e887a-113">For example, scaling out does not address the following bottlenecks:</span></span>  
  
    -   <span data-ttu-id="e887a-114">サイズの大きいメッセージを変換する。</span><span class="sxs-lookup"><span data-stu-id="e887a-114">Large Message Transforms</span></span>  
  
    -   <span data-ttu-id="e887a-115">1 回のインターチェンジに多数のメッセージを処理する。</span><span class="sxs-lookup"><span data-stu-id="e887a-115">Large number of messages per interchange</span></span>  
  
    -   <span data-ttu-id="e887a-116">パイプラインやアダプターなど、一部の BTS コンポーネントで多くのメモリを使用する。</span><span class="sxs-lookup"><span data-stu-id="e887a-116">High memory utilization by some of BTS components, such as pipelines or adapters</span></span>  
  
    -   <span data-ttu-id="e887a-117">EDI などのトランスポート。</span><span class="sxs-lookup"><span data-stu-id="e887a-117">A transport, such as EDI</span></span>  
  
## <a name="when-you-cant-scale-up-the-biztalk-tier"></a><span data-ttu-id="e887a-118">BizTalk 層をスケール アップできないケース</span><span class="sxs-lookup"><span data-stu-id="e887a-118">When You Can’t Scale Up the BizTalk Tier</span></span>  
  
-   <span data-ttu-id="e887a-119">メッセージ ボックス データベースがボトルネックの場合。</span><span class="sxs-lookup"><span data-stu-id="e887a-119">The MessageBox database is the bottleneck.</span></span>  
  
-   <span data-ttu-id="e887a-120">アダプターがボトルネックになる場合。</span><span class="sxs-lookup"><span data-stu-id="e887a-120">An adapter becomes the bottleneck.</span></span> <span data-ttu-id="e887a-121">たとえば、BizTalk の受信者数を増やした後、アダプターを使用している、ロックの競合が、BizTalk アダプターがデータを抽出するバックエンド アプリケーションで高まる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e887a-121">For example, if you are using an adapter, after you increase the number of BizTalk receivers, lock contention might increase on the backend application where the BizTalk adapter is pulling data from.</span></span> <span data-ttu-id="e887a-122">このため、アダプターのスケール アップが制限されます。</span><span class="sxs-lookup"><span data-stu-id="e887a-122">This limits your ability to scale up the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e887a-123">参照</span><span class="sxs-lookup"><span data-stu-id="e887a-123">See Also</span></span>  
 <span data-ttu-id="e887a-124">[BizTalk Server 層のスケール アウト](../core/scaling-out-the-biztalk-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="e887a-124">[Scaling Out the BizTalk Server Tier](../core/scaling-out-the-biztalk-server-tier.md) </span></span>  
 <span data-ttu-id="e887a-125">[SQL Server 層のスケール アップ](../core/scaling-up-the-sql-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="e887a-125">[Scaling Up the SQL Server Tier](../core/scaling-up-the-sql-server-tier.md) </span></span>  
 <span data-ttu-id="e887a-126">[SQL Server 層のスケール アウト](../core/scaling-out-the-sql-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="e887a-126">[Scaling Out the SQL Server Tier](../core/scaling-out-the-sql-server-tier.md) </span></span>  
 <span data-ttu-id="e887a-127">[スケール アウト受信ホスト](../core/scaled-out-receiving-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="e887a-127">[Scaled-Out Receiving Hosts](../core/scaled-out-receiving-hosts.md) </span></span>  
 <span data-ttu-id="e887a-128">[スケール アウトされた処理ホスト](../core/scaled-out-processing-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="e887a-128">[Scaled-Out Processing Hosts](../core/scaled-out-processing-hosts.md) </span></span>  
 <span data-ttu-id="e887a-129">[スケール アウトされた送信ホスト](../core/scaled-out-sending-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="e887a-129">[Scaled-Out Sending Hosts](../core/scaled-out-sending-hosts.md) </span></span>  
 <span data-ttu-id="e887a-130">[Windows Server クラスターを使用して BizTalk Server Hosts2 の高可用性を実現するには](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="e887a-130">[Using Windows Server Cluster to Provide High Availability for BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span></span>  
 <span data-ttu-id="e887a-131">[スケール アウト データベース](../core/scaled-out-databases.md) </span><span class="sxs-lookup"><span data-stu-id="e887a-131">[Scaled-Out Databases](../core/scaled-out-databases.md) </span></span>  
 [<span data-ttu-id="e887a-132">BizTalk Server データベースをクラスタ リング</span><span class="sxs-lookup"><span data-stu-id="e887a-132">Clustering the BizTalk Server Databases</span></span>](../core/clustering-the-biztalk-server-databases1.md)