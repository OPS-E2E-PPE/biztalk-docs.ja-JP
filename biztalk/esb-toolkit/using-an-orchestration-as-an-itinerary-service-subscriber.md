---
title: スケジュール サービス サブスクライバーとしてオーケストレーションを使用して |Microsoft Docs
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
ms.openlocfilehash: 707c9b37f671191b743912cb391c8e41d67d007b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396465"
---
# <a name="using-an-orchestration-as-an-itinerary-service-subscriber"></a><span data-ttu-id="1a41c-102">スケジュール サービス サブスクライバーとしてオーケストレーションを使用します。</span><span class="sxs-lookup"><span data-stu-id="1a41c-102">Using an Orchestration as an Itinerary Service Subscriber</span></span>
<span data-ttu-id="1a41c-103">オーケストレーション スケジュール サービスとしても機能します。</span><span class="sxs-lookup"><span data-stu-id="1a41c-103">Orchestrations can also act as itinerary services.</span></span> <span data-ttu-id="1a41c-104">スケジュールに参加するに直接バインドされた; としてオーケストレーションを最初にデザインする必要があります。これを行うと類似の前のトピックでは、送信ポート フィルター サブスクリプションを使用して、[送信ポートを使用して、スケジュール サービス サブスクライバーとして](../esb-toolkit/using-a-send-port-as-an-itinerary-service-subscriber.md)します。</span><span class="sxs-lookup"><span data-stu-id="1a41c-104">To participate in an itinerary, you must first design the orchestration as direct-bound; to do this, use a filter subscription similar to that of the send port in the previous topic, [Using a Send Port as an Itinerary Service Subscriber](../esb-toolkit/using-a-send-port-as-an-itinerary-service-subscriber.md).</span></span> <span data-ttu-id="1a41c-105">図 1 は、次の条件を満たすすべてのメッセージを取得する適切なオーケストレーションのフィルター式の例を示します。</span><span class="sxs-lookup"><span data-stu-id="1a41c-105">Figure 1 shows an example of a filter expression for a suitable orchestration to pick up any message that meets the following conditions:</span></span>  

- <span data-ttu-id="1a41c-106">**ServiceName = Microsoft.Practices.ESB.Services.Transform**</span><span class="sxs-lookup"><span data-stu-id="1a41c-106">**ServiceName = Microsoft.Practices.ESB.Services.Transform**</span></span>  

- <span data-ttu-id="1a41c-107">**ServiceState = 保留中**</span><span class="sxs-lookup"><span data-stu-id="1a41c-107">**ServiceState = Pending**</span></span>  

- <span data-ttu-id="1a41c-108">**ServiceType オーケストレーションを =**</span><span class="sxs-lookup"><span data-stu-id="1a41c-108">**ServiceType = Orchestration**</span></span>  

  <span data-ttu-id="1a41c-109">![オーケストレーション](../esb-toolkit/media/ch4-orchestration.jpg "Ch4 オーケストレーション")</span><span class="sxs-lookup"><span data-stu-id="1a41c-109">![Orchestration](../esb-toolkit/media/ch4-orchestration.jpg "Ch4-Orchestration")</span></span>  

  <span data-ttu-id="1a41c-110">**図 1**</span><span class="sxs-lookup"><span data-stu-id="1a41c-110">**Figure 1**</span></span>  

  <span data-ttu-id="1a41c-111">**サブスクライバーとして、スケジュールに参加するオーケストレーションのフィルター式の例**</span><span class="sxs-lookup"><span data-stu-id="1a41c-111">**Example filter expression for an orchestration that will participate in an itinerary as a subscriber**</span></span>  

  <span data-ttu-id="1a41c-112">Microsoft BizTalk Server で ESB 入り口を介してメッセージを受信と、ESB パイプラインの検証手順には、受信メッセージの BizTalk コンテキスト プロパティにフィルターのプロパティのプロパティ値を書き込みますこれは、メッセージ コンテキストにそれらを昇格します。</span><span class="sxs-lookup"><span data-stu-id="1a41c-112">When messages arrive in Microsoft BizTalk Server through an ESB on-ramp, the validation step in the ESB pipeline writes the property values for the filter properties into the BizTalk context properties of the incoming message; this promotes them to the message context.</span></span> <span data-ttu-id="1a41c-113">スケジュール サービスが常に設定、 **ServiceName**プロパティを次に、処理するサービスの名前に、現在アクティブなサービスを**ServiceState**プロパティ値の**保留中**します。</span><span class="sxs-lookup"><span data-stu-id="1a41c-113">The itinerary service always sets the **ServiceName** property for the currently active service to the name of the service to process next, and with a **ServiceState** property value of **Pending**.</span></span> <span data-ttu-id="1a41c-114">サブスクリプションを設定する必要が少なくとも最初の 3 つの次のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="1a41c-114">For a subscription, you must set at least the first three of the following properties:</span></span>  

- <span data-ttu-id="1a41c-115">**サービス名。**</span><span class="sxs-lookup"><span data-stu-id="1a41c-115">**ServiceName.**</span></span> <span data-ttu-id="1a41c-116">これにより、ESB 行程に格納されている、サービスの名前は、および任意の名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="1a41c-116">This is the name of the service, as stored in the ESB itinerary, and can be any name.</span></span> <span data-ttu-id="1a41c-117">旅行プランを実行するのにには、どのサービスを識別するためにこの名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="1a41c-117">The itinerary uses this name to identify which service to execute.</span></span>  

- <span data-ttu-id="1a41c-118">**ServiceState します。**</span><span class="sxs-lookup"><span data-stu-id="1a41c-118">**ServiceState.**</span></span> <span data-ttu-id="1a41c-119">これは、実行する現在のスケジュール サービス ステップの状態です。</span><span class="sxs-lookup"><span data-stu-id="1a41c-119">This is the state of the current itinerary service step to execute.</span></span> <span data-ttu-id="1a41c-120">(次の処理) の現在のサービス ステップには、値は常に**保留**か ESB スケジュール オンランプ パイプライン コンポーネントによって、ESB スケジュール セレクター パイプライン コンポーネントで、設定、またはを呼び出すコード、**事前**行程 API のメソッド。</span><span class="sxs-lookup"><span data-stu-id="1a41c-120">The current service step (for processing next) will always have the value **Pending**, set by either the ESB itinerary pipeline component, the ESB Itinerary Selector pipeline component, or code that calls the **Advance** method of the itinerary API.</span></span>  

- <span data-ttu-id="1a41c-121">**ServiceType します。**</span><span class="sxs-lookup"><span data-stu-id="1a41c-121">**ServiceType.**</span></span> <span data-ttu-id="1a41c-122">このプロパティは、オーケストレーションまたは BizTalk のメッセージング サブシステムから発生するかどうかを示す、サービスの種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="1a41c-122">This property defines the type of service, indicating whether it originates from the orchestration or the messaging subsystem in BizTalk.</span></span>  

- <span data-ttu-id="1a41c-123">**IsRequestResponse します。**</span><span class="sxs-lookup"><span data-stu-id="1a41c-123">**IsRequestResponse.**</span></span> <span data-ttu-id="1a41c-124">この省略可能なプロパティと同じ値が必要、 **IsRequestResponse**サービスのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="1a41c-124">This optional property must have the same value as the **IsRequestResponse** property of the service.</span></span>
