---
title: EventStream クラス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a3e7a6b3-69cc-4312-9074-acccd1175d37
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba599c008c571af520dbc9b7919157371e32750f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388315"
---
# <a name="eventstream-classes"></a><span data-ttu-id="b87ee-102">EventStream クラス</span><span class="sxs-lookup"><span data-stu-id="b87ee-102">EventStream Classes</span></span>
<span data-ttu-id="b87ee-103">BAM の EventStream Api は、Microsoft.BizTalk.BAM.EventObservation 名前空間に存在します。</span><span class="sxs-lookup"><span data-stu-id="b87ee-103">The EventStream APIs for BAM reside in the Microsoft.BizTalk.BAM.EventObservation namespace.</span></span> <span data-ttu-id="b87ee-104">Api に対するコードを記述、開発用コンピューターに、次の Dll をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b87ee-104">To code against the APIs, you must install the following DLLs on your development computer:</span></span>  
  
- <span data-ttu-id="b87ee-105">Microsoft.BizTalk.BAM.EventObservation.dll</span><span class="sxs-lookup"><span data-stu-id="b87ee-105">Microsoft.BizTalk.BAM.EventObservation.dll</span></span>  
  
- <span data-ttu-id="b87ee-106">Microsoft.Biztalk.BAM.Xlangs.dll:オーケストレーション イベント ストリームをコーディングする際、この DLL が必要です。</span><span class="sxs-lookup"><span data-stu-id="b87ee-106">Microsoft.Biztalk.BAM.Xlangs.dll: This DLL is required when coding for Orchestration event streams.</span></span>  
  
- <span data-ttu-id="b87ee-107">Microsoft.biztalk.pipeline.dll 内:メッセージング イベント ストリームのコード パイプライン コンテキストを使用する場合、この DLL が必要です。</span><span class="sxs-lookup"><span data-stu-id="b87ee-107">Microsoft.BizTalk.Pipeline.dll: This DLL required when using coding pipeline contexts for Messaging event streams.</span></span>  
  
  <span data-ttu-id="b87ee-108">DLL のプロジェクト参照を追加して、コードを次に、名前空間を含めるステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="b87ee-108">Add the DLL to your project reference and include the namespace in your code with the following using statement:</span></span>  
  
```  
using Microsoft.BizTalk.Bam.EventObservation;  
```  
  
 <span data-ttu-id="b87ee-109">**クラス**</span><span class="sxs-lookup"><span data-stu-id="b87ee-109">**Classes**</span></span>  
  
|<span data-ttu-id="b87ee-110">名前</span><span class="sxs-lookup"><span data-stu-id="b87ee-110">Name</span></span>|<span data-ttu-id="b87ee-111">説明</span><span class="sxs-lookup"><span data-stu-id="b87ee-111">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="b87ee-112">DirectEventStream (DES)</span><span class="sxs-lookup"><span data-stu-id="b87ee-112">DirectEventStream (DES)</span></span>|<span data-ttu-id="b87ee-113">同期、待機時間なし。</span><span class="sxs-lookup"><span data-stu-id="b87ee-113">Synchronous, no latency</span></span>|  
|<span data-ttu-id="b87ee-114">BufferedEventStream (BES)</span><span class="sxs-lookup"><span data-stu-id="b87ee-114">BufferedEventStream (BES)</span></span>|<span data-ttu-id="b87ee-115">非同期、高スループット、いくつかの待機時間</span><span class="sxs-lookup"><span data-stu-id="b87ee-115">Asynchronous, high throughput, some latency</span></span>|  
|<span data-ttu-id="b87ee-116">OrchestrationEventStream (OES)</span><span class="sxs-lookup"><span data-stu-id="b87ee-116">OrchestrationEventStream (OES)</span></span>|<span data-ttu-id="b87ee-117">非同期、BizTalk オーケストレーション トランザクションに参加します。</span><span class="sxs-lookup"><span data-stu-id="b87ee-117">Asynchronous, participates in BizTalk orchestration transactions</span></span>|  
|<span data-ttu-id="b87ee-118">IPipelineContext インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b87ee-118">IPipelineContext Interface</span></span>|<span data-ttu-id="b87ee-119">非同期は、BizTalk Server パイプライン トランザクションに参加します。</span><span class="sxs-lookup"><span data-stu-id="b87ee-119">Asynchronous, participates in BizTalk Server pipeline transactions.</span></span> <span data-ttu-id="b87ee-120">メッセージング イベント ストリーム (MES) を作成するために使用します。</span><span class="sxs-lookup"><span data-stu-id="b87ee-120">Used to create Messaging Event Streams (MES).</span></span>|  
  
 <span data-ttu-id="b87ee-121">次の要因に基づく API を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b87ee-121">You should choose an API based on the following factors:</span></span>  
  
- <span data-ttu-id="b87ee-122">待機時間を重視する場合は DES を選択します。DES では、データが BAM プライマリ インポート データベースと同期された状態で保持されます。</span><span class="sxs-lookup"><span data-stu-id="b87ee-122">If your concern is latency, choose DES, where data is persisted synchronously to the BAM Primary Import database.</span></span> <span data-ttu-id="b87ee-123">DES を除くその他のすべての EventStream クラスは非同期であり待ち時間が発生します。</span><span class="sxs-lookup"><span data-stu-id="b87ee-123">Except for DES, all other EventStream classes are asynchronous and have some latency.</span></span> <span data-ttu-id="b87ee-124">データはまずメッセージ ボックス データベースに保存され、BAMPrimaryImport データベースにデータを移動する TDDS により処理された後。</span><span class="sxs-lookup"><span data-stu-id="b87ee-124">The data is first persisted to MessageBox and subsequently processed by TDDS which moves data into the BAMPrimaryImport database.</span></span>  
  
- <span data-ttu-id="b87ee-125">イベント挿入のパフォーマンスとスループット、問題がある場合は、非同期 API を選択します。</span><span class="sxs-lookup"><span data-stu-id="b87ee-125">If your concern is performance and throughput of event insertion, choose an asynchronous API.</span></span>  
  
- <span data-ttu-id="b87ee-126">ないコンピューターで実行されるアプリケーションを作成する場合は、BizTalk Server がインストールされている、DES および BES を使用します。</span><span class="sxs-lookup"><span data-stu-id="b87ee-126">If you are writing an application that runs on a computer that does not have BizTalk Server installed, use DES and BES.</span></span> <span data-ttu-id="b87ee-127">(つまり、これらの Api できます非 BizTalk アプリケーションにします。)</span><span class="sxs-lookup"><span data-stu-id="b87ee-127">(In other words, these APIs can be used in non-BizTalk applications.)</span></span>  
  
- <span data-ttu-id="b87ee-128">BizTalk Server がインストールされているコンピューターでアプリケーションを実行する場合は、MES および OES を使用します </span><span class="sxs-lookup"><span data-stu-id="b87ee-128">If your application runs on a computer on which BizTalk Server is installed, use MES and OES.</span></span> <span data-ttu-id="b87ee-129">(これらの API は BizTalk アプリケーションでのみ使用できます)。</span><span class="sxs-lookup"><span data-stu-id="b87ee-129">(These APIs are available only from BizTalk applications.)</span></span>  
  
  -   <span data-ttu-id="b87ee-130">BAM イベントの永続化をパイプライン トランザクションと同期する場合は、メッセージングのイベント Stream を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b87ee-130">If you want BAM event persistence to be in sync with pipeline transaction, you should use a Messaging Event Stream.</span></span>  
  
  -   <span data-ttu-id="b87ee-131">OES は MES と同等ですが、BizTalk オーケストレーションを対象としています。</span><span class="sxs-lookup"><span data-stu-id="b87ee-131">OES is the equivalent of MES but for BizTalk orchestrations.</span></span>  
  
  <span data-ttu-id="b87ee-132">シナリオによっては、複数種類の EventStream を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b87ee-132">There are scenarios in which you may want to mix EventStream types.</span></span> <span data-ttu-id="b87ee-133">たとえば、パイプライン処理でかどうか、パイプラインはロールバック、トランザクションに関係なく、BAM で特定のデータをキャプチャすることがあります。</span><span class="sxs-lookup"><span data-stu-id="b87ee-133">For example, in a pipeline processing, you may want to capture the particular data in BAM regardless of whether the pipeline is rolling back its transaction.</span></span> <span data-ttu-id="b87ee-134">具体的には、パイプライン処理中に失敗したメッセージの数に関するデータをキャプチャまたは再試行の回数をする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b87ee-134">In particular, you may want capture data about how many messages failed or how many retries there were during pipeline processing.</span></span> <span data-ttu-id="b87ee-135">この状況でデータを取得するには、BES を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b87ee-135">To capture the data in this situation you should use BES.</span></span>  
  
  <span data-ttu-id="b87ee-136">すべて、非同期 EventStreams (BES、MES、OES) は、BizTalk メッセージ ボックス データベースで最初にデータを保持します。</span><span class="sxs-lookup"><span data-stu-id="b87ee-136">All the asynchronous EventStreams (BES, MES, and OES) persist data first in the BizTalk MessageBox database.</span></span> <span data-ttu-id="b87ee-137">このデータは Tracking Data Decode Service (TDDS) によって定期的に処理され、BAM プライマリ インポート データベースに保存されます。</span><span class="sxs-lookup"><span data-stu-id="b87ee-137">Periodically the data is processed and persisted to the BAM Primary Import database by the Tracking Data Decode Service (TDDS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b87ee-138">EventStream の呼び出しは BizTalk アプリケーションからボトルネックを作成しないようにするには、非同期 Api を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b87ee-138">To ensure that EventStream calls do not create a bottleneck from a BizTalk application, we recommend that you use asynchronous APIs.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b87ee-139">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b87ee-139">In This Section</span></span>  
  
-   [<span data-ttu-id="b87ee-140">OrchestrationEventStream</span><span class="sxs-lookup"><span data-stu-id="b87ee-140">OrchestrationEventStream</span></span>](../core/orchestrationeventstream.md)  
  
-   [<span data-ttu-id="b87ee-141">メッセージング イベント ストリーム</span><span class="sxs-lookup"><span data-stu-id="b87ee-141">Messaging Event Streams</span></span>](../core/messaging-event-streams.md)