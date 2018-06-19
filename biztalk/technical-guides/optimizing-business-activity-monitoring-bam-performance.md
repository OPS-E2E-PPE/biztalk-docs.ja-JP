---
title: ビジネス アクティビティ監視 (BAM) のパフォーマンスを最適化する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c9ed29b2-0be6-4a37-be68-9476832fd49f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83801a4e147b3e1eaf34c5e264d6adecfbdf8f9f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298954"
---
# <a name="optimizing-business-activity-monitoring-bam-performance"></a><span data-ttu-id="cfd13-102">ビジネス アクティビティ監視 (BAM) のパフォーマンスを最適化します。</span><span class="sxs-lookup"><span data-stu-id="cfd13-102">Optimizing Business Activity Monitoring (BAM) Performance</span></span>
<span data-ttu-id="cfd13-103">このトピックでは、ビジネス アクティビティ監視 (BAM) のパフォーマンス要因について説明します。</span><span class="sxs-lookup"><span data-stu-id="cfd13-103">This topic describes Business Activity Monitoring (BAM) performance factors.</span></span>  
  
## <a name="bam-disk-usage-configuration"></a><span data-ttu-id="cfd13-104">BAM のディスク使用量の構成</span><span class="sxs-lookup"><span data-stu-id="cfd13-104">BAM disk usage configuration</span></span>  
 <span data-ttu-id="cfd13-105">BAM では、大量のデータを BAM データベースに保存されているため、BizTalk システムに負荷がときに大幅なオーバーヘッドが発生します。</span><span class="sxs-lookup"><span data-stu-id="cfd13-105">BAM incurs significant overhead when a BizTalk system is under load because of the significant amount of data that is persisted to the BAM database.</span></span> <span data-ttu-id="cfd13-106">したがって、BAM データベースのディスク I/O の手法を賢く利用は非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="cfd13-106">Therefore, judicious use of disk I/O techniques for the BAM database is critically important.</span></span>  
  
## <a name="bam-eventstream-apis"></a><span data-ttu-id="cfd13-107">BAM の EventStream Api</span><span class="sxs-lookup"><span data-stu-id="cfd13-107">BAM EventStream APIs</span></span>  
 <span data-ttu-id="cfd13-108">EventStreams の 4 つの種類は、BizTalk BAM シナリオで使用可能です。</span><span class="sxs-lookup"><span data-stu-id="cfd13-108">Four types of EventStreams are available for use in a BizTalk BAM scenario:</span></span>  
  
-   <span data-ttu-id="cfd13-109">DirectEventStream (DES)</span><span class="sxs-lookup"><span data-stu-id="cfd13-109">DirectEventStream (DES)</span></span>  
  
-   <span data-ttu-id="cfd13-110">BufferedEventStream (BES)</span><span class="sxs-lookup"><span data-stu-id="cfd13-110">BufferedEventStream (BES)</span></span>  
  
-   <span data-ttu-id="cfd13-111">OrchestrationEventStream (OES)</span><span class="sxs-lookup"><span data-stu-id="cfd13-111">OrchestrationEventStream (OES)</span></span>  
  
-   <span data-ttu-id="cfd13-112">MessageEventStream (MES)</span><span class="sxs-lookup"><span data-stu-id="cfd13-112">MessageEventStream (MES)</span></span>  
  
 <span data-ttu-id="cfd13-113">次の要因に基づくこれらの Api のいずれかを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfd13-113">You should choose one of these APIs based on the following factors:</span></span>  
  
-   <span data-ttu-id="cfd13-114">待機時間を重視する場合は DES を選択します。DES では、データが BAM プライマリ インポート データベースと同期された状態で保持されます。</span><span class="sxs-lookup"><span data-stu-id="cfd13-114">If your concern is latency, choose DES, where data is persisted synchronously to the BAM Primary Import database.</span></span>  
  
-   <span data-ttu-id="cfd13-115">重視する場合はパフォーマンスとイベント挿入のスループット、非同期 API (BES、OES または MES) を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfd13-115">If your concern is performance and throughput of event insertion, choose an asynchronous API (BES, OES or MES).</span></span>  
  
-   <span data-ttu-id="cfd13-116">BizTalk Server がインストールされてがないコンピューターで実行されるアプリケーションを作成している場合、DES および BES; を使用します。これらの Api は、非 BizTalk アプリケーションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="cfd13-116">If you are writing an application that runs on a computer that does not have BizTalk Server installed, use DES and BES; these APIs can be used in non-BizTalk applications.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cfd13-117">シナリオによっては、複数種類の EventStream を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfd13-117">There are scenarios in which you may want to mix EventStream types.</span></span> <span data-ttu-id="cfd13-118">たとえば、パイプライン処理でのかどうか、パイプラインはロールバック、トランザクションに関係なく、BAM で特定のデータをキャプチャすることがあります。</span><span class="sxs-lookup"><span data-stu-id="cfd13-118">For example, for pipeline processing, you may want to capture the particular data in BAM regardless of whether the pipeline is rolling back its transaction.</span></span> <span data-ttu-id="cfd13-119">具体的には、失敗したメッセージの数に関するデータの取得または回数がパイプライン処理中に発生したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="cfd13-119">In particular, you may want capture data about how many messages failed or how many retries occurred during pipeline processing.</span></span> <span data-ttu-id="cfd13-120">この状況でデータを取得するには、BES を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfd13-120">To capture the data in this situation you should use BES.</span></span>  
  
-   <span data-ttu-id="cfd13-121">BizTalk Server がインストールされているコンピューターでアプリケーションを実行する場合は、MES および OES を使用します </span><span class="sxs-lookup"><span data-stu-id="cfd13-121">If your application runs on a computer on which BizTalk Server is installed, use MES and OES.</span></span> <span data-ttu-id="cfd13-122">(これらの API は BizTalk アプリケーションでのみ使用できます)。</span><span class="sxs-lookup"><span data-stu-id="cfd13-122">(These APIs are available only from BizTalk applications.)</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cfd13-123">OES は MES と同等ですが、BizTalk オーケストレーションを対象としています。</span><span class="sxs-lookup"><span data-stu-id="cfd13-123">OES is the equivalent of MES but for BizTalk orchestrations.</span></span>  
  
-   <span data-ttu-id="cfd13-124">パイプライン トランザクションと同期する BAM イベントの永続化する場合は、メッセージング イベント ストリーム (MES) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfd13-124">If you want BAM event persistence to be in sync with pipeline transaction, you should use a Messaging Event Stream (MES).</span></span>  
  
 <span data-ttu-id="cfd13-125">すべて、非同期 EventStreams (BES、MES、OES) は、BizTalk メッセージ ボックス データベースに最初のデータを保持します。</span><span class="sxs-lookup"><span data-stu-id="cfd13-125">All the asynchronous EventStreams (BES, MES, and OES) persist data first to the BizTalk MessageBox database.</span></span> <span data-ttu-id="cfd13-126">このデータは Tracking Data Decode Service (TDDS) によって定期的に処理され、BAM プライマリ インポート データベースに保存されます。</span><span class="sxs-lookup"><span data-stu-id="cfd13-126">Periodically the data is processed and persisted to the BAM Primary Import database by the Tracking Data Decode Service (TDDS).</span></span>  
  
 <span data-ttu-id="cfd13-127">BAM の EventStream Api の詳細については、次を参照してください。 [EventStream クラス](http://go.microsoft.com/fwlink/?LinkId=158046)(http://go.microsoft.com/fwlink/?LinkId=158046)、BizTalk Server のドキュメントにします。</span><span class="sxs-lookup"><span data-stu-id="cfd13-127">For more information about the BAM EventStream APIs, see [EventStream Classes](http://go.microsoft.com/fwlink/?LinkId=158046) (http://go.microsoft.com/fwlink/?LinkId=158046) in the BizTalk Server documentation.</span></span>  
  
## <a name="bam-performance-counters"></a><span data-ttu-id="cfd13-128">BAM パフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="cfd13-128">BAM performance counters</span></span>  
 <span data-ttu-id="cfd13-129">BAM のパフォーマンス カウンターの詳細な一覧についてを参照してください。 [BAM パフォーマンス カウンター](http://go.microsoft.com/fwlink/?LinkId=158048) (http://go.microsoft.com/fwlink/?LinkId=158048)、BizTalk Server のドキュメントにします。</span><span class="sxs-lookup"><span data-stu-id="cfd13-129">For a detailed list of the performance counters for BAM, see [BAM Performance Counters](http://go.microsoft.com/fwlink/?LinkId=158048) (http://go.microsoft.com/fwlink/?LinkId=158048) in the BizTalk Server documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfd13-130">参照</span><span class="sxs-lookup"><span data-stu-id="cfd13-130">See Also</span></span>  
 [<span data-ttu-id="cfd13-131">BizTalk Server のパフォーマンスを最適化します。</span><span class="sxs-lookup"><span data-stu-id="cfd13-131">Optimizing BizTalk Server Performance</span></span>](../technical-guides/optimizing-biztalk-server-performance.md)