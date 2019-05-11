---
title: ルーティングの定義と、メッセージのスケジュールを使用して変換サービスの呼び出し |Microsoft Docs
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
ms.openlocfilehash: 0145bb07e700133be91878f040f5a3db4825db5e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394679"
---
# <a name="defining-routing-and-message-transformation-service-invocations-using-itineraries"></a><span data-ttu-id="1a7ef-102">定義のルーティングとスケジュールを使用してメッセージ変換サービスの呼び出し</span><span class="sxs-lookup"><span data-stu-id="1a7ef-102">Defining Routing and Message Transformation Service Invocations Using Itineraries</span></span>
<span data-ttu-id="1a7ef-103">このユース ケースでは、処理のために送信されたメッセージには、サービスを実行して、解決の要件の一覧を記述するスケジュールの SOAP ヘッダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1a7ef-103">In this use case, a message submitted for processing contains an itinerary SOAP header that describes the list of services to execute and their resolution requirements.</span></span> <span data-ttu-id="1a7ef-104">具体的には、変換およびルーティング サービスは、必要に応じて各 Universal Description、検出、および Integration (UDDI)、ビジネス ルール エンジン ポリシー、XML Path Language (XPath) または静的な参照を通じて解決を必要とします。</span><span class="sxs-lookup"><span data-stu-id="1a7ef-104">Specifically, a transformation and routing service are defined, each optionally requiring resolution through a Universal Description, Discovery, and Integration (UDDI), Business Rules Engine Policy, XML Path Language (XPath), or STATIC lookup.</span></span> <span data-ttu-id="1a7ef-105">このユース ケースは、メッセージの発行時に、旅行計画に他のサービスを追加することによって拡張できます。</span><span class="sxs-lookup"><span data-stu-id="1a7ef-105">This use case can be extended by adding other services to the itinerary at the time of message publication.</span></span>  
  
 <span data-ttu-id="1a7ef-106">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]の 2 種類のグラデーションでの旅程を提供します。 一方向の通信および要求-応答シナリオをサポートするものをサポートするものです。</span><span class="sxs-lookup"><span data-stu-id="1a7ef-106">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] provides two types of itinerary on-ramps: those that support one-way communication and those that support request-response scenarios.</span></span> <span data-ttu-id="1a7ef-107">動的解決の機構は、旅行計画の情報を使用してエンドポイントを検索したり、エンドポイントに動的にバインドしたり、ために、特定のエンドポイントのルーティングの詳細を格納する Microsoft BizTalk Server の要件はありません。</span><span class="sxs-lookup"><span data-stu-id="1a7ef-107">Because the dynamic resolution mechanism can use information in the itinerary to look up endpoints or bind dynamically to endpoints, there is no requirement for Microsoft BizTalk Server to contain specific endpoint routing details.</span></span> <span data-ttu-id="1a7ef-108">図 1 は、プロセスの概略を示します。</span><span class="sxs-lookup"><span data-stu-id="1a7ef-108">Figure 1 illustrates a schematic view of the process.</span></span>  
  
 <span data-ttu-id="1a7ef-109">![ルーティング サービスの呼び出しを定義する](../esb-toolkit/media/ch3-definingroutingserviceinvocation.gif "Ch3 DefiningRoutingServiceInvocation")</span><span class="sxs-lookup"><span data-stu-id="1a7ef-109">![Defining Routing service Invocation](../esb-toolkit/media/ch3-definingroutingserviceinvocation.gif "Ch3-DefiningRoutingServiceInvocation")</span></span>  
  
 <span data-ttu-id="1a7ef-110">**図 1**</span><span class="sxs-lookup"><span data-stu-id="1a7ef-110">**Figure 1**</span></span>  
  
 <span data-ttu-id="1a7ef-111">**スケジュールを使用してルーティングおよびメッセージの変換サービス呼び出しを定義します。**</span><span class="sxs-lookup"><span data-stu-id="1a7ef-111">**Defining routing and message transformation service invocations using itineraries**</span></span>  
  
 <span data-ttu-id="1a7ef-112">含まれている行程導入サンプル、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示します。</span><span class="sxs-lookup"><span data-stu-id="1a7ef-112">The Itinerary On-Ramp sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="1a7ef-113">解像度、ルーティングが含まれているスケジュールを作成し、呼び出し命令をサービスとして、一連のスケジュールの手順を定義する方法を示しています、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]し、BizTalk Server では、発行を使用してメッセージを処理します-サブスクライブの機能。BizTalk Server です。</span><span class="sxs-lookup"><span data-stu-id="1a7ef-113">It shows how to create itineraries that contain resolution, routing, and service invocation instructions as a series of itinerary steps that define how the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] and BizTalk Server will process the message using the publish-subscribe functionality of BizTalk Server.</span></span> <span data-ttu-id="1a7ef-114">一方向および要求-応答のサンプルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1a7ef-114">One-way and request-response samples are included.</span></span>  
  
 <span data-ttu-id="1a7ef-115">詳細については、次を参照してください。[をインストールすると、日程ランプでサンプルを実行する](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="1a7ef-115">For more information, see [Installing and Running the Itinerary On-Ramp Sample](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).</span></span>