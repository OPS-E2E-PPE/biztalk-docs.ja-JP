---
title: オーケストレーションの追跡を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, tracking
- orchestrations, HAT
- managing [orchestrations], tracking
- configuring [HAT tracking], orchestrations
- tracking, orchestrations
- HAT, orchestrations
ms.assetid: 8f5ed525-11f8-4bef-95c4-cfe9c971b663
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c64d7521bf6d65458f66bb0ef06d08421edf1b4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013195"
---
# <a name="how-to-configure-tracking-for-an-orchestration"></a><span data-ttu-id="fdac0-102">オーケストレーションの追跡を構成する方法</span><span class="sxs-lookup"><span data-stu-id="fdac0-102">How to Configure Tracking for an Orchestration</span></span>
<span data-ttu-id="fdac0-103">このトピックでは、BizTalk Server 管理コンソールを使用して、オーケストレーションの追跡を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fdac0-103">This topic describes how to use the BizTalk Server Administration console to configure tracking for an orchestration.</span></span>  
  
 <span data-ttu-id="fdac0-104">作成とクエリの使用に関する詳細については、次を参照してください。 [、BizTalk Server 管理コンソールを使用して](../core/using-the-biztalk-server-administration-console.md)します。</span><span class="sxs-lookup"><span data-stu-id="fdac0-104">For more information about creating and using queries, see [Using the BizTalk Server Administration Console](../core/using-the-biztalk-server-administration-console.md).</span></span> <span data-ttu-id="fdac0-105">追跡機能の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[追跡メッセージを表示し、インスタンス データ](../core/viewing-tracked-message-and-instance-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="fdac0-105">For more information about the tracking features of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Viewing Tracked Message and Instance Data](../core/viewing-tracked-message-and-instance-data.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fdac0-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="fdac0-106">Prerequisites</span></span>  
 <span data-ttu-id="fdac0-107">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fdac0-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="fdac0-108">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="fdac0-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-tracking-for-an-orchestration"></a><span data-ttu-id="fdac0-109">オーケストレーションの追跡を構成するには</span><span class="sxs-lookup"><span data-stu-id="fdac0-109">To configure tracking for an orchestration</span></span>  
  
1. <span data-ttu-id="fdac0-110">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="fdac0-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="fdac0-111">コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]展開し、BizTalk グループを展開し、**アプリケーション**、し、追跡を構成するオーケストレーションを含むアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="fdac0-111">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, expand **Applications**, and then expand the application containing the orchestration for which you want to configure tracking.</span></span>  
  
3. <span data-ttu-id="fdac0-112">クリックして**オーケストレーション**をクリックして、追跡を構成するオーケストレーションを右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="fdac0-112">Click **Orchestrations**, right-click the orchestration for which you want to configure tracking, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="fdac0-113">をクリックして、**追跡**タブや次の表に示すように、必要な追跡オプションを選択します をクリックし、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="fdac0-113">Click the **Tracking** tab, select the tracking options you want, as described in the following table, and then click **OK**.</span></span>  
  
   |<span data-ttu-id="fdac0-114">オプション</span><span class="sxs-lookup"><span data-stu-id="fdac0-114">Option</span></span>|<span data-ttu-id="fdac0-115">説明</span><span class="sxs-lookup"><span data-stu-id="fdac0-115">Description</span></span>|  
   |------------|-----------------|  
   |<span data-ttu-id="fdac0-116">**イベントの追跡 - オーケストレーションの開始と終了**</span><span class="sxs-lookup"><span data-stu-id="fdac0-116">**Track Events - Orchestration start and end**</span></span>|<span data-ttu-id="fdac0-117">ビジネス プロセス全体の処理の前後にオーケストレーション インスタンスを追跡するには、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="fdac0-117">Select this check box to track the orchestration instance before and after processing of the entire business process.</span></span> <span data-ttu-id="fdac0-118">オーケストレーションの追跡を行うことで、追跡クエリ結果ビューでインスタンスを確認できるようになります。</span><span class="sxs-lookup"><span data-stu-id="fdac0-118">Orchestration tracking enables you to see the instances in the tracking query result views.</span></span>|  
   |<span data-ttu-id="fdac0-119">**イベントの追跡 - メッセージの送信および受信**</span><span class="sxs-lookup"><span data-stu-id="fdac0-119">**Track Events - Message send and receive**</span></span>|<span data-ttu-id="fdac0-120">メッセージの送信イベントと受信イベントを追跡する場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="fdac0-120">Select this check box to track message send and receive events.</span></span> <span data-ttu-id="fdac0-121">このチェック ボックスは選択した場合にのみ使用可能な**オーケストレーションの開始と終了**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="fdac0-121">This check box is available only if you select the **Orchestration start and end** check box.</span></span>|  
   |<span data-ttu-id="fdac0-122">**イベントの追跡の図形の開始と終了**</span><span class="sxs-lookup"><span data-stu-id="fdac0-122">**Track Events - Shape start and end**</span></span>|<span data-ttu-id="fdac0-123">オーケストレーション デバッガーでオーケストレーション インスタンスをデバッグする必要がある場合はこのチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="fdac0-123">Select this check box when you need to debug orchestration instances in the Orchestration Debugger.</span></span> <span data-ttu-id="fdac0-124">このチェック ボックスがオンの場合、オーケストレーション デバッガーのイベントの一覧が設定されます。</span><span class="sxs-lookup"><span data-stu-id="fdac0-124">When this check box is selected, the event list in the Orchestration Debugger is populated.</span></span> <span data-ttu-id="fdac0-125">このチェック ボックスは選択した場合にのみ使用可能な**オーケストレーションの開始と終了**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="fdac0-125">This check box is available only if you select the **Orchestration start and end** check box.</span></span>|  
   |<span data-ttu-id="fdac0-126">**オーケストレーション処理の前に、のメッセージ本文の追跡**</span><span class="sxs-lookup"><span data-stu-id="fdac0-126">**Track Message Bodies - Before orchestration processing**</span></span>|<span data-ttu-id="fdac0-127">オーケストレーション インスタンスによる処理の前に実際のメッセージの内容を保存および追跡するには、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="fdac0-127">Select this check box to save and track the actual message content prior to processing by the orchestration instance.</span></span> <span data-ttu-id="fdac0-128">このチェック ボックスは選択した場合にのみ使用可能な**メッセージの送信および受信**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="fdac0-128">This check box is available only if you select the **Message send and receive** check box.</span></span>|  
   |<span data-ttu-id="fdac0-129">**オーケストレーション処理の後のメッセージ本文の追跡**</span><span class="sxs-lookup"><span data-stu-id="fdac0-129">**Track Message Bodies - After orchestration processing**</span></span>|<span data-ttu-id="fdac0-130">オーケストレーション インスタンスによる処理の後に実際のメッセージの内容を保存および追跡するには、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="fdac0-130">Select this check box to save and track the actual message content after processing by the orchestration instance.</span></span> <span data-ttu-id="fdac0-131">このチェック ボックスは選択した場合にのみ使用可能な**メッセージの送信および受信**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="fdac0-131">This check box is available only if you select the **Message send and receive** check box.</span></span>|  
   |<span data-ttu-id="fdac0-132">**メッセージのプロパティ - 受信メッセージを追跡します。**</span><span class="sxs-lookup"><span data-stu-id="fdac0-132">**Track Message Properties - Incoming messages**</span></span>|<span data-ttu-id="fdac0-133">受信メッセージの昇格させたプロパティを追跡する場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="fdac0-133">Select this check box to track the promoted properties of an inbound message.</span></span>|  
   |<span data-ttu-id="fdac0-134">**送信メッセージのメッセージ プロパティを追跡します。**</span><span class="sxs-lookup"><span data-stu-id="fdac0-134">**Track Message Properties - Outgoing messages**</span></span>|<span data-ttu-id="fdac0-135">送信メッセージの昇格させたプロパティを追跡するには、このチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="fdac0-135">Select this check box to track the promoted properties of an outbound message.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fdac0-136">参照</span><span class="sxs-lookup"><span data-stu-id="fdac0-136">See Also</span></span>  
 [<span data-ttu-id="fdac0-137">オーケストレーションの管理</span><span class="sxs-lookup"><span data-stu-id="fdac0-137">Managing Orchestrations</span></span>](../core/managing-orchestrations.md)