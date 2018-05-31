---
title: スキャッター/ギャザー サンプルの動作 |Microsoft ドキュメント
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
ms.openlocfilehash: c1221c038fa2e59636092c5cb49c6cbc40053708
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294922"
---
# <a name="how-the-scatter-gather-sample-works"></a><span data-ttu-id="2c49d-102">スキャッター/ギャザー サンプルのしくみ</span><span class="sxs-lookup"><span data-stu-id="2c49d-102">How the Scatter-Gather Sample Works</span></span>
<span data-ttu-id="2c49d-103">サンプル アプリケーション スキャッター/ギャザー itinerary ファイルから読み込まれた旅程を含む SOAP ヘッダーのセットが作成され、ディスクから指定されたメッセージ ファイルを読み込み、itinerary ヘッダーをメッセージに追加および入り口のを通じて ESB に送信処理しています。</span><span class="sxs-lookup"><span data-stu-id="2c49d-103">The sample application builds a set of SOAP headers containing the itinerary loaded from the Scatter-Gather itinerary file, loads the specified message file from disk, appends the itinerary headers to the message, and submits it to the ESB through an on-ramp for processing.</span></span> <span data-ttu-id="2c49d-104">旅行計画は、応答を生成する場合、アプリケーションはこれを収集し、アプリケーション ウィンドウに表示します。</span><span class="sxs-lookup"><span data-stu-id="2c49d-104">If the itinerary generates a response, the application collects this and displays it in the application window.</span></span>  
  
 <span data-ttu-id="2c49d-105">行程サービスがメッセージの道順の情報を使用する方法を理解するためは、次のリストは、ScatterGatherItinerary.xml をという名前のサンプル itinerary 構成ファイルを示します。</span><span class="sxs-lookup"><span data-stu-id="2c49d-105">To help you understand how the Itinerary service uses the itinerary information in a message, the following listing shows the sample itinerary configuration file named ScatterGatherItinerary.xml.</span></span> <span data-ttu-id="2c49d-106">この行程の最初のセクションでは、次の 2 つのサービス呼び出しのステップを指定します。</span><span class="sxs-lookup"><span data-stu-id="2c49d-106">The first section of this itinerary specifies two service invocation steps.</span></span>  
  
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
  
 <span data-ttu-id="2c49d-107">次の旅行計画でのサービス呼び出しの手順の一覧は、競合回避モジュールと旅程サービスの次の XML に示すように、旅行計画で定義された各サービスを検索するようにする接続文字列の詳細を含むセクションです。</span><span class="sxs-lookup"><span data-stu-id="2c49d-107">Following the list of service invocation steps in the itinerary is the section containing details of the resolvers and connection strings that allow the Itinerary service to locate each service defined in the itinerary, as shown in the following XML.</span></span>  
  
```xml  
<ResolverGroups xmlns="">  
 <Resolvers serviceId="ScatterGather0"><![CDATA[BRE:\\policy=ResolveEndPointScatterGather;version=;useMsg=;]]><![CDATA[UDDI3:\\serverUrl=http://localhost/uddi;bindingKey=uddi:esb:purchaseordersubmitorderservicebinding;credentialType=Ntlm]]></Resolvers>  
<Resolvers serviceId="DynamicTest1"><![CDATA[UDDI3:\\serverUrl=http://localhost/uddi;bindingKey=uddi:esb:orderfileservicebinding;credentialType=Ntlm]]>  
</Resolvers>  
  </ResolverGroups>  
```  
  
 <span data-ttu-id="2c49d-108">この例では、アプリケーション実行 SubmitPOService Web サービスの両方の競合回避モジュールの接続文字列が (http://localhost/ESB.CanadianServices/SubmitPOService.asmx) このサービスの場所を解決するために 2 回です。</span><span class="sxs-lookup"><span data-stu-id="2c49d-108">In this example, the application executes the SubmitPOService Web service twice because both resolver connection strings resolve to the location of this service (http://localhost/ESB.CanadianServices/SubmitPOService.asmx).</span></span> <span data-ttu-id="2c49d-109">メッセージ コンテキストをアクティブ化すると、最初の itinerary サービスで定義されている、サンプルを次のようにブローカ オーケストレーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="2c49d-109">The message context specifies the Broker orchestration as the first itinerary service to activate, defined in the sample as the following.</span></span>  
  
```csharp  
(Microsoft.Practices.ESB.Itinerary.Schemas.ServiceName == "ScatterGather")  
     && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceState ==   
    "Pending") && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceType   
    == "Orchestration")  
```  
  
 <span data-ttu-id="2c49d-110">ブローカ オーケストレーションは、その itinerary のステップの設定を分析し、itinerary ステップに関連付けられた競合回避モジュールのコレクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="2c49d-110">The Broker orchestration analyzes the settings for its itinerary step and retrieves a collection of resolvers associated with the itinerary step.</span></span> <span data-ttu-id="2c49d-111">これらの競合回避モジュールのそれぞれについて、オーケストレーションを使用して、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サービス エンドポイントを解決するのには型リゾルバーとアダプター フレームワークです。</span><span class="sxs-lookup"><span data-stu-id="2c49d-111">For each of these resolvers, the orchestration uses the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Resolver and Adapter Framework to resolve the service endpoint.</span></span> <span data-ttu-id="2c49d-112">ブローカ オーケストレーションしをアクティブに n 個 ServiceDispatcher オーケストレーションの非同期的に (n は itinerary で ScatterGather サービスに関連付けられている競合回避モジュールの数) を次のパラメーターを使用して要求メッセージをディスパッチします。</span><span class="sxs-lookup"><span data-stu-id="2c49d-112">The Broker orchestration then activates n number of ServiceDispatcher orchestrations asynchronously (where n is the number of resolvers associated with the ScatterGather service in the itinerary) to dispatch the request message with following parameters:</span></span>  
  
-   <span data-ttu-id="2c49d-113">**TransportLocation**です。</span><span class="sxs-lookup"><span data-stu-id="2c49d-113">**TransportLocation**.</span></span> <span data-ttu-id="2c49d-114">競合回避モジュールは、このパラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="2c49d-114">The resolver populates this parameter.</span></span>  
  
-   <span data-ttu-id="2c49d-115">**TransportType**です。</span><span class="sxs-lookup"><span data-stu-id="2c49d-115">**TransportType**.</span></span> <span data-ttu-id="2c49d-116">競合回避モジュールは、このパラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="2c49d-116">The resolver populates this parameter.</span></span>  
  
-   <span data-ttu-id="2c49d-117">**ResolverDictionary**です。</span><span class="sxs-lookup"><span data-stu-id="2c49d-117">**ResolverDictionary**.</span></span> <span data-ttu-id="2c49d-118">このパラメーターには、具体的な競合回避モジュール インスタンスによって設定の競合回避モジュールのファクトのコレクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2c49d-118">This parameter contains a collection of resolver facts populated by the concrete resolver instance.</span></span>  
  
-   <span data-ttu-id="2c49d-119">**InboundMessage**です。</span><span class="sxs-lookup"><span data-stu-id="2c49d-119">**InboundMessage**.</span></span> <span data-ttu-id="2c49d-120">このパラメーターには、旅行計画を含む元のメッセージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2c49d-120">This parameter contains the original message that contains the itinerary.</span></span>  
  
-   <span data-ttu-id="2c49d-121">**ServiceResponsePort**です。</span><span class="sxs-lookup"><span data-stu-id="2c49d-121">**ServiceResponsePort**.</span></span> <span data-ttu-id="2c49d-122">このパラメーターは、ServiceDispatcher オーケストレーションのインスタンスからの応答を受信する自己関連付けを行う応答のポートの名前です。</span><span class="sxs-lookup"><span data-stu-id="2c49d-122">This parameter is the name of the self-correlating response port that will receive responses from the instances of the ServiceDispatcher orchestration.</span></span>  
  
 <span data-ttu-id="2c49d-123">ServiceDispatcher オーケストレーションの各インスタンスは ResolveMapScatterGather ポリシーを使用して解決するには、Microsoft BizTalk マップの種類に基づいて、要求と応答メッセージを**TransportType**と**TransportLocation**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="2c49d-123">Each instance of the ServiceDispatcher orchestration uses the ResolveMapScatterGather policy to resolve the Microsoft BizTalk map types for the request and response message, based on **TransportType** and **TransportLocation** properties.</span></span> <span data-ttu-id="2c49d-124">オーケストレーション インスタンスでは、解決済みのマップを使用して、受信メッセージを Web サービス呼び出しの要求メッセージに変換します。</span><span class="sxs-lookup"><span data-stu-id="2c49d-124">The orchestration instances use the resolved maps to transform the inbound message into the request message for the Web service call.</span></span>  
  
 <span data-ttu-id="2c49d-125">ESB アダプター マネージャーでは、どの BizTalk し、送信請求-応答ポートへの転送という ServiceRequestPort、要求メッセージの送信トランスポート コンテキスト プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="2c49d-125">The ESB Adapter Manager sets the outbound transport context properties on the request message, which BizTalk then forwards to the solicit-response port named ServiceRequestPort.</span></span>  
  
 <span data-ttu-id="2c49d-126">サービスから応答メッセージを受け取ると、ServiceDispatcher オーケストレーションは、正規の形式への着信応答メッセージを変換するのに解決マップ情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="2c49d-126">When it receives a response message from a service, the ServiceDispatcher orchestration uses the resolved map information to transform the inbound response message to a canonical format.</span></span> <span data-ttu-id="2c49d-127">ServiceResponse エンベロープ内で変更された応答をラップし、自己関連付けポートを通じてブローカ オーケストレーションに転送します。</span><span class="sxs-lookup"><span data-stu-id="2c49d-127">It then wraps the modified response within the ServiceResponse envelope and forwards it to the Broker orchestration through the self-correlating port.</span></span> <span data-ttu-id="2c49d-128">ブローカ オーケストレーションは、すべての着信応答を集計し、次のコードに示すように、GlobalBank.ESB.ScatterGather.Processes.AggregatingPipeline を使用して、最後の応答メッセージを準備します。</span><span class="sxs-lookup"><span data-stu-id="2c49d-128">The Broker orchestration aggregates all incoming responses and prepares the final response message using GlobalBank.ESB.ScatterGather.Processes.AggregatingPipeline, as shown in the following code.</span></span>  
  
```csharp  
AggregatedResponse.Body = null;  
AggregatedResponse(*) = InboundMessage(*);  
Microsoft.XLANGs.Pipeline.XLANGPipelineManager.ExecuteSendPipeline(  
    typeof(GlobalBank.ESB.ScatterGather.Processes.AggregatingPipeline),  
    messageAggregator,AggregatedResponse);  
```  
  
 <span data-ttu-id="2c49d-129">このコードは、定義済みのエンベロープ内の応答のバッチ全体をラップします。</span><span class="sxs-lookup"><span data-stu-id="2c49d-129">This code wraps the entire batch of responses within a predefined envelope.</span></span> <span data-ttu-id="2c49d-130">ブローカのオーケストレーション、進めますに行程、 **DynamicTest** itinerary 手順、次のコードに示すようにします。</span><span class="sxs-lookup"><span data-stu-id="2c49d-130">The Broker orchestration then advances the itinerary to the **DynamicTest** itinerary step, as shown in the following code.</span></span>  
  
```csharp  
// Copy the context and advance the itinerary.  
OutboundMessage = AggregatedResponse.Body;  
OutboundMessage(*) = AggregatedResponse(*);  
// Advance the Itinerary to the next step.  
itinerary.Itinerary.Advance(OutboundMessage, itineraryStep);  
```  
  
 <span data-ttu-id="2c49d-131">サービス型の属性が名前付きため**DynamicTest**に設定されている**メッセージング**、 **ItineraryHelper**クラスのコンテキストに競合回避モジュールのプロパティを昇格する、という名前のメッセージ**OutboundMessage**です。</span><span class="sxs-lookup"><span data-stu-id="2c49d-131">Because the service type attribute named **DynamicTest** is set to **Messaging**, the **ItineraryHelper** class promotes the resolver properties into the context of the message named **OutboundMessage**.</span></span> <span data-ttu-id="2c49d-132">ブローカ オーケストレーションは、このメッセージを BizTalk の直接バインド ポートに送信します。</span><span class="sxs-lookup"><span data-stu-id="2c49d-132">The Broker orchestration sends this message to a BizTalk direct-bound port.</span></span> <span data-ttu-id="2c49d-133">BizTalk によって表される動的送信ポートにメッセージを転送し、 **ServiceName**サブスクリプションの場合、これは**DynamicTest**です。</span><span class="sxs-lookup"><span data-stu-id="2c49d-133">BizTalk then forwards the message to the dynamic send port represented by the **ServiceName** subscription, which is **DynamicTest**.</span></span> <span data-ttu-id="2c49d-134">この送信ポートは、\Source\Samples\DynamicResolution\Test\Filedrop\Out フォルダーに集計された最後の応答をシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="2c49d-134">This send port serializes the final aggregated response to the \Source\Samples\DynamicResolution\Test\Filedrop\Out folder.</span></span>