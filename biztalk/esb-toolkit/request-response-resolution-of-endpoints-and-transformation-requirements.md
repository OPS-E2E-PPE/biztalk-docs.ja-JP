---
title: エンドポイントと変換の要件の要求-応答の解決 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a1bfdae-2651-402c-b164-16db663aaa95
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01ef1004d922fa8933ad021e958207ee36c91db6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400211"
---
# <a name="request-response-resolution-of-endpoints-and-transformation-requirements"></a><span data-ttu-id="641fe-102">エンドポイントと変換の要件の要求-応答の解決</span><span class="sxs-lookup"><span data-stu-id="641fe-102">Request-Response Resolution of Endpoints and Transformation Requirements</span></span>
<span data-ttu-id="641fe-103">このユース ケースでは、クライアント アプリケーションは、ランプの要求メッセージを送信して、応答を受信します。</span><span class="sxs-lookup"><span data-stu-id="641fe-103">In this use case, a client application submits a request message to an on-ramp and receives a response.</span></span> <span data-ttu-id="641fe-104">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]は、クライアントとターゲット サービスのエンドポイント間の媒介として機能し、ESB リゾルバーとアダプター フレームワークを使用して、図に示すように、動的なメッセージの変換と、ランプの構成に従ってルーティングを実行するには1。</span><span class="sxs-lookup"><span data-stu-id="641fe-104">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] acts as mediator between the client and the target service endpoint and uses the ESB Resolver and Adapter Framework to perform the dynamic message transformation and routing in accordance with the on-ramp configuration, as illustrated in Figure 1.</span></span>  
  
 <span data-ttu-id="641fe-105">![要求&#45;エンドポイントの応答の解決](../esb-toolkit/media/ch3-requestresponse.gif "Ch3 RequestResponse")</span><span class="sxs-lookup"><span data-stu-id="641fe-105">![Request&#45;Response Resolution of Endpoints](../esb-toolkit/media/ch3-requestresponse.gif "Ch3-RequestResponse")</span></span>  
  
 <span data-ttu-id="641fe-106">**図 1**</span><span class="sxs-lookup"><span data-stu-id="641fe-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="641fe-107">**エンドポイントと変換の要件の要求-応答の解決**</span><span class="sxs-lookup"><span data-stu-id="641fe-107">**Request-response resolution of endpoints and transformation requirements**</span></span>  
  
 <span data-ttu-id="641fe-108">動的解決サンプルに含まれている、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示します。</span><span class="sxs-lookup"><span data-stu-id="641fe-108">The Dynamic Resolution sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="641fe-109">動的変換と XML Path Language (XPath)、Universal Description, Discovery, and Integration (UDDI)、静的を使用して双方向のシナリオまたは BizTalk Server ビジネス ルール エンジンでのポリシーの解決を適用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="641fe-109">It shows how to apply dynamic transformation and resolution for two-way scenarios using XML Path Language (XPath), Universal Description, Discovery, and Integration (UDDI), STATIC, or policies in the BizTalk Server Business Rules Engine.</span></span>  
  
 <span data-ttu-id="641fe-110">詳細については、双方向メッセージング シナリオで説明を参照してください。[をインストールすると、動的解決サンプルを実行している](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="641fe-110">For more information, see the two-way messaging scenario described in [Installing and Running the Dynamic Resolution Sample](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md).</span></span>