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
# <a name="how-the-itinerary-on-ramp-sample-works"></a>スケジュール オンランプ ランプでサンプルのしくみ
サンプル アプリケーションで、クライアント アプリケーションのウィンドウでコントロールを使用して作成したスケジュールが含まれている SOAP ヘッダーのセットを作成スケジュールのテスト用クライアント ディスクから、指定されたメッセージ ファイルを読み込み、itinerary ヘッダーをメッセージに追加し、ESB 行程入り口の処理に送信します。 旅行プランは、応答を生成する場合、アプリケーションは、応答を収集し、アプリケーション ウィンドウに表示します。  

 オーケストレーション、メッセージング、またはその両方の組み合わせを使用する一方向と双方向のシナリオを表示するスケジュールの構成ファイルのサンプルをいくつかから選択することができます。  

 スケジュール サービスがメッセージのスケジュールの情報を使用する方法を理解するためは、次の XML は、TwoWay-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml 前の例で使用される名前付きサンプル スケジュールの構成ファイルを示します。 このスケジュールの最初のセクションでは、次の 3 つのサービス呼び出しのステップを指定します。  

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

 特定またはで定義されている各サービスの解決策情報を提供するスケジュール サービスを許可する (接続文字列で表されます)、リゾルバーの詳細を含むセクションには、旅行プランのサービス呼び出しのステップの一覧を次の旅行プラン。  

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
>  それぞれの実際のコンテンツ**\<リゾルバー\>** 要素に上記の一覧で、行をラップするために使用する空白文字が含まれていません。  

 以下は、前のスケジュールの構成で定義されている 3 つの手順です。  

1. BizTalk ビジネス ルール エンジン (BRE) を使用して ResolverMap ポリシーを使用して、メッセージを変換する Microsoft.Practices.ESB.Services.Transform オーケストレーションを実行します。  

2. 変換されたメッセージをルーティング Microsoft.Practices.ESB.Services.Routing1 を使用して複数の場所にルーティングする Microsoft.Practices.ESB.Services.Routing オーケストレーションを実行します。 **\<ResolverGroups\>** セクションが含まれています、 **\<リゾルバー\>** 要素とこの識別子は、接続文字列を定義します。  

3. このサンプルで提供される ProcessAndRespond オーケストレーションを実行します。 応答として送信しますこのオーケストレーションの実装は旅行プランのテスト クライアントに要求メッセージのコピー。  

   各サービスを完了したら、サービスが旅行計画を進めるし、現在のサービス インスタンス、その状態に設定するスケジュールで定義されている次のサービスを昇格させます**保留**します。  

> [!NOTE]
>  行程入口サンプルでは、動的解決を使用して出力フォルダーにメッセージを送信します。 これは理由がない静的送信ポートをこのサンプルに対して定義されています。  

 テスト用クライアント アプリケーションがメッセージを送信した後に発生するイベントのシーケンスを次に示します。  

- 受信ポートを OnRamp.Itinerary メッセージを受信します。  

- ItineraryReceiveXml パイプライン旅行プランを SOAP ヘッダーから抽出します、検証し事前処理、旅行プランをメッセージ コンテキスト プロパティとして、受信メッセージに書き込みますおよび BizTalk メッセージ ボックス データベースには、メッセージを公開します。  

- Microsoft.Practices.ESB.Services.Transform サービス オーケストレーションのサブスクリプションでは、このオーケストレーションの呼び出しをトリガーします。 オーケストレーションは、まず次のコードに示すように、パラメーターとして現在のメッセージを渡すことによってスケジュールの現在のステップを取得します。  

  ```csharp  
  itineraryStep =   itinerary.Itinerary.GetItineraryStep(InboundMessage);  
  ```  

- **ItineraryStep**オブジェクトには、実行するための現在のサービス インスタンスに関するすべての情報も関連付けられているすべてのリゾルバーが含まれています。  

- **リゾルバー**からオブジェクトを取得、 **ItineraryStep**インスタンスと ESB リゾルバー フレームワークが次のコードに示すように、変換マップの完全名の解決に使用されます。  

  ```csharp  
  resolverDictionary =   
     Microsoft.Practices.ESB.Resolver.ResolverMgr.Resolve(InboundMessage,  
                                                          resolver);  

  // Set the transform type.  
  transformType = resolverDictionary.Item("Resolver.TransformType");  
  ```  

- [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]リゾルバーとアダプター フレームワークはこれを実現する ResolverMap ポリシーの呼び出しを設定します (この例では、BizTalk ビジネス ルール エンジンの競合回避モジュール) でキャッシュから、適切な競合回避モジュールを読み込み、 **ResolverDictionary**オブジェクト。  

- オーケストレーションの完了後、コードの呼び出し、 **AdvanceItinerary**メソッドは、次のコードに示すようにします。  

  ```csharp  
  // Call the Itinerary helper to advance to the next step.  
  itinerary.Itinerary.Advance(OutboundMessage, itineraryStep.ItineraryStep);  
  ```  

- これは、そのプロパティを更新し、次に実行する 1 つとして、スケジュールで定義されている次のサービスを昇格によって現在の旅程を進めます。 メソッドは、直接バインドされた送信ポートを通じてメッセージ ボックス データベースにサービスを発行する、送信メッセージに旅行プランをコピーします。  

- Microsoft.Practices.ESB.Services.Delivery サービス オーケストレーションのサブスクリプションでは、このオーケストレーションの呼び出しをトリガーします。 このオーケストレーションでは、現在のスケジュール ステップを取得する最初の 1 つに、同様のプロセスに従います。 ただし、このオーケストレーションがによって返される競合回避モジュールのコレクションを反復処理し、 **ItineraryStep**インスタンス。 コレクション内の各リゾルバーの配信のオーケストレーションを使用して、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]リゾルバーとアダプター フレームワークは、トランスポートの場所を解決し、次のコードに示すように、送信メッセージのコンテキスト プロパティとして昇格させることです。  

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

- ProcessAndRespond オーケストレーションのサブスクリプションは、フィルター式のプロパティに対して定義されているメッセージ コンテキスト プロパティと一致するため、このオーケストレーションの呼び出しをトリガーします。  

  ```  
  (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceName == :"ProcessAndRespond")   
  && Microsoft.Practices.ESB.Itinerary.Schemas.ServiceState == "Pending")  
  && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceType == "Orchestration")  
  ```  

- ProcessAndRespond オーケストレーションでは、旅行計画を進めるし、元の要求メッセージを応答としてスケジュールのテスト用クライアント アプリケーションにランプでサービスに送信します。
