---
title: 変換と、複数のエンドポイントへのメッセージのルーティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 544db12c-95fc-4321-b397-ec9e7410e37d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c05d76c9f964ccfd326ed5091152545ee647a64
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399613"
---
# <a name="transforming-and-routing-a-message-to-multiple-endpoints"></a><span data-ttu-id="9cf7a-102">変換と、複数のエンドポイントへのメッセージのルーティング</span><span class="sxs-lookup"><span data-stu-id="9cf7a-102">Transforming and Routing a Message to Multiple Endpoints</span></span>
<span data-ttu-id="9cf7a-103">このユース ケースで、ESB は、旅行プランの Web サービスに着手を通じて送信されるメッセージの変換を実行します。</span><span class="sxs-lookup"><span data-stu-id="9cf7a-103">In this use case, the ESB performs a transformation on a message submitted through the Itinerary Web service on-ramp.</span></span> <span data-ttu-id="9cf7a-104">動的解決の参照は、マップの名前を決定し、受信メッセージを変換します。</span><span class="sxs-lookup"><span data-stu-id="9cf7a-104">A dynamic resolution lookup determines the map name and transforms the inbound message.</span></span> <span data-ttu-id="9cf7a-105">さらに、旅行計画には、n 個のスケジュール サービスを動的に解決して、変換されたメッセージをルーティングするターゲット エンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="9cf7a-105">Additionally, the itinerary specifies n number of target endpoints that the Itinerary service will dynamically resolve and to which it will route the transformed message.</span></span> <span data-ttu-id="9cf7a-106">図 1 に示すように、すべての操作は、メッセージング層で発生します。</span><span class="sxs-lookup"><span data-stu-id="9cf7a-106">All operations occur at the messaging layer, as illustrated in Figure 1.</span></span>  
  
 <span data-ttu-id="9cf7a-107">![複数のエンドポイントの変換](../esb-toolkit/media/ch3-transformingmultipleendpoints.gif "Ch3 TransformingMultipleEndpoints")</span><span class="sxs-lookup"><span data-stu-id="9cf7a-107">![Transforming Multiple Endpoints](../esb-toolkit/media/ch3-transformingmultipleendpoints.gif "Ch3-TransformingMultipleEndpoints")</span></span>  
  
 <span data-ttu-id="9cf7a-108">**図 1**</span><span class="sxs-lookup"><span data-stu-id="9cf7a-108">**Figure 1**</span></span>  
  
 <span data-ttu-id="9cf7a-109">**変換と、複数のエンドポイントへのメッセージのルーティング**</span><span class="sxs-lookup"><span data-stu-id="9cf7a-109">**Transforming and routing a message to multiple endpoints**</span></span>  
  
 <span data-ttu-id="9cf7a-110">動的解決サンプルに含まれている、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示します。</span><span class="sxs-lookup"><span data-stu-id="9cf7a-110">The Dynamic Resolution sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="9cf7a-111">ESB ディスパッチの逆アセンブラー コンポーネントでは具体的には、ESB パイプライン コンポーネントを使用する方法を示しますを使用せず、メッセージング レベルでのマップを動的にエンドポイントの場所を解決するには、ルーティング プロパティを設定し、解決して BizTalk Server を実行します。オーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="9cf7a-111">It shows how to use ESB pipeline components, specifically the ESB Dispatch Disassembler component, to dynamically resolve endpoint location, set routing properties, and resolve and execute BizTalk Server maps at the messaging level, without using an orchestration.</span></span> <span data-ttu-id="9cf7a-112">一方向と双方向の両方のメッセージング パターンも示します。</span><span class="sxs-lookup"><span data-stu-id="9cf7a-112">It also demonstrates both one-way and two-way messaging patterns.</span></span>  
  
 <span data-ttu-id="9cf7a-113">詳細については、次を参照してください。[をインストールすると、動的解決サンプルを実行している](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)と[をインストールすると、複数の Web サービス サンプルを実行している](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="9cf7a-113">For more information, see [Installing and Running the Dynamic Resolution Sample](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md) and [Installing and Running the Multiple Web Services Sample](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md).</span></span>