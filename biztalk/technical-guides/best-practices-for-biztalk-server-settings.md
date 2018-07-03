---
title: BizTalk Server 設定のベスト プラクティス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e62024e1-f502-45a8-932f-edd8460bcf5f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 461e2e1a4256d79112e4eec94047c25df34a4511
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001122"
---
# <a name="best-practices-for-biztalk-server-settings"></a><span data-ttu-id="73180-102">BizTalk Server 設定のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="73180-102">Best Practices for BizTalk Server Settings</span></span>
<span data-ttu-id="73180-103">このトピックでの運用準備の手順を実行する際に従う必要のあるベスト プラクティス[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="73180-103">This topic lists best practices that you should follow as you perform operational readiness procedures for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="73180-104">**アダプターのパフォーマンスを向上させるメッセージのバッチ処理を構成します。**</span><span class="sxs-lookup"><span data-stu-id="73180-104">**Configure message batching to increase adapter performance**</span></span>  
  
- <span data-ttu-id="73180-105">1 つのバッチには、複数の操作を組み合わせることで、アダプターによって実行されるトランザクションの数を最小限に抑えます。</span><span class="sxs-lookup"><span data-stu-id="73180-105">Minimize the number of transactions performed by an adapter by combining more than one operation into a single batch.</span></span>  
  
- <span data-ttu-id="73180-106">メッセージの数だけでなく、バッチ内のバイトの合計数に基づいてバッチ サイズを制限します。</span><span class="sxs-lookup"><span data-stu-id="73180-106">Limit the batch size based on the total number of bytes in the batch, in addition to message count.</span></span> <span data-ttu-id="73180-107">バッチ サイズの制限の詳細については、次を参照してください。[アダプターのパフォーマンスを向上させるバッチ処理構成](../technical-guides/configuring-batching-to-improve-adapter-performance.md)します。</span><span class="sxs-lookup"><span data-stu-id="73180-107">For more information about limiting the batch size, see [Configuring Batching to Improve Adapter Performance](../technical-guides/configuring-batching-to-improve-adapter-performance.md).</span></span>  
  
  <span data-ttu-id="73180-108">**サイズの大きいメッセージのしきい値を調整します。**</span><span class="sxs-lookup"><span data-stu-id="73180-108">**Adjust the large message threshold**</span></span>  
  
- <span data-ttu-id="73180-109">スループットを向上させるのにはバッファー サイズの大きいメッセージの数の削減サイズの大きいメッセージのしきい値を増やすマッピング中にディスクにします。</span><span class="sxs-lookup"><span data-stu-id="73180-109">To improve throughput, increase the large message threshold, which lowers the number of large messages that are buffered to disk during mapping.</span></span>  
  
  <span data-ttu-id="73180-110">**計画時に追跡する必要がある情報を決定します。**</span><span class="sxs-lookup"><span data-stu-id="73180-110">**Determine the information you need to track during planning**</span></span>  
  
- <span data-ttu-id="73180-111">計画段階中には、追跡する必要がある情報を決定する必要があります。これにより、プロジェクトを配置した後に追跡オプションを設定して必要な情報のみを付与する追跡データの量を制限します。</span><span class="sxs-lookup"><span data-stu-id="73180-111">You should decide during the planning stages which information you need to track. This way, after you deploy the project, you can set the tracking options and limit the amount of tracked data to give you only the information you need.</span></span>  
  
  > [!NOTE]  
  >  <span data-ttu-id="73180-112">追跡に関連するベスト プラクティスの詳細については、次を参照してください。[追跡の計画](../technical-guides/planning-for-tracking.md)このガイドと[状態と動作状況の追跡](http://go.microsoft.com/fwlink/p/?LinkId=154187)(http://go.microsoft.com/fwlink/p/?LinkId=154187)します。</span><span class="sxs-lookup"><span data-stu-id="73180-112">For more information about best practices related to tracking, see [Planning for Tracking](../technical-guides/planning-for-tracking.md) in this guide and [Health and Activity Tracking](http://go.microsoft.com/fwlink/p/?LinkId=154187) (http://go.microsoft.com/fwlink/p/?LinkId=154187).</span></span>  
  
  <span data-ttu-id="73180-113">**すべてのメッセージを追跡しません。**</span><span class="sxs-lookup"><span data-stu-id="73180-113">**Do not track all messages**</span></span>  
  
- <span data-ttu-id="73180-114">すべてのメッセージを追跡しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="73180-114">We recommend that you not track all messages.</span></span> <span data-ttu-id="73180-115">これは、メッセージにアクセスするたびに BizTalk Server がメッセージの別のコピーを作成するためです。</span><span class="sxs-lookup"><span data-stu-id="73180-115">This is because each time a message is touched, BizTalk Server makes another copy of the message.</span></span> <span data-ttu-id="73180-116">代わりに、特定のポートだけを追跡することによって、スコープを限定できます。</span><span class="sxs-lookup"><span data-stu-id="73180-116">You can instead narrow the scope by tracking only a specific port.</span></span> <span data-ttu-id="73180-117">これにより、システムのパフォーマンスを最大化して、データベースをきちんと整頓します。</span><span class="sxs-lookup"><span data-stu-id="73180-117">This helps to maximize the performance of your system and to keep the databases uncluttered.</span></span>  
  
  <span data-ttu-id="73180-118">**送信ポートの追跡を設定し、受信パイプラインでの代わりにポート**</span><span class="sxs-lookup"><span data-stu-id="73180-118">**Set tracking on send ports and receive ports instead of on a pipeline**</span></span>  
  
- <span data-ttu-id="73180-119">パイプラインに追跡オプションを設定した場合は、パイプラインを使用するすべてのポートに対してグローバルに追跡オプションも設定します。</span><span class="sxs-lookup"><span data-stu-id="73180-119">If you set tracking options on pipelines, you will also set the tracking options globally for every port that uses the pipeline.</span></span> <span data-ttu-id="73180-120">これは、さらに可能性より多くのデータが意図したものと、追跡されているシステムのパフォーマンスが低下します。</span><span class="sxs-lookup"><span data-stu-id="73180-120">This in turn may result in far more data being tracked than you intend, which will slow system performance.</span></span> <span data-ttu-id="73180-121">代わりに、ポートの送信に追跡オプションを設定して、ポートを受信できます。</span><span class="sxs-lookup"><span data-stu-id="73180-121">Instead, you can set tracking options on send ports and receive ports.</span></span>  
  
  <span data-ttu-id="73180-122">**リソース使用率に基づく制限を調整します。**</span><span class="sxs-lookup"><span data-stu-id="73180-122">**Adjust throttling based on resource utilization**</span></span>  
  
- <span data-ttu-id="73180-123">スロットル[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]既定では、システムの適切な保護を提供するように構成します。</span><span class="sxs-lookup"><span data-stu-id="73180-123">Throttling in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is configured by default to provide good protection for the system.</span></span> <span data-ttu-id="73180-124">制限の調整が実行を表示する状態のパフォーマンス カウンターを監視します。</span><span class="sxs-lookup"><span data-stu-id="73180-124">Monitor the performance counters for throttling states to see if throttling is taking place.</span></span> <span data-ttu-id="73180-125">自分のゲージでスロットルを適用するリソースが基づいている場合 (たとえば、データベースのサイズまたはメモリ使用率) はまたはの上に使用します。</span><span class="sxs-lookup"><span data-stu-id="73180-125">Then gauge for yourself if the resource on which throttling is based (for example, database size or memory usage) is under or over utilized.</span></span> <span data-ttu-id="73180-126">次に、調整、調整のしきい値は切り上げまたは切り捨てです。</span><span class="sxs-lookup"><span data-stu-id="73180-126">Next, adjust the throttling thresholds up or down accordingly.</span></span> <span data-ttu-id="73180-127">詳細については、次を参照してください。[制限のしきい値の調整: タイミングと理由](http://go.microsoft.com/fwlink/p/?LinkId=154188)(<http://go.microsoft.com/fwlink/p/?LinkId=154188>)。</span><span class="sxs-lookup"><span data-stu-id="73180-127">For more information, see [Adjusting Throttling Thresholds: When and Why](http://go.microsoft.com/fwlink/p/?LinkId=154188) (<http://go.microsoft.com/fwlink/p/?LinkId=154188>).</span></span>  
  
  <span data-ttu-id="73180-128">**可能であれば、PassThruTransmit パイプラインを使用します。**</span><span class="sxs-lookup"><span data-stu-id="73180-128">**Use the PassThruTransmit pipeline if possible**</span></span>  
  
- <span data-ttu-id="73180-129">場合は、宛先にメッセージを送信する前にドキュメントの処理は必要ありませんが、XML 送信パイプラインではなく PassThruTransmit パイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="73180-129">If no document processing is required before sending a message to its destination, use the PassThruTransmit pipeline instead of the XML send pipeline.</span></span>  
  
  <span data-ttu-id="73180-130">**オーケストレーション「図形の開始と終了」の使用量を最小限に抑えるイベントの追跡**</span><span class="sxs-lookup"><span data-stu-id="73180-130">**Minimize usage of orchestration “Shape start and end” tracking events**</span></span>  
  
- <span data-ttu-id="73180-131">オーケストレーション図形の追跡には、オーケストレーションのデバッグの明らかな利点がありますが、パフォーマンスとスケーラビリティに影響があります。</span><span class="sxs-lookup"><span data-stu-id="73180-131">While orchestration shape tracking has obvious benefits for orchestration debugging, it has performance and scalability implications.</span></span> <span data-ttu-id="73180-132">**図形の開始と終了**追跡イベント大きなオーバーヘッドが発生することができます。</span><span class="sxs-lookup"><span data-stu-id="73180-132">The **Shape start and end** tracking event can cause significant overhead.</span></span> <span data-ttu-id="73180-133">高スループットが必要な場合、運用環境におけるその使用を最小限に抑えることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="73180-133">It is best to minimize its usage in production environments where high throughput is necessary.</span></span>  
  
  > [!NOTE]  
  >  <span data-ttu-id="73180-134">**図形の開始と終了**追跡イベントはすべてのオーケストレーションでは、既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="73180-134">**Shape start and end** tracking events are ENABLED by default on all orchestrations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73180-135">参照</span><span class="sxs-lookup"><span data-stu-id="73180-135">See Also</span></span>  
 [<span data-ttu-id="73180-136">チェックリスト: BizTalk Server の構成</span><span class="sxs-lookup"><span data-stu-id="73180-136">Checklist: Configuring BizTalk Server</span></span>](../technical-guides/checklist-configuring-biztalk-server.md)