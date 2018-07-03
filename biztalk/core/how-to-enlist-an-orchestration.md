---
title: オーケストレーションを参加させる方法 |Microsoft Docs
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
ms.openlocfilehash: 203f8a61c439230b692577c8674b12e35944c24f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966291"
---
# <a name="how-to-enlist-an-orchestration"></a><span data-ttu-id="d8b4b-102">オーケストレーションを参加させる方法</span><span class="sxs-lookup"><span data-stu-id="d8b4b-102">How to Enlist an Orchestration</span></span>
<span data-ttu-id="d8b4b-103">このトピックでは、BizTalk Server 管理コンソールを使用して、オーケストレーションをホストに参加させる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d8b4b-103">This topic describes how to use the BizTalk Server Administration console to enlist an orchestration into a host.</span></span> <span data-ttu-id="d8b4b-104">オーケストレーションは参加させて初めて開始できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d8b4b-104">The orchestration must be enlisted before you can start it.</span></span>  
  
 <span data-ttu-id="d8b4b-105">オーケストレーションを参加させる際は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="d8b4b-105">When enlisting an orchestration, bear in mind the following points:</span></span>  
  
-   <span data-ttu-id="d8b4b-106">**参加させる前に、オーケストレーションをバインドする必要があります。**</span><span class="sxs-lookup"><span data-stu-id="d8b4b-106">**The orchestration must be bound before you can enlist it.**</span></span> <span data-ttu-id="d8b4b-107">オーケストレーションのバインドを構成する方法の詳細については、次を参照してください。[オーケストレーションのバインドを構成する方法](../core/how-to-configure-bindings-for-an-orchestration.md)します。</span><span class="sxs-lookup"><span data-stu-id="d8b4b-107">For instructions on configuring bindings for orchestrations, see [How to Configure Bindings for an Orchestration](../core/how-to-configure-bindings-for-an-orchestration.md).</span></span>  
  
-   <span data-ttu-id="d8b4b-108">**サブスクリプションは自動的に作成されます。**</span><span class="sxs-lookup"><span data-stu-id="d8b4b-108">**Subscriptions are automatically created.**</span></span> <span data-ttu-id="d8b4b-109">オーケストレーションの参加プロセスを経て、必要なサブスクリプションがメッセージ ボックス データベースに作成されます。</span><span class="sxs-lookup"><span data-stu-id="d8b4b-109">The orchestration enlistment process creates the necessary subscriptions in the MessageBox database.</span></span>  
  
-   <span data-ttu-id="d8b4b-110">**アプリケーションをインストールする必要があります。**</span><span class="sxs-lookup"><span data-stu-id="d8b4b-110">**You must install the application.**</span></span> <span data-ttu-id="d8b4b-111">オーケストレーションを実行するすべてのコンピューターに、そのオーケストレーションが含まれているアプリケーションをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8b4b-111">You must install the application containing the orchestration on all of computers where the orchestration will run.</span></span> <span data-ttu-id="d8b4b-112">詳細については、次を参照してください。 [BizTalk アプリケーションをインストールする方法](../core/how-to-install-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="d8b4b-112">For more information, see [How to Install a BizTalk Application](../core/how-to-install-a-biztalk-application.md).</span></span>  
  
-   <span data-ttu-id="d8b4b-113">**呼び出し元のオーケストレーションは、呼び出し先オーケストレーションと同じホストにバインドする必要があります。**</span><span class="sxs-lookup"><span data-stu-id="d8b4b-113">**A calling orchestration must be bound to the same host as the called orchestration.**</span></span> <span data-ttu-id="d8b4b-114">呼び出し元オーケストレーションは、呼び出し先オーケストレーションと同じホストにバインドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8b4b-114">Any orchestration that is called by another orchestration must be bound to the same host as the calling orchestration.</span></span>  
  
-   <span data-ttu-id="d8b4b-115">**依存オーケストレーションを登録する必要があります。**</span><span class="sxs-lookup"><span data-stu-id="d8b4b-115">**You should also enlist dependent orchestrations.**</span></span> <span data-ttu-id="d8b4b-116">オーケストレーションを参加させるとき、依存オーケストレーションがあれば、それらも一緒に参加させないと、依存オーケストレーションにサブスクリプションが割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="d8b4b-116">If you enlist an orchestration but do not enlist any dependent orchestrations, the dependent orchestrations will not have any subscriptions.</span></span> <span data-ttu-id="d8b4b-117">依存オーケストレーションにサブスクリプションがないと、メッセージに対応するサブスクリプションが存在しないため、メッセージが削除または保留される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d8b4b-117">A dependent orchestration without subscriptions may drop or suspend messages because there is no subscription for the messages to match.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d8b4b-118">アプリケーション開発者が開発プロセス中にオーケストレーションを参加させてその機能をテストするには、このトピックの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d8b4b-118">The application developer can enlist an orchestration to test its functionality during the development process  by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d8b4b-119">前提条件</span><span class="sxs-lookup"><span data-stu-id="d8b4b-119">Prerequisites</span></span>  
 <span data-ttu-id="d8b4b-120">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8b4b-120">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="d8b4b-121">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="d8b4b-121">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-enlist-an-orchestration"></a><span data-ttu-id="d8b4b-122">オーケストレーションを参加させるには</span><span class="sxs-lookup"><span data-stu-id="d8b4b-122">To enlist an orchestration</span></span>  
  
1. <span data-ttu-id="d8b4b-123">クリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="d8b4b-123">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="d8b4b-124">コンソール ツリーで、展開**BizTalk Server 管理**展開し、BizTalk グループを展開し、**アプリケーション**、し、参加させるオーケストレーションを含むアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="d8b4b-124">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the orchestration that you want to enlist.</span></span>  
  
3. <span data-ttu-id="d8b4b-125">クリックして**オーケストレーション**をクリックして、参加させ、オーケストレーションを右クリックして**参加**します。</span><span class="sxs-lookup"><span data-stu-id="d8b4b-125">Click **Orchestrations**, right-click the orchestration to enlist, and then click **Enlist**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d8b4b-126">一度に複数のオーケストレーションを参加させるし、shift キーを押しながら各オーケストレーションを参加させることを選択、オーケストレーションを右クリックし、**参加**します。</span><span class="sxs-lookup"><span data-stu-id="d8b4b-126">To enlist multiple orchestrations at once, hold down the shift key and select each orchestration to enlist, right-click an orchestration, and then click **Enlist**.</span></span>  
  
    <span data-ttu-id="d8b4b-127">オーケストレーションが登録され、適切なサブスクリプションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d8b4b-127">The orchestration is enlisted and the appropriate subscriptions are created.</span></span> <span data-ttu-id="d8b4b-128">オーケストレーションは停止状態になります。</span><span class="sxs-lookup"><span data-stu-id="d8b4b-128">The orchestration is in the stopped state.</span></span> <span data-ttu-id="d8b4b-129">受信メッセージの処理を開始するにする必要があります明示的に開始するオーケストレーションをそれを右クリックして**開始**します。</span><span class="sxs-lookup"><span data-stu-id="d8b4b-129">To start processing incoming messages, you must explicitly start the orchestration by right-clicking it and clicking **Start**.</span></span> <span data-ttu-id="d8b4b-130">詳細については、次を参照してください。[オーケストレーションを開始する方法](../core/how-to-start-an-orchestration.md)します。</span><span class="sxs-lookup"><span data-stu-id="d8b4b-130">For more information, see [How to Start an Orchestration](../core/how-to-start-an-orchestration.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8b4b-131">参照</span><span class="sxs-lookup"><span data-stu-id="d8b4b-131">See Also</span></span>  
 <span data-ttu-id="d8b4b-132">[オーケストレーションの管理](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="d8b4b-132">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 [<span data-ttu-id="d8b4b-133">オーケストレーションを参加解除する方法</span><span class="sxs-lookup"><span data-stu-id="d8b4b-133">How to Unenlist an Orchestration</span></span>](../core/how-to-unenlist-an-orchestration.md)