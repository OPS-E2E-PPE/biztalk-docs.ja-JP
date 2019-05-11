---
title: スキャッター/ギャザー サンプルのしくみ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ccfacb7-4fd2-4a1a-bece-27eedd86bbe9
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27b52b9ca48b381cf8032c5b33600ce349ce054c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279043"
---
# <a name="how-the-scatter-gather-sample-works"></a><span data-ttu-id="0e68e-102">スキャッター/ギャザー サンプルのしくみ</span><span class="sxs-lookup"><span data-stu-id="0e68e-102">How the Scatter-Gather Sample Works</span></span>
<span data-ttu-id="0e68e-103">サンプル アプリケーションは、スキャッター/ギャザー itinerary ファイルから読み込まれたスケジュールを格納している SOAP ヘッダーのセットを構築、ディスクから、指定されたメッセージ ファイルを読み込み、itinerary ヘッダーをメッセージに追加および入り口のを通じて ESB に送信します処理しています。</span><span class="sxs-lookup"><span data-stu-id="0e68e-103">The sample application builds a set of SOAP headers containing the itinerary loaded from the Scatter-Gather itinerary file, loads the specified message file from disk, appends the itinerary headers to the message, and submits it to the ESB through an on-ramp for processing.</span></span> <span data-ttu-id="0e68e-104">旅行プランは、応答を生成する場合、アプリケーションはこれを収集し、アプリケーション ウィンドウに表示します。</span><span class="sxs-lookup"><span data-stu-id="0e68e-104">If the itinerary generates a response, the application collects this and displays it in the application window.</span></span>  
  
 <span data-ttu-id="0e68e-105">スケジュール サービスがメッセージのスケジュールの情報を使用する方法を理解するためは、次のリストは、ScatterGatherItinerary.xml という名前のサンプルの itinerary 構成ファイルを示します。</span><span class="sxs-lookup"><span data-stu-id="0e68e-105">To help you understand how the Itinerary service uses the itinerary information in a message, the following listing shows the sample itinerary configuration file named ScatterGatherItinerary.xml.</span></span> <span data-ttu-id="0e68e-106">このスケジュールの最初のセクションでは、サービス呼び出しの 2 つの手順を指定します。</span><span class="sxs-lookup"><span data-stu-id="0e68e-106">The first section of this itinerary specifies two service invocation steps.</span></span>  
  
```xml  
<Itinerary xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"   
    xmlns:xsd="http://www.w3.org/2001/XMLSchema" uuid="" beginTime=""   
    completeTime="" state="Pending" isRequestResponse="false"   
    xmlns="http://schemas.microsoft.biztalk.practices.esb.com/itinerary">  
  <ServiceInstance uuid="" name="ScatterGather" type="Orchestration"  
                   state="Pending" position="0"   
                   isRequestResponse="false" xmlns="" />  
  <Services xmlns="">  
    <Service uuid="" beginTime="" completeTime="" name="ScatterGather"  
             type="Orchestration" state="Pending" isRequestResponse="false"  
             position="0" serviceInstanceId="" />  
  </Services>  
  <Services xmlns="">  
    <Service uuid="" beginTime="" completeTime="" name="DynamicTest"  
             type="Messaging" state="Pending" isRequestResponse="false"  
             position="1" serviceInstanceId="" />  
  </Services>  
</Itinerary>  
...  
```  
  
 <span data-ttu-id="0e68e-107">旅行プランのサービス呼び出しの手順の一覧は、競合回避モジュールと、次の XML に示すように、スケジュールで定義されている各サービスを検索するスケジュール サービスを許可する接続文字列の詳細を含むセクションです。</span><span class="sxs-lookup"><span data-stu-id="0e68e-107">Following the list of service invocation steps in the itinerary is the section containing details of the resolvers and connection strings that allow the Itinerary service to locate each service defined in the itinerary, as shown in the following XML.</span></span>  
  
```xml  
<ResolverGroups xmlns="">  
 <Resolvers serviceId="ScatterGather0"><![CDATA[BRE:\\policy=ResolveEndPointScatterGather;version=;useMsg=;]]><![CDATA[UDDI3:\\serverUrl=http://localhost/uddi;bindingKey=uddi:esb:purchaseordersubmitorderservicebinding;credentialType=Ntlm]]></Resolvers>  
<Resolvers serviceId="DynamicTest1"><![CDATA[UDDI3:\\serverUrl=http://localhost/uddi;bindingKey=uddi:esb:orderfileservicebinding;credentialType=Ntlm]]>  
</Resolvers>  
  </ResolverGroups>  
```  
  
 <span data-ttu-id="0e68e-108">この例で、アプリケーションの実行、SubmitPOService Web サービスの両方の競合回避モジュールの接続文字列をこのサービスの場所を解決するために 2 回 (http://localhost/ESB.CanadianServices/SubmitPOService.asmx)します。</span><span class="sxs-lookup"><span data-stu-id="0e68e-108">In this example, the application executes the SubmitPOService Web service twice because both resolver connection strings resolve to the location of this service (http://localhost/ESB.CanadianServices/SubmitPOService.asmx).</span></span> <span data-ttu-id="0e68e-109">メッセージ コンテキストは、として、次の例で定義されている最初のスケジュール サービスをアクティブ化するようにブローカ オーケストレーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="0e68e-109">The message context specifies the Broker orchestration as the first itinerary service to activate, defined in the sample as the following.</span></span>  
  
```csharp  
(Microsoft.Practices.ESB.Itinerary.Schemas.ServiceName == "ScatterGather")  
     && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceState ==   
    "Pending") && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceType   
    == "Orchestration")  
```  
  
 <span data-ttu-id="0e68e-110">ブローカ オーケストレーションは、スケジュールのステップの設定を分析し、スケジュールのステップに関連付けられた競合回避モジュールのコレクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="0e68e-110">The Broker orchestration analyzes the settings for its itinerary step and retrieves a collection of resolvers associated with the itinerary step.</span></span> <span data-ttu-id="0e68e-111">これらの競合回避モジュールごとに、オーケストレーションを使用して、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]リゾルバーとアダプター フレームワークは、サービス エンドポイントを解決します。</span><span class="sxs-lookup"><span data-stu-id="0e68e-111">For each of these resolvers, the orchestration uses the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Resolver and Adapter Framework to resolve the service endpoint.</span></span> <span data-ttu-id="0e68e-112">ブローカ オーケストレーションしをアクティブに n 個 ServiceDispatcher オーケストレーションの非同期的に (n は、スケジュールで ScatterGather サービスに関連付けられた競合回避モジュールの数) を次のパラメーターを含む要求メッセージをディスパッチします。</span><span class="sxs-lookup"><span data-stu-id="0e68e-112">The Broker orchestration then activates n number of ServiceDispatcher orchestrations asynchronously (where n is the number of resolvers associated with the ScatterGather service in the itinerary) to dispatch the request message with following parameters:</span></span>  
  
- <span data-ttu-id="0e68e-113">**TransportLocation**します。</span><span class="sxs-lookup"><span data-stu-id="0e68e-113">**TransportLocation**.</span></span> <span data-ttu-id="0e68e-114">競合回避モジュールは、このパラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="0e68e-114">The resolver populates this parameter.</span></span>  
  
- <span data-ttu-id="0e68e-115">**TransportType**します。</span><span class="sxs-lookup"><span data-stu-id="0e68e-115">**TransportType**.</span></span> <span data-ttu-id="0e68e-116">競合回避モジュールは、このパラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="0e68e-116">The resolver populates this parameter.</span></span>  
  
- <span data-ttu-id="0e68e-117">**ResolverDictionary**します。</span><span class="sxs-lookup"><span data-stu-id="0e68e-117">**ResolverDictionary**.</span></span> <span data-ttu-id="0e68e-118">このパラメーターには、競合回避モジュールのファクト具体的な競合回避モジュールのインスタンスによって設定のコレクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0e68e-118">This parameter contains a collection of resolver facts populated by the concrete resolver instance.</span></span>  
  
- <span data-ttu-id="0e68e-119">**InboundMessage**します。</span><span class="sxs-lookup"><span data-stu-id="0e68e-119">**InboundMessage**.</span></span> <span data-ttu-id="0e68e-120">このパラメーターには、旅行プランを含む元のメッセージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0e68e-120">This parameter contains the original message that contains the itinerary.</span></span>  
  
- <span data-ttu-id="0e68e-121">**ServiceResponsePort**します。</span><span class="sxs-lookup"><span data-stu-id="0e68e-121">**ServiceResponsePort**.</span></span> <span data-ttu-id="0e68e-122">このパラメーターは、自己関連付けを行うに ServiceDispatcher オーケストレーションのインスタンスからの応答を受信する応答のポートの名前です。</span><span class="sxs-lookup"><span data-stu-id="0e68e-122">This parameter is the name of the self-correlating response port that will receive responses from the instances of the ServiceDispatcher orchestration.</span></span>  
  
  <span data-ttu-id="0e68e-123">ServiceDispatcher オーケストレーションの各インスタンスでは、ResolveMapScatterGather ポリシーを使用して解決するには、Microsoft BizTalk マップの種類に基づいて、要求と応答メッセージの**TransportType**と**TransportLocation**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="0e68e-123">Each instance of the ServiceDispatcher orchestration uses the ResolveMapScatterGather policy to resolve the Microsoft BizTalk map types for the request and response message, based on **TransportType** and **TransportLocation** properties.</span></span> <span data-ttu-id="0e68e-124">オーケストレーション インスタンスでは、解決済みのマップを使用して、受信メッセージを Web サービス呼び出しの要求メッセージに変換します。</span><span class="sxs-lookup"><span data-stu-id="0e68e-124">The orchestration instances use the resolved maps to transform the inbound message into the request message for the Web service call.</span></span>  
  
  <span data-ttu-id="0e68e-125">ESB のアダプター マネージャーでは、どの BizTalk し、送信請求-応答ポートへの転送という ServiceRequestPort、要求メッセージの送信トランスポート コンテキスト プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="0e68e-125">The ESB Adapter Manager sets the outbound transport context properties on the request message, which BizTalk then forwards to the solicit-response port named ServiceRequestPort.</span></span>  
  
  <span data-ttu-id="0e68e-126">をサービスから応答メッセージを受信した場合、ServiceDispatcher オーケストレーションは受信応答メッセージを標準形式に変換する解決済みのマップ情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="0e68e-126">When it receives a response message from a service, the ServiceDispatcher orchestration uses the resolved map information to transform the inbound response message to a canonical format.</span></span> <span data-ttu-id="0e68e-127">ServiceResponse エンベロープ内で変更された応答をラップし、自己関連付けポートを通じてブローカ オーケストレーションに転送します。</span><span class="sxs-lookup"><span data-stu-id="0e68e-127">It then wraps the modified response within the ServiceResponse envelope and forwards it to the Broker orchestration through the self-correlating port.</span></span> <span data-ttu-id="0e68e-128">ブローカ オーケストレーションは、すべての着信応答を集計し、次のコードに示すように、GlobalBank.ESB.ScatterGather.Processes.AggregatingPipeline を使用して、最後の応答メッセージを準備します。</span><span class="sxs-lookup"><span data-stu-id="0e68e-128">The Broker orchestration aggregates all incoming responses and prepares the final response message using GlobalBank.ESB.ScatterGather.Processes.AggregatingPipeline, as shown in the following code.</span></span>  
  
```csharp  
AggregatedResponse.Body = null;  
AggregatedResponse(*) = InboundMessage(*);  
Microsoft.XLANGs.Pipeline.XLANGPipelineManager.ExecuteSendPipeline(  
    typeof(GlobalBank.ESB.ScatterGather.Processes.AggregatingPipeline),  
    messageAggregator,AggregatedResponse);  
```  
  
 <span data-ttu-id="0e68e-129">このコードは、定義済みのエンベロープ内の応答のバッチ全体をラップします。</span><span class="sxs-lookup"><span data-stu-id="0e68e-129">This code wraps the entire batch of responses within a predefined envelope.</span></span> <span data-ttu-id="0e68e-130">ブローカ オーケストレーションしするスケジュールを進めます、 **DynamicTest** itinerary の手順で次のコードに示すようにします。</span><span class="sxs-lookup"><span data-stu-id="0e68e-130">The Broker orchestration then advances the itinerary to the **DynamicTest** itinerary step, as shown in the following code.</span></span>  
  
```csharp  
// Copy the context and advance the itinerary.  
OutboundMessage = AggregatedResponse.Body;  
OutboundMessage(*) = AggregatedResponse(*);  
// Advance the Itinerary to the next step.  
itinerary.Itinerary.Advance(OutboundMessage, itineraryStep);  
```  
  
 <span data-ttu-id="0e68e-131">という名前のサービス型の属性のため**DynamicTest**に設定されている**メッセージング**、 **ItineraryHelper**クラスのコンテキストに競合回避モジュールのプロパティを昇格する、という名前のメッセージ**OutboundMessage**します。</span><span class="sxs-lookup"><span data-stu-id="0e68e-131">Because the service type attribute named **DynamicTest** is set to **Messaging**, the **ItineraryHelper** class promotes the resolver properties into the context of the message named **OutboundMessage**.</span></span> <span data-ttu-id="0e68e-132">ブローカ オーケストレーションは、このメッセージを BizTalk の直接バインド ポートに送信します。</span><span class="sxs-lookup"><span data-stu-id="0e68e-132">The Broker orchestration sends this message to a BizTalk direct-bound port.</span></span> <span data-ttu-id="0e68e-133">BizTalk によって表される動的送信ポートにメッセージを転送し、 **ServiceName**サブスクリプションの場合、これは**DynamicTest**します。</span><span class="sxs-lookup"><span data-stu-id="0e68e-133">BizTalk then forwards the message to the dynamic send port represented by the **ServiceName** subscription, which is **DynamicTest**.</span></span> <span data-ttu-id="0e68e-134">この送信ポートには、\Source\Samples\DynamicResolution\Test\Filedrop\Out フォルダーに集計された最後の応答がシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="0e68e-134">This send port serializes the final aggregated response to the \Source\Samples\DynamicResolution\Test\Filedrop\Out folder.</span></span>