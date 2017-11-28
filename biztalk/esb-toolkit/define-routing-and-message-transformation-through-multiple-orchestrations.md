---
title: "ルーティングの定義と、メッセージの日程を使用して複数のオーケストレーションを通じて変換 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 63141b83-798e-40d0-908d-6b7649923e69
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c5a87b06700794dca6c4aae9588c3068b98d995
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="defining-routing-and-message-transformation-through-multiple-orchestrations-using-itineraries"></a><span data-ttu-id="be5c0-102">定義するルーティングと旅程を使用して複数のオーケストレーションでメッセージの変換</span><span class="sxs-lookup"><span data-stu-id="be5c0-102">Defining Routing and Message Transformation Through Multiple Orchestrations Using Itineraries</span></span>
<span data-ttu-id="be5c0-103">このユース ケースでは、処理のために送信メッセージには、サービスを実行して、解決の要件の一覧を記述する itinerary の SOAP ヘッダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="be5c0-103">In this use case, a message submitted for processing contains an itinerary SOAP header that describes the list of services to execute and their resolution requirements.</span></span> <span data-ttu-id="be5c0-104">旅行計画では、メッセージが、処理サイクル中に通過する 1 つ以上の Microsoft BizTalk Server オーケストレーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="be5c0-104">The itinerary specifies one or more Microsoft BizTalk Server orchestrations through which the message will pass during the processing cycle.</span></span> <span data-ttu-id="be5c0-105">必要に応じて、旅行計画には、エンドポイントまたはメッセージの変換要件を決定するため、動的なルーティング情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="be5c0-105">Optionally, the itinerary can contain dynamic routing information used to determine endpoints or transformation requirements for the message.</span></span> <span data-ttu-id="be5c0-106">図 1 は、プロセスの概略を示します。</span><span class="sxs-lookup"><span data-stu-id="be5c0-106">Figure 1 illustrates a schematic view of the process.</span></span>  
  
 <span data-ttu-id="be5c0-107">![複数のオーケストレーションのルーティングの定義](../esb-toolkit/media/ch3-definingroutingmultipleorchestrations.gif "Ch3 DefiningRoutingMultipleOrchestrations")</span><span class="sxs-lookup"><span data-stu-id="be5c0-107">![Defining Routing Multiple Orchestrations](../esb-toolkit/media/ch3-definingroutingmultipleorchestrations.gif "Ch3-DefiningRoutingMultipleOrchestrations")</span></span>  
  
 <span data-ttu-id="be5c0-108">**図 1**</span><span class="sxs-lookup"><span data-stu-id="be5c0-108">**Figure 1**</span></span>  
  
 <span data-ttu-id="be5c0-109">**日程を使用して複数のオーケストレーションを通じてルーティングおよびメッセージの変換を定義します。**</span><span class="sxs-lookup"><span data-stu-id="be5c0-109">**Defining routing and message transformation through multiple orchestrations using itineraries**</span></span>  
  
 <span data-ttu-id="be5c0-110">含まれている行程入り口サンプル、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示しています。</span><span class="sxs-lookup"><span data-stu-id="be5c0-110">The Itinerary On-Ramp sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="be5c0-111">含む解像度、ルーティング、日程を作成し、一連の定義を itinerary 手順としてサービスの呼び出し命令する方法を示して 方法、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]し、BizTalk Server は、入力メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="be5c0-111">It shows how to create itineraries that contain resolution, routing, and service invocation instructions as a series of itinerary steps that define how the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] and BizTalk Server will process the input message.</span></span> <span data-ttu-id="be5c0-112">一方向と要求-応答のサンプルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="be5c0-112">One-way and request-response samples are included.</span></span>  
  
 <span data-ttu-id="be5c0-113">詳細については、次を参照してください。[のインストールと旅程ランプでサンプルを実行して](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="be5c0-113">For more information, see [Installing and Running the Itinerary On-Ramp Sample](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).</span></span>