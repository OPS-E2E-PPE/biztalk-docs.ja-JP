---
title: 要求-応答の解決エンドポイントおよび変換の要件 |Microsoft ドキュメント
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
ms.openlocfilehash: 72f442f1d9df457a3c1384f1d717e29c17b433f4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294570"
---
# <a name="request-response-resolution-of-endpoints-and-transformation-requirements"></a><span data-ttu-id="8e363-102">要求-応答の解決エンドポイントおよび変換の要件</span><span class="sxs-lookup"><span data-stu-id="8e363-102">Request-Response Resolution of Endpoints and Transformation Requirements</span></span>
<span data-ttu-id="8e363-103">このユース ケースでは、クライアント アプリケーションは、ランプで要求メッセージを送信し、応答を受信します。</span><span class="sxs-lookup"><span data-stu-id="8e363-103">In this use case, a client application submits a request message to an on-ramp and receives a response.</span></span> <span data-ttu-id="8e363-104">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]クライアントとターゲットのサービス エンドポイント間の媒介として機能し、図に示すように、動的なメッセージの変換と、入り口構成に従ってルーティングを実行する、ESB 競合回避モジュールとアダプター フレームワークを使用1。</span><span class="sxs-lookup"><span data-stu-id="8e363-104">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] acts as mediator between the client and the target service endpoint and uses the ESB Resolver and Adapter Framework to perform the dynamic message transformation and routing in accordance with the on-ramp configuration, as illustrated in Figure 1.</span></span>  
  
 <span data-ttu-id="8e363-105">![要求 &#45;エンドポイントの応答の解決](../esb-toolkit/media/ch3-requestresponse.gif "Ch3 RequestResponse")</span><span class="sxs-lookup"><span data-stu-id="8e363-105">![Request&#45;Response Resolution of Endpoints](../esb-toolkit/media/ch3-requestresponse.gif "Ch3-RequestResponse")</span></span>  
  
 <span data-ttu-id="8e363-106">**図 1**</span><span class="sxs-lookup"><span data-stu-id="8e363-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="8e363-107">**要求-応答の解決エンドポイントおよび変換の要件**</span><span class="sxs-lookup"><span data-stu-id="8e363-107">**Request-response resolution of endpoints and transformation requirements**</span></span>  
  
 <span data-ttu-id="8e363-108">動的解決サンプルに含まれている、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示しています。</span><span class="sxs-lookup"><span data-stu-id="8e363-108">The Dynamic Resolution sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="8e363-109">動的な変換と XML Path Language (XPath)、Universal Description, Discovery, and Integration (UDDI)、静的を使用する双方向のシナリオまたは BizTalk Server のビジネス ルール エンジンのポリシーの解決を適用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8e363-109">It shows how to apply dynamic transformation and resolution for two-way scenarios using XML Path Language (XPath), Universal Description, Discovery, and Integration (UDDI), STATIC, or policies in the BizTalk Server Business Rules Engine.</span></span>  
  
 <span data-ttu-id="8e363-110">詳細についてで説明する双方向のメッセージング シナリオを参照してください。[をインストールすると、動的の解決サンプルを実行している](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="8e363-110">For more information, see the two-way messaging scenario described in [Installing and Running the Dynamic Resolution Sample](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md).</span></span>