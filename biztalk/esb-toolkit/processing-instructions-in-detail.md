---
title: "処理命令の詳細 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ed5d92fb-d53b-49a2-b2c7-8558708d6554
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 532721c347189f2e3d4db9e57b2afc3aa45b76db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="processing-instructions-in-detail"></a><span data-ttu-id="29276-102">処理命令の詳細</span><span class="sxs-lookup"><span data-stu-id="29276-102">Processing Instructions in Detail</span></span>
<span data-ttu-id="29276-103">このトピックでは、形式と旅程処理に必要ないくつかのコンテキスト プロパティを定義するシステム Properties.xsd プロパティ スキーマの構造について説明します。</span><span class="sxs-lookup"><span data-stu-id="29276-103">This topic describes the format and structure of the System-Properties.xsd property schema, which defines several context properties required for itinerary processing.</span></span> <span data-ttu-id="29276-104">メッセージが受信され、を通して処理されたときに、これらのプロパティが昇格させた[!INCLUDE[prague](../includes/prague-md.md)]; パイプラインが BizTalk Server コンポーネントにアクセスできるため、昇格させたプロパティは、します。</span><span class="sxs-lookup"><span data-stu-id="29276-104">These properties are promoted when a message is received and processed through [!INCLUDE[prague](../includes/prague-md.md)] pipelines; because they are promoted properties, they are accessible to BizTalk Server components.</span></span> <span data-ttu-id="29276-105">次のプロパティは、システム Properties.xsd プロパティ スキーマで定義されます。</span><span class="sxs-lookup"><span data-stu-id="29276-105">The following properties are defined in the System-Properties.xsd property schema:</span></span>  
  
-   <span data-ttu-id="29276-106">**ItineraryHeader です。**</span><span class="sxs-lookup"><span data-stu-id="29276-106">**ItineraryHeader.**</span></span> <span data-ttu-id="29276-107">このプロパティには、すべての itinerary 情報および itinerary ステップの順序で呼び出される itinerary サービスの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="29276-107">This property contains all the itinerary information and a list of itinerary services to be invoked through a sequence of itinerary steps.</span></span> <span data-ttu-id="29276-108">行程 API は、このプロパティを内部的に使用します。</span><span class="sxs-lookup"><span data-stu-id="29276-108">The Itinerary API uses this property internally.</span></span>  
  
-   <span data-ttu-id="29276-109">**サービス名。**</span><span class="sxs-lookup"><span data-stu-id="29276-109">**ServiceName.**</span></span> <span data-ttu-id="29276-110">このプロパティには、処理する場合は、現在 itinerary サービスの名前が含まれています。</span><span class="sxs-lookup"><span data-stu-id="29276-110">This property contains the name of the current itinerary service to process.</span></span>  
  
-   <span data-ttu-id="29276-111">**ServiceState です。**</span><span class="sxs-lookup"><span data-stu-id="29276-111">**ServiceState.**</span></span> <span data-ttu-id="29276-112">このプロパティには、現在の itinerary サービスの状態が含まれています:**保留**、**完了**、または**Active**です。</span><span class="sxs-lookup"><span data-stu-id="29276-112">This property contains the state of the current itinerary service: **Pending**, **Complete**, or **Active**.</span></span> <span data-ttu-id="29276-113">すべてのサービスのサブスクライブを含む itinerary ステップに、 **ServiceState**の値**保留**です。</span><span class="sxs-lookup"><span data-stu-id="29276-113">All services subscribe to an itinerary step that contains a **ServiceState** value of **Pending**.</span></span>  
  
-   <span data-ttu-id="29276-114">**ServiceType です。**</span><span class="sxs-lookup"><span data-stu-id="29276-114">**ServiceType.**</span></span> <span data-ttu-id="29276-115">このプロパティは itinerary ステップの種類を定義 (**メッセージング**または**オーケストレーション**)。</span><span class="sxs-lookup"><span data-stu-id="29276-115">This property defines the type of the itinerary step (**Messaging** or **Orchestration**).</span></span>  
  
-   <span data-ttu-id="29276-116">**IsRequestResponse です。**</span><span class="sxs-lookup"><span data-stu-id="29276-116">**IsRequestResponse.**</span></span> <span data-ttu-id="29276-117">このプロパティをメッセージ型を定義します (一方向または要求-応答)。</span><span class="sxs-lookup"><span data-stu-id="29276-117">This property defines the messaging type (one-way or request-response).</span></span>  
  
 <span data-ttu-id="29276-118">行程サービスの値に応じて、2 つの方法のいずれかで itinerary 手順を実行する、 **ServiceType**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="29276-118">The Itinerary service executes itinerary steps in one of two ways, depending on the value of the **ServiceType** property:</span></span>  
  
-   <span data-ttu-id="29276-119">Itinerary パイプライン コンポーネントでのすべての itinerary 手順を実行する、 **ServiceType**プロパティ**メッセージング**です。</span><span class="sxs-lookup"><span data-stu-id="29276-119">Itinerary pipeline components execute all itinerary steps with a **ServiceType** property of **Messaging**.</span></span> <span data-ttu-id="29276-120">開発者は、カスタム パイプラインと旅程 API を使用してこのプロセスを拡張することができます。</span><span class="sxs-lookup"><span data-stu-id="29276-120">Developers can extend this process using a custom pipeline and the Itinerary API.</span></span>  
  
-   <span data-ttu-id="29276-121">ときに、 **ServiceType**プロパティは**オーケストレーション**、itinerary コンテキスト プロパティへのサブスクリプションによってアクティブ化、オーケストレーションは itinerary のステップを実行します。</span><span class="sxs-lookup"><span data-stu-id="29276-121">When the **ServiceType** property is **Orchestration**, an orchestration, activated by a subscription to itinerary context properties, executes the itinerary step.</span></span>  
  
 <span data-ttu-id="29276-122">行程サービス itinerary 手順を処理するとき、サービスは、旅行計画を進めると、さらに処理する、発行を使用して新しい itinerary コンテキストを持つメッセージをディスパッチ-BizTalk Server の機能をサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="29276-122">When an Itinerary service processes an itinerary step, the service is responsible for advancing the itinerary and dispatching the message with a new itinerary context for further processing using the publish-subscribe functionality of BizTalk Server.</span></span> <span data-ttu-id="29276-123">Itinerary サービスは、メッセージ コンテキストの日程のフル コントロールを持ち、その内部ロジックと、メッセージの内容に基づいて、適切な手順を進めることができます。</span><span class="sxs-lookup"><span data-stu-id="29276-123">An itinerary service has full control of the itinerary in the message context and can advance to the appropriate step based on its internal logic and the message content.</span></span>  
  
 <span data-ttu-id="29276-124">Itinerary 処理メカニズムでは、1 つの日程内のメッセージングおよびオーケストレーションの itinerary 手順の組み合わせをサポートします。</span><span class="sxs-lookup"><span data-stu-id="29276-124">The itinerary processing mechanism supports the combination of messaging and orchestration itinerary steps within a single itinerary.</span></span> <span data-ttu-id="29276-125">開発者は、itinerary のカスタムのサービスを定義し、カスタムの itinerary ステップを構成することができますも。</span><span class="sxs-lookup"><span data-stu-id="29276-125">Developers can also define custom itinerary services and configure custom itinerary steps.</span></span>  
  
 <span data-ttu-id="29276-126">行程の詳細については、次を参照してください。[のインストールと旅程ランプでサンプルを実行して](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="29276-126">For more information about itineraries, see [Installing and Running the Itinerary On-Ramp Sample](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).</span></span>  
  
 <span data-ttu-id="29276-127">カスタムの itinerary サービスとカスタムの itinerary 手順の詳細については、次を参照してください。[カスタム行程サービスを作成する](../esb-toolkit/creating-a-custom-itinerary-service.md)です。</span><span class="sxs-lookup"><span data-stu-id="29276-127">For more information about custom itinerary services and custom itinerary steps, see [Creating a Custom Itinerary Service](../esb-toolkit/creating-a-custom-itinerary-service.md).</span></span>