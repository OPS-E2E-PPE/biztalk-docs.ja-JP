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
ms.openlocfilehash: bad7bc94bd1721dcdf55dbf94af3b9ccc0e750d8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994811"
---
# <a name="send-ports-and-send-port-groups"></a><span data-ttu-id="921c0-102">送信ポートと送信ポート グループ</span><span class="sxs-lookup"><span data-stu-id="921c0-102">Send Ports and Send Port Groups</span></span>
<span data-ttu-id="921c0-103">A*送信ポート*Microsoft BizTalk Server がメッセージを送信する先の場所は、または元の BizTalk Server はメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="921c0-103">A *send port* is the location to which Microsoft BizTalk Server sends messages or from which BizTalk Server receives messages.</span></span> <span data-ttu-id="921c0-104">また、BizTalk Server は送信ポートの機能を使用して、通信アクションを実装します。</span><span class="sxs-lookup"><span data-stu-id="921c0-104">It also provides the technology that BizTalk Server uses to implement the communication action.</span></span> <span data-ttu-id="921c0-105">この場所は、ポートの名前により一意に識別されます。</span><span class="sxs-lookup"><span data-stu-id="921c0-105">The name of the port uniquely identifies the location.</span></span>  
  
 <span data-ttu-id="921c0-106">メッセージが送信ポートに送られるたびに、送信ポート サービスの新しいインスタンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="921c0-106">Any time a message is sent to a send port a new instance of a send port service is created.</span></span> <span data-ttu-id="921c0-107">これは、サービス インスタンスと呼ばれ、送信ポートのインスタンスとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="921c0-107">This is called a service instance, also known as a Send Port Instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="921c0-108">順次配送の送信ポートのインスタンスは 1 つだけ指定できます。</span><span class="sxs-lookup"><span data-stu-id="921c0-108">There can only be one instance of an In-order delivery send port.</span></span>  
  
 <span data-ttu-id="921c0-109">A*送信ポート グループ*は 1 つの構成で複数の送信先に同じメッセージを送信する BizTalk Server が使用できる送信ポートの名前付きコレクションです。</span><span class="sxs-lookup"><span data-stu-id="921c0-109">A *send port group* is a named collection of send ports that BizTalk Server can use to send the same message to multiple destinations in one configuration.</span></span>  
  
 <span data-ttu-id="921c0-110">BizTalk Server は、受信場所から送信ポートまたは送信ポート グループに、直接メッセージをルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="921c0-110">BizTalk Server can directly route messages from receive locations to a send port, or to a send port group.</span></span> <span data-ttu-id="921c0-111">送信ポート グループにルーティングされたメッセージは、そのグループ内のすべての送信ポートに送信されます。</span><span class="sxs-lookup"><span data-stu-id="921c0-111">BizTalk Server sends messages routed to a send port group to all of the send ports in that group.</span></span>  
  
 <span data-ttu-id="921c0-112">送信ポート グループのメンバーである送信ポートは、メッセージを 2 とおりの方法で処理します。</span><span class="sxs-lookup"><span data-stu-id="921c0-112">Send ports that are members of a send port group process messages in two ways:</span></span>  
  
-   <span data-ttu-id="921c0-113">送信ポート グループのメンバーとして</span><span class="sxs-lookup"><span data-stu-id="921c0-113">As a member of the send port group</span></span>  
  
-   <span data-ttu-id="921c0-114">BizTalk Server がメッセージを直接送信ポートにルーティングした場合と同じように</span><span class="sxs-lookup"><span data-stu-id="921c0-114">As if BizTalk Server routed the messages to the send port directly</span></span>  
  
## <a name="send-port-and-send-port-group-states"></a><span data-ttu-id="921c0-115">送信ポートと送信ポート グループの状態</span><span class="sxs-lookup"><span data-stu-id="921c0-115">Send Port and Send Port Group States</span></span>  
 <span data-ttu-id="921c0-116">BizTalk 管理コンソールには、送信ポートおよび送信ポート グループの状態が次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="921c0-116">The BizTalk Administration Console displays send ports and send port groups in one of the following states:</span></span>  
  
- <span data-ttu-id="921c0-117">**バインドされている**します。</span><span class="sxs-lookup"><span data-stu-id="921c0-117">**Bound**.</span></span> <span data-ttu-id="921c0-118">管理者は、BizTalk Server 管理コンソールを使用して、送信ポートまたは送信ポート グループをオーケストレーションにバインドします。</span><span class="sxs-lookup"><span data-stu-id="921c0-118">Using the BizTalk Server Administration Console, an administrator binds the send port or send port group to an orchestration.</span></span> <span data-ttu-id="921c0-119">BizTalk Server がメッセージをこの送信ポートまたは送信ポート グループにルーティングする前に、管理者はバインド済み送信ポートまたは送信ポート グループを参加させて開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="921c0-119">Before BizTalk Server routes messages to this send port or send port group, the administrator must enlist and start the bound send port or send port group.</span></span>  
  
- <span data-ttu-id="921c0-120">**開始**します。</span><span class="sxs-lookup"><span data-stu-id="921c0-120">**Started**.</span></span> <span data-ttu-id="921c0-121">この送信ポートまたは送信ポート グループのサブスクリプションが存在し、アクティブです。</span><span class="sxs-lookup"><span data-stu-id="921c0-121">The subscription for this send port or send port group exists and is active.</span></span> <span data-ttu-id="921c0-122">送信ポートまたは送信ポート グループが開始状態にある場合、BizTalk Server はメッセージを送信ポートまたは送信ポート グループに配信し、送信ポートまたは送信ポート グループによってメッセージが処理されます。</span><span class="sxs-lookup"><span data-stu-id="921c0-122">When the send port or send port group is in the started state, BizTalk Server delivers messages to the send port or send port group, and the send port or send port group processes them.</span></span> <span data-ttu-id="921c0-123">送信ポートまたは送信ポート グループを開始する前に、管理者は BizTalk 管理コンソールを使用し、バインド済み送信ポートまたは送信ポート グループを参加させて開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="921c0-123">Before you can start a send port or send port group, an administrator must use the BizTalk Administration Console to enlist the bound send port or send port group.</span></span>  
  
- <span data-ttu-id="921c0-124">**停止**します。</span><span class="sxs-lookup"><span data-stu-id="921c0-124">**Stopped**.</span></span> <span data-ttu-id="921c0-125">送信ポートまたは送信ポート グループは現在動作していません。</span><span class="sxs-lookup"><span data-stu-id="921c0-125">The send port or send port group is not currently running.</span></span> <span data-ttu-id="921c0-126">送信ポートまたは送信ポート グループを開始し、停止した場合、処理は作業キューで継続されます。</span><span class="sxs-lookup"><span data-stu-id="921c0-126">If you started the send port or send port group and then stopped it, processing continues in the work queue.</span></span> <span data-ttu-id="921c0-127">BizTalk Server は、停止状態の送信ポートまたは送信ポート グループにルーティングされた新しいメッセージをすべて、送信ハンドラーが動作しているホストの保留キューに送ります。</span><span class="sxs-lookup"><span data-stu-id="921c0-127">BizTalk Server sends all new messages routed to a stopped send port or send port group to the suspended queue of the host where the send handler is running.</span></span>  
  
  <span data-ttu-id="921c0-128">次の表に、それぞれの状態で利用可能なアクションとその結果を示します。</span><span class="sxs-lookup"><span data-stu-id="921c0-128">The following table shows the actions available from each state, and the result of each.</span></span>  
  
||<span data-ttu-id="921c0-129">バインド済み</span><span class="sxs-lookup"><span data-stu-id="921c0-129">Bound</span></span>|<span data-ttu-id="921c0-130">停止</span><span class="sxs-lookup"><span data-stu-id="921c0-130">Stopped</span></span>|<span data-ttu-id="921c0-131">Started</span><span class="sxs-lookup"><span data-stu-id="921c0-131">Started</span></span>|  
|------|-----------|-------------|-------------|  
|<span data-ttu-id="921c0-132">**参加させる**</span><span class="sxs-lookup"><span data-stu-id="921c0-132">**Enlist**</span></span>|<span data-ttu-id="921c0-133">停止</span><span class="sxs-lookup"><span data-stu-id="921c0-133">Stopped</span></span>|<span data-ttu-id="921c0-134">使用できません</span><span class="sxs-lookup"><span data-stu-id="921c0-134">Not available</span></span>|<span data-ttu-id="921c0-135">使用できません</span><span class="sxs-lookup"><span data-stu-id="921c0-135">Not available</span></span>|  
|<span data-ttu-id="921c0-136">**コントロール パネルの  ◆セグ : 文が分断されているため、訳の位置が入れ替わっています◇**</span><span class="sxs-lookup"><span data-stu-id="921c0-136">**Start**</span></span>|<span data-ttu-id="921c0-137">Started</span><span class="sxs-lookup"><span data-stu-id="921c0-137">Started</span></span>|<span data-ttu-id="921c0-138">Started</span><span class="sxs-lookup"><span data-stu-id="921c0-138">Started</span></span>|<span data-ttu-id="921c0-139">使用できません</span><span class="sxs-lookup"><span data-stu-id="921c0-139">Not available</span></span>|  
|<span data-ttu-id="921c0-140">**[停止]**</span><span class="sxs-lookup"><span data-stu-id="921c0-140">**Stop**</span></span>|<span data-ttu-id="921c0-141">使用できません</span><span class="sxs-lookup"><span data-stu-id="921c0-141">Not available</span></span>|<span data-ttu-id="921c0-142">使用できません</span><span class="sxs-lookup"><span data-stu-id="921c0-142">Not available</span></span>|<span data-ttu-id="921c0-143">停止</span><span class="sxs-lookup"><span data-stu-id="921c0-143">Stopped</span></span>|  
|<span data-ttu-id="921c0-144">**参加解除します。**</span><span class="sxs-lookup"><span data-stu-id="921c0-144">**Unenlist**</span></span>|<span data-ttu-id="921c0-145">使用できません</span><span class="sxs-lookup"><span data-stu-id="921c0-145">Not available</span></span>|<span data-ttu-id="921c0-146">バインド済み</span><span class="sxs-lookup"><span data-stu-id="921c0-146">Bound</span></span>|<span data-ttu-id="921c0-147">バインド済み</span><span class="sxs-lookup"><span data-stu-id="921c0-147">Bound</span></span>|  
  
 <span data-ttu-id="921c0-148">送信ポートおよび所属する送信ポート グループの組み合わされた状態により、送信ポートまたは送信ポート グループがメッセージを処理するかどうかがわかります。</span><span class="sxs-lookup"><span data-stu-id="921c0-148">The combined state of a send port and the send port group it belongs to determines if the send port or the send port group processes a message or not.</span></span>  
  
 <span data-ttu-id="921c0-149">次の表は、送信ポートおよび送信ポート グループの考えられる状態の組み合わせを示しています。</span><span class="sxs-lookup"><span data-stu-id="921c0-149">The following table describes the possible state combinations for send ports and send port groups.</span></span>  
  
|<span data-ttu-id="921c0-150">送信されたメッセージ</span><span class="sxs-lookup"><span data-stu-id="921c0-150">Message Sent</span></span>|<span data-ttu-id="921c0-151">送信ポート グループの状態</span><span class="sxs-lookup"><span data-stu-id="921c0-151">State of Send Port Group</span></span>|<span data-ttu-id="921c0-152">送信ポートの状態</span><span class="sxs-lookup"><span data-stu-id="921c0-152">State of Send Port</span></span>|<span data-ttu-id="921c0-153">結果</span><span class="sxs-lookup"><span data-stu-id="921c0-153">Outcome</span></span>|  
|------------------|------------------------------|------------------------|-------------|  
|<span data-ttu-id="921c0-154">直接送信ポートに</span><span class="sxs-lookup"><span data-stu-id="921c0-154">Directly to the send port</span></span>|<span data-ttu-id="921c0-155">すべての状態</span><span class="sxs-lookup"><span data-stu-id="921c0-155">Any state</span></span>|<span data-ttu-id="921c0-156">Started</span><span class="sxs-lookup"><span data-stu-id="921c0-156">Started</span></span>|<span data-ttu-id="921c0-157">メッセージが処理される。</span><span class="sxs-lookup"><span data-stu-id="921c0-157">Message is processed</span></span>|  
|<span data-ttu-id="921c0-158">直接送信ポートに</span><span class="sxs-lookup"><span data-stu-id="921c0-158">Directly to the send port</span></span>|<span data-ttu-id="921c0-159">すべての状態</span><span class="sxs-lookup"><span data-stu-id="921c0-159">Any state</span></span>|<span data-ttu-id="921c0-160">停止</span><span class="sxs-lookup"><span data-stu-id="921c0-160">Stopped</span></span>|<span data-ttu-id="921c0-161">メッセージが中断される。</span><span class="sxs-lookup"><span data-stu-id="921c0-161">Message is suspended</span></span>|  
|<span data-ttu-id="921c0-162">送信ポート グループを介して送信ポートに</span><span class="sxs-lookup"><span data-stu-id="921c0-162">To the send port by means of a send port group</span></span>|<span data-ttu-id="921c0-163">Started</span><span class="sxs-lookup"><span data-stu-id="921c0-163">Started</span></span>|<span data-ttu-id="921c0-164">Started</span><span class="sxs-lookup"><span data-stu-id="921c0-164">Started</span></span>|<span data-ttu-id="921c0-165">メッセージが処理される。</span><span class="sxs-lookup"><span data-stu-id="921c0-165">Message is processed</span></span>|  
|<span data-ttu-id="921c0-166">送信ポート グループを介して送信ポートに</span><span class="sxs-lookup"><span data-stu-id="921c0-166">To the send port by means of a send port group</span></span>|<span data-ttu-id="921c0-167">すべての状態</span><span class="sxs-lookup"><span data-stu-id="921c0-167">Any state</span></span>|<span data-ttu-id="921c0-168">停止</span><span class="sxs-lookup"><span data-stu-id="921c0-168">Stopped</span></span>|<span data-ttu-id="921c0-169">メッセージが中断される。</span><span class="sxs-lookup"><span data-stu-id="921c0-169">Message is suspended</span></span>|  
|<span data-ttu-id="921c0-170">送信ポート グループを介して送信ポートに</span><span class="sxs-lookup"><span data-stu-id="921c0-170">To the send port by means of a send port group</span></span>|<span data-ttu-id="921c0-171">停止</span><span class="sxs-lookup"><span data-stu-id="921c0-171">Stopped</span></span>|<span data-ttu-id="921c0-172">すべての状態</span><span class="sxs-lookup"><span data-stu-id="921c0-172">Any state</span></span>|<span data-ttu-id="921c0-173">メッセージが中断される。</span><span class="sxs-lookup"><span data-stu-id="921c0-173">Message is suspended</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="921c0-174">参照</span><span class="sxs-lookup"><span data-stu-id="921c0-174">See Also</span></span>  
 [<span data-ttu-id="921c0-175">アイテム</span><span class="sxs-lookup"><span data-stu-id="921c0-175">Artifacts</span></span>](../core/artifacts.md)