---
title: "オーケストレーションの追跡を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, tracking
- orchestrations, HAT
- managing [orchestrations], tracking
- configuring [HAT tracking], orchestrations
- tracking, orchestrations
- HAT, orchestrations
ms.assetid: 8f5ed525-11f8-4bef-95c4-cfe9c971b663
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ebae70ec70fb58a4a935be6b2c46f39cfafba59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-tracking-for-an-orchestration"></a><span data-ttu-id="91dfb-102">オーケストレーションの追跡を構成する方法</span><span class="sxs-lookup"><span data-stu-id="91dfb-102">How to Configure Tracking for an Orchestration</span></span>
<span data-ttu-id="91dfb-103">このトピックでは、BizTalk Server 管理コンソールを使用して、オーケストレーションの追跡を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="91dfb-103">This topic describes how to use the BizTalk Server Administration console to configure tracking for an orchestration.</span></span>  
  
 <span data-ttu-id="91dfb-104">詳細については、作成して、クエリを使用して、次を参照してください。 [、BizTalk Server 管理コンソールを使用して](../core/using-the-biztalk-server-administration-console.md)です。</span><span class="sxs-lookup"><span data-stu-id="91dfb-104">For more information about creating and using queries, see [Using the BizTalk Server Administration Console](../core/using-the-biztalk-server-administration-console.md).</span></span> <span data-ttu-id="91dfb-105">追跡機能の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[追跡メッセージを表示し、インスタンス データ](../core/viewing-tracked-message-and-instance-data.md)です。</span><span class="sxs-lookup"><span data-stu-id="91dfb-105">For more information about the tracking features of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Viewing Tracked Message and Instance Data](../core/viewing-tracked-message-and-instance-data.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="91dfb-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="91dfb-106">Prerequisites</span></span>  
 <span data-ttu-id="91dfb-107">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="91dfb-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="91dfb-108">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="91dfb-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-tracking-for-an-orchestration"></a><span data-ttu-id="91dfb-109">オーケストレーションの追跡を構成するには</span><span class="sxs-lookup"><span data-stu-id="91dfb-109">To configure tracking for an orchestration</span></span>  
  
1.  <span data-ttu-id="91dfb-110">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="91dfb-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="91dfb-111">コンソール ツリーで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、BizTalk グループを展開し、**アプリケーション**、し、追跡を構成する場合、オーケストレーションを含むアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="91dfb-111">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, expand **Applications**, and then expand the application containing the orchestration for which you want to configure tracking.</span></span>  
  
3.  <span data-ttu-id="91dfb-112">をクリックして**オーケストレーション**、追跡を構成しオーケストレーションを右クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="91dfb-112">Click **Orchestrations**, right-click the orchestration for which you want to configure tracking, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="91dfb-113">クリックして、**追跡**タブを次の表に示すように、必要な追跡オプションを選択し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="91dfb-113">Click the **Tracking** tab, select the tracking options you want, as described in the following table, and then click **OK**.</span></span>  
  
    |<span data-ttu-id="91dfb-114">オプション</span><span class="sxs-lookup"><span data-stu-id="91dfb-114">Option</span></span>|<span data-ttu-id="91dfb-115">Description</span><span class="sxs-lookup"><span data-stu-id="91dfb-115">Description</span></span>|  
    |------------|-----------------|  
    |<span data-ttu-id="91dfb-116">**イベントの追跡-オーケストレーションの開始と終了**</span><span class="sxs-lookup"><span data-stu-id="91dfb-116">**Track Events - Orchestration start and end**</span></span>|<span data-ttu-id="91dfb-117">ビジネス プロセス全体の処理の前後にオーケストレーション インスタンスを追跡するには、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="91dfb-117">Select this check box to track the orchestration instance before and after processing of the entire business process.</span></span> <span data-ttu-id="91dfb-118">オーケストレーションの追跡を行うことで、追跡クエリ結果ビューでインスタンスを確認できるようになります。</span><span class="sxs-lookup"><span data-stu-id="91dfb-118">Orchestration tracking enables you to see the instances in the tracking query result views.</span></span>|  
    |<span data-ttu-id="91dfb-119">**イベントの追跡 - メッセージの送信および受信**</span><span class="sxs-lookup"><span data-stu-id="91dfb-119">**Track Events - Message send and receive**</span></span>|<span data-ttu-id="91dfb-120">メッセージの送信イベントと受信イベントを追跡する場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="91dfb-120">Select this check box to track message send and receive events.</span></span> <span data-ttu-id="91dfb-121">このチェック ボックスは選択した場合にのみ使用可能な**オーケストレーションの開始と終了**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="91dfb-121">This check box is available only if you select the **Orchestration start and end** check box.</span></span>|  
    |<span data-ttu-id="91dfb-122">**イベントの追跡-図形の開始と終了**</span><span class="sxs-lookup"><span data-stu-id="91dfb-122">**Track Events - Shape start and end**</span></span>|<span data-ttu-id="91dfb-123">オーケストレーション デバッガーでオーケストレーション インスタンスをデバッグする必要がある場合はこのチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="91dfb-123">Select this check box when you need to debug orchestration instances in the Orchestration Debugger.</span></span> <span data-ttu-id="91dfb-124">このチェック ボックスがオンの場合、オーケストレーション デバッガーのイベントの一覧が設定されます。</span><span class="sxs-lookup"><span data-stu-id="91dfb-124">When this check box is selected, the event list in the Orchestration Debugger is populated.</span></span> <span data-ttu-id="91dfb-125">このチェック ボックスは選択した場合にのみ使用可能な**オーケストレーションの開始と終了**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="91dfb-125">This check box is available only if you select the **Orchestration start and end** check box.</span></span>|  
    |<span data-ttu-id="91dfb-126">**オーケストレーション処理の前に、のメッセージ本文の追跡**</span><span class="sxs-lookup"><span data-stu-id="91dfb-126">**Track Message Bodies - Before orchestration processing**</span></span>|<span data-ttu-id="91dfb-127">オーケストレーション インスタンスによる処理の前に実際のメッセージの内容を保存および追跡するには、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="91dfb-127">Select this check box to save and track the actual message content prior to processing by the orchestration instance.</span></span> <span data-ttu-id="91dfb-128">このチェック ボックスは選択した場合にのみ使用可能な**メッセージの送信および受信**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="91dfb-128">This check box is available only if you select the **Message send and receive** check box.</span></span>|  
    |<span data-ttu-id="91dfb-129">**オーケストレーション処理の後にメッセージ本文の追跡**</span><span class="sxs-lookup"><span data-stu-id="91dfb-129">**Track Message Bodies - After orchestration processing**</span></span>|<span data-ttu-id="91dfb-130">オーケストレーション インスタンスによる処理の後に実際のメッセージの内容を保存および追跡するには、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="91dfb-130">Select this check box to save and track the actual message content after processing by the orchestration instance.</span></span> <span data-ttu-id="91dfb-131">このチェック ボックスは選択した場合にのみ使用可能な**メッセージの送信および受信**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="91dfb-131">This check box is available only if you select the **Message send and receive** check box.</span></span>|  
    |<span data-ttu-id="91dfb-132">**メッセージのプロパティ - 着信メッセージを追跡します。**</span><span class="sxs-lookup"><span data-stu-id="91dfb-132">**Track Message Properties - Incoming messages**</span></span>|<span data-ttu-id="91dfb-133">受信メッセージの昇格させたプロパティを追跡する場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="91dfb-133">Select this check box to track the promoted properties of an inbound message.</span></span>|  
    |<span data-ttu-id="91dfb-134">**送信メッセージのメッセージ プロパティを追跡します。**</span><span class="sxs-lookup"><span data-stu-id="91dfb-134">**Track Message Properties - Outgoing messages**</span></span>|<span data-ttu-id="91dfb-135">送信メッセージの昇格させたプロパティを追跡するには、このチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="91dfb-135">Select this check box to track the promoted properties of an outbound message.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="91dfb-136">参照</span><span class="sxs-lookup"><span data-stu-id="91dfb-136">See Also</span></span>  
 [<span data-ttu-id="91dfb-137">オーケストレーションの管理</span><span class="sxs-lookup"><span data-stu-id="91dfb-137">Managing Orchestrations</span></span>](../core/managing-orchestrations.md)