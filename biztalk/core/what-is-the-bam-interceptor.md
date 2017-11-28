---
title: "BAM インターセプターについて | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM Interceptor object
- BAM, collecting data
- BAM, Interceptor object
- data, collecting [BAM]
ms.assetid: e0213c4e-e2f4-4bb0-bd27-e5810f7e39d9
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9400e80a2f8e8acfdeb12e3d6e61a046151d1e7e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-bam-interceptor"></a><span data-ttu-id="d83bd-103">BAM インターセプターについて</span><span class="sxs-lookup"><span data-stu-id="d83bd-103">What Is the BAM Interceptor?</span></span>
## <a name="overview"></a><span data-ttu-id="d83bd-104">概要</span><span class="sxs-lookup"><span data-stu-id="d83bd-104">Overview</span></span> 

<span data-ttu-id="d83bd-105">BAM インターセプターは、アプリケーションをインストルメント化して対象のデータを取得するためのオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="d83bd-105">The BAM Interceptor is an object that lets you instrument your application to capture data of interest.</span></span> <span data-ttu-id="d83bd-106">次の図は、BAM インターセプターの役割と、他の BAM コンポーネントとのやり取りを示しています。</span><span class="sxs-lookup"><span data-stu-id="d83bd-106">The following diagram shows the role of the BAM interceptor and its interaction with the other BAM components:</span></span>  
  
 ![](../core/media/bam-config-api.gif "bam_config_api")  
<span data-ttu-id="d83bd-107">BAM インターセプタ</span><span class="sxs-lookup"><span data-stu-id="d83bd-107">BAM Interceptor</span></span>  
  
 <span data-ttu-id="d83bd-108">ユーザーは、対象のデータが発生するアプリケーションのステップごとにインターセプター OnStep を呼び出し、ステップの識別子を指定して、アプリケーションで使用するデータや任意のオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="d83bd-108">In each step of your application where you could have data of interest, you call Interceptor OnStep, provide an identifier for the step, and provide some data or arbitrary object that you are using in your application.</span></span>  
  
 <span data-ttu-id="d83bd-109">コールバックが発生した場合に現在のステップ ID およびデータ オブジェクトをコールバック プロシージャで取得するためのコールバック関数を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d83bd-109">You must implement a callback function so when the callback occurs, your callback procedure gets the current step ID and your data object.</span></span> <span data-ttu-id="d83bd-110">BAM インターセプターの役割は基本的に、データ オブジェクトをコールバック関数に渡すという単純なものです。</span><span class="sxs-lookup"><span data-stu-id="d83bd-110">Essentially, the BAM interceptor is simply propagating the data object to the callback.</span></span> <span data-ttu-id="d83bd-111">データを抽出する実際のロジックはアプリケーション内に存在しています。</span><span class="sxs-lookup"><span data-stu-id="d83bd-111">The actual logic of extracting data resides in your application.</span></span> <span data-ttu-id="d83bd-112">たとえば、データが XML メッセージの形式である場合、コールバックは XPath を使用します。</span><span class="sxs-lookup"><span data-stu-id="d83bd-112">For example, if your data takes the form of XML messages, then the callback will use XPaths.</span></span> <span data-ttu-id="d83bd-113">Xpath の詳細については、次を参照してください。[メッセージ割り当てにおける Xpath の使用](../core/using-xpaths-in-message-assignments.md)です。</span><span class="sxs-lookup"><span data-stu-id="d83bd-113">For more information about XPaths, see [Using XPaths in Message Assignment](../core/using-xpaths-in-message-assignments.md).</span></span>  
  
 <span data-ttu-id="d83bd-114">BAM インターセプターは、構成に基づいて各ステップでどのデータを要求するかを判断します。この構成はプログラムで作成できます。</span><span class="sxs-lookup"><span data-stu-id="d83bd-114">The BAM interceptor decides which data to request at each step, based on the configuration that you can create programmatically.</span></span> <span data-ttu-id="d83bd-115">次に BAM インターセプターは取得したデータを使用して DirectEventStream または BufferedEventStream を呼び出します。これらのクラスを保持し、引数として OnStep インターセプターに渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="d83bd-115">The BAM Interceptor then uses the obtained data to call either DirectEventStream or BufferedEventStream that you need to keep around and pass each time as an argument to OnStep.</span></span>  
  
 <span data-ttu-id="d83bd-116">ステップごとにインターセプターを呼び出しても、リソースを消耗することはありません。</span><span class="sxs-lookup"><span data-stu-id="d83bd-116">Calling the interceptor for each step is not a resource-intensive operation.</span></span> <span data-ttu-id="d83bd-117">このステップでインターセプターを呼び出し、何も登録しなければ、インターセプターは直ちに戻ります。</span><span class="sxs-lookup"><span data-stu-id="d83bd-117">If you call and you register nothing for this step, the interceptor returns immediately.</span></span> <span data-ttu-id="d83bd-118">つまり、ディスク操作、トランザクション、メモリの割り当てが行われないため、パフォーマンスは影響をほとんど受けません。</span><span class="sxs-lookup"><span data-stu-id="d83bd-118">This means that there are no disk operations, no transactions, not even memory allocations, and thus almost no performance impact.</span></span> <span data-ttu-id="d83bd-119">また、必要に応じて BAM が使用するためのデータを抽出することもできます。</span><span class="sxs-lookup"><span data-stu-id="d83bd-119">At the same time, you have the opportunity to extract any data for BAM if necessary.</span></span> <span data-ttu-id="d83bd-120">データの抽出およびデータの可用性に関連する手順のパフォーマンスに影響の実装に依存、`IBAMDataExtractor Interface`です。</span><span class="sxs-lookup"><span data-stu-id="d83bd-120">The performance impact on the steps involving data extraction and the availability of the data will depend on your implementation of the `IBAMDataExtractor Interface`.</span></span>  
  
 <span data-ttu-id="d83bd-121">次のコード例は、構成時および実行時のインターセプターの使用例を示しています。</span><span class="sxs-lookup"><span data-stu-id="d83bd-121">The following code examples demonstrate the use of the interceptor during configuration and run time.</span></span>  
  
## <a name="configuration-time"></a><span data-ttu-id="d83bd-122">構成時</span><span class="sxs-lookup"><span data-stu-id="d83bd-122">Configuration time</span></span>  
 <span data-ttu-id="d83bd-123">次のコードは、アプリケーションの recvPO ステップでインターセプターを停止し、Customer Name および Customer SSN を要求するようにインターセプターを構成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d83bd-123">The following code shows how you configure the Interceptor to stop at step recvPO of the application, and ask for Customer Name and Customer SSN:</span></span>  
  
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
  
 <span data-ttu-id="d83bd-124">インターセプター インスタンスを一度作成すると、インスタンスを保存して後続の実行時に使用できます。</span><span class="sxs-lookup"><span data-stu-id="d83bd-124">After you create an interceptor instance, you can store it for later use at runtime.</span></span>  
  
 <span data-ttu-id="d83bd-125">BAM で使用するデータやマイルストーンについて、さまざまな環境設定を表すインターセプターをあらかじめ作成しておくことができます。</span><span class="sxs-lookup"><span data-stu-id="d83bd-125">You may keep different pre-created interceptors representing different preferences for the data and milestones for BAM.</span></span> <span data-ttu-id="d83bd-126">最高のパフォーマンスを得るには、BinaryFormatter クラスを使用してインターセプター インスタンスをシリアル化してください。</span><span class="sxs-lookup"><span data-stu-id="d83bd-126">For best performance, serialize the Interceptor instances using the BinaryFormatter class.</span></span>  
  
## <a name="run-time"></a><span data-ttu-id="d83bd-127">実行時</span><span class="sxs-lookup"><span data-stu-id="d83bd-127">Run time</span></span>  
 <span data-ttu-id="d83bd-128">実稼働環境で実行時にインターセプターを使用するには、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="d83bd-128">Use this code to use the interceptor at runtime in a production environment:</span></span>  
  
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
  
 <span data-ttu-id="d83bd-129">各要素の説明は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d83bd-129">Where:</span></span>  
  
-   <span data-ttu-id="d83bd-130">*recvPO*と*approvePO*アプリケーションでステップの識別に使用する任意のオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="d83bd-130">*recvPO* and *approvePO* are arbitrary objects you use to identify the steps in your application.</span></span>  
  
-   <span data-ttu-id="d83bd-131">*data1*と*data2*は任意のオブジェクトをその時点でし、注文書の XML ドキュメントの対象のデータを含めることがあります。</span><span class="sxs-lookup"><span data-stu-id="d83bd-131">*data1* and *data2* are arbitrary objects that you have at that point and may contain interesting data – for example the XML document of the purchase order.</span></span>  
  
-   <span data-ttu-id="d83bd-132">*es*は、パフォーマンスの要件に応じて、DirectEventStream または BufferedEvent ストリーム。</span><span class="sxs-lookup"><span data-stu-id="d83bd-132">*es* is either DirectEventStream or BufferedEvent stream depending on your performance requirements.</span></span>  
  
-   <span data-ttu-id="d83bd-133">*コールバック*の実装には、`IBAMDataExtractor Interface`です。</span><span class="sxs-lookup"><span data-stu-id="d83bd-133">*callback* is your implementation of the `IBAMDataExtractor Interface`.</span></span>  
  
 <span data-ttu-id="d83bd-134">SDK サンプル[BAM API (BizTalk Server サンプル)](../core/bam-api-biztalk-server-sample.md)、両方の構成ツールと例ランタイム アプリケーションを含む、インターセプターの使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d83bd-134">The SDK sample, [BAM API (BizTalk Server Sample)](../core/bam-api-biztalk-server-sample.md), demonstrates using the Interceptor, which contains both a configuration tool and example runtime application.</span></span>  
  
 <span data-ttu-id="d83bd-135">BizTalk オーケストレーション エンジンには、途中受信、BAM の追跡プロファイル エディターを使用して実行時に収集されるデータに変更できますが対応しています。</span><span class="sxs-lookup"><span data-stu-id="d83bd-135">The BizTalk Orchestration Engine accommodates interception, which allows changing what data is collected for BAM at runtime using the Tracking Profile Editor.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d83bd-136">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d83bd-136">In This Section</span></span>  
  
-   [<span data-ttu-id="d83bd-137">判断し、アクティビティ イベント ライター ロールを設定する方法</span><span class="sxs-lookup"><span data-stu-id="d83bd-137">How to Determine and Set Event Writer Roles for Activities</span></span>](../core/how-to-determine-and-set-event-writer-roles-for-activities.md)  
  
## <a name="see-also"></a><span data-ttu-id="d83bd-138">参照</span><span class="sxs-lookup"><span data-stu-id="d83bd-138">See Also</span></span>  
 [<span data-ttu-id="d83bd-139">BAM API (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="d83bd-139">BAM API (BizTalk Server Sample)</span></span>](../core/bam-api-biztalk-server-sample.md)