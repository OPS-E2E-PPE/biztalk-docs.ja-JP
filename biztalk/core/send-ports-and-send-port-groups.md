---
title: 送信ポートおよび送信ポート グループ |Microsoft ドキュメント
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
ms.openlocfilehash: e57e56d05cf3b1a98bba83d0df92d52f09c6eda5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271826"
---
# <a name="send-ports-and-send-port-groups"></a><span data-ttu-id="a9f1a-102">送信ポートと送信ポート グループ</span><span class="sxs-lookup"><span data-stu-id="a9f1a-102">Send Ports and Send Port Groups</span></span>
<span data-ttu-id="a9f1a-103">A*送信ポート*Microsoft BizTalk Server がメッセージを送信する先の場所は、または元となる BizTalk Server がメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="a9f1a-103">A *send port* is the location to which Microsoft BizTalk Server sends messages or from which BizTalk Server receives messages.</span></span> <span data-ttu-id="a9f1a-104">また、BizTalk Server は送信ポートの機能を使用して、通信アクションを実装します。</span><span class="sxs-lookup"><span data-stu-id="a9f1a-104">It also provides the technology that BizTalk Server uses to implement the communication action.</span></span> <span data-ttu-id="a9f1a-105">この場所は、ポートの名前により一意に識別されます。</span><span class="sxs-lookup"><span data-stu-id="a9f1a-105">The name of the port uniquely identifies the location.</span></span>  
  
 <span data-ttu-id="a9f1a-106">メッセージが送信ポートに送られるたびに、送信ポート サービスの新しいインスタンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a9f1a-106">Any time a message is sent to a send port a new instance of a send port service is created.</span></span> <span data-ttu-id="a9f1a-107">これは、サービス インスタンスと呼ばれ、送信ポートのインスタンスとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="a9f1a-107">This is called a service instance, also known as a Send Port Instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a9f1a-108">順次配送の送信ポートのインスタンスは 1 つだけ指定できます。</span><span class="sxs-lookup"><span data-stu-id="a9f1a-108">There can only be one instance of an In-order delivery send port.</span></span>  
  
 <span data-ttu-id="a9f1a-109">A*送信ポート グループ*BizTalk サーバーが 1 つの構成で複数の送信先に同じメッセージを送信に使用する送信ポートの名前付きコレクションです。</span><span class="sxs-lookup"><span data-stu-id="a9f1a-109">A *send port group* is a named collection of send ports that BizTalk Server can use to send the same message to multiple destinations in one configuration.</span></span>  
  
 <span data-ttu-id="a9f1a-110">BizTalk Server は、受信場所から送信ポートまたは送信ポート グループに、直接メッセージをルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="a9f1a-110">BizTalk Server can directly route messages from receive locations to a send port, or to a send port group.</span></span> <span data-ttu-id="a9f1a-111">送信ポート グループにルーティングされたメッセージは、そのグループ内のすべての送信ポートに送信されます。</span><span class="sxs-lookup"><span data-stu-id="a9f1a-111">BizTalk Server sends messages routed to a send port group to all of the send ports in that group.</span></span>  
  
 <span data-ttu-id="a9f1a-112">送信ポート グループのメンバーである送信ポートは、メッセージを 2 とおりの方法で処理します。</span><span class="sxs-lookup"><span data-stu-id="a9f1a-112">Send ports that are members of a send port group process messages in two ways:</span></span>  
  
-   <span data-ttu-id="a9f1a-113">送信ポート グループのメンバーとして</span><span class="sxs-lookup"><span data-stu-id="a9f1a-113">As a member of the send port group</span></span>  
  
-   <span data-ttu-id="a9f1a-114">BizTalk Server がメッセージを直接送信ポートにルーティングした場合と同じように</span><span class="sxs-lookup"><span data-stu-id="a9f1a-114">As if BizTalk Server routed the messages to the send port directly</span></span>  
  
## <a name="send-port-and-send-port-group-states"></a><span data-ttu-id="a9f1a-115">送信ポートと送信ポート グループの状態</span><span class="sxs-lookup"><span data-stu-id="a9f1a-115">Send Port and Send Port Group States</span></span>  
 <span data-ttu-id="a9f1a-116">BizTalk 管理コンソールには、送信ポートおよび送信ポート グループの状態が次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9f1a-116">The BizTalk Administration Console displays send ports and send port groups in one of the following states:</span></span>  
  
-   <span data-ttu-id="a9f1a-117">**バインド**です。</span><span class="sxs-lookup"><span data-stu-id="a9f1a-117">**Bound**.</span></span> <span data-ttu-id="a9f1a-118">管理者は、BizTalk Server 管理コンソールを使用して、送信ポートまたは送信ポート グループをオーケストレーションにバインドします。</span><span class="sxs-lookup"><span data-stu-id="a9f1a-118">Using the BizTalk Server Administration Console, an administrator binds the send port or send port group to an orchestration.</span></span> <span data-ttu-id="a9f1a-119">BizTalk Server がメッセージをこの送信ポートまたは送信ポート グループにルーティングする前に、管理者はバインド済み送信ポートまたは送信ポート グループを参加させて開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9f1a-119">Before BizTalk Server routes messages to this send port or send port group, the administrator must enlist and start the bound send port or send port group.</span></span>  
  
-   <span data-ttu-id="a9f1a-120">**開始**です。</span><span class="sxs-lookup"><span data-stu-id="a9f1a-120">**Started**.</span></span> <span data-ttu-id="a9f1a-121">この送信ポートまたは送信ポート グループのサブスクリプションが存在し、アクティブです。</span><span class="sxs-lookup"><span data-stu-id="a9f1a-121">The subscription for this send port or send port group exists and is active.</span></span> <span data-ttu-id="a9f1a-122">送信ポートまたは送信ポート グループが開始状態にある場合、BizTalk Server はメッセージを送信ポートまたは送信ポート グループに配信し、送信ポートまたは送信ポート グループによってメッセージが処理されます。</span><span class="sxs-lookup"><span data-stu-id="a9f1a-122">When the send port or send port group is in the started state, BizTalk Server delivers messages to the send port or send port group, and the send port or send port group processes them.</span></span> <span data-ttu-id="a9f1a-123">送信ポートまたは送信ポート グループを開始する前に、管理者は BizTalk 管理コンソールを使用し、バインド済み送信ポートまたは送信ポート グループを参加させて開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9f1a-123">Before you can start a send port or send port group, an administrator must use the BizTalk Administration Console to enlist the bound send port or send port group.</span></span>  
  
-   <span data-ttu-id="a9f1a-124">**停止**です。</span><span class="sxs-lookup"><span data-stu-id="a9f1a-124">**Stopped**.</span></span> <span data-ttu-id="a9f1a-125">送信ポートまたは送信ポート グループは現在動作していません。</span><span class="sxs-lookup"><span data-stu-id="a9f1a-125">The send port or send port group is not currently running.</span></span> <span data-ttu-id="a9f1a-126">送信ポートまたは送信ポート グループを開始し、停止した場合、処理は作業キューで継続されます。</span><span class="sxs-lookup"><span data-stu-id="a9f1a-126">If you started the send port or send port group and then stopped it, processing continues in the work queue.</span></span> <span data-ttu-id="a9f1a-127">BizTalk Server は、停止状態の送信ポートまたは送信ポート グループにルーティングされた新しいメッセージをすべて、送信ハンドラーが動作しているホストの保留キューに送ります。</span><span class="sxs-lookup"><span data-stu-id="a9f1a-127">BizTalk Server sends all new messages routed to a stopped send port or send port group to the suspended queue of the host where the send handler is running.</span></span>  
  
 <span data-ttu-id="a9f1a-128">次の表に、それぞれの状態で利用可能なアクションとその結果を示します。</span><span class="sxs-lookup"><span data-stu-id="a9f1a-128">The following table shows the actions available from each state, and the result of each.</span></span>  
  
||<span data-ttu-id="a9f1a-129">バインド済み</span><span class="sxs-lookup"><span data-stu-id="a9f1a-129">Bound</span></span>|<span data-ttu-id="a9f1a-130">停止</span><span class="sxs-lookup"><span data-stu-id="a9f1a-130">Stopped</span></span>|<span data-ttu-id="a9f1a-131">Started</span><span class="sxs-lookup"><span data-stu-id="a9f1a-131">Started</span></span>|  
|------|-----------|-------------|-------------|  
|<span data-ttu-id="a9f1a-132">**参加させる**</span><span class="sxs-lookup"><span data-stu-id="a9f1a-132">**Enlist**</span></span>|<span data-ttu-id="a9f1a-133">停止</span><span class="sxs-lookup"><span data-stu-id="a9f1a-133">Stopped</span></span>|<span data-ttu-id="a9f1a-134">使用不可</span><span class="sxs-lookup"><span data-stu-id="a9f1a-134">Not available</span></span>|<span data-ttu-id="a9f1a-135">使用不可</span><span class="sxs-lookup"><span data-stu-id="a9f1a-135">Not available</span></span>|  
|<span data-ttu-id="a9f1a-136">**コントロール パネルの  ◆セグ : 文が分断されているため、訳の位置が入れ替わっています◇**</span><span class="sxs-lookup"><span data-stu-id="a9f1a-136">**Start**</span></span>|<span data-ttu-id="a9f1a-137">Started</span><span class="sxs-lookup"><span data-stu-id="a9f1a-137">Started</span></span>|<span data-ttu-id="a9f1a-138">Started</span><span class="sxs-lookup"><span data-stu-id="a9f1a-138">Started</span></span>|<span data-ttu-id="a9f1a-139">使用不可</span><span class="sxs-lookup"><span data-stu-id="a9f1a-139">Not available</span></span>|  
|<span data-ttu-id="a9f1a-140">**[停止]**</span><span class="sxs-lookup"><span data-stu-id="a9f1a-140">**Stop**</span></span>|<span data-ttu-id="a9f1a-141">使用不可</span><span class="sxs-lookup"><span data-stu-id="a9f1a-141">Not available</span></span>|<span data-ttu-id="a9f1a-142">使用不可</span><span class="sxs-lookup"><span data-stu-id="a9f1a-142">Not available</span></span>|<span data-ttu-id="a9f1a-143">停止</span><span class="sxs-lookup"><span data-stu-id="a9f1a-143">Stopped</span></span>|  
|<span data-ttu-id="a9f1a-144">**参加解除します。**</span><span class="sxs-lookup"><span data-stu-id="a9f1a-144">**Unenlist**</span></span>|<span data-ttu-id="a9f1a-145">使用不可</span><span class="sxs-lookup"><span data-stu-id="a9f1a-145">Not available</span></span>|<span data-ttu-id="a9f1a-146">バインド済み</span><span class="sxs-lookup"><span data-stu-id="a9f1a-146">Bound</span></span>|<span data-ttu-id="a9f1a-147">バインド済み</span><span class="sxs-lookup"><span data-stu-id="a9f1a-147">Bound</span></span>|  
  
 <span data-ttu-id="a9f1a-148">送信ポートおよび所属する送信ポート グループの組み合わされた状態により、送信ポートまたは送信ポート グループがメッセージを処理するかどうかがわかります。</span><span class="sxs-lookup"><span data-stu-id="a9f1a-148">The combined state of a send port and the send port group it belongs to determines if the send port or the send port group processes a message or not.</span></span>  
  
 <span data-ttu-id="a9f1a-149">次の表は、送信ポートおよび送信ポート グループの考えられる状態の組み合わせを示しています。</span><span class="sxs-lookup"><span data-stu-id="a9f1a-149">The following table describes the possible state combinations for send ports and send port groups.</span></span>  
  
|<span data-ttu-id="a9f1a-150">送信されたメッセージ</span><span class="sxs-lookup"><span data-stu-id="a9f1a-150">Message Sent</span></span>|<span data-ttu-id="a9f1a-151">送信ポート グループの状態</span><span class="sxs-lookup"><span data-stu-id="a9f1a-151">State of Send Port Group</span></span>|<span data-ttu-id="a9f1a-152">送信ポートの状態</span><span class="sxs-lookup"><span data-stu-id="a9f1a-152">State of Send Port</span></span>|<span data-ttu-id="a9f1a-153">結果</span><span class="sxs-lookup"><span data-stu-id="a9f1a-153">Outcome</span></span>|  
|------------------|------------------------------|------------------------|-------------|  
|<span data-ttu-id="a9f1a-154">直接送信ポートに</span><span class="sxs-lookup"><span data-stu-id="a9f1a-154">Directly to the send port</span></span>|<span data-ttu-id="a9f1a-155">すべての状態</span><span class="sxs-lookup"><span data-stu-id="a9f1a-155">Any state</span></span>|<span data-ttu-id="a9f1a-156">Started</span><span class="sxs-lookup"><span data-stu-id="a9f1a-156">Started</span></span>|<span data-ttu-id="a9f1a-157">メッセージが処理される。</span><span class="sxs-lookup"><span data-stu-id="a9f1a-157">Message is processed</span></span>|  
|<span data-ttu-id="a9f1a-158">直接送信ポートに</span><span class="sxs-lookup"><span data-stu-id="a9f1a-158">Directly to the send port</span></span>|<span data-ttu-id="a9f1a-159">すべての状態</span><span class="sxs-lookup"><span data-stu-id="a9f1a-159">Any state</span></span>|<span data-ttu-id="a9f1a-160">停止</span><span class="sxs-lookup"><span data-stu-id="a9f1a-160">Stopped</span></span>|<span data-ttu-id="a9f1a-161">メッセージが中断される。</span><span class="sxs-lookup"><span data-stu-id="a9f1a-161">Message is suspended</span></span>|  
|<span data-ttu-id="a9f1a-162">送信ポート グループを介して送信ポートに</span><span class="sxs-lookup"><span data-stu-id="a9f1a-162">To the send port by means of a send port group</span></span>|<span data-ttu-id="a9f1a-163">Started</span><span class="sxs-lookup"><span data-stu-id="a9f1a-163">Started</span></span>|<span data-ttu-id="a9f1a-164">Started</span><span class="sxs-lookup"><span data-stu-id="a9f1a-164">Started</span></span>|<span data-ttu-id="a9f1a-165">メッセージが処理される。</span><span class="sxs-lookup"><span data-stu-id="a9f1a-165">Message is processed</span></span>|  
|<span data-ttu-id="a9f1a-166">送信ポート グループを介して送信ポートに</span><span class="sxs-lookup"><span data-stu-id="a9f1a-166">To the send port by means of a send port group</span></span>|<span data-ttu-id="a9f1a-167">すべての状態</span><span class="sxs-lookup"><span data-stu-id="a9f1a-167">Any state</span></span>|<span data-ttu-id="a9f1a-168">停止</span><span class="sxs-lookup"><span data-stu-id="a9f1a-168">Stopped</span></span>|<span data-ttu-id="a9f1a-169">メッセージが中断される。</span><span class="sxs-lookup"><span data-stu-id="a9f1a-169">Message is suspended</span></span>|  
|<span data-ttu-id="a9f1a-170">送信ポート グループを介して送信ポートに</span><span class="sxs-lookup"><span data-stu-id="a9f1a-170">To the send port by means of a send port group</span></span>|<span data-ttu-id="a9f1a-171">停止</span><span class="sxs-lookup"><span data-stu-id="a9f1a-171">Stopped</span></span>|<span data-ttu-id="a9f1a-172">すべての状態</span><span class="sxs-lookup"><span data-stu-id="a9f1a-172">Any state</span></span>|<span data-ttu-id="a9f1a-173">メッセージが中断される。</span><span class="sxs-lookup"><span data-stu-id="a9f1a-173">Message is suspended</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a9f1a-174">参照</span><span class="sxs-lookup"><span data-stu-id="a9f1a-174">See Also</span></span>  
 [<span data-ttu-id="a9f1a-175">成果物</span><span class="sxs-lookup"><span data-stu-id="a9f1a-175">Artifacts</span></span>](../core/artifacts.md)