---
title: "パイプライン コンポーネントを使用して、日程を読み取る |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7e3b40c7-0f17-4d33-a26f-f51346a98be5
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bceec4df732247be043e006b52c7abbfbf6a6b24
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-a-pipeline-component-to-read-an-itinerary"></a><span data-ttu-id="34392-102">パイプライン コンポーネントを使用して、日程を読み取る</span><span class="sxs-lookup"><span data-stu-id="34392-102">Using a Pipeline Component to Read an Itinerary</span></span>
<span data-ttu-id="34392-103">受信パイプラインで受信するメッセージには、その処理要件 (クライアント側行程) を定義する SOAP ヘッダー内のメタデータを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="34392-103">A message that arrives in a receive pipeline can contain metadata in its SOAP header that defines its processing requirements (client-side itinerary).</span></span> <span data-ttu-id="34392-104">図 1 は、ESB 行程 ESB ディスパッチャー パイプライン コンポーネントの使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="34392-104">Figure 1 illustrates the use of the ESB Itinerary and ESB Dispatcher pipeline components.</span></span>  
  
 <span data-ttu-id="34392-105">![パイプライン コンポーネントの読み取り](../esb-toolkit/media/ch4-pipelinecomponentread.gif "Ch4 PipelineComponentRead")</span><span class="sxs-lookup"><span data-stu-id="34392-105">![Pipeline Component Read](../esb-toolkit/media/ch4-pipelinecomponentread.gif "Ch4-PipelineComponentRead")</span></span>  
  
 <span data-ttu-id="34392-106">**図 1**</span><span class="sxs-lookup"><span data-stu-id="34392-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="34392-107">**ESB 行程パイプライン コンポーネントの例**</span><span class="sxs-lookup"><span data-stu-id="34392-107">**Example of an ESB Itinerary pipeline component**</span></span>  
  
 <span data-ttu-id="34392-108">ESB 行程パイプライン コンポーネントを使用して、ESB によって適用される処理を定義するコンテキスト プロパティとしてメッセージからのメタデータをキャプチャできます。</span><span class="sxs-lookup"><span data-stu-id="34392-108">An ESB Itinerary pipeline component can be used to capture the metadata from a message as context properties that can define the processing applied by the ESB.</span></span>  
  
 <span data-ttu-id="34392-109">次のセクションでは、各コンポーネントの実行手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="34392-109">The following sections describe the steps performed by each component.</span></span>  
  
## <a name="esb-itinerary-pipeline-component-process-steps"></a><span data-ttu-id="34392-110">ESB Itinerary パイプライン コンポーネント プロセスがステップ実行</span><span class="sxs-lookup"><span data-stu-id="34392-110">ESB Itinerary Pipeline Component Process Steps</span></span>  
 <span data-ttu-id="34392-111">図 1 の例では、ESB 行程パイプライン コンポーネントは、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="34392-111">In the example shown in Figure 1, the ESB Itinerary pipeline component executes the following steps:</span></span>  
  
-   <span data-ttu-id="34392-112">行程 SOAP ヘッダーを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="34392-112">It reads the itinerary SOAP header.</span></span> <span data-ttu-id="34392-113">送信パーティは、そのユーザーは、メッセージを送信するときに、SOAP ヘッダーを設定することで、日程を設定します。</span><span class="sxs-lookup"><span data-stu-id="34392-113">The submitting party sets the itinerary by populating the SOAP header when he or she submits the message.</span></span> <span data-ttu-id="34392-114">一連の BizTalk メッセージ コンテキスト プロパティを表す SOAP ヘッダーです。これらのプロパティは、使用されている Web サービス アダプターの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="34392-114">A series of BizTalk message context properties represent the SOAP header; these properties vary, depending on the type of Web service adapter that is used.</span></span> <span data-ttu-id="34392-115">関連する Web サービス アダプターを次に示します。</span><span class="sxs-lookup"><span data-stu-id="34392-115">The following are the relevant Web service adapters:</span></span>  
  
    -   <span data-ttu-id="34392-116">**WCF アダプター。**</span><span class="sxs-lookup"><span data-stu-id="34392-116">**WCF adapter.**</span></span> <span data-ttu-id="34392-117">このアダプターは、SOAP ヘッダーを解析し、次の表に、BizTalk メッセージ コンテキスト プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="34392-117">This adapter parses the SOAP headers and populates the BizTalk message context properties listed in the following table.</span></span>  
  
        |<span data-ttu-id="34392-118">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="34392-118">Properties</span></span>|  
        |----------------|  
        |<span data-ttu-id="34392-119">**名前旅程を =**</span><span class="sxs-lookup"><span data-stu-id="34392-119">**Name = Itinerary**</span></span>|  
        |<span data-ttu-id="34392-120">**Namespace http://schemas.microsoft.biztalk.practices.esb.com/itinerary を =**</span><span class="sxs-lookup"><span data-stu-id="34392-120">**Namespace = http://schemas.microsoft.biztalk.practices.esb.com/itinerary**</span></span>|  
  
        > [!NOTE]
        >  <span data-ttu-id="34392-121">既定では、Windows Communication Foundation (WCF) アダプターは BizTalk コンテキストとして ItineraryDescription.xsd (ESB 行程 SOAP ヘッダーを生成するこのスキーマが使用されます) という名前のスキーマのルート名を使用して**名前**引数BizTalk コンテキストとして、スキーマのターゲットの名前空間を使用して**Namespace**引数。</span><span class="sxs-lookup"><span data-stu-id="34392-121">By default, the Windows Communication Foundation (WCF) adapter uses the root name of the schema named ItineraryDescription.xsd (this schema is used to generate the ESB Itinerary SOAP header) as the BizTalk context **Name** argument, and it uses the target namespace of the schema as the BizTalk context **Namespace** argument.</span></span>  
  
    -   <span data-ttu-id="34392-122">**SOAP アダプター。**</span><span class="sxs-lookup"><span data-stu-id="34392-122">**SOAP adapter.**</span></span> <span data-ttu-id="34392-123">このアダプターは、SOAP ヘッダーを解析し、次の表に、BizTalk メッセージ コンテキスト プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="34392-123">This adapter parses the SOAP headers and populates the BizTalk message context properties listed in the following table.</span></span>  
  
        |<span data-ttu-id="34392-124">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="34392-124">Properties</span></span>|  
        |----------------|  
        |<span data-ttu-id="34392-125">**名前旅程を =**</span><span class="sxs-lookup"><span data-stu-id="34392-125">**Name = Itinerary**</span></span>|  
        |<span data-ttu-id="34392-126">**Namespace http://schemas.microsoft.com/BizTalk/2003/SOAPHeader を =**</span><span class="sxs-lookup"><span data-stu-id="34392-126">**Namespace = http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**</span></span>|  
  
        > [!NOTE]
        >  <span data-ttu-id="34392-127">既定では、SOAP アダプターは BizTalk コンテキストとして Itinerary.xsd (ESB 行程 SOAP ヘッダーを生成するこのスキーマが使用されます) という名前のスキーマのルート名を使用**名前**に SOAP ヘッダーの名前空間を使用して、引数、BizTalk コンテキスト**Namespace**引数。</span><span class="sxs-lookup"><span data-stu-id="34392-127">By default, the SOAP Adapter uses the root name of the schema named Itinerary.xsd (this schema is used to generate the ESB Itinerary SOAP header) as the BizTalk context **Name** argument, and it uses the namespace of the SOAP header as the BizTalk context **Namespace** argument.</span></span>  
  
-   <span data-ttu-id="34392-128">メッセージ コンテキストから元の itinerary 値を削除します。</span><span class="sxs-lookup"><span data-stu-id="34392-128">It removes the original itinerary value from the message context.</span></span>  
  
-   <span data-ttu-id="34392-129">旅行計画を検証して itinerary; は null の場合は、既定値を事前設定する特定のプロパティを設定例えば：</span><span class="sxs-lookup"><span data-stu-id="34392-129">It validates the itinerary and sets specific properties to preset default values if they are null in the itinerary; for example:</span></span>  
  
    -   <span data-ttu-id="34392-130">サービスの数が 1 未満の場合は、コンポーネントは、例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="34392-130">If Service count is less than 1, the component throws an exception.</span></span>  
  
    -   <span data-ttu-id="34392-131">コンポーネント サービスの数、識別子の値を使用して itinerary ルート属性を設定します (**Uuid**)、開始時刻 (**BeginTime**)、およびこれは一方向または双方向の要求かどうか (**IsRequestResponse**)。</span><span class="sxs-lookup"><span data-stu-id="34392-131">The component sets the itinerary root attributes using the values for the Service count, the identifier (**Uuid**), the start time (**BeginTime**), and whether this is a one-way or two-way request (**IsRequestResponse**).</span></span>  
  
    -   <span data-ttu-id="34392-132">コンポーネントは、サービスを検証、識別子を設定および現在のサービス インスタンス (次に処理するサービス) を設定したうえで、すべての関連するリゾルバーを検証します。</span><span class="sxs-lookup"><span data-stu-id="34392-132">The component validates the services, sets the identifiers, sets the current service instance (the service to process next), and validates any associated resolvers.</span></span>  
  
    -   <span data-ttu-id="34392-133">コンポーネントは、次のプロパティを使用して itinerary の BizTalk セグメントを設定します。</span><span class="sxs-lookup"><span data-stu-id="34392-133">The component sets the BizTalk Segment of the itinerary using the following properties:</span></span>  
  
        -   <span data-ttu-id="34392-134">**correlationToken**</span><span class="sxs-lookup"><span data-stu-id="34392-134">**correlationToken**</span></span>  
  
        -   <span data-ttu-id="34392-135">**reqRespTransmitPipelineID**</span><span class="sxs-lookup"><span data-stu-id="34392-135">**reqRespTransmitPipelineID**</span></span>  
  
        -   <span data-ttu-id="34392-136">**interchangeId**</span><span class="sxs-lookup"><span data-stu-id="34392-136">**interchangeId**</span></span>  
  
        -   <span data-ttu-id="34392-137">**receiveInstanceId**</span><span class="sxs-lookup"><span data-stu-id="34392-137">**receiveInstanceId**</span></span>  
  
        -   <span data-ttu-id="34392-138">**epmRRCorrelationToken**</span><span class="sxs-lookup"><span data-stu-id="34392-138">**epmRRCorrelationToken**</span></span>  
  
    -   <span data-ttu-id="34392-139">コンポーネントは、システム Properties.xsd スキーマで定義されたプロパティを使用して次の表に、BizTalk メッセージ コンテキスト プロパティを変更した日程を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="34392-139">The component writes the modified itinerary to the BizTalk message context properties listed in the following table using the properties defined in the System-Properties.xsd schema.</span></span>  
  
        |<span data-ttu-id="34392-140">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="34392-140">Properties</span></span>|  
        |----------------|  
        |<span data-ttu-id="34392-141">**名前 ItineraryHeader を =**</span><span class="sxs-lookup"><span data-stu-id="34392-141">**Name = ItineraryHeader**</span></span>|  
        |<span data-ttu-id="34392-142">**Namespace http://schemas.microsoft.biztalk.practices.esb.com/itinerary/system-properties を =**</span><span class="sxs-lookup"><span data-stu-id="34392-142">**Namespace = http://schemas.microsoft.biztalk.practices.esb.com/itinerary/system-properties**</span></span>|  
  
    -   <span data-ttu-id="34392-143">コンポーネントは、システム Properties.xsd スキーマで定義されている値を使用して次の表に示す 4 つの BizTalk コンテキスト プロパティを昇格させます。</span><span class="sxs-lookup"><span data-stu-id="34392-143">The component promotes the four BizTalk context properties listed in the following table using the values defined in the System-Properties.xsd schema.</span></span>  
  
        |<span data-ttu-id="34392-144">プロパティ</span><span class="sxs-lookup"><span data-stu-id="34392-144">Property</span></span>|<span data-ttu-id="34392-145">値</span><span class="sxs-lookup"><span data-stu-id="34392-145">Value</span></span>|  
        |--------------|-----------|  
        |<span data-ttu-id="34392-146">**サービス名**</span><span class="sxs-lookup"><span data-stu-id="34392-146">**ServiceName**</span></span>|<span data-ttu-id="34392-147">旅行計画で定義されている現在のサービス インスタンスの名前。</span><span class="sxs-lookup"><span data-stu-id="34392-147">The name of the current service instance defined in the itinerary.</span></span>|  
        |<span data-ttu-id="34392-148">**ServiceType**</span><span class="sxs-lookup"><span data-stu-id="34392-148">**ServiceType**</span></span>|<span data-ttu-id="34392-149">いずれかに設定**オーケストレーション**または**メッセージング**</span><span class="sxs-lookup"><span data-stu-id="34392-149">Set to either **Orchestration** or **Messaging**</span></span>|  
        |<span data-ttu-id="34392-150">**IsRequestResponse**</span><span class="sxs-lookup"><span data-stu-id="34392-150">**IsRequestResponse**</span></span>|<span data-ttu-id="34392-151">いずれかに設定**True**または**False**</span><span class="sxs-lookup"><span data-stu-id="34392-151">Set to either **True** or **False**</span></span>|  
        |<span data-ttu-id="34392-152">**ServiceState**</span><span class="sxs-lookup"><span data-stu-id="34392-152">**ServiceState**</span></span>|<span data-ttu-id="34392-153">設定**保留中**</span><span class="sxs-lookup"><span data-stu-id="34392-153">Set to **Pending**</span></span>|  
  
## <a name="esb-dispatcher-pipeline-component-process-steps"></a><span data-ttu-id="34392-154">ESB ディスパッチャー パイプライン コンポーネント プロセスがステップ実行</span><span class="sxs-lookup"><span data-stu-id="34392-154">ESB Dispatcher Pipeline Component Process Steps</span></span>  
 <span data-ttu-id="34392-155">図 1 の例では、ESB ディスパッチャー パイプライン コンポーネントは、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="34392-155">In the example shown in Figure 1, the ESB Dispatcher pipeline component executes the following steps:</span></span>  
  
-   <span data-ttu-id="34392-156">型の任意の itinerary ステップの実行を管理する**メッセージング**旅行計画を進めます。</span><span class="sxs-lookup"><span data-stu-id="34392-156">It manages the execution of any itinerary steps of type **Messaging** and advances the itinerary.</span></span> <span data-ttu-id="34392-157">ESB ディスパッチャー コンポーネントの場所に対応してロジックを実行生じる可能性があるメッセージの処理サイクルでの場所に基づく**受信の受信、送信する送信**、**受信送信**、または**送信受信**です。</span><span class="sxs-lookup"><span data-stu-id="34392-157">The ESB Dispatcher component is location-aware and executes logic based on its location in the messaging processing cycle, which could be **Receive Inbound, Send Transmit**, **Send Inbound**, or **Receive Outbound**.</span></span> <span data-ttu-id="34392-158">ESB ディスパッチャー パイプライン コンポーネントでは、Esb.config ファイルで指定された itinerary メッセージング サービスを ESB を開始します。</span><span class="sxs-lookup"><span data-stu-id="34392-158">The ESB Dispatcher pipeline component invokes ESB itinerary messaging services specified in the Esb.config file.</span></span> <span data-ttu-id="34392-159">既定では、ルーティングと変換のためには、このコンポーネントの構成プロパティは、次のサービスに関連付けられました。</span><span class="sxs-lookup"><span data-stu-id="34392-159">By default, the configuration properties of this component for routing and transformation are associated with the following services:</span></span>  
  
    -   <span data-ttu-id="34392-160">**Microsoft.Practices.ESB.Services.Transform です。**</span><span class="sxs-lookup"><span data-stu-id="34392-160">**Microsoft.Practices.ESB.Services.Transform.**</span></span> <span data-ttu-id="34392-161">このサービスは、受信メッセージのペイロードに対して BizTalk マップを実行します。</span><span class="sxs-lookup"><span data-stu-id="34392-161">This service executes BizTalk maps against the payload of an inbound message.</span></span> <span data-ttu-id="34392-162">サービスは、変換要件を検証し、ドキュメント仕様の名前とメッセージの種類を含む BizTalk コンテキスト プロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="34392-162">The service validates transform requirements and updates the BizTalk context properties that contain the document specification name and the message type.</span></span> <span data-ttu-id="34392-163">ESB ディスパッチャーは、変換サービスの名前、ESB ディスパッチャー パイプライン コンポーネントの対応するプロパティに表示される場合のみ、このサービスを実行します。</span><span class="sxs-lookup"><span data-stu-id="34392-163">The ESB Dispatcher executes this service only if this is the name of the transform service as it appears in the corresponding property of the ESB Dispatcher pipeline component.</span></span>  
  
    -   <span data-ttu-id="34392-164">**Microsoft.Practices.ESB.Services.Routing です。**このサービスは、適切なエンドポイントのルーティング情報を設定するアダプター プロバイダーのフレームワークとの競合回避モジュールを使用します。</span><span class="sxs-lookup"><span data-stu-id="34392-164">**Microsoft.Practices.ESB.Services.Routing.**This service uses the Resolver and Adapter Provider Framework to set the appropriate endpoint routing information.</span></span> <span data-ttu-id="34392-165">ESB ディスパッチャーは、これは、ルーティング サービスの名前、ESB ディスパッチャー パイプライン コンポーネントの対応するプロパティに表示される場合にのみ、このサービスを実行します。</span><span class="sxs-lookup"><span data-stu-id="34392-165">The ESB Dispatcher executes this service only if this is the name of the routing service as it appears in the corresponding property of the ESB Dispatcher pipeline component.</span></span>