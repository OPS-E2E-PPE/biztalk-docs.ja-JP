---
title: ESB スケジュール フォワーダー コンポーネント |Microsoft Docs
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
ms.openlocfilehash: e23368b1d74a2842659332d2c545b93e24386455
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399787"
---
# <a name="the-esb-itinerary-forwarder-component"></a><span data-ttu-id="36cee-102">ESB スケジュール フォワーダー コンポーネント</span><span class="sxs-lookup"><span data-stu-id="36cee-102">The ESB Itinerary Forwarder Component</span></span>
<span data-ttu-id="36cee-103">ESB スケジュール フォワーダー コンポーネントは、スケジュールは、複数の Web サービスを呼び出す必要があります順番に使用されます。</span><span class="sxs-lookup"><span data-stu-id="36cee-103">The ESB Itinerary Forwarder component is used when an itinerary must sequentially invoke multiple Web services.</span></span> <span data-ttu-id="36cee-104">コンポーネントを使用するのには、受信パイプラインは双方向オフ-ごとの傾斜増加の応答側に関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="36cee-104">The component can be used in receive pipelines that are associated with the response side of a two-way off-ramp.</span></span>  
  
## <a name="installation"></a><span data-ttu-id="36cee-105">インストール</span><span class="sxs-lookup"><span data-stu-id="36cee-105">Installation</span></span>  
 <span data-ttu-id="36cee-106">ESB コアを自動的にインストールするインストール、**スケジュール フォワーダー**コンポーネントを BizTalk Server パイプライン コンポーネント フォルダーでします。</span><span class="sxs-lookup"><span data-stu-id="36cee-106">Installing the ESB Core automatically installs the **Itinerary Forwarder** component in the BizTalk Server Pipeline Components folder.</span></span>  
  
## <a name="how-it-works"></a><span data-ttu-id="36cee-107">しくみ</span><span class="sxs-lookup"><span data-stu-id="36cee-107">How It Works</span></span>  
 <span data-ttu-id="36cee-108">Microsoft BizTalk が受信すると、メッセージがメッセージ ボックス データベースに公開されると、双方向でメッセージを受信ポート、インスタンスのサブスクリプションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="36cee-108">When Microsoft BizTalk receives a message through a two-way receive port as the message is published to the Message Box database, an instance subscription is created.</span></span> <span data-ttu-id="36cee-109">このサブスクリプションから成る、 **EpmRRCorrelationToken**プロパティを昇格と**RouteDirectToTP**プロパティを昇格します。</span><span class="sxs-lookup"><span data-stu-id="36cee-109">This subscription consists of the **EpmRRCorrelationToken** promoted property and a **RouteDirectToTP** promoted property.</span></span> <span data-ttu-id="36cee-110">サブスクライバー (オーケストレーションまたは双方向の送信ポート) には、応答メッセージが返される、ときにこれらの昇格させたプロパティは、サブスクリプションを照合し、応答がすぐに受信ポートの送信パイプラインを通じて返されます。</span><span class="sxs-lookup"><span data-stu-id="36cee-110">When the subscriber (orchestration or two-way send port) returns the response message, these promoted properties match the subscription and the response is immediately returned through the send pipeline of the receive port.</span></span>  
  
 <span data-ttu-id="36cee-111">ESB スケジュール フォワーダーを付ける応答パイプラインでの双方向オフ-ごとの傾斜増加オフ ランプが要求-応答 Web サービスを呼び出すことです。</span><span class="sxs-lookup"><span data-stu-id="36cee-111">The ESB Itinerary Forwarder should be used in the response pipeline for a two-way off-ramp where the off-ramp is calling a request-response Web service.</span></span> <span data-ttu-id="36cee-112">変更することで、一般的な BizTalk プロセス コンポーネントと競合、 **RouteDirectToTP**確認応答を開始する返されませんが、昇格させたプロパティを False、受信ポート。</span><span class="sxs-lookup"><span data-stu-id="36cee-112">The component interferes with the typical BizTalk process by changing the **RouteDirectToTP** promoted property to False, thus ensuring that the response will not be returned to the initiating receive port.</span></span> <span data-ttu-id="36cee-113">旅行プランの最後の手順に達すると、 **RouteDirectToTP**にプロパティが変更された**True**、発信側に着手する結果を返すためです。</span><span class="sxs-lookup"><span data-stu-id="36cee-113">After the last step in the itinerary is reached, the **RouteDirectToTP** property is changed back to **True**, thus returning the result to the initiating on-ramp.</span></span>  
  
## <a name="using-the-esb-itinerary-forwarder-component"></a><span data-ttu-id="36cee-114">ESB スケジュール フォワーダー コンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="36cee-114">Using the ESB Itinerary Forwarder Component</span></span>  
 <span data-ttu-id="36cee-115">ESB ItineraryForwarder コンポーネントを受信パイプラインに追加し、双方向オフ-ごとの傾斜増加の応答部分でパイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="36cee-115">Add the ESB ItineraryForwarder component to a receive pipeline and then use the pipeline with the response portion of a two-way off-ramp.</span></span> <span data-ttu-id="36cee-116">スケジュールを作成チェーンされている複数の Web サービスは、変換のスケジュール サービスの有無の前に、またはサービスの間で。</span><span class="sxs-lookup"><span data-stu-id="36cee-116">Create an itinerary that chains multiple Web services, with or without transformation itinerary services, before or between the services.</span></span> <span data-ttu-id="36cee-117">ESB スケジュール フォワーダー コンポーネントを使用する方法の例は、次を参照してください。、[をインストールすると、複数の Web サービス サンプルを実行している](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="36cee-117">For an example of how to use the ESB Itinerary Forwarder Component, see the [Installing and Running the Multiple Web Services Sample](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md).</span></span>