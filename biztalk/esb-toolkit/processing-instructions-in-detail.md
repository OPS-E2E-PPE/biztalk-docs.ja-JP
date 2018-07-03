---
title: 処理命令の詳細 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed5d92fb-d53b-49a2-b2c7-8558708d6554
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d867737599369ad8ff07780080b16f5ce0f6f2fe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005579"
---
# <a name="processing-instructions-in-detail"></a><span data-ttu-id="53105-102">処理命令の詳細</span><span class="sxs-lookup"><span data-stu-id="53105-102">Processing Instructions in Detail</span></span>
<span data-ttu-id="53105-103">このトピックでは、形式およびスケジュールの処理に必要ないくつかのコンテキスト プロパティを定義するシステム Properties.xsd プロパティ スキーマの構造について説明します。</span><span class="sxs-lookup"><span data-stu-id="53105-103">This topic describes the format and structure of the System-Properties.xsd property schema, which defines several context properties required for itinerary processing.</span></span> <span data-ttu-id="53105-104">これらのプロパティは、メッセージが受信され、BizTalk Server パイプライン; を通して処理されたときに昇格されます。昇格させたプロパティはため、BizTalk Server コンポーネントからアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="53105-104">These properties are promoted when a message is received and processed through BizTalk Server pipelines; because they are promoted properties, they are accessible to BizTalk Server components.</span></span> <span data-ttu-id="53105-105">次のプロパティは、システム Properties.xsd プロパティ スキーマで定義されます。</span><span class="sxs-lookup"><span data-stu-id="53105-105">The following properties are defined in the System-Properties.xsd property schema:</span></span>  
  
- <span data-ttu-id="53105-106">**ItineraryHeader します。**</span><span class="sxs-lookup"><span data-stu-id="53105-106">**ItineraryHeader.**</span></span> <span data-ttu-id="53105-107">このプロパティには、すべてのスケジュール情報とスケジュール オンランプ手順のシーケンスで呼び出されるスケジュール サービスの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="53105-107">This property contains all the itinerary information and a list of itinerary services to be invoked through a sequence of itinerary steps.</span></span> <span data-ttu-id="53105-108">行程 API では、このプロパティを内部的に使用します。</span><span class="sxs-lookup"><span data-stu-id="53105-108">The Itinerary API uses this property internally.</span></span>  
  
- <span data-ttu-id="53105-109">**サービス名。**</span><span class="sxs-lookup"><span data-stu-id="53105-109">**ServiceName.**</span></span> <span data-ttu-id="53105-110">このプロパティには、処理する現在のスケジュール サービスの名前が含まれています。</span><span class="sxs-lookup"><span data-stu-id="53105-110">This property contains the name of the current itinerary service to process.</span></span>  
  
- <span data-ttu-id="53105-111">**ServiceState します。**</span><span class="sxs-lookup"><span data-stu-id="53105-111">**ServiceState.**</span></span> <span data-ttu-id="53105-112">このプロパティには、現在のスケジュール サービスの状態が含まれています:**保留**、**完了**、または**Active**します。</span><span class="sxs-lookup"><span data-stu-id="53105-112">This property contains the state of the current itinerary service: **Pending**, **Complete**, or **Active**.</span></span> <span data-ttu-id="53105-113">すべてのサービスのサブスクライブを含むスケジュール オンランプの手順に、 **ServiceState** @property**保留中**します。</span><span class="sxs-lookup"><span data-stu-id="53105-113">All services subscribe to an itinerary step that contains a **ServiceState** value of **Pending**.</span></span>  
  
- <span data-ttu-id="53105-114">**ServiceType します。**</span><span class="sxs-lookup"><span data-stu-id="53105-114">**ServiceType.**</span></span> <span data-ttu-id="53105-115">このプロパティは、スケジュールのステップの種類を定義します (**メッセージング**または**オーケストレーション**)。</span><span class="sxs-lookup"><span data-stu-id="53105-115">This property defines the type of the itinerary step (**Messaging** or **Orchestration**).</span></span>  
  
- <span data-ttu-id="53105-116">**IsRequestResponse します。**</span><span class="sxs-lookup"><span data-stu-id="53105-116">**IsRequestResponse.**</span></span> <span data-ttu-id="53105-117">このプロパティは、メッセージ型を定義します (一方向または要求-応答)。</span><span class="sxs-lookup"><span data-stu-id="53105-117">This property defines the messaging type (one-way or request-response).</span></span>  
  
  <span data-ttu-id="53105-118">スケジュール サービスは、いずれかの値に応じて、2 つの方法でスケジュールの手順を実行、 **ServiceType**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="53105-118">The Itinerary service executes itinerary steps in one of two ways, depending on the value of the **ServiceType** property:</span></span>  
  
- <span data-ttu-id="53105-119">スケジュール オンランプ パイプライン コンポーネントでのすべてのスケジュール オンランプ手順を実行する、 **ServiceType**プロパティの**メッセージング**します。</span><span class="sxs-lookup"><span data-stu-id="53105-119">Itinerary pipeline components execute all itinerary steps with a **ServiceType** property of **Messaging**.</span></span> <span data-ttu-id="53105-120">開発者は、カスタム パイプラインと旅程 API を使用してこのプロセスを拡張できます。</span><span class="sxs-lookup"><span data-stu-id="53105-120">Developers can extend this process using a custom pipeline and the Itinerary API.</span></span>  
  
- <span data-ttu-id="53105-121">ときに、 **ServiceType**プロパティは**オーケストレーション**オーケストレーション、スケジュールのコンテキスト プロパティへのサブスクリプションがアクティブには、スケジュールの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="53105-121">When the **ServiceType** property is **Orchestration**, an orchestration, activated by a subscription to itinerary context properties, executes the itinerary step.</span></span>  
  
  <span data-ttu-id="53105-122">サービスが旅行計画を進めると、さらに処理する、発行を使用して新しいスケジュール オンランプ コンテキストを使用してメッセージをディスパッチする責任を負いますが、旅行プラン サービスは、スケジュールの手順を処理するときの BizTalk Server の機能をサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="53105-122">When an Itinerary service processes an itinerary step, the service is responsible for advancing the itinerary and dispatching the message with a new itinerary context for further processing using the publish-subscribe functionality of BizTalk Server.</span></span> <span data-ttu-id="53105-123">スケジュールのサービスは、メッセージ コンテキストでの旅程を完全に制御を備え、その内部ロジックと、メッセージの内容に基づいて適切な手順を進めることができます。</span><span class="sxs-lookup"><span data-stu-id="53105-123">An itinerary service has full control of the itinerary in the message context and can advance to the appropriate step based on its internal logic and the message content.</span></span>  
  
  <span data-ttu-id="53105-124">スケジュール オンランプ処理メカニズムは、1 つのスケジュール内のメッセージングおよびオーケストレーションの itinerary 手順の組み合わせをサポートします。</span><span class="sxs-lookup"><span data-stu-id="53105-124">The itinerary processing mechanism supports the combination of messaging and orchestration itinerary steps within a single itinerary.</span></span> <span data-ttu-id="53105-125">開発者はことができますも、カスタム スケジュール サービスを定義し、カスタム スケジュール ステップを構成します。</span><span class="sxs-lookup"><span data-stu-id="53105-125">Developers can also define custom itinerary services and configure custom itinerary steps.</span></span>  
  
  <span data-ttu-id="53105-126">スケジュールの詳細については、次を参照してください。[をインストールすると、日程ランプでサンプルを実行する](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="53105-126">For more information about itineraries, see [Installing and Running the Itinerary On-Ramp Sample](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).</span></span>  
  
  <span data-ttu-id="53105-127">カスタム スケジュール サービスとカスタム スケジュール オンランプ手順の詳細については、次を参照してください。[カスタム スケジュール サービスを作成する](../esb-toolkit/creating-a-custom-itinerary-service.md)します。</span><span class="sxs-lookup"><span data-stu-id="53105-127">For more information about custom itinerary services and custom itinerary steps, see [Creating a Custom Itinerary Service](../esb-toolkit/creating-a-custom-itinerary-service.md).</span></span>