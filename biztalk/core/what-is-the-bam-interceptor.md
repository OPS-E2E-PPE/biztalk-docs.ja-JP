---
title: BAM インターセプターについて | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM Interceptor object
- BAM, collecting data
- BAM, Interceptor object
- data, collecting [BAM]
ms.assetid: e0213c4e-e2f4-4bb0-bd27-e5810f7e39d9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2dbd9b3a2bff2d6a858de372de5e06b1ff6cbbde
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243065"
---
# <a name="what-is-the-bam-interceptor"></a><span data-ttu-id="20cb1-103">BAM インターセプターについて</span><span class="sxs-lookup"><span data-stu-id="20cb1-103">What Is the BAM Interceptor?</span></span>
## <a name="overview"></a><span data-ttu-id="20cb1-104">概要</span><span class="sxs-lookup"><span data-stu-id="20cb1-104">Overview</span></span> 

<span data-ttu-id="20cb1-105">BAM インターセプターは、アプリケーションをインストルメント化して対象のデータを取得するためのオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="20cb1-105">The BAM Interceptor is an object that lets you instrument your application to capture data of interest.</span></span> <span data-ttu-id="20cb1-106">次の図は、BAM インターセプターの役割と、他の BAM コンポーネントとのやり取りを示しています。</span><span class="sxs-lookup"><span data-stu-id="20cb1-106">The following diagram shows the role of the BAM interceptor and its interaction with the other BAM components:</span></span>  
  
 <span data-ttu-id="20cb1-107">![](../core/media/bam-config-api.gif "bam_config_api")</span><span class="sxs-lookup"><span data-stu-id="20cb1-107">![](../core/media/bam-config-api.gif "bam_config_api")</span></span>  
<span data-ttu-id="20cb1-108">BAM インターセプター</span><span class="sxs-lookup"><span data-stu-id="20cb1-108">BAM Interceptor</span></span>  
  
 <span data-ttu-id="20cb1-109">ユーザーは、対象のデータが発生するアプリケーションのステップごとにインターセプター OnStep を呼び出し、ステップの識別子を指定して、アプリケーションで使用するデータや任意のオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="20cb1-109">In each step of your application where you could have data of interest, you call Interceptor OnStep, provide an identifier for the step, and provide some data or arbitrary object that you are using in your application.</span></span>  
  
 <span data-ttu-id="20cb1-110">コールバックが発生した場合に現在のステップ ID およびデータ オブジェクトをコールバック プロシージャで取得するためのコールバック関数を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20cb1-110">You must implement a callback function so when the callback occurs, your callback procedure gets the current step ID and your data object.</span></span> <span data-ttu-id="20cb1-111">BAM インターセプターの役割は基本的に、データ オブジェクトをコールバック関数に渡すという単純なものです。</span><span class="sxs-lookup"><span data-stu-id="20cb1-111">Essentially, the BAM interceptor is simply propagating the data object to the callback.</span></span> <span data-ttu-id="20cb1-112">データを抽出する実際のロジックはアプリケーション内に存在しています。</span><span class="sxs-lookup"><span data-stu-id="20cb1-112">The actual logic of extracting data resides in your application.</span></span> <span data-ttu-id="20cb1-113">たとえば、データが XML メッセージの形式である場合、コールバックは XPath を使用します。</span><span class="sxs-lookup"><span data-stu-id="20cb1-113">For example, if your data takes the form of XML messages, then the callback will use XPaths.</span></span> <span data-ttu-id="20cb1-114">Xpath の詳細については、次を参照してください。[メッセージ割り当てにおける Xpath の使用](../core/using-xpaths-in-message-assignments.md)します。</span><span class="sxs-lookup"><span data-stu-id="20cb1-114">For more information about XPaths, see [Using XPaths in Message Assignment](../core/using-xpaths-in-message-assignments.md).</span></span>  
  
 <span data-ttu-id="20cb1-115">BAM インターセプターは、構成に基づいて各ステップでどのデータを要求するかを判断します。この構成はプログラムで作成できます。</span><span class="sxs-lookup"><span data-stu-id="20cb1-115">The BAM interceptor decides which data to request at each step, based on the configuration that you can create programmatically.</span></span> <span data-ttu-id="20cb1-116">次に BAM インターセプターは取得したデータを使用して DirectEventStream または BufferedEventStream を呼び出します。これらのクラスを保持し、引数として OnStep インターセプターに渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="20cb1-116">The BAM Interceptor then uses the obtained data to call either DirectEventStream or BufferedEventStream that you need to keep around and pass each time as an argument to OnStep.</span></span>  
  
 <span data-ttu-id="20cb1-117">ステップごとにインターセプターを呼び出しても、リソースを消耗することはありません。</span><span class="sxs-lookup"><span data-stu-id="20cb1-117">Calling the interceptor for each step is not a resource-intensive operation.</span></span> <span data-ttu-id="20cb1-118">このステップでインターセプターを呼び出し、何も登録しなければ、インターセプターは直ちに戻ります。</span><span class="sxs-lookup"><span data-stu-id="20cb1-118">If you call and you register nothing for this step, the interceptor returns immediately.</span></span> <span data-ttu-id="20cb1-119">つまり、ディスク操作、トランザクション、メモリの割り当てが行われないため、パフォーマンスは影響をほとんど受けません。</span><span class="sxs-lookup"><span data-stu-id="20cb1-119">This means that there are no disk operations, no transactions, not even memory allocations, and thus almost no performance impact.</span></span> <span data-ttu-id="20cb1-120">また、必要に応じて BAM が使用するためのデータを抽出することもできます。</span><span class="sxs-lookup"><span data-stu-id="20cb1-120">At the same time, you have the opportunity to extract any data for BAM if necessary.</span></span> <span data-ttu-id="20cb1-121">データの抽出とデータの可用性に関連する手順のパフォーマンスに影響の実装によって異なります、`IBAMDataExtractor Interface`します。</span><span class="sxs-lookup"><span data-stu-id="20cb1-121">The performance impact on the steps involving data extraction and the availability of the data will depend on your implementation of the `IBAMDataExtractor Interface`.</span></span>  
  
 <span data-ttu-id="20cb1-122">次のコード例は、構成時および実行時のインターセプターの使用例を示しています。</span><span class="sxs-lookup"><span data-stu-id="20cb1-122">The following code examples demonstrate the use of the interceptor during configuration and run time.</span></span>  
  
## <a name="configuration-time"></a><span data-ttu-id="20cb1-123">構成時</span><span class="sxs-lookup"><span data-stu-id="20cb1-123">Configuration time</span></span>  
 <span data-ttu-id="20cb1-124">次のコードは、アプリケーションの recvPO ステップでインターセプターを停止し、Customer Name および Customer SSN を要求するようにインターセプターを構成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="20cb1-124">The following code shows how you configure the Interceptor to stop at step recvPO of the application, and ask for Customer Name and Customer SSN:</span></span>  
  
```  
ActivityInterceptorConfiguration cfg= new ActivityInterceptorConfiguration ("PurchaseOrder");  
...  
cfg.RegisterDataExtraction("CustomerName",recvPO,XpathName);  
cfg.RegisterDataExtraction("CustomerSSN",recvPO,XpathSSN);  
...  
BAMInterceptor interceptor=new BAMInterceptor();  
cfg.UpdateInterceptor(interceptor);  
...  
// The interceptor instance is ready.  
```  
  
 <span data-ttu-id="20cb1-125">インターセプター インスタンスを一度作成すると、インスタンスを保存して後続の実行時に使用できます。</span><span class="sxs-lookup"><span data-stu-id="20cb1-125">After you create an interceptor instance, you can store it for later use at runtime.</span></span>  
  
 <span data-ttu-id="20cb1-126">BAM で使用するデータやマイルストーンについて、さまざまな環境設定を表すインターセプターをあらかじめ作成しておくことができます。</span><span class="sxs-lookup"><span data-stu-id="20cb1-126">You may keep different pre-created interceptors representing different preferences for the data and milestones for BAM.</span></span> <span data-ttu-id="20cb1-127">最高のパフォーマンスを得るには、BinaryFormatter クラスを使用してインターセプター インスタンスをシリアル化してください。</span><span class="sxs-lookup"><span data-stu-id="20cb1-127">For best performance, serialize the Interceptor instances using the BinaryFormatter class.</span></span>  
  
## <a name="run-time"></a><span data-ttu-id="20cb1-128">実行時</span><span class="sxs-lookup"><span data-stu-id="20cb1-128">Run time</span></span>  
 <span data-ttu-id="20cb1-129">実稼働環境で実行時にインターセプターを使用するには、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="20cb1-129">Use this code to use the interceptor at runtime in a production environment:</span></span>  
  
```  
// Deserialize the Interceptor that was prepared before  
...  
es=new DirectEventStream(...)  
...  
Interceptor.OnStep(recvPO, data1, es, callback)  
...  
Interceptor.OnStep(approvePO, data2, es, callback)  
...  
```  
  
 <span data-ttu-id="20cb1-130">各要素の説明は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="20cb1-130">Where:</span></span>  
  
- <span data-ttu-id="20cb1-131">*recvPO*と*approvePO*は、アプリケーションでのステップの識別に使用する任意のオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="20cb1-131">*recvPO* and *approvePO* are arbitrary objects you use to identify the steps in your application.</span></span>  
  
- <span data-ttu-id="20cb1-132">*data1*と*data2*は任意のオブジェクトがその時点でして注文書の XML ドキュメントの対象のデータを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="20cb1-132">*data1* and *data2* are arbitrary objects that you have at that point and may contain interesting data – for example the XML document of the purchase order.</span></span>  
  
- <span data-ttu-id="20cb1-133">*es*はパフォーマンスの要件に応じて、DirectEventStream または BufferedEvent ストリーム。</span><span class="sxs-lookup"><span data-stu-id="20cb1-133">*es* is either DirectEventStream or BufferedEvent stream depending on your performance requirements.</span></span>  
  
- <span data-ttu-id="20cb1-134">*コールバック*の実装には、`IBAMDataExtractor Interface`します。</span><span class="sxs-lookup"><span data-stu-id="20cb1-134">*callback* is your implementation of the `IBAMDataExtractor Interface`.</span></span>  
  
  <span data-ttu-id="20cb1-135">SDK サンプル[BAM API (BizTalk Server サンプル)](../core/bam-api-biztalk-server-sample.md)、両方の構成ツール、および例ランタイム アプリケーションを含む、インターセプターの使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="20cb1-135">The SDK sample, [BAM API (BizTalk Server Sample)](../core/bam-api-biztalk-server-sample.md), demonstrates using the Interceptor, which contains both a configuration tool and example runtime application.</span></span>  
  
  <span data-ttu-id="20cb1-136">BizTalk オーケストレーション エンジンは、BAM の追跡プロファイル エディターを使用して実行時に収集されるデータに変更できます傍受に対応します。</span><span class="sxs-lookup"><span data-stu-id="20cb1-136">The BizTalk Orchestration Engine accommodates interception, which allows changing what data is collected for BAM at runtime using the Tracking Profile Editor.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="20cb1-137">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="20cb1-137">In This Section</span></span>  
  
-   [<span data-ttu-id="20cb1-138">決定し、アクティビティ イベント ライター ロールを設定する方法</span><span class="sxs-lookup"><span data-stu-id="20cb1-138">How to Determine and Set Event Writer Roles for Activities</span></span>](../core/how-to-determine-and-set-event-writer-roles-for-activities.md)  
  
## <a name="see-also"></a><span data-ttu-id="20cb1-139">参照</span><span class="sxs-lookup"><span data-stu-id="20cb1-139">See Also</span></span>  
 [<span data-ttu-id="20cb1-140">BAM API (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="20cb1-140">BAM API (BizTalk Server Sample)</span></span>](../core/bam-api-biztalk-server-sample.md)