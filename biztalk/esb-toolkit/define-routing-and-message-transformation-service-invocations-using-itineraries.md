---
title: ルーティングの定義と、日程を使用して変換サービスの呼び出しをメッセージ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e6f2448e-a5a7-496c-86d3-47f12e6f1251
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 975c830f73e0de362b25f312a8d41c4b15368cfd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294282"
---
# <a name="defining-routing-and-message-transformation-service-invocations-using-itineraries"></a><span data-ttu-id="9e7d0-102">定義するルーティングと旅程を使用してメッセージ変換サービスの呼び出し</span><span class="sxs-lookup"><span data-stu-id="9e7d0-102">Defining Routing and Message Transformation Service Invocations Using Itineraries</span></span>
<span data-ttu-id="9e7d0-103">このユース ケースでは、処理のために送信メッセージには、サービスを実行して、解決の要件の一覧を記述する itinerary の SOAP ヘッダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9e7d0-103">In this use case, a message submitted for processing contains an itinerary SOAP header that describes the list of services to execute and their resolution requirements.</span></span> <span data-ttu-id="9e7d0-104">具体的には、変換およびルーティング サービスは、Universal Description、検出、および Integration (UDDI)、ビジネス ルール エンジン ポリシー、XML パス言語 (XPath)、または静的参照を通じて解決を必要に応じて各が必要です。</span><span class="sxs-lookup"><span data-stu-id="9e7d0-104">Specifically, a transformation and routing service are defined, each optionally requiring resolution through a Universal Description, Discovery, and Integration (UDDI), Business Rules Engine Policy, XML Path Language (XPath), or STATIC lookup.</span></span> <span data-ttu-id="9e7d0-105">このユース ケースは、メッセージの発行時に、旅行計画に他のサービスを追加することによって拡張できます。</span><span class="sxs-lookup"><span data-stu-id="9e7d0-105">This use case can be extended by adding other services to the itinerary at the time of message publication.</span></span>  
  
 <span data-ttu-id="9e7d0-106">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Itinerary ランプ上の 2 つの型を提供します。 一方向の通信および要求-応答シナリオをサポートするものをサポートするものです。</span><span class="sxs-lookup"><span data-stu-id="9e7d0-106">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] provides two types of itinerary on-ramps: those that support one-way communication and those that support request-response scenarios.</span></span> <span data-ttu-id="9e7d0-107">動的解決メカニズムは、エンドポイントを確認したり、エンドポイントに動的にバインドする、旅行計画の情報を使用できます、ために、特定のエンドポイントのルーティングの詳細を格納する Microsoft BizTalk Server の要件はありません。</span><span class="sxs-lookup"><span data-stu-id="9e7d0-107">Because the dynamic resolution mechanism can use information in the itinerary to look up endpoints or bind dynamically to endpoints, there is no requirement for Microsoft BizTalk Server to contain specific endpoint routing details.</span></span> <span data-ttu-id="9e7d0-108">図 1 は、プロセスの概略を示します。</span><span class="sxs-lookup"><span data-stu-id="9e7d0-108">Figure 1 illustrates a schematic view of the process.</span></span>  
  
 <span data-ttu-id="9e7d0-109">![ルーティング サービスの呼び出しを定義する](../esb-toolkit/media/ch3-definingroutingserviceinvocation.gif "Ch3 DefiningRoutingServiceInvocation")</span><span class="sxs-lookup"><span data-stu-id="9e7d0-109">![Defining Routing service Invocation](../esb-toolkit/media/ch3-definingroutingserviceinvocation.gif "Ch3-DefiningRoutingServiceInvocation")</span></span>  
  
 <span data-ttu-id="9e7d0-110">**図 1**</span><span class="sxs-lookup"><span data-stu-id="9e7d0-110">**Figure 1**</span></span>  
  
 <span data-ttu-id="9e7d0-111">**日程を使用してルーティングおよびメッセージの変換サービス呼び出しを定義します。**</span><span class="sxs-lookup"><span data-stu-id="9e7d0-111">**Defining routing and message transformation service invocations using itineraries**</span></span>  
  
 <span data-ttu-id="9e7d0-112">含まれている行程入り口サンプル、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示しています。</span><span class="sxs-lookup"><span data-stu-id="9e7d0-112">The Itinerary On-Ramp sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="9e7d0-113">含む解像度、ルーティング、日程を作成し、一連の定義を itinerary 手順としてサービスの呼び出し命令する方法を示して 方法、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] BizTalk Server は、発行を使用してメッセージを処理し、サブスクライブの機能BizTalk Server です。</span><span class="sxs-lookup"><span data-stu-id="9e7d0-113">It shows how to create itineraries that contain resolution, routing, and service invocation instructions as a series of itinerary steps that define how the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] and BizTalk Server will process the message using the publish-subscribe functionality of BizTalk Server.</span></span> <span data-ttu-id="9e7d0-114">一方向と要求-応答のサンプルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9e7d0-114">One-way and request-response samples are included.</span></span>  
  
 <span data-ttu-id="9e7d0-115">詳細については、次を参照してください。[のインストールと旅程ランプでサンプルを実行して](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="9e7d0-115">For more information, see [Installing and Running the Itinerary On-Ramp Sample](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).</span></span>