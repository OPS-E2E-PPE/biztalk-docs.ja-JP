---
title: 複数の Web サービスのサンプルのしくみ |Microsoft Docs
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
ms.openlocfilehash: 2a67e14115d404f523219b2e171f1abfba38b220
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65249774"
---
# <a name="how-the-multiple-web-services-sample-works"></a><span data-ttu-id="dbaf8-102">複数の Web サービス サンプルのしくみ</span><span class="sxs-lookup"><span data-stu-id="dbaf8-102">How the Multiple Web Services Sample Works</span></span>
<span data-ttu-id="dbaf8-103">複数の Web サービス サンプルでは、2 つの独立した手法を使用して、シリアルでを呼び出し元に適切な結果を返すことながら複数の Web サービスを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="dbaf8-103">The Multiple Web Services sample uses two separate techniques to call multiple Web services in serial while still being able to return a proper result to the original caller.</span></span> <span data-ttu-id="dbaf8-104">1 つのメソッドが応答パイプラインでは、カスタム パイプライン コンポーネントを使用し、もう一方のメソッドをカスタム双方向ルーティング オーケストレーションに基づく itinerary サービスを使用して web 要求/応答の呼び出しを完了するランプ オフ呼び出しの要件をバイパスします。サービス。</span><span class="sxs-lookup"><span data-stu-id="dbaf8-104">One method uses a custom pipeline component in the response pipeline, and the other method uses a custom two-way routing orchestration-based itinerary service that bypasses the requirement of an off-ramp invocation to complete a request/response call to a Web service.</span></span>  
  
 <span data-ttu-id="dbaf8-105">カスタム パイプライン コンポーネントのメソッドは、フォワーダーのパイプライン コンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="dbaf8-105">The custom pipeline component method uses the Forwarder Pipeline component.</span></span> <span data-ttu-id="dbaf8-106">このコンポーネントは、条件付きで Microsoft BizTalk がスケジュールのすべてのサービスが処理されるまでのランプの送信パイプラインにメッセージをルーティングするを防ぐためのプロパティを昇格させます。</span><span class="sxs-lookup"><span data-stu-id="dbaf8-106">This component conditionally promotes properties to keep Microsoft BizTalk from routing the message back to the send pipeline of the on-ramp until all the itinerary services are processed.</span></span>  
  
 <span data-ttu-id="dbaf8-107">カスタム オーケストレーションに基づくサービスのメソッドは、ESB に含まれている TwoWayRouting オーケストレーションを使用します。\Source\Samples\MultipleWebSerivces\Source\ESB MultipleWebServices.Orchestrations プロジェクトです。MultipleWebServices.Orchestrations フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="dbaf8-107">The custom orchestration-based service method uses the TwoWayRouting orchestration contained in the ESB.MultipleWebServices.Orchestrations project in the \Source\Samples\MultipleWebSerivces\Source\ESB.MultipleWebServices.Orchestrations folder.</span></span> <span data-ttu-id="dbaf8-108">このサービスは、双方向の Web サービスのエンドポイント アドレスを決定する関連付けの競合回避モジュールを処理します。</span><span class="sxs-lookup"><span data-stu-id="dbaf8-108">This service processes an associated resolver to determine the endpoint address of a two-way Web service.</span></span> <span data-ttu-id="dbaf8-109">という名前の Web サービスにメッセージを送信し、オーケストレーションに結果を返す RoutingPort 動的 Solict-応答送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="dbaf8-109">It then configures a Dynamic Solict-Response Send Port named RoutingPort to send the message to the Web service and return the result to the orchestration.</span></span> <span data-ttu-id="dbaf8-110">オーケストレーションは、旅行計画を進めるし、メッセージ ボックスに、結果のメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="dbaf8-110">The orchestration then advances the itinerary and returns the resulting message to the MessageBox.</span></span>  
  
 <span data-ttu-id="dbaf8-111">サンプルに含まれているスケジュールは、旅行プランを次のメッセージ フローを維持すること、これらのメソッドの一方または両方を使用します。</span><span class="sxs-lookup"><span data-stu-id="dbaf8-111">The itineraries included with the sample use one or both of these methods to ensure message flow following the itinerary is maintained.</span></span> <span data-ttu-id="dbaf8-112">詳細については、次を参照してください。 [、サンプル複数 Web Services 日程](../esb-toolkit/the-sample-multiple-web-services-itineraries.md)します。</span><span class="sxs-lookup"><span data-stu-id="dbaf8-112">For more information, see [The Sample Multiple Web Services Itineraries](../esb-toolkit/the-sample-multiple-web-services-itineraries.md).</span></span>