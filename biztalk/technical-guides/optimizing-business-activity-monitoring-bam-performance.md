---
title: ビジネス アクティビティ監視 (BAM) のパフォーマンスの最適化 |Microsoft Docs
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
ms.openlocfilehash: 2df07372e17d93ae458f3831401bec4979725173
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400728"
---
# <a name="optimizing-business-activity-monitoring-bam-performance"></a><span data-ttu-id="d5696-102">ビジネス アクティビティ監視 (BAM) のパフォーマンスを最適化します。</span><span class="sxs-lookup"><span data-stu-id="d5696-102">Optimizing Business Activity Monitoring (BAM) Performance</span></span>
<span data-ttu-id="d5696-103">このトピックでは、ビジネス アクティビティ監視 (BAM) のパフォーマンス要因について説明します。</span><span class="sxs-lookup"><span data-stu-id="d5696-103">This topic describes Business Activity Monitoring (BAM) performance factors.</span></span>  
  
## <a name="bam-disk-usage-configuration"></a><span data-ttu-id="d5696-104">BAM のディスク使用率の構成</span><span class="sxs-lookup"><span data-stu-id="d5696-104">BAM disk usage configuration</span></span>  
 <span data-ttu-id="d5696-105">BAM では、BizTalk システムが原因で BAM データベースに保存されているデータ量の大きな負荷がときに大きなオーバーヘッドが発生します。</span><span class="sxs-lookup"><span data-stu-id="d5696-105">BAM incurs significant overhead when a BizTalk system is under load because of the significant amount of data that is persisted to the BAM database.</span></span> <span data-ttu-id="d5696-106">そのため、BAM データベースのディスク I/O の手法を賢く利用は、非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="d5696-106">Therefore, judicious use of disk I/O techniques for the BAM database is critically important.</span></span>  
  
## <a name="bam-eventstream-apis"></a><span data-ttu-id="d5696-107">BAM の EventStream Api</span><span class="sxs-lookup"><span data-stu-id="d5696-107">BAM EventStream APIs</span></span>  
 <span data-ttu-id="d5696-108">BizTalk BAM シナリオで使用するため EventStreams の 4 種類があります。</span><span class="sxs-lookup"><span data-stu-id="d5696-108">Four types of EventStreams are available for use in a BizTalk BAM scenario:</span></span>  
  
- <span data-ttu-id="d5696-109">DirectEventStream (DES)</span><span class="sxs-lookup"><span data-stu-id="d5696-109">DirectEventStream (DES)</span></span>  
  
- <span data-ttu-id="d5696-110">BufferedEventStream (BES)</span><span class="sxs-lookup"><span data-stu-id="d5696-110">BufferedEventStream (BES)</span></span>  
  
- <span data-ttu-id="d5696-111">OrchestrationEventStream (OES)</span><span class="sxs-lookup"><span data-stu-id="d5696-111">OrchestrationEventStream (OES)</span></span>  
  
- <span data-ttu-id="d5696-112">MessageEventStream (MES)</span><span class="sxs-lookup"><span data-stu-id="d5696-112">MessageEventStream (MES)</span></span>  
  
  <span data-ttu-id="d5696-113">次の要因に基づくこれらの Api のいずれかを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5696-113">You should choose one of these APIs based on the following factors:</span></span>  
  
- <span data-ttu-id="d5696-114">待機時間を重視する場合は DES を選択します。DES では、データが BAM プライマリ インポート データベースと同期された状態で保持されます。</span><span class="sxs-lookup"><span data-stu-id="d5696-114">If your concern is latency, choose DES, where data is persisted synchronously to the BAM Primary Import database.</span></span>  
  
- <span data-ttu-id="d5696-115">イベント挿入のパフォーマンスとスループット、問題がある場合は、非同期 API (BES、OES または MES) を選択します。</span><span class="sxs-lookup"><span data-stu-id="d5696-115">If your concern is performance and throughput of event insertion, choose an asynchronous API (BES, OES or MES).</span></span>  
  
- <span data-ttu-id="d5696-116">ないコンピューターで実行されるアプリケーションを作成している場合は、BizTalk Server がインストールされている DES および BES; を使用して、これらの Api は、BizTalk 以外のアプリケーションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="d5696-116">If you are writing an application that runs on a computer that does not have BizTalk Server installed, use DES and BES; these APIs can be used in non-BizTalk applications.</span></span>  
  
  > [!NOTE]  
  >  <span data-ttu-id="d5696-117">シナリオによっては、複数種類の EventStream を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5696-117">There are scenarios in which you may want to mix EventStream types.</span></span> <span data-ttu-id="d5696-118">たとえば、パイプライン処理のかどうか、パイプラインはロールバック、トランザクションに関係なく、BAM で特定のデータをキャプチャすることがあります。</span><span class="sxs-lookup"><span data-stu-id="d5696-118">For example, for pipeline processing, you may want to capture the particular data in BAM regardless of whether the pipeline is rolling back its transaction.</span></span> <span data-ttu-id="d5696-119">具体的には、失敗したメッセージの数に関するデータの取得や再試行の回数がパイプライン処理中に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d5696-119">In particular, you may want capture data about how many messages failed or how many retries occurred during pipeline processing.</span></span> <span data-ttu-id="d5696-120">この状況でデータを取得するには、BES を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5696-120">To capture the data in this situation you should use BES.</span></span>  
  
- <span data-ttu-id="d5696-121">BizTalk Server がインストールされているコンピューターでアプリケーションを実行する場合は、MES および OES を使用します </span><span class="sxs-lookup"><span data-stu-id="d5696-121">If your application runs on a computer on which BizTalk Server is installed, use MES and OES.</span></span> <span data-ttu-id="d5696-122">(これらの API は BizTalk アプリケーションでのみ使用できます)。</span><span class="sxs-lookup"><span data-stu-id="d5696-122">(These APIs are available only from BizTalk applications.)</span></span>  
  
  > [!NOTE]  
  >  <span data-ttu-id="d5696-123">OES は MES と同等ですが、BizTalk オーケストレーションを対象としています。</span><span class="sxs-lookup"><span data-stu-id="d5696-123">OES is the equivalent of MES but for BizTalk orchestrations.</span></span>  
  
- <span data-ttu-id="d5696-124">BAM イベントの永続化をパイプライン トランザクションと同期する場合は、メッセージング イベント Stream (MES) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5696-124">If you want BAM event persistence to be in sync with pipeline transaction, you should use a Messaging Event Stream (MES).</span></span>  
  
  <span data-ttu-id="d5696-125">すべて、非同期 EventStreams (BES、MES、OES) は、BizTalk メッセージ ボックス データベースに最初にデータを保持します。</span><span class="sxs-lookup"><span data-stu-id="d5696-125">All the asynchronous EventStreams (BES, MES, and OES) persist data first to the BizTalk MessageBox database.</span></span> <span data-ttu-id="d5696-126">このデータは Tracking Data Decode Service (TDDS) によって定期的に処理され、BAM プライマリ インポート データベースに保存されます。</span><span class="sxs-lookup"><span data-stu-id="d5696-126">Periodically the data is processed and persisted to the BAM Primary Import database by the Tracking Data Decode Service (TDDS).</span></span>  
  
  <span data-ttu-id="d5696-127">BAM の EventStream Api の詳細については、次を参照してください。 [EventStream クラス](http://go.microsoft.com/fwlink/?LinkId=158046)(http://go.microsoft.com/fwlink/?LinkId=158046) 、BizTalk Server のドキュメントにします。</span><span class="sxs-lookup"><span data-stu-id="d5696-127">For more information about the BAM EventStream APIs, see [EventStream Classes](http://go.microsoft.com/fwlink/?LinkId=158046) (http://go.microsoft.com/fwlink/?LinkId=158046) in the BizTalk Server documentation.</span></span>  
  
## <a name="bam-performance-counters"></a><span data-ttu-id="d5696-128">BAM パフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="d5696-128">BAM performance counters</span></span>  
 <span data-ttu-id="d5696-129">BAM のパフォーマンス カウンターの詳細な一覧を参照してください。 [BAM パフォーマンス カウンター](http://go.microsoft.com/fwlink/?LinkId=158048) (http://go.microsoft.com/fwlink/?LinkId=158048) 、BizTalk Server のドキュメントにします。</span><span class="sxs-lookup"><span data-stu-id="d5696-129">For a detailed list of the performance counters for BAM, see [BAM Performance Counters](http://go.microsoft.com/fwlink/?LinkId=158048) (http://go.microsoft.com/fwlink/?LinkId=158048) in the BizTalk Server documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5696-130">参照</span><span class="sxs-lookup"><span data-stu-id="d5696-130">See Also</span></span>  
 [<span data-ttu-id="d5696-131">BizTalk Server パフォーマンスの最適化</span><span class="sxs-lookup"><span data-stu-id="d5696-131">Optimizing BizTalk Server Performance</span></span>](../technical-guides/optimizing-biztalk-server-performance.md)