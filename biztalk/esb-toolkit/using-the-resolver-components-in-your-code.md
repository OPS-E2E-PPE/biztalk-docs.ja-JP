---
title: コードで競合回避モジュール コンポーネントを使用する |Microsoft Docs
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
ms.openlocfilehash: 901ade5dd611c047c480f05ef0da8271150139d0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396391"
---
# <a name="using-the-resolver-components-in-your-code"></a>コードで競合回避モジュール コンポーネントを使用します。
動的変換エージェントからは、次のコード フラグメントでは、既定のジャストイン タイム (JIT) の解決機能を示します。 ようなコードを使用して、お使いのアプリケーションの解像度を簡単に実装できます。  
  
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
  
 上記の一覧で、**解決**のメソッド、 **ResolverMgr**クラスを返しますを**ディクショナリ**既定解像度のすべてのプロパティを格納しているオブジェクトとその。値を解決します。 任意のカスタム競合回避モジュールへのカスタム プロパティを追加できる、**ディクショナリ**オブジェクト。 これにより、任意のカスタム スケジュール サービスを使用可能なこれらのプロパティを実行します。  
  
 次の表に含まれる競合回避モジュールで必要に応じて値が設定できるプロパティ、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]します。 任意のスケジュール サービスは、返されたから抽出してこれらのプロパティ値を取得できます**ディクショナリ**オブジェクト。  
  
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
  
 マネージャーを返します、競合回避モジュールの後、**ディクショナリ**オブジェクト インスタンスの場合は、アダプター マネージャーがメッセージの特定の BizTalk アダプター コンテキスト プロパティを設定します。 ルーティング エージェントからは、次のコード フラグメントでは、アダプター マネージャーを使用して、送信メッセージのエンドポイント プロパティを設定する方法を示します。  
  
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
  
 ルーティング エージェントからは、次のコード フラグメントでは、カスタム パイプライン コンポーネント内からアダプター マネージャーを使用して、送信メッセージのエンドポイントのプロパティを設定する方法を示します。  
  
```csharp  
// Resolve the configuration for routing.  
ResolverDictionary = ResolverMgr.Resolve(info, pInMsg, pContext);  
  
// Call the adapter manager to set all required message properties.  
AdapterMgr.SetEndpoint(ResolverDictionary, pInMsg.Context);  
```