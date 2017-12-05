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
ms.openlocfilehash: b73b4379944db548a30898403239ffcf9704791a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-the-itinerary-on-ramp-sample-works"></a>Itinerary 入り口サンプルの動作
サンプル行程テスト用クライアント アプリケーションがビルドされたら、クライアント アプリケーションのウィンドウでコントロールを使用して作成した日程を含む SOAP ヘッダーのセットがディスクから指定されたメッセージ ファイルを読み込み、itinerary ヘッダーをメッセージに追加し、ESB 行程入り口処理を通じてに送信します。 旅行計画は、応答を生成する場合、アプリケーションは、応答を収集し、アプリケーション ウィンドウに表示します。  
  
 オーケストレーション、メッセージ、または両方の組み合わせを使用する一方向と双方向のシナリオを表示するいくつかのサンプル itinerary 構成ファイルから選択できます。  
  
 行程サービスがメッセージの道順の情報を使用する方法を理解するためは、次の XML は、TwoWay-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml 先ほどの例で使用されるという名前のサンプル itinerary 構成ファイルを示します。 この行程の最初のセクションでは、次の 3 つのサービス呼び出しのステップを指定します。  
  
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
  
 行程サービスを検索するかで定義されている各サービスの解決策情報を提供できるようにのリゾルバー (接続文字列で表される) の詳細を含むセクションは、次の旅行計画でのサービス呼び出しの手順の一覧、行程です。  
  
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
>  それぞれの実際のコンテンツ**\<リゾルバー\>** 要素に上記のリストで、行をラップするために使用する空白文字が含まれていません。  
  
 Itinerary 前の構成で定義されている 3 つの手順を次に示します。  
  
1.  BizTalk ビジネス ルール エンジン (BRE) を使用して ResolverMap ポリシーを使用して、メッセージを変換する Microsoft.Practices.ESB.Services.Transform オーケストレーションを実行します。  
  
2.  変換されたメッセージをルーティング Microsoft.Practices.ESB.Services.Routing1 を使用して複数の場所にルーティングする Microsoft.Practices.ESB.Services.Routing オーケストレーションを実行します。  **\<ResolverGroups\>** セクションが含まれています、 **\<リゾルバー\>** 要素とこの識別子は、接続文字列を定義します。  
  
3.  このサンプルで提供される ProcessAndRespond オーケストレーションを実行します。 このオーケストレーションの実装の応答として送信要求メッセージのコピー行程テスト クライアントに返送します。  
  
 各サービスの補完機能で、サービスが itinerary を移動し、[次へ] サービスの状態に設定と、現在のサービス インスタンスである行程で定義されている昇格**保留**です。  
  
> [!NOTE]
>  行程入り口サンプルでは、動的な解決を使用して、出力フォルダーにメッセージを送信します。 これは理由がない静的送信ポートこのサンプルに対して定義されています。  
  
 クライアント テスト アプリケーションがメッセージを送信した後に発生するイベントのシーケンスを次に示します。  
  
-   OnRamp.Itinerary 受信ポートがメッセージを受信します。  
  
-   ItineraryReceiveXml パイプライン itinerary を SOAP ヘッダーから抽出を検証や事前処理、受信メッセージにメッセージ コンテキスト プロパティとして、日程を書き込みます and を BizTalk メッセージ ボックス データベースにメッセージを公開します。  
  
-   Microsoft.Practices.ESB.Services.Transform サービス オーケストレーションのサブスクリプションでは、このオーケストレーションの呼び出しをトリガーします。 オーケストレーションは、次のコードに示すように、パラメーターとして現在のメッセージを渡すことによって最初の現在の itinerary ステップを取得します。  
  
    ```csharp  
    itineraryStep =   itinerary.Itinerary.GetItineraryStep(InboundMessage);  
    ```  
  
-   **ItineraryStep**実行のため、現在のサービス インスタンスに関するすべての情報と関連付けられているすべてのリゾルバー オブジェクトが含まれます。  
  
-   **リゾルバー**からオブジェクトを取得、 **ItineraryStep**インスタンスおよび、ESB リゾルバー Framework が使用される変換マップの完全な名前を解決するのには、次のコードに示すようにします。  
  
    ```csharp  
    resolverDictionary =   
       Microsoft.Practices.ESB.Resolver.ResolverMgr.Resolve(InboundMessage,  
                                                            resolver);  
  
    // Set the transform type.  
    transformType = resolverDictionary.Item("Resolver.TransformType");  
    ```  
  
-   [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]型リゾルバーとアダプター フレームワークでこれを行う ResolverMap ポリシーを起動し、追加する (この例では、BizTalk ビジネス ルール エンジンの競合回避モジュール) のキャッシュから、適切な競合回避モジュールを読み込むことにより、 **ResolverDictionary**オブジェクト。  
  
-   オーケストレーションが完了すると、コードの呼び出し、 **AdvanceItinerary**メソッドを次のコードに示すようにします。  
  
    ```csharp  
    // Call the Itinerary helper to advance to the next step.  
    itinerary.Itinerary.Advance(OutboundMessage, itineraryStep.ItineraryStep);  
    ```  
  
-   これは、そのプロパティを更新して、次に実行すると、日程で定義されている次のサービスを昇格によって現在の旅程を進めます。 メソッドは、サービスの直接バインドの送信ポートを通じて、メッセージ ボックス データベースに公開、送信メッセージに旅行計画をコピーします。  
  
-   Microsoft.Practices.ESB.Services.Delivery サービス オーケストレーションのサブスクリプションでは、このオーケストレーションの呼び出しをトリガーします。 このオーケストレーションでは、現在の日程ステップを取得する最初のブックマークに同様のプロセスに従います。 ただし、このオーケストレーションをによって返される競合回避モジュールのコレクションを反復処理して、 **ItineraryStep**インスタンス。 各競合回避モジュールのコレクション内で、配信のオーケストレーションを使用して、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]競合回避モジュールとアダプター フレームワークのトランスポートの場所を解決し、次のコードに示すように、送信メッセージ内のコンテキスト プロパティとして昇格します。  
  
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
  
-   ProcessAndRespond オーケストレーションのサブスクリプションは、フィルター式のプロパティに対して定義されているメッセージ コンテキスト プロパティの照合のため、このオーケストレーションの呼び出しをトリガーします。  
  
    ```  
    (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceName == :"ProcessAndRespond")   
    && Microsoft.Practices.ESB.Itinerary.Schemas.ServiceState == "Pending")  
    && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceType == "Orchestration")  
    ```  
  
-   ProcessAndRespond オーケストレーションは、旅行計画を進めるし、元の要求メッセージを応答として行程テスト用クライアント アプリケーションにランプでサービスに送信します。