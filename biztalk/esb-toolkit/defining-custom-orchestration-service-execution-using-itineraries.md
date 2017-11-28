---
title: "日程を使用するカスタム オーケストレーション サービスの実行を定義する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6089169d-2fa1-4f81-afe1-db9d90a10382
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e40c85daae67928e6fbe3c20e9c6dd61f3634bf0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="defining-custom-orchestration-service-execution-using-itineraries"></a><span data-ttu-id="40cdd-102">日程を使用するカスタム オーケストレーション サービスの実行を定義します。</span><span class="sxs-lookup"><span data-stu-id="40cdd-102">Defining Custom Orchestration Service Execution Using Itineraries</span></span>
<span data-ttu-id="40cdd-103">このユース ケースでは、処理のために送信メッセージには、サービスを実行して、解決の要件の一覧を記述する itinerary の SOAP ヘッダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="40cdd-103">In this use case, a message submitted for processing contains an itinerary SOAP header that describes the list of services to execute and their resolution requirements.</span></span> <span data-ttu-id="40cdd-104">旅行計画は、1 つ以上のカスタム オーケストレーションまたはメッセージが通過する、処理中のプロセスを指定します。</span><span class="sxs-lookup"><span data-stu-id="40cdd-104">The itinerary specifies one or more custom orchestrations or processes through which the message will pass during the processing cycle.</span></span> <span data-ttu-id="40cdd-105">カスタム オーケストレーションでは、旅行計画し、メッセージ コンテキストで公開されるその他のカスタム プロパティのフル コントロール アクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="40cdd-105">Custom orchestrations have full control of the itinerary and other custom properties exposed in the message context.</span></span> <span data-ttu-id="40cdd-106">必要に応じて、itinerary は変換の要件およびメッセージのエンドポイントを決定する動的な解決策の情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="40cdd-106">Optionally, the itinerary can contain dynamic resolution information that determines transformation requirements and endpoints for the message.</span></span> <span data-ttu-id="40cdd-107">図 1 は、プロセスの概略を示します。</span><span class="sxs-lookup"><span data-stu-id="40cdd-107">Figure 1 illustrates a schematic view of the process.</span></span>  
  
 <span data-ttu-id="40cdd-108">![カスタム オーケストレーションを定義する](../esb-toolkit/media/ch3-definingcustomorchestration.gif "Ch3 DefiningCustomOrchestration")</span><span class="sxs-lookup"><span data-stu-id="40cdd-108">![Defining Custom Orchestration](../esb-toolkit/media/ch3-definingcustomorchestration.gif "Ch3-DefiningCustomOrchestration")</span></span>  
  
 <span data-ttu-id="40cdd-109">**図 1**</span><span class="sxs-lookup"><span data-stu-id="40cdd-109">**Figure 1**</span></span>  
  
 <span data-ttu-id="40cdd-110">**日程を使用するカスタム オーケストレーション サービスの実行を定義します。**</span><span class="sxs-lookup"><span data-stu-id="40cdd-110">**Defining custom orchestration service execution using itineraries**</span></span>  
  
 <span data-ttu-id="40cdd-111">含まれている行程入り口サンプル、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示しています。</span><span class="sxs-lookup"><span data-stu-id="40cdd-111">The Itinerary On-Ramp sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="40cdd-112">含む解像度、ルーティング、日程を作成し、一連の定義を itinerary 手順としてサービスの呼び出し命令する方法を示して 方法、ESB と[!INCLUDE[prague](../includes/prague-md.md)]は入力メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="40cdd-112">It shows how to create itineraries that contain resolution, routing, and service invocation instructions as a series of itinerary steps that define how the ESB and [!INCLUDE[prague](../includes/prague-md.md)] will process the input message.</span></span> <span data-ttu-id="40cdd-113">一方向と要求-応答のサンプルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="40cdd-113">One-way and request-response samples are included.</span></span>  
  
 <span data-ttu-id="40cdd-114">詳細については、次を参照してください。[のインストールと旅程ランプでサンプルを実行して](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="40cdd-114">For more information, see [Installing and Running the Itinerary On-Ramp Sample](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).</span></span>