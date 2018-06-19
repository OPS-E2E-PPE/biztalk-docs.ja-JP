---
title: オーケストレーションを参加させる方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [orchestrations], enlisting
- orchestrations, enlisting
- enlisting, orchestrations
ms.assetid: b21a398b-8c9a-42ae-aac0-de35dbfd8176
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f58cb697e270052f8f42229997b1125e808816b6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255842"
---
# <a name="how-to-enlist-an-orchestration"></a><span data-ttu-id="4323f-102">オーケストレーションを参加させる方法</span><span class="sxs-lookup"><span data-stu-id="4323f-102">How to Enlist an Orchestration</span></span>
<span data-ttu-id="4323f-103">このトピックでは、BizTalk Server 管理コンソールを使用して、オーケストレーションをホストに参加させる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4323f-103">This topic describes how to use the BizTalk Server Administration console to enlist an orchestration into a host.</span></span> <span data-ttu-id="4323f-104">オーケストレーションは参加させて初めて開始できるようになります。</span><span class="sxs-lookup"><span data-stu-id="4323f-104">The orchestration must be enlisted before you can start it.</span></span>  
  
 <span data-ttu-id="4323f-105">オーケストレーションを参加させる際は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="4323f-105">When enlisting an orchestration, bear in mind the following points:</span></span>  
  
-   <span data-ttu-id="4323f-106">**参加させる前に、オーケストレーションをバインドする必要があります。**</span><span class="sxs-lookup"><span data-stu-id="4323f-106">**The orchestration must be bound before you can enlist it.**</span></span> <span data-ttu-id="4323f-107">オーケストレーションのバインドの構成方法の詳細については、次を参照してください。[オーケストレーションのバインドを構成する方法](../core/how-to-configure-bindings-for-an-orchestration.md)です。</span><span class="sxs-lookup"><span data-stu-id="4323f-107">For instructions on configuring bindings for orchestrations, see [How to Configure Bindings for an Orchestration](../core/how-to-configure-bindings-for-an-orchestration.md).</span></span>  
  
-   <span data-ttu-id="4323f-108">**サブスクリプションは自動的に作成されます。**</span><span class="sxs-lookup"><span data-stu-id="4323f-108">**Subscriptions are automatically created.**</span></span> <span data-ttu-id="4323f-109">オーケストレーションの参加プロセスを経て、必要なサブスクリプションがメッセージ ボックス データベースに作成されます。</span><span class="sxs-lookup"><span data-stu-id="4323f-109">The orchestration enlistment process creates the necessary subscriptions in the MessageBox database.</span></span>  
  
-   <span data-ttu-id="4323f-110">**アプリケーションをインストールする必要があります。**</span><span class="sxs-lookup"><span data-stu-id="4323f-110">**You must install the application.**</span></span> <span data-ttu-id="4323f-111">オーケストレーションを実行するすべてのコンピューターに、そのオーケストレーションが含まれているアプリケーションをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4323f-111">You must install the application containing the orchestration on all of computers where the orchestration will run.</span></span> <span data-ttu-id="4323f-112">詳細については、次を参照してください。[を BizTalk アプリケーションをインストールする方法](../core/how-to-install-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="4323f-112">For more information, see [How to Install a BizTalk Application](../core/how-to-install-a-biztalk-application.md).</span></span>  
  
-   <span data-ttu-id="4323f-113">**呼び出し元のオーケストレーションは、呼び出し先オーケストレーションと同じホストにバインドする必要があります。**</span><span class="sxs-lookup"><span data-stu-id="4323f-113">**A calling orchestration must be bound to the same host as the called orchestration.**</span></span> <span data-ttu-id="4323f-114">呼び出し元オーケストレーションは、呼び出し先オーケストレーションと同じホストにバインドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4323f-114">Any orchestration that is called by another orchestration must be bound to the same host as the calling orchestration.</span></span>  
  
-   <span data-ttu-id="4323f-115">**依存オーケストレーションを登録する必要があります。**</span><span class="sxs-lookup"><span data-stu-id="4323f-115">**You should also enlist dependent orchestrations.**</span></span> <span data-ttu-id="4323f-116">オーケストレーションを参加させるとき、依存オーケストレーションがあれば、それらも一緒に参加させないと、依存オーケストレーションにサブスクリプションが割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="4323f-116">If you enlist an orchestration but do not enlist any dependent orchestrations, the dependent orchestrations will not have any subscriptions.</span></span> <span data-ttu-id="4323f-117">依存オーケストレーションにサブスクリプションがないと、メッセージに対応するサブスクリプションが存在しないため、メッセージが削除または保留される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4323f-117">A dependent orchestration without subscriptions may drop or suspend messages because there is no subscription for the messages to match.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4323f-118">アプリケーション開発者が開発プロセス中にオーケストレーションを参加させてその機能をテストするには、このトピックの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4323f-118">The application developer can enlist an orchestration to test its functionality during the development process  by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4323f-119">前提条件</span><span class="sxs-lookup"><span data-stu-id="4323f-119">Prerequisites</span></span>  
 <span data-ttu-id="4323f-120">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4323f-120">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="4323f-121">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="4323f-121">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-enlist-an-orchestration"></a><span data-ttu-id="4323f-122">オーケストレーションを参加させるには</span><span class="sxs-lookup"><span data-stu-id="4323f-122">To enlist an orchestration</span></span>  
  
1.  <span data-ttu-id="4323f-123">をクリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="4323f-123">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="4323f-124">コンソール ツリーで  **BizTalk Server 管理コンソール**、BizTalk グループを展開し、**アプリケーション**、し、参加させるオーケストレーションを含むアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="4323f-124">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the orchestration that you want to enlist.</span></span>  
  
3.  <span data-ttu-id="4323f-125">をクリックして**オーケストレーション**、参加させ、をクリックしてオーケストレーションを右クリックして**Enlist**です。</span><span class="sxs-lookup"><span data-stu-id="4323f-125">Click **Orchestrations**, right-click the orchestration to enlist, and then click **Enlist**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4323f-126">一度に複数のオーケストレーションを参加させる、shift キーを押しながら、参加させる各オーケストレーションを選択する、オーケストレーションを右クリックし、をクリックして**Enlist**です。</span><span class="sxs-lookup"><span data-stu-id="4323f-126">To enlist multiple orchestrations at once, hold down the shift key and select each orchestration to enlist, right-click an orchestration, and then click **Enlist**.</span></span>  
  
     <span data-ttu-id="4323f-127">オーケストレーションが登録され、適切なサブスクリプションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4323f-127">The orchestration is enlisted and the appropriate subscriptions are created.</span></span> <span data-ttu-id="4323f-128">オーケストレーションは停止状態になります。</span><span class="sxs-lookup"><span data-stu-id="4323f-128">The orchestration is in the stopped state.</span></span> <span data-ttu-id="4323f-129">受信メッセージの処理を開始する必要があります明示的にオーケストレーションを開始しを右クリックし**開始**です。</span><span class="sxs-lookup"><span data-stu-id="4323f-129">To start processing incoming messages, you must explicitly start the orchestration by right-clicking it and clicking **Start**.</span></span> <span data-ttu-id="4323f-130">詳細については、次を参照してください。[オーケストレーションを開始する方法](../core/how-to-start-an-orchestration.md)です。</span><span class="sxs-lookup"><span data-stu-id="4323f-130">For more information, see [How to Start an Orchestration](../core/how-to-start-an-orchestration.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4323f-131">参照</span><span class="sxs-lookup"><span data-stu-id="4323f-131">See Also</span></span>  
 <span data-ttu-id="4323f-132">[オーケストレーションの管理](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="4323f-132">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 [<span data-ttu-id="4323f-133">オーケストレーションを参加解除する方法</span><span class="sxs-lookup"><span data-stu-id="4323f-133">How to Unenlist an Orchestration</span></span>](../core/how-to-unenlist-an-orchestration.md)