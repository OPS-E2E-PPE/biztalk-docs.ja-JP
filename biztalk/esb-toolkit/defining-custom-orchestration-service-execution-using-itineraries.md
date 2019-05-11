---
title: カスタム オーケストレーション実行スケジュールを定義する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6089169d-2fa1-4f81-afe1-db9d90a10382
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5c475178865f0ebe990dd75c87b29e75ab47753
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394648"
---
# <a name="defining-custom-orchestration-service-execution-using-itineraries"></a><span data-ttu-id="779bf-102">カスタム オーケストレーション実行スケジュールを定義します。</span><span class="sxs-lookup"><span data-stu-id="779bf-102">Defining Custom Orchestration Service Execution Using Itineraries</span></span>
<span data-ttu-id="779bf-103">このユース ケースでは、処理のために送信されたメッセージには、サービスを実行して、解決の要件の一覧を記述するスケジュールの SOAP ヘッダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="779bf-103">In this use case, a message submitted for processing contains an itinerary SOAP header that describes the list of services to execute and their resolution requirements.</span></span> <span data-ttu-id="779bf-104">旅行プランは、1 つまたは複数のカスタム オーケストレーションまたはメッセージが処理サイクルの間に通過するプロセスを指定します。</span><span class="sxs-lookup"><span data-stu-id="779bf-104">The itinerary specifies one or more custom orchestrations or processes through which the message will pass during the processing cycle.</span></span> <span data-ttu-id="779bf-105">カスタム オーケストレーションでは、旅行プランとその他のカスタム プロパティをメッセージ コンテキストで公開されているフル コントロールがあります。</span><span class="sxs-lookup"><span data-stu-id="779bf-105">Custom orchestrations have full control of the itinerary and other custom properties exposed in the message context.</span></span> <span data-ttu-id="779bf-106">必要に応じて、旅行プランは、変換の要件と、メッセージのエンドポイントを決定する動的解決の情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="779bf-106">Optionally, the itinerary can contain dynamic resolution information that determines transformation requirements and endpoints for the message.</span></span> <span data-ttu-id="779bf-107">図 1 は、プロセスの概略を示します。</span><span class="sxs-lookup"><span data-stu-id="779bf-107">Figure 1 illustrates a schematic view of the process.</span></span>  
  
 <span data-ttu-id="779bf-108">![カスタム オーケストレーションを定義する](../esb-toolkit/media/ch3-definingcustomorchestration.gif "Ch3 DefiningCustomOrchestration")</span><span class="sxs-lookup"><span data-stu-id="779bf-108">![Defining Custom Orchestration](../esb-toolkit/media/ch3-definingcustomorchestration.gif "Ch3-DefiningCustomOrchestration")</span></span>  
  
 <span data-ttu-id="779bf-109">**図 1**</span><span class="sxs-lookup"><span data-stu-id="779bf-109">**Figure 1**</span></span>  
  
 <span data-ttu-id="779bf-110">**カスタム オーケストレーション実行スケジュールを定義します。**</span><span class="sxs-lookup"><span data-stu-id="779bf-110">**Defining custom orchestration service execution using itineraries**</span></span>  
  
 <span data-ttu-id="779bf-111">含まれている行程導入サンプル、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示します。</span><span class="sxs-lookup"><span data-stu-id="779bf-111">The Itinerary On-Ramp sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="779bf-112">一連の ESB と BizTalk Server が、入力メッセージを処理する方法を定義するスケジュールのステップとして解像度、ルーティング、およびサービスの呼び出し命令を含むスケジュールを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="779bf-112">It shows how to create itineraries that contain resolution, routing, and service invocation instructions as a series of itinerary steps that define how the ESB and BizTalk Server will process the input message.</span></span> <span data-ttu-id="779bf-113">一方向および要求-応答のサンプルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="779bf-113">One-way and request-response samples are included.</span></span>  
  
 <span data-ttu-id="779bf-114">詳細については、次を参照してください。[をインストールすると、日程ランプでサンプルを実行する](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="779bf-114">For more information, see [Installing and Running the Itinerary On-Ramp Sample](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).</span></span>