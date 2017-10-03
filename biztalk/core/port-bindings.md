---
title: "ポートのバインド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ports, warnings
- ports, bindings
- bindings, Web ports
- bindings, design time
- Web ports, port bindings
- bindings, ports
- bindings, direct
- bindings, warnings
- bindings, deployment
- bindings, dynamic
ms.assetid: b61c725a-0082-42d3-b88a-533583161734
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 943cbbaa6db9413ffad15bfcf3302d2216e3ab17
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="port-bindings"></a><span data-ttu-id="dc2d1-102">ポートのバインド</span><span class="sxs-lookup"><span data-stu-id="dc2d1-102">Port Bindings</span></span>
<span data-ttu-id="dc2d1-103">ポートのバインドとは、メッセージを送受信する場所と方法を定義した構成情報です。</span><span class="sxs-lookup"><span data-stu-id="dc2d1-103">A port binding is the configuration information that determines where and how a message will be sent or received.</span></span> <span data-ttu-id="dc2d1-104">ポートのバインドの参照先は、物理的な場所、パイプライン、他のオーケストレーションなど、バインドの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="dc2d1-104">Depending on its type, a port binding might refer to physical locations, pipelines, or other orchestrations.</span></span>  
  
 <span data-ttu-id="dc2d1-105">メッセージを受信するポートのバインドには次の 3 種類があります。</span><span class="sxs-lookup"><span data-stu-id="dc2d1-105">There are three types of port binding for ports that receive messages:</span></span>  
  
-   <span data-ttu-id="dc2d1-106">今指定します。</span><span class="sxs-lookup"><span data-stu-id="dc2d1-106">Specify now</span></span>  
  
-   <span data-ttu-id="dc2d1-107">後で指定します。</span><span class="sxs-lookup"><span data-stu-id="dc2d1-107">Specify later</span></span>  
  
-   <span data-ttu-id="dc2d1-108">[直接]</span><span class="sxs-lookup"><span data-stu-id="dc2d1-108">Direct</span></span>  
  
 <span data-ttu-id="dc2d1-109">メッセージを送信するポートのバインドには次の 4 種類があります。</span><span class="sxs-lookup"><span data-stu-id="dc2d1-109">There are four types of port binding for ports that send messages:</span></span>  
  
-   <span data-ttu-id="dc2d1-110">今指定します。</span><span class="sxs-lookup"><span data-stu-id="dc2d1-110">Specify now</span></span>  
  
-   <span data-ttu-id="dc2d1-111">後で指定します。</span><span class="sxs-lookup"><span data-stu-id="dc2d1-111">Specify later</span></span>  
  
-   <span data-ttu-id="dc2d1-112">[直接]</span><span class="sxs-lookup"><span data-stu-id="dc2d1-112">Direct</span></span>  
  
-   <span data-ttu-id="dc2d1-113">動的</span><span class="sxs-lookup"><span data-stu-id="dc2d1-113">Dynamic</span></span>  
  
## <a name="binding-at-deployment-time"></a><span data-ttu-id="dc2d1-114">展開時のバインド</span><span class="sxs-lookup"><span data-stu-id="dc2d1-114">Binding at Deployment Time</span></span>  
 <span data-ttu-id="dc2d1-115">ポートを受信場所または送信ポートにバインドできます。</span><span class="sxs-lookup"><span data-stu-id="dc2d1-115">You can bind your port to a receive location or to a send port.</span></span> <span data-ttu-id="dc2d1-116">場合は、すべての情報は、物理的な場所を指定する必要があると、選択、**後指定**オーケストレーション デザイナーでポートのバインド オプションは、ポートを説明するポートの種類を指定するだけです。</span><span class="sxs-lookup"><span data-stu-id="dc2d1-116">If you do not have all of the information you need to specify a physical location, you can select the **Specify later** port binding option in Orchestration Designer, and you only need to specify the port type that describes the port.</span></span> <span data-ttu-id="dc2d1-117">アプリケーションを展開したら、BizTalk Server 管理コンソールを使用して場所に関する情報を指定できます。また、プログラムで場所情報を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="dc2d1-117">After the application has been deployed, you can specify information about the location by using the BizTalk Server Administration console, or you can configure the location information programmatically.</span></span>  
  
## <a name="binding-at-design-time"></a><span data-ttu-id="dc2d1-118">デザイン時のバインド</span><span class="sxs-lookup"><span data-stu-id="dc2d1-118">Binding at Design Time</span></span>  
 <span data-ttu-id="dc2d1-119">選択することができます、**今指定**ポートのバインドのオプション オーケストレーション デザイナーでデザイン時に、トランスポートとパイプラインを指定します。</span><span class="sxs-lookup"><span data-stu-id="dc2d1-119">You can select the **Specify now** port binding option in Orchestration Designer to specify the transport and pipeline at design time.</span></span> <span data-ttu-id="dc2d1-120">受信メッセージのポートを指定する場合にドロップダウン リストから選択できるのは、HTTP、SOAP、および FILE の各トランスポートだけです。</span><span class="sxs-lookup"><span data-stu-id="dc2d1-120">When specifying the port for receiving messages, only HTTP, SOAP, and FILE transports are available from the drop-down list.</span></span> <span data-ttu-id="dc2d1-121">送信メッセージのポートを指定する場合にドロップダウン リストから選択できるのは、HTTP、FILE、および SMTP の各トランスポートだけです。</span><span class="sxs-lookup"><span data-stu-id="dc2d1-121">When specifying the port for sending messages, only HTTP, FILE, and SMTP transports are available from the drop-down list.</span></span> <span data-ttu-id="dc2d1-122">このオプションは、メッセージの送信元または送信先があらかじめわかっている場合に使用すると便利です。</span><span class="sxs-lookup"><span data-stu-id="dc2d1-122">This option is useful if you know in advance the source or destination of transmitted messages.</span></span>  
  
## <a name="direct-binding"></a><span data-ttu-id="dc2d1-123">直接バインド</span><span class="sxs-lookup"><span data-stu-id="dc2d1-123">Direct Binding</span></span>  
 <span data-ttu-id="dc2d1-124">直接バインド ポートは、物理ポートに明示的にバインドされているオーケストレーション内の一方向または双方向の論理ポートです。</span><span class="sxs-lookup"><span data-stu-id="dc2d1-124">Direct bound ports are logical one-way or two-way ports in your orchestrations that are not explicitly bound to any physical ports.</span></span> <span data-ttu-id="dc2d1-125">直接バインド ポートを使用すると、サービス間で異なる通信方式を利用できます。</span><span class="sxs-lookup"><span data-stu-id="dc2d1-125">Direct bound ports allow you to have different communication patterns among your services.</span></span> <span data-ttu-id="dc2d1-126">直接バインドを実装するのには、選択、**直接**ポートのデザイン時にオーケストレーション デザイナーでバインド オプション。</span><span class="sxs-lookup"><span data-stu-id="dc2d1-126">To implement direct binding, select the **Direct** port binding option in Orchestration Designer at design time.</span></span>  
  
 <span data-ttu-id="dc2d1-127">直接バインド ポートには次の 3 種類があります。</span><span class="sxs-lookup"><span data-stu-id="dc2d1-127">There are three types of direct bound ports:</span></span>  
  
-   <span data-ttu-id="dc2d1-128">メッセージ ボックスの直接バインド ポート</span><span class="sxs-lookup"><span data-stu-id="dc2d1-128">MessageBox direct bound port</span></span>  
  
-   <span data-ttu-id="dc2d1-129">自己関連付けを行う直接バインド ポート</span><span class="sxs-lookup"><span data-stu-id="dc2d1-129">Self-correlating direct bound port</span></span>  
  
-   <span data-ttu-id="dc2d1-130">パートナー オーケストレーションの直接バインド ポート</span><span class="sxs-lookup"><span data-stu-id="dc2d1-130">Partner orchestration direct bound port</span></span>  
  
 <span data-ttu-id="dc2d1-131">直接バインド ポートを使用する方法の詳細については、次を参照してください。[オーケストレーションに直接バインド ポート操作](../core/working-with-direct-bound-ports-in-orchestrations.md)です。</span><span class="sxs-lookup"><span data-stu-id="dc2d1-131">For more information about how to work with direct bound ports, see [Working with Direct Bound Ports in Orchestrations](../core/working-with-direct-bound-ports-in-orchestrations.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc2d1-132">直接バインドを使用する場合、1 つの要求 - 応答ポートと 2 つの一方向ポートの間でメッセージを交換することはできません。</span><span class="sxs-lookup"><span data-stu-id="dc2d1-132">When you use direct binding, you cannot exchange messages between one request-response port and two one-way ports.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc2d1-133">直接バインドは、BPEL4WS (Business Process Engineering Language for Web Services) 標準に準拠していません。</span><span class="sxs-lookup"><span data-stu-id="dc2d1-133">Direct binding is not compliant with the standards of the Business Process Engineering Language for Web Services (BPEL4WS).</span></span> <span data-ttu-id="dc2d1-134">BPEL4WS に準拠する必要がある場合は、他の種類のバインドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="dc2d1-134">If you require BPEL4WS compliance, use another kind of binding.</span></span>  
  
## <a name="dynamic-binding"></a><span data-ttu-id="dc2d1-135">動的バインド</span><span class="sxs-lookup"><span data-stu-id="dc2d1-135">Dynamic Binding</span></span>  
 <span data-ttu-id="dc2d1-136">実行時まで送信先がわからない場合は、送信ポートに対して動的バインドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="dc2d1-136">If you will not know the destination of a communication until run time, you can use dynamic binding for a send port.</span></span> <span data-ttu-id="dc2d1-137">場所可能性などの受信メッセージのプロパティから決定がありで指定して、**式**図形を次のコードに示すようにします。</span><span class="sxs-lookup"><span data-stu-id="dc2d1-137">The location might, for example, be determined from a property on an incoming message, and then specified in the **Expression** shape, as shown in the following code:</span></span>  
  
```  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)="mailto:johnd@contoso.com";  
```  
  
 <span data-ttu-id="dc2d1-138">ポートに値を動的に割り当てる方法については、次を参照してください。[動的ポートに値を割り当てる方法](../core/how-to-use-expressions-to-assign-values-to-dynamic-ports.md)です。</span><span class="sxs-lookup"><span data-stu-id="dc2d1-138">For information about how to dynamically assign values to ports, see [How to Assign Values to Dynamic Ports](../core/how-to-use-expressions-to-assign-values-to-dynamic-ports.md).</span></span>  
  
## <a name="web-ports"></a><span data-ttu-id="dc2d1-139">Web ポート</span><span class="sxs-lookup"><span data-stu-id="dc2d1-139">Web Ports</span></span>  
 <span data-ttu-id="dc2d1-140">プロジェクトに Web サービスへの参照が含まれる場合、オーケストレーション デザイナーで参照が検出されて、対応する Web ポートの種類が使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="dc2d1-140">If your project contains a reference to a Web service, Orchestration Designer will detect it and will make available a corresponding Web port type.</span></span> <span data-ttu-id="dc2d1-141">Web ポートを作成するには、オーケストレーションにポートを追加して、既存の Web ポートの種類を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="dc2d1-141">To create a Web port, you simply add a port to your orchestration and assign it an existing Web port type.</span></span> <span data-ttu-id="dc2d1-142">詳細については、次を参照してください。 [Web ポートの作成](../core/creating-web-ports.md)です。</span><span class="sxs-lookup"><span data-stu-id="dc2d1-142">For more information, see [Creating Web Ports](../core/creating-web-ports.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc2d1-143">参照</span><span class="sxs-lookup"><span data-stu-id="dc2d1-143">See Also</span></span>  
 <span data-ttu-id="dc2d1-144">[ポートの種類を操作する方法](../core/how-to-work-with-port-types.md) </span><span class="sxs-lookup"><span data-stu-id="dc2d1-144">[How to Work with Port Types](../core/how-to-work-with-port-types.md) </span></span>  
 <span data-ttu-id="dc2d1-145">[通信方式](../core/communication-pattern.md) </span><span class="sxs-lookup"><span data-stu-id="dc2d1-145">[Communication Pattern](../core/communication-pattern.md) </span></span>  
 <span data-ttu-id="dc2d1-146">[通信方向](../core/communication-direction.md) </span><span class="sxs-lookup"><span data-stu-id="dc2d1-146">[Communication Direction](../core/communication-direction.md) </span></span>  
 <span data-ttu-id="dc2d1-147">[オーケストレーションでポートを使用します。](../core/using-ports-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="dc2d1-147">[Using Ports in Orchestrations](../core/using-ports-in-orchestrations.md) </span></span>  
 <span data-ttu-id="dc2d1-148">[ポート構成ウィザードを実行する方法](../core/how-to-run-the-port-configuration-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="dc2d1-148">[How to Run the Port Configuration Wizard](../core/how-to-run-the-port-configuration-wizard.md) </span></span>  
 [<span data-ttu-id="dc2d1-149">Web サービスの使用</span><span class="sxs-lookup"><span data-stu-id="dc2d1-149">Consuming Web Services</span></span>](../core/consuming-web-services.md)