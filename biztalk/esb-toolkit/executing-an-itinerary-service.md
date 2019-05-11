---
title: スケジュールのサービスを実行する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7d86d228-da28-494f-85c7-4225b54f9b98
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83551e31bfd822473e639c12abcf440c154dc826
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395124"
---
# <a name="executing-an-itinerary-service"></a>スケジュールのサービスを実行します。
ESB スケジュールは、オーケストレーションとして実装されているか、次のタスクを実行するメッセージング可能性のある任意のスケジュール サービスを含めることができます。  
  
- 旅行プランを含むメッセージを受信できます。  
  
- スケジュールの現在のステップを取得できます。  
  
- サービスを処理できます。  
  
- 呼び出すことによって、送信メッセージで旅行計画を進めることことができます、**事前**メソッド。  
  
- Microsoft BizTalk メッセージ ボックス データベースに、処理されたメッセージを発行できます。  
  
  たとえば、オーケストレーションの図 1 に示すように、アクティブ化された受信図形に定義されたフィルターを実装することにより、旅行プランを含むメッセージを表示される[スケジュール サービス サブスクライバーとしてオーケストレーションを使用して](../esb-toolkit/using-an-orchestration-as-an-itinerary-service-subscriber.md)します。 ただし、メッセージングは若干異なります: パイプライン コンポーネントの呼び出し、 **GetItineraryStep**日程が受信メッセージが存在するかどうかを判断するメソッド。 それが処理する必要があるかどうかを確認するメッセージのプロパティを調べます。  
  
  ![オーケストレーション](../esb-toolkit/media/ch4-orchestration.jpg "Ch4 オーケストレーション")  
  
  **図 1**  
  
  **サブスクライバーとして、スケジュールに参加するオーケストレーションのフィルター式の例**  
  
  呼び出す必要がありますが、サービスがメッセージを取得した後、 **GetItineraryStep**のインスタンスを返すメソッド、 **ItineraryStep**クラス。 次の一覧は、オーケストレーションとカスタム パイプライン コンポーネントの両方から行程 API のメソッドを呼び出す方法を示します。 次のコードが実行される、 **GetItineraryStep**オーケストレーションの式図形からメソッド。  
  
```  
  
//XLANGs  
// Retrieve the current itinerary step.  
itinerary = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryWrapper();  
step = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryStepWrapper();  
  
itinerary.Itinerary = Microsoft.Practices.ESB.Itinerary.ItineraryOMFactory.Create(InboundMessage);  
step.ItineraryStep = itinerary.Itinerary.GetItineraryStep(InboundMessage);  
```  
  
 次のコードでは、カスタム パイプライン コンポーネントからメッセージング サービス メソッドを実行する方法を示します。  
  
```csharp  
// Execute messaging step.  
public IBaseMessage Execute(IPipelineContext context, IBaseMessage msg, string resolverString, IItineraryStep step)  
{  
    if (null != step  
    && step.ServiceType == "Messaging"  
    && step.ServiceName == "SomeService")  
    {  
        // If the service name matches the required name, process the message here.  
    }  
    else  
    {  
        // Do not process the message.  
        return pInMsg;  
    }  
}  
```  
  
 インスタンス、 **IItineraryStep**クラスには、現在のサービスの実行環境のアンビエント プロパティを含む、現在のサービスのすべてのメタデータが含まれています。 この機能には 2 つの優れた例、 **ServiceInstanceID**と現在**MessageDirection**パイプライン コンポーネントのプロパティ。  
  
 サービスを呼び出してから、 **GetItineraryStep**メソッドを取得できる、関連付けられたすべての競合回避モジュール。 **ResolverCollection**のプロパティ、 **ItineraryStep**クラスは、サービスを列挙できるまで、次の例に示すように競合回避モジュールのコレクションを返します。  
  
```csharp  
Microsoft.Practices.ESB.Itinerary.ResolverCollection resolvers;  
resolvers = step.ItineraryStep.ResolverCollection;  
```  
  
 内の各項目、 **ResolverCollection**リゾルバーとアダプター フレームワークでサポートされる型のいずれかに一致する競合回避モジュールの接続文字列を表します。 たとえば、次のリストよう、コレクション内の項目になります。  
  
```idl  
BRE:\\policy=GetCanadaPurchaseEndPoint;version=;useMsg=;  
UDDI:\\serverUrl=http://localhost/uddi;serviceName=OrderFileServiceWBindings;  
STATIC:\\TransportLocation=http://localhost/ESB.CanadianServices/SubmitPOService.asmx;  
TargetNamespace=http://globalbank.esb.dynamicresolution.com/canadianservices/;  
XPATH:\\TransportType=; TransportLocation=/*[local-name()='OrderDoc' and namespace-  
uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/']/*  
[local-name()='ID' and namespace-  
uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/'];  
TargetNamespace=/*[local-name()='OrderDoc' and namespace-  
uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/']/*  
[local-name()='customerName' and namespace-  
uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/'];  
```  
  
 リゾルバーとアダプターのプロバイダー フレームワークの競合回避モジュールのマネージャーは、エンドポイントを解決し、メッセージのエンドポイントのプロパティを設定できます。 このしくみの詳細については、次を参照してください。[を使用して動的な解決とルーティング](../esb-toolkit/using-dynamic-resolution-and-routing.md)します。  
  
 サービスでは、メッセージの処理が完了すると後、は、送信メッセージで旅行計画を進める必要があり、メッセージをメッセージ ボックス データベースに発行します。 次の例では、オーケストレーションの式図形のプロセスを示します。  
  
```xml  
  
//XLANGs  
// Copy the context to the outbound message.  
OutboundMessage = InboundMessage;  
OutboundMessage(*) = InboundMessage(*);  
  
// Call the method of the ItinerarySerializableWrapper to advance to the next step.  
itinerary.Itinerary.Advance(OutboundMessage, step.ItineraryStep);  
```  
  
 次の例があることを示す方法を示します[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]コア エンジンは、カスタム パイプライン コンポーネントのスケジュールを進める必要があります。  
  
```csharp  
// Advance Itinerary  
// <summary>  
// Signals that the step should be advanced immediately following execution of the service.  
// </summary>  
// <param name="step">Current step</param>  
// <param name="msg">Current message</param>  
// <returns>True to advance the itinerary.</returns>  
public bool ShouldAdvanceStep(IItineraryStep step, IBaseMessage msg)  
{  
    return true;  
}  
```