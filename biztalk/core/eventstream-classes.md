---
title: "EventStream クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a3e7a6b3-69cc-4312-9074-acccd1175d37
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89eafdced54927007bcc8dfc02e4834641e2ae2f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="eventstream-classes"></a><span data-ttu-id="694a2-102">EventStream クラス</span><span class="sxs-lookup"><span data-stu-id="694a2-102">EventStream Classes</span></span>
<span data-ttu-id="694a2-103">BAM の EventStream API は、Microsoft.BizTalk.BAM.EventObservation 名前空間に含まれています。</span><span class="sxs-lookup"><span data-stu-id="694a2-103">The EventStream APIs for BAM reside in the Microsoft.BizTalk.BAM.EventObservation namespace.</span></span> <span data-ttu-id="694a2-104">これらの API に対してコードを記述するには、次の DLL を開発用コンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="694a2-104">To code against the APIs, you must install the following DLLs on your development computer:</span></span>  
  
-   <span data-ttu-id="694a2-105">Microsoft.BizTalk.BAM.EventObservation.dll</span><span class="sxs-lookup"><span data-stu-id="694a2-105">Microsoft.BizTalk.BAM.EventObservation.dll</span></span>  
  
-   <span data-ttu-id="694a2-106">Microsoft.Biztalk.BAM.Xlangs.dll: この DLL がオーケストレーション イベント ストリームのコーディング時に必要です。</span><span class="sxs-lookup"><span data-stu-id="694a2-106">Microsoft.Biztalk.BAM.Xlangs.dll: This DLL is required when coding for Orchestration event streams.</span></span>  
  
-   <span data-ttu-id="694a2-107">Microsoft.biztalk.pipeline.dll 内: この DLL は、メッセージング イベント ストリームのコード パイプライン コンテキストを使用する場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="694a2-107">Microsoft.BizTalk.Pipeline.dll: This DLL required when using coding pipeline contexts for Messaging event streams.</span></span>  
  
 <span data-ttu-id="694a2-108">プロジェクト参照に DLL を追加し、次のステートメントを使用してコードに名前空間を組み込みます。</span><span class="sxs-lookup"><span data-stu-id="694a2-108">Add the DLL to your project reference and include the namespace in your code with the following using statement:</span></span>  
  
```  
using Microsoft.BizTalk.Bam.EventObservation;  
```  
  
 <span data-ttu-id="694a2-109">**クラス**</span><span class="sxs-lookup"><span data-stu-id="694a2-109">**Classes**</span></span>  
  
|<span data-ttu-id="694a2-110">名前</span><span class="sxs-lookup"><span data-stu-id="694a2-110">Name</span></span>|<span data-ttu-id="694a2-111">Description</span><span class="sxs-lookup"><span data-stu-id="694a2-111">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="694a2-112">DirectEventStream (DES)</span><span class="sxs-lookup"><span data-stu-id="694a2-112">DirectEventStream (DES)</span></span>|<span data-ttu-id="694a2-113">同期、待機時間なし。</span><span class="sxs-lookup"><span data-stu-id="694a2-113">Synchronous, no latency</span></span>|  
|<span data-ttu-id="694a2-114">BufferedEventStream (BES)</span><span class="sxs-lookup"><span data-stu-id="694a2-114">BufferedEventStream (BES)</span></span>|<span data-ttu-id="694a2-115">非同期、高スループット、ある程度の待機時間あり。</span><span class="sxs-lookup"><span data-stu-id="694a2-115">Asynchronous, high throughput, some latency</span></span>|  
|<span data-ttu-id="694a2-116">OrchestrationEventStream (OES)</span><span class="sxs-lookup"><span data-stu-id="694a2-116">OrchestrationEventStream (OES)</span></span>|<span data-ttu-id="694a2-117">非同期、BizTalk オーケストレーション トランザクションに参加。</span><span class="sxs-lookup"><span data-stu-id="694a2-117">Asynchronous, participates in BizTalk orchestration transactions</span></span>|  
|<span data-ttu-id="694a2-118">IPipelineContext インターフェイス</span><span class="sxs-lookup"><span data-stu-id="694a2-118">IPipelineContext Interface</span></span>|<span data-ttu-id="694a2-119">非同期、BizTalk Server パイプライン トランザクションに参加。</span><span class="sxs-lookup"><span data-stu-id="694a2-119">Asynchronous, participates in BizTalk Server pipeline transactions.</span></span> <span data-ttu-id="694a2-120">メッセージング イベント ストリーム (MES) の作成に使用。</span><span class="sxs-lookup"><span data-stu-id="694a2-120">Used to create Messaging Event Streams (MES).</span></span>|  
  
 <span data-ttu-id="694a2-121">API は、次の要因に基づいて選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="694a2-121">You should choose an API based on the following factors:</span></span>  
  
-   <span data-ttu-id="694a2-122">待機時間を重視する場合は DES を選択します。DES では、データが BAM プライマリ インポート データベースと同期された状態で保持されます。</span><span class="sxs-lookup"><span data-stu-id="694a2-122">If your concern is latency, choose DES, where data is persisted synchronously to the BAM Primary Import database.</span></span> <span data-ttu-id="694a2-123">DES を除くその他すべての EventStream クラスは非同期であり、多少の待機時間があります。</span><span class="sxs-lookup"><span data-stu-id="694a2-123">Except for DES, all other EventStream classes are asynchronous and have some latency.</span></span> <span data-ttu-id="694a2-124">データは、まずメッセージ ボックスに保持され、その後 TDDS によって処理されて BAMPrimaryImport データベースに移動されます。</span><span class="sxs-lookup"><span data-stu-id="694a2-124">The data is first persisted to MessageBox and subsequently processed by TDDS which moves data into the BAMPrimaryImport database.</span></span>  
  
-   <span data-ttu-id="694a2-125">イベント挿入のパフォーマンスとスループットを重視する場合は、非同期 API を選択します。</span><span class="sxs-lookup"><span data-stu-id="694a2-125">If your concern is performance and throughput of event insertion, choose an asynchronous API.</span></span>  
  
-   <span data-ttu-id="694a2-126">BizTalk Server がインストールされていないコンピューターで実行するアプリケーションを作成する場合は、DES および BES を使用します </span><span class="sxs-lookup"><span data-stu-id="694a2-126">If you are writing an application that runs on a computer that does not have BizTalk Server installed, use DES and BES.</span></span> <span data-ttu-id="694a2-127">(つまり、これらの API は非 BizTalk アプリケーションで使用できます)。</span><span class="sxs-lookup"><span data-stu-id="694a2-127">(In other words, these APIs can be used in non-BizTalk applications.)</span></span>  
  
-   <span data-ttu-id="694a2-128">BizTalk Server がインストールされているコンピューターでアプリケーションを実行する場合は、MES および OES を使用します </span><span class="sxs-lookup"><span data-stu-id="694a2-128">If your application runs on a computer on which BizTalk Server is installed, use MES and OES.</span></span> <span data-ttu-id="694a2-129">(これらの API は BizTalk アプリケーションでのみ使用できます)。</span><span class="sxs-lookup"><span data-stu-id="694a2-129">(These APIs are available only from BizTalk applications.)</span></span>  
  
    -   <span data-ttu-id="694a2-130">BAM イベントをパイプライン トランザクションと同期された状態で保持する場合は、メッセージング イベント ストリームを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="694a2-130">If you want BAM event persistence to be in sync with pipeline transaction, you should use a Messaging Event Stream.</span></span>  
  
    -   <span data-ttu-id="694a2-131">OES は MES と同等ですが、BizTalk オーケストレーションを対象としています。</span><span class="sxs-lookup"><span data-stu-id="694a2-131">OES is the equivalent of MES but for BizTalk orchestrations.</span></span>  
  
 <span data-ttu-id="694a2-132">シナリオによっては、複数種類の EventStream を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="694a2-132">There are scenarios in which you may want to mix EventStream types.</span></span> <span data-ttu-id="694a2-133">たとえば、パイプライン処理では、パイプラインがそのトランザクションをロールバックするかどうかにかかわらず、BAM で特定のデータを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="694a2-133">For example, in a pipeline processing, you may want to capture the particular data in BAM regardless of whether the pipeline is rolling back its transaction.</span></span> <span data-ttu-id="694a2-134">特に、パイプライン処理での失敗したメッセージの数や再試行の回数に関するデータの取得が必要です。</span><span class="sxs-lookup"><span data-stu-id="694a2-134">In particular, you may want capture data about how many messages failed or how many retries there were during pipeline processing.</span></span> <span data-ttu-id="694a2-135">この状況でデータを取得するには、BES を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="694a2-135">To capture the data in this situation you should use BES.</span></span>  
  
 <span data-ttu-id="694a2-136">非同期 EventStream (BES、MES、OES) はいずれも、まず BizTalk メッセージ ボックス データベースにデータを保存します。</span><span class="sxs-lookup"><span data-stu-id="694a2-136">All the asynchronous EventStreams (BES, MES, and OES) persist data first in the BizTalk MessageBox database.</span></span> <span data-ttu-id="694a2-137">このデータは Tracking Data Decode Service (TDDS) によって定期的に処理され、BAM プライマリ インポート データベースに保存されます。</span><span class="sxs-lookup"><span data-stu-id="694a2-137">Periodically the data is processed and persisted to the BAM Primary Import database by the Tracking Data Decode Service (TDDS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="694a2-138">EventStream の呼び出しによって BizTalk アプリケーションからボトルネックが生じないようにするために、非同期 API の使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="694a2-138">To ensure that EventStream calls do not create a bottleneck from a BizTalk application, we recommend that you use asynchronous APIs.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="694a2-139">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="694a2-139">In This Section</span></span>  
  
-   [<span data-ttu-id="694a2-140">OrchestrationEventStream</span><span class="sxs-lookup"><span data-stu-id="694a2-140">OrchestrationEventStream</span></span>](../core/orchestrationeventstream.md)  
  
-   [<span data-ttu-id="694a2-141">メッセージング イベント ストリーム</span><span class="sxs-lookup"><span data-stu-id="694a2-141">Messaging Event Streams</span></span>](../core/messaging-event-streams.md)