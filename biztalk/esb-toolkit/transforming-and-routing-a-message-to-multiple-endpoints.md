---
title: "変換して、複数のエンドポイントにメッセージをルーティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 544db12c-95fc-4321-b397-ec9e7410e37d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c0fc2b3b9893607f760c564d03fc6090a7f1ea0
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="transforming-and-routing-a-message-to-multiple-endpoints"></a><span data-ttu-id="9e336-102">変換して、複数のエンドポイントにメッセージのルーティング</span><span class="sxs-lookup"><span data-stu-id="9e336-102">Transforming and Routing a Message to Multiple Endpoints</span></span>
<span data-ttu-id="9e336-103">このユース ケースでは、ESB は、行程 Web サービスに着手を通じて送信されたメッセージの変換を実行します。</span><span class="sxs-lookup"><span data-stu-id="9e336-103">In this use case, the ESB performs a transformation on a message submitted through the Itinerary Web service on-ramp.</span></span> <span data-ttu-id="9e336-104">動的解決の参照は、マップ名を決定し、受信メッセージを変換します。</span><span class="sxs-lookup"><span data-stu-id="9e336-104">A dynamic resolution lookup determines the map name and transforms the inbound message.</span></span> <span data-ttu-id="9e336-105">さらに、旅行計画には、行程サービスを動的に解決して、変換後のメッセージをルーティングするターゲット エンドポイントの n の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="9e336-105">Additionally, the itinerary specifies n number of target endpoints that the Itinerary service will dynamically resolve and to which it will route the transformed message.</span></span> <span data-ttu-id="9e336-106">図 1 に示すように、すべての操作は、メッセージング レイヤーで発生します。</span><span class="sxs-lookup"><span data-stu-id="9e336-106">All operations occur at the messaging layer, as illustrated in Figure 1.</span></span>  
  
 <span data-ttu-id="9e336-107">![複数のエンドポイントを変換する](../esb-toolkit/media/ch3-transformingmultipleendpoints.gif "Ch3 TransformingMultipleEndpoints")</span><span class="sxs-lookup"><span data-stu-id="9e336-107">![Transforming Multiple Endpoints](../esb-toolkit/media/ch3-transformingmultipleendpoints.gif "Ch3-TransformingMultipleEndpoints")</span></span>  
  
 <span data-ttu-id="9e336-108">**図 1**</span><span class="sxs-lookup"><span data-stu-id="9e336-108">**Figure 1**</span></span>  
  
 <span data-ttu-id="9e336-109">**変換して、複数のエンドポイントにメッセージのルーティング**</span><span class="sxs-lookup"><span data-stu-id="9e336-109">**Transforming and routing a message to multiple endpoints**</span></span>  
  
 <span data-ttu-id="9e336-110">動的解決サンプルに含まれている、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示しています。</span><span class="sxs-lookup"><span data-stu-id="9e336-110">The Dynamic Resolution sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="9e336-111">ESB のパイプライン コンポーネントを具体的には、ESB ディスパッチ逆アセンブラーを使用する方法を示していますを使用せず、メッセージ レベルでマップを動的にエンドポイントの場所を解決するには、ルーティングのプロパティを設定し、解決するにはおよび BizTalk Server を実行します。オーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="9e336-111">It shows how to use ESB pipeline components, specifically the ESB Dispatch Disassembler component, to dynamically resolve endpoint location, set routing properties, and resolve and execute BizTalk Server maps at the messaging level, without using an orchestration.</span></span> <span data-ttu-id="9e336-112">また、一方向と双方向の両方のメッセージング パターンを示します。</span><span class="sxs-lookup"><span data-stu-id="9e336-112">It also demonstrates both one-way and two-way messaging patterns.</span></span>  
  
 <span data-ttu-id="9e336-113">詳細については、次を参照してください。[をインストールすると、動的の解決サンプルを実行している](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)と[をインストールすると、複数の Web サービス サンプルを実行している](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="9e336-113">For more information, see [Installing and Running the Dynamic Resolution Sample](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md) and [Installing and Running the Multiple Web Services Sample](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md).</span></span>