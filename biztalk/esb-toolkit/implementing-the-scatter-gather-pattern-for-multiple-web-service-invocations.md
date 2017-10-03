---
title: "複数の Web サービス呼び出しのスキャッター/ギャザー パターンの実装 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 912512a4-9649-40df-bb82-b8f4b85c8ca6
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03fb129d23b0884fdca518dca574be64d7672c6c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="implementing-the-scatter-gather-pattern-for-multiple-web-service-invocations"></a><span data-ttu-id="9d82d-102">複数の Web サービス呼び出しのスキャッター/ギャザー パターンの実装</span><span class="sxs-lookup"><span data-stu-id="9d82d-102">Implementing the Scatter-Gather Pattern for Multiple Web Service Invocations</span></span>
<span data-ttu-id="9d82d-103">このユース ケースを含むメッセージを 1 つ以上の外部サービスを指定する itinerary サービス ステップ[!INCLUDE[prague](../includes/prague-md.md)]アクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d82d-103">In this use case, a message contains an itinerary service step that specifies more than one external service that [!INCLUDE[prague](../includes/prague-md.md)] should access.</span></span> <span data-ttu-id="9d82d-104">サービスの場所を決定する動的な解決を使用し、エンドポイントと省略可能な BizTalk サービスが、返されたデータを変換するマップします。</span><span class="sxs-lookup"><span data-stu-id="9d82d-104">It uses dynamic resolution to determine service locations and endpoints and any optional BizTalk Service maps for transforming the returned data.</span></span> <span data-ttu-id="9d82d-105">このサービスを実装するオーケストレーションが、変換と、呼び出しを実行し、すべてのサービスの呼び出しが非同期に行わします。</span><span class="sxs-lookup"><span data-stu-id="9d82d-105">The orchestration implementing this service performs the transformation and invocations, and all service invocations occur asynchronously.</span></span> <span data-ttu-id="9d82d-106">すべてのサービスの呼び出しが完了すると、itinerary サービスは 1 つの応答メッセージに応答を集計し、動的に割り当てられているエンドポイントを使用してクライアントにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="9d82d-106">After all service invocations complete, the itinerary service aggregates the responses into a single response message and sends the message to the client through a dynamically assigned endpoint.</span></span> <span data-ttu-id="9d82d-107">図 1 は、このユース ケースを示しています。</span><span class="sxs-lookup"><span data-stu-id="9d82d-107">Figure 1 illustrates this use case.</span></span>  
  
 <span data-ttu-id="9d82d-108">![散布図を実装するギャザー パターン](../esb-toolkit/media/ch3-implementingscatter.gif "Ch3 ImplementingScatter")</span><span class="sxs-lookup"><span data-stu-id="9d82d-108">![Implementing Scatter Gather Pattern](../esb-toolkit/media/ch3-implementingscatter.gif "Ch3-ImplementingScatter")</span></span>  
  
 <span data-ttu-id="9d82d-109">**図 1**</span><span class="sxs-lookup"><span data-stu-id="9d82d-109">**Figure 1**</span></span>  
  
 <span data-ttu-id="9d82d-110">**複数の Web サービス呼び出しのスキャッター/ギャザー パターンの実装**</span><span class="sxs-lookup"><span data-stu-id="9d82d-110">**Implementing the Scatter-Gather pattern for multiple Web service invocations**</span></span>  
  
 <span data-ttu-id="9d82d-111">スキャッター/ギャザー サンプルに含まれている、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示しています。</span><span class="sxs-lookup"><span data-stu-id="9d82d-111">The Scatter-Gather sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span>  
  
 <span data-ttu-id="9d82d-112">詳細については、次を参照してください。[をインストールすると、スキャッター/ギャザー サンプルを実行している](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="9d82d-112">For more information, see [Installing and Running the Scatter-Gather Sample](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md).</span></span>