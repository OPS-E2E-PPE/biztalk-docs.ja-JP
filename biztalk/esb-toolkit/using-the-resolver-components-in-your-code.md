---
title: コード内の競合回避モジュール コンポーネントを使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d197cb28-78a9-4c8a-872b-f61ef15e6622
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 220ae4983f2fcbf60f6de02f818095fe5c0c50a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295578"
---
# <a name="using-the-resolver-components-in-your-code"></a><span data-ttu-id="ffc16-102">コード内の競合回避モジュール コンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="ffc16-102">Using the Resolver Components in Your Code</span></span>
<span data-ttu-id="ffc16-103">動的な変換エージェントから次のコード フラグメントは、既定・ イン タイム (JIT) の解決策機能を示しています。</span><span class="sxs-lookup"><span data-stu-id="ffc16-103">The following code fragment from the dynamic transformation agent shows the default just-in-time (JIT) resolution functionality.</span></span> <span data-ttu-id="ffc16-104">解像度は、のようなコードを使用して、独自のアプリケーションで簡単に実装できます。</span><span class="sxs-lookup"><span data-stu-id="ffc16-104">You can easily implement resolution in your own application by using similar code.</span></span>  
  
```  
  
//XLANGs  
itinerary = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryWrapper();  
step = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryStepWrapper();  
  
itinerary.Itinerary = Microsoft.Practices.ESB.Itinerary.ItineraryOMFactory.Create(InboundMessage);  
step.ItineraryStep = itinerary.Itinerary.GetItineraryStep(InboundMessage);  
resolvers = step.ItineraryStep.ResolverCollection;  
resolvers.MoveNext();  
resolver = resolvers.Current;  
  
// Pass the resolver configuration to the Resolver mgr for resolution.  
resolverDictionary = Microsoft.Practices.ESB.Resolver.ResolverMgr.Resolve(InboundMessage, resolver);  
  
// Set the transform type.  
transformType = resolverDictionary.Item("Resolver.TransformType");  
```  
  
 <span data-ttu-id="ffc16-105">上記の一覧で、**解決**のメソッド、 **ResolverMgr**クラスを返します、**ディクショナリ**既定解像度のすべてのプロパティを格納しているオブジェクトとその値を解決します。</span><span class="sxs-lookup"><span data-stu-id="ffc16-105">In the preceding listing, the **Resolve** method of the **ResolverMgr** class returns a **Dictionary** object that contains all the default resolution properties and their resolved values.</span></span> <span data-ttu-id="ffc16-106">任意のカスタム競合回避モジュールはカスタム プロパティを追加できる、**ディクショナリ**オブジェクトです。 これにより、任意のカスタム itinerary サービスで使用できるこれらのプロパティを実行します。</span><span class="sxs-lookup"><span data-stu-id="ffc16-106">Any custom resolver can add custom properties to the **Dictionary** object; doing this makes those properties available to any custom itinerary service.</span></span>  
  
 <span data-ttu-id="ffc16-107">次の表に含まれるリゾルバーが必要に応じて設定できるプロパティを示しています、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ffc16-107">The following table shows the properties that can be optionally populated by the resolvers included in the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span> <span data-ttu-id="ffc16-108">によって返されたから抽出するこれらのプロパティ値を取得できます、itinerary サービス**ディクショナリ**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ffc16-108">Any itinerary service can retrieve these property values by extracting them from the returned **Dictionary** object.</span></span>  
  
 <span data-ttu-id="ffc16-109">**プロパティ**:</span><span class="sxs-lookup"><span data-stu-id="ffc16-109">**Properties**:</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="ffc16-110">**Resolver.Action**</span><span class="sxs-lookup"><span data-stu-id="ffc16-110">**Resolver.Action**</span></span>|<span data-ttu-id="ffc16-111">**Resolver.ActionField**</span><span class="sxs-lookup"><span data-stu-id="ffc16-111">**Resolver.ActionField**</span></span>|<span data-ttu-id="ffc16-112">**Resolver.DocumentSpecName**</span><span class="sxs-lookup"><span data-stu-id="ffc16-112">**Resolver.DocumentSpecName**</span></span>|  
|<span data-ttu-id="ffc16-113">**Resolver.Success**</span><span class="sxs-lookup"><span data-stu-id="ffc16-113">**Resolver.Success**</span></span>|<span data-ttu-id="ffc16-114">**Resolver.EndpointConfig**</span><span class="sxs-lookup"><span data-stu-id="ffc16-114">**Resolver.EndpointConfig**</span></span>|<span data-ttu-id="ffc16-115">**Resolver.DocumentSpecStrongName**</span><span class="sxs-lookup"><span data-stu-id="ffc16-115">**Resolver.DocumentSpecStrongName**</span></span>|  
|<span data-ttu-id="ffc16-116">**Resolver.FixJaxRpc**</span><span class="sxs-lookup"><span data-stu-id="ffc16-116">**Resolver.FixJaxRpc**</span></span>|<span data-ttu-id="ffc16-117">**Resolver.InboundTransportType**</span><span class="sxs-lookup"><span data-stu-id="ffc16-117">**Resolver.InboundTransportType**</span></span>|<span data-ttu-id="ffc16-118">**Resolver.EpmRRCorrelationToken**</span><span class="sxs-lookup"><span data-stu-id="ffc16-118">**Resolver.EpmRRCorrelationToken**</span></span>|  
|<span data-ttu-id="ffc16-119">**Resolver.InterchangeId**</span><span class="sxs-lookup"><span data-stu-id="ffc16-119">**Resolver.InterchangeId**</span></span>|<span data-ttu-id="ffc16-120">**Resolver.IsRequestResponse**</span><span class="sxs-lookup"><span data-stu-id="ffc16-120">**Resolver.IsRequestResponse**</span></span>|<span data-ttu-id="ffc16-121">**Resolver.InboundTransportLocation**</span><span class="sxs-lookup"><span data-stu-id="ffc16-121">**Resolver.InboundTransportLocation**</span></span>|  
|<span data-ttu-id="ffc16-122">**Resolver.MessageType**</span><span class="sxs-lookup"><span data-stu-id="ffc16-122">**Resolver.MessageType**</span></span>|<span data-ttu-id="ffc16-123">**Resolver.MethodName**</span><span class="sxs-lookup"><span data-stu-id="ffc16-123">**Resolver.MethodName**</span></span>|<span data-ttu-id="ffc16-124">**Resolver.MessageExchangePattern**</span><span class="sxs-lookup"><span data-stu-id="ffc16-124">**Resolver.MessageExchangePattern**</span></span>|  
|<span data-ttu-id="ffc16-125">**Resolver.ReceivePortName**</span><span class="sxs-lookup"><span data-stu-id="ffc16-125">**Resolver.ReceivePortName**</span></span>|<span data-ttu-id="ffc16-126">**Resolver.TransportLocation**</span><span class="sxs-lookup"><span data-stu-id="ffc16-126">**Resolver.TransportLocation**</span></span>|<span data-ttu-id="ffc16-127">**Resolver.OutboundTransportCLSID**</span><span class="sxs-lookup"><span data-stu-id="ffc16-127">**Resolver.OutboundTransportCLSID**</span></span>|  
|<span data-ttu-id="ffc16-128">**Resolver.TransformType**</span><span class="sxs-lookup"><span data-stu-id="ffc16-128">**Resolver.TransformType**</span></span>|<span data-ttu-id="ffc16-129">**Resolver.TargetNamespace**</span><span class="sxs-lookup"><span data-stu-id="ffc16-129">**Resolver.TargetNamespace**</span></span>|<span data-ttu-id="ffc16-130">**Resolver.ReceiveLocationName**</span><span class="sxs-lookup"><span data-stu-id="ffc16-130">**Resolver.ReceiveLocationName**</span></span>|  
|<span data-ttu-id="ffc16-131">**Resolver.TransportType**</span><span class="sxs-lookup"><span data-stu-id="ffc16-131">**Resolver.TransportType**</span></span>|<span data-ttu-id="ffc16-132">**Resolver.TransportNamespace**</span><span class="sxs-lookup"><span data-stu-id="ffc16-132">**Resolver.TransportNamespace**</span></span>|<span data-ttu-id="ffc16-133">**Resolver.WindowUserField**</span><span class="sxs-lookup"><span data-stu-id="ffc16-133">**Resolver.WindowUserField**</span></span>|  
|<span data-ttu-id="ffc16-134">**Resolver.CacheTimeout**</span><span class="sxs-lookup"><span data-stu-id="ffc16-134">**Resolver.CacheTimeout**</span></span>|||  
  
 <span data-ttu-id="ffc16-135">マネージャーが返した場合、競合回避モジュールの後に、**ディクショナリ**オブジェクト インスタンスの場合は、アダプター マネージャーがメッセージの特定の BizTalk アダプター コンテキスト プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="ffc16-135">After the resolver manager returns the **Dictionary** object instance, the adapter manager sets the specific BizTalk Adapter Context properties of the message.</span></span> <span data-ttu-id="ffc16-136">ルーティングのエージェントから次のコード フラグメントは、アダプター マネージャーを使用して、送信メッセージのエンドポイントのプロパティを設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ffc16-136">The following code fragment from the routing agent demonstrates how you can use the adapter manager to set the endpoint properties of the outgoing message.</span></span>  
  
```  
  
//XLANGs  
// Set the transport properties.  
transportLocation = resolverDictionary.Item("Resolver.TransportLocation");  
transportType = resolverDictionary.Item("Resolver.TransportType");  
  
// Create the delivery message.  
DeliveryMessage = InboundMessage;  
  
// Call the adapter manager to set all necessary properties on the message.  
Microsoft.Practices.ESB.Adapter.AdapterMgr.SetEndpoint(  
                                resolverDictionary,DeliveryMessage);  
  
// Set the delivery port address.  
DeliveryPort(Microsoft.XLANGs.BaseTypes.Address) = transportLocation;  
DeliveryPort(Microsoft.XLANGs.BaseTypes.TransportType) = transportType;  
```  
  
 <span data-ttu-id="ffc16-137">ルーティングのエージェントから次のコード フラグメントでは、カスタム パイプライン コンポーネント内からアダプター マネージャーを使用して、送信メッセージのエンドポイントのプロパティを設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ffc16-137">The following code fragment from the routing agent demonstrates how to use the adapter manager from within a custom pipeline component to set the endpoint properties of an outgoing message.</span></span>  
  
```csharp  
// Resolve the configuration for routing.  
ResolverDictionary = ResolverMgr.Resolve(info, pInMsg, pContext);  
  
// Call the adapter manager to set all required message properties.  
AdapterMgr.SetEndpoint(ResolverDictionary, pInMsg.Context);  
```