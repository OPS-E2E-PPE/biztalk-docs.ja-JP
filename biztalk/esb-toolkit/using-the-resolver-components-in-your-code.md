---
title: "コード内の競合回避モジュール コンポーネントを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d197cb28-78a9-4c8a-872b-f61ef15e6622
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 220ae4983f2fcbf60f6de02f818095fe5c0c50a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-resolver-components-in-your-code"></a>コード内の競合回避モジュール コンポーネントを使用します。
動的な変換エージェントから次のコード フラグメントは、既定・ イン タイム (JIT) の解決策機能を示しています。 解像度は、のようなコードを使用して、独自のアプリケーションで簡単に実装できます。  
  
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
  
 上記の一覧で、**解決**のメソッド、 **ResolverMgr**クラスを返します、**ディクショナリ**既定解像度のすべてのプロパティを格納しているオブジェクトとその値を解決します。 任意のカスタム競合回避モジュールはカスタム プロパティを追加できる、**ディクショナリ**オブジェクトです。 これにより、任意のカスタム itinerary サービスで使用できるこれらのプロパティを実行します。  
  
 次の表に含まれるリゾルバーが必要に応じて設定できるプロパティを示しています、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。 によって返されたから抽出するこれらのプロパティ値を取得できます、itinerary サービス**ディクショナリ**オブジェクト。  
  
 **プロパティ**:  
  
||||  
|-|-|-|  
|**Resolver.Action**|**Resolver.ActionField**|**Resolver.DocumentSpecName**|  
|**Resolver.Success**|**Resolver.EndpointConfig**|**Resolver.DocumentSpecStrongName**|  
|**Resolver.FixJaxRpc**|**Resolver.InboundTransportType**|**Resolver.EpmRRCorrelationToken**|  
|**Resolver.InterchangeId**|**Resolver.IsRequestResponse**|**Resolver.InboundTransportLocation**|  
|**Resolver.MessageType**|**Resolver.MethodName**|**Resolver.MessageExchangePattern**|  
|**Resolver.ReceivePortName**|**Resolver.TransportLocation**|**Resolver.OutboundTransportCLSID**|  
|**Resolver.TransformType**|**Resolver.TargetNamespace**|**Resolver.ReceiveLocationName**|  
|**Resolver.TransportType**|**Resolver.TransportNamespace**|**Resolver.WindowUserField**|  
|**Resolver.CacheTimeout**|||  
  
 マネージャーが返した場合、競合回避モジュールの後に、**ディクショナリ**オブジェクト インスタンスの場合は、アダプター マネージャーがメッセージの特定の BizTalk アダプター コンテキスト プロパティを設定します。 ルーティングのエージェントから次のコード フラグメントは、アダプター マネージャーを使用して、送信メッセージのエンドポイントのプロパティを設定する方法を示します。  
  
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
  
 ルーティングのエージェントから次のコード フラグメントでは、カスタム パイプライン コンポーネント内からアダプター マネージャーを使用して、送信メッセージのエンドポイントのプロパティを設定する方法を示します。  
  
```csharp  
// Resolve the configuration for routing.  
ResolverDictionary = ResolverMgr.Resolve(info, pInMsg, pContext);  
  
// Call the adapter manager to set all required message properties.  
AdapterMgr.SetEndpoint(ResolverDictionary, pInMsg.Context);  
```