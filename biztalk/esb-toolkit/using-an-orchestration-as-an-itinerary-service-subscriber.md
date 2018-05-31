---
title: オーケストレーションを使用して、Itinerary サービス サブスクライバーとして |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 278564f1-de9f-4fbf-8c7f-09b3e607c28b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f496884d0aed8d5f351f681ca8cfe59e05684240
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295322"
---
# <a name="using-an-orchestration-as-an-itinerary-service-subscriber"></a><span data-ttu-id="32067-102">Itinerary サービス サブスクライバーとして、オーケストレーションを使用します。</span><span class="sxs-lookup"><span data-stu-id="32067-102">Using an Orchestration as an Itinerary Service Subscriber</span></span>
<span data-ttu-id="32067-103">オーケストレーション itinerary サービスとして動作することもできます。</span><span class="sxs-lookup"><span data-stu-id="32067-103">Orchestrations can also act as itinerary services.</span></span> <span data-ttu-id="32067-104">参加するには、行程でオーケストレーション直接バインド; としてを最初にデザインする必要があります。これを行うと類似の前のトピックでは、送信ポート フィルター サブスクリプションを使用して[行程サービス サブスクライバーとして、送信ポートを使用して](../esb-toolkit/using-a-send-port-as-an-itinerary-service-subscriber.md)です。</span><span class="sxs-lookup"><span data-stu-id="32067-104">To participate in an itinerary, you must first design the orchestration as direct-bound; to do this, use a filter subscription similar to that of the send port in the previous topic, [Using a Send Port as an Itinerary Service Subscriber](../esb-toolkit/using-a-send-port-as-an-itinerary-service-subscriber.md).</span></span> <span data-ttu-id="32067-105">図 1 は、次の条件を満たすすべてのメッセージを取得するのに適切なオーケストレーションのフィルター式の例を示します。</span><span class="sxs-lookup"><span data-stu-id="32067-105">Figure 1 shows an example of a filter expression for a suitable orchestration to pick up any message that meets the following conditions:</span></span>  
  
-   <span data-ttu-id="32067-106">**ServiceName = Microsoft.Practices.ESB.Services.Transform**</span><span class="sxs-lookup"><span data-stu-id="32067-106">**ServiceName = Microsoft.Practices.ESB.Services.Transform**</span></span>  
  
-   <span data-ttu-id="32067-107">**ServiceState = 保留中**</span><span class="sxs-lookup"><span data-stu-id="32067-107">**ServiceState = Pending**</span></span>  
  
-   <span data-ttu-id="32067-108">**ServiceType オーケストレーションを =**</span><span class="sxs-lookup"><span data-stu-id="32067-108">**ServiceType = Orchestration**</span></span>  
  
 <span data-ttu-id="32067-109">![オーケストレーション](../esb-toolkit/media/ch4-orchestration.jpg "Ch4 オーケストレーション")</span><span class="sxs-lookup"><span data-stu-id="32067-109">![Orchestration](../esb-toolkit/media/ch4-orchestration.jpg "Ch4-Orchestration")</span></span>  
  
 <span data-ttu-id="32067-110">**図 1**</span><span class="sxs-lookup"><span data-stu-id="32067-110">**Figure 1**</span></span>  
  
 <span data-ttu-id="32067-111">**サブスクライバーとして日程に参加するオーケストレーションのフィルター式の例**</span><span class="sxs-lookup"><span data-stu-id="32067-111">**Example filter expression for an orchestration that will participate in an itinerary as a subscriber**</span></span>  
  
 <span data-ttu-id="32067-112">Microsoft BizTalk Server で ESB 入り口を介してメッセージを受信と、ESB パイプラインで検証手順には、受信メッセージの BizTalk コンテキスト プロパティにフィルターのプロパティのプロパティ値を書き込みますこれは、メッセージ コンテキストにそれらを昇格します。</span><span class="sxs-lookup"><span data-stu-id="32067-112">When messages arrive in Microsoft BizTalk Server through an ESB on-ramp, the validation step in the ESB pipeline writes the property values for the filter properties into the BizTalk context properties of the incoming message; this promotes them to the message context.</span></span> <span data-ttu-id="32067-113">Itinerary サービスは常に、設定、 **ServiceName**プロパティを次に、処理するサービスの名前に、現在アクティブなサービスを**ServiceState**のプロパティの値**保留中**です。</span><span class="sxs-lookup"><span data-stu-id="32067-113">The itinerary service always sets the **ServiceName** property for the currently active service to the name of the service to process next, and with a **ServiceState** property value of **Pending**.</span></span> <span data-ttu-id="32067-114">サブスクリプションを設定する必要が少なくとも 1 つ目、次のプロパティのうち 3 つ。</span><span class="sxs-lookup"><span data-stu-id="32067-114">For a subscription, you must set at least the first three of the following properties:</span></span>  
  
-   <span data-ttu-id="32067-115">**サービス名。**</span><span class="sxs-lookup"><span data-stu-id="32067-115">**ServiceName.**</span></span> <span data-ttu-id="32067-116">これはサービスの名前 ESB 行程に格納されている、任意の名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="32067-116">This is the name of the service, as stored in the ESB itinerary, and can be any name.</span></span> <span data-ttu-id="32067-117">旅行計画では、この名前を使ってを実行するサービスを識別します。</span><span class="sxs-lookup"><span data-stu-id="32067-117">The itinerary uses this name to identify which service to execute.</span></span>  
  
-   <span data-ttu-id="32067-118">**ServiceState です。**</span><span class="sxs-lookup"><span data-stu-id="32067-118">**ServiceState.**</span></span> <span data-ttu-id="32067-119">これは、実行する現在の itinerary サービス ステップの状態です。</span><span class="sxs-lookup"><span data-stu-id="32067-119">This is the state of the current itinerary service step to execute.</span></span> <span data-ttu-id="32067-120">サービスの現在の手順 (次の処理) が、値が常に**保留**、いずれか、ESB itinerary パイプライン コンポーネント、ESB 行程セレクター パイプライン コンポーネントによって設定するかを呼び出すコード、**先行**行程 API のメソッドです。</span><span class="sxs-lookup"><span data-stu-id="32067-120">The current service step (for processing next) will always have the value **Pending**, set by either the ESB itinerary pipeline component, the ESB Itinerary Selector pipeline component, or code that calls the **Advance** method of the itinerary API.</span></span>  
  
-   <span data-ttu-id="32067-121">**ServiceType です。**</span><span class="sxs-lookup"><span data-stu-id="32067-121">**ServiceType.**</span></span> <span data-ttu-id="32067-122">このプロパティは、オーケストレーションまたは BizTalk のメッセージング サブシステムから発生するかどうかを示す、サービスの種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="32067-122">This property defines the type of service, indicating whether it originates from the orchestration or the messaging subsystem in BizTalk.</span></span>  
  
-   <span data-ttu-id="32067-123">**IsRequestResponse です。**</span><span class="sxs-lookup"><span data-stu-id="32067-123">**IsRequestResponse.**</span></span> <span data-ttu-id="32067-124">このオプションのプロパティと同じ値を持つ必要があります、 **IsRequestResponse**サービスのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="32067-124">This optional property must have the same value as the **IsRequestResponse** property of the service.</span></span>