---
title: BizTalk アプリケーション開始および停止する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- starting
- starting, applications
- managing [applications], starting
- managing [applications], stopping
- applications, starting
- stopping, applications
- applications, stopping
- stopping
ms.assetid: f9f83e99-a1e2-4dfd-b3be-60d3ec2cbcc4
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 979de8e8614d05ba97223e43c90ed0ec83cefc4a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968731"
---
# <a name="how-to-start-and-stop-a-biztalk-application"></a><span data-ttu-id="6a876-102">BizTalk アプリケーションを開始および停止する方法</span><span class="sxs-lookup"><span data-stu-id="6a876-102">How to Start and Stop a BizTalk Application</span></span>
<span data-ttu-id="6a876-103">このトピックでは、BizTalk Server 管理コンソールを使用して、BizTalk アプリケーションを開始および停止する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6a876-103">This topic describes how to use the BizTalk Server Administration console to start and stop a BizTalk application.</span></span>  
  
 <span data-ttu-id="6a876-104">それに含まれるすべてのオーケストレーションのバインドを構成する必要があります、アプリケーションを開始する前に」の説明に従って[オーケストレーションのバインドを構成する方法](../core/how-to-configure-bindings-for-an-orchestration.md)します。</span><span class="sxs-lookup"><span data-stu-id="6a876-104">Before you can start an application, bindings must be configured for all orchestrations it contains, as described in [How to Configure Bindings for an Orchestration](../core/how-to-configure-bindings-for-an-orchestration.md).</span></span>  
  
 <span data-ttu-id="6a876-105">アプリケーションを開始するとき、次のオプションを 1 つ以上選択できます。</span><span class="sxs-lookup"><span data-stu-id="6a876-105">When you start an application, you can select one or more of the following options, as follows:</span></span>  
  
-   <span data-ttu-id="6a876-106">[すべてのオーケストレーションを参加させて開始する]</span><span class="sxs-lookup"><span data-stu-id="6a876-106">Enlist and start all orchestrations.</span></span>  
  
-   <span data-ttu-id="6a876-107">[すべての送信ポートを参加させて開始する]</span><span class="sxs-lookup"><span data-stu-id="6a876-107">Enlist and start all send ports.</span></span>  
  
-   <span data-ttu-id="6a876-108">[すべての送信ポート グループを参加させて開始する]</span><span class="sxs-lookup"><span data-stu-id="6a876-108">Enlist and start all send port groups.</span></span>  
  
-   <span data-ttu-id="6a876-109">[すべての受信場所を有効にする]</span><span class="sxs-lookup"><span data-stu-id="6a876-109">Enable all receive locations.</span></span>  
  
-   <span data-ttu-id="6a876-110">[関連するすべてのホスト インスタンスを開始する]</span><span class="sxs-lookup"><span data-stu-id="6a876-110">Start all associated host instances.</span></span>  
  
-   <span data-ttu-id="6a876-111">[中断したインスタンスを再開する]</span><span class="sxs-lookup"><span data-stu-id="6a876-111">Resume suspended instances.</span></span>  
  
-   <span data-ttu-id="6a876-112">すべてのポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="6a876-112">Deploy all policies.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6a876-113">自動的に展開されるのは、アプリケーションの公開済みポリシーのみです。</span><span class="sxs-lookup"><span data-stu-id="6a876-113">Only published policies in the application are deployed automatically.</span></span> <span data-ttu-id="6a876-114">公開されていないポリシーは展開されません。</span><span class="sxs-lookup"><span data-stu-id="6a876-114">If a policy is not published, it will not be deployed.</span></span>  
  
 <span data-ttu-id="6a876-115">アプリケーションを停止するとき、次のいずれかのオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="6a876-115">When you stop an application, you can select one of the following options:</span></span>  
  
-   <span data-ttu-id="6a876-116">**部分停止 - 実行中のインスタンスを続行します。**</span><span class="sxs-lookup"><span data-stu-id="6a876-116">**Partial Stop - Allow running instances to continue.**</span></span> <span data-ttu-id="6a876-117">このオプションを選択すると、アプリケーションの受信場所はすべて無効になりますが、その他のアイテムはすべて以前の状態のままになります。</span><span class="sxs-lookup"><span data-stu-id="6a876-117">This option disables all receive locations in the application, but leaves all other artifacts in their previous state.</span></span> <span data-ttu-id="6a876-118">これにより、実行中のインスタンスは現在システム内にあるメッセージの処理を完了できます。</span><span class="sxs-lookup"><span data-stu-id="6a876-118">This allows running instances to complete processing messages that are currently in the system.</span></span> <span data-ttu-id="6a876-119">このオプションを使用する場合、複数の入力を必要とするメッセージ トランザクションは完了できない可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6a876-119">Note that if a message transaction requires multiple inputs, it may not be able to complete when you use this option.</span></span>  
  
-   <span data-ttu-id="6a876-120">**部分停止 - 実行中のインスタンスを中断します。**</span><span class="sxs-lookup"><span data-stu-id="6a876-120">**Partial Stop - Suspend running instances.**</span></span> <span data-ttu-id="6a876-121">このオプションを選択すると、アプリケーションの受信場所がすべて無効になり、オーケストレーションと送信ポートがすべて停止されます。</span><span class="sxs-lookup"><span data-stu-id="6a876-121">This option disables all receive locations and stops all orchestrations and send ports in the application.</span></span> <span data-ttu-id="6a876-122">アイテムの参加解除や展開解除は行われません。</span><span class="sxs-lookup"><span data-stu-id="6a876-122">It does not unenlist or undeploy any artifacts.</span></span> <span data-ttu-id="6a876-123">このオプションは、アプリケーションを一時的に停止する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="6a876-123">Use this option when you want to temporarily pause the application.</span></span>  
  
-   <span data-ttu-id="6a876-124">**完全停止 - インスタンスを終了します。**</span><span class="sxs-lookup"><span data-stu-id="6a876-124">**Full Stop - Terminate instances.**</span></span> <span data-ttu-id="6a876-125">このオプションを選択すると、アプリケーションの受信場所がすべて無効になり、オーケストレーションと送信ポートがすべて停止されて参加解除され、ポリシーもすべて展開解除されます。</span><span class="sxs-lookup"><span data-stu-id="6a876-125">This option disables all receive locations, stops and unenlists all orchestrations and send ports, and undeploys all policies in the application.</span></span> <span data-ttu-id="6a876-126">このオプションは、アプリケーションを完全に展開解除する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="6a876-126">Use this option when you want to completely undeploy an application.</span></span> <span data-ttu-id="6a876-127">まだメッセージを処理している実行中のインスタンスがある場合、そのインスタンスの処理は完了しません。</span><span class="sxs-lookup"><span data-stu-id="6a876-127">Note that any running instances that are still processing messages will not complete processing.</span></span> <span data-ttu-id="6a876-128">詳細については、[BizTalk アプリケーションを展開解除](../core/undeploying-biztalk-applications.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a876-128">For more information, see [Undeploying BizTalk Applications](../core/undeploying-biztalk-applications.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6a876-129">前提条件</span><span class="sxs-lookup"><span data-stu-id="6a876-129">Prerequisites</span></span>  
 <span data-ttu-id="6a876-130">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a876-130">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="6a876-131">BizTalk Operators は、部分停止は実行できますが完全停止は実行できません。</span><span class="sxs-lookup"><span data-stu-id="6a876-131">BizTalk Operators can perform a partial stop, but not a full stop.</span></span> <span data-ttu-id="6a876-132">また、BizTalk Operators は、すべてのアイテムが参加している場合にはアプリケーションを開始できます。</span><span class="sxs-lookup"><span data-stu-id="6a876-132">In addition, BizTalk Operators can start an application if all artifacts are enlisted.</span></span> <span data-ttu-id="6a876-133">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="6a876-133">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-start-or-stop-a-biztalk-application"></a><span data-ttu-id="6a876-134">BizTalk アプリケーションを開始または停止するには</span><span class="sxs-lookup"><span data-stu-id="6a876-134">To start or stop a BizTalk application</span></span>  
  
1. <span data-ttu-id="6a876-135">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="6a876-135">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="6a876-136">コンソール ツリーで、展開**BizTalk Server 管理**、BizTalk グループを展開し、展開、**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="6a876-136">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="6a876-137">開始または停止、およびクリックする BizTalk アプリケーションを右クリックして**開始**または**停止**します。</span><span class="sxs-lookup"><span data-stu-id="6a876-137">Right-click the BizTalk application that you want to start or stop, and then click **Start** or **Stop**.</span></span>  
  
4. <span data-ttu-id="6a876-138">選択の開始または停止のオプションをクリックしします**開始**または**停止**します。</span><span class="sxs-lookup"><span data-stu-id="6a876-138">Select the start or stop options you want and click **Start** or **Stop**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a876-139">参照</span><span class="sxs-lookup"><span data-stu-id="6a876-139">See Also</span></span>  
 <span data-ttu-id="6a876-140">[BizTalk アプリケーション展開、管理](../core/deploying-and-managing-biztalk-applications.md) </span><span class="sxs-lookup"><span data-stu-id="6a876-140">[Deploying and Managing BizTalk Applications](../core/deploying-and-managing-biztalk-applications.md) </span></span>  
 [<span data-ttu-id="6a876-141">BizTalk アプリケーションの更新</span><span class="sxs-lookup"><span data-stu-id="6a876-141">Updating BizTalk Applications</span></span>](../core/updating-biztalk-applications.md)