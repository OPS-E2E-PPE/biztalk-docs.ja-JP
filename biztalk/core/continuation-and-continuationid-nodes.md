---
title: Continuation ノードと ContinuationID ノード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- continuation tokens
- Continuation nodes [Tracking Profile Editor]
- Tracking Profile Editor, node descriptions
- BAM, correlating activities
- activities, linking
- activities, continuation tokens
- ContinuationID nodes [Tracking Profile Editor]
ms.assetid: aa050660-66f7-4084-b6bf-b9319ce625af
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e0cd305241b04bbbb7a09a8cf716820978594e7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354592"
---
# <a name="continuation-and-continuationid-nodes"></a><span data-ttu-id="ad508-102">Continuation ノードと ContinuationID ノード</span><span class="sxs-lookup"><span data-stu-id="ad508-102">Continuation and ContinuationID Nodes</span></span>
<span data-ttu-id="ad508-103">Continuation は、次の情報に関するガイダンスを BAM インフラストラクチャに提供します。</span><span class="sxs-lookup"><span data-stu-id="ad508-103">Continuations provide guidance to the BAM infrastructure about the following information:</span></span>  
  
- <span data-ttu-id="ad508-104">イベントの発生順序</span><span class="sxs-lookup"><span data-stu-id="ad508-104">The order in which events are expected to occur</span></span>  
  
- <span data-ttu-id="ad508-105">イベント項目が関連付けられている一意 ID が変更された場合の処理方法</span><span class="sxs-lookup"><span data-stu-id="ad508-105">A way to handle any change in the unique ID to which event items are correlated</span></span>  
  
  <span data-ttu-id="ad508-106">別の方法ではこの状態では、継続は、アクティビティに関係者間のこの情報の転送を定義します。</span><span class="sxs-lookup"><span data-stu-id="ad508-106">To state this another way, continuations define the transfer of this information between contributors to an activity.</span></span> <span data-ttu-id="ad508-107">転送は、次の状況で発生します。</span><span class="sxs-lookup"><span data-stu-id="ad508-107">A transfer occurs in the following situations:</span></span>  
  
- <span data-ttu-id="ad508-108">アクティビティの開始時刻と終了の間の ActivityID に変更があります。</span><span class="sxs-lookup"><span data-stu-id="ad508-108">There is a change in the ActivityID between the time an activity begins and ends.</span></span> <span data-ttu-id="ad508-109">たとえば、発注番号、販売注文番号などの 2 つの関連するメッセージがあるとします。</span><span class="sxs-lookup"><span data-stu-id="ad508-109">For example, you have two related messages such as a Purchase Order number and Sales Order number.</span></span> <span data-ttu-id="ad508-110">それぞれが、注文書番号 123456、販売注文番号 987654 などに、それに割り当てられた一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="ad508-110">Each has a unique number assigned to it, such as 123456 for the Purchase Order number and 987654 for Sales Order number.</span></span> <span data-ttu-id="ad508-111">Continuation を使用して、注文書の一意の識別子を時と見なされ、Sales Order ようにする一意識別子に関係なく、一般的なアクティビティにイベントを関連付けることができますが、受信イベントに関連付け。</span><span class="sxs-lookup"><span data-stu-id="ad508-111">You would use a continuation to equate the unique identifiers for the Purchase Order and the Sales Order so that events can be correlated to the common activity regardless of which unique identifier is associated with the incoming events.</span></span>  
  
- <span data-ttu-id="ad508-112">1 つの実行時環境から別の遷移があります。</span><span class="sxs-lookup"><span data-stu-id="ad508-112">You have a transition from one run-time environment to another.</span></span> <span data-ttu-id="ad508-113">たとえば、オーケストレーションとオーケストレーションを起動し、出荷通知を送信するアプリケーションに制御を渡しますし、BizTalk Server メッセージング パイプラインに注文書を提供するアプリケーションがあるシナリオで必要がある 2 つ環境の遷移: メッセージング パイプラインから、オーケストレーションとメッセージング パイプラインをオーケストレーションから。</span><span class="sxs-lookup"><span data-stu-id="ad508-113">For example, in a scenario where you have an application that supplies a purchase order to a BizTalk Server messaging pipeline, which then invokes an orchestration, and the orchestration then passes control to an application that sends a shipping notice, you have two environment transitions: from a messaging pipeline to a an orchestration and from an orchestration to a messaging pipeline.</span></span>  
  
  <span data-ttu-id="ad508-114">Continuation を使用するプロパティを選択する際に重要な点は、同じコンテキストからプロパティをマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad508-114">An important point to remember when selecting a property to use for your continuation is that the properties must be mapped from the same context.</span></span>  
  
  <span data-ttu-id="ad508-115">たとえば、次のように、プロパティ Message.InterchangeID と servicecontext がある場合です。InterchangeID、InterchangeID を使用して continuation を作成することでしたが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ad508-115">For example, if you have the propertiesy Message.InterchangeID and servicecontext.InterchangeID it might appear that you could use the InterchangeID to create your continuation.</span></span> <span data-ttu-id="ad508-116">メッセージが別のコンテキストから取得する場合は、continuation を確実に作成する、InterchangeID (またはその他のプロパティ) を使用できません。</span><span class="sxs-lookup"><span data-stu-id="ad508-116">If the messages come from different contexts you cannot use the InterchangeID (or other property) to reliably create a continuation.</span></span>  
  
## <a name="working-with-continuation-nodes"></a><span data-ttu-id="ad508-117">Continuation ノードの操作</span><span class="sxs-lookup"><span data-stu-id="ad508-117">Working with Continuation nodes</span></span>  
 <span data-ttu-id="ad508-118">Continuation ノードにはとも呼ばれる、一意のインスタンス ID を示すデータ項目が含まれています、*継続トークン*します。</span><span class="sxs-lookup"><span data-stu-id="ad508-118">The Continuation node contains data items that indicate a unique instance ID, also called a *continuation token*.</span></span> <span data-ttu-id="ad508-119">継続トークンを使用すると、開発者は、ContinuationID ノードを使用して他のアクティビティにリンクできます。</span><span class="sxs-lookup"><span data-stu-id="ad508-119">By using the continuation token, developers can link to other activities using the ContinuationID node.</span></span>  
  
 <span data-ttu-id="ad508-120">Continuation と ContinuationID ノードを使用する 3 つの基本的なシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="ad508-120">There are three basic scenarios in which Continuation and ContinuationID nodes are used:</span></span>  
  
- <span data-ttu-id="ad508-121">オーケストレーションからオーケストレーションへ</span><span class="sxs-lookup"><span data-stu-id="ad508-121">Orchestration to orchestration</span></span>  
  
- <span data-ttu-id="ad508-122">BizTalk ソリューションにオーケストレーション</span><span class="sxs-lookup"><span data-stu-id="ad508-122">Orchestration to BizTalk solution</span></span>  
  
- <span data-ttu-id="ad508-123">BizTalk ソリューションからオーケストレーションへ</span><span class="sxs-lookup"><span data-stu-id="ad508-123">BizTalk solution to orchestration</span></span>  
  
  <span data-ttu-id="ad508-124">シナリオ、TPE のオーケストレーションで Continuation ノードと ContinuationID ノードを定義する必要があり、bam アクティビティを関連付けるために、ノードが同じ名前を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad508-124">In the orchestration scenario the TPE must define a Continuation node, and a ContinuationID node, and the nodes must have the same name in order for BAM to correlate the activities.</span></span>  
  
  <span data-ttu-id="ad508-125">BizTalk ソリューションのシナリオにオーケストレーションでは、TPE を使用して Continuation ノードを定義して、開発者は、継続の継続先部分を処理するために、BAM API を使用するソリューションを作成します.</span><span class="sxs-lookup"><span data-stu-id="ad508-125">In the orchestration to BizTalk solution scenario, you use the TPE to define a Continuation node and the developer creates a solution that uses the BAM API to handle the destination portion of the continuation..</span></span>  
  
  <span data-ttu-id="ad508-126">オーケストレーションを BizTalk ソリューションで、開発者は、BAM API を使用して continuation ペアの発信元を指定して、TPE を使用して、ContinuationID ノードを定義します。</span><span class="sxs-lookup"><span data-stu-id="ad508-126">In the BizTalk solution to orchestration, the developer uses the BAM API to supply the origination of the continuation pair and you use TPE to define a ContinuationID node.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ad508-127">双方向のポートは、ポートを通過するデータの傍受できます、によって BizTalk ソリューションの動作が必要に、continuation を有効にすることを意味するいずれかの方向で動作できます。</span><span class="sxs-lookup"><span data-stu-id="ad508-127">Two-way ports can operate in either direction, which means that interception of data that passes through the ports can, depending on the behavior of the BizTalk solution, require enabling of a continuation.</span></span> <span data-ttu-id="ad508-128">たとえば、アクティビティ レコードの"PortEndTime"を BizTalk Server がメッセージング (項目名は、たとえば、"MessageReceived"および"MessageSent"をこの順序で) 場合、どちらの方向のポートの数が場合は、間に continuation を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad508-128">For example, if the activity records “PortEndTime” for activation of a BizTalk Server messaging port in either direction (if the item names are, for example, “MessageReceived” and “MessageSent,” in that order), you need to create a continuation between them.</span></span> <span data-ttu-id="ad508-129">Continuation が必要です、いつ以上の 1 つのイベント ストリームは、BAM アクティビティに貢献し、実装の接点 (BTS メッセージング、BTS メッセージング送信、オーケストレーション、カスタム アプリケーション、および Web サービスなど) ごとに個別のイベント ストリームがあります。</span><span class="sxs-lookup"><span data-stu-id="ad508-129">A continuation is required any time more than one event stream contributes to a BAM activity, and there are distinct event streams per implementation touch point (such as BTS Messaging in, BTS Messaging out, Orchestration, custom applications, and Web services).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad508-130">参照</span><span class="sxs-lookup"><span data-stu-id="ad508-130">See Also</span></span>  
 <span data-ttu-id="ad508-131">[Continuation を作成する方法](../core/how-to-create-a-continuation.md) </span><span class="sxs-lookup"><span data-stu-id="ad508-131">[How to Create a Continuation](../core/how-to-create-a-continuation.md) </span></span>  
 [<span data-ttu-id="ad508-132">TPE アクティビティ ビューのノード</span><span class="sxs-lookup"><span data-stu-id="ad508-132">TPE Activity View Nodes</span></span>](../core/tpe-activity-view-nodes.md)