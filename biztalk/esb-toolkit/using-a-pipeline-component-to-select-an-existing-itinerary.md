---
title: パイプライン コンポーネントを使用して、既存のスケジュールを選択する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b93c5cb6-071f-485d-b0bb-22f95bafa3d0
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2aceef4385652918ee7326709e7838776501e885
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975499"
---
# <a name="using-a-pipeline-component-to-select-an-existing-itinerary"></a><span data-ttu-id="ba186-102">パイプライン コンポーネントを使用して、既存のスケジュールを選択するには</span><span class="sxs-lookup"><span data-stu-id="ba186-102">Using a Pipeline Component to Select an Existing Itinerary</span></span>
## <a name="esb-itinerary-selector-pipeline-component"></a><span data-ttu-id="ba186-103">ESB スケジュール セレクターのパイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ba186-103">ESB Itinerary Selector Pipeline Component</span></span>  
 <span data-ttu-id="ba186-104">スケジュール オンランプのヘッダーを使用せず、汎用的なスケジュール オンランプを使用して送信されたメッセージが送信されます。</span><span class="sxs-lookup"><span data-stu-id="ba186-104">Messages submitted using generic itinerary on-ramps are submitted without an itinerary header.</span></span> <span data-ttu-id="ba186-105">適切なスケジュールを解決し、受信メッセージに添付に着手が中央リポジトリからスケジュールにアクセスするように構成できるメカニズムを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba186-105">To resolve the appropriate itinerary and attach it to the incoming message, the on-ramp must provide a mechanism that can be configured to access itineraries from a central repository.</span></span>  

 <span data-ttu-id="ba186-106">ESB スケジュール セレクター パイプライン コンポーネントは、(既定では SQL Server) の中央リポジトリに格納されているサーバー側の旅行プランの内容を解決するのには、特殊な競合回避モジュールと組み合わせて、競合回避モジュールの接続文字列を使います。</span><span class="sxs-lookup"><span data-stu-id="ba186-106">The ESB Itinerary Selector pipeline component uses a resolver connection string, in conjunction with specialized resolvers, to resolve the content of a server-side itinerary stored in a central repository (by default, SQL Server).</span></span>  

 <span data-ttu-id="ba186-107">(SOAP ヘッダーで表される) ように、クライアントによって要求されたスケジュールのバージョンと名前を取得して、メッセージ コンテキストから WCF オンランプ行程静的競合回避モジュールと組み合わせてで ESB スケジュール セレクターのパイプライン コンポーネントを使用するときに、適切なスケジュールの選択に使用されます。</span><span class="sxs-lookup"><span data-stu-id="ba186-107">When the ESB Itinerary Selector pipeline component is used in WCF on-ramps in conjunction with the ITINERARY-STATIC resolver, the name and version of the itinerary requested by the client (as represented in the SOAP header) is retrieved from the message context and is used to select the appropriate itinerary.</span></span>  

 <span data-ttu-id="ba186-108">既定では、ESB スケジュール セレクターのパイプライン コンポーネントは次のパイプラインに存在します。</span><span class="sxs-lookup"><span data-stu-id="ba186-108">By default, the ESB Itinerary Selector pipeline component resides in the following pipelines:</span></span>  

- <span data-ttu-id="ba186-109">ItinerarySelectReceive</span><span class="sxs-lookup"><span data-stu-id="ba186-109">ItinerarySelectReceive</span></span>  

- <span data-ttu-id="ba186-110">ItinerarySelectReceivePassthrough</span><span class="sxs-lookup"><span data-stu-id="ba186-110">ItinerarySelectReceivePassthrough</span></span>  

- <span data-ttu-id="ba186-111">ItinerarySelectReceiveXml</span><span class="sxs-lookup"><span data-stu-id="ba186-111">ItinerarySelectReceiveXml</span></span>  

- <span data-ttu-id="ba186-112">ItinerarySelectSendReceive</span><span class="sxs-lookup"><span data-stu-id="ba186-112">ItinerarySelectSendReceive</span></span>  

  <span data-ttu-id="ba186-113">次のセクションでは、各コンポーネントによって実行される手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="ba186-113">The following sections describe the steps performed by each component.</span></span>  

## <a name="esb-itinerary-selector-pipeline-component-processing-steps"></a><span data-ttu-id="ba186-114">ESB スケジュール セレクター パイプライン コンポーネントの処理手順</span><span class="sxs-lookup"><span data-stu-id="ba186-114">ESB Itinerary Selector Pipeline Component Processing Steps</span></span>  
 <span data-ttu-id="ba186-115">ESB スケジュール セレクターのパイプライン コンポーネントは、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ba186-115">The ESB Itinerary Selector pipeline component executes the following steps:</span></span>  

- <span data-ttu-id="ba186-116">送信パーティは、処理対象のメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="ba186-116">The submitting party submits a message for processing.</span></span> <span data-ttu-id="ba186-117">スケジュール セレクター コンポーネントは、開発者によって構成された、プロパティの接続文字列として指定された競合回避モジュールを使用してメッセージの内容またはコンテキストに基づいて、スケジュールのストアから適切な旅行プランを選択します。</span><span class="sxs-lookup"><span data-stu-id="ba186-117">The Itinerary Selector component uses a resolver specified as a property connection string, configured by the developer, to determine and select the appropriate itinerary from the itinerary store, based on message content or context.</span></span>  

- <span data-ttu-id="ba186-118">旅行プランを検証し、日程; でそれらが null の場合、既定値を事前に特定のプロパティを設定します例えば：</span><span class="sxs-lookup"><span data-stu-id="ba186-118">It validates the itinerary and sets specific properties to preset default values if they are null in the itinerary; for example:</span></span>  

  - <span data-ttu-id="ba186-119">サービスの数が 1 未満の場合、コンポーネントは例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="ba186-119">If Service count is less than 1, the component throws an exception.</span></span>  

  - <span data-ttu-id="ba186-120">コンポーネント サービスの数、識別子の値を使用して、itinerary ルート属性を設定する (**Uuid**)、開始時刻 (**BeginTime**)、および一方向または双方向の要求かどうか (**IsRequestResponse**)。</span><span class="sxs-lookup"><span data-stu-id="ba186-120">The component sets the itinerary root attributes using the values for the Service count, the identifier (**Uuid**), the start time (**BeginTime**), and whether this is a one-way or two-way request (**IsRequestResponse**).</span></span>  

  - <span data-ttu-id="ba186-121">コンポーネントで、サービスを検証します、識別子を設定、現在のサービス インスタンス (次に処理するサービス) を設定、および関連付けられているすべての競合回避モジュールを検証します。</span><span class="sxs-lookup"><span data-stu-id="ba186-121">The component validates the services, sets the identifiers, sets the current service instance (the service to process next), and validates any associated resolvers.</span></span>  

  - <span data-ttu-id="ba186-122">コンポーネントは、Microsoft BizTalk Server のセグメントの次のプロパティを使用してスケジュールを設定します。</span><span class="sxs-lookup"><span data-stu-id="ba186-122">The component sets the Microsoft BizTalk Server segment of the itinerary using the following properties:</span></span>  

    -   <span data-ttu-id="ba186-123">**correlationToken**</span><span class="sxs-lookup"><span data-stu-id="ba186-123">**correlationToken**</span></span>  

    -   <span data-ttu-id="ba186-124">**reqRespTransmitPipelineID**</span><span class="sxs-lookup"><span data-stu-id="ba186-124">**reqRespTransmitPipelineID**</span></span>  

    -   <span data-ttu-id="ba186-125">**interchangeId**</span><span class="sxs-lookup"><span data-stu-id="ba186-125">**interchangeId**</span></span>  

    -   <span data-ttu-id="ba186-126">**receiveInstanceId**</span><span class="sxs-lookup"><span data-stu-id="ba186-126">**receiveInstanceId**</span></span>  

    -   <span data-ttu-id="ba186-127">**epmRRCorrelationToken**</span><span class="sxs-lookup"><span data-stu-id="ba186-127">**epmRRCorrelationToken**</span></span>  

  - <span data-ttu-id="ba186-128">コンポーネントは、システム Properties.xsd スキーマで定義されたプロパティを使用して次の表に、BizTalk メッセージ コンテキスト プロパティを変更後の日程を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="ba186-128">The component writes the modified itinerary to the BizTalk message context properties listed in the following table using the properties defined in the System-Properties.xsd schema.</span></span>  


    |                                           <span data-ttu-id="ba186-129">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="ba186-129">Properties</span></span>                                           |
    |------------------------------------------------------------------------------------------------|
    |                                   <span data-ttu-id="ba186-130">**名前 = ItineraryHeader**</span><span class="sxs-lookup"><span data-stu-id="ba186-130">**Name = ItineraryHeader**</span></span>                                   |
    | <span data-ttu-id="ba186-131">**Namespace = http://schemas.microsoft.biztalk.practices.esb.com/itinerary/system-properties**</span><span class="sxs-lookup"><span data-stu-id="ba186-131">**Namespace = http://schemas.microsoft.biztalk.practices.esb.com/itinerary/system-properties**</span></span> |


  - <span data-ttu-id="ba186-132">コンポーネントは、システム Properties.xsd スキーマで定義されている値を使用して次の表に示す 4 つの BizTalk コンテキスト プロパティを昇格させます。</span><span class="sxs-lookup"><span data-stu-id="ba186-132">The component promotes the four BizTalk context properties listed in the following table using the values defined in the System-Properties.xsd schema.</span></span>  

    |<span data-ttu-id="ba186-133">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ba186-133">Property</span></span>|<span data-ttu-id="ba186-134">値</span><span class="sxs-lookup"><span data-stu-id="ba186-134">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="ba186-135">**サービス名**</span><span class="sxs-lookup"><span data-stu-id="ba186-135">**ServiceName**</span></span>|<span data-ttu-id="ba186-136">旅行プランで定義されている現在のサービス インスタンスの名前。</span><span class="sxs-lookup"><span data-stu-id="ba186-136">The name of the current service instance defined in the itinerary.</span></span>|  
    |<span data-ttu-id="ba186-137">**ServiceType**</span><span class="sxs-lookup"><span data-stu-id="ba186-137">**ServiceType**</span></span>|<span data-ttu-id="ba186-138">いずれかに設定**オーケストレーション**または**メッセージング**します。</span><span class="sxs-lookup"><span data-stu-id="ba186-138">Set to either **Orchestration** or **Messaging**.</span></span>|  
    |<span data-ttu-id="ba186-139">**IsRequestResponse**</span><span class="sxs-lookup"><span data-stu-id="ba186-139">**IsRequestResponse**</span></span>|<span data-ttu-id="ba186-140">いずれかに設定**True**または**False**します。</span><span class="sxs-lookup"><span data-stu-id="ba186-140">Set to either **True** or **False**.</span></span>|  
    |<span data-ttu-id="ba186-141">**ServiceState**</span><span class="sxs-lookup"><span data-stu-id="ba186-141">**ServiceState**</span></span>|<span data-ttu-id="ba186-142">設定**保留**します。</span><span class="sxs-lookup"><span data-stu-id="ba186-142">Set to **Pending**.</span></span>|  

## <a name="esb-dispatcher-pipeline-component-process-steps"></a><span data-ttu-id="ba186-143">ESB ディスパッチャー パイプライン コンポーネントのプロセスの手順</span><span class="sxs-lookup"><span data-stu-id="ba186-143">ESB Dispatcher Pipeline Component Process Steps</span></span>  
 <span data-ttu-id="ba186-144">ESB ディスパッチャー パイプライン コンポーネントは、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ba186-144">The ESB Dispatcher pipeline component executes the following steps:</span></span>  

-   <span data-ttu-id="ba186-145">型の任意のスケジュール オンランプ手順の実行を管理**メッセージング**旅行計画を進めます。</span><span class="sxs-lookup"><span data-stu-id="ba186-145">It manages the execution of any itinerary steps of type **Messaging** and advances the itinerary.</span></span> <span data-ttu-id="ba186-146">ESB ディスパッチャー コンポーネントは位置認識され、ある可能性があるメッセージの処理サイクルでその場所に基づくロジックを実行**入力方向の受信**、**送信送信**、**送信受信**、または**送信受信**します。</span><span class="sxs-lookup"><span data-stu-id="ba186-146">The ESB Dispatcher component is location-aware and executes logic based on its location in the messaging processing cycle, which could be **Receive Inbound**, **Send Transmit**, **Send Inbound**, or **Receive Outbound**.</span></span> <span data-ttu-id="ba186-147">ESB ディスパッチャー パイプライン コンポーネントは、ESB スケジュール メッセージング サービス Esb.config ファイルで指定されたを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ba186-147">The ESB Dispatcher pipeline component invokes ESB itinerary messaging services specified in the Esb.config file.</span></span> <span data-ttu-id="ba186-148">既定では、ルーティングと変換のためには、このコンポーネントの構成プロパティは、次のサービスに関連付けられました。</span><span class="sxs-lookup"><span data-stu-id="ba186-148">By default, the configuration properties of this component for routing and transformation are associated with the following services:</span></span>  

    -   <span data-ttu-id="ba186-149">**Microsoft.Practices.ESB.Services.Transform**します。</span><span class="sxs-lookup"><span data-stu-id="ba186-149">**Microsoft.Practices.ESB.Services.Transform**.</span></span> <span data-ttu-id="ba186-150">このサービスは、受信メッセージのペイロードに対して BizTalk マップを実行します。</span><span class="sxs-lookup"><span data-stu-id="ba186-150">This service executes BizTalk maps against the payload of an inbound message.</span></span> <span data-ttu-id="ba186-151">サービスは、変換要件を検証し、ドキュメント仕様の名前とメッセージの種類が含まれている BizTalk コンテキスト プロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="ba186-151">The service validates transform requirements and updates the BizTalk context properties that contain the document specification name and the message type.</span></span> <span data-ttu-id="ba186-152">ESB ディスパッチャーは、変換サービスの名前、ESB ディスパッチャー パイプライン コンポーネントの対応するプロパティに表示される場合のみ、このサービスを実行します。</span><span class="sxs-lookup"><span data-stu-id="ba186-152">The ESB Dispatcher executes this service only if this is the name of the transform service as it appears in the corresponding property of the ESB Dispatcher pipeline component.</span></span>  

    -   <span data-ttu-id="ba186-153">**Microsoft.Practices.ESB.Services.Routing します。**</span><span class="sxs-lookup"><span data-stu-id="ba186-153">**Microsoft.Practices.ESB.Services.Routing.**</span></span> <span data-ttu-id="ba186-154">このサービスでは、リゾルバーとアダプターのプロバイダー フレームワークを使用して、適切なエンドポイントのルーティング情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="ba186-154">This service uses the Resolver and Adapter Provider Framework to set the appropriate endpoint routing information.</span></span> <span data-ttu-id="ba186-155">ESB ディスパッチャーは、ルーティング サービスの名前、ESB ディスパッチャー パイプライン コンポーネントの対応するプロパティに表示される場合のみ、このサービスを実行します。</span><span class="sxs-lookup"><span data-stu-id="ba186-155">The ESB Dispatcher executes this service only if this is the name of the routing service as it appears in the corresponding property of the ESB Dispatcher pipeline component.</span></span>