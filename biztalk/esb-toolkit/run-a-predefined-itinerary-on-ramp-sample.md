---
title: 定義済みスケジュール オンランプ ランプでサンプルを実行する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4400193-20ac-479a-8bf9-b1c99eb35231
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e428a9106582e5bad3408cfb6643cc5da21ac74
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996587"
---
# <a name="run-a-predefined-itinerary-on-ramp-sample"></a><span data-ttu-id="297d8-102">定義済みスケジュール オンランプ ランプでサンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="297d8-102">Run a Predefined Itinerary On-Ramp Sample</span></span>
<span data-ttu-id="297d8-103">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]実行できる 20 の定義済みスケジュール ユース ケースが含まれています。</span><span class="sxs-lookup"><span data-stu-id="297d8-103">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] includes 20 predefined Itinerary use cases you can execute.</span></span> <span data-ttu-id="297d8-104">これらのリストについては、ユース ケースを参照してください[、サンプル スケジュール シナリオ](../esb-toolkit/the-sample-itinerary-scenarios.md)します。</span><span class="sxs-lookup"><span data-stu-id="297d8-104">For a list of these use cases, see [The Sample Itinerary Scenarios](../esb-toolkit/the-sample-itinerary-scenarios.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="297d8-105">サンプルを実行する前に、GlobalBank.ESB BizTalk アプリケーションに適切なスケジュール オンランプ バインド ファイル \Source\Samples\Itinerary\Install\Binding フォルダーから手動でインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="297d8-105">Before you run any of the samples, you must manually import the appropriate itinerary binding file from the \Source\Samples\Itinerary\Install\Binding folder into the GlobalBank.ESB BizTalk application.</span></span> <span data-ttu-id="297d8-106">このバインド ファイルでは、2 つの動的送信ポートのプロパティをリセットします。</span><span class="sxs-lookup"><span data-stu-id="297d8-106">This binding file resets the properties on the two dynamic send ports.</span></span> <span data-ttu-id="297d8-107">GlobalBank.ESB.Itinerary_Bindings.xml をという名前のバインド ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="297d8-107">Import the binding file named GlobalBank.ESB.Itinerary_Bindings.xml.</span></span>  
  
### <a name="to-run-one-of-the-pre-defined-itinerary-on-ramp-samples"></a><span data-ttu-id="297d8-108">定義済みの旅程導入サンプルの 1 つを実行するには</span><span class="sxs-lookup"><span data-stu-id="297d8-108">To run one of the pre-defined Itinerary On-Ramp samples</span></span>  
  
1. <span data-ttu-id="297d8-109">GlobalBank.ESB アプリケーションが実行されていない場合は、BizTalk 管理コンソールを使用して開始します。</span><span class="sxs-lookup"><span data-stu-id="297d8-109">If the GlobalBank.ESB application is not already running, use the BizTalk Administration Console to start it.</span></span>  
  
2. <span data-ttu-id="297d8-110">Windows エクスプ ローラーでは、サブフォルダー \Source\Samples\Itinerary\Source\ESB を開きます。Itinerary.Test\bin\Debug BizTalk ESB Toolkit のサンプルをインストールしてアプリケーションを開始した場所では、Esb.Itinerary.Test.exe という名前です。</span><span class="sxs-lookup"><span data-stu-id="297d8-110">In Windows Explorer, open the subfolder \Source\Samples\Itinerary\Source\ESB.Itinerary.Test\bin\Debug where you installed the BizTalk ESB Toolkit samples, and then start the application named Esb.Itinerary.Test.exe.</span></span>  
  
3. <span data-ttu-id="297d8-111">をクリックして、 **LoadItinerary**ボタンをクリックし、TwoWay-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml \Source\Samples\Itinerary\Itineraries フォルダーからをという名前のサンプルの旅行プランを選択します。</span><span class="sxs-lookup"><span data-stu-id="297d8-111">Click the **LoadItinerary** button, and then select the sample itinerary named TwoWay-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml from the \Source\Samples\Itinerary\Itineraries folder.</span></span>  
  
4. <span data-ttu-id="297d8-112">**Web サービス オプション**セクションで、**双方向サービス**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="297d8-112">In the **Web Service Options** section, select the **Two-Way Service** check box.</span></span> <span data-ttu-id="297d8-113">これには、テスト用クライアントの要求-応答のスケジュール サービス操作を実行するように指示します。</span><span class="sxs-lookup"><span data-stu-id="297d8-113">This instructs the test client to perform a request-response itinerary service operation.</span></span>  
  
5. <span data-ttu-id="297d8-114">(省略可能)選択、 **WCF サービスを使用して**する場合は、アプリケーション、OnRamp.Itinerary.Response.WCF を使用する チェック ボックスの受信場所、既定ではなく OnRamp.Itinerary.Response.SOAP 受信場所。</span><span class="sxs-lookup"><span data-stu-id="297d8-114">(Optional) Select the **Use WCF Service** check box if you want the application to use the OnRamp.Itinerary.Response.WCF receive location instead of the default OnRamp.Itinerary.Response.SOAP receive location.</span></span>  
  
6. <span data-ttu-id="297d8-115">をクリックして、 **LoadMessage**ボタンをクリックし、\Source\Samples\Itinerary\Test\Data フォルダーから NAOrderDoc.xml サンプル メッセージを選択します。</span><span class="sxs-lookup"><span data-stu-id="297d8-115">Click the **LoadMessage** button, and then select the NAOrderDoc.xml sample message from the \Source\Samples\Itinerary\Test\Data folder.</span></span>  
  
7. <span data-ttu-id="297d8-116">をクリックして、 **SubmitRequest**行程入口サービスに要求を送信するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="297d8-116">Click the **SubmitRequest** button to send the request to the Itinerary On-Ramp service.</span></span> <span data-ttu-id="297d8-117">図 1 は、結果を示します。</span><span class="sxs-lookup"><span data-stu-id="297d8-117">Figure 1 shows the result.</span></span>  
  
   <span data-ttu-id="297d8-118">![傾斜の itinerary](../esb-toolkit/media/ch6-itineraryonramp.gif "Ch6 ItineraryOnRamp")</span><span class="sxs-lookup"><span data-stu-id="297d8-118">![Itinerary On Ramp](../esb-toolkit/media/ch6-itineraryonramp.gif "Ch6-ItineraryOnRamp")</span></span>  
  
   <span data-ttu-id="297d8-119">**図 1**</span><span class="sxs-lookup"><span data-stu-id="297d8-119">**Figure 1**</span></span>  
  
   <span data-ttu-id="297d8-120">**行程導入サンプルの 1 つの操作を実行しているスケジュール入口クライアント アプリケーション**</span><span class="sxs-lookup"><span data-stu-id="297d8-120">**The Itinerary On-Ramp client application running one of the Itinerary On-Ramp samples**</span></span>  
  
   <span data-ttu-id="297d8-121">スケジュールの定義で指定されたサービスの名前が対応に直接、 **ServiceName**サンプルがサブスクライブしているサービスのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="297d8-121">The name of the service specified in the itinerary definition corresponds directly to the **ServiceName** property of the service to which the sample subscribes.</span></span> <span data-ttu-id="297d8-122">前の手順 (TwoWay-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml) で実行されるスケジュール オンランプ サンプルは、実行される最初のサービスは、変換を実行するオーケストレーション ベースのサービスが。</span><span class="sxs-lookup"><span data-stu-id="297d8-122">In the itinerary sample executed in the previous procedure (TwoWay-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml), the first service executed is an orchestration-based service that performs a transformation.</span></span> <span data-ttu-id="297d8-123">旅行計画の次のセクションでは、このサービスを指定します。</span><span class="sxs-lookup"><span data-stu-id="297d8-123">The following section of the itinerary specifies this service.</span></span>  
  
```  
<Service uuid="" beginTime="" completeTime=""   
    name="Microsoft.Practices.ESB.Services.Transform"  
    type="Orchestration" state="Pending" isRequestResponse="false"  
    position="0" serviceInstanceId="" />  
```  
  
 <span data-ttu-id="297d8-124">このオーケストレーション サービス**\<サービス\>** 要素を図 2 に示すようにフィルターのプロパティを持つ直接バインドされたオーケストレーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="297d8-124">The orchestration service in this **\<Service\>** element specifies the direct-bound orchestration that has the filter properties shown in Figure 2.</span></span> <span data-ttu-id="297d8-125">オーケストレーションが値を持つメッセージのみにサブスクライブしていることに注意してください**Microsoft.Practices.ESB.Services.Transform**の、 **ServiceName**コンテキスト プロパティ、値 **。保留中**の**ServiceState**コンテキスト プロパティ、およびオーケストレーションの値を**ServiceType**コンテキスト プロパティ。</span><span class="sxs-lookup"><span data-stu-id="297d8-125">Notice that the orchestration subscribes only to messages that have the value **Microsoft.Practices.ESB.Services.Transform** for the **ServiceName** context property, the value **Pending** for the **ServiceState** context property, and the value Orchestration for the **ServiceType** context property.</span></span>  
  
 <span data-ttu-id="297d8-126">![フィルター式](../esb-toolkit/media/ch6-filterexpression.gif "Ch6 FilterExpression")</span><span class="sxs-lookup"><span data-stu-id="297d8-126">![Filter Expression](../esb-toolkit/media/ch6-filterexpression.gif "Ch6-FilterExpression")</span></span>  
  
 <span data-ttu-id="297d8-127">**図 2**</span><span class="sxs-lookup"><span data-stu-id="297d8-127">**Figure 2**</span></span>  
  
 <span data-ttu-id="297d8-128">**行程導入サンプルで使用する直接バインドされたオーケストレーションのフィルター式**</span><span class="sxs-lookup"><span data-stu-id="297d8-128">**The filter expression for the direct-bound orchestration used in the Itinerary On-Ramp sample**</span></span>