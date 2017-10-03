---
title: "Continuation ノードと ContinuationID ノード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8aa8956721d4a44b51b8d2c7776560aaa878f864
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="continuation-and-continuationid-nodes"></a><span data-ttu-id="e33f6-102">Continuation ノードと ContinuationID ノード</span><span class="sxs-lookup"><span data-stu-id="e33f6-102">Continuation and ContinuationID Nodes</span></span>
<span data-ttu-id="e33f6-103">Continuation は、次の情報に関するガイダンスを BAM インフラストラクチャに提供します。</span><span class="sxs-lookup"><span data-stu-id="e33f6-103">Continuations provide guidance to the BAM infrastructure about the following information:</span></span>  
  
-   <span data-ttu-id="e33f6-104">イベントの発生順序</span><span class="sxs-lookup"><span data-stu-id="e33f6-104">The order in which events are expected to occur</span></span>  
  
-   <span data-ttu-id="e33f6-105">イベント項目が関連付けられている一意 ID が変更された場合の処理方法</span><span class="sxs-lookup"><span data-stu-id="e33f6-105">A way to handle any change in the unique ID to which event items are correlated</span></span>  
  
 <span data-ttu-id="e33f6-106">つまり、関係者間の情報をアクティビティに転送する方法を定義するのが Continuation です。</span><span class="sxs-lookup"><span data-stu-id="e33f6-106">To state this another way, continuations define the transfer of this information between contributors to an activity.</span></span> <span data-ttu-id="e33f6-107">次の状況で転送が行われます。</span><span class="sxs-lookup"><span data-stu-id="e33f6-107">A transfer occurs in the following situations:</span></span>  
  
-   <span data-ttu-id="e33f6-108">アクティビティの開始から終了までに ActivityID が変わった場合。</span><span class="sxs-lookup"><span data-stu-id="e33f6-108">There is a change in the ActivityID between the time an activity begins and ends.</span></span> <span data-ttu-id="e33f6-109">たとえば、注文書番号と販売注文番号など、2 つの関連するメッセージがあるとします。</span><span class="sxs-lookup"><span data-stu-id="e33f6-109">For example, you have two related messages such as a Purchase Order number and Sales Order number.</span></span> <span data-ttu-id="e33f6-110">それぞれのメッセージには、注文書番号 123456、販売注文番号 987654 などの一意の数字が割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="e33f6-110">Each has a unique number assigned to it, such as 123456 for the Purchase Order number and 987654 for Sales Order number.</span></span> <span data-ttu-id="e33f6-111">Continuation を使用すると、注文書と販売注文の一意の ID を同等と見なすことができるので、受信したイベントがどちらの ID に関連付けられているかにかかわらず、イベントを共通のアクティビティに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="e33f6-111">You would use a continuation to equate the unique identifiers for the Purchase Order and the Sales Order so that events can be correlated to the common activity regardless of which unique identifier is associated with the incoming events.</span></span>  
  
-   <span data-ttu-id="e33f6-112">実行環境の移行が生じる場合。</span><span class="sxs-lookup"><span data-stu-id="e33f6-112">You have a transition from one run-time environment to another.</span></span> <span data-ttu-id="e33f6-113">たとえばを BizTalk Server メッセージング パイプライン、オーケストレーションとオーケストレーションを起動し、出荷通知を送信するアプリケーションに制御を渡しますに発注書を提供するアプリケーションが存在するシナリオでがある 2 つ環境の遷移: メッセージング パイプラインから、オーケストレーションとメッセージング パイプラインをオーケストレーションからです。</span><span class="sxs-lookup"><span data-stu-id="e33f6-113">For example, in a scenario where you have an application that supplies a purchase order to a BizTalk Server messaging pipeline, which then invokes an orchestration, and the orchestration then passes control to an application that sends a shipping notice, you have two environment transitions: from a messaging pipeline to a an orchestration and from an orchestration to a messaging pipeline.</span></span>  
  
 <span data-ttu-id="e33f6-114">Continuation に使用するプロパティを選択するときに重要なことは、プロパティが同じコンテキストからマップされていなければならないということです。</span><span class="sxs-lookup"><span data-stu-id="e33f6-114">An important point to remember when selecting a property to use for your continuation is that the properties must be mapped from the same context.</span></span>  
  
 <span data-ttu-id="e33f6-115">たとえば、プロパティ Message.InterchangeID と servicecontext.InterchangeID がある場合、InterchangeID を使用して Continuation を作成できるように見えます。</span><span class="sxs-lookup"><span data-stu-id="e33f6-115">For example, if you have the propertiesy Message.InterchangeID and servicecontext.InterchangeID it might appear that you could use the InterchangeID to create your continuation.</span></span> <span data-ttu-id="e33f6-116">しかし、メッセージの元になっているコンテキストが異なる場合は、InterchangeID (または他のプロパティ) を使用して Continuation を確実に作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="e33f6-116">If the messages come from different contexts you cannot use the InterchangeID (or other property) to reliably create a continuation.</span></span>  
  
## <a name="working-with-continuation-nodes"></a><span data-ttu-id="e33f6-117">Continuation ノードの操作</span><span class="sxs-lookup"><span data-stu-id="e33f6-117">Working with Continuation nodes</span></span>  
 <span data-ttu-id="e33f6-118">Continuation ノードにはとも呼ばれる、一意のインスタンス ID を示すデータ項目が含まれています、*継続トークン*です。</span><span class="sxs-lookup"><span data-stu-id="e33f6-118">The Continuation node contains data items that indicate a unique instance ID, also called a *continuation token*.</span></span> <span data-ttu-id="e33f6-119">継続トークンを使用することで、ContinuationID ノードを使用する他のアクティビティにリンクできます。</span><span class="sxs-lookup"><span data-stu-id="e33f6-119">By using the continuation token, developers can link to other activities using the ContinuationID node.</span></span>  
  
 <span data-ttu-id="e33f6-120">Continuation ノードと ContinuationID ノードを使用する基本的なシナリオは、次の 3 つです。</span><span class="sxs-lookup"><span data-stu-id="e33f6-120">There are three basic scenarios in which Continuation and ContinuationID nodes are used:</span></span>  
  
-   <span data-ttu-id="e33f6-121">オーケストレーションからオーケストレーションへ</span><span class="sxs-lookup"><span data-stu-id="e33f6-121">Orchestration to orchestration</span></span>  
  
-   <span data-ttu-id="e33f6-122">オーケストレーションから BizTalk ソリューションへ</span><span class="sxs-lookup"><span data-stu-id="e33f6-122">Orchestration to BizTalk solution</span></span>  
  
-   <span data-ttu-id="e33f6-123">BizTalk ソリューションからオーケストレーションへ</span><span class="sxs-lookup"><span data-stu-id="e33f6-123">BizTalk solution to orchestration</span></span>  
  
 <span data-ttu-id="e33f6-124">オーケストレーション間のシナリオでは、まず TPE で Continuation ノードと ContinuationID ノードを定義する必要があります。次に、BAM でアクティビティの関連付けを行うために、2 つのノードに同じ名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="e33f6-124">In the orchestration scenario the TPE must define a Continuation node, and a ContinuationID node, and the nodes must have the same name in order for BAM to correlate the activities.</span></span>  
  
 <span data-ttu-id="e33f6-125">オーケストレーションから BizTalk ソリューションへのシナリオでは、TEP を使用して Continuation ノードを定義し、Continuation の継続先部分を処理する、BAM API を使用したソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="e33f6-125">In the orchestration to BizTalk solution scenario, you use the TPE to define a Continuation node and the developer creates a solution that uses the BAM API to handle the destination portion of the continuation..</span></span>  
  
 <span data-ttu-id="e33f6-126">BizTalk ソリューションからオーケストレーションへのシナリオでは、BAM API で Continuation ペアの起点を指定し、TPE で ContinuationID ノードを定義します。</span><span class="sxs-lookup"><span data-stu-id="e33f6-126">In the BizTalk solution to orchestration, the developer uses the BAM API to supply the origination of the continuation pair and you use TPE to define a ContinuationID node.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e33f6-127">双方向のポートは、どちらの方向でも機能します。つまり、BizTalk ソリューションの動作によっては、そのポートを通過するデータを受信するために、Continuation を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e33f6-127">Two-way ports can operate in either direction, which means that interception of data that passes through the ports can, depending on the behavior of the BizTalk solution, require enabling of a continuation.</span></span> <span data-ttu-id="e33f6-128">たとえば、項目名を "MessageReceived" および "MessageSent" (順序はこのとおり) とした場合に、BizTalk Server メッセージング ポートをいずれかの方向で有効にしたときにアクティビティが "PortEndTime" を記録する場合、2 つの項目間に Continuation を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e33f6-128">For example, if the activity records “PortEndTime” for activation of a BizTalk Server messaging port in either direction (if the item names are, for example, “MessageReceived” and “MessageSent,” in that order), you need to create a continuation between them.</span></span> <span data-ttu-id="e33f6-129">複数のイベント ストリームが BAM アクティビティに関与していて、実装の接点 (BTS メッセージング受信、BTS メッセージング送信、オーケストレーション、カスタム アプリケーション、Web サービスなど) ごとに個別のイベント ストリームが存在する場合、常に Continuation が必要です。</span><span class="sxs-lookup"><span data-stu-id="e33f6-129">A continuation is required any time more than one event stream contributes to a BAM activity, and there are distinct event streams per implementation touch point (such as BTS Messaging in, BTS Messaging out, Orchestration, custom applications, and Web services).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e33f6-130">参照</span><span class="sxs-lookup"><span data-stu-id="e33f6-130">See Also</span></span>  
 <span data-ttu-id="e33f6-131">[Continuation を作成する方法](../core/how-to-create-a-continuation.md) </span><span class="sxs-lookup"><span data-stu-id="e33f6-131">[How to Create a Continuation](../core/how-to-create-a-continuation.md) </span></span>  
 [<span data-ttu-id="e33f6-132">TPE アクティビティ ビューのノード</span><span class="sxs-lookup"><span data-stu-id="e33f6-132">TPE Activity View Nodes</span></span>](../core/tpe-activity-view-nodes.md)