---
title: "パイプライン コンポーネントを使用して、既存の日程を選択する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b93c5cb6-071f-485d-b0bb-22f95bafa3d0
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a733da2348de13120ce37a205b77d2e8194c7790
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-a-pipeline-component-to-select-an-existing-itinerary"></a><span data-ttu-id="3d34f-102">パイプライン コンポーネントを使用して、既存の日程を選択するには</span><span class="sxs-lookup"><span data-stu-id="3d34f-102">Using a Pipeline Component to Select an Existing Itinerary</span></span>
## <a name="esb-itinerary-selector-pipeline-component"></a><span data-ttu-id="3d34f-103">ESB Itinerary セレクター パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3d34f-103">ESB Itinerary Selector Pipeline Component</span></span>  
 <span data-ttu-id="3d34f-104">Itinerary ヘッダーなしジェネリック itinerary での傾斜を使用して送信されたメッセージが送信されます。</span><span class="sxs-lookup"><span data-stu-id="3d34f-104">Messages submitted using generic itinerary on-ramps are submitted without an itinerary header.</span></span> <span data-ttu-id="3d34f-105">適切な旅程を解決し、受信メッセージにアタッチのランプは日程を中央のリポジトリからアクセスするように構成するメカニズムを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d34f-105">To resolve the appropriate itinerary and attach it to the incoming message, the on-ramp must provide a mechanism that can be configured to access itineraries from a central repository.</span></span>  
  
 <span data-ttu-id="3d34f-106">ESB 行程セレクター パイプライン コンポーネントでは、(既定では、SQL Server)、中央リポジトリに格納されているサーバー側行程の内容を解決するのには、特殊な競合回避モジュール、と共に競合回避モジュールの接続文字列を使用します。</span><span class="sxs-lookup"><span data-stu-id="3d34f-106">The ESB Itinerary Selector pipeline component uses a resolver connection string, in conjunction with specialized resolvers, to resolve the content of a server-side itinerary stored in a central repository (by default, SQL Server).</span></span>  
  
 <span data-ttu-id="3d34f-107">(SOAP ヘッダーで表される) ように、クライアントによって要求された行程のバージョンと名前を取得してメッセージ コンテキストから使用すると、ESB 行程セレクター パイプライン コンポーネントは、WCF での傾斜、行程静的競合回避モジュールと組み合わせて、および適切な行程の選択に使用します。</span><span class="sxs-lookup"><span data-stu-id="3d34f-107">When the ESB Itinerary Selector pipeline component is used in WCF on-ramps in conjunction with the ITINERARY-STATIC resolver, the name and version of the itinerary requested by the client (as represented in the SOAP header) is retrieved from the message context and is used to select the appropriate itinerary.</span></span>  
  
 <span data-ttu-id="3d34f-108">既定では、ESB 行程セレクター パイプライン コンポーネントは、次のパイプラインに存在します。</span><span class="sxs-lookup"><span data-stu-id="3d34f-108">By default, the ESB Itinerary Selector pipeline component resides in the following pipelines:</span></span>  
  
-   <span data-ttu-id="3d34f-109">ItinerarySelectReceive</span><span class="sxs-lookup"><span data-stu-id="3d34f-109">ItinerarySelectReceive</span></span>  
  
-   <span data-ttu-id="3d34f-110">ItinerarySelectReceivePassthrough</span><span class="sxs-lookup"><span data-stu-id="3d34f-110">ItinerarySelectReceivePassthrough</span></span>  
  
-   <span data-ttu-id="3d34f-111">ItinerarySelectReceiveXml</span><span class="sxs-lookup"><span data-stu-id="3d34f-111">ItinerarySelectReceiveXml</span></span>  
  
-   <span data-ttu-id="3d34f-112">ItinerarySelectSendReceive</span><span class="sxs-lookup"><span data-stu-id="3d34f-112">ItinerarySelectSendReceive</span></span>  
  
 <span data-ttu-id="3d34f-113">次のセクションでは、各コンポーネントの実行手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="3d34f-113">The following sections describe the steps performed by each component.</span></span>  
  
## <a name="esb-itinerary-selector-pipeline-component-processing-steps"></a><span data-ttu-id="3d34f-114">ESB Itinerary セレクター パイプライン コンポーネントの処理手順</span><span class="sxs-lookup"><span data-stu-id="3d34f-114">ESB Itinerary Selector Pipeline Component Processing Steps</span></span>  
 <span data-ttu-id="3d34f-115">ESB 行程セレクター パイプライン コンポーネントは、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3d34f-115">The ESB Itinerary Selector pipeline component executes the following steps:</span></span>  
  
-   <span data-ttu-id="3d34f-116">送信パーティは、処理対象のメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="3d34f-116">The submitting party submits a message for processing.</span></span> <span data-ttu-id="3d34f-117">行程セレクター コンポーネントは、決定し、メッセージの内容またはコンテキストに基づいて、itinerary ストアから適切な旅程を選択する、開発者によって構成されている、プロパティの接続文字列として指定された競合回避モジュールを使用します。</span><span class="sxs-lookup"><span data-stu-id="3d34f-117">The Itinerary Selector component uses a resolver specified as a property connection string, configured by the developer, to determine and select the appropriate itinerary from the itinerary store, based on message content or context.</span></span>  
  
-   <span data-ttu-id="3d34f-118">旅行計画を検証して itinerary; は null の場合は、既定値を事前設定する特定のプロパティを設定例えば：</span><span class="sxs-lookup"><span data-stu-id="3d34f-118">It validates the itinerary and sets specific properties to preset default values if they are null in the itinerary; for example:</span></span>  
  
    -   <span data-ttu-id="3d34f-119">サービスの数が 1 未満の場合は、コンポーネントは、例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="3d34f-119">If Service count is less than 1, the component throws an exception.</span></span>  
  
    -   <span data-ttu-id="3d34f-120">コンポーネント サービスの数、識別子の値を使用して itinerary ルート属性を設定します (**Uuid**)、開始時刻 (**BeginTime**)、およびこれは一方向または双方向の要求かどうか (**IsRequestResponse**)。</span><span class="sxs-lookup"><span data-stu-id="3d34f-120">The component sets the itinerary root attributes using the values for the Service count, the identifier (**Uuid**), the start time (**BeginTime**), and whether this is a one-way or two-way request (**IsRequestResponse**).</span></span>  
  
    -   <span data-ttu-id="3d34f-121">コンポーネントは、サービスを検証、識別子を設定および現在のサービス インスタンス (次に処理するサービス) を設定したうえで、すべての関連するリゾルバーを検証します。</span><span class="sxs-lookup"><span data-stu-id="3d34f-121">The component validates the services, sets the identifiers, sets the current service instance (the service to process next), and validates any associated resolvers.</span></span>  
  
    -   <span data-ttu-id="3d34f-122">コンポーネントは、次のプロパティを使用して itinerary の Microsoft BizTalk Server のセグメントを設定します。</span><span class="sxs-lookup"><span data-stu-id="3d34f-122">The component sets the Microsoft BizTalk Server segment of the itinerary using the following properties:</span></span>  
  
        -   <span data-ttu-id="3d34f-123">**correlationToken**</span><span class="sxs-lookup"><span data-stu-id="3d34f-123">**correlationToken**</span></span>  
  
        -   <span data-ttu-id="3d34f-124">**reqRespTransmitPipelineID**</span><span class="sxs-lookup"><span data-stu-id="3d34f-124">**reqRespTransmitPipelineID**</span></span>  
  
        -   <span data-ttu-id="3d34f-125">**interchangeId**</span><span class="sxs-lookup"><span data-stu-id="3d34f-125">**interchangeId**</span></span>  
  
        -   <span data-ttu-id="3d34f-126">**receiveInstanceId**</span><span class="sxs-lookup"><span data-stu-id="3d34f-126">**receiveInstanceId**</span></span>  
  
        -   <span data-ttu-id="3d34f-127">**epmRRCorrelationToken**</span><span class="sxs-lookup"><span data-stu-id="3d34f-127">**epmRRCorrelationToken**</span></span>  
  
    -   <span data-ttu-id="3d34f-128">コンポーネントは、システム Properties.xsd スキーマで定義されたプロパティを使用して次の表に、BizTalk メッセージ コンテキスト プロパティを変更した日程を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="3d34f-128">The component writes the modified itinerary to the BizTalk message context properties listed in the following table using the properties defined in the System-Properties.xsd schema.</span></span>  
  
        |<span data-ttu-id="3d34f-129">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="3d34f-129">Properties</span></span>|  
        |----------------|  
        |<span data-ttu-id="3d34f-130">**名前 ItineraryHeader を =**</span><span class="sxs-lookup"><span data-stu-id="3d34f-130">**Name = ItineraryHeader**</span></span>|  
        |<span data-ttu-id="3d34f-131">**Namespace http://schemas.microsoft.biztalk.practices.esb.com/itinerary/system-properties を =**</span><span class="sxs-lookup"><span data-stu-id="3d34f-131">**Namespace = http://schemas.microsoft.biztalk.practices.esb.com/itinerary/system-properties**</span></span>|  
  
    -   <span data-ttu-id="3d34f-132">コンポーネントは、システム Properties.xsd スキーマで定義されている値を使用して次の表に示す 4 つの BizTalk コンテキスト プロパティを昇格させます。</span><span class="sxs-lookup"><span data-stu-id="3d34f-132">The component promotes the four BizTalk context properties listed in the following table using the values defined in the System-Properties.xsd schema.</span></span>  
  
        |<span data-ttu-id="3d34f-133">プロパティ</span><span class="sxs-lookup"><span data-stu-id="3d34f-133">Property</span></span>|<span data-ttu-id="3d34f-134">値</span><span class="sxs-lookup"><span data-stu-id="3d34f-134">Value</span></span>|  
        |--------------|-----------|  
        |<span data-ttu-id="3d34f-135">**サービス名**</span><span class="sxs-lookup"><span data-stu-id="3d34f-135">**ServiceName**</span></span>|<span data-ttu-id="3d34f-136">旅行計画で定義されている現在のサービス インスタンスの名前。</span><span class="sxs-lookup"><span data-stu-id="3d34f-136">The name of the current service instance defined in the itinerary.</span></span>|  
        |<span data-ttu-id="3d34f-137">**ServiceType**</span><span class="sxs-lookup"><span data-stu-id="3d34f-137">**ServiceType**</span></span>|<span data-ttu-id="3d34f-138">いずれかに設定**オーケストレーション**または**メッセージング**です。</span><span class="sxs-lookup"><span data-stu-id="3d34f-138">Set to either **Orchestration** or **Messaging**.</span></span>|  
        |<span data-ttu-id="3d34f-139">**IsRequestResponse**</span><span class="sxs-lookup"><span data-stu-id="3d34f-139">**IsRequestResponse**</span></span>|<span data-ttu-id="3d34f-140">いずれかに設定**True**または**False**です。</span><span class="sxs-lookup"><span data-stu-id="3d34f-140">Set to either **True** or **False**.</span></span>|  
        |<span data-ttu-id="3d34f-141">**ServiceState**</span><span class="sxs-lookup"><span data-stu-id="3d34f-141">**ServiceState**</span></span>|<span data-ttu-id="3d34f-142">設定**保留**です。</span><span class="sxs-lookup"><span data-stu-id="3d34f-142">Set to **Pending**.</span></span>|  
  
## <a name="esb-dispatcher-pipeline-component-process-steps"></a><span data-ttu-id="3d34f-143">ESB ディスパッチャー パイプライン コンポーネント プロセスがステップ実行</span><span class="sxs-lookup"><span data-stu-id="3d34f-143">ESB Dispatcher Pipeline Component Process Steps</span></span>  
 <span data-ttu-id="3d34f-144">ESB ディスパッチャー パイプライン コンポーネントは、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3d34f-144">The ESB Dispatcher pipeline component executes the following steps:</span></span>  
  
-   <span data-ttu-id="3d34f-145">型の任意の itinerary ステップの実行を管理する**メッセージング**旅行計画を進めます。</span><span class="sxs-lookup"><span data-stu-id="3d34f-145">It manages the execution of any itinerary steps of type **Messaging** and advances the itinerary.</span></span> <span data-ttu-id="3d34f-146">ESB ディスパッチャー コンポーネントの場所に対応してロジックを実行生じる可能性があるメッセージの処理サイクルでの場所に基づく**受信受信**、**送信送信**、**送信受信**、または**送信受信**です。</span><span class="sxs-lookup"><span data-stu-id="3d34f-146">The ESB Dispatcher component is location-aware and executes logic based on its location in the messaging processing cycle, which could be **Receive Inbound**, **Send Transmit**, **Send Inbound**, or **Receive Outbound**.</span></span> <span data-ttu-id="3d34f-147">ESB ディスパッチャー パイプライン コンポーネントでは、Esb.config ファイルで指定された itinerary メッセージング サービスを ESB を開始します。</span><span class="sxs-lookup"><span data-stu-id="3d34f-147">The ESB Dispatcher pipeline component invokes ESB itinerary messaging services specified in the Esb.config file.</span></span> <span data-ttu-id="3d34f-148">既定では、ルーティングと変換のためには、このコンポーネントの構成プロパティは、次のサービスに関連付けられました。</span><span class="sxs-lookup"><span data-stu-id="3d34f-148">By default, the configuration properties of this component for routing and transformation are associated with the following services:</span></span>  
  
    -   <span data-ttu-id="3d34f-149">**Microsoft.Practices.ESB.Services.Transform**です。</span><span class="sxs-lookup"><span data-stu-id="3d34f-149">**Microsoft.Practices.ESB.Services.Transform**.</span></span> <span data-ttu-id="3d34f-150">このサービスは、受信メッセージのペイロードに対して BizTalk マップを実行します。</span><span class="sxs-lookup"><span data-stu-id="3d34f-150">This service executes BizTalk maps against the payload of an inbound message.</span></span> <span data-ttu-id="3d34f-151">サービスは、変換要件を検証し、ドキュメント仕様の名前とメッセージの種類を含む BizTalk コンテキスト プロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="3d34f-151">The service validates transform requirements and updates the BizTalk context properties that contain the document specification name and the message type.</span></span> <span data-ttu-id="3d34f-152">ESB ディスパッチャーは、変換サービスの名前、ESB ディスパッチャー パイプライン コンポーネントの対応するプロパティに表示される場合のみ、このサービスを実行します。</span><span class="sxs-lookup"><span data-stu-id="3d34f-152">The ESB Dispatcher executes this service only if this is the name of the transform service as it appears in the corresponding property of the ESB Dispatcher pipeline component.</span></span>  
  
    -   <span data-ttu-id="3d34f-153">**Microsoft.Practices.ESB.Services.Routing です。**</span><span class="sxs-lookup"><span data-stu-id="3d34f-153">**Microsoft.Practices.ESB.Services.Routing.**</span></span> <span data-ttu-id="3d34f-154">このサービスでは、競合回避モジュールとアダプターのプロバイダー フレームワークを使用して、適切なエンドポイントのルーティング情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="3d34f-154">This service uses the Resolver and Adapter Provider Framework to set the appropriate endpoint routing information.</span></span> <span data-ttu-id="3d34f-155">ESB ディスパッチャーは、これは、ルーティング サービスの名前、ESB ディスパッチャー パイプライン コンポーネントの対応するプロパティに表示される場合にのみ、このサービスを実行します。</span><span class="sxs-lookup"><span data-stu-id="3d34f-155">The ESB Dispatcher executes this service only if this is the name of the routing service as it appears in the corresponding property of the ESB Dispatcher pipeline component.</span></span>