---
title: ESB Itinerary フォワーダー コンポーネント |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 607cc8a0-4964-4751-baca-c3329983c98b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c61643423021701186745ab4275520cb14d3ceca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295338"
---
# <a name="the-esb-itinerary-forwarder-component"></a><span data-ttu-id="59629-102">ESB Itinerary フォワーダー コンポーネント</span><span class="sxs-lookup"><span data-stu-id="59629-102">The ESB Itinerary Forwarder Component</span></span>
<span data-ttu-id="59629-103">日程が複数の Web サービスを呼び出す必要があります順番に、ESB 行程フォワーダー コンポーネントが使用されます。</span><span class="sxs-lookup"><span data-stu-id="59629-103">The ESB Itinerary Forwarder component is used when an itinerary must sequentially invoke multiple Web services.</span></span> <span data-ttu-id="59629-104">コンポーネントを使用するのには、受信パイプライン、双方向出口の応答側に関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="59629-104">The component can be used in receive pipelines that are associated with the response side of a two-way off-ramp.</span></span>  
  
## <a name="installation"></a><span data-ttu-id="59629-105">インストール</span><span class="sxs-lookup"><span data-stu-id="59629-105">Installation</span></span>  
 <span data-ttu-id="59629-106">ESB コアを自動的にインストールするとインストール、**行程フォワーダー**コンポーネントを BizTalk Server パイプライン コンポーネント フォルダーでします。</span><span class="sxs-lookup"><span data-stu-id="59629-106">Installing the ESB Core automatically installs the **Itinerary Forwarder** component in the BizTalk Server Pipeline Components folder.</span></span>  
  
## <a name="how-it-works"></a><span data-ttu-id="59629-107">しくみ</span><span class="sxs-lookup"><span data-stu-id="59629-107">How It Works</span></span>  
 <span data-ttu-id="59629-108">Microsoft BizTalk の受信のように、メッセージは、メッセージ ボックス データベースに公開を介して、双方向メッセージ受信ポート、インスタンスのサブスクリプションを作成します。</span><span class="sxs-lookup"><span data-stu-id="59629-108">When Microsoft BizTalk receives a message through a two-way receive port as the message is published to the Message Box database, an instance subscription is created.</span></span> <span data-ttu-id="59629-109">このサブスクリプションから成る、 **EpmRRCorrelationToken**昇格されたプロパティと**RouteDirectToTP**プロパティを昇格します。</span><span class="sxs-lookup"><span data-stu-id="59629-109">This subscription consists of the **EpmRRCorrelationToken** promoted property and a **RouteDirectToTP** promoted property.</span></span> <span data-ttu-id="59629-110">サブスクライバー (オーケストレーションまたは双方向の送信ポート) には、応答メッセージが返されますとこれらの昇格させたプロパティ、サブスクリプションに一致応答が受信ポートの送信パイプラインを通じて直ちに返されます。</span><span class="sxs-lookup"><span data-stu-id="59629-110">When the subscriber (orchestration or two-way send port) returns the response message, these promoted properties match the subscription and the response is immediately returned through the send pipeline of the receive port.</span></span>  
  
 <span data-ttu-id="59629-111">ESB 行程フォワーダー必要がありますパイプラインで使用、応答を双方向出口のオフ ランプが要求-応答の Web サービスを呼び出すことです。</span><span class="sxs-lookup"><span data-stu-id="59629-111">The ESB Itinerary Forwarder should be used in the response pipeline for a two-way off-ramp where the off-ramp is calling a request-response Web service.</span></span> <span data-ttu-id="59629-112">コンポーネントが変更することによって、一般的な BizTalk プロセスに干渉、 **RouteDirectToTP**応答は返されません、開始するようになり、False に昇格させたプロパティがポートを受信します。</span><span class="sxs-lookup"><span data-stu-id="59629-112">The component interferes with the typical BizTalk process by changing the **RouteDirectToTP** promoted property to False, thus ensuring that the response will not be returned to the initiating receive port.</span></span> <span data-ttu-id="59629-113">旅行計画の最後の手順に達すると、 **RouteDirectToTP**にプロパティが変更された**True**、発信側で増加する結果を返すためです。</span><span class="sxs-lookup"><span data-stu-id="59629-113">After the last step in the itinerary is reached, the **RouteDirectToTP** property is changed back to **True**, thus returning the result to the initiating on-ramp.</span></span>  
  
## <a name="using-the-esb-itinerary-forwarder-component"></a><span data-ttu-id="59629-114">ESB Itinerary フォワーダー コンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="59629-114">Using the ESB Itinerary Forwarder Component</span></span>  
 <span data-ttu-id="59629-115">ESB ItineraryForwarder コンポーネントは、受信パイプラインに追加し、双方向出口の応答部分でパイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="59629-115">Add the ESB ItineraryForwarder component to a receive pipeline and then use the pipeline with the response portion of a two-way off-ramp.</span></span> <span data-ttu-id="59629-116">作成日程複数の Web サービスのチェーンされている変換 itinerary のサービスの有無前に、または、サービス間でします。</span><span class="sxs-lookup"><span data-stu-id="59629-116">Create an itinerary that chains multiple Web services, with or without transformation itinerary services, before or between the services.</span></span> <span data-ttu-id="59629-117">ESB 行程フォワーダー コンポーネントを使用する方法の例は、次を参照してください。、[をインストールすると、複数の Web サービス サンプルを実行している](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="59629-117">For an example of how to use the ESB Itinerary Forwarder Component, see the [Installing and Running the Multiple Web Services Sample](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md).</span></span>