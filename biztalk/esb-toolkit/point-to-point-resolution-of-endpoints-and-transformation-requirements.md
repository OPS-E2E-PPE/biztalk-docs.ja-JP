---
title: "ポイント ツー ポイントの解像度のエンドポイントと変換の要件 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c4c570bf-8274-4779-ae83-2aef2bf57ded
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8899c5f713f1c9ebfe299d3e431754dd8b9794d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="point-to-point-resolution-of-endpoints-and-transformation-requirements"></a><span data-ttu-id="152a5-102">エンドポイントおよび変換の要件のポイント間の解決</span><span class="sxs-lookup"><span data-stu-id="152a5-102">Point-to-Point Resolution of Endpoints and Transformation Requirements</span></span>
<span data-ttu-id="152a5-103">このユース ケースでは、Web サービス クライアントは、ESB を通らずに Web サービスを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="152a5-103">In this use case, a Web service client calls a Web service without going through the ESB.</span></span> <span data-ttu-id="152a5-104">2 つのポイントが直接、通信が、Web サービスのエンドポイントを解決する必要があります、クライアントは、呼び出しを行い、前にします。</span><span class="sxs-lookup"><span data-stu-id="152a5-104">The two points communicate directly, but before the client makes the call, it must resolve the endpoint of the Web service.</span></span> <span data-ttu-id="152a5-105">Web サービスへの呼び出しは、一方向または要求-応答のいずれかにできます。</span><span class="sxs-lookup"><span data-stu-id="152a5-105">The call to the Web service can be either a one-way or a request-response.</span></span> <span data-ttu-id="152a5-106">これを実現するための 1 つの方法では、図 1 に示すように、ESB の動的な解決機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="152a5-106">One way of achieving this is to use the dynamic resolution features of the ESB, as shown in Figure 1.</span></span>  
  
 <span data-ttu-id="152a5-107">![ポイント &#45; へ (& a) #45 です。エンドポイントのポイント解決](../esb-toolkit/media/ch3-pointtopoint.gif "Ch3 ポイントツー ポイント ・")</span><span class="sxs-lookup"><span data-stu-id="152a5-107">![Point&#45;to&#45;Point Resolution of Endpoints](../esb-toolkit/media/ch3-pointtopoint.gif "Ch3-PointToPoint")</span></span>  
  
 <span data-ttu-id="152a5-108">**図 1**</span><span class="sxs-lookup"><span data-stu-id="152a5-108">**Figure 1**</span></span>  
  
 <span data-ttu-id="152a5-109">**UDDI を使用してエンドポイントを解決します。**</span><span class="sxs-lookup"><span data-stu-id="152a5-109">**Resolving endpoints using UDDI**</span></span>  
  
 <span data-ttu-id="152a5-110">含まれているリゾルバー サービスのサンプル、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示しています。</span><span class="sxs-lookup"><span data-stu-id="152a5-110">The Resolver Service sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="152a5-111">サンプルは、Universal Description, Discovery, and Integration (UDDI)、XML パス言語 (XPath) など、バックエンド ストアの内容を開発しているように、解決をテストすることにより解決を実行する ESB リゾルバー サービスを呼び出す方法を示しています。スタティック、または BizTalk Server のビジネス ルール エンジンのポリシー。</span><span class="sxs-lookup"><span data-stu-id="152a5-111">The sample shows how to call the ESB Resolver Service to perform resolution, which enables you to test resolution as you are developing the contents of the back-end stores, such as Universal Description, Discovery, and Integration (UDDI), XML Path Language (XPath), Static, or policies in the BizTalk Server Business Rules Engine.</span></span>  
  
 <span data-ttu-id="152a5-112">詳細については、次を参照してください。[をインストールすると、リゾルバー サービスのサンプルを実行している](../esb-toolkit/installing-and-running-the-resolver-service-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="152a5-112">For more information, see [Installing and Running the Resolver Service Sample](../esb-toolkit/installing-and-running-the-resolver-service-sample.md).</span></span>