---
title: "BizTalk Server 設定のベスト プラクティス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e62024e1-f502-45a8-932f-edd8460bcf5f
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf1f89ced33be6f10ceaae37ccb2c899c4e01eac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="best-practices-for-biztalk-server-settings"></a><span data-ttu-id="abe23-102">BizTalk Server 設定のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="abe23-102">Best Practices for BizTalk Server Settings</span></span>
<span data-ttu-id="abe23-103">このトピックの運用の準備手順を実行する際に従う必要のあるベスト プラクティスの一覧[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="abe23-103">This topic lists best practices that you should follow as you perform operational readiness procedures for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="abe23-104">**アダプターのパフォーマンスを向上させるメッセージのバッチ処理を構成します。**</span><span class="sxs-lookup"><span data-stu-id="abe23-104">**Configure message batching to increase adapter performance**</span></span>  
  
-   <span data-ttu-id="abe23-105">単一のバッチに 1 つ以上の操作を組み合わせることによって、アダプターによって実行されたトランザクションの数を最小限に抑えます。</span><span class="sxs-lookup"><span data-stu-id="abe23-105">Minimize the number of transactions performed by an adapter by combining more than one operation into a single batch.</span></span>  
  
-   <span data-ttu-id="abe23-106">メッセージの数だけでなく、バッチ内のバイトの合計数に基づいてバッチ サイズを制限します。</span><span class="sxs-lookup"><span data-stu-id="abe23-106">Limit the batch size based on the total number of bytes in the batch, in addition to message count.</span></span> <span data-ttu-id="abe23-107">バッチ サイズの制限の詳細については、次を参照してください。[アダプターのパフォーマンスを向上させるバッチ処理構成](../technical-guides/configuring-batching-to-improve-adapter-performance.md)です。</span><span class="sxs-lookup"><span data-stu-id="abe23-107">For more information about limiting the batch size, see [Configuring Batching to Improve Adapter Performance](../technical-guides/configuring-batching-to-improve-adapter-performance.md).</span></span>  
  
 <span data-ttu-id="abe23-108">**サイズの大きいメッセージのしきい値を調整します。**</span><span class="sxs-lookup"><span data-stu-id="abe23-108">**Adjust the large message threshold**</span></span>  
  
-   <span data-ttu-id="abe23-109">スループットを向上させるのにはバッファーに格納されるサイズの大きいメッセージの数を減らすことがサイズの大きいメッセージのしきい値を増やすマッピング中にディスクにします。</span><span class="sxs-lookup"><span data-stu-id="abe23-109">To improve throughput, increase the large message threshold, which lowers the number of large messages that are buffered to disk during mapping.</span></span>  
  
 <span data-ttu-id="abe23-110">**計画時に追跡するために必要な情報を決定します。**</span><span class="sxs-lookup"><span data-stu-id="abe23-110">**Determine the information you need to track during planning**</span></span>  
  
-   <span data-ttu-id="abe23-111">計画段階中には、追跡する必要があります。 情報を決定する必要があります。このように、プロジェクトを配置した後に追跡オプションを設定できに必要な情報のみを付与する追跡データの量を制限できます。</span><span class="sxs-lookup"><span data-stu-id="abe23-111">You should decide during the planning stages which information you need to track. This way, after you deploy the project, you can set the tracking options and limit the amount of tracked data to give you only the information you need.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="abe23-112">追跡に関連するベスト プラクティスに関する詳細については、次を参照してください。[追跡の計画](../technical-guides/planning-for-tracking.md)このガイドでと[状態と動作状況の追跡](http://go.microsoft.com/fwlink/p/?LinkId=154187)(http://go.microsoft.com/fwlink/p/?LinkId=154187)。</span><span class="sxs-lookup"><span data-stu-id="abe23-112">For more information about best practices related to tracking, see [Planning for Tracking](../technical-guides/planning-for-tracking.md) in this guide and [Health and Activity Tracking](http://go.microsoft.com/fwlink/p/?LinkId=154187) (http://go.microsoft.com/fwlink/p/?LinkId=154187).</span></span>  
  
 <span data-ttu-id="abe23-113">**すべてのメッセージを追跡しません。**</span><span class="sxs-lookup"><span data-stu-id="abe23-113">**Do not track all messages**</span></span>  
  
-   <span data-ttu-id="abe23-114">いないすべてのメッセージを追跡することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="abe23-114">We recommend that you not track all messages.</span></span> <span data-ttu-id="abe23-115">メッセージの影響を受けるたびに BizTalk Server がメッセージの別のコピーを作成するためです。</span><span class="sxs-lookup"><span data-stu-id="abe23-115">This is because each time a message is touched, BizTalk Server makes another copy of the message.</span></span> <span data-ttu-id="abe23-116">特定のポートのみを追跡すると、代わりにスコープを絞ることができます。</span><span class="sxs-lookup"><span data-stu-id="abe23-116">You can instead narrow the scope by tracking only a specific port.</span></span> <span data-ttu-id="abe23-117">これにより、システムのパフォーマンスを最大限にし、データベースをきちんと整頓します。</span><span class="sxs-lookup"><span data-stu-id="abe23-117">This helps to maximize the performance of your system and to keep the databases uncluttered.</span></span>  
  
 <span data-ttu-id="abe23-118">**送信ポートの追跡を設定し、受信パイプラインでの代わりにポート**</span><span class="sxs-lookup"><span data-stu-id="abe23-118">**Set tracking on send ports and receive ports instead of on a pipeline**</span></span>  
  
-   <span data-ttu-id="abe23-119">パイプラインに追跡オプションを設定すると、パイプラインを使用するすべてのポートに対してグローバルに追跡オプションも設定されます。</span><span class="sxs-lookup"><span data-stu-id="abe23-119">If you set tracking options on pipelines, you will also set the tracking options globally for every port that uses the pipeline.</span></span> <span data-ttu-id="abe23-120">これは、順番が原因でより多くのデータが意図したものと追跡されているシステムのパフォーマンスが低下します。</span><span class="sxs-lookup"><span data-stu-id="abe23-120">This in turn may result in far more data being tracked than you intend, which will slow system performance.</span></span> <span data-ttu-id="abe23-121">代わりに、ポートの送信に追跡オプションを設定し、ポートを受信できます。</span><span class="sxs-lookup"><span data-stu-id="abe23-121">Instead, you can set tracking options on send ports and receive ports.</span></span>  
  
 <span data-ttu-id="abe23-122">**リソース使用率に基づいた制限を調整します。**</span><span class="sxs-lookup"><span data-stu-id="abe23-122">**Adjust throttling based on resource utilization**</span></span>  
  
-   <span data-ttu-id="abe23-123">調整[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]既定では、システムの適切な保護を提供するように構成します。</span><span class="sxs-lookup"><span data-stu-id="abe23-123">Throttling in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is configured by default to provide good protection for the system.</span></span> <span data-ttu-id="abe23-124">調整が実行を表示する状態の調整のパフォーマンス カウンターを監視します。</span><span class="sxs-lookup"><span data-stu-id="abe23-124">Monitor the performance counters for throttling states to see if throttling is taking place.</span></span> <span data-ttu-id="abe23-125">調整上のリソースが基づいている場合を各自で判断し、(たとえば、データベースのサイズまたはメモリ使用率) を下にある、または経由で利用できます。</span><span class="sxs-lookup"><span data-stu-id="abe23-125">Then gauge for yourself if the resource on which throttling is based (for example, database size or memory usage) is under or over utilized.</span></span> <span data-ttu-id="abe23-126">次に、調整、調整のしきい値が切り上げまたは切り捨てです。</span><span class="sxs-lookup"><span data-stu-id="abe23-126">Next, adjust the throttling thresholds up or down accordingly.</span></span> <span data-ttu-id="abe23-127">詳細については、次を参照してください。[制限のしきい値の調整: タイミングと理由](http://go.microsoft.com/fwlink/p/?LinkId=154188)(http://go.microsoft.com/fwlink/p/?LinkId=154188)。</span><span class="sxs-lookup"><span data-stu-id="abe23-127">For more information, see [Adjusting Throttling Thresholds: When and Why](http://go.microsoft.com/fwlink/p/?LinkId=154188) (http://go.microsoft.com/fwlink/p/?LinkId=154188).</span></span>  
  
 <span data-ttu-id="abe23-128">**可能であれば、PassThruTransmit パイプラインを使用します。**</span><span class="sxs-lookup"><span data-stu-id="abe23-128">**Use the PassThruTransmit pipeline if possible**</span></span>  
  
-   <span data-ttu-id="abe23-129">宛先にメッセージを送信する前に、ドキュメント処理は必要ありません、XML 送信パイプラインではなく、PassThruTransmit パイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="abe23-129">If no document processing is required before sending a message to its destination, use the PassThruTransmit pipeline instead of the XML send pipeline.</span></span>  
  
 <span data-ttu-id="abe23-130">**オーケストレーション「図形の開始と終了」の使用量を最小限に抑えるイベントの追跡**</span><span class="sxs-lookup"><span data-stu-id="abe23-130">**Minimize usage of orchestration “Shape start and end” tracking events**</span></span>  
  
-   <span data-ttu-id="abe23-131">オーケストレーション図形の追跡には、オーケストレーションをデバッグするための明らかな利点がありますが、パフォーマンスとスケーラビリティの問題があります。</span><span class="sxs-lookup"><span data-stu-id="abe23-131">While orchestration shape tracking has obvious benefits for orchestration debugging, it has performance and scalability implications.</span></span> <span data-ttu-id="abe23-132">**図形の開始と終了**追跡イベントと、大きなオーバーヘッドが発生することができます。</span><span class="sxs-lookup"><span data-stu-id="abe23-132">The **Shape start and end** tracking event can cause significant overhead.</span></span> <span data-ttu-id="abe23-133">高いスループットが必要な実稼働環境での使用率を最小限に抑えることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="abe23-133">It is best to minimize its usage in production environments where high throughput is necessary.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="abe23-134">**図形の開始と終了**追跡イベントがすべてのオーケストレーションでは既定で有効にします。</span><span class="sxs-lookup"><span data-stu-id="abe23-134">**Shape start and end** tracking events are ENABLED by default on all orchestrations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abe23-135">参照</span><span class="sxs-lookup"><span data-stu-id="abe23-135">See Also</span></span>  
 [<span data-ttu-id="abe23-136">チェックリスト: BizTalk Server を構成します。</span><span class="sxs-lookup"><span data-stu-id="abe23-136">Checklist: Configuring BizTalk Server</span></span>](../technical-guides/checklist-configuring-biztalk-server.md)