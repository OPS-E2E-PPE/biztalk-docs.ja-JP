---
title: "スキャッター/ギャザー サンプルの動作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ccfacb7-4fd2-4a1a-bece-27eedd86bbe9
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1221c038fa2e59636092c5cb49c6cbc40053708
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-the-scatter-gather-sample-works"></a>スキャッター/ギャザー サンプルのしくみ
サンプル アプリケーション スキャッター/ギャザー itinerary ファイルから読み込まれた旅程を含む SOAP ヘッダーのセットが作成され、ディスクから指定されたメッセージ ファイルを読み込み、itinerary ヘッダーをメッセージに追加および入り口のを通じて ESB に送信処理しています。 旅行計画は、応答を生成する場合、アプリケーションはこれを収集し、アプリケーション ウィンドウに表示します。  
  
 行程サービスがメッセージの道順の情報を使用する方法を理解するためは、次のリストは、ScatterGatherItinerary.xml をという名前のサンプル itinerary 構成ファイルを示します。 この行程の最初のセクションでは、次の 2 つのサービス呼び出しのステップを指定します。  
  
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
  
 次の旅行計画でのサービス呼び出しの手順の一覧は、競合回避モジュールと旅程サービスの次の XML に示すように、旅行計画で定義された各サービスを検索するようにする接続文字列の詳細を含むセクションです。  
  
```xml  
<ResolverGroups xmlns="">  
 <Resolvers serviceId="ScatterGather0"><![CDATA[BRE:\\policy=ResolveEndPointScatterGather;version=;useMsg=;]]><![CDATA[UDDI3:\\serverUrl=http://localhost/uddi;bindingKey=uddi:esb:purchaseordersubmitorderservicebinding;credentialType=Ntlm]]></Resolvers>  
<Resolvers serviceId="DynamicTest1"><![CDATA[UDDI3:\\serverUrl=http://localhost/uddi;bindingKey=uddi:esb:orderfileservicebinding;credentialType=Ntlm]]>  
</Resolvers>  
  </ResolverGroups>  
```  
  
 この例では、アプリケーション実行 SubmitPOService Web サービスの両方の競合回避モジュールの接続文字列が (http://localhost/ESB.CanadianServices/SubmitPOService.asmx) このサービスの場所を解決するために 2 回です。 メッセージ コンテキストをアクティブ化すると、最初の itinerary サービスで定義されている、サンプルを次のようにブローカ オーケストレーションを指定します。  
  
```csharp  
(Microsoft.Practices.ESB.Itinerary.Schemas.ServiceName == "ScatterGather")  
     && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceState ==   
    "Pending") && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceType   
    == "Orchestration")  
```  
  
 ブローカ オーケストレーションは、その itinerary のステップの設定を分析し、itinerary ステップに関連付けられた競合回避モジュールのコレクションを取得します。 これらの競合回避モジュールのそれぞれについて、オーケストレーションを使用して、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サービス エンドポイントを解決するのには型リゾルバーとアダプター フレームワークです。 ブローカ オーケストレーションしをアクティブに n 個 ServiceDispatcher オーケストレーションの非同期的に (n は itinerary で ScatterGather サービスに関連付けられている競合回避モジュールの数) を次のパラメーターを使用して要求メッセージをディスパッチします。  
  
-   **TransportLocation**です。 競合回避モジュールは、このパラメーターを追加します。  
  
-   **TransportType**です。 競合回避モジュールは、このパラメーターを追加します。  
  
-   **ResolverDictionary**です。 このパラメーターには、具体的な競合回避モジュール インスタンスによって設定の競合回避モジュールのファクトのコレクションが含まれています。  
  
-   **InboundMessage**です。 このパラメーターには、旅行計画を含む元のメッセージが含まれています。  
  
-   **ServiceResponsePort**です。 このパラメーターは、ServiceDispatcher オーケストレーションのインスタンスからの応答を受信する自己関連付けを行う応答のポートの名前です。  
  
 ServiceDispatcher オーケストレーションの各インスタンスは ResolveMapScatterGather ポリシーを使用して解決するには、Microsoft BizTalk マップの種類に基づいて、要求と応答メッセージを**TransportType**と**TransportLocation**プロパティです。 オーケストレーション インスタンスでは、解決済みのマップを使用して、受信メッセージを Web サービス呼び出しの要求メッセージに変換します。  
  
 ESB アダプター マネージャーでは、どの BizTalk し、送信請求-応答ポートへの転送という ServiceRequestPort、要求メッセージの送信トランスポート コンテキスト プロパティを設定します。  
  
 サービスから応答メッセージを受け取ると、ServiceDispatcher オーケストレーションは、正規の形式への着信応答メッセージを変換するのに解決マップ情報を使用します。 ServiceResponse エンベロープ内で変更された応答をラップし、自己関連付けポートを通じてブローカ オーケストレーションに転送します。 ブローカ オーケストレーションは、すべての着信応答を集計し、次のコードに示すように、GlobalBank.ESB.ScatterGather.Processes.AggregatingPipeline を使用して、最後の応答メッセージを準備します。  
  
```csharp  
AggregatedResponse.Body = null;  
AggregatedResponse(*) = InboundMessage(*);  
Microsoft.XLANGs.Pipeline.XLANGPipelineManager.ExecuteSendPipeline(  
    typeof(GlobalBank.ESB.ScatterGather.Processes.AggregatingPipeline),  
    messageAggregator,AggregatedResponse);  
```  
  
 このコードは、定義済みのエンベロープ内の応答のバッチ全体をラップします。 ブローカのオーケストレーション、進めますに行程、 **DynamicTest** itinerary 手順、次のコードに示すようにします。  
  
```csharp  
// Copy the context and advance the itinerary.  
OutboundMessage = AggregatedResponse.Body;  
OutboundMessage(*) = AggregatedResponse(*);  
// Advance the Itinerary to the next step.  
itinerary.Itinerary.Advance(OutboundMessage, itineraryStep);  
```  
  
 サービス型の属性が名前付きため**DynamicTest**に設定されている**メッセージング**、 **ItineraryHelper**クラスのコンテキストに競合回避モジュールのプロパティを昇格する、という名前のメッセージ**OutboundMessage**です。 ブローカ オーケストレーションは、このメッセージを BizTalk の直接バインド ポートに送信します。 BizTalk によって表される動的送信ポートにメッセージを転送し、 **ServiceName**サブスクリプションの場合、これは**DynamicTest**です。 この送信ポートは、\Source\Samples\DynamicResolution\Test\Filedrop\Out フォルダーに集計された最後の応答をシリアル化します。