---
title: 複数の Web サービスのサンプルの動作 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 16680ca7-16cc-47df-8c39-a3311d468a46
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b3d9faf350654be69015ea940b6b4f034d4de74
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294162"
---
# <a name="how-the-multiple-web-services-sample-works"></a><span data-ttu-id="05cf3-102">複数の Web サービス サンプルのしくみ</span><span class="sxs-lookup"><span data-stu-id="05cf3-102">How the Multiple Web Services Sample Works</span></span>
<span data-ttu-id="05cf3-103">複数の Web サービス サンプルでは、2 つの独立した手法を使用して、呼び出し元に適切な結果を返す直列に複数の Web サービスを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="05cf3-103">The Multiple Web Services sample uses two separate techniques to call multiple Web services in serial while still being able to return a proper result to the original caller.</span></span> <span data-ttu-id="05cf3-104">1 つのメソッドでは、応答パイプラインのカスタム パイプライン コンポーネントとその他のメソッド、カスタム双方向ルーティング オーケストレーションに基づく itinerary サービスを使用して web 要求/応答呼び出しを完了する出口呼び出しの要件をバイパスします。サービス。</span><span class="sxs-lookup"><span data-stu-id="05cf3-104">One method uses a custom pipeline component in the response pipeline, and the other method uses a custom two-way routing orchestration-based itinerary service that bypasses the requirement of an off-ramp invocation to complete a request/response call to a Web service.</span></span>  
  
 <span data-ttu-id="05cf3-105">カスタム パイプライン コンポーネントのメソッドは、フォワーダーのパイプライン コンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="05cf3-105">The custom pipeline component method uses the Forwarder Pipeline component.</span></span> <span data-ttu-id="05cf3-106">このコンポーネントは、条件付きで、Microsoft BizTalk が itinerary のすべてのサービスが処理されるまで、入り口の送信パイプラインにメッセージをルーティングすることを防止するプロパティを昇格させます。</span><span class="sxs-lookup"><span data-stu-id="05cf3-106">This component conditionally promotes properties to keep Microsoft BizTalk from routing the message back to the send pipeline of the on-ramp until all the itinerary services are processed.</span></span>  
  
 <span data-ttu-id="05cf3-107">カスタム オーケストレーションに基づくサービス メソッドは、ESB に含まれている TwoWayRouting オーケストレーションを使用します。\Source\Samples\MultipleWebSerivces\Source\ESB MultipleWebServices.Orchestrations プロジェクトです。MultipleWebServices.Orchestrations フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="05cf3-107">The custom orchestration-based service method uses the TwoWayRouting orchestration contained in the ESB.MultipleWebServices.Orchestrations project in the \Source\Samples\MultipleWebSerivces\Source\ESB.MultipleWebServices.Orchestrations folder.</span></span> <span data-ttu-id="05cf3-108">このサービスは、双方向の Web サービスのエンドポイント アドレスを決定する関連付けの競合回避モジュールを処理します。</span><span class="sxs-lookup"><span data-stu-id="05cf3-108">This service processes an associated resolver to determine the endpoint address of a two-way Web service.</span></span> <span data-ttu-id="05cf3-109">という名前を Web サービスにメッセージを送信し、オーケストレーションに結果を返す RoutingPort 動的 Solict-応答送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="05cf3-109">It then configures a Dynamic Solict-Response Send Port named RoutingPort to send the message to the Web service and return the result to the orchestration.</span></span> <span data-ttu-id="05cf3-110">オーケストレーションは、旅行計画を進めるし、メッセージ ボックスに、結果のメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="05cf3-110">The orchestration then advances the itinerary and returns the resulting message to the MessageBox.</span></span>  
  
 <span data-ttu-id="05cf3-111">サンプルに含まれている旅程は、メッセージ フローの次の旅行計画を維持するのにこれらのメソッドの一方または両方を使用します。</span><span class="sxs-lookup"><span data-stu-id="05cf3-111">The itineraries included with the sample use one or both of these methods to ensure message flow following the itinerary is maintained.</span></span> <span data-ttu-id="05cf3-112">詳細については、次を参照してください。 [、サンプル複数 Web Services 旅程](../esb-toolkit/the-sample-multiple-web-services-itineraries.md)です。</span><span class="sxs-lookup"><span data-stu-id="05cf3-112">For more information, see [The Sample Multiple Web Services Itineraries](../esb-toolkit/the-sample-multiple-web-services-itineraries.md).</span></span>