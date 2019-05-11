---
title: 送信ポートと送信ポート グループ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, states
- send port groups
- send port groups, states
- send ports, about send ports
- send ports
- send port groups, about send port groups
- states, send ports
ms.assetid: 274bdd27-9098-46a2-8762-8b57bbfc95b8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc8adf80d30be84236d0c4252f67257cfe92cbbc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254523"
---
# <a name="send-ports-and-send-port-groups"></a><span data-ttu-id="7c66c-102">送信ポートと送信ポート グループ</span><span class="sxs-lookup"><span data-stu-id="7c66c-102">Send Ports and Send Port Groups</span></span>
<span data-ttu-id="7c66c-103">A*送信ポート*Microsoft BizTalk Server がメッセージを送信する先の場所は、または元の BizTalk Server はメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="7c66c-103">A *send port* is the location to which Microsoft BizTalk Server sends messages or from which BizTalk Server receives messages.</span></span> <span data-ttu-id="7c66c-104">BizTalk Server を使用して通信アクションを実装するテクノロジも提供します。</span><span class="sxs-lookup"><span data-stu-id="7c66c-104">It also provides the technology that BizTalk Server uses to implement the communication action.</span></span> <span data-ttu-id="7c66c-105">ポートの名前は、場所を一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="7c66c-105">The name of the port uniquely identifies the location.</span></span>  
  
 <span data-ttu-id="7c66c-106">メッセージが送信ポートのサービスの新しいインスタンスを送信ポートに送られるたびに作成されます。</span><span class="sxs-lookup"><span data-stu-id="7c66c-106">Any time a message is sent to a send port a new instance of a send port service is created.</span></span> <span data-ttu-id="7c66c-107">これは、サービスのインスタンスとも呼ばれる、送信ポートのインスタンスと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="7c66c-107">This is called a service instance, also known as a Send Port Instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7c66c-108">順次配送送信ポートのインスタンスを 1 つだけあります。</span><span class="sxs-lookup"><span data-stu-id="7c66c-108">There can only be one instance of an In-order delivery send port.</span></span>  
  
 <span data-ttu-id="7c66c-109">A*送信ポート グループ*は 1 つの構成で複数の送信先に同じメッセージを送信する BizTalk Server が使用できる送信ポートの名前付きコレクションです。</span><span class="sxs-lookup"><span data-stu-id="7c66c-109">A *send port group* is a named collection of send ports that BizTalk Server can use to send the same message to multiple destinations in one configuration.</span></span>  
  
 <span data-ttu-id="7c66c-110">BizTalk Server 直接からメッセージをルーティング受信できる場所、送信ポートまたは送信ポート グループの場所。</span><span class="sxs-lookup"><span data-stu-id="7c66c-110">BizTalk Server can directly route messages from receive locations to a send port, or to a send port group.</span></span> <span data-ttu-id="7c66c-111">BizTalk Server では、すべての送信ポートがそのグループ内に送信ポート グループにルーティングされるメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="7c66c-111">BizTalk Server sends messages routed to a send port group to all of the send ports in that group.</span></span>  
  
 <span data-ttu-id="7c66c-112">2 つの方法で送信ポート グループ プロセス メッセージのメンバーであるポートを送信するには。</span><span class="sxs-lookup"><span data-stu-id="7c66c-112">Send ports that are members of a send port group process messages in two ways:</span></span>  
  
-   <span data-ttu-id="7c66c-113">送信ポート グループのメンバーとして</span><span class="sxs-lookup"><span data-stu-id="7c66c-113">As a member of the send port group</span></span>  
  
-   <span data-ttu-id="7c66c-114">BizTalk Server が直接送信ポートにメッセージをルーティングした場合と</span><span class="sxs-lookup"><span data-stu-id="7c66c-114">As if BizTalk Server routed the messages to the send port directly</span></span>  
  
## <a name="send-port-and-send-port-group-states"></a><span data-ttu-id="7c66c-115">送信ポートと送信ポート グループの状態</span><span class="sxs-lookup"><span data-stu-id="7c66c-115">Send Port and Send Port Group States</span></span>  
 <span data-ttu-id="7c66c-116">BizTalk 管理コンソールが表示されますは、送信ポートおよび送信ポート グループを次の状態のいずれか。</span><span class="sxs-lookup"><span data-stu-id="7c66c-116">The BizTalk Administration Console displays send ports and send port groups in one of the following states:</span></span>  
  
- <span data-ttu-id="7c66c-117">**バインドされている**します。</span><span class="sxs-lookup"><span data-stu-id="7c66c-117">**Bound**.</span></span> <span data-ttu-id="7c66c-118">管理者は、BizTalk Server 管理コンソールを使用して、送信ポートをバインドします。 またはをオーケストレーションに送信ポート グループ。</span><span class="sxs-lookup"><span data-stu-id="7c66c-118">Using the BizTalk Server Administration Console, an administrator binds the send port or send port group to an orchestration.</span></span> <span data-ttu-id="7c66c-119">BizTalk Server では、この送信ポートまたは送信ポート グループにメッセージをルーティング、前に、管理者必要があります参加させたりとバインド済み送信ポートの開始されて、送信ポート グループ。</span><span class="sxs-lookup"><span data-stu-id="7c66c-119">Before BizTalk Server routes messages to this send port or send port group, the administrator must enlist and start the bound send port or send port group.</span></span>  
  
- <span data-ttu-id="7c66c-120">**開始**します。</span><span class="sxs-lookup"><span data-stu-id="7c66c-120">**Started**.</span></span> <span data-ttu-id="7c66c-121">この送信ポートまたは送信ポート グループのサブスクリプションが存在し、アクティブな。</span><span class="sxs-lookup"><span data-stu-id="7c66c-121">The subscription for this send port or send port group exists and is active.</span></span> <span data-ttu-id="7c66c-122">送信ポートまたは送信ポート グループは、開始状態では、BizTalk Server が送信ポートまたは送信ポート グループにメッセージを配信し、送信ポートまたは送信ポート グループでは、処理します。</span><span class="sxs-lookup"><span data-stu-id="7c66c-122">When the send port or send port group is in the started state, BizTalk Server delivers messages to the send port or send port group, and the send port or send port group processes them.</span></span> <span data-ttu-id="7c66c-123">送信ポートまたは送信ポート グループを開始することができます、前に、管理者は、バインド済み送信ポートの参加または送信ポート グループを BizTalk 管理コンソールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c66c-123">Before you can start a send port or send port group, an administrator must use the BizTalk Administration Console to enlist the bound send port or send port group.</span></span>  
  
- <span data-ttu-id="7c66c-124">**停止**します。</span><span class="sxs-lookup"><span data-stu-id="7c66c-124">**Stopped**.</span></span> <span data-ttu-id="7c66c-125">送信ポートまたは送信ポート グループは現在実行されていません。</span><span class="sxs-lookup"><span data-stu-id="7c66c-125">The send port or send port group is not currently running.</span></span> <span data-ttu-id="7c66c-126">送信ポートまたは送信ポート グループを開始し、停止すると、作業キューの処理は続行されます。</span><span class="sxs-lookup"><span data-stu-id="7c66c-126">If you started the send port or send port group and then stopped it, processing continues in the work queue.</span></span> <span data-ttu-id="7c66c-127">BizTalk Server は、停止状態にルーティングされるすべての新しいメッセージの送信ポートまたは送信の送信ハンドラーが実行されているポート グループをホストの保留キューに送信します。</span><span class="sxs-lookup"><span data-stu-id="7c66c-127">BizTalk Server sends all new messages routed to a stopped send port or send port group to the suspended queue of the host where the send handler is running.</span></span>  
  
  <span data-ttu-id="7c66c-128">次の表では、各状態、およびそれぞれの結果から使用可能なアクションを示します。</span><span class="sxs-lookup"><span data-stu-id="7c66c-128">The following table shows the actions available from each state, and the result of each.</span></span>  
  
||<span data-ttu-id="7c66c-129">バインドされています。</span><span class="sxs-lookup"><span data-stu-id="7c66c-129">Bound</span></span>|<span data-ttu-id="7c66c-130">停止</span><span class="sxs-lookup"><span data-stu-id="7c66c-130">Stopped</span></span>|<span data-ttu-id="7c66c-131">Started</span><span class="sxs-lookup"><span data-stu-id="7c66c-131">Started</span></span>|  
|------|-----------|-------------|-------------|  
|<span data-ttu-id="7c66c-132">**参加させる**</span><span class="sxs-lookup"><span data-stu-id="7c66c-132">**Enlist**</span></span>|<span data-ttu-id="7c66c-133">停止</span><span class="sxs-lookup"><span data-stu-id="7c66c-133">Stopped</span></span>|<span data-ttu-id="7c66c-134">使用できません</span><span class="sxs-lookup"><span data-stu-id="7c66c-134">Not available</span></span>|<span data-ttu-id="7c66c-135">使用できません</span><span class="sxs-lookup"><span data-stu-id="7c66c-135">Not available</span></span>|  
|<span data-ttu-id="7c66c-136">**[開始]**</span><span class="sxs-lookup"><span data-stu-id="7c66c-136">**Start**</span></span>|<span data-ttu-id="7c66c-137">Started</span><span class="sxs-lookup"><span data-stu-id="7c66c-137">Started</span></span>|<span data-ttu-id="7c66c-138">Started</span><span class="sxs-lookup"><span data-stu-id="7c66c-138">Started</span></span>|<span data-ttu-id="7c66c-139">使用できません</span><span class="sxs-lookup"><span data-stu-id="7c66c-139">Not available</span></span>|  
|<span data-ttu-id="7c66c-140">**[停止]**</span><span class="sxs-lookup"><span data-stu-id="7c66c-140">**Stop**</span></span>|<span data-ttu-id="7c66c-141">使用できません</span><span class="sxs-lookup"><span data-stu-id="7c66c-141">Not available</span></span>|<span data-ttu-id="7c66c-142">使用できません</span><span class="sxs-lookup"><span data-stu-id="7c66c-142">Not available</span></span>|<span data-ttu-id="7c66c-143">停止</span><span class="sxs-lookup"><span data-stu-id="7c66c-143">Stopped</span></span>|  
|<span data-ttu-id="7c66c-144">**参加解除します。**</span><span class="sxs-lookup"><span data-stu-id="7c66c-144">**Unenlist**</span></span>|<span data-ttu-id="7c66c-145">使用できません</span><span class="sxs-lookup"><span data-stu-id="7c66c-145">Not available</span></span>|<span data-ttu-id="7c66c-146">バインドされています。</span><span class="sxs-lookup"><span data-stu-id="7c66c-146">Bound</span></span>|<span data-ttu-id="7c66c-147">バインドされています。</span><span class="sxs-lookup"><span data-stu-id="7c66c-147">Bound</span></span>|  
  
 <span data-ttu-id="7c66c-148">組み合わされた状態の送信ポートと送信ポート グループに属しているかどうか、送信ポートまたは送信ポート グループのメッセージを処理かどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="7c66c-148">The combined state of a send port and the send port group it belongs to determines if the send port or the send port group processes a message or not.</span></span>  
  
 <span data-ttu-id="7c66c-149">次の表では、送信ポートおよび送信ポート グループの考えられる状態の組み合わせについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7c66c-149">The following table describes the possible state combinations for send ports and send port groups.</span></span>  
  
|<span data-ttu-id="7c66c-150">送信されたメッセージ</span><span class="sxs-lookup"><span data-stu-id="7c66c-150">Message Sent</span></span>|<span data-ttu-id="7c66c-151">送信ポート グループの状態</span><span class="sxs-lookup"><span data-stu-id="7c66c-151">State of Send Port Group</span></span>|<span data-ttu-id="7c66c-152">送信ポートの状態</span><span class="sxs-lookup"><span data-stu-id="7c66c-152">State of Send Port</span></span>|<span data-ttu-id="7c66c-153">結果</span><span class="sxs-lookup"><span data-stu-id="7c66c-153">Outcome</span></span>|  
|------------------|------------------------------|------------------------|-------------|  
|<span data-ttu-id="7c66c-154">送信ポートに直接</span><span class="sxs-lookup"><span data-stu-id="7c66c-154">Directly to the send port</span></span>|<span data-ttu-id="7c66c-155">いずれかの状態</span><span class="sxs-lookup"><span data-stu-id="7c66c-155">Any state</span></span>|<span data-ttu-id="7c66c-156">Started</span><span class="sxs-lookup"><span data-stu-id="7c66c-156">Started</span></span>|<span data-ttu-id="7c66c-157">メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="7c66c-157">Message is processed</span></span>|  
|<span data-ttu-id="7c66c-158">送信ポートに直接</span><span class="sxs-lookup"><span data-stu-id="7c66c-158">Directly to the send port</span></span>|<span data-ttu-id="7c66c-159">いずれかの状態</span><span class="sxs-lookup"><span data-stu-id="7c66c-159">Any state</span></span>|<span data-ttu-id="7c66c-160">停止</span><span class="sxs-lookup"><span data-stu-id="7c66c-160">Stopped</span></span>|<span data-ttu-id="7c66c-161">メッセージは中断されます。</span><span class="sxs-lookup"><span data-stu-id="7c66c-161">Message is suspended</span></span>|  
|<span data-ttu-id="7c66c-162">送信ポート グループを使用して、送信ポートに</span><span class="sxs-lookup"><span data-stu-id="7c66c-162">To the send port by means of a send port group</span></span>|<span data-ttu-id="7c66c-163">Started</span><span class="sxs-lookup"><span data-stu-id="7c66c-163">Started</span></span>|<span data-ttu-id="7c66c-164">Started</span><span class="sxs-lookup"><span data-stu-id="7c66c-164">Started</span></span>|<span data-ttu-id="7c66c-165">メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="7c66c-165">Message is processed</span></span>|  
|<span data-ttu-id="7c66c-166">送信ポート グループを使用して、送信ポートに</span><span class="sxs-lookup"><span data-stu-id="7c66c-166">To the send port by means of a send port group</span></span>|<span data-ttu-id="7c66c-167">いずれかの状態</span><span class="sxs-lookup"><span data-stu-id="7c66c-167">Any state</span></span>|<span data-ttu-id="7c66c-168">停止</span><span class="sxs-lookup"><span data-stu-id="7c66c-168">Stopped</span></span>|<span data-ttu-id="7c66c-169">メッセージは中断されます。</span><span class="sxs-lookup"><span data-stu-id="7c66c-169">Message is suspended</span></span>|  
|<span data-ttu-id="7c66c-170">送信ポート グループを使用して、送信ポートに</span><span class="sxs-lookup"><span data-stu-id="7c66c-170">To the send port by means of a send port group</span></span>|<span data-ttu-id="7c66c-171">停止</span><span class="sxs-lookup"><span data-stu-id="7c66c-171">Stopped</span></span>|<span data-ttu-id="7c66c-172">いずれかの状態</span><span class="sxs-lookup"><span data-stu-id="7c66c-172">Any state</span></span>|<span data-ttu-id="7c66c-173">メッセージは中断されます。</span><span class="sxs-lookup"><span data-stu-id="7c66c-173">Message is suspended</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7c66c-174">参照</span><span class="sxs-lookup"><span data-stu-id="7c66c-174">See Also</span></span>  
 [<span data-ttu-id="7c66c-175">アイテム</span><span class="sxs-lookup"><span data-stu-id="7c66c-175">Artifacts</span></span>](../core/artifacts.md)