---
title: "Itinerary 入り口サンプルの動作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6f4f318c-b955-4a3d-88db-c0d324b63b21
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6c8af93f93e6acba6a0d2cffb69186715ccd49e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-the-itinerary-on-ramp-sample-works"></a><span data-ttu-id="4256c-102">Itinerary 入り口サンプルの動作</span><span class="sxs-lookup"><span data-stu-id="4256c-102">How the Itinerary On-Ramp Sample Works</span></span>
<span data-ttu-id="4256c-103">サンプル行程テスト用クライアント アプリケーションがビルドされたら、クライアント アプリケーションのウィンドウでコントロールを使用して作成した日程を含む SOAP ヘッダーのセットがディスクから指定されたメッセージ ファイルを読み込み、itinerary ヘッダーをメッセージに追加し、ESB 行程入り口処理を通じてに送信します。</span><span class="sxs-lookup"><span data-stu-id="4256c-103">The sample Itinerary Test Client application builds a set of SOAP headers that contain the itinerary that you create using the controls in the client application window, loads the specified message file from disk, appends the itinerary headers to the message, and submits it to the ESB through an Itinerary on-ramp for processing.</span></span> <span data-ttu-id="4256c-104">旅行計画は、応答を生成する場合、アプリケーションは、応答を収集し、アプリケーション ウィンドウに表示します。</span><span class="sxs-lookup"><span data-stu-id="4256c-104">If the itinerary generates a response, the application collects the response and displays it in the application window.</span></span>  
  
 <span data-ttu-id="4256c-105">オーケストレーション、メッセージ、または両方の組み合わせを使用する一方向と双方向のシナリオを表示するいくつかのサンプル itinerary 構成ファイルから選択できます。</span><span class="sxs-lookup"><span data-stu-id="4256c-105">You can choose from several sample itinerary configuration files to see one-way and two-way scenarios that use orchestrations, messaging, or a combination of both.</span></span>  
  
 <span data-ttu-id="4256c-106">行程サービスがメッセージの道順の情報を使用する方法を理解するためは、次の XML は、TwoWay-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml 先ほどの例で使用されるという名前のサンプル itinerary 構成ファイルを示します。</span><span class="sxs-lookup"><span data-stu-id="4256c-106">To help you understand how the Itinerary service uses the itinerary information in a message, the following XML shows the sample itinerary configuration file named TwoWay-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml used in the earlier example.</span></span> <span data-ttu-id="4256c-107">この行程の最初のセクションでは、次の 3 つのサービス呼び出しのステップを指定します。</span><span class="sxs-lookup"><span data-stu-id="4256c-107">The first section of this itinerary specifies three service invocation steps.</span></span>  
  
```xml  
<Itinerary xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" uuid="" beginTime="" completeTime="" state="Pending" isRequestResponse="false" servicecount="0" xmlns="http://schemas.microsoft.biztalk.practices.esb.com/itinerary">  
  <BizTalkSegment interchangeId="" epmRRCorrelationToken="" receiveInstanceId="" messageId="" xmlns="" />  
  <ServiceInstance name="Microsoft.Practices.ESB.Services.Transform" type="Orchestration" state="Pending" position="0" isRequestResponse="false" xmlns="" />  
  <Services xmlns="">  
    <Service uuid="92d3b293-e6d4-44a1-b27d-c42b48aec667" beginTime="" completeTime="" name="Microsoft.Practices.ESB.Services.Transform" type="Orchestration" state="Pending" isRequestResponse="false" position="0" serviceInstanceId="" />  
  </Services>  
  <Services xmlns="">  
    <Service uuid="774488bc-e5b9-4a4e-9ae7-d25cdf23fd1c" beginTime="" completeTime="" name="Microsoft.Practices.ESB.Services.Routing" type="Orchestration" state="Pending" isRequestResponse="false" position="1" serviceInstanceId="" />  
  </Services>  
  <Services xmlns="">  
    <Service uuid="" beginTime="" completeTime="" name="ProcessAndRespond" type="Orchestration" state="Pending" isRequestResponse="true" position="2" serviceInstanceId="" />  
  </Services>  
  ...  
```  
  
 <span data-ttu-id="4256c-108">行程サービスを検索するかで定義されている各サービスの解決策情報を提供できるようにのリゾルバー (接続文字列で表される) の詳細を含むセクションは、次の旅行計画でのサービス呼び出しの手順の一覧、行程です。</span><span class="sxs-lookup"><span data-stu-id="4256c-108">Following the list of service invocation steps in the itinerary is the section containing details of the resolvers (represented by connection strings) that allow the Itinerary service to locate or provide resolution information for each service defined in the itinerary.</span></span>  
  
```xml  
  ...  
<ResolverGroups xmlns="">  
    <Resolvers serviceId="Microsoft.Practices.ESB.Services.Transform0"><![CDATA[BRE:\\Policy=ResolveMap;Version=1.0;UseMsg=False;]]></Resolvers>  
    <Resolvers serviceId="Microsoft.Practices.ESB.Services.Routing1"><![CDATA[STATIC:\\TransportType=FILE;TransportLocation=C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\OUt\%MessageID%.xml;Action=;EndpointConfig=;JaxRpcResponse=False;MessageExchangePattern=;TargetNamespace=;TransformType=;]]><![CDATA[UDDI3:\\ServerUrl=http://localhost/uddi;SearchQualifiers=andAllKeys;CategorySearch=;BindingKey=uddi:esb:orderfileservicev3.1;]]></Resolvers>  
    <Resolvers serviceId="ProcessAndRespond2" />  
  </ResolverGroups>  
</Itinerary>  
```  
  
> [!NOTE]
>  <span data-ttu-id="4256c-109">それぞれの実際のコンテンツ**\<リゾルバー >**要素に上記のリストで、行をラップするために使用する空白文字が含まれていません。</span><span class="sxs-lookup"><span data-stu-id="4256c-109">The actual content of each **\<Resolvers>** element does not contain the white space characters used to wrap the lines in the preceding listing.</span></span>  
  
 <span data-ttu-id="4256c-110">Itinerary 前の構成で定義されている 3 つの手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4256c-110">The following are the three steps defined in the itinerary preceding configuration:</span></span>  
  
1.  <span data-ttu-id="4256c-111">BizTalk ビジネス ルール エンジン (BRE) を使用して ResolverMap ポリシーを使用して、メッセージを変換する Microsoft.Practices.ESB.Services.Transform オーケストレーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="4256c-111">Execute the Microsoft.Practices.ESB.Services.Transform orchestration to transform the message with the ResolverMap policy using BizTalk Business Rules Engine (BRE).</span></span>  
  
2.  <span data-ttu-id="4256c-112">変換されたメッセージをルーティング Microsoft.Practices.ESB.Services.Routing1 を使用して複数の場所にルーティングする Microsoft.Practices.ESB.Services.Routing オーケストレーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="4256c-112">Execute the Microsoft.Practices.ESB.Services.Routing orchestration to route the transformed message to multiple locations using the routing Microsoft.Practices.ESB.Services.Routing1.</span></span> <span data-ttu-id="4256c-113"> **\<ResolverGroups >**セクションが含まれています、 **\<リゾルバー >**要素とこの識別子は、接続文字列を定義します。</span><span class="sxs-lookup"><span data-stu-id="4256c-113">The **\<ResolverGroups>** section contains a **\<Resolvers>** element with this identifier, which defines the connection strings.</span></span>  
  
3.  <span data-ttu-id="4256c-114">このサンプルで提供される ProcessAndRespond オーケストレーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="4256c-114">Execute the ProcessAndRespond orchestration provided with this sample.</span></span> <span data-ttu-id="4256c-115">このオーケストレーションの実装の応答として送信要求メッセージのコピー行程テスト クライアントに返送します。</span><span class="sxs-lookup"><span data-stu-id="4256c-115">The implementation of this orchestration sends as the response a copy of the request message back to the Itinerary Test Client.</span></span>  
  
 <span data-ttu-id="4256c-116">各サービスの補完機能で、サービスが itinerary を移動し、[次へ] サービスの状態に設定と、現在のサービス インスタンスである行程で定義されている昇格**保留**です。</span><span class="sxs-lookup"><span data-stu-id="4256c-116">With the completion of each service, the service advances the itinerary and promotes the next service defined in the itinerary to be the current service instance, with its state set to **Pending**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4256c-117">行程入り口サンプルでは、動的な解決を使用して、出力フォルダーにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="4256c-117">The Itinerary On-Ramp sample uses dynamic resolution to send messages to the output folder.</span></span> <span data-ttu-id="4256c-118">これは理由がない静的送信ポートこのサンプルに対して定義されています。</span><span class="sxs-lookup"><span data-stu-id="4256c-118">This is why there is no static send port defined for this sample.</span></span>  
  
 <span data-ttu-id="4256c-119">クライアント テスト アプリケーションがメッセージを送信した後に発生するイベントのシーケンスを次に示します。</span><span class="sxs-lookup"><span data-stu-id="4256c-119">The following is the sequence of events that occur after the test client application submits the message:</span></span>  
  
-   <span data-ttu-id="4256c-120">OnRamp.Itinerary 受信ポートがメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="4256c-120">The OnRamp.Itinerary receive port receives the message.</span></span>  
  
-   <span data-ttu-id="4256c-121">ItineraryReceiveXml パイプライン itinerary を SOAP ヘッダーから抽出を検証や事前処理、受信メッセージにメッセージ コンテキスト プロパティとして、日程を書き込みます and を BizTalk メッセージ ボックス データベースにメッセージを公開します。</span><span class="sxs-lookup"><span data-stu-id="4256c-121">The ItineraryReceiveXml pipeline extracts the itinerary from the SOAP header, validates and pre-processes it, writes the itinerary as a message context property into the inbound message, and publishes the message to the BizTalk Message Box database.</span></span>  
  
-   <span data-ttu-id="4256c-122">Microsoft.Practices.ESB.Services.Transform サービス オーケストレーションのサブスクリプションでは、このオーケストレーションの呼び出しをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="4256c-122">A subscription for the Microsoft.Practices.ESB.Services.Transform service orchestration triggers invocation of this orchestration.</span></span> <span data-ttu-id="4256c-123">オーケストレーションは、次のコードに示すように、パラメーターとして現在のメッセージを渡すことによって最初の現在の itinerary ステップを取得します。</span><span class="sxs-lookup"><span data-stu-id="4256c-123">The orchestration first retrieves the current itinerary step by passing the current message as a parameter, as shown in the following code.</span></span>  
  
    ```csharp  
    itineraryStep =   itinerary.Itinerary.GetItineraryStep(InboundMessage);  
    ```  
  
-   <span data-ttu-id="4256c-124">**ItineraryStep**実行のため、現在のサービス インスタンスに関するすべての情報と関連付けられているすべてのリゾルバー オブジェクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4256c-124">The **ItineraryStep** object contains all the information about the current service instance for execution, as well as any resolvers associated with it.</span></span>  
  
-   <span data-ttu-id="4256c-125">**リゾルバー**からオブジェクトを取得、 **ItineraryStep**インスタンスおよび、ESB リゾルバー Framework が使用される変換マップの完全な名前を解決するのには、次のコードに示すようにします。</span><span class="sxs-lookup"><span data-stu-id="4256c-125">The **Resolver** object is retrieved from the **ItineraryStep** instance and the ESB Resolver Framework is used to resolve the full name of the transformation map, as shown in the following code.</span></span>  
  
    ```csharp  
    resolverDictionary =   
       Microsoft.Practices.ESB.Resolver.ResolverMgr.Resolve(InboundMessage,  
                                                            resolver);  
  
    // Set the transform type.  
    transformType = resolverDictionary.Item("Resolver.TransformType");  
    ```  
  
-   <span data-ttu-id="4256c-126">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]型リゾルバーとアダプター フレームワークでこれを行う ResolverMap ポリシーを起動し、追加する (この例では、BizTalk ビジネス ルール エンジンの競合回避モジュール) のキャッシュから、適切な競合回避モジュールを読み込むことにより、 **ResolverDictionary**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="4256c-126">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Resolver and Adapter Framework accomplishes this by loading the appropriate resolver from the cache (in this example, the BizTalk Business Rules Engine resolver), which invokes the ResolverMap policy and populates the **ResolverDictionary** object.</span></span>  
  
-   <span data-ttu-id="4256c-127">オーケストレーションが完了すると、コードの呼び出し、 **AdvanceItinerary**メソッドを次のコードに示すようにします。</span><span class="sxs-lookup"><span data-stu-id="4256c-127">After the orchestration completes, the code calls the **AdvanceItinerary** method, as shown in the following code.</span></span>  
  
    ```csharp  
    // Call the Itinerary helper to advance to the next step.  
    itinerary.Itinerary.Advance(OutboundMessage, itineraryStep.ItineraryStep);  
    ```  
  
-   <span data-ttu-id="4256c-128">これは、そのプロパティを更新して、次に実行すると、日程で定義されている次のサービスを昇格によって現在の旅程を進めます。</span><span class="sxs-lookup"><span data-stu-id="4256c-128">This advances the current itinerary by updating its properties and promoting the next service defined in the itinerary as the one to execute next.</span></span> <span data-ttu-id="4256c-129">メソッドは、サービスの直接バインドの送信ポートを通じて、メッセージ ボックス データベースに公開、送信メッセージに旅行計画をコピーします。</span><span class="sxs-lookup"><span data-stu-id="4256c-129">The method copies the itinerary into the outbound message, which the service publishes back into the Message Box database through a direct-bound send port.</span></span>  
  
-   <span data-ttu-id="4256c-130">Microsoft.Practices.ESB.Services.Delivery サービス オーケストレーションのサブスクリプションでは、このオーケストレーションの呼び出しをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="4256c-130">A subscription for the Microsoft.Practices.ESB.Services.Delivery service orchestration triggers invocation of this orchestration.</span></span> <span data-ttu-id="4256c-131">このオーケストレーションでは、現在の日程ステップを取得する最初のブックマークに同様のプロセスに従います。</span><span class="sxs-lookup"><span data-stu-id="4256c-131">This orchestration follows a similar process to the first one, obtaining the current Itinerary step.</span></span> <span data-ttu-id="4256c-132">ただし、このオーケストレーションをによって返される競合回避モジュールのコレクションを反復処理して、 **ItineraryStep**インスタンス。</span><span class="sxs-lookup"><span data-stu-id="4256c-132">However, this orchestration iterates through a collection of resolvers returned by the **ItineraryStep** instance.</span></span> <span data-ttu-id="4256c-133">各競合回避モジュールのコレクション内で、配信のオーケストレーションを使用して、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]競合回避モジュールとアダプター フレームワークのトランスポートの場所を解決し、次のコードに示すように、送信メッセージ内のコンテキスト プロパティとして昇格します。</span><span class="sxs-lookup"><span data-stu-id="4256c-133">For each resolver in the collection, the delivery orchestration uses the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Resolver and Adapter Framework to resolve the transport locations and promote them as context properties within the outgoing message, as shown in the following code.</span></span>  
  
    ```csharp  
    // Move to retrieve the first resolver.  
    resolver = resolvers.Current;  
  
    // Pass the resolver configuration to the Resolver Manager   
    // for resolution.  
    resolverDictionary =  
       Microsoft.Practices.ESB.Resolver.ResolverMgr.Resolve(InboundMessage,  
                                                            resolver);  
  
    // Set the transport properties.  
    transportLocation =   
       resolverDictionary.Item("Resolver.TransportLocation");  
    transportType =   
       resolverDictionary.Item("Resolver.TransportType");  
  
    // Call the Adapter Manager to set all necessary properties.  
    Microsoft.Practices.ESB.Adapter.AdapterMgr.SetEndpoint(  
                                    resolverDictionary, DeliveryMessage);  
  
    // Set the delivery port address and type.  
    DeliveryPort(Microsoft.XLANGs.BaseTypes.Address) = transportLocation;  
    DeliveryPort(Microsoft.XLANGs.BaseTypes.TransportType) = transportType;  
    ```  
  
-   <span data-ttu-id="4256c-134">ProcessAndRespond オーケストレーションのサブスクリプションは、フィルター式のプロパティに対して定義されているメッセージ コンテキスト プロパティの照合のため、このオーケストレーションの呼び出しをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="4256c-134">A subscription for the ProcessAndRespond orchestration triggers invocation of this orchestration because of a match of the message context properties defined for the filter expression properties.</span></span>  
  
    ```  
    (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceName == :"ProcessAndRespond")   
    && Microsoft.Practices.ESB.Itinerary.Schemas.ServiceState == "Pending")  
    && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceType == "Orchestration")  
    ```  
  
-   <span data-ttu-id="4256c-135">ProcessAndRespond オーケストレーションは、旅行計画を進めるし、元の要求メッセージを応答として行程テスト用クライアント アプリケーションにランプでサービスに送信します。</span><span class="sxs-lookup"><span data-stu-id="4256c-135">The ProcessAndRespond orchestration advances the itinerary and sends the original request message back to the on-ramp service to the Itinerary Test Client application as the response.</span></span>