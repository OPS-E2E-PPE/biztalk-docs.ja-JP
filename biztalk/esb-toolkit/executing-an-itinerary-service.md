---
title: Itinerary サービスを実行 |Microsoft ドキュメント
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
ms.openlocfilehash: f4a4dc5c201b26ec33ee5666bc0dbeec8f54ccfc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294458"
---
# <a name="executing-an-itinerary-service"></a>Itinerary サービスを実行します。
ESB 行程 itinerary する任意のサービス オーケストレーションとして実装されているか、次のタスクを実行するメッセージング可能性がありますを含めることができます。  
  
-   旅行計画を含むメッセージを受信できます。  
  
-   現在の itinerary ステップを取得できます。  
  
-   サービスを処理できます。  
  
-   呼び出して、送信メッセージに旅行計画を進めることことができます、**事前**メソッドです。  
  
-   Microsoft BizTalk メッセージ ボックス データベースに、処理済みのメッセージを発行できます。  
  
 たとえば、オーケストレーションがの図 1 に示すように、アクティブ化された受信図形に定義されたフィルターを実装することによって、日程を含むメッセージを受信できる[行程サービス サブスクライバーとして、オーケストレーションを使用して](../esb-toolkit/using-an-orchestration-as-an-itinerary-service-subscriber.md)です。 ただし、メッセージングが若干異なります: パイプライン コンポーネントの呼び出し、 **GetItineraryStep**日程が受信メッセージに存在するかどうかを調べます。 それが処理する必要があるかどうかを確認するメッセージのプロパティも検証します。  
  
 ![オーケストレーション](../esb-toolkit/media/ch4-orchestration.jpg "Ch4 オーケストレーション")  
  
 **図 1**  
  
 **サブスクライバーとして日程に参加するオーケストレーションのフィルター式の例**  
  
 サービスは、メッセージを取得した後に呼び出す必要があります、 **GetItineraryStep**のインスタンスを返すメソッド、 **ItineraryStep**クラスです。 次の一覧では、オーケストレーションとカスタム パイプライン コンポーネントの両方から行程 API のメソッドを呼び出す方法を示しています。 次のコードが実行される、 **GetItineraryStep**オーケストレーションの式図形からメソッドです。  
  
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
  
 インスタンス、 **IItineraryStep**クラスには、現在のサービスの実行環境のアンビエント プロパティを含め、現在のサービスのすべてのメタデータが含まれています。 この機能には 2 つの良い例、 **ServiceInstanceID**と現在**MessageDirection**パイプライン コンポーネントのプロパティです。  
  
 サービスの呼び出し後、 **GetItineraryStep**メソッドを取得できる、関連付けられたすべての競合回避モジュール。 **ResolverCollection**のプロパティ、 **ItineraryStep**クラスは、サービスを通じて、次の例に示すように列挙できる競合回避モジュールのコレクションを返します。  
  
```csharp  
Microsoft.Practices.ESB.Itinerary.ResolverCollection resolvers;  
resolvers = step.ItineraryStep.ResolverCollection;  
```  
  
 内の各項目、 **ResolverCollection**競合回避モジュールとアダプター フレームワークでサポートされる型のいずれかに一致する競合回避モジュールの接続文字列を表します。 など、コレクション内の項目は、次のリストのようになります。  
  
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
  
 競合回避モジュールとアダプターのプロバイダー フレームワークで競合回避モジュールのマネージャーでは、エンドポイントを解決でき、メッセージのエンドポイントのプロパティを設定することができます。 このしくみの詳細については、次を参照してください。[動的解決の使用とルーティング](../esb-toolkit/using-dynamic-resolution-and-routing.md)です。  
  
 サービスでは、メッセージの処理が完了すると後、は、送信メッセージに旅行計画を進める必要があり、メッセージをメッセージ ボックス データベースに発行します。 次の例では、オーケストレーションの式図形のプロセスを示します。  
  
```xml  
  
//XLANGs  
// Copy the context to the outbound message.  
OutboundMessage = InboundMessage;  
OutboundMessage(*) = InboundMessage(*);  
  
// Call the method of the ItinerarySerializableWrapper to advance to the next step.  
itinerary.Itinerary.Advance(OutboundMessage, step.ItineraryStep);  
```  
  
 次の例は、ことを指定する方法を示しています。[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]コア エンジンは、カスタム パイプライン コンポーネントの日程を進める必要があります。  
  
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