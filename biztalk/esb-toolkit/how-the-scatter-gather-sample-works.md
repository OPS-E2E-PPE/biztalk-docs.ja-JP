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
ms.openlocfilehash: c675f2c6a9f558be597f7765ec936daf0a5a2dde
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001101"
---
# <a name="how-the-scatter-gather-sample-works"></a>スキャッター/ギャザー サンプルのしくみ
サンプル アプリケーションは、スキャッター/ギャザー itinerary ファイルから読み込まれたスケジュールを格納している SOAP ヘッダーのセットを構築、ディスクから、指定されたメッセージ ファイルを読み込み、itinerary ヘッダーをメッセージに追加および入り口のを通じて ESB に送信します処理しています。 旅行プランは、応答を生成する場合、アプリケーションはこれを収集し、アプリケーション ウィンドウに表示します。  
  
 スケジュール サービスがメッセージのスケジュールの情報を使用する方法を理解するためは、次のリストは、ScatterGatherItinerary.xml という名前のサンプルの itinerary 構成ファイルを示します。 このスケジュールの最初のセクションでは、サービス呼び出しの 2 つの手順を指定します。  
  
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
  
 旅行プランのサービス呼び出しの手順の一覧は、競合回避モジュールと、次の XML に示すように、スケジュールで定義されている各サービスを検索するスケジュール サービスを許可する接続文字列の詳細を含むセクションです。  
  
```xml  
<ResolverGroups xmlns="">  
 <Resolvers serviceId="ScatterGather0"><![CDATA[BRE:\\policy=ResolveEndPointScatterGather;version=;useMsg=;]]><![CDATA[UDDI3:\\serverUrl=http://localhost/uddi;bindingKey=uddi:esb:purchaseordersubmitorderservicebinding;credentialType=Ntlm]]></Resolvers>  
<Resolvers serviceId="DynamicTest1"><![CDATA[UDDI3:\\serverUrl=http://localhost/uddi;bindingKey=uddi:esb:orderfileservicebinding;credentialType=Ntlm]]>  
</Resolvers>  
  </ResolverGroups>  
```  
  
 この例で、アプリケーションの実行、SubmitPOService Web サービスの両方の競合回避モジュールの接続文字列をこのサービスの場所を解決するために 2 回 (http://localhost/ESB.CanadianServices/SubmitPOService.asmx)します。 メッセージ コンテキストは、として、次の例で定義されている最初のスケジュール サービスをアクティブ化するようにブローカ オーケストレーションを指定します。  
  
```csharp  
(Microsoft.Practices.ESB.Itinerary.Schemas.ServiceName == "ScatterGather")  
     && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceState ==   
    "Pending") && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceType   
    == "Orchestration")  
```  
  
 ブローカ オーケストレーションは、スケジュールのステップの設定を分析し、スケジュールのステップに関連付けられた競合回避モジュールのコレクションを取得します。 これらの競合回避モジュールごとに、オーケストレーションを使用して、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]リゾルバーとアダプター フレームワークは、サービス エンドポイントを解決します。 ブローカ オーケストレーションしをアクティブに n 個 ServiceDispatcher オーケストレーションの非同期的に (n は、スケジュールで ScatterGather サービスに関連付けられた競合回避モジュールの数) を次のパラメーターを含む要求メッセージをディスパッチします。  
  
- **TransportLocation**します。 競合回避モジュールは、このパラメーターを設定します。  
  
- **TransportType**します。 競合回避モジュールは、このパラメーターを設定します。  
  
- **ResolverDictionary**します。 このパラメーターには、競合回避モジュールのファクト具体的な競合回避モジュールのインスタンスによって設定のコレクションが含まれています。  
  
- **InboundMessage**します。 このパラメーターには、旅行プランを含む元のメッセージが含まれています。  
  
- **ServiceResponsePort**します。 このパラメーターは、自己関連付けを行うに ServiceDispatcher オーケストレーションのインスタンスからの応答を受信する応答のポートの名前です。  
  
  ServiceDispatcher オーケストレーションの各インスタンスでは、ResolveMapScatterGather ポリシーを使用して解決するには、Microsoft BizTalk マップの種類に基づいて、要求と応答メッセージの**TransportType**と**TransportLocation**プロパティ。 オーケストレーション インスタンスでは、解決済みのマップを使用して、受信メッセージを Web サービス呼び出しの要求メッセージに変換します。  
  
  ESB のアダプター マネージャーでは、どの BizTalk し、送信請求-応答ポートへの転送という ServiceRequestPort、要求メッセージの送信トランスポート コンテキスト プロパティを設定します。  
  
  をサービスから応答メッセージを受信した場合、ServiceDispatcher オーケストレーションは受信応答メッセージを標準形式に変換する解決済みのマップ情報を使用します。 ServiceResponse エンベロープ内で変更された応答をラップし、自己関連付けポートを通じてブローカ オーケストレーションに転送します。 ブローカ オーケストレーションは、すべての着信応答を集計し、次のコードに示すように、GlobalBank.ESB.ScatterGather.Processes.AggregatingPipeline を使用して、最後の応答メッセージを準備します。  
  
```csharp  
AggregatedResponse.Body = null;  
AggregatedResponse(*) = InboundMessage(*);  
Microsoft.XLANGs.Pipeline.XLANGPipelineManager.ExecuteSendPipeline(  
    typeof(GlobalBank.ESB.ScatterGather.Processes.AggregatingPipeline),  
    messageAggregator,AggregatedResponse);  
```  
  
 このコードは、定義済みのエンベロープ内の応答のバッチ全体をラップします。 ブローカ オーケストレーションしするスケジュールを進めます、 **DynamicTest** itinerary の手順で次のコードに示すようにします。  
  
```csharp  
// Copy the context and advance the itinerary.  
OutboundMessage = AggregatedResponse.Body;  
OutboundMessage(*) = AggregatedResponse(*);  
// Advance the Itinerary to the next step.  
itinerary.Itinerary.Advance(OutboundMessage, itineraryStep);  
```  
  
 という名前のサービス型の属性のため**DynamicTest**に設定されている**メッセージング**、 **ItineraryHelper**クラスのコンテキストに競合回避モジュールのプロパティを昇格する、という名前のメッセージ**OutboundMessage**します。 ブローカ オーケストレーションは、このメッセージを BizTalk の直接バインド ポートに送信します。 BizTalk によって表される動的送信ポートにメッセージを転送し、 **ServiceName**サブスクリプションの場合、これは**DynamicTest**します。 この送信ポートには、\Source\Samples\DynamicResolution\Test\Filedrop\Out フォルダーに集計された最後の応答がシリアル化します。