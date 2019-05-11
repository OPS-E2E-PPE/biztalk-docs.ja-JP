---
title: ルーティングの定義と、メッセージにより、スケジュールを使用して複数のオーケストレーションの変換 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63141b83-798e-40d0-908d-6b7649923e69
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb39d156827dd88d043c86cf3fa27cf82889d9fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394654"
---
# <a name="defining-routing-and-message-transformation-through-multiple-orchestrations-using-itineraries"></a><span data-ttu-id="7e2f0-102">定義のルーティングとスケジュールを使用して複数のオーケストレーションによるメッセージの変換</span><span class="sxs-lookup"><span data-stu-id="7e2f0-102">Defining Routing and Message Transformation Through Multiple Orchestrations Using Itineraries</span></span>
<span data-ttu-id="7e2f0-103">このユース ケースでは、処理のために送信されたメッセージには、サービスを実行して、解決の要件の一覧を記述するスケジュールの SOAP ヘッダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7e2f0-103">In this use case, a message submitted for processing contains an itinerary SOAP header that describes the list of services to execute and their resolution requirements.</span></span> <span data-ttu-id="7e2f0-104">旅行プランでは、メッセージが処理サイクルの間に通過する 1 つまたは複数の Microsoft BizTalk Server オーケストレーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="7e2f0-104">The itinerary specifies one or more Microsoft BizTalk Server orchestrations through which the message will pass during the processing cycle.</span></span> <span data-ttu-id="7e2f0-105">必要に応じて、旅行プランは、エンドポイントまたはメッセージの変換の要件を決定するため、動的なルーティング情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="7e2f0-105">Optionally, the itinerary can contain dynamic routing information used to determine endpoints or transformation requirements for the message.</span></span> <span data-ttu-id="7e2f0-106">図 1 は、プロセスの概略を示します。</span><span class="sxs-lookup"><span data-stu-id="7e2f0-106">Figure 1 illustrates a schematic view of the process.</span></span>  
  
 <span data-ttu-id="7e2f0-107">![複数のオーケストレーションのルーティングを定義する](../esb-toolkit/media/ch3-definingroutingmultipleorchestrations.gif "Ch3 DefiningRoutingMultipleOrchestrations")</span><span class="sxs-lookup"><span data-stu-id="7e2f0-107">![Defining Routing Multiple Orchestrations](../esb-toolkit/media/ch3-definingroutingmultipleorchestrations.gif "Ch3-DefiningRoutingMultipleOrchestrations")</span></span>  
  
 <span data-ttu-id="7e2f0-108">**図 1**</span><span class="sxs-lookup"><span data-stu-id="7e2f0-108">**Figure 1**</span></span>  
  
 <span data-ttu-id="7e2f0-109">**スケジュールを使用して複数のオーケストレーションによるルーティングおよびメッセージの変換を定義します。**</span><span class="sxs-lookup"><span data-stu-id="7e2f0-109">**Defining routing and message transformation through multiple orchestrations using itineraries**</span></span>  
  
 <span data-ttu-id="7e2f0-110">含まれている行程導入サンプル、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示します。</span><span class="sxs-lookup"><span data-stu-id="7e2f0-110">The Itinerary On-Ramp sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="7e2f0-111">解像度、ルーティングが含まれているスケジュールを作成し、呼び出し命令をサービスとして、一連のスケジュールの手順を定義する方法を示す方法、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]し、BizTalk Server は、入力メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="7e2f0-111">It shows how to create itineraries that contain resolution, routing, and service invocation instructions as a series of itinerary steps that define how the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] and BizTalk Server will process the input message.</span></span> <span data-ttu-id="7e2f0-112">一方向および要求-応答のサンプルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7e2f0-112">One-way and request-response samples are included.</span></span>  
  
 <span data-ttu-id="7e2f0-113">詳細については、次を参照してください。[をインストールすると、日程ランプでサンプルを実行する](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="7e2f0-113">For more information, see [Installing and Running the Itinerary On-Ramp Sample](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).</span></span>