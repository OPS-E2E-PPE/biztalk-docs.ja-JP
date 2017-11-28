---
title: "Itinerary サービスを実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d86d228-da28-494f-85c7-4225b54f9b98
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4a4dc5c201b26ec33ee5666bc0dbeec8f54ccfc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="executing-an-itinerary-service"></a><span data-ttu-id="05254-102">Itinerary サービスを実行します。</span><span class="sxs-lookup"><span data-stu-id="05254-102">Executing an Itinerary Service</span></span>
<span data-ttu-id="05254-103">ESB 行程 itinerary する任意のサービス オーケストレーションとして実装されているか、次のタスクを実行するメッセージング可能性がありますを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="05254-103">An ESB itinerary can contain any itinerary service that may be implemented as orchestration or messaging to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="05254-104">旅行計画を含むメッセージを受信できます。</span><span class="sxs-lookup"><span data-stu-id="05254-104">It can receive the message containing the itinerary.</span></span>  
  
-   <span data-ttu-id="05254-105">現在の itinerary ステップを取得できます。</span><span class="sxs-lookup"><span data-stu-id="05254-105">It can retrieve the current itinerary step.</span></span>  
  
-   <span data-ttu-id="05254-106">サービスを処理できます。</span><span class="sxs-lookup"><span data-stu-id="05254-106">It can process the service.</span></span>  
  
-   <span data-ttu-id="05254-107">呼び出して、送信メッセージに旅行計画を進めることことができます、**事前**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="05254-107">It can advance the itinerary on the outgoing message by calling the **Advance** method.</span></span>  
  
-   <span data-ttu-id="05254-108">Microsoft BizTalk メッセージ ボックス データベースに、処理済みのメッセージを発行できます。</span><span class="sxs-lookup"><span data-stu-id="05254-108">It can publish the processed message back into the Microsoft BizTalk Message Box database.</span></span>  
  
 <span data-ttu-id="05254-109">たとえば、オーケストレーションがの図 1 に示すように、アクティブ化された受信図形に定義されたフィルターを実装することによって、日程を含むメッセージを受信できる[行程サービス サブスクライバーとして、オーケストレーションを使用して](../esb-toolkit/using-an-orchestration-as-an-itinerary-service-subscriber.md)です。</span><span class="sxs-lookup"><span data-stu-id="05254-109">For example, an orchestration can receive a message that contains an itinerary by implementing a filter defined on the activated receive shape, as shown in Figure 1 of [Using an Orchestration as an Itinerary Service Subscriber](../esb-toolkit/using-an-orchestration-as-an-itinerary-service-subscriber.md).</span></span> <span data-ttu-id="05254-110">ただし、メッセージングが若干異なります: パイプライン コンポーネントの呼び出し、 **GetItineraryStep**日程が受信メッセージに存在するかどうかを調べます。</span><span class="sxs-lookup"><span data-stu-id="05254-110">However, messaging is slightly different: the pipeline component calls the **GetItineraryStep** method to determine whether an itinerary exists in an incoming message.</span></span> <span data-ttu-id="05254-111">それが処理する必要があるかどうかを確認するメッセージのプロパティも検証します。</span><span class="sxs-lookup"><span data-stu-id="05254-111">It also examines the message properties to check whether it should process it.</span></span>  
  
 <span data-ttu-id="05254-112">![オーケストレーション](../esb-toolkit/media/ch4-orchestration.jpg "Ch4 オーケストレーション")</span><span class="sxs-lookup"><span data-stu-id="05254-112">![Orchestration](../esb-toolkit/media/ch4-orchestration.jpg "Ch4-Orchestration")</span></span>  
  
 <span data-ttu-id="05254-113">**図 1**</span><span class="sxs-lookup"><span data-stu-id="05254-113">**Figure 1**</span></span>  
  
 <span data-ttu-id="05254-114">**サブスクライバーとして日程に参加するオーケストレーションのフィルター式の例**</span><span class="sxs-lookup"><span data-stu-id="05254-114">**Example filter expression for an orchestration that will participate in an itinerary as a subscriber**</span></span>  
  
 <span data-ttu-id="05254-115">サービスは、メッセージを取得した後に呼び出す必要があります、 **GetItineraryStep**のインスタンスを返すメソッド、 **ItineraryStep**クラスです。</span><span class="sxs-lookup"><span data-stu-id="05254-115">After the service obtains the message, it must call the **GetItineraryStep** method, which returns an instance of the **ItineraryStep** class.</span></span> <span data-ttu-id="05254-116">次の一覧では、オーケストレーションとカスタム パイプライン コンポーネントの両方から行程 API のメソッドを呼び出す方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="05254-116">The following listings demonstrate how you can call the methods of the itinerary API from both an orchestration and a custom pipeline component.</span></span> <span data-ttu-id="05254-117">次のコードが実行される、 **GetItineraryStep**オーケストレーションの式図形からメソッドです。</span><span class="sxs-lookup"><span data-stu-id="05254-117">The following code executes the **GetItineraryStep** method from an orchestration Expression shape.</span></span>  
  
```  
  
//XLANGs  
// Retrieve the current itinerary step.  
itinerary = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryWrapper();  
step = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryStepWrapper();  
  
itinerary.Itinerary = Microsoft.Practices.ESB.Itinerary.ItineraryOMFactory.Create(InboundMessage);  
step.ItineraryStep = itinerary.Itinerary.GetItineraryStep(InboundMessage);  
```  
  
 <span data-ttu-id="05254-118">次のコードでは、カスタム パイプライン コンポーネントからメッセージング サービス メソッドを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="05254-118">The following code shows how to execute the messaging service method from a custom pipeline component.</span></span>  
  
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
  
 <span data-ttu-id="05254-119">インスタンス、 **IItineraryStep**クラスには、現在のサービスの実行環境のアンビエント プロパティを含め、現在のサービスのすべてのメタデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="05254-119">The instance of the **IItineraryStep** class contains all the metadata for the current service, including ambient properties of the current service execution environment.</span></span> <span data-ttu-id="05254-120">この機能には 2 つの良い例、 **ServiceInstanceID**と現在**MessageDirection**パイプライン コンポーネントのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="05254-120">Two good examples of this are the **ServiceInstanceID** and the current **MessageDirection** properties for a pipeline component.</span></span>  
  
 <span data-ttu-id="05254-121">サービスの呼び出し後、 **GetItineraryStep**メソッドを取得できる、関連付けられたすべての競合回避モジュール。</span><span class="sxs-lookup"><span data-stu-id="05254-121">After a service calls the **GetItineraryStep** method, it can retrieve any associated resolvers.</span></span> <span data-ttu-id="05254-122">**ResolverCollection**のプロパティ、 **ItineraryStep**クラスは、サービスを通じて、次の例に示すように列挙できる競合回避モジュールのコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="05254-122">The **ResolverCollection** property of the **ItineraryStep** class returns a collection of resolvers that the service can enumerate through, as shown in the following example.</span></span>  
  
```csharp  
Microsoft.Practices.ESB.Itinerary.ResolverCollection resolvers;  
resolvers = step.ItineraryStep.ResolverCollection;  
```  
  
 <span data-ttu-id="05254-123">内の各項目、 **ResolverCollection**競合回避モジュールとアダプター フレームワークでサポートされる型のいずれかに一致する競合回避モジュールの接続文字列を表します。</span><span class="sxs-lookup"><span data-stu-id="05254-123">Each item in the **ResolverCollection** represents a resolver connection string that matches one of the types supported by the Resolver and Adapter Framework.</span></span> <span data-ttu-id="05254-124">など、コレクション内の項目は、次のリストのようになります。</span><span class="sxs-lookup"><span data-stu-id="05254-124">For example, an item in the collection could look like the following listing.</span></span>  
  
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
  
 <span data-ttu-id="05254-125">競合回避モジュールとアダプターのプロバイダー フレームワークで競合回避モジュールのマネージャーでは、エンドポイントを解決でき、メッセージのエンドポイントのプロパティを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="05254-125">The resolver manager in the Resolver and Adapter Provider Framework can resolve the endpoints and set the endpoint properties of the message.</span></span> <span data-ttu-id="05254-126">このしくみの詳細については、次を参照してください。[動的解決の使用とルーティング](../esb-toolkit/using-dynamic-resolution-and-routing.md)です。</span><span class="sxs-lookup"><span data-stu-id="05254-126">For more information about how this occurs, see [Using Dynamic Resolution and Routing](../esb-toolkit/using-dynamic-resolution-and-routing.md).</span></span>  
  
 <span data-ttu-id="05254-127">サービスでは、メッセージの処理が完了すると後、は、送信メッセージに旅行計画を進める必要があり、メッセージをメッセージ ボックス データベースに発行します。</span><span class="sxs-lookup"><span data-stu-id="05254-127">After the service finishes processing the message, it must advance the itinerary on the outgoing message and publish the message back to the Message Box database.</span></span> <span data-ttu-id="05254-128">次の例では、オーケストレーションの式図形のプロセスを示します。</span><span class="sxs-lookup"><span data-stu-id="05254-128">The following example shows the process for an orchestration Expression shape.</span></span>  
  
```xml  
  
//XLANGs  
// Copy the context to the outbound message.  
OutboundMessage = InboundMessage;  
OutboundMessage(*) = InboundMessage(*);  
  
// Call the method of the ItinerarySerializableWrapper to advance to the next step.  
itinerary.Itinerary.Advance(OutboundMessage, step.ItineraryStep);  
```  
  
 <span data-ttu-id="05254-129">次の例は、ことを指定する方法を示しています。[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]コア エンジンは、カスタム パイプライン コンポーネントの日程を進める必要があります。</span><span class="sxs-lookup"><span data-stu-id="05254-129">The following example shows how to indicate that [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core engine should advance itinerary for a custom pipeline component.</span></span>  
  
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