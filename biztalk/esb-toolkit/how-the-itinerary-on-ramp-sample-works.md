---
title: スケジュール オンランプ ランプでサンプルのしくみ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f4f318c-b955-4a3d-88db-c0d324b63b21
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f52d8442f777d67b31b99c4fef336d6a5e71f60
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400773"
---
# <a name="how-the-itinerary-on-ramp-sample-works"></a><span data-ttu-id="ad214-102">スケジュール オンランプ ランプでサンプルのしくみ</span><span class="sxs-lookup"><span data-stu-id="ad214-102">How the Itinerary On-Ramp Sample Works</span></span>
<span data-ttu-id="ad214-103">サンプル アプリケーションで、クライアント アプリケーションのウィンドウでコントロールを使用して作成したスケジュールが含まれている SOAP ヘッダーのセットを作成スケジュールのテスト用クライアント ディスクから、指定されたメッセージ ファイルを読み込み、itinerary ヘッダーをメッセージに追加し、ESB 行程入り口の処理に送信します。</span><span class="sxs-lookup"><span data-stu-id="ad214-103">The sample Itinerary Test Client application builds a set of SOAP headers that contain the itinerary that you create using the controls in the client application window, loads the specified message file from disk, appends the itinerary headers to the message, and submits it to the ESB through an Itinerary on-ramp for processing.</span></span> <span data-ttu-id="ad214-104">旅行プランは、応答を生成する場合、アプリケーションは、応答を収集し、アプリケーション ウィンドウに表示します。</span><span class="sxs-lookup"><span data-stu-id="ad214-104">If the itinerary generates a response, the application collects the response and displays it in the application window.</span></span>  

 <span data-ttu-id="ad214-105">オーケストレーション、メッセージング、またはその両方の組み合わせを使用する一方向と双方向のシナリオを表示するスケジュールの構成ファイルのサンプルをいくつかから選択することができます。</span><span class="sxs-lookup"><span data-stu-id="ad214-105">You can choose from several sample itinerary configuration files to see one-way and two-way scenarios that use orchestrations, messaging, or a combination of both.</span></span>  

 <span data-ttu-id="ad214-106">スケジュール サービスがメッセージのスケジュールの情報を使用する方法を理解するためは、次の XML は、TwoWay-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml 前の例で使用される名前付きサンプル スケジュールの構成ファイルを示します。</span><span class="sxs-lookup"><span data-stu-id="ad214-106">To help you understand how the Itinerary service uses the itinerary information in a message, the following XML shows the sample itinerary configuration file named TwoWay-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml used in the earlier example.</span></span> <span data-ttu-id="ad214-107">このスケジュールの最初のセクションでは、次の 3 つのサービス呼び出しのステップを指定します。</span><span class="sxs-lookup"><span data-stu-id="ad214-107">The first section of this itinerary specifies three service invocation steps.</span></span>  

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

 <span data-ttu-id="ad214-108">特定またはで定義されている各サービスの解決策情報を提供するスケジュール サービスを許可する (接続文字列で表されます)、リゾルバーの詳細を含むセクションには、旅行プランのサービス呼び出しのステップの一覧を次の旅行プラン。</span><span class="sxs-lookup"><span data-stu-id="ad214-108">Following the list of service invocation steps in the itinerary is the section containing details of the resolvers (represented by connection strings) that allow the Itinerary service to locate or provide resolution information for each service defined in the itinerary.</span></span>  

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
>  <span data-ttu-id="ad214-109">それぞれの実際のコンテンツ **\<リゾルバー\>** 要素に上記の一覧で、行をラップするために使用する空白文字が含まれていません。</span><span class="sxs-lookup"><span data-stu-id="ad214-109">The actual content of each **\<Resolvers\>** element does not contain the white space characters used to wrap the lines in the preceding listing.</span></span>  

 <span data-ttu-id="ad214-110">以下は、前のスケジュールの構成で定義されている 3 つの手順です。</span><span class="sxs-lookup"><span data-stu-id="ad214-110">The following are the three steps defined in the itinerary preceding configuration:</span></span>  

1. <span data-ttu-id="ad214-111">BizTalk ビジネス ルール エンジン (BRE) を使用して ResolverMap ポリシーを使用して、メッセージを変換する Microsoft.Practices.ESB.Services.Transform オーケストレーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="ad214-111">Execute the Microsoft.Practices.ESB.Services.Transform orchestration to transform the message with the ResolverMap policy using BizTalk Business Rules Engine (BRE).</span></span>  

2. <span data-ttu-id="ad214-112">変換されたメッセージをルーティング Microsoft.Practices.ESB.Services.Routing1 を使用して複数の場所にルーティングする Microsoft.Practices.ESB.Services.Routing オーケストレーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="ad214-112">Execute the Microsoft.Practices.ESB.Services.Routing orchestration to route the transformed message to multiple locations using the routing Microsoft.Practices.ESB.Services.Routing1.</span></span> <span data-ttu-id="ad214-113">**\<ResolverGroups\>** セクションが含まれています、 **\<リゾルバー\>** 要素とこの識別子は、接続文字列を定義します。</span><span class="sxs-lookup"><span data-stu-id="ad214-113">The **\<ResolverGroups\>** section contains a **\<Resolvers\>** element with this identifier, which defines the connection strings.</span></span>  

3. <span data-ttu-id="ad214-114">このサンプルで提供される ProcessAndRespond オーケストレーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="ad214-114">Execute the ProcessAndRespond orchestration provided with this sample.</span></span> <span data-ttu-id="ad214-115">応答として送信しますこのオーケストレーションの実装は旅行プランのテスト クライアントに要求メッセージのコピー。</span><span class="sxs-lookup"><span data-stu-id="ad214-115">The implementation of this orchestration sends as the response a copy of the request message back to the Itinerary Test Client.</span></span>  

   <span data-ttu-id="ad214-116">各サービスを完了したら、サービスが旅行計画を進めるし、現在のサービス インスタンス、その状態に設定するスケジュールで定義されている次のサービスを昇格させます**保留**します。</span><span class="sxs-lookup"><span data-stu-id="ad214-116">With the completion of each service, the service advances the itinerary and promotes the next service defined in the itinerary to be the current service instance, with its state set to **Pending**.</span></span>  

> [!NOTE]
>  <span data-ttu-id="ad214-117">行程入口サンプルでは、動的解決を使用して出力フォルダーにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="ad214-117">The Itinerary On-Ramp sample uses dynamic resolution to send messages to the output folder.</span></span> <span data-ttu-id="ad214-118">これは理由がない静的送信ポートをこのサンプルに対して定義されています。</span><span class="sxs-lookup"><span data-stu-id="ad214-118">This is why there is no static send port defined for this sample.</span></span>  

 <span data-ttu-id="ad214-119">テスト用クライアント アプリケーションがメッセージを送信した後に発生するイベントのシーケンスを次に示します。</span><span class="sxs-lookup"><span data-stu-id="ad214-119">The following is the sequence of events that occur after the test client application submits the message:</span></span>  

- <span data-ttu-id="ad214-120">受信ポートを OnRamp.Itinerary メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="ad214-120">The OnRamp.Itinerary receive port receives the message.</span></span>  

- <span data-ttu-id="ad214-121">ItineraryReceiveXml パイプライン旅行プランを SOAP ヘッダーから抽出します、検証し事前処理、旅行プランをメッセージ コンテキスト プロパティとして、受信メッセージに書き込みますおよび BizTalk メッセージ ボックス データベースには、メッセージを公開します。</span><span class="sxs-lookup"><span data-stu-id="ad214-121">The ItineraryReceiveXml pipeline extracts the itinerary from the SOAP header, validates and pre-processes it, writes the itinerary as a message context property into the inbound message, and publishes the message to the BizTalk Message Box database.</span></span>  

- <span data-ttu-id="ad214-122">Microsoft.Practices.ESB.Services.Transform サービス オーケストレーションのサブスクリプションでは、このオーケストレーションの呼び出しをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="ad214-122">A subscription for the Microsoft.Practices.ESB.Services.Transform service orchestration triggers invocation of this orchestration.</span></span> <span data-ttu-id="ad214-123">オーケストレーションは、まず次のコードに示すように、パラメーターとして現在のメッセージを渡すことによってスケジュールの現在のステップを取得します。</span><span class="sxs-lookup"><span data-stu-id="ad214-123">The orchestration first retrieves the current itinerary step by passing the current message as a parameter, as shown in the following code.</span></span>  

  ```csharp  
  itineraryStep =   itinerary.Itinerary.GetItineraryStep(InboundMessage);  
  ```  

- <span data-ttu-id="ad214-124">**ItineraryStep**オブジェクトには、実行するための現在のサービス インスタンスに関するすべての情報も関連付けられているすべてのリゾルバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ad214-124">The **ItineraryStep** object contains all the information about the current service instance for execution, as well as any resolvers associated with it.</span></span>  

- <span data-ttu-id="ad214-125">**リゾルバー**からオブジェクトを取得、 **ItineraryStep**インスタンスと ESB リゾルバー フレームワークが次のコードに示すように、変換マップの完全名の解決に使用されます。</span><span class="sxs-lookup"><span data-stu-id="ad214-125">The **Resolver** object is retrieved from the **ItineraryStep** instance and the ESB Resolver Framework is used to resolve the full name of the transformation map, as shown in the following code.</span></span>  

  ```csharp  
  resolverDictionary =   
     Microsoft.Practices.ESB.Resolver.ResolverMgr.Resolve(InboundMessage,  
                                                          resolver);  

  // Set the transform type.  
  transformType = resolverDictionary.Item("Resolver.TransformType");  
  ```  

- <span data-ttu-id="ad214-126">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]リゾルバーとアダプター フレームワークはこれを実現する ResolverMap ポリシーの呼び出しを設定します (この例では、BizTalk ビジネス ルール エンジンの競合回避モジュール) でキャッシュから、適切な競合回避モジュールを読み込み、 **ResolverDictionary**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ad214-126">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Resolver and Adapter Framework accomplishes this by loading the appropriate resolver from the cache (in this example, the BizTalk Business Rules Engine resolver), which invokes the ResolverMap policy and populates the **ResolverDictionary** object.</span></span>  

- <span data-ttu-id="ad214-127">オーケストレーションの完了後、コードの呼び出し、 **AdvanceItinerary**メソッドは、次のコードに示すようにします。</span><span class="sxs-lookup"><span data-stu-id="ad214-127">After the orchestration completes, the code calls the **AdvanceItinerary** method, as shown in the following code.</span></span>  

  ```csharp  
  // Call the Itinerary helper to advance to the next step.  
  itinerary.Itinerary.Advance(OutboundMessage, itineraryStep.ItineraryStep);  
  ```  

- <span data-ttu-id="ad214-128">これは、そのプロパティを更新し、次に実行する 1 つとして、スケジュールで定義されている次のサービスを昇格によって現在の旅程を進めます。</span><span class="sxs-lookup"><span data-stu-id="ad214-128">This advances the current itinerary by updating its properties and promoting the next service defined in the itinerary as the one to execute next.</span></span> <span data-ttu-id="ad214-129">メソッドは、直接バインドされた送信ポートを通じてメッセージ ボックス データベースにサービスを発行する、送信メッセージに旅行プランをコピーします。</span><span class="sxs-lookup"><span data-stu-id="ad214-129">The method copies the itinerary into the outbound message, which the service publishes back into the Message Box database through a direct-bound send port.</span></span>  

- <span data-ttu-id="ad214-130">Microsoft.Practices.ESB.Services.Delivery サービス オーケストレーションのサブスクリプションでは、このオーケストレーションの呼び出しをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="ad214-130">A subscription for the Microsoft.Practices.ESB.Services.Delivery service orchestration triggers invocation of this orchestration.</span></span> <span data-ttu-id="ad214-131">このオーケストレーションでは、現在のスケジュール ステップを取得する最初の 1 つに、同様のプロセスに従います。</span><span class="sxs-lookup"><span data-stu-id="ad214-131">This orchestration follows a similar process to the first one, obtaining the current Itinerary step.</span></span> <span data-ttu-id="ad214-132">ただし、このオーケストレーションがによって返される競合回避モジュールのコレクションを反復処理し、 **ItineraryStep**インスタンス。</span><span class="sxs-lookup"><span data-stu-id="ad214-132">However, this orchestration iterates through a collection of resolvers returned by the **ItineraryStep** instance.</span></span> <span data-ttu-id="ad214-133">コレクション内の各リゾルバーの配信のオーケストレーションを使用して、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]リゾルバーとアダプター フレームワークは、トランスポートの場所を解決し、次のコードに示すように、送信メッセージのコンテキスト プロパティとして昇格させることです。</span><span class="sxs-lookup"><span data-stu-id="ad214-133">For each resolver in the collection, the delivery orchestration uses the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Resolver and Adapter Framework to resolve the transport locations and promote them as context properties within the outgoing message, as shown in the following code.</span></span>  

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

- <span data-ttu-id="ad214-134">ProcessAndRespond オーケストレーションのサブスクリプションは、フィルター式のプロパティに対して定義されているメッセージ コンテキスト プロパティと一致するため、このオーケストレーションの呼び出しをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="ad214-134">A subscription for the ProcessAndRespond orchestration triggers invocation of this orchestration because of a match of the message context properties defined for the filter expression properties.</span></span>  

  ```  
  (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceName == :"ProcessAndRespond")   
  && Microsoft.Practices.ESB.Itinerary.Schemas.ServiceState == "Pending")  
  && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceType == "Orchestration")  
  ```  

- <span data-ttu-id="ad214-135">ProcessAndRespond オーケストレーションでは、旅行計画を進めるし、元の要求メッセージを応答としてスケジュールのテスト用クライアント アプリケーションにランプでサービスに送信します。</span><span class="sxs-lookup"><span data-stu-id="ad214-135">The ProcessAndRespond orchestration advances the itinerary and sends the original request message back to the on-ramp service to the Itinerary Test Client application as the response.</span></span>
